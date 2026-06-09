# StartPerflibFunctionTimer(OPEN_PROC_WAIT_INFO *)

- ea: `0x18000c424`
- end: `0x18000c6ec`
- name: `?StartPerflibFunctionTimer@@YAPEAXPEAUOPEN_PROC_WAIT_INFO@@@Z`
- size: `712`
- prototype: `unsigned __int16 *__fastcall(struct OPEN_PROC_WAIT_INFO *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011d10`
- `0x1800136b0`
- `0x18001403c`

## callees

- `0x180005da0`
- `0x1800070d0`
- `0x18000ac80`
- `0x18000bef8`
- `0x18000c424`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x18000c667`
- `ntdll!NtWaitForSingleObject` at `0x18000c667`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c477`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c4a6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c477`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000c4a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c51a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000c51a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c6d2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c6d2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000c4d0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000c4d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c6c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c6c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c449`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c57c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c57c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c52d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c52d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c56a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c56a`

## pseudocode

```c
unsigned __int16 *__fastcall StartPerflibFunctionTimer(struct OPEN_PROC_WAIT_INFO *a1)
{
  __int64 v2; // rbp
  DWORD LastError; // ebx
  DWORD v4; // ecx
  HANDLE MutexW; // rax
  __int64 *v7; // rdx
  __int64 *v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  unsigned int v12; // r14d
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rdi
  unsigned __int16 *v15; // rcx
  unsigned int v16; // edx
  NTSTATUS v17; // eax
  ULONG v18; // eax
  union _LARGE_INTEGER Timeout; // [rsp+70h] [rbp+8h] BYREF

  Timeout.QuadPart = 0;
  v2 = 0;
  if ( !a1 )
  {
    LastError = 87;
LABEL_3:
    v4 = LastError;
LABEL_4:
    SetLastError(v4);
    return (unsigned __int16 *)v2;
  }
  LastError = 0;
  if ( !Object[0] )
  {
    Object[0] = CreateEventW(0, 1, 0, 0);
    if ( !Object[0] )
      LastError = GetLastError();
  }
  if ( !hEvent )
  {
    hEvent = CreateEventW(0, 1, 0, 0);
    if ( !hEvent )
      LastError = GetLastError();
  }
  if ( !Handle )
  {
    MutexW = CreateMutexW(0, 0, 0);
    if ( MutexW )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&Handle, (signed __int64)MutexW, 0) )
        CloseHandle(MutexW);
      else
        Handle = MutexW;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  if ( LastError )
    goto LABEL_3;
  if ( !hObject )
    goto LABEL_25;
  LastError = WaitForSingleObject(hObject, 0);
  if ( !LastError )
  {
    CloseHandle(hObject);
    hObject = 0;
    LastError = 0;
LABEL_25:
    hObject = CreateThread(0, 0, PerflibTimerFunction, 0, 0, 0);
    if ( !hObject )
      LastError = GetLastError();
    goto LABEL_27;
  }
  if ( LastError == 258 )
    LastError = 0;
  if ( !hObject )
    goto LABEL_25;
LABEL_27:
  if ( LastError )
    goto LABEL_3;
  v7 = &qword_180023510;
  v8 = &qword_180023510;
  if ( *((_QWORD *)a1 + 1) )
    v8 = (__int64 *)*((_QWORD *)a1 + 1);
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( *((_WORD *)v8 + v10) );
  v11 = (unsigned int)(2 * v10 + 2);
  if ( *((_QWORD *)a1 + 2) )
    v7 = (__int64 *)*((_QWORD *)a1 + 2);
  do
    ++v9;
  while ( *((_WORD *)v7 + v9) );
  v12 = 2 * v9 + 2;
  v13 = (unsigned __int16 *)operator new(((_DWORD)v11 + 2 * (_DWORD)v9 + 49) & 0xFFFFFFF8);
  v14 = v13;
  if ( !v13 )
  {
    LastError = 14;
    goto LABEL_3;
  }
  *((_QWORD *)v13 + 1) = v13 + 20;
  StringCbCopyW(v13 + 20, v11, *((const unsigned __int16 **)a1 + 1));
  v15 = (unsigned __int16 *)(v11 + *((_QWORD *)v14 + 1));
  *((_QWORD *)v14 + 2) = v15;
  StringCbCopyW(v15, v12, *((const unsigned __int16 **)a1 + 2));
  v16 = *((_DWORD *)a1 + 6) / 0xC8u;
  *((_DWORD *)v14 + 6) = v16;
  if ( !v16 )
    *((_DWORD *)v14 + 6) = 1;
  *((_DWORD *)v14 + 7) = *((_DWORD *)a1 + 7);
  *((_QWORD *)v14 + 4) = *((_QWORD *)a1 + 4);
  if ( !Handle )
  {
    v18 = 21;
    goto LABEL_48;
  }
  Timeout.QuadPart = -4000000;
  v17 = NtWaitForSingleObject(Handle, 0, &Timeout);
  v18 = PerfpDosError(v17);
  if ( v18 )
  {
LABEL_48:
    v4 = v18;
    goto LABEL_4;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids,
      v14,
      *((_DWORD *)v14 + 6));
  *(_QWORD *)v14 = Block;
  Block = v14;
  ReleaseMutex(Handle);
  if ( !*(_QWORD *)v14 )
    SetEvent(Object[0]);
  return v14;
}

```

## disassembly

```asm
0x18000c424  push    rbx
0x18000c426  push    rbp
0x18000c427  push    rsi
0x18000c428  push    rdi
0x18000c429  push    r14
0x18000c42b  push    r15
0x18000c42d  sub     rsp, 38h
0x18000c431  xor     r15d, r15d
0x18000c434  mov     rsi, rcx
0x18000c437  mov     qword ptr [rsp+68h+Timeout], r15
0x18000c43c  mov     ebp, r15d
0x18000c43f  test    rcx, rcx
0x18000c442  jnz     short loc_18000C45F
0x18000c444  lea     ebx, [rcx+57h]
0x18000c447  mov     ecx, ebx; dwErrCode
0x18000c449  call    cs:__imp_SetLastError
0x18000c44f  mov     rax, rbp
0x18000c452  add     rsp, 38h
0x18000c456  pop     r15
0x18000c458  pop     r14
0x18000c45a  pop     rdi
0x18000c45b  pop     rsi
0x18000c45c  pop     rbp
0x18000c45d  pop     rbx
0x18000c45e  retn
0x18000c45f  cmp     cs:Object, r15
0x18000c466  mov     ebx, r15d
0x18000c469  jnz     short loc_18000C491
0x18000c46b  xor     r9d, r9d; lpName
0x18000c46e  xor     r8d, r8d; bInitialState
0x18000c471  xor     ecx, ecx; lpEventAttributes
0x18000c473  lea     edx, [r9+1]; bManualReset
0x18000c477  call    cs:__imp_CreateEventW
0x18000c47d  mov     cs:Object, rax
0x18000c484  test    rax, rax
0x18000c487  jnz     short loc_18000C491
0x18000c489  call    cs:__imp_GetLastError
0x18000c48f  mov     ebx, eax
0x18000c491  cmp     cs:hEvent, r15
0x18000c498  jnz     short loc_18000C4C0
0x18000c49a  xor     r9d, r9d; lpName
0x18000c49d  xor     r8d, r8d; bInitialState
0x18000c4a0  xor     ecx, ecx; lpEventAttributes
0x18000c4a2  lea     edx, [r9+1]; bManualReset
0x18000c4a6  call    cs:__imp_CreateEventW
0x18000c4ac  mov     cs:hEvent, rax
0x18000c4b3  test    rax, rax
0x18000c4b6  jnz     short loc_18000C4C0
0x18000c4b8  call    cs:__imp_GetLastError
0x18000c4be  mov     ebx, eax
0x18000c4c0  cmp     cs:Handle, r15
0x18000c4c7  jnz     short loc_18000C504
0x18000c4c9  xor     r8d, r8d; lpName
0x18000c4cc  xor     edx, edx; bInitialOwner
0x18000c4ce  xor     ecx, ecx; lpMutexAttributes
0x18000c4d0  call    cs:__imp_CreateMutexW
0x18000c4d6  mov     rcx, rax; hObject
0x18000c4d9  test    rax, rax
0x18000c4dc  jnz     short loc_18000C4E8
0x18000c4de  call    cs:__imp_GetLastError
0x18000c4e4  mov     ebx, eax
0x18000c4e6  jmp     short loc_18000C504
0x18000c4e8  xor     eax, eax
0x18000c4ea  lock cmpxchg cs:Handle, rcx
0x18000c4f3  jz      short loc_18000C4FD
0x18000c4f5  call    cs:__imp_CloseHandle
0x18000c4fb  jmp     short loc_18000C504
0x18000c4fd  mov     cs:Handle, rcx
0x18000c504  test    ebx, ebx
0x18000c506  jnz     loc_18000C447
0x18000c50c  mov     rcx, cs:hObject; hHandle
0x18000c513  test    rcx, rcx
0x18000c516  jz      short loc_18000C552
0x18000c518  xor     edx, edx; dwMilliseconds
0x18000c51a  call    cs:__imp_WaitForSingleObject
0x18000c520  mov     ebx, eax
0x18000c522  test    eax, eax
0x18000c524  jnz     short loc_18000C53F
0x18000c526  mov     rcx, cs:hObject; hObject
0x18000c52d  call    cs:__imp_CloseHandle
0x18000c533  mov     cs:hObject, r15
0x18000c53a  mov     ebx, r15d
0x18000c53d  jmp     short loc_18000C552
0x18000c53f  cmp     ebx, 102h
0x18000c545  cmovz   ebx, r15d
0x18000c549  cmp     cs:hObject, r15
0x18000c550  jnz     short loc_18000C584
0x18000c552  mov     [rsp+68h+lpThreadId], r15; lpThreadId
0x18000c557  lea     r8, ?PerflibTimerFunction@@YAKPEAK@Z; lpStartAddress
0x18000c55e  xor     r9d, r9d; lpParameter
0x18000c561  mov     [rsp+68h+dwCreationFlags], r15d; dwCreationFlags
0x18000c566  xor     edx, edx; dwStackSize
0x18000c568  xor     ecx, ecx; lpThreadAttributes
0x18000c56a  call    cs:__imp_CreateThread
0x18000c570  mov     cs:hObject, rax
0x18000c577  test    rax, rax
0x18000c57a  jnz     short loc_18000C584
0x18000c57c  call    cs:__imp_GetLastError
0x18000c582  mov     ebx, eax
0x18000c584  test    ebx, ebx
0x18000c586  jnz     loc_18000C447
0x18000c58c  cmp     [rsi+8], r15
0x18000c590  lea     rdx, qword_180023510
0x18000c597  mov     r8, rdx
0x18000c59a  cmovnz  r8, [rsi+8]
0x18000c59f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c5a3  mov     rcx, rax
0x18000c5a6  inc     rcx
0x18000c5a9  cmp     [r8+rcx*2], r15w
0x18000c5ae  jnz     short loc_18000C5A6
0x18000c5b0  cmp     [rsi+10h], r15
0x18000c5b4  lea     ebx, ds:2[rcx*2]
0x18000c5bb  cmovnz  rdx, [rsi+10h]
0x18000c5c0  inc     rax
0x18000c5c3  cmp     [rdx+rax*2], r15w
0x18000c5c8  jnz     short loc_18000C5C0
0x18000c5ca  lea     r14d, ds:2[rax*2]
0x18000c5d2  mov     eax, 0FFFFFFF8h
0x18000c5d7  lea     ecx, [r14+2Fh]
0x18000c5db  add     ecx, ebx
0x18000c5dd  and     rcx, rax
0x18000c5e0  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18000c5e5  mov     rdi, rax
0x18000c5e8  test    rax, rax
0x18000c5eb  jnz     short loc_18000C5F5
0x18000c5ed  lea     ebx, [rax+0Eh]
0x18000c5f0  jmp     loc_18000C447
0x18000c5f5  lea     rcx, [rax+28h]; unsigned __int16 *
0x18000c5f9  mov     rdx, rbx; unsigned __int64
0x18000c5fc  mov     [rax+8], rcx
0x18000c600  mov     r8, [rsi+8]; unsigned __int16 *
0x18000c604  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c609  mov     rcx, [rdi+8]
0x18000c60d  add     rcx, rbx; unsigned __int16 *
0x18000c610  mov     edx, r14d; unsigned __int64
0x18000c613  mov     [rdi+10h], rcx
0x18000c617  mov     r8, [rsi+10h]; unsigned __int16 *
0x18000c61b  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c620  mov     eax, 51EB851Fh
0x18000c625  mul     dword ptr [rsi+18h]
0x18000c628  shr     edx, 6
0x18000c62b  mov     [rdi+18h], edx
0x18000c62e  test    edx, edx
0x18000c630  jnz     short loc_18000C639
0x18000c632  mov     dword ptr [rdi+18h], 1
0x18000c639  mov     eax, [rsi+1Ch]
0x18000c63c  mov     [rdi+1Ch], eax
0x18000c63f  mov     rax, [rsi+20h]
0x18000c643  mov     [rdi+20h], rax
0x18000c647  mov     rcx, cs:Handle; Handle
0x18000c64e  test    rcx, rcx
0x18000c651  jz      loc_18000C6E0
0x18000c657  lea     r8, [rsp+68h+Timeout]; Timeout
0x18000c65c  mov     qword ptr [rsp+68h+Timeout], 0FFFFFFFFFFC2F700h
0x18000c665  xor     edx, edx; Alertable
0x18000c667  call    cs:__imp_NtWaitForSingleObject
0x18000c66d  mov     ecx, eax; int
0x18000c66f  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x18000c674  test    eax, eax
0x18000c676  jnz     short loc_18000C6E5
0x18000c678  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c67f  test    byte ptr [rcx+1Ch], 40h
0x18000c683  jz      short loc_18000C6A8
0x18000c685  cmp     byte ptr [rcx+19h], 4
0x18000c689  jb      short loc_18000C6A8
0x18000c68b  mov     rcx, [rcx+10h]
0x18000c68f  lea     edx, [rax+16h]
0x18000c692  mov     eax, [rdi+18h]
0x18000c695  lea     r8, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids
0x18000c69c  mov     r9, rdi
0x18000c69f  mov     [rsp+68h+dwCreationFlags], eax
0x18000c6a3  call    WPP_SF_qd
0x18000c6a8  mov     rax, cs:Block
0x18000c6af  mov     [rdi], rax
0x18000c6b2  mov     rcx, cs:Handle; hMutex
0x18000c6b9  mov     cs:Block, rdi
0x18000c6c0  call    cs:__imp_ReleaseMutex
0x18000c6c6  cmp     [rdi], r15
0x18000c6c9  jnz     short loc_18000C6D8
0x18000c6cb  mov     rcx, cs:Object; hEvent
0x18000c6d2  call    cs:__imp_SetEvent
0x18000c6d8  mov     rbp, rdi
0x18000c6db  jmp     loc_18000C44F
0x18000c6e0  mov     eax, 15h
0x18000c6e5  mov     ecx, eax
0x18000c6e7  jmp     loc_18000C449
```
