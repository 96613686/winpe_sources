# RtlWriteULong64ToUser

- ea: `0x140011c9c`
- end: `0x140011cdc`
- name: `RtlWriteULong64ToUser`
- size: `64`
- prototype: `void __fastcall(_QWORD *, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140007040`
- `0x14001a29c`
- `0x14001a41c`
- `0x14001a59c`
- `0x14002a2ec`
- `0x14002aebc`

## callees

- `0x140003051`
- `0x140011c9c`

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
0x140011c9c  mov     [rsp+arg_0], rbx
0x140011ca1  push    rdi
0x140011ca2  sub     rsp, 20h
0x140011ca6  mov     rax, cs:qword_14000F5D0
0x140011cad  mov     rdi, rdx
0x140011cb0  mov     rbx, rcx
0x140011cb3  test    rax, rax
0x140011cb6  jz      short loc_140011CBF
0x140011cb8  call    rax ; qword_14000F5D0
0x140011cba  nop     dword ptr [rax]
0x140011cbd  jmp     short loc_140011CD0
0x140011cbf  mov     edx, 8; Length
0x140011cc4  lea     r8d, [rdx-7]; Alignment
0x140011cc8  call    ProbeForRead_0
0x140011ccd  mov     [rbx], rdi
0x140011cd0  mov     rbx, [rsp+28h+arg_0]
0x140011cd5  add     rsp, 20h
0x140011cd9  pop     rdi
0x140011cda  retn
```
