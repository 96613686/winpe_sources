# CSpWmiMethod<_SPACES_StoragePool_SetUsage>::RunMethod<CSpStoragePool::SetUsage,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bd0e0`
- end: `0x1800bd42e`
- name: `??$RunMethod@VSetUsage@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_SetUsage@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800bd0e0`
- `0x1800be320`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd2ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd2ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bd28d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bd28d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bd2a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bd2a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bd273`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bd273`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bd34c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bd34c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bd3ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bd3ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd3f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd3f1`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_SetUsage>::RunMethod<CSpStoragePool::SetUsage,11>(
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
  CSpStoragePool::SetUsage *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::SetUsage *)operator new(0x160u);
  v7 = CSpStoragePool::SetUsage::SetUsage(v25);
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
      v25 = (CSpStoragePool::SetUsage *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_180327BC6,
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
0x1800bd0e0  mov     [rsp-38h+arg_18], rbx
0x1800bd0e5  push    rbp
0x1800bd0e6  push    rsi
0x1800bd0e7  push    rdi
0x1800bd0e8  push    r12
0x1800bd0ea  push    r13
0x1800bd0ec  push    r14
0x1800bd0ee  push    r15
0x1800bd0f0  mov     rbp, rsp
0x1800bd0f3  sub     rsp, 80h
0x1800bd0fa  mov     rax, cs:__security_cookie
0x1800bd101  xor     rax, rsp
0x1800bd104  mov     [rbp+var_8], rax
0x1800bd108  xor     eax, eax
0x1800bd10a  mov     rsi, rcx
0x1800bd10d  xorps   xmm0, xmm0
0x1800bd110  mov     [rbp+var_10], eax
0x1800bd113  mov     ecx, 160h; Size
0x1800bd118  mov     [rbp+var_40], eax
0x1800bd11b  movups  [rbp+var_20], xmm0
0x1800bd11f  mov     [rbp+TokenHandle], rax
0x1800bd123  mov     r12, r8
0x1800bd126  mov     r13, rdx
0x1800bd129  xor     r14d, r14d
0x1800bd12c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bd131  mov     rcx, rax; this
0x1800bd134  mov     [rbp+var_28], rax
0x1800bd138  call    ??0SetUsage@CSpStoragePool@@QEAA@XZ; CSpStoragePool::SetUsage::SetUsage(void)
0x1800bd13d  mov     rdi, rax
0x1800bd140  test    rax, rax
0x1800bd143  jnz     short loc_1800BD14D
0x1800bd145  lea     ebx, [rax+1Bh]
0x1800bd148  jmp     loc_1800BD3E8
0x1800bd14d  mov     rax, [rax]
0x1800bd150  mov     rdx, rsi
0x1800bd153  mov     rcx, rdi
0x1800bd156  xor     r15d, r15d
0x1800bd159  mov     rax, [rax+8]
0x1800bd15d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd162  lea     rcx, [rbp+var_40]
0x1800bd166  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bd16b  mov     [rdi+1Ch], eax
0x1800bd16e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bd172  mov     ecx, [rsi+14h]; unsigned int
0x1800bd175  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bd17a  mov     eax, cs:dword_180397B68
0x1800bd180  cmp     eax, 5
0x1800bd183  jbe     short loc_1800BD1F3
0x1800bd185  mov     rdx, 400000000000h
0x1800bd18f  lea     rcx, dword_180397B68
0x1800bd196  call    _tlgKeywordOn
0x1800bd19b  test    al, al
0x1800bd19d  jz      short loc_1800BD1F3
0x1800bd19f  mov     eax, [rbp+var_40]
0x1800bd1a2  lea     rdx, word_180327BC6
0x1800bd1a9  xor     ecx, ecx
0x1800bd1ab  cmp     [rdi+1Ch], eax
0x1800bd1ae  movzx   eax, word ptr [rbp+var_10]
0x1800bd1b2  mov     word ptr [rbp+var_40], ax
0x1800bd1b6  setnz   cl
0x1800bd1b9  mov     eax, [rsi+14h]
0x1800bd1bc  mov     [rbp+var_38], eax
0x1800bd1bf  lea     rax, [rbp+var_20]
0x1800bd1c3  mov     [rbp+var_28], rax
0x1800bd1c7  lea     rax, [rbp+var_3C]
0x1800bd1cb  mov     [rsp+80h+var_48], rax
0x1800bd1d0  lea     rax, [rbp+var_40]
0x1800bd1d4  mov     [rsp+80h+var_50], rax
0x1800bd1d9  lea     rax, [rbp+var_38]
0x1800bd1dd  mov     [rsp+80h+var_58], rax
0x1800bd1e2  lea     rax, [rbp+var_28]
0x1800bd1e6  mov     [rsp+80h+var_60], rax
0x1800bd1eb  mov     [rbp+var_3C], ecx
0x1800bd1ee  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bd1f3  mov     rcx, [rsi]
0x1800bd1f6  test    rcx, rcx
0x1800bd1f9  jz      loc_1800BD3BE
0x1800bd1ff  mov     rax, [rcx]
0x1800bd202  test    rax, rax
0x1800bd205  jz      loc_1800BD3BE
0x1800bd20b  mov     rax, [rax+18h]
0x1800bd20f  lea     r8, [rdi+20h]
0x1800bd213  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bd21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd21f  mov     ebx, eax
0x1800bd221  test    eax, eax
0x1800bd223  jnz     loc_1800BD3C3
0x1800bd229  cmp     [rsi+10h], r14d
0x1800bd22d  jz      loc_1800BD357
0x1800bd233  lea     rbx, [rdi+148h]
0x1800bd23a  mov     rcx, rbx
0x1800bd23d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bd242  mov     rcx, rbx; struct CSpJobMgr **
0x1800bd245  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bd24a  test    eax, eax
0x1800bd24c  jnz     short loc_1800BD256
0x1800bd24e  lea     ebx, [rax+1Ch]
0x1800bd251  jmp     loc_1800BD3C3
0x1800bd256  mov     ecx, 10h; Size
0x1800bd25b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bd260  xor     r8d, r8d; pcbe
0x1800bd263  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bd26a  mov     rdx, rax; pv
0x1800bd26d  mov     r15, rax
0x1800bd270  mov     [rax], rdi
0x1800bd273  call    cs:__imp_CreateThreadpoolWork
0x1800bd279  mov     r14, rax
0x1800bd27c  test    rax, rax
0x1800bd27f  jnz     short loc_1800BD28D
0x1800bd281  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bd286  mov     ebx, eax
0x1800bd288  jmp     loc_1800BD3C3
0x1800bd28d  call    cs:__imp_GetCurrentThread
0x1800bd293  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bd297  xor     r8d, r8d; OpenAsSelf
0x1800bd29a  mov     rcx, rax; ThreadHandle
0x1800bd29d  mov     edx, 2000Ch; DesiredAccess
0x1800bd2a2  call    cs:__imp_OpenThreadToken
0x1800bd2a8  test    eax, eax
0x1800bd2aa  jnz     short loc_1800BD2B9
0x1800bd2ac  call    cs:__imp_GetLastError
0x1800bd2b2  cmp     eax, 3F0h
0x1800bd2b7  jnz     short loc_1800BD281
0x1800bd2b9  mov     rax, [rbp+TokenHandle]
0x1800bd2bd  mov     r8, r13
0x1800bd2c0  mov     [r15+8], rax
0x1800bd2c4  mov     rcx, rdi
0x1800bd2c7  mov     rax, [rdi]
0x1800bd2ca  mov     rdx, [rsi+8]
0x1800bd2ce  mov     rax, [rax+18h]
0x1800bd2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd2d7  mov     rax, [rdi]
0x1800bd2da  mov     rdx, r12
0x1800bd2dd  mov     rcx, rdi
0x1800bd2e0  mov     rax, [rax+28h]
0x1800bd2e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd2e9  mov     ebx, eax
0x1800bd2eb  test    eax, eax
0x1800bd2ed  jz      short loc_1800BD2F8
0x1800bd2ef  cmp     eax, 7
0x1800bd2f2  jnz     loc_1800BD3C3
0x1800bd2f8  mov     rax, [rdi]
0x1800bd2fb  mov     rdx, r12
0x1800bd2fe  mov     rcx, rdi
0x1800bd301  mov     rax, [rax+38h]
0x1800bd305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd30a  mov     ebx, eax
0x1800bd30c  test    eax, eax
0x1800bd30e  jnz     loc_1800BD3C3
0x1800bd314  mov     rax, [rdi+150h]
0x1800bd31b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bd322  jnz     short loc_1800BD338
0x1800bd324  mov     rax, [rdi+158h]
0x1800bd32b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bd332  jz      loc_1800BD3C3
0x1800bd338  mov     rdx, r12
0x1800bd33b  mov     rcx, rdi
0x1800bd33e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bd343  mov     ebx, eax
0x1800bd345  test    eax, eax
0x1800bd347  jnz     short loc_1800BD3C3
0x1800bd349  mov     rcx, r14; pwk
0x1800bd34c  call    cs:__imp_SubmitThreadpoolWork
0x1800bd352  jmp     loc_1800BD405
0x1800bd357  mov     rax, [rdi]
0x1800bd35a  mov     r8, r13
0x1800bd35d  mov     rdx, [rsi+8]
0x1800bd361  mov     rcx, rdi
0x1800bd364  mov     rax, [rax+10h]
0x1800bd368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd36d  mov     rax, [rdi]
0x1800bd370  mov     rdx, r12
0x1800bd373  mov     rcx, rdi
0x1800bd376  mov     rax, [rax+30h]
0x1800bd37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd37f  mov     ebx, eax
0x1800bd381  test    eax, eax
0x1800bd383  jz      short loc_1800BD38A
0x1800bd385  cmp     eax, 7
0x1800bd388  jnz     short loc_1800BD3C3
0x1800bd38a  mov     rax, [rdi]
0x1800bd38d  mov     rdx, r12
0x1800bd390  mov     rcx, rdi
0x1800bd393  mov     rax, [rax+28h]
0x1800bd397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd39c  mov     ebx, eax
0x1800bd39e  test    eax, eax
0x1800bd3a0  jz      short loc_1800BD3A7
0x1800bd3a2  cmp     eax, 7
0x1800bd3a5  jnz     short loc_1800BD3C3
0x1800bd3a7  mov     rax, [rdi]
0x1800bd3aa  mov     rdx, r12
0x1800bd3ad  mov     rcx, rdi
0x1800bd3b0  mov     rax, [rax+38h]
0x1800bd3b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd3b9  jmp     loc_1800BD286
0x1800bd3be  mov     ebx, 4
0x1800bd3c3  mov     rax, [rdi]
0x1800bd3c6  mov     edx, 1
0x1800bd3cb  mov     rcx, rdi
0x1800bd3ce  mov     rax, [rax]
0x1800bd3d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd3d6  test    r15, r15
0x1800bd3d9  jz      short loc_1800BD3E8
0x1800bd3db  mov     edx, 10h
0x1800bd3e0  mov     rcx, r15; Block
0x1800bd3e3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bd3e8  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bd3ec  test    rcx, rcx
0x1800bd3ef  jz      short loc_1800BD3F7
0x1800bd3f1  call    cs:__imp_CloseHandle
0x1800bd3f7  test    r14, r14
0x1800bd3fa  jz      short loc_1800BD405
0x1800bd3fc  mov     rcx, r14; pwk
0x1800bd3ff  call    cs:__imp_CloseThreadpoolWork
0x1800bd405  mov     eax, ebx
0x1800bd407  mov     rcx, [rbp+var_8]
0x1800bd40b  xor     rcx, rsp; StackCookie
0x1800bd40e  call    __security_check_cookie
0x1800bd413  mov     rbx, [rsp+80h+arg_18]
0x1800bd41b  add     rsp, 80h
0x1800bd422  pop     r15
0x1800bd424  pop     r14
0x1800bd426  pop     r13
0x1800bd428  pop     r12
0x1800bd42a  pop     rdi
0x1800bd42b  pop     rsi
0x1800bd42c  pop     rbp
0x1800bd42d  retn
```
