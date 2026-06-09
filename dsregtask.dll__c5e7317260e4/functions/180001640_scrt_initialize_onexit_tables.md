# __scrt_initialize_onexit_tables

- ea: `0x180001640`
- end: `0x1800016cb`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: `char __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001500`

## callees

- `0x180001640`
- `0x180001954`
- `0x180001c98`
- `0x180001d4e`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_180008150 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5u);
    if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_180008138._first = *(_OWORD *)&Table._first;
      stru_180008138._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_180008138) )
    {
      return 0;
    }
    byte_180008150 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180001640  push    rbx
0x180001642  sub     rsp, 20h
0x180001646  cmp     cs:byte_180008150, 0
0x18000164d  mov     ebx, ecx
0x18000164f  jnz     short loc_1800016B8
0x180001651  cmp     ecx, 1
0x180001654  ja      short loc_1800016C0
0x180001656  call    __scrt_is_ucrt_dll_in_use
0x18000165b  test    eax, eax
0x18000165d  jz      short loc_180001687
0x18000165f  test    ebx, ebx
0x180001661  jnz     short loc_180001687
0x180001663  lea     rcx, Table; Table
0x18000166a  call    _initialize_onexit_table
0x18000166f  test    eax, eax
0x180001671  jnz     short loc_180001683
0x180001673  lea     rcx, stru_180008138; Table
0x18000167a  call    _initialize_onexit_table
0x18000167f  test    eax, eax
0x180001681  jz      short loc_1800016B1
0x180001683  xor     al, al
0x180001685  jmp     short loc_1800016BA
0x180001687  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000168f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001693  movdqu  xmmword ptr cs:Table._first, xmm0
0x18000169b  mov     cs:Table._end, rax
0x1800016a2  movdqu  xmmword ptr cs:stru_180008138._first, xmm0
0x1800016aa  mov     cs:stru_180008138._end, rax
0x1800016b1  mov     cs:byte_180008150, 1
0x1800016b8  mov     al, 1
0x1800016ba  add     rsp, 20h
0x1800016be  pop     rbx
0x1800016bf  retn
0x1800016c0  mov     ecx, 5
0x1800016c5  call    __scrt_fastfail
```
