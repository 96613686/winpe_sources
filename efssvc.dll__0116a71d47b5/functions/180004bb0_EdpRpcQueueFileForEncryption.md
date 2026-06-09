# EdpRpcQueueFileForEncryption

- ea: `0x180004bb0`
- end: `0x180004e14`
- name: `EdpRpcQueueFileForEncryption`
- size: `612`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003604`
- `0x180004bb0`
- `0x18000b308`
- `0x18000c392`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d3e`
- `RPCRT4!RpcRevertToSelf` at `0x180004d6e`
- `RPCRT4!RpcRevertToSelf` at `0x180004dc7`
- `RPCRT4!RpcRevertToSelf` at `0x180004d6e`
- `RPCRT4!RpcRevertToSelf` at `0x180004dc7`
- `RPCRT4!RpcImpersonateClient` at `0x180004c7e`
- `RPCRT4!RpcImpersonateClient` at `0x180004c7e`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180004c3d`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180004c3d`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180004cab`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180004cab`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180004db3`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180004db3`
- `EFSCORE!EdpDllQueueFileForEncryption` at `0x180004d86`
- `EFSCORE!EdpDllQueueFileForEncryption` at `0x180004d86`
- `EFSCORE!EfsDllDisabled` at `0x180004bfc`
- `EFSCORE!EfsDllDisabled` at `0x180004bfc`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180004dbd`
- `EFSCORE!EfsDllFreeUserInfo` at `0x180004dbd`
- `EFSCORE!EfsDllGetUserInfo` at `0x180004d06`
- `EFSCORE!EfsDllGetUserInfo` at `0x180004d06`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180004d31`
- `EFSCORE!EfsDllLoadUserProfile` at `0x180004d31`

## pseudocode

```c
__int64 __fastcall EdpRpcQueueFileForEncryption(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  int v5; // esi
  unsigned int v9; // ebx
  bool v10; // zf
  RPC_STATUS IsClientLocal; // eax
  int v12; // ecx
  int v13; // eax
  int v14; // ecx
  RPC_STATUS v15; // eax
  int v16; // ecx
  int v17; // ecx
  signed int LastError; // eax
  int v19; // ecx
  signed int v20; // eax
  signed int v21; // eax
  int v22; // ecx
  int v23; // eax
  int v24; // ecx
  char v26; // [rsp+20h] [rbp-81h]
  unsigned int ClientLocalFlag; // [rsp+30h] [rbp-71h] BYREF
  WINBOOL IsMember[3]; // [rsp+34h] [rbp-6Dh] BYREF
  _BYTE v29[24]; // [rsp+40h] [rbp-61h] BYREF
  __int64 v30; // [rsp+58h] [rbp-49h]

  v5 = 0;
  ClientLocalFlag = 0;
  IsMember[0] = 0;
  memset_0(v29, 0, 0x70u);
  if ( !EfsServerInitialized )
    return (unsigned int)-2147024846;
  if ( (unsigned __int8)EfsDllDisabled() )
    return (unsigned int)-2147018881;
  if ( a2 )
  {
    v10 = a3 == 0;
  }
  else
  {
    if ( a3 )
      return (unsigned int)-2147024809;
    v10 = a4 == 0;
  }
  if ( v10 || !a5 )
    return (unsigned int)-2147024809;
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  v9 = IsClientLocal;
  if ( IsClientLocal )
  {
    if ( IsClientLocal > 0 )
      v9 = (unsigned __int16)IsClientLocal | 0x80070000;
    goto LABEL_46;
  }
  if ( !ClientLocalFlag )
  {
    v9 = -2147024891;
LABEL_46:
    fnEfsLogTrace1(v12, (unsigned int)EFS_API_ERROR, v9, 6, 145);
    return v9;
  }
  v13 = EfsEnforceClientAuthentication();
  v9 = v13;
  if ( v13 > 0 )
    v9 = (unsigned __int16)v13 | 0x80070000;
  if ( (v9 & 0x80000000) != 0 )
  {
    fnEfsLogTrace1(v14, (unsigned int)EFS_API_ERROR, v9, 6, 150);
    return v9;
  }
  v15 = RpcImpersonateClient(0);
  v9 = v15;
  if ( v15 )
  {
    if ( v15 > 0 )
      v9 = (unsigned __int16)v15 | 0x80070000;
    fnEfsLogTrace1(v16, (unsigned int)EFS_API_ERROR, v9, 6, 164);
    return v9;
  }
  if ( !CheckTokenMembership(0, g_AdminSid, IsMember) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v26 = -74;
LABEL_26:
    fnEfsLogTrace1(v19, (unsigned int)EFS_API_ERROR, v9, 6, v26);
    goto LABEL_42;
  }
  if ( !IsMember[0] )
  {
    v9 = -2147024891;
    fnEfsLogTrace1(v17, (unsigned int)EFS_API_ERROR, -2147024891, 6, 189);
LABEL_42:
    RpcRevertToSelf();
    return v9;
  }
  if ( !(unsigned __int8)EfsDllGetUserInfo(v29) )
  {
    v20 = GetLastError();
    v9 = v20;
    if ( v20 > 0 )
      v9 = (unsigned __int16)v20 | 0x80070000;
    v26 = -61;
    goto LABEL_26;
  }
  if ( (unsigned int)EfsDllLoadUserProfile(v29, 0) )
  {
    RpcRevertToSelf();
    v23 = EdpDllQueueFileForEncryption(v30, a2, a3, a4, a5);
    v9 = v23;
    if ( v23 < 0 )
      fnEfsLogTrace1(v24, (unsigned int)EFS_API_ERROR, v23, 6, 219);
    EfsDllUnloadUserProfile(v29);
  }
  else
  {
    v5 = 1;
    v21 = GetLastError();
    v9 = v21;
    if ( v21 > 0 )
      v9 = (unsigned __int16)v21 | 0x80070000;
    fnEfsLogTrace1(v22, (unsigned int)EFS_API_ERROR, v9, 6, 203);
  }
  EfsDllFreeUserInfo(v29);
  if ( v5 )
    goto LABEL_42;
  return v9;
}

```

## disassembly

```asm
0x180004bb0  push    rbp
0x180004bb2  push    rbx
0x180004bb3  push    rsi
0x180004bb4  push    rdi
0x180004bb5  push    r12
0x180004bb7  push    r13
0x180004bb9  push    r14
0x180004bbb  push    r15
0x180004bbd  lea     rbp, [rsp-17h]
0x180004bc2  sub     rsp, 0B8h
0x180004bc9  xor     esi, esi
0x180004bcb  lea     rcx, [rbp+4Fh+var_B0]; void *
0x180004bcf  mov     r14, r8
0x180004bd2  mov     [rbp+4Fh+ClientLocalFlag], esi
0x180004bd5  mov     r13, rdx
0x180004bd8  mov     [rbp+4Fh+IsMember], esi
0x180004bdb  xor     edx, edx; Val
0x180004bdd  mov     r12, r9
0x180004be0  lea     r8d, [rsi+70h]; Size
0x180004be4  call    memset_0
0x180004be9  cmp     cs:EfsServerInitialized, sil
0x180004bf0  jnz     short loc_180004BFC
0x180004bf2  mov     ebx, 80070032h
0x180004bf7  jmp     loc_180004DFE
0x180004bfc  call    cs:__imp_EfsDllDisabled
0x180004c02  test    al, al
0x180004c04  jz      short loc_180004C10
0x180004c06  mov     ebx, 8007177Fh
0x180004c0b  jmp     loc_180004DFE
0x180004c10  test    r13, r13
0x180004c13  jnz     short loc_180004C29
0x180004c15  test    r14, r14
0x180004c18  jnz     short loc_180004C1F
0x180004c1a  test    r12, r12
0x180004c1d  jnz     short loc_180004C2E
0x180004c1f  mov     ebx, 80070057h
0x180004c24  jmp     loc_180004DFE
0x180004c29  test    r14, r14
0x180004c2c  jmp     short loc_180004C1D
0x180004c2e  mov     r15, [rbp+4Fh+arg_20]
0x180004c32  test    r15, r15
0x180004c35  jz      short loc_180004C1F
0x180004c37  lea     rdx, [rbp+4Fh+ClientLocalFlag]; ClientLocalFlag
0x180004c3b  xor     ecx, ecx; BindingHandle
0x180004c3d  call    cs:__imp_I_RpcBindingIsClientLocal
0x180004c43  mov     ebx, eax
0x180004c45  test    eax, eax
0x180004c47  jnz     loc_180004DD6
0x180004c4d  cmp     [rbp+4Fh+ClientLocalFlag], esi
0x180004c50  jz      loc_180004DCF
0x180004c56  call    EfsEnforceClientAuthentication
0x180004c5b  mov     ebx, eax
0x180004c5d  mov     edi, 80070000h
0x180004c62  test    eax, eax
0x180004c64  jle     short loc_180004C6B
0x180004c66  movzx   ebx, ax
0x180004c69  or      ebx, edi
0x180004c6b  test    ebx, ebx
0x180004c6d  jns     short loc_180004C7C
0x180004c6f  mov     dword ptr [rsp+0F0h+var_D0], 0E96h
0x180004c77  jmp     loc_180004DE9
0x180004c7c  xor     ecx, ecx; BindingHandle
0x180004c7e  call    cs:__imp_RpcImpersonateClient
0x180004c84  mov     ebx, eax
0x180004c86  test    eax, eax
0x180004c88  jz      short loc_180004C9E
0x180004c8a  jle     short loc_180004C91
0x180004c8c  movzx   ebx, ax
0x180004c8f  or      ebx, edi
0x180004c91  mov     dword ptr [rsp+0F0h+var_D0], 0EA4h
0x180004c99  jmp     loc_180004DE9
0x180004c9e  mov     rdx, cs:g_AdminSid; SidToCheck
0x180004ca5  lea     r8, [rbp+4Fh+IsMember]; IsMember
0x180004ca9  xor     ecx, ecx; TokenHandle
0x180004cab  call    cs:__imp_CheckTokenMembership
0x180004cb1  test    eax, eax
0x180004cb3  jnz     short loc_180004CE8
0x180004cb5  call    cs:__imp_GetLastError
0x180004cbb  mov     ebx, eax
0x180004cbd  test    eax, eax
0x180004cbf  jle     short loc_180004CC6
0x180004cc1  movzx   ebx, ax
0x180004cc4  or      ebx, edi
0x180004cc6  mov     dword ptr [rsp+0F0h+var_D0], 0EB6h
0x180004cce  mov     r8d, ebx
0x180004cd1  mov     r9d, 6
0x180004cd7  lea     rdx, EFS_API_ERROR
0x180004cde  call    fnEfsLogTrace1
0x180004ce3  jmp     loc_180004DC7
0x180004ce8  cmp     [rbp+4Fh+IsMember], esi
0x180004ceb  jnz     short loc_180004D02
0x180004ced  mov     ebx, 80070005h
0x180004cf2  mov     dword ptr [rsp+0F0h+var_D0], 0EBDh
0x180004cfa  mov     r8d, 80070005h
0x180004d00  jmp     short loc_180004CD1
0x180004d02  lea     rcx, [rbp+4Fh+var_B0]
0x180004d06  call    cs:__imp_EfsDllGetUserInfo
0x180004d0c  test    al, al
0x180004d0e  jnz     short loc_180004D2B
0x180004d10  call    cs:__imp_GetLastError
0x180004d16  mov     ebx, eax
0x180004d18  test    eax, eax
0x180004d1a  jle     short loc_180004D21
0x180004d1c  movzx   ebx, ax
0x180004d1f  or      ebx, edi
0x180004d21  mov     dword ptr [rsp+0F0h+var_D0], 0EC3h
0x180004d29  jmp     short loc_180004CCE
0x180004d2b  xor     edx, edx
0x180004d2d  lea     rcx, [rbp+4Fh+var_B0]
0x180004d31  call    cs:__imp_EfsDllLoadUserProfile
0x180004d37  test    eax, eax
0x180004d39  jnz     short loc_180004D6E
0x180004d3b  lea     esi, [rax+1]
0x180004d3e  call    cs:__imp_GetLastError
0x180004d44  mov     ebx, eax
0x180004d46  test    eax, eax
0x180004d48  jle     short loc_180004D4F
0x180004d4a  movzx   ebx, ax
0x180004d4d  or      ebx, edi
0x180004d4f  mov     r9d, 6
0x180004d55  mov     dword ptr [rsp+0F0h+var_D0], 0ECBh
0x180004d5d  mov     r8d, ebx
0x180004d60  lea     rdx, EFS_API_ERROR
0x180004d67  call    fnEfsLogTrace1
0x180004d6c  jmp     short loc_180004DB9
0x180004d6e  call    cs:__imp_RpcRevertToSelf
0x180004d74  mov     rcx, [rbp+4Fh+var_98]
0x180004d78  mov     r9, r12
0x180004d7b  mov     r8, r14
0x180004d7e  mov     qword ptr [rsp+0F0h+var_D0], r15
0x180004d83  mov     rdx, r13
0x180004d86  call    cs:__imp_EdpDllQueueFileForEncryption
0x180004d8c  mov     ebx, eax
0x180004d8e  test    eax, eax
0x180004d90  jns     short loc_180004DAF
0x180004d92  mov     r9d, 6
0x180004d98  mov     dword ptr [rsp+0F0h+var_D0], 0EDBh
0x180004da0  mov     r8d, eax
0x180004da3  lea     rdx, EFS_API_ERROR
0x180004daa  call    fnEfsLogTrace1
0x180004daf  lea     rcx, [rbp+4Fh+var_B0]
0x180004db3  call    cs:__imp_EfsDllUnloadUserProfile
0x180004db9  lea     rcx, [rbp+4Fh+var_B0]
0x180004dbd  call    cs:__imp_EfsDllFreeUserInfo
0x180004dc3  test    esi, esi
0x180004dc5  jz      short loc_180004DFE
0x180004dc7  call    cs:__imp_RpcRevertToSelf
0x180004dcd  jmp     short loc_180004DFE
0x180004dcf  mov     ebx, 80070005h
0x180004dd4  jmp     short loc_180004DE1
0x180004dd6  jle     short loc_180004DE1
0x180004dd8  movzx   ebx, ax
0x180004ddb  or      ebx, 80070000h
0x180004de1  mov     dword ptr [rsp+0F0h+var_D0], 0E91h
0x180004de9  mov     r9d, 6
0x180004def  lea     rdx, EFS_API_ERROR
0x180004df6  mov     r8d, ebx
0x180004df9  call    fnEfsLogTrace1
0x180004dfe  mov     eax, ebx
0x180004e00  add     rsp, 0B8h
0x180004e07  pop     r15
0x180004e09  pop     r14
0x180004e0b  pop     r13
0x180004e0d  pop     r12
0x180004e0f  pop     rdi
0x180004e10  pop     rsi
0x180004e11  pop     rbx
0x180004e12  pop     rbp
0x180004e13  retn
```
