# CSpWmiMethod<_SPACES_StorageTier_RemoveStorageFaultDomain>::RunMethod<CSpStorageTier::RemoveStorageFaultDomain,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x180102cc8`
- end: `0x180103045`
- name: `??$RunMethod@VRemoveStorageFaultDomain@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_RemoveStorageFaultDomain@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x180102cc8`
- `0x180104034`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102ea6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102ea6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180102e7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180102e7b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180102e96`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180102e96`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180102e5b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180102e5b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180102f50`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180102f50`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010300f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010300f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180102ffb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180102ffb`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_RemoveStorageFaultDomain>::RunMethod<CSpStorageTier::RemoveStorageFaultDomain,12>(
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
  CSpStorageTier::RemoveStorageFaultDomain *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::RemoveStorageFaultDomain *)operator new(0x160u);
  v7 = CSpStorageTier::RemoveStorageFaultDomain::RemoveStorageFaultDomain(v25);
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
      v25 = (CSpStorageTier::RemoveStorageFaultDomain *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_18034026C,
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
0x180102cc8  mov     [rsp-38h+arg_18], rbx
0x180102ccd  push    rbp
0x180102cce  push    rsi
0x180102ccf  push    rdi
0x180102cd0  push    r12
0x180102cd2  push    r13
0x180102cd4  push    r14
0x180102cd6  push    r15
0x180102cd8  mov     rbp, rsp
0x180102cdb  sub     rsp, 80h
0x180102ce2  mov     rax, cs:__security_cookie
0x180102ce9  xor     rax, rsp
0x180102cec  mov     [rbp+var_8], rax
0x180102cf0  xor     eax, eax
0x180102cf2  mov     rsi, rcx
0x180102cf5  xorps   xmm0, xmm0
0x180102cf8  mov     [rbp+var_10], eax
0x180102cfb  mov     ecx, 160h; Size
0x180102d00  mov     [rbp+var_40], eax
0x180102d03  movups  [rbp+var_20], xmm0
0x180102d07  mov     [rbp+TokenHandle], rax
0x180102d0b  mov     r12, r8
0x180102d0e  mov     r13, rdx
0x180102d11  xor     r14d, r14d
0x180102d14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180102d19  mov     rcx, rax; this
0x180102d1c  mov     [rbp+var_28], rax
0x180102d20  call    ??0RemoveStorageFaultDomain@CSpStorageTier@@QEAA@XZ; CSpStorageTier::RemoveStorageFaultDomain::RemoveStorageFaultDomain(void)
0x180102d25  mov     rdi, rax
0x180102d28  test    rax, rax
0x180102d2b  jnz     short loc_180102D35
0x180102d2d  lea     ebx, [rax+1Bh]
0x180102d30  jmp     loc_180102FF2
0x180102d35  mov     rax, [rax]
0x180102d38  mov     rdx, rsi
0x180102d3b  mov     rcx, rdi
0x180102d3e  xor     r15d, r15d
0x180102d41  mov     rax, [rax+8]
0x180102d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102d4a  lea     rcx, [rbp+var_40]
0x180102d4e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180102d53  mov     [rdi+1Ch], eax
0x180102d56  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x180102d5a  mov     ecx, [rsi+14h]; unsigned int
0x180102d5d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180102d62  mov     eax, cs:dword_18039EB68
0x180102d68  cmp     eax, 5
0x180102d6b  jbe     short loc_180102DDB
0x180102d6d  mov     rdx, 400000000000h
0x180102d77  lea     rcx, dword_18039EB68
0x180102d7e  call    _tlgKeywordOn
0x180102d83  test    al, al
0x180102d85  jz      short loc_180102DDB
0x180102d87  mov     eax, [rbp+var_40]
0x180102d8a  lea     rdx, dword_18034026C
0x180102d91  xor     ecx, ecx
0x180102d93  cmp     [rdi+1Ch], eax
0x180102d96  movzx   eax, word ptr [rbp+var_10]
0x180102d9a  mov     word ptr [rbp+var_40], ax
0x180102d9e  setnz   cl
0x180102da1  mov     eax, [rsi+14h]
0x180102da4  mov     [rbp+var_38], eax
0x180102da7  lea     rax, [rbp+var_20]
0x180102dab  mov     [rbp+var_28], rax
0x180102daf  lea     rax, [rbp+var_3C]
0x180102db3  mov     [rsp+80h+var_48], rax
0x180102db8  lea     rax, [rbp+var_40]
0x180102dbc  mov     [rsp+80h+var_50], rax
0x180102dc1  lea     rax, [rbp+var_38]
0x180102dc5  mov     [rsp+80h+var_58], rax
0x180102dca  lea     rax, [rbp+var_28]
0x180102dce  mov     [rsp+80h+var_60], rax
0x180102dd3  mov     [rbp+var_3C], ecx
0x180102dd6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x180102ddb  mov     rcx, [rsi]
0x180102dde  test    rcx, rcx
0x180102de1  jz      loc_180102FC8
0x180102de7  mov     rax, [rcx]
0x180102dea  test    rax, rax
0x180102ded  jz      loc_180102FC8
0x180102df3  mov     rax, [rax+18h]
0x180102df7  lea     r8, [rdi+20h]
0x180102dfb  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180102e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102e07  mov     ebx, eax
0x180102e09  test    eax, eax
0x180102e0b  jnz     loc_180102FCD
0x180102e11  cmp     [rsi+10h], r14d
0x180102e15  jz      loc_180102F61
0x180102e1b  lea     rbx, [rdi+148h]
0x180102e22  mov     rcx, rbx
0x180102e25  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180102e2a  mov     rcx, rbx; struct CSpJobMgr **
0x180102e2d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x180102e32  test    eax, eax
0x180102e34  jnz     short loc_180102E3E
0x180102e36  lea     ebx, [rax+1Ch]
0x180102e39  jmp     loc_180102FCD
0x180102e3e  mov     ecx, 10h; Size
0x180102e43  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180102e48  xor     r8d, r8d; pcbe
0x180102e4b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180102e52  mov     rdx, rax; pv
0x180102e55  mov     r15, rax
0x180102e58  mov     [rax], rdi
0x180102e5b  call    cs:__imp_CreateThreadpoolWork
0x180102e62  nop     dword ptr [rax+rax+00h]
0x180102e67  mov     r14, rax
0x180102e6a  test    rax, rax
0x180102e6d  jnz     short loc_180102E7B
0x180102e6f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180102e74  mov     ebx, eax
0x180102e76  jmp     loc_180102FCD
0x180102e7b  call    cs:__imp_GetCurrentThread
0x180102e82  nop     dword ptr [rax+rax+00h]
0x180102e87  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180102e8b  xor     r8d, r8d; OpenAsSelf
0x180102e8e  mov     rcx, rax; ThreadHandle
0x180102e91  mov     edx, 2000Ch; DesiredAccess
0x180102e96  call    cs:__imp_OpenThreadToken
0x180102e9d  nop     dword ptr [rax+rax+00h]
0x180102ea2  test    eax, eax
0x180102ea4  jnz     short loc_180102EB9
0x180102ea6  call    cs:__imp_GetLastError
0x180102ead  nop     dword ptr [rax+rax+00h]
0x180102eb2  cmp     eax, 3F0h
0x180102eb7  jnz     short loc_180102E6F
0x180102eb9  mov     rax, [rbp+TokenHandle]
0x180102ebd  mov     r8, r13
0x180102ec0  mov     [r15+8], rax
0x180102ec4  mov     rcx, rdi
0x180102ec7  mov     rax, [rdi]
0x180102eca  mov     rdx, [rsi+8]
0x180102ece  mov     rax, [rax+18h]
0x180102ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102ed7  mov     rax, [rdi]
0x180102eda  mov     rdx, r12
0x180102edd  mov     rcx, rdi
0x180102ee0  mov     rax, [rax+28h]
0x180102ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102ee9  mov     ebx, eax
0x180102eeb  test    eax, eax
0x180102eed  jz      short loc_180102EF8
0x180102eef  cmp     eax, 7
0x180102ef2  jnz     loc_180102FCD
0x180102ef8  mov     rax, [rdi]
0x180102efb  mov     rdx, r12
0x180102efe  mov     rcx, rdi
0x180102f01  mov     rax, [rax+38h]
0x180102f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102f0a  mov     ebx, eax
0x180102f0c  test    eax, eax
0x180102f0e  jnz     loc_180102FCD
0x180102f14  mov     rax, [rdi+150h]
0x180102f1b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180102f22  jnz     short loc_180102F38
0x180102f24  mov     rax, [rdi+158h]
0x180102f2b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180102f32  jz      loc_180102FCD
0x180102f38  mov     rdx, r12
0x180102f3b  mov     rcx, rdi
0x180102f3e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x180102f43  mov     ebx, eax
0x180102f45  test    eax, eax
0x180102f47  jnz     loc_180102FCD
0x180102f4d  mov     rcx, r14; pwk
0x180102f50  call    cs:__imp_SubmitThreadpoolWork
0x180102f57  nop     dword ptr [rax+rax+00h]
0x180102f5c  jmp     loc_18010301B
0x180102f61  mov     rax, [rdi]
0x180102f64  mov     r8, r13
0x180102f67  mov     rdx, [rsi+8]
0x180102f6b  mov     rcx, rdi
0x180102f6e  mov     rax, [rax+10h]
0x180102f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102f77  mov     rax, [rdi]
0x180102f7a  mov     rdx, r12
0x180102f7d  mov     rcx, rdi
0x180102f80  mov     rax, [rax+30h]
0x180102f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102f89  mov     ebx, eax
0x180102f8b  test    eax, eax
0x180102f8d  jz      short loc_180102F94
0x180102f8f  cmp     eax, 7
0x180102f92  jnz     short loc_180102FCD
0x180102f94  mov     rax, [rdi]
0x180102f97  mov     rdx, r12
0x180102f9a  mov     rcx, rdi
0x180102f9d  mov     rax, [rax+28h]
0x180102fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102fa6  mov     ebx, eax
0x180102fa8  test    eax, eax
0x180102faa  jz      short loc_180102FB1
0x180102fac  cmp     eax, 7
0x180102faf  jnz     short loc_180102FCD
0x180102fb1  mov     rax, [rdi]
0x180102fb4  mov     rdx, r12
0x180102fb7  mov     rcx, rdi
0x180102fba  mov     rax, [rax+38h]
0x180102fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102fc3  jmp     loc_180102E74
0x180102fc8  mov     ebx, 4
0x180102fcd  mov     rax, [rdi]
0x180102fd0  mov     edx, 1
0x180102fd5  mov     rcx, rdi
0x180102fd8  mov     rax, [rax]
0x180102fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102fe0  test    r15, r15
0x180102fe3  jz      short loc_180102FF2
0x180102fe5  mov     edx, 10h
0x180102fea  mov     rcx, r15; Block
0x180102fed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180102ff2  mov     rcx, [rbp+TokenHandle]; hObject
0x180102ff6  test    rcx, rcx
0x180102ff9  jz      short loc_180103007
0x180102ffb  call    cs:__imp_CloseHandle
0x180103002  nop     dword ptr [rax+rax+00h]
0x180103007  test    r14, r14
0x18010300a  jz      short loc_18010301B
0x18010300c  mov     rcx, r14; pwk
0x18010300f  call    cs:__imp_CloseThreadpoolWork
0x180103016  nop     dword ptr [rax+rax+00h]
0x18010301b  mov     eax, ebx
0x18010301d  mov     rcx, [rbp+var_8]
0x180103021  xor     rcx, rsp; StackCookie
0x180103024  call    __security_check_cookie
0x180103029  mov     rbx, [rsp+80h+arg_18]
0x180103031  add     rsp, 80h
0x180103038  pop     r15
0x18010303a  pop     r14
0x18010303c  pop     r13
0x18010303e  pop     r12
0x180103040  pop     rdi
0x180103041  pop     rsi
0x180103042  pop     rbp
0x180103043  retn
```
