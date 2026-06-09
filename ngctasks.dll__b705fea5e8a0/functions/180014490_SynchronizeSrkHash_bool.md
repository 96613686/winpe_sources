# SynchronizeSrkHash(bool *)

- ea: `0x180014490`
- end: `0x1800149b0`
- name: `?SynchronizeSrkHash@@YAJPEA_N@Z`
- size: `1312`
- prototype: `__int64 __fastcall(bool *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014ea4`

## callees

- `0x180007345`
- `0x180008c74`
- `0x18000cc34`
- `0x18000ebc0`
- `0x18000ef9c`
- `0x180010248`
- `0x180010310`
- `0x180011a80`
- `0x180011df4`
- `0x180014490`
- `0x180014bcc`
- `0x18001c9ac`
- `0x18001cc04`
- `0x18001ce64`
- `0x18001cff4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800145bc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800145bc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001479a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001479a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014526`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014776`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001481f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014969`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014991`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014526`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014776`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001481f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800148a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014928`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014969`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014991`

## string_xrefs

- `0x180014507`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x18001455f`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x1800145dc`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x18001464b`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SynchronizeSrkHash(bool *a1, __int64 a2, unsigned int *a3)
{
  signed int SrkHash; // edi
  HLOCAL v5; // rcx
  const unsigned __int16 *v7; // rdx
  NgcUtils *v8; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  LSTATUS v10; // eax
  NgcUtils *v11; // rcx
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r9
  int RegistryValue; // edi
  int v15; // r14d
  char v16; // di
  __int64 i; // rdi
  int v18; // eax
  __int64 j; // rdi
  int v20; // eax
  const unsigned __int16 *v21; // rdx
  NgcUtils *v22; // rcx
  int v23; // eax
  void *v24; // rcx
  int v25; // eax
  const unsigned __int16 *v26; // rdx
  NgcUtils *v27; // rcx
  int v28; // eax
  void *v29; // rcx
  const unsigned __int16 *v30; // rdx
  NgcUtils *v31; // rcx
  int v32; // eax
  NgcUtils *v33; // rcx
  const unsigned __int16 *v34; // r8
  void *v35; // rcx
  int v36; // eax
  void *v37; // rcx
  void *v38; // rcx
  HLOCAL v39; // rcx
  int dwOptions; // [rsp+20h] [rbp-59h]
  int dwOptionsa; // [rsp+20h] [rbp-59h]
  const unsigned __int16 *dwOptionsb; // [rsp+20h] [rbp-59h]
  int dwOptionsc; // [rsp+20h] [rbp-59h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-49h]
  unsigned __int8 *lpSecurityAttributesa; // [rsp+30h] [rbp-49h]
  unsigned int phkResult; // [rsp+38h] [rbp-41h]
  HLOCAL hMem; // [rsp+50h] [rbp-29h] BYREF
  void *Buf2; // [rsp+58h] [rbp-21h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-11h] BYREF
  int v51; // [rsp+70h] [rbp-9h]
  LPCWSTR v52; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int16 *v53; // [rsp+80h] [rbp+7h] BYREF
  HKEY v54; // [rsp+88h] [rbp+Fh] BYREF
  HLOCAL *p_hMem; // [rsp+90h] [rbp+17h] BYREF
  unsigned __int16 *v56; // [rsp+98h] [rbp+1Fh] BYREF
  char v57; // [rsp+A0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  size_t Size; // [rsp+E0h] [rbp+67h] BYREF
  unsigned __int8 *v60; // [rsp+E8h] [rbp+6Fh] BYREF

  v51 = 0;
  if ( a1 )
    *a1 = 0;
  LODWORD(v60) = 0;
  hMem = 0;
  p_hMem = &hMem;
  v56 = 0;
  v57 = 1;
  v51 = 1;
  SrkHash = NgcUtils::GetSrkHash((NgcUtils *)&v56, &v60, a3);
  v51 = 0;
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( SrkHash < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FA,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)SrkHash,
      dwOptions);
LABEL_5:
    v5 = hMem;
    hMem = 0;
    if ( v5 )
      LocalFree(v5);
    return (unsigned int)SrkHash;
  }
  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v8,
                                        v7,
                                        L"PregenKeys",
                                        (unsigned __int16 *)&lpSubKey);
  SrkHash = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FF,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      dwOptions);
LABEL_10:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
    goto LABEL_5;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  SrkHash = v10;
  if ( v10 > 0 )
    SrkHash = (unsigned __int16)v10 | 0x80070000;
  if ( SrkHash < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)SrkHash,
      dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_10;
  }
  LODWORD(Size) = 0;
  Buf2 = 0;
  p_hMem = &Buf2;
  v56 = 0;
  v57 = 1;
  v51 = 2;
  RegistryValue = NgcUtils::GetRegistryValue(
                    v11,
                    (HKEY)lpSubKey,
                    v12,
                    v13,
                    (unsigned int)&v56,
                    (unsigned __int8 **)&Size,
                    &lpSecurityAttributes->nLength);
  v51 = 0;
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  v15 = (int)v60;
  if ( RegistryValue < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x217,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)RegistryValue,
      (int)dwOptionsb);
LABEL_17:
    v16 = 1;
    goto LABEL_18;
  }
  if ( !Buf2 )
    goto LABEL_17;
  v16 = 0;
  if ( (_DWORD)v60 == (_DWORD)Size && !memcmp_0(hMem, Buf2, (unsigned int)Size) )
    goto LABEL_54;
LABEL_18:
  if ( !a1 )
  {
    if ( !v16 )
    {
      for ( i = 0; i != 7; ++i )
      {
        v18 = DeleteChildRegistry(hKey, off_180031080[i], 2u);
        if ( v18 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x230,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
            (const char *)(unsigned int)v18,
            (int)dwOptionsb);
      }
      for ( j = 0; j != 3; ++j )
      {
        v20 = DeleteChildRegistry(hKey, off_1800310C0[j], 1u);
        if ( v20 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x237,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
            (const char *)(unsigned int)v20,
            (int)dwOptionsb);
      }
    }
    v52 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v52,
      0);
    v23 = NgcUtils::GetNgcStateSeparatedRegistryLocation(v22, v21, L"AIK", (unsigned __int16 *)&v52);
    SrkHash = v23;
    if ( v23 >= 0 )
    {
      v25 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v52);
      if ( v25 > 0 )
        v25 = (unsigned __int16)v25 | 0x80070000;
      if ( v25 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x245,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v25,
          (int)dwOptionsb);
      v53 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v53,
        0);
      v28 = NgcUtils::GetNgcStateSeparatedRegistryLocation(v27, v26, L"KeyTransportKey", (unsigned __int16 *)&v53);
      SrkHash = v28;
      if ( v28 >= 0 )
      {
        DeleteTpmKeyTransportKeyReg(HKEY_LOCAL_MACHINE, v53);
        v54 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v54,
          0);
        v32 = NgcUtils::GetNgcStateSeparatedRegistryLocation(v31, v30, L"PregenKeys", (unsigned __int16 *)&v54);
        SrkHash = v32;
        if ( v32 >= 0 )
        {
          LODWORD(lpSecurityAttributesa) = v15;
          LODWORD(dwOptionsb) = 3;
          v36 = NgcUtils::SetRegistryValue(
                  v33,
                  v54,
                  v34,
                  (struct _SECURITY_ATTRIBUTES *)L"SRKModulusHash",
                  dwOptionsb,
                  (unsigned int)hMem,
                  lpSecurityAttributesa,
                  phkResult);
          SrkHash = v36;
          if ( v36 >= 0 )
          {
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
            goto LABEL_54;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x25F,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
            (const char *)(unsigned int)v36,
            dwOptionsc);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
          v37 = Buf2;
          Buf2 = 0;
          if ( v37 )
            LocalFree(v37);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x255,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
            (const char *)(unsigned int)v32,
            (int)dwOptionsb);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
          v35 = Buf2;
          Buf2 = 0;
          if ( v35 )
            LocalFree(v35);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24A,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v28,
          (int)dwOptionsb);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v53);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
        v29 = Buf2;
        Buf2 = 0;
        if ( v29 )
          LocalFree(v29);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23E,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)(unsigned int)v23,
        (int)dwOptionsb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
      v24 = Buf2;
      Buf2 = 0;
      if ( v24 )
        LocalFree(v24);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_10;
  }
  *a1 = 1;
LABEL_54:
  v38 = Buf2;
  Buf2 = 0;
  if ( v38 )
    LocalFree(v38);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  v39 = hMem;
  hMem = 0;
  if ( v39 )
    LocalFree(v39);
  return 0;
}

```

## disassembly

```asm
0x180014490  mov     [rsp-8+arg_10], rbx
0x180014495  push    rbp
0x180014496  push    rsi
0x180014497  push    rdi
0x180014498  push    r14
0x18001449a  push    r15
0x18001449c  lea     rbp, [rsp-37h]
0x1800144a1  sub     rsp, 0B0h
0x1800144a8  mov     rsi, rcx
0x1800144ab  xor     r15d, r15d
0x1800144ae  mov     [rbp+57h+var_60], r15d
0x1800144b2  test    rcx, rcx
0x1800144b5  jz      short loc_1800144BA
0x1800144b7  mov     [rcx], r15b
0x1800144ba  mov     dword ptr [rbp+57h+arg_8], r15d
0x1800144be  mov     [rbp+57h+hMem], r15
0x1800144c2  lea     rax, [rbp+57h+hMem]
0x1800144c6  mov     [rbp+57h+var_40], rax
0x1800144ca  mov     [rbp+57h+var_38], r15
0x1800144ce  mov     [rbp+57h+var_30], 1
0x1800144d2  mov     [rbp+57h+var_60], 1
0x1800144d9  lea     rdx, [rbp+57h+arg_8]; unsigned __int8 **
0x1800144dd  lea     rcx, [rbp+57h+var_38]; this
0x1800144e1  call    ?GetSrkHash@NgcUtils@@YAJPEAPEAEPEAK@Z; NgcUtils::GetSrkHash(uchar * *,ulong *)
0x1800144e6  mov     edi, eax
0x1800144e8  mov     ebx, 1
0x1800144ed  and     ebx, 0FFFFFFFEh
0x1800144f0  mov     [rbp+57h+var_60], ebx
0x1800144f3  lea     rcx, [rbp+57h+var_40]
0x1800144f7  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800144fc  test    edi, edi
0x1800144fe  jns     short loc_180014533
0x180014500  mov     rcx, [rbp+5Fh]; this
0x180014504  mov     r9d, edi; char *
0x180014507  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001450e  mov     edx, 1FAh; void *
0x180014513  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014518  nop
0x180014519  mov     rcx, [rbp+57h+hMem]; hMem
0x18001451d  mov     [rbp+57h+hMem], r15
0x180014521  test    rcx, rcx
0x180014524  jz      short loc_18001452C
0x180014526  call    cs:__imp_LocalFree
0x18001452c  mov     eax, edi
0x18001452e  jmp     loc_180014999
0x180014533  mov     [rbp+57h+lpSubKey], r15
0x180014537  xor     edx, edx
0x180014539  lea     rcx, [rbp+57h+lpSubKey]
0x18001453d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180014542  lea     r9, [rbp+57h+lpSubKey]; unsigned __int16 *
0x180014546  lea     r8, aPregenkeys; "PregenKeys"
0x18001454d  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180014552  mov     edi, eax
0x180014554  test    eax, eax
0x180014556  jns     short loc_18001457C
0x180014558  mov     rcx, [rbp+5Fh]; this
0x18001455c  mov     r9d, eax; char *
0x18001455f  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180014566  mov     edx, 1FFh; void *
0x18001456b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014570  nop
0x180014571  lea     rcx, [rbp+57h+lpSubKey]
0x180014575  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001457a  jmp     short loc_180014519
0x18001457c  mov     [rbp+57h+hKey], r15
0x180014580  xor     edx, edx
0x180014582  lea     rcx, [rbp+57h+hKey]
0x180014586  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001458b  mov     [rsp+0D0h+lpdwDisposition], r15; lpdwDisposition
0x180014590  lea     rax, [rbp+57h+hKey]
0x180014594  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x180014599  mov     [rsp+0D0h+lpSecurityAttributes], r15; unsigned int *
0x18001459e  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x1800145a6  mov     [rsp+0D0h+dwOptions], r15d; int
0x1800145ab  xor     r9d, r9d; lpClass
0x1800145ae  xor     r8d, r8d; Reserved
0x1800145b1  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800145b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800145bc  call    cs:__imp_RegCreateKeyExW
0x1800145c2  mov     edi, eax
0x1800145c4  test    eax, eax
0x1800145c6  jle     short loc_1800145D1
0x1800145c8  movzx   edi, ax
0x1800145cb  or      edi, 80070000h
0x1800145d1  test    edi, edi
0x1800145d3  jns     short loc_1800145FD
0x1800145d5  mov     rcx, [rbp+5Fh]; this
0x1800145d9  mov     r9d, edi; char *
0x1800145dc  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800145e3  mov     edx, 20Ch; void *
0x1800145e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800145ed  nop
0x1800145ee  lea     rcx, [rbp+57h+hKey]
0x1800145f2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800145f7  nop
0x1800145f8  jmp     loc_180014571
0x1800145fd  mov     dword ptr [rbp+57h+Size], r15d
0x180014601  mov     [rbp+57h+Buf2], r15
0x180014605  lea     rax, [rbp+57h+Buf2]
0x180014609  mov     [rbp+57h+var_40], rax
0x18001460d  mov     [rbp+57h+var_38], r15
0x180014611  mov     [rbp+57h+var_30], 1
0x180014615  or      ebx, 2
0x180014618  mov     [rbp+57h+var_60], ebx
0x18001461b  lea     rax, [rbp+57h+Size]
0x18001461f  mov     qword ptr [rsp+0D0h+samDesired], rax; unsigned __int8 **
0x180014624  lea     rax, [rbp+57h+var_38]
0x180014628  mov     qword ptr [rsp+0D0h+dwOptions], rax; int
0x18001462d  mov     rdx, [rbp+57h+lpSubKey]; HKEY
0x180014631  call    ?GetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1KPEAPEAEPEAK@Z; NgcUtils::GetRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x180014636  mov     edi, eax
0x180014638  and     ebx, 0FFFFFFFDh
0x18001463b  mov     [rbp+57h+var_60], ebx
0x18001463e  lea     rcx, [rbp+57h+var_40]
0x180014642  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180014647  mov     rcx, [rbp+5Fh]; this
0x18001464b  lea     rbx, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180014652  mov     r14d, dword ptr [rbp+57h+arg_8]
0x180014656  test    edi, edi
0x180014658  jns     short loc_18001467A
0x18001465a  mov     r9d, edi; char *
0x18001465d  mov     r8, rbx; unsigned int
0x180014660  mov     edx, 217h; void *
0x180014665  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001466a  mov     dil, 1
0x18001466d  test    rsi, rsi
0x180014670  jz      short loc_1800146A3
0x180014672  mov     byte ptr [rsi], 1
0x180014675  jmp     loc_18001495C
0x18001467a  mov     rdx, [rbp+57h+Buf2]; Buf2
0x18001467e  test    rdx, rdx
0x180014681  jz      short loc_18001466A
0x180014683  mov     dil, r15b
0x180014686  cmp     r14d, dword ptr [rbp+57h+Size]
0x18001468a  jnz     short loc_18001466D
0x18001468c  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x180014690  mov     rcx, [rbp+57h+hMem]; Buf1
0x180014694  call    memcmp_0
0x180014699  test    eax, eax
0x18001469b  jz      loc_18001495C
0x1800146a1  jmp     short loc_18001466D
0x1800146a3  test    dil, dil
0x1800146a6  jnz     short loc_180014725
0x1800146a8  mov     rdi, r15
0x1800146ab  lea     rsi, __ImageBase
0x1800146b2  mov     r8d, 2; unsigned int
0x1800146b8  mov     rdx, rva off_180031080[rsi+rdi*8]; lpSubKey
0x1800146c0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800146c4  call    ?DeleteChildRegistry@@YAJPEAUHKEY__@@PEBGK@Z; DeleteChildRegistry(HKEY__ *,ushort const *,ulong)
0x1800146c9  mov     rcx, [rbp+5Fh]; this
0x1800146cd  test    eax, eax
0x1800146cf  jns     short loc_1800146E1
0x1800146d1  mov     r9d, eax; char *
0x1800146d4  mov     r8, rbx; unsigned int
0x1800146d7  mov     edx, 230h; void *
0x1800146dc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800146e1  inc     rdi
0x1800146e4  cmp     rdi, 7
0x1800146e8  jnz     short loc_1800146B2
0x1800146ea  mov     rdi, r15
0x1800146ed  mov     r8d, 1; unsigned int
0x1800146f3  mov     rdx, rva off_1800310C0[rsi+rdi*8]; lpSubKey
0x1800146fb  mov     rcx, [rbp+57h+hKey]; hKey
0x1800146ff  call    ?DeleteChildRegistry@@YAJPEAUHKEY__@@PEBGK@Z; DeleteChildRegistry(HKEY__ *,ushort const *,ulong)
0x180014704  mov     rcx, [rbp+5Fh]; this
0x180014708  test    eax, eax
0x18001470a  jns     short loc_18001471C
0x18001470c  mov     r9d, eax; char *
0x18001470f  mov     r8, rbx; unsigned int
0x180014712  mov     edx, 237h; void *
0x180014717  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001471c  inc     rdi
0x18001471f  cmp     rdi, 3
0x180014723  jnz     short loc_1800146ED
0x180014725  mov     [rbp+57h+var_58], r15
0x180014729  xor     edx, edx
0x18001472b  lea     rcx, [rbp+57h+var_58]
0x18001472f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180014734  lea     r9, [rbp+57h+var_58]; unsigned __int16 *
0x180014738  lea     r8, aAik; "AIK"
0x18001473f  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180014744  mov     edi, eax
0x180014746  test    eax, eax
0x180014748  jns     short loc_18001478C
0x18001474a  mov     rcx, [rbp+5Fh]; this
0x18001474e  mov     r9d, eax; char *
0x180014751  mov     r8, rbx; unsigned int
0x180014754  mov     edx, 23Eh; void *
0x180014759  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001475e  nop
0x18001475f  lea     rcx, [rbp+57h+var_58]
0x180014763  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014768  nop
0x180014769  mov     rcx, [rbp+57h+Buf2]; hMem
0x18001476d  mov     [rbp+57h+Buf2], r15
0x180014771  test    rcx, rcx
0x180014774  jz      short loc_18001477D
0x180014776  call    cs:__imp_LocalFree
0x18001477c  nop
0x18001477d  lea     rcx, [rbp+57h+hKey]
0x180014781  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180014786  nop
0x180014787  jmp     loc_180014571
0x18001478c  mov     rdx, [rbp+57h+var_58]; lpSubKey
0x180014790  mov     rsi, 0FFFFFFFF80000002h
0x180014797  mov     rcx, rsi; hKey
0x18001479a  call    cs:__imp_RegDeleteTreeW
0x1800147a0  test    eax, eax
0x1800147a2  jle     short loc_1800147AC
0x1800147a4  movzx   eax, ax
0x1800147a7  or      eax, 80070000h
0x1800147ac  mov     rcx, [rbp+5Fh]; this
0x1800147b0  test    eax, eax
0x1800147b2  jns     short loc_1800147C4
0x1800147b4  mov     r9d, eax; char *
0x1800147b7  mov     r8, rbx; unsigned int
0x1800147ba  mov     edx, 245h; void *
0x1800147bf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800147c4  mov     [rbp+57h+var_50], r15
0x1800147c8  xor     edx, edx
0x1800147ca  lea     rcx, [rbp+57h+var_50]
0x1800147ce  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800147d3  lea     r9, [rbp+57h+var_50]; unsigned __int16 *
0x1800147d7  lea     r8, aKeytransportke; "KeyTransportKey"
0x1800147de  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800147e3  mov     edi, eax
0x1800147e5  test    eax, eax
0x1800147e7  jns     short loc_180014835
0x1800147e9  mov     rcx, [rbp+5Fh]; this
0x1800147ed  mov     r9d, eax; char *
0x1800147f0  mov     r8, rbx; unsigned int
0x1800147f3  mov     edx, 24Ah; void *
0x1800147f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800147fd  nop
0x1800147fe  lea     rcx, [rbp+57h+var_50]
0x180014802  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014807  nop
0x180014808  lea     rcx, [rbp+57h+var_58]
0x18001480c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014811  nop
0x180014812  mov     rcx, [rbp+57h+Buf2]; hMem
0x180014816  mov     [rbp+57h+Buf2], r15
0x18001481a  test    rcx, rcx
0x18001481d  jz      short loc_180014826
0x18001481f  call    cs:__imp_LocalFree
0x180014825  nop
0x180014826  lea     rcx, [rbp+57h+hKey]
0x18001482a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001482f  nop
0x180014830  jmp     loc_180014571
0x180014835  mov     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x180014839  mov     rcx, rsi; HKEY
0x18001483c  call    ?DeleteTpmKeyTransportKeyReg@@YAXPEAUHKEY__@@PEBG@Z; DeleteTpmKeyTransportKeyReg(HKEY__ *,ushort const *)
0x180014841  mov     [rbp+57h+var_48], r15
0x180014845  xor     edx, edx
0x180014847  lea     rcx, [rbp+57h+var_48]
0x18001484b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180014850  lea     r9, [rbp+57h+var_48]; unsigned __int16 *
0x180014854  lea     r8, aPregenkeys; "PregenKeys"
0x18001485b  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180014860  mov     edi, eax
0x180014862  test    eax, eax
0x180014864  jns     short loc_1800148BC
0x180014866  mov     rcx, [rbp+5Fh]; this
0x18001486a  mov     r9d, eax; char *
0x18001486d  mov     r8, rbx; unsigned int
0x180014870  mov     edx, 255h; void *
0x180014875  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001487a  nop
0x18001487b  lea     rcx, [rbp+57h+var_48]
0x18001487f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014884  nop
0x180014885  lea     rcx, [rbp+57h+var_50]
0x180014889  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001488e  nop
0x18001488f  lea     rcx, [rbp+57h+var_58]
0x180014893  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014898  nop
0x180014899  mov     rcx, [rbp+57h+Buf2]; hMem
0x18001489d  mov     [rbp+57h+Buf2], r15
0x1800148a1  test    rcx, rcx
0x1800148a4  jz      short loc_1800148AD
0x1800148a6  call    cs:__imp_LocalFree
0x1800148ac  nop
0x1800148ad  lea     rcx, [rbp+57h+hKey]
0x1800148b1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800148b6  nop
0x1800148b7  jmp     loc_180014571
0x1800148bc  mov     rax, [rbp+57h+hMem]
0x1800148c0  mov     dword ptr [rsp+0D0h+lpSecurityAttributes], r14d; unsigned __int8 *
0x1800148c5  mov     qword ptr [rsp+0D0h+samDesired], rax; unsigned int
0x1800148ca  mov     [rsp+0D0h+dwOptions], 3; int
0x1800148d2  lea     r9, aSrkmodulushash; "SRKModulusHash"
0x1800148d9  mov     rdx, [rbp+57h+var_48]; HKEY
0x1800148dd  call    ?SetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBGPEAU_SECURITY_ATTRIBUTES@@1KPEAEK@Z; NgcUtils::SetRegistryValue(HKEY__ *,ushort const *,_SECURITY_ATTRIBUTES *,ushort const *,ulong,uchar *,ulong)
0x1800148e2  mov     edi, eax
0x1800148e4  test    eax, eax
0x1800148e6  jns     short loc_18001493E
0x1800148e8  mov     rcx, [rbp+5Fh]; this
0x1800148ec  mov     r9d, eax; char *
  ... truncated ...
```
