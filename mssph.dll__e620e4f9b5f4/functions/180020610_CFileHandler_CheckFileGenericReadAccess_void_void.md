# CFileHandler::CheckFileGenericReadAccess(void *,void *)

- ea: `0x180020610`
- end: `0x1800207cf`
- name: `?CheckFileGenericReadAccess@CFileHandler@@QEAAJPEAX0@Z`
- size: `447`
- prototype: `__int64 __fastcall(CFileHandler *this, void *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800219a0`

## callees

- `0x180005eb0`
- `0x180020610`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002063a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002063a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002079b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800207ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002079b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800207ac`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800206ce`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800206ce`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180020657`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180020657`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800206e3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800206e3`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180020643`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180020643`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x1800206a0`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x1800206a0`
- `AUTHZ!AuthzFreeContext` at `0x18002078e`
- `AUTHZ!AuthzFreeContext` at `0x18002078e`
- `AUTHZ!AuthzAccessCheck` at `0x180020760`
- `AUTHZ!AuthzAccessCheck` at `0x180020760`

## pseudocode

```c
__int64 __fastcall CFileHandler::CheckFileGenericReadAccess(CFileHandler *this, void *a2, void *a3)
{
  AUTHZ_RESOURCE_MANAGER_HANDLE v6; // r8
  int v7; // eax
  unsigned int Error; // ebx
  int v10; // [rsp+50h] [rbp-19h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+58h] [rbp-11h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+60h] [rbp-9h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+80h] [rbp+17h] BYREF
  LUID v14; // [rsp+E8h] [rbp+7Fh] BYREF

  EnterCriticalSection(&CFileHandler::s_mutex);
  if ( IsValidSecurityDescriptor(a3) && IsValidSid(a2) )
  {
    v6 = (AUTHZ_RESOURCE_MANAGER_HANDLE)*((_QWORD *)this + 18);
    v14 = (LUID)0xBEEF0000DEADLL;
    hAuthzClientContext = 0;
    if ( AuthzInitializeContextFromSid(0, a2, v6, 0, (LUID)0xBEEF0000DEADLL, 0, &hAuthzClientContext)
      || (v7 = ResultFromLastError(), Error = v7, v7 >= 0) )
    {
      pReply.GrantedAccessMask = (PACCESS_MASK)&v14;
      *(_QWORD *)&pRequest.DesiredAccess = 0x2000000;
      pReply.Error = (PDWORD)&v10;
      memset(&pRequest.PrincipalSelfSid, 0, 32);
      v10 = 0;
      v14.LowPart = 0;
      *(_QWORD *)&pReply.ResultListLength = 1;
      pReply.SaclEvaluationResults = 0;
      if ( AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, a3, 0, 0, &pReply, 0) )
        Error = (v14.LowPart & 0x120089) != 1179785;
      else
        Error = ResultFromLastError();
    }
    else if ( v7 == -805306145 )
    {
      v14 = 0;
      if ( GetSecurityDescriptorOwner(a3, (PSID *)&v14, 0) )
        Error = !EqualSid(a2, *(PSID *)&v14) ? 0x80070005 : 0;
    }
    if ( hAuthzClientContext )
      AuthzFreeContext(hAuthzClientContext);
    LeaveCriticalSection(&CFileHandler::s_mutex);
    return Error;
  }
  else
  {
    LeaveCriticalSection(&CFileHandler::s_mutex);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180020610  mov     [rsp-8+arg_0], rbx
0x180020615  mov     [rsp-8+arg_8], rsi
0x18002061a  push    rbp
0x18002061b  push    rdi
0x18002061c  push    r14
0x18002061e  lea     rbp, [rsp-47h]
0x180020623  sub     rsp, 0B0h
0x18002062a  mov     rbx, rcx
0x18002062d  mov     rsi, r8
0x180020630  lea     rcx, ?s_mutex@CFileHandler@@0VCMutexSem@@A; lpCriticalSection
0x180020637  mov     rdi, rdx
0x18002063a  call    cs:__imp_EnterCriticalSection
0x180020640  mov     rcx, rsi; pSecurityDescriptor
0x180020643  call    cs:__imp_IsValidSecurityDescriptor
0x180020649  xor     r14d, r14d
0x18002064c  test    eax, eax
0x18002064e  jz      loc_1800207A5
0x180020654  mov     rcx, rdi; pSid
0x180020657  call    cs:__imp_IsValidSid
0x18002065d  test    eax, eax
0x18002065f  jz      loc_1800207A5
0x180020665  mov     r8, [rbx+90h]; hAuthzResourceManager
0x18002066c  lea     rax, [rbp+57h+hAuthzClientContext]
0x180020670  mov     [rsp+0C0h+phAuthzClientContext], rax; phAuthzClientContext
0x180020675  xor     r9d, r9d; pExpirationTime
0x180020678  mov     [rbp+57h+arg_18.LowPart], 0DEADh
0x18002067f  mov     rdx, rdi; UserSid
0x180020682  mov     [rbp+57h+arg_18.HighPart], 0BEEFh
0x18002068c  xor     ecx, ecx; Flags
0x18002068e  mov     rax, qword ptr [rbp+57h+arg_18.LowPart]
0x180020692  mov     [rsp+0C0h+DynamicGroupArgs], r14; DynamicGroupArgs
0x180020697  mov     qword ptr [rsp+0C0h+Identifier.LowPart], rax; Identifier
0x18002069c  mov     [rbp+57h+hAuthzClientContext], r14
0x1800206a0  call    cs:__imp_AuthzInitializeContextFromSid
0x1800206a6  test    eax, eax
0x1800206a8  jnz     short loc_1800206FA
0x1800206aa  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800206af  mov     ebx, eax
0x1800206b1  test    eax, eax
0x1800206b3  jns     short loc_1800206FA
0x1800206b5  cmp     eax, 0D00000DFh
0x1800206ba  jnz     loc_180020785
0x1800206c0  xor     r8d, r8d; lpbOwnerDefaulted
0x1800206c3  mov     qword ptr [rbp+57h+arg_18.LowPart], r14
0x1800206c7  lea     rdx, [rbp+57h+arg_18]; pOwner
0x1800206cb  mov     rcx, rsi; pSecurityDescriptor
0x1800206ce  call    cs:__imp_GetSecurityDescriptorOwner
0x1800206d4  test    eax, eax
0x1800206d6  jz      loc_180020785
0x1800206dc  mov     rdx, qword ptr [rbp+57h+arg_18.LowPart]; pSid2
0x1800206e0  mov     rcx, rdi; pSid1
0x1800206e3  call    cs:__imp_EqualSid
0x1800206e9  neg     eax
0x1800206eb  sbb     ebx, ebx
0x1800206ed  not     ebx
0x1800206ef  and     ebx, 80070005h
0x1800206f5  jmp     loc_180020785
0x1800206fa  mov     rdx, [rbp+57h+hAuthzClientContext]; hAuthzClientContext
0x1800206fe  lea     rax, [rbp+57h+arg_18]
0x180020702  mov     [rsp+0C0h+phAccessCheckResults], r14; phAccessCheckResults
0x180020707  lea     r8, [rbp+57h+pRequest]; pRequest
0x18002070b  mov     [rbp+57h+var_60.GrantedAccessMask], rax
0x18002070f  xorps   xmm0, xmm0
0x180020712  lea     rax, [rbp+57h+var_70]
0x180020716  mov     qword ptr [rbp+57h+pRequest.DesiredAccess], 2000000h
0x18002071e  mov     [rbp+57h+var_60.Error], rax
0x180020722  xor     r9d, r9d; hAuditEvent
0x180020725  lea     rax, [rbp+57h+var_60]
0x180020729  mov     qword ptr [rbp+57h+pRequest.ObjectTypeListLength], r14
0x18002072d  mov     [rsp+0C0h+pReply], rax; pReply
0x180020732  xor     ecx, ecx; Flags
0x180020734  mov     dword ptr [rsp+0C0h+phAuthzClientContext], r14d; OptionalSecurityDescriptorCount
0x180020739  mov     [rsp+0C0h+DynamicGroupArgs], r14; OptionalSecurityDescriptorArray
0x18002073e  mov     qword ptr [rsp+0C0h+Identifier.LowPart], rsi; pSecurityDescriptor
0x180020743  movdqu  xmmword ptr [rbp+57h+pRequest.PrincipalSelfSid], xmm0
0x180020748  mov     [rbp+57h+pRequest.OptionalArguments], r14
0x18002074c  mov     [rbp+57h+var_70], r14d
0x180020750  mov     [rbp+57h+arg_18.LowPart], r14d
0x180020754  mov     qword ptr [rbp+57h+var_60.ResultListLength], 1
0x18002075c  mov     [rbp+57h+var_60.SaclEvaluationResults], r14
0x180020760  call    cs:__imp_AuthzAccessCheck
0x180020766  test    eax, eax
0x180020768  jz      short loc_18002077E
0x18002076a  mov     eax, [rbp+57h+arg_18.LowPart]
0x18002076d  mov     ecx, 120089h
0x180020772  and     eax, ecx
0x180020774  mov     ebx, r14d
0x180020777  cmp     eax, ecx
0x180020779  setnz   bl
0x18002077c  jmp     short loc_180020785
0x18002077e  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180020783  mov     ebx, eax
0x180020785  mov     rcx, [rbp+57h+hAuthzClientContext]; hAuthzClientContext
0x180020789  test    rcx, rcx
0x18002078c  jz      short loc_180020794
0x18002078e  call    cs:__imp_AuthzFreeContext
0x180020794  lea     rcx, ?s_mutex@CFileHandler@@0VCMutexSem@@A; lpCriticalSection
0x18002079b  call    cs:__imp_LeaveCriticalSection
0x1800207a1  mov     eax, ebx
0x1800207a3  jmp     short loc_1800207B7
0x1800207a5  lea     rcx, ?s_mutex@CFileHandler@@0VCMutexSem@@A; lpCriticalSection
0x1800207ac  call    cs:__imp_LeaveCriticalSection
0x1800207b2  mov     eax, 80070057h
0x1800207b7  lea     r11, [rsp+0C0h+var_10]
0x1800207bf  mov     rbx, [r11+20h]
0x1800207c3  mov     rsi, [r11+28h]
0x1800207c7  mov     rsp, r11
0x1800207ca  pop     r14
0x1800207cc  pop     rdi
0x1800207cd  pop     rbp
0x1800207ce  retn
```
