# Microsoft.Crm.ServiceBus.ServiceBusService::ConvertToRemoteExecutionContext

- ea: `0xfe0`
- end: `0x1184`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::ConvertToRemoteExecutionContext`
- size: `420`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xe20`
- `0xe80`
- `0xfe0`

## callees

- `0xfe0`
- `0x1190`
- `0x1350`

## pseudocode

```c

```

## disassembly

```asm
0xfe0  ldarg.0
0xfe1  brtrue.s loc_FE5
0xfe3  ldnull
0xfe4  ret
0xfe5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::.ctor()
0xfea  stloc.0
0xfeb  ldloc.0
0xfec  ldarg.0
0xfed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_BusinessUnitId()
0xff2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_BusinessUnitId(valuetype [mscorlib]System.Guid)
0xff7  ldloc.0
0xff8  ldarg.0
0xff9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0xffe  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_CorrelationId(valuetype [mscorlib]System.Guid)
0x1003  ldloc.0
0x1004  ldarg.0
0x1005  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Depth()
0x100a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_Depth(int32)
0x100f  ldloc.0
0x1010  ldarg.0
0x1011  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InitiatingUserId()
0x1016  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_InitiatingUserId(valuetype [mscorlib]System.Guid)
0x101b  ldarg.0
0x101c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x1021  ldloc.0
0x1022  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_InputParameters()
0x1027  ldstr    aInputparameter// "InputParameters"
0x102c  ldarg.0
0x102d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x1032  call     void Microsoft.Crm.ServiceBus.ServiceBusService::CopyParameterCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection destination, string parameterCollectionName, valuetype [mscorlib]System.Guid operationId)
0x1037  ldloc.0
0x1038  ldarg.0
0x1039  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_IsExecutingOffline()
0x103e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_IsExecutingOffline(bool)
0x1043  ldloc.0
0x1044  ldarg.0
0x1045  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_IsOfflinePlayback()
0x104a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_IsOfflinePlayback(bool)
0x104f  ldloc.0
0x1050  ldarg.0
0x1051  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_IsInTransaction()
0x1056  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_IsInTransaction(bool)
0x105b  ldloc.0
0x105c  ldarg.0
0x105d  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_IsolationMode()
0x1062  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_IsolationMode(int32)
0x1067  ldloc.0
0x1068  ldarg.0
0x1069  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x106e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_MessageName(string)
0x1073  ldloc.0
0x1074  ldarg.0
0x1075  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Mode()
0x107a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_Mode(int32)
0x107f  ldloc.0
0x1080  ldarg.0
0x1081  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationCreatedOn()
0x1086  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_OperationCreatedOn(valuetype [mscorlib]System.DateTime)
0x108b  ldloc.0
0x108c  ldarg.0
0x108d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x1092  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_OperationId(valuetype [mscorlib]System.Guid)
0x1097  ldloc.0
0x1098  ldarg.0
0x1099  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x109e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x10a3  ldloc.0
0x10a4  ldarg.0
0x10a5  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationName()
0x10aa  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_OrganizationName(string)
0x10af  ldarg.0
0x10b0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OutputParameters()
0x10b5  ldloc.0
0x10b6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OutputParameters()
0x10bb  ldstr    aOutputparamete// "OutputParameters"
0x10c0  ldarg.0
0x10c1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x10c6  call     void Microsoft.Crm.ServiceBus.ServiceBusService::CopyParameterCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection destination, string parameterCollectionName, valuetype [mscorlib]System.Guid operationId)
0x10cb  ldloc.0
0x10cc  ldarg.0
0x10cd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x10d2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_OwningExtension(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x10d7  ldarg.0
0x10d8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PreEntityImages()
0x10dd  ldloc.0
0x10de  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_PreEntityImages()
0x10e3  call     void Microsoft.Crm.ServiceBus.ServiceBusService::CopyEntityImageCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection destination)
0x10e8  ldarg.0
0x10e9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PostEntityImages()
0x10ee  ldloc.0
0x10ef  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_PostEntityImages()
0x10f4  call     void Microsoft.Crm.ServiceBus.ServiceBusService::CopyEntityImageCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection destination)
0x10f9  ldloc.0
0x10fa  ldarg.0
0x10fb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PrimaryEntityId()
0x1100  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_PrimaryEntityId(valuetype [mscorlib]System.Guid)
0x1105  ldloc.0
0x1106  ldarg.0
0x1107  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PrimaryEntityName()
0x110c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_PrimaryEntityName(string)
0x1111  ldloc.0
0x1112  ldarg.0
0x1113  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SecondaryEntityName()
0x1118  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_SecondaryEntityName(string)
0x111d  ldarg.0
0x111e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0x1123  ldloc.0
0x1124  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_SharedVariables()
0x1129  ldstr    aSharedvariable// "SharedVariables"
0x112e  ldarg.0
0x112f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x1134  call     void Microsoft.Crm.ServiceBus.ServiceBusService::CopyParameterCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection source, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection destination, string parameterCollectionName, valuetype [mscorlib]System.Guid operationId)
0x1139  ldloc.0
0x113a  ldarg.0
0x113b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_UserId()
0x1140  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_UserId(valuetype [mscorlib]System.Guid)
0x1145  ldloc.0
0x1146  ldarg.0
0x1147  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_RequestId()
0x114c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_RequestId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x1151  ldarg.0
0x1152  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext
0x1157  stloc.1
0x1158  ldloc.1
0x1159  brfalse.s loc_117A
0x115b  ldloc.0
0x115c  ldloc.1
0x115d  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext::get_Stage()
0x1162  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_Stage(int32)
0x1167  ldloc.0
0x1168  ldloc.1
0x1169  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext::get_ParentContext()
0x116e  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext Microsoft.Crm.ServiceBus.ServiceBusService::ConvertToRemoteExecutionContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0x1173  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_ParentContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext)
0x1178  br.s     loc_1182
0x117a  ldloc.0
0x117b  ldc.i4.s 0x32
0x117d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::set_Stage(int32)
0x1182  ldloc.0
0x1183  ret
```
