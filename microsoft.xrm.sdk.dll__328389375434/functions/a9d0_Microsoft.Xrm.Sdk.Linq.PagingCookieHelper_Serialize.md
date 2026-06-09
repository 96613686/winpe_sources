# Microsoft.Xrm.Sdk.Linq.PagingCookieHelper::Serialize

- ea: `0xa9d0`
- end: `0xabcd`
- name: `Microsoft.Xrm.Sdk.Linq.PagingCookieHelper::Serialize`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xa820`

## callees

- `0x7cb0`
- `0xa9d0`
- `0xabd0`

## string_xrefs

- `0xa9e4`: `Skip token has incorrect length`
- `0xaa24`: `Skip token has incorrect page value`

## pseudocode

```c

```

## disassembly

```asm
0xa9d0  ldarg.1
0xa9d1  ldc.i4.0
0xa9d2  stind.i4
0xa9d3  ldarg.0
0xa9d4  brfalse.s loc_A9DA
0xa9d6  ldarg.0
0xa9d7  ldlen
0xa9d8  brtrue.s loc_A9DC
0xa9da  ldnull
0xa9db  ret
0xa9dc  ldarg.0
0xa9dd  ldlen
0xa9de  conv.i4
0xa9df  ldc.i4.3
0xa9e0  rem
0xa9e1  ldc.i4.1
0xa9e2  beq.s    loc_A9EF
0xa9e4  ldstr    aSkipTokenHasIn// "Skip token has incorrect length"
0xa9e9  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xa9ee  throw
0xa9ef  ldarg.0
0xa9f0  ldc.i4.0
0xa9f1  ldelem.ref
0xa9f2  brfalse.s loc_AA24
0xa9f4  ldarg.0
0xa9f5  ldc.i4.0
0xa9f6  ldelem.ref
0xa9f7  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xa9fc  ldtoken  [mscorlib]System.Int32
0xaa01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xaa06  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xaa0b  brfalse.s loc_AA24
0xaa0d  ldarg.0
0xaa0e  ldc.i4.0
0xaa0f  ldelem.ref
0xaa10  unbox.any [mscorlib]System.Int32
0xaa15  ldc.i4.0
0xaa16  blt.s    loc_AA24
0xaa18  ldarg.1
0xaa19  ldarg.0
0xaa1a  ldc.i4.0
0xaa1b  ldelem.ref
0xaa1c  unbox.any [mscorlib]System.Int32
0xaa21  stind.i4
0xaa22  br.s     loc_AA2F
0xaa24  ldstr    aSkipTokenHasIn_0// "Skip token has incorrect page value"
0xaa29  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xaa2e  throw
0xaa2f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaa34  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0xaa39  stloc.0
0xaa3a  ldloc.0
0xaa3b  call     class [System.Xml]System.Xml.XmlWriter Microsoft.Xrm.Sdk.Linq.PagingCookieHelper::CreateXmlWriter(class [mscorlib]System.IO.TextWriter textWriter)
0xaa40  stloc.1
0xaa41  ldloc.1
0xaa42  ldstr    aCookie// "cookie"
0xaa47  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xaa4c  ldloc.1
0xaa4d  ldstr    aPage// "page"
0xaa52  ldarg.1
0xaa53  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xaa58  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xaa5d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xaa62  ldc.i4.1
0xaa63  stloc.2
0xaa64  ldarg.0
0xaa65  ldc.i4.1
0xaa66  ldelem.ref
0xaa67  brfalse  loc_AAFC
0xaa6c  ldarg.0
0xaa6d  ldc.i4.1
0xaa6e  ldelem.ref
0xaa6f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xaa74  ldtoken  [mscorlib]System.Guid
0xaa79  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xaa7e  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xaa83  brfalse.s loc_AAFC
0xaa85  ldarg.0
0xaa86  ldc.i4.2
0xaa87  ldelem.ref
0xaa88  brfalse.s loc_AAFC
0xaa8a  ldarg.0
0xaa8b  ldc.i4.2
0xaa8c  ldelem.ref
0xaa8d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xaa92  ldtoken  [mscorlib]System.String
0xaa97  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xaa9c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xaaa1  brfalse.s loc_AAFC
0xaaa3  ldarg.0
0xaaa4  ldc.i4.3
0xaaa5  ldelem.ref
0xaaa6  brfalse.s loc_AAFC
0xaaa8  ldarg.0
0xaaa9  ldc.i4.3
0xaaaa  ldelem.ref
0xaaab  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xaab0  ldtoken  [mscorlib]System.Int32
0xaab5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xaaba  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xaabf  brfalse.s loc_AAFC
0xaac1  ldc.i4.4
0xaac2  stloc.2
0xaac3  ldloc.1
0xaac4  ldstr    aParententityid// "parentEntityId"
0xaac9  ldarg.0
0xaaca  ldc.i4.1
0xaacb  ldelem.ref
0xaacc  callvirt instance string [mscorlib]System.Object::ToString()
0xaad1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xaad6  ldloc.1
0xaad7  ldstr    aParentattribut// "parentAttributeName"
0xaadc  ldarg.0
0xaadd  ldc.i4.2
0xaade  ldelem.ref
0xaadf  castclass [mscorlib]System.String
0xaae4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xaae9  ldloc.1
0xaaea  ldstr    aParententityob// "parentEntityObjectTypeCode"
0xaaef  ldarg.0
0xaaf0  ldc.i4.3
0xaaf1  ldelem.ref
0xaaf2  callvirt instance string [mscorlib]System.Object::ToString()
0xaaf7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xaafc  ldloc.2
0xaafd  stloc.3
0xaafe  br       loc_AB9B
0xab03  ldarg.0
0xab04  ldloc.3
0xab05  ldelem.ref
0xab06  castclass [mscorlib]System.String
0xab0b  stloc.s  4
0xab0d  ldloc.s  4
0xab0f  ldstr    aAttributename// "attributeName"
0xab14  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNullOrEmpty(string parameter, string name)
0xab19  ldsfld   string [mscorlib]System.String::Empty
0xab1e  stloc.s  5
0xab20  ldsfld   string [mscorlib]System.String::Empty
0xab25  stloc.s  6
0xab27  ldarg.0
0xab28  ldloc.3
0xab29  ldc.i4.1
0xab2a  add
0xab2b  ldelem.ref
0xab2c  castclass [mscorlib]System.String
0xab31  stloc.s  7
0xab33  ldarg.0
0xab34  ldloc.3
0xab35  ldc.i4.2
0xab36  add
0xab37  ldelem.ref
0xab38  castclass [mscorlib]System.String
0xab3d  stloc.s  8
0xab3f  ldloc.1
0xab40  ldloc.s  4
0xab42  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xab47  ldloc.s  7
0xab49  brfalse.s loc_AB54
0xab4b  ldstr    aLast// "last"
0xab50  stloc.s  6
0xab52  br.s     loc_AB62
0xab54  ldstr    aLastnull// "lastnull"
0xab59  stloc.s  6
0xab5b  ldstr    a1// "1"
0xab60  stloc.s  7
0xab62  ldloc.s  8
0xab64  brfalse.s loc_AB6F
0xab66  ldstr    aFirst// "first"
0xab6b  stloc.s  5
0xab6d  br.s     loc_AB7D
0xab6f  ldstr    aFirstnull// "firstnull"
0xab74  stloc.s  5
0xab76  ldstr    a1// "1"
0xab7b  stloc.s  8
0xab7d  ldloc.1
0xab7e  ldloc.s  6
0xab80  ldloc.s  7
0xab82  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xab87  ldloc.1
0xab88  ldloc.s  5
0xab8a  ldloc.s  8
0xab8c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xab91  ldloc.1
0xab92  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xab97  ldloc.3
0xab98  ldc.i4.3
0xab99  add
0xab9a  stloc.3
0xab9b  ldloc.3
0xab9c  ldarg.0
0xab9d  ldlen
0xab9e  conv.i4
0xab9f  blt      loc_AB03
0xaba4  ldloc.1
0xaba5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xabaa  leave.s  loc_ABB6
0xabac  ldloc.1
0xabad  brfalse.s loc_ABB5
0xabaf  ldloc.1
0xabb0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xabb5  endfinally
0xabb6  ldloc.0
0xabb7  callvirt instance string [mscorlib]System.Object::ToString()
0xabbc  stloc.s  9
0xabbe  leave.s  loc_ABCA
0xabc0  ldloc.0
0xabc1  brfalse.s loc_ABC9
0xabc3  ldloc.0
0xabc4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xabc9  endfinally
0xabca  ldloc.s  9
0xabcc  ret
```
