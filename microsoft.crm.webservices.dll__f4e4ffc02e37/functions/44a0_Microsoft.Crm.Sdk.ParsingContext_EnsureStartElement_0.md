# Microsoft.Crm.Sdk.ParsingContext::EnsureStartElement_0

- ea: `0x44a0`
- end: `0x44e2`
- name: `Microsoft.Crm.Sdk.ParsingContext::EnsureStartElement_0`
- size: `66`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1530`
- `0x19c0`
- `0x2190`
- `0x2780`
- `0x4490`
- `0x61e0`

## callees

- `0x43d0`
- `0x44a0`
- `0x45f0`
- `0x4a80`

## string_xrefs

- `0x44b4`: `Invalid format of input XML for request {0}: required field '{1}' is missing.`

## pseudocode

```c

```

## disassembly

```asm
0x44a0  ldarg.0
0x44a1  ldfld    class [System.Xml]System.Xml.XmlReader Microsoft.Crm.Sdk.ParsingContext::_reader
0x44a6  ldarg.1
0x44a7  ldarg.2
0x44a8  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement(string, string)
0x44ad  brtrue.s loc_44E1
0x44af  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x44b4  ldstr    aInvalidFormatO// "Invalid format of input XML for request"...
0x44b9  ldc.i4.2
0x44ba  newarr   [mscorlib]System.Object
0x44bf  dup
0x44c0  ldc.i4.0
0x44c1  ldarg.0
0x44c2  call     instance class Microsoft.Crm.Sdk.RequestBase Microsoft.Crm.Sdk.ParsingContext::get_Request()
0x44c7  callvirt instance class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::get_RequestBuilder()
0x44cc  callvirt instance string Microsoft.Crm.Sdk.IRequestBuilder::get_RequestName()
0x44d1  stelem.ref
0x44d2  dup
0x44d3  ldc.i4.1
0x44d4  ldarg.1
0x44d5  stelem.ref
0x44d6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x44db  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x44e0  throw
0x44e1  ret
```
