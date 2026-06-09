# RtlWriteULongToUser

- ea: `0x1400081e8`
- end: `0x140008226`
- name: `RtlWriteULongToUser`
- size: `62`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002060`
- `0x140008fb4`
- `0x14000ce70`

## callees

- `0x14000113f`
- `0x1400081e8`

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
0x1400081e8  mov     [rsp+arg_0], rbx
0x1400081ed  push    rdi
0x1400081ee  sub     rsp, 20h
0x1400081f2  mov     rax, cs:qword_140007300
0x1400081f9  mov     edi, edx
0x1400081fb  mov     rbx, rcx
0x1400081fe  test    rax, rax
0x140008201  jz      short loc_14000820A
0x140008203  call    rax ; qword_140007300
0x140008205  nop     dword ptr [rax]
0x140008208  jmp     short loc_14000821A
0x14000820a  mov     edx, 4; Length
0x14000820f  lea     r8d, [rdx-3]; Alignment
0x140008213  call    ProbeForRead_0
0x140008218  mov     [rbx], edi
0x14000821a  mov     rbx, [rsp+28h+arg_0]
0x14000821f  add     rsp, 20h
0x140008223  pop     rdi
0x140008224  retn
```
