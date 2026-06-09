# CRpcIOManagerServer::RegisterProtocolSequences(ulong,ulong)

- ea: `0x180011c38`
- end: `0x180011fa2`
- name: `?RegisterProtocolSequences@CRpcIOManagerServer@@QEAAJKK@Z`
- size: `874`
- prototype: `__int64 __fastcall(CRpcIOManagerServer *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019f80`

## callees

- `0x180003cf0`
- `0x180011c38`
- `0x180019908`
- `0x18002f534`
- `0x180054968`
- `0x180081dd0`

## import_xrefs

- `RPCRT4!RpcServerUseProtseqEpA` at `0x180011f15`
- `RPCRT4!RpcServerUseProtseqEpA` at `0x180011f15`
- `RPCRT4!RpcServerUseProtseqA` at `0x180011c82`
- `RPCRT4!RpcServerUseProtseqA` at `0x180011d57`
- `RPCRT4!RpcServerUseProtseqA` at `0x180011d87`
- `RPCRT4!RpcServerUseProtseqA` at `0x180011c82`
- `RPCRT4!RpcServerUseProtseqA` at `0x180011d57`
- `RPCRT4!RpcServerUseProtseqA` at `0x180011d87`

## string_xrefs

- `0x180011cbc`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180011dcd`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180011e57`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180011e8c`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180011cdd`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180011d39`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180011dff`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180011eb8`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180011caa`: `MSDTC was unable to register the LRPC protocol.`
- `0x180011c8f`: `CRpcIOManagerServer::RegisterProtocolSequences`
- `0x180011de6`: `CRpcIOManagerServer::RegisterProtocolSequences`
- `0x180011e5e`: `CRpcIOManagerServer::RegisterProtocolSequences`
- `0x180011e93`: `CRpcIOManagerServer::RegisterProtocolSequences`
- `0x180011dd4`: `Invalid port(%s) specified in the registry`
- `0x180011e45`: `MSDTC was unable to register the TCP protocol.`
- `0x180011e80`: `The server port used is %d (0 implies default RPC dynamic port is used). If "ServerTcpPort" is configured, verify if the configured server TCP port is valid and is not already in use by a different component`

## pseudocode

```c
__int64 __fastcall CRpcIOManagerServer::RegisterProtocolSequences(CRpcIOManagerServer *this, int a2, int a3)
{
  RPC_STATUS v7; // eax
  int v8; // edi
  unsigned int v9; // ebp
  RPC_STATUS v10; // eax
  int v11; // eax
  RPC_STATUS v12; // eax
  __int64 v13; // [rsp+28h] [rbp-70h]
  __int64 v14; // [rsp+28h] [rbp-70h]
  void *v15; // [rsp+38h] [rbp-60h]
  void *v16; // [rsp+50h] [rbp-48h]
  char Endpoint[8]; // [rsp+60h] [rbp-38h] BYREF

  if ( a2 && (a2 & 0xFFFFFFD6) != 0 )
    return 2147484019LL;
  v7 = RpcServerUseProtseqA((RPC_CSTR)"ncalrpc", *((_DWORD *)this + 14), 0);
  v8 = RpcStatusToHresult(v7);
  if ( v8 )
  {
    LODWORD(v13) = v8;
    v9 = v8;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      2677,
      L"CRpcIOManagerServer::RegisterProtocolSequences",
      v13,
      L"MSDTC was unable to register the LRPC protocol.");
    DELLog(
      *(struct ITmInstance **)(*((_QWORD *)this + 11) + 64LL),
      1u,
      0xAu,
      0xC0001106,
      v8,
      1,
      0,
      0,
      "com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      2680,
      v16);
  }
  else
  {
    v9 = 0;
    *((_DWORD *)this + 20) |= 0x20u;
  }
  if ( !a2 || (a2 & 1) != 0 )
  {
    if ( dword_1800D715C )
    {
      *((_DWORD *)this + 20) |= 1u;
      goto LABEL_11;
    }
    if ( a3 )
    {
      v8 = StringCchPrintfA(Endpoint, 7u, "%d", a3);
      if ( v8 < 0 )
      {
        LODWORD(v13) = v8;
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
          2715,
          L"CRpcIOManagerServer::RegisterProtocolSequences",
          v13,
          L"Invalid port(%s) specified in the registry",
          Endpoint);
        DELLog(
          *(struct ITmInstance **)(*((_QWORD *)this + 11) + 64LL),
          1u,
          0xAu,
          0xC0001106,
          v8,
          1,
          0,
          0,
          "com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
          2718,
          v16);
LABEL_19:
        LODWORD(v13) = v8;
        v9 = v8;
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
          2743,
          L"CRpcIOManagerServer::RegisterProtocolSequences",
          v13,
          L"MSDTC was unable to register the TCP protocol.");
        LODWORD(v15) = a3;
        LODWORD(v14) = v8;
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
          2746,
          L"CRpcIOManagerServer::RegisterProtocolSequences",
          v14,
          L"The server port used is %d (0 implies default RPC dynamic port is used). If \"ServerTcpPort\" is configured, v"
           "erify if the configured server TCP port is valid and is not already in use by a different component",
          v15);
        DELLog(
          *(struct ITmInstance **)(*((_QWORD *)this + 11) + 64LL),
          1u,
          0xAu,
          0xC0001106,
          v8,
          1,
          0,
          0,
          "com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
          2749,
          v16);
        goto LABEL_11;
      }
      v12 = RpcServerUseProtseqEpA((RPC_CSTR)"ncacn_ip_tcp", *((_DWORD *)this + 14), (RPC_CSTR)Endpoint, 0);
    }
    else
    {
      v12 = RpcServerUseProtseqA((RPC_CSTR)"ncacn_ip_tcp", *((_DWORD *)this + 14), 0);
      if ( v8 < 0 )
        goto LABEL_22;
    }
    v8 = RpcStatusToHresult(v12);
LABEL_22:
    if ( !v8 )
    {
      *((_DWORD *)this + 20) |= 1u;
      dword_1800D715C = 1;
      goto LABEL_11;
    }
    goto LABEL_19;
  }
LABEL_11:
  if ( (a2 & 8) != 0 )
  {
    v10 = RpcServerUseProtseqA((RPC_CSTR)"ncacn_ip_udp", *((_DWORD *)this + 14), 0);
    v11 = RpcStatusToHresult(v10);
    if ( v11 )
      DELLog(
        *(struct ITmInstance **)(*((_QWORD *)this + 11) + 64LL),
        2u,
        0xAu,
        0xC0001106,
        v11,
        1,
        0,
        0,
        "com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
        2772,
        v16);
    else
      *((_DWORD *)this + 20) |= 8u;
  }
  return v9;
}

```

## disassembly

```asm
0x180011c38  mov     [rsp+arg_8], rbx
0x180011c3d  push    rbp
0x180011c3e  push    rsi
0x180011c3f  push    rdi
0x180011c40  push    r12
0x180011c42  push    r14
0x180011c44  sub     rsp, 70h
0x180011c48  mov     rax, cs:__security_cookie
0x180011c4f  xor     rax, rsp
0x180011c52  mov     [rsp+98h+var_30], rax
0x180011c57  mov     r14d, r8d
0x180011c5a  mov     esi, edx
0x180011c5c  mov     rbx, rcx
0x180011c5f  test    edx, edx
0x180011c61  jz      short loc_180011C75
0x180011c63  test    edx, 0FFFFFFD6h
0x180011c69  jz      short loc_180011C75
0x180011c6b  mov     eax, 80000173h
0x180011c70  jmp     loc_180011F81
0x180011c75  mov     edx, [rcx+38h]; MaxCalls
0x180011c78  xor     r8d, r8d; SecurityDescriptor
0x180011c7b  lea     rcx, Protseq; "ncalrpc"
0x180011c82  call    cs:__imp_RpcServerUseProtseqA
0x180011c88  mov     ecx, eax; int
0x180011c8a  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x180011c8f  lea     rcx, aCrpciomanagers_24; "CRpcIOManagerServer::RegisterProtocolSe"...
0x180011c96  mov     edi, eax
0x180011c98  mov     r12d, 1
0x180011c9e  test    eax, eax
0x180011ca0  jnz     short loc_180011CAA
0x180011ca2  xor     ebp, ebp
0x180011ca4  or      dword ptr [rbx+50h], 20h
0x180011ca8  jmp     short loc_180011D23
0x180011caa  lea     rax, aMsdtcWasUnable; "MSDTC was unable to register the LRPC p"...
0x180011cb1  mov     r9d, 0A75h
0x180011cb7  mov     qword ptr [rsp+98h+var_68], rax
0x180011cbc  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180011cc3  mov     dword ptr [rsp+98h+var_70], edi
0x180011cc7  mov     edx, r12d
0x180011cca  mov     qword ptr [rsp+98h+var_78], rcx
0x180011ccf  mov     ebp, edi
0x180011cd1  mov     ecx, r12d
0x180011cd4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011cd9  mov     rcx, [rbx+58h]
0x180011cdd  lea     rax, aComComplusDtcD_42; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180011ce4  mov     [rsp+98h+var_50], 0A78h; int
0x180011cec  mov     r8d, 0Ah; unsigned __int16
0x180011cf2  mov     [rsp+98h+var_58], rax; char *
0x180011cf7  mov     edx, r12d; unsigned __int16
0x180011cfa  mov     [rsp+98h+var_60], 0; void *
0x180011d03  mov     r9d, 0C0001106h; unsigned int
0x180011d09  mov     rcx, [rcx+40h]; struct ITmInstance *
0x180011d0d  mov     [rsp+98h+var_68], 0; unsigned int
0x180011d15  mov     dword ptr [rsp+98h+var_70], r12d; int
0x180011d1a  mov     [rsp+98h+var_78], edi; int
0x180011d1e  call    ?DELLog@@YAXPEAUITmInstance@@GGKJHKPEAXPEADH1@Z; DELLog(ITmInstance *,ushort,ushort,ulong,long,int,ulong,void *,char *,int,void *)
0x180011d23  test    esi, esi
0x180011d25  jz      short loc_180011D2C
0x180011d27  test    r12b, sil
0x180011d2a  jz      short loc_180011D39
0x180011d2c  cmp     cs:dword_1800D715C, 0
0x180011d33  jz      short loc_180011D75
0x180011d35  or      [rbx+50h], r12d
0x180011d39  lea     r14, aComComplusDtcD_42; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180011d40  test    sil, 8
0x180011d44  jz      loc_180011F7F
0x180011d4a  mov     edx, [rbx+38h]; MaxCalls
0x180011d4d  lea     rcx, aNcacnIpUdp; "ncacn_ip_udp"
0x180011d54  xor     r8d, r8d; SecurityDescriptor
0x180011d57  call    cs:__imp_RpcServerUseProtseqA
0x180011d5d  mov     ecx, eax; int
0x180011d5f  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x180011d64  test    eax, eax
0x180011d66  jnz     loc_180011F3C
0x180011d6c  or      dword ptr [rbx+50h], 8
0x180011d70  jmp     loc_180011F7F
0x180011d75  test    r14d, r14d
0x180011d78  jnz     short loc_180011D9A
0x180011d7a  mov     edx, [rbx+38h]; MaxCalls
0x180011d7d  lea     rcx, aNcacnIpTcp; "ncacn_ip_tcp"
0x180011d84  xor     r8d, r8d; SecurityDescriptor
0x180011d87  call    cs:__imp_RpcServerUseProtseqA
0x180011d8d  test    edi, edi
0x180011d8f  js      loc_180011F24
0x180011d95  jmp     loc_180011F1B
0x180011d9a  mov     r9d, r14d
0x180011d9d  lea     r8, aD; "%d"
0x180011da4  mov     edx, 7; unsigned __int64
0x180011da9  lea     rcx, [rsp+98h+Endpoint]; char *
0x180011dae  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180011db3  mov     edi, eax
0x180011db5  test    eax, eax
0x180011db7  jns     loc_180011F03
0x180011dbd  lea     rax, [rsp+98h+Endpoint]
0x180011dc2  mov     r9d, 0A9Bh
0x180011dc8  mov     [rsp+98h+var_60], rax
0x180011dcd  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180011dd4  lea     rax, aInvalidPortSSp; "Invalid port(%s) specified in the regis"...
0x180011ddb  mov     edx, r12d
0x180011dde  mov     qword ptr [rsp+98h+var_68], rax
0x180011de3  mov     ecx, r12d
0x180011de6  lea     rax, aCrpciomanagers_24; "CRpcIOManagerServer::RegisterProtocolSe"...
0x180011ded  mov     dword ptr [rsp+98h+var_70], edi
0x180011df1  mov     qword ptr [rsp+98h+var_78], rax
0x180011df6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011dfb  mov     rcx, [rbx+58h]
0x180011dff  lea     rax, aComComplusDtcD_42; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180011e06  mov     [rsp+98h+var_50], 0A9Eh; int
0x180011e0e  mov     r8d, 0Ah; unsigned __int16
0x180011e14  mov     [rsp+98h+var_58], rax; char *
0x180011e19  mov     edx, r12d; unsigned __int16
0x180011e1c  mov     [rsp+98h+var_60], 0; void *
0x180011e25  mov     r9d, 0C0001106h; unsigned int
0x180011e2b  mov     rcx, [rcx+40h]; struct ITmInstance *
0x180011e2f  mov     [rsp+98h+var_68], 0; unsigned int
0x180011e37  mov     dword ptr [rsp+98h+var_70], r12d; int
0x180011e3c  mov     [rsp+98h+var_78], edi; int
0x180011e40  call    ?DELLog@@YAXPEAUITmInstance@@GGKJHKPEAXPEADH1@Z; DELLog(ITmInstance *,ushort,ushort,ulong,long,int,ulong,void *,char *,int,void *)
0x180011e45  lea     rax, aMsdtcWasUnable_0; "MSDTC was unable to register the TCP pr"...
0x180011e4c  mov     r9d, 0AB7h
0x180011e52  mov     qword ptr [rsp+98h+var_68], rax
0x180011e57  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180011e5e  lea     rax, aCrpciomanagers_24; "CRpcIOManagerServer::RegisterProtocolSe"...
0x180011e65  mov     dword ptr [rsp+98h+var_70], edi
0x180011e69  mov     edx, r12d
0x180011e6c  mov     qword ptr [rsp+98h+var_78], rax
0x180011e71  mov     ecx, r12d
0x180011e74  mov     ebp, edi
0x180011e76  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011e7b  mov     dword ptr [rsp+98h+var_60], r14d
0x180011e80  lea     rax, aTheServerPortU; "The server port used is %d (0 implies d"...
0x180011e87  mov     qword ptr [rsp+98h+var_68], rax
0x180011e8c  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180011e93  lea     rax, aCrpciomanagers_24; "CRpcIOManagerServer::RegisterProtocolSe"...
0x180011e9a  mov     dword ptr [rsp+98h+var_70], edi
0x180011e9e  mov     r9d, 0ABAh
0x180011ea4  mov     qword ptr [rsp+98h+var_78], rax
0x180011ea9  mov     edx, r12d
0x180011eac  mov     ecx, r12d
0x180011eaf  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180011eb4  mov     rcx, [rbx+58h]
0x180011eb8  lea     r14, aComComplusDtcD_42; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x180011ebf  mov     [rsp+98h+var_50], 0ABDh; int
0x180011ec7  mov     r8d, 0Ah; unsigned __int16
0x180011ecd  mov     [rsp+98h+var_58], r14; char *
0x180011ed2  mov     edx, r12d; unsigned __int16
0x180011ed5  mov     [rsp+98h+var_60], 0; void *
0x180011ede  mov     r9d, 0C0001106h; unsigned int
0x180011ee4  mov     rcx, [rcx+40h]; struct ITmInstance *
0x180011ee8  mov     [rsp+98h+var_68], 0; unsigned int
0x180011ef0  mov     dword ptr [rsp+98h+var_70], r12d; int
0x180011ef5  mov     [rsp+98h+var_78], edi; int
0x180011ef9  call    ?DELLog@@YAXPEAUITmInstance@@GGKJHKPEAXPEADH1@Z; DELLog(ITmInstance *,ushort,ushort,ulong,long,int,ulong,void *,char *,int,void *)
0x180011efe  jmp     loc_180011D40
0x180011f03  mov     edx, [rbx+38h]; MaxCalls
0x180011f06  lea     r8, [rsp+98h+Endpoint]; Endpoint
0x180011f0b  xor     r9d, r9d; SecurityDescriptor
0x180011f0e  lea     rcx, aNcacnIpTcp; "ncacn_ip_tcp"
0x180011f15  call    cs:__imp_RpcServerUseProtseqEpA
0x180011f1b  mov     ecx, eax; int
0x180011f1d  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x180011f22  mov     edi, eax
0x180011f24  test    edi, edi
0x180011f26  jnz     loc_180011E45
0x180011f2c  or      [rbx+50h], r12d
0x180011f30  mov     cs:dword_1800D715C, r12d
0x180011f37  jmp     loc_180011D39
0x180011f3c  mov     rcx, [rbx+58h]
0x180011f40  mov     edx, 2; unsigned __int16
0x180011f45  mov     [rsp+98h+var_50], 0AD4h; int
0x180011f4d  mov     r9d, 0C0001106h; unsigned int
0x180011f53  mov     [rsp+98h+var_58], r14; char *
0x180011f58  mov     [rsp+98h+var_60], 0; void *
0x180011f61  mov     rcx, [rcx+40h]; struct ITmInstance *
0x180011f65  lea     r8d, [rdx+8]; unsigned __int16
0x180011f69  mov     [rsp+98h+var_68], 0; unsigned int
0x180011f71  mov     dword ptr [rsp+98h+var_70], r12d; int
0x180011f76  mov     [rsp+98h+var_78], eax; int
0x180011f7a  call    ?DELLog@@YAXPEAUITmInstance@@GGKJHKPEAXPEADH1@Z; DELLog(ITmInstance *,ushort,ushort,ulong,long,int,ulong,void *,char *,int,void *)
0x180011f7f  mov     eax, ebp
0x180011f81  mov     rcx, [rsp+98h+var_30]
0x180011f86  xor     rcx, rsp; StackCookie
0x180011f89  call    __security_check_cookie
0x180011f8e  mov     rbx, [rsp+98h+arg_8]
0x180011f96  add     rsp, 70h
0x180011f9a  pop     r14
0x180011f9c  pop     r12
0x180011f9e  pop     rdi
0x180011f9f  pop     rsi
0x180011fa0  pop     rbp
0x180011fa1  retn
```
