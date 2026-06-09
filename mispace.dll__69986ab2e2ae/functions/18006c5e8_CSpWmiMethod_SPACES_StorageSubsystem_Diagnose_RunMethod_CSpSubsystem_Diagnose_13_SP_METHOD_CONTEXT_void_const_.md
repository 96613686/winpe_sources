# CSpWmiMethod<_SPACES_StorageSubsystem_Diagnose>::RunMethod<CSpSubsystem::Diagnose,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006c5e8`
- end: `0x18006c965`
- name: `??$RunMethod@VDiagnose@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_Diagnose@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x18006c5e8`
- `0x18006e238`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c7c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c7c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006c79b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006c79b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006c7b6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006c7b6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006c77b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006c77b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006c870`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006c870`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006c92f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006c92f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c91b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c91b`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_Diagnose>::RunMethod<CSpSubsystem::Diagnose,13>(
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
  CSpSubsystem::Diagnose *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::Diagnose *)operator new(0x168u);
  v7 = CSpSubsystem::Diagnose::Diagnose(v25);
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
      v25 = (CSpSubsystem::Diagnose *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_180318200,
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
0x18006c5e8  mov     [rsp-38h+arg_18], rbx
0x18006c5ed  push    rbp
0x18006c5ee  push    rsi
0x18006c5ef  push    rdi
0x18006c5f0  push    r12
0x18006c5f2  push    r13
0x18006c5f4  push    r14
0x18006c5f6  push    r15
0x18006c5f8  mov     rbp, rsp
0x18006c5fb  sub     rsp, 80h
0x18006c602  mov     rax, cs:__security_cookie
0x18006c609  xor     rax, rsp
0x18006c60c  mov     [rbp+var_8], rax
0x18006c610  xor     eax, eax
0x18006c612  mov     rsi, rcx
0x18006c615  xorps   xmm0, xmm0
0x18006c618  mov     [rbp+var_10], eax
0x18006c61b  mov     ecx, 168h; Size
0x18006c620  mov     [rbp+var_40], eax
0x18006c623  movups  [rbp+var_20], xmm0
0x18006c627  mov     [rbp+TokenHandle], rax
0x18006c62b  mov     r12, r8
0x18006c62e  mov     r13, rdx
0x18006c631  xor     r14d, r14d
0x18006c634  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006c639  mov     rcx, rax; this
0x18006c63c  mov     [rbp+var_28], rax
0x18006c640  call    ??0Diagnose@CSpSubsystem@@QEAA@XZ; CSpSubsystem::Diagnose::Diagnose(void)
0x18006c645  mov     rdi, rax
0x18006c648  test    rax, rax
0x18006c64b  jnz     short loc_18006C655
0x18006c64d  lea     ebx, [rax+1Bh]
0x18006c650  jmp     loc_18006C912
0x18006c655  mov     rax, [rax]
0x18006c658  mov     rdx, rsi
0x18006c65b  mov     rcx, rdi
0x18006c65e  xor     r15d, r15d
0x18006c661  mov     rax, [rax+8]
0x18006c665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c66a  lea     rcx, [rbp+var_40]
0x18006c66e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006c673  mov     [rdi+1Ch], eax
0x18006c676  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006c67a  mov     ecx, [rsi+14h]; unsigned int
0x18006c67d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006c682  mov     eax, cs:dword_18039EB68
0x18006c688  cmp     eax, 5
0x18006c68b  jbe     short loc_18006C6FB
0x18006c68d  mov     rdx, 400000000000h
0x18006c697  lea     rcx, dword_18039EB68
0x18006c69e  call    _tlgKeywordOn
0x18006c6a3  test    al, al
0x18006c6a5  jz      short loc_18006C6FB
0x18006c6a7  mov     eax, [rbp+var_40]
0x18006c6aa  lea     rdx, unk_180318200
0x18006c6b1  xor     ecx, ecx
0x18006c6b3  cmp     [rdi+1Ch], eax
0x18006c6b6  movzx   eax, word ptr [rbp+var_10]
0x18006c6ba  mov     word ptr [rbp+var_40], ax
0x18006c6be  setnz   cl
0x18006c6c1  mov     eax, [rsi+14h]
0x18006c6c4  mov     [rbp+var_38], eax
0x18006c6c7  lea     rax, [rbp+var_20]
0x18006c6cb  mov     [rbp+var_28], rax
0x18006c6cf  lea     rax, [rbp+var_3C]
0x18006c6d3  mov     [rsp+80h+var_48], rax
0x18006c6d8  lea     rax, [rbp+var_40]
0x18006c6dc  mov     [rsp+80h+var_50], rax
0x18006c6e1  lea     rax, [rbp+var_38]
0x18006c6e5  mov     [rsp+80h+var_58], rax
0x18006c6ea  lea     rax, [rbp+var_28]
0x18006c6ee  mov     [rsp+80h+var_60], rax
0x18006c6f3  mov     [rbp+var_3C], ecx
0x18006c6f6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006c6fb  mov     rcx, [rsi]
0x18006c6fe  test    rcx, rcx
0x18006c701  jz      loc_18006C8E8
0x18006c707  mov     rax, [rcx]
0x18006c70a  test    rax, rax
0x18006c70d  jz      loc_18006C8E8
0x18006c713  mov     rax, [rax+18h]
0x18006c717  lea     r8, [rdi+20h]
0x18006c71b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006c722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c727  mov     ebx, eax
0x18006c729  test    eax, eax
0x18006c72b  jnz     loc_18006C8ED
0x18006c731  cmp     [rsi+10h], r14d
0x18006c735  jz      loc_18006C881
0x18006c73b  lea     rbx, [rdi+148h]
0x18006c742  mov     rcx, rbx
0x18006c745  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006c74a  mov     rcx, rbx; struct CSpJobMgr **
0x18006c74d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006c752  test    eax, eax
0x18006c754  jnz     short loc_18006C75E
0x18006c756  lea     ebx, [rax+1Ch]
0x18006c759  jmp     loc_18006C8ED
0x18006c75e  mov     ecx, 10h; Size
0x18006c763  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006c768  xor     r8d, r8d; pcbe
0x18006c76b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006c772  mov     rdx, rax; pv
0x18006c775  mov     r15, rax
0x18006c778  mov     [rax], rdi
0x18006c77b  call    cs:__imp_CreateThreadpoolWork
0x18006c782  nop     dword ptr [rax+rax+00h]
0x18006c787  mov     r14, rax
0x18006c78a  test    rax, rax
0x18006c78d  jnz     short loc_18006C79B
0x18006c78f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006c794  mov     ebx, eax
0x18006c796  jmp     loc_18006C8ED
0x18006c79b  call    cs:__imp_GetCurrentThread
0x18006c7a2  nop     dword ptr [rax+rax+00h]
0x18006c7a7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006c7ab  xor     r8d, r8d; OpenAsSelf
0x18006c7ae  mov     rcx, rax; ThreadHandle
0x18006c7b1  mov     edx, 2000Ch; DesiredAccess
0x18006c7b6  call    cs:__imp_OpenThreadToken
0x18006c7bd  nop     dword ptr [rax+rax+00h]
0x18006c7c2  test    eax, eax
0x18006c7c4  jnz     short loc_18006C7D9
0x18006c7c6  call    cs:__imp_GetLastError
0x18006c7cd  nop     dword ptr [rax+rax+00h]
0x18006c7d2  cmp     eax, 3F0h
0x18006c7d7  jnz     short loc_18006C78F
0x18006c7d9  mov     rax, [rbp+TokenHandle]
0x18006c7dd  mov     r8, r13
0x18006c7e0  mov     [r15+8], rax
0x18006c7e4  mov     rcx, rdi
0x18006c7e7  mov     rax, [rdi]
0x18006c7ea  mov     rdx, [rsi+8]
0x18006c7ee  mov     rax, [rax+18h]
0x18006c7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7f7  mov     rax, [rdi]
0x18006c7fa  mov     rdx, r12
0x18006c7fd  mov     rcx, rdi
0x18006c800  mov     rax, [rax+28h]
0x18006c804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c809  mov     ebx, eax
0x18006c80b  test    eax, eax
0x18006c80d  jz      short loc_18006C818
0x18006c80f  cmp     eax, 7
0x18006c812  jnz     loc_18006C8ED
0x18006c818  mov     rax, [rdi]
0x18006c81b  mov     rdx, r12
0x18006c81e  mov     rcx, rdi
0x18006c821  mov     rax, [rax+38h]
0x18006c825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c82a  mov     ebx, eax
0x18006c82c  test    eax, eax
0x18006c82e  jnz     loc_18006C8ED
0x18006c834  mov     rax, [rdi+150h]
0x18006c83b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006c842  jnz     short loc_18006C858
0x18006c844  mov     rax, [rdi+158h]
0x18006c84b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006c852  jz      loc_18006C8ED
0x18006c858  mov     rdx, r12
0x18006c85b  mov     rcx, rdi
0x18006c85e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006c863  mov     ebx, eax
0x18006c865  test    eax, eax
0x18006c867  jnz     loc_18006C8ED
0x18006c86d  mov     rcx, r14; pwk
0x18006c870  call    cs:__imp_SubmitThreadpoolWork
0x18006c877  nop     dword ptr [rax+rax+00h]
0x18006c87c  jmp     loc_18006C93B
0x18006c881  mov     rax, [rdi]
0x18006c884  mov     r8, r13
0x18006c887  mov     rdx, [rsi+8]
0x18006c88b  mov     rcx, rdi
0x18006c88e  mov     rax, [rax+10h]
0x18006c892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c897  mov     rax, [rdi]
0x18006c89a  mov     rdx, r12
0x18006c89d  mov     rcx, rdi
0x18006c8a0  mov     rax, [rax+30h]
0x18006c8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c8a9  mov     ebx, eax
0x18006c8ab  test    eax, eax
0x18006c8ad  jz      short loc_18006C8B4
0x18006c8af  cmp     eax, 7
0x18006c8b2  jnz     short loc_18006C8ED
0x18006c8b4  mov     rax, [rdi]
0x18006c8b7  mov     rdx, r12
0x18006c8ba  mov     rcx, rdi
0x18006c8bd  mov     rax, [rax+28h]
0x18006c8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c8c6  mov     ebx, eax
0x18006c8c8  test    eax, eax
0x18006c8ca  jz      short loc_18006C8D1
0x18006c8cc  cmp     eax, 7
0x18006c8cf  jnz     short loc_18006C8ED
0x18006c8d1  mov     rax, [rdi]
0x18006c8d4  mov     rdx, r12
0x18006c8d7  mov     rcx, rdi
0x18006c8da  mov     rax, [rax+38h]
0x18006c8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c8e3  jmp     loc_18006C794
0x18006c8e8  mov     ebx, 4
0x18006c8ed  mov     rax, [rdi]
0x18006c8f0  mov     edx, 1
0x18006c8f5  mov     rcx, rdi
0x18006c8f8  mov     rax, [rax]
0x18006c8fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c900  test    r15, r15
0x18006c903  jz      short loc_18006C912
0x18006c905  mov     edx, 10h
0x18006c90a  mov     rcx, r15; Block
0x18006c90d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006c912  mov     rcx, [rbp+TokenHandle]; hObject
0x18006c916  test    rcx, rcx
0x18006c919  jz      short loc_18006C927
0x18006c91b  call    cs:__imp_CloseHandle
0x18006c922  nop     dword ptr [rax+rax+00h]
0x18006c927  test    r14, r14
0x18006c92a  jz      short loc_18006C93B
0x18006c92c  mov     rcx, r14; pwk
0x18006c92f  call    cs:__imp_CloseThreadpoolWork
0x18006c936  nop     dword ptr [rax+rax+00h]
0x18006c93b  mov     eax, ebx
0x18006c93d  mov     rcx, [rbp+var_8]
0x18006c941  xor     rcx, rsp; StackCookie
0x18006c944  call    __security_check_cookie
0x18006c949  mov     rbx, [rsp+80h+arg_18]
0x18006c951  add     rsp, 80h
0x18006c958  pop     r15
0x18006c95a  pop     r14
0x18006c95c  pop     r13
0x18006c95e  pop     r12
0x18006c960  pop     rdi
0x18006c961  pop     rsi
0x18006c962  pop     rbp
0x18006c963  retn
```
