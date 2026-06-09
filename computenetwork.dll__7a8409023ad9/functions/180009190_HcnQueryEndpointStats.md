# HcnQueryEndpointStats

- ea: `0x180009190`
- end: `0x18000927f`
- name: `HcnQueryEndpointStats`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002188`
- `0x180007904`
- `0x180009190`
- `0x180009d10`

## string_xrefs

- `0x180009252`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x18000926c`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnQueryEndpointStats(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4)
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
        (void *)0x310,
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
           (unsigned int)HnsRpc_QueryEndpointStats,
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
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x31F, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180009190  mov     rax, rsp
0x180009193  mov     [rax+20h], rbx
0x180009197  mov     [rax+18h], r8
0x18000919b  mov     [rax+10h], rdx
0x18000919f  mov     [rax+8], rcx
0x1800091a3  push    rdi
0x1800091a4  sub     rsp, 40h
0x1800091a8  mov     rbx, r9
0x1800091ab  mov     rax, [rsp+48h]
0x1800091b0  test    rcx, rcx
0x1800091b3  jz      loc_18000924C
0x1800091b9  mov     rcx, [rsp+48h]; this
0x1800091be  test    r8, r8
0x1800091c1  jz      loc_180009266
0x1800091c7  mov     qword ptr [r8], 0
0x1800091ce  test    rbx, rbx
0x1800091d1  jz      short loc_1800091DA
0x1800091d3  mov     qword ptr [r9], 0
0x1800091da  mov     [rsp+48h+var_18], 0
0x1800091e3  lea     rax, [rsp+48h+var_18]
0x1800091e8  mov     [rsp+48h+var_10], rax
0x1800091ed  lea     rax, [rsp+48h+var_10]
0x1800091f2  mov     qword ptr [rsp+48h+var_28], rax
0x1800091f7  lea     r9, [rsp+48h+arg_10]
0x1800091fc  lea     r8, [rsp+48h+arg_8]
0x180009201  lea     rdx, [rsp+48h+arg_0]
0x180009206  lea     rcx, HnsRpc_QueryEndpointStats
0x18000920d  call    ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x180009212  mov     edi, eax
0x180009214  test    rbx, rbx
0x180009217  jz      short loc_18000922A
0x180009219  mov     rdx, [rsp+48h+var_18]
0x18000921e  xor     ecx, ecx
0x180009220  mov     [rsp+48h+var_18], rcx
0x180009225  mov     [rbx], rdx
0x180009228  jmp     short loc_18000922F
0x18000922a  mov     rcx, [rsp+48h+var_18]; void *
0x18000922f  test    rcx, rcx
0x180009232  jz      short loc_180009239
0x180009234  call    MIDL_user_free
0x180009239  mov     eax, edi
0x18000923b  jmp     short loc_180009241
0x18000923d  mov     eax, dword ptr [rsp+48h+arg_0]
0x180009241  mov     rbx, [rsp+48h+arg_18]
0x180009246  add     rsp, 40h
0x18000924a  pop     rdi
0x18000924b  retn
0x18000924c  mov     r9d, 80070057h; char *
0x180009252  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009259  mov     edx, 310h; void *
0x18000925e  mov     rcx, rax; this
0x180009261  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009266  mov     r9d, 80004003h; char *
0x18000926c  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009273  mov     edx, 10h; void *
0x180009278  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
