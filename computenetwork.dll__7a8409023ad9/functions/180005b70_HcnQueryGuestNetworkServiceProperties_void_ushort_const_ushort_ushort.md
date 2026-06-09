# HcnQueryGuestNetworkServiceProperties(void *,ushort const *,ushort * *,ushort * *)

- ea: `0x180005b70`
- end: `0x180005c5f`
- name: `?HcnQueryGuestNetworkServiceProperties@@YAJPEAXPEBGPEAPEAG2@Z`
- size: `239`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002188`
- `0x180005b70`
- `0x180007904`
- `0x180009d10`

## string_xrefs

- `0x180005c32`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180005c4c`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnQueryGuestNetworkServiceProperties(
        void *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  unsigned int v5; // edi
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned __int16 *v8; // rdx
  void *v9; // rcx
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-28h]
  void *v12; // [rsp+30h] [rbp-18h] BYREF
  void **v13; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *v15; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 *v16; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int16 **v17; // [rsp+60h] [rbp+18h] BYREF

  v17 = a3;
  v16 = a2;
  v15 = a1;
  try
  {
    if ( !a1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x637,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v11);
    if ( a4 )
      *a4 = 0;
    if ( !a3 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v11);
    *a3 = 0;
    v12 = 0;
    v13 = &v12;
    v5 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void *,unsigned short const *,unsigned short * *,unsigned short * *),void * &,unsigned short const * &,unsigned short * * &,unsigned short * *>(
           (unsigned int)HnsRpc_QueryGuestNetworkServiceProperties,
           (unsigned int)&v15,
           (unsigned int)&v16,
           (unsigned int)&v17,
           (__int64)&v13);
    if ( a4 )
    {
      v8 = (unsigned __int16 *)v12;
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
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x646, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180005b70  mov     rax, rsp
0x180005b73  mov     [rax+20h], rbx
0x180005b77  mov     [rax+18h], r8
0x180005b7b  mov     [rax+10h], rdx
0x180005b7f  mov     [rax+8], rcx
0x180005b83  push    rdi
0x180005b84  sub     rsp, 40h
0x180005b88  mov     rbx, r9
0x180005b8b  mov     rax, [rsp+48h]
0x180005b90  test    rcx, rcx
0x180005b93  jz      loc_180005C2C
0x180005b99  test    rbx, rbx
0x180005b9c  jz      short loc_180005BA5
0x180005b9e  mov     qword ptr [r9], 0
0x180005ba5  mov     rcx, [rsp+48h]; this
0x180005baa  test    r8, r8
0x180005bad  jz      loc_180005C46
0x180005bb3  mov     qword ptr [r8], 0
0x180005bba  mov     [rsp+48h+var_18], 0
0x180005bc3  lea     rax, [rsp+48h+var_18]
0x180005bc8  mov     [rsp+48h+var_10], rax
0x180005bcd  lea     rax, [rsp+48h+var_10]
0x180005bd2  mov     qword ptr [rsp+48h+var_28], rax
0x180005bd7  lea     r9, [rsp+48h+arg_10]
0x180005bdc  lea     r8, [rsp+48h+arg_8]
0x180005be1  lea     rdx, [rsp+48h+arg_0]
0x180005be6  lea     rcx, HnsRpc_QueryGuestNetworkServiceProperties
0x180005bed  call    ??$InvokeRpcFunction@P6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAGPEAPEAG@RpcHelper@Client@Hns@@YA?A_TP6AJPEAXPEBGPEAPEAG2@ZAEAPEAXAEAPEBGAEAPEAPEAG$$QEAPEAPEAG@Z
0x180005bf2  mov     edi, eax
0x180005bf4  test    rbx, rbx
0x180005bf7  jz      short loc_180005C0A
0x180005bf9  mov     rdx, [rsp+48h+var_18]
0x180005bfe  xor     ecx, ecx
0x180005c00  mov     [rsp+48h+var_18], rcx
0x180005c05  mov     [rbx], rdx
0x180005c08  jmp     short loc_180005C0F
0x180005c0a  mov     rcx, [rsp+48h+var_18]; void *
0x180005c0f  test    rcx, rcx
0x180005c12  jz      short loc_180005C19
0x180005c14  call    MIDL_user_free
0x180005c19  mov     eax, edi
0x180005c1b  jmp     short loc_180005C21
0x180005c1d  mov     eax, dword ptr [rsp+48h+arg_0]
0x180005c21  mov     rbx, [rsp+48h+arg_18]
0x180005c26  add     rsp, 40h
0x180005c2a  pop     rdi
0x180005c2b  retn
0x180005c2c  mov     r9d, 80070057h; char *
0x180005c32  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005c39  mov     edx, 637h; void *
0x180005c3e  mov     rcx, rax; this
0x180005c41  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005c46  mov     r9d, 80004003h; char *
0x180005c4c  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005c53  mov     edx, 10h; void *
0x180005c58  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
