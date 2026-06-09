# CSpWmiMethod<_SPACES_StorageSubsystem_CreateReplicationGroup>::RunMethod<CSpSubsystem::CreateReplicationGroup,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006bee0`
- end: `0x18006c25d`
- name: `??$RunMethod@VCreateReplicationGroup@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_CreateReplicationGroup@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800743e0`

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
- `0x18006bee0`
- `0x18006e0a4`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c0be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c0be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006c093`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006c093`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006c0ae`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006c0ae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006c073`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006c073`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006c168`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006c168`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006c227`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006c227`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c213`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c213`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_CreateReplicationGroup>::RunMethod<CSpSubsystem::CreateReplicationGroup,13>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 ReplicationGroup; // rax
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
  CSpSubsystem::CreateReplicationGroup *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::CreateReplicationGroup *)operator new(0x180u);
  ReplicationGroup = CSpSubsystem::CreateReplicationGroup::CreateReplicationGroup(v25);
  v8 = ReplicationGroup;
  if ( ReplicationGroup )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)ReplicationGroup + 8LL))(ReplicationGroup, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpSubsystem::CreateReplicationGroup *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_180315A16,
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
0x18006bee0  mov     [rsp-38h+arg_18], rbx
0x18006bee5  push    rbp
0x18006bee6  push    rsi
0x18006bee7  push    rdi
0x18006bee8  push    r12
0x18006beea  push    r13
0x18006beec  push    r14
0x18006beee  push    r15
0x18006bef0  mov     rbp, rsp
0x18006bef3  sub     rsp, 80h
0x18006befa  mov     rax, cs:__security_cookie
0x18006bf01  xor     rax, rsp
0x18006bf04  mov     [rbp+var_8], rax
0x18006bf08  xor     eax, eax
0x18006bf0a  mov     rsi, rcx
0x18006bf0d  xorps   xmm0, xmm0
0x18006bf10  mov     [rbp+var_10], eax
0x18006bf13  mov     ecx, 180h; Size
0x18006bf18  mov     [rbp+var_40], eax
0x18006bf1b  movups  [rbp+var_20], xmm0
0x18006bf1f  mov     [rbp+TokenHandle], rax
0x18006bf23  mov     r12, r8
0x18006bf26  mov     r13, rdx
0x18006bf29  xor     r14d, r14d
0x18006bf2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006bf31  mov     rcx, rax; this
0x18006bf34  mov     [rbp+var_28], rax
0x18006bf38  call    ??0CreateReplicationGroup@CSpSubsystem@@QEAA@XZ; CSpSubsystem::CreateReplicationGroup::CreateReplicationGroup(void)
0x18006bf3d  mov     rdi, rax
0x18006bf40  test    rax, rax
0x18006bf43  jnz     short loc_18006BF4D
0x18006bf45  lea     ebx, [rax+1Bh]
0x18006bf48  jmp     loc_18006C20A
0x18006bf4d  mov     rax, [rax]
0x18006bf50  mov     rdx, rsi
0x18006bf53  mov     rcx, rdi
0x18006bf56  xor     r15d, r15d
0x18006bf59  mov     rax, [rax+8]
0x18006bf5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bf62  lea     rcx, [rbp+var_40]
0x18006bf66  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006bf6b  mov     [rdi+1Ch], eax
0x18006bf6e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006bf72  mov     ecx, [rsi+14h]; unsigned int
0x18006bf75  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006bf7a  mov     eax, cs:dword_18039EB68
0x18006bf80  cmp     eax, 5
0x18006bf83  jbe     short loc_18006BFF3
0x18006bf85  mov     rdx, 400000000000h
0x18006bf8f  lea     rcx, dword_18039EB68
0x18006bf96  call    _tlgKeywordOn
0x18006bf9b  test    al, al
0x18006bf9d  jz      short loc_18006BFF3
0x18006bf9f  mov     eax, [rbp+var_40]
0x18006bfa2  lea     rdx, word_180315A16
0x18006bfa9  xor     ecx, ecx
0x18006bfab  cmp     [rdi+1Ch], eax
0x18006bfae  movzx   eax, word ptr [rbp+var_10]
0x18006bfb2  mov     word ptr [rbp+var_40], ax
0x18006bfb6  setnz   cl
0x18006bfb9  mov     eax, [rsi+14h]
0x18006bfbc  mov     [rbp+var_38], eax
0x18006bfbf  lea     rax, [rbp+var_20]
0x18006bfc3  mov     [rbp+var_28], rax
0x18006bfc7  lea     rax, [rbp+var_3C]
0x18006bfcb  mov     [rsp+80h+var_48], rax
0x18006bfd0  lea     rax, [rbp+var_40]
0x18006bfd4  mov     [rsp+80h+var_50], rax
0x18006bfd9  lea     rax, [rbp+var_38]
0x18006bfdd  mov     [rsp+80h+var_58], rax
0x18006bfe2  lea     rax, [rbp+var_28]
0x18006bfe6  mov     [rsp+80h+var_60], rax
0x18006bfeb  mov     [rbp+var_3C], ecx
0x18006bfee  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006bff3  mov     rcx, [rsi]
0x18006bff6  test    rcx, rcx
0x18006bff9  jz      loc_18006C1E0
0x18006bfff  mov     rax, [rcx]
0x18006c002  test    rax, rax
0x18006c005  jz      loc_18006C1E0
0x18006c00b  mov     rax, [rax+18h]
0x18006c00f  lea     r8, [rdi+20h]
0x18006c013  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006c01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c01f  mov     ebx, eax
0x18006c021  test    eax, eax
0x18006c023  jnz     loc_18006C1E5
0x18006c029  cmp     [rsi+10h], r14d
0x18006c02d  jz      loc_18006C179
0x18006c033  lea     rbx, [rdi+148h]
0x18006c03a  mov     rcx, rbx
0x18006c03d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006c042  mov     rcx, rbx; struct CSpJobMgr **
0x18006c045  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006c04a  test    eax, eax
0x18006c04c  jnz     short loc_18006C056
0x18006c04e  lea     ebx, [rax+1Ch]
0x18006c051  jmp     loc_18006C1E5
0x18006c056  mov     ecx, 10h; Size
0x18006c05b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006c060  xor     r8d, r8d; pcbe
0x18006c063  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006c06a  mov     rdx, rax; pv
0x18006c06d  mov     r15, rax
0x18006c070  mov     [rax], rdi
0x18006c073  call    cs:__imp_CreateThreadpoolWork
0x18006c07a  nop     dword ptr [rax+rax+00h]
0x18006c07f  mov     r14, rax
0x18006c082  test    rax, rax
0x18006c085  jnz     short loc_18006C093
0x18006c087  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006c08c  mov     ebx, eax
0x18006c08e  jmp     loc_18006C1E5
0x18006c093  call    cs:__imp_GetCurrentThread
0x18006c09a  nop     dword ptr [rax+rax+00h]
0x18006c09f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006c0a3  xor     r8d, r8d; OpenAsSelf
0x18006c0a6  mov     rcx, rax; ThreadHandle
0x18006c0a9  mov     edx, 2000Ch; DesiredAccess
0x18006c0ae  call    cs:__imp_OpenThreadToken
0x18006c0b5  nop     dword ptr [rax+rax+00h]
0x18006c0ba  test    eax, eax
0x18006c0bc  jnz     short loc_18006C0D1
0x18006c0be  call    cs:__imp_GetLastError
0x18006c0c5  nop     dword ptr [rax+rax+00h]
0x18006c0ca  cmp     eax, 3F0h
0x18006c0cf  jnz     short loc_18006C087
0x18006c0d1  mov     rax, [rbp+TokenHandle]
0x18006c0d5  mov     r8, r13
0x18006c0d8  mov     [r15+8], rax
0x18006c0dc  mov     rcx, rdi
0x18006c0df  mov     rax, [rdi]
0x18006c0e2  mov     rdx, [rsi+8]
0x18006c0e6  mov     rax, [rax+18h]
0x18006c0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c0ef  mov     rax, [rdi]
0x18006c0f2  mov     rdx, r12
0x18006c0f5  mov     rcx, rdi
0x18006c0f8  mov     rax, [rax+28h]
0x18006c0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c101  mov     ebx, eax
0x18006c103  test    eax, eax
0x18006c105  jz      short loc_18006C110
0x18006c107  cmp     eax, 7
0x18006c10a  jnz     loc_18006C1E5
0x18006c110  mov     rax, [rdi]
0x18006c113  mov     rdx, r12
0x18006c116  mov     rcx, rdi
0x18006c119  mov     rax, [rax+38h]
0x18006c11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c122  mov     ebx, eax
0x18006c124  test    eax, eax
0x18006c126  jnz     loc_18006C1E5
0x18006c12c  mov     rax, [rdi+150h]
0x18006c133  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006c13a  jnz     short loc_18006C150
0x18006c13c  mov     rax, [rdi+158h]
0x18006c143  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006c14a  jz      loc_18006C1E5
0x18006c150  mov     rdx, r12
0x18006c153  mov     rcx, rdi
0x18006c156  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006c15b  mov     ebx, eax
0x18006c15d  test    eax, eax
0x18006c15f  jnz     loc_18006C1E5
0x18006c165  mov     rcx, r14; pwk
0x18006c168  call    cs:__imp_SubmitThreadpoolWork
0x18006c16f  nop     dword ptr [rax+rax+00h]
0x18006c174  jmp     loc_18006C233
0x18006c179  mov     rax, [rdi]
0x18006c17c  mov     r8, r13
0x18006c17f  mov     rdx, [rsi+8]
0x18006c183  mov     rcx, rdi
0x18006c186  mov     rax, [rax+10h]
0x18006c18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c18f  mov     rax, [rdi]
0x18006c192  mov     rdx, r12
0x18006c195  mov     rcx, rdi
0x18006c198  mov     rax, [rax+30h]
0x18006c19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c1a1  mov     ebx, eax
0x18006c1a3  test    eax, eax
0x18006c1a5  jz      short loc_18006C1AC
0x18006c1a7  cmp     eax, 7
0x18006c1aa  jnz     short loc_18006C1E5
0x18006c1ac  mov     rax, [rdi]
0x18006c1af  mov     rdx, r12
0x18006c1b2  mov     rcx, rdi
0x18006c1b5  mov     rax, [rax+28h]
0x18006c1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c1be  mov     ebx, eax
0x18006c1c0  test    eax, eax
0x18006c1c2  jz      short loc_18006C1C9
0x18006c1c4  cmp     eax, 7
0x18006c1c7  jnz     short loc_18006C1E5
0x18006c1c9  mov     rax, [rdi]
0x18006c1cc  mov     rdx, r12
0x18006c1cf  mov     rcx, rdi
0x18006c1d2  mov     rax, [rax+38h]
0x18006c1d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c1db  jmp     loc_18006C08C
0x18006c1e0  mov     ebx, 4
0x18006c1e5  mov     rax, [rdi]
0x18006c1e8  mov     edx, 1
0x18006c1ed  mov     rcx, rdi
0x18006c1f0  mov     rax, [rax]
0x18006c1f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c1f8  test    r15, r15
0x18006c1fb  jz      short loc_18006C20A
0x18006c1fd  mov     edx, 10h
0x18006c202  mov     rcx, r15; Block
0x18006c205  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006c20a  mov     rcx, [rbp+TokenHandle]; hObject
0x18006c20e  test    rcx, rcx
0x18006c211  jz      short loc_18006C21F
0x18006c213  call    cs:__imp_CloseHandle
0x18006c21a  nop     dword ptr [rax+rax+00h]
0x18006c21f  test    r14, r14
0x18006c222  jz      short loc_18006C233
0x18006c224  mov     rcx, r14; pwk
0x18006c227  call    cs:__imp_CloseThreadpoolWork
0x18006c22e  nop     dword ptr [rax+rax+00h]
0x18006c233  mov     eax, ebx
0x18006c235  mov     rcx, [rbp+var_8]
0x18006c239  xor     rcx, rsp; StackCookie
0x18006c23c  call    __security_check_cookie
0x18006c241  mov     rbx, [rsp+80h+arg_18]
0x18006c249  add     rsp, 80h
0x18006c250  pop     r15
0x18006c252  pop     r14
0x18006c254  pop     r13
0x18006c256  pop     r12
0x18006c258  pop     rdi
0x18006c259  pop     rsi
0x18006c25a  pop     rbp
0x18006c25b  retn
```
