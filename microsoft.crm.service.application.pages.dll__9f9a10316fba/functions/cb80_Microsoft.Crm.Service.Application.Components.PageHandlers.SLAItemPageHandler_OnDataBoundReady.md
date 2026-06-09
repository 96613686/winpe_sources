# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::OnDataBoundReady

- ea: `0xcb80`
- end: `0xcc94`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::OnDataBoundReady`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xc610`
- `0xc670`
- `0xcb80`
- `0xccc0`
- `0xccf0`
- `0xcdb0`
- `0x14350`
- `0x14380`
- `0x14410`

## pseudocode

```c

```

## disassembly

```asm
0xcb80  ldarg.0
0xcb81  ldarg.0
0xcb82  ldarg.0
0xcb83  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::get_SlaEntity()
0xcb88  call     instance bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::ShouldUseSLAKPI(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity SLA)
0xcb8d  stfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::useSLAKPI
0xcb92  ldarg.0
0xcb93  ldarg.0
0xcb94  ldarg.0
0xcb95  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::get_SlaEntity()
0xcb9a  call     instance bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::IsSLAStateActive(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity SLA)
0xcb9f  stfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::isSLAStateActive
0xcba4  ldarg.2
0xcba5  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0xcbaa  ldstr    aRelatedcasefie// "relatedcasefield"
0xcbaf  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xcbb4  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl
0xcbb9  stloc.0
0xcbba  ldloc.0
0xcbbb  ldc.i4.1
0xcbbc  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::set_AllowStringValues(bool)
0xcbc1  newobj   instance void AttributeRelationUtil::.ctor()
0xcbc6  stloc.1
0xcbc7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xcbcc  stloc.2
0xcbcd  ldarg.0
0xcbce  ldfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::useSLAKPI
0xcbd3  brtrue.s loc_CBE4
0xcbd5  ldloc.1
0xcbd6  ldarg.0
0xcbd7  call     instance int32 Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::get_ObjectTypeId()
0xcbdc  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> AttributeRelationUtil::RetrieveDateTimeAttributeList(int32 ObjectTypeId)
0xcbe1  stloc.2
0xcbe2  br.s     loc_CC17
0xcbe4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcbe9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xcbee  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xcbf3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcbf8  ldarg.0
0xcbf9  call     instance int32 Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::get_ObjectTypeId()
0xcbfe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xcc03  stloc.3
0xcc04  ldloc.1
0xcc05  ldloc.3
0xcc06  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xcc0b  ldstr    aSlakpiinstance// "slakpiinstance"
0xcc10  ldc.i4.1
0xcc11  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> AttributeRelationUtil::RetrieveLinkedEntityList(string fromEntityName, string toEntityName, bool includeReferencesFrom)
0xcc16  stloc.2
0xcc17  ldloc.2
0xcc18  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__17_0
0xcc1d  dup
0xcc1e  brtrue.s loc_CC37
0xcc20  pop
0xcc21  ldsfld   class <>c <>c::<>9
0xcc26  ldftn    instance string <>c::<OnDataBoundReady>b__17_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> Item)
0xcc2c  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0xcc31  dup
0xcc32  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__17_0
0xcc37  call     T0x2B000001
0xcc3c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0xcc41  stloc.s  4
0xcc43  br.s     loc_CC62
0xcc45  ldloc.s  4
0xcc47  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0xcc4c  stloc.s  5
0xcc4e  ldloc.0
0xcc4f  ldloca.s 5
0xcc51  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0xcc56  ldloca.s 5
0xcc58  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0xcc5d  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::AddItem(string, string)
0xcc62  ldloc.s  4
0xcc64  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcc69  brtrue.s loc_CC45
0xcc6b  leave.s  loc_CC79
0xcc6d  ldloc.s  4
0xcc6f  brfalse.s loc_CC78
0xcc71  ldloc.s  4
0xcc73  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcc78  endfinally
0xcc79  ldarg.0
0xcc7a  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xcc7f  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0xcc84  ldc.i4.1
0xcc85  bne.un.s loc_CC93
0xcc87  ldloc.0
0xcc88  ldarg.0
0xcc89  call     instance object Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::GetDefaultRealtedField()
0xcc8e  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xcc93  ret
```
