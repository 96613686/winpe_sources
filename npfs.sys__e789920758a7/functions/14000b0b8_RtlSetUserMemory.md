# RtlSetUserMemory

- ea: `0x14000b0b8`
- end: `0x14000b112`
- name: `RtlSetUserMemory`
- size: `90`
- prototype: `void *__fastcall(void *, unsigned __int8, SIZE_T)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140003030`
- `0x140014ed4`

## callees

- `0x140001abf`
- `0x140001e60`
- `0x14000b0b8`

## pseudocode

```c
void *__fastcall RtlSetUserMemory(void *a1, unsigned __int8 a2, SIZE_T a3)
{
  int v4; // esi

  v4 = a2;
  ProbeForRead_0(a1, a3, 1u);
  return RtlSetVolatileMemory(a1, v4, a3);
}

```

## disassembly

```asm
0x14000b0b8  mov     [rsp+arg_0], rbx
0x14000b0bd  mov     [rsp+arg_8], rsi
0x14000b0c2  push    rdi
0x14000b0c3  sub     rsp, 20h
0x14000b0c7  mov     rax, cs:qword_1400083B0
0x14000b0ce  mov     rbx, r8
0x14000b0d1  movzx   esi, dl
0x14000b0d4  mov     rdi, rcx
0x14000b0d7  test    rax, rax
0x14000b0da  jz      short loc_14000B0E6
0x14000b0dc  mov     dl, sil
0x14000b0df  call    rax ; qword_1400083B0
0x14000b0e1  nop     dword ptr [rax]
0x14000b0e4  jmp     short loc_14000B101
0x14000b0e6  mov     r8d, 1; Alignment
0x14000b0ec  mov     rdx, rbx; Length
0x14000b0ef  call    ProbeForRead_0
0x14000b0f4  mov     edx, esi; Val
0x14000b0f6  mov     r8, rbx; Size
0x14000b0f9  mov     rcx, rdi; void *
0x14000b0fc  call    RtlSetVolatileMemory
0x14000b101  mov     rbx, [rsp+28h+arg_0]
0x14000b106  mov     rsi, [rsp+28h+arg_8]
0x14000b10b  add     rsp, 20h
0x14000b10f  pop     rdi
0x14000b110  retn
```
