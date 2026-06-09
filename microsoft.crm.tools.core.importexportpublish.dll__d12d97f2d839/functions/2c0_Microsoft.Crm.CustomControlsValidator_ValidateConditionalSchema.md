# Microsoft.Crm.CustomControlsValidator::ValidateConditionalSchema

- ea: `0x2c0`
- end: `0x493`
- name: `Microsoft.Crm.CustomControlsValidator::ValidateConditionalSchema`
- size: `467`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2c0`
- `0x4a0`
- `0x930`
- `0xac0`
- `0xc80`
- `0xf40`
- `0x11c0`
- `0x12e0`
- `0x1480`
- `0x16f0`
- `0x1800`
- `0x1b40`
- `0x1d70`
- `0x1f80`
- `0x24d0`
- `0x2790`
- `0x2910`
- `0x2e10`
- `0x2f70`
- `0x31d0`
- `0x33b0`
- `0x3570`
- `0x38a0`
- `0x3d20`

## string_xrefs

- `0x2c9`: `ValidateManifestMandateChildNodes`
- `0x31a`: `ValidateLookupManifestPropertyUsage`
- `0x32e`: `ValidateManifestBoundPropertyOfSameType`
- `0x356`: `ValidateManifestInputPropertyOfSameType`
- `0x3e2`: `ValidateManifestTypeGroup`
- `0x487`: `ValidateCompositeControls`

## pseudocode

```c

```

## disassembly

```asm
0x2c0  ldarg.0
0x2c1  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateManifestMandateChildNodes()
0x2c6  brtrue.s loc_2D4
0x2c8  ldarg.0
0x2c9  ldstr    aValidatemanife// "ValidateManifestMandateChildNodes"
0x2ce  ldarg.2
0x2cf  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x2d4  ldarg.0
0x2d5  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidatePropertyNode()
0x2da  brtrue.s loc_2E8
0x2dc  ldarg.0
0x2dd  ldstr    aValidateproper// "ValidatePropertyNode"
0x2e2  ldarg.2
0x2e3  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x2e8  ldarg.0
0x2e9  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidatePropertyDefaultValueAttribute()
0x2ee  brtrue.s loc_2FC
0x2f0  ldarg.0
0x2f1  ldstr    aValidateproper_0// "ValidatePropertyDefaultValueAttribute"
0x2f6  ldarg.2
0x2f7  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x2fc  ldarg.0
0x2fd  ldarg.1
0x2fe  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidatePrimaryProperty(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x303  brtrue.s loc_311
0x305  ldarg.0
0x306  ldstr    aValidateprimar// "ValidatePrimaryProperty"
0x30b  ldarg.2
0x30c  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x311  ldarg.0
0x312  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateLookupManifestPropertyUsage()
0x317  brtrue.s loc_325
0x319  ldarg.0
0x31a  ldstr    aValidatelookup// "ValidateLookupManifestPropertyUsage"
0x31f  ldarg.2
0x320  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x325  ldarg.0
0x326  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateManifestBoundPropertyOfSameType()
0x32b  brtrue.s loc_339
0x32d  ldarg.0
0x32e  ldstr    aValidatemanife_0// "ValidateManifestBoundPropertyOfSameType"
0x333  ldarg.2
0x334  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x339  ldarg.0
0x33a  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidatePropertyBound()
0x33f  brtrue.s loc_34D
0x341  ldarg.0
0x342  ldstr    aValidateproper_1// "ValidatePropertyBound"
0x347  ldarg.2
0x348  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x34d  ldarg.0
0x34e  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateManifestInputPropertyOfSameType()
0x353  brtrue.s loc_361
0x355  ldarg.0
0x356  ldstr    aValidatemanife_1// "ValidateManifestInputPropertyOfSameType"
0x35b  ldarg.2
0x35c  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x361  ldarg.0
0x362  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidatePropertyInput()
0x367  brtrue.s loc_375
0x369  ldarg.0
0x36a  ldstr    aValidateproper_2// "ValidatePropertyInput"
0x36f  ldarg.2
0x370  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x375  ldarg.0
0x376  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidatePropertySetNode()
0x37b  brtrue.s loc_389
0x37d  ldarg.0
0x37e  ldstr    aValidateproper_3// "ValidatePropertySetNode"
0x383  ldarg.2
0x384  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x389  ldarg.0
0x38a  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateMaxOccursValue()
0x38f  brtrue.s loc_39D
0x391  ldarg.0
0x392  ldstr    aValidatemaxocc// "ValidateMaxOccursValue"
0x397  ldarg.2
0x398  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x39d  ldarg.0
0x39e  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateConditionalPropertyType()
0x3a3  brtrue.s loc_3B1
0x3a5  ldarg.0
0x3a6  ldstr    aValidatecondit// "ValidateConditionalPropertyType"
0x3ab  ldarg.2
0x3ac  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x3b1  ldarg.0
0x3b2  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidatePropertyTypesNode()
0x3b7  brtrue.s loc_3C5
0x3b9  ldarg.0
0x3ba  ldstr    aValidateproper_4// "ValidatePropertyTypesNode"
0x3bf  ldarg.2
0x3c0  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x3c5  ldarg.0
0x3c6  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidatePropertySetTypesNode()
0x3cb  brtrue.s loc_3D9
0x3cd  ldarg.0
0x3ce  ldstr    aValidateproper_5// "ValidatePropertySetTypesNode"
0x3d3  ldarg.2
0x3d4  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x3d9  ldarg.0
0x3da  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateManifestTypeGroup()
0x3df  brtrue.s loc_3ED
0x3e1  ldarg.0
0x3e2  ldstr    aValidatemanife_2// "ValidateManifestTypeGroup"
0x3e7  ldarg.2
0x3e8  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x3ed  ldarg.0
0x3ee  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidatePropertyParameter()
0x3f3  brtrue.s loc_401
0x3f5  ldarg.0
0x3f6  ldstr    aValidateproper_6// "ValidatePropertyParameter"
0x3fb  ldarg.2
0x3fc  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x401  ldarg.0
0x402  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateConditionalPropertySetType()
0x407  brtrue.s loc_415
0x409  ldarg.0
0x40a  ldstr    aValidatecondit_0// "ValidateConditionalPropertySetType"
0x40f  ldarg.2
0x410  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x415  ldarg.0
0x416  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateResourceNode()
0x41b  brtrue.s loc_429
0x41d  ldarg.0
0x41e  ldstr    aValidateresour// "ValidateResourceNode"
0x423  ldarg.2
0x424  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x429  ldarg.0
0x42a  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateDependeciesNode()
0x42f  brtrue.s loc_43D
0x431  ldarg.0
0x432  ldstr    aValidatedepend// "ValidateDependeciesNode"
0x437  ldarg.2
0x438  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x43d  ldarg.0
0x43e  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateSchemaVersion()
0x443  brtrue.s loc_451
0x445  ldarg.0
0x446  ldstr    aValidateschema// "ValidateSchemaVersion"
0x44b  ldarg.2
0x44c  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x451  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x456  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x45b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlSolutionExport()
0x460  ldarg.1
0x461  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x466  brfalse.s loc_47D
0x468  ldarg.0
0x469  ldarg.1
0x46a  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateAvailableOnNode(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x46f  brtrue.s loc_47D
0x471  ldarg.0
0x472  ldstr    aValidateavaila// "ValidateAvailableOnNode"
0x477  ldarg.2
0x478  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x47d  ldarg.0
0x47e  ldarg.1
0x47f  call     instance bool Microsoft.Crm.CustomControlsValidator::ValidateCompositeControls(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x484  brtrue.s loc_492
0x486  ldarg.0
0x487  ldstr    aValidatecompos// "ValidateCompositeControls"
0x48c  ldarg.2
0x48d  call     instance void Microsoft.Crm.CustomControlsValidator::LogAndThrowConditionalValidationMessage(string errorMethod, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x492  ret
```
