# LpacRegHelper::DeleteRegistryLpac(void *,ushort const *,ushort const *)

- ea: `0x18001fdec`
- end: `0x18001fec9`
- name: `?DeleteRegistryLpac@LpacRegHelper@@CAJPEAXPEBG1@Z`
- size: `221`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fc88`

## callees

- `0x1800040c0`
- `0x180004594`
- `0x180008044`
- `0x18001fdec`
- `0x180020488`
- `0x180021564`
- `0x180022830`

## string_xrefs

- `0x18001fe32`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001fe92`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LpacRegHelper::DeleteRegistryLpac(_WORD *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v3; // eax
  HKEY v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  char **v7; // rdx
  unsigned int v8; // eax
  const char *v9; // rdx
  int v11; // [rsp+20h] [rbp-48h]
  char *v12[3]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int64 v13; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v13 = 7;
  v12[2] = 0;
  LOWORD(v12[0]) = 0;
  v3 = LpacRegHelper::DeriveLpacTopRegistryKey(a1, (__int64)a2, (__int64)a3, (__int64)v12);
  v5 = v3;
  if ( v3 >= 0 )
  {
    v7 = v12;
    if ( v13 >= 8 )
      v7 = (char **)v12[0];
    v8 = RemoveRegistryTree(v4, (WCHAR *)v7);
    v5 = v8;
    if ( v8 && v8 != -2147024894 )
    {
      v9 = (const char *)v12;
      if ( v13 >= 8 )
        v9 = v12[0];
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x219,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
        (const char *)v8,
        (__int64)"Subkey %ls",
        v9);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x213,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)(unsigned int)v3,
      v11);
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v12, v6, 0);
  return v5;
}

```

## disassembly

```asm
0x18001fdec  push    rbx
0x18001fdee  sub     rsp, 60h
0x18001fdf2  mov     rax, cs:__security_cookie
0x18001fdf9  xor     rax, rsp
0x18001fdfc  mov     [rsp+68h+var_18], rax
0x18001fe01  mov     [rsp+68h+var_20], 7
0x18001fe0a  mov     [rsp+68h+var_28], 0
0x18001fe13  xor     eax, eax
0x18001fe15  mov     word ptr [rsp+68h+var_38], ax
0x18001fe1a  lea     r9, [rsp+68h+var_38]
0x18001fe1f  call    ?DeriveLpacTopRegistryKey@LpacRegHelper@@CAJPEAXPEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LpacRegHelper::DeriveLpacTopRegistryKey(void *,ushort const *,ushort const *,std::wstring &)
0x18001fe24  mov     ebx, eax
0x18001fe26  test    eax, eax
0x18001fe28  jns     short loc_18001FE45
0x18001fe2a  mov     rcx, [rsp+68h]; this
0x18001fe2f  mov     r9d, eax; char *
0x18001fe32  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001fe39  mov     edx, 213h; void *
0x18001fe3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe43  jmp     short loc_18001FEA4
0x18001fe45  lea     rdx, [rsp+68h+var_38]
0x18001fe4a  cmp     [rsp+68h+var_20], 8
0x18001fe50  cmovnb  rdx, [rsp+68h+var_38]; unsigned __int16 *
0x18001fe56  call    ?RemoveRegistryTree@@YAJPEAUHKEY__@@PEBG@Z; RemoveRegistryTree(HKEY__ *,ushort const *)
0x18001fe5b  mov     ebx, eax
0x18001fe5d  test    eax, eax
0x18001fe5f  jz      short loc_18001FEA4
0x18001fe61  cmp     eax, 80070002h
0x18001fe66  jz      short loc_18001FEA4
0x18001fe68  lea     rdx, [rsp+68h+var_38]
0x18001fe6d  cmp     [rsp+68h+var_20], 8
0x18001fe73  cmovnb  rdx, [rsp+68h+var_38]
0x18001fe79  mov     rcx, [rsp+68h]; this
0x18001fe7e  mov     [rsp+68h+var_40], rdx; char *
0x18001fe83  lea     rax, aSubkeyLs; "Subkey %ls"
0x18001fe8a  mov     [rsp+68h+var_48], rax; __int64
0x18001fe8f  mov     r9d, ebx; char *
0x18001fe92  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001fe99  mov     edx, 219h; void *
0x18001fe9e  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001fea3  nop
0x18001fea4  xor     r8d, r8d
0x18001fea7  mov     dl, 1
0x18001fea9  lea     rcx, [rsp+68h+var_38]
0x18001feae  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001feb3  mov     eax, ebx
0x18001feb5  mov     rcx, [rsp+68h+var_18]
0x18001feba  xor     rcx, rsp; StackCookie
0x18001febd  call    __security_check_cookie
0x18001fec2  add     rsp, 60h
0x18001fec6  pop     rbx
0x18001fec7  retn
```
