# DiagnosticsManager::HandleWlanServiceStateChange(bool)

- ea: `0x180071f44`
- end: `0x180072086`
- name: `?HandleWlanServiceStateChange@DiagnosticsManager@@SAX_N@Z`
- size: `322`
- prototype: `void __fastcall(bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801046b4`
- `0x1801048c0`

## callees

- `0x1800097ec`
- `0x180009990`
- `0x18000e190`
- `0x1800713b8`
- `0x180071f44`
- `0x1800a88a0`
- `0x18010f55c`
- `0x18010f620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007200f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072040`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007200f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072040`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180072055`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180072055`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180071fbd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180071fbd`

## string_xrefs

- `0x180071f88`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DiagnosticsManager::HandleWlanServiceStateChange(__int64 a1)
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
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__DiagnosticsManager::HandleWlanServiceStateChange_::_3_::_lambda_1___(
            (char *)v2 + 1408,
            v5);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__DiagnosticsManager::HandleWlanServiceStateChange_::_3_::_lambda_1___(
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
        (void *)0x3FA,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
        v3);
    }
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x3DA,
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
0x180071f44  mov     [rsp+arg_0], rbx
0x180071f49  push    rdi
0x180071f4a  sub     rsp, 60h
0x180071f4e  mov     rax, cs:__security_cookie
0x180071f55  xor     rax, rsp
0x180071f58  mov     [rsp+68h+var_10], rax
0x180071f5d  mov     dil, cl
0x180071f60  xorps   xmm0, xmm0
0x180071f63  movups  xmmword ptr [rsp+68h+var_20], xmm0
0x180071f68  lea     rdx, [rsp+68h+var_20]
0x180071f6d  call    ?lock@?$weak_ptr@VDiagnosticsManager@@@std@@QEBA?AV?$shared_ptr@VDiagnosticsManager@@@2@XZ; std::weak_ptr<DiagnosticsManager>::lock(void)
0x180071f72  nop
0x180071f73  mov     rbx, [rsp+68h+var_20]
0x180071f78  test    rbx, rbx
0x180071f7b  jnz     short loc_180071FAF
0x180071f7d  mov     rcx, [rsp+68h]; this
0x180071f82  mov     r9d, 45Bh; char *
0x180071f88  lea     r8, aOnecoreNetNetp_9; "onecore\\net\\netprofiles\\service\\src"...
0x180071f8f  mov     edx, 3DAh; void *
0x180071f94  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180071f99  nop
0x180071f9a  mov     rcx, [rsp+68h+var_20+8]; this
0x180071f9f  test    rcx, rcx
0x180071fa2  jz      short loc_180071FAA
0x180071fa4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071fa9  nop
0x180071faa  jmp     loc_18007206E
0x180071faf  mov     qword ptr [rsp+68h+PerformanceCount], 0
0x180071fb8  lea     rcx, [rsp+68h+PerformanceCount]; lpPerformanceCount
0x180071fbd  call    cs:__imp_QueryPerformanceCounter
0x180071fc3  mov     [rsp+68h+var_40], rbx
0x180071fc8  mov     eax, dword ptr [rsp+68h+PerformanceCount]
0x180071fcc  mov     dword ptr [rsp+68h+var_38], eax
0x180071fd0  mov     eax, dword ptr [rsp+68h+PerformanceCount+4]
0x180071fd4  mov     dword ptr [rsp+68h+var_38+4], eax
0x180071fd8  mov     [rsp+68h+var_30], dil
0x180071fdd  mov     [rsp+68h+lpCriticalSection], 0
0x180071fe6  lea     rdx, [rbx+4F0h]
0x180071fed  lea     rcx, [rsp+68h+lpCriticalSection]
0x180071ff2  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180071ff7  nop
0x180071ff8  lea     rcx, [rbx+580h]
0x180071fff  cmp     byte ptr [rcx+78h], 0
0x180072003  jz      short loc_180072017
0x180072005  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x18007200a  test    rcx, rcx
0x18007200d  jz      short loc_18007205C
0x18007200f  call    cs:__imp_LeaveCriticalSection
0x180072015  jmp     short loc_18007205C
0x180072017  lea     rdx, [rsp+68h+var_40]
0x18007201c  cmp     dword ptr [rbx+4E8h], 1
0x180072023  jnz     short loc_18007202C
0x180072025  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__DiagnosticsManager__HandleWlanServiceStateChange____3____lambda_1___
0x18007202a  jmp     short loc_180072036
0x18007202c  add     rcx, 50h ; 'P'
0x180072030  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__DiagnosticsManager__HandleWlanServiceStateChange____3____lambda_1___
0x180072035  nop
0x180072036  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x18007203b  test    rcx, rcx
0x18007203e  jz      short loc_180072046
0x180072040  call    cs:__imp_LeaveCriticalSection
0x180072046  lock inc qword ptr [rbx+570h]
0x18007204e  mov     rcx, [rbx+568h]; pwk
0x180072055  call    cs:__imp_SubmitThreadpoolWork
0x18007205b  nop
0x18007205c  mov     rcx, [rsp+68h+var_20+8]; this
0x180072061  test    rcx, rcx
0x180072064  jz      short loc_18007206C
0x180072066  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007206b  nop
0x18007206c  jmp     short $+2
0x18007206e  mov     rcx, [rsp+68h+var_10]
0x180072073  xor     rcx, rsp; StackCookie
0x180072076  call    __security_check_cookie
0x18007207b  mov     rbx, [rsp+68h+arg_0]
0x180072080  add     rsp, 60h
0x180072084  pop     rdi
0x180072085  retn
```
