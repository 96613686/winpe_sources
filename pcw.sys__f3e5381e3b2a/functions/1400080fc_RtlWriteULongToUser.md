# RtlWriteULongToUser

- ea: `0x1400080fc`
- end: `0x14000813a`
- name: `RtlWriteULongToUser`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002050`
- `0x140009d40`

## callees

- `0x1400010af`
- `0x1400080fc`

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
0x1400080fc  mov     [rsp+arg_0], rbx
0x140008101  push    rdi
0x140008102  sub     rsp, 20h
0x140008106  mov     rax, cs:qword_1400063E0
0x14000810d  mov     edi, edx
0x14000810f  mov     rbx, rcx
0x140008112  test    rax, rax
0x140008115  jz      short loc_14000811E
0x140008117  call    rax ; qword_1400063E0
0x140008119  nop     dword ptr [rax]
0x14000811c  jmp     short loc_14000812E
0x14000811e  mov     edx, 4; Length
0x140008123  lea     r8d, [rdx-3]; Alignment
0x140008127  call    ProbeForRead_0
0x14000812c  mov     [rbx], edi
0x14000812e  mov     rbx, [rsp+28h+arg_0]
0x140008133  add     rsp, 20h
0x140008137  pop     rdi
0x140008138  retn
```
