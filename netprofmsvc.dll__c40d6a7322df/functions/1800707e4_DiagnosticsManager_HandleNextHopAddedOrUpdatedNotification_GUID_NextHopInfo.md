# DiagnosticsManager::HandleNextHopAddedOrUpdatedNotification(_GUID,NextHopInfo)

- ea: `0x1800707e4`
- end: `0x180070998`
- name: `?HandleNextHopAddedOrUpdatedNotification@DiagnosticsManager@@SAXU_GUID@@UNextHopInfo@@@Z`
- size: `436`
- prototype: `static void __high(struct _GUID, struct NextHopInfo)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002d4b4`
- `0x180066a90`

## callees

- `0x1800097ec`
- `0x180009990`
- `0x18000a08c`
- `0x18000a114`
- `0x18000e190`
- `0x1800707e4`
- `0x1800713b8`
- `0x1800a88a0`
- `0x18010ea28`
- `0x18010eacc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800708f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070926`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800708f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180070926`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007093b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007093b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180070886`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180070886`

## string_xrefs

- `0x180070840`: `onecore\net\netprofiles\service\src\networkdiagnostics\lib\diagnosticsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
void __fastcall DiagnosticsManager::HandleNextHopAddedOrUpdatedNotification(__int128 *a1, NextHopInfo *a2)
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
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__DiagnosticsManager::HandleNextHopAddedOrUpdatedNotification_::_3_::_lambda_1___(
          v4 + 1408,
          &v6);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__DiagnosticsManager::HandleNextHopAddedOrUpdatedNotification_::_3_::_lambda_1___(
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
      (void *)0x2E2,
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
0x1800707e4  mov     r11, rsp
0x1800707e7  mov     [r11+8], rbx
0x1800707eb  mov     [r11+18h], rsi
0x1800707ef  push    rdi
0x1800707f0  sub     rsp, 150h
0x1800707f7  mov     rax, cs:__security_cookie
0x1800707fe  xor     rax, rsp
0x180070801  mov     [rsp+158h+var_18], rax
0x180070809  mov     rbx, rdx
0x18007080c  mov     rsi, rcx
0x18007080f  mov     [r11-38h], rdx
0x180070813  xorps   xmm0, xmm0
0x180070816  movups  xmmword ptr [r11-28h], xmm0
0x18007081b  lea     rdx, [r11-28h]
0x18007081f  call    ?lock@?$weak_ptr@VDiagnosticsManager@@@std@@QEBA?AV?$shared_ptr@VDiagnosticsManager@@@2@XZ; std::weak_ptr<DiagnosticsManager>::lock(void)
0x180070824  nop
0x180070825  mov     rdi, [rsp+158h+var_28]
0x18007082d  test    rdi, rdi
0x180070830  jnz     short loc_180070872
0x180070832  mov     rcx, [rsp+158h]; this
0x18007083a  mov     r9d, 45Bh; char *
0x180070840  lea     r8, aOnecoreNetNetp_9; "onecore\\net\\netprofiles\\service\\src"...
0x180070847  mov     edx, 2E2h; void *
0x18007084c  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180070851  nop
0x180070852  mov     rcx, [rsp+158h+var_20]; this
0x18007085a  test    rcx, rcx
0x18007085d  jz      short loc_180070865
0x18007085f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070864  nop
0x180070865  mov     rcx, rbx; this
0x180070868  call    ??1NextHopInfo@@QEAA@XZ; NextHopInfo::~NextHopInfo(void)
0x18007086d  jmp     loc_180070973
0x180070872  mov     qword ptr [rsp+158h+PerformanceCount], 0
0x18007087e  lea     rcx, [rsp+158h+PerformanceCount]; lpPerformanceCount
0x180070886  call    cs:__imp_QueryPerformanceCounter
0x18007088c  mov     [rsp+158h+var_128], rdi
0x180070891  movups  xmm0, xmmword ptr [rsi]
0x180070894  movdqu  [rsp+158h+var_120], xmm0
0x18007089a  mov     rdx, rbx
0x18007089d  lea     rcx, [rsp+158h+var_110]
0x1800708a2  call    ??0NextHopInfo@@QEAA@$$QEAU0@@Z; NextHopInfo::NextHopInfo(NextHopInfo &&)
0x1800708a7  mov     eax, dword ptr [rsp+158h+PerformanceCount]
0x1800708ae  mov     dword ptr [rsp+158h+var_48], eax
0x1800708b5  mov     eax, dword ptr [rsp+158h+PerformanceCount+4]
0x1800708bc  mov     dword ptr [rsp+158h+var_48+4], eax
0x1800708c3  mov     [rsp+158h+lpCriticalSection], 0
0x1800708cc  lea     rdx, [rdi+4F0h]
0x1800708d3  lea     rcx, [rsp+158h+lpCriticalSection]
0x1800708d8  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800708dd  nop
0x1800708de  lea     rcx, [rdi+580h]
0x1800708e5  cmp     byte ptr [rcx+78h], 0
0x1800708e9  jz      short loc_1800708FD
0x1800708eb  mov     rcx, [rsp+158h+lpCriticalSection]; lpCriticalSection
0x1800708f0  test    rcx, rcx
0x1800708f3  jz      short loc_180070942
0x1800708f5  call    cs:__imp_LeaveCriticalSection
0x1800708fb  jmp     short loc_180070942
0x1800708fd  lea     rdx, [rsp+158h+var_128]
0x180070902  cmp     dword ptr [rdi+4E8h], 1
0x180070909  jnz     short loc_180070912
0x18007090b  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__DiagnosticsManager__HandleNextHopAddedOrUpdatedNotification____3____lambda_1___
0x180070910  jmp     short loc_18007091C
0x180070912  add     rcx, 50h ; 'P'
0x180070916  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__DiagnosticsManager__HandleNextHopAddedOrUpdatedNotification____3____lambda_1___
0x18007091b  nop
0x18007091c  mov     rcx, [rsp+158h+lpCriticalSection]; lpCriticalSection
0x180070921  test    rcx, rcx
0x180070924  jz      short loc_18007092C
0x180070926  call    cs:__imp_LeaveCriticalSection
0x18007092c  lock inc qword ptr [rdi+570h]
0x180070934  mov     rcx, [rdi+568h]; pwk
0x18007093b  call    cs:__imp_SubmitThreadpoolWork
0x180070941  nop
0x180070942  lea     rcx, [rsp+158h+var_110]; this
0x180070947  call    ??1NextHopInfo@@QEAA@XZ; NextHopInfo::~NextHopInfo(void)
0x18007094c  nop
0x18007094d  mov     rcx, [rsp+158h+var_20]; this
0x180070955  test    rcx, rcx
0x180070958  jz      short loc_180070960
0x18007095a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007095f  nop
0x180070960  jmp     short loc_18007096A
0x180070962  mov     rbx, [rsp+158h+var_38]
0x18007096a  mov     rcx, rbx; this
0x18007096d  call    ??1NextHopInfo@@QEAA@XZ; NextHopInfo::~NextHopInfo(void)
0x180070972  nop
0x180070973  mov     rcx, [rsp+158h+var_18]
0x18007097b  xor     rcx, rsp; StackCookie
0x18007097e  call    __security_check_cookie
0x180070983  lea     r11, [rsp+158h+var_8]
0x18007098b  mov     rbx, [r11+10h]
0x18007098f  mov     rsi, [r11+20h]
0x180070993  mov     rsp, r11
0x180070996  pop     rdi
0x180070997  retn
```
