# Microsoft.Crm.Authentication.CrmPrincipal::AddPrincipalToConfigDB_2

- ea: `0x5660`
- end: `0x568a`
- name: `Microsoft.Crm.Authentication.CrmPrincipal::AddPrincipalToConfigDB_2`
- size: `42`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5610`
- `0x5630`
- `0x5640`

## callees

- `0x5660`

## pseudocode

```c

```

## disassembly

```asm
0x5660  ldarg.2
0x5661  ldstr    aAuthinfo// "authInfo"
0x5666  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x566b  ldarg.3
0x566c  brfalse.s loc_567A
0x566e  ldarg.s  4
0x5670  ldstr    aOriginalauthin// "originalAuthInfo"
0x5675  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x567a  ldarg.0
0x567b  ldarg.1
0x567c  ldarg.2
0x567d  ldarg.3
0x567e  ldarg.s  4
0x5680  ldarg.s  5
0x5682  ldarg.s  6
0x5684  call     void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.UserService::AddPrincipalToConfigDB(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, bool, string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext, valuetype [mscorlib]System.Guid)
0x5689  ret
```
