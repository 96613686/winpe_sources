# EfsRpcDuplicateEncryptionInfoFile

- ea: `0x180005bc0`
- end: `0x180005ee1`
- name: `EfsRpcDuplicateEncryptionInfoFile`
- size: `801`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003604`
- `0x180005bc0`
- `0x1800076b4`
- `0x180007ae8`
- `0x18000b308`
- `0x18000b480`
- `0x18000c392`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005d95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e38`
- `RPCRT4!RpcRevertToSelf` at `0x180005ec5`
- `RPCRT4!RpcRevertToSelf` at `0x180005ec5`
- `RPCRT4!RpcImpersonateClient` at `0x180005d0d`
- `RPCRT4!RpcImpersonateClient` at `0x180005d0d`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180005c96`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180005c96`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180005eab`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180005eab`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180005cb9`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180005cf5`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180005cb9`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180005cf5`
- `EFSCORE!EfsDllDisabled` at `0x180005c2d`
- `EFSCORE!EfsDllDisabled` at `0x180005c2d`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180005eba`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180005eba`
- `EFSCORE!EfsDllGetUserInfo` at `0x180005e14`
- `EFSCORE!EfsDllGetUserInfo` at `0x180005e14`
- `EFSCORE!EfsDllDuplicateEncryptionInfoFileSrv` at `0x180005e75`
- `EFSCORE!EfsDllDuplicateEncryptionInfoFileSrv` at `0x180005e75`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180005e2e`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180005e2e`
- `EFSCORE!EfsDllShareDecline` at `0x180005d8b`
- `EFSCORE!EfsDllShareDecline` at `0x180005daf`
- `EFSCORE!EfsDllShareDecline` at `0x180005d8b`
- `EFSCORE!EfsDllShareDecline` at `0x180005daf`
- `EFSCORE!EfsDllFreeHeap` at `0x180005e8c`
- `EFSCORE!EfsDllFreeHeap` at `0x180005e9c`
- `EFSCORE!EfsDllFreeHeap` at `0x180005e8c`
- `EFSCORE!EfsDllFreeHeap` at `0x180005e9c`

## pseudocode

```c
__int64 __fastcall EfsRpcDuplicateEncryptionInfoFile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        int a7)
{
  DWORD LastError; // ebx
  char v11; // di
  char v12; // si
  char v13; // r14
  DWORD v14; // eax
  int v15; // ecx
  DWORD LocalFileName; // eax
  int v17; // ecx
  DWORD v18; // eax
  int v19; // ecx
  RPC_STATUS v20; // eax
  int v21; // ecx
  DWORD v22; // eax
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  DWORD IsValidNetworkProtSeq; // eax
  int v27; // ecx
  DWORD v28; // eax
  __int16 v30; // [rsp+44h] [rbp-8Dh] BYREF
  __int16 v31; // [rsp+48h] [rbp-89h] BYREF
  __int64 v32; // [rsp+50h] [rbp-81h] BYREF
  __int64 v33; // [rsp+58h] [rbp-79h] BYREF
  _BYTE v34[176]; // [rsp+60h] [rbp-71h] BYREF

  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  memset_0(v34, 0, 0x70u);
  if ( !EfsServerInitialized )
    return 50;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( !(unsigned __int8)EfsDllDisabled() )
  {
    v14 = EfsEnforceClientAuthentication();
    LastError = v14;
    if ( v14 )
    {
      fnEfsLogTrace1(v15, (unsigned int)EFS_API_ERROR, v14, 6, 53);
      goto LABEL_41;
    }
    if ( !a2 )
    {
      LastError = 87;
      goto LABEL_41;
    }
    if ( a6
      && (*(_DWORD *)a6 > 0x41000u
       || !RtlValidRelativeSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a6 + 8), *(_DWORD *)a6, 0)) )
    {
      LastError = 5;
LABEL_40:
      v12 = v11;
      goto LABEL_41;
    }
    LocalFileName = EfsDllGetLocalFileName(a2, 0, &v32, &v30);
    LastError = LocalFileName;
    if ( LocalFileName )
    {
      fnEfsLogTrace1(v17, (unsigned int)EFS_API_ERROR, LocalFileName, 6, 71);
      goto LABEL_40;
    }
    v18 = EfsDllGetLocalFileName(a3, 0, &v33, &v31);
    LastError = v18;
    if ( v18 )
    {
      fnEfsLogTrace1(v19, (unsigned int)EFS_API_ERROR, v18, 6, 76);
      goto LABEL_40;
    }
    v20 = RpcImpersonateClient(0);
    LastError = v20;
    if ( v20 )
    {
      fnEfsLogTrace1(v21, (unsigned int)EFS_API_ERROR, v20, 6, 81);
      goto LABEL_40;
    }
    v11 = 1;
    v22 = EfsEnsureLocalPath(v32);
    LastError = v22;
    if ( v22 )
    {
      fnEfsLogTrace1(v23, (unsigned int)EFS_API_ERROR, v22, 6, 87);
LABEL_22:
      v12 = 0;
      goto LABEL_41;
    }
    if ( !(unsigned int)EfspCheckForNetSession() )
      goto LABEL_54;
    if ( v30 == 1 || v31 == 1 )
    {
      LastError = 5;
      goto LABEL_22;
    }
    if ( (unsigned int)EfsDllShareDecline(a2, 1, 128) )
    {
      LastError = GetLastError();
      fnEfsLogTrace1(v24, (unsigned int)EFS_API_ERROR, LastError, 6, 114);
      goto LABEL_22;
    }
    if ( (unsigned int)EfsDllShareDecline(a3, 0, 0) )
    {
      LastError = GetLastError();
      fnEfsLogTrace1(v25, (unsigned int)EFS_API_ERROR, LastError, 6, 120);
      goto LABEL_22;
    }
    v13 = 1;
    IsValidNetworkProtSeq = EfspIsValidNetworkProtSeq(a1);
    LastError = IsValidNetworkProtSeq;
    if ( IsValidNetworkProtSeq )
    {
      fnEfsLogTrace1(v27, (unsigned int)EFS_API_ERROR, IsValidNetworkProtSeq, 6, 131);
    }
    else
    {
LABEL_54:
      if ( (unsigned __int8)EfsDllGetUserInfo(v34) )
      {
        if ( (unsigned int)EfsDllLoadUserProfile(v34, 0) )
        {
          v28 = EfsDllDuplicateEncryptionInfoFileSrv(v34, v32, v33, a3 & -(__int64)(v13 != 0), a4, a5, a6, a7);
          v13 = 1;
        }
        else
        {
          v28 = GetLastError();
          v13 = 0;
        }
        LastError = v28;
        goto LABEL_40;
      }
      LastError = GetLastError();
    }
    v12 = 0;
    v13 = 0;
    goto LABEL_41;
  }
  LastError = 6015;
LABEL_41:
  if ( v33 )
    EfsDllFreeHeap();
  if ( v32 )
    EfsDllFreeHeap();
  if ( v13 )
    EfsDllUnloadUserProfile(v34);
  if ( v12 )
    EfsDllFreeUserInfo(v34);
  if ( v11 )
    RpcRevertToSelf();
  return LastError;
}

```

## disassembly

```asm
0x180005bc0  mov     [rsp-8+arg_18], r9d
0x180005bc5  push    rbp
0x180005bc6  push    rbx
0x180005bc7  push    rsi
0x180005bc8  push    rdi
0x180005bc9  push    r12
0x180005bcb  push    r13
0x180005bcd  push    r14
0x180005bcf  push    r15
0x180005bd1  lea     rbp, [rsp-7]
0x180005bd6  sub     rsp, 0D8h
0x180005bdd  xor     ebx, ebx
0x180005bdf  mov     r12, r8
0x180005be2  mov     r15, rdx
0x180005be5  mov     [rsp+110h+var_C0], rbx
0x180005bea  mov     r13, rcx
0x180005bed  mov     [rbp+3Fh+var_B8], rbx
0x180005bf1  xor     edx, edx; Val
0x180005bf3  mov     [rsp+110h+var_CC], bx
0x180005bf8  lea     r8d, [rbx+70h]; Size
0x180005bfc  mov     [rsp+110h+var_C8], bx
0x180005c01  lea     rcx, [rbp+3Fh+var_B0]; void *
0x180005c05  call    memset_0
0x180005c0a  cmp     cs:EfsServerInitialized, bl
0x180005c10  jnz     short loc_180005C1C
0x180005c12  mov     ebx, 32h ; '2'
0x180005c17  jmp     loc_180005ECB
0x180005c1c  mov     dil, bl
0x180005c1f  mov     [rsp+110h+var_D0], bl
0x180005c23  mov     sil, bl
0x180005c26  mov     [rsp+110h+var_CF], bl
0x180005c2a  mov     r14b, bl
0x180005c2d  call    cs:__imp_EfsDllDisabled
0x180005c33  test    al, al
0x180005c35  jz      short loc_180005C41
0x180005c37  mov     ebx, 177Fh
0x180005c3c  jmp     loc_180005E83
0x180005c41  call    EfsEnforceClientAuthentication
0x180005c46  mov     ebx, eax
0x180005c48  test    eax, eax
0x180005c4a  jz      short loc_180005C6E
0x180005c4c  mov     r9d, 6
0x180005c52  mov     [rsp+110h+var_F0], 735h
0x180005c5a  mov     r8d, eax
0x180005c5d  lea     rdx, EFS_API_ERROR
0x180005c64  call    fnEfsLogTrace1
0x180005c69  jmp     loc_180005E83
0x180005c6e  test    r15, r15
0x180005c71  jnz     short loc_180005C7C
0x180005c73  lea     ebx, [r15+57h]
0x180005c77  jmp     loc_180005E83
0x180005c7c  mov     rsi, [rbp+3Fh+arg_28]
0x180005c80  test    rsi, rsi
0x180005c83  jz      short loc_180005CAA
0x180005c85  cmp     dword ptr [rsi], 41000h
0x180005c8b  ja      short loc_180005CA0
0x180005c8d  mov     edx, [rsi]; SecurityDescriptorLength
0x180005c8f  xor     r8d, r8d; RequiredInformation
0x180005c92  mov     rcx, [rsi+8]; SecurityDescriptorInput
0x180005c96  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x180005c9c  test    al, al
0x180005c9e  jnz     short loc_180005CAA
0x180005ca0  mov     ebx, 5
0x180005ca5  jmp     loc_180005E80
0x180005caa  lea     r9, [rsp+110h+var_CC]
0x180005caf  xor     edx, edx
0x180005cb1  lea     r8, [rsp+110h+var_C0]
0x180005cb6  mov     rcx, r15
0x180005cb9  call    cs:__imp_EfsDllGetLocalFileName
0x180005cbf  mov     ebx, eax
0x180005cc1  test    eax, eax
0x180005cc3  jz      short loc_180005CE7
0x180005cc5  mov     [rsp+110h+var_F0], 747h
0x180005ccd  mov     r9d, 6
0x180005cd3  lea     rdx, EFS_API_ERROR
0x180005cda  mov     r8d, eax
0x180005cdd  call    fnEfsLogTrace1
0x180005ce2  jmp     loc_180005E80
0x180005ce7  lea     r9, [rsp+110h+var_C8]
0x180005cec  xor     edx, edx
0x180005cee  lea     r8, [rbp+3Fh+var_B8]
0x180005cf2  mov     rcx, r12
0x180005cf5  call    cs:__imp_EfsDllGetLocalFileName
0x180005cfb  mov     ebx, eax
0x180005cfd  test    eax, eax
0x180005cff  jz      short loc_180005D0B
0x180005d01  mov     [rsp+110h+var_F0], 74Ch
0x180005d09  jmp     short loc_180005CCD
0x180005d0b  xor     ecx, ecx; BindingHandle
0x180005d0d  call    cs:__imp_RpcImpersonateClient
0x180005d13  mov     ebx, eax
0x180005d15  test    eax, eax
0x180005d17  jz      short loc_180005D23
0x180005d19  mov     [rsp+110h+var_F0], 751h
0x180005d21  jmp     short loc_180005CCD
0x180005d23  mov     rcx, [rsp+110h+var_C0]
0x180005d28  mov     edi, 1
0x180005d2d  call    EfsEnsureLocalPath
0x180005d32  mov     ebx, eax
0x180005d34  test    eax, eax
0x180005d36  jz      short loc_180005D5D
0x180005d38  mov     [rsp+110h+var_F0], 757h
0x180005d40  mov     r9d, 6
0x180005d46  lea     rdx, EFS_API_ERROR
0x180005d4d  mov     r8d, eax
0x180005d50  call    fnEfsLogTrace1
0x180005d55  mov     sil, r14b
0x180005d58  jmp     loc_180005E83
0x180005d5d  call    EfspCheckForNetSession
0x180005d62  test    eax, eax
0x180005d64  jz      loc_180005E10
0x180005d6a  cmp     [rsp+110h+var_CC], di
0x180005d6f  jz      loc_180005E06
0x180005d75  cmp     [rsp+110h+var_C8], di
0x180005d7a  jz      loc_180005E06
0x180005d80  mov     r8d, 80h
0x180005d86  mov     edx, edi
0x180005d88  mov     rcx, r15
0x180005d8b  call    cs:__imp_EfsDllShareDecline
0x180005d91  test    eax, eax
0x180005d93  jz      short loc_180005DA7
0x180005d95  call    cs:__imp_GetLastError
0x180005d9b  mov     ebx, eax
0x180005d9d  mov     [rsp+110h+var_F0], 772h
0x180005da5  jmp     short loc_180005D40
0x180005da7  xor     r8d, r8d
0x180005daa  xor     edx, edx
0x180005dac  mov     rcx, r12
0x180005daf  call    cs:__imp_EfsDllShareDecline
0x180005db5  test    eax, eax
0x180005db7  jz      short loc_180005DCE
0x180005db9  call    cs:__imp_GetLastError
0x180005dbf  mov     ebx, eax
0x180005dc1  mov     [rsp+110h+var_F0], 778h
0x180005dc9  jmp     loc_180005D40
0x180005dce  mov     rcx, r13
0x180005dd1  mov     r14b, dil
0x180005dd4  call    EfspIsValidNetworkProtSeq
0x180005dd9  mov     ebx, eax
0x180005ddb  test    eax, eax
0x180005ddd  jz      short loc_180005E10
0x180005ddf  mov     r9d, 6
0x180005de5  mov     [rsp+110h+var_F0], 783h
0x180005ded  mov     r8d, eax
0x180005df0  lea     rdx, EFS_API_ERROR
0x180005df7  call    fnEfsLogTrace1
0x180005dfc  mov     sil, [rsp+110h+var_D0]
0x180005e01  mov     r14b, sil
0x180005e04  jmp     short loc_180005E83
0x180005e06  mov     ebx, 5
0x180005e0b  jmp     loc_180005D55
0x180005e10  lea     rcx, [rbp+3Fh+var_B0]
0x180005e14  call    cs:__imp_EfsDllGetUserInfo
0x180005e1a  test    al, al
0x180005e1c  jnz     short loc_180005E28
0x180005e1e  call    cs:__imp_GetLastError
0x180005e24  mov     ebx, eax
0x180005e26  jmp     short loc_180005DFC
0x180005e28  xor     edx, edx
0x180005e2a  lea     rcx, [rbp+3Fh+var_B0]
0x180005e2e  call    cs:__imp_EfsDllLoadUserProfile
0x180005e34  test    eax, eax
0x180005e36  jnz     short loc_180005E45
0x180005e38  call    cs:__imp_GetLastError
0x180005e3e  mov     r14b, [rsp+110h+var_CF]
0x180005e43  jmp     short loc_180005E7E
0x180005e45  mov     eax, [rbp+3Fh+arg_30]
0x180005e48  lea     rcx, [rbp+3Fh+var_B0]
0x180005e4c  mov     r8, [rbp+3Fh+var_B8]
0x180005e50  neg     r14b
0x180005e53  mov     rdx, [rsp+110h+var_C0]
0x180005e58  mov     [rsp+110h+var_D8], eax
0x180005e5c  sbb     r9, r9
0x180005e5f  mov     eax, [rbp+3Fh+arg_20]
0x180005e62  and     r9, r12
0x180005e65  mov     [rsp+110h+var_E0], rsi
0x180005e6a  mov     [rsp+110h+var_E8], eax
0x180005e6e  mov     eax, [rbp+3Fh+arg_18]
0x180005e71  mov     [rsp+110h+var_F0], eax
0x180005e75  call    cs:__imp_EfsDllDuplicateEncryptionInfoFileSrv
0x180005e7b  mov     r14b, dil
0x180005e7e  mov     ebx, eax
0x180005e80  mov     sil, dil
0x180005e83  mov     rcx, [rbp+3Fh+var_B8]
0x180005e87  test    rcx, rcx
0x180005e8a  jz      short loc_180005E92
0x180005e8c  call    cs:__imp_EfsDllFreeHeap
0x180005e92  mov     rcx, [rsp+110h+var_C0]
0x180005e97  test    rcx, rcx
0x180005e9a  jz      short loc_180005EA2
0x180005e9c  call    cs:__imp_EfsDllFreeHeap
0x180005ea2  test    r14b, r14b
0x180005ea5  jz      short loc_180005EB1
0x180005ea7  lea     rcx, [rbp+3Fh+var_B0]
0x180005eab  call    cs:__imp_EfsDllUnloadUserProfile
0x180005eb1  test    sil, sil
0x180005eb4  jz      short loc_180005EC0
0x180005eb6  lea     rcx, [rbp+3Fh+var_B0]
0x180005eba  call    cs:__imp_EfsDllFreeUserInfo
0x180005ec0  test    dil, dil
0x180005ec3  jz      short loc_180005ECB
0x180005ec5  call    cs:__imp_RpcRevertToSelf
0x180005ecb  mov     eax, ebx
0x180005ecd  add     rsp, 0D8h
0x180005ed4  pop     r15
0x180005ed6  pop     r14
0x180005ed8  pop     r13
0x180005eda  pop     r12
0x180005edc  pop     rdi
0x180005edd  pop     rsi
0x180005ede  pop     rbx
0x180005edf  pop     rbp
0x180005ee0  retn
```
