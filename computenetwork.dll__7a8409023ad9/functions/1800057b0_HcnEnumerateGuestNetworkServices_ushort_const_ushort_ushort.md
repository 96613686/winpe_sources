# HcnEnumerateGuestNetworkServices(ushort const *,ushort * *,ushort * *)

- ea: `0x1800057b0`
- end: `0x180005865`
- name: `?HcnEnumerateGuestNetworkServices@@YAJPEBGPEAPEAG1@Z`
- size: `181`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002f88`
- `0x1800057b0`
- `0x180007904`
- `0x180009d10`

## string_xrefs

- `0x180005852`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnEnumerateGuestNetworkServices(
        const unsigned __int16 *a1,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
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
           HnsRpc_EnumerateGuestNetworkServices,
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
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x5AD, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800057b0  mov     [rsp+arg_10], rbx
0x1800057b5  mov     [rsp+arg_8], rdx
0x1800057ba  mov     [rsp+arg_0], rcx
0x1800057bf  push    rdi
0x1800057c0  sub     rsp, 30h
0x1800057c4  mov     rbx, r8
0x1800057c7  mov     rcx, [rsp+38h]; this
0x1800057cc  test    rdx, rdx
0x1800057cf  jz      short loc_18000584C
0x1800057d1  mov     qword ptr [rdx], 0
0x1800057d8  test    rbx, rbx
0x1800057db  jz      short loc_1800057E4
0x1800057dd  mov     qword ptr [r8], 0
0x1800057e4  mov     [rsp+38h+arg_18], 0
0x1800057ed  lea     rax, [rsp+38h+arg_18]
0x1800057f2  mov     [rsp+38h+var_18], rax
0x1800057f7  lea     r9, [rsp+38h+var_18]
0x1800057fc  lea     r8, [rsp+38h+arg_8]
0x180005801  lea     rdx, [rsp+38h+arg_0]
0x180005806  lea     rcx, HnsRpc_EnumerateGuestNetworkServices
0x18000580d  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x180005812  mov     edi, eax
0x180005814  test    rbx, rbx
0x180005817  jz      short loc_18000582A
0x180005819  mov     rdx, [rsp+38h+arg_18]
0x18000581e  xor     ecx, ecx
0x180005820  mov     [rsp+38h+arg_18], rcx
0x180005825  mov     [rbx], rdx
0x180005828  jmp     short loc_18000582F
0x18000582a  mov     rcx, [rsp+38h+arg_18]; void *
0x18000582f  test    rcx, rcx
0x180005832  jz      short loc_180005839
0x180005834  call    MIDL_user_free
0x180005839  mov     eax, edi
0x18000583b  jmp     short loc_180005841
0x18000583d  mov     eax, dword ptr [rsp+38h+arg_8]
0x180005841  mov     rbx, [rsp+38h+arg_10]
0x180005846  add     rsp, 30h
0x18000584a  pop     rdi
0x18000584b  retn
0x18000584c  mov     r9d, 80004003h; char *
0x180005852  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005859  mov     edx, 10h; void *
0x18000585e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
