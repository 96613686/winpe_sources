# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x18007ebd0`
- end: `0x18007ed39`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18004ca90`
- `0x18007e894`
- `0x18007ebd0`

## import_xrefs

- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x18007ecbe`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x18007ecbe`
- `msvcp_win!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x18007ec32`
- `msvcp_win!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x18007ec32`
- `msvcp_win!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18007ec18`
- `msvcp_win!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18007ec18`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18007ec0a`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18007ec24`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18007ec0a`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18007ec24`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x18007ec6d`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x18007ec6d`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18007ecf8`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18007ecf8`

## pseudocode

```c
__int64 __fastcall std::filebuf::overflow(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  bool v9; // zf
  int v10; // eax
  int v11; // eax
  __int64 v12; // rbx
  char v13; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v14[7]; // [rsp+41h] [rbp-3Fh] BYREF
  _BYTE *v15; // [rsp+48h] [rbp-38h] BYREF
  char *v16; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v17[32]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v18; // [rsp+78h] [rbp-8h] BYREF

  v2 = -1;
  if ( a2 == -1 )
    return 0;
  if ( ((__int64 (*)(void))std::streambuf::pptr)() )
  {
    v6 = std::streambuf::epptr(a1);
    if ( std::streambuf::pptr(a1) < v6 )
    {
      *(_BYTE *)std::streambuf::_Pninc(a1) = a2;
      return a2;
    }
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    std::filebuf::_Reset_back(a1);
    v7 = *(_QWORD *)(a1 + 104);
    if ( !v7 )
    {
      v8 = (unsigned int)(char)a2;
LABEL_9:
      v9 = (unsigned int)_o_fputc(v8, *(_QWORD *)(a1 + 128)) == -1;
LABEL_17:
      if ( !v9 )
        return a2;
      return v2;
    }
    v13 = a2;
    v16 = 0;
    v15 = 0;
    v10 = std::codecvt<char,char,_Mbstatet>::out(v7, a1 + 116, &v13, v14, &v16, v17, &v18, &v15);
    if ( !v10 || (v11 = v10 - 1) == 0 )
    {
      if ( v15 != v17 )
      {
        v12 = v15 - v17;
        if ( v12 != _o_fwrite(v17, 1, v15 - v17, *(_QWORD *)(a1 + 128)) )
          return v2;
      }
      *(_BYTE *)(a1 + 113) = 1;
      v9 = v16 == &v13;
      goto LABEL_17;
    }
    if ( v11 == 2 )
    {
      v8 = (unsigned int)v13;
      goto LABEL_9;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18007ebd0  mov     [rsp-18h+arg_10], rbx
0x18007ebd5  mov     [rsp-18h+arg_18], rsi
0x18007ebda  push    rbp
0x18007ebdb  push    rdi
0x18007ebdc  push    r14
0x18007ebde  mov     rbp, rsp
0x18007ebe1  sub     rsp, 80h
0x18007ebe8  mov     rax, cs:__security_cookie
0x18007ebef  xor     rax, rsp
0x18007ebf2  mov     [rbp+var_8], rax
0x18007ebf6  or      edi, 0FFFFFFFFh
0x18007ebf9  mov     r14d, edx
0x18007ebfc  mov     rsi, rcx
0x18007ebff  cmp     edx, edi
0x18007ec01  jnz     short loc_18007EC0A
0x18007ec03  xor     eax, eax
0x18007ec05  jmp     loc_18007ED15
0x18007ec0a  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x18007ec10  test    rax, rax
0x18007ec13  jz      short loc_18007EC43
0x18007ec15  mov     rcx, rsi
0x18007ec18  call    cs:__imp_?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::epptr(void)
0x18007ec1e  mov     rcx, rsi
0x18007ec21  mov     rbx, rax
0x18007ec24  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x18007ec2a  cmp     rax, rbx
0x18007ec2d  jnb     short loc_18007EC43
0x18007ec2f  mov     rcx, rsi
0x18007ec32  call    cs:__imp_?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ; std::streambuf::_Pninc(void)
0x18007ec38  mov     [rax], r14b
0x18007ec3b  mov     eax, r14d
0x18007ec3e  jmp     loc_18007ED15
0x18007ec43  cmp     qword ptr [rsi+80h], 0
0x18007ec4b  jz      loc_18007ED13
0x18007ec51  mov     rcx, rsi
0x18007ec54  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x18007ec59  mov     rcx, [rsi+68h]
0x18007ec5d  test    rcx, rcx
0x18007ec60  jnz     short loc_18007EC7A
0x18007ec62  movsx   ecx, r14b
0x18007ec66  mov     rdx, [rsi+80h]
0x18007ec6d  call    cs:__imp__o_fputc
0x18007ec73  cmp     eax, edi
0x18007ec75  jmp     loc_18007ED0F
0x18007ec7a  lea     rax, [rbp+var_38]
0x18007ec7e  mov     [rbp+var_40], r14b
0x18007ec82  mov     [rsp+80h+var_48], rax
0x18007ec87  lea     rdx, [rsi+74h]
0x18007ec8b  lea     rax, [rbp+var_8]
0x18007ec8f  mov     [rbp+var_30], 0
0x18007ec97  mov     [rsp+80h+var_50], rax
0x18007ec9c  lea     r9, [rbp+var_3F]
0x18007eca0  lea     rax, [rbp+var_28]
0x18007eca4  mov     [rbp+var_38], 0
0x18007ecac  mov     [rsp+80h+var_58], rax
0x18007ecb1  lea     r8, [rbp+var_40]
0x18007ecb5  lea     rax, [rbp+var_30]
0x18007ecb9  mov     [rsp+80h+var_60], rax
0x18007ecbe  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x18007ecc4  test    eax, eax
0x18007ecc6  jz      short loc_18007ECD8
0x18007ecc8  sub     eax, 1
0x18007eccb  jz      short loc_18007ECD8
0x18007eccd  cmp     eax, 2
0x18007ecd0  jnz     short loc_18007ED13
0x18007ecd2  movsx   ecx, [rbp+var_40]
0x18007ecd6  jmp     short loc_18007EC66
0x18007ecd8  mov     rbx, [rbp+var_38]
0x18007ecdc  lea     rax, [rbp+var_28]
0x18007ece0  sub     rbx, rax
0x18007ece3  jz      short loc_18007ED03
0x18007ece5  mov     r9, [rsi+80h]
0x18007ecec  lea     rcx, [rbp+var_28]
0x18007ecf0  mov     r8, rbx
0x18007ecf3  mov     edx, 1
0x18007ecf8  call    cs:__imp__o_fwrite
0x18007ecfe  cmp     rbx, rax
0x18007ed01  jnz     short loc_18007ED13
0x18007ed03  lea     rax, [rbp+var_40]
0x18007ed07  mov     byte ptr [rsi+71h], 1
0x18007ed0b  cmp     [rbp+var_30], rax
0x18007ed0f  cmovnz  edi, r14d
0x18007ed13  mov     eax, edi
0x18007ed15  mov     rcx, [rbp+var_8]
0x18007ed19  xor     rcx, rsp; StackCookie
0x18007ed1c  call    __security_check_cookie
0x18007ed21  lea     r11, [rsp+80h+var_s0]
0x18007ed29  mov     rbx, [r11+30h]
0x18007ed2d  mov     rsi, [r11+38h]
0x18007ed31  mov     rsp, r11
0x18007ed34  pop     r14
0x18007ed36  pop     rdi
0x18007ed37  pop     rbp
0x18007ed38  retn
```
