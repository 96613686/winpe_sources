# HcnQueryNamespaceProperties

- ea: `0x180009490`
- end: `0x18000957f`
- name: `HcnQueryNamespaceProperties`
- size: `239`
- prototype: `HRESULT __stdcall(HCN_NAMESPACE Namespace, PCWSTR Query, PWSTR *Properties, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002188`
- `0x180007904`
- `0x180009490`
- `0x180009d10`

## string_xrefs

- `0x180009552`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x18000956c`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnQueryNamespaceProperties(
        HCN_NAMESPACE Namespace,
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
  HCN_NAMESPACE v15; // [rsp+50h] [rbp+8h] BYREF
  PCWSTR v16; // [rsp+58h] [rbp+10h] BYREF
  PWSTR *v17; // [rsp+60h] [rbp+18h] BYREF

  v17 = Properties;
  v16 = Query;
  v15 = Namespace;
  try
  {
    if ( !Namespace )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1E0,
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
           (unsigned int)HnsRpc_QueryNamespaceProperties,
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x1EF, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180009490  mov     rax, rsp
0x180009493  mov     [rax+20h], rbx
0x180009497  mov     [rax+18h], r8
0x18000949b  mov     [rax+10h], rdx
0x18000949f  mov     [rax+8], rcx
0x1800094a3  push    rdi
0x1800094a4  sub     rsp, 40h
0x1800094a8  mov     rbx, r9
0x1800094ab  mov     rax, [rsp+48h]
0x1800094b0  test    rcx, rcx
0x1800094b3  jz      loc_18000954C
0x1800094b9  mov     rcx, [rsp+48h]; this
0x1800094be  test    r8, r8
0x1800094c1  jz      loc_180009566
0x1800094c7  mov     qword ptr [r8], 0
0x1800094ce  test    rbx, rbx
0x1800094d1  jz      short loc_1800094DA
0x1800094d3  mov     qword ptr [r9], 0
0x1800094da  mov     [rsp+48h+var_18], 0
0x1800094e3  lea     rax, [rsp+48h+var_18]
0x1800094e8  mov     [rsp+48h+var_10], rax
0x1800094ed  lea     rax, [rsp+48h+var_10]
0x1800094f2  mov     qword ptr [rsp+48h+var_28], rax
0x1800094f7  lea     r9, [rsp+48h+arg_10]
0x1800094fc  lea     r8, [rsp+48h+arg_8]
0x180009501  lea     rdx, [rsp+48h+arg_0]
0x180009506  lea     rcx, HnsRpc_QueryNamespaceProperties
0x18000950d  call    ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x180009512  mov     edi, eax
0x180009514  test    rbx, rbx
0x180009517  jz      short loc_18000952A
0x180009519  mov     rdx, [rsp+48h+var_18]
0x18000951e  xor     ecx, ecx
0x180009520  mov     [rsp+48h+var_18], rcx
0x180009525  mov     [rbx], rdx
0x180009528  jmp     short loc_18000952F
0x18000952a  mov     rcx, [rsp+48h+var_18]; void *
0x18000952f  test    rcx, rcx
0x180009532  jz      short loc_180009539
0x180009534  call    MIDL_user_free
0x180009539  mov     eax, edi
0x18000953b  jmp     short loc_180009541
0x18000953d  mov     eax, dword ptr [rsp+48h+arg_0]
0x180009541  mov     rbx, [rsp+48h+arg_18]
0x180009546  add     rsp, 40h
0x18000954a  pop     rdi
0x18000954b  retn
0x18000954c  mov     r9d, 80070057h; char *
0x180009552  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009559  mov     edx, 1E0h; void *
0x18000955e  mov     rcx, rax; this
0x180009561  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009566  mov     r9d, 80004003h; char *
0x18000956c  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009573  mov     edx, 10h; void *
0x180009578  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
