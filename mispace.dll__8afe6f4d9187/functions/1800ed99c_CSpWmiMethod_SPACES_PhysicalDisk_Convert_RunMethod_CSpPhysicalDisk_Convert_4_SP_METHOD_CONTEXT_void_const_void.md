# CSpWmiMethod<_SPACES_PhysicalDisk_Convert>::RunMethod<CSpPhysicalDisk::Convert,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ed99c`
- end: `0x1800edcea`
- name: `??$RunMethod@VConvert@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_Convert@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800ed99c`
- `0x1800f01a4`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edb68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edb68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800edb49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800edb49`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800edb5e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800edb5e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800edb2f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800edb2f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800edc08`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800edc08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800edcbb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800edcbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800edcad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800edcad`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_Convert>::RunMethod<CSpPhysicalDisk::Convert,4>(
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
  CSpPhysicalDisk::Convert *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::Convert *)operator new(0x1D0u);
  v7 = CSpPhysicalDisk::Convert::Convert(v25);
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
      v25 = (CSpPhysicalDisk::Convert *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_1803357A1,
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
0x1800ed99c  mov     [rsp-38h+arg_18], rbx
0x1800ed9a1  push    rbp
0x1800ed9a2  push    rsi
0x1800ed9a3  push    rdi
0x1800ed9a4  push    r12
0x1800ed9a6  push    r13
0x1800ed9a8  push    r14
0x1800ed9aa  push    r15
0x1800ed9ac  mov     rbp, rsp
0x1800ed9af  sub     rsp, 80h
0x1800ed9b6  mov     rax, cs:__security_cookie
0x1800ed9bd  xor     rax, rsp
0x1800ed9c0  mov     [rbp+var_8], rax
0x1800ed9c4  xor     eax, eax
0x1800ed9c6  mov     rsi, rcx
0x1800ed9c9  xorps   xmm0, xmm0
0x1800ed9cc  mov     [rbp+var_10], eax
0x1800ed9cf  mov     ecx, 1D0h; Size
0x1800ed9d4  mov     [rbp+var_40], eax
0x1800ed9d7  movups  [rbp+var_20], xmm0
0x1800ed9db  mov     [rbp+TokenHandle], rax
0x1800ed9df  mov     r12, r8
0x1800ed9e2  mov     r13, rdx
0x1800ed9e5  xor     r14d, r14d
0x1800ed9e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ed9ed  mov     rcx, rax; this
0x1800ed9f0  mov     [rbp+var_28], rax
0x1800ed9f4  call    ??0Convert@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::Convert::Convert(void)
0x1800ed9f9  mov     rdi, rax
0x1800ed9fc  test    rax, rax
0x1800ed9ff  jnz     short loc_1800EDA09
0x1800eda01  lea     ebx, [rax+1Bh]
0x1800eda04  jmp     loc_1800EDCA4
0x1800eda09  mov     rax, [rax]
0x1800eda0c  mov     rdx, rsi
0x1800eda0f  mov     rcx, rdi
0x1800eda12  xor     r15d, r15d
0x1800eda15  mov     rax, [rax+8]
0x1800eda19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eda1e  lea     rcx, [rbp+var_40]
0x1800eda22  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800eda27  mov     [rdi+1Ch], eax
0x1800eda2a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800eda2e  mov     ecx, [rsi+14h]; unsigned int
0x1800eda31  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800eda36  mov     eax, cs:dword_180397B68
0x1800eda3c  cmp     eax, 5
0x1800eda3f  jbe     short loc_1800EDAAF
0x1800eda41  mov     rdx, 400000000000h
0x1800eda4b  lea     rcx, dword_180397B68
0x1800eda52  call    _tlgKeywordOn
0x1800eda57  test    al, al
0x1800eda59  jz      short loc_1800EDAAF
0x1800eda5b  mov     eax, [rbp+var_40]
0x1800eda5e  lea     rdx, byte_1803357A1
0x1800eda65  xor     ecx, ecx
0x1800eda67  cmp     [rdi+1Ch], eax
0x1800eda6a  movzx   eax, word ptr [rbp+var_10]
0x1800eda6e  mov     word ptr [rbp+var_40], ax
0x1800eda72  setnz   cl
0x1800eda75  mov     eax, [rsi+14h]
0x1800eda78  mov     [rbp+var_38], eax
0x1800eda7b  lea     rax, [rbp+var_20]
0x1800eda7f  mov     [rbp+var_28], rax
0x1800eda83  lea     rax, [rbp+var_3C]
0x1800eda87  mov     [rsp+80h+var_48], rax
0x1800eda8c  lea     rax, [rbp+var_40]
0x1800eda90  mov     [rsp+80h+var_50], rax
0x1800eda95  lea     rax, [rbp+var_38]
0x1800eda99  mov     [rsp+80h+var_58], rax
0x1800eda9e  lea     rax, [rbp+var_28]
0x1800edaa2  mov     [rsp+80h+var_60], rax
0x1800edaa7  mov     [rbp+var_3C], ecx
0x1800edaaa  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800edaaf  mov     rcx, [rsi]
0x1800edab2  test    rcx, rcx
0x1800edab5  jz      loc_1800EDC7A
0x1800edabb  mov     rax, [rcx]
0x1800edabe  test    rax, rax
0x1800edac1  jz      loc_1800EDC7A
0x1800edac7  mov     rax, [rax+18h]
0x1800edacb  lea     r8, [rdi+20h]
0x1800edacf  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800edad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edadb  mov     ebx, eax
0x1800edadd  test    eax, eax
0x1800edadf  jnz     loc_1800EDC7F
0x1800edae5  cmp     [rsi+10h], r14d
0x1800edae9  jz      loc_1800EDC13
0x1800edaef  lea     rbx, [rdi+148h]
0x1800edaf6  mov     rcx, rbx
0x1800edaf9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800edafe  mov     rcx, rbx; struct CSpJobMgr **
0x1800edb01  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800edb06  test    eax, eax
0x1800edb08  jnz     short loc_1800EDB12
0x1800edb0a  lea     ebx, [rax+1Ch]
0x1800edb0d  jmp     loc_1800EDC7F
0x1800edb12  mov     ecx, 10h; Size
0x1800edb17  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800edb1c  xor     r8d, r8d; pcbe
0x1800edb1f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800edb26  mov     rdx, rax; pv
0x1800edb29  mov     r15, rax
0x1800edb2c  mov     [rax], rdi
0x1800edb2f  call    cs:__imp_CreateThreadpoolWork
0x1800edb35  mov     r14, rax
0x1800edb38  test    rax, rax
0x1800edb3b  jnz     short loc_1800EDB49
0x1800edb3d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800edb42  mov     ebx, eax
0x1800edb44  jmp     loc_1800EDC7F
0x1800edb49  call    cs:__imp_GetCurrentThread
0x1800edb4f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800edb53  xor     r8d, r8d; OpenAsSelf
0x1800edb56  mov     rcx, rax; ThreadHandle
0x1800edb59  mov     edx, 2000Ch; DesiredAccess
0x1800edb5e  call    cs:__imp_OpenThreadToken
0x1800edb64  test    eax, eax
0x1800edb66  jnz     short loc_1800EDB75
0x1800edb68  call    cs:__imp_GetLastError
0x1800edb6e  cmp     eax, 3F0h
0x1800edb73  jnz     short loc_1800EDB3D
0x1800edb75  mov     rax, [rbp+TokenHandle]
0x1800edb79  mov     r8, r13
0x1800edb7c  mov     [r15+8], rax
0x1800edb80  mov     rcx, rdi
0x1800edb83  mov     rax, [rdi]
0x1800edb86  mov     rdx, [rsi+8]
0x1800edb8a  mov     rax, [rax+18h]
0x1800edb8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edb93  mov     rax, [rdi]
0x1800edb96  mov     rdx, r12
0x1800edb99  mov     rcx, rdi
0x1800edb9c  mov     rax, [rax+28h]
0x1800edba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edba5  mov     ebx, eax
0x1800edba7  test    eax, eax
0x1800edba9  jz      short loc_1800EDBB4
0x1800edbab  cmp     eax, 7
0x1800edbae  jnz     loc_1800EDC7F
0x1800edbb4  mov     rax, [rdi]
0x1800edbb7  mov     rdx, r12
0x1800edbba  mov     rcx, rdi
0x1800edbbd  mov     rax, [rax+38h]
0x1800edbc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edbc6  mov     ebx, eax
0x1800edbc8  test    eax, eax
0x1800edbca  jnz     loc_1800EDC7F
0x1800edbd0  mov     rax, [rdi+150h]
0x1800edbd7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800edbde  jnz     short loc_1800EDBF4
0x1800edbe0  mov     rax, [rdi+158h]
0x1800edbe7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800edbee  jz      loc_1800EDC7F
0x1800edbf4  mov     rdx, r12
0x1800edbf7  mov     rcx, rdi
0x1800edbfa  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800edbff  mov     ebx, eax
0x1800edc01  test    eax, eax
0x1800edc03  jnz     short loc_1800EDC7F
0x1800edc05  mov     rcx, r14; pwk
0x1800edc08  call    cs:__imp_SubmitThreadpoolWork
0x1800edc0e  jmp     loc_1800EDCC1
0x1800edc13  mov     rax, [rdi]
0x1800edc16  mov     r8, r13
0x1800edc19  mov     rdx, [rsi+8]
0x1800edc1d  mov     rcx, rdi
0x1800edc20  mov     rax, [rax+10h]
0x1800edc24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edc29  mov     rax, [rdi]
0x1800edc2c  mov     rdx, r12
0x1800edc2f  mov     rcx, rdi
0x1800edc32  mov     rax, [rax+30h]
0x1800edc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edc3b  mov     ebx, eax
0x1800edc3d  test    eax, eax
0x1800edc3f  jz      short loc_1800EDC46
0x1800edc41  cmp     eax, 7
0x1800edc44  jnz     short loc_1800EDC7F
0x1800edc46  mov     rax, [rdi]
0x1800edc49  mov     rdx, r12
0x1800edc4c  mov     rcx, rdi
0x1800edc4f  mov     rax, [rax+28h]
0x1800edc53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edc58  mov     ebx, eax
0x1800edc5a  test    eax, eax
0x1800edc5c  jz      short loc_1800EDC63
0x1800edc5e  cmp     eax, 7
0x1800edc61  jnz     short loc_1800EDC7F
0x1800edc63  mov     rax, [rdi]
0x1800edc66  mov     rdx, r12
0x1800edc69  mov     rcx, rdi
0x1800edc6c  mov     rax, [rax+38h]
0x1800edc70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edc75  jmp     loc_1800EDB42
0x1800edc7a  mov     ebx, 4
0x1800edc7f  mov     rax, [rdi]
0x1800edc82  mov     edx, 1
0x1800edc87  mov     rcx, rdi
0x1800edc8a  mov     rax, [rax]
0x1800edc8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800edc92  test    r15, r15
0x1800edc95  jz      short loc_1800EDCA4
0x1800edc97  mov     edx, 10h
0x1800edc9c  mov     rcx, r15; Block
0x1800edc9f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800edca4  mov     rcx, [rbp+TokenHandle]; hObject
0x1800edca8  test    rcx, rcx
0x1800edcab  jz      short loc_1800EDCB3
0x1800edcad  call    cs:__imp_CloseHandle
0x1800edcb3  test    r14, r14
0x1800edcb6  jz      short loc_1800EDCC1
0x1800edcb8  mov     rcx, r14; pwk
0x1800edcbb  call    cs:__imp_CloseThreadpoolWork
0x1800edcc1  mov     eax, ebx
0x1800edcc3  mov     rcx, [rbp+var_8]
0x1800edcc7  xor     rcx, rsp; StackCookie
0x1800edcca  call    __security_check_cookie
0x1800edccf  mov     rbx, [rsp+80h+arg_18]
0x1800edcd7  add     rsp, 80h
0x1800edcde  pop     r15
0x1800edce0  pop     r14
0x1800edce2  pop     r13
0x1800edce4  pop     r12
0x1800edce6  pop     rdi
0x1800edce7  pop     rsi
0x1800edce8  pop     rbp
0x1800edce9  retn
```
