# CSpWmiMethod<_SPACES_PhysicalDisk_Reset>::RunMethod<CSpPhysicalDisk::Reset,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800f24fc`
- end: `0x1800f2879`
- name: `??$RunMethod@VReset@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_Reset@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800f77c0`

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
- `0x1800f24fc`
- `0x1800f3cf8`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f26da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f26da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f26af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f26af`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f26ca`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f26ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f268f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f268f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f2784`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f2784`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f2843`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f2843`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f282f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f282f`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_Reset>::RunMethod<CSpPhysicalDisk::Reset,4>(
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
  CSpPhysicalDisk::Reset *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::Reset *)operator new(0x160u);
  v7 = CSpPhysicalDisk::Reset::Reset(v25);
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
      v25 = (CSpPhysicalDisk::Reset *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_18033CF7C,
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
0x1800f24fc  mov     [rsp-38h+arg_18], rbx
0x1800f2501  push    rbp
0x1800f2502  push    rsi
0x1800f2503  push    rdi
0x1800f2504  push    r12
0x1800f2506  push    r13
0x1800f2508  push    r14
0x1800f250a  push    r15
0x1800f250c  mov     rbp, rsp
0x1800f250f  sub     rsp, 80h
0x1800f2516  mov     rax, cs:__security_cookie
0x1800f251d  xor     rax, rsp
0x1800f2520  mov     [rbp+var_8], rax
0x1800f2524  xor     eax, eax
0x1800f2526  mov     rsi, rcx
0x1800f2529  xorps   xmm0, xmm0
0x1800f252c  mov     [rbp+var_10], eax
0x1800f252f  mov     ecx, 160h; Size
0x1800f2534  mov     [rbp+var_40], eax
0x1800f2537  movups  [rbp+var_20], xmm0
0x1800f253b  mov     [rbp+TokenHandle], rax
0x1800f253f  mov     r12, r8
0x1800f2542  mov     r13, rdx
0x1800f2545  xor     r14d, r14d
0x1800f2548  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f254d  mov     rcx, rax; this
0x1800f2550  mov     [rbp+var_28], rax
0x1800f2554  call    ??0Reset@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::Reset::Reset(void)
0x1800f2559  mov     rdi, rax
0x1800f255c  test    rax, rax
0x1800f255f  jnz     short loc_1800F2569
0x1800f2561  lea     ebx, [rax+1Bh]
0x1800f2564  jmp     loc_1800F2826
0x1800f2569  mov     rax, [rax]
0x1800f256c  mov     rdx, rsi
0x1800f256f  mov     rcx, rdi
0x1800f2572  xor     r15d, r15d
0x1800f2575  mov     rax, [rax+8]
0x1800f2579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f257e  lea     rcx, [rbp+var_40]
0x1800f2582  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800f2587  mov     [rdi+1Ch], eax
0x1800f258a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800f258e  mov     ecx, [rsi+14h]; unsigned int
0x1800f2591  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800f2596  mov     eax, cs:dword_18039EB68
0x1800f259c  cmp     eax, 5
0x1800f259f  jbe     short loc_1800F260F
0x1800f25a1  mov     rdx, 400000000000h
0x1800f25ab  lea     rcx, dword_18039EB68
0x1800f25b2  call    _tlgKeywordOn
0x1800f25b7  test    al, al
0x1800f25b9  jz      short loc_1800F260F
0x1800f25bb  mov     eax, [rbp+var_40]
0x1800f25be  lea     rdx, dword_18033CF7C
0x1800f25c5  xor     ecx, ecx
0x1800f25c7  cmp     [rdi+1Ch], eax
0x1800f25ca  movzx   eax, word ptr [rbp+var_10]
0x1800f25ce  mov     word ptr [rbp+var_40], ax
0x1800f25d2  setnz   cl
0x1800f25d5  mov     eax, [rsi+14h]
0x1800f25d8  mov     [rbp+var_38], eax
0x1800f25db  lea     rax, [rbp+var_20]
0x1800f25df  mov     [rbp+var_28], rax
0x1800f25e3  lea     rax, [rbp+var_3C]
0x1800f25e7  mov     [rsp+80h+var_48], rax
0x1800f25ec  lea     rax, [rbp+var_40]
0x1800f25f0  mov     [rsp+80h+var_50], rax
0x1800f25f5  lea     rax, [rbp+var_38]
0x1800f25f9  mov     [rsp+80h+var_58], rax
0x1800f25fe  lea     rax, [rbp+var_28]
0x1800f2602  mov     [rsp+80h+var_60], rax
0x1800f2607  mov     [rbp+var_3C], ecx
0x1800f260a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800f260f  mov     rcx, [rsi]
0x1800f2612  test    rcx, rcx
0x1800f2615  jz      loc_1800F27FC
0x1800f261b  mov     rax, [rcx]
0x1800f261e  test    rax, rax
0x1800f2621  jz      loc_1800F27FC
0x1800f2627  mov     rax, [rax+18h]
0x1800f262b  lea     r8, [rdi+20h]
0x1800f262f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800f2636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f263b  mov     ebx, eax
0x1800f263d  test    eax, eax
0x1800f263f  jnz     loc_1800F2801
0x1800f2645  cmp     [rsi+10h], r14d
0x1800f2649  jz      loc_1800F2795
0x1800f264f  lea     rbx, [rdi+148h]
0x1800f2656  mov     rcx, rbx
0x1800f2659  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800f265e  mov     rcx, rbx; struct CSpJobMgr **
0x1800f2661  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800f2666  test    eax, eax
0x1800f2668  jnz     short loc_1800F2672
0x1800f266a  lea     ebx, [rax+1Ch]
0x1800f266d  jmp     loc_1800F2801
0x1800f2672  mov     ecx, 10h; Size
0x1800f2677  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f267c  xor     r8d, r8d; pcbe
0x1800f267f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f2686  mov     rdx, rax; pv
0x1800f2689  mov     r15, rax
0x1800f268c  mov     [rax], rdi
0x1800f268f  call    cs:__imp_CreateThreadpoolWork
0x1800f2696  nop     dword ptr [rax+rax+00h]
0x1800f269b  mov     r14, rax
0x1800f269e  test    rax, rax
0x1800f26a1  jnz     short loc_1800F26AF
0x1800f26a3  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800f26a8  mov     ebx, eax
0x1800f26aa  jmp     loc_1800F2801
0x1800f26af  call    cs:__imp_GetCurrentThread
0x1800f26b6  nop     dword ptr [rax+rax+00h]
0x1800f26bb  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f26bf  xor     r8d, r8d; OpenAsSelf
0x1800f26c2  mov     rcx, rax; ThreadHandle
0x1800f26c5  mov     edx, 2000Ch; DesiredAccess
0x1800f26ca  call    cs:__imp_OpenThreadToken
0x1800f26d1  nop     dword ptr [rax+rax+00h]
0x1800f26d6  test    eax, eax
0x1800f26d8  jnz     short loc_1800F26ED
0x1800f26da  call    cs:__imp_GetLastError
0x1800f26e1  nop     dword ptr [rax+rax+00h]
0x1800f26e6  cmp     eax, 3F0h
0x1800f26eb  jnz     short loc_1800F26A3
0x1800f26ed  mov     rax, [rbp+TokenHandle]
0x1800f26f1  mov     r8, r13
0x1800f26f4  mov     [r15+8], rax
0x1800f26f8  mov     rcx, rdi
0x1800f26fb  mov     rax, [rdi]
0x1800f26fe  mov     rdx, [rsi+8]
0x1800f2702  mov     rax, [rax+18h]
0x1800f2706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f270b  mov     rax, [rdi]
0x1800f270e  mov     rdx, r12
0x1800f2711  mov     rcx, rdi
0x1800f2714  mov     rax, [rax+28h]
0x1800f2718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f271d  mov     ebx, eax
0x1800f271f  test    eax, eax
0x1800f2721  jz      short loc_1800F272C
0x1800f2723  cmp     eax, 7
0x1800f2726  jnz     loc_1800F2801
0x1800f272c  mov     rax, [rdi]
0x1800f272f  mov     rdx, r12
0x1800f2732  mov     rcx, rdi
0x1800f2735  mov     rax, [rax+38h]
0x1800f2739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f273e  mov     ebx, eax
0x1800f2740  test    eax, eax
0x1800f2742  jnz     loc_1800F2801
0x1800f2748  mov     rax, [rdi+150h]
0x1800f274f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800f2756  jnz     short loc_1800F276C
0x1800f2758  mov     rax, [rdi+158h]
0x1800f275f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800f2766  jz      loc_1800F2801
0x1800f276c  mov     rdx, r12
0x1800f276f  mov     rcx, rdi
0x1800f2772  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800f2777  mov     ebx, eax
0x1800f2779  test    eax, eax
0x1800f277b  jnz     loc_1800F2801
0x1800f2781  mov     rcx, r14; pwk
0x1800f2784  call    cs:__imp_SubmitThreadpoolWork
0x1800f278b  nop     dword ptr [rax+rax+00h]
0x1800f2790  jmp     loc_1800F284F
0x1800f2795  mov     rax, [rdi]
0x1800f2798  mov     r8, r13
0x1800f279b  mov     rdx, [rsi+8]
0x1800f279f  mov     rcx, rdi
0x1800f27a2  mov     rax, [rax+10h]
0x1800f27a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f27ab  mov     rax, [rdi]
0x1800f27ae  mov     rdx, r12
0x1800f27b1  mov     rcx, rdi
0x1800f27b4  mov     rax, [rax+30h]
0x1800f27b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f27bd  mov     ebx, eax
0x1800f27bf  test    eax, eax
0x1800f27c1  jz      short loc_1800F27C8
0x1800f27c3  cmp     eax, 7
0x1800f27c6  jnz     short loc_1800F2801
0x1800f27c8  mov     rax, [rdi]
0x1800f27cb  mov     rdx, r12
0x1800f27ce  mov     rcx, rdi
0x1800f27d1  mov     rax, [rax+28h]
0x1800f27d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f27da  mov     ebx, eax
0x1800f27dc  test    eax, eax
0x1800f27de  jz      short loc_1800F27E5
0x1800f27e0  cmp     eax, 7
0x1800f27e3  jnz     short loc_1800F2801
0x1800f27e5  mov     rax, [rdi]
0x1800f27e8  mov     rdx, r12
0x1800f27eb  mov     rcx, rdi
0x1800f27ee  mov     rax, [rax+38h]
0x1800f27f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f27f7  jmp     loc_1800F26A8
0x1800f27fc  mov     ebx, 4
0x1800f2801  mov     rax, [rdi]
0x1800f2804  mov     edx, 1
0x1800f2809  mov     rcx, rdi
0x1800f280c  mov     rax, [rax]
0x1800f280f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2814  test    r15, r15
0x1800f2817  jz      short loc_1800F2826
0x1800f2819  mov     edx, 10h
0x1800f281e  mov     rcx, r15; Block
0x1800f2821  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f2826  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f282a  test    rcx, rcx
0x1800f282d  jz      short loc_1800F283B
0x1800f282f  call    cs:__imp_CloseHandle
0x1800f2836  nop     dword ptr [rax+rax+00h]
0x1800f283b  test    r14, r14
0x1800f283e  jz      short loc_1800F284F
0x1800f2840  mov     rcx, r14; pwk
0x1800f2843  call    cs:__imp_CloseThreadpoolWork
0x1800f284a  nop     dword ptr [rax+rax+00h]
0x1800f284f  mov     eax, ebx
0x1800f2851  mov     rcx, [rbp+var_8]
0x1800f2855  xor     rcx, rsp; StackCookie
0x1800f2858  call    __security_check_cookie
0x1800f285d  mov     rbx, [rsp+80h+arg_18]
0x1800f2865  add     rsp, 80h
0x1800f286c  pop     r15
0x1800f286e  pop     r14
0x1800f2870  pop     r13
0x1800f2872  pop     r12
0x1800f2874  pop     rdi
0x1800f2875  pop     rsi
0x1800f2876  pop     rbp
0x1800f2877  retn
```
