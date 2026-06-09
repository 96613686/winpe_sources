# HcnEnumerateNamespaces

- ea: `0x180008730`
- end: `0x1800087e5`
- name: `HcnEnumerateNamespaces`
- size: `181`
- prototype: `HRESULT __stdcall(PCWSTR Query, PWSTR *Namespaces, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f88`
- `0x180007904`
- `0x180008730`
- `0x180009d10`

## string_xrefs

- `0x1800087d2`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnEnumerateNamespaces(PCWSTR Query, PWSTR *Namespaces, PWSTR *ErrorRecord)
{
  HRESULT v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  WCHAR *v7; // rdx
  void *v8; // rcx
  HRESULT result; // eax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PCWSTR v12; // [rsp+40h] [rbp+8h] BYREF
  PWSTR *v13; // [rsp+48h] [rbp+10h] BYREF
  void *v14; // [rsp+58h] [rbp+20h] BYREF

  v13 = Namespaces;
  v12 = Query;
  try
  {
    if ( !Namespaces )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v10[0]);
    *Namespaces = 0;
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v14 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,unsigned short const *,unsigned short * *,unsigned short * *),unsigned short const * &,unsigned short * * &,unsigned short * *>(
           HnsRpc_EnumerateNamespaces,
           &v12,
           &v13,
           v10,
           &v14);
    if ( ErrorRecord )
    {
      v7 = (WCHAR *)v14;
      v8 = 0;
      v14 = 0;
      *ErrorRecord = v7;
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x152, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180008730  mov     [rsp+arg_10], rbx
0x180008735  mov     [rsp+arg_8], rdx
0x18000873a  mov     [rsp+arg_0], rcx
0x18000873f  push    rdi
0x180008740  sub     rsp, 30h
0x180008744  mov     rbx, r8
0x180008747  mov     rcx, [rsp+38h]; this
0x18000874c  test    rdx, rdx
0x18000874f  jz      short loc_1800087CC
0x180008751  mov     qword ptr [rdx], 0
0x180008758  test    rbx, rbx
0x18000875b  jz      short loc_180008764
0x18000875d  mov     qword ptr [r8], 0
0x180008764  mov     [rsp+38h+arg_18], 0
0x18000876d  lea     rax, [rsp+38h+arg_18]
0x180008772  mov     [rsp+38h+var_18], rax
0x180008777  lea     r9, [rsp+38h+var_18]
0x18000877c  lea     r8, [rsp+38h+arg_8]
0x180008781  lea     rdx, [rsp+38h+arg_0]
0x180008786  lea     rcx, HnsRpc_EnumerateNamespaces
0x18000878d  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x180008792  mov     edi, eax
0x180008794  test    rbx, rbx
0x180008797  jz      short loc_1800087AA
0x180008799  mov     rdx, [rsp+38h+arg_18]
0x18000879e  xor     ecx, ecx
0x1800087a0  mov     [rsp+38h+arg_18], rcx
0x1800087a5  mov     [rbx], rdx
0x1800087a8  jmp     short loc_1800087AF
0x1800087aa  mov     rcx, [rsp+38h+arg_18]; void *
0x1800087af  test    rcx, rcx
0x1800087b2  jz      short loc_1800087B9
0x1800087b4  call    MIDL_user_free
0x1800087b9  mov     eax, edi
0x1800087bb  jmp     short loc_1800087C1
0x1800087bd  mov     eax, dword ptr [rsp+38h+arg_8]
0x1800087c1  mov     rbx, [rsp+38h+arg_10]
0x1800087c6  add     rsp, 30h
0x1800087ca  pop     rdi
0x1800087cb  retn
0x1800087cc  mov     r9d, 80004003h; char *
0x1800087d2  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x1800087d9  mov     edx, 10h; void *
0x1800087de  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
