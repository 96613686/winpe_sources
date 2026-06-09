# CThread::StartThread(ulong)

- ea: `0x180269880`
- end: `0x18026999f`
- name: `?StartThread@CThread@@UEAAJK@Z`
- size: `287`
- prototype: `__int64 __fastcall(CThread *__hidden this, DWORD dwCreationFlags)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180269880`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180269934`
- `KERNEL32!CloseHandle` at `0x180269963`
- `KERNEL32!CloseHandle` at `0x180269934`
- `KERNEL32!CloseHandle` at `0x180269963`
- `KERNEL32!GetLastError` at `0x1802698af`
- `KERNEL32!GetLastError` at `0x180269912`
- `KERNEL32!GetLastError` at `0x18026993e`
- `KERNEL32!GetLastError` at `0x18026996d`
- `KERNEL32!GetLastError` at `0x1802698af`
- `KERNEL32!GetLastError` at `0x180269912`
- `KERNEL32!GetLastError` at `0x18026993e`
- `KERNEL32!GetLastError` at `0x18026996d`
- `KERNEL32!CreateEventW` at `0x1802698a0`
- `KERNEL32!CreateEventW` at `0x1802698d6`
- `KERNEL32!CreateEventW` at `0x1802698a0`
- `KERNEL32!CreateEventW` at `0x1802698d6`
- `KERNEL32!CreateThread` at `0x180269903`
- `KERNEL32!CreateThread` at `0x180269903`

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
0x180269880  mov     [rsp+arg_0], rbx
0x180269885  mov     [rsp+arg_8], rbp
0x18026988a  push    rsi
0x18026988b  sub     rsp, 30h
0x18026988f  xor     r9d, r9d; lpName
0x180269892  mov     ebx, edx
0x180269894  mov     rbp, rcx
0x180269897  xor     r8d, r8d; bInitialState
0x18026989a  xor     ecx, ecx; lpEventAttributes
0x18026989c  lea     edx, [r9+1]; bManualReset
0x1802698a0  call    cs:__imp_CreateEventW
0x1802698a6  mov     [rbp+10h], rax
0x1802698aa  test    rax, rax
0x1802698ad  jnz     short loc_1802698CA
0x1802698af  call    cs:__imp_GetLastError
0x1802698b5  mov     ebx, eax
0x1802698b7  test    eax, eax
0x1802698b9  jle     short loc_1802698C4
0x1802698bb  movzx   ebx, ax
0x1802698be  or      ebx, 80070000h
0x1802698c4  lea     rsi, [rbp+18h]
0x1802698c8  jmp     short loc_180269927
0x1802698ca  xor     r9d, r9d; lpName
0x1802698cd  xor     r8d, r8d; bInitialState
0x1802698d0  xor     ecx, ecx; lpEventAttributes
0x1802698d2  lea     edx, [r9+1]; bManualReset
0x1802698d6  call    cs:__imp_CreateEventW
0x1802698dc  lea     rsi, [rbp+18h]
0x1802698e0  mov     [rsi], rax
0x1802698e3  test    rax, rax
0x1802698e6  jz      short loc_180269912
0x1802698e8  lea     rax, [rbp+20h]
0x1802698ec  mov     r9, rbp; lpParameter
0x1802698ef  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1802698f4  lea     r8, ?staticThreadProc@CThread@@CAKPEAX@Z; lpStartAddress
0x1802698fb  xor     edx, edx; dwStackSize
0x1802698fd  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180269901  xor     ecx, ecx; lpThreadAttributes
0x180269903  call    cs:__imp_CreateThread
0x180269909  mov     [rbp+8], rax
0x18026990d  test    rax, rax
0x180269910  jnz     short loc_18026998B
0x180269912  call    cs:__imp_GetLastError
0x180269918  mov     ebx, eax
0x18026991a  test    eax, eax
0x18026991c  jle     short loc_180269927
0x18026991e  movzx   ebx, ax
0x180269921  or      ebx, 80070000h
0x180269927  test    ebx, ebx
0x180269929  jns     short loc_18026998D
0x18026992b  mov     rcx, [rbp+10h]; hObject
0x18026992f  test    rcx, rcx
0x180269932  jz      short loc_18026995B
0x180269934  call    cs:__imp_CloseHandle
0x18026993a  test    eax, eax
0x18026993c  jnz     short loc_180269953
0x18026993e  call    cs:__imp_GetLastError
0x180269944  mov     ebx, eax
0x180269946  test    eax, eax
0x180269948  jle     short loc_180269953
0x18026994a  movzx   ebx, ax
0x18026994d  or      ebx, 80070000h
0x180269953  mov     qword ptr [rbp+10h], 0
0x18026995b  mov     rcx, [rsi]; hObject
0x18026995e  test    rcx, rcx
0x180269961  jz      short loc_18026998D
0x180269963  call    cs:__imp_CloseHandle
0x180269969  test    eax, eax
0x18026996b  jnz     short loc_180269982
0x18026996d  call    cs:__imp_GetLastError
0x180269973  mov     ebx, eax
0x180269975  test    eax, eax
0x180269977  jle     short loc_180269982
0x180269979  movzx   ebx, ax
0x18026997c  or      ebx, 80070000h
0x180269982  mov     qword ptr [rsi], 0
0x180269989  jmp     short loc_18026998D
0x18026998b  xor     ebx, ebx
0x18026998d  mov     rbp, [rsp+38h+arg_8]
0x180269992  mov     eax, ebx
0x180269994  mov     rbx, [rsp+38h+arg_0]
0x180269999  add     rsp, 30h
0x18026999d  pop     rsi
0x18026999e  retn
```
