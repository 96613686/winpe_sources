# PsmpAdjustActivationToken

- ea: `0x18002cfc4`
- end: `0x18002d892`
- name: `PsmpAdjustActivationToken`
- size: `2254`
- prototype: `__int64 __fastcall(void *, int, __int64, WCHAR *, wchar_t *Str)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001e20c`

## callees

- `0x18001b7e0`
- `0x18001c10c`
- `0x18002cf3c`
- `0x18002cf80`
- `0x18002cfc4`
- `0x18002d898`
- `0x18002e170`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002d15e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002d15e`
- `ntdll!NtClose` at `0x18002d860`
- `ntdll!NtClose` at `0x18002d860`
- `ntdll!RtlReleasePrivilege` at `0x18002d3de`
- `ntdll!RtlReleasePrivilege` at `0x18002d48d`
- `ntdll!RtlReleasePrivilege` at `0x18002d52c`
- `ntdll!RtlReleasePrivilege` at `0x18002d5d7`
- `ntdll!RtlReleasePrivilege` at `0x18002d66d`
- `ntdll!RtlReleasePrivilege` at `0x18002d83e`
- `ntdll!RtlReleasePrivilege` at `0x18002d3de`
- `ntdll!RtlReleasePrivilege` at `0x18002d48d`
- `ntdll!RtlReleasePrivilege` at `0x18002d52c`
- `ntdll!RtlReleasePrivilege` at `0x18002d5d7`
- `ntdll!RtlReleasePrivilege` at `0x18002d66d`
- `ntdll!RtlReleasePrivilege` at `0x18002d83e`
- `ntdll!NtSetInformationToken` at `0x18002d3d1`
- `ntdll!NtSetInformationToken` at `0x18002d480`
- `ntdll!NtSetInformationToken` at `0x18002d51f`
- `ntdll!NtSetInformationToken` at `0x18002d5ca`
- `ntdll!NtSetInformationToken` at `0x18002d660`
- `ntdll!NtSetInformationToken` at `0x18002d831`
- `ntdll!NtSetInformationToken` at `0x18002d3d1`
- `ntdll!NtSetInformationToken` at `0x18002d480`
- `ntdll!NtSetInformationToken` at `0x18002d51f`
- `ntdll!NtSetInformationToken` at `0x18002d5ca`
- `ntdll!NtSetInformationToken` at `0x18002d660`
- `ntdll!NtSetInformationToken` at `0x18002d831`
- `ntdll!RtlAcquirePrivilege` at `0x18002d3b0`
- `ntdll!RtlAcquirePrivilege` at `0x18002d45c`
- `ntdll!RtlAcquirePrivilege` at `0x18002d4fb`
- `ntdll!RtlAcquirePrivilege` at `0x18002d5a6`
- `ntdll!RtlAcquirePrivilege` at `0x18002d63c`
- `ntdll!RtlAcquirePrivilege` at `0x18002d811`
- `ntdll!RtlAcquirePrivilege` at `0x18002d3b0`
- `ntdll!RtlAcquirePrivilege` at `0x18002d45c`
- `ntdll!RtlAcquirePrivilege` at `0x18002d4fb`
- `ntdll!RtlAcquirePrivilege` at `0x18002d5a6`
- `ntdll!RtlAcquirePrivilege` at `0x18002d63c`
- `ntdll!RtlAcquirePrivilege` at `0x18002d811`
- `ntdll!RtlInitUnicodeStringEx` at `0x18002d268`
- `ntdll!RtlInitUnicodeStringEx` at `0x18002d282`
- `ntdll!RtlInitUnicodeStringEx` at `0x18002d2d5`
- `ntdll!RtlInitUnicodeStringEx` at `0x18002d268`
- `ntdll!RtlInitUnicodeStringEx` at `0x18002d282`
- `ntdll!RtlInitUnicodeStringEx` at `0x18002d2d5`
- `ntdll!RtlStringFromGUIDEx` at `0x18002d33b`
- `ntdll!RtlStringFromGUIDEx` at `0x18002d33b`
- `ntdll!RtlQueryPackageClaims` at `0x18002d0ef`
- `ntdll!RtlQueryPackageClaims` at `0x18002d0ef`
- `RPCRT4!UuidCreate` at `0x18002d2fc`
- `RPCRT4!UuidCreate` at `0x18002d2fc`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18002d2a7`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18002d2a7`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackageOrigin` at `0x18002d1ae`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackageOrigin` at `0x18002d1ae`

## pseudocode

```c
__int64 __fastcall PsmpAdjustActivationToken(void *a1, int a2, __int64 a3, WCHAR *a4, wchar_t *Str)
{
  WCHAR *v5; // rsi
  int inited; // ebx
  WCHAR *v8; // r14
  int v9; // r15d
  UUID *p_Buf2; // r12
  wchar_t *v11; // rax
  int v12; // ebx
  bool v13; // zf
  LONG v14; // eax
  int v15; // r14d
  int v16; // esi
  unsigned int v17; // r14d
  int v18; // edx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 *v22; // [rsp+20h] [rbp-E0h]
  ULONG Privilege; // [rsp+40h] [rbp-C0h] BYREF
  PVOID ReturnedState; // [rsp+48h] [rbp-B8h] BYREF
  PackageOrigin origin; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp-A8h]
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v28; // [rsp+68h] [rbp-98h] BYREF
  __int128 TokenInformation; // [rsp+78h] [rbp-88h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+88h] [rbp-78h] BYREF
  __int64 v31; // [rsp+90h] [rbp-70h] BYREF
  HANDLE v32; // [rsp+98h] [rbp-68h]
  __int64 v33; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v34; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  __int64 v37; // [rsp+C0h] [rbp-40h]
  WCHAR *v38; // [rsp+C8h] [rbp-38h]
  WCHAR *v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  __int64 v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  _OWORD Buf1[2]; // [rsp+F0h] [rbp-10h] BYREF
  UUID Buf2; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v45[4]; // [rsp+120h] [rbp+20h] BYREF
  int v46; // [rsp+130h] [rbp+30h] BYREF
  int v47; // [rsp+134h] [rbp+34h]
  const wchar_t *v48; // [rsp+138h] [rbp+38h]
  _WORD v49[2]; // [rsp+140h] [rbp+40h]
  int v50; // [rsp+144h] [rbp+44h]
  _DWORD v51[2]; // [rsp+148h] [rbp+48h]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+150h] [rbp+50h]
  int v53; // [rsp+158h] [rbp+58h]
  int v54; // [rsp+15Ch] [rbp+5Ch]
  const wchar_t *v55; // [rsp+160h] [rbp+60h]
  __int16 v56; // [rsp+168h] [rbp+68h]
  int v57; // [rsp+16Ch] [rbp+6Ch]
  int v58; // [rsp+170h] [rbp+70h]
  __int64 *v59; // [rsp+178h] [rbp+78h]
  struct _UNICODE_STRING DestinationString; // [rsp+1D0h] [rbp+D0h] BYREF
  struct _UNICODE_STRING v61; // [rsp+1E0h] [rbp+E0h] BYREF
  struct _UNICODE_STRING v62; // [rsp+1F0h] [rbp+F0h] BYREF
  char v63[2]; // [rsp+200h] [rbp+100h] BYREF
  __int16 v64; // [rsp+202h] [rbp+102h]
  char *v65; // [rsp+208h] [rbp+108h]
  WCHAR SourceString[72]; // [rsp+210h] [rbp+110h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+2A0h] [rbp+1A0h] BYREF
  char v68; // [rsp+330h] [rbp+230h] BYREF
  WCHAR packageFullName[128]; // [rsp+380h] [rbp+280h] BYREF

  v32 = a1;
  v39 = a4;
  origin = PackageOrigin_Unknown;
  v36 = 0;
  v41 = 0;
  v37 = 0;
  v5 = a4;
  v40 = 0;
  v42 = 0;
  v31 = 0;
  packageFamilyNameLength = 0;
  v34 = 0;
  v33 = 0;
  v35 = 0;
  ReturnedState = 0;
  Privilege = 7;
  v27 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  v28 = 0;
  Buf2 = 0;
  memset(Buf1, 0, sizeof(Buf1));
  if ( (a2 & 0x4000000) != 0 )
  {
    if ( (a2 & 0xEC000001) != a2 )
    {
LABEL_3:
      inited = -1073741584;
      goto LABEL_78;
    }
    if ( a4 || Str )
    {
      inited = -1073741776;
      goto LABEL_78;
    }
    v34 = 256;
    v33 = 130;
    v22 = &v33;
    RtlQueryPackageClaims(a1, packageFullName, &v34, SourceString);
    if ( (v35 & 3) != 3 )
    {
      inited = -1073741585;
      goto LABEL_78;
    }
    v5 = packageFullName;
    v8 = SourceString;
    v39 = packageFullName;
    v38 = SourceString;
    v9 = v27;
    p_Buf2 = (UUID *)((unsigned __int64)&Buf2 & -(__int64)(memcmp_0(Buf1, &Buf2, 0x10u) != 0));
    origin = BYTE4(v27);
  }
  else
  {
    v11 = wcschr(Str, 0x21u);
    if ( !v11 )
    {
      inited = -1073741581;
      goto LABEL_78;
    }
    v8 = v11 + 1;
    v38 = v11 + 1;
    v9 = a2 & 0x3FBE5F;
    p_Buf2 = 0;
    if ( !(unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline() )
      v9 = a2 & 0x1FBE5F;
  }
  if ( *v5 )
    GetStagedPackageOrigin(v5, &origin);
  if ( (a2 & 0x2000) != 0 && (a2 & 1) == 0
    || (a2 & 0x8000) != 0 && (a2 & 1) == 0
    || (a2 & 0x100000) != 0 && (a2 & 1) == 0
    || (a2 & 2) != 0 && (a2 & 1) == 0 && (a2 & 0x800) == 0
    || (unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline() && (a2 & 0x200001) == 0x200000 )
  {
    goto LABEL_3;
  }
  v12 = a2 & 0x10000;
  if ( (unsigned int)Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( !v12 )
      goto LABEL_31;
    v13 = (a2 & 0x1A0) == 0;
  }
  else
  {
    if ( !v12 )
      goto LABEL_31;
    v13 = (a2 & 0x180) == 0;
  }
  if ( v13 )
    goto LABEL_3;
LABEL_31:
  if ( a2 < 0 )
  {
    memset_0(&v46, 0, 0xA0u);
    inited = RtlInitUnicodeStringEx(&DestinationString, v5);
    if ( inited >= 0 )
    {
      inited = RtlInitUnicodeStringEx(&v61, v8);
      if ( inited >= 0 )
      {
        packageFamilyNameLength = 65;
        v14 = PackageFamilyNameFromFullName(v5, &packageFamilyNameLength, packageFamilyName);
        inited = v14;
        if ( v14 )
        {
          if ( v14 > 0 )
            inited = (unsigned __int16)v14 | 0xC0070000;
        }
        else
        {
          inited = RtlInitUnicodeStringEx(&v62, packageFamilyName);
          if ( inited >= 0 )
          {
            v15 = 3;
            if ( (a2 & 0x40000000) != 0 )
            {
              if ( !p_Buf2 )
              {
                if ( UuidCreate(&Buf2) )
                {
                  inited = -1073741823;
                  goto LABEL_78;
                }
                p_Buf2 = &Buf2;
              }
              v65 = &v68;
              v64 = 78;
              RtlStringFromGUIDEx(p_Buf2, v63, 0);
              v15 = 4;
            }
            TokenHandle = v32;
            v47 = v36;
            v45[0] = 3;
            v48 = L"WIN://SYSAPPID";
            *((_QWORD *)&v28 + 1) = &v46;
            v46 = 1966108;
            *(_QWORD *)&TokenInformation = &v28;
            *((_QWORD *)&TokenInformation + 1) = v45;
            v49[0] = 3;
            p_DestinationString = 0;
            v51[0] = 0;
            *(_QWORD *)&v28 = 0x100000001LL;
            inited = RtlAcquirePrivilege(&Privilege, 1u, 2u, &ReturnedState);
            if ( inited >= 0 )
            {
              inited = NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation, 0x10u);
              RtlReleasePrivilege(ReturnedState);
              if ( (int)(inited + 0x80000000) < 0 || inited == -1073741275 )
              {
                v47 = v41;
                v45[0] = 3;
                v48 = L"WIN://SYSAPPGROUPID";
                v49[0] = 3;
                *((_QWORD *)&v28 + 1) = &v46;
                v46 = 2621478;
                *(_QWORD *)&TokenInformation = &v28;
                p_DestinationString = 0;
                *((_QWORD *)&TokenInformation + 1) = v45;
                v51[0] = 0;
                *(_QWORD *)&v28 = 0x100000001LL;
                inited = RtlAcquirePrivilege(&Privilege, 1u, 2u, &ReturnedState);
                if ( inited >= 0 )
                {
                  inited = NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation, 0x10u);
                  RtlReleasePrivilege(ReturnedState);
                  if ( (int)(inited + 0x80000000) < 0 || inited == -1073741275 )
                  {
                    if ( !v9 && origin == PackageOrigin_Unknown )
                      goto LABEL_59;
                    v48 = L"WIN://PKG";
                    v47 = v37;
                    v45[0] = 3;
                    v46 = 1310738;
                    v49[0] = 2;
                    p_DestinationString = 0;
                    v51[0] = 0;
                    inited = RtlAcquirePrivilege(&Privilege, 1u, 2u, &ReturnedState);
                    if ( inited >= 0 )
                    {
                      inited = NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation, 0x10u);
                      RtlReleasePrivilege(ReturnedState);
                      if ( (int)(inited + 0x80000000) < 0 || inited == -1073741275 )
                      {
LABEL_59:
                        if ( (a2 & 0x30000002) == 0 && !p_Buf2 )
                          goto LABEL_65;
                        v48 = L"WIN://PKGHOSTID";
                        v47 = v40;
                        v45[0] = 3;
                        v46 = 2097182;
                        v49[0] = 2;
                        p_DestinationString = 0;
                        v51[0] = 0;
                        inited = RtlAcquirePrivilege(&Privilege, 1u, 2u, &ReturnedState);
                        if ( inited >= 0 )
                        {
                          inited = NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation, 0x10u);
                          RtlReleasePrivilege(ReturnedState);
                          if ( (int)(inited + 0x80000000) < 0 || inited == -1073741275 )
                          {
LABEL_65:
                            v47 = v42;
                            v45[0] = 3;
                            v48 = L"WIN://BGKD";
                            v46 = 1441812;
                            v49[0] = 2;
                            p_DestinationString = 0;
                            v51[0] = 0;
                            inited = RtlAcquirePrivilege(&Privilege, 1u, 2u, &ReturnedState);
                            if ( inited >= 0 )
                            {
                              inited = NtSetInformationToken(
                                         TokenHandle,
                                         TokenSecurityAttributes,
                                         &TokenInformation,
                                         0x10u);
                              RtlReleasePrivilege(ReturnedState);
                              if ( (int)(inited + 0x80000000) < 0 || inited == -1073741275 )
                              {
                                v16 = 128;
                                if ( (a2 & 0x100) == 0 )
                                  v16 = (a2 & 0x80u) != 0;
                                v47 = v36;
                                v48 = L"WIN://SYSAPPID";
                                v49[0] = 3;
                                p_DestinationString = &DestinationString;
                                v45[0] = 2;
                                v46 = 1966108;
                                v51[0] = v15;
                                v50 = v16;
                                if ( v9 || (v17 = 1, origin) )
                                {
                                  LODWORD(v27) = v9;
                                  v54 = v37;
                                  v17 = 2;
                                  HIDWORD(v27) = (unsigned __int8)origin | HIDWORD(v27) & 0xFFFFFF00;
                                  v55 = L"WIN://PKG";
                                  v59 = &v27;
                                  v53 = 1310738;
                                  v56 = 2;
                                  v58 = 1;
                                  v57 = v16;
                                  v45[1] = 2;
                                }
                                v31 = -1;
                                if ( (a2 & 0x30000002) != 0 || p_Buf2 )
                                {
                                  inited = PsmpGenerateHostIdFromExtension(v32, (int)v22, a2, (__int64)&v31);
                                  if ( inited < 0 )
                                    goto LABEL_78;
                                  v18 = v40;
                                  v19 = v17++;
                                  v20 = 5 * v19;
                                  v45[v19] = 2;
                                  *(&v47 + 2 * v20) = v18;
                                  *(_QWORD *)&v49[4 * v20 - 4] = L"WIN://PKGHOSTID";
                                  *(&p_DestinationString + v20) = (struct _UNICODE_STRING *)&v31;
                                  *(&v46 + 2 * v20) = 2097182;
                                  v51[2 * v20] = 1;
                                  v49[4 * v20] = 2;
                                  v51[2 * v20 - 1] = v16;
                                }
                                LODWORD(v28) = 1;
                                *((_QWORD *)&v28 + 1) = &v46;
                                DWORD1(v28) = v17;
                                *(_QWORD *)&TokenInformation = &v28;
                                *((_QWORD *)&TokenInformation + 1) = v45;
                                inited = RtlAcquirePrivilege(&Privilege, 1u, 2u, &ReturnedState);
                                if ( inited >= 0 )
                                {
                                  inited = NtSetInformationToken(
                                             TokenHandle,
                                             TokenSecurityAttributes,
                                             &TokenInformation,
                                             0x10u);
                                  RtlReleasePrivilege(ReturnedState);
                                  if ( inited >= 0 )
                                  {
                                    TokenHandle = 0;
                                    inited = 0;
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
        }
      }
    }
  }
  else
  {
    inited = -1073741580;
  }
LABEL_78:
  if ( TokenHandle != v32 && TokenHandle )
    NtClose(TokenHandle);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18002cfc4  mov     [rsp-8+arg_8], rbx
0x18002cfc9  push    rbp
0x18002cfca  push    rsi
0x18002cfcb  push    rdi
0x18002cfcc  push    r12
0x18002cfce  push    r13
0x18002cfd0  push    r14
0x18002cfd2  push    r15
0x18002cfd4  lea     rbp, [rsp-390h]
0x18002cfdc  sub     rsp, 490h
0x18002cfe3  mov     rax, cs:__security_cookie
0x18002cfea  xor     rax, rsp
0x18002cfed  mov     [rbp+3C0h+var_40], rax
0x18002cff4  xor     r13d, r13d
0x18002cff7  mov     [rbp+3C0h+var_428], rcx
0x18002cffb  xor     eax, eax
0x18002cffd  mov     [rbp+3C0h+var_3F0], r9
0x18002d001  mov     [rsp+4C0h+origin], r13d
0x18002d006  xorps   xmm0, xmm0
0x18002d009  mov     [rbp+3C0h+var_408], rax
0x18002d00d  xorps   xmm1, xmm1
0x18002d010  mov     [rbp+3C0h+var_3E0], rax
0x18002d014  mov     rbx, rcx
0x18002d017  mov     rcx, [rbp+3C0h+Str]; Str
0x18002d01e  lea     r14d, [r13+3]
0x18002d022  mov     [rbp+3C0h+var_400], rax
0x18002d026  mov     rsi, r9
0x18002d029  mov     [rbp+3C0h+var_3E8], rax
0x18002d02d  mov     edi, edx
0x18002d02f  mov     [rbp+3C0h+var_3D8], rax
0x18002d033  mov     [rbp+3C0h+var_430], r13
0x18002d037  mov     [rbp+3C0h+packageFamilyNameLength], r13d
0x18002d03b  mov     [rbp+3C0h+var_418], r13
0x18002d03f  mov     [rbp+3C0h+var_420], r13
0x18002d043  mov     [rbp+3C0h+var_410], r13
0x18002d047  mov     [rsp+4C0h+ReturnedState], r13
0x18002d04c  mov     [rsp+4C0h+Privilege], 7
0x18002d054  mov     [rsp+4C0h+var_460], r13
0x18002d059  mov     [rsp+4C0h+TokenHandle], r13
0x18002d05e  movups  [rsp+4C0h+TokenInformation], xmm0
0x18002d063  movups  [rbp+3C0h+var_3C0], xmm1
0x18002d067  movups  [rsp+4C0h+var_458], xmm0
0x18002d06c  movups  [rbp+3C0h+Buf2], xmm1
0x18002d070  movups  [rbp+3C0h+Buf1], xmm0
0x18002d074  bt      edx, 1Ah
0x18002d078  jnb     loc_18002D159
0x18002d07e  mov     eax, edx
0x18002d080  and     eax, 0EC000001h
0x18002d085  cmp     eax, edx
0x18002d087  jz      short loc_18002D093
0x18002d089  mov     ebx, 0C00000F0h
0x18002d08e  jmp     loc_18002D850
0x18002d093  test    r9, r9
0x18002d096  jnz     loc_18002D14F
0x18002d09c  test    rcx, rcx
0x18002d09f  jnz     loc_18002D14F
0x18002d0a5  lea     rax, [rbp+3C0h+var_410]
0x18002d0a9  mov     [rbp+3C0h+var_418], 100h
0x18002d0b1  mov     [rsp+4C0h+var_488], rax
0x18002d0b6  lea     r9, [rbp+3C0h+SourceString]
0x18002d0bd  lea     rax, [rsp+4C0h+var_460]
0x18002d0c2  mov     [rbp+3C0h+var_420], 82h
0x18002d0ca  mov     [rsp+4C0h+var_490], rax
0x18002d0cf  lea     r8, [rbp+3C0h+var_418]
0x18002d0d3  lea     rax, [rbp+3C0h+Buf2]
0x18002d0d7  mov     rcx, rbx
0x18002d0da  mov     qword ptr [rsp+4C0h+var_498], rax
0x18002d0df  lea     rdx, [rbp+3C0h+packageFullName]
0x18002d0e6  lea     rax, [rbp+3C0h+var_420]
0x18002d0ea  mov     [rsp+4C0h+var_4A0], rax
0x18002d0ef  call    cs:__imp_RtlQueryPackageClaims
0x18002d0f5  mov     al, byte ptr [rbp+3C0h+var_410]
0x18002d0f8  and     al, r14b
0x18002d0fb  cmp     al, r14b
0x18002d0fe  jz      short loc_18002D10A
0x18002d100  mov     ebx, 0C00000EFh
0x18002d105  jmp     loc_18002D850
0x18002d10a  lea     rsi, [rbp+3C0h+packageFullName]
0x18002d111  mov     r8d, 10h; Size
0x18002d117  lea     r14, [rbp+3C0h+SourceString]
0x18002d11e  mov     [rbp+3C0h+var_3F0], rsi
0x18002d122  lea     rdx, [rbp+3C0h+Buf2]; Buf2
0x18002d126  mov     [rbp+3C0h+var_3F8], r14
0x18002d12a  lea     rcx, [rbp+3C0h+Buf1]; Buf1
0x18002d12e  call    memcmp_0
0x18002d133  mov     r15d, dword ptr [rsp+4C0h+var_460]
0x18002d138  neg     eax
0x18002d13a  lea     rax, [rbp+3C0h+Buf2]
0x18002d13e  sbb     r12, r12
0x18002d141  and     r12, rax
0x18002d144  movzx   eax, byte ptr [rsp+4C0h+var_460+4]
0x18002d149  mov     [rsp+4C0h+origin], eax
0x18002d14d  jmp     short loc_18002D199
0x18002d14f  mov     ebx, 0C0000030h
0x18002d154  jmp     loc_18002D850
0x18002d159  mov     edx, 21h ; '!'; Ch
0x18002d15e  call    cs:__imp_wcschr
0x18002d164  mov     r14, rax
0x18002d167  test    rax, rax
0x18002d16a  jnz     short loc_18002D176
0x18002d16c  mov     ebx, 0C00000F3h
0x18002d171  jmp     loc_18002D850
0x18002d176  add     r14, 2
0x18002d17a  mov     r15d, edi
0x18002d17d  mov     [rbp+3C0h+var_3F8], r14
0x18002d181  and     r15d, 3FBE5Fh
0x18002d188  mov     r12, r13
0x18002d18b  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x18002d190  test    eax, eax
0x18002d192  jnz     short loc_18002D199
0x18002d194  btr     r15d, 15h
0x18002d199  cmp     [rsp+4C0h+origin], r13d
0x18002d19e  jnz     short loc_18002D1B4
0x18002d1a0  cmp     [rsi], r13w
0x18002d1a4  jz      short loc_18002D1B4
0x18002d1a6  lea     rdx, [rsp+4C0h+origin]; origin
0x18002d1ab  mov     rcx, rsi; packageFullName
0x18002d1ae  call    cs:__imp_GetStagedPackageOrigin
0x18002d1b4  mov     eax, edi
0x18002d1b6  and     eax, 1
0x18002d1b9  bt      edi, 0Dh
0x18002d1bd  jnb     short loc_18002D1C7
0x18002d1bf  test    eax, eax
0x18002d1c1  jz      loc_18002D089
0x18002d1c7  bt      edi, 0Fh
0x18002d1cb  jnb     short loc_18002D1D5
0x18002d1cd  test    eax, eax
0x18002d1cf  jz      loc_18002D089
0x18002d1d5  bt      edi, 14h
0x18002d1d9  jnb     short loc_18002D1E3
0x18002d1db  test    eax, eax
0x18002d1dd  jz      loc_18002D089
0x18002d1e3  test    dil, 2
0x18002d1e7  jz      short loc_18002D1F7
0x18002d1e9  test    eax, eax
0x18002d1eb  jnz     short loc_18002D1F7
0x18002d1ed  bt      edi, 0Bh
0x18002d1f1  jnb     loc_18002D089
0x18002d1f7  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x18002d1fc  test    eax, eax
0x18002d1fe  jz      short loc_18002D212
0x18002d200  mov     eax, edi
0x18002d202  and     eax, 200001h
0x18002d207  cmp     eax, 200000h
0x18002d20c  jz      loc_18002D089
0x18002d212  mov     ebx, edi
0x18002d214  and     ebx, 10000h
0x18002d21a  call    Feature_AllowDisableProcessTreeBreakawayFlagForWin32alacarte__private_IsEnabledDeviceUsageNoInline
0x18002d21f  test    eax, eax
0x18002d221  jz      short loc_18002D241
0x18002d223  test    ebx, ebx
0x18002d225  jz      short loc_18002D233
0x18002d227  test    edi, 1A0h
0x18002d22d  jz      loc_18002D089
0x18002d233  test    edi, edi
0x18002d235  js      short loc_18002D24D
0x18002d237  mov     ebx, 0C00000F4h
0x18002d23c  jmp     loc_18002D850
0x18002d241  test    ebx, ebx
0x18002d243  jz      short loc_18002D233
0x18002d245  test    edi, 180h
0x18002d24b  jmp     short loc_18002D22D
0x18002d24d  xor     edx, edx; Val
0x18002d24f  lea     rcx, [rbp+3C0h+var_390]; void *
0x18002d253  mov     r8d, 0A0h; Size
0x18002d259  call    memset_0
0x18002d25e  mov     rdx, rsi; SourceString
0x18002d261  lea     rcx, [rbp+3C0h+DestinationString]; DestinationString
0x18002d268  call    cs:__imp_RtlInitUnicodeStringEx
0x18002d26e  mov     ebx, eax
0x18002d270  test    eax, eax
0x18002d272  js      loc_18002D850
0x18002d278  mov     rdx, r14; SourceString
0x18002d27b  lea     rcx, [rbp+3C0h+var_2E0]; DestinationString
0x18002d282  call    cs:__imp_RtlInitUnicodeStringEx
0x18002d288  mov     ebx, eax
0x18002d28a  test    eax, eax
0x18002d28c  js      loc_18002D850
0x18002d292  lea     r8, [rbp+3C0h+packageFamilyName]; packageFamilyName
0x18002d299  mov     [rbp+3C0h+packageFamilyNameLength], 41h ; 'A'
0x18002d2a0  lea     rdx, [rbp+3C0h+packageFamilyNameLength]; packageFamilyNameLength
0x18002d2a4  mov     rcx, rsi; packageFullName
0x18002d2a7  call    cs:__imp_PackageFamilyNameFromFullName
0x18002d2ad  mov     ebx, eax
0x18002d2af  test    eax, eax
0x18002d2b1  jz      short loc_18002D2C7
0x18002d2b3  jle     loc_18002D850
0x18002d2b9  movzx   ebx, ax
0x18002d2bc  or      ebx, 0C0070000h
0x18002d2c2  jmp     loc_18002D850
0x18002d2c7  lea     rdx, [rbp+3C0h+packageFamilyName]; SourceString
0x18002d2ce  lea     rcx, [rbp+3C0h+var_2D0]; DestinationString
0x18002d2d5  call    cs:__imp_RtlInitUnicodeStringEx
0x18002d2db  mov     ebx, eax
0x18002d2dd  test    eax, eax
0x18002d2df  js      loc_18002D850
0x18002d2e5  mov     ebx, 3
0x18002d2ea  mov     r14d, ebx
0x18002d2ed  bt      edi, 1Eh
0x18002d2f1  jnb     short loc_18002D347
0x18002d2f3  test    r12, r12
0x18002d2f6  jnz     short loc_18002D314
0x18002d2f8  lea     rcx, [rbp+3C0h+Buf2]; Uuid
0x18002d2fc  call    cs:__imp_UuidCreate
0x18002d302  test    eax, eax
0x18002d304  jz      short loc_18002D310
0x18002d306  mov     ebx, 0C0000001h
0x18002d30b  jmp     loc_18002D850
0x18002d310  lea     r12, [rbp+3C0h+Buf2]
0x18002d314  lea     rax, [rbp+3C0h+var_190]
0x18002d31b  xor     r8d, r8d
0x18002d31e  mov     [rbp+3C0h+var_2B8], rax
0x18002d325  lea     rdx, [rbp+3C0h+var_2C0]
0x18002d32c  mov     eax, 4Eh ; 'N'
0x18002d331  mov     rcx, r12
0x18002d334  mov     [rbp+3C0h+var_2BE], ax
0x18002d33b  call    cs:__imp_RtlStringFromGUIDEx
0x18002d341  mov     r14d, 4
0x18002d347  mov     rax, [rbp+3C0h+var_428]
0x18002d34b  lea     r9, [rsp+4C0h+ReturnedState]; ReturnedState
0x18002d350  mov     [rsp+4C0h+TokenHandle], rax
0x18002d355  lea     rcx, [rsp+4C0h+Privilege]; Privilege
0x18002d35a  mov     rax, [rbp+3C0h+var_408]
0x18002d35e  mov     esi, 1
0x18002d363  mov     [rbp+3C0h+var_38C], eax
0x18002d366  mov     edx, esi; NumPriv
0x18002d368  lea     rax, aWinSysappid; "WIN://SYSAPPID"
0x18002d36f  mov     [rbp+3C0h+var_3A0], ebx
0x18002d372  mov     [rbp+3C0h+var_388], rax
0x18002d376  lea     rax, [rbp+3C0h+var_390]
0x18002d37a  mov     qword ptr [rsp+4C0h+var_458+8], rax
0x18002d37f  lea     r8d, [rsi+1]; Flags
0x18002d383  lea     rax, [rsp+4C0h+var_458]
0x18002d388  mov     [rbp+3C0h+var_390], 1E001Ch
0x18002d38f  mov     qword ptr [rsp+4C0h+TokenInformation], rax
0x18002d394  lea     rax, [rbp+3C0h+var_3A0]
0x18002d398  mov     qword ptr [rbp+3C0h+TokenInformation+8], rax
0x18002d39c  mov     [rbp+3C0h+var_380], bx
0x18002d3a0  mov     [rbp+3C0h+var_370], r13
0x18002d3a4  mov     [rbp+3C0h+var_378], r13d
0x18002d3a8  mov     dword ptr [rsp+4C0h+var_458], esi
0x18002d3ac  mov     dword ptr [rsp+4C0h+var_458+4], esi
0x18002d3b0  call    cs:__imp_RtlAcquirePrivilege
0x18002d3b6  mov     ebx, eax
0x18002d3b8  test    eax, eax
0x18002d3ba  js      loc_18002D850
0x18002d3c0  mov     rcx, [rsp+4C0h+TokenHandle]; TokenHandle
0x18002d3c5  lea     r9d, [rsi+0Fh]; TokenInformationLength
0x18002d3c9  lea     r8, [rsp+4C0h+TokenInformation]; TokenInformation
0x18002d3ce  lea     edx, [rsi+26h]; TokenInformationClass
0x18002d3d1  call    cs:__imp_NtSetInformationToken
0x18002d3d7  mov     rcx, [rsp+4C0h+ReturnedState]; ReturnedState
0x18002d3dc  mov     ebx, eax
0x18002d3de  call    cs:__imp_RtlReleasePrivilege
0x18002d3e4  mov     ecx, 80000000h
0x18002d3e9  lea     eax, [rbx+rcx]
0x18002d3ec  test    ecx, eax
0x18002d3ee  jnz     short loc_18002D3FC
0x18002d3f0  cmp     ebx, 0C0000225h
0x18002d3f6  jnz     loc_18002D850
0x18002d3fc  mov     rax, [rbp+3C0h+var_3E0]
0x18002d400  lea     r9, [rsp+4C0h+ReturnedState]; ReturnedState
0x18002d405  mov     [rbp+3C0h+var_38C], eax
0x18002d408  mov     ecx, 3
0x18002d40d  lea     rax, aWinSysappgroup; "WIN://SYSAPPGROUPID"
0x18002d414  mov     [rbp+3C0h+var_3A0], ecx
0x18002d417  mov     [rbp+3C0h+var_388], rax
0x18002d41b  mov     edx, esi; NumPriv
0x18002d41d  lea     rax, [rbp+3C0h+var_390]
0x18002d421  mov     [rbp+3C0h+var_380], cx
0x18002d425  mov     qword ptr [rsp+4C0h+var_458+8], rax
0x18002d42a  lea     r8d, [rcx-1]; Flags
0x18002d42e  lea     rax, [rsp+4C0h+var_458]
0x18002d433  mov     [rbp+3C0h+var_390], 280026h
0x18002d43a  mov     qword ptr [rsp+4C0h+TokenInformation], rax
0x18002d43f  lea     rcx, [rsp+4C0h+Privilege]; Privilege
0x18002d444  lea     rax, [rbp+3C0h+var_3A0]
0x18002d448  mov     [rbp+3C0h+var_370], r13
0x18002d44c  mov     qword ptr [rbp+3C0h+TokenInformation+8], rax
0x18002d450  mov     [rbp+3C0h+var_378], r13d
0x18002d454  mov     dword ptr [rsp+4C0h+var_458], esi
0x18002d458  mov     dword ptr [rsp+4C0h+var_458+4], esi
0x18002d45c  call    cs:__imp_RtlAcquirePrivilege
0x18002d462  mov     ebx, eax
0x18002d464  test    eax, eax
0x18002d466  js      loc_18002D850
0x18002d46c  mov     rcx, [rsp+4C0h+TokenHandle]; TokenHandle
0x18002d471  lea     r8, [rsp+4C0h+TokenInformation]; TokenInformation
0x18002d476  mov     r9d, 10h; TokenInformationLength
0x18002d47c  lea     edx, [r9+17h]; TokenInformationClass
0x18002d480  call    cs:__imp_NtSetInformationToken
0x18002d486  mov     rcx, [rsp+4C0h+ReturnedState]; ReturnedState
0x18002d48b  mov     ebx, eax
0x18002d48d  call    cs:__imp_RtlReleasePrivilege
0x18002d493  mov     ecx, 80000000h
0x18002d498  lea     eax, [rbx+rcx]
0x18002d49b  test    ecx, eax
0x18002d49d  jnz     short loc_18002D4AB
0x18002d49f  cmp     ebx, 0C0000225h
0x18002d4a5  jnz     loc_18002D850
  ... truncated ...
```
