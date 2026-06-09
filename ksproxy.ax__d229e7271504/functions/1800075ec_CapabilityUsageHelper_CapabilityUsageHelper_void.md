# CapabilityUsageHelper::~CapabilityUsageHelper(void)

- ea: `0x1800075ec`
- end: `0x180007634`
- name: `??1CapabilityUsageHelper@@EEAA@XZ`
- size: `72`
- prototype: `void __fastcall(CapabilityUsageHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800075b0`

## callees

- `0x1800076b4`
- `0x18001b908`
- `0x18001b934`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007608`
- `KERNEL32!DeleteCriticalSection` at `0x180007608`

## pseudocode

```c
void __fastcall CapabilityUsageHelper::~CapabilityUsageHelper(CapabilityUsageHelper *this)
{
  *(_QWORD *)this = &CapabilityUsageHelper::`vftable';
  CapabilityUsageHelper::Stop(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 24);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 16);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x1800075ec  push    rbx
0x1800075ee  sub     rsp, 20h
0x1800075f2  lea     rax, ??_7CapabilityUsageHelper@@6B@; const CapabilityUsageHelper::`vftable'
0x1800075f9  mov     rbx, rcx
0x1800075fc  mov     [rcx], rax
0x1800075ff  call    ?Stop@CapabilityUsageHelper@@QEAAJXZ; CapabilityUsageHelper::Stop(void)
0x180007604  lea     rcx, [rbx+20h]; lpCriticalSection
0x180007608  call    cs:__imp_DeleteCriticalSection
0x18000760f  nop     dword ptr [rax+rax+00h]
0x180007614  lea     rcx, [rbx+18h]
0x180007618  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000761d  lea     rcx, [rbx+10h]
0x180007621  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007626  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18000762d  add     rsp, 20h
0x180007631  pop     rbx
0x180007632  retn
```
