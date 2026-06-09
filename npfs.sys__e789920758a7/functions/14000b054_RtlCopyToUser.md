# RtlCopyToUser

- ea: `0x14000b054`
- end: `0x14000b0b1`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `void *__fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140003020`
- `0x14000e1b0`
- `0x140014ed4`

## callees

- `0x140001abf`
- `0x140001e40`
- `0x14000b054`

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
0x14000b054  mov     [rsp+arg_0], rbx
0x14000b059  mov     [rsp+arg_8], rsi
0x14000b05e  push    rdi
0x14000b05f  sub     rsp, 20h
0x14000b063  mov     rax, cs:qword_140008390
0x14000b06a  mov     rbx, r8
0x14000b06d  mov     rsi, rdx
0x14000b070  mov     rdi, rcx
0x14000b073  test    rax, rax
0x14000b076  jz      short loc_14000B07F
0x14000b078  call    rax ; qword_140008390
0x14000b07a  nop     dword ptr [rax]
0x14000b07d  jmp     short loc_14000B0A0
0x14000b07f  test    rbx, rbx
0x14000b082  jz      short loc_14000B0A0
0x14000b084  mov     r8d, 1; Alignment
0x14000b08a  mov     rdx, rbx; Length
0x14000b08d  call    ProbeForRead_0
0x14000b092  mov     r8, rbx; Size
0x14000b095  mov     rdx, rsi; Src
0x14000b098  mov     rcx, rdi; void *
0x14000b09b  call    RtlCopyVolatileMemory
0x14000b0a0  mov     rbx, [rsp+28h+arg_0]
0x14000b0a5  mov     rsi, [rsp+28h+arg_8]
0x14000b0aa  add     rsp, 20h
0x14000b0ae  pop     rdi
0x14000b0af  retn
```
