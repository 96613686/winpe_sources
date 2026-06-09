# NlpCreateAuthzContext(_DOMAIN_INFO *,_NETLOGON_VALIDATION_SAM_INFO4 *,_SAM_CLAIMS_BLOB *,uchar,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)

- ea: `0x180054504`
- end: `0x180054899`
- name: `?NlpCreateAuthzContext@@YAJPEAU_DOMAIN_INFO@@PEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_SAM_CLAIMS_BLOB@@EPEAPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@@Z`
- size: `917`
- prototype: `int(struct _DOMAIN_INFO *, struct _NETLOGON_VALIDATION_SAM_INFO4 *, struct _SAM_CLAIMS_BLOB *, unsigned __int8, struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800549a4`

## callees

- `0x180007518`
- `0x18000d7a0`
- `0x18000dd00`
- `0x1800542fc`
- `0x180054504`
- `0x18008a5c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005480e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180054828`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180054851`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005480e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180054828`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180054851`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800547cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800547cc`
- `AUTHZ!AuthzModifyClaims` at `0x1800547bc`
- `AUTHZ!AuthzModifyClaims` at `0x1800547bc`
- `AUTHZ!AuthzFreeContext` at `0x180054866`
- `AUTHZ!AuthzFreeContext` at `0x180054866`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x180054732`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x180054732`
- `SAMSRV!SamIFreeAuthzSecurityAttributesInfo` at `0x180054876`
- `SAMSRV!SamIFreeAuthzSecurityAttributesInfo` at `0x180054876`
- `SAMSRV!SamIFreeSidArray` at `0x18005483d`
- `SAMSRV!SamIFreeSidArray` at `0x18005483d`
- `SAMSRV!SamIDecodeClaimsBlobToAuthz` at `0x18005478d`
- `SAMSRV!SamIDecodeClaimsBlobToAuthz` at `0x18005478d`
- `SAMSRV!SamIGetResourceGroupMembershipsTransitive` at `0x1800545ca`
- `SAMSRV!SamIGetResourceGroupMembershipsTransitive` at `0x1800545ca`

## string_xrefs

- `0x1800546c2`: `onecore\ds\netapi\svcdlls\logonsrv\server\rgroups.cxx`
- `0x180054569`: `NlpCreateAuthzContext received authorization data with no user RID or extra SID!\n`
- `0x18005459a`: `Failed to build SID list from user information: 0x%08X\n`
- `0x1800546c9`: `SidIndex == SidAndAttributesCount`
- `0x18005474e`: `NlpCreateAuthzContext: AuthzInitializeContextFromSid failed 0x%lx\n`
- `0x1800547d8`: `NlpCreateAuthzContext: AuthzModifyClaims failed 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NlpCreateAuthzContext(
        struct _DOMAIN_INFO *a1,
        struct _NETLOGON_VALIDATION_SAM_INFO4 *a2,
        struct _SAM_CLAIMS_BLOB *a3,
        char a4,
        struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **a5)
{
  void **v9; // rdi
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  unsigned int v14; // r15d
  char *j; // r9
  unsigned int i; // r8d
  __int64 v17; // rcx
  __int64 v18; // rdx
  _DWORD *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rcx
  unsigned int v23; // r8d
  __int64 v24; // rcx
  void **v25; // rax
  void *v26; // rbx
  void *v27; // rdx
  DWORD LastError; // eax
  unsigned __int16 *v29; // rdx
  DWORD v30; // ebx
  int v31; // eax
  AUTHZ_CLIENT_CONTEXT_HANDLE v32; // rcx
  void **v33; // rax
  unsigned int k; // esi
  _DWORD *v36; // [rsp+40h] [rbp-41h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+48h] [rbp-39h] BYREF
  LUID Identifier; // [rsp+50h] [rbp-31h]
  void *Block[2]; // [rsp+58h] [rbp-29h] BYREF
  __int128 DynamicGroupArgs; // [rsp+70h] [rbp-11h] BYREF
  _OWORD v41[5]; // [rsp+80h] [rbp-1h] BYREF
  unsigned int v42; // [rsp+E8h] [rbp+67h] BYREF

  v9 = 0;
  v42 = 0;
  *(_OWORD *)Block = 0;
  v36 = 0;
  hAuthzClientContext = 0;
  v41[0] = 0;
  Identifier = 0;
  DynamicGroupArgs = 0;
  if ( !*((_DWORD *)a2 + 37) && ((*((_BYTE *)a2 + 168) & 0x20) == 0 || !*((_DWORD *)a2 + 68)) )
  {
    NlPrintRoutine(0x100u, L"NlpCreateAuthzContext received authorization data with no user RID or extra SID!\n");
    v10 = -1073741811;
    goto LABEL_35;
  }
  v11 = NlpBuildPacSidList(a2, (struct _SAMPR_PSID_ARRAY *)Block, &v42);
  v10 = v11;
  if ( v11 >= 0 )
  {
    if ( a4 )
    {
      v12 = SamIGetResourceGroupMembershipsTransitive(*((_QWORD *)a1 + 47), Block, 0, &v36);
      v10 = v12;
      if ( v12 < 0 )
      {
        NlPrintRoutine(0x800u, L"Failed to expand resource groups for A2A: 0x%08X\n", (unsigned int)v12);
        goto LABEL_35;
      }
    }
    v13 = (int)Block[0];
    if ( v36 )
      v13 = *v36 + LODWORD(Block[0]);
    v14 = v13 + 2;
    v9 = (void **)MIDL_user_allocate(16LL * (unsigned int)(v13 + 2));
    if ( !v9 )
    {
      v10 = -1073741670;
      goto LABEL_35;
    }
    for ( i = 0; i < LODWORD(Block[0]); LODWORD(v9[v18 + 1]) = 7 )
    {
      v17 = i;
      v18 = i++;
      v18 *= 2;
      v9[v18] = (void *)*((_QWORD *)Block[1] + v17);
    }
    v19 = v36;
    if ( v36 )
    {
      for ( j = 0; (unsigned int)j < *v36; v19 = v36 )
      {
        v20 = i++;
        v20 *= 2;
        v21 = (unsigned int)j;
        j = (char *)(unsigned int)((_DWORD)j + 1);
        v9[v20] = *(void **)(*((_QWORD *)v19 + 1) + 8 * v21);
        LODWORD(v9[v20 + 1]) = 536870919;
      }
    }
    v22 = i;
    v23 = i + 1;
    v22 *= 2;
    v9[v22] = (void *)WorldSid;
    LODWORD(v9[v22 + 1]) = 536870919;
    v24 = 2LL * v23;
    v9[v24] = (void *)AuthenticatedUserSid;
    LODWORD(v9[v24 + 1]) = 536870919;
    if ( v23 + 1 != v14 )
      NlAssertFailed(
        "SidIndex == SidAndAttributesCount",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\rgroups.cxx",
        0x394u,
        j);
    if ( *((_DWORD *)a2 + 37) )
      v25 = v9;
    else
      v25 = &v9[2 * v42];
    v26 = *v25;
    v27 = *v25;
    *(_QWORD *)&DynamicGroupArgs = v9;
    *((_QWORD *)&DynamicGroupArgs + 1) = v14;
    if ( AuthzInitializeContextFromSid(2u, v27, NlAuthzRM, 0, Identifier, &DynamicGroupArgs, &hAuthzClientContext) )
    {
      if ( !a3 || !*(_DWORD *)a3 )
        goto LABEL_34;
      v42 = 1;
      v31 = SamIDecodeClaimsBlobToAuthz(v26, a3, v41);
      v10 = v31;
      if ( v31 < 0 )
      {
        NlPrintRoutine(0x800u, L"SamIDecodeClaimsBlobToAuthz failed to decode claims: 0x%08X\n", (unsigned int)v31);
        goto LABEL_35;
      }
      if ( (unsigned int)AuthzModifyClaims(hAuthzClientContext, 13, &v42, v41) )
      {
LABEL_34:
        v32 = hAuthzClientContext;
        v10 = 0;
        hAuthzClientContext = 0;
        *a5 = v32;
        goto LABEL_35;
      }
      LastError = GetLastError();
      v29 = L"NlpCreateAuthzContext: AuthzModifyClaims failed 0x%lx\n";
    }
    else
    {
      LastError = GetLastError();
      v29 = L"NlpCreateAuthzContext: AuthzInitializeContextFromSid failed 0x%lx\n";
    }
    v30 = LastError;
    NlPrintRoutine(0x100u, v29, LastError);
    v10 = NetpApiStatusToNtStatus(v30);
    goto LABEL_35;
  }
  NlPrintRoutine(0x800u, L"Failed to build SID list from user information: 0x%08X\n", (unsigned int)v11);
LABEL_35:
  v33 = (void **)Block[1];
  if ( Block[1] )
  {
    for ( k = 0; k < LODWORD(Block[0]); ++k )
    {
      free(v33[k]);
      v33 = (void **)Block[1];
    }
    free(v33);
  }
  if ( v36 )
    SamIFreeSidArray();
  if ( v9 )
    free(v9);
  if ( hAuthzClientContext )
    AuthzFreeContext(hAuthzClientContext);
  SamIFreeAuthzSecurityAttributesInfo(v41);
  return v10;
}

```

## disassembly

```asm
0x180054504  push    rbp
0x180054506  push    rbx
0x180054507  push    rsi
0x180054508  push    rdi
0x180054509  push    r12
0x18005450b  push    r13
0x18005450d  push    r14
0x18005450f  push    r15
0x180054511  lea     rbp, [rsp-17h]
0x180054516  sub     rsp, 98h
0x18005451d  xor     r12d, r12d
0x180054520  xorps   xmm0, xmm0
0x180054523  mov     r15b, r9b
0x180054526  mov     r14, r8
0x180054529  mov     rsi, rdx
0x18005452c  mov     r13, rcx
0x18005452f  mov     edi, r12d
0x180054532  mov     [rbp+4Fh+arg_8], r12d
0x180054536  movups  xmmword ptr [rbp+4Fh+Block], xmm0
0x18005453a  mov     [rbp+4Fh+var_90], r12
0x18005453e  mov     [rbp+4Fh+hAuthzClientContext], r12
0x180054542  movups  [rbp+4Fh+var_50], xmm0
0x180054546  mov     qword ptr [rbp+4Fh+var_80.LowPart], r12
0x18005454a  movups  [rbp+4Fh+var_60], xmm0
0x18005454e  cmp     [rdx+94h], r12d
0x180054555  jnz     short loc_180054584
0x180054557  test    byte ptr [rdx+0A8h], 20h
0x18005455e  jz      short loc_180054569
0x180054560  cmp     [rdx+110h], r12d
0x180054567  jnz     short loc_180054584
0x180054569  lea     rdx, aNlpcreateauthz; "NlpCreateAuthzContext received authoriz"...
0x180054570  mov     ecx, 100h; unsigned int
0x180054575  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005457a  mov     ebx, 0C000000Dh
0x18005457f  jmp     loc_1800547F6
0x180054584  lea     r8, [rbp+4Fh+arg_8]; unsigned int *
0x180054588  mov     rcx, rsi; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x18005458b  lea     rdx, [rbp+4Fh+Block]; struct _SAMPR_PSID_ARRAY *
0x18005458f  call    ?NlpBuildPacSidList@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_SAMPR_PSID_ARRAY@@PEAK@Z; NlpBuildPacSidList(_NETLOGON_VALIDATION_SAM_INFO4 *,_SAMPR_PSID_ARRAY *,ulong *)
0x180054594  mov     ebx, eax
0x180054596  test    eax, eax
0x180054598  jns     short loc_1800545B3
0x18005459a  lea     rdx, aFailedToBuildS; "Failed to build SID list from user info"...
0x1800545a1  mov     r8d, eax
0x1800545a4  mov     ecx, 800h; unsigned int
0x1800545a9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800545ae  jmp     loc_1800547F6
0x1800545b3  test    r15b, r15b
0x1800545b6  jz      short loc_1800545E5
0x1800545b8  mov     rcx, [r13+178h]
0x1800545bf  lea     r9, [rbp+4Fh+var_90]
0x1800545c3  xor     r8d, r8d
0x1800545c6  lea     rdx, [rbp+4Fh+Block]
0x1800545ca  call    cs:__imp_SamIGetResourceGroupMembershipsTransitive
0x1800545d1  nop     dword ptr [rax+rax+00h]
0x1800545d6  mov     ebx, eax
0x1800545d8  test    eax, eax
0x1800545da  jns     short loc_1800545E5
0x1800545dc  lea     rdx, aFailedToExpand; "Failed to expand resource groups for A2"...
0x1800545e3  jmp     short loc_1800545A1
0x1800545e5  mov     rcx, [rbp+4Fh+var_90]
0x1800545e9  mov     eax, dword ptr [rbp+4Fh+Block]
0x1800545ec  test    rcx, rcx
0x1800545ef  jz      short loc_1800545F3
0x1800545f1  add     eax, [rcx]
0x1800545f3  lea     r15d, [rax+2]
0x1800545f7  mov     ecx, r15d
0x1800545fa  shl     rcx, 4; size
0x1800545fe  call    MIDL_user_allocate
0x180054603  mov     rdi, rax
0x180054606  test    rax, rax
0x180054609  jnz     short loc_180054615
0x18005460b  mov     ebx, 0C000009Ah
0x180054610  jmp     loc_1800547F6
0x180054615  mov     r8d, r12d
0x180054618  cmp     dword ptr [rbp+4Fh+Block], r12d
0x18005461c  jbe     short loc_180054644
0x18005461e  mov     rax, [rbp+4Fh+Block+8]
0x180054622  mov     ecx, r8d
0x180054625  mov     edx, r8d
0x180054628  inc     r8d
0x18005462b  add     rdx, rdx
0x18005462e  mov     rcx, [rax+rcx*8]
0x180054632  mov     [rdi+rdx*8], rcx
0x180054636  mov     dword ptr [rdi+rdx*8+8], 7
0x18005463e  cmp     r8d, dword ptr [rbp+4Fh+Block]
0x180054642  jb      short loc_18005461E
0x180054644  mov     rax, [rbp+4Fh+var_90]
0x180054648  mov     r10d, 20000007h
0x18005464e  test    rax, rax
0x180054651  jz      short loc_180054684
0x180054653  mov     r9d, r12d
0x180054656  cmp     [rax], r12d
0x180054659  jbe     short loc_180054684
0x18005465b  mov     rax, [rax+8]
0x18005465f  mov     edx, r8d
0x180054662  inc     r8d
0x180054665  add     rdx, rdx
0x180054668  mov     ecx, r9d
0x18005466b  inc     r9d; char *
0x18005466e  mov     rcx, [rax+rcx*8]
0x180054672  mov     [rdi+rdx*8], rcx
0x180054676  mov     [rdi+rdx*8+8], r10d
0x18005467b  mov     rax, [rbp+4Fh+var_90]
0x18005467f  cmp     r9d, [rax]
0x180054682  jb      short loc_18005465B
0x180054684  mov     rax, cs:WorldSid
0x18005468b  mov     ecx, r8d
0x18005468e  inc     r8d
0x180054691  add     rcx, rcx
0x180054694  mov     [rdi+rcx*8], rax
0x180054698  mov     [rdi+rcx*8+8], r10d
0x18005469d  mov     rax, cs:AuthenticatedUserSid
0x1800546a4  mov     ecx, r8d
0x1800546a7  add     rcx, rcx
0x1800546aa  mov     [rdi+rcx*8], rax
0x1800546ae  lea     eax, [r8+1]
0x1800546b2  mov     [rdi+rcx*8+8], r10d
0x1800546b7  cmp     eax, r15d
0x1800546ba  jz      short loc_1800546D5
0x1800546bc  mov     r8d, 394h; unsigned int
0x1800546c2  lea     rdx, aOnecoreDsNetap_12; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800546c9  lea     rcx, aSidindexSidand; "SidIndex == SidAndAttributesCount"
0x1800546d0  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800546d5  cmp     [rsi+94h], r12d
0x1800546dc  jz      short loc_1800546E3
0x1800546de  mov     rax, rdi
0x1800546e1  jmp     short loc_1800546ED
0x1800546e3  mov     eax, [rbp+4Fh+arg_8]
0x1800546e6  shl     rax, 4
0x1800546ea  add     rax, rdi
0x1800546ed  mov     rbx, [rax]
0x1800546f0  xor     r9d, r9d; pExpirationTime
0x1800546f3  mov     r8, cs:?NlAuthzRM@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA; hAuthzResourceManager
0x1800546fa  xor     eax, eax
0x1800546fc  mov     dword ptr [rbp+4Fh+var_60+0Ch], eax
0x1800546ff  mov     rdx, rbx; UserSid
0x180054702  mov     qword ptr [rbp+4Fh+var_60], rdi
0x180054706  lea     rax, [rbp+4Fh+hAuthzClientContext]
0x18005470a  mov     [rsp+0D0h+phAuthzClientContext], rax; phAuthzClientContext
0x18005470f  lea     ecx, [r9+2]; Flags
0x180054713  mov     dword ptr [rbp+4Fh+var_60+8], r15d
0x180054717  lea     rax, [rbp+4Fh+var_60]
0x18005471b  movaps  xmm0, [rbp+4Fh+var_60]
0x18005471f  mov     [rsp+0D0h+DynamicGroupArgs], rax; DynamicGroupArgs
0x180054724  mov     rax, qword ptr [rbp+4Fh+var_80.LowPart]
0x180054728  mov     qword ptr [rsp+0D0h+Identifier.LowPart], rax; Identifier
0x18005472d  movdqa  [rbp+4Fh+var_60], xmm0
0x180054732  call    cs:__imp_AuthzInitializeContextFromSid
0x180054739  nop     dword ptr [rax+rax+00h]
0x18005473e  test    eax, eax
0x180054740  jnz     short loc_180054772
0x180054742  call    cs:__imp_GetLastError
0x180054749  nop     dword ptr [rax+rax+00h]
0x18005474e  lea     rdx, aNlpcreateauthz_1; "NlpCreateAuthzContext: AuthzInitializeC"...
0x180054755  mov     r8d, eax
0x180054758  mov     ecx, 100h; unsigned int
0x18005475d  mov     ebx, eax
0x18005475f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054764  mov     ecx, ebx
0x180054766  call    NetpApiStatusToNtStatus
0x18005476b  mov     ebx, eax
0x18005476d  jmp     loc_1800547F6
0x180054772  test    r14, r14
0x180054775  jz      short loc_1800547E4
0x180054777  cmp     [r14], r12d
0x18005477a  jbe     short loc_1800547E4
0x18005477c  lea     r8, [rbp+4Fh+var_50]
0x180054780  mov     [rbp+4Fh+arg_8], 1
0x180054787  mov     rdx, r14
0x18005478a  mov     rcx, rbx
0x18005478d  call    cs:__imp_SamIDecodeClaimsBlobToAuthz
0x180054794  nop     dword ptr [rax+rax+00h]
0x180054799  mov     ebx, eax
0x18005479b  test    eax, eax
0x18005479d  jns     short loc_1800547AB
0x18005479f  lea     rdx, aSamidecodeclai_0; "SamIDecodeClaimsBlobToAuthz failed to d"...
0x1800547a6  jmp     loc_1800545A1
0x1800547ab  mov     rcx, [rbp+4Fh+hAuthzClientContext]
0x1800547af  lea     r9, [rbp+4Fh+var_50]
0x1800547b3  lea     r8, [rbp+4Fh+arg_8]
0x1800547b7  mov     edx, 0Dh
0x1800547bc  call    cs:__imp_AuthzModifyClaims
0x1800547c3  nop     dword ptr [rax+rax+00h]
0x1800547c8  test    eax, eax
0x1800547ca  jnz     short loc_1800547E4
0x1800547cc  call    cs:__imp_GetLastError
0x1800547d3  nop     dword ptr [rax+rax+00h]
0x1800547d8  lea     rdx, aNlpcreateauthz_0; "NlpCreateAuthzContext: AuthzModifyClaim"...
0x1800547df  jmp     loc_180054755
0x1800547e4  mov     rcx, [rbp+4Fh+hAuthzClientContext]
0x1800547e8  mov     ebx, r12d
0x1800547eb  mov     rax, [rbp+4Fh+arg_20]
0x1800547ef  mov     [rbp+4Fh+hAuthzClientContext], r12
0x1800547f3  mov     [rax], rcx
0x1800547f6  mov     rax, [rbp+4Fh+Block+8]
0x1800547fa  test    rax, rax
0x1800547fd  jz      short loc_180054834
0x1800547ff  mov     esi, r12d
0x180054802  cmp     dword ptr [rbp+4Fh+Block], r12d
0x180054806  jbe     short loc_180054825
0x180054808  mov     ecx, esi
0x18005480a  mov     rcx, [rax+rcx*8]; Block
0x18005480e  call    cs:__imp_free
0x180054815  nop     dword ptr [rax+rax+00h]
0x18005481a  mov     rax, [rbp+4Fh+Block+8]
0x18005481e  inc     esi
0x180054820  cmp     esi, dword ptr [rbp+4Fh+Block]
0x180054823  jb      short loc_180054808
0x180054825  mov     rcx, rax; Block
0x180054828  call    cs:__imp_free
0x18005482f  nop     dword ptr [rax+rax+00h]
0x180054834  mov     rcx, [rbp+4Fh+var_90]
0x180054838  test    rcx, rcx
0x18005483b  jz      short loc_180054849
0x18005483d  call    cs:__imp_SamIFreeSidArray
0x180054844  nop     dword ptr [rax+rax+00h]
0x180054849  test    rdi, rdi
0x18005484c  jz      short loc_18005485D
0x18005484e  mov     rcx, rdi; Block
0x180054851  call    cs:__imp_free
0x180054858  nop     dword ptr [rax+rax+00h]
0x18005485d  mov     rcx, [rbp+4Fh+hAuthzClientContext]; hAuthzClientContext
0x180054861  test    rcx, rcx
0x180054864  jz      short loc_180054872
0x180054866  call    cs:__imp_AuthzFreeContext
0x18005486d  nop     dword ptr [rax+rax+00h]
0x180054872  lea     rcx, [rbp+4Fh+var_50]
0x180054876  call    cs:__imp_SamIFreeAuthzSecurityAttributesInfo
0x18005487d  nop     dword ptr [rax+rax+00h]
0x180054882  mov     eax, ebx
0x180054884  add     rsp, 98h
0x18005488b  pop     r15
0x18005488d  pop     r14
0x18005488f  pop     r13
0x180054891  pop     r12
0x180054893  pop     rdi
0x180054894  pop     rsi
0x180054895  pop     rbx
0x180054896  pop     rbp
0x180054897  retn
```
