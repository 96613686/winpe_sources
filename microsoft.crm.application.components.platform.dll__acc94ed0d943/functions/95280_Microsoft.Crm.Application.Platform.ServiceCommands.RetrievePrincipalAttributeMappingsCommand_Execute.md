# Microsoft.Crm.Application.Platform.ServiceCommands.RetrievePrincipalAttributeMappingsCommand::Execute

- ea: `0x95280`
- end: `0x952d2`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.RetrievePrincipalAttributeMappingsCommand::Execute`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14b20`
- `0x5aa80`

## callees

- `0x90e70`
- `0x95280`

## string_xrefs

- `0x95285`: `RetrievePrincipalAttributeMappingsCommand_BEGIN_{0}.profile`
- `0x952b6`: `RetrievePrincipalAttributeMappingsCommand_END_{0}.prorfile`

## pseudocode

```c

```

## disassembly

```asm
0x95280  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x95285  ldstr    aRetrieveprinci_1// "RetrievePrincipalAttributeMappingsComma"...
0x9528a  ldc.i4.1
0x9528b  newarr   [mscorlib]System.Object
0x95290  dup
0x95291  ldc.i4.0
0x95292  ldarg.0
0x95293  stelem.ref
0x95294  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x95299  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x9529e  ldarg.0
0x9529f  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0x952a4  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RetrievePrincipalSyncAttributeMappingsResponse
0x952a9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeMappingCollection [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.RetrievePrincipalSyncAttributeMappingsResponse::get_AttributeMappings()
0x952ae  stloc.0
0x952af  leave.s  loc_952D0
0x952b1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x952b6  ldstr    aRetrieveprinci_2// "RetrievePrincipalAttributeMappingsComma"...
0x952bb  ldc.i4.1
0x952bc  newarr   [mscorlib]System.Object
0x952c1  dup
0x952c2  ldc.i4.0
0x952c3  ldarg.0
0x952c4  stelem.ref
0x952c5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x952ca  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x952cf  endfinally
0x952d0  ldloc.0
0x952d1  ret
```
