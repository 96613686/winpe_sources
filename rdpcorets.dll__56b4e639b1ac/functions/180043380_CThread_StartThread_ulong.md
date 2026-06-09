# CThread::StartThread(ulong)

- ea: `0x180043380`
- end: `0x18004349f`
- name: `?StartThread@CThread@@UEAAJK@Z`
- size: `287`
- prototype: `__int64 __fastcall(CThread *__hidden this, DWORD dwCreationFlags)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180043380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800433a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800433d6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800433a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800433d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800433af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004343e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004346d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800433af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004343e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004346d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180043403`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180043403`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043434`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043463`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043434`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043463`

## pseudocode

```c
__int64 __fastcall CThread::StartThread(CThread *this, DWORD dwCreationFlags)
{
  HANDLE EventW; // rax
  signed int v5; // eax
  signed int v6; // ebx
  HANDLE *v7; // rsi
  HANDLE v8; // rax
  HANDLE Thread; // rax
  signed int LastError; // eax
  void *v11; // rcx
  signed int v12; // eax
  signed int v13; // eax

  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 2) = EventW;
  if ( EventW )
  {
    v8 = CreateEventW(0, 1, 0, 0);
    v7 = (HANDLE *)((char *)this + 24);
    *((_QWORD *)this + 3) = v8;
    if ( v8 )
    {
      Thread = CreateThread(0, 0, CThread::staticThreadProc, this, dwCreationFlags, (LPDWORD)this + 8);
      *((_QWORD *)this + 1) = Thread;
      if ( Thread )
        return 0;
    }
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v7 = (HANDLE *)((char *)this + 24);
  }
  if ( v6 < 0 )
  {
    v11 = (void *)*((_QWORD *)this + 2);
    if ( v11 )
    {
      if ( !CloseHandle(v11) )
      {
        v12 = GetLastError();
        v6 = v12;
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
      }
      *((_QWORD *)this + 2) = 0;
    }
    if ( *v7 )
    {
      if ( !CloseHandle(*v7) )
      {
        v13 = GetLastError();
        v6 = v13;
        if ( v13 > 0 )
          v6 = (unsigned __int16)v13 | 0x80070000;
      }
      *v7 = 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180043380  mov     [rsp+arg_0], rbx
0x180043385  mov     [rsp+arg_8], rbp
0x18004338a  push    rsi
0x18004338b  sub     rsp, 30h
0x18004338f  xor     r9d, r9d; lpName
0x180043392  mov     ebx, edx
0x180043394  mov     rbp, rcx
0x180043397  xor     r8d, r8d; bInitialState
0x18004339a  xor     ecx, ecx; lpEventAttributes
0x18004339c  lea     edx, [r9+1]; bManualReset
0x1800433a0  call    cs:__imp_CreateEventW
0x1800433a6  mov     [rbp+10h], rax
0x1800433aa  test    rax, rax
0x1800433ad  jnz     short loc_1800433CA
0x1800433af  call    cs:__imp_GetLastError
0x1800433b5  mov     ebx, eax
0x1800433b7  test    eax, eax
0x1800433b9  jle     short loc_1800433C4
0x1800433bb  movzx   ebx, ax
0x1800433be  or      ebx, 80070000h
0x1800433c4  lea     rsi, [rbp+18h]
0x1800433c8  jmp     short loc_180043427
0x1800433ca  xor     r9d, r9d; lpName
0x1800433cd  xor     r8d, r8d; bInitialState
0x1800433d0  xor     ecx, ecx; lpEventAttributes
0x1800433d2  lea     edx, [r9+1]; bManualReset
0x1800433d6  call    cs:__imp_CreateEventW
0x1800433dc  lea     rsi, [rbp+18h]
0x1800433e0  mov     [rsi], rax
0x1800433e3  test    rax, rax
0x1800433e6  jz      short loc_180043412
0x1800433e8  lea     rax, [rbp+20h]
0x1800433ec  mov     r9, rbp; lpParameter
0x1800433ef  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800433f4  lea     r8, ?staticThreadProc@CThread@@CAKPEAX@Z; lpStartAddress
0x1800433fb  xor     edx, edx; dwStackSize
0x1800433fd  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180043401  xor     ecx, ecx; lpThreadAttributes
0x180043403  call    cs:__imp_CreateThread
0x180043409  mov     [rbp+8], rax
0x18004340d  test    rax, rax
0x180043410  jnz     short loc_18004348B
0x180043412  call    cs:__imp_GetLastError
0x180043418  mov     ebx, eax
0x18004341a  test    eax, eax
0x18004341c  jle     short loc_180043427
0x18004341e  movzx   ebx, ax
0x180043421  or      ebx, 80070000h
0x180043427  test    ebx, ebx
0x180043429  jns     short loc_18004348D
0x18004342b  mov     rcx, [rbp+10h]; hObject
0x18004342f  test    rcx, rcx
0x180043432  jz      short loc_18004345B
0x180043434  call    cs:__imp_CloseHandle
0x18004343a  test    eax, eax
0x18004343c  jnz     short loc_180043453
0x18004343e  call    cs:__imp_GetLastError
0x180043444  mov     ebx, eax
0x180043446  test    eax, eax
0x180043448  jle     short loc_180043453
0x18004344a  movzx   ebx, ax
0x18004344d  or      ebx, 80070000h
0x180043453  mov     qword ptr [rbp+10h], 0
0x18004345b  mov     rcx, [rsi]; hObject
0x18004345e  test    rcx, rcx
0x180043461  jz      short loc_18004348D
0x180043463  call    cs:__imp_CloseHandle
0x180043469  test    eax, eax
0x18004346b  jnz     short loc_180043482
0x18004346d  call    cs:__imp_GetLastError
0x180043473  mov     ebx, eax
0x180043475  test    eax, eax
0x180043477  jle     short loc_180043482
0x180043479  movzx   ebx, ax
0x18004347c  or      ebx, 80070000h
0x180043482  mov     qword ptr [rsi], 0
0x180043489  jmp     short loc_18004348D
0x18004348b  xor     ebx, ebx
0x18004348d  mov     rbp, [rsp+38h+arg_8]
0x180043492  mov     eax, ebx
0x180043494  mov     rbx, [rsp+38h+arg_0]
0x180043499  add     rsp, 30h
0x18004349d  pop     rsi
0x18004349e  retn
```
