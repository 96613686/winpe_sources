# CSpWmiMethod<_SPACES_VirtualDisk_SetProperties>::RunMethod<CSpVirtualDisk::SetProperties,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e3204`
- end: `0x1800e3581`
- name: `??$RunMethod@VSetProperties@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_SetProperties@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

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
- `0x1800e3204`
- `0x1800e426c`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e33e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e33e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e33b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e33b7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e33d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e33d2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e3397`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e3397`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e348c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e348c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e354b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e354b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e3537`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e3537`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_SetProperties>::RunMethod<CSpVirtualDisk::SetProperties,16>(
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
  CSpVirtualDisk::SetProperties *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::SetProperties *)operator new(0x160u);
  v7 = CSpVirtualDisk::SetProperties::SetProperties(v25);
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
      v25 = (CSpVirtualDisk::SetProperties *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)word_18033A842,
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
0x1800e3204  mov     [rsp-38h+arg_18], rbx
0x1800e3209  push    rbp
0x1800e320a  push    rsi
0x1800e320b  push    rdi
0x1800e320c  push    r12
0x1800e320e  push    r13
0x1800e3210  push    r14
0x1800e3212  push    r15
0x1800e3214  mov     rbp, rsp
0x1800e3217  sub     rsp, 80h
0x1800e321e  mov     rax, cs:__security_cookie
0x1800e3225  xor     rax, rsp
0x1800e3228  mov     [rbp+var_8], rax
0x1800e322c  xor     eax, eax
0x1800e322e  mov     rsi, rcx
0x1800e3231  xorps   xmm0, xmm0
0x1800e3234  mov     [rbp+var_10], eax
0x1800e3237  mov     ecx, 160h; Size
0x1800e323c  mov     [rbp+var_40], eax
0x1800e323f  movups  [rbp+var_20], xmm0
0x1800e3243  mov     [rbp+TokenHandle], rax
0x1800e3247  mov     r12, r8
0x1800e324a  mov     r13, rdx
0x1800e324d  xor     r14d, r14d
0x1800e3250  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e3255  mov     rcx, rax; this
0x1800e3258  mov     [rbp+var_28], rax
0x1800e325c  call    ??0SetProperties@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::SetProperties::SetProperties(void)
0x1800e3261  mov     rdi, rax
0x1800e3264  test    rax, rax
0x1800e3267  jnz     short loc_1800E3271
0x1800e3269  lea     ebx, [rax+1Bh]
0x1800e326c  jmp     loc_1800E352E
0x1800e3271  mov     rax, [rax]
0x1800e3274  mov     rdx, rsi
0x1800e3277  mov     rcx, rdi
0x1800e327a  xor     r15d, r15d
0x1800e327d  mov     rax, [rax+8]
0x1800e3281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3286  lea     rcx, [rbp+var_40]
0x1800e328a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e328f  mov     [rdi+1Ch], eax
0x1800e3292  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e3296  mov     ecx, [rsi+14h]; unsigned int
0x1800e3299  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e329e  mov     eax, cs:dword_18039EB68
0x1800e32a4  cmp     eax, 5
0x1800e32a7  jbe     short loc_1800E3317
0x1800e32a9  mov     rdx, 400000000000h
0x1800e32b3  lea     rcx, dword_18039EB68
0x1800e32ba  call    _tlgKeywordOn
0x1800e32bf  test    al, al
0x1800e32c1  jz      short loc_1800E3317
0x1800e32c3  mov     eax, [rbp+var_40]
0x1800e32c6  lea     rdx, word_18033A842
0x1800e32cd  xor     ecx, ecx
0x1800e32cf  cmp     [rdi+1Ch], eax
0x1800e32d2  movzx   eax, word ptr [rbp+var_10]
0x1800e32d6  mov     word ptr [rbp+var_40], ax
0x1800e32da  setnz   cl
0x1800e32dd  mov     eax, [rsi+14h]
0x1800e32e0  mov     [rbp+var_38], eax
0x1800e32e3  lea     rax, [rbp+var_20]
0x1800e32e7  mov     [rbp+var_28], rax
0x1800e32eb  lea     rax, [rbp+var_3C]
0x1800e32ef  mov     [rsp+80h+var_48], rax
0x1800e32f4  lea     rax, [rbp+var_40]
0x1800e32f8  mov     [rsp+80h+var_50], rax
0x1800e32fd  lea     rax, [rbp+var_38]
0x1800e3301  mov     [rsp+80h+var_58], rax
0x1800e3306  lea     rax, [rbp+var_28]
0x1800e330a  mov     [rsp+80h+var_60], rax
0x1800e330f  mov     [rbp+var_3C], ecx
0x1800e3312  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e3317  mov     rcx, [rsi]
0x1800e331a  test    rcx, rcx
0x1800e331d  jz      loc_1800E3504
0x1800e3323  mov     rax, [rcx]
0x1800e3326  test    rax, rax
0x1800e3329  jz      loc_1800E3504
0x1800e332f  mov     rax, [rax+18h]
0x1800e3333  lea     r8, [rdi+20h]
0x1800e3337  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e333e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3343  mov     ebx, eax
0x1800e3345  test    eax, eax
0x1800e3347  jnz     loc_1800E3509
0x1800e334d  cmp     [rsi+10h], r14d
0x1800e3351  jz      loc_1800E349D
0x1800e3357  lea     rbx, [rdi+148h]
0x1800e335e  mov     rcx, rbx
0x1800e3361  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e3366  mov     rcx, rbx; struct CSpJobMgr **
0x1800e3369  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e336e  test    eax, eax
0x1800e3370  jnz     short loc_1800E337A
0x1800e3372  lea     ebx, [rax+1Ch]
0x1800e3375  jmp     loc_1800E3509
0x1800e337a  mov     ecx, 10h; Size
0x1800e337f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e3384  xor     r8d, r8d; pcbe
0x1800e3387  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e338e  mov     rdx, rax; pv
0x1800e3391  mov     r15, rax
0x1800e3394  mov     [rax], rdi
0x1800e3397  call    cs:__imp_CreateThreadpoolWork
0x1800e339e  nop     dword ptr [rax+rax+00h]
0x1800e33a3  mov     r14, rax
0x1800e33a6  test    rax, rax
0x1800e33a9  jnz     short loc_1800E33B7
0x1800e33ab  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e33b0  mov     ebx, eax
0x1800e33b2  jmp     loc_1800E3509
0x1800e33b7  call    cs:__imp_GetCurrentThread
0x1800e33be  nop     dword ptr [rax+rax+00h]
0x1800e33c3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e33c7  xor     r8d, r8d; OpenAsSelf
0x1800e33ca  mov     rcx, rax; ThreadHandle
0x1800e33cd  mov     edx, 2000Ch; DesiredAccess
0x1800e33d2  call    cs:__imp_OpenThreadToken
0x1800e33d9  nop     dword ptr [rax+rax+00h]
0x1800e33de  test    eax, eax
0x1800e33e0  jnz     short loc_1800E33F5
0x1800e33e2  call    cs:__imp_GetLastError
0x1800e33e9  nop     dword ptr [rax+rax+00h]
0x1800e33ee  cmp     eax, 3F0h
0x1800e33f3  jnz     short loc_1800E33AB
0x1800e33f5  mov     rax, [rbp+TokenHandle]
0x1800e33f9  mov     r8, r13
0x1800e33fc  mov     [r15+8], rax
0x1800e3400  mov     rcx, rdi
0x1800e3403  mov     rax, [rdi]
0x1800e3406  mov     rdx, [rsi+8]
0x1800e340a  mov     rax, [rax+18h]
0x1800e340e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3413  mov     rax, [rdi]
0x1800e3416  mov     rdx, r12
0x1800e3419  mov     rcx, rdi
0x1800e341c  mov     rax, [rax+28h]
0x1800e3420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3425  mov     ebx, eax
0x1800e3427  test    eax, eax
0x1800e3429  jz      short loc_1800E3434
0x1800e342b  cmp     eax, 7
0x1800e342e  jnz     loc_1800E3509
0x1800e3434  mov     rax, [rdi]
0x1800e3437  mov     rdx, r12
0x1800e343a  mov     rcx, rdi
0x1800e343d  mov     rax, [rax+38h]
0x1800e3441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3446  mov     ebx, eax
0x1800e3448  test    eax, eax
0x1800e344a  jnz     loc_1800E3509
0x1800e3450  mov     rax, [rdi+150h]
0x1800e3457  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e345e  jnz     short loc_1800E3474
0x1800e3460  mov     rax, [rdi+158h]
0x1800e3467  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e346e  jz      loc_1800E3509
0x1800e3474  mov     rdx, r12
0x1800e3477  mov     rcx, rdi
0x1800e347a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e347f  mov     ebx, eax
0x1800e3481  test    eax, eax
0x1800e3483  jnz     loc_1800E3509
0x1800e3489  mov     rcx, r14; pwk
0x1800e348c  call    cs:__imp_SubmitThreadpoolWork
0x1800e3493  nop     dword ptr [rax+rax+00h]
0x1800e3498  jmp     loc_1800E3557
0x1800e349d  mov     rax, [rdi]
0x1800e34a0  mov     r8, r13
0x1800e34a3  mov     rdx, [rsi+8]
0x1800e34a7  mov     rcx, rdi
0x1800e34aa  mov     rax, [rax+10h]
0x1800e34ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e34b3  mov     rax, [rdi]
0x1800e34b6  mov     rdx, r12
0x1800e34b9  mov     rcx, rdi
0x1800e34bc  mov     rax, [rax+30h]
0x1800e34c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e34c5  mov     ebx, eax
0x1800e34c7  test    eax, eax
0x1800e34c9  jz      short loc_1800E34D0
0x1800e34cb  cmp     eax, 7
0x1800e34ce  jnz     short loc_1800E3509
0x1800e34d0  mov     rax, [rdi]
0x1800e34d3  mov     rdx, r12
0x1800e34d6  mov     rcx, rdi
0x1800e34d9  mov     rax, [rax+28h]
0x1800e34dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e34e2  mov     ebx, eax
0x1800e34e4  test    eax, eax
0x1800e34e6  jz      short loc_1800E34ED
0x1800e34e8  cmp     eax, 7
0x1800e34eb  jnz     short loc_1800E3509
0x1800e34ed  mov     rax, [rdi]
0x1800e34f0  mov     rdx, r12
0x1800e34f3  mov     rcx, rdi
0x1800e34f6  mov     rax, [rax+38h]
0x1800e34fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e34ff  jmp     loc_1800E33B0
0x1800e3504  mov     ebx, 4
0x1800e3509  mov     rax, [rdi]
0x1800e350c  mov     edx, 1
0x1800e3511  mov     rcx, rdi
0x1800e3514  mov     rax, [rax]
0x1800e3517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e351c  test    r15, r15
0x1800e351f  jz      short loc_1800E352E
0x1800e3521  mov     edx, 10h
0x1800e3526  mov     rcx, r15; Block
0x1800e3529  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e352e  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e3532  test    rcx, rcx
0x1800e3535  jz      short loc_1800E3543
0x1800e3537  call    cs:__imp_CloseHandle
0x1800e353e  nop     dword ptr [rax+rax+00h]
0x1800e3543  test    r14, r14
0x1800e3546  jz      short loc_1800E3557
0x1800e3548  mov     rcx, r14; pwk
0x1800e354b  call    cs:__imp_CloseThreadpoolWork
0x1800e3552  nop     dword ptr [rax+rax+00h]
0x1800e3557  mov     eax, ebx
0x1800e3559  mov     rcx, [rbp+var_8]
0x1800e355d  xor     rcx, rsp; StackCookie
0x1800e3560  call    __security_check_cookie
0x1800e3565  mov     rbx, [rsp+80h+arg_18]
0x1800e356d  add     rsp, 80h
0x1800e3574  pop     r15
0x1800e3576  pop     r14
0x1800e3578  pop     r13
0x1800e357a  pop     r12
0x1800e357c  pop     rdi
0x1800e357d  pop     rsi
0x1800e357e  pop     rbp
0x1800e357f  retn
```
