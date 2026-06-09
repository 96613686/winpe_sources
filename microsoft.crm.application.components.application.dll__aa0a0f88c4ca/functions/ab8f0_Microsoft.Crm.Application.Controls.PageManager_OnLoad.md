# Microsoft.Crm.Application.Controls.PageManager::OnLoad

- ea: `0xab8f0`
- end: `0xab9ee`
- name: `Microsoft.Crm.Application.Controls.PageManager::OnLoad`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x6a00`
- `0x8d750`
- `0x8dbb0`
- `0xa99b0`
- `0xab8f0`
- `0xe00a0`
- `0xf3cd0`
- `0xf3ce0`

## string_xrefs

- `0xab959`: `Microsoft.Crm.Service.Application.Pages`
- `0xab95e`: `ServicePageHandlerFactory`
- `0xab96a`: `Microsoft.Crm.Common.Application.Pages`
- `0xab96f`: `CommonPageHandlerFactory`

## pseudocode

```c

```

## disassembly

```asm
0xab8f0  ldarg.0
0xab8f1  ldarg.1
0xab8f2  call     instance void Microsoft.Crm.Application.Controls.AppPage::OnLoad(class [mscorlib]System.EventArgs e)
0xab8f7  ldarg.0
0xab8f8  call     instance bool Microsoft.Crm.Application.Controls.AppPage::get_PageHandlerEnabled()
0xab8fd  brfalse  loc_AB9ED
0xab902  ldstr    aMicrosoftCrmAp_184// "Microsoft.Crm.Application.Pages"
0xab907  stloc.0
0xab908  ldloc.0
0xab909  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xab90e  brtrue   loc_AB9D1
0xab913  ldsfld   class IsPageHandlerDelegate <>c::<>9__79_0
0xab918  dup
0xab919  brtrue.s loc_AB932
0xab91b  pop
0xab91c  ldsfld   class <>c <>c::<>9
0xab921  ldftn    instance bool <>c::<OnLoad>b__79_0(class [mscorlib]System.Type t)
0xab927  newobj   instance void IsPageHandlerDelegate::.ctor(object object, native int method)
0xab92c  dup
0xab92d  stsfld   class IsPageHandlerDelegate <>c::<>9__79_0
0xab932  stloc.1
0xab933  ldloc.0
0xab934  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0xab939  ldstr    aMicrosoftCrmSa// "Microsoft.Crm.Sales.Application.Pages"
0xab93e  ldstr    aSalespagehandl// "SalesPageHandlerFactory"
0xab943  call     class Microsoft.Crm.Application.Components.PageHandlers.IPageHandlerFactory Microsoft.Crm.Utility.HelpUtility::PageHandlerFactory(string assembyName, string typeName)
0xab948  stloc.2
0xab949  ldstr    aMicrosoftCrmMa// "Microsoft.Crm.Marketing.Application.Pag"...
0xab94e  ldstr    aMarketingpageh// "MarketingPageHandlerFactory"
0xab953  call     class Microsoft.Crm.Application.Components.PageHandlers.IPageHandlerFactory Microsoft.Crm.Utility.HelpUtility::PageHandlerFactory(string assembyName, string typeName)
0xab958  stloc.3
0xab959  ldstr    aMicrosoftCrmSe_8// "Microsoft.Crm.Service.Application.Pages"
0xab95e  ldstr    aServicepagehan// "ServicePageHandlerFactory"
0xab963  call     class Microsoft.Crm.Application.Components.PageHandlers.IPageHandlerFactory Microsoft.Crm.Utility.HelpUtility::PageHandlerFactory(string assembyName, string typeName)
0xab968  stloc.s  4
0xab96a  ldstr    aMicrosoftCrmCo// "Microsoft.Crm.Common.Application.Pages"
0xab96f  ldstr    aCommonpagehand// "CommonPageHandlerFactory"
0xab974  call     class Microsoft.Crm.Application.Components.PageHandlers.IPageHandlerFactory Microsoft.Crm.Utility.HelpUtility::PageHandlerFactory(string assembyName, string typeName)
0xab979  stloc.s  5
0xab97b  callvirt instance class [mscorlib]System.Type[] [mscorlib]System.Reflection.Assembly::GetTypes()
0xab980  stloc.s  6
0xab982  ldc.i4.0
0xab983  stloc.s  7
0xab985  br.s     loc_AB9C9
0xab987  ldloc.s  6
0xab989  ldloc.s  7
0xab98b  ldelem.ref
0xab98c  stloc.s  8
0xab98e  ldloc.1
0xab98f  ldloc.s  8
0xab991  callvirt instance bool IsPageHandlerDelegate::Invoke(class [mscorlib]System.Type t)
0xab996  brfalse.s loc_AB9C3
0xab998  ldloc.s  8
0xab99a  ldc.i4.4
0xab99b  newarr   [mscorlib]System.Object
0xab9a0  dup
0xab9a1  ldc.i4.0
0xab9a2  ldloc.2
0xab9a3  stelem.ref
0xab9a4  dup
0xab9a5  ldc.i4.1
0xab9a6  ldloc.3
0xab9a7  stelem.ref
0xab9a8  dup
0xab9a9  ldc.i4.2
0xab9aa  ldloc.s  4
0xab9ac  stelem.ref
0xab9ad  dup
0xab9ae  ldc.i4.3
0xab9af  ldloc.s  5
0xab9b1  stelem.ref
0xab9b2  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, object[])
0xab9b7  castclass Microsoft.Crm.Application.Components.PageHandlers.IPageHandlerFactory
0xab9bc  stsfld   class Microsoft.Crm.Application.Components.PageHandlers.IPageHandlerFactory Microsoft.Crm.Application.Controls.PageManager::_pageHandlerFactory
0xab9c1  br.s     loc_AB9D1
0xab9c3  ldloc.s  7
0xab9c5  ldc.i4.1
0xab9c6  add
0xab9c7  stloc.s  7
0xab9c9  ldloc.s  7
0xab9cb  ldloc.s  6
0xab9cd  ldlen
0xab9ce  conv.i4
0xab9cf  blt.s    loc_AB987
0xab9d1  ldarg.0
0xab9d2  ldsfld   class Microsoft.Crm.Application.Components.PageHandlers.IPageHandlerFactory Microsoft.Crm.Application.Controls.PageManager::_pageHandlerFactory
0xab9d7  ldarg.0
0xab9d8  ldfld    valuetype Microsoft.Crm.Application.Components.PageHandlers.HandlerPageType Microsoft.Crm.Application.Controls.PageManager::pageType
0xab9dd  ldarg.0
0xab9de  call     instance int32 Microsoft.Crm.Application.Controls.PageManager::get_HandlerEntityTypeCode()
0xab9e3  callvirt instance class Microsoft.Crm.Application.Components.PageHandlers.PageHandler Microsoft.Crm.Application.Components.PageHandlers.IPageHandlerFactory::RetrievePageHandler(valuetype Microsoft.Crm.Application.Components.PageHandlers.HandlerPageType pageType, int32 entityTypeCode)
0xab9e8  stfld    class Microsoft.Crm.Application.Components.PageHandlers.PageHandler Microsoft.Crm.Application.Controls.PageManager::crmPageHandler
0xab9ed  ret
```
