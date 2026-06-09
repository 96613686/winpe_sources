# Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::GetSlaItemProperties

- ea: `0x930c0`
- end: `0x93269`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::GetSlaItemProperties`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x92f10`

## callees

- `0x930c0`
- `0x93360`

## string_xrefs

- `0x93190`: `applicablewhenxml`
- `0x93195`: `applicablewhenxml`
- `0x931b4`: `successconditionsxml`
- `0x931b9`: `successconditionsxml`

## pseudocode

```c

```

## disassembly

```asm
0x930c0  ldarg.0
0x930c1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::_slaItemProperties
0x930c6  brtrue   loc_93262
0x930cb  ldarg.0
0x930cc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap>::.ctor()
0x930d1  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::_slaItemProperties
0x930d6  ldarg.0
0x930d7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::_slaItemProperties
0x930dc  ldstr    aSlaid// "slaid"
0x930e1  ldstr    aSlaid// "slaid"
0x930e6  ldtoken  [mscorlib]System.Guid
0x930eb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x930f0  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x930f5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap>::Add(var<u1>)
0x930fa  ldarg.0
0x930fb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::_slaItemProperties
0x93100  ldstr    aSlaitemid// "slaitemid"
0x93105  ldstr    aSlaitemid// "slaitemid"
0x9310a  ldtoken  [mscorlib]System.Guid
0x9310f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93114  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93119  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap>::Add(var<u1>)
0x9311e  ldarg.0
0x9311f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::_slaItemProperties
0x93124  ldstr    aRelatedfield// "relatedfield"
0x93129  ldstr    aRelatedfield// "relatedfield"
0x9312e  ldtoken  [mscorlib]System.String
0x93133  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93138  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x9313d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap>::Add(var<u1>)
0x93142  ldarg.0
0x93143  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::_slaItemProperties
0x93148  ldstr    aName// "name"
0x9314d  ldstr    aName// "name"
0x93152  ldtoken  [mscorlib]System.String
0x93157  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9315c  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93161  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap>::Add(var<u1>)
0x93166  ldarg.0
0x93167  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::_slaItemProperties
0x9316c  ldstr    aDescription// "description"
0x93171  ldstr    aDescription// "description"
0x93176  ldtoken  [mscorlib]System.String
0x9317b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93180  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93185  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap>::Add(var<u1>)
0x9318a  ldarg.0
0x9318b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::_slaItemProperties
0x93190  ldstr    aApplicablewhen// "applicablewhenxml"
0x93195  ldstr    aApplicablewhen// "applicablewhenxml"
0x9319a  ldtoken  [mscorlib]System.String
0x9319f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x931a4  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x931a9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap>::Add(var<u1>)
0x931ae  ldarg.0
0x931af  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::_slaItemProperties
0x931b4  ldstr    aSuccessconditi// "successconditionsxml"
0x931b9  ldstr    aSuccessconditi// "successconditionsxml"
0x931be  ldtoken  [mscorlib]System.String
0x931c3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x931c8  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x931cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap>::Add(var<u1>)
0x931d2  ldarg.0
0x931d3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::_slaItemProperties
0x931d8  ldstr    aSequencenumber_0// "sequencenumber"
0x931dd  ldstr    aSequencenumber_0// "sequencenumber"
0x931e2  ldtoken  [mscorlib]System.Int32
0x931e7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x931ec  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x931f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap>::Add(var<u1>)
0x931f6  ldarg.0
0x931f7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::_slaItemProperties
0x931fc  ldstr    aWorkflowid_0// "workflowid"
0x93201  ldstr    aWorkflowid_0// "workflowid"
0x93206  ldtoken  [mscorlib]System.Guid
0x9320b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93210  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93215  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap>::Add(var<u1>)
0x9321a  ldarg.0
0x9321b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::_slaItemProperties
0x93220  ldstr    aFailureafter// "failureafter"
0x93225  ldstr    aFailureafter// "failureafter"
0x9322a  ldtoken  [mscorlib]System.Int32
0x9322f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93234  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93239  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap>::Add(var<u1>)
0x9323e  ldarg.0
0x9323f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::_slaItemProperties
0x93244  ldstr    aWarnafter// "warnafter"
0x93249  ldstr    aWarnafter// "warnafter"
0x9324e  ldtoken  [mscorlib]System.Int32
0x93253  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93258  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x9325d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap>::Add(var<u1>)
0x93262  ldarg.0
0x93263  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.SlaItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.SlaItemConvertor::_slaItemProperties
0x93268  ret
```
