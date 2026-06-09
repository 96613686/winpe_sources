# operator new(unsigned __int64)

- ea: `0x180001140`
- end: `0x180001171`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x180001f68`
- `0x1800024b0`
- `0x180002e9c`
- `0x180003a40`
- `0x180003b30`
- `0x180003c40`
- `0x180003d60`
- `0x180003e50`
- `0x180007cb8`
- `0x1800088d4`
- `0x18000a9fa`
- `0x18000ae6c`

## callees

- `0x180001140`
- `0x180001348`
- `0x180001cd7`

## import_xrefs

- `msvcrt!malloc` at `0x18000115a`
- `msvcrt!malloc` at `0x18000115a`

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
0x180001140  push    rbx
0x180001142  sub     rsp, 20h
0x180001146  mov     rbx, rcx
0x180001149  jmp     short loc_18000115A
0x18000114b  mov     rcx, rbx; Size
0x18000114e  call    _callnewh_0
0x180001153  test    eax, eax
0x180001155  jz      short loc_18000116B
0x180001157  mov     rcx, rbx; Size
0x18000115a  call    cs:__imp_malloc
0x180001160  test    rax, rax
0x180001163  jz      short loc_18000114B
0x180001165  add     rsp, 20h
0x180001169  pop     rbx
0x18000116a  retn
0x18000116b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
