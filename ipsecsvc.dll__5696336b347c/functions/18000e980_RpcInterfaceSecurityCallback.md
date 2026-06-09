# RpcInterfaceSecurityCallback

- ea: `0x18000e980`
- end: `0x18000eba5`
- name: `RpcInterfaceSecurityCallback`
- size: `549`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000e980`
- `0x18004d06a`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000e9ee`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000e9ee`
- `RPCRT4!RpcStringFreeW` at `0x18000eb75`
- `RPCRT4!RpcStringFreeW` at `0x18000eb85`
- `RPCRT4!RpcStringFreeW` at `0x18000eb75`
- `RPCRT4!RpcStringFreeW` at `0x18000eb85`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000ea12`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000ea12`
- `RPCRT4!RpcStringBindingParseW` at `0x18000ea49`
- `RPCRT4!RpcStringBindingParseW` at `0x18000ea49`
- `RPCRT4!RpcFreeAuthorizationContext` at `0x18000eb65`
- `RPCRT4!RpcFreeAuthorizationContext` at `0x18000eb65`
- `RPCRT4!RpcGetAuthorizationContextForClient` at `0x18000eae5`
- `RPCRT4!RpcGetAuthorizationContextForClient` at `0x18000eae5`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x18000eaa1`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x18000eaa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb4a`
- `AUTHZ!AuthzAccessCheck` at `0x18000eb40`
- `AUTHZ!AuthzAccessCheck` at `0x18000eb40`

## pseudocode

```c
__int64 __fastcall RpcInterfaceSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  DWORD IsClientLocal; // ebx
  RPC_WSTR Protseq; // [rsp+50h] [rbp-39h] BYREF
  int v6; // [rsp+58h] [rbp-31h] BYREF
  RPC_WSTR StringBinding; // [rsp+60h] [rbp-29h] BYREF
  PVOID v8; // [rsp+68h] [rbp-21h] BYREF
  int v9; // [rsp+70h] [rbp-19h] BYREF
  PVOID pAuthzClientContext; // [rsp+78h] [rbp-11h] BYREF
  _AUTHZ_ACCESS_REPLY pReply; // [rsp+80h] [rbp-9h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+A0h] [rbp+17h] BYREF
  unsigned int ClientLocalFlag; // [rsp+100h] [rbp+77h] BYREF
  unsigned int AuthnLevel; // [rsp+108h] [rbp+7Fh] BYREF

  *(_QWORD *)&pRequest.DesiredAccess = 0x20000;
  ClientLocalFlag = 0;
  AuthnLevel = 0;
  memset(&pReply, 0, 28);
  v6 = 5;
  StringBinding = 0;
  Protseq = 0;
  v9 = 0;
  memset(&pRequest.PrincipalSelfSid, 0, 32);
  v8 = 0;
  if ( !gbEnableRemoteMgmt )
  {
    IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
    if ( IsClientLocal )
      goto LABEL_19;
    if ( !ClientLocalFlag )
      goto LABEL_4;
  }
  IsClientLocal = RpcBindingToStringBindingW(Context, &StringBinding);
  if ( !IsClientLocal )
  {
    if ( !StringBinding )
    {
LABEL_7:
      IsClientLocal = 1766;
      goto LABEL_19;
    }
    IsClientLocal = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
    if ( !IsClientLocal )
    {
      if ( !Protseq )
        goto LABEL_7;
      if ( wcscmp_0(Protseq, L"ncalrpc") && wcscmp_0(Protseq, L"ncacn_np") )
        goto LABEL_4;
      IsClientLocal = RpcBindingInqAuthClientW(Context, 0, 0, &AuthnLevel, 0, 0);
      if ( IsClientLocal )
        goto LABEL_19;
      if ( AuthnLevel < 6 )
      {
LABEL_4:
        IsClientLocal = 5;
        goto LABEL_19;
      }
      pAuthzClientContext = 0;
      v8 = 0;
      IsClientLocal = RpcGetAuthorizationContextForClient(Context, 0, 0, 0, 0, 0, 0, &pAuthzClientContext);
      if ( !IsClientLocal )
      {
        pReply.GrantedAccessMask = (PACCESS_MASK)&v9;
        pReply.Error = (PDWORD)&v6;
        v8 = pAuthzClientContext;
        pReply.ResultListLength = 1;
        pReply.SaclEvaluationResults = 0;
        if ( AuthzAccessCheck(
               0,
               (AUTHZ_CLIENT_CONTEXT_HANDLE)pAuthzClientContext,
               &pRequest,
               0,
               gpSPDSD,
               0,
               0,
               &pReply,
               0) )
        {
          if ( v6 )
            IsClientLocal = 5;
        }
        else
        {
          IsClientLocal = GetLastError();
        }
      }
    }
  }
LABEL_19:
  if ( v8 )
    RpcFreeAuthorizationContext(&v8);
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return IsClientLocal;
}

```

## disassembly

```asm
0x18000e980  mov     [rsp-8+arg_0], rbx
0x18000e985  mov     [rsp-8+arg_8], rsi
0x18000e98a  push    rbp
0x18000e98b  push    rdi
0x18000e98c  push    r14
0x18000e98e  lea     rbp, [rsp-47h]
0x18000e993  sub     rsp, 0D0h
0x18000e99a  xor     esi, esi
0x18000e99c  mov     qword ptr [rbp+57h+pRequest.DesiredAccess], 20000h
0x18000e9a4  xorps   xmm0, xmm0
0x18000e9a7  mov     [rbp+57h+ClientLocalFlag], esi
0x18000e9aa  xor     eax, eax
0x18000e9ac  mov     [rbp+57h+AuthnLevel], esi
0x18000e9af  cmp     cs:gbEnableRemoteMgmt, esi
0x18000e9b5  mov     r14d, 5
0x18000e9bb  movups  xmmword ptr [rbp+57h+pReply.ResultListLength], xmm0
0x18000e9bf  mov     rdi, rdx
0x18000e9c2  mov     [rbp+57h+var_88], r14d
0x18000e9c6  movups  xmmword ptr [rbp+57h+pReply.GrantedAccessMask+4], xmm0
0x18000e9ca  mov     [rbp+57h+StringBinding], rsi
0x18000e9ce  mov     [rbp+57h+Protseq], rsi
0x18000e9d2  mov     [rbp+57h+var_70], esi
0x18000e9d5  movdqu  xmmword ptr [rbp+57h+pRequest.PrincipalSelfSid], xmm0
0x18000e9da  mov     qword ptr [rbp+57h+pRequest.ObjectTypeListLength], rsi
0x18000e9de  mov     [rbp+57h+pRequest.OptionalArguments], rsi
0x18000e9e2  mov     [rbp+57h+var_78], rsi
0x18000e9e6  jnz     short loc_18000EA0B
0x18000e9e8  lea     rdx, [rbp+57h+ClientLocalFlag]; ClientLocalFlag
0x18000e9ec  xor     ecx, ecx; BindingHandle
0x18000e9ee  call    cs:__imp_I_RpcBindingIsClientLocal
0x18000e9f4  mov     ebx, eax
0x18000e9f6  test    eax, eax
0x18000e9f8  jnz     loc_18000EB5B
0x18000e9fe  cmp     [rbp+57h+ClientLocalFlag], esi
0x18000ea01  jnz     short loc_18000EA0B
0x18000ea03  mov     ebx, r14d
0x18000ea06  jmp     loc_18000EB5B
0x18000ea0b  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x18000ea0f  mov     rcx, rdi; Binding
0x18000ea12  call    cs:__imp_RpcBindingToStringBindingW
0x18000ea18  mov     ebx, eax
0x18000ea1a  test    eax, eax
0x18000ea1c  jnz     loc_18000EB5B
0x18000ea22  cmp     [rbp+57h+StringBinding], rsi
0x18000ea26  jnz     short loc_18000EA32
0x18000ea28  mov     ebx, 6E6h
0x18000ea2d  jmp     loc_18000EB5B
0x18000ea32  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x18000ea36  lea     r8, [rbp+57h+Protseq]; Protseq
0x18000ea3a  mov     [rsp+0E0h+NetworkOptions], rsi; NetworkOptions
0x18000ea3f  xor     r9d, r9d; NetworkAddr
0x18000ea42  xor     edx, edx; ObjUuid
0x18000ea44  mov     [rsp+0E0h+Endpoint], rsi; Endpoint
0x18000ea49  call    cs:__imp_RpcStringBindingParseW
0x18000ea4f  mov     ebx, eax
0x18000ea51  test    eax, eax
0x18000ea53  jnz     loc_18000EB5B
0x18000ea59  cmp     [rbp+57h+Protseq], rsi
0x18000ea5d  jz      short loc_18000EA28
0x18000ea5f  mov     rcx, [rbp+57h+Protseq]; String1
0x18000ea63  lea     rdx, aNcalrpc; "ncalrpc"
0x18000ea6a  call    wcscmp_0
0x18000ea6f  test    eax, eax
0x18000ea71  jz      short loc_18000EA8B
0x18000ea73  mov     rcx, [rbp+57h+Protseq]; String1
0x18000ea77  lea     rdx, aNcacnNp; "ncacn_np"
0x18000ea7e  call    wcscmp_0
0x18000ea83  test    eax, eax
0x18000ea85  jnz     loc_18000EA03
0x18000ea8b  mov     [rsp+0E0h+NetworkOptions], rsi; AuthzSvc
0x18000ea90  lea     r9, [rbp+57h+AuthnLevel]; AuthnLevel
0x18000ea94  xor     r8d, r8d; ServerPrincName
0x18000ea97  mov     [rsp+0E0h+Endpoint], rsi; AuthnSvc
0x18000ea9c  xor     edx, edx; Privs
0x18000ea9e  mov     rcx, rdi; ClientBinding
0x18000eaa1  call    cs:__imp_RpcBindingInqAuthClientW
0x18000eaa7  mov     ebx, eax
0x18000eaa9  test    eax, eax
0x18000eaab  jnz     loc_18000EB5B
0x18000eab1  cmp     [rbp+57h+AuthnLevel], 6
0x18000eab5  jb      loc_18000EA03
0x18000eabb  lea     rcx, [rbp+57h+var_68]
0x18000eabf  mov     [rbp+57h+var_68], rsi
0x18000eac3  mov     [rsp+0E0h+pAuthzClientContext], rcx; pAuthzClientContext
0x18000eac8  xor     r9d, r9d; pExpirationTime
0x18000eacb  mov     [rsp+0E0h+Reserved4], rsi; Reserved4
0x18000ead0  xor     r8d, r8d; Reserved1
0x18000ead3  mov     dword ptr [rsp+0E0h+NetworkOptions], esi; Reserved3
0x18000ead7  xor     edx, edx; ImpersonateOnReturn
0x18000ead9  mov     rcx, rdi; ClientBinding
0x18000eadc  mov     [rsp+0E0h+Endpoint], rsi; Reserved2
0x18000eae1  mov     [rbp+57h+var_78], rsi
0x18000eae5  call    cs:__imp_RpcGetAuthorizationContextForClient
0x18000eaeb  mov     ebx, eax
0x18000eaed  test    eax, eax
0x18000eaef  jnz     short loc_18000EB5B
0x18000eaf1  mov     rdx, [rbp+57h+var_68]; hAuthzClientContext
0x18000eaf5  lea     rax, [rbp+57h+var_70]
0x18000eaf9  mov     [rbp+57h+pReply.GrantedAccessMask], rax
0x18000eafd  lea     r8, [rbp+57h+pRequest]; pRequest
0x18000eb01  mov     [rsp+0E0h+phAccessCheckResults], rsi; phAccessCheckResults
0x18000eb06  lea     rax, [rbp+57h+var_88]
0x18000eb0a  mov     [rbp+57h+pReply.Error], rax
0x18000eb0e  xor     r9d, r9d; hAuditEvent
0x18000eb11  lea     rax, [rbp+57h+pReply]
0x18000eb15  mov     [rbp+57h+var_78], rdx
0x18000eb19  mov     [rsp+0E0h+pAuthzClientContext], rax; pReply
0x18000eb1e  xor     ecx, ecx; Flags
0x18000eb20  mov     rax, cs:gpSPDSD
0x18000eb27  mov     dword ptr [rsp+0E0h+Reserved4], esi; OptionalSecurityDescriptorCount
0x18000eb2b  mov     [rsp+0E0h+NetworkOptions], rsi; OptionalSecurityDescriptorArray
0x18000eb30  mov     [rsp+0E0h+Endpoint], rax; pSecurityDescriptor
0x18000eb35  mov     [rbp+57h+pReply.ResultListLength], 1
0x18000eb3c  mov     [rbp+57h+pReply.SaclEvaluationResults], rsi
0x18000eb40  call    cs:__imp_AuthzAccessCheck
0x18000eb46  test    eax, eax
0x18000eb48  jnz     short loc_18000EB54
0x18000eb4a  call    cs:__imp_GetLastError
0x18000eb50  mov     ebx, eax
0x18000eb52  jmp     short loc_18000EB5B
0x18000eb54  cmp     [rbp+57h+var_88], esi
0x18000eb57  cmovnz  ebx, r14d
0x18000eb5b  cmp     [rbp+57h+var_78], rsi
0x18000eb5f  jz      short loc_18000EB6B
0x18000eb61  lea     rcx, [rbp+57h+var_78]; pAuthzClientContext
0x18000eb65  call    cs:__imp_RpcFreeAuthorizationContext
0x18000eb6b  cmp     [rbp+57h+Protseq], rsi
0x18000eb6f  jz      short loc_18000EB7B
0x18000eb71  lea     rcx, [rbp+57h+Protseq]; String
0x18000eb75  call    cs:__imp_RpcStringFreeW
0x18000eb7b  cmp     [rbp+57h+StringBinding], rsi
0x18000eb7f  jz      short loc_18000EB8B
0x18000eb81  lea     rcx, [rbp+57h+StringBinding]; String
0x18000eb85  call    cs:__imp_RpcStringFreeW
0x18000eb8b  lea     r11, [rsp+0E0h+var_10]
0x18000eb93  mov     eax, ebx
0x18000eb95  mov     rbx, [r11+20h]
0x18000eb99  mov     rsi, [r11+28h]
0x18000eb9d  mov     rsp, r11
0x18000eba0  pop     r14
0x18000eba2  pop     rdi
0x18000eba3  pop     rbp
0x18000eba4  retn
```
