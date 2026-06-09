# DasSerializeResults(CQueryContext *,ulong *,uchar * *)

- ea: `0x180014ce0`
- end: `0x1800152ad`
- name: `?DasSerializeResults@@YAJPEAVCQueryContext@@PEAKPEAPEAE@Z`
- size: `1485`
- prototype: `__int64 __fastcall(struct CQueryContext *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180014c50`

## callees

- `0x180007500`
- `0x180014ce0`
- `0x1800152c0`
- `0x1800153e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001513b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180015212`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001513b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180015212`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014d8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014e03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800150af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015271`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014e03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800150af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015271`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014ef8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800150ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001528d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014ef8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800150ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001528d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800150fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001529b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800150fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001529b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014f06`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014f06`
- `RPCRT4!MesHandleFree` at `0x18001510c`
- `RPCRT4!MesHandleFree` at `0x18001510c`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x180014d2e`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x180014d2e`
- `RPCRT4!MesIncrementalHandleReset` at `0x180014d6c`
- `RPCRT4!MesIncrementalHandleReset` at `0x180014f31`
- `RPCRT4!MesIncrementalHandleReset` at `0x180014d6c`
- `RPCRT4!MesIncrementalHandleReset` at `0x180014f31`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x180014e4b`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x180014e4b`
- `RPCRT4!NdrMesTypeEncode3` at `0x180014fb0`
- `RPCRT4!NdrMesTypeEncode3` at `0x180014fb0`

## pseudocode

```c
__int64 __fastcall DasSerializeResults(struct CQueryContext *a1, unsigned int *a2, unsigned __int8 **a3)
{
  RPC_STATUS v4; // eax
  signed int v5; // esi
  MIDL_ES_CODE Operation; // r15d
  RPC_STATUS v7; // eax
  int v8; // edx
  int v9; // r8d
  char *v10; // r12
  char *v11; // r13
  struct _QUERY_RESULT *v12; // rbx
  __int64 v13; // rax
  _DWORD *v14; // rdi
  unsigned __int64 v15; // rdx
  unsigned int v16; // eax
  unsigned int v17; // edi
  HANDLE ProcessHeap; // rax
  RPC_STATUS v19; // eax
  struct _RTL_CRITICAL_SECTION *v20; // r15
  int v21; // eax
  int v22; // r8d
  int v23; // edx
  int v24; // r8d
  struct _QUERY_RESULT *v25; // rax
  __int64 v26; // rcx
  struct _QUERY_RESULT *v27; // rax
  void *v28; // rbx
  HANDLE v29; // rax
  void *v31; // rbx
  HANDLE v32; // rax
  _QWORD *pObject; // [rsp+38h] [rbp-B0h] BYREF
  handle_t pHandle; // [rsp+40h] [rbp-A8h] BYREF
  _DWORD *v35; // [rsp+48h] [rbp-A0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp-98h]
  struct _QUERY_RESULT *v37; // [rsp+58h] [rbp-90h]
  signed int v38; // [rsp+60h] [rbp-88h]
  char *v39; // [rsp+68h] [rbp-80h]
  char *v40; // [rsp+70h] [rbp-78h]
  _QWORD *v41; // [rsp+78h] [rbp-70h] BYREF
  __int128 UserState; // [rsp+80h] [rbp-68h] BYREF
  __int128 lpMem; // [rsp+90h] [rbp-58h]
  _DWORD *v44; // [rsp+A0h] [rbp-48h]
  char *v45; // [rsp+A8h] [rbp-40h]
  int v49; // [rsp+108h] [rbp+20h]

  UserState = 0;
  lpMem = 0;
  pHandle = 0;
  v4 = MesEncodeIncrementalHandleCreate(&UserState, RpcSerializationAlloc, RpcSerializationWrite, &pHandle);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 >= 0 )
      v5 = (unsigned __int16)v4 | 0x80010000;
    goto LABEL_29;
  }
  Operation = *((_DWORD *)a1 + 12) != 0 ? MES_ENCODE_NDR64 : MES_ENCODE;
  LODWORD(v39) = Operation;
  v7 = MesIncrementalHandleReset(pHandle, &UserState, 0, 0, 0, Operation);
  v5 = v7;
  if ( v7 )
  {
    if ( v7 >= 0 )
      v5 = (unsigned __int16)v7 | 0x80010000;
    goto LABEL_29;
  }
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)a1 + 72);
  v40 = (char *)a1 + 72;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 72));
  v10 = (char *)a1 + 112;
  v11 = (char *)a1 + 112;
  v45 = (char *)a1 + 112;
  v12 = (struct _QUERY_RESULT *)*((_QWORD *)a1 + 14);
  if ( v12 == (struct CQueryContext *)((char *)a1 + 112) )
  {
    v12 = 0;
    v37 = 0;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v8,
        v9,
        11,
        &WPP_d8c419530c9e3c806862643a024b7686_Traceguids);
    ResetEvent(*((HANDLE *)a1 + 7));
    v49 = 1;
    LODWORD(pObject) = 1;
    v14 = (_DWORD *)((char *)a1 + 64);
  }
  else
  {
    if ( *((char **)v12 + 1) != v10 )
      goto LABEL_53;
    v13 = *(_QWORD *)v12;
    if ( *(struct _QUERY_RESULT **)(*(_QWORD *)v12 + 8LL) != v12 )
      goto LABEL_53;
    LODWORD(pObject) = 0;
    *(_QWORD *)v10 = v13;
    *(_QWORD *)(v13 + 8) = v10;
    v37 = v12;
    v14 = (_DWORD *)((char *)a1 + 64);
    --*v14;
    v49 = 1;
  }
  v35 = v14;
  v44 = v14;
  v5 = 0;
  LeaveCriticalSection(lpCriticalSection);
  if ( (_DWORD)pObject )
    goto LABEL_29;
  pObject = (_QWORD *)((char *)v12 + 16);
  v15 = (unsigned int)NdrMesTypeAlignSize3(
                        pHandle,
                        &pPicklingInfo,
                        &pProxyInfo,
                        (const unsigned int **)&ArrTypeOffset,
                        0,
                        &pObject)
      * (unsigned __int64)(unsigned int)(*v14 + 1);
  if ( v15 > 0xFFFFFFFF )
    v16 = -1;
  else
    v16 = v15;
  v5 = 0;
  if ( v15 > 0xFFFFFFFF )
    v5 = -2147024362;
  v38 = v5;
  if ( v15 > 0xFFFFFFFF )
    goto LABEL_29;
  HIDWORD(lpMem) = 0;
  *((_QWORD *)&UserState + 1) = v16;
  v17 = v16;
  ProcessHeap = GetProcessHeap();
  *(_QWORD *)&UserState = HeapAlloc(ProcessHeap, 0, v17);
  v19 = MesIncrementalHandleReset(pHandle, &UserState, 0, 0, 0, Operation);
  if ( v19 )
  {
    if ( v19 >= 0 )
      v5 = (unsigned __int16)v19 | 0x80010000;
    else
      v5 = v19;
    goto LABEL_29;
  }
  v37 = v12;
  LODWORD(pObject) = 1;
  v20 = lpCriticalSection;
  v40 = v10;
  v39 = v10;
  EnterCriticalSection(lpCriticalSection);
  v21 = 1;
  while ( 1 )
  {
    if ( !v21 )
      goto LABEL_28;
    v41 = (_QWORD *)((char *)v12 + 16);
    NdrMesTypeEncode3(pHandle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 0, &v41);
    if ( v5 < 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)&WPP_RECORDER_INITIALIZED,
          v22,
          12,
          &WPP_d8c419530c9e3c806862643a024b7686_Traceguids,
          v5);
      LeaveCriticalSection(v20);
      goto LABEL_29;
    }
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)&WPP_RECORDER_INITIALIZED,
        v22,
        13,
        &WPP_d8c419530c9e3c806862643a024b7686_Traceguids);
    if ( HIDWORD(lpMem) )
      break;
    FreeQueryResult(v12);
    v25 = *(struct _QUERY_RESULT **)v11;
    if ( *(char **)v11 == v11 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v23,
          v24,
          14,
          &WPP_d8c419530c9e3c806862643a024b7686_Traceguids);
      ResetEvent(*((HANDLE *)a1 + 7));
      v21 = 0;
      v49 = 0;
      LODWORD(pObject) = 0;
    }
    else
    {
      if ( *((char **)v25 + 1) != v39 )
        goto LABEL_53;
      v26 = *(_QWORD *)v25;
      if ( *(struct _QUERY_RESULT **)(*(_QWORD *)v25 + 8LL) != v25 )
        goto LABEL_53;
      *(_QWORD *)v11 = v26;
      *(_QWORD *)(v26 + 8) = v10;
      --*v35;
      v12 = v25;
      v37 = v25;
      v21 = v49;
    }
  }
  v27 = *(struct _QUERY_RESULT **)v11;
  if ( *(char **)(*(_QWORD *)v11 + 8LL) != v11 )
LABEL_53:
    __fastfail(3u);
  *(_QWORD *)v12 = v27;
  *((_QWORD *)v12 + 1) = v11;
  *((_QWORD *)v27 + 1) = v12;
  *(_QWORD *)v11 = v12;
  ++*v35;
LABEL_28:
  LeaveCriticalSection(v20);
  *a2 = HIDWORD(UserState);
  *a3 = (unsigned __int8 *)UserState;
LABEL_29:
  if ( v5 < 0 )
  {
    v31 = (void *)UserState;
    if ( (_QWORD)UserState )
    {
      v32 = GetProcessHeap();
      HeapFree(v32, 0, v31);
    }
  }
  v28 = (void *)lpMem;
  if ( (_QWORD)lpMem )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v28);
  }
  if ( pHandle )
    MesHandleFree(pHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180014ce0  mov     rax, rsp
0x180014ce3  mov     [rax+18h], r8
0x180014ce7  mov     [rax+10h], rdx
0x180014ceb  mov     [rax+8], rcx
0x180014cef  push    rbx
0x180014cf0  push    rsi
0x180014cf1  push    rdi
0x180014cf2  push    r12
0x180014cf4  push    r13
0x180014cf6  push    r14
0x180014cf8  push    r15
0x180014cfa  sub     rsp, 0B0h
0x180014d01  mov     rdi, rcx
0x180014d04  xorps   xmm0, xmm0
0x180014d07  movups  xmmword ptr [rax-68h], xmm0
0x180014d0b  movups  xmmword ptr [rax-58h], xmm0
0x180014d0f  xor     r14d, r14d
0x180014d12  mov     [rsp+0E8h+pHandle], r14
0x180014d17  lea     r9, [rsp+0E8h+pHandle]; pHandle
0x180014d1c  lea     r8, ?RpcSerializationWrite@@YAXPEAXPEADI@Z; WriteFn
0x180014d23  lea     rdx, ?RpcSerializationAlloc@@YAXPEAXPEAPEADPEAI@Z; AllocFn
0x180014d2a  lea     rcx, [rax-68h]; UserState
0x180014d2e  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x180014d34  mov     esi, eax
0x180014d36  test    eax, eax
0x180014d38  jnz     loc_1800151AC
0x180014d3e  mov     eax, [rdi+30h]
0x180014d41  neg     eax
0x180014d43  sbb     r15d, r15d
0x180014d46  and     r15d, 2
0x180014d4a  mov     dword ptr [rsp+0E8h+var_80], r15d
0x180014d4f  mov     [rsp+0E8h+Operation], r15d; Operation
0x180014d54  mov     [rsp+0E8h+ReadFn], r14; ReadFn
0x180014d59  xor     r9d, r9d; WriteFn
0x180014d5c  xor     r8d, r8d; AllocFn
0x180014d5f  lea     rdx, [rsp+0E8h+UserState]; UserState
0x180014d67  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x180014d6c  call    cs:__imp_MesIncrementalHandleReset
0x180014d72  mov     esi, eax
0x180014d74  test    eax, eax
0x180014d76  jnz     loc_1800151C0
0x180014d7c  lea     rax, [rdi+48h]
0x180014d80  mov     [rsp+0E8h+lpCriticalSection], rax
0x180014d85  mov     [rsp+0E8h+var_78], rax
0x180014d8a  mov     rcx, rax; lpCriticalSection
0x180014d8d  call    cs:__imp_EnterCriticalSection
0x180014d93  lea     r12, [rdi+70h]
0x180014d97  mov     r13, r12
0x180014d9a  mov     [rsp+0E8h+var_40], r12
0x180014da2  mov     rbx, [r12]
0x180014da6  cmp     rbx, r12
0x180014da9  jz      loc_1800151D4
0x180014daf  cmp     [rbx+8], r12
0x180014db3  jnz     loc_1800152A6
0x180014db9  mov     rax, [rbx]
0x180014dbc  cmp     [rax+8], rbx
0x180014dc0  jnz     loc_1800152A6
0x180014dc6  mov     dword ptr [rsp+0E8h+pObject], r14d
0x180014dcb  mov     [r12], rax
0x180014dcf  mov     [rax+8], r12
0x180014dd3  mov     [rsp+0E8h+var_90], rbx
0x180014dd8  add     rdi, 40h ; '@'
0x180014ddc  mov     eax, 0FFFFFFFFh
0x180014de1  add     [rdi], eax
0x180014de3  mov     [rsp+0E8h+arg_18], 1
0x180014dee  mov     [rsp+0E8h+var_A0], rdi
0x180014df3  mov     [rsp+0E8h+var_48], rdi
0x180014dfb  mov     esi, r14d
0x180014dfe  mov     rcx, [rsp+0E8h+lpCriticalSection]; lpCriticalSection
0x180014e03  call    cs:__imp_LeaveCriticalSection
0x180014e09  cmp     dword ptr [rsp+0E8h+pObject], r14d
0x180014e0e  jnz     loc_1800150D9
0x180014e14  mov     [rsp+0E8h+var_B8], r14d
0x180014e19  lea     rax, [rbx+10h]
0x180014e1d  mov     [rsp+0E8h+pObject], rax
0x180014e22  lea     rax, [rsp+0E8h+pObject]
0x180014e27  mov     qword ptr [rsp+0E8h+Operation], rax; pObject
0x180014e2c  mov     dword ptr [rsp+0E8h+ReadFn], r14d; nTypeIndex
0x180014e31  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180014e38  lea     r8, pProxyInfo; pProxyInfo
0x180014e3f  lea     rdx, pPicklingInfo; pPicklingInfo
0x180014e46  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x180014e4b  call    cs:__imp_NdrMesTypeAlignSize3
0x180014e51  mov     edx, [rdi]
0x180014e53  inc     edx
0x180014e55  mov     eax, eax
0x180014e57  imul    rdx, rax
0x180014e5b  mov     ecx, 0FFFFFFFFh
0x180014e60  cmp     rdx, rcx
0x180014e63  ja      short loc_180014E83
0x180014e65  mov     eax, edx
0x180014e67  mov     [rsp+0E8h+var_B8], edx
0x180014e6b  mov     esi, r14d
0x180014e6e  mov     r8d, 80070216h
0x180014e74  cmova   esi, r8d
0x180014e78  mov     [rsp+0E8h+var_88], esi
0x180014e7c  jbe     short loc_180014E8B
0x180014e7e  jmp     loc_1800150D9
0x180014e83  mov     eax, ecx
0x180014e85  mov     [rsp+0E8h+var_B8], ecx
0x180014e89  jmp     short loc_180014E6B
0x180014e8b  jmp     short loc_180014EDF
0x180014e8d  mov     esi, eax
0x180014e8f  cmp     eax, 1
0x180014e92  jl      short loc_180014E9D
0x180014e94  movzx   esi, ax
0x180014e97  or      esi, 80010000h
0x180014e9d  mov     [rsp+0E8h+var_88], esi
0x180014ea1  xor     r14d, r14d
0x180014ea4  mov     [rsp+0E8h+arg_18], 1
0x180014eaf  mov     eax, [rsp+0E8h+var_B8]
0x180014eb3  mov     rbx, [rsp+0E8h+var_90]
0x180014eb8  mov     rcx, [rsp+0E8h+var_48]
0x180014ec0  mov     [rsp+0E8h+var_A0], rcx
0x180014ec5  mov     r13, [rsp+0E8h+var_40]
0x180014ecd  mov     rcx, [rsp+0E8h+var_78]
0x180014ed2  mov     [rsp+0E8h+lpCriticalSection], rcx
0x180014ed7  mov     r15d, dword ptr [rsp+0E8h+var_80]
0x180014edc  mov     r12, r13
0x180014edf  mov     [rsp+0E8h+var_4C], r14d
0x180014ee7  mov     [rsp+0E8h+var_5C], r14d
0x180014eef  mov     [rsp+0E8h+var_60], eax
0x180014ef6  mov     edi, eax
0x180014ef8  call    cs:__imp_GetProcessHeap
0x180014efe  mov     rcx, rax; hHeap
0x180014f01  mov     r8d, edi; dwBytes
0x180014f04  xor     edx, edx; dwFlags
0x180014f06  call    cs:__imp_HeapAlloc
0x180014f0c  mov     [rsp+0E8h+UserState], rax
0x180014f14  mov     [rsp+0E8h+Operation], r15d; Operation
0x180014f19  mov     [rsp+0E8h+ReadFn], r14; ReadFn
0x180014f1e  xor     r9d, r9d; WriteFn
0x180014f21  xor     r8d, r8d; AllocFn
0x180014f24  lea     rdx, [rsp+0E8h+UserState]; UserState
0x180014f2c  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x180014f31  call    cs:__imp_MesIncrementalHandleReset
0x180014f37  test    eax, eax
0x180014f39  jnz     loc_18001519F
0x180014f3f  mov     [rsp+0E8h+var_90], rbx
0x180014f44  mov     dword ptr [rsp+0E8h+pObject], 1
0x180014f4c  mov     r15, [rsp+0E8h+lpCriticalSection]
0x180014f51  mov     [rsp+0E8h+lpCriticalSection], r15
0x180014f56  mov     [rsp+0E8h+var_78], r12
0x180014f5b  mov     [rsp+0E8h+var_80], r12
0x180014f60  mov     rcx, r15; lpCriticalSection
0x180014f63  call    cs:__imp_EnterCriticalSection
0x180014f69  mov     rdi, [rsp+0E8h+arg_0]
0x180014f71  mov     eax, 1
0x180014f76  test    eax, eax
0x180014f78  jz      loc_1800150AC
0x180014f7e  lea     rax, [rbx+10h]
0x180014f82  mov     [rsp+0E8h+var_70], rax
0x180014f87  lea     rax, [rsp+0E8h+var_70]
0x180014f8c  mov     qword ptr [rsp+0E8h+Operation], rax; pObject
0x180014f91  mov     dword ptr [rsp+0E8h+ReadFn], r14d; nTypeIndex
0x180014f96  lea     r9, ArrTypeOffset; ArrTypeOffset
0x180014f9d  lea     r8, pProxyInfo; pProxyInfo
0x180014fa4  lea     rdx, pPicklingInfo; pPicklingInfo
0x180014fab  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x180014fb0  call    cs:__imp_NdrMesTypeEncode3
0x180014fb6  lea     rdx, WPP_RECORDER_INITIALIZED
0x180014fbd  jmp     short loc_180015010
0x180014fbf  mov     esi, eax
0x180014fc1  cmp     eax, 1
0x180014fc4  jl      short loc_180014FCF
0x180014fc6  movzx   esi, ax
0x180014fc9  or      esi, 80010000h
0x180014fcf  xor     r14d, r14d
0x180014fd2  lea     rdx, WPP_RECORDER_INITIALIZED; int
0x180014fd9  mov     rbx, [rsp+0E8h+var_90]
0x180014fde  mov     eax, dword ptr [rsp+0E8h+pObject]
0x180014fe2  mov     [rsp+0E8h+arg_18], eax
0x180014fe9  mov     r12, [rsp+0E8h+var_78]
0x180014fee  mov     rcx, [rsp+0E8h+var_48]
0x180014ff6  mov     [rsp+0E8h+var_A0], rcx
0x180014ffb  mov     r15, [rsp+0E8h+lpCriticalSection]
0x180015000  mov     r13, [rsp+0E8h+var_40]
0x180015008  mov     rdi, [rsp+0E8h+arg_0]
0x180015010  test    esi, esi
0x180015012  js      loc_18001523F
0x180015018  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x18001501f  jnz     loc_180015178
0x180015025  cmp     [rsp+0E8h+var_4C], 0
0x18001502d  jnz     short loc_180015088
0x18001502f  mov     rcx, rbx; struct _QUERY_RESULT *
0x180015032  call    ?FreeQueryResult@@YAXPEAU_QUERY_RESULT@@@Z; FreeQueryResult(_QUERY_RESULT *)
0x180015037  mov     rax, [r13+0]
0x18001503b  cmp     rax, r13
0x18001503e  jz      loc_180015127
0x180015044  mov     rcx, [rsp+0E8h+var_80]
0x180015049  cmp     [rax+8], rcx
0x18001504d  jnz     loc_1800152A6
0x180015053  mov     rcx, [rax]
0x180015056  cmp     [rcx+8], rax
0x18001505a  jnz     loc_1800152A6
0x180015060  mov     [r13+0], rcx
0x180015064  mov     [rcx+8], r12
0x180015068  mov     rcx, [rsp+0E8h+var_A0]
0x18001506d  mov     edx, 0FFFFFFFFh
0x180015072  add     [rcx], edx
0x180015074  mov     rbx, rax
0x180015077  mov     [rsp+0E8h+var_90], rax
0x18001507c  mov     eax, [rsp+0E8h+arg_18]
0x180015083  jmp     loc_180014F76
0x180015088  mov     rax, [r13+0]
0x18001508c  cmp     [rax+8], r13
0x180015090  jnz     loc_1800152A6
0x180015096  mov     [rbx], rax
0x180015099  mov     [rbx+8], r13
0x18001509d  mov     [rax+8], rbx
0x1800150a1  mov     [r13+0], rbx
0x1800150a5  mov     rax, [rsp+0E8h+var_A0]
0x1800150aa  inc     dword ptr [rax]
0x1800150ac  mov     rcx, r15; lpCriticalSection
0x1800150af  call    cs:__imp_LeaveCriticalSection
0x1800150b5  mov     rcx, [rsp+0E8h+arg_8]
0x1800150bd  mov     eax, [rsp+0E8h+var_5C]
0x1800150c4  mov     [rcx], eax
0x1800150c6  mov     rcx, [rsp+0E8h+arg_10]
0x1800150ce  mov     rax, [rsp+0E8h+UserState]
0x1800150d6  mov     [rcx], rax
0x1800150d9  test    esi, esi
0x1800150db  js      loc_18001527C
0x1800150e1  mov     rbx, [rsp+0E8h+lpMem]
0x1800150e9  test    rbx, rbx
0x1800150ec  jz      short loc_180015102
0x1800150ee  call    cs:__imp_GetProcessHeap
0x1800150f4  mov     rcx, rax; hHeap
0x1800150f7  mov     r8, rbx; lpMem
0x1800150fa  xor     edx, edx; dwFlags
0x1800150fc  call    cs:__imp_HeapFree
0x180015102  mov     rcx, [rsp+0E8h+pHandle]; Handle
0x180015107  test    rcx, rcx
0x18001510a  jz      short loc_180015112
0x18001510c  call    cs:__imp_MesHandleFree
0x180015112  mov     eax, esi
0x180015114  add     rsp, 0B0h
0x18001511b  pop     r15
0x18001511d  pop     r14
0x18001511f  pop     r13
0x180015121  pop     r12
0x180015123  pop     rdi
0x180015124  pop     rsi
0x180015125  pop     rbx
0x180015126  retn
0x180015127  lea     rax, WPP_RECORDER_INITIALIZED
0x18001512e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180015135  jnz     short loc_180015154
0x180015137  mov     rcx, [rdi+38h]; hEvent
0x18001513b  call    cs:__imp_ResetEvent
0x180015141  mov     eax, r14d
0x180015144  mov     [rsp+0E8h+arg_18], eax
0x18001514b  mov     dword ptr [rsp+0E8h+pObject], eax
0x18001514f  jmp     loc_180014F76
0x180015154  mov     r9d, 0Eh; int
0x18001515a  lea     rax, WPP_d8c419530c9e3c806862643a024b7686_Traceguids
0x180015161  mov     [rsp+0E8h+ReadFn], rax; MessageGuid
0x180015166  mov     rcx, cs:WPP_GLOBAL_Control
0x18001516d  mov     rcx, [rcx+28h]; int
0x180015171  call    WPP_RECORDER_SF_
0x180015176  jmp     short loc_180015137
0x180015178  mov     r9d, 0Dh; int
0x18001517e  lea     rax, WPP_d8c419530c9e3c806862643a024b7686_Traceguids
0x180015185  mov     [rsp+0E8h+ReadFn], rax; MessageGuid
0x18001518a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015191  mov     rcx, [rcx+28h]; int
0x180015195  call    WPP_RECORDER_SF_
0x18001519a  jmp     loc_180015025
0x18001519f  jns     loc_180015231
0x1800151a5  mov     esi, eax
0x1800151a7  jmp     loc_1800150D9
0x1800151ac  js      loc_1800150D9
0x1800151b2  movzx   esi, ax
0x1800151b5  or      esi, 80010000h
0x1800151bb  jmp     loc_1800150D9
0x1800151c0  js      loc_1800150D9
0x1800151c6  movzx   esi, ax
0x1800151c9  or      esi, 80010000h
0x1800151cf  jmp     loc_1800150D9
0x1800151d4  mov     rbx, r14
0x1800151d7  mov     [rsp+0E8h+var_90], rbx
0x1800151dc  lea     rax, WPP_RECORDER_INITIALIZED
0x1800151e3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800151ea  jz      short loc_18001520E
0x1800151ec  mov     r9d, 0Bh; int
0x1800151f2  lea     rsi, WPP_d8c419530c9e3c806862643a024b7686_Traceguids
0x1800151f9  mov     [rsp+0E8h+ReadFn], rsi; MessageGuid
0x1800151fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180015205  mov     rcx, [rcx+28h]; int
0x180015209  call    WPP_RECORDER_SF_
0x18001520e  mov     rcx, [rdi+38h]; hEvent
0x180015212  call    cs:__imp_ResetEvent
0x180015218  mov     eax, 1
0x18001521d  mov     [rsp+0E8h+arg_18], eax
0x180015224  mov     dword ptr [rsp+0E8h+pObject], eax
0x180015228  add     rdi, 40h ; '@'
0x18001522c  jmp     loc_180014DEE
0x180015231  movzx   esi, ax
0x180015234  or      esi, 80010000h
0x18001523a  jmp     loc_1800150D9
  ... truncated ...
```
