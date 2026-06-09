# CSpWmiMethod<_SPACES_PhysicalDisk_UpdateFirmware>::RunMethod<CSpPhysicalDisk::UpdateFirmware,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800f3694`
- end: `0x1800f3a11`
- name: `??$RunMethod@VUpdateFirmware@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_UpdateFirmware@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update`

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
- `0x1800f3694`
- `0x1800f3eb8`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3872`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f3847`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f3847`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f3862`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f3862`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f3827`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f3827`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f391c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f391c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f39db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f39db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f39c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f39c7`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_UpdateFirmware>::RunMethod<CSpPhysicalDisk::UpdateFirmware,4>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 updated; // rax
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
  CSpPhysicalDisk::UpdateFirmware *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::UpdateFirmware *)operator new(0x160u);
  updated = CSpPhysicalDisk::UpdateFirmware::UpdateFirmware(v25);
  v8 = updated;
  if ( updated )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)updated + 8LL))(updated, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpPhysicalDisk::UpdateFirmware *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_18033C8F0,
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
0x1800f3694  mov     [rsp-38h+arg_18], rbx
0x1800f3699  push    rbp
0x1800f369a  push    rsi
0x1800f369b  push    rdi
0x1800f369c  push    r12
0x1800f369e  push    r13
0x1800f36a0  push    r14
0x1800f36a2  push    r15
0x1800f36a4  mov     rbp, rsp
0x1800f36a7  sub     rsp, 80h
0x1800f36ae  mov     rax, cs:__security_cookie
0x1800f36b5  xor     rax, rsp
0x1800f36b8  mov     [rbp+var_8], rax
0x1800f36bc  xor     eax, eax
0x1800f36be  mov     rsi, rcx
0x1800f36c1  xorps   xmm0, xmm0
0x1800f36c4  mov     [rbp+var_10], eax
0x1800f36c7  mov     ecx, 160h; Size
0x1800f36cc  mov     [rbp+var_40], eax
0x1800f36cf  movups  [rbp+var_20], xmm0
0x1800f36d3  mov     [rbp+TokenHandle], rax
0x1800f36d7  mov     r12, r8
0x1800f36da  mov     r13, rdx
0x1800f36dd  xor     r14d, r14d
0x1800f36e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f36e5  mov     rcx, rax; this
0x1800f36e8  mov     [rbp+var_28], rax
0x1800f36ec  call    ??0UpdateFirmware@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::UpdateFirmware::UpdateFirmware(void)
0x1800f36f1  mov     rdi, rax
0x1800f36f4  test    rax, rax
0x1800f36f7  jnz     short loc_1800F3701
0x1800f36f9  lea     ebx, [rax+1Bh]
0x1800f36fc  jmp     loc_1800F39BE
0x1800f3701  mov     rax, [rax]
0x1800f3704  mov     rdx, rsi
0x1800f3707  mov     rcx, rdi
0x1800f370a  xor     r15d, r15d
0x1800f370d  mov     rax, [rax+8]
0x1800f3711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3716  lea     rcx, [rbp+var_40]
0x1800f371a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800f371f  mov     [rdi+1Ch], eax
0x1800f3722  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800f3726  mov     ecx, [rsi+14h]; unsigned int
0x1800f3729  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800f372e  mov     eax, cs:dword_18039EB68
0x1800f3734  cmp     eax, 5
0x1800f3737  jbe     short loc_1800F37A7
0x1800f3739  mov     rdx, 400000000000h
0x1800f3743  lea     rcx, dword_18039EB68
0x1800f374a  call    _tlgKeywordOn
0x1800f374f  test    al, al
0x1800f3751  jz      short loc_1800F37A7
0x1800f3753  mov     eax, [rbp+var_40]
0x1800f3756  lea     rdx, unk_18033C8F0
0x1800f375d  xor     ecx, ecx
0x1800f375f  cmp     [rdi+1Ch], eax
0x1800f3762  movzx   eax, word ptr [rbp+var_10]
0x1800f3766  mov     word ptr [rbp+var_40], ax
0x1800f376a  setnz   cl
0x1800f376d  mov     eax, [rsi+14h]
0x1800f3770  mov     [rbp+var_38], eax
0x1800f3773  lea     rax, [rbp+var_20]
0x1800f3777  mov     [rbp+var_28], rax
0x1800f377b  lea     rax, [rbp+var_3C]
0x1800f377f  mov     [rsp+80h+var_48], rax
0x1800f3784  lea     rax, [rbp+var_40]
0x1800f3788  mov     [rsp+80h+var_50], rax
0x1800f378d  lea     rax, [rbp+var_38]
0x1800f3791  mov     [rsp+80h+var_58], rax
0x1800f3796  lea     rax, [rbp+var_28]
0x1800f379a  mov     [rsp+80h+var_60], rax
0x1800f379f  mov     [rbp+var_3C], ecx
0x1800f37a2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800f37a7  mov     rcx, [rsi]
0x1800f37aa  test    rcx, rcx
0x1800f37ad  jz      loc_1800F3994
0x1800f37b3  mov     rax, [rcx]
0x1800f37b6  test    rax, rax
0x1800f37b9  jz      loc_1800F3994
0x1800f37bf  mov     rax, [rax+18h]
0x1800f37c3  lea     r8, [rdi+20h]
0x1800f37c7  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800f37ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f37d3  mov     ebx, eax
0x1800f37d5  test    eax, eax
0x1800f37d7  jnz     loc_1800F3999
0x1800f37dd  cmp     [rsi+10h], r14d
0x1800f37e1  jz      loc_1800F392D
0x1800f37e7  lea     rbx, [rdi+148h]
0x1800f37ee  mov     rcx, rbx
0x1800f37f1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800f37f6  mov     rcx, rbx; struct CSpJobMgr **
0x1800f37f9  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800f37fe  test    eax, eax
0x1800f3800  jnz     short loc_1800F380A
0x1800f3802  lea     ebx, [rax+1Ch]
0x1800f3805  jmp     loc_1800F3999
0x1800f380a  mov     ecx, 10h; Size
0x1800f380f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f3814  xor     r8d, r8d; pcbe
0x1800f3817  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f381e  mov     rdx, rax; pv
0x1800f3821  mov     r15, rax
0x1800f3824  mov     [rax], rdi
0x1800f3827  call    cs:__imp_CreateThreadpoolWork
0x1800f382e  nop     dword ptr [rax+rax+00h]
0x1800f3833  mov     r14, rax
0x1800f3836  test    rax, rax
0x1800f3839  jnz     short loc_1800F3847
0x1800f383b  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800f3840  mov     ebx, eax
0x1800f3842  jmp     loc_1800F3999
0x1800f3847  call    cs:__imp_GetCurrentThread
0x1800f384e  nop     dword ptr [rax+rax+00h]
0x1800f3853  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f3857  xor     r8d, r8d; OpenAsSelf
0x1800f385a  mov     rcx, rax; ThreadHandle
0x1800f385d  mov     edx, 2000Ch; DesiredAccess
0x1800f3862  call    cs:__imp_OpenThreadToken
0x1800f3869  nop     dword ptr [rax+rax+00h]
0x1800f386e  test    eax, eax
0x1800f3870  jnz     short loc_1800F3885
0x1800f3872  call    cs:__imp_GetLastError
0x1800f3879  nop     dword ptr [rax+rax+00h]
0x1800f387e  cmp     eax, 3F0h
0x1800f3883  jnz     short loc_1800F383B
0x1800f3885  mov     rax, [rbp+TokenHandle]
0x1800f3889  mov     r8, r13
0x1800f388c  mov     [r15+8], rax
0x1800f3890  mov     rcx, rdi
0x1800f3893  mov     rax, [rdi]
0x1800f3896  mov     rdx, [rsi+8]
0x1800f389a  mov     rax, [rax+18h]
0x1800f389e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f38a3  mov     rax, [rdi]
0x1800f38a6  mov     rdx, r12
0x1800f38a9  mov     rcx, rdi
0x1800f38ac  mov     rax, [rax+28h]
0x1800f38b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f38b5  mov     ebx, eax
0x1800f38b7  test    eax, eax
0x1800f38b9  jz      short loc_1800F38C4
0x1800f38bb  cmp     eax, 7
0x1800f38be  jnz     loc_1800F3999
0x1800f38c4  mov     rax, [rdi]
0x1800f38c7  mov     rdx, r12
0x1800f38ca  mov     rcx, rdi
0x1800f38cd  mov     rax, [rax+38h]
0x1800f38d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f38d6  mov     ebx, eax
0x1800f38d8  test    eax, eax
0x1800f38da  jnz     loc_1800F3999
0x1800f38e0  mov     rax, [rdi+150h]
0x1800f38e7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800f38ee  jnz     short loc_1800F3904
0x1800f38f0  mov     rax, [rdi+158h]
0x1800f38f7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800f38fe  jz      loc_1800F3999
0x1800f3904  mov     rdx, r12
0x1800f3907  mov     rcx, rdi
0x1800f390a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800f390f  mov     ebx, eax
0x1800f3911  test    eax, eax
0x1800f3913  jnz     loc_1800F3999
0x1800f3919  mov     rcx, r14; pwk
0x1800f391c  call    cs:__imp_SubmitThreadpoolWork
0x1800f3923  nop     dword ptr [rax+rax+00h]
0x1800f3928  jmp     loc_1800F39E7
0x1800f392d  mov     rax, [rdi]
0x1800f3930  mov     r8, r13
0x1800f3933  mov     rdx, [rsi+8]
0x1800f3937  mov     rcx, rdi
0x1800f393a  mov     rax, [rax+10h]
0x1800f393e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3943  mov     rax, [rdi]
0x1800f3946  mov     rdx, r12
0x1800f3949  mov     rcx, rdi
0x1800f394c  mov     rax, [rax+30h]
0x1800f3950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3955  mov     ebx, eax
0x1800f3957  test    eax, eax
0x1800f3959  jz      short loc_1800F3960
0x1800f395b  cmp     eax, 7
0x1800f395e  jnz     short loc_1800F3999
0x1800f3960  mov     rax, [rdi]
0x1800f3963  mov     rdx, r12
0x1800f3966  mov     rcx, rdi
0x1800f3969  mov     rax, [rax+28h]
0x1800f396d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3972  mov     ebx, eax
0x1800f3974  test    eax, eax
0x1800f3976  jz      short loc_1800F397D
0x1800f3978  cmp     eax, 7
0x1800f397b  jnz     short loc_1800F3999
0x1800f397d  mov     rax, [rdi]
0x1800f3980  mov     rdx, r12
0x1800f3983  mov     rcx, rdi
0x1800f3986  mov     rax, [rax+38h]
0x1800f398a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f398f  jmp     loc_1800F3840
0x1800f3994  mov     ebx, 4
0x1800f3999  mov     rax, [rdi]
0x1800f399c  mov     edx, 1
0x1800f39a1  mov     rcx, rdi
0x1800f39a4  mov     rax, [rax]
0x1800f39a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f39ac  test    r15, r15
0x1800f39af  jz      short loc_1800F39BE
0x1800f39b1  mov     edx, 10h
0x1800f39b6  mov     rcx, r15; Block
0x1800f39b9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f39be  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f39c2  test    rcx, rcx
0x1800f39c5  jz      short loc_1800F39D3
0x1800f39c7  call    cs:__imp_CloseHandle
0x1800f39ce  nop     dword ptr [rax+rax+00h]
0x1800f39d3  test    r14, r14
0x1800f39d6  jz      short loc_1800F39E7
0x1800f39d8  mov     rcx, r14; pwk
0x1800f39db  call    cs:__imp_CloseThreadpoolWork
0x1800f39e2  nop     dword ptr [rax+rax+00h]
0x1800f39e7  mov     eax, ebx
0x1800f39e9  mov     rcx, [rbp+var_8]
0x1800f39ed  xor     rcx, rsp; StackCookie
0x1800f39f0  call    __security_check_cookie
0x1800f39f5  mov     rbx, [rsp+80h+arg_18]
0x1800f39fd  add     rsp, 80h
0x1800f3a04  pop     r15
0x1800f3a06  pop     r14
0x1800f3a08  pop     r13
0x1800f3a0a  pop     r12
0x1800f3a0c  pop     rdi
0x1800f3a0d  pop     rsi
0x1800f3a0e  pop     rbp
0x1800f3a0f  retn
```
