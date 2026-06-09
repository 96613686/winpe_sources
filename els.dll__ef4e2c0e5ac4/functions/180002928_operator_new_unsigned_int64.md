# operator new(unsigned __int64)

- ea: `0x180002928`
- end: `0x180002959`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `30`
- callee_count: `3`
- tags: ``

## callers

- `0x180001974`
- `0x180002bb8`
- `0x180003398`
- `0x1800038fc`
- `0x180004380`
- `0x180004a24`
- `0x180004b7c`
- `0x180004fb0`
- `0x180005a10`
- `0x180005ab0`
- `0x180006340`
- `0x180006930`
- `0x18000728c`
- `0x180007488`
- `0x1800075f0`
- `0x180007a08`
- `0x180007bd8`
- `0x18000c728`
- `0x180015f90`
- `0x180016084`
- `0x1800179a0`
- `0x180018154`
- `0x1800183e0`
- `0x18001b3f8`
- `0x18001cac0`
- `0x18001d134`
- `0x18001d42c`
- `0x180021584`
- `0x1800223ab`
- `0x180023293`

## callees

- `0x180002928`
- `0x180002ad8`
- `0x180003636`

## import_xrefs

- `msvcrt!malloc` at `0x180002942`
- `msvcrt!malloc` at `0x180002942`

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
0x180002928  push    rbx
0x18000292a  sub     rsp, 20h
0x18000292e  mov     rbx, rcx
0x180002931  jmp     short loc_180002942
0x180002933  mov     rcx, rbx; Size
0x180002936  call    _callnewh_0
0x18000293b  test    eax, eax
0x18000293d  jz      short loc_180002953
0x18000293f  mov     rcx, rbx; Size
0x180002942  call    cs:__imp_malloc
0x180002948  test    rax, rax
0x18000294b  jz      short loc_180002933
0x18000294d  add     rsp, 20h
0x180002951  pop     rbx
0x180002952  retn
0x180002953  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
