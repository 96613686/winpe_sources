# RtlWriteULongToUser

- ea: `0x140014c8c`
- end: `0x140014cca`
- name: `RtlWriteULongToUser`
- size: `62`
- prototype: `void __fastcall(_DWORD *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007040`
- `0x14002205c`
- `0x140024050`
- `0x140024614`

## callees

- `0x140002546`
- `0x140014c8c`

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
0x140014c8c  mov     [rsp+arg_0], rbx
0x140014c91  push    rdi
0x140014c92  sub     rsp, 20h
0x140014c96  mov     rax, cs:qword_140012620
0x140014c9d  mov     edi, edx
0x140014c9f  mov     rbx, rcx
0x140014ca2  test    rax, rax
0x140014ca5  jz      short loc_140014CAE
0x140014ca7  call    rax ; qword_140012620
0x140014ca9  nop     dword ptr [rax]
0x140014cac  jmp     short loc_140014CBE
0x140014cae  mov     edx, 4; Length
0x140014cb3  lea     r8d, [rdx-3]; Alignment
0x140014cb7  call    ProbeForRead_0
0x140014cbc  mov     [rbx], edi
0x140014cbe  mov     rbx, [rsp+28h+arg_0]
0x140014cc3  add     rsp, 20h
0x140014cc7  pop     rdi
0x140014cc8  retn
```
