# Microsoft.Crm.Common.Application.Commands.ApplicationCommand::ApplyEmailTemplate

- ea: `0x2420`
- end: `0x24e2`
- name: `Microsoft.Crm.Common.Application.Commands.ApplicationCommand::ApplyEmailTemplate`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2420`
- `0x2fd0`

## string_xrefs

- `0x2457`: `SDKEmailTemplateHTMLLineBreak`

## pseudocode

```c

```

## disassembly

```asm
0x2420  ldsfld   string [mscorlib]System.String::Empty
0x2425  stloc.0
0x2426  ldarg.0
0x2427  ldarg.1
0x2428  ldarg.2
0x2429  ldarg.3
0x242a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Common.Application.Platform.DataSourceCommon::InstantiateTemplate(valuetype [mscorlib]System.Guid templateId, valuetype [mscorlib]System.Guid objectId, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType objectType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x242f  stloc.1
0x2430  ldnull
0x2431  stloc.2
0x2432  ldloc.1
0x2433  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x2438  ldc.i4.0
0x2439  ble.s    loc_2443
0x243b  ldloc.1
0x243c  ldc.i4.0
0x243d  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x2442  stloc.2
0x2443  ldloc.2
0x2444  brfalse.s loc_2457
0x2446  ldloc.2
0x2447  ldstr    aDescription// "description"
0x244c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2451  castclass [mscorlib]System.String
0x2456  stloc.0
0x2457  ldstr    aSdkemailtempla// "SDKEmailTemplateHTMLLineBreak"
0x245c  ldc.i4.0
0x245d  box      [mscorlib]System.Int32
0x2462  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x2467  unbox.any [mscorlib]System.Int32
0x246c  brtrue.s loc_24BE
0x246e  ldloc.0
0x246f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2474  brtrue.s loc_24BE
0x2476  ldloc.0
0x2477  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x247c  ldstr    a1310// "&#13;&#10;"
0x2481  ldstr    aBr// "<br>"
0x2486  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Replace(string, string)
0x248b  ldstr    a1013// "&#10;&#13;"
0x2490  ldstr    aBr// "<br>"
0x2495  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Replace(string, string)
0x249a  ldstr    a13// "&#13;"
0x249f  ldstr    aBr// "<br>"
0x24a4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Replace(string, string)
0x24a9  ldstr    a10// "&#10;"
0x24ae  ldstr    aBr// "<br>"
0x24b3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Replace(string, string)
0x24b8  callvirt instance string [mscorlib]System.Object::ToString()
0x24bd  stloc.0
0x24be  ldloc.0
0x24bf  call     string [Microsoft.Crm.SafeHtml]Microsoft.Crm.SafeHtml::GetSafeHtml(string)
0x24c4  stloc.0
0x24c5  ldloc.2
0x24c6  brtrue.s loc_24D4
0x24c8  ldstr    aEmail// "email"
0x24cd  ldarg.3
0x24ce  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24d3  stloc.2
0x24d4  ldloc.2
0x24d5  ldstr    aDescription// "description"
0x24da  ldloc.0
0x24db  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x24e0  ldloc.2
0x24e1  ret
```
