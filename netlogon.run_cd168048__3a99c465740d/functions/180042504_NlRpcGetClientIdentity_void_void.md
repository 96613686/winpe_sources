# NlRpcGetClientIdentity(void *,void * *)

- ea: `0x180042504`
- end: `0x1800426a7`
- name: `?NlRpcGetClientIdentity@@YAJPEAXPEAPEAX@Z`
- size: `419`
- prototype: `__int64 __fastcall(void *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800426b0`

## callees

- `0x180003320`
- `0x180007518`
- `0x180042504`
- `0x18005448c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180042662`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180042662`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042687`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042687`
- `RPCRT4!RpcImpersonateClient` at `0x180042528`
- `RPCRT4!RpcImpersonateClient` at `0x180042528`
- `RPCRT4!RpcRevertToSelf` at `0x18004256d`
- `RPCRT4!RpcRevertToSelf` at `0x18004256d`
- `ntdll!NtOpenThreadToken` at `0x180042549`
- `ntdll!NtOpenThreadToken` at `0x180042549`
- `ntdll!NtQueryInformationToken` at `0x1800425ba`
- `ntdll!NtQueryInformationToken` at `0x1800425fa`
- `ntdll!NtQueryInformationToken` at `0x1800425ba`
- `ntdll!NtQueryInformationToken` at `0x1800425fa`
- `netutils!NetApiBufferFree` at `0x180042671`
- `netutils!NetApiBufferFree` at `0x180042671`

## string_xrefs

- `0x18004255c`: `NlRpcGetClientIdentity: NtOpenThreadToken failed Status:0x%x\n`
- `0x18004257e`: `NlRpcGetClientIdentity: RpcImpersonate failed RpcStatus:0x%x\n`
- `0x18004260d`: `NlRpcGetClientIdentity: NtQueryInformationToken(2) failed Status:0x%x\n`
- `0x18004263e`: `NlRpcGetClientIdentity: failed to allocate TokenUserInfo TokenUserInfoSize:0x%x\n`
- `0x18004264a`: `NlRpcGetClientIdentity: NtQueryInformationToken(1) failed Status:0x%x\n`

## pseudocode

```c
__int64 __fastcall NlRpcGetClientIdentity(void *a1, void **a2)
{
  PSID *v2; // rbx
  unsigned int v4; // eax
  unsigned int v5; // edi
  NTSTATUS v6; // eax
  unsigned int v7; // eax
  NTSTATUS v8; // eax
  void *v9; // rax
  ULONG TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  *a2 = 0;
  v4 = RpcImpersonateClient(a1);
  v5 = v4;
  if ( v4 )
  {
    NlPrintRoutine(0x100u, L"NlRpcGetClientIdentity: RpcImpersonate failed RpcStatus:0x%x\n", v4);
  }
  else
  {
    v6 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
    if ( v6 < 0 )
      NlPrintRoutine(0x100u, L"NlRpcGetClientIdentity: NtOpenThreadToken failed Status:0x%x\n", (unsigned int)v6);
    RpcRevertToSelf();
  }
  if ( TokenHandle )
  {
    v7 = NtQueryInformationToken(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( v7 == -1073741789 )
    {
      v2 = (PSID *)NetpMemoryAllocate(TokenInformationLength);
      if ( v2 )
      {
        v8 = NtQueryInformationToken(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength);
        if ( v8 < 0 )
          NlPrintRoutine(
            0x100u,
            L"NlRpcGetClientIdentity: NtQueryInformationToken(2) failed Status:0x%x\n",
            (unsigned int)v8);
        v9 = NlpCopySid(*v2);
        if ( v9 )
        {
          *a2 = v9;
          v5 = 0;
          goto LABEL_18;
        }
      }
      else
      {
        NlPrintRoutine(
          0x100u,
          L"NlRpcGetClientIdentity: failed to allocate TokenUserInfo TokenUserInfoSize:0x%x\n",
          TokenInformationLength);
      }
    }
    else
    {
      NlPrintRoutine(0x100u, L"NlRpcGetClientIdentity: NtQueryInformationToken(1) failed Status:0x%x\n", v7);
    }
  }
  else if ( v5 )
  {
    goto LABEL_18;
  }
  v5 = 8;
LABEL_18:
  free(0);
  NetApiBufferFree(v2);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x180042504  mov     rax, rsp
0x180042507  mov     [rax+8], rbx
0x18004250b  mov     [rax+20h], rdi
0x18004250f  push    r14
0x180042511  sub     rsp, 30h
0x180042515  xor     ebx, ebx
0x180042517  mov     qword ptr [rax+18h], 0
0x18004251f  mov     [rax+10h], ebx
0x180042522  mov     r14, rdx
0x180042525  mov     [rdx], rbx
0x180042528  call    cs:__imp_RpcImpersonateClient
0x18004252f  nop     dword ptr [rax+rax+00h]
0x180042534  mov     edi, eax
0x180042536  test    eax, eax
0x180042538  jnz     short loc_18004257B
0x18004253a  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18004253f  mov     r8b, 1; OpenAsSelf
0x180042542  lea     edx, [rbx+8]; DesiredAccess
0x180042545  lea     rcx, [rbx-2]; ThreadHandle
0x180042549  call    cs:__imp_NtOpenThreadToken
0x180042550  nop     dword ptr [rax+rax+00h]
0x180042555  test    eax, eax
0x180042557  jns     short loc_18004256D
0x180042559  mov     r8d, eax
0x18004255c  lea     rdx, aNlrpcgetclient_2; "NlRpcGetClientIdentity: NtOpenThreadTok"...
0x180042563  mov     ecx, 100h; unsigned int
0x180042568  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004256d  call    cs:__imp_RpcRevertToSelf
0x180042574  nop     dword ptr [rax+rax+00h]
0x180042579  jmp     short loc_18004258F
0x18004257b  mov     r8d, edi
0x18004257e  lea     rdx, aNlrpcgetclient_4; "NlRpcGetClientIdentity: RpcImpersonate "...
0x180042585  mov     ecx, 100h; unsigned int
0x18004258a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004258f  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180042594  test    rcx, rcx
0x180042597  jnz     short loc_1800425A6
0x180042599  test    edi, edi
0x18004259b  jnz     loc_180042660
0x1800425a1  jmp     loc_18004265B
0x1800425a6  xor     r9d, r9d; TokenInformationLength
0x1800425a9  lea     rax, [rsp+38h+TokenInformationLength]
0x1800425ae  xor     r8d, r8d; TokenInformation
0x1800425b1  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800425b6  lea     edx, [r9+1]; TokenInformationClass
0x1800425ba  call    cs:__imp_NtQueryInformationToken
0x1800425c1  nop     dword ptr [rax+rax+00h]
0x1800425c6  cmp     eax, 0C0000023h
0x1800425cb  jnz     short loc_180042647
0x1800425cd  mov     ecx, [rsp+38h+TokenInformationLength]
0x1800425d1  call    NetpMemoryAllocate
0x1800425d6  mov     rbx, rax
0x1800425d9  test    rax, rax
0x1800425dc  jz      short loc_180042639
0x1800425de  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800425e3  lea     rax, [rsp+38h+TokenInformationLength]
0x1800425e8  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800425ed  mov     r8, rbx; TokenInformation
0x1800425f0  mov     edx, 1; TokenInformationClass
0x1800425f5  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800425fa  call    cs:__imp_NtQueryInformationToken
0x180042601  nop     dword ptr [rax+rax+00h]
0x180042606  test    eax, eax
0x180042608  jns     short loc_180042620
0x18004260a  mov     r8d, eax
0x18004260d  lea     rdx, aNlrpcgetclient_3; "NlRpcGetClientIdentity: NtQueryInformat"...
0x180042614  mov     ecx, 100h; unsigned int
0x180042619  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004261e  jmp     short loc_180042625
0x180042620  test    rbx, rbx
0x180042623  jz      short loc_18004265B
0x180042625  mov     rcx, [rbx]; SourceSid
0x180042628  call    ?NlpCopySid@@YAPEAXPEAX@Z; NlpCopySid(void *)
0x18004262d  test    rax, rax
0x180042630  jz      short loc_18004265B
0x180042632  mov     [r14], rax
0x180042635  xor     edi, edi
0x180042637  jmp     short loc_180042660
0x180042639  mov     r8d, [rsp+38h+TokenInformationLength]
0x18004263e  lea     rdx, aNlrpcgetclient_7; "NlRpcGetClientIdentity: failed to alloc"...
0x180042645  jmp     short loc_180042651
0x180042647  mov     r8d, eax
0x18004264a  lea     rdx, aNlrpcgetclient; "NlRpcGetClientIdentity: NtQueryInformat"...
0x180042651  mov     ecx, 100h; unsigned int
0x180042656  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004265b  mov     edi, 8
0x180042660  xor     ecx, ecx; Block
0x180042662  call    cs:__imp_free
0x180042669  nop     dword ptr [rax+rax+00h]
0x18004266e  mov     rcx, rbx; Buffer
0x180042671  call    cs:__imp_NetApiBufferFree
0x180042678  nop     dword ptr [rax+rax+00h]
0x18004267d  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180042682  test    rcx, rcx
0x180042685  jz      short loc_180042693
0x180042687  call    cs:__imp_CloseHandle
0x18004268e  nop     dword ptr [rax+rax+00h]
0x180042693  mov     rbx, [rsp+38h+arg_0]
0x180042698  mov     eax, edi
0x18004269a  mov     rdi, [rsp+38h+arg_18]
0x18004269f  add     rsp, 30h
0x1800426a3  pop     r14
0x1800426a5  retn
```
