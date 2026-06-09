# RtlCopyFromUser

- ea: `0x140001514`
- end: `0x140001574`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 (*__fastcall(void *, void *Src, size_t Size))(void)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140014010`
- `0x140031a00`

## callees

- `0x1400014ff`
- `0x140001514`
- `0x14000ba50`

## pseudocode

```c
__int64 (*__fastcall RtlCopyFromUser(void *a1, void *Src, size_t Size))(void)
{
  __int64 (*result)(void); // rax

  result = _uma_functions;
  if ( _uma_functions )
    return (__int64 (*)(void))_uma_functions();
  if ( Size )
  {
    ProbeForRead_0(Src, Size, 1u);
    return (__int64 (*)(void))RtlCopyVolatileMemory(a1, Src, Size);
  }
  return result;
}

```

## disassembly

```asm
0x140001514  mov     [rsp+arg_0], rbx
0x140001519  mov     [rsp+arg_8], rsi
0x14000151e  push    rdi
0x14000151f  sub     rsp, 20h
0x140001523  mov     rax, cs:__uma_functions
0x14000152a  mov     rbx, r8
0x14000152d  mov     rdi, rdx
0x140001530  mov     rsi, rcx
0x140001533  test    rax, rax
0x140001536  jz      short loc_14000153F
0x140001538  call    rax ; __uma_functions
0x14000153a  nop     dword ptr [rax]
0x14000153d  jmp     short loc_140001563
0x14000153f  test    rbx, rbx
0x140001542  jz      short loc_140001563
0x140001544  mov     r8d, 1; Alignment
0x14000154a  mov     rdx, rbx; Length
0x14000154d  mov     rcx, rdi; Address
0x140001550  call    ProbeForRead_0
0x140001555  mov     r8, rbx; Size
0x140001558  mov     rdx, rdi; Src
0x14000155b  mov     rcx, rsi; void *
0x14000155e  call    RtlCopyVolatileMemory
0x140001563  mov     rbx, [rsp+28h+arg_0]
0x140001568  mov     rsi, [rsp+28h+arg_8]
0x14000156d  add     rsp, 20h
0x140001571  pop     rdi
0x140001572  retn
```
