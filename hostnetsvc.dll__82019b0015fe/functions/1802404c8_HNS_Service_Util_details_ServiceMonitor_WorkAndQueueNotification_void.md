# HNS::Service::Util::details::ServiceMonitor::WorkAndQueueNotification(void)

- ea: `0x1802404c8`
- end: `0x18024070f`
- name: `?WorkAndQueueNotification@ServiceMonitor@details@Util@Service@HNS@@AEAAKXZ`
- size: `583`
- prototype: `unsigned int __fastcall(HNS::Service::Util::details::ServiceMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180240720`

## callees

- `0x18005f560`
- `0x18005ffc4`
- `0x18006035c`
- `0x180064018`
- `0x1800663fc`
- `0x1800759d8`
- `0x180075aac`
- `0x180080804`
- `0x18023feb0`
- `0x1802404c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802405be`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802405d3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802405be`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1802405d3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180240598`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180240598`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18024061b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18024061b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180240608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180240658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180240608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180240658`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180240613`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180240613`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18024064e`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18024064e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18024053f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180240567`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18024053f`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180240567`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1802405f0`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1802405f0`

## string_xrefs

- `0x1802404e0`: `HNS::Service::Util::details::ServiceMonitor::WorkAndQueueNotification`
- `0x1802406a2`: `HNS::Service::Util::details::ServiceMonitor::WorkAndQueueNotification`
- `0x18024068c`: `onecore\vm\dv\net\hns\service\common\helperlib\src\servicemonitor.cpp`
- `0x1802406cf`: `onecore\vm\dv\net\hns\service\common\helperlib\src\servicemonitor.cpp`
- `0x1802406fd`: `onecore\vm\dv\net\hns\service\common\helperlib\src\servicemonitor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HNS::Service::Util::details::ServiceMonitor::WorkAndQueueNotification(
        HNS::Service::Util::details::ServiceMonitor *this)
{
  int v2; // r14d
  struct _QUERY_SERVICE_CONFIGW *v3; // rbx
  const struct std::nothrow_t *v4; // rdx
  const char *v5; // r9
  DWORD dwStartType; // ebp
  void *v7; // rcx
  unsigned int v8; // r8d
  const char *v9; // r9
  DWORD v10; // edx
  unsigned int v11; // ebx
  unsigned int v12; // r8d
  const char *v13; // r9
  unsigned int v14; // r8d
  const char *v15; // r9
  DWORD v16; // esi
  SC_HANDLE v17; // rsi
  DWORD LastError; // ebx
  const char *v19; // r9
  const char *v22; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD pcbBytesNeeded; // [rsp+60h] [rbp+8h] BYREF
  struct _QUERY_SERVICE_CONFIGW *v25; // [rsp+68h] [rbp+10h]

  HNSTraceProvider::TraceEnter("HNS::Service::Util::details::ServiceMonitor::WorkAndQueueNotification", 0x5Bu);
  while ( 1 )
  {
    HNS::Service::Util::details::ServiceMonitor::OpenServiceHandle(this);
    v2 = *(_DWORD *)this;
    memset_0((char *)this + 168, 0, 0x50u);
    *((_DWORD *)this + 42) = 2;
    *((_QWORD *)this + 22) = HNS::Service::Util::details::ServiceMonitor::ServiceNotify;
    *((_QWORD *)this + 23) = this;
    pcbBytesNeeded = 0;
    QueryServiceConfigW(*((SC_HANDLE *)this + 1), 0, 0, &pcbBytesNeeded);
    v3 = (struct _QUERY_SERVICE_CONFIGW *)operator new[](pcbBytesNeeded);
    v25 = v3;
    if ( !QueryServiceConfigW(*((SC_HANDLE *)this + 1), v3, pcbBytesNeeded, &pcbBytesNeeded) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\servicemonitor.cpp",
        v5);
    dwStartType = v3->dwStartType;
    operator delete(v3, v4);
    v7 = (void *)*((_QWORD *)this + 8);
    if ( v2 )
    {
      if ( !SetEvent(v7) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v14, v15);
      v10 = 5;
      goto LABEL_11;
    }
    if ( dwStartType == 4 )
    {
      if ( !SetEvent(v7) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v12, v13);
      v10 = 8;
LABEL_11:
      v11 = -1;
      goto LABEL_12;
    }
    if ( !ResetEvent(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA06, v8, v9);
    v10 = 8;
    v11 = *((_BYTE *)this + 248) != 0 ? 5000 : -1;
LABEL_12:
    v16 = NotifyServiceStatusChangeW(*((SC_HANDLE *)this + 1), v10, (PSERVICE_NOTIFYW)((char *)this + 168));
    if ( v16 != 1294 )
      break;
    v17 = (SC_HANDLE)*((_QWORD *)this + 1);
    if ( v17 )
    {
      LastError = GetLastError();
      CloseServiceHandle(v17);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 1) = 0;
  }
  if ( !v16
    && *((_BYTE *)this + 248)
    && !v2
    && dwStartType != 4
    && !StartServiceW(*((SC_HANDLE *)this + 1), 0, 0)
    && GetLastError() != 1056 )
  {
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\servicemonitor.cpp",
      v19);
  }
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x93,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\common\\helperlib\\src\\servicemonitor.cpp",
    (const char *)v16,
    (unsigned int)"Queing notification failed",
    v22);
  HNSTraceProvider::TraceSuccess("HNS::Service::Util::details::ServiceMonitor::WorkAndQueueNotification", 0x94u);
  return v11;
}

```

## disassembly

```asm
0x1802404c8  mov     [rsp+arg_10], rbx
0x1802404cd  push    rbp
0x1802404ce  push    rsi
0x1802404cf  push    rdi
0x1802404d0  push    r14
0x1802404d2  push    r15
0x1802404d4  sub     rsp, 30h
0x1802404d8  mov     rdi, rcx
0x1802404db  mov     edx, 5Bh ; '['; unsigned int
0x1802404e0  lea     rcx, aHnsServiceUtil; "HNS::Service::Util::details::ServiceMon"...
0x1802404e7  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1802404ec  lea     r15, [rdi+0A8h]
0x1802404f3  mov     rcx, rdi; this
0x1802404f6  call    ?OpenServiceHandle@ServiceMonitor@details@Util@Service@HNS@@AEAAXXZ; HNS::Service::Util::details::ServiceMonitor::OpenServiceHandle(void)
0x1802404fb  mov     r14d, [rdi]
0x1802404fe  nop
0x1802404ff  xor     edx, edx; Val
0x180240501  lea     r8d, [rdx+50h]; Size
0x180240505  mov     rcx, r15; void *
0x180240508  call    memset_0
0x18024050d  mov     dword ptr [r15], 2
0x180240514  lea     rax, ?ServiceNotify@ServiceMonitor@details@Util@Service@HNS@@CAXPEAX@Z; HNS::Service::Util::details::ServiceMonitor::ServiceNotify(void *)
0x18024051b  mov     [rdi+0B0h], rax
0x180240522  mov     [rdi+0B8h], rdi
0x180240529  mov     [rsp+58h+pcbBytesNeeded], 0
0x180240531  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x180240536  xor     r8d, r8d; cbBufSize
0x180240539  xor     edx, edx; lpServiceConfig
0x18024053b  mov     rcx, [rdi+8]; hService
0x18024053f  call    cs:__imp_QueryServiceConfigW
0x180240545  mov     ecx, [rsp+58h+pcbBytesNeeded]; unsigned __int64
0x180240549  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18024054e  mov     rbx, rax
0x180240551  mov     [rsp+58h+arg_8], rax
0x180240556  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x18024055b  mov     r8d, [rsp+58h+pcbBytesNeeded]; cbBufSize
0x180240560  mov     rdx, rax; lpServiceConfig
0x180240563  mov     rcx, [rdi+8]; hService
0x180240567  call    cs:__imp_QueryServiceConfigW
0x18024056d  mov     rcx, [rsp+58h]; this
0x180240572  test    eax, eax
0x180240574  jz      loc_1802406CF
0x18024057a  mov     ebp, [rbx+4]
0x18024057d  mov     rcx, rbx; void *
0x180240580  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180240585  mov     rcx, [rdi+40h]; hEvent
0x180240589  mov     rbx, [rsp+58h]
0x18024058e  test    r14d, r14d
0x180240591  jnz     short loc_1802405D3
0x180240593  cmp     ebp, 4
0x180240596  jz      short loc_1802405BE
0x180240598  call    cs:__imp_ResetEvent
0x18024059e  test    eax, eax
0x1802405a0  jz      loc_1802406E1
0x1802405a6  lea     edx, [r14+8]
0x1802405aa  mov     al, [rdi+0F8h]
0x1802405b0  neg     al
0x1802405b2  sbb     ebx, ebx
0x1802405b4  and     ebx, 1389h
0x1802405ba  dec     ebx
0x1802405bc  jmp     short loc_1802405E9
0x1802405be  call    cs:__imp_SetEvent
0x1802405c4  test    eax, eax
0x1802405c6  jz      loc_1802406EF
0x1802405cc  mov     edx, 8
0x1802405d1  jmp     short loc_1802405E6
0x1802405d3  call    cs:__imp_SetEvent
0x1802405d9  test    eax, eax
0x1802405db  jz      loc_1802406C1
0x1802405e1  mov     edx, 5; dwNotifyMask
0x1802405e6  or      ebx, 0FFFFFFFFh
0x1802405e9  mov     r8, r15; pNotifyBuffer
0x1802405ec  mov     rcx, [rdi+8]; hService
0x1802405f0  call    cs:__imp_NotifyServiceStatusChangeW
0x1802405f6  mov     esi, eax
0x1802405f8  cmp     eax, 50Eh
0x1802405fd  jnz     short loc_18024062E
0x1802405ff  mov     rsi, [rdi+8]
0x180240603  test    rsi, rsi
0x180240606  jz      short loc_180240621
0x180240608  call    cs:__imp_GetLastError
0x18024060e  mov     ebx, eax
0x180240610  mov     rcx, rsi; hSCObject
0x180240613  call    cs:__imp_CloseServiceHandle
0x180240619  mov     ecx, ebx; dwErrCode
0x18024061b  call    cs:__imp_SetLastError
0x180240621  mov     qword ptr [rdi+8], 0
0x180240629  jmp     loc_1802404F3
0x18024062e  test    esi, esi
0x180240630  jnz     short loc_180240678
0x180240632  cmp     [rdi+0F8h], sil
0x180240639  jz      short loc_180240678
0x18024063b  test    r14d, r14d
0x18024063e  jnz     short loc_180240678
0x180240640  cmp     ebp, 4
0x180240643  jz      short loc_180240678
0x180240645  xor     r8d, r8d; lpServiceArgVectors
0x180240648  xor     edx, edx; dwNumServiceArgs
0x18024064a  mov     rcx, [rdi+8]; hService
0x18024064e  call    cs:__imp_StartServiceW
0x180240654  test    eax, eax
0x180240656  jnz     short loc_180240669
0x180240658  call    cs:__imp_GetLastError
0x18024065e  cmp     eax, 420h
0x180240663  jz      short loc_180240669
0x180240665  mov     al, 1
0x180240667  jmp     short loc_18024066B
0x180240669  xor     al, al
0x18024066b  mov     rcx, [rsp+58h]; this
0x180240670  test    al, al
0x180240672  jnz     loc_1802406FD
0x180240678  mov     rcx, [rsp+58h]; this
0x18024067d  lea     rax, aQueingNotifica; "Queing notification failed"
0x180240684  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x180240689  mov     r9d, esi; char *
0x18024068c  lea     r8, aOnecoreVmDvNet_47; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x180240693  mov     edx, 93h; void *
0x180240698  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18024069d  mov     edx, 94h; unsigned int
0x1802406a2  lea     rcx, aHnsServiceUtil; "HNS::Service::Util::details::ServiceMon"...
0x1802406a9  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x1802406ae  mov     eax, ebx
0x1802406b0  mov     rbx, [rsp+58h+arg_10]
0x1802406b5  add     rsp, 30h
0x1802406b9  pop     r15
0x1802406bb  pop     r14
0x1802406bd  pop     rdi
0x1802406be  pop     rsi
0x1802406bf  pop     rbp
0x1802406c0  retn
0x1802406c1  mov     edx, 0A01h; void *
0x1802406c6  mov     rcx, rbx; this
0x1802406c9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1802406cf  lea     r8, aOnecoreVmDvNet_47; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x1802406d6  mov     edx, 0FFh; void *
0x1802406db  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1802406e1  mov     edx, 0A06h; void *
0x1802406e6  mov     rcx, rbx; this
0x1802406e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1802406ef  mov     edx, 0A01h; void *
0x1802406f4  mov     rcx, rbx; this
0x1802406f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1802406fd  lea     r8, aOnecoreVmDvNet_47; "onecore\\vm\\dv\\net\\hns\\service\\com"...
0x180240704  mov     edx, 8Eh; void *
0x180240709  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
