# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)

- ea: `0x14000422c`
- end: `0x14000429c`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z`
- size: `112`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1400042a4`
- `0x1400045d4`
- `0x140004718`
- `0x140004924`
- `0x14000e878`
- `0x14000e970`
- `0x14000f530`

## callees

- `0x1400021c0`
- `0x14000422c`
- `0x14000ce78`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Allocate_for_capacity<0>(__int64 a1, _QWORD *a2)
{
  size_t v3; // rcx
  _QWORD *result; // rax
  void *v5; // rax
  void *v6; // rcx

  if ( ++*a2 > 0x7FFFFFFFFFFFFFFFuLL )
    goto LABEL_11;
  v3 = 2LL * *a2;
  if ( !v3 )
  {
    result = 0;
    goto LABEL_10;
  }
  if ( v3 < 0x1000 )
  {
    result = operator new(v3);
    goto LABEL_10;
  }
  if ( v3 + 39 < v3 )
LABEL_11:
    __scrt_throw_std_bad_array_new_length();
  v5 = operator new(v3 + 39);
  v6 = v5;
  if ( !v5 )
    __fastfail(5u);
  result = (_QWORD *)(((unsigned __int64)v5 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(result - 1) = v6;
LABEL_10:
  --*a2;
  return result;
}

```

## disassembly

```asm
0x14000422c  push    rbx
0x14000422e  sub     rsp, 20h
0x140004232  inc     qword ptr [rdx]
0x140004235  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000423f  mov     rcx, [rdx]
0x140004242  mov     rbx, rdx
0x140004245  cmp     rcx, rax
0x140004248  ja      short loc_140004296
0x14000424a  add     rcx, rcx; Size
0x14000424d  jnz     short loc_140004253
0x14000424f  xor     eax, eax
0x140004251  jmp     short loc_14000428D
0x140004253  cmp     rcx, 1000h
0x14000425a  jb      short loc_140004288
0x14000425c  lea     rax, [rcx+27h]
0x140004260  cmp     rax, rcx
0x140004263  jbe     short loc_140004296
0x140004265  mov     rcx, rax; Size
0x140004268  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000426d  mov     rcx, rax
0x140004270  test    rax, rax
0x140004273  jnz     short loc_14000427A
0x140004275  lea     ecx, [rax+5]
0x140004278  int     29h; Win8: RtlFailFast(ecx)
0x14000427a  add     rax, 27h ; '''
0x14000427e  and     rax, 0FFFFFFFFFFFFFFE0h
0x140004282  mov     [rax-8], rcx
0x140004286  jmp     short loc_14000428D
0x140004288  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000428d  dec     qword ptr [rbx]
0x140004290  add     rsp, 20h
0x140004294  pop     rbx
0x140004295  retn
0x140004296  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
