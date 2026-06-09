# NsipDetachFromContainer

- ea: `0x1400a9fdc`
- end: `0x1400aa028`
- name: `NsipDetachFromContainer`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400205f0`

## import_xrefs

- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400a9ff1`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400a9ff1`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400aa010`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400aa010`

## pseudocode

```c
__int64 __fastcall NsipDetachFromContainer(__int64 a1)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)(a1 + 32);
  PsDetachSiloFromCurrentThread(*(_QWORD *)(a1 + 24));
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  return PsDereferenceSiloContext(v1);
}

```

## disassembly

```asm
0x1400a9fdc  mov     [rsp+arg_0], rbx
0x1400a9fe1  push    rdi
0x1400a9fe2  sub     rsp, 20h
0x1400a9fe6  mov     rbx, [rcx+20h]
0x1400a9fea  mov     rdi, rcx
0x1400a9fed  mov     rcx, [rcx+18h]
0x1400a9ff1  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1400a9ff8  nop     dword ptr [rax+rax+00h]
0x1400a9ffd  mov     rcx, rbx
0x1400aa000  mov     qword ptr [rdi+18h], 0
0x1400aa008  mov     qword ptr [rdi+20h], 0
0x1400aa010  call    cs:__imp_PsDereferenceSiloContext
0x1400aa017  nop     dword ptr [rax+rax+00h]
0x1400aa01c  mov     rbx, [rsp+28h+arg_0]
0x1400aa021  add     rsp, 20h
0x1400aa025  pop     rdi
0x1400aa026  retn
```
