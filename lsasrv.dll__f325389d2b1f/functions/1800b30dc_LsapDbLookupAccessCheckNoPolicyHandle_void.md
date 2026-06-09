# LsapDbLookupAccessCheckNoPolicyHandle(void)

- ea: `0x1800b30dc`
- end: `0x1800b331e`
- name: `?LsapDbLookupAccessCheckNoPolicyHandle@@YAJXZ`
- size: `578`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ddc0`
- `0x18000f8f0`
- `0x1800101e0`

## callees

- `0x1800b30dc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800b3185`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800b3185`
- `ntdll!NtClose` at `0x1800b32ce`
- `ntdll!NtClose` at `0x1800b32ce`
- `ntdll!NtOpenThreadToken` at `0x1800b31de`
- `ntdll!NtOpenThreadToken` at `0x1800b31de`
- `RPCRT4!RpcRevertToSelf` at `0x1800b31ee`
- `RPCRT4!RpcRevertToSelf` at `0x1800b32de`
- `RPCRT4!RpcRevertToSelf` at `0x1800b31ee`
- `RPCRT4!RpcRevertToSelf` at `0x1800b32de`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800b31af`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800b31fc`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800b32ec`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800b31af`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800b31fc`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800b32ec`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x1800b313b`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x1800b313b`
- `RPCRT4!RpcImpersonateClient` at `0x1800b31a1`
- `RPCRT4!RpcImpersonateClient` at `0x1800b31a1`
- `AUTHZ!AuthzInitializeContextFromToken` at `0x1800b3235`
- `AUTHZ!AuthzInitializeContextFromToken` at `0x1800b3235`
- `AUTHZ!AuthzFreeContext` at `0x1800b3303`
- `AUTHZ!AuthzFreeContext` at `0x1800b3303`
- `AUTHZ!AuthzAccessCheck` at `0x1800b32a2`
- `AUTHZ!AuthzAccessCheck` at `0x1800b32a2`

## pseudocode

```c
__int64 LsapDbLookupAccessCheckNoPolicyHandle(void)
{
  int v0; // edi
  unsigned int v1; // ebx
  RPC_STATUS v2; // eax
  RPC_STATUS v3; // eax
  RPC_STATUS v4; // eax
  void *TokenHandle; // [rsp+50h] [rbp-29h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+58h] [rbp-21h] BYREF
  LUID Identifier; // [rsp+60h] [rbp-19h]
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+68h] [rbp-11h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+88h] [rbp+Fh] BYREF
  unsigned int AuthnLevel; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int AuthnSvc; // [rsp+E8h] [rbp+6Fh] BYREF
  int v13; // [rsp+F0h] [rbp+77h] BYREF
  int v14; // [rsp+F8h] [rbp+7Fh] BYREF

  AuthnLevel = 0;
  AuthnSvc = 0;
  TokenHandle = 0;
  v0 = 0;
  hAuthzClientContext = 0;
  Identifier = 0;
  memset(&pRequest, 0, sizeof(pRequest));
  v13 = 0;
  v14 = 0;
  memset(&pReply, 0, sizeof(pReply));
  if ( RpcBindingInqAuthClientW(0, 0, 0, &AuthnLevel, &AuthnSvc, 0) || AuthnLevel < 5 || AuthnSvc != 68 )
  {
    if ( LsapProductType == NtProductLanManNt )
    {
      if ( InitOnceExecuteOnce(&g_LsapLookupAccessCheckInitOnce, LsapInitializeLookupAuthzOnce, 0, 0) )
      {
        v2 = RpcImpersonateClient(0);
        if ( I_RpcMapWin32Status(v2) >= 0
          && (v0 = 1, NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle) >= 0)
          && (v3 = RpcRevertToSelf(), I_RpcMapWin32Status(v3) >= 0)
          && (v0 = 0,
              AuthzInitializeContextFromToken(0, TokenHandle, LsaLookupAuthzRM, 0, Identifier, 0, &hAuthzClientContext)) )
        {
          pReply.GrantedAccessMask = (PACCESS_MASK)&v13;
          pReply.Error = (PDWORD)&v14;
          pRequest.DesiredAccess = 2048;
          pRequest.OptionalArguments = 0;
          memset(&pRequest.PrincipalSelfSid, 0, 20);
          pReply.ResultListLength = 1;
          v1 = -1073741790;
          if ( AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, g_LsapComputerGroupsSD, 0, 0, &pReply, 0) )
            v1 = *pReply.Error != 0 ? 0xC0000022 : 0;
        }
        else
        {
          v1 = -1073741790;
        }
      }
      else
      {
        v1 = -1073741801;
      }
    }
    else
    {
      v1 = -1073741604;
    }
  }
  else
  {
    v1 = 0;
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( v0 )
  {
    v4 = RpcRevertToSelf();
    v1 = I_RpcMapWin32Status(v4);
  }
  if ( hAuthzClientContext )
    AuthzFreeContext(hAuthzClientContext);
  return v1;
}

```

## disassembly

```asm
0x1800b30dc  push    rbp
0x1800b30de  push    rbx
0x1800b30df  push    rsi
0x1800b30e0  push    rdi
0x1800b30e1  lea     rbp, [rsp-3Fh]
0x1800b30e6  sub     rsp, 0B8h
0x1800b30ed  xor     esi, esi
0x1800b30ef  lea     r9, [rbp+57h+AuthnLevel]; AuthnLevel
0x1800b30f3  xorps   xmm0, xmm0
0x1800b30f6  mov     [rsp+0D0h+AuthzSvc], rsi; AuthzSvc
0x1800b30fb  xor     eax, eax
0x1800b30fd  mov     [rbp+57h+AuthnLevel], esi
0x1800b3100  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x1800b3104  xor     r8d, r8d; ServerPrincName
0x1800b3107  lea     rax, [rbp+57h+arg_8]
0x1800b310b  mov     [rbp+57h+arg_8], esi
0x1800b310e  xor     edx, edx; Privs
0x1800b3110  mov     [rsp+0D0h+AuthnSvc], rax; AuthnSvc
0x1800b3115  xor     ecx, ecx; ClientBinding
0x1800b3117  mov     [rbp+57h+TokenHandle], rsi
0x1800b311b  mov     edi, esi
0x1800b311d  mov     [rbp+57h+hAuthzClientContext], rsi
0x1800b3121  mov     qword ptr [rbp+57h+Identifier.LowPart], rsi
0x1800b3125  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x1800b3129  mov     [rbp+57h+arg_10], esi
0x1800b312c  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x1800b3130  mov     [rbp+57h+arg_18], esi
0x1800b3133  movups  xmmword ptr [rbp+57h+var_68.ResultListLength], xmm0
0x1800b3137  movups  xmmword ptr [rbp+57h+var_68.SaclEvaluationResults], xmm0
0x1800b313b  call    cs:__imp_RpcBindingInqAuthClientW
0x1800b3142  nop     dword ptr [rax+rax+00h]
0x1800b3147  test    eax, eax
0x1800b3149  jnz     short loc_1800B315E
0x1800b314b  cmp     [rbp+57h+AuthnLevel], 5
0x1800b314f  jb      short loc_1800B315E
0x1800b3151  cmp     [rbp+57h+arg_8], 44h ; 'D'
0x1800b3155  jnz     short loc_1800B315E
0x1800b3157  mov     ebx, esi
0x1800b3159  jmp     loc_1800B32C5
0x1800b315e  cmp     cs:LsapProductType, 2
0x1800b3165  jz      short loc_1800B3171
0x1800b3167  mov     ebx, 0C00000DCh
0x1800b316c  jmp     loc_1800B32C5
0x1800b3171  xor     r9d, r9d; Context
0x1800b3174  lea     rdx, ?LsapInitializeLookupAuthzOnce@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800b317b  xor     r8d, r8d; Parameter
0x1800b317e  lea     rcx, ?g_LsapLookupAccessCheckInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800b3185  call    cs:__imp_InitOnceExecuteOnce
0x1800b318c  nop     dword ptr [rax+rax+00h]
0x1800b3191  test    eax, eax
0x1800b3193  jnz     short loc_1800B319F
0x1800b3195  mov     ebx, 0C0000017h
0x1800b319a  jmp     loc_1800B32C5
0x1800b319f  xor     ecx, ecx; BindingHandle
0x1800b31a1  call    cs:__imp_RpcImpersonateClient
0x1800b31a8  nop     dword ptr [rax+rax+00h]
0x1800b31ad  mov     ecx, eax; Status
0x1800b31af  call    cs:__imp_I_RpcMapWin32Status
0x1800b31b6  nop     dword ptr [rax+rax+00h]
0x1800b31bb  test    eax, eax
0x1800b31bd  jns     short loc_1800B31C9
0x1800b31bf  mov     ebx, 0C0000022h
0x1800b31c4  jmp     loc_1800B32C5
0x1800b31c9  mov     ebx, 1
0x1800b31ce  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800b31d2  xor     r8d, r8d; OpenAsSelf
0x1800b31d5  mov     edi, ebx
0x1800b31d7  lea     edx, [rbx+7]; DesiredAccess
0x1800b31da  lea     rcx, [r8-2]; ThreadHandle
0x1800b31de  call    cs:__imp_NtOpenThreadToken
0x1800b31e5  nop     dword ptr [rax+rax+00h]
0x1800b31ea  test    eax, eax
0x1800b31ec  js      short loc_1800B31BF
0x1800b31ee  call    cs:__imp_RpcRevertToSelf
0x1800b31f5  nop     dword ptr [rax+rax+00h]
0x1800b31fa  mov     ecx, eax; Status
0x1800b31fc  call    cs:__imp_I_RpcMapWin32Status
0x1800b3203  nop     dword ptr [rax+rax+00h]
0x1800b3208  test    eax, eax
0x1800b320a  js      short loc_1800B31BF
0x1800b320c  mov     r8, cs:?LsaLookupAuthzRM@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA; hAuthzResourceManager
0x1800b3213  lea     rax, [rbp+57h+hAuthzClientContext]
0x1800b3217  mov     rdx, [rbp+57h+TokenHandle]; TokenHandle
0x1800b321b  xor     r9d, r9d; pExpirationTime
0x1800b321e  mov     [rsp+0D0h+phAuthzClientContext], rax; phAuthzClientContext
0x1800b3223  xor     ecx, ecx; Flags
0x1800b3225  mov     rax, qword ptr [rbp+57h+Identifier.LowPart]
0x1800b3229  mov     edi, esi
0x1800b322b  mov     [rsp+0D0h+AuthzSvc], rsi; DynamicGroupArgs
0x1800b3230  mov     [rsp+0D0h+AuthnSvc], rax; Identifier
0x1800b3235  call    cs:__imp_AuthzInitializeContextFromToken
0x1800b323c  nop     dword ptr [rax+rax+00h]
0x1800b3241  test    eax, eax
0x1800b3243  jz      loc_1800B31BF
0x1800b3249  mov     rdx, [rbp+57h+hAuthzClientContext]; hAuthzClientContext
0x1800b324d  lea     rax, [rbp+57h+arg_10]
0x1800b3251  mov     [rbp+57h+var_68.GrantedAccessMask], rax
0x1800b3255  lea     r8, [rbp+57h+pRequest]; pRequest
0x1800b3259  mov     [rsp+0D0h+phAccessCheckResults], rsi; phAccessCheckResults
0x1800b325e  lea     rax, [rbp+57h+arg_18]
0x1800b3262  mov     [rbp+57h+var_68.Error], rax
0x1800b3266  xor     r9d, r9d; hAuditEvent
0x1800b3269  lea     rax, [rbp+57h+var_68]
0x1800b326d  mov     [rbp+57h+pRequest.DesiredAccess], 800h
0x1800b3274  mov     [rsp+0D0h+pReply], rax; pReply
0x1800b3279  xor     ecx, ecx; Flags
0x1800b327b  mov     rax, cs:?g_LsapComputerGroupsSD@@3PEAXEA; void * g_LsapComputerGroupsSD
0x1800b3282  mov     dword ptr [rsp+0D0h+phAuthzClientContext], esi; OptionalSecurityDescriptorCount
0x1800b3286  mov     [rsp+0D0h+AuthzSvc], rsi; OptionalSecurityDescriptorArray
0x1800b328b  mov     [rsp+0D0h+AuthnSvc], rax; pSecurityDescriptor
0x1800b3290  mov     [rbp+57h+pRequest.ObjectTypeList], rsi
0x1800b3294  mov     [rbp+57h+pRequest.ObjectTypeListLength], esi
0x1800b3297  mov     [rbp+57h+pRequest.OptionalArguments], rsi
0x1800b329b  mov     [rbp+57h+pRequest.PrincipalSelfSid], rsi
0x1800b329f  mov     [rbp+57h+var_68.ResultListLength], ebx
0x1800b32a2  call    cs:__imp_AuthzAccessCheck
0x1800b32a9  nop     dword ptr [rax+rax+00h]
0x1800b32ae  mov     ebx, 0C0000022h
0x1800b32b3  test    eax, eax
0x1800b32b5  jz      short loc_1800B32C5
0x1800b32b7  mov     rax, [rbp+57h+var_68.Error]
0x1800b32bb  mov     ecx, esi
0x1800b32bd  sub     ecx, [rax]
0x1800b32bf  neg     ecx
0x1800b32c1  sbb     eax, eax
0x1800b32c3  and     ebx, eax
0x1800b32c5  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800b32c9  test    rcx, rcx
0x1800b32cc  jz      short loc_1800B32DA
0x1800b32ce  call    cs:__imp_NtClose
0x1800b32d5  nop     dword ptr [rax+rax+00h]
0x1800b32da  test    edi, edi
0x1800b32dc  jz      short loc_1800B32FA
0x1800b32de  call    cs:__imp_RpcRevertToSelf
0x1800b32e5  nop     dword ptr [rax+rax+00h]
0x1800b32ea  mov     ecx, eax; Status
0x1800b32ec  call    cs:__imp_I_RpcMapWin32Status
0x1800b32f3  nop     dword ptr [rax+rax+00h]
0x1800b32f8  mov     ebx, eax
0x1800b32fa  mov     rcx, [rbp+57h+hAuthzClientContext]; hAuthzClientContext
0x1800b32fe  test    rcx, rcx
0x1800b3301  jz      short loc_1800B330F
0x1800b3303  call    cs:__imp_AuthzFreeContext
0x1800b330a  nop     dword ptr [rax+rax+00h]
0x1800b330f  mov     eax, ebx
0x1800b3311  add     rsp, 0B8h
0x1800b3318  pop     rdi
0x1800b3319  pop     rsi
0x1800b331a  pop     rbx
0x1800b331b  pop     rbp
0x1800b331c  retn
```
