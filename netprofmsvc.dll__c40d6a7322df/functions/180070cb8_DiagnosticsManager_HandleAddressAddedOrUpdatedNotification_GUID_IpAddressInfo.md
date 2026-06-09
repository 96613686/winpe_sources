# DiagnosticsManager::HandleAddressAddedOrUpdatedNotification(_GUID,IpAddressInfo)

- ea: `0x180070cb8`
- end: `0x180070e44`
- name: `?HandleAddressAddedOrUpdatedNotification@DiagnosticsManager@@SAXU_GUID@@UIpAddressInfo@@@Z`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180067120`

## callees

- `0x1800097ec`
- `0x180009990`
- `0x18000e190`
- `0x1800213a0`
- `0x180070cb8`
- `0x1800713b8`
- `0x1800a88a0`
- `0x18010df20`
- `0x18010dfc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070dbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070dee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070dbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070dee`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180070e03`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180070e03`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180070d4e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180070d4e`

## string_xrefs

- `0x180070d10`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DiagnosticsManager::HandleAddressAddedOrUpdatedNotification(__int128 *a1, __int64 a2)
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
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__DiagnosticsManager::HandleAddressAddedOrUpdatedNotification_::_3_::_lambda_1___(
            v4 + 1408,
            &v7);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__DiagnosticsManager::HandleAddressAddedOrUpdatedNotification_::_3_::_lambda_1___(
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
        (void *)0x353,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
        v5);
    }
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x332,
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
0x180070cb8  mov     r11, rsp
0x180070cbb  mov     [r11+8], rbx
0x180070cbf  mov     [r11+10h], rsi
0x180070cc3  push    rdi
0x180070cc4  sub     rsp, 110h
0x180070ccb  mov     rax, cs:__security_cookie
0x180070cd2  xor     rax, rsp
0x180070cd5  mov     [rsp+118h+var_10], rax
0x180070cdd  mov     rdi, rdx
0x180070ce0  mov     rsi, rcx
0x180070ce3  xorps   xmm0, xmm0
0x180070ce6  movups  xmmword ptr [r11-20h], xmm0
0x180070ceb  lea     rdx, [r11-20h]
0x180070cef  call    ?lock@?$weak_ptr@VDiagnosticsManager@@@std@@QEBA?AV?$shared_ptr@VDiagnosticsManager@@@2@XZ; std::weak_ptr<DiagnosticsManager>::lock(void)
0x180070cf4  nop
0x180070cf5  mov     rbx, [rsp+118h+var_20]
0x180070cfd  test    rbx, rbx
0x180070d00  jnz     short loc_180070D3A
0x180070d02  mov     rcx, [rsp+118h]; this
0x180070d0a  mov     r9d, 45Bh; char *
0x180070d10  lea     r8, aOnecoreNetNetp_9; "onecore\\net\\netprofiles\\service\\src"...
0x180070d17  mov     edx, 332h; void *
0x180070d1c  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180070d21  nop
0x180070d22  mov     rcx, [rsp+118h+var_18]; this
0x180070d2a  test    rcx, rcx
0x180070d2d  jz      short loc_180070D35
0x180070d2f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070d34  nop
0x180070d35  jmp     loc_180070E1F
0x180070d3a  mov     qword ptr [rsp+118h+PerformanceCount], 0
0x180070d46  lea     rcx, [rsp+118h+PerformanceCount]; lpPerformanceCount
0x180070d4e  call    cs:__imp_QueryPerformanceCounter
0x180070d54  mov     [rsp+118h+var_E8], rbx
0x180070d59  movups  xmm0, xmmword ptr [rsi]
0x180070d5c  movdqu  [rsp+118h+var_E0], xmm0
0x180070d62  mov     rdx, rdi
0x180070d65  lea     rcx, [rsp+118h+var_D0]
0x180070d6a  call    ??0IpAddressInfo@@QEAA@$$QEAU0@@Z; IpAddressInfo::IpAddressInfo(IpAddressInfo &&)
0x180070d6f  mov     ecx, dword ptr [rsp+118h+PerformanceCount]
0x180070d76  mov     dword ptr [rsp+118h+var_30], ecx
0x180070d7d  mov     eax, dword ptr [rsp+118h+PerformanceCount+4]
0x180070d84  mov     dword ptr [rsp+118h+var_30+4], eax
0x180070d8b  mov     [rsp+118h+lpCriticalSection], 0
0x180070d94  lea     rdx, [rbx+4F0h]
0x180070d9b  lea     rcx, [rsp+118h+lpCriticalSection]
0x180070da0  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180070da5  nop
0x180070da6  lea     rcx, [rbx+580h]
0x180070dad  cmp     byte ptr [rcx+78h], 0
0x180070db1  jz      short loc_180070DC5
0x180070db3  mov     rcx, [rsp+118h+lpCriticalSection]; lpCriticalSection
0x180070db8  test    rcx, rcx
0x180070dbb  jz      short loc_180070E0A
0x180070dbd  call    cs:__imp_LeaveCriticalSection
0x180070dc3  jmp     short loc_180070E0A
0x180070dc5  lea     rdx, [rsp+118h+var_E8]
0x180070dca  cmp     dword ptr [rbx+4E8h], 1
0x180070dd1  jnz     short loc_180070DDA
0x180070dd3  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__DiagnosticsManager__HandleAddressAddedOrUpdatedNotification____3____lambda_1___
0x180070dd8  jmp     short loc_180070DE4
0x180070dda  add     rcx, 50h ; 'P'
0x180070dde  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__DiagnosticsManager__HandleAddressAddedOrUpdatedNotification____3____lambda_1___
0x180070de3  nop
0x180070de4  mov     rcx, [rsp+118h+lpCriticalSection]; lpCriticalSection
0x180070de9  test    rcx, rcx
0x180070dec  jz      short loc_180070DF4
0x180070dee  call    cs:__imp_LeaveCriticalSection
0x180070df4  lock inc qword ptr [rbx+570h]
0x180070dfc  mov     rcx, [rbx+568h]; pwk
0x180070e03  call    cs:__imp_SubmitThreadpoolWork
0x180070e09  nop
0x180070e0a  mov     rcx, [rsp+118h+var_18]; this
0x180070e12  test    rcx, rcx
0x180070e15  jz      short loc_180070E1D
0x180070e17  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070e1c  nop
0x180070e1d  jmp     short $+2
0x180070e1f  mov     rcx, [rsp+118h+var_10]
0x180070e27  xor     rcx, rsp; StackCookie
0x180070e2a  call    __security_check_cookie
0x180070e2f  lea     r11, [rsp+118h+var_8]
0x180070e37  mov     rbx, [r11+10h]
0x180070e3b  mov     rsi, [r11+18h]
0x180070e3f  mov     rsp, r11
0x180070e42  pop     rdi
0x180070e43  retn
```
