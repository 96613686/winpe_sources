# HcnEnumerateEndpoints

- ea: `0x1800084a0`
- end: `0x180008555`
- name: `HcnEnumerateEndpoints`
- size: `181`
- prototype: `HRESULT __stdcall(PCWSTR Query, PWSTR *Endpoints, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f88`
- `0x180007904`
- `0x1800084a0`
- `0x180009d10`

## string_xrefs

- `0x180008542`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall HcnEnumerateEndpoints(PCWSTR Query, PWSTR *Endpoints, PWSTR *ErrorRecord)
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

  v13 = Endpoints;
  v12 = Query;
  try
  {
    if ( !Endpoints )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v10[0]);
    *Endpoints = 0;
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v14 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,unsigned short const *,unsigned short * *,unsigned short * *),unsigned short const * &,unsigned short * * &,unsigned short * *>(
           HnsRpc_EnumerateEndpoints,
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
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x254, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800084a0  mov     [rsp+arg_10], rbx
0x1800084a5  mov     [rsp+arg_8], rdx
0x1800084aa  mov     [rsp+arg_0], rcx
0x1800084af  push    rdi
0x1800084b0  sub     rsp, 30h
0x1800084b4  mov     rbx, r8
0x1800084b7  mov     rcx, [rsp+38h]; this
0x1800084bc  test    rdx, rdx
0x1800084bf  jz      short loc_18000853C
0x1800084c1  mov     qword ptr [rdx], 0
0x1800084c8  test    rbx, rbx
0x1800084cb  jz      short loc_1800084D4
0x1800084cd  mov     qword ptr [r8], 0
0x1800084d4  mov     [rsp+38h+arg_18], 0
0x1800084dd  lea     rax, [rsp+38h+arg_18]
0x1800084e2  mov     [rsp+38h+var_18], rax
0x1800084e7  lea     r9, [rsp+38h+var_18]
0x1800084ec  lea     r8, [rsp+38h+arg_8]
0x1800084f1  lea     rdx, [rsp+38h+arg_0]
0x1800084f6  lea     rcx, HnsRpc_EnumerateEndpoints
0x1800084fd  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x180008502  mov     edi, eax
0x180008504  test    rbx, rbx
0x180008507  jz      short loc_18000851A
0x180008509  mov     rdx, [rsp+38h+arg_18]
0x18000850e  xor     ecx, ecx
0x180008510  mov     [rsp+38h+arg_18], rcx
0x180008515  mov     [rbx], rdx
0x180008518  jmp     short loc_18000851F
0x18000851a  mov     rcx, [rsp+38h+arg_18]; void *
0x18000851f  test    rcx, rcx
0x180008522  jz      short loc_180008529
0x180008524  call    MIDL_user_free
0x180008529  mov     eax, edi
0x18000852b  jmp     short loc_180008531
0x18000852d  mov     eax, dword ptr [rsp+38h+arg_8]
0x180008531  mov     rbx, [rsp+38h+arg_10]
0x180008536  add     rsp, 30h
0x18000853a  pop     rdi
0x18000853b  retn
0x18000853c  mov     r9d, 80004003h; char *
0x180008542  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008549  mov     edx, 10h; void *
0x18000854e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
