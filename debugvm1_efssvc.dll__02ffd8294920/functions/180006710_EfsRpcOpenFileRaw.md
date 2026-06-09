# EfsRpcOpenFileRaw

- ea: `0x180006710`
- end: `0x18000688b`
- name: `EfsRpcOpenFileRaw`
- size: `379`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003604`
- `0x180006710`
- `0x1800076b4`
- `0x180007ae8`
- `0x18000b308`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000680c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000680c`
- `RPCRT4!RpcRevertToSelf` at `0x180006866`
- `RPCRT4!RpcRevertToSelf` at `0x180006866`
- `RPCRT4!RpcImpersonateClient` at `0x1800067ca`
- `RPCRT4!RpcImpersonateClient` at `0x1800067ca`
- `EFSCORE!EfsDllGetLocalFileName` at `0x1800067b2`
- `EFSCORE!EfsDllGetLocalFileName` at `0x1800067b2`
- `EFSCORE!EfsDllDisabled` at `0x180006749`
- `EFSCORE!EfsDllDisabled` at `0x180006749`
- `EFSCORE!EfsDllOpenFileRaw` at `0x18000685e`
- `EFSCORE!EfsDllOpenFileRaw` at `0x18000685e`
- `EFSCORE!EfsDllShareDecline` at `0x180006802`
- `EFSCORE!EfsDllShareDecline` at `0x180006802`
- `EFSCORE!EfsDllFreeHeap` at `0x180006876`
- `EFSCORE!EfsDllFreeHeap` at `0x180006876`

## pseudocode

```c
__int64 __fastcall EfsRpcOpenFileRaw(__int64 a1, _QWORD *a2, __int64 a3, unsigned int a4)
{
  DWORD LastError; // ebx
  DWORD v9; // eax
  int v10; // ecx
  DWORD LocalFileName; // eax
  int v12; // ecx
  RPC_STATUS v13; // eax
  int v14; // ecx
  unsigned int v15; // esi
  int v16; // ecx
  DWORD IsValidNetworkProtSeq; // eax
  int v18; // ecx
  __int16 v20; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v21[8]; // [rsp+38h] [rbp-40h] BYREF

  v21[0] = 0;
  v20 = 0;
  if ( !EfsServerInitialized )
    return 50;
  if ( (unsigned __int8)EfsDllDisabled() )
  {
    LastError = 6015;
    goto LABEL_25;
  }
  if ( !a2 && !a3 )
  {
    LastError = 5;
    goto LABEL_25;
  }
  v9 = EfsEnforceClientAuthentication();
  LastError = v9;
  if ( !v9 )
  {
    *a2 = 0;
    LocalFileName = EfsDllGetLocalFileName(a3, 0, v21, &v20);
    LastError = LocalFileName;
    if ( LocalFileName )
    {
      fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, LocalFileName, 6, 147);
      goto LABEL_25;
    }
    v13 = RpcImpersonateClient(0);
    LastError = v13;
    if ( v13 )
    {
      fnEfsLogTrace1(v14, (unsigned int)EFS_API_ERROR, v13, 6, 152);
      goto LABEL_25;
    }
    v15 = EfspCheckForNetSession();
    if ( v15 )
    {
      if ( v20 == 1 )
      {
        LastError = 5;
LABEL_24:
        RpcRevertToSelf();
        goto LABEL_25;
      }
      if ( (unsigned int)EfsDllShareDecline(a3, 0, 0) )
      {
        LastError = GetLastError();
        fnEfsLogTrace1(v16, (unsigned int)EFS_API_ERROR, LastError, 6, 171);
        goto LABEL_24;
      }
      IsValidNetworkProtSeq = EfspIsValidNetworkProtSeq(a1);
      LastError = IsValidNetworkProtSeq;
      if ( IsValidNetworkProtSeq )
      {
        fnEfsLogTrace1(v18, (unsigned int)EFS_API_ERROR, IsValidNetworkProtSeq, 6, 180);
        goto LABEL_24;
      }
    }
    LastError = EfsDllOpenFileRaw(a3, v21[0], v15, a4, a2);
    goto LABEL_24;
  }
  fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, v9, 6, 141);
LABEL_25:
  if ( v21[0] )
    EfsDllFreeHeap();
  return LastError;
}

```

## disassembly

```asm
0x180006710  push    rbx
0x180006712  push    rbp
0x180006713  push    rsi
0x180006714  push    rdi
0x180006715  push    r14
0x180006717  push    r15
0x180006719  sub     rsp, 48h
0x18000671d  xor     eax, eax
0x18000671f  mov     [rsp+78h+var_40], 0
0x180006728  cmp     cs:EfsServerInitialized, al
0x18000672e  mov     r15d, r9d
0x180006731  mov     rdi, r8
0x180006734  mov     [rsp+78h+var_48], ax
0x180006739  mov     r14, rdx
0x18000673c  mov     rbp, rcx
0x18000673f  jnz     short loc_180006749
0x180006741  lea     ebx, [rax+32h]
0x180006744  jmp     loc_18000687C
0x180006749  call    cs:__imp_EfsDllDisabled
0x18000674f  test    al, al
0x180006751  jz      short loc_18000675D
0x180006753  mov     ebx, 177Fh
0x180006758  jmp     loc_18000686C
0x18000675d  test    r14, r14
0x180006760  jnz     short loc_18000676F
0x180006762  test    rdi, rdi
0x180006765  jnz     short loc_18000676F
0x180006767  lea     ebx, [rdi+5]
0x18000676a  jmp     loc_18000686C
0x18000676f  call    EfsEnforceClientAuthentication
0x180006774  mov     ebx, eax
0x180006776  test    eax, eax
0x180006778  jz      short loc_18000679C
0x18000677a  mov     dword ptr [rsp+78h+var_58], 8Dh
0x180006782  mov     r9d, 6
0x180006788  lea     rdx, EFS_API_ERROR
0x18000678f  mov     r8d, eax
0x180006792  call    fnEfsLogTrace1
0x180006797  jmp     loc_18000686C
0x18000679c  lea     r9, [rsp+78h+var_48]
0x1800067a1  mov     qword ptr [r14], 0
0x1800067a8  lea     r8, [rsp+78h+var_40]
0x1800067ad  xor     edx, edx
0x1800067af  mov     rcx, rdi
0x1800067b2  call    cs:__imp_EfsDllGetLocalFileName
0x1800067b8  mov     ebx, eax
0x1800067ba  test    eax, eax
0x1800067bc  jz      short loc_1800067C8
0x1800067be  mov     dword ptr [rsp+78h+var_58], 93h
0x1800067c6  jmp     short loc_180006782
0x1800067c8  xor     ecx, ecx; BindingHandle
0x1800067ca  call    cs:__imp_RpcImpersonateClient
0x1800067d0  mov     ebx, eax
0x1800067d2  test    eax, eax
0x1800067d4  jz      short loc_1800067E0
0x1800067d6  mov     dword ptr [rsp+78h+var_58], 98h
0x1800067de  jmp     short loc_180006782
0x1800067e0  call    EfspCheckForNetSession
0x1800067e5  mov     esi, eax
0x1800067e7  test    eax, eax
0x1800067e9  jz      short loc_18000684B
0x1800067eb  cmp     [rsp+78h+var_48], 1
0x1800067f1  jnz     short loc_1800067FA
0x1800067f3  mov     ebx, 5
0x1800067f8  jmp     short loc_180006866
0x1800067fa  xor     r8d, r8d
0x1800067fd  xor     edx, edx
0x1800067ff  mov     rcx, rdi
0x180006802  call    cs:__imp_EfsDllShareDecline
0x180006808  test    eax, eax
0x18000680a  jz      short loc_180006833
0x18000680c  call    cs:__imp_GetLastError
0x180006812  mov     ebx, eax
0x180006814  mov     dword ptr [rsp+78h+var_58], 0ABh
0x18000681c  mov     r9d, 6
0x180006822  lea     rdx, EFS_API_ERROR
0x180006829  mov     r8d, eax
0x18000682c  call    fnEfsLogTrace1
0x180006831  jmp     short loc_180006866
0x180006833  mov     rcx, rbp
0x180006836  call    EfspIsValidNetworkProtSeq
0x18000683b  mov     ebx, eax
0x18000683d  test    eax, eax
0x18000683f  jz      short loc_18000684B
0x180006841  mov     dword ptr [rsp+78h+var_58], 0B4h
0x180006849  jmp     short loc_18000681C
0x18000684b  mov     rdx, [rsp+78h+var_40]
0x180006850  mov     r9d, r15d
0x180006853  mov     r8d, esi
0x180006856  mov     [rsp+78h+var_58], r14
0x18000685b  mov     rcx, rdi
0x18000685e  call    cs:__imp_EfsDllOpenFileRaw
0x180006864  mov     ebx, eax
0x180006866  call    cs:__imp_RpcRevertToSelf
0x18000686c  mov     rcx, [rsp+78h+var_40]
0x180006871  test    rcx, rcx
0x180006874  jz      short loc_18000687C
0x180006876  call    cs:__imp_EfsDllFreeHeap
0x18000687c  mov     eax, ebx
0x18000687e  add     rsp, 48h
0x180006882  pop     r15
0x180006884  pop     r14
0x180006886  pop     rdi
0x180006887  pop     rsi
0x180006888  pop     rbp
0x180006889  pop     rbx
0x18000688a  retn
```
