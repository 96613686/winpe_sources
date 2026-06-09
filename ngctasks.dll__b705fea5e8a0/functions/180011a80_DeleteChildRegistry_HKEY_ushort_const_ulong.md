# DeleteChildRegistry(HKEY__ *,ushort const *,ulong)

- ea: `0x180011a80`
- end: `0x180011dec`
- name: `?DeleteChildRegistry@@YAJPEAUHKEY__@@PEBGK@Z`
- size: `876`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, char)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014490`

## callees

- `0x180008c74`
- `0x18000cc34`
- `0x18000ebc0`
- `0x18000ef9c`
- `0x18000ff9c`
- `0x180010310`
- `0x180011a80`
- `0x180014bcc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180011cf6`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180011cf6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180011d1b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180011d1b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180011c58`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180011c58`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180011c2d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180011c2d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180011b60`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180011b60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011ad1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011ad1`

## string_xrefs

- `0x180011af2`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180011b7d`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180011c75`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180011c9d`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180011d38`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180011d5d`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180011da9`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
__int64 __fastcall DeleteChildRegistry(HKEY hKey, LPCWSTR lpSubKey, char a3)
{
  int v6; // eax
  bool v7; // sf
  signed int v8; // edi
  LSTATUS v9; // eax
  const char *v10; // r9
  DWORD v11; // eax
  DWORD v12; // esi
  WCHAR *v13; // rbx
  DWORD v14; // eax
  void **v15; // rdi
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  LSTATUS v19; // eax
  int phkResult; // [rsp+20h] [rbp-39h]
  int phkResulta; // [rsp+20h] [rbp-39h]
  int phkResultb; // [rsp+20h] [rbp-39h]
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp+7h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp+Bh] BYREF
  DWORD cValues; // [rsp+68h] [rbp+Fh] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+6Ch] [rbp+13h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp+17h] BYREF
  HKEY hKeya; // [rsp+78h] [rbp+1Fh] BYREF
  void *v30[2]; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  void *cchName; // [rsp+D8h] [rbp+7Fh] BYREF

  hKeya = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKeya,
    0);
  v6 = RegOpenKeyExW(hKey, lpSubKey, 0, 0xF003Fu, &hKeya);
  v7 = v6 < 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    v7 = v6 < 0;
  }
  if ( v7 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x11A,
      (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)v6);
    v8 = 0;
LABEL_39:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
    return (unsigned int)v8;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  v9 = RegQueryInfoKeyW(hKeya, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  v8 = v9;
  if ( v9 > 0 )
    v8 = (unsigned __int16)v9 | 0x80070000;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)v8,
      phkResult);
    goto LABEL_39;
  }
  v11 = cbMaxSubKeyLen;
  if ( cbMaxSubKeyLen < cbMaxValueNameLen )
    v11 = cbMaxValueNameLen;
  v12 = v11 + 1;
  v13 = 0;
  v30[0] = 0;
  v14 = cSubKeys;
  if ( cSubKeys || cValues )
  {
    v15 = (void **)wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                     &cchName,
                     0,
                     v12,
                     v10);
    if ( v30 != v15 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v30,
        *v15);
      *v15 = 0;
      v13 = (WCHAR *)v30[0];
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&cchName);
    if ( !v13 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13B,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)0x8007000ELL,
        phkResult);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v30);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
      return 2147942414LL;
    }
    v14 = cSubKeys;
  }
  if ( (a3 & 2) != 0 && v14 )
  {
    while ( 1 )
    {
      LODWORD(cchName) = v12;
      v16 = RegEnumKeyExW(hKeya, 0, v13, (LPDWORD)&cchName, 0, 0, 0, 0);
      v8 = v16;
      if ( v16 > 0 )
        v8 = (unsigned __int16)v16 | 0x80070000;
      if ( v8 == -2147024637 )
        break;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x153,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v8,
          phkResulta);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v30);
        goto LABEL_39;
      }
      v17 = RegDeleteKeyExW(hKeya, v13, 0, 0);
      v8 = v17;
      if ( v17 > 0 )
        v8 = (unsigned __int16)v17 | 0x80070000;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x159,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v8,
          phkResulta);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v30);
        goto LABEL_39;
      }
    }
  }
  if ( (a3 & 1) != 0 && cValues )
  {
    while ( 1 )
    {
      cchValueName = v12;
      v18 = RegEnumValueW(hKeya, 0, v13, &cchValueName, 0, 0, 0, 0);
      v8 = v18;
      if ( v18 > 0 )
        v8 = (unsigned __int16)v18 | 0x80070000;
      if ( v8 == -2147024637 )
        break;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x172,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v8,
          phkResultb);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v30);
        goto LABEL_39;
      }
      v19 = RegDeleteValueW(hKeya, v13);
      v8 = v19;
      if ( v19 > 0 )
        v8 = (unsigned __int16)v19 | 0x80070000;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x176,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v8,
          phkResultb);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v30);
        goto LABEL_39;
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v30);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
  return 0;
}

```

## disassembly

```asm
0x180011a80  mov     [rsp-8+arg_0], rbx
0x180011a85  mov     [rsp-8+arg_8], rsi
0x180011a8a  push    rbp
0x180011a8b  push    rdi
0x180011a8c  push    r12
0x180011a8e  push    r14
0x180011a90  push    r15
0x180011a92  lea     rbp, [rsp-37h]
0x180011a97  sub     rsp, 90h
0x180011a9e  mov     r14d, r8d
0x180011aa1  mov     rbx, rdx
0x180011aa4  mov     rdi, rcx
0x180011aa7  xor     r15d, r15d
0x180011aaa  mov     [rbp+57h+hKey], r15
0x180011aae  xor     edx, edx
0x180011ab0  lea     rcx, [rbp+57h+hKey]
0x180011ab4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180011ab9  lea     rax, [rbp+57h+hKey]
0x180011abd  mov     [rsp+0B0h+phkResult], rax; int
0x180011ac2  mov     r9d, 0F003Fh; samDesired
0x180011ac8  xor     r8d, r8d; ulOptions
0x180011acb  mov     rdx, rbx; lpSubKey
0x180011ace  mov     rcx, rdi; hKey
0x180011ad1  call    cs:__imp_RegOpenKeyExW
0x180011ad7  mov     r12d, 80070000h
0x180011add  test    eax, eax
0x180011adf  jle     short loc_180011AE9
0x180011ae1  movzx   eax, ax
0x180011ae4  or      eax, r12d
0x180011ae7  test    eax, eax
0x180011ae9  jns     short loc_180011B0C
0x180011aeb  mov     rcx, [rbp+5Fh]; this
0x180011aef  mov     r9d, eax; char *
0x180011af2  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180011af9  mov     edx, 11Ah; void *
0x180011afe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011b03  nop
0x180011b04  mov     edi, r15d
0x180011b07  jmp     loc_180011D79
0x180011b0c  mov     [rbp+57h+cSubKeys], r15d
0x180011b10  mov     [rbp+57h+cbMaxSubKeyLen], r15d
0x180011b14  mov     [rbp+57h+cValues], r15d
0x180011b18  mov     [rbp+57h+cbMaxValueNameLen], r15d
0x180011b1c  mov     [rsp+0B0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180011b21  mov     [rsp+0B0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180011b26  mov     [rsp+0B0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180011b2b  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x180011b2f  mov     [rsp+0B0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180011b34  lea     rax, [rbp+57h+cValues]
0x180011b38  mov     [rsp+0B0h+lpcValues], rax; lpcValues
0x180011b3d  mov     [rsp+0B0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180011b42  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180011b46  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180011b4b  lea     rax, [rbp+57h+cSubKeys]
0x180011b4f  mov     [rsp+0B0h+phkResult], rax; int
0x180011b54  xor     r9d, r9d; lpReserved
0x180011b57  xor     r8d, r8d; lpcchClass
0x180011b5a  xor     edx, edx; lpClass
0x180011b5c  mov     rcx, [rbp+57h+hKey]; hKey
0x180011b60  call    cs:__imp_RegQueryInfoKeyW
0x180011b66  mov     edi, eax
0x180011b68  test    eax, eax
0x180011b6a  jle     short loc_180011B72
0x180011b6c  movzx   edi, ax
0x180011b6f  or      edi, r12d
0x180011b72  test    edi, edi
0x180011b74  jns     short loc_180011B94
0x180011b76  mov     rcx, [rbp+5Fh]; this
0x180011b7a  mov     r9d, edi; char *
0x180011b7d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180011b84  mov     edx, 130h; void *
0x180011b89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011b8e  nop
0x180011b8f  jmp     loc_180011D79
0x180011b94  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180011b97  cmp     eax, [rbp+57h+cbMaxValueNameLen]
0x180011b9a  cmovb   eax, [rbp+57h+cbMaxValueNameLen]
0x180011b9e  lea     esi, [rax+1]
0x180011ba1  mov     rbx, r15
0x180011ba4  mov     [rbp+57h+var_30], rbx
0x180011ba8  mov     eax, [rbp+57h+cSubKeys]
0x180011bab  test    eax, eax
0x180011bad  jnz     short loc_180011BB5
0x180011baf  cmp     [rbp+57h+cValues], r15d
0x180011bb3  jbe     short loc_180011BF7
0x180011bb5  mov     r8d, esi
0x180011bb8  xor     edx, edx
0x180011bba  lea     rcx, [rbp+57h+cchName]
0x180011bbe  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180011bc3  mov     rdi, rax
0x180011bc6  lea     rax, [rbp+57h+var_30]
0x180011bca  cmp     rax, rdi
0x180011bcd  jz      short loc_180011BE2
0x180011bcf  mov     rdx, [rdi]
0x180011bd2  lea     rcx, [rbp+57h+var_30]
0x180011bd6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180011bdb  mov     [rdi], r15
0x180011bde  mov     rbx, [rbp+57h+var_30]
0x180011be2  lea     rcx, [rbp+57h+cchName]
0x180011be6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180011beb  test    rbx, rbx
0x180011bee  jz      loc_180011D9D
0x180011bf4  mov     eax, [rbp+57h+cSubKeys]
0x180011bf7  test    r14b, 2
0x180011bfb  jz      loc_180011CBE
0x180011c01  test    eax, eax
0x180011c03  jz      loc_180011CBE
0x180011c09  mov     dword ptr [rbp+57h+cchName], esi
0x180011c0c  mov     [rsp+0B0h+lpcValues], r15; lpftLastWriteTime
0x180011c11  mov     [rsp+0B0h+lpcbMaxClassLen], r15; lpcchClass
0x180011c16  mov     [rsp+0B0h+lpcbMaxSubKeyLen], r15; lpClass
0x180011c1b  mov     [rsp+0B0h+phkResult], r15; int
0x180011c20  lea     r9, [rbp+57h+cchName]; lpcchName
0x180011c24  mov     r8, rbx; lpName
0x180011c27  xor     edx, edx; dwIndex
0x180011c29  mov     rcx, [rbp+57h+hKey]; hKey
0x180011c2d  call    cs:__imp_RegEnumKeyExW
0x180011c33  mov     edi, eax
0x180011c35  test    eax, eax
0x180011c37  jle     short loc_180011C3F
0x180011c39  movzx   edi, ax
0x180011c3c  or      edi, r12d
0x180011c3f  cmp     edi, 80070103h
0x180011c45  jz      short loc_180011CBE
0x180011c47  test    edi, edi
0x180011c49  js      short loc_180011C96
0x180011c4b  xor     r9d, r9d; Reserved
0x180011c4e  xor     r8d, r8d; samDesired
0x180011c51  mov     rdx, rbx; lpSubKey
0x180011c54  mov     rcx, [rbp+57h+hKey]; hKey
0x180011c58  call    cs:__imp_RegDeleteKeyExW
0x180011c5e  mov     edi, eax
0x180011c60  test    eax, eax
0x180011c62  jle     short loc_180011C6A
0x180011c64  movzx   edi, ax
0x180011c67  or      edi, r12d
0x180011c6a  test    edi, edi
0x180011c6c  jns     short loc_180011C09
0x180011c6e  mov     rcx, [rbp+5Fh]; this
0x180011c72  mov     r9d, edi; char *
0x180011c75  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180011c7c  mov     edx, 159h; void *
0x180011c81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c86  nop
0x180011c87  lea     rcx, [rbp+57h+var_30]
0x180011c8b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180011c90  nop
0x180011c91  jmp     loc_180011D79
0x180011c96  mov     rcx, [rbp+5Fh]; this
0x180011c9a  mov     r9d, edi; char *
0x180011c9d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180011ca4  mov     edx, 153h; void *
0x180011ca9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011cae  nop
0x180011caf  lea     rcx, [rbp+57h+var_30]
0x180011cb3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180011cb8  nop
0x180011cb9  jmp     loc_180011D79
0x180011cbe  test    r14b, 1
0x180011cc2  jz      loc_180011D86
0x180011cc8  cmp     [rbp+57h+cValues], r15d
0x180011ccc  jbe     loc_180011D86
0x180011cd2  mov     [rbp+57h+cchValueName], esi
0x180011cd5  mov     [rsp+0B0h+lpcValues], r15; lpcbData
0x180011cda  mov     [rsp+0B0h+lpcbMaxClassLen], r15; lpData
0x180011cdf  mov     [rsp+0B0h+lpcbMaxSubKeyLen], r15; lpType
0x180011ce4  mov     [rsp+0B0h+phkResult], r15; int
0x180011ce9  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180011ced  mov     r8, rbx; lpValueName
0x180011cf0  xor     edx, edx; dwIndex
0x180011cf2  mov     rcx, [rbp+57h+hKey]; hKey
0x180011cf6  call    cs:__imp_RegEnumValueW
0x180011cfc  mov     edi, eax
0x180011cfe  test    eax, eax
0x180011d00  jle     short loc_180011D08
0x180011d02  movzx   edi, ax
0x180011d05  or      edi, r12d
0x180011d08  cmp     edi, 80070103h
0x180011d0e  jz      short loc_180011D86
0x180011d10  test    edi, edi
0x180011d12  js      short loc_180011D56
0x180011d14  mov     rdx, rbx; lpValueName
0x180011d17  mov     rcx, [rbp+57h+hKey]; hKey
0x180011d1b  call    cs:__imp_RegDeleteValueW
0x180011d21  mov     edi, eax
0x180011d23  test    eax, eax
0x180011d25  jle     short loc_180011D2D
0x180011d27  movzx   edi, ax
0x180011d2a  or      edi, r12d
0x180011d2d  test    edi, edi
0x180011d2f  jns     short loc_180011CD2
0x180011d31  mov     rcx, [rbp+5Fh]; this
0x180011d35  mov     r9d, edi; char *
0x180011d38  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180011d3f  mov     edx, 176h; void *
0x180011d44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011d49  nop
0x180011d4a  lea     rcx, [rbp+57h+var_30]
0x180011d4e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180011d53  nop
0x180011d54  jmp     short loc_180011D79
0x180011d56  mov     rcx, [rbp+5Fh]; this
0x180011d5a  mov     r9d, edi; char *
0x180011d5d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180011d64  mov     edx, 172h; void *
0x180011d69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011d6e  nop
0x180011d6f  lea     rcx, [rbp+57h+var_30]
0x180011d73  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180011d78  nop
0x180011d79  lea     rcx, [rbp+57h+hKey]
0x180011d7d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180011d82  mov     eax, edi
0x180011d84  jmp     short loc_180011DD0
0x180011d86  lea     rcx, [rbp+57h+var_30]
0x180011d8a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180011d8f  nop
0x180011d90  lea     rcx, [rbp+57h+hKey]
0x180011d94  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180011d99  xor     eax, eax
0x180011d9b  jmp     short loc_180011DD0
0x180011d9d  mov     rcx, [rbp+5Fh]; this
0x180011da1  mov     ebx, 8007000Eh
0x180011da6  mov     r9d, ebx; char *
0x180011da9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180011db0  mov     edx, 13Bh; void *
0x180011db5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011dba  nop
0x180011dbb  lea     rcx, [rbp+57h+var_30]
0x180011dbf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180011dc4  nop
0x180011dc5  lea     rcx, [rbp+57h+hKey]
0x180011dc9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180011dce  mov     eax, ebx
0x180011dd0  lea     r11, [rsp+0B0h+var_20]
0x180011dd8  mov     rbx, [r11+30h]
0x180011ddc  mov     rsi, [r11+38h]
0x180011de0  mov     rsp, r11
0x180011de3  pop     r15
0x180011de5  pop     r14
0x180011de7  pop     r12
0x180011de9  pop     rdi
0x180011dea  pop     rbp
0x180011deb  retn
```
