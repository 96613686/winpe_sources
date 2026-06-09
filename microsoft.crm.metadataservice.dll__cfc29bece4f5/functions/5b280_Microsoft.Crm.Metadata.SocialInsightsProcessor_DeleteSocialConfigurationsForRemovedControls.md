# Microsoft.Crm.Metadata.SocialInsightsProcessor::DeleteSocialConfigurationsForRemovedControls

- ea: `0x5b280`
- end: `0x5b2f8`
- name: `Microsoft.Crm.Metadata.SocialInsightsProcessor::DeleteSocialConfigurationsForRemovedControls`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5b200`

## callees

- `0x5b280`
- `0x5b300`

## string_xrefs

- `0x5b2cb`: `SocialInsightsConfiguration`
- `0x5b2bc`: `socialinsightsconfigurationid`

## pseudocode

```c

```

## disassembly

```asm
0x5b280  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SocialInsightsConfigurationService::.ctor()
0x5b285  stloc.0
0x5b286  ldarg.0
0x5b287  ldloc.0
0x5b288  ldarg.2
0x5b289  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Metadata.SocialInsightsProcessor::RetrieveConfigurationRecordsForForm(valuetype [mscorlib]System.Guid formId, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SocialInsightsConfigurationService service, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b28e  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5b293  stloc.1
0x5b294  br.s     loc_5B2DC
0x5b296  ldloc.1
0x5b297  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5b29c  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SocialInsightsConfiguration
0x5b2a1  stloc.2
0x5b2a2  ldarg.1
0x5b2a3  ldloc.2
0x5b2a4  ldstr    aControlid// "controlid"
0x5b2a9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b2ae  castclass [mscorlib]System.String
0x5b2b3  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x5b2b8  brtrue.s loc_5B2DC
0x5b2ba  ldloc.0
0x5b2bb  ldloc.2
0x5b2bc  ldstr    aSocialinsights_0// "socialinsightsconfigurationid"
0x5b2c1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5b2c6  unbox.any [mscorlib]System.Guid
0x5b2cb  ldstr    aSocialinsights// "SocialInsightsConfiguration"
0x5b2d0  ldarg.2
0x5b2d1  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5b2d6  ldarg.2
0x5b2d7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5b2dc  ldloc.1
0x5b2dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5b2e2  brtrue.s loc_5B296
0x5b2e4  leave.s  loc_5B2F7
0x5b2e6  ldloc.1
0x5b2e7  isinst   [mscorlib]System.IDisposable
0x5b2ec  stloc.3
0x5b2ed  ldloc.3
0x5b2ee  brfalse.s loc_5B2F6
0x5b2f0  ldloc.3
0x5b2f1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b2f6  endfinally
0x5b2f7  ret
```
