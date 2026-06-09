# ThreadProcHelper::~ThreadProcHelper(void)

- ea: `0x18001b8c0`
- end: `0x18001b8ff`
- name: `??1ThreadProcHelper@@MEAA@XZ`
- size: `63`
- prototype: `void __fastcall(ThreadProcHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180017240`

## callees

- `0x18001b908`
- `0x18001b934`
- `0x18001b960`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001b8dc`
- `KERNEL32!DeleteCriticalSection` at `0x18001b8dc`

## pseudocode

```c
void __fastcall ThreadProcHelper::~ThreadProcHelper(ThreadProcHelper *this)
{
  *(_QWORD *)this = &ThreadProcHelper::`vftable';
  ThreadProcHelper::Shutdown(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 40);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 24);
}

```

## disassembly

```asm
0x18001b8c0  push    rbx
0x18001b8c2  sub     rsp, 20h
0x18001b8c6  lea     rax, ??_7ThreadProcHelper@@6B@; const ThreadProcHelper::`vftable'
0x18001b8cd  mov     rbx, rcx
0x18001b8d0  mov     [rcx], rax
0x18001b8d3  call    ?Shutdown@ThreadProcHelper@@UEAAJXZ; ThreadProcHelper::Shutdown(void)
0x18001b8d8  lea     rcx, [rbx+30h]; lpCriticalSection
0x18001b8dc  call    cs:__imp_DeleteCriticalSection
0x18001b8e3  nop     dword ptr [rax+rax+00h]
0x18001b8e8  lea     rcx, [rbx+28h]
0x18001b8ec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b8f1  lea     rcx, [rbx+18h]
0x18001b8f5  add     rsp, 20h
0x18001b8f9  pop     rbx
0x18001b8fa  jmp     ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
```
