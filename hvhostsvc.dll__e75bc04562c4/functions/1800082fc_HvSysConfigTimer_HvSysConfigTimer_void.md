# HvSysConfigTimer::~HvSysConfigTimer(void)

- ea: `0x1800082fc`
- end: `0x180008324`
- name: `??1HvSysConfigTimer@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(HvSysConfigTimer *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180009770`

## callees

- `0x180007064`
- `0x180008234`
- `0x18000828c`

## pseudocode

```c
void __fastcall HvSysConfigTimer::~HvSysConfigTimer(HvSysConfigTimer *this)
{
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((void **)this + 2);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>((__int64 *)this + 1);
  std::unique_ptr<HvServiceUtil>::~unique_ptr<HvServiceUtil>(this);
}

```

## disassembly

```asm
0x1800082fc  push    rbx
0x1800082fe  sub     rsp, 20h
0x180008302  mov     rbx, rcx
0x180008305  add     rcx, 10h
0x180008309  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000830e  lea     rcx, [rbx+8]
0x180008312  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x180008317  mov     rcx, rbx
0x18000831a  add     rsp, 20h
0x18000831e  pop     rbx
0x18000831f  jmp     ??1?$unique_ptr@VHvServiceUtil@@U?$default_delete@VHvServiceUtil@@@std@@@std@@QEAA@XZ; std::unique_ptr<HvServiceUtil>::~unique_ptr<HvServiceUtil>(void)
```
