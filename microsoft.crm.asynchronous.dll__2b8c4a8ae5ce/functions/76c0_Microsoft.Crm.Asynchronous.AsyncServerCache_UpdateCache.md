# Microsoft.Crm.Asynchronous.AsyncServerCache::UpdateCache

- ea: `0x76c0`
- end: `0x7725`
- name: `Microsoft.Crm.Asynchronous.AsyncServerCache::UpdateCache`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7610`
- `0x7690`

## callees

- `0x76c0`

## pseudocode

```c

```

## disassembly

```asm
0x76c0  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerFilter::.ctor()
0x76c5  stloc.0
0x76c6  ldloc.0
0x76c7  ldarg.0
0x76c8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncServerCache::_scaleGroupId
0x76cd  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerFilter::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0x76d2  ldloc.0
0x76d3  ldc.i4.1
0x76d4  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerFilter::set_State(valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerState)
0x76d9  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmServerService::.ctor()
0x76de  ldloc.0
0x76df  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmServerService::RetrieveMultiple(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerFilter)
0x76e4  stloc.1
0x76e5  ldloc.1
0x76e6  brfalse.s loc_7719
0x76e8  ldarg.0
0x76e9  ldloc.1
0x76ea  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData, bool> <>c::<>9__12_0
0x76ef  dup
0x76f0  brtrue.s loc_7709
0x76f2  pop
0x76f3  ldsfld   class <>c <>c::<>9
0x76f8  ldftn    instance bool <>c::<UpdateCache>b__12_0(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData s)
0x76fe  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData, bool>::.ctor(object, native int)
0x7703  dup
0x7704  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData, bool> <>c::<>9__12_0
0x7709  call     T0x2B000011
0x770e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x7713  stfld    class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData> Microsoft.Crm.Asynchronous.AsyncServerCache::_asyncServerData
0x7718  ret
0x7719  ldarg.0
0x771a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>::.ctor()
0x771f  stfld    class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData> Microsoft.Crm.Asynchronous.AsyncServerCache::_asyncServerData
0x7724  ret
```
