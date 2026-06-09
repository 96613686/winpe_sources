# HcnModifySdnRoute(void *,ushort const *,ushort * *)

- ea: `0x180005930`
- end: `0x1800059e1`
- name: `?HcnModifySdnRoute@@YAJPEAXPEBGPEAPEAG@Z`
- size: `177`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002254`
- `0x180005930`
- `0x180007904`
- `0x180009d10`

## string_xrefs

- `0x1800059cb`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnModifySdnRoute(void *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned int v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  unsigned __int16 *v7; // rdx
  void *v8; // rcx
  __int64 result; // rax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *v12; // [rsp+40h] [rbp+8h] BYREF
  const unsigned __int16 *v13; // [rsp+48h] [rbp+10h] BYREF
  void *v14; // [rsp+58h] [rbp+20h] BYREF

  v13 = a2;
  v12 = a1;
  try
  {
    if ( !a1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x513,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v10[0]);
    if ( a3 )
      *a3 = 0;
    v14 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,unsigned short const *,unsigned short * *),void * &,unsigned short const * &,unsigned short * *>(
           HnsRpc_ModifySdnRoute,
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
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x520, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180005930  mov     [rsp+arg_10], rbx
0x180005935  mov     [rsp+arg_8], rdx
0x18000593a  mov     [rsp+arg_0], rcx
0x18000593f  push    rdi
0x180005940  sub     rsp, 30h
0x180005944  mov     rbx, r8
0x180005947  mov     rax, [rsp+38h]
0x18000594c  test    rcx, rcx
0x18000594f  jz      short loc_1800059C5
0x180005951  test    rbx, rbx
0x180005954  jz      short loc_18000595D
0x180005956  mov     qword ptr [r8], 0
0x18000595d  mov     [rsp+38h+arg_18], 0
0x180005966  lea     rax, [rsp+38h+arg_18]
0x18000596b  mov     [rsp+38h+var_18], rax
0x180005970  lea     r9, [rsp+38h+var_18]
0x180005975  lea     r8, [rsp+38h+arg_8]
0x18000597a  lea     rdx, [rsp+38h+arg_0]
0x18000597f  lea     rcx, HnsRpc_ModifySdnRoute
0x180005986  call    ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBG$$QEAPEAPEAG@Z
0x18000598b  mov     edi, eax
0x18000598d  test    rbx, rbx
0x180005990  jz      short loc_1800059A3
0x180005992  mov     rdx, [rsp+38h+arg_18]
0x180005997  xor     ecx, ecx
0x180005999  mov     [rsp+38h+arg_18], rcx
0x18000599e  mov     [rbx], rdx
0x1800059a1  jmp     short loc_1800059A8
0x1800059a3  mov     rcx, [rsp+38h+arg_18]; void *
0x1800059a8  test    rcx, rcx
0x1800059ab  jz      short loc_1800059B2
0x1800059ad  call    MIDL_user_free
0x1800059b2  mov     eax, edi
0x1800059b4  jmp     short loc_1800059BA
0x1800059b6  mov     eax, dword ptr [rsp+38h+arg_0]
0x1800059ba  mov     rbx, [rsp+38h+arg_10]
0x1800059bf  add     rsp, 30h
0x1800059c3  pop     rdi
0x1800059c4  retn
0x1800059c5  mov     r9d, 80070057h; char *
0x1800059cb  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x1800059d2  mov     edx, 513h; void *
0x1800059d7  mov     rcx, rax; this
0x1800059da  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
