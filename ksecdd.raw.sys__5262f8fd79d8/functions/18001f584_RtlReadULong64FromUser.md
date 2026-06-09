# RtlReadULong64FromUser

- ea: `0x18001f584`
- end: `0x18001f5b8`
- name: `RtlReadULong64FromUser`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c93c`
- `0x180012030`

## callees

- `0x180007a4f`
- `0x18001f584`

## pseudocode

```c
__int64 __fastcall RtlReadULong64FromUser(volatile void *a1)
{
  ProbeForRead_0(a1, 8u, 1u);
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x18001f584  push    rbx
0x18001f586  sub     rsp, 20h
0x18001f58a  mov     rax, cs:qword_18001C4F8
0x18001f591  mov     rbx, rcx
0x18001f594  test    rax, rax
0x18001f597  jz      short loc_18001F5A0
0x18001f599  call    rax ; qword_18001C4F8
0x18001f59b  nop     dword ptr [rax]
0x18001f59e  jmp     short loc_18001F5B1
0x18001f5a0  mov     edx, 8; Length
0x18001f5a5  lea     r8d, [rdx-7]; Alignment
0x18001f5a9  call    ProbeForRead_0
0x18001f5ae  mov     rax, [rbx]
0x18001f5b1  add     rsp, 20h
0x18001f5b5  pop     rbx
0x18001f5b6  retn
```
