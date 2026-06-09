# __scrt_initialize_onexit_tables

- ea: `0x180001758`
- end: `0x1800017e3`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: `char __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001618`

## callees

- `0x180001758`
- `0x1800018f8`
- `0x180001c48`
- `0x180001cca`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_18002A0F0 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5u);
    if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_18002A0D8._first = *(_OWORD *)&Table._first;
      stru_18002A0D8._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_18002A0D8) )
    {
      return 0;
    }
    byte_18002A0F0 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180001758  push    rbx
0x18000175a  sub     rsp, 20h
0x18000175e  cmp     cs:byte_18002A0F0, 0
0x180001765  mov     ebx, ecx
0x180001767  jnz     short loc_1800017D0
0x180001769  cmp     ecx, 1
0x18000176c  ja      short loc_1800017D8
0x18000176e  call    __scrt_is_ucrt_dll_in_use
0x180001773  test    eax, eax
0x180001775  jz      short loc_18000179F
0x180001777  test    ebx, ebx
0x180001779  jnz     short loc_18000179F
0x18000177b  lea     rcx, Table; Table
0x180001782  call    _initialize_onexit_table
0x180001787  test    eax, eax
0x180001789  jnz     short loc_18000179B
0x18000178b  lea     rcx, stru_18002A0D8; Table
0x180001792  call    _initialize_onexit_table
0x180001797  test    eax, eax
0x180001799  jz      short loc_1800017C9
0x18000179b  xor     al, al
0x18000179d  jmp     short loc_1800017D2
0x18000179f  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800017a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800017ab  movdqu  xmmword ptr cs:Table._first, xmm0
0x1800017b3  mov     cs:Table._end, rax
0x1800017ba  movdqu  xmmword ptr cs:stru_18002A0D8._first, xmm0
0x1800017c2  mov     cs:stru_18002A0D8._end, rax
0x1800017c9  mov     cs:byte_18002A0F0, 1
0x1800017d0  mov     al, 1
0x1800017d2  add     rsp, 20h
0x1800017d6  pop     rbx
0x1800017d7  retn
0x1800017d8  mov     ecx, 5
0x1800017dd  call    __scrt_fastfail
```
