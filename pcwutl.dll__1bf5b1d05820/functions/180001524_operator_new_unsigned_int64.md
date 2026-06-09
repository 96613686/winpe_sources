# operator new(unsigned __int64)

- ea: `0x180001524`
- end: `0x180001555`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800016f8`
- `0x180005a6c`
- `0x1800063a0`
- `0x180019303`

## callees

- `0x180001524`
- `0x180001858`
- `0x180002759`

## import_xrefs

- `msvcrt!malloc` at `0x18000153e`
- `msvcrt!malloc` at `0x18000153e`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = malloc(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
      std::_Xbad_alloc();
  }
  return result;
}

```

## disassembly

```asm
0x180001524  push    rbx
0x180001526  sub     rsp, 20h
0x18000152a  mov     rbx, rcx
0x18000152d  jmp     short loc_18000153E
0x18000152f  mov     rcx, rbx; Size
0x180001532  call    _callnewh_0
0x180001537  test    eax, eax
0x180001539  jz      short loc_18000154F
0x18000153b  mov     rcx, rbx; Size
0x18000153e  call    cs:__imp_malloc
0x180001544  test    rax, rax
0x180001547  jz      short loc_18000152F
0x180001549  add     rsp, 20h
0x18000154d  pop     rbx
0x18000154e  retn
0x18000154f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
