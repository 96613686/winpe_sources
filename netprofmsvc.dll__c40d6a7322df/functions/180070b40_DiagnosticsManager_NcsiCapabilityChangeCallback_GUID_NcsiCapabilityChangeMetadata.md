# DiagnosticsManager::NcsiCapabilityChangeCallback(_GUID,_NcsiCapabilityChangeMetadata)

- ea: `0x180070b40`
- end: `0x180070caf`
- name: `?NcsiCapabilityChangeCallback@DiagnosticsManager@@CAXU_GUID@@U_NcsiCapabilityChangeMetadata@@@Z`
- size: `367`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800097ec`
- `0x180009990`
- `0x18000e190`
- `0x180070b40`
- `0x1800713b8`
- `0x1800a88a0`
- `0x18010f828`
- `0x18010f8f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070c2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070c5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070c2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070c5f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180070c74`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180070c74`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180070bc7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180070bc7`

## string_xrefs

- `0x180070b92`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DiagnosticsManager::NcsiCapabilityChangeCallback(__int128 *a1, __int64 *a2)
{
  std::_Ref_count_base *v4; // rbx
  const char *v5; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-68h] BYREF
  std::_Ref_count_base *v7; // [rsp+28h] [rbp-60h] BYREF
  __int128 v8; // [rsp+30h] [rbp-58h]
  __int64 v9; // [rsp+40h] [rbp-48h]
  int v10; // [rsp+48h] [rbp-40h]
  LARGE_INTEGER v11; // [rsp+50h] [rbp-38h]
  LARGE_INTEGER PerformanceCount; // [rsp+58h] [rbp-30h] BYREF
  std::_Ref_count_base *v13[2]; // [rsp+60h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *(_OWORD *)v13 = 0;
  std::weak_ptr<DiagnosticsManager>::lock(a1, v13);
  v4 = v13[0];
  if ( v13[0] )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v7 = v4;
    v8 = *a1;
    v9 = *a2;
    v10 = *((_DWORD *)a2 + 2);
    v11 = PerformanceCount;
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
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__DiagnosticsManager::NcsiCapabilityChangeCallback_::_3_::_lambda_1___(
            (char *)v4 + 1408,
            &v7);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__DiagnosticsManager::NcsiCapabilityChangeCallback_::_3_::_lambda_1___(
            (char *)v4 + 1488,
            &v7);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        _InterlockedIncrement64((volatile signed __int64 *)v4 + 174);
        SubmitThreadpoolWork(*((PTP_WORK *)v4 + 173));
      }
      if ( v13[1] )
        std::_Ref_count_base::_Decref(v13[1]);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xB2,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
        v5);
    }
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
      (const char *)0x45B,
      (unsigned int)lpCriticalSection);
    if ( v13[1] )
      std::_Ref_count_base::_Decref(v13[1]);
  }
}

```

## disassembly

```asm
0x180070b40  mov     [rsp+arg_0], rbx
0x180070b45  mov     [rsp+arg_8], rsi
0x180070b4a  push    rdi
0x180070b4b  sub     rsp, 80h
0x180070b52  mov     rax, cs:__security_cookie
0x180070b59  xor     rax, rsp
0x180070b5c  mov     [rsp+88h+var_18], rax
0x180070b61  mov     rdi, rdx
0x180070b64  mov     rsi, rcx
0x180070b67  xorps   xmm0, xmm0
0x180070b6a  movups  xmmword ptr [rsp+88h+var_28], xmm0
0x180070b6f  lea     rdx, [rsp+88h+var_28]
0x180070b74  call    ?lock@?$weak_ptr@VDiagnosticsManager@@@std@@QEBA?AV?$shared_ptr@VDiagnosticsManager@@@2@XZ; std::weak_ptr<DiagnosticsManager>::lock(void)
0x180070b79  nop
0x180070b7a  mov     rbx, [rsp+88h+var_28]
0x180070b7f  test    rbx, rbx
0x180070b82  jnz     short loc_180070BB9
0x180070b84  mov     rcx, [rsp+88h]; this
0x180070b8c  mov     r9d, 45Bh; char *
0x180070b92  lea     r8, aOnecoreNetNetp_9; "onecore\\net\\netprofiles\\service\\src"...
0x180070b99  mov     edx, 92h; void *
0x180070b9e  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180070ba3  nop
0x180070ba4  mov     rcx, [rsp+88h+var_28+8]; this
0x180070ba9  test    rcx, rcx
0x180070bac  jz      short loc_180070BB4
0x180070bae  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070bb3  nop
0x180070bb4  jmp     loc_180070C8D
0x180070bb9  mov     qword ptr [rsp+88h+PerformanceCount], 0
0x180070bc2  lea     rcx, [rsp+88h+PerformanceCount]; lpPerformanceCount
0x180070bc7  call    cs:__imp_QueryPerformanceCounter
0x180070bcd  mov     [rsp+88h+var_60], rbx
0x180070bd2  movups  xmm0, xmmword ptr [rsi]
0x180070bd5  movdqu  [rsp+88h+var_58], xmm0
0x180070bdb  movsd   xmm1, qword ptr [rdi]
0x180070bdf  movsd   [rsp+88h+var_48], xmm1
0x180070be5  mov     eax, [rdi+8]
0x180070be8  mov     [rsp+88h+var_40], eax
0x180070bec  mov     eax, dword ptr [rsp+88h+PerformanceCount]
0x180070bf0  mov     dword ptr [rsp+88h+var_38], eax
0x180070bf4  mov     eax, dword ptr [rsp+88h+PerformanceCount+4]
0x180070bf8  mov     dword ptr [rsp+88h+var_38+4], eax
0x180070bfc  mov     [rsp+88h+lpCriticalSection], 0
0x180070c05  lea     rdx, [rbx+4F0h]
0x180070c0c  lea     rcx, [rsp+88h+lpCriticalSection]
0x180070c11  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180070c16  nop
0x180070c17  lea     rcx, [rbx+580h]
0x180070c1e  cmp     byte ptr [rcx+78h], 0
0x180070c22  jz      short loc_180070C36
0x180070c24  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x180070c29  test    rcx, rcx
0x180070c2c  jz      short loc_180070C7B
0x180070c2e  call    cs:__imp_LeaveCriticalSection
0x180070c34  jmp     short loc_180070C7B
0x180070c36  lea     rdx, [rsp+88h+var_60]
0x180070c3b  cmp     dword ptr [rbx+4E8h], 1
0x180070c42  jnz     short loc_180070C4B
0x180070c44  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__DiagnosticsManager__NcsiCapabilityChangeCallback____3____lambda_1___
0x180070c49  jmp     short loc_180070C55
0x180070c4b  add     rcx, 50h ; 'P'
0x180070c4f  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__DiagnosticsManager__NcsiCapabilityChangeCallback____3____lambda_1___
0x180070c54  nop
0x180070c55  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x180070c5a  test    rcx, rcx
0x180070c5d  jz      short loc_180070C65
0x180070c5f  call    cs:__imp_LeaveCriticalSection
0x180070c65  lock inc qword ptr [rbx+570h]
0x180070c6d  mov     rcx, [rbx+568h]; pwk
0x180070c74  call    cs:__imp_SubmitThreadpoolWork
0x180070c7a  nop
0x180070c7b  mov     rcx, [rsp+88h+var_28+8]; this
0x180070c80  test    rcx, rcx
0x180070c83  jz      short loc_180070C8B
0x180070c85  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070c8a  nop
0x180070c8b  jmp     short $+2
0x180070c8d  mov     rcx, [rsp+88h+var_18]
0x180070c92  xor     rcx, rsp; StackCookie
0x180070c95  call    __security_check_cookie
0x180070c9a  lea     r11, [rsp+88h+var_8]
0x180070ca2  mov     rbx, [r11+10h]
0x180070ca6  mov     rsi, [r11+18h]
0x180070caa  mov     rsp, r11
0x180070cad  pop     rdi
0x180070cae  retn
```
