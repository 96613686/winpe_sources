# Microsoft.Crm.Metadata.RelationshipSerializationHelper::CascadeLinkTypeFromXmlString

- ea: `0x6f350`
- end: `0x6f3de`
- name: `Microsoft.Crm.Metadata.RelationshipSerializationHelper::CascadeLinkTypeFromXmlString`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3e310`

## callees

- `0x6f350`

## string_xrefs

- `0x6f36b`: `RemoveLink`
- `0x6f3bd`: `Cannot convert CascadeLinkType From XmlString, CascadeLinkType is not supported: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6f350  ldarg.0
0x6f351  ldstr    aNocascade// "NoCascade"
0x6f356  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6f35b  brtrue.s loc_6F3A0
0x6f35d  ldarg.0
0x6f35e  ldstr    aCascade// "Cascade"
0x6f363  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6f368  brtrue.s loc_6F3A4
0x6f36a  ldarg.0
0x6f36b  ldstr    aRemovelink// "RemoveLink"
0x6f370  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6f375  brtrue.s loc_6F3A8
0x6f377  ldarg.0
0x6f378  ldstr    aRestrict// "Restrict"
0x6f37d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6f382  brtrue.s loc_6F3AC
0x6f384  ldarg.0
0x6f385  ldstr    aActiveonly// "ActiveOnly"
0x6f38a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6f38f  brtrue.s loc_6F3B0
0x6f391  ldarg.0
0x6f392  ldstr    aUserowned// "UserOwned"
0x6f397  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6f39c  brtrue.s loc_6F3B4
0x6f39e  br.s     loc_6F3B8
0x6f3a0  ldc.i4.0
0x6f3a1  stloc.0
0x6f3a2  br.s     loc_6F3DC
0x6f3a4  ldc.i4.1
0x6f3a5  stloc.0
0x6f3a6  br.s     loc_6F3DC
0x6f3a8  ldc.i4.2
0x6f3a9  stloc.0
0x6f3aa  br.s     loc_6F3DC
0x6f3ac  ldc.i4.3
0x6f3ad  stloc.0
0x6f3ae  br.s     loc_6F3DC
0x6f3b0  ldc.i4.4
0x6f3b1  stloc.0
0x6f3b2  br.s     loc_6F3DC
0x6f3b4  ldc.i4.5
0x6f3b5  stloc.0
0x6f3b6  br.s     loc_6F3DC
0x6f3b8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6f3bd  ldstr    aCannotConvertC_3// "Cannot convert CascadeLinkType From Xml"...
0x6f3c2  ldc.i4.1
0x6f3c3  newarr   [mscorlib]System.Object
0x6f3c8  dup
0x6f3c9  ldc.i4.0
0x6f3ca  ldarg.0
0x6f3cb  stelem.ref
0x6f3cc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6f3d1  ldc.i4   0x80040203
0x6f3d6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x6f3db  throw
0x6f3dc  ldloc.0
0x6f3dd  ret
```
