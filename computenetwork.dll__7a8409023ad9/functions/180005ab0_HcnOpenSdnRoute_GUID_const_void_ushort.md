# HcnOpenSdnRoute(_GUID const &,void * *,ushort * *)

- ea: `0x180005ab0`
- end: `0x180005b61`
- name: `?HcnOpenSdnRoute@@YAJAEBU_GUID@@PEAPEAXPEAPEAG@Z`
- size: `177`
- prototype: `__int64 __fastcall(const struct _GUID *, void **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002ad4`
- `0x180005ab0`
- `0x180007904`
- `0x180009d10`

## string_xrefs

- `0x180005b4e`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnOpenSdnRoute(const struct _GUID *a1, void **a2, unsigned __int16 **a3)
{
  unsigned int v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  unsigned __int16 *v7; // rdx
  void *v8; // rcx
  __int64 result; // rax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void **v12; // [rsp+48h] [rbp+10h] BYREF
  void *v13; // [rsp+58h] [rbp+20h] BYREF

  v12 = a2;
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
    v13 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,void * *,unsigned short * *),_GUID const &,void * * &,unsigned short * *>(
           HnsRpc_OpenSdnRoute,
           a1,
           &v12,
           v10,
           &v13);
    if ( a3 )
    {
      v7 = (unsigned __int16 *)v13;
      v8 = 0;
      v13 = 0;
      *a3 = v7;
    }
    else
    {
      v8 = v13;
    }
    if ( v8 )
      MIDL_user_free(v8);
    result = v4;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x4FC, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180005ab0  mov     [rsp+arg_0], rbx
0x180005ab5  mov     [rsp+arg_8], rdx
0x180005aba  push    rdi
0x180005abb  sub     rsp, 30h
0x180005abf  mov     rbx, r8
0x180005ac2  mov     rax, rcx
0x180005ac5  mov     rcx, [rsp+38h]; this
0x180005aca  test    rdx, rdx
0x180005acd  jz      short loc_180005B48
0x180005acf  mov     qword ptr [rdx], 0
0x180005ad6  test    rbx, rbx
0x180005ad9  jz      short loc_180005AE2
0x180005adb  mov     qword ptr [r8], 0
0x180005ae2  mov     [rsp+38h+arg_18], 0
0x180005aeb  lea     rcx, [rsp+38h+arg_18]
0x180005af0  mov     [rsp+38h+var_18], rcx
0x180005af5  lea     r9, [rsp+38h+var_18]
0x180005afa  lea     r8, [rsp+38h+arg_8]
0x180005aff  mov     rdx, rax
0x180005b02  lea     rcx, HnsRpc_OpenSdnRoute
0x180005b09  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@ZAEBU1@AEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@Z1AEAPEAPEAX$$QEAPEAPEAG@Z
0x180005b0e  mov     edi, eax
0x180005b10  test    rbx, rbx
0x180005b13  jz      short loc_180005B26
0x180005b15  mov     rdx, [rsp+38h+arg_18]
0x180005b1a  xor     ecx, ecx
0x180005b1c  mov     [rsp+38h+arg_18], rcx
0x180005b21  mov     [rbx], rdx
0x180005b24  jmp     short loc_180005B2B
0x180005b26  mov     rcx, [rsp+38h+arg_18]; void *
0x180005b2b  test    rcx, rcx
0x180005b2e  jz      short loc_180005B35
0x180005b30  call    MIDL_user_free
0x180005b35  mov     eax, edi
0x180005b37  jmp     short loc_180005B3D
0x180005b39  mov     eax, dword ptr [rsp+38h+arg_8]
0x180005b3d  mov     rbx, [rsp+38h+arg_0]
0x180005b42  add     rsp, 30h
0x180005b46  pop     rdi
0x180005b47  retn
0x180005b48  mov     r9d, 80004003h; char *
0x180005b4e  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005b55  mov     edx, 10h; void *
0x180005b5a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
