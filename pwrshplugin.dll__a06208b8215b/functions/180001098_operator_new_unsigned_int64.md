# operator new(unsigned __int64)

- ea: `0x180001098`
- end: `0x1800010c9`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x180001318`
- `0x180002170`
- `0x180002fac`
- `0x180003158`
- `0x180003a68`
- `0x180003f0c`
- `0x180004370`
- `0x180004960`
- `0x180004a18`
- `0x1800050b0`
- `0x180005500`
- `0x180005ba0`
- `0x180005e70`
- `0x180007428`
- `0x180009df3`
- `0x180009f4f`

## callees

- `0x180001098`
- `0x180001238`
- `0x180001db4`

## import_xrefs

- `msvcrt!malloc` at `0x1800010b2`
- `msvcrt!malloc` at `0x1800010b2`

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
0x180001098  push    rbx
0x18000109a  sub     rsp, 20h
0x18000109e  mov     rbx, rcx
0x1800010a1  jmp     short loc_1800010B2
0x1800010a3  mov     rcx, rbx; Size
0x1800010a6  call    _callnewh_0
0x1800010ab  test    eax, eax
0x1800010ad  jz      short loc_1800010C3
0x1800010af  mov     rcx, rbx; Size
0x1800010b2  call    cs:__imp_malloc
0x1800010b8  test    rax, rax
0x1800010bb  jz      short loc_1800010A3
0x1800010bd  add     rsp, 20h
0x1800010c1  pop     rbx
0x1800010c2  retn
0x1800010c3  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
