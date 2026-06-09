# EfsRpcWriteFileWithHeaderRaw

- ea: `0x180007330`
- end: `0x1800074c2`
- name: `EfsRpcWriteFileWithHeaderRaw`
- size: `402`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x180003604`
- `0x180007330`
- `0x18000b308`
- `0x18000c392`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000744b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000744b`
- `RPCRT4!RpcRevertToSelf` at `0x180007491`
- `RPCRT4!RpcRevertToSelf` at `0x180007491`
- `RPCRT4!RpcImpersonateClient` at `0x180007411`
- `RPCRT4!RpcImpersonateClient` at `0x180007411`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180007397`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180007397`
- `RPCRT4!RpcRaiseException` at `0x1800074bb`
- `RPCRT4!RpcRaiseException` at `0x1800074bb`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180007480`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180007480`
- `EFSCORE!EfsDllWriteEncryptedFileWithHeader` at `0x180007473`
- `EFSCORE!EfsDllWriteEncryptedFileWithHeader` at `0x180007473`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000748b`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000748b`
- `EFSCORE!EfsDllGetUserInfo` at `0x180007426`
- `EFSCORE!EfsDllGetUserInfo` at `0x180007426`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180007441`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180007441`

## pseudocode

```c
__int64 __fastcall EfsRpcWriteFileWithHeaderRaw(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  RPC_STATUS IsClientLocal; // eax
  int v10; // ecx
  RPC_STATUS LastError; // ebx
  RPC_STATUS v12; // eax
  int v13; // ecx
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
    fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, IsClientLocal, 6, 196);
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
    fnEfsLogTrace1(v13, (unsigned int)EFS_API_ERROR, v12, 6, 205);
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
0x180007330  push    rbx
0x180007332  push    rbp
0x180007333  push    rsi
0x180007334  push    rdi
0x180007335  push    r14
0x180007337  push    r15
0x180007339  sub     rsp, 0B8h
0x180007340  mov     r14, rdx
0x180007343  mov     rdi, r8
0x180007346  xor     edx, edx; Val
0x180007348  mov     rbp, rcx
0x18000734b  lea     rcx, [rsp+0E8h+var_A8]; void *
0x180007350  mov     r15, r9
0x180007353  lea     r8d, [rdx+70h]; Size
0x180007357  call    memset_0
0x18000735c  mov     [rsp+0E8h+ClientLocalFlag], 0
0x180007367  test    r14, r14
0x18000736a  jz      loc_1800074B4
0x180007370  test    rbp, rbp
0x180007373  jz      loc_1800074B4
0x180007379  test    rdi, rdi
0x18000737c  jz      loc_1800074B4
0x180007382  cmp     qword ptr [rdi+8], 0
0x180007387  jz      loc_1800074B4
0x18000738d  lea     rdx, [rsp+0E8h+ClientLocalFlag]; ClientLocalFlag
0x180007395  xor     ecx, ecx; BindingHandle
0x180007397  call    cs:__imp_I_RpcBindingIsClientLocal
0x18000739d  mov     ebx, eax
0x18000739f  test    eax, eax
0x1800073a1  jz      short loc_1800073C5
0x1800073a3  mov     [rsp+0E8h+var_C8], 1C4h
0x1800073ab  mov     r9d, 6
0x1800073b1  lea     rdx, EFS_API_ERROR
0x1800073b8  mov     r8d, eax
0x1800073bb  call    fnEfsLogTrace1
0x1800073c0  jmp     loc_1800074B9
0x1800073c5  cmp     [rsp+0E8h+ClientLocalFlag], 0
0x1800073cd  jnz     short loc_1800073D9
0x1800073cf  mov     ebx, 32h ; '2'
0x1800073d4  jmp     loc_1800074B9
0x1800073d9  call    EfsEnforceClientAuthentication
0x1800073de  mov     ebx, eax
0x1800073e0  test    eax, eax
0x1800073e2  jz      short loc_1800073EE
0x1800073e4  mov     [rsp+0E8h+var_C8], 1CDh
0x1800073ec  jmp     short loc_1800073AB
0x1800073ee  mov     esi, 1
0x1800073f3  test    [rsp+0E8h+arg_20], sil
0x1800073fb  jz      short loc_180007401
0x1800073fd  xor     esi, esi
0x1800073ff  jmp     short loc_18000740F
0x180007401  test    [rsp+0E8h+arg_20], 2
0x180007409  jz      loc_1800074AD
0x18000740f  xor     ecx, ecx; BindingHandle
0x180007411  call    cs:__imp_RpcImpersonateClient
0x180007417  mov     ebx, eax
0x180007419  test    eax, eax
0x18000741b  jnz     loc_1800074B9
0x180007421  lea     rcx, [rsp+0E8h+var_A8]
0x180007426  call    cs:__imp_EfsDllGetUserInfo
0x18000742c  test    al, al
0x18000742e  jnz     short loc_18000743A
0x180007430  call    cs:__imp_GetLastError
0x180007436  mov     ebx, eax
0x180007438  jmp     short loc_180007491
0x18000743a  xor     edx, edx
0x18000743c  lea     rcx, [rsp+0E8h+var_A8]
0x180007441  call    cs:__imp_EfsDllLoadUserProfile
0x180007447  test    eax, eax
0x180007449  jnz     short loc_180007455
0x18000744b  call    cs:__imp_GetLastError
0x180007451  mov     ebx, eax
0x180007453  jmp     short loc_180007486
0x180007455  mov     eax, [rdi]
0x180007457  lea     r8, [rsp+0E8h+var_A8]
0x18000745c  mov     r9, [rdi+8]
0x180007460  mov     rdx, r14
0x180007463  mov     [rsp+0E8h+var_B8], esi
0x180007467  mov     rcx, rbp
0x18000746a  mov     [rsp+0E8h+var_C0], r15
0x18000746f  mov     [rsp+0E8h+var_C8], eax
0x180007473  call    cs:__imp_EfsDllWriteEncryptedFileWithHeader
0x180007479  lea     rcx, [rsp+0E8h+var_A8]
0x18000747e  mov     ebx, eax
0x180007480  call    cs:__imp_EfsDllUnloadUserProfile
0x180007486  lea     rcx, [rsp+0E8h+var_A8]
0x18000748b  call    cs:__imp_EfsDllFreeUserInfo
0x180007491  call    cs:__imp_RpcRevertToSelf
0x180007497  test    ebx, ebx
0x180007499  jnz     short loc_1800074B9
0x18000749b  xor     eax, eax
0x18000749d  add     rsp, 0B8h
0x1800074a4  pop     r15
0x1800074a6  pop     r14
0x1800074a8  pop     rdi
0x1800074a9  pop     rsi
0x1800074aa  pop     rbp
0x1800074ab  pop     rbx
0x1800074ac  retn
0x1800074ad  mov     ebx, 57h ; 'W'
0x1800074b2  jmp     short loc_1800074B9
0x1800074b4  mov     ebx, 5
0x1800074b9  mov     ecx, ebx; exception
0x1800074bb  call    cs:__imp_RpcRaiseException
```
