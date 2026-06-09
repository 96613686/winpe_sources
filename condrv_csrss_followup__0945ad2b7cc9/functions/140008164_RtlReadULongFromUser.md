# RtlReadULongFromUser

- ea: `0x140008164`
- end: `0x140008197`
- name: `RtlReadULongFromUser`
- size: `51`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002040`
- `0x140008fb4`
- `0x14000ac50`

## callees

- `0x14000113f`
- `0x140008164`

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
0x140008164  push    rbx
0x140008166  sub     rsp, 20h
0x14000816a  mov     rax, cs:qword_1400072F8
0x140008171  mov     rbx, rcx
0x140008174  test    rax, rax
0x140008177  jz      short loc_140008180
0x140008179  call    rax ; qword_1400072F8
0x14000817b  nop     dword ptr [rax]
0x14000817e  jmp     short loc_140008190
0x140008180  mov     edx, 4; Length
0x140008185  lea     r8d, [rdx-3]; Alignment
0x140008189  call    ProbeForRead_0
0x14000818e  mov     eax, [rbx]
0x140008190  add     rsp, 20h
0x140008194  pop     rbx
0x140008195  retn
```
