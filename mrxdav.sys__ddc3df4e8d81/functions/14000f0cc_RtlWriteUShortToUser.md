# RtlWriteUShortToUser

- ea: `0x14000f0cc`
- end: `0x14000f10c`
- name: `RtlWriteUShortToUser`
- size: `64`
- prototype: `void __fastcall(_WORD *, __int16)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140008040`
- `0x1400199a0`
- `0x14001b360`

## callees

- `0x14000102f`
- `0x14000f0cc`

## pseudocode

```c
void __fastcall RtlWriteUShortToUser(_WORD *a1, __int16 a2)
{
  ProbeForRead_0(a1, 2u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x14000f0cc  mov     [rsp+arg_0], rbx
0x14000f0d1  push    rdi
0x14000f0d2  sub     rsp, 20h
0x14000f0d6  mov     rax, cs:qword_14000D490
0x14000f0dd  movzx   edi, dx
0x14000f0e0  mov     rbx, rcx
0x14000f0e3  test    rax, rax
0x14000f0e6  jz      short loc_14000F0EF
0x14000f0e8  call    rax ; qword_14000D490
0x14000f0ea  nop     dword ptr [rax]
0x14000f0ed  jmp     short loc_14000F100
0x14000f0ef  mov     edx, 2; Length
0x14000f0f4  lea     r8d, [rdx-1]; Alignment
0x14000f0f8  call    ProbeForRead_0
0x14000f0fd  mov     [rbx], di
0x14000f100  mov     rbx, [rsp+28h+arg_0]
0x14000f105  add     rsp, 20h
0x14000f109  pop     rdi
0x14000f10a  retn
```
