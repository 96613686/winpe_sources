# HcnEnumerateSdnRoutes(ushort const *,ushort * *,ushort * *)

- ea: `0x180005870`
- end: `0x180005925`
- name: `?HcnEnumerateSdnRoutes@@YAJPEBGPEAPEAG1@Z`
- size: `181`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f88`
- `0x180005870`
- `0x180007904`
- `0x180009d10`

## string_xrefs

- `0x180005912`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnEnumerateSdnRoutes(const unsigned __int16 *a1, unsigned __int16 **a2, unsigned __int16 **a3)
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
           HnsRpc_EnumerateSdnRoutes,
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
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x4B1, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180005870  mov     [rsp+arg_10], rbx
0x180005875  mov     [rsp+arg_8], rdx
0x18000587a  mov     [rsp+arg_0], rcx
0x18000587f  push    rdi
0x180005880  sub     rsp, 30h
0x180005884  mov     rbx, r8
0x180005887  mov     rcx, [rsp+38h]; this
0x18000588c  test    rdx, rdx
0x18000588f  jz      short loc_18000590C
0x180005891  mov     qword ptr [rdx], 0
0x180005898  test    rbx, rbx
0x18000589b  jz      short loc_1800058A4
0x18000589d  mov     qword ptr [r8], 0
0x1800058a4  mov     [rsp+38h+arg_18], 0
0x1800058ad  lea     rax, [rsp+38h+arg_18]
0x1800058b2  mov     [rsp+38h+var_18], rax
0x1800058b7  lea     r9, [rsp+38h+var_18]
0x1800058bc  lea     r8, [rsp+38h+arg_8]
0x1800058c1  lea     rdx, [rsp+38h+arg_0]
0x1800058c6  lea     rcx, HnsRpc_EnumerateSdnRoutes
0x1800058cd  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x1800058d2  mov     edi, eax
0x1800058d4  test    rbx, rbx
0x1800058d7  jz      short loc_1800058EA
0x1800058d9  mov     rdx, [rsp+38h+arg_18]
0x1800058de  xor     ecx, ecx
0x1800058e0  mov     [rsp+38h+arg_18], rcx
0x1800058e5  mov     [rbx], rdx
0x1800058e8  jmp     short loc_1800058EF
0x1800058ea  mov     rcx, [rsp+38h+arg_18]; void *
0x1800058ef  test    rcx, rcx
0x1800058f2  jz      short loc_1800058F9
0x1800058f4  call    MIDL_user_free
0x1800058f9  mov     eax, edi
0x1800058fb  jmp     short loc_180005901
0x1800058fd  mov     eax, dword ptr [rsp+38h+arg_8]
0x180005901  mov     rbx, [rsp+38h+arg_10]
0x180005906  add     rsp, 30h
0x18000590a  pop     rdi
0x18000590b  retn
0x18000590c  mov     r9d, 80004003h; char *
0x180005912  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005919  mov     edx, 10h; void *
0x18000591e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
