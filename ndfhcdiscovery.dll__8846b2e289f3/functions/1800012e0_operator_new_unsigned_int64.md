# operator new(unsigned __int64)

- ea: `0x1800012e0`
- end: `0x180001311`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `23`
- callee_count: `3`
- tags: ``

## callers

- `0x180001568`
- `0x180001f34`
- `0x18000354c`
- `0x180006a6c`
- `0x180006b84`
- `0x180006c9c`
- `0x180006d90`
- `0x180009fcc`
- `0x18000a00c`
- `0x18000a04c`
- `0x18000a098`
- `0x18000a0e4`
- `0x18000c5d0`
- `0x180010984`
- `0x1800109c4`
- `0x180010a8c`
- `0x180010b18`
- `0x180010c18`
- `0x180010d18`
- `0x180010e0c`
- `0x180010eac`
- `0x180013af1`
- `0x180013ed8`

## callees

- `0x1800012e0`
- `0x180001488`
- `0x180001f67`

## import_xrefs

- `msvcrt!malloc` at `0x1800012fa`
- `msvcrt!malloc` at `0x1800012fa`

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
0x1800012e0  push    rbx
0x1800012e2  sub     rsp, 20h
0x1800012e6  mov     rbx, rcx
0x1800012e9  jmp     short loc_1800012FA
0x1800012eb  mov     rcx, rbx; Size
0x1800012ee  call    _callnewh_0
0x1800012f3  test    eax, eax
0x1800012f5  jz      short loc_18000130B
0x1800012f7  mov     rcx, rbx; Size
0x1800012fa  call    cs:__imp_malloc
0x180001300  test    rax, rax
0x180001303  jz      short loc_1800012EB
0x180001305  add     rsp, 20h
0x180001309  pop     rbx
0x18000130a  retn
0x18000130b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
