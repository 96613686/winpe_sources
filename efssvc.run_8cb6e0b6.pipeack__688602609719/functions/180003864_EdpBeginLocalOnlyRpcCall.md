# EdpBeginLocalOnlyRpcCall

- ea: `0x180003864`
- end: `0x180003a1e`
- name: `EdpBeginLocalOnlyRpcCall`
- size: `442`
- prototype: ``
- caller_count: `22`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180003dd0`
- `0x180003e90`
- `0x180003fe0`
- `0x1800040c0`
- `0x1800041a0`
- `0x180004290`
- `0x180004380`
- `0x180004470`
- `0x180004540`
- `0x180004630`
- `0x1800047c0`
- `0x180004900`
- `0x180004ad0`
- `0x180004b90`
- `0x180004d30`
- `0x180004e00`
- `0x1800052b0`
- `0x1800053b0`
- `0x180005480`
- `0x180005640`
- `0x1800077c0`
- `0x1800084f0`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x18000bf0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003990`
- `RPCRT4!RpcRevertToSelf` at `0x1800039fc`
- `RPCRT4!RpcRevertToSelf` at `0x1800039fc`
- `RPCRT4!RpcImpersonateClient` at `0x180003917`
- `RPCRT4!RpcImpersonateClient` at `0x180003917`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800038ba`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800038ba`
- `EFSCORE!EfsDllDisabled` at `0x180003894`
- `EFSCORE!EfsDllDisabled` at `0x180003894`
- `EFSCORE!EfsDllFreeUserInfo` at `0x1800039ec`
- `EFSCORE!EfsDllFreeUserInfo` at `0x1800039ec`
- `EFSCORE!EfsDllGetUserInfo` at `0x180003947`
- `EFSCORE!EfsDllGetUserInfo` at `0x180003947`
- `EFSCORE!EfsDllLoadUserProfile` at `0x18000397d`
- `EFSCORE!EfsDllLoadUserProfile` at `0x18000397d`

## pseudocode

```c
__int64 __fastcall EdpBeginLocalOnlyRpcCall(__int64 a1)
{
  signed int v2; // ebx
  int v3; // esi
  int v4; // r14d
  RPC_STATUS IsClientLocal; // eax
  int v6; // ecx
  int v7; // eax
  int v8; // ecx
  RPC_STATUS v9; // eax
  int v10; // ecx
  signed int v11; // eax
  int v12; // ecx
  signed int LastError; // eax
  int v14; // ecx
  unsigned int ClientLocalFlag; // [rsp+58h] [rbp+10h] BYREF

  ClientLocalFlag = 0;
  if ( !EfsServerInitialized )
    return (unsigned int)-2147024846;
  if ( (unsigned __int8)EfsDllDisabled(a1) )
    return (unsigned int)-2147018881;
  v3 = 0;
  v4 = 0;
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  v2 = IsClientLocal;
  if ( IsClientLocal )
  {
    if ( IsClientLocal > 0 )
      v2 = (unsigned __int16)IsClientLocal | 0x80070000;
  }
  else
  {
    if ( ClientLocalFlag )
    {
      v7 = EfsEnforceClientAuthentication();
      v2 = v7;
      if ( v7 > 0 )
        v2 = (unsigned __int16)v7 | 0x80070000;
      if ( v2 < 0 )
      {
        fnEfsLogTrace1(v8, (unsigned int)EFS_API_ERROR, v2, 6, 114);
        return (unsigned int)v2;
      }
      v9 = RpcImpersonateClient(0);
      if ( v9 )
      {
        if ( v9 > 0 )
          v2 = (unsigned __int16)v9 | 0x80070000;
        else
          v2 = v9;
        fnEfsLogTrace1(v10, (unsigned int)EFS_API_ERROR, v2, 6, 123);
      }
      else
      {
        v3 = 1;
        if ( (unsigned __int8)EfsDllGetUserInfo(a1) )
        {
          if ( (unsigned int)EfsDllLoadUserProfile(a1, 0) )
            return (unsigned int)v2;
          v4 = 1;
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
          fnEfsLogTrace1(v14, (unsigned int)EFS_API_ERROR, v2, 6, 139);
        }
        else
        {
          v11 = GetLastError();
          v2 = v11;
          if ( v11 > 0 )
            v2 = (unsigned __int16)v11 | 0x80070000;
          fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, v2, 6, 131);
        }
      }
      goto LABEL_28;
    }
    v2 = -2147024891;
  }
  fnEfsLogTrace1(v6, (unsigned int)EFS_API_ERROR, v2, 6, 109);
LABEL_28:
  if ( v2 < 0 )
  {
    if ( v4 )
      EfsDllFreeUserInfo(a1);
    if ( v3 )
      RpcRevertToSelf();
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003864  mov     [rsp+arg_0], rbx
0x180003869  mov     [rsp+arg_10], rbp
0x18000386e  push    rsi
0x18000386f  push    rdi
0x180003870  push    r14
0x180003872  sub     rsp, 30h
0x180003876  cmp     cs:EfsServerInitialized, 0
0x18000387d  mov     rbp, rcx
0x180003880  mov     [rsp+48h+ClientLocalFlag], 0
0x180003888  jnz     short loc_180003894
0x18000388a  mov     ebx, 80070032h
0x18000388f  jmp     loc_180003A08
0x180003894  call    cs:__imp_EfsDllDisabled
0x18000389b  nop     dword ptr [rax+rax+00h]
0x1800038a0  test    al, al
0x1800038a2  jz      short loc_1800038AE
0x1800038a4  mov     ebx, 8007177Fh
0x1800038a9  jmp     loc_180003A08
0x1800038ae  lea     rdx, [rsp+48h+ClientLocalFlag]; ClientLocalFlag
0x1800038b3  xor     ecx, ecx; BindingHandle
0x1800038b5  xor     esi, esi
0x1800038b7  xor     r14d, r14d
0x1800038ba  call    cs:__imp_I_RpcBindingIsClientLocal
0x1800038c1  nop     dword ptr [rax+rax+00h]
0x1800038c6  mov     ebx, eax
0x1800038c8  test    eax, eax
0x1800038ca  jnz     loc_1800039B8
0x1800038d0  cmp     [rsp+48h+ClientLocalFlag], esi
0x1800038d4  jz      loc_1800039B1
0x1800038da  call    EfsEnforceClientAuthentication
0x1800038df  mov     ebx, eax
0x1800038e1  mov     edi, 80070000h
0x1800038e6  test    eax, eax
0x1800038e8  jle     short loc_1800038EF
0x1800038ea  movzx   ebx, ax
0x1800038ed  or      ebx, edi
0x1800038ef  test    ebx, ebx
0x1800038f1  jns     short loc_180003915
0x1800038f3  mov     r9d, 6
0x1800038f9  mov     [rsp+48h+var_28], 972h
0x180003901  mov     r8d, ebx
0x180003904  lea     rdx, EFS_API_ERROR
0x18000390b  call    fnEfsLogTrace1
0x180003910  jmp     loc_180003A08
0x180003915  xor     ecx, ecx; BindingHandle
0x180003917  call    cs:__imp_RpcImpersonateClient
0x18000391e  nop     dword ptr [rax+rax+00h]
0x180003923  test    eax, eax
0x180003925  jz      short loc_18000393F
0x180003927  jg      short loc_18000392D
0x180003929  mov     ebx, eax
0x18000392b  jmp     short loc_180003932
0x18000392d  movzx   ebx, ax
0x180003930  or      ebx, edi
0x180003932  mov     [rsp+48h+var_28], 97Bh
0x18000393a  jmp     loc_1800039CB
0x18000393f  mov     rcx, rbp
0x180003942  mov     esi, 1
0x180003947  call    cs:__imp_EfsDllGetUserInfo
0x18000394e  nop     dword ptr [rax+rax+00h]
0x180003953  test    al, al
0x180003955  jnz     short loc_180003978
0x180003957  call    cs:__imp_GetLastError
0x18000395e  nop     dword ptr [rax+rax+00h]
0x180003963  mov     ebx, eax
0x180003965  test    eax, eax
0x180003967  jle     short loc_18000396E
0x180003969  movzx   ebx, ax
0x18000396c  or      ebx, edi
0x18000396e  mov     [rsp+48h+var_28], 983h
0x180003976  jmp     short loc_1800039CB
0x180003978  xor     edx, edx
0x18000397a  mov     rcx, rbp
0x18000397d  call    cs:__imp_EfsDllLoadUserProfile
0x180003984  nop     dword ptr [rax+rax+00h]
0x180003989  test    eax, eax
0x18000398b  jnz     short loc_180003A08
0x18000398d  mov     r14d, esi
0x180003990  call    cs:__imp_GetLastError
0x180003997  nop     dword ptr [rax+rax+00h]
0x18000399c  mov     ebx, eax
0x18000399e  test    eax, eax
0x1800039a0  jle     short loc_1800039A7
0x1800039a2  movzx   ebx, ax
0x1800039a5  or      ebx, edi
0x1800039a7  mov     [rsp+48h+var_28], 98Bh
0x1800039af  jmp     short loc_1800039CB
0x1800039b1  mov     ebx, 80070005h
0x1800039b6  jmp     short loc_1800039C3
0x1800039b8  jle     short loc_1800039C3
0x1800039ba  movzx   ebx, ax
0x1800039bd  or      ebx, 80070000h
0x1800039c3  mov     [rsp+48h+var_28], 96Dh
0x1800039cb  mov     r9d, 6
0x1800039d1  lea     rdx, EFS_API_ERROR
0x1800039d8  mov     r8d, ebx
0x1800039db  call    fnEfsLogTrace1
0x1800039e0  test    ebx, ebx
0x1800039e2  jns     short loc_180003A08
0x1800039e4  test    r14d, r14d
0x1800039e7  jz      short loc_1800039F8
0x1800039e9  mov     rcx, rbp
0x1800039ec  call    cs:__imp_EfsDllFreeUserInfo
0x1800039f3  nop     dword ptr [rax+rax+00h]
0x1800039f8  test    esi, esi
0x1800039fa  jz      short loc_180003A08
0x1800039fc  call    cs:__imp_RpcRevertToSelf
0x180003a03  nop     dword ptr [rax+rax+00h]
0x180003a08  mov     rbp, [rsp+48h+arg_10]
0x180003a0d  mov     eax, ebx
0x180003a0f  mov     rbx, [rsp+48h+arg_0]
0x180003a14  add     rsp, 30h
0x180003a18  pop     r14
0x180003a1a  pop     rdi
0x180003a1b  pop     rsi
0x180003a1c  retn
```
