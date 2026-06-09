# Microsoft::IoT::Utility::MTAThread::~MTAThread(void)

- ea: `0x18000d480`
- end: `0x18000d501`
- name: `??1MTAThread@Utility@IoT@Microsoft@@UEAA@XZ`
- size: `129`
- prototype: `void __fastcall(Microsoft::IoT::Utility::MTAThread *this, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d660`
- `0x18000d6a0`

## callees

- `0x1800044e0`
- `0x18000c3d4`
- `0x18000d3ec`
- `0x18000d480`
- `0x18000dcb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d4ae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d4ae`

## string_xrefs

- `0x18000d4bd`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`

## pseudocode

```c
void __fastcall Microsoft::IoT::Utility::MTAThread::~MTAThread(Microsoft::IoT::Utility::MTAThread *this, void *a2)
{
  const char *v3; // r9
  void *v4; // rdx
  void *v5; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &Microsoft::IoT::Utility::MTAThread::`vftable';
  wil::details::SetEvent(*((wil::details **)this + 1), a2);
  if ( WaitForSingleObject(*((HANDLE *)this + 3), 0x1388u) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
      v3);
  *((_QWORD *)this + 4) = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 24);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)this + 2,
    v4);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)this + 1,
    v5);
}

```

## disassembly

```asm
0x18000d480  mov     [rsp+arg_0], rbx
0x18000d485  mov     [rsp+arg_8], rsi
0x18000d48a  push    rdi
0x18000d48b  sub     rsp, 20h
0x18000d48f  lea     rax, ??_7MTAThread@Utility@IoT@Microsoft@@6B@; const Microsoft::IoT::Utility::MTAThread::`vftable'
0x18000d496  mov     rbx, rcx
0x18000d499  mov     [rcx], rax
0x18000d49c  mov     rcx, [rcx+8]; this
0x18000d4a0  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18000d4a5  mov     rcx, [rbx+18h]; hHandle
0x18000d4a9  mov     edx, 1388h; dwMilliseconds
0x18000d4ae  call    cs:__imp_WaitForSingleObject
0x18000d4b4  test    eax, eax
0x18000d4b6  jz      short loc_18000D4CF
0x18000d4b8  mov     rcx, [rsp+28h]; this
0x18000d4bd  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18000d4c4  mov     edx, 9Bh; void *
0x18000d4c9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000d4cf  lea     rcx, [rbx+18h]
0x18000d4d3  mov     qword ptr [rbx+20h], 0
0x18000d4db  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000d4e0  lea     rcx, [rbx+10h]
0x18000d4e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d4e9  lea     rcx, [rbx+8]
0x18000d4ed  mov     rbx, [rsp+28h+arg_0]
0x18000d4f2  mov     rsi, [rsp+28h+arg_8]
0x18000d4f7  add     rsp, 20h
0x18000d4fb  pop     rdi
0x18000d4fc  jmp     ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
```
