# __scrt_initialize_onexit_tables

- ea: `0x180001740`
- end: `0x1800017cb`
- name: `__scrt_initialize_onexit_tables`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001600`

## callees

- `0x180001740`
- `0x1800018e0`
- `0x180001c10`
- `0x180001ca6`

## pseudocode

```c
char __fastcall _scrt_initialize_onexit_tables(unsigned int a1)
{
  if ( !byte_18000B410 )
  {
    if ( a1 > 1 )
      _scrt_fastfail(5);
    if ( !_scrt_is_ucrt_dll_in_use() || a1 )
    {
      *(__m128i *)&Table._first = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      Table._end = (_PVFV *)-1LL;
      *(_OWORD *)&stru_18000B3F8._first = *(_OWORD *)&Table._first;
      stru_18000B3F8._end = (_PVFV *)-1LL;
    }
    else if ( initialize_onexit_table(&Table) || initialize_onexit_table(&stru_18000B3F8) )
    {
      return 0;
    }
    byte_18000B410 = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x180001740  push    rbx
0x180001742  sub     rsp, 20h
0x180001746  cmp     cs:byte_18000B410, 0
0x18000174d  mov     ebx, ecx
0x18000174f  jnz     short loc_1800017B8
0x180001751  cmp     ecx, 1
0x180001754  ja      short loc_1800017C0
0x180001756  call    __scrt_is_ucrt_dll_in_use
0x18000175b  test    eax, eax
0x18000175d  jz      short loc_180001787
0x18000175f  test    ebx, ebx
0x180001761  jnz     short loc_180001787
0x180001763  lea     rcx, Table; Table
0x18000176a  call    _initialize_onexit_table
0x18000176f  test    eax, eax
0x180001771  jnz     short loc_180001783
0x180001773  lea     rcx, stru_18000B3F8; Table
0x18000177a  call    _initialize_onexit_table
0x18000177f  test    eax, eax
0x180001781  jz      short loc_1800017B1
0x180001783  xor     al, al
0x180001785  jmp     short loc_1800017BA
0x180001787  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000178f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001793  movdqu  xmmword ptr cs:Table._first, xmm0
0x18000179b  mov     cs:Table._end, rax
0x1800017a2  movdqu  xmmword ptr cs:stru_18000B3F8._first, xmm0
0x1800017aa  mov     cs:stru_18000B3F8._end, rax
0x1800017b1  mov     cs:byte_18000B410, 1
0x1800017b8  mov     al, 1
0x1800017ba  add     rsp, 20h
0x1800017be  pop     rbx
0x1800017bf  retn
0x1800017c0  mov     ecx, 5
0x1800017c5  call    __scrt_fastfail
```
