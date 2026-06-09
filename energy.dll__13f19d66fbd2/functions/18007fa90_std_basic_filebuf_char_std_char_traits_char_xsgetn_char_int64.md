# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x18007fa90`
- end: `0x18007fb79`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18004d8e4`
- `0x18007e894`
- `0x18007fa90`

## import_xrefs

- `msvcp_win!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x18007fac2`
- `msvcp_win!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x18007fac2`
- `msvcp_win!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x18007fafc`
- `msvcp_win!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x18007fafc`
- `msvcp_win!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18007fada`
- `msvcp_win!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18007fada`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x18007fab7`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x18007fab7`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18007fb35`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18007fb5f`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18007fb35`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18007fb5f`

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
0x18007fa90  push    rbx
0x18007fa92  push    rbp
0x18007fa93  push    rsi
0x18007fa94  push    rdi
0x18007fa95  push    r14
0x18007fa97  sub     rsp, 20h
0x18007fa9b  mov     rdi, r8
0x18007fa9e  mov     r14, rdx
0x18007faa1  mov     rbp, rcx
0x18007faa4  test    r8, r8
0x18007faa7  jg      short loc_18007FAB0
0x18007faa9  xor     eax, eax
0x18007faab  jmp     loc_18007FB6E
0x18007fab0  cmp     qword ptr [rcx+68h], 0
0x18007fab5  jz      short loc_18007FAC2
0x18007fab7  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x18007fabd  jmp     loc_18007FB6E
0x18007fac2  call    cs:__imp_?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Gnavail(void)
0x18007fac8  test    rax, rax
0x18007facb  jz      short loc_18007FB04
0x18007facd  cmp     rax, rdi
0x18007fad0  mov     rbx, rdi
0x18007fad3  mov     rcx, rbp
0x18007fad6  cmovb   rbx, rax
0x18007fada  call    cs:__imp_?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::gptr(void)
0x18007fae0  mov     r8, rbx; Size
0x18007fae3  mov     rcx, r14; void *
0x18007fae6  mov     rdx, rax; Src
0x18007fae9  call    memcpy_0
0x18007faee  mov     rsi, rdi
0x18007faf1  add     r14, rbx
0x18007faf4  sub     rsi, rbx
0x18007faf7  mov     edx, ebx
0x18007faf9  mov     rcx, rbp
0x18007fafc  call    cs:__imp_?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::gbump(int)
0x18007fb02  jmp     short loc_18007FB07
0x18007fb04  mov     rsi, rdi
0x18007fb07  cmp     qword ptr [rbp+80h], 0
0x18007fb0f  jz      short loc_18007FB68
0x18007fb11  mov     rcx, rbp
0x18007fb14  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x18007fb19  mov     ebx, 0FFFh
0x18007fb1e  cmp     rsi, rbx
0x18007fb21  jbe     short loc_18007FB48
0x18007fb23  mov     r9, [rbp+80h]; Stream
0x18007fb2a  mov     r8, rbx; ElementCount
0x18007fb2d  mov     edx, 1; ElementSize
0x18007fb32  mov     rcx, r14; Buffer
0x18007fb35  call    cs:__imp_fread
0x18007fb3b  add     r14, rax
0x18007fb3e  sub     rsi, rax
0x18007fb41  cmp     rax, rbx
0x18007fb44  jz      short loc_18007FB1E
0x18007fb46  jmp     short loc_18007FB68
0x18007fb48  test    rsi, rsi
0x18007fb4b  jz      short loc_18007FB68
0x18007fb4d  mov     r9, [rbp+80h]; Stream
0x18007fb54  mov     r8, rsi; ElementCount
0x18007fb57  mov     edx, 1; ElementSize
0x18007fb5c  mov     rcx, r14; Buffer
0x18007fb5f  call    cs:__imp_fread
0x18007fb65  sub     rsi, rax
0x18007fb68  sub     rdi, rsi
0x18007fb6b  mov     rax, rdi
0x18007fb6e  add     rsp, 20h
0x18007fb72  pop     r14
0x18007fb74  pop     rdi
0x18007fb75  pop     rsi
0x18007fb76  pop     rbp
0x18007fb77  pop     rbx
0x18007fb78  retn
```
