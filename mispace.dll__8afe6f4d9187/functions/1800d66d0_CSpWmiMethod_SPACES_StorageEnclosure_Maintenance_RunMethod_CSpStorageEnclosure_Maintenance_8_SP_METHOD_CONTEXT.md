# CSpWmiMethod<_SPACES_StorageEnclosure_Maintenance>::RunMethod<CSpStorageEnclosure::Maintenance,8>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800d66d0`
- end: `0x1800d6a1e`
- name: `??$RunMethod@VMaintenance@CSpStorageEnclosure@@$07@?$CSpWmiMethod@U_SPACES_StorageEnclosure_Maintenance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800d8f20`

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
- `0x1800d66d0`
- `0x1800d7228`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d689c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d689c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d687d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d687d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d6892`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d6892`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d6863`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d6863`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d693c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d693c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d69ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d69ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d69e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d69e1`

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
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageEnclosure::Maintenance *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_18032F5CE,
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
0x1800d66d0  mov     [rsp-38h+arg_18], rbx
0x1800d66d5  push    rbp
0x1800d66d6  push    rsi
0x1800d66d7  push    rdi
0x1800d66d8  push    r12
0x1800d66da  push    r13
0x1800d66dc  push    r14
0x1800d66de  push    r15
0x1800d66e0  mov     rbp, rsp
0x1800d66e3  sub     rsp, 80h
0x1800d66ea  mov     rax, cs:__security_cookie
0x1800d66f1  xor     rax, rsp
0x1800d66f4  mov     [rbp+var_8], rax
0x1800d66f8  xor     eax, eax
0x1800d66fa  mov     rsi, rcx
0x1800d66fd  xorps   xmm0, xmm0
0x1800d6700  mov     [rbp+var_10], eax
0x1800d6703  mov     ecx, 180h; Size
0x1800d6708  mov     [rbp+var_40], eax
0x1800d670b  movups  [rbp+var_20], xmm0
0x1800d670f  mov     [rbp+TokenHandle], rax
0x1800d6713  mov     r12, r8
0x1800d6716  mov     r13, rdx
0x1800d6719  xor     r14d, r14d
0x1800d671c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d6721  mov     rcx, rax; this
0x1800d6724  mov     [rbp+var_28], rax
0x1800d6728  call    ??0Maintenance@CSpStorageEnclosure@@QEAA@XZ; CSpStorageEnclosure::Maintenance::Maintenance(void)
0x1800d672d  mov     rdi, rax
0x1800d6730  test    rax, rax
0x1800d6733  jnz     short loc_1800D673D
0x1800d6735  lea     ebx, [rax+1Bh]
0x1800d6738  jmp     loc_1800D69D8
0x1800d673d  mov     rax, [rax]
0x1800d6740  mov     rdx, rsi
0x1800d6743  mov     rcx, rdi
0x1800d6746  xor     r15d, r15d
0x1800d6749  mov     rax, [rax+8]
0x1800d674d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6752  lea     rcx, [rbp+var_40]
0x1800d6756  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800d675b  mov     [rdi+1Ch], eax
0x1800d675e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800d6762  mov     ecx, [rsi+14h]; unsigned int
0x1800d6765  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800d676a  mov     eax, cs:dword_180397B68
0x1800d6770  cmp     eax, 5
0x1800d6773  jbe     short loc_1800D67E3
0x1800d6775  mov     rdx, 400000000000h
0x1800d677f  lea     rcx, dword_180397B68
0x1800d6786  call    _tlgKeywordOn
0x1800d678b  test    al, al
0x1800d678d  jz      short loc_1800D67E3
0x1800d678f  mov     eax, [rbp+var_40]
0x1800d6792  lea     rdx, word_18032F5CE
0x1800d6799  xor     ecx, ecx
0x1800d679b  cmp     [rdi+1Ch], eax
0x1800d679e  movzx   eax, word ptr [rbp+var_10]
0x1800d67a2  mov     word ptr [rbp+var_40], ax
0x1800d67a6  setnz   cl
0x1800d67a9  mov     eax, [rsi+14h]
0x1800d67ac  mov     [rbp+var_38], eax
0x1800d67af  lea     rax, [rbp+var_20]
0x1800d67b3  mov     [rbp+var_28], rax
0x1800d67b7  lea     rax, [rbp+var_3C]
0x1800d67bb  mov     [rsp+80h+var_48], rax
0x1800d67c0  lea     rax, [rbp+var_40]
0x1800d67c4  mov     [rsp+80h+var_50], rax
0x1800d67c9  lea     rax, [rbp+var_38]
0x1800d67cd  mov     [rsp+80h+var_58], rax
0x1800d67d2  lea     rax, [rbp+var_28]
0x1800d67d6  mov     [rsp+80h+var_60], rax
0x1800d67db  mov     [rbp+var_3C], ecx
0x1800d67de  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800d67e3  mov     rcx, [rsi]
0x1800d67e6  test    rcx, rcx
0x1800d67e9  jz      loc_1800D69AE
0x1800d67ef  mov     rax, [rcx]
0x1800d67f2  test    rax, rax
0x1800d67f5  jz      loc_1800D69AE
0x1800d67fb  mov     rax, [rax+18h]
0x1800d67ff  lea     r8, [rdi+20h]
0x1800d6803  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800d680a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d680f  mov     ebx, eax
0x1800d6811  test    eax, eax
0x1800d6813  jnz     loc_1800D69B3
0x1800d6819  cmp     [rsi+10h], r14d
0x1800d681d  jz      loc_1800D6947
0x1800d6823  lea     rbx, [rdi+148h]
0x1800d682a  mov     rcx, rbx
0x1800d682d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800d6832  mov     rcx, rbx; struct CSpJobMgr **
0x1800d6835  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800d683a  test    eax, eax
0x1800d683c  jnz     short loc_1800D6846
0x1800d683e  lea     ebx, [rax+1Ch]
0x1800d6841  jmp     loc_1800D69B3
0x1800d6846  mov     ecx, 10h; Size
0x1800d684b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d6850  xor     r8d, r8d; pcbe
0x1800d6853  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800d685a  mov     rdx, rax; pv
0x1800d685d  mov     r15, rax
0x1800d6860  mov     [rax], rdi
0x1800d6863  call    cs:__imp_CreateThreadpoolWork
0x1800d6869  mov     r14, rax
0x1800d686c  test    rax, rax
0x1800d686f  jnz     short loc_1800D687D
0x1800d6871  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800d6876  mov     ebx, eax
0x1800d6878  jmp     loc_1800D69B3
0x1800d687d  call    cs:__imp_GetCurrentThread
0x1800d6883  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d6887  xor     r8d, r8d; OpenAsSelf
0x1800d688a  mov     rcx, rax; ThreadHandle
0x1800d688d  mov     edx, 2000Ch; DesiredAccess
0x1800d6892  call    cs:__imp_OpenThreadToken
0x1800d6898  test    eax, eax
0x1800d689a  jnz     short loc_1800D68A9
0x1800d689c  call    cs:__imp_GetLastError
0x1800d68a2  cmp     eax, 3F0h
0x1800d68a7  jnz     short loc_1800D6871
0x1800d68a9  mov     rax, [rbp+TokenHandle]
0x1800d68ad  mov     r8, r13
0x1800d68b0  mov     [r15+8], rax
0x1800d68b4  mov     rcx, rdi
0x1800d68b7  mov     rax, [rdi]
0x1800d68ba  mov     rdx, [rsi+8]
0x1800d68be  mov     rax, [rax+18h]
0x1800d68c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d68c7  mov     rax, [rdi]
0x1800d68ca  mov     rdx, r12
0x1800d68cd  mov     rcx, rdi
0x1800d68d0  mov     rax, [rax+28h]
0x1800d68d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d68d9  mov     ebx, eax
0x1800d68db  test    eax, eax
0x1800d68dd  jz      short loc_1800D68E8
0x1800d68df  cmp     eax, 7
0x1800d68e2  jnz     loc_1800D69B3
0x1800d68e8  mov     rax, [rdi]
0x1800d68eb  mov     rdx, r12
0x1800d68ee  mov     rcx, rdi
0x1800d68f1  mov     rax, [rax+38h]
0x1800d68f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d68fa  mov     ebx, eax
0x1800d68fc  test    eax, eax
0x1800d68fe  jnz     loc_1800D69B3
0x1800d6904  mov     rax, [rdi+150h]
0x1800d690b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800d6912  jnz     short loc_1800D6928
0x1800d6914  mov     rax, [rdi+158h]
0x1800d691b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800d6922  jz      loc_1800D69B3
0x1800d6928  mov     rdx, r12
0x1800d692b  mov     rcx, rdi
0x1800d692e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800d6933  mov     ebx, eax
0x1800d6935  test    eax, eax
0x1800d6937  jnz     short loc_1800D69B3
0x1800d6939  mov     rcx, r14; pwk
0x1800d693c  call    cs:__imp_SubmitThreadpoolWork
0x1800d6942  jmp     loc_1800D69F5
0x1800d6947  mov     rax, [rdi]
0x1800d694a  mov     r8, r13
0x1800d694d  mov     rdx, [rsi+8]
0x1800d6951  mov     rcx, rdi
0x1800d6954  mov     rax, [rax+10h]
0x1800d6958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d695d  mov     rax, [rdi]
0x1800d6960  mov     rdx, r12
0x1800d6963  mov     rcx, rdi
0x1800d6966  mov     rax, [rax+30h]
0x1800d696a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d696f  mov     ebx, eax
0x1800d6971  test    eax, eax
0x1800d6973  jz      short loc_1800D697A
0x1800d6975  cmp     eax, 7
0x1800d6978  jnz     short loc_1800D69B3
0x1800d697a  mov     rax, [rdi]
0x1800d697d  mov     rdx, r12
0x1800d6980  mov     rcx, rdi
0x1800d6983  mov     rax, [rax+28h]
0x1800d6987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d698c  mov     ebx, eax
0x1800d698e  test    eax, eax
0x1800d6990  jz      short loc_1800D6997
0x1800d6992  cmp     eax, 7
0x1800d6995  jnz     short loc_1800D69B3
0x1800d6997  mov     rax, [rdi]
0x1800d699a  mov     rdx, r12
0x1800d699d  mov     rcx, rdi
0x1800d69a0  mov     rax, [rax+38h]
0x1800d69a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d69a9  jmp     loc_1800D6876
0x1800d69ae  mov     ebx, 4
0x1800d69b3  mov     rax, [rdi]
0x1800d69b6  mov     edx, 1
0x1800d69bb  mov     rcx, rdi
0x1800d69be  mov     rax, [rax]
0x1800d69c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d69c6  test    r15, r15
0x1800d69c9  jz      short loc_1800D69D8
0x1800d69cb  mov     edx, 10h
0x1800d69d0  mov     rcx, r15; Block
0x1800d69d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d69d8  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d69dc  test    rcx, rcx
0x1800d69df  jz      short loc_1800D69E7
0x1800d69e1  call    cs:__imp_CloseHandle
0x1800d69e7  test    r14, r14
0x1800d69ea  jz      short loc_1800D69F5
0x1800d69ec  mov     rcx, r14; pwk
0x1800d69ef  call    cs:__imp_CloseThreadpoolWork
0x1800d69f5  mov     eax, ebx
0x1800d69f7  mov     rcx, [rbp+var_8]
0x1800d69fb  xor     rcx, rsp; StackCookie
0x1800d69fe  call    __security_check_cookie
0x1800d6a03  mov     rbx, [rsp+80h+arg_18]
0x1800d6a0b  add     rsp, 80h
0x1800d6a12  pop     r15
0x1800d6a14  pop     r14
0x1800d6a16  pop     r13
0x1800d6a18  pop     r12
0x1800d6a1a  pop     rdi
0x1800d6a1b  pop     rsi
0x1800d6a1c  pop     rbp
0x1800d6a1d  retn
```
