# DiagnosticsManager::NcsiActiveProbeCompleteCallback(_GUID,_NcsiActiveProbeCompleteMetadata)

- ea: `0x1800713f0`
- end: `0x1800715d0`
- name: `?NcsiActiveProbeCompleteCallback@DiagnosticsManager@@CAXU_GUID@@U_NcsiActiveProbeCompleteMetadata@@@Z`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800097ec`
- `0x180009990`
- `0x18000e190`
- `0x1800713b8`
- `0x1800713f0`
- `0x1800a88a0`
- `0x18010f6e0`
- `0x18010f784`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071549`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007157a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071549`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007157a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007158f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007158f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180071486`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180071486`

## string_xrefs

- `0x180071448`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DiagnosticsManager::NcsiActiveProbeCompleteCallback(__int128 *a1, _OWORD *a2)
{
  __int64 v4; // rbx
  char *v5; // rax
  __int64 v6; // rcx
  const char *v7; // r9
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+20h] [rbp-278h] BYREF
  __int64 v9; // [rsp+30h] [rbp-268h] BYREF
  __int128 v10; // [rsp+38h] [rbp-260h]
  char v11; // [rsp+48h] [rbp-250h] BYREF
  LARGE_INTEGER v12; // [rsp+268h] [rbp-30h]
  LARGE_INTEGER PerformanceCount; // [rsp+270h] [rbp-28h] BYREF
  __int128 v14; // [rsp+278h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v14 = 0;
  std::weak_ptr<DiagnosticsManager>::lock(a1, &v14);
  v4 = v14;
  if ( (_QWORD)v14 )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v9 = v4;
    v10 = *a1;
    v5 = &v11;
    v6 = 4;
    do
    {
      *(_OWORD *)v5 = *a2;
      *((_OWORD *)v5 + 1) = a2[1];
      *((_OWORD *)v5 + 2) = a2[2];
      *((_OWORD *)v5 + 3) = a2[3];
      *((_OWORD *)v5 + 4) = a2[4];
      *((_OWORD *)v5 + 5) = a2[5];
      *((_OWORD *)v5 + 6) = a2[6];
      *((_OWORD *)v5 + 7) = a2[7];
      v5 += 128;
      a2 += 8;
      --v6;
    }
    while ( v6 );
    *(_OWORD *)v5 = *a2;
    *((_OWORD *)v5 + 1) = a2[1];
    v12 = PerformanceCount;
    lpCriticalSection[0] = 0;
    wil::EnterCriticalSection(lpCriticalSection, v4 + 1264);
    try
    {
      if ( *(_BYTE *)(v4 + 1528) )
      {
        if ( lpCriticalSection[0] )
          LeaveCriticalSection(lpCriticalSection[0]);
      }
      else
      {
        if ( *(_DWORD *)(v4 + 1256) == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__DiagnosticsManager::NcsiActiveProbeCompleteCallback_::_3_::_lambda_1___(
            v4 + 1408,
            &v9);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__DiagnosticsManager::NcsiActiveProbeCompleteCallback_::_3_::_lambda_1___(
            v4 + 1488,
            &v9);
        if ( lpCriticalSection[0] )
          LeaveCriticalSection(lpCriticalSection[0]);
        _InterlockedIncrement64((volatile signed __int64 *)(v4 + 1392));
        SubmitThreadpoolWork(*(PTP_WORK *)(v4 + 1384));
      }
      if ( *((_QWORD *)&v14 + 1) )
        std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v14 + 1));
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xDC,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
        v7);
    }
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
      (const char *)0x45B,
      (unsigned int)lpCriticalSection[0]);
    if ( *((_QWORD *)&v14 + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v14 + 1));
  }
}

```

## disassembly

```asm
0x1800713f0  mov     r11, rsp
0x1800713f3  mov     [r11+8], rbx
0x1800713f7  mov     [r11+10h], rsi
0x1800713fb  push    rdi
0x1800713fc  sub     rsp, 290h
0x180071403  mov     rax, cs:__security_cookie
0x18007140a  xor     rax, rsp
0x18007140d  mov     [rsp+298h+var_10], rax
0x180071415  mov     rdi, rdx
0x180071418  mov     rsi, rcx
0x18007141b  xorps   xmm0, xmm0
0x18007141e  movups  xmmword ptr [r11-20h], xmm0
0x180071423  lea     rdx, [r11-20h]
0x180071427  call    ?lock@?$weak_ptr@VDiagnosticsManager@@@std@@QEBA?AV?$shared_ptr@VDiagnosticsManager@@@2@XZ; std::weak_ptr<DiagnosticsManager>::lock(void)
0x18007142c  nop
0x18007142d  mov     rbx, [rsp+298h+var_20]
0x180071435  test    rbx, rbx
0x180071438  jnz     short loc_180071472
0x18007143a  mov     rcx, [rsp+298h]; this
0x180071442  mov     r9d, 45Bh; char *
0x180071448  lea     r8, aOnecoreNetNetp_9; "onecore\\net\\netprofiles\\service\\src"...
0x18007144f  mov     edx, 0BAh; void *
0x180071454  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180071459  nop
0x18007145a  mov     rcx, [rsp+298h+var_18]; this
0x180071462  test    rcx, rcx
0x180071465  jz      short loc_18007146D
0x180071467  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007146c  nop
0x18007146d  jmp     loc_1800715AB
0x180071472  mov     qword ptr [rsp+298h+PerformanceCount], 0
0x18007147e  lea     rcx, [rsp+298h+PerformanceCount]; lpPerformanceCount
0x180071486  call    cs:__imp_QueryPerformanceCounter
0x18007148c  mov     [rsp+298h+var_268], rbx
0x180071491  movups  xmm0, xmmword ptr [rsi]
0x180071494  movdqu  [rsp+298h+var_260], xmm0
0x18007149a  lea     rax, [rsp+298h+var_250]
0x18007149f  mov     ecx, 4
0x1800714a4  lea     edx, [rcx+7Ch]
0x1800714a7  movups  xmm0, xmmword ptr [rdi]
0x1800714aa  movups  xmmword ptr [rax], xmm0
0x1800714ad  movups  xmm1, xmmword ptr [rdi+10h]
0x1800714b1  movups  xmmword ptr [rax+10h], xmm1
0x1800714b5  movups  xmm0, xmmword ptr [rdi+20h]
0x1800714b9  movups  xmmword ptr [rax+20h], xmm0
0x1800714bd  movups  xmm1, xmmword ptr [rdi+30h]
0x1800714c1  movups  xmmword ptr [rax+30h], xmm1
0x1800714c5  movups  xmm0, xmmword ptr [rdi+40h]
0x1800714c9  movups  xmmword ptr [rax+40h], xmm0
0x1800714cd  movups  xmm1, xmmword ptr [rdi+50h]
0x1800714d1  movups  xmmword ptr [rax+50h], xmm1
0x1800714d5  movups  xmm0, xmmword ptr [rdi+60h]
0x1800714d9  movups  xmmword ptr [rax+60h], xmm0
0x1800714dd  movups  xmm1, xmmword ptr [rdi+70h]
0x1800714e1  movups  xmmword ptr [rax+70h], xmm1
0x1800714e5  add     rax, rdx
0x1800714e8  add     rdi, rdx
0x1800714eb  sub     rcx, 1
0x1800714ef  jnz     short loc_1800714A7
0x1800714f1  movups  xmm0, xmmword ptr [rdi]
0x1800714f4  movups  xmmword ptr [rax], xmm0
0x1800714f7  movups  xmm1, xmmword ptr [rdi+10h]
0x1800714fb  movups  xmmword ptr [rax+10h], xmm1
0x1800714ff  mov     eax, dword ptr [rsp+298h+PerformanceCount]
0x180071506  mov     dword ptr [rsp+298h+var_30], eax
0x18007150d  mov     eax, dword ptr [rsp+298h+PerformanceCount+4]
0x180071514  mov     dword ptr [rsp+298h+var_30+4], eax
0x18007151b  mov     [rsp+298h+lpCriticalSection], rcx
0x180071520  lea     rdx, [rbx+4F0h]
0x180071527  lea     rcx, [rsp+298h+lpCriticalSection]
0x18007152c  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180071531  nop
0x180071532  lea     rcx, [rbx+580h]
0x180071539  cmp     byte ptr [rcx+78h], 0
0x18007153d  jz      short loc_180071551
0x18007153f  mov     rcx, [rsp+298h+lpCriticalSection]; lpCriticalSection
0x180071544  test    rcx, rcx
0x180071547  jz      short loc_180071596
0x180071549  call    cs:__imp_LeaveCriticalSection
0x18007154f  jmp     short loc_180071596
0x180071551  lea     rdx, [rsp+298h+var_268]
0x180071556  cmp     dword ptr [rbx+4E8h], 1
0x18007155d  jnz     short loc_180071566
0x18007155f  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__DiagnosticsManager__NcsiActiveProbeCompleteCallback____3____lambda_1___
0x180071564  jmp     short loc_180071570
0x180071566  add     rcx, 50h ; 'P'
0x18007156a  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__DiagnosticsManager__NcsiActiveProbeCompleteCallback____3____lambda_1___
0x18007156f  nop
0x180071570  mov     rcx, [rsp+298h+lpCriticalSection]; lpCriticalSection
0x180071575  test    rcx, rcx
0x180071578  jz      short loc_180071580
0x18007157a  call    cs:__imp_LeaveCriticalSection
0x180071580  lock inc qword ptr [rbx+570h]
0x180071588  mov     rcx, [rbx+568h]; pwk
0x18007158f  call    cs:__imp_SubmitThreadpoolWork
0x180071595  nop
0x180071596  mov     rcx, [rsp+298h+var_18]; this
0x18007159e  test    rcx, rcx
0x1800715a1  jz      short loc_1800715A9
0x1800715a3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800715a8  nop
0x1800715a9  jmp     short $+2
0x1800715ab  mov     rcx, [rsp+298h+var_10]
0x1800715b3  xor     rcx, rsp; StackCookie
0x1800715b6  call    __security_check_cookie
0x1800715bb  lea     r11, [rsp+298h+var_8]
0x1800715c3  mov     rbx, [r11+10h]
0x1800715c7  mov     rsi, [r11+18h]
0x1800715cb  mov     rsp, r11
0x1800715ce  pop     rdi
0x1800715cf  retn
```
