# operator new(unsigned __int64)

- ea: `0x140002060`
- end: `0x140002091`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1400025f8`
- `0x14000ba8c`
- `0x14000bacc`
- `0x14000f964`
- `0x14000f9b0`
- `0x140018b7b`
- `0x140018c6c`

## callees

- `0x140002060`
- `0x140002208`
- `0x140002766`

## import_xrefs

- `msvcrt!malloc` at `0x14000207a`
- `msvcrt!malloc` at `0x14000207a`

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
0x140002060  push    rbx
0x140002062  sub     rsp, 20h
0x140002066  mov     rbx, rcx
0x140002069  jmp     short loc_14000207A
0x14000206b  mov     rcx, rbx; Size
0x14000206e  call    _callnewh_0
0x140002073  test    eax, eax
0x140002075  jz      short loc_14000208B
0x140002077  mov     rcx, rbx; Size
0x14000207a  call    cs:__imp_malloc
0x140002080  test    rax, rax
0x140002083  jz      short loc_14000206B
0x140002085  add     rsp, 20h
0x140002089  pop     rbx
0x14000208a  retn
0x14000208b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
