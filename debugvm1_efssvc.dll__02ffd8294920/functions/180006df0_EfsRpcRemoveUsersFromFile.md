# EfsRpcRemoveUsersFromFile

- ea: `0x180006df0`
- end: `0x18000701e`
- name: `EfsRpcRemoveUsersFromFile`
- size: `558`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003604`
- `0x180006df0`
- `0x1800076b4`
- `0x18000b308`
- `0x18000b480`
- `0x18000c392`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f6b`
- `RPCRT4!RpcRevertToSelf` at `0x180006fe9`
- `RPCRT4!RpcRevertToSelf` at `0x180006fe9`
- `RPCRT4!RpcImpersonateClient` at `0x180006eea`
- `RPCRT4!RpcImpersonateClient` at `0x180006eea`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180006fcf`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180006fcf`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180006ed2`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180006ed2`
- `EFSCORE!EfsDllDisabled` at `0x180006e50`
- `EFSCORE!EfsDllDisabled` at `0x180006e50`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180006fdf`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180006fdf`
- `EFSCORE!EfsDllGetUserInfo` at `0x180006f61`
- `EFSCORE!EfsDllGetUserInfo` at `0x180006f61`
- `EFSCORE!EfsDllRemoveUsersFromFileSrv` at `0x180006f9d`
- `EFSCORE!EfsDllRemoveUsersFromFileSrv` at `0x180006f9d`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180006f7f`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180006f7f`
- `EFSCORE!EfsDllShareDecline` at `0x180006f3d`
- `EFSCORE!EfsDllShareDecline` at `0x180006f3d`
- `EFSCORE!EfsDllFreeHeap` at `0x180006ff9`
- `EFSCORE!EfsDllFreeHeap` at `0x180006ff9`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x180006e3e`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x180006e3e`

## pseudocode

```c
__int64 __fastcall EfsRpcRemoveUsersFromFile(__int64 a1, __int64 a2, unsigned int *a3)
{
  int v5; // esi
  int v6; // r15d
  int v7; // r13d
  DWORD LastError; // ebx
  DWORD v9; // eax
  int v10; // ecx
  DWORD LocalFileName; // eax
  int v12; // ecx
  DWORD v13; // eax
  int v14; // ecx
  int v15; // ecx
  __int64 v17; // [rsp+30h] [rbp-B8h] BYREF
  DWORD v18; // [rsp+38h] [rbp-B0h]
  int v19; // [rsp+3Ch] [rbp-ACh]
  _BYTE v20[112]; // [rsp+50h] [rbp-98h] BYREF
  __int16 v21; // [rsp+108h] [rbp+20h] BYREF

  v17 = 0;
  memset_0(v20, 0, sizeof(v20));
  v21 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  if ( (unsigned __int8)EfsDllIsNonEfsSKU(L"feclient-EfsEnabled") )
  {
    LastError = 50;
    goto LABEL_27;
  }
  if ( (unsigned __int8)EfsDllDisabled() )
  {
    LastError = 6015;
    goto LABEL_27;
  }
  if ( a3 && a2 && *((_QWORD *)a3 + 1) )
  {
    if ( *a3 > 0x1F4 )
    {
LABEL_9:
      LastError = 5;
      goto LABEL_27;
    }
    v9 = EfsEnforceClientAuthentication();
    LastError = v9;
    if ( v9 )
    {
      fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, v9, 6, 212);
    }
    else
    {
      LocalFileName = EfsDllGetLocalFileName(a2, 0, &v17, &v21);
      LastError = LocalFileName;
      if ( LocalFileName )
      {
        fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, LocalFileName, 6, 217);
      }
      else
      {
        LastError = RpcImpersonateClient(0);
        if ( !LastError )
        {
          v5 = 1;
          v19 = 1;
          v13 = EfsEnsureLocalPath(v17);
          LastError = v13;
          if ( v13 )
          {
            fnEfsLogTrace1(v14, (unsigned int)EFS_API_ERROR, v13, 6, 228);
          }
          else
          {
            if ( !(unsigned int)EfspCheckForNetSession() )
              goto LABEL_38;
            if ( v21 == 1 )
              goto LABEL_9;
            if ( (unsigned int)EfsDllShareDecline(a2, 1, 130) )
            {
              LastError = GetLastError();
              fnEfsLogTrace1(v15, (unsigned int)EFS_API_ERROR, LastError, 6, 247);
            }
            else
            {
LABEL_38:
              if ( (unsigned __int8)EfsDllGetUserInfo(v20) && (v7 = 1, (unsigned int)EfsDllLoadUserProfile(v20, 0)) )
              {
                v6 = 1;
                LastError = EfsDllRemoveUsersFromFileSrv(v20, v17, *a3, *((_QWORD *)a3 + 1));
                v18 = LastError;
              }
              else
              {
                LastError = GetLastError();
              }
            }
          }
        }
      }
    }
  }
  else
  {
    LastError = 87;
  }
LABEL_27:
  if ( v6 )
    EfsDllUnloadUserProfile(v20);
  if ( v7 )
    EfsDllFreeUserInfo(v20);
  if ( v5 )
    RpcRevertToSelf();
  if ( v17 )
    EfsDllFreeHeap();
  return LastError;
}

```

## disassembly

```asm
0x180006df0  mov     [rsp+arg_0], rbx
0x180006df5  mov     [rsp+arg_8], rsi
0x180006dfa  push    rdi
0x180006dfb  push    r12
0x180006dfd  push    r13
0x180006dff  push    r14
0x180006e01  push    r15
0x180006e03  sub     rsp, 0C0h
0x180006e0a  mov     r14, r8
0x180006e0d  mov     r12, rdx
0x180006e10  xor     edi, edi
0x180006e12  mov     [rsp+0E8h+var_B8], rdi
0x180006e17  xor     edx, edx; Val
0x180006e19  lea     r8d, [rdi+70h]; Size
0x180006e1d  lea     rcx, [rsp+0E8h+var_98]; void *
0x180006e22  call    memset_0
0x180006e27  mov     [rsp+0E8h+arg_18], di
0x180006e2f  mov     esi, edi
0x180006e31  mov     r15d, edi
0x180006e34  mov     r13d, edi
0x180006e37  lea     rcx, aFeclientEfsena_0; "feclient-EfsEnabled"
0x180006e3e  call    cs:__imp_EfsDllIsNonEfsSKU
0x180006e44  test    al, al
0x180006e46  jz      short loc_180006E50
0x180006e48  lea     ebx, [rdi+32h]
0x180006e4b  jmp     loc_180006FC5
0x180006e50  call    cs:__imp_EfsDllDisabled
0x180006e56  test    al, al
0x180006e58  jz      short loc_180006E64
0x180006e5a  mov     ebx, 177Fh
0x180006e5f  jmp     loc_180006FC5
0x180006e64  test    r14, r14
0x180006e67  jz      loc_180006FC0
0x180006e6d  test    r12, r12
0x180006e70  jz      loc_180006FC0
0x180006e76  cmp     [r14+8], rdi
0x180006e7a  jz      loc_180006FC0
0x180006e80  cmp     dword ptr [r14], 1F4h
0x180006e87  jbe     short loc_180006E93
0x180006e89  mov     ebx, 5
0x180006e8e  jmp     loc_180006FC5
0x180006e93  call    EfsEnforceClientAuthentication
0x180006e98  mov     ebx, eax
0x180006e9a  test    eax, eax
0x180006e9c  jz      short loc_180006EC0
0x180006e9e  mov     [rsp+0E8h+var_C8], 5D4h
0x180006ea6  mov     r9d, 6
0x180006eac  mov     r8d, eax
0x180006eaf  lea     rdx, EFS_API_ERROR
0x180006eb6  call    fnEfsLogTrace1
0x180006ebb  jmp     loc_180006FC5
0x180006ec0  lea     r9, [rsp+0E8h+arg_18]
0x180006ec8  lea     r8, [rsp+0E8h+var_B8]
0x180006ecd  xor     edx, edx
0x180006ecf  mov     rcx, r12
0x180006ed2  call    cs:__imp_EfsDllGetLocalFileName
0x180006ed8  mov     ebx, eax
0x180006eda  test    eax, eax
0x180006edc  jz      short loc_180006EE8
0x180006ede  mov     [rsp+0E8h+var_C8], 5D9h
0x180006ee6  jmp     short loc_180006EA6
0x180006ee8  xor     ecx, ecx; BindingHandle
0x180006eea  call    cs:__imp_RpcImpersonateClient
0x180006ef0  mov     ebx, eax
0x180006ef2  test    eax, eax
0x180006ef4  jnz     loc_180006FC5
0x180006efa  lea     esi, [rax+1]
0x180006efd  mov     [rsp+0E8h+var_AC], esi
0x180006f01  mov     rcx, [rsp+0E8h+var_B8]
0x180006f06  call    EfsEnsureLocalPath
0x180006f0b  mov     ebx, eax
0x180006f0d  test    eax, eax
0x180006f0f  jz      short loc_180006F1B
0x180006f11  mov     [rsp+0E8h+var_C8], 5E4h
0x180006f19  jmp     short loc_180006EA6
0x180006f1b  call    EfspCheckForNetSession
0x180006f20  test    eax, eax
0x180006f22  jz      short loc_180006F5C
0x180006f24  cmp     [rsp+0E8h+arg_18], si
0x180006f2c  jz      loc_180006E89
0x180006f32  mov     r8d, 82h
0x180006f38  mov     edx, esi
0x180006f3a  mov     rcx, r12
0x180006f3d  call    cs:__imp_EfsDllShareDecline
0x180006f43  test    eax, eax
0x180006f45  jz      short loc_180006F5C
0x180006f47  call    cs:__imp_GetLastError
0x180006f4d  mov     ebx, eax
0x180006f4f  mov     [rsp+0E8h+var_C8], 5F7h
0x180006f57  jmp     loc_180006EA6
0x180006f5c  lea     rcx, [rsp+0E8h+var_98]
0x180006f61  call    cs:__imp_EfsDllGetUserInfo
0x180006f67  test    al, al
0x180006f69  jnz     short loc_180006F75
0x180006f6b  call    cs:__imp_GetLastError
0x180006f71  mov     ebx, eax
0x180006f73  jmp     short loc_180006FC5
0x180006f75  mov     r13d, esi
0x180006f78  xor     edx, edx
0x180006f7a  lea     rcx, [rsp+0E8h+var_98]
0x180006f7f  call    cs:__imp_EfsDllLoadUserProfile
0x180006f85  test    eax, eax
0x180006f87  jz      short loc_180006F6B
0x180006f89  mov     r15d, esi
0x180006f8c  mov     r9, [r14+8]
0x180006f90  mov     r8d, [r14]
0x180006f93  mov     rdx, [rsp+0E8h+var_B8]
0x180006f98  lea     rcx, [rsp+0E8h+var_98]
0x180006f9d  call    cs:__imp_EfsDllRemoveUsersFromFileSrv
0x180006fa3  mov     ebx, eax
0x180006fa5  mov     [rsp+0E8h+var_B0], eax
0x180006fa9  jmp     short loc_180006FC5
0x180006fab  mov     ebx, 57h ; 'W'
0x180006fb0  mov     [rsp+0E8h+var_B0], ebx
0x180006fb4  mov     esi, [rsp+0E8h+var_AC]
0x180006fb8  mov     r15d, esi
0x180006fbb  mov     r13d, esi
0x180006fbe  jmp     short loc_180006FC5
0x180006fc0  mov     ebx, 57h ; 'W'
0x180006fc5  test    r15d, r15d
0x180006fc8  jz      short loc_180006FD5
0x180006fca  lea     rcx, [rsp+0E8h+var_98]
0x180006fcf  call    cs:__imp_EfsDllUnloadUserProfile
0x180006fd5  test    r13d, r13d
0x180006fd8  jz      short loc_180006FE5
0x180006fda  lea     rcx, [rsp+0E8h+var_98]
0x180006fdf  call    cs:__imp_EfsDllFreeUserInfo
0x180006fe5  test    esi, esi
0x180006fe7  jz      short loc_180006FEF
0x180006fe9  call    cs:__imp_RpcRevertToSelf
0x180006fef  mov     rcx, [rsp+0E8h+var_B8]
0x180006ff4  test    rcx, rcx
0x180006ff7  jz      short loc_180006FFF
0x180006ff9  call    cs:__imp_EfsDllFreeHeap
0x180006fff  mov     eax, ebx
0x180007001  lea     r11, [rsp+0E8h+var_28]
0x180007009  mov     rbx, [r11+30h]
0x18000700d  mov     rsi, [r11+38h]
0x180007011  mov     rsp, r11
0x180007014  pop     r15
0x180007016  pop     r14
0x180007018  pop     r13
0x18000701a  pop     r12
0x18000701c  pop     rdi
0x18000701d  retn
```
