# RtlWriteULongToUser

- ea: `0x14000d174`
- end: `0x14000d1b2`
- name: `RtlWriteULongToUser`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005040`
- `0x14000d8cc`

## callees

- `0x140003046`
- `0x14000d174`

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
0x14000d174  mov     [rsp+arg_0], rbx
0x14000d179  push    rdi
0x14000d17a  sub     rsp, 20h
0x14000d17e  mov     rax, cs:qword_14000B4F0
0x14000d185  mov     edi, edx
0x14000d187  mov     rbx, rcx
0x14000d18a  test    rax, rax
0x14000d18d  jz      short loc_14000D196
0x14000d18f  call    rax ; qword_14000B4F0
0x14000d191  nop     dword ptr [rax]
0x14000d194  jmp     short loc_14000D1A6
0x14000d196  mov     edx, 4; Length
0x14000d19b  lea     r8d, [rdx-3]; Alignment
0x14000d19f  call    ProbeForRead_0
0x14000d1a4  mov     [rbx], edi
0x14000d1a6  mov     rbx, [rsp+28h+arg_0]
0x14000d1ab  add     rsp, 20h
0x14000d1af  pop     rdi
0x14000d1b0  retn
```
