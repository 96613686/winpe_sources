# CheckPermissionsAnyClient

- ea: `0x18011cfa4`
- end: `0x18011d6ae`
- name: `CheckPermissionsAnyClient`
- size: `1802`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, __int64, __int64, char, int, PWSTR, __int64, __int64)`
- caller_count: `6`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800c8620`
- `0x1802033b4`
- `0x180205090`
- `0x18023f1c8`
- `0x18034ec74`
- `0x180375de0`

## callees

- `0x1800067d0`
- `0x180017d1c`
- `0x18001e090`
- `0x18001ea60`
- `0x180021aa3`
- `0x180035f7c`
- `0x18011cfa4`
- `0x18011eea0`
- `0x18011fdc0`
- `0x18042addc`
- `0x180453340`
- `0x18047b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18011d044`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18011d044`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18011d44f`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18011d44f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d1d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011d1d1`
- `AUTHZ!AuthzFreeAuditEvent` at `0x18011d683`
- `AUTHZ!AuthzFreeAuditEvent` at `0x18045e4da`
- `AUTHZ!AuthzFreeAuditEvent` at `0x18011d683`
- `AUTHZ!AuthzFreeAuditEvent` at `0x18045e4da`
- `AUTHZ!AuthzInitializeObjectAccessAuditEvent2` at `0x18011d22b`
- `AUTHZ!AuthzInitializeObjectAccessAuditEvent2` at `0x18011d22b`
- `AUTHZ!AuthzOpenObjectAudit` at `0x18011d544`
- `AUTHZ!AuthzOpenObjectAudit` at `0x18011d544`
- `AUTHZ!AuthzAccessCheck` at `0x18011d592`
- `AUTHZ!AuthzAccessCheck` at `0x18011d592`
- `AUTHZ!AuthziModifyAuditEvent2` at `0x18011d1c7`
- `AUTHZ!AuthziModifyAuditEvent2` at `0x18011d1c7`

## string_xrefs

- `0x18011d222`: `Object Access`

## pseudocode

```c
__int64 __fastcall CheckPermissionsAnyClient(
        void *a1,
        __int64 a2,
        __int64 a3,
        DWORD a4,
        struct _OBJECT_TYPE_LIST *a5,
        DWORD a6,
        DWORD *a7,
        DWORD *a8,
        char a9,
        int a10,
        PWSTR a11,
        __int64 a12,
        _QWORD *a13)
{
  DWORD *v14; // rbx
  AUTHZ_AUDIT_EVENT_HANDLE *Value; // r13
  DWORD AuthzContextHandle; // esi
  int v17; // r15d
  DWORD *v18; // rdi
  __int64 v19; // rax
  const wchar_t *v20; // rax
  WCHAR *szAdditionalInfo; // r14
  AUTHZ_AUDIT_EVENT_HANDLE v22; // rdx
  DWORD LastError; // eax
  unsigned __int64 v24; // r14
  __int64 v25; // rcx
  unsigned __int64 v26; // rcx
  void *v27; // rsp
  void *v28; // rsp
  DWORD *v29; // rax
  unsigned __int64 v30; // r14
  __int64 v31; // rcx
  unsigned __int64 v32; // rcx
  void *v33; // rsp
  void *v34; // rsp
  DWORD *v35; // rax
  DWORD *v36; // r8
  AUTHZ_CLIENT_CONTEXT_HANDLE v37; // r14
  __int64 i; // rdx
  BOOL v39; // eax
  _QWORD *v40; // r14
  void *v41; // rax
  WCHAR *szObjectName; // [rsp+20h] [rbp-30h]
  PWSTR szAdditionalInfo2; // [rsp+30h] [rbp-20h]
  DWORD v45; // [rsp+50h] [rbp+0h] BYREF
  AUTHZ_AUDIT_EVENT_HANDLE hAuditEvent; // [rsp+58h] [rbp+8h] BYREF
  DWORD AccessMask; // [rsp+60h] [rbp+10h] BYREF
  int v48; // [rsp+64h] [rbp+14h]
  int v49; // [rsp+68h] [rbp+18h]
  DWORD v50; // [rsp+70h] [rbp+20h]
  DWORD *v51; // [rsp+78h] [rbp+28h]
  DWORD *v52; // [rsp+80h] [rbp+30h]
  DWORD v53; // [rsp+88h] [rbp+38h]
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+90h] [rbp+40h] BYREF
  __int64 v55; // [rsp+98h] [rbp+48h]
  void *v56; // [rsp+A0h] [rbp+50h]
  DWORD *v57; // [rsp+A8h] [rbp+58h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+B0h] [rbp+60h]
  __int64 v59; // [rsp+B8h] [rbp+68h]
  PWSTR v60; // [rsp+C0h] [rbp+70h]
  struct _OBJECT_TYPE_LIST *v61; // [rsp+C8h] [rbp+78h]
  __int64 v62; // [rsp+D0h] [rbp+80h]
  _QWORD *v63; // [rsp+D8h] [rbp+88h]
  __int64 v64; // [rsp+E0h] [rbp+90h]
  void *Src; // [rsp+E8h] [rbp+98h]
  AUTHZ_AUDIT_EVENT_HANDLE *v66; // [rsp+F0h] [rbp+A0h]
  __int64 v67; // [rsp+F8h] [rbp+A8h]
  _AUTHZ_ACCESS_REPLY pReply; // [rsp+100h] [rbp+B0h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+120h] [rbp+D0h] BYREF
  const wchar_t *v70; // [rsp+148h] [rbp+F8h]
  _GENERIC_MAPPING GenericMapping; // [rsp+150h] [rbp+100h] BYREF
  WCHAR v72[40]; // [rsp+160h] [rbp+110h] BYREF
  WCHAR szObjectType[40]; // [rsp+1B0h] [rbp+160h] BYREF
  WCHAR v74[40]; // [rsp+200h] [rbp+1B0h] BYREF

  v53 = a4;
  v62 = a3;
  v55 = a2;
  pSecurityDescriptor = a1;
  v61 = a5;
  v50 = a6;
  v14 = a7;
  v64 = (__int64)a7;
  v57 = a8;
  v60 = a11;
  v59 = a12;
  v63 = a13;
  v67 = (__int64)a13;
  Value = (AUTHZ_AUDIT_EVENT_HANDLE *)TlsGetValue(dwTSindex);
  v66 = Value;
  GenericMapping.GenericRead = 131220;
  GenericMapping.GenericWrite = 131112;
  GenericMapping.GenericExecute = 131076;
  GenericMapping.GenericAll = 983551;
  AccessMask = a4;
  AuthzContextHandle = 0;
  hAuthzClientContext = 0;
  memset(&pRequest, 0, sizeof(pRequest));
  memset(&pReply, 0, sizeof(pReply));
  hAuditEvent = 0;
  v17 = 0;
  v48 = 0;
  v18 = 0;
  Src = 0;
  if ( a13 )
    *v63 = 0;
  v19 = v55;
  if ( *(_DWORD *)(v55 + 4) )
  {
    v56 = (void *)(v55 + 24);
    v19 = v55;
  }
  else
  {
    v56 = 0;
  }
  if ( (a9 & 1) != 0 || !gfAuthzUseAuditing )
  {
    hAuditEvent = 0;
    goto LABEL_40;
  }
  Guid(v74, v19 + 8);
  if ( v62 )
    Guid(szObjectType, v62 + 128);
  else
    szObjectType[0] = 0;
  v20 = L"-";
  if ( a11 )
    v20 = a11;
  szAdditionalInfo = (WCHAR *)v20;
  v60 = (PWSTR)v20;
  v70 = v20;
  if ( v59 )
    Guid(v72, v59);
  else
    v72[0] = 0;
  if ( Value )
  {
    v22 = Value[746];
    hAuditEvent = v22;
    if ( v22 )
    {
      HIDWORD(szAdditionalInfo2) = HIDWORD(szAdditionalInfo);
      szObjectName = szObjectType;
      if ( !(unsigned int)AuthziModifyAuditEvent2(60, v22, 0) )
      {
LABEL_19:
        LastError = GetLastError();
LABEL_74:
        AuthzContextHandle = LastError;
        v45 = LastError;
        goto LABEL_75;
      }
LABEL_23:
      v24 = 4LL * a6;
      v18 = 0;
      v51 = 0;
      if ( v24 && v24 <= g_ulMaxStackAllocSize && v24 + g_ulAdditionalProbeSize + 8 >= v24 )
      {
        if ( (unsigned int)VerifyStackAvailable() )
        {
          v25 = v24 + 23;
          if ( v24 + 23 <= v24 + 8 )
            v25 = 0xFFFFFFFFFFFFFF0LL;
          v26 = v25 & 0xFFFFFFFFFFFFFFF0uLL;
          v27 = alloca(v26);
          v28 = alloca(v26);
          v18 = &v45;
          v51 = &v45;
        }
        if ( !v18 )
          goto LABEL_33;
        *v18 = 1801679955;
        v18 += 2;
        v51 = v18;
      }
      if ( v18 )
      {
LABEL_36:
        Src = v18;
        if ( !v18 )
          RaiseDsaExcept(0xE0010003, 1);
        memset_0(v18, 0, 4LL * a6);
        goto LABEL_40;
      }
LABEL_33:
      if ( v24 + 8 >= v24 )
      {
        v29 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        v18 = v29;
        v51 = v29;
        if ( v29 )
        {
          *v29 = 1885431112;
          v18 = v29 + 2;
          v51 = v29 + 2;
        }
      }
      goto LABEL_36;
    }
  }
  if ( !AuthzInitializeObjectAccessAuditEvent2(
          *(_DWORD *)gfADAM != 0 ? 15 : 12,
          0,
          (PWSTR)L"Object Access",
          szObjectType,
          v74,
          szAdditionalInfo,
          v72,
          &hAuditEvent,
          0) )
    goto LABEL_19;
  if ( Value )
  {
    Value[746] = hAuditEvent;
    goto LABEL_23;
  }
LABEL_40:
  if ( a7 )
  {
    v17 = v48;
    goto LABEL_58;
  }
  v30 = 4LL * a6;
  v52 = 0;
  if ( v30 && v30 <= g_ulMaxStackAllocSize && v30 + g_ulAdditionalProbeSize + 8 >= v30 )
  {
    if ( (unsigned int)VerifyStackAvailable() )
    {
      v31 = v30 + 23;
      if ( v30 + 23 <= v30 + 8 )
        v31 = 0xFFFFFFFFFFFFFF0LL;
      v32 = v31 & 0xFFFFFFFFFFFFFFF0uLL;
      v33 = alloca(v32);
      v34 = alloca(v32);
      v14 = &v45;
      v52 = &v45;
    }
    if ( !v14 )
      goto LABEL_51;
    *v14 = 1801679955;
    v14 += 2;
    v52 = v14;
  }
  if ( !v14 )
  {
LABEL_51:
    if ( v30 + 8 >= v30 )
    {
      v35 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      v14 = v35;
      v52 = v35;
      if ( v35 )
      {
        *v35 = 1885431112;
        v14 = v35 + 2;
        v52 = v35 + 2;
      }
    }
  }
  v64 = (__int64)v14;
  if ( !v14 )
    RaiseDsaExcept(0xE0010003, 1);
  v17 = 1;
  v48 = 1;
LABEL_58:
  MapGenericMask(&AccessMask, &GenericMapping);
  pRequest.DesiredAccess = AccessMask;
  pRequest.ObjectTypeList = v61;
  pRequest.ObjectTypeListLength = a6;
  pRequest.OptionalArguments = 0;
  pRequest.PrincipalSelfSid = v56;
  v36 = v57;
  pReply.Error = v57;
  pReply.GrantedAccessMask = v14;
  pReply.ResultListLength = a6;
  pReply.SaclEvaluationResults = v18;
  if ( Value )
  {
    AuthzContextHandle = GetAuthzContextHandle(Value, &hAuthzClientContext);
    v45 = AuthzContextHandle;
    if ( AuthzContextHandle )
      goto LABEL_75;
    v37 = hAuthzClientContext;
    v36 = v57;
  }
  else
  {
    v37 = 0;
    hAuthzClientContext = 0;
  }
  if ( (a9 & 2) == 0 )
  {
    v39 = AuthzAccessCheck(0, v37, &pRequest, hAuditEvent, pSecurityDescriptor, 0, 0, &pReply, 0);
LABEL_68:
    if ( !v39 )
      goto LABEL_19;
    goto LABEL_71;
  }
  v49 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v49 = i;
    if ( (unsigned int)i >= a6 )
      break;
    v14[i] = AccessMask;
    v36[i] = 0;
  }
  if ( gfAuthzUseAuditing )
  {
    v39 = AuthzOpenObjectAudit(0, v37, &pRequest, hAuditEvent, pSecurityDescriptor, 0, 0, &pReply);
    goto LABEL_68;
  }
LABEL_71:
  if ( *(_DWORD *)gfADAM && v18 )
  {
    LODWORD(szAdditionalInfo2) = a6;
    LODWORD(szObjectName) = v53;
    LastError = GenerateSourceAudits(Value, v37, v55, v62, szObjectName, v61, szAdditionalInfo2, v18, v60, v59, v45);
    goto LABEL_74;
  }
LABEL_75:
  if ( v17 && v14 && *(v14 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( v18 )
  {
    v40 = v63;
    if ( v63 )
    {
      v41 = (void *)THAlloc_((_DWORD)Value, a6, 4, 1, 0, 52561518);
      *v40 = v41;
      memcpy_0(v41, v18, 4LL * a6);
    }
    if ( *(v18 - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  if ( !Value && hAuditEvent )
    AuthzFreeAuditEvent(hAuditEvent);
  return AuthzContextHandle;
}

```

## disassembly

```asm
0x18011cfa4  push    rbp
0x18011cfa6  push    rbx
0x18011cfa7  push    rsi
0x18011cfa8  push    rdi
0x18011cfa9  push    r12
0x18011cfab  push    r13
0x18011cfad  push    r14
0x18011cfaf  push    r15
0x18011cfb1  sub     rsp, 268h
0x18011cfb8  lea     rbp, [rsp+50h]
0x18011cfbd  mov     rax, cs:__security_cookie
0x18011cfc4  xor     rax, rbp
0x18011cfc7  mov     [rbp+250h+var_50], rax
0x18011cfce  mov     edi, r9d
0x18011cfd1  mov     [rbp+250h+var_218], r9d
0x18011cfd5  mov     [rbp+250h+var_1D0], r8
0x18011cfdc  mov     [rbp+250h+var_208], rdx
0x18011cfe0  mov     [rbp+250h+pSecurityDescriptor], rcx
0x18011cfe4  mov     rax, [rbp+250h+arg_20]
0x18011cfeb  mov     [rbp+250h+var_1D8], rax
0x18011cfef  mov     r12d, [rbp+250h+arg_28]
0x18011cff6  mov     [rbp+250h+var_230], r12d
0x18011cffa  mov     rbx, [rbp+250h+arg_30]
0x18011d001  mov     [rbp+250h+var_1C0], rbx
0x18011d008  mov     rax, [rbp+250h+arg_38]
0x18011d00f  mov     [rbp+250h+var_1F8], rax
0x18011d013  mov     r14, [rbp+250h+arg_50]
0x18011d01a  mov     [rbp+250h+var_1E0], r14
0x18011d01e  mov     rax, [rbp+250h+arg_58]
0x18011d025  mov     [rbp+250h+var_1E8], rax
0x18011d029  mov     rax, [rbp+250h+arg_60]
0x18011d030  mov     [rbp+250h+var_1C8], rax
0x18011d037  mov     [rbp+250h+var_1A8], rax
0x18011d03e  mov     ecx, cs:dwTSindex; dwTlsIndex
0x18011d044  call    cs:__imp_TlsGetValue
0x18011d04a  mov     r13, rax
0x18011d04d  mov     [rbp+250h+var_1B0], rax
0x18011d054  mov     [rbp+250h+GenericMapping.GenericRead], 20094h
0x18011d05e  mov     [rbp+250h+GenericMapping.GenericWrite], 20028h
0x18011d068  mov     [rbp+250h+GenericMapping.GenericExecute], 20004h
0x18011d072  mov     [rbp+250h+GenericMapping.GenericAll], 0F01FFh
0x18011d07c  mov     [rbp+250h+AccessMask], edi
0x18011d07f  xor     esi, esi
0x18011d081  mov     [rbp+250h+hAuthzClientContext], rsi
0x18011d085  xorps   xmm0, xmm0
0x18011d088  xor     eax, eax
0x18011d08a  movups  xmmword ptr [rbp+250h+pRequest.DesiredAccess], xmm0
0x18011d091  movups  xmmword ptr [rbp+250h+pRequest.ObjectTypeList], xmm0
0x18011d098  mov     [rbp+250h+pRequest.OptionalArguments], rax
0x18011d09f  movups  xmmword ptr [rbp+250h+pReply.ResultListLength], xmm0
0x18011d0a6  movups  xmmword ptr [rbp+250h+pReply.SaclEvaluationResults], xmm0
0x18011d0ad  mov     [rbp+250h+hAuditEvent], rax
0x18011d0b1  xor     r15d, r15d
0x18011d0b4  mov     [rbp+250h+var_23C], r15d
0x18011d0b8  xor     edi, edi
0x18011d0ba  mov     [rbp+250h+Src], rdi
0x18011d0c1  mov     rax, [rbp+250h+var_1C8]
0x18011d0c8  test    rax, rax
0x18011d0cb  jz      short loc_18011D0D0
0x18011d0cd  mov     [rax], rsi
0x18011d0d0  mov     rax, [rbp+250h+var_208]
0x18011d0d4  cmp     dword ptr [rax+4], 0
0x18011d0d8  jz      short loc_18011D0E8
0x18011d0da  add     rax, 18h
0x18011d0de  mov     [rbp+250h+var_200], rax
0x18011d0e2  mov     rax, [rbp+250h+var_208]
0x18011d0e6  jmp     short loc_18011D0F0
0x18011d0e8  mov     [rbp+250h+var_200], 0
0x18011d0f0  test    [rbp+250h+arg_40], 1
0x18011d0f7  jnz     loc_18011D34B
0x18011d0fd  cmp     cs:gfAuthzUseAuditing, 0
0x18011d104  jz      loc_18011D34B
0x18011d10a  lea     rdx, [rax+8]
0x18011d10e  lea     rcx, [rbp+250h+var_A0]
0x18011d115  call    Guid
0x18011d11a  mov     rax, [rbp+250h+var_1D0]
0x18011d121  test    rax, rax
0x18011d124  jz      short loc_18011D13B
0x18011d126  lea     rdx, [rax+80h]
0x18011d12d  lea     rcx, [rbp+250h+szObjectType]
0x18011d134  call    Guid
0x18011d139  jmp     short loc_18011D142
0x18011d13b  mov     [rbp+250h+szObjectType], ax
0x18011d142  lea     rax, asc_1804AB17C; "-"
0x18011d149  test    r14, r14
0x18011d14c  cmovnz  rax, r14
0x18011d150  mov     r14, rax
0x18011d153  mov     [rbp+250h+var_1E0], rax
0x18011d157  mov     [rbp+250h+var_158], rax
0x18011d15e  mov     rax, [rbp+250h+var_1E8]
0x18011d162  test    rax, rax
0x18011d165  jz      short loc_18011D178
0x18011d167  mov     rdx, rax
0x18011d16a  lea     rcx, [rbp+250h+var_140]
0x18011d171  call    Guid
0x18011d176  jmp     short loc_18011D17F
0x18011d178  mov     [rbp+250h+var_140], ax
0x18011d17f  test    r13, r13
0x18011d182  jz      short loc_18011D1DC
0x18011d184  mov     rdx, [r13+1750h]
0x18011d18b  mov     [rbp+250h+hAuditEvent], rdx
0x18011d18f  test    rdx, rdx
0x18011d192  jz      short loc_18011D1DC
0x18011d194  lea     rax, [rbp+250h+var_140]
0x18011d19b  mov     [rsp+2A0h+phAuditEvent], rax
0x18011d1a0  mov     [rsp+2A0h+szAdditionalInfo2], r14
0x18011d1a5  lea     rax, [rbp+250h+var_A0]
0x18011d1ac  mov     [rsp+2A0h+szAdditionalInfo], rax
0x18011d1b1  lea     rax, [rbp+250h+szObjectType]
0x18011d1b8  mov     [rsp+2A0h+szObjectName], rax
0x18011d1bd  xor     r9d, r9d
0x18011d1c0  xor     r8d, r8d
0x18011d1c3  lea     ecx, [r9+3Ch]
0x18011d1c7  call    cs:__imp_AuthziModifyAuditEvent2
0x18011d1cd  test    eax, eax
0x18011d1cf  jnz     short loc_18011D249
0x18011d1d1  call    cs:__imp_GetLastError
0x18011d1d7  jmp     loc_18011D5EA
0x18011d1dc  mov     eax, cs:gfADAM
0x18011d1e2  neg     eax
0x18011d1e4  sbb     ecx, ecx
0x18011d1e6  and     ecx, 3
0x18011d1e9  add     ecx, 0Ch; Flags
0x18011d1ec  mov     qword ptr [rsp+2A0h+dwAdditionalParameterCount], 0; dwAdditionalParameterCount
0x18011d1f5  lea     rax, [rbp+250h+hAuditEvent]
0x18011d1f9  mov     [rsp+2A0h+phAuditEvent], rax; phAuditEvent
0x18011d1fe  lea     rax, [rbp+250h+var_140]
0x18011d205  mov     [rsp+2A0h+szAdditionalInfo2], rax; szAdditionalInfo2
0x18011d20a  mov     [rsp+2A0h+szAdditionalInfo], r14; szAdditionalInfo
0x18011d20f  lea     rax, [rbp+250h+var_A0]
0x18011d216  mov     [rsp+2A0h+szObjectName], rax; szObjectName
0x18011d21b  lea     r9, [rbp+250h+szObjectType]; szObjectType
0x18011d222  lea     r8, szOperationType; "Object Access"
0x18011d229  xor     edx, edx; hAuditEventType
0x18011d22b  call    cs:__imp_AuthzInitializeObjectAccessAuditEvent2
0x18011d231  test    eax, eax
0x18011d233  jz      short loc_18011D1D1
0x18011d235  test    r13, r13
0x18011d238  jz      loc_18011D353
0x18011d23e  mov     rax, [rbp+250h+hAuditEvent]
0x18011d242  mov     [r13+1750h], rax
0x18011d249  test    r13, r13
0x18011d24c  jz      loc_18011D353
0x18011d252  lea     r14, ds:0[r12*4]
0x18011d25a  xor     edi, edi
0x18011d25c  mov     [rbp+250h+var_228], rdi
0x18011d260  test    r14, r14
0x18011d263  jz      short loc_18011D2D1
0x18011d265  cmp     r14, cs:g_ulMaxStackAllocSize
0x18011d26c  ja      short loc_18011D2D1
0x18011d26e  mov     rcx, cs:g_ulAdditionalProbeSize
0x18011d275  add     rcx, 8
0x18011d279  add     rcx, r14
0x18011d27c  cmp     rcx, r14
0x18011d27f  jb      short loc_18011D2D1
0x18011d281  call    VerifyStackAvailable
0x18011d286  mov     r15, 0FFFFFFFFFFFFFF0h
0x18011d290  test    eax, eax
0x18011d292  jz      short loc_18011D2BC
0x18011d294  lea     rax, [r14+8]
0x18011d298  lea     rcx, [rax+0Fh]
0x18011d29c  cmp     rcx, rax
0x18011d29f  ja      short loc_18011D2A4
0x18011d2a1  mov     rcx, r15
0x18011d2a4  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18011d2a8  mov     rax, rcx
0x18011d2ab  call    _alloca_probe
0x18011d2b0  sub     rsp, rcx
0x18011d2b3  lea     rdi, [rsp+2A0h+var_250]
0x18011d2b8  mov     [rbp+250h+var_228], rdi
0x18011d2bc  test    rdi, rdi
0x18011d2bf  jz      short loc_18011D2E0
0x18011d2c1  mov     dword ptr [rdi], 6B637453h
0x18011d2c7  add     rdi, 8
0x18011d2cb  mov     [rbp+250h+var_228], rdi
0x18011d2cf  jmp     short loc_18011D2DB
0x18011d2d1  mov     r15, 0FFFFFFFFFFFFFF0h
0x18011d2db  test    rdi, rdi
0x18011d2de  jnz     short loc_18011D30F
0x18011d2e0  lea     rcx, [r14+8]
0x18011d2e4  cmp     rcx, r14
0x18011d2e7  jb      short loc_18011D30F
0x18011d2e9  mov     rax, cs:g_pfnAllocate
0x18011d2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d2f5  mov     rdi, rax
0x18011d2f8  mov     [rbp+250h+var_228], rax
0x18011d2fc  test    rax, rax
0x18011d2ff  jz      short loc_18011D30F
0x18011d301  mov     dword ptr [rax], 70616548h
0x18011d307  add     rdi, 8
0x18011d30b  mov     [rbp+250h+var_228], rdi
0x18011d30f  mov     [rbp+250h+Src], rdi
0x18011d316  test    rdi, rdi
0x18011d319  jnz     short loc_18011D338
0x18011d31b  mov     dword ptr [rsp+2A0h+szObjectName], 1; int
0x18011d323  mov     r9d, 32205F5h
0x18011d329  xor     r8d, r8d
0x18011d32c  xor     edx, edx
0x18011d32e  mov     ecx, 0E0010003h; dwExceptionCode
0x18011d333  call    RaiseDsaExcept
0x18011d338  mov     r8, r12
0x18011d33b  shl     r8, 2; Size
0x18011d33f  xor     edx, edx; Val
0x18011d341  mov     rcx, rdi; void *
0x18011d344  call    memset_0
0x18011d349  jmp     short loc_18011D35D
0x18011d34b  mov     [rbp+250h+hAuditEvent], 0
0x18011d353  mov     r15, 0FFFFFFFFFFFFFF0h
0x18011d35d  test    rbx, rbx
0x18011d360  jnz     loc_18011D440
0x18011d366  lea     r14, ds:0[r12*4]
0x18011d36e  mov     [rbp+250h+var_220], rbx
0x18011d372  test    r14, r14
0x18011d375  jz      short loc_18011D3D7
0x18011d377  cmp     r14, cs:g_ulMaxStackAllocSize
0x18011d37e  ja      short loc_18011D3D7
0x18011d380  mov     rcx, cs:g_ulAdditionalProbeSize
0x18011d387  add     rcx, 8
0x18011d38b  add     rcx, r14
0x18011d38e  cmp     rcx, r14
0x18011d391  jb      short loc_18011D3D7
0x18011d393  call    VerifyStackAvailable
0x18011d398  test    eax, eax
0x18011d39a  jz      short loc_18011D3C4
0x18011d39c  lea     rax, [r14+8]
0x18011d3a0  lea     rcx, [rax+0Fh]
0x18011d3a4  cmp     rcx, rax
0x18011d3a7  ja      short loc_18011D3AC
0x18011d3a9  mov     rcx, r15
0x18011d3ac  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18011d3b0  mov     rax, rcx
0x18011d3b3  call    _alloca_probe
0x18011d3b8  sub     rsp, rcx
0x18011d3bb  lea     rbx, [rsp+2A0h+var_250]
0x18011d3c0  mov     [rbp+250h+var_220], rbx
0x18011d3c4  test    rbx, rbx
0x18011d3c7  jz      short loc_18011D3DC
0x18011d3c9  mov     dword ptr [rbx], 6B637453h
0x18011d3cf  add     rbx, 8
0x18011d3d3  mov     [rbp+250h+var_220], rbx
0x18011d3d7  test    rbx, rbx
0x18011d3da  jnz     short loc_18011D40B
0x18011d3dc  lea     rcx, [r14+8]
0x18011d3e0  cmp     rcx, r14
0x18011d3e3  jb      short loc_18011D40B
0x18011d3e5  mov     rax, cs:g_pfnAllocate
0x18011d3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011d3f1  mov     rbx, rax
0x18011d3f4  mov     [rbp+250h+var_220], rax
0x18011d3f8  test    rax, rax
0x18011d3fb  jz      short loc_18011D40B
0x18011d3fd  mov     dword ptr [rax], 70616548h
0x18011d403  add     rbx, 8
0x18011d407  mov     [rbp+250h+var_220], rbx
0x18011d40b  mov     [rbp+250h+var_1C0], rbx
0x18011d412  test    rbx, rbx
0x18011d415  jnz     short loc_18011D434
0x18011d417  mov     dword ptr [rsp+2A0h+szObjectName], 1; int
0x18011d41f  mov     r9d, 3220601h
0x18011d425  xor     r8d, r8d
0x18011d428  xor     edx, edx
0x18011d42a  mov     ecx, 0E0010003h; dwExceptionCode
0x18011d42f  call    RaiseDsaExcept
0x18011d434  mov     r15d, 1
0x18011d43a  mov     [rbp+250h+var_23C], r15d
0x18011d43e  jmp     short loc_18011D444
0x18011d440  mov     r15d, [rbp+250h+var_23C]
0x18011d444  lea     rdx, [rbp+250h+GenericMapping]; GenericMapping
0x18011d44b  lea     rcx, [rbp+250h+AccessMask]; AccessMask
0x18011d44f  call    cs:__imp_MapGenericMask
0x18011d455  mov     eax, [rbp+250h+AccessMask]
0x18011d458  mov     [rbp+250h+pRequest.DesiredAccess], eax
0x18011d45e  mov     rax, [rbp+250h+var_1D8]
0x18011d462  mov     [rbp+250h+pRequest.ObjectTypeList], rax
0x18011d469  mov     [rbp+250h+pRequest.ObjectTypeListLength], r12d
0x18011d470  mov     [rbp+250h+pRequest.OptionalArguments], 0
0x18011d47b  mov     rax, [rbp+250h+var_200]
0x18011d47f  mov     [rbp+250h+pRequest.PrincipalSelfSid], rax
0x18011d486  mov     r8, [rbp+250h+var_1F8]
0x18011d48a  mov     [rbp+250h+pReply.Error], r8
0x18011d491  mov     [rbp+250h+pReply.GrantedAccessMask], rbx
0x18011d498  mov     [rbp+250h+pReply.ResultListLength], r12d
0x18011d49f  mov     [rbp+250h+pReply.SaclEvaluationResults], rdi
0x18011d4a6  test    r13, r13
0x18011d4a9  jz      short loc_18011D4CE
0x18011d4ab  lea     rdx, [rbp+250h+hAuthzClientContext]
0x18011d4af  mov     rcx, r13
0x18011d4b2  call    GetAuthzContextHandle
0x18011d4b7  mov     esi, eax
0x18011d4b9  mov     [rbp+250h+var_250], eax
0x18011d4bc  test    eax, eax
0x18011d4be  jnz     loc_18011D5EF
0x18011d4c4  mov     r14, [rbp+250h+hAuthzClientContext]
0x18011d4c8  mov     r8, [rbp+250h+var_1F8]
0x18011d4cc  jmp     short loc_18011D4D5
0x18011d4ce  xor     r14d, r14d
0x18011d4d1  mov     [rbp+250h+hAuthzClientContext], r14
0x18011d4d5  test    [rbp+250h+arg_40], 2
0x18011d4dc  jz      short loc_18011D553
0x18011d4de  mov     [rbp+250h+var_238], 0
  ... truncated ...
```
