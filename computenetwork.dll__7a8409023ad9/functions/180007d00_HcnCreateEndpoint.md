# HcnCreateEndpoint

- ea: `0x180007d00`
- end: `0x180007e81`
- name: `HcnCreateEndpoint`
- size: `385`
- prototype: `HRESULT __stdcall(HCN_NETWORK Network, const GUID *const Id, PCWSTR Settings, PHCN_ENDPOINT Endpoint, PWSTR *ErrorRecord)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002544`
- `0x180007904`
- `0x180007d00`
- `0x180009d10`
- `0x18000b8c4`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007dce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180007dce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007d7e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180007d7e`

## string_xrefs

- `0x180007e54`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180007e6e`: `onecore\vm\dv\net\hns\computenetwork\src\Common.h`

## pseudocode

```c
HRESULT __stdcall HcnCreateEndpoint(
        HCN_NETWORK Network,
        const GUID *const Id,
        PCWSTR Settings,
        PHCN_ENDPOINT Endpoint,
        PWSTR *ErrorRecord)
{
  int v5; // esi
  PWSTR *v6; // rdi
  RTL_SRWLOCK *v7; // rbx
  int v8; // ecx
  HRESULT v9; // esi
  unsigned int v10; // r8d
  const char *v11; // r9
  volatile signed __int32 *v12; // rbx
  WCHAR *v13; // rax
  void *v14; // rcx
  HRESULT result; // eax
  int v16; // [rsp+20h] [rbp-68h]
  void *v17; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v18[2]; // [rsp+48h] [rbp-40h] BYREF
  _BYTE v19[8]; // [rsp+58h] [rbp-30h] BYREF
  volatile signed __int32 *v20; // [rsp+60h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  HCN_NETWORK v22; // [rsp+90h] [rbp+8h] BYREF
  PCWSTR v23; // [rsp+A0h] [rbp+18h] BYREF
  PHCN_ENDPOINT v24; // [rsp+A8h] [rbp+20h] BYREF

  v24 = Endpoint;
  v23 = Settings;
  v22 = Network;
  try
  {
    v5 = (int)Id;
    if ( !Network )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x26F,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v16);
    if ( !Endpoint )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\Common.h",
        (const char *)0x80004003LL,
        v16);
    *Endpoint = 0;
    v6 = ErrorRecord;
    if ( ErrorRecord )
      *ErrorRecord = 0;
    v17 = 0;
    v18[0] = &v17;
    v7 = (RTL_SRWLOCK *)(*(_QWORD *)Hns::Client::RpcHelper::GetRpcClient(v19) + 8LL);
    AcquireSRWLockShared(v7);
    v18[1] = v7;
    v9 = Rpc::RpcClient::InvokeRpcFunctionInternal<long (*)(void *,_GUID const &,unsigned short const *,void * *,unsigned short * *),void * &,_GUID const &,unsigned short const * &,void * * &,unsigned short * *>(
           v8,
           (unsigned int)HnsRpc_CreateEndpoint,
           (unsigned int)&v22,
           v5,
           (__int64)&v23,
           (__int64)&v24,
           (__int64)v18);
    if ( v7 )
      ReleaseSRWLockShared(v7);
    v12 = v20;
    if ( v20 )
    {
      if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    if ( v6 )
    {
      v13 = (WCHAR *)v17;
      v14 = 0;
      v17 = 0;
      *v6 = v13;
    }
    else
    {
      v14 = v17;
    }
    if ( v14 )
      MIDL_user_free(v14);
    result = v9;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x27F, v10, v11);
  }
  return result;
}

```

## disassembly

```asm
0x180007d00  mov     [rsp+arg_18], r9
0x180007d05  mov     [rsp+arg_10], r8
0x180007d0a  mov     [rsp+arg_0], rcx
0x180007d0f  push    rbx
0x180007d10  push    rsi
0x180007d11  push    rdi
0x180007d12  sub     rsp, 70h
0x180007d16  mov     rsi, rdx
0x180007d19  mov     rax, [rsp+88h]
0x180007d21  test    rcx, rcx
0x180007d24  jz      loc_180007E4E
0x180007d2a  mov     rcx, [rsp+88h]; this
0x180007d32  test    r9, r9
0x180007d35  jz      loc_180007E68
0x180007d3b  mov     qword ptr [r9], 0
0x180007d42  mov     rdi, [rsp+88h+ErrorRecord]
0x180007d4a  test    rdi, rdi
0x180007d4d  jz      short loc_180007D56
0x180007d4f  mov     qword ptr [rdi], 0
0x180007d56  mov     [rsp+88h+var_48], 0
0x180007d5f  lea     rax, [rsp+88h+var_48]
0x180007d64  mov     [rsp+88h+var_40], rax
0x180007d69  lea     rcx, [rsp+88h+var_30]
0x180007d6e  call    ?GetRpcClient@RpcHelper@Client@Hns@@YA?AV?$shared_ptr@VRpcClient@Rpc@@@std@@XZ; Hns::Client::RpcHelper::GetRpcClient(void)
0x180007d73  nop
0x180007d74  mov     rbx, [rax]
0x180007d77  add     rbx, 8
0x180007d7b  mov     rcx, rbx; SRWLock
0x180007d7e  call    cs:__imp_AcquireSRWLockShared
0x180007d84  mov     [rsp+88h+var_38], rbx
0x180007d89  lea     rax, [rsp+88h+var_40]
0x180007d8e  mov     [rsp+88h+var_58], rax
0x180007d93  lea     rax, [rsp+88h+arg_18]
0x180007d9b  mov     [rsp+88h+var_60], rax
0x180007da0  lea     rax, [rsp+88h+arg_10]
0x180007da8  mov     [rsp+88h+var_68], rax
0x180007dad  mov     r9, rsi
0x180007db0  lea     r8, [rsp+88h+arg_0]
0x180007db8  lea     rdx, HnsRpc_CreateEndpoint
0x180007dbf  call    ??$InvokeRpcFunctionInternal@P6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@ZAEAPEAXAEBU1@AEAPEBGAEAPEAPEAXPEAPEAG@RpcClient@Rpc@@AEAA?A_TP6AJPEAXAEBU_GUID@@PEBGPEAPEAXPEAPEAG@ZAEAPEAX1AEAPEBGAEAPEAPEAX$$QEAPEAPEAG@Z
0x180007dc4  mov     esi, eax
0x180007dc6  test    rbx, rbx
0x180007dc9  jz      short loc_180007DD5
0x180007dcb  mov     rcx, rbx; SRWLock
0x180007dce  call    cs:__imp_ReleaseSRWLockShared
0x180007dd4  nop
0x180007dd5  mov     rbx, [rsp+88h+var_28]
0x180007dda  test    rbx, rbx
0x180007ddd  jz      short loc_180007E16
0x180007ddf  or      eax, 0FFFFFFFFh
0x180007de2  lock xadd [rbx+8], eax
0x180007de7  cmp     eax, 1
0x180007dea  jnz     short loc_180007E16
0x180007dec  mov     rax, [rbx]
0x180007def  mov     rcx, rbx
0x180007df2  mov     rax, [rax]
0x180007df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dfa  or      eax, 0FFFFFFFFh
0x180007dfd  lock xadd [rbx+0Ch], eax
0x180007e02  cmp     eax, 1
0x180007e05  jnz     short loc_180007E16
0x180007e07  mov     rax, [rbx]
0x180007e0a  mov     rcx, rbx
0x180007e0d  mov     rax, [rax+8]
0x180007e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e16  test    rdi, rdi
0x180007e19  jz      short loc_180007E2C
0x180007e1b  mov     rax, [rsp+88h+var_48]
0x180007e20  xor     ecx, ecx
0x180007e22  mov     [rsp+88h+var_48], rcx
0x180007e27  mov     [rdi], rax
0x180007e2a  jmp     short loc_180007E31
0x180007e2c  mov     rcx, [rsp+88h+var_48]; void *
0x180007e31  test    rcx, rcx
0x180007e34  jz      short loc_180007E3B
0x180007e36  call    MIDL_user_free
0x180007e3b  mov     eax, esi
0x180007e3d  jmp     short loc_180007E46
0x180007e3f  mov     eax, dword ptr [rsp+88h+arg_0]
0x180007e46  add     rsp, 70h
0x180007e4a  pop     rdi
0x180007e4b  pop     rsi
0x180007e4c  pop     rbx
0x180007e4d  retn
0x180007e4e  mov     r9d, 80070057h; char *
0x180007e54  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180007e5b  mov     edx, 26Fh; void *
0x180007e60  mov     rcx, rax; this
0x180007e63  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180007e68  mov     r9d, 80004003h; char *
0x180007e6e  lea     r8, aOnecoreVmDvNet_0; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180007e75  mov     edx, 10h; void *
0x180007e7a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
