# EfsRpcAddUsersToFileEx

- ea: `0x1800055b0`
- end: `0x180005848`
- name: `EfsRpcAddUsersToFileEx`
- size: `664`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180005580`

## callees

- `0x180003604`
- `0x1800055b0`
- `0x1800076b4`
- `0x180007ae8`
- `0x18000b308`
- `0x18000b480`
- `0x18000c392`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057d9`
- `RPCRT4!RpcRevertToSelf` at `0x180005818`
- `RPCRT4!RpcRevertToSelf` at `0x180005818`
- `RPCRT4!RpcImpersonateClient` at `0x18000570c`
- `RPCRT4!RpcImpersonateClient` at `0x18000570c`
- `ntdll!RtlValidSid` at `0x1800056bf`
- `ntdll!RtlValidSid` at `0x1800056bf`
- `EFSCORE!EfsDllAddUsersToFileSrv` at `0x1800057fc`
- `EFSCORE!EfsDllAddUsersToFileSrv` at `0x1800057fc`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180005808`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180005808`
- `EFSCORE!EfsDllGetLocalFileName` at `0x1800056e0`
- `EFSCORE!EfsDllGetLocalFileName` at `0x1800056e0`
- `EFSCORE!EfsDllDisabled` at `0x180005608`
- `EFSCORE!EfsDllDisabled` at `0x180005608`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180005812`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180005812`
- `EFSCORE!EfsDllGetUserInfo` at `0x1800057b5`
- `EFSCORE!EfsDllGetUserInfo` at `0x1800057b5`
- `EFSCORE!EfsDllLoadUserProfile` at `0x1800057cf`
- `EFSCORE!EfsDllLoadUserProfile` at `0x1800057cf`
- `EFSCORE!EfsDllShareDecline` at `0x18000577d`
- `EFSCORE!EfsDllShareDecline` at `0x18000577d`
- `EFSCORE!EfsDllFreeHeap` at `0x18000582e`
- `EFSCORE!EfsDllFreeHeap` at `0x18000582e`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x1800055f4`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x1800055f4`

## pseudocode

```c
__int64 __fastcall EfsRpcAddUsersToFileEx(__int64 a1, int a2, __int64 a3, __int64 a4, unsigned int *a5)
{
  DWORD LastError; // ebx
  DWORD v9; // eax
  int v10; // ecx
  __int64 v11; // rsi
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rax
  void *v15; // rcx
  DWORD LocalFileName; // eax
  int v17; // ecx
  bool v18; // si
  RPC_STATUS v19; // eax
  int v20; // ecx
  DWORD v21; // eax
  int v22; // ecx
  int v23; // ecx
  DWORD IsValidNetworkProtSeq; // eax
  int v25; // ecx
  __int16 v27; // [rsp+30h] [rbp-61h] BYREF
  __int64 v28; // [rsp+38h] [rbp-59h] BYREF
  _BYTE v29[160]; // [rsp+40h] [rbp-51h] BYREF

  v28 = 0;
  memset_0(v29, 0, 0x70u);
  v27 = 0;
  if ( (unsigned __int8)EfsDllIsNonEfsSKU(L"feclient-EfsEnabled") )
  {
    LastError = 50;
    goto LABEL_40;
  }
  if ( (unsigned __int8)EfsDllDisabled() )
  {
    LastError = 6015;
    goto LABEL_40;
  }
  if ( !a5 )
  {
    LastError = 87;
    goto LABEL_40;
  }
  v9 = EfsEnforceClientAuthentication();
  LastError = v9;
  if ( v9 )
  {
    fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, v9, 6, 72);
    goto LABEL_40;
  }
  if ( *a5 > 0x1F4 )
    goto LABEL_39;
  v11 = *((_QWORD *)a5 + 1);
  if ( (*a5 == 0) != (v11 == 0) )
    goto LABEL_39;
  v12 = 0;
  if ( !*a5 )
  {
LABEL_19:
    LocalFileName = EfsDllGetLocalFileName(a4, 0, &v28, &v27);
    LastError = LocalFileName;
    if ( LocalFileName )
    {
      fnEfsLogTrace1(v17, (unsigned int)EFS_API_ERROR, LocalFileName, 6, 86);
      goto LABEL_40;
    }
    v18 = v27 == 1;
    v19 = RpcImpersonateClient(0);
    LastError = v19;
    if ( v19 )
    {
      fnEfsLogTrace1(v20, (unsigned int)EFS_API_ERROR, v19, 6, 95);
      goto LABEL_40;
    }
    v21 = EfsEnsureLocalPath(v28);
    LastError = v21;
    if ( v21 )
    {
      fnEfsLogTrace1(v22, (unsigned int)EFS_API_ERROR, v21, 6, 101);
LABEL_38:
      RpcRevertToSelf();
      goto LABEL_40;
    }
    if ( (unsigned int)EfspCheckForNetSession() )
    {
      if ( v27 == 1 )
      {
        LastError = 5;
        goto LABEL_38;
      }
      if ( (unsigned int)EfsDllShareDecline(a4, 1, 130) )
      {
        LastError = GetLastError();
        fnEfsLogTrace1(v23, (unsigned int)EFS_API_ERROR, LastError, 6, 120);
        goto LABEL_38;
      }
      IsValidNetworkProtSeq = EfspIsValidNetworkProtSeq(a1);
      LastError = IsValidNetworkProtSeq;
      if ( IsValidNetworkProtSeq )
      {
        fnEfsLogTrace1(v25, (unsigned int)EFS_API_ERROR, IsValidNetworkProtSeq, 6, 129);
        goto LABEL_38;
      }
    }
    if ( (unsigned __int8)EfsDllGetUserInfo(v29) )
    {
      if ( (unsigned int)EfsDllLoadUserProfile(v29, 0) )
      {
        LastError = EfsDllAddUsersToFileSrv(v29, v28, *a5, *((_QWORD *)a5 + 1), a2, v18);
        EfsDllUnloadUserProfile(v29);
      }
      else
      {
        LastError = GetLastError();
      }
      EfsDllFreeUserInfo(v29);
    }
    else
    {
      LastError = GetLastError();
    }
    goto LABEL_38;
  }
  while ( 1 )
  {
    v13 = *(_QWORD *)(v11 + 8 * v12);
    if ( !v13 )
      break;
    v14 = *(_QWORD *)(v13 + 16);
    if ( !v14 )
      break;
    if ( !*(_DWORD *)(v14 + 4) )
      break;
    if ( !*(_QWORD *)(v14 + 8) )
      break;
    v15 = *(void **)(v13 + 8);
    if ( v15 )
    {
      if ( !RtlValidSid(v15) )
        break;
    }
    v12 = (unsigned int)(v12 + 1);
    if ( (unsigned int)v12 >= *a5 )
      goto LABEL_19;
  }
LABEL_39:
  LastError = 5;
LABEL_40:
  if ( v28 )
    EfsDllFreeHeap();
  return LastError;
}

```

## disassembly

```asm
0x1800055b0  push    rbp
0x1800055b2  push    rbx
0x1800055b3  push    rsi
0x1800055b4  push    rdi
0x1800055b5  push    r12
0x1800055b7  push    r14
0x1800055b9  push    r15
0x1800055bb  lea     rbp, [rsp-1Fh]
0x1800055c0  sub     rsp, 0B0h
0x1800055c7  mov     r12d, edx
0x1800055ca  mov     [rbp+4Fh+var_A8], 0
0x1800055d2  xor     edx, edx; Val
0x1800055d4  mov     r15, rcx
0x1800055d7  lea     rcx, [rbp+4Fh+var_A0]; void *
0x1800055db  mov     r14, r9
0x1800055de  lea     r8d, [rdx+70h]; Size
0x1800055e2  call    memset_0
0x1800055e7  xor     eax, eax
0x1800055e9  lea     rcx, aFeclientEfsena_0; "feclient-EfsEnabled"
0x1800055f0  mov     [rbp+4Fh+var_B0], ax
0x1800055f4  call    cs:__imp_EfsDllIsNonEfsSKU
0x1800055fa  test    al, al
0x1800055fc  jz      short loc_180005608
0x1800055fe  mov     ebx, 32h ; '2'
0x180005603  jmp     loc_180005825
0x180005608  call    cs:__imp_EfsDllDisabled
0x18000560e  test    al, al
0x180005610  jz      short loc_18000561C
0x180005612  mov     ebx, 177Fh
0x180005617  jmp     loc_180005825
0x18000561c  mov     rdi, [rbp+4Fh+arg_20]
0x180005620  test    rdi, rdi
0x180005623  jnz     short loc_18000562D
0x180005625  lea     ebx, [rdi+57h]
0x180005628  jmp     loc_180005825
0x18000562d  call    EfsEnforceClientAuthentication
0x180005632  mov     ebx, eax
0x180005634  test    eax, eax
0x180005636  jz      short loc_18000565A
0x180005638  mov     [rsp+0E0h+var_C0], 648h
0x180005640  mov     r9d, 6
0x180005646  lea     rdx, EFS_API_ERROR
0x18000564d  mov     r8d, eax
0x180005650  call    fnEfsLogTrace1
0x180005655  jmp     loc_180005825
0x18000565a  cmp     dword ptr [rdi], 1F4h
0x180005660  ja      loc_180005820
0x180005666  mov     rsi, [rdi+8]
0x18000566a  xor     ecx, ecx
0x18000566c  test    rsi, rsi
0x18000566f  setz    cl
0x180005672  xor     eax, eax
0x180005674  cmp     [rdi], eax
0x180005676  setz    al
0x180005679  cmp     eax, ecx
0x18000567b  jnz     loc_180005820
0x180005681  xor     ebx, ebx
0x180005683  cmp     [rdi], ebx
0x180005685  jbe     short loc_1800056D3
0x180005687  mov     rcx, [rsi+rbx*8]
0x18000568b  test    rcx, rcx
0x18000568e  jz      loc_180005820
0x180005694  mov     rax, [rcx+10h]
0x180005698  test    rax, rax
0x18000569b  jz      loc_180005820
0x1800056a1  cmp     dword ptr [rax+4], 0
0x1800056a5  jz      loc_180005820
0x1800056ab  cmp     qword ptr [rax+8], 0
0x1800056b0  jz      loc_180005820
0x1800056b6  mov     rcx, [rcx+8]; Sid
0x1800056ba  test    rcx, rcx
0x1800056bd  jz      short loc_1800056CD
0x1800056bf  call    cs:__imp_RtlValidSid
0x1800056c5  test    al, al
0x1800056c7  jz      loc_180005820
0x1800056cd  inc     ebx
0x1800056cf  cmp     ebx, [rdi]
0x1800056d1  jb      short loc_180005687
0x1800056d3  lea     r9, [rbp+4Fh+var_B0]
0x1800056d7  xor     edx, edx
0x1800056d9  lea     r8, [rbp+4Fh+var_A8]
0x1800056dd  mov     rcx, r14
0x1800056e0  call    cs:__imp_EfsDllGetLocalFileName
0x1800056e6  mov     ebx, eax
0x1800056e8  test    eax, eax
0x1800056ea  jz      short loc_1800056F9
0x1800056ec  mov     [rsp+0E0h+var_C0], 656h
0x1800056f4  jmp     loc_180005640
0x1800056f9  xor     al, al
0x1800056fb  movzx   esi, al
0x1800056fe  mov     eax, 1
0x180005703  cmp     ax, [rbp+4Fh+var_B0]
0x180005707  cmovz   esi, eax
0x18000570a  xor     ecx, ecx; BindingHandle
0x18000570c  call    cs:__imp_RpcImpersonateClient
0x180005712  mov     ebx, eax
0x180005714  test    eax, eax
0x180005716  jz      short loc_180005725
0x180005718  mov     [rsp+0E0h+var_C0], 65Fh
0x180005720  jmp     loc_180005640
0x180005725  mov     rcx, [rbp+4Fh+var_A8]
0x180005729  call    EfsEnsureLocalPath
0x18000572e  mov     ebx, eax
0x180005730  test    eax, eax
0x180005732  jz      short loc_180005756
0x180005734  mov     [rsp+0E0h+var_C0], 665h
0x18000573c  mov     r9d, 6
0x180005742  lea     rdx, EFS_API_ERROR
0x180005749  mov     r8d, eax
0x18000574c  call    fnEfsLogTrace1
0x180005751  jmp     loc_180005818
0x180005756  call    EfspCheckForNetSession
0x18000575b  test    eax, eax
0x18000575d  jz      short loc_1800057B1
0x18000575f  mov     eax, 1
0x180005764  cmp     [rbp+4Fh+var_B0], ax
0x180005768  jnz     short loc_180005772
0x18000576a  lea     ebx, [rax+4]
0x18000576d  jmp     loc_180005818
0x180005772  mov     r8d, 82h
0x180005778  mov     edx, eax
0x18000577a  mov     rcx, r14
0x18000577d  call    cs:__imp_EfsDllShareDecline
0x180005783  test    eax, eax
0x180005785  jz      short loc_180005799
0x180005787  call    cs:__imp_GetLastError
0x18000578d  mov     ebx, eax
0x18000578f  mov     [rsp+0E0h+var_C0], 678h
0x180005797  jmp     short loc_18000573C
0x180005799  mov     rcx, r15
0x18000579c  call    EfspIsValidNetworkProtSeq
0x1800057a1  mov     ebx, eax
0x1800057a3  test    eax, eax
0x1800057a5  jz      short loc_1800057B1
0x1800057a7  mov     [rsp+0E0h+var_C0], 681h
0x1800057af  jmp     short loc_18000573C
0x1800057b1  lea     rcx, [rbp+4Fh+var_A0]
0x1800057b5  call    cs:__imp_EfsDllGetUserInfo
0x1800057bb  test    al, al
0x1800057bd  jnz     short loc_1800057C9
0x1800057bf  call    cs:__imp_GetLastError
0x1800057c5  mov     ebx, eax
0x1800057c7  jmp     short loc_180005818
0x1800057c9  xor     edx, edx
0x1800057cb  lea     rcx, [rbp+4Fh+var_A0]
0x1800057cf  call    cs:__imp_EfsDllLoadUserProfile
0x1800057d5  test    eax, eax
0x1800057d7  jnz     short loc_1800057E3
0x1800057d9  call    cs:__imp_GetLastError
0x1800057df  mov     ebx, eax
0x1800057e1  jmp     short loc_18000580E
0x1800057e3  mov     r9, [rdi+8]
0x1800057e7  lea     rcx, [rbp+4Fh+var_A0]
0x1800057eb  mov     r8d, [rdi]
0x1800057ee  mov     rdx, [rbp+4Fh+var_A8]
0x1800057f2  mov     [rsp+0E0h+var_B8], sil
0x1800057f7  mov     [rsp+0E0h+var_C0], r12d
0x1800057fc  call    cs:__imp_EfsDllAddUsersToFileSrv
0x180005802  mov     ebx, eax
0x180005804  lea     rcx, [rbp+4Fh+var_A0]
0x180005808  call    cs:__imp_EfsDllUnloadUserProfile
0x18000580e  lea     rcx, [rbp+4Fh+var_A0]
0x180005812  call    cs:__imp_EfsDllFreeUserInfo
0x180005818  call    cs:__imp_RpcRevertToSelf
0x18000581e  jmp     short loc_180005825
0x180005820  mov     ebx, 5
0x180005825  mov     rcx, [rbp+4Fh+var_A8]
0x180005829  test    rcx, rcx
0x18000582c  jz      short loc_180005834
0x18000582e  call    cs:__imp_EfsDllFreeHeap
0x180005834  mov     eax, ebx
0x180005836  add     rsp, 0B0h
0x18000583d  pop     r15
0x18000583f  pop     r14
0x180005841  pop     r12
0x180005843  pop     rdi
0x180005844  pop     rsi
0x180005845  pop     rbx
0x180005846  pop     rbp
0x180005847  retn
```
