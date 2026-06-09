# operator new(unsigned __int64)

- ea: `0x140001510`
- end: `0x140001541`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400024fc`
- `0x140002f5c`
- `0x1400117c7`

## callees

- `0x140001510`
- `0x1400016b8`
- `0x140001f7d`

## import_xrefs

- `msvcrt!malloc` at `0x14000152a`
- `msvcrt!malloc` at `0x14000152a`

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
0x140001510  push    rbx
0x140001512  sub     rsp, 20h
0x140001516  mov     rbx, rcx
0x140001519  jmp     short loc_14000152A
0x14000151b  mov     rcx, rbx; Size
0x14000151e  call    _callnewh_0
0x140001523  test    eax, eax
0x140001525  jz      short loc_14000153B
0x140001527  mov     rcx, rbx; Size
0x14000152a  call    cs:__imp_malloc
0x140001530  test    rax, rax
0x140001533  jz      short loc_14000151B
0x140001535  add     rsp, 20h
0x140001539  pop     rbx
0x14000153a  retn
0x14000153b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
