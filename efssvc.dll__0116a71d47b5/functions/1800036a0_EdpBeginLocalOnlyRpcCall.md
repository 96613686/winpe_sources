# EdpBeginLocalOnlyRpcCall

- ea: `0x1800036a0`
- end: `0x180003820`
- name: `EdpBeginLocalOnlyRpcCall`
- size: `384`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `22`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180003b80`
- `0x180003c30`
- `0x180003d70`
- `0x180003e50`
- `0x180003f20`
- `0x180004000`
- `0x1800040f0`
- `0x1800041d0`
- `0x180004290`
- `0x180004370`
- `0x1800044f0`
- `0x180004630`
- `0x180004800`
- `0x1800048b0`
- `0x180004a30`
- `0x180004af0`
- `0x180004f30`
- `0x180005030`
- `0x1800050f0`
- `0x1800052a0`
- `0x180007030`
- `0x180007bb0`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x18000b308`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037a5`
- `RPCRT4!RpcRevertToSelf` at `0x180003805`
- `RPCRT4!RpcRevertToSelf` at `0x180003805`
- `RPCRT4!RpcImpersonateClient` at `0x180003747`
- `RPCRT4!RpcImpersonateClient` at `0x180003747`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800036f0`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800036f0`
- `EFSCORE!EfsDllDisabled` at `0x1800036d0`
- `EFSCORE!EfsDllDisabled` at `0x1800036d0`
- `EFSCORE!EfsDllFreeUserInfo` at `0x1800037fb`
- `EFSCORE!EfsDllFreeUserInfo` at `0x1800037fb`
- `EFSCORE!EfsDllGetUserInfo` at `0x18000376e`
- `EFSCORE!EfsDllGetUserInfo` at `0x18000376e`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180003798`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180003798`

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
  if ( (unsigned __int8)EfsDllDisabled() )
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
0x1800036a0  mov     [rsp+arg_0], rbx
0x1800036a5  mov     [rsp+arg_10], rbp
0x1800036aa  push    rsi
0x1800036ab  push    rdi
0x1800036ac  push    r14
0x1800036ae  sub     rsp, 30h
0x1800036b2  cmp     cs:EfsServerInitialized, 0
0x1800036b9  mov     rbp, rcx
0x1800036bc  mov     [rsp+48h+ClientLocalFlag], 0
0x1800036c4  jnz     short loc_1800036D0
0x1800036c6  mov     ebx, 80070032h
0x1800036cb  jmp     loc_18000380B
0x1800036d0  call    cs:__imp_EfsDllDisabled
0x1800036d6  test    al, al
0x1800036d8  jz      short loc_1800036E4
0x1800036da  mov     ebx, 8007177Fh
0x1800036df  jmp     loc_18000380B
0x1800036e4  lea     rdx, [rsp+48h+ClientLocalFlag]; ClientLocalFlag
0x1800036e9  xor     ecx, ecx; BindingHandle
0x1800036eb  xor     esi, esi
0x1800036ed  xor     r14d, r14d
0x1800036f0  call    cs:__imp_I_RpcBindingIsClientLocal
0x1800036f6  mov     ebx, eax
0x1800036f8  test    eax, eax
0x1800036fa  jnz     loc_1800037C7
0x180003700  cmp     [rsp+48h+ClientLocalFlag], esi
0x180003704  jz      loc_1800037C0
0x18000370a  call    EfsEnforceClientAuthentication
0x18000370f  mov     ebx, eax
0x180003711  mov     edi, 80070000h
0x180003716  test    eax, eax
0x180003718  jle     short loc_18000371F
0x18000371a  movzx   ebx, ax
0x18000371d  or      ebx, edi
0x18000371f  test    ebx, ebx
0x180003721  jns     short loc_180003745
0x180003723  mov     r9d, 6
0x180003729  mov     [rsp+48h+var_28], 972h
0x180003731  mov     r8d, ebx
0x180003734  lea     rdx, EFS_API_ERROR
0x18000373b  call    fnEfsLogTrace1
0x180003740  jmp     loc_18000380B
0x180003745  xor     ecx, ecx; BindingHandle
0x180003747  call    cs:__imp_RpcImpersonateClient
0x18000374d  test    eax, eax
0x18000374f  jz      short loc_180003766
0x180003751  jg      short loc_180003757
0x180003753  mov     ebx, eax
0x180003755  jmp     short loc_18000375C
0x180003757  movzx   ebx, ax
0x18000375a  or      ebx, edi
0x18000375c  mov     [rsp+48h+var_28], 97Bh
0x180003764  jmp     short loc_1800037DA
0x180003766  mov     rcx, rbp
0x180003769  mov     esi, 1
0x18000376e  call    cs:__imp_EfsDllGetUserInfo
0x180003774  test    al, al
0x180003776  jnz     short loc_180003793
0x180003778  call    cs:__imp_GetLastError
0x18000377e  mov     ebx, eax
0x180003780  test    eax, eax
0x180003782  jle     short loc_180003789
0x180003784  movzx   ebx, ax
0x180003787  or      ebx, edi
0x180003789  mov     [rsp+48h+var_28], 983h
0x180003791  jmp     short loc_1800037DA
0x180003793  xor     edx, edx
0x180003795  mov     rcx, rbp
0x180003798  call    cs:__imp_EfsDllLoadUserProfile
0x18000379e  test    eax, eax
0x1800037a0  jnz     short loc_18000380B
0x1800037a2  mov     r14d, esi
0x1800037a5  call    cs:__imp_GetLastError
0x1800037ab  mov     ebx, eax
0x1800037ad  test    eax, eax
0x1800037af  jle     short loc_1800037B6
0x1800037b1  movzx   ebx, ax
0x1800037b4  or      ebx, edi
0x1800037b6  mov     [rsp+48h+var_28], 98Bh
0x1800037be  jmp     short loc_1800037DA
0x1800037c0  mov     ebx, 80070005h
0x1800037c5  jmp     short loc_1800037D2
0x1800037c7  jle     short loc_1800037D2
0x1800037c9  movzx   ebx, ax
0x1800037cc  or      ebx, 80070000h
0x1800037d2  mov     [rsp+48h+var_28], 96Dh
0x1800037da  mov     r9d, 6
0x1800037e0  lea     rdx, EFS_API_ERROR
0x1800037e7  mov     r8d, ebx
0x1800037ea  call    fnEfsLogTrace1
0x1800037ef  test    ebx, ebx
0x1800037f1  jns     short loc_18000380B
0x1800037f3  test    r14d, r14d
0x1800037f6  jz      short loc_180003801
0x1800037f8  mov     rcx, rbp
0x1800037fb  call    cs:__imp_EfsDllFreeUserInfo
0x180003801  test    esi, esi
0x180003803  jz      short loc_18000380B
0x180003805  call    cs:__imp_RpcRevertToSelf
0x18000380b  mov     rbp, [rsp+48h+arg_10]
0x180003810  mov     eax, ebx
0x180003812  mov     rbx, [rsp+48h+arg_0]
0x180003817  add     rsp, 30h
0x18000381b  pop     r14
0x18000381d  pop     rdi
0x18000381e  pop     rsi
0x18000381f  retn
```
