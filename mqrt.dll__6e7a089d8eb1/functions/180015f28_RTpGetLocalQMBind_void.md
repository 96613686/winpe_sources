# RTpGetLocalQMBind(void)

- ea: `0x180015f28`
- end: `0x1800160dd`
- name: `?RTpGetLocalQMBind@@YAPEAXXZ`
- size: `437`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800140e4`

## callees

- `0x1800022d6`
- `0x1800087f8`
- `0x1800093d0`
- `0x180013dc8`
- `0x180015f28`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x180015fe8`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180015fe8`
- `RPCRT4!RpcStringBindingComposeW` at `0x180015f6e`
- `RPCRT4!RpcStringBindingComposeW` at `0x180015f6e`
- `mqsec!MQSec_SetLocalRpcMutualAuth` at `0x180016053`
- `mqsec!MQSec_SetLocalRpcMutualAuth` at `0x180016053`
- `mqsec!mqrpcUnbindQMService` at `0x1800160a4`
- `mqsec!mqrpcUnbindQMService` at `0x1800160a4`

## string_xrefs

- `0x180015f5f`: `Security=Impersonation Dynamic True`

## pseudocode

```c
RPC_BINDING_HANDLE RTpGetLocalQMBind(void)
{
  unsigned __int16 *v0; // rcx
  unsigned int v1; // eax
  wchar_t *v2; // rdx
  unsigned int v3; // ebx
  unsigned int v4; // eax
  wchar_t *v5; // rdx
  unsigned int v6; // ebx
  unsigned int v7; // eax
  wchar_t *v8; // rdx
  unsigned int v9; // ebx
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-20h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp+10h] BYREF

  v0 = g_pszStringBinding;
  if ( !g_pszStringBinding )
  {
    v1 = RpcStringBindingComposeW(
           0,
           (RPC_WSTR)L"ncalrpc",
           0,
           g_pwzQmsvcEndpoint,
           (RPC_WSTR)L"Security=Impersonation Dynamic True",
           &g_pszStringBinding);
    v3 = v1;
    if ( v1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b7214267925a383e3cf1d9b04fd0d288_Traceguids, v1);
      LogMsgRPCStatus(v3, v2, 0x4B1u);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v3);
      throw (bad_win32_error *)pExceptionObject;
    }
    v0 = g_pszStringBinding;
  }
  Binding = 0;
  v4 = RpcBindingFromStringBindingW(v0, &Binding);
  v6 = v4;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b7214267925a383e3cf1d9b04fd0d288_Traceguids, v4);
    LogMsgRPCStatus(v6, v5, 0x4B2u);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v6);
    throw (bad_win32_error *)pExceptionObject;
  }
  v7 = MQSec_SetLocalRpcMutualAuth(&Binding);
  v9 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b7214267925a383e3cf1d9b04fd0d288_Traceguids, v7);
    LogMsgRPCStatus(v9, v8, 0x4B3u);
    mqrpcUnbindQMService(&Binding, 0);
    Binding = 0;
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v9);
    throw (bad_win32_error *)pExceptionObject;
  }
  return Binding;
}

```

## disassembly

```asm
0x180015f28  mov     [rsp-8+arg_8], rbx
0x180015f2d  push    rbp
0x180015f2e  mov     rbp, rsp
0x180015f31  sub     rsp, 50h
0x180015f35  mov     rcx, cs:?g_pszStringBinding@@3PEA_WEA; ObjUuid
0x180015f3c  test    rcx, rcx
0x180015f3f  jnz     loc_180015FDC
0x180015f45  mov     r9, cs:?g_pwzQmsvcEndpoint@@3V?$AP@_W@@A; Endpoint
0x180015f4c  lea     rax, ?g_pszStringBinding@@3PEA_WEA; wchar_t * g_pszStringBinding
0x180015f53  mov     [rsp+50h+StringBinding], rax; StringBinding
0x180015f58  lea     rdx, ProtSeq; "ncalrpc"
0x180015f5f  lea     rax, Options; "Security=Impersonation Dynamic True"
0x180015f66  xor     r8d, r8d; NetworkAddr
0x180015f69  mov     [rsp+50h+Options], rax; Options
0x180015f6e  call    cs:__imp_RpcStringBindingComposeW
0x180015f74  mov     ebx, eax
0x180015f76  test    eax, eax
0x180015f78  jz      short loc_180015FD5
0x180015f7a  mov     r10, cs:WPP_GLOBAL_Control
0x180015f81  lea     rcx, WPP_GLOBAL_Control
0x180015f88  cmp     r10, rcx
0x180015f8b  jz      short loc_180015FAC
0x180015f8d  test    byte ptr [r10+1Ch], 1
0x180015f92  jz      short loc_180015FAC
0x180015f94  mov     rcx, [r10+10h]
0x180015f98  lea     r8, WPP_b7214267925a383e3cf1d9b04fd0d288_Traceguids
0x180015f9f  mov     edx, 0Ah
0x180015fa4  mov     r9d, eax
0x180015fa7  call    WPP_SF_d
0x180015fac  mov     r8d, 4B1h; unsigned __int16
0x180015fb2  mov     ecx, ebx; int
0x180015fb4  call    ?LogMsgRPCStatus@@YAXJPEA_WG@Z; LogMsgRPCStatus(long,wchar_t *,ushort)
0x180015fb9  mov     edx, ebx; unsigned int
0x180015fbb  lea     rcx, [rbp+pExceptionObject]; this
0x180015fbf  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180015fc4  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180015fcb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180015fcf  call    _CxxThrowException_0
0x180015fd5  mov     rcx, cs:?g_pszStringBinding@@3PEA_WEA; StringBinding
0x180015fdc  lea     rdx, [rbp+Binding]; Binding
0x180015fe0  mov     [rbp+Binding], 0
0x180015fe8  call    cs:__imp_RpcBindingFromStringBindingW
0x180015fee  mov     ebx, eax
0x180015ff0  test    eax, eax
0x180015ff2  jz      short loc_18001604F
0x180015ff4  mov     r10, cs:WPP_GLOBAL_Control
0x180015ffb  lea     rcx, WPP_GLOBAL_Control
0x180016002  cmp     r10, rcx
0x180016005  jz      short loc_180016026
0x180016007  test    byte ptr [r10+1Ch], 1
0x18001600c  jz      short loc_180016026
0x18001600e  mov     rcx, [r10+10h]
0x180016012  lea     r8, WPP_b7214267925a383e3cf1d9b04fd0d288_Traceguids
0x180016019  mov     edx, 0Bh
0x18001601e  mov     r9d, eax
0x180016021  call    WPP_SF_d
0x180016026  mov     r8d, 4B2h; unsigned __int16
0x18001602c  mov     ecx, ebx; int
0x18001602e  call    ?LogMsgRPCStatus@@YAXJPEA_WG@Z; LogMsgRPCStatus(long,wchar_t *,ushort)
0x180016033  mov     edx, ebx; unsigned int
0x180016035  lea     rcx, [rbp+pExceptionObject]; this
0x180016039  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18001603e  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x180016045  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180016049  call    _CxxThrowException_0
0x18001604f  lea     rcx, [rbp+Binding]
0x180016053  call    cs:__imp_?MQSec_SetLocalRpcMutualAuth@@YAJPEAPEAX@Z; MQSec_SetLocalRpcMutualAuth(void * *)
0x180016059  mov     ebx, eax
0x18001605b  test    eax, eax
0x18001605d  jz      short loc_1800160CE
0x18001605f  mov     r10, cs:WPP_GLOBAL_Control
0x180016066  lea     rcx, WPP_GLOBAL_Control
0x18001606d  cmp     r10, rcx
0x180016070  jz      short loc_180016091
0x180016072  test    byte ptr [r10+1Ch], 1
0x180016077  jz      short loc_180016091
0x180016079  mov     rcx, [r10+10h]
0x18001607d  lea     r8, WPP_b7214267925a383e3cf1d9b04fd0d288_Traceguids
0x180016084  mov     edx, 0Ch
0x180016089  mov     r9d, eax
0x18001608c  call    WPP_SF_d
0x180016091  mov     r8d, 4B3h; unsigned __int16
0x180016097  mov     ecx, ebx; int
0x180016099  call    ?LogMsgRPCStatus@@YAXJPEA_WG@Z; LogMsgRPCStatus(long,wchar_t *,ushort)
0x18001609e  xor     edx, edx
0x1800160a0  lea     rcx, [rbp+Binding]
0x1800160a4  call    cs:__imp_?mqrpcUnbindQMService@@YAJPEAPEAXPEAPEA_W@Z; mqrpcUnbindQMService(void * *,wchar_t * *)
0x1800160aa  mov     edx, ebx; unsigned int
0x1800160ac  mov     [rbp+Binding], 0
0x1800160b4  lea     rcx, [rbp+pExceptionObject]; this
0x1800160b8  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800160bd  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x1800160c4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800160c8  call    _CxxThrowException_0
0x1800160ce  mov     rax, [rbp+Binding]
0x1800160d2  mov     rbx, [rsp+50h+arg_8]
0x1800160d7  add     rsp, 50h
0x1800160db  pop     rbp
0x1800160dc  retn
```
