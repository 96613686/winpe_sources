# CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::SetDefaults,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bf650`
- end: `0x1800bf9cd`
- name: `??$RunMethod@VSetDefaults@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800bf650`
- `0x1800c1258`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf82e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf82e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bf803`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bf803`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bf81e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bf81e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bf7e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bf7e3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bf8d8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bf8d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bf997`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bf997`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bf983`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bf983`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::SetDefaults,11>(
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
  CSpStoragePool::SetDefaults *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::SetDefaults *)operator new(0x188u);
  v7 = CSpStoragePool::SetDefaults::SetDefaults(v25);
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
      v25 = (CSpStoragePool::SetDefaults *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_180333187,
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
0x1800bf650  mov     [rsp-38h+arg_18], rbx
0x1800bf655  push    rbp
0x1800bf656  push    rsi
0x1800bf657  push    rdi
0x1800bf658  push    r12
0x1800bf65a  push    r13
0x1800bf65c  push    r14
0x1800bf65e  push    r15
0x1800bf660  mov     rbp, rsp
0x1800bf663  sub     rsp, 80h
0x1800bf66a  mov     rax, cs:__security_cookie
0x1800bf671  xor     rax, rsp
0x1800bf674  mov     [rbp+var_8], rax
0x1800bf678  xor     eax, eax
0x1800bf67a  mov     rsi, rcx
0x1800bf67d  xorps   xmm0, xmm0
0x1800bf680  mov     [rbp+var_10], eax
0x1800bf683  mov     ecx, 188h; Size
0x1800bf688  mov     [rbp+var_40], eax
0x1800bf68b  movups  [rbp+var_20], xmm0
0x1800bf68f  mov     [rbp+TokenHandle], rax
0x1800bf693  mov     r12, r8
0x1800bf696  mov     r13, rdx
0x1800bf699  xor     r14d, r14d
0x1800bf69c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bf6a1  mov     rcx, rax; this
0x1800bf6a4  mov     [rbp+var_28], rax
0x1800bf6a8  call    ??0SetDefaults@CSpStoragePool@@QEAA@XZ; CSpStoragePool::SetDefaults::SetDefaults(void)
0x1800bf6ad  mov     rdi, rax
0x1800bf6b0  test    rax, rax
0x1800bf6b3  jnz     short loc_1800BF6BD
0x1800bf6b5  lea     ebx, [rax+1Bh]
0x1800bf6b8  jmp     loc_1800BF97A
0x1800bf6bd  mov     rax, [rax]
0x1800bf6c0  mov     rdx, rsi
0x1800bf6c3  mov     rcx, rdi
0x1800bf6c6  xor     r15d, r15d
0x1800bf6c9  mov     rax, [rax+8]
0x1800bf6cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf6d2  lea     rcx, [rbp+var_40]
0x1800bf6d6  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bf6db  mov     [rdi+1Ch], eax
0x1800bf6de  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bf6e2  mov     ecx, [rsi+14h]; unsigned int
0x1800bf6e5  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bf6ea  mov     eax, cs:dword_18039EB68
0x1800bf6f0  cmp     eax, 5
0x1800bf6f3  jbe     short loc_1800BF763
0x1800bf6f5  mov     rdx, 400000000000h
0x1800bf6ff  lea     rcx, dword_18039EB68
0x1800bf706  call    _tlgKeywordOn
0x1800bf70b  test    al, al
0x1800bf70d  jz      short loc_1800BF763
0x1800bf70f  mov     eax, [rbp+var_40]
0x1800bf712  lea     rdx, byte_180333187
0x1800bf719  xor     ecx, ecx
0x1800bf71b  cmp     [rdi+1Ch], eax
0x1800bf71e  movzx   eax, word ptr [rbp+var_10]
0x1800bf722  mov     word ptr [rbp+var_40], ax
0x1800bf726  setnz   cl
0x1800bf729  mov     eax, [rsi+14h]
0x1800bf72c  mov     [rbp+var_38], eax
0x1800bf72f  lea     rax, [rbp+var_20]
0x1800bf733  mov     [rbp+var_28], rax
0x1800bf737  lea     rax, [rbp+var_3C]
0x1800bf73b  mov     [rsp+80h+var_48], rax
0x1800bf740  lea     rax, [rbp+var_40]
0x1800bf744  mov     [rsp+80h+var_50], rax
0x1800bf749  lea     rax, [rbp+var_38]
0x1800bf74d  mov     [rsp+80h+var_58], rax
0x1800bf752  lea     rax, [rbp+var_28]
0x1800bf756  mov     [rsp+80h+var_60], rax
0x1800bf75b  mov     [rbp+var_3C], ecx
0x1800bf75e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bf763  mov     rcx, [rsi]
0x1800bf766  test    rcx, rcx
0x1800bf769  jz      loc_1800BF950
0x1800bf76f  mov     rax, [rcx]
0x1800bf772  test    rax, rax
0x1800bf775  jz      loc_1800BF950
0x1800bf77b  mov     rax, [rax+18h]
0x1800bf77f  lea     r8, [rdi+20h]
0x1800bf783  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bf78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf78f  mov     ebx, eax
0x1800bf791  test    eax, eax
0x1800bf793  jnz     loc_1800BF955
0x1800bf799  cmp     [rsi+10h], r14d
0x1800bf79d  jz      loc_1800BF8E9
0x1800bf7a3  lea     rbx, [rdi+148h]
0x1800bf7aa  mov     rcx, rbx
0x1800bf7ad  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bf7b2  mov     rcx, rbx; struct CSpJobMgr **
0x1800bf7b5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bf7ba  test    eax, eax
0x1800bf7bc  jnz     short loc_1800BF7C6
0x1800bf7be  lea     ebx, [rax+1Ch]
0x1800bf7c1  jmp     loc_1800BF955
0x1800bf7c6  mov     ecx, 10h; Size
0x1800bf7cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bf7d0  xor     r8d, r8d; pcbe
0x1800bf7d3  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bf7da  mov     rdx, rax; pv
0x1800bf7dd  mov     r15, rax
0x1800bf7e0  mov     [rax], rdi
0x1800bf7e3  call    cs:__imp_CreateThreadpoolWork
0x1800bf7ea  nop     dword ptr [rax+rax+00h]
0x1800bf7ef  mov     r14, rax
0x1800bf7f2  test    rax, rax
0x1800bf7f5  jnz     short loc_1800BF803
0x1800bf7f7  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bf7fc  mov     ebx, eax
0x1800bf7fe  jmp     loc_1800BF955
0x1800bf803  call    cs:__imp_GetCurrentThread
0x1800bf80a  nop     dword ptr [rax+rax+00h]
0x1800bf80f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bf813  xor     r8d, r8d; OpenAsSelf
0x1800bf816  mov     rcx, rax; ThreadHandle
0x1800bf819  mov     edx, 2000Ch; DesiredAccess
0x1800bf81e  call    cs:__imp_OpenThreadToken
0x1800bf825  nop     dword ptr [rax+rax+00h]
0x1800bf82a  test    eax, eax
0x1800bf82c  jnz     short loc_1800BF841
0x1800bf82e  call    cs:__imp_GetLastError
0x1800bf835  nop     dword ptr [rax+rax+00h]
0x1800bf83a  cmp     eax, 3F0h
0x1800bf83f  jnz     short loc_1800BF7F7
0x1800bf841  mov     rax, [rbp+TokenHandle]
0x1800bf845  mov     r8, r13
0x1800bf848  mov     [r15+8], rax
0x1800bf84c  mov     rcx, rdi
0x1800bf84f  mov     rax, [rdi]
0x1800bf852  mov     rdx, [rsi+8]
0x1800bf856  mov     rax, [rax+18h]
0x1800bf85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf85f  mov     rax, [rdi]
0x1800bf862  mov     rdx, r12
0x1800bf865  mov     rcx, rdi
0x1800bf868  mov     rax, [rax+28h]
0x1800bf86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf871  mov     ebx, eax
0x1800bf873  test    eax, eax
0x1800bf875  jz      short loc_1800BF880
0x1800bf877  cmp     eax, 7
0x1800bf87a  jnz     loc_1800BF955
0x1800bf880  mov     rax, [rdi]
0x1800bf883  mov     rdx, r12
0x1800bf886  mov     rcx, rdi
0x1800bf889  mov     rax, [rax+38h]
0x1800bf88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf892  mov     ebx, eax
0x1800bf894  test    eax, eax
0x1800bf896  jnz     loc_1800BF955
0x1800bf89c  mov     rax, [rdi+150h]
0x1800bf8a3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bf8aa  jnz     short loc_1800BF8C0
0x1800bf8ac  mov     rax, [rdi+158h]
0x1800bf8b3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bf8ba  jz      loc_1800BF955
0x1800bf8c0  mov     rdx, r12
0x1800bf8c3  mov     rcx, rdi
0x1800bf8c6  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bf8cb  mov     ebx, eax
0x1800bf8cd  test    eax, eax
0x1800bf8cf  jnz     loc_1800BF955
0x1800bf8d5  mov     rcx, r14; pwk
0x1800bf8d8  call    cs:__imp_SubmitThreadpoolWork
0x1800bf8df  nop     dword ptr [rax+rax+00h]
0x1800bf8e4  jmp     loc_1800BF9A3
0x1800bf8e9  mov     rax, [rdi]
0x1800bf8ec  mov     r8, r13
0x1800bf8ef  mov     rdx, [rsi+8]
0x1800bf8f3  mov     rcx, rdi
0x1800bf8f6  mov     rax, [rax+10h]
0x1800bf8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf8ff  mov     rax, [rdi]
0x1800bf902  mov     rdx, r12
0x1800bf905  mov     rcx, rdi
0x1800bf908  mov     rax, [rax+30h]
0x1800bf90c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf911  mov     ebx, eax
0x1800bf913  test    eax, eax
0x1800bf915  jz      short loc_1800BF91C
0x1800bf917  cmp     eax, 7
0x1800bf91a  jnz     short loc_1800BF955
0x1800bf91c  mov     rax, [rdi]
0x1800bf91f  mov     rdx, r12
0x1800bf922  mov     rcx, rdi
0x1800bf925  mov     rax, [rax+28h]
0x1800bf929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf92e  mov     ebx, eax
0x1800bf930  test    eax, eax
0x1800bf932  jz      short loc_1800BF939
0x1800bf934  cmp     eax, 7
0x1800bf937  jnz     short loc_1800BF955
0x1800bf939  mov     rax, [rdi]
0x1800bf93c  mov     rdx, r12
0x1800bf93f  mov     rcx, rdi
0x1800bf942  mov     rax, [rax+38h]
0x1800bf946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf94b  jmp     loc_1800BF7FC
0x1800bf950  mov     ebx, 4
0x1800bf955  mov     rax, [rdi]
0x1800bf958  mov     edx, 1
0x1800bf95d  mov     rcx, rdi
0x1800bf960  mov     rax, [rax]
0x1800bf963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf968  test    r15, r15
0x1800bf96b  jz      short loc_1800BF97A
0x1800bf96d  mov     edx, 10h
0x1800bf972  mov     rcx, r15; Block
0x1800bf975  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bf97a  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bf97e  test    rcx, rcx
0x1800bf981  jz      short loc_1800BF98F
0x1800bf983  call    cs:__imp_CloseHandle
0x1800bf98a  nop     dword ptr [rax+rax+00h]
0x1800bf98f  test    r14, r14
0x1800bf992  jz      short loc_1800BF9A3
0x1800bf994  mov     rcx, r14; pwk
0x1800bf997  call    cs:__imp_CloseThreadpoolWork
0x1800bf99e  nop     dword ptr [rax+rax+00h]
0x1800bf9a3  mov     eax, ebx
0x1800bf9a5  mov     rcx, [rbp+var_8]
0x1800bf9a9  xor     rcx, rsp; StackCookie
0x1800bf9ac  call    __security_check_cookie
0x1800bf9b1  mov     rbx, [rsp+80h+arg_18]
0x1800bf9b9  add     rsp, 80h
0x1800bf9c0  pop     r15
0x1800bf9c2  pop     r14
0x1800bf9c4  pop     r13
0x1800bf9c6  pop     r12
0x1800bf9c8  pop     rdi
0x1800bf9c9  pop     rsi
0x1800bf9ca  pop     rbp
0x1800bf9cb  retn
```
