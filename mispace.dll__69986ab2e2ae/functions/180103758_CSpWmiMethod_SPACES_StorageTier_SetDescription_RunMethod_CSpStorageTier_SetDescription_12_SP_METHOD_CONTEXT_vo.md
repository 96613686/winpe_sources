# CSpWmiMethod<_SPACES_StorageTier_SetDescription>::RunMethod<CSpStorageTier::SetDescription,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x180103758`
- end: `0x180103ad5`
- name: `??$RunMethod@VSetDescription@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_SetDescription@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x180103758`
- `0x180104114`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103936`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010390b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010390b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180103926`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180103926`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801038eb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1801038eb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801039e0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1801039e0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180103a9f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180103a9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180103a8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180103a8b`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_SetDescription>::RunMethod<CSpStorageTier::SetDescription,12>(
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
  CSpStorageTier::SetDescription *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::SetDescription *)operator new(0x160u);
  v7 = CSpStorageTier::SetDescription::SetDescription(v25);
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
      v25 = (CSpStorageTier::SetDescription *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_18033F7C4,
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
0x180103758  mov     [rsp-38h+arg_18], rbx
0x18010375d  push    rbp
0x18010375e  push    rsi
0x18010375f  push    rdi
0x180103760  push    r12
0x180103762  push    r13
0x180103764  push    r14
0x180103766  push    r15
0x180103768  mov     rbp, rsp
0x18010376b  sub     rsp, 80h
0x180103772  mov     rax, cs:__security_cookie
0x180103779  xor     rax, rsp
0x18010377c  mov     [rbp+var_8], rax
0x180103780  xor     eax, eax
0x180103782  mov     rsi, rcx
0x180103785  xorps   xmm0, xmm0
0x180103788  mov     [rbp+var_10], eax
0x18010378b  mov     ecx, 160h; Size
0x180103790  mov     [rbp+var_40], eax
0x180103793  movups  [rbp+var_20], xmm0
0x180103797  mov     [rbp+TokenHandle], rax
0x18010379b  mov     r12, r8
0x18010379e  mov     r13, rdx
0x1801037a1  xor     r14d, r14d
0x1801037a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801037a9  mov     rcx, rax; this
0x1801037ac  mov     [rbp+var_28], rax
0x1801037b0  call    ??0SetDescription@CSpStorageTier@@QEAA@XZ; CSpStorageTier::SetDescription::SetDescription(void)
0x1801037b5  mov     rdi, rax
0x1801037b8  test    rax, rax
0x1801037bb  jnz     short loc_1801037C5
0x1801037bd  lea     ebx, [rax+1Bh]
0x1801037c0  jmp     loc_180103A82
0x1801037c5  mov     rax, [rax]
0x1801037c8  mov     rdx, rsi
0x1801037cb  mov     rcx, rdi
0x1801037ce  xor     r15d, r15d
0x1801037d1  mov     rax, [rax+8]
0x1801037d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801037da  lea     rcx, [rbp+var_40]
0x1801037de  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1801037e3  mov     [rdi+1Ch], eax
0x1801037e6  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1801037ea  mov     ecx, [rsi+14h]; unsigned int
0x1801037ed  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1801037f2  mov     eax, cs:dword_18039EB68
0x1801037f8  cmp     eax, 5
0x1801037fb  jbe     short loc_18010386B
0x1801037fd  mov     rdx, 400000000000h
0x180103807  lea     rcx, dword_18039EB68
0x18010380e  call    _tlgKeywordOn
0x180103813  test    al, al
0x180103815  jz      short loc_18010386B
0x180103817  mov     eax, [rbp+var_40]
0x18010381a  lea     rdx, dword_18033F7C4
0x180103821  xor     ecx, ecx
0x180103823  cmp     [rdi+1Ch], eax
0x180103826  movzx   eax, word ptr [rbp+var_10]
0x18010382a  mov     word ptr [rbp+var_40], ax
0x18010382e  setnz   cl
0x180103831  mov     eax, [rsi+14h]
0x180103834  mov     [rbp+var_38], eax
0x180103837  lea     rax, [rbp+var_20]
0x18010383b  mov     [rbp+var_28], rax
0x18010383f  lea     rax, [rbp+var_3C]
0x180103843  mov     [rsp+80h+var_48], rax
0x180103848  lea     rax, [rbp+var_40]
0x18010384c  mov     [rsp+80h+var_50], rax
0x180103851  lea     rax, [rbp+var_38]
0x180103855  mov     [rsp+80h+var_58], rax
0x18010385a  lea     rax, [rbp+var_28]
0x18010385e  mov     [rsp+80h+var_60], rax
0x180103863  mov     [rbp+var_3C], ecx
0x180103866  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18010386b  mov     rcx, [rsi]
0x18010386e  test    rcx, rcx
0x180103871  jz      loc_180103A58
0x180103877  mov     rax, [rcx]
0x18010387a  test    rax, rax
0x18010387d  jz      loc_180103A58
0x180103883  mov     rax, [rax+18h]
0x180103887  lea     r8, [rdi+20h]
0x18010388b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180103892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103897  mov     ebx, eax
0x180103899  test    eax, eax
0x18010389b  jnz     loc_180103A5D
0x1801038a1  cmp     [rsi+10h], r14d
0x1801038a5  jz      loc_1801039F1
0x1801038ab  lea     rbx, [rdi+148h]
0x1801038b2  mov     rcx, rbx
0x1801038b5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1801038ba  mov     rcx, rbx; struct CSpJobMgr **
0x1801038bd  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1801038c2  test    eax, eax
0x1801038c4  jnz     short loc_1801038CE
0x1801038c6  lea     ebx, [rax+1Ch]
0x1801038c9  jmp     loc_180103A5D
0x1801038ce  mov     ecx, 10h; Size
0x1801038d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801038d8  xor     r8d, r8d; pcbe
0x1801038db  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1801038e2  mov     rdx, rax; pv
0x1801038e5  mov     r15, rax
0x1801038e8  mov     [rax], rdi
0x1801038eb  call    cs:__imp_CreateThreadpoolWork
0x1801038f2  nop     dword ptr [rax+rax+00h]
0x1801038f7  mov     r14, rax
0x1801038fa  test    rax, rax
0x1801038fd  jnz     short loc_18010390B
0x1801038ff  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180103904  mov     ebx, eax
0x180103906  jmp     loc_180103A5D
0x18010390b  call    cs:__imp_GetCurrentThread
0x180103912  nop     dword ptr [rax+rax+00h]
0x180103917  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18010391b  xor     r8d, r8d; OpenAsSelf
0x18010391e  mov     rcx, rax; ThreadHandle
0x180103921  mov     edx, 2000Ch; DesiredAccess
0x180103926  call    cs:__imp_OpenThreadToken
0x18010392d  nop     dword ptr [rax+rax+00h]
0x180103932  test    eax, eax
0x180103934  jnz     short loc_180103949
0x180103936  call    cs:__imp_GetLastError
0x18010393d  nop     dword ptr [rax+rax+00h]
0x180103942  cmp     eax, 3F0h
0x180103947  jnz     short loc_1801038FF
0x180103949  mov     rax, [rbp+TokenHandle]
0x18010394d  mov     r8, r13
0x180103950  mov     [r15+8], rax
0x180103954  mov     rcx, rdi
0x180103957  mov     rax, [rdi]
0x18010395a  mov     rdx, [rsi+8]
0x18010395e  mov     rax, [rax+18h]
0x180103962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103967  mov     rax, [rdi]
0x18010396a  mov     rdx, r12
0x18010396d  mov     rcx, rdi
0x180103970  mov     rax, [rax+28h]
0x180103974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103979  mov     ebx, eax
0x18010397b  test    eax, eax
0x18010397d  jz      short loc_180103988
0x18010397f  cmp     eax, 7
0x180103982  jnz     loc_180103A5D
0x180103988  mov     rax, [rdi]
0x18010398b  mov     rdx, r12
0x18010398e  mov     rcx, rdi
0x180103991  mov     rax, [rax+38h]
0x180103995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010399a  mov     ebx, eax
0x18010399c  test    eax, eax
0x18010399e  jnz     loc_180103A5D
0x1801039a4  mov     rax, [rdi+150h]
0x1801039ab  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1801039b2  jnz     short loc_1801039C8
0x1801039b4  mov     rax, [rdi+158h]
0x1801039bb  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1801039c2  jz      loc_180103A5D
0x1801039c8  mov     rdx, r12
0x1801039cb  mov     rcx, rdi
0x1801039ce  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1801039d3  mov     ebx, eax
0x1801039d5  test    eax, eax
0x1801039d7  jnz     loc_180103A5D
0x1801039dd  mov     rcx, r14; pwk
0x1801039e0  call    cs:__imp_SubmitThreadpoolWork
0x1801039e7  nop     dword ptr [rax+rax+00h]
0x1801039ec  jmp     loc_180103AAB
0x1801039f1  mov     rax, [rdi]
0x1801039f4  mov     r8, r13
0x1801039f7  mov     rdx, [rsi+8]
0x1801039fb  mov     rcx, rdi
0x1801039fe  mov     rax, [rax+10h]
0x180103a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103a07  mov     rax, [rdi]
0x180103a0a  mov     rdx, r12
0x180103a0d  mov     rcx, rdi
0x180103a10  mov     rax, [rax+30h]
0x180103a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103a19  mov     ebx, eax
0x180103a1b  test    eax, eax
0x180103a1d  jz      short loc_180103A24
0x180103a1f  cmp     eax, 7
0x180103a22  jnz     short loc_180103A5D
0x180103a24  mov     rax, [rdi]
0x180103a27  mov     rdx, r12
0x180103a2a  mov     rcx, rdi
0x180103a2d  mov     rax, [rax+28h]
0x180103a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103a36  mov     ebx, eax
0x180103a38  test    eax, eax
0x180103a3a  jz      short loc_180103A41
0x180103a3c  cmp     eax, 7
0x180103a3f  jnz     short loc_180103A5D
0x180103a41  mov     rax, [rdi]
0x180103a44  mov     rdx, r12
0x180103a47  mov     rcx, rdi
0x180103a4a  mov     rax, [rax+38h]
0x180103a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103a53  jmp     loc_180103904
0x180103a58  mov     ebx, 4
0x180103a5d  mov     rax, [rdi]
0x180103a60  mov     edx, 1
0x180103a65  mov     rcx, rdi
0x180103a68  mov     rax, [rax]
0x180103a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103a70  test    r15, r15
0x180103a73  jz      short loc_180103A82
0x180103a75  mov     edx, 10h
0x180103a7a  mov     rcx, r15; Block
0x180103a7d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180103a82  mov     rcx, [rbp+TokenHandle]; hObject
0x180103a86  test    rcx, rcx
0x180103a89  jz      short loc_180103A97
0x180103a8b  call    cs:__imp_CloseHandle
0x180103a92  nop     dword ptr [rax+rax+00h]
0x180103a97  test    r14, r14
0x180103a9a  jz      short loc_180103AAB
0x180103a9c  mov     rcx, r14; pwk
0x180103a9f  call    cs:__imp_CloseThreadpoolWork
0x180103aa6  nop     dword ptr [rax+rax+00h]
0x180103aab  mov     eax, ebx
0x180103aad  mov     rcx, [rbp+var_8]
0x180103ab1  xor     rcx, rsp; StackCookie
0x180103ab4  call    __security_check_cookie
0x180103ab9  mov     rbx, [rsp+80h+arg_18]
0x180103ac1  add     rsp, 80h
0x180103ac8  pop     r15
0x180103aca  pop     r14
0x180103acc  pop     r13
0x180103ace  pop     r12
0x180103ad0  pop     rdi
0x180103ad1  pop     rsi
0x180103ad2  pop     rbp
0x180103ad3  retn
```
