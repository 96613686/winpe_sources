# Microsoft.Crm.CrmLicenseHelper::IsInvalidLicensePrivilege

- ea: `0x15f80`
- end: `0x16019`
- name: `Microsoft.Crm.CrmLicenseHelper::IsInvalidLicensePrivilege`
- size: `153`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xc5f0`
- `0x15f80`

## string_xrefs

- `0x15f8c`: `privilegeId`
- `0x15f97`: `privilegeObjectTypeCode`
- `0x15fa4`: `accessMode`

## pseudocode

```c

```

## disassembly

```asm
0x15f80  ldarg.0
0x15f81  ldstr    aLicenseid// "licenseId"
0x15f86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x15f8b  ldarg.1
0x15f8c  ldstr    aPrivilegeid// "privilegeId"
0x15f91  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x15f96  ldarg.2
0x15f97  ldstr    aPrivilegeobjec// "privilegeObjectTypeCode"
0x15f9c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNegative(int32, string)
0x15fa1  ldarg.3
0x15fa2  ldc.i4.0
0x15fa3  ldc.i4.5
0x15fa4  ldstr    aAccessmode// "accessMode"
0x15fa9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfOutOfRange(int32, int32, int32, string)
0x15fae  call     class Microsoft.Xrm.LicensesPrivileges Microsoft.Xrm.CrmLicenseData::get_LicensesPrivileges()
0x15fb3  ldarg.0
0x15fb4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.LicensePrivileges>::get_Item(void)
0x15fb9  ldarg.1
0x15fba  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.PrivilegeDefinition>::ContainsKey(var<u1>)
0x15fbf  brfalse.s loc_15FC3
0x15fc1  ldc.i4.0
0x15fc2  ret
0x15fc3  ldarg.s  4
0x15fc5  brfalse.s loc_15FCB
0x15fc7  ldarg.3
0x15fc8  ldc.i4.1
0x15fc9  beq.s    loc_15FCD
0x15fcb  ldc.i4.0
0x15fcc  ret
0x15fcd  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x15fd2  brfalse.s loc_16017
0x15fd4  ldloca.s 0
0x15fd6  ldstr    aF343f9c2381043// "F343F9C2-3810-4328-ADBC-7FE57A0A63C5"
0x15fdb  call     instance void [mscorlib]System.Guid::.ctor(string)
0x15fe0  ldloca.s 1
0x15fe2  ldstr    aBe7b84652a8946// "BE7B8465-2A89-467F-B11A-982BD429EFF4"
0x15fe7  call     instance void [mscorlib]System.Guid::.ctor(string)
0x15fec  ldloca.s 2
0x15fee  ldstr    a4d91c047E2f742// "4D91C047-E2F7-4247-84C3-45A567F40D0D"
0x15ff3  call     instance void [mscorlib]System.Guid::.ctor(string)
0x15ff8  ldarg.1
0x15ff9  ldloc.0
0x15ffa  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x15fff  brtrue.s loc_16013
0x16001  ldarg.1
0x16002  ldloc.1
0x16003  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x16008  brtrue.s loc_16013
0x1600a  ldarg.1
0x1600b  ldloc.2
0x1600c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x16011  brfalse.s loc_16015
0x16013  ldc.i4.0
0x16014  ret
0x16015  ldc.i4.1
0x16016  ret
0x16017  ldc.i4.1
0x16018  ret
```
