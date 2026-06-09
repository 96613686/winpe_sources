# CSpWmiMethod<_SPACES_StoragePool_AddPhysicalDisk>::RunMethod<CSpStoragePool::AddPhysicalDisk,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ba580`
- end: `0x1800ba8ce`
- name: `??$RunMethod@VAddPhysicalDisk@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_AddPhysicalDisk@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800c1f80`

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
- `0x1800ba580`
- `0x1800bdba4`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba74c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba74c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ba72d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ba72d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ba742`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ba742`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ba713`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ba713`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ba7ec`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ba7ec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ba89f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ba89f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba891`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba891`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_AddPhysicalDisk>::RunMethod<CSpStoragePool::AddPhysicalDisk,11>(
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
  CSpStoragePool::AddPhysicalDisk *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::AddPhysicalDisk *)operator new(0x170u);
  v7 = CSpStoragePool::AddPhysicalDisk::AddPhysicalDisk(v25);
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
      v25 = (CSpStoragePool::AddPhysicalDisk *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_180328368,
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
0x1800ba580  mov     [rsp-38h+arg_18], rbx
0x1800ba585  push    rbp
0x1800ba586  push    rsi
0x1800ba587  push    rdi
0x1800ba588  push    r12
0x1800ba58a  push    r13
0x1800ba58c  push    r14
0x1800ba58e  push    r15
0x1800ba590  mov     rbp, rsp
0x1800ba593  sub     rsp, 80h
0x1800ba59a  mov     rax, cs:__security_cookie
0x1800ba5a1  xor     rax, rsp
0x1800ba5a4  mov     [rbp+var_8], rax
0x1800ba5a8  xor     eax, eax
0x1800ba5aa  mov     rsi, rcx
0x1800ba5ad  xorps   xmm0, xmm0
0x1800ba5b0  mov     [rbp+var_10], eax
0x1800ba5b3  mov     ecx, 170h; Size
0x1800ba5b8  mov     [rbp+var_40], eax
0x1800ba5bb  movups  [rbp+var_20], xmm0
0x1800ba5bf  mov     [rbp+TokenHandle], rax
0x1800ba5c3  mov     r12, r8
0x1800ba5c6  mov     r13, rdx
0x1800ba5c9  xor     r14d, r14d
0x1800ba5cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ba5d1  mov     rcx, rax; this
0x1800ba5d4  mov     [rbp+var_28], rax
0x1800ba5d8  call    ??0AddPhysicalDisk@CSpStoragePool@@QEAA@XZ; CSpStoragePool::AddPhysicalDisk::AddPhysicalDisk(void)
0x1800ba5dd  mov     rdi, rax
0x1800ba5e0  test    rax, rax
0x1800ba5e3  jnz     short loc_1800BA5ED
0x1800ba5e5  lea     ebx, [rax+1Bh]
0x1800ba5e8  jmp     loc_1800BA888
0x1800ba5ed  mov     rax, [rax]
0x1800ba5f0  mov     rdx, rsi
0x1800ba5f3  mov     rcx, rdi
0x1800ba5f6  xor     r15d, r15d
0x1800ba5f9  mov     rax, [rax+8]
0x1800ba5fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba602  lea     rcx, [rbp+var_40]
0x1800ba606  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ba60b  mov     [rdi+1Ch], eax
0x1800ba60e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ba612  mov     ecx, [rsi+14h]; unsigned int
0x1800ba615  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ba61a  mov     eax, cs:dword_180397B68
0x1800ba620  cmp     eax, 5
0x1800ba623  jbe     short loc_1800BA693
0x1800ba625  mov     rdx, 400000000000h
0x1800ba62f  lea     rcx, dword_180397B68
0x1800ba636  call    _tlgKeywordOn
0x1800ba63b  test    al, al
0x1800ba63d  jz      short loc_1800BA693
0x1800ba63f  mov     eax, [rbp+var_40]
0x1800ba642  lea     rdx, unk_180328368
0x1800ba649  xor     ecx, ecx
0x1800ba64b  cmp     [rdi+1Ch], eax
0x1800ba64e  movzx   eax, word ptr [rbp+var_10]
0x1800ba652  mov     word ptr [rbp+var_40], ax
0x1800ba656  setnz   cl
0x1800ba659  mov     eax, [rsi+14h]
0x1800ba65c  mov     [rbp+var_38], eax
0x1800ba65f  lea     rax, [rbp+var_20]
0x1800ba663  mov     [rbp+var_28], rax
0x1800ba667  lea     rax, [rbp+var_3C]
0x1800ba66b  mov     [rsp+80h+var_48], rax
0x1800ba670  lea     rax, [rbp+var_40]
0x1800ba674  mov     [rsp+80h+var_50], rax
0x1800ba679  lea     rax, [rbp+var_38]
0x1800ba67d  mov     [rsp+80h+var_58], rax
0x1800ba682  lea     rax, [rbp+var_28]
0x1800ba686  mov     [rsp+80h+var_60], rax
0x1800ba68b  mov     [rbp+var_3C], ecx
0x1800ba68e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ba693  mov     rcx, [rsi]
0x1800ba696  test    rcx, rcx
0x1800ba699  jz      loc_1800BA85E
0x1800ba69f  mov     rax, [rcx]
0x1800ba6a2  test    rax, rax
0x1800ba6a5  jz      loc_1800BA85E
0x1800ba6ab  mov     rax, [rax+18h]
0x1800ba6af  lea     r8, [rdi+20h]
0x1800ba6b3  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ba6ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba6bf  mov     ebx, eax
0x1800ba6c1  test    eax, eax
0x1800ba6c3  jnz     loc_1800BA863
0x1800ba6c9  cmp     [rsi+10h], r14d
0x1800ba6cd  jz      loc_1800BA7F7
0x1800ba6d3  lea     rbx, [rdi+148h]
0x1800ba6da  mov     rcx, rbx
0x1800ba6dd  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ba6e2  mov     rcx, rbx; struct CSpJobMgr **
0x1800ba6e5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ba6ea  test    eax, eax
0x1800ba6ec  jnz     short loc_1800BA6F6
0x1800ba6ee  lea     ebx, [rax+1Ch]
0x1800ba6f1  jmp     loc_1800BA863
0x1800ba6f6  mov     ecx, 10h; Size
0x1800ba6fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ba700  xor     r8d, r8d; pcbe
0x1800ba703  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ba70a  mov     rdx, rax; pv
0x1800ba70d  mov     r15, rax
0x1800ba710  mov     [rax], rdi
0x1800ba713  call    cs:__imp_CreateThreadpoolWork
0x1800ba719  mov     r14, rax
0x1800ba71c  test    rax, rax
0x1800ba71f  jnz     short loc_1800BA72D
0x1800ba721  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800ba726  mov     ebx, eax
0x1800ba728  jmp     loc_1800BA863
0x1800ba72d  call    cs:__imp_GetCurrentThread
0x1800ba733  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ba737  xor     r8d, r8d; OpenAsSelf
0x1800ba73a  mov     rcx, rax; ThreadHandle
0x1800ba73d  mov     edx, 2000Ch; DesiredAccess
0x1800ba742  call    cs:__imp_OpenThreadToken
0x1800ba748  test    eax, eax
0x1800ba74a  jnz     short loc_1800BA759
0x1800ba74c  call    cs:__imp_GetLastError
0x1800ba752  cmp     eax, 3F0h
0x1800ba757  jnz     short loc_1800BA721
0x1800ba759  mov     rax, [rbp+TokenHandle]
0x1800ba75d  mov     r8, r13
0x1800ba760  mov     [r15+8], rax
0x1800ba764  mov     rcx, rdi
0x1800ba767  mov     rax, [rdi]
0x1800ba76a  mov     rdx, [rsi+8]
0x1800ba76e  mov     rax, [rax+18h]
0x1800ba772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba777  mov     rax, [rdi]
0x1800ba77a  mov     rdx, r12
0x1800ba77d  mov     rcx, rdi
0x1800ba780  mov     rax, [rax+28h]
0x1800ba784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba789  mov     ebx, eax
0x1800ba78b  test    eax, eax
0x1800ba78d  jz      short loc_1800BA798
0x1800ba78f  cmp     eax, 7
0x1800ba792  jnz     loc_1800BA863
0x1800ba798  mov     rax, [rdi]
0x1800ba79b  mov     rdx, r12
0x1800ba79e  mov     rcx, rdi
0x1800ba7a1  mov     rax, [rax+38h]
0x1800ba7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba7aa  mov     ebx, eax
0x1800ba7ac  test    eax, eax
0x1800ba7ae  jnz     loc_1800BA863
0x1800ba7b4  mov     rax, [rdi+150h]
0x1800ba7bb  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800ba7c2  jnz     short loc_1800BA7D8
0x1800ba7c4  mov     rax, [rdi+158h]
0x1800ba7cb  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800ba7d2  jz      loc_1800BA863
0x1800ba7d8  mov     rdx, r12
0x1800ba7db  mov     rcx, rdi
0x1800ba7de  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800ba7e3  mov     ebx, eax
0x1800ba7e5  test    eax, eax
0x1800ba7e7  jnz     short loc_1800BA863
0x1800ba7e9  mov     rcx, r14; pwk
0x1800ba7ec  call    cs:__imp_SubmitThreadpoolWork
0x1800ba7f2  jmp     loc_1800BA8A5
0x1800ba7f7  mov     rax, [rdi]
0x1800ba7fa  mov     r8, r13
0x1800ba7fd  mov     rdx, [rsi+8]
0x1800ba801  mov     rcx, rdi
0x1800ba804  mov     rax, [rax+10h]
0x1800ba808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba80d  mov     rax, [rdi]
0x1800ba810  mov     rdx, r12
0x1800ba813  mov     rcx, rdi
0x1800ba816  mov     rax, [rax+30h]
0x1800ba81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba81f  mov     ebx, eax
0x1800ba821  test    eax, eax
0x1800ba823  jz      short loc_1800BA82A
0x1800ba825  cmp     eax, 7
0x1800ba828  jnz     short loc_1800BA863
0x1800ba82a  mov     rax, [rdi]
0x1800ba82d  mov     rdx, r12
0x1800ba830  mov     rcx, rdi
0x1800ba833  mov     rax, [rax+28h]
0x1800ba837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba83c  mov     ebx, eax
0x1800ba83e  test    eax, eax
0x1800ba840  jz      short loc_1800BA847
0x1800ba842  cmp     eax, 7
0x1800ba845  jnz     short loc_1800BA863
0x1800ba847  mov     rax, [rdi]
0x1800ba84a  mov     rdx, r12
0x1800ba84d  mov     rcx, rdi
0x1800ba850  mov     rax, [rax+38h]
0x1800ba854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba859  jmp     loc_1800BA726
0x1800ba85e  mov     ebx, 4
0x1800ba863  mov     rax, [rdi]
0x1800ba866  mov     edx, 1
0x1800ba86b  mov     rcx, rdi
0x1800ba86e  mov     rax, [rax]
0x1800ba871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba876  test    r15, r15
0x1800ba879  jz      short loc_1800BA888
0x1800ba87b  mov     edx, 10h
0x1800ba880  mov     rcx, r15; Block
0x1800ba883  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ba888  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ba88c  test    rcx, rcx
0x1800ba88f  jz      short loc_1800BA897
0x1800ba891  call    cs:__imp_CloseHandle
0x1800ba897  test    r14, r14
0x1800ba89a  jz      short loc_1800BA8A5
0x1800ba89c  mov     rcx, r14; pwk
0x1800ba89f  call    cs:__imp_CloseThreadpoolWork
0x1800ba8a5  mov     eax, ebx
0x1800ba8a7  mov     rcx, [rbp+var_8]
0x1800ba8ab  xor     rcx, rsp; StackCookie
0x1800ba8ae  call    __security_check_cookie
0x1800ba8b3  mov     rbx, [rsp+80h+arg_18]
0x1800ba8bb  add     rsp, 80h
0x1800ba8c2  pop     r15
0x1800ba8c4  pop     r14
0x1800ba8c6  pop     r13
0x1800ba8c8  pop     r12
0x1800ba8ca  pop     rdi
0x1800ba8cb  pop     rsi
0x1800ba8cc  pop     rbp
0x1800ba8cd  retn
```
