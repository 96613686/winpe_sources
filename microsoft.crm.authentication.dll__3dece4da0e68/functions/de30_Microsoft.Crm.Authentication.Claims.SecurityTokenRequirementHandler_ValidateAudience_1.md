# Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::ValidateAudience_1

- ea: `0xde30`
- end: `0xde77`
- name: `Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::ValidateAudience_1`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xdd40`
- `0xddc0`

## callees

- `0x5340`
- `0x5360`
- `0xde30`
- `0xde80`

## pseudocode

```c

```

## disassembly

```asm
0xde30  ldnull
0xde31  stloc.0
0xde32  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xde37  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xde3c  stloc.1
0xde3d  ldloc.1
0xde3e  ldc.i4.1
0xde3f  beq.s    loc_DE4F
0xde41  ldloc.1
0xde42  ldc.i4.2
0xde43  bne.un.s loc_DE66
0xde45  ldc.i4.1
0xde46  ldc.i4.1
0xde47  call     class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider [Microsoft.Crm.Core]Microsoft.Crm.WebServices.OrganizationEndpointProviderFactory::Create(int32, bool)
0xde4c  stloc.0
0xde4d  br.s     loc_DE66
0xde4f  call     class Microsoft.Crm.Authentication.WebConfigAuthenticationSettings Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::get_Instance()
0xde54  callvirt instance bool Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::get_IfdEnabled()
0xde59  brtrue.s loc_DE5E
0xde5b  ldc.i4.0
0xde5c  br.s     loc_DE5F
0xde5e  ldc.i4.2
0xde5f  ldc.i4.1
0xde60  call     class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider [Microsoft.Crm.Core]Microsoft.Crm.WebServices.OrganizationEndpointProviderFactory::Create(int32, bool)
0xde65  stloc.0
0xde66  ldarg.0
0xde67  ldloc.0
0xde68  ldarg.1
0xde69  call     class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri> Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::ValidateCrmAudience(class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri> tokenAudiences, class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider endpointProvider, class [mscorlib]System.Collections.Generic.IList`1<class [System]System.Uri> allowedAudienceUris)
0xde6e  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [System]System.Uri>::get_Count()
0xde73  ldc.i4.0
0xde74  ceq
0xde76  ret
```
