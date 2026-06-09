# RtlCopyToUser

- ea: `0x140021008`
- end: `0x140021065`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `void *__fastcall(void *, void *Src, size_t Size)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x140014020`
- `0x1400260a4`
- `0x1400266ec`
- `0x140026d94`
- `0x140027144`
- `0x1400277f4`
- `0x140027ca0`
- `0x140027f64`
- `0x140028048`
- `0x140031a00`

## callees

- `0x1400014ff`
- `0x14000ba50`
- `0x140021008`

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
0x140021008  mov     [rsp+arg_0], rbx
0x14002100d  mov     [rsp+arg_8], rsi
0x140021012  push    rdi
0x140021013  sub     rsp, 20h
0x140021017  mov     rax, cs:qword_14001D850
0x14002101e  mov     rbx, r8
0x140021021  mov     rsi, rdx
0x140021024  mov     rdi, rcx
0x140021027  test    rax, rax
0x14002102a  jz      short loc_140021033
0x14002102c  call    rax ; qword_14001D850
0x14002102e  nop     dword ptr [rax]
0x140021031  jmp     short loc_140021054
0x140021033  test    rbx, rbx
0x140021036  jz      short loc_140021054
0x140021038  mov     r8d, 1; Alignment
0x14002103e  mov     rdx, rbx; Length
0x140021041  call    ProbeForRead_0
0x140021046  mov     r8, rbx; Size
0x140021049  mov     rdx, rsi; Src
0x14002104c  mov     rcx, rdi; void *
0x14002104f  call    RtlCopyVolatileMemory
0x140021054  mov     rbx, [rsp+28h+arg_0]
0x140021059  mov     rsi, [rsp+28h+arg_8]
0x14002105e  add     rsp, 20h
0x140021062  pop     rdi
0x140021063  retn
```
