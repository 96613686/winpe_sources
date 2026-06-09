# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x1800f12e0`
- end: `0x1800f1499`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `441`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180019080`
- `0x1800ef948`
- `0x1800f1120`
- `0x1800f12a4`
- `0x1800f12e0`
- `0x1800f4bb0`

## import_xrefs

- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x1800f140d`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x1800f140d`
- `msvcp_win!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x1800f1364`
- `msvcp_win!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x1800f1364`
- `msvcp_win!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f133e`
- `msvcp_win!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f133e`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f132a`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f1350`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f132a`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f1350`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x1800f13b1`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x1800f13b1`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800f1450`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800f1450`

## pseudocode

```c
__int64 __fastcall std::filebuf::overflow(__int64 a1, __int64 a2)
{
  unsigned int v3; // r14d
  unsigned int v4; // edi
  unsigned __int64 v6; // rbx
  _BYTE *v7; // rbx
  char v8; // al
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rbx
  char v14; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v15[7]; // [rsp+41h] [rbp-3Fh] BYREF
  _BYTE *v16; // [rsp+48h] [rbp-38h] BYREF
  char *v17; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v18[32]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v19; // [rsp+78h] [rbp-8h] BYREF

  v3 = -1;
  v4 = a2;
  if ( (unsigned __int8)std::_Narrow_char_traits<char,int>::eq_int_type(0xFFFFFFFFLL, a2) )
    return std::_Narrow_char_traits<char,int>::not_eof(v4);
  if ( std::streambuf::pptr(a1) )
  {
    v6 = std::streambuf::epptr(a1);
    if ( std::streambuf::pptr(a1) < v6 )
    {
      v7 = (_BYTE *)std::streambuf::_Pninc(a1);
      *v7 = std::_Narrow_char_traits<char,int>::to_char_type(v4);
      return v4;
    }
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    std::filebuf::_Reset_back(a1);
    v8 = std::_Narrow_char_traits<char,int>::to_char_type(v4);
    if ( !*(_QWORD *)(a1 + 104) )
    {
      v9 = (unsigned int)v8;
      goto LABEL_10;
    }
    v10 = *(_QWORD *)(a1 + 104);
    v14 = v8;
    v17 = 0;
    v16 = 0;
    v11 = std::codecvt<char,char,_Mbstatet>::out(v10, a1 + 116, &v14, v15, &v17, v18, &v19, &v16);
    if ( v11 && (v12 = v11 - 1) != 0 )
    {
      if ( v12 == 2 )
      {
        v9 = (unsigned int)v14;
LABEL_10:
        if ( (unsigned int)_o_fputc(v9, *(_QWORD *)(a1 + 128)) == -1 )
          return (unsigned int)-1;
        return v4;
      }
    }
    else if ( v16 == v18 || (v13 = v16 - v18, v13 == _o_fwrite(v18, 1, v16 - v18, *(_QWORD *)(a1 + 128))) )
    {
      *(_BYTE *)(a1 + 113) = 1;
      if ( v17 != &v14 )
        return v4;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800f12e0  mov     [rsp-18h+arg_10], rbx
0x1800f12e5  mov     [rsp-18h+arg_18], rsi
0x1800f12ea  push    rbp
0x1800f12eb  push    rdi
0x1800f12ec  push    r14
0x1800f12ee  mov     rbp, rsp
0x1800f12f1  sub     rsp, 80h
0x1800f12f8  mov     rax, cs:__security_cookie
0x1800f12ff  xor     rax, rsp
0x1800f1302  mov     [rbp+var_8], rax
0x1800f1306  mov     rsi, rcx
0x1800f1309  or      r14d, 0FFFFFFFFh
0x1800f130d  mov     ecx, r14d
0x1800f1310  mov     edi, edx
0x1800f1312  call    ?eq_int_type@?$_Narrow_char_traits@DH@std@@SA_NHH@Z; std::_Narrow_char_traits<char,int>::eq_int_type(int,int)
0x1800f1317  test    al, al
0x1800f1319  jz      short loc_1800F1327
0x1800f131b  mov     ecx, edi
0x1800f131d  call    ?not_eof@?$_Narrow_char_traits@DH@std@@SAHH@Z; std::_Narrow_char_traits<char,int>::not_eof(int)
0x1800f1322  jmp     loc_1800F1474
0x1800f1327  mov     rcx, rsi
0x1800f132a  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x1800f1331  nop     dword ptr [rax+rax+00h]
0x1800f1336  test    rax, rax
0x1800f1339  jz      short loc_1800F1383
0x1800f133b  mov     rcx, rsi
0x1800f133e  call    cs:__imp_?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::epptr(void)
0x1800f1345  nop     dword ptr [rax+rax+00h]
0x1800f134a  mov     rcx, rsi
0x1800f134d  mov     rbx, rax
0x1800f1350  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x1800f1357  nop     dword ptr [rax+rax+00h]
0x1800f135c  cmp     rax, rbx
0x1800f135f  jnb     short loc_1800F1383
0x1800f1361  mov     rcx, rsi
0x1800f1364  call    cs:__imp_?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ; std::streambuf::_Pninc(void)
0x1800f136b  nop     dword ptr [rax+rax+00h]
0x1800f1370  mov     ecx, edi
0x1800f1372  mov     rbx, rax
0x1800f1375  call    ?to_char_type@?$_Narrow_char_traits@DH@std@@SADH@Z; std::_Narrow_char_traits<char,int>::to_char_type(int)
0x1800f137a  mov     [rbx], al
0x1800f137c  mov     eax, edi
0x1800f137e  jmp     loc_1800F1474
0x1800f1383  cmp     qword ptr [rsi+80h], 0
0x1800f138b  jz      loc_1800F1471
0x1800f1391  mov     rcx, rsi
0x1800f1394  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x1800f1399  mov     ecx, edi
0x1800f139b  call    ?to_char_type@?$_Narrow_char_traits@DH@std@@SADH@Z; std::_Narrow_char_traits<char,int>::to_char_type(int)
0x1800f13a0  cmp     qword ptr [rsi+68h], 0
0x1800f13a5  jnz     short loc_1800F13C6
0x1800f13a7  movsx   ecx, al
0x1800f13aa  mov     rdx, [rsi+80h]
0x1800f13b1  call    cs:__imp__o_fputc
0x1800f13b8  nop     dword ptr [rax+rax+00h]
0x1800f13bd  cmp     eax, r14d
0x1800f13c0  cmovz   edi, r14d
0x1800f13c4  jmp     short loc_1800F137C
0x1800f13c6  mov     rcx, [rsi+68h]
0x1800f13ca  lea     rdx, [rsi+74h]
0x1800f13ce  mov     [rbp+var_40], al
0x1800f13d1  lea     r9, [rbp+var_3F]
0x1800f13d5  lea     rax, [rbp+var_38]
0x1800f13d9  mov     [rbp+var_30], 0
0x1800f13e1  mov     [rsp+80h+var_48], rax
0x1800f13e6  lea     r8, [rbp+var_40]
0x1800f13ea  lea     rax, [rbp+var_8]
0x1800f13ee  mov     [rbp+var_38], 0
0x1800f13f6  mov     [rsp+80h+var_50], rax
0x1800f13fb  lea     rax, [rbp+var_28]
0x1800f13ff  mov     [rsp+80h+var_58], rax
0x1800f1404  lea     rax, [rbp+var_30]
0x1800f1408  mov     [rsp+80h+var_60], rax
0x1800f140d  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x1800f1414  nop     dword ptr [rax+rax+00h]
0x1800f1419  test    eax, eax
0x1800f141b  jz      short loc_1800F1430
0x1800f141d  sub     eax, 1
0x1800f1420  jz      short loc_1800F1430
0x1800f1422  cmp     eax, 2
0x1800f1425  jnz     short loc_1800F1471
0x1800f1427  movsx   ecx, [rbp+var_40]
0x1800f142b  jmp     loc_1800F13AA
0x1800f1430  mov     rbx, [rbp+var_38]
0x1800f1434  lea     rax, [rbp+var_28]
0x1800f1438  sub     rbx, rax
0x1800f143b  jz      short loc_1800F1461
0x1800f143d  mov     r9, [rsi+80h]
0x1800f1444  lea     rcx, [rbp+var_28]
0x1800f1448  mov     r8, rbx
0x1800f144b  mov     edx, 1
0x1800f1450  call    cs:__imp__o_fwrite
0x1800f1457  nop     dword ptr [rax+rax+00h]
0x1800f145c  cmp     rbx, rax
0x1800f145f  jnz     short loc_1800F1471
0x1800f1461  lea     rax, [rbp+var_40]
0x1800f1465  mov     byte ptr [rsi+71h], 1
0x1800f1469  cmp     [rbp+var_30], rax
0x1800f146d  cmovnz  r14d, edi
0x1800f1471  mov     eax, r14d
0x1800f1474  mov     rcx, [rbp+var_8]
0x1800f1478  xor     rcx, rsp; StackCookie
0x1800f147b  call    __security_check_cookie
0x1800f1480  lea     r11, [rsp+80h+var_s0]
0x1800f1488  mov     rbx, [r11+30h]
0x1800f148c  mov     rsi, [r11+38h]
0x1800f1490  mov     rsp, r11
0x1800f1493  pop     r14
0x1800f1495  pop     rdi
0x1800f1496  pop     rbp
0x1800f1497  retn
```
