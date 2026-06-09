# DiagnosticsManager::HandleNextHopRemovedNotification(_GUID,NextHopInfo)

- ea: `0x180071bdc`
- end: `0x180071d90`
- name: `?HandleNextHopRemovedNotification@DiagnosticsManager@@SAXU_GUID@@UNextHopInfo@@@Z`
- size: `436`
- prototype: `static void __high(struct _GUID, struct NextHopInfo)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d4b4`

## callees

- `0x1800097ec`
- `0x180009990`
- `0x18000a08c`
- `0x18000a114`
- `0x18000e190`
- `0x1800713b8`
- `0x180071bdc`
- `0x1800a88a0`
- `0x18010eb70`
- `0x18010ec14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071ced`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071d1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071ced`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180071d1e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180071d33`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180071d33`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180071c7e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180071c7e`

## string_xrefs

- `0x180071c38`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
void __fastcall DiagnosticsManager::HandleNextHopRemovedNotification(__int128 *a1, NextHopInfo *a2)
{
  __int64 v4; // rdi
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+20h] [rbp-138h] BYREF
  __int64 v6; // [rsp+30h] [rbp-128h] BYREF
  __int128 v7; // [rsp+38h] [rbp-120h]
  _BYTE v8[200]; // [rsp+48h] [rbp-110h] BYREF
  LARGE_INTEGER v9; // [rsp+110h] [rbp-48h]
  NextHopInfo *v10; // [rsp+120h] [rbp-38h]
  LARGE_INTEGER PerformanceCount; // [rsp+128h] [rbp-30h] BYREF
  __int128 v12; // [rsp+130h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v10 = a2;
  v12 = 0;
  std::weak_ptr<DiagnosticsManager>::lock(a1, &v12);
  v4 = v12;
  if ( (_QWORD)v12 )
  {
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v6 = v4;
    v7 = *a1;
    NextHopInfo::NextHopInfo(v8, a2);
    v9 = PerformanceCount;
    lpCriticalSection[0] = 0;
    wil::EnterCriticalSection(lpCriticalSection, v4 + 1264);
    if ( *(_BYTE *)(v4 + 1528) )
    {
      if ( lpCriticalSection[0] )
        LeaveCriticalSection(lpCriticalSection[0]);
    }
    else
    {
      if ( *(_DWORD *)(v4 + 1256) == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__DiagnosticsManager::HandleNextHopRemovedNotification_::_3_::_lambda_1___(
          v4 + 1408,
          &v6);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__DiagnosticsManager::HandleNextHopRemovedNotification_::_3_::_lambda_1___(
          v4 + 1488,
          &v6);
      if ( lpCriticalSection[0] )
        LeaveCriticalSection(lpCriticalSection[0]);
      _InterlockedIncrement64((volatile signed __int64 *)(v4 + 1392));
      SubmitThreadpoolWork(*(PTP_WORK *)(v4 + 1384));
    }
    NextHopInfo::~NextHopInfo((NextHopInfo *)v8);
    if ( *((_QWORD *)&v12 + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v12 + 1));
    NextHopInfo::~NextHopInfo(a2);
  }
  else
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x30C,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\networkdiagnostics\\lib\\diagnosticsmanager.cpp",
      (const char *)0x45B,
      (unsigned int)lpCriticalSection[0]);
    if ( *((_QWORD *)&v12 + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v12 + 1));
    NextHopInfo::~NextHopInfo(a2);
  }
}

```

## disassembly

```asm
0x180071bdc  mov     r11, rsp
0x180071bdf  mov     [r11+8], rbx
0x180071be3  mov     [r11+18h], rsi
0x180071be7  push    rdi
0x180071be8  sub     rsp, 150h
0x180071bef  mov     rax, cs:__security_cookie
0x180071bf6  xor     rax, rsp
0x180071bf9  mov     [rsp+158h+var_18], rax
0x180071c01  mov     rbx, rdx
0x180071c04  mov     rsi, rcx
0x180071c07  mov     [r11-38h], rdx
0x180071c0b  xorps   xmm0, xmm0
0x180071c0e  movups  xmmword ptr [r11-28h], xmm0
0x180071c13  lea     rdx, [r11-28h]
0x180071c17  call    ?lock@?$weak_ptr@VDiagnosticsManager@@@std@@QEBA?AV?$shared_ptr@VDiagnosticsManager@@@2@XZ; std::weak_ptr<DiagnosticsManager>::lock(void)
0x180071c1c  nop
0x180071c1d  mov     rdi, [rsp+158h+var_28]
0x180071c25  test    rdi, rdi
0x180071c28  jnz     short loc_180071C6A
0x180071c2a  mov     rcx, [rsp+158h]; this
0x180071c32  mov     r9d, 45Bh; char *
0x180071c38  lea     r8, aOnecoreNetNetp_9; "onecore\\net\\netprofiles\\service\\src"...
0x180071c3f  mov     edx, 30Ch; void *
0x180071c44  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180071c49  nop
0x180071c4a  mov     rcx, [rsp+158h+var_20]; this
0x180071c52  test    rcx, rcx
0x180071c55  jz      short loc_180071C5D
0x180071c57  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071c5c  nop
0x180071c5d  mov     rcx, rbx; this
0x180071c60  call    ??1NextHopInfo@@QEAA@XZ; NextHopInfo::~NextHopInfo(void)
0x180071c65  jmp     loc_180071D6B
0x180071c6a  mov     qword ptr [rsp+158h+PerformanceCount], 0
0x180071c76  lea     rcx, [rsp+158h+PerformanceCount]; lpPerformanceCount
0x180071c7e  call    cs:__imp_QueryPerformanceCounter
0x180071c84  mov     [rsp+158h+var_128], rdi
0x180071c89  movups  xmm0, xmmword ptr [rsi]
0x180071c8c  movdqu  [rsp+158h+var_120], xmm0
0x180071c92  mov     rdx, rbx
0x180071c95  lea     rcx, [rsp+158h+var_110]
0x180071c9a  call    ??0NextHopInfo@@QEAA@$$QEAU0@@Z; NextHopInfo::NextHopInfo(NextHopInfo &&)
0x180071c9f  mov     eax, dword ptr [rsp+158h+PerformanceCount]
0x180071ca6  mov     dword ptr [rsp+158h+var_48], eax
0x180071cad  mov     eax, dword ptr [rsp+158h+PerformanceCount+4]
0x180071cb4  mov     dword ptr [rsp+158h+var_48+4], eax
0x180071cbb  mov     [rsp+158h+lpCriticalSection], 0
0x180071cc4  lea     rdx, [rdi+4F0h]
0x180071ccb  lea     rcx, [rsp+158h+lpCriticalSection]
0x180071cd0  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180071cd5  nop
0x180071cd6  lea     rcx, [rdi+580h]
0x180071cdd  cmp     byte ptr [rcx+78h], 0
0x180071ce1  jz      short loc_180071CF5
0x180071ce3  mov     rcx, [rsp+158h+lpCriticalSection]; lpCriticalSection
0x180071ce8  test    rcx, rcx
0x180071ceb  jz      short loc_180071D3A
0x180071ced  call    cs:__imp_LeaveCriticalSection
0x180071cf3  jmp     short loc_180071D3A
0x180071cf5  lea     rdx, [rsp+158h+var_128]
0x180071cfa  cmp     dword ptr [rdi+4E8h], 1
0x180071d01  jnz     short loc_180071D0A
0x180071d03  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__DiagnosticsManager__HandleNextHopRemovedNotification____3____lambda_1___
0x180071d08  jmp     short loc_180071D14
0x180071d0a  add     rcx, 50h ; 'P'
0x180071d0e  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__DiagnosticsManager__HandleNextHopRemovedNotification____3____lambda_1___
0x180071d13  nop
0x180071d14  mov     rcx, [rsp+158h+lpCriticalSection]; lpCriticalSection
0x180071d19  test    rcx, rcx
0x180071d1c  jz      short loc_180071D24
0x180071d1e  call    cs:__imp_LeaveCriticalSection
0x180071d24  lock inc qword ptr [rdi+570h]
0x180071d2c  mov     rcx, [rdi+568h]; pwk
0x180071d33  call    cs:__imp_SubmitThreadpoolWork
0x180071d39  nop
0x180071d3a  lea     rcx, [rsp+158h+var_110]; this
0x180071d3f  call    ??1NextHopInfo@@QEAA@XZ; NextHopInfo::~NextHopInfo(void)
0x180071d44  nop
0x180071d45  mov     rcx, [rsp+158h+var_20]; this
0x180071d4d  test    rcx, rcx
0x180071d50  jz      short loc_180071D58
0x180071d52  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180071d57  nop
0x180071d58  jmp     short loc_180071D62
0x180071d5a  mov     rbx, [rsp+158h+var_38]
0x180071d62  mov     rcx, rbx; this
0x180071d65  call    ??1NextHopInfo@@QEAA@XZ; NextHopInfo::~NextHopInfo(void)
0x180071d6a  nop
0x180071d6b  mov     rcx, [rsp+158h+var_18]
0x180071d73  xor     rcx, rsp; StackCookie
0x180071d76  call    __security_check_cookie
0x180071d7b  lea     r11, [rsp+158h+var_8]
0x180071d83  mov     rbx, [r11+10h]
0x180071d87  mov     rsi, [r11+20h]
0x180071d8b  mov     rsp, r11
0x180071d8e  pop     rdi
0x180071d8f  retn
```
