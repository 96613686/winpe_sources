# InitNamedPipeThread

- ea: `0x180026fe4`
- end: `0x1800270fc`
- name: `InitNamedPipeThread`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180025c1c`

## callees

- `0x180026fe4`

## import_xrefs

- `msvcrt!__doserrno` at `0x180027060`
- `msvcrt!__doserrno` at `0x180027060`
- `msvcrt!_beginthreadex` at `0x18002704c`
- `msvcrt!_beginthreadex` at `0x18002704c`
- `KERNEL32!GetExitCodeThread` at `0x1800270b0`
- `KERNEL32!GetExitCodeThread` at `0x1800270b0`
- `KERNEL32!WaitForMultipleObjects` at `0x18002708c`
- `KERNEL32!WaitForMultipleObjects` at `0x18002708c`
- `KERNEL32!CreateEventW` at `0x18002700b`
- `KERNEL32!CreateEventW` at `0x18002700b`
- `KERNEL32!GetLastError` at `0x18002701f`
- `KERNEL32!GetLastError` at `0x18002701f`
- `KERNEL32!CloseHandle` at `0x1800270c8`
- `KERNEL32!CloseHandle` at `0x1800270dc`
- `KERNEL32!CloseHandle` at `0x1800270c8`
- `KERNEL32!CloseHandle` at `0x1800270dc`

## pseudocode

```c
DWORD InitNamedPipeThread()
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
  v2 = (void *)_beginthreadex(0, 0, (_beginthreadex_proc_type)NamedPipeThread, EventW, 0, &ThrdAddr);
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
0x180026fe4  mov     [rsp-8+arg_10], rbx
0x180026fe9  mov     [rsp-8+arg_18], rdi
0x180026fee  push    rbp
0x180026fef  mov     rbp, rsp
0x180026ff2  sub     rsp, 40h
0x180026ff6  and     [rbp+arg_8], 0
0x180026ffa  xorps   xmm0, xmm0
0x180026ffd  xor     r9d, r9d; lpName
0x180027000  xor     r8d, r8d; bInitialState
0x180027003  xor     edx, edx; bManualReset
0x180027005  xor     ecx, ecx; lpEventAttributes
0x180027007  movups  xmmword ptr [rbp+Handles], xmm0
0x18002700b  call    cs:__imp_CreateEventW
0x180027012  nop     dword ptr [rax+rax+00h]
0x180027017  mov     rdi, rax
0x18002701a  test    rax, rax
0x18002701d  jnz     short loc_180027030
0x18002701f  call    cs:__imp_GetLastError
0x180027026  nop     dword ptr [rax+rax+00h]
0x18002702b  jmp     loc_1800270EB
0x180027030  lea     rax, [rbp+arg_8]
0x180027034  mov     r9, rdi; ArgList
0x180027037  mov     [rsp+40h+ThrdAddr], rax; ThrdAddr
0x18002703c  lea     r8, ?NamedPipeThread@@YAIPEAX@Z; StartAddress
0x180027043  and     [rsp+40h+var_20], 0
0x180027048  xor     edx, edx; StackSize
0x18002704a  xor     ecx, ecx; Security
0x18002704c  call    cs:__imp__beginthreadex
0x180027053  nop     dword ptr [rax+rax+00h]
0x180027058  mov     rbx, rax
0x18002705b  test    rax, rax
0x18002705e  jnz     short loc_180027073
0x180027060  call    cs:__imp___doserrno
0x180027067  nop     dword ptr [rax+rax+00h]
0x18002706c  mov     ecx, [rax]
0x18002706e  mov     [rbp+ExitCode], ecx
0x180027071  jmp     short loc_1800270C5
0x180027073  xor     r8d, r8d; bWaitAll
0x180027076  mov     [rbp+Handles], rdi
0x18002707a  mov     r9d, 7530h; dwMilliseconds
0x180027080  mov     [rbp+Handles+8], rbx
0x180027084  lea     rdx, [rbp+Handles]; lpHandles
0x180027088  lea     ecx, [r8+2]; nCount
0x18002708c  call    cs:__imp_WaitForMultipleObjects
0x180027093  nop     dword ptr [rax+rax+00h]
0x180027098  mov     [rbp+ExitCode], eax
0x18002709b  test    eax, eax
0x18002709d  jnz     short loc_1800270A4
0x18002709f  and     [rbp+ExitCode], eax
0x1800270a2  jmp     short loc_1800270C5
0x1800270a4  cmp     eax, 1
0x1800270a7  jnz     short loc_1800270BE
0x1800270a9  lea     rdx, [rbp+ExitCode]; lpExitCode
0x1800270ad  mov     rcx, rbx; hThread
0x1800270b0  call    cs:__imp_GetExitCodeThread
0x1800270b7  nop     dword ptr [rax+rax+00h]
0x1800270bc  jmp     short loc_1800270C5
0x1800270be  mov     [rbp+ExitCode], 1Eh
0x1800270c5  mov     rcx, rdi; hObject
0x1800270c8  call    cs:__imp_CloseHandle
0x1800270cf  nop     dword ptr [rax+rax+00h]
0x1800270d4  test    rbx, rbx
0x1800270d7  jz      short loc_1800270E8
0x1800270d9  mov     rcx, rbx; hObject
0x1800270dc  call    cs:__imp_CloseHandle
0x1800270e3  nop     dword ptr [rax+rax+00h]
0x1800270e8  mov     eax, [rbp+ExitCode]
0x1800270eb  mov     rbx, [rsp+40h+arg_10]
0x1800270f0  mov     rdi, [rsp+40h+arg_18]
0x1800270f5  add     rsp, 40h
0x1800270f9  pop     rbp
0x1800270fa  retn
```
