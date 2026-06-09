# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x1800a3890`
- end: `0x1800a39a3`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800a2bf0`
- `0x1800a3890`
- `0x1801a65f0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x1800a3948`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x1800a397b`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x1800a3948`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x1800a397b`
- `MSVCP140!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800a38f0`
- `MSVCP140!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800a38f0`
- `MSVCP140!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800a390f`
- `MSVCP140!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800a390f`
- `MSVCP140!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1800a38d8`
- `MSVCP140!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1800a38d8`
- `MSVCP140!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1800a38c4`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsgetn(__int64 a1, char *a2, __int64 a3)
{
  __int64 result; // rax
  size_t v7; // rbx
  unsigned __int64 v8; // rax
  size_t v9; // rdi
  const void *v10; // rax
  size_t v11; // rdi
  size_t v12; // rax

  if ( a3 <= 0 )
    return 0;
  if ( *(_QWORD *)(a1 + 104) )
  {
    _mm_lfence();
    return std::streambuf::xsgetn();
  }
  else
  {
    v7 = a3;
    v8 = std::streambuf::_Gnavail();
    if ( v8 )
    {
      v9 = a3;
      if ( v8 < a3 )
        v9 = v8;
      v10 = (const void *)std::streambuf::gptr(a1);
      memcpy_0(a2, v10, v9);
      a2 += v9;
      v7 = a3 - v9;
      std::streambuf::gbump(a1, (unsigned int)v9);
    }
    if ( *(_QWORD *)(a1 + 128) )
    {
      std::filebuf::_Reset_back(a1);
      v11 = v7;
      if ( v7 <= 0xFFF )
      {
LABEL_13:
        if ( v11 )
          v7 = v11 - fread(a2, 1u, v7, *(FILE **)(a1 + 128));
      }
      else
      {
        while ( 1 )
        {
          v12 = fread(a2, 1u, 0xFFFu, *(FILE **)(a1 + 128));
          v7 -= v12;
          a2 += v12;
          v11 = v7;
          if ( v12 != 4095 )
            break;
          if ( v7 <= 0xFFF )
            goto LABEL_13;
        }
      }
    }
    result = a3 - v7;
    _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x1800a3890  push    rbp
0x1800a3892  push    rsi
0x1800a3893  push    r14
0x1800a3895  sub     rsp, 30h
0x1800a3899  mov     rsi, r8
0x1800a389c  mov     rbp, rdx
0x1800a389f  mov     r14, rcx
0x1800a38a2  test    r8, r8
0x1800a38a5  jg      short loc_1800A38B2
0x1800a38a7  xor     eax, eax
0x1800a38a9  add     rsp, 30h
0x1800a38ad  pop     r14
0x1800a38af  pop     rsi
0x1800a38b0  pop     rbp
0x1800a38b1  retn
0x1800a38b2  cmp     qword ptr [rcx+68h], 0
0x1800a38b7  jz      short loc_1800A38CB
0x1800a38b9  lfence
0x1800a38bc  add     rsp, 30h
0x1800a38c0  pop     r14
0x1800a38c2  pop     rsi
0x1800a38c3  pop     rbp
0x1800a38c4  jmp     cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x1800a38cb  mov     [rsp+48h+var_20], rbx
0x1800a38d0  mov     rbx, rsi
0x1800a38d3  mov     [rsp+48h+var_28], rdi
0x1800a38d8  call    cs:__imp_?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Gnavail(void)
0x1800a38de  test    rax, rax
0x1800a38e1  jz      short loc_1800A3915
0x1800a38e3  cmp     rax, rsi
0x1800a38e6  mov     rdi, rsi
0x1800a38e9  mov     rcx, r14
0x1800a38ec  cmovb   rdi, rax
0x1800a38f0  call    cs:__imp_?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::gptr(void)
0x1800a38f6  mov     r8, rdi; Size
0x1800a38f9  mov     rcx, rbp; void *
0x1800a38fc  mov     rdx, rax; Src
0x1800a38ff  call    memcpy_0
0x1800a3904  mov     edx, edi
0x1800a3906  mov     rcx, r14
0x1800a3909  add     rbp, rdi
0x1800a390c  sub     rbx, rdi
0x1800a390f  call    cs:__imp_?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::gbump(int)
0x1800a3915  cmp     qword ptr [r14+80h], 0
0x1800a391d  jz      short loc_1800A3987
0x1800a391f  mov     rcx, r14
0x1800a3922  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x1800a3927  mov     rdi, rbx
0x1800a392a  cmp     rbx, 0FFFh
0x1800a3931  jbe     short loc_1800A3964
0x1800a3933  mov     r9, [r14+80h]; Stream
0x1800a393a  mov     edx, 1; ElementSize
0x1800a393f  mov     r8d, 0FFFh; ElementCount
0x1800a3945  mov     rcx, rbp; Buffer
0x1800a3948  call    cs:__imp_fread
0x1800a394e  sub     rbx, rax
0x1800a3951  add     rbp, rax
0x1800a3954  mov     rdi, rbx
0x1800a3957  cmp     rax, 0FFFh
0x1800a395d  jnz     short loc_1800A3987
0x1800a395f  cmp     rbx, rax
0x1800a3962  ja      short loc_1800A3933
0x1800a3964  test    rdi, rdi
0x1800a3967  jz      short loc_1800A3987
0x1800a3969  mov     r9, [r14+80h]; Stream
0x1800a3970  mov     r8, rbx; ElementCount
0x1800a3973  mov     edx, 1; ElementSize
0x1800a3978  mov     rcx, rbp; Buffer
0x1800a397b  call    cs:__imp_fread
0x1800a3981  mov     rbx, rdi
0x1800a3984  sub     rbx, rax
0x1800a3987  sub     rsi, rbx
0x1800a398a  mov     rax, rsi
0x1800a398d  lfence
0x1800a3990  mov     rbx, [rsp+48h+var_20]
0x1800a3995  mov     rdi, [rsp+48h+var_28]
0x1800a399a  add     rsp, 30h
0x1800a399e  pop     r14
0x1800a39a0  pop     rsi
0x1800a39a1  pop     rbp
0x1800a39a2  retn
```
