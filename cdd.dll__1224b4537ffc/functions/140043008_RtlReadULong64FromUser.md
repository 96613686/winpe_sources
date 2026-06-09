# RtlReadULong64FromUser

- ea: `0x140043008`
- end: `0x14004303c`
- name: `RtlReadULong64FromUser`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140012e98`
- `0x140038010`

## callees

- `0x140029456`
- `0x140043008`

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
0x140043008  push    rbx
0x14004300a  sub     rsp, 20h
0x14004300e  mov     rax, cs:qword_140041658
0x140043015  mov     rbx, rcx
0x140043018  test    rax, rax
0x14004301b  jz      short loc_140043024
0x14004301d  call    rax ; qword_140041658
0x14004301f  nop     dword ptr [rax]
0x140043022  jmp     short loc_140043035
0x140043024  mov     edx, 8; Length
0x140043029  lea     r8d, [rdx-7]; Alignment
0x14004302d  call    ProbeForRead_0
0x140043032  mov     rax, [rbx]
0x140043035  add     rsp, 20h
0x140043039  pop     rbx
0x14004303a  retn
```
