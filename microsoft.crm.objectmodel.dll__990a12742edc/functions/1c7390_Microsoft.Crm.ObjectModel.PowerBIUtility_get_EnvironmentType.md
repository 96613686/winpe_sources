# Microsoft.Crm.ObjectModel.PowerBIUtility::get_EnvironmentType

- ea: `0x1c7390`
- end: `0x1c7461`
- name: `Microsoft.Crm.ObjectModel.PowerBIUtility::get_EnvironmentType`
- size: `209`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x58110`
- `0x58190`
- `0x1befa0`

## callees

- `0x1c7390`
- `0x1c74c0`
- `0x1c74f0`

## string_xrefs

- `0x1c73b9`: `extest.microsoft.com`
- `0x1c73d1`: `crmlivetie.com`
- `0x1c73e9`: `crmlivetoday.com`
- `0x1c7401`: `1boxtest.com`
- `0x1c7419`: `dynamics-int.com`
- `0x1c7431`: `crm9.dynamics.com`
- `0x1c7449`: `dynamics.com`

## pseudocode

```c

```

## disassembly

```asm
0x1c7390  call     class Microsoft.Crm.ObjectModel.EnvironmentUtility Microsoft.Crm.ObjectModel.EnvironmentUtility::get_Instance()
0x1c7395  ldloca.s 1
0x1c7397  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1c739d  ldloc.1
0x1c739e  callvirt instance string Microsoft.Crm.ObjectModel.EnvironmentUtility::GetWebServer([opt] valuetype [mscorlib]System.Nullable`1<int32> authType)
0x1c73a3  ldc.i4.1
0x1c73a4  ldloca.s 0
0x1c73a6  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x1c73ab  brtrue.s loc_1C73B3
0x1c73ad  ldstr    aPpe// "ppe"
0x1c73b2  ret
0x1c73b3  ldloc.0
0x1c73b4  callvirt instance string [System]System.Uri::get_Host()
0x1c73b9  ldstr    aExtestMicrosof// "extest.microsoft.com"
0x1c73be  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1c73c3  brfalse.s loc_1C73CB
0x1c73c5  ldstr    aPpe// "ppe"
0x1c73ca  ret
0x1c73cb  ldloc.0
0x1c73cc  callvirt instance string [System]System.Uri::get_Host()
0x1c73d1  ldstr    aCrmlivetieCom// "crmlivetie.com"
0x1c73d6  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1c73db  brfalse.s loc_1C73E3
0x1c73dd  ldstr    aPpe// "ppe"
0x1c73e2  ret
0x1c73e3  ldloc.0
0x1c73e4  callvirt instance string [System]System.Uri::get_Host()
0x1c73e9  ldstr    aCrmlivetodayCo// "crmlivetoday.com"
0x1c73ee  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1c73f3  brfalse.s loc_1C73FB
0x1c73f5  ldstr    aPpe// "ppe"
0x1c73fa  ret
0x1c73fb  ldloc.0
0x1c73fc  callvirt instance string [System]System.Uri::get_Host()
0x1c7401  ldstr    a1boxtestCom// "1boxtest.com"
0x1c7406  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1c740b  brfalse.s loc_1C7413
0x1c740d  ldstr    aPpe// "ppe"
0x1c7412  ret
0x1c7413  ldloc.0
0x1c7414  callvirt instance string [System]System.Uri::get_Host()
0x1c7419  ldstr    aDynamicsIntCom// "dynamics-int.com"
0x1c741e  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1c7423  brfalse.s loc_1C742B
0x1c7425  ldstr    aInt// "int"
0x1c742a  ret
0x1c742b  ldloc.0
0x1c742c  callvirt instance string [System]System.Uri::get_Host()
0x1c7431  ldstr    aCrm9DynamicsCo// "crm9.dynamics.com"
0x1c7436  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1c743b  brfalse.s loc_1C7443
0x1c743d  ldstr    aGcc// "gcc"
0x1c7442  ret
0x1c7443  ldloc.0
0x1c7444  callvirt instance string [System]System.Uri::get_Host()
0x1c7449  ldstr    aDynamicsCom// "dynamics.com"
0x1c744e  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1c7453  brfalse.s loc_1C745B
0x1c7455  ldstr    aProd// "prod"
0x1c745a  ret
0x1c745b  ldstr    aPpe// "ppe"
0x1c7460  ret
```
