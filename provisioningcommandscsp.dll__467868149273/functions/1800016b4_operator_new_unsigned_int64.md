# operator new(unsigned __int64)

- ea: `0x1800016b4`
- end: `0x1800016e5`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180002208`
- `0x180005be8`
- `0x180006240`
- `0x1800064e0`
- `0x180007a08`
- `0x180007a64`
- `0x18000c0d0`
- `0x18000c12c`
- `0x18000d4d2`
- `0x18000d768`

## callees

- `0x1800016b4`
- `0x180001dc6`
- `0x180001dd2`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800016de`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800016de`

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
      JUMPOUT(0x1800016E4LL);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800016b4  push    rbx
0x1800016b6  sub     rsp, 20h
0x1800016ba  mov     rbx, rcx
0x1800016bd  jmp     short loc_1800016CE
0x1800016bf  mov     rcx, rbx; Size
0x1800016c2  call    _callnewh_0
0x1800016c7  test    eax, eax
0x1800016c9  jz      short loc_1800016DE
0x1800016cb  mov     rcx, rbx; Size
0x1800016ce  call    malloc_0
0x1800016d3  test    rax, rax
0x1800016d6  jz      short loc_1800016BF
0x1800016d8  add     rsp, 20h
0x1800016dc  pop     rbx
0x1800016dd  retn
0x1800016de  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
