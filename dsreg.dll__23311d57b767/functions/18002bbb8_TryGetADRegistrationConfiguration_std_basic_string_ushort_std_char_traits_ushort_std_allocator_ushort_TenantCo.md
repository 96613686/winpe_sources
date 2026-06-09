# TryGetADRegistrationConfiguration(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,TenantConfiguration &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002bbb8`
- end: `0x18002c1ca`
- name: `?TryGetADRegistrationConfiguration@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVTenantConfiguration@@AEAV12@@Z`
- size: `1554`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task`

## callers

- `0x18006e318`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x180012948`
- `0x18001378c`
- `0x180016b90`
- `0x18001e0f4`
- `0x18002b9b4`
- `0x18002ba70`
- `0x18002bbb8`
- `0x18002dd24`
- `0x18002de28`
- `0x1800382fc`
- `0x18003c408`
- `0x180043eb8`
- `0x180044300`
- `0x18004c490`
- `0x18006a270`
- `0x18006c144`
- `0x18006c4a4`
- `0x18007313c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002bf9f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c029`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c0b3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002bf9f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c029`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c0b3`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18002c18b`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18002c18b`

## string_xrefs

- `0x18002bbf7`: `TryGetADRegistrationConfiguration`
- `0x18002bc95`: `TryGetADRegistrationConfiguration`
- `0x18002bcff`: `TryGetADRegistrationConfiguration`
- `0x18002bd87`: `TryGetADRegistrationConfiguration`
- `0x18002be25`: `TryGetADRegistrationConfiguration`
- `0x18002be82`: `TryGetADRegistrationConfiguration`
- `0x18002bf65`: `TryGetADRegistrationConfiguration`
- `0x18002c113`: `TryGetADRegistrationConfiguration`
- `0x18002c080`: `%s: read tenant id %s`
- `0x18002bff6`: `%s: read tenant name %s`
- `0x18002c10c`: `%s: read enterprise DRS name %s`
- `0x18002bd4e`: `configurationNamingContext`
- `0x18002bdd6`: `CN=62a0ff2e-97b9-4513-943f-0d221bd30080,CN=Device Registration Configuration,CN=services,`
- `0x18002bf6c`: `%s: read keywords found value %s`
- `0x18002bf98`: `azureADName:`
- `0x18002c022`: `azureADId:`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall TryGetADRegistrationConfiguration(unsigned __int16 *a1, _QWORD *a2, _QWORD *a3)
{
  unsigned __int16 *v5; // r15
  int v6; // r13d
  LdapSearchResult *v7; // rax
  LdapSearchResult *v8; // rsi
  LdapServer *v9; // rax
  unsigned int v10; // edx
  LdapServer *v11; // rdi
  const unsigned __int16 *v12; // rdx
  int v13; // eax
  unsigned __int16 **v14; // rdx
  unsigned int v15; // ebx
  int RootDSE; // eax
  __int64 v17; // rax
  int StringValues; // eax
  unsigned int v19; // esi
  _QWORD *v20; // r8
  const unsigned __int16 *v21; // r8
  const unsigned __int16 *v22; // r9
  const unsigned __int16 *v23; // rdx
  int AttributeValues; // eax
  _WORD **v25; // rdi
  _WORD *v26; // rcx
  _WORD *v27; // rcx
  _WORD *v28; // rcx
  _QWORD *v29; // r8
  _QWORD *v30; // rcx
  _QWORD *v31; // r8
  _QWORD *v32; // rcx
  _WORD *v33; // r8
  _QWORD *v34; // rcx
  _QWORD *v35; // r8
  unsigned int v36; // edx
  const char *v38; // r8
  signed int LastError; // eax
  unsigned int v40[2]; // [rsp+30h] [rbp-F8h] BYREF
  void *v41; // [rsp+38h] [rbp-F0h] BYREF
  __int64 v42; // [rsp+40h] [rbp-E8h]
  __int64 v43; // [rsp+48h] [rbp-E0h]
  LdapSearchResult *v44; // [rsp+50h] [rbp-D8h] BYREF
  PWCHAR *vals; // [rsp+58h] [rbp-D0h] BYREF
  LdapServer *v46; // [rsp+60h] [rbp-C8h] BYREF
  void **v47; // [rsp+68h] [rbp-C0h] BYREF
  const char *v48; // [rsp+70h] [rbp-B8h] BYREF
  unsigned __int16 *v49; // [rsp+80h] [rbp-A8h]
  _QWORD v50[3]; // [rsp+88h] [rbp-A0h] BYREF
  unsigned __int64 v51; // [rsp+A0h] [rbp-88h]
  _BYTE v52[32]; // [rsp+A8h] [rbp-80h] BYREF
  _QWORD Src[3]; // [rsp+C8h] [rbp-60h] BYREF
  unsigned __int64 v54; // [rsp+E0h] [rbp-48h]

  v5 = a1;
  v49 = a1;
  v6 = 0;
  v40[0] = 0;
  Logger::TraceVerbose((wchar_t *)L"%s started", L"TryGetADRegistrationConfiguration");
  v46 = 0;
  vals = 0;
  std::vector<DsrHKeyUserHandle>::vector<DsrHKeyUserHandle>(&v41);
  try
  {
    v7 = (LdapSearchResult *)operator new(0x10u);
    v8 = v7;
    if ( v7 )
    {
      *(_QWORD *)v7 = 0;
      *((_QWORD *)v7 + 1) = 0;
    }
    else
    {
      v8 = 0;
    }
    v44 = v8;
    v9 = (LdapServer *)operator new(8u);
    v11 = v9;
    if ( v9 )
      *(_QWORD *)v9 = 0;
    else
      v11 = 0;
    *(_QWORD *)v40 = 0;
    v46 = v11;
    std::unique_ptr<LdapServer>::~unique_ptr<LdapServer>((LdapServer **)v40, v10);
    if ( *((_QWORD *)v5 + 3) <= 7u )
      v12 = v5;
    else
      v12 = *(const unsigned __int16 **)v5;
    v13 = LdapServer::Connect(v11, v12);
    v15 = v13;
    if ( v13 >= 0 )
    {
      RootDSE = LdapServer::GetRootDSE(v11, v14, v8);
      v15 = RootDSE;
      if ( RootDSE >= 0 )
      {
        v17 = std::wstring::wstring((__int64)v52, (__int64)L"configurationNamingContext");
        StringValues = LdapServer::GetStringValues(v11, v8, v17, &v41);
        v15 = StringValues;
        v19 = 0;
        if ( StringValues >= 0 )
        {
          std::wstring::wstring(
            (__int64)Src,
            (__int64)L"CN=62a0ff2e-97b9-4513-943f-0d221bd30080,CN=Device Registration Configuration,CN=services,");
          std::wstring::_Append<unsigned short>(Src);
          v20 = Src;
          if ( v54 > 7 )
            v20 = (_QWORD *)Src[0];
          Logger::TraceInformation(L"%s: DRS confg dn %s", L"TryGetADRegistrationConfiguration", v20);
          v40[0] = 0;
          v23 = (const unsigned __int16 *)Src;
          if ( v54 > 7 )
            v23 = (const unsigned __int16 *)Src[0];
          AttributeValues = LdapServer::GetAttributeValues(v11, v23, v21, v22, v40, &vals);
          v15 = AttributeValues;
          if ( AttributeValues >= 0 )
          {
            v25 = (_WORD **)(a2 + 4);
            a2[6] = 0;
            if ( a2[7] <= 7u )
              v26 = a2 + 4;
            else
              v26 = *v25;
            *v26 = 0;
            a2[2] = 0;
            if ( a2[3] <= 7u )
              v27 = a2;
            else
              v27 = (_WORD *)*a2;
            *v27 = 0;
            a3[2] = 0;
            if ( a3[3] <= 7u )
              v28 = a3;
            else
              v28 = (_WORD *)*a3;
            *v28 = 0;
            while ( v19 < v40[0] )
            {
              std::wstring::wstring((__int64)v50, (__int64)vals[v19]);
              v29 = v50;
              if ( v51 > 7 )
                v29 = (_QWORD *)v50[0];
              Logger::TraceInformation(L"%s: read keywords found value %s", L"TryGetADRegistrationConfiguration", v29);
              v30 = v50;
              if ( v51 > 7 )
                v30 = (_QWORD *)v50[0];
              if ( (unsigned int)_o__wcsnicmp(v30, L"azureADName:", 12) )
              {
                v32 = v50;
                if ( v51 > 7 )
                  v32 = (_QWORD *)v50[0];
                if ( (unsigned int)_o__wcsnicmp(v32, L"azureADId:", 10) )
                {
                  v34 = v50;
                  if ( v51 > 7 )
                    v34 = (_QWORD *)v50[0];
                  if ( !(unsigned int)_o__wcsnicmp(v34, L"enterpriseDrsName:", 18) )
                  {
                    std::wstring::wstring(v52, v50, 18, -1);
                    v6 |= 4u;
                    std::wstring::operator=((__int64)a3, (__int64)v52);
                    std::wstring::_Tidy_deallocate((__int64)v52);
                    if ( a3[3] <= 7u )
                      v35 = a3;
                    else
                      v35 = (_QWORD *)*a3;
                    Logger::TraceInformation(
                      L"%s: read enterprise DRS name %s",
                      L"TryGetADRegistrationConfiguration",
                      v35);
                  }
                }
                else
                {
                  std::wstring::wstring(v52, v50, 10, -1);
                  v6 |= 2u;
                  std::wstring::operator=((__int64)(a2 + 4), (__int64)v52);
                  std::wstring::_Tidy_deallocate((__int64)v52);
                  if ( a2[7] <= 7u )
                    v33 = a2 + 4;
                  else
                    v33 = *v25;
                  Logger::TraceInformation(L"%s: read tenant id %s", L"TryGetADRegistrationConfiguration", v33);
                }
              }
              else
              {
                std::wstring::wstring(v52, v50, 12, -1);
                v6 |= 1u;
                std::wstring::operator=((__int64)a2, (__int64)v52);
                std::wstring::_Tidy_deallocate((__int64)v52);
                if ( a2[3] <= 7u )
                  v31 = a2;
                else
                  v31 = (_QWORD *)*a2;
                Logger::TraceInformation(L"%s: read tenant name %s", L"TryGetADRegistrationConfiguration", v31);
              }
              std::wstring::_Tidy_deallocate((__int64)v50);
              ++v19;
            }
            std::wstring::_Tidy_deallocate((__int64)Src);
            std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(&v44);
            if ( v41 )
            {
              std::_Destroy_range<std::allocator<std::wstring>>(v41, v42);
              std::_Deallocate<16>(v41, (v43 - (_QWORD)v41) & 0xFFFFFFFFFFFFFFE0uLL);
            }
          }
          else
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"TryGetADRegistrationConfiguration",
              L"LdapServer::GetAttributeValues",
              (unsigned int)AttributeValues);
            std::wstring::_Tidy_deallocate((__int64)Src);
            std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(&v44);
            if ( v41 )
            {
              std::_Destroy_range<std::allocator<std::wstring>>(v41, v42);
              std::_Deallocate<16>(v41, (v43 - (_QWORD)v41) & 0xFFFFFFFFFFFFFFE0uLL);
            }
          }
        }
        else
        {
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"TryGetADRegistrationConfiguration",
            L"LdapServer::GetStringValues",
            (unsigned int)StringValues);
          std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(&v44);
          if ( v41 )
          {
            std::_Destroy_range<std::allocator<std::wstring>>(v41, v42);
            std::_Deallocate<16>(v41, (v43 - (_QWORD)v41) & 0xFFFFFFFFFFFFFFE0uLL);
          }
        }
      }
      else
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"TryGetADRegistrationConfiguration",
          L"LdapServer::GetRootDSE",
          (unsigned int)RootDSE);
        std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(&v44);
        if ( v41 )
        {
          std::_Destroy_range<std::allocator<std::wstring>>(v41, v42);
          std::_Deallocate<16>(v41, (v43 - (_QWORD)v41) & 0xFFFFFFFFFFFFFFE0uLL);
        }
      }
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"TryGetADRegistrationConfiguration",
        L"LdapServer::Connect",
        (unsigned int)v13);
      std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(&v44);
      if ( v41 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v41, v42);
        std::_Deallocate<16>(v41, (v43 - (_QWORD)v41) & 0xFFFFFFFFFFFFFFE0uLL);
      }
    }
  }
  catch ( std::exception v47 )
  {
    v38 = "Unknown exception";
    if ( v48 )
      v38 = v48;
    Logger::TraceError(L"%s: unhandled exception: %hs", L"TryGetADRegistrationConfiguration", v38);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2145648611;
    v40[0] = LastError;
    v47 = &std::exception::`vftable';
    o___std_exception_destroy_0(&v48);
    v15 = v40[0];
    v5 = v49;
  }
  ldap_value_freeW(vals);
  std::unique_ptr<LdapServer>::~unique_ptr<LdapServer>(&v46, v36);
  std::wstring::_Tidy_deallocate((__int64)v5);
  return v15;
}

```

## disassembly

```asm
0x18002bbb8  push    rbx
0x18002bbba  push    rsi
0x18002bbbb  push    rdi
0x18002bbbc  push    r12
0x18002bbbe  push    r13
0x18002bbc0  push    r14
0x18002bbc2  push    r15
0x18002bbc4  sub     rsp, 0F0h
0x18002bbcb  mov     rax, cs:__security_cookie
0x18002bbd2  xor     rax, rsp
0x18002bbd5  mov     [rsp+128h+var_40], rax
0x18002bbdd  mov     r12, r8
0x18002bbe0  mov     r14, rdx
0x18002bbe3  mov     r15, rcx
0x18002bbe6  mov     [rsp+128h+var_A8], rcx
0x18002bbee  xor     ebx, ebx
0x18002bbf0  mov     r13d, ebx
0x18002bbf3  mov     [rsp+128h+var_F8], ebx
0x18002bbf7  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18002bbfe  lea     rcx, aSStarted; "%s started"
0x18002bc05  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18002bc0a  mov     [rsp+128h+var_C8], rbx
0x18002bc0f  mov     [rsp+128h+vals], rbx
0x18002bc14  lea     rcx, [rsp+128h+var_F0]; void *
0x18002bc19  call    ??0?$vector@VDsrHKeyUserHandle@@V?$allocator@VDsrHKeyUserHandle@@@std@@@std@@QEAA@XZ; std::vector<DsrHKeyUserHandle>::vector<DsrHKeyUserHandle>(void)
0x18002bc1e  nop
0x18002bc1f  lea     ecx, [rbx+10h]; Size
0x18002bc22  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bc27  mov     rsi, rax
0x18002bc2a  test    rax, rax
0x18002bc2d  jz      short loc_18002BC38
0x18002bc2f  mov     [rax], rbx
0x18002bc32  mov     [rax+8], rbx
0x18002bc36  jmp     short loc_18002BC3B
0x18002bc38  mov     rsi, rbx
0x18002bc3b  mov     [rsp+128h+var_D8], rsi
0x18002bc40  mov     ecx, 8; Size
0x18002bc45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bc4a  mov     rdi, rax
0x18002bc4d  test    rax, rax
0x18002bc50  jz      short loc_18002BC57
0x18002bc52  mov     [rax], rbx
0x18002bc55  jmp     short loc_18002BC5A
0x18002bc57  mov     rdi, rbx
0x18002bc5a  mov     qword ptr [rsp+128h+var_F8], rbx
0x18002bc5f  mov     [rsp+128h+var_C8], rdi
0x18002bc64  lea     rcx, [rsp+128h+var_F8]
0x18002bc69  call    ??1?$unique_ptr@VLdapServer@@U?$default_delete@VLdapServer@@@std@@@std@@QEAA@XZ; std::unique_ptr<LdapServer>::~unique_ptr<LdapServer>(void)
0x18002bc6e  cmp     qword ptr [r15+18h], 7
0x18002bc73  jbe     short loc_18002BC7A
0x18002bc75  mov     rdx, [r15]
0x18002bc78  jmp     short loc_18002BC7D
0x18002bc7a  mov     rdx, r15; unsigned __int16 *
0x18002bc7d  mov     rcx, rdi; this
0x18002bc80  call    ?Connect@LdapServer@@QEAAJPEBG@Z; LdapServer::Connect(ushort const *)
0x18002bc85  mov     ebx, eax
0x18002bc87  test    eax, eax
0x18002bc89  jns     short loc_18002BCE4
0x18002bc8b  mov     r9d, eax
0x18002bc8e  lea     r8, aLdapserverConn; "LdapServer::Connect"
0x18002bc95  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18002bc9c  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18002bca3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002bca8  nop
0x18002bca9  lea     rcx, [rsp+128h+var_D8]
0x18002bcae  call    ??1?$unique_ptr@VLdapSearchResult@@U?$default_delete@VLdapSearchResult@@@std@@@std@@QEAA@XZ; std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(void)
0x18002bcb3  nop
0x18002bcb4  mov     rcx, [rsp+128h+var_F0]
0x18002bcb9  test    rcx, rcx
0x18002bcbc  jz      short loc_18002BCDF
0x18002bcbe  mov     rdx, [rsp+128h+var_E8]
0x18002bcc3  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002bcc8  mov     rcx, [rsp+128h+var_F0]
0x18002bccd  mov     rdx, [rsp+128h+var_E0]
0x18002bcd2  sub     rdx, rcx
0x18002bcd5  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002bcd9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002bcde  nop
0x18002bcdf  jmp     loc_18002C186
0x18002bce4  mov     r8, rsi; struct LdapSearchResult *
0x18002bce7  mov     rcx, rdi; this
0x18002bcea  call    ?GetRootDSE@LdapServer@@QEAAJPEAPEAGPEAVLdapSearchResult@@@Z; LdapServer::GetRootDSE(ushort * *,LdapSearchResult *)
0x18002bcef  mov     ebx, eax
0x18002bcf1  test    eax, eax
0x18002bcf3  jns     short loc_18002BD4E
0x18002bcf5  mov     r9d, eax
0x18002bcf8  lea     r8, aLdapserverGetr; "LdapServer::GetRootDSE"
0x18002bcff  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18002bd06  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18002bd0d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002bd12  nop
0x18002bd13  lea     rcx, [rsp+128h+var_D8]
0x18002bd18  call    ??1?$unique_ptr@VLdapSearchResult@@U?$default_delete@VLdapSearchResult@@@std@@@std@@QEAA@XZ; std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(void)
0x18002bd1d  nop
0x18002bd1e  mov     rcx, [rsp+128h+var_F0]
0x18002bd23  test    rcx, rcx
0x18002bd26  jz      short loc_18002BD49
0x18002bd28  mov     rdx, [rsp+128h+var_E8]
0x18002bd2d  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002bd32  mov     rcx, [rsp+128h+var_F0]
0x18002bd37  mov     rdx, [rsp+128h+var_E0]
0x18002bd3c  sub     rdx, rcx
0x18002bd3f  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002bd43  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002bd48  nop
0x18002bd49  jmp     loc_18002C186
0x18002bd4e  lea     rdx, aConfigurationn; "configurationNamingContext"
0x18002bd55  lea     rcx, [rsp+128h+var_80]
0x18002bd5d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002bd62  lea     r9, [rsp+128h+var_F0]
0x18002bd67  mov     r8, rax
0x18002bd6a  mov     rdx, rsi
0x18002bd6d  mov     rcx, rdi
0x18002bd70  call    ?GetStringValues@LdapServer@@QEAAJPEAVLdapSearchResult@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z; LdapServer::GetStringValues(LdapSearchResult *,std::wstring,std::vector<std::wstring> &)
0x18002bd75  mov     ebx, eax
0x18002bd77  xor     esi, esi
0x18002bd79  test    eax, eax
0x18002bd7b  jns     short loc_18002BDD6
0x18002bd7d  mov     r9d, eax
0x18002bd80  lea     r8, aLdapserverGets_0; "LdapServer::GetStringValues"
0x18002bd87  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18002bd8e  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18002bd95  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002bd9a  nop
0x18002bd9b  lea     rcx, [rsp+128h+var_D8]
0x18002bda0  call    ??1?$unique_ptr@VLdapSearchResult@@U?$default_delete@VLdapSearchResult@@@std@@@std@@QEAA@XZ; std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(void)
0x18002bda5  nop
0x18002bda6  mov     rcx, [rsp+128h+var_F0]
0x18002bdab  test    rcx, rcx
0x18002bdae  jz      short loc_18002BDD1
0x18002bdb0  mov     rdx, [rsp+128h+var_E8]
0x18002bdb5  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002bdba  mov     rcx, [rsp+128h+var_F0]
0x18002bdbf  mov     rdx, [rsp+128h+var_E0]
0x18002bdc4  sub     rdx, rcx
0x18002bdc7  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002bdcb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002bdd0  nop
0x18002bdd1  jmp     loc_18002C186
0x18002bdd6  lea     rdx, aCn62a0ff2e97b9; "CN=62a0ff2e-97b9-4513-943f-0d221bd30080"...
0x18002bddd  lea     rcx, [rsp+128h+Src]
0x18002bde5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002bdea  nop
0x18002bdeb  mov     rdx, [rsp+128h+var_F0]
0x18002bdf0  mov     r8, [rdx+10h]
0x18002bdf4  cmp     qword ptr [rdx+18h], 7
0x18002bdf9  jbe     short loc_18002BDFE
0x18002bdfb  mov     rdx, [rdx]
0x18002bdfe  lea     rcx, [rsp+128h+Src]; Src
0x18002be06  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002be0b  lea     r8, [rsp+128h+Src]
0x18002be13  cmp     [rsp+128h+var_48], 7
0x18002be1c  cmova   r8, [rsp+128h+Src]
0x18002be25  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18002be2c  lea     rcx, aSDrsConfgDnS; "%s: DRS confg dn %s"
0x18002be33  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18002be38  mov     [rsp+128h+var_F8], esi
0x18002be3c  lea     rdx, [rsp+128h+Src]
0x18002be44  cmp     [rsp+128h+var_48], 7
0x18002be4d  cmova   rdx, [rsp+128h+Src]; unsigned __int16 *
0x18002be56  lea     rax, [rsp+128h+vals]
0x18002be5b  mov     [rsp+128h+var_100], rax; unsigned __int16 ***
0x18002be60  lea     rax, [rsp+128h+var_F8]
0x18002be65  mov     [rsp+128h+var_108], rax; unsigned int *
0x18002be6a  mov     rcx, rdi; this
0x18002be6d  call    ?GetAttributeValues@LdapServer@@QEAAJPEBG00PEAKPEAPEAPEAG@Z; LdapServer::GetAttributeValues(ushort const *,ushort const *,ushort const *,ulong *,ushort * * *)
0x18002be72  mov     ebx, eax
0x18002be74  test    eax, eax
0x18002be76  jns     short loc_18002BEDF
0x18002be78  mov     r9d, eax
0x18002be7b  lea     r8, aLdapserverGeta; "LdapServer::GetAttributeValues"
0x18002be82  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18002be89  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18002be90  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002be95  nop
0x18002be96  lea     rcx, [rsp+128h+Src]
0x18002be9e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002bea3  nop
0x18002bea4  lea     rcx, [rsp+128h+var_D8]
0x18002bea9  call    ??1?$unique_ptr@VLdapSearchResult@@U?$default_delete@VLdapSearchResult@@@std@@@std@@QEAA@XZ; std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(void)
0x18002beae  nop
0x18002beaf  mov     rcx, [rsp+128h+var_F0]
0x18002beb4  test    rcx, rcx
0x18002beb7  jz      short loc_18002BEDA
0x18002beb9  mov     rdx, [rsp+128h+var_E8]
0x18002bebe  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002bec3  mov     rcx, [rsp+128h+var_F0]
0x18002bec8  mov     rdx, [rsp+128h+var_E0]
0x18002becd  sub     rdx, rcx
0x18002bed0  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002bed4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002bed9  nop
0x18002beda  jmp     loc_18002C186
0x18002bedf  lea     rdi, [r14+20h]
0x18002bee3  mov     [rdi+10h], rsi
0x18002bee7  cmp     qword ptr [rdi+18h], 7
0x18002beec  jbe     short loc_18002BEF3
0x18002beee  mov     rcx, [rdi]
0x18002bef1  jmp     short loc_18002BEF6
0x18002bef3  mov     rcx, rdi
0x18002bef6  mov     [rcx], si
0x18002bef9  mov     [r14+10h], rsi
0x18002befd  cmp     qword ptr [r14+18h], 7
0x18002bf02  jbe     short loc_18002BF09
0x18002bf04  mov     rcx, [r14]
0x18002bf07  jmp     short loc_18002BF0C
0x18002bf09  mov     rcx, r14
0x18002bf0c  mov     [rcx], si
0x18002bf0f  mov     [r12+10h], rsi
0x18002bf14  cmp     qword ptr [r12+18h], 7
0x18002bf1a  jbe     short loc_18002BF22
0x18002bf1c  mov     rcx, [r12]
0x18002bf20  jmp     short loc_18002BF25
0x18002bf22  mov     rcx, r12
0x18002bf25  mov     [rcx], si
0x18002bf28  cmp     esi, [rsp+128h+var_F8]
0x18002bf2c  jnb     loc_18002C134
0x18002bf32  mov     eax, esi
0x18002bf34  mov     rdx, [rsp+128h+vals]
0x18002bf39  mov     rdx, [rdx+rax*8]
0x18002bf3d  lea     rcx, [rsp+128h+var_A0]
0x18002bf45  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002bf4a  nop
0x18002bf4b  lea     r8, [rsp+128h+var_A0]
0x18002bf53  cmp     [rsp+128h+var_88], 7
0x18002bf5c  cmova   r8, [rsp+128h+var_A0]
0x18002bf65  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18002bf6c  lea     rcx, aSReadKeywordsF; "%s: read keywords found value %s"
0x18002bf73  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18002bf78  lea     rcx, [rsp+128h+var_A0]
0x18002bf80  cmp     [rsp+128h+var_88], 7
0x18002bf89  cmova   rcx, [rsp+128h+var_A0]
0x18002bf92  mov     r8d, 0Ch
0x18002bf98  lea     rdx, aAzureadname; "azureADName:"
0x18002bf9f  call    cs:__imp__o__wcsnicmp
0x18002bfa5  test    eax, eax
0x18002bfa7  jnz     short loc_18002C002
0x18002bfa9  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002bfad  lea     r8d, [rax+0Ch]
0x18002bfb1  lea     rdx, [rsp+128h+var_A0]
0x18002bfb9  lea     rcx, [rsp+128h+var_80]
0x18002bfc1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x18002bfc6  or      r13d, 1
0x18002bfca  lea     rdx, [rsp+128h+var_80]
0x18002bfd2  mov     rcx, r14
0x18002bfd5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002bfda  lea     rcx, [rsp+128h+var_80]
0x18002bfe2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002bfe7  cmp     qword ptr [r14+18h], 7
0x18002bfec  jbe     short loc_18002BFF3
0x18002bfee  mov     r8, [r14]
0x18002bff1  jmp     short loc_18002BFF6
0x18002bff3  mov     r8, r14
0x18002bff6  lea     rcx, aSReadTenantNam; "%s: read tenant name %s"
0x18002bffd  jmp     loc_18002C113
0x18002c002  lea     rcx, [rsp+128h+var_A0]
0x18002c00a  cmp     [rsp+128h+var_88], 7
0x18002c013  cmova   rcx, [rsp+128h+var_A0]
0x18002c01c  mov     r8d, 0Ah
0x18002c022  lea     rdx, aAzureadid; "azureADId:"
0x18002c029  call    cs:__imp__o__wcsnicmp
0x18002c02f  test    eax, eax
0x18002c031  jnz     short loc_18002C08C
0x18002c033  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002c037  lea     r8d, [rax+0Ah]
0x18002c03b  lea     rdx, [rsp+128h+var_A0]
0x18002c043  lea     rcx, [rsp+128h+var_80]
0x18002c04b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x18002c050  or      r13d, 2
0x18002c054  lea     rdx, [rsp+128h+var_80]
0x18002c05c  mov     rcx, rdi
0x18002c05f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c064  lea     rcx, [rsp+128h+var_80]
0x18002c06c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c071  cmp     qword ptr [r14+38h], 7
0x18002c076  jbe     short loc_18002C07D
0x18002c078  mov     r8, [rdi]
0x18002c07b  jmp     short loc_18002C080
0x18002c07d  mov     r8, rdi
0x18002c080  lea     rcx, aSReadTenantIdS; "%s: read tenant id %s"
0x18002c087  jmp     loc_18002C113
0x18002c08c  lea     rcx, [rsp+128h+var_A0]
0x18002c094  cmp     [rsp+128h+var_88], 7
0x18002c09d  cmova   rcx, [rsp+128h+var_A0]
0x18002c0a6  mov     r8d, 12h
0x18002c0ac  lea     rdx, aEnterprisedrsn_0; "enterpriseDrsName:"
0x18002c0b3  call    cs:__imp__o__wcsnicmp
0x18002c0b9  test    eax, eax
0x18002c0bb  jnz     short loc_18002C120
0x18002c0bd  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002c0c1  lea     r8d, [rax+12h]
0x18002c0c5  lea     rdx, [rsp+128h+var_A0]
0x18002c0cd  lea     rcx, [rsp+128h+var_80]
0x18002c0d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x18002c0da  or      r13d, 4
0x18002c0de  lea     rdx, [rsp+128h+var_80]
0x18002c0e6  mov     rcx, r12
0x18002c0e9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c0ee  lea     rcx, [rsp+128h+var_80]
0x18002c0f6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```
