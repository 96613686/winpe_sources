# __scrt_initialize_onexit_tables

- ea: `0x1800016e8`
- end: `0x180001773`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800015a8`

## callees

- `0x1800016e8`
- `0x180001888`
- `0x180001bd8`
- `0x180001c66`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_180007130 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5);
    if ( !_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_180007118._first = *(_OWORD *)&Table._first;
      stru_180007118._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_180007118) )
    {
      return 0;
    }
    byte_180007130 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x1800016e8  push    rbx
0x1800016ea  sub     rsp, 20h
0x1800016ee  cmp     cs:byte_180007130, 0
0x1800016f5  mov     ebx, ecx
0x1800016f7  jnz     short loc_180001760
0x1800016f9  cmp     ecx, 1
0x1800016fc  ja      short loc_180001768
0x1800016fe  call    __scrt_is_ucrt_dll_in_use
0x180001703  test    eax, eax
0x180001705  jz      short loc_18000172F
0x180001707  test    ebx, ebx
0x180001709  jnz     short loc_18000172F
0x18000170b  lea     rcx, Table; Table
0x180001712  call    _initialize_onexit_table
0x180001717  test    eax, eax
0x180001719  jnz     short loc_18000172B
0x18000171b  lea     rcx, stru_180007118; Table
0x180001722  call    _initialize_onexit_table
0x180001727  test    eax, eax
0x180001729  jz      short loc_180001759
0x18000172b  xor     al, al
0x18000172d  jmp     short loc_180001762
0x18000172f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180001737  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000173b  movdqu  xmmword ptr cs:Table._first, xmm0
0x180001743  mov     cs:Table._end, rax
0x18000174a  movdqu  xmmword ptr cs:stru_180007118._first, xmm0
0x180001752  mov     cs:stru_180007118._end, rax
0x180001759  mov     cs:byte_180007130, 1
0x180001760  mov     al, 1
0x180001762  add     rsp, 20h
0x180001766  pop     rbx
0x180001767  retn
0x180001768  mov     ecx, 5
0x18000176d  call    __scrt_fastfail
```
