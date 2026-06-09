# CPublicRpc::Start(void)

- ea: `0x180049310`
- end: `0x180049642`
- name: `?Start@CPublicRpc@@UEAAJXZ`
- size: `818`
- prototype: `__int64 __fastcall(CPublicRpc *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800074c0`
- `0x180049310`
- `0x18004b460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800493f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004940b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800493f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004940b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004961b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004961b`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18004943e`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18004943e`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800494ac`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800494f1`
- `RPCRT4!RpcServerRegisterIf3` at `0x180049533`
- `RPCRT4!RpcServerRegisterIf3` at `0x180049574`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800495b6`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800495f7`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800494ac`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800494f1`
- `RPCRT4!RpcServerRegisterIf3` at `0x180049533`
- `RPCRT4!RpcServerRegisterIf3` at `0x180049574`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800495b6`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800495f7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800493e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800493e7`

## string_xrefs

- `0x1800493f7`: `Error %d ConvertStringSecurityDescriptorToSecurityDescriptor`

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
    v20 = RpcServerRegisterIf3(qword_18009EEE0, 0, 0, 9, 1234, 0, CPublicRpc::staticPublicRpcSecurityCallback, 0);
    if ( v20 )
    {
      _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( Pub/Session )", v20);
    }
    else
    {
      v20 = RpcServerRegisterIf3(
              qword_18009DD70,
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
                qword_18009DA40,
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
          v20 = RpcServerRegisterIf3(qword_18009D640, 0, 0, 9, 1234, 0, CPublicRpc::staticPublicRpcSecurityCallback, 0);
          if ( v20 )
          {
            _DbgPrintMessage(8, "Error %d RpcServerRegisterIf( Pub/Notification )", v20);
          }
          else
          {
            v20 = RpcServerRegisterIf3(
                    qword_18009EC20,
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
                      qword_18009D410,
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
0x180049310  push    rbx
0x180049312  push    rbp
0x180049313  push    rsi
0x180049314  push    r14
0x180049316  push    r15
0x180049318  sub     rsp, 1E0h
0x18004931f  mov     rax, cs:__security_cookie
0x180049326  xor     rax, rsp
0x180049329  mov     [rsp+208h+var_38], rax
0x180049331  mov     edx, 2
0x180049336  mov     [rsp+208h+SecurityDescriptor], 0
0x18004933f  lea     rax, [rsp+208h+StringSecurityDescriptor]
0x180049344  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18004934b  lea     ebx, [rdx+7Eh]
0x18004934e  movups  xmm0, xmmword ptr [rcx]
0x180049351  movups  xmm1, xmmword ptr [rcx+10h]
0x180049355  movups  xmmword ptr [rax], xmm0
0x180049358  movups  xmm0, xmmword ptr [rcx+20h]
0x18004935c  movups  xmmword ptr [rax+10h], xmm1
0x180049360  movups  xmm1, xmmword ptr [rcx+30h]
0x180049364  movups  xmmword ptr [rax+20h], xmm0
0x180049368  movups  xmm0, xmmword ptr [rcx+40h]
0x18004936c  movups  xmmword ptr [rax+30h], xmm1
0x180049370  movups  xmm1, xmmword ptr [rcx+50h]
0x180049374  movups  xmmword ptr [rax+40h], xmm0
0x180049378  movups  xmm0, xmmword ptr [rcx+60h]
0x18004937c  movups  xmmword ptr [rax+50h], xmm1
0x180049380  movups  xmm1, xmmword ptr [rcx+70h]
0x180049384  add     rcx, rbx
0x180049387  movups  xmmword ptr [rax+60h], xmm0
0x18004938b  movups  xmmword ptr [rax+70h], xmm1
0x18004938f  add     rax, rbx
0x180049392  sub     rdx, 1
0x180049396  jnz     short loc_18004934E
0x180049398  movups  xmm0, xmmword ptr [rcx]
0x18004939b  xor     r9d, r9d; SecurityDescriptorSize
0x18004939e  lea     r8, [rsp+208h+SecurityDescriptor]; SecurityDescriptor
0x1800493a3  movups  xmm1, xmmword ptr [rcx+10h]
0x1800493a7  movups  xmmword ptr [rax], xmm0
0x1800493aa  lea     edx, [r9+1]; StringSDRevision
0x1800493ae  movups  xmm0, xmmword ptr [rcx+20h]
0x1800493b2  movups  xmmword ptr [rax+10h], xmm1
0x1800493b6  movups  xmm1, xmmword ptr [rcx+30h]
0x1800493ba  movups  xmmword ptr [rax+20h], xmm0
0x1800493be  movups  xmm0, xmmword ptr [rcx+40h]
0x1800493c2  movups  xmmword ptr [rax+30h], xmm1
0x1800493c6  movups  xmm1, xmmword ptr [rcx+50h]
0x1800493ca  movups  xmmword ptr [rax+40h], xmm0
0x1800493ce  movups  xmm0, xmmword ptr [rcx+60h]
0x1800493d2  movups  xmmword ptr [rax+50h], xmm1
0x1800493d6  movups  xmm1, xmmword ptr [rcx+6Ah]
0x1800493da  lea     rcx, [rsp+208h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800493df  movups  xmmword ptr [rax+60h], xmm0
0x1800493e3  movups  xmmword ptr [rax+6Ah], xmm1
0x1800493e7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800493ed  test    eax, eax
0x1800493ef  jnz     short loc_180049429
0x1800493f1  call    cs:__imp_GetLastError
0x1800493f7  lea     rdx, aErrorDConverts; "Error %d ConvertStringSecurityDescripto"...
0x1800493fe  mov     ecx, 8; int
0x180049403  mov     r8d, eax
0x180049406  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004940b  call    cs:__imp_GetLastError
0x180049411  mov     ebx, eax
0x180049413  test    eax, eax
0x180049415  jle     loc_180049611
0x18004941b  movzx   ebx, ax
0x18004941e  or      ebx, 80070000h
0x180049424  jmp     loc_180049611
0x180049429  mov     r9, [rsp+208h+SecurityDescriptor]; SecurityDescriptor
0x18004942e  lea     r8, aLsmapi; "LSMApi"
0x180049435  mov     edx, ebx; MaxCalls
0x180049437  lea     rcx, ProtSeq; "ncalrpc"
0x18004943e  call    cs:__imp_RpcServerUseProtseqEpW
0x180049444  mov     ebx, eax
0x180049446  test    eax, eax
0x180049448  jz      short loc_180049472
0x18004944a  cmp     eax, 6CCh
0x18004944f  jz      short loc_180049472
0x180049451  lea     rdx, aErrorDRpcusepr; "Error %d RpcUseProtseqEp on ncalrpc"
0x180049458  mov     r8d, ebx
0x18004945b  mov     ecx, 8; int
0x180049460  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180049465  test    ebx, ebx
0x180049467  jle     loc_180049611
0x18004946d  movzx   ebx, bx
0x180049470  jmp     short loc_18004941E
0x180049472  mov     [rsp+208h+var_1D0], 0
0x18004947b  lea     r14, ?staticPublicRpcSecurityCallback@CPublicRpc@@CAJPEAX0@Z; CPublicRpc::staticPublicRpcSecurityCallback(void *,void *)
0x180049482  mov     [rsp+208h+var_1D8], r14
0x180049487  lea     rcx, qword_18009EEE0
0x18004948e  mov     ebp, 9
0x180049493  mov     [rsp+208h+var_1E0], 0
0x18004949b  mov     esi, 4D2h
0x1800494a0  mov     r9d, ebp
0x1800494a3  xor     r8d, r8d
0x1800494a6  mov     [rsp+208h+var_1E8], esi
0x1800494aa  xor     edx, edx
0x1800494ac  call    cs:__imp_RpcServerRegisterIf3
0x1800494b2  mov     ebx, eax
0x1800494b4  test    eax, eax
0x1800494b6  jz      short loc_1800494C1
0x1800494b8  lea     rdx, aErrorDRpcserve_6; "Error %d RpcServerRegisterIf( Pub/Sessi"...
0x1800494bf  jmp     short loc_180049458
0x1800494c1  mov     [rsp+208h+var_1D0], 0
0x1800494ca  lea     r15, ?staticPublicLocalOnlyRpcSecurityCallback@CPublicRpc@@CAJPEAX0@Z; CPublicRpc::staticPublicLocalOnlyRpcSecurityCallback(void *,void *)
0x1800494d1  mov     [rsp+208h+var_1D8], r15
0x1800494d6  lea     rcx, qword_18009DD70
0x1800494dd  mov     [rsp+208h+var_1E0], 0
0x1800494e5  mov     r9d, ebp
0x1800494e8  xor     r8d, r8d
0x1800494eb  mov     [rsp+208h+var_1E8], esi
0x1800494ef  xor     edx, edx
0x1800494f1  call    cs:__imp_RpcServerRegisterIf3
0x1800494f7  mov     ebx, eax
0x1800494f9  test    eax, eax
0x1800494fb  jz      short loc_180049509
0x1800494fd  lea     rdx, aErrorDRpcserve_4; "Error %d RpcServerRegisterIf( Pub/Sessi"...
0x180049504  jmp     loc_180049458
0x180049509  mov     rax, [rsp+208h+SecurityDescriptor]
0x18004950e  lea     rcx, qword_18009DA40
0x180049515  mov     [rsp+208h+var_1D0], rax
0x18004951a  mov     r9d, ebp
0x18004951d  mov     [rsp+208h+var_1D8], r15
0x180049522  xor     r8d, r8d
0x180049525  mov     [rsp+208h+var_1E0], 0
0x18004952d  xor     edx, edx
0x18004952f  mov     [rsp+208h+var_1E8], esi
0x180049533  call    cs:__imp_RpcServerRegisterIf3
0x180049539  mov     ebx, eax
0x18004953b  test    eax, eax
0x18004953d  jz      short loc_18004954B
0x18004953f  lea     rdx, aErrorDRpcserve_7; "Error %d RpcServerRegisterIf( Pub/Sessi"...
0x180049546  jmp     loc_180049458
0x18004954b  mov     [rsp+208h+var_1D0], 0
0x180049554  lea     rcx, qword_18009D640
0x18004955b  mov     [rsp+208h+var_1D8], r14
0x180049560  mov     r9d, ebp
0x180049563  mov     [rsp+208h+var_1E0], 0
0x18004956b  xor     r8d, r8d
0x18004956e  xor     edx, edx
0x180049570  mov     [rsp+208h+var_1E8], esi
0x180049574  call    cs:__imp_RpcServerRegisterIf3
0x18004957a  mov     ebx, eax
0x18004957c  test    eax, eax
0x18004957e  jz      short loc_18004958C
0x180049580  lea     rdx, aErrorDRpcserve_1; "Error %d RpcServerRegisterIf( Pub/Notif"...
0x180049587  jmp     loc_180049458
0x18004958c  mov     rax, [rsp+208h+SecurityDescriptor]
0x180049591  lea     rcx, qword_18009EC20
0x180049598  mov     [rsp+208h+var_1D0], rax
0x18004959d  mov     r9d, ebp
0x1800495a0  mov     [rsp+208h+var_1D8], r15
0x1800495a5  xor     r8d, r8d
0x1800495a8  mov     [rsp+208h+var_1E0], 0
0x1800495b0  xor     edx, edx
0x1800495b2  mov     [rsp+208h+var_1E8], esi
0x1800495b6  call    cs:__imp_RpcServerRegisterIf3
0x1800495bc  mov     ebx, eax
0x1800495be  test    eax, eax
0x1800495c0  jz      short loc_1800495CE
0x1800495c2  lea     rdx, aErrorDRpcserve_8; "Error %d RpcServerRegisterIf( Pub/Notif"...
0x1800495c9  jmp     loc_180049458
0x1800495ce  mov     [rsp+208h+var_1D0], 0
0x1800495d7  lea     rcx, qword_18009D410
0x1800495de  mov     [rsp+208h+var_1D8], r14
0x1800495e3  mov     r9d, ebp
0x1800495e6  mov     [rsp+208h+var_1E0], 0
0x1800495ee  xor     r8d, r8d
0x1800495f1  xor     edx, edx
0x1800495f3  mov     [rsp+208h+var_1E8], esi
0x1800495f7  call    cs:__imp_RpcServerRegisterIf3
0x1800495fd  mov     ebx, eax
0x1800495ff  test    eax, eax
0x180049601  jz      short loc_18004960F
0x180049603  lea     rdx, aErrorDRpcserve_0; "Error %d RpcServerRegisterIf( Pub/Enume"...
0x18004960a  jmp     loc_180049458
0x18004960f  xor     ebx, ebx
0x180049611  mov     rcx, [rsp+208h+SecurityDescriptor]; hMem
0x180049616  test    rcx, rcx
0x180049619  jz      short loc_180049621
0x18004961b  call    cs:__imp_LocalFree
0x180049621  mov     eax, ebx
0x180049623  mov     rcx, [rsp+208h+var_38]
0x18004962b  xor     rcx, rsp; StackCookie
0x18004962e  call    __security_check_cookie
0x180049633  add     rsp, 1E0h
0x18004963a  pop     r15
0x18004963c  pop     r14
0x18004963e  pop     rsi
0x18004963f  pop     rbp
0x180049640  pop     rbx
0x180049641  retn
```
