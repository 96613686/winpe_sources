# CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::SetDefaults,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bc6e4`
- end: `0x1800bca32`
- name: `??$RunMethod@VSetDefaults@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800c1f80`

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
- `0x1800bc6e4`
- `0x1800be1d0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc8b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc8b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bc891`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bc891`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bc8a6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bc8a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bc877`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bc877`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bc950`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bc950`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bca03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bca03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bc9f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bc9f5`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::SetDefaults,11>(
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
  CSpStoragePool::SetDefaults *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::SetDefaults *)operator new(0x188u);
  v7 = CSpStoragePool::SetDefaults::SetDefaults(v25);
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
      v25 = (CSpStoragePool::SetDefaults *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)word_18032C1D2,
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
0x1800bc6e4  mov     [rsp-38h+arg_18], rbx
0x1800bc6e9  push    rbp
0x1800bc6ea  push    rsi
0x1800bc6eb  push    rdi
0x1800bc6ec  push    r12
0x1800bc6ee  push    r13
0x1800bc6f0  push    r14
0x1800bc6f2  push    r15
0x1800bc6f4  mov     rbp, rsp
0x1800bc6f7  sub     rsp, 80h
0x1800bc6fe  mov     rax, cs:__security_cookie
0x1800bc705  xor     rax, rsp
0x1800bc708  mov     [rbp+var_8], rax
0x1800bc70c  xor     eax, eax
0x1800bc70e  mov     rsi, rcx
0x1800bc711  xorps   xmm0, xmm0
0x1800bc714  mov     [rbp+var_10], eax
0x1800bc717  mov     ecx, 188h; Size
0x1800bc71c  mov     [rbp+var_40], eax
0x1800bc71f  movups  [rbp+var_20], xmm0
0x1800bc723  mov     [rbp+TokenHandle], rax
0x1800bc727  mov     r12, r8
0x1800bc72a  mov     r13, rdx
0x1800bc72d  xor     r14d, r14d
0x1800bc730  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bc735  mov     rcx, rax; this
0x1800bc738  mov     [rbp+var_28], rax
0x1800bc73c  call    ??0SetDefaults@CSpStoragePool@@QEAA@XZ; CSpStoragePool::SetDefaults::SetDefaults(void)
0x1800bc741  mov     rdi, rax
0x1800bc744  test    rax, rax
0x1800bc747  jnz     short loc_1800BC751
0x1800bc749  lea     ebx, [rax+1Bh]
0x1800bc74c  jmp     loc_1800BC9EC
0x1800bc751  mov     rax, [rax]
0x1800bc754  mov     rdx, rsi
0x1800bc757  mov     rcx, rdi
0x1800bc75a  xor     r15d, r15d
0x1800bc75d  mov     rax, [rax+8]
0x1800bc761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc766  lea     rcx, [rbp+var_40]
0x1800bc76a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bc76f  mov     [rdi+1Ch], eax
0x1800bc772  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bc776  mov     ecx, [rsi+14h]; unsigned int
0x1800bc779  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bc77e  mov     eax, cs:dword_180397B68
0x1800bc784  cmp     eax, 5
0x1800bc787  jbe     short loc_1800BC7F7
0x1800bc789  mov     rdx, 400000000000h
0x1800bc793  lea     rcx, dword_180397B68
0x1800bc79a  call    _tlgKeywordOn
0x1800bc79f  test    al, al
0x1800bc7a1  jz      short loc_1800BC7F7
0x1800bc7a3  mov     eax, [rbp+var_40]
0x1800bc7a6  lea     rdx, word_18032C1D2
0x1800bc7ad  xor     ecx, ecx
0x1800bc7af  cmp     [rdi+1Ch], eax
0x1800bc7b2  movzx   eax, word ptr [rbp+var_10]
0x1800bc7b6  mov     word ptr [rbp+var_40], ax
0x1800bc7ba  setnz   cl
0x1800bc7bd  mov     eax, [rsi+14h]
0x1800bc7c0  mov     [rbp+var_38], eax
0x1800bc7c3  lea     rax, [rbp+var_20]
0x1800bc7c7  mov     [rbp+var_28], rax
0x1800bc7cb  lea     rax, [rbp+var_3C]
0x1800bc7cf  mov     [rsp+80h+var_48], rax
0x1800bc7d4  lea     rax, [rbp+var_40]
0x1800bc7d8  mov     [rsp+80h+var_50], rax
0x1800bc7dd  lea     rax, [rbp+var_38]
0x1800bc7e1  mov     [rsp+80h+var_58], rax
0x1800bc7e6  lea     rax, [rbp+var_28]
0x1800bc7ea  mov     [rsp+80h+var_60], rax
0x1800bc7ef  mov     [rbp+var_3C], ecx
0x1800bc7f2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bc7f7  mov     rcx, [rsi]
0x1800bc7fa  test    rcx, rcx
0x1800bc7fd  jz      loc_1800BC9C2
0x1800bc803  mov     rax, [rcx]
0x1800bc806  test    rax, rax
0x1800bc809  jz      loc_1800BC9C2
0x1800bc80f  mov     rax, [rax+18h]
0x1800bc813  lea     r8, [rdi+20h]
0x1800bc817  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bc81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc823  mov     ebx, eax
0x1800bc825  test    eax, eax
0x1800bc827  jnz     loc_1800BC9C7
0x1800bc82d  cmp     [rsi+10h], r14d
0x1800bc831  jz      loc_1800BC95B
0x1800bc837  lea     rbx, [rdi+148h]
0x1800bc83e  mov     rcx, rbx
0x1800bc841  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bc846  mov     rcx, rbx; struct CSpJobMgr **
0x1800bc849  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bc84e  test    eax, eax
0x1800bc850  jnz     short loc_1800BC85A
0x1800bc852  lea     ebx, [rax+1Ch]
0x1800bc855  jmp     loc_1800BC9C7
0x1800bc85a  mov     ecx, 10h; Size
0x1800bc85f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bc864  xor     r8d, r8d; pcbe
0x1800bc867  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bc86e  mov     rdx, rax; pv
0x1800bc871  mov     r15, rax
0x1800bc874  mov     [rax], rdi
0x1800bc877  call    cs:__imp_CreateThreadpoolWork
0x1800bc87d  mov     r14, rax
0x1800bc880  test    rax, rax
0x1800bc883  jnz     short loc_1800BC891
0x1800bc885  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bc88a  mov     ebx, eax
0x1800bc88c  jmp     loc_1800BC9C7
0x1800bc891  call    cs:__imp_GetCurrentThread
0x1800bc897  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bc89b  xor     r8d, r8d; OpenAsSelf
0x1800bc89e  mov     rcx, rax; ThreadHandle
0x1800bc8a1  mov     edx, 2000Ch; DesiredAccess
0x1800bc8a6  call    cs:__imp_OpenThreadToken
0x1800bc8ac  test    eax, eax
0x1800bc8ae  jnz     short loc_1800BC8BD
0x1800bc8b0  call    cs:__imp_GetLastError
0x1800bc8b6  cmp     eax, 3F0h
0x1800bc8bb  jnz     short loc_1800BC885
0x1800bc8bd  mov     rax, [rbp+TokenHandle]
0x1800bc8c1  mov     r8, r13
0x1800bc8c4  mov     [r15+8], rax
0x1800bc8c8  mov     rcx, rdi
0x1800bc8cb  mov     rax, [rdi]
0x1800bc8ce  mov     rdx, [rsi+8]
0x1800bc8d2  mov     rax, [rax+18h]
0x1800bc8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc8db  mov     rax, [rdi]
0x1800bc8de  mov     rdx, r12
0x1800bc8e1  mov     rcx, rdi
0x1800bc8e4  mov     rax, [rax+28h]
0x1800bc8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc8ed  mov     ebx, eax
0x1800bc8ef  test    eax, eax
0x1800bc8f1  jz      short loc_1800BC8FC
0x1800bc8f3  cmp     eax, 7
0x1800bc8f6  jnz     loc_1800BC9C7
0x1800bc8fc  mov     rax, [rdi]
0x1800bc8ff  mov     rdx, r12
0x1800bc902  mov     rcx, rdi
0x1800bc905  mov     rax, [rax+38h]
0x1800bc909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc90e  mov     ebx, eax
0x1800bc910  test    eax, eax
0x1800bc912  jnz     loc_1800BC9C7
0x1800bc918  mov     rax, [rdi+150h]
0x1800bc91f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bc926  jnz     short loc_1800BC93C
0x1800bc928  mov     rax, [rdi+158h]
0x1800bc92f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bc936  jz      loc_1800BC9C7
0x1800bc93c  mov     rdx, r12
0x1800bc93f  mov     rcx, rdi
0x1800bc942  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bc947  mov     ebx, eax
0x1800bc949  test    eax, eax
0x1800bc94b  jnz     short loc_1800BC9C7
0x1800bc94d  mov     rcx, r14; pwk
0x1800bc950  call    cs:__imp_SubmitThreadpoolWork
0x1800bc956  jmp     loc_1800BCA09
0x1800bc95b  mov     rax, [rdi]
0x1800bc95e  mov     r8, r13
0x1800bc961  mov     rdx, [rsi+8]
0x1800bc965  mov     rcx, rdi
0x1800bc968  mov     rax, [rax+10h]
0x1800bc96c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc971  mov     rax, [rdi]
0x1800bc974  mov     rdx, r12
0x1800bc977  mov     rcx, rdi
0x1800bc97a  mov     rax, [rax+30h]
0x1800bc97e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc983  mov     ebx, eax
0x1800bc985  test    eax, eax
0x1800bc987  jz      short loc_1800BC98E
0x1800bc989  cmp     eax, 7
0x1800bc98c  jnz     short loc_1800BC9C7
0x1800bc98e  mov     rax, [rdi]
0x1800bc991  mov     rdx, r12
0x1800bc994  mov     rcx, rdi
0x1800bc997  mov     rax, [rax+28h]
0x1800bc99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc9a0  mov     ebx, eax
0x1800bc9a2  test    eax, eax
0x1800bc9a4  jz      short loc_1800BC9AB
0x1800bc9a6  cmp     eax, 7
0x1800bc9a9  jnz     short loc_1800BC9C7
0x1800bc9ab  mov     rax, [rdi]
0x1800bc9ae  mov     rdx, r12
0x1800bc9b1  mov     rcx, rdi
0x1800bc9b4  mov     rax, [rax+38h]
0x1800bc9b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc9bd  jmp     loc_1800BC88A
0x1800bc9c2  mov     ebx, 4
0x1800bc9c7  mov     rax, [rdi]
0x1800bc9ca  mov     edx, 1
0x1800bc9cf  mov     rcx, rdi
0x1800bc9d2  mov     rax, [rax]
0x1800bc9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc9da  test    r15, r15
0x1800bc9dd  jz      short loc_1800BC9EC
0x1800bc9df  mov     edx, 10h
0x1800bc9e4  mov     rcx, r15; Block
0x1800bc9e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bc9ec  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bc9f0  test    rcx, rcx
0x1800bc9f3  jz      short loc_1800BC9FB
0x1800bc9f5  call    cs:__imp_CloseHandle
0x1800bc9fb  test    r14, r14
0x1800bc9fe  jz      short loc_1800BCA09
0x1800bca00  mov     rcx, r14; pwk
0x1800bca03  call    cs:__imp_CloseThreadpoolWork
0x1800bca09  mov     eax, ebx
0x1800bca0b  mov     rcx, [rbp+var_8]
0x1800bca0f  xor     rcx, rsp; StackCookie
0x1800bca12  call    __security_check_cookie
0x1800bca17  mov     rbx, [rsp+80h+arg_18]
0x1800bca1f  add     rsp, 80h
0x1800bca26  pop     r15
0x1800bca28  pop     r14
0x1800bca2a  pop     r13
0x1800bca2c  pop     r12
0x1800bca2e  pop     rdi
0x1800bca2f  pop     rsi
0x1800bca30  pop     rbp
0x1800bca31  retn
```
