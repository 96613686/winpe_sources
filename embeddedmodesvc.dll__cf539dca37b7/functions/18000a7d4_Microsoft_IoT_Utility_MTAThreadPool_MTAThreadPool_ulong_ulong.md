# Microsoft::IoT::Utility::MTAThreadPool::MTAThreadPool(ulong,ulong)

- ea: `0x18000a7d4`
- end: `0x18000a8c3`
- name: `??0MTAThreadPool@Utility@IoT@Microsoft@@QEAA@KK@Z`
- size: `239`
- prototype: `Microsoft::IoT::Utility::MTAThreadPool *__fastcall(Microsoft::IoT::Utility::MTAThreadPool *this, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009f6c`

## callees

- `0x18000a658`
- `0x18000a730`
- `0x18000a7d4`
- `0x18000c26c`
- `0x18000c710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a83c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a860`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a880`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a83c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a860`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a880`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000a80f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000a80f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a821`

## pseudocode

```c
Microsoft::IoT::Utility::MTAThreadPool *__fastcall Microsoft::IoT::Utility::MTAThreadPool::MTAThreadPool(
        Microsoft::IoT::Utility::MTAThreadPool *this,
        int a2,
        int a3)
{
  void *v6; // rdx
  HANDLE Event; // rdi
  unsigned int v8; // r8d
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  Event = CreateEventExW(0, 0, 3u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v6, v8, v9);
  GetLastError();
  _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
    this,
    Event);
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 16), 0, 0);
  std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>((_QWORD *)this + 7);
  std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>((_QWORD *)this + 10);
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 104), 0, 0);
  std::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>,std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>>((_QWORD *)this + 18);
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 184), 0, 0);
  std::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>,std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>>((_QWORD *)this + 28);
  *((_DWORD *)this + 66) = a2;
  *((_DWORD *)this + 67) = a3;
  *((_WORD *)this + 136) = 0;
  return this;
}

```

## disassembly

```asm
0x18000a7d4  mov     [rsp+arg_8], rbx
0x18000a7d9  mov     [rsp+arg_0], rcx
0x18000a7de  push    rbp
0x18000a7df  push    rsi
0x18000a7e0  push    rdi
0x18000a7e1  sub     rsp, 20h
0x18000a7e5  mov     esi, r8d
0x18000a7e8  mov     ebp, edx
0x18000a7ea  mov     rbx, rcx
0x18000a7ed  mov     [rsp+38h+arg_18], rcx
0x18000a7f2  mov     qword ptr [rcx], 0
0x18000a7f9  mov     qword ptr [rcx+8], 0
0x18000a801  xor     edx, edx; lpName
0x18000a803  xor     ecx, ecx; lpEventAttributes
0x18000a805  mov     r9d, 1F0003h; dwDesiredAccess
0x18000a80b  lea     r8d, [rdx+3]; dwFlags
0x18000a80f  call    cs:__imp_CreateEventExW
0x18000a815  mov     rdi, rax
0x18000a818  test    rax, rax
0x18000a81b  jz      loc_18000A8B8
0x18000a821  call    cs:__imp_GetLastError
0x18000a827  mov     rdx, rdi
0x18000a82a  mov     rcx, rbx
0x18000a82d  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a832  nop
0x18000a833  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000a837  xor     r8d, r8d; Flags
0x18000a83a  xor     edx, edx; dwSpinCount
0x18000a83c  call    cs:__imp_InitializeCriticalSectionEx
0x18000a842  nop
0x18000a843  lea     rcx, [rbx+38h]
0x18000a847  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x18000a84c  nop
0x18000a84d  lea     rcx, [rbx+50h]
0x18000a851  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x18000a856  nop
0x18000a857  lea     rcx, [rbx+68h]; lpCriticalSection
0x18000a85b  xor     r8d, r8d; Flags
0x18000a85e  xor     edx, edx; dwSpinCount
0x18000a860  call    cs:__imp_InitializeCriticalSectionEx
0x18000a866  nop
0x18000a867  lea     rcx, [rbx+90h]
0x18000a86e  call    ??0?$queue@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@@std@@QEAA@XZ; std::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>,std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>>(void)
0x18000a873  nop
0x18000a874  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x18000a87b  xor     r8d, r8d; Flags
0x18000a87e  xor     edx, edx; dwSpinCount
0x18000a880  call    cs:__imp_InitializeCriticalSectionEx
0x18000a886  nop
0x18000a887  lea     rcx, [rbx+0E0h]
0x18000a88e  call    ??0?$queue@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@@std@@QEAA@XZ; std::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>,std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>>(void)
0x18000a893  mov     [rbx+108h], ebp
0x18000a899  mov     [rbx+10Ch], esi
0x18000a89f  mov     word ptr [rbx+110h], 0
0x18000a8a8  mov     rax, rbx
0x18000a8ab  mov     rbx, [rsp+38h+arg_8]
0x18000a8b0  add     rsp, 20h
0x18000a8b4  pop     rdi
0x18000a8b5  pop     rsi
0x18000a8b6  pop     rbp
0x18000a8b7  retn
0x18000a8b8  mov     rcx, [rsp+38h]; this
0x18000a8bd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
