# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x1800f4d00`
- end: `0x1800f4de9`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019fac`
- `0x1800ef208`
- `0x1800f4d00`

## import_xrefs

- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1800f4d27`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1800f4d27`
- `msvcp_win!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1800f4d32`
- `msvcp_win!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1800f4d32`
- `msvcp_win!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800f4d6c`
- `msvcp_win!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800f4d6c`
- `msvcp_win!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f4d4a`
- `msvcp_win!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f4d4a`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800f4da5`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800f4dcf`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800f4da5`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800f4dcf`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsgetn(__int64 a1, char *a2, __int64 a3)
{
  unsigned __int64 v7; // rax
  size_t v8; // rbx
  const void *v9; // rax
  size_t v10; // rsi
  size_t v11; // rax

  if ( a3 <= 0 )
    return 0;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsgetn();
  v7 = std::streambuf::_Gnavail();
  if ( v7 )
  {
    v8 = a3;
    if ( v7 < a3 )
      v8 = v7;
    v9 = (const void *)std::streambuf::gptr(a1);
    memcpy_0(a2, v9, v8);
    a2 += v8;
    v10 = a3 - v8;
    std::streambuf::gbump(a1, (unsigned int)v8);
  }
  else
  {
    v10 = a3;
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    std::filebuf::_Reset_back(a1);
    while ( v10 > 0xFFF )
    {
      v11 = fread(a2, 1u, 0xFFFu, *(FILE **)(a1 + 128));
      a2 += v11;
      v10 -= v11;
      if ( v11 != 4095 )
        return a3 - v10;
    }
    if ( v10 )
      v10 -= fread(a2, 1u, v10, *(FILE **)(a1 + 128));
  }
  return a3 - v10;
}

```

## disassembly

```asm
0x1800f4d00  push    rbx
0x1800f4d02  push    rbp
0x1800f4d03  push    rsi
0x1800f4d04  push    rdi
0x1800f4d05  push    r14
0x1800f4d07  sub     rsp, 20h
0x1800f4d0b  mov     rdi, r8
0x1800f4d0e  mov     r14, rdx
0x1800f4d11  mov     rbp, rcx
0x1800f4d14  test    r8, r8
0x1800f4d17  jg      short loc_1800F4D20
0x1800f4d19  xor     eax, eax
0x1800f4d1b  jmp     loc_1800F4DDE
0x1800f4d20  cmp     qword ptr [rcx+68h], 0
0x1800f4d25  jz      short loc_1800F4D32
0x1800f4d27  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x1800f4d2d  jmp     loc_1800F4DDE
0x1800f4d32  call    cs:__imp_?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Gnavail(void)
0x1800f4d38  test    rax, rax
0x1800f4d3b  jz      short loc_1800F4D74
0x1800f4d3d  cmp     rax, rdi
0x1800f4d40  mov     rbx, rdi
0x1800f4d43  mov     rcx, rbp
0x1800f4d46  cmovb   rbx, rax
0x1800f4d4a  call    cs:__imp_?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::gptr(void)
0x1800f4d50  mov     r8, rbx; Size
0x1800f4d53  mov     rcx, r14; void *
0x1800f4d56  mov     rdx, rax; Src
0x1800f4d59  call    memcpy_0
0x1800f4d5e  mov     rsi, rdi
0x1800f4d61  add     r14, rbx
0x1800f4d64  sub     rsi, rbx
0x1800f4d67  mov     edx, ebx
0x1800f4d69  mov     rcx, rbp
0x1800f4d6c  call    cs:__imp_?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::gbump(int)
0x1800f4d72  jmp     short loc_1800F4D77
0x1800f4d74  mov     rsi, rdi
0x1800f4d77  cmp     qword ptr [rbp+80h], 0
0x1800f4d7f  jz      short loc_1800F4DD8
0x1800f4d81  mov     rcx, rbp
0x1800f4d84  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x1800f4d89  mov     ebx, 0FFFh
0x1800f4d8e  cmp     rsi, rbx
0x1800f4d91  jbe     short loc_1800F4DB8
0x1800f4d93  mov     r9, [rbp+80h]; Stream
0x1800f4d9a  mov     r8, rbx; ElementCount
0x1800f4d9d  mov     edx, 1; ElementSize
0x1800f4da2  mov     rcx, r14; Buffer
0x1800f4da5  call    cs:__imp_fread
0x1800f4dab  add     r14, rax
0x1800f4dae  sub     rsi, rax
0x1800f4db1  cmp     rax, rbx
0x1800f4db4  jz      short loc_1800F4D8E
0x1800f4db6  jmp     short loc_1800F4DD8
0x1800f4db8  test    rsi, rsi
0x1800f4dbb  jz      short loc_1800F4DD8
0x1800f4dbd  mov     r9, [rbp+80h]; Stream
0x1800f4dc4  mov     r8, rsi; ElementCount
0x1800f4dc7  mov     edx, 1; ElementSize
0x1800f4dcc  mov     rcx, r14; Buffer
0x1800f4dcf  call    cs:__imp_fread
0x1800f4dd5  sub     rsi, rax
0x1800f4dd8  sub     rdi, rsi
0x1800f4ddb  mov     rax, rdi
0x1800f4dde  add     rsp, 20h
0x1800f4de2  pop     r14
0x1800f4de4  pop     rdi
0x1800f4de5  pop     rsi
0x1800f4de6  pop     rbp
0x1800f4de7  pop     rbx
0x1800f4de8  retn
```
