# RtlWriteULongToUser

- ea: `0x140021198`
- end: `0x1400211d6`
- name: `RtlWriteULongToUser`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140014070`
- `0x1400260a4`
- `0x1400266ec`
- `0x140026d94`
- `0x140027144`
- `0x1400277f4`
- `0x140027ca0`
- `0x140027f64`

## callees

- `0x1400014ff`
- `0x140021198`

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
0x140021198  mov     [rsp+arg_0], rbx
0x14002119d  push    rdi
0x14002119e  sub     rsp, 20h
0x1400211a2  mov     rax, cs:qword_14001D8A0
0x1400211a9  mov     edi, edx
0x1400211ab  mov     rbx, rcx
0x1400211ae  test    rax, rax
0x1400211b1  jz      short loc_1400211BA
0x1400211b3  call    rax ; qword_14001D8A0
0x1400211b5  nop     dword ptr [rax]
0x1400211b8  jmp     short loc_1400211CA
0x1400211ba  mov     edx, 4; Length
0x1400211bf  lea     r8d, [rdx-3]; Alignment
0x1400211c3  call    ProbeForRead_0
0x1400211c8  mov     [rbx], edi
0x1400211ca  mov     rbx, [rsp+28h+arg_0]
0x1400211cf  add     rsp, 20h
0x1400211d3  pop     rdi
0x1400211d4  retn
```
