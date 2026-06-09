# KerbMakeTokenInformationV3(uchar,_NETLOGON_VALIDATION_SAM_INFO4 *,uchar,uchar,uchar,_SAM_CLAIMS_BLOB *,_NETLOGON_VALIDATION_SAM_INFO4 *,_SAM_CLAIMS_BLOB *,_LSA_TOKEN_INFORMATION_V3 * *)

- ea: `0x1800841e4`
- end: `0x180084b6c`
- name: `?KerbMakeTokenInformationV3@@YAJEPEAU_NETLOGON_VALIDATION_SAM_INFO4@@EEEPEAU_SAM_CLAIMS_BLOB@@01PEAPEAU_LSA_TOKEN_INFORMATION_V3@@@Z`
- size: `2440`
- prototype: `__int64 __fastcall(unsigned __int8, struct _NETLOGON_VALIDATION_SAM_INFO4 *, unsigned __int8, unsigned __int8, char, struct _SAM_CLAIMS_BLOB *, struct _NETLOGON_VALIDATION_SAM_INFO4 *, struct _SAM_CLAIMS_BLOB *, struct _LSA_TOKEN_INFORMATION_V3 **)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x1800819b0`
- `0x180082ef4`
- `0x1800b8908`
- `0x1800bed70`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x18003510c`
- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x1800841e4`
- `0x18008b70c`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18008477b`
- `ntdll!RtlCopySid` at `0x18008479e`
- `ntdll!RtlCopySid` at `0x1800848be`
- `ntdll!RtlCopySid` at `0x180084927`
- `ntdll!RtlCopySid` at `0x180084980`
- `ntdll!RtlCopySid` at `0x1800849cd`
- `ntdll!RtlCopySid` at `0x180084aff`
- `ntdll!RtlCopySid` at `0x18008477b`
- `ntdll!RtlCopySid` at `0x18008479e`
- `ntdll!RtlCopySid` at `0x1800848be`
- `ntdll!RtlCopySid` at `0x180084927`
- `ntdll!RtlCopySid` at `0x180084980`
- `ntdll!RtlCopySid` at `0x1800849cd`
- `ntdll!RtlCopySid` at `0x180084aff`
- `ntdll!RtlEqualSid` at `0x180084420`
- `ntdll!RtlEqualSid` at `0x180084420`
- `ntdll!RtlLengthSid` at `0x1800843c5`
- `ntdll!RtlLengthSid` at `0x180084400`
- `ntdll!RtlLengthSid` at `0x18008445b`
- `ntdll!RtlLengthSid` at `0x180084488`
- `ntdll!RtlLengthSid` at `0x180084493`
- `ntdll!RtlLengthSid` at `0x1800844c2`
- `ntdll!RtlLengthSid` at `0x1800844de`
- `ntdll!RtlLengthSid` at `0x18008452c`
- `ntdll!RtlLengthSid` at `0x180084578`
- `ntdll!RtlLengthSid` at `0x1800845b3`
- `ntdll!RtlLengthSid` at `0x1800845d7`
- `ntdll!RtlLengthSid` at `0x18008478d`
- `ntdll!RtlLengthSid` at `0x1800848a7`
- `ntdll!RtlLengthSid` at `0x18008490f`
- `ntdll!RtlLengthSid` at `0x1800849bc`
- `ntdll!RtlLengthSid` at `0x180084ae7`
- `ntdll!RtlLengthSid` at `0x1800843c5`
- `ntdll!RtlLengthSid` at `0x180084400`
- `ntdll!RtlLengthSid` at `0x18008445b`
- `ntdll!RtlLengthSid` at `0x180084488`
- `ntdll!RtlLengthSid` at `0x180084493`
- `ntdll!RtlLengthSid` at `0x1800844c2`
- `ntdll!RtlLengthSid` at `0x1800844de`
- `ntdll!RtlLengthSid` at `0x18008452c`
- `ntdll!RtlLengthSid` at `0x180084578`
- `ntdll!RtlLengthSid` at `0x1800845b3`
- `ntdll!RtlLengthSid` at `0x1800845d7`
- `ntdll!RtlLengthSid` at `0x18008478d`
- `ntdll!RtlLengthSid` at `0x1800848a7`
- `ntdll!RtlLengthSid` at `0x18008490f`
- `ntdll!RtlLengthSid` at `0x1800849bc`
- `ntdll!RtlLengthSid` at `0x180084ae7`
- `ntdll!RtlSubAuthoritySid` at `0x18008435d`
- `ntdll!RtlSubAuthoritySid` at `0x180084372`
- `ntdll!RtlSubAuthoritySid` at `0x1800843a7`
- `ntdll!RtlSubAuthoritySid` at `0x180084509`
- `ntdll!RtlSubAuthoritySid` at `0x18008451c`
- `ntdll!RtlSubAuthoritySid` at `0x18008435d`
- `ntdll!RtlSubAuthoritySid` at `0x180084372`
- `ntdll!RtlSubAuthoritySid` at `0x1800843a7`
- `ntdll!RtlSubAuthoritySid` at `0x180084509`
- `ntdll!RtlSubAuthoritySid` at `0x18008451c`
- `ntdll!RtlInitializeSid` at `0x180084351`
- `ntdll!RtlInitializeSid` at `0x18008439b`
- `ntdll!RtlInitializeSid` at `0x1800844fd`
- `ntdll!RtlInitializeSid` at `0x180084351`
- `ntdll!RtlInitializeSid` at `0x18008439b`
- `ntdll!RtlInitializeSid` at `0x1800844fd`
- `LSASRV!LsaIFilterSids` at `0x1800842f0`
- `LSASRV!LsaIFilterSids` at `0x18008432a`
- `LSASRV!LsaIFilterSids` at `0x1800842f0`
- `LSASRV!LsaIFilterSids` at `0x18008432a`

## string_xrefs

- `0x180084266`: `KerbMakeTokenInformationV3 LocalSystemSid %d, IsNetworkService %d, MaybeAddThisOrgCertSid %d\n`
- `0x180084271`: `KerbMakeTokenInformationV3`

## pseudocode

```c
__int64 __fastcall KerbMakeTokenInformationV3(
        char a1,
        struct _NETLOGON_VALIDATION_SAM_INFO4 *a2,
        unsigned __int8 a3,
        unsigned __int8 a4,
        unsigned __int8 a5,
        const void **a6,
        struct _NETLOGON_VALIDATION_SAM_INFO4 *a7,
        struct _SAM_CLAIMS_BLOB *a8,
        struct _LSA_TOKEN_INFORMATION_V3 **a9)
{
  __int64 result; // rax
  struct _LSA_TOKEN_INFORMATION_V3 *v13; // r14
  unsigned int v14; // r12d
  ULONG v15; // esi
  int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // r14d
  ULONG v20; // ecx
  void *v21; // rbx
  ULONG v22; // edi
  unsigned int v23; // eax
  ULONG v24; // ebx
  unsigned int v25; // r12d
  int v26; // edi
  ULONG v27; // edx
  size_t v28; // rcx
  int v29; // ebx
  int v30; // eax
  unsigned int v31; // esi
  size_t v32; // rsi
  struct _LSA_TOKEN_INFORMATION_V3 *v33; // rax
  SID_AND_ATTRIBUTES *v34; // rbx
  SID_AND_ATTRIBUTES *v35; // rsi
  unsigned int v36; // r12d
  SID_AND_ATTRIBUTES *v37; // rdi
  struct _SAM_CLAIMS_BLOB *v38; // rcx
  unsigned int v39; // eax
  unsigned int v40; // eax
  char *v41; // rsi
  _DWORD *v42; // rdi
  ULONG v43; // eax
  void *v44; // rdx
  __int64 v45; // rsi
  unsigned int i; // ebx
  ULONG v47; // eax
  __int64 v48; // rbx
  ULONG v49; // eax
  __int64 v50; // rbx
  ULONG v51; // eax
  __int64 v52; // rbx
  unsigned int j; // ebx
  unsigned int k; // r15d
  ULONG v55; // eax
  __int64 v56; // rbx
  int v59; // [rsp+54h] [rbp-ACh]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+78h] [rbp-88h] BYREF
  _DWORD SourceSid[4]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v62[4]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE Sid[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v64[80]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE Sid1[80]; // [rsp+100h] [rbp+0h] BYREF

  v59 = a5;
  SourceSid[0] = 257;
  SourceSid[1] = 83886080;
  SourceSid[2] = 18;
  v62[0] = 257;
  v62[1] = 83886080;
  v62[2] = 20;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  KerbTracerT::Log(
    10,
    "KerbMakeTokenInformationV3",
    1276,
    "KerbMakeTokenInformationV3 LocalSystemSid %d, IsNetworkService %d, MaybeAddThisOrgCertSid %d\n",
    a3,
    a4,
    a5);
  if ( a1 )
  {
    result = LsaIFilterSids(0, 0, 0, 0, 0, 6, a2, 0, 0, 0);
    if ( (int)result < 0 )
      return result;
    if ( a7 )
    {
      result = LsaIFilterSids(0, 0, 0, 0, 0, 6, a7, 0, 0, 0);
      if ( (int)result < 0 )
        return result;
    }
  }
  v13 = 0;
  if ( a3 )
  {
    RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
    *RtlSubAuthoritySid(Sid, 0) = 32;
    *RtlSubAuthoritySid(Sid, 1u) = 544;
  }
  v14 = *((_DWORD *)a2 + 39);
  v15 = 112;
  if ( a5 )
  {
    RtlInitializeSid(Sid1, &IdentifierAuthority, 1u);
    *RtlSubAuthoritySid(Sid1, 0) = 1000;
  }
  v16 = *((_DWORD *)a2 + 39);
  if ( v16 )
    v15 = v16 * (RtlLengthSid(*((PSID *)a2 + 28)) + 4) + 112;
  if ( (*((_BYTE *)a2 + 168) & 0x20) != 0 )
  {
    v17 = *((_DWORD *)a2 + 68);
    v18 = 0;
    v14 += v17;
    if ( v17 )
    {
      v19 = a5;
      do
      {
        v15 += RtlLengthSid(*(PSID *)(*((_QWORD *)a2 + 35) + 16LL * v18));
        if ( a5 && RtlEqualSid(Sid1, *(PSID *)(*((_QWORD *)a2 + 35) + 16LL * v18)) )
          v19 = 0;
        ++v18;
      }
      while ( v18 < *((_DWORD *)a2 + 68) );
      v59 = v19;
      v13 = 0;
    }
  }
  if ( a3 )
  {
    v25 = v14 + 2;
    v24 = v15 + RtlLengthSid(Sid) + 12;
    if ( *((_DWORD *)a2 + 37) )
      v24 += RtlLengthSid(*((PSID *)a2 + 28)) + 4;
  }
  else
  {
    if ( *((_DWORD *)a2 + 37) )
    {
      v20 = v15 + 2 * (RtlLengthSid(*((PSID *)a2 + 28)) + 4);
    }
    else
    {
      if ( !*((_DWORD *)a2 + 68) )
        goto LABEL_90;
      v21 = (void *)*((_QWORD *)a2 + 28);
      v22 = RtlLengthSid(**((PSID **)a2 + 35));
      v20 = v15 + RtlLengthSid(v21) + v22 + 4;
    }
    v23 = v14 + 1;
    v24 = v20 + 12;
    if ( !a4 )
    {
      v23 = v14;
      v24 = v20;
    }
    v25 = v23;
  }
  v26 = 0;
  if ( v59 )
  {
    RtlInitializeSid(v64, &IdentifierAuthority, 2u);
    *RtlSubAuthoritySid(v64, 0) = 65;
    *RtlSubAuthoritySid(v64, 1u) = 1;
    v24 += RtlLengthSid(v64);
    ++v25;
  }
  v27 = v24 + 16 * v25;
  v28 = v27 - 16;
  if ( a6 && *(_DWORD *)a6 )
    v28 = v27 + ((*(_DWORD *)a6 + 3) & 0xFFFFFFFC);
  if ( !a7 )
    goto LABEL_45;
  v26 = *((_DWORD *)a7 + 39);
  if ( v26 )
    v29 = v28 + 24 + v26 * (RtlLengthSid(*((PSID *)a7 + 28)) + 4);
  else
    v29 = v28 + 24;
  if ( (*((_BYTE *)a7 + 168) & 0x20) != 0 )
  {
    v30 = *((_DWORD *)a7 + 68);
    v31 = 0;
    v26 += v30;
    if ( v30 )
    {
      do
        v29 += RtlLengthSid(*(PSID *)(*((_QWORD *)a7 + 35) + 16LL * v31++));
      while ( v31 < *((_DWORD *)a7 + 68) );
    }
  }
  if ( !*((_DWORD *)a7 + 37) )
  {
    if ( *((_DWORD *)a2 + 68) )
      goto LABEL_44;
LABEL_90:
    KerbFree(v13);
    return 3221226064LL;
  }
  v29 += RtlLengthSid(*((PSID *)a2 + 28)) + 4;
  ++v26;
LABEL_44:
  v28 = (unsigned int)(v29 + 16 * v26 - 16);
LABEL_45:
  if ( a8 && *(_DWORD *)a8 )
    v28 = ((*(_DWORD *)a8 + 3) & 0xFFFFFFFC) + 16 + (unsigned int)v28;
  v32 = (unsigned int)v28;
  v33 = (struct _LSA_TOKEN_INFORMATION_V3 *)MIDL_user_allocate(v28);
  v13 = v33;
  if ( !v33 )
    return 3221225626LL;
  v34 = 0;
  memset_0(v33, 0, v32);
  v35 = &v13[1].User.User + v25;
  v13->Groups = (PTOKEN_GROUPS)&v13[1];
  v36 = 0;
  v13[1].ExpirationTime.LowPart = 0;
  if ( a7 )
  {
    v13->DeviceGroups = (PTOKEN_GROUPS)v35;
    LODWORD(v35->Sid) = 0;
    v35 = &v13->DeviceGroups->Groups[v26];
  }
  if ( a6 && *(_DWORD *)a6 )
  {
    v13->UserClaims.UserClaims = v35;
    v37 = v35++;
  }
  else
  {
    v37 = 0;
  }
  v38 = a8;
  if ( a8 && *(_DWORD *)a8 )
  {
    v13->DeviceClaims.DeviceClaims = v35;
    v34 = v35++;
  }
  if ( v37 )
  {
    *(_QWORD *)&v37->Attributes = v35;
    v39 = *(_DWORD *)a6;
    LODWORD(v37->Sid) = *(_DWORD *)a6;
    memcpy_0(v35, a6[1], v39);
    v38 = a8;
    v35 = (SID_AND_ATTRIBUTES *)((char *)v35 + ((LODWORD(v37->Sid) + 3LL) & 0xFFFFFFFFFFFFFFFCuLL));
  }
  if ( v34 )
  {
    *(_QWORD *)&v34->Attributes = v35;
    v40 = *(_DWORD *)v38;
    LODWORD(v34->Sid) = *(_DWORD *)v38;
    memcpy_0(v35, *((const void **)v38 + 1), v40);
    v35 = (SID_AND_ATTRIBUTES *)((char *)v35 + ((LODWORD(v34->Sid) + 3LL) & 0xFFFFFFFFFFFFFFFCuLL));
  }
  v13->ExpirationTime.LowPart = *((_DWORD *)a2 + 4);
  v13->ExpirationTime.HighPart = *((_DWORD *)a2 + 5);
  if ( a3 )
  {
    v13->User.User.Sid = v35;
    RtlCopySid(0xCu, v35, SourceSid);
    v42 = &v35->Attributes + 1;
    v13->PrimaryGroup.PrimaryGroup = &v35->Attributes + 1;
    v43 = RtlLengthSid(Sid);
    v44 = &v35->Attributes + 1;
    v45 = v43;
    RtlCopySid(v43, v44, Sid);
    v41 = (char *)v42 + v45;
    if ( *((_DWORD *)a2 + 37) )
    {
      v13->Groups->Groups[v13->Groups->GroupCount].Attributes = 7;
      v13->Groups->Groups[v13->Groups->GroupCount].Sid = v41;
      v41 += (unsigned int)KerbCopyDomainRelativeSid(v41, *((PSID *)a2 + 28));
      ++v13->Groups->GroupCount;
    }
    v13->Groups->Groups[v13->Groups->GroupCount].Attributes = 14;
    v13->Groups->Groups[v13->Groups->GroupCount++].Sid = v13->PrimaryGroup.PrimaryGroup;
  }
  else
  {
    if ( *((_DWORD *)a2 + 37) )
    {
      v13->User.User.Sid = v35;
      v35 = (SID_AND_ATTRIBUTES *)((char *)v35 + (unsigned int)KerbCopyDomainRelativeSid(v35, *((PSID *)a2 + 28)));
    }
    v13->PrimaryGroup.PrimaryGroup = v35;
    v41 = (char *)v35 + (unsigned int)KerbCopyDomainRelativeSid(v35, *((PSID *)a2 + 28));
  }
  for ( i = 0; i < *((_DWORD *)a2 + 39); ++v13->Groups->GroupCount )
  {
    v13->Groups->Groups[v13->Groups->GroupCount].Attributes = *(_DWORD *)(*((_QWORD *)a2 + 20) + 8LL * i + 4);
    v13->Groups->Groups[v13->Groups->GroupCount].Sid = v41;
    ++i;
    v41 += (unsigned int)KerbCopyDomainRelativeSid(v41, *((PSID *)a2 + 28));
  }
  if ( (*((_BYTE *)a2 + 168) & 0x20) != 0 )
  {
    if ( !v13->User.User.Sid )
    {
      v13->User.User.Sid = v41;
      v47 = RtlLengthSid(**((PSID **)a2 + 35));
      v48 = v47;
      RtlCopySid(v47, v41, **((PSID **)a2 + 35));
      v41 += v48;
      v36 = 1;
    }
    while ( v36 < *((_DWORD *)a2 + 68) )
    {
      v13->Groups->Groups[v13->Groups->GroupCount].Attributes = *(_DWORD *)(*((_QWORD *)a2 + 35) + 16LL * v36 + 8);
      v13->Groups->Groups[v13->Groups->GroupCount].Sid = v41;
      v49 = RtlLengthSid(*(PSID *)(*((_QWORD *)a2 + 35) + 16LL * v36));
      v50 = v49;
      RtlCopySid(v49, v41, *(PSID *)(*((_QWORD *)a2 + 35) + 16LL * v36));
      v41 += v50;
      ++v13->Groups->GroupCount;
      ++v36;
    }
  }
  if ( a4 )
  {
    v13->Groups->Groups[v13->Groups->GroupCount].Sid = v41;
    v13->Groups->Groups[v13->Groups->GroupCount].Attributes = 14;
    v13->Groups->Groups[v13->Groups->GroupCount].Sid = v41;
    RtlCopySid(0xCu, v41, v62);
    v41 += 12;
    ++v13->Groups->GroupCount;
  }
  if ( v59 )
  {
    v13->Groups->Groups[v13->Groups->GroupCount].Sid = v41;
    v13->Groups->Groups[v13->Groups->GroupCount].Attributes = 7;
    v51 = RtlLengthSid(v64);
    v52 = v51;
    RtlCopySid(v51, v41, v64);
    v41 += v52;
    ++v13->Groups->GroupCount;
  }
  if ( a7 )
  {
    if ( *((_DWORD *)a7 + 37) )
    {
      v13->DeviceGroups->Groups[v13->DeviceGroups->GroupCount].Attributes = 7;
      v13->DeviceGroups->Groups[v13->DeviceGroups->GroupCount].Sid = v41;
      v41 += (unsigned int)KerbCopyDomainRelativeSid(v41, *((PSID *)a7 + 28));
      ++v13->DeviceGroups->GroupCount;
    }
    for ( j = 0; j < *((_DWORD *)a7 + 39); ++v13->DeviceGroups->GroupCount )
    {
      v13->DeviceGroups->Groups[v13->DeviceGroups->GroupCount].Attributes = *(_DWORD *)(*((_QWORD *)a7 + 20)
                                                                                      + 8LL * j
                                                                                      + 4);
      v13->DeviceGroups->Groups[v13->DeviceGroups->GroupCount].Sid = v41;
      ++j;
      v41 += (unsigned int)KerbCopyDomainRelativeSid(v41, *((PSID *)a7 + 28));
    }
    if ( (*((_BYTE *)a7 + 168) & 0x20) != 0 )
    {
      for ( k = 0; k < *((_DWORD *)a7 + 68); ++v13->DeviceGroups->GroupCount )
      {
        v13->DeviceGroups->Groups[v13->DeviceGroups->GroupCount].Attributes = *(_DWORD *)(*((_QWORD *)a7 + 35)
                                                                                        + 16LL * k
                                                                                        + 8);
        v13->DeviceGroups->Groups[v13->DeviceGroups->GroupCount].Sid = v41;
        v55 = RtlLengthSid(*(PSID *)(*((_QWORD *)a7 + 35) + 16LL * k));
        v56 = v55;
        RtlCopySid(v55, v41, *(PSID *)(*((_QWORD *)a7 + 35) + 16LL * k));
        v41 += v56;
        ++k;
      }
    }
  }
  if ( !v13->User.User.Sid )
    goto LABEL_90;
  v13->Privileges = 0;
  v13->Owner.Owner = 0;
  v13->DefaultDacl.DefaultDacl = 0;
  *a9 = v13;
  return 0;
}

```

## disassembly

```asm
0x1800841e4  mov     [rsp-8+arg_0], rbx
0x1800841e9  push    rbp
0x1800841ea  push    rsi
0x1800841eb  push    rdi
0x1800841ec  push    r12
0x1800841ee  push    r13
0x1800841f0  push    r14
0x1800841f2  push    r15
0x1800841f4  lea     rbp, [rsp-60h]
0x1800841f9  sub     rsp, 160h
0x180084200  mov     rax, cs:__security_cookie
0x180084207  xor     rax, rsp
0x18008420a  mov     [rbp+90h+var_40], rax
0x18008420e  mov     rax, [rbp+90h+arg_38]
0x180084215  mov     r15, rdx
0x180084218  movzx   edi, [rbp+90h+arg_20]
0x18008421f  xor     r12d, r12d
0x180084222  mov     r13, [rbp+90h+arg_30]
0x180084229  mov     edx, edi
0x18008422b  mov     [rsp+190h+var_130], rax
0x180084230  mov     bl, cl
0x180084232  mov     rax, [rbp+90h+arg_28]
0x180084239  movzx   esi, r8b
0x18008423d  lea     ecx, [r12+0Ah]
0x180084242  mov     dword ptr [rsp+190h+var_160], edx
0x180084246  mov     r8d, 4FCh
0x18008424c  mov     [rsp+190h+var_128], rax
0x180084251  mov     rax, [rbp+90h+arg_40]
0x180084258  mov     [rsp+190h+var_120], rax
0x18008425d  movzx   eax, r9b
0x180084261  mov     [rsp+190h+var_13F], r9b
0x180084266  lea     r9, aKerbmaketokeni_0; "KerbMakeTokenInformationV3 LocalSystemS"...
0x18008426d  mov     [rsp+190h+var_13C], edx
0x180084271  lea     rdx, aKerbmaketokeni; "KerbMakeTokenInformationV3"
0x180084278  mov     [rsp+190h+var_168], eax
0x18008427c  mov     dword ptr [rsp+190h+var_170], esi
0x180084280  mov     [rsp+190h+var_140], sil
0x180084285  mov     [rbp+90h+SourceSid], 101h
0x18008428c  mov     [rbp+90h+var_10C], 5000000h
0x180084293  mov     [rbp+90h+var_108], 12h
0x18008429a  mov     [rbp+90h+var_100], 101h
0x1800842a1  mov     [rbp+90h+var_FC], 5000000h
0x1800842a8  mov     [rbp+90h+var_F8], 14h
0x1800842af  mov     dword ptr [rsp+190h+IdentifierAuthority.Value], r12d
0x1800842b4  mov     word ptr [rsp+190h+IdentifierAuthority.Value+4], 500h
0x1800842bb  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800842c0  test    bl, bl
0x1800842c2  jz      short loc_180084338
0x1800842c4  mov     [rsp+190h+var_148], r12
0x1800842c9  lea     ebx, [r12+6]
0x1800842ce  mov     [rsp+190h+var_150], r12
0x1800842d3  xor     r9d, r9d
0x1800842d6  mov     [rsp+190h+var_158], r12
0x1800842db  xor     r8d, r8d
0x1800842de  mov     [rsp+190h+var_160], r15
0x1800842e3  xor     edx, edx
0x1800842e5  mov     [rsp+190h+var_168], ebx
0x1800842e9  xor     ecx, ecx
0x1800842eb  mov     [rsp+190h+var_170], r12
0x1800842f0  call    cs:__imp_LsaIFilterSids
0x1800842f6  test    eax, eax
0x1800842f8  js      loc_180084B45
0x1800842fe  test    r13, r13
0x180084301  jz      short loc_180084338
0x180084303  mov     [rsp+190h+var_148], r12
0x180084308  xor     r9d, r9d
0x18008430b  mov     [rsp+190h+var_150], r12
0x180084310  xor     r8d, r8d
0x180084313  mov     [rsp+190h+var_158], r12
0x180084318  xor     edx, edx
0x18008431a  mov     [rsp+190h+var_160], r13
0x18008431f  xor     ecx, ecx
0x180084321  mov     [rsp+190h+var_168], ebx
0x180084325  mov     [rsp+190h+var_170], r12
0x18008432a  call    cs:__imp_LsaIFilterSids
0x180084330  test    eax, eax
0x180084332  js      loc_180084B45
0x180084338  mov     [rsp+190h+var_138], r12
0x18008433d  mov     r14, r12
0x180084340  test    sil, sil
0x180084343  jz      short loc_18008437E
0x180084345  mov     r8b, 2; SubAuthorityCount
0x180084348  lea     rdx, [rsp+190h+IdentifierAuthority]; IdentifierAuthority
0x18008434d  lea     rcx, [rbp+90h+Sid]; Sid
0x180084351  call    cs:__imp_RtlInitializeSid
0x180084357  xor     edx, edx; SubAuthority
0x180084359  lea     rcx, [rbp+90h+Sid]; Sid
0x18008435d  call    cs:__imp_RtlSubAuthoritySid
0x180084363  mov     edx, 1; SubAuthority
0x180084368  lea     rcx, [rbp+90h+Sid]; Sid
0x18008436c  mov     dword ptr [rax], 20h ; ' '
0x180084372  call    cs:__imp_RtlSubAuthoritySid
0x180084378  mov     dword ptr [rax], 220h
0x18008437e  mov     r12d, [r15+9Ch]
0x180084385  mov     esi, 70h ; 'p'
0x18008438a  test    dil, dil
0x18008438d  jz      short loc_1800843B3
0x18008438f  mov     r8b, 1; SubAuthorityCount
0x180084392  lea     rdx, [rsp+190h+IdentifierAuthority]; IdentifierAuthority
0x180084397  lea     rcx, [rbp+90h+Sid1]; Sid
0x18008439b  call    cs:__imp_RtlInitializeSid
0x1800843a1  xor     edx, edx; SubAuthority
0x1800843a3  lea     rcx, [rbp+90h+Sid1]; Sid
0x1800843a7  call    cs:__imp_RtlSubAuthoritySid
0x1800843ad  mov     dword ptr [rax], 3E8h
0x1800843b3  mov     ebx, [r15+9Ch]
0x1800843ba  test    ebx, ebx
0x1800843bc  jz      short loc_1800843D3
0x1800843be  mov     rcx, [r15+0E0h]; Sid
0x1800843c5  call    cs:__imp_RtlLengthSid
0x1800843cb  add     eax, 4
0x1800843ce  imul    eax, ebx
0x1800843d1  add     esi, eax
0x1800843d3  test    byte ptr [r15+0A8h], 20h
0x1800843db  jz      short loc_180084443
0x1800843dd  mov     eax, [r15+110h]
0x1800843e4  xor     ebx, ebx
0x1800843e6  add     r12d, eax
0x1800843e9  test    eax, eax
0x1800843eb  jz      short loc_180084443
0x1800843ed  mov     r14d, edi
0x1800843f0  mov     rcx, [r15+118h]
0x1800843f7  mov     edi, ebx
0x1800843f9  add     rdi, rdi
0x1800843fc  mov     rcx, [rcx+rdi*8]; Sid
0x180084400  call    cs:__imp_RtlLengthSid
0x180084406  add     esi, eax
0x180084408  cmp     [rbp+90h+arg_20], 0
0x18008440f  jz      short loc_18008442E
0x180084411  mov     rdx, [r15+118h]
0x180084418  lea     rcx, [rbp+90h+Sid1]; Sid1
0x18008441c  mov     rdx, [rdx+rdi*8]; Sid2
0x180084420  call    cs:__imp_RtlEqualSid
0x180084426  xor     ecx, ecx
0x180084428  test    al, al
0x18008442a  cmovnz  r14d, ecx
0x18008442e  inc     ebx
0x180084430  cmp     ebx, [r15+110h]
0x180084437  jb      short loc_1800843F0
0x180084439  mov     [rsp+190h+var_13C], r14d
0x18008443e  mov     r14, [rsp+190h+var_138]
0x180084443  cmp     [rsp+190h+var_140], 0
0x180084448  jnz     short loc_1800844BA
0x18008444a  cmp     dword ptr [r15+94h], 0
0x180084452  jz      short loc_180084469
0x180084454  mov     rcx, [r15+0E0h]; Sid
0x18008445b  call    cs:__imp_RtlLengthSid
0x180084461  lea     ecx, [rax+4]
0x180084464  lea     ecx, [rsi+rcx*2]
0x180084467  jmp     short loc_1800844A0
0x180084469  cmp     dword ptr [r15+110h], 0
0x180084471  jbe     loc_180084B20
0x180084477  mov     rax, [r15+118h]
0x18008447e  mov     rbx, [r15+0E0h]
0x180084485  mov     rcx, [rax]; Sid
0x180084488  call    cs:__imp_RtlLengthSid
0x18008448e  mov     rcx, rbx; Sid
0x180084491  mov     edi, eax
0x180084493  call    cs:__imp_RtlLengthSid
0x180084499  add     eax, esi
0x18008449b  lea     ecx, [rdi+4]
0x18008449e  add     ecx, eax
0x1800844a0  mov     dl, [rsp+190h+var_13F]
0x1800844a4  lea     eax, [r12+1]
0x1800844a9  test    dl, dl
0x1800844ab  lea     ebx, [rcx+0Ch]
0x1800844ae  cmovz   eax, r12d
0x1800844b2  cmovz   ebx, ecx
0x1800844b5  mov     r12d, eax
0x1800844b8  jmp     short loc_1800844E9
0x1800844ba  lea     rcx, [rbp+90h+Sid]; Sid
0x1800844be  add     r12d, 2
0x1800844c2  call    cs:__imp_RtlLengthSid
0x1800844c8  lea     ebx, [rax+0Ch]
0x1800844cb  add     ebx, esi
0x1800844cd  cmp     dword ptr [r15+94h], 0
0x1800844d5  jz      short loc_1800844E9
0x1800844d7  mov     rcx, [r15+0E0h]; Sid
0x1800844de  call    cs:__imp_RtlLengthSid
0x1800844e4  add     ebx, 4
0x1800844e7  add     ebx, eax
0x1800844e9  xor     edi, edi
0x1800844eb  cmp     [rsp+190h+var_13C], edi
0x1800844ef  jz      short loc_180084537
0x1800844f1  mov     r8b, 2; SubAuthorityCount
0x1800844f4  lea     rdx, [rsp+190h+IdentifierAuthority]; IdentifierAuthority
0x1800844f9  lea     rcx, [rbp+90h+var_E0]; Sid
0x1800844fd  call    cs:__imp_RtlInitializeSid
0x180084503  xor     edx, edx; SubAuthority
0x180084505  lea     rcx, [rbp+90h+var_E0]; Sid
0x180084509  call    cs:__imp_RtlSubAuthoritySid
0x18008450f  lea     edx, [rdi+1]; SubAuthority
0x180084512  lea     rcx, [rbp+90h+var_E0]; Sid
0x180084516  mov     dword ptr [rax], 41h ; 'A'
0x18008451c  call    cs:__imp_RtlSubAuthoritySid
0x180084522  lea     rcx, [rbp+90h+var_E0]; Sid
0x180084526  mov     dword ptr [rax], 1
0x18008452c  call    cs:__imp_RtlLengthSid
0x180084532  add     ebx, eax
0x180084534  inc     r12d
0x180084537  mov     rax, [rsp+190h+var_128]
0x18008453c  mov     edx, r12d
0x18008453f  shl     edx, 4
0x180084542  add     edx, ebx
0x180084544  lea     ecx, [rdx-10h]
0x180084547  test    rax, rax
0x18008454a  jz      short loc_18008455A
0x18008454c  mov     eax, [rax]
0x18008454e  test    eax, eax
0x180084550  jz      short loc_18008455A
0x180084552  lea     ecx, [rax+3]
0x180084555  and     ecx, 0FFFFFFFCh
0x180084558  add     ecx, edx
0x18008455a  test    r13, r13
0x18008455d  jz      loc_1800845FE
0x180084563  mov     edi, [r13+9Ch]
0x18008456a  lea     esi, [rcx+18h]
0x18008456d  test    edi, edi
0x18008456f  jz      short loc_180084588
0x180084571  mov     rcx, [r13+0E0h]; Sid
0x180084578  call    cs:__imp_RtlLengthSid
0x18008457e  lea     ebx, [rax+4]
0x180084581  imul    ebx, edi
0x180084584  add     ebx, esi
0x180084586  jmp     short loc_18008458A
0x180084588  mov     ebx, esi
0x18008458a  test    byte ptr [r13+0A8h], 20h
0x180084592  jz      short loc_1800845C6
0x180084594  mov     eax, [r13+110h]
0x18008459b  xor     esi, esi
0x18008459d  add     edi, eax
0x18008459f  test    eax, eax
0x1800845a1  jz      short loc_1800845C6
0x1800845a3  mov     rcx, [r13+118h]
0x1800845aa  mov     eax, esi
0x1800845ac  add     rax, rax
0x1800845af  mov     rcx, [rcx+rax*8]; Sid
0x1800845b3  call    cs:__imp_RtlLengthSid
0x1800845b9  add     ebx, eax
0x1800845bb  inc     esi
0x1800845bd  cmp     esi, [r13+110h]
0x1800845c4  jb      short loc_1800845A3
0x1800845c6  cmp     dword ptr [r13+94h], 0
0x1800845ce  jz      short loc_1800845E6
0x1800845d0  mov     rcx, [r15+0E0h]; Sid
0x1800845d7  call    cs:__imp_RtlLengthSid
0x1800845dd  add     eax, 4
0x1800845e0  add     ebx, eax
0x1800845e2  inc     edi
0x1800845e4  jmp     short loc_1800845F4
0x1800845e6  cmp     dword ptr [r15+110h], 0
0x1800845ee  jbe     loc_180084B20
0x1800845f4  mov     ecx, edi
0x1800845f6  shl     ecx, 4
0x1800845f9  add     ecx, 0FFFFFFF0h
0x1800845fc  add     ecx, ebx
0x1800845fe  mov     rax, [rsp+190h+var_130]
0x180084603  test    rax, rax
0x180084606  jz      short loc_180084619
0x180084608  mov     eax, [rax]
0x18008460a  test    eax, eax
0x18008460c  jz      short loc_180084619
0x18008460e  add     eax, 3
0x180084611  and     eax, 0FFFFFFFCh
0x180084614  add     eax, 10h
0x180084617  add     ecx, eax; size
0x180084619  mov     esi, ecx
0x18008461b  call    MIDL_user_allocate
0x180084620  mov     r14, rax
0x180084623  test    rax, rax
0x180084626  jnz     short loc_180084632
0x180084628  mov     eax, 0C000009Ah
0x18008462d  jmp     loc_180084B45
0x180084632  mov     r8, rsi; Size
0x180084635  xor     edx, edx; Val
0x180084637  mov     rcx, r14; void *
0x18008463a  xor     ebx, ebx
0x18008463c  call    memset_0
0x180084641  lea     rcx, [r14+58h]
0x180084645  mov     eax, r12d
0x180084648  shl     rax, 4
0x18008464c  lea     rsi, [rcx+8]
0x180084650  add     rsi, rax
0x180084653  mov     [r14+18h], rcx
0x180084657  xor     r12d, r12d
0x18008465a  mov     [rcx], ebx
0x18008465c  test    r13, r13
0x18008465f  jz      short loc_180084679
0x180084661  mov     [r14+50h], rsi
0x180084665  mov     [rsi], r12d
0x180084668  mov     rsi, [r14+50h]
0x18008466c  mov     ecx, edi
0x18008466e  add     rsi, 8
0x180084672  shl     rcx, 4
0x180084676  add     rsi, rcx
0x180084679  mov     rdx, [rsp+190h+var_128]
0x18008467e  test    rdx, rdx
0x180084681  jz      short loc_180084695
0x180084683  cmp     [rdx], r12d
0x180084686  jz      short loc_180084695
  ... truncated ...
```
