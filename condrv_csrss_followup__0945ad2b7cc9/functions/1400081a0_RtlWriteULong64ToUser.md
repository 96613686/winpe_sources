# RtlWriteULong64ToUser

- ea: `0x1400081a0`
- end: `0x1400081e0`
- name: `RtlWriteULong64ToUser`
- size: `64`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140002050`
- `0x140008da4`
- `0x140008e54`
- `0x14000ce70`
- `0x14000e2e0`

## callees

- `0x14000113f`
- `0x1400081a0`

## pseudocode

```c
void __fastcall RtlWriteULong64ToUser(_QWORD *a1, __int64 a2)
{
  ProbeForRead_0(a1, 8u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x1400081a0  mov     [rsp+arg_0], rbx
0x1400081a5  push    rdi
0x1400081a6  sub     rsp, 20h
0x1400081aa  mov     rax, cs:qword_140007310
0x1400081b1  mov     rdi, rdx
0x1400081b4  mov     rbx, rcx
0x1400081b7  test    rax, rax
0x1400081ba  jz      short loc_1400081C3
0x1400081bc  call    rax ; qword_140007310
0x1400081be  nop     dword ptr [rax]
0x1400081c1  jmp     short loc_1400081D4
0x1400081c3  mov     edx, 8; Length
0x1400081c8  lea     r8d, [rdx-7]; Alignment
0x1400081cc  call    ProbeForRead_0
0x1400081d1  mov     [rbx], rdi
0x1400081d4  mov     rbx, [rsp+28h+arg_0]
0x1400081d9  add     rsp, 20h
0x1400081dd  pop     rdi
0x1400081de  retn
```
