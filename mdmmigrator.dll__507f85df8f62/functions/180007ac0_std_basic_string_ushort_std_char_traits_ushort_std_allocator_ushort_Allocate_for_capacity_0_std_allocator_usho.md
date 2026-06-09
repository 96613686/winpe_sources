# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)

- ea: `0x180007ac0`
- end: `0x180007b30`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z`
- size: `112`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180007b38`
- `0x180007c94`
- `0x180007f40`
- `0x180009cb4`
- `0x18000cc28`
- `0x18000d1b0`
- `0x18000d2a8`
- `0x18000d3c4`
- `0x180010864`
- `0x180011610`

## callees

- `0x1800034ac`
- `0x180007ac0`
- `0x18000970c`

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
0x180007ac0  push    rbx
0x180007ac2  sub     rsp, 20h
0x180007ac6  inc     qword ptr [rdx]
0x180007ac9  mov     rax, 7FFFFFFFFFFFFFFFh
0x180007ad3  mov     rcx, [rdx]
0x180007ad6  mov     rbx, rdx
0x180007ad9  cmp     rcx, rax
0x180007adc  ja      short loc_180007B2A
0x180007ade  add     rcx, rcx; Size
0x180007ae1  jnz     short loc_180007AE7
0x180007ae3  xor     eax, eax
0x180007ae5  jmp     short loc_180007B21
0x180007ae7  cmp     rcx, 1000h
0x180007aee  jb      short loc_180007B1C
0x180007af0  lea     rax, [rcx+27h]
0x180007af4  cmp     rax, rcx
0x180007af7  jbe     short loc_180007B2A
0x180007af9  mov     rcx, rax; Size
0x180007afc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007b01  mov     rcx, rax
0x180007b04  test    rax, rax
0x180007b07  jnz     short loc_180007B0E
0x180007b09  lea     ecx, [rax+5]
0x180007b0c  int     29h; Win8: RtlFailFast(ecx)
0x180007b0e  add     rax, 27h ; '''
0x180007b12  and     rax, 0FFFFFFFFFFFFFFE0h
0x180007b16  mov     [rax-8], rcx
0x180007b1a  jmp     short loc_180007B21
0x180007b1c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007b21  dec     qword ptr [rbx]
0x180007b24  add     rsp, 20h
0x180007b28  pop     rbx
0x180007b29  retn
0x180007b2a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
