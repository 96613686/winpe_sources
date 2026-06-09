# operator new(unsigned __int64)

- ea: `0x180001370`
- end: `0x1800013a1`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `35`
- callee_count: `3`
- tags: ``

## callers

- `0x1800015f8`
- `0x180002bb8`
- `0x180002cb0`
- `0x180004f54`
- `0x180004f94`
- `0x180004fd4`
- `0x180005020`
- `0x1800050d4`
- `0x1800051a8`
- `0x18000527c`
- `0x180005350`
- `0x180005b8c`
- `0x180006350`
- `0x18000c250`
- `0x18000c4a0`
- `0x18000c70c`
- `0x18000cca0`
- `0x18000d68c`
- `0x18000d840`
- `0x18000dba0`
- `0x18000e0b8`
- `0x18000e2a8`
- `0x18000f2f0`
- `0x18000f3f0`
- `0x18000f5b0`
- `0x18000f698`
- `0x18000f7e8`
- `0x18000f8fc`
- `0x18000fa4c`
- `0x18000fb44`
- `0x18000fc5c`
- `0x18000fd50`
- `0x18000fef0`
- `0x180012f73`
- `0x180012feb`

## callees

- `0x180001370`
- `0x180001518`
- `0x180001eed`

## import_xrefs

- `msvcrt!malloc` at `0x18000138a`
- `msvcrt!malloc` at `0x18000138a`

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
0x180001370  push    rbx
0x180001372  sub     rsp, 20h
0x180001376  mov     rbx, rcx
0x180001379  jmp     short loc_18000138A
0x18000137b  mov     rcx, rbx; Size
0x18000137e  call    _callnewh_0
0x180001383  test    eax, eax
0x180001385  jz      short loc_18000139B
0x180001387  mov     rcx, rbx; Size
0x18000138a  call    cs:__imp_malloc
0x180001390  test    rax, rax
0x180001393  jz      short loc_18000137B
0x180001395  add     rsp, 20h
0x180001399  pop     rbx
0x18000139a  retn
0x18000139b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
