# std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)

- ea: `0x180008b7c`
- end: `0x180008bd3`
- name: `??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z`
- size: `87`
- prototype: `_QWORD *__fastcall(size_t)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x180008bdc`
- `0x180008c88`
- `0x180008eb0`
- `0x180008f68`
- `0x1800095fc`
- `0x1800096ac`
- `0x18000983c`
- `0x180009d28`
- `0x18000bd10`
- `0x18000d114`
- `0x18000d2c0`
- `0x18000d578`
- `0x18000d824`
- `0x18000d8e8`
- `0x18000da04`

## callees

- `0x180002334`
- `0x180008b7c`
- `0x18000c45c`

## pseudocode

```c
_QWORD *__fastcall std::_Allocate<16,std::_Default_allocate_traits>(size_t a1)
{
  _QWORD *result; // rax
  void *v2; // rax
  void *v3; // rcx

  if ( !a1 )
    return 0;
  if ( a1 < 0x1000 )
    return operator new(a1);
  if ( a1 + 39 < a1 )
    std::_Throw_bad_array_new_length();
  v2 = operator new(a1 + 39);
  v3 = v2;
  if ( !v2 )
    __fastfail(5u);
  result = (_QWORD *)(((unsigned __int64)v2 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(result - 1) = v3;
  return result;
}

```

## disassembly

```asm
0x180008b7c  sub     rsp, 28h
0x180008b80  test    rcx, rcx
0x180008b83  jnz     short loc_180008B8C
0x180008b85  xor     eax, eax
0x180008b87  add     rsp, 28h
0x180008b8b  retn
0x180008b8c  cmp     rcx, 1000h
0x180008b93  jb      short loc_180008BC4
0x180008b95  lea     rax, [rcx+27h]
0x180008b99  cmp     rax, rcx
0x180008b9c  jbe     short loc_180008BCD
0x180008b9e  mov     rcx, rax; Size
0x180008ba1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008ba6  mov     rcx, rax
0x180008ba9  test    rax, rax
0x180008bac  jnz     short loc_180008BB3
0x180008bae  lea     ecx, [rax+5]; Size
0x180008bb1  int     29h; Win8: RtlFailFast(ecx)
0x180008bb3  add     rax, 27h ; '''
0x180008bb7  and     rax, 0FFFFFFFFFFFFFFE0h
0x180008bbb  mov     [rax-8], rcx
0x180008bbf  add     rsp, 28h
0x180008bc3  retn
0x180008bc4  add     rsp, 28h
0x180008bc8  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008bcd  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
