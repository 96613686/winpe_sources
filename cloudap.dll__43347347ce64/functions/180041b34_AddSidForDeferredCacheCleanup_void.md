# _AddSidForDeferredCacheCleanup(void *)

- ea: `0x180041b34`
- end: `0x180041d4f`
- name: `?_AddSidForDeferredCacheCleanup@@YAJPEAX@Z`
- size: `539`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180041820`

## callees

- `0x18003a5cc`
- `0x18003bf28`
- `0x18003c73c`
- `0x18003dd9c`
- `0x180040024`
- `0x180041b34`
- `0x180042410`
- `0x180046efc`
- `0x180047350`
- `0x180047474`
- `0x18004755c`
- `0x18004af14`
- `0x18004bfe4`
- `0x18004c034`
- `0x18005c97c`
- `0x18005e458`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180041b63`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180041b63`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041bd2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180041bd2`

## string_xrefs

- `0x180041b71`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180041be3`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180041c56`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180041cda`: `onecore\ds\ext\cloudap\dll\cloudap.cpp`
- `0x180041bc4`: `Software\Microsoft\IdentityStore\DeferredCacheCleanup`

## pseudocode

```c
__int64 __fastcall _AddSidForDeferredCacheCleanup(void *a1)
{
  const char *v1; // r9
  unsigned int LastError; // ebx
  unsigned int v3; // eax
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  int MultiStringRegValAsVector; // eax
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-59h]
  HKEY phkResult; // [rsp+50h] [rbp-29h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-21h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-19h] BYREF
  int v19; // [rsp+68h] [rbp-11h] BYREF
  __int64 v20; // [rsp+70h] [rbp-9h] BYREF
  __int64 v21; // [rsp+78h] [rbp-1h]
  _BYTE v22[8]; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+90h] [rbp+17h]
  _BYTE v24[32]; // [rsp+A0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) )
  {
    phkResult = 0;
    dwDisposition = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v3 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\IdentityStore\\DeferredCacheCleanup",
           0,
           0,
           0,
           3u,
           0,
           &phkResult,
           &dwDisposition);
    if ( v3 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x6B7,
                    (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp",
                    (const char *)v3,
                    dwOptions);
LABEL_5:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      goto LABEL_19;
    }
    v4 = -1;
    do
      ++v4;
    while ( StringSid[v4] );
    std::wstring::wstring(v24, StringSid, &StringSid[v4]);
    v19 = 0;
    std::vector<std::wstring>::vector<std::wstring>(&v20);
    MultiStringRegValAsVector = GetMultiStringRegValAsVector(v6, v5, &v19, &v20);
    LastError = MultiStringRegValAsVector;
    if ( !MultiStringRegValAsVector || MultiStringRegValAsVector == -2147024894 )
    {
      v10 = std::_Find_unchecked<std::wstring *,std::wstring>(v20, v21, v24);
      if ( v21 == v10 )
      {
        std::vector<std::wstring>::vector<std::wstring>(v22);
        std::vector<std::wstring>::emplace<std::wstring const &>(v22, &v19, v23, v24);
        v13 = SetMultiStringRegValWithVector(v12, v11, v22);
        LastError = v13;
        if ( v13 >= 0 )
        {
          std::vector<std::wstring>::_Tidy(v22);
          std::vector<std::wstring>::_Tidy(&v20);
          std::wstring::_Tidy_deallocate(v24);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
          LastError = 0;
          goto LABEL_19;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6C9,
          (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp",
          (const char *)(unsigned int)v13,
          dwOptions);
        std::vector<std::wstring>::_Tidy(v22);
        goto LABEL_13;
      }
      LastError = -2147024713;
      v8 = 2147942583LL;
      v9 = 1732;
    }
    else
    {
      if ( MultiStringRegValAsVector >= 0 )
      {
LABEL_13:
        std::vector<std::wstring>::_Tidy(&v20);
        std::wstring::_Tidy_deallocate(v24);
        goto LABEL_5;
      }
      v8 = (unsigned int)MultiStringRegValAsVector;
      v9 = 1729;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp",
      (const char *)v8,
      dwOptions);
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x6AB,
                (unsigned int)"onecore\\ds\\ext\\cloudap\\dll\\cloudap.cpp",
                v1);
LABEL_19:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  return LastError;
}

```

## disassembly

```asm
0x180041b34  mov     [rsp-8+arg_8], rbx
0x180041b39  mov     [rsp-8+arg_10], rdi
0x180041b3e  push    rbp
0x180041b3f  lea     rbp, [rsp-57h]
0x180041b44  sub     rsp, 0D0h
0x180041b4b  mov     rax, cs:__security_cookie
0x180041b52  xor     rax, rsp
0x180041b55  mov     [rbp+57h+var_10], rax
0x180041b59  xor     edi, edi
0x180041b5b  mov     [rbp+57h+StringSid], rdi
0x180041b5f  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180041b63  call    cs:__imp_ConvertSidToStringSidW
0x180041b69  test    eax, eax
0x180041b6b  jnz     short loc_180041B89
0x180041b6d  mov     rcx, [rbp+5Fh]; this
0x180041b71  lea     r8, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180041b78  mov     edx, 6ABh; void *
0x180041b7d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180041b82  mov     ebx, eax
0x180041b84  jmp     loc_180041D23
0x180041b89  mov     [rbp+57h+var_80], rdi
0x180041b8d  mov     [rbp+57h+dwDisposition], edi
0x180041b90  xor     edx, edx
0x180041b92  lea     rcx, [rbp+57h+var_80]
0x180041b96  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180041b9b  lea     rax, [rbp+57h+dwDisposition]
0x180041b9f  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180041ba4  lea     rax, [rbp+57h+var_80]
0x180041ba8  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180041bad  mov     [rsp+0D0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180041bb2  mov     [rsp+0D0h+samDesired], 3; samDesired
0x180041bba  mov     [rsp+0D0h+dwOptions], edi; int
0x180041bbe  xor     r9d, r9d; lpClass
0x180041bc1  xor     r8d, r8d; Reserved
0x180041bc4  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\IdentityStore\\Def"...
0x180041bcb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041bd2  call    cs:__imp_RegCreateKeyExW
0x180041bd8  test    eax, eax
0x180041bda  jz      short loc_180041C04
0x180041bdc  mov     rcx, [rbp+5Fh]; this
0x180041be0  mov     r9d, eax; char *
0x180041be3  lea     r8, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180041bea  mov     edx, 6B7h; void *
0x180041bef  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180041bf4  mov     ebx, eax
0x180041bf6  lea     rcx, [rbp+57h+var_80]
0x180041bfa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041bff  jmp     loc_180041D23
0x180041c04  mov     rdx, [rbp+57h+StringSid]
0x180041c08  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041c0c  inc     rax
0x180041c0f  cmp     [rdx+rax*2], di
0x180041c13  jnz     short loc_180041C0C
0x180041c15  lea     r8, [rdx+rax*2]
0x180041c19  lea     rcx, [rbp+57h+var_30]
0x180041c1d  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x180041c22  nop
0x180041c23  mov     [rbp+57h+var_68], edi
0x180041c26  lea     rcx, [rbp+57h+var_60]
0x180041c2a  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x180041c2f  nop
0x180041c30  lea     r9, [rbp+57h+var_60]
0x180041c34  lea     r8, [rbp+57h+var_68]
0x180041c38  call    ?GetMultiStringRegValAsVector@@YAJPEBG0PEAKPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; GetMultiStringRegValAsVector(ushort const *,ushort const *,ulong *,std::vector<std::wstring> *)
0x180041c3d  mov     ebx, eax
0x180041c3f  test    eax, eax
0x180041c41  jz      short loc_180041C7F
0x180041c43  cmp     eax, 80070002h
0x180041c48  jz      short loc_180041C7F
0x180041c4a  test    eax, eax
0x180041c4c  jns     short loc_180041C67
0x180041c4e  mov     r9d, eax; char *
0x180041c51  mov     edx, 6C1h; void *
0x180041c56  lea     r8, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180041c5d  mov     rcx, [rbp+5Fh]; this
0x180041c61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041c66  nop
0x180041c67  lea     rcx, [rbp+57h+var_60]
0x180041c6b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180041c70  nop
0x180041c71  lea     rcx, [rbp+57h+var_30]
0x180041c75  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041c7a  jmp     loc_180041BF6
0x180041c7f  lea     r8, [rbp+57h+var_30]
0x180041c83  mov     rdx, [rbp+57h+var_58]
0x180041c87  mov     rcx, [rbp+57h+var_60]
0x180041c8b  call    ??$_Find_unchecked@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEAV10@QEAV10@AEBV10@@Z; std::_Find_unchecked<std::wstring *,std::wstring>(std::wstring *,std::wstring * const,std::wstring const &)
0x180041c90  cmp     [rbp+57h+var_58], rax
0x180041c94  jz      short loc_180041CA5
0x180041c96  mov     ebx, 800700B7h
0x180041c9b  mov     r9d, ebx
0x180041c9e  mov     edx, 6C4h
0x180041ca3  jmp     short loc_180041C56
0x180041ca5  lea     rcx, [rbp+57h+var_48]
0x180041ca9  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x180041cae  nop
0x180041caf  lea     r9, [rbp+57h+var_30]
0x180041cb3  mov     r8, [rbp+57h+var_40]
0x180041cb7  lea     rdx, [rbp+57h+var_68]
0x180041cbb  lea     rcx, [rbp+57h+var_48]
0x180041cbf  call    ??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::vector<std::wstring>::emplace<std::wstring const &>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring const &)
0x180041cc4  lea     r8, [rbp+57h+var_48]
0x180041cc8  call    ?SetMultiStringRegValWithVector@@YAJPEBG0AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; SetMultiStringRegValWithVector(ushort const *,ushort const *,std::vector<std::wstring> const &)
0x180041ccd  mov     ebx, eax
0x180041ccf  test    eax, eax
0x180041cd1  jns     short loc_180041CFA
0x180041cd3  mov     rcx, [rbp+5Fh]; this
0x180041cd7  mov     r9d, eax; char *
0x180041cda  lea     r8, aOnecoreDsExtCl_16; "onecore\\ds\\ext\\cloudap\\dll\\cloudap"...
0x180041ce1  mov     edx, 6C9h; void *
0x180041ce6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041ceb  nop
0x180041cec  lea     rcx, [rbp+57h+var_48]
0x180041cf0  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180041cf5  jmp     loc_180041C67
0x180041cfa  lea     rcx, [rbp+57h+var_48]
0x180041cfe  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180041d03  nop
0x180041d04  lea     rcx, [rbp+57h+var_60]
0x180041d08  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180041d0d  nop
0x180041d0e  lea     rcx, [rbp+57h+var_30]
0x180041d12  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041d17  nop
0x180041d18  lea     rcx, [rbp+57h+var_80]
0x180041d1c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041d21  mov     ebx, edi
0x180041d23  lea     rcx, [rbp+57h+StringSid]
0x180041d27  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180041d2c  mov     eax, ebx
0x180041d2e  mov     rcx, [rbp+57h+var_10]
0x180041d32  xor     rcx, rsp; StackCookie
0x180041d35  call    __security_check_cookie
0x180041d3a  lea     r11, [rsp+0D0h+var_s0]
0x180041d42  mov     rbx, [r11+18h]
0x180041d46  mov     rdi, [r11+20h]
0x180041d4a  mov     rsp, r11
0x180041d4d  pop     rbp
0x180041d4e  retn
```
