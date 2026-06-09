# RtlCopyFromUser

- ea: `0x140001ad4`
- end: `0x140001b34`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 (*__fastcall(void *, void *Src, size_t Size))(void)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140003010`
- `0x14000d314`
- `0x14000deb8`
- `0x140010890`

## callees

- `0x140001abf`
- `0x140001ad4`
- `0x140001e40`

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
0x140001ad4  mov     [rsp+arg_0], rbx
0x140001ad9  mov     [rsp+arg_8], rsi
0x140001ade  push    rdi
0x140001adf  sub     rsp, 20h
0x140001ae3  mov     rax, cs:__uma_functions
0x140001aea  mov     rbx, r8
0x140001aed  mov     rdi, rdx
0x140001af0  mov     rsi, rcx
0x140001af3  test    rax, rax
0x140001af6  jz      short loc_140001AFF
0x140001af8  call    rax ; __uma_functions
0x140001afa  nop     dword ptr [rax]
0x140001afd  jmp     short loc_140001B23
0x140001aff  test    rbx, rbx
0x140001b02  jz      short loc_140001B23
0x140001b04  mov     r8d, 1; Alignment
0x140001b0a  mov     rdx, rbx; Length
0x140001b0d  mov     rcx, rdi; Address
0x140001b10  call    ProbeForRead_0
0x140001b15  mov     r8, rbx; Size
0x140001b18  mov     rdx, rdi; Src
0x140001b1b  mov     rcx, rsi; void *
0x140001b1e  call    RtlCopyVolatileMemory
0x140001b23  mov     rbx, [rsp+28h+arg_0]
0x140001b28  mov     rsi, [rsp+28h+arg_8]
0x140001b2d  add     rsp, 20h
0x140001b31  pop     rdi
0x140001b32  retn
```
