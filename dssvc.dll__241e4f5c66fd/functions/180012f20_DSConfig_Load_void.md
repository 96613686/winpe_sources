# DSConfig::Load(void)

- ea: `0x180012f20`
- end: `0x1800132a7`
- name: `?Load@DSConfig@@QEAAJXZ`
- size: `903`
- prototype: `__int64 __fastcall(DSConfig *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d21c`

## callees

- `0x180006e2c`
- `0x180006e54`
- `0x180006f78`
- `0x18000bf80`
- `0x18000c158`
- `0x18000c728`
- `0x18000c93c`
- `0x180012388`
- `0x1800123b8`
- `0x180012d84`
- `0x180012e28`
- `0x180012f20`
- `0x180019a94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800130bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001312f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800131a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800130bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001312f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800131a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012f6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012f6d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800131fd`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800131fd`

## string_xrefs

- `0x180012f82`: `Failed to open registry. Err=0x%x`
- `0x180012f93`: `DSConfig::Load`
- `0x18001305e`: `DSConfig::Load`
- `0x1800130eb`: `DSConfig::Load`
- `0x180013159`: `DSConfig::Load`
- `0x1800131cb`: `DSConfig::Load`
- `0x180013250`: `DSConfig::Load`
- `0x18001304d`: `Fail to read Version. HR=0x%x`
- `0x1800130d9`: `Failed to read ShortTermExpirySeconds. Err=0x%x`
- `0x180013147`: `Failed to read LongTermExpirySeconds. Err=0x%x`
- `0x1800131b9`: `Failed to read TokenCleanupIntervalSeconds. Err=0x%x`
- `0x18001323f`: `Failed to read DatabaseFolderPath config setting, using default. Err=0x%x`
- `0x180013193`: `TokenCleanupIntervalSeconds`

## pseudocode

```c
__int64 __fastcall DSConfig::Load(DSConfig *this)
{
  HKEY *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  LSTATUS v5; // ebx
  __int64 v6; // r8
  __int64 v7; // r9
  DSLogger *v8; // rax
  HRESULT v9; // ebx
  _WORD *v10; // rcx
  HKEY v11; // rdx
  __int64 v12; // rdx
  unsigned __int64 v13; // rcx
  int v14; // ebx
  __int64 v15; // r8
  __int64 v16; // r9
  DSLogger *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  LSTATUS v22; // r15d
  DSLogger *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  LSTATUS v28; // r15d
  DSLogger *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  LSTATUS v34; // r15d
  DSLogger *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  const unsigned __int16 *v40; // rax
  unsigned __int16 **v41; // r9
  char v42; // al
  DSLogger *v43; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-40h]
  PHKEY phkResulta; // [rsp+20h] [rbp-40h]
  PHKEY phkResultb; // [rsp+20h] [rbp-40h]
  PHKEY phkResultc; // [rsp+20h] [rbp-40h]
  __int64 v49; // [rsp+30h] [rbp-30h] BYREF
  PWSTR ppszPath; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v51[4]; // [rsp+40h] [rbp-20h] BYREF
  DWORD Type; // [rsp+98h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+48h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  v2 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\DataSharing", 0, 1u, v2);
  if ( v5 )
  {
    v8 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                       v4,
                       v3,
                       v6,
                       v7);
    LODWORD(phkResult) = v5;
    DSLogger::LogError(v8, L"DSConfig::Load", 0x30u, L"Failed to open registry. Err=0x%x", phkResult);
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            this,
                            L"8.0",
                            3) )
    {
      *((_DWORD *)this + 9) = 1296000;
      *((_DWORD *)this + 8) = 86400;
      *((_DWORD *)this + 10) = 86400;
      v9 = (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                              (char *)this + 48,
                              L"\\Data\\Users\\System\\AppData\\Local\\DataSharing\\Storage\\",
                              53) == 0
         ? 0x8007000E
         : 0;
      goto LABEL_24;
    }
    goto LABEL_3;
  }
  v10 = *(_WORD **)this;
  v11 = hKey;
  *((_QWORD *)this + 1) = *(_QWORD *)this;
  v51[0] = v11;
  *v10 = 0;
  v51[1] = L"Version";
  v51[2] = 0;
  v14 = tlx::_AppendFnImpl<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>,_lambda_01deaffebe426f0eea4c98c3933b105d_>(
          this,
          v51);
  if ( v14 < 0 || (v13 = (__int64)(*((_QWORD *)this + 1) - *(_QWORD *)this) >> 1, v13 <= 1) )
  {
    v17 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v13,
                        v12,
                        v15,
                        v16);
    LODWORD(phkResult) = v14;
    DSLogger::LogError(v17, L"DSConfig::Load", 0x3Cu, L"Fail to read Version. HR=0x%x", phkResult);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             this,
                             L"8.0",
                             3) )
    {
LABEL_3:
      v9 = -2147024882;
      goto LABEL_24;
    }
  }
  cbData = 4;
  Type = 0;
  v22 = RegQueryValueExW(hKey, L"ShortTermExpirySeconds", 0, &Type, (LPBYTE)this + 32, &cbData);
  if ( v22 || Type != 4 )
  {
    v23 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v19,
                        v18,
                        v20,
                        v21);
    LODWORD(phkResulta) = v22;
    DSLogger::LogError(v23, L"DSConfig::Load", 0x4Cu, L"Failed to read ShortTermExpirySeconds. Err=0x%x", phkResulta);
    *((_DWORD *)this + 8) = 86400;
  }
  cbData = 4;
  Type = 0;
  v28 = RegQueryValueExW(hKey, L"LongTermExpirySeconds", 0, &Type, (LPBYTE)this + 36, &cbData);
  if ( v28 || Type != 4 )
  {
    v29 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v25,
                        v24,
                        v26,
                        v27);
    LODWORD(phkResultb) = v28;
    DSLogger::LogError(v29, L"DSConfig::Load", 0x5Cu, L"Failed to read LongTermExpirySeconds. Err=0x%x", phkResultb);
    *((_DWORD *)this + 9) = 1296000;
  }
  cbData = 4;
  Type = 0;
  v34 = RegQueryValueExW(hKey, L"TokenCleanupIntervalSeconds", 0, &Type, (LPBYTE)this + 40, &cbData);
  if ( v34 || Type != 4 )
  {
    v35 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v31,
                        v30,
                        v32,
                        v33);
    LODWORD(phkResultc) = v34;
    DSLogger::LogError(
      v35,
      L"DSConfig::Load",
      0x6Cu,
      L"Failed to read TokenCleanupIntervalSeconds. Err=0x%x",
      phkResultc);
    *((_DWORD *)this + 10) = 86400;
  }
  v49 = 0;
  ppszPath = 0;
  v9 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath);
  if ( v9 < 0
    || (v40 = (const unsigned __int16 *)tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&void * LocalFree(void *),0>>(&v49),
        v9 = DSUtils::CombinePath(ppszPath, L"DataSharing\\Storage\\", v40, v41),
        v9 < 0) )
  {
    v43 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v37,
                        v36,
                        v38,
                        v39);
    LODWORD(phkResultc) = v9;
    DSLogger::LogWarning(
      v43,
      L"DSConfig::Load",
      0x81u,
      L"Failed to read DatabaseFolderPath config setting, using default. Err=0x%x",
      phkResultc);
    v42 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
            (char *)this + 48,
            L"\\Data\\Users\\System\\AppData\\Local\\DataSharing\\Storage\\",
            53);
  }
  else
  {
    v42 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
            (char *)this + 48,
            v49);
  }
  if ( !v42 )
    v9 = -2147024882;
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(&v49);
  tlx::unique_any<tlx::handle_traits<unsigned char *,void (*)(void *),&void CoTaskMemFree(void *),0>>::~unique_any<tlx::handle_traits<unsigned char *,void (*)(void *),&void CoTaskMemFree(void *),0>>(&ppszPath);
LABEL_24:
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180012f20  push    rbp
0x180012f22  push    rbx
0x180012f23  push    rdi
0x180012f24  push    r14
0x180012f26  push    r15
0x180012f28  mov     rbp, rsp
0x180012f2b  sub     rsp, 60h
0x180012f2f  mov     rdi, rcx
0x180012f32  mov     [rbp+hKey], 0
0x180012f3a  lea     rcx, [rbp+hKey]
0x180012f3e  mov     [rbp+cbData], 0
0x180012f45  mov     [rbp+Type], 0
0x180012f4c  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180012f51  mov     r9d, 1; samDesired
0x180012f57  mov     [rsp+60h+phkResult], rax; phkResult
0x180012f5c  xor     r8d, r8d; ulOptions
0x180012f5f  lea     rdx, SubKey; "Software\\Microsoft\\DataSharing"
0x180012f66  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012f6d  call    cs:__imp_RegOpenKeyExW
0x180012f73  mov     ebx, eax
0x180012f75  test    eax, eax
0x180012f77  jz      loc_180012FFF
0x180012f7d  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180012f82  lea     r9, aFailedToOpenRe; "Failed to open registry. Err=0x%x"
0x180012f89  mov     dword ptr [rsp+60h+phkResult], ebx
0x180012f8d  mov     r8d, 30h ; '0'; unsigned int
0x180012f93  lea     rdx, aDsconfigLoad; "DSConfig::Load"
0x180012f9a  mov     rcx, rax; this
0x180012f9d  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180012fa2  mov     r8d, 3
0x180012fa8  lea     rdx, a80; "8.0"
0x180012faf  mov     rcx, rdi
0x180012fb2  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180012fb7  test    al, al
0x180012fb9  jnz     short loc_180012FC5
0x180012fbb  mov     ebx, 8007000Eh
0x180012fc0  jmp     loc_180013290
0x180012fc5  mov     ebx, 15180h
0x180012fca  mov     dword ptr [rdi+24h], 13C680h
0x180012fd1  lea     rcx, [rdi+30h]
0x180012fd5  mov     [rdi+20h], ebx
0x180012fd8  mov     r8d, 35h ; '5'
0x180012fde  mov     [rdi+28h], ebx
0x180012fe1  lea     rdx, aDataUsersSyste; "\\Data\\Users\\System\\AppData\\Local\\"...
0x180012fe8  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180012fed  neg     al
0x180012fef  mov     ebx, 8007000Eh
0x180012ff4  sbb     ecx, ecx
0x180012ff6  not     ecx
0x180012ff8  and     ebx, ecx
0x180012ffa  jmp     loc_180013290
0x180012fff  mov     rcx, [rdi]
0x180013002  xor     eax, eax
0x180013004  mov     rdx, [rbp+hKey]
0x180013008  mov     [rdi+8], rcx
0x18001300c  mov     [rbp+var_20], rdx
0x180013010  lea     rdx, [rbp+var_20]
0x180013014  mov     [rcx], ax
0x180013017  lea     rax, aVersion; "Version"
0x18001301e  mov     rcx, rdi
0x180013021  mov     [rbp+var_18], rax
0x180013025  mov     [rbp+var_10], 0
0x18001302d  call    ??$_AppendFnImpl@GU?$char_traits@G@utl@@V?$allocator@G@2@V_lambda_01deaffebe426f0eea4c98c3933b105d_@@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@$$QEAV_lambda_01deaffebe426f0eea4c98c3933b105d_@@@Z; tlx::_AppendFnImpl<ushort,utl::char_traits<ushort>,utl::allocator<ushort>,_lambda_01deaffebe426f0eea4c98c3933b105d_>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,_lambda_01deaffebe426f0eea4c98c3933b105d_ &&)
0x180013032  mov     ebx, eax
0x180013034  test    eax, eax
0x180013036  js      short loc_180013048
0x180013038  mov     rcx, [rdi+8]
0x18001303c  sub     rcx, [rdi]
0x18001303f  sar     rcx, 1
0x180013042  cmp     rcx, 1
0x180013046  ja      short loc_18001308A
0x180013048  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001304d  lea     r9, aFailToReadVers; "Fail to read Version. HR=0x%x"
0x180013054  mov     dword ptr [rsp+60h+phkResult], ebx
0x180013058  mov     r8d, 3Ch ; '<'; unsigned int
0x18001305e  lea     rdx, aDsconfigLoad; "DSConfig::Load"
0x180013065  mov     rcx, rax; this
0x180013068  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001306d  mov     r8d, 3
0x180013073  lea     rdx, a80; "8.0"
0x18001307a  mov     rcx, rdi
0x18001307d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180013082  test    al, al
0x180013084  jz      loc_180012FBB
0x18001308a  mov     rcx, [rbp+hKey]; hKey
0x18001308e  lea     rax, [rbp+cbData]
0x180013092  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180013097  lea     r14, [rdi+20h]
0x18001309b  lea     r9, [rbp+Type]; lpType
0x18001309f  mov     [rsp+60h+phkResult], r14; lpData
0x1800130a4  xor     r8d, r8d; lpReserved
0x1800130a7  mov     [rbp+cbData], 4
0x1800130ae  lea     rdx, ValueName; "ShortTermExpirySeconds"
0x1800130b5  mov     [rbp+Type], 0
0x1800130bc  call    cs:__imp_RegQueryValueExW
0x1800130c2  mov     r15d, eax
0x1800130c5  mov     ebx, 15180h
0x1800130ca  test    eax, eax
0x1800130cc  jnz     short loc_1800130D4
0x1800130ce  cmp     [rbp+Type], 4
0x1800130d2  jz      short loc_1800130FD
0x1800130d4  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800130d9  lea     r9, aFailedToReadSh; "Failed to read ShortTermExpirySeconds. "...
0x1800130e0  mov     dword ptr [rsp+60h+phkResult], r15d
0x1800130e5  mov     r8d, 4Ch ; 'L'; unsigned int
0x1800130eb  lea     rdx, aDsconfigLoad; "DSConfig::Load"
0x1800130f2  mov     rcx, rax; this
0x1800130f5  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800130fa  mov     [r14], ebx
0x1800130fd  mov     rcx, [rbp+hKey]; hKey
0x180013101  lea     rax, [rbp+cbData]
0x180013105  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18001310a  lea     r14, [rdi+24h]
0x18001310e  lea     r9, [rbp+Type]; lpType
0x180013112  mov     [rsp+60h+phkResult], r14; lpData
0x180013117  xor     r8d, r8d; lpReserved
0x18001311a  mov     [rbp+cbData], 4
0x180013121  lea     rdx, aLongtermexpiry; "LongTermExpirySeconds"
0x180013128  mov     [rbp+Type], 0
0x18001312f  call    cs:__imp_RegQueryValueExW
0x180013135  mov     r15d, eax
0x180013138  test    eax, eax
0x18001313a  jnz     short loc_180013142
0x18001313c  cmp     [rbp+Type], 4
0x180013140  jz      short loc_18001316F
0x180013142  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180013147  lea     r9, aFailedToReadLo; "Failed to read LongTermExpirySeconds. E"...
0x18001314e  mov     dword ptr [rsp+60h+phkResult], r15d
0x180013153  mov     r8d, 5Ch ; '\'; unsigned int
0x180013159  lea     rdx, aDsconfigLoad; "DSConfig::Load"
0x180013160  mov     rcx, rax; this
0x180013163  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180013168  mov     dword ptr [r14], 13C680h
0x18001316f  mov     rcx, [rbp+hKey]; hKey
0x180013173  lea     rax, [rbp+cbData]
0x180013177  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18001317c  lea     r14, [rdi+28h]
0x180013180  lea     r9, [rbp+Type]; lpType
0x180013184  mov     [rsp+60h+phkResult], r14; lpData
0x180013189  xor     r8d, r8d; lpReserved
0x18001318c  mov     [rbp+cbData], 4
0x180013193  lea     rdx, aTokencleanupin; "TokenCleanupIntervalSeconds"
0x18001319a  mov     [rbp+Type], 0
0x1800131a1  call    cs:__imp_RegQueryValueExW
0x1800131a7  mov     r15d, eax
0x1800131aa  test    eax, eax
0x1800131ac  jnz     short loc_1800131B4
0x1800131ae  cmp     [rbp+Type], 4
0x1800131b2  jz      short loc_1800131DD
0x1800131b4  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x1800131b9  lea     r9, aFailedToReadTo; "Failed to read TokenCleanupIntervalSeco"...
0x1800131c0  mov     dword ptr [rsp+60h+phkResult], r15d
0x1800131c5  mov     r8d, 6Ch ; 'l'; unsigned int
0x1800131cb  lea     rdx, aDsconfigLoad; "DSConfig::Load"
0x1800131d2  mov     rcx, rax; this
0x1800131d5  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800131da  mov     [r14], ebx
0x1800131dd  lea     r9, [rbp+ppszPath]; ppszPath
0x1800131e1  mov     [rbp+var_30], 0
0x1800131e9  xor     r8d, r8d; hToken
0x1800131ec  mov     [rbp+ppszPath], 0
0x1800131f4  xor     edx, edx; dwFlags
0x1800131f6  lea     rcx, FOLDERID_LocalAppData; rfid
0x1800131fd  call    cs:__imp_SHGetKnownFolderPath
0x180013203  mov     ebx, eax
0x180013205  test    eax, eax
0x180013207  js      short loc_18001323A
0x180013209  lea     rcx, [rbp+var_30]
0x18001320d  call    ??$replace@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>> &)
0x180013212  mov     rcx, [rbp+ppszPath]; pszPathIn
0x180013216  lea     rdx, aDatasharingSto; "DataSharing\\Storage\\"
0x18001321d  mov     r8, rax; unsigned __int16 *
0x180013220  call    ?CombinePath@DSUtils@@YAJPEBG0PEAPEAG@Z; DSUtils::CombinePath(ushort const *,ushort const *,ushort * *)
0x180013225  mov     ebx, eax
0x180013227  test    eax, eax
0x180013229  js      short loc_18001323A
0x18001322b  mov     rdx, [rbp+var_30]
0x18001322f  lea     rcx, [rdi+30h]
0x180013233  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180013238  jmp     short loc_180013275
0x18001323a  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001323f  lea     r9, aFailedToReadDa; "Failed to read DatabaseFolderPath confi"...
0x180013246  mov     dword ptr [rsp+60h+phkResult], ebx
0x18001324a  mov     r8d, 81h; unsigned int
0x180013250  lea     rdx, aDsconfigLoad; "DSConfig::Load"
0x180013257  mov     rcx, rax; this
0x18001325a  call    ?LogWarning@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogWarning(ushort const *,ulong,ushort const *,...)
0x18001325f  lea     rcx, [rdi+30h]
0x180013263  mov     r8d, 35h ; '5'
0x180013269  lea     rdx, aDataUsersSyste; "\\Data\\Users\\System\\AppData\\Local\\"...
0x180013270  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180013275  test    al, al
0x180013277  jnz     short loc_18001327E
0x180013279  mov     ebx, 8007000Eh
0x18001327e  lea     rcx, [rbp+var_30]
0x180013282  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x180013287  lea     rcx, [rbp+ppszPath]
0x18001328b  call    ??1?$unique_any@U?$handle_traits@PEAEP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<uchar *,void (*)(void *),&CoTaskMemFree(void *),0>>::~unique_any<tlx::handle_traits<uchar *,void (*)(void *),&CoTaskMemFree(void *),0>>(void)
0x180013290  lea     rcx, [rbp+hKey]
0x180013294  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180013299  mov     eax, ebx
0x18001329b  add     rsp, 60h
0x18001329f  pop     r15
0x1800132a1  pop     r14
0x1800132a3  pop     rdi
0x1800132a4  pop     rbx
0x1800132a5  pop     rbp
0x1800132a6  retn
```
