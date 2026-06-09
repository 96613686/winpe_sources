# Microsoft.Crm.Entities.DynamicProperty::ToString

- ea: `0x1d70`
- end: `0x1e91`
- name: `Microsoft.Crm.Entities.DynamicProperty::ToString`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1d70`

## pseudocode

```c

```

## disassembly

```asm
0x1d70  ldarg.0
0x1d71  ldfld    string Microsoft.Crm.Entities.DynamicProperty::strValue
0x1d76  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d7b  brfalse  loc_1E8A
0x1d80  ldsfld   string [mscorlib]System.String::Empty
0x1d85  stloc.0
0x1d86  ldarg.0
0x1d87  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x1d8c  callvirt instance string [mscorlib]System.Object::ToString()
0x1d91  stloc.1
0x1d92  ldarg.0
0x1d93  ldstr    aName// "name"
0x1d98  call     instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1d9d  brtrue.s loc_1DB1
0x1d9f  ldarg.0
0x1da0  ldstr    aName// "name"
0x1da5  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1daa  castclass [mscorlib]System.String
0x1daf  br.s     loc_1DB6
0x1db1  ldsfld   string [mscorlib]System.String::Empty
0x1db6  stloc.2
0x1db7  ldarg.0
0x1db8  ldstr    aBasedynamicpro// "basedynamicpropertyid"
0x1dbd  call     instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1dc2  brtrue.s loc_1DCB
0x1dc4  ldstr    aOverriden// "overriden"
0x1dc9  br.s     loc_1DD0
0x1dcb  ldstr    aNone// "none"
0x1dd0  stloc.3
0x1dd1  ldarg.0
0x1dd2  ldstr    aDatatype// "datatype"
0x1dd7  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1ddc  unbox.any Microsoft.Crm.Entities.DynamicPropertyDataType
0x1de1  stloc.s  4
0x1de3  ldnull
0x1de4  stloc.s  5
0x1de6  ldloc.s  4
0x1de8  switch   loc_1E3F, loc_1E12, loc_1E21, loc_1E30, loc_1E03
0x1e01  br.s     loc_1E4C
0x1e03  ldarg.0
0x1e04  ldstr    aDefaultvaluein// "defaultvalueinteger"
0x1e09  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1e0e  stloc.s  5
0x1e10  br.s     loc_1E4C
0x1e12  ldarg.0
0x1e13  ldstr    aDefaultvaluede// "defaultvaluedecimal"
0x1e18  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1e1d  stloc.s  5
0x1e1f  br.s     loc_1E4C
0x1e21  ldarg.0
0x1e22  ldstr    aDefaultvaluedo// "defaultvaluedouble"
0x1e27  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1e2c  stloc.s  5
0x1e2e  br.s     loc_1E4C
0x1e30  ldarg.0
0x1e31  ldstr    aDefaultvaluest// "defaultvaluestring"
0x1e36  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1e3b  stloc.s  5
0x1e3d  br.s     loc_1E4C
0x1e3f  ldarg.0
0x1e40  ldstr    aDefaultvalueop// "defaultvalueoptionset"
0x1e45  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x1e4a  stloc.s  5
0x1e4c  ldloc.s  5
0x1e4e  brtrue.s loc_1E57
0x1e50  ldsfld   string [mscorlib]System.String::Empty
0x1e55  br.s     loc_1E5E
0x1e57  ldloc.s  5
0x1e59  callvirt instance string [mscorlib]System.Object::ToString()
0x1e5e  stloc.0
0x1e5f  ldarg.0
0x1e60  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e65  ldstr    aName0Dynamicpr// "name = {0}, dynamicPropertyId = {1}, de"...
0x1e6a  ldc.i4.4
0x1e6b  newarr   [mscorlib]System.Object
0x1e70  dup
0x1e71  ldc.i4.0
0x1e72  ldloc.2
0x1e73  stelem.ref
0x1e74  dup
0x1e75  ldc.i4.1
0x1e76  ldloc.1
0x1e77  stelem.ref
0x1e78  dup
0x1e79  ldc.i4.2
0x1e7a  ldloc.0
0x1e7b  stelem.ref
0x1e7c  dup
0x1e7d  ldc.i4.3
0x1e7e  ldloc.3
0x1e7f  stelem.ref
0x1e80  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e85  stfld    string Microsoft.Crm.Entities.DynamicProperty::strValue
0x1e8a  ldarg.0
0x1e8b  ldfld    string Microsoft.Crm.Entities.DynamicProperty::strValue
0x1e90  ret
```
