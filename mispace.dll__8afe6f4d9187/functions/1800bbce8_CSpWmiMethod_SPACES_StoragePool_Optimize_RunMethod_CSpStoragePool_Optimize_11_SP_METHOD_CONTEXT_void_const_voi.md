# CSpWmiMethod<_SPACES_StoragePool_Optimize>::RunMethod<CSpStoragePool::Optimize,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bbce8`
- end: `0x1800bc036`
- name: `??$RunMethod@VOptimize@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_Optimize@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800bbce8`
- `0x1800be040`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbeb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbeb4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bbe95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bbe95`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bbeaa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bbeaa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bbe7b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bbe7b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bbf54`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bbf54`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bc007`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bc007`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbff9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bbff9`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_Optimize>::RunMethod<CSpStoragePool::Optimize,11>(
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
  CSpStoragePool::Optimize *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::Optimize *)operator new(0x168u);
  v7 = CSpStoragePool::Optimize::Optimize(v25);
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
      v25 = (CSpStoragePool::Optimize *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_18032C4CE,
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
0x1800bbce8  mov     [rsp-38h+arg_18], rbx
0x1800bbced  push    rbp
0x1800bbcee  push    rsi
0x1800bbcef  push    rdi
0x1800bbcf0  push    r12
0x1800bbcf2  push    r13
0x1800bbcf4  push    r14
0x1800bbcf6  push    r15
0x1800bbcf8  mov     rbp, rsp
0x1800bbcfb  sub     rsp, 80h
0x1800bbd02  mov     rax, cs:__security_cookie
0x1800bbd09  xor     rax, rsp
0x1800bbd0c  mov     [rbp+var_8], rax
0x1800bbd10  xor     eax, eax
0x1800bbd12  mov     rsi, rcx
0x1800bbd15  xorps   xmm0, xmm0
0x1800bbd18  mov     [rbp+var_10], eax
0x1800bbd1b  mov     ecx, 168h; Size
0x1800bbd20  mov     [rbp+var_40], eax
0x1800bbd23  movups  [rbp+var_20], xmm0
0x1800bbd27  mov     [rbp+TokenHandle], rax
0x1800bbd2b  mov     r12, r8
0x1800bbd2e  mov     r13, rdx
0x1800bbd31  xor     r14d, r14d
0x1800bbd34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bbd39  mov     rcx, rax; this
0x1800bbd3c  mov     [rbp+var_28], rax
0x1800bbd40  call    ??0Optimize@CSpStoragePool@@QEAA@XZ; CSpStoragePool::Optimize::Optimize(void)
0x1800bbd45  mov     rdi, rax
0x1800bbd48  test    rax, rax
0x1800bbd4b  jnz     short loc_1800BBD55
0x1800bbd4d  lea     ebx, [rax+1Bh]
0x1800bbd50  jmp     loc_1800BBFF0
0x1800bbd55  mov     rax, [rax]
0x1800bbd58  mov     rdx, rsi
0x1800bbd5b  mov     rcx, rdi
0x1800bbd5e  xor     r15d, r15d
0x1800bbd61  mov     rax, [rax+8]
0x1800bbd65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbd6a  lea     rcx, [rbp+var_40]
0x1800bbd6e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bbd73  mov     [rdi+1Ch], eax
0x1800bbd76  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bbd7a  mov     ecx, [rsi+14h]; unsigned int
0x1800bbd7d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bbd82  mov     eax, cs:dword_180397B68
0x1800bbd88  cmp     eax, 5
0x1800bbd8b  jbe     short loc_1800BBDFB
0x1800bbd8d  mov     rdx, 400000000000h
0x1800bbd97  lea     rcx, dword_180397B68
0x1800bbd9e  call    _tlgKeywordOn
0x1800bbda3  test    al, al
0x1800bbda5  jz      short loc_1800BBDFB
0x1800bbda7  mov     eax, [rbp+var_40]
0x1800bbdaa  lea     rdx, word_18032C4CE
0x1800bbdb1  xor     ecx, ecx
0x1800bbdb3  cmp     [rdi+1Ch], eax
0x1800bbdb6  movzx   eax, word ptr [rbp+var_10]
0x1800bbdba  mov     word ptr [rbp+var_40], ax
0x1800bbdbe  setnz   cl
0x1800bbdc1  mov     eax, [rsi+14h]
0x1800bbdc4  mov     [rbp+var_38], eax
0x1800bbdc7  lea     rax, [rbp+var_20]
0x1800bbdcb  mov     [rbp+var_28], rax
0x1800bbdcf  lea     rax, [rbp+var_3C]
0x1800bbdd3  mov     [rsp+80h+var_48], rax
0x1800bbdd8  lea     rax, [rbp+var_40]
0x1800bbddc  mov     [rsp+80h+var_50], rax
0x1800bbde1  lea     rax, [rbp+var_38]
0x1800bbde5  mov     [rsp+80h+var_58], rax
0x1800bbdea  lea     rax, [rbp+var_28]
0x1800bbdee  mov     [rsp+80h+var_60], rax
0x1800bbdf3  mov     [rbp+var_3C], ecx
0x1800bbdf6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bbdfb  mov     rcx, [rsi]
0x1800bbdfe  test    rcx, rcx
0x1800bbe01  jz      loc_1800BBFC6
0x1800bbe07  mov     rax, [rcx]
0x1800bbe0a  test    rax, rax
0x1800bbe0d  jz      loc_1800BBFC6
0x1800bbe13  mov     rax, [rax+18h]
0x1800bbe17  lea     r8, [rdi+20h]
0x1800bbe1b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bbe22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbe27  mov     ebx, eax
0x1800bbe29  test    eax, eax
0x1800bbe2b  jnz     loc_1800BBFCB
0x1800bbe31  cmp     [rsi+10h], r14d
0x1800bbe35  jz      loc_1800BBF5F
0x1800bbe3b  lea     rbx, [rdi+148h]
0x1800bbe42  mov     rcx, rbx
0x1800bbe45  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bbe4a  mov     rcx, rbx; struct CSpJobMgr **
0x1800bbe4d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bbe52  test    eax, eax
0x1800bbe54  jnz     short loc_1800BBE5E
0x1800bbe56  lea     ebx, [rax+1Ch]
0x1800bbe59  jmp     loc_1800BBFCB
0x1800bbe5e  mov     ecx, 10h; Size
0x1800bbe63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bbe68  xor     r8d, r8d; pcbe
0x1800bbe6b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bbe72  mov     rdx, rax; pv
0x1800bbe75  mov     r15, rax
0x1800bbe78  mov     [rax], rdi
0x1800bbe7b  call    cs:__imp_CreateThreadpoolWork
0x1800bbe81  mov     r14, rax
0x1800bbe84  test    rax, rax
0x1800bbe87  jnz     short loc_1800BBE95
0x1800bbe89  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bbe8e  mov     ebx, eax
0x1800bbe90  jmp     loc_1800BBFCB
0x1800bbe95  call    cs:__imp_GetCurrentThread
0x1800bbe9b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bbe9f  xor     r8d, r8d; OpenAsSelf
0x1800bbea2  mov     rcx, rax; ThreadHandle
0x1800bbea5  mov     edx, 2000Ch; DesiredAccess
0x1800bbeaa  call    cs:__imp_OpenThreadToken
0x1800bbeb0  test    eax, eax
0x1800bbeb2  jnz     short loc_1800BBEC1
0x1800bbeb4  call    cs:__imp_GetLastError
0x1800bbeba  cmp     eax, 3F0h
0x1800bbebf  jnz     short loc_1800BBE89
0x1800bbec1  mov     rax, [rbp+TokenHandle]
0x1800bbec5  mov     r8, r13
0x1800bbec8  mov     [r15+8], rax
0x1800bbecc  mov     rcx, rdi
0x1800bbecf  mov     rax, [rdi]
0x1800bbed2  mov     rdx, [rsi+8]
0x1800bbed6  mov     rax, [rax+18h]
0x1800bbeda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbedf  mov     rax, [rdi]
0x1800bbee2  mov     rdx, r12
0x1800bbee5  mov     rcx, rdi
0x1800bbee8  mov     rax, [rax+28h]
0x1800bbeec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbef1  mov     ebx, eax
0x1800bbef3  test    eax, eax
0x1800bbef5  jz      short loc_1800BBF00
0x1800bbef7  cmp     eax, 7
0x1800bbefa  jnz     loc_1800BBFCB
0x1800bbf00  mov     rax, [rdi]
0x1800bbf03  mov     rdx, r12
0x1800bbf06  mov     rcx, rdi
0x1800bbf09  mov     rax, [rax+38h]
0x1800bbf0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbf12  mov     ebx, eax
0x1800bbf14  test    eax, eax
0x1800bbf16  jnz     loc_1800BBFCB
0x1800bbf1c  mov     rax, [rdi+150h]
0x1800bbf23  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bbf2a  jnz     short loc_1800BBF40
0x1800bbf2c  mov     rax, [rdi+158h]
0x1800bbf33  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bbf3a  jz      loc_1800BBFCB
0x1800bbf40  mov     rdx, r12
0x1800bbf43  mov     rcx, rdi
0x1800bbf46  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bbf4b  mov     ebx, eax
0x1800bbf4d  test    eax, eax
0x1800bbf4f  jnz     short loc_1800BBFCB
0x1800bbf51  mov     rcx, r14; pwk
0x1800bbf54  call    cs:__imp_SubmitThreadpoolWork
0x1800bbf5a  jmp     loc_1800BC00D
0x1800bbf5f  mov     rax, [rdi]
0x1800bbf62  mov     r8, r13
0x1800bbf65  mov     rdx, [rsi+8]
0x1800bbf69  mov     rcx, rdi
0x1800bbf6c  mov     rax, [rax+10h]
0x1800bbf70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbf75  mov     rax, [rdi]
0x1800bbf78  mov     rdx, r12
0x1800bbf7b  mov     rcx, rdi
0x1800bbf7e  mov     rax, [rax+30h]
0x1800bbf82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbf87  mov     ebx, eax
0x1800bbf89  test    eax, eax
0x1800bbf8b  jz      short loc_1800BBF92
0x1800bbf8d  cmp     eax, 7
0x1800bbf90  jnz     short loc_1800BBFCB
0x1800bbf92  mov     rax, [rdi]
0x1800bbf95  mov     rdx, r12
0x1800bbf98  mov     rcx, rdi
0x1800bbf9b  mov     rax, [rax+28h]
0x1800bbf9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbfa4  mov     ebx, eax
0x1800bbfa6  test    eax, eax
0x1800bbfa8  jz      short loc_1800BBFAF
0x1800bbfaa  cmp     eax, 7
0x1800bbfad  jnz     short loc_1800BBFCB
0x1800bbfaf  mov     rax, [rdi]
0x1800bbfb2  mov     rdx, r12
0x1800bbfb5  mov     rcx, rdi
0x1800bbfb8  mov     rax, [rax+38h]
0x1800bbfbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbfc1  jmp     loc_1800BBE8E
0x1800bbfc6  mov     ebx, 4
0x1800bbfcb  mov     rax, [rdi]
0x1800bbfce  mov     edx, 1
0x1800bbfd3  mov     rcx, rdi
0x1800bbfd6  mov     rax, [rax]
0x1800bbfd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbfde  test    r15, r15
0x1800bbfe1  jz      short loc_1800BBFF0
0x1800bbfe3  mov     edx, 10h
0x1800bbfe8  mov     rcx, r15; Block
0x1800bbfeb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bbff0  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bbff4  test    rcx, rcx
0x1800bbff7  jz      short loc_1800BBFFF
0x1800bbff9  call    cs:__imp_CloseHandle
0x1800bbfff  test    r14, r14
0x1800bc002  jz      short loc_1800BC00D
0x1800bc004  mov     rcx, r14; pwk
0x1800bc007  call    cs:__imp_CloseThreadpoolWork
0x1800bc00d  mov     eax, ebx
0x1800bc00f  mov     rcx, [rbp+var_8]
0x1800bc013  xor     rcx, rsp; StackCookie
0x1800bc016  call    __security_check_cookie
0x1800bc01b  mov     rbx, [rsp+80h+arg_18]
0x1800bc023  add     rsp, 80h
0x1800bc02a  pop     r15
0x1800bc02c  pop     r14
0x1800bc02e  pop     r13
0x1800bc030  pop     r12
0x1800bc032  pop     rdi
0x1800bc033  pop     rsi
0x1800bc034  pop     rbp
0x1800bc035  retn
```
