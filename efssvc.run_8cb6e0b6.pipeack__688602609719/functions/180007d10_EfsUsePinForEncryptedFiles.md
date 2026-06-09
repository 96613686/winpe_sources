# EfsUsePinForEncryptedFiles

- ea: `0x180007d10`
- end: `0x180007f2f`
- name: `EfsUsePinForEncryptedFiles`
- size: `543`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800037b8`
- `0x180007d10`
- `0x18000bf0c`
- `0x18000d192`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e57`
- `RPCRT4!RpcRevertToSelf` at `0x180007f04`
- `RPCRT4!RpcRevertToSelf` at `0x180007f04`
- `RPCRT4!RpcImpersonateClient` at `0x180007dc4`
- `RPCRT4!RpcImpersonateClient` at `0x180007dc4`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180007dea`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180007dea`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180007ec3`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180007ec3`
- `EFSCORE!EfsDllUsePinForEncryptedFilesSrv` at `0x180007e8f`
- `EFSCORE!EfsDllUsePinForEncryptedFilesSrv` at `0x180007e8f`
- `EFSCORE!EfsDllDisabled` at `0x180007d52`
- `EFSCORE!EfsDllDisabled` at `0x180007d52`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180007ed4`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180007ed4`
- `EFSCORE!EfsDllGetUserInfo` at `0x180007e12`
- `EFSCORE!EfsDllGetUserInfo` at `0x180007e12`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180007e47`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180007e47`

## pseudocode

```c
__int64 __fastcall EfsUsePinForEncryptedFiles(__int64 a1, __int64 a2, __int64 a3)
{
  DWORD IsClientLocal; // ebx
  DWORD v6; // eax
  int v7; // ecx
  RPC_STATUS v8; // eax
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  DWORD v13; // eax
  int v14; // ecx
  _BYTE v16[112]; // [rsp+30h] [rbp-78h] BYREF
  unsigned int ClientLocalFlag; // [rsp+C8h] [rbp+20h] BYREF

  ClientLocalFlag = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( EfsServerInitialized )
  {
    if ( (unsigned __int8)EfsDllDisabled() )
      return 6015;
    v6 = EfsEnforceClientAuthentication();
    IsClientLocal = v6;
    if ( v6 )
    {
      fnEfsLogTrace1(v7, (unsigned int)EFS_API_ERROR, v6, 6, 143);
      return IsClientLocal;
    }
    if ( !*(_QWORD *)(a2 + 8) || !*(_DWORD *)a2 || !*(_QWORD *)(a3 + 8) || !*(_DWORD *)(a3 + 4) )
      return 87;
    v8 = RpcImpersonateClient(0);
    IsClientLocal = v8;
    if ( v8 )
    {
      fnEfsLogTrace1(v9, (unsigned int)EFS_API_ERROR, v8, 6, 155);
      return IsClientLocal;
    }
    IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
    if ( !IsClientLocal )
    {
      if ( ClientLocalFlag )
      {
        if ( (unsigned __int8)EfsDllGetUserInfo(v16) )
        {
          if ( (unsigned int)EfsDllLoadUserProfile(v16, 0) )
          {
            v13 = EfsDllUsePinForEncryptedFilesSrv(v16, a2, a3);
            IsClientLocal = v13;
            if ( v13 )
              fnEfsLogTrace1(v14, (unsigned int)EFS_API_ERROR, v13, 6, 186);
            EfsDllUnloadUserProfile(v16);
          }
          else
          {
            IsClientLocal = GetLastError();
            fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, IsClientLocal, 6, 180);
          }
          EfsDllFreeUserInfo(v16);
        }
        else
        {
          IsClientLocal = GetLastError();
          fnEfsLogTrace1(v11, (unsigned int)EFS_API_ERROR, IsClientLocal, 6, 173);
        }
        goto LABEL_26;
      }
      IsClientLocal = 5;
    }
    fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, IsClientLocal, 6, 167);
LABEL_26:
    RpcRevertToSelf();
    return IsClientLocal;
  }
  return 50;
}

```

## disassembly

```asm
0x180007d10  mov     rax, rsp
0x180007d13  mov     [rax+8], rbx
0x180007d17  mov     [rax+10h], rsi
0x180007d1b  push    rdi
0x180007d1c  sub     rsp, 0A0h
0x180007d23  mov     rsi, rdx
0x180007d26  mov     dword ptr [rax+20h], 0
0x180007d2d  xor     edx, edx; Val
0x180007d2f  lea     rcx, [rax-78h]; void *
0x180007d33  mov     rdi, r8
0x180007d36  lea     r8d, [rdx+70h]; Size
0x180007d3a  call    memset_0
0x180007d3f  cmp     cs:EfsServerInitialized, 0
0x180007d46  jnz     short loc_180007D52
0x180007d48  mov     ebx, 32h ; '2'
0x180007d4d  jmp     loc_180007F17
0x180007d52  call    cs:__imp_EfsDllDisabled
0x180007d59  nop     dword ptr [rax+rax+00h]
0x180007d5e  test    al, al
0x180007d60  jz      short loc_180007D6C
0x180007d62  mov     ebx, 177Fh
0x180007d67  jmp     loc_180007F17
0x180007d6c  call    EfsEnforceClientAuthentication
0x180007d71  mov     ebx, eax
0x180007d73  test    eax, eax
0x180007d75  jz      short loc_180007D99
0x180007d77  mov     [rsp+0A8h+var_88], 88Fh
0x180007d7f  mov     r9d, 6
0x180007d85  lea     rdx, EFS_API_ERROR
0x180007d8c  mov     r8d, eax
0x180007d8f  call    fnEfsLogTrace1
0x180007d94  jmp     loc_180007F17
0x180007d99  cmp     qword ptr [rsi+8], 0
0x180007d9e  jz      loc_180007F12
0x180007da4  cmp     dword ptr [rsi], 0
0x180007da7  jz      loc_180007F12
0x180007dad  cmp     qword ptr [rdi+8], 0
0x180007db2  jz      loc_180007F12
0x180007db8  cmp     dword ptr [rdi+4], 0
0x180007dbc  jz      loc_180007F12
0x180007dc2  xor     ecx, ecx; BindingHandle
0x180007dc4  call    cs:__imp_RpcImpersonateClient
0x180007dcb  nop     dword ptr [rax+rax+00h]
0x180007dd0  mov     ebx, eax
0x180007dd2  test    eax, eax
0x180007dd4  jz      short loc_180007DE0
0x180007dd6  mov     [rsp+0A8h+var_88], 89Bh
0x180007dde  jmp     short loc_180007D7F
0x180007de0  lea     rdx, [rsp+0A8h+ClientLocalFlag]; ClientLocalFlag
0x180007de8  xor     ecx, ecx; BindingHandle
0x180007dea  call    cs:__imp_I_RpcBindingIsClientLocal
0x180007df1  nop     dword ptr [rax+rax+00h]
0x180007df6  mov     ebx, eax
0x180007df8  test    eax, eax
0x180007dfa  jnz     loc_180007EE7
0x180007e00  cmp     [rsp+0A8h+ClientLocalFlag], eax
0x180007e07  jz      loc_180007EE2
0x180007e0d  lea     rcx, [rsp+0A8h+var_78]
0x180007e12  call    cs:__imp_EfsDllGetUserInfo
0x180007e19  nop     dword ptr [rax+rax+00h]
0x180007e1e  test    al, al
0x180007e20  jnz     short loc_180007E40
0x180007e22  call    cs:__imp_GetLastError
0x180007e29  nop     dword ptr [rax+rax+00h]
0x180007e2e  mov     ebx, eax
0x180007e30  mov     [rsp+0A8h+var_88], 8ADh
0x180007e38  mov     r8d, eax
0x180007e3b  jmp     loc_180007EF2
0x180007e40  xor     edx, edx
0x180007e42  lea     rcx, [rsp+0A8h+var_78]
0x180007e47  call    cs:__imp_EfsDllLoadUserProfile
0x180007e4e  nop     dword ptr [rax+rax+00h]
0x180007e53  test    eax, eax
0x180007e55  jnz     short loc_180007E84
0x180007e57  call    cs:__imp_GetLastError
0x180007e5e  nop     dword ptr [rax+rax+00h]
0x180007e63  mov     r9d, 6
0x180007e69  mov     [rsp+0A8h+var_88], 8B4h
0x180007e71  mov     r8d, eax
0x180007e74  lea     rdx, EFS_API_ERROR
0x180007e7b  mov     ebx, eax
0x180007e7d  call    fnEfsLogTrace1
0x180007e82  jmp     short loc_180007ECF
0x180007e84  mov     r8, rdi
0x180007e87  lea     rcx, [rsp+0A8h+var_78]
0x180007e8c  mov     rdx, rsi
0x180007e8f  call    cs:__imp_EfsDllUsePinForEncryptedFilesSrv
0x180007e96  nop     dword ptr [rax+rax+00h]
0x180007e9b  mov     ebx, eax
0x180007e9d  test    eax, eax
0x180007e9f  jz      short loc_180007EBE
0x180007ea1  mov     r9d, 6
0x180007ea7  mov     [rsp+0A8h+var_88], 8BAh
0x180007eaf  mov     r8d, eax
0x180007eb2  lea     rdx, EFS_API_ERROR
0x180007eb9  call    fnEfsLogTrace1
0x180007ebe  lea     rcx, [rsp+0A8h+var_78]
0x180007ec3  call    cs:__imp_EfsDllUnloadUserProfile
0x180007eca  nop     dword ptr [rax+rax+00h]
0x180007ecf  lea     rcx, [rsp+0A8h+var_78]
0x180007ed4  call    cs:__imp_EfsDllFreeUserInfo
0x180007edb  nop     dword ptr [rax+rax+00h]
0x180007ee0  jmp     short loc_180007F04
0x180007ee2  mov     ebx, 5
0x180007ee7  mov     [rsp+0A8h+var_88], 8A7h
0x180007eef  mov     r8d, ebx
0x180007ef2  mov     r9d, 6
0x180007ef8  lea     rdx, EFS_API_ERROR
0x180007eff  call    fnEfsLogTrace1
0x180007f04  call    cs:__imp_RpcRevertToSelf
0x180007f0b  nop     dword ptr [rax+rax+00h]
0x180007f10  jmp     short loc_180007F17
0x180007f12  mov     ebx, 57h ; 'W'
0x180007f17  lea     r11, [rsp+0A8h+var_8]
0x180007f1f  mov     eax, ebx
0x180007f21  mov     rbx, [r11+10h]
0x180007f25  mov     rsi, [r11+18h]
0x180007f29  mov     rsp, r11
0x180007f2c  pop     rdi
0x180007f2d  retn
```
