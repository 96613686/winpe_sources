# DfsApiInit(void)

- ea: `0x140002a28`
- end: `0x140002cc5`
- name: `?DfsApiInit@@YAKXZ`
- size: `669`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140018e88`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140002a28`
- `0x14001ab6c`
- `0x14001ac74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002ab5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002bf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002ab5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002bf6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140002bca`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140002bca`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140002bb1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140002bb1`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140002b98`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140002b98`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140002b52`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140002b75`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140002b52`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140002b75`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140002b2f`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140002b2f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140002aec`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140002afd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140002aec`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140002afd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140002aa5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140002ad9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140002aa5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140002ad9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140002be6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140002be6`
- `RPCRT4!RpcServerRegisterIf` at `0x140002c82`
- `RPCRT4!RpcServerRegisterIf` at `0x140002c82`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x140002c64`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x140002c64`
- `RPCRT4!RpcServerListen` at `0x140002ca3`
- `RPCRT4!RpcServerListen` at `0x140002ca3`

## pseudocode

```c
__int64 DfsApiInit(void)
{
  struct _ACL *v0; // rdi
  void *v1; // rbp
  int LastError; // ebx
  void *v3; // rsi
  DWORD LengthSid; // ebx
  DWORD v5; // ebx
  struct _ACL *v6; // rax
  DWORD cbSid; // [rsp+40h] [rbp+8h] BYREF

  cbSid = 0;
  RpcAllocator = MIDL_user_allocate;
  v0 = 0;
  qword_140071340 = (__int64)MIDL_user_free;
  DfsCreateNetDfsApiPerfCtrInstances();
  v1 = operator new(0x44u);
  if ( !v1 )
  {
    LastError = 8;
LABEL_23:
    DfsDeleteNetDfsApiPerfCtrInstances();
    return (unsigned int)LastError;
  }
  v3 = operator new(0x44u);
  if ( !v3 )
  {
    LastError = 8;
    goto LABEL_18;
  }
  cbSid = 68;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v1, &cbSid)
    || (cbSid = 68, !CreateWellKnownSid(WinAuthenticatedUserSid, 0, v3, &cbSid)) )
  {
    LastError = GetLastError();
    goto LABEL_18;
  }
  LengthSid = GetLengthSid(v3);
  v5 = GetLengthSid(v1) + 32 + LengthSid;
  v6 = (struct _ACL *)operator new(v5);
  v0 = v6;
  if ( !v6 )
  {
LABEL_17:
    LastError = 1336;
    goto LABEL_18;
  }
  if ( !InitializeAcl(v6, v5, 2u)
    || !AddAccessAllowedAce(v0, 2u, 0x12019Bu, v3)
    || !AddAccessAllowedAce(v0, 2u, 0x1201BFu, v1)
    || !InitializeSecurityDescriptor(&DfsRpcSecurityDesc, 1u)
    || !SetSecurityDescriptorOwner(&DfsRpcSecurityDesc, v1, 0)
    || !SetSecurityDescriptorGroup(&DfsRpcSecurityDesc, v1, 0)
    || !SetSecurityDescriptorDacl(&DfsRpcSecurityDesc, 1, v0, 0) )
  {
    LastError = GetLastError();
    if ( LastError < 0 )
      goto LABEL_18;
    goto LABEL_17;
  }
  LastError = RpcServerUseProtseqEpW((RPC_WSTR)L"ncacn_np", 0x4D2u, (RPC_WSTR)L"\\pipe\\netdfs", &DfsRpcSecurityDesc);
  if ( !LastError )
  {
    LastError = RpcServerRegisterIf(qword_14005FE50, 0, 0);
    if ( !LastError )
    {
      LastError = RpcServerListen(1u, 0x4D2u, 1u);
      if ( !LastError )
        ServerListen = 1;
    }
  }
LABEL_18:
  operator delete(v1);
  if ( v3 )
    operator delete(v3);
  if ( v0 )
    operator delete(v0);
  if ( LastError )
    goto LABEL_23;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140002a28  mov     [rsp+arg_8], rbx
0x140002a2d  mov     [rsp+arg_10], rbp
0x140002a32  push    rsi
0x140002a33  push    rdi
0x140002a34  push    r14
0x140002a36  sub     rsp, 20h
0x140002a3a  and     [rsp+38h+cbSid], 0
0x140002a3f  lea     rax, MIDL_user_allocate
0x140002a46  mov     cs:?RpcAllocator@@3U_HEAP_ALLOCATOR@@A, rax; _HEAP_ALLOCATOR RpcAllocator
0x140002a4d  xor     edi, edi
0x140002a4f  lea     rax, MIDL_user_free
0x140002a56  mov     cs:qword_140071340, rax
0x140002a5d  call    ?DfsCreateNetDfsApiPerfCtrInstances@@YAXXZ; DfsCreateNetDfsApiPerfCtrInstances(void)
0x140002a62  lea     ebx, [rdi+44h]
0x140002a65  mov     ecx, ebx; Size
0x140002a67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002a6c  mov     rbp, rax
0x140002a6f  test    rax, rax
0x140002a72  jnz     short loc_140002A7C
0x140002a74  lea     ebx, [rdi+8]
0x140002a77  jmp     loc_140002C33
0x140002a7c  mov     rcx, rbx; Size
0x140002a7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002a84  mov     rsi, rax
0x140002a87  test    rax, rax
0x140002a8a  jnz     short loc_140002A94
0x140002a8c  lea     ebx, [rax+8]
0x140002a8f  jmp     loc_140002C0D
0x140002a94  xor     edx, edx; DomainSid
0x140002a96  mov     [rsp+38h+cbSid], ebx
0x140002a9a  lea     r9, [rsp+38h+cbSid]; cbSid
0x140002a9f  mov     r8, rbp; pSid
0x140002aa2  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x140002aa5  call    cs:__imp_CreateWellKnownSid
0x140002aac  nop     dword ptr [rax+rax+00h]
0x140002ab1  test    eax, eax
0x140002ab3  jnz     short loc_140002AC8
0x140002ab5  call    cs:__imp_GetLastError
0x140002abc  nop     dword ptr [rax+rax+00h]
0x140002ac1  mov     ebx, eax
0x140002ac3  jmp     loc_140002C0D
0x140002ac8  xor     edx, edx; DomainSid
0x140002aca  mov     [rsp+38h+cbSid], ebx
0x140002ace  lea     r9, [rsp+38h+cbSid]; cbSid
0x140002ad3  mov     r8, rsi; pSid
0x140002ad6  lea     ecx, [rdx+11h]; WellKnownSidType
0x140002ad9  call    cs:__imp_CreateWellKnownSid
0x140002ae0  nop     dword ptr [rax+rax+00h]
0x140002ae5  test    eax, eax
0x140002ae7  jz      short loc_140002AB5
0x140002ae9  mov     rcx, rsi; pSid
0x140002aec  call    cs:__imp_GetLengthSid
0x140002af3  nop     dword ptr [rax+rax+00h]
0x140002af8  mov     rcx, rbp; pSid
0x140002afb  mov     ebx, eax
0x140002afd  call    cs:__imp_GetLengthSid
0x140002b04  nop     dword ptr [rax+rax+00h]
0x140002b09  add     eax, 20h ; ' '
0x140002b0c  add     ebx, eax
0x140002b0e  mov     ecx, ebx; Size
0x140002b10  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002b15  mov     rdi, rax
0x140002b18  test    rax, rax
0x140002b1b  jz      loc_140002C08
0x140002b21  mov     r14d, 2
0x140002b27  mov     edx, ebx; nAclLength
0x140002b29  mov     r8d, r14d; dwAclRevision
0x140002b2c  mov     rcx, rax; pAcl
0x140002b2f  call    cs:__imp_InitializeAcl
0x140002b36  nop     dword ptr [rax+rax+00h]
0x140002b3b  test    eax, eax
0x140002b3d  jz      loc_140002BF6
0x140002b43  mov     r9, rsi; pSid
0x140002b46  mov     r8d, 12019Bh; AccessMask
0x140002b4c  mov     edx, r14d; dwAceRevision
0x140002b4f  mov     rcx, rdi; pAcl
0x140002b52  call    cs:__imp_AddAccessAllowedAce
0x140002b59  nop     dword ptr [rax+rax+00h]
0x140002b5e  test    eax, eax
0x140002b60  jz      loc_140002BF6
0x140002b66  mov     r9, rbp; pSid
0x140002b69  mov     r8d, 1201BFh; AccessMask
0x140002b6f  mov     edx, r14d; dwAceRevision
0x140002b72  mov     rcx, rdi; pAcl
0x140002b75  call    cs:__imp_AddAccessAllowedAce
0x140002b7c  nop     dword ptr [rax+rax+00h]
0x140002b81  test    eax, eax
0x140002b83  jz      short loc_140002BF6
0x140002b85  mov     r14d, 1
0x140002b8b  lea     rbx, ?DfsRpcSecurityDesc@@3U_SECURITY_DESCRIPTOR@@A; _SECURITY_DESCRIPTOR DfsRpcSecurityDesc
0x140002b92  mov     edx, r14d; dwRevision
0x140002b95  mov     rcx, rbx; pSecurityDescriptor
0x140002b98  call    cs:__imp_InitializeSecurityDescriptor
0x140002b9f  nop     dword ptr [rax+rax+00h]
0x140002ba4  test    eax, eax
0x140002ba6  jz      short loc_140002BF6
0x140002ba8  xor     r8d, r8d; bOwnerDefaulted
0x140002bab  mov     rdx, rbp; pOwner
0x140002bae  mov     rcx, rbx; pSecurityDescriptor
0x140002bb1  call    cs:__imp_SetSecurityDescriptorOwner
0x140002bb8  nop     dword ptr [rax+rax+00h]
0x140002bbd  test    eax, eax
0x140002bbf  jz      short loc_140002BF6
0x140002bc1  xor     r8d, r8d; bGroupDefaulted
0x140002bc4  mov     rdx, rbp; pGroup
0x140002bc7  mov     rcx, rbx; pSecurityDescriptor
0x140002bca  call    cs:__imp_SetSecurityDescriptorGroup
0x140002bd1  nop     dword ptr [rax+rax+00h]
0x140002bd6  test    eax, eax
0x140002bd8  jz      short loc_140002BF6
0x140002bda  xor     r9d, r9d; bDaclDefaulted
0x140002bdd  mov     r8, rdi; pDacl
0x140002be0  mov     edx, r14d; bDaclPresent
0x140002be3  mov     rcx, rbx; pSecurityDescriptor
0x140002be6  call    cs:__imp_SetSecurityDescriptorDacl
0x140002bed  nop     dword ptr [rax+rax+00h]
0x140002bf2  test    eax, eax
0x140002bf4  jnz     short loc_140002C4E
0x140002bf6  call    cs:__imp_GetLastError
0x140002bfd  nop     dword ptr [rax+rax+00h]
0x140002c02  mov     ebx, eax
0x140002c04  test    eax, eax
0x140002c06  js      short loc_140002C0D
0x140002c08  mov     ebx, 538h
0x140002c0d  mov     rcx, rbp; Block
0x140002c10  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002c15  test    rsi, rsi
0x140002c18  jz      short loc_140002C22
0x140002c1a  mov     rcx, rsi; Block
0x140002c1d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002c22  test    rdi, rdi
0x140002c25  jz      short loc_140002C2F
0x140002c27  mov     rcx, rdi; Block
0x140002c2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002c2f  test    ebx, ebx
0x140002c31  jz      short loc_140002C38
0x140002c33  call    ?DfsDeleteNetDfsApiPerfCtrInstances@@YAXXZ; DfsDeleteNetDfsApiPerfCtrInstances(void)
0x140002c38  mov     rbp, [rsp+38h+arg_10]
0x140002c3d  mov     eax, ebx
0x140002c3f  mov     rbx, [rsp+38h+arg_8]
0x140002c44  add     rsp, 20h
0x140002c48  pop     r14
0x140002c4a  pop     rdi
0x140002c4b  pop     rsi
0x140002c4c  retn
0x140002c4e  mov     r9, rbx; SecurityDescriptor
0x140002c51  lea     r8, Endpoint; "\\pipe\\netdfs"
0x140002c58  mov     edx, 4D2h; MaxCalls
0x140002c5d  lea     rcx, Protseq; "ncacn_np"
0x140002c64  call    cs:__imp_RpcServerUseProtseqEpW
0x140002c6b  nop     dword ptr [rax+rax+00h]
0x140002c70  mov     ebx, eax
0x140002c72  test    eax, eax
0x140002c74  jnz     short loc_140002C0D
0x140002c76  xor     r8d, r8d; MgrEpv
0x140002c79  lea     rcx, qword_14005FE50; IfSpec
0x140002c80  xor     edx, edx; MgrTypeUuid
0x140002c82  call    cs:__imp_RpcServerRegisterIf
0x140002c89  nop     dword ptr [rax+rax+00h]
0x140002c8e  mov     ebx, eax
0x140002c90  test    eax, eax
0x140002c92  jnz     loc_140002C0D
0x140002c98  mov     r8d, r14d; DontWait
0x140002c9b  mov     edx, 4D2h; MaxCalls
0x140002ca0  mov     ecx, r14d; MinimumCallThreads
0x140002ca3  call    cs:__imp_RpcServerListen
0x140002caa  nop     dword ptr [rax+rax+00h]
0x140002caf  mov     ebx, eax
0x140002cb1  test    eax, eax
0x140002cb3  jnz     loc_140002C0D
0x140002cb9  mov     cs:?ServerListen@@3HA, r14d; int ServerListen
0x140002cc0  jmp     loc_140002C0D
```
