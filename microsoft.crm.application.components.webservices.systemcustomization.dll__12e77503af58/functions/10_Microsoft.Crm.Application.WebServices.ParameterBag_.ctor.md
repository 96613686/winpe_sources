# Microsoft.Crm.Application.WebServices.ParameterBag::.ctor

- ea: `0x10`
- end: `0x66`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::.ctor`
- size: `86`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a0`
- `0x1c0`
- `0x5ea0`
- `0x5ed0`
- `0x6240`
- `0x6380`
- `0xada0`
- `0xadc0`
- `0xaf20`
- `0xafd0`
- `0xb020`
- `0xb050`
- `0xb080`
- `0xb0f0`
- `0xb130`
- `0xb180`
- `0xb1b0`
- `0xb930`
- `0xbac0`

## callees

- `0x10`

## pseudocode

```c

```

## disassembly

```asm
0x10  ldarg.0
0x11  call     instance void [mscorlib]System.Object::.ctor()
0x16  ldarg.1
0x17  ldstr    aParameterbag// "parameterBag"
0x1c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x21  ldarg.2
0x22  ldstr    aName// "name"
0x27  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2c  ldarg.1
0x2d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x32  ldarg.2
0x33  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x38  brfalse.s loc_59
0x3a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f  ldstr    aTheRootNodeOfT// "The root node of the parameter bag must"...
0x44  ldc.i4.1
0x45  newarr   [mscorlib]System.Object
0x4a  dup
0x4b  ldc.i4.0
0x4c  ldarg.2
0x4d  stelem.ref
0x4e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x53  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x58  throw
0x59  ldarg.0
0x5a  ldarg.1
0x5b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::Clone()
0x60  stfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.ParameterBag::_parameterBag
0x65  ret
```
