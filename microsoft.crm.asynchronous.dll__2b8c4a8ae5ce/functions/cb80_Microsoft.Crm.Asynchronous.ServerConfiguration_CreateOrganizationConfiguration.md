# Microsoft.Crm.Asynchronous.ServerConfiguration::CreateOrganizationConfiguration

- ea: `0xcb80`
- end: `0xcc30`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::CreateOrganizationConfiguration`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x17ad0`

## callees

- `0xba90`
- `0xbac0`
- `0xcb80`

## pseudocode

```c

```

## disassembly

```asm
0xcb80  ldarg.1
0xcb81  ldstr    aState// "State"
0xcb86  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xcb8b  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0xcb90  stloc.0
0xcb91  ldarg.2
0xcb92  ldc.i4   0x40000002
0xcb97  and
0xcb98  brtrue.s loc_CB9C
0xcb9a  ldc.i4.0
0xcb9b  stloc.0
0xcb9c  ldarg.1
0xcb9d  ldstr    aIsdisabledfora// "IsDisabledForAsyncProcessing"
0xcba2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xcba7  stloc.1
0xcba8  ldloc.1
0xcba9  brfalse.s loc_CBB3
0xcbab  ldloc.1
0xcbac  unbox.any [mscorlib]System.Boolean
0xcbb1  br.s     loc_CBB4
0xcbb3  ldc.i4.0
0xcbb4  brfalse.s loc_CBB8
0xcbb6  ldc.i4.0
0xcbb7  stloc.0
0xcbb8  ldarg.1
0xcbb9  ldstr    aId_0// "Id"
0xcbbe  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xcbc3  unbox.any [mscorlib]System.Guid
0xcbc8  ldloc.0
0xcbc9  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xcbce  newobj   instance void Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::.ctor(valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState organizationState, class [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService locatorService)
0xcbd3  stloc.2
0xcbd4  ldarg.3
0xcbd5  ldloc.2
0xcbd6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::get_OrganizationId()
0xcbdb  ldloc.2
0xcbdc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::Add(var<u1>, !!T0)
0xcbe1  ldloc.0
0xcbe2  ldc.i4.1
0xcbe3  beq.s    loc_CC2F
0xcbe5  ldarg.0
0xcbe6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.ServerConfiguration::_organizations
0xcbeb  ldloc.2
0xcbec  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::get_OrganizationId()
0xcbf1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::ContainsKey(var<u1>)
0xcbf6  brfalse.s loc_CC2F
0xcbf8  ldarg.0
0xcbf9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.ServerConfiguration::_organizations
0xcbfe  ldloc.2
0xcbff  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::get_OrganizationId()
0xcc04  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Item(void)
0xcc09  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationState()
0xcc0e  ldloc.0
0xcc0f  beq.s    loc_CC2F
0xcc11  ldarg.s  4
0xcc13  ldloc.2
0xcc14  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::get_OrganizationId()
0xcc19  ldarg.0
0xcc1a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.ServerConfiguration::_organizations
0xcc1f  ldloc.2
0xcc20  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::get_OrganizationId()
0xcc25  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Item(void)
0xcc2a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::Add(var<u1>, !!T0)
0xcc2f  ret
```
