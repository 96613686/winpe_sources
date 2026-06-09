# EfsRpcAddUsersToFileEx

- ea: `0x1800059a0`
- end: `0x180005c9c`
- name: `EfsRpcAddUsersToFileEx`
- size: `764`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180005970`

## callees

- `0x1800037b8`
- `0x1800059a0`
- `0x180007f38`
- `0x180008404`
- `0x18000bf0c`
- `0x18000c094`
- `0x18000d192`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005be2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005be2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c08`
- `RPCRT4!RpcRevertToSelf` at `0x180005c5f`
- `RPCRT4!RpcRevertToSelf` at `0x180005c5f`
- `RPCRT4!RpcImpersonateClient` at `0x180005b14`
- `RPCRT4!RpcImpersonateClient` at `0x180005b14`
- `ntdll!RtlValidSid` at `0x180005abb`
- `ntdll!RtlValidSid` at `0x180005abb`
- `EFSCORE!EfsDllAddUsersToFileSrv` at `0x180005c31`
- `EFSCORE!EfsDllAddUsersToFileSrv` at `0x180005c31`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180005c43`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180005c43`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180005ae2`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180005ae2`
- `EFSCORE!EfsDllDisabled` at `0x1800059fe`
- `EFSCORE!EfsDllDisabled` at `0x1800059fe`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180005c53`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180005c53`
- `EFSCORE!EfsDllGetUserInfo` at `0x180005bd2`
- `EFSCORE!EfsDllGetUserInfo` at `0x180005bd2`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180005bf8`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180005bf8`
- `EFSCORE!EfsDllShareDecline` at `0x180005b8b`
- `EFSCORE!EfsDllShareDecline` at `0x180005b8b`
- `EFSCORE!EfsDllFreeHeap` at `0x180005c7b`
- `EFSCORE!EfsDllFreeHeap` at `0x180005c7b`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x1800059e4`
- `EFSCORE!EfsDllIsNonEfsSKU` at `0x1800059e4`

## pseudocode

```c
__int64 __fastcall EfsRpcAddUsersToFileEx(__int64 a1, int a2, __int64 a3, __int64 a4, unsigned int *a5)
{
  DWORD LastError; // ebx
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rax
  void *v15; // rcx
  unsigned int LocalFileName; // eax
  __int64 v17; // rcx
  bool v18; // si
  RPC_STATUS v19; // eax
  __int64 v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  unsigned int IsValidNetworkProtSeq; // eax
  __int64 v25; // rcx
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
    fnEfsLogTrace1(v10, (__int64)EFS_API_ERROR, v9, 6, 72);
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
      fnEfsLogTrace1(v17, (__int64)EFS_API_ERROR, LocalFileName, 6, 86);
      goto LABEL_40;
    }
    v18 = v27 == 1;
    v19 = RpcImpersonateClient(0);
    LastError = v19;
    if ( v19 )
    {
      fnEfsLogTrace1(v20, (__int64)EFS_API_ERROR, v19, 6, 95);
      goto LABEL_40;
    }
    v21 = EfsEnsureLocalPath(v28);
    LastError = v21;
    if ( v21 )
    {
      fnEfsLogTrace1(v22, (__int64)EFS_API_ERROR, v21, 6, 101);
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
        fnEfsLogTrace1(v23, (__int64)EFS_API_ERROR, LastError, 6, 120);
        goto LABEL_38;
      }
      IsValidNetworkProtSeq = EfspIsValidNetworkProtSeq(a1);
      LastError = IsValidNetworkProtSeq;
      if ( IsValidNetworkProtSeq )
      {
        fnEfsLogTrace1(v25, (__int64)EFS_API_ERROR, IsValidNetworkProtSeq, 6, 129);
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
0x1800059a0  push    rbp
0x1800059a2  push    rbx
0x1800059a3  push    rsi
0x1800059a4  push    rdi
0x1800059a5  push    r12
0x1800059a7  push    r14
0x1800059a9  push    r15
0x1800059ab  lea     rbp, [rsp-1Fh]
0x1800059b0  sub     rsp, 0B0h
0x1800059b7  mov     r12d, edx
0x1800059ba  mov     [rbp+4Fh+var_A8], 0
0x1800059c2  xor     edx, edx; Val
0x1800059c4  mov     r15, rcx
0x1800059c7  lea     rcx, [rbp+4Fh+var_A0]; void *
0x1800059cb  mov     r14, r9
0x1800059ce  lea     r8d, [rdx+70h]; Size
0x1800059d2  call    memset_0
0x1800059d7  xor     eax, eax
0x1800059d9  lea     rcx, aFeclientEfsena_0; "feclient-EfsEnabled"
0x1800059e0  mov     [rbp+4Fh+var_B0], ax
0x1800059e4  call    cs:__imp_EfsDllIsNonEfsSKU
0x1800059eb  nop     dword ptr [rax+rax+00h]
0x1800059f0  test    al, al
0x1800059f2  jz      short loc_1800059FE
0x1800059f4  mov     ebx, 32h ; '2'
0x1800059f9  jmp     loc_180005C72
0x1800059fe  call    cs:__imp_EfsDllDisabled
0x180005a05  nop     dword ptr [rax+rax+00h]
0x180005a0a  test    al, al
0x180005a0c  jz      short loc_180005A18
0x180005a0e  mov     ebx, 177Fh
0x180005a13  jmp     loc_180005C72
0x180005a18  mov     rdi, [rbp+4Fh+arg_20]
0x180005a1c  test    rdi, rdi
0x180005a1f  jnz     short loc_180005A29
0x180005a21  lea     ebx, [rdi+57h]
0x180005a24  jmp     loc_180005C72
0x180005a29  call    EfsEnforceClientAuthentication
0x180005a2e  mov     ebx, eax
0x180005a30  test    eax, eax
0x180005a32  jz      short loc_180005A56
0x180005a34  mov     [rsp+0E0h+var_C0], 648h
0x180005a3c  mov     r9d, 6
0x180005a42  lea     rdx, EFS_API_ERROR
0x180005a49  mov     r8d, eax
0x180005a4c  call    fnEfsLogTrace1
0x180005a51  jmp     loc_180005C72
0x180005a56  cmp     dword ptr [rdi], 1F4h
0x180005a5c  ja      loc_180005C6D
0x180005a62  mov     rsi, [rdi+8]
0x180005a66  xor     ecx, ecx
0x180005a68  test    rsi, rsi
0x180005a6b  setz    cl
0x180005a6e  xor     eax, eax
0x180005a70  cmp     [rdi], eax
0x180005a72  setz    al
0x180005a75  cmp     eax, ecx
0x180005a77  jnz     loc_180005C6D
0x180005a7d  xor     ebx, ebx
0x180005a7f  cmp     [rdi], ebx
0x180005a81  jbe     short loc_180005AD5
0x180005a83  mov     rcx, [rsi+rbx*8]
0x180005a87  test    rcx, rcx
0x180005a8a  jz      loc_180005C6D
0x180005a90  mov     rax, [rcx+10h]
0x180005a94  test    rax, rax
0x180005a97  jz      loc_180005C6D
0x180005a9d  cmp     dword ptr [rax+4], 0
0x180005aa1  jz      loc_180005C6D
0x180005aa7  cmp     qword ptr [rax+8], 0
0x180005aac  jz      loc_180005C6D
0x180005ab2  mov     rcx, [rcx+8]; Sid
0x180005ab6  test    rcx, rcx
0x180005ab9  jz      short loc_180005ACF
0x180005abb  call    cs:__imp_RtlValidSid
0x180005ac2  nop     dword ptr [rax+rax+00h]
0x180005ac7  test    al, al
0x180005ac9  jz      loc_180005C6D
0x180005acf  inc     ebx
0x180005ad1  cmp     ebx, [rdi]
0x180005ad3  jb      short loc_180005A83
0x180005ad5  lea     r9, [rbp+4Fh+var_B0]
0x180005ad9  xor     edx, edx
0x180005adb  lea     r8, [rbp+4Fh+var_A8]
0x180005adf  mov     rcx, r14
0x180005ae2  call    cs:__imp_EfsDllGetLocalFileName
0x180005ae9  nop     dword ptr [rax+rax+00h]
0x180005aee  mov     ebx, eax
0x180005af0  test    eax, eax
0x180005af2  jz      short loc_180005B01
0x180005af4  mov     [rsp+0E0h+var_C0], 656h
0x180005afc  jmp     loc_180005A3C
0x180005b01  xor     al, al
0x180005b03  movzx   esi, al
0x180005b06  mov     eax, 1
0x180005b0b  cmp     ax, [rbp+4Fh+var_B0]
0x180005b0f  cmovz   esi, eax
0x180005b12  xor     ecx, ecx; BindingHandle
0x180005b14  call    cs:__imp_RpcImpersonateClient
0x180005b1b  nop     dword ptr [rax+rax+00h]
0x180005b20  mov     ebx, eax
0x180005b22  test    eax, eax
0x180005b24  jz      short loc_180005B33
0x180005b26  mov     [rsp+0E0h+var_C0], 65Fh
0x180005b2e  jmp     loc_180005A3C
0x180005b33  mov     rcx, [rbp+4Fh+var_A8]
0x180005b37  call    EfsEnsureLocalPath
0x180005b3c  mov     ebx, eax
0x180005b3e  test    eax, eax
0x180005b40  jz      short loc_180005B64
0x180005b42  mov     [rsp+0E0h+var_C0], 665h
0x180005b4a  mov     r9d, 6
0x180005b50  lea     rdx, EFS_API_ERROR
0x180005b57  mov     r8d, eax
0x180005b5a  call    fnEfsLogTrace1
0x180005b5f  jmp     loc_180005C5F
0x180005b64  call    EfspCheckForNetSession
0x180005b69  test    eax, eax
0x180005b6b  jz      short loc_180005BCE
0x180005b6d  mov     eax, 1
0x180005b72  cmp     [rbp+4Fh+var_B0], ax
0x180005b76  jnz     short loc_180005B80
0x180005b78  lea     ebx, [rax+4]
0x180005b7b  jmp     loc_180005C5F
0x180005b80  mov     r8d, 82h
0x180005b86  mov     edx, eax
0x180005b88  mov     rcx, r14
0x180005b8b  call    cs:__imp_EfsDllShareDecline
0x180005b92  nop     dword ptr [rax+rax+00h]
0x180005b97  test    eax, eax
0x180005b99  jz      short loc_180005BB3
0x180005b9b  call    cs:__imp_GetLastError
0x180005ba2  nop     dword ptr [rax+rax+00h]
0x180005ba7  mov     ebx, eax
0x180005ba9  mov     [rsp+0E0h+var_C0], 678h
0x180005bb1  jmp     short loc_180005B4A
0x180005bb3  mov     rcx, r15
0x180005bb6  call    EfspIsValidNetworkProtSeq
0x180005bbb  mov     ebx, eax
0x180005bbd  test    eax, eax
0x180005bbf  jz      short loc_180005BCE
0x180005bc1  mov     [rsp+0E0h+var_C0], 681h
0x180005bc9  jmp     loc_180005B4A
0x180005bce  lea     rcx, [rbp+4Fh+var_A0]
0x180005bd2  call    cs:__imp_EfsDllGetUserInfo
0x180005bd9  nop     dword ptr [rax+rax+00h]
0x180005bde  test    al, al
0x180005be0  jnz     short loc_180005BF2
0x180005be2  call    cs:__imp_GetLastError
0x180005be9  nop     dword ptr [rax+rax+00h]
0x180005bee  mov     ebx, eax
0x180005bf0  jmp     short loc_180005C5F
0x180005bf2  xor     edx, edx
0x180005bf4  lea     rcx, [rbp+4Fh+var_A0]
0x180005bf8  call    cs:__imp_EfsDllLoadUserProfile
0x180005bff  nop     dword ptr [rax+rax+00h]
0x180005c04  test    eax, eax
0x180005c06  jnz     short loc_180005C18
0x180005c08  call    cs:__imp_GetLastError
0x180005c0f  nop     dword ptr [rax+rax+00h]
0x180005c14  mov     ebx, eax
0x180005c16  jmp     short loc_180005C4F
0x180005c18  mov     r9, [rdi+8]
0x180005c1c  lea     rcx, [rbp+4Fh+var_A0]
0x180005c20  mov     r8d, [rdi]
0x180005c23  mov     rdx, [rbp+4Fh+var_A8]
0x180005c27  mov     [rsp+0E0h+var_B8], sil
0x180005c2c  mov     [rsp+0E0h+var_C0], r12d
0x180005c31  call    cs:__imp_EfsDllAddUsersToFileSrv
0x180005c38  nop     dword ptr [rax+rax+00h]
0x180005c3d  mov     ebx, eax
0x180005c3f  lea     rcx, [rbp+4Fh+var_A0]
0x180005c43  call    cs:__imp_EfsDllUnloadUserProfile
0x180005c4a  nop     dword ptr [rax+rax+00h]
0x180005c4f  lea     rcx, [rbp+4Fh+var_A0]
0x180005c53  call    cs:__imp_EfsDllFreeUserInfo
0x180005c5a  nop     dword ptr [rax+rax+00h]
0x180005c5f  call    cs:__imp_RpcRevertToSelf
0x180005c66  nop     dword ptr [rax+rax+00h]
0x180005c6b  jmp     short loc_180005C72
0x180005c6d  mov     ebx, 5
0x180005c72  mov     rcx, [rbp+4Fh+var_A8]
0x180005c76  test    rcx, rcx
0x180005c79  jz      short loc_180005C87
0x180005c7b  call    cs:__imp_EfsDllFreeHeap
0x180005c82  nop     dword ptr [rax+rax+00h]
0x180005c87  mov     eax, ebx
0x180005c89  add     rsp, 0B0h
0x180005c90  pop     r15
0x180005c92  pop     r14
0x180005c94  pop     r12
0x180005c96  pop     rdi
0x180005c97  pop     rsi
0x180005c98  pop     rbx
0x180005c99  pop     rbp
0x180005c9a  retn
```
