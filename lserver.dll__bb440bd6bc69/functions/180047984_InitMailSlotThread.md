# InitMailSlotThread

- ea: `0x180047984`
- end: `0x180047a9c`
- name: `InitMailSlotThread`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180025c1c`

## callees

- `0x180047984`

## import_xrefs

- `msvcrt!__doserrno` at `0x180047a00`
- `msvcrt!__doserrno` at `0x180047a00`
- `msvcrt!_beginthreadex` at `0x1800479ec`
- `msvcrt!_beginthreadex` at `0x1800479ec`
- `KERNEL32!GetExitCodeThread` at `0x180047a50`
- `KERNEL32!GetExitCodeThread` at `0x180047a50`
- `KERNEL32!WaitForMultipleObjects` at `0x180047a2c`
- `KERNEL32!WaitForMultipleObjects` at `0x180047a2c`
- `KERNEL32!CreateEventW` at `0x1800479ab`
- `KERNEL32!CreateEventW` at `0x1800479ab`
- `KERNEL32!GetLastError` at `0x1800479bf`
- `KERNEL32!GetLastError` at `0x1800479bf`
- `KERNEL32!CloseHandle` at `0x180047a68`
- `KERNEL32!CloseHandle` at `0x180047a7c`
- `KERNEL32!CloseHandle` at `0x180047a68`
- `KERNEL32!CloseHandle` at `0x180047a7c`

## pseudocode

```c
DWORD InitMailSlotThread()
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
  v2 = (void *)_beginthreadex(0, 0, (_beginthreadex_proc_type)MailSlotThread, EventW, 0, &ThrdAddr);
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
0x180047984  mov     [rsp-8+arg_10], rbx
0x180047989  mov     [rsp-8+arg_18], rdi
0x18004798e  push    rbp
0x18004798f  mov     rbp, rsp
0x180047992  sub     rsp, 40h
0x180047996  and     [rbp+arg_8], 0
0x18004799a  xorps   xmm0, xmm0
0x18004799d  xor     r9d, r9d; lpName
0x1800479a0  xor     r8d, r8d; bInitialState
0x1800479a3  xor     edx, edx; bManualReset
0x1800479a5  xor     ecx, ecx; lpEventAttributes
0x1800479a7  movups  xmmword ptr [rbp+Handles], xmm0
0x1800479ab  call    cs:__imp_CreateEventW
0x1800479b2  nop     dword ptr [rax+rax+00h]
0x1800479b7  mov     rdi, rax
0x1800479ba  test    rax, rax
0x1800479bd  jnz     short loc_1800479D0
0x1800479bf  call    cs:__imp_GetLastError
0x1800479c6  nop     dword ptr [rax+rax+00h]
0x1800479cb  jmp     loc_180047A8B
0x1800479d0  lea     rax, [rbp+arg_8]
0x1800479d4  mov     r9, rdi; ArgList
0x1800479d7  mov     [rsp+40h+ThrdAddr], rax; ThrdAddr
0x1800479dc  lea     r8, MailSlotThread; StartAddress
0x1800479e3  and     [rsp+40h+var_20], 0
0x1800479e8  xor     edx, edx; StackSize
0x1800479ea  xor     ecx, ecx; Security
0x1800479ec  call    cs:__imp__beginthreadex
0x1800479f3  nop     dword ptr [rax+rax+00h]
0x1800479f8  mov     rbx, rax
0x1800479fb  test    rax, rax
0x1800479fe  jnz     short loc_180047A13
0x180047a00  call    cs:__imp___doserrno
0x180047a07  nop     dword ptr [rax+rax+00h]
0x180047a0c  mov     ecx, [rax]
0x180047a0e  mov     [rbp+ExitCode], ecx
0x180047a11  jmp     short loc_180047A65
0x180047a13  xor     r8d, r8d; bWaitAll
0x180047a16  mov     [rbp+Handles], rdi
0x180047a1a  mov     r9d, 7530h; dwMilliseconds
0x180047a20  mov     [rbp+Handles+8], rbx
0x180047a24  lea     rdx, [rbp+Handles]; lpHandles
0x180047a28  lea     ecx, [r8+2]; nCount
0x180047a2c  call    cs:__imp_WaitForMultipleObjects
0x180047a33  nop     dword ptr [rax+rax+00h]
0x180047a38  mov     [rbp+ExitCode], eax
0x180047a3b  test    eax, eax
0x180047a3d  jnz     short loc_180047A44
0x180047a3f  and     [rbp+ExitCode], eax
0x180047a42  jmp     short loc_180047A65
0x180047a44  cmp     eax, 1
0x180047a47  jnz     short loc_180047A5E
0x180047a49  lea     rdx, [rbp+ExitCode]; lpExitCode
0x180047a4d  mov     rcx, rbx; hThread
0x180047a50  call    cs:__imp_GetExitCodeThread
0x180047a57  nop     dword ptr [rax+rax+00h]
0x180047a5c  jmp     short loc_180047A65
0x180047a5e  mov     [rbp+ExitCode], 1Eh
0x180047a65  mov     rcx, rdi; hObject
0x180047a68  call    cs:__imp_CloseHandle
0x180047a6f  nop     dword ptr [rax+rax+00h]
0x180047a74  test    rbx, rbx
0x180047a77  jz      short loc_180047A88
0x180047a79  mov     rcx, rbx; hObject
0x180047a7c  call    cs:__imp_CloseHandle
0x180047a83  nop     dword ptr [rax+rax+00h]
0x180047a88  mov     eax, [rbp+ExitCode]
0x180047a8b  mov     rbx, [rsp+40h+arg_10]
0x180047a90  mov     rdi, [rsp+40h+arg_18]
0x180047a95  add     rsp, 40h
0x180047a99  pop     rbp
0x180047a9a  retn
```
