# __scrt_initialize_onexit_tables

- ea: `0x140002164`
- end: `0x1400021ef`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140001e10`

## callees

- `0x140002164`
- `0x140002490`
- `0x1400028bc`
- `0x140002972`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_14000C150 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5);
    if ( !_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_14000C138._first = *(_OWORD *)&Table._first;
      stru_14000C138._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_14000C138) )
    {
      return 0;
    }
    byte_14000C150 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x140002164  push    rbx
0x140002166  sub     rsp, 20h
0x14000216a  cmp     cs:byte_14000C150, 0
0x140002171  mov     ebx, ecx
0x140002173  jnz     short loc_1400021DC
0x140002175  cmp     ecx, 1
0x140002178  ja      short loc_1400021E4
0x14000217a  call    __scrt_is_ucrt_dll_in_use
0x14000217f  test    eax, eax
0x140002181  jz      short loc_1400021AB
0x140002183  test    ebx, ebx
0x140002185  jnz     short loc_1400021AB
0x140002187  lea     rcx, Table; Table
0x14000218e  call    _initialize_onexit_table
0x140002193  test    eax, eax
0x140002195  jnz     short loc_1400021A7
0x140002197  lea     rcx, stru_14000C138; Table
0x14000219e  call    _initialize_onexit_table
0x1400021a3  test    eax, eax
0x1400021a5  jz      short loc_1400021D5
0x1400021a7  xor     al, al
0x1400021a9  jmp     short loc_1400021DE
0x1400021ab  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400021b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400021b7  movdqu  xmmword ptr cs:Table._first, xmm0
0x1400021bf  mov     cs:Table._end, rax
0x1400021c6  movdqu  xmmword ptr cs:stru_14000C138._first, xmm0
0x1400021ce  mov     cs:stru_14000C138._end, rax
0x1400021d5  mov     cs:byte_14000C150, 1
0x1400021dc  mov     al, 1
0x1400021de  add     rsp, 20h
0x1400021e2  pop     rbx
0x1400021e3  retn
0x1400021e4  mov     ecx, 5
0x1400021e9  call    __scrt_fastfail
```
