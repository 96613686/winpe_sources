# HcnQueryEndpointAddresses

- ea: `0x180008f90`
- end: `0x18000907f`
- name: `HcnQueryEndpointAddresses`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002188`
- `0x180007904`
- `0x180008f90`
- `0x180009d10`

## string_xrefs

- `0x180009052`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x18000906c`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnQueryEndpointAddresses(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
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
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF
  _QWORD *v17; // [rsp+60h] [rbp+18h] BYREF

  v17 = a3;
  v16 = a2;
  v15 = a1;
  try
  {
    if ( !a1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x33B,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v11);
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
    v5 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,unsigned short const *,unsigned short * *,unsigned short * *),void * &,unsigned short const * &,unsigned short * * &,unsigned short * *>(
           (unsigned int)HnsRpc_QueryEndpointAddresses,
           (unsigned int)&v15,
           (unsigned int)&v16,
           (unsigned int)&v17,
           (__int64)&v13);
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
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x34A, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180008f90  mov     rax, rsp
0x180008f93  mov     [rax+20h], rbx
0x180008f97  mov     [rax+18h], r8
0x180008f9b  mov     [rax+10h], rdx
0x180008f9f  mov     [rax+8], rcx
0x180008fa3  push    rdi
0x180008fa4  sub     rsp, 40h
0x180008fa8  mov     rbx, r9
0x180008fab  mov     rax, [rsp+48h]
0x180008fb0  test    rcx, rcx
0x180008fb3  jz      loc_18000904C
0x180008fb9  mov     rcx, [rsp+48h]; this
0x180008fbe  test    r8, r8
0x180008fc1  jz      loc_180009066
0x180008fc7  mov     qword ptr [r8], 0
0x180008fce  test    rbx, rbx
0x180008fd1  jz      short loc_180008FDA
0x180008fd3  mov     qword ptr [r9], 0
0x180008fda  mov     [rsp+48h+var_18], 0
0x180008fe3  lea     rax, [rsp+48h+var_18]
0x180008fe8  mov     [rsp+48h+var_10], rax
0x180008fed  lea     rax, [rsp+48h+var_10]
0x180008ff2  mov     qword ptr [rsp+48h+var_28], rax
0x180008ff7  lea     r9, [rsp+48h+arg_10]
0x180008ffc  lea     r8, [rsp+48h+arg_8]
0x180009001  lea     rdx, [rsp+48h+arg_0]
0x180009006  lea     rcx, HnsRpc_QueryEndpointAddresses
0x18000900d  call    ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x180009012  mov     edi, eax
0x180009014  test    rbx, rbx
0x180009017  jz      short loc_18000902A
0x180009019  mov     rdx, [rsp+48h+var_18]
0x18000901e  xor     ecx, ecx
0x180009020  mov     [rsp+48h+var_18], rcx
0x180009025  mov     [rbx], rdx
0x180009028  jmp     short loc_18000902F
0x18000902a  mov     rcx, [rsp+48h+var_18]; void *
0x18000902f  test    rcx, rcx
0x180009032  jz      short loc_180009039
0x180009034  call    MIDL_user_free
0x180009039  mov     eax, edi
0x18000903b  jmp     short loc_180009041
0x18000903d  mov     eax, dword ptr [rsp+48h+arg_0]
0x180009041  mov     rbx, [rsp+48h+arg_18]
0x180009046  add     rsp, 40h
0x18000904a  pop     rdi
0x18000904b  retn
0x18000904c  mov     r9d, 80070057h; char *
0x180009052  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009059  mov     edx, 33Bh; void *
0x18000905e  mov     rcx, rax; this
0x180009061  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009066  mov     r9d, 80004003h; char *
0x18000906c  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009073  mov     edx, 10h; void *
0x180009078  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
