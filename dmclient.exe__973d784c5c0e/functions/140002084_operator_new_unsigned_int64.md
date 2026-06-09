# operator new(unsigned __int64)

- ea: `0x140002084`
- end: `0x1400020b5`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140002618`
- `0x14000be28`
- `0x14000be68`
- `0x14000ff24`
- `0x14000ff70`
- `0x1400199ac`
- `0x140019a9d`

## callees

- `0x140002084`
- `0x140002228`
- `0x140002786`

## import_xrefs

- `msvcrt!malloc` at `0x14000209e`
- `msvcrt!malloc` at `0x14000209e`

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
0x140002084  push    rbx
0x140002086  sub     rsp, 20h
0x14000208a  mov     rbx, rcx
0x14000208d  jmp     short loc_14000209E
0x14000208f  mov     rcx, rbx; Size
0x140002092  call    _callnewh_0
0x140002097  test    eax, eax
0x140002099  jz      short loc_1400020AF
0x14000209b  mov     rcx, rbx; Size
0x14000209e  call    cs:__imp_malloc
0x1400020a4  test    rax, rax
0x1400020a7  jz      short loc_14000208F
0x1400020a9  add     rsp, 20h
0x1400020ad  pop     rbx
0x1400020ae  retn
0x1400020af  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
