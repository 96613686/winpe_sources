# NlRpcGetClientIdentity(void *,void * *)

- ea: `0x18003fb94`
- end: `0x18003fd06`
- name: `?NlRpcGetClientIdentity@@YAJPEAXPEAPEAX@Z`
- size: `370`
- prototype: `__int64 __fastcall(void *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003fd0c`

## callees

- `0x180003200`
- `0x180007278`
- `0x18003fb94`
- `0x180050ca0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fcd4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003fcd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fced`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fced`
- `RPCRT4!RpcImpersonateClient` at `0x18003fbb8`
- `RPCRT4!RpcImpersonateClient` at `0x18003fbb8`
- `RPCRT4!RpcRevertToSelf` at `0x18003fbf1`
- `RPCRT4!RpcRevertToSelf` at `0x18003fbf1`
- `ntdll!NtOpenThreadToken` at `0x18003fbd3`
- `ntdll!NtOpenThreadToken` at `0x18003fbd3`
- `ntdll!NtQueryInformationToken` at `0x18003fc38`
- `ntdll!NtQueryInformationToken` at `0x18003fc72`
- `ntdll!NtQueryInformationToken` at `0x18003fc38`
- `ntdll!NtQueryInformationToken` at `0x18003fc72`
- `netutils!NetApiBufferFree` at `0x18003fcdd`
- `netutils!NetApiBufferFree` at `0x18003fcdd`

## string_xrefs

- `0x18003fbe0`: `NlRpcGetClientIdentity: NtOpenThreadToken failed Status:0x%x\n`
- `0x18003fbfc`: `NlRpcGetClientIdentity: RpcImpersonate failed RpcStatus:0x%x\n`
- `0x18003fc7f`: `NlRpcGetClientIdentity: NtQueryInformationToken(2) failed Status:0x%x\n`
- `0x18003fcb0`: `NlRpcGetClientIdentity: failed to allocate TokenUserInfo TokenUserInfoSize:0x%x\n`
- `0x18003fcbc`: `NlRpcGetClientIdentity: NtQueryInformationToken(1) failed Status:0x%x\n`

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
0x18003fb94  mov     rax, rsp
0x18003fb97  mov     [rax+8], rbx
0x18003fb9b  mov     [rax+20h], rdi
0x18003fb9f  push    r14
0x18003fba1  sub     rsp, 30h
0x18003fba5  xor     ebx, ebx
0x18003fba7  mov     qword ptr [rax+18h], 0
0x18003fbaf  mov     [rax+10h], ebx
0x18003fbb2  mov     r14, rdx
0x18003fbb5  mov     [rdx], rbx
0x18003fbb8  call    cs:__imp_RpcImpersonateClient
0x18003fbbe  mov     edi, eax
0x18003fbc0  test    eax, eax
0x18003fbc2  jnz     short loc_18003FBF9
0x18003fbc4  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18003fbc9  mov     r8b, 1; OpenAsSelf
0x18003fbcc  lea     edx, [rbx+8]; DesiredAccess
0x18003fbcf  lea     rcx, [rbx-2]; ThreadHandle
0x18003fbd3  call    cs:__imp_NtOpenThreadToken
0x18003fbd9  test    eax, eax
0x18003fbdb  jns     short loc_18003FBF1
0x18003fbdd  mov     r8d, eax
0x18003fbe0  lea     rdx, aNlrpcgetclient_2; "NlRpcGetClientIdentity: NtOpenThreadTok"...
0x18003fbe7  mov     ecx, 100h; unsigned int
0x18003fbec  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003fbf1  call    cs:__imp_RpcRevertToSelf
0x18003fbf7  jmp     short loc_18003FC0D
0x18003fbf9  mov     r8d, edi
0x18003fbfc  lea     rdx, aNlrpcgetclient_4; "NlRpcGetClientIdentity: RpcImpersonate "...
0x18003fc03  mov     ecx, 100h; unsigned int
0x18003fc08  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003fc0d  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18003fc12  test    rcx, rcx
0x18003fc15  jnz     short loc_18003FC24
0x18003fc17  test    edi, edi
0x18003fc19  jnz     loc_18003FCD2
0x18003fc1f  jmp     loc_18003FCCD
0x18003fc24  xor     r9d, r9d; TokenInformationLength
0x18003fc27  lea     rax, [rsp+38h+TokenInformationLength]
0x18003fc2c  xor     r8d, r8d; TokenInformation
0x18003fc2f  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18003fc34  lea     edx, [r9+1]; TokenInformationClass
0x18003fc38  call    cs:__imp_NtQueryInformationToken
0x18003fc3e  cmp     eax, 0C0000023h
0x18003fc43  jnz     short loc_18003FCB9
0x18003fc45  mov     ecx, [rsp+38h+TokenInformationLength]
0x18003fc49  call    NetpMemoryAllocate
0x18003fc4e  mov     rbx, rax
0x18003fc51  test    rax, rax
0x18003fc54  jz      short loc_18003FCAB
0x18003fc56  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18003fc5b  lea     rax, [rsp+38h+TokenInformationLength]
0x18003fc60  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18003fc65  mov     r8, rbx; TokenInformation
0x18003fc68  mov     edx, 1; TokenInformationClass
0x18003fc6d  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18003fc72  call    cs:__imp_NtQueryInformationToken
0x18003fc78  test    eax, eax
0x18003fc7a  jns     short loc_18003FC92
0x18003fc7c  mov     r8d, eax
0x18003fc7f  lea     rdx, aNlrpcgetclient_3; "NlRpcGetClientIdentity: NtQueryInformat"...
0x18003fc86  mov     ecx, 100h; unsigned int
0x18003fc8b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003fc90  jmp     short loc_18003FC97
0x18003fc92  test    rbx, rbx
0x18003fc95  jz      short loc_18003FCCD
0x18003fc97  mov     rcx, [rbx]; SourceSid
0x18003fc9a  call    ?NlpCopySid@@YAPEAXPEAX@Z; NlpCopySid(void *)
0x18003fc9f  test    rax, rax
0x18003fca2  jz      short loc_18003FCCD
0x18003fca4  mov     [r14], rax
0x18003fca7  xor     edi, edi
0x18003fca9  jmp     short loc_18003FCD2
0x18003fcab  mov     r8d, [rsp+38h+TokenInformationLength]
0x18003fcb0  lea     rdx, aNlrpcgetclient_7; "NlRpcGetClientIdentity: failed to alloc"...
0x18003fcb7  jmp     short loc_18003FCC3
0x18003fcb9  mov     r8d, eax
0x18003fcbc  lea     rdx, aNlrpcgetclient; "NlRpcGetClientIdentity: NtQueryInformat"...
0x18003fcc3  mov     ecx, 100h; unsigned int
0x18003fcc8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003fccd  mov     edi, 8
0x18003fcd2  xor     ecx, ecx; Block
0x18003fcd4  call    cs:__imp_free
0x18003fcda  mov     rcx, rbx; Buffer
0x18003fcdd  call    cs:__imp_NetApiBufferFree
0x18003fce3  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18003fce8  test    rcx, rcx
0x18003fceb  jz      short loc_18003FCF3
0x18003fced  call    cs:__imp_CloseHandle
0x18003fcf3  mov     rbx, [rsp+38h+arg_0]
0x18003fcf8  mov     eax, edi
0x18003fcfa  mov     rdi, [rsp+38h+arg_18]
0x18003fcff  add     rsp, 30h
0x18003fd03  pop     r14
0x18003fd05  retn
```
