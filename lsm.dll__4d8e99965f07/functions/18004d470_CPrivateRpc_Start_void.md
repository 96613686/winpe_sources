# CPrivateRpc::Start(void)

- ea: `0x18004d470`
- end: `0x18004d69d`
- name: `?Start@CPrivateRpc@@UEAAJXZ`
- size: `557`
- prototype: `__int64 __fastcall(CPrivateRpc *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800077a0`
- `0x18004d470`
- `0x18004e850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d551`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d571`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d675`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d675`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18004d60a`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18004d64b`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18004d60a`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18004d64b`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18004d5aa`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18004d5aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d541`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004d541`

## string_xrefs

- `0x18004d55d`: `Error %d ConvertStringSecurityDescriptorToSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall CPrivateRpc::Start(CPrivateRpc *this)
{
  __int64 v1; // rdx
  WCHAR *v2; // rax
  const wchar_t *v3; // rcx
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  DWORD LastError; // eax
  signed int v19; // eax
  unsigned int v20; // ebx
  unsigned int v21; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-1A8h] BYREF
  WCHAR StringSecurityDescriptor[192]; // [rsp+40h] [rbp-198h] BYREF

  v1 = 2;
  SecurityDescriptor = 0;
  v2 = StringSecurityDescriptor;
  v3 = L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GRGWGX;;;AC)(A;;GRGWGX;;;S-1-15-3-1024-1864111754-7"
        "76273317-3666925027-2523908081-3792458206-3582472437-4114419977-1582884857)";
  do
  {
    v4 = *((_OWORD *)v3 + 1);
    *(_OWORD *)v2 = *(_OWORD *)v3;
    v5 = *((_OWORD *)v3 + 2);
    *((_OWORD *)v2 + 1) = v4;
    v6 = *((_OWORD *)v3 + 3);
    *((_OWORD *)v2 + 2) = v5;
    v7 = *((_OWORD *)v3 + 4);
    *((_OWORD *)v2 + 3) = v6;
    v8 = *((_OWORD *)v3 + 5);
    *((_OWORD *)v2 + 4) = v7;
    v9 = *((_OWORD *)v3 + 6);
    *((_OWORD *)v2 + 5) = v8;
    v10 = *((_OWORD *)v3 + 7);
    v3 += 64;
    *((_OWORD *)v2 + 6) = v9;
    *((_OWORD *)v2 + 7) = v10;
    v2 += 64;
    --v1;
  }
  while ( v1 );
  v11 = *((_OWORD *)v3 + 1);
  *(_OWORD *)v2 = *(_OWORD *)v3;
  v12 = *((_OWORD *)v3 + 2);
  *((_OWORD *)v2 + 1) = v11;
  v13 = *((_OWORD *)v3 + 3);
  *((_OWORD *)v2 + 2) = v12;
  v14 = *((_OWORD *)v3 + 4);
  *((_OWORD *)v2 + 3) = v13;
  v15 = *((_OWORD *)v3 + 5);
  *((_OWORD *)v2 + 4) = v14;
  v16 = *((_OWORD *)v3 + 6);
  *((_OWORD *)v2 + 5) = v15;
  v17 = *(_OWORD *)(v3 + 53);
  *((_OWORD *)v2 + 6) = v16;
  *(_OWORD *)(v2 + 53) = v17;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    _DbgPrintMessage(8, "Error %d ConvertStringSecurityDescriptorToSecurityDescriptor", LastError);
    v19 = GetLastError();
    v20 = v19;
    if ( v19 <= 0 )
      goto LABEL_17;
    v20 = (unsigned __int16)v19;
    goto LABEL_6;
  }
  v21 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0x80u, (RPC_WSTR)L"LSMApi", SecurityDescriptor);
  v20 = v21;
  if ( !v21 || v21 == 1740 )
  {
    v20 = RpcServerRegisterIfEx(qword_1800A1C10, 0, 0, 9u, 0x4D2u, CPrivateRpc::staticPrivateRpcSecurityCallback);
    if ( v20 )
    {
      _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( private )", v20);
    }
    else
    {
      v20 = RpcServerRegisterIfEx(qword_1800A1EF0, 0, 0, 9u, 0x4D2u, CPrivateRpc::staticAdminRpcSecurityCallback);
      if ( !v20 )
      {
        v20 = 0;
        goto LABEL_17;
      }
      _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( admin )", v20);
    }
  }
  else
  {
    _DbgPrintMessage(8, "Error %d RpcUseProtseqEp on ncalrpc", v21);
  }
  if ( (int)v20 > 0 )
  {
    v20 = (unsigned __int16)v20;
LABEL_6:
    v20 |= 0x80070000;
  }
LABEL_17:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v20;
}

```

## disassembly

```asm
0x18004d470  push    rbx
0x18004d472  sub     rsp, 1D0h
0x18004d479  mov     rax, cs:__security_cookie
0x18004d480  xor     rax, rsp
0x18004d483  mov     [rsp+1D8h+var_18], rax
0x18004d48b  mov     edx, 2
0x18004d490  mov     [rsp+1D8h+SecurityDescriptor], 0
0x18004d499  lea     rax, [rsp+1D8h+StringSecurityDescriptor]
0x18004d49e  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18004d4a5  lea     ebx, [rdx+7Eh]
0x18004d4a8  movups  xmm0, xmmword ptr [rcx]
0x18004d4ab  movups  xmm1, xmmword ptr [rcx+10h]
0x18004d4af  movups  xmmword ptr [rax], xmm0
0x18004d4b2  movups  xmm0, xmmword ptr [rcx+20h]
0x18004d4b6  movups  xmmword ptr [rax+10h], xmm1
0x18004d4ba  movups  xmm1, xmmword ptr [rcx+30h]
0x18004d4be  movups  xmmword ptr [rax+20h], xmm0
0x18004d4c2  movups  xmm0, xmmword ptr [rcx+40h]
0x18004d4c6  movups  xmmword ptr [rax+30h], xmm1
0x18004d4ca  movups  xmm1, xmmword ptr [rcx+50h]
0x18004d4ce  movups  xmmword ptr [rax+40h], xmm0
0x18004d4d2  movups  xmm0, xmmword ptr [rcx+60h]
0x18004d4d6  movups  xmmword ptr [rax+50h], xmm1
0x18004d4da  movups  xmm1, xmmword ptr [rcx+70h]
0x18004d4de  add     rcx, rbx
0x18004d4e1  movups  xmmword ptr [rax+60h], xmm0
0x18004d4e5  movups  xmmword ptr [rax+70h], xmm1
0x18004d4e9  add     rax, rbx
0x18004d4ec  sub     rdx, 1
0x18004d4f0  jnz     short loc_18004D4A8
0x18004d4f2  movups  xmm0, xmmword ptr [rcx]
0x18004d4f5  xor     r9d, r9d; SecurityDescriptorSize
0x18004d4f8  lea     r8, [rsp+1D8h+SecurityDescriptor]; SecurityDescriptor
0x18004d4fd  movups  xmm1, xmmword ptr [rcx+10h]
0x18004d501  movups  xmmword ptr [rax], xmm0
0x18004d504  lea     edx, [r9+1]; StringSDRevision
0x18004d508  movups  xmm0, xmmword ptr [rcx+20h]
0x18004d50c  movups  xmmword ptr [rax+10h], xmm1
0x18004d510  movups  xmm1, xmmword ptr [rcx+30h]
0x18004d514  movups  xmmword ptr [rax+20h], xmm0
0x18004d518  movups  xmm0, xmmword ptr [rcx+40h]
0x18004d51c  movups  xmmword ptr [rax+30h], xmm1
0x18004d520  movups  xmm1, xmmword ptr [rcx+50h]
0x18004d524  movups  xmmword ptr [rax+40h], xmm0
0x18004d528  movups  xmm0, xmmword ptr [rcx+60h]
0x18004d52c  movups  xmmword ptr [rax+50h], xmm1
0x18004d530  movups  xmm1, xmmword ptr [rcx+6Ah]
0x18004d534  lea     rcx, [rsp+1D8h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18004d539  movups  xmmword ptr [rax+60h], xmm0
0x18004d53d  movups  xmmword ptr [rax+6Ah], xmm1
0x18004d541  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004d548  nop     dword ptr [rax+rax+00h]
0x18004d54d  test    eax, eax
0x18004d54f  jnz     short loc_18004D595
0x18004d551  call    cs:__imp_GetLastError
0x18004d558  nop     dword ptr [rax+rax+00h]
0x18004d55d  lea     rdx, aErrorDConverts; "Error %d ConvertStringSecurityDescripto"...
0x18004d564  mov     ecx, 8; int
0x18004d569  mov     r8d, eax
0x18004d56c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004d571  call    cs:__imp_GetLastError
0x18004d578  nop     dword ptr [rax+rax+00h]
0x18004d57d  mov     ebx, eax
0x18004d57f  test    eax, eax
0x18004d581  jle     loc_18004D66B
0x18004d587  movzx   ebx, ax
0x18004d58a  or      ebx, 80070000h
0x18004d590  jmp     loc_18004D66B
0x18004d595  mov     r9, [rsp+1D8h+SecurityDescriptor]; SecurityDescriptor
0x18004d59a  lea     r8, aLsmapi_0; "LSMApi"
0x18004d5a1  mov     edx, ebx; MaxCalls
0x18004d5a3  lea     rcx, ProtSeq; "ncalrpc"
0x18004d5aa  call    cs:__imp_RpcServerUseProtseqEpW
0x18004d5b1  nop     dword ptr [rax+rax+00h]
0x18004d5b6  mov     ebx, eax
0x18004d5b8  test    eax, eax
0x18004d5ba  jz      short loc_18004D5E4
0x18004d5bc  cmp     eax, 6CCh
0x18004d5c1  jz      short loc_18004D5E4
0x18004d5c3  lea     rdx, aErrorDRpcusepr; "Error %d RpcUseProtseqEp on ncalrpc"
0x18004d5ca  mov     r8d, ebx
0x18004d5cd  mov     ecx, 8; int
0x18004d5d2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004d5d7  test    ebx, ebx
0x18004d5d9  jle     loc_18004D66B
0x18004d5df  movzx   ebx, bx
0x18004d5e2  jmp     short loc_18004D58A
0x18004d5e4  lea     rax, ?staticPrivateRpcSecurityCallback@CPrivateRpc@@CAJPEAX0@Z; CPrivateRpc::staticPrivateRpcSecurityCallback(void *,void *)
0x18004d5eb  mov     r9d, 9; Flags
0x18004d5f1  mov     [rsp+1D8h+IfCallback], rax; IfCallback
0x18004d5f6  lea     rcx, qword_1800A1C10; IfSpec
0x18004d5fd  xor     r8d, r8d; MgrEpv
0x18004d600  mov     [rsp+1D8h+MaxCalls], 4D2h; MaxCalls
0x18004d608  xor     edx, edx; MgrTypeUuid
0x18004d60a  call    cs:__imp_RpcServerRegisterIfEx
0x18004d611  nop     dword ptr [rax+rax+00h]
0x18004d616  mov     ebx, eax
0x18004d618  test    eax, eax
0x18004d61a  jz      short loc_18004D625
0x18004d61c  lea     rdx, aErrorDRpcserve; "Error %d RpcServerRegisterIf( private )"
0x18004d623  jmp     short loc_18004D5CA
0x18004d625  lea     rax, ?staticAdminRpcSecurityCallback@CPrivateRpc@@CAJPEAX0@Z; CPrivateRpc::staticAdminRpcSecurityCallback(void *,void *)
0x18004d62c  mov     r9d, 9; Flags
0x18004d632  mov     [rsp+1D8h+IfCallback], rax; IfCallback
0x18004d637  lea     rcx, qword_1800A1EF0; IfSpec
0x18004d63e  xor     r8d, r8d; MgrEpv
0x18004d641  mov     [rsp+1D8h+MaxCalls], 4D2h; MaxCalls
0x18004d649  xor     edx, edx; MgrTypeUuid
0x18004d64b  call    cs:__imp_RpcServerRegisterIfEx
0x18004d652  nop     dword ptr [rax+rax+00h]
0x18004d657  mov     ebx, eax
0x18004d659  test    eax, eax
0x18004d65b  jz      short loc_18004D669
0x18004d65d  lea     rdx, aErrorDRpcserve_3; "Error %d RpcServerRegisterIf( admin )"
0x18004d664  jmp     loc_18004D5CA
0x18004d669  xor     ebx, ebx
0x18004d66b  mov     rcx, [rsp+1D8h+SecurityDescriptor]; hMem
0x18004d670  test    rcx, rcx
0x18004d673  jz      short loc_18004D681
0x18004d675  call    cs:__imp_LocalFree
0x18004d67c  nop     dword ptr [rax+rax+00h]
0x18004d681  mov     eax, ebx
0x18004d683  mov     rcx, [rsp+1D8h+var_18]
0x18004d68b  xor     rcx, rsp; StackCookie
0x18004d68e  call    __security_check_cookie
0x18004d693  add     rsp, 1D0h
0x18004d69a  pop     rbx
0x18004d69b  retn
```
