# MQMgmtGetInfo

- ea: `0x180015c30`
- end: `0x180015e02`
- name: `MQMgmtGetInfo`
- size: `466`
- prototype: `HRESULT __stdcall(LPCWSTR pComputerName, LPCWSTR pObjectName, MQMGMTPROPS *pMgmtProps)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180013c74`
- `0x180014458`
- `0x1800153ec`
- `0x1800155e0`
- `0x1800156b4`
- `0x18001593c`
- `0x180015c30`
- `0x180017ce0`
- `0x180023c5a`

## import_xrefs

- `msvcrt!free` at `0x180015cc7`
- `msvcrt!free` at `0x180015d90`
- `msvcrt!free` at `0x180015dd8`
- `msvcrt!free` at `0x180015dec`
- `msvcrt!free` at `0x180015cc7`
- `msvcrt!free` at `0x180015d90`
- `msvcrt!free` at `0x180015dd8`
- `msvcrt!free` at `0x180015dec`
- `RPCRT4!RpcBindingFree` at `0x180015d46`
- `RPCRT4!RpcBindingFree` at `0x180015d46`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HRESULT __stdcall MQMgmtGetInfo(LPCWSTR pComputerName, LPCWSTR pObjectName, MQMGMTPROPS *pMgmtProps)
{
  int v6; // eax
  HRESULT v7; // ebx
  int v9; // eax
  __int64 i; // rdx
  int RpcClientHandle; // eax
  int v12; // ebx
  unsigned __int16 v13; // r8
  int v14; // ecx
  int v15; // eax
  int Info; // eax
  int v17; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-68h] BYREF
  _OWORD v19[6]; // [rsp+28h] [rbp-60h] BYREF
  void *Block; // [rsp+A8h] [rbp+20h] BYREF

  v6 = RtpOneTimeThreadInit();
  v7 = v6;
  if ( v6 < 0 )
  {
    LogMsgHR(v6, (wchar_t *)L"rt/rtmgmt", 0x46Du);
    return v7;
  }
  memset(v19, 0, 48);
  Block = 0;
  try
  {
    v9 = RTpMgmtObjectNameToMgmtObject((wchar_t *)pObjectName, (wchar_t **)&Block);
  }
  catch ( exception )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_74788f79e40038513548c4e45be49262_Traceguids);
    LogMsgHR(-1072824281, (wchar_t *)L"rt/rtmgmt", 0x46Eu);
    free(Block);
    return -1072824281;
  }
  if ( v9 )
  {
    memset_0(pMgmtProps->aPropVar, 0, 24LL * pMgmtProps->cProp);
    for ( i = 0; (unsigned int)i < pMgmtProps->cProp; i = (unsigned int)(i + 1) )
      pMgmtProps->aPropVar[i].vt = 1;
    if ( pComputerName )
    {
      Info = RemoteMgmtGetInfo(pComputerName, (__int64)v19, (__int64)pMgmtProps);
      v17 = RTpConvertToMQCode(Info, 1u);
      v7 = v17;
      if ( v17 < 0 )
        LogMsgHR(v17, (wchar_t *)L"rt/rtmgmt", 0xC8u);
      free(Block);
      return v7;
    }
    Binding = 0;
    RpcClientHandle = GetRpcClientHandle(&Binding);
    v12 = RpcClientHandle;
    if ( RpcClientHandle >= 0 )
    {
      v12 = RTpMgmtGetInfo(Binding, v19, pMgmtProps);
      RpcBindingFree(&Binding);
      if ( v12 >= 0 )
      {
LABEL_15:
        v15 = RTpConvertToMQCode(v12, 1u);
        v7 = v15;
        if ( v15 < 0 )
          LogMsgHR(v15, (wchar_t *)L"rt/rtmgmt", 0xBEu);
        free(Block);
        return v7;
      }
      v13 = 160;
      v14 = v12;
    }
    else
    {
      v13 = 150;
      v14 = RpcClientHandle;
    }
    LogMsgHR(v14, (wchar_t *)L"rt/rtmgmt", v13);
    goto LABEL_15;
  }
  LogMsgHR(-1072824290, (wchar_t *)L"rt/rtmgmt", 0xB4u);
  free(Block);
  return -1072824290;
}

```

## disassembly

```asm
0x180015c30  push    rbx
0x180015c32  push    rsi
0x180015c33  push    rdi
0x180015c34  push    r14
0x180015c36  sub     rsp, 68h
0x180015c3a  mov     rdi, r8
0x180015c3d  mov     rsi, rdx
0x180015c40  mov     r14, rcx
0x180015c43  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x180015c48  mov     ebx, eax
0x180015c4a  test    eax, eax
0x180015c4c  jns     short loc_180015C69
0x180015c4e  mov     r8d, 46Dh; unsigned __int16
0x180015c54  lea     rdx, aRtRtmgmt; "rt/rtmgmt"
0x180015c5b  mov     ecx, eax; int
0x180015c5d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180015c62  mov     eax, ebx
0x180015c64  jmp     loc_180015DF8
0x180015c69  xorps   xmm0, xmm0
0x180015c6c  movups  [rsp+88h+var_50], xmm0
0x180015c71  movups  [rsp+88h+var_40], xmm0
0x180015c76  movups  [rsp+88h+var_60], xmm0
0x180015c7b  mov     [rsp+88h+Block], 0
0x180015c87  lea     r9, [rsp+88h+var_50]
0x180015c8c  lea     r8, [rsp+88h+var_60]
0x180015c91  lea     rdx, [rsp+88h+Block]; wchar_t **
0x180015c99  mov     rcx, rsi; String1
0x180015c9c  call    RTpMgmtObjectNameToMgmtObject
0x180015ca1  test    eax, eax
0x180015ca3  jnz     short loc_180015CD5
0x180015ca5  mov     r8d, 0B4h; unsigned __int16
0x180015cab  lea     rdx, aRtRtmgmt; "rt/rtmgmt"
0x180015cb2  mov     ebx, 0C00E001Eh
0x180015cb7  mov     ecx, ebx; int
0x180015cb9  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180015cbe  nop
0x180015cbf  mov     rcx, [rsp+88h+Block]; Block
0x180015cc7  call    cs:__imp_free
0x180015ccd  nop
0x180015cce  mov     eax, ebx
0x180015cd0  jmp     loc_180015DF8
0x180015cd5  mov     eax, [rdi]
0x180015cd7  lea     r8, [rax+rax*2]
0x180015cdb  shl     r8, 3; Size
0x180015cdf  xor     edx, edx; Val
0x180015ce1  mov     rcx, [rdi+10h]; void *
0x180015ce5  call    memset_0
0x180015cea  xor     edx, edx
0x180015cec  lea     esi, [rdx+1]
0x180015cef  cmp     [rdi], edx
0x180015cf1  jbe     short loc_180015D05
0x180015cf3  lea     rcx, [rdx+rdx*2]
0x180015cf7  mov     rax, [rdi+10h]
0x180015cfb  mov     [rax+rcx*8], si
0x180015cff  add     edx, esi
0x180015d01  cmp     edx, [rdi]
0x180015d03  jb      short loc_180015CF3
0x180015d05  test    r14, r14
0x180015d08  jnz     loc_180015D9C
0x180015d0e  mov     [rsp+88h+Binding], r14
0x180015d13  lea     rcx, [rsp+88h+Binding]; Binding
0x180015d18  call    GetRpcClientHandle
0x180015d1d  mov     ebx, eax
0x180015d1f  test    eax, eax
0x180015d21  jns     short loc_180015D2D
0x180015d23  mov     r8d, 96h
0x180015d29  mov     ecx, eax
0x180015d2b  jmp     short loc_180015D58
0x180015d2d  mov     r8, rdi
0x180015d30  lea     rdx, [rsp+88h+var_60]
0x180015d35  mov     rcx, [rsp+88h+Binding]
0x180015d3a  call    RTpMgmtGetInfo
0x180015d3f  mov     ebx, eax
0x180015d41  lea     rcx, [rsp+88h+Binding]; Binding
0x180015d46  call    cs:__imp_RpcBindingFree
0x180015d4c  test    ebx, ebx
0x180015d4e  jns     short loc_180015D64
0x180015d50  mov     r8d, 0A0h; unsigned __int16
0x180015d56  mov     ecx, ebx; int
0x180015d58  lea     rdx, aRtRtmgmt; "rt/rtmgmt"
0x180015d5f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180015d64  mov     edx, esi; unsigned int
0x180015d66  mov     ecx, ebx; int
0x180015d68  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x180015d6d  mov     ebx, eax
0x180015d6f  test    eax, eax
0x180015d71  jns     short loc_180015D88
0x180015d73  mov     r8d, 0BEh; unsigned __int16
0x180015d79  lea     rdx, aRtRtmgmt; "rt/rtmgmt"
0x180015d80  mov     ecx, eax; int
0x180015d82  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180015d87  nop
0x180015d88  mov     rcx, [rsp+88h+Block]; Block
0x180015d90  call    cs:__imp_free
0x180015d96  nop
0x180015d97  jmp     loc_180015C62
0x180015d9c  mov     r8, rdi
0x180015d9f  lea     rdx, [rsp+88h+var_60]
0x180015da4  mov     rcx, r14
0x180015da7  call    RemoteMgmtGetInfo
0x180015dac  mov     edx, esi; unsigned int
0x180015dae  mov     ecx, eax; int
0x180015db0  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x180015db5  mov     ebx, eax
0x180015db7  test    eax, eax
0x180015db9  jns     short loc_180015DD0
0x180015dbb  mov     r8d, 0C8h; unsigned __int16
0x180015dc1  lea     rdx, aRtRtmgmt; "rt/rtmgmt"
0x180015dc8  mov     ecx, eax; int
0x180015dca  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180015dcf  nop
0x180015dd0  mov     rcx, [rsp+88h+Block]; Block
0x180015dd8  call    cs:__imp_free
0x180015dde  nop
0x180015ddf  jmp     loc_180015C62
0x180015de4  mov     rcx, [rsp+88h+Block]; Block
0x180015dec  call    cs:__imp_free
0x180015df2  nop
0x180015df3  mov     eax, 0C00E0027h
0x180015df8  add     rsp, 68h
0x180015dfc  pop     r14
0x180015dfe  pop     rdi
0x180015dff  pop     rsi
0x180015e00  pop     rbx
0x180015e01  retn
```
