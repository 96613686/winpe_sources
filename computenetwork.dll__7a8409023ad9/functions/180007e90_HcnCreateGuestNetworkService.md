# HcnCreateGuestNetworkService

- ea: `0x180007e90`
- end: `0x180007f51`
- name: `HcnCreateGuestNetworkService`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002c38`
- `0x180007904`
- `0x180007e90`
- `0x180009d10`

## string_xrefs

- `0x180007f3e`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnCreateGuestNetworkService(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  unsigned int v5; // edi
  unsigned int v6; // r8d
  const char *v7; // r9
  void *v8; // rdx
  void *v9; // rcx
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-28h]
  void *v12; // [rsp+30h] [rbp-18h] BYREF
  void **v13; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF
  _QWORD *v16; // [rsp+60h] [rbp+18h] BYREF

  v16 = a3;
  v15 = a2;
  try
  {
    if ( !a3 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v11);
    *a3 = 0;
    if ( a4 )
      *a4 = 0;
    v12 = 0;
    v13 = &v12;
    v5 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,unsigned short const *,void * *,unsigned short * *),_GUID const &,unsigned short const * &,void * * &,unsigned short * *>(
           HnsRpc_CreateGuestNetworkService,
           a1,
           &v15,
           &v16,
           &v13);
    if ( a4 )
    {
      v8 = v12;
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
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x5D4, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180007e90  mov     [rsp+arg_0], rbx
0x180007e95  mov     [rsp+arg_10], r8
0x180007e9a  mov     [rsp+arg_8], rdx
0x180007e9f  push    rdi
0x180007ea0  sub     rsp, 40h
0x180007ea4  mov     rbx, r9
0x180007ea7  mov     rdx, rcx
0x180007eaa  mov     rcx, [rsp+48h]; this
0x180007eaf  test    r8, r8
0x180007eb2  jz      loc_180007F38
0x180007eb8  mov     qword ptr [r8], 0
0x180007ebf  test    rbx, rbx
0x180007ec2  jz      short loc_180007ECB
0x180007ec4  mov     qword ptr [r9], 0
0x180007ecb  mov     [rsp+48h+var_18], 0
0x180007ed4  lea     rax, [rsp+48h+var_18]
0x180007ed9  mov     [rsp+48h+var_10], rax
0x180007ede  lea     rax, [rsp+48h+var_10]
0x180007ee3  mov     qword ptr [rsp+48h+var_28], rax
0x180007ee8  lea     r9, [rsp+48h+arg_10]
0x180007eed  lea     r8, [rsp+48h+arg_8]
0x180007ef2  lea     rcx, HnsRpc_CreateGuestNetworkService
0x180007ef9  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@ZAEBU1@AEAPEBGAEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@Z1AEAPEBGAEAPEAPEAX$$QEAPEAPEAG@Z
0x180007efe  mov     edi, eax
0x180007f00  test    rbx, rbx
0x180007f03  jz      short loc_180007F16
0x180007f05  mov     rdx, [rsp+48h+var_18]
0x180007f0a  xor     ecx, ecx
0x180007f0c  mov     [rsp+48h+var_18], rcx
0x180007f11  mov     [rbx], rdx
0x180007f14  jmp     short loc_180007F1B
0x180007f16  mov     rcx, [rsp+48h+var_18]; void *
0x180007f1b  test    rcx, rcx
0x180007f1e  jz      short loc_180007F25
0x180007f20  call    MIDL_user_free
0x180007f25  mov     eax, edi
0x180007f27  jmp     short loc_180007F2D
0x180007f29  mov     eax, dword ptr [rsp+48h+arg_10]
0x180007f2d  mov     rbx, [rsp+48h+arg_0]
0x180007f32  add     rsp, 40h
0x180007f36  pop     rdi
0x180007f37  retn
0x180007f38  mov     r9d, 80004003h; char *
0x180007f3e  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180007f45  mov     edx, 10h; void *
0x180007f4a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
