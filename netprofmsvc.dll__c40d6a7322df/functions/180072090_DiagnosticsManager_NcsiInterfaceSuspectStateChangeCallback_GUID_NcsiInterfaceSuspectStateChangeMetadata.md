# DiagnosticsManager::NcsiInterfaceSuspectStateChangeCallback(_GUID,_NcsiInterfaceSuspectStateChangeMetadata)

- ea: `0x180072090`
- end: `0x1800721ea`
- name: `?NcsiInterfaceSuspectStateChangeCallback@DiagnosticsManager@@CAXU_GUID@@U_NcsiInterfaceSuspectStateChangeMetadata@@@Z`
- size: `346`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800097ec`
- `0x180009990`
- `0x18000e190`
- `0x1800713b8`
- `0x180072090`
- `0x1800a88a0`
- `0x18010fb38`
- `0x18010fc00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007216c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007219d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007216c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007219d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800721b2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800721b2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180072111`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180072111`

## string_xrefs

- `0x1800720dc`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DiagnosticsManager::NcsiInterfaceSuspectStateChangeCallback(__int128 *a1, __int64 a2)
{
  std::_Ref_count_base *v4; // rdi
  const char *v5; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-58h] BYREF
  std::_Ref_count_base *v7; // [rsp+28h] [rbp-50h] BYREF
  __int128 v8; // [rsp+30h] [rbp-48h]
  __int64 v9; // [rsp+40h] [rbp-38h]
  LARGE_INTEGER v10; // [rsp+48h] [rbp-30h]
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-28h] BYREF
  std::_Ref_count_base *v12[2]; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_OWORD *)v12 = 0;
  std::weak_ptr<DiagnosticsManager>::lock(a1, v12);
  v4 = v12[0];
  if ( v12[0] )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v7 = v4;
    v8 = *a1;
    v9 = a2;
    v10 = PerformanceCount;
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, (char *)v4 + 1264);
    try
    {
      if ( *((_BYTE *)v4 + 1528) )
      {
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
      }
      else
      {
        if ( *((_DWORD *)v4 + 314) == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__DiagnosticsManager::NcsiInterfaceSuspectStateChangeCallback_::_3_::_lambda_1___(
            (char *)v4 + 1408,
            &v7);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__DiagnosticsManager::NcsiInterfaceSuspectStateChangeCallback_::_3_::_lambda_1___(
            (char *)v4 + 1488,
            &v7);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        _InterlockedIncrement64((volatile signed __int64 *)v4 + 174);
        SubmitThreadpoolWork(*((PTP_WORK *)v4 + 173));
      }
      if ( v12[1] )
        std::_Ref_count_base::_Decref(v12[1]);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x129,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
        v5);
    }
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
      (const char *)0x45B,
      (unsigned int)lpCriticalSection);
    if ( v12[1] )
      std::_Ref_count_base::_Decref(v12[1]);
  }
}

```

## disassembly

```asm
0x180072090  mov     [rsp+arg_0], rbx
0x180072095  mov     [rsp+arg_10], rsi
0x18007209a  push    rdi
0x18007209b  sub     rsp, 70h
0x18007209f  mov     rax, cs:__security_cookie
0x1800720a6  xor     rax, rsp
0x1800720a9  mov     [rsp+78h+var_10], rax
0x1800720ae  mov     rbx, rdx
0x1800720b1  mov     rsi, rcx
0x1800720b4  xorps   xmm0, xmm0
0x1800720b7  movups  xmmword ptr [rsp+78h+var_20], xmm0
0x1800720bc  lea     rdx, [rsp+78h+var_20]
0x1800720c1  call    ?lock@?$weak_ptr@VDiagnosticsManager@@@std@@QEBA?AV?$shared_ptr@VDiagnosticsManager@@@2@XZ; std::weak_ptr<DiagnosticsManager>::lock(void)
0x1800720c6  nop
0x1800720c7  mov     rdi, [rsp+78h+var_20]
0x1800720cc  test    rdi, rdi
0x1800720cf  jnz     short loc_180072103
0x1800720d1  mov     rcx, [rsp+78h]; this
0x1800720d6  mov     r9d, 45Bh; char *
0x1800720dc  lea     r8, aOnecoreNetNetp_9; "onecore\\net\\netprofiles\\service\\src"...
0x1800720e3  mov     edx, 10Ch; void *
0x1800720e8  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800720ed  nop
0x1800720ee  mov     rcx, [rsp+78h+var_20+8]; this
0x1800720f3  test    rcx, rcx
0x1800720f6  jz      short loc_1800720FE
0x1800720f8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800720fd  nop
0x1800720fe  jmp     loc_1800721CB
0x180072103  mov     qword ptr [rsp+78h+PerformanceCount], 0
0x18007210c  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x180072111  call    cs:__imp_QueryPerformanceCounter
0x180072117  mov     [rsp+78h+var_50], rdi
0x18007211c  movups  xmm0, xmmword ptr [rsi]
0x18007211f  movdqu  [rsp+78h+var_48], xmm0
0x180072125  mov     [rsp+78h+var_38], rbx
0x18007212a  mov     eax, dword ptr [rsp+78h+PerformanceCount]
0x18007212e  mov     dword ptr [rsp+78h+var_30], eax
0x180072132  mov     eax, dword ptr [rsp+78h+PerformanceCount+4]
0x180072136  mov     dword ptr [rsp+78h+var_30+4], eax
0x18007213a  mov     [rsp+78h+lpCriticalSection], 0
0x180072143  lea     rdx, [rdi+4F0h]
0x18007214a  lea     rcx, [rsp+78h+lpCriticalSection]
0x18007214f  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180072154  nop
0x180072155  lea     rcx, [rdi+580h]
0x18007215c  cmp     byte ptr [rcx+78h], 0
0x180072160  jz      short loc_180072174
0x180072162  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x180072167  test    rcx, rcx
0x18007216a  jz      short loc_1800721B9
0x18007216c  call    cs:__imp_LeaveCriticalSection
0x180072172  jmp     short loc_1800721B9
0x180072174  lea     rdx, [rsp+78h+var_50]
0x180072179  cmp     dword ptr [rdi+4E8h], 1
0x180072180  jnz     short loc_180072189
0x180072182  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__DiagnosticsManager__NcsiInterfaceSuspectStateChangeCallback____3____lambda_1___
0x180072187  jmp     short loc_180072193
0x180072189  add     rcx, 50h ; 'P'
0x18007218d  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__DiagnosticsManager__NcsiInterfaceSuspectStateChangeCallback____3____lambda_1___
0x180072192  nop
0x180072193  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x180072198  test    rcx, rcx
0x18007219b  jz      short loc_1800721A3
0x18007219d  call    cs:__imp_LeaveCriticalSection
0x1800721a3  lock inc qword ptr [rdi+570h]
0x1800721ab  mov     rcx, [rdi+568h]; pwk
0x1800721b2  call    cs:__imp_SubmitThreadpoolWork
0x1800721b8  nop
0x1800721b9  mov     rcx, [rsp+78h+var_20+8]; this
0x1800721be  test    rcx, rcx
0x1800721c1  jz      short loc_1800721C9
0x1800721c3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800721c8  nop
0x1800721c9  jmp     short $+2
0x1800721cb  mov     rcx, [rsp+78h+var_10]
0x1800721d0  xor     rcx, rsp; StackCookie
0x1800721d3  call    __security_check_cookie
0x1800721d8  lea     r11, [rsp+78h+var_8]
0x1800721dd  mov     rbx, [r11+10h]
0x1800721e1  mov     rsi, [r11+20h]
0x1800721e5  mov     rsp, r11
0x1800721e8  pop     rdi
0x1800721e9  retn
```
