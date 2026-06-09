# RtlWriteUCharToUser

- ea: `0x14000806c`
- end: `0x1400080ab`
- name: `RtlWriteUCharToUser`
- size: `63`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002030`
- `0x14000a0e0`
- `0x14000a320`

## callees

- `0x1400010af`
- `0x14000806c`

## pseudocode

```c
void __fastcall RtlWriteUCharToUser(_BYTE *a1, char a2)
{
  ProbeForRead_0(a1, 1u, 1u);
  *a1 = a2;
}

```

## disassembly

```asm
0x14000806c  mov     [rsp+arg_0], rbx
0x140008071  push    rdi
0x140008072  sub     rsp, 20h
0x140008076  mov     rax, cs:qword_1400063C0
0x14000807d  mov     dil, dl
0x140008080  mov     rbx, rcx
0x140008083  test    rax, rax
0x140008086  jz      short loc_14000808F
0x140008088  call    rax ; qword_1400063C0
0x14000808a  nop     dword ptr [rax]
0x14000808d  jmp     short loc_14000809F
0x14000808f  mov     edx, 1; Length
0x140008094  mov     r8d, edx; Alignment
0x140008097  call    ProbeForRead_0
0x14000809c  mov     [rbx], dil
0x14000809f  mov     rbx, [rsp+28h+arg_0]
0x1400080a4  add     rsp, 20h
0x1400080a8  pop     rdi
0x1400080a9  retn
```
