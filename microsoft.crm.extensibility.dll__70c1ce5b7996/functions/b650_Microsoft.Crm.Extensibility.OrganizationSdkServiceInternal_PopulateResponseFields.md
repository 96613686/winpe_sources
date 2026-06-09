# Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::PopulateResponseFields

- ea: `0xb650`
- end: `0xb867`
- name: `Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::PopulateResponseFields`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xaff0`

## callees

- `0xb630`
- `0xb650`
- `0xbce0`

## string_xrefs

- `0xb819`: `Update`
- `0xb82c`: `Create`
- `0xb6dc`: `[ExtendedRetrieveMultipleNullChecks] Expected a response to RetrieveMultiple to have at least one field (EntityCollection), but the response description did not request any fields -- check the SdkResponseDescriptionCache.`

## pseudocode

```c

```

## disassembly

```asm
0xb650  ldarg.2
0xb651  brfalse  loc_B813
0xb656  ldarg.0
0xb657  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_ResponseName()
0xb65c  ldstr    aRetrievemultip// "RetrieveMultiple"
0xb661  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0xb666  brfalse  loc_B6EE
0xb66b  ldstr    aExtendedretrie// "ExtendedRetrieveMultipleNullChecks"
0xb670  ldc.i4.0
0xb671  box      [mscorlib]System.Int32
0xb676  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xb67b  unbox.any [mscorlib]System.Int32
0xb680  ldc.i4.1
0xb681  bne.un.s loc_B6EE
0xb683  ldnull
0xb684  ldstr    aNotAnErrorExte// "Not An Error: [ExtendedRetrieveMultiple"...
0xb689  ldc.i4.2
0xb68a  newarr   [mscorlib]System.Object
0xb68f  dup
0xb690  ldc.i4.0
0xb691  ldarg.2
0xb692  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseDescription::get_Fields()
0xb697  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription>::get_Count()
0xb69c  box      [mscorlib]System.Int32
0xb6a1  stelem.ref
0xb6a2  dup
0xb6a3  ldc.i4.1
0xb6a4  ldarg.2
0xb6a5  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseDescription::get_Fields()
0xb6aa  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription>::get_Count()
0xb6af  ldc.i4.1
0xb6b0  beq.s    loc_B6B9
0xb6b2  ldstr    aS// "s"
0xb6b7  br.s     loc_B6BE
0xb6b9  ldstr    asc_39E2A// ""
0xb6be  stelem.ref
0xb6bf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0xb6c4  ldarg.2
0xb6c5  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseDescription::get_Fields()
0xb6ca  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription>::get_Count()
0xb6cf  brtrue.s loc_B6EE
0xb6d1  ldstr    asc_39E2A// ""
0xb6d6  newobj   instance void Microsoft.Crm.Extensibility.SdkResponseDescriptionIncorrectException::.ctor(string hint)
0xb6db  throw
0xb6dc  ldstr    aExtendedretrie_0// "[ExtendedRetrieveMultipleNullChecks] Ex"...
0xb6e1  ldc.i4.0
0xb6e2  newarr   [mscorlib]System.Object
0xb6e7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0xb6ec  leave.s  loc_B6EE
0xb6ee  ldarg.2
0xb6ef  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseDescription::get_Fields()
0xb6f4  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription>::GetEnumerator()
0xb6f9  stloc.0
0xb6fa  br       loc_B7F7
0xb6ff  ldloca.s 0
0xb701  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription>::get_Current()
0xb706  stloc.1
0xb707  ldarg.0
0xb708  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_ResponseName()
0xb70d  ldstr    aRetrievemultip// "RetrieveMultiple"
0xb712  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0xb717  brfalse.s loc_B754
0xb719  ldstr    aExtendedretrie// "ExtendedRetrieveMultipleNullChecks"
0xb71e  ldc.i4.0
0xb71f  box      [mscorlib]System.Int32
0xb724  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xb729  unbox.any [mscorlib]System.Int32
0xb72e  ldc.i4.1
0xb72f  bne.un.s loc_B754
0xb731  ldnull
0xb732  ldstr    aNotAnErrorExte_0// "Not An Error: [ExtendedRetrieveMultiple"...
0xb737  ldc.i4.2
0xb738  newarr   [mscorlib]System.Object
0xb73d  dup
0xb73e  ldc.i4.0
0xb73f  ldloc.1
0xb740  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription::get_Name()
0xb745  stelem.ref
0xb746  dup
0xb747  ldc.i4.1
0xb748  ldloc.1
0xb749  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription::get_ValueSource()
0xb74e  stelem.ref
0xb74f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0xb754  ldnull
0xb755  stloc.2
0xb756  ldarg.1
0xb757  ldloc.1
0xb758  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription::get_ValueSource()
0xb75d  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xb762  brfalse.s loc_B7CA
0xb764  ldarg.1
0xb765  ldloc.1
0xb766  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription::get_ValueSource()
0xb76b  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb770  stloc.3
0xb771  ldloc.1
0xb772  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription::get_ClrFormatter()
0xb777  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb77c  brtrue.s loc_B7C8
0xb77e  ldloc.1
0xb77f  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription::get_ClrFormatter()
0xb784  call     class [mscorlib]System.Type Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::GetFieldValueType(string parserType)
0xb789  stloc.s  4
0xb78b  ldloc.s  4
0xb78d  ldnull
0xb78e  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xb793  brfalse.s loc_B7C8
0xb795  ldloc.3
0xb796  brfalse.s loc_B7C8
0xb798  ldloc.3
0xb799  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xb79e  ldloc.s  4
0xb7a0  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xb7a5  brfalse.s loc_B7C8
0xb7a7  ldarg.3
0xb7a8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_UserId()
0xb7ad  ldarg.s  4
0xb7af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0xb7b4  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.UserAndOrganizationContext::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb7b9  ldc.i4.0
0xb7ba  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ConversionContext::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext, int32)
0xb7bf  ldloc.3
0xb7c0  ldloc.s  4
0xb7c2  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ConversionHelpers::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, object, class [mscorlib]System.Type)
0xb7c7  stloc.3
0xb7c8  ldloc.3
0xb7c9  stloc.2
0xb7ca  ldloc.1
0xb7cb  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription::get_ValueSource()
0xb7d0  ldstr    aNotifications// "Notifications"
0xb7d5  ldc.i4.4
0xb7d6  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xb7db  brfalse.s loc_B7E0
0xb7dd  ldloc.2
0xb7de  brfalse.s loc_B7F7
0xb7e0  ldarg.0
0xb7e1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xb7e6  ldloc.1
0xb7e7  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription::get_Name()
0xb7ec  ldloc.2
0xb7ed  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::.ctor(var<u1>, !!T0)
0xb7f2  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>)
0xb7f7  ldloca.s 0
0xb7f9  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription>::MoveNext()
0xb7fe  brtrue   loc_B6FF
0xb803  leave.s  loc_B813
0xb805  ldloca.s 0
0xb807  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Caching.SdkResponseFieldDescription>
0xb80d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb812  endfinally
0xb813  ldarg.0
0xb814  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_ResponseName()
0xb819  ldstr    aUpdate// "Update"
0xb81e  ldc.i4.3
0xb81f  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xb824  brtrue.s loc_B839
0xb826  ldarg.0
0xb827  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_ResponseName()
0xb82c  ldstr    aCreate// "Create"
0xb831  ldc.i4.3
0xb832  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xb837  brfalse.s loc_B866
0xb839  ldarg.1
0xb83a  ldstr    aEntityreferenc_0// "EntityReference"
0xb83f  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xb844  brfalse.s loc_B866
0xb846  ldarg.0
0xb847  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0xb84c  ldstr    aEntityreferenc_0// "EntityReference"
0xb851  ldarg.1
0xb852  ldstr    aEntityreferenc_0// "EntityReference"
0xb857  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xb85c  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::.ctor(var<u1>, !!T0)
0xb861  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>)
0xb866  ret
```
