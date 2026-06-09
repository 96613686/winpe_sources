# Microsoft.Crm.Authentication.CrmAuthorizationUtility::ValidateTokenOrganization

- ea: `0xe40`
- end: `0xe97`
- name: `Microsoft.Crm.Authentication.CrmAuthorizationUtility::ValidateTokenOrganization`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xea0`

## callees

- `0xe40`
- `0x7780`

## string_xrefs

- `0xe5d`: `CrmAuthorizationUtility.ValidateTokenOrganization: failed. Requested organization id is {0} but organization id presented in Session Security Token is {1}`

## pseudocode

```c

```

## disassembly

```asm
0xe40  ldarga.s 0
0xe42  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe47  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xe4c  brtrue.s loc_E95
0xe4e  ldarga.s 1
0xe50  ldarg.0
0xe51  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xe56  brtrue.s loc_E95
0xe58  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe5d  ldstr    aCrmauthorizati_1// "CrmAuthorizationUtility.ValidateTokenOr"...
0xe62  ldc.i4.2
0xe63  newarr   [mscorlib]System.Object
0xe68  dup
0xe69  ldc.i4.0
0xe6a  ldarg.0
0xe6b  box      [mscorlib]System.Guid
0xe70  stelem.ref
0xe71  dup
0xe72  ldc.i4.1
0xe73  ldarg.1
0xe74  box      [mscorlib]System.Guid
0xe79  stelem.ref
0xe7a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe7f  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xe84  ldc.i4   0x8004A102
0xe89  ldc.i4.0
0xe8a  newarr   [mscorlib]System.Object
0xe8f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xe94  throw
0xe95  ldc.i4.1
0xe96  ret
```
