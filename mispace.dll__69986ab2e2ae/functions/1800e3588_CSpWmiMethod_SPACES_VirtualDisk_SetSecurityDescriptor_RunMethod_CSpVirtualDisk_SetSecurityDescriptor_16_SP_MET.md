# CSpWmiMethod<_SPACES_VirtualDisk_SetSecurityDescriptor>::RunMethod<CSpVirtualDisk::SetSecurityDescriptor,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e3588`
- end: `0x1800e3905`
- name: `??$RunMethod@VSetSecurityDescriptor@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_SetSecurityDescriptor@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

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
- `0x1800e3588`
- `0x1800e42dc`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3766`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e373b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e373b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e3756`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e3756`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e371b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e371b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e3810`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e3810`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e38cf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e38cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e38bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e38bb`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_SetSecurityDescriptor>::RunMethod<CSpVirtualDisk::SetSecurityDescriptor,16>(
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
  CSpVirtualDisk::SetSecurityDescriptor *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::SetSecurityDescriptor *)operator new(0x160u);
  v7 = CSpVirtualDisk::SetSecurityDescriptor::SetSecurityDescriptor(v25);
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
      v25 = (CSpVirtualDisk::SetSecurityDescriptor *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_180339D7E,
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
0x1800e3588  mov     [rsp-38h+arg_18], rbx
0x1800e358d  push    rbp
0x1800e358e  push    rsi
0x1800e358f  push    rdi
0x1800e3590  push    r12
0x1800e3592  push    r13
0x1800e3594  push    r14
0x1800e3596  push    r15
0x1800e3598  mov     rbp, rsp
0x1800e359b  sub     rsp, 80h
0x1800e35a2  mov     rax, cs:__security_cookie
0x1800e35a9  xor     rax, rsp
0x1800e35ac  mov     [rbp+var_8], rax
0x1800e35b0  xor     eax, eax
0x1800e35b2  mov     rsi, rcx
0x1800e35b5  xorps   xmm0, xmm0
0x1800e35b8  mov     [rbp+var_10], eax
0x1800e35bb  mov     ecx, 160h; Size
0x1800e35c0  mov     [rbp+var_40], eax
0x1800e35c3  movups  [rbp+var_20], xmm0
0x1800e35c7  mov     [rbp+TokenHandle], rax
0x1800e35cb  mov     r12, r8
0x1800e35ce  mov     r13, rdx
0x1800e35d1  xor     r14d, r14d
0x1800e35d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e35d9  mov     rcx, rax; this
0x1800e35dc  mov     [rbp+var_28], rax
0x1800e35e0  call    ??0SetSecurityDescriptor@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::SetSecurityDescriptor::SetSecurityDescriptor(void)
0x1800e35e5  mov     rdi, rax
0x1800e35e8  test    rax, rax
0x1800e35eb  jnz     short loc_1800E35F5
0x1800e35ed  lea     ebx, [rax+1Bh]
0x1800e35f0  jmp     loc_1800E38B2
0x1800e35f5  mov     rax, [rax]
0x1800e35f8  mov     rdx, rsi
0x1800e35fb  mov     rcx, rdi
0x1800e35fe  xor     r15d, r15d
0x1800e3601  mov     rax, [rax+8]
0x1800e3605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e360a  lea     rcx, [rbp+var_40]
0x1800e360e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e3613  mov     [rdi+1Ch], eax
0x1800e3616  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e361a  mov     ecx, [rsi+14h]; unsigned int
0x1800e361d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e3622  mov     eax, cs:dword_18039EB68
0x1800e3628  cmp     eax, 5
0x1800e362b  jbe     short loc_1800E369B
0x1800e362d  mov     rdx, 400000000000h
0x1800e3637  lea     rcx, dword_18039EB68
0x1800e363e  call    _tlgKeywordOn
0x1800e3643  test    al, al
0x1800e3645  jz      short loc_1800E369B
0x1800e3647  mov     eax, [rbp+var_40]
0x1800e364a  lea     rdx, word_180339D7E
0x1800e3651  xor     ecx, ecx
0x1800e3653  cmp     [rdi+1Ch], eax
0x1800e3656  movzx   eax, word ptr [rbp+var_10]
0x1800e365a  mov     word ptr [rbp+var_40], ax
0x1800e365e  setnz   cl
0x1800e3661  mov     eax, [rsi+14h]
0x1800e3664  mov     [rbp+var_38], eax
0x1800e3667  lea     rax, [rbp+var_20]
0x1800e366b  mov     [rbp+var_28], rax
0x1800e366f  lea     rax, [rbp+var_3C]
0x1800e3673  mov     [rsp+80h+var_48], rax
0x1800e3678  lea     rax, [rbp+var_40]
0x1800e367c  mov     [rsp+80h+var_50], rax
0x1800e3681  lea     rax, [rbp+var_38]
0x1800e3685  mov     [rsp+80h+var_58], rax
0x1800e368a  lea     rax, [rbp+var_28]
0x1800e368e  mov     [rsp+80h+var_60], rax
0x1800e3693  mov     [rbp+var_3C], ecx
0x1800e3696  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e369b  mov     rcx, [rsi]
0x1800e369e  test    rcx, rcx
0x1800e36a1  jz      loc_1800E3888
0x1800e36a7  mov     rax, [rcx]
0x1800e36aa  test    rax, rax
0x1800e36ad  jz      loc_1800E3888
0x1800e36b3  mov     rax, [rax+18h]
0x1800e36b7  lea     r8, [rdi+20h]
0x1800e36bb  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e36c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e36c7  mov     ebx, eax
0x1800e36c9  test    eax, eax
0x1800e36cb  jnz     loc_1800E388D
0x1800e36d1  cmp     [rsi+10h], r14d
0x1800e36d5  jz      loc_1800E3821
0x1800e36db  lea     rbx, [rdi+148h]
0x1800e36e2  mov     rcx, rbx
0x1800e36e5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e36ea  mov     rcx, rbx; struct CSpJobMgr **
0x1800e36ed  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e36f2  test    eax, eax
0x1800e36f4  jnz     short loc_1800E36FE
0x1800e36f6  lea     ebx, [rax+1Ch]
0x1800e36f9  jmp     loc_1800E388D
0x1800e36fe  mov     ecx, 10h; Size
0x1800e3703  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e3708  xor     r8d, r8d; pcbe
0x1800e370b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e3712  mov     rdx, rax; pv
0x1800e3715  mov     r15, rax
0x1800e3718  mov     [rax], rdi
0x1800e371b  call    cs:__imp_CreateThreadpoolWork
0x1800e3722  nop     dword ptr [rax+rax+00h]
0x1800e3727  mov     r14, rax
0x1800e372a  test    rax, rax
0x1800e372d  jnz     short loc_1800E373B
0x1800e372f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e3734  mov     ebx, eax
0x1800e3736  jmp     loc_1800E388D
0x1800e373b  call    cs:__imp_GetCurrentThread
0x1800e3742  nop     dword ptr [rax+rax+00h]
0x1800e3747  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e374b  xor     r8d, r8d; OpenAsSelf
0x1800e374e  mov     rcx, rax; ThreadHandle
0x1800e3751  mov     edx, 2000Ch; DesiredAccess
0x1800e3756  call    cs:__imp_OpenThreadToken
0x1800e375d  nop     dword ptr [rax+rax+00h]
0x1800e3762  test    eax, eax
0x1800e3764  jnz     short loc_1800E3779
0x1800e3766  call    cs:__imp_GetLastError
0x1800e376d  nop     dword ptr [rax+rax+00h]
0x1800e3772  cmp     eax, 3F0h
0x1800e3777  jnz     short loc_1800E372F
0x1800e3779  mov     rax, [rbp+TokenHandle]
0x1800e377d  mov     r8, r13
0x1800e3780  mov     [r15+8], rax
0x1800e3784  mov     rcx, rdi
0x1800e3787  mov     rax, [rdi]
0x1800e378a  mov     rdx, [rsi+8]
0x1800e378e  mov     rax, [rax+18h]
0x1800e3792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3797  mov     rax, [rdi]
0x1800e379a  mov     rdx, r12
0x1800e379d  mov     rcx, rdi
0x1800e37a0  mov     rax, [rax+28h]
0x1800e37a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e37a9  mov     ebx, eax
0x1800e37ab  test    eax, eax
0x1800e37ad  jz      short loc_1800E37B8
0x1800e37af  cmp     eax, 7
0x1800e37b2  jnz     loc_1800E388D
0x1800e37b8  mov     rax, [rdi]
0x1800e37bb  mov     rdx, r12
0x1800e37be  mov     rcx, rdi
0x1800e37c1  mov     rax, [rax+38h]
0x1800e37c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e37ca  mov     ebx, eax
0x1800e37cc  test    eax, eax
0x1800e37ce  jnz     loc_1800E388D
0x1800e37d4  mov     rax, [rdi+150h]
0x1800e37db  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e37e2  jnz     short loc_1800E37F8
0x1800e37e4  mov     rax, [rdi+158h]
0x1800e37eb  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e37f2  jz      loc_1800E388D
0x1800e37f8  mov     rdx, r12
0x1800e37fb  mov     rcx, rdi
0x1800e37fe  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e3803  mov     ebx, eax
0x1800e3805  test    eax, eax
0x1800e3807  jnz     loc_1800E388D
0x1800e380d  mov     rcx, r14; pwk
0x1800e3810  call    cs:__imp_SubmitThreadpoolWork
0x1800e3817  nop     dword ptr [rax+rax+00h]
0x1800e381c  jmp     loc_1800E38DB
0x1800e3821  mov     rax, [rdi]
0x1800e3824  mov     r8, r13
0x1800e3827  mov     rdx, [rsi+8]
0x1800e382b  mov     rcx, rdi
0x1800e382e  mov     rax, [rax+10h]
0x1800e3832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3837  mov     rax, [rdi]
0x1800e383a  mov     rdx, r12
0x1800e383d  mov     rcx, rdi
0x1800e3840  mov     rax, [rax+30h]
0x1800e3844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3849  mov     ebx, eax
0x1800e384b  test    eax, eax
0x1800e384d  jz      short loc_1800E3854
0x1800e384f  cmp     eax, 7
0x1800e3852  jnz     short loc_1800E388D
0x1800e3854  mov     rax, [rdi]
0x1800e3857  mov     rdx, r12
0x1800e385a  mov     rcx, rdi
0x1800e385d  mov     rax, [rax+28h]
0x1800e3861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3866  mov     ebx, eax
0x1800e3868  test    eax, eax
0x1800e386a  jz      short loc_1800E3871
0x1800e386c  cmp     eax, 7
0x1800e386f  jnz     short loc_1800E388D
0x1800e3871  mov     rax, [rdi]
0x1800e3874  mov     rdx, r12
0x1800e3877  mov     rcx, rdi
0x1800e387a  mov     rax, [rax+38h]
0x1800e387e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3883  jmp     loc_1800E3734
0x1800e3888  mov     ebx, 4
0x1800e388d  mov     rax, [rdi]
0x1800e3890  mov     edx, 1
0x1800e3895  mov     rcx, rdi
0x1800e3898  mov     rax, [rax]
0x1800e389b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e38a0  test    r15, r15
0x1800e38a3  jz      short loc_1800E38B2
0x1800e38a5  mov     edx, 10h
0x1800e38aa  mov     rcx, r15; Block
0x1800e38ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e38b2  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e38b6  test    rcx, rcx
0x1800e38b9  jz      short loc_1800E38C7
0x1800e38bb  call    cs:__imp_CloseHandle
0x1800e38c2  nop     dword ptr [rax+rax+00h]
0x1800e38c7  test    r14, r14
0x1800e38ca  jz      short loc_1800E38DB
0x1800e38cc  mov     rcx, r14; pwk
0x1800e38cf  call    cs:__imp_CloseThreadpoolWork
0x1800e38d6  nop     dword ptr [rax+rax+00h]
0x1800e38db  mov     eax, ebx
0x1800e38dd  mov     rcx, [rbp+var_8]
0x1800e38e1  xor     rcx, rsp; StackCookie
0x1800e38e4  call    __security_check_cookie
0x1800e38e9  mov     rbx, [rsp+80h+arg_18]
0x1800e38f1  add     rsp, 80h
0x1800e38f8  pop     r15
0x1800e38fa  pop     r14
0x1800e38fc  pop     r13
0x1800e38fe  pop     r12
0x1800e3900  pop     rdi
0x1800e3901  pop     rsi
0x1800e3902  pop     rbp
0x1800e3903  retn
```
