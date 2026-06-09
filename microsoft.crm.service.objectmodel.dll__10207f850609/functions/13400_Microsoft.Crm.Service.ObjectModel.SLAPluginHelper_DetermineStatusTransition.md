# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::DetermineStatusTransition

- ea: `0x13400`
- end: `0x134a5`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::DetermineStatusTransition`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x132b0`

## callees

- `0x13400`
- `0x134b0`
- `0x13500`

## pseudocode

```c

```

## disassembly

```asm
0x13400  ldarg.0
0x13401  ldarg.1
0x13402  call     bool Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HasStatusCode(class [mscorlib]System.Collections.Generic.List`1<string> List, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Entity)
0x13407  stloc.0
0x13408  ldarg.0
0x13409  ldarg.2
0x1340a  call     bool Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::HasStatusCode(class [mscorlib]System.Collections.Generic.List`1<string> List, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Entity)
0x1340f  stloc.1
0x13410  ldarg.1
0x13411  brfalse.s loc_1343A
0x13413  ldarg.2
0x13414  brfalse.s loc_1343A
0x13416  ldarg.1
0x13417  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1341c  ldstr    aStatuscode// "statuscode"
0x13421  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x13426  brfalse.s loc_1343A
0x13428  ldarg.2
0x13429  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1342e  ldstr    aStatuscode// "statuscode"
0x13433  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x13438  br.s     loc_1343B
0x1343a  ldc.i4.0
0x1343b  stloc.2
0x1343c  ldarg.1
0x1343d  brfalse.s loc_13466
0x1343f  ldarg.2
0x13440  brfalse.s loc_13466
0x13442  ldarg.1
0x13443  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x13448  ldstr    aStatuscode// "statuscode"
0x1344d  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x13452  brtrue.s loc_13466
0x13454  ldarg.2
0x13455  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1345a  ldstr    aStatuscode// "statuscode"
0x1345f  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x13464  br.s     loc_13467
0x13466  ldc.i4.0
0x13467  stloc.3
0x13468  ldarg.2
0x13469  brtrue.s loc_13471
0x1346b  ldarg.1
0x1346c  ldnull
0x1346d  cgt.un
0x1346f  br.s     loc_13472
0x13471  ldc.i4.0
0x13472  ldloc.0
0x13473  and
0x13474  stloc.s  4
0x13476  ldloc.2
0x13477  ldloc.0
0x13478  and
0x13479  brfalse.s loc_13482
0x1347b  ldloc.1
0x1347c  brfalse.s loc_13480
0x1347e  ldc.i4.1
0x1347f  ret
0x13480  ldc.i4.0
0x13481  ret
0x13482  ldloc.3
0x13483  ldloc.1
0x13484  and
0x13485  brfalse.s loc_13489
0x13487  ldc.i4.2
0x13488  ret
0x13489  ldloc.s  4
0x1348b  brfalse.s loc_1348F
0x1348d  ldc.i4.4
0x1348e  ret
0x1348f  ldloc.1
0x13490  brfalse.s loc_13495
0x13492  ldloc.0
0x13493  brfalse.s loc_134A1
0x13495  ldloc.2
0x13496  brfalse.s loc_134A3
0x13498  ldarg.1
0x13499  ldarg.3
0x1349a  call     bool Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::FromHoldtoInProgress(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1349f  brfalse.s loc_134A3
0x134a1  ldc.i4.3
0x134a2  ret
0x134a3  ldc.i4.5
0x134a4  ret
```
