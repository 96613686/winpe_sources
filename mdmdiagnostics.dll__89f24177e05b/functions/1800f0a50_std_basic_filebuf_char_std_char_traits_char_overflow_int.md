# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x1800f0a50`
- end: `0x1800f0bdb`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `395`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180019000`
- `0x1800ef208`
- `0x1800f08b4`
- `0x1800f0a24`
- `0x1800f0a50`
- `0x1800f4058`

## import_xrefs

- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x1800f0b5f`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x1800f0b5f`
- `msvcp_win!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x1800f0ac2`
- `msvcp_win!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x1800f0ac2`
- `msvcp_win!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f0aa8`
- `msvcp_win!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f0aa8`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f0a9a`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f0ab4`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f0a9a`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800f0ab4`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x1800f0b09`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x1800f0b09`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800f0b99`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800f0b99`

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
0x1800f0a50  mov     [rsp-18h+arg_10], rbx
0x1800f0a55  mov     [rsp-18h+arg_18], rsi
0x1800f0a5a  push    rbp
0x1800f0a5b  push    rdi
0x1800f0a5c  push    r14
0x1800f0a5e  mov     rbp, rsp
0x1800f0a61  sub     rsp, 80h
0x1800f0a68  mov     rax, cs:__security_cookie
0x1800f0a6f  xor     rax, rsp
0x1800f0a72  mov     [rbp+var_8], rax
0x1800f0a76  mov     rsi, rcx
0x1800f0a79  or      r14d, 0FFFFFFFFh
0x1800f0a7d  mov     ecx, r14d
0x1800f0a80  mov     edi, edx
0x1800f0a82  call    ?eq_int_type@?$_Narrow_char_traits@DH@std@@SA_NHH@Z; std::_Narrow_char_traits<char,int>::eq_int_type(int,int)
0x1800f0a87  test    al, al
0x1800f0a89  jz      short loc_1800F0A97
0x1800f0a8b  mov     ecx, edi
0x1800f0a8d  call    ?not_eof@?$_Narrow_char_traits@DH@std@@SAHH@Z; std::_Narrow_char_traits<char,int>::not_eof(int)
0x1800f0a92  jmp     loc_1800F0BB7
0x1800f0a97  mov     rcx, rsi
0x1800f0a9a  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x1800f0aa0  test    rax, rax
0x1800f0aa3  jz      short loc_1800F0ADB
0x1800f0aa5  mov     rcx, rsi
0x1800f0aa8  call    cs:__imp_?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::epptr(void)
0x1800f0aae  mov     rcx, rsi
0x1800f0ab1  mov     rbx, rax
0x1800f0ab4  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x1800f0aba  cmp     rax, rbx
0x1800f0abd  jnb     short loc_1800F0ADB
0x1800f0abf  mov     rcx, rsi
0x1800f0ac2  call    cs:__imp_?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ; std::streambuf::_Pninc(void)
0x1800f0ac8  mov     ecx, edi
0x1800f0aca  mov     rbx, rax
0x1800f0acd  call    ?to_char_type@?$_Narrow_char_traits@DH@std@@SADH@Z; std::_Narrow_char_traits<char,int>::to_char_type(int)
0x1800f0ad2  mov     [rbx], al
0x1800f0ad4  mov     eax, edi
0x1800f0ad6  jmp     loc_1800F0BB7
0x1800f0adb  cmp     qword ptr [rsi+80h], 0
0x1800f0ae3  jz      loc_1800F0BB4
0x1800f0ae9  mov     rcx, rsi
0x1800f0aec  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x1800f0af1  mov     ecx, edi
0x1800f0af3  call    ?to_char_type@?$_Narrow_char_traits@DH@std@@SADH@Z; std::_Narrow_char_traits<char,int>::to_char_type(int)
0x1800f0af8  cmp     qword ptr [rsi+68h], 0
0x1800f0afd  jnz     short loc_1800F0B18
0x1800f0aff  movsx   ecx, al
0x1800f0b02  mov     rdx, [rsi+80h]
0x1800f0b09  call    cs:__imp__o_fputc
0x1800f0b0f  cmp     eax, r14d
0x1800f0b12  cmovz   edi, r14d
0x1800f0b16  jmp     short loc_1800F0AD4
0x1800f0b18  mov     rcx, [rsi+68h]
0x1800f0b1c  lea     rdx, [rsi+74h]
0x1800f0b20  mov     [rbp+var_40], al
0x1800f0b23  lea     r9, [rbp+var_3F]
0x1800f0b27  lea     rax, [rbp+var_38]
0x1800f0b2b  mov     [rbp+var_30], 0
0x1800f0b33  mov     [rsp+80h+var_48], rax
0x1800f0b38  lea     r8, [rbp+var_40]
0x1800f0b3c  lea     rax, [rbp+var_8]
0x1800f0b40  mov     [rbp+var_38], 0
0x1800f0b48  mov     [rsp+80h+var_50], rax
0x1800f0b4d  lea     rax, [rbp+var_28]
0x1800f0b51  mov     [rsp+80h+var_58], rax
0x1800f0b56  lea     rax, [rbp+var_30]
0x1800f0b5a  mov     [rsp+80h+var_60], rax
0x1800f0b5f  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x1800f0b65  test    eax, eax
0x1800f0b67  jz      short loc_1800F0B79
0x1800f0b69  sub     eax, 1
0x1800f0b6c  jz      short loc_1800F0B79
0x1800f0b6e  cmp     eax, 2
0x1800f0b71  jnz     short loc_1800F0BB4
0x1800f0b73  movsx   ecx, [rbp+var_40]
0x1800f0b77  jmp     short loc_1800F0B02
0x1800f0b79  mov     rbx, [rbp+var_38]
0x1800f0b7d  lea     rax, [rbp+var_28]
0x1800f0b81  sub     rbx, rax
0x1800f0b84  jz      short loc_1800F0BA4
0x1800f0b86  mov     r9, [rsi+80h]
0x1800f0b8d  lea     rcx, [rbp+var_28]
0x1800f0b91  mov     r8, rbx
0x1800f0b94  mov     edx, 1
0x1800f0b99  call    cs:__imp__o_fwrite
0x1800f0b9f  cmp     rbx, rax
0x1800f0ba2  jnz     short loc_1800F0BB4
0x1800f0ba4  lea     rax, [rbp+var_40]
0x1800f0ba8  mov     byte ptr [rsi+71h], 1
0x1800f0bac  cmp     [rbp+var_30], rax
0x1800f0bb0  cmovnz  r14d, edi
0x1800f0bb4  mov     eax, r14d
0x1800f0bb7  mov     rcx, [rbp+var_8]
0x1800f0bbb  xor     rcx, rsp; StackCookie
0x1800f0bbe  call    __security_check_cookie
0x1800f0bc3  lea     r11, [rsp+80h+var_s0]
0x1800f0bcb  mov     rbx, [r11+30h]
0x1800f0bcf  mov     rsi, [r11+38h]
0x1800f0bd3  mov     rsp, r11
0x1800f0bd6  pop     r14
0x1800f0bd8  pop     rdi
0x1800f0bd9  pop     rbp
0x1800f0bda  retn
```
