# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::UpdatePrimaryImage

- ea: `0x4230`
- end: `0x4388`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::UpdatePrimaryImage`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x220`
- `0x4230`
- `0x4390`

## pseudocode

```c

```

## disassembly

```asm
0x4230  ldsfld   string [mscorlib]System.String::Empty
0x4235  stloc.0
0x4236  ldarg.2
0x4237  ldstr    aPrimaryimagena// "primaryimagename"
0x423c  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x4241  brfalse.s loc_424F
0x4243  ldarg.2
0x4244  ldstr    aPrimaryimagena// "primaryimagename"
0x4249  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x424e  stloc.0
0x424f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0x4254  ldarg.1
0x4255  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x425a  stloc.1
0x425b  ldloc.1
0x425c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x4261  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x4266  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x426b  stloc.2
0x426c  br.s     loc_42D0
0x426e  ldloc.2
0x426f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4274  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x4279  stloc.3
0x427a  ldloc.3
0x427b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x4280  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x4285  ldstr    aImage// "image"
0x428a  ldc.i4.4
0x428b  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x4290  brfalse.s loc_42D0
0x4292  ldloc.3
0x4293  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x4298  ldloc.0
0x4299  ldc.i4.4
0x429a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x429f  brtrue.s loc_42D0
0x42a1  ldloc.3
0x42a2  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayMask()
0x42a7  ldc.i4   0x1000000
0x42ac  and
0x42ad  brfalse.s loc_42D0
0x42af  ldloc.3
0x42b0  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayMask()
0x42b5  ldc.i4   0xFEFFFFFF
0x42ba  and
0x42bb  stloc.s  4
0x42bd  ldarg.0
0x42be  ldloc.3
0x42bf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x42c4  ldstr    aImage// "image"
0x42c9  ldloc.s  4
0x42cb  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::UpdateAttributeDisplayMask(valuetype [mscorlib]System.Guid solutionId, valuetype [mscorlib]System.Guid attributeId, string attributeType, int32 displayMask)
0x42d0  ldloc.2
0x42d1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x42d6  brtrue.s loc_426E
0x42d8  leave.s  loc_42EE
0x42da  ldloc.2
0x42db  isinst   [mscorlib]System.IDisposable
0x42e0  stloc.s  5
0x42e2  ldloc.s  5
0x42e4  brfalse.s loc_42ED
0x42e6  ldloc.s  5
0x42e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x42ed  endfinally
0x42ee  ldloc.1
0x42ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x42f4  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x42f9  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x42fe  stloc.2
0x42ff  br.s     loc_4369
0x4301  ldloc.2
0x4302  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4307  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x430c  stloc.s  6
0x430e  ldloc.s  6
0x4310  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x4315  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x431a  ldstr    aImage// "image"
0x431f  ldc.i4.4
0x4320  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x4325  brfalse.s loc_4369
0x4327  ldloc.s  6
0x4329  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x432e  ldloc.0
0x432f  ldc.i4.4
0x4330  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x4335  brfalse.s loc_4369
0x4337  ldloc.s  6
0x4339  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayMask()
0x433e  ldc.i4   0x1000000
0x4343  and
0x4344  brtrue.s loc_4369
0x4346  ldloc.s  6
0x4348  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayMask()
0x434d  ldc.i4   0x1000000
0x4352  or
0x4353  stloc.s  7
0x4355  ldarg.0
0x4356  ldloc.s  6
0x4358  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x435d  ldstr    aImage// "image"
0x4362  ldloc.s  7
0x4364  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::UpdateAttributeDisplayMask(valuetype [mscorlib]System.Guid solutionId, valuetype [mscorlib]System.Guid attributeId, string attributeType, int32 displayMask)
0x4369  ldloc.2
0x436a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x436f  brtrue.s loc_4301
0x4371  leave.s  loc_4387
0x4373  ldloc.2
0x4374  isinst   [mscorlib]System.IDisposable
0x4379  stloc.s  5
0x437b  ldloc.s  5
0x437d  brfalse.s loc_4386
0x437f  ldloc.s  5
0x4381  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4386  endfinally
0x4387  ret
```
