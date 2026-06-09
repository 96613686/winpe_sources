# CSpWmiMethod<_SPACES_StorageSubsystem_StopDiagnosticLog>::RunMethod<CSpSubsystem::StopDiagnosticLog,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006b754`
- end: `0x18006baa2`
- name: `??$RunMethod@VStopDiagnosticLog@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_StopDiagnosticLog@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800555c0`
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
- `0x18006b754`
- `0x18006c0c0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b920`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006b901`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006b901`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006b916`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006b916`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006b8e7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006b8e7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006b9c0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006b9c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006ba73`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006ba73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ba65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ba65`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_StopDiagnosticLog>::RunMethod<CSpSubsystem::StopDiagnosticLog,13>(
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
  CSpSubsystem::StopDiagnosticLog *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::StopDiagnosticLog *)operator new(0x160u);
  v7 = CSpSubsystem::StopDiagnosticLog::StopDiagnosticLog(v25);
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
      v25 = (CSpSubsystem::StopDiagnosticLog *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_180310A33,
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
0x18006b754  mov     [rsp-38h+arg_18], rbx
0x18006b759  push    rbp
0x18006b75a  push    rsi
0x18006b75b  push    rdi
0x18006b75c  push    r12
0x18006b75e  push    r13
0x18006b760  push    r14
0x18006b762  push    r15
0x18006b764  mov     rbp, rsp
0x18006b767  sub     rsp, 80h
0x18006b76e  mov     rax, cs:__security_cookie
0x18006b775  xor     rax, rsp
0x18006b778  mov     [rbp+var_8], rax
0x18006b77c  xor     eax, eax
0x18006b77e  mov     rsi, rcx
0x18006b781  xorps   xmm0, xmm0
0x18006b784  mov     [rbp+var_10], eax
0x18006b787  mov     ecx, 160h; Size
0x18006b78c  mov     [rbp+var_40], eax
0x18006b78f  movups  [rbp+var_20], xmm0
0x18006b793  mov     [rbp+TokenHandle], rax
0x18006b797  mov     r12, r8
0x18006b79a  mov     r13, rdx
0x18006b79d  xor     r14d, r14d
0x18006b7a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b7a5  mov     rcx, rax; this
0x18006b7a8  mov     [rbp+var_28], rax
0x18006b7ac  call    ??0StopDiagnosticLog@CSpSubsystem@@QEAA@XZ; CSpSubsystem::StopDiagnosticLog::StopDiagnosticLog(void)
0x18006b7b1  mov     rdi, rax
0x18006b7b4  test    rax, rax
0x18006b7b7  jnz     short loc_18006B7C1
0x18006b7b9  lea     ebx, [rax+1Bh]
0x18006b7bc  jmp     loc_18006BA5C
0x18006b7c1  mov     rax, [rax]
0x18006b7c4  mov     rdx, rsi
0x18006b7c7  mov     rcx, rdi
0x18006b7ca  xor     r15d, r15d
0x18006b7cd  mov     rax, [rax+8]
0x18006b7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b7d6  lea     rcx, [rbp+var_40]
0x18006b7da  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006b7df  mov     [rdi+1Ch], eax
0x18006b7e2  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006b7e6  mov     ecx, [rsi+14h]; unsigned int
0x18006b7e9  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006b7ee  mov     eax, cs:dword_180397B68
0x18006b7f4  cmp     eax, 5
0x18006b7f7  jbe     short loc_18006B867
0x18006b7f9  mov     rdx, 400000000000h
0x18006b803  lea     rcx, dword_180397B68
0x18006b80a  call    _tlgKeywordOn
0x18006b80f  test    al, al
0x18006b811  jz      short loc_18006B867
0x18006b813  mov     eax, [rbp+var_40]
0x18006b816  lea     rdx, byte_180310A33
0x18006b81d  xor     ecx, ecx
0x18006b81f  cmp     [rdi+1Ch], eax
0x18006b822  movzx   eax, word ptr [rbp+var_10]
0x18006b826  mov     word ptr [rbp+var_40], ax
0x18006b82a  setnz   cl
0x18006b82d  mov     eax, [rsi+14h]
0x18006b830  mov     [rbp+var_38], eax
0x18006b833  lea     rax, [rbp+var_20]
0x18006b837  mov     [rbp+var_28], rax
0x18006b83b  lea     rax, [rbp+var_3C]
0x18006b83f  mov     [rsp+80h+var_48], rax
0x18006b844  lea     rax, [rbp+var_40]
0x18006b848  mov     [rsp+80h+var_50], rax
0x18006b84d  lea     rax, [rbp+var_38]
0x18006b851  mov     [rsp+80h+var_58], rax
0x18006b856  lea     rax, [rbp+var_28]
0x18006b85a  mov     [rsp+80h+var_60], rax
0x18006b85f  mov     [rbp+var_3C], ecx
0x18006b862  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006b867  mov     rcx, [rsi]
0x18006b86a  test    rcx, rcx
0x18006b86d  jz      loc_18006BA32
0x18006b873  mov     rax, [rcx]
0x18006b876  test    rax, rax
0x18006b879  jz      loc_18006BA32
0x18006b87f  mov     rax, [rax+18h]
0x18006b883  lea     r8, [rdi+20h]
0x18006b887  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006b88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b893  mov     ebx, eax
0x18006b895  test    eax, eax
0x18006b897  jnz     loc_18006BA37
0x18006b89d  cmp     [rsi+10h], r14d
0x18006b8a1  jz      loc_18006B9CB
0x18006b8a7  lea     rbx, [rdi+148h]
0x18006b8ae  mov     rcx, rbx
0x18006b8b1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006b8b6  mov     rcx, rbx; struct CSpJobMgr **
0x18006b8b9  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006b8be  test    eax, eax
0x18006b8c0  jnz     short loc_18006B8CA
0x18006b8c2  lea     ebx, [rax+1Ch]
0x18006b8c5  jmp     loc_18006BA37
0x18006b8ca  mov     ecx, 10h; Size
0x18006b8cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b8d4  xor     r8d, r8d; pcbe
0x18006b8d7  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006b8de  mov     rdx, rax; pv
0x18006b8e1  mov     r15, rax
0x18006b8e4  mov     [rax], rdi
0x18006b8e7  call    cs:__imp_CreateThreadpoolWork
0x18006b8ed  mov     r14, rax
0x18006b8f0  test    rax, rax
0x18006b8f3  jnz     short loc_18006B901
0x18006b8f5  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006b8fa  mov     ebx, eax
0x18006b8fc  jmp     loc_18006BA37
0x18006b901  call    cs:__imp_GetCurrentThread
0x18006b907  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006b90b  xor     r8d, r8d; OpenAsSelf
0x18006b90e  mov     rcx, rax; ThreadHandle
0x18006b911  mov     edx, 2000Ch; DesiredAccess
0x18006b916  call    cs:__imp_OpenThreadToken
0x18006b91c  test    eax, eax
0x18006b91e  jnz     short loc_18006B92D
0x18006b920  call    cs:__imp_GetLastError
0x18006b926  cmp     eax, 3F0h
0x18006b92b  jnz     short loc_18006B8F5
0x18006b92d  mov     rax, [rbp+TokenHandle]
0x18006b931  mov     r8, r13
0x18006b934  mov     [r15+8], rax
0x18006b938  mov     rcx, rdi
0x18006b93b  mov     rax, [rdi]
0x18006b93e  mov     rdx, [rsi+8]
0x18006b942  mov     rax, [rax+18h]
0x18006b946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b94b  mov     rax, [rdi]
0x18006b94e  mov     rdx, r12
0x18006b951  mov     rcx, rdi
0x18006b954  mov     rax, [rax+28h]
0x18006b958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b95d  mov     ebx, eax
0x18006b95f  test    eax, eax
0x18006b961  jz      short loc_18006B96C
0x18006b963  cmp     eax, 7
0x18006b966  jnz     loc_18006BA37
0x18006b96c  mov     rax, [rdi]
0x18006b96f  mov     rdx, r12
0x18006b972  mov     rcx, rdi
0x18006b975  mov     rax, [rax+38h]
0x18006b979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b97e  mov     ebx, eax
0x18006b980  test    eax, eax
0x18006b982  jnz     loc_18006BA37
0x18006b988  mov     rax, [rdi+150h]
0x18006b98f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006b996  jnz     short loc_18006B9AC
0x18006b998  mov     rax, [rdi+158h]
0x18006b99f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006b9a6  jz      loc_18006BA37
0x18006b9ac  mov     rdx, r12
0x18006b9af  mov     rcx, rdi
0x18006b9b2  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006b9b7  mov     ebx, eax
0x18006b9b9  test    eax, eax
0x18006b9bb  jnz     short loc_18006BA37
0x18006b9bd  mov     rcx, r14; pwk
0x18006b9c0  call    cs:__imp_SubmitThreadpoolWork
0x18006b9c6  jmp     loc_18006BA79
0x18006b9cb  mov     rax, [rdi]
0x18006b9ce  mov     r8, r13
0x18006b9d1  mov     rdx, [rsi+8]
0x18006b9d5  mov     rcx, rdi
0x18006b9d8  mov     rax, [rax+10h]
0x18006b9dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b9e1  mov     rax, [rdi]
0x18006b9e4  mov     rdx, r12
0x18006b9e7  mov     rcx, rdi
0x18006b9ea  mov     rax, [rax+30h]
0x18006b9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b9f3  mov     ebx, eax
0x18006b9f5  test    eax, eax
0x18006b9f7  jz      short loc_18006B9FE
0x18006b9f9  cmp     eax, 7
0x18006b9fc  jnz     short loc_18006BA37
0x18006b9fe  mov     rax, [rdi]
0x18006ba01  mov     rdx, r12
0x18006ba04  mov     rcx, rdi
0x18006ba07  mov     rax, [rax+28h]
0x18006ba0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba10  mov     ebx, eax
0x18006ba12  test    eax, eax
0x18006ba14  jz      short loc_18006BA1B
0x18006ba16  cmp     eax, 7
0x18006ba19  jnz     short loc_18006BA37
0x18006ba1b  mov     rax, [rdi]
0x18006ba1e  mov     rdx, r12
0x18006ba21  mov     rcx, rdi
0x18006ba24  mov     rax, [rax+38h]
0x18006ba28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba2d  jmp     loc_18006B8FA
0x18006ba32  mov     ebx, 4
0x18006ba37  mov     rax, [rdi]
0x18006ba3a  mov     edx, 1
0x18006ba3f  mov     rcx, rdi
0x18006ba42  mov     rax, [rax]
0x18006ba45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba4a  test    r15, r15
0x18006ba4d  jz      short loc_18006BA5C
0x18006ba4f  mov     edx, 10h
0x18006ba54  mov     rcx, r15; Block
0x18006ba57  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006ba5c  mov     rcx, [rbp+TokenHandle]; hObject
0x18006ba60  test    rcx, rcx
0x18006ba63  jz      short loc_18006BA6B
0x18006ba65  call    cs:__imp_CloseHandle
0x18006ba6b  test    r14, r14
0x18006ba6e  jz      short loc_18006BA79
0x18006ba70  mov     rcx, r14; pwk
0x18006ba73  call    cs:__imp_CloseThreadpoolWork
0x18006ba79  mov     eax, ebx
0x18006ba7b  mov     rcx, [rbp+var_8]
0x18006ba7f  xor     rcx, rsp; StackCookie
0x18006ba82  call    __security_check_cookie
0x18006ba87  mov     rbx, [rsp+80h+arg_18]
0x18006ba8f  add     rsp, 80h
0x18006ba96  pop     r15
0x18006ba98  pop     r14
0x18006ba9a  pop     r13
0x18006ba9c  pop     r12
0x18006ba9e  pop     rdi
0x18006ba9f  pop     rsi
0x18006baa0  pop     rbp
0x18006baa1  retn
```
