# PAC_EncodeValidationInformation(_NETLOGON_VALIDATION_SAM_INFO3 *,uchar * *,ulong *)

- ea: `0x180044260`
- end: `0x1800443e5`
- name: `?PAC_EncodeValidationInformation@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAPEAEPEAK@Z`
- size: `389`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180044770`

## callees

- `0x1800057f0`
- `0x180018870`
- `0x180044260`

## import_xrefs

- `RPCRT4!NdrMesTypeEncode3` at `0x18004438a`
- `RPCRT4!NdrMesTypeEncode3` at `0x18004438a`
- `RPCRT4!MesIncrementalHandleReset` at `0x180044342`
- `RPCRT4!MesIncrementalHandleReset` at `0x180044342`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x1800442f3`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x1800442f3`
- `RPCRT4!MesHandleFree` at `0x1800443d1`
- `RPCRT4!MesHandleFree` at `0x1800443d1`
- `RPCRT4!I_RpcMapWin32Status` at `0x18004434e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18004434e`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x1800442ad`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x1800442ad`

## pseudocode

```c
__int64 __fastcall PAC_EncodeValidationInformation(
        struct _NETLOGON_VALIDATION_SAM_INFO3 *a1,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  unsigned __int8 *v5; // rdi
  unsigned int v6; // ebx
  unsigned int v7; // esi
  unsigned __int8 *v8; // rax
  RPC_STATUS v9; // eax
  __int128 v11; // [rsp+38h] [rbp-40h] BYREF
  struct _NETLOGON_VALIDATION_SAM_INFO3 *pObject; // [rsp+80h] [rbp+8h] BYREF
  handle_t Handle; // [rsp+88h] [rbp+10h] BYREF
  unsigned __int8 *v14; // [rsp+90h] [rbp+18h]

  pObject = a1;
  Handle = 0;
  v11 = 0;
  v5 = 0;
  v14 = 0;
  *a2 = 0;
  *a3 = 0;
  if ( MesEncodeIncrementalHandleCreate(
         &v11,
         PacReadFcn,
         wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         &Handle)
    || (v7 = NdrMesTypeAlignSize3(
               Handle,
               &pPicklingInfo,
               &pProxyInfo,
               (const unsigned int **)&ArrTypeOffset,
               1u,
               &pObject),
        v8 = (unsigned __int8 *)basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, v7),
        v5 = v8,
        (v14 = v8) == 0) )
  {
    v6 = -1073741670;
  }
  else
  {
    v6 = 0;
    DWORD2(v11) = v7;
    *(_QWORD *)&v11 = v8;
    v9 = MesIncrementalHandleReset(Handle, 0, 0, 0, 0, MES_ENCODE);
    if ( v9 )
    {
      v6 = I_RpcMapWin32Status(v9);
    }
    else
    {
      NdrMesTypeEncode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 1u, &pObject);
      *a2 = v5;
      *a3 = v7;
      v5 = 0;
    }
  }
  if ( v5 )
    Pku2uFree(v5);
  if ( Handle )
    MesHandleFree(Handle);
  return v6;
}

```

## disassembly

```asm
0x180044260  mov     rax, rsp
0x180044263  mov     [rax+8], rcx
0x180044267  push    rbx
0x180044268  push    rsi
0x180044269  push    rdi
0x18004426a  push    r14
0x18004426c  push    r15
0x18004426e  sub     rsp, 50h
0x180044272  mov     r14, r8
0x180044275  mov     r15, rdx
0x180044278  mov     qword ptr [rax+10h], 0
0x180044280  xorps   xmm0, xmm0
0x180044283  movups  xmmword ptr [rax-40h], xmm0
0x180044287  xor     edi, edi
0x180044289  mov     [rsp+78h+arg_10], rdi
0x180044291  mov     [rdx], rdi
0x180044294  mov     [r8], edi
0x180044297  lea     r9, [rax+10h]; pHandle
0x18004429b  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; WriteFn
0x1800442a2  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; AllocFn
0x1800442a9  lea     rcx, [rax-40h]; UserState
0x1800442ad  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x1800442b3  test    eax, eax
0x1800442b5  jz      short loc_1800442C1
0x1800442b7  mov     ebx, 0C000009Ah
0x1800442bc  jmp     loc_1800443B7
0x1800442c1  lea     rax, [rsp+78h+arg_0]
0x1800442c9  mov     [rsp+78h+pObject], rax; pObject
0x1800442ce  mov     [rsp+78h+nTypeIndex], 1; nTypeIndex
0x1800442d6  lea     r9, ArrTypeOffset; ArrTypeOffset
0x1800442dd  lea     r8, pProxyInfo; pProxyInfo
0x1800442e4  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800442eb  mov     rcx, [rsp+78h+Handle]; Handle
0x1800442f3  call    cs:__imp_NdrMesTypeAlignSize3
0x1800442f9  mov     rsi, rax
0x1800442fc  mov     [rsp+78h+var_48], esi
0x180044300  mov     edx, esi; unsigned __int64
0x180044302  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180044309  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18004430e  mov     rdi, rax
0x180044311  mov     [rsp+78h+arg_10], rax
0x180044319  test    rax, rax
0x18004431c  jz      short loc_1800442B7
0x18004431e  xor     ebx, ebx
0x180044320  mov     [rsp+78h+var_38], esi
0x180044324  mov     [rsp+78h+var_40], rax
0x180044329  mov     dword ptr [rsp+78h+pObject], ebx; Operation
0x18004432d  mov     qword ptr [rsp+78h+nTypeIndex], rbx; ReadFn
0x180044332  xor     r9d, r9d; WriteFn
0x180044335  xor     r8d, r8d; AllocFn
0x180044338  xor     edx, edx; UserState
0x18004433a  mov     rcx, [rsp+78h+Handle]; Handle
0x180044342  call    cs:__imp_MesIncrementalHandleReset
0x180044348  test    eax, eax
0x18004434a  jz      short loc_180044358
0x18004434c  mov     ecx, eax; Status
0x18004434e  call    cs:__imp_I_RpcMapWin32Status
0x180044354  mov     ebx, eax
0x180044356  jmp     short loc_1800443B7
0x180044358  lea     rax, [rsp+78h+arg_0]
0x180044360  mov     [rsp+78h+pObject], rax; pObject
0x180044365  mov     [rsp+78h+nTypeIndex], 1; nTypeIndex
0x18004436d  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180044374  lea     r8, pProxyInfo; pProxyInfo
0x18004437b  lea     rdx, pPicklingInfo; pPicklingInfo
0x180044382  mov     rcx, [rsp+78h+Handle]; Handle
0x18004438a  call    cs:__imp_NdrMesTypeEncode3
0x180044390  nop
0x180044391  mov     [r15], rdi
0x180044394  mov     [r14], esi
0x180044397  xor     edi, edi
0x180044399  jmp     short loc_1800443B7
0x18004439b  mov     ebx, 0C000000Dh
0x1800443a0  mov     rdi, [rsp+78h+arg_10]
0x1800443a8  jmp     short loc_1800443B7
0x1800443aa  mov     ebx, 0C000000Dh
0x1800443af  mov     rdi, [rsp+78h+arg_10]
0x1800443b7  test    rdi, rdi
0x1800443ba  jz      short loc_1800443C4
0x1800443bc  mov     rcx, rdi; void *
0x1800443bf  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x1800443c4  mov     rcx, [rsp+78h+Handle]; Handle
0x1800443cc  test    rcx, rcx
0x1800443cf  jz      short loc_1800443D7
0x1800443d1  call    cs:__imp_MesHandleFree
0x1800443d7  mov     eax, ebx
0x1800443d9  add     rsp, 50h
0x1800443dd  pop     r15
0x1800443df  pop     r14
0x1800443e1  pop     rdi
0x1800443e2  pop     rsi
0x1800443e3  pop     rbx
0x1800443e4  retn
```
