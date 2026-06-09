# LpacRegHelper::OpenLpacRegistrySubKey(void *,ushort const *,ushort const *,ushort const *,HKEY__ * *)

- ea: `0x180020f70`
- end: `0x1800210c9`
- name: `?OpenLpacRegistrySubKey@LpacRegHelper@@CAJPEAXPEBG11PEAPEAUHKEY__@@@Z`
- size: `345`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, HKEY *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020898`
- `0x180020ab0`

## callees

- `0x180004594`
- `0x18000a740`
- `0x180020488`
- `0x180020f70`
- `0x180021564`
- `0x180021688`
- `0x180021f10`
- `0x180022830`

## string_xrefs

- `0x180020fac`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x180020ffc`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18002106e`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LpacRegHelper::OpenLpacRegistrySubKey(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        HKEY *a5)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  const WCHAR *v11; // rdx
  LSTATUS v12; // eax
  HKEY v13; // rax
  HKEY v15; // [rsp+20h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+28h] [rbp-28h] BYREF
  unsigned __int64 v17; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  if ( !a2 )
  {
    v6 = 253;
LABEL_3:
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)0x80070057LL,
      (int)v15);
    return v7;
  }
  if ( !a3 )
  {
    v6 = 254;
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v6 = 255;
    goto LABEL_3;
  }
  v17 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  v8 = LpacRegHelper::DeriveLpacTopRegistryKey(a1, a2, a3, lpSubKey);
  v7 = v8;
  if ( v8 >= 0 )
  {
    if ( a4 )
    {
      if ( *a4 )
      {
        v10 = -1;
        do
          ++v10;
        while ( a4[v10] );
      }
      else
      {
        v10 = 0;
      }
      std::wstring::append(lpSubKey, a4, v10);
    }
    v15 = 0;
    v11 = (const WCHAR *)lpSubKey;
    if ( v17 >= 8 )
      v11 = lpSubKey[0];
    v12 = wil::reg::open_unique_key_nothrow(HKEY_USERS, v11, (__int64)&v15, 0);
    v7 = v12;
    if ( v12 >= 0 )
    {
      v13 = v15;
      v15 = 0;
      *a5 = v13;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
      v7 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x113,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
        (const char *)(unsigned int)v12,
        (int)v15);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)(unsigned int)v8,
      (int)v15);
  }
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(lpSubKey, v9, 0);
  return v7;
}

```

## disassembly

```asm
0x180020f70  push    rbp
0x180020f72  push    rbx
0x180020f73  push    rsi
0x180020f74  push    rdi
0x180020f75  push    r14
0x180020f77  mov     rbp, rsp
0x180020f7a  sub     rsp, 50h
0x180020f7e  mov     rax, cs:__security_cookie
0x180020f85  xor     rax, rsp
0x180020f88  mov     [rbp+var_8], rax
0x180020f8c  mov     rdi, r9
0x180020f8f  mov     rsi, [rbp+arg_20]
0x180020f93  xor     r14d, r14d
0x180020f96  test    rdx, rdx
0x180020f99  jnz     short loc_180020FBD
0x180020f9b  mov     edx, 0FDh; void *
0x180020fa0  mov     ebx, 80070057h
0x180020fa5  mov     rcx, [rbp+28h]; this
0x180020fa9  mov     r9d, ebx; char *
0x180020fac  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180020fb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020fb8  jmp     loc_1800210AF
0x180020fbd  test    r8, r8
0x180020fc0  jnz     short loc_180020FC9
0x180020fc2  mov     edx, 0FEh
0x180020fc7  jmp     short loc_180020FA0
0x180020fc9  test    rsi, rsi
0x180020fcc  jnz     short loc_180020FD5
0x180020fce  mov     edx, 0FFh
0x180020fd3  jmp     short loc_180020FA0
0x180020fd5  mov     [rbp+var_10], 7
0x180020fdd  mov     [rbp+var_18], r14
0x180020fe1  mov     word ptr [rbp+lpSubKey], r14w
0x180020fe6  lea     r9, [rbp+lpSubKey]
0x180020fea  call    ?DeriveLpacTopRegistryKey@LpacRegHelper@@CAJPEAXPEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LpacRegHelper::DeriveLpacTopRegistryKey(void *,ushort const *,ushort const *,std::wstring &)
0x180020fef  mov     ebx, eax
0x180020ff1  test    eax, eax
0x180020ff3  jns     short loc_180021012
0x180020ff5  mov     rcx, [rbp+28h]; this
0x180020ff9  mov     r9d, eax; char *
0x180020ffc  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180021003  mov     edx, 106h; void *
0x180021008  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002100d  jmp     loc_1800210A1
0x180021012  test    rdi, rdi
0x180021015  jz      short loc_18002103C
0x180021017  cmp     [rdi], r14w
0x18002101b  jnz     short loc_180021022
0x18002101d  mov     r8, r14
0x180021020  jmp     short loc_180021030
0x180021022  or      r8, 0FFFFFFFFFFFFFFFFh
0x180021026  inc     r8
0x180021029  cmp     [rdi+r8*2], r14w
0x18002102e  jnz     short loc_180021026
0x180021030  mov     rdx, rdi
0x180021033  lea     rcx, [rbp+lpSubKey]
0x180021037  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002103c  mov     [rbp+var_30], r14
0x180021040  lea     rdx, [rbp+lpSubKey]
0x180021044  cmp     [rbp+var_10], 8
0x180021049  cmovnb  rdx, [rbp+lpSubKey]; lpSubKey
0x18002104e  xor     r9d, r9d
0x180021051  lea     r8, [rbp+var_30]
0x180021055  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18002105c  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x180021061  mov     ebx, eax
0x180021063  test    eax, eax
0x180021065  jns     short loc_18002108A
0x180021067  mov     rcx, [rbp+28h]; this
0x18002106b  mov     r9d, eax; char *
0x18002106e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x180021075  mov     edx, 113h; void *
0x18002107a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002107f  lea     rcx, [rbp+var_30]
0x180021083  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180021088  jmp     short loc_1800210A1
0x18002108a  mov     rax, [rbp+var_30]
0x18002108e  mov     [rbp+var_30], r14
0x180021092  mov     [rsi], rax
0x180021095  lea     rcx, [rbp+var_30]
0x180021099  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002109e  mov     ebx, r14d
0x1800210a1  xor     r8d, r8d
0x1800210a4  mov     dl, 1
0x1800210a6  lea     rcx, [rbp+lpSubKey]
0x1800210aa  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800210af  mov     eax, ebx
0x1800210b1  mov     rcx, [rbp+var_8]
0x1800210b5  xor     rcx, rsp; StackCookie
0x1800210b8  call    __security_check_cookie
0x1800210bd  add     rsp, 50h
0x1800210c1  pop     r14
0x1800210c3  pop     rdi
0x1800210c4  pop     rsi
0x1800210c5  pop     rbx
0x1800210c6  pop     rbp
0x1800210c7  retn
```
