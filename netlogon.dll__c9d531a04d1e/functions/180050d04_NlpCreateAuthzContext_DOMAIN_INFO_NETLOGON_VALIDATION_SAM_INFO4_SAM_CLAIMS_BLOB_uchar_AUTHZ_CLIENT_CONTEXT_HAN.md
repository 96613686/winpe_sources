# NlpCreateAuthzContext(_DOMAIN_INFO *,_NETLOGON_VALIDATION_SAM_INFO4 *,_SAM_CLAIMS_BLOB *,uchar,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)

- ea: `0x180050d04`
- end: `0x18005104a`
- name: `?NlpCreateAuthzContext@@YAJPEAU_DOMAIN_INFO@@PEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_SAM_CLAIMS_BLOB@@EPEAPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@@Z`
- size: `838`
- prototype: `int(struct _DOMAIN_INFO *, struct _NETLOGON_VALIDATION_SAM_INFO4 *, struct _SAM_CLAIMS_BLOB *, unsigned __int8, struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005113c`

## callees

- `0x180007278`
- `0x18000d100`
- `0x18000d710`
- `0x180050b20`
- `0x180050d04`
- `0x1800844d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180050fe4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180050ff8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051015`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180050fe4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180050ff8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180051015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050fab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050fab`
- `AUTHZ!AuthzModifyClaims` at `0x180050fa1`
- `AUTHZ!AuthzModifyClaims` at `0x180050fa1`
- `AUTHZ!AuthzFreeContext` at `0x180051024`
- `AUTHZ!AuthzFreeContext` at `0x180051024`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x180050f2c`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x180050f2c`
- `SAMSRV!SamIFreeAuthzSecurityAttributesInfo` at `0x18005102e`
- `SAMSRV!SamIFreeAuthzSecurityAttributesInfo` at `0x18005102e`
- `SAMSRV!SamIFreeSidArray` at `0x180051007`
- `SAMSRV!SamIFreeSidArray` at `0x180051007`
- `SAMSRV!SamIDecodeClaimsBlobToAuthz` at `0x180050f78`
- `SAMSRV!SamIDecodeClaimsBlobToAuthz` at `0x180050f78`
- `SAMSRV!SamIGetResourceGroupMembershipsTransitive` at `0x180050dca`
- `SAMSRV!SamIGetResourceGroupMembershipsTransitive` at `0x180050dca`

## string_xrefs

- `0x180050ebc`: `onecore\ds\netapi\svcdlls\logonsrv\server\rgroups.cxx`
- `0x180050d69`: `NlpCreateAuthzContext received authorization data with no user RID or extra SID!\n`
- `0x180050d9a`: `Failed to build SID list from user information: 0x%08X\n`
- `0x180050ec3`: `SidIndex == SidAndAttributesCount`
- `0x180050f3c`: `NlpCreateAuthzContext: AuthzInitializeContextFromSid failed 0x%lx\n`
- `0x180050fb1`: `NlpCreateAuthzContext: AuthzModifyClaims failed 0x%lx\n`

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
        916,
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
0x180050d04  push    rbp
0x180050d06  push    rbx
0x180050d07  push    rsi
0x180050d08  push    rdi
0x180050d09  push    r12
0x180050d0b  push    r13
0x180050d0d  push    r14
0x180050d0f  push    r15
0x180050d11  lea     rbp, [rsp-17h]
0x180050d16  sub     rsp, 98h
0x180050d1d  xor     r12d, r12d
0x180050d20  xorps   xmm0, xmm0
0x180050d23  mov     r15b, r9b
0x180050d26  mov     r14, r8
0x180050d29  mov     rsi, rdx
0x180050d2c  mov     r13, rcx
0x180050d2f  mov     edi, r12d
0x180050d32  mov     [rbp+4Fh+arg_8], r12d
0x180050d36  movups  xmmword ptr [rbp+4Fh+Block], xmm0
0x180050d3a  mov     [rbp+4Fh+var_90], r12
0x180050d3e  mov     [rbp+4Fh+hAuthzClientContext], r12
0x180050d42  movups  [rbp+4Fh+var_50], xmm0
0x180050d46  mov     qword ptr [rbp+4Fh+var_80.LowPart], r12
0x180050d4a  movups  [rbp+4Fh+var_60], xmm0
0x180050d4e  cmp     [rdx+94h], r12d
0x180050d55  jnz     short loc_180050D84
0x180050d57  test    byte ptr [rdx+0A8h], 20h
0x180050d5e  jz      short loc_180050D69
0x180050d60  cmp     [rdx+110h], r12d
0x180050d67  jnz     short loc_180050D84
0x180050d69  lea     rdx, aNlpcreateauthz; "NlpCreateAuthzContext received authoriz"...
0x180050d70  mov     ecx, 100h; unsigned int
0x180050d75  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180050d7a  mov     ebx, 0C000000Dh
0x180050d7f  jmp     loc_180050FCC
0x180050d84  lea     r8, [rbp+4Fh+arg_8]; unsigned int *
0x180050d88  mov     rcx, rsi; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x180050d8b  lea     rdx, [rbp+4Fh+Block]; struct _SAMPR_PSID_ARRAY *
0x180050d8f  call    ?NlpBuildPacSidList@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_SAMPR_PSID_ARRAY@@PEAK@Z; NlpBuildPacSidList(_NETLOGON_VALIDATION_SAM_INFO4 *,_SAMPR_PSID_ARRAY *,ulong *)
0x180050d94  mov     ebx, eax
0x180050d96  test    eax, eax
0x180050d98  jns     short loc_180050DB3
0x180050d9a  lea     rdx, aFailedToBuildS; "Failed to build SID list from user info"...
0x180050da1  mov     r8d, eax
0x180050da4  mov     ecx, 800h; unsigned int
0x180050da9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180050dae  jmp     loc_180050FCC
0x180050db3  test    r15b, r15b
0x180050db6  jz      short loc_180050DDF
0x180050db8  mov     rcx, [r13+178h]
0x180050dbf  lea     r9, [rbp+4Fh+var_90]
0x180050dc3  xor     r8d, r8d
0x180050dc6  lea     rdx, [rbp+4Fh+Block]
0x180050dca  call    cs:__imp_SamIGetResourceGroupMembershipsTransitive
0x180050dd0  mov     ebx, eax
0x180050dd2  test    eax, eax
0x180050dd4  jns     short loc_180050DDF
0x180050dd6  lea     rdx, aFailedToExpand; "Failed to expand resource groups for A2"...
0x180050ddd  jmp     short loc_180050DA1
0x180050ddf  mov     rcx, [rbp+4Fh+var_90]
0x180050de3  mov     eax, dword ptr [rbp+4Fh+Block]
0x180050de6  test    rcx, rcx
0x180050de9  jz      short loc_180050DED
0x180050deb  add     eax, [rcx]
0x180050ded  lea     r15d, [rax+2]
0x180050df1  mov     ecx, r15d
0x180050df4  shl     rcx, 4; size
0x180050df8  call    MIDL_user_allocate
0x180050dfd  mov     rdi, rax
0x180050e00  test    rax, rax
0x180050e03  jnz     short loc_180050E0F
0x180050e05  mov     ebx, 0C000009Ah
0x180050e0a  jmp     loc_180050FCC
0x180050e0f  mov     r8d, r12d
0x180050e12  cmp     dword ptr [rbp+4Fh+Block], r12d
0x180050e16  jbe     short loc_180050E3E
0x180050e18  mov     rax, [rbp+4Fh+Block+8]
0x180050e1c  mov     ecx, r8d
0x180050e1f  mov     edx, r8d
0x180050e22  inc     r8d
0x180050e25  add     rdx, rdx
0x180050e28  mov     rcx, [rax+rcx*8]
0x180050e2c  mov     [rdi+rdx*8], rcx
0x180050e30  mov     dword ptr [rdi+rdx*8+8], 7
0x180050e38  cmp     r8d, dword ptr [rbp+4Fh+Block]
0x180050e3c  jb      short loc_180050E18
0x180050e3e  mov     rax, [rbp+4Fh+var_90]
0x180050e42  mov     r10d, 20000007h
0x180050e48  test    rax, rax
0x180050e4b  jz      short loc_180050E7E
0x180050e4d  mov     r9d, r12d
0x180050e50  cmp     [rax], r12d
0x180050e53  jbe     short loc_180050E7E
0x180050e55  mov     rax, [rax+8]
0x180050e59  mov     edx, r8d
0x180050e5c  inc     r8d
0x180050e5f  add     rdx, rdx
0x180050e62  mov     ecx, r9d
0x180050e65  inc     r9d; char *
0x180050e68  mov     rcx, [rax+rcx*8]
0x180050e6c  mov     [rdi+rdx*8], rcx
0x180050e70  mov     [rdi+rdx*8+8], r10d
0x180050e75  mov     rax, [rbp+4Fh+var_90]
0x180050e79  cmp     r9d, [rax]
0x180050e7c  jb      short loc_180050E55
0x180050e7e  mov     rax, cs:WorldSid
0x180050e85  mov     ecx, r8d
0x180050e88  inc     r8d
0x180050e8b  add     rcx, rcx
0x180050e8e  mov     [rdi+rcx*8], rax
0x180050e92  mov     [rdi+rcx*8+8], r10d
0x180050e97  mov     rax, cs:AuthenticatedUserSid
0x180050e9e  mov     ecx, r8d
0x180050ea1  add     rcx, rcx
0x180050ea4  mov     [rdi+rcx*8], rax
0x180050ea8  lea     eax, [r8+1]
0x180050eac  mov     [rdi+rcx*8+8], r10d
0x180050eb1  cmp     eax, r15d
0x180050eb4  jz      short loc_180050ECF
0x180050eb6  mov     r8d, 394h; unsigned int
0x180050ebc  lea     rdx, aOnecoreDsNetap_12; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180050ec3  lea     rcx, aSidindexSidand; "SidIndex == SidAndAttributesCount"
0x180050eca  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180050ecf  cmp     [rsi+94h], r12d
0x180050ed6  jz      short loc_180050EDD
0x180050ed8  mov     rax, rdi
0x180050edb  jmp     short loc_180050EE7
0x180050edd  mov     eax, [rbp+4Fh+arg_8]
0x180050ee0  shl     rax, 4
0x180050ee4  add     rax, rdi
0x180050ee7  mov     rbx, [rax]
0x180050eea  xor     r9d, r9d; pExpirationTime
0x180050eed  mov     r8, cs:?NlAuthzRM@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA; hAuthzResourceManager
0x180050ef4  xor     eax, eax
0x180050ef6  mov     dword ptr [rbp+4Fh+var_60+0Ch], eax
0x180050ef9  mov     rdx, rbx; UserSid
0x180050efc  mov     qword ptr [rbp+4Fh+var_60], rdi
0x180050f00  lea     rax, [rbp+4Fh+hAuthzClientContext]
0x180050f04  mov     [rsp+0D0h+phAuthzClientContext], rax; phAuthzClientContext
0x180050f09  lea     ecx, [r9+2]; Flags
0x180050f0d  mov     dword ptr [rbp+4Fh+var_60+8], r15d
0x180050f11  lea     rax, [rbp+4Fh+var_60]
0x180050f15  movaps  xmm0, [rbp+4Fh+var_60]
0x180050f19  mov     [rsp+0D0h+DynamicGroupArgs], rax; DynamicGroupArgs
0x180050f1e  mov     rax, qword ptr [rbp+4Fh+var_80.LowPart]
0x180050f22  mov     qword ptr [rsp+0D0h+Identifier.LowPart], rax; Identifier
0x180050f27  movdqa  [rbp+4Fh+var_60], xmm0
0x180050f2c  call    cs:__imp_AuthzInitializeContextFromSid
0x180050f32  test    eax, eax
0x180050f34  jnz     short loc_180050F5D
0x180050f36  call    cs:__imp_GetLastError
0x180050f3c  lea     rdx, aNlpcreateauthz_1; "NlpCreateAuthzContext: AuthzInitializeC"...
0x180050f43  mov     r8d, eax
0x180050f46  mov     ecx, 100h; unsigned int
0x180050f4b  mov     ebx, eax
0x180050f4d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180050f52  mov     ecx, ebx
0x180050f54  call    NetpApiStatusToNtStatus
0x180050f59  mov     ebx, eax
0x180050f5b  jmp     short loc_180050FCC
0x180050f5d  test    r14, r14
0x180050f60  jz      short loc_180050FBA
0x180050f62  cmp     [r14], r12d
0x180050f65  jbe     short loc_180050FBA
0x180050f67  lea     r8, [rbp+4Fh+var_50]
0x180050f6b  mov     [rbp+4Fh+arg_8], 1
0x180050f72  mov     rdx, r14
0x180050f75  mov     rcx, rbx
0x180050f78  call    cs:__imp_SamIDecodeClaimsBlobToAuthz
0x180050f7e  mov     ebx, eax
0x180050f80  test    eax, eax
0x180050f82  jns     short loc_180050F90
0x180050f84  lea     rdx, aSamidecodeclai_0; "SamIDecodeClaimsBlobToAuthz failed to d"...
0x180050f8b  jmp     loc_180050DA1
0x180050f90  mov     rcx, [rbp+4Fh+hAuthzClientContext]
0x180050f94  lea     r9, [rbp+4Fh+var_50]
0x180050f98  lea     r8, [rbp+4Fh+arg_8]
0x180050f9c  mov     edx, 0Dh
0x180050fa1  call    cs:__imp_AuthzModifyClaims
0x180050fa7  test    eax, eax
0x180050fa9  jnz     short loc_180050FBA
0x180050fab  call    cs:__imp_GetLastError
0x180050fb1  lea     rdx, aNlpcreateauthz_0; "NlpCreateAuthzContext: AuthzModifyClaim"...
0x180050fb8  jmp     short loc_180050F43
0x180050fba  mov     rcx, [rbp+4Fh+hAuthzClientContext]
0x180050fbe  mov     ebx, r12d
0x180050fc1  mov     rax, [rbp+4Fh+arg_20]
0x180050fc5  mov     [rbp+4Fh+hAuthzClientContext], r12
0x180050fc9  mov     [rax], rcx
0x180050fcc  mov     rax, [rbp+4Fh+Block+8]
0x180050fd0  test    rax, rax
0x180050fd3  jz      short loc_180050FFE
0x180050fd5  mov     esi, r12d
0x180050fd8  cmp     dword ptr [rbp+4Fh+Block], r12d
0x180050fdc  jbe     short loc_180050FF5
0x180050fde  mov     ecx, esi
0x180050fe0  mov     rcx, [rax+rcx*8]; Block
0x180050fe4  call    cs:__imp_free
0x180050fea  mov     rax, [rbp+4Fh+Block+8]
0x180050fee  inc     esi
0x180050ff0  cmp     esi, dword ptr [rbp+4Fh+Block]
0x180050ff3  jb      short loc_180050FDE
0x180050ff5  mov     rcx, rax; Block
0x180050ff8  call    cs:__imp_free
0x180050ffe  mov     rcx, [rbp+4Fh+var_90]
0x180051002  test    rcx, rcx
0x180051005  jz      short loc_18005100D
0x180051007  call    cs:__imp_SamIFreeSidArray
0x18005100d  test    rdi, rdi
0x180051010  jz      short loc_18005101B
0x180051012  mov     rcx, rdi; Block
0x180051015  call    cs:__imp_free
0x18005101b  mov     rcx, [rbp+4Fh+hAuthzClientContext]; hAuthzClientContext
0x18005101f  test    rcx, rcx
0x180051022  jz      short loc_18005102A
0x180051024  call    cs:__imp_AuthzFreeContext
0x18005102a  lea     rcx, [rbp+4Fh+var_50]
0x18005102e  call    cs:__imp_SamIFreeAuthzSecurityAttributesInfo
0x180051034  mov     eax, ebx
0x180051036  add     rsp, 98h
0x18005103d  pop     r15
0x18005103f  pop     r14
0x180051041  pop     r13
0x180051043  pop     r12
0x180051045  pop     rdi
0x180051046  pop     rsi
0x180051047  pop     rbx
0x180051048  pop     rbp
0x180051049  retn
```
