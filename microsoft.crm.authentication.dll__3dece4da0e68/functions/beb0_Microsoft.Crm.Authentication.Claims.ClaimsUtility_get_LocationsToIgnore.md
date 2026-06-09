# Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_LocationsToIgnore

- ea: `0xbeb0`
- end: `0xbf54`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_LocationsToIgnore`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xc3e0`

## callees

- `0xbe90`
- `0xbeb0`
- `0xbf90`

## string_xrefs

- `0xbf1e`: `/AppWebServices/KeyService.asmx`
- `0xbf28`: `/Handlers/ProcessAccessUrlHandler.ashx`

## pseudocode

```c

```

## disassembly

```asm
0xbeb0  ldsfld   bool Microsoft.Crm.Authentication.Claims.ClaimsUtility::locationsToIgnoreLoaded
0xbeb5  brtrue   loc_BF4E
0xbeba  ldsfld   object Microsoft.Crm.Authentication.Claims.ClaimsUtility::_lockObject
0xbebf  stloc.0
0xbec0  ldc.i4.0
0xbec1  stloc.1
0xbec2  ldloc.0
0xbec3  ldloca.s 1
0xbec5  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xbeca  ldsfld   bool Microsoft.Crm.Authentication.Claims.ClaimsUtility::locationsToIgnoreLoaded
0xbecf  brtrue.s loc_BF42
0xbed1  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_FederationProvider()
0xbed6  ldstr    aLocationstoign// "LocationsToIgnore"
0xbedb  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::GetFederationProviderProperty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, string)
0xbee0  stloc.2
0xbee1  ldloc.2
0xbee2  brfalse.s loc_BF3C
0xbee4  ldloc.2
0xbee5  isinst   [mscorlib]System.String
0xbeea  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0xbeef  dup
0xbef0  ldstr    aPortalSignupSi// "/Portal/signup/signup.aspx"
0xbef5  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xbefa  pop
0xbefb  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Authentication.Claims.ClaimsUtility::LoadValues(string locationXml, class [System]System.Collections.Specialized.StringCollection locationsToRemove)
0xbf00  stloc.3
0xbf01  ldloc.3
0xbf02  brfalse.s loc_BF14
0xbf04  ldsfld   class [System]System.Collections.Specialized.StringCollection Microsoft.Crm.Authentication.Claims.ClaimsUtility::locationsToIgnore
0xbf09  ldloc.3
0xbf0a  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0xbf0f  callvirt instance void [System]System.Collections.Specialized.StringCollection::AddRange(string[])
0xbf14  ldstr    aHandlersWopise// "/Handlers/WopiServerHandler.ashx"
0xbf19  call     void Microsoft.Crm.Authentication.Claims.ClaimsUtility::AddLocationToIgnore(string path)
0xbf1e  ldstr    aAppwebservices// "/AppWebServices/KeyService.asmx"
0xbf23  call     void Microsoft.Crm.Authentication.Claims.ClaimsUtility::AddLocationToIgnore(string path)
0xbf28  ldstr    aHandlersProces// "/Handlers/ProcessAccessUrlHandler.ashx"
0xbf2d  call     void Microsoft.Crm.Authentication.Claims.ClaimsUtility::AddLocationToIgnore(string path)
0xbf32  ldstr    aCrmmailappRefr// "/crmmailapp/refresh_auth.ashx"
0xbf37  call     void Microsoft.Crm.Authentication.Claims.ClaimsUtility::AddLocationToIgnore(string path)
0xbf3c  ldc.i4.1
0xbf3d  stsfld   bool Microsoft.Crm.Authentication.Claims.ClaimsUtility::locationsToIgnoreLoaded
0xbf42  leave.s  loc_BF4E
0xbf44  ldloc.1
0xbf45  brfalse.s loc_BF4D
0xbf47  ldloc.0
0xbf48  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xbf4d  endfinally
0xbf4e  ldsfld   class [System]System.Collections.Specialized.StringCollection Microsoft.Crm.Authentication.Claims.ClaimsUtility::locationsToIgnore
0xbf53  ret
```
