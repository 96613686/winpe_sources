# HcnQueryMetrics(ushort const *,ushort * *,ushort * *)

- ea: `0x180005c70`
- end: `0x180005d25`
- name: `?HcnQueryMetrics@@YAJPEBGPEAPEAG1@Z`
- size: `181`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f88`
- `0x180005c70`
- `0x180007904`
- `0x180009d10`

## string_xrefs

- `0x180005d12`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnQueryMetrics(const unsigned __int16 *a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  unsigned int v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  unsigned __int16 *v7; // rdx
  void *v8; // rcx
  __int64 result; // rax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  const unsigned __int16 *v12; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int16 **v13; // [rsp+48h] [rbp+10h] BYREF
  void *v14; // [rsp+58h] [rbp+20h] BYREF

  v13 = a2;
  v12 = a1;
  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v10[0]);
    *a2 = 0;
    if ( a3 )
      *a3 = 0;
    v14 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,unsigned short const *,unsigned short * *,unsigned short * *),unsigned short const * &,unsigned short * * &,unsigned short * *>(
           HnsRpc_QueryMetrics,
           &v12,
           &v13,
           v10,
           &v14);
    if ( a3 )
    {
      v7 = (unsigned __int16 *)v14;
      v8 = 0;
      v14 = 0;
      *a3 = v7;
    }
    else
    {
      v8 = v14;
    }
    if ( v8 )
      MIDL_user_free(v8);
    result = v4;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x821, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180005c70  mov     [rsp+arg_10], rbx
0x180005c75  mov     [rsp+arg_8], rdx
0x180005c7a  mov     [rsp+arg_0], rcx
0x180005c7f  push    rdi
0x180005c80  sub     rsp, 30h
0x180005c84  mov     rbx, r8
0x180005c87  mov     rcx, [rsp+38h]; this
0x180005c8c  test    rdx, rdx
0x180005c8f  jz      short loc_180005D0C
0x180005c91  mov     qword ptr [rdx], 0
0x180005c98  test    rbx, rbx
0x180005c9b  jz      short loc_180005CA4
0x180005c9d  mov     qword ptr [r8], 0
0x180005ca4  mov     [rsp+38h+arg_18], 0
0x180005cad  lea     rax, [rsp+38h+arg_18]
0x180005cb2  mov     [rsp+38h+var_18], rax
0x180005cb7  lea     r9, [rsp+38h+var_18]
0x180005cbc  lea     r8, [rsp+38h+arg_8]
0x180005cc1  lea     rdx, [rsp+38h+arg_0]
0x180005cc6  lea     rcx, HnsRpc_QueryMetrics
0x180005ccd  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x180005cd2  mov     edi, eax
0x180005cd4  test    rbx, rbx
0x180005cd7  jz      short loc_180005CEA
0x180005cd9  mov     rdx, [rsp+38h+arg_18]
0x180005cde  xor     ecx, ecx
0x180005ce0  mov     [rsp+38h+arg_18], rcx
0x180005ce5  mov     [rbx], rdx
0x180005ce8  jmp     short loc_180005CEF
0x180005cea  mov     rcx, [rsp+38h+arg_18]; void *
0x180005cef  test    rcx, rcx
0x180005cf2  jz      short loc_180005CF9
0x180005cf4  call    MIDL_user_free
0x180005cf9  mov     eax, edi
0x180005cfb  jmp     short loc_180005D01
0x180005cfd  mov     eax, dword ptr [rsp+38h+arg_8]
0x180005d01  mov     rbx, [rsp+38h+arg_10]
0x180005d06  add     rsp, 30h
0x180005d0a  pop     rdi
0x180005d0b  retn
0x180005d0c  mov     r9d, 80004003h; char *
0x180005d12  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005d19  mov     edx, 10h; void *
0x180005d1e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
