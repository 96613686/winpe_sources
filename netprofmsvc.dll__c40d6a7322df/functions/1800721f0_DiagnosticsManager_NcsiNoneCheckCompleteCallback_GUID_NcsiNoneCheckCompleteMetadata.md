# DiagnosticsManager::NcsiNoneCheckCompleteCallback(_GUID,_NcsiNoneCheckCompleteMetadata)

- ea: `0x1800721f0`
- end: `0x18007235d`
- name: `?NcsiNoneCheckCompleteCallback@DiagnosticsManager@@CAXU_GUID@@U_NcsiNoneCheckCompleteMetadata@@@Z`
- size: `365`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800097ec`
- `0x180009990`
- `0x18000e190`
- `0x1800713b8`
- `0x1800721f0`
- `0x1800a88a0`
- `0x18010fcc8`
- `0x18010fd6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800722dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007230d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800722dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007230d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180072322`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180072322`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180072277`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180072277`

## string_xrefs

- `0x180072242`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DiagnosticsManager::NcsiNoneCheckCompleteCallback(__int128 *a1, __int128 *a2)
{
  std::_Ref_count_base *v4; // rbx
  const char *v5; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-68h] BYREF
  std::_Ref_count_base *v7; // [rsp+28h] [rbp-60h] BYREF
  __int128 v8; // [rsp+30h] [rbp-58h]
  __int128 v9; // [rsp+40h] [rbp-48h]
  int v10; // [rsp+50h] [rbp-38h]
  LARGE_INTEGER v11; // [rsp+58h] [rbp-30h]
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp-28h] BYREF
  std::_Ref_count_base *v13[2]; // [rsp+68h] [rbp-20h] BYREF
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
    v10 = *((_DWORD *)a2 + 4);
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
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__DiagnosticsManager::NcsiNoneCheckCompleteCallback_::_3_::_lambda_1___(
            (char *)v4 + 1408,
            &v7);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__DiagnosticsManager::NcsiNoneCheckCompleteCallback_::_3_::_lambda_1___(
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
        (void *)0x104,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
        v5);
    }
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0xE4,
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
0x1800721f0  mov     [rsp+arg_0], rbx
0x1800721f5  mov     [rsp+arg_8], rsi
0x1800721fa  push    rdi
0x1800721fb  sub     rsp, 80h
0x180072202  mov     rax, cs:__security_cookie
0x180072209  xor     rax, rsp
0x18007220c  mov     [rsp+88h+var_10], rax
0x180072211  mov     rdi, rdx
0x180072214  mov     rsi, rcx
0x180072217  xorps   xmm0, xmm0
0x18007221a  movups  xmmword ptr [rsp+88h+var_20], xmm0
0x18007221f  lea     rdx, [rsp+88h+var_20]
0x180072224  call    ?lock@?$weak_ptr@VDiagnosticsManager@@@std@@QEBA?AV?$shared_ptr@VDiagnosticsManager@@@2@XZ; std::weak_ptr<DiagnosticsManager>::lock(void)
0x180072229  nop
0x18007222a  mov     rbx, [rsp+88h+var_20]
0x18007222f  test    rbx, rbx
0x180072232  jnz     short loc_180072269
0x180072234  mov     rcx, [rsp+88h]; this
0x18007223c  mov     r9d, 45Bh; char *
0x180072242  lea     r8, aOnecoreNetNetp_9; "onecore\\net\\netprofiles\\service\\src"...
0x180072249  mov     edx, 0E4h; void *
0x18007224e  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180072253  nop
0x180072254  mov     rcx, [rsp+88h+var_20+8]; this
0x180072259  test    rcx, rcx
0x18007225c  jz      short loc_180072264
0x18007225e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180072263  nop
0x180072264  jmp     loc_18007233B
0x180072269  mov     qword ptr [rsp+88h+PerformanceCount], 0
0x180072272  lea     rcx, [rsp+88h+PerformanceCount]; lpPerformanceCount
0x180072277  call    cs:__imp_QueryPerformanceCounter
0x18007227d  mov     [rsp+88h+var_60], rbx
0x180072282  movups  xmm0, xmmword ptr [rsi]
0x180072285  movdqu  [rsp+88h+var_58], xmm0
0x18007228b  movups  xmm1, xmmword ptr [rdi]
0x18007228e  movups  [rsp+88h+var_48], xmm1
0x180072293  mov     eax, [rdi+10h]
0x180072296  mov     [rsp+88h+var_38], eax
0x18007229a  mov     eax, dword ptr [rsp+88h+PerformanceCount]
0x18007229e  mov     dword ptr [rsp+88h+var_30], eax
0x1800722a2  mov     eax, dword ptr [rsp+88h+PerformanceCount+4]
0x1800722a6  mov     dword ptr [rsp+88h+var_30+4], eax
0x1800722aa  mov     [rsp+88h+lpCriticalSection], 0
0x1800722b3  lea     rdx, [rbx+4F0h]
0x1800722ba  lea     rcx, [rsp+88h+lpCriticalSection]
0x1800722bf  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800722c4  nop
0x1800722c5  lea     rcx, [rbx+580h]
0x1800722cc  cmp     byte ptr [rcx+78h], 0
0x1800722d0  jz      short loc_1800722E4
0x1800722d2  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x1800722d7  test    rcx, rcx
0x1800722da  jz      short loc_180072329
0x1800722dc  call    cs:__imp_LeaveCriticalSection
0x1800722e2  jmp     short loc_180072329
0x1800722e4  lea     rdx, [rsp+88h+var_60]
0x1800722e9  cmp     dword ptr [rbx+4E8h], 1
0x1800722f0  jnz     short loc_1800722F9
0x1800722f2  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__DiagnosticsManager__NcsiNoneCheckCompleteCallback____3____lambda_1___
0x1800722f7  jmp     short loc_180072303
0x1800722f9  add     rcx, 50h ; 'P'
0x1800722fd  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__DiagnosticsManager__NcsiNoneCheckCompleteCallback____3____lambda_1___
0x180072302  nop
0x180072303  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x180072308  test    rcx, rcx
0x18007230b  jz      short loc_180072313
0x18007230d  call    cs:__imp_LeaveCriticalSection
0x180072313  lock inc qword ptr [rbx+570h]
0x18007231b  mov     rcx, [rbx+568h]; pwk
0x180072322  call    cs:__imp_SubmitThreadpoolWork
0x180072328  nop
0x180072329  mov     rcx, [rsp+88h+var_20+8]; this
0x18007232e  test    rcx, rcx
0x180072331  jz      short loc_180072339
0x180072333  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180072338  nop
0x180072339  jmp     short $+2
0x18007233b  mov     rcx, [rsp+88h+var_10]
0x180072340  xor     rcx, rsp; StackCookie
0x180072343  call    __security_check_cookie
0x180072348  lea     r11, [rsp+88h+var_8]
0x180072350  mov     rbx, [r11+10h]
0x180072354  mov     rsi, [r11+18h]
0x180072358  mov     rsp, r11
0x18007235b  pop     rdi
0x18007235c  retn
```
