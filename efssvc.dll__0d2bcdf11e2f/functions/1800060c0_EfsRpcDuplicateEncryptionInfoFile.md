# EfsRpcDuplicateEncryptionInfoFile

- ea: `0x1800060c0`
- end: `0x180006457`
- name: `EfsRpcDuplicateEncryptionInfoFile`
- size: `919`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, int, __int64, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800037b8`
- `0x1800060c0`
- `0x180007f38`
- `0x180008404`
- `0x18000bf0c`
- `0x18000c094`
- `0x18000d192`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000635d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000635d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006383`
- `RPCRT4!RpcRevertToSelf` at `0x180006434`
- `RPCRT4!RpcRevertToSelf` at `0x180006434`
- `RPCRT4!RpcImpersonateClient` at `0x180006225`
- `RPCRT4!RpcImpersonateClient` at `0x180006225`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18000619c`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18000619c`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000640e`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000640e`
- `EFSCORE!EfsDllGetLocalFileName` at `0x1800061c5`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180006207`
- `EFSCORE!EfsDllGetLocalFileName` at `0x1800061c5`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180006207`
- `EFSCORE!EfsDllDisabled` at `0x18000612d`
- `EFSCORE!EfsDllDisabled` at `0x18000612d`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180006423`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180006423`
- `EFSCORE!EfsDllGetUserInfo` at `0x18000634d`
- `EFSCORE!EfsDllGetUserInfo` at `0x18000634d`
- `EFSCORE!EfsDllDuplicateEncryptionInfoFileSrv` at `0x1800063c6`
- `EFSCORE!EfsDllDuplicateEncryptionInfoFileSrv` at `0x1800063c6`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180006373`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180006373`
- `EFSCORE!EfsDllShareDecline` at `0x1800062a9`
- `EFSCORE!EfsDllShareDecline` at `0x1800062d9`
- `EFSCORE!EfsDllShareDecline` at `0x1800062a9`
- `EFSCORE!EfsDllShareDecline` at `0x1800062d9`
- `EFSCORE!EfsDllFreeHeap` at `0x1800063e3`
- `EFSCORE!EfsDllFreeHeap` at `0x1800063f9`
- `EFSCORE!EfsDllFreeHeap` at `0x1800063e3`
- `EFSCORE!EfsDllFreeHeap` at `0x1800063f9`

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
  unsigned int v14; // eax
  __int64 v15; // rcx
  unsigned int LocalFileName; // eax
  __int64 v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rcx
  RPC_STATUS v20; // eax
  __int64 v21; // rcx
  unsigned int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int IsValidNetworkProtSeq; // eax
  __int64 v27; // rcx
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
      fnEfsLogTrace1(v15, (__int64)EFS_API_ERROR, v14, 6, 53);
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
      fnEfsLogTrace1(v17, (__int64)EFS_API_ERROR, LocalFileName, 6, 71);
      goto LABEL_40;
    }
    v18 = EfsDllGetLocalFileName(a3, 0, &v33, &v31);
    LastError = v18;
    if ( v18 )
    {
      fnEfsLogTrace1(v19, (__int64)EFS_API_ERROR, v18, 6, 76);
      goto LABEL_40;
    }
    v20 = RpcImpersonateClient(0);
    LastError = v20;
    if ( v20 )
    {
      fnEfsLogTrace1(v21, (__int64)EFS_API_ERROR, v20, 6, 81);
      goto LABEL_40;
    }
    v11 = 1;
    v22 = EfsEnsureLocalPath(v32);
    LastError = v22;
    if ( v22 )
    {
      fnEfsLogTrace1(v23, (__int64)EFS_API_ERROR, v22, 6, 87);
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
      fnEfsLogTrace1(v24, (__int64)EFS_API_ERROR, LastError, 6, 114);
      goto LABEL_22;
    }
    if ( (unsigned int)EfsDllShareDecline(a3, 0, 0) )
    {
      LastError = GetLastError();
      fnEfsLogTrace1(v25, (__int64)EFS_API_ERROR, LastError, 6, 120);
      goto LABEL_22;
    }
    v13 = 1;
    IsValidNetworkProtSeq = EfspIsValidNetworkProtSeq(a1);
    LastError = IsValidNetworkProtSeq;
    if ( IsValidNetworkProtSeq )
    {
      fnEfsLogTrace1(v27, (__int64)EFS_API_ERROR, IsValidNetworkProtSeq, 6, 131);
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
0x1800060c0  mov     [rsp-8+arg_18], r9d
0x1800060c5  push    rbp
0x1800060c6  push    rbx
0x1800060c7  push    rsi
0x1800060c8  push    rdi
0x1800060c9  push    r12
0x1800060cb  push    r13
0x1800060cd  push    r14
0x1800060cf  push    r15
0x1800060d1  lea     rbp, [rsp-7]
0x1800060d6  sub     rsp, 0D8h
0x1800060dd  xor     ebx, ebx
0x1800060df  mov     r12, r8
0x1800060e2  mov     r15, rdx
0x1800060e5  mov     [rsp+110h+var_C0], rbx
0x1800060ea  mov     r13, rcx
0x1800060ed  mov     [rbp+3Fh+var_B8], rbx
0x1800060f1  xor     edx, edx; Val
0x1800060f3  mov     [rsp+110h+var_CC], bx
0x1800060f8  lea     r8d, [rbx+70h]; Size
0x1800060fc  mov     [rsp+110h+var_C8], bx
0x180006101  lea     rcx, [rbp+3Fh+var_B0]; void *
0x180006105  call    memset_0
0x18000610a  cmp     cs:EfsServerInitialized, bl
0x180006110  jnz     short loc_18000611C
0x180006112  mov     ebx, 32h ; '2'
0x180006117  jmp     loc_180006440
0x18000611c  mov     dil, bl
0x18000611f  mov     [rsp+110h+var_D0], bl
0x180006123  mov     sil, bl
0x180006126  mov     [rsp+110h+var_CF], bl
0x18000612a  mov     r14b, bl
0x18000612d  call    cs:__imp_EfsDllDisabled
0x180006134  nop     dword ptr [rax+rax+00h]
0x180006139  test    al, al
0x18000613b  jz      short loc_180006147
0x18000613d  mov     ebx, 177Fh
0x180006142  jmp     loc_1800063DA
0x180006147  call    EfsEnforceClientAuthentication
0x18000614c  mov     ebx, eax
0x18000614e  test    eax, eax
0x180006150  jz      short loc_180006174
0x180006152  mov     r9d, 6
0x180006158  mov     [rsp+110h+var_F0], 735h
0x180006160  mov     r8d, eax
0x180006163  lea     rdx, EFS_API_ERROR
0x18000616a  call    fnEfsLogTrace1
0x18000616f  jmp     loc_1800063DA
0x180006174  test    r15, r15
0x180006177  jnz     short loc_180006182
0x180006179  lea     ebx, [r15+57h]
0x18000617d  jmp     loc_1800063DA
0x180006182  mov     rsi, [rbp+3Fh+arg_28]
0x180006186  test    rsi, rsi
0x180006189  jz      short loc_1800061B6
0x18000618b  cmp     dword ptr [rsi], 41000h
0x180006191  ja      short loc_1800061AC
0x180006193  mov     edx, [rsi]; SecurityDescriptorLength
0x180006195  xor     r8d, r8d; RequiredInformation
0x180006198  mov     rcx, [rsi+8]; SecurityDescriptorInput
0x18000619c  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1800061a3  nop     dword ptr [rax+rax+00h]
0x1800061a8  test    al, al
0x1800061aa  jnz     short loc_1800061B6
0x1800061ac  mov     ebx, 5
0x1800061b1  jmp     loc_1800063D7
0x1800061b6  lea     r9, [rsp+110h+var_CC]
0x1800061bb  xor     edx, edx
0x1800061bd  lea     r8, [rsp+110h+var_C0]
0x1800061c2  mov     rcx, r15
0x1800061c5  call    cs:__imp_EfsDllGetLocalFileName
0x1800061cc  nop     dword ptr [rax+rax+00h]
0x1800061d1  mov     ebx, eax
0x1800061d3  test    eax, eax
0x1800061d5  jz      short loc_1800061F9
0x1800061d7  mov     [rsp+110h+var_F0], 747h
0x1800061df  mov     r9d, 6
0x1800061e5  lea     rdx, EFS_API_ERROR
0x1800061ec  mov     r8d, eax
0x1800061ef  call    fnEfsLogTrace1
0x1800061f4  jmp     loc_1800063D7
0x1800061f9  lea     r9, [rsp+110h+var_C8]
0x1800061fe  xor     edx, edx
0x180006200  lea     r8, [rbp+3Fh+var_B8]
0x180006204  mov     rcx, r12
0x180006207  call    cs:__imp_EfsDllGetLocalFileName
0x18000620e  nop     dword ptr [rax+rax+00h]
0x180006213  mov     ebx, eax
0x180006215  test    eax, eax
0x180006217  jz      short loc_180006223
0x180006219  mov     [rsp+110h+var_F0], 74Ch
0x180006221  jmp     short loc_1800061DF
0x180006223  xor     ecx, ecx; BindingHandle
0x180006225  call    cs:__imp_RpcImpersonateClient
0x18000622c  nop     dword ptr [rax+rax+00h]
0x180006231  mov     ebx, eax
0x180006233  test    eax, eax
0x180006235  jz      short loc_180006241
0x180006237  mov     [rsp+110h+var_F0], 751h
0x18000623f  jmp     short loc_1800061DF
0x180006241  mov     rcx, [rsp+110h+var_C0]
0x180006246  mov     edi, 1
0x18000624b  call    EfsEnsureLocalPath
0x180006250  mov     ebx, eax
0x180006252  test    eax, eax
0x180006254  jz      short loc_18000627B
0x180006256  mov     [rsp+110h+var_F0], 757h
0x18000625e  mov     r9d, 6
0x180006264  lea     rdx, EFS_API_ERROR
0x18000626b  mov     r8d, eax
0x18000626e  call    fnEfsLogTrace1
0x180006273  mov     sil, r14b
0x180006276  jmp     loc_1800063DA
0x18000627b  call    EfspCheckForNetSession
0x180006280  test    eax, eax
0x180006282  jz      loc_180006349
0x180006288  cmp     [rsp+110h+var_CC], di
0x18000628d  jz      loc_18000633F
0x180006293  cmp     [rsp+110h+var_C8], di
0x180006298  jz      loc_18000633F
0x18000629e  mov     r8d, 80h
0x1800062a4  mov     edx, edi
0x1800062a6  mov     rcx, r15
0x1800062a9  call    cs:__imp_EfsDllShareDecline
0x1800062b0  nop     dword ptr [rax+rax+00h]
0x1800062b5  test    eax, eax
0x1800062b7  jz      short loc_1800062D1
0x1800062b9  call    cs:__imp_GetLastError
0x1800062c0  nop     dword ptr [rax+rax+00h]
0x1800062c5  mov     ebx, eax
0x1800062c7  mov     [rsp+110h+var_F0], 772h
0x1800062cf  jmp     short loc_18000625E
0x1800062d1  xor     r8d, r8d
0x1800062d4  xor     edx, edx
0x1800062d6  mov     rcx, r12
0x1800062d9  call    cs:__imp_EfsDllShareDecline
0x1800062e0  nop     dword ptr [rax+rax+00h]
0x1800062e5  test    eax, eax
0x1800062e7  jz      short loc_180006304
0x1800062e9  call    cs:__imp_GetLastError
0x1800062f0  nop     dword ptr [rax+rax+00h]
0x1800062f5  mov     ebx, eax
0x1800062f7  mov     [rsp+110h+var_F0], 778h
0x1800062ff  jmp     loc_18000625E
0x180006304  mov     rcx, r13
0x180006307  mov     r14b, dil
0x18000630a  call    EfspIsValidNetworkProtSeq
0x18000630f  mov     ebx, eax
0x180006311  test    eax, eax
0x180006313  jz      short loc_180006349
0x180006315  mov     r9d, 6
0x18000631b  mov     [rsp+110h+var_F0], 783h
0x180006323  mov     r8d, eax
0x180006326  lea     rdx, EFS_API_ERROR
0x18000632d  call    fnEfsLogTrace1
0x180006332  mov     sil, [rsp+110h+var_D0]
0x180006337  mov     r14b, sil
0x18000633a  jmp     loc_1800063DA
0x18000633f  mov     ebx, 5
0x180006344  jmp     loc_180006273
0x180006349  lea     rcx, [rbp+3Fh+var_B0]
0x18000634d  call    cs:__imp_EfsDllGetUserInfo
0x180006354  nop     dword ptr [rax+rax+00h]
0x180006359  test    al, al
0x18000635b  jnz     short loc_18000636D
0x18000635d  call    cs:__imp_GetLastError
0x180006364  nop     dword ptr [rax+rax+00h]
0x180006369  mov     ebx, eax
0x18000636b  jmp     short loc_180006332
0x18000636d  xor     edx, edx
0x18000636f  lea     rcx, [rbp+3Fh+var_B0]
0x180006373  call    cs:__imp_EfsDllLoadUserProfile
0x18000637a  nop     dword ptr [rax+rax+00h]
0x18000637f  test    eax, eax
0x180006381  jnz     short loc_180006396
0x180006383  call    cs:__imp_GetLastError
0x18000638a  nop     dword ptr [rax+rax+00h]
0x18000638f  mov     r14b, [rsp+110h+var_CF]
0x180006394  jmp     short loc_1800063D5
0x180006396  mov     eax, [rbp+3Fh+arg_30]
0x180006399  lea     rcx, [rbp+3Fh+var_B0]
0x18000639d  mov     r8, [rbp+3Fh+var_B8]
0x1800063a1  neg     r14b
0x1800063a4  mov     rdx, [rsp+110h+var_C0]
0x1800063a9  mov     [rsp+110h+var_D8], eax
0x1800063ad  sbb     r9, r9
0x1800063b0  mov     eax, [rbp+3Fh+arg_20]
0x1800063b3  and     r9, r12
0x1800063b6  mov     [rsp+110h+var_E0], rsi
0x1800063bb  mov     [rsp+110h+var_E8], eax
0x1800063bf  mov     eax, [rbp+3Fh+arg_18]
0x1800063c2  mov     [rsp+110h+var_F0], eax
0x1800063c6  call    cs:__imp_EfsDllDuplicateEncryptionInfoFileSrv
0x1800063cd  nop     dword ptr [rax+rax+00h]
0x1800063d2  mov     r14b, dil
0x1800063d5  mov     ebx, eax
0x1800063d7  mov     sil, dil
0x1800063da  mov     rcx, [rbp+3Fh+var_B8]
0x1800063de  test    rcx, rcx
0x1800063e1  jz      short loc_1800063EF
0x1800063e3  call    cs:__imp_EfsDllFreeHeap
0x1800063ea  nop     dword ptr [rax+rax+00h]
0x1800063ef  mov     rcx, [rsp+110h+var_C0]
0x1800063f4  test    rcx, rcx
0x1800063f7  jz      short loc_180006405
0x1800063f9  call    cs:__imp_EfsDllFreeHeap
0x180006400  nop     dword ptr [rax+rax+00h]
0x180006405  test    r14b, r14b
0x180006408  jz      short loc_18000641A
0x18000640a  lea     rcx, [rbp+3Fh+var_B0]
0x18000640e  call    cs:__imp_EfsDllUnloadUserProfile
0x180006415  nop     dword ptr [rax+rax+00h]
0x18000641a  test    sil, sil
0x18000641d  jz      short loc_18000642F
0x18000641f  lea     rcx, [rbp+3Fh+var_B0]
0x180006423  call    cs:__imp_EfsDllFreeUserInfo
0x18000642a  nop     dword ptr [rax+rax+00h]
0x18000642f  test    dil, dil
0x180006432  jz      short loc_180006440
0x180006434  call    cs:__imp_RpcRevertToSelf
0x18000643b  nop     dword ptr [rax+rax+00h]
0x180006440  mov     eax, ebx
0x180006442  add     rsp, 0D8h
0x180006449  pop     r15
0x18000644b  pop     r14
0x18000644d  pop     r13
0x18000644f  pop     r12
0x180006451  pop     rdi
0x180006452  pop     rsi
0x180006453  pop     rbx
0x180006454  pop     rbp
0x180006455  retn
```
