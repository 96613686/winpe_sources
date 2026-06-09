# RtlWriteULong64ToUser

- ea: `0x140021150`
- end: `0x140021190`
- name: `RtlWriteULong64ToUser`
- size: `64`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140014060`
- `0x1400260a4`
- `0x1400266ec`
- `0x140026d94`
- `0x140027144`
- `0x1400277f4`
- `0x140027ca0`

## callees

- `0x1400014ff`
- `0x140021150`

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
0x140021150  mov     [rsp+arg_0], rbx
0x140021155  push    rdi
0x140021156  sub     rsp, 20h
0x14002115a  mov     rax, cs:qword_14001D8B0
0x140021161  mov     rdi, rdx
0x140021164  mov     rbx, rcx
0x140021167  test    rax, rax
0x14002116a  jz      short loc_140021173
0x14002116c  call    rax ; qword_14001D8B0
0x14002116e  nop     dword ptr [rax]
0x140021171  jmp     short loc_140021184
0x140021173  mov     edx, 8; Length
0x140021178  lea     r8d, [rdx-7]; Alignment
0x14002117c  call    ProbeForRead_0
0x140021181  mov     [rbx], rdi
0x140021184  mov     rbx, [rsp+28h+arg_0]
0x140021189  add     rsp, 20h
0x14002118d  pop     rdi
0x14002118e  retn
```
