# MQMgmtAction

- ea: `0x180015a80`
- end: `0x180015c24`
- name: `MQMgmtAction`
- size: `420`
- prototype: `HRESULT __stdcall(LPCWSTR pComputerName, LPCWSTR pObjectName, LPCWSTR pAction)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180013c74`
- `0x180014458`
- `0x1800153ec`
- `0x18001551c`
- `0x1800156b4`
- `0x1800157f8`
- `0x180015a80`
- `0x180017ce0`

## import_xrefs

- `msvcrt!free` at `0x180015b15`
- `msvcrt!free` at `0x180015baf`
- `msvcrt!free` at `0x180015bfa`
- `msvcrt!free` at `0x180015c0e`
- `msvcrt!free` at `0x180015b15`
- `msvcrt!free` at `0x180015baf`
- `msvcrt!free` at `0x180015bfa`
- `msvcrt!free` at `0x180015c0e`
- `RPCRT4!RpcBindingFree` at `0x180015b62`
- `RPCRT4!RpcBindingFree` at `0x180015b62`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HRESULT __stdcall MQMgmtAction(LPCWSTR pComputerName, LPCWSTR pObjectName, LPCWSTR pAction)
{
  int v6; // eax
  HRESULT v7; // ebx
  int v9; // eax
  int RpcClientHandle; // eax
  int v11; // ebx
  unsigned __int16 v12; // r8
  int v13; // ecx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-68h] BYREF
  _OWORD v18[6]; // [rsp+28h] [rbp-60h] BYREF
  void *Block; // [rsp+A8h] [rbp+20h] BYREF

  v6 = RtpOneTimeThreadInit();
  v7 = v6;
  if ( v6 < 0 )
  {
    LogMsgHR(v6, (wchar_t *)L"rt/rtmgmt", 0x454u);
    return v7;
  }
  memset(v18, 0, 48);
  Block = 0;
  try
  {
    v9 = RTpMgmtObjectNameToMgmtObject((wchar_t *)pObjectName, (wchar_t **)&Block);
  }
  catch ( exception )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_74788f79e40038513548c4e45be49262_Traceguids);
    LogMsgHR(-1072824281, (wchar_t *)L"rt/rtmgmt", 0x68Eu);
    free(Block);
    return -1072824281;
  }
  if ( v9 )
  {
    if ( pComputerName )
    {
      v15 = RemoteMgmtAction(pComputerName, (const struct _MGMT_OBJECT *)v18, pAction);
      v16 = RTpConvertToMQCode(v15, 1u);
      v7 = v16;
      if ( v16 < 0 )
        LogMsgHR(v16, (wchar_t *)L"rt/rtmgmt", 0x6Eu);
      free(Block);
      return v7;
    }
    Binding = 0;
    RpcClientHandle = GetRpcClientHandle(&Binding);
    v11 = RpcClientHandle;
    if ( RpcClientHandle >= 0 )
    {
      v11 = RTpMgmtAction(Binding, v18, pAction);
      RpcBindingFree(&Binding);
      if ( v11 >= 0 )
      {
LABEL_13:
        v14 = RTpConvertToMQCode(v11, 1u);
        v7 = v14;
        if ( v14 < 0 )
          LogMsgHR(v14, (wchar_t *)L"rt/rtmgmt", 0x64u);
        free(Block);
        return v7;
      }
      v12 = 70;
      v13 = v11;
    }
    else
    {
      v12 = 60;
      v13 = RpcClientHandle;
    }
    LogMsgHR(v13, (wchar_t *)L"rt/rtmgmt", v12);
    goto LABEL_13;
  }
  LogMsgHR(-1072824290, (wchar_t *)L"rt/rtmgmt", 0x5Au);
  free(Block);
  return -1072824290;
}

```

## disassembly

```asm
0x180015a80  push    rbx
0x180015a82  push    rsi
0x180015a83  push    rdi
0x180015a84  push    r14
0x180015a86  sub     rsp, 68h
0x180015a8a  mov     rsi, r8
0x180015a8d  mov     r14, rdx
0x180015a90  mov     rdi, rcx
0x180015a93  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x180015a98  mov     ebx, eax
0x180015a9a  test    eax, eax
0x180015a9c  jns     short loc_180015AB9
0x180015a9e  mov     r8d, 454h; unsigned __int16
0x180015aa4  lea     rdx, aRtRtmgmt; "rt/rtmgmt"
0x180015aab  mov     ecx, eax; int
0x180015aad  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180015ab2  mov     eax, ebx
0x180015ab4  jmp     loc_180015C1A
0x180015ab9  xorps   xmm0, xmm0
0x180015abc  movups  [rsp+88h+var_50], xmm0
0x180015ac1  movups  [rsp+88h+var_40], xmm0
0x180015ac6  movups  [rsp+88h+var_60], xmm0
0x180015acb  mov     [rsp+88h+Block], 0
0x180015ad7  lea     r9, [rsp+88h+var_50]
0x180015adc  lea     r8, [rsp+88h+var_60]
0x180015ae1  lea     rdx, [rsp+88h+Block]; wchar_t **
0x180015ae9  mov     rcx, r14; String1
0x180015aec  call    RTpMgmtObjectNameToMgmtObject
0x180015af1  test    eax, eax
0x180015af3  jnz     short loc_180015B23
0x180015af5  lea     r8d, [rax+5Ah]; unsigned __int16
0x180015af9  lea     rdx, aRtRtmgmt; "rt/rtmgmt"
0x180015b00  mov     ebx, 0C00E001Eh
0x180015b05  mov     ecx, ebx; int
0x180015b07  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180015b0c  nop
0x180015b0d  mov     rcx, [rsp+88h+Block]; Block
0x180015b15  call    cs:__imp_free
0x180015b1b  nop
0x180015b1c  mov     eax, ebx
0x180015b1e  jmp     loc_180015C1A
0x180015b23  test    rdi, rdi
0x180015b26  jnz     loc_180015BBB
0x180015b2c  mov     [rsp+88h+Binding], rdi
0x180015b31  lea     rcx, [rsp+88h+Binding]; Binding
0x180015b36  call    GetRpcClientHandle
0x180015b3b  mov     ebx, eax
0x180015b3d  test    eax, eax
0x180015b3f  jns     short loc_180015B49
0x180015b41  lea     r8d, [rdi+3Ch]
0x180015b45  mov     ecx, eax
0x180015b47  jmp     short loc_180015B74
0x180015b49  mov     r8, rsi
0x180015b4c  lea     rdx, [rsp+88h+var_60]
0x180015b51  mov     rcx, [rsp+88h+Binding]
0x180015b56  call    RTpMgmtAction
0x180015b5b  mov     ebx, eax
0x180015b5d  lea     rcx, [rsp+88h+Binding]; Binding
0x180015b62  call    cs:__imp_RpcBindingFree
0x180015b68  test    ebx, ebx
0x180015b6a  jns     short loc_180015B80
0x180015b6c  mov     r8d, 46h ; 'F'; unsigned __int16
0x180015b72  mov     ecx, ebx; int
0x180015b74  lea     rdx, aRtRtmgmt; "rt/rtmgmt"
0x180015b7b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180015b80  mov     edx, 1; unsigned int
0x180015b85  mov     ecx, ebx; int
0x180015b87  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x180015b8c  mov     ebx, eax
0x180015b8e  test    eax, eax
0x180015b90  jns     short loc_180015BA7
0x180015b92  mov     r8d, 64h ; 'd'; unsigned __int16
0x180015b98  lea     rdx, aRtRtmgmt; "rt/rtmgmt"
0x180015b9f  mov     ecx, eax; int
0x180015ba1  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180015ba6  nop
0x180015ba7  mov     rcx, [rsp+88h+Block]; Block
0x180015baf  call    cs:__imp_free
0x180015bb5  nop
0x180015bb6  jmp     loc_180015AB2
0x180015bbb  mov     r8, rsi; wchar_t *
0x180015bbe  lea     rdx, [rsp+88h+var_60]; struct _MGMT_OBJECT *
0x180015bc3  mov     rcx, rdi; wchar_t *
0x180015bc6  call    ?RemoteMgmtAction@@YAJPEB_WPEBU_MGMT_OBJECT@@0@Z; RemoteMgmtAction(wchar_t const *,_MGMT_OBJECT const *,wchar_t const *)
0x180015bcb  mov     edx, 1; unsigned int
0x180015bd0  mov     ecx, eax; int
0x180015bd2  call    ?RTpConvertToMQCode@@YAJJK@Z; RTpConvertToMQCode(long,ulong)
0x180015bd7  mov     ebx, eax
0x180015bd9  test    eax, eax
0x180015bdb  jns     short loc_180015BF2
0x180015bdd  mov     r8d, 6Eh ; 'n'; unsigned __int16
0x180015be3  lea     rdx, aRtRtmgmt; "rt/rtmgmt"
0x180015bea  mov     ecx, eax; int
0x180015bec  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180015bf1  nop
0x180015bf2  mov     rcx, [rsp+88h+Block]; Block
0x180015bfa  call    cs:__imp_free
0x180015c00  nop
0x180015c01  jmp     loc_180015AB2
0x180015c06  mov     rcx, [rsp+88h+Block]; Block
0x180015c0e  call    cs:__imp_free
0x180015c14  nop
0x180015c15  mov     eax, 0C00E0027h
0x180015c1a  add     rsp, 68h
0x180015c1e  pop     r14
0x180015c20  pop     rdi
0x180015c21  pop     rsi
0x180015c22  pop     rbx
0x180015c23  retn
```
