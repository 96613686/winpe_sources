# LsapLookupUserAccountType(ushort *,_LSAPR_SID *,_LSA_USER_ACCOUNT_TYPE *)

- ea: `0x18005eda0`
- end: `0x18005f48d`
- name: `?LsapLookupUserAccountType@@YAJPEAGPEAU_LSAPR_SID@@PEAW4_LSA_USER_ACCOUNT_TYPE@@@Z`
- size: `1773`
- prototype: `int(unsigned __int16 *, struct _LSAPR_SID *, enum _LSA_USER_ACCOUNT_TYPE *)`
- caller_count: `8`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022590`
- `0x1800250c4`
- `0x18005ec10`
- `0x1800cd9e8`
- `0x1800d541c`
- `0x1800fbde0`
- `0x1800fce7c`
- `0x18012a430`

## callees

- `0x180011278`
- `0x18005ec24`
- `0x18005eda0`
- `0x18005f494`
- `0x18005f550`
- `0x18005fb34`
- `0x18005fecc`
- `0x18006064c`
- `0x180060c8c`
- `0x180075034`
- `0x1800b86d0`
- `0x1800bd6e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f420`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005f0ed`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005f27d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005f410`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005f0ed`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005f27d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005f410`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18005ef8f`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x18005ef8f`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005ee3b`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005ee75`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005ef21`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005ef33`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005f04f`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005f061`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005f2d9`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005ee3b`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005ee75`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005ef21`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005ef33`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005f04f`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005f061`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005f2d9`
- `ntdll!RtlSubAuthoritySid` at `0x18005ef5e`
- `ntdll!RtlSubAuthoritySid` at `0x18005ef72`
- `ntdll!RtlSubAuthoritySid` at `0x18005f091`
- `ntdll!RtlSubAuthoritySid` at `0x18005f0a5`
- `ntdll!RtlSubAuthoritySid` at `0x18005ef5e`
- `ntdll!RtlSubAuthoritySid` at `0x18005ef72`
- `ntdll!RtlSubAuthoritySid` at `0x18005f091`
- `ntdll!RtlSubAuthoritySid` at `0x18005f0a5`
- `ntdll!NtClose` at `0x18005f298`
- `ntdll!NtClose` at `0x18005f472`
- `ntdll!NtClose` at `0x18005f298`
- `ntdll!NtClose` at `0x18005f472`
- `ntdll!RtlValidSid` at `0x18005efc5`
- `ntdll!RtlValidSid` at `0x18005efc5`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005eea8`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005eeba`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005eeeb`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005eefd`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005eea8`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005eeba`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005eeeb`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005eefd`
- `ntdll!RtlLengthSid` at `0x18005ee16`
- `ntdll!RtlLengthSid` at `0x18005ee52`
- `ntdll!RtlLengthSid` at `0x18005f2b6`
- `ntdll!RtlLengthSid` at `0x18005ee16`
- `ntdll!RtlLengthSid` at `0x18005ee52`
- `ntdll!RtlLengthSid` at `0x18005f2b6`
- `ntdll!NtOpenThreadToken` at `0x18005f0d7`
- `ntdll!NtOpenThreadToken` at `0x18005f0d7`
- `RPCRT4!UuidEqual` at `0x18005f1f1`
- `RPCRT4!UuidEqual` at `0x18005f1f1`

## string_xrefs

- `0x18005f3fc`: `LsapSidBelongsToIdProv:LsapRefIdProvByInternetSid`
- `0x18005f228`: `LsapSidBelongsToIdProv:SID Validation`

## pseudocode

```c
__int64 __fastcall LsapLookupUserAccountType(
        unsigned __int16 *a1,
        struct _LSAPR_SID *a2,
        enum _LSA_USER_ACCOUNT_TYPE *a3)
{
  int v5; // edi
  _BYTE *v6; // r13
  ULONG v7; // eax
  PUCHAR v8; // rax
  PSID v9; // rcx
  ULONG v10; // eax
  PUCHAR v11; // rax
  PSID v12; // rcx
  PSID_IDENTIFIER_AUTHORITY v13; // rbx
  PSID_IDENTIFIER_AUTHORITY v14; // rax
  int v15; // ecx
  PSID_IDENTIFIER_AUTHORITY v16; // rbx
  PSID_IDENTIFIER_AUTHORITY v17; // rax
  int v18; // ecx
  PUCHAR v19; // r12
  UCHAR j; // r14
  PULONG v21; // rdi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v23; // ecx
  struct _RTL_BALANCED_NODE *v24; // r14
  BOOL v25; // edi
  __int64 v26; // rcx
  UUID *p_Uuid1; // rax
  int v28; // eax
  signed int MappedSidInternal; // ebx
  PUCHAR v30; // r12
  UCHAR i; // r14
  PULONG v32; // rdi
  NTSTATUS v33; // eax
  struct _UNICODE_STRING *v34; // r9
  int v35; // edi
  signed int ConnectedUserByLocalSid; // eax
  int v38; // eax
  const char *v39; // rcx
  __int64 v40; // rdx
  bool v41; // zf
  int v42; // eax
  ULONG v43; // eax
  PUCHAR v44; // rax
  LsaHandleCache *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r9
  signed int LastError; // eax
  DWORD v49; // eax
  int v50; // edi
  DWORD v51; // eax
  int v52; // edi
  int v53; // [rsp+30h] [rbp-D0h]
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  RPC_STATUS Status; // [rsp+40h] [rbp-C0h] BYREF
  struct _RTL_BALANCED_NODE *v56; // [rsp+48h] [rbp-B8h] BYREF
  UUID Uuid1; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Sid[80]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v59[80]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v60[80]; // [rsp+100h] [rbp+0h] BYREF

  Status = 0;
  TokenHandle = 0;
  *(_DWORD *)a3 = 0;
  Uuid1 = 0;
  if ( !a2 )
    return (unsigned int)-1073741811;
  if ( !LsapNullSidAuthority.SubAuthority[0] )
    return 0;
  v5 = 0;
  v53 = 0;
  v6 = 0;
  v7 = RtlLengthSid(LsapBuiltinDomainMemberSid);
  memcpy_0(Sid, LsapBuiltinDomainMemberSid, v7);
  v8 = RtlSubAuthorityCountSid(Sid);
  v9 = LsapAccountDomainMemberSid;
  --*v8;
  v10 = RtlLengthSid(v9);
  memcpy_0(v59, LsapAccountDomainMemberSid, v10);
  v11 = RtlSubAuthorityCountSid(v59);
  v12 = LsapLocalAccountDomainMemberSid;
  --*v11;
  if ( v12 )
  {
    v6 = v60;
    v43 = RtlLengthSid(v12);
    memcpy_0(v60, LsapLocalAccountDomainMemberSid, v43);
    v44 = RtlSubAuthorityCountSid(v60);
    --*v44;
  }
  if ( LsapIsDomainUser(a2) )
  {
    if ( !LsapPrimaryDomainSid || (v41 = LsapSidBelongsToDomain(a2, LsapPrimaryDomainSid) == 0, v42 = 2, v41) )
      v42 = 3;
    *(_DWORD *)a3 = v42;
    goto LABEL_44;
  }
  v13 = RtlIdentifierAuthoritySid(Sid);
  v14 = RtlIdentifierAuthoritySid(a2);
  v15 = *(_DWORD *)v13->Value - *(_DWORD *)v14->Value;
  if ( *(_DWORD *)v13->Value == *(_DWORD *)v14->Value )
    v15 = *(unsigned __int16 *)&v13->Value[4] - *(unsigned __int16 *)&v14->Value[4];
  if ( !v15 )
  {
    v30 = RtlSubAuthorityCountSid(Sid);
    if ( *v30 <= *RtlSubAuthorityCountSid(a2) )
    {
      for ( i = 0; i < *v30; ++i )
      {
        v32 = RtlSubAuthoritySid(Sid, i);
        if ( *RtlSubAuthoritySid(a2, i) != *v32 )
          goto LABEL_9;
      }
      goto LABEL_69;
    }
  }
LABEL_9:
  if ( v6 && LsapSidBelongsToDomain(a2, v6) )
  {
LABEL_69:
    *(_DWORD *)a3 = 1;
    goto LABEL_43;
  }
  v16 = RtlIdentifierAuthoritySid(v59);
  v17 = RtlIdentifierAuthoritySid(a2);
  v18 = *(_DWORD *)v16->Value - *(_DWORD *)v17->Value;
  if ( *(_DWORD *)v16->Value == *(_DWORD *)v17->Value )
    v18 = *(unsigned __int16 *)&v16->Value[4] - *(unsigned __int16 *)&v17->Value[4];
  if ( v18 || (v19 = RtlSubAuthorityCountSid(v59), *v19 > *RtlSubAuthorityCountSid(a2)) )
  {
LABEL_18:
    SidIdentifierAuthority = GetSidIdentifierAuthority(a2);
    v23 = -*(_DWORD *)SidIdentifierAuthority->Value;
    if ( !*(_DWORD *)SidIdentifierAuthority->Value )
      v23 = 3072 - *(unsigned __int16 *)&SidIdentifierAuthority->Value[4];
    if ( !v23 )
    {
      *(_DWORD *)a3 = 5;
      goto LABEL_43;
    }
    v24 = 0;
    v56 = 0;
    v25 = 0;
    if ( RtlValidSid(a2) )
    {
      v26 = 16;
      p_Uuid1 = &Uuid1;
      do
      {
        LOBYTE(p_Uuid1->Data1) = 0;
        p_Uuid1 = (UUID *)((char *)p_Uuid1 + 1);
        --v26;
      }
      while ( v26 );
      if ( !(unsigned int)LsapCheckConnectedUserEnabled() )
      {
        MappedSidInternal = 0;
        goto LABEL_28;
      }
      v28 = LsapRefIdProvByInternetSid(a2, (struct _LSAP_IDPROV_REG_ENTRY **)&v56);
      v24 = v56;
      if ( v28 >= 0 )
      {
        Uuid1 = (UUID)v56[1].0;
        goto LABEL_27;
      }
      if ( v28 == -1073741275 )
      {
LABEL_27:
        MappedSidInternal = 0;
        v25 = v28 >= 0;
        goto LABEL_28;
      }
      MappedSidInternal = v28;
      v39 = "LsapSidBelongsToIdProv:LsapRefIdProvByInternetSid";
      v40 = (unsigned int)v28;
    }
    else
    {
      MappedSidInternal = -1073741811;
      v39 = "LsapSidBelongsToIdProv:SID Validation";
      v40 = 3221225485LL;
    }
    CONNECTED_TRACE_ERROR(v39, v40);
LABEL_28:
    LsapDerefIdProv(v24);
    if ( MappedSidInternal >= 0 )
    {
      if ( v25 )
        *(_DWORD *)a3 = 6 - (UuidEqual(&Uuid1, (UUID *)&Uuid2, &Status) != 0);
      goto LABEL_43;
    }
    goto LABEL_29;
  }
  for ( j = 0; j < *v19; ++j )
  {
    v21 = RtlSubAuthoritySid(v59, j);
    if ( *RtlSubAuthoritySid(a2, j) != *v21 )
      goto LABEL_18;
  }
  v33 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  MappedSidInternal = v33;
  if ( v33 >= 0 )
  {
    if ( SetThreadToken(0, 0) )
    {
      v35 = 1;
      v53 = 1;
      goto LABEL_40;
    }
    LastError = GetLastError();
    MappedSidInternal = LastError;
    if ( LastError > 0 )
      MappedSidInternal = (unsigned __int16)LastError | 0xC0070000;
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_29;
    v46 = 70;
    v47 = (unsigned int)MappedSidInternal;
LABEL_73:
    WPP_SF_d(*((_QWORD *)v45 + 2), v46, WPP_fbab38a9e468344a0955481828104e3b_Traceguids, v47);
    goto LABEL_29;
  }
  if ( v33 != -1073741700 )
  {
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_29;
    v46 = 69;
    v47 = (unsigned int)v33;
    goto LABEL_73;
  }
  v35 = 0;
  TokenHandle = 0;
LABEL_40:
  ConnectedUserByLocalSid = LsapFindConnectedUserByLocalSid(a2, 0, 0, v34, 0);
  MappedSidInternal = ConnectedUserByLocalSid;
  if ( ConnectedUserByLocalSid )
  {
    if ( ConnectedUserByLocalSid == -1073741801 || ConnectedUserByLocalSid == -1073741670 )
      goto LABEL_29;
    MappedSidInternal = LsapFindMappedSidInternal(a2);
    v38 = 1;
    if ( MappedSidInternal >= 0 )
      v38 = 5;
    *(_DWORD *)a3 = v38;
  }
  else
  {
    *(_DWORD *)a3 = 4;
  }
  if ( TokenHandle )
  {
    if ( !v35 )
    {
      v5 = v53;
      goto LABEL_67;
    }
    if ( SetThreadToken(0, TokenHandle) )
    {
      v5 = 0;
LABEL_67:
      NtClose(TokenHandle);
      TokenHandle = 0;
      goto LABEL_44;
    }
    v49 = GetLastError();
    v50 = v49;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_fbab38a9e468344a0955481828104e3b_Traceguids, v49);
    if ( MappedSidInternal >= 0 )
    {
      if ( v50 > 0 )
        MappedSidInternal = (unsigned __int16)v50 | 0xC0070000;
      else
        MappedSidInternal = v50;
    }
LABEL_29:
    v5 = v53;
    goto LABEL_45;
  }
LABEL_43:
  v5 = v53;
LABEL_44:
  MappedSidInternal = 0;
LABEL_45:
  if ( TokenHandle )
  {
    if ( v5 && !SetThreadToken(0, TokenHandle) )
    {
      v51 = GetLastError();
      v52 = v51;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_fbab38a9e468344a0955481828104e3b_Traceguids, v51);
      if ( MappedSidInternal >= 0 )
      {
        if ( v52 > 0 )
          MappedSidInternal = (unsigned __int16)v52 | 0xC0070000;
        else
          MappedSidInternal = v52;
      }
    }
    NtClose(TokenHandle);
  }
  return (unsigned int)MappedSidInternal;
}

```

## disassembly

```asm
0x18005eda0  mov     [rsp-8+arg_0], rbx
0x18005eda5  push    rbp
0x18005eda6  push    rsi
0x18005eda7  push    rdi
0x18005eda8  push    r12
0x18005edaa  push    r13
0x18005edac  push    r14
0x18005edae  push    r15
0x18005edb0  lea     rbp, [rsp-60h]
0x18005edb5  sub     rsp, 160h
0x18005edbc  mov     rax, cs:__security_cookie
0x18005edc3  xor     rax, rsp
0x18005edc6  mov     [rbp+90h+var_40], rax
0x18005edca  mov     [rsp+190h+Status], 0
0x18005edd2  xorps   xmm0, xmm0
0x18005edd5  mov     [rsp+190h+TokenHandle], 0
0x18005edde  mov     r15, r8
0x18005ede1  mov     dword ptr [r8], 0
0x18005ede8  mov     rsi, rdx
0x18005edeb  movups  xmmword ptr [rsp+190h+Uuid1.Data1], xmm0
0x18005edf0  test    rdx, rdx
0x18005edf3  jz      loc_18005F483
0x18005edf9  cmp     cs:?LsapNullSidAuthority@@3U_SID_IDENTIFIER_AUTHORITY@@A.SubAuthority, 0; _SID_IDENTIFIER_AUTHORITY LsapNullSidAuthority ...
0x18005ee00  jz      loc_18005F1D4
0x18005ee06  mov     rcx, cs:?LsapBuiltinDomainMemberSid@@3PEAXEA; Sid
0x18005ee0d  xor     edi, edi
0x18005ee0f  mov     [rsp+190h+var_160], edi
0x18005ee13  xor     r13d, r13d
0x18005ee16  call    cs:__imp_RtlLengthSid
0x18005ee1d  nop     dword ptr [rax+rax+00h]
0x18005ee22  mov     rdx, cs:?LsapBuiltinDomainMemberSid@@3PEAXEA; Src
0x18005ee29  lea     rcx, [rsp+190h+Sid]; void *
0x18005ee2e  mov     r8d, eax; Size
0x18005ee31  call    memcpy_0
0x18005ee36  lea     rcx, [rsp+190h+Sid]; Sid
0x18005ee3b  call    cs:__imp_RtlSubAuthorityCountSid
0x18005ee42  nop     dword ptr [rax+rax+00h]
0x18005ee47  mov     rcx, cs:?LsapAccountDomainMemberSid@@3PEAXEA; Sid
0x18005ee4e  mov     bl, 0FFh
0x18005ee50  add     [rax], bl
0x18005ee52  call    cs:__imp_RtlLengthSid
0x18005ee59  nop     dword ptr [rax+rax+00h]
0x18005ee5e  mov     rdx, cs:?LsapAccountDomainMemberSid@@3PEAXEA; Src
0x18005ee65  lea     rcx, [rbp+90h+var_E0]; void *
0x18005ee69  mov     r8d, eax; Size
0x18005ee6c  call    memcpy_0
0x18005ee71  lea     rcx, [rbp+90h+var_E0]; Sid
0x18005ee75  call    cs:__imp_RtlSubAuthorityCountSid
0x18005ee7c  nop     dword ptr [rax+rax+00h]
0x18005ee81  mov     rcx, cs:?LsapLocalAccountDomainMemberSid@@3PEAXEA; Sid
0x18005ee88  add     [rax], bl
0x18005ee8a  test    rcx, rcx
0x18005ee8d  jnz     loc_18005F2B2
0x18005ee93  mov     rcx, rsi; Sid2
0x18005ee96  call    ?LsapIsDomainUser@@YAEPEAX@Z; LsapIsDomainUser(void *)
0x18005ee9b  test    al, al
0x18005ee9d  jnz     loc_18005F23B
0x18005eea3  lea     rcx, [rsp+190h+Sid]; Sid
0x18005eea8  call    cs:__imp_RtlIdentifierAuthoritySid
0x18005eeaf  nop     dword ptr [rax+rax+00h]
0x18005eeb4  mov     rcx, rsi; Sid
0x18005eeb7  mov     rbx, rax
0x18005eeba  call    cs:__imp_RtlIdentifierAuthoritySid
0x18005eec1  nop     dword ptr [rax+rax+00h]
0x18005eec6  mov     ecx, [rbx]
0x18005eec8  sub     ecx, [rax]
0x18005eeca  jnz     short loc_18005EED6
0x18005eecc  movzx   ecx, word ptr [rbx+4]
0x18005eed0  movzx   eax, word ptr [rax+4]
0x18005eed4  sub     ecx, eax
0x18005eed6  test    ecx, ecx
0x18005eed8  jz      loc_18005F04A
0x18005eede  test    r13, r13
0x18005eee1  jnz     loc_18005F2EC
0x18005eee7  lea     rcx, [rbp+90h+var_E0]; Sid
0x18005eeeb  call    cs:__imp_RtlIdentifierAuthoritySid
0x18005eef2  nop     dword ptr [rax+rax+00h]
0x18005eef7  mov     rcx, rsi; Sid
0x18005eefa  mov     rbx, rax
0x18005eefd  call    cs:__imp_RtlIdentifierAuthoritySid
0x18005ef04  nop     dword ptr [rax+rax+00h]
0x18005ef09  mov     ecx, [rbx]
0x18005ef0b  sub     ecx, [rax]
0x18005ef0d  jnz     short loc_18005EF19
0x18005ef0f  movzx   ecx, word ptr [rbx+4]
0x18005ef13  movzx   eax, word ptr [rax+4]
0x18005ef17  sub     ecx, eax
0x18005ef19  test    ecx, ecx
0x18005ef1b  jnz     short loc_18005EF8C
0x18005ef1d  lea     rcx, [rbp+90h+var_E0]; Sid
0x18005ef21  call    cs:__imp_RtlSubAuthorityCountSid
0x18005ef28  nop     dword ptr [rax+rax+00h]
0x18005ef2d  mov     rcx, rsi; Sid
0x18005ef30  mov     r12, rax
0x18005ef33  call    cs:__imp_RtlSubAuthorityCountSid
0x18005ef3a  nop     dword ptr [rax+rax+00h]
0x18005ef3f  mov     cl, [rax]
0x18005ef41  cmp     [r12], cl
0x18005ef45  ja      short loc_18005EF8C
0x18005ef47  xor     r14b, r14b
0x18005ef4a  cmp     r14b, [r12]
0x18005ef4e  jnb     loc_18005F0C3
0x18005ef54  movzx   ebx, r14b
0x18005ef58  lea     rcx, [rbp+90h+var_E0]; Sid
0x18005ef5c  mov     edx, ebx; SubAuthority
0x18005ef5e  call    cs:__imp_RtlSubAuthoritySid
0x18005ef65  nop     dword ptr [rax+rax+00h]
0x18005ef6a  mov     edx, ebx; SubAuthority
0x18005ef6c  mov     rcx, rsi; Sid
0x18005ef6f  mov     rdi, rax
0x18005ef72  call    cs:__imp_RtlSubAuthoritySid
0x18005ef79  nop     dword ptr [rax+rax+00h]
0x18005ef7e  mov     rcx, rax
0x18005ef81  mov     eax, [rdi]
0x18005ef83  cmp     [rcx], eax
0x18005ef85  jnz     short loc_18005EF8C
0x18005ef87  inc     r14b
0x18005ef8a  jmp     short loc_18005EF4A
0x18005ef8c  mov     rcx, rsi; pSid
0x18005ef8f  call    cs:__imp_GetSidIdentifierAuthority
0x18005ef96  nop     dword ptr [rax+rax+00h]
0x18005ef9b  mov     ecx, cs:dword_1801625A4
0x18005efa1  sub     ecx, [rax]
0x18005efa3  jnz     short loc_18005EFB2
0x18005efa5  movzx   ecx, cs:word_1801625A8
0x18005efac  movzx   eax, word ptr [rax+4]
0x18005efb0  sub     ecx, eax
0x18005efb2  test    ecx, ecx
0x18005efb4  jz      loc_18005F260
0x18005efba  xor     r14d, r14d
0x18005efbd  mov     rcx, rsi; Sid
0x18005efc0  mov     [rsp+190h+var_148], r14
0x18005efc5  call    cs:__imp_RtlValidSid
0x18005efcc  nop     dword ptr [rax+rax+00h]
0x18005efd1  xor     edi, edi
0x18005efd3  test    al, al
0x18005efd5  jz      loc_18005F223
0x18005efdb  lea     ecx, [rdi+10h]
0x18005efde  lea     rax, [rsp+190h+Uuid1]
0x18005efe3  mov     [rax], dil
0x18005efe6  inc     rax
0x18005efe9  sub     rcx, 1
0x18005efed  jnz     short loc_18005EFE3
0x18005efef  call    ?LsapCheckConnectedUserEnabled@@YAHXZ; LsapCheckConnectedUserEnabled(void)
0x18005eff4  test    eax, eax
0x18005eff6  jz      loc_18005F20C
0x18005effc  lea     rdx, [rsp+190h+var_148]; struct _LSAP_IDPROV_REG_ENTRY **
0x18005f001  mov     rcx, rsi; Sid
0x18005f004  call    ?LsapRefIdProvByInternetSid@@YAJPEAXPEAPEAU_LSAP_IDPROV_REG_ENTRY@@@Z; LsapRefIdProvByInternetSid(void *,_LSAP_IDPROV_REG_ENTRY * *)
0x18005f009  mov     r14, [rsp+190h+var_148]
0x18005f00e  test    eax, eax
0x18005f010  jns     loc_18005F213
0x18005f016  cmp     eax, 0C0000225h
0x18005f01b  jnz     loc_18005F3FA
0x18005f021  mov     edi, eax
0x18005f023  xor     ebx, ebx
0x18005f025  not     edi
0x18005f027  shr     edi, 1Fh
0x18005f02a  mov     rcx, r14; struct _RTL_BALANCED_NODE *
0x18005f02d  call    ?LsapDerefIdProv@@YAXPEAU_LSAP_IDPROV_REG_ENTRY@@@Z; LsapDerefIdProv(_LSAP_IDPROV_REG_ENTRY *)
0x18005f032  test    ebx, ebx
0x18005f034  jns     loc_18005F1D8
0x18005f03a  lea     rsi, WPP_GLOBAL_Control
0x18005f041  mov     edi, [rsp+190h+var_160]
0x18005f045  jmp     loc_18005F162
0x18005f04a  lea     rcx, [rsp+190h+Sid]; Sid
0x18005f04f  call    cs:__imp_RtlSubAuthorityCountSid
0x18005f056  nop     dword ptr [rax+rax+00h]
0x18005f05b  mov     rcx, rsi; Sid
0x18005f05e  mov     r12, rax
0x18005f061  call    cs:__imp_RtlSubAuthorityCountSid
0x18005f068  nop     dword ptr [rax+rax+00h]
0x18005f06d  mov     cl, [rax]
0x18005f06f  cmp     [r12], cl
0x18005f073  ja      loc_18005EEDE
0x18005f079  xor     r14b, r14b
0x18005f07c  cmp     r14b, [r12]
0x18005f080  jnb     loc_18005F2FF
0x18005f086  movzx   ebx, r14b
0x18005f08a  lea     rcx, [rsp+190h+Sid]; Sid
0x18005f08f  mov     edx, ebx; SubAuthority
0x18005f091  call    cs:__imp_RtlSubAuthoritySid
0x18005f098  nop     dword ptr [rax+rax+00h]
0x18005f09d  mov     edx, ebx; SubAuthority
0x18005f09f  mov     rcx, rsi; Sid
0x18005f0a2  mov     rdi, rax
0x18005f0a5  call    cs:__imp_RtlSubAuthoritySid
0x18005f0ac  nop     dword ptr [rax+rax+00h]
0x18005f0b1  mov     rcx, rax
0x18005f0b4  mov     eax, [rdi]
0x18005f0b6  cmp     [rcx], eax
0x18005f0b8  jnz     loc_18005EEDE
0x18005f0be  inc     r14b
0x18005f0c1  jmp     short loc_18005F07C
0x18005f0c3  lea     r9, [rsp+190h+TokenHandle]; TokenHandle
0x18005f0c8  mov     r8b, 1; OpenAsSelf
0x18005f0cb  mov     edx, 0Ch; DesiredAccess
0x18005f0d0  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18005f0d7  call    cs:__imp_NtOpenThreadToken
0x18005f0de  nop     dword ptr [rax+rax+00h]
0x18005f0e3  mov     ebx, eax
0x18005f0e5  test    eax, eax
0x18005f0e7  js      short loc_18005F10C
0x18005f0e9  xor     edx, edx; Token
0x18005f0eb  xor     ecx, ecx; Thread
0x18005f0ed  call    cs:__imp_SetThreadToken
0x18005f0f4  nop     dword ptr [rax+rax+00h]
0x18005f0f9  test    eax, eax
0x18005f0fb  jz      loc_18005F353
0x18005f101  mov     edi, 1
0x18005f106  mov     [rsp+190h+var_160], edi
0x18005f10a  jmp     short loc_18005F124
0x18005f10c  cmp     eax, 0C000007Ch
0x18005f111  jnz     loc_18005F30B
0x18005f117  mov     edi, [rsp+190h+var_160]
0x18005f11b  mov     [rsp+190h+TokenHandle], 0
0x18005f124  xor     r8d, r8d; struct _UNICODE_STRING *
0x18005f127  mov     [rsp+190h+var_170], 0; void **
0x18005f130  xor     edx, edx; struct _UNICODE_STRING *
0x18005f132  mov     rcx, rsi; SourceSid
0x18005f135  call    ?LsapFindConnectedUserByLocalSid@@YAJPEAXPEAU_UNICODE_STRING@@11PEAPEAX@Z; LsapFindConnectedUserByLocalSid(void *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void * *)
0x18005f13a  mov     ebx, eax
0x18005f13c  test    eax, eax
0x18005f13e  jnz     short loc_18005F19A
0x18005f140  mov     dword ptr [r15], 4
0x18005f147  mov     rdx, [rsp+190h+TokenHandle]; Token
0x18005f14c  test    rdx, rdx
0x18005f14f  jnz     loc_18005F273
0x18005f155  mov     edi, [rsp+190h+var_160]
0x18005f159  xor     ebx, ebx
0x18005f15b  lea     rsi, WPP_GLOBAL_Control
0x18005f162  mov     rdx, [rsp+190h+TokenHandle]; Token
0x18005f167  test    rdx, rdx
0x18005f16a  jnz     loc_18005F40A
0x18005f170  mov     eax, ebx
0x18005f172  mov     rcx, [rbp+90h+var_40]
0x18005f176  xor     rcx, rsp; StackCookie
0x18005f179  call    __security_check_cookie
0x18005f17e  mov     rbx, [rsp+190h+arg_0]
0x18005f186  add     rsp, 160h
0x18005f18d  pop     r15
0x18005f18f  pop     r14
0x18005f191  pop     r13
0x18005f193  pop     r12
0x18005f195  pop     rdi
0x18005f196  pop     rsi
0x18005f197  pop     rbp
0x18005f198  retn
0x18005f19a  cmp     eax, 0C0000017h
0x18005f19f  jz      loc_18005F03A
0x18005f1a5  cmp     eax, 0C000009Ah
0x18005f1aa  jz      loc_18005F03A
0x18005f1b0  xor     r8d, r8d
0x18005f1b3  xor     edx, edx
0x18005f1b5  mov     rcx, rsi; Sid
0x18005f1b8  call    LsapFindMappedSidInternal
0x18005f1bd  mov     ebx, eax
0x18005f1bf  mov     eax, 1
0x18005f1c4  test    ebx, ebx
0x18005f1c6  lea     ecx, [rax+4]
0x18005f1c9  cmovns  eax, ecx
0x18005f1cc  mov     [r15], eax
0x18005f1cf  jmp     loc_18005F147
0x18005f1d4  xor     ebx, ebx
0x18005f1d6  jmp     short loc_18005F170
0x18005f1d8  test    edi, edi
0x18005f1da  jz      loc_18005F155
0x18005f1e0  lea     r8, [rsp+190h+Status]; Status
0x18005f1e5  lea     rdx, Uuid2; Uuid2
0x18005f1ec  lea     rcx, [rsp+190h+Uuid1]; Uuid1
0x18005f1f1  call    cs:__imp_UuidEqual
0x18005f1f8  nop     dword ptr [rax+rax+00h]
0x18005f1fd  neg     eax
0x18005f1ff  sbb     ecx, ecx
0x18005f201  add     ecx, 6
0x18005f204  mov     [r15], ecx
0x18005f207  jmp     loc_18005F155
0x18005f20c  xor     ebx, ebx
0x18005f20e  jmp     loc_18005F02A
0x18005f213  movups  xmm0, xmmword ptr [r14+18h]
0x18005f218  movdqu  xmmword ptr [rsp+190h+Uuid1.Data1], xmm0
0x18005f21e  jmp     loc_18005F021
0x18005f223  mov     ebx, 0C000000Dh
0x18005f228  lea     rcx, aLsapsidbelongs_0; "LsapSidBelongsToIdProv:SID Validation"
0x18005f22f  mov     edx, ebx
0x18005f231  call    CONNECTED_TRACE_ERROR
0x18005f236  jmp     loc_18005F02A
0x18005f23b  mov     rdx, cs:?LsapPrimaryDomainSid@@3PEAXEA; PSID
0x18005f242  test    rdx, rdx
0x18005f245  jz      short loc_18005F26C
0x18005f247  mov     rcx, rsi; Sid
0x18005f24a  call    ?LsapSidBelongsToDomain@@YAEPEAX0@Z; LsapSidBelongsToDomain(void *,void *)
0x18005f24f  test    al, al
0x18005f251  mov     eax, 2
0x18005f256  jz      short loc_18005F26C
0x18005f258  mov     [r15], eax
0x18005f25b  jmp     loc_18005F159
0x18005f260  mov     dword ptr [r15], 5
0x18005f267  jmp     loc_18005F155
0x18005f26c  mov     eax, 3
  ... truncated ...
```
