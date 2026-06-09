# EfsRpcQueryRecoveryAgents

- ea: `0x1800070d0`
- end: `0x1800072a3`
- name: `EfsRpcQueryRecoveryAgents`
- size: `467`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x1800036a0`
- `0x1800036e0`
- `0x1800037b8`
- `0x1800070d0`
- `0x180007f38`
- `0x180008404`
- `0x18000bf0c`
- `0x18000c094`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000720e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000720e`
- `RPCRT4!RpcRevertToSelf` at `0x180007275`
- `RPCRT4!RpcRevertToSelf` at `0x180007275`
- `RPCRT4!RpcImpersonateClient` at `0x180007187`
- `RPCRT4!RpcImpersonateClient` at `0x180007187`
- `EFSCORE!EfsDllQueryRecoveryAgentsSrv` at `0x18000724f`
- `EFSCORE!EfsDllQueryRecoveryAgentsSrv` at `0x18000724f`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180007169`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180007169`
- `EFSCORE!EfsDllDisabled` at `0x180007103`
- `EFSCORE!EfsDllDisabled` at `0x180007103`
- `EFSCORE!EfsDllShareDecline` at `0x1800071fe`
- `EFSCORE!EfsDllShareDecline` at `0x1800071fe`
- `EFSCORE!EfsDllFreeHeap` at `0x18000728b`
- `EFSCORE!EfsDllFreeHeap` at `0x18000728b`

## pseudocode

```c
__int64 __fastcall EfsRpcQueryRecoveryAgents(__int64 a1, __int64 a2, _QWORD *a3)
{
  DWORD LastError; // ebx
  unsigned int v7; // eax
  __int64 v8; // rcx
  unsigned int LocalFileName; // eax
  __int64 v10; // rcx
  RPC_STATUS v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // rcx
  char *v15; // rax
  void *v16; // rdi
  _QWORD v18[7]; // [rsp+30h] [rbp-38h] BYREF
  __int16 v19; // [rsp+88h] [rbp+20h] BYREF

  v18[0] = 0;
  v19 = 0;
  if ( !EfsServerInitialized )
    return 50;
  if ( (unsigned __int8)EfsDllDisabled() )
  {
    LastError = 6015;
    goto LABEL_28;
  }
  if ( !a3 )
  {
    LastError = 87;
    goto LABEL_28;
  }
  v7 = EfsEnforceClientAuthentication();
  LastError = v7;
  if ( !v7 )
  {
    LocalFileName = EfsDllGetLocalFileName(a2, 0, v18, &v19);
    LastError = LocalFileName;
    if ( LocalFileName )
    {
      fnEfsLogTrace1(v10, (__int64)EFS_API_ERROR, LocalFileName, 6, 246);
      goto LABEL_28;
    }
    v11 = RpcImpersonateClient(0);
    LastError = v11;
    if ( v11 )
    {
      fnEfsLogTrace1(v12, (__int64)EFS_API_ERROR, v11, 6, 251);
      goto LABEL_28;
    }
    v13 = EfsEnsureLocalPath(v18[0]);
    LastError = v13;
    if ( v13 )
    {
      fnEfsLogTrace1(v14, (__int64)EFS_API_ERROR, v13, 6, 1);
LABEL_27:
      RpcRevertToSelf();
      goto LABEL_28;
    }
    if ( (unsigned int)EfspCheckForNetSession() )
    {
      if ( v19 == 1 )
      {
        LastError = 5;
        goto LABEL_27;
      }
      if ( (unsigned int)EfsDllShareDecline(a2, 1, 128) )
      {
        LastError = GetLastError();
        goto LABEL_27;
      }
      LastError = EfspIsValidNetworkProtSeq(a1);
      if ( LastError )
        goto LABEL_27;
    }
    v15 = (char *)MIDL_user_allocate(0x10u);
    v16 = v15;
    if ( v15 )
    {
      LastError = EfsDllQueryRecoveryAgentsSrv(v18[0], v15, v15 + 8);
      if ( LastError )
      {
        MIDL_user_free(v16);
        *a3 = 0;
      }
      else
      {
        *a3 = v16;
      }
    }
    else
    {
      LastError = 8;
    }
    goto LABEL_27;
  }
  fnEfsLogTrace1(v8, (__int64)EFS_API_ERROR, v7, 6, 241);
LABEL_28:
  if ( v18[0] )
    EfsDllFreeHeap();
  return LastError;
}

```

## disassembly

```asm
0x1800070d0  mov     r11, rsp
0x1800070d3  push    rbx
0x1800070d4  push    rbp
0x1800070d5  push    rsi
0x1800070d6  push    rdi
0x1800070d7  sub     rsp, 48h
0x1800070db  xor     eax, eax
0x1800070dd  mov     qword ptr [r11-38h], 0
0x1800070e5  cmp     cs:EfsServerInitialized, al
0x1800070eb  mov     rsi, r8
0x1800070ee  mov     rdi, rdx
0x1800070f1  mov     [r11+20h], ax
0x1800070f6  mov     rbp, rcx
0x1800070f9  jnz     short loc_180007103
0x1800070fb  lea     ebx, [rax+32h]
0x1800070fe  jmp     loc_180007297
0x180007103  call    cs:__imp_EfsDllDisabled
0x18000710a  nop     dword ptr [rax+rax+00h]
0x18000710f  test    al, al
0x180007111  jz      short loc_18000711D
0x180007113  mov     ebx, 177Fh
0x180007118  jmp     loc_180007281
0x18000711d  test    rsi, rsi
0x180007120  jnz     short loc_18000712A
0x180007122  lea     ebx, [rsi+57h]
0x180007125  jmp     loc_180007281
0x18000712a  call    EfsEnforceClientAuthentication
0x18000712f  mov     ebx, eax
0x180007131  test    eax, eax
0x180007133  jz      short loc_180007157
0x180007135  mov     [rsp+68h+var_48], 4F1h
0x18000713d  mov     r9d, 6
0x180007143  lea     rdx, EFS_API_ERROR
0x18000714a  mov     r8d, eax
0x18000714d  call    fnEfsLogTrace1
0x180007152  jmp     loc_180007281
0x180007157  lea     r9, [rsp+68h+arg_18]
0x18000715f  xor     edx, edx
0x180007161  lea     r8, [rsp+68h+var_38]
0x180007166  mov     rcx, rdi
0x180007169  call    cs:__imp_EfsDllGetLocalFileName
0x180007170  nop     dword ptr [rax+rax+00h]
0x180007175  mov     ebx, eax
0x180007177  test    eax, eax
0x180007179  jz      short loc_180007185
0x18000717b  mov     [rsp+68h+var_48], 4F6h
0x180007183  jmp     short loc_18000713D
0x180007185  xor     ecx, ecx; BindingHandle
0x180007187  call    cs:__imp_RpcImpersonateClient
0x18000718e  nop     dword ptr [rax+rax+00h]
0x180007193  mov     ebx, eax
0x180007195  test    eax, eax
0x180007197  jz      short loc_1800071A3
0x180007199  mov     [rsp+68h+var_48], 4FBh
0x1800071a1  jmp     short loc_18000713D
0x1800071a3  mov     rcx, [rsp+68h+var_38]
0x1800071a8  call    EfsEnsureLocalPath
0x1800071ad  mov     ebx, eax
0x1800071af  test    eax, eax
0x1800071b1  jz      short loc_1800071D5
0x1800071b3  mov     r9d, 6
0x1800071b9  mov     [rsp+68h+var_48], 501h
0x1800071c1  mov     r8d, eax
0x1800071c4  lea     rdx, EFS_API_ERROR
0x1800071cb  call    fnEfsLogTrace1
0x1800071d0  jmp     loc_180007275
0x1800071d5  call    EfspCheckForNetSession
0x1800071da  test    eax, eax
0x1800071dc  jz      short loc_18000722C
0x1800071de  mov     edx, 1
0x1800071e3  cmp     [rsp+68h+arg_18], dx
0x1800071eb  jnz     short loc_1800071F5
0x1800071ed  lea     ebx, [rdx+4]
0x1800071f0  jmp     loc_180007275
0x1800071f5  mov     r8d, 80h
0x1800071fb  mov     rcx, rdi
0x1800071fe  call    cs:__imp_EfsDllShareDecline
0x180007205  nop     dword ptr [rax+rax+00h]
0x18000720a  test    eax, eax
0x18000720c  jz      short loc_18000721E
0x18000720e  call    cs:__imp_GetLastError
0x180007215  nop     dword ptr [rax+rax+00h]
0x18000721a  mov     ebx, eax
0x18000721c  jmp     short loc_180007275
0x18000721e  mov     rcx, rbp
0x180007221  call    EfspIsValidNetworkProtSeq
0x180007226  mov     ebx, eax
0x180007228  test    eax, eax
0x18000722a  jnz     short loc_180007275
0x18000722c  mov     ecx, 10h; size
0x180007231  call    MIDL_user_allocate
0x180007236  mov     rdi, rax
0x180007239  test    rax, rax
0x18000723c  jnz     short loc_180007243
0x18000723e  lea     ebx, [rax+8]
0x180007241  jmp     short loc_180007275
0x180007243  mov     rcx, [rsp+68h+var_38]
0x180007248  lea     r8, [rax+8]
0x18000724c  mov     rdx, rdi
0x18000724f  call    cs:__imp_EfsDllQueryRecoveryAgentsSrv
0x180007256  nop     dword ptr [rax+rax+00h]
0x18000725b  mov     ebx, eax
0x18000725d  test    eax, eax
0x18000725f  jnz     short loc_180007266
0x180007261  mov     [rsi], rdi
0x180007264  jmp     short loc_180007275
0x180007266  mov     rcx, rdi; void *
0x180007269  call    MIDL_user_free
0x18000726e  mov     qword ptr [rsi], 0
0x180007275  call    cs:__imp_RpcRevertToSelf
0x18000727c  nop     dword ptr [rax+rax+00h]
0x180007281  mov     rcx, [rsp+68h+var_38]
0x180007286  test    rcx, rcx
0x180007289  jz      short loc_180007297
0x18000728b  call    cs:__imp_EfsDllFreeHeap
0x180007292  nop     dword ptr [rax+rax+00h]
0x180007297  mov     eax, ebx
0x180007299  add     rsp, 48h
0x18000729d  pop     rdi
0x18000729e  pop     rsi
0x18000729f  pop     rbp
0x1800072a0  pop     rbx
0x1800072a1  retn
```
