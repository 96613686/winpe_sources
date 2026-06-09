# EfspEncryptFileCommonPrologue

- ea: `0x180007810`
- end: `0x180007ae1`
- name: `EfspEncryptFileCommonPrologue`
- size: `721`
- prototype: `__int64 __fastcall(void *, __int64, LPCWSTR *, int, DWORD, _WORD *, int *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005ef0`

## callees

- `0x180003604`
- `0x1800076b4`
- `0x180007810`
- `0x180007ae8`
- `0x18000b480`
- `0x18000c392`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000790f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000790f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a45`
- `RPCRT4!RpcRevertToSelf` at `0x180007ab1`
- `RPCRT4!RpcRevertToSelf` at `0x180007ab1`
- `RPCRT4!RpcImpersonateClient` at `0x180007899`
- `RPCRT4!RpcImpersonateClient` at `0x180007899`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180007948`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180007975`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180007948`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180007975`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180007aa1`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180007aa1`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180007868`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180007868`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180007aab`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180007aab`
- `EFSCORE!EfsDllGetUserInfo` at `0x180007a27`
- `EFSCORE!EfsDllGetUserInfo` at `0x180007a27`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180007a3b`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180007a3b`
- `EFSCORE!EfsDllShareDecline` at `0x180007905`
- `EFSCORE!EfsDllShareDecline` at `0x180007905`
- `EFSCORE!EfsDllFreeHeap` at `0x180007ac0`
- `EFSCORE!EfsDllFreeHeap` at `0x180007ac0`
- `EFSCORE!EfsDllCheckFileAccess` at `0x180007a58`
- `EFSCORE!EfsDllCheckFileAccess` at `0x180007a58`
- `FeClient!EfsClientFileEncryptionStatus` at `0x1800079a4`
- `FeClient!EfsClientFileEncryptionStatus` at `0x1800079a4`

## pseudocode

```c
__int64 __fastcall EfspEncryptFileCommonPrologue(
        void *a1,
        __int64 a2,
        LPCWSTR *a3,
        int a4,
        DWORD a5,
        _WORD *a6,
        int *a7,
        _DWORD *a8)
{
  DWORD LocalFileName; // eax
  int v12; // ecx
  RPC_STATUS v13; // eax
  int v14; // ecx
  DWORD LastError; // eax
  int v16; // ecx
  int v17; // ebx
  DWORD FileAttributesW; // eax
  DWORD v19; // eax
  int v20; // ecx
  int v21; // r8d
  int v22; // edx
  _WORD *v23; // rcx
  char v25; // [rsp+28h] [rbp-69h]
  LPCWSTR lpFileName[2]; // [rsp+38h] [rbp-59h] BYREF
  _BYTE v27[112]; // [rsp+48h] [rbp-49h] BYREF
  __int16 v28; // [rsp+F0h] [rbp+5Fh] BYREF
  __int16 v29; // [rsp+F2h] [rbp+61h]

  v29 = HIWORD(a4);
  a5 = 0;
  lpFileName[0] = 0;
  v28 = 0;
  memset_0(v27, 0, sizeof(v27));
  LocalFileName = EfsDllGetLocalFileName(a2, 0, lpFileName, &v28);
  a5 = LocalFileName;
  if ( !LocalFileName )
  {
    v13 = RpcImpersonateClient(0);
    a5 = v13;
    if ( v13 )
    {
      fnEfsLogTrace1(v14, (unsigned int)EFS_API_ERROR, v13, 6, 54);
      goto LABEL_51;
    }
    LastError = EfsEnsureLocalPath(lpFileName[0]);
    a5 = LastError;
    if ( LastError )
    {
      v25 = 60;
LABEL_8:
      fnEfsLogTrace1(v16, (unsigned int)EFS_API_ERROR, LastError, 6, v25);
      goto LABEL_50;
    }
    v17 = 1;
    if ( (unsigned int)EfspCheckForNetSession() )
    {
      if ( v28 == 1 )
        goto LABEL_37;
      if ( (unsigned int)EfsDllShareDecline(a2, 1, 387) )
      {
        LastError = GetLastError();
        a5 = LastError;
        v25 = 76;
        goto LABEL_8;
      }
      LastError = EfspIsValidNetworkProtSeq(a1);
      a5 = LastError;
      if ( LastError )
      {
        v25 = 85;
        goto LABEL_8;
      }
    }
    if ( v28 == 1 )
    {
      FileAttributesW = GetFileAttributesW(lpFileName[0]);
      if ( FileAttributesW == -1 )
      {
        LastError = GetLastError();
        a5 = LastError;
        v25 = 99;
        goto LABEL_8;
      }
      if ( (FileAttributesW & 0x4000) != 0 )
        a5 = 1;
      else
        a5 = (FileAttributesW & 1) != 0 ? 8 : 5;
    }
    else if ( !(unsigned int)EfsClientFileEncryptionStatus(lpFileName[0], &a5) )
    {
      v21 = a5;
      if ( !a5 )
      {
        v21 = 13;
        a5 = 13;
      }
      fnEfsLogTrace1(v20, (unsigned int)EFS_API_ERROR, v21, 6, 133);
      goto LABEL_50;
    }
    v19 = GetFileAttributesW(lpFileName[0]);
    if ( v19 == -1 )
      goto LABEL_22;
    v22 = 0;
    if ( (v19 & 0x10) != 0 )
      *a8 = 1;
    switch ( a5 )
    {
      case 0u:
      case 5u:
        a5 = 0;
        break;
      case 9u:
        a5 = 6010;
        goto LABEL_50;
      case 8u:
        a5 = 6009;
        goto LABEL_50;
      case 1u:
        if ( (v19 & 0x10) == 0 )
        {
          if ( !(unsigned __int8)EfsDllGetUserInfo(v27) )
          {
LABEL_22:
            a5 = GetLastError();
LABEL_50:
            RpcRevertToSelf();
            goto LABEL_51;
          }
          if ( !(unsigned int)EfsDllLoadUserProfile(v27, 0) )
          {
            a5 = GetLastError();
LABEL_49:
            EfsDllFreeUserInfo(v27);
            goto LABEL_50;
          }
          if ( (int)EfsDllCheckFileAccess(v27, lpFileName[0]) < 0 )
          {
            a5 = 5;
LABEL_48:
            EfsDllUnloadUserProfile(v27);
            goto LABEL_49;
          }
          v22 = 1;
        }
        v17 = 0;
        a5 = 0;
        break;
      default:
LABEL_37:
        a5 = 5;
        goto LABEL_50;
    }
    v23 = a6;
    *a3 = lpFileName[0];
    lpFileName[0] = 0;
    *v23 = v28;
    *a7 = v17;
    if ( !v22 )
      goto LABEL_50;
    goto LABEL_48;
  }
  fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, LocalFileName, 6, 45);
LABEL_51:
  if ( lpFileName[0] )
    EfsDllFreeHeap(lpFileName[0]);
  return a5;
}

```

## disassembly

```asm
0x180007810  mov     rax, rsp
0x180007813  mov     [rax+8], rbx
0x180007817  mov     [rax+10h], rsi
0x18000781b  mov     [rax+20h], r9d
0x18000781f  push    rbp
0x180007820  push    rdi
0x180007821  push    r14
0x180007823  lea     rbp, [rax-3Fh]
0x180007827  sub     rsp, 0B0h
0x18000782e  xor     eax, eax
0x180007830  mov     [rbp+37h+arg_20], 0
0x180007837  mov     r14, r8
0x18000783a  mov     [rbp+37h+lpFileName], 0
0x180007842  mov     rdi, rdx
0x180007845  mov     [rbp+37h+arg_18], ax
0x180007849  mov     rsi, rcx
0x18000784c  xor     edx, edx; Val
0x18000784e  lea     r8d, [rax+70h]; Size
0x180007852  lea     rcx, [rbp+37h+var_80]; void *
0x180007856  call    memset_0
0x18000785b  lea     r9, [rbp+37h+arg_18]
0x18000785f  xor     edx, edx
0x180007861  lea     r8, [rbp+37h+lpFileName]
0x180007865  mov     rcx, rdi
0x180007868  call    cs:__imp_EfsDllGetLocalFileName
0x18000786e  mov     [rbp+37h+arg_20], eax
0x180007871  test    eax, eax
0x180007873  jz      short loc_180007897
0x180007875  mov     dword ptr [rsp+0C0h+var_A0], 132Dh
0x18000787d  mov     r9d, 6
0x180007883  lea     rdx, EFS_API_ERROR
0x18000788a  mov     r8d, eax
0x18000788d  call    fnEfsLogTrace1
0x180007892  jmp     loc_180007AB7
0x180007897  xor     ecx, ecx; BindingHandle
0x180007899  call    cs:__imp_RpcImpersonateClient
0x18000789f  mov     [rbp+37h+arg_20], eax
0x1800078a2  test    eax, eax
0x1800078a4  jz      short loc_1800078B0
0x1800078a6  mov     dword ptr [rsp+0C0h+var_A0], 1336h
0x1800078ae  jmp     short loc_18000787D
0x1800078b0  mov     rcx, [rbp+37h+lpFileName]
0x1800078b4  call    EfsEnsureLocalPath
0x1800078b9  mov     [rbp+37h+arg_20], eax
0x1800078bc  test    eax, eax
0x1800078be  jz      short loc_1800078E2
0x1800078c0  mov     dword ptr [rsp+0C0h+var_A0], 133Ch
0x1800078c8  mov     r8d, eax
0x1800078cb  mov     r9d, 6
0x1800078d1  lea     rdx, EFS_API_ERROR
0x1800078d8  call    fnEfsLogTrace1
0x1800078dd  jmp     loc_180007AB1
0x1800078e2  call    EfspCheckForNetSession
0x1800078e7  mov     ebx, 1
0x1800078ec  test    eax, eax
0x1800078ee  jz      short loc_18000793B
0x1800078f0  cmp     [rbp+37h+arg_18], bx
0x1800078f4  jz      loc_180007A13
0x1800078fa  mov     r8d, 183h
0x180007900  mov     edx, ebx
0x180007902  mov     rcx, rdi
0x180007905  call    cs:__imp_EfsDllShareDecline
0x18000790b  test    eax, eax
0x18000790d  jz      short loc_180007922
0x18000790f  call    cs:__imp_GetLastError
0x180007915  mov     [rbp+37h+arg_20], eax
0x180007918  mov     dword ptr [rsp+0C0h+var_A0], 134Ch
0x180007920  jmp     short loc_1800078C8
0x180007922  mov     rcx, rsi
0x180007925  call    EfspIsValidNetworkProtSeq
0x18000792a  mov     [rbp+37h+arg_20], eax
0x18000792d  test    eax, eax
0x18000792f  jz      short loc_18000793B
0x180007931  mov     dword ptr [rsp+0C0h+var_A0], 1355h
0x180007939  jmp     short loc_1800078C8
0x18000793b  mov     rcx, [rbp+37h+lpFileName]; lpFileName
0x18000793f  or      edi, 0FFFFFFFFh
0x180007942  cmp     [rbp+37h+arg_18], bx
0x180007946  jnz     short loc_1800079A0
0x180007948  call    cs:__imp_GetFileAttributesW
0x18000794e  cmp     eax, edi
0x180007950  jnz     short loc_180007968
0x180007952  call    cs:__imp_GetLastError
0x180007958  mov     [rbp+37h+arg_20], eax
0x18000795b  mov     dword ptr [rsp+0C0h+var_A0], 1363h
0x180007963  jmp     loc_1800078C8
0x180007968  bt      eax, 0Eh
0x18000796c  jnb     short loc_18000798F
0x18000796e  mov     [rbp+37h+arg_20], ebx
0x180007971  mov     rcx, [rbp+37h+lpFileName]; lpFileName
0x180007975  call    cs:__imp_GetFileAttributesW
0x18000797b  mov     ecx, eax
0x18000797d  cmp     eax, edi
0x18000797f  jnz     short loc_1800079CC
0x180007981  call    cs:__imp_GetLastError
0x180007987  mov     [rbp+37h+arg_20], eax
0x18000798a  jmp     loc_180007AB1
0x18000798f  and     al, bl
0x180007991  neg     al
0x180007993  sbb     eax, eax
0x180007995  and     eax, 3
0x180007998  add     eax, 5
0x18000799b  mov     [rbp+37h+arg_20], eax
0x18000799e  jmp     short loc_180007971
0x1800079a0  lea     rdx, [rbp+37h+arg_20]
0x1800079a4  call    cs:__imp_EfsClientFileEncryptionStatus
0x1800079aa  test    eax, eax
0x1800079ac  jnz     short loc_180007971
0x1800079ae  mov     r8d, [rbp+37h+arg_20]
0x1800079b2  test    r8d, r8d
0x1800079b5  jnz     short loc_1800079BF
0x1800079b7  lea     r8d, [rax+0Dh]
0x1800079bb  mov     [rbp+37h+arg_20], r8d
0x1800079bf  mov     dword ptr [rsp+0C0h+var_A0], 1385h
0x1800079c7  jmp     loc_1800078CB
0x1800079cc  xor     edx, edx
0x1800079ce  and     ecx, 10h
0x1800079d1  jz      short loc_1800079D9
0x1800079d3  mov     rax, [rbp+37h+arg_38]
0x1800079d7  mov     [rax], ebx
0x1800079d9  mov     eax, [rbp+37h+arg_20]
0x1800079dc  test    eax, eax
0x1800079de  jz      loc_180007A76
0x1800079e4  cmp     eax, 5
0x1800079e7  jz      loc_180007A76
0x1800079ed  cmp     eax, 9
0x1800079f0  jnz     short loc_1800079FE
0x1800079f2  mov     [rbp+37h+arg_20], 177Ah
0x1800079f9  jmp     loc_180007AB1
0x1800079fe  cmp     eax, 8
0x180007a01  jnz     short loc_180007A0F
0x180007a03  mov     [rbp+37h+arg_20], 1779h
0x180007a0a  jmp     loc_180007AB1
0x180007a0f  cmp     eax, ebx
0x180007a11  jz      short loc_180007A1F
0x180007a13  mov     [rbp+37h+arg_20], 5
0x180007a1a  jmp     loc_180007AB1
0x180007a1f  test    ecx, ecx
0x180007a21  jnz     short loc_180007A6D
0x180007a23  lea     rcx, [rbp+37h+var_80]
0x180007a27  call    cs:__imp_EfsDllGetUserInfo
0x180007a2d  test    al, al
0x180007a2f  jz      loc_180007981
0x180007a35  xor     edx, edx
0x180007a37  lea     rcx, [rbp+37h+var_80]
0x180007a3b  call    cs:__imp_EfsDllLoadUserProfile
0x180007a41  test    eax, eax
0x180007a43  jnz     short loc_180007A50
0x180007a45  call    cs:__imp_GetLastError
0x180007a4b  mov     [rbp+37h+arg_20], eax
0x180007a4e  jmp     short loc_180007AA7
0x180007a50  mov     rdx, [rbp+37h+lpFileName]
0x180007a54  lea     rcx, [rbp+37h+var_80]
0x180007a58  call    cs:__imp_EfsDllCheckFileAccess
0x180007a5e  test    eax, eax
0x180007a60  jns     short loc_180007A6B
0x180007a62  mov     [rbp+37h+arg_20], 5
0x180007a69  jmp     short loc_180007A9D
0x180007a6b  mov     edx, ebx
0x180007a6d  xor     eax, eax
0x180007a6f  xor     ebx, ebx
0x180007a71  mov     [rbp+37h+arg_20], eax
0x180007a74  jmp     short loc_180007A79
0x180007a76  mov     [rbp+37h+arg_20], edx
0x180007a79  mov     rax, [rbp+37h+lpFileName]
0x180007a7d  mov     rcx, [rbp+37h+arg_28]
0x180007a81  mov     [r14], rax
0x180007a84  movzx   eax, [rbp+37h+arg_18]
0x180007a88  mov     [rbp+37h+lpFileName], 0
0x180007a90  mov     [rcx], ax
0x180007a93  mov     rax, [rbp+37h+arg_30]
0x180007a97  mov     [rax], ebx
0x180007a99  test    edx, edx
0x180007a9b  jz      short loc_180007AB1
0x180007a9d  lea     rcx, [rbp+37h+var_80]
0x180007aa1  call    cs:__imp_EfsDllUnloadUserProfile
0x180007aa7  lea     rcx, [rbp+37h+var_80]
0x180007aab  call    cs:__imp_EfsDllFreeUserInfo
0x180007ab1  call    cs:__imp_RpcRevertToSelf
0x180007ab7  mov     rcx, [rbp+37h+lpFileName]
0x180007abb  test    rcx, rcx
0x180007abe  jz      short loc_180007AC6
0x180007ac0  call    cs:__imp_EfsDllFreeHeap
0x180007ac6  mov     eax, [rbp+37h+arg_20]
0x180007ac9  lea     r11, [rsp+0C0h+var_10]
0x180007ad1  mov     rbx, [r11+20h]
0x180007ad5  mov     rsi, [r11+28h]
0x180007ad9  mov     rsp, r11
0x180007adc  pop     r14
0x180007ade  pop     rdi
0x180007adf  pop     rbp
0x180007ae0  retn
```
