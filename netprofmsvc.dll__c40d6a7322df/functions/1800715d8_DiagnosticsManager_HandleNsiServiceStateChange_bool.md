# DiagnosticsManager::HandleNsiServiceStateChange(bool)

- ea: `0x1800715d8`
- end: `0x18007171a`
- name: `?HandleNsiServiceStateChange@DiagnosticsManager@@SAX_N@Z`
- size: `322`
- prototype: `void __fastcall(bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18010b338`
- `0x18010b5b4`

## callees

- `0x1800097ec`
- `0x180009990`
- `0x18000e190`
- `0x1800713b8`
- `0x1800715d8`
- `0x1800a88a0`
- `0x18010ecb8`
- `0x18010ed7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800716a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800716d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800716a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800716d4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800716e9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800716e9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180071651`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180071651`

## string_xrefs

- `0x18007161c`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DiagnosticsManager::HandleNsiServiceStateChange(__int64 a1)
{
  char v1; // di
  std::_Ref_count_base *v2; // rbx
  const char *v3; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v5[2]; // [rsp+28h] [rbp-40h] BYREF
  char v6; // [rsp+38h] [rbp-30h]
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-28h] BYREF
  std::_Ref_count_base *v8[2]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v1 = a1;
  *(_OWORD *)v8 = 0;
  std::weak_ptr<DiagnosticsManager>::lock(a1, v8);
  v2 = v8[0];
  if ( v8[0] )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v5[0] = v2;
    v5[1] = PerformanceCount.QuadPart;
    v6 = v1;
    lpCriticalSection = 0;
    wil::EnterCriticalSection(&lpCriticalSection, (char *)v2 + 1264);
    try
    {
      if ( *((_BYTE *)v2 + 1528) )
      {
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
      }
      else
      {
        if ( *((_DWORD *)v2 + 314) == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__DiagnosticsManager::HandleNsiServiceStateChange_::_3_::_lambda_1___(
            (char *)v2 + 1408,
            v5);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__DiagnosticsManager::HandleNsiServiceStateChange_::_3_::_lambda_1___(
            (char *)v2 + 1488,
            v5);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        _InterlockedIncrement64((volatile signed __int64 *)v2 + 174);
        SubmitThreadpoolWork(*((PTP_WORK *)v2 + 173));
      }
      if ( v8[1] )
        std::_Ref_count_base::_Decref(v8[1]);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x266,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
        v3);
    }
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x247,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
      (const char *)0x45B,
      (unsigned int)lpCriticalSection);
    if ( v8[1] )
      std::_Ref_count_base::_Decref(v8[1]);
  }
}

```

## disassembly

```asm
0x1800715d8  mov     [rsp+arg_0], rbx
0x1800715dd  push    rdi
0x1800715de  sub     rsp, 60h
0x1800715e2  mov     rax, cs:__security_cookie
0x1800715e9  xor     rax, rsp
0x1800715ec  mov     [rsp+68h+var_10], rax
0x1800715f1  mov     dil, cl
0x1800715f4  xorps   xmm0, xmm0
0x1800715f7  movups  xmmword ptr [rsp+68h+var_20], xmm0
0x1800715fc  lea     rdx, [rsp+68h+var_20]
0x180071601  call    ?lock@?$weak_ptr@VDiagnosticsManager@@@std@@QEBA?AV?$shared_ptr@VDiagnosticsManager@@@2@XZ; std::weak_ptr<DiagnosticsManager>::lock(void)
0x180071606  nop
0x180071607  mov     rbx, [rsp+68h+var_20]
0x18007160c  test    rbx, rbx
0x18007160f  jnz     short loc_180071643
0x180071611  mov     rcx, [rsp+68h]; this
0x180071616  mov     r9d, 45Bh; char *
0x18007161c  lea     r8, aOnecoreNetNetp_9; "onecore\\net\\netprofiles\\service\\src"...
0x180071623  mov     edx, 247h; void *
0x180071628  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18007162d  nop
0x18007162e  mov     rcx, [rsp+68h+var_20+8]; this
0x180071633  test    rcx, rcx
0x180071636  jz      short loc_18007163E
0x180071638  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007163d  nop
0x18007163e  jmp     loc_180071702
0x180071643  mov     qword ptr [rsp+68h+PerformanceCount], 0
0x18007164c  lea     rcx, [rsp+68h+PerformanceCount]; lpPerformanceCount
0x180071651  call    cs:__imp_QueryPerformanceCounter
0x180071657  mov     [rsp+68h+var_40], rbx
0x18007165c  mov     eax, dword ptr [rsp+68h+PerformanceCount]
0x180071660  mov     dword ptr [rsp+68h+var_38], eax
0x180071664  mov     eax, dword ptr [rsp+68h+PerformanceCount+4]
0x180071668  mov     dword ptr [rsp+68h+var_38+4], eax
0x18007166c  mov     [rsp+68h+var_30], dil
0x180071671  mov     [rsp+68h+lpCriticalSection], 0
0x18007167a  lea     rdx, [rbx+4F0h]
0x180071681  lea     rcx, [rsp+68h+lpCriticalSection]
0x180071686  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18007168b  nop
0x18007168c  lea     rcx, [rbx+580h]
0x180071693  cmp     byte ptr [rcx+78h], 0
0x180071697  jz      short loc_1800716AB
0x180071699  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x18007169e  test    rcx, rcx
0x1800716a1  jz      short loc_1800716F0
0x1800716a3  call    cs:__imp_LeaveCriticalSection
0x1800716a9  jmp     short loc_1800716F0
0x1800716ab  lea     rdx, [rsp+68h+var_40]
0x1800716b0  cmp     dword ptr [rbx+4E8h], 1
0x1800716b7  jnz     short loc_1800716C0
0x1800716b9  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__DiagnosticsManager__HandleNsiServiceStateChange____3____lambda_1___
0x1800716be  jmp     short loc_1800716CA
0x1800716c0  add     rcx, 50h ; 'P'
0x1800716c4  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__DiagnosticsManager__HandleNsiServiceStateChange____3____lambda_1___
0x1800716c9  nop
0x1800716ca  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x1800716cf  test    rcx, rcx
0x1800716d2  jz      short loc_1800716DA
0x1800716d4  call    cs:__imp_LeaveCriticalSection
0x1800716da  lock inc qword ptr [rbx+570h]
0x1800716e2  mov     rcx, [rbx+568h]; pwk
0x1800716e9  call    cs:__imp_SubmitThreadpoolWork
0x1800716ef  nop
0x1800716f0  mov     rcx, [rsp+68h+var_20+8]; this
0x1800716f5  test    rcx, rcx
0x1800716f8  jz      short loc_180071700
0x1800716fa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800716ff  nop
0x180071700  jmp     short $+2
0x180071702  mov     rcx, [rsp+68h+var_10]
0x180071707  xor     rcx, rsp; StackCookie
0x18007170a  call    __security_check_cookie
0x18007170f  mov     rbx, [rsp+68h+arg_0]
0x180071714  add     rsp, 60h
0x180071718  pop     rdi
0x180071719  retn
```
