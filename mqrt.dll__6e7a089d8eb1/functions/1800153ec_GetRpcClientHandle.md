# GetRpcClientHandle

- ea: `0x1800153ec`
- end: `0x180015514`
- name: `GetRpcClientHandle`
- size: `296`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015a80`
- `0x180015c30`

## callees

- `0x1800087f8`
- `0x180013c74`
- `0x1800153ec`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x1800154aa`
- `RPCRT4!RpcStringFreeW` at `0x1800154aa`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001549d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18001549d`
- `RPCRT4!RpcStringBindingComposeW` at `0x180015429`
- `RPCRT4!RpcStringBindingComposeW` at `0x180015429`

## string_xrefs

- `0x18001540e`: `Security=Impersonation Dynamic True`

## pseudocode

```c
__int64 __fastcall GetRpcClientHandle(RPC_BINDING_HANDLE *Binding)
{
  int v2; // ebx
  bool v3; // sf
  unsigned __int16 v4; // r8
  bool v6; // sf
  RPC_WSTR StringBinding; // [rsp+48h] [rbp+10h] BYREF

  StringBinding = 0;
  v2 = RpcStringBindingComposeW(
         0,
         (RPC_WSTR)L"ncalrpc",
         0,
         g_pwzQmmgmtEndpoint,
         (RPC_WSTR)L"Security=Impersonation Dynamic True",
         &StringBinding);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        10,
        WPP_74788f79e40038513548c4e45be49262_Traceguids,
        (unsigned int)v2);
    v3 = v2 < 0;
    if ( v2 > 0 )
    {
      v2 = (unsigned __int16)v2 | 0x80070000;
      v3 = v2 < 0;
    }
    if ( !v3 )
      return (unsigned int)v2;
    v4 = 1101;
LABEL_9:
    LogMsgHR(v2, (wchar_t *)L"rt/rtmgmt", v4);
    return (unsigned int)v2;
  }
  v2 = RpcBindingFromStringBindingW(StringBinding, Binding);
  RpcStringFreeW(&StringBinding);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        11,
        WPP_74788f79e40038513548c4e45be49262_Traceguids,
        (unsigned int)v2);
    v6 = v2 < 0;
    if ( v2 > 0 )
    {
      v2 = (unsigned __int16)v2 | 0x80070000;
      v6 = v2 < 0;
    }
    if ( !v6 )
      return (unsigned int)v2;
    v4 = 1102;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x1800153ec  mov     r11, rsp
0x1800153ef  mov     [r11+8], rbx
0x1800153f3  push    rdi
0x1800153f4  sub     rsp, 30h
0x1800153f8  mov     r9, cs:?g_pwzQmmgmtEndpoint@@3V?$AP@_W@@A; Endpoint
0x1800153ff  lea     rax, [r11+10h]
0x180015403  mov     [r11-10h], rax
0x180015407  lea     rdx, ProtSeq; "ncalrpc"
0x18001540e  lea     rax, Options; "Security=Impersonation Dynamic True"
0x180015415  mov     qword ptr [r11+10h], 0
0x18001541d  mov     rdi, rcx
0x180015420  mov     [r11-18h], rax
0x180015424  xor     r8d, r8d; NetworkAddr
0x180015427  xor     ecx, ecx; ObjUuid
0x180015429  call    cs:__imp_RpcStringBindingComposeW
0x18001542f  mov     ebx, eax
0x180015431  test    eax, eax
0x180015433  jz      short loc_180015495
0x180015435  mov     rcx, cs:WPP_GLOBAL_Control
0x18001543c  lea     rax, WPP_GLOBAL_Control
0x180015443  cmp     rcx, rax
0x180015446  jz      short loc_18001546C
0x180015448  test    byte ptr [rcx+0BCh], 1
0x18001544f  jz      short loc_18001546C
0x180015451  mov     rcx, [rcx+0B0h]
0x180015458  lea     r8, WPP_74788f79e40038513548c4e45be49262_Traceguids
0x18001545f  mov     edx, 0Ah
0x180015464  mov     r9d, ebx
0x180015467  call    WPP_SF_d
0x18001546c  test    ebx, ebx
0x18001546e  jle     short loc_18001547B
0x180015470  movzx   ebx, bx
0x180015473  or      ebx, 80070000h
0x180015479  test    ebx, ebx
0x18001547b  jns     short loc_180015491
0x18001547d  mov     r8d, 44Dh; unsigned __int16
0x180015483  lea     rdx, aRtRtmgmt; "rt/rtmgmt"
0x18001548a  mov     ecx, ebx; int
0x18001548c  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180015491  mov     eax, ebx
0x180015493  jmp     short loc_180015509
0x180015495  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x18001549a  mov     rdx, rdi; Binding
0x18001549d  call    cs:__imp_RpcBindingFromStringBindingW
0x1800154a3  lea     rcx, [rsp+38h+StringBinding]; String
0x1800154a8  mov     ebx, eax
0x1800154aa  call    cs:__imp_RpcStringFreeW
0x1800154b0  test    ebx, ebx
0x1800154b2  jz      short loc_180015507
0x1800154b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154bb  lea     rax, WPP_GLOBAL_Control
0x1800154c2  cmp     rcx, rax
0x1800154c5  jz      short loc_1800154EB
0x1800154c7  test    byte ptr [rcx+0BCh], 1
0x1800154ce  jz      short loc_1800154EB
0x1800154d0  mov     rcx, [rcx+0B0h]
0x1800154d7  lea     r8, WPP_74788f79e40038513548c4e45be49262_Traceguids
0x1800154de  mov     edx, 0Bh
0x1800154e3  mov     r9d, ebx
0x1800154e6  call    WPP_SF_d
0x1800154eb  test    ebx, ebx
0x1800154ed  jle     short loc_1800154FA
0x1800154ef  movzx   ebx, bx
0x1800154f2  or      ebx, 80070000h
0x1800154f8  test    ebx, ebx
0x1800154fa  jns     short loc_180015491
0x1800154fc  mov     r8d, 44Eh
0x180015502  jmp     loc_180015483
0x180015507  xor     eax, eax
0x180015509  mov     rbx, [rsp+38h+arg_0]
0x18001550e  add     rsp, 30h
0x180015512  pop     rdi
0x180015513  retn
```
