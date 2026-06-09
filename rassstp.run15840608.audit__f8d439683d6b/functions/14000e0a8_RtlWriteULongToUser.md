# RtlWriteULongToUser

- ea: `0x14000e0a8`
- end: `0x14000e0e6`
- name: `RtlWriteULongToUser`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007040`
- `0x140011b00`

## callees

- `0x140002b06`
- `0x14000e0a8`

## pseudocode

```c
void __fastcall RtlWriteULongToUser(_DWORD *a1, int a2)
{
  ProbeForRead_0(a1, 4u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x14000e0a8  mov     [rsp+arg_0], rbx
0x14000e0ad  push    rdi
0x14000e0ae  sub     rsp, 20h
0x14000e0b2  mov     rax, cs:qword_14000C470
0x14000e0b9  mov     edi, edx
0x14000e0bb  mov     rbx, rcx
0x14000e0be  test    rax, rax
0x14000e0c1  jz      short loc_14000E0CA
0x14000e0c3  call    rax ; qword_14000C470
0x14000e0c5  nop     dword ptr [rax]
0x14000e0c8  jmp     short loc_14000E0DA
0x14000e0ca  mov     edx, 4; Length
0x14000e0cf  lea     r8d, [rdx-3]; Alignment
0x14000e0d3  call    ProbeForRead_0
0x14000e0d8  mov     [rbx], edi
0x14000e0da  mov     rbx, [rsp+28h+arg_0]
0x14000e0df  add     rsp, 20h
0x14000e0e3  pop     rdi
0x14000e0e4  retn
```
