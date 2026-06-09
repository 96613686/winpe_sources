# EfsRpcQueryUsersOnFile

- ea: `0x1800072b0`
- end: `0x180007498`
- name: `EfsRpcQueryUsersOnFile`
- size: `488`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800036a0`
- `0x1800036e0`
- `0x1800037b8`
- `0x1800072b0`
- `0x180007f38`
- `0x180008404`
- `0x18000bf0c`
- `0x18000c094`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073ee`
- `RPCRT4!RpcRevertToSelf` at `0x18000746a`
- `RPCRT4!RpcRevertToSelf` at `0x18000746a`
- `RPCRT4!RpcImpersonateClient` at `0x180007367`
- `RPCRT4!RpcImpersonateClient` at `0x180007367`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180007349`
- `EFSCORE!EfsDllGetLocalFileName` at `0x180007349`
- `EFSCORE!EfsDllDisabled` at `0x1800072e3`
- `EFSCORE!EfsDllDisabled` at `0x1800072e3`
- `EFSCORE!EfsDllShareDecline` at `0x1800073de`
- `EFSCORE!EfsDllShareDecline` at `0x1800073de`
- `EFSCORE!EfsDllFreeHeap` at `0x180007480`
- `EFSCORE!EfsDllFreeHeap` at `0x180007480`
- `EFSCORE!EfsDllQueryUsersOnFileSrv` at `0x180007444`
- `EFSCORE!EfsDllQueryUsersOnFileSrv` at `0x180007444`

## pseudocode

```c
__int64 __fastcall EfsRpcQueryUsersOnFile(__int64 a1, __int64 a2, _QWORD *a3)
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
  __int64 v15; // rcx
  unsigned int IsValidNetworkProtSeq; // eax
  __int64 v17; // rcx
  char *v18; // rax
  void *v19; // rdi
  _QWORD v21[7]; // [rsp+30h] [rbp-38h] BYREF
  __int16 v22; // [rsp+88h] [rbp+20h] BYREF

  v21[0] = 0;
  v22 = 0;
  if ( !EfsServerInitialized )
    return 50;
  if ( (unsigned __int8)EfsDllDisabled() )
  {
    LastError = 6015;
    goto LABEL_30;
  }
  if ( !a3 )
  {
    LastError = 87;
    goto LABEL_30;
  }
  v7 = EfsEnforceClientAuthentication();
  LastError = v7;
  if ( !v7 )
  {
    LocalFileName = EfsDllGetLocalFileName(a2, 0, v21, &v22);
    LastError = LocalFileName;
    if ( LocalFileName )
    {
      fnEfsLogTrace1(v10, (__int64)EFS_API_ERROR, LocalFileName, 6, 136);
      goto LABEL_30;
    }
    v11 = RpcImpersonateClient(0);
    LastError = v11;
    if ( v11 )
    {
      fnEfsLogTrace1(v12, (__int64)EFS_API_ERROR, v11, 6, 141);
      goto LABEL_30;
    }
    v13 = EfsEnsureLocalPath(v21[0]);
    LastError = v13;
    if ( v13 )
    {
      fnEfsLogTrace1(v14, (__int64)EFS_API_ERROR, v13, 6, 147);
      goto LABEL_29;
    }
    if ( (unsigned int)EfspCheckForNetSession() )
    {
      if ( v22 == 1 )
      {
        LastError = 5;
LABEL_29:
        RpcRevertToSelf();
        goto LABEL_30;
      }
      if ( (unsigned int)EfsDllShareDecline(a2, 1, 128) )
      {
        LastError = GetLastError();
        fnEfsLogTrace1(v15, (__int64)EFS_API_ERROR, LastError, 6, 164);
        goto LABEL_29;
      }
      IsValidNetworkProtSeq = EfspIsValidNetworkProtSeq(a1);
      LastError = IsValidNetworkProtSeq;
      if ( IsValidNetworkProtSeq )
      {
        fnEfsLogTrace1(v17, (__int64)EFS_API_ERROR, IsValidNetworkProtSeq, 6, 173);
        goto LABEL_29;
      }
    }
    v18 = (char *)MIDL_user_allocate(0x10u);
    v19 = v18;
    if ( v18 )
    {
      LastError = EfsDllQueryUsersOnFileSrv(v21[0], v18, v18 + 8);
      if ( LastError )
      {
        MIDL_user_free(v19);
        *a3 = 0;
      }
      else
      {
        *a3 = v19;
      }
    }
    else
    {
      LastError = 8;
    }
    goto LABEL_29;
  }
  fnEfsLogTrace1(v8, (__int64)EFS_API_ERROR, v7, 6, 131);
LABEL_30:
  if ( v21[0] )
    EfsDllFreeHeap();
  return LastError;
}

```

## disassembly

```asm
0x1800072b0  mov     r11, rsp
0x1800072b3  push    rbx
0x1800072b4  push    rbp
0x1800072b5  push    rsi
0x1800072b6  push    rdi
0x1800072b7  sub     rsp, 48h
0x1800072bb  xor     eax, eax
0x1800072bd  mov     qword ptr [r11-38h], 0
0x1800072c5  cmp     cs:EfsServerInitialized, al
0x1800072cb  mov     rsi, r8
0x1800072ce  mov     rdi, rdx
0x1800072d1  mov     [r11+20h], ax
0x1800072d6  mov     rbp, rcx
0x1800072d9  jnz     short loc_1800072E3
0x1800072db  lea     ebx, [rax+32h]
0x1800072de  jmp     loc_18000748C
0x1800072e3  call    cs:__imp_EfsDllDisabled
0x1800072ea  nop     dword ptr [rax+rax+00h]
0x1800072ef  test    al, al
0x1800072f1  jz      short loc_1800072FD
0x1800072f3  mov     ebx, 177Fh
0x1800072f8  jmp     loc_180007476
0x1800072fd  test    rsi, rsi
0x180007300  jnz     short loc_18000730A
0x180007302  lea     ebx, [rsi+57h]
0x180007305  jmp     loc_180007476
0x18000730a  call    EfsEnforceClientAuthentication
0x18000730f  mov     ebx, eax
0x180007311  test    eax, eax
0x180007313  jz      short loc_180007337
0x180007315  mov     [rsp+68h+var_48], 483h
0x18000731d  mov     r9d, 6
0x180007323  lea     rdx, EFS_API_ERROR
0x18000732a  mov     r8d, eax
0x18000732d  call    fnEfsLogTrace1
0x180007332  jmp     loc_180007476
0x180007337  lea     r9, [rsp+68h+arg_18]
0x18000733f  xor     edx, edx
0x180007341  lea     r8, [rsp+68h+var_38]
0x180007346  mov     rcx, rdi
0x180007349  call    cs:__imp_EfsDllGetLocalFileName
0x180007350  nop     dword ptr [rax+rax+00h]
0x180007355  mov     ebx, eax
0x180007357  test    eax, eax
0x180007359  jz      short loc_180007365
0x18000735b  mov     [rsp+68h+var_48], 488h
0x180007363  jmp     short loc_18000731D
0x180007365  xor     ecx, ecx; BindingHandle
0x180007367  call    cs:__imp_RpcImpersonateClient
0x18000736e  nop     dword ptr [rax+rax+00h]
0x180007373  mov     ebx, eax
0x180007375  test    eax, eax
0x180007377  jz      short loc_180007383
0x180007379  mov     [rsp+68h+var_48], 48Dh
0x180007381  jmp     short loc_18000731D
0x180007383  mov     rcx, [rsp+68h+var_38]
0x180007388  call    EfsEnsureLocalPath
0x18000738d  mov     ebx, eax
0x18000738f  test    eax, eax
0x180007391  jz      short loc_1800073B5
0x180007393  mov     [rsp+68h+var_48], 493h
0x18000739b  mov     r9d, 6
0x1800073a1  lea     rdx, EFS_API_ERROR
0x1800073a8  mov     r8d, eax
0x1800073ab  call    fnEfsLogTrace1
0x1800073b0  jmp     loc_18000746A
0x1800073b5  call    EfspCheckForNetSession
0x1800073ba  test    eax, eax
0x1800073bc  jz      short loc_180007421
0x1800073be  mov     edx, 1
0x1800073c3  cmp     [rsp+68h+arg_18], dx
0x1800073cb  jnz     short loc_1800073D5
0x1800073cd  lea     ebx, [rdx+4]
0x1800073d0  jmp     loc_18000746A
0x1800073d5  mov     r8d, 80h
0x1800073db  mov     rcx, rdi
0x1800073de  call    cs:__imp_EfsDllShareDecline
0x1800073e5  nop     dword ptr [rax+rax+00h]
0x1800073ea  test    eax, eax
0x1800073ec  jz      short loc_180007406
0x1800073ee  call    cs:__imp_GetLastError
0x1800073f5  nop     dword ptr [rax+rax+00h]
0x1800073fa  mov     ebx, eax
0x1800073fc  mov     [rsp+68h+var_48], 4A4h
0x180007404  jmp     short loc_18000739B
0x180007406  mov     rcx, rbp
0x180007409  call    EfspIsValidNetworkProtSeq
0x18000740e  mov     ebx, eax
0x180007410  test    eax, eax
0x180007412  jz      short loc_180007421
0x180007414  mov     [rsp+68h+var_48], 4ADh
0x18000741c  jmp     loc_18000739B
0x180007421  mov     ecx, 10h; size
0x180007426  call    MIDL_user_allocate
0x18000742b  mov     rdi, rax
0x18000742e  test    rax, rax
0x180007431  jnz     short loc_180007438
0x180007433  lea     ebx, [rax+8]
0x180007436  jmp     short loc_18000746A
0x180007438  mov     rcx, [rsp+68h+var_38]
0x18000743d  lea     r8, [rax+8]
0x180007441  mov     rdx, rdi
0x180007444  call    cs:__imp_EfsDllQueryUsersOnFileSrv
0x18000744b  nop     dword ptr [rax+rax+00h]
0x180007450  mov     ebx, eax
0x180007452  test    eax, eax
0x180007454  jnz     short loc_18000745B
0x180007456  mov     [rsi], rdi
0x180007459  jmp     short loc_18000746A
0x18000745b  mov     rcx, rdi; void *
0x18000745e  call    MIDL_user_free
0x180007463  mov     qword ptr [rsi], 0
0x18000746a  call    cs:__imp_RpcRevertToSelf
0x180007471  nop     dword ptr [rax+rax+00h]
0x180007476  mov     rcx, [rsp+68h+var_38]
0x18000747b  test    rcx, rcx
0x18000747e  jz      short loc_18000748C
0x180007480  call    cs:__imp_EfsDllFreeHeap
0x180007487  nop     dword ptr [rax+rax+00h]
0x18000748c  mov     eax, ebx
0x18000748e  add     rsp, 48h
0x180007492  pop     rdi
0x180007493  pop     rsi
0x180007494  pop     rbp
0x180007495  pop     rbx
0x180007496  retn
```
