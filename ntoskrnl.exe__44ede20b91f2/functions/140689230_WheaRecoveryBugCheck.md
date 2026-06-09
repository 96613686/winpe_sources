# WheaRecoveryBugCheck

- ea: `0x140689230`
- end: `0x140689292`
- name: `WheaRecoveryBugCheck`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14040c2f0`
- `0x1405f8910`

## callees

- `0x14040cc28`
- `0x140689320`
- `0x1406894b0`

## import_xrefs

- `PSHED!PshedWriteErrorRecord` at `0x14068925d`
- `PSHED!PshedWriteErrorRecord` at `0x14068925d`
- `PSHED!PshedBugCheckSystem` at `0x14068927a`
- `PSHED!PshedBugCheckSystem` at `0x14068927a`

## pseudocode

```c
__int64 __fastcall WheaRecoveryBugCheck(__int64 a1, __int64 a2)
{
  sub_14040CC28(3, a1);
  sub_1406894B0(a1);
  PshedWriteErrorRecord(0, *(unsigned int *)(a1 + 20), a1);
  sub_140689320(a1, *(unsigned int *)(a1 + 20));
  return PshedBugCheckSystem(a2, a1);
}

```

## disassembly

```asm
0x140689230  mov     [rsp+arg_0], rbx
0x140689235  push    rdi
0x140689236  sub     rsp, 20h
0x14068923a  mov     rdi, rdx
0x14068923d  mov     rbx, rcx
0x140689240  mov     rdx, rcx
0x140689243  mov     ecx, 3
0x140689248  call    sub_14040CC28
0x14068924d  mov     rcx, rbx
0x140689250  call    sub_1406894B0
0x140689255  mov     edx, [rbx+14h]
0x140689258  mov     r8, rbx
0x14068925b  xor     ecx, ecx
0x14068925d  call    cs:PshedWriteErrorRecord
0x140689264  nop     dword ptr [rax+rax+00h]
0x140689269  mov     edx, [rbx+14h]
0x14068926c  mov     rcx, rbx
0x14068926f  call    sub_140689320
0x140689274  mov     rdx, rbx
0x140689277  mov     rcx, rdi
0x14068927a  call    cs:PshedBugCheckSystem
0x140689281  nop     dword ptr [rax+rax+00h]
0x140689286  mov     rbx, [rsp+28h+arg_0]
0x14068928b  add     rsp, 20h
0x14068928f  pop     rdi
0x140689290  retn
```
