# HcnModifyGuestNetworkService

- ea: `0x180008990`
- end: `0x180008a41`
- name: `HcnModifyGuestNetworkService`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002254`
- `0x180007904`
- `0x180008990`
- `0x180009d10`

## string_xrefs

- `0x180008a2b`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnModifyGuestNetworkService(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  void *v7; // rdx
  void *v8; // rcx
  __int64 result; // rax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF
  __int64 v13; // [rsp+48h] [rbp+10h] BYREF
  void *v14; // [rsp+58h] [rbp+20h] BYREF

  v13 = a2;
  v12 = a1;
  try
  {
    if ( !a1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x60F,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v10[0]);
    if ( a3 )
      *a3 = 0;
    v14 = 0;
    v4 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,unsigned short const *,unsigned short * *),void * &,unsigned short const * &,unsigned short * *>(
           HnsRpc_ModifyGuestNetworkService,
           &v12,
           &v13,
           v10,
           &v14);
    if ( a3 )
    {
      v7 = v14;
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
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x61C, v5, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180008990  mov     [rsp+arg_10], rbx
0x180008995  mov     [rsp+arg_8], rdx
0x18000899a  mov     [rsp+arg_0], rcx
0x18000899f  push    rdi
0x1800089a0  sub     rsp, 30h
0x1800089a4  mov     rbx, r8
0x1800089a7  mov     rax, [rsp+38h]
0x1800089ac  test    rcx, rcx
0x1800089af  jz      short loc_180008A25
0x1800089b1  test    rbx, rbx
0x1800089b4  jz      short loc_1800089BD
0x1800089b6  mov     qword ptr [r8], 0
0x1800089bd  mov     [rsp+38h+arg_18], 0
0x1800089c6  lea     rax, [rsp+38h+arg_18]
0x1800089cb  mov     [rsp+38h+var_18], rax
0x1800089d0  lea     r9, [rsp+38h+var_18]
0x1800089d5  lea     r8, [rsp+38h+arg_8]
0x1800089da  lea     rdx, [rsp+38h+arg_0]
0x1800089df  lea     rcx, HnsRpc_ModifyGuestNetworkService
0x1800089e6  call    ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG@ZAEAPEAXAEAPEBG$$QEAPEAPEAG@Z
0x1800089eb  mov     edi, eax
0x1800089ed  test    rbx, rbx
0x1800089f0  jz      short loc_180008A03
0x1800089f2  mov     rdx, [rsp+38h+arg_18]
0x1800089f7  xor     ecx, ecx
0x1800089f9  mov     [rsp+38h+arg_18], rcx
0x1800089fe  mov     [rbx], rdx
0x180008a01  jmp     short loc_180008A08
0x180008a03  mov     rcx, [rsp+38h+arg_18]; void *
0x180008a08  test    rcx, rcx
0x180008a0b  jz      short loc_180008A12
0x180008a0d  call    MIDL_user_free
0x180008a12  mov     eax, edi
0x180008a14  jmp     short loc_180008A1A
0x180008a16  mov     eax, dword ptr [rsp+38h+arg_0]
0x180008a1a  mov     rbx, [rsp+38h+arg_10]
0x180008a1f  add     rsp, 30h
0x180008a23  pop     rdi
0x180008a24  retn
0x180008a25  mov     r9d, 80070057h; char *
0x180008a2b  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008a32  mov     edx, 60Fh; void *
0x180008a37  mov     rcx, rax; this
0x180008a3a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
