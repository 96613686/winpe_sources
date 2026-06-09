# AddRetrievalPreFetchJob

- ea: `0x180001ca0`
- end: `0x180001e66`
- name: `AddRetrievalPreFetchJob`
- size: `454`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180005460`
- `0x180006aa0`

## callees

- `0x180001ca0`
- `0x180001e70`
- `0x180001eac`
- `0x1800033a0`
- `0x1800068b0`
- `0x1800068f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001da7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001d78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001da7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001cba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001dbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001cba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001dbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e25`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001d23`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180001d23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d43`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001e5b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001e5b`

## pseudocode

```c
void __fastcall AddRetrievalPreFetchJob(_QWORD *a1)
{
  LPCRITICAL_SECTION v2; // rax
  HMODULE v3; // rsi
  LPCRITICAL_SECTION v4; // r9
  HANDLE v5; // rcx
  struct _CUCS_PRE_FETCH_JOB_ENTRY *v6; // rax
  struct _RTL_CRITICAL_SECTION *v7; // rax
  DWORD LastError; // eax
  DWORD ThreadId; // [rsp+48h] [rbp+10h] BYREF

  EnterCriticalSection(&JobsCriticalSection);
  v2 = pRetrievalPreFetchJobInfo;
  if ( !pRetrievalPreFetchJobInfo || (v3 = 0, !*(_QWORD *)&pRetrievalPreFetchJobInfo[1].LockCount) )
  {
    LeaveCriticalSection(&JobsCriticalSection);
    v3 = (HMODULE)DuplicateLibrary();
    EnterCriticalSection(&JobsCriticalSection);
    v2 = pRetrievalPreFetchJobInfo;
  }
  if ( !v2 )
  {
    v7 = (struct _RTL_CRITICAL_SECTION *)PkiZeroAlloc(0x38u);
    pRetrievalPreFetchJobInfo = v7;
    if ( !v7 )
      goto LABEL_22;
    if ( !(unsigned int)Pki_InitializeCriticalSection(v7) )
    {
      PkiFree(pRetrievalPreFetchJobInfo);
      pRetrievalPreFetchJobInfo = 0;
      goto LABEL_22;
    }
    v2 = pRetrievalPreFetchJobInfo;
  }
  if ( HIDWORD(v2[1].DebugInfo) )
  {
LABEL_9:
    v6 = pRetrievalPreFetchJobTail;
    if ( pRetrievalPreFetchJobTail )
    {
      a1[1] = pRetrievalPreFetchJobTail;
      *(_QWORD *)v6 = a1;
    }
    else
    {
      a1[1] = 0;
      pRetrievalPreFetchJobHead = a1;
    }
    *a1 = 0;
    pRetrievalPreFetchJobTail = (struct _CUCS_PRE_FETCH_JOB_ENTRY *)a1;
    *((_DWORD *)a1 + 29) = 2;
    goto LABEL_12;
  }
  v4 = pRetrievalPreFetchJobInfo;
  ThreadId = 0;
  if ( !*(_QWORD *)&pRetrievalPreFetchJobInfo[1].LockCount )
  {
    *(_QWORD *)&pRetrievalPreFetchJobInfo[1].LockCount = v3;
    v3 = 0;
  }
  v5 = CreateThread(0, 0x5000u, (LPTHREAD_START_ROUTINE)RetrievalPreFetchJobThreadProc, v4, 0, &ThreadId);
  if ( v5 )
  {
    HIDWORD(pRetrievalPreFetchJobInfo[1].DebugInfo) = 1;
    CloseHandle(v5);
    goto LABEL_9;
  }
  if ( !v3 )
  {
    v3 = *(HMODULE *)&pRetrievalPreFetchJobInfo[1].LockCount;
    *(_QWORD *)&pRetrievalPreFetchJobInfo[1].LockCount = 0;
  }
LABEL_22:
  LastError = GetLastError();
  *((_DWORD *)a1 + 30) = LastError;
  if ( !LastError )
    *((_DWORD *)a1 + 30) = -2147418113;
  *((_DWORD *)a1 + 29) = 4;
  AddToBeRunJobEx(a1, 3, 0);
LABEL_12:
  LeaveCriticalSection(&JobsCriticalSection);
  if ( v3 )
    FreeLibrary(v3);
}

```

## disassembly

```asm
0x180001ca0  push    rsi
0x180001ca2  sub     rsp, 30h
0x180001ca6  mov     [rsp+38h+arg_0], rbx
0x180001cab  mov     rbx, rcx
0x180001cae  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001cb5  mov     [rsp+38h+arg_10], rdi
0x180001cba  call    cs:__imp_EnterCriticalSection
0x180001cc0  mov     rax, cs:?pRetrievalPreFetchJobInfo@@3PEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@EA; _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO * pRetrievalPreFetchJobInfo
0x180001cc7  xor     edi, edi
0x180001cc9  test    rax, rax
0x180001ccc  jz      loc_180001DA0
0x180001cd2  mov     esi, edi
0x180001cd4  cmp     [rax+30h], rdi
0x180001cd8  jz      loc_180001DA0
0x180001cde  test    rax, rax
0x180001ce1  jz      loc_180001DCE
0x180001ce7  mov     eax, [rax+2Ch]
0x180001cea  test    eax, eax
0x180001cec  jnz     short loc_180001D49
0x180001cee  mov     r9, cs:?pRetrievalPreFetchJobInfo@@3PEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@EA; lpParameter
0x180001cf5  mov     [rsp+38h+ThreadId], edi
0x180001cf9  cmp     qword ptr [r9+30h], 0
0x180001cfe  jnz     short loc_180001D07
0x180001d00  mov     [r9+30h], rsi
0x180001d04  mov     rsi, rdi
0x180001d07  lea     rax, [rsp+38h+ThreadId]
0x180001d0c  mov     edx, 5000h; dwStackSize
0x180001d11  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180001d16  lea     r8, ?RetrievalPreFetchJobThreadProc@@YAKPEAX@Z; lpStartAddress
0x180001d1d  xor     ecx, ecx; lpThreadAttributes
0x180001d1f  mov     [rsp+38h+dwCreationFlags], edi; dwCreationFlags
0x180001d23  call    cs:__imp_CreateThread
0x180001d29  mov     rcx, rax; hObject
0x180001d2c  test    rax, rax
0x180001d2f  jz      loc_180001E11
0x180001d35  mov     rax, cs:?pRetrievalPreFetchJobInfo@@3PEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@EA; _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO * pRetrievalPreFetchJobInfo
0x180001d3c  mov     dword ptr [rax+2Ch], 1
0x180001d43  call    cs:__imp_CloseHandle
0x180001d49  mov     rax, cs:?pRetrievalPreFetchJobTail@@3PEAU_CUCS_PRE_FETCH_JOB_ENTRY@@EA; _CUCS_PRE_FETCH_JOB_ENTRY * pRetrievalPreFetchJobTail
0x180001d50  test    rax, rax
0x180001d53  jnz     short loc_180001D97
0x180001d55  mov     [rbx+8], rdi
0x180001d59  mov     cs:?pRetrievalPreFetchJobHead@@3PEAU_CUCS_PRE_FETCH_JOB_ENTRY@@EA, rbx; _CUCS_PRE_FETCH_JOB_ENTRY * pRetrievalPreFetchJobHead
0x180001d60  mov     [rbx], rdi
0x180001d63  mov     cs:?pRetrievalPreFetchJobTail@@3PEAU_CUCS_PRE_FETCH_JOB_ENTRY@@EA, rbx; _CUCS_PRE_FETCH_JOB_ENTRY * pRetrievalPreFetchJobTail
0x180001d6a  mov     dword ptr [rbx+74h], 2
0x180001d71  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001d78  call    cs:__imp_LeaveCriticalSection
0x180001d7e  mov     rdi, [rsp+38h+arg_10]
0x180001d83  mov     rbx, [rsp+38h+arg_0]
0x180001d88  test    rsi, rsi
0x180001d8b  jnz     loc_180001E58
0x180001d91  add     rsp, 30h
0x180001d95  pop     rsi
0x180001d96  retn
0x180001d97  mov     [rbx+8], rax
0x180001d9b  mov     [rax], rbx
0x180001d9e  jmp     short loc_180001D60
0x180001da0  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001da7  call    cs:__imp_LeaveCriticalSection
0x180001dad  call    DuplicateLibrary
0x180001db2  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180001db9  mov     rsi, rax
0x180001dbc  call    cs:__imp_EnterCriticalSection
0x180001dc2  mov     rax, cs:?pRetrievalPreFetchJobInfo@@3PEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@EA; _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO * pRetrievalPreFetchJobInfo
0x180001dc9  jmp     loc_180001CDE
0x180001dce  mov     ecx, 38h ; '8'; uBytes
0x180001dd3  call    PkiZeroAlloc
0x180001dd8  mov     cs:?pRetrievalPreFetchJobInfo@@3PEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@EA, rax; _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO * pRetrievalPreFetchJobInfo
0x180001ddf  test    rax, rax
0x180001de2  jz      short loc_180001E25
0x180001de4  mov     rcx, rax
0x180001de7  call    Pki_InitializeCriticalSection
0x180001dec  test    eax, eax
0x180001dee  jz      short loc_180001DFC
0x180001df0  mov     rax, cs:?pRetrievalPreFetchJobInfo@@3PEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@EA; _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO * pRetrievalPreFetchJobInfo
0x180001df7  jmp     loc_180001CE7
0x180001dfc  mov     rcx, cs:?pRetrievalPreFetchJobInfo@@3PEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@EA; hMem
0x180001e03  call    PkiFree
0x180001e08  mov     cs:?pRetrievalPreFetchJobInfo@@3PEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@EA, rdi; _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO * pRetrievalPreFetchJobInfo
0x180001e0f  jmp     short loc_180001E25
0x180001e11  test    rsi, rsi
0x180001e14  jnz     short loc_180001E25
0x180001e16  mov     rax, cs:?pRetrievalPreFetchJobInfo@@3PEAU_CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO@@EA; _CUCS_RETRIEVAL_PRE_FETCH_JOB_INFO * pRetrievalPreFetchJobInfo
0x180001e1d  mov     rsi, [rax+30h]
0x180001e21  mov     [rax+30h], rdi
0x180001e25  call    cs:__imp_GetLastError
0x180001e2b  mov     [rbx+78h], eax
0x180001e2e  test    eax, eax
0x180001e30  jnz     short loc_180001E39
0x180001e32  mov     dword ptr [rbx+78h], 8000FFFFh
0x180001e39  xor     r9d, r9d
0x180001e3c  mov     dword ptr [rbx+74h], 4
0x180001e43  xor     r8d, r8d
0x180001e46  mov     edx, 3
0x180001e4b  mov     rcx, rbx
0x180001e4e  call    AddToBeRunJobEx
0x180001e53  jmp     loc_180001D71
0x180001e58  mov     rcx, rsi; hLibModule
0x180001e5b  call    cs:__imp_FreeLibrary
0x180001e61  jmp     loc_180001D91
```
