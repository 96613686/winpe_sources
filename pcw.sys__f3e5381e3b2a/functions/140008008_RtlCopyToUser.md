# RtlCopyToUser

- ea: `0x140008008`
- end: `0x140008065`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140002020`
- `0x140008fb0`
- `0x14000ba08`

## callees

- `0x1400010af`
- `0x1400013a0`
- `0x140008008`

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
0x140008008  mov     [rsp+arg_0], rbx
0x14000800d  mov     [rsp+arg_8], rsi
0x140008012  push    rdi
0x140008013  sub     rsp, 20h
0x140008017  mov     rax, cs:qword_140006390
0x14000801e  mov     rbx, r8
0x140008021  mov     rsi, rdx
0x140008024  mov     rdi, rcx
0x140008027  test    rax, rax
0x14000802a  jz      short loc_140008033
0x14000802c  call    rax ; qword_140006390
0x14000802e  nop     dword ptr [rax]
0x140008031  jmp     short loc_140008054
0x140008033  test    rbx, rbx
0x140008036  jz      short loc_140008054
0x140008038  mov     r8d, 1; Alignment
0x14000803e  mov     rdx, rbx; Length
0x140008041  call    ProbeForRead_0
0x140008046  mov     r8, rbx; Size
0x140008049  mov     rdx, rsi; Src
0x14000804c  mov     rcx, rdi; void *
0x14000804f  call    RtlCopyVolatileMemory
0x140008054  mov     rbx, [rsp+28h+arg_0]
0x140008059  mov     rsi, [rsp+28h+arg_8]
0x14000805e  add     rsp, 20h
0x140008062  pop     rdi
0x140008063  retn
```
