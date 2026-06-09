# RdbsspKernelInterfaceGetSubProcessTag

- ea: `0x140052110`
- end: `0x1400521df`
- name: `RdbsspKernelInterfaceGetSubProcessTag`
- size: `207`
- prototype: `__int64 __fastcall(__int64, struct _KTHREAD *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400442e4`
- `0x140044320`
- `0x140052110`

## import_xrefs

- `ntoskrnl!PsGetProcessWow64Process` at `0x140052187`
- `ntoskrnl!PsGetProcessWow64Process` at `0x140052187`
- `ntoskrnl!PsGetCurrentProcess` at `0x14005212f`
- `ntoskrnl!PsGetCurrentProcess` at `0x14005212f`
- `ntoskrnl!PsGetThreadTeb` at `0x140052141`
- `ntoskrnl!PsGetThreadTeb` at `0x140052141`
- `ntoskrnl!PsGetThreadProcess` at `0x14005215f`
- `ntoskrnl!PsGetThreadProcess` at `0x140052178`
- `ntoskrnl!PsGetThreadProcess` at `0x14005215f`
- `ntoskrnl!PsGetThreadProcess` at `0x140052178`

## pseudocode

```c
__int64 __fastcall RdbsspKernelInterfaceGetSubProcessTag(__int64 a1, struct _KTHREAD *a2)
{
  struct _KTHREAD *CurrentThread; // rsi
  struct _KPROCESS *CurrentProcess; // r15
  __int64 ThreadTeb; // rdi
  unsigned int v6; // ebx
  PEPROCESS ThreadProcess; // rax

  CurrentThread = KeGetCurrentThread();
  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
  ThreadTeb = PsGetThreadTeb(CurrentThread);
  v6 = 0;
  if ( a2 == CurrentThread && PsGetThreadProcess(CurrentThread) == CurrentProcess && ThreadTeb )
  {
    ThreadProcess = PsGetThreadProcess(a2);
    if ( PsGetProcessWow64Process(ThreadProcess) )
      return (unsigned int)RtlReadULongFromUser(ThreadTeb + 12128);
    else
      return (unsigned int)RtlReadULong64FromUser((volatile void *)(ThreadTeb + 5920));
  }
  return v6;
}

```

## disassembly

```asm
0x140052110  mov     [rsp+arg_0], rbx
0x140052115  mov     [rsp+arg_10], rsi
0x14005211a  push    rdi
0x14005211b  push    r14
0x14005211d  push    r15
0x14005211f  sub     rsp, 20h
0x140052123  mov     r14, rdx
0x140052126  mov     rsi, gs:188h
0x14005212f  call    cs:__imp_PsGetCurrentProcess
0x140052136  nop     dword ptr [rax+rax+00h]
0x14005213b  mov     r15, rax
0x14005213e  mov     rcx, rsi
0x140052141  call    cs:__imp_PsGetThreadTeb
0x140052148  nop     dword ptr [rax+rax+00h]
0x14005214d  mov     rdi, rax
0x140052150  xor     ebx, ebx
0x140052152  mov     [rsp+38h+arg_8], rbx
0x140052157  cmp     r14, rsi
0x14005215a  jnz     short loc_1400521C8
0x14005215c  mov     rcx, rsi; Thread
0x14005215f  call    cs:__imp_PsGetThreadProcess
0x140052166  nop     dword ptr [rax+rax+00h]
0x14005216b  cmp     rax, r15
0x14005216e  jnz     short loc_1400521C8
0x140052170  test    rdi, rdi
0x140052173  jz      short loc_1400521C8
0x140052175  mov     rcx, r14; Thread
0x140052178  call    cs:__imp_PsGetThreadProcess
0x14005217f  nop     dword ptr [rax+rax+00h]
0x140052184  mov     rcx, rax
0x140052187  call    cs:__imp_PsGetProcessWow64Process
0x14005218e  nop     dword ptr [rax+rax+00h]
0x140052193  test    rax, rax
0x140052196  jz      short loc_1400521AD
0x140052198  lea     rcx, [rdi+2F60h]
0x14005219f  call    RtlReadULongFromUser
0x1400521a4  mov     ebx, eax
0x1400521a6  mov     [rsp+38h+arg_8], rbx
0x1400521ab  jmp     short loc_1400521C1
0x1400521ad  lea     rcx, [rdi+1720h]
0x1400521b4  call    RtlReadULong64FromUser
0x1400521b9  mov     rbx, rax
0x1400521bc  mov     [rsp+38h+arg_8], rax
0x1400521c1  jmp     short loc_1400521C8
0x1400521c3  mov     rbx, [rsp+38h+arg_8]
0x1400521c8  mov     eax, ebx
0x1400521ca  mov     rbx, [rsp+38h+arg_0]
0x1400521cf  mov     rsi, [rsp+38h+arg_10]
0x1400521d4  add     rsp, 20h
0x1400521d8  pop     r15
0x1400521da  pop     r14
0x1400521dc  pop     rdi
0x1400521dd  retn
```
