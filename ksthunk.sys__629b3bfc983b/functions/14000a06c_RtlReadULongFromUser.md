# RtlReadULongFromUser

- ea: `0x14000a06c`
- end: `0x14000a09f`
- name: `RtlReadULongFromUser`
- size: `51`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002dc8`
- `0x140003310`
- `0x140004030`

## callees

- `0x140001044`
- `0x14000a06c`

## pseudocode

```c
__int64 __fastcall RtlReadULongFromUser(unsigned int *a1)
{
  ProbeForRead_0(a1, 4u, 1u);
  return *a1;
}

```

## disassembly

```asm
0x14000a06c  push    rbx
0x14000a06e  sub     rsp, 20h
0x14000a072  mov     rax, cs:qword_140009258
0x14000a079  mov     rbx, rcx
0x14000a07c  test    rax, rax
0x14000a07f  jz      short loc_14000A088
0x14000a081  call    rax ; qword_140009258
0x14000a083  nop     dword ptr [rax]
0x14000a086  jmp     short loc_14000A098
0x14000a088  mov     edx, 4; Length
0x14000a08d  lea     r8d, [rdx-3]; Alignment
0x14000a091  call    ProbeForRead_0
0x14000a096  mov     eax, [rbx]
0x14000a098  add     rsp, 20h
0x14000a09c  pop     rbx
0x14000a09d  retn
```
