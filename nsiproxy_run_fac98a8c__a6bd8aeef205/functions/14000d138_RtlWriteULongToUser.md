# RtlWriteULongToUser

- ea: `0x14000d138`
- end: `0x14000d176`
- name: `RtlWriteULongToUser`
- size: `62`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140002280`
- `0x140002850`
- `0x140002eb0`
- `0x140005c3c`
- `0x140007040`

## callees

- `0x1400056cf`
- `0x14000d138`

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
0x14000d138  mov     [rsp+arg_0], rbx
0x14000d13d  push    rdi
0x14000d13e  sub     rsp, 20h
0x14000d142  mov     rax, cs:qword_14000C2F0
0x14000d149  mov     edi, edx
0x14000d14b  mov     rbx, rcx
0x14000d14e  test    rax, rax
0x14000d151  jz      short loc_14000D15A
0x14000d153  call    rax ; qword_14000C2F0
0x14000d155  nop     dword ptr [rax]
0x14000d158  jmp     short loc_14000D16A
0x14000d15a  mov     edx, 4; Length
0x14000d15f  lea     r8d, [rdx-3]; Alignment
0x14000d163  call    ProbeForRead_0
0x14000d168  mov     [rbx], edi
0x14000d16a  mov     rbx, [rsp+28h+arg_0]
0x14000d16f  add     rsp, 20h
0x14000d173  pop     rdi
0x14000d174  retn
```
