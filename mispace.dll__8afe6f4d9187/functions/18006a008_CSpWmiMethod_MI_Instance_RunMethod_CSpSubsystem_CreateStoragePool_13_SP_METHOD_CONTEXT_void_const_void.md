# CSpWmiMethod<_MI_Instance>::RunMethod<CSpSubsystem::CreateStoragePool,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006a008`
- end: `0x18006a356`
- name: `??$RunMethod@VCreateStoragePool@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180072020`

## callees

- `0x1800014ec`
- `0x180001970`
- `0x180006290`
- `0x1800062e0`
- `0x1800062ec`
- `0x18000c704`
- `0x180013898`
- `0x180014000`
- `0x180014720`
- `0x180024dfc`
- `0x18005d58c`
- `0x18006a008`
- `0x18006bd54`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a1d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a1d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006a1b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006a1b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006a1ca`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006a1ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006a19b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006a19b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006a274`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006a274`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006a327`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006a327`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a319`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a319`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpSubsystem::CreateStoragePool,13>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 StoragePool; // rax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  __int64 *v10; // r15
  int v11; // r8d
  int v12; // r9d
  bool v13; // zf
  __int64 v14; // rcx
  enum _MI_Result v15; // eax
  HANDLE CurrentThread; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v21; // [rsp+40h] [rbp-40h] BYREF
  BOOL v22; // [rsp+44h] [rbp-3Ch] BYREF
  int v23; // [rsp+48h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-30h] BYREF
  CSpSubsystem::CreateStoragePool *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::CreateStoragePool *)operator new(0x428u);
  StoragePool = CSpSubsystem::CreateStoragePool::CreateStoragePool(v25);
  v8 = StoragePool;
  if ( StoragePool )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)StoragePool + 8LL))(StoragePool, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpSubsystem::CreateStoragePool *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_18030EBB0,
        v11,
        v12,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)&v21,
        (__int64)&v22);
    }
    v14 = *a1;
    if ( *a1 && *(_QWORD *)v14 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v14 + 24LL))(
             v14,
             &MSFT_StorageExtendedStatus_rtti,
             v8 + 32);
      if ( v9 )
        goto LABEL_30;
      if ( *((_DWORD *)a1 + 4) )
      {
        CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(v8 + 328);
        if ( !(unsigned int)CSpJobMgr::GetInstance((struct CSpJobMgr **)(v8 + 328)) )
        {
          v9 = 28;
          goto LABEL_30;
        }
        v10 = (__int64 *)operator new(0x10u);
        *v10 = v8;
        ThreadpoolWork = CreateThreadpoolWork(
                           CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::ResumeMethodWorker,
                           v10,
                           0);
        if ( ThreadpoolWork )
        {
          CurrentThread = GetCurrentThread();
          if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) || GetLastError() == 1008 )
          {
            v10[1] = (__int64)TokenHandle;
            (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 24LL))(v8, a1[1], a2);
            v17 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
            v9 = v17;
            if ( !v17 || v17 == 7 )
            {
              v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
              if ( !v9
                && (*(_QWORD *)(v8 + 336) != *(_QWORD *)&GUID_NULL.Data1
                 || *(_QWORD *)(v8 + 344) != *(_QWORD *)GUID_NULL.Data4) )
              {
                v9 = CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(v8, a3);
                if ( !v9 )
                {
                  SubmitThreadpoolWork(ThreadpoolWork);
                  return v9;
                }
              }
            }
            goto LABEL_30;
          }
        }
        v15 = GleToMiResult();
        goto LABEL_14;
      }
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 16LL))(v8, a1[1], a2);
      v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 48LL))(v8, a3);
      v9 = v18;
      if ( !v18 || v18 == 7 )
      {
        v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
        v9 = v19;
        if ( !v19 || v19 == 7 )
        {
          v15 = (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
LABEL_14:
          v9 = v15;
        }
      }
    }
    else
    {
      v9 = 4;
    }
LABEL_30:
    (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
    if ( v10 )
      operator delete(v10);
    goto LABEL_32;
  }
  v9 = 27;
LABEL_32:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v9;
}

```

## disassembly

```asm
0x18006a008  mov     [rsp-38h+arg_18], rbx
0x18006a00d  push    rbp
0x18006a00e  push    rsi
0x18006a00f  push    rdi
0x18006a010  push    r12
0x18006a012  push    r13
0x18006a014  push    r14
0x18006a016  push    r15
0x18006a018  mov     rbp, rsp
0x18006a01b  sub     rsp, 80h
0x18006a022  mov     rax, cs:__security_cookie
0x18006a029  xor     rax, rsp
0x18006a02c  mov     [rbp+var_8], rax
0x18006a030  xor     eax, eax
0x18006a032  mov     rsi, rcx
0x18006a035  xorps   xmm0, xmm0
0x18006a038  mov     [rbp+var_10], eax
0x18006a03b  mov     ecx, 428h; Size
0x18006a040  mov     [rbp+var_40], eax
0x18006a043  movups  [rbp+var_20], xmm0
0x18006a047  mov     [rbp+TokenHandle], rax
0x18006a04b  mov     r12, r8
0x18006a04e  mov     r13, rdx
0x18006a051  xor     r14d, r14d
0x18006a054  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006a059  mov     rcx, rax; this
0x18006a05c  mov     [rbp+var_28], rax
0x18006a060  call    ??0CreateStoragePool@CSpSubsystem@@QEAA@XZ; CSpSubsystem::CreateStoragePool::CreateStoragePool(void)
0x18006a065  mov     rdi, rax
0x18006a068  test    rax, rax
0x18006a06b  jnz     short loc_18006A075
0x18006a06d  lea     ebx, [rax+1Bh]
0x18006a070  jmp     loc_18006A310
0x18006a075  mov     rax, [rax]
0x18006a078  mov     rdx, rsi
0x18006a07b  mov     rcx, rdi
0x18006a07e  xor     r15d, r15d
0x18006a081  mov     rax, [rax+8]
0x18006a085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a08a  lea     rcx, [rbp+var_40]
0x18006a08e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006a093  mov     [rdi+1Ch], eax
0x18006a096  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006a09a  mov     ecx, [rsi+14h]; unsigned int
0x18006a09d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006a0a2  mov     eax, cs:dword_180397B68
0x18006a0a8  cmp     eax, 5
0x18006a0ab  jbe     short loc_18006A11B
0x18006a0ad  mov     rdx, 400000000000h
0x18006a0b7  lea     rcx, dword_180397B68
0x18006a0be  call    _tlgKeywordOn
0x18006a0c3  test    al, al
0x18006a0c5  jz      short loc_18006A11B
0x18006a0c7  mov     eax, [rbp+var_40]
0x18006a0ca  lea     rdx, unk_18030EBB0
0x18006a0d1  xor     ecx, ecx
0x18006a0d3  cmp     [rdi+1Ch], eax
0x18006a0d6  movzx   eax, word ptr [rbp+var_10]
0x18006a0da  mov     word ptr [rbp+var_40], ax
0x18006a0de  setnz   cl
0x18006a0e1  mov     eax, [rsi+14h]
0x18006a0e4  mov     [rbp+var_38], eax
0x18006a0e7  lea     rax, [rbp+var_20]
0x18006a0eb  mov     [rbp+var_28], rax
0x18006a0ef  lea     rax, [rbp+var_3C]
0x18006a0f3  mov     [rsp+80h+var_48], rax
0x18006a0f8  lea     rax, [rbp+var_40]
0x18006a0fc  mov     [rsp+80h+var_50], rax
0x18006a101  lea     rax, [rbp+var_38]
0x18006a105  mov     [rsp+80h+var_58], rax
0x18006a10a  lea     rax, [rbp+var_28]
0x18006a10e  mov     [rsp+80h+var_60], rax
0x18006a113  mov     [rbp+var_3C], ecx
0x18006a116  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006a11b  mov     rcx, [rsi]
0x18006a11e  test    rcx, rcx
0x18006a121  jz      loc_18006A2E6
0x18006a127  mov     rax, [rcx]
0x18006a12a  test    rax, rax
0x18006a12d  jz      loc_18006A2E6
0x18006a133  mov     rax, [rax+18h]
0x18006a137  lea     r8, [rdi+20h]
0x18006a13b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006a142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a147  mov     ebx, eax
0x18006a149  test    eax, eax
0x18006a14b  jnz     loc_18006A2EB
0x18006a151  cmp     [rsi+10h], r14d
0x18006a155  jz      loc_18006A27F
0x18006a15b  lea     rbx, [rdi+148h]
0x18006a162  mov     rcx, rbx
0x18006a165  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006a16a  mov     rcx, rbx; struct CSpJobMgr **
0x18006a16d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006a172  test    eax, eax
0x18006a174  jnz     short loc_18006A17E
0x18006a176  lea     ebx, [rax+1Ch]
0x18006a179  jmp     loc_18006A2EB
0x18006a17e  mov     ecx, 10h; Size
0x18006a183  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006a188  xor     r8d, r8d; pcbe
0x18006a18b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006a192  mov     rdx, rax; pv
0x18006a195  mov     r15, rax
0x18006a198  mov     [rax], rdi
0x18006a19b  call    cs:__imp_CreateThreadpoolWork
0x18006a1a1  mov     r14, rax
0x18006a1a4  test    rax, rax
0x18006a1a7  jnz     short loc_18006A1B5
0x18006a1a9  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006a1ae  mov     ebx, eax
0x18006a1b0  jmp     loc_18006A2EB
0x18006a1b5  call    cs:__imp_GetCurrentThread
0x18006a1bb  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006a1bf  xor     r8d, r8d; OpenAsSelf
0x18006a1c2  mov     rcx, rax; ThreadHandle
0x18006a1c5  mov     edx, 2000Ch; DesiredAccess
0x18006a1ca  call    cs:__imp_OpenThreadToken
0x18006a1d0  test    eax, eax
0x18006a1d2  jnz     short loc_18006A1E1
0x18006a1d4  call    cs:__imp_GetLastError
0x18006a1da  cmp     eax, 3F0h
0x18006a1df  jnz     short loc_18006A1A9
0x18006a1e1  mov     rax, [rbp+TokenHandle]
0x18006a1e5  mov     r8, r13
0x18006a1e8  mov     [r15+8], rax
0x18006a1ec  mov     rcx, rdi
0x18006a1ef  mov     rax, [rdi]
0x18006a1f2  mov     rdx, [rsi+8]
0x18006a1f6  mov     rax, [rax+18h]
0x18006a1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a1ff  mov     rax, [rdi]
0x18006a202  mov     rdx, r12
0x18006a205  mov     rcx, rdi
0x18006a208  mov     rax, [rax+28h]
0x18006a20c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a211  mov     ebx, eax
0x18006a213  test    eax, eax
0x18006a215  jz      short loc_18006A220
0x18006a217  cmp     eax, 7
0x18006a21a  jnz     loc_18006A2EB
0x18006a220  mov     rax, [rdi]
0x18006a223  mov     rdx, r12
0x18006a226  mov     rcx, rdi
0x18006a229  mov     rax, [rax+38h]
0x18006a22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a232  mov     ebx, eax
0x18006a234  test    eax, eax
0x18006a236  jnz     loc_18006A2EB
0x18006a23c  mov     rax, [rdi+150h]
0x18006a243  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006a24a  jnz     short loc_18006A260
0x18006a24c  mov     rax, [rdi+158h]
0x18006a253  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006a25a  jz      loc_18006A2EB
0x18006a260  mov     rdx, r12
0x18006a263  mov     rcx, rdi
0x18006a266  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006a26b  mov     ebx, eax
0x18006a26d  test    eax, eax
0x18006a26f  jnz     short loc_18006A2EB
0x18006a271  mov     rcx, r14; pwk
0x18006a274  call    cs:__imp_SubmitThreadpoolWork
0x18006a27a  jmp     loc_18006A32D
0x18006a27f  mov     rax, [rdi]
0x18006a282  mov     r8, r13
0x18006a285  mov     rdx, [rsi+8]
0x18006a289  mov     rcx, rdi
0x18006a28c  mov     rax, [rax+10h]
0x18006a290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a295  mov     rax, [rdi]
0x18006a298  mov     rdx, r12
0x18006a29b  mov     rcx, rdi
0x18006a29e  mov     rax, [rax+30h]
0x18006a2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2a7  mov     ebx, eax
0x18006a2a9  test    eax, eax
0x18006a2ab  jz      short loc_18006A2B2
0x18006a2ad  cmp     eax, 7
0x18006a2b0  jnz     short loc_18006A2EB
0x18006a2b2  mov     rax, [rdi]
0x18006a2b5  mov     rdx, r12
0x18006a2b8  mov     rcx, rdi
0x18006a2bb  mov     rax, [rax+28h]
0x18006a2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2c4  mov     ebx, eax
0x18006a2c6  test    eax, eax
0x18006a2c8  jz      short loc_18006A2CF
0x18006a2ca  cmp     eax, 7
0x18006a2cd  jnz     short loc_18006A2EB
0x18006a2cf  mov     rax, [rdi]
0x18006a2d2  mov     rdx, r12
0x18006a2d5  mov     rcx, rdi
0x18006a2d8  mov     rax, [rax+38h]
0x18006a2dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2e1  jmp     loc_18006A1AE
0x18006a2e6  mov     ebx, 4
0x18006a2eb  mov     rax, [rdi]
0x18006a2ee  mov     edx, 1
0x18006a2f3  mov     rcx, rdi
0x18006a2f6  mov     rax, [rax]
0x18006a2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2fe  test    r15, r15
0x18006a301  jz      short loc_18006A310
0x18006a303  mov     edx, 10h
0x18006a308  mov     rcx, r15; Block
0x18006a30b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006a310  mov     rcx, [rbp+TokenHandle]; hObject
0x18006a314  test    rcx, rcx
0x18006a317  jz      short loc_18006A31F
0x18006a319  call    cs:__imp_CloseHandle
0x18006a31f  test    r14, r14
0x18006a322  jz      short loc_18006A32D
0x18006a324  mov     rcx, r14; pwk
0x18006a327  call    cs:__imp_CloseThreadpoolWork
0x18006a32d  mov     eax, ebx
0x18006a32f  mov     rcx, [rbp+var_8]
0x18006a333  xor     rcx, rsp; StackCookie
0x18006a336  call    __security_check_cookie
0x18006a33b  mov     rbx, [rsp+80h+arg_18]
0x18006a343  add     rsp, 80h
0x18006a34a  pop     r15
0x18006a34c  pop     r14
0x18006a34e  pop     r13
0x18006a350  pop     r12
0x18006a352  pop     rdi
0x18006a353  pop     rsi
0x18006a354  pop     rbp
0x18006a355  retn
```
