# NlpAuthzAccessCheck(ulong,_DOMAIN_INFO *,_SafeSecurityDescriptor *)

- ea: `0x1800508a8`
- end: `0x180050b19`
- name: `?NlpAuthzAccessCheck@@YAJKPEAU_DOMAIN_INFO@@PEAU_SafeSecurityDescriptor@@@Z`
- size: `625`
- prototype: `__int64 __fastcall(unsigned int, struct _DOMAIN_INFO *, struct _SafeSecurityDescriptor *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18005f2f8`

## callees

- `0x180007278`
- `0x18000d100`
- `0x1800508a8`
- `0x1800877e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180050af7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180050af7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005091c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005091c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800509c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800509c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a88`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18005090f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18005090f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050926`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050950`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050985`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800509ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050a3c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050ac4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050926`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050950`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050985`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800509ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050a3c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050ac4`
- `AUTHZ!AuthzFreeContext` at `0x180050b06`
- `AUTHZ!AuthzFreeContext` at `0x180050b06`
- `AUTHZ!AuthzAccessCheck` at `0x180050a7e`
- `AUTHZ!AuthzAccessCheck` at `0x180050a7e`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x1800509b6`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x1800509b6`

## string_xrefs

- `0x180050972`: `NlpAuthzAccessCheck: NetpDomainIdToSid took %lld microseconds to run\n`
- `0x1800509c6`: `NlpAuthzAccessCheck: AuthzInitializeContextFromSid failed 0x%lx\n`
- `0x180050a0b`: `NlpAuthzAccessCheck: AuthzInitialzieContextFromSid took %lld microseconds to run\n`
- `0x180050a8e`: `NlpAuthzAccessCheck: AuthzAccessCheck failed unexpectedly 0x%lx\n`
- `0x180050aa6`: `NlpAuthzAccessCheck: AuthzAccessCheck failed for Vulnerable Channel Allow List Check: 0x%lx\n`
- `0x180050ae1`: `NlpAuthzAccessCheck: AuthzAccessCheck took %lld microseconds to run\n`

## pseudocode

```c
__int64 __fastcall NlpAuthzAccessCheck(ULONG a1, PSID *a2, struct _SafeSecurityDescriptor *a3)
{
  unsigned int v5; // ebx
  DWORD LastError; // eax
  unsigned __int16 *v7; // rdx
  DWORD v8; // ebx
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-39h] BYREF
  LARGE_INTEGER Frequency; // [rsp+58h] [rbp-31h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+60h] [rbp-29h] BYREF
  LUID Identifier; // [rsp+68h] [rbp-21h]
  PSID UserSid; // [rsp+70h] [rbp-19h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+78h] [rbp-11h] BYREF
  __int128 DynamicGroupArgs; // [rsp+98h] [rbp+Fh] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+A8h] [rbp+1Fh] BYREF
  int v18; // [rsp+F8h] [rbp+6Fh] BYREF
  int v19; // [rsp+100h] [rbp+77h] BYREF
  int v20; // [rsp+104h] [rbp+7Bh]
  LARGE_INTEGER v21; // [rsp+108h] [rbp+7Fh] BYREF

  v20 = HIDWORD(a3);
  UserSid = 0;
  v19 = 0;
  Identifier = 0;
  PerformanceCount.QuadPart = 0;
  DynamicGroupArgs = 0;
  v21.QuadPart = 0;
  memset(&pReply, 0, sizeof(pReply));
  Frequency.QuadPart = 0;
  hAuthzClientContext = 0;
  memset(&pRequest, 0, sizeof(pRequest));
  v18 = 5;
  QueryPerformanceFrequency(&Frequency);
  AcquireSRWLockExclusive(&stru_1800F0F58);
  QueryPerformanceCounter(&PerformanceCount);
  if ( (unsigned int)NetpDomainIdToSid(a2[23], a1, &UserSid) )
  {
    v5 = -1073741670;
  }
  else
  {
    QueryPerformanceCounter(&v21);
    NlPrintRoutine(
      0x200u,
      L"NlpAuthzAccessCheck: NetpDomainIdToSid took %lld microseconds to run\n",
      1000000 * (v21.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
    QueryPerformanceCounter(&PerformanceCount);
    if ( AuthzInitializeContextFromSid(0, UserSid, NlAuthzRM, 0, Identifier, &DynamicGroupArgs, &hAuthzClientContext) )
    {
      QueryPerformanceCounter(&v21);
      NlPrintRoutine(
        0x200u,
        L"NlpAuthzAccessCheck: AuthzInitialzieContextFromSid took %lld microseconds to run\n",
        1000000 * (v21.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
      pRequest.DesiredAccess = 0x20000;
      pReply.GrantedAccessMask = (PACCESS_MASK)&v19;
      pReply.ResultListLength = 1;
      pReply.Error = (PDWORD)&v18;
      QueryPerformanceCounter(&PerformanceCount);
      if ( AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, NlGlobalVulnerableChannelAllowList, 0, 0, &pReply, 0) )
      {
        if ( *pReply.Error )
        {
          NlPrintRoutine(
            4u,
            L"NlpAuthzAccessCheck: AuthzAccessCheck failed for Vulnerable Channel Allow List Check: 0x%lx\n");
          v5 = -1073741790;
        }
        else
        {
          v5 = 0;
        }
        QueryPerformanceCounter(&v21);
        NlPrintRoutine(
          0x200u,
          L"NlpAuthzAccessCheck: AuthzAccessCheck took %lld microseconds to run\n",
          1000000 * (v21.QuadPart - PerformanceCount.QuadPart) / Frequency.QuadPart);
        goto LABEL_12;
      }
      LastError = GetLastError();
      v7 = L"NlpAuthzAccessCheck: AuthzAccessCheck failed unexpectedly 0x%lx\n";
    }
    else
    {
      LastError = GetLastError();
      v7 = L"NlpAuthzAccessCheck: AuthzInitializeContextFromSid failed 0x%lx\n";
    }
    v8 = LastError;
    NlPrintRoutine(0x100u, v7, LastError);
    v5 = NetpApiStatusToNtStatus(v8);
  }
LABEL_12:
  ReleaseSRWLockExclusive(&stru_1800F0F58);
  if ( hAuthzClientContext )
    AuthzFreeContext(hAuthzClientContext);
  return v5;
}

```

## disassembly

```asm
0x1800508a8  mov     [rsp-8+arg_10], r8
0x1800508ad  push    rbp
0x1800508ae  push    rbx
0x1800508af  push    rdi
0x1800508b0  lea     rbp, [rsp-47h]
0x1800508b5  sub     rsp, 0D0h
0x1800508bc  xor     eax, eax
0x1800508be  mov     [rbp+57h+UserSid], 0
0x1800508c6  xorps   xmm0, xmm0
0x1800508c9  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x1800508cd  xorps   xmm1, xmm1
0x1800508d0  mov     dword ptr [rbp+57h+arg_10], eax
0x1800508d3  mov     ebx, ecx
0x1800508d5  mov     qword ptr [rbp+57h+var_78.LowPart], rax
0x1800508d9  lea     rcx, [rbp+57h+Frequency]; lpFrequency
0x1800508dd  mov     qword ptr [rbp+57h+PerformanceCount], rax
0x1800508e1  movups  [rbp+57h+var_48], xmm0
0x1800508e5  mov     qword ptr [rbp+57h+arg_18], rax
0x1800508e9  mov     rdi, rdx
0x1800508ec  movups  xmmword ptr [rbp+57h+var_68.ResultListLength], xmm1
0x1800508f0  mov     qword ptr [rbp+57h+Frequency], rax
0x1800508f4  movups  xmmword ptr [rbp+57h+var_68.SaclEvaluationResults], xmm1
0x1800508f8  mov     [rbp+57h+hAuthzClientContext], 0
0x180050900  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x180050904  mov     [rbp+57h+arg_8], 5
0x18005090b  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x18005090f  call    cs:__imp_QueryPerformanceFrequency
0x180050915  lea     rcx, stru_1800F0F58; SRWLock
0x18005091c  call    cs:__imp_AcquireSRWLockExclusive
0x180050922  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180050926  call    cs:__imp_QueryPerformanceCounter
0x18005092c  mov     rcx, [rdi+0B8h]; SourceSid
0x180050933  lea     r8, [rbp+57h+UserSid]
0x180050937  mov     edx, ebx
0x180050939  call    NetpDomainIdToSid
0x18005093e  test    eax, eax
0x180050940  jz      short loc_18005094C
0x180050942  mov     ebx, 0C000009Ah
0x180050947  jmp     loc_180050AF0
0x18005094c  lea     rcx, [rbp+57h+arg_18]; lpPerformanceCount
0x180050950  call    cs:__imp_QueryPerformanceCounter
0x180050956  mov     rax, qword ptr [rbp+57h+arg_18]
0x18005095a  mov     edi, 200h
0x18005095f  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x180050963  mov     ecx, edi; unsigned int
0x180050965  imul    rax, 0F4240h
0x18005096c  cqo
0x18005096e  idiv    qword ptr [rbp+57h+Frequency]
0x180050972  lea     rdx, aNlpauthzaccess_0; "NlpAuthzAccessCheck: NetpDomainIdToSid "...
0x180050979  mov     r8, rax
0x18005097c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180050981  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180050985  call    cs:__imp_QueryPerformanceCounter
0x18005098b  mov     r8, cs:?NlAuthzRM@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA; hAuthzResourceManager
0x180050992  lea     rax, [rbp+57h+hAuthzClientContext]
0x180050996  mov     rdx, [rbp+57h+UserSid]; UserSid
0x18005099a  xor     r9d, r9d; pExpirationTime
0x18005099d  mov     [rsp+0E0h+phAuthzClientContext], rax; phAuthzClientContext
0x1800509a2  xor     ecx, ecx; Flags
0x1800509a4  lea     rax, [rbp+57h+var_48]
0x1800509a8  mov     [rsp+0E0h+DynamicGroupArgs], rax; DynamicGroupArgs
0x1800509ad  mov     rax, qword ptr [rbp+57h+var_78.LowPart]
0x1800509b1  mov     qword ptr [rsp+0E0h+Identifier.LowPart], rax; Identifier
0x1800509b6  call    cs:__imp_AuthzInitializeContextFromSid
0x1800509bc  test    eax, eax
0x1800509be  jnz     short loc_1800509EA
0x1800509c0  call    cs:__imp_GetLastError
0x1800509c6  lea     rdx, aNlpauthzaccess_4; "NlpAuthzAccessCheck: AuthzInitializeCon"...
0x1800509cd  mov     r8d, eax
0x1800509d0  mov     ecx, 100h; unsigned int
0x1800509d5  mov     ebx, eax
0x1800509d7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800509dc  mov     ecx, ebx
0x1800509de  call    NetpApiStatusToNtStatus
0x1800509e3  mov     ebx, eax
0x1800509e5  jmp     loc_180050AF0
0x1800509ea  lea     rcx, [rbp+57h+arg_18]; lpPerformanceCount
0x1800509ee  call    cs:__imp_QueryPerformanceCounter
0x1800509f4  mov     rax, qword ptr [rbp+57h+arg_18]
0x1800509f8  mov     ecx, edi; unsigned int
0x1800509fa  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x1800509fe  imul    rax, 0F4240h
0x180050a05  cqo
0x180050a07  idiv    qword ptr [rbp+57h+Frequency]
0x180050a0b  lea     rdx, aNlpauthzaccess_2; "NlpAuthzAccessCheck: AuthzInitialzieCon"...
0x180050a12  mov     r8, rax
0x180050a15  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180050a1a  lea     rax, [rbp+57h+arg_10]
0x180050a1e  mov     [rbp+57h+pRequest.DesiredAccess], 20000h
0x180050a25  mov     [rbp+57h+var_68.GrantedAccessMask], rax
0x180050a29  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180050a2d  lea     rax, [rbp+57h+arg_8]
0x180050a31  mov     [rbp+57h+var_68.ResultListLength], 1
0x180050a38  mov     [rbp+57h+var_68.Error], rax
0x180050a3c  call    cs:__imp_QueryPerformanceCounter
0x180050a42  mov     rdx, [rbp+57h+hAuthzClientContext]; hAuthzClientContext
0x180050a46  lea     rax, [rbp+57h+var_68]
0x180050a4a  mov     [rsp+0E0h+phAccessCheckResults], 0; phAccessCheckResults
0x180050a53  lea     r8, [rbp+57h+pRequest]; pRequest
0x180050a57  mov     [rsp+0E0h+pReply], rax; pReply
0x180050a5c  xor     r9d, r9d; hAuditEvent
0x180050a5f  mov     rax, cs:?NlGlobalVulnerableChannelAllowList@@3U_SafeSecurityDescriptor@@A; _SafeSecurityDescriptor NlGlobalVulnerableChannelAllowList
0x180050a66  xor     ecx, ecx; Flags
0x180050a68  mov     dword ptr [rsp+0E0h+phAuthzClientContext], 0; OptionalSecurityDescriptorCount
0x180050a70  mov     [rsp+0E0h+DynamicGroupArgs], 0; OptionalSecurityDescriptorArray
0x180050a79  mov     qword ptr [rsp+0E0h+Identifier.LowPart], rax; pSecurityDescriptor
0x180050a7e  call    cs:__imp_AuthzAccessCheck
0x180050a84  test    eax, eax
0x180050a86  jnz     short loc_180050A9A
0x180050a88  call    cs:__imp_GetLastError
0x180050a8e  lea     rdx, aNlpauthzaccess_3; "NlpAuthzAccessCheck: AuthzAccessCheck f"...
0x180050a95  jmp     loc_1800509CD
0x180050a9a  mov     rax, [rbp+57h+var_68.Error]
0x180050a9e  mov     r8d, [rax]
0x180050aa1  test    r8d, r8d
0x180050aa4  jz      short loc_180050ABE
0x180050aa6  lea     rdx, aNlpauthzaccess_1; "NlpAuthzAccessCheck: AuthzAccessCheck f"...
0x180050aad  mov     ecx, 4; unsigned int
0x180050ab2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180050ab7  mov     ebx, 0C0000022h
0x180050abc  jmp     short loc_180050AC0
0x180050abe  xor     ebx, ebx
0x180050ac0  lea     rcx, [rbp+57h+arg_18]; lpPerformanceCount
0x180050ac4  call    cs:__imp_QueryPerformanceCounter
0x180050aca  mov     rax, qword ptr [rbp+57h+arg_18]
0x180050ace  mov     ecx, edi; unsigned int
0x180050ad0  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x180050ad4  imul    rax, 0F4240h
0x180050adb  cqo
0x180050add  idiv    qword ptr [rbp+57h+Frequency]
0x180050ae1  lea     rdx, aNlpauthzaccess; "NlpAuthzAccessCheck: AuthzAccessCheck t"...
0x180050ae8  mov     r8, rax
0x180050aeb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180050af0  lea     rcx, stru_1800F0F58; SRWLock
0x180050af7  call    cs:__imp_ReleaseSRWLockExclusive
0x180050afd  mov     rcx, [rbp+57h+hAuthzClientContext]; hAuthzClientContext
0x180050b01  test    rcx, rcx
0x180050b04  jz      short loc_180050B0C
0x180050b06  call    cs:__imp_AuthzFreeContext
0x180050b0c  mov     eax, ebx
0x180050b0e  add     rsp, 0D0h
0x180050b15  pop     rdi
0x180050b16  pop     rbx
0x180050b17  pop     rbp
0x180050b18  retn
```
