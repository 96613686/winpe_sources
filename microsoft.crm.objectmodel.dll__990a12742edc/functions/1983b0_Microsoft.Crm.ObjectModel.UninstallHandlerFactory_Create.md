# Microsoft.Crm.ObjectModel.UninstallHandlerFactory::Create

- ea: `0x1983b0`
- end: `0x19872c`
- name: `Microsoft.Crm.ObjectModel.UninstallHandlerFactory::Create`
- size: `892`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x197a00`

## callees

- `0x1983b0`
- `0x198730`
- `0x22be40`

## string_xrefs

- `0x19862a`: `Privilege`
- `0x1983bf`: `Microsoft.Crm.MetadataService`
- `0x19863f`: `PrivilegeObjectTypeCode`
- `0x198653`: `Microsoft.Crm.Metadata.EntityUninstallHandler`
- `0x19865e`: `Microsoft.Crm.Metadata.AttributeUninstallHandler`
- `0x198669`: `Microsoft.Crm.Metadata.LabelUninstallHandler`
- `0x198674`: `Microsoft.Crm.Metadata.OptionSetUninstallHandler`
- `0x19867f`: `Microsoft.Crm.Metadata.EnumOptionUninstallHandler`
- `0x19868a`: `Microsoft.Crm.Metadata.EntityRelationshipUninstallHandler`
- `0x198692`: `Microsoft.Crm.Metadata.EntityRelationshipRolesUninstallHandler`
- `0x19869a`: `Microsoft.Crm.Metadata.EntityRelationshipRelationshipsUninstallHandler`
- `0x1986a2`: `Microsoft.Crm.Metadata.RelationshipUninstallHandler`
- `0x1986aa`: `Microsoft.Crm.Metadata.ViewAttributeUninstallHandler`
- `0x1986b2`: `Microsoft.Crm.Metadata.RelationshipExtraConditionUninstallHandler`
- `0x1986ba`: `Microsoft.Crm.Metadata.AttributeLookupValueUninstallHandler`
- `0x1986c2`: `Microsoft.Crm.Metadata.NullMetadataUninstallHandler`
- `0x1986ca`: `Microsoft.Crm.Metadata.EntityKeyUninstallHandler`
- `0x1986d2`: `Microsoft.Crm.Metadata.EntityKeyAttributeUninstallHandler`
- `0x1986da`: `Microsoft.Crm.Metadata.PrivilegeUninstallHandler`
- `0x1986e2`: `Microsoft.Crm.Metadata.PrivilegeObjectTypeCodeUninstallHandler`
- `0x1986ef`: `UninstallOperation class not implemented for Component: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1983b0  ldarg.0
0x1983b1  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData::get_IsMetadata()
0x1983b6  brtrue.s loc_1983BF
0x1983b8  ldarg.0
0x1983b9  call     class Microsoft.Crm.ObjectModel.UninstallHandler Microsoft.Crm.ObjectModel.UninstallHandlerFactory::CreateNonMetadataUninstaller(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData component)
0x1983be  ret
0x1983bf  ldstr    aMicrosoftCrmMe// "Microsoft.Crm.MetadataService"
0x1983c4  stloc.0
0x1983c5  ldarg.0
0x1983c6  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData::get_PlatformName()
0x1983cb  stloc.2
0x1983cc  ldloc.2
0x1983cd  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x1983d2  stloc.3
0x1983d3  ldloc.3
0x1983d4  ldc.i4   0x7A787910
0x1983d9  bgt.un   loc_198462
0x1983de  ldloc.3
0x1983df  ldc.i4   0x3578225F
0x1983e4  bgt.un.s loc_198424
0x1983e6  ldloc.3
0x1983e7  ldc.i4   0x21E27D10
0x1983ec  bgt.un.s loc_198409
0x1983ee  ldloc.3
0x1983ef  ldc.i4   0x1ACCD85B
0x1983f4  beq      loc_198596
0x1983f9  ldloc.3
0x1983fa  ldc.i4   0x21E27D10
0x1983ff  beq      loc_19856C
0x198404  br       loc_1986EA
0x198409  ldloc.3
0x19840a  ldc.i4   0x2FB17EF0
0x19840f  beq      loc_1985C0
0x198414  ldloc.3
0x198415  ldc.i4   0x3578225F
0x19841a  beq      loc_198542
0x19841f  br       loc_1986EA
0x198424  ldloc.3
0x198425  ldc.i4   0x62FA988F
0x19842a  bgt.un.s loc_198447
0x19842c  ldloc.3
0x19842d  ldc.i4   0x4F6B9560
0x198432  beq      loc_198557
0x198437  ldloc.3
0x198438  ldc.i4   0x62FA988F
0x19843d  beq      loc_198503
0x198442  br       loc_1986EA
0x198447  ldloc.3
0x198448  ldc.i4   0x6E61547A
0x19844d  beq      loc_19863E
0x198452  ldloc.3
0x198453  ldc.i4   0x7A787910
0x198458  beq      loc_198518
0x19845d  br       loc_1986EA
0x198462  ldloc.3
0x198463  ldc.i4   0x9F56E047
0x198468  bgt.un.s loc_1984A8
0x19846a  ldloc.3
0x19846b  ldc.i4   0x80D2874B
0x198470  bgt.un.s loc_19848D
0x198472  ldloc.3
0x198473  ldc.i4   0x7B5DF6A6
0x198478  beq      loc_1985D5
0x19847d  ldloc.3
0x19847e  ldc.i4   0x80D2874B
0x198483  beq      loc_198614
0x198488  br       loc_1986EA
0x19848d  ldloc.3
0x19848e  ldc.i4   0x946992DC
0x198493  beq      loc_19852D
0x198498  ldloc.3
0x198499  ldc.i4   0x9F56E047
0x19849e  beq      loc_198581
0x1984a3  br       loc_1986EA
0x1984a8  ldloc.3
0x1984a9  ldc.i4   0xC0670678
0x1984ae  bgt.un.s loc_1984CB
0x1984b0  ldloc.3
0x1984b1  ldc.i4   0xA6468091
0x1984b6  beq      loc_1985FF
0x1984bb  ldloc.3
0x1984bc  ldc.i4   0xC0670678
0x1984c1  beq      loc_1985AB
0x1984c6  br       loc_1986EA
0x1984cb  ldloc.3
0x1984cc  ldc.i4   0xC09B32FA
0x1984d1  beq.s    loc_1984EE
0x1984d3  ldloc.3
0x1984d4  ldc.i4   0xCEEE0703
0x1984d9  beq      loc_1985EA
0x1984de  ldloc.3
0x1984df  ldc.i4   0xF92D43AC
0x1984e4  beq      loc_198629
0x1984e9  br       loc_1986EA
0x1984ee  ldloc.2
0x1984ef  ldstr    aEntity// "Entity"
0x1984f4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1984f9  brtrue   loc_198653
0x1984fe  br       loc_1986EA
0x198503  ldloc.2
0x198504  ldstr    aAttribute// "Attribute"
0x198509  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19850e  brtrue   loc_19865E
0x198513  br       loc_1986EA
0x198518  ldloc.2
0x198519  ldstr    aLocalizedlabel// "LocalizedLabel"
0x19851e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198523  brtrue   loc_198669
0x198528  br       loc_1986EA
0x19852d  ldloc.2
0x19852e  ldstr    aOptionset// "OptionSet"
0x198533  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198538  brtrue   loc_198674
0x19853d  br       loc_1986EA
0x198542  ldloc.2
0x198543  ldstr    aAttributepickl// "AttributePicklistValue"
0x198548  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19854d  brtrue   loc_19867F
0x198552  br       loc_1986EA
0x198557  ldloc.2
0x198558  ldstr    aEntityrelation// "EntityRelationship"
0x19855d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198562  brtrue   loc_19868A
0x198567  br       loc_1986EA
0x19856c  ldloc.2
0x19856d  ldstr    aEntityrelation_0// "EntityRelationshipRole"
0x198572  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198577  brtrue   loc_198692
0x19857c  br       loc_1986EA
0x198581  ldloc.2
0x198582  ldstr    aEntityrelation_1// "EntityRelationshipRelationships"
0x198587  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19858c  brtrue   loc_19869A
0x198591  br       loc_1986EA
0x198596  ldloc.2
0x198597  ldstr    aRelationship// "Relationship"
0x19859c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1985a1  brtrue   loc_1986A2
0x1985a6  br       loc_1986EA
0x1985ab  ldloc.2
0x1985ac  ldstr    aViewattribute// "ViewAttribute"
0x1985b1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1985b6  brtrue   loc_1986AA
0x1985bb  br       loc_1986EA
0x1985c0  ldloc.2
0x1985c1  ldstr    aRelationshipex// "RelationshipExtraCondition"
0x1985c6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1985cb  brtrue   loc_1986B2
0x1985d0  br       loc_1986EA
0x1985d5  ldloc.2
0x1985d6  ldstr    aAttributelooku// "AttributeLookupValue"
0x1985db  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1985e0  brtrue   loc_1986BA
0x1985e5  br       loc_1986EA
0x1985ea  ldloc.2
0x1985eb  ldstr    aManagedpropert// "ManagedProperty"
0x1985f0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1985f5  brtrue   loc_1986C2
0x1985fa  br       loc_1986EA
0x1985ff  ldloc.2
0x198600  ldstr    aEntitykey// "EntityKey"
0x198605  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19860a  brtrue   loc_1986CA
0x19860f  br       loc_1986EA
0x198614  ldloc.2
0x198615  ldstr    aEntitykeyattri_1// "EntityKeyAttribute"
0x19861a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19861f  brtrue   loc_1986D2
0x198624  br       loc_1986EA
0x198629  ldloc.2
0x19862a  ldstr    aPrivilege// "Privilege"
0x19862f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198634  brtrue   loc_1986DA
0x198639  br       loc_1986EA
0x19863e  ldloc.2
0x19863f  ldstr    aPrivilegeobjec_0// "PrivilegeObjectTypeCode"
0x198644  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198649  brtrue   loc_1986E2
0x19864e  br       loc_1986EA
0x198653  ldstr    aMicrosoftCrmMe_0// "Microsoft.Crm.Metadata.EntityUninstallH"...
0x198658  stloc.1
0x198659  br       loc_19870E
0x19865e  ldstr    aMicrosoftCrmMe_1// "Microsoft.Crm.Metadata.AttributeUninsta"...
0x198663  stloc.1
0x198664  br       loc_19870E
0x198669  ldstr    aMicrosoftCrmMe_2// "Microsoft.Crm.Metadata.LabelUninstallHa"...
0x19866e  stloc.1
0x19866f  br       loc_19870E
0x198674  ldstr    aMicrosoftCrmMe_3// "Microsoft.Crm.Metadata.OptionSetUninsta"...
0x198679  stloc.1
0x19867a  br       loc_19870E
0x19867f  ldstr    aMicrosoftCrmMe_4// "Microsoft.Crm.Metadata.EnumOptionUninst"...
0x198684  stloc.1
0x198685  br       loc_19870E
0x19868a  ldstr    aMicrosoftCrmMe_5// "Microsoft.Crm.Metadata.EntityRelationsh"...
0x19868f  stloc.1
0x198690  br.s     loc_19870E
0x198692  ldstr    aMicrosoftCrmMe_6// "Microsoft.Crm.Metadata.EntityRelationsh"...
0x198697  stloc.1
0x198698  br.s     loc_19870E
0x19869a  ldstr    aMicrosoftCrmMe_7// "Microsoft.Crm.Metadata.EntityRelationsh"...
0x19869f  stloc.1
0x1986a0  br.s     loc_19870E
0x1986a2  ldstr    aMicrosoftCrmMe_8// "Microsoft.Crm.Metadata.RelationshipUnin"...
0x1986a7  stloc.1
0x1986a8  br.s     loc_19870E
0x1986aa  ldstr    aMicrosoftCrmMe_9// "Microsoft.Crm.Metadata.ViewAttributeUni"...
0x1986af  stloc.1
0x1986b0  br.s     loc_19870E
0x1986b2  ldstr    aMicrosoftCrmMe_10// "Microsoft.Crm.Metadata.RelationshipExtr"...
0x1986b7  stloc.1
0x1986b8  br.s     loc_19870E
0x1986ba  ldstr    aMicrosoftCrmMe_11// "Microsoft.Crm.Metadata.AttributeLookupV"...
0x1986bf  stloc.1
0x1986c0  br.s     loc_19870E
0x1986c2  ldstr    aMicrosoftCrmMe_12// "Microsoft.Crm.Metadata.NullMetadataUnin"...
0x1986c7  stloc.1
0x1986c8  br.s     loc_19870E
0x1986ca  ldstr    aMicrosoftCrmMe_13// "Microsoft.Crm.Metadata.EntityKeyUninsta"...
0x1986cf  stloc.1
0x1986d0  br.s     loc_19870E
0x1986d2  ldstr    aMicrosoftCrmMe_14// "Microsoft.Crm.Metadata.EntityKeyAttribu"...
0x1986d7  stloc.1
0x1986d8  br.s     loc_19870E
0x1986da  ldstr    aMicrosoftCrmMe_15// "Microsoft.Crm.Metadata.PrivilegeUninsta"...
0x1986df  stloc.1
0x1986e0  br.s     loc_19870E
0x1986e2  ldstr    aMicrosoftCrmMe_16// "Microsoft.Crm.Metadata.PrivilegeObjectT"...
0x1986e7  stloc.1
0x1986e8  br.s     loc_19870E
0x1986ea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1986ef  ldstr    aUninstallopera// "UninstallOperation class not implemente"...
0x1986f4  ldc.i4.1
0x1986f5  newarr   [mscorlib]System.Object
0x1986fa  dup
0x1986fb  ldc.i4.0
0x1986fc  ldarg.0
0x1986fd  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData::get_PlatformName()
0x198702  stelem.ref
0x198703  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x198708  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x19870d  throw
0x19870e  ldloc.0
0x19870f  ldloc.1
0x198710  ldc.i4.0
0x198711  newarr   [mscorlib]System.Object
0x198716  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string, string, object[])
0x19871b  ldc.i4.1
0x19871c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool)
0x198721  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x198726  castclass Microsoft.Crm.ObjectModel.UninstallHandler
0x19872b  ret
```
