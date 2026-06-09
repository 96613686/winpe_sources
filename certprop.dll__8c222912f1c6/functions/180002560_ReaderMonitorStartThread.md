# ReaderMonitorStartThread

- ea: `0x180002560`
- end: `0x1800025fb`
- name: `ReaderMonitorStartThread`
- size: `155`
- prototype: `DWORD __fastcall(char *lpParameter)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ee0`
- `0x18000ec48`

## callees

- `0x180002560`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180002574`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180002574`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800025a8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800025a8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800025cc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800025cc`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800025db`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800025db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000257e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000257e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800025e6`

## pseudocode

```c
DWORD __fastcall ReaderMonitorStartThread(char *lpParameter)
{
  HANDLE Thread; // rax
  HANDLE *v4; // rdi
  int v5; // ebx

  if ( !ResetEvent(*((HANDLE *)lpParameter + 30)) )
    return GetLastError();
  Thread = CreateThread(
             0,
             0,
             (LPTHREAD_START_ROUTINE)I_ReaderMonitorThreadProc,
             lpParameter,
             4u,
             (LPDWORD)lpParameter + 55);
  v4 = (HANDLE *)(lpParameter + 224);
  *((_QWORD *)lpParameter + 28) = Thread;
  if ( !Thread )
    return GetLastError();
  if ( *(_DWORD *)lpParameter && !SetThreadToken((PHANDLE)lpParameter + 28, *((HANDLE *)lpParameter + 31)) )
    return GetLastError();
  v5 = 0;
  if ( ResumeThread(*v4) == -1 )
    return GetLastError();
  return v5;
}

```

## disassembly

```asm
0x180002560  mov     [rsp+arg_0], rbx
0x180002565  push    rdi
0x180002566  sub     rsp, 30h
0x18000256a  mov     rbx, rcx
0x18000256d  mov     rcx, [rcx+0F0h]; hEvent
0x180002574  call    cs:__imp_ResetEvent
0x18000257a  test    eax, eax
0x18000257c  jnz     short loc_180002586
0x18000257e  call    cs:__imp_GetLastError
0x180002584  jmp     short loc_1800025F0
0x180002586  lea     rax, [rbx+0DCh]
0x18000258d  mov     r9, rbx; lpParameter
0x180002590  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180002595  lea     r8, I_ReaderMonitorThreadProc; lpStartAddress
0x18000259c  xor     edx, edx; dwStackSize
0x18000259e  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1800025a6  xor     ecx, ecx; lpThreadAttributes
0x1800025a8  call    cs:__imp_CreateThread
0x1800025ae  lea     rdi, [rbx+0E0h]
0x1800025b5  mov     [rdi], rax
0x1800025b8  test    rax, rax
0x1800025bb  jz      short loc_18000257E
0x1800025bd  cmp     dword ptr [rbx], 0
0x1800025c0  jz      short loc_1800025D6
0x1800025c2  mov     rdx, [rbx+0F8h]; Token
0x1800025c9  mov     rcx, rdi; Thread
0x1800025cc  call    cs:__imp_SetThreadToken
0x1800025d2  test    eax, eax
0x1800025d4  jz      short loc_1800025E6
0x1800025d6  mov     rcx, [rdi]; hThread
0x1800025d9  xor     ebx, ebx
0x1800025db  call    cs:__imp_ResumeThread
0x1800025e1  cmp     eax, 0FFFFFFFFh
0x1800025e4  jnz     short loc_1800025EE
0x1800025e6  call    cs:__imp_GetLastError
0x1800025ec  mov     ebx, eax
0x1800025ee  mov     eax, ebx
0x1800025f0  mov     rbx, [rsp+38h+arg_0]
0x1800025f5  add     rsp, 30h
0x1800025f9  pop     rdi
0x1800025fa  retn
```
