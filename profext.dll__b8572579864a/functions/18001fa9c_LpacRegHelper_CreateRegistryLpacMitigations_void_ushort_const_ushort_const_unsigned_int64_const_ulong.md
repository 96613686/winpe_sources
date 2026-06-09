# LpacRegHelper::CreateRegistryLpacMitigations(void *,ushort const *,ushort const *,unsigned __int64 const *,ulong)

- ea: `0x18001fa9c`
- end: `0x18001fc81`
- name: `?CreateRegistryLpacMitigations@LpacRegHelper@@CAJPEAXPEBG1PEB_KK@Z`
- size: `485`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f390`

## callees

- `0x180004594`
- `0x18000a740`
- `0x18000c7d4`
- `0x18001ef5c`
- `0x18001fa9c`
- `0x180020488`
- `0x180021564`
- `0x180021f10`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001fbd5`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001fbd5`

## string_xrefs

- `0x18001fad2`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001fb24`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001fb73`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001fc31`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LpacRegHelper::CreateRegistryLpacMitigations(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int64 *a4)
{
  __int64 v5; // rdx
  signed int v6; // ebx
  int v7; // eax
  __int64 v8; // rdx
  const WCHAR *v9; // rdx
  int v10; // eax
  __int64 v11; // rdi
  LSTATUS v12; // eax
  __int64 v13; // rdx
  __int64 v15; // rdx
  int lpData; // [rsp+20h] [rbp-50h]
  HKEY hKey; // [rsp+30h] [rbp-40h] BYREF
  LPCWSTR lpValueName; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int64 Data; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v21; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  if ( !a2 )
  {
    v5 = 121;
LABEL_3:
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)0x80070057LL,
      lpData);
    return (unsigned int)v6;
  }
  if ( !a3 )
  {
    v5 = 122;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v5 = 123;
    goto LABEL_3;
  }
  v21 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  v7 = LpacRegHelper::DeriveLpacTopRegistryKey(a1, a2, a3, lpSubKey);
  v6 = v7;
  if ( v7 >= 0 )
  {
    hKey = 0;
    v9 = (const WCHAR *)lpSubKey;
    if ( v21 >= 8 )
      v9 = lpSubKey[0];
    v10 = wil::reg::open_unique_key_nothrow(HKEY_USERS, v9);
    v6 = v10;
    if ( v10 >= 0 )
    {
      v11 = 0;
      while ( 1 )
      {
        lpValueName = 0;
        v6 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
               &lpValueName,
               L"MitigationOption%d",
               v11);
        if ( v6 < 0 )
          break;
        Data = a4[v11];
        v12 = RegSetKeyValueW(hKey, 0, lpValueName, 0xBu, &Data, 8u);
        v6 = v12;
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
        if ( v6 < 0 )
        {
          v15 = 155;
          goto LABEL_23;
        }
        wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&lpValueName);
        if ( (unsigned __int64)++v11 >= 3 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          LOBYTE(v13) = 1;
          std::wstring::_Tidy(lpSubKey, v13, 0);
          return 0;
        }
      }
      v15 = 148;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
        (const char *)(unsigned int)v6,
        lpData);
      wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&lpValueName);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
        (const char *)(unsigned int)v10,
        lpData);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)(unsigned int)v7,
      lpData);
  }
  LOBYTE(v8) = 1;
  std::wstring::_Tidy(lpSubKey, v8, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001fa9c  mov     [rsp-18h+arg_0], rbx
0x18001faa1  push    rbp
0x18001faa2  push    rsi
0x18001faa3  push    rdi
0x18001faa4  mov     rbp, rsp
0x18001faa7  sub     rsp, 70h
0x18001faab  mov     rax, cs:__security_cookie
0x18001fab2  xor     rax, rsp
0x18001fab5  mov     [rbp+var_8], rax
0x18001fab9  mov     rsi, r9
0x18001fabc  test    rdx, rdx
0x18001fabf  jnz     short loc_18001FAE3
0x18001fac1  mov     edx, 79h ; 'y'; void *
0x18001fac6  mov     ebx, 80070057h
0x18001facb  mov     rcx, [rbp+18h]; this
0x18001facf  mov     r9d, ebx; char *
0x18001fad2  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001fad9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fade  jmp     loc_18001FC62
0x18001fae3  test    r8, r8
0x18001fae6  jnz     short loc_18001FAEE
0x18001fae8  lea     edx, [r8+7Ah]
0x18001faec  jmp     short loc_18001FAC6
0x18001faee  test    rsi, rsi
0x18001faf1  jnz     short loc_18001FAF8
0x18001faf3  lea     edx, [rsi+7Bh]
0x18001faf6  jmp     short loc_18001FAC6
0x18001faf8  mov     [rbp+var_10], 7
0x18001fb00  mov     [rbp+var_18], 0
0x18001fb08  xor     eax, eax
0x18001fb0a  mov     word ptr [rbp+lpSubKey], ax
0x18001fb0e  lea     r9, [rbp+lpSubKey]
0x18001fb12  call    ?DeriveLpacTopRegistryKey@LpacRegHelper@@CAJPEAXPEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LpacRegHelper::DeriveLpacTopRegistryKey(void *,ushort const *,ushort const *,std::wstring &)
0x18001fb17  mov     ebx, eax
0x18001fb19  test    eax, eax
0x18001fb1b  jns     short loc_18001FB3A
0x18001fb1d  mov     rcx, [rbp+18h]; this
0x18001fb21  mov     r9d, eax; char *
0x18001fb24  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001fb2b  mov     edx, 82h; void *
0x18001fb30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb35  jmp     loc_18001FC54
0x18001fb3a  mov     [rbp+hKey], 0
0x18001fb42  lea     rdx, [rbp+lpSubKey]
0x18001fb46  cmp     [rbp+var_10], 8
0x18001fb4b  cmovnb  rdx, [rbp+lpSubKey]; lpSubKey
0x18001fb50  mov     r9d, 1
0x18001fb56  lea     r8, [rbp+hKey]
0x18001fb5a  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001fb61  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18001fb66  mov     ebx, eax
0x18001fb68  test    eax, eax
0x18001fb6a  jns     short loc_18001FB89
0x18001fb6c  mov     rcx, [rbp+18h]; this
0x18001fb70  mov     r9d, eax; char *
0x18001fb73  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001fb7a  mov     edx, 8Ah; void *
0x18001fb7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb84  jmp     loc_18001FC4A
0x18001fb89  xor     edi, edi
0x18001fb8b  mov     [rbp+lpValueName], 0
0x18001fb93  mov     r8, rdi
0x18001fb96  lea     rdx, aMitigationopti; "MitigationOption%d"
0x18001fb9d  lea     rcx, [rbp+lpValueName]
0x18001fba1  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18001fba6  mov     ebx, eax
0x18001fba8  test    eax, eax
0x18001fbaa  js      short loc_18001FC29
0x18001fbac  mov     rax, [rsi+rdi*8]
0x18001fbb0  mov     [rbp+Data], rax
0x18001fbb4  mov     [rsp+70h+cbData], 8; cbData
0x18001fbbc  lea     rax, [rbp+Data]
0x18001fbc0  mov     [rsp+70h+lpData], rax; lpData
0x18001fbc5  mov     r9d, 0Bh; dwType
0x18001fbcb  mov     r8, [rbp+lpValueName]; lpValueName
0x18001fbcf  xor     edx, edx; lpSubKey
0x18001fbd1  mov     rcx, [rbp+hKey]; hKey
0x18001fbd5  call    cs:__imp_RegSetKeyValueW
0x18001fbdc  nop     dword ptr [rax+rax+00h]
0x18001fbe1  mov     ebx, eax
0x18001fbe3  test    eax, eax
0x18001fbe5  jle     short loc_18001FBF0
0x18001fbe7  movzx   ebx, ax
0x18001fbea  or      ebx, 80070000h
0x18001fbf0  test    ebx, ebx
0x18001fbf2  js      short loc_18001FC22
0x18001fbf4  lea     rcx, [rbp+lpValueName]
0x18001fbf8  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001fbfd  inc     rdi
0x18001fc00  cmp     rdi, 3
0x18001fc04  jb      short loc_18001FB8B
0x18001fc06  lea     rcx, [rbp+hKey]
0x18001fc0a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001fc0f  nop
0x18001fc10  xor     r8d, r8d
0x18001fc13  mov     dl, 1
0x18001fc15  lea     rcx, [rbp+lpSubKey]
0x18001fc19  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001fc1e  xor     eax, eax
0x18001fc20  jmp     short loc_18001FC64
0x18001fc22  mov     edx, 9Bh
0x18001fc27  jmp     short loc_18001FC2E
0x18001fc29  mov     edx, 94h; void *
0x18001fc2e  mov     r9d, ebx; char *
0x18001fc31  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001fc38  mov     rcx, [rbp+18h]; this
0x18001fc3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fc41  lea     rcx, [rbp+lpValueName]
0x18001fc45  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001fc4a  lea     rcx, [rbp+hKey]
0x18001fc4e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001fc53  nop
0x18001fc54  xor     r8d, r8d
0x18001fc57  mov     dl, 1
0x18001fc59  lea     rcx, [rbp+lpSubKey]
0x18001fc5d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001fc62  mov     eax, ebx
0x18001fc64  mov     rcx, [rbp+var_8]
0x18001fc68  xor     rcx, rsp; StackCookie
0x18001fc6b  call    __security_check_cookie
0x18001fc70  mov     rbx, [rsp+70h+arg_0]
0x18001fc78  add     rsp, 70h
0x18001fc7c  pop     rdi
0x18001fc7d  pop     rsi
0x18001fc7e  pop     rbp
0x18001fc7f  retn
```
