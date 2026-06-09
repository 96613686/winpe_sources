# RtlWriteULong64ToUser

- ea: `0x1400080b4`
- end: `0x1400080f4`
- name: `RtlWriteULong64ToUser`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140002040`
- `0x14000a1e0`
- `0x14000a280`
- `0x14000bc80`
- `0x14000c5e0`

## callees

- `0x1400010af`
- `0x1400080b4`

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
0x1400080b4  mov     [rsp+arg_0], rbx
0x1400080b9  push    rdi
0x1400080ba  sub     rsp, 20h
0x1400080be  mov     rax, cs:qword_1400063F0
0x1400080c5  mov     rdi, rdx
0x1400080c8  mov     rbx, rcx
0x1400080cb  test    rax, rax
0x1400080ce  jz      short loc_1400080D7
0x1400080d0  call    rax ; qword_1400063F0
0x1400080d2  nop     dword ptr [rax]
0x1400080d5  jmp     short loc_1400080E8
0x1400080d7  mov     edx, 8; Length
0x1400080dc  lea     r8d, [rdx-7]; Alignment
0x1400080e0  call    ProbeForRead_0
0x1400080e5  mov     [rbx], rdi
0x1400080e8  mov     rbx, [rsp+28h+arg_0]
0x1400080ed  add     rsp, 20h
0x1400080f1  pop     rdi
0x1400080f2  retn
```
