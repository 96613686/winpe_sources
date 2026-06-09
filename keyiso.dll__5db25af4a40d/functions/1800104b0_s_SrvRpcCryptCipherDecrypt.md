# s_SrvRpcCryptCipherDecrypt

- ea: `0x1800104b0`
- end: `0x180010652`
- name: `s_SrvRpcCryptCipherDecrypt`
- size: `418`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, __int64, __int64, __int64, __int64, int, __int64, __int64, int, _DWORD *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x18000d0ac`
- `0x180010398`
- `0x1800104b0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180010559`
- `RPCRT4!RpcImpersonateClient` at `0x180010559`
- `RPCRT4!RpcRevertToSelf` at `0x180010639`
- `RPCRT4!RpcRevertToSelf` at `0x180010639`

## string_xrefs

- `0x18001051b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010569`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800105f8`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180010617`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptCipherDecrypt(
        RPC_BINDING_HANDLE BindingHandle,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        _DWORD *a10,
        int a11)
{
  unsigned int v15; // ebx
  __int64 v16; // r9
  __int64 v17; // rcx
  int v18; // eax
  unsigned int v19; // eax
  int v20; // eax
  _OWORD v22[2]; // [rsp+68h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+88h] [rbp-A0h]
  _DWORD v24[38]; // [rsp+90h] [rbp-98h] BYREF

  memset(v22, 0, sizeof(v22));
  v23 = 0;
  memset_0(v24, 0, 0x58u);
  if ( !a10 )
  {
    v15 = -2146893785;
    v16 = 1161;
    v17 = 2148073511LL;
LABEL_3:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", v16);
    return v15;
  }
  v18 = UnpackCipherPaddingInfo(a7, (__int64)v22, v24);
  v15 = v18;
  if ( v18 < 0 )
  {
    v16 = 1175;
    v17 = (unsigned int)v18;
    goto LABEL_3;
  }
  v19 = RpcImpersonateClient(BindingHandle);
  if ( v19 )
  {
    DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1184);
    return (unsigned int)-2146893792;
  }
  else
  {
    *a10 = 0;
    v20 = off_180025080(a2, a3, a4, a5, a6, (__int64)v22, a8, a9, (__int64)a10, a11);
    v15 = v20;
    if ( v20 < 0 )
      DebugTraceError(
        (unsigned int)v20,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        1206);
    RpcRevertToSelf();
  }
  return v15;
}

```

## disassembly

```asm
0x1800104b0  push    rbx
0x1800104b2  push    rsi
0x1800104b3  push    rdi
0x1800104b4  push    r12
0x1800104b6  push    r14
0x1800104b8  push    r15
0x1800104ba  sub     rsp, 0F8h
0x1800104c1  mov     r14, r9
0x1800104c4  mov     r15, r8
0x1800104c7  mov     r12, rdx
0x1800104ca  mov     rdi, rcx
0x1800104cd  xorps   xmm0, xmm0
0x1800104d0  xor     eax, eax
0x1800104d2  movups  [rsp+128h+var_C0], xmm0
0x1800104d7  movups  [rsp+128h+var_B0], xmm0
0x1800104dc  mov     [rsp+128h+var_A0], rax
0x1800104e4  xor     edx, edx; Val
0x1800104e6  lea     r8d, [rax+58h]; Size
0x1800104ea  lea     rcx, [rsp+128h+var_98]; void *
0x1800104f2  call    memset_0
0x1800104f7  mov     rsi, [rsp+128h+arg_48]
0x1800104ff  test    rsi, rsi
0x180010502  jnz     short loc_18001052C
0x180010504  mov     ebx, 80090027h
0x180010509  mov     r9d, 489h
0x18001050f  mov     ecx, 80090027h
0x180010514  lea     rdx, aStatus; "Status"
0x18001051b  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010522  call    DebugTraceError
0x180010527  jmp     loc_18001063F
0x18001052c  lea     r8, [rsp+128h+var_98]
0x180010534  lea     rdx, [rsp+128h+var_C0]
0x180010539  mov     rcx, [rsp+128h+arg_30]
0x180010541  call    _UnpackCipherPaddingInfo
0x180010546  mov     ebx, eax
0x180010548  test    eax, eax
0x18001054a  jns     short loc_180010556
0x18001054c  mov     r9d, 497h
0x180010552  mov     ecx, eax
0x180010554  jmp     short loc_180010514
0x180010556  mov     rcx, rdi; BindingHandle
0x180010559  call    cs:__imp_RpcImpersonateClient
0x18001055f  test    eax, eax
0x180010561  jz      short loc_180010588
0x180010563  mov     r9d, 4A0h
0x180010569  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010570  lea     rdx, aStatus; "Status"
0x180010577  mov     ecx, eax
0x180010579  call    DebugTraceError
0x18001057e  mov     ebx, 80090020h
0x180010583  jmp     loc_18001063F
0x180010588  mov     dword ptr [rsi], 0
0x18001058e  mov     ecx, [rsp+128h+arg_50]
0x180010595  mov     [rsp+128h+var_E0], ecx
0x180010599  mov     [rsp+128h+var_E8], rsi
0x18001059e  mov     ecx, [rsp+128h+arg_40]
0x1800105a5  mov     [rsp+128h+var_F0], ecx
0x1800105a9  mov     rcx, [rsp+128h+arg_38]
0x1800105b1  mov     [rsp+128h+var_F8], rcx
0x1800105b6  lea     rax, [rsp+128h+var_C0]
0x1800105bb  mov     [rsp+128h+var_100], rax
0x1800105c0  mov     ecx, [rsp+128h+arg_28]
0x1800105c7  mov     [rsp+128h+var_108], ecx
0x1800105cb  mov     r9, [rsp+128h+arg_20]
0x1800105d3  mov     r8, r14
0x1800105d6  mov     rdx, r15
0x1800105d9  mov     rcx, r12
0x1800105dc  mov     rax, cs:off_180025080
0x1800105e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105e8  mov     ebx, eax
0x1800105ea  mov     [rsp+128h+var_C8], eax
0x1800105ee  test    eax, eax
0x1800105f0  jns     short loc_18001060D
0x1800105f2  mov     r9d, 4B6h
0x1800105f8  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800105ff  lea     rdx, aStatus; "Status"
0x180010606  mov     ecx, eax
0x180010608  call    DebugTraceError
0x18001060d  jmp     short loc_180010639
0x18001060f  mov     ebx, eax
0x180010611  mov     r9d, 4BCh
0x180010617  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001061e  lea     rdx, aNtstatus; "ntStatus"
0x180010625  mov     ecx, eax
0x180010627  call    DebugTraceError
0x18001062c  mov     ecx, ebx
0x18001062e  call    NormalizeNteStatus
0x180010633  mov     ebx, eax
0x180010635  mov     [rsp+128h+var_C8], eax
0x180010639  call    cs:__imp_RpcRevertToSelf
0x18001063f  mov     eax, ebx
0x180010641  add     rsp, 0F8h
0x180010648  pop     r15
0x18001064a  pop     r14
0x18001064c  pop     r12
0x18001064e  pop     rdi
0x18001064f  pop     rsi
0x180010650  pop     rbx
0x180010651  retn
```
