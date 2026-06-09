# CSpWmiMethod<_MI_Instance>::RunMethod<CSpSubsystem::CreateStoragePool,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006c264`
- end: `0x18006c5e1`
- name: `??$RunMethod@VCreateStoragePool@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

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
- `0x18006c264`
- `0x18006e134`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c442`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006c417`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006c417`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006c432`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006c432`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006c3f7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006c3f7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006c4ec`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006c4ec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006c5ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006c5ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c597`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c597`

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
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpSubsystem::CreateStoragePool *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_180315B38,
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
0x18006c264  mov     [rsp-38h+arg_18], rbx
0x18006c269  push    rbp
0x18006c26a  push    rsi
0x18006c26b  push    rdi
0x18006c26c  push    r12
0x18006c26e  push    r13
0x18006c270  push    r14
0x18006c272  push    r15
0x18006c274  mov     rbp, rsp
0x18006c277  sub     rsp, 80h
0x18006c27e  mov     rax, cs:__security_cookie
0x18006c285  xor     rax, rsp
0x18006c288  mov     [rbp+var_8], rax
0x18006c28c  xor     eax, eax
0x18006c28e  mov     rsi, rcx
0x18006c291  xorps   xmm0, xmm0
0x18006c294  mov     [rbp+var_10], eax
0x18006c297  mov     ecx, 428h; Size
0x18006c29c  mov     [rbp+var_40], eax
0x18006c29f  movups  [rbp+var_20], xmm0
0x18006c2a3  mov     [rbp+TokenHandle], rax
0x18006c2a7  mov     r12, r8
0x18006c2aa  mov     r13, rdx
0x18006c2ad  xor     r14d, r14d
0x18006c2b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006c2b5  mov     rcx, rax; this
0x18006c2b8  mov     [rbp+var_28], rax
0x18006c2bc  call    ??0CreateStoragePool@CSpSubsystem@@QEAA@XZ; CSpSubsystem::CreateStoragePool::CreateStoragePool(void)
0x18006c2c1  mov     rdi, rax
0x18006c2c4  test    rax, rax
0x18006c2c7  jnz     short loc_18006C2D1
0x18006c2c9  lea     ebx, [rax+1Bh]
0x18006c2cc  jmp     loc_18006C58E
0x18006c2d1  mov     rax, [rax]
0x18006c2d4  mov     rdx, rsi
0x18006c2d7  mov     rcx, rdi
0x18006c2da  xor     r15d, r15d
0x18006c2dd  mov     rax, [rax+8]
0x18006c2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c2e6  lea     rcx, [rbp+var_40]
0x18006c2ea  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006c2ef  mov     [rdi+1Ch], eax
0x18006c2f2  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006c2f6  mov     ecx, [rsi+14h]; unsigned int
0x18006c2f9  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006c2fe  mov     eax, cs:dword_18039EB68
0x18006c304  cmp     eax, 5
0x18006c307  jbe     short loc_18006C377
0x18006c309  mov     rdx, 400000000000h
0x18006c313  lea     rcx, dword_18039EB68
0x18006c31a  call    _tlgKeywordOn
0x18006c31f  test    al, al
0x18006c321  jz      short loc_18006C377
0x18006c323  mov     eax, [rbp+var_40]
0x18006c326  lea     rdx, unk_180315B38
0x18006c32d  xor     ecx, ecx
0x18006c32f  cmp     [rdi+1Ch], eax
0x18006c332  movzx   eax, word ptr [rbp+var_10]
0x18006c336  mov     word ptr [rbp+var_40], ax
0x18006c33a  setnz   cl
0x18006c33d  mov     eax, [rsi+14h]
0x18006c340  mov     [rbp+var_38], eax
0x18006c343  lea     rax, [rbp+var_20]
0x18006c347  mov     [rbp+var_28], rax
0x18006c34b  lea     rax, [rbp+var_3C]
0x18006c34f  mov     [rsp+80h+var_48], rax
0x18006c354  lea     rax, [rbp+var_40]
0x18006c358  mov     [rsp+80h+var_50], rax
0x18006c35d  lea     rax, [rbp+var_38]
0x18006c361  mov     [rsp+80h+var_58], rax
0x18006c366  lea     rax, [rbp+var_28]
0x18006c36a  mov     [rsp+80h+var_60], rax
0x18006c36f  mov     [rbp+var_3C], ecx
0x18006c372  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006c377  mov     rcx, [rsi]
0x18006c37a  test    rcx, rcx
0x18006c37d  jz      loc_18006C564
0x18006c383  mov     rax, [rcx]
0x18006c386  test    rax, rax
0x18006c389  jz      loc_18006C564
0x18006c38f  mov     rax, [rax+18h]
0x18006c393  lea     r8, [rdi+20h]
0x18006c397  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006c39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c3a3  mov     ebx, eax
0x18006c3a5  test    eax, eax
0x18006c3a7  jnz     loc_18006C569
0x18006c3ad  cmp     [rsi+10h], r14d
0x18006c3b1  jz      loc_18006C4FD
0x18006c3b7  lea     rbx, [rdi+148h]
0x18006c3be  mov     rcx, rbx
0x18006c3c1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006c3c6  mov     rcx, rbx; struct CSpJobMgr **
0x18006c3c9  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006c3ce  test    eax, eax
0x18006c3d0  jnz     short loc_18006C3DA
0x18006c3d2  lea     ebx, [rax+1Ch]
0x18006c3d5  jmp     loc_18006C569
0x18006c3da  mov     ecx, 10h; Size
0x18006c3df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006c3e4  xor     r8d, r8d; pcbe
0x18006c3e7  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006c3ee  mov     rdx, rax; pv
0x18006c3f1  mov     r15, rax
0x18006c3f4  mov     [rax], rdi
0x18006c3f7  call    cs:__imp_CreateThreadpoolWork
0x18006c3fe  nop     dword ptr [rax+rax+00h]
0x18006c403  mov     r14, rax
0x18006c406  test    rax, rax
0x18006c409  jnz     short loc_18006C417
0x18006c40b  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006c410  mov     ebx, eax
0x18006c412  jmp     loc_18006C569
0x18006c417  call    cs:__imp_GetCurrentThread
0x18006c41e  nop     dword ptr [rax+rax+00h]
0x18006c423  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006c427  xor     r8d, r8d; OpenAsSelf
0x18006c42a  mov     rcx, rax; ThreadHandle
0x18006c42d  mov     edx, 2000Ch; DesiredAccess
0x18006c432  call    cs:__imp_OpenThreadToken
0x18006c439  nop     dword ptr [rax+rax+00h]
0x18006c43e  test    eax, eax
0x18006c440  jnz     short loc_18006C455
0x18006c442  call    cs:__imp_GetLastError
0x18006c449  nop     dword ptr [rax+rax+00h]
0x18006c44e  cmp     eax, 3F0h
0x18006c453  jnz     short loc_18006C40B
0x18006c455  mov     rax, [rbp+TokenHandle]
0x18006c459  mov     r8, r13
0x18006c45c  mov     [r15+8], rax
0x18006c460  mov     rcx, rdi
0x18006c463  mov     rax, [rdi]
0x18006c466  mov     rdx, [rsi+8]
0x18006c46a  mov     rax, [rax+18h]
0x18006c46e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c473  mov     rax, [rdi]
0x18006c476  mov     rdx, r12
0x18006c479  mov     rcx, rdi
0x18006c47c  mov     rax, [rax+28h]
0x18006c480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c485  mov     ebx, eax
0x18006c487  test    eax, eax
0x18006c489  jz      short loc_18006C494
0x18006c48b  cmp     eax, 7
0x18006c48e  jnz     loc_18006C569
0x18006c494  mov     rax, [rdi]
0x18006c497  mov     rdx, r12
0x18006c49a  mov     rcx, rdi
0x18006c49d  mov     rax, [rax+38h]
0x18006c4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c4a6  mov     ebx, eax
0x18006c4a8  test    eax, eax
0x18006c4aa  jnz     loc_18006C569
0x18006c4b0  mov     rax, [rdi+150h]
0x18006c4b7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006c4be  jnz     short loc_18006C4D4
0x18006c4c0  mov     rax, [rdi+158h]
0x18006c4c7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006c4ce  jz      loc_18006C569
0x18006c4d4  mov     rdx, r12
0x18006c4d7  mov     rcx, rdi
0x18006c4da  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006c4df  mov     ebx, eax
0x18006c4e1  test    eax, eax
0x18006c4e3  jnz     loc_18006C569
0x18006c4e9  mov     rcx, r14; pwk
0x18006c4ec  call    cs:__imp_SubmitThreadpoolWork
0x18006c4f3  nop     dword ptr [rax+rax+00h]
0x18006c4f8  jmp     loc_18006C5B7
0x18006c4fd  mov     rax, [rdi]
0x18006c500  mov     r8, r13
0x18006c503  mov     rdx, [rsi+8]
0x18006c507  mov     rcx, rdi
0x18006c50a  mov     rax, [rax+10h]
0x18006c50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c513  mov     rax, [rdi]
0x18006c516  mov     rdx, r12
0x18006c519  mov     rcx, rdi
0x18006c51c  mov     rax, [rax+30h]
0x18006c520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c525  mov     ebx, eax
0x18006c527  test    eax, eax
0x18006c529  jz      short loc_18006C530
0x18006c52b  cmp     eax, 7
0x18006c52e  jnz     short loc_18006C569
0x18006c530  mov     rax, [rdi]
0x18006c533  mov     rdx, r12
0x18006c536  mov     rcx, rdi
0x18006c539  mov     rax, [rax+28h]
0x18006c53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c542  mov     ebx, eax
0x18006c544  test    eax, eax
0x18006c546  jz      short loc_18006C54D
0x18006c548  cmp     eax, 7
0x18006c54b  jnz     short loc_18006C569
0x18006c54d  mov     rax, [rdi]
0x18006c550  mov     rdx, r12
0x18006c553  mov     rcx, rdi
0x18006c556  mov     rax, [rax+38h]
0x18006c55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c55f  jmp     loc_18006C410
0x18006c564  mov     ebx, 4
0x18006c569  mov     rax, [rdi]
0x18006c56c  mov     edx, 1
0x18006c571  mov     rcx, rdi
0x18006c574  mov     rax, [rax]
0x18006c577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c57c  test    r15, r15
0x18006c57f  jz      short loc_18006C58E
0x18006c581  mov     edx, 10h
0x18006c586  mov     rcx, r15; Block
0x18006c589  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006c58e  mov     rcx, [rbp+TokenHandle]; hObject
0x18006c592  test    rcx, rcx
0x18006c595  jz      short loc_18006C5A3
0x18006c597  call    cs:__imp_CloseHandle
0x18006c59e  nop     dword ptr [rax+rax+00h]
0x18006c5a3  test    r14, r14
0x18006c5a6  jz      short loc_18006C5B7
0x18006c5a8  mov     rcx, r14; pwk
0x18006c5ab  call    cs:__imp_CloseThreadpoolWork
0x18006c5b2  nop     dword ptr [rax+rax+00h]
0x18006c5b7  mov     eax, ebx
0x18006c5b9  mov     rcx, [rbp+var_8]
0x18006c5bd  xor     rcx, rsp; StackCookie
0x18006c5c0  call    __security_check_cookie
0x18006c5c5  mov     rbx, [rsp+80h+arg_18]
0x18006c5cd  add     rsp, 80h
0x18006c5d4  pop     r15
0x18006c5d6  pop     r14
0x18006c5d8  pop     r13
0x18006c5da  pop     r12
0x18006c5dc  pop     rdi
0x18006c5dd  pop     rsi
0x18006c5de  pop     rbp
0x18006c5df  retn
```
