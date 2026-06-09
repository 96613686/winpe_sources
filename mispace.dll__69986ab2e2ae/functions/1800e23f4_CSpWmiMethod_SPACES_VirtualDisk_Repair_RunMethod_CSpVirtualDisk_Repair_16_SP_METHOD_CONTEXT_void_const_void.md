# CSpWmiMethod<_SPACES_VirtualDisk_Repair>::RunMethod<CSpVirtualDisk::Repair,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e23f4`
- end: `0x1800e2771`
- name: `??$RunMethod@VRepair@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_Repair@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x1800e7d60`

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
- `0x1800e23f4`
- `0x1800e40a4`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e25d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e25d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e25a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e25a7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e25c2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e25c2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e2587`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e2587`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e267c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e267c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e273b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e273b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e2727`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e2727`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_Repair>::RunMethod<CSpVirtualDisk::Repair,16>(
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
  CSpVirtualDisk::Repair *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::Repair *)operator new(0x170u);
  v7 = CSpVirtualDisk::Repair::Repair(v25);
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
      v25 = (CSpVirtualDisk::Repair *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18033725D,
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
0x1800e23f4  mov     [rsp-38h+arg_18], rbx
0x1800e23f9  push    rbp
0x1800e23fa  push    rsi
0x1800e23fb  push    rdi
0x1800e23fc  push    r12
0x1800e23fe  push    r13
0x1800e2400  push    r14
0x1800e2402  push    r15
0x1800e2404  mov     rbp, rsp
0x1800e2407  sub     rsp, 80h
0x1800e240e  mov     rax, cs:__security_cookie
0x1800e2415  xor     rax, rsp
0x1800e2418  mov     [rbp+var_8], rax
0x1800e241c  xor     eax, eax
0x1800e241e  mov     rsi, rcx
0x1800e2421  xorps   xmm0, xmm0
0x1800e2424  mov     [rbp+var_10], eax
0x1800e2427  mov     ecx, 170h; Size
0x1800e242c  mov     [rbp+var_40], eax
0x1800e242f  movups  [rbp+var_20], xmm0
0x1800e2433  mov     [rbp+TokenHandle], rax
0x1800e2437  mov     r12, r8
0x1800e243a  mov     r13, rdx
0x1800e243d  xor     r14d, r14d
0x1800e2440  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e2445  mov     rcx, rax; this
0x1800e2448  mov     [rbp+var_28], rax
0x1800e244c  call    ??0Repair@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::Repair::Repair(void)
0x1800e2451  mov     rdi, rax
0x1800e2454  test    rax, rax
0x1800e2457  jnz     short loc_1800E2461
0x1800e2459  lea     ebx, [rax+1Bh]
0x1800e245c  jmp     loc_1800E271E
0x1800e2461  mov     rax, [rax]
0x1800e2464  mov     rdx, rsi
0x1800e2467  mov     rcx, rdi
0x1800e246a  xor     r15d, r15d
0x1800e246d  mov     rax, [rax+8]
0x1800e2471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2476  lea     rcx, [rbp+var_40]
0x1800e247a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e247f  mov     [rdi+1Ch], eax
0x1800e2482  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e2486  mov     ecx, [rsi+14h]; unsigned int
0x1800e2489  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e248e  mov     eax, cs:dword_18039EB68
0x1800e2494  cmp     eax, 5
0x1800e2497  jbe     short loc_1800E2507
0x1800e2499  mov     rdx, 400000000000h
0x1800e24a3  lea     rcx, dword_18039EB68
0x1800e24aa  call    _tlgKeywordOn
0x1800e24af  test    al, al
0x1800e24b1  jz      short loc_1800E2507
0x1800e24b3  mov     eax, [rbp+var_40]
0x1800e24b6  lea     rdx, byte_18033725D
0x1800e24bd  xor     ecx, ecx
0x1800e24bf  cmp     [rdi+1Ch], eax
0x1800e24c2  movzx   eax, word ptr [rbp+var_10]
0x1800e24c6  mov     word ptr [rbp+var_40], ax
0x1800e24ca  setnz   cl
0x1800e24cd  mov     eax, [rsi+14h]
0x1800e24d0  mov     [rbp+var_38], eax
0x1800e24d3  lea     rax, [rbp+var_20]
0x1800e24d7  mov     [rbp+var_28], rax
0x1800e24db  lea     rax, [rbp+var_3C]
0x1800e24df  mov     [rsp+80h+var_48], rax
0x1800e24e4  lea     rax, [rbp+var_40]
0x1800e24e8  mov     [rsp+80h+var_50], rax
0x1800e24ed  lea     rax, [rbp+var_38]
0x1800e24f1  mov     [rsp+80h+var_58], rax
0x1800e24f6  lea     rax, [rbp+var_28]
0x1800e24fa  mov     [rsp+80h+var_60], rax
0x1800e24ff  mov     [rbp+var_3C], ecx
0x1800e2502  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e2507  mov     rcx, [rsi]
0x1800e250a  test    rcx, rcx
0x1800e250d  jz      loc_1800E26F4
0x1800e2513  mov     rax, [rcx]
0x1800e2516  test    rax, rax
0x1800e2519  jz      loc_1800E26F4
0x1800e251f  mov     rax, [rax+18h]
0x1800e2523  lea     r8, [rdi+20h]
0x1800e2527  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e252e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2533  mov     ebx, eax
0x1800e2535  test    eax, eax
0x1800e2537  jnz     loc_1800E26F9
0x1800e253d  cmp     [rsi+10h], r14d
0x1800e2541  jz      loc_1800E268D
0x1800e2547  lea     rbx, [rdi+148h]
0x1800e254e  mov     rcx, rbx
0x1800e2551  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e2556  mov     rcx, rbx; struct CSpJobMgr **
0x1800e2559  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e255e  test    eax, eax
0x1800e2560  jnz     short loc_1800E256A
0x1800e2562  lea     ebx, [rax+1Ch]
0x1800e2565  jmp     loc_1800E26F9
0x1800e256a  mov     ecx, 10h; Size
0x1800e256f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e2574  xor     r8d, r8d; pcbe
0x1800e2577  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e257e  mov     rdx, rax; pv
0x1800e2581  mov     r15, rax
0x1800e2584  mov     [rax], rdi
0x1800e2587  call    cs:__imp_CreateThreadpoolWork
0x1800e258e  nop     dword ptr [rax+rax+00h]
0x1800e2593  mov     r14, rax
0x1800e2596  test    rax, rax
0x1800e2599  jnz     short loc_1800E25A7
0x1800e259b  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e25a0  mov     ebx, eax
0x1800e25a2  jmp     loc_1800E26F9
0x1800e25a7  call    cs:__imp_GetCurrentThread
0x1800e25ae  nop     dword ptr [rax+rax+00h]
0x1800e25b3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e25b7  xor     r8d, r8d; OpenAsSelf
0x1800e25ba  mov     rcx, rax; ThreadHandle
0x1800e25bd  mov     edx, 2000Ch; DesiredAccess
0x1800e25c2  call    cs:__imp_OpenThreadToken
0x1800e25c9  nop     dword ptr [rax+rax+00h]
0x1800e25ce  test    eax, eax
0x1800e25d0  jnz     short loc_1800E25E5
0x1800e25d2  call    cs:__imp_GetLastError
0x1800e25d9  nop     dword ptr [rax+rax+00h]
0x1800e25de  cmp     eax, 3F0h
0x1800e25e3  jnz     short loc_1800E259B
0x1800e25e5  mov     rax, [rbp+TokenHandle]
0x1800e25e9  mov     r8, r13
0x1800e25ec  mov     [r15+8], rax
0x1800e25f0  mov     rcx, rdi
0x1800e25f3  mov     rax, [rdi]
0x1800e25f6  mov     rdx, [rsi+8]
0x1800e25fa  mov     rax, [rax+18h]
0x1800e25fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2603  mov     rax, [rdi]
0x1800e2606  mov     rdx, r12
0x1800e2609  mov     rcx, rdi
0x1800e260c  mov     rax, [rax+28h]
0x1800e2610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2615  mov     ebx, eax
0x1800e2617  test    eax, eax
0x1800e2619  jz      short loc_1800E2624
0x1800e261b  cmp     eax, 7
0x1800e261e  jnz     loc_1800E26F9
0x1800e2624  mov     rax, [rdi]
0x1800e2627  mov     rdx, r12
0x1800e262a  mov     rcx, rdi
0x1800e262d  mov     rax, [rax+38h]
0x1800e2631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2636  mov     ebx, eax
0x1800e2638  test    eax, eax
0x1800e263a  jnz     loc_1800E26F9
0x1800e2640  mov     rax, [rdi+150h]
0x1800e2647  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e264e  jnz     short loc_1800E2664
0x1800e2650  mov     rax, [rdi+158h]
0x1800e2657  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e265e  jz      loc_1800E26F9
0x1800e2664  mov     rdx, r12
0x1800e2667  mov     rcx, rdi
0x1800e266a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e266f  mov     ebx, eax
0x1800e2671  test    eax, eax
0x1800e2673  jnz     loc_1800E26F9
0x1800e2679  mov     rcx, r14; pwk
0x1800e267c  call    cs:__imp_SubmitThreadpoolWork
0x1800e2683  nop     dword ptr [rax+rax+00h]
0x1800e2688  jmp     loc_1800E2747
0x1800e268d  mov     rax, [rdi]
0x1800e2690  mov     r8, r13
0x1800e2693  mov     rdx, [rsi+8]
0x1800e2697  mov     rcx, rdi
0x1800e269a  mov     rax, [rax+10h]
0x1800e269e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e26a3  mov     rax, [rdi]
0x1800e26a6  mov     rdx, r12
0x1800e26a9  mov     rcx, rdi
0x1800e26ac  mov     rax, [rax+30h]
0x1800e26b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e26b5  mov     ebx, eax
0x1800e26b7  test    eax, eax
0x1800e26b9  jz      short loc_1800E26C0
0x1800e26bb  cmp     eax, 7
0x1800e26be  jnz     short loc_1800E26F9
0x1800e26c0  mov     rax, [rdi]
0x1800e26c3  mov     rdx, r12
0x1800e26c6  mov     rcx, rdi
0x1800e26c9  mov     rax, [rax+28h]
0x1800e26cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e26d2  mov     ebx, eax
0x1800e26d4  test    eax, eax
0x1800e26d6  jz      short loc_1800E26DD
0x1800e26d8  cmp     eax, 7
0x1800e26db  jnz     short loc_1800E26F9
0x1800e26dd  mov     rax, [rdi]
0x1800e26e0  mov     rdx, r12
0x1800e26e3  mov     rcx, rdi
0x1800e26e6  mov     rax, [rax+38h]
0x1800e26ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e26ef  jmp     loc_1800E25A0
0x1800e26f4  mov     ebx, 4
0x1800e26f9  mov     rax, [rdi]
0x1800e26fc  mov     edx, 1
0x1800e2701  mov     rcx, rdi
0x1800e2704  mov     rax, [rax]
0x1800e2707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e270c  test    r15, r15
0x1800e270f  jz      short loc_1800E271E
0x1800e2711  mov     edx, 10h
0x1800e2716  mov     rcx, r15; Block
0x1800e2719  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e271e  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e2722  test    rcx, rcx
0x1800e2725  jz      short loc_1800E2733
0x1800e2727  call    cs:__imp_CloseHandle
0x1800e272e  nop     dword ptr [rax+rax+00h]
0x1800e2733  test    r14, r14
0x1800e2736  jz      short loc_1800E2747
0x1800e2738  mov     rcx, r14; pwk
0x1800e273b  call    cs:__imp_CloseThreadpoolWork
0x1800e2742  nop     dword ptr [rax+rax+00h]
0x1800e2747  mov     eax, ebx
0x1800e2749  mov     rcx, [rbp+var_8]
0x1800e274d  xor     rcx, rsp; StackCookie
0x1800e2750  call    __security_check_cookie
0x1800e2755  mov     rbx, [rsp+80h+arg_18]
0x1800e275d  add     rsp, 80h
0x1800e2764  pop     r15
0x1800e2766  pop     r14
0x1800e2768  pop     r13
0x1800e276a  pop     r12
0x1800e276c  pop     rdi
0x1800e276d  pop     rsi
0x1800e276e  pop     rbp
0x1800e276f  retn
```
