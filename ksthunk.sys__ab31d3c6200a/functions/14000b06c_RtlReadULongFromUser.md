# RtlReadULongFromUser

- ea: `0x14000b06c`
- end: `0x14000b09f`
- name: `RtlReadULongFromUser`
- size: `51`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003728`
- `0x140003d50`
- `0x140005030`

## callees

- `0x140001044`
- `0x14000b06c`

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
0x14000b06c  push    rbx
0x14000b06e  sub     rsp, 20h
0x14000b072  mov     rax, cs:qword_14000A258
0x14000b079  mov     rbx, rcx
0x14000b07c  test    rax, rax
0x14000b07f  jz      short loc_14000B088
0x14000b081  call    rax ; qword_14000A258
0x14000b083  nop     dword ptr [rax]
0x14000b086  jmp     short loc_14000B098
0x14000b088  mov     edx, 4; Length
0x14000b08d  lea     r8d, [rdx-3]; Alignment
0x14000b091  call    ProbeForRead_0
0x14000b096  mov     eax, [rbx]
0x14000b098  add     rsp, 20h
0x14000b09c  pop     rbx
0x14000b09d  retn
```
