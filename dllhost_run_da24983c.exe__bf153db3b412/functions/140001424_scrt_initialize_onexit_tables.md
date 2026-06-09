# __scrt_initialize_onexit_tables

- ea: `0x140001424`
- end: `0x1400014af`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400010e0`

## callees

- `0x140001424`
- `0x140001770`
- `0x140001bdc`
- `0x140001c86`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_1400070D0 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5);
    if ( !_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_1400070B8._first = *(_OWORD *)&Table._first;
      stru_1400070B8._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_1400070B8) )
    {
      return 0;
    }
    byte_1400070D0 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x140001424  push    rbx
0x140001426  sub     rsp, 20h
0x14000142a  cmp     cs:byte_1400070D0, 0
0x140001431  mov     ebx, ecx
0x140001433  jnz     short loc_14000149C
0x140001435  cmp     ecx, 1
0x140001438  ja      short loc_1400014A4
0x14000143a  call    __scrt_is_ucrt_dll_in_use
0x14000143f  test    eax, eax
0x140001441  jz      short loc_14000146B
0x140001443  test    ebx, ebx
0x140001445  jnz     short loc_14000146B
0x140001447  lea     rcx, Table; Table
0x14000144e  call    _initialize_onexit_table
0x140001453  test    eax, eax
0x140001455  jnz     short loc_140001467
0x140001457  lea     rcx, stru_1400070B8; Table
0x14000145e  call    _initialize_onexit_table
0x140001463  test    eax, eax
0x140001465  jz      short loc_140001495
0x140001467  xor     al, al
0x140001469  jmp     short loc_14000149E
0x14000146b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140001473  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001477  movdqu  xmmword ptr cs:Table._first, xmm0
0x14000147f  mov     cs:Table._end, rax
0x140001486  movdqu  xmmword ptr cs:stru_1400070B8._first, xmm0
0x14000148e  mov     cs:stru_1400070B8._end, rax
0x140001495  mov     cs:byte_1400070D0, 1
0x14000149c  mov     al, 1
0x14000149e  add     rsp, 20h
0x1400014a2  pop     rbx
0x1400014a3  retn
0x1400014a4  mov     ecx, 5
0x1400014a9  call    __scrt_fastfail
```
