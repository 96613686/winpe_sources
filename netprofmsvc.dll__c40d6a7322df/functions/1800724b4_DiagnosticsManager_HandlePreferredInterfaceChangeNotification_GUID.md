# DiagnosticsManager::HandlePreferredInterfaceChangeNotification(_GUID)

- ea: `0x1800724b4`
- end: `0x1800725fc`
- name: `?HandlePreferredInterfaceChangeNotification@DiagnosticsManager@@SAXU_GUID@@@Z`
- size: `328`
- prototype: `void __fastcall(struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180057ca0`

## callees

- `0x1800097ec`
- `0x180009990`
- `0x18000e190`
- `0x1800713b8`
- `0x1800724b4`
- `0x1800a88a0`
- `0x18010ee3c`
- `0x18010eefc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072582`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800725b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072582`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800725b3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800725c8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800725c8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007252c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007252c`

## string_xrefs

- `0x1800724f8`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DiagnosticsManager::HandlePreferredInterfaceChangeNotification(struct _GUID *a1)
{
  std::_Ref_count_base *v2; // rbx
  const char *v3; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v5[2]; // [rsp+28h] [rbp-50h] BYREF
  struct _GUID v6; // [rsp+38h] [rbp-40h]
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-30h] BYREF
  std::_Ref_count_base *v8[2]; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_OWORD *)v8 = 0;
  std::weak_ptr<DiagnosticsManager>::lock(a1, v8);
  v2 = v8[0];
  if ( v8[0] )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v5[0] = v2;
    v5[1] = PerformanceCount.QuadPart;
    v6 = *a1;
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
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__DiagnosticsManager::HandlePreferredInterfaceChangeNotification_::_3_::_lambda_1___(
            (char *)v2 + 1408,
            v5);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__DiagnosticsManager::HandlePreferredInterfaceChangeNotification_::_3_::_lambda_1___(
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
        (void *)0x4DB,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
        v3);
    }
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x4C3,
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
0x1800724b4  mov     [rsp+arg_0], rbx
0x1800724b9  push    rdi
0x1800724ba  sub     rsp, 70h
0x1800724be  mov     rax, cs:__security_cookie
0x1800724c5  xor     rax, rsp
0x1800724c8  mov     [rsp+78h+var_18], rax
0x1800724cd  mov     rdi, rcx
0x1800724d0  xorps   xmm0, xmm0
0x1800724d3  movups  xmmword ptr [rsp+78h+var_28], xmm0
0x1800724d8  lea     rdx, [rsp+78h+var_28]
0x1800724dd  call    ?lock@?$weak_ptr@VDiagnosticsManager@@@std@@QEBA?AV?$shared_ptr@VDiagnosticsManager@@@2@XZ; std::weak_ptr<DiagnosticsManager>::lock(void)
0x1800724e2  nop
0x1800724e3  mov     rbx, [rsp+78h+var_28]
0x1800724e8  test    rbx, rbx
0x1800724eb  jnz     short loc_18007251E
0x1800724ed  mov     rcx, [rsp+78h]; this
0x1800724f2  mov     r9d, 45Bh; char *
0x1800724f8  lea     r8, aOnecoreNetNetp_9; "onecore\\net\\netprofiles\\service\\src"...
0x1800724ff  lea     edx, [r9+68h]; void *
0x180072503  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180072508  nop
0x180072509  mov     rcx, [rsp+78h+var_28+8]; this
0x18007250e  test    rcx, rcx
0x180072511  jz      short loc_180072519
0x180072513  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180072518  nop
0x180072519  jmp     loc_1800725E1
0x18007251e  mov     qword ptr [rsp+78h+PerformanceCount], 0
0x180072527  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x18007252c  call    cs:__imp_QueryPerformanceCounter
0x180072532  mov     [rsp+78h+var_50], rbx
0x180072537  mov     eax, dword ptr [rsp+78h+PerformanceCount]
0x18007253b  mov     dword ptr [rsp+78h+var_48], eax
0x18007253f  mov     eax, dword ptr [rsp+78h+PerformanceCount+4]
0x180072543  mov     dword ptr [rsp+78h+var_48+4], eax
0x180072547  movups  xmm0, xmmword ptr [rdi]
0x18007254a  movdqu  [rsp+78h+var_40], xmm0
0x180072550  mov     [rsp+78h+lpCriticalSection], 0
0x180072559  lea     rdx, [rbx+4F0h]
0x180072560  lea     rcx, [rsp+78h+lpCriticalSection]
0x180072565  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18007256a  nop
0x18007256b  lea     rcx, [rbx+580h]
0x180072572  cmp     byte ptr [rcx+78h], 0
0x180072576  jz      short loc_18007258A
0x180072578  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x18007257d  test    rcx, rcx
0x180072580  jz      short loc_1800725CF
0x180072582  call    cs:__imp_LeaveCriticalSection
0x180072588  jmp     short loc_1800725CF
0x18007258a  lea     rdx, [rsp+78h+var_50]
0x18007258f  cmp     dword ptr [rbx+4E8h], 1
0x180072596  jnz     short loc_18007259F
0x180072598  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__DiagnosticsManager__HandlePreferredInterfaceChangeNotification____3____lambda_1___
0x18007259d  jmp     short loc_1800725A9
0x18007259f  add     rcx, 50h ; 'P'
0x1800725a3  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__DiagnosticsManager__HandlePreferredInterfaceChangeNotification____3____lambda_1___
0x1800725a8  nop
0x1800725a9  mov     rcx, [rsp+78h+lpCriticalSection]; lpCriticalSection
0x1800725ae  test    rcx, rcx
0x1800725b1  jz      short loc_1800725B9
0x1800725b3  call    cs:__imp_LeaveCriticalSection
0x1800725b9  lock inc qword ptr [rbx+570h]
0x1800725c1  mov     rcx, [rbx+568h]; pwk
0x1800725c8  call    cs:__imp_SubmitThreadpoolWork
0x1800725ce  nop
0x1800725cf  mov     rcx, [rsp+78h+var_28+8]; this
0x1800725d4  test    rcx, rcx
0x1800725d7  jz      short loc_1800725DF
0x1800725d9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800725de  nop
0x1800725df  jmp     short $+2
0x1800725e1  mov     rcx, [rsp+78h+var_18]
0x1800725e6  xor     rcx, rsp; StackCookie
0x1800725e9  call    __security_check_cookie
0x1800725ee  mov     rbx, [rsp+78h+arg_0]
0x1800725f6  add     rsp, 70h
0x1800725fa  pop     rdi
0x1800725fb  retn
```
