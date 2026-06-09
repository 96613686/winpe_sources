# PerformAccessCheckAgainstFileObject

- ea: `0x1800025cc`
- end: `0x18000284c`
- name: `PerformAccessCheckAgainstFileObject`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004db40`

## callees

- `0x1800025cc`
- `0x1800cc9e0`
- `0x1800ccaa0`

## import_xrefs

- `ADVAPI32!GetNamedSecurityInfoW` at `0x18000269b`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18000269b`
- `ADVAPI32!OpenProcessToken` at `0x1800026de`
- `ADVAPI32!OpenProcessToken` at `0x1800026de`
- `RPCRT4!RpcImpersonateClient` at `0x180002665`
- `RPCRT4!RpcImpersonateClient` at `0x180002665`
- `RPCRT4!RpcRevertToSelf` at `0x1800026af`
- `RPCRT4!RpcRevertToSelf` at `0x1800026af`
- `AUTHZ!AuthzInitializeContextFromToken` at `0x180002742`
- `AUTHZ!AuthzInitializeContextFromToken` at `0x180002742`
- `AUTHZ!AuthzFreeResourceManager` at `0x180002803`
- `AUTHZ!AuthzFreeResourceManager` at `0x180002803`
- `AUTHZ!AuthzFreeContext` at `0x180002819`
- `AUTHZ!AuthzFreeContext` at `0x180002819`
- `AUTHZ!AuthzInitializeResourceManager` at `0x18000270b`
- `AUTHZ!AuthzInitializeResourceManager` at `0x18000270b`
- `AUTHZ!AuthzAccessCheck` at `0x1800027a7`
- `AUTHZ!AuthzAccessCheck` at `0x1800027a7`
- `KERNEL32!GetLastError` at `0x18000264e`
- `KERNEL32!GetLastError` at `0x18000264e`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000263e`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000263e`
- `KERNEL32!GetCurrentProcess` at `0x1800026c5`
- `KERNEL32!GetCurrentProcess` at `0x1800026c5`
- `KERNEL32!CloseHandle` at `0x1800027d7`
- `KERNEL32!CloseHandle` at `0x1800027d7`
- `KERNEL32!LocalFree` at `0x1800027ed`
- `KERNEL32!LocalFree` at `0x1800027ed`

## pseudocode

```c
__int64 __fastcall PerformAccessCheckAgainstFileObject(const WCHAR *a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  RPC_STATUS v5; // edi
  HANDLE CurrentProcess; // rax
  DWORD NamedSecurityInfoW; // [rsp+50h] [rbp-B0h] BYREF
  int v9; // [rsp+54h] [rbp-ACh] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+60h] [rbp-A0h] BYREF
  AUTHZ_RESOURCE_MANAGER_HANDLE phAuthzResourceManager; // [rsp+68h] [rbp-98h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE phAuthzClientContext; // [rsp+70h] [rbp-90h] BYREF
  _AUTHZ_ACCESS_REPLY pReply; // [rsp+78h] [rbp-88h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Dst[32768]; // [rsp+C0h] [rbp-40h] BYREF

  pSecurityDescriptor = 0;
  v9 = 0;
  memset(&pRequest, 0, sizeof(pRequest));
  phAuthzResourceManager = 0;
  phAuthzClientContext = 0;
  memset(&pReply, 0, sizeof(pReply));
  TokenHandle = 0;
  *a4 = 0;
  if ( !ExpandEnvironmentStringsW(a1, Dst, 0x7FFFu) )
    goto LABEL_2;
  v5 = RpcImpersonateClient(0);
  NamedSecurityInfoW = GetNamedSecurityInfoW(Dst, SE_FILE_OBJECT, 5u, 0, 0, 0, 0, &pSecurityDescriptor);
  if ( !v5 )
    RpcRevertToSelf();
  if ( !NamedSecurityInfoW )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle)
      || !AuthzInitializeResourceManager(0, 0, 0, 0, 0, &phAuthzResourceManager)
      || !AuthzInitializeContextFromToken(0, TokenHandle, phAuthzResourceManager, 0, 0, 0, &phAuthzClientContext)
      || (pReply.GrantedAccessMask = (PACCESS_MASK)&v9,
          pReply.Error = &NamedSecurityInfoW,
          pRequest.DesiredAccess = 279,
          pReply.ResultListLength = 1,
          !AuthzAccessCheck(0, phAuthzClientContext, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0)) )
    {
LABEL_2:
      NamedSecurityInfoW = GetLastError();
      goto LABEL_13;
    }
    if ( NamedSecurityInfoW )
      NamedSecurityInfoW = 0;
    else
      *a4 = 1;
  }
LABEL_13:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( pSecurityDescriptor )
    LocalFree(pSecurityDescriptor);
  if ( phAuthzResourceManager )
    AuthzFreeResourceManager(phAuthzResourceManager);
  if ( phAuthzClientContext )
    AuthzFreeContext(phAuthzClientContext);
  return NamedSecurityInfoW;
}

```

## disassembly

```asm
0x1800025cc  mov     [rsp-8+arg_8], rbx
0x1800025d1  push    rbp
0x1800025d2  push    rsi
0x1800025d3  push    rdi
0x1800025d4  lea     rbp, [rsp-0FFD0h]
0x1800025dc  mov     eax, 100D0h
0x1800025e1  call    _alloca_probe
0x1800025e6  sub     rsp, rax
0x1800025e9  mov     rax, cs:__security_cookie
0x1800025f0  xor     rax, rsp
0x1800025f3  mov     [rbp+0FFE0h+var_20], rax
0x1800025fa  xor     ebx, ebx
0x1800025fc  lea     rdx, [rbp+0FFE0h+Dst]; lpDst
0x180002600  xorps   xmm0, xmm0
0x180002603  mov     [rsp+100E0h+pSecurityDescriptor], rbx
0x180002608  xor     eax, eax
0x18000260a  mov     [rsp+100E0h+var_1008C], ebx
0x18000260e  mov     r8d, 7FFFh; nSize
0x180002614  mov     [rbp+0FFE0h+pRequest.OptionalArguments], rax
0x180002618  movups  xmmword ptr [rbp+0FFE0h+pRequest.DesiredAccess], xmm0
0x18000261c  mov     [rsp+100E0h+phAuthzResourceManager], rbx
0x180002621  mov     rsi, r9
0x180002624  movups  xmmword ptr [rbp+0FFE0h+pRequest.ObjectTypeList], xmm0
0x180002628  mov     [rsp+100E0h+phAuthzClientContext], rbx
0x18000262d  movups  xmmword ptr [rsp+100E0h+pReply.ResultListLength], xmm0
0x180002632  mov     [rsp+100E0h+TokenHandle], rbx
0x180002637  movups  xmmword ptr [rbp+0FFE0h+pReply.SaclEvaluationResults], xmm0
0x18000263b  mov     [r9], ebx
0x18000263e  call    cs:__imp_ExpandEnvironmentStringsW
0x180002645  nop     dword ptr [rax+rax+00h]
0x18000264a  test    eax, eax
0x18000264c  jnz     short loc_180002663
0x18000264e  call    cs:__imp_GetLastError
0x180002655  nop     dword ptr [rax+rax+00h]
0x18000265a  mov     [rsp+100E0h+var_10090], eax
0x18000265e  jmp     loc_1800027CD
0x180002663  xor     ecx, ecx; BindingHandle
0x180002665  call    cs:__imp_RpcImpersonateClient
0x18000266c  nop     dword ptr [rax+rax+00h]
0x180002671  xor     r9d, r9d; ppsidOwner
0x180002674  lea     rcx, [rbp+0FFE0h+Dst]; pObjectName
0x180002678  mov     edi, eax
0x18000267a  lea     rax, [rsp+100E0h+pSecurityDescriptor]
0x18000267f  mov     [rsp+100E0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180002684  mov     [rsp+100E0h+ppSacl], rbx; ppSacl
0x180002689  mov     [rsp+100E0h+ppDacl], rbx; ppDacl
0x18000268e  lea     edx, [r9+1]; ObjectType
0x180002692  lea     r8d, [r9+5]; SecurityInfo
0x180002696  mov     [rsp+100E0h+ppsidGroup], rbx; ppsidGroup
0x18000269b  call    cs:__imp_GetNamedSecurityInfoW
0x1800026a2  nop     dword ptr [rax+rax+00h]
0x1800026a7  mov     [rsp+100E0h+var_10090], eax
0x1800026ab  test    edi, edi
0x1800026ad  jnz     short loc_1800026BB
0x1800026af  call    cs:__imp_RpcRevertToSelf
0x1800026b6  nop     dword ptr [rax+rax+00h]
0x1800026bb  cmp     [rsp+100E0h+var_10090], ebx
0x1800026bf  jnz     loc_1800027CD
0x1800026c5  call    cs:__imp_GetCurrentProcess
0x1800026cc  nop     dword ptr [rax+rax+00h]
0x1800026d1  lea     r8, [rsp+100E0h+TokenHandle]; TokenHandle
0x1800026d6  mov     edx, 20008h; DesiredAccess
0x1800026db  mov     rcx, rax; ProcessHandle
0x1800026de  call    cs:__imp_OpenProcessToken
0x1800026e5  nop     dword ptr [rax+rax+00h]
0x1800026ea  test    eax, eax
0x1800026ec  jz      loc_18000264E
0x1800026f2  lea     rax, [rsp+100E0h+phAuthzResourceManager]
0x1800026f7  xor     r9d, r9d; pfnFreeDynamicGroups
0x1800026fa  mov     [rsp+100E0h+ppDacl], rax; phAuthzResourceManager
0x1800026ff  xor     r8d, r8d; pfnComputeDynamicGroups
0x180002702  xor     edx, edx; pfnDynamicAccessCheck
0x180002704  mov     [rsp+100E0h+ppsidGroup], rbx; szResourceManagerName
0x180002709  xor     ecx, ecx; Flags
0x18000270b  call    cs:__imp_AuthzInitializeResourceManager
0x180002712  nop     dword ptr [rax+rax+00h]
0x180002717  test    eax, eax
0x180002719  jz      loc_18000264E
0x18000271f  mov     r8, [rsp+100E0h+phAuthzResourceManager]; hAuthzResourceManager
0x180002724  lea     rax, [rsp+100E0h+phAuthzClientContext]
0x180002729  mov     rdx, [rsp+100E0h+TokenHandle]; TokenHandle
0x18000272e  xor     r9d, r9d; pExpirationTime
0x180002731  mov     [rsp+100E0h+ppSacl], rax; phAuthzClientContext
0x180002736  xor     ecx, ecx; Flags
0x180002738  mov     [rsp+100E0h+ppDacl], rbx; DynamicGroupArgs
0x18000273d  mov     [rsp+100E0h+ppsidGroup], rbx; Identifier
0x180002742  call    cs:__imp_AuthzInitializeContextFromToken
0x180002749  nop     dword ptr [rax+rax+00h]
0x18000274e  test    eax, eax
0x180002750  jz      loc_18000264E
0x180002756  mov     rdx, [rsp+100E0h+phAuthzClientContext]; hAuthzClientContext
0x18000275b  lea     rax, [rsp+100E0h+var_1008C]
0x180002760  mov     [rbp+0FFE0h+pReply.GrantedAccessMask], rax
0x180002764  lea     r8, [rbp+0FFE0h+pRequest]; pRequest
0x180002768  mov     [rsp+100E0h+phAccessCheckResults], rbx; phAccessCheckResults
0x18000276d  lea     rax, [rsp+100E0h+var_10090]
0x180002772  mov     [rbp+0FFE0h+pReply.Error], rax
0x180002776  xor     r9d, r9d; hAuditEvent
0x180002779  lea     rax, [rsp+100E0h+pReply]
0x18000277e  mov     [rbp+0FFE0h+pRequest.DesiredAccess], 117h
0x180002785  mov     [rsp+100E0h+ppSecurityDescriptor], rax; pReply
0x18000278a  xor     ecx, ecx; Flags
0x18000278c  mov     rax, [rsp+100E0h+pSecurityDescriptor]
0x180002791  mov     dword ptr [rsp+100E0h+ppSacl], ebx; OptionalSecurityDescriptorCount
0x180002795  mov     [rsp+100E0h+ppDacl], rbx; OptionalSecurityDescriptorArray
0x18000279a  mov     [rsp+100E0h+ppsidGroup], rax; pSecurityDescriptor
0x18000279f  mov     [rsp+100E0h+pReply.ResultListLength], 1
0x1800027a7  call    cs:__imp_AuthzAccessCheck
0x1800027ae  nop     dword ptr [rax+rax+00h]
0x1800027b3  test    eax, eax
0x1800027b5  jz      loc_18000264E
0x1800027bb  cmp     [rsp+100E0h+var_10090], ebx
0x1800027bf  jnz     short loc_1800027C9
0x1800027c1  mov     dword ptr [rsi], 1
0x1800027c7  jmp     short loc_1800027CD
0x1800027c9  mov     [rsp+100E0h+var_10090], ebx
0x1800027cd  mov     rcx, [rsp+100E0h+TokenHandle]; hObject
0x1800027d2  test    rcx, rcx
0x1800027d5  jz      short loc_1800027E3
0x1800027d7  call    cs:__imp_CloseHandle
0x1800027de  nop     dword ptr [rax+rax+00h]
0x1800027e3  mov     rcx, [rsp+100E0h+pSecurityDescriptor]; hMem
0x1800027e8  test    rcx, rcx
0x1800027eb  jz      short loc_1800027F9
0x1800027ed  call    cs:__imp_LocalFree
0x1800027f4  nop     dword ptr [rax+rax+00h]
0x1800027f9  mov     rcx, [rsp+100E0h+phAuthzResourceManager]; hAuthzResourceManager
0x1800027fe  test    rcx, rcx
0x180002801  jz      short loc_18000280F
0x180002803  call    cs:__imp_AuthzFreeResourceManager
0x18000280a  nop     dword ptr [rax+rax+00h]
0x18000280f  mov     rcx, [rsp+100E0h+phAuthzClientContext]; hAuthzClientContext
0x180002814  test    rcx, rcx
0x180002817  jz      short loc_180002825
0x180002819  call    cs:__imp_AuthzFreeContext
0x180002820  nop     dword ptr [rax+rax+00h]
0x180002825  mov     eax, [rsp+100E0h+var_10090]
0x180002829  mov     rcx, [rbp+0FFE0h+var_20]
0x180002830  xor     rcx, rsp; StackCookie
0x180002833  call    __security_check_cookie
0x180002838  mov     rbx, [rsp+100E0h+arg_8]
0x180002840  add     rsp, 100D0h
0x180002847  pop     rdi
0x180002848  pop     rsi
0x180002849  pop     rbp
0x18000284a  retn
```
