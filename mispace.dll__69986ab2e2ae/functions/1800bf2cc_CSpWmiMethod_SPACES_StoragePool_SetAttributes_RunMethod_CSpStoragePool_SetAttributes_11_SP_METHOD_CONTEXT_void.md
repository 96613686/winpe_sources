# CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::RunMethod<CSpStoragePool::SetAttributes,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bf2cc`
- end: `0x1800bf649`
- name: `??$RunMethod@VSetAttributes@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800bf2cc`
- `0x1800c11e8`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf4aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf4aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bf47f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bf47f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bf49a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bf49a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bf45f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bf45f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bf554`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bf554`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bf613`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bf613`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bf5ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bf5ff`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::RunMethod<CSpStoragePool::SetAttributes,11>(
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
  CSpStoragePool::SetAttributes *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::SetAttributes *)operator new(0x160u);
  v7 = CSpStoragePool::SetAttributes::SetAttributes(v25);
  v8 = v7;
  if ( v7 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 8LL))(v7, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStoragePool::SetAttributes *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18032E5B9,
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
0x1800bf2cc  mov     [rsp-38h+arg_18], rbx
0x1800bf2d1  push    rbp
0x1800bf2d2  push    rsi
0x1800bf2d3  push    rdi
0x1800bf2d4  push    r12
0x1800bf2d6  push    r13
0x1800bf2d8  push    r14
0x1800bf2da  push    r15
0x1800bf2dc  mov     rbp, rsp
0x1800bf2df  sub     rsp, 80h
0x1800bf2e6  mov     rax, cs:__security_cookie
0x1800bf2ed  xor     rax, rsp
0x1800bf2f0  mov     [rbp+var_8], rax
0x1800bf2f4  xor     eax, eax
0x1800bf2f6  mov     rsi, rcx
0x1800bf2f9  xorps   xmm0, xmm0
0x1800bf2fc  mov     [rbp+var_10], eax
0x1800bf2ff  mov     ecx, 160h; Size
0x1800bf304  mov     [rbp+var_40], eax
0x1800bf307  movups  [rbp+var_20], xmm0
0x1800bf30b  mov     [rbp+TokenHandle], rax
0x1800bf30f  mov     r12, r8
0x1800bf312  mov     r13, rdx
0x1800bf315  xor     r14d, r14d
0x1800bf318  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bf31d  mov     rcx, rax; this
0x1800bf320  mov     [rbp+var_28], rax
0x1800bf324  call    ??0SetAttributes@CSpStoragePool@@QEAA@XZ; CSpStoragePool::SetAttributes::SetAttributes(void)
0x1800bf329  mov     rdi, rax
0x1800bf32c  test    rax, rax
0x1800bf32f  jnz     short loc_1800BF339
0x1800bf331  lea     ebx, [rax+1Bh]
0x1800bf334  jmp     loc_1800BF5F6
0x1800bf339  mov     rax, [rax]
0x1800bf33c  mov     rdx, rsi
0x1800bf33f  mov     rcx, rdi
0x1800bf342  xor     r15d, r15d
0x1800bf345  mov     rax, [rax+8]
0x1800bf349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf34e  lea     rcx, [rbp+var_40]
0x1800bf352  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bf357  mov     [rdi+1Ch], eax
0x1800bf35a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bf35e  mov     ecx, [rsi+14h]; unsigned int
0x1800bf361  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bf366  mov     eax, cs:dword_18039EB68
0x1800bf36c  cmp     eax, 5
0x1800bf36f  jbe     short loc_1800BF3DF
0x1800bf371  mov     rdx, 400000000000h
0x1800bf37b  lea     rcx, dword_18039EB68
0x1800bf382  call    _tlgKeywordOn
0x1800bf387  test    al, al
0x1800bf389  jz      short loc_1800BF3DF
0x1800bf38b  mov     eax, [rbp+var_40]
0x1800bf38e  lea     rdx, byte_18032E5B9
0x1800bf395  xor     ecx, ecx
0x1800bf397  cmp     [rdi+1Ch], eax
0x1800bf39a  movzx   eax, word ptr [rbp+var_10]
0x1800bf39e  mov     word ptr [rbp+var_40], ax
0x1800bf3a2  setnz   cl
0x1800bf3a5  mov     eax, [rsi+14h]
0x1800bf3a8  mov     [rbp+var_38], eax
0x1800bf3ab  lea     rax, [rbp+var_20]
0x1800bf3af  mov     [rbp+var_28], rax
0x1800bf3b3  lea     rax, [rbp+var_3C]
0x1800bf3b7  mov     [rsp+80h+var_48], rax
0x1800bf3bc  lea     rax, [rbp+var_40]
0x1800bf3c0  mov     [rsp+80h+var_50], rax
0x1800bf3c5  lea     rax, [rbp+var_38]
0x1800bf3c9  mov     [rsp+80h+var_58], rax
0x1800bf3ce  lea     rax, [rbp+var_28]
0x1800bf3d2  mov     [rsp+80h+var_60], rax
0x1800bf3d7  mov     [rbp+var_3C], ecx
0x1800bf3da  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bf3df  mov     rcx, [rsi]
0x1800bf3e2  test    rcx, rcx
0x1800bf3e5  jz      loc_1800BF5CC
0x1800bf3eb  mov     rax, [rcx]
0x1800bf3ee  test    rax, rax
0x1800bf3f1  jz      loc_1800BF5CC
0x1800bf3f7  mov     rax, [rax+18h]
0x1800bf3fb  lea     r8, [rdi+20h]
0x1800bf3ff  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bf406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf40b  mov     ebx, eax
0x1800bf40d  test    eax, eax
0x1800bf40f  jnz     loc_1800BF5D1
0x1800bf415  cmp     [rsi+10h], r14d
0x1800bf419  jz      loc_1800BF565
0x1800bf41f  lea     rbx, [rdi+148h]
0x1800bf426  mov     rcx, rbx
0x1800bf429  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bf42e  mov     rcx, rbx; struct CSpJobMgr **
0x1800bf431  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bf436  test    eax, eax
0x1800bf438  jnz     short loc_1800BF442
0x1800bf43a  lea     ebx, [rax+1Ch]
0x1800bf43d  jmp     loc_1800BF5D1
0x1800bf442  mov     ecx, 10h; Size
0x1800bf447  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bf44c  xor     r8d, r8d; pcbe
0x1800bf44f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bf456  mov     rdx, rax; pv
0x1800bf459  mov     r15, rax
0x1800bf45c  mov     [rax], rdi
0x1800bf45f  call    cs:__imp_CreateThreadpoolWork
0x1800bf466  nop     dword ptr [rax+rax+00h]
0x1800bf46b  mov     r14, rax
0x1800bf46e  test    rax, rax
0x1800bf471  jnz     short loc_1800BF47F
0x1800bf473  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bf478  mov     ebx, eax
0x1800bf47a  jmp     loc_1800BF5D1
0x1800bf47f  call    cs:__imp_GetCurrentThread
0x1800bf486  nop     dword ptr [rax+rax+00h]
0x1800bf48b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bf48f  xor     r8d, r8d; OpenAsSelf
0x1800bf492  mov     rcx, rax; ThreadHandle
0x1800bf495  mov     edx, 2000Ch; DesiredAccess
0x1800bf49a  call    cs:__imp_OpenThreadToken
0x1800bf4a1  nop     dword ptr [rax+rax+00h]
0x1800bf4a6  test    eax, eax
0x1800bf4a8  jnz     short loc_1800BF4BD
0x1800bf4aa  call    cs:__imp_GetLastError
0x1800bf4b1  nop     dword ptr [rax+rax+00h]
0x1800bf4b6  cmp     eax, 3F0h
0x1800bf4bb  jnz     short loc_1800BF473
0x1800bf4bd  mov     rax, [rbp+TokenHandle]
0x1800bf4c1  mov     r8, r13
0x1800bf4c4  mov     [r15+8], rax
0x1800bf4c8  mov     rcx, rdi
0x1800bf4cb  mov     rax, [rdi]
0x1800bf4ce  mov     rdx, [rsi+8]
0x1800bf4d2  mov     rax, [rax+18h]
0x1800bf4d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf4db  mov     rax, [rdi]
0x1800bf4de  mov     rdx, r12
0x1800bf4e1  mov     rcx, rdi
0x1800bf4e4  mov     rax, [rax+28h]
0x1800bf4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf4ed  mov     ebx, eax
0x1800bf4ef  test    eax, eax
0x1800bf4f1  jz      short loc_1800BF4FC
0x1800bf4f3  cmp     eax, 7
0x1800bf4f6  jnz     loc_1800BF5D1
0x1800bf4fc  mov     rax, [rdi]
0x1800bf4ff  mov     rdx, r12
0x1800bf502  mov     rcx, rdi
0x1800bf505  mov     rax, [rax+38h]
0x1800bf509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf50e  mov     ebx, eax
0x1800bf510  test    eax, eax
0x1800bf512  jnz     loc_1800BF5D1
0x1800bf518  mov     rax, [rdi+150h]
0x1800bf51f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bf526  jnz     short loc_1800BF53C
0x1800bf528  mov     rax, [rdi+158h]
0x1800bf52f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bf536  jz      loc_1800BF5D1
0x1800bf53c  mov     rdx, r12
0x1800bf53f  mov     rcx, rdi
0x1800bf542  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bf547  mov     ebx, eax
0x1800bf549  test    eax, eax
0x1800bf54b  jnz     loc_1800BF5D1
0x1800bf551  mov     rcx, r14; pwk
0x1800bf554  call    cs:__imp_SubmitThreadpoolWork
0x1800bf55b  nop     dword ptr [rax+rax+00h]
0x1800bf560  jmp     loc_1800BF61F
0x1800bf565  mov     rax, [rdi]
0x1800bf568  mov     r8, r13
0x1800bf56b  mov     rdx, [rsi+8]
0x1800bf56f  mov     rcx, rdi
0x1800bf572  mov     rax, [rax+10h]
0x1800bf576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf57b  mov     rax, [rdi]
0x1800bf57e  mov     rdx, r12
0x1800bf581  mov     rcx, rdi
0x1800bf584  mov     rax, [rax+30h]
0x1800bf588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf58d  mov     ebx, eax
0x1800bf58f  test    eax, eax
0x1800bf591  jz      short loc_1800BF598
0x1800bf593  cmp     eax, 7
0x1800bf596  jnz     short loc_1800BF5D1
0x1800bf598  mov     rax, [rdi]
0x1800bf59b  mov     rdx, r12
0x1800bf59e  mov     rcx, rdi
0x1800bf5a1  mov     rax, [rax+28h]
0x1800bf5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf5aa  mov     ebx, eax
0x1800bf5ac  test    eax, eax
0x1800bf5ae  jz      short loc_1800BF5B5
0x1800bf5b0  cmp     eax, 7
0x1800bf5b3  jnz     short loc_1800BF5D1
0x1800bf5b5  mov     rax, [rdi]
0x1800bf5b8  mov     rdx, r12
0x1800bf5bb  mov     rcx, rdi
0x1800bf5be  mov     rax, [rax+38h]
0x1800bf5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf5c7  jmp     loc_1800BF478
0x1800bf5cc  mov     ebx, 4
0x1800bf5d1  mov     rax, [rdi]
0x1800bf5d4  mov     edx, 1
0x1800bf5d9  mov     rcx, rdi
0x1800bf5dc  mov     rax, [rax]
0x1800bf5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf5e4  test    r15, r15
0x1800bf5e7  jz      short loc_1800BF5F6
0x1800bf5e9  mov     edx, 10h
0x1800bf5ee  mov     rcx, r15; Block
0x1800bf5f1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bf5f6  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bf5fa  test    rcx, rcx
0x1800bf5fd  jz      short loc_1800BF60B
0x1800bf5ff  call    cs:__imp_CloseHandle
0x1800bf606  nop     dword ptr [rax+rax+00h]
0x1800bf60b  test    r14, r14
0x1800bf60e  jz      short loc_1800BF61F
0x1800bf610  mov     rcx, r14; pwk
0x1800bf613  call    cs:__imp_CloseThreadpoolWork
0x1800bf61a  nop     dword ptr [rax+rax+00h]
0x1800bf61f  mov     eax, ebx
0x1800bf621  mov     rcx, [rbp+var_8]
0x1800bf625  xor     rcx, rsp; StackCookie
0x1800bf628  call    __security_check_cookie
0x1800bf62d  mov     rbx, [rsp+80h+arg_18]
0x1800bf635  add     rsp, 80h
0x1800bf63c  pop     r15
0x1800bf63e  pop     r14
0x1800bf640  pop     r13
0x1800bf642  pop     r12
0x1800bf644  pop     rdi
0x1800bf645  pop     rsi
0x1800bf646  pop     rbp
0x1800bf647  retn
```
