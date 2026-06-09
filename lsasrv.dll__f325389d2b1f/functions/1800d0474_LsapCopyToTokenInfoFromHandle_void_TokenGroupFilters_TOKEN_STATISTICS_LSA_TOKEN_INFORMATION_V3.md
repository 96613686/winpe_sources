# LsapCopyToTokenInfoFromHandle(void *,TokenGroupFilters,_TOKEN_STATISTICS *,_LSA_TOKEN_INFORMATION_V3 * *)

- ea: `0x1800d0474`
- end: `0x1800d0cfe`
- name: `?LsapCopyToTokenInfoFromHandle@@YAJPEAXW4TokenGroupFilters@@PEAU_TOKEN_STATISTICS@@PEAPEAU_LSA_TOKEN_INFORMATION_V3@@@Z`
- size: `2186`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d0d04`
- `0x1800d13c0`

## callees

- `0x180009330`
- `0x180016f70`
- `0x180056f84`
- `0x18005af38`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bd6e0`
- `0x1800d0474`
- `0x1801234f4`
- `0x180123580`
- `0x18012cf40`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800d0aa4`
- `ntdll!RtlCopySid` at `0x1800d0bcf`
- `ntdll!RtlCopySid` at `0x1800d0aa4`
- `ntdll!RtlCopySid` at `0x1800d0bcf`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800d0a26`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800d0b64`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800d0a26`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800d0b64`
- `ntdll!RtlLengthSid` at `0x1800d0a8c`
- `ntdll!RtlLengthSid` at `0x1800d0bb7`
- `ntdll!RtlLengthSid` at `0x1800d0c14`
- `ntdll!RtlLengthSid` at `0x1800d0c3a`
- `ntdll!RtlLengthSid` at `0x1800d0c5e`
- `ntdll!RtlLengthSid` at `0x1800d0a8c`
- `ntdll!RtlLengthSid` at `0x1800d0bb7`
- `ntdll!RtlLengthSid` at `0x1800d0c14`
- `ntdll!RtlLengthSid` at `0x1800d0c3a`
- `ntdll!RtlLengthSid` at `0x1800d0c5e`
- `ntdll!RtlEqualSid` at `0x1800d0a4a`
- `ntdll!RtlEqualSid` at `0x1800d0b88`
- `ntdll!RtlEqualSid` at `0x1800d0a4a`
- `ntdll!RtlEqualSid` at `0x1800d0b88`
- `ntdll!NtQueryInformationToken` at `0x1800d0565`
- `ntdll!NtQueryInformationToken` at `0x1800d059b`
- `ntdll!NtQueryInformationToken` at `0x1800d05ca`
- `ntdll!NtQueryInformationToken` at `0x1800d0610`
- `ntdll!NtQueryInformationToken` at `0x1800d064d`
- `ntdll!NtQueryInformationToken` at `0x1800d0689`
- `ntdll!NtQueryInformationToken` at `0x1800d06d2`
- `ntdll!NtQueryInformationToken` at `0x1800d081e`
- `ntdll!NtQueryInformationToken` at `0x1800d0882`
- `ntdll!NtQueryInformationToken` at `0x1800d08ff`
- `ntdll!NtQueryInformationToken` at `0x1800d0993`
- `ntdll!NtQueryInformationToken` at `0x1800d09c8`
- `ntdll!NtQueryInformationToken` at `0x1800d0b09`
- `ntdll!NtQueryInformationToken` at `0x1800d0565`
- `ntdll!NtQueryInformationToken` at `0x1800d059b`
- `ntdll!NtQueryInformationToken` at `0x1800d05ca`
- `ntdll!NtQueryInformationToken` at `0x1800d0610`
- `ntdll!NtQueryInformationToken` at `0x1800d064d`
- `ntdll!NtQueryInformationToken` at `0x1800d0689`
- `ntdll!NtQueryInformationToken` at `0x1800d06d2`
- `ntdll!NtQueryInformationToken` at `0x1800d081e`
- `ntdll!NtQueryInformationToken` at `0x1800d0882`
- `ntdll!NtQueryInformationToken` at `0x1800d08ff`
- `ntdll!NtQueryInformationToken` at `0x1800d0993`
- `ntdll!NtQueryInformationToken` at `0x1800d09c8`
- `ntdll!NtQueryInformationToken` at `0x1800d0b09`

## pseudocode

```c
__int64 __fastcall LsapCopyToTokenInfoFromHandle(void *a1, int a2, int *a3, _QWORD *a4)
{
  struct _CLAIM_SECURITY_ATTRIBUTES_INFORMATION *p_TokenInformationLength; // r14
  void *v6; // rdi
  char *v7; // r15
  int *v8; // rax
  NTSTATUS v9; // esi
  ULONG v10; // ebx
  ULONG v11; // ebx
  NTSTATUS v12; // eax
  ULONG v13; // ebx
  NTSTATUS v14; // eax
  ULONG v15; // ebx
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  ULONG v18; // eax
  ULONG v19; // r13d
  NTSTATUS v20; // eax
  __int64 v21; // r9
  ULONG v22; // ecx
  ULONG v23; // edx
  ULONG v24; // eax
  ULONG v25; // eax
  ULONG v26; // r12d
  ULONG v27; // eax
  unsigned __int64 v28; // r8
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // rcx
  void *v31; // rsp
  void *v32; // rsp
  _DWORD *v33; // rax
  _QWORD *v34; // r13
  char *v35; // rbx
  __int64 v36; // r13
  int v37; // edx
  unsigned int v38; // eax
  _DWORD *v39; // r8
  char *v40; // r13
  int v41; // edi
  _DWORD *v42; // r15
  unsigned int v43; // r12d
  unsigned int v44; // esi
  __int64 v45; // rcx
  ULONG v46; // eax
  __int64 v47; // rbx
  int v48; // edx
  _DWORD *v49; // r12
  unsigned int v50; // r13d
  unsigned int v51; // eax
  char *v52; // r15
  unsigned int v53; // esi
  __int64 v54; // rcx
  ULONG v55; // eax
  __int64 v56; // rbx
  ULONG v57; // eax
  ULONG v58; // eax
  ULONG v59; // eax
  __int64 v61; // [rsp+0h] [rbp-30h] BYREF
  ULONG TokenInformationLength; // [rsp+30h] [rbp+0h] BYREF
  ULONG v63; // [rsp+34h] [rbp+4h] BYREF
  unsigned int v64; // [rsp+38h] [rbp+8h] BYREF
  ULONG v65; // [rsp+3Ch] [rbp+Ch] BYREF
  ULONG v66; // [rsp+40h] [rbp+10h] BYREF
  ULONG v67; // [rsp+44h] [rbp+14h] BYREF
  ULONG v68; // [rsp+48h] [rbp+18h] BYREF
  ULONG v69; // [rsp+4Ch] [rbp+1Ch]
  int v70; // [rsp+50h] [rbp+20h]
  NTSTATUS v71; // [rsp+54h] [rbp+24h]
  ULONG ReturnLength; // [rsp+58h] [rbp+28h] BYREF
  ULONG v73; // [rsp+5Ch] [rbp+2Ch] BYREF
  PSID DestinationSid; // [rsp+60h] [rbp+30h]
  PVOID v75; // [rsp+68h] [rbp+38h]
  __int64 v76; // [rsp+70h] [rbp+40h]
  __int128 v77; // [rsp+78h] [rbp+48h] BYREF
  __int128 v78; // [rsp+88h] [rbp+58h] BYREF
  void *v79; // [rsp+98h] [rbp+68h]
  _QWORD *v80; // [rsp+A0h] [rbp+70h]
  void *TokenInformation[12]; // [rsp+B0h] [rbp+80h] BYREF
  PSID Sid[10]; // [rsp+110h] [rbp+E0h] BYREF
  int v83; // [rsp+160h] [rbp+130h] BYREF
  __int128 v84; // [rsp+164h] [rbp+134h]
  __int128 v85; // [rsp+174h] [rbp+144h]
  __int128 v86; // [rsp+184h] [rbp+154h]
  int v87; // [rsp+194h] [rbp+164h]

  p_TokenInformationLength = 0;
  v70 = a2;
  v79 = a1;
  v6 = a1;
  v80 = a4;
  ReturnLength = 0;
  v73 = 0;
  v68 = 0;
  v66 = 0;
  v67 = 0;
  v65 = 0;
  v63 = 0;
  v7 = 0;
  TokenInformationLength = 0;
  v77 = 0;
  v78 = 0;
  memset_0(TokenInformation, 0, 0x58u);
  memset_0(Sid, 0, sizeof(Sid));
  v83 = 0;
  v87 = 0;
  v8 = &v83;
  if ( a3 )
    v8 = a3;
  v75 = v8;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v9 = NtQueryInformationToken(v6, TokenUser, TokenInformation, 0x58u, &ReturnLength);
  if ( v9 >= 0 )
  {
    v10 = ReturnLength + 72;
    v9 = NtQueryInformationToken(v6, TokenPrimaryGroup, Sid, 0x50u, &v73);
    if ( v9 >= 0 )
    {
      v11 = v73 + v10;
      v12 = NtQueryInformationToken(v6, TokenGroups, 0, 0, &v68);
      v9 = v12;
      if ( v12 == -2147483643 || v12 == -1073741789 )
      {
        v13 = v68 - 8 + v11;
        v14 = NtQueryInformationToken(v6, TokenPrivileges, 0, 0, &v67);
        v9 = v14;
        if ( v14 == -2147483643 || v14 == -1073741789 )
        {
          v15 = ((v67 + 7) & 0xFFFFFFF8) + v13;
          v16 = NtQueryInformationToken(v6, TokenDeviceClaimAttributes, 0, 0, &v63);
          v9 = v16;
          if ( v16 == -2147483643 || v16 == -1073741789 )
          {
            if ( v63 == 16 )
              v63 = 0;
            v17 = NtQueryInformationToken(v6, TokenDeviceGroups, 0, 0, &v66);
            v9 = v17;
            if ( v17 == -2147483643 || v17 == -1073741789 )
            {
              v18 = v66;
              if ( v66 == 24 )
              {
                v18 = 0;
                v66 = 0;
              }
              else
              {
                v15 += 8;
              }
              v19 = v18 + v15;
              v20 = NtQueryInformationToken(v6, TokenUserClaimAttributes, 0, 0, &v65);
              v9 = v20;
              if ( v20 == -2147483643 || v20 == -1073741789 )
              {
                v22 = v65;
                if ( v65 == 16 )
                {
                  v22 = 0;
                  v65 = 0;
                }
                v23 = v63;
                v24 = v63;
                if ( v22 > v63 )
                  v24 = v22;
                if ( v66 <= v24 )
                {
                  v25 = v63;
                  if ( v22 > v63 )
                    v25 = v22;
                }
                else
                {
                  v25 = v66;
                }
                v26 = v68;
                v69 = v68;
                if ( v68 <= v25 )
                {
                  v27 = v63;
                  if ( v22 > v63 )
                    v27 = v22;
                  if ( v66 <= v27 )
                  {
                    v26 = v63;
                    if ( v22 > v63 )
                      v26 = v22;
                    v69 = v26;
                  }
                  else
                  {
                    v26 = v66;
                    v69 = v66;
                  }
                }
                TokenInformationLength = v26;
                if ( v26 )
                {
                  if ( v26 <= (unsigned __int64)g_ulMaxStackAllocSize )
                  {
                    v28 = v26 + g_ulAdditionalProbeSize + 8;
                    if ( v28 >= v26 )
                    {
                      if ( (unsigned int)VerifyStackAvailable(v26 + g_ulAdditionalProbeSize + 8, v63, v28, v21) )
                      {
                        v29 = v26 + 23LL;
                        if ( v29 <= (unsigned __int64)v26 + 8 )
                          v29 = 0xFFFFFFFFFFFFFF0LL;
                        v30 = v29 & 0xFFFFFFFFFFFFFFF0uLL;
                        v31 = alloca(v30);
                        v32 = alloca(v30);
                        p_TokenInformationLength = (struct _CLAIM_SECURITY_ATTRIBUTES_INFORMATION *)&TokenInformationLength;
                        if ( &v61 != (__int64 *)-48LL )
                        {
                          TokenInformationLength = 1801679955;
                          p_TokenInformationLength = (struct _CLAIM_SECURITY_ATTRIBUTES_INFORMATION *)&v64;
                          if ( &v64 )
                            goto LABEL_48;
                        }
                      }
                      v22 = v65;
                      v23 = v63;
                    }
                  }
                }
                if ( (unsigned __int64)v26 + 8 < v26 )
                  goto LABEL_49;
                v33 = (_DWORD *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(v26 + 8LL);
                p_TokenInformationLength = (struct _CLAIM_SECURITY_ATTRIBUTES_INFORMATION *)v33;
                if ( v33 )
                {
                  *v33 = 1885431112;
                  p_TokenInformationLength = (struct _CLAIM_SECURITY_ATTRIBUTES_INFORMATION *)(v33 + 2);
                }
LABEL_48:
                v23 = v63;
                v22 = v65;
LABEL_49:
                if ( !p_TokenInformationLength )
                {
                  v9 = -1073741801;
                  goto LABEL_92;
                }
                if ( v22 )
                {
                  v9 = NtQueryInformationToken(
                         v6,
                         TokenUserClaimAttributes,
                         p_TokenInformationLength,
                         TokenInformationLength,
                         &TokenInformationLength);
                  if ( v9 < 0 )
                    goto LABEL_90;
                  v9 = LsapSamExtConvertSecurityAttributesToClaimsBlob(
                         TokenInformation[0],
                         p_TokenInformationLength,
                         (struct _SAM_CLAIMS_BLOB *)&v77);
                  if ( v9 < 0 )
                    goto LABEL_90;
                  v23 = v63;
                  v19 += ((v77 + 7) & 0xFFFFFFF8) + 16;
                }
                if ( v23 )
                {
                  TokenInformationLength = v26;
                  v9 = NtQueryInformationToken(
                         v6,
                         TokenDeviceClaimAttributes,
                         p_TokenInformationLength,
                         v26,
                         &TokenInformationLength);
                  if ( v9 < 0 )
                    goto LABEL_90;
                  v9 = LsapSamExtConvertSecurityAttributesToClaimsBlob(
                         TokenInformation[0],
                         p_TokenInformationLength,
                         (struct _SAM_CLAIMS_BLOB *)&v78);
                  if ( v9 < 0 )
                    goto LABEL_90;
                  v19 += ((v78 + 7) & 0xFFFFFFF8) + 16;
                }
                v76 = LsapAllocate(v19);
                v7 = (char *)v76;
                if ( !v76 )
                {
                  v9 = -1073741801;
                  goto LABEL_90;
                }
                v34 = v75;
                v9 = NtQueryInformationToken(v6, TokenStatistics, v75, 0x38u, &TokenInformationLength);
                if ( v9 < 0 )
                  goto LABEL_90;
                v35 = v7 + 88;
                *(_QWORD *)v7 = v34[2];
                if ( *((_QWORD *)&v77 + 1) )
                {
                  *((_QWORD *)v7 + 8) = v35;
                  LsapDuplicateClaimsBlob(v7 + 88, &v77);
                  v35 += (((unsigned int)v77 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + 16;
                }
                if ( *((_QWORD *)&v78 + 1) )
                {
                  *((_QWORD *)v7 + 9) = v35;
                  LsapDuplicateClaimsBlob(v35, &v78);
                  v35 += (((unsigned int)v78 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL) + 16;
                }
                *((_QWORD *)v7 + 5) = v35;
                TokenInformationLength = v67;
                v9 = NtQueryInformationToken(v6, TokenPrivileges, *((PVOID *)v7 + 5), v67, &TokenInformationLength);
                if ( v9 < 0 )
                  goto LABEL_90;
                v36 = v67;
                TokenInformationLength = v26;
                v71 = NtQueryInformationToken(v6, TokenGroups, p_TokenInformationLength, v26, &TokenInformationLength);
                v9 = v71;
                if ( v71 < 0 )
                  goto LABEL_90;
                v37 = *(_DWORD *)&p_TokenInformationLength->Version;
                v38 = 0;
                v39 = (_DWORD *)((unsigned __int64)&v35[v36 + 7] & 0xFFFFFFFFFFFFFFF8uLL);
                v75 = v39;
                v40 = (char *)&v39[4 * (v37 - 1) + 6];
                if ( v37 )
                {
                  v41 = v70;
                  v42 = v39;
                  v43 = 0;
                  v44 = 0;
                  do
                  {
                    if ( v41 == 2
                      || (*RtlSubAuthorityCountSid(p_TokenInformationLength[v43].Attribute.pAttributeV1) > 2u
                       || RtlEqualSid(
                            *((PSID *)WellKnownSids + 282),
                            p_TokenInformationLength[v43].Attribute.pAttributeV1))
                      && (v41 != 1 || !LsapIsSidLogonSid(p_TokenInformationLength[v43].Attribute.pAttributeV1)) )
                    {
                      v45 = 2LL * v44;
                      v42[2 * v45 + 4] = *(_DWORD *)&p_TokenInformationLength[v43 + 1].Version;
                      *(_QWORD *)&v42[2 * v45 + 2] = v40;
                      v46 = RtlLengthSid(p_TokenInformationLength[v43].Attribute.pAttributeV1);
                      v47 = v46;
                      RtlCopySid(v46, v40, p_TokenInformationLength[v43].Attribute.pAttributeV1);
                      v41 = v70;
                      v40 += v47;
                      ++v44;
                    }
                    ++v43;
                  }
                  while ( v43 < *(_DWORD *)&p_TokenInformationLength->Version );
                  v7 = (char *)v76;
                  v26 = v69;
                  v6 = v79;
                  v39 = v75;
                  v64 = v44;
                  v38 = v44;
                  v9 = v71;
                }
                *v39 = v38;
                *((_QWORD *)v7 + 3) = v39;
                if ( v66 )
                {
                  TokenInformationLength = v26;
                  v71 = NtQueryInformationToken(
                          v6,
                          TokenDeviceGroups,
                          p_TokenInformationLength,
                          v26,
                          &TokenInformationLength);
                  v9 = v71;
                  if ( v71 < 0 )
                    goto LABEL_90;
                  v48 = *(_DWORD *)&p_TokenInformationLength->Version;
                  v49 = (_DWORD *)((unsigned __int64)(v40 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
                  v50 = 0;
                  DestinationSid = &v49[4 * (*(_DWORD *)&p_TokenInformationLength->Version - 1) + 6];
                  v51 = 0;
                  if ( v48 )
                  {
                    v52 = (char *)DestinationSid;
                    v53 = 0;
                    do
                    {
                      if ( v70 == 2
                        || *RtlSubAuthorityCountSid(p_TokenInformationLength[v50].Attribute.pAttributeV1) > 2u
                        || RtlEqualSid(
                             *((PSID *)WellKnownSids + 282),
                             p_TokenInformationLength[v50].Attribute.pAttributeV1) )
                      {
                        v54 = 2LL * v53;
                        v49[2 * v54 + 4] = *(_DWORD *)&p_TokenInformationLength[v50 + 1].Version;
                        *(_QWORD *)&v49[2 * v54 + 2] = v52;
                        v55 = RtlLengthSid(p_TokenInformationLength[v50].Attribute.pAttributeV1);
                        v56 = v55;
                        RtlCopySid(v55, v52, p_TokenInformationLength[v50].Attribute.pAttributeV1);
                        v52 += v56;
                        ++v53;
                      }
                      ++v50;
                    }
                    while ( v50 < *(_DWORD *)&p_TokenInformationLength->Version );
                    v64 = v53;
                    v51 = v53;
                    v9 = v71;
                    DestinationSid = v52;
                    v7 = (char *)v76;
                  }
                  v40 = (char *)DestinationSid;
                  *v49 = v51;
                  *((_QWORD *)v7 + 10) = v49;
                }
                *((_QWORD *)v7 + 4) = v40;
                v57 = RtlLengthSid(Sid[0]);
                memcpy_0(*((void **)v7 + 4), Sid[0], v57);
                v58 = RtlLengthSid(Sid[0]);
                *((_DWORD *)v7 + 4) = 0;
                *((_QWORD *)v7 + 1) = &v40[v58];
                v59 = RtlLengthSid(TokenInformation[0]);
                memcpy_0(*((void **)v7 + 1), TokenInformation[0], v59);
                *v80 = v7;
                v7 = 0;
LABEL_90:
                if ( LODWORD(p_TokenInformationLength[-1].Attribute.pAttributeV1) == 1885431112 )
                  ((void (*)(void))g_pfnFree)();
              }
            }
          }
        }
      }
    }
  }
LABEL_92:
  if ( *((_QWORD *)&v77 + 1) )
    LsapSamExtFreeClaimsBlob((struct _SAM_CLAIMS_BLOB *)&v77);
  if ( *((_QWORD *)&v78 + 1) )
    LsapSamExtFreeClaimsBlob((struct _SAM_CLAIMS_BLOB *)&v78);
  if ( v7 )
    LsapFreeTokenInformation(LsaTokenInformationV3, v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800d0474  push    rbp
0x1800d0476  push    rsi
0x1800d0477  push    rdi
0x1800d0478  push    r12
0x1800d047a  push    r13
0x1800d047c  push    r14
0x1800d047e  push    r15
0x1800d0480  sub     rsp, 1A0h
0x1800d0487  lea     rbp, [rsp+30h]
0x1800d048c  mov     [rbp+1A0h+arg_8], rbx
0x1800d0493  mov     rax, cs:__security_cookie
0x1800d049a  xor     rax, rbp
0x1800d049d  mov     [rbp+1A0h+var_38], rax
0x1800d04a4  xor     r14d, r14d
0x1800d04a7  mov     [rbp+1A0h+var_180], edx
0x1800d04aa  mov     rbx, r8
0x1800d04ad  mov     [rbp+1A0h+var_138], rcx
0x1800d04b1  mov     rdi, rcx
0x1800d04b4  mov     [rbp+1A0h+var_130], r9
0x1800d04b8  xorps   xmm0, xmm0
0x1800d04bb  mov     [rbp+1A0h+var_178], r14d
0x1800d04bf  xorps   xmm1, xmm1
0x1800d04c2  mov     [rbp+1A0h+var_174], r14d
0x1800d04c6  lea     esi, [r14+58h]
0x1800d04ca  mov     [rbp+1A0h+var_188], r14d
0x1800d04ce  mov     r8d, esi; Size
0x1800d04d1  mov     [rbp+1A0h+var_190], r14d
0x1800d04d5  xor     edx, edx; Val
0x1800d04d7  mov     [rbp+1A0h+var_18C], r14d
0x1800d04db  lea     rcx, [rbp+1A0h+TokenInformation]; void *
0x1800d04e2  mov     [rbp+1A0h+var_194], r14d
0x1800d04e6  mov     [rbp+1A0h+var_19C], r14d
0x1800d04ea  mov     r15d, r14d
0x1800d04ed  mov     [rbp+1A0h+TokenInformationLength], r14d
0x1800d04f1  movups  [rbp+1A0h+var_158], xmm0
0x1800d04f5  movups  [rbp+1A0h+var_148], xmm1
0x1800d04f9  call    memset_0
0x1800d04fe  lea     r12d, [r14+50h]
0x1800d0502  xor     edx, edx; Val
0x1800d0504  mov     r8d, r12d; Size
0x1800d0507  lea     rcx, [rbp+1A0h+Sid]; void *
0x1800d050e  call    memset_0
0x1800d0513  xor     eax, eax
0x1800d0515  mov     [rbp+1A0h+var_70], r14d
0x1800d051c  mov     [rbp+1A0h+var_3C], eax
0x1800d0522  lea     r8, [rbp+1A0h+TokenInformation]; TokenInformation
0x1800d0529  xorps   xmm0, xmm0
0x1800d052c  lea     rax, [rbp+1A0h+var_70]
0x1800d0533  test    rbx, rbx
0x1800d0536  lea     edx, [rsi-57h]; TokenInformationClass
0x1800d0539  mov     r9d, esi; TokenInformationLength
0x1800d053c  mov     rcx, rdi; TokenHandle
0x1800d053f  cmovnz  rax, rbx
0x1800d0543  mov     [rbp+1A0h+var_168], rax
0x1800d0547  lea     rax, [rbp+1A0h+var_178]
0x1800d054b  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x1800d0550  movups  [rbp+1A0h+var_6C], xmm0
0x1800d0557  movups  [rbp+1A0h+var_5C], xmm0
0x1800d055e  movups  [rbp+1A0h+var_4C], xmm0
0x1800d0565  call    cs:__imp_NtQueryInformationToken
0x1800d056c  nop     dword ptr [rax+rax+00h]
0x1800d0571  mov     esi, eax
0x1800d0573  test    eax, eax
0x1800d0575  js      loc_1800D0CA2
0x1800d057b  mov     ebx, [rbp+1A0h+var_178]
0x1800d057e  lea     rax, [rbp+1A0h+var_174]
0x1800d0582  mov     r9d, r12d; TokenInformationLength
0x1800d0585  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x1800d058a  lea     r8, [rbp+1A0h+Sid]; TokenInformation
0x1800d0591  mov     rcx, rdi; TokenHandle
0x1800d0594  lea     edx, [r14+5]; TokenInformationClass
0x1800d0598  add     ebx, 48h ; 'H'
0x1800d059b  call    cs:__imp_NtQueryInformationToken
0x1800d05a2  nop     dword ptr [rax+rax+00h]
0x1800d05a7  mov     esi, eax
0x1800d05a9  test    eax, eax
0x1800d05ab  js      loc_1800D0CA2
0x1800d05b1  add     ebx, [rbp+1A0h+var_174]
0x1800d05b4  lea     rax, [rbp+1A0h+var_188]
0x1800d05b8  xor     r9d, r9d; TokenInformationLength
0x1800d05bb  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x1800d05c0  xor     r8d, r8d; TokenInformation
0x1800d05c3  lea     edx, [r14+2]; TokenInformationClass
0x1800d05c7  mov     rcx, rdi; TokenHandle
0x1800d05ca  call    cs:__imp_NtQueryInformationToken
0x1800d05d1  nop     dword ptr [rax+rax+00h]
0x1800d05d6  mov     r13d, 80000005h
0x1800d05dc  mov     r12d, 0C0000023h
0x1800d05e2  mov     esi, eax
0x1800d05e4  cmp     eax, r13d
0x1800d05e7  jz      short loc_1800D05F2
0x1800d05e9  cmp     eax, r12d
0x1800d05ec  jnz     loc_1800D0CA2
0x1800d05f2  mov     eax, [rbp+1A0h+var_188]
0x1800d05f5  xor     r9d, r9d; TokenInformationLength
0x1800d05f8  add     eax, 0FFFFFFF8h
0x1800d05fb  xor     r8d, r8d; TokenInformation
0x1800d05fe  add     ebx, eax
0x1800d0600  mov     rcx, rdi; TokenHandle
0x1800d0603  lea     rax, [rbp+1A0h+var_18C]
0x1800d0607  lea     edx, [r9+3]; TokenInformationClass
0x1800d060b  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x1800d0610  call    cs:__imp_NtQueryInformationToken
0x1800d0617  nop     dword ptr [rax+rax+00h]
0x1800d061c  mov     esi, eax
0x1800d061e  cmp     eax, r13d
0x1800d0621  jz      short loc_1800D062C
0x1800d0623  cmp     eax, r12d
0x1800d0626  jnz     loc_1800D0CA2
0x1800d062c  mov     eax, [rbp+1A0h+var_18C]
0x1800d062f  xor     r9d, r9d; TokenInformationLength
0x1800d0632  add     eax, 7
0x1800d0635  xor     r8d, r8d; TokenInformation
0x1800d0638  and     eax, 0FFFFFFF8h
0x1800d063b  mov     rcx, rdi; TokenHandle
0x1800d063e  add     ebx, eax
0x1800d0640  lea     rax, [rbp+1A0h+var_19C]
0x1800d0644  lea     edx, [r9+22h]; TokenInformationClass
0x1800d0648  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x1800d064d  call    cs:__imp_NtQueryInformationToken
0x1800d0654  nop     dword ptr [rax+rax+00h]
0x1800d0659  mov     esi, eax
0x1800d065b  cmp     eax, r13d
0x1800d065e  jz      short loc_1800D0669
0x1800d0660  cmp     eax, r12d
0x1800d0663  jnz     loc_1800D0CA2
0x1800d0669  cmp     [rbp+1A0h+var_19C], 10h
0x1800d066d  jnz     short loc_1800D0673
0x1800d066f  mov     [rbp+1A0h+var_19C], r14d
0x1800d0673  xor     r9d, r9d; TokenInformationLength
0x1800d0676  lea     rax, [rbp+1A0h+var_190]
0x1800d067a  xor     r8d, r8d; TokenInformation
0x1800d067d  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x1800d0682  mov     rcx, rdi; TokenHandle
0x1800d0685  lea     edx, [r9+25h]; TokenInformationClass
0x1800d0689  call    cs:__imp_NtQueryInformationToken
0x1800d0690  nop     dword ptr [rax+rax+00h]
0x1800d0695  mov     esi, eax
0x1800d0697  cmp     eax, r13d
0x1800d069a  jz      short loc_1800D06A5
0x1800d069c  cmp     eax, r12d
0x1800d069f  jnz     loc_1800D0CA2
0x1800d06a5  mov     eax, [rbp+1A0h+var_190]
0x1800d06a8  cmp     eax, 18h
0x1800d06ab  jnz     short loc_1800D06B5
0x1800d06ad  mov     eax, r14d
0x1800d06b0  mov     [rbp+1A0h+var_190], eax
0x1800d06b3  jmp     short loc_1800D06B8
0x1800d06b5  add     ebx, 8
0x1800d06b8  xor     r9d, r9d; TokenInformationLength
0x1800d06bb  lea     r13d, [rax+rbx]
0x1800d06bf  lea     rax, [rbp+1A0h+var_194]
0x1800d06c3  xor     r8d, r8d; TokenInformation
0x1800d06c6  mov     rcx, rdi; TokenHandle
0x1800d06c9  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x1800d06ce  lea     edx, [r9+21h]; TokenInformationClass
0x1800d06d2  call    cs:__imp_NtQueryInformationToken
0x1800d06d9  nop     dword ptr [rax+rax+00h]
0x1800d06de  mov     esi, eax
0x1800d06e0  cmp     eax, 80000005h
0x1800d06e5  jz      short loc_1800D06F0
0x1800d06e7  cmp     eax, r12d
0x1800d06ea  jnz     loc_1800D0CA2
0x1800d06f0  mov     ecx, [rbp+1A0h+var_194]
0x1800d06f3  cmp     ecx, 10h
0x1800d06f6  jnz     short loc_1800D06FE
0x1800d06f8  mov     ecx, r14d
0x1800d06fb  mov     [rbp+1A0h+var_194], ecx
0x1800d06fe  mov     edx, [rbp+1A0h+var_19C]
0x1800d0701  mov     eax, edx
0x1800d0703  mov     r8d, [rbp+1A0h+var_190]
0x1800d0707  cmp     ecx, edx
0x1800d0709  cmova   eax, ecx
0x1800d070c  cmp     r8d, eax
0x1800d070f  jbe     short loc_1800D0716
0x1800d0711  mov     eax, r8d
0x1800d0714  jmp     short loc_1800D071D
0x1800d0716  cmp     ecx, edx
0x1800d0718  mov     eax, edx
0x1800d071a  cmova   eax, ecx
0x1800d071d  mov     r12d, [rbp+1A0h+var_188]
0x1800d0721  mov     [rbp+1A0h+var_184], r12d
0x1800d0725  cmp     r12d, eax
0x1800d0728  ja      short loc_1800D074C
0x1800d072a  cmp     ecx, edx
0x1800d072c  mov     eax, edx
0x1800d072e  cmova   eax, ecx
0x1800d0731  cmp     r8d, eax
0x1800d0734  jbe     short loc_1800D073F
0x1800d0736  mov     r12d, r8d
0x1800d0739  mov     [rbp+1A0h+var_184], r8d
0x1800d073d  jmp     short loc_1800D074C
0x1800d073f  cmp     ecx, edx
0x1800d0741  mov     r12d, edx
0x1800d0744  cmova   r12d, ecx
0x1800d0748  mov     [rbp+1A0h+var_184], r12d
0x1800d074c  mov     [rbp+1A0h+TokenInformationLength], r12d
0x1800d0750  mov     ebx, r12d
0x1800d0753  test    r12d, r12d
0x1800d0756  jz      short loc_1800D07C3
0x1800d0758  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800d075f  ja      short loc_1800D07C3
0x1800d0761  mov     r8, cs:g_ulAdditionalProbeSize
0x1800d0768  add     r8, 8
0x1800d076c  add     r8, rbx
0x1800d076f  cmp     r8, rbx
0x1800d0772  jb      short loc_1800D07C3
0x1800d0774  mov     rcx, r8
0x1800d0777  call    VerifyStackAvailable
0x1800d077c  test    eax, eax
0x1800d077e  jz      short loc_1800D07BD
0x1800d0780  lea     rax, [rbx+8]
0x1800d0784  lea     rcx, [rax+0Fh]
0x1800d0788  cmp     rcx, rax
0x1800d078b  ja      short loc_1800D0797
0x1800d078d  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800d0797  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800d079b  mov     rax, rcx
0x1800d079e  call    _alloca_probe
0x1800d07a3  sub     rsp, rcx
0x1800d07a6  lea     r14, [rsp+1D0h+TokenInformationLength]
0x1800d07ab  test    r14, r14
0x1800d07ae  jz      short loc_1800D07BD
0x1800d07b0  mov     dword ptr [r14], 6B637453h
0x1800d07b7  add     r14, 8
0x1800d07bb  jnz     short loc_1800D07ED
0x1800d07bd  mov     ecx, [rbp+1A0h+var_194]
0x1800d07c0  mov     edx, [rbp+1A0h+var_19C]
0x1800d07c3  lea     rax, [rbx+8]
0x1800d07c7  cmp     rax, rbx
0x1800d07ca  jb      short loc_1800D07F3
0x1800d07cc  mov     rcx, rax
0x1800d07cf  mov     rax, cs:g_pfnAllocate
0x1800d07d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d07db  mov     r14, rax
0x1800d07de  test    rax, rax
0x1800d07e1  jz      short loc_1800D07ED
0x1800d07e3  mov     dword ptr [rax], 70616548h
0x1800d07e9  add     r14, 8
0x1800d07ed  mov     edx, [rbp+1A0h+var_19C]
0x1800d07f0  mov     ecx, [rbp+1A0h+var_194]
0x1800d07f3  test    r14, r14
0x1800d07f6  jnz     short loc_1800D0802
0x1800d07f8  mov     esi, 0C0000017h
0x1800d07fd  jmp     loc_1800D0C9F
0x1800d0802  test    ecx, ecx
0x1800d0804  jz      short loc_1800D0863
0x1800d0806  mov     r9d, [rbp+1A0h+TokenInformationLength]; TokenInformationLength
0x1800d080a  lea     rax, [rbp+1A0h+TokenInformationLength]
0x1800d080e  mov     r8, r14; TokenInformation
0x1800d0811  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x1800d0816  mov     edx, 21h ; '!'; TokenInformationClass
0x1800d081b  mov     rcx, rdi; TokenHandle
0x1800d081e  call    cs:__imp_NtQueryInformationToken
0x1800d0825  nop     dword ptr [rax+rax+00h]
0x1800d082a  mov     esi, eax
0x1800d082c  test    eax, eax
0x1800d082e  js      loc_1800D0C87
0x1800d0834  mov     rcx, [rbp+1A0h+TokenInformation]; void *
0x1800d083b  lea     r8, [rbp+1A0h+var_158]; struct _SAM_CLAIMS_BLOB *
0x1800d083f  mov     rdx, r14; struct _CLAIM_SECURITY_ATTRIBUTES_INFORMATION *
0x1800d0842  call    ?LsapSamExtConvertSecurityAttributesToClaimsBlob@@YAJPEAXPEAU_CLAIM_SECURITY_ATTRIBUTES_INFORMATION@@PEAU_SAM_CLAIMS_BLOB@@@Z; LsapSamExtConvertSecurityAttributesToClaimsBlob(void *,_CLAIM_SECURITY_ATTRIBUTES_INFORMATION *,_SAM_CLAIMS_BLOB *)
0x1800d0847  mov     esi, eax
0x1800d0849  test    eax, eax
0x1800d084b  js      loc_1800D0C87
0x1800d0851  mov     eax, dword ptr [rbp+1A0h+var_158]
0x1800d0854  mov     edx, [rbp+1A0h+var_19C]
0x1800d0857  add     eax, 7
0x1800d085a  and     eax, 0FFFFFFF8h
0x1800d085d  add     eax, 10h
0x1800d0860  add     r13d, eax
0x1800d0863  test    edx, edx
0x1800d0865  jz      short loc_1800D08C4
0x1800d0867  lea     rax, [rbp+1A0h+TokenInformationLength]
0x1800d086b  mov     [rbp+1A0h+TokenInformationLength], r12d
0x1800d086f  mov     r9d, r12d; TokenInformationLength
0x1800d0872  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x1800d0877  mov     r8, r14; TokenInformation
0x1800d087a  mov     edx, 22h ; '"'; TokenInformationClass
0x1800d087f  mov     rcx, rdi; TokenHandle
0x1800d0882  call    cs:__imp_NtQueryInformationToken
0x1800d0889  nop     dword ptr [rax+rax+00h]
0x1800d088e  mov     esi, eax
0x1800d0890  test    eax, eax
0x1800d0892  js      loc_1800D0C87
0x1800d0898  mov     rcx, [rbp+1A0h+TokenInformation]; void *
0x1800d089f  lea     r8, [rbp+1A0h+var_148]; struct _SAM_CLAIMS_BLOB *
0x1800d08a3  mov     rdx, r14; struct _CLAIM_SECURITY_ATTRIBUTES_INFORMATION *
0x1800d08a6  call    ?LsapSamExtConvertSecurityAttributesToClaimsBlob@@YAJPEAXPEAU_CLAIM_SECURITY_ATTRIBUTES_INFORMATION@@PEAU_SAM_CLAIMS_BLOB@@@Z; LsapSamExtConvertSecurityAttributesToClaimsBlob(void *,_CLAIM_SECURITY_ATTRIBUTES_INFORMATION *,_SAM_CLAIMS_BLOB *)
0x1800d08ab  mov     esi, eax
0x1800d08ad  test    eax, eax
0x1800d08af  js      loc_1800D0C87
0x1800d08b5  mov     eax, dword ptr [rbp+1A0h+var_148]
0x1800d08b8  add     eax, 7
0x1800d08bb  and     eax, 0FFFFFFF8h
0x1800d08be  add     eax, 10h
0x1800d08c1  add     r13d, eax
0x1800d08c4  mov     ecx, r13d
0x1800d08c7  call    LsapAllocate
0x1800d08cc  mov     [rbp+1A0h+var_160], rax
  ... truncated ...
```
