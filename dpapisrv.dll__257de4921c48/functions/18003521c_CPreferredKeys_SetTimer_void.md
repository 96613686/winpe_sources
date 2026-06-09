# CPreferredKeys::SetTimer(void)

- ea: `0x18003521c`
- end: `0x180035318`
- name: `?SetTimer@CPreferredKeys@@SAKXZ`
- size: `252`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003576c`

## callees

- `0x180001184`
- `0x180007f10`
- `0x18001467c`
- `0x18003521c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352e6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180035251`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180035251`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003528b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003528b`

## string_xrefs

- `0x180035303`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180035231`: `ERROR_ALREADY_INITIALIZED`

## pseudocode

```c
__int64 CPreferredKeys::SetTimer(void)
{
  unsigned int v0; // ebx
  const char *v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r9
  struct _TP_TIMER *ThreadpoolTimer; // rax
  __int64 v5; // r9
  DWORD LastError; // eax
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  if ( CPreferredKeys::s_renewTimer )
  {
    v0 = 1247;
    v1 = "ERROR_ALREADY_INITIALIZED";
    v2 = 1247;
    v3 = 4240;
LABEL_9:
    DebugTraceError(v2, v1, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v3);
    return v0;
  }
  ThreadpoolTimer = CreateThreadpoolTimer((PTP_TIMER_CALLBACK)CPreferredKeys::RenewCallback, 0, 0);
  CPreferredKeys::s_renewTimer = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
  {
    if ( (unsigned int)dword_18004C260 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
    {
      pftDueTime.dwLowDateTime = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (int)&dword_18004C260,
        (int)byte_1800451D5,
        0,
        v5,
        (__int64)&pftDueTime);
    }
    LastError = GetLastError();
    v3 = 4276;
    v1 = "lastError";
    v0 = LastError;
    v2 = LastError;
    goto LABEL_9;
  }
  pftDueTime = (struct _FILETIME)-3000000000LL;
  v0 = 0;
  SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0x5265C00u, 0);
  return v0;
}

```

## disassembly

```asm
0x18003521c  push    rbx
0x18003521e  sub     rsp, 30h
0x180035222  cmp     cs:?s_renewTimer@CPreferredKeys@@0PEAU_TP_TIMER@@EA, 0; _TP_TIMER * CPreferredKeys::s_renewTimer
0x18003522a  jz      short loc_180035245
0x18003522c  mov     ebx, 4DFh
0x180035231  lea     rdx, aErrorAlreadyIn; "ERROR_ALREADY_INITIALIZED"
0x180035238  mov     ecx, ebx
0x18003523a  mov     r9d, 1090h
0x180035240  jmp     loc_180035303
0x180035245  xor     r8d, r8d; pcbe
0x180035248  lea     rcx, ?RenewCallback@CPreferredKeys@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003524f  xor     edx, edx; pv
0x180035251  call    cs:__imp_CreateThreadpoolTimer
0x180035258  nop     dword ptr [rax+rax+00h]
0x18003525d  mov     cs:?s_renewTimer@CPreferredKeys@@0PEAU_TP_TIMER@@EA, rax; _TP_TIMER * CPreferredKeys::s_renewTimer
0x180035264  test    rax, rax
0x180035267  jz      short loc_180035299
0x180035269  mov     rcx, 0FFFFFFFF4D2FA200h
0x180035273  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180035278  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rcx
0x18003527d  xor     ebx, ebx
0x18003527f  mov     rcx, rax; pti
0x180035282  xor     r9d, r9d; msWindowLength
0x180035285  mov     r8d, 5265C00h; msPeriod
0x18003528b  call    cs:__imp_SetThreadpoolTimer
0x180035292  nop     dword ptr [rax+rax+00h]
0x180035297  jmp     short loc_18003530F
0x180035299  mov     eax, cs:dword_18004C260
0x18003529f  cmp     eax, 5
0x1800352a2  jbe     short loc_1800352E6
0x1800352a4  mov     rdx, 400000000000h
0x1800352ae  lea     rcx, dword_18004C260
0x1800352b5  call    _tlgKeywordOn
0x1800352ba  test    al, al
0x1800352bc  jz      short loc_1800352E6
0x1800352be  lea     rax, [rsp+38h+pftDueTime]
0x1800352c3  mov     [rsp+38h+pftDueTime.dwLowDateTime], 0
0x1800352cb  xor     r8d, r8d
0x1800352ce  mov     [rsp+38h+var_18], rax
0x1800352d3  lea     rdx, byte_1800451D5
0x1800352da  lea     rcx, dword_18004C260
0x1800352e1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800352e6  call    cs:__imp_GetLastError
0x1800352ed  nop     dword ptr [rax+rax+00h]
0x1800352f2  mov     r9d, 10B4h
0x1800352f8  lea     rdx, aLasterror; "lastError"
0x1800352ff  mov     ebx, eax
0x180035301  mov     ecx, eax
0x180035303  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18003530a  call    DebugTraceError
0x18003530f  mov     eax, ebx
0x180035311  add     rsp, 30h
0x180035315  pop     rbx
0x180035316  retn
```
