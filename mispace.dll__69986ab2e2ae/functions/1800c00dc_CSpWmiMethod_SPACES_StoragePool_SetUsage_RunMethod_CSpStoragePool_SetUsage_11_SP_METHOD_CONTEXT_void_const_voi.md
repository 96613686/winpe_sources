# CSpWmiMethod<_SPACES_StoragePool_SetUsage>::RunMethod<CSpStoragePool::SetUsage,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800c00dc`
- end: `0x1800c0459`
- name: `??$RunMethod@VSetUsage@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_SetUsage@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800c00dc`
- `0x1800c13b0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c02ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c02ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c028f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c028f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c02aa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c02aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800c026f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800c026f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800c0364`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800c0364`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800c0423`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800c0423`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c040f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c040f`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_SetUsage>::RunMethod<CSpStoragePool::SetUsage,11>(
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
  CSpStoragePool::SetUsage *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::SetUsage *)operator new(0x160u);
  v7 = CSpStoragePool::SetUsage::SetUsage(v25);
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
      v25 = (CSpStoragePool::SetUsage *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_18032EB84,
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
0x1800c00dc  mov     [rsp-38h+arg_18], rbx
0x1800c00e1  push    rbp
0x1800c00e2  push    rsi
0x1800c00e3  push    rdi
0x1800c00e4  push    r12
0x1800c00e6  push    r13
0x1800c00e8  push    r14
0x1800c00ea  push    r15
0x1800c00ec  mov     rbp, rsp
0x1800c00ef  sub     rsp, 80h
0x1800c00f6  mov     rax, cs:__security_cookie
0x1800c00fd  xor     rax, rsp
0x1800c0100  mov     [rbp+var_8], rax
0x1800c0104  xor     eax, eax
0x1800c0106  mov     rsi, rcx
0x1800c0109  xorps   xmm0, xmm0
0x1800c010c  mov     [rbp+var_10], eax
0x1800c010f  mov     ecx, 160h; Size
0x1800c0114  mov     [rbp+var_40], eax
0x1800c0117  movups  [rbp+var_20], xmm0
0x1800c011b  mov     [rbp+TokenHandle], rax
0x1800c011f  mov     r12, r8
0x1800c0122  mov     r13, rdx
0x1800c0125  xor     r14d, r14d
0x1800c0128  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c012d  mov     rcx, rax; this
0x1800c0130  mov     [rbp+var_28], rax
0x1800c0134  call    ??0SetUsage@CSpStoragePool@@QEAA@XZ; CSpStoragePool::SetUsage::SetUsage(void)
0x1800c0139  mov     rdi, rax
0x1800c013c  test    rax, rax
0x1800c013f  jnz     short loc_1800C0149
0x1800c0141  lea     ebx, [rax+1Bh]
0x1800c0144  jmp     loc_1800C0406
0x1800c0149  mov     rax, [rax]
0x1800c014c  mov     rdx, rsi
0x1800c014f  mov     rcx, rdi
0x1800c0152  xor     r15d, r15d
0x1800c0155  mov     rax, [rax+8]
0x1800c0159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c015e  lea     rcx, [rbp+var_40]
0x1800c0162  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800c0167  mov     [rdi+1Ch], eax
0x1800c016a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800c016e  mov     ecx, [rsi+14h]; unsigned int
0x1800c0171  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800c0176  mov     eax, cs:dword_18039EB68
0x1800c017c  cmp     eax, 5
0x1800c017f  jbe     short loc_1800C01EF
0x1800c0181  mov     rdx, 400000000000h
0x1800c018b  lea     rcx, dword_18039EB68
0x1800c0192  call    _tlgKeywordOn
0x1800c0197  test    al, al
0x1800c0199  jz      short loc_1800C01EF
0x1800c019b  mov     eax, [rbp+var_40]
0x1800c019e  lea     rdx, dword_18032EB84
0x1800c01a5  xor     ecx, ecx
0x1800c01a7  cmp     [rdi+1Ch], eax
0x1800c01aa  movzx   eax, word ptr [rbp+var_10]
0x1800c01ae  mov     word ptr [rbp+var_40], ax
0x1800c01b2  setnz   cl
0x1800c01b5  mov     eax, [rsi+14h]
0x1800c01b8  mov     [rbp+var_38], eax
0x1800c01bb  lea     rax, [rbp+var_20]
0x1800c01bf  mov     [rbp+var_28], rax
0x1800c01c3  lea     rax, [rbp+var_3C]
0x1800c01c7  mov     [rsp+80h+var_48], rax
0x1800c01cc  lea     rax, [rbp+var_40]
0x1800c01d0  mov     [rsp+80h+var_50], rax
0x1800c01d5  lea     rax, [rbp+var_38]
0x1800c01d9  mov     [rsp+80h+var_58], rax
0x1800c01de  lea     rax, [rbp+var_28]
0x1800c01e2  mov     [rsp+80h+var_60], rax
0x1800c01e7  mov     [rbp+var_3C], ecx
0x1800c01ea  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800c01ef  mov     rcx, [rsi]
0x1800c01f2  test    rcx, rcx
0x1800c01f5  jz      loc_1800C03DC
0x1800c01fb  mov     rax, [rcx]
0x1800c01fe  test    rax, rax
0x1800c0201  jz      loc_1800C03DC
0x1800c0207  mov     rax, [rax+18h]
0x1800c020b  lea     r8, [rdi+20h]
0x1800c020f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800c0216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c021b  mov     ebx, eax
0x1800c021d  test    eax, eax
0x1800c021f  jnz     loc_1800C03E1
0x1800c0225  cmp     [rsi+10h], r14d
0x1800c0229  jz      loc_1800C0375
0x1800c022f  lea     rbx, [rdi+148h]
0x1800c0236  mov     rcx, rbx
0x1800c0239  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800c023e  mov     rcx, rbx; struct CSpJobMgr **
0x1800c0241  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800c0246  test    eax, eax
0x1800c0248  jnz     short loc_1800C0252
0x1800c024a  lea     ebx, [rax+1Ch]
0x1800c024d  jmp     loc_1800C03E1
0x1800c0252  mov     ecx, 10h; Size
0x1800c0257  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c025c  xor     r8d, r8d; pcbe
0x1800c025f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800c0266  mov     rdx, rax; pv
0x1800c0269  mov     r15, rax
0x1800c026c  mov     [rax], rdi
0x1800c026f  call    cs:__imp_CreateThreadpoolWork
0x1800c0276  nop     dword ptr [rax+rax+00h]
0x1800c027b  mov     r14, rax
0x1800c027e  test    rax, rax
0x1800c0281  jnz     short loc_1800C028F
0x1800c0283  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800c0288  mov     ebx, eax
0x1800c028a  jmp     loc_1800C03E1
0x1800c028f  call    cs:__imp_GetCurrentThread
0x1800c0296  nop     dword ptr [rax+rax+00h]
0x1800c029b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800c029f  xor     r8d, r8d; OpenAsSelf
0x1800c02a2  mov     rcx, rax; ThreadHandle
0x1800c02a5  mov     edx, 2000Ch; DesiredAccess
0x1800c02aa  call    cs:__imp_OpenThreadToken
0x1800c02b1  nop     dword ptr [rax+rax+00h]
0x1800c02b6  test    eax, eax
0x1800c02b8  jnz     short loc_1800C02CD
0x1800c02ba  call    cs:__imp_GetLastError
0x1800c02c1  nop     dword ptr [rax+rax+00h]
0x1800c02c6  cmp     eax, 3F0h
0x1800c02cb  jnz     short loc_1800C0283
0x1800c02cd  mov     rax, [rbp+TokenHandle]
0x1800c02d1  mov     r8, r13
0x1800c02d4  mov     [r15+8], rax
0x1800c02d8  mov     rcx, rdi
0x1800c02db  mov     rax, [rdi]
0x1800c02de  mov     rdx, [rsi+8]
0x1800c02e2  mov     rax, [rax+18h]
0x1800c02e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c02eb  mov     rax, [rdi]
0x1800c02ee  mov     rdx, r12
0x1800c02f1  mov     rcx, rdi
0x1800c02f4  mov     rax, [rax+28h]
0x1800c02f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c02fd  mov     ebx, eax
0x1800c02ff  test    eax, eax
0x1800c0301  jz      short loc_1800C030C
0x1800c0303  cmp     eax, 7
0x1800c0306  jnz     loc_1800C03E1
0x1800c030c  mov     rax, [rdi]
0x1800c030f  mov     rdx, r12
0x1800c0312  mov     rcx, rdi
0x1800c0315  mov     rax, [rax+38h]
0x1800c0319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c031e  mov     ebx, eax
0x1800c0320  test    eax, eax
0x1800c0322  jnz     loc_1800C03E1
0x1800c0328  mov     rax, [rdi+150h]
0x1800c032f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800c0336  jnz     short loc_1800C034C
0x1800c0338  mov     rax, [rdi+158h]
0x1800c033f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800c0346  jz      loc_1800C03E1
0x1800c034c  mov     rdx, r12
0x1800c034f  mov     rcx, rdi
0x1800c0352  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800c0357  mov     ebx, eax
0x1800c0359  test    eax, eax
0x1800c035b  jnz     loc_1800C03E1
0x1800c0361  mov     rcx, r14; pwk
0x1800c0364  call    cs:__imp_SubmitThreadpoolWork
0x1800c036b  nop     dword ptr [rax+rax+00h]
0x1800c0370  jmp     loc_1800C042F
0x1800c0375  mov     rax, [rdi]
0x1800c0378  mov     r8, r13
0x1800c037b  mov     rdx, [rsi+8]
0x1800c037f  mov     rcx, rdi
0x1800c0382  mov     rax, [rax+10h]
0x1800c0386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c038b  mov     rax, [rdi]
0x1800c038e  mov     rdx, r12
0x1800c0391  mov     rcx, rdi
0x1800c0394  mov     rax, [rax+30h]
0x1800c0398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c039d  mov     ebx, eax
0x1800c039f  test    eax, eax
0x1800c03a1  jz      short loc_1800C03A8
0x1800c03a3  cmp     eax, 7
0x1800c03a6  jnz     short loc_1800C03E1
0x1800c03a8  mov     rax, [rdi]
0x1800c03ab  mov     rdx, r12
0x1800c03ae  mov     rcx, rdi
0x1800c03b1  mov     rax, [rax+28h]
0x1800c03b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c03ba  mov     ebx, eax
0x1800c03bc  test    eax, eax
0x1800c03be  jz      short loc_1800C03C5
0x1800c03c0  cmp     eax, 7
0x1800c03c3  jnz     short loc_1800C03E1
0x1800c03c5  mov     rax, [rdi]
0x1800c03c8  mov     rdx, r12
0x1800c03cb  mov     rcx, rdi
0x1800c03ce  mov     rax, [rax+38h]
0x1800c03d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c03d7  jmp     loc_1800C0288
0x1800c03dc  mov     ebx, 4
0x1800c03e1  mov     rax, [rdi]
0x1800c03e4  mov     edx, 1
0x1800c03e9  mov     rcx, rdi
0x1800c03ec  mov     rax, [rax]
0x1800c03ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c03f4  test    r15, r15
0x1800c03f7  jz      short loc_1800C0406
0x1800c03f9  mov     edx, 10h
0x1800c03fe  mov     rcx, r15; Block
0x1800c0401  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800c0406  mov     rcx, [rbp+TokenHandle]; hObject
0x1800c040a  test    rcx, rcx
0x1800c040d  jz      short loc_1800C041B
0x1800c040f  call    cs:__imp_CloseHandle
0x1800c0416  nop     dword ptr [rax+rax+00h]
0x1800c041b  test    r14, r14
0x1800c041e  jz      short loc_1800C042F
0x1800c0420  mov     rcx, r14; pwk
0x1800c0423  call    cs:__imp_CloseThreadpoolWork
0x1800c042a  nop     dword ptr [rax+rax+00h]
0x1800c042f  mov     eax, ebx
0x1800c0431  mov     rcx, [rbp+var_8]
0x1800c0435  xor     rcx, rsp; StackCookie
0x1800c0438  call    __security_check_cookie
0x1800c043d  mov     rbx, [rsp+80h+arg_18]
0x1800c0445  add     rsp, 80h
0x1800c044c  pop     r15
0x1800c044e  pop     r14
0x1800c0450  pop     r13
0x1800c0452  pop     r12
0x1800c0454  pop     rdi
0x1800c0455  pop     rsi
0x1800c0456  pop     rbp
0x1800c0457  retn
```
