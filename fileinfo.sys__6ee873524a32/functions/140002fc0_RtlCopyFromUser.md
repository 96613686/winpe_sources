# RtlCopyFromUser

- ea: `0x140002fc0`
- end: `0x140003020`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140005010`
- `0x14000d8cc`

## callees

- `0x140002fc0`
- `0x140003046`
- `0x140003950`

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
0x140002fc0  mov     [rsp+arg_0], rbx
0x140002fc5  mov     [rsp+arg_8], rsi
0x140002fca  push    rdi
0x140002fcb  sub     rsp, 20h
0x140002fcf  mov     rax, cs:__uma_functions
0x140002fd6  mov     rbx, r8
0x140002fd9  mov     rdi, rdx
0x140002fdc  mov     rsi, rcx
0x140002fdf  test    rax, rax
0x140002fe2  jz      short loc_140002FEB
0x140002fe4  call    rax ; __uma_functions
0x140002fe6  nop     dword ptr [rax]
0x140002fe9  jmp     short loc_14000300F
0x140002feb  test    rbx, rbx
0x140002fee  jz      short loc_14000300F
0x140002ff0  mov     r8d, 1; Alignment
0x140002ff6  mov     rdx, rbx; Length
0x140002ff9  mov     rcx, rdi; Address
0x140002ffc  call    ProbeForRead_0
0x140003001  mov     r8, rbx; Size
0x140003004  mov     rdx, rdi; Src
0x140003007  mov     rcx, rsi; void *
0x14000300a  call    RtlCopyVolatileMemory
0x14000300f  mov     rbx, [rsp+28h+arg_0]
0x140003014  mov     rsi, [rsp+28h+arg_8]
0x140003019  add     rsp, 20h
0x14000301d  pop     rdi
0x14000301e  retn
```
