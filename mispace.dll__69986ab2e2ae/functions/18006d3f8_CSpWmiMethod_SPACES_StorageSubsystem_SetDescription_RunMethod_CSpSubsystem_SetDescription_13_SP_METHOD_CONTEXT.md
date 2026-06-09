# CSpWmiMethod<_SPACES_StorageSubsystem_SetDescription>::RunMethod<CSpSubsystem::SetDescription,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006d3f8`
- end: `0x18006d775`
- name: `??$RunMethod@VSetDescription@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_SetDescription@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800743e0`

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
- `0x18006d3f8`
- `0x18006e3d4`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d5d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d5d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006d5ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006d5ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006d5c6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006d5c6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006d58b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006d58b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006d680`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006d680`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006d73f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006d73f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d72b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d72b`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_SetDescription>::RunMethod<CSpSubsystem::SetDescription,13>(
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
  CSpSubsystem::SetDescription *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::SetDescription *)operator new(0x160u);
  v7 = CSpSubsystem::SetDescription::SetDescription(v25);
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
      v25 = (CSpSubsystem::SetDescription *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_180315539,
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
0x18006d3f8  mov     [rsp-38h+arg_18], rbx
0x18006d3fd  push    rbp
0x18006d3fe  push    rsi
0x18006d3ff  push    rdi
0x18006d400  push    r12
0x18006d402  push    r13
0x18006d404  push    r14
0x18006d406  push    r15
0x18006d408  mov     rbp, rsp
0x18006d40b  sub     rsp, 80h
0x18006d412  mov     rax, cs:__security_cookie
0x18006d419  xor     rax, rsp
0x18006d41c  mov     [rbp+var_8], rax
0x18006d420  xor     eax, eax
0x18006d422  mov     rsi, rcx
0x18006d425  xorps   xmm0, xmm0
0x18006d428  mov     [rbp+var_10], eax
0x18006d42b  mov     ecx, 160h; Size
0x18006d430  mov     [rbp+var_40], eax
0x18006d433  movups  [rbp+var_20], xmm0
0x18006d437  mov     [rbp+TokenHandle], rax
0x18006d43b  mov     r12, r8
0x18006d43e  mov     r13, rdx
0x18006d441  xor     r14d, r14d
0x18006d444  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006d449  mov     rcx, rax; this
0x18006d44c  mov     [rbp+var_28], rax
0x18006d450  call    ??0SetDescription@CSpSubsystem@@QEAA@XZ; CSpSubsystem::SetDescription::SetDescription(void)
0x18006d455  mov     rdi, rax
0x18006d458  test    rax, rax
0x18006d45b  jnz     short loc_18006D465
0x18006d45d  lea     ebx, [rax+1Bh]
0x18006d460  jmp     loc_18006D722
0x18006d465  mov     rax, [rax]
0x18006d468  mov     rdx, rsi
0x18006d46b  mov     rcx, rdi
0x18006d46e  xor     r15d, r15d
0x18006d471  mov     rax, [rax+8]
0x18006d475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d47a  lea     rcx, [rbp+var_40]
0x18006d47e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006d483  mov     [rdi+1Ch], eax
0x18006d486  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006d48a  mov     ecx, [rsi+14h]; unsigned int
0x18006d48d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006d492  mov     eax, cs:dword_18039EB68
0x18006d498  cmp     eax, 5
0x18006d49b  jbe     short loc_18006D50B
0x18006d49d  mov     rdx, 400000000000h
0x18006d4a7  lea     rcx, dword_18039EB68
0x18006d4ae  call    _tlgKeywordOn
0x18006d4b3  test    al, al
0x18006d4b5  jz      short loc_18006D50B
0x18006d4b7  mov     eax, [rbp+var_40]
0x18006d4ba  lea     rdx, byte_180315539
0x18006d4c1  xor     ecx, ecx
0x18006d4c3  cmp     [rdi+1Ch], eax
0x18006d4c6  movzx   eax, word ptr [rbp+var_10]
0x18006d4ca  mov     word ptr [rbp+var_40], ax
0x18006d4ce  setnz   cl
0x18006d4d1  mov     eax, [rsi+14h]
0x18006d4d4  mov     [rbp+var_38], eax
0x18006d4d7  lea     rax, [rbp+var_20]
0x18006d4db  mov     [rbp+var_28], rax
0x18006d4df  lea     rax, [rbp+var_3C]
0x18006d4e3  mov     [rsp+80h+var_48], rax
0x18006d4e8  lea     rax, [rbp+var_40]
0x18006d4ec  mov     [rsp+80h+var_50], rax
0x18006d4f1  lea     rax, [rbp+var_38]
0x18006d4f5  mov     [rsp+80h+var_58], rax
0x18006d4fa  lea     rax, [rbp+var_28]
0x18006d4fe  mov     [rsp+80h+var_60], rax
0x18006d503  mov     [rbp+var_3C], ecx
0x18006d506  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006d50b  mov     rcx, [rsi]
0x18006d50e  test    rcx, rcx
0x18006d511  jz      loc_18006D6F8
0x18006d517  mov     rax, [rcx]
0x18006d51a  test    rax, rax
0x18006d51d  jz      loc_18006D6F8
0x18006d523  mov     rax, [rax+18h]
0x18006d527  lea     r8, [rdi+20h]
0x18006d52b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006d532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d537  mov     ebx, eax
0x18006d539  test    eax, eax
0x18006d53b  jnz     loc_18006D6FD
0x18006d541  cmp     [rsi+10h], r14d
0x18006d545  jz      loc_18006D691
0x18006d54b  lea     rbx, [rdi+148h]
0x18006d552  mov     rcx, rbx
0x18006d555  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006d55a  mov     rcx, rbx; struct CSpJobMgr **
0x18006d55d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006d562  test    eax, eax
0x18006d564  jnz     short loc_18006D56E
0x18006d566  lea     ebx, [rax+1Ch]
0x18006d569  jmp     loc_18006D6FD
0x18006d56e  mov     ecx, 10h; Size
0x18006d573  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006d578  xor     r8d, r8d; pcbe
0x18006d57b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006d582  mov     rdx, rax; pv
0x18006d585  mov     r15, rax
0x18006d588  mov     [rax], rdi
0x18006d58b  call    cs:__imp_CreateThreadpoolWork
0x18006d592  nop     dword ptr [rax+rax+00h]
0x18006d597  mov     r14, rax
0x18006d59a  test    rax, rax
0x18006d59d  jnz     short loc_18006D5AB
0x18006d59f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006d5a4  mov     ebx, eax
0x18006d5a6  jmp     loc_18006D6FD
0x18006d5ab  call    cs:__imp_GetCurrentThread
0x18006d5b2  nop     dword ptr [rax+rax+00h]
0x18006d5b7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006d5bb  xor     r8d, r8d; OpenAsSelf
0x18006d5be  mov     rcx, rax; ThreadHandle
0x18006d5c1  mov     edx, 2000Ch; DesiredAccess
0x18006d5c6  call    cs:__imp_OpenThreadToken
0x18006d5cd  nop     dword ptr [rax+rax+00h]
0x18006d5d2  test    eax, eax
0x18006d5d4  jnz     short loc_18006D5E9
0x18006d5d6  call    cs:__imp_GetLastError
0x18006d5dd  nop     dword ptr [rax+rax+00h]
0x18006d5e2  cmp     eax, 3F0h
0x18006d5e7  jnz     short loc_18006D59F
0x18006d5e9  mov     rax, [rbp+TokenHandle]
0x18006d5ed  mov     r8, r13
0x18006d5f0  mov     [r15+8], rax
0x18006d5f4  mov     rcx, rdi
0x18006d5f7  mov     rax, [rdi]
0x18006d5fa  mov     rdx, [rsi+8]
0x18006d5fe  mov     rax, [rax+18h]
0x18006d602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d607  mov     rax, [rdi]
0x18006d60a  mov     rdx, r12
0x18006d60d  mov     rcx, rdi
0x18006d610  mov     rax, [rax+28h]
0x18006d614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d619  mov     ebx, eax
0x18006d61b  test    eax, eax
0x18006d61d  jz      short loc_18006D628
0x18006d61f  cmp     eax, 7
0x18006d622  jnz     loc_18006D6FD
0x18006d628  mov     rax, [rdi]
0x18006d62b  mov     rdx, r12
0x18006d62e  mov     rcx, rdi
0x18006d631  mov     rax, [rax+38h]
0x18006d635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d63a  mov     ebx, eax
0x18006d63c  test    eax, eax
0x18006d63e  jnz     loc_18006D6FD
0x18006d644  mov     rax, [rdi+150h]
0x18006d64b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006d652  jnz     short loc_18006D668
0x18006d654  mov     rax, [rdi+158h]
0x18006d65b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006d662  jz      loc_18006D6FD
0x18006d668  mov     rdx, r12
0x18006d66b  mov     rcx, rdi
0x18006d66e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006d673  mov     ebx, eax
0x18006d675  test    eax, eax
0x18006d677  jnz     loc_18006D6FD
0x18006d67d  mov     rcx, r14; pwk
0x18006d680  call    cs:__imp_SubmitThreadpoolWork
0x18006d687  nop     dword ptr [rax+rax+00h]
0x18006d68c  jmp     loc_18006D74B
0x18006d691  mov     rax, [rdi]
0x18006d694  mov     r8, r13
0x18006d697  mov     rdx, [rsi+8]
0x18006d69b  mov     rcx, rdi
0x18006d69e  mov     rax, [rax+10h]
0x18006d6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d6a7  mov     rax, [rdi]
0x18006d6aa  mov     rdx, r12
0x18006d6ad  mov     rcx, rdi
0x18006d6b0  mov     rax, [rax+30h]
0x18006d6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d6b9  mov     ebx, eax
0x18006d6bb  test    eax, eax
0x18006d6bd  jz      short loc_18006D6C4
0x18006d6bf  cmp     eax, 7
0x18006d6c2  jnz     short loc_18006D6FD
0x18006d6c4  mov     rax, [rdi]
0x18006d6c7  mov     rdx, r12
0x18006d6ca  mov     rcx, rdi
0x18006d6cd  mov     rax, [rax+28h]
0x18006d6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d6d6  mov     ebx, eax
0x18006d6d8  test    eax, eax
0x18006d6da  jz      short loc_18006D6E1
0x18006d6dc  cmp     eax, 7
0x18006d6df  jnz     short loc_18006D6FD
0x18006d6e1  mov     rax, [rdi]
0x18006d6e4  mov     rdx, r12
0x18006d6e7  mov     rcx, rdi
0x18006d6ea  mov     rax, [rax+38h]
0x18006d6ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d6f3  jmp     loc_18006D5A4
0x18006d6f8  mov     ebx, 4
0x18006d6fd  mov     rax, [rdi]
0x18006d700  mov     edx, 1
0x18006d705  mov     rcx, rdi
0x18006d708  mov     rax, [rax]
0x18006d70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d710  test    r15, r15
0x18006d713  jz      short loc_18006D722
0x18006d715  mov     edx, 10h
0x18006d71a  mov     rcx, r15; Block
0x18006d71d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006d722  mov     rcx, [rbp+TokenHandle]; hObject
0x18006d726  test    rcx, rcx
0x18006d729  jz      short loc_18006D737
0x18006d72b  call    cs:__imp_CloseHandle
0x18006d732  nop     dword ptr [rax+rax+00h]
0x18006d737  test    r14, r14
0x18006d73a  jz      short loc_18006D74B
0x18006d73c  mov     rcx, r14; pwk
0x18006d73f  call    cs:__imp_CloseThreadpoolWork
0x18006d746  nop     dword ptr [rax+rax+00h]
0x18006d74b  mov     eax, ebx
0x18006d74d  mov     rcx, [rbp+var_8]
0x18006d751  xor     rcx, rsp; StackCookie
0x18006d754  call    __security_check_cookie
0x18006d759  mov     rbx, [rsp+80h+arg_18]
0x18006d761  add     rsp, 80h
0x18006d768  pop     r15
0x18006d76a  pop     r14
0x18006d76c  pop     r13
0x18006d76e  pop     r12
0x18006d770  pop     rdi
0x18006d771  pop     rsi
0x18006d772  pop     rbp
0x18006d773  retn
```
