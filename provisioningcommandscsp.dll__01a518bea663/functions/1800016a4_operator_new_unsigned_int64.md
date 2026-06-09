# operator new(unsigned __int64)

- ea: `0x1800016a4`
- end: `0x1800016d5`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x1800021f8`
- `0x180005a0c`
- `0x180005f70`
- `0x1800061f0`
- `0x180007698`
- `0x1800076ec`
- `0x18000ba18`
- `0x18000ba6c`
- `0x18000ce12`
- `0x18000d0a2`

## callees

- `0x1800016a4`
- `0x180001db6`
- `0x180001dc2`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800016ce`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800016ce`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = malloc_0(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
    {
      std::_Xbad_alloc();
      JUMPOUT(0x1800016D4LL);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800016a4  push    rbx
0x1800016a6  sub     rsp, 20h
0x1800016aa  mov     rbx, rcx
0x1800016ad  jmp     short loc_1800016BE
0x1800016af  mov     rcx, rbx; Size
0x1800016b2  call    _callnewh_0
0x1800016b7  test    eax, eax
0x1800016b9  jz      short loc_1800016CE
0x1800016bb  mov     rcx, rbx; Size
0x1800016be  call    malloc_0
0x1800016c3  test    rax, rax
0x1800016c6  jz      short loc_1800016AF
0x1800016c8  add     rsp, 20h
0x1800016cc  pop     rbx
0x1800016cd  retn
0x1800016ce  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
