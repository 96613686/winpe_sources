# FwGetRpcCallersProcessInfo

- ea: `0x1800039f0`
- end: `0x180003b22`
- name: `FwGetRpcCallersProcessInfo`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180001da0`

## callees

- `0x1800039f0`
- `0x180003b30`
- `0x18000ccd4`
- `0x180017d1c`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180003a0e`
- `RPCRT4!RpcImpersonateClient` at `0x180003a0e`
- `RPCRT4!RpcRevertToSelf` at `0x180003a2b`
- `RPCRT4!RpcRevertToSelf` at `0x180003a2b`

## pseudocode

```c
__int64 __fastcall FwGetRpcCallersProcessInfo(void *a1, __int64 a2)
{
  RPC_STATUS v4; // eax
  unsigned int v5; // esi
  int RpcClientInfo; // eax
  unsigned int v7; // ebx
  _QWORD *v9; // rcx

  if ( a2 )
  {
    v4 = RpcImpersonateClient(a1);
    v5 = v4;
    if ( !v4 )
      goto LABEL_3;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids, v5);
      return v5;
    }
    else
    {
LABEL_3:
      RpcClientInfo = FwQueryRpcClientInfo(a1, a2);
      v7 = RpcClientInfo;
      if ( RpcClientInfo < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids,
          (unsigned int)RpcClientInfo);
      }
      RpcRevertToSelf();
      return v7;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
        WPP_SF_d(v9[2], 18, WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids, 2147942487LL);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800039f0  mov     [rsp+arg_8], rbx
0x1800039f5  push    rdi
0x1800039f6  sub     rsp, 20h
0x1800039fa  mov     rbx, rdx
0x1800039fd  mov     rdi, rcx
0x180003a00  test    rdx, rdx
0x180003a03  jz      loc_180003ABD
0x180003a09  mov     [rsp+28h+arg_0], rsi
0x180003a0e  call    cs:__imp_RpcImpersonateClient
0x180003a14  mov     esi, eax
0x180003a16  test    eax, eax
0x180003a18  jnz     short loc_180003A76
0x180003a1a  mov     rdx, rbx
0x180003a1d  mov     rcx, rdi
0x180003a20  call    FwQueryRpcClientInfo
0x180003a25  mov     ebx, eax
0x180003a27  test    eax, eax
0x180003a29  js      short loc_180003A43
0x180003a2b  call    cs:__imp_RpcRevertToSelf
0x180003a31  mov     eax, ebx
0x180003a33  mov     rsi, [rsp+28h+arg_0]
0x180003a38  mov     rbx, [rsp+28h+arg_8]
0x180003a3d  add     rsp, 20h
0x180003a41  pop     rdi
0x180003a42  retn
0x180003a43  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a4a  lea     rdi, WPP_GLOBAL_Control
0x180003a51  cmp     rcx, rdi
0x180003a54  jz      short loc_180003A2B
0x180003a56  test    byte ptr [rcx+1Ch], 1
0x180003a5a  jz      short loc_180003A2B
0x180003a5c  mov     rcx, [rcx+10h]
0x180003a60  lea     r8, WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids
0x180003a67  mov     edx, 14h
0x180003a6c  mov     r9d, ebx
0x180003a6f  call    WPP_SF_d
0x180003a74  jmp     short loc_180003A2B
0x180003a76  jle     short loc_180003A81
0x180003a78  movzx   esi, ax
0x180003a7b  or      esi, 80070000h
0x180003a81  test    esi, esi
0x180003a83  jns     short loc_180003A1A
0x180003a85  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a8c  lea     rdi, WPP_GLOBAL_Control
0x180003a93  cmp     rcx, rdi
0x180003a96  jz      short loc_180003AB6
0x180003a98  test    byte ptr [rcx+1Ch], 1
0x180003a9c  jz      short loc_180003AB6
0x180003a9e  mov     rcx, [rcx+10h]
0x180003aa2  lea     r8, WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids
0x180003aa9  mov     edx, 13h
0x180003aae  mov     r9d, esi
0x180003ab1  call    WPP_SF_d
0x180003ab6  mov     eax, esi
0x180003ab8  jmp     loc_180003A33
0x180003abd  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ac4  lea     rdi, WPP_GLOBAL_Control
0x180003acb  cmp     rcx, rdi
0x180003ace  jz      short loc_180003B18
0x180003ad0  test    byte ptr [rcx+1Ch], 1
0x180003ad4  jz      short loc_180003AF2
0x180003ad6  mov     rcx, [rcx+10h]
0x180003ada  lea     r8, WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids
0x180003ae1  mov     edx, 11h
0x180003ae6  call    WPP_SF_
0x180003aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003af2  cmp     rcx, rdi
0x180003af5  jz      short loc_180003B18
0x180003af7  test    byte ptr [rcx+1Ch], 1
0x180003afb  jz      short loc_180003B18
0x180003afd  mov     rcx, [rcx+10h]
0x180003b01  lea     r8, WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids
0x180003b08  mov     edx, 12h
0x180003b0d  mov     r9d, 80070057h
0x180003b13  call    WPP_SF_d
0x180003b18  mov     eax, 80070057h
0x180003b1d  jmp     loc_180003A38
```
