# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)

- ea: `0x180005e78`
- end: `0x180005ee8`
- name: `??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z`
- size: `112`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180005ef0`
- `0x180005fa4`
- `0x1800060e4`
- `0x180006e1c`
- `0x18001e794`
- `0x18001e88c`
- `0x18001e9a8`
- `0x18001eaac`

## callees

- `0x180002e74`
- `0x180005e78`
- `0x1800156a0`

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
0x180005e78  push    rbx
0x180005e7a  sub     rsp, 20h
0x180005e7e  inc     qword ptr [rdx]
0x180005e81  mov     rax, 7FFFFFFFFFFFFFFFh
0x180005e8b  mov     rcx, [rdx]
0x180005e8e  mov     rbx, rdx
0x180005e91  cmp     rcx, rax
0x180005e94  ja      short loc_180005EE2
0x180005e96  add     rcx, rcx; Size
0x180005e99  jnz     short loc_180005E9F
0x180005e9b  xor     eax, eax
0x180005e9d  jmp     short loc_180005ED9
0x180005e9f  cmp     rcx, 1000h
0x180005ea6  jb      short loc_180005ED4
0x180005ea8  lea     rax, [rcx+27h]
0x180005eac  cmp     rax, rcx
0x180005eaf  jbe     short loc_180005EE2
0x180005eb1  mov     rcx, rax; Size
0x180005eb4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005eb9  mov     rcx, rax
0x180005ebc  test    rax, rax
0x180005ebf  jnz     short loc_180005EC6
0x180005ec1  lea     ecx, [rax+5]
0x180005ec4  int     29h; Win8: RtlFailFast(ecx)
0x180005ec6  add     rax, 27h ; '''
0x180005eca  and     rax, 0FFFFFFFFFFFFFFE0h
0x180005ece  mov     [rax-8], rcx
0x180005ed2  jmp     short loc_180005ED9
0x180005ed4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005ed9  dec     qword ptr [rbx]
0x180005edc  add     rsp, 20h
0x180005ee0  pop     rbx
0x180005ee1  retn
0x180005ee2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
