# deepflow-dashboards

An automated observability platform for cloud-native developers.

## Dashboard 规范

dashboard 增加 datasource 变量，手动改为 `"selected": true,"value": "1"`：

```json
      {
        "current": {
          "selected": true,
          "value": "1"
        },
        "hide": 0,
        "includeAll": false,
        "label": "Data Source",
        "multi": false,
        "name": "datasource",
        "options": [],
        "query": "deepflow-querier-datasource",
        "queryValue": "",
        "refresh": 1,
        "regex": "",
        "skipUrlSync": false,
        "type": "datasource"
      }
```

所有 panel 的 datasource 使用 $datasource：
```json
        {
          "datasource": {
            "type": "deepflow-querier-datasource",
            "uid": "${datasource}"
          }
```

dashboard title 和uid 要固定：
```json
  "title": "Network - K8s Pod",
  "uid": "Network_K8s_Pod",
```