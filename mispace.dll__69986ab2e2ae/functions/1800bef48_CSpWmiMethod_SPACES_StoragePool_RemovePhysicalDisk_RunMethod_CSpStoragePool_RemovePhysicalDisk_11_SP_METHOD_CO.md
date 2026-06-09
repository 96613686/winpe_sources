# CSpWmiMethod<_SPACES_StoragePool_RemovePhysicalDisk>::RunMethod<CSpStoragePool::RemovePhysicalDisk,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bef48`
- end: `0x1800bf2c5`
- name: `??$RunMethod@VRemovePhysicalDisk@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_RemovePhysicalDisk@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800c5060`

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
- `0x1800bef48`
- `0x1800c113c`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf126`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bf0fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bf0fb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bf116`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bf116`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bf0db`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bf0db`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bf1d0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bf1d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bf28f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bf28f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bf27b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bf27b`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_RemovePhysicalDisk>::RunMethod<CSpStoragePool::RemovePhysicalDisk,11>(
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
  CSpStoragePool::RemovePhysicalDisk *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::RemovePhysicalDisk *)operator new(0x1A0u);
  v7 = CSpStoragePool::RemovePhysicalDisk::RemovePhysicalDisk(v25);
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
      v25 = (CSpStoragePool::RemovePhysicalDisk *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_1803319A4,
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
0x1800bef48  mov     [rsp-38h+arg_18], rbx
0x1800bef4d  push    rbp
0x1800bef4e  push    rsi
0x1800bef4f  push    rdi
0x1800bef50  push    r12
0x1800bef52  push    r13
0x1800bef54  push    r14
0x1800bef56  push    r15
0x1800bef58  mov     rbp, rsp
0x1800bef5b  sub     rsp, 80h
0x1800bef62  mov     rax, cs:__security_cookie
0x1800bef69  xor     rax, rsp
0x1800bef6c  mov     [rbp+var_8], rax
0x1800bef70  xor     eax, eax
0x1800bef72  mov     rsi, rcx
0x1800bef75  xorps   xmm0, xmm0
0x1800bef78  mov     [rbp+var_10], eax
0x1800bef7b  mov     ecx, 1A0h; Size
0x1800bef80  mov     [rbp+var_40], eax
0x1800bef83  movups  [rbp+var_20], xmm0
0x1800bef87  mov     [rbp+TokenHandle], rax
0x1800bef8b  mov     r12, r8
0x1800bef8e  mov     r13, rdx
0x1800bef91  xor     r14d, r14d
0x1800bef94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bef99  mov     rcx, rax; this
0x1800bef9c  mov     [rbp+var_28], rax
0x1800befa0  call    ??0RemovePhysicalDisk@CSpStoragePool@@QEAA@XZ; CSpStoragePool::RemovePhysicalDisk::RemovePhysicalDisk(void)
0x1800befa5  mov     rdi, rax
0x1800befa8  test    rax, rax
0x1800befab  jnz     short loc_1800BEFB5
0x1800befad  lea     ebx, [rax+1Bh]
0x1800befb0  jmp     loc_1800BF272
0x1800befb5  mov     rax, [rax]
0x1800befb8  mov     rdx, rsi
0x1800befbb  mov     rcx, rdi
0x1800befbe  xor     r15d, r15d
0x1800befc1  mov     rax, [rax+8]
0x1800befc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800befca  lea     rcx, [rbp+var_40]
0x1800befce  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800befd3  mov     [rdi+1Ch], eax
0x1800befd6  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800befda  mov     ecx, [rsi+14h]; unsigned int
0x1800befdd  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800befe2  mov     eax, cs:dword_18039EB68
0x1800befe8  cmp     eax, 5
0x1800befeb  jbe     short loc_1800BF05B
0x1800befed  mov     rdx, 400000000000h
0x1800beff7  lea     rcx, dword_18039EB68
0x1800beffe  call    _tlgKeywordOn
0x1800bf003  test    al, al
0x1800bf005  jz      short loc_1800BF05B
0x1800bf007  mov     eax, [rbp+var_40]
0x1800bf00a  lea     rdx, dword_1803319A4
0x1800bf011  xor     ecx, ecx
0x1800bf013  cmp     [rdi+1Ch], eax
0x1800bf016  movzx   eax, word ptr [rbp+var_10]
0x1800bf01a  mov     word ptr [rbp+var_40], ax
0x1800bf01e  setnz   cl
0x1800bf021  mov     eax, [rsi+14h]
0x1800bf024  mov     [rbp+var_38], eax
0x1800bf027  lea     rax, [rbp+var_20]
0x1800bf02b  mov     [rbp+var_28], rax
0x1800bf02f  lea     rax, [rbp+var_3C]
0x1800bf033  mov     [rsp+80h+var_48], rax
0x1800bf038  lea     rax, [rbp+var_40]
0x1800bf03c  mov     [rsp+80h+var_50], rax
0x1800bf041  lea     rax, [rbp+var_38]
0x1800bf045  mov     [rsp+80h+var_58], rax
0x1800bf04a  lea     rax, [rbp+var_28]
0x1800bf04e  mov     [rsp+80h+var_60], rax
0x1800bf053  mov     [rbp+var_3C], ecx
0x1800bf056  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bf05b  mov     rcx, [rsi]
0x1800bf05e  test    rcx, rcx
0x1800bf061  jz      loc_1800BF248
0x1800bf067  mov     rax, [rcx]
0x1800bf06a  test    rax, rax
0x1800bf06d  jz      loc_1800BF248
0x1800bf073  mov     rax, [rax+18h]
0x1800bf077  lea     r8, [rdi+20h]
0x1800bf07b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bf082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf087  mov     ebx, eax
0x1800bf089  test    eax, eax
0x1800bf08b  jnz     loc_1800BF24D
0x1800bf091  cmp     [rsi+10h], r14d
0x1800bf095  jz      loc_1800BF1E1
0x1800bf09b  lea     rbx, [rdi+148h]
0x1800bf0a2  mov     rcx, rbx
0x1800bf0a5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bf0aa  mov     rcx, rbx; struct CSpJobMgr **
0x1800bf0ad  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bf0b2  test    eax, eax
0x1800bf0b4  jnz     short loc_1800BF0BE
0x1800bf0b6  lea     ebx, [rax+1Ch]
0x1800bf0b9  jmp     loc_1800BF24D
0x1800bf0be  mov     ecx, 10h; Size
0x1800bf0c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bf0c8  xor     r8d, r8d; pcbe
0x1800bf0cb  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bf0d2  mov     rdx, rax; pv
0x1800bf0d5  mov     r15, rax
0x1800bf0d8  mov     [rax], rdi
0x1800bf0db  call    cs:__imp_CreateThreadpoolWork
0x1800bf0e2  nop     dword ptr [rax+rax+00h]
0x1800bf0e7  mov     r14, rax
0x1800bf0ea  test    rax, rax
0x1800bf0ed  jnz     short loc_1800BF0FB
0x1800bf0ef  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bf0f4  mov     ebx, eax
0x1800bf0f6  jmp     loc_1800BF24D
0x1800bf0fb  call    cs:__imp_GetCurrentThread
0x1800bf102  nop     dword ptr [rax+rax+00h]
0x1800bf107  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bf10b  xor     r8d, r8d; OpenAsSelf
0x1800bf10e  mov     rcx, rax; ThreadHandle
0x1800bf111  mov     edx, 2000Ch; DesiredAccess
0x1800bf116  call    cs:__imp_OpenThreadToken
0x1800bf11d  nop     dword ptr [rax+rax+00h]
0x1800bf122  test    eax, eax
0x1800bf124  jnz     short loc_1800BF139
0x1800bf126  call    cs:__imp_GetLastError
0x1800bf12d  nop     dword ptr [rax+rax+00h]
0x1800bf132  cmp     eax, 3F0h
0x1800bf137  jnz     short loc_1800BF0EF
0x1800bf139  mov     rax, [rbp+TokenHandle]
0x1800bf13d  mov     r8, r13
0x1800bf140  mov     [r15+8], rax
0x1800bf144  mov     rcx, rdi
0x1800bf147  mov     rax, [rdi]
0x1800bf14a  mov     rdx, [rsi+8]
0x1800bf14e  mov     rax, [rax+18h]
0x1800bf152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf157  mov     rax, [rdi]
0x1800bf15a  mov     rdx, r12
0x1800bf15d  mov     rcx, rdi
0x1800bf160  mov     rax, [rax+28h]
0x1800bf164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf169  mov     ebx, eax
0x1800bf16b  test    eax, eax
0x1800bf16d  jz      short loc_1800BF178
0x1800bf16f  cmp     eax, 7
0x1800bf172  jnz     loc_1800BF24D
0x1800bf178  mov     rax, [rdi]
0x1800bf17b  mov     rdx, r12
0x1800bf17e  mov     rcx, rdi
0x1800bf181  mov     rax, [rax+38h]
0x1800bf185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf18a  mov     ebx, eax
0x1800bf18c  test    eax, eax
0x1800bf18e  jnz     loc_1800BF24D
0x1800bf194  mov     rax, [rdi+150h]
0x1800bf19b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bf1a2  jnz     short loc_1800BF1B8
0x1800bf1a4  mov     rax, [rdi+158h]
0x1800bf1ab  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bf1b2  jz      loc_1800BF24D
0x1800bf1b8  mov     rdx, r12
0x1800bf1bb  mov     rcx, rdi
0x1800bf1be  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bf1c3  mov     ebx, eax
0x1800bf1c5  test    eax, eax
0x1800bf1c7  jnz     loc_1800BF24D
0x1800bf1cd  mov     rcx, r14; pwk
0x1800bf1d0  call    cs:__imp_SubmitThreadpoolWork
0x1800bf1d7  nop     dword ptr [rax+rax+00h]
0x1800bf1dc  jmp     loc_1800BF29B
0x1800bf1e1  mov     rax, [rdi]
0x1800bf1e4  mov     r8, r13
0x1800bf1e7  mov     rdx, [rsi+8]
0x1800bf1eb  mov     rcx, rdi
0x1800bf1ee  mov     rax, [rax+10h]
0x1800bf1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf1f7  mov     rax, [rdi]
0x1800bf1fa  mov     rdx, r12
0x1800bf1fd  mov     rcx, rdi
0x1800bf200  mov     rax, [rax+30h]
0x1800bf204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf209  mov     ebx, eax
0x1800bf20b  test    eax, eax
0x1800bf20d  jz      short loc_1800BF214
0x1800bf20f  cmp     eax, 7
0x1800bf212  jnz     short loc_1800BF24D
0x1800bf214  mov     rax, [rdi]
0x1800bf217  mov     rdx, r12
0x1800bf21a  mov     rcx, rdi
0x1800bf21d  mov     rax, [rax+28h]
0x1800bf221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf226  mov     ebx, eax
0x1800bf228  test    eax, eax
0x1800bf22a  jz      short loc_1800BF231
0x1800bf22c  cmp     eax, 7
0x1800bf22f  jnz     short loc_1800BF24D
0x1800bf231  mov     rax, [rdi]
0x1800bf234  mov     rdx, r12
0x1800bf237  mov     rcx, rdi
0x1800bf23a  mov     rax, [rax+38h]
0x1800bf23e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf243  jmp     loc_1800BF0F4
0x1800bf248  mov     ebx, 4
0x1800bf24d  mov     rax, [rdi]
0x1800bf250  mov     edx, 1
0x1800bf255  mov     rcx, rdi
0x1800bf258  mov     rax, [rax]
0x1800bf25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf260  test    r15, r15
0x1800bf263  jz      short loc_1800BF272
0x1800bf265  mov     edx, 10h
0x1800bf26a  mov     rcx, r15; Block
0x1800bf26d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bf272  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bf276  test    rcx, rcx
0x1800bf279  jz      short loc_1800BF287
0x1800bf27b  call    cs:__imp_CloseHandle
0x1800bf282  nop     dword ptr [rax+rax+00h]
0x1800bf287  test    r14, r14
0x1800bf28a  jz      short loc_1800BF29B
0x1800bf28c  mov     rcx, r14; pwk
0x1800bf28f  call    cs:__imp_CloseThreadpoolWork
0x1800bf296  nop     dword ptr [rax+rax+00h]
0x1800bf29b  mov     eax, ebx
0x1800bf29d  mov     rcx, [rbp+var_8]
0x1800bf2a1  xor     rcx, rsp; StackCookie
0x1800bf2a4  call    __security_check_cookie
0x1800bf2a9  mov     rbx, [rsp+80h+arg_18]
0x1800bf2b1  add     rsp, 80h
0x1800bf2b8  pop     r15
0x1800bf2ba  pop     r14
0x1800bf2bc  pop     r13
0x1800bf2be  pop     r12
0x1800bf2c0  pop     rdi
0x1800bf2c1  pop     rsi
0x1800bf2c2  pop     rbp
0x1800bf2c3  retn
```
