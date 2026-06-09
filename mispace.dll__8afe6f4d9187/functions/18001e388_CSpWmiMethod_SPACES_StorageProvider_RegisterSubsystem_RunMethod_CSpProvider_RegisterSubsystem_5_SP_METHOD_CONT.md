# CSpWmiMethod<_SPACES_StorageProvider_RegisterSubsystem>::RunMethod<CSpProvider::_RegisterSubsystem,5>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18001e388`
- end: `0x18001e6d6`
- name: `??$RunMethod@V_RegisterSubsystem@CSpProvider@@$04@?$CSpWmiMethod@U_SPACES_StorageProvider_RegisterSubsystem@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800227d0`

## callees

- `0x1800014ec`
- `0x180001970`
- `0x180006290`
- `0x1800062e0`
- `0x1800062ec`
- `0x18000c704`
- `0x180013898`
- `0x180014000`
- `0x180014720`
- `0x18001e388`
- `0x18001eb30`
- `0x180024dfc`
- `0x18005d58c`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e554`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e535`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e535`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e54a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e54a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001e51b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001e51b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e5f4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e5f4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001e6a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001e6a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e699`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e699`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageProvider_RegisterSubsystem>::RunMethod<CSpProvider::_RegisterSubsystem,5>(
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
  CSpProvider::_RegisterSubsystem *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpProvider::_RegisterSubsystem *)operator new(0x170u);
  v7 = CSpProvider::_RegisterSubsystem::_RegisterSubsystem(v25);
  v8 = v7;
  if ( v7 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 8LL))(v7, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpProvider::_RegisterSubsystem *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_1802F1651,
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
0x18001e388  mov     [rsp-38h+arg_18], rbx
0x18001e38d  push    rbp
0x18001e38e  push    rsi
0x18001e38f  push    rdi
0x18001e390  push    r12
0x18001e392  push    r13
0x18001e394  push    r14
0x18001e396  push    r15
0x18001e398  mov     rbp, rsp
0x18001e39b  sub     rsp, 80h
0x18001e3a2  mov     rax, cs:__security_cookie
0x18001e3a9  xor     rax, rsp
0x18001e3ac  mov     [rbp+var_8], rax
0x18001e3b0  xor     eax, eax
0x18001e3b2  mov     rsi, rcx
0x18001e3b5  xorps   xmm0, xmm0
0x18001e3b8  mov     [rbp+var_10], eax
0x18001e3bb  mov     ecx, 170h; Size
0x18001e3c0  mov     [rbp+var_40], eax
0x18001e3c3  movups  [rbp+var_20], xmm0
0x18001e3c7  mov     [rbp+TokenHandle], rax
0x18001e3cb  mov     r12, r8
0x18001e3ce  mov     r13, rdx
0x18001e3d1  xor     r14d, r14d
0x18001e3d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e3d9  mov     rcx, rax; this
0x18001e3dc  mov     [rbp+var_28], rax
0x18001e3e0  call    ??0_RegisterSubsystem@CSpProvider@@QEAA@XZ; CSpProvider::_RegisterSubsystem::_RegisterSubsystem(void)
0x18001e3e5  mov     rdi, rax
0x18001e3e8  test    rax, rax
0x18001e3eb  jnz     short loc_18001E3F5
0x18001e3ed  lea     ebx, [rax+1Bh]
0x18001e3f0  jmp     loc_18001E690
0x18001e3f5  mov     rax, [rax]
0x18001e3f8  mov     rdx, rsi
0x18001e3fb  mov     rcx, rdi
0x18001e3fe  xor     r15d, r15d
0x18001e401  mov     rax, [rax+8]
0x18001e405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e40a  lea     rcx, [rbp+var_40]
0x18001e40e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18001e413  mov     [rdi+1Ch], eax
0x18001e416  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18001e41a  mov     ecx, [rsi+14h]; unsigned int
0x18001e41d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18001e422  mov     eax, cs:dword_180397B68
0x18001e428  cmp     eax, 5
0x18001e42b  jbe     short loc_18001E49B
0x18001e42d  mov     rdx, 400000000000h
0x18001e437  lea     rcx, dword_180397B68
0x18001e43e  call    _tlgKeywordOn
0x18001e443  test    al, al
0x18001e445  jz      short loc_18001E49B
0x18001e447  mov     eax, [rbp+var_40]
0x18001e44a  lea     rdx, byte_1802F1651
0x18001e451  xor     ecx, ecx
0x18001e453  cmp     [rdi+1Ch], eax
0x18001e456  movzx   eax, word ptr [rbp+var_10]
0x18001e45a  mov     word ptr [rbp+var_40], ax
0x18001e45e  setnz   cl
0x18001e461  mov     eax, [rsi+14h]
0x18001e464  mov     [rbp+var_38], eax
0x18001e467  lea     rax, [rbp+var_20]
0x18001e46b  mov     [rbp+var_28], rax
0x18001e46f  lea     rax, [rbp+var_3C]
0x18001e473  mov     [rsp+80h+var_48], rax
0x18001e478  lea     rax, [rbp+var_40]
0x18001e47c  mov     [rsp+80h+var_50], rax
0x18001e481  lea     rax, [rbp+var_38]
0x18001e485  mov     [rsp+80h+var_58], rax
0x18001e48a  lea     rax, [rbp+var_28]
0x18001e48e  mov     [rsp+80h+var_60], rax
0x18001e493  mov     [rbp+var_3C], ecx
0x18001e496  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18001e49b  mov     rcx, [rsi]
0x18001e49e  test    rcx, rcx
0x18001e4a1  jz      loc_18001E666
0x18001e4a7  mov     rax, [rcx]
0x18001e4aa  test    rax, rax
0x18001e4ad  jz      loc_18001E666
0x18001e4b3  mov     rax, [rax+18h]
0x18001e4b7  lea     r8, [rdi+20h]
0x18001e4bb  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18001e4c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4c7  mov     ebx, eax
0x18001e4c9  test    eax, eax
0x18001e4cb  jnz     loc_18001E66B
0x18001e4d1  cmp     [rsi+10h], r14d
0x18001e4d5  jz      loc_18001E5FF
0x18001e4db  lea     rbx, [rdi+148h]
0x18001e4e2  mov     rcx, rbx
0x18001e4e5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18001e4ea  mov     rcx, rbx; struct CSpJobMgr **
0x18001e4ed  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18001e4f2  test    eax, eax
0x18001e4f4  jnz     short loc_18001E4FE
0x18001e4f6  lea     ebx, [rax+1Ch]
0x18001e4f9  jmp     loc_18001E66B
0x18001e4fe  mov     ecx, 10h; Size
0x18001e503  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e508  xor     r8d, r8d; pcbe
0x18001e50b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001e512  mov     rdx, rax; pv
0x18001e515  mov     r15, rax
0x18001e518  mov     [rax], rdi
0x18001e51b  call    cs:__imp_CreateThreadpoolWork
0x18001e521  mov     r14, rax
0x18001e524  test    rax, rax
0x18001e527  jnz     short loc_18001E535
0x18001e529  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18001e52e  mov     ebx, eax
0x18001e530  jmp     loc_18001E66B
0x18001e535  call    cs:__imp_GetCurrentThread
0x18001e53b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001e53f  xor     r8d, r8d; OpenAsSelf
0x18001e542  mov     rcx, rax; ThreadHandle
0x18001e545  mov     edx, 2000Ch; DesiredAccess
0x18001e54a  call    cs:__imp_OpenThreadToken
0x18001e550  test    eax, eax
0x18001e552  jnz     short loc_18001E561
0x18001e554  call    cs:__imp_GetLastError
0x18001e55a  cmp     eax, 3F0h
0x18001e55f  jnz     short loc_18001E529
0x18001e561  mov     rax, [rbp+TokenHandle]
0x18001e565  mov     r8, r13
0x18001e568  mov     [r15+8], rax
0x18001e56c  mov     rcx, rdi
0x18001e56f  mov     rax, [rdi]
0x18001e572  mov     rdx, [rsi+8]
0x18001e576  mov     rax, [rax+18h]
0x18001e57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e57f  mov     rax, [rdi]
0x18001e582  mov     rdx, r12
0x18001e585  mov     rcx, rdi
0x18001e588  mov     rax, [rax+28h]
0x18001e58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e591  mov     ebx, eax
0x18001e593  test    eax, eax
0x18001e595  jz      short loc_18001E5A0
0x18001e597  cmp     eax, 7
0x18001e59a  jnz     loc_18001E66B
0x18001e5a0  mov     rax, [rdi]
0x18001e5a3  mov     rdx, r12
0x18001e5a6  mov     rcx, rdi
0x18001e5a9  mov     rax, [rax+38h]
0x18001e5ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5b2  mov     ebx, eax
0x18001e5b4  test    eax, eax
0x18001e5b6  jnz     loc_18001E66B
0x18001e5bc  mov     rax, [rdi+150h]
0x18001e5c3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18001e5ca  jnz     short loc_18001E5E0
0x18001e5cc  mov     rax, [rdi+158h]
0x18001e5d3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18001e5da  jz      loc_18001E66B
0x18001e5e0  mov     rdx, r12
0x18001e5e3  mov     rcx, rdi
0x18001e5e6  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18001e5eb  mov     ebx, eax
0x18001e5ed  test    eax, eax
0x18001e5ef  jnz     short loc_18001E66B
0x18001e5f1  mov     rcx, r14; pwk
0x18001e5f4  call    cs:__imp_SubmitThreadpoolWork
0x18001e5fa  jmp     loc_18001E6AD
0x18001e5ff  mov     rax, [rdi]
0x18001e602  mov     r8, r13
0x18001e605  mov     rdx, [rsi+8]
0x18001e609  mov     rcx, rdi
0x18001e60c  mov     rax, [rax+10h]
0x18001e610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e615  mov     rax, [rdi]
0x18001e618  mov     rdx, r12
0x18001e61b  mov     rcx, rdi
0x18001e61e  mov     rax, [rax+30h]
0x18001e622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e627  mov     ebx, eax
0x18001e629  test    eax, eax
0x18001e62b  jz      short loc_18001E632
0x18001e62d  cmp     eax, 7
0x18001e630  jnz     short loc_18001E66B
0x18001e632  mov     rax, [rdi]
0x18001e635  mov     rdx, r12
0x18001e638  mov     rcx, rdi
0x18001e63b  mov     rax, [rax+28h]
0x18001e63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e644  mov     ebx, eax
0x18001e646  test    eax, eax
0x18001e648  jz      short loc_18001E64F
0x18001e64a  cmp     eax, 7
0x18001e64d  jnz     short loc_18001E66B
0x18001e64f  mov     rax, [rdi]
0x18001e652  mov     rdx, r12
0x18001e655  mov     rcx, rdi
0x18001e658  mov     rax, [rax+38h]
0x18001e65c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e661  jmp     loc_18001E52E
0x18001e666  mov     ebx, 4
0x18001e66b  mov     rax, [rdi]
0x18001e66e  mov     edx, 1
0x18001e673  mov     rcx, rdi
0x18001e676  mov     rax, [rax]
0x18001e679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e67e  test    r15, r15
0x18001e681  jz      short loc_18001E690
0x18001e683  mov     edx, 10h
0x18001e688  mov     rcx, r15; Block
0x18001e68b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e690  mov     rcx, [rbp+TokenHandle]; hObject
0x18001e694  test    rcx, rcx
0x18001e697  jz      short loc_18001E69F
0x18001e699  call    cs:__imp_CloseHandle
0x18001e69f  test    r14, r14
0x18001e6a2  jz      short loc_18001E6AD
0x18001e6a4  mov     rcx, r14; pwk
0x18001e6a7  call    cs:__imp_CloseThreadpoolWork
0x18001e6ad  mov     eax, ebx
0x18001e6af  mov     rcx, [rbp+var_8]
0x18001e6b3  xor     rcx, rsp; StackCookie
0x18001e6b6  call    __security_check_cookie
0x18001e6bb  mov     rbx, [rsp+80h+arg_18]
0x18001e6c3  add     rsp, 80h
0x18001e6ca  pop     r15
0x18001e6cc  pop     r14
0x18001e6ce  pop     r13
0x18001e6d0  pop     r12
0x18001e6d2  pop     rdi
0x18001e6d3  pop     rsi
0x18001e6d4  pop     rbp
0x18001e6d5  retn
```
