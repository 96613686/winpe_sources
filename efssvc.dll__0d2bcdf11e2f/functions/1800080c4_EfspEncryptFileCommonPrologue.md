# EfspEncryptFileCommonPrologue

- ea: `0x1800080c4`
- end: `0x1800083fc`
- name: `EfspEncryptFileCommonPrologue`
- size: `824`
- prototype: `__int64 __fastcall(__int64, __int64, LPCWSTR *, int, DWORD, _WORD *, int *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006460`

## callees

- `0x1800037b8`
- `0x180007f38`
- `0x1800080c4`
- `0x180008404`
- `0x18000c094`
- `0x18000d192`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000825f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000833b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000825f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000833b`
- `RPCRT4!RpcRevertToSelf` at `0x1800083bf`
- `RPCRT4!RpcRevertToSelf` at `0x1800083bf`
- `RPCRT4!RpcImpersonateClient` at `0x180008153`
- `RPCRT4!RpcImpersonateClient` at `0x180008153`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008214`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000824d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008214`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000824d`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x1800083a3`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x1800083a3`
- `EFSCORE!EfsDllGetLocalFileName` at `0x18000811c`
- `EFSCORE!EfsDllGetLocalFileName` at `0x18000811c`
- `EFSCORE!EfsDllFreeUserInfo` at `0x1800083b3`
- `EFSCORE!EfsDllFreeUserInfo` at `0x1800083b3`
- `EFSCORE!EfsDllGetUserInfo` at `0x180008311`
- `EFSCORE!EfsDllGetUserInfo` at `0x180008311`
- `EFSCORE!EfsDllLoadUserProfile` at `0x18000832b`
- `EFSCORE!EfsDllLoadUserProfile` at `0x18000832b`
- `EFSCORE!EfsDllShareDecline` at `0x1800081c5`
- `EFSCORE!EfsDllShareDecline` at `0x1800081c5`
- `EFSCORE!EfsDllFreeHeap` at `0x1800083d4`
- `EFSCORE!EfsDllFreeHeap` at `0x1800083d4`
- `EFSCORE!EfsDllCheckFileAccess` at `0x180008354`
- `EFSCORE!EfsDllCheckFileAccess` at `0x180008354`
- `FeClient!EfsClientFileEncryptionStatus` at `0x180008288`
- `FeClient!EfsClientFileEncryptionStatus` at `0x180008288`

## pseudocode

```c
__int64 __fastcall EfspEncryptFileCommonPrologue(
        __int64 a1,
        __int64 a2,
        LPCWSTR *a3,
        int a4,
        DWORD a5,
        _WORD *a6,
        int *a7,
        _DWORD *a8)
{
  unsigned int LocalFileName; // eax
  __int64 v12; // rcx
  RPC_STATUS v13; // eax
  __int64 v14; // rcx
  DWORD LastError; // eax
  __int64 v16; // rcx
  int v17; // ebx
  DWORD FileAttributesW; // eax
  DWORD v19; // eax
  __int64 v20; // rcx
  unsigned int v21; // r8d
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
      fnEfsLogTrace1(v14, (__int64)EFS_API_ERROR, v13, 6, 54);
      goto LABEL_51;
    }
    LastError = EfsEnsureLocalPath(lpFileName[0]);
    a5 = LastError;
    if ( LastError )
    {
      v25 = 60;
LABEL_8:
      fnEfsLogTrace1(v16, (__int64)EFS_API_ERROR, LastError, 6, v25);
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
      fnEfsLogTrace1(v20, (__int64)EFS_API_ERROR, v21, 6, 133);
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
  fnEfsLogTrace1(v12, (__int64)EFS_API_ERROR, LocalFileName, 6, 45);
LABEL_51:
  if ( lpFileName[0] )
    EfsDllFreeHeap();
  return a5;
}

```

## disassembly

```asm
0x1800080c4  mov     rax, rsp
0x1800080c7  mov     [rax+8], rbx
0x1800080cb  mov     [rax+10h], rsi
0x1800080cf  mov     [rax+20h], r9d
0x1800080d3  push    rbp
0x1800080d4  push    rdi
0x1800080d5  push    r14
0x1800080d7  lea     rbp, [rax-3Fh]
0x1800080db  sub     rsp, 0B0h
0x1800080e2  xor     eax, eax
0x1800080e4  mov     [rbp+37h+arg_20], 0
0x1800080eb  mov     r14, r8
0x1800080ee  mov     [rbp+37h+lpFileName], 0
0x1800080f6  mov     rdi, rdx
0x1800080f9  mov     [rbp+37h+arg_18], ax
0x1800080fd  mov     rsi, rcx
0x180008100  xor     edx, edx; Val
0x180008102  lea     r8d, [rax+70h]; Size
0x180008106  lea     rcx, [rbp+37h+var_80]; void *
0x18000810a  call    memset_0
0x18000810f  lea     r9, [rbp+37h+arg_18]
0x180008113  xor     edx, edx
0x180008115  lea     r8, [rbp+37h+lpFileName]
0x180008119  mov     rcx, rdi
0x18000811c  call    cs:__imp_EfsDllGetLocalFileName
0x180008123  nop     dword ptr [rax+rax+00h]
0x180008128  mov     [rbp+37h+arg_20], eax
0x18000812b  test    eax, eax
0x18000812d  jz      short loc_180008151
0x18000812f  mov     dword ptr [rsp+0C0h+var_A0], 132Dh
0x180008137  mov     r9d, 6
0x18000813d  lea     rdx, EFS_API_ERROR
0x180008144  mov     r8d, eax
0x180008147  call    fnEfsLogTrace1
0x18000814c  jmp     loc_1800083CB
0x180008151  xor     ecx, ecx; BindingHandle
0x180008153  call    cs:__imp_RpcImpersonateClient
0x18000815a  nop     dword ptr [rax+rax+00h]
0x18000815f  mov     [rbp+37h+arg_20], eax
0x180008162  test    eax, eax
0x180008164  jz      short loc_180008170
0x180008166  mov     dword ptr [rsp+0C0h+var_A0], 1336h
0x18000816e  jmp     short loc_180008137
0x180008170  mov     rcx, [rbp+37h+lpFileName]
0x180008174  call    EfsEnsureLocalPath
0x180008179  mov     [rbp+37h+arg_20], eax
0x18000817c  test    eax, eax
0x18000817e  jz      short loc_1800081A2
0x180008180  mov     dword ptr [rsp+0C0h+var_A0], 133Ch
0x180008188  mov     r8d, eax
0x18000818b  mov     r9d, 6
0x180008191  lea     rdx, EFS_API_ERROR
0x180008198  call    fnEfsLogTrace1
0x18000819d  jmp     loc_1800083BF
0x1800081a2  call    EfspCheckForNetSession
0x1800081a7  mov     ebx, 1
0x1800081ac  test    eax, eax
0x1800081ae  jz      short loc_180008207
0x1800081b0  cmp     [rbp+37h+arg_18], bx
0x1800081b4  jz      loc_1800082FD
0x1800081ba  mov     r8d, 183h
0x1800081c0  mov     edx, ebx
0x1800081c2  mov     rcx, rdi
0x1800081c5  call    cs:__imp_EfsDllShareDecline
0x1800081cc  nop     dword ptr [rax+rax+00h]
0x1800081d1  test    eax, eax
0x1800081d3  jz      short loc_1800081EE
0x1800081d5  call    cs:__imp_GetLastError
0x1800081dc  nop     dword ptr [rax+rax+00h]
0x1800081e1  mov     [rbp+37h+arg_20], eax
0x1800081e4  mov     dword ptr [rsp+0C0h+var_A0], 134Ch
0x1800081ec  jmp     short loc_180008188
0x1800081ee  mov     rcx, rsi
0x1800081f1  call    EfspIsValidNetworkProtSeq
0x1800081f6  mov     [rbp+37h+arg_20], eax
0x1800081f9  test    eax, eax
0x1800081fb  jz      short loc_180008207
0x1800081fd  mov     dword ptr [rsp+0C0h+var_A0], 1355h
0x180008205  jmp     short loc_180008188
0x180008207  mov     rcx, [rbp+37h+lpFileName]; lpFileName
0x18000820b  or      edi, 0FFFFFFFFh
0x18000820e  cmp     [rbp+37h+arg_18], bx
0x180008212  jnz     short loc_180008284
0x180008214  call    cs:__imp_GetFileAttributesW
0x18000821b  nop     dword ptr [rax+rax+00h]
0x180008220  cmp     eax, edi
0x180008222  jnz     short loc_180008240
0x180008224  call    cs:__imp_GetLastError
0x18000822b  nop     dword ptr [rax+rax+00h]
0x180008230  mov     [rbp+37h+arg_20], eax
0x180008233  mov     dword ptr [rsp+0C0h+var_A0], 1363h
0x18000823b  jmp     loc_180008188
0x180008240  bt      eax, 0Eh
0x180008244  jnb     short loc_180008273
0x180008246  mov     [rbp+37h+arg_20], ebx
0x180008249  mov     rcx, [rbp+37h+lpFileName]; lpFileName
0x18000824d  call    cs:__imp_GetFileAttributesW
0x180008254  nop     dword ptr [rax+rax+00h]
0x180008259  mov     ecx, eax
0x18000825b  cmp     eax, edi
0x18000825d  jnz     short loc_1800082B6
0x18000825f  call    cs:__imp_GetLastError
0x180008266  nop     dword ptr [rax+rax+00h]
0x18000826b  mov     [rbp+37h+arg_20], eax
0x18000826e  jmp     loc_1800083BF
0x180008273  and     al, bl
0x180008275  neg     al
0x180008277  sbb     eax, eax
0x180008279  and     eax, 3
0x18000827c  add     eax, 5
0x18000827f  mov     [rbp+37h+arg_20], eax
0x180008282  jmp     short loc_180008249
0x180008284  lea     rdx, [rbp+37h+arg_20]
0x180008288  call    cs:__imp_EfsClientFileEncryptionStatus
0x18000828f  nop     dword ptr [rax+rax+00h]
0x180008294  test    eax, eax
0x180008296  jnz     short loc_180008249
0x180008298  mov     r8d, [rbp+37h+arg_20]
0x18000829c  test    r8d, r8d
0x18000829f  jnz     short loc_1800082A9
0x1800082a1  lea     r8d, [rax+0Dh]
0x1800082a5  mov     [rbp+37h+arg_20], r8d
0x1800082a9  mov     dword ptr [rsp+0C0h+var_A0], 1385h
0x1800082b1  jmp     loc_18000818B
0x1800082b6  xor     edx, edx
0x1800082b8  and     ecx, 10h
0x1800082bb  jz      short loc_1800082C3
0x1800082bd  mov     rax, [rbp+37h+arg_38]
0x1800082c1  mov     [rax], ebx
0x1800082c3  mov     eax, [rbp+37h+arg_20]
0x1800082c6  test    eax, eax
0x1800082c8  jz      loc_180008378
0x1800082ce  cmp     eax, 5
0x1800082d1  jz      loc_180008378
0x1800082d7  cmp     eax, 9
0x1800082da  jnz     short loc_1800082E8
0x1800082dc  mov     [rbp+37h+arg_20], 177Ah
0x1800082e3  jmp     loc_1800083BF
0x1800082e8  cmp     eax, 8
0x1800082eb  jnz     short loc_1800082F9
0x1800082ed  mov     [rbp+37h+arg_20], 1779h
0x1800082f4  jmp     loc_1800083BF
0x1800082f9  cmp     eax, ebx
0x1800082fb  jz      short loc_180008309
0x1800082fd  mov     [rbp+37h+arg_20], 5
0x180008304  jmp     loc_1800083BF
0x180008309  test    ecx, ecx
0x18000830b  jnz     short loc_18000836F
0x18000830d  lea     rcx, [rbp+37h+var_80]
0x180008311  call    cs:__imp_EfsDllGetUserInfo
0x180008318  nop     dword ptr [rax+rax+00h]
0x18000831d  test    al, al
0x18000831f  jz      loc_18000825F
0x180008325  xor     edx, edx
0x180008327  lea     rcx, [rbp+37h+var_80]
0x18000832b  call    cs:__imp_EfsDllLoadUserProfile
0x180008332  nop     dword ptr [rax+rax+00h]
0x180008337  test    eax, eax
0x180008339  jnz     short loc_18000834C
0x18000833b  call    cs:__imp_GetLastError
0x180008342  nop     dword ptr [rax+rax+00h]
0x180008347  mov     [rbp+37h+arg_20], eax
0x18000834a  jmp     short loc_1800083AF
0x18000834c  mov     rdx, [rbp+37h+lpFileName]
0x180008350  lea     rcx, [rbp+37h+var_80]
0x180008354  call    cs:__imp_EfsDllCheckFileAccess
0x18000835b  nop     dword ptr [rax+rax+00h]
0x180008360  test    eax, eax
0x180008362  jns     short loc_18000836D
0x180008364  mov     [rbp+37h+arg_20], 5
0x18000836b  jmp     short loc_18000839F
0x18000836d  mov     edx, ebx
0x18000836f  xor     eax, eax
0x180008371  xor     ebx, ebx
0x180008373  mov     [rbp+37h+arg_20], eax
0x180008376  jmp     short loc_18000837B
0x180008378  mov     [rbp+37h+arg_20], edx
0x18000837b  mov     rax, [rbp+37h+lpFileName]
0x18000837f  mov     rcx, [rbp+37h+arg_28]
0x180008383  mov     [r14], rax
0x180008386  movzx   eax, [rbp+37h+arg_18]
0x18000838a  mov     [rbp+37h+lpFileName], 0
0x180008392  mov     [rcx], ax
0x180008395  mov     rax, [rbp+37h+arg_30]
0x180008399  mov     [rax], ebx
0x18000839b  test    edx, edx
0x18000839d  jz      short loc_1800083BF
0x18000839f  lea     rcx, [rbp+37h+var_80]
0x1800083a3  call    cs:__imp_EfsDllUnloadUserProfile
0x1800083aa  nop     dword ptr [rax+rax+00h]
0x1800083af  lea     rcx, [rbp+37h+var_80]
0x1800083b3  call    cs:__imp_EfsDllFreeUserInfo
0x1800083ba  nop     dword ptr [rax+rax+00h]
0x1800083bf  call    cs:__imp_RpcRevertToSelf
0x1800083c6  nop     dword ptr [rax+rax+00h]
0x1800083cb  mov     rcx, [rbp+37h+lpFileName]
0x1800083cf  test    rcx, rcx
0x1800083d2  jz      short loc_1800083E0
0x1800083d4  call    cs:__imp_EfsDllFreeHeap
0x1800083db  nop     dword ptr [rax+rax+00h]
0x1800083e0  mov     eax, [rbp+37h+arg_20]
0x1800083e3  lea     r11, [rsp+0C0h+var_10]
0x1800083eb  mov     rbx, [r11+20h]
0x1800083ef  mov     rsi, [r11+28h]
0x1800083f3  mov     rsp, r11
0x1800083f6  pop     r14
0x1800083f8  pop     rdi
0x1800083f9  pop     rbp
0x1800083fa  retn
```
