# Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::BuildBagsWithReservedNamesFromXml

- ea: `0xc230`
- end: `0xc37f`
- name: `Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::BuildBagsWithReservedNamesFromXml`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc1e0`

## callees

- `0xc230`
- `0xc380`
- `0xc3a0`

## string_xrefs

- `0xc240`: `config\5.0\Scripts\Reserved.sql`
- `0xc333`: `IsDeleted`
- `0xc340`: `IsDeleted`

## pseudocode

```c

```

## disassembly

```asm
0xc230  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::bagsReservedNamesFromXml
0xc235  brtrue   loc_C379
0xc23a  ldarg.0
0xc23b  ldfld    string Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::rootPathServerSetup
0xc240  ldstr    aConfig50Script// "config\\5.0\\Scripts\\Reserved.sql"
0xc245  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xc24a  stloc.0
0xc24b  ldloc.0
0xc24c  call     string [mscorlib]System.IO.File::ReadAllText(string)
0xc251  dup
0xc252  ldstr    aRoot// "<root>"
0xc257  ldc.i4.0
0xc258  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xc25d  stloc.1
0xc25e  ldc.i4.m1
0xc25f  ldloc.1
0xc260  bne.un.s loc_C273
0xc262  ldstr    aCannotFindTheT// "Cannot find the text <root> in the file"...
0xc267  ldloc.0
0xc268  call     string [mscorlib]System.String::Concat(string, string)
0xc26d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xc272  throw
0xc273  dup
0xc274  ldstr    aRoot_0// "</root>"
0xc279  ldc.i4.0
0xc27a  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xc27f  stloc.2
0xc280  ldc.i4.m1
0xc281  ldloc.2
0xc282  bne.un.s loc_C295
0xc284  ldstr    aCannotFindTheT_0// "Cannot find the text </root> in the fil"...
0xc289  ldloc.0
0xc28a  call     string [mscorlib]System.String::Concat(string, string)
0xc28f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xc294  throw
0xc295  ldloc.2
0xc296  ldstr    aRoot_0// "</root>"
0xc29b  call     instance int32 [mscorlib]System.String::get_Length()
0xc2a0  add
0xc2a1  stloc.2
0xc2a2  ldloc.2
0xc2a3  ldloc.1
0xc2a4  sub
0xc2a5  stloc.3
0xc2a6  ldloc.1
0xc2a7  ldloc.3
0xc2a8  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xc2ad  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::.ctor()
0xc2b2  stloc.s  4
0xc2b4  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0xc2b9  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0xc2be  stloc.s  5
0xc2c0  ldloc.s  5
0xc2c2  ldstr    aRoot_1// "root"
0xc2c7  ldloc.0
0xc2c8  call     void Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::ThrowIfCannotReadToDescendantInXml(class [System.Xml]System.Xml.XmlReader xmlReader, string elementName, string fullPath)
0xc2cd  ldloc.s  5
0xc2cf  ldstr    aReservednames// "ReservedNames"
0xc2d4  ldloc.0
0xc2d5  call     void Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::ThrowIfCannotReadToDescendantInXml(class [System.Xml]System.Xml.XmlReader xmlReader, string elementName, string fullPath)
0xc2da  ldc.i4.3
0xc2db  ldc.i4.0
0xc2dc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor(int32, bool)
0xc2e1  stloc.s  6
0xc2e3  ldloc.s  5
0xc2e5  ldstr    aReservedname// "ReservedName"
0xc2ea  ldloc.0
0xc2eb  call     void Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::ThrowIfCannotMoveToAttributeInXml(class [System.Xml]System.Xml.XmlReader xmlReader, string attributeName, string fullPath)
0xc2f0  ldloc.s  6
0xc2f2  ldstr    aReservedname// "ReservedName"
0xc2f7  ldloc.s  5
0xc2f9  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadContentAsString()
0xc2fe  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0xc303  ldloc.s  5
0xc305  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadContentAsString()
0xc30a  stloc.s  7
0xc30c  ldloc.s  5
0xc30e  ldstr    aReservedreason// "ReservedReason"
0xc313  ldloc.0
0xc314  call     void Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::ThrowIfCannotMoveToAttributeInXml(class [System.Xml]System.Xml.XmlReader xmlReader, string attributeName, string fullPath)
0xc319  ldloc.s  6
0xc31b  ldstr    aReservedreason// "ReservedReason"
0xc320  ldloc.s  5
0xc322  callvirt instance int32 [System.Xml]System.Xml.XmlReader::ReadContentAsInt()
0xc327  box      [mscorlib]System.Int32
0xc32c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0xc331  ldloc.s  5
0xc333  ldstr    aIsdeleted// "IsDeleted"
0xc338  ldloc.0
0xc339  call     void Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::ThrowIfCannotMoveToAttributeInXml(class [System.Xml]System.Xml.XmlReader xmlReader, string attributeName, string fullPath)
0xc33e  ldloc.s  6
0xc340  ldstr    aIsdeleted// "IsDeleted"
0xc345  ldloc.s  5
0xc347  callvirt instance int32 [System.Xml]System.Xml.XmlReader::ReadContentAsInt()
0xc34c  box      [mscorlib]System.Int32
0xc351  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0xc356  ldloc.s  4
0xc358  ldloc.s  7
0xc35a  ldloc.s  6
0xc35c  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>, !!T0)
0xc361  ldloc.s  5
0xc363  ldstr    aReservednames// "ReservedNames"
0xc368  callvirt instance bool [System.Xml]System.Xml.XmlReader::ReadToNextSibling(string)
0xc36d  brtrue   loc_C2DA
0xc372  ldloc.s  4
0xc374  stsfld   class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::bagsReservedNamesFromXml
0xc379  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Tools.Admin.OrgUniqueNameValidator::bagsReservedNamesFromXml
0xc37e  ret
```
