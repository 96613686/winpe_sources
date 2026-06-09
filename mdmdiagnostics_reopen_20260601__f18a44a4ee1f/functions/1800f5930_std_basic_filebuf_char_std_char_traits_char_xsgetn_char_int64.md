# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x1800f5930`
- end: `0x1800f5a3e`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001a03c`
- `0x1800ef948`
- `0x1800f5930`

## import_xrefs

- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1800f5957`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1800f5957`
- `msvcp_win!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1800f5968`
- `msvcp_win!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1800f5968`
- `msvcp_win!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800f59ae`
- `msvcp_win!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800f59ae`
- `msvcp_win!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f5986`
- `msvcp_win!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f5986`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800f59ed`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800f5a1d`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800f59ed`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800f5a1d`

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
0x1800f5930  push    rbx
0x1800f5932  push    rbp
0x1800f5933  push    rsi
0x1800f5934  push    rdi
0x1800f5935  push    r14
0x1800f5937  sub     rsp, 20h
0x1800f593b  mov     rdi, r8
0x1800f593e  mov     r14, rdx
0x1800f5941  mov     rbp, rcx
0x1800f5944  test    r8, r8
0x1800f5947  jg      short loc_1800F5950
0x1800f5949  xor     eax, eax
0x1800f594b  jmp     loc_1800F5A32
0x1800f5950  cmp     qword ptr [rcx+68h], 0
0x1800f5955  jz      short loc_1800F5968
0x1800f5957  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x1800f595e  nop     dword ptr [rax+rax+00h]
0x1800f5963  jmp     loc_1800F5A32
0x1800f5968  call    cs:__imp_?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Gnavail(void)
0x1800f596f  nop     dword ptr [rax+rax+00h]
0x1800f5974  test    rax, rax
0x1800f5977  jz      short loc_1800F59BC
0x1800f5979  cmp     rax, rdi
0x1800f597c  mov     rbx, rdi
0x1800f597f  mov     rcx, rbp
0x1800f5982  cmovb   rbx, rax
0x1800f5986  call    cs:__imp_?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::gptr(void)
0x1800f598d  nop     dword ptr [rax+rax+00h]
0x1800f5992  mov     r8, rbx; Size
0x1800f5995  mov     rcx, r14; void *
0x1800f5998  mov     rdx, rax; Src
0x1800f599b  call    memcpy_0
0x1800f59a0  mov     rsi, rdi
0x1800f59a3  add     r14, rbx
0x1800f59a6  sub     rsi, rbx
0x1800f59a9  mov     edx, ebx
0x1800f59ab  mov     rcx, rbp
0x1800f59ae  call    cs:__imp_?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::gbump(int)
0x1800f59b5  nop     dword ptr [rax+rax+00h]
0x1800f59ba  jmp     short loc_1800F59BF
0x1800f59bc  mov     rsi, rdi
0x1800f59bf  cmp     qword ptr [rbp+80h], 0
0x1800f59c7  jz      short loc_1800F5A2C
0x1800f59c9  mov     rcx, rbp
0x1800f59cc  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x1800f59d1  mov     ebx, 0FFFh
0x1800f59d6  cmp     rsi, rbx
0x1800f59d9  jbe     short loc_1800F5A06
0x1800f59db  mov     r9, [rbp+80h]; Stream
0x1800f59e2  mov     r8, rbx; ElementCount
0x1800f59e5  mov     edx, 1; ElementSize
0x1800f59ea  mov     rcx, r14; Buffer
0x1800f59ed  call    cs:__imp_fread
0x1800f59f4  nop     dword ptr [rax+rax+00h]
0x1800f59f9  add     r14, rax
0x1800f59fc  sub     rsi, rax
0x1800f59ff  cmp     rax, rbx
0x1800f5a02  jz      short loc_1800F59D6
0x1800f5a04  jmp     short loc_1800F5A2C
0x1800f5a06  test    rsi, rsi
0x1800f5a09  jz      short loc_1800F5A2C
0x1800f5a0b  mov     r9, [rbp+80h]; Stream
0x1800f5a12  mov     r8, rsi; ElementCount
0x1800f5a15  mov     edx, 1; ElementSize
0x1800f5a1a  mov     rcx, r14; Buffer
0x1800f5a1d  call    cs:__imp_fread
0x1800f5a24  nop     dword ptr [rax+rax+00h]
0x1800f5a29  sub     rsi, rax
0x1800f5a2c  sub     rdi, rsi
0x1800f5a2f  mov     rax, rdi
0x1800f5a32  add     rsp, 20h
0x1800f5a36  pop     r14
0x1800f5a38  pop     rdi
0x1800f5a39  pop     rsi
0x1800f5a3a  pop     rbp
0x1800f5a3b  pop     rbx
0x1800f5a3c  retn
```
