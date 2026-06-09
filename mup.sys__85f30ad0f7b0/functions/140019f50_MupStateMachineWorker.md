# MupStateMachineWorker

- ea: `0x140019f50`
- end: `0x140019fa7`
- name: `MupStateMachineWorker`
- size: `87`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001b30`

## callees

- `0x140019f50`
- `0x14001bbb0`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140019f76`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140019f76`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140019f92`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140019f92`

## pseudocode

```c
__int64 __fastcall MupStateMachineWorker(_QWORD *P, unsigned __int64 a2)
{
  __int64 v3; // rcx
  __int64 v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned int v7; // ebx

  v3 = P[7];
  if ( !v3 )
    return MupStateMachine((unsigned __int64)P, a2);
  v5 = PsAttachSiloToCurrentThread(v3);
  v7 = MupStateMachine((unsigned __int64)P, v6);
  PsDetachSiloFromCurrentThread(v5);
  return v7;
}

```

## disassembly

```asm
0x140019f50  push    rbx
0x140019f52  sub     rsp, 20h
0x140019f56  mov     rbx, rcx
0x140019f59  mov     rcx, [rcx+38h]
0x140019f5d  test    rcx, rcx
0x140019f60  jnz     short loc_140019F71
0x140019f62  mov     rcx, rbx; P
0x140019f65  call    MupStateMachine
0x140019f6a  add     rsp, 20h
0x140019f6e  pop     rbx
0x140019f6f  retn
0x140019f71  mov     [rsp+28h+arg_0], rdi
0x140019f76  call    cs:__imp_PsAttachSiloToCurrentThread
0x140019f7d  nop     dword ptr [rax+rax+00h]
0x140019f82  mov     rcx, rbx; P
0x140019f85  mov     rdi, rax
0x140019f88  call    MupStateMachine
0x140019f8d  mov     rcx, rdi
0x140019f90  mov     ebx, eax
0x140019f92  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140019f99  nop     dword ptr [rax+rax+00h]
0x140019f9e  mov     rdi, [rsp+28h+arg_0]
0x140019fa3  mov     eax, ebx
0x140019fa5  jmp     short loc_140019F6A
```
