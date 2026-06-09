# Microsoft.Crm.ServiceBus.RouterClient::RetrieveRouterServicePrincipalName

- ea: `0x390`
- end: `0x3eb`
- name: `Microsoft.Crm.ServiceBus.RouterClient::RetrieveRouterServicePrincipalName`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x230`

## callees

- `0x390`

## string_xrefs

- `0x3ba`: `ServiceBusRouterServiceSPN`
- `0x3d1`: `MSCRMRouterService`

## pseudocode

```c

```

## disassembly

```asm
0x390  ldarg.1
0x391  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x396  brtrue.s loc_3B4
0x398  ldarg.1
0x399  ldstr    aLocalhost// "localhost"
0x39e  ldc.i4.5
0x39f  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3a4  brtrue.s loc_3B4
0x3a6  ldarg.1
0x3a7  call     string [mscorlib]System.Environment::get_MachineName()
0x3ac  ldc.i4.5
0x3ad  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3b2  brfalse.s loc_3BA
0x3b4  ldsfld   string [mscorlib]System.String::Empty
0x3b9  ret
0x3ba  ldstr    aServicebusrout// "ServiceBusRouterServiceSPN"
0x3bf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c4  ldstr    a01// "{0}/{1}"
0x3c9  ldc.i4.2
0x3ca  newarr   [mscorlib]System.Object
0x3cf  dup
0x3d0  ldc.i4.0
0x3d1  ldstr    aMscrmrouterser// "MSCRMRouterService"
0x3d6  stelem.ref
0x3d7  dup
0x3d8  ldc.i4.1
0x3d9  ldarg.1
0x3da  stelem.ref
0x3db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3e0  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x3e5  castclass [mscorlib]System.String
0x3ea  ret
```
