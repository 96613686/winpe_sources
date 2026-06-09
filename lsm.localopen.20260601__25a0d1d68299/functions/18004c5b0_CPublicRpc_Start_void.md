# CPublicRpc::Start(void)

- ea: `0x18004c5b0`
- end: `0x18004c925`
- name: `?Start@CPublicRpc@@UEAAJXZ`
- size: `885`
- prototype: `__int64 __fastcall(CPublicRpc *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800077a0`
- `0x18004c5b0`
- `0x18004e850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c697`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c6b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c697`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c6b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c8f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c8f7`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18004c6f0`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18004c6f0`
- `RPCRT4!RpcServerRegisterIf3` at `0x18004c764`
- `RPCRT4!RpcServerRegisterIf3` at `0x18004c7af`
- `RPCRT4!RpcServerRegisterIf3` at `0x18004c7f7`
- `RPCRT4!RpcServerRegisterIf3` at `0x18004c83e`
- `RPCRT4!RpcServerRegisterIf3` at `0x18004c886`
- `RPCRT4!RpcServerRegisterIf3` at `0x18004c8cd`
- `RPCRT4!RpcServerRegisterIf3` at `0x18004c764`
- `RPCRT4!RpcServerRegisterIf3` at `0x18004c7af`
- `RPCRT4!RpcServerRegisterIf3` at `0x18004c7f7`
- `RPCRT4!RpcServerRegisterIf3` at `0x18004c83e`
- `RPCRT4!RpcServerRegisterIf3` at `0x18004c886`
- `RPCRT4!RpcServerRegisterIf3` at `0x18004c8cd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004c687`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004c687`

## string_xrefs

- `0x18004c6a3`: `Error %d ConvertStringSecurityDescriptorToSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall CPublicRpc::Start(CPublicRpc *this)
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
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-1C8h] BYREF
  WCHAR StringSecurityDescriptor[192]; // [rsp+50h] [rbp-1B8h] BYREF

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
      goto LABEL_25;
    v20 = (unsigned __int16)v19;
    goto LABEL_6;
  }
  v21 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0x80u, (RPC_WSTR)L"LSMApi", SecurityDescriptor);
  v20 = v21;
  if ( !v21 || v21 == 1740 )
  {
    v20 = RpcServerRegisterIf3(qword_1800A3E30, 0, 0, 9, 1234, 0, CPublicRpc::staticPublicRpcSecurityCallback, 0);
    if ( v20 )
    {
      _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( Pub/Session )", v20);
    }
    else
    {
      v20 = RpcServerRegisterIf3(
              qword_1800A2D30,
              0,
              0,
              9,
              1234,
              0,
              CPublicRpc::staticPublicLocalOnlyRpcSecurityCallback,
              0);
      if ( v20 )
      {
        _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( Pub/Session/LocalOnly )", v20);
      }
      else
      {
        v20 = RpcServerRegisterIf3(
                qword_1800A2A80,
                0,
                0,
                9,
                1234,
                0,
                CPublicRpc::staticPublicLocalOnlyRpcSecurityCallback,
                SecurityDescriptor);
        if ( v20 )
        {
          _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( Pub/SessionAppContainer )", v20);
        }
        else
        {
          v20 = RpcServerRegisterIf3(qword_1800A2600, 0, 0, 9, 1234, 0, CPublicRpc::staticPublicRpcSecurityCallback, 0);
          if ( v20 )
          {
            _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( Pub/Notification )", v20);
          }
          else
          {
            v20 = RpcServerRegisterIf3(
                    qword_1800A3C10,
                    0,
                    0,
                    9,
                    1234,
                    0,
                    CPublicRpc::staticPublicLocalOnlyRpcSecurityCallback,
                    SecurityDescriptor);
            if ( v20 )
            {
              _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( Pub/NotificationAppContainer )", v20);
            }
            else
            {
              v20 = RpcServerRegisterIf3(
                      qword_1800A23C0,
                      0,
                      0,
                      9,
                      1234,
                      0,
                      CPublicRpc::staticPublicRpcSecurityCallback,
                      0);
              if ( !v20 )
              {
                v20 = 0;
                goto LABEL_25;
              }
              _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( Pub/Enumeration )", v20);
            }
          }
        }
      }
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
LABEL_25:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v20;
}

```

## disassembly

```asm
0x18004c5b0  push    rbx
0x18004c5b2  push    rbp
0x18004c5b3  push    rsi
0x18004c5b4  push    r14
0x18004c5b6  push    r15
0x18004c5b8  sub     rsp, 1E0h
0x18004c5bf  mov     rax, cs:__security_cookie
0x18004c5c6  xor     rax, rsp
0x18004c5c9  mov     [rsp+208h+var_38], rax
0x18004c5d1  mov     edx, 2
0x18004c5d6  mov     [rsp+208h+SecurityDescriptor], 0
0x18004c5df  lea     rax, [rsp+208h+StringSecurityDescriptor]
0x18004c5e4  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18004c5eb  lea     ebx, [rdx+7Eh]
0x18004c5ee  movups  xmm0, xmmword ptr [rcx]
0x18004c5f1  movups  xmm1, xmmword ptr [rcx+10h]
0x18004c5f5  movups  xmmword ptr [rax], xmm0
0x18004c5f8  movups  xmm0, xmmword ptr [rcx+20h]
0x18004c5fc  movups  xmmword ptr [rax+10h], xmm1
0x18004c600  movups  xmm1, xmmword ptr [rcx+30h]
0x18004c604  movups  xmmword ptr [rax+20h], xmm0
0x18004c608  movups  xmm0, xmmword ptr [rcx+40h]
0x18004c60c  movups  xmmword ptr [rax+30h], xmm1
0x18004c610  movups  xmm1, xmmword ptr [rcx+50h]
0x18004c614  movups  xmmword ptr [rax+40h], xmm0
0x18004c618  movups  xmm0, xmmword ptr [rcx+60h]
0x18004c61c  movups  xmmword ptr [rax+50h], xmm1
0x18004c620  movups  xmm1, xmmword ptr [rcx+70h]
0x18004c624  add     rcx, rbx
0x18004c627  movups  xmmword ptr [rax+60h], xmm0
0x18004c62b  movups  xmmword ptr [rax+70h], xmm1
0x18004c62f  add     rax, rbx
0x18004c632  sub     rdx, 1
0x18004c636  jnz     short loc_18004C5EE
0x18004c638  movups  xmm0, xmmword ptr [rcx]
0x18004c63b  xor     r9d, r9d; SecurityDescriptorSize
0x18004c63e  lea     r8, [rsp+208h+SecurityDescriptor]; SecurityDescriptor
0x18004c643  movups  xmm1, xmmword ptr [rcx+10h]
0x18004c647  movups  xmmword ptr [rax], xmm0
0x18004c64a  lea     edx, [r9+1]; StringSDRevision
0x18004c64e  movups  xmm0, xmmword ptr [rcx+20h]
0x18004c652  movups  xmmword ptr [rax+10h], xmm1
0x18004c656  movups  xmm1, xmmword ptr [rcx+30h]
0x18004c65a  movups  xmmword ptr [rax+20h], xmm0
0x18004c65e  movups  xmm0, xmmword ptr [rcx+40h]
0x18004c662  movups  xmmword ptr [rax+30h], xmm1
0x18004c666  movups  xmm1, xmmword ptr [rcx+50h]
0x18004c66a  movups  xmmword ptr [rax+40h], xmm0
0x18004c66e  movups  xmm0, xmmword ptr [rcx+60h]
0x18004c672  movups  xmmword ptr [rax+50h], xmm1
0x18004c676  movups  xmm1, xmmword ptr [rcx+6Ah]
0x18004c67a  lea     rcx, [rsp+208h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18004c67f  movups  xmmword ptr [rax+60h], xmm0
0x18004c683  movups  xmmword ptr [rax+6Ah], xmm1
0x18004c687  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004c68e  nop     dword ptr [rax+rax+00h]
0x18004c693  test    eax, eax
0x18004c695  jnz     short loc_18004C6DB
0x18004c697  call    cs:__imp_GetLastError
0x18004c69e  nop     dword ptr [rax+rax+00h]
0x18004c6a3  lea     rdx, aErrorDConverts; "Error %d ConvertStringSecurityDescripto"...
0x18004c6aa  mov     ecx, 8; int
0x18004c6af  mov     r8d, eax
0x18004c6b2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004c6b7  call    cs:__imp_GetLastError
0x18004c6be  nop     dword ptr [rax+rax+00h]
0x18004c6c3  mov     ebx, eax
0x18004c6c5  test    eax, eax
0x18004c6c7  jle     loc_18004C8ED
0x18004c6cd  movzx   ebx, ax
0x18004c6d0  or      ebx, 80070000h
0x18004c6d6  jmp     loc_18004C8ED
0x18004c6db  mov     r9, [rsp+208h+SecurityDescriptor]; SecurityDescriptor
0x18004c6e0  lea     r8, aLsmapi; "LSMApi"
0x18004c6e7  mov     edx, ebx; MaxCalls
0x18004c6e9  lea     rcx, ProtSeq; "ncalrpc"
0x18004c6f0  call    cs:__imp_RpcServerUseProtseqEpW
0x18004c6f7  nop     dword ptr [rax+rax+00h]
0x18004c6fc  mov     ebx, eax
0x18004c6fe  test    eax, eax
0x18004c700  jz      short loc_18004C72A
0x18004c702  cmp     eax, 6CCh
0x18004c707  jz      short loc_18004C72A
0x18004c709  lea     rdx, aErrorDRpcusepr; "Error %d RpcUseProtseqEp on ncalrpc"
0x18004c710  mov     r8d, ebx
0x18004c713  mov     ecx, 8; int
0x18004c718  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004c71d  test    ebx, ebx
0x18004c71f  jle     loc_18004C8ED
0x18004c725  movzx   ebx, bx
0x18004c728  jmp     short loc_18004C6D0
0x18004c72a  mov     [rsp+208h+var_1D0], 0
0x18004c733  lea     r14, ?staticPublicRpcSecurityCallback@CPublicRpc@@CAJPEAX0@Z; CPublicRpc::staticPublicRpcSecurityCallback(void *,void *)
0x18004c73a  mov     [rsp+208h+var_1D8], r14
0x18004c73f  lea     rcx, qword_1800A3E30
0x18004c746  mov     ebp, 9
0x18004c74b  mov     [rsp+208h+var_1E0], 0
0x18004c753  mov     esi, 4D2h
0x18004c758  mov     r9d, ebp
0x18004c75b  xor     r8d, r8d
0x18004c75e  mov     [rsp+208h+var_1E8], esi
0x18004c762  xor     edx, edx
0x18004c764  call    cs:__imp_RpcServerRegisterIf3
0x18004c76b  nop     dword ptr [rax+rax+00h]
0x18004c770  mov     ebx, eax
0x18004c772  test    eax, eax
0x18004c774  jz      short loc_18004C77F
0x18004c776  lea     rdx, aErrorDRpcserve_6; "Error %d RpcServerRegisterIf( Pub/Sessi"...
0x18004c77d  jmp     short loc_18004C710
0x18004c77f  mov     [rsp+208h+var_1D0], 0
0x18004c788  lea     r15, ?staticPublicLocalOnlyRpcSecurityCallback@CPublicRpc@@CAJPEAX0@Z; CPublicRpc::staticPublicLocalOnlyRpcSecurityCallback(void *,void *)
0x18004c78f  mov     [rsp+208h+var_1D8], r15
0x18004c794  lea     rcx, qword_1800A2D30
0x18004c79b  mov     [rsp+208h+var_1E0], 0
0x18004c7a3  mov     r9d, ebp
0x18004c7a6  xor     r8d, r8d
0x18004c7a9  mov     [rsp+208h+var_1E8], esi
0x18004c7ad  xor     edx, edx
0x18004c7af  call    cs:__imp_RpcServerRegisterIf3
0x18004c7b6  nop     dword ptr [rax+rax+00h]
0x18004c7bb  mov     ebx, eax
0x18004c7bd  test    eax, eax
0x18004c7bf  jz      short loc_18004C7CD
0x18004c7c1  lea     rdx, aErrorDRpcserve_4; "Error %d RpcServerRegisterIf( Pub/Sessi"...
0x18004c7c8  jmp     loc_18004C710
0x18004c7cd  mov     rax, [rsp+208h+SecurityDescriptor]
0x18004c7d2  lea     rcx, qword_1800A2A80
0x18004c7d9  mov     [rsp+208h+var_1D0], rax
0x18004c7de  mov     r9d, ebp
0x18004c7e1  mov     [rsp+208h+var_1D8], r15
0x18004c7e6  xor     r8d, r8d
0x18004c7e9  mov     [rsp+208h+var_1E0], 0
0x18004c7f1  xor     edx, edx
0x18004c7f3  mov     [rsp+208h+var_1E8], esi
0x18004c7f7  call    cs:__imp_RpcServerRegisterIf3
0x18004c7fe  nop     dword ptr [rax+rax+00h]
0x18004c803  mov     ebx, eax
0x18004c805  test    eax, eax
0x18004c807  jz      short loc_18004C815
0x18004c809  lea     rdx, aErrorDRpcserve_7; "Error %d RpcServerRegisterIf( Pub/Sessi"...
0x18004c810  jmp     loc_18004C710
0x18004c815  mov     [rsp+208h+var_1D0], 0
0x18004c81e  lea     rcx, qword_1800A2600
0x18004c825  mov     [rsp+208h+var_1D8], r14
0x18004c82a  mov     r9d, ebp
0x18004c82d  mov     [rsp+208h+var_1E0], 0
0x18004c835  xor     r8d, r8d
0x18004c838  xor     edx, edx
0x18004c83a  mov     [rsp+208h+var_1E8], esi
0x18004c83e  call    cs:__imp_RpcServerRegisterIf3
0x18004c845  nop     dword ptr [rax+rax+00h]
0x18004c84a  mov     ebx, eax
0x18004c84c  test    eax, eax
0x18004c84e  jz      short loc_18004C85C
0x18004c850  lea     rdx, aErrorDRpcserve_1; "Error %d RpcServerRegisterIf( Pub/Notif"...
0x18004c857  jmp     loc_18004C710
0x18004c85c  mov     rax, [rsp+208h+SecurityDescriptor]
0x18004c861  lea     rcx, qword_1800A3C10
0x18004c868  mov     [rsp+208h+var_1D0], rax
0x18004c86d  mov     r9d, ebp
0x18004c870  mov     [rsp+208h+var_1D8], r15
0x18004c875  xor     r8d, r8d
0x18004c878  mov     [rsp+208h+var_1E0], 0
0x18004c880  xor     edx, edx
0x18004c882  mov     [rsp+208h+var_1E8], esi
0x18004c886  call    cs:__imp_RpcServerRegisterIf3
0x18004c88d  nop     dword ptr [rax+rax+00h]
0x18004c892  mov     ebx, eax
0x18004c894  test    eax, eax
0x18004c896  jz      short loc_18004C8A4
0x18004c898  lea     rdx, aErrorDRpcserve_8; "Error %d RpcServerRegisterIf( Pub/Notif"...
0x18004c89f  jmp     loc_18004C710
0x18004c8a4  mov     [rsp+208h+var_1D0], 0
0x18004c8ad  lea     rcx, qword_1800A23C0
0x18004c8b4  mov     [rsp+208h+var_1D8], r14
0x18004c8b9  mov     r9d, ebp
0x18004c8bc  mov     [rsp+208h+var_1E0], 0
0x18004c8c4  xor     r8d, r8d
0x18004c8c7  xor     edx, edx
0x18004c8c9  mov     [rsp+208h+var_1E8], esi
0x18004c8cd  call    cs:__imp_RpcServerRegisterIf3
0x18004c8d4  nop     dword ptr [rax+rax+00h]
0x18004c8d9  mov     ebx, eax
0x18004c8db  test    eax, eax
0x18004c8dd  jz      short loc_18004C8EB
0x18004c8df  lea     rdx, aErrorDRpcserve_0; "Error %d RpcServerRegisterIf( Pub/Enume"...
0x18004c8e6  jmp     loc_18004C710
0x18004c8eb  xor     ebx, ebx
0x18004c8ed  mov     rcx, [rsp+208h+SecurityDescriptor]; hMem
0x18004c8f2  test    rcx, rcx
0x18004c8f5  jz      short loc_18004C903
0x18004c8f7  call    cs:__imp_LocalFree
0x18004c8fe  nop     dword ptr [rax+rax+00h]
0x18004c903  mov     eax, ebx
0x18004c905  mov     rcx, [rsp+208h+var_38]
0x18004c90d  xor     rcx, rsp; StackCookie
0x18004c910  call    __security_check_cookie
0x18004c915  add     rsp, 1E0h
0x18004c91c  pop     r15
0x18004c91e  pop     r14
0x18004c920  pop     rsi
0x18004c921  pop     rbp
0x18004c922  pop     rbx
0x18004c923  retn
```
