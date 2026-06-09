# std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)

- ea: `0x14000dc84`
- end: `0x14000dcdb`
- name: `??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z`
- size: `87`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000dce4`
- `0x14000dd14`
- `0x14000dd48`
- `0x14000dea0`

## callees

- `0x140005db8`
- `0x14000dc84`
- `0x14000f0fc`

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
0x14000dc84  sub     rsp, 28h
0x14000dc88  test    rcx, rcx
0x14000dc8b  jnz     short loc_14000DC94
0x14000dc8d  xor     eax, eax
0x14000dc8f  add     rsp, 28h
0x14000dc93  retn
0x14000dc94  cmp     rcx, 1000h
0x14000dc9b  jb      short loc_14000DCCC
0x14000dc9d  lea     rax, [rcx+27h]
0x14000dca1  cmp     rax, rcx
0x14000dca4  jbe     short loc_14000DCD5
0x14000dca6  mov     rcx, rax; Size
0x14000dca9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000dcae  mov     rcx, rax
0x14000dcb1  test    rax, rax
0x14000dcb4  jnz     short loc_14000DCBB
0x14000dcb6  lea     ecx, [rax+5]; Size
0x14000dcb9  int     29h; Win8: RtlFailFast(ecx)
0x14000dcbb  add     rax, 27h ; '''
0x14000dcbf  and     rax, 0FFFFFFFFFFFFFFE0h
0x14000dcc3  mov     [rax-8], rcx
0x14000dcc7  add     rsp, 28h
0x14000dccb  retn
0x14000dccc  add     rsp, 28h
0x14000dcd0  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000dcd5  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
