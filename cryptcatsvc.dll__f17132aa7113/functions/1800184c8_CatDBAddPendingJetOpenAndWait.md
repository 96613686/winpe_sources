# _CatDBAddPendingJetOpenAndWait

- ea: `0x1800184c8`
- end: `0x180018618`
- name: `_CatDBAddPendingJetOpenAndWait`
- size: `336`
- prototype: `__int64 __fastcall(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002fd0`

## callees

- `0x1800015b0`
- `0x180003538`
- `0x18000a59c`
- `0x1800184c8`
- `0x18001b620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018563`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018563`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018511`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180018511`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018556`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018556`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001854b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001854b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018576`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800185b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018607`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018576`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800185b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018607`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800185e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800185e8`

## pseudocode

```c
__int64 __fastcall CatDBAddPendingJetOpenAndWait(DWORD dwMilliseconds)
{
  unsigned int v1; // esi
  _OWORD *v3; // rax
  unsigned int v4; // edx
  unsigned __int16 *v5; // rcx
  _OWORD *v6; // rbx
  HANDLE *v7; // rdi
  unsigned int v8; // r8d
  HANDLE EventW; // rax
  struct _JET_DB_PENDING_OPEN_STRUCT *v10; // rax
  DWORD v11; // ecx
  DWORD LastError; // ebp
  _QWORD *v13; // rcx
  int v15; // [rsp+28h] [rbp-30h]

  v1 = 1;
  ++g_dwJetDBPendingOpenRefCnt;
  v3 = _CatDBAlloc(0x20u);
  v6 = v3;
  v7 = (HANDLE *)(v3 + 1);
  if ( !v3 )
  {
    v8 = 7908;
    goto LABEL_17;
  }
  *v3 = 0;
  v3[1] = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *v7 = EventW;
  if ( !EventW )
  {
    v8 = 7918;
    goto LABEL_17;
  }
  v10 = g_pJetDBPendingOpenHead;
  if ( g_pJetDBPendingOpenHead )
  {
    *((_QWORD *)g_pJetDBPendingOpenHead + 1) = v6;
    *(_QWORD *)v6 = v10;
  }
  g_pJetDBPendingOpenHead = (struct _JET_DB_PENDING_OPEN_STRUCT *)v6;
  LeaveCriticalSection(&g_JetDBOpenCS);
  WaitForSingleObject(*v7, dwMilliseconds);
  EnterCriticalSection(&g_JetDBOpenCS);
  if ( !*((_DWORD *)v6 + 6) )
  {
    if ( *(_QWORD *)v6 )
      *(_QWORD *)(*(_QWORD *)v6 + 8LL) = *((_QWORD *)v6 + 1);
    v13 = (_QWORD *)*((_QWORD *)v6 + 1);
    if ( v13 )
      *v13 = *(_QWORD *)v6;
    else
      g_pJetDBPendingOpenHead = *(struct _JET_DB_PENDING_OPEN_STRUCT **)v6;
    SetLastError(0x5B4u);
    v8 = 7957;
LABEL_17:
    ErrLog_LogError(v5, v4, v8, 0, 0, v15);
    LastError = GetLastError();
    v1 = 0;
    if ( !v6 )
      goto LABEL_21;
    goto LABEL_18;
  }
  v11 = *((_DWORD *)v6 + 7);
  if ( v11 )
  {
    SetLastError(v11);
    v8 = 7938;
    goto LABEL_17;
  }
  LastError = 0;
LABEL_18:
  if ( *v7 )
    CloseHandle(*v7);
  _CatDBFree(v6);
LABEL_21:
  --g_dwJetDBPendingOpenRefCnt;
  CatDBSignalPendingJetFreezeOrStop();
  if ( !v1 )
    SetLastError(LastError);
  return v1;
}

```

## disassembly

```asm
0x1800184c8  push    rbx
0x1800184ca  push    rbp
0x1800184cb  push    rsi
0x1800184cc  push    rdi
0x1800184cd  sub     rsp, 38h
0x1800184d1  mov     esi, 1
0x1800184d6  mov     ebp, ecx
0x1800184d8  add     cs:?g_dwJetDBPendingOpenRefCnt@@3KA, esi; ulong g_dwJetDBPendingOpenRefCnt
0x1800184de  lea     ecx, [rsi+1Fh]; uBytes
0x1800184e1  call    ?_CatDBAlloc@@YAPEAX_K@Z; _CatDBAlloc(unsigned __int64)
0x1800184e6  mov     rbx, rax
0x1800184e9  lea     rdi, [rax+10h]
0x1800184ed  test    rax, rax
0x1800184f0  jnz     short loc_1800184FD
0x1800184f2  mov     r8d, 1EE4h
0x1800184f8  jmp     loc_1800185C1
0x1800184fd  xorps   xmm0, xmm0
0x180018500  xor     r9d, r9d; lpName
0x180018503  movups  xmmword ptr [rax], xmm0
0x180018506  xor     r8d, r8d; bInitialState
0x180018509  xor     edx, edx; bManualReset
0x18001850b  xor     ecx, ecx; lpEventAttributes
0x18001850d  movups  xmmword ptr [rax+10h], xmm0
0x180018511  call    cs:__imp_CreateEventW
0x180018517  mov     [rdi], rax
0x18001851a  test    rax, rax
0x18001851d  jnz     short loc_18001852A
0x18001851f  mov     r8d, 1EEEh
0x180018525  jmp     loc_1800185C1
0x18001852a  mov     rax, cs:?g_pJetDBPendingOpenHead@@3PEAU_JET_DB_PENDING_OPEN_STRUCT@@EA; _JET_DB_PENDING_OPEN_STRUCT * g_pJetDBPendingOpenHead
0x180018531  test    rax, rax
0x180018534  jz      short loc_18001853D
0x180018536  mov     [rax+8], rbx
0x18001853a  mov     [rbx], rax
0x18001853d  lea     rcx, ?g_JetDBOpenCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180018544  mov     cs:?g_pJetDBPendingOpenHead@@3PEAU_JET_DB_PENDING_OPEN_STRUCT@@EA, rbx; _JET_DB_PENDING_OPEN_STRUCT * g_pJetDBPendingOpenHead
0x18001854b  call    cs:__imp_LeaveCriticalSection
0x180018551  mov     rcx, [rdi]; hHandle
0x180018554  mov     edx, ebp; dwMilliseconds
0x180018556  call    cs:__imp_WaitForSingleObject
0x18001855c  lea     rcx, ?g_JetDBOpenCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180018563  call    cs:__imp_EnterCriticalSection
0x180018569  cmp     dword ptr [rbx+18h], 0
0x18001856d  jz      short loc_180018588
0x18001856f  mov     ecx, [rbx+1Ch]; dwErrCode
0x180018572  test    ecx, ecx
0x180018574  jz      short loc_180018584
0x180018576  call    cs:__imp_SetLastError
0x18001857c  mov     r8d, 1F02h
0x180018582  jmp     short loc_1800185C1
0x180018584  xor     ebp, ebp
0x180018586  jmp     short loc_1800185E0
0x180018588  mov     rcx, [rbx]
0x18001858b  test    rcx, rcx
0x18001858e  jz      short loc_180018598
0x180018590  mov     rax, [rbx+8]
0x180018594  mov     [rcx+8], rax
0x180018598  mov     rcx, [rbx+8]
0x18001859c  mov     rax, [rbx]
0x18001859f  test    rcx, rcx
0x1800185a2  jz      short loc_1800185A9
0x1800185a4  mov     [rcx], rax
0x1800185a7  jmp     short loc_1800185B0
0x1800185a9  mov     cs:?g_pJetDBPendingOpenHead@@3PEAU_JET_DB_PENDING_OPEN_STRUCT@@EA, rax; _JET_DB_PENDING_OPEN_STRUCT * g_pJetDBPendingOpenHead
0x1800185b0  mov     ecx, 5B4h; dwErrCode
0x1800185b5  call    cs:__imp_SetLastError
0x1800185bb  mov     r8d, 1F15h; unsigned int
0x1800185c1  xor     r9d, r9d; unsigned int
0x1800185c4  mov     [rsp+58h+var_38], 0; int
0x1800185cc  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800185d1  call    cs:__imp_GetLastError
0x1800185d7  mov     ebp, eax
0x1800185d9  xor     esi, esi
0x1800185db  test    rbx, rbx
0x1800185de  jz      short loc_1800185F6
0x1800185e0  mov     rcx, [rdi]; hObject
0x1800185e3  test    rcx, rcx
0x1800185e6  jz      short loc_1800185EE
0x1800185e8  call    cs:__imp_CloseHandle
0x1800185ee  mov     rcx, rbx; void *
0x1800185f1  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x1800185f6  dec     cs:?g_dwJetDBPendingOpenRefCnt@@3KA; ulong g_dwJetDBPendingOpenRefCnt
0x1800185fc  call    _CatDBSignalPendingJetFreezeOrStop
0x180018601  test    esi, esi
0x180018603  jnz     short loc_18001860D
0x180018605  mov     ecx, ebp; dwErrCode
0x180018607  call    cs:__imp_SetLastError
0x18001860d  mov     eax, esi
0x18001860f  add     rsp, 38h
0x180018613  pop     rdi
0x180018614  pop     rsi
0x180018615  pop     rbp
0x180018616  pop     rbx
0x180018617  retn
```
