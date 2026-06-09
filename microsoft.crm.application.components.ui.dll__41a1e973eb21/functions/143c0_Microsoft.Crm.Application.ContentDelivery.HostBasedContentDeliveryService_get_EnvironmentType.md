# Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::get_EnvironmentType

- ea: `0x143c0`
- end: `0x14502`
- name: `Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::get_EnvironmentType`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x141b0`

## callees

- `0x143c0`

## string_xrefs

- `0x143e9`: `extest.microsoft.com`
- `0x14401`: `crmlivetie.com`
- `0x14419`: `crmlivetoday.com`
- `0x14431`: `1boxtest.com`
- `0x14449`: `dynamics-int.com`
- `0x14461`: `dynamics.com`
- `0x14479`: `dynamics-tie.com`
- `0x14491`: `dynamics-servicestie.com`
- `0x144a9`: `dynamics-ppe.com`
- `0x144c1`: `powerapps.com`
- `0x144d9`: `flow.microsoft.com`

## pseudocode

```c

```

## disassembly

```asm
0x143c0  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.EnvironmentUtility [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.EnvironmentUtility::get_Instance()
0x143c5  ldloca.s 1
0x143c7  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x143cd  ldloc.1
0x143ce  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.EnvironmentUtility::GetWebServer(valuetype [mscorlib]System.Nullable`1<int32>)
0x143d3  ldc.i4.1
0x143d4  ldloca.s 0
0x143d6  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x143db  brtrue.s loc_143E3
0x143dd  ldstr    aPpe// "ppe"
0x143e2  ret
0x143e3  ldloc.0
0x143e4  callvirt instance string [System]System.Uri::get_Host()
0x143e9  ldstr    aExtestMicrosof// "extest.microsoft.com"
0x143ee  callvirt instance bool [mscorlib]System.String::Contains(string)
0x143f3  brfalse.s loc_143FB
0x143f5  ldstr    aPpe// "ppe"
0x143fa  ret
0x143fb  ldloc.0
0x143fc  callvirt instance string [System]System.Uri::get_Host()
0x14401  ldstr    aCrmlivetieCom// "crmlivetie.com"
0x14406  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1440b  brfalse.s loc_14413
0x1440d  ldstr    aPpe// "ppe"
0x14412  ret
0x14413  ldloc.0
0x14414  callvirt instance string [System]System.Uri::get_Host()
0x14419  ldstr    aCrmlivetodayCo// "crmlivetoday.com"
0x1441e  callvirt instance bool [mscorlib]System.String::Contains(string)
0x14423  brfalse.s loc_1442B
0x14425  ldstr    aPpe// "ppe"
0x1442a  ret
0x1442b  ldloc.0
0x1442c  callvirt instance string [System]System.Uri::get_Host()
0x14431  ldstr    a1boxtestCom// "1boxtest.com"
0x14436  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1443b  brfalse.s loc_14443
0x1443d  ldstr    aPpe// "ppe"
0x14442  ret
0x14443  ldloc.0
0x14444  callvirt instance string [System]System.Uri::get_Host()
0x14449  ldstr    aDynamicsIntCom// "dynamics-int.com"
0x1444e  callvirt instance bool [mscorlib]System.String::Contains(string)
0x14453  brfalse.s loc_1445B
0x14455  ldstr    aInt// "int"
0x1445a  ret
0x1445b  ldloc.0
0x1445c  callvirt instance string [System]System.Uri::get_Host()
0x14461  ldstr    aDynamicsCom// "dynamics.com"
0x14466  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1446b  brfalse.s loc_14473
0x1446d  ldstr    aProd// "prod"
0x14472  ret
0x14473  ldloc.0
0x14474  callvirt instance string [System]System.Uri::get_Host()
0x14479  ldstr    aDynamicsTieCom// "dynamics-tie.com"
0x1447e  callvirt instance bool [mscorlib]System.String::Contains(string)
0x14483  brfalse.s loc_1448B
0x14485  ldstr    aPpe// "ppe"
0x1448a  ret
0x1448b  ldloc.0
0x1448c  callvirt instance string [System]System.Uri::get_Host()
0x14491  ldstr    aDynamicsServic// "dynamics-servicestie.com"
0x14496  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1449b  brfalse.s loc_144A3
0x1449d  ldstr    aPpe// "ppe"
0x144a2  ret
0x144a3  ldloc.0
0x144a4  callvirt instance string [System]System.Uri::get_Host()
0x144a9  ldstr    aDynamicsPpeCom// "dynamics-ppe.com"
0x144ae  callvirt instance bool [mscorlib]System.String::Contains(string)
0x144b3  brfalse.s loc_144BB
0x144b5  ldstr    aPpe// "ppe"
0x144ba  ret
0x144bb  ldloc.0
0x144bc  callvirt instance string [System]System.Uri::get_Host()
0x144c1  ldstr    aPowerappsCom// "powerapps.com"
0x144c6  callvirt instance bool [mscorlib]System.String::Contains(string)
0x144cb  brfalse.s loc_144D3
0x144cd  ldstr    aProd// "prod"
0x144d2  ret
0x144d3  ldloc.0
0x144d4  callvirt instance string [System]System.Uri::get_Host()
0x144d9  ldstr    aFlowMicrosoftC// "flow.microsoft.com"
0x144de  callvirt instance bool [mscorlib]System.String::Contains(string)
0x144e3  brfalse.s loc_144EB
0x144e5  ldstr    aProd// "prod"
0x144ea  ret
0x144eb  ldloc.0
0x144ec  callvirt instance string [System]System.Uri::get_Host()
0x144f1  ldstr    aPowerappsCloud// "powerapps.cloudapp.net"
0x144f6  callvirt instance bool [mscorlib]System.String::Contains(string)
0x144fb  pop
0x144fc  ldstr    aProd// "prod"
0x14501  ret
```
