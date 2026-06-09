# HcnCreateSdnRoute(_GUID const &,ushort const *,void * *,ushort * *)

- ea: `0x180005650`
- end: `0x180005711`
- name: `?HcnCreateSdnRoute@@YAJAEBU_GUID@@PEBGPEAPEAXPEAPEAG@Z`
- size: `193`
- prototype: `__int64 __fastcall(const struct _GUID *, const unsigned __int16 *, void **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002c38`
- `0x180005650`
- `0x180007904`
- `0x180009d10`

## string_xrefs

- `0x1800056fe`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnCreateSdnRoute(
        const struct _GUID *a1,
        const unsigned __int16 *a2,
        void **a3,
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
  const unsigned __int16 *v15; // [rsp+58h] [rbp+10h] BYREF
  void **v16; // [rsp+60h] [rbp+18h] BYREF

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
           HnsRpc_CreateSdnRoute,
           a1,
           &v15,
           &v16,
           &v13);
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
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x4D8, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180005650  mov     [rsp+arg_0], rbx
0x180005655  mov     [rsp+arg_10], r8
0x18000565a  mov     [rsp+arg_8], rdx
0x18000565f  push    rdi
0x180005660  sub     rsp, 40h
0x180005664  mov     rbx, r9
0x180005667  mov     rdx, rcx
0x18000566a  mov     rcx, [rsp+48h]; this
0x18000566f  test    r8, r8
0x180005672  jz      loc_1800056F8
0x180005678  mov     qword ptr [r8], 0
0x18000567f  test    rbx, rbx
0x180005682  jz      short loc_18000568B
0x180005684  mov     qword ptr [r9], 0
0x18000568b  mov     [rsp+48h+var_18], 0
0x180005694  lea     rax, [rsp+48h+var_18]
0x180005699  mov     [rsp+48h+var_10], rax
0x18000569e  lea     rax, [rsp+48h+var_10]
0x1800056a3  mov     qword ptr [rsp+48h+var_28], rax
0x1800056a8  lea     r9, [rsp+48h+arg_10]
0x1800056ad  lea     r8, [rsp+48h+arg_8]
0x1800056b2  lea     rcx, HnsRpc_CreateSdnRoute
0x1800056b9  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@ZAEBU1@AEAPEBGAEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@Z1AEAPEBGAEAPEAPEAX$$QEAPEAPEAG@Z
0x1800056be  mov     edi, eax
0x1800056c0  test    rbx, rbx
0x1800056c3  jz      short loc_1800056D6
0x1800056c5  mov     rdx, [rsp+48h+var_18]
0x1800056ca  xor     ecx, ecx
0x1800056cc  mov     [rsp+48h+var_18], rcx
0x1800056d1  mov     [rbx], rdx
0x1800056d4  jmp     short loc_1800056DB
0x1800056d6  mov     rcx, [rsp+48h+var_18]; void *
0x1800056db  test    rcx, rcx
0x1800056de  jz      short loc_1800056E5
0x1800056e0  call    MIDL_user_free
0x1800056e5  mov     eax, edi
0x1800056e7  jmp     short loc_1800056ED
0x1800056e9  mov     eax, dword ptr [rsp+48h+arg_10]
0x1800056ed  mov     rbx, [rsp+48h+arg_0]
0x1800056f2  add     rsp, 40h
0x1800056f6  pop     rdi
0x1800056f7  retn
0x1800056f8  mov     r9d, 80004003h; char *
0x1800056fe  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005705  mov     edx, 10h; void *
0x18000570a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
