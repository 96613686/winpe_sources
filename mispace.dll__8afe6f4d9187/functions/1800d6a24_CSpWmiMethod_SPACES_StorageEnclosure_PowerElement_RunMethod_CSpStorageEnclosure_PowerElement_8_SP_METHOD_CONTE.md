# CSpWmiMethod<_SPACES_StorageEnclosure_PowerElement>::RunMethod<CSpStorageEnclosure::PowerElement,8>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800d6a24`
- end: `0x1800d6d72`
- name: `??$RunMethod@VPowerElement@CSpStorageEnclosure@@$07@?$CSpWmiMethod@U_SPACES_StorageEnclosure_PowerElement@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800d8f20`

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
- `0x180024dfc`
- `0x18005d58c`
- `0x1800d6a24`
- `0x1800d7294`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6bf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d6bd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d6bd1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d6be6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d6be6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d6bb7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d6bb7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d6c90`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d6c90`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d6d43`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d6d43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d6d35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d6d35`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageEnclosure_PowerElement>::RunMethod<CSpStorageEnclosure::PowerElement,8>(
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
  CSpStorageEnclosure::PowerElement *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageEnclosure::PowerElement *)operator new(0x160u);
  v7 = CSpStorageEnclosure::PowerElement::PowerElement(v25);
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
      v25 = (CSpStorageEnclosure::PowerElement *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)word_18032F9BA,
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
0x1800d6a24  mov     [rsp-38h+arg_18], rbx
0x1800d6a29  push    rbp
0x1800d6a2a  push    rsi
0x1800d6a2b  push    rdi
0x1800d6a2c  push    r12
0x1800d6a2e  push    r13
0x1800d6a30  push    r14
0x1800d6a32  push    r15
0x1800d6a34  mov     rbp, rsp
0x1800d6a37  sub     rsp, 80h
0x1800d6a3e  mov     rax, cs:__security_cookie
0x1800d6a45  xor     rax, rsp
0x1800d6a48  mov     [rbp+var_8], rax
0x1800d6a4c  xor     eax, eax
0x1800d6a4e  mov     rsi, rcx
0x1800d6a51  xorps   xmm0, xmm0
0x1800d6a54  mov     [rbp+var_10], eax
0x1800d6a57  mov     ecx, 160h; Size
0x1800d6a5c  mov     [rbp+var_40], eax
0x1800d6a5f  movups  [rbp+var_20], xmm0
0x1800d6a63  mov     [rbp+TokenHandle], rax
0x1800d6a67  mov     r12, r8
0x1800d6a6a  mov     r13, rdx
0x1800d6a6d  xor     r14d, r14d
0x1800d6a70  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d6a75  mov     rcx, rax; this
0x1800d6a78  mov     [rbp+var_28], rax
0x1800d6a7c  call    ??0PowerElement@CSpStorageEnclosure@@QEAA@XZ; CSpStorageEnclosure::PowerElement::PowerElement(void)
0x1800d6a81  mov     rdi, rax
0x1800d6a84  test    rax, rax
0x1800d6a87  jnz     short loc_1800D6A91
0x1800d6a89  lea     ebx, [rax+1Bh]
0x1800d6a8c  jmp     loc_1800D6D2C
0x1800d6a91  mov     rax, [rax]
0x1800d6a94  mov     rdx, rsi
0x1800d6a97  mov     rcx, rdi
0x1800d6a9a  xor     r15d, r15d
0x1800d6a9d  mov     rax, [rax+8]
0x1800d6aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6aa6  lea     rcx, [rbp+var_40]
0x1800d6aaa  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800d6aaf  mov     [rdi+1Ch], eax
0x1800d6ab2  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800d6ab6  mov     ecx, [rsi+14h]; unsigned int
0x1800d6ab9  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800d6abe  mov     eax, cs:dword_180397B68
0x1800d6ac4  cmp     eax, 5
0x1800d6ac7  jbe     short loc_1800D6B37
0x1800d6ac9  mov     rdx, 400000000000h
0x1800d6ad3  lea     rcx, dword_180397B68
0x1800d6ada  call    _tlgKeywordOn
0x1800d6adf  test    al, al
0x1800d6ae1  jz      short loc_1800D6B37
0x1800d6ae3  mov     eax, [rbp+var_40]
0x1800d6ae6  lea     rdx, word_18032F9BA
0x1800d6aed  xor     ecx, ecx
0x1800d6aef  cmp     [rdi+1Ch], eax
0x1800d6af2  movzx   eax, word ptr [rbp+var_10]
0x1800d6af6  mov     word ptr [rbp+var_40], ax
0x1800d6afa  setnz   cl
0x1800d6afd  mov     eax, [rsi+14h]
0x1800d6b00  mov     [rbp+var_38], eax
0x1800d6b03  lea     rax, [rbp+var_20]
0x1800d6b07  mov     [rbp+var_28], rax
0x1800d6b0b  lea     rax, [rbp+var_3C]
0x1800d6b0f  mov     [rsp+80h+var_48], rax
0x1800d6b14  lea     rax, [rbp+var_40]
0x1800d6b18  mov     [rsp+80h+var_50], rax
0x1800d6b1d  lea     rax, [rbp+var_38]
0x1800d6b21  mov     [rsp+80h+var_58], rax
0x1800d6b26  lea     rax, [rbp+var_28]
0x1800d6b2a  mov     [rsp+80h+var_60], rax
0x1800d6b2f  mov     [rbp+var_3C], ecx
0x1800d6b32  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800d6b37  mov     rcx, [rsi]
0x1800d6b3a  test    rcx, rcx
0x1800d6b3d  jz      loc_1800D6D02
0x1800d6b43  mov     rax, [rcx]
0x1800d6b46  test    rax, rax
0x1800d6b49  jz      loc_1800D6D02
0x1800d6b4f  mov     rax, [rax+18h]
0x1800d6b53  lea     r8, [rdi+20h]
0x1800d6b57  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800d6b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6b63  mov     ebx, eax
0x1800d6b65  test    eax, eax
0x1800d6b67  jnz     loc_1800D6D07
0x1800d6b6d  cmp     [rsi+10h], r14d
0x1800d6b71  jz      loc_1800D6C9B
0x1800d6b77  lea     rbx, [rdi+148h]
0x1800d6b7e  mov     rcx, rbx
0x1800d6b81  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800d6b86  mov     rcx, rbx; struct CSpJobMgr **
0x1800d6b89  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800d6b8e  test    eax, eax
0x1800d6b90  jnz     short loc_1800D6B9A
0x1800d6b92  lea     ebx, [rax+1Ch]
0x1800d6b95  jmp     loc_1800D6D07
0x1800d6b9a  mov     ecx, 10h; Size
0x1800d6b9f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d6ba4  xor     r8d, r8d; pcbe
0x1800d6ba7  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800d6bae  mov     rdx, rax; pv
0x1800d6bb1  mov     r15, rax
0x1800d6bb4  mov     [rax], rdi
0x1800d6bb7  call    cs:__imp_CreateThreadpoolWork
0x1800d6bbd  mov     r14, rax
0x1800d6bc0  test    rax, rax
0x1800d6bc3  jnz     short loc_1800D6BD1
0x1800d6bc5  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800d6bca  mov     ebx, eax
0x1800d6bcc  jmp     loc_1800D6D07
0x1800d6bd1  call    cs:__imp_GetCurrentThread
0x1800d6bd7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d6bdb  xor     r8d, r8d; OpenAsSelf
0x1800d6bde  mov     rcx, rax; ThreadHandle
0x1800d6be1  mov     edx, 2000Ch; DesiredAccess
0x1800d6be6  call    cs:__imp_OpenThreadToken
0x1800d6bec  test    eax, eax
0x1800d6bee  jnz     short loc_1800D6BFD
0x1800d6bf0  call    cs:__imp_GetLastError
0x1800d6bf6  cmp     eax, 3F0h
0x1800d6bfb  jnz     short loc_1800D6BC5
0x1800d6bfd  mov     rax, [rbp+TokenHandle]
0x1800d6c01  mov     r8, r13
0x1800d6c04  mov     [r15+8], rax
0x1800d6c08  mov     rcx, rdi
0x1800d6c0b  mov     rax, [rdi]
0x1800d6c0e  mov     rdx, [rsi+8]
0x1800d6c12  mov     rax, [rax+18h]
0x1800d6c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6c1b  mov     rax, [rdi]
0x1800d6c1e  mov     rdx, r12
0x1800d6c21  mov     rcx, rdi
0x1800d6c24  mov     rax, [rax+28h]
0x1800d6c28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6c2d  mov     ebx, eax
0x1800d6c2f  test    eax, eax
0x1800d6c31  jz      short loc_1800D6C3C
0x1800d6c33  cmp     eax, 7
0x1800d6c36  jnz     loc_1800D6D07
0x1800d6c3c  mov     rax, [rdi]
0x1800d6c3f  mov     rdx, r12
0x1800d6c42  mov     rcx, rdi
0x1800d6c45  mov     rax, [rax+38h]
0x1800d6c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6c4e  mov     ebx, eax
0x1800d6c50  test    eax, eax
0x1800d6c52  jnz     loc_1800D6D07
0x1800d6c58  mov     rax, [rdi+150h]
0x1800d6c5f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800d6c66  jnz     short loc_1800D6C7C
0x1800d6c68  mov     rax, [rdi+158h]
0x1800d6c6f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800d6c76  jz      loc_1800D6D07
0x1800d6c7c  mov     rdx, r12
0x1800d6c7f  mov     rcx, rdi
0x1800d6c82  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800d6c87  mov     ebx, eax
0x1800d6c89  test    eax, eax
0x1800d6c8b  jnz     short loc_1800D6D07
0x1800d6c8d  mov     rcx, r14; pwk
0x1800d6c90  call    cs:__imp_SubmitThreadpoolWork
0x1800d6c96  jmp     loc_1800D6D49
0x1800d6c9b  mov     rax, [rdi]
0x1800d6c9e  mov     r8, r13
0x1800d6ca1  mov     rdx, [rsi+8]
0x1800d6ca5  mov     rcx, rdi
0x1800d6ca8  mov     rax, [rax+10h]
0x1800d6cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6cb1  mov     rax, [rdi]
0x1800d6cb4  mov     rdx, r12
0x1800d6cb7  mov     rcx, rdi
0x1800d6cba  mov     rax, [rax+30h]
0x1800d6cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6cc3  mov     ebx, eax
0x1800d6cc5  test    eax, eax
0x1800d6cc7  jz      short loc_1800D6CCE
0x1800d6cc9  cmp     eax, 7
0x1800d6ccc  jnz     short loc_1800D6D07
0x1800d6cce  mov     rax, [rdi]
0x1800d6cd1  mov     rdx, r12
0x1800d6cd4  mov     rcx, rdi
0x1800d6cd7  mov     rax, [rax+28h]
0x1800d6cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6ce0  mov     ebx, eax
0x1800d6ce2  test    eax, eax
0x1800d6ce4  jz      short loc_1800D6CEB
0x1800d6ce6  cmp     eax, 7
0x1800d6ce9  jnz     short loc_1800D6D07
0x1800d6ceb  mov     rax, [rdi]
0x1800d6cee  mov     rdx, r12
0x1800d6cf1  mov     rcx, rdi
0x1800d6cf4  mov     rax, [rax+38h]
0x1800d6cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6cfd  jmp     loc_1800D6BCA
0x1800d6d02  mov     ebx, 4
0x1800d6d07  mov     rax, [rdi]
0x1800d6d0a  mov     edx, 1
0x1800d6d0f  mov     rcx, rdi
0x1800d6d12  mov     rax, [rax]
0x1800d6d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6d1a  test    r15, r15
0x1800d6d1d  jz      short loc_1800D6D2C
0x1800d6d1f  mov     edx, 10h
0x1800d6d24  mov     rcx, r15; Block
0x1800d6d27  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d6d2c  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d6d30  test    rcx, rcx
0x1800d6d33  jz      short loc_1800D6D3B
0x1800d6d35  call    cs:__imp_CloseHandle
0x1800d6d3b  test    r14, r14
0x1800d6d3e  jz      short loc_1800D6D49
0x1800d6d40  mov     rcx, r14; pwk
0x1800d6d43  call    cs:__imp_CloseThreadpoolWork
0x1800d6d49  mov     eax, ebx
0x1800d6d4b  mov     rcx, [rbp+var_8]
0x1800d6d4f  xor     rcx, rsp; StackCookie
0x1800d6d52  call    __security_check_cookie
0x1800d6d57  mov     rbx, [rsp+80h+arg_18]
0x1800d6d5f  add     rsp, 80h
0x1800d6d66  pop     r15
0x1800d6d68  pop     r14
0x1800d6d6a  pop     r13
0x1800d6d6c  pop     r12
0x1800d6d6e  pop     rdi
0x1800d6d6f  pop     rsi
0x1800d6d70  pop     rbp
0x1800d6d71  retn
```
