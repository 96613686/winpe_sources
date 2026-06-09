# EfsRpcRemoveUsersFromFile

- ea: `0x180007530`
- end: `0x1800077b6`
- name: `EfsRpcRemoveUsersFromFile`
- size: `646`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800037b8`
- `0x180007530`
- `0x180007f38`
- `0x18000bf0c`
- `0x18000c094`
- `0x18000d192`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076d8`
- `RPCRT4!RpcRevertToSelf` at `0x180007774`
- `RPCRT4!RpcRevertToSelf` at `0x180007774`
- `RPCRT4!RpcImpersonateClient` at `0x18000763c`
- `RPCRT4!RpcImpersonateClient` at `0x18000763c`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000774e`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000774e`
- `EFSCORE!EfsDllGetLocalFileName` at `0x18000761e`
- `EFSCORE!EfsDllGetLocalFileName` at `0x18000761e`
- `EFSCORE!EfsDllDisabled` at `0x180007596`
- `EFSCORE!EfsDllDisabled` at `0x180007596`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180007764`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180007764`
- `EFSCORE!EfsDllGetUserInfo` at `0x1800076c8`
- `EFSCORE!EfsDllGetUserInfo` at `0x1800076c8`
- `EFSCORE!EfsDllRemoveUsersFromFileSrv` at `0x180007716`
- `EFSCORE!EfsDllRemoveUsersFromFileSrv` at `0x180007716`
- `EFSCORE!EfsDllLoadUserProfile` at `0x1800076f2`
- `EFSCORE!EfsDllLoadUserProfile` at `0x1800076f2`
- `EFSCORE!EfsDllShareDecline` at `0x180007698`
- `EFSCORE!EfsDllShareDecline` at `0x180007698`
- `EFSCORE!EfsDllFreeHeap` at `0x18000778a`
- `EFSCORE!EfsDllFreeHeap` at `0x18000778a`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x18000757e`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x18000757e`

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
0x180007530  mov     [rsp+arg_0], rbx
0x180007535  mov     [rsp+arg_8], rsi
0x18000753a  push    rdi
0x18000753b  push    r12
0x18000753d  push    r13
0x18000753f  push    r14
0x180007541  push    r15
0x180007543  sub     rsp, 0C0h
0x18000754a  mov     r14, r8
0x18000754d  mov     r12, rdx
0x180007550  xor     edi, edi
0x180007552  mov     [rsp+0E8h+var_B8], rdi
0x180007557  xor     edx, edx; Val
0x180007559  lea     r8d, [rdi+70h]; Size
0x18000755d  lea     rcx, [rsp+0E8h+var_98]; void *
0x180007562  call    memset_0
0x180007567  mov     [rsp+0E8h+arg_18], di
0x18000756f  mov     esi, edi
0x180007571  mov     r15d, edi
0x180007574  mov     r13d, edi
0x180007577  lea     rcx, aFeclientEfsena_0; "feclient-EfsEnabled"
0x18000757e  call    cs:__imp_EfsDllIsNonEfsSKU
0x180007585  nop     dword ptr [rax+rax+00h]
0x18000758a  test    al, al
0x18000758c  jz      short loc_180007596
0x18000758e  lea     ebx, [rdi+32h]
0x180007591  jmp     loc_180007744
0x180007596  call    cs:__imp_EfsDllDisabled
0x18000759d  nop     dword ptr [rax+rax+00h]
0x1800075a2  test    al, al
0x1800075a4  jz      short loc_1800075B0
0x1800075a6  mov     ebx, 177Fh
0x1800075ab  jmp     loc_180007744
0x1800075b0  test    r14, r14
0x1800075b3  jz      loc_18000773F
0x1800075b9  test    r12, r12
0x1800075bc  jz      loc_18000773F
0x1800075c2  cmp     [r14+8], rdi
0x1800075c6  jz      loc_18000773F
0x1800075cc  cmp     dword ptr [r14], 1F4h
0x1800075d3  jbe     short loc_1800075DF
0x1800075d5  mov     ebx, 5
0x1800075da  jmp     loc_180007744
0x1800075df  call    EfsEnforceClientAuthentication
0x1800075e4  mov     ebx, eax
0x1800075e6  test    eax, eax
0x1800075e8  jz      short loc_18000760C
0x1800075ea  mov     [rsp+0E8h+var_C8], 5D4h
0x1800075f2  mov     r9d, 6
0x1800075f8  mov     r8d, eax
0x1800075fb  lea     rdx, EFS_API_ERROR
0x180007602  call    fnEfsLogTrace1
0x180007607  jmp     loc_180007744
0x18000760c  lea     r9, [rsp+0E8h+arg_18]
0x180007614  lea     r8, [rsp+0E8h+var_B8]
0x180007619  xor     edx, edx
0x18000761b  mov     rcx, r12
0x18000761e  call    cs:__imp_EfsDllGetLocalFileName
0x180007625  nop     dword ptr [rax+rax+00h]
0x18000762a  mov     ebx, eax
0x18000762c  test    eax, eax
0x18000762e  jz      short loc_18000763A
0x180007630  mov     [rsp+0E8h+var_C8], 5D9h
0x180007638  jmp     short loc_1800075F2
0x18000763a  xor     ecx, ecx; BindingHandle
0x18000763c  call    cs:__imp_RpcImpersonateClient
0x180007643  nop     dword ptr [rax+rax+00h]
0x180007648  mov     ebx, eax
0x18000764a  test    eax, eax
0x18000764c  jnz     loc_180007744
0x180007652  lea     esi, [rax+1]
0x180007655  mov     [rsp+0E8h+var_AC], esi
0x180007659  mov     rcx, [rsp+0E8h+var_B8]
0x18000765e  call    EfsEnsureLocalPath
0x180007663  mov     ebx, eax
0x180007665  test    eax, eax
0x180007667  jz      short loc_180007676
0x180007669  mov     [rsp+0E8h+var_C8], 5E4h
0x180007671  jmp     loc_1800075F2
0x180007676  call    EfspCheckForNetSession
0x18000767b  test    eax, eax
0x18000767d  jz      short loc_1800076C3
0x18000767f  cmp     [rsp+0E8h+arg_18], si
0x180007687  jz      loc_1800075D5
0x18000768d  mov     r8d, 82h
0x180007693  mov     edx, esi
0x180007695  mov     rcx, r12
0x180007698  call    cs:__imp_EfsDllShareDecline
0x18000769f  nop     dword ptr [rax+rax+00h]
0x1800076a4  test    eax, eax
0x1800076a6  jz      short loc_1800076C3
0x1800076a8  call    cs:__imp_GetLastError
0x1800076af  nop     dword ptr [rax+rax+00h]
0x1800076b4  mov     ebx, eax
0x1800076b6  mov     [rsp+0E8h+var_C8], 5F7h
0x1800076be  jmp     loc_1800075F2
0x1800076c3  lea     rcx, [rsp+0E8h+var_98]
0x1800076c8  call    cs:__imp_EfsDllGetUserInfo
0x1800076cf  nop     dword ptr [rax+rax+00h]
0x1800076d4  test    al, al
0x1800076d6  jnz     short loc_1800076E8
0x1800076d8  call    cs:__imp_GetLastError
0x1800076df  nop     dword ptr [rax+rax+00h]
0x1800076e4  mov     ebx, eax
0x1800076e6  jmp     short loc_180007744
0x1800076e8  mov     r13d, esi
0x1800076eb  xor     edx, edx
0x1800076ed  lea     rcx, [rsp+0E8h+var_98]
0x1800076f2  call    cs:__imp_EfsDllLoadUserProfile
0x1800076f9  nop     dword ptr [rax+rax+00h]
0x1800076fe  test    eax, eax
0x180007700  jz      short loc_1800076D8
0x180007702  mov     r15d, esi
0x180007705  mov     r9, [r14+8]
0x180007709  mov     r8d, [r14]
0x18000770c  mov     rdx, [rsp+0E8h+var_B8]
0x180007711  lea     rcx, [rsp+0E8h+var_98]
0x180007716  call    cs:__imp_EfsDllRemoveUsersFromFileSrv
0x18000771d  nop     dword ptr [rax+rax+00h]
0x180007722  mov     ebx, eax
0x180007724  mov     [rsp+0E8h+var_B0], eax
0x180007728  jmp     short loc_180007744
0x18000772a  mov     ebx, 57h ; 'W'
0x18000772f  mov     [rsp+0E8h+var_B0], ebx
0x180007733  mov     esi, [rsp+0E8h+var_AC]
0x180007737  mov     r15d, esi
0x18000773a  mov     r13d, esi
0x18000773d  jmp     short loc_180007744
0x18000773f  mov     ebx, 57h ; 'W'
0x180007744  test    r15d, r15d
0x180007747  jz      short loc_18000775A
0x180007749  lea     rcx, [rsp+0E8h+var_98]
0x18000774e  call    cs:__imp_EfsDllUnloadUserProfile
0x180007755  nop     dword ptr [rax+rax+00h]
0x18000775a  test    r13d, r13d
0x18000775d  jz      short loc_180007770
0x18000775f  lea     rcx, [rsp+0E8h+var_98]
0x180007764  call    cs:__imp_EfsDllFreeUserInfo
0x18000776b  nop     dword ptr [rax+rax+00h]
0x180007770  test    esi, esi
0x180007772  jz      short loc_180007780
0x180007774  call    cs:__imp_RpcRevertToSelf
0x18000777b  nop     dword ptr [rax+rax+00h]
0x180007780  mov     rcx, [rsp+0E8h+var_B8]
0x180007785  test    rcx, rcx
0x180007788  jz      short loc_180007796
0x18000778a  call    cs:__imp_EfsDllFreeHeap
0x180007791  nop     dword ptr [rax+rax+00h]
0x180007796  mov     eax, ebx
0x180007798  lea     r11, [rsp+0E8h+var_28]
0x1800077a0  mov     rbx, [r11+30h]
0x1800077a4  mov     rsi, [r11+38h]
0x1800077a8  mov     rsp, r11
0x1800077ab  pop     r15
0x1800077ad  pop     r14
0x1800077af  pop     r13
0x1800077b1  pop     r12
0x1800077b3  pop     rdi
0x1800077b4  retn
```
