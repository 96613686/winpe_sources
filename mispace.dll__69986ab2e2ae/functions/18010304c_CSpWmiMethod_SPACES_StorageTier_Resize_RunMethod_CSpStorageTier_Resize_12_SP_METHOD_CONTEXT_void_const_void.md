# CSpWmiMethod<_SPACES_StorageTier_Resize>::RunMethod<CSpStorageTier::Resize,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18010304c`
- end: `0x1801033c9`
- name: `??$RunMethod@VResize@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_Resize@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180105a90`

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
- `0x18010304c`
- `0x1801040a4`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010322a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010322a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801031ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801031ff`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010321a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010321a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801031df`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801031df`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801032d4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801032d4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180103393`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180103393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010337f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010337f`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_Resize>::RunMethod<CSpStorageTier::Resize,12>(
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
  CSpStorageTier::Resize *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::Resize *)operator new(0x160u);
  v7 = CSpStorageTier::Resize::Resize(v25);
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
      v25 = (CSpStorageTier::Resize *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_1803412E4,
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
0x18010304c  mov     [rsp-38h+arg_18], rbx
0x180103051  push    rbp
0x180103052  push    rsi
0x180103053  push    rdi
0x180103054  push    r12
0x180103056  push    r13
0x180103058  push    r14
0x18010305a  push    r15
0x18010305c  mov     rbp, rsp
0x18010305f  sub     rsp, 80h
0x180103066  mov     rax, cs:__security_cookie
0x18010306d  xor     rax, rsp
0x180103070  mov     [rbp+var_8], rax
0x180103074  xor     eax, eax
0x180103076  mov     rsi, rcx
0x180103079  xorps   xmm0, xmm0
0x18010307c  mov     [rbp+var_10], eax
0x18010307f  mov     ecx, 160h; Size
0x180103084  mov     [rbp+var_40], eax
0x180103087  movups  [rbp+var_20], xmm0
0x18010308b  mov     [rbp+TokenHandle], rax
0x18010308f  mov     r12, r8
0x180103092  mov     r13, rdx
0x180103095  xor     r14d, r14d
0x180103098  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18010309d  mov     rcx, rax; this
0x1801030a0  mov     [rbp+var_28], rax
0x1801030a4  call    ??0Resize@CSpStorageTier@@QEAA@XZ; CSpStorageTier::Resize::Resize(void)
0x1801030a9  mov     rdi, rax
0x1801030ac  test    rax, rax
0x1801030af  jnz     short loc_1801030B9
0x1801030b1  lea     ebx, [rax+1Bh]
0x1801030b4  jmp     loc_180103376
0x1801030b9  mov     rax, [rax]
0x1801030bc  mov     rdx, rsi
0x1801030bf  mov     rcx, rdi
0x1801030c2  xor     r15d, r15d
0x1801030c5  mov     rax, [rax+8]
0x1801030c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801030ce  lea     rcx, [rbp+var_40]
0x1801030d2  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1801030d7  mov     [rdi+1Ch], eax
0x1801030da  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1801030de  mov     ecx, [rsi+14h]; unsigned int
0x1801030e1  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1801030e6  mov     eax, cs:dword_18039EB68
0x1801030ec  cmp     eax, 5
0x1801030ef  jbe     short loc_18010315F
0x1801030f1  mov     rdx, 400000000000h
0x1801030fb  lea     rcx, dword_18039EB68
0x180103102  call    _tlgKeywordOn
0x180103107  test    al, al
0x180103109  jz      short loc_18010315F
0x18010310b  mov     eax, [rbp+var_40]
0x18010310e  lea     rdx, dword_1803412E4
0x180103115  xor     ecx, ecx
0x180103117  cmp     [rdi+1Ch], eax
0x18010311a  movzx   eax, word ptr [rbp+var_10]
0x18010311e  mov     word ptr [rbp+var_40], ax
0x180103122  setnz   cl
0x180103125  mov     eax, [rsi+14h]
0x180103128  mov     [rbp+var_38], eax
0x18010312b  lea     rax, [rbp+var_20]
0x18010312f  mov     [rbp+var_28], rax
0x180103133  lea     rax, [rbp+var_3C]
0x180103137  mov     [rsp+80h+var_48], rax
0x18010313c  lea     rax, [rbp+var_40]
0x180103140  mov     [rsp+80h+var_50], rax
0x180103145  lea     rax, [rbp+var_38]
0x180103149  mov     [rsp+80h+var_58], rax
0x18010314e  lea     rax, [rbp+var_28]
0x180103152  mov     [rsp+80h+var_60], rax
0x180103157  mov     [rbp+var_3C], ecx
0x18010315a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18010315f  mov     rcx, [rsi]
0x180103162  test    rcx, rcx
0x180103165  jz      loc_18010334C
0x18010316b  mov     rax, [rcx]
0x18010316e  test    rax, rax
0x180103171  jz      loc_18010334C
0x180103177  mov     rax, [rax+18h]
0x18010317b  lea     r8, [rdi+20h]
0x18010317f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180103186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010318b  mov     ebx, eax
0x18010318d  test    eax, eax
0x18010318f  jnz     loc_180103351
0x180103195  cmp     [rsi+10h], r14d
0x180103199  jz      loc_1801032E5
0x18010319f  lea     rbx, [rdi+148h]
0x1801031a6  mov     rcx, rbx
0x1801031a9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1801031ae  mov     rcx, rbx; struct CSpJobMgr **
0x1801031b1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1801031b6  test    eax, eax
0x1801031b8  jnz     short loc_1801031C2
0x1801031ba  lea     ebx, [rax+1Ch]
0x1801031bd  jmp     loc_180103351
0x1801031c2  mov     ecx, 10h; Size
0x1801031c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801031cc  xor     r8d, r8d; pcbe
0x1801031cf  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1801031d6  mov     rdx, rax; pv
0x1801031d9  mov     r15, rax
0x1801031dc  mov     [rax], rdi
0x1801031df  call    cs:__imp_CreateThreadpoolWork
0x1801031e6  nop     dword ptr [rax+rax+00h]
0x1801031eb  mov     r14, rax
0x1801031ee  test    rax, rax
0x1801031f1  jnz     short loc_1801031FF
0x1801031f3  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1801031f8  mov     ebx, eax
0x1801031fa  jmp     loc_180103351
0x1801031ff  call    cs:__imp_GetCurrentThread
0x180103206  nop     dword ptr [rax+rax+00h]
0x18010320b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18010320f  xor     r8d, r8d; OpenAsSelf
0x180103212  mov     rcx, rax; ThreadHandle
0x180103215  mov     edx, 2000Ch; DesiredAccess
0x18010321a  call    cs:__imp_OpenThreadToken
0x180103221  nop     dword ptr [rax+rax+00h]
0x180103226  test    eax, eax
0x180103228  jnz     short loc_18010323D
0x18010322a  call    cs:__imp_GetLastError
0x180103231  nop     dword ptr [rax+rax+00h]
0x180103236  cmp     eax, 3F0h
0x18010323b  jnz     short loc_1801031F3
0x18010323d  mov     rax, [rbp+TokenHandle]
0x180103241  mov     r8, r13
0x180103244  mov     [r15+8], rax
0x180103248  mov     rcx, rdi
0x18010324b  mov     rax, [rdi]
0x18010324e  mov     rdx, [rsi+8]
0x180103252  mov     rax, [rax+18h]
0x180103256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010325b  mov     rax, [rdi]
0x18010325e  mov     rdx, r12
0x180103261  mov     rcx, rdi
0x180103264  mov     rax, [rax+28h]
0x180103268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010326d  mov     ebx, eax
0x18010326f  test    eax, eax
0x180103271  jz      short loc_18010327C
0x180103273  cmp     eax, 7
0x180103276  jnz     loc_180103351
0x18010327c  mov     rax, [rdi]
0x18010327f  mov     rdx, r12
0x180103282  mov     rcx, rdi
0x180103285  mov     rax, [rax+38h]
0x180103289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010328e  mov     ebx, eax
0x180103290  test    eax, eax
0x180103292  jnz     loc_180103351
0x180103298  mov     rax, [rdi+150h]
0x18010329f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1801032a6  jnz     short loc_1801032BC
0x1801032a8  mov     rax, [rdi+158h]
0x1801032af  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1801032b6  jz      loc_180103351
0x1801032bc  mov     rdx, r12
0x1801032bf  mov     rcx, rdi
0x1801032c2  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1801032c7  mov     ebx, eax
0x1801032c9  test    eax, eax
0x1801032cb  jnz     loc_180103351
0x1801032d1  mov     rcx, r14; pwk
0x1801032d4  call    cs:__imp_SubmitThreadpoolWork
0x1801032db  nop     dword ptr [rax+rax+00h]
0x1801032e0  jmp     loc_18010339F
0x1801032e5  mov     rax, [rdi]
0x1801032e8  mov     r8, r13
0x1801032eb  mov     rdx, [rsi+8]
0x1801032ef  mov     rcx, rdi
0x1801032f2  mov     rax, [rax+10h]
0x1801032f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801032fb  mov     rax, [rdi]
0x1801032fe  mov     rdx, r12
0x180103301  mov     rcx, rdi
0x180103304  mov     rax, [rax+30h]
0x180103308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010330d  mov     ebx, eax
0x18010330f  test    eax, eax
0x180103311  jz      short loc_180103318
0x180103313  cmp     eax, 7
0x180103316  jnz     short loc_180103351
0x180103318  mov     rax, [rdi]
0x18010331b  mov     rdx, r12
0x18010331e  mov     rcx, rdi
0x180103321  mov     rax, [rax+28h]
0x180103325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010332a  mov     ebx, eax
0x18010332c  test    eax, eax
0x18010332e  jz      short loc_180103335
0x180103330  cmp     eax, 7
0x180103333  jnz     short loc_180103351
0x180103335  mov     rax, [rdi]
0x180103338  mov     rdx, r12
0x18010333b  mov     rcx, rdi
0x18010333e  mov     rax, [rax+38h]
0x180103342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103347  jmp     loc_1801031F8
0x18010334c  mov     ebx, 4
0x180103351  mov     rax, [rdi]
0x180103354  mov     edx, 1
0x180103359  mov     rcx, rdi
0x18010335c  mov     rax, [rax]
0x18010335f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103364  test    r15, r15
0x180103367  jz      short loc_180103376
0x180103369  mov     edx, 10h
0x18010336e  mov     rcx, r15; Block
0x180103371  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180103376  mov     rcx, [rbp+TokenHandle]; hObject
0x18010337a  test    rcx, rcx
0x18010337d  jz      short loc_18010338B
0x18010337f  call    cs:__imp_CloseHandle
0x180103386  nop     dword ptr [rax+rax+00h]
0x18010338b  test    r14, r14
0x18010338e  jz      short loc_18010339F
0x180103390  mov     rcx, r14; pwk
0x180103393  call    cs:__imp_CloseThreadpoolWork
0x18010339a  nop     dword ptr [rax+rax+00h]
0x18010339f  mov     eax, ebx
0x1801033a1  mov     rcx, [rbp+var_8]
0x1801033a5  xor     rcx, rsp; StackCookie
0x1801033a8  call    __security_check_cookie
0x1801033ad  mov     rbx, [rsp+80h+arg_18]
0x1801033b5  add     rsp, 80h
0x1801033bc  pop     r15
0x1801033be  pop     r14
0x1801033c0  pop     r13
0x1801033c2  pop     r12
0x1801033c4  pop     rdi
0x1801033c5  pop     rsi
0x1801033c6  pop     rbp
0x1801033c7  retn
```
