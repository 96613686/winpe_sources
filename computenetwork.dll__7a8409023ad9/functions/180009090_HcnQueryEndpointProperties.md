# HcnQueryEndpointProperties

- ea: `0x180009090`
- end: `0x18000917f`
- name: `HcnQueryEndpointProperties`
- size: `239`
- prototype: `HRESULT __stdcall(HCN_ENDPOINT Endpoint, PCWSTR Query, PWSTR *Properties, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002188`
- `0x180007904`
- `0x180009090`
- `0x180009d10`

## string_xrefs

- `0x180009152`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x18000916c`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnQueryEndpointProperties(
        HCN_ENDPOINT Endpoint,
        PCWSTR Query,
        PWSTR *Properties,
        PWSTR *ErrorRecord)
{
  HRESULT v5; // edi
  unsigned int v6; // r8d
  const char *v7; // r9
  WCHAR *v8; // rdx
  void *v9; // rcx
  HRESULT result; // eax
  int v11; // [rsp+20h] [rbp-28h]
  void *v12; // [rsp+30h] [rbp-18h] BYREF
  void **v13; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HCN_ENDPOINT v15; // [rsp+50h] [rbp+8h] BYREF
  PCWSTR v16; // [rsp+58h] [rbp+10h] BYREF
  PWSTR *v17; // [rsp+60h] [rbp+18h] BYREF

  v17 = Properties;
  v16 = Query;
  v15 = Endpoint;
  try
  {
    if ( !Endpoint )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2E5,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v11);
    if ( !Properties )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v11);
    *Properties = 0;
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v12 = 0;
    v13 = &v12;
    v5 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,unsigned short const *,unsigned short * *,unsigned short * *),void * &,unsigned short const * &,unsigned short * * &,unsigned short * *>(
           (unsigned int)HnsRpc_QueryEndpointProperties,
           (unsigned int)&v15,
           (unsigned int)&v16,
           (unsigned int)&v17,
           (__int64)&v13);
    if ( ErrorRecord )
    {
      v8 = (WCHAR *)v12;
      v9 = 0;
      v12 = 0;
      *ErrorRecord = v8;
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x2F4, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180009090  mov     rax, rsp
0x180009093  mov     [rax+20h], rbx
0x180009097  mov     [rax+18h], r8
0x18000909b  mov     [rax+10h], rdx
0x18000909f  mov     [rax+8], rcx
0x1800090a3  push    rdi
0x1800090a4  sub     rsp, 40h
0x1800090a8  mov     rbx, r9
0x1800090ab  mov     rax, [rsp+48h]
0x1800090b0  test    rcx, rcx
0x1800090b3  jz      loc_18000914C
0x1800090b9  mov     rcx, [rsp+48h]; this
0x1800090be  test    r8, r8
0x1800090c1  jz      loc_180009166
0x1800090c7  mov     qword ptr [r8], 0
0x1800090ce  test    rbx, rbx
0x1800090d1  jz      short loc_1800090DA
0x1800090d3  mov     qword ptr [r9], 0
0x1800090da  mov     [rsp+48h+var_18], 0
0x1800090e3  lea     rax, [rsp+48h+var_18]
0x1800090e8  mov     [rsp+48h+var_10], rax
0x1800090ed  lea     rax, [rsp+48h+var_10]
0x1800090f2  mov     qword ptr [rsp+48h+var_28], rax
0x1800090f7  lea     r9, [rsp+48h+arg_10]
0x1800090fc  lea     r8, [rsp+48h+arg_8]
0x180009101  lea     rdx, [rsp+48h+arg_0]
0x180009106  lea     rcx, HnsRpc_QueryEndpointProperties
0x18000910d  call    ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x180009112  mov     edi, eax
0x180009114  test    rbx, rbx
0x180009117  jz      short loc_18000912A
0x180009119  mov     rdx, [rsp+48h+var_18]
0x18000911e  xor     ecx, ecx
0x180009120  mov     [rsp+48h+var_18], rcx
0x180009125  mov     [rbx], rdx
0x180009128  jmp     short loc_18000912F
0x18000912a  mov     rcx, [rsp+48h+var_18]; void *
0x18000912f  test    rcx, rcx
0x180009132  jz      short loc_180009139
0x180009134  call    MIDL_user_free
0x180009139  mov     eax, edi
0x18000913b  jmp     short loc_180009141
0x18000913d  mov     eax, dword ptr [rsp+48h+arg_0]
0x180009141  mov     rbx, [rsp+48h+arg_18]
0x180009146  add     rsp, 40h
0x18000914a  pop     rdi
0x18000914b  retn
0x18000914c  mov     r9d, 80070057h; char *
0x180009152  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009159  mov     edx, 2E5h; void *
0x18000915e  mov     rcx, rax; this
0x180009161  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009166  mov     r9d, 80004003h; char *
0x18000916c  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009173  mov     edx, 10h; void *
0x180009178  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
