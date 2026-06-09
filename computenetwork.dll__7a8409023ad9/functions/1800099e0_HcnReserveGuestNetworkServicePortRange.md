# HcnReserveGuestNetworkServicePortRange

- ea: `0x1800099e0`
- end: `0x180009bb4`
- name: `HcnReserveGuestNetworkServicePortRange`
- size: `468`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002314`
- `0x180006a54`
- `0x180007904`
- `0x1800099e0`

## string_xrefs

- `0x180009a18`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180009a3d`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180009a79`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180009aa4`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180009b4e`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180009ba1`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
__int64 __fastcall HcnReserveGuestNetworkServicePortRange(__int64 a1, unsigned __int16 a2, int *a3, _QWORD *a4)
{
  bool v5; // zf
  int v6; // ecx
  __int64 result; // rax
  unsigned __int16 v8; // bx
  unsigned int v9; // r8d
  const char *v10; // r9
  unsigned int v11; // edi
  int v12; // [rsp+20h] [rbp-48h]
  int v13; // [rsp+20h] [rbp-48h]
  int v14; // [rsp+40h] [rbp-28h] BYREF
  int v15; // [rsp+44h] [rbp-24h] BYREF
  int v16; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v18; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v19; // [rsp+88h] [rbp+20h] BYREF

  v19 = a4;
  v18 = a1;
  v5 = a1 == 0;
  v6 = (int)retaddr;
  if ( v5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6BF,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
      (const char *)0x80070057LL,
      v12);
    return 2147942487LL;
  }
  else if ( a3 )
  {
    if ( !a4 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v12);
    *a4 = 0;
    if ( a2 <= 0xEA47u )
    {
      if ( a2 )
      {
        v8 = a2 / 3u;
        if ( (int)(a2 / 3u) < 1 )
          v8 = 1;
        HIWORD(v14) = -4536;
        LOWORD(v14) = -4536 - a2;
        try
        {
          while ( 1 )
          {
            v15 = 1;
            v16 = 3;
            LODWORD(result) = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,enum __MIDL_HnsRpc_0001,enum __MIDL_HnsRpc_0002,unsigned short,unsigned short,void * *),void * &,enum __MIDL_HnsRpc_0001,enum __MIDL_HnsRpc_0002,unsigned short &,unsigned short &,void * *>(
                                v6,
                                (unsigned int)&v18,
                                (unsigned int)&v16,
                                (unsigned int)&v15,
                                (__int64)&v14,
                                (__int64)&v14 + 2,
                                (__int64)&v19);
            v11 = result;
            if ( (int)result >= 0 )
              break;
            if ( (unsigned __int16)v14 < (unsigned int)v8 + 1025 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x6E8,
                (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
                (const char *)(unsigned int)result,
                v13);
              result = v11;
              goto LABEL_23;
            }
            LOWORD(v14) = v14 - v8;
            HIWORD(v14) -= v8;
          }
          *a3 = v14;
          result = (unsigned int)result;
        }
        catch ( ... )
        {
          result = (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x6F9, v9, v10);
        }
LABEL_23:
        ;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6CF,
          (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
          (const char *)0x80070057LL,
          v12);
        return 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6CB,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v12);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C0,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
      (const char *)0x80070057LL,
      v12);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800099e0  mov     rax, rsp
0x1800099e3  mov     [rax+10h], rbx
0x1800099e7  mov     [rax+18h], rsi
0x1800099eb  mov     [rax+20h], r9
0x1800099ef  mov     [rax+8], rcx
0x1800099f3  push    rdi
0x1800099f4  push    r14
0x1800099f6  push    r15
0x1800099f8  sub     rsp, 50h
0x1800099fc  mov     rsi, r8
0x1800099ff  movzx   r10d, dx
0x180009a03  xor     r14d, r14d
0x180009a06  test    rcx, rcx
0x180009a09  mov     rcx, [rsp+68h]; this
0x180009a0e  jnz     short loc_180009A30
0x180009a10  mov     ebx, 80070057h
0x180009a15  mov     r9d, ebx; char *
0x180009a18  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009a1f  mov     edx, 6BFh; void *
0x180009a24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a29  mov     eax, ebx
0x180009a2b  jmp     loc_180009B85
0x180009a30  test    rsi, rsi
0x180009a33  jnz     short loc_180009A55
0x180009a35  mov     ebx, 80070057h
0x180009a3a  mov     r9d, ebx; char *
0x180009a3d  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009a44  mov     edx, 6C0h; void *
0x180009a49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a4e  mov     eax, ebx
0x180009a50  jmp     loc_180009B85
0x180009a55  test    r9, r9
0x180009a58  jz      loc_180009B9B
0x180009a5e  mov     [r9], r14
0x180009a61  mov     eax, 0EA47h
0x180009a66  cmp     r10w, ax
0x180009a6a  jbe     short loc_180009A91
0x180009a6c  mov     rcx, [rsp+68h]; this
0x180009a71  mov     ebx, 80070057h
0x180009a76  mov     r9d, ebx; char *
0x180009a79  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009a80  mov     edx, 6CBh; void *
0x180009a85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a8a  mov     eax, ebx
0x180009a8c  jmp     loc_180009B85
0x180009a91  test    r10w, r10w
0x180009a95  jnz     short loc_180009ABC
0x180009a97  mov     rcx, [rsp+68h]; this
0x180009a9c  mov     ebx, 80070057h
0x180009aa1  mov     r9d, ebx; char *
0x180009aa4  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009aab  mov     edx, 6CFh; void *
0x180009ab0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ab5  mov     eax, ebx
0x180009ab7  jmp     loc_180009B85
0x180009abc  mov     eax, 0AAAAAAABh
0x180009ac1  mul     r10d
0x180009ac4  mov     ebx, edx
0x180009ac6  shr     ebx, 1
0x180009ac8  mov     r15d, 1
0x180009ace  cmp     ebx, r15d
0x180009ad1  jge     short loc_180009AD7
0x180009ad3  movzx   ebx, r15w
0x180009ad7  mov     eax, 0EE48h
0x180009adc  mov     word ptr [rsp+68h+var_28+2], ax
0x180009ae1  sub     ax, r10w
0x180009ae5  mov     word ptr [rsp+68h+var_28], ax
0x180009aea  mov     [rsp+68h+var_24], r15d
0x180009aef  mov     [rsp+68h+var_20], 3
0x180009af7  lea     rax, [rsp+68h+arg_18]
0x180009aff  mov     [rsp+68h+var_38], rax
0x180009b04  lea     rax, [rsp+68h+var_28+2]
0x180009b09  mov     [rsp+68h+var_40], rax
0x180009b0e  lea     rax, [rsp+68h+var_28]
0x180009b13  mov     qword ptr [rsp+68h+var_48], rax; int
0x180009b18  lea     r9, [rsp+68h+var_24]
0x180009b1d  lea     r8, [rsp+68h+var_20]
0x180009b22  lea     rdx, [rsp+68h+arg_0]
0x180009b27  call    ??$InvokeRpcFunction@P6AJPEAXW4__MIDL_HnsRpc_0001@@W4__MIDL_HnsRpc_0002@@GGPEAPEAX@ZAEAPEAXW41@W42@AEAGAEAGPEAPEAX@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXW4__MIDL_HnsRpc_0001@@W4__MIDL_HnsRpc_0002@@GGPEAPEAX@ZAEAPEAX$$QEAW43@$$QEAW44@AEAG8$$QEAPEAPEAX@Z
0x180009b2c  mov     edi, eax
0x180009b2e  test    eax, eax
0x180009b30  jns     short loc_180009B77
0x180009b32  movzx   edx, bx
0x180009b35  add     edx, 401h
0x180009b3b  movzx   r8d, word ptr [rsp+68h+var_28]
0x180009b41  cmp     r8d, edx
0x180009b44  jnb     short loc_180009B63
0x180009b46  mov     rcx, [rsp+68h]; this
0x180009b4b  mov     r9d, eax; char *
0x180009b4e  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009b55  mov     edx, 6E8h; void *
0x180009b5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b5f  mov     eax, edi
0x180009b61  jmp     short loc_180009B85
0x180009b63  sub     r8w, bx
0x180009b67  mov     word ptr [rsp+68h+var_28], r8w
0x180009b6d  sub     word ptr [rsp+68h+var_28+2], bx
0x180009b72  jmp     loc_180009AEA
0x180009b77  mov     eax, [rsp+68h+var_28]
0x180009b7b  mov     [rsi], eax
0x180009b7d  mov     eax, edi
0x180009b7f  jmp     short loc_180009B85
0x180009b81  mov     eax, dword ptr [rsp+68h+arg_0]
0x180009b85  lea     r11, [rsp+68h+var_18]
0x180009b8a  mov     rbx, [r11+28h]
0x180009b8e  mov     rsi, [r11+30h]
0x180009b92  mov     rsp, r11
0x180009b95  pop     r15
0x180009b97  pop     r14
0x180009b99  pop     rdi
0x180009b9a  retn
0x180009b9b  mov     r9d, 80004003h; char *
0x180009ba1  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009ba8  mov     edx, 10h; void *
0x180009bad  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
