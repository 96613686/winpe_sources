# RtlWriteULongToUser

- ea: `0x14000b118`
- end: `0x14000b156`
- name: `RtlWriteULongToUser`
- size: `62`
- prototype: `void __fastcall(_DWORD *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003040`
- `0x140014ed4`

## callees

- `0x140001abf`
- `0x14000b118`

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
0x14000b118  mov     [rsp+arg_0], rbx
0x14000b11d  push    rdi
0x14000b11e  sub     rsp, 20h
0x14000b122  mov     rax, cs:qword_1400083E0
0x14000b129  mov     edi, edx
0x14000b12b  mov     rbx, rcx
0x14000b12e  test    rax, rax
0x14000b131  jz      short loc_14000B13A
0x14000b133  call    rax ; qword_1400083E0
0x14000b135  nop     dword ptr [rax]
0x14000b138  jmp     short loc_14000B14A
0x14000b13a  mov     edx, 4; Length
0x14000b13f  lea     r8d, [rdx-3]; Alignment
0x14000b143  call    ProbeForRead_0
0x14000b148  mov     [rbx], edi
0x14000b14a  mov     rbx, [rsp+28h+arg_0]
0x14000b14f  add     rsp, 20h
0x14000b153  pop     rdi
0x14000b154  retn
```
