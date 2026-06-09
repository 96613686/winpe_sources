# Microsoft.Crm.ObjectModel.SyncManager::SelectClause

- ea: `0x166200`
- end: `0x166576`
- name: `Microsoft.Crm.ObjectModel.SyncManager::SelectClause`
- size: `886`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x165fe0`

## callees

- `0x1649c0`
- `0x166200`
- `0x168f70`

## string_xrefs

- `0x166421`: `ComponentState`
- `0x16645b`: `ComponentState`
- `0x1664a3`: `ComponentState`
- `0x1664d6`: `ComponentState`
- `0x1662ee`: `(Globals!RenderFormat.Name = "EXCEL" or Globals!RenderFormat.Name = "EXCELOPENXML")`
- `0x1662f5`: `(Globals!RenderFormat.Name = "PDF" or Globals!RenderFormat.Name = "IMAGE" or Globals!RenderFormat.Name = "WORD" or Globals!RenderFormat.Name = "WORDOPENXML" or Globals!RenderFormat.IsInteractive)`
- `0x166302`: `REPLACE(REPLACE(bodytext, '{0}','true'), '{1}', 'false') as {2}`
- `0x1663e2`: `REPLACE(REPLACE(REPLACE(xaml, 'IsUnbound="False"', ''),'IsUnbound="True"', ''),'IsUnbound="{x:Null}"', '')`
- `0x16642f`: `OverwriteTime`

## pseudocode

```c

```

## disassembly

```asm
0x166200  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x166205  ldarg.s  5
0x166207  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x16620c  ldarg.s  5
0x16620e  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x166213  pop
0x166214  ldc.i4.1
0x166215  stloc.0
0x166216  ldc.i4   0x400
0x16621b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x166220  stloc.1
0x166221  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x166226  stloc.2
0x166227  ldarg.3
0x166228  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesSortedByColumnNumber()
0x16622d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::GetEnumerator()
0x166232  stloc.3
0x166233  br       loc_16655D
0x166238  ldloc.3
0x166239  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Current()
0x16623e  stloc.s  4
0x166240  ldloc.s  4
0x166242  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsLogical()
0x166247  brtrue   loc_16655D
0x16624c  ldloc.s  4
0x16624e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsReplicated()
0x166253  brfalse  loc_16655D
0x166258  ldloc.0
0x166259  brfalse.s loc_166268
0x16625b  ldc.i4.0
0x16625c  stloc.0
0x16625d  ldloc.1
0x16625e  ldc.i4.s 0x20
0x166260  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x166265  pop
0x166266  br.s     loc_166274
0x166268  ldloc.1
0x166269  ldstr    asc_2790D6// ", "
0x16626e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x166273  pop
0x166274  ldloc.s  4
0x166276  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsStoredOnPrimaryTable()
0x16627b  brtrue.s loc_166280
0x16627d  ldarg.2
0x16627e  br.s     loc_166281
0x166280  ldarg.1
0x166281  stloc.s  5
0x166283  ldloc.s  4
0x166285  ldc.i4.1
0x166286  ldarg.s  5
0x166288  ldloc.s  5
0x16628a  ldloca.s 6
0x16628c  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::NeedFieldLevelSecurityJoin(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.SecuredAttributeRetrieveBehavior, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>&)
0x166291  brfalse.s loc_1662C3
0x166293  ldloca.s 6
0x166295  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Value()
0x16629a  ldloc.s  5
0x16629c  ldc.i4.0
0x16629d  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetReferenceToAttributeWithTableAliasString(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, string, bool)
0x1662a2  stloc.s  7
0x1662a4  ldloc.s  4
0x1662a6  ldloc.s  7
0x1662a8  ldarg.s  5
0x1662aa  ldarg.s  4
0x1662ac  ldloc.s  6
0x1662ae  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GetFieldLevelSecuritySql(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.SecuredAttributeJoinInfoCollectionWrapper, valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>)
0x1662b3  stloc.s  8
0x1662b5  ldloc.1
0x1662b6  ldloc.s  8
0x1662b8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1662bd  pop
0x1662be  br       loc_16655D
0x1662c3  ldloc.s  4
0x1662c5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x1662ca  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x1662cf  ldstr    aReport// "Report"
0x1662d4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1662d9  brfalse.s loc_16632C
0x1662db  ldloc.s  4
0x1662dd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x1662e2  ldstr    aBodytext// "bodytext"
0x1662e7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1662ec  brfalse.s loc_16632C
0x1662ee  ldstr    aGlobalsRenderf// "(Globals!RenderFormat.Name = \"EXCEL\" "...
0x1662f3  stloc.s  9
0x1662f5  ldstr    aGlobalsRenderf_0// "(Globals!RenderFormat.Name = \"PDF\" or"...
0x1662fa  stloc.s  0xA
0x1662fc  ldloc.1
0x1662fd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x166302  ldstr    aReplaceReplace// "REPLACE(REPLACE(bodytext, '{0}','true')"...
0x166307  ldc.i4.3
0x166308  newarr   [mscorlib]System.Object
0x16630d  dup
0x16630e  ldc.i4.0
0x16630f  ldloc.s  9
0x166311  stelem.ref
0x166312  dup
0x166313  ldc.i4.1
0x166314  ldloc.s  0xA
0x166316  stelem.ref
0x166317  dup
0x166318  ldc.i4.2
0x166319  ldloc.s  4
0x16631b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x166320  stelem.ref
0x166321  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x166326  pop
0x166327  br       loc_16655D
0x16632c  ldloc.s  4
0x16632e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x166333  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x166338  ldstr    aTimezonerule// "TimeZoneRule"
0x16633d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x166342  brfalse.s loc_16639C
0x166344  ldloc.s  4
0x166346  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x16634b  ldstr    aEffectivedatet// "effectivedatetime"
0x166350  call     bool [mscorlib]System.String::op_Equality(string, string)
0x166355  brfalse.s loc_16639C
0x166357  ldarg.0
0x166358  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.SyncManager::_subscriptionId
0x16635d  ldarg.0
0x16635e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SyncSettingBase::_context
0x166363  ldc.i4.7
0x166364  ldc.i4.1
0x166365  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32)
0x16636a  call     bool Microsoft.Crm.ObjectModel.SubscriptionUtils::IsClientVersionLessThanGivenVersion(valuetype [mscorlib]System.Guid subscriptionId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [mscorlib]System.Version givenVersion)
0x16636f  brfalse.s loc_16639C
0x166371  ldloc.1
0x166372  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x166377  ldstr    aIsnullCaseWhen// "isnull(CASE WHEN {1}.{0} < '1900-01-01'"...
0x16637c  ldc.i4.2
0x16637d  newarr   [mscorlib]System.Object
0x166382  dup
0x166383  ldc.i4.0
0x166384  ldloc.s  4
0x166386  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x16638b  stelem.ref
0x16638c  dup
0x16638d  ldc.i4.1
0x16638e  ldloc.s  5
0x166390  stelem.ref
0x166391  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x166396  pop
0x166397  br       loc_16655D
0x16639c  ldloc.s  4
0x16639e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x1663a3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x1663a8  ldstr    aWorkflow// "Workflow"
0x1663ad  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1663b2  brfalse.s loc_1663F2
0x1663b4  ldloc.s  4
0x1663b6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x1663bb  ldstr    aXaml// "xaml"
0x1663c0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1663c5  brfalse.s loc_1663F2
0x1663c7  ldarg.0
0x1663c8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.SyncManager::_subscriptionId
0x1663cd  ldarg.0
0x1663ce  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.SyncSettingBase::_context
0x1663d3  ldc.i4.8
0x1663d4  ldc.i4.2
0x1663d5  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32)
0x1663da  call     bool Microsoft.Crm.ObjectModel.SubscriptionUtils::IsClientVersionLessThanGivenVersion(valuetype [mscorlib]System.Guid subscriptionId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [mscorlib]System.Version givenVersion)
0x1663df  brfalse.s loc_1663F2
0x1663e1  ldloc.1
0x1663e2  ldstr    aReplaceReplace_0// "REPLACE(REPLACE(REPLACE(xaml, 'IsUnboun"...
0x1663e7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1663ec  pop
0x1663ed  br       loc_16655D
0x1663f2  ldarg.3
0x1663f3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsSnapshotRequired()
0x1663f8  brfalse  loc_166516
0x1663fd  ldarg.0
0x1663fe  call     instance bool Microsoft.Crm.ObjectModel.SyncManager::get_RequiresSnapshotRows()
0x166403  brfalse  loc_166516
0x166408  ldloc.s  4
0x16640a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x16640f  stloc.s  0xB
0x166411  ldloc.s  0xB
0x166413  ldstr    aSolutionid_0// "SolutionId"
0x166418  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16641d  brtrue.s loc_166443
0x16641f  ldloc.s  0xB
0x166421  ldstr    aComponentstate_3// "ComponentState"
0x166426  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16642b  brtrue.s loc_16648B
0x16642d  ldloc.s  0xB
0x16642f  ldstr    aOverwritetime_0// "OverwriteTime"
0x166434  call     bool [mscorlib]System.String::op_Equality(string, string)
0x166439  brtrue   loc_1664BE
0x16643e  br       loc_1664EE
0x166443  ldloc.1
0x166444  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x166449  ldstr    aIsnullCastCase// "isnull(cast(CASE {0}.{1} WHEN 4 then {0"...
0x16644e  ldc.i4.5
0x16644f  newarr   [mscorlib]System.Object
0x166454  dup
0x166455  ldc.i4.0
0x166456  ldloc.s  5
0x166458  stelem.ref
0x166459  dup
0x16645a  ldc.i4.1
0x16645b  ldstr    aComponentstate_3// "ComponentState"
0x166460  stelem.ref
0x166461  dup
0x166462  ldc.i4.2
0x166463  ldloc.s  4
0x166465  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x16646a  stelem.ref
0x16646b  dup
0x16646c  ldc.i4.3
0x16646d  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x166472  box      [mscorlib]System.Guid
0x166477  stelem.ref
0x166478  dup
0x166479  ldc.i4.4
0x16647a  ldstr    aSupportingsolu// "SupportingSolutionId"
0x16647f  stelem.ref
0x166480  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x166485  pop
0x166486  br       loc_16655D
0x16648b  ldloc.1
0x16648c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x166491  ldstr    aIsnullCastCase_0// "isnull(cast(CASE {0}.{1} WHEN 4 then (0"...
0x166496  ldc.i4.3
0x166497  newarr   [mscorlib]System.Object
0x16649c  dup
0x16649d  ldc.i4.0
0x16649e  ldloc.s  5
0x1664a0  stelem.ref
0x1664a1  dup
0x1664a2  ldc.i4.1
0x1664a3  ldstr    aComponentstate_3// "ComponentState"
0x1664a8  stelem.ref
0x1664a9  dup
0x1664aa  ldc.i4.2
0x1664ab  ldloc.s  4
0x1664ad  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x1664b2  stelem.ref
0x1664b3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1664b8  pop
0x1664b9  br       loc_16655D
0x1664be  ldloc.1
0x1664bf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1664c4  ldstr    aIsnullCastCase_1// "isnull(cast(CASE {0}.{1} WHEN 4 then (0"...
0x1664c9  ldc.i4.3
0x1664ca  newarr   [mscorlib]System.Object
0x1664cf  dup
0x1664d0  ldc.i4.0
0x1664d1  ldloc.s  5
0x1664d3  stelem.ref
0x1664d4  dup
0x1664d5  ldc.i4.1
0x1664d6  ldstr    aComponentstate_3// "ComponentState"
0x1664db  stelem.ref
0x1664dc  dup
0x1664dd  ldc.i4.2
0x1664de  ldloc.s  4
0x1664e0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x1664e5  stelem.ref
0x1664e6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1664eb  pop
0x1664ec  br.s     loc_16655D
0x1664ee  ldloc.1
0x1664ef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1664f4  ldstr    a01_3// "{0}.{1}"
0x1664f9  ldc.i4.2
0x1664fa  newarr   [mscorlib]System.Object
0x1664ff  dup
0x166500  ldc.i4.0
0x166501  ldloc.s  5
0x166503  stelem.ref
0x166504  dup
0x166505  ldc.i4.1
0x166506  ldloc.s  4
0x166508  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x16650d  stelem.ref
0x16650e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x166513  pop
0x166514  br.s     loc_16655D
0x166516  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16651b  ldstr    a01_3// "{0}.{1}"
0x166520  ldc.i4.2
0x166521  newarr   [mscorlib]System.Object
0x166526  dup
0x166527  ldc.i4.0
0x166528  ldloc.s  5
0x16652a  stelem.ref
0x16652b  dup
0x16652c  ldc.i4.1
0x16652d  ldloc.s  4
0x16652f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x166534  stelem.ref
0x166535  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16653a  stloc.s  0xC
0x16653c  ldloc.2
0x16653d  ldloc.s  0xC
0x16653f  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x166544  brtrue.s loc_16655D
  ... truncated ...
```
