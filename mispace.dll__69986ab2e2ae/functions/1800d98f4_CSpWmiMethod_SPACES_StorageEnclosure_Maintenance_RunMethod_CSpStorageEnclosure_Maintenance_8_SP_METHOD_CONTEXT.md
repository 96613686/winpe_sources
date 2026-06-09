# CSpWmiMethod<_SPACES_StorageEnclosure_Maintenance>::RunMethod<CSpStorageEnclosure::Maintenance,8>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800d98f4`
- end: `0x1800d9c71`
- name: `??$RunMethod@VMaintenance@CSpStorageEnclosure@@$07@?$CSpWmiMethod@U_SPACES_StorageEnclosure_Maintenance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800d98f4`
- `0x1800da4e0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9ad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9ad2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d9aa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d9aa7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d9ac2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d9ac2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d9a87`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d9a87`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d9b7c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d9b7c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d9c3b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d9c3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d9c27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d9c27`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageEnclosure_Maintenance>::RunMethod<CSpStorageEnclosure::Maintenance,8>(
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
  CSpStorageEnclosure::Maintenance *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageEnclosure::Maintenance *)operator new(0x180u);
  v7 = CSpStorageEnclosure::Maintenance::Maintenance(v25);
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
      v25 = (CSpStorageEnclosure::Maintenance *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_1803364F4,
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
0x1800d98f4  mov     [rsp-38h+arg_18], rbx
0x1800d98f9  push    rbp
0x1800d98fa  push    rsi
0x1800d98fb  push    rdi
0x1800d98fc  push    r12
0x1800d98fe  push    r13
0x1800d9900  push    r14
0x1800d9902  push    r15
0x1800d9904  mov     rbp, rsp
0x1800d9907  sub     rsp, 80h
0x1800d990e  mov     rax, cs:__security_cookie
0x1800d9915  xor     rax, rsp
0x1800d9918  mov     [rbp+var_8], rax
0x1800d991c  xor     eax, eax
0x1800d991e  mov     rsi, rcx
0x1800d9921  xorps   xmm0, xmm0
0x1800d9924  mov     [rbp+var_10], eax
0x1800d9927  mov     ecx, 180h; Size
0x1800d992c  mov     [rbp+var_40], eax
0x1800d992f  movups  [rbp+var_20], xmm0
0x1800d9933  mov     [rbp+TokenHandle], rax
0x1800d9937  mov     r12, r8
0x1800d993a  mov     r13, rdx
0x1800d993d  xor     r14d, r14d
0x1800d9940  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d9945  mov     rcx, rax; this
0x1800d9948  mov     [rbp+var_28], rax
0x1800d994c  call    ??0Maintenance@CSpStorageEnclosure@@QEAA@XZ; CSpStorageEnclosure::Maintenance::Maintenance(void)
0x1800d9951  mov     rdi, rax
0x1800d9954  test    rax, rax
0x1800d9957  jnz     short loc_1800D9961
0x1800d9959  lea     ebx, [rax+1Bh]
0x1800d995c  jmp     loc_1800D9C1E
0x1800d9961  mov     rax, [rax]
0x1800d9964  mov     rdx, rsi
0x1800d9967  mov     rcx, rdi
0x1800d996a  xor     r15d, r15d
0x1800d996d  mov     rax, [rax+8]
0x1800d9971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9976  lea     rcx, [rbp+var_40]
0x1800d997a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800d997f  mov     [rdi+1Ch], eax
0x1800d9982  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800d9986  mov     ecx, [rsi+14h]; unsigned int
0x1800d9989  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800d998e  mov     eax, cs:dword_18039EB68
0x1800d9994  cmp     eax, 5
0x1800d9997  jbe     short loc_1800D9A07
0x1800d9999  mov     rdx, 400000000000h
0x1800d99a3  lea     rcx, dword_18039EB68
0x1800d99aa  call    _tlgKeywordOn
0x1800d99af  test    al, al
0x1800d99b1  jz      short loc_1800D9A07
0x1800d99b3  mov     eax, [rbp+var_40]
0x1800d99b6  lea     rdx, dword_1803364F4
0x1800d99bd  xor     ecx, ecx
0x1800d99bf  cmp     [rdi+1Ch], eax
0x1800d99c2  movzx   eax, word ptr [rbp+var_10]
0x1800d99c6  mov     word ptr [rbp+var_40], ax
0x1800d99ca  setnz   cl
0x1800d99cd  mov     eax, [rsi+14h]
0x1800d99d0  mov     [rbp+var_38], eax
0x1800d99d3  lea     rax, [rbp+var_20]
0x1800d99d7  mov     [rbp+var_28], rax
0x1800d99db  lea     rax, [rbp+var_3C]
0x1800d99df  mov     [rsp+80h+var_48], rax
0x1800d99e4  lea     rax, [rbp+var_40]
0x1800d99e8  mov     [rsp+80h+var_50], rax
0x1800d99ed  lea     rax, [rbp+var_38]
0x1800d99f1  mov     [rsp+80h+var_58], rax
0x1800d99f6  lea     rax, [rbp+var_28]
0x1800d99fa  mov     [rsp+80h+var_60], rax
0x1800d99ff  mov     [rbp+var_3C], ecx
0x1800d9a02  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800d9a07  mov     rcx, [rsi]
0x1800d9a0a  test    rcx, rcx
0x1800d9a0d  jz      loc_1800D9BF4
0x1800d9a13  mov     rax, [rcx]
0x1800d9a16  test    rax, rax
0x1800d9a19  jz      loc_1800D9BF4
0x1800d9a1f  mov     rax, [rax+18h]
0x1800d9a23  lea     r8, [rdi+20h]
0x1800d9a27  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800d9a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9a33  mov     ebx, eax
0x1800d9a35  test    eax, eax
0x1800d9a37  jnz     loc_1800D9BF9
0x1800d9a3d  cmp     [rsi+10h], r14d
0x1800d9a41  jz      loc_1800D9B8D
0x1800d9a47  lea     rbx, [rdi+148h]
0x1800d9a4e  mov     rcx, rbx
0x1800d9a51  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800d9a56  mov     rcx, rbx; struct CSpJobMgr **
0x1800d9a59  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800d9a5e  test    eax, eax
0x1800d9a60  jnz     short loc_1800D9A6A
0x1800d9a62  lea     ebx, [rax+1Ch]
0x1800d9a65  jmp     loc_1800D9BF9
0x1800d9a6a  mov     ecx, 10h; Size
0x1800d9a6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d9a74  xor     r8d, r8d; pcbe
0x1800d9a77  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800d9a7e  mov     rdx, rax; pv
0x1800d9a81  mov     r15, rax
0x1800d9a84  mov     [rax], rdi
0x1800d9a87  call    cs:__imp_CreateThreadpoolWork
0x1800d9a8e  nop     dword ptr [rax+rax+00h]
0x1800d9a93  mov     r14, rax
0x1800d9a96  test    rax, rax
0x1800d9a99  jnz     short loc_1800D9AA7
0x1800d9a9b  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800d9aa0  mov     ebx, eax
0x1800d9aa2  jmp     loc_1800D9BF9
0x1800d9aa7  call    cs:__imp_GetCurrentThread
0x1800d9aae  nop     dword ptr [rax+rax+00h]
0x1800d9ab3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d9ab7  xor     r8d, r8d; OpenAsSelf
0x1800d9aba  mov     rcx, rax; ThreadHandle
0x1800d9abd  mov     edx, 2000Ch; DesiredAccess
0x1800d9ac2  call    cs:__imp_OpenThreadToken
0x1800d9ac9  nop     dword ptr [rax+rax+00h]
0x1800d9ace  test    eax, eax
0x1800d9ad0  jnz     short loc_1800D9AE5
0x1800d9ad2  call    cs:__imp_GetLastError
0x1800d9ad9  nop     dword ptr [rax+rax+00h]
0x1800d9ade  cmp     eax, 3F0h
0x1800d9ae3  jnz     short loc_1800D9A9B
0x1800d9ae5  mov     rax, [rbp+TokenHandle]
0x1800d9ae9  mov     r8, r13
0x1800d9aec  mov     [r15+8], rax
0x1800d9af0  mov     rcx, rdi
0x1800d9af3  mov     rax, [rdi]
0x1800d9af6  mov     rdx, [rsi+8]
0x1800d9afa  mov     rax, [rax+18h]
0x1800d9afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9b03  mov     rax, [rdi]
0x1800d9b06  mov     rdx, r12
0x1800d9b09  mov     rcx, rdi
0x1800d9b0c  mov     rax, [rax+28h]
0x1800d9b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9b15  mov     ebx, eax
0x1800d9b17  test    eax, eax
0x1800d9b19  jz      short loc_1800D9B24
0x1800d9b1b  cmp     eax, 7
0x1800d9b1e  jnz     loc_1800D9BF9
0x1800d9b24  mov     rax, [rdi]
0x1800d9b27  mov     rdx, r12
0x1800d9b2a  mov     rcx, rdi
0x1800d9b2d  mov     rax, [rax+38h]
0x1800d9b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9b36  mov     ebx, eax
0x1800d9b38  test    eax, eax
0x1800d9b3a  jnz     loc_1800D9BF9
0x1800d9b40  mov     rax, [rdi+150h]
0x1800d9b47  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800d9b4e  jnz     short loc_1800D9B64
0x1800d9b50  mov     rax, [rdi+158h]
0x1800d9b57  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800d9b5e  jz      loc_1800D9BF9
0x1800d9b64  mov     rdx, r12
0x1800d9b67  mov     rcx, rdi
0x1800d9b6a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800d9b6f  mov     ebx, eax
0x1800d9b71  test    eax, eax
0x1800d9b73  jnz     loc_1800D9BF9
0x1800d9b79  mov     rcx, r14; pwk
0x1800d9b7c  call    cs:__imp_SubmitThreadpoolWork
0x1800d9b83  nop     dword ptr [rax+rax+00h]
0x1800d9b88  jmp     loc_1800D9C47
0x1800d9b8d  mov     rax, [rdi]
0x1800d9b90  mov     r8, r13
0x1800d9b93  mov     rdx, [rsi+8]
0x1800d9b97  mov     rcx, rdi
0x1800d9b9a  mov     rax, [rax+10h]
0x1800d9b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9ba3  mov     rax, [rdi]
0x1800d9ba6  mov     rdx, r12
0x1800d9ba9  mov     rcx, rdi
0x1800d9bac  mov     rax, [rax+30h]
0x1800d9bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9bb5  mov     ebx, eax
0x1800d9bb7  test    eax, eax
0x1800d9bb9  jz      short loc_1800D9BC0
0x1800d9bbb  cmp     eax, 7
0x1800d9bbe  jnz     short loc_1800D9BF9
0x1800d9bc0  mov     rax, [rdi]
0x1800d9bc3  mov     rdx, r12
0x1800d9bc6  mov     rcx, rdi
0x1800d9bc9  mov     rax, [rax+28h]
0x1800d9bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9bd2  mov     ebx, eax
0x1800d9bd4  test    eax, eax
0x1800d9bd6  jz      short loc_1800D9BDD
0x1800d9bd8  cmp     eax, 7
0x1800d9bdb  jnz     short loc_1800D9BF9
0x1800d9bdd  mov     rax, [rdi]
0x1800d9be0  mov     rdx, r12
0x1800d9be3  mov     rcx, rdi
0x1800d9be6  mov     rax, [rax+38h]
0x1800d9bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9bef  jmp     loc_1800D9AA0
0x1800d9bf4  mov     ebx, 4
0x1800d9bf9  mov     rax, [rdi]
0x1800d9bfc  mov     edx, 1
0x1800d9c01  mov     rcx, rdi
0x1800d9c04  mov     rax, [rax]
0x1800d9c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9c0c  test    r15, r15
0x1800d9c0f  jz      short loc_1800D9C1E
0x1800d9c11  mov     edx, 10h
0x1800d9c16  mov     rcx, r15; Block
0x1800d9c19  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d9c1e  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d9c22  test    rcx, rcx
0x1800d9c25  jz      short loc_1800D9C33
0x1800d9c27  call    cs:__imp_CloseHandle
0x1800d9c2e  nop     dword ptr [rax+rax+00h]
0x1800d9c33  test    r14, r14
0x1800d9c36  jz      short loc_1800D9C47
0x1800d9c38  mov     rcx, r14; pwk
0x1800d9c3b  call    cs:__imp_CloseThreadpoolWork
0x1800d9c42  nop     dword ptr [rax+rax+00h]
0x1800d9c47  mov     eax, ebx
0x1800d9c49  mov     rcx, [rbp+var_8]
0x1800d9c4d  xor     rcx, rsp; StackCookie
0x1800d9c50  call    __security_check_cookie
0x1800d9c55  mov     rbx, [rsp+80h+arg_18]
0x1800d9c5d  add     rsp, 80h
0x1800d9c64  pop     r15
0x1800d9c66  pop     r14
0x1800d9c68  pop     r13
0x1800d9c6a  pop     r12
0x1800d9c6c  pop     rdi
0x1800d9c6d  pop     rsi
0x1800d9c6e  pop     rbp
0x1800d9c6f  retn
```
