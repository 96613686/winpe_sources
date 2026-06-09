# HcnOpenGuestNetworkService(_GUID const &,void * *,ushort * *)

- ea: `0x1800059f0`
- end: `0x180005aa1`
- name: `?HcnOpenGuestNetworkService@@YAJAEBU_GUID@@PEAPEAXPEAPEAG@Z`
- size: `177`
- prototype: `__int64 __fastcall(const struct _GUID *, void **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002ad4`
- `0x1800059f0`
- `0x180007904`
- `0x180009d10`

## string_xrefs

- `0x180005a8e`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnOpenGuestNetworkService(const struct _GUID *a1, void **a2, unsigned __int16 **a3)
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
           HnsRpc_OpenGuestNetworkService,
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
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x5F8, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800059f0  mov     [rsp+arg_0], rbx
0x1800059f5  mov     [rsp+arg_8], rdx
0x1800059fa  push    rdi
0x1800059fb  sub     rsp, 30h
0x1800059ff  mov     rbx, r8
0x180005a02  mov     rax, rcx
0x180005a05  mov     rcx, [rsp+38h]; this
0x180005a0a  test    rdx, rdx
0x180005a0d  jz      short loc_180005A88
0x180005a0f  mov     qword ptr [rdx], 0
0x180005a16  test    rbx, rbx
0x180005a19  jz      short loc_180005A22
0x180005a1b  mov     qword ptr [r8], 0
0x180005a22  mov     [rsp+38h+arg_18], 0
0x180005a2b  lea     rcx, [rsp+38h+arg_18]
0x180005a30  mov     [rsp+38h+var_18], rcx
0x180005a35  lea     r9, [rsp+38h+var_18]
0x180005a3a  lea     r8, [rsp+38h+arg_8]
0x180005a3f  mov     rdx, rax
0x180005a42  lea     rcx, HnsRpc_OpenGuestNetworkService
0x180005a49  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@ZAEBU1@AEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAXPEAPEAG@Z1AEAPEAPEAX$$QEAPEAPEAG@Z
0x180005a4e  mov     edi, eax
0x180005a50  test    rbx, rbx
0x180005a53  jz      short loc_180005A66
0x180005a55  mov     rdx, [rsp+38h+arg_18]
0x180005a5a  xor     ecx, ecx
0x180005a5c  mov     [rsp+38h+arg_18], rcx
0x180005a61  mov     [rbx], rdx
0x180005a64  jmp     short loc_180005A6B
0x180005a66  mov     rcx, [rsp+38h+arg_18]; void *
0x180005a6b  test    rcx, rcx
0x180005a6e  jz      short loc_180005A75
0x180005a70  call    MIDL_user_free
0x180005a75  mov     eax, edi
0x180005a77  jmp     short loc_180005A7D
0x180005a79  mov     eax, dword ptr [rsp+38h+arg_8]
0x180005a7d  mov     rbx, [rsp+38h+arg_0]
0x180005a82  add     rsp, 30h
0x180005a86  pop     rdi
0x180005a87  retn
0x180005a88  mov     r9d, 80004003h; char *
0x180005a8e  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005a95  mov     edx, 10h; void *
0x180005a9a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
