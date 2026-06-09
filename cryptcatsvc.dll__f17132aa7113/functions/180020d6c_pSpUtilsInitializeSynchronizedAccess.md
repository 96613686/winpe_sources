# _pSpUtilsInitializeSynchronizedAccess

- ea: `0x180020d6c`
- end: `0x180020dee`
- name: `_pSpUtilsInitializeSynchronizedAccess`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002078c`

## callees

- `0x180020d6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020d8c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020d8c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180020da1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180020da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020db4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020db4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020dce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020dce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020dbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020dbf`

## pseudocode

```c
__int64 __fastcall pSpUtilsInitializeSynchronizedAccess(__int64 a1)
{
  HANDLE EventW; // rax
  HANDLE MutexW; // rax
  DWORD LastError; // ebx

  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)a1 = EventW;
  if ( EventW )
  {
    MutexW = CreateMutexW(0, 0, 0);
    *(_QWORD *)(a1 + 8) = MutexW;
    if ( MutexW )
      return 1;
    LastError = GetLastError();
    CloseHandle(*(HANDLE *)a1);
    *(_QWORD *)a1 = 0;
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 8) = 0;
  return 0;
}

```

## disassembly

```asm
0x180020d6c  mov     [rsp+arg_0], rbx
0x180020d71  mov     [rsp+arg_8], rsi
0x180020d76  push    rdi
0x180020d77  sub     rsp, 20h
0x180020d7b  xor     r9d, r9d; lpName
0x180020d7e  mov     rsi, rcx
0x180020d81  xor     r8d, r8d; bInitialState
0x180020d84  xor     ecx, ecx; lpEventAttributes
0x180020d86  lea     ebx, [r9+1]
0x180020d8a  mov     edx, ebx; bManualReset
0x180020d8c  call    cs:__imp_CreateEventW
0x180020d92  mov     [rsi], rax
0x180020d95  test    rax, rax
0x180020d98  jz      short loc_180020DD4
0x180020d9a  xor     r8d, r8d; lpName
0x180020d9d  xor     edx, edx; bInitialOwner
0x180020d9f  xor     ecx, ecx; lpMutexAttributes
0x180020da1  call    cs:__imp_CreateMutexW
0x180020da7  mov     [rsi+8], rax
0x180020dab  test    rax, rax
0x180020dae  jz      short loc_180020DB4
0x180020db0  mov     eax, ebx
0x180020db2  jmp     short loc_180020DDE
0x180020db4  call    cs:__imp_GetLastError
0x180020dba  mov     rcx, [rsi]; hObject
0x180020dbd  mov     ebx, eax
0x180020dbf  call    cs:__imp_CloseHandle
0x180020dc5  mov     ecx, ebx; dwErrCode
0x180020dc7  mov     qword ptr [rsi], 0
0x180020dce  call    cs:__imp_SetLastError
0x180020dd4  mov     qword ptr [rsi+8], 0
0x180020ddc  xor     eax, eax
0x180020dde  mov     rbx, [rsp+28h+arg_0]
0x180020de3  mov     rsi, [rsp+28h+arg_8]
0x180020de8  add     rsp, 20h
0x180020dec  pop     rdi
0x180020ded  retn
```
