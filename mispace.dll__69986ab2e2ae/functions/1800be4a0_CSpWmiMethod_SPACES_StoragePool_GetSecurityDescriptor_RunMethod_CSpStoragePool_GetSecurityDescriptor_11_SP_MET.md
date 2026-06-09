# CSpWmiMethod<_SPACES_StoragePool_GetSecurityDescriptor>::RunMethod<CSpStoragePool::GetSecurityDescriptor,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800be4a0`
- end: `0x1800be81d`
- name: `??$RunMethod@VGetSecurityDescriptor@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_GetSecurityDescriptor@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

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
- `0x1800be4a0`
- `0x1800c104c`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be67e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be67e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800be653`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800be653`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800be66e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800be66e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800be633`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800be633`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800be728`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800be728`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800be7e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800be7e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be7d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be7d3`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_GetSecurityDescriptor>::RunMethod<CSpStoragePool::GetSecurityDescriptor,11>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 SecurityDescriptor; // rax
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
  CSpStoragePool::GetSecurityDescriptor *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::GetSecurityDescriptor *)operator new(0x168u);
  SecurityDescriptor = CSpStoragePool::GetSecurityDescriptor::GetSecurityDescriptor(v25);
  v8 = SecurityDescriptor;
  if ( SecurityDescriptor )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)SecurityDescriptor + 8LL))(SecurityDescriptor, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStoragePool::GetSecurityDescriptor *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)word_18033259A,
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
0x1800be4a0  mov     [rsp-38h+arg_18], rbx
0x1800be4a5  push    rbp
0x1800be4a6  push    rsi
0x1800be4a7  push    rdi
0x1800be4a8  push    r12
0x1800be4aa  push    r13
0x1800be4ac  push    r14
0x1800be4ae  push    r15
0x1800be4b0  mov     rbp, rsp
0x1800be4b3  sub     rsp, 80h
0x1800be4ba  mov     rax, cs:__security_cookie
0x1800be4c1  xor     rax, rsp
0x1800be4c4  mov     [rbp+var_8], rax
0x1800be4c8  xor     eax, eax
0x1800be4ca  mov     rsi, rcx
0x1800be4cd  xorps   xmm0, xmm0
0x1800be4d0  mov     [rbp+var_10], eax
0x1800be4d3  mov     ecx, 168h; Size
0x1800be4d8  mov     [rbp+var_40], eax
0x1800be4db  movups  [rbp+var_20], xmm0
0x1800be4df  mov     [rbp+TokenHandle], rax
0x1800be4e3  mov     r12, r8
0x1800be4e6  mov     r13, rdx
0x1800be4e9  xor     r14d, r14d
0x1800be4ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800be4f1  mov     rcx, rax; this
0x1800be4f4  mov     [rbp+var_28], rax
0x1800be4f8  call    ??0GetSecurityDescriptor@CSpStoragePool@@QEAA@XZ; CSpStoragePool::GetSecurityDescriptor::GetSecurityDescriptor(void)
0x1800be4fd  mov     rdi, rax
0x1800be500  test    rax, rax
0x1800be503  jnz     short loc_1800BE50D
0x1800be505  lea     ebx, [rax+1Bh]
0x1800be508  jmp     loc_1800BE7CA
0x1800be50d  mov     rax, [rax]
0x1800be510  mov     rdx, rsi
0x1800be513  mov     rcx, rdi
0x1800be516  xor     r15d, r15d
0x1800be519  mov     rax, [rax+8]
0x1800be51d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be522  lea     rcx, [rbp+var_40]
0x1800be526  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800be52b  mov     [rdi+1Ch], eax
0x1800be52e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800be532  mov     ecx, [rsi+14h]; unsigned int
0x1800be535  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800be53a  mov     eax, cs:dword_18039EB68
0x1800be540  cmp     eax, 5
0x1800be543  jbe     short loc_1800BE5B3
0x1800be545  mov     rdx, 400000000000h
0x1800be54f  lea     rcx, dword_18039EB68
0x1800be556  call    _tlgKeywordOn
0x1800be55b  test    al, al
0x1800be55d  jz      short loc_1800BE5B3
0x1800be55f  mov     eax, [rbp+var_40]
0x1800be562  lea     rdx, word_18033259A
0x1800be569  xor     ecx, ecx
0x1800be56b  cmp     [rdi+1Ch], eax
0x1800be56e  movzx   eax, word ptr [rbp+var_10]
0x1800be572  mov     word ptr [rbp+var_40], ax
0x1800be576  setnz   cl
0x1800be579  mov     eax, [rsi+14h]
0x1800be57c  mov     [rbp+var_38], eax
0x1800be57f  lea     rax, [rbp+var_20]
0x1800be583  mov     [rbp+var_28], rax
0x1800be587  lea     rax, [rbp+var_3C]
0x1800be58b  mov     [rsp+80h+var_48], rax
0x1800be590  lea     rax, [rbp+var_40]
0x1800be594  mov     [rsp+80h+var_50], rax
0x1800be599  lea     rax, [rbp+var_38]
0x1800be59d  mov     [rsp+80h+var_58], rax
0x1800be5a2  lea     rax, [rbp+var_28]
0x1800be5a6  mov     [rsp+80h+var_60], rax
0x1800be5ab  mov     [rbp+var_3C], ecx
0x1800be5ae  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800be5b3  mov     rcx, [rsi]
0x1800be5b6  test    rcx, rcx
0x1800be5b9  jz      loc_1800BE7A0
0x1800be5bf  mov     rax, [rcx]
0x1800be5c2  test    rax, rax
0x1800be5c5  jz      loc_1800BE7A0
0x1800be5cb  mov     rax, [rax+18h]
0x1800be5cf  lea     r8, [rdi+20h]
0x1800be5d3  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800be5da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be5df  mov     ebx, eax
0x1800be5e1  test    eax, eax
0x1800be5e3  jnz     loc_1800BE7A5
0x1800be5e9  cmp     [rsi+10h], r14d
0x1800be5ed  jz      loc_1800BE739
0x1800be5f3  lea     rbx, [rdi+148h]
0x1800be5fa  mov     rcx, rbx
0x1800be5fd  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800be602  mov     rcx, rbx; struct CSpJobMgr **
0x1800be605  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800be60a  test    eax, eax
0x1800be60c  jnz     short loc_1800BE616
0x1800be60e  lea     ebx, [rax+1Ch]
0x1800be611  jmp     loc_1800BE7A5
0x1800be616  mov     ecx, 10h; Size
0x1800be61b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800be620  xor     r8d, r8d; pcbe
0x1800be623  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800be62a  mov     rdx, rax; pv
0x1800be62d  mov     r15, rax
0x1800be630  mov     [rax], rdi
0x1800be633  call    cs:__imp_CreateThreadpoolWork
0x1800be63a  nop     dword ptr [rax+rax+00h]
0x1800be63f  mov     r14, rax
0x1800be642  test    rax, rax
0x1800be645  jnz     short loc_1800BE653
0x1800be647  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800be64c  mov     ebx, eax
0x1800be64e  jmp     loc_1800BE7A5
0x1800be653  call    cs:__imp_GetCurrentThread
0x1800be65a  nop     dword ptr [rax+rax+00h]
0x1800be65f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800be663  xor     r8d, r8d; OpenAsSelf
0x1800be666  mov     rcx, rax; ThreadHandle
0x1800be669  mov     edx, 2000Ch; DesiredAccess
0x1800be66e  call    cs:__imp_OpenThreadToken
0x1800be675  nop     dword ptr [rax+rax+00h]
0x1800be67a  test    eax, eax
0x1800be67c  jnz     short loc_1800BE691
0x1800be67e  call    cs:__imp_GetLastError
0x1800be685  nop     dword ptr [rax+rax+00h]
0x1800be68a  cmp     eax, 3F0h
0x1800be68f  jnz     short loc_1800BE647
0x1800be691  mov     rax, [rbp+TokenHandle]
0x1800be695  mov     r8, r13
0x1800be698  mov     [r15+8], rax
0x1800be69c  mov     rcx, rdi
0x1800be69f  mov     rax, [rdi]
0x1800be6a2  mov     rdx, [rsi+8]
0x1800be6a6  mov     rax, [rax+18h]
0x1800be6aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be6af  mov     rax, [rdi]
0x1800be6b2  mov     rdx, r12
0x1800be6b5  mov     rcx, rdi
0x1800be6b8  mov     rax, [rax+28h]
0x1800be6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be6c1  mov     ebx, eax
0x1800be6c3  test    eax, eax
0x1800be6c5  jz      short loc_1800BE6D0
0x1800be6c7  cmp     eax, 7
0x1800be6ca  jnz     loc_1800BE7A5
0x1800be6d0  mov     rax, [rdi]
0x1800be6d3  mov     rdx, r12
0x1800be6d6  mov     rcx, rdi
0x1800be6d9  mov     rax, [rax+38h]
0x1800be6dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be6e2  mov     ebx, eax
0x1800be6e4  test    eax, eax
0x1800be6e6  jnz     loc_1800BE7A5
0x1800be6ec  mov     rax, [rdi+150h]
0x1800be6f3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800be6fa  jnz     short loc_1800BE710
0x1800be6fc  mov     rax, [rdi+158h]
0x1800be703  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800be70a  jz      loc_1800BE7A5
0x1800be710  mov     rdx, r12
0x1800be713  mov     rcx, rdi
0x1800be716  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800be71b  mov     ebx, eax
0x1800be71d  test    eax, eax
0x1800be71f  jnz     loc_1800BE7A5
0x1800be725  mov     rcx, r14; pwk
0x1800be728  call    cs:__imp_SubmitThreadpoolWork
0x1800be72f  nop     dword ptr [rax+rax+00h]
0x1800be734  jmp     loc_1800BE7F3
0x1800be739  mov     rax, [rdi]
0x1800be73c  mov     r8, r13
0x1800be73f  mov     rdx, [rsi+8]
0x1800be743  mov     rcx, rdi
0x1800be746  mov     rax, [rax+10h]
0x1800be74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be74f  mov     rax, [rdi]
0x1800be752  mov     rdx, r12
0x1800be755  mov     rcx, rdi
0x1800be758  mov     rax, [rax+30h]
0x1800be75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be761  mov     ebx, eax
0x1800be763  test    eax, eax
0x1800be765  jz      short loc_1800BE76C
0x1800be767  cmp     eax, 7
0x1800be76a  jnz     short loc_1800BE7A5
0x1800be76c  mov     rax, [rdi]
0x1800be76f  mov     rdx, r12
0x1800be772  mov     rcx, rdi
0x1800be775  mov     rax, [rax+28h]
0x1800be779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be77e  mov     ebx, eax
0x1800be780  test    eax, eax
0x1800be782  jz      short loc_1800BE789
0x1800be784  cmp     eax, 7
0x1800be787  jnz     short loc_1800BE7A5
0x1800be789  mov     rax, [rdi]
0x1800be78c  mov     rdx, r12
0x1800be78f  mov     rcx, rdi
0x1800be792  mov     rax, [rax+38h]
0x1800be796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be79b  jmp     loc_1800BE64C
0x1800be7a0  mov     ebx, 4
0x1800be7a5  mov     rax, [rdi]
0x1800be7a8  mov     edx, 1
0x1800be7ad  mov     rcx, rdi
0x1800be7b0  mov     rax, [rax]
0x1800be7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be7b8  test    r15, r15
0x1800be7bb  jz      short loc_1800BE7CA
0x1800be7bd  mov     edx, 10h
0x1800be7c2  mov     rcx, r15; Block
0x1800be7c5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800be7ca  mov     rcx, [rbp+TokenHandle]; hObject
0x1800be7ce  test    rcx, rcx
0x1800be7d1  jz      short loc_1800BE7DF
0x1800be7d3  call    cs:__imp_CloseHandle
0x1800be7da  nop     dword ptr [rax+rax+00h]
0x1800be7df  test    r14, r14
0x1800be7e2  jz      short loc_1800BE7F3
0x1800be7e4  mov     rcx, r14; pwk
0x1800be7e7  call    cs:__imp_CloseThreadpoolWork
0x1800be7ee  nop     dword ptr [rax+rax+00h]
0x1800be7f3  mov     eax, ebx
0x1800be7f5  mov     rcx, [rbp+var_8]
0x1800be7f9  xor     rcx, rsp; StackCookie
0x1800be7fc  call    __security_check_cookie
0x1800be801  mov     rbx, [rsp+80h+arg_18]
0x1800be809  add     rsp, 80h
0x1800be810  pop     r15
0x1800be812  pop     r14
0x1800be814  pop     r13
0x1800be816  pop     r12
0x1800be818  pop     rdi
0x1800be819  pop     rsi
0x1800be81a  pop     rbp
0x1800be81b  retn
```
