# Microsoft.Crm.Sdk.InProcessCrmService::CreateSoapContext

- ea: `0x33c0`
- end: `0x3423`
- name: `Microsoft.Crm.Sdk.InProcessCrmService::CreateSoapContext`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e20`

## callees

- `0x33c0`
- `0x3480`
- `0x3490`

## string_xrefs

- `0x33e0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x33e6`: `http://localhost/MSCRMServices/2007/CrmService.asmx`

## pseudocode

```c

```

## disassembly

```asm
0x33c0  ldarg.0
0x33c1  call     instance object Microsoft.Crm.Sdk.InProcessCrmService::get_RawRequest()
0x33c6  brtrue.s loc_33CF
0x33c8  ldarg.0
0x33c9  ldarg.1
0x33ca  call     instance void Microsoft.Crm.Sdk.InProcessCrmService::set_RawRequest(object value)
0x33cf  ldarg.0
0x33d0  call     instance object Microsoft.Crm.Sdk.InProcessCrmService::get_RawRequest()
0x33d5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x33da  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x33df  stloc.0
0x33e0  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0x33e5  stloc.1
0x33e6  ldstr    aHttpLocalhostM// "http://localhost/MSCRMServices/2007/Crm"...
0x33eb  stloc.2
0x33ec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x33f1  ldstr    a0Execute// "{0}/Execute"
0x33f6  ldc.i4.1
0x33f7  newarr   [mscorlib]System.Object
0x33fc  dup
0x33fd  ldc.i4.0
0x33fe  ldloc.1
0x33ff  stelem.ref
0x3400  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3405  ldloc.2
0x3406  newobj   instance void [System]System.Uri::.ctor(string)
0x340b  ldloc.0
0x340c  ldsfld   string [mscorlib]System.String::Empty
0x3411  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::.ctor(string, class [System]System.Uri, string, string)
0x3416  dup
0x3417  ldarg.0
0x3418  call     instance object Microsoft.Crm.Sdk.InProcessCrmService::get_RawRequest()
0x341d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::set_RawRequest(object)
0x3422  ret
```
