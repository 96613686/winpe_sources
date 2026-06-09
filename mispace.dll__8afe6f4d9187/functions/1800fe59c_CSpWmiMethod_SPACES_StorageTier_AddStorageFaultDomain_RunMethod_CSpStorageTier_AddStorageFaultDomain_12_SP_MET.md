# CSpWmiMethod<_SPACES_StorageTier_AddStorageFaultDomain>::RunMethod<CSpStorageTier::AddStorageFaultDomain,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800fe59c`
- end: `0x1800fe8ea`
- name: `??$RunMethod@VAddStorageFaultDomain@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_AddStorageFaultDomain@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180102030`

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
- `0x1800fe59c`
- `0x180100394`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe768`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fe749`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fe749`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800fe75e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800fe75e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800fe72f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800fe72f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800fe808`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800fe808`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800fe8bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800fe8bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fe8ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fe8ad`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_AddStorageFaultDomain>::RunMethod<CSpStorageTier::AddStorageFaultDomain,12>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 v7; // rax
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
  CSpStorageTier::AddStorageFaultDomain *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::AddStorageFaultDomain *)operator new(0x160u);
  v7 = CSpStorageTier::AddStorageFaultDomain::AddStorageFaultDomain(v25);
  v8 = v7;
  if ( v7 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 8LL))(v7, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageTier::AddStorageFaultDomain *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_180339B56,
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
0x1800fe59c  mov     [rsp-38h+arg_18], rbx
0x1800fe5a1  push    rbp
0x1800fe5a2  push    rsi
0x1800fe5a3  push    rdi
0x1800fe5a4  push    r12
0x1800fe5a6  push    r13
0x1800fe5a8  push    r14
0x1800fe5aa  push    r15
0x1800fe5ac  mov     rbp, rsp
0x1800fe5af  sub     rsp, 80h
0x1800fe5b6  mov     rax, cs:__security_cookie
0x1800fe5bd  xor     rax, rsp
0x1800fe5c0  mov     [rbp+var_8], rax
0x1800fe5c4  xor     eax, eax
0x1800fe5c6  mov     rsi, rcx
0x1800fe5c9  xorps   xmm0, xmm0
0x1800fe5cc  mov     [rbp+var_10], eax
0x1800fe5cf  mov     ecx, 160h; Size
0x1800fe5d4  mov     [rbp+var_40], eax
0x1800fe5d7  movups  [rbp+var_20], xmm0
0x1800fe5db  mov     [rbp+TokenHandle], rax
0x1800fe5df  mov     r12, r8
0x1800fe5e2  mov     r13, rdx
0x1800fe5e5  xor     r14d, r14d
0x1800fe5e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fe5ed  mov     rcx, rax; this
0x1800fe5f0  mov     [rbp+var_28], rax
0x1800fe5f4  call    ??0AddStorageFaultDomain@CSpStorageTier@@QEAA@XZ; CSpStorageTier::AddStorageFaultDomain::AddStorageFaultDomain(void)
0x1800fe5f9  mov     rdi, rax
0x1800fe5fc  test    rax, rax
0x1800fe5ff  jnz     short loc_1800FE609
0x1800fe601  lea     ebx, [rax+1Bh]
0x1800fe604  jmp     loc_1800FE8A4
0x1800fe609  mov     rax, [rax]
0x1800fe60c  mov     rdx, rsi
0x1800fe60f  mov     rcx, rdi
0x1800fe612  xor     r15d, r15d
0x1800fe615  mov     rax, [rax+8]
0x1800fe619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe61e  lea     rcx, [rbp+var_40]
0x1800fe622  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800fe627  mov     [rdi+1Ch], eax
0x1800fe62a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800fe62e  mov     ecx, [rsi+14h]; unsigned int
0x1800fe631  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800fe636  mov     eax, cs:dword_180397B68
0x1800fe63c  cmp     eax, 5
0x1800fe63f  jbe     short loc_1800FE6AF
0x1800fe641  mov     rdx, 400000000000h
0x1800fe64b  lea     rcx, dword_180397B68
0x1800fe652  call    _tlgKeywordOn
0x1800fe657  test    al, al
0x1800fe659  jz      short loc_1800FE6AF
0x1800fe65b  mov     eax, [rbp+var_40]
0x1800fe65e  lea     rdx, word_180339B56
0x1800fe665  xor     ecx, ecx
0x1800fe667  cmp     [rdi+1Ch], eax
0x1800fe66a  movzx   eax, word ptr [rbp+var_10]
0x1800fe66e  mov     word ptr [rbp+var_40], ax
0x1800fe672  setnz   cl
0x1800fe675  mov     eax, [rsi+14h]
0x1800fe678  mov     [rbp+var_38], eax
0x1800fe67b  lea     rax, [rbp+var_20]
0x1800fe67f  mov     [rbp+var_28], rax
0x1800fe683  lea     rax, [rbp+var_3C]
0x1800fe687  mov     [rsp+80h+var_48], rax
0x1800fe68c  lea     rax, [rbp+var_40]
0x1800fe690  mov     [rsp+80h+var_50], rax
0x1800fe695  lea     rax, [rbp+var_38]
0x1800fe699  mov     [rsp+80h+var_58], rax
0x1800fe69e  lea     rax, [rbp+var_28]
0x1800fe6a2  mov     [rsp+80h+var_60], rax
0x1800fe6a7  mov     [rbp+var_3C], ecx
0x1800fe6aa  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800fe6af  mov     rcx, [rsi]
0x1800fe6b2  test    rcx, rcx
0x1800fe6b5  jz      loc_1800FE87A
0x1800fe6bb  mov     rax, [rcx]
0x1800fe6be  test    rax, rax
0x1800fe6c1  jz      loc_1800FE87A
0x1800fe6c7  mov     rax, [rax+18h]
0x1800fe6cb  lea     r8, [rdi+20h]
0x1800fe6cf  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800fe6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe6db  mov     ebx, eax
0x1800fe6dd  test    eax, eax
0x1800fe6df  jnz     loc_1800FE87F
0x1800fe6e5  cmp     [rsi+10h], r14d
0x1800fe6e9  jz      loc_1800FE813
0x1800fe6ef  lea     rbx, [rdi+148h]
0x1800fe6f6  mov     rcx, rbx
0x1800fe6f9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800fe6fe  mov     rcx, rbx; struct CSpJobMgr **
0x1800fe701  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800fe706  test    eax, eax
0x1800fe708  jnz     short loc_1800FE712
0x1800fe70a  lea     ebx, [rax+1Ch]
0x1800fe70d  jmp     loc_1800FE87F
0x1800fe712  mov     ecx, 10h; Size
0x1800fe717  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fe71c  xor     r8d, r8d; pcbe
0x1800fe71f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800fe726  mov     rdx, rax; pv
0x1800fe729  mov     r15, rax
0x1800fe72c  mov     [rax], rdi
0x1800fe72f  call    cs:__imp_CreateThreadpoolWork
0x1800fe735  mov     r14, rax
0x1800fe738  test    rax, rax
0x1800fe73b  jnz     short loc_1800FE749
0x1800fe73d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800fe742  mov     ebx, eax
0x1800fe744  jmp     loc_1800FE87F
0x1800fe749  call    cs:__imp_GetCurrentThread
0x1800fe74f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800fe753  xor     r8d, r8d; OpenAsSelf
0x1800fe756  mov     rcx, rax; ThreadHandle
0x1800fe759  mov     edx, 2000Ch; DesiredAccess
0x1800fe75e  call    cs:__imp_OpenThreadToken
0x1800fe764  test    eax, eax
0x1800fe766  jnz     short loc_1800FE775
0x1800fe768  call    cs:__imp_GetLastError
0x1800fe76e  cmp     eax, 3F0h
0x1800fe773  jnz     short loc_1800FE73D
0x1800fe775  mov     rax, [rbp+TokenHandle]
0x1800fe779  mov     r8, r13
0x1800fe77c  mov     [r15+8], rax
0x1800fe780  mov     rcx, rdi
0x1800fe783  mov     rax, [rdi]
0x1800fe786  mov     rdx, [rsi+8]
0x1800fe78a  mov     rax, [rax+18h]
0x1800fe78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe793  mov     rax, [rdi]
0x1800fe796  mov     rdx, r12
0x1800fe799  mov     rcx, rdi
0x1800fe79c  mov     rax, [rax+28h]
0x1800fe7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe7a5  mov     ebx, eax
0x1800fe7a7  test    eax, eax
0x1800fe7a9  jz      short loc_1800FE7B4
0x1800fe7ab  cmp     eax, 7
0x1800fe7ae  jnz     loc_1800FE87F
0x1800fe7b4  mov     rax, [rdi]
0x1800fe7b7  mov     rdx, r12
0x1800fe7ba  mov     rcx, rdi
0x1800fe7bd  mov     rax, [rax+38h]
0x1800fe7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe7c6  mov     ebx, eax
0x1800fe7c8  test    eax, eax
0x1800fe7ca  jnz     loc_1800FE87F
0x1800fe7d0  mov     rax, [rdi+150h]
0x1800fe7d7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800fe7de  jnz     short loc_1800FE7F4
0x1800fe7e0  mov     rax, [rdi+158h]
0x1800fe7e7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800fe7ee  jz      loc_1800FE87F
0x1800fe7f4  mov     rdx, r12
0x1800fe7f7  mov     rcx, rdi
0x1800fe7fa  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800fe7ff  mov     ebx, eax
0x1800fe801  test    eax, eax
0x1800fe803  jnz     short loc_1800FE87F
0x1800fe805  mov     rcx, r14; pwk
0x1800fe808  call    cs:__imp_SubmitThreadpoolWork
0x1800fe80e  jmp     loc_1800FE8C1
0x1800fe813  mov     rax, [rdi]
0x1800fe816  mov     r8, r13
0x1800fe819  mov     rdx, [rsi+8]
0x1800fe81d  mov     rcx, rdi
0x1800fe820  mov     rax, [rax+10h]
0x1800fe824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe829  mov     rax, [rdi]
0x1800fe82c  mov     rdx, r12
0x1800fe82f  mov     rcx, rdi
0x1800fe832  mov     rax, [rax+30h]
0x1800fe836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe83b  mov     ebx, eax
0x1800fe83d  test    eax, eax
0x1800fe83f  jz      short loc_1800FE846
0x1800fe841  cmp     eax, 7
0x1800fe844  jnz     short loc_1800FE87F
0x1800fe846  mov     rax, [rdi]
0x1800fe849  mov     rdx, r12
0x1800fe84c  mov     rcx, rdi
0x1800fe84f  mov     rax, [rax+28h]
0x1800fe853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe858  mov     ebx, eax
0x1800fe85a  test    eax, eax
0x1800fe85c  jz      short loc_1800FE863
0x1800fe85e  cmp     eax, 7
0x1800fe861  jnz     short loc_1800FE87F
0x1800fe863  mov     rax, [rdi]
0x1800fe866  mov     rdx, r12
0x1800fe869  mov     rcx, rdi
0x1800fe86c  mov     rax, [rax+38h]
0x1800fe870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe875  jmp     loc_1800FE742
0x1800fe87a  mov     ebx, 4
0x1800fe87f  mov     rax, [rdi]
0x1800fe882  mov     edx, 1
0x1800fe887  mov     rcx, rdi
0x1800fe88a  mov     rax, [rax]
0x1800fe88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe892  test    r15, r15
0x1800fe895  jz      short loc_1800FE8A4
0x1800fe897  mov     edx, 10h
0x1800fe89c  mov     rcx, r15; Block
0x1800fe89f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800fe8a4  mov     rcx, [rbp+TokenHandle]; hObject
0x1800fe8a8  test    rcx, rcx
0x1800fe8ab  jz      short loc_1800FE8B3
0x1800fe8ad  call    cs:__imp_CloseHandle
0x1800fe8b3  test    r14, r14
0x1800fe8b6  jz      short loc_1800FE8C1
0x1800fe8b8  mov     rcx, r14; pwk
0x1800fe8bb  call    cs:__imp_CloseThreadpoolWork
0x1800fe8c1  mov     eax, ebx
0x1800fe8c3  mov     rcx, [rbp+var_8]
0x1800fe8c7  xor     rcx, rsp; StackCookie
0x1800fe8ca  call    __security_check_cookie
0x1800fe8cf  mov     rbx, [rsp+80h+arg_18]
0x1800fe8d7  add     rsp, 80h
0x1800fe8de  pop     r15
0x1800fe8e0  pop     r14
0x1800fe8e2  pop     r13
0x1800fe8e4  pop     r12
0x1800fe8e6  pop     rdi
0x1800fe8e7  pop     rsi
0x1800fe8e8  pop     rbp
0x1800fe8e9  retn
```
