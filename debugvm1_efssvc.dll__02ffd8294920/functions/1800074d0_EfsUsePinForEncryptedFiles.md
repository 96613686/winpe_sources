# EfsUsePinForEncryptedFiles

- ea: `0x1800074d0`
- end: `0x1800076ac`
- name: `EfsUsePinForEncryptedFiles`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003604`
- `0x1800074d0`
- `0x18000b308`
- `0x18000c392`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075f3`
- `RPCRT4!RpcRevertToSelf` at `0x180007688`
- `RPCRT4!RpcRevertToSelf` at `0x180007688`
- `RPCRT4!RpcImpersonateClient` at `0x18000757e`
- `RPCRT4!RpcImpersonateClient` at `0x18000757e`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000759e`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18000759e`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180007653`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180007653`
- `EFSCORE!EfsDllUsePinForEncryptedFilesSrv` at `0x180007625`
- `EFSCORE!EfsDllUsePinForEncryptedFilesSrv` at `0x180007625`
- `EFSCORE!EfsDllDisabled` at `0x180007512`
- `EFSCORE!EfsDllDisabled` at `0x180007512`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000765e`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000765e`
- `EFSCORE!EfsDllGetUserInfo` at `0x1800075c0`
- `EFSCORE!EfsDllGetUserInfo` at `0x1800075c0`
- `EFSCORE!EfsDllLoadUserProfile` at `0x1800075e9`
- `EFSCORE!EfsDllLoadUserProfile` at `0x1800075e9`

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
0x1800074d0  mov     rax, rsp
0x1800074d3  mov     [rax+8], rbx
0x1800074d7  mov     [rax+10h], rsi
0x1800074db  push    rdi
0x1800074dc  sub     rsp, 0A0h
0x1800074e3  mov     rsi, rdx
0x1800074e6  mov     dword ptr [rax+20h], 0
0x1800074ed  xor     edx, edx; Val
0x1800074ef  lea     rcx, [rax-78h]; void *
0x1800074f3  mov     rdi, r8
0x1800074f6  lea     r8d, [rdx+70h]; Size
0x1800074fa  call    memset_0
0x1800074ff  cmp     cs:EfsServerInitialized, 0
0x180007506  jnz     short loc_180007512
0x180007508  mov     ebx, 32h ; '2'
0x18000750d  jmp     loc_180007695
0x180007512  call    cs:__imp_EfsDllDisabled
0x180007518  test    al, al
0x18000751a  jz      short loc_180007526
0x18000751c  mov     ebx, 177Fh
0x180007521  jmp     loc_180007695
0x180007526  call    EfsEnforceClientAuthentication
0x18000752b  mov     ebx, eax
0x18000752d  test    eax, eax
0x18000752f  jz      short loc_180007553
0x180007531  mov     [rsp+0A8h+var_88], 88Fh
0x180007539  mov     r9d, 6
0x18000753f  lea     rdx, EFS_API_ERROR
0x180007546  mov     r8d, eax
0x180007549  call    fnEfsLogTrace1
0x18000754e  jmp     loc_180007695
0x180007553  cmp     qword ptr [rsi+8], 0
0x180007558  jz      loc_180007690
0x18000755e  cmp     dword ptr [rsi], 0
0x180007561  jz      loc_180007690
0x180007567  cmp     qword ptr [rdi+8], 0
0x18000756c  jz      loc_180007690
0x180007572  cmp     dword ptr [rdi+4], 0
0x180007576  jz      loc_180007690
0x18000757c  xor     ecx, ecx; BindingHandle
0x18000757e  call    cs:__imp_RpcImpersonateClient
0x180007584  mov     ebx, eax
0x180007586  test    eax, eax
0x180007588  jz      short loc_180007594
0x18000758a  mov     [rsp+0A8h+var_88], 89Bh
0x180007592  jmp     short loc_180007539
0x180007594  lea     rdx, [rsp+0A8h+ClientLocalFlag]; ClientLocalFlag
0x18000759c  xor     ecx, ecx; BindingHandle
0x18000759e  call    cs:__imp_I_RpcBindingIsClientLocal
0x1800075a4  mov     ebx, eax
0x1800075a6  test    eax, eax
0x1800075a8  jnz     loc_18000766B
0x1800075ae  cmp     [rsp+0A8h+ClientLocalFlag], eax
0x1800075b5  jz      loc_180007666
0x1800075bb  lea     rcx, [rsp+0A8h+var_78]
0x1800075c0  call    cs:__imp_EfsDllGetUserInfo
0x1800075c6  test    al, al
0x1800075c8  jnz     short loc_1800075E2
0x1800075ca  call    cs:__imp_GetLastError
0x1800075d0  mov     ebx, eax
0x1800075d2  mov     [rsp+0A8h+var_88], 8ADh
0x1800075da  mov     r8d, eax
0x1800075dd  jmp     loc_180007676
0x1800075e2  xor     edx, edx
0x1800075e4  lea     rcx, [rsp+0A8h+var_78]
0x1800075e9  call    cs:__imp_EfsDllLoadUserProfile
0x1800075ef  test    eax, eax
0x1800075f1  jnz     short loc_18000761A
0x1800075f3  call    cs:__imp_GetLastError
0x1800075f9  mov     r9d, 6
0x1800075ff  mov     [rsp+0A8h+var_88], 8B4h
0x180007607  mov     r8d, eax
0x18000760a  lea     rdx, EFS_API_ERROR
0x180007611  mov     ebx, eax
0x180007613  call    fnEfsLogTrace1
0x180007618  jmp     short loc_180007659
0x18000761a  mov     r8, rdi
0x18000761d  lea     rcx, [rsp+0A8h+var_78]
0x180007622  mov     rdx, rsi
0x180007625  call    cs:__imp_EfsDllUsePinForEncryptedFilesSrv
0x18000762b  mov     ebx, eax
0x18000762d  test    eax, eax
0x18000762f  jz      short loc_18000764E
0x180007631  mov     r9d, 6
0x180007637  mov     [rsp+0A8h+var_88], 8BAh
0x18000763f  mov     r8d, eax
0x180007642  lea     rdx, EFS_API_ERROR
0x180007649  call    fnEfsLogTrace1
0x18000764e  lea     rcx, [rsp+0A8h+var_78]
0x180007653  call    cs:__imp_EfsDllUnloadUserProfile
0x180007659  lea     rcx, [rsp+0A8h+var_78]
0x18000765e  call    cs:__imp_EfsDllFreeUserInfo
0x180007664  jmp     short loc_180007688
0x180007666  mov     ebx, 5
0x18000766b  mov     [rsp+0A8h+var_88], 8A7h
0x180007673  mov     r8d, ebx
0x180007676  mov     r9d, 6
0x18000767c  lea     rdx, EFS_API_ERROR
0x180007683  call    fnEfsLogTrace1
0x180007688  call    cs:__imp_RpcRevertToSelf
0x18000768e  jmp     short loc_180007695
0x180007690  mov     ebx, 57h ; 'W'
0x180007695  lea     r11, [rsp+0A8h+var_8]
0x18000769d  mov     eax, ebx
0x18000769f  mov     rbx, [r11+10h]
0x1800076a3  mov     rsi, [r11+18h]
0x1800076a7  mov     rsp, r11
0x1800076aa  pop     rdi
0x1800076ab  retn
```
