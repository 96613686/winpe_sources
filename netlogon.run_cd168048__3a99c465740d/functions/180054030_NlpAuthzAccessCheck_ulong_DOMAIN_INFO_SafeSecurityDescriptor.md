# NlpAuthzAccessCheck(ulong,_DOMAIN_INFO *,_SafeSecurityDescriptor *)

- ea: `0x180054030`
- end: `0x1800542f6`
- name: `?NlpAuthzAccessCheck@@YAJKPEAU_DOMAIN_INFO@@PEAU_SafeSecurityDescriptor@@@Z`
- size: `710`
- prototype: `__int64 __fastcall(unsigned int, struct _DOMAIN_INFO *, struct _SafeSecurityDescriptor *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180063770`

## callees

- `0x180007518`
- `0x18000d7a0`
- `0x180054030`
- `0x18008dc90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800542c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800542c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800540aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800540aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005416c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005424c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005416c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005424c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180054097`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180054097`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800540ba`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800540ea`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180054125`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800541a0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800541f4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005428e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800540ba`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800540ea`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180054125`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800541a0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800541f4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005428e`
- `AUTHZ!AuthzFreeContext` at `0x1800542dc`
- `AUTHZ!AuthzFreeContext` at `0x1800542dc`
- `AUTHZ!AuthzAccessCheck` at `0x18005423c`
- `AUTHZ!AuthzAccessCheck` at `0x18005423c`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x18005415c`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x18005415c`

## string_xrefs

- `0x180054112`: `NlpAuthzAccessCheck: NetpDomainIdToSid took %lld microseconds to run\n`
- `0x180054178`: `NlpAuthzAccessCheck: AuthzInitializeContextFromSid failed 0x%lx\n`
- `0x1800541c3`: `NlpAuthzAccessCheck: AuthzInitialzieContextFromSid took %lld microseconds to run\n`
- `0x180054258`: `NlpAuthzAccessCheck: AuthzAccessCheck failed unexpectedly 0x%lx\n`
- `0x180054270`: `NlpAuthzAccessCheck: AuthzAccessCheck failed for Vulnerable Channel Allow List Check: 0x%lx\n`
- `0x1800542b1`: `NlpAuthzAccessCheck: AuthzAccessCheck took %lld microseconds to run\n`

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
  AcquireSRWLockExclusive(&stru_1800F7F58);
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
  ReleaseSRWLockExclusive(&stru_1800F7F58);
  if ( hAuthzClientContext )
    AuthzFreeContext(hAuthzClientContext);
  return v5;
}

```

## disassembly

```asm
0x180054030  mov     [rsp-8+arg_10], r8
0x180054035  push    rbp
0x180054036  push    rbx
0x180054037  push    rdi
0x180054038  lea     rbp, [rsp-47h]
0x18005403d  sub     rsp, 0D0h
0x180054044  xor     eax, eax
0x180054046  mov     [rbp+57h+UserSid], 0
0x18005404e  xorps   xmm0, xmm0
0x180054051  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x180054055  xorps   xmm1, xmm1
0x180054058  mov     dword ptr [rbp+57h+arg_10], eax
0x18005405b  mov     ebx, ecx
0x18005405d  mov     qword ptr [rbp+57h+var_78.LowPart], rax
0x180054061  lea     rcx, [rbp+57h+Frequency]; lpFrequency
0x180054065  mov     qword ptr [rbp+57h+PerformanceCount], rax
0x180054069  movups  [rbp+57h+var_48], xmm0
0x18005406d  mov     qword ptr [rbp+57h+arg_18], rax
0x180054071  mov     rdi, rdx
0x180054074  movups  xmmword ptr [rbp+57h+var_68.ResultListLength], xmm1
0x180054078  mov     qword ptr [rbp+57h+Frequency], rax
0x18005407c  movups  xmmword ptr [rbp+57h+var_68.SaclEvaluationResults], xmm1
0x180054080  mov     [rbp+57h+hAuthzClientContext], 0
0x180054088  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x18005408c  mov     [rbp+57h+arg_8], 5
0x180054093  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x180054097  call    cs:__imp_QueryPerformanceFrequency
0x18005409e  nop     dword ptr [rax+rax+00h]
0x1800540a3  lea     rcx, stru_1800F7F58; SRWLock
0x1800540aa  call    cs:__imp_AcquireSRWLockExclusive
0x1800540b1  nop     dword ptr [rax+rax+00h]
0x1800540b6  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1800540ba  call    cs:__imp_QueryPerformanceCounter
0x1800540c1  nop     dword ptr [rax+rax+00h]
0x1800540c6  mov     rcx, [rdi+0B8h]; SourceSid
0x1800540cd  lea     r8, [rbp+57h+UserSid]
0x1800540d1  mov     edx, ebx
0x1800540d3  call    NetpDomainIdToSid
0x1800540d8  test    eax, eax
0x1800540da  jz      short loc_1800540E6
0x1800540dc  mov     ebx, 0C000009Ah
0x1800540e1  jmp     loc_1800542C0
0x1800540e6  lea     rcx, [rbp+57h+arg_18]; lpPerformanceCount
0x1800540ea  call    cs:__imp_QueryPerformanceCounter
0x1800540f1  nop     dword ptr [rax+rax+00h]
0x1800540f6  mov     rax, qword ptr [rbp+57h+arg_18]
0x1800540fa  mov     edi, 200h
0x1800540ff  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x180054103  mov     ecx, edi; unsigned int
0x180054105  imul    rax, 0F4240h
0x18005410c  cqo
0x18005410e  idiv    qword ptr [rbp+57h+Frequency]
0x180054112  lea     rdx, aNlpauthzaccess_0; "NlpAuthzAccessCheck: NetpDomainIdToSid "...
0x180054119  mov     r8, rax
0x18005411c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054121  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180054125  call    cs:__imp_QueryPerformanceCounter
0x18005412c  nop     dword ptr [rax+rax+00h]
0x180054131  mov     r8, cs:?NlAuthzRM@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA; hAuthzResourceManager
0x180054138  lea     rax, [rbp+57h+hAuthzClientContext]
0x18005413c  mov     rdx, [rbp+57h+UserSid]; UserSid
0x180054140  xor     r9d, r9d; pExpirationTime
0x180054143  mov     [rsp+0E0h+phAuthzClientContext], rax; phAuthzClientContext
0x180054148  xor     ecx, ecx; Flags
0x18005414a  lea     rax, [rbp+57h+var_48]
0x18005414e  mov     [rsp+0E0h+DynamicGroupArgs], rax; DynamicGroupArgs
0x180054153  mov     rax, qword ptr [rbp+57h+var_78.LowPart]
0x180054157  mov     qword ptr [rsp+0E0h+Identifier.LowPart], rax; Identifier
0x18005415c  call    cs:__imp_AuthzInitializeContextFromSid
0x180054163  nop     dword ptr [rax+rax+00h]
0x180054168  test    eax, eax
0x18005416a  jnz     short loc_18005419C
0x18005416c  call    cs:__imp_GetLastError
0x180054173  nop     dword ptr [rax+rax+00h]
0x180054178  lea     rdx, aNlpauthzaccess_4; "NlpAuthzAccessCheck: AuthzInitializeCon"...
0x18005417f  mov     r8d, eax
0x180054182  mov     ecx, 100h; unsigned int
0x180054187  mov     ebx, eax
0x180054189  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005418e  mov     ecx, ebx
0x180054190  call    NetpApiStatusToNtStatus
0x180054195  mov     ebx, eax
0x180054197  jmp     loc_1800542C0
0x18005419c  lea     rcx, [rbp+57h+arg_18]; lpPerformanceCount
0x1800541a0  call    cs:__imp_QueryPerformanceCounter
0x1800541a7  nop     dword ptr [rax+rax+00h]
0x1800541ac  mov     rax, qword ptr [rbp+57h+arg_18]
0x1800541b0  mov     ecx, edi; unsigned int
0x1800541b2  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x1800541b6  imul    rax, 0F4240h
0x1800541bd  cqo
0x1800541bf  idiv    qword ptr [rbp+57h+Frequency]
0x1800541c3  lea     rdx, aNlpauthzaccess_2; "NlpAuthzAccessCheck: AuthzInitialzieCon"...
0x1800541ca  mov     r8, rax
0x1800541cd  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800541d2  lea     rax, [rbp+57h+arg_10]
0x1800541d6  mov     [rbp+57h+pRequest.DesiredAccess], 20000h
0x1800541dd  mov     [rbp+57h+var_68.GrantedAccessMask], rax
0x1800541e1  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1800541e5  lea     rax, [rbp+57h+arg_8]
0x1800541e9  mov     [rbp+57h+var_68.ResultListLength], 1
0x1800541f0  mov     [rbp+57h+var_68.Error], rax
0x1800541f4  call    cs:__imp_QueryPerformanceCounter
0x1800541fb  nop     dword ptr [rax+rax+00h]
0x180054200  mov     rdx, [rbp+57h+hAuthzClientContext]; hAuthzClientContext
0x180054204  lea     rax, [rbp+57h+var_68]
0x180054208  mov     [rsp+0E0h+phAccessCheckResults], 0; phAccessCheckResults
0x180054211  lea     r8, [rbp+57h+pRequest]; pRequest
0x180054215  mov     [rsp+0E0h+pReply], rax; pReply
0x18005421a  xor     r9d, r9d; hAuditEvent
0x18005421d  mov     rax, cs:?NlGlobalVulnerableChannelAllowList@@3U_SafeSecurityDescriptor@@A; _SafeSecurityDescriptor NlGlobalVulnerableChannelAllowList
0x180054224  xor     ecx, ecx; Flags
0x180054226  mov     dword ptr [rsp+0E0h+phAuthzClientContext], 0; OptionalSecurityDescriptorCount
0x18005422e  mov     [rsp+0E0h+DynamicGroupArgs], 0; OptionalSecurityDescriptorArray
0x180054237  mov     qword ptr [rsp+0E0h+Identifier.LowPart], rax; pSecurityDescriptor
0x18005423c  call    cs:__imp_AuthzAccessCheck
0x180054243  nop     dword ptr [rax+rax+00h]
0x180054248  test    eax, eax
0x18005424a  jnz     short loc_180054264
0x18005424c  call    cs:__imp_GetLastError
0x180054253  nop     dword ptr [rax+rax+00h]
0x180054258  lea     rdx, aNlpauthzaccess_3; "NlpAuthzAccessCheck: AuthzAccessCheck f"...
0x18005425f  jmp     loc_18005417F
0x180054264  mov     rax, [rbp+57h+var_68.Error]
0x180054268  mov     r8d, [rax]
0x18005426b  test    r8d, r8d
0x18005426e  jz      short loc_180054288
0x180054270  lea     rdx, aNlpauthzaccess_1; "NlpAuthzAccessCheck: AuthzAccessCheck f"...
0x180054277  mov     ecx, 4; unsigned int
0x18005427c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054281  mov     ebx, 0C0000022h
0x180054286  jmp     short loc_18005428A
0x180054288  xor     ebx, ebx
0x18005428a  lea     rcx, [rbp+57h+arg_18]; lpPerformanceCount
0x18005428e  call    cs:__imp_QueryPerformanceCounter
0x180054295  nop     dword ptr [rax+rax+00h]
0x18005429a  mov     rax, qword ptr [rbp+57h+arg_18]
0x18005429e  mov     ecx, edi; unsigned int
0x1800542a0  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x1800542a4  imul    rax, 0F4240h
0x1800542ab  cqo
0x1800542ad  idiv    qword ptr [rbp+57h+Frequency]
0x1800542b1  lea     rdx, aNlpauthzaccess; "NlpAuthzAccessCheck: AuthzAccessCheck t"...
0x1800542b8  mov     r8, rax
0x1800542bb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800542c0  lea     rcx, stru_1800F7F58; SRWLock
0x1800542c7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800542ce  nop     dword ptr [rax+rax+00h]
0x1800542d3  mov     rcx, [rbp+57h+hAuthzClientContext]; hAuthzClientContext
0x1800542d7  test    rcx, rcx
0x1800542da  jz      short loc_1800542E8
0x1800542dc  call    cs:__imp_AuthzFreeContext
0x1800542e3  nop     dword ptr [rax+rax+00h]
0x1800542e8  mov     eax, ebx
0x1800542ea  add     rsp, 0D0h
0x1800542f1  pop     rdi
0x1800542f2  pop     rbx
0x1800542f3  pop     rbp
0x1800542f4  retn
```
