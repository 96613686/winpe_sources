# CSpWmiMethod<_SPACES_VirtualDisk_GetSecurityDescriptor>::RunMethod<CSpVirtualDisk::GetSecurityDescriptor,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800de568`
- end: `0x1800de8b6`
- name: `??$RunMethod@VGetSecurityDescriptor@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_GetSecurityDescriptor@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800e4700`

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
- `0x1800de568`
- `0x1800e095c`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de734`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800de734`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800de715`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800de715`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800de72a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800de72a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800de6fb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800de6fb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800de7d4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800de7d4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800de887`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800de887`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800de879`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800de879`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_GetSecurityDescriptor>::RunMethod<CSpVirtualDisk::GetSecurityDescriptor,16>(
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
  CSpVirtualDisk::GetSecurityDescriptor *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::GetSecurityDescriptor *)operator new(0x168u);
  SecurityDescriptor = CSpVirtualDisk::GetSecurityDescriptor::GetSecurityDescriptor(v25);
  v8 = SecurityDescriptor;
  if ( SecurityDescriptor )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)SecurityDescriptor + 8LL))(SecurityDescriptor, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpVirtualDisk::GetSecurityDescriptor *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_180331C40,
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
0x1800de568  mov     [rsp-38h+arg_18], rbx
0x1800de56d  push    rbp
0x1800de56e  push    rsi
0x1800de56f  push    rdi
0x1800de570  push    r12
0x1800de572  push    r13
0x1800de574  push    r14
0x1800de576  push    r15
0x1800de578  mov     rbp, rsp
0x1800de57b  sub     rsp, 80h
0x1800de582  mov     rax, cs:__security_cookie
0x1800de589  xor     rax, rsp
0x1800de58c  mov     [rbp+var_8], rax
0x1800de590  xor     eax, eax
0x1800de592  mov     rsi, rcx
0x1800de595  xorps   xmm0, xmm0
0x1800de598  mov     [rbp+var_10], eax
0x1800de59b  mov     ecx, 168h; Size
0x1800de5a0  mov     [rbp+var_40], eax
0x1800de5a3  movups  [rbp+var_20], xmm0
0x1800de5a7  mov     [rbp+TokenHandle], rax
0x1800de5ab  mov     r12, r8
0x1800de5ae  mov     r13, rdx
0x1800de5b1  xor     r14d, r14d
0x1800de5b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800de5b9  mov     rcx, rax; this
0x1800de5bc  mov     [rbp+var_28], rax
0x1800de5c0  call    ??0GetSecurityDescriptor@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::GetSecurityDescriptor::GetSecurityDescriptor(void)
0x1800de5c5  mov     rdi, rax
0x1800de5c8  test    rax, rax
0x1800de5cb  jnz     short loc_1800DE5D5
0x1800de5cd  lea     ebx, [rax+1Bh]
0x1800de5d0  jmp     loc_1800DE870
0x1800de5d5  mov     rax, [rax]
0x1800de5d8  mov     rdx, rsi
0x1800de5db  mov     rcx, rdi
0x1800de5de  xor     r15d, r15d
0x1800de5e1  mov     rax, [rax+8]
0x1800de5e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de5ea  lea     rcx, [rbp+var_40]
0x1800de5ee  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800de5f3  mov     [rdi+1Ch], eax
0x1800de5f6  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800de5fa  mov     ecx, [rsi+14h]; unsigned int
0x1800de5fd  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800de602  mov     eax, cs:dword_180397B68
0x1800de608  cmp     eax, 5
0x1800de60b  jbe     short loc_1800DE67B
0x1800de60d  mov     rdx, 400000000000h
0x1800de617  lea     rcx, dword_180397B68
0x1800de61e  call    _tlgKeywordOn
0x1800de623  test    al, al
0x1800de625  jz      short loc_1800DE67B
0x1800de627  mov     eax, [rbp+var_40]
0x1800de62a  lea     rdx, unk_180331C40
0x1800de631  xor     ecx, ecx
0x1800de633  cmp     [rdi+1Ch], eax
0x1800de636  movzx   eax, word ptr [rbp+var_10]
0x1800de63a  mov     word ptr [rbp+var_40], ax
0x1800de63e  setnz   cl
0x1800de641  mov     eax, [rsi+14h]
0x1800de644  mov     [rbp+var_38], eax
0x1800de647  lea     rax, [rbp+var_20]
0x1800de64b  mov     [rbp+var_28], rax
0x1800de64f  lea     rax, [rbp+var_3C]
0x1800de653  mov     [rsp+80h+var_48], rax
0x1800de658  lea     rax, [rbp+var_40]
0x1800de65c  mov     [rsp+80h+var_50], rax
0x1800de661  lea     rax, [rbp+var_38]
0x1800de665  mov     [rsp+80h+var_58], rax
0x1800de66a  lea     rax, [rbp+var_28]
0x1800de66e  mov     [rsp+80h+var_60], rax
0x1800de673  mov     [rbp+var_3C], ecx
0x1800de676  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800de67b  mov     rcx, [rsi]
0x1800de67e  test    rcx, rcx
0x1800de681  jz      loc_1800DE846
0x1800de687  mov     rax, [rcx]
0x1800de68a  test    rax, rax
0x1800de68d  jz      loc_1800DE846
0x1800de693  mov     rax, [rax+18h]
0x1800de697  lea     r8, [rdi+20h]
0x1800de69b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800de6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de6a7  mov     ebx, eax
0x1800de6a9  test    eax, eax
0x1800de6ab  jnz     loc_1800DE84B
0x1800de6b1  cmp     [rsi+10h], r14d
0x1800de6b5  jz      loc_1800DE7DF
0x1800de6bb  lea     rbx, [rdi+148h]
0x1800de6c2  mov     rcx, rbx
0x1800de6c5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800de6ca  mov     rcx, rbx; struct CSpJobMgr **
0x1800de6cd  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800de6d2  test    eax, eax
0x1800de6d4  jnz     short loc_1800DE6DE
0x1800de6d6  lea     ebx, [rax+1Ch]
0x1800de6d9  jmp     loc_1800DE84B
0x1800de6de  mov     ecx, 10h; Size
0x1800de6e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800de6e8  xor     r8d, r8d; pcbe
0x1800de6eb  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800de6f2  mov     rdx, rax; pv
0x1800de6f5  mov     r15, rax
0x1800de6f8  mov     [rax], rdi
0x1800de6fb  call    cs:__imp_CreateThreadpoolWork
0x1800de701  mov     r14, rax
0x1800de704  test    rax, rax
0x1800de707  jnz     short loc_1800DE715
0x1800de709  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800de70e  mov     ebx, eax
0x1800de710  jmp     loc_1800DE84B
0x1800de715  call    cs:__imp_GetCurrentThread
0x1800de71b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800de71f  xor     r8d, r8d; OpenAsSelf
0x1800de722  mov     rcx, rax; ThreadHandle
0x1800de725  mov     edx, 2000Ch; DesiredAccess
0x1800de72a  call    cs:__imp_OpenThreadToken
0x1800de730  test    eax, eax
0x1800de732  jnz     short loc_1800DE741
0x1800de734  call    cs:__imp_GetLastError
0x1800de73a  cmp     eax, 3F0h
0x1800de73f  jnz     short loc_1800DE709
0x1800de741  mov     rax, [rbp+TokenHandle]
0x1800de745  mov     r8, r13
0x1800de748  mov     [r15+8], rax
0x1800de74c  mov     rcx, rdi
0x1800de74f  mov     rax, [rdi]
0x1800de752  mov     rdx, [rsi+8]
0x1800de756  mov     rax, [rax+18h]
0x1800de75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de75f  mov     rax, [rdi]
0x1800de762  mov     rdx, r12
0x1800de765  mov     rcx, rdi
0x1800de768  mov     rax, [rax+28h]
0x1800de76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de771  mov     ebx, eax
0x1800de773  test    eax, eax
0x1800de775  jz      short loc_1800DE780
0x1800de777  cmp     eax, 7
0x1800de77a  jnz     loc_1800DE84B
0x1800de780  mov     rax, [rdi]
0x1800de783  mov     rdx, r12
0x1800de786  mov     rcx, rdi
0x1800de789  mov     rax, [rax+38h]
0x1800de78d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de792  mov     ebx, eax
0x1800de794  test    eax, eax
0x1800de796  jnz     loc_1800DE84B
0x1800de79c  mov     rax, [rdi+150h]
0x1800de7a3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800de7aa  jnz     short loc_1800DE7C0
0x1800de7ac  mov     rax, [rdi+158h]
0x1800de7b3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800de7ba  jz      loc_1800DE84B
0x1800de7c0  mov     rdx, r12
0x1800de7c3  mov     rcx, rdi
0x1800de7c6  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800de7cb  mov     ebx, eax
0x1800de7cd  test    eax, eax
0x1800de7cf  jnz     short loc_1800DE84B
0x1800de7d1  mov     rcx, r14; pwk
0x1800de7d4  call    cs:__imp_SubmitThreadpoolWork
0x1800de7da  jmp     loc_1800DE88D
0x1800de7df  mov     rax, [rdi]
0x1800de7e2  mov     r8, r13
0x1800de7e5  mov     rdx, [rsi+8]
0x1800de7e9  mov     rcx, rdi
0x1800de7ec  mov     rax, [rax+10h]
0x1800de7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de7f5  mov     rax, [rdi]
0x1800de7f8  mov     rdx, r12
0x1800de7fb  mov     rcx, rdi
0x1800de7fe  mov     rax, [rax+30h]
0x1800de802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de807  mov     ebx, eax
0x1800de809  test    eax, eax
0x1800de80b  jz      short loc_1800DE812
0x1800de80d  cmp     eax, 7
0x1800de810  jnz     short loc_1800DE84B
0x1800de812  mov     rax, [rdi]
0x1800de815  mov     rdx, r12
0x1800de818  mov     rcx, rdi
0x1800de81b  mov     rax, [rax+28h]
0x1800de81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de824  mov     ebx, eax
0x1800de826  test    eax, eax
0x1800de828  jz      short loc_1800DE82F
0x1800de82a  cmp     eax, 7
0x1800de82d  jnz     short loc_1800DE84B
0x1800de82f  mov     rax, [rdi]
0x1800de832  mov     rdx, r12
0x1800de835  mov     rcx, rdi
0x1800de838  mov     rax, [rax+38h]
0x1800de83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de841  jmp     loc_1800DE70E
0x1800de846  mov     ebx, 4
0x1800de84b  mov     rax, [rdi]
0x1800de84e  mov     edx, 1
0x1800de853  mov     rcx, rdi
0x1800de856  mov     rax, [rax]
0x1800de859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de85e  test    r15, r15
0x1800de861  jz      short loc_1800DE870
0x1800de863  mov     edx, 10h
0x1800de868  mov     rcx, r15; Block
0x1800de86b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800de870  mov     rcx, [rbp+TokenHandle]; hObject
0x1800de874  test    rcx, rcx
0x1800de877  jz      short loc_1800DE87F
0x1800de879  call    cs:__imp_CloseHandle
0x1800de87f  test    r14, r14
0x1800de882  jz      short loc_1800DE88D
0x1800de884  mov     rcx, r14; pwk
0x1800de887  call    cs:__imp_CloseThreadpoolWork
0x1800de88d  mov     eax, ebx
0x1800de88f  mov     rcx, [rbp+var_8]
0x1800de893  xor     rcx, rsp; StackCookie
0x1800de896  call    __security_check_cookie
0x1800de89b  mov     rbx, [rsp+80h+arg_18]
0x1800de8a3  add     rsp, 80h
0x1800de8aa  pop     r15
0x1800de8ac  pop     r14
0x1800de8ae  pop     r13
0x1800de8b0  pop     r12
0x1800de8b2  pop     rdi
0x1800de8b3  pop     rsi
0x1800de8b4  pop     rbp
0x1800de8b5  retn
```
