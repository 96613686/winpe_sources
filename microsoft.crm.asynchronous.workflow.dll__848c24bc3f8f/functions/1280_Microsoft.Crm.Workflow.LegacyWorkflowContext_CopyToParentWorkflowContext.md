# Microsoft.Crm.Workflow.LegacyWorkflowContext::CopyToParentWorkflowContext

- ea: `0x1280`
- end: `0x135b`
- name: `Microsoft.Crm.Workflow.LegacyWorkflowContext::CopyToParentWorkflowContext`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1240`
- `0x1280`

## pseudocode

```c

```

## disassembly

```asm
0x1280  ldarg.0
0x1281  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Workflow.LegacyWorkflowContext::_inputParameters
0x1286  brfalse.s loc_12B4
0x1288  ldarg.0
0x1289  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x128e  ldarg.0
0x128f  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x1294  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::get_ConversionContext()
0x1299  ldarg.0
0x129a  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Workflow.LegacyWorkflowContext::_inputParameters
0x129f  ldarg.0
0x12a0  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x12a5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x12aa  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.LegacyContextConverters::ConvertPropertyBagToParameterCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection)
0x12af  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::SetInputParameters(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection)
0x12b4  ldarg.0
0x12b5  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Workflow.LegacyWorkflowContext::_outputParameters
0x12ba  brfalse.s loc_12E8
0x12bc  ldarg.0
0x12bd  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x12c2  ldarg.0
0x12c3  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x12c8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::get_ConversionContext()
0x12cd  ldarg.0
0x12ce  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Workflow.LegacyWorkflowContext::_outputParameters
0x12d3  ldarg.0
0x12d4  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x12d9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OutputParameters()
0x12de  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.LegacyContextConverters::ConvertPropertyBagToParameterCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection)
0x12e3  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::SetOutputParameters(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection)
0x12e8  ldarg.0
0x12e9  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Workflow.LegacyWorkflowContext::_sharedVariables
0x12ee  brfalse.s loc_131C
0x12f0  ldarg.0
0x12f1  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x12f6  ldarg.0
0x12f7  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x12fc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::get_ConversionContext()
0x1301  ldarg.0
0x1302  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Workflow.LegacyWorkflowContext::_sharedVariables
0x1307  ldarg.0
0x1308  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x130d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0x1312  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.LegacyContextConverters::ConvertPropertyBagToParameterCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection)
0x1317  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::SetSharedVariables(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection)
0x131c  ldarg.0
0x131d  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Workflow.LegacyWorkflowContext::_primaryEntityPreImage
0x1322  brfalse.s loc_133B
0x1324  ldarg.0
0x1325  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x132a  ldarg.0
0x132b  ldarg.0
0x132c  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Workflow.LegacyWorkflowContext::_primaryEntityPreImage
0x1331  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection Microsoft.Crm.Workflow.LegacyWorkflowContext::ConvertDynamicEntityToEntityImageCollection(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity dynamicEntity)
0x1336  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::SetPreEntityImages(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection)
0x133b  ldarg.0
0x133c  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Workflow.LegacyWorkflowContext::_primaryEntityPostImage
0x1341  brfalse.s loc_135A
0x1343  ldarg.0
0x1344  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.LegacyWorkflowContext::_workflowContext
0x1349  ldarg.0
0x134a  ldarg.0
0x134b  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Workflow.LegacyWorkflowContext::_primaryEntityPostImage
0x1350  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection Microsoft.Crm.Workflow.LegacyWorkflowContext::ConvertDynamicEntityToEntityImageCollection(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity dynamicEntity)
0x1355  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::SetPostEntityImages(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection)
0x135a  ret
```
