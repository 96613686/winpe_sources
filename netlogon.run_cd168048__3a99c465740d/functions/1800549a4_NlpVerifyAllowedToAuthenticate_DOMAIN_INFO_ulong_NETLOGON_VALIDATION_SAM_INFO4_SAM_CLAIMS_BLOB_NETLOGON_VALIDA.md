# NlpVerifyAllowedToAuthenticate(_DOMAIN_INFO *,ulong,_NETLOGON_VALIDATION_SAM_INFO4 *,_SAM_CLAIMS_BLOB *,_NETLOGON_VALIDATION_SAM_INFO4 *,_SAM_CLAIMS_BLOB *,uchar)

- ea: `0x1800549a4`
- end: `0x180054e22`
- name: `?NlpVerifyAllowedToAuthenticate@@YAJPEAU_DOMAIN_INFO@@KPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_SAM_CLAIMS_BLOB@@12E@Z`
- size: `1150`
- prototype: `__int64 __usercall@<rax>(struct _DOMAIN_INFO *@<rcx>, unsigned int@<edx>, struct _NETLOGON_VALIDATION_SAM_INFO4 *@<r8>, struct _SAM_CLAIMS_BLOB *@<r9>, struct _NETLOGON_VALIDATION_SAM_INFO4 *, struct _SAM_CLAIMS_BLOB *, unsigned __int8)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003033c`
- `0x1800719f4`

## callees

- `0x1800037f0`
- `0x180007518`
- `0x18000d7a0`
- `0x180054504`
- `0x1800549a4`
- `0x18008dc90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054bd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054cb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054bd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054cb9`
- `ntdll!RtlEqualSid` at `0x180054aef`
- `ntdll!RtlEqualSid` at `0x180054aef`
- `ntdll!RtlLengthSid` at `0x180054a49`
- `ntdll!RtlLengthSid` at `0x180054a49`
- `AUTHZ!AuthzFreeContext` at `0x180054da8`
- `AUTHZ!AuthzFreeContext` at `0x180054dbc`
- `AUTHZ!AuthzFreeContext` at `0x180054dd2`
- `AUTHZ!AuthzFreeContext` at `0x180054da8`
- `AUTHZ!AuthzFreeContext` at `0x180054dbc`
- `AUTHZ!AuthzFreeContext` at `0x180054dd2`
- `AUTHZ!AuthzInitializeCompoundContext` at `0x180054bc4`
- `AUTHZ!AuthzInitializeCompoundContext` at `0x180054bc4`
- `AUTHZ!AuthzAccessCheck` at `0x180054ca9`
- `AUTHZ!AuthzAccessCheck` at `0x180054d64`
- `AUTHZ!AuthzAccessCheck` at `0x180054ca9`
- `AUTHZ!AuthzAccessCheck` at `0x180054d64`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180054de8`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180054de8`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x180054a98`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x180054a98`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180054df8`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180054df8`

## string_xrefs

- `0x180054b41`: `NlpVerifyAllowedToAuthenticate failed to create user AuthZ context: 0x%08X`
- `0x180054b9c`: `NlpVerifyAllowedToAuthenticate failed to create device AuthZ context: 0x%08X`
- `0x180054bf7`: `NlpVerifyAllowedToAuthenticate failed to compound user AuthZ context gle:0x%x Status:0x%x`
- `0x180054cc5`: `NlpVerifyAllowedToAuthenticate: AuthzAccessCheck failed unexpectedly 0x%lx\n`
- `0x180054cf2`: `NlpVerifyAllowedToAuthenticate: AuthzAccessCheck failed 0x%lx\n`
- `0x180054d84`: `NlpVerifyAllowedToAuthenticate: AuthzAccessCheck failed for A2ATo 0x%lx.  This can be due to the lack of claims and compound support in NTLM\n`

## pseudocode

```c
__int64 __fastcall NlpVerifyAllowedToAuthenticate(
        struct _DOMAIN_INFO *a1,
        __int64 a2,
        struct _NETLOGON_VALIDATION_SAM_INFO4 *a3,
        struct _SAM_CLAIMS_BLOB *a4,
        struct _NETLOGON_VALIDATION_SAM_INFO4 *a5,
        struct _SAM_CLAIMS_BLOB *a6,
        unsigned __int8 a7)
{
  int v7; // r15d
  void *v10; // rcx
  struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *v11; // rdi
  struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *v12; // r12
  unsigned int v13; // ebx
  __int16 v14; // ax
  __int64 v15; // rcx
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // eax
  int v19; // eax
  signed int LastError; // eax
  struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **v21; // r14
  DWORD v22; // ebx
  AUTHZ_CLIENT_CONTEXT_HANDLE v23; // rdx
  __int64 v25; // [rsp+50h] [rbp-A1h] BYREF
  struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *v26; // [rsp+58h] [rbp-99h] BYREF
  int v27; // [rsp+60h] [rbp-91h] BYREF
  struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *v28; // [rsp+68h] [rbp-89h] BYREF
  __int64 v29; // [rsp+70h] [rbp-81h] BYREF
  PSID Sid; // [rsp+78h] [rbp-79h]
  __int128 v31; // [rsp+80h] [rbp-71h] BYREF
  __int128 v32; // [rsp+90h] [rbp-61h] BYREF
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+A0h] [rbp-51h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+C8h] [rbp-29h] BYREF
  _OWORD v35[4]; // [rsp+E8h] [rbp-9h] BYREF
  int v36; // [rsp+140h] [rbp+4Fh] BYREF
  struct _SAM_CLAIMS_BLOB *v37; // [rsp+158h] [rbp+67h]

  v37 = a4;
  v7 = 0;
  v27 = 5;
  Sid = 0;
  v25 = 0;
  v26 = 0;
  v28 = 0;
  v10 = (void *)*((_QWORD *)a1 + 23);
  v29 = 0;
  v31 = 0;
  v11 = 0;
  v12 = 0;
  v35[0] = 0;
  memset(&pRequest, 0, sizeof(pRequest));
  v36 = 0;
  v32 = 0;
  memset(&pReply, 0, sizeof(pReply));
  if ( (unsigned int)NetpDomainIdToSid(v10) )
  {
    v13 = -1073741670;
    goto LABEL_40;
  }
  *((_QWORD *)&v31 + 1) = Sid;
  v14 = RtlLengthSid(Sid);
  v15 = *((_QWORD *)a1 + 47);
  LOWORD(v31) = v14;
  WORD1(v31) = v14;
  v16 = SamIGetUserLogonInformation2(v15, 136, &v31, 0x10000000, 0x2000000, 0, &v25, v35, 0);
  v13 = v16;
  if ( v16 >= 0 )
  {
    if ( (*((_BYTE *)a3 + 168) & 0x20) != 0 && (v17 = 0, *((_DWORD *)a3 + 68)) )
    {
      while ( !RtlEqualSid(*(PSID *)(*((_QWORD *)a3 + 35) + 16LL * v17), OtherOrganizationSid) )
      {
        if ( ++v17 >= *((_DWORD *)a3 + 68) )
          goto LABEL_9;
      }
      v7 = 1;
    }
    else
    {
LABEL_9:
      if ( !*(_QWORD *)(v25 + 584) )
        goto LABEL_35;
    }
    v18 = NlpCreateAuthzContext(a1, a3, v37, a7, &v26);
    v13 = v18;
    if ( v18 < 0 )
    {
      NlPrintRoutine(
        0x800u,
        L"NlpVerifyAllowedToAuthenticate failed to create user AuthZ context: 0x%08X",
        (unsigned int)v18);
      v11 = v26;
      goto LABEL_36;
    }
    v11 = v26;
    if ( a5 )
    {
      v19 = NlpCreateAuthzContext(a1, a5, a6, a7, &v28);
      v13 = v19;
      if ( v19 < 0 )
      {
        NlPrintRoutine(
          0x800u,
          L"NlpVerifyAllowedToAuthenticate failed to create device AuthZ context: 0x%08X",
          (unsigned int)v19);
        v12 = v28;
        goto LABEL_36;
      }
      v12 = v28;
      if ( !(unsigned int)AuthzInitializeCompoundContext(v11, v28, &v29) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0xC0070000;
        else
          v13 = LastError;
        NlPrintRoutine(
          0x800u,
          L"NlpVerifyAllowedToAuthenticate failed to compound user AuthZ context gle:0x%x Status:0x%x",
          (unsigned int)LastError,
          v13);
        goto LABEL_36;
      }
      v21 = (struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **)&v29;
    }
    else
    {
      v21 = &v26;
    }
    pRequest.OptionalArguments = 0;
    LODWORD(v32) = 0;
    *((_QWORD *)&v32 + 1) = &GUID_A_SECURED_FOR_CROSS_ORGANIZATION;
    pRequest.ObjectTypeList = (POBJECT_TYPE_LIST)&v32;
    pRequest.ObjectTypeListLength = 1;
    pReply.ResultListLength = 1;
    pReply.GrantedAccessMask = (PACCESS_MASK)&v36;
    pReply.Error = (PDWORD)&v27;
    pRequest.DesiredAccess = 256;
    pRequest.PrincipalSelfSid = 0;
    if ( v7 )
    {
      if ( !AuthzAccessCheck(0, *v21, &pRequest, 0, *(PSECURITY_DESCRIPTOR *)(v25 + 264), 0, 0, &pReply, 0) )
      {
LABEL_25:
        v22 = GetLastError();
        NlPrintRoutine(0x100u, L"NlpVerifyAllowedToAuthenticate: AuthzAccessCheck failed unexpectedly 0x%lx\n", v22);
        v13 = NetpApiStatusToNtStatus(v22);
        goto LABEL_36;
      }
      if ( *pReply.Error )
      {
        NlPrintRoutine(4u, L"NlpVerifyAllowedToAuthenticate: AuthzAccessCheck failed 0x%lx\n");
LABEL_28:
        v13 = -1073740781;
        goto LABEL_36;
      }
      v13 = 0;
    }
    if ( !*(_QWORD *)(v25 + 584) || !*(_BYTE *)(v25 + 568) )
      goto LABEL_36;
    v23 = *v21;
    pRequest.ObjectTypeList = 0;
    pRequest.ObjectTypeListLength = 0;
    if ( !AuthzAccessCheck(0, v23, &pRequest, 0, *(PSECURITY_DESCRIPTOR *)(v25 + 584), 0, 0, &pReply, 0) )
      goto LABEL_25;
    if ( *pReply.Error )
    {
      NlPrintRoutine(
        4u,
        L"NlpVerifyAllowedToAuthenticate: AuthzAccessCheck failed for A2ATo 0x%lx.  This can be due to the lack of claims "
         "and compound support in NTLM\n");
      goto LABEL_28;
    }
LABEL_35:
    v13 = 0;
    goto LABEL_36;
  }
  NlPrintRoutine(
    0x100u,
    L"NlpVerifyAllowedToAuthenticate: SamIGetUserLogonInformation2 failed 0x%lx\n",
    (unsigned int)v16);
LABEL_36:
  if ( v11 )
    AuthzFreeContext(v11);
  if ( v12 )
    AuthzFreeContext(v11);
LABEL_40:
  if ( v29 )
    AuthzFreeContext(v11);
  if ( v25 )
    SamIFree_UserInternal6Information();
  SamIFreeSidAndAttributesList(v35);
  return v13;
}

```

## disassembly

```asm
0x1800549a4  mov     [rsp-8+arg_8], rbx
0x1800549a9  mov     [rsp-8+arg_18], r9
0x1800549ae  push    rbp
0x1800549af  push    rsi
0x1800549b0  push    rdi
0x1800549b1  push    r12
0x1800549b3  push    r13
0x1800549b5  push    r14
0x1800549b7  push    r15
0x1800549b9  lea     rbp, [rsp-0Fh]
0x1800549be  sub     rsp, 100h
0x1800549c5  xor     r15d, r15d
0x1800549c8  mov     [rsp+130h+var_D0], 5
0x1800549d0  xorps   xmm0, xmm0
0x1800549d3  mov     [rbp+3Fh+Sid], r15
0x1800549d7  xorps   xmm1, xmm1
0x1800549da  mov     [rsp+130h+var_E0], r15
0x1800549df  mov     rsi, r8
0x1800549e2  mov     [rsp+130h+var_D8], r15
0x1800549e7  mov     r14, rcx
0x1800549ea  mov     [rsp+130h+var_C8], r15
0x1800549ef  mov     rcx, [rcx+0B8h]; SourceSid
0x1800549f6  lea     r8, [rbp+3Fh+Sid]
0x1800549fa  xor     eax, eax
0x1800549fc  mov     [rsp+130h+var_C0], r15
0x180054a01  movups  [rbp+3Fh+var_B0], xmm0
0x180054a05  mov     edi, r15d
0x180054a08  mov     r12d, r15d
0x180054a0b  movups  [rbp+3Fh+var_48], xmm1
0x180054a0f  mov     [rbp+3Fh+pRequest.OptionalArguments], rax
0x180054a13  movups  xmmword ptr [rbp+3Fh+pRequest.DesiredAccess], xmm0
0x180054a17  mov     [rbp+3Fh+arg_0], r15d
0x180054a1b  movups  xmmword ptr [rbp+3Fh+pRequest.ObjectTypeList], xmm0
0x180054a1f  movups  [rbp+3Fh+var_A0], xmm0
0x180054a23  movups  xmmword ptr [rbp+3Fh+var_68.ResultListLength], xmm1
0x180054a27  movups  xmmword ptr [rbp+3Fh+var_68.SaclEvaluationResults], xmm1
0x180054a2b  call    NetpDomainIdToSid
0x180054a30  test    eax, eax
0x180054a32  jz      short loc_180054A3E
0x180054a34  mov     ebx, 0C000009Ah
0x180054a39  jmp     loc_180054DC8
0x180054a3e  mov     r13, [rbp+3Fh+Sid]
0x180054a42  mov     rcx, r13; Sid
0x180054a45  mov     qword ptr [rbp+3Fh+var_B0+8], r13
0x180054a49  call    cs:__imp_RtlLengthSid
0x180054a50  nop     dword ptr [rax+rax+00h]
0x180054a55  mov     rcx, [r14+178h]
0x180054a5c  lea     r8, [rbp+3Fh+var_B0]
0x180054a60  mov     [rsp+130h+phAccessCheckResults], r15
0x180054a65  mov     r9d, 10000000h
0x180054a6b  mov     word ptr [rbp+3Fh+var_B0], ax
0x180054a6f  mov     edx, 88h
0x180054a74  mov     word ptr [rbp+3Fh+var_B0+2], ax
0x180054a78  lea     rax, [rbp+3Fh+var_48]
0x180054a7c  mov     [rsp+130h+pReply], rax
0x180054a81  lea     rax, [rsp+130h+var_E0]
0x180054a86  mov     qword ptr [rsp+130h+OptionalSecurityDescriptorCount], rax
0x180054a8b  mov     [rsp+130h+OptionalSecurityDescriptorArray], r15
0x180054a90  mov     dword ptr [rsp+130h+pSecurityDescriptor], 2000000h
0x180054a98  call    cs:__imp_SamIGetUserLogonInformation2
0x180054a9f  nop     dword ptr [rax+rax+00h]
0x180054aa4  mov     ebx, eax
0x180054aa6  test    eax, eax
0x180054aa8  jns     short loc_180054AC3
0x180054aaa  mov     r8d, eax
0x180054aad  lea     rdx, aNlpverifyallow; "NlpVerifyAllowedToAuthenticate: SamIGet"...
0x180054ab4  mov     ecx, 100h; unsigned int
0x180054ab9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054abe  jmp     loc_180054D93
0x180054ac3  test    byte ptr [rsi+0A8h], 20h
0x180054aca  jz      short loc_180054B09
0x180054acc  mov     ebx, r15d
0x180054acf  cmp     [rsi+110h], r15d
0x180054ad6  jbe     short loc_180054B09
0x180054ad8  mov     rcx, [rsi+118h]
0x180054adf  mov     rdx, cs:OtherOrganizationSid; Sid2
0x180054ae6  mov     eax, ebx
0x180054ae8  add     rax, rax
0x180054aeb  mov     rcx, [rcx+rax*8]; Sid1
0x180054aef  call    cs:__imp_RtlEqualSid
0x180054af6  nop     dword ptr [rax+rax+00h]
0x180054afb  test    al, al
0x180054afd  jnz     short loc_180054B5F
0x180054aff  inc     ebx
0x180054b01  cmp     ebx, [rsi+110h]
0x180054b07  jb      short loc_180054AD8
0x180054b09  mov     rax, [rsp+130h+var_E0]
0x180054b0e  cmp     [rax+248h], r15
0x180054b15  jz      loc_180054D90
0x180054b1b  mov     r9b, [rbp+3Fh+arg_30]; unsigned __int8
0x180054b1f  lea     rax, [rsp+130h+var_D8]
0x180054b24  mov     r8, [rbp+3Fh+arg_18]; struct _SAM_CLAIMS_BLOB *
0x180054b28  mov     rdx, rsi; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x180054b2b  mov     rcx, r14; struct _DOMAIN_INFO *
0x180054b2e  mov     [rsp+130h+pSecurityDescriptor], rax; struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **
0x180054b33  call    ?NlpCreateAuthzContext@@YAJPEAU_DOMAIN_INFO@@PEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_SAM_CLAIMS_BLOB@@EPEAPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@@Z; NlpCreateAuthzContext(_DOMAIN_INFO *,_NETLOGON_VALIDATION_SAM_INFO4 *,_SAM_CLAIMS_BLOB *,uchar,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)
0x180054b38  mov     ebx, eax
0x180054b3a  test    eax, eax
0x180054b3c  jns     short loc_180054B67
0x180054b3e  mov     r8d, eax
0x180054b41  lea     rdx, aNlpverifyallow_3; "NlpVerifyAllowedToAuthenticate failed t"...
0x180054b48  mov     ecx, 800h; unsigned int
0x180054b4d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054b52  mov     rdi, [rsp+130h+var_D8]
0x180054b57  xor     r15d, r15d
0x180054b5a  jmp     loc_180054D93
0x180054b5f  mov     r15d, 1
0x180054b65  jmp     short loc_180054B1B
0x180054b67  mov     rdx, [rbp+3Fh+arg_20]; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x180054b6b  mov     rdi, [rsp+130h+var_D8]
0x180054b70  test    rdx, rdx
0x180054b73  jz      loc_180054C17
0x180054b79  mov     r9b, [rbp+3Fh+arg_30]; unsigned __int8
0x180054b7d  lea     rax, [rsp+130h+var_C8]
0x180054b82  mov     r8, [rbp+3Fh+arg_28]; struct _SAM_CLAIMS_BLOB *
0x180054b86  mov     rcx, r14; struct _DOMAIN_INFO *
0x180054b89  mov     [rsp+130h+pSecurityDescriptor], rax; struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **
0x180054b8e  call    ?NlpCreateAuthzContext@@YAJPEAU_DOMAIN_INFO@@PEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_SAM_CLAIMS_BLOB@@EPEAPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@@Z; NlpCreateAuthzContext(_DOMAIN_INFO *,_NETLOGON_VALIDATION_SAM_INFO4 *,_SAM_CLAIMS_BLOB *,uchar,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)
0x180054b93  mov     ebx, eax
0x180054b95  test    eax, eax
0x180054b97  jns     short loc_180054BB4
0x180054b99  mov     r8d, eax
0x180054b9c  lea     rdx, aNlpverifyallow_0; "NlpVerifyAllowedToAuthenticate failed t"...
0x180054ba3  mov     ecx, 800h; unsigned int
0x180054ba8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054bad  mov     r12, [rsp+130h+var_C8]
0x180054bb2  jmp     short loc_180054B57
0x180054bb4  mov     r12, [rsp+130h+var_C8]
0x180054bb9  lea     r8, [rsp+130h+var_C0]
0x180054bbe  mov     rdx, r12
0x180054bc1  mov     rcx, rdi
0x180054bc4  call    cs:__imp_AuthzInitializeCompoundContext
0x180054bcb  nop     dword ptr [rax+rax+00h]
0x180054bd0  test    eax, eax
0x180054bd2  jnz     short loc_180054C10
0x180054bd4  call    cs:__imp_GetLastError
0x180054bdb  nop     dword ptr [rax+rax+00h]
0x180054be0  xor     r15d, r15d
0x180054be3  test    eax, eax
0x180054be5  jg      short loc_180054BEB
0x180054be7  mov     ebx, eax
0x180054be9  jmp     short loc_180054BF4
0x180054beb  movzx   ebx, ax
0x180054bee  or      ebx, 0C0070000h
0x180054bf4  mov     r9d, ebx
0x180054bf7  lea     rdx, aNlpverifyallow_5; "NlpVerifyAllowedToAuthenticate failed t"...
0x180054bfe  mov     r8d, eax
0x180054c01  mov     ecx, 800h; unsigned int
0x180054c06  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054c0b  jmp     loc_180054D93
0x180054c10  lea     r14, [rsp+130h+var_C0]
0x180054c15  jmp     short loc_180054C1C
0x180054c17  lea     r14, [rsp+130h+var_D8]
0x180054c1c  xor     eax, eax
0x180054c1e  mov     [rbp+3Fh+pRequest.OptionalArguments], 0
0x180054c26  mov     dword ptr [rbp+3Fh+var_A0], eax
0x180054c29  lea     rax, ?GUID_A_SECURED_FOR_CROSS_ORGANIZATION@@3U_GUID@@A; _GUID GUID_A_SECURED_FOR_CROSS_ORGANIZATION
0x180054c30  mov     qword ptr [rbp+3Fh+var_A0+8], rax
0x180054c34  lea     rax, [rbp+3Fh+var_A0]
0x180054c38  mov     [rbp+3Fh+pRequest.ObjectTypeList], rax
0x180054c3c  mov     eax, 1
0x180054c41  mov     [rbp+3Fh+pRequest.ObjectTypeListLength], eax
0x180054c44  mov     esi, 100h
0x180054c49  mov     [rbp+3Fh+var_68.ResultListLength], eax
0x180054c4c  lea     rax, [rbp+3Fh+arg_0]
0x180054c50  mov     [rbp+3Fh+var_68.GrantedAccessMask], rax
0x180054c54  lea     rax, [rsp+130h+var_D0]
0x180054c59  mov     [rbp+3Fh+var_68.Error], rax
0x180054c5d  mov     [rbp+3Fh+pRequest.DesiredAccess], esi
0x180054c60  mov     [rbp+3Fh+pRequest.PrincipalSelfSid], 0
0x180054c68  test    r15d, r15d
0x180054c6b  jz      loc_180054D12
0x180054c71  mov     rdx, [r14]; hAuthzClientContext
0x180054c74  lea     rax, [rbp+3Fh+var_68]
0x180054c78  xor     r15d, r15d
0x180054c7b  lea     r8, [rbp+3Fh+pRequest]; pRequest
0x180054c7f  mov     [rsp+130h+phAccessCheckResults], r15; phAccessCheckResults
0x180054c84  xor     r9d, r9d; hAuditEvent
0x180054c87  mov     [rsp+130h+pReply], rax; pReply
0x180054c8c  mov     rax, [rsp+130h+var_E0]
0x180054c91  mov     [rsp+130h+OptionalSecurityDescriptorCount], r15d; OptionalSecurityDescriptorCount
0x180054c96  mov     [rsp+130h+OptionalSecurityDescriptorArray], r15; OptionalSecurityDescriptorArray
0x180054c9b  mov     rcx, [rax+108h]
0x180054ca2  mov     [rsp+130h+pSecurityDescriptor], rcx; pSecurityDescriptor
0x180054ca7  xor     ecx, ecx; Flags
0x180054ca9  call    cs:__imp_AuthzAccessCheck
0x180054cb0  nop     dword ptr [rax+rax+00h]
0x180054cb5  test    eax, eax
0x180054cb7  jnz     short loc_180054CE6
0x180054cb9  call    cs:__imp_GetLastError
0x180054cc0  nop     dword ptr [rax+rax+00h]
0x180054cc5  lea     rdx, aNlpverifyallow_4; "NlpVerifyAllowedToAuthenticate: AuthzAc"...
0x180054ccc  mov     ecx, esi; unsigned int
0x180054cce  mov     r8d, eax
0x180054cd1  mov     ebx, eax
0x180054cd3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054cd8  mov     ecx, ebx
0x180054cda  call    NetpApiStatusToNtStatus
0x180054cdf  mov     ebx, eax
0x180054ce1  jmp     loc_180054D93
0x180054ce6  mov     rax, [rbp+3Fh+var_68.Error]
0x180054cea  mov     r8d, [rax]
0x180054ced  test    r8d, r8d
0x180054cf0  jz      short loc_180054D0D
0x180054cf2  lea     rdx, aNlpverifyallow_2; "NlpVerifyAllowedToAuthenticate: AuthzAc"...
0x180054cf9  mov     ecx, 4; unsigned int
0x180054cfe  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054d03  mov     ebx, 0C0000413h
0x180054d08  jmp     loc_180054D93
0x180054d0d  mov     ebx, r15d
0x180054d10  jmp     short loc_180054D15
0x180054d12  xor     r15d, r15d
0x180054d15  mov     rcx, [rsp+130h+var_E0]
0x180054d1a  cmp     [rcx+248h], r15
0x180054d21  jz      short loc_180054D93
0x180054d23  cmp     [rcx+238h], r15b
0x180054d2a  jz      short loc_180054D93
0x180054d2c  mov     rdx, [r14]; hAuthzClientContext
0x180054d2f  lea     rax, [rbp+3Fh+var_68]
0x180054d33  mov     [rsp+130h+phAccessCheckResults], r15; phAccessCheckResults
0x180054d38  lea     r8, [rbp+3Fh+pRequest]; pRequest
0x180054d3c  mov     [rsp+130h+pReply], rax; pReply
0x180054d41  xor     r9d, r9d; hAuditEvent
0x180054d44  mov     [rbp+3Fh+pRequest.ObjectTypeList], r15
0x180054d48  mov     [rbp+3Fh+pRequest.ObjectTypeListLength], r15d
0x180054d4c  mov     rax, [rcx+248h]
0x180054d53  xor     ecx, ecx; Flags
0x180054d55  mov     [rsp+130h+OptionalSecurityDescriptorCount], r15d; OptionalSecurityDescriptorCount
0x180054d5a  mov     [rsp+130h+OptionalSecurityDescriptorArray], r15; OptionalSecurityDescriptorArray
0x180054d5f  mov     [rsp+130h+pSecurityDescriptor], rax; pSecurityDescriptor
0x180054d64  call    cs:__imp_AuthzAccessCheck
0x180054d6b  nop     dword ptr [rax+rax+00h]
0x180054d70  test    eax, eax
0x180054d72  jz      loc_180054CB9
0x180054d78  mov     rax, [rbp+3Fh+var_68.Error]
0x180054d7c  mov     r8d, [rax]
0x180054d7f  test    r8d, r8d
0x180054d82  jz      short loc_180054D90
0x180054d84  lea     rdx, aNlpverifyallow_1; "NlpVerifyAllowedToAuthenticate: AuthzAc"...
0x180054d8b  jmp     loc_180054CF9
0x180054d90  mov     ebx, r15d
0x180054d93  test    r13, r13
0x180054d96  jz      short loc_180054DA0
0x180054d98  mov     rcx, r13
0x180054d9b  call    NetpMemoryFree
0x180054da0  test    rdi, rdi
0x180054da3  jz      short loc_180054DB4
0x180054da5  mov     rcx, rdi; hAuthzClientContext
0x180054da8  call    cs:__imp_AuthzFreeContext
0x180054daf  nop     dword ptr [rax+rax+00h]
0x180054db4  test    r12, r12
0x180054db7  jz      short loc_180054DC8
0x180054db9  mov     rcx, rdi; hAuthzClientContext
0x180054dbc  call    cs:__imp_AuthzFreeContext
0x180054dc3  nop     dword ptr [rax+rax+00h]
0x180054dc8  cmp     [rsp+130h+var_C0], r15
0x180054dcd  jz      short loc_180054DDE
0x180054dcf  mov     rcx, rdi; hAuthzClientContext
0x180054dd2  call    cs:__imp_AuthzFreeContext
0x180054dd9  nop     dword ptr [rax+rax+00h]
0x180054dde  mov     rcx, [rsp+130h+var_E0]
0x180054de3  test    rcx, rcx
0x180054de6  jz      short loc_180054DF4
0x180054de8  call    cs:__imp_SamIFree_UserInternal6Information
0x180054def  nop     dword ptr [rax+rax+00h]
0x180054df4  lea     rcx, [rbp+3Fh+var_48]
0x180054df8  call    cs:__imp_SamIFreeSidAndAttributesList
0x180054dff  nop     dword ptr [rax+rax+00h]
0x180054e04  mov     eax, ebx
0x180054e06  mov     rbx, [rsp+130h+arg_8]
0x180054e0e  add     rsp, 100h
0x180054e15  pop     r15
0x180054e17  pop     r14
0x180054e19  pop     r13
0x180054e1b  pop     r12
0x180054e1d  pop     rdi
0x180054e1e  pop     rsi
0x180054e1f  pop     rbp
0x180054e20  retn
```
