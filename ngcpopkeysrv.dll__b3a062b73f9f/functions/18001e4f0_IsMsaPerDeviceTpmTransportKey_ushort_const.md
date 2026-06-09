# IsMsaPerDeviceTpmTransportKey(ushort const *)

- ea: `0x18001e4f0`
- end: `0x18001e861`
- name: `?IsMsaPerDeviceTpmTransportKey@@YA_NPEBG@Z`
- size: `881`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e330`

## callees

- `0x18000dad8`
- `0x18000db5c`
- `0x1800105dc`
- `0x18001069c`
- `0x18001070c`
- `0x180010730`
- `0x180014e40`
- `0x1800152f4`
- `0x1800153f0`
- `0x18001737c`
- `0x18001c984`
- `0x18001e1a4`
- `0x18001e4f0`
- `0x180023124`
- `0x180023264`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001e6e3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001e6e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e61e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e61e`

## string_xrefs

- `0x18001e533`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\tpmsymmetricpopkey.cpp`
- `0x18001e5e1`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\tpmsymmetricpopkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall IsMsaPerDeviceTpmTransportKey(char *a1)
{
  int MsaPerDeviceKeyRegLocation; // eax
  char v3; // di
  int RegistryValue; // ebx
  unsigned __int64 v5; // r8
  char *v6; // r11
  char *v7; // rdx
  int v8; // ecx
  int v9; // eax
  HKEY *v10; // rax
  unsigned int v11; // eax
  unsigned int *v12; // r9
  int v13; // eax
  DWORD v14; // r15d
  WCHAR *v15; // rbx
  DWORD i; // r14d
  unsigned int v17; // eax
  int v18; // r12d
  unsigned __int64 v19; // r8
  char *v20; // r11
  char *v21; // rdx
  int v22; // ecx
  int v23; // eax
  int phkResult; // [rsp+20h] [rbp-60h]
  int phkResulta; // [rsp+20h] [rbp-60h]
  unsigned int phkResultb; // [rsp+20h] [rbp-60h]
  unsigned int phkResultc; // [rsp+20h] [rbp-60h]
  int phkResultd; // [rsp+20h] [rbp-60h]
  HKEY hKey; // [rsp+40h] [rbp-40h] BYREF
  NgcUtils *v31; // [rsp+48h] [rbp-38h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-30h] BYREF
  NgcUtils *v33; // [rsp+58h] [rbp-28h] BYREF
  LPWSTR lpName; // [rsp+60h] [rbp-20h] BYREF
  NgcUtils **v35; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v36[2]; // [rsp+70h] [rbp-10h] BYREF
  char v37; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  unsigned __int8 *v39; // [rsp+C8h] [rbp+48h] BYREF
  struct HKEY__ v40; // [rsp+D0h] [rbp+50h] BYREF
  DWORD cchName; // [rsp+D8h] [rbp+58h] BYREF

  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  MsaPerDeviceKeyRegLocation = GetMsaPerDeviceKeyRegLocation((unsigned __int16 **)&lpSubKey);
  if ( MsaPerDeviceKeyRegLocation < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\tpmsymmetricpopkey.cpp",
      (const char *)(unsigned int)MsaPerDeviceKeyRegLocation,
      phkResult);
LABEL_14:
    v3 = 0;
LABEL_33:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
    return v3;
  }
  LODWORD(v39) = 0;
  v31 = 0;
  v35 = &v31;
  *(_QWORD *)v36 = 0;
  v3 = 1;
  v37 = 1;
  RegistryValue = NgcUtils::GetRegistryValue(HKEY_LOCAL_MACHINE, lpSubKey, L"TpmKeyTransportKeyName", 2u, v36, &v39);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v35);
  if ( RegistryValue >= 0
    && NgcUtils::IsStringNullTerminated(v31, (const unsigned __int16 *)(unsigned int)((_DWORD)v39 + 1), v5) )
  {
    v7 = (char *)(a1 - v6);
    do
    {
      v8 = *(unsigned __int16 *)&v7[(_QWORD)v6];
      v9 = *(unsigned __int16 *)v6 - v8;
      if ( v9 )
        break;
      v6 += 2;
    }
    while ( v8 );
    if ( !v9 )
    {
LABEL_32:
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v31,
        0);
      goto LABEL_33;
    }
  }
  if ( RegistryValue < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\tpmsymmetricpopkey.cpp",
      (const char *)(unsigned int)RegistryValue,
      phkResulta);
  hKey = 0;
  v10 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, v10);
  if ( v11 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\tpmsymmetricpopkey.cpp",
      (const char *)v11,
      phkResultb);
LABEL_13:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v31, 0);
    goto LABEL_14;
  }
  v40.unused = 0;
  LODWORD(v39) = 0;
  v13 = NgcUtils::QueryRegistrySubKeys((NgcUtils *)hKey, &v40, (unsigned int *)&v39, v12);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\tpmsymmetricpopkey.cpp",
      (const char *)(unsigned int)v13,
      phkResultb);
    goto LABEL_13;
  }
  v14 = (_DWORD)v39 + 1;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpName,
    0,
    (unsigned int)((_DWORD)v39 + 1));
  v15 = lpName;
  if ( lpName )
  {
    for ( i = 0; i < v40.unused; ++i )
    {
      cchName = v14;
      v17 = RegEnumKeyExW(hKey, i, v15, &cchName, 0, 0, 0, 0);
      if ( v17 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x82,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\tpmsymmetricpopkey.cpp",
          (const char *)v17,
          phkResultc);
      }
      else
      {
        LODWORD(v39) = 0;
        v33 = 0;
        v35 = &v33;
        *(_QWORD *)v36 = 0;
        v37 = 1;
        v18 = NgcUtils::GetRegistryValue(hKey, v15, L"TpmKeyTransportKeyName", 2u, v36, &v39);
        wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v35);
        if ( v18 >= 0 )
        {
          if ( NgcUtils::IsStringNullTerminated(v33, (const unsigned __int16 *)(unsigned int)((_DWORD)v39 + 1), v19) )
          {
            v21 = (char *)(a1 - v20);
            do
            {
              v22 = *(unsigned __int16 *)&v21[(_QWORD)v20];
              v23 = *(unsigned __int16 *)v20 - v22;
              if ( v23 )
                break;
              v20 += 2;
            }
            while ( v22 );
            if ( !v23 )
            {
              wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
                &v33,
                0);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              goto LABEL_32;
            }
          }
          wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
            &v33,
            0);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x90,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\tpmsymmetricpopkey.cpp",
            (const char *)(unsigned int)v18,
            phkResultd);
          wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
            &v33,
            0);
        }
      }
    }
  }
  else
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\tpmsymmetricpopkey.cpp",
      (const char *)0x8009000ELL,
      phkResultb);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpName);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v31, 0);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
  return 0;
}

```

## disassembly

```asm
0x18001e4f0  mov     [rsp-38h+arg_0], rbx
0x18001e4f5  push    rbp
0x18001e4f6  push    rsi
0x18001e4f7  push    rdi
0x18001e4f8  push    r12
0x18001e4fa  push    r13
0x18001e4fc  push    r14
0x18001e4fe  push    r15
0x18001e500  mov     rbp, rsp
0x18001e503  sub     rsp, 80h
0x18001e50a  mov     r13, rcx
0x18001e50d  xor     r12d, r12d
0x18001e510  mov     [rbp+lpSubKey], r12
0x18001e514  xor     edx, edx
0x18001e516  lea     rcx, [rbp+lpSubKey]
0x18001e51a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001e51f  lea     rcx, [rbp+lpSubKey]; unsigned __int16 **
0x18001e523  call    ?GetMsaPerDeviceKeyRegLocation@@YAJPEAPEAG@Z; GetMsaPerDeviceKeyRegLocation(ushort * *)
0x18001e528  mov     rcx, [rbp+38h]; this
0x18001e52c  test    eax, eax
0x18001e52e  jns     short loc_18001E549
0x18001e530  mov     r9d, eax; char *
0x18001e533  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001e53a  lea     edx, [r12+39h]; void *
0x18001e53f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e544  jmp     loc_18001E652
0x18001e549  mov     dword ptr [rbp+arg_8], r12d
0x18001e54d  mov     [rbp+var_38], r12
0x18001e551  lea     rax, [rbp+var_38]
0x18001e555  mov     [rbp+var_18], rax
0x18001e559  mov     qword ptr [rbp+var_10], r12
0x18001e55d  mov     edi, 1
0x18001e562  mov     [rbp+var_8], dil
0x18001e566  lea     rax, [rbp+arg_8]
0x18001e56a  mov     [rsp+80h+lpClass], rax; unsigned __int8 **
0x18001e56f  lea     rax, [rbp+var_10]
0x18001e573  mov     [rsp+80h+phkResult], rax; int
0x18001e578  lea     r9d, [rdi+1]; dwFlags
0x18001e57c  lea     r8, aTpmkeytranspor; "TpmKeyTransportKeyName"
0x18001e583  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001e587  mov     r14, 0FFFFFFFF80000002h
0x18001e58e  mov     rcx, r14; hkey
0x18001e591  call    ?GetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1KPEAPEAEPEAK@Z; NgcUtils::GetRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x18001e596  mov     ebx, eax
0x18001e598  lea     rcx, [rbp+var_18]
0x18001e59c  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001e5a1  test    ebx, ebx
0x18001e5a3  js      short loc_18001E5DD
0x18001e5a5  mov     r11, [rbp+var_38]
0x18001e5a9  mov     edx, dword ptr [rbp+arg_8]
0x18001e5ac  inc     edx; unsigned __int16 *
0x18001e5ae  mov     rcx, r11; this
0x18001e5b1  call    ?IsStringNullTerminated@NgcUtils@@YA_NPEBG_K@Z; NgcUtils::IsStringNullTerminated(ushort const *,unsigned __int64)
0x18001e5b6  test    al, al
0x18001e5b8  jz      short loc_18001E5DD
0x18001e5ba  mov     rdx, r13
0x18001e5bd  sub     rdx, r11
0x18001e5c0  movzx   eax, word ptr [r11]
0x18001e5c4  movzx   ecx, word ptr [r11+rdx]
0x18001e5c9  sub     eax, ecx
0x18001e5cb  jnz     short loc_18001E5D5
0x18001e5cd  add     r11, 2
0x18001e5d1  test    ecx, ecx
0x18001e5d3  jnz     short loc_18001E5C0
0x18001e5d5  test    eax, eax
0x18001e5d7  jz      loc_18001E7E9
0x18001e5dd  mov     rcx, [rbp+38h]; this
0x18001e5e1  lea     rsi, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001e5e8  test    ebx, ebx
0x18001e5ea  jns     short loc_18001E5FC
0x18001e5ec  mov     r9d, ebx; char *
0x18001e5ef  mov     r8, rsi; unsigned int
0x18001e5f2  mov     edx, 52h ; 'R'; void *
0x18001e5f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e5fc  mov     [rbp+hKey], r12
0x18001e600  lea     rcx, [rbp+hKey]
0x18001e604  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18001e609  mov     [rsp+80h+phkResult], rax; int
0x18001e60e  mov     r9d, 0F003Fh; samDesired
0x18001e614  xor     r8d, r8d; ulOptions
0x18001e617  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001e61b  mov     rcx, r14; hKey
0x18001e61e  call    cs:__imp_RegOpenKeyExW
0x18001e624  mov     rcx, [rbp+38h]; this
0x18001e628  test    eax, eax
0x18001e62a  jz      short loc_18001E65A
0x18001e62c  mov     r9d, eax; char *
0x18001e62f  mov     r8, rsi; unsigned int
0x18001e632  mov     edx, 5Bh ; '['; void *
0x18001e637  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18001e63c  nop
0x18001e63d  lea     rcx, [rbp+hKey]
0x18001e641  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001e646  nop
0x18001e647  xor     edx, edx
0x18001e649  lea     rcx, [rbp+var_38]
0x18001e64d  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001e652  mov     dil, r12b
0x18001e655  jmp     loc_18001E7F5
0x18001e65a  mov     [rbp+arg_10.unused], r12d
0x18001e65e  mov     dword ptr [rbp+arg_8], r12d
0x18001e662  lea     r8, [rbp+arg_8]; unsigned int *
0x18001e666  lea     rdx, [rbp+arg_10]; HKEY
0x18001e66a  mov     rcx, [rbp+hKey]; this
0x18001e66e  call    ?QueryRegistrySubKeys@NgcUtils@@YAJPEAUHKEY__@@PEAK1@Z; NgcUtils::QueryRegistrySubKeys(HKEY__ *,ulong *,ulong *)
0x18001e673  mov     rcx, [rbp+38h]; this
0x18001e677  test    eax, eax
0x18001e679  jns     short loc_18001E68D
0x18001e67b  mov     r9d, eax; char *
0x18001e67e  mov     r8, rsi; unsigned int
0x18001e681  mov     edx, 66h ; 'f'; void *
0x18001e686  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e68b  jmp     short loc_18001E63D
0x18001e68d  mov     r15d, dword ptr [rbp+arg_8]
0x18001e691  add     r15d, edi
0x18001e694  mov     r8d, r15d
0x18001e697  xor     edx, edx
0x18001e699  lea     rcx, [rbp+lpName]
0x18001e69d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001e6a2  nop
0x18001e6a3  mov     rbx, [rbp+lpName]
0x18001e6a7  test    rbx, rbx
0x18001e6aa  jz      loc_18001E803
0x18001e6b0  mov     r14d, r12d
0x18001e6b3  cmp     r14d, [rbp+arg_10.unused]
0x18001e6b7  jnb     loc_18001E81B
0x18001e6bd  mov     [rbp+cchName], r15d
0x18001e6c1  mov     [rsp+80h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18001e6c6  mov     [rsp+80h+lpcchClass], r12; unsigned int *
0x18001e6cb  mov     [rsp+80h+lpClass], r12; lpClass
0x18001e6d0  mov     [rsp+80h+phkResult], r12; unsigned int
0x18001e6d5  lea     r9, [rbp+cchName]; lpcchName
0x18001e6d9  mov     r8, rbx; lpName
0x18001e6dc  mov     edx, r14d; dwIndex
0x18001e6df  mov     rcx, [rbp+hKey]; hKey
0x18001e6e3  call    cs:__imp_RegEnumKeyExW
0x18001e6e9  mov     rcx, [rbp+38h]; this
0x18001e6ed  test    eax, eax
0x18001e6ef  jz      short loc_18001E706
0x18001e6f1  mov     r9d, eax; char *
0x18001e6f4  mov     r8, rsi; unsigned int
0x18001e6f7  mov     edx, 82h; void *
0x18001e6fc  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18001e701  jmp     loc_18001E7C1
0x18001e706  mov     dword ptr [rbp+arg_8], r12d
0x18001e70a  mov     [rbp+var_28], r12
0x18001e70e  lea     rax, [rbp+var_28]
0x18001e712  mov     [rbp+var_18], rax
0x18001e716  mov     qword ptr [rbp+var_10], r12
0x18001e71a  mov     [rbp+var_8], dil
0x18001e71e  lea     rax, [rbp+arg_8]
0x18001e722  mov     [rsp+80h+lpClass], rax; unsigned __int8 **
0x18001e727  lea     rax, [rbp+var_10]
0x18001e72b  mov     [rsp+80h+phkResult], rax; int
0x18001e730  mov     r9d, 2; dwFlags
0x18001e736  lea     r8, aTpmkeytranspor; "TpmKeyTransportKeyName"
0x18001e73d  mov     rdx, rbx; lpSubKey
0x18001e740  mov     rcx, [rbp+hKey]; hkey
0x18001e744  call    ?GetRegistryValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1KPEAPEAEPEAK@Z; NgcUtils::GetRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x18001e749  mov     r12d, eax
0x18001e74c  lea     rcx, [rbp+var_18]
0x18001e750  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001e755  mov     rcx, [rbp+38h]; this
0x18001e759  test    r12d, r12d
0x18001e75c  jns     short loc_18001E77F
0x18001e75e  mov     r9d, r12d; char *
0x18001e761  mov     r8, rsi; unsigned int
0x18001e764  mov     edx, 90h; void *
0x18001e769  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e76e  nop
0x18001e76f  xor     edx, edx
0x18001e771  lea     rcx, [rbp+var_28]
0x18001e775  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001e77a  xor     r12d, r12d
0x18001e77d  jmp     short loc_18001E7C1
0x18001e77f  mov     r11, [rbp+var_28]
0x18001e783  mov     edx, dword ptr [rbp+arg_8]
0x18001e786  inc     edx; unsigned __int16 *
0x18001e788  mov     rcx, r11; this
0x18001e78b  call    ?IsStringNullTerminated@NgcUtils@@YA_NPEBG_K@Z; NgcUtils::IsStringNullTerminated(ushort const *,unsigned __int64)
0x18001e790  xor     r12d, r12d
0x18001e793  test    al, al
0x18001e795  jz      short loc_18001E7B6
0x18001e797  mov     rdx, r13
0x18001e79a  sub     rdx, r11
0x18001e79d  movzx   eax, word ptr [r11]
0x18001e7a1  movzx   ecx, word ptr [r11+rdx]
0x18001e7a6  sub     eax, ecx
0x18001e7a8  jnz     short loc_18001E7B2
0x18001e7aa  add     r11, 2
0x18001e7ae  test    ecx, ecx
0x18001e7b0  jnz     short loc_18001E79D
0x18001e7b2  test    eax, eax
0x18001e7b4  jz      short loc_18001E7C9
0x18001e7b6  xor     edx, edx
0x18001e7b8  lea     rcx, [rbp+var_28]
0x18001e7bc  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001e7c1  add     r14d, edi
0x18001e7c4  jmp     loc_18001E6B3
0x18001e7c9  xor     edx, edx
0x18001e7cb  lea     rcx, [rbp+var_28]
0x18001e7cf  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001e7d4  nop
0x18001e7d5  lea     rcx, [rbp+lpName]
0x18001e7d9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001e7de  nop
0x18001e7df  lea     rcx, [rbp+hKey]
0x18001e7e3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001e7e8  nop
0x18001e7e9  xor     edx, edx
0x18001e7eb  lea     rcx, [rbp+var_38]
0x18001e7ef  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001e7f4  nop
0x18001e7f5  lea     rcx, [rbp+lpSubKey]
0x18001e7f9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001e7fe  mov     al, dil
0x18001e801  jmp     short loc_18001E846
0x18001e803  mov     rcx, [rbp+38h]; this
0x18001e807  mov     r9d, 8009000Eh; char *
0x18001e80d  mov     r8, rsi; unsigned int
0x18001e810  mov     edx, 72h ; 'r'; void *
0x18001e815  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001e81a  nop
0x18001e81b  lea     rcx, [rbp+lpName]
0x18001e81f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001e824  nop
0x18001e825  lea     rcx, [rbp+hKey]
0x18001e829  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001e82e  nop
0x18001e82f  xor     edx, edx
0x18001e831  lea     rcx, [rbp+var_38]
0x18001e835  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001e83a  nop
0x18001e83b  lea     rcx, [rbp+lpSubKey]
0x18001e83f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001e844  xor     al, al
0x18001e846  mov     rbx, [rsp+80h+arg_0]
0x18001e84e  add     rsp, 80h
0x18001e855  pop     r15
0x18001e857  pop     r14
0x18001e859  pop     r13
0x18001e85b  pop     r12
0x18001e85d  pop     rdi
0x18001e85e  pop     rsi
0x18001e85f  pop     rbp
0x18001e860  retn
```
