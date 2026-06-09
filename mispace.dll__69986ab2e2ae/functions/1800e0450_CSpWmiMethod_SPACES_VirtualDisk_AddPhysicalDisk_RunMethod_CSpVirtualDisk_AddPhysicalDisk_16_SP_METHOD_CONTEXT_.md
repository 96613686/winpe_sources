# CSpWmiMethod<_SPACES_VirtualDisk_AddPhysicalDisk>::RunMethod<CSpVirtualDisk::AddPhysicalDisk,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e0450`
- end: `0x1800e07cd`
- name: `??$RunMethod@VAddPhysicalDisk@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_AddPhysicalDisk@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800e7d60`

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
- `0x1800e0450`
- `0x1800e3c90`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e062e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e062e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0603`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0603`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e061e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e061e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e05e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e05e3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e06d8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e06d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e0797`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e0797`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0783`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0783`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_AddPhysicalDisk>::RunMethod<CSpVirtualDisk::AddPhysicalDisk,16>(
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
  CSpVirtualDisk::AddPhysicalDisk *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::AddPhysicalDisk *)operator new(0x160u);
  v7 = CSpVirtualDisk::AddPhysicalDisk::AddPhysicalDisk(v25);
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
      v25 = (CSpVirtualDisk::AddPhysicalDisk *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_180338463,
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
0x1800e0450  mov     [rsp-38h+arg_18], rbx
0x1800e0455  push    rbp
0x1800e0456  push    rsi
0x1800e0457  push    rdi
0x1800e0458  push    r12
0x1800e045a  push    r13
0x1800e045c  push    r14
0x1800e045e  push    r15
0x1800e0460  mov     rbp, rsp
0x1800e0463  sub     rsp, 80h
0x1800e046a  mov     rax, cs:__security_cookie
0x1800e0471  xor     rax, rsp
0x1800e0474  mov     [rbp+var_8], rax
0x1800e0478  xor     eax, eax
0x1800e047a  mov     rsi, rcx
0x1800e047d  xorps   xmm0, xmm0
0x1800e0480  mov     [rbp+var_10], eax
0x1800e0483  mov     ecx, 160h; Size
0x1800e0488  mov     [rbp+var_40], eax
0x1800e048b  movups  [rbp+var_20], xmm0
0x1800e048f  mov     [rbp+TokenHandle], rax
0x1800e0493  mov     r12, r8
0x1800e0496  mov     r13, rdx
0x1800e0499  xor     r14d, r14d
0x1800e049c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e04a1  mov     rcx, rax; this
0x1800e04a4  mov     [rbp+var_28], rax
0x1800e04a8  call    ??0AddPhysicalDisk@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::AddPhysicalDisk::AddPhysicalDisk(void)
0x1800e04ad  mov     rdi, rax
0x1800e04b0  test    rax, rax
0x1800e04b3  jnz     short loc_1800E04BD
0x1800e04b5  lea     ebx, [rax+1Bh]
0x1800e04b8  jmp     loc_1800E077A
0x1800e04bd  mov     rax, [rax]
0x1800e04c0  mov     rdx, rsi
0x1800e04c3  mov     rcx, rdi
0x1800e04c6  xor     r15d, r15d
0x1800e04c9  mov     rax, [rax+8]
0x1800e04cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e04d2  lea     rcx, [rbp+var_40]
0x1800e04d6  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e04db  mov     [rdi+1Ch], eax
0x1800e04de  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e04e2  mov     ecx, [rsi+14h]; unsigned int
0x1800e04e5  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e04ea  mov     eax, cs:dword_18039EB68
0x1800e04f0  cmp     eax, 5
0x1800e04f3  jbe     short loc_1800E0563
0x1800e04f5  mov     rdx, 400000000000h
0x1800e04ff  lea     rcx, dword_18039EB68
0x1800e0506  call    _tlgKeywordOn
0x1800e050b  test    al, al
0x1800e050d  jz      short loc_1800E0563
0x1800e050f  mov     eax, [rbp+var_40]
0x1800e0512  lea     rdx, byte_180338463
0x1800e0519  xor     ecx, ecx
0x1800e051b  cmp     [rdi+1Ch], eax
0x1800e051e  movzx   eax, word ptr [rbp+var_10]
0x1800e0522  mov     word ptr [rbp+var_40], ax
0x1800e0526  setnz   cl
0x1800e0529  mov     eax, [rsi+14h]
0x1800e052c  mov     [rbp+var_38], eax
0x1800e052f  lea     rax, [rbp+var_20]
0x1800e0533  mov     [rbp+var_28], rax
0x1800e0537  lea     rax, [rbp+var_3C]
0x1800e053b  mov     [rsp+80h+var_48], rax
0x1800e0540  lea     rax, [rbp+var_40]
0x1800e0544  mov     [rsp+80h+var_50], rax
0x1800e0549  lea     rax, [rbp+var_38]
0x1800e054d  mov     [rsp+80h+var_58], rax
0x1800e0552  lea     rax, [rbp+var_28]
0x1800e0556  mov     [rsp+80h+var_60], rax
0x1800e055b  mov     [rbp+var_3C], ecx
0x1800e055e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e0563  mov     rcx, [rsi]
0x1800e0566  test    rcx, rcx
0x1800e0569  jz      loc_1800E0750
0x1800e056f  mov     rax, [rcx]
0x1800e0572  test    rax, rax
0x1800e0575  jz      loc_1800E0750
0x1800e057b  mov     rax, [rax+18h]
0x1800e057f  lea     r8, [rdi+20h]
0x1800e0583  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e058a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e058f  mov     ebx, eax
0x1800e0591  test    eax, eax
0x1800e0593  jnz     loc_1800E0755
0x1800e0599  cmp     [rsi+10h], r14d
0x1800e059d  jz      loc_1800E06E9
0x1800e05a3  lea     rbx, [rdi+148h]
0x1800e05aa  mov     rcx, rbx
0x1800e05ad  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e05b2  mov     rcx, rbx; struct CSpJobMgr **
0x1800e05b5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e05ba  test    eax, eax
0x1800e05bc  jnz     short loc_1800E05C6
0x1800e05be  lea     ebx, [rax+1Ch]
0x1800e05c1  jmp     loc_1800E0755
0x1800e05c6  mov     ecx, 10h; Size
0x1800e05cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e05d0  xor     r8d, r8d; pcbe
0x1800e05d3  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e05da  mov     rdx, rax; pv
0x1800e05dd  mov     r15, rax
0x1800e05e0  mov     [rax], rdi
0x1800e05e3  call    cs:__imp_CreateThreadpoolWork
0x1800e05ea  nop     dword ptr [rax+rax+00h]
0x1800e05ef  mov     r14, rax
0x1800e05f2  test    rax, rax
0x1800e05f5  jnz     short loc_1800E0603
0x1800e05f7  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e05fc  mov     ebx, eax
0x1800e05fe  jmp     loc_1800E0755
0x1800e0603  call    cs:__imp_GetCurrentThread
0x1800e060a  nop     dword ptr [rax+rax+00h]
0x1800e060f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e0613  xor     r8d, r8d; OpenAsSelf
0x1800e0616  mov     rcx, rax; ThreadHandle
0x1800e0619  mov     edx, 2000Ch; DesiredAccess
0x1800e061e  call    cs:__imp_OpenThreadToken
0x1800e0625  nop     dword ptr [rax+rax+00h]
0x1800e062a  test    eax, eax
0x1800e062c  jnz     short loc_1800E0641
0x1800e062e  call    cs:__imp_GetLastError
0x1800e0635  nop     dword ptr [rax+rax+00h]
0x1800e063a  cmp     eax, 3F0h
0x1800e063f  jnz     short loc_1800E05F7
0x1800e0641  mov     rax, [rbp+TokenHandle]
0x1800e0645  mov     r8, r13
0x1800e0648  mov     [r15+8], rax
0x1800e064c  mov     rcx, rdi
0x1800e064f  mov     rax, [rdi]
0x1800e0652  mov     rdx, [rsi+8]
0x1800e0656  mov     rax, [rax+18h]
0x1800e065a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e065f  mov     rax, [rdi]
0x1800e0662  mov     rdx, r12
0x1800e0665  mov     rcx, rdi
0x1800e0668  mov     rax, [rax+28h]
0x1800e066c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0671  mov     ebx, eax
0x1800e0673  test    eax, eax
0x1800e0675  jz      short loc_1800E0680
0x1800e0677  cmp     eax, 7
0x1800e067a  jnz     loc_1800E0755
0x1800e0680  mov     rax, [rdi]
0x1800e0683  mov     rdx, r12
0x1800e0686  mov     rcx, rdi
0x1800e0689  mov     rax, [rax+38h]
0x1800e068d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0692  mov     ebx, eax
0x1800e0694  test    eax, eax
0x1800e0696  jnz     loc_1800E0755
0x1800e069c  mov     rax, [rdi+150h]
0x1800e06a3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e06aa  jnz     short loc_1800E06C0
0x1800e06ac  mov     rax, [rdi+158h]
0x1800e06b3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e06ba  jz      loc_1800E0755
0x1800e06c0  mov     rdx, r12
0x1800e06c3  mov     rcx, rdi
0x1800e06c6  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e06cb  mov     ebx, eax
0x1800e06cd  test    eax, eax
0x1800e06cf  jnz     loc_1800E0755
0x1800e06d5  mov     rcx, r14; pwk
0x1800e06d8  call    cs:__imp_SubmitThreadpoolWork
0x1800e06df  nop     dword ptr [rax+rax+00h]
0x1800e06e4  jmp     loc_1800E07A3
0x1800e06e9  mov     rax, [rdi]
0x1800e06ec  mov     r8, r13
0x1800e06ef  mov     rdx, [rsi+8]
0x1800e06f3  mov     rcx, rdi
0x1800e06f6  mov     rax, [rax+10h]
0x1800e06fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e06ff  mov     rax, [rdi]
0x1800e0702  mov     rdx, r12
0x1800e0705  mov     rcx, rdi
0x1800e0708  mov     rax, [rax+30h]
0x1800e070c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0711  mov     ebx, eax
0x1800e0713  test    eax, eax
0x1800e0715  jz      short loc_1800E071C
0x1800e0717  cmp     eax, 7
0x1800e071a  jnz     short loc_1800E0755
0x1800e071c  mov     rax, [rdi]
0x1800e071f  mov     rdx, r12
0x1800e0722  mov     rcx, rdi
0x1800e0725  mov     rax, [rax+28h]
0x1800e0729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e072e  mov     ebx, eax
0x1800e0730  test    eax, eax
0x1800e0732  jz      short loc_1800E0739
0x1800e0734  cmp     eax, 7
0x1800e0737  jnz     short loc_1800E0755
0x1800e0739  mov     rax, [rdi]
0x1800e073c  mov     rdx, r12
0x1800e073f  mov     rcx, rdi
0x1800e0742  mov     rax, [rax+38h]
0x1800e0746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e074b  jmp     loc_1800E05FC
0x1800e0750  mov     ebx, 4
0x1800e0755  mov     rax, [rdi]
0x1800e0758  mov     edx, 1
0x1800e075d  mov     rcx, rdi
0x1800e0760  mov     rax, [rax]
0x1800e0763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0768  test    r15, r15
0x1800e076b  jz      short loc_1800E077A
0x1800e076d  mov     edx, 10h
0x1800e0772  mov     rcx, r15; Block
0x1800e0775  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e077a  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e077e  test    rcx, rcx
0x1800e0781  jz      short loc_1800E078F
0x1800e0783  call    cs:__imp_CloseHandle
0x1800e078a  nop     dword ptr [rax+rax+00h]
0x1800e078f  test    r14, r14
0x1800e0792  jz      short loc_1800E07A3
0x1800e0794  mov     rcx, r14; pwk
0x1800e0797  call    cs:__imp_CloseThreadpoolWork
0x1800e079e  nop     dword ptr [rax+rax+00h]
0x1800e07a3  mov     eax, ebx
0x1800e07a5  mov     rcx, [rbp+var_8]
0x1800e07a9  xor     rcx, rsp; StackCookie
0x1800e07ac  call    __security_check_cookie
0x1800e07b1  mov     rbx, [rsp+80h+arg_18]
0x1800e07b9  add     rsp, 80h
0x1800e07c0  pop     r15
0x1800e07c2  pop     r14
0x1800e07c4  pop     r13
0x1800e07c6  pop     r12
0x1800e07c8  pop     rdi
0x1800e07c9  pop     rsi
0x1800e07ca  pop     rbp
0x1800e07cb  retn
```
