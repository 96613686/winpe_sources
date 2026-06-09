# RtlWriteULong64ToUser

- ea: `0x14000d0f0`
- end: `0x14000d130`
- name: `RtlWriteULong64ToUser`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003700`
- `0x140007030`

## callees

- `0x1400056cf`
- `0x14000d0f0`

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
0x14000d0f0  mov     [rsp+arg_0], rbx
0x14000d0f5  push    rdi
0x14000d0f6  sub     rsp, 20h
0x14000d0fa  mov     rax, cs:qword_14000C300
0x14000d101  mov     rdi, rdx
0x14000d104  mov     rbx, rcx
0x14000d107  test    rax, rax
0x14000d10a  jz      short loc_14000D113
0x14000d10c  call    rax ; qword_14000C300
0x14000d10e  nop     dword ptr [rax]
0x14000d111  jmp     short loc_14000D124
0x14000d113  mov     edx, 8; Length
0x14000d118  lea     r8d, [rdx-7]; Alignment
0x14000d11c  call    ProbeForRead_0
0x14000d121  mov     [rbx], rdi
0x14000d124  mov     rbx, [rsp+28h+arg_0]
0x14000d129  add     rsp, 20h
0x14000d12d  pop     rdi
0x14000d12e  retn
```
