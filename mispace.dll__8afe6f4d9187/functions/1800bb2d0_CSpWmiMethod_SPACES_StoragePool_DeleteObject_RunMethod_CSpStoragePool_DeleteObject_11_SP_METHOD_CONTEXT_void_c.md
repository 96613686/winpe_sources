# CSpWmiMethod<_SPACES_StoragePool_DeleteObject>::RunMethod<CSpStoragePool::DeleteObject,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bb2d0`
- end: `0x1800bb61e`
- name: `??$RunMethod@VDeleteObject@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_DeleteObject@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800bb2d0`
- `0x1800bdf50`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb49c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb49c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bb47d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bb47d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bb492`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bb492`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bb463`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bb463`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bb53c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bb53c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bb5ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bb5ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb5e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb5e1`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_DeleteObject>::RunMethod<CSpStoragePool::DeleteObject,11>(
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
  CSpStoragePool::DeleteObject *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::DeleteObject *)operator new(0x168u);
  v7 = CSpStoragePool::DeleteObject::DeleteObject(v25);
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
      v25 = (CSpStoragePool::DeleteObject *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)word_180328ECA,
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
0x1800bb2d0  mov     [rsp-38h+arg_18], rbx
0x1800bb2d5  push    rbp
0x1800bb2d6  push    rsi
0x1800bb2d7  push    rdi
0x1800bb2d8  push    r12
0x1800bb2da  push    r13
0x1800bb2dc  push    r14
0x1800bb2de  push    r15
0x1800bb2e0  mov     rbp, rsp
0x1800bb2e3  sub     rsp, 80h
0x1800bb2ea  mov     rax, cs:__security_cookie
0x1800bb2f1  xor     rax, rsp
0x1800bb2f4  mov     [rbp+var_8], rax
0x1800bb2f8  xor     eax, eax
0x1800bb2fa  mov     rsi, rcx
0x1800bb2fd  xorps   xmm0, xmm0
0x1800bb300  mov     [rbp+var_10], eax
0x1800bb303  mov     ecx, 168h; Size
0x1800bb308  mov     [rbp+var_40], eax
0x1800bb30b  movups  [rbp+var_20], xmm0
0x1800bb30f  mov     [rbp+TokenHandle], rax
0x1800bb313  mov     r12, r8
0x1800bb316  mov     r13, rdx
0x1800bb319  xor     r14d, r14d
0x1800bb31c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bb321  mov     rcx, rax; this
0x1800bb324  mov     [rbp+var_28], rax
0x1800bb328  call    ??0DeleteObject@CSpStoragePool@@QEAA@XZ; CSpStoragePool::DeleteObject::DeleteObject(void)
0x1800bb32d  mov     rdi, rax
0x1800bb330  test    rax, rax
0x1800bb333  jnz     short loc_1800BB33D
0x1800bb335  lea     ebx, [rax+1Bh]
0x1800bb338  jmp     loc_1800BB5D8
0x1800bb33d  mov     rax, [rax]
0x1800bb340  mov     rdx, rsi
0x1800bb343  mov     rcx, rdi
0x1800bb346  xor     r15d, r15d
0x1800bb349  mov     rax, [rax+8]
0x1800bb34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb352  lea     rcx, [rbp+var_40]
0x1800bb356  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bb35b  mov     [rdi+1Ch], eax
0x1800bb35e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bb362  mov     ecx, [rsi+14h]; unsigned int
0x1800bb365  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bb36a  mov     eax, cs:dword_180397B68
0x1800bb370  cmp     eax, 5
0x1800bb373  jbe     short loc_1800BB3E3
0x1800bb375  mov     rdx, 400000000000h
0x1800bb37f  lea     rcx, dword_180397B68
0x1800bb386  call    _tlgKeywordOn
0x1800bb38b  test    al, al
0x1800bb38d  jz      short loc_1800BB3E3
0x1800bb38f  mov     eax, [rbp+var_40]
0x1800bb392  lea     rdx, word_180328ECA
0x1800bb399  xor     ecx, ecx
0x1800bb39b  cmp     [rdi+1Ch], eax
0x1800bb39e  movzx   eax, word ptr [rbp+var_10]
0x1800bb3a2  mov     word ptr [rbp+var_40], ax
0x1800bb3a6  setnz   cl
0x1800bb3a9  mov     eax, [rsi+14h]
0x1800bb3ac  mov     [rbp+var_38], eax
0x1800bb3af  lea     rax, [rbp+var_20]
0x1800bb3b3  mov     [rbp+var_28], rax
0x1800bb3b7  lea     rax, [rbp+var_3C]
0x1800bb3bb  mov     [rsp+80h+var_48], rax
0x1800bb3c0  lea     rax, [rbp+var_40]
0x1800bb3c4  mov     [rsp+80h+var_50], rax
0x1800bb3c9  lea     rax, [rbp+var_38]
0x1800bb3cd  mov     [rsp+80h+var_58], rax
0x1800bb3d2  lea     rax, [rbp+var_28]
0x1800bb3d6  mov     [rsp+80h+var_60], rax
0x1800bb3db  mov     [rbp+var_3C], ecx
0x1800bb3de  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bb3e3  mov     rcx, [rsi]
0x1800bb3e6  test    rcx, rcx
0x1800bb3e9  jz      loc_1800BB5AE
0x1800bb3ef  mov     rax, [rcx]
0x1800bb3f2  test    rax, rax
0x1800bb3f5  jz      loc_1800BB5AE
0x1800bb3fb  mov     rax, [rax+18h]
0x1800bb3ff  lea     r8, [rdi+20h]
0x1800bb403  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bb40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb40f  mov     ebx, eax
0x1800bb411  test    eax, eax
0x1800bb413  jnz     loc_1800BB5B3
0x1800bb419  cmp     [rsi+10h], r14d
0x1800bb41d  jz      loc_1800BB547
0x1800bb423  lea     rbx, [rdi+148h]
0x1800bb42a  mov     rcx, rbx
0x1800bb42d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bb432  mov     rcx, rbx; struct CSpJobMgr **
0x1800bb435  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bb43a  test    eax, eax
0x1800bb43c  jnz     short loc_1800BB446
0x1800bb43e  lea     ebx, [rax+1Ch]
0x1800bb441  jmp     loc_1800BB5B3
0x1800bb446  mov     ecx, 10h; Size
0x1800bb44b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bb450  xor     r8d, r8d; pcbe
0x1800bb453  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bb45a  mov     rdx, rax; pv
0x1800bb45d  mov     r15, rax
0x1800bb460  mov     [rax], rdi
0x1800bb463  call    cs:__imp_CreateThreadpoolWork
0x1800bb469  mov     r14, rax
0x1800bb46c  test    rax, rax
0x1800bb46f  jnz     short loc_1800BB47D
0x1800bb471  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bb476  mov     ebx, eax
0x1800bb478  jmp     loc_1800BB5B3
0x1800bb47d  call    cs:__imp_GetCurrentThread
0x1800bb483  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bb487  xor     r8d, r8d; OpenAsSelf
0x1800bb48a  mov     rcx, rax; ThreadHandle
0x1800bb48d  mov     edx, 2000Ch; DesiredAccess
0x1800bb492  call    cs:__imp_OpenThreadToken
0x1800bb498  test    eax, eax
0x1800bb49a  jnz     short loc_1800BB4A9
0x1800bb49c  call    cs:__imp_GetLastError
0x1800bb4a2  cmp     eax, 3F0h
0x1800bb4a7  jnz     short loc_1800BB471
0x1800bb4a9  mov     rax, [rbp+TokenHandle]
0x1800bb4ad  mov     r8, r13
0x1800bb4b0  mov     [r15+8], rax
0x1800bb4b4  mov     rcx, rdi
0x1800bb4b7  mov     rax, [rdi]
0x1800bb4ba  mov     rdx, [rsi+8]
0x1800bb4be  mov     rax, [rax+18h]
0x1800bb4c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb4c7  mov     rax, [rdi]
0x1800bb4ca  mov     rdx, r12
0x1800bb4cd  mov     rcx, rdi
0x1800bb4d0  mov     rax, [rax+28h]
0x1800bb4d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb4d9  mov     ebx, eax
0x1800bb4db  test    eax, eax
0x1800bb4dd  jz      short loc_1800BB4E8
0x1800bb4df  cmp     eax, 7
0x1800bb4e2  jnz     loc_1800BB5B3
0x1800bb4e8  mov     rax, [rdi]
0x1800bb4eb  mov     rdx, r12
0x1800bb4ee  mov     rcx, rdi
0x1800bb4f1  mov     rax, [rax+38h]
0x1800bb4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb4fa  mov     ebx, eax
0x1800bb4fc  test    eax, eax
0x1800bb4fe  jnz     loc_1800BB5B3
0x1800bb504  mov     rax, [rdi+150h]
0x1800bb50b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bb512  jnz     short loc_1800BB528
0x1800bb514  mov     rax, [rdi+158h]
0x1800bb51b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bb522  jz      loc_1800BB5B3
0x1800bb528  mov     rdx, r12
0x1800bb52b  mov     rcx, rdi
0x1800bb52e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bb533  mov     ebx, eax
0x1800bb535  test    eax, eax
0x1800bb537  jnz     short loc_1800BB5B3
0x1800bb539  mov     rcx, r14; pwk
0x1800bb53c  call    cs:__imp_SubmitThreadpoolWork
0x1800bb542  jmp     loc_1800BB5F5
0x1800bb547  mov     rax, [rdi]
0x1800bb54a  mov     r8, r13
0x1800bb54d  mov     rdx, [rsi+8]
0x1800bb551  mov     rcx, rdi
0x1800bb554  mov     rax, [rax+10h]
0x1800bb558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb55d  mov     rax, [rdi]
0x1800bb560  mov     rdx, r12
0x1800bb563  mov     rcx, rdi
0x1800bb566  mov     rax, [rax+30h]
0x1800bb56a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb56f  mov     ebx, eax
0x1800bb571  test    eax, eax
0x1800bb573  jz      short loc_1800BB57A
0x1800bb575  cmp     eax, 7
0x1800bb578  jnz     short loc_1800BB5B3
0x1800bb57a  mov     rax, [rdi]
0x1800bb57d  mov     rdx, r12
0x1800bb580  mov     rcx, rdi
0x1800bb583  mov     rax, [rax+28h]
0x1800bb587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb58c  mov     ebx, eax
0x1800bb58e  test    eax, eax
0x1800bb590  jz      short loc_1800BB597
0x1800bb592  cmp     eax, 7
0x1800bb595  jnz     short loc_1800BB5B3
0x1800bb597  mov     rax, [rdi]
0x1800bb59a  mov     rdx, r12
0x1800bb59d  mov     rcx, rdi
0x1800bb5a0  mov     rax, [rax+38h]
0x1800bb5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb5a9  jmp     loc_1800BB476
0x1800bb5ae  mov     ebx, 4
0x1800bb5b3  mov     rax, [rdi]
0x1800bb5b6  mov     edx, 1
0x1800bb5bb  mov     rcx, rdi
0x1800bb5be  mov     rax, [rax]
0x1800bb5c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb5c6  test    r15, r15
0x1800bb5c9  jz      short loc_1800BB5D8
0x1800bb5cb  mov     edx, 10h
0x1800bb5d0  mov     rcx, r15; Block
0x1800bb5d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bb5d8  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bb5dc  test    rcx, rcx
0x1800bb5df  jz      short loc_1800BB5E7
0x1800bb5e1  call    cs:__imp_CloseHandle
0x1800bb5e7  test    r14, r14
0x1800bb5ea  jz      short loc_1800BB5F5
0x1800bb5ec  mov     rcx, r14; pwk
0x1800bb5ef  call    cs:__imp_CloseThreadpoolWork
0x1800bb5f5  mov     eax, ebx
0x1800bb5f7  mov     rcx, [rbp+var_8]
0x1800bb5fb  xor     rcx, rsp; StackCookie
0x1800bb5fe  call    __security_check_cookie
0x1800bb603  mov     rbx, [rsp+80h+arg_18]
0x1800bb60b  add     rsp, 80h
0x1800bb612  pop     r15
0x1800bb614  pop     r14
0x1800bb616  pop     r13
0x1800bb618  pop     r12
0x1800bb61a  pop     rdi
0x1800bb61b  pop     rsi
0x1800bb61c  pop     rbp
0x1800bb61d  retn
```
