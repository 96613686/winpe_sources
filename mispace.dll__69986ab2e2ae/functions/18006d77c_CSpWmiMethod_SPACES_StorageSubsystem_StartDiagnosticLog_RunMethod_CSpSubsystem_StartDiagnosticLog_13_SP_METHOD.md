# CSpWmiMethod<_SPACES_StorageSubsystem_StartDiagnosticLog>::RunMethod<CSpSubsystem::StartDiagnosticLog,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006d77c`
- end: `0x18006daf9`
- name: `??$RunMethod@VStartDiagnosticLog@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_StartDiagnosticLog@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180057100`
- `0x1800743e0`

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
- `0x18006d77c`
- `0x18006e444`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d95a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d95a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006d92f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006d92f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006d94a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006d94a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006d90f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006d90f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006da04`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006da04`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006dac3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006dac3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006daaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006daaf`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_StartDiagnosticLog>::RunMethod<CSpSubsystem::StartDiagnosticLog,13>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 started; // rax
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
  CSpSubsystem::StartDiagnosticLog *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::StartDiagnosticLog *)operator new(0x160u);
  started = CSpSubsystem::StartDiagnosticLog::StartDiagnosticLog(v25);
  v8 = started;
  if ( started )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)started + 8LL))(started, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpSubsystem::StartDiagnosticLog *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_180316483,
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
0x18006d77c  mov     [rsp-38h+arg_18], rbx
0x18006d781  push    rbp
0x18006d782  push    rsi
0x18006d783  push    rdi
0x18006d784  push    r12
0x18006d786  push    r13
0x18006d788  push    r14
0x18006d78a  push    r15
0x18006d78c  mov     rbp, rsp
0x18006d78f  sub     rsp, 80h
0x18006d796  mov     rax, cs:__security_cookie
0x18006d79d  xor     rax, rsp
0x18006d7a0  mov     [rbp+var_8], rax
0x18006d7a4  xor     eax, eax
0x18006d7a6  mov     rsi, rcx
0x18006d7a9  xorps   xmm0, xmm0
0x18006d7ac  mov     [rbp+var_10], eax
0x18006d7af  mov     ecx, 160h; Size
0x18006d7b4  mov     [rbp+var_40], eax
0x18006d7b7  movups  [rbp+var_20], xmm0
0x18006d7bb  mov     [rbp+TokenHandle], rax
0x18006d7bf  mov     r12, r8
0x18006d7c2  mov     r13, rdx
0x18006d7c5  xor     r14d, r14d
0x18006d7c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006d7cd  mov     rcx, rax; this
0x18006d7d0  mov     [rbp+var_28], rax
0x18006d7d4  call    ??0StartDiagnosticLog@CSpSubsystem@@QEAA@XZ; CSpSubsystem::StartDiagnosticLog::StartDiagnosticLog(void)
0x18006d7d9  mov     rdi, rax
0x18006d7dc  test    rax, rax
0x18006d7df  jnz     short loc_18006D7E9
0x18006d7e1  lea     ebx, [rax+1Bh]
0x18006d7e4  jmp     loc_18006DAA6
0x18006d7e9  mov     rax, [rax]
0x18006d7ec  mov     rdx, rsi
0x18006d7ef  mov     rcx, rdi
0x18006d7f2  xor     r15d, r15d
0x18006d7f5  mov     rax, [rax+8]
0x18006d7f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d7fe  lea     rcx, [rbp+var_40]
0x18006d802  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006d807  mov     [rdi+1Ch], eax
0x18006d80a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006d80e  mov     ecx, [rsi+14h]; unsigned int
0x18006d811  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006d816  mov     eax, cs:dword_18039EB68
0x18006d81c  cmp     eax, 5
0x18006d81f  jbe     short loc_18006D88F
0x18006d821  mov     rdx, 400000000000h
0x18006d82b  lea     rcx, dword_18039EB68
0x18006d832  call    _tlgKeywordOn
0x18006d837  test    al, al
0x18006d839  jz      short loc_18006D88F
0x18006d83b  mov     eax, [rbp+var_40]
0x18006d83e  lea     rdx, byte_180316483
0x18006d845  xor     ecx, ecx
0x18006d847  cmp     [rdi+1Ch], eax
0x18006d84a  movzx   eax, word ptr [rbp+var_10]
0x18006d84e  mov     word ptr [rbp+var_40], ax
0x18006d852  setnz   cl
0x18006d855  mov     eax, [rsi+14h]
0x18006d858  mov     [rbp+var_38], eax
0x18006d85b  lea     rax, [rbp+var_20]
0x18006d85f  mov     [rbp+var_28], rax
0x18006d863  lea     rax, [rbp+var_3C]
0x18006d867  mov     [rsp+80h+var_48], rax
0x18006d86c  lea     rax, [rbp+var_40]
0x18006d870  mov     [rsp+80h+var_50], rax
0x18006d875  lea     rax, [rbp+var_38]
0x18006d879  mov     [rsp+80h+var_58], rax
0x18006d87e  lea     rax, [rbp+var_28]
0x18006d882  mov     [rsp+80h+var_60], rax
0x18006d887  mov     [rbp+var_3C], ecx
0x18006d88a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006d88f  mov     rcx, [rsi]
0x18006d892  test    rcx, rcx
0x18006d895  jz      loc_18006DA7C
0x18006d89b  mov     rax, [rcx]
0x18006d89e  test    rax, rax
0x18006d8a1  jz      loc_18006DA7C
0x18006d8a7  mov     rax, [rax+18h]
0x18006d8ab  lea     r8, [rdi+20h]
0x18006d8af  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006d8b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d8bb  mov     ebx, eax
0x18006d8bd  test    eax, eax
0x18006d8bf  jnz     loc_18006DA81
0x18006d8c5  cmp     [rsi+10h], r14d
0x18006d8c9  jz      loc_18006DA15
0x18006d8cf  lea     rbx, [rdi+148h]
0x18006d8d6  mov     rcx, rbx
0x18006d8d9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006d8de  mov     rcx, rbx; struct CSpJobMgr **
0x18006d8e1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006d8e6  test    eax, eax
0x18006d8e8  jnz     short loc_18006D8F2
0x18006d8ea  lea     ebx, [rax+1Ch]
0x18006d8ed  jmp     loc_18006DA81
0x18006d8f2  mov     ecx, 10h; Size
0x18006d8f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006d8fc  xor     r8d, r8d; pcbe
0x18006d8ff  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006d906  mov     rdx, rax; pv
0x18006d909  mov     r15, rax
0x18006d90c  mov     [rax], rdi
0x18006d90f  call    cs:__imp_CreateThreadpoolWork
0x18006d916  nop     dword ptr [rax+rax+00h]
0x18006d91b  mov     r14, rax
0x18006d91e  test    rax, rax
0x18006d921  jnz     short loc_18006D92F
0x18006d923  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006d928  mov     ebx, eax
0x18006d92a  jmp     loc_18006DA81
0x18006d92f  call    cs:__imp_GetCurrentThread
0x18006d936  nop     dword ptr [rax+rax+00h]
0x18006d93b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006d93f  xor     r8d, r8d; OpenAsSelf
0x18006d942  mov     rcx, rax; ThreadHandle
0x18006d945  mov     edx, 2000Ch; DesiredAccess
0x18006d94a  call    cs:__imp_OpenThreadToken
0x18006d951  nop     dword ptr [rax+rax+00h]
0x18006d956  test    eax, eax
0x18006d958  jnz     short loc_18006D96D
0x18006d95a  call    cs:__imp_GetLastError
0x18006d961  nop     dword ptr [rax+rax+00h]
0x18006d966  cmp     eax, 3F0h
0x18006d96b  jnz     short loc_18006D923
0x18006d96d  mov     rax, [rbp+TokenHandle]
0x18006d971  mov     r8, r13
0x18006d974  mov     [r15+8], rax
0x18006d978  mov     rcx, rdi
0x18006d97b  mov     rax, [rdi]
0x18006d97e  mov     rdx, [rsi+8]
0x18006d982  mov     rax, [rax+18h]
0x18006d986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d98b  mov     rax, [rdi]
0x18006d98e  mov     rdx, r12
0x18006d991  mov     rcx, rdi
0x18006d994  mov     rax, [rax+28h]
0x18006d998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d99d  mov     ebx, eax
0x18006d99f  test    eax, eax
0x18006d9a1  jz      short loc_18006D9AC
0x18006d9a3  cmp     eax, 7
0x18006d9a6  jnz     loc_18006DA81
0x18006d9ac  mov     rax, [rdi]
0x18006d9af  mov     rdx, r12
0x18006d9b2  mov     rcx, rdi
0x18006d9b5  mov     rax, [rax+38h]
0x18006d9b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d9be  mov     ebx, eax
0x18006d9c0  test    eax, eax
0x18006d9c2  jnz     loc_18006DA81
0x18006d9c8  mov     rax, [rdi+150h]
0x18006d9cf  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006d9d6  jnz     short loc_18006D9EC
0x18006d9d8  mov     rax, [rdi+158h]
0x18006d9df  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006d9e6  jz      loc_18006DA81
0x18006d9ec  mov     rdx, r12
0x18006d9ef  mov     rcx, rdi
0x18006d9f2  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006d9f7  mov     ebx, eax
0x18006d9f9  test    eax, eax
0x18006d9fb  jnz     loc_18006DA81
0x18006da01  mov     rcx, r14; pwk
0x18006da04  call    cs:__imp_SubmitThreadpoolWork
0x18006da0b  nop     dword ptr [rax+rax+00h]
0x18006da10  jmp     loc_18006DACF
0x18006da15  mov     rax, [rdi]
0x18006da18  mov     r8, r13
0x18006da1b  mov     rdx, [rsi+8]
0x18006da1f  mov     rcx, rdi
0x18006da22  mov     rax, [rax+10h]
0x18006da26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006da2b  mov     rax, [rdi]
0x18006da2e  mov     rdx, r12
0x18006da31  mov     rcx, rdi
0x18006da34  mov     rax, [rax+30h]
0x18006da38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006da3d  mov     ebx, eax
0x18006da3f  test    eax, eax
0x18006da41  jz      short loc_18006DA48
0x18006da43  cmp     eax, 7
0x18006da46  jnz     short loc_18006DA81
0x18006da48  mov     rax, [rdi]
0x18006da4b  mov     rdx, r12
0x18006da4e  mov     rcx, rdi
0x18006da51  mov     rax, [rax+28h]
0x18006da55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006da5a  mov     ebx, eax
0x18006da5c  test    eax, eax
0x18006da5e  jz      short loc_18006DA65
0x18006da60  cmp     eax, 7
0x18006da63  jnz     short loc_18006DA81
0x18006da65  mov     rax, [rdi]
0x18006da68  mov     rdx, r12
0x18006da6b  mov     rcx, rdi
0x18006da6e  mov     rax, [rax+38h]
0x18006da72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006da77  jmp     loc_18006D928
0x18006da7c  mov     ebx, 4
0x18006da81  mov     rax, [rdi]
0x18006da84  mov     edx, 1
0x18006da89  mov     rcx, rdi
0x18006da8c  mov     rax, [rax]
0x18006da8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006da94  test    r15, r15
0x18006da97  jz      short loc_18006DAA6
0x18006da99  mov     edx, 10h
0x18006da9e  mov     rcx, r15; Block
0x18006daa1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006daa6  mov     rcx, [rbp+TokenHandle]; hObject
0x18006daaa  test    rcx, rcx
0x18006daad  jz      short loc_18006DABB
0x18006daaf  call    cs:__imp_CloseHandle
0x18006dab6  nop     dword ptr [rax+rax+00h]
0x18006dabb  test    r14, r14
0x18006dabe  jz      short loc_18006DACF
0x18006dac0  mov     rcx, r14; pwk
0x18006dac3  call    cs:__imp_CloseThreadpoolWork
0x18006daca  nop     dword ptr [rax+rax+00h]
0x18006dacf  mov     eax, ebx
0x18006dad1  mov     rcx, [rbp+var_8]
0x18006dad5  xor     rcx, rsp; StackCookie
0x18006dad8  call    __security_check_cookie
0x18006dadd  mov     rbx, [rsp+80h+arg_18]
0x18006dae5  add     rsp, 80h
0x18006daec  pop     r15
0x18006daee  pop     r14
0x18006daf0  pop     r13
0x18006daf2  pop     r12
0x18006daf4  pop     rdi
0x18006daf5  pop     rsi
0x18006daf6  pop     rbp
0x18006daf7  retn
```
