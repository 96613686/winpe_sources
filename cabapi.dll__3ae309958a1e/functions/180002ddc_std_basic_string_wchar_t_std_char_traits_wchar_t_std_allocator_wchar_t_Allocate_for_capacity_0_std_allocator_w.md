# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)

- ea: `0x180002ddc`
- end: `0x180002e4c`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z`
- size: `112`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180002e54`
- `0x180002f70`
- `0x180007e88`
- `0x180007fd0`
- `0x18000f83c`

## callees

- `0x180001570`
- `0x180002ddc`
- `0x180006764`

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
0x180002ddc  push    rbx
0x180002dde  sub     rsp, 20h
0x180002de2  inc     qword ptr [rdx]
0x180002de5  mov     rax, 7FFFFFFFFFFFFFFFh
0x180002def  mov     rcx, [rdx]
0x180002df2  mov     rbx, rdx
0x180002df5  cmp     rcx, rax
0x180002df8  ja      short loc_180002E46
0x180002dfa  add     rcx, rcx; Size
0x180002dfd  jnz     short loc_180002E03
0x180002dff  xor     eax, eax
0x180002e01  jmp     short loc_180002E3D
0x180002e03  cmp     rcx, 1000h
0x180002e0a  jb      short loc_180002E38
0x180002e0c  lea     rax, [rcx+27h]
0x180002e10  cmp     rax, rcx
0x180002e13  jbe     short loc_180002E46
0x180002e15  mov     rcx, rax; Size
0x180002e18  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e1d  mov     rcx, rax
0x180002e20  test    rax, rax
0x180002e23  jnz     short loc_180002E2A
0x180002e25  lea     ecx, [rax+5]
0x180002e28  int     29h; Win8: RtlFailFast(ecx)
0x180002e2a  add     rax, 27h ; '''
0x180002e2e  and     rax, 0FFFFFFFFFFFFFFE0h
0x180002e32  mov     [rax-8], rcx
0x180002e36  jmp     short loc_180002E3D
0x180002e38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e3d  dec     qword ptr [rbx]
0x180002e40  add     rsp, 20h
0x180002e44  pop     rbx
0x180002e45  retn
0x180002e46  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
