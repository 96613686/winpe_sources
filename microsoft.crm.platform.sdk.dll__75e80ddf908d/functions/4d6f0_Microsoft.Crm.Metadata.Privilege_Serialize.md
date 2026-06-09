# Microsoft.Crm.Metadata.Privilege::Serialize

- ea: `0x4d6f0`
- end: `0x4d82f`
- name: `Microsoft.Crm.Metadata.Privilege::Serialize`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x4a9b0`

## callees

- `0x12d20`
- `0x4d440`
- `0x4d460`
- `0x4d470`
- `0x4d480`
- `0x4d490`
- `0x4d4a0`
- `0x4d4b0`
- `0x4d4c0`
- `0x4d4d0`
- `0x4d4e0`
- `0x4d6f0`

## string_xrefs

- `0x4d6f1`: `writer`
- `0x4d707`: `privilegeid`
- `0x4d73b`: `accessright`
- `0x4d759`: `privilegetype`
- `0x4d6fc`: `privilege`

## pseudocode

```c

```

## disassembly

```asm
0x4d6f0  ldarg.1
0x4d6f1  ldstr    aWriter// "writer"
0x4d6f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4d6fb  ldarg.1
0x4d6fc  ldstr    aPrivilege_0// "privilege"
0x4d701  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4d706  ldarg.1
0x4d707  ldstr    aPrivilegeid_1// "privilegeid"
0x4d70c  ldarg.0
0x4d70d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.Privilege::get_Id()
0x4d712  stloc.0
0x4d713  ldloca.s 0
0x4d715  ldstr    aD_0// "D"
0x4d71a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4d71f  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x4d724  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x4d729  ldarg.1
0x4d72a  ldstr    aName_0// "name"
0x4d72f  ldarg.0
0x4d730  call     instance string Microsoft.Crm.Metadata.Privilege::get_Name()
0x4d735  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x4d73a  ldarg.1
0x4d73b  ldstr    aAccessright_0// "accessright"
0x4d740  ldarg.0
0x4d741  call     instance int32 Microsoft.Crm.Metadata.Privilege::get_AccessRight()
0x4d746  stloc.1
0x4d747  ldloca.s 1
0x4d749  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4d74e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4d753  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x4d758  ldarg.1
0x4d759  ldstr    aPrivilegetype// "privilegetype"
0x4d75e  ldarg.0
0x4d75f  call     instance valuetype Microsoft.Crm.Metadata.PrivilegeType Microsoft.Crm.Metadata.Privilege::get_PrivilegeType()
0x4d764  stloc.2
0x4d765  ldloca.s 2
0x4d767  constrained. Microsoft.Crm.Metadata.PrivilegeType
0x4d76d  callvirt instance string [mscorlib]System.Object::ToString()
0x4d772  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x4d777  ldarg.0
0x4d778  call     instance bool Microsoft.Crm.Metadata.Privilege::get_CanBeBasic()
0x4d77d  brtrue.s loc_4D78F
0x4d77f  ldarg.1
0x4d780  ldstr    aCanbebasic_0// "canbebasic"
0x4d785  ldstr    a0_0// "0"
0x4d78a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x4d78f  ldarg.0
0x4d790  call     instance bool Microsoft.Crm.Metadata.Privilege::get_CanBeLocal()
0x4d795  brtrue.s loc_4D7A7
0x4d797  ldarg.1
0x4d798  ldstr    aCanbelocal_0// "canbelocal"
0x4d79d  ldstr    a0_0// "0"
0x4d7a2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x4d7a7  ldarg.0
0x4d7a8  call     instance bool Microsoft.Crm.Metadata.Privilege::get_CanBeDeep()
0x4d7ad  brtrue.s loc_4D7BF
0x4d7af  ldarg.1
0x4d7b0  ldstr    aCanbedeep_0// "canbedeep"
0x4d7b5  ldstr    a0_0// "0"
0x4d7ba  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x4d7bf  ldarg.0
0x4d7c0  call     instance bool Microsoft.Crm.Metadata.Privilege::get_CanBeGlobal()
0x4d7c5  brtrue.s loc_4D7D7
0x4d7c7  ldarg.1
0x4d7c8  ldstr    aCanbeglobal_0// "canbeglobal"
0x4d7cd  ldstr    a0_0// "0"
0x4d7d2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x4d7d7  ldarg.0
0x4d7d8  call     instance bool Microsoft.Crm.Metadata.Privilege::get_CanBeEntityReference()
0x4d7dd  brtrue.s loc_4D7EF
0x4d7df  ldarg.1
0x4d7e0  ldstr    aCanbeentityref_0// "canbeentityreference"
0x4d7e5  ldstr    a0_0// "0"
0x4d7ea  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x4d7ef  ldarg.0
0x4d7f0  call     instance bool Microsoft.Crm.Metadata.Privilege::get_CanBeParentEntityReference()
0x4d7f5  brtrue.s loc_4D807
0x4d7f7  ldarg.1
0x4d7f8  ldstr    aCanbeparentent_0// "canbeparententityreference"
0x4d7fd  ldstr    a0_0// "0"
0x4d802  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x4d807  ldarg.2
0x4d808  brfalse.s loc_4D828
0x4d80a  ldarg.1
0x4d80b  ldstr    aOtc// "otc"
0x4d810  ldarg.2
0x4d811  callvirt instance int32 Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x4d816  stloc.1
0x4d817  ldloca.s 1
0x4d819  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4d81e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x4d823  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x4d828  ldarg.1
0x4d829  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4d82e  ret
```
