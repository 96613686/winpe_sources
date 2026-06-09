# CSpWmiMethod<_SPACES_StorageReliabilityCounter_Reset>::RunMethod<CSpReliabilityCounter::Reset,6>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800fe784`
- end: `0x1800feb01`
- name: `??$RunMethod@VReset@CSpReliabilityCounter@@$05@?$CSpWmiMethod@U_SPACES_StorageReliabilityCounter_Reset@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800ff3a0`

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
- `0x18005f41c`
- `0x1800d7c5c`
- `0x1800fe784`
- `0x1800feb08`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe962`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fe937`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fe937`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800fe952`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800fe952`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800fe917`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800fe917`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800fea0c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800fea0c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800feacb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800feacb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800feab7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800feab7`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageReliabilityCounter_Reset>::RunMethod<CSpReliabilityCounter::Reset,6>(
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
  CSpReliabilityCounter::Reset *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpReliabilityCounter::Reset *)operator new(0x160u);
  v7 = CSpReliabilityCounter::Reset::Reset(v25);
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
      v25 = (CSpReliabilityCounter::Reset *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18033ECB5,
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
                v9 = CSpWmiMethod<_SPACES_StorageReliabilityCounter_Reset>::SetCreatedJob(v8, a3);
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
0x1800fe784  mov     [rsp-38h+arg_18], rbx
0x1800fe789  push    rbp
0x1800fe78a  push    rsi
0x1800fe78b  push    rdi
0x1800fe78c  push    r12
0x1800fe78e  push    r13
0x1800fe790  push    r14
0x1800fe792  push    r15
0x1800fe794  mov     rbp, rsp
0x1800fe797  sub     rsp, 80h
0x1800fe79e  mov     rax, cs:__security_cookie
0x1800fe7a5  xor     rax, rsp
0x1800fe7a8  mov     [rbp+var_8], rax
0x1800fe7ac  xor     eax, eax
0x1800fe7ae  mov     rsi, rcx
0x1800fe7b1  xorps   xmm0, xmm0
0x1800fe7b4  mov     [rbp+var_10], eax
0x1800fe7b7  mov     ecx, 160h; Size
0x1800fe7bc  mov     [rbp+var_40], eax
0x1800fe7bf  movups  [rbp+var_20], xmm0
0x1800fe7c3  mov     [rbp+TokenHandle], rax
0x1800fe7c7  mov     r12, r8
0x1800fe7ca  mov     r13, rdx
0x1800fe7cd  xor     r14d, r14d
0x1800fe7d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fe7d5  mov     rcx, rax; this
0x1800fe7d8  mov     [rbp+var_28], rax
0x1800fe7dc  call    ??0Reset@CSpReliabilityCounter@@QEAA@XZ; CSpReliabilityCounter::Reset::Reset(void)
0x1800fe7e1  mov     rdi, rax
0x1800fe7e4  test    rax, rax
0x1800fe7e7  jnz     short loc_1800FE7F1
0x1800fe7e9  lea     ebx, [rax+1Bh]
0x1800fe7ec  jmp     loc_1800FEAAE
0x1800fe7f1  mov     rax, [rax]
0x1800fe7f4  mov     rdx, rsi
0x1800fe7f7  mov     rcx, rdi
0x1800fe7fa  xor     r15d, r15d
0x1800fe7fd  mov     rax, [rax+8]
0x1800fe801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe806  lea     rcx, [rbp+var_40]
0x1800fe80a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800fe80f  mov     [rdi+1Ch], eax
0x1800fe812  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800fe816  mov     ecx, [rsi+14h]; unsigned int
0x1800fe819  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800fe81e  mov     eax, cs:dword_18039EB68
0x1800fe824  cmp     eax, 5
0x1800fe827  jbe     short loc_1800FE897
0x1800fe829  mov     rdx, 400000000000h
0x1800fe833  lea     rcx, dword_18039EB68
0x1800fe83a  call    _tlgKeywordOn
0x1800fe83f  test    al, al
0x1800fe841  jz      short loc_1800FE897
0x1800fe843  mov     eax, [rbp+var_40]
0x1800fe846  lea     rdx, byte_18033ECB5
0x1800fe84d  xor     ecx, ecx
0x1800fe84f  cmp     [rdi+1Ch], eax
0x1800fe852  movzx   eax, word ptr [rbp+var_10]
0x1800fe856  mov     word ptr [rbp+var_40], ax
0x1800fe85a  setnz   cl
0x1800fe85d  mov     eax, [rsi+14h]
0x1800fe860  mov     [rbp+var_38], eax
0x1800fe863  lea     rax, [rbp+var_20]
0x1800fe867  mov     [rbp+var_28], rax
0x1800fe86b  lea     rax, [rbp+var_3C]
0x1800fe86f  mov     [rsp+80h+var_48], rax
0x1800fe874  lea     rax, [rbp+var_40]
0x1800fe878  mov     [rsp+80h+var_50], rax
0x1800fe87d  lea     rax, [rbp+var_38]
0x1800fe881  mov     [rsp+80h+var_58], rax
0x1800fe886  lea     rax, [rbp+var_28]
0x1800fe88a  mov     [rsp+80h+var_60], rax
0x1800fe88f  mov     [rbp+var_3C], ecx
0x1800fe892  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800fe897  mov     rcx, [rsi]
0x1800fe89a  test    rcx, rcx
0x1800fe89d  jz      loc_1800FEA84
0x1800fe8a3  mov     rax, [rcx]
0x1800fe8a6  test    rax, rax
0x1800fe8a9  jz      loc_1800FEA84
0x1800fe8af  mov     rax, [rax+18h]
0x1800fe8b3  lea     r8, [rdi+20h]
0x1800fe8b7  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800fe8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe8c3  mov     ebx, eax
0x1800fe8c5  test    eax, eax
0x1800fe8c7  jnz     loc_1800FEA89
0x1800fe8cd  cmp     [rsi+10h], r14d
0x1800fe8d1  jz      loc_1800FEA1D
0x1800fe8d7  lea     rbx, [rdi+148h]
0x1800fe8de  mov     rcx, rbx
0x1800fe8e1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800fe8e6  mov     rcx, rbx; struct CSpJobMgr **
0x1800fe8e9  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800fe8ee  test    eax, eax
0x1800fe8f0  jnz     short loc_1800FE8FA
0x1800fe8f2  lea     ebx, [rax+1Ch]
0x1800fe8f5  jmp     loc_1800FEA89
0x1800fe8fa  mov     ecx, 10h; Size
0x1800fe8ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fe904  xor     r8d, r8d; pcbe
0x1800fe907  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800fe90e  mov     rdx, rax; pv
0x1800fe911  mov     r15, rax
0x1800fe914  mov     [rax], rdi
0x1800fe917  call    cs:__imp_CreateThreadpoolWork
0x1800fe91e  nop     dword ptr [rax+rax+00h]
0x1800fe923  mov     r14, rax
0x1800fe926  test    rax, rax
0x1800fe929  jnz     short loc_1800FE937
0x1800fe92b  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800fe930  mov     ebx, eax
0x1800fe932  jmp     loc_1800FEA89
0x1800fe937  call    cs:__imp_GetCurrentThread
0x1800fe93e  nop     dword ptr [rax+rax+00h]
0x1800fe943  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800fe947  xor     r8d, r8d; OpenAsSelf
0x1800fe94a  mov     rcx, rax; ThreadHandle
0x1800fe94d  mov     edx, 2000Ch; DesiredAccess
0x1800fe952  call    cs:__imp_OpenThreadToken
0x1800fe959  nop     dword ptr [rax+rax+00h]
0x1800fe95e  test    eax, eax
0x1800fe960  jnz     short loc_1800FE975
0x1800fe962  call    cs:__imp_GetLastError
0x1800fe969  nop     dword ptr [rax+rax+00h]
0x1800fe96e  cmp     eax, 3F0h
0x1800fe973  jnz     short loc_1800FE92B
0x1800fe975  mov     rax, [rbp+TokenHandle]
0x1800fe979  mov     r8, r13
0x1800fe97c  mov     [r15+8], rax
0x1800fe980  mov     rcx, rdi
0x1800fe983  mov     rax, [rdi]
0x1800fe986  mov     rdx, [rsi+8]
0x1800fe98a  mov     rax, [rax+18h]
0x1800fe98e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe993  mov     rax, [rdi]
0x1800fe996  mov     rdx, r12
0x1800fe999  mov     rcx, rdi
0x1800fe99c  mov     rax, [rax+28h]
0x1800fe9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe9a5  mov     ebx, eax
0x1800fe9a7  test    eax, eax
0x1800fe9a9  jz      short loc_1800FE9B4
0x1800fe9ab  cmp     eax, 7
0x1800fe9ae  jnz     loc_1800FEA89
0x1800fe9b4  mov     rax, [rdi]
0x1800fe9b7  mov     rdx, r12
0x1800fe9ba  mov     rcx, rdi
0x1800fe9bd  mov     rax, [rax+38h]
0x1800fe9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe9c6  mov     ebx, eax
0x1800fe9c8  test    eax, eax
0x1800fe9ca  jnz     loc_1800FEA89
0x1800fe9d0  mov     rax, [rdi+150h]
0x1800fe9d7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800fe9de  jnz     short loc_1800FE9F4
0x1800fe9e0  mov     rax, [rdi+158h]
0x1800fe9e7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800fe9ee  jz      loc_1800FEA89
0x1800fe9f4  mov     rdx, r12
0x1800fe9f7  mov     rcx, rdi
0x1800fe9fa  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StorageReliabilityCounter_Reset@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StorageReliabilityCounter_Reset@@@Z; CSpWmiMethod<_SPACES_StorageReliabilityCounter_Reset>::SetCreatedJob(_SPACES_StorageReliabilityCounter_Reset *)
0x1800fe9ff  mov     ebx, eax
0x1800fea01  test    eax, eax
0x1800fea03  jnz     loc_1800FEA89
0x1800fea09  mov     rcx, r14; pwk
0x1800fea0c  call    cs:__imp_SubmitThreadpoolWork
0x1800fea13  nop     dword ptr [rax+rax+00h]
0x1800fea18  jmp     loc_1800FEAD7
0x1800fea1d  mov     rax, [rdi]
0x1800fea20  mov     r8, r13
0x1800fea23  mov     rdx, [rsi+8]
0x1800fea27  mov     rcx, rdi
0x1800fea2a  mov     rax, [rax+10h]
0x1800fea2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fea33  mov     rax, [rdi]
0x1800fea36  mov     rdx, r12
0x1800fea39  mov     rcx, rdi
0x1800fea3c  mov     rax, [rax+30h]
0x1800fea40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fea45  mov     ebx, eax
0x1800fea47  test    eax, eax
0x1800fea49  jz      short loc_1800FEA50
0x1800fea4b  cmp     eax, 7
0x1800fea4e  jnz     short loc_1800FEA89
0x1800fea50  mov     rax, [rdi]
0x1800fea53  mov     rdx, r12
0x1800fea56  mov     rcx, rdi
0x1800fea59  mov     rax, [rax+28h]
0x1800fea5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fea62  mov     ebx, eax
0x1800fea64  test    eax, eax
0x1800fea66  jz      short loc_1800FEA6D
0x1800fea68  cmp     eax, 7
0x1800fea6b  jnz     short loc_1800FEA89
0x1800fea6d  mov     rax, [rdi]
0x1800fea70  mov     rdx, r12
0x1800fea73  mov     rcx, rdi
0x1800fea76  mov     rax, [rax+38h]
0x1800fea7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fea7f  jmp     loc_1800FE930
0x1800fea84  mov     ebx, 4
0x1800fea89  mov     rax, [rdi]
0x1800fea8c  mov     edx, 1
0x1800fea91  mov     rcx, rdi
0x1800fea94  mov     rax, [rax]
0x1800fea97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fea9c  test    r15, r15
0x1800fea9f  jz      short loc_1800FEAAE
0x1800feaa1  mov     edx, 10h
0x1800feaa6  mov     rcx, r15; Block
0x1800feaa9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800feaae  mov     rcx, [rbp+TokenHandle]; hObject
0x1800feab2  test    rcx, rcx
0x1800feab5  jz      short loc_1800FEAC3
0x1800feab7  call    cs:__imp_CloseHandle
0x1800feabe  nop     dword ptr [rax+rax+00h]
0x1800feac3  test    r14, r14
0x1800feac6  jz      short loc_1800FEAD7
0x1800feac8  mov     rcx, r14; pwk
0x1800feacb  call    cs:__imp_CloseThreadpoolWork
0x1800fead2  nop     dword ptr [rax+rax+00h]
0x1800fead7  mov     eax, ebx
0x1800fead9  mov     rcx, [rbp+var_8]
0x1800feadd  xor     rcx, rsp; StackCookie
0x1800feae0  call    __security_check_cookie
0x1800feae5  mov     rbx, [rsp+80h+arg_18]
0x1800feaed  add     rsp, 80h
0x1800feaf4  pop     r15
0x1800feaf6  pop     r14
0x1800feaf8  pop     r13
0x1800feafa  pop     r12
0x1800feafc  pop     rdi
0x1800feafd  pop     rsi
0x1800feafe  pop     rbp
0x1800feaff  retn
```
