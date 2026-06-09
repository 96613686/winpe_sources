# NlpVerifyAllowedToAuthenticate(_DOMAIN_INFO *,ulong,_NETLOGON_VALIDATION_SAM_INFO4 *,_SAM_CLAIMS_BLOB *,_NETLOGON_VALIDATION_SAM_INFO4 *,_SAM_CLAIMS_BLOB *,uchar)

- ea: `0x18005113c`
- end: `0x18005156b`
- name: `?NlpVerifyAllowedToAuthenticate@@YAJPEAU_DOMAIN_INFO@@KPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_SAM_CLAIMS_BLOB@@12E@Z`
- size: `1071`
- prototype: `__int64 __usercall@<rax>(struct _DOMAIN_INFO *@<rcx>, unsigned int@<edx>, struct _NETLOGON_VALIDATION_SAM_INFO4 *@<r8>, struct _SAM_CLAIMS_BLOB *@<r9>, struct _NETLOGON_VALIDATION_SAM_INFO4 *, struct _SAM_CLAIMS_BLOB *, unsigned __int8)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002e730`
- `0x18006c838`

## callees

- `0x180003670`
- `0x180007278`
- `0x18000d100`
- `0x180050d04`
- `0x18005113c`
- `0x1800877e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005142d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005142d`
- `ntdll!RtlEqualSid` at `0x18005127b`
- `ntdll!RtlEqualSid` at `0x18005127b`
- `ntdll!RtlLengthSid` at `0x1800511e1`
- `ntdll!RtlLengthSid` at `0x1800511e1`
- `AUTHZ!AuthzFreeContext` at `0x180051510`
- `AUTHZ!AuthzFreeContext` at `0x18005151e`
- `AUTHZ!AuthzFreeContext` at `0x18005152e`
- `AUTHZ!AuthzFreeContext` at `0x180051510`
- `AUTHZ!AuthzFreeContext` at `0x18005151e`
- `AUTHZ!AuthzFreeContext` at `0x18005152e`
- `AUTHZ!AuthzInitializeCompoundContext` at `0x18005134a`
- `AUTHZ!AuthzInitializeCompoundContext` at `0x18005134a`
- `AUTHZ!AuthzAccessCheck` at `0x180051423`
- `AUTHZ!AuthzAccessCheck` at `0x1800514d2`
- `AUTHZ!AuthzAccessCheck` at `0x180051423`
- `AUTHZ!AuthzAccessCheck` at `0x1800514d2`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18005153e`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18005153e`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x18005122a`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x18005122a`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180051548`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180051548`

## string_xrefs

- `0x1800512c7`: `NlpVerifyAllowedToAuthenticate failed to create user AuthZ context: 0x%08X`
- `0x180051322`: `NlpVerifyAllowedToAuthenticate failed to create device AuthZ context: 0x%08X`
- `0x180051371`: `NlpVerifyAllowedToAuthenticate failed to compound user AuthZ context gle:0x%x Status:0x%x`
- `0x180051433`: `NlpVerifyAllowedToAuthenticate: AuthzAccessCheck failed unexpectedly 0x%lx\n`
- `0x180051460`: `NlpVerifyAllowedToAuthenticate: AuthzAccessCheck failed 0x%lx\n`
- `0x1800514ec`: `NlpVerifyAllowedToAuthenticate: AuthzAccessCheck failed for A2ATo 0x%lx.  This can be due to the lack of claims and compound support in NTLM\n`

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
0x18005113c  mov     [rsp-8+arg_8], rbx
0x180051141  mov     [rsp-8+arg_18], r9
0x180051146  push    rbp
0x180051147  push    rsi
0x180051148  push    rdi
0x180051149  push    r12
0x18005114b  push    r13
0x18005114d  push    r14
0x18005114f  push    r15
0x180051151  lea     rbp, [rsp-0Fh]
0x180051156  sub     rsp, 100h
0x18005115d  xor     r15d, r15d
0x180051160  mov     [rsp+130h+var_D0], 5
0x180051168  xorps   xmm0, xmm0
0x18005116b  mov     [rbp+3Fh+Sid], r15
0x18005116f  xorps   xmm1, xmm1
0x180051172  mov     [rsp+130h+var_E0], r15
0x180051177  mov     rsi, r8
0x18005117a  mov     [rsp+130h+var_D8], r15
0x18005117f  mov     r14, rcx
0x180051182  mov     [rsp+130h+var_C8], r15
0x180051187  mov     rcx, [rcx+0B8h]; SourceSid
0x18005118e  lea     r8, [rbp+3Fh+Sid]
0x180051192  xor     eax, eax
0x180051194  mov     [rsp+130h+var_C0], r15
0x180051199  movups  [rbp+3Fh+var_B0], xmm0
0x18005119d  mov     edi, r15d
0x1800511a0  mov     r12d, r15d
0x1800511a3  movups  [rbp+3Fh+var_48], xmm1
0x1800511a7  mov     [rbp+3Fh+pRequest.OptionalArguments], rax
0x1800511ab  movups  xmmword ptr [rbp+3Fh+pRequest.DesiredAccess], xmm0
0x1800511af  mov     [rbp+3Fh+arg_0], r15d
0x1800511b3  movups  xmmword ptr [rbp+3Fh+pRequest.ObjectTypeList], xmm0
0x1800511b7  movups  [rbp+3Fh+var_A0], xmm0
0x1800511bb  movups  xmmword ptr [rbp+3Fh+var_68.ResultListLength], xmm1
0x1800511bf  movups  xmmword ptr [rbp+3Fh+var_68.SaclEvaluationResults], xmm1
0x1800511c3  call    NetpDomainIdToSid
0x1800511c8  test    eax, eax
0x1800511ca  jz      short loc_1800511D6
0x1800511cc  mov     ebx, 0C000009Ah
0x1800511d1  jmp     loc_180051524
0x1800511d6  mov     r13, [rbp+3Fh+Sid]
0x1800511da  mov     rcx, r13; Sid
0x1800511dd  mov     qword ptr [rbp+3Fh+var_B0+8], r13
0x1800511e1  call    cs:__imp_RtlLengthSid
0x1800511e7  mov     rcx, [r14+178h]
0x1800511ee  lea     r8, [rbp+3Fh+var_B0]
0x1800511f2  mov     [rsp+130h+phAccessCheckResults], r15
0x1800511f7  mov     r9d, 10000000h
0x1800511fd  mov     word ptr [rbp+3Fh+var_B0], ax
0x180051201  mov     edx, 88h
0x180051206  mov     word ptr [rbp+3Fh+var_B0+2], ax
0x18005120a  lea     rax, [rbp+3Fh+var_48]
0x18005120e  mov     [rsp+130h+pReply], rax
0x180051213  lea     rax, [rsp+130h+var_E0]
0x180051218  mov     qword ptr [rsp+130h+OptionalSecurityDescriptorCount], rax
0x18005121d  mov     [rsp+130h+OptionalSecurityDescriptorArray], r15
0x180051222  mov     dword ptr [rsp+130h+pSecurityDescriptor], 2000000h
0x18005122a  call    cs:__imp_SamIGetUserLogonInformation2
0x180051230  mov     ebx, eax
0x180051232  test    eax, eax
0x180051234  jns     short loc_18005124F
0x180051236  mov     r8d, eax
0x180051239  lea     rdx, aNlpverifyallow; "NlpVerifyAllowedToAuthenticate: SamIGet"...
0x180051240  mov     ecx, 100h; unsigned int
0x180051245  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005124a  jmp     loc_1800514FB
0x18005124f  test    byte ptr [rsi+0A8h], 20h
0x180051256  jz      short loc_18005128F
0x180051258  mov     ebx, r15d
0x18005125b  cmp     [rsi+110h], r15d
0x180051262  jbe     short loc_18005128F
0x180051264  mov     rcx, [rsi+118h]
0x18005126b  mov     rdx, cs:OtherOrganizationSid; Sid2
0x180051272  mov     eax, ebx
0x180051274  add     rax, rax
0x180051277  mov     rcx, [rcx+rax*8]; Sid1
0x18005127b  call    cs:__imp_RtlEqualSid
0x180051281  test    al, al
0x180051283  jnz     short loc_1800512E5
0x180051285  inc     ebx
0x180051287  cmp     ebx, [rsi+110h]
0x18005128d  jb      short loc_180051264
0x18005128f  mov     rax, [rsp+130h+var_E0]
0x180051294  cmp     [rax+248h], r15
0x18005129b  jz      loc_1800514F8
0x1800512a1  mov     r9b, [rbp+3Fh+arg_30]; unsigned __int8
0x1800512a5  lea     rax, [rsp+130h+var_D8]
0x1800512aa  mov     r8, [rbp+3Fh+arg_18]; struct _SAM_CLAIMS_BLOB *
0x1800512ae  mov     rdx, rsi; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x1800512b1  mov     rcx, r14; struct _DOMAIN_INFO *
0x1800512b4  mov     [rsp+130h+pSecurityDescriptor], rax; struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **
0x1800512b9  call    ?NlpCreateAuthzContext@@YAJPEAU_DOMAIN_INFO@@PEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_SAM_CLAIMS_BLOB@@EPEAPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@@Z; NlpCreateAuthzContext(_DOMAIN_INFO *,_NETLOGON_VALIDATION_SAM_INFO4 *,_SAM_CLAIMS_BLOB *,uchar,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)
0x1800512be  mov     ebx, eax
0x1800512c0  test    eax, eax
0x1800512c2  jns     short loc_1800512ED
0x1800512c4  mov     r8d, eax
0x1800512c7  lea     rdx, aNlpverifyallow_3; "NlpVerifyAllowedToAuthenticate failed t"...
0x1800512ce  mov     ecx, 800h; unsigned int
0x1800512d3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800512d8  mov     rdi, [rsp+130h+var_D8]
0x1800512dd  xor     r15d, r15d
0x1800512e0  jmp     loc_1800514FB
0x1800512e5  mov     r15d, 1
0x1800512eb  jmp     short loc_1800512A1
0x1800512ed  mov     rdx, [rbp+3Fh+arg_20]; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x1800512f1  mov     rdi, [rsp+130h+var_D8]
0x1800512f6  test    rdx, rdx
0x1800512f9  jz      loc_180051391
0x1800512ff  mov     r9b, [rbp+3Fh+arg_30]; unsigned __int8
0x180051303  lea     rax, [rsp+130h+var_C8]
0x180051308  mov     r8, [rbp+3Fh+arg_28]; struct _SAM_CLAIMS_BLOB *
0x18005130c  mov     rcx, r14; struct _DOMAIN_INFO *
0x18005130f  mov     [rsp+130h+pSecurityDescriptor], rax; struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **
0x180051314  call    ?NlpCreateAuthzContext@@YAJPEAU_DOMAIN_INFO@@PEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_SAM_CLAIMS_BLOB@@EPEAPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@@Z; NlpCreateAuthzContext(_DOMAIN_INFO *,_NETLOGON_VALIDATION_SAM_INFO4 *,_SAM_CLAIMS_BLOB *,uchar,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *)
0x180051319  mov     ebx, eax
0x18005131b  test    eax, eax
0x18005131d  jns     short loc_18005133A
0x18005131f  mov     r8d, eax
0x180051322  lea     rdx, aNlpverifyallow_0; "NlpVerifyAllowedToAuthenticate failed t"...
0x180051329  mov     ecx, 800h; unsigned int
0x18005132e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180051333  mov     r12, [rsp+130h+var_C8]
0x180051338  jmp     short loc_1800512DD
0x18005133a  mov     r12, [rsp+130h+var_C8]
0x18005133f  lea     r8, [rsp+130h+var_C0]
0x180051344  mov     rdx, r12
0x180051347  mov     rcx, rdi
0x18005134a  call    cs:__imp_AuthzInitializeCompoundContext
0x180051350  test    eax, eax
0x180051352  jnz     short loc_18005138A
0x180051354  call    cs:__imp_GetLastError
0x18005135a  xor     r15d, r15d
0x18005135d  test    eax, eax
0x18005135f  jg      short loc_180051365
0x180051361  mov     ebx, eax
0x180051363  jmp     short loc_18005136E
0x180051365  movzx   ebx, ax
0x180051368  or      ebx, 0C0070000h
0x18005136e  mov     r9d, ebx
0x180051371  lea     rdx, aNlpverifyallow_5; "NlpVerifyAllowedToAuthenticate failed t"...
0x180051378  mov     r8d, eax
0x18005137b  mov     ecx, 800h; unsigned int
0x180051380  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180051385  jmp     loc_1800514FB
0x18005138a  lea     r14, [rsp+130h+var_C0]
0x18005138f  jmp     short loc_180051396
0x180051391  lea     r14, [rsp+130h+var_D8]
0x180051396  xor     eax, eax
0x180051398  mov     [rbp+3Fh+pRequest.OptionalArguments], 0
0x1800513a0  mov     dword ptr [rbp+3Fh+var_A0], eax
0x1800513a3  lea     rax, ?GUID_A_SECURED_FOR_CROSS_ORGANIZATION@@3U_GUID@@A; _GUID GUID_A_SECURED_FOR_CROSS_ORGANIZATION
0x1800513aa  mov     qword ptr [rbp+3Fh+var_A0+8], rax
0x1800513ae  lea     rax, [rbp+3Fh+var_A0]
0x1800513b2  mov     [rbp+3Fh+pRequest.ObjectTypeList], rax
0x1800513b6  mov     eax, 1
0x1800513bb  mov     [rbp+3Fh+pRequest.ObjectTypeListLength], eax
0x1800513be  mov     esi, 100h
0x1800513c3  mov     [rbp+3Fh+var_68.ResultListLength], eax
0x1800513c6  lea     rax, [rbp+3Fh+arg_0]
0x1800513ca  mov     [rbp+3Fh+var_68.GrantedAccessMask], rax
0x1800513ce  lea     rax, [rsp+130h+var_D0]
0x1800513d3  mov     [rbp+3Fh+var_68.Error], rax
0x1800513d7  mov     [rbp+3Fh+pRequest.DesiredAccess], esi
0x1800513da  mov     [rbp+3Fh+pRequest.PrincipalSelfSid], 0
0x1800513e2  test    r15d, r15d
0x1800513e5  jz      loc_180051480
0x1800513eb  mov     rdx, [r14]; hAuthzClientContext
0x1800513ee  lea     rax, [rbp+3Fh+var_68]
0x1800513f2  xor     r15d, r15d
0x1800513f5  lea     r8, [rbp+3Fh+pRequest]; pRequest
0x1800513f9  mov     [rsp+130h+phAccessCheckResults], r15; phAccessCheckResults
0x1800513fe  xor     r9d, r9d; hAuditEvent
0x180051401  mov     [rsp+130h+pReply], rax; pReply
0x180051406  mov     rax, [rsp+130h+var_E0]
0x18005140b  mov     [rsp+130h+OptionalSecurityDescriptorCount], r15d; OptionalSecurityDescriptorCount
0x180051410  mov     [rsp+130h+OptionalSecurityDescriptorArray], r15; OptionalSecurityDescriptorArray
0x180051415  mov     rcx, [rax+108h]
0x18005141c  mov     [rsp+130h+pSecurityDescriptor], rcx; pSecurityDescriptor
0x180051421  xor     ecx, ecx; Flags
0x180051423  call    cs:__imp_AuthzAccessCheck
0x180051429  test    eax, eax
0x18005142b  jnz     short loc_180051454
0x18005142d  call    cs:__imp_GetLastError
0x180051433  lea     rdx, aNlpverifyallow_4; "NlpVerifyAllowedToAuthenticate: AuthzAc"...
0x18005143a  mov     ecx, esi; unsigned int
0x18005143c  mov     r8d, eax
0x18005143f  mov     ebx, eax
0x180051441  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180051446  mov     ecx, ebx
0x180051448  call    NetpApiStatusToNtStatus
0x18005144d  mov     ebx, eax
0x18005144f  jmp     loc_1800514FB
0x180051454  mov     rax, [rbp+3Fh+var_68.Error]
0x180051458  mov     r8d, [rax]
0x18005145b  test    r8d, r8d
0x18005145e  jz      short loc_18005147B
0x180051460  lea     rdx, aNlpverifyallow_2; "NlpVerifyAllowedToAuthenticate: AuthzAc"...
0x180051467  mov     ecx, 4; unsigned int
0x18005146c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180051471  mov     ebx, 0C0000413h
0x180051476  jmp     loc_1800514FB
0x18005147b  mov     ebx, r15d
0x18005147e  jmp     short loc_180051483
0x180051480  xor     r15d, r15d
0x180051483  mov     rcx, [rsp+130h+var_E0]
0x180051488  cmp     [rcx+248h], r15
0x18005148f  jz      short loc_1800514FB
0x180051491  cmp     [rcx+238h], r15b
0x180051498  jz      short loc_1800514FB
0x18005149a  mov     rdx, [r14]; hAuthzClientContext
0x18005149d  lea     rax, [rbp+3Fh+var_68]
0x1800514a1  mov     [rsp+130h+phAccessCheckResults], r15; phAccessCheckResults
0x1800514a6  lea     r8, [rbp+3Fh+pRequest]; pRequest
0x1800514aa  mov     [rsp+130h+pReply], rax; pReply
0x1800514af  xor     r9d, r9d; hAuditEvent
0x1800514b2  mov     [rbp+3Fh+pRequest.ObjectTypeList], r15
0x1800514b6  mov     [rbp+3Fh+pRequest.ObjectTypeListLength], r15d
0x1800514ba  mov     rax, [rcx+248h]
0x1800514c1  xor     ecx, ecx; Flags
0x1800514c3  mov     [rsp+130h+OptionalSecurityDescriptorCount], r15d; OptionalSecurityDescriptorCount
0x1800514c8  mov     [rsp+130h+OptionalSecurityDescriptorArray], r15; OptionalSecurityDescriptorArray
0x1800514cd  mov     [rsp+130h+pSecurityDescriptor], rax; pSecurityDescriptor
0x1800514d2  call    cs:__imp_AuthzAccessCheck
0x1800514d8  test    eax, eax
0x1800514da  jz      loc_18005142D
0x1800514e0  mov     rax, [rbp+3Fh+var_68.Error]
0x1800514e4  mov     r8d, [rax]
0x1800514e7  test    r8d, r8d
0x1800514ea  jz      short loc_1800514F8
0x1800514ec  lea     rdx, aNlpverifyallow_1; "NlpVerifyAllowedToAuthenticate: AuthzAc"...
0x1800514f3  jmp     loc_180051467
0x1800514f8  mov     ebx, r15d
0x1800514fb  test    r13, r13
0x1800514fe  jz      short loc_180051508
0x180051500  mov     rcx, r13
0x180051503  call    NetpMemoryFree
0x180051508  test    rdi, rdi
0x18005150b  jz      short loc_180051516
0x18005150d  mov     rcx, rdi; hAuthzClientContext
0x180051510  call    cs:__imp_AuthzFreeContext
0x180051516  test    r12, r12
0x180051519  jz      short loc_180051524
0x18005151b  mov     rcx, rdi; hAuthzClientContext
0x18005151e  call    cs:__imp_AuthzFreeContext
0x180051524  cmp     [rsp+130h+var_C0], r15
0x180051529  jz      short loc_180051534
0x18005152b  mov     rcx, rdi; hAuthzClientContext
0x18005152e  call    cs:__imp_AuthzFreeContext
0x180051534  mov     rcx, [rsp+130h+var_E0]
0x180051539  test    rcx, rcx
0x18005153c  jz      short loc_180051544
0x18005153e  call    cs:__imp_SamIFree_UserInternal6Information
0x180051544  lea     rcx, [rbp+3Fh+var_48]
0x180051548  call    cs:__imp_SamIFreeSidAndAttributesList
0x18005154e  mov     eax, ebx
0x180051550  mov     rbx, [rsp+130h+arg_8]
0x180051558  add     rsp, 100h
0x18005155f  pop     r15
0x180051561  pop     r14
0x180051563  pop     r13
0x180051565  pop     r12
0x180051567  pop     rdi
0x180051568  pop     rsi
0x180051569  pop     rbp
0x18005156a  retn
```
