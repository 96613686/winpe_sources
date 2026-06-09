# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x18000d3e0`
- end: `0x18000d4c9`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `233`
- prototype: `__int64 __fastcall(__int64, char *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800027d9`
- `0x18000c484`
- `0x18000d3e0`

## import_xrefs

- `msvcp_win!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18000d42a`
- `msvcp_win!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18000d42a`
- `msvcp_win!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x18000d44c`
- `msvcp_win!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x18000d44c`
- `msvcp_win!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x18000d412`
- `msvcp_win!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x18000d412`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x18000d407`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x18000d407`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18000d485`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18000d4af`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18000d485`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18000d4af`

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
0x18000d3e0  push    rbx
0x18000d3e2  push    rbp
0x18000d3e3  push    rsi
0x18000d3e4  push    rdi
0x18000d3e5  push    r14
0x18000d3e7  sub     rsp, 20h
0x18000d3eb  mov     rdi, r8
0x18000d3ee  mov     r14, rdx
0x18000d3f1  mov     rbp, rcx
0x18000d3f4  test    r8, r8
0x18000d3f7  jg      short loc_18000D400
0x18000d3f9  xor     eax, eax
0x18000d3fb  jmp     loc_18000D4BE
0x18000d400  cmp     qword ptr [rcx+68h], 0
0x18000d405  jz      short loc_18000D412
0x18000d407  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x18000d40d  jmp     loc_18000D4BE
0x18000d412  call    cs:__imp_?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Gnavail(void)
0x18000d418  test    rax, rax
0x18000d41b  jz      short loc_18000D454
0x18000d41d  cmp     rax, rdi
0x18000d420  mov     rbx, rdi
0x18000d423  mov     rcx, rbp
0x18000d426  cmovb   rbx, rax
0x18000d42a  call    cs:__imp_?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::gptr(void)
0x18000d430  mov     r8, rbx; Size
0x18000d433  mov     rcx, r14; void *
0x18000d436  mov     rdx, rax; Src
0x18000d439  call    memcpy_0
0x18000d43e  mov     rsi, rdi
0x18000d441  add     r14, rbx
0x18000d444  sub     rsi, rbx
0x18000d447  mov     edx, ebx
0x18000d449  mov     rcx, rbp
0x18000d44c  call    cs:__imp_?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::gbump(int)
0x18000d452  jmp     short loc_18000D457
0x18000d454  mov     rsi, rdi
0x18000d457  cmp     qword ptr [rbp+80h], 0
0x18000d45f  jz      short loc_18000D4B8
0x18000d461  mov     rcx, rbp
0x18000d464  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x18000d469  mov     ebx, 0FFFh
0x18000d46e  cmp     rsi, rbx
0x18000d471  jbe     short loc_18000D498
0x18000d473  mov     r9, [rbp+80h]; Stream
0x18000d47a  mov     r8, rbx; ElementCount
0x18000d47d  mov     edx, 1; ElementSize
0x18000d482  mov     rcx, r14; Buffer
0x18000d485  call    cs:__imp_fread
0x18000d48b  add     r14, rax
0x18000d48e  sub     rsi, rax
0x18000d491  cmp     rax, rbx
0x18000d494  jz      short loc_18000D46E
0x18000d496  jmp     short loc_18000D4B8
0x18000d498  test    rsi, rsi
0x18000d49b  jz      short loc_18000D4B8
0x18000d49d  mov     r9, [rbp+80h]; Stream
0x18000d4a4  mov     r8, rsi; ElementCount
0x18000d4a7  mov     edx, 1; ElementSize
0x18000d4ac  mov     rcx, r14; Buffer
0x18000d4af  call    cs:__imp_fread
0x18000d4b5  sub     rsi, rax
0x18000d4b8  sub     rdi, rsi
0x18000d4bb  mov     rax, rdi
0x18000d4be  add     rsp, 20h
0x18000d4c2  pop     r14
0x18000d4c4  pop     rdi
0x18000d4c5  pop     rsi
0x18000d4c6  pop     rbp
0x18000d4c7  pop     rbx
0x18000d4c8  retn
```
