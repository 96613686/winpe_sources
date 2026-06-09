# HcnDeleteSdnRoute(_GUID const &,ushort * *)

- ea: `0x180005720`
- end: `0x18000579b`
- name: `?HcnDeleteSdnRoute@@YAJAEBU_GUID@@PEAPEAG@Z`
- size: `123`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002978`
- `0x180005720`
- `0x180009d10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnDeleteSdnRoute(const struct _GUID *a1, unsigned __int16 **a2)
{
  unsigned int v3; // edi
  unsigned int v4; // r8d
  const char *v5; // r9
  unsigned __int16 *v6; // rdx
  void *v7; // rcx
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v10; // [rsp+38h] [rbp+10h] BYREF
  void **v11; // [rsp+40h] [rbp+18h]

  if ( a2 )
    *a2 = 0;
  v10 = 0;
  v11 = &v10;
  try
  {
    v3 = Hns::Client::RpcHelper::InvokeRpcFunctionWithBinding<long (*)(void *,_GUID const &,unsigned short * *),_GUID const &,unsigned short * *>();
    if ( a2 )
    {
      v6 = (unsigned __int16 *)v10;
      v7 = 0;
      v10 = 0;
      *a2 = v6;
    }
    else
    {
      v7 = v10;
    }
    if ( v7 )
      MIDL_user_free(v7);
    result = v3;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x56A, v4, v5);
  }
  return result;
}

```

## disassembly

```asm
0x180005720  mov     [rsp+arg_0], rbx
0x180005725  push    rdi
0x180005726  sub     rsp, 20h
0x18000572a  mov     rbx, rdx
0x18000572d  test    rdx, rdx
0x180005730  jz      short loc_180005739
0x180005732  mov     qword ptr [rdx], 0
0x180005739  mov     [rsp+28h+arg_8], 0
0x180005742  lea     rax, [rsp+28h+arg_8]
0x180005747  mov     [rsp+28h+arg_10], rax
0x18000574c  lea     r8, [rsp+28h+arg_10]
0x180005751  mov     rdx, rcx
0x180005754  lea     rcx, HnsRpc_DeleteSdnRoute
0x18000575b  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXAEBU_GUID@@PEAPEAG@ZAEBU1@PEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXAEBU_GUID@@PEAPEAG@Z1$$QEAPEAPEAG@Z
0x180005760  mov     edi, eax
0x180005762  test    rbx, rbx
0x180005765  jz      short loc_180005778
0x180005767  mov     rdx, [rsp+28h+arg_8]
0x18000576c  xor     ecx, ecx
0x18000576e  mov     [rsp+28h+arg_8], rcx
0x180005773  mov     [rbx], rdx
0x180005776  jmp     short loc_18000577D
0x180005778  mov     rcx, [rsp+28h+arg_8]; void *
0x18000577d  test    rcx, rcx
0x180005780  jz      short loc_180005787
0x180005782  call    MIDL_user_free
0x180005787  mov     eax, edi
0x180005789  jmp     short loc_18000578F
0x18000578b  mov     eax, dword ptr [rsp+28h+arg_8]
0x18000578f  mov     rbx, [rsp+28h+arg_0]
0x180005794  add     rsp, 20h
0x180005798  pop     rdi
0x180005799  retn
```
