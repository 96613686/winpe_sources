# CPrivateRpc::Start(void)

- ea: `0x18004a150`
- end: `0x18004a352`
- name: `?Start@CPrivateRpc@@UEAAJXZ`
- size: `514`
- prototype: `__int64 __fastcall(CPrivateRpc *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800074c0`
- `0x18004a150`
- `0x18004b460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a22b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a22b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a245`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a331`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a331`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18004a2d2`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18004a30d`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18004a2d2`
- `RPCRT4!RpcServerRegisterIfEx` at `0x18004a30d`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18004a278`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18004a278`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a221`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004a221`

## string_xrefs

- `0x18004a231`: `Error %d ConvertStringSecurityDescriptorToSecurityDescriptor`

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
    v20 = RpcServerRegisterIfEx(qword_18009CBC0, 0, 0, 9u, 0x4D2u, CPrivateRpc::staticPrivateRpcSecurityCallback);
    if ( v20 )
    {
      _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( private )", v20);
    }
    else
    {
      v20 = RpcServerRegisterIfEx(qword_18009CF30, 0, 0, 9u, 0x4D2u, CPrivateRpc::staticAdminRpcSecurityCallback);
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
0x18004a150  push    rbx
0x18004a152  sub     rsp, 1D0h
0x18004a159  mov     rax, cs:__security_cookie
0x18004a160  xor     rax, rsp
0x18004a163  mov     [rsp+1D8h+var_18], rax
0x18004a16b  mov     edx, 2
0x18004a170  mov     [rsp+1D8h+SecurityDescriptor], 0
0x18004a179  lea     rax, [rsp+1D8h+StringSecurityDescriptor]
0x18004a17e  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18004a185  lea     ebx, [rdx+7Eh]
0x18004a188  movups  xmm0, xmmword ptr [rcx]
0x18004a18b  movups  xmm1, xmmword ptr [rcx+10h]
0x18004a18f  movups  xmmword ptr [rax], xmm0
0x18004a192  movups  xmm0, xmmword ptr [rcx+20h]
0x18004a196  movups  xmmword ptr [rax+10h], xmm1
0x18004a19a  movups  xmm1, xmmword ptr [rcx+30h]
0x18004a19e  movups  xmmword ptr [rax+20h], xmm0
0x18004a1a2  movups  xmm0, xmmword ptr [rcx+40h]
0x18004a1a6  movups  xmmword ptr [rax+30h], xmm1
0x18004a1aa  movups  xmm1, xmmword ptr [rcx+50h]
0x18004a1ae  movups  xmmword ptr [rax+40h], xmm0
0x18004a1b2  movups  xmm0, xmmword ptr [rcx+60h]
0x18004a1b6  movups  xmmword ptr [rax+50h], xmm1
0x18004a1ba  movups  xmm1, xmmword ptr [rcx+70h]
0x18004a1be  add     rcx, rbx
0x18004a1c1  movups  xmmword ptr [rax+60h], xmm0
0x18004a1c5  movups  xmmword ptr [rax+70h], xmm1
0x18004a1c9  add     rax, rbx
0x18004a1cc  sub     rdx, 1
0x18004a1d0  jnz     short loc_18004A188
0x18004a1d2  movups  xmm0, xmmword ptr [rcx]
0x18004a1d5  xor     r9d, r9d; SecurityDescriptorSize
0x18004a1d8  lea     r8, [rsp+1D8h+SecurityDescriptor]; SecurityDescriptor
0x18004a1dd  movups  xmm1, xmmword ptr [rcx+10h]
0x18004a1e1  movups  xmmword ptr [rax], xmm0
0x18004a1e4  lea     edx, [r9+1]; StringSDRevision
0x18004a1e8  movups  xmm0, xmmword ptr [rcx+20h]
0x18004a1ec  movups  xmmword ptr [rax+10h], xmm1
0x18004a1f0  movups  xmm1, xmmword ptr [rcx+30h]
0x18004a1f4  movups  xmmword ptr [rax+20h], xmm0
0x18004a1f8  movups  xmm0, xmmword ptr [rcx+40h]
0x18004a1fc  movups  xmmword ptr [rax+30h], xmm1
0x18004a200  movups  xmm1, xmmword ptr [rcx+50h]
0x18004a204  movups  xmmword ptr [rax+40h], xmm0
0x18004a208  movups  xmm0, xmmword ptr [rcx+60h]
0x18004a20c  movups  xmmword ptr [rax+50h], xmm1
0x18004a210  movups  xmm1, xmmword ptr [rcx+6Ah]
0x18004a214  lea     rcx, [rsp+1D8h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18004a219  movups  xmmword ptr [rax+60h], xmm0
0x18004a21d  movups  xmmword ptr [rax+6Ah], xmm1
0x18004a221  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004a227  test    eax, eax
0x18004a229  jnz     short loc_18004A263
0x18004a22b  call    cs:__imp_GetLastError
0x18004a231  lea     rdx, aErrorDConverts; "Error %d ConvertStringSecurityDescripto"...
0x18004a238  mov     ecx, 8; int
0x18004a23d  mov     r8d, eax
0x18004a240  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004a245  call    cs:__imp_GetLastError
0x18004a24b  mov     ebx, eax
0x18004a24d  test    eax, eax
0x18004a24f  jle     loc_18004A327
0x18004a255  movzx   ebx, ax
0x18004a258  or      ebx, 80070000h
0x18004a25e  jmp     loc_18004A327
0x18004a263  mov     r9, [rsp+1D8h+SecurityDescriptor]; SecurityDescriptor
0x18004a268  lea     r8, aLsmapi_0; "LSMApi"
0x18004a26f  mov     edx, ebx; MaxCalls
0x18004a271  lea     rcx, ProtSeq; "ncalrpc"
0x18004a278  call    cs:__imp_RpcServerUseProtseqEpW
0x18004a27e  mov     ebx, eax
0x18004a280  test    eax, eax
0x18004a282  jz      short loc_18004A2AC
0x18004a284  cmp     eax, 6CCh
0x18004a289  jz      short loc_18004A2AC
0x18004a28b  lea     rdx, aErrorDRpcusepr; "Error %d RpcUseProtseqEp on ncalrpc"
0x18004a292  mov     r8d, ebx
0x18004a295  mov     ecx, 8; int
0x18004a29a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004a29f  test    ebx, ebx
0x18004a2a1  jle     loc_18004A327
0x18004a2a7  movzx   ebx, bx
0x18004a2aa  jmp     short loc_18004A258
0x18004a2ac  lea     rax, ?staticPrivateRpcSecurityCallback@CPrivateRpc@@CAJPEAX0@Z; CPrivateRpc::staticPrivateRpcSecurityCallback(void *,void *)
0x18004a2b3  mov     r9d, 9; Flags
0x18004a2b9  mov     [rsp+1D8h+IfCallback], rax; IfCallback
0x18004a2be  lea     rcx, qword_18009CBC0; IfSpec
0x18004a2c5  xor     r8d, r8d; MgrEpv
0x18004a2c8  mov     [rsp+1D8h+MaxCalls], 4D2h; MaxCalls
0x18004a2d0  xor     edx, edx; MgrTypeUuid
0x18004a2d2  call    cs:__imp_RpcServerRegisterIfEx
0x18004a2d8  mov     ebx, eax
0x18004a2da  test    eax, eax
0x18004a2dc  jz      short loc_18004A2E7
0x18004a2de  lea     rdx, aErrorDRpcserve; "Error %d RpcServerRegisterIf( private )"
0x18004a2e5  jmp     short loc_18004A292
0x18004a2e7  lea     rax, ?staticAdminRpcSecurityCallback@CPrivateRpc@@CAJPEAX0@Z; CPrivateRpc::staticAdminRpcSecurityCallback(void *,void *)
0x18004a2ee  mov     r9d, 9; Flags
0x18004a2f4  mov     [rsp+1D8h+IfCallback], rax; IfCallback
0x18004a2f9  lea     rcx, qword_18009CF30; IfSpec
0x18004a300  xor     r8d, r8d; MgrEpv
0x18004a303  mov     [rsp+1D8h+MaxCalls], 4D2h; MaxCalls
0x18004a30b  xor     edx, edx; MgrTypeUuid
0x18004a30d  call    cs:__imp_RpcServerRegisterIfEx
0x18004a313  mov     ebx, eax
0x18004a315  test    eax, eax
0x18004a317  jz      short loc_18004A325
0x18004a319  lea     rdx, aErrorDRpcserve_3; "Error %d RpcServerRegisterIf( admin )"
0x18004a320  jmp     loc_18004A292
0x18004a325  xor     ebx, ebx
0x18004a327  mov     rcx, [rsp+1D8h+SecurityDescriptor]; hMem
0x18004a32c  test    rcx, rcx
0x18004a32f  jz      short loc_18004A337
0x18004a331  call    cs:__imp_LocalFree
0x18004a337  mov     eax, ebx
0x18004a339  mov     rcx, [rsp+1D8h+var_18]
0x18004a341  xor     rcx, rsp; StackCookie
0x18004a344  call    __security_check_cookie
0x18004a349  add     rsp, 1D0h
0x18004a350  pop     rbx
0x18004a351  retn
```
