# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)

- ea: `0x18000739c`
- end: `0x18000740c`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z`
- size: `112`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180007504`
- `0x18000773c`
- `0x1800079a8`
- `0x180007da4`
- `0x180007ff8`
- `0x180008a68`
- `0x18000c06c`

## callees

- `0x180001fb8`
- `0x18000739c`
- `0x18000a938`

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
0x18000739c  push    rbx
0x18000739e  sub     rsp, 20h
0x1800073a2  inc     qword ptr [rdx]
0x1800073a5  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800073af  mov     rcx, [rdx]
0x1800073b2  mov     rbx, rdx
0x1800073b5  cmp     rcx, rax
0x1800073b8  ja      short loc_180007406
0x1800073ba  add     rcx, rcx; Size
0x1800073bd  jnz     short loc_1800073C3
0x1800073bf  xor     eax, eax
0x1800073c1  jmp     short loc_1800073FD
0x1800073c3  cmp     rcx, 1000h
0x1800073ca  jb      short loc_1800073F8
0x1800073cc  lea     rax, [rcx+27h]
0x1800073d0  cmp     rax, rcx
0x1800073d3  jbe     short loc_180007406
0x1800073d5  mov     rcx, rax; Size
0x1800073d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800073dd  mov     rcx, rax
0x1800073e0  test    rax, rax
0x1800073e3  jnz     short loc_1800073EA
0x1800073e5  lea     ecx, [rax+5]
0x1800073e8  int     29h; Win8: RtlFailFast(ecx)
0x1800073ea  add     rax, 27h ; '''
0x1800073ee  and     rax, 0FFFFFFFFFFFFFFE0h
0x1800073f2  mov     [rax-8], rcx
0x1800073f6  jmp     short loc_1800073FD
0x1800073f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800073fd  dec     qword ptr [rbx]
0x180007400  add     rsp, 20h
0x180007404  pop     rbx
0x180007405  retn
0x180007406  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
