# PsmpAdjustActivationToken

- ea: `0x1800038d0`
- end: `0x1800043a1`
- name: `PsmpAdjustActivationToken`
- size: `2769`
- prototype: `__int64 __fastcall(void *, int, int, WCHAR *, wchar_t *Str, PackageOrigin origin, UUID *, __int64 *, const WCHAR *, HANDLE *)`
- caller_count: `6`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003590`
- `0x1800035f0`
- `0x180003640`
- `0x1800038c0`
- `0x180007e60`
- `0x180007ec0`

## callees

- `0x1800038d0`
- `0x180004700`
- `0x180005d5c`
- `0x1800082fc`
- `0x180009d86`
- `0x180009d9e`
- `0x180009dd0`

## import_xrefs

- `ntdll!RtlStringFromGUIDEx` at `0x180003d05`
- `ntdll!RtlStringFromGUIDEx` at `0x180003d05`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003c31`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003c4b`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003c9e`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800040f1`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003c31`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003c4b`
- `ntdll!RtlInitUnicodeStringEx` at `0x180003c9e`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800040f1`
- `ntdll!NtClose` at `0x180004380`
- `ntdll!NtClose` at `0x180004380`
- `ntdll!RtlAcquirePrivilege` at `0x180003db2`
- `ntdll!RtlAcquirePrivilege` at `0x180003e62`
- `ntdll!RtlAcquirePrivilege` at `0x180003f07`
- `ntdll!RtlAcquirePrivilege` at `0x180003fac`
- `ntdll!RtlAcquirePrivilege` at `0x180004039`
- `ntdll!RtlAcquirePrivilege` at `0x1800042ec`
- `ntdll!RtlAcquirePrivilege` at `0x180003db2`
- `ntdll!RtlAcquirePrivilege` at `0x180003e62`
- `ntdll!RtlAcquirePrivilege` at `0x180003f07`
- `ntdll!RtlAcquirePrivilege` at `0x180003fac`
- `ntdll!RtlAcquirePrivilege` at `0x180004039`
- `ntdll!RtlAcquirePrivilege` at `0x1800042ec`
- `ntdll!RtlQueryPackageClaims` at `0x180003a4e`
- `ntdll!RtlQueryPackageClaims` at `0x180003a4e`
- `ntdll!NtSetInformationToken` at `0x180003dd7`
- `ntdll!NtSetInformationToken` at `0x180003e87`
- `ntdll!NtSetInformationToken` at `0x180003f2c`
- `ntdll!NtSetInformationToken` at `0x180003fd1`
- `ntdll!NtSetInformationToken` at `0x18000405e`
- `ntdll!NtSetInformationToken` at `0x18000430d`
- `ntdll!NtSetInformationToken` at `0x180003dd7`
- `ntdll!NtSetInformationToken` at `0x180003e87`
- `ntdll!NtSetInformationToken` at `0x180003f2c`
- `ntdll!NtSetInformationToken` at `0x180003fd1`
- `ntdll!NtSetInformationToken` at `0x18000405e`
- `ntdll!NtSetInformationToken` at `0x18000430d`
- `ntdll!RtlReleasePrivilege` at `0x180003de4`
- `ntdll!RtlReleasePrivilege` at `0x180003e94`
- `ntdll!RtlReleasePrivilege` at `0x180003f39`
- `ntdll!RtlReleasePrivilege` at `0x180003fde`
- `ntdll!RtlReleasePrivilege` at `0x18000406b`
- `ntdll!RtlReleasePrivilege` at `0x18000431a`
- `ntdll!RtlReleasePrivilege` at `0x180003de4`
- `ntdll!RtlReleasePrivilege` at `0x180003e94`
- `ntdll!RtlReleasePrivilege` at `0x180003f39`
- `ntdll!RtlReleasePrivilege` at `0x180003fde`
- `ntdll!RtlReleasePrivilege` at `0x18000406b`
- `ntdll!RtlReleasePrivilege` at `0x18000431a`
- `ntdll!NtDuplicateToken` at `0x180003d34`
- `ntdll!NtDuplicateToken` at `0x180003d34`
- `KERNELBASE!GetStagedPackageOrigin` at `0x180003b03`
- `KERNELBASE!GetStagedPackageOrigin` at `0x180003b03`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x180003c70`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x180003c70`
- `msvcrt!wcschr` at `0x180003ab2`
- `msvcrt!wcschr` at `0x180003ab2`
- `RPCRT4!UuidCreate` at `0x180003cc6`
- `RPCRT4!UuidCreate` at `0x180003cc6`

## pseudocode

```c
__int64 __fastcall PsmpAdjustActivationToken(
        void *a1,
        int a2,
        int a3,
        WCHAR *a4,
        wchar_t *Str,
        PackageOrigin origin,
        UUID *a7,
        __int64 *a8,
        const WCHAR *a9,
        HANDLE *a10)
{
  WCHAR *v10; // rsi
  UUID *p_Buf2; // r12
  __int64 *v13; // r13
  int inited; // ebx
  WCHAR *v15; // r14
  int v16; // r15d
  wchar_t *v17; // rax
  int v18; // ebx
  LONG v19; // eax
  int v20; // r13d
  unsigned int v21; // esi
  int v22; // r14d
  int v23; // edx
  __int64 v24; // rcx
  __int64 v25; // rax
  int v26; // ecx
  int v27; // edx
  __int64 v28; // rcx
  __int64 v29; // rax
  int v30; // edx
  __int64 v31; // rcx
  __int64 v32; // rax
  ULONG Privilege[2]; // [rsp+48h] [rbp-C0h] BYREF
  PVOID ReturnedState; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A8h]
  __int64 v38; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v39; // [rsp+70h] [rbp-98h] BYREF
  __int128 TokenInformation_8; // [rsp+80h] [rbp-88h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+90h] [rbp-78h] BYREF
  __int64 v42; // [rsp+98h] [rbp-70h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+A0h] [rbp-68h]
  __int64 v44; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v45; // [rsp+B0h] [rbp-58h]
  __int64 v46; // [rsp+B8h] [rbp-50h]
  __int64 v47; // [rsp+C0h] [rbp-48h]
  __int64 v48; // [rsp+C8h] [rbp-40h]
  __int64 v49; // [rsp+D0h] [rbp-38h] BYREF
  __int64 *v50; // [rsp+D8h] [rbp-30h]
  WCHAR *v51; // [rsp+E0h] [rbp-28h]
  WCHAR *v52; // [rsp+E8h] [rbp-20h]
  __int64 v53; // [rsp+F0h] [rbp-18h]
  HANDLE *v54; // [rsp+F8h] [rbp-10h]
  __int64 v55; // [rsp+100h] [rbp-8h] BYREF
  __int64 v56; // [rsp+108h] [rbp+0h] BYREF
  PCWSTR v57; // [rsp+110h] [rbp+8h]
  struct _UNICODE_STRING v58; // [rsp+118h] [rbp+10h] BYREF
  __int128 Buf1; // [rsp+128h] [rbp+20h] BYREF
  UUID Buf2; // [rsp+138h] [rbp+30h] BYREF
  _DWORD v61[4]; // [rsp+148h] [rbp+40h] BYREF
  int v62; // [rsp+158h] [rbp+50h] BYREF
  int v63; // [rsp+15Ch] [rbp+54h]
  const wchar_t *v64; // [rsp+160h] [rbp+58h]
  _WORD v65[2]; // [rsp+168h] [rbp+60h]
  int v66; // [rsp+16Ch] [rbp+64h]
  _DWORD v67[2]; // [rsp+170h] [rbp+68h]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+178h] [rbp+70h]
  int v69; // [rsp+180h] [rbp+78h]
  int v70; // [rsp+184h] [rbp+7Ch]
  const wchar_t *v71; // [rsp+188h] [rbp+80h]
  __int16 v72; // [rsp+190h] [rbp+88h]
  int v73; // [rsp+194h] [rbp+8Ch]
  int v74; // [rsp+198h] [rbp+90h]
  struct _UNICODE_STRING *v75; // [rsp+1A0h] [rbp+98h]
  struct _UNICODE_STRING DestinationString; // [rsp+1F8h] [rbp+F0h] BYREF
  struct _UNICODE_STRING v77; // [rsp+208h] [rbp+100h] BYREF
  struct _UNICODE_STRING v78; // [rsp+218h] [rbp+110h] BYREF
  char v79[2]; // [rsp+228h] [rbp+120h] BYREF
  __int16 v80; // [rsp+22Ah] [rbp+122h]
  char *v81; // [rsp+230h] [rbp+128h]
  WCHAR SourceString[72]; // [rsp+238h] [rbp+130h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+2C8h] [rbp+1C0h] BYREF
  char v84; // [rsp+358h] [rbp+250h] BYREF
  WCHAR packageFullName[128]; // [rsp+3A8h] [rbp+2A0h] BYREF

  v10 = a4;
  p_Buf2 = a7;
  v13 = a8;
  v57 = a9;
  v54 = a10;
  ExistingTokenHandle = a1;
  v52 = a4;
  LODWORD(v37) = a3;
  v50 = a8;
  v49 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v53 = 0;
  v48 = 0;
  v42 = 0;
  packageFamilyNameLength = 0;
  v56 = 0;
  v55 = 0;
  v44 = 0;
  ReturnedState = 0;
  Privilege[0] = 7;
  v38 = 0;
  TokenHandle = 0;
  TokenInformation_8 = 0;
  v58 = 0;
  v39 = 0;
  Buf2 = 0;
  Buf1 = 0;
  if ( (a2 & 0x4000000) != 0 )
  {
    if ( (a2 & 0xEC000001) != a2 )
    {
      inited = -1073741584;
      goto LABEL_114;
    }
    if ( a4 || Str || a7 || origin || a8 )
    {
LABEL_51:
      inited = -1073741776;
      goto LABEL_114;
    }
    v56 = 256;
    v55 = 130;
    RtlQueryPackageClaims(a1, packageFullName, &v56, SourceString, &v55, &Buf2, &v38, &v44, Privilege[0], ReturnedState);
    if ( (v44 & 3) != 3 )
    {
      inited = -1073741585;
      goto LABEL_114;
    }
    v10 = packageFullName;
    v15 = SourceString;
    v52 = packageFullName;
    v51 = SourceString;
    p_Buf2 = &Buf2;
    if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
      p_Buf2 = 0;
    origin = BYTE4(v38);
    v16 = v38;
  }
  else
  {
    v17 = wcschr(Str, 0x21u);
    if ( !v17 )
    {
      inited = -1073741581;
      goto LABEL_114;
    }
    v15 = v17 + 1;
    v51 = v17 + 1;
    v16 = a2 & 0x3FBE5F;
    if ( !(unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline() )
      v16 = a2 & 0x1FBE5F;
  }
  if ( origin == PackageOrigin_Unknown && *v10 )
    GetStagedPackageOrigin(v10, &origin);
  if ( (a2 & 0x2000) != 0 && (a2 & 1) == 0 )
  {
    inited = -1073741584;
    goto LABEL_114;
  }
  if ( (a2 & 0x8000) != 0 && (a2 & 1) == 0 )
  {
    inited = -1073741584;
    goto LABEL_114;
  }
  if ( (a2 & 0x100000) != 0 && (a2 & 1) == 0 )
  {
    inited = -1073741584;
    goto LABEL_114;
  }
  if ( (a2 & 2) != 0 && (a2 & 1) == 0 && (a2 & 0x800) == 0 )
  {
    inited = -1073741584;
    goto LABEL_114;
  }
  if ( (unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline() && (a2 & 0x200001) == 0x200000 )
  {
    inited = -1073741584;
    goto LABEL_114;
  }
  v18 = a2 & 0x10000;
  if ( (unsigned int)Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( v18 && (a2 & 0x1A0) == 0 )
    {
      inited = -1073741584;
      goto LABEL_114;
    }
  }
  else if ( v18 && (a2 & 0x180) == 0 )
  {
    inited = -1073741584;
    goto LABEL_114;
  }
  if ( v13 && (a2 & 0x30000002) != 0 )
  {
    inited = -1073741578;
    goto LABEL_114;
  }
  if ( (unsigned int)v37 >= 4 )
  {
    inited = -1073741583;
    goto LABEL_114;
  }
  if ( (a2 & 0x8000000) != 0 && (int)v37 > 1 )
    goto LABEL_51;
  if ( a2 >= 0 && !v54 )
  {
    inited = -1073741580;
    goto LABEL_114;
  }
  memset_0(&v62, 0, 0xA0u);
  inited = RtlInitUnicodeStringEx(&DestinationString, v10);
  if ( inited >= 0 )
  {
    inited = RtlInitUnicodeStringEx(&v77, v15);
    if ( inited >= 0 )
    {
      packageFamilyNameLength = 65;
      v19 = PackageFamilyNameFromFullName(v10, &packageFamilyNameLength, packageFamilyName);
      inited = v19;
      if ( v19 )
      {
        if ( v19 > 0 )
          inited = (unsigned __int16)v19 | 0xC0070000;
        goto LABEL_114;
      }
      inited = RtlInitUnicodeStringEx(&v78, packageFamilyName);
      if ( inited >= 0 )
      {
        v20 = 3;
        if ( (a2 & 0x40000000) != 0 )
        {
          if ( !p_Buf2 )
          {
            if ( UuidCreate(&Buf2) )
            {
              inited = -1073741823;
              goto LABEL_114;
            }
            p_Buf2 = &Buf2;
          }
          v81 = &v84;
          v80 = 78;
          RtlStringFromGUIDEx(p_Buf2, v79, 0);
          v20 = 4;
        }
        v21 = 1;
        if ( a2 < 0 )
        {
          TokenHandle = ExistingTokenHandle;
        }
        else
        {
          inited = NtDuplicateToken(ExistingTokenHandle, 0, 0, 0, TokenPrimary, &TokenHandle);
          if ( inited < 0 )
            goto LABEL_114;
        }
        v63 = v45;
        v61[0] = 3;
        v64 = L"WIN://SYSAPPID";
        v65[0] = 3;
        p_DestinationString = 0;
        v67[0] = 0;
        v62 = 1966108;
        *((_QWORD *)&v39 + 1) = &v62;
        *(_QWORD *)&TokenInformation_8 = &v39;
        *((_QWORD *)&TokenInformation_8 + 1) = v61;
        *(_QWORD *)&v39 = 0x100000001LL;
        inited = RtlAcquirePrivilege(Privilege, 1u, 2u, &ReturnedState);
        if ( inited >= 0 )
        {
          inited = NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation_8, 0x10u);
          RtlReleasePrivilege(ReturnedState);
          if ( (int)(inited + 0x80000000) < 0 || inited == -1073741275 )
          {
            v63 = v46;
            v61[0] = 3;
            v65[0] = 3;
            v64 = L"WIN://SYSAPPGROUPID";
            p_DestinationString = 0;
            v67[0] = 0;
            v62 = 2621478;
            *((_QWORD *)&v39 + 1) = &v62;
            *(_QWORD *)&TokenInformation_8 = &v39;
            *((_QWORD *)&TokenInformation_8 + 1) = v61;
            *(_QWORD *)&v39 = 0x100000001LL;
            inited = RtlAcquirePrivilege(Privilege, 1u, 2u, &ReturnedState);
            if ( inited >= 0 )
            {
              inited = NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation_8, 0x10u);
              RtlReleasePrivilege(ReturnedState);
              if ( (int)(inited + 0x80000000) < 0 || inited == -1073741275 )
              {
                if ( !v16 && origin == PackageOrigin_Unknown )
                  goto LABEL_84;
                v63 = v47;
                v61[0] = 3;
                v62 = 1310738;
                v64 = L"WIN://PKG";
                v65[0] = 2;
                p_DestinationString = 0;
                v67[0] = 0;
                inited = RtlAcquirePrivilege(Privilege, 1u, 2u, &ReturnedState);
                if ( inited >= 0 )
                {
                  inited = NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation_8, 0x10u);
                  RtlReleasePrivilege(ReturnedState);
                  if ( (int)(inited + 0x80000000) < 0 || inited == -1073741275 )
                  {
LABEL_84:
                    if ( !v50 && (a2 & 0x30000002) == 0 && !p_Buf2 )
                      goto LABEL_90;
                    v64 = L"WIN://PKGHOSTID";
                    v63 = v53;
                    v61[0] = 3;
                    v62 = 2097182;
                    v65[0] = 2;
                    p_DestinationString = 0;
                    v67[0] = 0;
                    inited = RtlAcquirePrivilege(Privilege, 1u, 2u, &ReturnedState);
                    if ( inited >= 0 )
                    {
                      inited = NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation_8, 0x10u);
                      RtlReleasePrivilege(ReturnedState);
                      if ( (int)(inited + 0x80000000) < 0 || inited == -1073741275 )
                      {
LABEL_90:
                        v63 = v48;
                        v61[0] = 3;
                        v64 = L"WIN://BGKD";
                        v62 = 1441812;
                        p_DestinationString = 0;
                        v67[0] = 0;
                        v65[0] = 2;
                        inited = RtlAcquirePrivilege(Privilege, 1u, 2u, &ReturnedState);
                        if ( inited >= 0 )
                        {
                          inited = NtSetInformationToken(
                                     TokenHandle,
                                     TokenSecurityAttributes,
                                     &TokenInformation_8,
                                     0x10u);
                          RtlReleasePrivilege(ReturnedState);
                          if ( (int)(inited + 0x80000000) < 0 || inited == -1073741275 )
                          {
                            if ( (a2 & 0x100) != 0 )
                              v22 = 128;
                            else
                              v22 = (a2 & 0x80u) != 0;
                            v63 = v45;
                            v64 = L"WIN://SYSAPPID";
                            v65[0] = 3;
                            p_DestinationString = &DestinationString;
                            v61[0] = 2;
                            v62 = 1966108;
                            v67[0] = v20;
                            v66 = v22;
                            if ( v57 )
                            {
                              inited = RtlInitUnicodeStringEx(&v58, v57);
                              if ( inited < 0 )
                                goto LABEL_114;
                              v70 = v46;
                              v74 = 1;
                              v71 = L"WIN://SYSAPPGROUPID";
                              v21 = 2;
                              v61[1] = 2;
                              v72 = 3;
                              v75 = &v58;
                              v69 = 2621478;
                              v73 = v22;
                            }
                            if ( v16 || origin )
                            {
                              v23 = v47;
                              LODWORD(v38) = v16;
                              HIDWORD(v38) = (unsigned __int8)origin | HIDWORD(v38) & 0xFFFFFF00;
                              v24 = v21++;
                              v25 = 5 * v24;
                              v61[v24] = 2;
                              *(&v63 + 2 * v25) = v23;
                              *(_QWORD *)&v65[4 * v25 - 4] = L"WIN://PKG";
                              *(&p_DestinationString + v25) = (struct _UNICODE_STRING *)&v38;
                              *(&v62 + 2 * v25) = 1310738;
                              v65[4 * v25] = 2;
                              v67[2 * v25] = 1;
                              v67[2 * v25 - 1] = v22;
                            }
                            v26 = v37;
                            if ( (int)v37 >= 2 )
                            {
                              v27 = v48;
                              v49 = (int)v37;
                              v28 = v21++;
                              v29 = 5 * v28;
                              v61[v28] = 2;
                              v26 = v37;
                              *(&v63 + 2 * v29) = v27;
                              *(_QWORD *)&v65[4 * v29 - 4] = L"WIN://BGKD";
                              *(&p_DestinationString + v29) = (struct _UNICODE_STRING *)&v49;
                              *(&v62 + 2 * v29) = 1441812;
                              v65[4 * v29] = 1;
                              v67[2 * v29] = 1;
                              v67[2 * v29 - 1] = v22;
                            }
                            v42 = -1;
                            if ( !v50 || *v50 == -1 )
                            {
                              if ( (a2 & 0x30000002) == 0 && !p_Buf2 )
                              {
LABEL_109:
                                LODWORD(v39) = 1;
                                *((_QWORD *)&v39 + 1) = &v62;
                                DWORD1(v39) = v21;
                                *(_QWORD *)&TokenInformation_8 = &v39;
                                *((_QWORD *)&TokenInformation_8 + 1) = v61;
                                inited = RtlAcquirePrivilege(Privilege, 1u, 2u, &ReturnedState);
                                if ( inited >= 0 )
                                {
                                  inited = NtSetInformationToken(
                                             TokenHandle,
                                             TokenSecurityAttributes,
                                             &TokenInformation_8,
                                             0x10u);
                                  RtlReleasePrivilege(ReturnedState);
                                  if ( inited >= 0 )
                                  {
                                    if ( v54 )
                                      *v54 = TokenHandle;
                                    TokenHandle = 0;
                                    inited = 0;
                                  }
                                }
                                goto LABEL_114;
                              }
                              inited = PsmpGenerateHostIdFromExtension(ExistingTokenHandle, v26, a2, (__int64)&v42);
                              if ( inited < 0 )
                                goto LABEL_114;
                            }
                            else
                            {
                              v42 = *v50;
                            }
                            v30 = v53;
                            v31 = v21++;
                            v32 = 5 * v31;
                            v61[v31] = 2;
                            *(&v63 + 2 * v32) = v30;
                            *(_QWORD *)&v65[4 * v32 - 4] = L"WIN://PKGHOSTID";
                            *(&p_DestinationString + v32) = (struct _UNICODE_STRING *)&v42;
                            *(&v62 + 2 * v32) = 2097182;
                            v67[2 * v32] = 1;
                            v65[4 * v32] = 2;
                            v67[2 * v32 - 1] = v22;
                            goto LABEL_109;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_114:
  if ( TokenHandle != ExistingTokenHandle && TokenHandle )
    NtClose(TokenHandle);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800038d0  mov     r11, rsp
0x1800038d3  push    rbp
0x1800038d4  push    rbx
0x1800038d5  lea     rbp, [r11-3E8h]
0x1800038dc  sub     rsp, 4D8h
0x1800038e3  mov     rax, cs:__security_cookie
0x1800038ea  xor     rax, rsp
0x1800038ed  mov     [rbp+3E0h+var_40], rax
0x1800038f4  mov     rax, [rbp+3E0h+arg_40]
0x1800038fb  xorps   xmm0, xmm0
0x1800038fe  mov     [r11+10h], rsi
0x180003902  xorps   xmm1, xmm1
0x180003905  mov     [r11-18h], rdi
0x180003909  mov     rbx, rcx
0x18000390c  mov     [r11-20h], r12
0x180003910  mov     rsi, r9
0x180003913  mov     r12, [rbp+3E0h+arg_30]
0x18000391a  mov     edi, edx
0x18000391c  mov     [r11-28h], r13
0x180003920  mov     r13, [rbp+3E0h+arg_38]
0x180003927  mov     [rbp+3E0h+var_3D8], rax
0x18000392b  mov     rax, [rbp+3E0h+arg_48]
0x180003932  mov     [r11-30h], r14
0x180003936  mov     [r11-38h], r15
0x18000393a  xor     r15d, r15d
0x18000393d  mov     [rbp+3E0h+var_3F0], rax
0x180003941  xor     eax, eax
0x180003943  mov     [rbp+3E0h+ExistingTokenHandle], rcx
0x180003947  mov     rcx, [rbp+3E0h+Str]; Str
0x18000394e  mov     [rbp+3E0h+var_400], r9
0x180003952  mov     dword ptr [rsp+4E0h+var_488], r8d
0x180003957  mov     [rbp+3E0h+var_410], r13
0x18000395b  mov     [rbp+3E0h+var_418], r15
0x18000395f  mov     [rbp+3E0h+var_438], rax
0x180003963  mov     [rbp+3E0h+var_430], rax
0x180003967  mov     [rbp+3E0h+var_428], rax
0x18000396b  mov     [rbp+3E0h+var_3F8], rax
0x18000396f  mov     [rbp+3E0h+var_420], rax
0x180003973  mov     [rbp+3E0h+var_450], r15
0x180003977  mov     [rbp+3E0h+packageFamilyNameLength], r15d
0x18000397b  mov     [rbp+3E0h+var_3E0], r15
0x18000397f  mov     [rbp+3E0h+var_3E8], r15
0x180003983  mov     [rbp+3E0h+var_440], r15
0x180003987  mov     [rsp+4E0h+ReturnedState], r15
0x18000398c  mov     [rsp+4E0h+Privilege], 7
0x180003994  mov     qword ptr [rsp+4E0h+var_480], r15
0x180003999  mov     [rsp+4E0h+TokenHandle], r15
0x18000399e  movups  [rsp+4E0h+TokenInformation+8], xmm0
0x1800039a3  movups  xmmword ptr [rbp+3E0h+var_3D0.Length], xmm1
0x1800039a7  movups  [rsp+4E0h+var_480+8], xmm0
0x1800039ac  movups  [rbp+3E0h+Buf2], xmm1
0x1800039b0  movups  [rbp+3E0h+Buf1], xmm0
0x1800039b4  bt      edx, 1Ah
0x1800039b8  jnb     loc_180003AAD
0x1800039be  mov     eax, edx
0x1800039c0  and     eax, 0EC000001h
0x1800039c5  cmp     eax, edx
0x1800039c7  jz      short loc_1800039D3
0x1800039c9  mov     ebx, 0C00000F0h
0x1800039ce  jmp     loc_180004340
0x1800039d3  test    r9, r9
0x1800039d6  jnz     loc_180003BF7
0x1800039dc  test    rcx, rcx
0x1800039df  jnz     loc_180003BF7
0x1800039e5  test    r12, r12
0x1800039e8  jnz     loc_180003BF7
0x1800039ee  cmp     [rbp+3E0h+origin], r15d
0x1800039f5  jnz     loc_180003BF7
0x1800039fb  test    r13, r13
0x1800039fe  jnz     loc_180003BF7
0x180003a04  lea     rax, [rbp+3E0h+var_440]
0x180003a08  mov     [rbp+3E0h+var_3E0], 100h
0x180003a10  mov     qword ptr [rsp+4E0h+var_4A8], rax
0x180003a15  lea     r9, [rbp+3E0h+SourceString]
0x180003a1c  lea     rax, [rsp+4E0h+var_480]
0x180003a21  mov     [rbp+3E0h+var_3E8], 82h
0x180003a29  mov     [rsp+4E0h+var_4B0], rax
0x180003a2e  lea     r8, [rbp+3E0h+var_3E0]
0x180003a32  lea     rax, [rbp+3E0h+Buf2]
0x180003a36  mov     rcx, rbx
0x180003a39  mov     [rsp+4E0h+NewTokenHandle], rax
0x180003a3e  lea     rdx, [rbp+3E0h+packageFullName]
0x180003a45  lea     rax, [rbp+3E0h+var_3E8]
0x180003a49  mov     qword ptr [rsp+4E0h+TokenType], rax
0x180003a4e  call    cs:__imp_RtlQueryPackageClaims
0x180003a54  movzx   eax, byte ptr [rbp+3E0h+var_440]
0x180003a58  and     al, 3
0x180003a5a  cmp     al, 3
0x180003a5c  jz      short loc_180003A68
0x180003a5e  mov     ebx, 0C00000EFh
0x180003a63  jmp     loc_180004340
0x180003a68  lea     rsi, [rbp+3E0h+packageFullName]
0x180003a6f  mov     r8d, 10h; Size
0x180003a75  lea     r14, [rbp+3E0h+SourceString]
0x180003a7c  mov     [rbp+3E0h+var_400], rsi
0x180003a80  lea     rdx, [rbp+3E0h+Buf2]; Buf2
0x180003a84  mov     [rbp+3E0h+var_408], r14
0x180003a88  lea     rcx, [rbp+3E0h+Buf1]; Buf1
0x180003a8c  call    memcmp_0
0x180003a91  test    eax, eax
0x180003a93  lea     r12, [rbp+3E0h+Buf2]
0x180003a97  movzx   eax, byte ptr [rsp+4E0h+var_480+4]
0x180003a9c  cmovz   r12, r15
0x180003aa0  mov     [rbp+3E0h+origin], eax
0x180003aa6  mov     r15d, dword ptr [rsp+4E0h+var_480]
0x180003aab  jmp     short loc_180003AEA
0x180003aad  mov     edx, 21h ; '!'; Ch
0x180003ab2  call    cs:__imp_wcschr
0x180003ab8  mov     r14, rax
0x180003abb  test    rax, rax
0x180003abe  jnz     short loc_180003ACA
0x180003ac0  mov     ebx, 0C00000F3h
0x180003ac5  jmp     loc_180004340
0x180003aca  add     r14, 2
0x180003ace  mov     r15d, edi
0x180003ad1  mov     [rbp+3E0h+var_408], r14
0x180003ad5  and     r15d, 3FBE5Fh
0x180003adc  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x180003ae1  test    eax, eax
0x180003ae3  jnz     short loc_180003AEA
0x180003ae5  btr     r15d, 15h
0x180003aea  cmp     [rbp+3E0h+origin], 0
0x180003af1  jnz     short loc_180003B09
0x180003af3  cmp     word ptr [rsi], 0
0x180003af7  jz      short loc_180003B09
0x180003af9  lea     rdx, [rbp+3E0h+origin]; origin
0x180003b00  mov     rcx, rsi; packageFullName
0x180003b03  call    cs:__imp_GetStagedPackageOrigin
0x180003b09  mov     eax, edi
0x180003b0b  and     eax, 1
0x180003b0e  bt      edi, 0Dh
0x180003b12  jnb     short loc_180003B22
0x180003b14  test    eax, eax
0x180003b16  jnz     short loc_180003B22
0x180003b18  mov     ebx, 0C00000F0h
0x180003b1d  jmp     loc_180004340
0x180003b22  bt      edi, 0Fh
0x180003b26  jnb     short loc_180003B36
0x180003b28  test    eax, eax
0x180003b2a  jnz     short loc_180003B36
0x180003b2c  mov     ebx, 0C00000F0h
0x180003b31  jmp     loc_180004340
0x180003b36  bt      edi, 14h
0x180003b3a  jnb     short loc_180003B4A
0x180003b3c  test    eax, eax
0x180003b3e  jnz     short loc_180003B4A
0x180003b40  mov     ebx, 0C00000F0h
0x180003b45  jmp     loc_180004340
0x180003b4a  test    dil, 2
0x180003b4e  jz      short loc_180003B64
0x180003b50  test    eax, eax
0x180003b52  jnz     short loc_180003B64
0x180003b54  bt      edi, 0Bh
0x180003b58  jb      short loc_180003B64
0x180003b5a  mov     ebx, 0C00000F0h
0x180003b5f  jmp     loc_180004340
0x180003b64  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x180003b69  test    eax, eax
0x180003b6b  jz      short loc_180003B85
0x180003b6d  mov     eax, edi
0x180003b6f  and     eax, 200001h
0x180003b74  cmp     eax, 200000h
0x180003b79  jnz     short loc_180003B85
0x180003b7b  mov     ebx, 0C00000F0h
0x180003b80  jmp     loc_180004340
0x180003b85  mov     ebx, edi
0x180003b87  and     ebx, 10000h
0x180003b8d  call    Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte__private_IsEnabledDeviceUsageNoInline
0x180003b92  test    eax, eax
0x180003b94  jz      short loc_180003BAC
0x180003b96  test    ebx, ebx
0x180003b98  jz      short loc_180003BC2
0x180003b9a  test    edi, 1A0h
0x180003ba0  jnz     short loc_180003BC2
0x180003ba2  mov     ebx, 0C00000F0h
0x180003ba7  jmp     loc_180004340
0x180003bac  test    ebx, ebx
0x180003bae  jz      short loc_180003BC2
0x180003bb0  test    edi, 180h
0x180003bb6  jnz     short loc_180003BC2
0x180003bb8  mov     ebx, 0C00000F0h
0x180003bbd  jmp     loc_180004340
0x180003bc2  test    r13, r13
0x180003bc5  jz      short loc_180003BD9
0x180003bc7  test    edi, 30000002h
0x180003bcd  jz      short loc_180003BD9
0x180003bcf  mov     ebx, 0C00000F6h
0x180003bd4  jmp     loc_180004340
0x180003bd9  mov     eax, dword ptr [rsp+4E0h+var_488]
0x180003bdd  cmp     eax, 4
0x180003be0  jb      short loc_180003BEC
0x180003be2  mov     ebx, 0C00000F1h
0x180003be7  jmp     loc_180004340
0x180003bec  bt      edi, 1Bh
0x180003bf0  jnb     short loc_180003C01
0x180003bf2  cmp     eax, 1
0x180003bf5  jle     short loc_180003C01
0x180003bf7  mov     ebx, 0C0000030h
0x180003bfc  jmp     loc_180004340
0x180003c01  test    edi, edi
0x180003c03  js      short loc_180003C16
0x180003c05  cmp     [rbp+3E0h+var_3F0], 0
0x180003c0a  jnz     short loc_180003C16
0x180003c0c  mov     ebx, 0C00000F4h
0x180003c11  jmp     loc_180004340
0x180003c16  xor     edx, edx; Val
0x180003c18  lea     rcx, [rbp+3E0h+var_390]; void *
0x180003c1c  mov     r8d, 0A0h; Size
0x180003c22  call    memset_0
0x180003c27  mov     rdx, rsi; SourceString
0x180003c2a  lea     rcx, [rbp+3E0h+DestinationString]; DestinationString
0x180003c31  call    cs:__imp_RtlInitUnicodeStringEx
0x180003c37  mov     ebx, eax
0x180003c39  test    eax, eax
0x180003c3b  js      loc_180004340
0x180003c41  mov     rdx, r14; SourceString
0x180003c44  lea     rcx, [rbp+3E0h+var_2E0]; DestinationString
0x180003c4b  call    cs:__imp_RtlInitUnicodeStringEx
0x180003c51  mov     ebx, eax
0x180003c53  test    eax, eax
0x180003c55  js      loc_180004340
0x180003c5b  lea     r8, [rbp+3E0h+packageFamilyName]; packageFamilyName
0x180003c62  mov     [rbp+3E0h+packageFamilyNameLength], 41h ; 'A'
0x180003c69  lea     rdx, [rbp+3E0h+packageFamilyNameLength]; packageFamilyNameLength
0x180003c6d  mov     rcx, rsi; packageFullName
0x180003c70  call    cs:__imp_PackageFamilyNameFromFullName
0x180003c76  mov     ebx, eax
0x180003c78  test    eax, eax
0x180003c7a  jz      short loc_180003C90
0x180003c7c  jle     loc_180004340
0x180003c82  movzx   ebx, ax
0x180003c85  or      ebx, 0C0070000h
0x180003c8b  jmp     loc_180004340
0x180003c90  lea     rdx, [rbp+3E0h+packageFamilyName]; SourceString
0x180003c97  lea     rcx, [rbp+3E0h+var_2D0]; DestinationString
0x180003c9e  call    cs:__imp_RtlInitUnicodeStringEx
0x180003ca4  mov     ebx, eax
0x180003ca6  test    eax, eax
0x180003ca8  js      loc_180004340
0x180003cae  mov     r14d, 3
0x180003cb4  mov     r13d, r14d
0x180003cb7  bt      edi, 1Eh
0x180003cbb  jnb     short loc_180003D11
0x180003cbd  test    r12, r12
0x180003cc0  jnz     short loc_180003CDE
0x180003cc2  lea     rcx, [rbp+3E0h+Buf2]; Uuid
0x180003cc6  call    cs:__imp_UuidCreate
0x180003ccc  test    eax, eax
0x180003cce  jz      short loc_180003CDA
0x180003cd0  mov     ebx, 0C0000001h
0x180003cd5  jmp     loc_180004340
0x180003cda  lea     r12, [rbp+3E0h+Buf2]
0x180003cde  lea     rax, [rbp+3E0h+var_190]
0x180003ce5  xor     r8d, r8d
0x180003ce8  mov     [rbp+3E0h+var_2B8], rax
0x180003cef  lea     rdx, [rbp+3E0h+var_2C0]
0x180003cf6  mov     eax, 4Eh ; 'N'
0x180003cfb  mov     rcx, r12
0x180003cfe  mov     [rbp+3E0h+var_2BE], ax
0x180003d05  call    cs:__imp_RtlStringFromGUIDEx
0x180003d0b  mov     r13d, 4
0x180003d11  mov     esi, 1
0x180003d16  test    edi, edi
0x180003d18  js      short loc_180003D46
0x180003d1a  mov     rcx, [rbp+3E0h+ExistingTokenHandle]; ExistingTokenHandle
0x180003d1e  lea     rax, [rsp+4E0h+TokenHandle]
0x180003d23  mov     [rsp+4E0h+NewTokenHandle], rax; NewTokenHandle
0x180003d28  xor     r9d, r9d; EffectiveOnly
0x180003d2b  xor     r8d, r8d; ObjectAttributes
0x180003d2e  mov     [rsp+4E0h+TokenType], esi; TokenType
0x180003d32  xor     edx, edx; DesiredAccess
0x180003d34  call    cs:__imp_NtDuplicateToken
0x180003d3a  mov     ebx, eax
0x180003d3c  test    eax, eax
0x180003d3e  js      loc_180004340
0x180003d44  jmp     short loc_180003D4F
0x180003d46  mov     rax, [rbp+3E0h+ExistingTokenHandle]
0x180003d4a  mov     [rsp+4E0h+TokenHandle], rax
0x180003d4f  mov     rax, [rbp+3E0h+var_438]
0x180003d53  lea     r9, [rsp+4E0h+ReturnedState]; ReturnedState
0x180003d58  mov     [rbp+3E0h+var_38C], eax
0x180003d5b  lea     rcx, [rsp+4E0h+Privilege]; Privilege
0x180003d60  lea     rax, aWinSysappid; "WIN://SYSAPPID"
0x180003d67  mov     [rbp+3E0h+var_3A0], r14d
0x180003d6b  mov     [rbp+3E0h+var_388], rax
0x180003d6f  mov     edx, esi; NumPriv
0x180003d71  xor     eax, eax
0x180003d73  mov     [rbp+3E0h+var_380], r14w
0x180003d78  mov     [rbp+3E0h+var_370], rax
0x180003d7c  mov     r14d, 2
0x180003d82  mov     [rbp+3E0h+var_378], eax
0x180003d85  mov     r8d, r14d; Flags
0x180003d88  lea     rax, [rbp+3E0h+var_390]
0x180003d8c  mov     [rbp+3E0h+var_390], 1E001Ch
0x180003d93  mov     qword ptr [rsp+4E0h+TokenInformation], rax
0x180003d98  lea     rax, [rsp+4E0h+var_480+8]
0x180003d9d  mov     qword ptr [rsp+4E0h+TokenInformation+8], rax
0x180003da2  lea     rax, [rbp+3E0h+var_3A0]
0x180003da6  mov     [rbp+3E0h+var_460], rax
0x180003daa  mov     dword ptr [rsp+4E0h+var_480+8], esi
  ... truncated ...
```
