# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x180035160`
- end: `0x180035274`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800064a2`
- `0x180035160`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18003522d`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18003525a`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18003522d`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18003525a`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x180035187`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x180035187`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsgetn(__int64 a1, char *a2, __int64 a3)
{
  size_t v7; // rbp
  const void *v8; // rdx
  int v9; // ecx
  size_t v10; // rbx
  _QWORD *v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rdx
  size_t v14; // rax

  if ( a3 <= 0 )
    return 0;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsgetn();
  v7 = a3;
  v8 = **(const void ***)(a1 + 56);
  if ( v8 )
    v9 = **(_DWORD **)(a1 + 80);
  else
    v9 = 0;
  if ( v9 )
  {
    v10 = a3;
    if ( v9 < (unsigned __int64)a3 )
      v10 = v9;
    memcpy_0(a2, v8, v10);
    a2 += v10;
    v7 = a3 - v10;
    **(_DWORD **)(a1 + 80) -= v10;
    **(_QWORD **)(a1 + 56) += (int)v10;
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    v11 = *(_QWORD **)(a1 + 24);
    if ( *v11 == a1 + 112 )
    {
      v12 = *(_QWORD *)(a1 + 136);
      v13 = *(_QWORD *)(a1 + 144);
      *v11 = v12;
      **(_QWORD **)(a1 + 56) = v12;
      **(_DWORD **)(a1 + 80) = v13 - v12;
    }
    while ( v7 > 0xFFF )
    {
      v14 = fread(a2, 1u, 0xFFFu, *(FILE **)(a1 + 128));
      v7 -= v14;
      if ( v14 != 4095 )
        return a3 - v7;
      a2 += 4095;
    }
    if ( v7 )
      v7 -= fread(a2, 1u, v7, *(FILE **)(a1 + 128));
  }
  return a3 - v7;
}

```

## disassembly

```asm
0x180035160  push    rbx
0x180035162  push    rbp
0x180035163  push    rsi
0x180035164  push    rdi
0x180035165  push    r14
0x180035167  sub     rsp, 20h
0x18003516b  mov     rdi, r8
0x18003516e  mov     r14, rdx
0x180035171  mov     rsi, rcx
0x180035174  test    r8, r8
0x180035177  jg      short loc_180035180
0x180035179  xor     eax, eax
0x18003517b  jmp     loc_180035269
0x180035180  cmp     qword ptr [rcx+68h], 0
0x180035185  jz      short loc_180035192
0x180035187  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x18003518d  jmp     loc_180035269
0x180035192  mov     rax, [rcx+38h]
0x180035196  mov     rbp, rdi
0x180035199  mov     rdx, [rax]; Src
0x18003519c  test    rdx, rdx
0x18003519f  jz      short loc_1800351A9
0x1800351a1  mov     rax, [rcx+50h]
0x1800351a5  mov     ecx, [rax]
0x1800351a7  jmp     short loc_1800351AB
0x1800351a9  xor     ecx, ecx
0x1800351ab  movsxd  rax, ecx
0x1800351ae  test    ecx, ecx
0x1800351b0  jz      short loc_1800351DD
0x1800351b2  cmp     rax, rdi
0x1800351b5  mov     rbx, rdi
0x1800351b8  mov     rcx, r14; void *
0x1800351bb  cmovb   rbx, rax
0x1800351bf  mov     r8, rbx; Size
0x1800351c2  call    memcpy_0
0x1800351c7  mov     rax, [rsi+50h]
0x1800351cb  add     r14, rbx
0x1800351ce  sub     rbp, rbx
0x1800351d1  sub     [rax], ebx
0x1800351d3  mov     rcx, [rsi+38h]
0x1800351d7  movsxd  rax, ebx
0x1800351da  add     [rcx], rax
0x1800351dd  cmp     qword ptr [rsi+80h], 0
0x1800351e5  jz      short loc_180035263
0x1800351e7  mov     r8, [rsi+18h]
0x1800351eb  lea     rax, [rsi+70h]
0x1800351ef  cmp     [r8], rax
0x1800351f2  jnz     short loc_180035214
0x1800351f4  mov     rcx, [rsi+88h]
0x1800351fb  mov     rdx, [rsi+90h]
0x180035202  mov     [r8], rcx
0x180035205  sub     edx, ecx
0x180035207  mov     rax, [rsi+38h]
0x18003520b  mov     [rax], rcx
0x18003520e  mov     rax, [rsi+50h]
0x180035212  mov     [rax], edx
0x180035214  mov     ebx, 0FFFh
0x180035219  jmp     short loc_18003523E
0x18003521b  mov     r9, [rsi+80h]; Stream
0x180035222  mov     r8, rbx; ElementCount
0x180035225  mov     edx, 1; ElementSize
0x18003522a  mov     rcx, r14; Buffer
0x18003522d  call    cs:__imp_fread
0x180035233  sub     rbp, rax
0x180035236  cmp     rax, rbx
0x180035239  jnz     short loc_180035263
0x18003523b  add     r14, rbx
0x18003523e  cmp     rbp, rbx
0x180035241  ja      short loc_18003521B
0x180035243  test    rbp, rbp
0x180035246  jz      short loc_180035263
0x180035248  mov     r9, [rsi+80h]; Stream
0x18003524f  mov     r8, rbp; ElementCount
0x180035252  mov     edx, 1; ElementSize
0x180035257  mov     rcx, r14; Buffer
0x18003525a  call    cs:__imp_fread
0x180035260  sub     rbp, rax
0x180035263  sub     rdi, rbp
0x180035266  mov     rax, rdi
0x180035269  add     rsp, 20h
0x18003526d  pop     r14
0x18003526f  pop     rdi
0x180035270  pop     rsi
0x180035271  pop     rbp
0x180035272  pop     rbx
0x180035273  retn
```
