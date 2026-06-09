# RtlCopyFromUser

- ea: `0x140001154`
- end: `0x1400011b4`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140002010`
- `0x140008f04`
- `0x140008fb4`
- `0x14000ca90`
- `0x14000cc10`
- `0x14000cd40`
- `0x14000d4a0`

## callees

- `0x14000113f`
- `0x140001154`
- `0x140001500`

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
0x140001154  mov     [rsp+arg_0], rbx
0x140001159  mov     [rsp+arg_8], rsi
0x14000115e  push    rdi
0x14000115f  sub     rsp, 20h
0x140001163  mov     rax, cs:__uma_functions
0x14000116a  mov     rbx, r8
0x14000116d  mov     rdi, rdx
0x140001170  mov     rsi, rcx
0x140001173  test    rax, rax
0x140001176  jz      short loc_14000117F
0x140001178  call    rax ; __uma_functions
0x14000117a  nop     dword ptr [rax]
0x14000117d  jmp     short loc_1400011A3
0x14000117f  test    rbx, rbx
0x140001182  jz      short loc_1400011A3
0x140001184  mov     r8d, 1; Alignment
0x14000118a  mov     rdx, rbx; Length
0x14000118d  mov     rcx, rdi; Address
0x140001190  call    ProbeForRead_0
0x140001195  mov     r8, rbx; Size
0x140001198  mov     rdx, rdi; Src
0x14000119b  mov     rcx, rsi; void *
0x14000119e  call    RtlCopyVolatileMemory
0x1400011a3  mov     rbx, [rsp+28h+arg_0]
0x1400011a8  mov     rsi, [rsp+28h+arg_8]
0x1400011ad  add     rsp, 20h
0x1400011b1  pop     rdi
0x1400011b2  retn
```
