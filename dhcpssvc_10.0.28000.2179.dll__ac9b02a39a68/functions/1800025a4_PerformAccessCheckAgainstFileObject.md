# PerformAccessCheckAgainstFileObject

- ea: `0x1800025a4`
- end: `0x180002824`
- name: `PerformAccessCheckAgainstFileObject`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004d780`

## callees

- `0x1800025a4`
- `0x1800cdac0`
- `0x1800cdb80`

## import_xrefs

- `ADVAPI32!GetNamedSecurityInfoW` at `0x180002673`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180002673`
- `ADVAPI32!OpenProcessToken` at `0x1800026b6`
- `ADVAPI32!OpenProcessToken` at `0x1800026b6`
- `RPCRT4!RpcImpersonateClient` at `0x18000263d`
- `RPCRT4!RpcImpersonateClient` at `0x18000263d`
- `RPCRT4!RpcRevertToSelf` at `0x180002687`
- `RPCRT4!RpcRevertToSelf` at `0x180002687`
- `AUTHZ!AuthzInitializeContextFromToken` at `0x18000271a`
- `AUTHZ!AuthzInitializeContextFromToken` at `0x18000271a`
- `AUTHZ!AuthzFreeResourceManager` at `0x1800027db`
- `AUTHZ!AuthzFreeResourceManager` at `0x1800027db`
- `AUTHZ!AuthzFreeContext` at `0x1800027f1`
- `AUTHZ!AuthzFreeContext` at `0x1800027f1`
- `AUTHZ!AuthzInitializeResourceManager` at `0x1800026e3`
- `AUTHZ!AuthzInitializeResourceManager` at `0x1800026e3`
- `AUTHZ!AuthzAccessCheck` at `0x18000277f`
- `AUTHZ!AuthzAccessCheck` at `0x18000277f`
- `KERNEL32!GetLastError` at `0x180002626`
- `KERNEL32!GetLastError` at `0x180002626`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180002616`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180002616`
- `KERNEL32!GetCurrentProcess` at `0x18000269d`
- `KERNEL32!GetCurrentProcess` at `0x18000269d`
- `KERNEL32!CloseHandle` at `0x1800027af`
- `KERNEL32!CloseHandle` at `0x1800027af`
- `KERNEL32!LocalFree` at `0x1800027c5`
- `KERNEL32!LocalFree` at `0x1800027c5`

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
0x1800025a4  mov     [rsp-8+arg_8], rbx
0x1800025a9  push    rbp
0x1800025aa  push    rsi
0x1800025ab  push    rdi
0x1800025ac  lea     rbp, [rsp-0FFD0h]
0x1800025b4  mov     eax, 100D0h
0x1800025b9  call    _alloca_probe
0x1800025be  sub     rsp, rax
0x1800025c1  mov     rax, cs:__security_cookie
0x1800025c8  xor     rax, rsp
0x1800025cb  mov     [rbp+0FFE0h+var_20], rax
0x1800025d2  xor     ebx, ebx
0x1800025d4  lea     rdx, [rbp+0FFE0h+Dst]; lpDst
0x1800025d8  xorps   xmm0, xmm0
0x1800025db  mov     [rsp+100E0h+pSecurityDescriptor], rbx
0x1800025e0  xor     eax, eax
0x1800025e2  mov     [rsp+100E0h+var_1008C], ebx
0x1800025e6  mov     r8d, 7FFFh; nSize
0x1800025ec  mov     [rbp+0FFE0h+pRequest.OptionalArguments], rax
0x1800025f0  movups  xmmword ptr [rbp+0FFE0h+pRequest.DesiredAccess], xmm0
0x1800025f4  mov     [rsp+100E0h+phAuthzResourceManager], rbx
0x1800025f9  mov     rsi, r9
0x1800025fc  movups  xmmword ptr [rbp+0FFE0h+pRequest.ObjectTypeList], xmm0
0x180002600  mov     [rsp+100E0h+phAuthzClientContext], rbx
0x180002605  movups  xmmword ptr [rsp+100E0h+pReply.ResultListLength], xmm0
0x18000260a  mov     [rsp+100E0h+TokenHandle], rbx
0x18000260f  movups  xmmword ptr [rbp+0FFE0h+pReply.SaclEvaluationResults], xmm0
0x180002613  mov     [r9], ebx
0x180002616  call    cs:__imp_ExpandEnvironmentStringsW
0x18000261d  nop     dword ptr [rax+rax+00h]
0x180002622  test    eax, eax
0x180002624  jnz     short loc_18000263B
0x180002626  call    cs:__imp_GetLastError
0x18000262d  nop     dword ptr [rax+rax+00h]
0x180002632  mov     [rsp+100E0h+var_10090], eax
0x180002636  jmp     loc_1800027A5
0x18000263b  xor     ecx, ecx; BindingHandle
0x18000263d  call    cs:__imp_RpcImpersonateClient
0x180002644  nop     dword ptr [rax+rax+00h]
0x180002649  xor     r9d, r9d; ppsidOwner
0x18000264c  lea     rcx, [rbp+0FFE0h+Dst]; pObjectName
0x180002650  mov     edi, eax
0x180002652  lea     rax, [rsp+100E0h+pSecurityDescriptor]
0x180002657  mov     [rsp+100E0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18000265c  mov     [rsp+100E0h+ppSacl], rbx; ppSacl
0x180002661  mov     [rsp+100E0h+ppDacl], rbx; ppDacl
0x180002666  lea     edx, [r9+1]; ObjectType
0x18000266a  lea     r8d, [r9+5]; SecurityInfo
0x18000266e  mov     [rsp+100E0h+ppsidGroup], rbx; ppsidGroup
0x180002673  call    cs:__imp_GetNamedSecurityInfoW
0x18000267a  nop     dword ptr [rax+rax+00h]
0x18000267f  mov     [rsp+100E0h+var_10090], eax
0x180002683  test    edi, edi
0x180002685  jnz     short loc_180002693
0x180002687  call    cs:__imp_RpcRevertToSelf
0x18000268e  nop     dword ptr [rax+rax+00h]
0x180002693  cmp     [rsp+100E0h+var_10090], ebx
0x180002697  jnz     loc_1800027A5
0x18000269d  call    cs:__imp_GetCurrentProcess
0x1800026a4  nop     dword ptr [rax+rax+00h]
0x1800026a9  lea     r8, [rsp+100E0h+TokenHandle]; TokenHandle
0x1800026ae  mov     edx, 20008h; DesiredAccess
0x1800026b3  mov     rcx, rax; ProcessHandle
0x1800026b6  call    cs:__imp_OpenProcessToken
0x1800026bd  nop     dword ptr [rax+rax+00h]
0x1800026c2  test    eax, eax
0x1800026c4  jz      loc_180002626
0x1800026ca  lea     rax, [rsp+100E0h+phAuthzResourceManager]
0x1800026cf  xor     r9d, r9d; pfnFreeDynamicGroups
0x1800026d2  mov     [rsp+100E0h+ppDacl], rax; phAuthzResourceManager
0x1800026d7  xor     r8d, r8d; pfnComputeDynamicGroups
0x1800026da  xor     edx, edx; pfnDynamicAccessCheck
0x1800026dc  mov     [rsp+100E0h+ppsidGroup], rbx; szResourceManagerName
0x1800026e1  xor     ecx, ecx; Flags
0x1800026e3  call    cs:__imp_AuthzInitializeResourceManager
0x1800026ea  nop     dword ptr [rax+rax+00h]
0x1800026ef  test    eax, eax
0x1800026f1  jz      loc_180002626
0x1800026f7  mov     r8, [rsp+100E0h+phAuthzResourceManager]; hAuthzResourceManager
0x1800026fc  lea     rax, [rsp+100E0h+phAuthzClientContext]
0x180002701  mov     rdx, [rsp+100E0h+TokenHandle]; TokenHandle
0x180002706  xor     r9d, r9d; pExpirationTime
0x180002709  mov     [rsp+100E0h+ppSacl], rax; phAuthzClientContext
0x18000270e  xor     ecx, ecx; Flags
0x180002710  mov     [rsp+100E0h+ppDacl], rbx; DynamicGroupArgs
0x180002715  mov     [rsp+100E0h+ppsidGroup], rbx; Identifier
0x18000271a  call    cs:__imp_AuthzInitializeContextFromToken
0x180002721  nop     dword ptr [rax+rax+00h]
0x180002726  test    eax, eax
0x180002728  jz      loc_180002626
0x18000272e  mov     rdx, [rsp+100E0h+phAuthzClientContext]; hAuthzClientContext
0x180002733  lea     rax, [rsp+100E0h+var_1008C]
0x180002738  mov     [rbp+0FFE0h+pReply.GrantedAccessMask], rax
0x18000273c  lea     r8, [rbp+0FFE0h+pRequest]; pRequest
0x180002740  mov     [rsp+100E0h+phAccessCheckResults], rbx; phAccessCheckResults
0x180002745  lea     rax, [rsp+100E0h+var_10090]
0x18000274a  mov     [rbp+0FFE0h+pReply.Error], rax
0x18000274e  xor     r9d, r9d; hAuditEvent
0x180002751  lea     rax, [rsp+100E0h+pReply]
0x180002756  mov     [rbp+0FFE0h+pRequest.DesiredAccess], 117h
0x18000275d  mov     [rsp+100E0h+ppSecurityDescriptor], rax; pReply
0x180002762  xor     ecx, ecx; Flags
0x180002764  mov     rax, [rsp+100E0h+pSecurityDescriptor]
0x180002769  mov     dword ptr [rsp+100E0h+ppSacl], ebx; OptionalSecurityDescriptorCount
0x18000276d  mov     [rsp+100E0h+ppDacl], rbx; OptionalSecurityDescriptorArray
0x180002772  mov     [rsp+100E0h+ppsidGroup], rax; pSecurityDescriptor
0x180002777  mov     [rsp+100E0h+pReply.ResultListLength], 1
0x18000277f  call    cs:__imp_AuthzAccessCheck
0x180002786  nop     dword ptr [rax+rax+00h]
0x18000278b  test    eax, eax
0x18000278d  jz      loc_180002626
0x180002793  cmp     [rsp+100E0h+var_10090], ebx
0x180002797  jnz     short loc_1800027A1
0x180002799  mov     dword ptr [rsi], 1
0x18000279f  jmp     short loc_1800027A5
0x1800027a1  mov     [rsp+100E0h+var_10090], ebx
0x1800027a5  mov     rcx, [rsp+100E0h+TokenHandle]; hObject
0x1800027aa  test    rcx, rcx
0x1800027ad  jz      short loc_1800027BB
0x1800027af  call    cs:__imp_CloseHandle
0x1800027b6  nop     dword ptr [rax+rax+00h]
0x1800027bb  mov     rcx, [rsp+100E0h+pSecurityDescriptor]; hMem
0x1800027c0  test    rcx, rcx
0x1800027c3  jz      short loc_1800027D1
0x1800027c5  call    cs:__imp_LocalFree
0x1800027cc  nop     dword ptr [rax+rax+00h]
0x1800027d1  mov     rcx, [rsp+100E0h+phAuthzResourceManager]; hAuthzResourceManager
0x1800027d6  test    rcx, rcx
0x1800027d9  jz      short loc_1800027E7
0x1800027db  call    cs:__imp_AuthzFreeResourceManager
0x1800027e2  nop     dword ptr [rax+rax+00h]
0x1800027e7  mov     rcx, [rsp+100E0h+phAuthzClientContext]; hAuthzClientContext
0x1800027ec  test    rcx, rcx
0x1800027ef  jz      short loc_1800027FD
0x1800027f1  call    cs:__imp_AuthzFreeContext
0x1800027f8  nop     dword ptr [rax+rax+00h]
0x1800027fd  mov     eax, [rsp+100E0h+var_10090]
0x180002801  mov     rcx, [rbp+0FFE0h+var_20]
0x180002808  xor     rcx, rsp; StackCookie
0x18000280b  call    __security_check_cookie
0x180002810  mov     rbx, [rsp+100E0h+arg_8]
0x180002818  add     rsp, 100D0h
0x18000281f  pop     rdi
0x180002820  pop     rsi
0x180002821  pop     rbp
0x180002822  retn
```
