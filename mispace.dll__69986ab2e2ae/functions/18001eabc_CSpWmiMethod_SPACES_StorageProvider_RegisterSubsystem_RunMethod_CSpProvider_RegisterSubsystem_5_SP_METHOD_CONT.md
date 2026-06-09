# CSpWmiMethod<_SPACES_StorageProvider_RegisterSubsystem>::RunMethod<CSpProvider::_RegisterSubsystem,5>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18001eabc`
- end: `0x18001ee39`
- name: `??$RunMethod@V_RegisterSubsystem@CSpProvider@@$04@?$CSpWmiMethod@U_SPACES_StorageProvider_RegisterSubsystem@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180023030`

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
- `0x18001eabc`
- `0x18001f2c8`
- `0x1800257fc`
- `0x18005f41c`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ec6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001ec6f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ec8a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001ec8a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001ec4f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001ec4f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001ed44`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001ed44`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001ee03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001ee03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001edef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001edef`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageProvider_RegisterSubsystem>::RunMethod<CSpProvider::_RegisterSubsystem,5>(
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
  CSpProvider::_RegisterSubsystem *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpProvider::_RegisterSubsystem *)operator new(0x170u);
  v7 = CSpProvider::_RegisterSubsystem::_RegisterSubsystem(v25);
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
      v25 = (CSpProvider::_RegisterSubsystem *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_1802F85D9,
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
0x18001eabc  mov     [rsp-38h+arg_18], rbx
0x18001eac1  push    rbp
0x18001eac2  push    rsi
0x18001eac3  push    rdi
0x18001eac4  push    r12
0x18001eac6  push    r13
0x18001eac8  push    r14
0x18001eaca  push    r15
0x18001eacc  mov     rbp, rsp
0x18001eacf  sub     rsp, 80h
0x18001ead6  mov     rax, cs:__security_cookie
0x18001eadd  xor     rax, rsp
0x18001eae0  mov     [rbp+var_8], rax
0x18001eae4  xor     eax, eax
0x18001eae6  mov     rsi, rcx
0x18001eae9  xorps   xmm0, xmm0
0x18001eaec  mov     [rbp+var_10], eax
0x18001eaef  mov     ecx, 170h; Size
0x18001eaf4  mov     [rbp+var_40], eax
0x18001eaf7  movups  [rbp+var_20], xmm0
0x18001eafb  mov     [rbp+TokenHandle], rax
0x18001eaff  mov     r12, r8
0x18001eb02  mov     r13, rdx
0x18001eb05  xor     r14d, r14d
0x18001eb08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001eb0d  mov     rcx, rax; this
0x18001eb10  mov     [rbp+var_28], rax
0x18001eb14  call    ??0_RegisterSubsystem@CSpProvider@@QEAA@XZ; CSpProvider::_RegisterSubsystem::_RegisterSubsystem(void)
0x18001eb19  mov     rdi, rax
0x18001eb1c  test    rax, rax
0x18001eb1f  jnz     short loc_18001EB29
0x18001eb21  lea     ebx, [rax+1Bh]
0x18001eb24  jmp     loc_18001EDE6
0x18001eb29  mov     rax, [rax]
0x18001eb2c  mov     rdx, rsi
0x18001eb2f  mov     rcx, rdi
0x18001eb32  xor     r15d, r15d
0x18001eb35  mov     rax, [rax+8]
0x18001eb39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb3e  lea     rcx, [rbp+var_40]
0x18001eb42  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18001eb47  mov     [rdi+1Ch], eax
0x18001eb4a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18001eb4e  mov     ecx, [rsi+14h]; unsigned int
0x18001eb51  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18001eb56  mov     eax, cs:dword_18039EB68
0x18001eb5c  cmp     eax, 5
0x18001eb5f  jbe     short loc_18001EBCF
0x18001eb61  mov     rdx, 400000000000h
0x18001eb6b  lea     rcx, dword_18039EB68
0x18001eb72  call    _tlgKeywordOn
0x18001eb77  test    al, al
0x18001eb79  jz      short loc_18001EBCF
0x18001eb7b  mov     eax, [rbp+var_40]
0x18001eb7e  lea     rdx, byte_1802F85D9
0x18001eb85  xor     ecx, ecx
0x18001eb87  cmp     [rdi+1Ch], eax
0x18001eb8a  movzx   eax, word ptr [rbp+var_10]
0x18001eb8e  mov     word ptr [rbp+var_40], ax
0x18001eb92  setnz   cl
0x18001eb95  mov     eax, [rsi+14h]
0x18001eb98  mov     [rbp+var_38], eax
0x18001eb9b  lea     rax, [rbp+var_20]
0x18001eb9f  mov     [rbp+var_28], rax
0x18001eba3  lea     rax, [rbp+var_3C]
0x18001eba7  mov     [rsp+80h+var_48], rax
0x18001ebac  lea     rax, [rbp+var_40]
0x18001ebb0  mov     [rsp+80h+var_50], rax
0x18001ebb5  lea     rax, [rbp+var_38]
0x18001ebb9  mov     [rsp+80h+var_58], rax
0x18001ebbe  lea     rax, [rbp+var_28]
0x18001ebc2  mov     [rsp+80h+var_60], rax
0x18001ebc7  mov     [rbp+var_3C], ecx
0x18001ebca  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18001ebcf  mov     rcx, [rsi]
0x18001ebd2  test    rcx, rcx
0x18001ebd5  jz      loc_18001EDBC
0x18001ebdb  mov     rax, [rcx]
0x18001ebde  test    rax, rax
0x18001ebe1  jz      loc_18001EDBC
0x18001ebe7  mov     rax, [rax+18h]
0x18001ebeb  lea     r8, [rdi+20h]
0x18001ebef  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18001ebf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebfb  mov     ebx, eax
0x18001ebfd  test    eax, eax
0x18001ebff  jnz     loc_18001EDC1
0x18001ec05  cmp     [rsi+10h], r14d
0x18001ec09  jz      loc_18001ED55
0x18001ec0f  lea     rbx, [rdi+148h]
0x18001ec16  mov     rcx, rbx
0x18001ec19  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18001ec1e  mov     rcx, rbx; struct CSpJobMgr **
0x18001ec21  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18001ec26  test    eax, eax
0x18001ec28  jnz     short loc_18001EC32
0x18001ec2a  lea     ebx, [rax+1Ch]
0x18001ec2d  jmp     loc_18001EDC1
0x18001ec32  mov     ecx, 10h; Size
0x18001ec37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ec3c  xor     r8d, r8d; pcbe
0x18001ec3f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001ec46  mov     rdx, rax; pv
0x18001ec49  mov     r15, rax
0x18001ec4c  mov     [rax], rdi
0x18001ec4f  call    cs:__imp_CreateThreadpoolWork
0x18001ec56  nop     dword ptr [rax+rax+00h]
0x18001ec5b  mov     r14, rax
0x18001ec5e  test    rax, rax
0x18001ec61  jnz     short loc_18001EC6F
0x18001ec63  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18001ec68  mov     ebx, eax
0x18001ec6a  jmp     loc_18001EDC1
0x18001ec6f  call    cs:__imp_GetCurrentThread
0x18001ec76  nop     dword ptr [rax+rax+00h]
0x18001ec7b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001ec7f  xor     r8d, r8d; OpenAsSelf
0x18001ec82  mov     rcx, rax; ThreadHandle
0x18001ec85  mov     edx, 2000Ch; DesiredAccess
0x18001ec8a  call    cs:__imp_OpenThreadToken
0x18001ec91  nop     dword ptr [rax+rax+00h]
0x18001ec96  test    eax, eax
0x18001ec98  jnz     short loc_18001ECAD
0x18001ec9a  call    cs:__imp_GetLastError
0x18001eca1  nop     dword ptr [rax+rax+00h]
0x18001eca6  cmp     eax, 3F0h
0x18001ecab  jnz     short loc_18001EC63
0x18001ecad  mov     rax, [rbp+TokenHandle]
0x18001ecb1  mov     r8, r13
0x18001ecb4  mov     [r15+8], rax
0x18001ecb8  mov     rcx, rdi
0x18001ecbb  mov     rax, [rdi]
0x18001ecbe  mov     rdx, [rsi+8]
0x18001ecc2  mov     rax, [rax+18h]
0x18001ecc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eccb  mov     rax, [rdi]
0x18001ecce  mov     rdx, r12
0x18001ecd1  mov     rcx, rdi
0x18001ecd4  mov     rax, [rax+28h]
0x18001ecd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecdd  mov     ebx, eax
0x18001ecdf  test    eax, eax
0x18001ece1  jz      short loc_18001ECEC
0x18001ece3  cmp     eax, 7
0x18001ece6  jnz     loc_18001EDC1
0x18001ecec  mov     rax, [rdi]
0x18001ecef  mov     rdx, r12
0x18001ecf2  mov     rcx, rdi
0x18001ecf5  mov     rax, [rax+38h]
0x18001ecf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecfe  mov     ebx, eax
0x18001ed00  test    eax, eax
0x18001ed02  jnz     loc_18001EDC1
0x18001ed08  mov     rax, [rdi+150h]
0x18001ed0f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18001ed16  jnz     short loc_18001ED2C
0x18001ed18  mov     rax, [rdi+158h]
0x18001ed1f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18001ed26  jz      loc_18001EDC1
0x18001ed2c  mov     rdx, r12
0x18001ed2f  mov     rcx, rdi
0x18001ed32  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18001ed37  mov     ebx, eax
0x18001ed39  test    eax, eax
0x18001ed3b  jnz     loc_18001EDC1
0x18001ed41  mov     rcx, r14; pwk
0x18001ed44  call    cs:__imp_SubmitThreadpoolWork
0x18001ed4b  nop     dword ptr [rax+rax+00h]
0x18001ed50  jmp     loc_18001EE0F
0x18001ed55  mov     rax, [rdi]
0x18001ed58  mov     r8, r13
0x18001ed5b  mov     rdx, [rsi+8]
0x18001ed5f  mov     rcx, rdi
0x18001ed62  mov     rax, [rax+10h]
0x18001ed66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed6b  mov     rax, [rdi]
0x18001ed6e  mov     rdx, r12
0x18001ed71  mov     rcx, rdi
0x18001ed74  mov     rax, [rax+30h]
0x18001ed78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed7d  mov     ebx, eax
0x18001ed7f  test    eax, eax
0x18001ed81  jz      short loc_18001ED88
0x18001ed83  cmp     eax, 7
0x18001ed86  jnz     short loc_18001EDC1
0x18001ed88  mov     rax, [rdi]
0x18001ed8b  mov     rdx, r12
0x18001ed8e  mov     rcx, rdi
0x18001ed91  mov     rax, [rax+28h]
0x18001ed95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed9a  mov     ebx, eax
0x18001ed9c  test    eax, eax
0x18001ed9e  jz      short loc_18001EDA5
0x18001eda0  cmp     eax, 7
0x18001eda3  jnz     short loc_18001EDC1
0x18001eda5  mov     rax, [rdi]
0x18001eda8  mov     rdx, r12
0x18001edab  mov     rcx, rdi
0x18001edae  mov     rax, [rax+38h]
0x18001edb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edb7  jmp     loc_18001EC68
0x18001edbc  mov     ebx, 4
0x18001edc1  mov     rax, [rdi]
0x18001edc4  mov     edx, 1
0x18001edc9  mov     rcx, rdi
0x18001edcc  mov     rax, [rax]
0x18001edcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edd4  test    r15, r15
0x18001edd7  jz      short loc_18001EDE6
0x18001edd9  mov     edx, 10h
0x18001edde  mov     rcx, r15; Block
0x18001ede1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ede6  mov     rcx, [rbp+TokenHandle]; hObject
0x18001edea  test    rcx, rcx
0x18001eded  jz      short loc_18001EDFB
0x18001edef  call    cs:__imp_CloseHandle
0x18001edf6  nop     dword ptr [rax+rax+00h]
0x18001edfb  test    r14, r14
0x18001edfe  jz      short loc_18001EE0F
0x18001ee00  mov     rcx, r14; pwk
0x18001ee03  call    cs:__imp_CloseThreadpoolWork
0x18001ee0a  nop     dword ptr [rax+rax+00h]
0x18001ee0f  mov     eax, ebx
0x18001ee11  mov     rcx, [rbp+var_8]
0x18001ee15  xor     rcx, rsp; StackCookie
0x18001ee18  call    __security_check_cookie
0x18001ee1d  mov     rbx, [rsp+80h+arg_18]
0x18001ee25  add     rsp, 80h
0x18001ee2c  pop     r15
0x18001ee2e  pop     r14
0x18001ee30  pop     r13
0x18001ee32  pop     r12
0x18001ee34  pop     rdi
0x18001ee35  pop     rsi
0x18001ee36  pop     rbp
0x18001ee37  retn
```
