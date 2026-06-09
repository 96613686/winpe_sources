# AddSrvOcspResp(_SRV_OCSP_RESP *)

- ea: `0x1800c6470`
- end: `0x1800c654f`
- name: `?AddSrvOcspResp@@YAHPEAU_SRV_OCSP_RESP@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(struct _SRV_OCSP_RESP *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800ab390`

## callees

- `0x1800c6470`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c64e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c64e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c6504`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c6504`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800c64a2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800c64a2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c652f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c652f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6541`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6541`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c6480`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c6480`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800c64d7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800c64d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c64f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6511`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c64f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6511`

## pseudocode

```c
__int64 __fastcall AddSrvOcspResp(struct _SRV_OCSP_RESP *a1)
{
  LPSECURITY_ATTRIBUTES v2; // rcx
  HANDLE v3; // rax
  DWORD LastError; // ebx
  unsigned int v5; // ebx
  DWORD ThreadId; // [rsp+48h] [rbp+10h] BYREF

  EnterCriticalSection(&SrvOcspRespGlobalCriticalSection);
  v2 = hSrvOcspRespThreadEvent;
  if ( hSrvOcspRespThreadEvent )
    goto LABEL_7;
  ThreadId = 0;
  hSrvOcspRespThreadEvent = (LPSECURITY_ATTRIBUTES)CreateEventA(0, 0, 0, 0);
  if ( hSrvOcspRespThreadEvent )
  {
    v3 = CreateThread(0, 0x5000u, SrvOcspRespPreFetchThreadProc, 0, 0, &ThreadId);
    if ( !v3 )
    {
      LastError = GetLastError();
      CloseHandle(hSrvOcspRespThreadEvent);
      hSrvOcspRespThreadEvent = 0;
      SetLastError(LastError);
      goto LABEL_5;
    }
    CloseHandle(v3);
    v2 = hSrvOcspRespThreadEvent;
LABEL_7:
    *(_QWORD *)a1 = pSrvOcspRespAddHead;
    pSrvOcspRespAddHead = a1;
    SetEvent(v2);
    v5 = 1;
    goto LABEL_8;
  }
LABEL_5:
  v5 = 0;
LABEL_8:
  LeaveCriticalSection(&SrvOcspRespGlobalCriticalSection);
  return v5;
}

```

## disassembly

```asm
0x1800c6470  push    rbx
0x1800c6472  sub     rsp, 30h
0x1800c6476  mov     rbx, rcx
0x1800c6479  lea     rcx, ?SrvOcspRespGlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800c6480  call    cs:__imp_EnterCriticalSection
0x1800c6486  mov     rcx, cs:?hSrvOcspRespThreadEvent@@3PEAXEA; lpEventAttributes
0x1800c648d  test    rcx, rcx
0x1800c6490  jnz     loc_1800C651E
0x1800c6496  xor     r9d, r9d; lpName
0x1800c6499  mov     [rsp+38h+ThreadId], ecx
0x1800c649d  xor     r8d, r8d; bInitialState
0x1800c64a0  xor     edx, edx; bManualReset
0x1800c64a2  call    cs:__imp_CreateEventA
0x1800c64a8  mov     cs:?hSrvOcspRespThreadEvent@@3PEAXEA, rax; void * hSrvOcspRespThreadEvent
0x1800c64af  test    rax, rax
0x1800c64b2  jz      short loc_1800C650A
0x1800c64b4  lea     rax, [rsp+38h+ThreadId]
0x1800c64b9  xor     r9d, r9d; lpParameter
0x1800c64bc  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800c64c1  lea     r8, ?SrvOcspRespPreFetchThreadProc@@YAKPEAX@Z; lpStartAddress
0x1800c64c8  mov     edx, 5000h; dwStackSize
0x1800c64cd  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800c64d5  xor     ecx, ecx; lpThreadAttributes
0x1800c64d7  call    cs:__imp_CreateThread
0x1800c64dd  test    rax, rax
0x1800c64e0  jnz     short loc_1800C650E
0x1800c64e2  call    cs:__imp_GetLastError
0x1800c64e8  mov     rcx, cs:?hSrvOcspRespThreadEvent@@3PEAXEA; hObject
0x1800c64ef  mov     ebx, eax
0x1800c64f1  call    cs:__imp_CloseHandle
0x1800c64f7  mov     ecx, ebx; dwErrCode
0x1800c64f9  mov     cs:?hSrvOcspRespThreadEvent@@3PEAXEA, 0; void * hSrvOcspRespThreadEvent
0x1800c6504  call    cs:__imp_SetLastError
0x1800c650a  xor     ebx, ebx
0x1800c650c  jmp     short loc_1800C653A
0x1800c650e  mov     rcx, rax; hObject
0x1800c6511  call    cs:__imp_CloseHandle
0x1800c6517  mov     rcx, cs:?hSrvOcspRespThreadEvent@@3PEAXEA; hEvent
0x1800c651e  mov     rax, cs:?pSrvOcspRespAddHead@@3PEAU_SRV_OCSP_RESP@@EA; _SRV_OCSP_RESP * pSrvOcspRespAddHead
0x1800c6525  mov     [rbx], rax
0x1800c6528  mov     cs:?pSrvOcspRespAddHead@@3PEAU_SRV_OCSP_RESP@@EA, rbx; _SRV_OCSP_RESP * pSrvOcspRespAddHead
0x1800c652f  call    cs:__imp_SetEvent
0x1800c6535  mov     ebx, 1
0x1800c653a  lea     rcx, ?SrvOcspRespGlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800c6541  call    cs:__imp_LeaveCriticalSection
0x1800c6547  mov     eax, ebx
0x1800c6549  add     rsp, 30h
0x1800c654d  pop     rbx
0x1800c654e  retn
```
