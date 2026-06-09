# __scrt_initialize_onexit_tables

- ea: `0x1400013e4`
- end: `0x14000146f`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140001090`

## callees

- `0x1400013e4`
- `0x140001730`
- `0x140001b5c`
- `0x140001c12`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_1400040D0 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5);
    if ( !_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_1400040B8._first = *(_OWORD *)&Table._first;
      stru_1400040B8._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_1400040B8) )
    {
      return 0;
    }
    byte_1400040D0 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x1400013e4  push    rbx
0x1400013e6  sub     rsp, 20h
0x1400013ea  cmp     cs:byte_1400040D0, 0
0x1400013f1  mov     ebx, ecx
0x1400013f3  jnz     short loc_14000145C
0x1400013f5  cmp     ecx, 1
0x1400013f8  ja      short loc_140001464
0x1400013fa  call    __scrt_is_ucrt_dll_in_use
0x1400013ff  test    eax, eax
0x140001401  jz      short loc_14000142B
0x140001403  test    ebx, ebx
0x140001405  jnz     short loc_14000142B
0x140001407  lea     rcx, Table; Table
0x14000140e  call    _initialize_onexit_table
0x140001413  test    eax, eax
0x140001415  jnz     short loc_140001427
0x140001417  lea     rcx, stru_1400040B8; Table
0x14000141e  call    _initialize_onexit_table
0x140001423  test    eax, eax
0x140001425  jz      short loc_140001455
0x140001427  xor     al, al
0x140001429  jmp     short loc_14000145E
0x14000142b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140001433  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001437  movdqu  xmmword ptr cs:Table._first, xmm0
0x14000143f  mov     cs:Table._end, rax
0x140001446  movdqu  xmmword ptr cs:stru_1400040B8._first, xmm0
0x14000144e  mov     cs:stru_1400040B8._end, rax
0x140001455  mov     cs:byte_1400040D0, 1
0x14000145c  mov     al, 1
0x14000145e  add     rsp, 20h
0x140001462  pop     rbx
0x140001463  retn
0x140001464  mov     ecx, 5
0x140001469  call    __scrt_fastfail
```
