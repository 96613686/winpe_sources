# RtlCopyToUser

- ea: `0x14000f008`
- end: `0x14000f065`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `void *__fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140008020`
- `0x140014e00`
- `0x1400199a0`

## callees

- `0x14000102f`
- `0x1400067d0`
- `0x14000f008`

## pseudocode

```c
void *__fastcall RtlCopyToUser(void *a1, void *Src, size_t Size)
{
  void *result; // rax

  result = 0;
  if ( Size )
  {
    ProbeForRead_0(a1, Size, 1u);
    return RtlCopyVolatileMemory(a1, Src, Size);
  }
  return result;
}

```

## disassembly

```asm
0x14000f008  mov     [rsp+arg_0], rbx
0x14000f00d  mov     [rsp+arg_8], rsi
0x14000f012  push    rdi
0x14000f013  sub     rsp, 20h
0x14000f017  mov     rax, cs:qword_14000D450
0x14000f01e  mov     rbx, r8
0x14000f021  mov     rsi, rdx
0x14000f024  mov     rdi, rcx
0x14000f027  test    rax, rax
0x14000f02a  jz      short loc_14000F033
0x14000f02c  call    rax ; qword_14000D450
0x14000f02e  nop     dword ptr [rax]
0x14000f031  jmp     short loc_14000F054
0x14000f033  test    rbx, rbx
0x14000f036  jz      short loc_14000F054
0x14000f038  mov     r8d, 1; Alignment
0x14000f03e  mov     rdx, rbx; Length
0x14000f041  call    ProbeForRead_0
0x14000f046  mov     r8, rbx; Size
0x14000f049  mov     rdx, rsi; Src
0x14000f04c  mov     rcx, rdi; void *
0x14000f04f  call    RtlCopyVolatileMemory
0x14000f054  mov     rbx, [rsp+28h+arg_0]
0x14000f059  mov     rsi, [rsp+28h+arg_8]
0x14000f05e  add     rsp, 20h
0x14000f062  pop     rdi
0x14000f063  retn
```
