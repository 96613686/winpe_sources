# RtlReadULong64FromUser

- ea: `0x140008128`
- end: `0x14000815c`
- name: `RtlReadULong64FromUser`
- size: `52`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002030`
- `0x14000ac50`
- `0x14000ce70`
- `0x14000d2a0`

## callees

- `0x14000113f`
- `0x140008128`

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
0x140008128  push    rbx
0x14000812a  sub     rsp, 20h
0x14000812e  mov     rax, cs:qword_140007308
0x140008135  mov     rbx, rcx
0x140008138  test    rax, rax
0x14000813b  jz      short loc_140008144
0x14000813d  call    rax ; qword_140007308
0x14000813f  nop     dword ptr [rax]
0x140008142  jmp     short loc_140008155
0x140008144  mov     edx, 8; Length
0x140008149  lea     r8d, [rdx-7]; Alignment
0x14000814d  call    ProbeForRead_0
0x140008152  mov     rax, [rbx]
0x140008155  add     rsp, 20h
0x140008159  pop     rbx
0x14000815a  retn
```
