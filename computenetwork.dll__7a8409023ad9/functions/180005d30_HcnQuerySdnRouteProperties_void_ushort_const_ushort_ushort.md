# HcnQuerySdnRouteProperties(void *,ushort const *,ushort * *,ushort * *)

- ea: `0x180005d30`
- end: `0x180005e1f`
- name: `?HcnQuerySdnRouteProperties@@YAJPEAXPEBGPEAPEAG2@Z`
- size: `239`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002188`
- `0x180005d30`
- `0x180007904`
- `0x180009d10`

## string_xrefs

- `0x180005df2`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180005e0c`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnQuerySdnRouteProperties(
        void *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  unsigned int v5; // edi
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned __int16 *v8; // rdx
  void *v9; // rcx
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-28h]
  void *v12; // [rsp+30h] [rbp-18h] BYREF
  void **v13; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *v15; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 *v16; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int16 **v17; // [rsp+60h] [rbp+18h] BYREF

  v17 = a3;
  v16 = a2;
  v15 = a1;
  try
  {
    if ( !a1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x53B,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v11);
    if ( a4 )
      *a4 = 0;
    if ( !a3 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v11);
    *a3 = 0;
    v12 = 0;
    v13 = &v12;
    v5 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,unsigned short const *,unsigned short * *,unsigned short * *),void * &,unsigned short const * &,unsigned short * * &,unsigned short * *>(
           (unsigned int)HnsRpc_QuerySdnRouteProperties,
           (unsigned int)&v15,
           (unsigned int)&v16,
           (unsigned int)&v17,
           (__int64)&v13);
    if ( a4 )
    {
      v8 = (unsigned __int16 *)v12;
      v9 = 0;
      v12 = 0;
      *a4 = v8;
    }
    else
    {
      v9 = v12;
    }
    if ( v9 )
      MIDL_user_free(v9);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x54A, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180005d30  mov     rax, rsp
0x180005d33  mov     [rax+20h], rbx
0x180005d37  mov     [rax+18h], r8
0x180005d3b  mov     [rax+10h], rdx
0x180005d3f  mov     [rax+8], rcx
0x180005d43  push    rdi
0x180005d44  sub     rsp, 40h
0x180005d48  mov     rbx, r9
0x180005d4b  mov     rax, [rsp+48h]
0x180005d50  test    rcx, rcx
0x180005d53  jz      loc_180005DEC
0x180005d59  test    rbx, rbx
0x180005d5c  jz      short loc_180005D65
0x180005d5e  mov     qword ptr [r9], 0
0x180005d65  mov     rcx, [rsp+48h]; this
0x180005d6a  test    r8, r8
0x180005d6d  jz      loc_180005E06
0x180005d73  mov     qword ptr [r8], 0
0x180005d7a  mov     [rsp+48h+var_18], 0
0x180005d83  lea     rax, [rsp+48h+var_18]
0x180005d88  mov     [rsp+48h+var_10], rax
0x180005d8d  lea     rax, [rsp+48h+var_10]
0x180005d92  mov     qword ptr [rsp+48h+var_28], rax
0x180005d97  lea     r9, [rsp+48h+arg_10]
0x180005d9c  lea     r8, [rsp+48h+arg_8]
0x180005da1  lea     rdx, [rsp+48h+arg_0]
0x180005da6  lea     rcx, HnsRpc_QuerySdnRouteProperties
0x180005dad  call    ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x180005db2  mov     edi, eax
0x180005db4  test    rbx, rbx
0x180005db7  jz      short loc_180005DCA
0x180005db9  mov     rdx, [rsp+48h+var_18]
0x180005dbe  xor     ecx, ecx
0x180005dc0  mov     [rsp+48h+var_18], rcx
0x180005dc5  mov     [rbx], rdx
0x180005dc8  jmp     short loc_180005DCF
0x180005dca  mov     rcx, [rsp+48h+var_18]; void *
0x180005dcf  test    rcx, rcx
0x180005dd2  jz      short loc_180005DD9
0x180005dd4  call    MIDL_user_free
0x180005dd9  mov     eax, edi
0x180005ddb  jmp     short loc_180005DE1
0x180005ddd  mov     eax, dword ptr [rsp+48h+arg_0]
0x180005de1  mov     rbx, [rsp+48h+arg_18]
0x180005de6  add     rsp, 40h
0x180005dea  pop     rdi
0x180005deb  retn
0x180005dec  mov     r9d, 80070057h; char *
0x180005df2  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005df9  mov     edx, 53Bh; void *
0x180005dfe  mov     rcx, rax; this
0x180005e01  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005e06  mov     r9d, 80004003h; char *
0x180005e0c  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005e13  mov     edx, 10h; void *
0x180005e18  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
