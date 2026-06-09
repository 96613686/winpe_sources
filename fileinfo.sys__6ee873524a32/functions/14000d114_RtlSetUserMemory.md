# RtlSetUserMemory

- ea: `0x14000d114`
- end: `0x14000d16e`
- name: `RtlSetUserMemory`
- size: `90`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140005030`
- `0x14000d8cc`
- `0x140016fa0`
- `0x140017284`

## callees

- `0x140003046`
- `0x140003970`
- `0x14000d114`

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
0x14000d114  mov     [rsp+arg_0], rbx
0x14000d119  mov     [rsp+arg_8], rsi
0x14000d11e  push    rdi
0x14000d11f  sub     rsp, 20h
0x14000d123  mov     rax, cs:qword_14000B4C0
0x14000d12a  mov     rbx, r8
0x14000d12d  movzx   esi, dl
0x14000d130  mov     rdi, rcx
0x14000d133  test    rax, rax
0x14000d136  jz      short loc_14000D142
0x14000d138  mov     dl, sil
0x14000d13b  call    rax ; qword_14000B4C0
0x14000d13d  nop     dword ptr [rax]
0x14000d140  jmp     short loc_14000D15D
0x14000d142  mov     r8d, 1; Alignment
0x14000d148  mov     rdx, rbx; Length
0x14000d14b  call    ProbeForRead_0
0x14000d150  mov     edx, esi; Val
0x14000d152  mov     r8, rbx; Size
0x14000d155  mov     rcx, rdi; void *
0x14000d158  call    RtlSetVolatileMemory
0x14000d15d  mov     rbx, [rsp+28h+arg_0]
0x14000d162  mov     rsi, [rsp+28h+arg_8]
0x14000d167  add     rsp, 20h
0x14000d16b  pop     rdi
0x14000d16c  retn
```
