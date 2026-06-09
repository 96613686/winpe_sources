# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x18000c7d0`
- end: `0x18000c939`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `361`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001a70`
- `0x18000c484`
- `0x18000c7d0`

## import_xrefs

- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18000c80a`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18000c824`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18000c80a`
- `msvcp_win!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18000c824`
- `msvcp_win!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18000c818`
- `msvcp_win!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x18000c818`
- `msvcp_win!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x18000c832`
- `msvcp_win!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x18000c832`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x18000c8be`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x18000c8be`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x18000c86d`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x18000c86d`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18000c8f8`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18000c8f8`

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
0x18000c7d0  mov     [rsp-18h+arg_10], rbx
0x18000c7d5  mov     [rsp-18h+arg_18], rsi
0x18000c7da  push    rbp
0x18000c7db  push    rdi
0x18000c7dc  push    r14
0x18000c7de  mov     rbp, rsp
0x18000c7e1  sub     rsp, 80h
0x18000c7e8  mov     rax, cs:__security_cookie
0x18000c7ef  xor     rax, rsp
0x18000c7f2  mov     [rbp+var_8], rax
0x18000c7f6  or      edi, 0FFFFFFFFh
0x18000c7f9  mov     r14d, edx
0x18000c7fc  mov     rsi, rcx
0x18000c7ff  cmp     edx, edi
0x18000c801  jnz     short loc_18000C80A
0x18000c803  xor     eax, eax
0x18000c805  jmp     loc_18000C915
0x18000c80a  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x18000c810  test    rax, rax
0x18000c813  jz      short loc_18000C843
0x18000c815  mov     rcx, rsi
0x18000c818  call    cs:__imp_?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::epptr(void)
0x18000c81e  mov     rcx, rsi
0x18000c821  mov     rbx, rax
0x18000c824  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x18000c82a  cmp     rax, rbx
0x18000c82d  jnb     short loc_18000C843
0x18000c82f  mov     rcx, rsi
0x18000c832  call    cs:__imp_?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ; std::streambuf::_Pninc(void)
0x18000c838  mov     [rax], r14b
0x18000c83b  mov     eax, r14d
0x18000c83e  jmp     loc_18000C915
0x18000c843  cmp     qword ptr [rsi+80h], 0
0x18000c84b  jz      loc_18000C913
0x18000c851  mov     rcx, rsi
0x18000c854  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x18000c859  mov     rcx, [rsi+68h]
0x18000c85d  test    rcx, rcx
0x18000c860  jnz     short loc_18000C87A
0x18000c862  movsx   ecx, r14b
0x18000c866  mov     rdx, [rsi+80h]
0x18000c86d  call    cs:__imp__o_fputc
0x18000c873  cmp     eax, edi
0x18000c875  jmp     loc_18000C90F
0x18000c87a  lea     rax, [rbp+var_38]
0x18000c87e  mov     [rbp+var_40], r14b
0x18000c882  mov     [rsp+80h+var_48], rax
0x18000c887  lea     rdx, [rsi+74h]
0x18000c88b  lea     rax, [rbp+var_8]
0x18000c88f  mov     [rbp+var_30], 0
0x18000c897  mov     [rsp+80h+var_50], rax
0x18000c89c  lea     r9, [rbp+var_3F]
0x18000c8a0  lea     rax, [rbp+var_28]
0x18000c8a4  mov     [rbp+var_38], 0
0x18000c8ac  mov     [rsp+80h+var_58], rax
0x18000c8b1  lea     r8, [rbp+var_40]
0x18000c8b5  lea     rax, [rbp+var_30]
0x18000c8b9  mov     [rsp+80h+var_60], rax
0x18000c8be  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x18000c8c4  test    eax, eax
0x18000c8c6  jz      short loc_18000C8D8
0x18000c8c8  sub     eax, 1
0x18000c8cb  jz      short loc_18000C8D8
0x18000c8cd  cmp     eax, 2
0x18000c8d0  jnz     short loc_18000C913
0x18000c8d2  movsx   ecx, [rbp+var_40]
0x18000c8d6  jmp     short loc_18000C866
0x18000c8d8  mov     rbx, [rbp+var_38]
0x18000c8dc  lea     rax, [rbp+var_28]
0x18000c8e0  sub     rbx, rax
0x18000c8e3  jz      short loc_18000C903
0x18000c8e5  mov     r9, [rsi+80h]
0x18000c8ec  lea     rcx, [rbp+var_28]
0x18000c8f0  mov     r8, rbx
0x18000c8f3  mov     edx, 1
0x18000c8f8  call    cs:__imp__o_fwrite
0x18000c8fe  cmp     rbx, rax
0x18000c901  jnz     short loc_18000C913
0x18000c903  lea     rax, [rbp+var_40]
0x18000c907  mov     byte ptr [rsi+71h], 1
0x18000c90b  cmp     [rbp+var_30], rax
0x18000c90f  cmovnz  edi, r14d
0x18000c913  mov     eax, edi
0x18000c915  mov     rcx, [rbp+var_8]
0x18000c919  xor     rcx, rsp; StackCookie
0x18000c91c  call    __security_check_cookie
0x18000c921  lea     r11, [rsp+80h+var_s0]
0x18000c929  mov     rbx, [r11+30h]
0x18000c92d  mov     rsi, [r11+38h]
0x18000c931  mov     rsp, r11
0x18000c934  pop     r14
0x18000c936  pop     rdi
0x18000c937  pop     rbp
0x18000c938  retn
```
