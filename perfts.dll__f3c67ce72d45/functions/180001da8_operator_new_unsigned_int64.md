# operator new(unsigned __int64)

- ea: `0x180001da8`
- end: `0x180001dd9`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180001f88`
- `0x1800026b0`
- `0x180004d5c`
- `0x180004e40`
- `0x1800058b8`
- `0x180007668`
- `0x180008074`
- `0x180008e9c`
- `0x180008edc`
- `0x180009d27`

## callees

- `0x180001da8`
- `0x1800020e8`
- `0x180002796`

## import_xrefs

- `msvcrt!malloc` at `0x180001dc2`
- `msvcrt!malloc` at `0x180001dc2`

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
0x180001da8  push    rbx
0x180001daa  sub     rsp, 20h
0x180001dae  mov     rbx, rcx
0x180001db1  jmp     short loc_180001DC2
0x180001db3  mov     rcx, rbx; Size
0x180001db6  call    _callnewh_0
0x180001dbb  test    eax, eax
0x180001dbd  jz      short loc_180001DD3
0x180001dbf  mov     rcx, rbx; Size
0x180001dc2  call    cs:__imp_malloc
0x180001dc8  test    rax, rax
0x180001dcb  jz      short loc_180001DB3
0x180001dcd  add     rsp, 20h
0x180001dd1  pop     rbx
0x180001dd2  retn
0x180001dd3  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
