# CRpcIOManagerServer::VerifyRpcSecuritySchannel(ushort * *,int *,int *,ushort *)

- ea: `0x1800594e0`
- end: `0x18005976a`
- name: `?VerifyRpcSecuritySchannel@CRpcIOManagerServer@@AEAAJPEAPEAGPEAH1PEAG@Z`
- size: `650`
- prototype: `__int64 __fastcall(CRpcIOManagerServer *__hidden this, unsigned __int16 **, int *, int *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005743c`
- `0x180058304`

## callees

- `0x180003cf0`
- `0x180006764`
- `0x18000d5f4`
- `0x180054968`
- `0x1800594e0`
- `0x180070f24`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005975f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005975f`
- `RPCRT4!RpcBindingInqAuthClientExW` at `0x1800595a4`
- `RPCRT4!RpcBindingInqAuthClientExW` at `0x1800595a4`

## string_xrefs

- `0x180059556`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x1800595cb`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180059625`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180059686`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x1800596c6`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180059538`: `CRpcIOManagerServer::VerifyRpcSecuritySchannel (com\complus\dtc\dtc\cm\src\iomgrsrv.cpp@636): pwszHostName != NULL`
- `0x18005954a`: `CRpcIOManagerServer::VerifyRpcSecuritySchannel started.`
- `0x18005955d`: `CRpcIOManagerServer::VerifyRpcSecuritySchannel`
- `0x1800595d6`: `CRpcIOManagerServer::VerifyRpcSecuritySchannel`
- `0x18005962c`: `CRpcIOManagerServer::VerifyRpcSecuritySchannel`
- `0x18005968d`: `CRpcIOManagerServer::VerifyRpcSecuritySchannel`
- `0x1800596cd`: `CRpcIOManagerServer::VerifyRpcSecuritySchannel`
- `0x1800595b9`: `CRpcIOManagerServer::VerifyRpcSecuritySchannel - Received unauthenticated Rpc Call`
- `0x180059674`: `CRpcIOManagerServer::VerifyRpcSecuritySchannel - RpcBindingInqAuthClient call failed`
- `0x1800596b5`: `CRpcIOManagerServer::VerifyRpcSecuritySchannel - RPC_C_AUTHN_GSS_SCHANNEL is expected for authnSvc for Schannel Mutual Authentication`
- `0x180059613`: `CRpcIOManagerServer::VerifyRpcSecuritySchannel completed.`

## pseudocode

```c
__int64 __fastcall CRpcIOManagerServer::VerifyRpcSecuritySchannel(
        CRpcIOManagerServer *this,
        unsigned __int16 **a2,
        int *a3,
        int *a4,
        unsigned __int16 *a5)
{
  RPC_STATUS v8; // ebx
  int v9; // ecx
  int v10; // ebx
  void *v12; // r9
  unsigned int *AuthzSvc; // [rsp+28h] [rbp-49h]
  unsigned int AuthnSvc; // [rsp+50h] [rbp-21h] BYREF
  unsigned int v15; // [rsp+54h] [rbp-1Dh] BYREF
  unsigned int AuthnLevel; // [rsp+58h] [rbp-19h] BYREF
  RPC_AUTHZ_HANDLE Privs; // [rsp+60h] [rbp-11h] BYREF
  LPVOID pv[2]; // [rsp+68h] [rbp-9h] BYREF
  __int64 v19; // [rsp+78h] [rbp+7h]

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  Privs = 0;
  AuthnLevel = 0;
  AuthnSvc = 0;
  v15 = 0;
  if ( !a5 )
    DtcInternalErrorW(
      L"CRpcIOManagerServer::VerifyRpcSecuritySchannel (com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp@636): pwszHostName != NULL");
  TraceStringInline(
    1,
    3,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
    640,
    L"CRpcIOManagerServer::VerifyRpcSecuritySchannel",
    0,
    L"CRpcIOManagerServer::VerifyRpcSecuritySchannel started.");
  v8 = RpcBindingInqAuthClientExW(0, &Privs, 0, &AuthnLevel, &AuthnSvc, &v15, 0);
  if ( v8 == 1746 )
  {
    LODWORD(AuthzSvc) = 1746;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      652,
      L"CRpcIOManagerServer::VerifyRpcSecuritySchannel",
      AuthzSvc,
      L"CRpcIOManagerServer::VerifyRpcSecuritySchannel - Received unauthenticated Rpc Call");
    if ( *(_DWORD *)(*((_QWORD *)this + 11) + 40LL) == 2 )
    {
      v10 = 0;
      *a4 = 1;
      goto LABEL_8;
    }
    v9 = 1746;
  }
  else
  {
    if ( !v8 )
    {
      if ( AuthnSvc != 14 )
      {
        v10 = -2147467259;
        LODWORD(AuthzSvc) = -2147467259;
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
          685,
          L"CRpcIOManagerServer::VerifyRpcSecuritySchannel",
          AuthzSvc,
          L"CRpcIOManagerServer::VerifyRpcSecuritySchannel - RPC_C_AUTHN_GSS_SCHANNEL is expected for authnSvc for Schanne"
           "l Mutual Authentication");
LABEL_15:
        v19 = 0;
        *(_OWORD *)pv = 0;
        MakeStringW((unsigned __int16 **)pv, L"%X", (unsigned int)v10);
        v19 = (__int64)*a2;
        LODWORD(AuthzSvc) = 0;
        pv[1] = a5;
        DtcWriteToEventLoggerExW(2u, 3u, 0x8000130E, v12, 3u, (size_t)AuthzSvc, (const unsigned __int16 **)pv, 0, 1);
        CoTaskMemFree(pv[0]);
        goto LABEL_8;
      }
      v10 = 0;
      *a4 = 1;
      goto LABEL_14;
    }
    LODWORD(AuthzSvc) = v8;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      677,
      L"CRpcIOManagerServer::VerifyRpcSecuritySchannel",
      AuthzSvc,
      L"CRpcIOManagerServer::VerifyRpcSecuritySchannel - RpcBindingInqAuthClient call failed");
    v9 = v8;
  }
  v10 = RpcStatusToHresult(v9);
LABEL_14:
  if ( v10 < 0 )
    goto LABEL_15;
LABEL_8:
  TraceStringInline(
    1,
    3,
    L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
    717,
    L"CRpcIOManagerServer::VerifyRpcSecuritySchannel",
    0,
    L"CRpcIOManagerServer::VerifyRpcSecuritySchannel completed.");
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800594e0  mov     [rsp-8+arg_0], rbx
0x1800594e5  push    rbp
0x1800594e6  push    rsi
0x1800594e7  push    rdi
0x1800594e8  push    r12
0x1800594ea  push    r13
0x1800594ec  push    r14
0x1800594ee  push    r15
0x1800594f0  lea     rbp, [rsp-1Fh]
0x1800594f5  sub     rsp, 90h
0x1800594fc  mov     rax, cs:__security_cookie
0x180059503  xor     rax, rsp
0x180059506  mov     [rbp+4Fh+var_40], rax
0x18005950a  mov     r14, [rbp+4Fh+arg_20]
0x18005950e  xor     r12d, r12d
0x180059511  mov     [rdx], r12
0x180059514  mov     rdi, r9
0x180059517  mov     [r8], r12d
0x18005951a  mov     rsi, rdx
0x18005951d  mov     [r9], r12d
0x180059520  mov     r15, rcx
0x180059523  mov     [rbp+4Fh+Privs], r12
0x180059527  mov     [rbp+4Fh+AuthnLevel], r12d
0x18005952b  mov     [rbp+4Fh+var_70], r12d
0x18005952f  mov     [rbp+4Fh+var_6C], r12d
0x180059533  test    r14, r14
0x180059536  jnz     short loc_180059545
0x180059538  lea     rcx, aCrpciomanagers_15; "CRpcIOManagerServer::VerifyRpcSecurityS"...
0x18005953f  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180059545  mov     edx, 3
0x18005954a  lea     rax, aCrpciomanagers_4; "CRpcIOManagerServer::VerifyRpcSecurityS"...
0x180059551  mov     qword ptr [rsp+0C0h+Flags], rax
0x180059556  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x18005955d  lea     rax, aCrpciomanagers_20; "CRpcIOManagerServer::VerifyRpcSecurityS"...
0x180059564  mov     [rsp+0C0h+AuthzSvc], r12
0x180059569  mov     r9d, 280h
0x18005956f  mov     [rsp+0C0h+AuthnSvc], rax
0x180059574  lea     r13d, [rdx-2]
0x180059578  mov     ecx, r13d
0x18005957b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180059580  lea     rax, [rbp+4Fh+var_6C]
0x180059584  mov     [rsp+0C0h+Flags], r12d; Flags
0x180059589  mov     [rsp+0C0h+AuthzSvc], rax; AuthzSvc
0x18005958e  lea     r9, [rbp+4Fh+AuthnLevel]; AuthnLevel
0x180059592  lea     rax, [rbp+4Fh+var_70]
0x180059596  xor     r8d, r8d; ServerPrincName
0x180059599  lea     rdx, [rbp+4Fh+Privs]; Privs
0x18005959d  mov     [rsp+0C0h+AuthnSvc], rax; AuthnSvc
0x1800595a2  xor     ecx, ecx; ClientBinding
0x1800595a4  call    cs:__imp_RpcBindingInqAuthClientExW
0x1800595aa  mov     ecx, 6D2h
0x1800595af  mov     ebx, eax
0x1800595b1  cmp     eax, ecx
0x1800595b3  jnz     loc_180059670
0x1800595b9  lea     rax, aCrpciomanagers_18; "CRpcIOManagerServer::VerifyRpcSecurityS"...
0x1800595c0  mov     r9d, 28Ch
0x1800595c6  mov     qword ptr [rsp+0C0h+Flags], rax
0x1800595cb  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x1800595d2  mov     dword ptr [rsp+0C0h+AuthzSvc], ecx
0x1800595d6  lea     rax, aCrpciomanagers_20; "CRpcIOManagerServer::VerifyRpcSecurityS"...
0x1800595dd  mov     ecx, r13d
0x1800595e0  mov     [rsp+0C0h+AuthnSvc], rax
0x1800595e5  mov     edx, r13d
0x1800595e8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800595ed  mov     rax, [r15+58h]
0x1800595f1  cmp     dword ptr [rax+28h], 2
0x1800595f5  jz      short loc_180059608
0x1800595f7  mov     ecx, 6D2h; int
0x1800595fc  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x180059601  mov     ebx, eax
0x180059603  jmp     loc_1800596F6
0x180059608  mov     ebx, r12d
0x18005960b  mov     [rdi], r13d
0x18005960e  mov     edi, 3
0x180059613  lea     rax, aCrpciomanagers_6; "CRpcIOManagerServer::VerifyRpcSecurityS"...
0x18005961a  mov     r9d, 2CDh
0x180059620  mov     qword ptr [rsp+0C0h+Flags], rax
0x180059625  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x18005962c  lea     rax, aCrpciomanagers_20; "CRpcIOManagerServer::VerifyRpcSecurityS"...
0x180059633  mov     [rsp+0C0h+AuthzSvc], r12
0x180059638  mov     edx, edi
0x18005963a  mov     [rsp+0C0h+AuthnSvc], rax
0x18005963f  mov     ecx, r13d
0x180059642  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180059647  mov     eax, ebx
0x180059649  mov     rcx, [rbp+4Fh+var_40]
0x18005964d  xor     rcx, rsp; StackCookie
0x180059650  call    __security_check_cookie
0x180059655  mov     rbx, [rsp+0C0h+arg_0]
0x18005965d  add     rsp, 90h
0x180059664  pop     r15
0x180059666  pop     r14
0x180059668  pop     r13
0x18005966a  pop     r12
0x18005966c  pop     rdi
0x18005966d  pop     rsi
0x18005966e  pop     rbp
0x18005966f  retn
0x180059670  test    ebx, ebx
0x180059672  jz      short loc_1800596AF
0x180059674  lea     rax, aCrpciomanagers_9; "CRpcIOManagerServer::VerifyRpcSecurityS"...
0x18005967b  mov     r9d, 2A5h
0x180059681  mov     qword ptr [rsp+0C0h+Flags], rax
0x180059686  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x18005968d  lea     rax, aCrpciomanagers_20; "CRpcIOManagerServer::VerifyRpcSecurityS"...
0x180059694  mov     dword ptr [rsp+0C0h+AuthzSvc], ebx
0x180059698  mov     edx, r13d
0x18005969b  mov     [rsp+0C0h+AuthnSvc], rax
0x1800596a0  mov     ecx, r13d
0x1800596a3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800596a8  mov     ecx, ebx
0x1800596aa  jmp     loc_1800595FC
0x1800596af  cmp     [rbp+4Fh+var_70], 0Eh
0x1800596b3  jz      short loc_1800596F0
0x1800596b5  lea     rax, aCrpciomanagers_13; "CRpcIOManagerServer::VerifyRpcSecurityS"...
0x1800596bc  mov     ebx, 80004005h
0x1800596c1  mov     qword ptr [rsp+0C0h+Flags], rax
0x1800596c6  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x1800596cd  lea     rax, aCrpciomanagers_20; "CRpcIOManagerServer::VerifyRpcSecurityS"...
0x1800596d4  mov     dword ptr [rsp+0C0h+AuthzSvc], ebx
0x1800596d8  mov     r9d, 2ADh
0x1800596de  mov     [rsp+0C0h+AuthnSvc], rax
0x1800596e3  mov     edx, r13d
0x1800596e6  mov     ecx, r13d
0x1800596e9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800596ee  jmp     short loc_1800596FE
0x1800596f0  mov     ebx, r12d
0x1800596f3  mov     [rdi], r13d
0x1800596f6  test    ebx, ebx
0x1800596f8  jns     loc_18005960E
0x1800596fe  xorps   xmm0, xmm0
0x180059701  lea     rdx, asc_1800B060C; "%X"
0x180059708  xor     eax, eax
0x18005970a  lea     rcx, [rbp+4Fh+pv]; unsigned __int16 **
0x18005970e  mov     r8d, ebx
0x180059711  mov     [rbp+4Fh+var_48], rax
0x180059715  movups  xmmword ptr [rbp+4Fh+pv], xmm0
0x180059719  call    ?MakeStringW@@YAJPEAPEAGPEBGZZ; MakeStringW(ushort * *,ushort const *,...)
0x18005971e  mov     rax, [rsi]
0x180059721  mov     edi, 3
0x180059726  mov     [rsp+0C0h+var_80], r13d; int
0x18005972b  mov     edx, edi; unsigned __int16
0x18005972d  mov     [rsp+0C0h+Src], r12; Src
0x180059732  mov     r8d, 8000130Eh; unsigned int
0x180059738  mov     [rbp+4Fh+var_48], rax
0x18005973c  lea     rax, [rbp+4Fh+pv]
0x180059740  mov     qword ptr [rsp+0C0h+Flags], rax; unsigned __int16 **
0x180059745  lea     ecx, [rdi-1]; unsigned __int16
0x180059748  mov     dword ptr [rsp+0C0h+AuthzSvc], r12d; Size
0x18005974d  mov     word ptr [rsp+0C0h+AuthnSvc], di; unsigned __int16
0x180059752  mov     [rbp+4Fh+pv+8], r14
0x180059756  call    ?DtcWriteToEventLoggerExW@@YAJGGKPEAXGKPEAPEBG0H@Z; DtcWriteToEventLoggerExW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)
0x18005975b  mov     rcx, [rbp+4Fh+pv]; pv
0x18005975f  call    cs:__imp_CoTaskMemFree
0x180059765  jmp     loc_180059613
```
