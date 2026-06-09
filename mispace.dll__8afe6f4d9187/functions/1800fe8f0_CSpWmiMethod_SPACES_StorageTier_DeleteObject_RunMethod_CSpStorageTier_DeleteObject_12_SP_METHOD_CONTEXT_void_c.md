# CSpWmiMethod<_SPACES_StorageTier_DeleteObject>::RunMethod<CSpStorageTier::DeleteObject,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800fe8f0`
- end: `0x1800fec3e`
- name: `??$RunMethod@VDeleteObject@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_DeleteObject@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180102030`

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
- `0x1800fe8f0`
- `0x180100400`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800feabc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800feabc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fea9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800fea9d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800feab2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800feab2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800fea83`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800fea83`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800feb5c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800feb5c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800fec0f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800fec0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fec01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fec01`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_DeleteObject>::RunMethod<CSpStorageTier::DeleteObject,12>(
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
  CSpStorageTier::DeleteObject *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::DeleteObject *)operator new(0x160u);
  v7 = CSpStorageTier::DeleteObject::DeleteObject(v25);
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
      v25 = (CSpStorageTier::DeleteObject *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_1803396F7,
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
0x1800fe8f0  mov     [rsp-38h+arg_18], rbx
0x1800fe8f5  push    rbp
0x1800fe8f6  push    rsi
0x1800fe8f7  push    rdi
0x1800fe8f8  push    r12
0x1800fe8fa  push    r13
0x1800fe8fc  push    r14
0x1800fe8fe  push    r15
0x1800fe900  mov     rbp, rsp
0x1800fe903  sub     rsp, 80h
0x1800fe90a  mov     rax, cs:__security_cookie
0x1800fe911  xor     rax, rsp
0x1800fe914  mov     [rbp+var_8], rax
0x1800fe918  xor     eax, eax
0x1800fe91a  mov     rsi, rcx
0x1800fe91d  xorps   xmm0, xmm0
0x1800fe920  mov     [rbp+var_10], eax
0x1800fe923  mov     ecx, 160h; Size
0x1800fe928  mov     [rbp+var_40], eax
0x1800fe92b  movups  [rbp+var_20], xmm0
0x1800fe92f  mov     [rbp+TokenHandle], rax
0x1800fe933  mov     r12, r8
0x1800fe936  mov     r13, rdx
0x1800fe939  xor     r14d, r14d
0x1800fe93c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fe941  mov     rcx, rax; this
0x1800fe944  mov     [rbp+var_28], rax
0x1800fe948  call    ??0DeleteObject@CSpStorageTier@@QEAA@XZ; CSpStorageTier::DeleteObject::DeleteObject(void)
0x1800fe94d  mov     rdi, rax
0x1800fe950  test    rax, rax
0x1800fe953  jnz     short loc_1800FE95D
0x1800fe955  lea     ebx, [rax+1Bh]
0x1800fe958  jmp     loc_1800FEBF8
0x1800fe95d  mov     rax, [rax]
0x1800fe960  mov     rdx, rsi
0x1800fe963  mov     rcx, rdi
0x1800fe966  xor     r15d, r15d
0x1800fe969  mov     rax, [rax+8]
0x1800fe96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe972  lea     rcx, [rbp+var_40]
0x1800fe976  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800fe97b  mov     [rdi+1Ch], eax
0x1800fe97e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800fe982  mov     ecx, [rsi+14h]; unsigned int
0x1800fe985  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800fe98a  mov     eax, cs:dword_180397B68
0x1800fe990  cmp     eax, 5
0x1800fe993  jbe     short loc_1800FEA03
0x1800fe995  mov     rdx, 400000000000h
0x1800fe99f  lea     rcx, dword_180397B68
0x1800fe9a6  call    _tlgKeywordOn
0x1800fe9ab  test    al, al
0x1800fe9ad  jz      short loc_1800FEA03
0x1800fe9af  mov     eax, [rbp+var_40]
0x1800fe9b2  lea     rdx, byte_1803396F7
0x1800fe9b9  xor     ecx, ecx
0x1800fe9bb  cmp     [rdi+1Ch], eax
0x1800fe9be  movzx   eax, word ptr [rbp+var_10]
0x1800fe9c2  mov     word ptr [rbp+var_40], ax
0x1800fe9c6  setnz   cl
0x1800fe9c9  mov     eax, [rsi+14h]
0x1800fe9cc  mov     [rbp+var_38], eax
0x1800fe9cf  lea     rax, [rbp+var_20]
0x1800fe9d3  mov     [rbp+var_28], rax
0x1800fe9d7  lea     rax, [rbp+var_3C]
0x1800fe9db  mov     [rsp+80h+var_48], rax
0x1800fe9e0  lea     rax, [rbp+var_40]
0x1800fe9e4  mov     [rsp+80h+var_50], rax
0x1800fe9e9  lea     rax, [rbp+var_38]
0x1800fe9ed  mov     [rsp+80h+var_58], rax
0x1800fe9f2  lea     rax, [rbp+var_28]
0x1800fe9f6  mov     [rsp+80h+var_60], rax
0x1800fe9fb  mov     [rbp+var_3C], ecx
0x1800fe9fe  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800fea03  mov     rcx, [rsi]
0x1800fea06  test    rcx, rcx
0x1800fea09  jz      loc_1800FEBCE
0x1800fea0f  mov     rax, [rcx]
0x1800fea12  test    rax, rax
0x1800fea15  jz      loc_1800FEBCE
0x1800fea1b  mov     rax, [rax+18h]
0x1800fea1f  lea     r8, [rdi+20h]
0x1800fea23  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800fea2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fea2f  mov     ebx, eax
0x1800fea31  test    eax, eax
0x1800fea33  jnz     loc_1800FEBD3
0x1800fea39  cmp     [rsi+10h], r14d
0x1800fea3d  jz      loc_1800FEB67
0x1800fea43  lea     rbx, [rdi+148h]
0x1800fea4a  mov     rcx, rbx
0x1800fea4d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800fea52  mov     rcx, rbx; struct CSpJobMgr **
0x1800fea55  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800fea5a  test    eax, eax
0x1800fea5c  jnz     short loc_1800FEA66
0x1800fea5e  lea     ebx, [rax+1Ch]
0x1800fea61  jmp     loc_1800FEBD3
0x1800fea66  mov     ecx, 10h; Size
0x1800fea6b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800fea70  xor     r8d, r8d; pcbe
0x1800fea73  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800fea7a  mov     rdx, rax; pv
0x1800fea7d  mov     r15, rax
0x1800fea80  mov     [rax], rdi
0x1800fea83  call    cs:__imp_CreateThreadpoolWork
0x1800fea89  mov     r14, rax
0x1800fea8c  test    rax, rax
0x1800fea8f  jnz     short loc_1800FEA9D
0x1800fea91  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800fea96  mov     ebx, eax
0x1800fea98  jmp     loc_1800FEBD3
0x1800fea9d  call    cs:__imp_GetCurrentThread
0x1800feaa3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800feaa7  xor     r8d, r8d; OpenAsSelf
0x1800feaaa  mov     rcx, rax; ThreadHandle
0x1800feaad  mov     edx, 2000Ch; DesiredAccess
0x1800feab2  call    cs:__imp_OpenThreadToken
0x1800feab8  test    eax, eax
0x1800feaba  jnz     short loc_1800FEAC9
0x1800feabc  call    cs:__imp_GetLastError
0x1800feac2  cmp     eax, 3F0h
0x1800feac7  jnz     short loc_1800FEA91
0x1800feac9  mov     rax, [rbp+TokenHandle]
0x1800feacd  mov     r8, r13
0x1800fead0  mov     [r15+8], rax
0x1800fead4  mov     rcx, rdi
0x1800fead7  mov     rax, [rdi]
0x1800feada  mov     rdx, [rsi+8]
0x1800feade  mov     rax, [rax+18h]
0x1800feae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800feae7  mov     rax, [rdi]
0x1800feaea  mov     rdx, r12
0x1800feaed  mov     rcx, rdi
0x1800feaf0  mov     rax, [rax+28h]
0x1800feaf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800feaf9  mov     ebx, eax
0x1800feafb  test    eax, eax
0x1800feafd  jz      short loc_1800FEB08
0x1800feaff  cmp     eax, 7
0x1800feb02  jnz     loc_1800FEBD3
0x1800feb08  mov     rax, [rdi]
0x1800feb0b  mov     rdx, r12
0x1800feb0e  mov     rcx, rdi
0x1800feb11  mov     rax, [rax+38h]
0x1800feb15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800feb1a  mov     ebx, eax
0x1800feb1c  test    eax, eax
0x1800feb1e  jnz     loc_1800FEBD3
0x1800feb24  mov     rax, [rdi+150h]
0x1800feb2b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800feb32  jnz     short loc_1800FEB48
0x1800feb34  mov     rax, [rdi+158h]
0x1800feb3b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800feb42  jz      loc_1800FEBD3
0x1800feb48  mov     rdx, r12
0x1800feb4b  mov     rcx, rdi
0x1800feb4e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800feb53  mov     ebx, eax
0x1800feb55  test    eax, eax
0x1800feb57  jnz     short loc_1800FEBD3
0x1800feb59  mov     rcx, r14; pwk
0x1800feb5c  call    cs:__imp_SubmitThreadpoolWork
0x1800feb62  jmp     loc_1800FEC15
0x1800feb67  mov     rax, [rdi]
0x1800feb6a  mov     r8, r13
0x1800feb6d  mov     rdx, [rsi+8]
0x1800feb71  mov     rcx, rdi
0x1800feb74  mov     rax, [rax+10h]
0x1800feb78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800feb7d  mov     rax, [rdi]
0x1800feb80  mov     rdx, r12
0x1800feb83  mov     rcx, rdi
0x1800feb86  mov     rax, [rax+30h]
0x1800feb8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800feb8f  mov     ebx, eax
0x1800feb91  test    eax, eax
0x1800feb93  jz      short loc_1800FEB9A
0x1800feb95  cmp     eax, 7
0x1800feb98  jnz     short loc_1800FEBD3
0x1800feb9a  mov     rax, [rdi]
0x1800feb9d  mov     rdx, r12
0x1800feba0  mov     rcx, rdi
0x1800feba3  mov     rax, [rax+28h]
0x1800feba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800febac  mov     ebx, eax
0x1800febae  test    eax, eax
0x1800febb0  jz      short loc_1800FEBB7
0x1800febb2  cmp     eax, 7
0x1800febb5  jnz     short loc_1800FEBD3
0x1800febb7  mov     rax, [rdi]
0x1800febba  mov     rdx, r12
0x1800febbd  mov     rcx, rdi
0x1800febc0  mov     rax, [rax+38h]
0x1800febc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800febc9  jmp     loc_1800FEA96
0x1800febce  mov     ebx, 4
0x1800febd3  mov     rax, [rdi]
0x1800febd6  mov     edx, 1
0x1800febdb  mov     rcx, rdi
0x1800febde  mov     rax, [rax]
0x1800febe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800febe6  test    r15, r15
0x1800febe9  jz      short loc_1800FEBF8
0x1800febeb  mov     edx, 10h
0x1800febf0  mov     rcx, r15; Block
0x1800febf3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800febf8  mov     rcx, [rbp+TokenHandle]; hObject
0x1800febfc  test    rcx, rcx
0x1800febff  jz      short loc_1800FEC07
0x1800fec01  call    cs:__imp_CloseHandle
0x1800fec07  test    r14, r14
0x1800fec0a  jz      short loc_1800FEC15
0x1800fec0c  mov     rcx, r14; pwk
0x1800fec0f  call    cs:__imp_CloseThreadpoolWork
0x1800fec15  mov     eax, ebx
0x1800fec17  mov     rcx, [rbp+var_8]
0x1800fec1b  xor     rcx, rsp; StackCookie
0x1800fec1e  call    __security_check_cookie
0x1800fec23  mov     rbx, [rsp+80h+arg_18]
0x1800fec2b  add     rsp, 80h
0x1800fec32  pop     r15
0x1800fec34  pop     r14
0x1800fec36  pop     r13
0x1800fec38  pop     r12
0x1800fec3a  pop     rdi
0x1800fec3b  pop     rsi
0x1800fec3c  pop     rbp
0x1800fec3d  retn
```
