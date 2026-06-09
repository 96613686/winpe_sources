# RtlCopyFromUser

- ea: `0x1400010c4`
- end: `0x140001124`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140002010`
- `0x140009a08`
- `0x140009b60`

## callees

- `0x1400010af`
- `0x1400010c4`
- `0x1400013a0`

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
0x1400010c4  mov     [rsp+arg_0], rbx
0x1400010c9  mov     [rsp+arg_8], rsi
0x1400010ce  push    rdi
0x1400010cf  sub     rsp, 20h
0x1400010d3  mov     rax, cs:__uma_functions
0x1400010da  mov     rbx, r8
0x1400010dd  mov     rdi, rdx
0x1400010e0  mov     rsi, rcx
0x1400010e3  test    rax, rax
0x1400010e6  jz      short loc_1400010EF
0x1400010e8  call    rax ; __uma_functions
0x1400010ea  nop     dword ptr [rax]
0x1400010ed  jmp     short loc_140001113
0x1400010ef  test    rbx, rbx
0x1400010f2  jz      short loc_140001113
0x1400010f4  mov     r8d, 1; Alignment
0x1400010fa  mov     rdx, rbx; Length
0x1400010fd  mov     rcx, rdi; Address
0x140001100  call    ProbeForRead_0
0x140001105  mov     r8, rbx; Size
0x140001108  mov     rdx, rdi; Src
0x14000110b  mov     rcx, rsi; void *
0x14000110e  call    RtlCopyVolatileMemory
0x140001113  mov     rbx, [rsp+28h+arg_0]
0x140001118  mov     rsi, [rsp+28h+arg_8]
0x14000111d  add     rsp, 20h
0x140001121  pop     rdi
0x140001122  retn
```
