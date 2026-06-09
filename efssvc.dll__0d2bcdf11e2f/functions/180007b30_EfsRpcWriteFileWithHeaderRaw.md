# EfsRpcWriteFileWithHeaderRaw

- ea: `0x180007b30`
- end: `0x180007d05`
- name: `EfsRpcWriteFileWithHeaderRaw`
- size: `469`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x1800037b8`
- `0x180007b30`
- `0x18000bf0c`
- `0x18000d192`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c69`
- `RPCRT4!RpcRevertToSelf` at `0x180007cc7`
- `RPCRT4!RpcRevertToSelf` at `0x180007cc7`
- `RPCRT4!RpcImpersonateClient` at `0x180007c17`
- `RPCRT4!RpcImpersonateClient` at `0x180007c17`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180007b97`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180007b97`
- `RPCRT4!RpcRaiseException` at `0x180007cf8`
- `RPCRT4!RpcRaiseException` at `0x180007cf8`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180007caa`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180007caa`
- `EFSCORE!EfsDllWriteEncryptedFileWithHeader` at `0x180007c97`
- `EFSCORE!EfsDllWriteEncryptedFileWithHeader` at `0x180007c97`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180007cbb`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180007cbb`
- `EFSCORE!EfsDllGetUserInfo` at `0x180007c32`
- `EFSCORE!EfsDllGetUserInfo` at `0x180007c32`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180007c59`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180007c59`

## pseudocode

```c
__int64 __fastcall EfsRpcWriteFileWithHeaderRaw(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  RPC_STATUS IsClientLocal; // eax
  __int64 v10; // rcx
  RPC_STATUS LastError; // ebx
  unsigned int v12; // eax
  __int64 v13; // rcx
  int v14; // esi
  _BYTE v16[168]; // [rsp+40h] [rbp-A8h] BYREF
  unsigned int ClientLocalFlag; // [rsp+F8h] [rbp+10h] BYREF

  memset_0(v16, 0, 0x70u);
  ClientLocalFlag = 0;
  if ( !a2 || !a1 || !a3 || !*(_QWORD *)(a3 + 8) )
  {
    LastError = 5;
    goto LABEL_26;
  }
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  LastError = IsClientLocal;
  if ( IsClientLocal )
  {
    fnEfsLogTrace1(v10, (__int64)EFS_API_ERROR, IsClientLocal, 6, 196);
    goto LABEL_26;
  }
  if ( !ClientLocalFlag )
  {
    LastError = 50;
    goto LABEL_26;
  }
  v12 = EfsEnforceClientAuthentication();
  LastError = v12;
  if ( v12 )
  {
    fnEfsLogTrace1(v13, (__int64)EFS_API_ERROR, v12, 6, 205);
    goto LABEL_26;
  }
  v14 = 1;
  if ( (a5 & 1) != 0 )
  {
    v14 = 0;
  }
  else if ( (a5 & 2) == 0 )
  {
    LastError = 87;
    goto LABEL_26;
  }
  LastError = RpcImpersonateClient(0);
  if ( LastError )
    goto LABEL_26;
  if ( (unsigned __int8)EfsDllGetUserInfo(v16) )
  {
    if ( (unsigned int)EfsDllLoadUserProfile(v16, 0) )
    {
      LastError = EfsDllWriteEncryptedFileWithHeader(a1, a2, v16, *(_QWORD *)(a3 + 8), *(_DWORD *)a3, a4, v14);
      EfsDllUnloadUserProfile(v16);
    }
    else
    {
      LastError = GetLastError();
    }
    EfsDllFreeUserInfo(v16);
  }
  else
  {
    LastError = GetLastError();
  }
  RpcRevertToSelf();
  if ( LastError )
LABEL_26:
    RpcRaiseException(LastError);
  return 0;
}

```

## disassembly

```asm
0x180007b30  push    rbx
0x180007b32  push    rbp
0x180007b33  push    rsi
0x180007b34  push    rdi
0x180007b35  push    r14
0x180007b37  push    r15
0x180007b39  sub     rsp, 0B8h
0x180007b40  mov     r14, rdx
0x180007b43  mov     rdi, r8
0x180007b46  xor     edx, edx; Val
0x180007b48  mov     rbp, rcx
0x180007b4b  lea     rcx, [rsp+0E8h+var_A8]; void *
0x180007b50  mov     r15, r9
0x180007b53  lea     r8d, [rdx+70h]; Size
0x180007b57  call    memset_0
0x180007b5c  mov     [rsp+0E8h+ClientLocalFlag], 0
0x180007b67  test    r14, r14
0x180007b6a  jz      loc_180007CF1
0x180007b70  test    rbp, rbp
0x180007b73  jz      loc_180007CF1
0x180007b79  test    rdi, rdi
0x180007b7c  jz      loc_180007CF1
0x180007b82  cmp     qword ptr [rdi+8], 0
0x180007b87  jz      loc_180007CF1
0x180007b8d  lea     rdx, [rsp+0E8h+ClientLocalFlag]; ClientLocalFlag
0x180007b95  xor     ecx, ecx; BindingHandle
0x180007b97  call    cs:__imp_I_RpcBindingIsClientLocal
0x180007b9e  nop     dword ptr [rax+rax+00h]
0x180007ba3  mov     ebx, eax
0x180007ba5  test    eax, eax
0x180007ba7  jz      short loc_180007BCB
0x180007ba9  mov     [rsp+0E8h+var_C8], 1C4h
0x180007bb1  mov     r9d, 6
0x180007bb7  lea     rdx, EFS_API_ERROR
0x180007bbe  mov     r8d, eax
0x180007bc1  call    fnEfsLogTrace1
0x180007bc6  jmp     loc_180007CF6
0x180007bcb  cmp     [rsp+0E8h+ClientLocalFlag], 0
0x180007bd3  jnz     short loc_180007BDF
0x180007bd5  mov     ebx, 32h ; '2'
0x180007bda  jmp     loc_180007CF6
0x180007bdf  call    EfsEnforceClientAuthentication
0x180007be4  mov     ebx, eax
0x180007be6  test    eax, eax
0x180007be8  jz      short loc_180007BF4
0x180007bea  mov     [rsp+0E8h+var_C8], 1CDh
0x180007bf2  jmp     short loc_180007BB1
0x180007bf4  mov     esi, 1
0x180007bf9  test    [rsp+0E8h+arg_20], sil
0x180007c01  jz      short loc_180007C07
0x180007c03  xor     esi, esi
0x180007c05  jmp     short loc_180007C15
0x180007c07  test    [rsp+0E8h+arg_20], 2
0x180007c0f  jz      loc_180007CEA
0x180007c15  xor     ecx, ecx; BindingHandle
0x180007c17  call    cs:__imp_RpcImpersonateClient
0x180007c1e  nop     dword ptr [rax+rax+00h]
0x180007c23  mov     ebx, eax
0x180007c25  test    eax, eax
0x180007c27  jnz     loc_180007CF6
0x180007c2d  lea     rcx, [rsp+0E8h+var_A8]
0x180007c32  call    cs:__imp_EfsDllGetUserInfo
0x180007c39  nop     dword ptr [rax+rax+00h]
0x180007c3e  test    al, al
0x180007c40  jnz     short loc_180007C52
0x180007c42  call    cs:__imp_GetLastError
0x180007c49  nop     dword ptr [rax+rax+00h]
0x180007c4e  mov     ebx, eax
0x180007c50  jmp     short loc_180007CC7
0x180007c52  xor     edx, edx
0x180007c54  lea     rcx, [rsp+0E8h+var_A8]
0x180007c59  call    cs:__imp_EfsDllLoadUserProfile
0x180007c60  nop     dword ptr [rax+rax+00h]
0x180007c65  test    eax, eax
0x180007c67  jnz     short loc_180007C79
0x180007c69  call    cs:__imp_GetLastError
0x180007c70  nop     dword ptr [rax+rax+00h]
0x180007c75  mov     ebx, eax
0x180007c77  jmp     short loc_180007CB6
0x180007c79  mov     eax, [rdi]
0x180007c7b  lea     r8, [rsp+0E8h+var_A8]
0x180007c80  mov     r9, [rdi+8]
0x180007c84  mov     rdx, r14
0x180007c87  mov     [rsp+0E8h+var_B8], esi
0x180007c8b  mov     rcx, rbp
0x180007c8e  mov     [rsp+0E8h+var_C0], r15
0x180007c93  mov     [rsp+0E8h+var_C8], eax
0x180007c97  call    cs:__imp_EfsDllWriteEncryptedFileWithHeader
0x180007c9e  nop     dword ptr [rax+rax+00h]
0x180007ca3  lea     rcx, [rsp+0E8h+var_A8]
0x180007ca8  mov     ebx, eax
0x180007caa  call    cs:__imp_EfsDllUnloadUserProfile
0x180007cb1  nop     dword ptr [rax+rax+00h]
0x180007cb6  lea     rcx, [rsp+0E8h+var_A8]
0x180007cbb  call    cs:__imp_EfsDllFreeUserInfo
0x180007cc2  nop     dword ptr [rax+rax+00h]
0x180007cc7  call    cs:__imp_RpcRevertToSelf
0x180007cce  nop     dword ptr [rax+rax+00h]
0x180007cd3  test    ebx, ebx
0x180007cd5  jnz     short loc_180007CF6
0x180007cd7  xor     eax, eax
0x180007cd9  add     rsp, 0B8h
0x180007ce0  pop     r15
0x180007ce2  pop     r14
0x180007ce4  pop     rdi
0x180007ce5  pop     rsi
0x180007ce6  pop     rbp
0x180007ce7  pop     rbx
0x180007ce8  retn
0x180007cea  mov     ebx, 57h ; 'W'
0x180007cef  jmp     short loc_180007CF6
0x180007cf1  mov     ebx, 5
0x180007cf6  mov     ecx, ebx; exception
0x180007cf8  call    cs:__imp_RpcRaiseException
0x180007cff  nop     dword ptr [rax+rax+00h]
0x180007d04  int     3; Trap to Debugger
```
