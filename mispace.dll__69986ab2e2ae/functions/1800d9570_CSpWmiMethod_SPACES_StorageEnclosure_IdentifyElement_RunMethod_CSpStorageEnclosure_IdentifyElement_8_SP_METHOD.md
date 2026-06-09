# CSpWmiMethod<_SPACES_StorageEnclosure_IdentifyElement>::RunMethod<CSpStorageEnclosure::IdentifyElement,8>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800d9570`
- end: `0x1800d98ed`
- name: `??$RunMethod@VIdentifyElement@CSpStorageEnclosure@@$07@?$CSpWmiMethod@U_SPACES_StorageEnclosure_IdentifyElement@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800dc240`

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
- `0x1800d9570`
- `0x1800da470`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d974e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d974e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d9723`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d9723`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d973e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d973e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d9703`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d9703`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d97f8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d97f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d98b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d98b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d98a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d98a3`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageEnclosure_IdentifyElement>::RunMethod<CSpStorageEnclosure::IdentifyElement,8>(
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
  CSpStorageEnclosure::IdentifyElement *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageEnclosure::IdentifyElement *)operator new(0x160u);
  v7 = CSpStorageEnclosure::IdentifyElement::IdentifyElement(v25);
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
      v25 = (CSpStorageEnclosure::IdentifyElement *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_180335B2F,
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
0x1800d9570  mov     [rsp-38h+arg_18], rbx
0x1800d9575  push    rbp
0x1800d9576  push    rsi
0x1800d9577  push    rdi
0x1800d9578  push    r12
0x1800d957a  push    r13
0x1800d957c  push    r14
0x1800d957e  push    r15
0x1800d9580  mov     rbp, rsp
0x1800d9583  sub     rsp, 80h
0x1800d958a  mov     rax, cs:__security_cookie
0x1800d9591  xor     rax, rsp
0x1800d9594  mov     [rbp+var_8], rax
0x1800d9598  xor     eax, eax
0x1800d959a  mov     rsi, rcx
0x1800d959d  xorps   xmm0, xmm0
0x1800d95a0  mov     [rbp+var_10], eax
0x1800d95a3  mov     ecx, 160h; Size
0x1800d95a8  mov     [rbp+var_40], eax
0x1800d95ab  movups  [rbp+var_20], xmm0
0x1800d95af  mov     [rbp+TokenHandle], rax
0x1800d95b3  mov     r12, r8
0x1800d95b6  mov     r13, rdx
0x1800d95b9  xor     r14d, r14d
0x1800d95bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d95c1  mov     rcx, rax; this
0x1800d95c4  mov     [rbp+var_28], rax
0x1800d95c8  call    ??0IdentifyElement@CSpStorageEnclosure@@QEAA@XZ; CSpStorageEnclosure::IdentifyElement::IdentifyElement(void)
0x1800d95cd  mov     rdi, rax
0x1800d95d0  test    rax, rax
0x1800d95d3  jnz     short loc_1800D95DD
0x1800d95d5  lea     ebx, [rax+1Bh]
0x1800d95d8  jmp     loc_1800D989A
0x1800d95dd  mov     rax, [rax]
0x1800d95e0  mov     rdx, rsi
0x1800d95e3  mov     rcx, rdi
0x1800d95e6  xor     r15d, r15d
0x1800d95e9  mov     rax, [rax+8]
0x1800d95ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d95f2  lea     rcx, [rbp+var_40]
0x1800d95f6  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800d95fb  mov     [rdi+1Ch], eax
0x1800d95fe  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800d9602  mov     ecx, [rsi+14h]; unsigned int
0x1800d9605  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800d960a  mov     eax, cs:dword_18039EB68
0x1800d9610  cmp     eax, 5
0x1800d9613  jbe     short loc_1800D9683
0x1800d9615  mov     rdx, 400000000000h
0x1800d961f  lea     rcx, dword_18039EB68
0x1800d9626  call    _tlgKeywordOn
0x1800d962b  test    al, al
0x1800d962d  jz      short loc_1800D9683
0x1800d962f  mov     eax, [rbp+var_40]
0x1800d9632  lea     rdx, byte_180335B2F
0x1800d9639  xor     ecx, ecx
0x1800d963b  cmp     [rdi+1Ch], eax
0x1800d963e  movzx   eax, word ptr [rbp+var_10]
0x1800d9642  mov     word ptr [rbp+var_40], ax
0x1800d9646  setnz   cl
0x1800d9649  mov     eax, [rsi+14h]
0x1800d964c  mov     [rbp+var_38], eax
0x1800d964f  lea     rax, [rbp+var_20]
0x1800d9653  mov     [rbp+var_28], rax
0x1800d9657  lea     rax, [rbp+var_3C]
0x1800d965b  mov     [rsp+80h+var_48], rax
0x1800d9660  lea     rax, [rbp+var_40]
0x1800d9664  mov     [rsp+80h+var_50], rax
0x1800d9669  lea     rax, [rbp+var_38]
0x1800d966d  mov     [rsp+80h+var_58], rax
0x1800d9672  lea     rax, [rbp+var_28]
0x1800d9676  mov     [rsp+80h+var_60], rax
0x1800d967b  mov     [rbp+var_3C], ecx
0x1800d967e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800d9683  mov     rcx, [rsi]
0x1800d9686  test    rcx, rcx
0x1800d9689  jz      loc_1800D9870
0x1800d968f  mov     rax, [rcx]
0x1800d9692  test    rax, rax
0x1800d9695  jz      loc_1800D9870
0x1800d969b  mov     rax, [rax+18h]
0x1800d969f  lea     r8, [rdi+20h]
0x1800d96a3  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800d96aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d96af  mov     ebx, eax
0x1800d96b1  test    eax, eax
0x1800d96b3  jnz     loc_1800D9875
0x1800d96b9  cmp     [rsi+10h], r14d
0x1800d96bd  jz      loc_1800D9809
0x1800d96c3  lea     rbx, [rdi+148h]
0x1800d96ca  mov     rcx, rbx
0x1800d96cd  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800d96d2  mov     rcx, rbx; struct CSpJobMgr **
0x1800d96d5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800d96da  test    eax, eax
0x1800d96dc  jnz     short loc_1800D96E6
0x1800d96de  lea     ebx, [rax+1Ch]
0x1800d96e1  jmp     loc_1800D9875
0x1800d96e6  mov     ecx, 10h; Size
0x1800d96eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d96f0  xor     r8d, r8d; pcbe
0x1800d96f3  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800d96fa  mov     rdx, rax; pv
0x1800d96fd  mov     r15, rax
0x1800d9700  mov     [rax], rdi
0x1800d9703  call    cs:__imp_CreateThreadpoolWork
0x1800d970a  nop     dword ptr [rax+rax+00h]
0x1800d970f  mov     r14, rax
0x1800d9712  test    rax, rax
0x1800d9715  jnz     short loc_1800D9723
0x1800d9717  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800d971c  mov     ebx, eax
0x1800d971e  jmp     loc_1800D9875
0x1800d9723  call    cs:__imp_GetCurrentThread
0x1800d972a  nop     dword ptr [rax+rax+00h]
0x1800d972f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d9733  xor     r8d, r8d; OpenAsSelf
0x1800d9736  mov     rcx, rax; ThreadHandle
0x1800d9739  mov     edx, 2000Ch; DesiredAccess
0x1800d973e  call    cs:__imp_OpenThreadToken
0x1800d9745  nop     dword ptr [rax+rax+00h]
0x1800d974a  test    eax, eax
0x1800d974c  jnz     short loc_1800D9761
0x1800d974e  call    cs:__imp_GetLastError
0x1800d9755  nop     dword ptr [rax+rax+00h]
0x1800d975a  cmp     eax, 3F0h
0x1800d975f  jnz     short loc_1800D9717
0x1800d9761  mov     rax, [rbp+TokenHandle]
0x1800d9765  mov     r8, r13
0x1800d9768  mov     [r15+8], rax
0x1800d976c  mov     rcx, rdi
0x1800d976f  mov     rax, [rdi]
0x1800d9772  mov     rdx, [rsi+8]
0x1800d9776  mov     rax, [rax+18h]
0x1800d977a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d977f  mov     rax, [rdi]
0x1800d9782  mov     rdx, r12
0x1800d9785  mov     rcx, rdi
0x1800d9788  mov     rax, [rax+28h]
0x1800d978c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9791  mov     ebx, eax
0x1800d9793  test    eax, eax
0x1800d9795  jz      short loc_1800D97A0
0x1800d9797  cmp     eax, 7
0x1800d979a  jnz     loc_1800D9875
0x1800d97a0  mov     rax, [rdi]
0x1800d97a3  mov     rdx, r12
0x1800d97a6  mov     rcx, rdi
0x1800d97a9  mov     rax, [rax+38h]
0x1800d97ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d97b2  mov     ebx, eax
0x1800d97b4  test    eax, eax
0x1800d97b6  jnz     loc_1800D9875
0x1800d97bc  mov     rax, [rdi+150h]
0x1800d97c3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800d97ca  jnz     short loc_1800D97E0
0x1800d97cc  mov     rax, [rdi+158h]
0x1800d97d3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800d97da  jz      loc_1800D9875
0x1800d97e0  mov     rdx, r12
0x1800d97e3  mov     rcx, rdi
0x1800d97e6  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800d97eb  mov     ebx, eax
0x1800d97ed  test    eax, eax
0x1800d97ef  jnz     loc_1800D9875
0x1800d97f5  mov     rcx, r14; pwk
0x1800d97f8  call    cs:__imp_SubmitThreadpoolWork
0x1800d97ff  nop     dword ptr [rax+rax+00h]
0x1800d9804  jmp     loc_1800D98C3
0x1800d9809  mov     rax, [rdi]
0x1800d980c  mov     r8, r13
0x1800d980f  mov     rdx, [rsi+8]
0x1800d9813  mov     rcx, rdi
0x1800d9816  mov     rax, [rax+10h]
0x1800d981a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d981f  mov     rax, [rdi]
0x1800d9822  mov     rdx, r12
0x1800d9825  mov     rcx, rdi
0x1800d9828  mov     rax, [rax+30h]
0x1800d982c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9831  mov     ebx, eax
0x1800d9833  test    eax, eax
0x1800d9835  jz      short loc_1800D983C
0x1800d9837  cmp     eax, 7
0x1800d983a  jnz     short loc_1800D9875
0x1800d983c  mov     rax, [rdi]
0x1800d983f  mov     rdx, r12
0x1800d9842  mov     rcx, rdi
0x1800d9845  mov     rax, [rax+28h]
0x1800d9849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d984e  mov     ebx, eax
0x1800d9850  test    eax, eax
0x1800d9852  jz      short loc_1800D9859
0x1800d9854  cmp     eax, 7
0x1800d9857  jnz     short loc_1800D9875
0x1800d9859  mov     rax, [rdi]
0x1800d985c  mov     rdx, r12
0x1800d985f  mov     rcx, rdi
0x1800d9862  mov     rax, [rax+38h]
0x1800d9866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d986b  jmp     loc_1800D971C
0x1800d9870  mov     ebx, 4
0x1800d9875  mov     rax, [rdi]
0x1800d9878  mov     edx, 1
0x1800d987d  mov     rcx, rdi
0x1800d9880  mov     rax, [rax]
0x1800d9883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9888  test    r15, r15
0x1800d988b  jz      short loc_1800D989A
0x1800d988d  mov     edx, 10h
0x1800d9892  mov     rcx, r15; Block
0x1800d9895  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d989a  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d989e  test    rcx, rcx
0x1800d98a1  jz      short loc_1800D98AF
0x1800d98a3  call    cs:__imp_CloseHandle
0x1800d98aa  nop     dword ptr [rax+rax+00h]
0x1800d98af  test    r14, r14
0x1800d98b2  jz      short loc_1800D98C3
0x1800d98b4  mov     rcx, r14; pwk
0x1800d98b7  call    cs:__imp_CloseThreadpoolWork
0x1800d98be  nop     dword ptr [rax+rax+00h]
0x1800d98c3  mov     eax, ebx
0x1800d98c5  mov     rcx, [rbp+var_8]
0x1800d98c9  xor     rcx, rsp; StackCookie
0x1800d98cc  call    __security_check_cookie
0x1800d98d1  mov     rbx, [rsp+80h+arg_18]
0x1800d98d9  add     rsp, 80h
0x1800d98e0  pop     r15
0x1800d98e2  pop     r14
0x1800d98e4  pop     r13
0x1800d98e6  pop     r12
0x1800d98e8  pop     rdi
0x1800d98e9  pop     rsi
0x1800d98ea  pop     rbp
0x1800d98eb  retn
```
