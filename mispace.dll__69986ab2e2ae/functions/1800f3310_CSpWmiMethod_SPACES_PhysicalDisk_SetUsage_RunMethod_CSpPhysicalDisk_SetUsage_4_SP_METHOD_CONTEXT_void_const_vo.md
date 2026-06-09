# CSpWmiMethod<_SPACES_PhysicalDisk_SetUsage>::RunMethod<CSpPhysicalDisk::SetUsage,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800f3310`
- end: `0x1800f368d`
- name: `??$RunMethod@VSetUsage@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_SetUsage@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800f3310`
- `0x1800f3e48`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f34ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f34ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f34c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f34c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f34de`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f34de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f34a3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f34a3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f3598`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f3598`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f3657`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f3657`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f3643`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f3643`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_SetUsage>::RunMethod<CSpPhysicalDisk::SetUsage,4>(
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
  CSpPhysicalDisk::SetUsage *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::SetUsage *)operator new(0x160u);
  v7 = CSpPhysicalDisk::SetUsage::SetUsage(v25);
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
      v25 = (CSpPhysicalDisk::SetUsage *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_18033DCA4,
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
0x1800f3310  mov     [rsp-38h+arg_18], rbx
0x1800f3315  push    rbp
0x1800f3316  push    rsi
0x1800f3317  push    rdi
0x1800f3318  push    r12
0x1800f331a  push    r13
0x1800f331c  push    r14
0x1800f331e  push    r15
0x1800f3320  mov     rbp, rsp
0x1800f3323  sub     rsp, 80h
0x1800f332a  mov     rax, cs:__security_cookie
0x1800f3331  xor     rax, rsp
0x1800f3334  mov     [rbp+var_8], rax
0x1800f3338  xor     eax, eax
0x1800f333a  mov     rsi, rcx
0x1800f333d  xorps   xmm0, xmm0
0x1800f3340  mov     [rbp+var_10], eax
0x1800f3343  mov     ecx, 160h; Size
0x1800f3348  mov     [rbp+var_40], eax
0x1800f334b  movups  [rbp+var_20], xmm0
0x1800f334f  mov     [rbp+TokenHandle], rax
0x1800f3353  mov     r12, r8
0x1800f3356  mov     r13, rdx
0x1800f3359  xor     r14d, r14d
0x1800f335c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f3361  mov     rcx, rax; this
0x1800f3364  mov     [rbp+var_28], rax
0x1800f3368  call    ??0SetUsage@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::SetUsage::SetUsage(void)
0x1800f336d  mov     rdi, rax
0x1800f3370  test    rax, rax
0x1800f3373  jnz     short loc_1800F337D
0x1800f3375  lea     ebx, [rax+1Bh]
0x1800f3378  jmp     loc_1800F363A
0x1800f337d  mov     rax, [rax]
0x1800f3380  mov     rdx, rsi
0x1800f3383  mov     rcx, rdi
0x1800f3386  xor     r15d, r15d
0x1800f3389  mov     rax, [rax+8]
0x1800f338d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3392  lea     rcx, [rbp+var_40]
0x1800f3396  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800f339b  mov     [rdi+1Ch], eax
0x1800f339e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800f33a2  mov     ecx, [rsi+14h]; unsigned int
0x1800f33a5  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800f33aa  mov     eax, cs:dword_18039EB68
0x1800f33b0  cmp     eax, 5
0x1800f33b3  jbe     short loc_1800F3423
0x1800f33b5  mov     rdx, 400000000000h
0x1800f33bf  lea     rcx, dword_18039EB68
0x1800f33c6  call    _tlgKeywordOn
0x1800f33cb  test    al, al
0x1800f33cd  jz      short loc_1800F3423
0x1800f33cf  mov     eax, [rbp+var_40]
0x1800f33d2  lea     rdx, dword_18033DCA4
0x1800f33d9  xor     ecx, ecx
0x1800f33db  cmp     [rdi+1Ch], eax
0x1800f33de  movzx   eax, word ptr [rbp+var_10]
0x1800f33e2  mov     word ptr [rbp+var_40], ax
0x1800f33e6  setnz   cl
0x1800f33e9  mov     eax, [rsi+14h]
0x1800f33ec  mov     [rbp+var_38], eax
0x1800f33ef  lea     rax, [rbp+var_20]
0x1800f33f3  mov     [rbp+var_28], rax
0x1800f33f7  lea     rax, [rbp+var_3C]
0x1800f33fb  mov     [rsp+80h+var_48], rax
0x1800f3400  lea     rax, [rbp+var_40]
0x1800f3404  mov     [rsp+80h+var_50], rax
0x1800f3409  lea     rax, [rbp+var_38]
0x1800f340d  mov     [rsp+80h+var_58], rax
0x1800f3412  lea     rax, [rbp+var_28]
0x1800f3416  mov     [rsp+80h+var_60], rax
0x1800f341b  mov     [rbp+var_3C], ecx
0x1800f341e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800f3423  mov     rcx, [rsi]
0x1800f3426  test    rcx, rcx
0x1800f3429  jz      loc_1800F3610
0x1800f342f  mov     rax, [rcx]
0x1800f3432  test    rax, rax
0x1800f3435  jz      loc_1800F3610
0x1800f343b  mov     rax, [rax+18h]
0x1800f343f  lea     r8, [rdi+20h]
0x1800f3443  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800f344a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f344f  mov     ebx, eax
0x1800f3451  test    eax, eax
0x1800f3453  jnz     loc_1800F3615
0x1800f3459  cmp     [rsi+10h], r14d
0x1800f345d  jz      loc_1800F35A9
0x1800f3463  lea     rbx, [rdi+148h]
0x1800f346a  mov     rcx, rbx
0x1800f346d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800f3472  mov     rcx, rbx; struct CSpJobMgr **
0x1800f3475  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800f347a  test    eax, eax
0x1800f347c  jnz     short loc_1800F3486
0x1800f347e  lea     ebx, [rax+1Ch]
0x1800f3481  jmp     loc_1800F3615
0x1800f3486  mov     ecx, 10h; Size
0x1800f348b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f3490  xor     r8d, r8d; pcbe
0x1800f3493  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f349a  mov     rdx, rax; pv
0x1800f349d  mov     r15, rax
0x1800f34a0  mov     [rax], rdi
0x1800f34a3  call    cs:__imp_CreateThreadpoolWork
0x1800f34aa  nop     dword ptr [rax+rax+00h]
0x1800f34af  mov     r14, rax
0x1800f34b2  test    rax, rax
0x1800f34b5  jnz     short loc_1800F34C3
0x1800f34b7  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800f34bc  mov     ebx, eax
0x1800f34be  jmp     loc_1800F3615
0x1800f34c3  call    cs:__imp_GetCurrentThread
0x1800f34ca  nop     dword ptr [rax+rax+00h]
0x1800f34cf  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f34d3  xor     r8d, r8d; OpenAsSelf
0x1800f34d6  mov     rcx, rax; ThreadHandle
0x1800f34d9  mov     edx, 2000Ch; DesiredAccess
0x1800f34de  call    cs:__imp_OpenThreadToken
0x1800f34e5  nop     dword ptr [rax+rax+00h]
0x1800f34ea  test    eax, eax
0x1800f34ec  jnz     short loc_1800F3501
0x1800f34ee  call    cs:__imp_GetLastError
0x1800f34f5  nop     dword ptr [rax+rax+00h]
0x1800f34fa  cmp     eax, 3F0h
0x1800f34ff  jnz     short loc_1800F34B7
0x1800f3501  mov     rax, [rbp+TokenHandle]
0x1800f3505  mov     r8, r13
0x1800f3508  mov     [r15+8], rax
0x1800f350c  mov     rcx, rdi
0x1800f350f  mov     rax, [rdi]
0x1800f3512  mov     rdx, [rsi+8]
0x1800f3516  mov     rax, [rax+18h]
0x1800f351a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f351f  mov     rax, [rdi]
0x1800f3522  mov     rdx, r12
0x1800f3525  mov     rcx, rdi
0x1800f3528  mov     rax, [rax+28h]
0x1800f352c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3531  mov     ebx, eax
0x1800f3533  test    eax, eax
0x1800f3535  jz      short loc_1800F3540
0x1800f3537  cmp     eax, 7
0x1800f353a  jnz     loc_1800F3615
0x1800f3540  mov     rax, [rdi]
0x1800f3543  mov     rdx, r12
0x1800f3546  mov     rcx, rdi
0x1800f3549  mov     rax, [rax+38h]
0x1800f354d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3552  mov     ebx, eax
0x1800f3554  test    eax, eax
0x1800f3556  jnz     loc_1800F3615
0x1800f355c  mov     rax, [rdi+150h]
0x1800f3563  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800f356a  jnz     short loc_1800F3580
0x1800f356c  mov     rax, [rdi+158h]
0x1800f3573  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800f357a  jz      loc_1800F3615
0x1800f3580  mov     rdx, r12
0x1800f3583  mov     rcx, rdi
0x1800f3586  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800f358b  mov     ebx, eax
0x1800f358d  test    eax, eax
0x1800f358f  jnz     loc_1800F3615
0x1800f3595  mov     rcx, r14; pwk
0x1800f3598  call    cs:__imp_SubmitThreadpoolWork
0x1800f359f  nop     dword ptr [rax+rax+00h]
0x1800f35a4  jmp     loc_1800F3663
0x1800f35a9  mov     rax, [rdi]
0x1800f35ac  mov     r8, r13
0x1800f35af  mov     rdx, [rsi+8]
0x1800f35b3  mov     rcx, rdi
0x1800f35b6  mov     rax, [rax+10h]
0x1800f35ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f35bf  mov     rax, [rdi]
0x1800f35c2  mov     rdx, r12
0x1800f35c5  mov     rcx, rdi
0x1800f35c8  mov     rax, [rax+30h]
0x1800f35cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f35d1  mov     ebx, eax
0x1800f35d3  test    eax, eax
0x1800f35d5  jz      short loc_1800F35DC
0x1800f35d7  cmp     eax, 7
0x1800f35da  jnz     short loc_1800F3615
0x1800f35dc  mov     rax, [rdi]
0x1800f35df  mov     rdx, r12
0x1800f35e2  mov     rcx, rdi
0x1800f35e5  mov     rax, [rax+28h]
0x1800f35e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f35ee  mov     ebx, eax
0x1800f35f0  test    eax, eax
0x1800f35f2  jz      short loc_1800F35F9
0x1800f35f4  cmp     eax, 7
0x1800f35f7  jnz     short loc_1800F3615
0x1800f35f9  mov     rax, [rdi]
0x1800f35fc  mov     rdx, r12
0x1800f35ff  mov     rcx, rdi
0x1800f3602  mov     rax, [rax+38h]
0x1800f3606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f360b  jmp     loc_1800F34BC
0x1800f3610  mov     ebx, 4
0x1800f3615  mov     rax, [rdi]
0x1800f3618  mov     edx, 1
0x1800f361d  mov     rcx, rdi
0x1800f3620  mov     rax, [rax]
0x1800f3623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3628  test    r15, r15
0x1800f362b  jz      short loc_1800F363A
0x1800f362d  mov     edx, 10h
0x1800f3632  mov     rcx, r15; Block
0x1800f3635  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f363a  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f363e  test    rcx, rcx
0x1800f3641  jz      short loc_1800F364F
0x1800f3643  call    cs:__imp_CloseHandle
0x1800f364a  nop     dword ptr [rax+rax+00h]
0x1800f364f  test    r14, r14
0x1800f3652  jz      short loc_1800F3663
0x1800f3654  mov     rcx, r14; pwk
0x1800f3657  call    cs:__imp_CloseThreadpoolWork
0x1800f365e  nop     dword ptr [rax+rax+00h]
0x1800f3663  mov     eax, ebx
0x1800f3665  mov     rcx, [rbp+var_8]
0x1800f3669  xor     rcx, rsp; StackCookie
0x1800f366c  call    __security_check_cookie
0x1800f3671  mov     rbx, [rsp+80h+arg_18]
0x1800f3679  add     rsp, 80h
0x1800f3680  pop     r15
0x1800f3682  pop     r14
0x1800f3684  pop     r13
0x1800f3686  pop     r12
0x1800f3688  pop     rdi
0x1800f3689  pop     rsi
0x1800f368a  pop     rbp
0x1800f368b  retn
```
