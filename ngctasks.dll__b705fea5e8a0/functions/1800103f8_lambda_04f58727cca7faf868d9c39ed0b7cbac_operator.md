# _lambda_04f58727cca7faf868d9c39ed0b7cbac_::operator()

- ea: `0x1800103f8`
- end: `0x180010652`
- name: `_lambda_04f58727cca7faf868d9c39ed0b7cbac_::operator()`
- size: `602`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011df4`

## callees

- `0x180008c74`
- `0x18000cc34`
- `0x18000ebc0`
- `0x18000ef9c`
- `0x18000ff9c`
- `0x180010310`
- `0x1800103f8`
- `0x180011df4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180010511`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180010511`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180010598`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180010598`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800104cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800104cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010443`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010443`

## string_xrefs

- `0x180010466`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x1800104ea`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x18001052c`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x1800105d2`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180010613`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall lambda_04f58727cca7faf868d9c39ed0b7cbac_::operator()(__int64 a1)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  const char *v5; // r9
  int v6; // eax
  WCHAR *v7; // r8
  DWORD i; // edi
  LSTATUS v9; // eax
  int phkResult; // [rsp+20h] [rbp-60h]
  int phkResulta; // [rsp+20h] [rbp-60h]
  int phkResultb; // [rsp+20h] [rbp-60h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-20h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-1Ch] BYREF
  DWORD cValues; // [rsp+68h] [rbp-18h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+6Ch] [rbp-14h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-10h] BYREF
  LPWSTR lpName; // [rsp+78h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  DWORD cchName; // [rsp+A0h] [rbp+20h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v2 = RegOpenKeyExW(**(HKEY **)a1, **(LPCWSTR **)(a1 + 8), 0, 0xF003Fu, &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)v3,
      phkResult);
LABEL_27:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return (unsigned int)v3;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  v3 = v4;
  if ( v4 > 0 )
    v3 = (unsigned __int16)v4 | 0x80070000;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)v3,
      phkResulta);
    goto LABEL_27;
  }
  if ( cValues )
  {
    v6 = RegDeleteValueW(hKey, L"TpmKeyTransportKeyName");
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1BB,
        (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)(unsigned int)v6);
  }
  if ( !cSubKeys )
  {
    v3 = 0;
    goto LABEL_27;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpName,
    0,
    ++cbMaxSubKeyLen,
    v5);
  v7 = lpName;
  if ( !lpName )
  {
    v3 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C7,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)0x8007000ELL,
      phkResulta);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpName);
    goto LABEL_27;
  }
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = cbMaxSubKeyLen;
    v9 = RegEnumKeyExW(hKey, i, v7, &cchName, 0, 0, 0, 0);
    v3 = v9;
    if ( v9 > 0 )
      v3 = (unsigned __int16)v9 | 0x80070000;
    if ( v3 == -2147024637 )
      break;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DC,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)(unsigned int)v3,
        phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpName);
      goto LABEL_27;
    }
    DeleteTpmKeyTransportKeyReg(hKey, lpName);
    v7 = lpName;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpName);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x1800103f8  mov     [rsp-18h+arg_8], rbx
0x1800103fd  mov     [rsp-18h+arg_10], rsi
0x180010402  push    rbp
0x180010403  push    rdi
0x180010404  push    r14
0x180010406  mov     rbp, rsp
0x180010409  sub     rsp, 80h
0x180010410  mov     rbx, rcx
0x180010413  xor     esi, esi
0x180010415  mov     [rbp+hKey], rsi
0x180010419  xor     edx, edx
0x18001041b  lea     rcx, [rbp+hKey]
0x18001041f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180010424  mov     rdx, [rbx+8]
0x180010428  mov     rcx, [rbx]
0x18001042b  lea     rax, [rbp+hKey]
0x18001042f  mov     [rsp+80h+phkResult], rax; int
0x180010434  mov     r9d, 0F003Fh; samDesired
0x18001043a  xor     r8d, r8d; ulOptions
0x18001043d  mov     rdx, [rdx]; lpSubKey
0x180010440  mov     rcx, [rcx]; hKey
0x180010443  call    cs:__imp_RegOpenKeyExW
0x180010449  mov     ebx, eax
0x18001044b  mov     r14d, 80070000h
0x180010451  test    eax, eax
0x180010453  jle     short loc_18001045B
0x180010455  movzx   ebx, ax
0x180010458  or      ebx, r14d
0x18001045b  test    ebx, ebx
0x18001045d  jns     short loc_18001047D
0x18001045f  mov     rcx, [rbp+18h]; this
0x180010463  mov     r9d, ebx; char *
0x180010466  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001046d  mov     edx, 1A2h; void *
0x180010472  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010477  nop
0x180010478  jmp     loc_18001062F
0x18001047d  mov     [rbp+cSubKeys], esi
0x180010480  mov     [rbp+cbMaxSubKeyLen], esi
0x180010483  mov     [rbp+cValues], esi
0x180010486  mov     [rbp+cbMaxValueNameLen], esi
0x180010489  mov     [rsp+80h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18001048e  mov     [rsp+80h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180010493  mov     [rsp+80h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180010498  lea     rax, [rbp+cbMaxValueNameLen]
0x18001049c  mov     [rsp+80h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800104a1  lea     rax, [rbp+cValues]
0x1800104a5  mov     [rsp+80h+lpcValues], rax; lpcValues
0x1800104aa  mov     [rsp+80h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1800104af  lea     rax, [rbp+cbMaxSubKeyLen]
0x1800104b3  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800104b8  lea     rax, [rbp+cSubKeys]
0x1800104bc  mov     [rsp+80h+phkResult], rax; int
0x1800104c1  xor     r9d, r9d; lpReserved
0x1800104c4  xor     r8d, r8d; lpcchClass
0x1800104c7  xor     edx, edx; lpClass
0x1800104c9  mov     rcx, [rbp+hKey]; hKey
0x1800104cd  call    cs:__imp_RegQueryInfoKeyW
0x1800104d3  mov     ebx, eax
0x1800104d5  test    eax, eax
0x1800104d7  jle     short loc_1800104DF
0x1800104d9  movzx   ebx, ax
0x1800104dc  or      ebx, r14d
0x1800104df  test    ebx, ebx
0x1800104e1  jns     short loc_180010501
0x1800104e3  mov     rcx, [rbp+18h]; this
0x1800104e7  mov     r9d, ebx; char *
0x1800104ea  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800104f1  mov     edx, 1B4h; void *
0x1800104f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800104fb  nop
0x1800104fc  jmp     loc_18001062F
0x180010501  cmp     [rbp+cValues], esi
0x180010504  jbe     short loc_18001053D
0x180010506  lea     rdx, ValueName; "TpmKeyTransportKeyName"
0x18001050d  mov     rcx, [rbp+hKey]; hKey
0x180010511  call    cs:__imp_RegDeleteValueW
0x180010517  test    eax, eax
0x180010519  jle     short loc_180010521
0x18001051b  movzx   eax, ax
0x18001051e  or      eax, r14d
0x180010521  mov     rcx, [rbp+18h]; this
0x180010525  test    eax, eax
0x180010527  jns     short loc_18001053D
0x180010529  mov     r9d, eax; char *
0x18001052c  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180010533  mov     edx, 1BBh; void *
0x180010538  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001053d  cmp     [rbp+cSubKeys], esi
0x180010540  jnz     short loc_180010549
0x180010542  mov     ebx, esi
0x180010544  jmp     loc_18001062F
0x180010549  mov     eax, [rbp+cbMaxSubKeyLen]
0x18001054c  inc     eax
0x18001054e  mov     [rbp+cbMaxSubKeyLen], eax
0x180010551  mov     r8d, eax
0x180010554  xor     edx, edx
0x180010556  lea     rcx, [rbp+lpName]
0x18001055a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001055f  nop
0x180010560  mov     r8, [rbp+lpName]; lpName
0x180010564  test    r8, r8
0x180010567  jz      loc_180010607
0x18001056d  mov     edi, esi
0x18001056f  cmp     edi, [rbp+cSubKeys]
0x180010572  jnb     short loc_1800105F0
0x180010574  mov     eax, [rbp+cbMaxSubKeyLen]
0x180010577  mov     [rbp+cchName], eax
0x18001057a  mov     [rsp+80h+lpcValues], rsi; lpftLastWriteTime
0x18001057f  mov     [rsp+80h+lpcbMaxClassLen], rsi; lpcchClass
0x180010584  mov     [rsp+80h+lpcbMaxSubKeyLen], rsi; lpClass
0x180010589  mov     [rsp+80h+phkResult], rsi; int
0x18001058e  lea     r9, [rbp+cchName]; lpcchName
0x180010592  mov     edx, edi; dwIndex
0x180010594  mov     rcx, [rbp+hKey]; hKey
0x180010598  call    cs:__imp_RegEnumKeyExW
0x18001059e  mov     ebx, eax
0x1800105a0  test    eax, eax
0x1800105a2  jle     short loc_1800105AA
0x1800105a4  movzx   ebx, ax
0x1800105a7  or      ebx, r14d
0x1800105aa  cmp     ebx, 80070103h
0x1800105b0  jz      short loc_1800105F0
0x1800105b2  test    ebx, ebx
0x1800105b4  js      short loc_1800105CB
0x1800105b6  mov     rdx, [rbp+lpName]; unsigned __int16 *
0x1800105ba  mov     rcx, [rbp+hKey]; HKEY
0x1800105be  call    ?DeleteTpmKeyTransportKeyReg@@YAXPEAUHKEY__@@PEBG@Z; DeleteTpmKeyTransportKeyReg(HKEY__ *,ushort const *)
0x1800105c3  inc     edi
0x1800105c5  mov     r8, [rbp+lpName]
0x1800105c9  jmp     short loc_18001056F
0x1800105cb  mov     rcx, [rbp+18h]; this
0x1800105cf  mov     r9d, ebx; char *
0x1800105d2  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800105d9  mov     edx, 1DCh; void *
0x1800105de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800105e3  nop
0x1800105e4  lea     rcx, [rbp+lpName]
0x1800105e8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800105ed  nop
0x1800105ee  jmp     short loc_18001062F
0x1800105f0  lea     rcx, [rbp+lpName]
0x1800105f4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800105f9  nop
0x1800105fa  lea     rcx, [rbp+hKey]
0x1800105fe  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010603  xor     eax, eax
0x180010605  jmp     short loc_18001063A
0x180010607  mov     rcx, [rbp+18h]; this
0x18001060b  mov     ebx, 8007000Eh
0x180010610  mov     r9d, ebx; char *
0x180010613  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001061a  mov     edx, 1C7h; void *
0x18001061f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010624  nop
0x180010625  lea     rcx, [rbp+lpName]
0x180010629  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001062e  nop
0x18001062f  lea     rcx, [rbp+hKey]
0x180010633  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010638  mov     eax, ebx
0x18001063a  lea     r11, [rsp+80h+var_s0]
0x180010642  mov     rbx, [r11+28h]
0x180010646  mov     rsi, [r11+30h]
0x18001064a  mov     rsp, r11
0x18001064d  pop     r14
0x18001064f  pop     rdi
0x180010650  pop     rbp
0x180010651  retn
```
