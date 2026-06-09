# SerializeResult(_PROVIDER_QUERY_ENTRY *,ulong *,uchar * *)

- ea: `0x14000a4f4`
- end: `0x14000a8a5`
- name: `?SerializeResult@@YAJPEAU_PROVIDER_QUERY_ENTRY@@PEAKPEAPEAE@Z`
- size: `945`
- prototype: `__int64 __fastcall(struct _PROVIDER_QUERY_ENTRY *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14000acf0`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x140009060`
- `0x140009090`
- `0x140009cd8`
- `0x14000a4f4`

## import_xrefs

- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x14000a57c`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x14000a57c`
- `RPCRT4!NdrMesTypeEncode3` at `0x14000a7da`
- `RPCRT4!NdrMesTypeEncode3` at `0x14000a7da`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x14000a6be`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x14000a6be`
- `RPCRT4!MesIncrementalHandleReset` at `0x14000a5b9`
- `RPCRT4!MesIncrementalHandleReset` at `0x14000a781`
- `RPCRT4!MesIncrementalHandleReset` at `0x14000a5b9`
- `RPCRT4!MesIncrementalHandleReset` at `0x14000a781`
- `RPCRT4!MesHandleFree` at `0x14000a607`
- `RPCRT4!MesHandleFree` at `0x14000a607`

## pseudocode

```c
__int64 __fastcall SerializeResult(struct _PROVIDER_QUERY_ENTRY *a1, unsigned int *a2, unsigned __int8 **a3)
{
  RPC_STATUS v4; // eax
  unsigned __int64 v5; // rdx
  int v6; // r8d
  signed int v7; // ebx
  bool v8; // sf
  char *v9; // r15
  struct _DAS_HOST_QUERY_RESULT *v10; // rsi
  __int64 v12; // rax
  unsigned int v13; // eax
  RPC_STATUS v14; // eax
  struct _DAS_HOST_QUERY_RESULT *v15; // rax
  __int64 v16; // rax
  int Operation; // [rsp+28h] [rbp-90h]
  __int128 UserState; // [rsp+68h] [rbp-50h] BYREF
  void *v19[2]; // [rsp+78h] [rbp-40h]
  handle_t pHandle; // [rsp+D8h] [rbp+20h] BYREF

  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      (int)a3,
      22,
      &WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids);
  UserState = 0;
  *(_OWORD *)v19 = 0;
  pHandle = 0;
  v4 = MesEncodeIncrementalHandleCreate(
         &UserState,
         RpcSerializationAlloc,
         (MIDL_ES_WRITE)RpcSerializationWrite,
         &pHandle);
  v7 = v4;
  v8 = v4 < 0;
  if ( v4 || (v4 = MesIncrementalHandleReset(pHandle, &UserState, 0, 0, 0, MES_ENCODE_NDR64), v7 = v4, v8 = v4 < 0, v4) )
  {
    if ( !v8 )
      v7 = (unsigned __int16)v4 | 0x80010000;
  }
  else
  {
    v9 = (char *)a1 + 128;
    v10 = *(struct _DAS_HOST_QUERY_RESULT **)v9;
    if ( *(char **)v9 == v9 )
      goto LABEL_8;
    if ( *((char **)v10 + 1) != v9 )
      goto LABEL_37;
    v12 = *(_QWORD *)v10;
    if ( *(struct _DAS_HOST_QUERY_RESULT **)(*(_QWORD *)v10 + 8LL) != v10 )
      goto LABEL_37;
    *(_QWORD *)v9 = v12;
    *(_QWORD *)(v12 + 8) = v9;
    --g_cResults;
    v5 = (unsigned int)NdrMesTypeAlignSize3(
                         pHandle,
                         &pPicklingInfo,
                         &pProxyInfo,
                         (const unsigned int **)&ArrTypeOffset,
                         0,
                         (char *)v10 + 16)
       * (unsigned __int64)(g_cResults + 1);
    if ( v5 > 0xFFFFFFFF )
      v13 = -1;
    else
      v13 = v5;
    v7 = v5 > 0xFFFFFFFF ? 0x80070216 : 0;
    if ( v5 > 0xFFFFFFFF )
      goto LABEL_8;
    HIDWORD(v19[1]) = 0;
    *((_QWORD *)&UserState + 1) = v13;
    *(_QWORD *)&UserState = DAF_user_alloc(v13);
    v14 = MesIncrementalHandleReset(pHandle, &UserState, 0, 0, 0, MES_ENCODE_NDR64);
    if ( v14 )
    {
      if ( v14 < 0 )
        v7 = v14;
      else
        v7 = (unsigned __int16)v14 | 0x80010000;
      goto LABEL_8;
    }
    while ( 1 )
    {
      NdrMesTypeEncode3(
        pHandle,
        &pPicklingInfo,
        &pProxyInfo,
        (const unsigned int **)&ArrTypeOffset,
        0,
        (char *)v10 + 16);
      if ( v7 < 0 )
        goto LABEL_8;
      if ( HIDWORD(v19[1]) )
        break;
      FreeResult(v10);
      v10 = *(struct _DAS_HOST_QUERY_RESULT **)v9;
      if ( *(char **)v9 == v9 )
        goto LABEL_33;
      if ( *((char **)v10 + 1) != v9 )
        goto LABEL_37;
      v16 = *(_QWORD *)v10;
      if ( *(struct _DAS_HOST_QUERY_RESULT **)(*(_QWORD *)v10 + 8LL) != v10 )
        goto LABEL_37;
      *(_QWORD *)v9 = v16;
      *(_QWORD *)(v16 + 8) = v9;
      --g_cResults;
    }
    v15 = *(struct _DAS_HOST_QUERY_RESULT **)v9;
    if ( *(char **)(*(_QWORD *)v9 + 8LL) != v9 )
LABEL_37:
      __fastfail(3u);
    *(_QWORD *)v10 = v15;
    *((_QWORD *)v10 + 1) = v9;
    *((_QWORD *)v15 + 1) = v10;
    *(_QWORD *)v9 = v10;
    ++g_cResults;
LABEL_33:
    *a2 = HIDWORD(UserState);
    *a3 = (unsigned __int8 *)UserState;
  }
LABEL_8:
  if ( v7 < 0 && (_QWORD)UserState )
    MIDL_user_free((void *)UserState);
  if ( v19[0] )
    MIDL_user_free(v19[0]);
  if ( pHandle )
    MesHandleFree(pHandle);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v5,
      v6,
      23,
      &WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids,
      Operation,
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000a4f4  mov     [rsp+arg_0], rbx
0x14000a4f9  mov     [rsp+arg_10], r8
0x14000a4fe  mov     [rsp+arg_8], rdx
0x14000a503  push    rsi
0x14000a504  push    r12
0x14000a506  push    r13
0x14000a508  push    r14
0x14000a50a  push    r15
0x14000a50c  sub     rsp, 90h
0x14000a513  mov     r15, rcx
0x14000a516  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000a51d  lea     r13, WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids
0x14000a524  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000a52b  jz      short loc_14000A548
0x14000a52d  mov     r9d, 16h; int
0x14000a533  mov     [rsp+0B8h+ReadFn], r13; MessageGuid
0x14000a538  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a53f  mov     rcx, [rcx+28h]; int
0x14000a543  call    WPP_RECORDER_SF_s
0x14000a548  xorps   xmm0, xmm0
0x14000a54b  movups  [rsp+0B8h+UserState], xmm0
0x14000a550  movups  xmmword ptr [rsp+0B8h+var_40], xmm0
0x14000a555  mov     [rsp+0B8h+pHandle], 0
0x14000a561  lea     r9, [rsp+0B8h+pHandle]; pHandle
0x14000a569  lea     r8, ?RpcSerializationWrite@@YAXPEAXPEADI@Z; WriteFn
0x14000a570  lea     rdx, ?RpcSerializationAlloc@@YAXPEAXPEAPEADPEAI@Z; AllocFn
0x14000a577  lea     rcx, [rsp+0B8h+UserState]; UserState
0x14000a57c  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x14000a582  mov     ebx, eax
0x14000a584  test    eax, eax
0x14000a586  jz      short loc_14000A595
0x14000a588  js      short loc_14000A5D8
0x14000a58a  movzx   ebx, ax
0x14000a58d  or      ebx, 80010000h
0x14000a593  jmp     short loc_14000A5D8
0x14000a595  mov     [rsp+0B8h+Operation], 2; int
0x14000a59d  mov     [rsp+0B8h+ReadFn], 0; ReadFn
0x14000a5a6  xor     r9d, r9d; WriteFn
0x14000a5a9  xor     r8d, r8d; AllocFn
0x14000a5ac  lea     rdx, [rsp+0B8h+UserState]; UserState
0x14000a5b1  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x14000a5b9  call    cs:__imp_MesIncrementalHandleReset
0x14000a5bf  mov     ebx, eax
0x14000a5c1  test    eax, eax
0x14000a5c3  jnz     short loc_14000A588
0x14000a5c5  sub     r15, 0FFFFFFFFFFFFFF80h
0x14000a5c9  mov     rsi, [r15]
0x14000a5cc  cmp     rsi, r15
0x14000a5cf  jnz     short loc_14000A650
0x14000a5d1  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000a5d8  test    ebx, ebx
0x14000a5da  jns     short loc_14000A5EB
0x14000a5dc  mov     rcx, qword ptr [rsp+0B8h+UserState]; void *
0x14000a5e1  test    rcx, rcx
0x14000a5e4  jz      short loc_14000A5EB
0x14000a5e6  call    MIDL_user_free
0x14000a5eb  mov     rcx, [rsp+0B8h+var_40]; void *
0x14000a5f0  test    rcx, rcx
0x14000a5f3  jz      short loc_14000A5FA
0x14000a5f5  call    MIDL_user_free
0x14000a5fa  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x14000a602  test    rcx, rcx
0x14000a605  jz      short loc_14000A60D
0x14000a607  call    cs:__imp_MesHandleFree
0x14000a60d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000a614  jz      short loc_14000A635
0x14000a616  mov     r9d, 17h; int
0x14000a61c  mov     dword ptr [rsp+0B8h+var_88], ebx; char
0x14000a620  mov     [rsp+0B8h+ReadFn], r13; MessageGuid
0x14000a625  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a62c  mov     rcx, [rcx+28h]; int
0x14000a630  call    WPP_RECORDER_SF_sd
0x14000a635  mov     eax, ebx
0x14000a637  mov     rbx, [rsp+0B8h+arg_0]
0x14000a63f  add     rsp, 90h
0x14000a646  pop     r15
0x14000a648  pop     r14
0x14000a64a  pop     r13
0x14000a64c  pop     r12
0x14000a64e  pop     rsi
0x14000a64f  retn
0x14000a650  mov     r14, r15
0x14000a653  mov     [rsp+0B8h+var_68], r15
0x14000a658  cmp     [rsi+8], r15
0x14000a65c  jnz     loc_14000A89E
0x14000a662  mov     rax, [rsi]
0x14000a665  cmp     [rax+8], rsi
0x14000a669  jnz     loc_14000A89E
0x14000a66f  mov     [rsp+0B8h+var_78], 0
0x14000a677  mov     [r15], rax
0x14000a67a  mov     [rax+8], r15
0x14000a67e  mov     r12d, 0FFFFFFFFh
0x14000a684  add     cs:?g_cResults@@3KA, r12d; ulong g_cResults
0x14000a68b  mov     [rsp+0B8h+var_70], rsi
0x14000a690  lea     rax, [rsi+10h]
0x14000a694  mov     qword ptr [rsp+0B8h+Operation], rax; pObject
0x14000a699  mov     dword ptr [rsp+0B8h+ReadFn], 0; nTypeIndex
0x14000a6a1  lea     r9, ArrTypeOffset; ArrTypeOffset
0x14000a6a8  lea     r8, pProxyInfo; pProxyInfo
0x14000a6af  lea     rdx, pPicklingInfo; pPicklingInfo
0x14000a6b6  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x14000a6be  call    cs:__imp_NdrMesTypeAlignSize3
0x14000a6c4  mov     edx, cs:?g_cResults@@3KA; ulong g_cResults
0x14000a6ca  inc     edx
0x14000a6cc  mov     eax, eax
0x14000a6ce  imul    rdx, rax
0x14000a6d2  cmp     rdx, r12
0x14000a6d5  ja      short loc_14000A6DF
0x14000a6d7  mov     eax, edx
0x14000a6d9  mov     [rsp+0B8h+var_78], edx
0x14000a6dd  jmp     short loc_14000A6E6
0x14000a6df  mov     eax, r12d
0x14000a6e2  mov     [rsp+0B8h+var_78], eax
0x14000a6e6  cmp     r12, rdx
0x14000a6e9  sbb     ebx, ebx
0x14000a6eb  and     ebx, 80070216h
0x14000a6f1  mov     [rsp+0B8h+var_74], ebx
0x14000a6f5  cmp     rdx, r12
0x14000a6f8  jbe     short loc_14000A706
0x14000a6fa  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000a701  jmp     loc_14000A5D8
0x14000a706  jmp     short loc_14000A73A
0x14000a708  mov     ebx, eax
0x14000a70a  cmp     eax, 1
0x14000a70d  jl      short loc_14000A718
0x14000a70f  movzx   ebx, ax
0x14000a712  or      ebx, 80010000h
0x14000a718  mov     [rsp+0B8h+var_74], ebx
0x14000a71c  lea     r13, WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids
0x14000a723  mov     r12d, 0FFFFFFFFh
0x14000a729  mov     eax, [rsp+0B8h+var_78]
0x14000a72d  mov     rsi, [rsp+0B8h+var_70]
0x14000a732  mov     r14, [rsp+0B8h+var_68]
0x14000a737  mov     r15, r14
0x14000a73a  mov     dword ptr [rsp+0B8h+var_40+0Ch], 0
0x14000a745  mov     dword ptr [rsp+0B8h+UserState+0Ch], 0
0x14000a74d  mov     dword ptr [rsp+0B8h+UserState+8], eax
0x14000a751  mov     ecx, eax
0x14000a753  call    DAF_user_alloc
0x14000a758  mov     qword ptr [rsp+0B8h+UserState], rax
0x14000a75d  mov     [rsp+0B8h+Operation], 2; Operation
0x14000a765  mov     [rsp+0B8h+ReadFn], 0; ReadFn
0x14000a76e  xor     r9d, r9d; WriteFn
0x14000a771  xor     r8d, r8d; AllocFn
0x14000a774  lea     rdx, [rsp+0B8h+UserState]; UserState
0x14000a779  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x14000a781  call    cs:__imp_MesIncrementalHandleReset
0x14000a787  test    eax, eax
0x14000a789  jz      short loc_14000A7A2
0x14000a78b  js      short loc_14000A79B
0x14000a78d  movzx   ebx, ax
0x14000a790  or      ebx, 80010000h
0x14000a796  jmp     loc_14000A5D1
0x14000a79b  mov     ebx, eax
0x14000a79d  jmp     loc_14000A5D1
0x14000a7a2  mov     [rsp+0B8h+var_60], r15
0x14000a7a7  mov     [rsp+0B8h+var_58], r15
0x14000a7ac  lea     rax, [rsi+10h]
0x14000a7b0  mov     qword ptr [rsp+0B8h+Operation], rax; pObject
0x14000a7b5  mov     dword ptr [rsp+0B8h+ReadFn], 0; nTypeIndex
0x14000a7bd  lea     r9, ArrTypeOffset; ArrTypeOffset
0x14000a7c4  lea     r8, pProxyInfo; pProxyInfo
0x14000a7cb  lea     rdx, pPicklingInfo; pPicklingInfo
0x14000a7d2  mov     rcx, [rsp+0B8h+pHandle]; Handle
0x14000a7da  call    cs:__imp_NdrMesTypeEncode3
0x14000a7e0  jmp     short loc_14000A80E
0x14000a7e2  mov     ebx, eax
0x14000a7e4  cmp     eax, 1
0x14000a7e7  jl      short loc_14000A7F2
0x14000a7e9  movzx   ebx, ax
0x14000a7ec  or      ebx, 80010000h
0x14000a7f2  lea     r13, WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids
0x14000a7f9  mov     r12d, 0FFFFFFFFh
0x14000a7ff  mov     rsi, [rsp+0B8h+var_70]
0x14000a804  mov     r15, [rsp+0B8h+var_60]
0x14000a809  mov     r14, [rsp+0B8h+var_68]
0x14000a80e  test    ebx, ebx
0x14000a810  js      loc_14000A5D1
0x14000a816  cmp     dword ptr [rsp+0B8h+var_40+0Ch], 0
0x14000a81e  jz      short loc_14000A83F
0x14000a820  mov     rax, [r14]
0x14000a823  cmp     [rax+8], r14
0x14000a827  jnz     short loc_14000A89E
0x14000a829  mov     [rsi], rax
0x14000a82c  mov     [rsi+8], r14
0x14000a830  mov     [rax+8], rsi
0x14000a834  mov     [r14], rsi
0x14000a837  inc     cs:?g_cResults@@3KA; ulong g_cResults
0x14000a83d  jmp     short loc_14000A84F
0x14000a83f  mov     rcx, rsi; lpMem
0x14000a842  call    ?FreeResult@@YAXPEAU_DAS_HOST_QUERY_RESULT@@@Z; FreeResult(_DAS_HOST_QUERY_RESULT *)
0x14000a847  mov     rsi, [r14]
0x14000a84a  cmp     rsi, r14
0x14000a84d  jnz     short loc_14000A872
0x14000a84f  mov     ecx, dword ptr [rsp+0B8h+UserState+0Ch]
0x14000a853  mov     rax, [rsp+0B8h+arg_8]
0x14000a85b  mov     [rax], ecx
0x14000a85d  mov     rcx, [rsp+0B8h+arg_10]
0x14000a865  mov     rax, qword ptr [rsp+0B8h+UserState]
0x14000a86a  mov     [rcx], rax
0x14000a86d  jmp     loc_14000A5D1
0x14000a872  mov     rax, [rsp+0B8h+var_58]
0x14000a877  cmp     [rsi+8], rax
0x14000a87b  jnz     short loc_14000A89E
0x14000a87d  mov     rax, [rsi]
0x14000a880  cmp     [rax+8], rsi
0x14000a884  jnz     short loc_14000A89E
0x14000a886  mov     [r14], rax
0x14000a889  mov     [rax+8], r15
0x14000a88d  add     cs:?g_cResults@@3KA, r12d; ulong g_cResults
0x14000a894  mov     [rsp+0B8h+var_70], rsi
0x14000a899  jmp     loc_14000A7AC
0x14000a89e  mov     ecx, 3
0x14000a8a3  int     29h; Win8: RtlFailFast(ecx)
```
