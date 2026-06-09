# MupStateMachineWorker

- ea: `0x140019f00`
- end: `0x140019f57`
- name: `MupStateMachineWorker`
- size: `87`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001b30`

## callees

- `0x140019f00`
- `0x14001bb60`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140019f26`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140019f26`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140019f42`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140019f42`

## pseudocode

```c
__int64 __fastcall MupStateMachineWorker(_QWORD *P)
{
  __int64 v2; // rcx
  __int64 v4; // rdi
  unsigned int v5; // ebx

  v2 = P[7];
  if ( !v2 )
    return MupStateMachine(P);
  v4 = PsAttachSiloToCurrentThread(v2);
  v5 = MupStateMachine(P);
  PsDetachSiloFromCurrentThread(v4);
  return v5;
}

```

## disassembly

```asm
0x140019f00  push    rbx
0x140019f02  sub     rsp, 20h
0x140019f06  mov     rbx, rcx
0x140019f09  mov     rcx, [rcx+38h]
0x140019f0d  test    rcx, rcx
0x140019f10  jnz     short loc_140019F21
0x140019f12  mov     rcx, rbx; P
0x140019f15  call    MupStateMachine
0x140019f1a  add     rsp, 20h
0x140019f1e  pop     rbx
0x140019f1f  retn
0x140019f21  mov     [rsp+28h+arg_0], rdi
0x140019f26  call    cs:__imp_PsAttachSiloToCurrentThread
0x140019f2d  nop     dword ptr [rax+rax+00h]
0x140019f32  mov     rcx, rbx; P
0x140019f35  mov     rdi, rax
0x140019f38  call    MupStateMachine
0x140019f3d  mov     rcx, rdi
0x140019f40  mov     ebx, eax
0x140019f42  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140019f49  nop     dword ptr [rax+rax+00h]
0x140019f4e  mov     rdi, [rsp+28h+arg_0]
0x140019f53  mov     eax, ebx
0x140019f55  jmp     short loc_140019F1A
```
