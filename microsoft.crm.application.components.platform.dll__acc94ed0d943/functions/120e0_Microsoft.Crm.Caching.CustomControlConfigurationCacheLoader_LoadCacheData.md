# Microsoft.Crm.Caching.CustomControlConfigurationCacheLoader::LoadCacheData

- ea: `0x120e0`
- end: `0x12167`
- name: `Microsoft.Crm.Caching.CustomControlConfigurationCacheLoader::LoadCacheData`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x120e0`
- `0x5be20`
- `0x94440`
- `0x94500`

## string_xrefs

- `0x120e0`: `GetCustomControlConfiguration`
- `0x120f7`: `customcontroldefaultconfig`
- `0x12108`: `controldescriptionxml`
- `0x1214f`: `controldescriptionxml`

## pseudocode

```c

```

## disassembly

```asm
0x120e0  ldstr    aGetcustomcontr// "GetCustomControlConfiguration"
0x120e5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::.ctor(string)
0x120ea  stloc.0
0x120eb  ldloc.0
0x120ec  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Start()
0x120f1  ldsfld   string [mscorlib]System.String::Empty
0x120f6  stloc.1
0x120f7  ldstr    aCustomcontrold// "customcontroldefaultconfig"
0x120fc  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x12101  stloc.2
0x12102  ldloc.2
0x12103  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x12108  ldstr    aControldescrip// "controldescriptionxml"
0x1210d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x12112  ldloc.2
0x12113  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x12118  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x1211d  ldc.i4.0
0x1211e  ldc.i4.1
0x1211f  newarr   [mscorlib]System.Object
0x12124  dup
0x12125  ldc.i4.0
0x12126  ldarg.1
0x12127  box      [mscorlib]System.Int32
0x1212c  stelem.ref
0x1212d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x12132  ldloc.2
0x12133  ldarg.2
0x12134  newobj   instance void Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x12139  callvirt instance class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::Execute()
0x1213e  stloc.3
0x1213f  ldloc.3
0x12140  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x12145  ldc.i4.1
0x12146  bne.un.s loc_1215F
0x12148  ldloc.3
0x12149  ldc.i4.0
0x1214a  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x1214f  ldstr    aControldescrip// "controldescriptionxml"
0x12154  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x12159  castclass [mscorlib]System.String
0x1215e  stloc.1
0x1215f  ldloc.0
0x12160  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.MetricsStopwatch::Stop()
0x12165  ldloc.1
0x12166  ret
```
