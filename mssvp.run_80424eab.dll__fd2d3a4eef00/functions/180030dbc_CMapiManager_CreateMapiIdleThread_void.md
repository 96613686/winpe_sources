# CMapiManager::CreateMapiIdleThread(void)

- ea: `0x180030dbc`
- end: `0x180030e67`
- name: `?CreateMapiIdleThread@CMapiManager@@AEAAJXZ`
- size: `171`
- prototype: `__int64 __fastcall(CMapiManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180031828`

## callees

- `0x18000557c`
- `0x180030dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e3a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180030e28`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180030e28`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030de7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030de7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180030e4c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180030e4c`

## pseudocode

```c
DWORD __fastcall CMapiManager::CreateMapiIdleThread(CMapiManager *this)
{
  DWORD result; // eax
  HANDLE EventW; // rax
  HANDLE v4; // rax
  bool v5; // zf
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 32) == 1 )
    return 0;
  *((_DWORD *)this + 32) = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 23) = EventW;
  if ( !EventW )
    return ResultFromLastError();
  ThreadId = 0;
  v4 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)MapiIdleThreadMain, this, 0, &ThreadId);
  *((_QWORD *)this + 22) = v4;
  if ( !v4 )
    return GetLastError();
  v5 = WaitForSingleObject(*((HANDLE *)this + 23), 0xFFFFFFFF) == 0;
  result = -2147467259;
  if ( v5 )
    return *((_DWORD *)this + 48);
  return result;
}

```

## disassembly

```asm
0x180030dbc  push    rbx
0x180030dbe  sub     rsp, 30h
0x180030dc2  mov     edx, 1; bManualReset
0x180030dc7  mov     rbx, rcx
0x180030dca  cmp     [rcx+80h], edx
0x180030dd0  jnz     short loc_180030DD9
0x180030dd2  xor     eax, eax
0x180030dd4  jmp     loc_180030E61
0x180030dd9  mov     [rcx+80h], edx
0x180030ddf  xor     r9d, r9d; lpName
0x180030de2  xor     ecx, ecx; lpEventAttributes
0x180030de4  xor     r8d, r8d; bInitialState
0x180030de7  call    cs:__imp_CreateEventW
0x180030ded  mov     [rbx+0B8h], rax
0x180030df4  test    rax, rax
0x180030df7  jnz     short loc_180030E00
0x180030df9  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180030dfe  jmp     short loc_180030E61
0x180030e00  lea     rax, [rsp+38h+ThreadId]
0x180030e05  mov     [rsp+38h+ThreadId], 0
0x180030e0d  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180030e12  lea     r8, ?MapiIdleThreadMain@@YAKPEAX@Z; lpStartAddress
0x180030e19  mov     r9, rbx; lpParameter
0x180030e1c  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180030e24  xor     edx, edx; dwStackSize
0x180030e26  xor     ecx, ecx; lpThreadAttributes
0x180030e28  call    cs:__imp_CreateThread
0x180030e2e  mov     [rbx+0B0h], rax
0x180030e35  test    rax, rax
0x180030e38  jnz     short loc_180030E42
0x180030e3a  call    cs:__imp_GetLastError
0x180030e40  jmp     short loc_180030E61
0x180030e42  mov     rcx, [rbx+0B8h]; hHandle
0x180030e49  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180030e4c  call    cs:__imp_WaitForSingleObject
0x180030e52  test    eax, eax
0x180030e54  mov     eax, 80004005h
0x180030e59  jnz     short loc_180030E61
0x180030e5b  mov     eax, [rbx+0C0h]
0x180030e61  add     rsp, 30h
0x180030e65  pop     rbx
0x180030e66  retn
```
