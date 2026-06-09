# operator new(unsigned __int64)

- ea: `0x180001250`
- end: `0x180001281`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180001244`
- `0x180001428`
- `0x180006368`
- `0x180006490`
- `0x180009b28`
- `0x18000d67c`
- `0x18000eb94`
- `0x18000ebd4`
- `0x180011453`

## callees

- `0x180001250`
- `0x180001588`
- `0x18000267a`

## import_xrefs

- `msvcrt!malloc` at `0x18000126a`
- `msvcrt!malloc` at `0x18000126a`

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
0x180001250  push    rbx
0x180001252  sub     rsp, 20h
0x180001256  mov     rbx, rcx
0x180001259  jmp     short loc_18000126A
0x18000125b  mov     rcx, rbx; Size
0x18000125e  call    _callnewh_0
0x180001263  test    eax, eax
0x180001265  jz      short loc_18000127B
0x180001267  mov     rcx, rbx; Size
0x18000126a  call    cs:__imp_malloc
0x180001270  test    rax, rax
0x180001273  jz      short loc_18000125B
0x180001275  add     rsp, 20h
0x180001279  pop     rbx
0x18000127a  retn
0x18000127b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
