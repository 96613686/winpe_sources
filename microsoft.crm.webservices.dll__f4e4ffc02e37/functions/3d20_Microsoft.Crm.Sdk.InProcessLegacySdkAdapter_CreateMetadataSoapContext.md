# Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::CreateMetadataSoapContext

- ea: `0x3d20`
- end: `0x3d5f`
- name: `Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::CreateMetadataSoapContext`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xfe40`

## string_xrefs

- `0x3d3e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3d49`: `http://localhost/MSCRMServices/2007/MetadataService.asmx`

## pseudocode

```c

```

## disassembly

```asm
0x3d20  ldarg.1
0x3d21  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3d26  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3d2b  stloc.0
0x3d2c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3d31  ldstr    a0Execute// "{0}/Execute"
0x3d36  ldc.i4.1
0x3d37  newarr   [mscorlib]System.Object
0x3d3c  dup
0x3d3d  ldc.i4.0
0x3d3e  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0x3d43  stelem.ref
0x3d44  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3d49  ldstr    aHttpLocalhostM_0// "http://localhost/MSCRMServices/2007/Met"...
0x3d4e  newobj   instance void [System]System.Uri::.ctor(string)
0x3d53  ldloc.0
0x3d54  ldsfld   string [mscorlib]System.String::Empty
0x3d59  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::.ctor(string, class [System]System.Uri, string, string)
0x3d5e  ret
```
