# CSpWmiMethod<_SPACES_StoragePool_RemovePhysicalDisk>::RunMethod<CSpStoragePool::RemovePhysicalDisk,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bc03c`
- end: `0x1800bc38a`
- name: `??$RunMethod@VRemovePhysicalDisk@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_RemovePhysicalDisk@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800bc03c`
- `0x1800be0b8`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc208`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bc1e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bc1e9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bc1fe`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bc1fe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bc1cf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bc1cf`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bc2a8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bc2a8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bc35b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bc35b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bc34d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bc34d`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_RemovePhysicalDisk>::RunMethod<CSpStoragePool::RemovePhysicalDisk,11>(
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
  CSpStoragePool::RemovePhysicalDisk *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::RemovePhysicalDisk *)operator new(0x1A0u);
  v7 = CSpStoragePool::RemovePhysicalDisk::RemovePhysicalDisk(v25);
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
      v25 = (CSpStoragePool::RemovePhysicalDisk *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)word_18032AA4A,
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
0x1800bc03c  mov     [rsp-38h+arg_18], rbx
0x1800bc041  push    rbp
0x1800bc042  push    rsi
0x1800bc043  push    rdi
0x1800bc044  push    r12
0x1800bc046  push    r13
0x1800bc048  push    r14
0x1800bc04a  push    r15
0x1800bc04c  mov     rbp, rsp
0x1800bc04f  sub     rsp, 80h
0x1800bc056  mov     rax, cs:__security_cookie
0x1800bc05d  xor     rax, rsp
0x1800bc060  mov     [rbp+var_8], rax
0x1800bc064  xor     eax, eax
0x1800bc066  mov     rsi, rcx
0x1800bc069  xorps   xmm0, xmm0
0x1800bc06c  mov     [rbp+var_10], eax
0x1800bc06f  mov     ecx, 1A0h; Size
0x1800bc074  mov     [rbp+var_40], eax
0x1800bc077  movups  [rbp+var_20], xmm0
0x1800bc07b  mov     [rbp+TokenHandle], rax
0x1800bc07f  mov     r12, r8
0x1800bc082  mov     r13, rdx
0x1800bc085  xor     r14d, r14d
0x1800bc088  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bc08d  mov     rcx, rax; this
0x1800bc090  mov     [rbp+var_28], rax
0x1800bc094  call    ??0RemovePhysicalDisk@CSpStoragePool@@QEAA@XZ; CSpStoragePool::RemovePhysicalDisk::RemovePhysicalDisk(void)
0x1800bc099  mov     rdi, rax
0x1800bc09c  test    rax, rax
0x1800bc09f  jnz     short loc_1800BC0A9
0x1800bc0a1  lea     ebx, [rax+1Bh]
0x1800bc0a4  jmp     loc_1800BC344
0x1800bc0a9  mov     rax, [rax]
0x1800bc0ac  mov     rdx, rsi
0x1800bc0af  mov     rcx, rdi
0x1800bc0b2  xor     r15d, r15d
0x1800bc0b5  mov     rax, [rax+8]
0x1800bc0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc0be  lea     rcx, [rbp+var_40]
0x1800bc0c2  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bc0c7  mov     [rdi+1Ch], eax
0x1800bc0ca  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bc0ce  mov     ecx, [rsi+14h]; unsigned int
0x1800bc0d1  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bc0d6  mov     eax, cs:dword_180397B68
0x1800bc0dc  cmp     eax, 5
0x1800bc0df  jbe     short loc_1800BC14F
0x1800bc0e1  mov     rdx, 400000000000h
0x1800bc0eb  lea     rcx, dword_180397B68
0x1800bc0f2  call    _tlgKeywordOn
0x1800bc0f7  test    al, al
0x1800bc0f9  jz      short loc_1800BC14F
0x1800bc0fb  mov     eax, [rbp+var_40]
0x1800bc0fe  lea     rdx, word_18032AA4A
0x1800bc105  xor     ecx, ecx
0x1800bc107  cmp     [rdi+1Ch], eax
0x1800bc10a  movzx   eax, word ptr [rbp+var_10]
0x1800bc10e  mov     word ptr [rbp+var_40], ax
0x1800bc112  setnz   cl
0x1800bc115  mov     eax, [rsi+14h]
0x1800bc118  mov     [rbp+var_38], eax
0x1800bc11b  lea     rax, [rbp+var_20]
0x1800bc11f  mov     [rbp+var_28], rax
0x1800bc123  lea     rax, [rbp+var_3C]
0x1800bc127  mov     [rsp+80h+var_48], rax
0x1800bc12c  lea     rax, [rbp+var_40]
0x1800bc130  mov     [rsp+80h+var_50], rax
0x1800bc135  lea     rax, [rbp+var_38]
0x1800bc139  mov     [rsp+80h+var_58], rax
0x1800bc13e  lea     rax, [rbp+var_28]
0x1800bc142  mov     [rsp+80h+var_60], rax
0x1800bc147  mov     [rbp+var_3C], ecx
0x1800bc14a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bc14f  mov     rcx, [rsi]
0x1800bc152  test    rcx, rcx
0x1800bc155  jz      loc_1800BC31A
0x1800bc15b  mov     rax, [rcx]
0x1800bc15e  test    rax, rax
0x1800bc161  jz      loc_1800BC31A
0x1800bc167  mov     rax, [rax+18h]
0x1800bc16b  lea     r8, [rdi+20h]
0x1800bc16f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bc176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc17b  mov     ebx, eax
0x1800bc17d  test    eax, eax
0x1800bc17f  jnz     loc_1800BC31F
0x1800bc185  cmp     [rsi+10h], r14d
0x1800bc189  jz      loc_1800BC2B3
0x1800bc18f  lea     rbx, [rdi+148h]
0x1800bc196  mov     rcx, rbx
0x1800bc199  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bc19e  mov     rcx, rbx; struct CSpJobMgr **
0x1800bc1a1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bc1a6  test    eax, eax
0x1800bc1a8  jnz     short loc_1800BC1B2
0x1800bc1aa  lea     ebx, [rax+1Ch]
0x1800bc1ad  jmp     loc_1800BC31F
0x1800bc1b2  mov     ecx, 10h; Size
0x1800bc1b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bc1bc  xor     r8d, r8d; pcbe
0x1800bc1bf  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bc1c6  mov     rdx, rax; pv
0x1800bc1c9  mov     r15, rax
0x1800bc1cc  mov     [rax], rdi
0x1800bc1cf  call    cs:__imp_CreateThreadpoolWork
0x1800bc1d5  mov     r14, rax
0x1800bc1d8  test    rax, rax
0x1800bc1db  jnz     short loc_1800BC1E9
0x1800bc1dd  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bc1e2  mov     ebx, eax
0x1800bc1e4  jmp     loc_1800BC31F
0x1800bc1e9  call    cs:__imp_GetCurrentThread
0x1800bc1ef  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bc1f3  xor     r8d, r8d; OpenAsSelf
0x1800bc1f6  mov     rcx, rax; ThreadHandle
0x1800bc1f9  mov     edx, 2000Ch; DesiredAccess
0x1800bc1fe  call    cs:__imp_OpenThreadToken
0x1800bc204  test    eax, eax
0x1800bc206  jnz     short loc_1800BC215
0x1800bc208  call    cs:__imp_GetLastError
0x1800bc20e  cmp     eax, 3F0h
0x1800bc213  jnz     short loc_1800BC1DD
0x1800bc215  mov     rax, [rbp+TokenHandle]
0x1800bc219  mov     r8, r13
0x1800bc21c  mov     [r15+8], rax
0x1800bc220  mov     rcx, rdi
0x1800bc223  mov     rax, [rdi]
0x1800bc226  mov     rdx, [rsi+8]
0x1800bc22a  mov     rax, [rax+18h]
0x1800bc22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc233  mov     rax, [rdi]
0x1800bc236  mov     rdx, r12
0x1800bc239  mov     rcx, rdi
0x1800bc23c  mov     rax, [rax+28h]
0x1800bc240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc245  mov     ebx, eax
0x1800bc247  test    eax, eax
0x1800bc249  jz      short loc_1800BC254
0x1800bc24b  cmp     eax, 7
0x1800bc24e  jnz     loc_1800BC31F
0x1800bc254  mov     rax, [rdi]
0x1800bc257  mov     rdx, r12
0x1800bc25a  mov     rcx, rdi
0x1800bc25d  mov     rax, [rax+38h]
0x1800bc261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc266  mov     ebx, eax
0x1800bc268  test    eax, eax
0x1800bc26a  jnz     loc_1800BC31F
0x1800bc270  mov     rax, [rdi+150h]
0x1800bc277  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bc27e  jnz     short loc_1800BC294
0x1800bc280  mov     rax, [rdi+158h]
0x1800bc287  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bc28e  jz      loc_1800BC31F
0x1800bc294  mov     rdx, r12
0x1800bc297  mov     rcx, rdi
0x1800bc29a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bc29f  mov     ebx, eax
0x1800bc2a1  test    eax, eax
0x1800bc2a3  jnz     short loc_1800BC31F
0x1800bc2a5  mov     rcx, r14; pwk
0x1800bc2a8  call    cs:__imp_SubmitThreadpoolWork
0x1800bc2ae  jmp     loc_1800BC361
0x1800bc2b3  mov     rax, [rdi]
0x1800bc2b6  mov     r8, r13
0x1800bc2b9  mov     rdx, [rsi+8]
0x1800bc2bd  mov     rcx, rdi
0x1800bc2c0  mov     rax, [rax+10h]
0x1800bc2c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc2c9  mov     rax, [rdi]
0x1800bc2cc  mov     rdx, r12
0x1800bc2cf  mov     rcx, rdi
0x1800bc2d2  mov     rax, [rax+30h]
0x1800bc2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc2db  mov     ebx, eax
0x1800bc2dd  test    eax, eax
0x1800bc2df  jz      short loc_1800BC2E6
0x1800bc2e1  cmp     eax, 7
0x1800bc2e4  jnz     short loc_1800BC31F
0x1800bc2e6  mov     rax, [rdi]
0x1800bc2e9  mov     rdx, r12
0x1800bc2ec  mov     rcx, rdi
0x1800bc2ef  mov     rax, [rax+28h]
0x1800bc2f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc2f8  mov     ebx, eax
0x1800bc2fa  test    eax, eax
0x1800bc2fc  jz      short loc_1800BC303
0x1800bc2fe  cmp     eax, 7
0x1800bc301  jnz     short loc_1800BC31F
0x1800bc303  mov     rax, [rdi]
0x1800bc306  mov     rdx, r12
0x1800bc309  mov     rcx, rdi
0x1800bc30c  mov     rax, [rax+38h]
0x1800bc310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc315  jmp     loc_1800BC1E2
0x1800bc31a  mov     ebx, 4
0x1800bc31f  mov     rax, [rdi]
0x1800bc322  mov     edx, 1
0x1800bc327  mov     rcx, rdi
0x1800bc32a  mov     rax, [rax]
0x1800bc32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc332  test    r15, r15
0x1800bc335  jz      short loc_1800BC344
0x1800bc337  mov     edx, 10h
0x1800bc33c  mov     rcx, r15; Block
0x1800bc33f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bc344  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bc348  test    rcx, rcx
0x1800bc34b  jz      short loc_1800BC353
0x1800bc34d  call    cs:__imp_CloseHandle
0x1800bc353  test    r14, r14
0x1800bc356  jz      short loc_1800BC361
0x1800bc358  mov     rcx, r14; pwk
0x1800bc35b  call    cs:__imp_CloseThreadpoolWork
0x1800bc361  mov     eax, ebx
0x1800bc363  mov     rcx, [rbp+var_8]
0x1800bc367  xor     rcx, rsp; StackCookie
0x1800bc36a  call    __security_check_cookie
0x1800bc36f  mov     rbx, [rsp+80h+arg_18]
0x1800bc377  add     rsp, 80h
0x1800bc37e  pop     r15
0x1800bc380  pop     r14
0x1800bc382  pop     r13
0x1800bc384  pop     r12
0x1800bc386  pop     rdi
0x1800bc387  pop     rsi
0x1800bc388  pop     rbp
0x1800bc389  retn
```
