# operator new(unsigned __int64)

- ea: `0x140001c34`
- end: `0x140001c65`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140002aa0`
- `0x140009d10`
- `0x1400142a8`
- `0x1400147f0`
- `0x140015294`
- `0x140015bea`
- `0x140015fa6`

## callees

- `0x140001c34`
- `0x140001e38`
- `0x1400023ac`

## import_xrefs

- `msvcrt!malloc` at `0x140001c4e`
- `msvcrt!malloc` at `0x140001c4e`

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
0x140001c34  push    rbx
0x140001c36  sub     rsp, 20h
0x140001c3a  mov     rbx, rcx
0x140001c3d  jmp     short loc_140001C4E
0x140001c3f  mov     rcx, rbx; Size
0x140001c42  call    _callnewh_0
0x140001c47  test    eax, eax
0x140001c49  jz      short loc_140001C5F
0x140001c4b  mov     rcx, rbx; Size
0x140001c4e  call    cs:__imp_malloc
0x140001c54  test    rax, rax
0x140001c57  jz      short loc_140001C3F
0x140001c59  add     rsp, 20h
0x140001c5d  pop     rbx
0x140001c5e  retn
0x140001c5f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
