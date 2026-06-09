# Microsoft.Crm.Application.Platform.ServiceCommands.RetrievePrincipalAttributePrivilegesCommand::Execute

- ea: `0x94960`
- end: `0x949b2`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.RetrievePrincipalAttributePrivilegesCommand::Execute`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14df0`

## callees

- `0x90e70`
- `0x94960`

## string_xrefs

- `0x94965`: `RetrievePrincipalAttributePrivilegesCommand_BEGIN_{0}.principal`
- `0x94996`: `RetrievePrincipalAttributePrivilegesCommand_END_{0}.principal`

## pseudocode

```c

```

## disassembly

```asm
0x94960  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x94965  ldstr    aRetrieveprinci// "RetrievePrincipalAttributePrivilegesCom"...
0x9496a  ldc.i4.1
0x9496b  newarr   [mscorlib]System.Object
0x94970  dup
0x94971  ldc.i4.0
0x94972  ldarg.0
0x94973  stelem.ref
0x94974  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x94979  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x9497e  ldarg.0
0x9497f  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0x94984  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RetrievePrincipalAttributePrivilegesResponse
0x94989  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributePrivilegeCollection [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RetrievePrincipalAttributePrivilegesResponse::get_AttributePrivileges()
0x9498e  stloc.0
0x9498f  leave.s  loc_949B0
0x94991  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x94996  ldstr    aRetrieveprinci_0// "RetrievePrincipalAttributePrivilegesCom"...
0x9499b  ldc.i4.1
0x9499c  newarr   [mscorlib]System.Object
0x949a1  dup
0x949a2  ldc.i4.0
0x949a3  ldarg.0
0x949a4  stelem.ref
0x949a5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x949aa  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x949af  endfinally
0x949b0  ldloc.0
0x949b1  ret
```
