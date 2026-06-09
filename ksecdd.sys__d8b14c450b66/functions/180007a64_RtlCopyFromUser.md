# RtlCopyFromUser

- ea: `0x180007a64`
- end: `0x180007ac4`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x180004e7c`
- `0x180005160`
- `0x180005e94`
- `0x18000cbb4`
- `0x18000d01c`
- `0x18000d2f0`
- `0x18000d574`
- `0x18000d664`
- `0x18000d86c`
- `0x18000d94c`
- `0x18000da6c`
- `0x180012010`

## callees

- `0x180007a4f`
- `0x180007a64`
- `0x180010870`

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
0x180007a64  mov     [rsp+arg_0], rbx
0x180007a69  mov     [rsp+arg_8], rsi
0x180007a6e  push    rdi
0x180007a6f  sub     rsp, 20h
0x180007a73  mov     rax, cs:__uma_functions
0x180007a7a  mov     rbx, r8
0x180007a7d  mov     rdi, rdx
0x180007a80  mov     rsi, rcx
0x180007a83  test    rax, rax
0x180007a86  jz      short loc_180007A8F
0x180007a88  call    rax ; __uma_functions
0x180007a8a  nop     dword ptr [rax]
0x180007a8d  jmp     short loc_180007AB3
0x180007a8f  test    rbx, rbx
0x180007a92  jz      short loc_180007AB3
0x180007a94  mov     r8d, 1; Alignment
0x180007a9a  mov     rdx, rbx; Length
0x180007a9d  mov     rcx, rdi; Address
0x180007aa0  call    ProbeForRead_0
0x180007aa5  mov     r8, rbx; Size
0x180007aa8  mov     rdx, rdi; Src
0x180007aab  mov     rcx, rsi; void *
0x180007aae  call    RtlCopyVolatileMemory
0x180007ab3  mov     rbx, [rsp+28h+arg_0]
0x180007ab8  mov     rsi, [rsp+28h+arg_8]
0x180007abd  add     rsp, 20h
0x180007ac1  pop     rdi
0x180007ac2  retn
```
