# EfsRpcSetFileEncryptionKey

- ea: `0x1800078e0`
- end: `0x180007a64`
- name: `EfsRpcSetFileEncryptionKey`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting`

## callees

- `0x1800037b8`
- `0x1800078e0`
- `0x18000bf0c`
- `0x18000d192`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079f4`
- `RPCRT4!RpcRevertToSelf` at `0x180007a42`
- `RPCRT4!RpcRevertToSelf` at `0x180007a42`
- `RPCRT4!RpcImpersonateClient` at `0x18000799c`
- `RPCRT4!RpcImpersonateClient` at `0x18000799c`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000794f`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000794f`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180007a25`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180007a25`
- `EFSCORE!EfsDllDisabled` at `0x18000792e`
- `EFSCORE!EfsDllDisabled` at `0x18000792e`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180007a36`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180007a36`
- `EFSCORE!EfsDllGetUserInfo` at `0x1800079bd`
- `EFSCORE!EfsDllGetUserInfo` at `0x1800079bd`
- `EFSCORE!EfsDllSetFileEncryptionKeySrv` at `0x180007a12`
- `EFSCORE!EfsDllSetFileEncryptionKeySrv` at `0x180007a12`
- `EFSCORE!EfsDllLoadUserProfile` at `0x1800079e4`
- `EFSCORE!EfsDllLoadUserProfile` at `0x1800079e4`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x180007914`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x180007914`

## pseudocode

```c
__int64 __fastcall EfsRpcSetFileEncryptionKey(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  DWORD LastError; // ebx
  DWORD v8; // eax
  int v9; // ecx
  RPC_STATUS v10; // eax
  int v11; // ecx
  __int64 v12; // rdx
  unsigned int ClientLocalFlag[4]; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v15[152]; // [rsp+40h] [rbp-98h] BYREF

  ClientLocalFlag[0] = 0;
  memset_0(v15, 0, 0x70u);
  if ( (unsigned __int8)EfsDllIsNonEfsSKU(L"feclient-EfsEnabled") )
  {
    return 50;
  }
  else if ( (unsigned __int8)EfsDllDisabled() )
  {
    return 6015;
  }
  else if ( I_RpcBindingIsClientLocal(0, ClientLocalFlag) || !ClientLocalFlag[0] )
  {
    return 5;
  }
  else
  {
    v8 = EfsEnforceClientAuthentication();
    LastError = v8;
    if ( v8 )
    {
      fnEfsLogTrace1(v9, (unsigned int)EFS_API_ERROR, v8, 6, 233);
    }
    else
    {
      v10 = RpcImpersonateClient(0);
      LastError = v10;
      if ( v10 )
      {
        fnEfsLogTrace1(v11, (unsigned int)EFS_API_ERROR, v10, 6, 238);
      }
      else
      {
        if ( (unsigned __int8)EfsDllGetUserInfo(v15) )
        {
          LOBYTE(v12) = 1;
          if ( (unsigned int)EfsDllLoadUserProfile(v15, v12) )
          {
            LastError = EfsDllSetFileEncryptionKeySrv(v15, a2, a3, a4);
            EfsDllUnloadUserProfile(v15);
          }
          else
          {
            LastError = GetLastError();
          }
          EfsDllFreeUserInfo(v15);
        }
        else
        {
          LastError = GetLastError();
        }
        RpcRevertToSelf();
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800078e0  push    rbx
0x1800078e2  push    rbp
0x1800078e3  push    rsi
0x1800078e4  push    rdi
0x1800078e5  sub     rsp, 0B8h
0x1800078ec  mov     rbp, rdx
0x1800078ef  mov     [rsp+0D8h+ClientLocalFlag], 0
0x1800078f7  xor     edx, edx; Val
0x1800078f9  lea     rcx, [rsp+0D8h+var_98]; void *
0x1800078fe  mov     esi, r8d
0x180007901  mov     edi, r9d
0x180007904  lea     r8d, [rdx+70h]; Size
0x180007908  call    memset_0
0x18000790d  lea     rcx, aFeclientEfsena_0; "feclient-EfsEnabled"
0x180007914  call    cs:__imp_EfsDllIsNonEfsSKU
0x18000791b  nop     dword ptr [rax+rax+00h]
0x180007920  test    al, al
0x180007922  jz      short loc_18000792E
0x180007924  mov     ebx, 32h ; '2'
0x180007929  jmp     loc_180007A55
0x18000792e  call    cs:__imp_EfsDllDisabled
0x180007935  nop     dword ptr [rax+rax+00h]
0x18000793a  test    al, al
0x18000793c  jz      short loc_180007948
0x18000793e  mov     ebx, 177Fh
0x180007943  jmp     loc_180007A55
0x180007948  lea     rdx, [rsp+0D8h+ClientLocalFlag]; ClientLocalFlag
0x18000794d  xor     ecx, ecx; BindingHandle
0x18000794f  call    cs:__imp_I_RpcBindingIsClientLocal
0x180007956  nop     dword ptr [rax+rax+00h]
0x18000795b  test    eax, eax
0x18000795d  jnz     loc_180007A50
0x180007963  cmp     [rsp+0D8h+ClientLocalFlag], eax
0x180007967  jz      loc_180007A50
0x18000796d  call    EfsEnforceClientAuthentication
0x180007972  mov     ebx, eax
0x180007974  test    eax, eax
0x180007976  jz      short loc_18000799A
0x180007978  mov     [rsp+0D8h+var_B8], 6E9h
0x180007980  mov     r9d, 6
0x180007986  lea     rdx, EFS_API_ERROR
0x18000798d  mov     r8d, eax
0x180007990  call    fnEfsLogTrace1
0x180007995  jmp     loc_180007A55
0x18000799a  xor     ecx, ecx; BindingHandle
0x18000799c  call    cs:__imp_RpcImpersonateClient
0x1800079a3  nop     dword ptr [rax+rax+00h]
0x1800079a8  mov     ebx, eax
0x1800079aa  test    eax, eax
0x1800079ac  jz      short loc_1800079B8
0x1800079ae  mov     [rsp+0D8h+var_B8], 6EEh
0x1800079b6  jmp     short loc_180007980
0x1800079b8  lea     rcx, [rsp+0D8h+var_98]
0x1800079bd  call    cs:__imp_EfsDllGetUserInfo
0x1800079c4  nop     dword ptr [rax+rax+00h]
0x1800079c9  test    al, al
0x1800079cb  jnz     short loc_1800079DD
0x1800079cd  call    cs:__imp_GetLastError
0x1800079d4  nop     dword ptr [rax+rax+00h]
0x1800079d9  mov     ebx, eax
0x1800079db  jmp     short loc_180007A42
0x1800079dd  mov     dl, 1
0x1800079df  lea     rcx, [rsp+0D8h+var_98]
0x1800079e4  call    cs:__imp_EfsDllLoadUserProfile
0x1800079eb  nop     dword ptr [rax+rax+00h]
0x1800079f0  test    eax, eax
0x1800079f2  jnz     short loc_180007A04
0x1800079f4  call    cs:__imp_GetLastError
0x1800079fb  nop     dword ptr [rax+rax+00h]
0x180007a00  mov     ebx, eax
0x180007a02  jmp     short loc_180007A31
0x180007a04  mov     r9d, edi
0x180007a07  lea     rcx, [rsp+0D8h+var_98]
0x180007a0c  mov     r8d, esi
0x180007a0f  mov     rdx, rbp
0x180007a12  call    cs:__imp_EfsDllSetFileEncryptionKeySrv
0x180007a19  nop     dword ptr [rax+rax+00h]
0x180007a1e  lea     rcx, [rsp+0D8h+var_98]
0x180007a23  mov     ebx, eax
0x180007a25  call    cs:__imp_EfsDllUnloadUserProfile
0x180007a2c  nop     dword ptr [rax+rax+00h]
0x180007a31  lea     rcx, [rsp+0D8h+var_98]
0x180007a36  call    cs:__imp_EfsDllFreeUserInfo
0x180007a3d  nop     dword ptr [rax+rax+00h]
0x180007a42  call    cs:__imp_RpcRevertToSelf
0x180007a49  nop     dword ptr [rax+rax+00h]
0x180007a4e  jmp     short loc_180007A55
0x180007a50  mov     ebx, 5
0x180007a55  mov     eax, ebx
0x180007a57  add     rsp, 0B8h
0x180007a5e  pop     rdi
0x180007a5f  pop     rsi
0x180007a60  pop     rbp
0x180007a61  pop     rbx
0x180007a62  retn
```
