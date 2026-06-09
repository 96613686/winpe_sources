# CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::RunMethod<CSpPhysicalDisk::GetPhysicalExtent,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ee044`
- end: `0x1800ee392`
- name: `??$RunMethod@VGetPhysicalExtent@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800f3f30`

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
- `0x1800ee044`
- `0x1800f0300`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee210`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ee1f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ee1f1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ee206`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ee206`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ee1d7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ee1d7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ee2b0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ee2b0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ee363`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ee363`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ee355`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::RunMethod<CSpPhysicalDisk::GetPhysicalExtent,4>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 PhysicalExtent; // rax
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
  CSpPhysicalDisk::GetPhysicalExtent *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::GetPhysicalExtent *)operator new(0x170u);
  PhysicalExtent = CSpPhysicalDisk::GetPhysicalExtent::GetPhysicalExtent(v25);
  v8 = PhysicalExtent;
  if ( PhysicalExtent )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)PhysicalExtent + 8LL))(PhysicalExtent, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpPhysicalDisk::GetPhysicalExtent *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_180334538,
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
0x1800ee044  mov     [rsp-38h+arg_18], rbx
0x1800ee049  push    rbp
0x1800ee04a  push    rsi
0x1800ee04b  push    rdi
0x1800ee04c  push    r12
0x1800ee04e  push    r13
0x1800ee050  push    r14
0x1800ee052  push    r15
0x1800ee054  mov     rbp, rsp
0x1800ee057  sub     rsp, 80h
0x1800ee05e  mov     rax, cs:__security_cookie
0x1800ee065  xor     rax, rsp
0x1800ee068  mov     [rbp+var_8], rax
0x1800ee06c  xor     eax, eax
0x1800ee06e  mov     rsi, rcx
0x1800ee071  xorps   xmm0, xmm0
0x1800ee074  mov     [rbp+var_10], eax
0x1800ee077  mov     ecx, 170h; Size
0x1800ee07c  mov     [rbp+var_40], eax
0x1800ee07f  movups  [rbp+var_20], xmm0
0x1800ee083  mov     [rbp+TokenHandle], rax
0x1800ee087  mov     r12, r8
0x1800ee08a  mov     r13, rdx
0x1800ee08d  xor     r14d, r14d
0x1800ee090  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ee095  mov     rcx, rax; this
0x1800ee098  mov     [rbp+var_28], rax
0x1800ee09c  call    ??0GetPhysicalExtent@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::GetPhysicalExtent::GetPhysicalExtent(void)
0x1800ee0a1  mov     rdi, rax
0x1800ee0a4  test    rax, rax
0x1800ee0a7  jnz     short loc_1800EE0B1
0x1800ee0a9  lea     ebx, [rax+1Bh]
0x1800ee0ac  jmp     loc_1800EE34C
0x1800ee0b1  mov     rax, [rax]
0x1800ee0b4  mov     rdx, rsi
0x1800ee0b7  mov     rcx, rdi
0x1800ee0ba  xor     r15d, r15d
0x1800ee0bd  mov     rax, [rax+8]
0x1800ee0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee0c6  lea     rcx, [rbp+var_40]
0x1800ee0ca  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ee0cf  mov     [rdi+1Ch], eax
0x1800ee0d2  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ee0d6  mov     ecx, [rsi+14h]; unsigned int
0x1800ee0d9  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ee0de  mov     eax, cs:dword_180397B68
0x1800ee0e4  cmp     eax, 5
0x1800ee0e7  jbe     short loc_1800EE157
0x1800ee0e9  mov     rdx, 400000000000h
0x1800ee0f3  lea     rcx, dword_180397B68
0x1800ee0fa  call    _tlgKeywordOn
0x1800ee0ff  test    al, al
0x1800ee101  jz      short loc_1800EE157
0x1800ee103  mov     eax, [rbp+var_40]
0x1800ee106  lea     rdx, unk_180334538
0x1800ee10d  xor     ecx, ecx
0x1800ee10f  cmp     [rdi+1Ch], eax
0x1800ee112  movzx   eax, word ptr [rbp+var_10]
0x1800ee116  mov     word ptr [rbp+var_40], ax
0x1800ee11a  setnz   cl
0x1800ee11d  mov     eax, [rsi+14h]
0x1800ee120  mov     [rbp+var_38], eax
0x1800ee123  lea     rax, [rbp+var_20]
0x1800ee127  mov     [rbp+var_28], rax
0x1800ee12b  lea     rax, [rbp+var_3C]
0x1800ee12f  mov     [rsp+80h+var_48], rax
0x1800ee134  lea     rax, [rbp+var_40]
0x1800ee138  mov     [rsp+80h+var_50], rax
0x1800ee13d  lea     rax, [rbp+var_38]
0x1800ee141  mov     [rsp+80h+var_58], rax
0x1800ee146  lea     rax, [rbp+var_28]
0x1800ee14a  mov     [rsp+80h+var_60], rax
0x1800ee14f  mov     [rbp+var_3C], ecx
0x1800ee152  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ee157  mov     rcx, [rsi]
0x1800ee15a  test    rcx, rcx
0x1800ee15d  jz      loc_1800EE322
0x1800ee163  mov     rax, [rcx]
0x1800ee166  test    rax, rax
0x1800ee169  jz      loc_1800EE322
0x1800ee16f  mov     rax, [rax+18h]
0x1800ee173  lea     r8, [rdi+20h]
0x1800ee177  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ee17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee183  mov     ebx, eax
0x1800ee185  test    eax, eax
0x1800ee187  jnz     loc_1800EE327
0x1800ee18d  cmp     [rsi+10h], r14d
0x1800ee191  jz      loc_1800EE2BB
0x1800ee197  lea     rbx, [rdi+148h]
0x1800ee19e  mov     rcx, rbx
0x1800ee1a1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ee1a6  mov     rcx, rbx; struct CSpJobMgr **
0x1800ee1a9  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ee1ae  test    eax, eax
0x1800ee1b0  jnz     short loc_1800EE1BA
0x1800ee1b2  lea     ebx, [rax+1Ch]
0x1800ee1b5  jmp     loc_1800EE327
0x1800ee1ba  mov     ecx, 10h; Size
0x1800ee1bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ee1c4  xor     r8d, r8d; pcbe
0x1800ee1c7  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ee1ce  mov     rdx, rax; pv
0x1800ee1d1  mov     r15, rax
0x1800ee1d4  mov     [rax], rdi
0x1800ee1d7  call    cs:__imp_CreateThreadpoolWork
0x1800ee1dd  mov     r14, rax
0x1800ee1e0  test    rax, rax
0x1800ee1e3  jnz     short loc_1800EE1F1
0x1800ee1e5  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800ee1ea  mov     ebx, eax
0x1800ee1ec  jmp     loc_1800EE327
0x1800ee1f1  call    cs:__imp_GetCurrentThread
0x1800ee1f7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ee1fb  xor     r8d, r8d; OpenAsSelf
0x1800ee1fe  mov     rcx, rax; ThreadHandle
0x1800ee201  mov     edx, 2000Ch; DesiredAccess
0x1800ee206  call    cs:__imp_OpenThreadToken
0x1800ee20c  test    eax, eax
0x1800ee20e  jnz     short loc_1800EE21D
0x1800ee210  call    cs:__imp_GetLastError
0x1800ee216  cmp     eax, 3F0h
0x1800ee21b  jnz     short loc_1800EE1E5
0x1800ee21d  mov     rax, [rbp+TokenHandle]
0x1800ee221  mov     r8, r13
0x1800ee224  mov     [r15+8], rax
0x1800ee228  mov     rcx, rdi
0x1800ee22b  mov     rax, [rdi]
0x1800ee22e  mov     rdx, [rsi+8]
0x1800ee232  mov     rax, [rax+18h]
0x1800ee236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee23b  mov     rax, [rdi]
0x1800ee23e  mov     rdx, r12
0x1800ee241  mov     rcx, rdi
0x1800ee244  mov     rax, [rax+28h]
0x1800ee248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee24d  mov     ebx, eax
0x1800ee24f  test    eax, eax
0x1800ee251  jz      short loc_1800EE25C
0x1800ee253  cmp     eax, 7
0x1800ee256  jnz     loc_1800EE327
0x1800ee25c  mov     rax, [rdi]
0x1800ee25f  mov     rdx, r12
0x1800ee262  mov     rcx, rdi
0x1800ee265  mov     rax, [rax+38h]
0x1800ee269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee26e  mov     ebx, eax
0x1800ee270  test    eax, eax
0x1800ee272  jnz     loc_1800EE327
0x1800ee278  mov     rax, [rdi+150h]
0x1800ee27f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800ee286  jnz     short loc_1800EE29C
0x1800ee288  mov     rax, [rdi+158h]
0x1800ee28f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800ee296  jz      loc_1800EE327
0x1800ee29c  mov     rdx, r12
0x1800ee29f  mov     rcx, rdi
0x1800ee2a2  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800ee2a7  mov     ebx, eax
0x1800ee2a9  test    eax, eax
0x1800ee2ab  jnz     short loc_1800EE327
0x1800ee2ad  mov     rcx, r14; pwk
0x1800ee2b0  call    cs:__imp_SubmitThreadpoolWork
0x1800ee2b6  jmp     loc_1800EE369
0x1800ee2bb  mov     rax, [rdi]
0x1800ee2be  mov     r8, r13
0x1800ee2c1  mov     rdx, [rsi+8]
0x1800ee2c5  mov     rcx, rdi
0x1800ee2c8  mov     rax, [rax+10h]
0x1800ee2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee2d1  mov     rax, [rdi]
0x1800ee2d4  mov     rdx, r12
0x1800ee2d7  mov     rcx, rdi
0x1800ee2da  mov     rax, [rax+30h]
0x1800ee2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee2e3  mov     ebx, eax
0x1800ee2e5  test    eax, eax
0x1800ee2e7  jz      short loc_1800EE2EE
0x1800ee2e9  cmp     eax, 7
0x1800ee2ec  jnz     short loc_1800EE327
0x1800ee2ee  mov     rax, [rdi]
0x1800ee2f1  mov     rdx, r12
0x1800ee2f4  mov     rcx, rdi
0x1800ee2f7  mov     rax, [rax+28h]
0x1800ee2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee300  mov     ebx, eax
0x1800ee302  test    eax, eax
0x1800ee304  jz      short loc_1800EE30B
0x1800ee306  cmp     eax, 7
0x1800ee309  jnz     short loc_1800EE327
0x1800ee30b  mov     rax, [rdi]
0x1800ee30e  mov     rdx, r12
0x1800ee311  mov     rcx, rdi
0x1800ee314  mov     rax, [rax+38h]
0x1800ee318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee31d  jmp     loc_1800EE1EA
0x1800ee322  mov     ebx, 4
0x1800ee327  mov     rax, [rdi]
0x1800ee32a  mov     edx, 1
0x1800ee32f  mov     rcx, rdi
0x1800ee332  mov     rax, [rax]
0x1800ee335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee33a  test    r15, r15
0x1800ee33d  jz      short loc_1800EE34C
0x1800ee33f  mov     edx, 10h
0x1800ee344  mov     rcx, r15; Block
0x1800ee347  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ee34c  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ee350  test    rcx, rcx
0x1800ee353  jz      short loc_1800EE35B
0x1800ee355  call    cs:__imp_CloseHandle
0x1800ee35b  test    r14, r14
0x1800ee35e  jz      short loc_1800EE369
0x1800ee360  mov     rcx, r14; pwk
0x1800ee363  call    cs:__imp_CloseThreadpoolWork
0x1800ee369  mov     eax, ebx
0x1800ee36b  mov     rcx, [rbp+var_8]
0x1800ee36f  xor     rcx, rsp; StackCookie
0x1800ee372  call    __security_check_cookie
0x1800ee377  mov     rbx, [rsp+80h+arg_18]
0x1800ee37f  add     rsp, 80h
0x1800ee386  pop     r15
0x1800ee388  pop     r14
0x1800ee38a  pop     r13
0x1800ee38c  pop     r12
0x1800ee38e  pop     rdi
0x1800ee38f  pop     rsi
0x1800ee390  pop     rbp
0x1800ee391  retn
```
