# CSpWmiMethod<_SPACES_PhysicalDisk_SetUsage>::RunMethod<CSpPhysicalDisk::SetUsage,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800efafc`
- end: `0x1800efe4a`
- name: `??$RunMethod@VSetUsage@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_SetUsage@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800efafc`
- `0x1800f05c8`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efcc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800efcc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800efca9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800efca9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800efcbe`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800efcbe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800efc8f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800efc8f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800efd68`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800efd68`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800efe1b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800efe1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800efe0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800efe0d`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_SetUsage>::RunMethod<CSpPhysicalDisk::SetUsage,4>(
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
  CSpPhysicalDisk::SetUsage *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::SetUsage *)operator new(0x160u);
  v7 = CSpPhysicalDisk::SetUsage::SetUsage(v25);
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
      v25 = (CSpPhysicalDisk::SetUsage *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_180336CEE,
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
0x1800efafc  mov     [rsp-38h+arg_18], rbx
0x1800efb01  push    rbp
0x1800efb02  push    rsi
0x1800efb03  push    rdi
0x1800efb04  push    r12
0x1800efb06  push    r13
0x1800efb08  push    r14
0x1800efb0a  push    r15
0x1800efb0c  mov     rbp, rsp
0x1800efb0f  sub     rsp, 80h
0x1800efb16  mov     rax, cs:__security_cookie
0x1800efb1d  xor     rax, rsp
0x1800efb20  mov     [rbp+var_8], rax
0x1800efb24  xor     eax, eax
0x1800efb26  mov     rsi, rcx
0x1800efb29  xorps   xmm0, xmm0
0x1800efb2c  mov     [rbp+var_10], eax
0x1800efb2f  mov     ecx, 160h; Size
0x1800efb34  mov     [rbp+var_40], eax
0x1800efb37  movups  [rbp+var_20], xmm0
0x1800efb3b  mov     [rbp+TokenHandle], rax
0x1800efb3f  mov     r12, r8
0x1800efb42  mov     r13, rdx
0x1800efb45  xor     r14d, r14d
0x1800efb48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800efb4d  mov     rcx, rax; this
0x1800efb50  mov     [rbp+var_28], rax
0x1800efb54  call    ??0SetUsage@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::SetUsage::SetUsage(void)
0x1800efb59  mov     rdi, rax
0x1800efb5c  test    rax, rax
0x1800efb5f  jnz     short loc_1800EFB69
0x1800efb61  lea     ebx, [rax+1Bh]
0x1800efb64  jmp     loc_1800EFE04
0x1800efb69  mov     rax, [rax]
0x1800efb6c  mov     rdx, rsi
0x1800efb6f  mov     rcx, rdi
0x1800efb72  xor     r15d, r15d
0x1800efb75  mov     rax, [rax+8]
0x1800efb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efb7e  lea     rcx, [rbp+var_40]
0x1800efb82  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800efb87  mov     [rdi+1Ch], eax
0x1800efb8a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800efb8e  mov     ecx, [rsi+14h]; unsigned int
0x1800efb91  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800efb96  mov     eax, cs:dword_180397B68
0x1800efb9c  cmp     eax, 5
0x1800efb9f  jbe     short loc_1800EFC0F
0x1800efba1  mov     rdx, 400000000000h
0x1800efbab  lea     rcx, dword_180397B68
0x1800efbb2  call    _tlgKeywordOn
0x1800efbb7  test    al, al
0x1800efbb9  jz      short loc_1800EFC0F
0x1800efbbb  mov     eax, [rbp+var_40]
0x1800efbbe  lea     rdx, word_180336CEE
0x1800efbc5  xor     ecx, ecx
0x1800efbc7  cmp     [rdi+1Ch], eax
0x1800efbca  movzx   eax, word ptr [rbp+var_10]
0x1800efbce  mov     word ptr [rbp+var_40], ax
0x1800efbd2  setnz   cl
0x1800efbd5  mov     eax, [rsi+14h]
0x1800efbd8  mov     [rbp+var_38], eax
0x1800efbdb  lea     rax, [rbp+var_20]
0x1800efbdf  mov     [rbp+var_28], rax
0x1800efbe3  lea     rax, [rbp+var_3C]
0x1800efbe7  mov     [rsp+80h+var_48], rax
0x1800efbec  lea     rax, [rbp+var_40]
0x1800efbf0  mov     [rsp+80h+var_50], rax
0x1800efbf5  lea     rax, [rbp+var_38]
0x1800efbf9  mov     [rsp+80h+var_58], rax
0x1800efbfe  lea     rax, [rbp+var_28]
0x1800efc02  mov     [rsp+80h+var_60], rax
0x1800efc07  mov     [rbp+var_3C], ecx
0x1800efc0a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800efc0f  mov     rcx, [rsi]
0x1800efc12  test    rcx, rcx
0x1800efc15  jz      loc_1800EFDDA
0x1800efc1b  mov     rax, [rcx]
0x1800efc1e  test    rax, rax
0x1800efc21  jz      loc_1800EFDDA
0x1800efc27  mov     rax, [rax+18h]
0x1800efc2b  lea     r8, [rdi+20h]
0x1800efc2f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800efc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efc3b  mov     ebx, eax
0x1800efc3d  test    eax, eax
0x1800efc3f  jnz     loc_1800EFDDF
0x1800efc45  cmp     [rsi+10h], r14d
0x1800efc49  jz      loc_1800EFD73
0x1800efc4f  lea     rbx, [rdi+148h]
0x1800efc56  mov     rcx, rbx
0x1800efc59  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800efc5e  mov     rcx, rbx; struct CSpJobMgr **
0x1800efc61  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800efc66  test    eax, eax
0x1800efc68  jnz     short loc_1800EFC72
0x1800efc6a  lea     ebx, [rax+1Ch]
0x1800efc6d  jmp     loc_1800EFDDF
0x1800efc72  mov     ecx, 10h; Size
0x1800efc77  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800efc7c  xor     r8d, r8d; pcbe
0x1800efc7f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800efc86  mov     rdx, rax; pv
0x1800efc89  mov     r15, rax
0x1800efc8c  mov     [rax], rdi
0x1800efc8f  call    cs:__imp_CreateThreadpoolWork
0x1800efc95  mov     r14, rax
0x1800efc98  test    rax, rax
0x1800efc9b  jnz     short loc_1800EFCA9
0x1800efc9d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800efca2  mov     ebx, eax
0x1800efca4  jmp     loc_1800EFDDF
0x1800efca9  call    cs:__imp_GetCurrentThread
0x1800efcaf  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800efcb3  xor     r8d, r8d; OpenAsSelf
0x1800efcb6  mov     rcx, rax; ThreadHandle
0x1800efcb9  mov     edx, 2000Ch; DesiredAccess
0x1800efcbe  call    cs:__imp_OpenThreadToken
0x1800efcc4  test    eax, eax
0x1800efcc6  jnz     short loc_1800EFCD5
0x1800efcc8  call    cs:__imp_GetLastError
0x1800efcce  cmp     eax, 3F0h
0x1800efcd3  jnz     short loc_1800EFC9D
0x1800efcd5  mov     rax, [rbp+TokenHandle]
0x1800efcd9  mov     r8, r13
0x1800efcdc  mov     [r15+8], rax
0x1800efce0  mov     rcx, rdi
0x1800efce3  mov     rax, [rdi]
0x1800efce6  mov     rdx, [rsi+8]
0x1800efcea  mov     rax, [rax+18h]
0x1800efcee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efcf3  mov     rax, [rdi]
0x1800efcf6  mov     rdx, r12
0x1800efcf9  mov     rcx, rdi
0x1800efcfc  mov     rax, [rax+28h]
0x1800efd00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efd05  mov     ebx, eax
0x1800efd07  test    eax, eax
0x1800efd09  jz      short loc_1800EFD14
0x1800efd0b  cmp     eax, 7
0x1800efd0e  jnz     loc_1800EFDDF
0x1800efd14  mov     rax, [rdi]
0x1800efd17  mov     rdx, r12
0x1800efd1a  mov     rcx, rdi
0x1800efd1d  mov     rax, [rax+38h]
0x1800efd21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efd26  mov     ebx, eax
0x1800efd28  test    eax, eax
0x1800efd2a  jnz     loc_1800EFDDF
0x1800efd30  mov     rax, [rdi+150h]
0x1800efd37  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800efd3e  jnz     short loc_1800EFD54
0x1800efd40  mov     rax, [rdi+158h]
0x1800efd47  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800efd4e  jz      loc_1800EFDDF
0x1800efd54  mov     rdx, r12
0x1800efd57  mov     rcx, rdi
0x1800efd5a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800efd5f  mov     ebx, eax
0x1800efd61  test    eax, eax
0x1800efd63  jnz     short loc_1800EFDDF
0x1800efd65  mov     rcx, r14; pwk
0x1800efd68  call    cs:__imp_SubmitThreadpoolWork
0x1800efd6e  jmp     loc_1800EFE21
0x1800efd73  mov     rax, [rdi]
0x1800efd76  mov     r8, r13
0x1800efd79  mov     rdx, [rsi+8]
0x1800efd7d  mov     rcx, rdi
0x1800efd80  mov     rax, [rax+10h]
0x1800efd84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efd89  mov     rax, [rdi]
0x1800efd8c  mov     rdx, r12
0x1800efd8f  mov     rcx, rdi
0x1800efd92  mov     rax, [rax+30h]
0x1800efd96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efd9b  mov     ebx, eax
0x1800efd9d  test    eax, eax
0x1800efd9f  jz      short loc_1800EFDA6
0x1800efda1  cmp     eax, 7
0x1800efda4  jnz     short loc_1800EFDDF
0x1800efda6  mov     rax, [rdi]
0x1800efda9  mov     rdx, r12
0x1800efdac  mov     rcx, rdi
0x1800efdaf  mov     rax, [rax+28h]
0x1800efdb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efdb8  mov     ebx, eax
0x1800efdba  test    eax, eax
0x1800efdbc  jz      short loc_1800EFDC3
0x1800efdbe  cmp     eax, 7
0x1800efdc1  jnz     short loc_1800EFDDF
0x1800efdc3  mov     rax, [rdi]
0x1800efdc6  mov     rdx, r12
0x1800efdc9  mov     rcx, rdi
0x1800efdcc  mov     rax, [rax+38h]
0x1800efdd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efdd5  jmp     loc_1800EFCA2
0x1800efdda  mov     ebx, 4
0x1800efddf  mov     rax, [rdi]
0x1800efde2  mov     edx, 1
0x1800efde7  mov     rcx, rdi
0x1800efdea  mov     rax, [rax]
0x1800efded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efdf2  test    r15, r15
0x1800efdf5  jz      short loc_1800EFE04
0x1800efdf7  mov     edx, 10h
0x1800efdfc  mov     rcx, r15; Block
0x1800efdff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800efe04  mov     rcx, [rbp+TokenHandle]; hObject
0x1800efe08  test    rcx, rcx
0x1800efe0b  jz      short loc_1800EFE13
0x1800efe0d  call    cs:__imp_CloseHandle
0x1800efe13  test    r14, r14
0x1800efe16  jz      short loc_1800EFE21
0x1800efe18  mov     rcx, r14; pwk
0x1800efe1b  call    cs:__imp_CloseThreadpoolWork
0x1800efe21  mov     eax, ebx
0x1800efe23  mov     rcx, [rbp+var_8]
0x1800efe27  xor     rcx, rsp; StackCookie
0x1800efe2a  call    __security_check_cookie
0x1800efe2f  mov     rbx, [rsp+80h+arg_18]
0x1800efe37  add     rsp, 80h
0x1800efe3e  pop     r15
0x1800efe40  pop     r14
0x1800efe42  pop     r13
0x1800efe44  pop     r12
0x1800efe46  pop     rdi
0x1800efe47  pop     rsi
0x1800efe48  pop     rbp
0x1800efe49  retn
```
