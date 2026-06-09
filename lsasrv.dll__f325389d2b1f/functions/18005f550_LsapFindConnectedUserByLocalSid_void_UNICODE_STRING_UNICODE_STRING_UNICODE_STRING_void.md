# LsapFindConnectedUserByLocalSid(void *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void * *)

- ea: `0x18005f550`
- end: `0x18005fa2a`
- name: `?LsapFindConnectedUserByLocalSid@@YAJPEAXPEAU_UNICODE_STRING@@11PEAPEAX@Z`
- size: `1242`
- prototype: `__int64 __usercall@<rax>(PSID SourceSid@<rcx>, struct _UNICODE_STRING *@<rdx>, struct _UNICODE_STRING *@<r8>, struct _UNICODE_STRING *@<r9>, void **)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005c8b4`
- `0x18005eda0`
- `0x1800cd9e8`
- `0x180126b7c`

## callees

- `0x18000c300`
- `0x18000d3b0`
- `0x18000dd90`
- `0x180011278`
- `0x18005f550`
- `0x18005fa30`
- `0x18005faf0`
- `0x18005fecc`
- `0x1800b86d0`
- `0x1800bbbfc`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18005f622`
- `ntdll!RtlCopySid` at `0x18005f9af`
- `ntdll!RtlCopySid` at `0x18005f622`
- `ntdll!RtlCopySid` at `0x18005f9af`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005f632`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005f648`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005f67b`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005f632`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005f648`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005f67b`
- `ntdll!RtlSubAuthoritySid` at `0x18005f669`
- `ntdll!RtlSubAuthoritySid` at `0x18005f669`
- `ntdll!RtlEqualSid` at `0x18005f696`
- `ntdll!RtlEqualSid` at `0x18005f696`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrOpenUser` at `0x18005f6cd`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrOpenUser` at `0x18005f6cd`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x18005f794`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x18005f83f`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x18005f794`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x18005f83f`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrCloseHandle` at `0x18005f761`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrCloseHandle` at `0x18005f761`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrQueryInformationUser` at `0x18005f700`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrQueryInformationUser` at `0x18005f8b0`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrQueryInformationUser` at `0x18005f700`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrQueryInformationUser` at `0x18005f8b0`

## string_xrefs

- `0x18005f850`: `LsapFindConnectedUserByLocalSid: LsapSamExtOpenUser`
- `0x18005fa14`: `LsapFindConnectedUserByLocalSid: LsapSamExtQueryInformationUser(UserExtendedInformation)`
- `0x18005f91a`: `LsapFindConnectedUserByLocalSid: LsapLazyInitSamConnection`
- `0x18005fa03`: `LsapFindConnectedUserByLocalSid: LsapSamExtQueryInformationUser(SamAccountInformation)`
- `0x18005f993`: `LsapFindConnectedUserByLocalSid: LsapDuplicateString(AccountName)`
- `0x18005f8f4`: `LsapFindConnectedUserByLocalSid: LsapDuplicateString(DisplayName)`
- `0x18005f821`: `LsapFindConnectedUserByLocalSid: LsapDuplicateString(InternetSID)`
- `0x18005f9c7`: `LsapFindConnectedUserByLocalSid: RtlCopySid`

## pseudocode

```c
__int64 __fastcall LsapFindConnectedUserByLocalSid(
        PSID SourceSid,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        void **a5)
{
  int v8; // ebx
  void *v9; // rdx
  int inited; // eax
  unsigned int v11; // ebx
  PUCHAR v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  ULONG v15; // edi
  __int64 v16; // rcx
  void *v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rdi
  __int64 v25; // rdi
  ULONG v27; // ebx
  void *NoZero; // rax
  const char *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rbx
  int v33; // eax
  __int64 v34; // r9
  int v35; // eax
  NTSTATUS v36; // eax
  __int64 v37; // [rsp+20h] [rbp-51h] BYREF
  __int64 v38; // [rsp+28h] [rbp-49h] BYREF
  __int64 v39; // [rsp+30h] [rbp-41h] BYREF
  _BYTE DestinationSid[80]; // [rsp+40h] [rbp-31h] BYREF

  v37 = 0;
  v39 = 0;
  v38 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !g_cRegisteredIdProv || !g_fHasInitIdProvExtension )
  {
    v8 = -1073741637;
LABEL_9:
    LsapFreeString(a2);
    LsapFreeString(a3);
    LsapFreeString(0);
    if ( a5 && *a5 )
      LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)*a5, v9);
    return (unsigned int)v8;
  }
  inited = LsapLazyInitSamConnection();
  v8 = inited;
  if ( inited < 0 )
  {
    v30 = (unsigned int)inited;
    v29 = "LsapFindConnectedUserByLocalSid: LsapLazyInitSamConnection";
    goto LABEL_45;
  }
  RtlCopySid(0x44u, DestinationSid, SourceSid);
  v11 = *RtlSubAuthorityCountSid(DestinationSid);
  v12 = RtlSubAuthorityCountSid(g_IdProvExtDomainSid);
  v14 = v11;
  if ( v11 != *v12 + 1 )
  {
    v8 = -1073741724;
    v22 = (__int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_25;
    v31 = 10;
LABEL_56:
    v34 = 3221225572LL;
LABEL_57:
    WPP_SF_d(*(_QWORD *)(v22 + 16), v31, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids, v34);
    goto LABEL_25;
  }
  v15 = *RtlSubAuthoritySid(DestinationSid, v11 - 1);
  *RtlSubAuthorityCountSid(DestinationSid) = v11 - 1;
  if ( !RtlEqualSid(g_IdProvExtDomainSid, DestinationSid) )
  {
    v8 = -1073741724;
    v22 = (__int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_25;
    v31 = 11;
    goto LABEL_56;
  }
  v17 = g_hIdProvExtSamAccountDomain;
  if ( !(unsigned __int8)IsSamIDecodeClaimsBlobPresent(v16, v14, v13) )
  {
    v8 = -1073741637;
    goto LABEL_43;
  }
  v8 = SamrOpenUser(v17, 985087, v15, &v37);
  if ( v8 < 0 )
  {
LABEL_43:
    v29 = "LsapFindConnectedUserByLocalSid: LsapSamExtOpenUser";
LABEL_44:
    v30 = (unsigned int)v8;
LABEL_45:
    CONNECTED_TRACE_ERROR(v29, v30);
    goto LABEL_25;
  }
  v21 = v37;
  if ( !(unsigned __int8)IsSamIDecodeClaimsBlobPresent(v19, v18, v20) )
  {
    v8 = -1073741637;
    goto LABEL_71;
  }
  v8 = SamrQueryInformationUser(v21, 28, &v38);
  if ( v8 < 0 )
  {
LABEL_71:
    v29 = "LsapFindConnectedUserByLocalSid: LsapSamExtQueryInformationUser(UserExtendedInformation)";
    goto LABEL_44;
  }
  v22 = 1441792;
  if ( (*(_DWORD *)v38 & 0x160000) != 0x160000 )
    goto LABEL_24;
  v23 = *(_QWORD *)(v38 + 96) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v23 )
    v23 = *(_QWORD *)(v38 + 104) - *(_QWORD *)GUID_NULL.Data4;
  if ( !v23 )
  {
LABEL_24:
    v8 = -1073741724;
    goto LABEL_25;
  }
  if ( !a2 && !a3 )
    goto LABEL_36;
  v32 = v37;
  if ( !(unsigned __int8)IsSamIDecodeClaimsBlobPresent(1441792, v14, v13) )
  {
    v8 = -1073741637;
    goto LABEL_69;
  }
  v8 = SamrQueryInformationUser(v32, 5, &v39);
  if ( v8 < 0 )
  {
LABEL_69:
    v29 = "LsapFindConnectedUserByLocalSid: LsapSamExtQueryInformationUser(SamAccountInformation)";
    goto LABEL_44;
  }
  if ( a2 )
  {
    v35 = LsapDuplicateString(a2, v39);
    v8 = v35;
    if ( v35 < 0 )
    {
      v30 = (unsigned int)v35;
      v29 = "LsapFindConnectedUserByLocalSid: LsapDuplicateString(AccountName)";
      goto LABEL_45;
    }
  }
  if ( a3 )
  {
    v33 = LsapDuplicateString(a3, v39 + 16);
    v8 = v33;
    if ( v33 < 0 )
    {
      v30 = (unsigned int)v33;
      v29 = "LsapFindConnectedUserByLocalSid: LsapDuplicateString(DisplayName)";
      goto LABEL_45;
    }
  }
LABEL_36:
  if ( !a5 )
    goto LABEL_25;
  v27 = *(_DWORD *)(v38 + 128);
  if ( v27 && *(_QWORD *)(v38 + 136) )
  {
    NoZero = (void *)LsapAllocateNoZero(v27);
    *a5 = NoZero;
    if ( NoZero )
    {
      v36 = RtlCopySid(v27, NoZero, *(PSID *)(v38 + 136));
      v8 = v36;
      if ( v36 >= 0 )
        goto LABEL_25;
      v30 = (unsigned int)v36;
      v29 = "LsapFindConnectedUserByLocalSid: RtlCopySid";
      goto LABEL_45;
    }
    v8 = -1073741670;
    v29 = "LsapFindConnectedUserByLocalSid: LsapDuplicateString(InternetSID)";
    goto LABEL_44;
  }
  v8 = -1073741595;
  v22 = (__int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v31 = 13;
    v34 = 3221225701LL;
    goto LABEL_57;
  }
LABEL_25:
  if ( v37 && (unsigned __int8)IsSamIDecodeClaimsBlobPresent(v22, v14, v13) )
    SamrCloseHandle(&v37);
  v24 = v39;
  if ( v39 && (unsigned __int8)IsSamIDecodeClaimsBlobPresent(v22, v14, v13) )
    SamIFree_SAMPR_USER_INFO_BUFFER(v24, 5);
  v25 = v38;
  if ( v38 && (unsigned __int8)IsSamIDecodeClaimsBlobPresent(v22, v14, v13) )
    SamIFree_SAMPR_USER_INFO_BUFFER(v25, 28);
  if ( v8 < 0 )
    goto LABEL_9;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005f550  mov     [rsp-8+arg_18], rbx
0x18005f555  push    rbp
0x18005f556  push    rsi
0x18005f557  push    rdi
0x18005f558  push    r14
0x18005f55a  push    r15
0x18005f55c  lea     rbp, [rsp-2Fh]
0x18005f561  sub     rsp, 0A0h
0x18005f568  mov     rax, cs:__security_cookie
0x18005f56f  xor     rax, rsp
0x18005f572  mov     [rbp+4Fh+var_30], rax
0x18005f576  mov     rsi, [rbp+4Fh+arg_20]
0x18005f57a  mov     r14, r8
0x18005f57d  mov     [rbp+4Fh+var_A0], 0
0x18005f585  mov     r15, rdx
0x18005f588  mov     [rbp+4Fh+var_90], 0
0x18005f590  mov     rdi, rcx
0x18005f593  mov     [rbp+4Fh+var_98], 0
0x18005f59b  test    rdx, rdx
0x18005f59e  jnz     short loc_18005F5F6
0x18005f5a0  test    r14, r14
0x18005f5a3  jnz     loc_18005F900
0x18005f5a9  test    rsi, rsi
0x18005f5ac  jnz     loc_18005F90C
0x18005f5b2  cmp     cs:?g_cRegisteredIdProv@@3JA, 0; long g_cRegisteredIdProv
0x18005f5b9  jnz     short loc_18005F5FE
0x18005f5bb  mov     ebx, 0C00000BBh
0x18005f5c0  mov     rcx, r15
0x18005f5c3  call    LsapFreeString
0x18005f5c8  mov     rcx, r14
0x18005f5cb  call    LsapFreeString
0x18005f5d0  xor     ecx, ecx
0x18005f5d2  call    LsapFreeString
0x18005f5d7  test    rsi, rsi
0x18005f5da  jz      loc_18005F7A8
0x18005f5e0  mov     rcx, [rsi]; struct _RTL_BALANCED_NODE *
0x18005f5e3  test    rcx, rcx
0x18005f5e6  jz      loc_18005F7A8
0x18005f5ec  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18005f5f1  jmp     loc_18005F7A8
0x18005f5f6  xorps   xmm0, xmm0
0x18005f5f9  movups  xmmword ptr [rdx], xmm0
0x18005f5fc  jmp     short loc_18005F5A0
0x18005f5fe  cmp     cs:?g_fHasInitIdProvExtension@@3HA, 0; int g_fHasInitIdProvExtension
0x18005f605  jz      short loc_18005F5BB
0x18005f607  call    ?LsapLazyInitSamConnection@@YAJXZ; LsapLazyInitSamConnection(void)
0x18005f60c  mov     ebx, eax
0x18005f60e  test    eax, eax
0x18005f610  js      loc_18005F918
0x18005f616  mov     r8, rdi; SourceSid
0x18005f619  lea     rdx, [rbp+4Fh+DestinationSid]; DestinationSid
0x18005f61d  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18005f622  call    cs:__imp_RtlCopySid
0x18005f629  nop     dword ptr [rax+rax+00h]
0x18005f62e  lea     rcx, [rbp+4Fh+DestinationSid]; Sid
0x18005f632  call    cs:__imp_RtlSubAuthorityCountSid
0x18005f639  nop     dword ptr [rax+rax+00h]
0x18005f63e  mov     rcx, cs:?g_IdProvExtDomainSid@@3PEAXEA; Sid
0x18005f645  movzx   ebx, byte ptr [rax]
0x18005f648  call    cs:__imp_RtlSubAuthorityCountSid
0x18005f64f  nop     dword ptr [rax+rax+00h]
0x18005f654  mov     edx, ebx
0x18005f656  movzx   ecx, byte ptr [rax]
0x18005f659  inc     ecx
0x18005f65b  cmp     ebx, ecx
0x18005f65d  jnz     loc_18005F863
0x18005f663  dec     edx; SubAuthority
0x18005f665  lea     rcx, [rbp+4Fh+DestinationSid]; Sid
0x18005f669  call    cs:__imp_RtlSubAuthoritySid
0x18005f670  nop     dword ptr [rax+rax+00h]
0x18005f675  lea     rcx, [rbp+4Fh+DestinationSid]; Sid
0x18005f679  mov     edi, [rax]
0x18005f67b  call    cs:__imp_RtlSubAuthorityCountSid
0x18005f682  nop     dword ptr [rax+rax+00h]
0x18005f687  dec     bl
0x18005f689  lea     rdx, [rbp+4Fh+DestinationSid]; Sid2
0x18005f68d  mov     [rax], bl
0x18005f68f  mov     rcx, cs:?g_IdProvExtDomainSid@@3PEAXEA; Sid1
0x18005f696  call    cs:__imp_RtlEqualSid
0x18005f69d  nop     dword ptr [rax+rax+00h]
0x18005f6a2  test    al, al
0x18005f6a4  jz      loc_18005F953
0x18005f6aa  mov     rbx, cs:?g_hIdProvExtSamAccountDomain@@3PEAXEA; void * g_hIdProvExtSamAccountDomain
0x18005f6b1  call    IsSamIDecodeClaimsBlobPresent
0x18005f6b6  test    al, al
0x18005f6b8  jz      loc_18005FA20
0x18005f6be  lea     r9, [rbp+4Fh+var_A0]
0x18005f6c2  mov     r8d, edi
0x18005f6c5  mov     edx, 0F07FFh
0x18005f6ca  mov     rcx, rbx
0x18005f6cd  call    cs:__imp_SamrOpenUser
0x18005f6d4  nop     dword ptr [rax+rax+00h]
0x18005f6d9  mov     ebx, eax
0x18005f6db  test    eax, eax
0x18005f6dd  js      loc_18005F850
0x18005f6e3  mov     rbx, [rbp+4Fh+var_A0]
0x18005f6e7  call    IsSamIDecodeClaimsBlobPresent
0x18005f6ec  test    al, al
0x18005f6ee  jz      loc_18005FA0F
0x18005f6f4  lea     r8, [rbp+4Fh+var_98]
0x18005f6f8  mov     edx, 1Ch
0x18005f6fd  mov     rcx, rbx
0x18005f700  call    cs:__imp_SamrQueryInformationUser
0x18005f707  nop     dword ptr [rax+rax+00h]
0x18005f70c  mov     ebx, eax
0x18005f70e  test    eax, eax
0x18005f710  js      loc_18005FA14
0x18005f716  mov     rdi, [rbp+4Fh+var_98]
0x18005f71a  mov     ecx, 160000h
0x18005f71f  mov     eax, [rdi]
0x18005f721  and     eax, ecx
0x18005f723  cmp     eax, ecx
0x18005f725  jnz     short loc_18005F748
0x18005f727  mov     rax, [rdi+60h]
0x18005f72b  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18005f732  jnz     short loc_18005F73F
0x18005f734  mov     rax, [rdi+68h]
0x18005f738  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18005f73f  test    rax, rax
0x18005f742  jnz     loc_18005F7CE
0x18005f748  mov     ebx, 0C0000064h
0x18005f74d  cmp     [rbp+4Fh+var_A0], 0
0x18005f752  jz      short loc_18005F76D
0x18005f754  call    IsSamIDecodeClaimsBlobPresent
0x18005f759  test    al, al
0x18005f75b  jz      short loc_18005F76D
0x18005f75d  lea     rcx, [rbp+4Fh+var_A0]
0x18005f761  call    cs:__imp_SamrCloseHandle
0x18005f768  nop     dword ptr [rax+rax+00h]
0x18005f76d  mov     rdi, [rbp+4Fh+var_90]
0x18005f771  test    rdi, rdi
0x18005f774  jnz     loc_18005F82A
0x18005f77a  mov     rdi, [rbp+4Fh+var_98]
0x18005f77e  test    rdi, rdi
0x18005f781  jz      short loc_18005F7A0
0x18005f783  call    IsSamIDecodeClaimsBlobPresent
0x18005f788  test    al, al
0x18005f78a  jz      short loc_18005F7A0
0x18005f78c  mov     edx, 1Ch
0x18005f791  mov     rcx, rdi
0x18005f794  call    cs:__imp_SamIFree_SAMPR_USER_INFO_BUFFER
0x18005f79b  nop     dword ptr [rax+rax+00h]
0x18005f7a0  test    ebx, ebx
0x18005f7a2  js      loc_18005F5C0
0x18005f7a8  mov     eax, ebx
0x18005f7aa  mov     rcx, [rbp+4Fh+var_30]
0x18005f7ae  xor     rcx, rsp; StackCookie
0x18005f7b1  call    __security_check_cookie
0x18005f7b6  mov     rbx, [rsp+0C0h+arg_18]
0x18005f7be  add     rsp, 0A0h
0x18005f7c5  pop     r15
0x18005f7c7  pop     r14
0x18005f7c9  pop     rdi
0x18005f7ca  pop     rsi
0x18005f7cb  pop     rbp
0x18005f7cc  retn
0x18005f7ce  test    r15, r15
0x18005f7d1  jnz     loc_18005F893
0x18005f7d7  test    r14, r14
0x18005f7da  jnz     loc_18005F893
0x18005f7e0  test    rsi, rsi
0x18005f7e3  jz      loc_18005F74D
0x18005f7e9  mov     rdi, [rbp+4Fh+var_98]
0x18005f7ed  mov     ebx, [rdi+80h]
0x18005f7f3  test    ebx, ebx
0x18005f7f5  jz      loc_18005F9D3
0x18005f7fb  cmp     qword ptr [rdi+88h], 0
0x18005f803  jz      loc_18005F9D3
0x18005f809  mov     ecx, ebx
0x18005f80b  call    LsapAllocateNoZero
0x18005f810  mov     [rsi], rax
0x18005f813  test    rax, rax
0x18005f816  jnz     loc_18005F99F
0x18005f81c  mov     ebx, 0C000009Ah
0x18005f821  lea     rcx, aLsapfindconnec_10; "LsapFindConnectedUserByLocalSid: LsapDu"...
0x18005f828  jmp     short loc_18005F857
0x18005f82a  call    IsSamIDecodeClaimsBlobPresent
0x18005f82f  test    al, al
0x18005f831  jz      loc_18005F77A
0x18005f837  mov     edx, 5
0x18005f83c  mov     rcx, rdi
0x18005f83f  call    cs:__imp_SamIFree_SAMPR_USER_INFO_BUFFER
0x18005f846  nop     dword ptr [rax+rax+00h]
0x18005f84b  jmp     loc_18005F77A
0x18005f850  lea     rcx, aLsapfindconnec_9; "LsapFindConnectedUserByLocalSid: LsapSa"...
0x18005f857  mov     edx, ebx
0x18005f859  call    CONNECTED_TRACE_ERROR
0x18005f85e  jmp     loc_18005F74D
0x18005f863  mov     ebx, 0C0000064h
0x18005f868  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f86f  lea     rax, WPP_GLOBAL_Control
0x18005f876  cmp     rcx, rax
0x18005f879  jz      loc_18005F74D
0x18005f87f  test    byte ptr [rcx+1Ch], 1
0x18005f883  jz      loc_18005F74D
0x18005f889  mov     edx, 0Ah
0x18005f88e  jmp     loc_18005F92B
0x18005f893  mov     rbx, [rbp+4Fh+var_A0]
0x18005f897  call    IsSamIDecodeClaimsBlobPresent
0x18005f89c  test    al, al
0x18005f89e  jz      loc_18005F9FE
0x18005f8a4  lea     r8, [rbp+4Fh+var_90]
0x18005f8a8  mov     edx, 5
0x18005f8ad  mov     rcx, rbx
0x18005f8b0  call    cs:__imp_SamrQueryInformationUser
0x18005f8b7  nop     dword ptr [rax+rax+00h]
0x18005f8bc  mov     ebx, eax
0x18005f8be  test    eax, eax
0x18005f8c0  js      loc_18005FA03
0x18005f8c6  test    r15, r15
0x18005f8c9  jnz     loc_18005F97B
0x18005f8cf  test    r14, r14
0x18005f8d2  jz      loc_18005F7E0
0x18005f8d8  mov     rdx, [rbp+4Fh+var_90]
0x18005f8dc  mov     rcx, r14
0x18005f8df  add     rdx, 10h
0x18005f8e3  call    LsapDuplicateString
0x18005f8e8  mov     ebx, eax
0x18005f8ea  test    eax, eax
0x18005f8ec  jns     loc_18005F7E0
0x18005f8f2  mov     edx, eax
0x18005f8f4  lea     rcx, aLsapfindconnec_0; "LsapFindConnectedUserByLocalSid: LsapDu"...
0x18005f8fb  jmp     loc_18005F859
0x18005f900  xorps   xmm0, xmm0
0x18005f903  movups  xmmword ptr [r8], xmm0
0x18005f907  jmp     loc_18005F5A9
0x18005f90c  mov     qword ptr [rsi], 0
0x18005f913  jmp     loc_18005F5B2
0x18005f918  mov     edx, eax
0x18005f91a  lea     rcx, aLsapfindconnec; "LsapFindConnectedUserByLocalSid: LsapLa"...
0x18005f921  jmp     loc_18005F859
0x18005f926  mov     edx, 0Bh
0x18005f92b  mov     r9d, 0C0000064h
0x18005f931  jmp     short loc_18005F93E
0x18005f933  mov     edx, 0Dh
0x18005f938  mov     r9d, 0C00000E5h
0x18005f93e  mov     rcx, [rcx+10h]
0x18005f942  lea     r8, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids
0x18005f949  call    WPP_SF_d
0x18005f94e  jmp     loc_18005F74D
0x18005f953  mov     ebx, 0C0000064h
0x18005f958  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f95f  lea     rax, WPP_GLOBAL_Control
0x18005f966  cmp     rcx, rax
0x18005f969  jz      loc_18005F74D
0x18005f96f  test    byte ptr [rcx+1Ch], 1
0x18005f973  jz      loc_18005F74D
0x18005f979  jmp     short loc_18005F926
0x18005f97b  mov     rdx, [rbp+4Fh+var_90]
0x18005f97f  mov     rcx, r15
0x18005f982  call    LsapDuplicateString
0x18005f987  mov     ebx, eax
0x18005f989  test    eax, eax
0x18005f98b  jns     loc_18005F8CF
0x18005f991  mov     edx, eax
0x18005f993  lea     rcx, aLsapfindconnec_3; "LsapFindConnectedUserByLocalSid: LsapDu"...
0x18005f99a  jmp     loc_18005F859
0x18005f99f  mov     r8, [rbp+4Fh+var_98]
0x18005f9a3  mov     rdx, rax; DestinationSid
0x18005f9a6  mov     ecx, ebx; DestinationSidLength
0x18005f9a8  mov     r8, [r8+88h]; SourceSid
0x18005f9af  call    cs:__imp_RtlCopySid
0x18005f9b6  nop     dword ptr [rax+rax+00h]
0x18005f9bb  mov     ebx, eax
0x18005f9bd  test    eax, eax
0x18005f9bf  jns     loc_18005F74D
0x18005f9c5  mov     edx, eax
0x18005f9c7  lea     rcx, aLsapfindconnec_5; "LsapFindConnectedUserByLocalSid: RtlCop"...
0x18005f9ce  jmp     loc_18005F859
0x18005f9d3  mov     ebx, 0C00000E5h
0x18005f9d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f9df  lea     rax, WPP_GLOBAL_Control
0x18005f9e6  cmp     rcx, rax
0x18005f9e9  jz      loc_18005F74D
0x18005f9ef  test    byte ptr [rcx+1Ch], 1
0x18005f9f3  jz      loc_18005F74D
0x18005f9f9  jmp     loc_18005F933
0x18005f9fe  mov     ebx, 0C00000BBh
0x18005fa03  lea     rcx, aLsapfindconnec_8; "LsapFindConnectedUserByLocalSid: LsapSa"...
0x18005fa0a  jmp     loc_18005F857
0x18005fa0f  mov     ebx, 0C00000BBh
0x18005fa14  lea     rcx, aLsapfindconnec_6; "LsapFindConnectedUserByLocalSid: LsapSa"...
0x18005fa1b  jmp     loc_18005F857
0x18005fa20  mov     ebx, 0C00000BBh
0x18005fa25  jmp     loc_18005F850
```
