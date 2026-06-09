# Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToSpreadsheetML::InitializeSpreadsheetMLGenerator

- ea: `0xd4ff0`
- end: `0xd5330`
- name: `Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToSpreadsheetML::InitializeSpreadsheetMLGenerator`
- size: `832`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xd4f60`

## callees

- `0xcd200`
- `0xcd7f0`
- `0xd4ff0`
- `0xd5bd0`
- `0xd5c80`

## string_xrefs

- `0xd51c4`: `createdon`
- `0xd51e9`: `createdon`
- `0xd51d2`: `overriddencreatedon`
- `0xd51e0`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0xd4ff0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd4ff5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd4ffa  ldarg.0
0xd4ffb  ldfld    int32 Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToSpreadsheetML::entityTypeCode
0xd5000  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xd5005  stloc.0
0xd5006  ldloc.0
0xd5007  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0xd500c  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xd5011  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xd5016  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd501b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd5020  stloc.1
0xd5021  ldloc.1
0xd5022  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd5027  brfalse.s loc_D5030
0xd5029  ldloc.0
0xd502a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xd502f  stloc.1
0xd5030  ldc.i4.1
0xd5031  ldloc.1
0xd5032  ldloc.0
0xd5033  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xd5038  ldc.i4.1
0xd5039  ldc.i4.1
0xd503a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties::.ctor(valuetype [Microsoft.Crm]Microsoft.Crm.SpreadsheetExportMode, string, string, bool, bool)
0xd503f  stloc.2
0xd5040  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties>::.ctor()
0xd5045  stloc.3
0xd5046  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd504b  ldstr    aCsvExportColum// "CSV_Export_ColumnHeader"
0xd5050  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd5055  stloc.s  4
0xd5057  ldloc.0
0xd5058  ldc.i4.1
0xd5059  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd505e  call     class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::GetImportableAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd5063  stloc.s  5
0xd5065  ldc.i4.0
0xd5066  stloc.s  6
0xd5068  br       loc_D530B
0xd506d  ldarg.0
0xd506e  call     instance class Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor Microsoft.Crm.Application.Controls.Grid.UI.LayoutProvider::get_LayoutDescriptor()
0xd5073  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnCollection Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor::get_Columns()
0xd5078  ldloc.s  6
0xd507a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnCollection::get_Item(int32)
0xd507f  stloc.s  7
0xd5081  ldc.i4.0
0xd5082  stloc.s  8
0xd5084  ldc.i4.0
0xd5085  stloc.s  9
0xd5087  ldc.i4.0
0xd5088  stloc.s  0xA
0xd508a  ldc.i4.0
0xd508b  stloc.s  0xB
0xd508d  ldc.i4.0
0xd508e  stloc.s  0xC
0xd5090  ldsfld   string [mscorlib]System.String::Empty
0xd5095  stloc.s  0xD
0xd5097  ldsfld   string [mscorlib]System.String::Empty
0xd509c  stloc.s  0xF
0xd509e  ldloc.s  7
0xd50a0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_UIInfo()
0xd50a5  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo::get_IsHidden()
0xd50aa  stloc.s  8
0xd50ac  ldloc.s  7
0xd50ae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_Name()
0xd50b3  stloc.s  0xE
0xd50b5  ldarg.0
0xd50b6  ldloc.s  6
0xd50b8  ldloc.s  8
0xd50ba  ldloc.s  0xE
0xd50bc  call     instance bool Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToSpreadsheetML::IgnoreColumn(int32 columnIndex, bool isHidden, string attributeLogicalName)
0xd50c1  brtrue   loc_D5305
0xd50c6  ldloc.0
0xd50c7  ldloc.s  0xE
0xd50c9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0xd50ce  stloc.s  0x10
0xd50d0  ldloc.s  6
0xd50d2  ldc.i4.1
0xd50d3  beq.s    loc_D50DA
0xd50d5  ldloc.s  6
0xd50d7  ldc.i4.2
0xd50d8  bne.un.s loc_D50FA
0xd50da  ldc.i4.0
0xd50db  stloc.s  0xC
0xd50dd  ldc.i4.1
0xd50de  stloc.s  8
0xd50e0  ldsfld   string [mscorlib]System.String::Empty
0xd50e5  stloc.s  0xF
0xd50e7  ldloc.s  7
0xd50e9  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_UIInfo()
0xd50ee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo::get_Label()
0xd50f3  stloc.s  0xD
0xd50f5  br       loc_D5244
0xd50fa  ldloc.s  6
0xd50fc  ldc.i4.3
0xd50fd  bne.un.s loc_D514C
0xd50ff  ldc.i4.0
0xd5100  stloc.s  0xC
0xd5102  ldc.i4.0
0xd5103  stloc.s  8
0xd5105  ldloc.0
0xd5106  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0xd510b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Description()
0xd5110  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xd5115  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xd511a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd511f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd5124  stloc.s  0xF
0xd5126  ldloc.0
0xd5127  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0xd512c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0xd5131  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xd5136  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xd513b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd5140  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd5145  stloc.s  0xD
0xd5147  br       loc_D5244
0xd514c  ldloc.s  7
0xd514e  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_IsMetadataBound()
0xd5153  brfalse.s loc_D5162
0xd5155  ldloc.s  7
0xd5157  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_IsFromRelatedEntity()
0xd515c  brtrue.s loc_D5162
0xd515e  ldloc.s  0x10
0xd5160  brtrue.s loc_D517F
0xd5162  ldc.i4.0
0xd5163  stloc.s  0xC
0xd5165  ldsfld   string [mscorlib]System.String::Empty
0xd516a  stloc.s  0xF
0xd516c  ldloc.s  7
0xd516e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_UIInfo()
0xd5173  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo::get_Label()
0xd5178  stloc.s  0xD
0xd517a  br       loc_D5244
0xd517f  ldloc.s  0x10
0xd5181  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0xd5186  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xd518b  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xd5190  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd5195  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd519a  stloc.s  0xD
0xd519c  ldloc.s  0x10
0xd519e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Description()
0xd51a3  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xd51a8  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xd51ad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd51b2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd51b7  stloc.s  0xF
0xd51b9  ldloc.s  0x10
0xd51bb  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportHelper::IsAttributeMandatoryAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0xd51c0  stloc.s  0xB
0xd51c2  ldloc.s  0xE
0xd51c4  ldstr    aCreatedon// "createdon"
0xd51c9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd51ce  brtrue.s loc_D51E0
0xd51d0  ldloc.s  0xE
0xd51d2  ldstr    aOverriddencrea// "overriddencreatedon"
0xd51d7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd51dc  brtrue.s loc_D51E9
0xd51de  br.s     loc_D51F2
0xd51e0  ldstr    aOverriddencrea// "overriddencreatedon"
0xd51e5  stloc.s  0x13
0xd51e7  br.s     loc_D51F6
0xd51e9  ldstr    aCreatedon// "createdon"
0xd51ee  stloc.s  0x13
0xd51f0  br.s     loc_D51F6
0xd51f2  ldloc.s  0xE
0xd51f4  stloc.s  0x13
0xd51f6  ldloc.0
0xd51f7  ldloc.s  0x13
0xd51f9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0xd51fe  ldloc.s  5
0xd5200  ldloc.s  0x13
0xd5202  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0xd5207  stloc.s  0xC
0xd5209  dup
0xd520a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForUpdate()
0xd520f  ldc.i4.0
0xd5210  ceq
0xd5212  stloc.s  9
0xd5214  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForCreate()
0xd5219  ldc.i4.0
0xd521a  ceq
0xd521c  stloc.s  0xA
0xd521e  ldloc.s  0x10
0xd5220  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xd5225  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0xd522a  ldc.i4.s 0xE
0xd522c  beq.s    loc_D523E
0xd522e  ldloc.s  0x10
0xd5230  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xd5235  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0xd523a  ldc.i4.s 0xA
0xd523c  bne.un.s loc_D5244
0xd523e  ldc.i4.0
0xd523f  stloc.s  9
0xd5241  ldc.i4.0
0xd5242  stloc.s  0xA
0xd5244  ldloc.s  0xD
0xd5246  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd524b  brfalse.s loc_D5254
0xd524d  ldloc.s  0xE
0xd524f  stloc.s  0xD
0xd5251  ldc.i4.0
0xd5252  stloc.s  0xC
0xd5254  ldloc.s  0xC
0xd5256  brtrue.s loc_D5264
0xd5258  ldloc.2
0xd5259  ldarg.0
0xd525a  ldfld    int32 Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToSpreadsheetML::columnCount
0xd525f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties::AddNonImportableColumnIndex(int32)
0xd5264  ldloc.s  0xC
0xd5266  ldc.i4.0
0xd5267  ceq
0xd5269  ldloc.s  8
0xd526b  or
0xd526c  brfalse.s loc_D5274
0xd526e  ldc.i4.1
0xd526f  stloc.s  9
0xd5271  ldc.i4.1
0xd5272  stloc.s  0xA
0xd5274  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xd5279  ldloc.s  4
0xd527b  ldc.i4.1
0xd527c  newarr   [mscorlib]System.Object
0xd5281  dup
0xd5282  ldc.i4.0
0xd5283  ldloc.s  0xD
0xd5285  stelem.ref
0xd5286  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd528b  stloc.s  0x11
0xd528d  ldloc.s  8
0xd528f  brtrue.s loc_D5295
0xd5291  ldloc.s  0xD
0xd5293  br.s     loc_D5297
0xd5295  ldloc.s  0x11
0xd5297  ldloc.s  0xE
0xd5299  ldloc.s  0xF
0xd529b  ldloc.s  9
0xd529d  ldloc.s  0xA
0xd529f  ldloc.s  8
0xd52a1  ldloc.s  0xB
0xd52a3  ldloc.s  0xC
0xd52a5  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties::.ctor(string, string, string, bool, bool, bool, bool, bool)
0xd52aa  stloc.s  0x12
0xd52ac  ldloc.3
0xd52ad  ldloc.s  0x12
0xd52af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties>::Add(var<u1>)
0xd52b4  ldarg.0
0xd52b5  ldarg.0
0xd52b6  ldfld    int32 Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToSpreadsheetML::columnCount
0xd52bb  ldc.i4.1
0xd52bc  add
0xd52bd  stfld    int32 Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToSpreadsheetML::columnCount
0xd52c2  ldloc.s  0xC
0xd52c4  brfalse.s loc_D5305
0xd52c6  ldarg.0
0xd52c7  ldloc.s  7
0xd52c9  ldloc.0
0xd52ca  call     instance bool Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToSpreadsheetML::NeedsDuplication(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column column, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0xd52cf  brfalse.s loc_D5305
0xd52d1  ldloc.2
0xd52d2  ldarg.0
0xd52d3  ldfld    int32 Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToSpreadsheetML::columnCount
0xd52d8  ldc.i4.1
0xd52d9  sub
0xd52da  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties::AddDuplicatedColumnIndex(int32)
0xd52df  ldloc.3
0xd52e0  ldloc.s  0x11
0xd52e2  ldloc.s  0xE
0xd52e4  ldloc.s  0xF
0xd52e6  ldc.i4.1
0xd52e7  ldc.i4.1
0xd52e8  ldc.i4.1
0xd52e9  ldloc.s  0xB
0xd52eb  ldloc.s  0xC
0xd52ed  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties::.ctor(string, string, string, bool, bool, bool, bool, bool)
0xd52f2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties>::Add(var<u1>)
0xd52f7  ldarg.0
0xd52f8  ldarg.0
0xd52f9  ldfld    int32 Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToSpreadsheetML::columnCount
0xd52fe  ldc.i4.1
0xd52ff  add
0xd5300  stfld    int32 Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToSpreadsheetML::columnCount
0xd5305  ldloc.s  6
0xd5307  ldc.i4.1
0xd5308  add
0xd5309  stloc.s  6
0xd530b  ldloc.s  6
0xd530d  ldarg.0
0xd530e  call     instance class Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor Microsoft.Crm.Application.Controls.Grid.UI.LayoutProvider::get_LayoutDescriptor()
0xd5313  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnCollection Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor::get_Columns()
0xd5318  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xd531d  blt      loc_D506D
0xd5322  ldarg.0
0xd5323  ldloc.2
0xd5324  ldloc.3
0xd5325  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties>)
  ... truncated ...
```
