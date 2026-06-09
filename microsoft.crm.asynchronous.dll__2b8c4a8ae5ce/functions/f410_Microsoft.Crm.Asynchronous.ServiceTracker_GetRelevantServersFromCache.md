# Microsoft.Crm.Asynchronous.ServiceTracker::GetRelevantServersFromCache

- ea: `0xf410`
- end: `0xf47b`
- name: `Microsoft.Crm.Asynchronous.ServiceTracker::GetRelevantServersFromCache`
- size: `107`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xf300`
- `0xf3e0`

## callees

- `0x7550`
- `0x75a0`
- `0xf370`
- `0xf410`

## pseudocode

```c

```

## disassembly

```asm
0xf410  ldarg.0
0xf411  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData> Microsoft.Crm.Asynchronous.ServiceTracker::get_Services()
0xf416  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>::get_Count()
0xf41b  ldarg.0
0xf41c  call     class Microsoft.Crm.Asynchronous.AsyncServerCache Microsoft.Crm.Asynchronous.AsyncServerCache::get_Instance()
0xf421  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData> Microsoft.Crm.Asynchronous.AsyncServerCache::get_Servers()
0xf426  ldarg.0
0xf427  ldftn    instance bool Microsoft.Crm.Asynchronous.ServiceTracker::<GetRelevantServersFromCache>b__11_0(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData s)
0xf42d  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData, bool>::.ctor(object, native int)
0xf432  call     T0x2B000011
0xf437  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData, string> <>c::<>9__11_1
0xf43c  dup
0xf43d  brtrue.s loc_F456
0xf43f  pop
0xf440  ldsfld   class <>c <>c::<>9
0xf445  ldftn    instance string <>c::<GetRelevantServersFromCache>b__11_1(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData s)
0xf44b  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData, string>::.ctor(object, native int)
0xf450  dup
0xf451  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData, string> <>c::<>9__11_1
0xf456  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xf45b  call     T0x2B00001E
0xf460  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xf465  stfld    class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData> Microsoft.Crm.Asynchronous.ServiceTracker::_services
0xf46a  ldarg.0
0xf46b  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData> Microsoft.Crm.Asynchronous.ServiceTracker::get_Services()
0xf470  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>::get_Count()
0xf475  ceq
0xf477  ldc.i4.0
0xf478  ceq
0xf47a  ret
```
