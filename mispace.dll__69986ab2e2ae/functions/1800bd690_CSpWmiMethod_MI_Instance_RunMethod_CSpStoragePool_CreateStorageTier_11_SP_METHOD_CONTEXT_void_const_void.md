# CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::CreateStorageTier,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bd690`
- end: `0x1800bda0d`
- name: `??$RunMethod@VCreateStorageTier@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800c5060`

## callees

- `0x180001504`
- `0x180001994`
- `0x180006350`
- `0x1800063a0`
- `0x1800063ac`
- `0x18000c644`
- `0x180013b4c`
- `0x1800142e8`
- `0x180014a54`
- `0x1800257fc`
- `0x18005f41c`
- `0x1800bd690`
- `0x1800c0ca8`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd86e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd86e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bd843`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bd843`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bd85e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bd85e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bd823`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bd823`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bd918`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bd918`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bd9d7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bd9d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd9c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd9c3`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::CreateStorageTier,11>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 StorageTier; // rax
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
  CSpStoragePool::CreateStorageTier *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::CreateStorageTier *)operator new(0x1D0u);
  StorageTier = CSpStoragePool::CreateStorageTier::CreateStorageTier(v25);
  v8 = StorageTier;
  if ( StorageTier )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)StorageTier + 8LL))(StorageTier, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStoragePool::CreateStorageTier *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_180332B2E,
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
0x1800bd690  mov     [rsp-38h+arg_18], rbx
0x1800bd695  push    rbp
0x1800bd696  push    rsi
0x1800bd697  push    rdi
0x1800bd698  push    r12
0x1800bd69a  push    r13
0x1800bd69c  push    r14
0x1800bd69e  push    r15
0x1800bd6a0  mov     rbp, rsp
0x1800bd6a3  sub     rsp, 80h
0x1800bd6aa  mov     rax, cs:__security_cookie
0x1800bd6b1  xor     rax, rsp
0x1800bd6b4  mov     [rbp+var_8], rax
0x1800bd6b8  xor     eax, eax
0x1800bd6ba  mov     rsi, rcx
0x1800bd6bd  xorps   xmm0, xmm0
0x1800bd6c0  mov     [rbp+var_10], eax
0x1800bd6c3  mov     ecx, 1D0h; Size
0x1800bd6c8  mov     [rbp+var_40], eax
0x1800bd6cb  movups  [rbp+var_20], xmm0
0x1800bd6cf  mov     [rbp+TokenHandle], rax
0x1800bd6d3  mov     r12, r8
0x1800bd6d6  mov     r13, rdx
0x1800bd6d9  xor     r14d, r14d
0x1800bd6dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bd6e1  mov     rcx, rax; this
0x1800bd6e4  mov     [rbp+var_28], rax
0x1800bd6e8  call    ??0CreateStorageTier@CSpStoragePool@@QEAA@XZ; CSpStoragePool::CreateStorageTier::CreateStorageTier(void)
0x1800bd6ed  mov     rdi, rax
0x1800bd6f0  test    rax, rax
0x1800bd6f3  jnz     short loc_1800BD6FD
0x1800bd6f5  lea     ebx, [rax+1Bh]
0x1800bd6f8  jmp     loc_1800BD9BA
0x1800bd6fd  mov     rax, [rax]
0x1800bd700  mov     rdx, rsi
0x1800bd703  mov     rcx, rdi
0x1800bd706  xor     r15d, r15d
0x1800bd709  mov     rax, [rax+8]
0x1800bd70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd712  lea     rcx, [rbp+var_40]
0x1800bd716  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bd71b  mov     [rdi+1Ch], eax
0x1800bd71e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bd722  mov     ecx, [rsi+14h]; unsigned int
0x1800bd725  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bd72a  mov     eax, cs:dword_18039EB68
0x1800bd730  cmp     eax, 5
0x1800bd733  jbe     short loc_1800BD7A3
0x1800bd735  mov     rdx, 400000000000h
0x1800bd73f  lea     rcx, dword_18039EB68
0x1800bd746  call    _tlgKeywordOn
0x1800bd74b  test    al, al
0x1800bd74d  jz      short loc_1800BD7A3
0x1800bd74f  mov     eax, [rbp+var_40]
0x1800bd752  lea     rdx, word_180332B2E
0x1800bd759  xor     ecx, ecx
0x1800bd75b  cmp     [rdi+1Ch], eax
0x1800bd75e  movzx   eax, word ptr [rbp+var_10]
0x1800bd762  mov     word ptr [rbp+var_40], ax
0x1800bd766  setnz   cl
0x1800bd769  mov     eax, [rsi+14h]
0x1800bd76c  mov     [rbp+var_38], eax
0x1800bd76f  lea     rax, [rbp+var_20]
0x1800bd773  mov     [rbp+var_28], rax
0x1800bd777  lea     rax, [rbp+var_3C]
0x1800bd77b  mov     [rsp+80h+var_48], rax
0x1800bd780  lea     rax, [rbp+var_40]
0x1800bd784  mov     [rsp+80h+var_50], rax
0x1800bd789  lea     rax, [rbp+var_38]
0x1800bd78d  mov     [rsp+80h+var_58], rax
0x1800bd792  lea     rax, [rbp+var_28]
0x1800bd796  mov     [rsp+80h+var_60], rax
0x1800bd79b  mov     [rbp+var_3C], ecx
0x1800bd79e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bd7a3  mov     rcx, [rsi]
0x1800bd7a6  test    rcx, rcx
0x1800bd7a9  jz      loc_1800BD990
0x1800bd7af  mov     rax, [rcx]
0x1800bd7b2  test    rax, rax
0x1800bd7b5  jz      loc_1800BD990
0x1800bd7bb  mov     rax, [rax+18h]
0x1800bd7bf  lea     r8, [rdi+20h]
0x1800bd7c3  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bd7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd7cf  mov     ebx, eax
0x1800bd7d1  test    eax, eax
0x1800bd7d3  jnz     loc_1800BD995
0x1800bd7d9  cmp     [rsi+10h], r14d
0x1800bd7dd  jz      loc_1800BD929
0x1800bd7e3  lea     rbx, [rdi+148h]
0x1800bd7ea  mov     rcx, rbx
0x1800bd7ed  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bd7f2  mov     rcx, rbx; struct CSpJobMgr **
0x1800bd7f5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bd7fa  test    eax, eax
0x1800bd7fc  jnz     short loc_1800BD806
0x1800bd7fe  lea     ebx, [rax+1Ch]
0x1800bd801  jmp     loc_1800BD995
0x1800bd806  mov     ecx, 10h; Size
0x1800bd80b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bd810  xor     r8d, r8d; pcbe
0x1800bd813  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bd81a  mov     rdx, rax; pv
0x1800bd81d  mov     r15, rax
0x1800bd820  mov     [rax], rdi
0x1800bd823  call    cs:__imp_CreateThreadpoolWork
0x1800bd82a  nop     dword ptr [rax+rax+00h]
0x1800bd82f  mov     r14, rax
0x1800bd832  test    rax, rax
0x1800bd835  jnz     short loc_1800BD843
0x1800bd837  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bd83c  mov     ebx, eax
0x1800bd83e  jmp     loc_1800BD995
0x1800bd843  call    cs:__imp_GetCurrentThread
0x1800bd84a  nop     dword ptr [rax+rax+00h]
0x1800bd84f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bd853  xor     r8d, r8d; OpenAsSelf
0x1800bd856  mov     rcx, rax; ThreadHandle
0x1800bd859  mov     edx, 2000Ch; DesiredAccess
0x1800bd85e  call    cs:__imp_OpenThreadToken
0x1800bd865  nop     dword ptr [rax+rax+00h]
0x1800bd86a  test    eax, eax
0x1800bd86c  jnz     short loc_1800BD881
0x1800bd86e  call    cs:__imp_GetLastError
0x1800bd875  nop     dword ptr [rax+rax+00h]
0x1800bd87a  cmp     eax, 3F0h
0x1800bd87f  jnz     short loc_1800BD837
0x1800bd881  mov     rax, [rbp+TokenHandle]
0x1800bd885  mov     r8, r13
0x1800bd888  mov     [r15+8], rax
0x1800bd88c  mov     rcx, rdi
0x1800bd88f  mov     rax, [rdi]
0x1800bd892  mov     rdx, [rsi+8]
0x1800bd896  mov     rax, [rax+18h]
0x1800bd89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd89f  mov     rax, [rdi]
0x1800bd8a2  mov     rdx, r12
0x1800bd8a5  mov     rcx, rdi
0x1800bd8a8  mov     rax, [rax+28h]
0x1800bd8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd8b1  mov     ebx, eax
0x1800bd8b3  test    eax, eax
0x1800bd8b5  jz      short loc_1800BD8C0
0x1800bd8b7  cmp     eax, 7
0x1800bd8ba  jnz     loc_1800BD995
0x1800bd8c0  mov     rax, [rdi]
0x1800bd8c3  mov     rdx, r12
0x1800bd8c6  mov     rcx, rdi
0x1800bd8c9  mov     rax, [rax+38h]
0x1800bd8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd8d2  mov     ebx, eax
0x1800bd8d4  test    eax, eax
0x1800bd8d6  jnz     loc_1800BD995
0x1800bd8dc  mov     rax, [rdi+150h]
0x1800bd8e3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bd8ea  jnz     short loc_1800BD900
0x1800bd8ec  mov     rax, [rdi+158h]
0x1800bd8f3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bd8fa  jz      loc_1800BD995
0x1800bd900  mov     rdx, r12
0x1800bd903  mov     rcx, rdi
0x1800bd906  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bd90b  mov     ebx, eax
0x1800bd90d  test    eax, eax
0x1800bd90f  jnz     loc_1800BD995
0x1800bd915  mov     rcx, r14; pwk
0x1800bd918  call    cs:__imp_SubmitThreadpoolWork
0x1800bd91f  nop     dword ptr [rax+rax+00h]
0x1800bd924  jmp     loc_1800BD9E3
0x1800bd929  mov     rax, [rdi]
0x1800bd92c  mov     r8, r13
0x1800bd92f  mov     rdx, [rsi+8]
0x1800bd933  mov     rcx, rdi
0x1800bd936  mov     rax, [rax+10h]
0x1800bd93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd93f  mov     rax, [rdi]
0x1800bd942  mov     rdx, r12
0x1800bd945  mov     rcx, rdi
0x1800bd948  mov     rax, [rax+30h]
0x1800bd94c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd951  mov     ebx, eax
0x1800bd953  test    eax, eax
0x1800bd955  jz      short loc_1800BD95C
0x1800bd957  cmp     eax, 7
0x1800bd95a  jnz     short loc_1800BD995
0x1800bd95c  mov     rax, [rdi]
0x1800bd95f  mov     rdx, r12
0x1800bd962  mov     rcx, rdi
0x1800bd965  mov     rax, [rax+28h]
0x1800bd969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd96e  mov     ebx, eax
0x1800bd970  test    eax, eax
0x1800bd972  jz      short loc_1800BD979
0x1800bd974  cmp     eax, 7
0x1800bd977  jnz     short loc_1800BD995
0x1800bd979  mov     rax, [rdi]
0x1800bd97c  mov     rdx, r12
0x1800bd97f  mov     rcx, rdi
0x1800bd982  mov     rax, [rax+38h]
0x1800bd986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd98b  jmp     loc_1800BD83C
0x1800bd990  mov     ebx, 4
0x1800bd995  mov     rax, [rdi]
0x1800bd998  mov     edx, 1
0x1800bd99d  mov     rcx, rdi
0x1800bd9a0  mov     rax, [rax]
0x1800bd9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd9a8  test    r15, r15
0x1800bd9ab  jz      short loc_1800BD9BA
0x1800bd9ad  mov     edx, 10h
0x1800bd9b2  mov     rcx, r15; Block
0x1800bd9b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bd9ba  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bd9be  test    rcx, rcx
0x1800bd9c1  jz      short loc_1800BD9CF
0x1800bd9c3  call    cs:__imp_CloseHandle
0x1800bd9ca  nop     dword ptr [rax+rax+00h]
0x1800bd9cf  test    r14, r14
0x1800bd9d2  jz      short loc_1800BD9E3
0x1800bd9d4  mov     rcx, r14; pwk
0x1800bd9d7  call    cs:__imp_CloseThreadpoolWork
0x1800bd9de  nop     dword ptr [rax+rax+00h]
0x1800bd9e3  mov     eax, ebx
0x1800bd9e5  mov     rcx, [rbp+var_8]
0x1800bd9e9  xor     rcx, rsp; StackCookie
0x1800bd9ec  call    __security_check_cookie
0x1800bd9f1  mov     rbx, [rsp+80h+arg_18]
0x1800bd9f9  add     rsp, 80h
0x1800bda00  pop     r15
0x1800bda02  pop     r14
0x1800bda04  pop     r13
0x1800bda06  pop     r12
0x1800bda08  pop     rdi
0x1800bda09  pop     rsi
0x1800bda0a  pop     rbp
0x1800bda0b  retn
```
