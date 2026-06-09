# CSpWmiMethod<_SPACES_StorageSubsystem_ClearDiagnosticInfo>::RunMethod<CSpSubsystem::ClearDiagnosticInfo,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006b7d8`
- end: `0x18006bb55`
- name: `??$RunMethod@VClearDiagnosticInfo@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_ClearDiagnosticInfo@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180057100`
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
- `0x18006b7d8`
- `0x18006dfa4`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b9b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b9b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006b98b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006b98b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006b9a6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006b9a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006b96b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006b96b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006ba60`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006ba60`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006bb1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006bb1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bb0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bb0b`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_ClearDiagnosticInfo>::RunMethod<CSpSubsystem::ClearDiagnosticInfo,13>(
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
  CSpSubsystem::ClearDiagnosticInfo *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::ClearDiagnosticInfo *)operator new(0x160u);
  v7 = CSpSubsystem::ClearDiagnosticInfo::ClearDiagnosticInfo(v25);
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
      v25 = (CSpSubsystem::ClearDiagnosticInfo *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_1803162B7,
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
0x18006b7d8  mov     [rsp-38h+arg_18], rbx
0x18006b7dd  push    rbp
0x18006b7de  push    rsi
0x18006b7df  push    rdi
0x18006b7e0  push    r12
0x18006b7e2  push    r13
0x18006b7e4  push    r14
0x18006b7e6  push    r15
0x18006b7e8  mov     rbp, rsp
0x18006b7eb  sub     rsp, 80h
0x18006b7f2  mov     rax, cs:__security_cookie
0x18006b7f9  xor     rax, rsp
0x18006b7fc  mov     [rbp+var_8], rax
0x18006b800  xor     eax, eax
0x18006b802  mov     rsi, rcx
0x18006b805  xorps   xmm0, xmm0
0x18006b808  mov     [rbp+var_10], eax
0x18006b80b  mov     ecx, 160h; Size
0x18006b810  mov     [rbp+var_40], eax
0x18006b813  movups  [rbp+var_20], xmm0
0x18006b817  mov     [rbp+TokenHandle], rax
0x18006b81b  mov     r12, r8
0x18006b81e  mov     r13, rdx
0x18006b821  xor     r14d, r14d
0x18006b824  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b829  mov     rcx, rax; this
0x18006b82c  mov     [rbp+var_28], rax
0x18006b830  call    ??0ClearDiagnosticInfo@CSpSubsystem@@QEAA@XZ; CSpSubsystem::ClearDiagnosticInfo::ClearDiagnosticInfo(void)
0x18006b835  mov     rdi, rax
0x18006b838  test    rax, rax
0x18006b83b  jnz     short loc_18006B845
0x18006b83d  lea     ebx, [rax+1Bh]
0x18006b840  jmp     loc_18006BB02
0x18006b845  mov     rax, [rax]
0x18006b848  mov     rdx, rsi
0x18006b84b  mov     rcx, rdi
0x18006b84e  xor     r15d, r15d
0x18006b851  mov     rax, [rax+8]
0x18006b855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b85a  lea     rcx, [rbp+var_40]
0x18006b85e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006b863  mov     [rdi+1Ch], eax
0x18006b866  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006b86a  mov     ecx, [rsi+14h]; unsigned int
0x18006b86d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006b872  mov     eax, cs:dword_18039EB68
0x18006b878  cmp     eax, 5
0x18006b87b  jbe     short loc_18006B8EB
0x18006b87d  mov     rdx, 400000000000h
0x18006b887  lea     rcx, dword_18039EB68
0x18006b88e  call    _tlgKeywordOn
0x18006b893  test    al, al
0x18006b895  jz      short loc_18006B8EB
0x18006b897  mov     eax, [rbp+var_40]
0x18006b89a  lea     rdx, byte_1803162B7
0x18006b8a1  xor     ecx, ecx
0x18006b8a3  cmp     [rdi+1Ch], eax
0x18006b8a6  movzx   eax, word ptr [rbp+var_10]
0x18006b8aa  mov     word ptr [rbp+var_40], ax
0x18006b8ae  setnz   cl
0x18006b8b1  mov     eax, [rsi+14h]
0x18006b8b4  mov     [rbp+var_38], eax
0x18006b8b7  lea     rax, [rbp+var_20]
0x18006b8bb  mov     [rbp+var_28], rax
0x18006b8bf  lea     rax, [rbp+var_3C]
0x18006b8c3  mov     [rsp+80h+var_48], rax
0x18006b8c8  lea     rax, [rbp+var_40]
0x18006b8cc  mov     [rsp+80h+var_50], rax
0x18006b8d1  lea     rax, [rbp+var_38]
0x18006b8d5  mov     [rsp+80h+var_58], rax
0x18006b8da  lea     rax, [rbp+var_28]
0x18006b8de  mov     [rsp+80h+var_60], rax
0x18006b8e3  mov     [rbp+var_3C], ecx
0x18006b8e6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006b8eb  mov     rcx, [rsi]
0x18006b8ee  test    rcx, rcx
0x18006b8f1  jz      loc_18006BAD8
0x18006b8f7  mov     rax, [rcx]
0x18006b8fa  test    rax, rax
0x18006b8fd  jz      loc_18006BAD8
0x18006b903  mov     rax, [rax+18h]
0x18006b907  lea     r8, [rdi+20h]
0x18006b90b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006b912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b917  mov     ebx, eax
0x18006b919  test    eax, eax
0x18006b91b  jnz     loc_18006BADD
0x18006b921  cmp     [rsi+10h], r14d
0x18006b925  jz      loc_18006BA71
0x18006b92b  lea     rbx, [rdi+148h]
0x18006b932  mov     rcx, rbx
0x18006b935  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006b93a  mov     rcx, rbx; struct CSpJobMgr **
0x18006b93d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006b942  test    eax, eax
0x18006b944  jnz     short loc_18006B94E
0x18006b946  lea     ebx, [rax+1Ch]
0x18006b949  jmp     loc_18006BADD
0x18006b94e  mov     ecx, 10h; Size
0x18006b953  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b958  xor     r8d, r8d; pcbe
0x18006b95b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006b962  mov     rdx, rax; pv
0x18006b965  mov     r15, rax
0x18006b968  mov     [rax], rdi
0x18006b96b  call    cs:__imp_CreateThreadpoolWork
0x18006b972  nop     dword ptr [rax+rax+00h]
0x18006b977  mov     r14, rax
0x18006b97a  test    rax, rax
0x18006b97d  jnz     short loc_18006B98B
0x18006b97f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006b984  mov     ebx, eax
0x18006b986  jmp     loc_18006BADD
0x18006b98b  call    cs:__imp_GetCurrentThread
0x18006b992  nop     dword ptr [rax+rax+00h]
0x18006b997  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006b99b  xor     r8d, r8d; OpenAsSelf
0x18006b99e  mov     rcx, rax; ThreadHandle
0x18006b9a1  mov     edx, 2000Ch; DesiredAccess
0x18006b9a6  call    cs:__imp_OpenThreadToken
0x18006b9ad  nop     dword ptr [rax+rax+00h]
0x18006b9b2  test    eax, eax
0x18006b9b4  jnz     short loc_18006B9C9
0x18006b9b6  call    cs:__imp_GetLastError
0x18006b9bd  nop     dword ptr [rax+rax+00h]
0x18006b9c2  cmp     eax, 3F0h
0x18006b9c7  jnz     short loc_18006B97F
0x18006b9c9  mov     rax, [rbp+TokenHandle]
0x18006b9cd  mov     r8, r13
0x18006b9d0  mov     [r15+8], rax
0x18006b9d4  mov     rcx, rdi
0x18006b9d7  mov     rax, [rdi]
0x18006b9da  mov     rdx, [rsi+8]
0x18006b9de  mov     rax, [rax+18h]
0x18006b9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b9e7  mov     rax, [rdi]
0x18006b9ea  mov     rdx, r12
0x18006b9ed  mov     rcx, rdi
0x18006b9f0  mov     rax, [rax+28h]
0x18006b9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b9f9  mov     ebx, eax
0x18006b9fb  test    eax, eax
0x18006b9fd  jz      short loc_18006BA08
0x18006b9ff  cmp     eax, 7
0x18006ba02  jnz     loc_18006BADD
0x18006ba08  mov     rax, [rdi]
0x18006ba0b  mov     rdx, r12
0x18006ba0e  mov     rcx, rdi
0x18006ba11  mov     rax, [rax+38h]
0x18006ba15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba1a  mov     ebx, eax
0x18006ba1c  test    eax, eax
0x18006ba1e  jnz     loc_18006BADD
0x18006ba24  mov     rax, [rdi+150h]
0x18006ba2b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006ba32  jnz     short loc_18006BA48
0x18006ba34  mov     rax, [rdi+158h]
0x18006ba3b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006ba42  jz      loc_18006BADD
0x18006ba48  mov     rdx, r12
0x18006ba4b  mov     rcx, rdi
0x18006ba4e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006ba53  mov     ebx, eax
0x18006ba55  test    eax, eax
0x18006ba57  jnz     loc_18006BADD
0x18006ba5d  mov     rcx, r14; pwk
0x18006ba60  call    cs:__imp_SubmitThreadpoolWork
0x18006ba67  nop     dword ptr [rax+rax+00h]
0x18006ba6c  jmp     loc_18006BB2B
0x18006ba71  mov     rax, [rdi]
0x18006ba74  mov     r8, r13
0x18006ba77  mov     rdx, [rsi+8]
0x18006ba7b  mov     rcx, rdi
0x18006ba7e  mov     rax, [rax+10h]
0x18006ba82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba87  mov     rax, [rdi]
0x18006ba8a  mov     rdx, r12
0x18006ba8d  mov     rcx, rdi
0x18006ba90  mov     rax, [rax+30h]
0x18006ba94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ba99  mov     ebx, eax
0x18006ba9b  test    eax, eax
0x18006ba9d  jz      short loc_18006BAA4
0x18006ba9f  cmp     eax, 7
0x18006baa2  jnz     short loc_18006BADD
0x18006baa4  mov     rax, [rdi]
0x18006baa7  mov     rdx, r12
0x18006baaa  mov     rcx, rdi
0x18006baad  mov     rax, [rax+28h]
0x18006bab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bab6  mov     ebx, eax
0x18006bab8  test    eax, eax
0x18006baba  jz      short loc_18006BAC1
0x18006babc  cmp     eax, 7
0x18006babf  jnz     short loc_18006BADD
0x18006bac1  mov     rax, [rdi]
0x18006bac4  mov     rdx, r12
0x18006bac7  mov     rcx, rdi
0x18006baca  mov     rax, [rax+38h]
0x18006bace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bad3  jmp     loc_18006B984
0x18006bad8  mov     ebx, 4
0x18006badd  mov     rax, [rdi]
0x18006bae0  mov     edx, 1
0x18006bae5  mov     rcx, rdi
0x18006bae8  mov     rax, [rax]
0x18006baeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006baf0  test    r15, r15
0x18006baf3  jz      short loc_18006BB02
0x18006baf5  mov     edx, 10h
0x18006bafa  mov     rcx, r15; Block
0x18006bafd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006bb02  mov     rcx, [rbp+TokenHandle]; hObject
0x18006bb06  test    rcx, rcx
0x18006bb09  jz      short loc_18006BB17
0x18006bb0b  call    cs:__imp_CloseHandle
0x18006bb12  nop     dword ptr [rax+rax+00h]
0x18006bb17  test    r14, r14
0x18006bb1a  jz      short loc_18006BB2B
0x18006bb1c  mov     rcx, r14; pwk
0x18006bb1f  call    cs:__imp_CloseThreadpoolWork
0x18006bb26  nop     dword ptr [rax+rax+00h]
0x18006bb2b  mov     eax, ebx
0x18006bb2d  mov     rcx, [rbp+var_8]
0x18006bb31  xor     rcx, rsp; StackCookie
0x18006bb34  call    __security_check_cookie
0x18006bb39  mov     rbx, [rsp+80h+arg_18]
0x18006bb41  add     rsp, 80h
0x18006bb48  pop     r15
0x18006bb4a  pop     r14
0x18006bb4c  pop     r13
0x18006bb4e  pop     r12
0x18006bb50  pop     rdi
0x18006bb51  pop     rsi
0x18006bb52  pop     rbp
0x18006bb53  retn
```
