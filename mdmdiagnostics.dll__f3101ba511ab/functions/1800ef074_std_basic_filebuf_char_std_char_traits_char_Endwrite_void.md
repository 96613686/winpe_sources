# std::basic_filebuf<char,std::char_traits<char>>::_Endwrite(void)

- ea: `0x1800ef074`
- end: `0x1800ef162`
- name: `?_Endwrite@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAA_NXZ`
- size: `238`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800f0224`
- `0x1800f2390`
- `0x1800f2790`

## callees

- `0x180019080`
- `0x1800ef074`
- `0x1800f1120`
- `0x180193010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x1800ef0e4`
- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x1800ef0e4`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800ef144`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800ef144`

## pseudocode

```c
bool __fastcall std::filebuf::_Endwrite(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // rcx
  int v4; // eax
  int v5; // eax
  __int64 v7; // rdi
  _BYTE *v8; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v10; // [rsp+58h] [rbp-10h] BYREF

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 113) )
    return 1;
  v2 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFFFFFFLL);
  if ( (unsigned __int8)std::_Narrow_char_traits<char,int>::eq_int_type(0xFFFFFFFFLL, v2) )
    return 0;
  v3 = *(_QWORD *)(a1 + 104);
  v8 = 0;
  v4 = std::codecvt<char,char,_Mbstatet>::unshift(v3, a1 + 116, v9, &v10, &v8);
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      if ( v5 == 2 )
      {
        *(_BYTE *)(a1 + 113) = 0;
        return 1;
      }
      return 0;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 113) = 0;
  }
  if ( v8 == v9 )
    return *(_BYTE *)(a1 + 113) == 0;
  v7 = v8 - v9;
  if ( v7 == _o_fwrite(v9, 1, v8 - v9, *(_QWORD *)(a1 + 128)) )
    return *(_BYTE *)(a1 + 113) == 0;
  return 0;
}

```

## disassembly

```asm
0x1800ef074  mov     [rsp+arg_8], rbx
0x1800ef079  push    rdi
0x1800ef07a  sub     rsp, 60h
0x1800ef07e  mov     rax, cs:__security_cookie
0x1800ef085  xor     rax, rsp
0x1800ef088  mov     [rsp+68h+var_10], rax
0x1800ef08d  cmp     qword ptr [rcx+68h], 0
0x1800ef092  mov     rbx, rcx
0x1800ef095  jz      short loc_1800EF102
0x1800ef097  cmp     byte ptr [rcx+71h], 0
0x1800ef09b  jz      short loc_1800EF102
0x1800ef09d  mov     rax, [rcx]
0x1800ef0a0  or      edi, 0FFFFFFFFh
0x1800ef0a3  mov     edx, edi
0x1800ef0a5  mov     rax, [rax+18h]
0x1800ef0a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef0ae  mov     edx, eax
0x1800ef0b0  mov     ecx, edi
0x1800ef0b2  call    ?eq_int_type@?$_Narrow_char_traits@DH@std@@SA_NHH@Z; std::_Narrow_char_traits<char,int>::eq_int_type(int,int)
0x1800ef0b7  test    al, al
0x1800ef0b9  jnz     loc_1800EF15E
0x1800ef0bf  mov     rcx, [rbx+68h]
0x1800ef0c3  lea     rax, [rsp+68h+var_38]
0x1800ef0c8  lea     rdx, [rbx+74h]
0x1800ef0cc  mov     [rsp+68h+var_48], rax
0x1800ef0d1  lea     r9, [rsp+68h+var_10]
0x1800ef0d6  mov     [rsp+68h+var_38], 0
0x1800ef0df  lea     r8, [rsp+68h+var_30]
0x1800ef0e4  call    cs:__imp_?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x1800ef0eb  nop     dword ptr [rax+rax+00h]
0x1800ef0f0  test    eax, eax
0x1800ef0f2  jz      short loc_1800EF11D
0x1800ef0f4  sub     eax, 1
0x1800ef0f7  jz      short loc_1800EF121
0x1800ef0f9  cmp     eax, 2
0x1800ef0fc  jnz     short loc_1800EF15E
0x1800ef0fe  mov     byte ptr [rbx+71h], 0
0x1800ef102  mov     al, 1
0x1800ef104  mov     rcx, [rsp+68h+var_10]
0x1800ef109  xor     rcx, rsp; StackCookie
0x1800ef10c  call    __security_check_cookie
0x1800ef111  mov     rbx, [rsp+68h+arg_8]
0x1800ef116  add     rsp, 60h
0x1800ef11a  pop     rdi
0x1800ef11b  retn
0x1800ef11d  mov     byte ptr [rbx+71h], 0
0x1800ef121  mov     rdi, [rsp+68h+var_38]
0x1800ef126  lea     rax, [rsp+68h+var_30]
0x1800ef12b  sub     rdi, rax
0x1800ef12e  jz      short loc_1800EF155
0x1800ef130  mov     r9, [rbx+80h]
0x1800ef137  lea     rcx, [rsp+68h+var_30]
0x1800ef13c  mov     r8, rdi
0x1800ef13f  mov     edx, 1
0x1800ef144  call    cs:__imp__o_fwrite
0x1800ef14b  nop     dword ptr [rax+rax+00h]
0x1800ef150  cmp     rdi, rax
0x1800ef153  jnz     short loc_1800EF15E
0x1800ef155  cmp     byte ptr [rbx+71h], 0
0x1800ef159  setz    al
0x1800ef15c  jmp     short loc_1800EF104
0x1800ef15e  xor     al, al
0x1800ef160  jmp     short loc_1800EF104
```
