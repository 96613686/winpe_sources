# CompareSecurityContexts

- ea: `0x180046ed0`
- end: `0x180047033`
- name: `CompareSecurityContexts`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800455b0`

## callees

- `0x1800034e0`
- `0x180012bd0`
- `0x180046dcc`
- `0x180046e48`
- `0x180046ed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046fd3`
- `AUTHZ!AuthzFreeContext` at `0x180047005`
- `AUTHZ!AuthzFreeContext` at `0x180047005`
- `AUTHZ!AuthzAccessCheck` at `0x180046fc3`
- `AUTHZ!AuthzAccessCheck` at `0x180046fc3`

## string_xrefs

- `0x180046fe2`: `AuthzAccessCheck`

## pseudocode

```c
__int64 __fastcall CompareSecurityContexts(__int64 a1, __int64 a2, _QWORD *a3)
{
  bool v5; // zf
  unsigned int v6; // ebx
  __int64 v7; // rax
  DWORD LastError; // eax
  __int64 v9; // rcx
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+20h] [rbp-59h]
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+50h] [rbp-29h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+58h] [rbp-21h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+78h] [rbp-1h] BYREF
  int v15; // [rsp+A0h] [rbp+27h] BYREF
  int v16; // [rsp+A4h] [rbp+2Bh] BYREF
  int v17; // [rsp+A8h] [rbp+2Fh] BYREF

  hAuthzClientContext = 0;
  v5 = *(_DWORD *)a2 == 13;
  memset(&pReply, 0, 28);
  v6 = 2;
  v16 = 0;
  memset(&pRequest, 0, 36);
  v17 = 0;
  v15 = 0;
  if ( v5 )
  {
    v7 = ClientContextFromSid(*(_QWORD *)(a2 + 8), &hAuthzClientContext);
  }
  else
  {
    if ( *(_DWORD *)a2 != 15 )
      __fastfail(5u);
    v7 = ClientContextFromTokenInformation(*(PSID ***)(a2 + 8), &hAuthzClientContext);
  }
  if ( !v7 )
  {
    pRequest.OptionalArguments = 0;
    pReply.GrantedAccessMask = (PACCESS_MASK)&v16;
    pRequest.DesiredAccess = 1;
    pReply.SaclEvaluationResults = (PDWORD)&v17;
    pReply.Error = (PDWORD)&v15;
    pSecurityDescriptor = *(PSECURITY_DESCRIPTOR *)(a1 + 8);
    memset(&pRequest.PrincipalSelfSid, 0, 20);
    *(_QWORD *)&pReply.ResultListLength = 1;
    if ( AuthzAccessCheck(1u, hAuthzClientContext, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
    {
      v6 = v15 != 0 ? 2 : 0;
    }
    else
    {
      LastError = GetLastError();
      *a3 = WfpReportSysErrorAsWinError(v9, "AuthzAccessCheck", LastError);
    }
  }
  if ( hAuthzClientContext )
    AuthzFreeContext(hAuthzClientContext);
  return v6;
}

```

## disassembly

```asm
0x180046ed0  mov     [rsp-8+arg_18], rbx
0x180046ed5  push    rbp
0x180046ed6  push    rsi
0x180046ed7  push    rdi
0x180046ed8  lea     rbp, [rsp-47h]
0x180046edd  sub     rsp, 0C0h
0x180046ee4  mov     rax, cs:__security_cookie
0x180046eeb  xor     rax, rsp
0x180046eee  mov     [rbp+57h+var_20], rax
0x180046ef2  xorps   xmm0, xmm0
0x180046ef5  mov     [rbp+57h+hAuthzClientContext], 0
0x180046efd  mov     rsi, rcx
0x180046f00  mov     rdi, r8
0x180046f03  xor     ecx, ecx
0x180046f05  mov     rax, rdx
0x180046f08  cmp     dword ptr [rdx], 0Dh
0x180046f0b  movups  xmmword ptr [rbp+57h+var_78.ResultListLength], xmm0
0x180046f0f  mov     dword ptr [rbp+57h+pRequest.OptionalArguments], ecx
0x180046f12  lea     ebx, [rcx+2]
0x180046f15  mov     [rbp+57h+var_2C], ecx
0x180046f18  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x180046f1c  mov     [rbp+57h+var_28], ecx
0x180046f1f  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x180046f23  mov     [rbp+57h+var_30], ecx
0x180046f26  movups  xmmword ptr [rbp+57h+var_78.GrantedAccessMask+4], xmm0
0x180046f2a  jz      short loc_180046F45
0x180046f2c  cmp     dword ptr [rdx], 0Fh
0x180046f2f  jz      short loc_180046F36
0x180046f31  lea     ecx, [rbx+3]
0x180046f34  int     29h; Win8: RtlFailFast(ecx)
0x180046f36  mov     rcx, [rax+8]; DynamicGroupArgs
0x180046f3a  lea     rdx, [rbp+57h+hAuthzClientContext]; phAuthzClientContext
0x180046f3e  call    ClientContextFromTokenInformation
0x180046f43  jmp     short loc_180046F52
0x180046f45  mov     rcx, [rax+8]
0x180046f49  lea     rdx, [rbp+57h+hAuthzClientContext]
0x180046f4d  call    ClientContextFromSid
0x180046f52  test    rax, rax
0x180046f55  jnz     loc_180046FFC
0x180046f5b  mov     rdx, [rbp+57h+hAuthzClientContext]; hAuthzClientContext
0x180046f5f  lea     ecx, [rax+1]; Flags
0x180046f62  mov     [rbp+57h+pRequest.ObjectTypeListLength], eax
0x180046f65  lea     r8, [rbp+57h+pRequest]; pRequest
0x180046f69  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x180046f6d  xorps   xmm0, xmm0
0x180046f70  mov     [rsp+0D0h+phAccessCheckResults], 0; phAccessCheckResults
0x180046f79  lea     rax, [rbp+57h+var_2C]
0x180046f7d  mov     [rbp+57h+var_78.GrantedAccessMask], rax
0x180046f81  xor     r9d, r9d; hAuditEvent
0x180046f84  lea     rax, [rbp+57h+var_28]
0x180046f88  mov     [rbp+57h+pRequest.DesiredAccess], ecx
0x180046f8b  mov     [rbp+57h+var_78.SaclEvaluationResults], rax
0x180046f8f  lea     rax, [rbp+57h+var_30]
0x180046f93  mov     [rbp+57h+var_78.Error], rax
0x180046f97  lea     rax, [rbp+57h+var_78]
0x180046f9b  mov     [rsp+0D0h+pReply], rax; pReply
0x180046fa0  mov     rax, [rsi+8]
0x180046fa4  mov     [rsp+0D0h+OptionalSecurityDescriptorCount], 0; OptionalSecurityDescriptorCount
0x180046fac  mov     [rsp+0D0h+OptionalSecurityDescriptorArray], 0; OptionalSecurityDescriptorArray
0x180046fb5  mov     [rsp+0D0h+pSecurityDescriptor], rax; pSecurityDescriptor
0x180046fba  movdqu  xmmword ptr [rbp+57h+pRequest.PrincipalSelfSid], xmm0
0x180046fbf  mov     qword ptr [rbp+57h+var_78.ResultListLength], rcx
0x180046fc3  call    cs:__imp_AuthzAccessCheck
0x180046fca  nop     dword ptr [rax+rax+00h]
0x180046fcf  test    eax, eax
0x180046fd1  jnz     short loc_180046FF3
0x180046fd3  call    cs:__imp_GetLastError
0x180046fda  nop     dword ptr [rax+rax+00h]
0x180046fdf  mov     r8d, eax
0x180046fe2  lea     rdx, aAuthzaccessche_0; "AuthzAccessCheck"
0x180046fe9  call    WfpReportSysErrorAsWinError
0x180046fee  mov     [rdi], rax
0x180046ff1  jmp     short loc_180046FFC
0x180046ff3  mov     eax, [rbp+57h+var_30]
0x180046ff6  neg     eax
0x180046ff8  sbb     ecx, ecx
0x180046ffa  and     ebx, ecx
0x180046ffc  mov     rcx, [rbp+57h+hAuthzClientContext]; hAuthzClientContext
0x180047000  test    rcx, rcx
0x180047003  jz      short loc_180047011
0x180047005  call    cs:__imp_AuthzFreeContext
0x18004700c  nop     dword ptr [rax+rax+00h]
0x180047011  mov     eax, ebx
0x180047013  mov     rcx, [rbp+57h+var_20]
0x180047017  xor     rcx, rsp; StackCookie
0x18004701a  call    __security_check_cookie
0x18004701f  mov     rbx, [rsp+0D0h+arg_18]
0x180047027  add     rsp, 0C0h
0x18004702e  pop     rdi
0x18004702f  pop     rsi
0x180047030  pop     rbp
0x180047031  retn
```
