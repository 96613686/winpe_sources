# Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandler::SetSyncWorkflowAttributes

- ea: `0x66120`
- end: `0x6617b`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandler::SetSyncWorkflowAttributes`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x654f0`

## callees

- `0x66180`

## string_xrefs

- `0x66128`: `CreateStage`
- `0x66122`: `createstage`
- `0x6613a`: `UpdateStage`
- `0x66134`: `updatestage`
- `0x6614c`: `DeleteStage`
- `0x66146`: `deletestage`

## pseudocode

```c

```

## disassembly

```asm
0x66120  ldarg.0
0x66121  ldarg.1
0x66122  ldstr    aCreatestage_0// "createstage"
0x66127  ldarg.2
0x66128  ldstr    aCreatestage// "CreateStage"
0x6612d  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandler::SetIntAttributeFromNode(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity workflow, string attributeName, class [System.Xml]System.Xml.XmlNode workflowNode, string nodeName)
0x66132  ldarg.0
0x66133  ldarg.1
0x66134  ldstr    aUpdatestage_0// "updatestage"
0x66139  ldarg.2
0x6613a  ldstr    aUpdatestage// "UpdateStage"
0x6613f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandler::SetIntAttributeFromNode(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity workflow, string attributeName, class [System.Xml]System.Xml.XmlNode workflowNode, string nodeName)
0x66144  ldarg.0
0x66145  ldarg.1
0x66146  ldstr    aDeletestage_0// "deletestage"
0x6614b  ldarg.2
0x6614c  ldstr    aDeletestage// "DeleteStage"
0x66151  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandler::SetIntAttributeFromNode(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity workflow, string attributeName, class [System.Xml]System.Xml.XmlNode workflowNode, string nodeName)
0x66156  ldarg.0
0x66157  ldarg.1
0x66158  ldstr    aRank_0// "rank"
0x6615d  ldarg.2
0x6615e  ldstr    aRank// "Rank"
0x66163  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandler::SetIntAttributeFromNode(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity workflow, string attributeName, class [System.Xml]System.Xml.XmlNode workflowNode, string nodeName)
0x66168  ldarg.0
0x66169  ldarg.1
0x6616a  ldstr    aRunas_0// "runas"
0x6616f  ldarg.2
0x66170  ldstr    aRunas// "RunAs"
0x66175  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportWorkflowSubHandler::SetIntAttributeFromNode(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity workflow, string attributeName, class [System.Xml]System.Xml.XmlNode workflowNode, string nodeName)
0x6617a  ret
```
