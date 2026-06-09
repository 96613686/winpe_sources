# CSpWmiMethod<_SPACES_StoragePool_AddPhysicalDisk>::RunMethod<CSpStoragePool::AddPhysicalDisk,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bd30c`
- end: `0x1800bd689`
- name: `??$RunMethod@VAddPhysicalDisk@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_AddPhysicalDisk@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800bd30c`
- `0x1800c0c24`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd4ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd4ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bd4bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bd4bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bd4da`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bd4da`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bd49f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bd49f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bd594`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bd594`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bd653`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bd653`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd63f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd63f`

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
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStoragePool::AddPhysicalDisk *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_18032F2B8,
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
0x1800bd30c  mov     [rsp-38h+arg_18], rbx
0x1800bd311  push    rbp
0x1800bd312  push    rsi
0x1800bd313  push    rdi
0x1800bd314  push    r12
0x1800bd316  push    r13
0x1800bd318  push    r14
0x1800bd31a  push    r15
0x1800bd31c  mov     rbp, rsp
0x1800bd31f  sub     rsp, 80h
0x1800bd326  mov     rax, cs:__security_cookie
0x1800bd32d  xor     rax, rsp
0x1800bd330  mov     [rbp+var_8], rax
0x1800bd334  xor     eax, eax
0x1800bd336  mov     rsi, rcx
0x1800bd339  xorps   xmm0, xmm0
0x1800bd33c  mov     [rbp+var_10], eax
0x1800bd33f  mov     ecx, 170h; Size
0x1800bd344  mov     [rbp+var_40], eax
0x1800bd347  movups  [rbp+var_20], xmm0
0x1800bd34b  mov     [rbp+TokenHandle], rax
0x1800bd34f  mov     r12, r8
0x1800bd352  mov     r13, rdx
0x1800bd355  xor     r14d, r14d
0x1800bd358  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bd35d  mov     rcx, rax; this
0x1800bd360  mov     [rbp+var_28], rax
0x1800bd364  call    ??0AddPhysicalDisk@CSpStoragePool@@QEAA@XZ; CSpStoragePool::AddPhysicalDisk::AddPhysicalDisk(void)
0x1800bd369  mov     rdi, rax
0x1800bd36c  test    rax, rax
0x1800bd36f  jnz     short loc_1800BD379
0x1800bd371  lea     ebx, [rax+1Bh]
0x1800bd374  jmp     loc_1800BD636
0x1800bd379  mov     rax, [rax]
0x1800bd37c  mov     rdx, rsi
0x1800bd37f  mov     rcx, rdi
0x1800bd382  xor     r15d, r15d
0x1800bd385  mov     rax, [rax+8]
0x1800bd389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd38e  lea     rcx, [rbp+var_40]
0x1800bd392  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bd397  mov     [rdi+1Ch], eax
0x1800bd39a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bd39e  mov     ecx, [rsi+14h]; unsigned int
0x1800bd3a1  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bd3a6  mov     eax, cs:dword_18039EB68
0x1800bd3ac  cmp     eax, 5
0x1800bd3af  jbe     short loc_1800BD41F
0x1800bd3b1  mov     rdx, 400000000000h
0x1800bd3bb  lea     rcx, dword_18039EB68
0x1800bd3c2  call    _tlgKeywordOn
0x1800bd3c7  test    al, al
0x1800bd3c9  jz      short loc_1800BD41F
0x1800bd3cb  mov     eax, [rbp+var_40]
0x1800bd3ce  lea     rdx, unk_18032F2B8
0x1800bd3d5  xor     ecx, ecx
0x1800bd3d7  cmp     [rdi+1Ch], eax
0x1800bd3da  movzx   eax, word ptr [rbp+var_10]
0x1800bd3de  mov     word ptr [rbp+var_40], ax
0x1800bd3e2  setnz   cl
0x1800bd3e5  mov     eax, [rsi+14h]
0x1800bd3e8  mov     [rbp+var_38], eax
0x1800bd3eb  lea     rax, [rbp+var_20]
0x1800bd3ef  mov     [rbp+var_28], rax
0x1800bd3f3  lea     rax, [rbp+var_3C]
0x1800bd3f7  mov     [rsp+80h+var_48], rax
0x1800bd3fc  lea     rax, [rbp+var_40]
0x1800bd400  mov     [rsp+80h+var_50], rax
0x1800bd405  lea     rax, [rbp+var_38]
0x1800bd409  mov     [rsp+80h+var_58], rax
0x1800bd40e  lea     rax, [rbp+var_28]
0x1800bd412  mov     [rsp+80h+var_60], rax
0x1800bd417  mov     [rbp+var_3C], ecx
0x1800bd41a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bd41f  mov     rcx, [rsi]
0x1800bd422  test    rcx, rcx
0x1800bd425  jz      loc_1800BD60C
0x1800bd42b  mov     rax, [rcx]
0x1800bd42e  test    rax, rax
0x1800bd431  jz      loc_1800BD60C
0x1800bd437  mov     rax, [rax+18h]
0x1800bd43b  lea     r8, [rdi+20h]
0x1800bd43f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bd446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd44b  mov     ebx, eax
0x1800bd44d  test    eax, eax
0x1800bd44f  jnz     loc_1800BD611
0x1800bd455  cmp     [rsi+10h], r14d
0x1800bd459  jz      loc_1800BD5A5
0x1800bd45f  lea     rbx, [rdi+148h]
0x1800bd466  mov     rcx, rbx
0x1800bd469  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bd46e  mov     rcx, rbx; struct CSpJobMgr **
0x1800bd471  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bd476  test    eax, eax
0x1800bd478  jnz     short loc_1800BD482
0x1800bd47a  lea     ebx, [rax+1Ch]
0x1800bd47d  jmp     loc_1800BD611
0x1800bd482  mov     ecx, 10h; Size
0x1800bd487  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bd48c  xor     r8d, r8d; pcbe
0x1800bd48f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bd496  mov     rdx, rax; pv
0x1800bd499  mov     r15, rax
0x1800bd49c  mov     [rax], rdi
0x1800bd49f  call    cs:__imp_CreateThreadpoolWork
0x1800bd4a6  nop     dword ptr [rax+rax+00h]
0x1800bd4ab  mov     r14, rax
0x1800bd4ae  test    rax, rax
0x1800bd4b1  jnz     short loc_1800BD4BF
0x1800bd4b3  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bd4b8  mov     ebx, eax
0x1800bd4ba  jmp     loc_1800BD611
0x1800bd4bf  call    cs:__imp_GetCurrentThread
0x1800bd4c6  nop     dword ptr [rax+rax+00h]
0x1800bd4cb  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bd4cf  xor     r8d, r8d; OpenAsSelf
0x1800bd4d2  mov     rcx, rax; ThreadHandle
0x1800bd4d5  mov     edx, 2000Ch; DesiredAccess
0x1800bd4da  call    cs:__imp_OpenThreadToken
0x1800bd4e1  nop     dword ptr [rax+rax+00h]
0x1800bd4e6  test    eax, eax
0x1800bd4e8  jnz     short loc_1800BD4FD
0x1800bd4ea  call    cs:__imp_GetLastError
0x1800bd4f1  nop     dword ptr [rax+rax+00h]
0x1800bd4f6  cmp     eax, 3F0h
0x1800bd4fb  jnz     short loc_1800BD4B3
0x1800bd4fd  mov     rax, [rbp+TokenHandle]
0x1800bd501  mov     r8, r13
0x1800bd504  mov     [r15+8], rax
0x1800bd508  mov     rcx, rdi
0x1800bd50b  mov     rax, [rdi]
0x1800bd50e  mov     rdx, [rsi+8]
0x1800bd512  mov     rax, [rax+18h]
0x1800bd516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd51b  mov     rax, [rdi]
0x1800bd51e  mov     rdx, r12
0x1800bd521  mov     rcx, rdi
0x1800bd524  mov     rax, [rax+28h]
0x1800bd528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd52d  mov     ebx, eax
0x1800bd52f  test    eax, eax
0x1800bd531  jz      short loc_1800BD53C
0x1800bd533  cmp     eax, 7
0x1800bd536  jnz     loc_1800BD611
0x1800bd53c  mov     rax, [rdi]
0x1800bd53f  mov     rdx, r12
0x1800bd542  mov     rcx, rdi
0x1800bd545  mov     rax, [rax+38h]
0x1800bd549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd54e  mov     ebx, eax
0x1800bd550  test    eax, eax
0x1800bd552  jnz     loc_1800BD611
0x1800bd558  mov     rax, [rdi+150h]
0x1800bd55f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bd566  jnz     short loc_1800BD57C
0x1800bd568  mov     rax, [rdi+158h]
0x1800bd56f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bd576  jz      loc_1800BD611
0x1800bd57c  mov     rdx, r12
0x1800bd57f  mov     rcx, rdi
0x1800bd582  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bd587  mov     ebx, eax
0x1800bd589  test    eax, eax
0x1800bd58b  jnz     loc_1800BD611
0x1800bd591  mov     rcx, r14; pwk
0x1800bd594  call    cs:__imp_SubmitThreadpoolWork
0x1800bd59b  nop     dword ptr [rax+rax+00h]
0x1800bd5a0  jmp     loc_1800BD65F
0x1800bd5a5  mov     rax, [rdi]
0x1800bd5a8  mov     r8, r13
0x1800bd5ab  mov     rdx, [rsi+8]
0x1800bd5af  mov     rcx, rdi
0x1800bd5b2  mov     rax, [rax+10h]
0x1800bd5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd5bb  mov     rax, [rdi]
0x1800bd5be  mov     rdx, r12
0x1800bd5c1  mov     rcx, rdi
0x1800bd5c4  mov     rax, [rax+30h]
0x1800bd5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd5cd  mov     ebx, eax
0x1800bd5cf  test    eax, eax
0x1800bd5d1  jz      short loc_1800BD5D8
0x1800bd5d3  cmp     eax, 7
0x1800bd5d6  jnz     short loc_1800BD611
0x1800bd5d8  mov     rax, [rdi]
0x1800bd5db  mov     rdx, r12
0x1800bd5de  mov     rcx, rdi
0x1800bd5e1  mov     rax, [rax+28h]
0x1800bd5e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd5ea  mov     ebx, eax
0x1800bd5ec  test    eax, eax
0x1800bd5ee  jz      short loc_1800BD5F5
0x1800bd5f0  cmp     eax, 7
0x1800bd5f3  jnz     short loc_1800BD611
0x1800bd5f5  mov     rax, [rdi]
0x1800bd5f8  mov     rdx, r12
0x1800bd5fb  mov     rcx, rdi
0x1800bd5fe  mov     rax, [rax+38h]
0x1800bd602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd607  jmp     loc_1800BD4B8
0x1800bd60c  mov     ebx, 4
0x1800bd611  mov     rax, [rdi]
0x1800bd614  mov     edx, 1
0x1800bd619  mov     rcx, rdi
0x1800bd61c  mov     rax, [rax]
0x1800bd61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd624  test    r15, r15
0x1800bd627  jz      short loc_1800BD636
0x1800bd629  mov     edx, 10h
0x1800bd62e  mov     rcx, r15; Block
0x1800bd631  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bd636  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bd63a  test    rcx, rcx
0x1800bd63d  jz      short loc_1800BD64B
0x1800bd63f  call    cs:__imp_CloseHandle
0x1800bd646  nop     dword ptr [rax+rax+00h]
0x1800bd64b  test    r14, r14
0x1800bd64e  jz      short loc_1800BD65F
0x1800bd650  mov     rcx, r14; pwk
0x1800bd653  call    cs:__imp_CloseThreadpoolWork
0x1800bd65a  nop     dword ptr [rax+rax+00h]
0x1800bd65f  mov     eax, ebx
0x1800bd661  mov     rcx, [rbp+var_8]
0x1800bd665  xor     rcx, rsp; StackCookie
0x1800bd668  call    __security_check_cookie
0x1800bd66d  mov     rbx, [rsp+80h+arg_18]
0x1800bd675  add     rsp, 80h
0x1800bd67c  pop     r15
0x1800bd67e  pop     r14
0x1800bd680  pop     r13
0x1800bd682  pop     r12
0x1800bd684  pop     rdi
0x1800bd685  pop     rsi
0x1800bd686  pop     rbp
0x1800bd687  retn
```
