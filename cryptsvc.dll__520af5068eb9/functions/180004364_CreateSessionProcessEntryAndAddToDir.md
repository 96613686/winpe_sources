# CreateSessionProcessEntryAndAddToDir

- ea: `0x180004364`
- end: `0x180004491`
- name: `CreateSessionProcessEntryAndAddToDir`
- size: `301`
- prototype: `__int64 __fastcall(__int64, int, int, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005700`

## callees

- `0x1800023f4`
- `0x1800033a0`
- `0x180004364`
- `0x1800068b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000444b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000444b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004381`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004381`

## pseudocode

```c
__int64 __fastcall CreateSessionProcessEntryAndAddToDir(__int64 a1, int a2, int a3, _QWORD *a4)
{
  _QWORD *v8; // rbx
  _QWORD *LogoffExitJob; // rax
  bool v10; // zf
  _QWORD *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // ebx

  EnterCriticalSection(&JobsCriticalSection);
  v8 = (_QWORD *)PkiZeroAlloc(0x30u);
  if ( !v8 )
    goto LABEL_23;
  LogoffExitJob = pPendingLogoffExitJobHead;
  if ( pPendingLogoffExitJobHead )
  {
    do
    {
      if ( a2 )
        v10 = a2 == *((_DWORD *)LogoffExitJob + 10);
      else
        v10 = a3 == *((_DWORD *)LogoffExitJob + 11);
      if ( v10 )
        break;
      LogoffExitJob = (_QWORD *)*LogoffExitJob;
    }
    while ( LogoffExitJob );
    if ( LogoffExitJob )
      goto LABEL_12;
  }
  LogoffExitJob = CreateLogoffExitJob(a2, a3, a4);
  if ( !LogoffExitJob )
  {
    PkiFree(v8);
LABEL_23:
    v14 = 0;
    goto LABEL_17;
  }
  v11 = pPendingLogoffExitJobHead;
  if ( pPendingLogoffExitJobHead )
  {
    *LogoffExitJob = pPendingLogoffExitJobHead;
    v11[1] = LogoffExitJob;
  }
  else
  {
    *LogoffExitJob = 0;
  }
  LogoffExitJob[1] = 0;
  pPendingLogoffExitJobHead = LogoffExitJob;
LABEL_12:
  v12 = LogoffExitJob[4];
  if ( v12 )
  {
    v8[3] = v12;
    *(_QWORD *)(v12 + 32) = v8;
  }
  else
  {
    v8[3] = 0;
  }
  v8[4] = 0;
  LogoffExitJob[4] = v8;
  v8[5] = LogoffExitJob;
  v13 = *(_QWORD *)(a1 + 16);
  if ( v13 )
  {
    *v8 = v13;
    *(_QWORD *)(v13 + 8) = v8;
  }
  else
  {
    *v8 = 0;
  }
  v8[1] = 0;
  *(_QWORD *)(a1 + 16) = v8;
  v8[2] = a1;
  v14 = 1;
LABEL_17:
  LeaveCriticalSection(&JobsCriticalSection);
  return v14;
}

```

## disassembly

```asm
0x180004364  push    rbx
0x180004366  push    rbp
0x180004367  push    rsi
0x180004368  push    rdi
0x180004369  push    r14
0x18000436b  sub     rsp, 20h
0x18000436f  mov     rsi, rcx
0x180004372  mov     r14, r9
0x180004375  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000437c  mov     ebp, r8d
0x18000437f  mov     edi, edx
0x180004381  call    cs:__imp_EnterCriticalSection
0x180004387  mov     ecx, 30h ; '0'; uBytes
0x18000438c  call    PkiZeroAlloc
0x180004391  mov     rbx, rax
0x180004394  test    rax, rax
0x180004397  jz      loc_18000448D
0x18000439d  mov     rax, cs:?pPendingLogoffExitJobHead@@3PEAU_CUCS_LOGOFF_EXIT_JOB_ENTRY@@EA; _CUCS_LOGOFF_EXIT_JOB_ENTRY * pPendingLogoffExitJobHead
0x1800043a4  test    rax, rax
0x1800043a7  jz      short loc_1800043C3
0x1800043a9  test    edi, edi
0x1800043ab  jnz     loc_18000445E
0x1800043b1  cmp     ebp, [rax+2Ch]
0x1800043b4  jz      short loc_1800043BE
0x1800043b6  mov     rax, [rax]
0x1800043b9  test    rax, rax
0x1800043bc  jnz     short loc_1800043A9
0x1800043be  test    rax, rax
0x1800043c1  jnz     short loc_1800043FE
0x1800043c3  mov     r8, r14
0x1800043c6  mov     edx, ebp
0x1800043c8  mov     ecx, edi
0x1800043ca  call    CreateLogoffExitJob
0x1800043cf  test    rax, rax
0x1800043d2  jz      loc_180004485
0x1800043d8  mov     rcx, cs:?pPendingLogoffExitJobHead@@3PEAU_CUCS_LOGOFF_EXIT_JOB_ENTRY@@EA; _CUCS_LOGOFF_EXIT_JOB_ENTRY * pPendingLogoffExitJobHead
0x1800043df  test    rcx, rcx
0x1800043e2  jz      loc_180004479
0x1800043e8  mov     [rax], rcx
0x1800043eb  mov     [rcx+8], rax
0x1800043ef  mov     qword ptr [rax+8], 0
0x1800043f7  mov     cs:?pPendingLogoffExitJobHead@@3PEAU_CUCS_LOGOFF_EXIT_JOB_ENTRY@@EA, rax; _CUCS_LOGOFF_EXIT_JOB_ENTRY * pPendingLogoffExitJobHead
0x1800043fe  mov     rcx, [rax+20h]
0x180004402  test    rcx, rcx
0x180004405  jz      short loc_180004466
0x180004407  mov     [rbx+18h], rcx
0x18000440b  mov     [rcx+20h], rbx
0x18000440f  mov     qword ptr [rbx+20h], 0
0x180004417  mov     [rax+20h], rbx
0x18000441b  mov     [rbx+28h], rax
0x18000441f  mov     rax, [rsi+10h]
0x180004423  test    rax, rax
0x180004426  jz      short loc_180004470
0x180004428  mov     [rbx], rax
0x18000442b  mov     [rax+8], rbx
0x18000442f  mov     qword ptr [rbx+8], 0
0x180004437  mov     [rsi+10h], rbx
0x18000443b  mov     [rbx+10h], rsi
0x18000443f  mov     ebx, 1
0x180004444  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000444b  call    cs:__imp_LeaveCriticalSection
0x180004451  mov     eax, ebx
0x180004453  add     rsp, 20h
0x180004457  pop     r14
0x180004459  pop     rdi
0x18000445a  pop     rsi
0x18000445b  pop     rbp
0x18000445c  pop     rbx
0x18000445d  retn
0x18000445e  cmp     edi, [rax+28h]
0x180004461  jmp     loc_1800043B4
0x180004466  mov     qword ptr [rbx+18h], 0
0x18000446e  jmp     short loc_18000440F
0x180004470  mov     qword ptr [rbx], 0
0x180004477  jmp     short loc_18000442F
0x180004479  mov     qword ptr [rax], 0
0x180004480  jmp     loc_1800043EF
0x180004485  mov     rcx, rbx; hMem
0x180004488  call    PkiFree
0x18000448d  xor     ebx, ebx
0x18000448f  jmp     short loc_180004444
```
