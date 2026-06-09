# CSpWmiMethod<_SPACES_VirtualDisk_Attach>::RunMethod<CSpVirtualDisk::Attach,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e0b58`
- end: `0x1800e0ed5`
- name: `??$RunMethod@VAttach@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_Attach@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800e0b58`
- `0x1800e3d70`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0d36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0d0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0d0b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e0d26`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e0d26`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e0ceb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e0ceb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e0de0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e0de0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e0e9f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e0e9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0e8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0e8b`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_Attach>::RunMethod<CSpVirtualDisk::Attach,16>(
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
  CSpVirtualDisk::Attach *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::Attach *)operator new(0x160u);
  v7 = CSpVirtualDisk::Attach::Attach(v25);
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
      v25 = (CSpVirtualDisk::Attach *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_180339828,
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
0x1800e0b58  mov     [rsp-38h+arg_18], rbx
0x1800e0b5d  push    rbp
0x1800e0b5e  push    rsi
0x1800e0b5f  push    rdi
0x1800e0b60  push    r12
0x1800e0b62  push    r13
0x1800e0b64  push    r14
0x1800e0b66  push    r15
0x1800e0b68  mov     rbp, rsp
0x1800e0b6b  sub     rsp, 80h
0x1800e0b72  mov     rax, cs:__security_cookie
0x1800e0b79  xor     rax, rsp
0x1800e0b7c  mov     [rbp+var_8], rax
0x1800e0b80  xor     eax, eax
0x1800e0b82  mov     rsi, rcx
0x1800e0b85  xorps   xmm0, xmm0
0x1800e0b88  mov     [rbp+var_10], eax
0x1800e0b8b  mov     ecx, 160h; Size
0x1800e0b90  mov     [rbp+var_40], eax
0x1800e0b93  movups  [rbp+var_20], xmm0
0x1800e0b97  mov     [rbp+TokenHandle], rax
0x1800e0b9b  mov     r12, r8
0x1800e0b9e  mov     r13, rdx
0x1800e0ba1  xor     r14d, r14d
0x1800e0ba4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e0ba9  mov     rcx, rax; this
0x1800e0bac  mov     [rbp+var_28], rax
0x1800e0bb0  call    ??0Attach@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::Attach::Attach(void)
0x1800e0bb5  mov     rdi, rax
0x1800e0bb8  test    rax, rax
0x1800e0bbb  jnz     short loc_1800E0BC5
0x1800e0bbd  lea     ebx, [rax+1Bh]
0x1800e0bc0  jmp     loc_1800E0E82
0x1800e0bc5  mov     rax, [rax]
0x1800e0bc8  mov     rdx, rsi
0x1800e0bcb  mov     rcx, rdi
0x1800e0bce  xor     r15d, r15d
0x1800e0bd1  mov     rax, [rax+8]
0x1800e0bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0bda  lea     rcx, [rbp+var_40]
0x1800e0bde  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e0be3  mov     [rdi+1Ch], eax
0x1800e0be6  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e0bea  mov     ecx, [rsi+14h]; unsigned int
0x1800e0bed  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e0bf2  mov     eax, cs:dword_18039EB68
0x1800e0bf8  cmp     eax, 5
0x1800e0bfb  jbe     short loc_1800E0C6B
0x1800e0bfd  mov     rdx, 400000000000h
0x1800e0c07  lea     rcx, dword_18039EB68
0x1800e0c0e  call    _tlgKeywordOn
0x1800e0c13  test    al, al
0x1800e0c15  jz      short loc_1800E0C6B
0x1800e0c17  mov     eax, [rbp+var_40]
0x1800e0c1a  lea     rdx, unk_180339828
0x1800e0c21  xor     ecx, ecx
0x1800e0c23  cmp     [rdi+1Ch], eax
0x1800e0c26  movzx   eax, word ptr [rbp+var_10]
0x1800e0c2a  mov     word ptr [rbp+var_40], ax
0x1800e0c2e  setnz   cl
0x1800e0c31  mov     eax, [rsi+14h]
0x1800e0c34  mov     [rbp+var_38], eax
0x1800e0c37  lea     rax, [rbp+var_20]
0x1800e0c3b  mov     [rbp+var_28], rax
0x1800e0c3f  lea     rax, [rbp+var_3C]
0x1800e0c43  mov     [rsp+80h+var_48], rax
0x1800e0c48  lea     rax, [rbp+var_40]
0x1800e0c4c  mov     [rsp+80h+var_50], rax
0x1800e0c51  lea     rax, [rbp+var_38]
0x1800e0c55  mov     [rsp+80h+var_58], rax
0x1800e0c5a  lea     rax, [rbp+var_28]
0x1800e0c5e  mov     [rsp+80h+var_60], rax
0x1800e0c63  mov     [rbp+var_3C], ecx
0x1800e0c66  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e0c6b  mov     rcx, [rsi]
0x1800e0c6e  test    rcx, rcx
0x1800e0c71  jz      loc_1800E0E58
0x1800e0c77  mov     rax, [rcx]
0x1800e0c7a  test    rax, rax
0x1800e0c7d  jz      loc_1800E0E58
0x1800e0c83  mov     rax, [rax+18h]
0x1800e0c87  lea     r8, [rdi+20h]
0x1800e0c8b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e0c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0c97  mov     ebx, eax
0x1800e0c99  test    eax, eax
0x1800e0c9b  jnz     loc_1800E0E5D
0x1800e0ca1  cmp     [rsi+10h], r14d
0x1800e0ca5  jz      loc_1800E0DF1
0x1800e0cab  lea     rbx, [rdi+148h]
0x1800e0cb2  mov     rcx, rbx
0x1800e0cb5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e0cba  mov     rcx, rbx; struct CSpJobMgr **
0x1800e0cbd  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e0cc2  test    eax, eax
0x1800e0cc4  jnz     short loc_1800E0CCE
0x1800e0cc6  lea     ebx, [rax+1Ch]
0x1800e0cc9  jmp     loc_1800E0E5D
0x1800e0cce  mov     ecx, 10h; Size
0x1800e0cd3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e0cd8  xor     r8d, r8d; pcbe
0x1800e0cdb  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e0ce2  mov     rdx, rax; pv
0x1800e0ce5  mov     r15, rax
0x1800e0ce8  mov     [rax], rdi
0x1800e0ceb  call    cs:__imp_CreateThreadpoolWork
0x1800e0cf2  nop     dword ptr [rax+rax+00h]
0x1800e0cf7  mov     r14, rax
0x1800e0cfa  test    rax, rax
0x1800e0cfd  jnz     short loc_1800E0D0B
0x1800e0cff  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e0d04  mov     ebx, eax
0x1800e0d06  jmp     loc_1800E0E5D
0x1800e0d0b  call    cs:__imp_GetCurrentThread
0x1800e0d12  nop     dword ptr [rax+rax+00h]
0x1800e0d17  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e0d1b  xor     r8d, r8d; OpenAsSelf
0x1800e0d1e  mov     rcx, rax; ThreadHandle
0x1800e0d21  mov     edx, 2000Ch; DesiredAccess
0x1800e0d26  call    cs:__imp_OpenThreadToken
0x1800e0d2d  nop     dword ptr [rax+rax+00h]
0x1800e0d32  test    eax, eax
0x1800e0d34  jnz     short loc_1800E0D49
0x1800e0d36  call    cs:__imp_GetLastError
0x1800e0d3d  nop     dword ptr [rax+rax+00h]
0x1800e0d42  cmp     eax, 3F0h
0x1800e0d47  jnz     short loc_1800E0CFF
0x1800e0d49  mov     rax, [rbp+TokenHandle]
0x1800e0d4d  mov     r8, r13
0x1800e0d50  mov     [r15+8], rax
0x1800e0d54  mov     rcx, rdi
0x1800e0d57  mov     rax, [rdi]
0x1800e0d5a  mov     rdx, [rsi+8]
0x1800e0d5e  mov     rax, [rax+18h]
0x1800e0d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0d67  mov     rax, [rdi]
0x1800e0d6a  mov     rdx, r12
0x1800e0d6d  mov     rcx, rdi
0x1800e0d70  mov     rax, [rax+28h]
0x1800e0d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0d79  mov     ebx, eax
0x1800e0d7b  test    eax, eax
0x1800e0d7d  jz      short loc_1800E0D88
0x1800e0d7f  cmp     eax, 7
0x1800e0d82  jnz     loc_1800E0E5D
0x1800e0d88  mov     rax, [rdi]
0x1800e0d8b  mov     rdx, r12
0x1800e0d8e  mov     rcx, rdi
0x1800e0d91  mov     rax, [rax+38h]
0x1800e0d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0d9a  mov     ebx, eax
0x1800e0d9c  test    eax, eax
0x1800e0d9e  jnz     loc_1800E0E5D
0x1800e0da4  mov     rax, [rdi+150h]
0x1800e0dab  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e0db2  jnz     short loc_1800E0DC8
0x1800e0db4  mov     rax, [rdi+158h]
0x1800e0dbb  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e0dc2  jz      loc_1800E0E5D
0x1800e0dc8  mov     rdx, r12
0x1800e0dcb  mov     rcx, rdi
0x1800e0dce  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e0dd3  mov     ebx, eax
0x1800e0dd5  test    eax, eax
0x1800e0dd7  jnz     loc_1800E0E5D
0x1800e0ddd  mov     rcx, r14; pwk
0x1800e0de0  call    cs:__imp_SubmitThreadpoolWork
0x1800e0de7  nop     dword ptr [rax+rax+00h]
0x1800e0dec  jmp     loc_1800E0EAB
0x1800e0df1  mov     rax, [rdi]
0x1800e0df4  mov     r8, r13
0x1800e0df7  mov     rdx, [rsi+8]
0x1800e0dfb  mov     rcx, rdi
0x1800e0dfe  mov     rax, [rax+10h]
0x1800e0e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0e07  mov     rax, [rdi]
0x1800e0e0a  mov     rdx, r12
0x1800e0e0d  mov     rcx, rdi
0x1800e0e10  mov     rax, [rax+30h]
0x1800e0e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0e19  mov     ebx, eax
0x1800e0e1b  test    eax, eax
0x1800e0e1d  jz      short loc_1800E0E24
0x1800e0e1f  cmp     eax, 7
0x1800e0e22  jnz     short loc_1800E0E5D
0x1800e0e24  mov     rax, [rdi]
0x1800e0e27  mov     rdx, r12
0x1800e0e2a  mov     rcx, rdi
0x1800e0e2d  mov     rax, [rax+28h]
0x1800e0e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0e36  mov     ebx, eax
0x1800e0e38  test    eax, eax
0x1800e0e3a  jz      short loc_1800E0E41
0x1800e0e3c  cmp     eax, 7
0x1800e0e3f  jnz     short loc_1800E0E5D
0x1800e0e41  mov     rax, [rdi]
0x1800e0e44  mov     rdx, r12
0x1800e0e47  mov     rcx, rdi
0x1800e0e4a  mov     rax, [rax+38h]
0x1800e0e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0e53  jmp     loc_1800E0D04
0x1800e0e58  mov     ebx, 4
0x1800e0e5d  mov     rax, [rdi]
0x1800e0e60  mov     edx, 1
0x1800e0e65  mov     rcx, rdi
0x1800e0e68  mov     rax, [rax]
0x1800e0e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0e70  test    r15, r15
0x1800e0e73  jz      short loc_1800E0E82
0x1800e0e75  mov     edx, 10h
0x1800e0e7a  mov     rcx, r15; Block
0x1800e0e7d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e0e82  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e0e86  test    rcx, rcx
0x1800e0e89  jz      short loc_1800E0E97
0x1800e0e8b  call    cs:__imp_CloseHandle
0x1800e0e92  nop     dword ptr [rax+rax+00h]
0x1800e0e97  test    r14, r14
0x1800e0e9a  jz      short loc_1800E0EAB
0x1800e0e9c  mov     rcx, r14; pwk
0x1800e0e9f  call    cs:__imp_CloseThreadpoolWork
0x1800e0ea6  nop     dword ptr [rax+rax+00h]
0x1800e0eab  mov     eax, ebx
0x1800e0ead  mov     rcx, [rbp+var_8]
0x1800e0eb1  xor     rcx, rsp; StackCookie
0x1800e0eb4  call    __security_check_cookie
0x1800e0eb9  mov     rbx, [rsp+80h+arg_18]
0x1800e0ec1  add     rsp, 80h
0x1800e0ec8  pop     r15
0x1800e0eca  pop     r14
0x1800e0ecc  pop     r13
0x1800e0ece  pop     r12
0x1800e0ed0  pop     rdi
0x1800e0ed1  pop     rsi
0x1800e0ed2  pop     rbp
0x1800e0ed3  retn
```
