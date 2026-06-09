# LdapGetBindings

- ea: `0x180019b00`
- end: `0x180019fff`
- name: `LdapGetBindings`
- size: `1279`
- prototype: `__int64 __usercall@<rax>(PWSTR HostName@<rcx>, ULONG PortNumber@<edx>, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800196e0`
- `0x18001d698`

## callees

- `0x1800013fc`
- `0x18000a990`
- `0x180011060`
- `0x180019b00`
- `0x18001a0a4`
- `0x18001a440`
- `0x18001a574`
- `0x18001ab2c`
- `0x18001ac64`
- `0x18002007c`
- `0x18002656a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019d62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019fd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019d62`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019fd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019c05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019c05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019b93`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019b93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019bcf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019bcf`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180019eed`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180019f4e`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180019f79`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180019eed`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180019f4e`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180019f79`
- `WLDAP32!__imp_ldap_connect` at `0x180019dac`
- `WLDAP32!__imp_ldap_connect` at `0x180019ddf`
- `WLDAP32!__imp_ldap_connect` at `0x180019dac`
- `WLDAP32!__imp_ldap_connect` at `0x180019ddf`
- `WLDAP32!__imp_ldap_get_option` at `0x180019e35`
- `WLDAP32!__imp_ldap_get_option` at `0x180019e35`
- `WLDAP32!__imp_ldap_initW` at `0x180019c7b`
- `WLDAP32!__imp_ldap_initW` at `0x180019c7b`
- `WLDAP32!__imp_ldap_set_option` at `0x180019ca0`
- `WLDAP32!__imp_ldap_set_option` at `0x180019ceb`
- `WLDAP32!__imp_ldap_set_option` at `0x180019cfd`
- `WLDAP32!__imp_ldap_set_option` at `0x180019d19`
- `WLDAP32!__imp_ldap_set_option` at `0x180019d91`
- `WLDAP32!__imp_ldap_set_option` at `0x180019dcf`
- `WLDAP32!__imp_ldap_set_option` at `0x180019e78`
- `WLDAP32!__imp_ldap_set_option` at `0x180019f2e`
- `WLDAP32!__imp_ldap_set_option` at `0x180019f64`
- `WLDAP32!__imp_ldap_set_option` at `0x180019ca0`
- `WLDAP32!__imp_ldap_set_option` at `0x180019ceb`
- `WLDAP32!__imp_ldap_set_option` at `0x180019cfd`
- `WLDAP32!__imp_ldap_set_option` at `0x180019d19`
- `WLDAP32!__imp_ldap_set_option` at `0x180019d91`
- `WLDAP32!__imp_ldap_set_option` at `0x180019dcf`
- `WLDAP32!__imp_ldap_set_option` at `0x180019e78`
- `WLDAP32!__imp_ldap_set_option` at `0x180019f2e`
- `WLDAP32!__imp_ldap_set_option` at `0x180019f64`

## string_xrefs

- `0x180019c25`: `Software\Microsoft\Cryptography\OID\EncodingType 0\CertDllCreateCertificateChainEngine\Config`
- `0x180019b6e`: `Software\Policies\Microsoft\SystemCertificates\ChainEngine\Config`

## pseudocode

```c
__int64 __fastcall LdapGetBindings(
        PWSTR HostName,
        ULONG PortNumber,
        int a3,
        char a4,
        unsigned int a5,
        __int64 a6,
        LDAP **a7)
{
  struct l_timeval *v7; // r15
  unsigned int v11; // esi
  LSTATUS v12; // ebx
  unsigned int v13; // r14d
  int v14; // eax
  DWORD LastError; // esi
  LDAP *v16; // rax
  LDAP *v17; // rdi
  unsigned int v18; // edx
  ULONG option; // ebx
  const wchar_t *v20; // rcx
  ULONG v21; // eax
  unsigned int v23; // eax
  HLOCAL v24; // r15
  __int64 v25; // rsi
  WCHAR *v26; // rax
  DWORD v27; // eax
  DWORD v28; // ebx
  __int64 v29; // rcx
  __int128 *v30; // rax
  unsigned int outvalue; // [rsp+30h] [rbp-C1h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-BDh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-B9h] BYREF
  unsigned int v34; // [rsp+3Ch] [rbp-B5h] BYREF
  DWORD Type; // [rsp+40h] [rbp-B1h] BYREF
  int v36; // [rsp+44h] [rbp-ADh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-A9h] BYREF
  __int64 v38; // [rsp+50h] [rbp-A1h] BYREF
  __int128 v39; // [rsp+58h] [rbp-99h] BYREF
  __int64 v40; // [rsp+68h] [rbp-89h]
  __int128 v41; // [rsp+70h] [rbp-81h] BYREF
  HLOCAL hMem[2]; // [rsp+80h] [rbp-71h]
  __int128 v43; // [rsp+90h] [rbp-61h]
  WCHAR cred[2]; // [rsp+A0h] [rbp-51h] BYREF
  int v45; // [rsp+A4h] [rbp-4Dh]
  __int64 v46; // [rsp+A8h] [rbp-49h]
  int v47; // [rsp+B0h] [rbp-41h]
  HLOCAL v48; // [rsp+B8h] [rbp-39h]
  int v49; // [rsp+C0h] [rbp-31h]
  __int128 v50; // [rsp+C8h] [rbp-29h]
  const wchar_t *v51; // [rsp+D8h] [rbp-19h]
  int v52; // [rsp+E0h] [rbp-11h]

  v7 = 0;
  outvalue = 0;
  v36 = 0;
  v41 = 0;
  *(_OWORD *)hMem = 0;
  v43 = 0;
  memset_0(cred, 0, 0x48u);
  v38 = 0;
  v34 = 0;
  Type = 0;
  cbData = 0;
  v11 = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  v12 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\SystemCertificates\\ChainEngine\\Config",
          0,
          0x20019u,
          &hKey);
  if ( !v12 )
  {
    cbData = 4;
    v12 = RegQueryValueExW(hKey, L"DisableLDAPSignAndEncrypt", 0, &Type, Data, &cbData);
    if ( !v12 )
    {
      if ( Type == 4 && cbData == 4 )
      {
        v11 = *(_DWORD *)Data;
        v12 = 0;
        v34 = *(_DWORD *)Data;
      }
      else
      {
        v12 = 13;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  v13 = 1;
  if ( v12 == 2 )
  {
    v14 = ReadRegDwordValue(
            L"Software\\Microsoft\\Cryptography\\OID\\EncodingType 0\\CertDllCreateCertificateChainEngine\\Config",
            L"DisableLDAPSignAndEncrypt",
            1,
            &v34);
    v11 = v34;
    if ( v14 == 2 )
      v11 = 0;
  }
  v39 = 0;
  LODWORD(v39) = 24;
  v40 = 0;
  if ( !(unsigned int)SchemeGetPasswordCredentialsW(a6, &v39, &v36)
    || (v16 = ldap_initW(HostName, PortNumber), (v17 = v16) == 0) )
  {
    LastError = GetLastError();
    goto LABEL_30;
  }
  if ( (a3 & 0x40000) != 0 && HostName )
    ldap_set_option(v16, 152, (const void *)1);
  if ( a5 )
  {
    if ( a5 >= 0x1388 )
      v18 = a5 / 0x3E8;
    else
      v18 = 5;
    *(_DWORD *)Data = 20 * v18;
    v38 = 20 * v18;
    v7 = (struct l_timeval *)&v38;
    ldap_set_option(v17, 4, Data);
  }
  ldap_set_option(v17, 17, (const void *)3);
  if ( !v11 || (a3 & 0x10000) != 0 )
  {
    option = ldap_set_option(v17, 149, (const void *)1);
    if ( option )
    {
      v20 = L"Call_ldap_set_option_LDAP_OPT_SIGN";
LABEL_27:
      CryptDiagAddActionWithLdapError(v20, v17, option);
      v21 = I_CryptNetLdapMapErrorToWin32(v17, option);
LABEL_28:
      LastError = v21;
LABEL_29:
      LdapFreeBindings(v17);
      goto LABEL_30;
    }
  }
  if ( !v11 )
  {
    option = ldap_set_option(v17, 150, (const void *)1);
    if ( option )
    {
      v20 = L"Call_ldap_set_option_LDAP_OPT_ENCRYPT";
      goto LABEL_27;
    }
  }
  option = ldap_connect(v17, v7);
  if ( option )
  {
    if ( HostName || (*(_DWORD *)Data = 1, ldap_set_option(v17, 61, Data)) || (option = ldap_connect(v17, v7)) != 0 )
    {
      v20 = L"Call_ldap_connect";
      goto LABEL_27;
    }
  }
  if ( !(unsigned int)SchemeGetAuthIdentityFromPasswordCredentialsW(&v39, &v41) )
  {
    v21 = GetLastError();
    goto LABEL_28;
  }
  v23 = 0;
  option = 7;
  outvalue = 0;
  if ( !v11 )
  {
    option = ldap_get_option(v17, 146, &outvalue);
    if ( option )
    {
      v20 = L"Call_ldap_get_option_LDAP_OPT_SSPI_FLAGS";
      goto LABEL_27;
    }
    v23 = outvalue;
  }
  v24 = hMem[0];
  if ( (a4 & 1) != 0 )
  {
    outvalue = v23 | 2;
    if ( !v11 )
    {
      option = ldap_set_option(v17, 146, &outvalue);
      if ( option )
        goto LABEL_52;
    }
    v46 = v41;
    v25 = 72;
    v47 = DWORD2(v41);
    v49 = (int)hMem[1];
    v50 = v43;
    v51 = L"Kerberos,!NTLM";
    wcscpy(cred, L"Ȁ");
    v45 = 72;
    v48 = v24;
    v52 = 30;
    option = ldap_bind_sW(v17, 0, cred, 0x486u);
    v26 = cred;
    do
    {
      *(_BYTE *)v26 = 0;
      v26 = (WCHAR *)((char *)v26 + 1);
      --v25;
    }
    while ( v25 );
    v23 = outvalue;
  }
  if ( (a4 & 2) == 0 || option != 7 && option != 49 )
  {
LABEL_64:
    if ( option )
      goto LABEL_65;
LABEL_69:
    LastError = 0;
    goto LABEL_70;
  }
  if ( (v23 & 2) != 0 )
  {
    outvalue = v23 & 0xFFFFFFFD;
    option = ldap_set_option(v17, 146, &outvalue);
    if ( option )
    {
LABEL_52:
      v20 = L"Call_ldap_set_option_LDAP_OPT_SSPI_FLAGS";
      goto LABEL_27;
    }
  }
  option = ldap_bind_sW(v17, 0, 0, 0x80u);
  if ( !option )
    goto LABEL_69;
  if ( !ldap_set_option(v17, 17, (const void *)2) )
  {
    option = ldap_bind_sW(v17, 0, 0, 0x80u);
    goto LABEL_64;
  }
LABEL_65:
  if ( option == 82 )
  {
    CryptDiagAddActionWithLastError((__int64)L"Call_ldap_bind");
    v27 = GetLastError();
  }
  else
  {
    CryptDiagAddActionWithLdapError(L"Call_ldap_bind", v17, option);
    v27 = I_CryptNetLdapMapErrorToWin32(v17, option);
  }
  LastError = v27;
LABEL_70:
  if ( v24 )
  {
    v28 = GetLastError();
    operator delete(v24);
    SetLastError(v28);
  }
  v29 = 48;
  v30 = &v41;
  do
  {
    *(_BYTE *)v30 = 0;
    v30 = (__int128 *)((char *)v30 + 1);
    --v29;
  }
  while ( v29 );
  if ( LastError )
    goto LABEL_29;
  *a7 = v17;
LABEL_30:
  if ( v36 )
    SchemeFreePasswordCredentialsW(&v39);
  if ( LastError )
  {
    SetLastError(LastError);
    return 0;
  }
  return v13;
}

```

## disassembly

```asm
0x180019b00  mov     [rsp-8+arg_18], r9d
0x180019b05  push    rbp
0x180019b06  push    rbx
0x180019b07  push    rsi
0x180019b08  push    rdi
0x180019b09  push    r12
0x180019b0b  push    r13
0x180019b0d  push    r14
0x180019b0f  push    r15
0x180019b11  lea     rbp, [rsp-7]
0x180019b16  sub     rsp, 0F8h
0x180019b1d  xorps   xmm0, xmm0
0x180019b20  xor     r15d, r15d
0x180019b23  mov     r13d, r8d
0x180019b26  mov     [rsp+130h+outvalue], r15d
0x180019b2b  mov     edi, edx
0x180019b2d  mov     [rsp+130h+var_EC], r15d
0x180019b32  mov     r12, rcx
0x180019b35  xor     edx, edx; Val
0x180019b37  lea     r8d, [r15+48h]; Size
0x180019b3b  lea     rcx, [rbp+3Fh+cred]; void *
0x180019b3f  movups  [rsp+130h+var_C0], xmm0
0x180019b44  movups  xmmword ptr [rbp+3Fh+hMem], xmm0
0x180019b48  movups  [rbp+3Fh+var_A0], xmm0
0x180019b4c  call    memset_0
0x180019b51  lea     rax, [rsp+130h+hKey]
0x180019b56  mov     [rsp+130h+var_E0], r15
0x180019b5b  mov     r9d, 20019h; samDesired
0x180019b61  mov     [rsp+130h+phkResult], rax; phkResult
0x180019b66  xor     r8d, r8d; ulOptions
0x180019b69  mov     [rsp+130h+var_F4], r15d
0x180019b6e  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\SystemCe"...
0x180019b75  mov     [rsp+130h+Type], r15d
0x180019b7a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019b81  mov     [rsp+130h+cbData], r15d
0x180019b86  mov     esi, r15d
0x180019b89  mov     dword ptr [rsp+130h+Data], r15d
0x180019b8e  mov     [rsp+130h+hKey], r15
0x180019b93  call    cs:__imp_RegOpenKeyExW
0x180019b99  mov     ebx, eax
0x180019b9b  test    eax, eax
0x180019b9d  jnz     short loc_180019BFB
0x180019b9f  mov     rcx, [rsp+130h+hKey]; hKey
0x180019ba4  lea     rax, [rsp+130h+cbData]
0x180019ba9  mov     [rsp+130h+lpcbData], rax; lpcbData
0x180019bae  lea     r9, [rsp+130h+Type]; lpType
0x180019bb3  lea     rax, [rsp+130h+Data]
0x180019bb8  mov     [rsp+130h+cbData], 4
0x180019bc0  xor     r8d, r8d; lpReserved
0x180019bc3  mov     [rsp+130h+phkResult], rax; lpData
0x180019bc8  lea     rdx, aDisableldapsig; "DisableLDAPSignAndEncrypt"
0x180019bcf  call    cs:__imp_RegQueryValueExW
0x180019bd5  mov     ebx, eax
0x180019bd7  test    eax, eax
0x180019bd9  jnz     short loc_180019BFB
0x180019bdb  cmp     [rsp+130h+Type], 4
0x180019be0  jnz     short loc_180019BF6
0x180019be2  cmp     [rsp+130h+cbData], 4
0x180019be7  jnz     short loc_180019BF6
0x180019be9  mov     esi, dword ptr [rsp+130h+Data]
0x180019bed  mov     ebx, r15d
0x180019bf0  mov     [rsp+130h+var_F4], esi
0x180019bf4  jmp     short loc_180019BFB
0x180019bf6  mov     ebx, 0Dh
0x180019bfb  mov     rcx, [rsp+130h+hKey]; hKey
0x180019c00  test    rcx, rcx
0x180019c03  jz      short loc_180019C0B
0x180019c05  call    cs:__imp_RegCloseKey
0x180019c0b  mov     r14d, 1
0x180019c11  cmp     ebx, 2
0x180019c14  jnz     short loc_180019C3B
0x180019c16  lea     r9, [rsp+130h+var_F4]; unsigned int *
0x180019c1b  mov     r8d, r14d; int
0x180019c1e  lea     rdx, aDisableldapsig; "DisableLDAPSignAndEncrypt"
0x180019c25  lea     rcx, SubKey; "Software\\Microsoft\\Cryptography\\OID"...
0x180019c2c  call    ?ReadRegDwordValue@@YAKPEBG0HPEAK@Z; ReadRegDwordValue(ushort const *,ushort const *,int,ulong *)
0x180019c31  mov     esi, [rsp+130h+var_F4]
0x180019c35  cmp     eax, ebx
0x180019c37  cmovz   esi, r15d
0x180019c3b  mov     rcx, [rbp+3Fh+arg_28]
0x180019c3f  lea     r8, [rsp+130h+var_EC]
0x180019c44  xorps   xmm0, xmm0
0x180019c47  lea     rdx, [rsp+130h+var_D8]
0x180019c4c  xor     eax, eax
0x180019c4e  movups  [rsp+130h+var_D8], xmm0
0x180019c53  mov     dword ptr [rsp+130h+var_D8], 18h
0x180019c5b  mov     [rsp+130h+var_C8], rax
0x180019c60  call    SchemeGetPasswordCredentialsW
0x180019c65  test    eax, eax
0x180019c67  jnz     short loc_180019C76
0x180019c69  call    cs:__imp_GetLastError
0x180019c6f  mov     esi, eax
0x180019c71  jmp     loc_180019D4B
0x180019c76  mov     edx, edi; PortNumber
0x180019c78  mov     rcx, r12; HostName
0x180019c7b  call    cs:__imp_ldap_initW
0x180019c81  mov     rdi, rax
0x180019c84  test    rax, rax
0x180019c87  jz      short loc_180019C69
0x180019c89  bt      r13d, 12h
0x180019c8e  jnb     short loc_180019CA6
0x180019c90  test    r12, r12
0x180019c93  jz      short loc_180019CA6
0x180019c95  mov     r8, r14; invalue
0x180019c98  mov     edx, 98h; option
0x180019c9d  mov     rcx, rax; ld
0x180019ca0  call    cs:__imp_ldap_set_option
0x180019ca6  mov     ecx, [rbp+3Fh+arg_20]
0x180019ca9  test    ecx, ecx
0x180019cab  jz      short loc_180019CF1
0x180019cad  cmp     ecx, 1388h
0x180019cb3  jnb     short loc_180019CBC
0x180019cb5  mov     edx, 5
0x180019cba  jmp     short loc_180019CC6
0x180019cbc  mov     eax, 10624DD3h
0x180019cc1  mul     ecx
0x180019cc3  shr     edx, 6
0x180019cc6  lea     eax, [rdx+rdx*4]
0x180019cc9  mov     dword ptr [rsp+130h+var_E0+4], r15d
0x180019cce  shl     eax, 2
0x180019cd1  lea     r8, [rsp+130h+Data]; invalue
0x180019cd6  mov     edx, 4; option
0x180019cdb  mov     dword ptr [rsp+130h+Data], eax
0x180019cdf  mov     rcx, rdi; ld
0x180019ce2  mov     dword ptr [rsp+130h+var_E0], eax
0x180019ce6  lea     r15, [rsp+130h+var_E0]
0x180019ceb  call    cs:__imp_ldap_set_option
0x180019cf1  mov     edx, 11h; option
0x180019cf6  mov     rcx, rdi; ld
0x180019cf9  lea     r8d, [rdx-0Eh]; invalue
0x180019cfd  call    cs:__imp_ldap_set_option
0x180019d03  test    esi, esi
0x180019d05  jz      short loc_180019D0E
0x180019d07  bt      r13d, 10h
0x180019d0c  jnb     short loc_180019D82
0x180019d0e  mov     r8, r14; invalue
0x180019d11  mov     edx, 95h; option
0x180019d16  mov     rcx, rdi; ld
0x180019d19  call    cs:__imp_ldap_set_option
0x180019d1f  mov     ebx, eax
0x180019d21  test    eax, eax
0x180019d23  jz      short loc_180019D82
0x180019d25  lea     rcx, aCallLdapSetOpt_0; "Call_ldap_set_option_LDAP_OPT_SIGN"
0x180019d2c  mov     r8d, ebx
0x180019d2f  mov     rdx, rdi
0x180019d32  call    CryptDiagAddActionWithLdapError
0x180019d37  mov     edx, ebx
0x180019d39  mov     rcx, rdi; ld
0x180019d3c  call    I_CryptNetLdapMapErrorToWin32
0x180019d41  mov     esi, eax
0x180019d43  mov     rcx, rdi
0x180019d46  call    LdapFreeBindings
0x180019d4b  cmp     [rsp+130h+var_EC], 0
0x180019d50  jz      short loc_180019D5C
0x180019d52  lea     rcx, [rsp+130h+var_D8]
0x180019d57  call    SchemeFreePasswordCredentialsW
0x180019d5c  test    esi, esi
0x180019d5e  jz      short loc_180019D6B
0x180019d60  mov     ecx, esi; dwErrCode
0x180019d62  call    cs:__imp_SetLastError
0x180019d68  xor     r14d, r14d
0x180019d6b  mov     eax, r14d
0x180019d6e  add     rsp, 0F8h
0x180019d75  pop     r15
0x180019d77  pop     r14
0x180019d79  pop     r13
0x180019d7b  pop     r12
0x180019d7d  pop     rdi
0x180019d7e  pop     rsi
0x180019d7f  pop     rbx
0x180019d80  pop     rbp
0x180019d81  retn
0x180019d82  test    esi, esi
0x180019d84  jnz     short loc_180019DA6
0x180019d86  mov     r8, r14; invalue
0x180019d89  mov     edx, 96h; option
0x180019d8e  mov     rcx, rdi; ld
0x180019d91  call    cs:__imp_ldap_set_option
0x180019d97  mov     ebx, eax
0x180019d99  test    eax, eax
0x180019d9b  jz      short loc_180019DA6
0x180019d9d  lea     rcx, aCallLdapSetOpt_1; "Call_ldap_set_option_LDAP_OPT_ENCRYPT"
0x180019da4  jmp     short loc_180019D2C
0x180019da6  mov     rdx, r15; timeout
0x180019da9  mov     rcx, rdi; ld
0x180019dac  call    cs:__imp_ldap_connect
0x180019db2  mov     ebx, eax
0x180019db4  test    eax, eax
0x180019db6  jz      short loc_180019DF7
0x180019db8  test    r12, r12
0x180019dbb  jnz     short loc_180019DEB
0x180019dbd  lea     r8, [rsp+130h+Data]; invalue
0x180019dc2  mov     dword ptr [rsp+130h+Data], r14d
0x180019dc7  lea     edx, [r12+3Dh]; option
0x180019dcc  mov     rcx, rdi; ld
0x180019dcf  call    cs:__imp_ldap_set_option
0x180019dd5  test    eax, eax
0x180019dd7  jnz     short loc_180019DEB
0x180019dd9  mov     rdx, r15; timeout
0x180019ddc  mov     rcx, rdi; ld
0x180019ddf  call    cs:__imp_ldap_connect
0x180019de5  mov     ebx, eax
0x180019de7  test    eax, eax
0x180019de9  jz      short loc_180019DF7
0x180019deb  lea     rcx, aCallLdapConnec; "Call_ldap_connect"
0x180019df2  jmp     loc_180019D2C
0x180019df7  lea     rdx, [rsp+130h+var_C0]
0x180019dfc  lea     rcx, [rsp+130h+var_D8]
0x180019e01  call    SchemeGetAuthIdentityFromPasswordCredentialsW
0x180019e06  test    eax, eax
0x180019e08  jnz     short loc_180019E15
0x180019e0a  call    cs:__imp_GetLastError
0x180019e10  jmp     loc_180019D41
0x180019e15  xor     eax, eax
0x180019e17  mov     ebx, 7
0x180019e1c  mov     [rsp+130h+outvalue], eax
0x180019e20  mov     r13d, 92h
0x180019e26  test    esi, esi
0x180019e28  jnz     short loc_180019E51
0x180019e2a  lea     r8, [rsp+130h+outvalue]; outvalue
0x180019e2f  mov     edx, r13d; option
0x180019e32  mov     rcx, rdi; ld
0x180019e35  call    cs:__imp_ldap_get_option
0x180019e3b  mov     ebx, eax
0x180019e3d  test    eax, eax
0x180019e3f  jz      short loc_180019E4D
0x180019e41  lea     rcx, aCallLdapGetOpt; "Call_ldap_get_option_LDAP_OPT_SSPI_FLAG"...
0x180019e48  jmp     loc_180019D2C
0x180019e4d  mov     eax, [rsp+130h+outvalue]
0x180019e51  mov     r12d, [rbp+3Fh+arg_18]
0x180019e55  mov     r15, [rbp+3Fh+hMem]
0x180019e59  test    r14b, r12b
0x180019e5c  jz      loc_180019F08
0x180019e62  or      eax, 2
0x180019e65  mov     [rsp+130h+outvalue], eax
0x180019e69  test    esi, esi
0x180019e6b  jnz     short loc_180019E90
0x180019e6d  lea     r8, [rsp+130h+outvalue]; invalue
0x180019e72  mov     edx, r13d; option
0x180019e75  mov     rcx, rdi; ld
0x180019e78  call    cs:__imp_ldap_set_option
0x180019e7e  mov     ebx, eax
0x180019e80  test    eax, eax
0x180019e82  jz      short loc_180019E90
0x180019e84  lea     rcx, aCallLdapSetOpt; "Call_ldap_set_option_LDAP_OPT_SSPI_FLAG"...
0x180019e8b  jmp     loc_180019D2C
0x180019e90  mov     rax, qword ptr [rsp+130h+var_C0]
0x180019e95  lea     r8, [rbp+3Fh+cred]; cred
0x180019e99  mov     [rbp+3Fh+var_88], rax
0x180019e9d  mov     esi, 48h ; 'H'
0x180019ea2  mov     eax, dword ptr [rbp+3Fh+var_C0+8]
0x180019ea5  mov     r9d, 486h; method
0x180019eab  mov     [rbp+3Fh+var_80], eax
0x180019eae  xor     edx, edx; dn
0x180019eb0  mov     eax, dword ptr [rbp+3Fh+hMem+8]
0x180019eb3  mov     rcx, rdi; ld
0x180019eb6  mov     [rbp+3Fh+var_70], eax
0x180019eb9  mov     rax, qword ptr [rbp+3Fh+var_A0]
0x180019ebd  mov     qword ptr [rbp+3Fh+var_68], rax
0x180019ec1  mov     eax, dword ptr [rbp+3Fh+var_A0+8]
0x180019ec4  mov     dword ptr [rbp+3Fh+var_68+8], eax
0x180019ec7  mov     eax, dword ptr [rbp+3Fh+var_A0+0Ch]
0x180019eca  mov     dword ptr [rbp+3Fh+var_68+0Ch], eax
0x180019ecd  lea     rax, aKerberosNtlm; "Kerberos,!NTLM"
0x180019ed4  mov     [rbp+3Fh+var_58], rax
0x180019ed8  mov     dword ptr [rbp+3Fh+cred], 200h
0x180019edf  mov     [rbp+3Fh+var_8C], esi
0x180019ee2  mov     [rbp+3Fh+var_78], r15
0x180019ee6  mov     [rbp+3Fh+var_50], 1Eh
0x180019eed  call    cs:__imp_ldap_bind_sW
0x180019ef3  mov     ebx, eax
0x180019ef5  lea     rax, [rbp+3Fh+cred]
0x180019ef9  mov     byte ptr [rax], 0
0x180019efc  add     rax, r14
0x180019eff  sub     rsi, r14
0x180019f02  jnz     short loc_180019EF9
0x180019f04  mov     eax, [rsp+130h+outvalue]
0x180019f08  test    r12b, 2
0x180019f0c  jz      short loc_180019F81
0x180019f0e  cmp     ebx, 7
0x180019f11  jz      short loc_180019F18
0x180019f13  cmp     ebx, 31h ; '1'
0x180019f16  jnz     short loc_180019F81
0x180019f18  test    al, 2
0x180019f1a  jz      short loc_180019F3E
0x180019f1c  and     eax, 0FFFFFFFDh
0x180019f1f  lea     r8, [rsp+130h+outvalue]; invalue
0x180019f24  mov     edx, r13d; option
0x180019f27  mov     [rsp+130h+outvalue], eax
0x180019f2b  mov     rcx, rdi; ld
0x180019f2e  call    cs:__imp_ldap_set_option
0x180019f34  mov     ebx, eax
0x180019f36  test    eax, eax
0x180019f38  jnz     loc_180019E84
0x180019f3e  mov     esi, 80h
0x180019f43  xor     r8d, r8d; cred
0x180019f46  mov     r9d, esi; method
0x180019f49  xor     edx, edx; dn
0x180019f4b  mov     rcx, rdi; ld
0x180019f4e  call    cs:__imp_ldap_bind_sW
  ... truncated ...
```
