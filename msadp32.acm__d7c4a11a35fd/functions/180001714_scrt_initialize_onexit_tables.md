# __scrt_initialize_onexit_tables

- ea: `0x180001714`
- end: `0x18000179f`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800015d4`

## callees

- `0x180001714`
- `0x1800018b4`
- `0x180001bf8`
- `0x180001c7a`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_1800080F0 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5);
    if ( !_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_1800080D8._first = *(_OWORD *)&Table._first;
      stru_1800080D8._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_1800080D8) )
    {
      return 0;
    }
    byte_1800080F0 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180001714  push    rbx
0x180001716  sub     rsp, 20h
0x18000171a  cmp     cs:byte_1800080F0, 0
0x180001721  mov     ebx, ecx
0x180001723  jnz     short loc_18000178C
0x180001725  cmp     ecx, 1
0x180001728  ja      short loc_180001794
0x18000172a  call    __scrt_is_ucrt_dll_in_use
0x18000172f  test    eax, eax
0x180001731  jz      short loc_18000175B
0x180001733  test    ebx, ebx
0x180001735  jnz     short loc_18000175B
0x180001737  lea     rcx, Table; Table
0x18000173e  call    _initialize_onexit_table
0x180001743  test    eax, eax
0x180001745  jnz     short loc_180001757
0x180001747  lea     rcx, stru_1800080D8; Table
0x18000174e  call    _initialize_onexit_table
0x180001753  test    eax, eax
0x180001755  jz      short loc_180001785
0x180001757  xor     al, al
0x180001759  jmp     short loc_18000178E
0x18000175b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180001763  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001767  movdqu  xmmword ptr cs:Table._first, xmm0
0x18000176f  mov     cs:Table._end, rax
0x180001776  movdqu  xmmword ptr cs:stru_1800080D8._first, xmm0
0x18000177e  mov     cs:stru_1800080D8._end, rax
0x180001785  mov     cs:byte_1800080F0, 1
0x18000178c  mov     al, 1
0x18000178e  add     rsp, 20h
0x180001792  pop     rbx
0x180001793  retn
0x180001794  mov     ecx, 5
0x180001799  call    __scrt_fastfail
```
