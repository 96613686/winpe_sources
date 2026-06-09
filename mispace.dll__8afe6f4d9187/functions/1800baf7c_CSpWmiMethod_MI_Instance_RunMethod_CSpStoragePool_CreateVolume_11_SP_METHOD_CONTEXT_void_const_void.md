# CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::CreateVolume,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800baf7c`
- end: `0x1800bb2ca`
- name: `??$RunMethod@VCreateVolume@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800baf7c`
- `0x1800bde64`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb148`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bb129`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bb129`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bb13e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bb13e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bb10f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bb10f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bb1e8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bb1e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bb29b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bb29b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb28d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb28d`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::CreateVolume,11>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 Volume; // rax
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
  CSpStoragePool::CreateVolume *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::CreateVolume *)operator new(0x240u);
  Volume = CSpStoragePool::CreateVolume::CreateVolume(v25);
  v8 = Volume;
  if ( Volume )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)Volume + 8LL))(Volume, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStoragePool::CreateVolume *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18032B409,
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
0x1800baf7c  mov     [rsp-38h+arg_18], rbx
0x1800baf81  push    rbp
0x1800baf82  push    rsi
0x1800baf83  push    rdi
0x1800baf84  push    r12
0x1800baf86  push    r13
0x1800baf88  push    r14
0x1800baf8a  push    r15
0x1800baf8c  mov     rbp, rsp
0x1800baf8f  sub     rsp, 80h
0x1800baf96  mov     rax, cs:__security_cookie
0x1800baf9d  xor     rax, rsp
0x1800bafa0  mov     [rbp+var_8], rax
0x1800bafa4  xor     eax, eax
0x1800bafa6  mov     rsi, rcx
0x1800bafa9  xorps   xmm0, xmm0
0x1800bafac  mov     [rbp+var_10], eax
0x1800bafaf  mov     ecx, 240h; Size
0x1800bafb4  mov     [rbp+var_40], eax
0x1800bafb7  movups  [rbp+var_20], xmm0
0x1800bafbb  mov     [rbp+TokenHandle], rax
0x1800bafbf  mov     r12, r8
0x1800bafc2  mov     r13, rdx
0x1800bafc5  xor     r14d, r14d
0x1800bafc8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bafcd  mov     rcx, rax; this
0x1800bafd0  mov     [rbp+var_28], rax
0x1800bafd4  call    ??0CreateVolume@CSpStoragePool@@QEAA@XZ; CSpStoragePool::CreateVolume::CreateVolume(void)
0x1800bafd9  mov     rdi, rax
0x1800bafdc  test    rax, rax
0x1800bafdf  jnz     short loc_1800BAFE9
0x1800bafe1  lea     ebx, [rax+1Bh]
0x1800bafe4  jmp     loc_1800BB284
0x1800bafe9  mov     rax, [rax]
0x1800bafec  mov     rdx, rsi
0x1800bafef  mov     rcx, rdi
0x1800baff2  xor     r15d, r15d
0x1800baff5  mov     rax, [rax+8]
0x1800baff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baffe  lea     rcx, [rbp+var_40]
0x1800bb002  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bb007  mov     [rdi+1Ch], eax
0x1800bb00a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bb00e  mov     ecx, [rsi+14h]; unsigned int
0x1800bb011  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bb016  mov     eax, cs:dword_180397B68
0x1800bb01c  cmp     eax, 5
0x1800bb01f  jbe     short loc_1800BB08F
0x1800bb021  mov     rdx, 400000000000h
0x1800bb02b  lea     rcx, dword_180397B68
0x1800bb032  call    _tlgKeywordOn
0x1800bb037  test    al, al
0x1800bb039  jz      short loc_1800BB08F
0x1800bb03b  mov     eax, [rbp+var_40]
0x1800bb03e  lea     rdx, byte_18032B409
0x1800bb045  xor     ecx, ecx
0x1800bb047  cmp     [rdi+1Ch], eax
0x1800bb04a  movzx   eax, word ptr [rbp+var_10]
0x1800bb04e  mov     word ptr [rbp+var_40], ax
0x1800bb052  setnz   cl
0x1800bb055  mov     eax, [rsi+14h]
0x1800bb058  mov     [rbp+var_38], eax
0x1800bb05b  lea     rax, [rbp+var_20]
0x1800bb05f  mov     [rbp+var_28], rax
0x1800bb063  lea     rax, [rbp+var_3C]
0x1800bb067  mov     [rsp+80h+var_48], rax
0x1800bb06c  lea     rax, [rbp+var_40]
0x1800bb070  mov     [rsp+80h+var_50], rax
0x1800bb075  lea     rax, [rbp+var_38]
0x1800bb079  mov     [rsp+80h+var_58], rax
0x1800bb07e  lea     rax, [rbp+var_28]
0x1800bb082  mov     [rsp+80h+var_60], rax
0x1800bb087  mov     [rbp+var_3C], ecx
0x1800bb08a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bb08f  mov     rcx, [rsi]
0x1800bb092  test    rcx, rcx
0x1800bb095  jz      loc_1800BB25A
0x1800bb09b  mov     rax, [rcx]
0x1800bb09e  test    rax, rax
0x1800bb0a1  jz      loc_1800BB25A
0x1800bb0a7  mov     rax, [rax+18h]
0x1800bb0ab  lea     r8, [rdi+20h]
0x1800bb0af  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bb0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb0bb  mov     ebx, eax
0x1800bb0bd  test    eax, eax
0x1800bb0bf  jnz     loc_1800BB25F
0x1800bb0c5  cmp     [rsi+10h], r14d
0x1800bb0c9  jz      loc_1800BB1F3
0x1800bb0cf  lea     rbx, [rdi+148h]
0x1800bb0d6  mov     rcx, rbx
0x1800bb0d9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bb0de  mov     rcx, rbx; struct CSpJobMgr **
0x1800bb0e1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bb0e6  test    eax, eax
0x1800bb0e8  jnz     short loc_1800BB0F2
0x1800bb0ea  lea     ebx, [rax+1Ch]
0x1800bb0ed  jmp     loc_1800BB25F
0x1800bb0f2  mov     ecx, 10h; Size
0x1800bb0f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bb0fc  xor     r8d, r8d; pcbe
0x1800bb0ff  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bb106  mov     rdx, rax; pv
0x1800bb109  mov     r15, rax
0x1800bb10c  mov     [rax], rdi
0x1800bb10f  call    cs:__imp_CreateThreadpoolWork
0x1800bb115  mov     r14, rax
0x1800bb118  test    rax, rax
0x1800bb11b  jnz     short loc_1800BB129
0x1800bb11d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bb122  mov     ebx, eax
0x1800bb124  jmp     loc_1800BB25F
0x1800bb129  call    cs:__imp_GetCurrentThread
0x1800bb12f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bb133  xor     r8d, r8d; OpenAsSelf
0x1800bb136  mov     rcx, rax; ThreadHandle
0x1800bb139  mov     edx, 2000Ch; DesiredAccess
0x1800bb13e  call    cs:__imp_OpenThreadToken
0x1800bb144  test    eax, eax
0x1800bb146  jnz     short loc_1800BB155
0x1800bb148  call    cs:__imp_GetLastError
0x1800bb14e  cmp     eax, 3F0h
0x1800bb153  jnz     short loc_1800BB11D
0x1800bb155  mov     rax, [rbp+TokenHandle]
0x1800bb159  mov     r8, r13
0x1800bb15c  mov     [r15+8], rax
0x1800bb160  mov     rcx, rdi
0x1800bb163  mov     rax, [rdi]
0x1800bb166  mov     rdx, [rsi+8]
0x1800bb16a  mov     rax, [rax+18h]
0x1800bb16e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb173  mov     rax, [rdi]
0x1800bb176  mov     rdx, r12
0x1800bb179  mov     rcx, rdi
0x1800bb17c  mov     rax, [rax+28h]
0x1800bb180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb185  mov     ebx, eax
0x1800bb187  test    eax, eax
0x1800bb189  jz      short loc_1800BB194
0x1800bb18b  cmp     eax, 7
0x1800bb18e  jnz     loc_1800BB25F
0x1800bb194  mov     rax, [rdi]
0x1800bb197  mov     rdx, r12
0x1800bb19a  mov     rcx, rdi
0x1800bb19d  mov     rax, [rax+38h]
0x1800bb1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb1a6  mov     ebx, eax
0x1800bb1a8  test    eax, eax
0x1800bb1aa  jnz     loc_1800BB25F
0x1800bb1b0  mov     rax, [rdi+150h]
0x1800bb1b7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bb1be  jnz     short loc_1800BB1D4
0x1800bb1c0  mov     rax, [rdi+158h]
0x1800bb1c7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bb1ce  jz      loc_1800BB25F
0x1800bb1d4  mov     rdx, r12
0x1800bb1d7  mov     rcx, rdi
0x1800bb1da  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bb1df  mov     ebx, eax
0x1800bb1e1  test    eax, eax
0x1800bb1e3  jnz     short loc_1800BB25F
0x1800bb1e5  mov     rcx, r14; pwk
0x1800bb1e8  call    cs:__imp_SubmitThreadpoolWork
0x1800bb1ee  jmp     loc_1800BB2A1
0x1800bb1f3  mov     rax, [rdi]
0x1800bb1f6  mov     r8, r13
0x1800bb1f9  mov     rdx, [rsi+8]
0x1800bb1fd  mov     rcx, rdi
0x1800bb200  mov     rax, [rax+10h]
0x1800bb204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb209  mov     rax, [rdi]
0x1800bb20c  mov     rdx, r12
0x1800bb20f  mov     rcx, rdi
0x1800bb212  mov     rax, [rax+30h]
0x1800bb216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb21b  mov     ebx, eax
0x1800bb21d  test    eax, eax
0x1800bb21f  jz      short loc_1800BB226
0x1800bb221  cmp     eax, 7
0x1800bb224  jnz     short loc_1800BB25F
0x1800bb226  mov     rax, [rdi]
0x1800bb229  mov     rdx, r12
0x1800bb22c  mov     rcx, rdi
0x1800bb22f  mov     rax, [rax+28h]
0x1800bb233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb238  mov     ebx, eax
0x1800bb23a  test    eax, eax
0x1800bb23c  jz      short loc_1800BB243
0x1800bb23e  cmp     eax, 7
0x1800bb241  jnz     short loc_1800BB25F
0x1800bb243  mov     rax, [rdi]
0x1800bb246  mov     rdx, r12
0x1800bb249  mov     rcx, rdi
0x1800bb24c  mov     rax, [rax+38h]
0x1800bb250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb255  jmp     loc_1800BB122
0x1800bb25a  mov     ebx, 4
0x1800bb25f  mov     rax, [rdi]
0x1800bb262  mov     edx, 1
0x1800bb267  mov     rcx, rdi
0x1800bb26a  mov     rax, [rax]
0x1800bb26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb272  test    r15, r15
0x1800bb275  jz      short loc_1800BB284
0x1800bb277  mov     edx, 10h
0x1800bb27c  mov     rcx, r15; Block
0x1800bb27f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bb284  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bb288  test    rcx, rcx
0x1800bb28b  jz      short loc_1800BB293
0x1800bb28d  call    cs:__imp_CloseHandle
0x1800bb293  test    r14, r14
0x1800bb296  jz      short loc_1800BB2A1
0x1800bb298  mov     rcx, r14; pwk
0x1800bb29b  call    cs:__imp_CloseThreadpoolWork
0x1800bb2a1  mov     eax, ebx
0x1800bb2a3  mov     rcx, [rbp+var_8]
0x1800bb2a7  xor     rcx, rsp; StackCookie
0x1800bb2aa  call    __security_check_cookie
0x1800bb2af  mov     rbx, [rsp+80h+arg_18]
0x1800bb2b7  add     rsp, 80h
0x1800bb2be  pop     r15
0x1800bb2c0  pop     r14
0x1800bb2c2  pop     r13
0x1800bb2c4  pop     r12
0x1800bb2c6  pop     rdi
0x1800bb2c7  pop     rsi
0x1800bb2c8  pop     rbp
0x1800bb2c9  retn
```
