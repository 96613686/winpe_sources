# CloudIdSvcModule::ServiceStopped(void)

- ea: `0x180006f7c`
- end: `0x180007031`
- name: `?ServiceStopped@CloudIdSvcModule@@QEAAXXZ`
- size: `181`
- prototype: `void __fastcall(CloudIdSvcModule *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004820`

## callees

- `0x180003e84`
- `0x180004518`
- `0x180006cf4`
- `0x180006d14`
- `0x180006f7c`
- `0x18000ca48`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180006fa9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180006fa9`

## string_xrefs

- `0x180006f85`: `ServiceStop`
- `0x180006fbb`: `onecoreuap\ds\ext\common\ntservice\lib\tenantrestrictions.cpp`
- `0x180006fdb`: `onecoreuap\ds\ext\common\ntservice\lib\tenantrestrictions.cpp`

## pseudocode

```c
void __fastcall CloudIdSvcModule::ServiceStopped(CloudIdSvcModule *this)
{
  TenantRestrictions *v1; // rbx
  __int64 v2; // rcx
  const char *v3; // r9
  int LastError; // eax
  _BYTE v5[244]; // [rsp+20h] [rbp-118h] BYREF
  int v6; // [rsp+114h] [rbp-24h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  TenantRestrictionsLoggers::AutoMeasureLogger::AutoMeasureLogger(
    (TenantRestrictionsLoggers::AutoMeasureLogger *)v5,
    "ServiceStop");
  v1 = g_trGlobals;
  if ( DeleteTimerQueueTimer(*((HANDLE *)g_trGlobals + 14), *((HANDLE *)g_trGlobals + 13), (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
  {
    *((_QWORD *)v1 + 13) = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xAB,
                  (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
                  v3);
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E,
        (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
        (const char *)(unsigned int)LastError);
      TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger((TenantRestrictionsLoggers::AutoMeasureLogger *)v5);
      return;
    }
  }
  std::unique_ptr<TenantRestrictions>::reset(v2, 0);
  v5[240] = 1;
  v6 = 0;
  TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger((TenantRestrictionsLoggers::AutoMeasureLogger *)v5);
}

```

## disassembly

```asm
0x180006f7c  push    rbx
0x180006f7e  sub     rsp, 130h
0x180006f85  lea     rdx, aServicestop; "ServiceStop"
0x180006f8c  lea     rcx, [rsp+138h+var_118]; this
0x180006f91  call    ??0AutoMeasureLogger@TenantRestrictionsLoggers@@QEAA@PEBD@Z; TenantRestrictionsLoggers::AutoMeasureLogger::AutoMeasureLogger(char const *)
0x180006f96  mov     rbx, cs:?g_trGlobals@@3V?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@A; std::unique_ptr<TenantRestrictions> g_trGlobals
0x180006f9d  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180006fa1  mov     rdx, [rbx+68h]; Timer
0x180006fa5  mov     rcx, [rbx+70h]; TimerQueue
0x180006fa9  call    cs:__imp_DeleteTimerQueueTimer
0x180006faf  test    eax, eax
0x180006fb1  jnz     short loc_180006FF9
0x180006fb3  mov     rcx, [rsp+138h]; this
0x180006fbb  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x180006fc2  mov     edx, 0ABh; void *
0x180006fc7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006fcc  test    eax, eax
0x180006fce  jns     short loc_180007001
0x180006fd0  mov     rcx, [rsp+138h]; this
0x180006fd8  mov     r9d, eax; char *
0x180006fdb  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x180006fe2  mov     edx, 2Eh ; '.'; void *
0x180006fe7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006fec  lea     rcx, [rsp+138h+var_118]; this
0x180006ff1  call    ??1AutoMeasureLogger@TenantRestrictionsLoggers@@UEAA@XZ; TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger(void)
0x180006ff6  nop
0x180006ff7  jmp     short loc_180007028
0x180006ff9  mov     qword ptr [rbx+68h], 0
0x180007001  xor     edx, edx
0x180007003  call    ?reset@?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@QEAAXPEAVTenantRestrictions@@@Z; std::unique_ptr<TenantRestrictions>::reset(TenantRestrictions *)
0x180007008  mov     [rsp+138h+var_28], 1
0x180007010  mov     [rsp+138h+var_24], 0
0x18000701b  lea     rcx, [rsp+138h+var_118]; this
0x180007020  call    ??1AutoMeasureLogger@TenantRestrictionsLoggers@@UEAA@XZ; TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger(void)
0x180007025  nop
0x180007026  jmp     short $+2
0x180007028  add     rsp, 130h
0x18000702f  pop     rbx
0x180007030  retn
```
