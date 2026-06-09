# CSpWmiMethod<_SPACES_PhysicalDisk_SetFriendlyName>::RunMethod<CSpPhysicalDisk::SetFriendlyName,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ef7a8`
- end: `0x1800efaf6`
- name: `??$RunMethod@VSetFriendlyName@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_SetFriendlyName@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800ef7a8`
- `0x1800f055c`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef974`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ef955`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ef955`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ef96a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ef96a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ef93b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ef93b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800efa14`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800efa14`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800efac7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800efac7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800efab9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800efab9`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_SetFriendlyName>::RunMethod<CSpPhysicalDisk::SetFriendlyName,4>(
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
  CSpPhysicalDisk::SetFriendlyName *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::SetFriendlyName *)operator new(0x160u);
  v7 = CSpPhysicalDisk::SetFriendlyName::SetFriendlyName(v25);
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
      v25 = (CSpPhysicalDisk::SetFriendlyName *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_180334F26,
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
0x1800ef7a8  mov     [rsp-38h+arg_18], rbx
0x1800ef7ad  push    rbp
0x1800ef7ae  push    rsi
0x1800ef7af  push    rdi
0x1800ef7b0  push    r12
0x1800ef7b2  push    r13
0x1800ef7b4  push    r14
0x1800ef7b6  push    r15
0x1800ef7b8  mov     rbp, rsp
0x1800ef7bb  sub     rsp, 80h
0x1800ef7c2  mov     rax, cs:__security_cookie
0x1800ef7c9  xor     rax, rsp
0x1800ef7cc  mov     [rbp+var_8], rax
0x1800ef7d0  xor     eax, eax
0x1800ef7d2  mov     rsi, rcx
0x1800ef7d5  xorps   xmm0, xmm0
0x1800ef7d8  mov     [rbp+var_10], eax
0x1800ef7db  mov     ecx, 160h; Size
0x1800ef7e0  mov     [rbp+var_40], eax
0x1800ef7e3  movups  [rbp+var_20], xmm0
0x1800ef7e7  mov     [rbp+TokenHandle], rax
0x1800ef7eb  mov     r12, r8
0x1800ef7ee  mov     r13, rdx
0x1800ef7f1  xor     r14d, r14d
0x1800ef7f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ef7f9  mov     rcx, rax; this
0x1800ef7fc  mov     [rbp+var_28], rax
0x1800ef800  call    ??0SetFriendlyName@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::SetFriendlyName::SetFriendlyName(void)
0x1800ef805  mov     rdi, rax
0x1800ef808  test    rax, rax
0x1800ef80b  jnz     short loc_1800EF815
0x1800ef80d  lea     ebx, [rax+1Bh]
0x1800ef810  jmp     loc_1800EFAB0
0x1800ef815  mov     rax, [rax]
0x1800ef818  mov     rdx, rsi
0x1800ef81b  mov     rcx, rdi
0x1800ef81e  xor     r15d, r15d
0x1800ef821  mov     rax, [rax+8]
0x1800ef825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef82a  lea     rcx, [rbp+var_40]
0x1800ef82e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ef833  mov     [rdi+1Ch], eax
0x1800ef836  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ef83a  mov     ecx, [rsi+14h]; unsigned int
0x1800ef83d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ef842  mov     eax, cs:dword_180397B68
0x1800ef848  cmp     eax, 5
0x1800ef84b  jbe     short loc_1800EF8BB
0x1800ef84d  mov     rdx, 400000000000h
0x1800ef857  lea     rcx, dword_180397B68
0x1800ef85e  call    _tlgKeywordOn
0x1800ef863  test    al, al
0x1800ef865  jz      short loc_1800EF8BB
0x1800ef867  mov     eax, [rbp+var_40]
0x1800ef86a  lea     rdx, word_180334F26
0x1800ef871  xor     ecx, ecx
0x1800ef873  cmp     [rdi+1Ch], eax
0x1800ef876  movzx   eax, word ptr [rbp+var_10]
0x1800ef87a  mov     word ptr [rbp+var_40], ax
0x1800ef87e  setnz   cl
0x1800ef881  mov     eax, [rsi+14h]
0x1800ef884  mov     [rbp+var_38], eax
0x1800ef887  lea     rax, [rbp+var_20]
0x1800ef88b  mov     [rbp+var_28], rax
0x1800ef88f  lea     rax, [rbp+var_3C]
0x1800ef893  mov     [rsp+80h+var_48], rax
0x1800ef898  lea     rax, [rbp+var_40]
0x1800ef89c  mov     [rsp+80h+var_50], rax
0x1800ef8a1  lea     rax, [rbp+var_38]
0x1800ef8a5  mov     [rsp+80h+var_58], rax
0x1800ef8aa  lea     rax, [rbp+var_28]
0x1800ef8ae  mov     [rsp+80h+var_60], rax
0x1800ef8b3  mov     [rbp+var_3C], ecx
0x1800ef8b6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ef8bb  mov     rcx, [rsi]
0x1800ef8be  test    rcx, rcx
0x1800ef8c1  jz      loc_1800EFA86
0x1800ef8c7  mov     rax, [rcx]
0x1800ef8ca  test    rax, rax
0x1800ef8cd  jz      loc_1800EFA86
0x1800ef8d3  mov     rax, [rax+18h]
0x1800ef8d7  lea     r8, [rdi+20h]
0x1800ef8db  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ef8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef8e7  mov     ebx, eax
0x1800ef8e9  test    eax, eax
0x1800ef8eb  jnz     loc_1800EFA8B
0x1800ef8f1  cmp     [rsi+10h], r14d
0x1800ef8f5  jz      loc_1800EFA1F
0x1800ef8fb  lea     rbx, [rdi+148h]
0x1800ef902  mov     rcx, rbx
0x1800ef905  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ef90a  mov     rcx, rbx; struct CSpJobMgr **
0x1800ef90d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ef912  test    eax, eax
0x1800ef914  jnz     short loc_1800EF91E
0x1800ef916  lea     ebx, [rax+1Ch]
0x1800ef919  jmp     loc_1800EFA8B
0x1800ef91e  mov     ecx, 10h; Size
0x1800ef923  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ef928  xor     r8d, r8d; pcbe
0x1800ef92b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ef932  mov     rdx, rax; pv
0x1800ef935  mov     r15, rax
0x1800ef938  mov     [rax], rdi
0x1800ef93b  call    cs:__imp_CreateThreadpoolWork
0x1800ef941  mov     r14, rax
0x1800ef944  test    rax, rax
0x1800ef947  jnz     short loc_1800EF955
0x1800ef949  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800ef94e  mov     ebx, eax
0x1800ef950  jmp     loc_1800EFA8B
0x1800ef955  call    cs:__imp_GetCurrentThread
0x1800ef95b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ef95f  xor     r8d, r8d; OpenAsSelf
0x1800ef962  mov     rcx, rax; ThreadHandle
0x1800ef965  mov     edx, 2000Ch; DesiredAccess
0x1800ef96a  call    cs:__imp_OpenThreadToken
0x1800ef970  test    eax, eax
0x1800ef972  jnz     short loc_1800EF981
0x1800ef974  call    cs:__imp_GetLastError
0x1800ef97a  cmp     eax, 3F0h
0x1800ef97f  jnz     short loc_1800EF949
0x1800ef981  mov     rax, [rbp+TokenHandle]
0x1800ef985  mov     r8, r13
0x1800ef988  mov     [r15+8], rax
0x1800ef98c  mov     rcx, rdi
0x1800ef98f  mov     rax, [rdi]
0x1800ef992  mov     rdx, [rsi+8]
0x1800ef996  mov     rax, [rax+18h]
0x1800ef99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef99f  mov     rax, [rdi]
0x1800ef9a2  mov     rdx, r12
0x1800ef9a5  mov     rcx, rdi
0x1800ef9a8  mov     rax, [rax+28h]
0x1800ef9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef9b1  mov     ebx, eax
0x1800ef9b3  test    eax, eax
0x1800ef9b5  jz      short loc_1800EF9C0
0x1800ef9b7  cmp     eax, 7
0x1800ef9ba  jnz     loc_1800EFA8B
0x1800ef9c0  mov     rax, [rdi]
0x1800ef9c3  mov     rdx, r12
0x1800ef9c6  mov     rcx, rdi
0x1800ef9c9  mov     rax, [rax+38h]
0x1800ef9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef9d2  mov     ebx, eax
0x1800ef9d4  test    eax, eax
0x1800ef9d6  jnz     loc_1800EFA8B
0x1800ef9dc  mov     rax, [rdi+150h]
0x1800ef9e3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800ef9ea  jnz     short loc_1800EFA00
0x1800ef9ec  mov     rax, [rdi+158h]
0x1800ef9f3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800ef9fa  jz      loc_1800EFA8B
0x1800efa00  mov     rdx, r12
0x1800efa03  mov     rcx, rdi
0x1800efa06  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800efa0b  mov     ebx, eax
0x1800efa0d  test    eax, eax
0x1800efa0f  jnz     short loc_1800EFA8B
0x1800efa11  mov     rcx, r14; pwk
0x1800efa14  call    cs:__imp_SubmitThreadpoolWork
0x1800efa1a  jmp     loc_1800EFACD
0x1800efa1f  mov     rax, [rdi]
0x1800efa22  mov     r8, r13
0x1800efa25  mov     rdx, [rsi+8]
0x1800efa29  mov     rcx, rdi
0x1800efa2c  mov     rax, [rax+10h]
0x1800efa30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efa35  mov     rax, [rdi]
0x1800efa38  mov     rdx, r12
0x1800efa3b  mov     rcx, rdi
0x1800efa3e  mov     rax, [rax+30h]
0x1800efa42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efa47  mov     ebx, eax
0x1800efa49  test    eax, eax
0x1800efa4b  jz      short loc_1800EFA52
0x1800efa4d  cmp     eax, 7
0x1800efa50  jnz     short loc_1800EFA8B
0x1800efa52  mov     rax, [rdi]
0x1800efa55  mov     rdx, r12
0x1800efa58  mov     rcx, rdi
0x1800efa5b  mov     rax, [rax+28h]
0x1800efa5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efa64  mov     ebx, eax
0x1800efa66  test    eax, eax
0x1800efa68  jz      short loc_1800EFA6F
0x1800efa6a  cmp     eax, 7
0x1800efa6d  jnz     short loc_1800EFA8B
0x1800efa6f  mov     rax, [rdi]
0x1800efa72  mov     rdx, r12
0x1800efa75  mov     rcx, rdi
0x1800efa78  mov     rax, [rax+38h]
0x1800efa7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efa81  jmp     loc_1800EF94E
0x1800efa86  mov     ebx, 4
0x1800efa8b  mov     rax, [rdi]
0x1800efa8e  mov     edx, 1
0x1800efa93  mov     rcx, rdi
0x1800efa96  mov     rax, [rax]
0x1800efa99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efa9e  test    r15, r15
0x1800efaa1  jz      short loc_1800EFAB0
0x1800efaa3  mov     edx, 10h
0x1800efaa8  mov     rcx, r15; Block
0x1800efaab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800efab0  mov     rcx, [rbp+TokenHandle]; hObject
0x1800efab4  test    rcx, rcx
0x1800efab7  jz      short loc_1800EFABF
0x1800efab9  call    cs:__imp_CloseHandle
0x1800efabf  test    r14, r14
0x1800efac2  jz      short loc_1800EFACD
0x1800efac4  mov     rcx, r14; pwk
0x1800efac7  call    cs:__imp_CloseThreadpoolWork
0x1800efacd  mov     eax, ebx
0x1800efacf  mov     rcx, [rbp+var_8]
0x1800efad3  xor     rcx, rsp; StackCookie
0x1800efad6  call    __security_check_cookie
0x1800efadb  mov     rbx, [rsp+80h+arg_18]
0x1800efae3  add     rsp, 80h
0x1800efaea  pop     r15
0x1800efaec  pop     r14
0x1800efaee  pop     r13
0x1800efaf0  pop     r12
0x1800efaf2  pop     rdi
0x1800efaf3  pop     rsi
0x1800efaf4  pop     rbp
0x1800efaf5  retn
```
