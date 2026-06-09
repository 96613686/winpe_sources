# InitExpirePermanentThread

- ea: `0x18004d840`
- end: `0x18004d958`
- name: `InitExpirePermanentThread`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180025c1c`

## callees

- `0x18004d840`

## import_xrefs

- `msvcrt!__doserrno` at `0x18004d8bc`
- `msvcrt!__doserrno` at `0x18004d8bc`
- `msvcrt!_beginthreadex` at `0x18004d8a8`
- `msvcrt!_beginthreadex` at `0x18004d8a8`
- `KERNEL32!GetExitCodeThread` at `0x18004d90c`
- `KERNEL32!GetExitCodeThread` at `0x18004d90c`
- `KERNEL32!WaitForMultipleObjects` at `0x18004d8e8`
- `KERNEL32!WaitForMultipleObjects` at `0x18004d8e8`
- `KERNEL32!CreateEventW` at `0x18004d867`
- `KERNEL32!CreateEventW` at `0x18004d867`
- `KERNEL32!GetLastError` at `0x18004d87b`
- `KERNEL32!GetLastError` at `0x18004d87b`
- `KERNEL32!CloseHandle` at `0x18004d924`
- `KERNEL32!CloseHandle` at `0x18004d938`
- `KERNEL32!CloseHandle` at `0x18004d924`
- `KERNEL32!CloseHandle` at `0x18004d938`

## pseudocode

```c
DWORD InitExpirePermanentThread()
{
  HANDLE EventW; // rdi
  void *v2; // rax
  void *v3; // rbx
  DWORD v4; // eax
  HANDLE Handles[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD ExitCode; // [rsp+50h] [rbp+10h] BYREF
  unsigned int ThrdAddr; // [rsp+58h] [rbp+18h] BYREF

  ThrdAddr = 0;
  *(_OWORD *)Handles = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
    return GetLastError();
  v2 = (void *)_beginthreadex(0, 0, ExpirePermanentThread, EventW, 0, &ThrdAddr);
  v3 = v2;
  if ( v2 )
  {
    Handles[0] = EventW;
    Handles[1] = v2;
    v4 = WaitForMultipleObjects(2u, Handles, 0, 0x7530u);
    ExitCode = v4;
    if ( v4 )
    {
      if ( v4 == 1 )
        GetExitCodeThread(v3, &ExitCode);
      else
        ExitCode = 30;
    }
    else
    {
      ExitCode = 0;
    }
  }
  else
  {
    ExitCode = *__doserrno();
  }
  CloseHandle(EventW);
  if ( v3 )
    CloseHandle(v3);
  return ExitCode;
}

```

## disassembly

```asm
0x18004d840  mov     [rsp-8+arg_10], rbx
0x18004d845  mov     [rsp-8+arg_18], rdi
0x18004d84a  push    rbp
0x18004d84b  mov     rbp, rsp
0x18004d84e  sub     rsp, 40h
0x18004d852  and     [rbp+arg_8], 0
0x18004d856  xorps   xmm0, xmm0
0x18004d859  xor     r9d, r9d; lpName
0x18004d85c  xor     r8d, r8d; bInitialState
0x18004d85f  xor     edx, edx; bManualReset
0x18004d861  xor     ecx, ecx; lpEventAttributes
0x18004d863  movups  xmmword ptr [rbp+Handles], xmm0
0x18004d867  call    cs:__imp_CreateEventW
0x18004d86e  nop     dword ptr [rax+rax+00h]
0x18004d873  mov     rdi, rax
0x18004d876  test    rax, rax
0x18004d879  jnz     short loc_18004D88C
0x18004d87b  call    cs:__imp_GetLastError
0x18004d882  nop     dword ptr [rax+rax+00h]
0x18004d887  jmp     loc_18004D947
0x18004d88c  lea     rax, [rbp+arg_8]
0x18004d890  mov     r9, rdi; ArgList
0x18004d893  mov     [rsp+40h+ThrdAddr], rax; ThrdAddr
0x18004d898  lea     r8, ?ExpirePermanentThread@@YAIPEAX@Z; StartAddress
0x18004d89f  and     [rsp+40h+var_20], 0
0x18004d8a4  xor     edx, edx; StackSize
0x18004d8a6  xor     ecx, ecx; Security
0x18004d8a8  call    cs:__imp__beginthreadex
0x18004d8af  nop     dword ptr [rax+rax+00h]
0x18004d8b4  mov     rbx, rax
0x18004d8b7  test    rax, rax
0x18004d8ba  jnz     short loc_18004D8CF
0x18004d8bc  call    cs:__imp___doserrno
0x18004d8c3  nop     dword ptr [rax+rax+00h]
0x18004d8c8  mov     ecx, [rax]
0x18004d8ca  mov     [rbp+ExitCode], ecx
0x18004d8cd  jmp     short loc_18004D921
0x18004d8cf  xor     r8d, r8d; bWaitAll
0x18004d8d2  mov     [rbp+Handles], rdi
0x18004d8d6  mov     r9d, 7530h; dwMilliseconds
0x18004d8dc  mov     [rbp+Handles+8], rbx
0x18004d8e0  lea     rdx, [rbp+Handles]; lpHandles
0x18004d8e4  lea     ecx, [r8+2]; nCount
0x18004d8e8  call    cs:__imp_WaitForMultipleObjects
0x18004d8ef  nop     dword ptr [rax+rax+00h]
0x18004d8f4  mov     [rbp+ExitCode], eax
0x18004d8f7  test    eax, eax
0x18004d8f9  jnz     short loc_18004D900
0x18004d8fb  and     [rbp+ExitCode], eax
0x18004d8fe  jmp     short loc_18004D921
0x18004d900  cmp     eax, 1
0x18004d903  jnz     short loc_18004D91A
0x18004d905  lea     rdx, [rbp+ExitCode]; lpExitCode
0x18004d909  mov     rcx, rbx; hThread
0x18004d90c  call    cs:__imp_GetExitCodeThread
0x18004d913  nop     dword ptr [rax+rax+00h]
0x18004d918  jmp     short loc_18004D921
0x18004d91a  mov     [rbp+ExitCode], 1Eh
0x18004d921  mov     rcx, rdi; hObject
0x18004d924  call    cs:__imp_CloseHandle
0x18004d92b  nop     dword ptr [rax+rax+00h]
0x18004d930  test    rbx, rbx
0x18004d933  jz      short loc_18004D944
0x18004d935  mov     rcx, rbx; hObject
0x18004d938  call    cs:__imp_CloseHandle
0x18004d93f  nop     dword ptr [rax+rax+00h]
0x18004d944  mov     eax, [rbp+ExitCode]
0x18004d947  mov     rbx, [rsp+40h+arg_10]
0x18004d94c  mov     rdi, [rsp+40h+arg_18]
0x18004d951  add     rsp, 40h
0x18004d955  pop     rbp
0x18004d956  retn
```
