# HcnCreateNamespace

- ea: `0x180008030`
- end: `0x1800080f1`
- name: `HcnCreateNamespace`
- size: `193`
- prototype: `HRESULT __stdcall(const GUID *const Id, PCWSTR Settings, PHCN_NAMESPACE Namespace, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002c38`
- `0x180007904`
- `0x180008030`
- `0x180009d10`

## string_xrefs

- `0x1800080de`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnCreateNamespace(
        const GUID *const Id,
        PCWSTR Settings,
        PHCN_NAMESPACE Namespace,
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
  PCWSTR v15; // [rsp+58h] [rbp+10h] BYREF
  PHCN_NAMESPACE v16; // [rsp+60h] [rbp+18h] BYREF

  v16 = Namespace;
  v15 = Settings;
  try
  {
    if ( !Namespace )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v11);
    *Namespace = 0;
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v12 = 0;
    v13 = &v12;
    v5 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,unsigned short const *,void * *,unsigned short * *),_GUID const &,unsigned short const * &,void * * &,unsigned short * *>(
           HnsRpc_CreateNamespace,
           Id,
           &v15,
           &v16,
           &v13);
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x17A, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180008030  mov     [rsp+arg_0], rbx
0x180008035  mov     [rsp+arg_10], r8
0x18000803a  mov     [rsp+arg_8], rdx
0x18000803f  push    rdi
0x180008040  sub     rsp, 40h
0x180008044  mov     rbx, r9
0x180008047  mov     rdx, rcx
0x18000804a  mov     rcx, [rsp+48h]; this
0x18000804f  test    r8, r8
0x180008052  jz      loc_1800080D8
0x180008058  mov     qword ptr [r8], 0
0x18000805f  test    rbx, rbx
0x180008062  jz      short loc_18000806B
0x180008064  mov     qword ptr [r9], 0
0x18000806b  mov     [rsp+48h+var_18], 0
0x180008074  lea     rax, [rsp+48h+var_18]
0x180008079  mov     [rsp+48h+var_10], rax
0x18000807e  lea     rax, [rsp+48h+var_10]
0x180008083  mov     qword ptr [rsp+48h+var_28], rax
0x180008088  lea     r9, [rsp+48h+arg_10]
0x18000808d  lea     r8, [rsp+48h+arg_8]
0x180008092  lea     rcx, HnsRpc_CreateNamespace
0x180008099  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@ZAEBU1@AEAPEBGAEAPEAPEAXPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@Z1AEAPEBGAEAPEAPEAX$$QEAPEAPEAG@Z
0x18000809e  mov     edi, eax
0x1800080a0  test    rbx, rbx
0x1800080a3  jz      short loc_1800080B6
0x1800080a5  mov     rdx, [rsp+48h+var_18]
0x1800080aa  xor     ecx, ecx
0x1800080ac  mov     [rsp+48h+var_18], rcx
0x1800080b1  mov     [rbx], rdx
0x1800080b4  jmp     short loc_1800080BB
0x1800080b6  mov     rcx, [rsp+48h+var_18]; void *
0x1800080bb  test    rcx, rcx
0x1800080be  jz      short loc_1800080C5
0x1800080c0  call    MIDL_user_free
0x1800080c5  mov     eax, edi
0x1800080c7  jmp     short loc_1800080CD
0x1800080c9  mov     eax, dword ptr [rsp+48h+arg_10]
0x1800080cd  mov     rbx, [rsp+48h+arg_0]
0x1800080d2  add     rsp, 40h
0x1800080d6  pop     rdi
0x1800080d7  retn
0x1800080d8  mov     r9d, 80004003h; char *
0x1800080de  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x1800080e5  mov     edx, 10h; void *
0x1800080ea  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
