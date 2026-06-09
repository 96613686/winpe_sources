# DiagnosticsManager::HandleAddressRemovedNotification(_GUID,IpAddressInfo)

- ea: `0x1800709a0`
- end: `0x180070b2c`
- name: `?HandleAddressRemovedNotification@DiagnosticsManager@@SAXU_GUID@@UIpAddressInfo@@@Z`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180067120`

## callees

- `0x1800097ec`
- `0x180009990`
- `0x18000e190`
- `0x1800213a0`
- `0x1800709a0`
- `0x1800713b8`
- `0x1800a88a0`
- `0x18010e068`
- `0x18010e10c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070aa5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070ad6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070aa5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070ad6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180070aeb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180070aeb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180070a36`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180070a36`

## string_xrefs

- `0x1800709f8`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DiagnosticsManager::HandleAddressRemovedNotification(__int128 *a1, __int64 a2)
{
  __int64 v4; // rbx
  const char *v5; // r9
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+20h] [rbp-F8h] BYREF
  __int64 v7; // [rsp+30h] [rbp-E8h] BYREF
  __int128 v8; // [rsp+38h] [rbp-E0h]
  _BYTE v9[160]; // [rsp+48h] [rbp-D0h] BYREF
  LARGE_INTEGER v10; // [rsp+E8h] [rbp-30h]
  LARGE_INTEGER PerformanceCount; // [rsp+F0h] [rbp-28h] BYREF
  __int128 v12; // [rsp+F8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v12 = 0;
  std::weak_ptr<DiagnosticsManager>::lock(a1, &v12);
  v4 = v12;
  if ( (_QWORD)v12 )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v7 = v4;
    v8 = *a1;
    IpAddressInfo::IpAddressInfo(v9, a2);
    v10 = PerformanceCount;
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
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__DiagnosticsManager::HandleAddressRemovedNotification_::_3_::_lambda_1___(
            v4 + 1408,
            &v7);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__DiagnosticsManager::HandleAddressRemovedNotification_::_3_::_lambda_1___(
            v4 + 1488,
            &v7);
        if ( lpCriticalSection[0] )
          LeaveCriticalSection(lpCriticalSection[0]);
        _InterlockedIncrement64((volatile signed __int64 *)(v4 + 1392));
        SubmitThreadpoolWork(*(PTP_WORK *)(v4 + 1384));
      }
      if ( *((_QWORD *)&v12 + 1) )
        std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v12 + 1));
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x379,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
        v5);
    }
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x35B,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
      (const char *)0x45B,
      (unsigned int)lpCriticalSection[0]);
    if ( *((_QWORD *)&v12 + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v12 + 1));
  }
}

```

## disassembly

```asm
0x1800709a0  mov     r11, rsp
0x1800709a3  mov     [r11+8], rbx
0x1800709a7  mov     [r11+10h], rsi
0x1800709ab  push    rdi
0x1800709ac  sub     rsp, 110h
0x1800709b3  mov     rax, cs:__security_cookie
0x1800709ba  xor     rax, rsp
0x1800709bd  mov     [rsp+118h+var_10], rax
0x1800709c5  mov     rdi, rdx
0x1800709c8  mov     rsi, rcx
0x1800709cb  xorps   xmm0, xmm0
0x1800709ce  movups  xmmword ptr [r11-20h], xmm0
0x1800709d3  lea     rdx, [r11-20h]
0x1800709d7  call    ?lock@?$weak_ptr@VDiagnosticsManager@@@std@@QEBA?AV?$shared_ptr@VDiagnosticsManager@@@2@XZ; std::weak_ptr<DiagnosticsManager>::lock(void)
0x1800709dc  nop
0x1800709dd  mov     rbx, [rsp+118h+var_20]
0x1800709e5  test    rbx, rbx
0x1800709e8  jnz     short loc_180070A22
0x1800709ea  mov     rcx, [rsp+118h]; this
0x1800709f2  mov     r9d, 45Bh; char *
0x1800709f8  lea     r8, aOnecoreNetNetp_9; "onecore\\net\\netprofiles\\service\\src"...
0x1800709ff  mov     edx, 35Bh; void *
0x180070a04  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180070a09  nop
0x180070a0a  mov     rcx, [rsp+118h+var_18]; this
0x180070a12  test    rcx, rcx
0x180070a15  jz      short loc_180070A1D
0x180070a17  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070a1c  nop
0x180070a1d  jmp     loc_180070B07
0x180070a22  mov     qword ptr [rsp+118h+PerformanceCount], 0
0x180070a2e  lea     rcx, [rsp+118h+PerformanceCount]; lpPerformanceCount
0x180070a36  call    cs:__imp_QueryPerformanceCounter
0x180070a3c  mov     [rsp+118h+var_E8], rbx
0x180070a41  movups  xmm0, xmmword ptr [rsi]
0x180070a44  movdqu  [rsp+118h+var_E0], xmm0
0x180070a4a  mov     rdx, rdi
0x180070a4d  lea     rcx, [rsp+118h+var_D0]
0x180070a52  call    ??0IpAddressInfo@@QEAA@$$QEAU0@@Z; IpAddressInfo::IpAddressInfo(IpAddressInfo &&)
0x180070a57  mov     ecx, dword ptr [rsp+118h+PerformanceCount]
0x180070a5e  mov     dword ptr [rsp+118h+var_30], ecx
0x180070a65  mov     eax, dword ptr [rsp+118h+PerformanceCount+4]
0x180070a6c  mov     dword ptr [rsp+118h+var_30+4], eax
0x180070a73  mov     [rsp+118h+lpCriticalSection], 0
0x180070a7c  lea     rdx, [rbx+4F0h]
0x180070a83  lea     rcx, [rsp+118h+lpCriticalSection]
0x180070a88  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180070a8d  nop
0x180070a8e  lea     rcx, [rbx+580h]
0x180070a95  cmp     byte ptr [rcx+78h], 0
0x180070a99  jz      short loc_180070AAD
0x180070a9b  mov     rcx, [rsp+118h+lpCriticalSection]; lpCriticalSection
0x180070aa0  test    rcx, rcx
0x180070aa3  jz      short loc_180070AF2
0x180070aa5  call    cs:__imp_LeaveCriticalSection
0x180070aab  jmp     short loc_180070AF2
0x180070aad  lea     rdx, [rsp+118h+var_E8]
0x180070ab2  cmp     dword ptr [rbx+4E8h], 1
0x180070ab9  jnz     short loc_180070AC2
0x180070abb  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__DiagnosticsManager__HandleAddressRemovedNotification____3____lambda_1___
0x180070ac0  jmp     short loc_180070ACC
0x180070ac2  add     rcx, 50h ; 'P'
0x180070ac6  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__DiagnosticsManager__HandleAddressRemovedNotification____3____lambda_1___
0x180070acb  nop
0x180070acc  mov     rcx, [rsp+118h+lpCriticalSection]; lpCriticalSection
0x180070ad1  test    rcx, rcx
0x180070ad4  jz      short loc_180070ADC
0x180070ad6  call    cs:__imp_LeaveCriticalSection
0x180070adc  lock inc qword ptr [rbx+570h]
0x180070ae4  mov     rcx, [rbx+568h]; pwk
0x180070aeb  call    cs:__imp_SubmitThreadpoolWork
0x180070af1  nop
0x180070af2  mov     rcx, [rsp+118h+var_18]; this
0x180070afa  test    rcx, rcx
0x180070afd  jz      short loc_180070B05
0x180070aff  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070b04  nop
0x180070b05  jmp     short $+2
0x180070b07  mov     rcx, [rsp+118h+var_10]
0x180070b0f  xor     rcx, rsp; StackCookie
0x180070b12  call    __security_check_cookie
0x180070b17  lea     r11, [rsp+118h+var_8]
0x180070b1f  mov     rbx, [r11+10h]
0x180070b23  mov     rsi, [r11+18h]
0x180070b27  mov     rsp, r11
0x180070b2a  pop     rdi
0x180070b2b  retn
```
