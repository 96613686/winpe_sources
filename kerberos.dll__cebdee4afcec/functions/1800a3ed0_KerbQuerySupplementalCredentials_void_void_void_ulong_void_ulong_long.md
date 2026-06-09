# KerbQuerySupplementalCredentials(void * *,void *,void *,ulong,void * *,ulong *,long *)

- ea: `0x1800a3ed0`
- end: `0x1800a45b2`
- name: `?KerbQuerySupplementalCredentials@@YAJPEAPEAXPEAX1K0PEAKPEAJ@Z`
- size: `1762`
- prototype: `__int64 __fastcall(void **, unsigned int *, void *, unsigned int, void **, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800069a0`
- `0x180008e18`
- `0x180009afc`
- `0x18000a630`
- `0x180048a28`
- `0x1800627b0`
- `0x18006517c`
- `0x18007108c`
- `0x18008b70c`
- `0x18008d6c4`
- `0x1800a3ed0`
- `0x1800c4a0c`
- `0x1800c4d58`
- `0x1800c531c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a427b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a459c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a427b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800a459c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a3fe2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a3ff2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a3fe2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a3ff2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a45a7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800a45a7`
- `ntdll!RtlEqualUnicodeString` at `0x1800a4401`
- `ntdll!RtlEqualUnicodeString` at `0x1800a4401`
- `ntdll!RtlInitUnicodeString` at `0x1800a42bb`
- `ntdll!RtlInitUnicodeString` at `0x1800a42d9`
- `ntdll!RtlInitUnicodeString` at `0x1800a43ee`
- `ntdll!RtlInitUnicodeString` at `0x1800a42bb`
- `ntdll!RtlInitUnicodeString` at `0x1800a42d9`
- `ntdll!RtlInitUnicodeString` at `0x1800a43ee`
- `ntdll!NtOpenThreadToken` at `0x1800a41f4`
- `ntdll!NtOpenThreadToken` at `0x1800a41f4`
- `ntdll!RtlEnterCriticalSection` at `0x1800a441d`
- `ntdll!RtlEnterCriticalSection` at `0x1800a441d`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a4447`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a4447`

## string_xrefs

- `0x1800a419b`: `Failed to create dummy logon session %x\n`
- `0x1800a4213`: `NtOpenThreadToken failed %x\n`
- `0x1800a4251`: `Unable to get the client token handle.\n`
- `0x1800a4285`: `Unable to impersonate the client token handle.\n`

## pseudocode

```c
__int64 __fastcall KerbQuerySupplementalCredentials(
        void **a1,
        unsigned int *a2,
        void *a3,
        unsigned int a4,
        void **a5,
        unsigned int *a6,
        int *a7)
{
  struct _KERB_QUERY_SUPPLEMENTAL_CREDS_RESPONSE *v7; // r15
  struct _RTL_CRITICAL_SECTION *v10; // r14
  void **v12; // r13
  unsigned int v13; // edx
  __int64 v14; // rax
  NTSTATUS inited; // edi
  PWSTR Buffer; // rcx
  __int64 MaximumLength; // rax
  PWSTR v18; // r8
  int v20; // eax
  enum _SECURITY_IMPERSONATION_LEVEL v21; // edi
  unsigned __int8 v22; // r12
  void *v23; // r13
  int v24; // eax
  char v25; // r12
  HANDLE *p_LockSemaphore; // rbx
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  unsigned int v30; // edi
  __int64 v31; // rcx
  unsigned int v32; // eax
  HANDLE v33; // rax
  struct _UNICODE_STRING *p_DestinationString; // r9
  int v35; // eax
  unsigned int *v36; // rcx
  struct _UNICODE_STRING *v37; // [rsp+20h] [rbp-E0h]
  struct _UNICODE_STRING *v38; // [rsp+20h] [rbp-E0h]
  struct _UNICODE_STRING *v39; // [rsp+20h] [rbp-E0h]
  struct _KERB_LOGON_SESSION *LogonSession; // [rsp+40h] [rbp-C0h] BYREF
  struct _KERB_QUERY_SUPPLEMENTAL_CREDS_RESPONSE *v41; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE Token; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING String1; // [rsp+60h] [rbp-A0h] BYREF
  struct _KERB_CREDMAN_CRED *v45; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING v47; // [rsp+88h] [rbp-78h] BYREF
  __int128 v48; // [rsp+98h] [rbp-68h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL v49[4]; // [rsp+A8h] [rbp-58h]
  __int128 v50; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-38h]
  __int64 v52; // [rsp+D0h] [rbp-30h] BYREF
  char v53[20]; // [rsp+D8h] [rbp-28h] BYREF
  HANDLE v54; // [rsp+ECh] [rbp-14h]
  struct _KERB_PRIMARY_CREDENTIAL *v55; // [rsp+118h] [rbp+18h]
  unsigned int v56; // [rsp+1A0h] [rbp+A0h] BYREF
  struct _KERB_PRIMARY_CREDENTIAL *v57; // [rsp+1A8h] [rbp+A8h] BYREF

  v7 = 0;
  v41 = 0;
  v10 = 0;
  Token = 0;
  hObject = 0;
  v45 = 0;
  v52 = 0;
  memset_0(v53, 0, 0x88u);
  v12 = a5;
  v57 = 0;
  v51 = 0;
  v56 = 0;
  *a5 = 0;
  DestinationString = 0;
  *a6 = 0;
  v47 = 0;
  String1 = 0;
  v50 = 0;
  KerbTracerT::Log(7, "KerbQuerySupplementalCredentials", 6856, "KerbQuerySupplementalCredentials\n");
  KerbTelemetry::QuerySuppCreds((KerbTelemetry *)a2[10], v13);
  if ( a1 || a4 < 0x30 || *a2 != 18 )
    goto LABEL_8;
  if ( (a2[10] & 8) == 0 )
  {
    v14 = *((_QWORD *)a2 + 3);
    if ( !v14 || *(_DWORD *)(v14 + 4) != 3 )
    {
      KerbTracerT::Log(
        1,
        "KerbQuerySupplementalCredentials",
        6883,
        "PKI credential was not passed, and default credentials were not selected.\n");
LABEL_8:
      inited = -1073741811;
      goto LABEL_9;
    }
  }
  LogonSession = KerbLocateLogonSession((const struct _LUID *)a2 + 4, 0);
  v10 = (struct _RTL_CRITICAL_SECTION *)LogonSession;
  if ( !LogonSession )
  {
    if ( (a2[10] & 8) != 0 )
    {
      KerbTracerT::Log(
        1,
        "KerbQuerySupplementalCredentials",
        6907,
        "KerbQuerySupplementalCredentials called for default creds with an unknown logon session\n");
      inited = -2146893042;
      goto LABEL_9;
    }
    v48 = 0;
    *(_OWORD *)v49 = 0;
    KerbTracerT::Log(1, "KerbQuerySupplementalCredentials", 6917, "Missing logon session \n");
    v20 = ((__int64 (__fastcall *)(__int128 *))LsaFunctions->GetClientInfo)(&v48);
    inited = v20;
    if ( v20 < 0 )
    {
      KerbTracerT::Log(1, "KerbQuerySupplementalCredentials", 6924, "Failed to get client information: 0x%x", v20);
      goto LABEL_9;
    }
    if ( (HIBYTE(v49[0]) & 2) != 0 )
    {
      inited = -1073741790;
      goto LABEL_9;
    }
    v21 = v49[1];
    v22 = BYTE1(v49[0]);
    v23 = (void *)SDWORD2(v48);
    if ( !((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v50) )
    {
      KerbTracerT::Log(
        1,
        "KerbQuerySupplementalCredentials",
        6939,
        "KerbQuerySupplementalCredentials failed to get call info");
      inited = -1073741670;
      goto LABEL_9;
    }
    v24 = KerbCreateDummyLogonSession(WORD4(v50) & 0x2000, (struct _LUID *)a2 + 4, &LogonSession, v21, v22, v23);
    inited = v24;
    if ( v24 < 0 )
    {
      KerbTracerT::Log(1, "KerbQuerySupplementalCredentials", 6955, "Failed to create dummy logon session %x\n", v24);
      v10 = (struct _RTL_CRITICAL_SECTION *)LogonSession;
      goto LABEL_9;
    }
    v10 = (struct _RTL_CRITICAL_SECTION *)LogonSession;
    v12 = a5;
  }
  v25 = 0;
  if ( (a2[10] & 8) == 0 )
  {
    inited = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &hObject);
    if ( (int)(inited + 0x80000000) >= 0 && inited != -1073741700 )
    {
      LODWORD(v37) = inited;
      KerbTracerT::Log(1, "KerbQuerySupplementalCredentials", 6977, "NtOpenThreadToken failed %x\n", v37);
      goto LABEL_9;
    }
    p_LockSemaphore = &v10[1].LockSemaphore;
    inited = ((__int64 (__fastcall *)(HANDLE *, HANDLE *))LsaFunctions->OpenTokenByLogonId)(
               &v10[1].LockSemaphore,
               &Token);
    if ( inited < 0 )
    {
      KerbTracerT::Log(1, "KerbQuerySupplementalCredentials", 6988, "Unable to get the client token handle.\n");
      goto LABEL_9;
    }
    if ( !SetThreadToken(0, Token) )
    {
      KerbTracerT::Log(1, "KerbQuerySupplementalCredentials", 6994, "Unable to impersonate the client token handle.\n");
      inited = -1073741555;
      goto LABEL_9;
    }
    v25 = 1;
    RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(*((_QWORD *)a2 + 3) + 8LL));
    v27 = *((_QWORD *)a2 + 3);
    if ( (a2[10] & 2) != 0 )
    {
      if ( *(_DWORD *)(v27 + 32) < 8u )
      {
        inited = -1073741811;
        goto LABEL_76;
      }
      v31 = *(_QWORD *)(v27 + 40);
      if ( *(_WORD *)(v31 + 24) )
        *(_QWORD *)(v31 + 32) += v31;
      if ( *(_WORD *)(v31 + 8) )
        *(_QWORD *)(v31 + 16) += v31;
      if ( *(_WORD *)(v31 + 40) )
        *(_QWORD *)(v31 + 48) += v31;
      v32 = *(_DWORD *)(v31 + 60);
      if ( v32 )
        *(_QWORD *)(v31 + 64) += v31;
      inited = KerbInitPrimaryCredentialFromPKCreds(
                 (struct _KERB_LOGON_SESSION *)v10,
                 (struct _UNICODE_STRING *)(v31 + 24),
                 (struct _UNICODE_STRING *)(v31 + 8),
                 (struct _UNICODE_STRING *)(v31 + 40),
                 *(unsigned __int8 **)(v31 + 64),
                 v32,
                 &v57);
      if ( inited < 0 )
        goto LABEL_76;
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v27 + 8));
      if ( (a2[10] & 1) != 0 )
      {
        v28 = *((_QWORD *)a2 + 3);
        if ( !*(_QWORD *)(v28 + 40) )
        {
          KerbTracerT::Log(
            1,
            "KerbQuerySupplementalCredentials",
            7025,
            "KerbQuerySupplementalCredentials called with pin set to NULL\n");
          inited = -2146893042;
          goto LABEL_76;
        }
        String1.Buffer = *(PWSTR *)(v28 + 40);
        String1.MaximumLength = *(_WORD *)(v28 + 32);
        String1.Length = String1.MaximumLength;
        inited = KerbDuplicatePassword(&v47, &String1);
        if ( inited < 0 )
        {
          KerbTracerT::Log(1, "KerbQuerySupplementalCredentials", 7037, "Failed to duplicate user pin\n");
          goto LABEL_76;
        }
      }
      v29 = KerbConvertCertCredential(
              (struct _KERB_LOGON_SESSION *)v10,
              *(const unsigned __int16 **)(*((_QWORD *)a2 + 3) + 72LL),
              ((a2[10] & 0x10) << 6) | (16 * ((a2[10] & 1) + 1)),
              (struct _UNICODE_STRING *)((unsigned __int64)&v47 & -(__int64)(v47.Buffer != 0)),
              &DestinationString,
              &v57);
      inited = v29;
      if ( v29 < 0 )
      {
        LODWORD(v38) = v29;
        KerbTracerT::Log(1, "KerbQuerySupplementalCredentials", 7055, "KerbConvertCertCredential failed %x\n", v38);
LABEL_76:
        if ( hObject )
          SetThreadToken(0, hObject);
        else
          RevertToSelf();
        goto LABEL_9;
      }
      RtlInitUnicodeString(&String1, L"*Session");
      v30 = RtlEqualUnicodeString(&String1, &DestinationString, 1u) != 0;
      if ( (a2[10] & 1) == 0 )
      {
        RtlEnterCriticalSection(v10 + 2);
        inited = KerbAddCredmanCredToLogonSession((struct _KERB_LOGON_SESSION *)v10, 0, &v57, v30, &v45);
        RtlLeaveCriticalSection(v10 + 2);
        if ( inited < 0 )
        {
          LODWORD(v39) = inited;
          KerbTracerT::Log(
            1,
            "KerbQuerySupplementalCredentials",
            7090,
            "KerbAddCredmanCredToLogonSession failed %x\n",
            v39);
          goto LABEL_76;
        }
        goto LABEL_69;
      }
    }
    v33 = *p_LockSemaphore;
    v54 = *p_LockSemaphore;
    v55 = v57;
    goto LABEL_70;
  }
LABEL_69:
  v33 = v54;
LABEL_70:
  p_DestinationString = &DestinationString;
  if ( (a2[10] & 8) != 0 )
    p_DestinationString = 0;
  v35 = KerbRetrieveOWF(
          (struct _KERB_LOGON_SESSION *)v10,
          (struct _KERB_CREDENTIAL *)((unsigned __int64)&v52 & -(__int64)(v33 != 0)),
          v45,
          p_DestinationString,
          &v41,
          &v56);
  inited = v35;
  if ( v35 >= 0 )
  {
    v36 = a6;
    *v12 = v41;
    *v36 = v56;
  }
  else
  {
    KerbTracerT::Log(1, "KerbQuerySupplementalCredentials", 7172, "KerbRetrieveOWF failed %x\n", v35);
    v7 = v41;
  }
  if ( v25 )
    goto LABEL_76;
LABEL_9:
  if ( hObject )
    CloseHandle(hObject);
  if ( Token )
    CloseHandle(Token);
  if ( v10 )
    KerbDereferenceLogonSession((struct _KERB_LOGON_SESSION *)v10);
  if ( v7 )
    KerbFree(v7);
  Buffer = v47.Buffer;
  if ( v47.Buffer )
  {
    MaximumLength = v47.MaximumLength;
    v18 = v47.Buffer;
    if ( v47.MaximumLength )
    {
      do
      {
        *(_BYTE *)v18 = 0;
        v18 = (PWSTR)((char *)v18 + 1);
        --MaximumLength;
      }
      while ( MaximumLength );
    }
    KerbFree(Buffer);
  }
  if ( v57 )
    KerbFreePrimaryCredentials(v57, 1u);
  *a7 = inited;
  return 0;
}

```

## disassembly

```asm
0x1800a3ed0  mov     [rsp-8+arg_10], rbx
0x1800a3ed5  push    rbp
0x1800a3ed6  push    rsi
0x1800a3ed7  push    rdi
0x1800a3ed8  push    r12
0x1800a3eda  push    r13
0x1800a3edc  push    r14
0x1800a3ede  push    r15
0x1800a3ee0  lea     rbp, [rsp-60h]
0x1800a3ee5  sub     rsp, 160h
0x1800a3eec  xor     r15d, r15d
0x1800a3eef  mov     rsi, rdx
0x1800a3ef2  mov     rbx, rcx
0x1800a3ef5  mov     [rsp+190h+var_148], r15
0x1800a3efa  xor     r14d, r14d
0x1800a3efd  mov     [rsp+190h+Token], r15
0x1800a3f02  xor     edx, edx; Val
0x1800a3f04  mov     [rsp+190h+hObject], r15
0x1800a3f09  lea     rcx, [rbp+90h+var_B8]; void *
0x1800a3f0d  mov     [rsp+190h+var_120], r14
0x1800a3f12  mov     r8d, 88h; Size
0x1800a3f18  mov     [rbp+90h+var_C0], r14
0x1800a3f1c  mov     edi, r9d
0x1800a3f1f  call    memset_0
0x1800a3f24  mov     r13, [rbp+90h+arg_20]
0x1800a3f2b  lea     r12, aKerbquerysuppl_3; "KerbQuerySupplementalCredentials"
0x1800a3f32  xor     eax, eax
0x1800a3f34  mov     [rbp+90h+arg_8], r14
0x1800a3f3b  xorps   xmm0, xmm0
0x1800a3f3e  mov     [rbp+90h+var_C8], rax
0x1800a3f42  xorps   xmm1, xmm1
0x1800a3f45  mov     [rbp+90h+arg_0], r14d
0x1800a3f4c  mov     [r13+0], rax
0x1800a3f50  lea     r9, aKerbquerysuppl_1; "KerbQuerySupplementalCredentials\n"
0x1800a3f57  mov     rax, [rbp+90h+arg_28]
0x1800a3f5e  lea     ecx, [r15+7]
0x1800a3f62  mov     r8d, 1AC8h
0x1800a3f68  mov     rdx, r12
0x1800a3f6b  movups  xmmword ptr [rsp+190h+DestinationString.Length], xmm0
0x1800a3f70  mov     [rax], r14d
0x1800a3f73  movups  xmmword ptr [rbp+90h+var_108.Length], xmm1
0x1800a3f77  movups  xmmword ptr [rsp+190h+String1.Length], xmm0
0x1800a3f7c  movups  [rbp+90h+var_D8], xmm1
0x1800a3f80  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a3f85  mov     ecx, [rsi+28h]; this
0x1800a3f88  call    ?QuerySuppCreds@KerbTelemetry@@YAXK@Z; KerbTelemetry::QuerySuppCreds(ulong)
0x1800a3f8d  test    rbx, rbx
0x1800a3f90  jnz     short loc_1800A3FD3
0x1800a3f92  cmp     edi, 30h ; '0'
0x1800a3f95  jb      short loc_1800A3FD3
0x1800a3f97  cmp     dword ptr [rsi], 12h
0x1800a3f9a  jnz     short loc_1800A3FD3
0x1800a3f9c  test    byte ptr [rsi+28h], 8
0x1800a3fa0  jnz     loc_1800A4072
0x1800a3fa6  mov     rax, [rsi+18h]
0x1800a3faa  test    rax, rax
0x1800a3fad  jz      short loc_1800A3FB9
0x1800a3faf  cmp     dword ptr [rax+4], 3
0x1800a3fb3  jz      loc_1800A4072
0x1800a3fb9  lea     r9, aPkiCredentialW; "PKI credential was not passed, and defa"...
0x1800a3fc0  mov     r8d, 1AE3h
0x1800a3fc6  mov     rdx, r12
0x1800a3fc9  mov     ecx, 1
0x1800a3fce  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a3fd3  mov     edi, 0C000000Dh
0x1800a3fd8  mov     rcx, [rsp+190h+hObject]; hObject
0x1800a3fdd  test    rcx, rcx
0x1800a3fe0  jz      short loc_1800A3FE8
0x1800a3fe2  call    cs:__imp_CloseHandle
0x1800a3fe8  mov     rcx, [rsp+190h+Token]; hObject
0x1800a3fed  test    rcx, rcx
0x1800a3ff0  jz      short loc_1800A3FF8
0x1800a3ff2  call    cs:__imp_CloseHandle
0x1800a3ff8  test    r14, r14
0x1800a3ffb  jz      short loc_1800A4005
0x1800a3ffd  mov     rcx, r14; struct _KERB_LOGON_SESSION *
0x1800a4000  call    ?KerbDereferenceLogonSession@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbDereferenceLogonSession(_KERB_LOGON_SESSION *)
0x1800a4005  test    r15, r15
0x1800a4008  jz      short loc_1800A4012
0x1800a400a  mov     rcx, r15
0x1800a400d  call    KerbFree
0x1800a4012  mov     rcx, [rbp+90h+var_108.Buffer]
0x1800a4016  test    rcx, rcx
0x1800a4019  jz      short loc_1800A4039
0x1800a401b  movzx   eax, [rbp+90h+var_108.MaximumLength]
0x1800a401f  mov     r8, rcx
0x1800a4022  test    rax, rax
0x1800a4025  jz      short loc_1800A4034
0x1800a4027  mov     byte ptr [r8], 0
0x1800a402b  inc     r8
0x1800a402e  sub     rax, 1
0x1800a4032  jnz     short loc_1800A4027
0x1800a4034  call    KerbFree
0x1800a4039  mov     rcx, [rbp+90h+arg_8]; this
0x1800a4040  test    rcx, rcx
0x1800a4043  jz      short loc_1800A404C
0x1800a4045  mov     dl, 1; unsigned __int8
0x1800a4047  call    ?KerbFreePrimaryCredentials@@YAXPEAU_KERB_PRIMARY_CREDENTIAL@@E@Z; KerbFreePrimaryCredentials(_KERB_PRIMARY_CREDENTIAL *,uchar)
0x1800a404c  mov     rax, [rbp+90h+arg_30]
0x1800a4053  mov     rbx, [rsp+190h+arg_10]
0x1800a405b  mov     [rax], edi
0x1800a405d  xor     eax, eax
0x1800a405f  add     rsp, 160h
0x1800a4066  pop     r15
0x1800a4068  pop     r14
0x1800a406a  pop     r13
0x1800a406c  pop     r12
0x1800a406e  pop     rdi
0x1800a406f  pop     rsi
0x1800a4070  pop     rbp
0x1800a4071  retn
0x1800a4072  xor     edx, edx; unsigned __int8
0x1800a4074  lea     rcx, [rsi+20h]; struct _LUID *
0x1800a4078  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x1800a407d  mov     [rsp+190h+var_150], rax
0x1800a4082  mov     r14, rax
0x1800a4085  test    rax, rax
0x1800a4088  jnz     loc_1800A41D3
0x1800a408e  test    byte ptr [rsi+28h], 8
0x1800a4092  lea     ecx, [rax+1]
0x1800a4095  mov     rdx, r12
0x1800a4098  jz      short loc_1800A40B6
0x1800a409a  lea     r9, aKerbquerysuppl; "KerbQuerySupplementalCredentials called"...
0x1800a40a1  mov     r8d, 1AFBh
0x1800a40a7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a40ac  mov     edi, 8009030Eh
0x1800a40b1  jmp     loc_1800A3FD8
0x1800a40b6  xorps   xmm0, xmm0
0x1800a40b9  lea     r9, aMissingLogonSe; "Missing logon session \n"
0x1800a40c0  mov     r8d, 1B05h
0x1800a40c6  movups  [rbp+90h+var_F8], xmm0
0x1800a40ca  movups  xmmword ptr [rbp+90h+var_E8], xmm0
0x1800a40ce  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a40d3  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800a40da  lea     rcx, [rbp+90h+var_F8]
0x1800a40de  mov     rax, [rax+80h]
0x1800a40e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a40ea  mov     edi, eax
0x1800a40ec  test    eax, eax
0x1800a40ee  jns     short loc_1800A4113
0x1800a40f0  mov     dword ptr [rsp+190h+var_170], eax
0x1800a40f4  lea     r9, aFailedToGetCli_4; "Failed to get client information: 0x%x"
0x1800a40fb  mov     r8d, 1B0Ch
0x1800a4101  mov     rdx, r12
0x1800a4104  mov     ecx, 1
0x1800a4109  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a410e  jmp     loc_1800A3FD8
0x1800a4113  test    byte ptr [rbp+90h+var_E8+3], 2
0x1800a4117  jz      short loc_1800A4123
0x1800a4119  mov     edi, 0C0000022h
0x1800a411e  jmp     loc_1800A3FD8
0x1800a4123  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800a412a  lea     rcx, [rbp+90h+var_D8]
0x1800a412e  mov     edi, [rbp+90h+var_E8+4]
0x1800a4131  mov     r12b, byte ptr [rbp+90h+var_E8+1]
0x1800a4135  movsxd  r13, dword ptr [rbp+90h+var_F8+8]
0x1800a4139  mov     rax, [rax+0C0h]
0x1800a4140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4145  test    al, al
0x1800a4147  jnz     short loc_1800A4171
0x1800a4149  lea     r9, aKerbquerysuppl_0; "KerbQuerySupplementalCredentials failed"...
0x1800a4150  mov     r8d, 1B1Bh
0x1800a4156  lea     rdx, aKerbquerysuppl_3; "KerbQuerySupplementalCredentials"
0x1800a415d  mov     ecx, 1
0x1800a4162  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a4167  mov     edi, 0C000009Ah
0x1800a416c  jmp     loc_1800A3FD8
0x1800a4171  mov     ecx, dword ptr [rbp+90h+var_D8+8]
0x1800a4174  lea     r8, [rsp+190h+var_150]; struct _KERB_LOGON_SESSION **
0x1800a4179  and     ecx, 2000h; int
0x1800a417f  mov     [rsp+190h+var_168], r13; void *
0x1800a4184  mov     r9d, edi; enum _SECURITY_IMPERSONATION_LEVEL
0x1800a4187  mov     byte ptr [rsp+190h+var_170], r12b; unsigned __int8
0x1800a418c  lea     rdx, [rsi+20h]; struct _LUID *
0x1800a4190  call    ?KerbCreateDummyLogonSession@@YAJHPEAU_LUID@@PEAPEAU_KERB_LOGON_SESSION@@W4_SECURITY_IMPERSONATION_LEVEL@@EPEAX@Z; KerbCreateDummyLogonSession(int,_LUID *,_KERB_LOGON_SESSION * *,_SECURITY_IMPERSONATION_LEVEL,uchar,void *)
0x1800a4195  mov     edi, eax
0x1800a4197  test    eax, eax
0x1800a4199  jns     short loc_1800A41C7
0x1800a419b  lea     r9, aFailedToCreate_34; "Failed to create dummy logon session %x"...
0x1800a41a2  mov     dword ptr [rsp+190h+var_170], eax
0x1800a41a6  mov     r8d, 1B2Bh
0x1800a41ac  lea     rdx, aKerbquerysuppl_3; "KerbQuerySupplementalCredentials"
0x1800a41b3  mov     ecx, 1
0x1800a41b8  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a41bd  mov     r14, [rsp+190h+var_150]
0x1800a41c2  jmp     loc_1800A3FD8
0x1800a41c7  mov     r14, [rsp+190h+var_150]
0x1800a41cc  mov     r13, [rbp+90h+arg_20]
0x1800a41d3  xor     r12b, r12b
0x1800a41d6  test    byte ptr [rsi+28h], 8
0x1800a41da  jnz     loc_1800A44F4
0x1800a41e0  lea     r9, [rsp+190h+hObject]; TokenHandle
0x1800a41e5  mov     r8b, 1; OpenAsSelf
0x1800a41e8  mov     edx, 0Ch; DesiredAccess
0x1800a41ed  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800a41f4  call    cs:__imp_NtOpenThreadToken
0x1800a41fa  mov     ecx, 80000000h
0x1800a41ff  mov     edi, eax
0x1800a4201  add     eax, ecx
0x1800a4203  test    ecx, eax
0x1800a4205  jnz     short loc_1800A422C
0x1800a4207  cmp     edi, 0C000007Ch
0x1800a420d  jz      short loc_1800A422C
0x1800a420f  mov     dword ptr [rsp+190h+var_170], edi
0x1800a4213  lea     r9, aNtopenthreadto; "NtOpenThreadToken failed %x\n"
0x1800a421a  mov     r8d, 1B41h
0x1800a4220  lea     rdx, aKerbquerysuppl_3; "KerbQuerySupplementalCredentials"
0x1800a4227  jmp     loc_1800A4104
0x1800a422c  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800a4233  lea     rbx, [r14+40h]
0x1800a4237  lea     rdx, [rsp+190h+Token]
0x1800a423c  mov     rcx, rbx
0x1800a423f  mov     rax, [rax+170h]
0x1800a4246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a424b  mov     edi, eax
0x1800a424d  test    eax, eax
0x1800a424f  jns     short loc_1800A4274
0x1800a4251  lea     r9, aUnableToGetThe; "Unable to get the client token handle."...
0x1800a4258  mov     r8d, 1B4Ch
0x1800a425e  lea     rdx, aKerbquerysuppl_3; "KerbQuerySupplementalCredentials"
0x1800a4265  mov     ecx, 1
0x1800a426a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a426f  jmp     loc_1800A3FD8
0x1800a4274  mov     rdx, [rsp+190h+Token]; Token
0x1800a4279  xor     ecx, ecx; Thread
0x1800a427b  call    cs:__imp_SetThreadToken
0x1800a4281  test    eax, eax
0x1800a4283  jnz     short loc_1800A42AB
0x1800a4285  lea     r9, aUnableToImpers_3; "Unable to impersonate the client token "...
0x1800a428c  mov     r8d, 1B52h
0x1800a4292  lea     rdx, aKerbquerysuppl_3; "KerbQuerySupplementalCredentials"
0x1800a4299  lea     ecx, [rax+1]
0x1800a429c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a42a1  mov     edi, 0C000010Dh
0x1800a42a6  jmp     loc_1800A3FD8
0x1800a42ab  mov     rdx, [rsi+18h]
0x1800a42af  lea     rcx, [rsp+190h+DestinationString]; DestinationString
0x1800a42b4  mov     r12b, 1
0x1800a42b7  mov     rdx, [rdx+8]; SourceString
0x1800a42bb  call    cs:__imp_RtlInitUnicodeString
0x1800a42c1  mov     eax, [rsi+28h]
0x1800a42c4  mov     rcx, [rsi+18h]
0x1800a42c8  test    al, 2
0x1800a42ca  jnz     loc_1800A446B
0x1800a42d0  mov     rdx, [rcx+8]; SourceString
0x1800a42d4  lea     rcx, [rsp+190h+DestinationString]; DestinationString
0x1800a42d9  call    cs:__imp_RtlInitUnicodeString
0x1800a42df  test    [rsi+28h], r12b
0x1800a42e3  jz      short loc_1800A4364
0x1800a42e5  mov     rax, [rsi+18h]
0x1800a42e9  mov     rcx, [rax+28h]
0x1800a42ed  test    rcx, rcx
0x1800a42f0  jnz     short loc_1800A431A
0x1800a42f2  lea     r9, aKerbquerysuppl_2; "KerbQuerySupplementalCredentials called"...
0x1800a42f9  mov     r8d, 1B71h
0x1800a42ff  lea     rdx, aKerbquerysuppl_3; "KerbQuerySupplementalCredentials"
0x1800a4306  mov     ecx, 1
0x1800a430b  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a4310  mov     edi, 8009030Eh
0x1800a4315  jmp     loc_1800A4590
0x1800a431a  mov     [rsp+190h+String1.Buffer], rcx
0x1800a431f  lea     rdx, [rsp+190h+String1]; struct _UNICODE_STRING *
0x1800a4324  movzx   eax, word ptr [rax+20h]
0x1800a4328  lea     rcx, [rbp+90h+var_108]; struct _UNICODE_STRING *
0x1800a432c  mov     [rsp+190h+String1.MaximumLength], ax
0x1800a4331  mov     [rsp+190h+String1.Length], ax
0x1800a4336  call    ?KerbDuplicatePassword@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; KerbDuplicatePassword(_UNICODE_STRING *,_UNICODE_STRING const *)
0x1800a433b  mov     edi, eax
0x1800a433d  test    eax, eax
0x1800a433f  jns     short loc_1800A4364
0x1800a4341  lea     r9, aFailedToDuplic_12; "Failed to duplicate user pin\n"
0x1800a4348  mov     r8d, 1B7Dh
0x1800a434e  lea     rdx, aKerbquerysuppl_3; "KerbQuerySupplementalCredentials"
0x1800a4355  mov     ecx, 1
0x1800a435a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800a435f  jmp     loc_1800A4590
0x1800a4364  mov     rax, [rbp+90h+var_108.Buffer]
0x1800a4368  mov     rcx, r14; struct _KERB_LOGON_SESSION *
0x1800a436b  mov     rdx, [rsi+18h]
0x1800a436f  neg     rax
0x1800a4372  lea     rax, [rbp+90h+var_108]
0x1800a4376  sbb     r9, r9
0x1800a4379  and     r9, rax; struct _UNICODE_STRING *
0x1800a437c  mov     eax, [rsi+28h]
0x1800a437f  mov     rdx, [rdx+48h]; unsigned __int16 *
0x1800a4383  mov     r8d, eax
0x1800a4386  and     r8d, 1
0x1800a438a  and     eax, 10h
0x1800a438d  shl     eax, 6
0x1800a4390  inc     r8d
0x1800a4393  shl     r8d, 4
0x1800a4397  or      r8d, eax; unsigned int
0x1800a439a  lea     rax, [rbp+90h+arg_8]
0x1800a43a1  mov     [rsp+190h+var_168], rax; struct _KERB_PRIMARY_CREDENTIAL **
0x1800a43a6  lea     rax, [rsp+190h+DestinationString]
0x1800a43ab  mov     [rsp+190h+var_170], rax; struct _UNICODE_STRING *
0x1800a43b0  call    ?KerbConvertCertCredential@@YAJPEAU_KERB_LOGON_SESSION@@PEBGKPEAU_UNICODE_STRING@@2PEAPEAU_KERB_PRIMARY_CREDENTIAL@@@Z; KerbConvertCertCredential(_KERB_LOGON_SESSION *,ushort const *,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_KERB_PRIMARY_CREDENTIAL * *)
0x1800a43b5  mov     edi, eax
0x1800a43b7  test    eax, eax
0x1800a43b9  jns     short loc_1800A43E2
  ... truncated ...
```
