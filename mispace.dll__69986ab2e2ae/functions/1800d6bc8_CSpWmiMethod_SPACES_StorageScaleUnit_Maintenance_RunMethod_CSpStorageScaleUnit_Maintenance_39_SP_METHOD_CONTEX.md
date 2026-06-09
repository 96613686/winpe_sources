# CSpWmiMethod<_SPACES_StorageScaleUnit_Maintenance>::RunMethod<CSpStorageScaleUnit::Maintenance,39>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800d6bc8`
- end: `0x1800d6f45`
- name: `??$RunMethod@VMaintenance@CSpStorageScaleUnit@@$0CH@@?$CSpWmiMethod@U_SPACES_StorageScaleUnit_Maintenance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800d77b0`

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
- `0x18005f41c`
- `0x1800d6bc8`
- `0x1800d7004`
- `0x1800d7c5c`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6da6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6da6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d6d7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d6d7b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d6d96`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d6d96`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d6d5b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d6d5b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d6e50`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d6e50`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d6f0f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d6f0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d6efb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d6efb`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageScaleUnit_Maintenance>::RunMethod<CSpStorageScaleUnit::Maintenance,39>(
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
  CSpStorageScaleUnit::Maintenance *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageScaleUnit::Maintenance *)operator new(0x180u);
  v7 = CSpStorageScaleUnit::Maintenance::Maintenance(v25);
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
      v25 = (CSpStorageScaleUnit::Maintenance *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_180334F4F,
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
                v9 = CSpWmiMethod<_SPACES_StorageReliabilityCounter_Reset>::SetCreatedJob(v8, a3);
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
0x1800d6bc8  mov     [rsp-38h+arg_18], rbx
0x1800d6bcd  push    rbp
0x1800d6bce  push    rsi
0x1800d6bcf  push    rdi
0x1800d6bd0  push    r12
0x1800d6bd2  push    r13
0x1800d6bd4  push    r14
0x1800d6bd6  push    r15
0x1800d6bd8  mov     rbp, rsp
0x1800d6bdb  sub     rsp, 80h
0x1800d6be2  mov     rax, cs:__security_cookie
0x1800d6be9  xor     rax, rsp
0x1800d6bec  mov     [rbp+var_8], rax
0x1800d6bf0  xor     eax, eax
0x1800d6bf2  mov     rsi, rcx
0x1800d6bf5  xorps   xmm0, xmm0
0x1800d6bf8  mov     [rbp+var_10], eax
0x1800d6bfb  mov     ecx, 180h; Size
0x1800d6c00  mov     [rbp+var_40], eax
0x1800d6c03  movups  [rbp+var_20], xmm0
0x1800d6c07  mov     [rbp+TokenHandle], rax
0x1800d6c0b  mov     r12, r8
0x1800d6c0e  mov     r13, rdx
0x1800d6c11  xor     r14d, r14d
0x1800d6c14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d6c19  mov     rcx, rax; this
0x1800d6c1c  mov     [rbp+var_28], rax
0x1800d6c20  call    ??0Maintenance@CSpStorageScaleUnit@@QEAA@XZ; CSpStorageScaleUnit::Maintenance::Maintenance(void)
0x1800d6c25  mov     rdi, rax
0x1800d6c28  test    rax, rax
0x1800d6c2b  jnz     short loc_1800D6C35
0x1800d6c2d  lea     ebx, [rax+1Bh]
0x1800d6c30  jmp     loc_1800D6EF2
0x1800d6c35  mov     rax, [rax]
0x1800d6c38  mov     rdx, rsi
0x1800d6c3b  mov     rcx, rdi
0x1800d6c3e  xor     r15d, r15d
0x1800d6c41  mov     rax, [rax+8]
0x1800d6c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6c4a  lea     rcx, [rbp+var_40]
0x1800d6c4e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800d6c53  mov     [rdi+1Ch], eax
0x1800d6c56  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800d6c5a  mov     ecx, [rsi+14h]; unsigned int
0x1800d6c5d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800d6c62  mov     eax, cs:dword_18039EB68
0x1800d6c68  cmp     eax, 5
0x1800d6c6b  jbe     short loc_1800D6CDB
0x1800d6c6d  mov     rdx, 400000000000h
0x1800d6c77  lea     rcx, dword_18039EB68
0x1800d6c7e  call    _tlgKeywordOn
0x1800d6c83  test    al, al
0x1800d6c85  jz      short loc_1800D6CDB
0x1800d6c87  mov     eax, [rbp+var_40]
0x1800d6c8a  lea     rdx, byte_180334F4F
0x1800d6c91  xor     ecx, ecx
0x1800d6c93  cmp     [rdi+1Ch], eax
0x1800d6c96  movzx   eax, word ptr [rbp+var_10]
0x1800d6c9a  mov     word ptr [rbp+var_40], ax
0x1800d6c9e  setnz   cl
0x1800d6ca1  mov     eax, [rsi+14h]
0x1800d6ca4  mov     [rbp+var_38], eax
0x1800d6ca7  lea     rax, [rbp+var_20]
0x1800d6cab  mov     [rbp+var_28], rax
0x1800d6caf  lea     rax, [rbp+var_3C]
0x1800d6cb3  mov     [rsp+80h+var_48], rax
0x1800d6cb8  lea     rax, [rbp+var_40]
0x1800d6cbc  mov     [rsp+80h+var_50], rax
0x1800d6cc1  lea     rax, [rbp+var_38]
0x1800d6cc5  mov     [rsp+80h+var_58], rax
0x1800d6cca  lea     rax, [rbp+var_28]
0x1800d6cce  mov     [rsp+80h+var_60], rax
0x1800d6cd3  mov     [rbp+var_3C], ecx
0x1800d6cd6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800d6cdb  mov     rcx, [rsi]
0x1800d6cde  test    rcx, rcx
0x1800d6ce1  jz      loc_1800D6EC8
0x1800d6ce7  mov     rax, [rcx]
0x1800d6cea  test    rax, rax
0x1800d6ced  jz      loc_1800D6EC8
0x1800d6cf3  mov     rax, [rax+18h]
0x1800d6cf7  lea     r8, [rdi+20h]
0x1800d6cfb  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800d6d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6d07  mov     ebx, eax
0x1800d6d09  test    eax, eax
0x1800d6d0b  jnz     loc_1800D6ECD
0x1800d6d11  cmp     [rsi+10h], r14d
0x1800d6d15  jz      loc_1800D6E61
0x1800d6d1b  lea     rbx, [rdi+148h]
0x1800d6d22  mov     rcx, rbx
0x1800d6d25  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800d6d2a  mov     rcx, rbx; struct CSpJobMgr **
0x1800d6d2d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800d6d32  test    eax, eax
0x1800d6d34  jnz     short loc_1800D6D3E
0x1800d6d36  lea     ebx, [rax+1Ch]
0x1800d6d39  jmp     loc_1800D6ECD
0x1800d6d3e  mov     ecx, 10h; Size
0x1800d6d43  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d6d48  xor     r8d, r8d; pcbe
0x1800d6d4b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800d6d52  mov     rdx, rax; pv
0x1800d6d55  mov     r15, rax
0x1800d6d58  mov     [rax], rdi
0x1800d6d5b  call    cs:__imp_CreateThreadpoolWork
0x1800d6d62  nop     dword ptr [rax+rax+00h]
0x1800d6d67  mov     r14, rax
0x1800d6d6a  test    rax, rax
0x1800d6d6d  jnz     short loc_1800D6D7B
0x1800d6d6f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800d6d74  mov     ebx, eax
0x1800d6d76  jmp     loc_1800D6ECD
0x1800d6d7b  call    cs:__imp_GetCurrentThread
0x1800d6d82  nop     dword ptr [rax+rax+00h]
0x1800d6d87  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d6d8b  xor     r8d, r8d; OpenAsSelf
0x1800d6d8e  mov     rcx, rax; ThreadHandle
0x1800d6d91  mov     edx, 2000Ch; DesiredAccess
0x1800d6d96  call    cs:__imp_OpenThreadToken
0x1800d6d9d  nop     dword ptr [rax+rax+00h]
0x1800d6da2  test    eax, eax
0x1800d6da4  jnz     short loc_1800D6DB9
0x1800d6da6  call    cs:__imp_GetLastError
0x1800d6dad  nop     dword ptr [rax+rax+00h]
0x1800d6db2  cmp     eax, 3F0h
0x1800d6db7  jnz     short loc_1800D6D6F
0x1800d6db9  mov     rax, [rbp+TokenHandle]
0x1800d6dbd  mov     r8, r13
0x1800d6dc0  mov     [r15+8], rax
0x1800d6dc4  mov     rcx, rdi
0x1800d6dc7  mov     rax, [rdi]
0x1800d6dca  mov     rdx, [rsi+8]
0x1800d6dce  mov     rax, [rax+18h]
0x1800d6dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6dd7  mov     rax, [rdi]
0x1800d6dda  mov     rdx, r12
0x1800d6ddd  mov     rcx, rdi
0x1800d6de0  mov     rax, [rax+28h]
0x1800d6de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6de9  mov     ebx, eax
0x1800d6deb  test    eax, eax
0x1800d6ded  jz      short loc_1800D6DF8
0x1800d6def  cmp     eax, 7
0x1800d6df2  jnz     loc_1800D6ECD
0x1800d6df8  mov     rax, [rdi]
0x1800d6dfb  mov     rdx, r12
0x1800d6dfe  mov     rcx, rdi
0x1800d6e01  mov     rax, [rax+38h]
0x1800d6e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6e0a  mov     ebx, eax
0x1800d6e0c  test    eax, eax
0x1800d6e0e  jnz     loc_1800D6ECD
0x1800d6e14  mov     rax, [rdi+150h]
0x1800d6e1b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800d6e22  jnz     short loc_1800D6E38
0x1800d6e24  mov     rax, [rdi+158h]
0x1800d6e2b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800d6e32  jz      loc_1800D6ECD
0x1800d6e38  mov     rdx, r12
0x1800d6e3b  mov     rcx, rdi
0x1800d6e3e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StorageReliabilityCounter_Reset@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StorageReliabilityCounter_Reset@@@Z; CSpWmiMethod<_SPACES_StorageReliabilityCounter_Reset>::SetCreatedJob(_SPACES_StorageReliabilityCounter_Reset *)
0x1800d6e43  mov     ebx, eax
0x1800d6e45  test    eax, eax
0x1800d6e47  jnz     loc_1800D6ECD
0x1800d6e4d  mov     rcx, r14; pwk
0x1800d6e50  call    cs:__imp_SubmitThreadpoolWork
0x1800d6e57  nop     dword ptr [rax+rax+00h]
0x1800d6e5c  jmp     loc_1800D6F1B
0x1800d6e61  mov     rax, [rdi]
0x1800d6e64  mov     r8, r13
0x1800d6e67  mov     rdx, [rsi+8]
0x1800d6e6b  mov     rcx, rdi
0x1800d6e6e  mov     rax, [rax+10h]
0x1800d6e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6e77  mov     rax, [rdi]
0x1800d6e7a  mov     rdx, r12
0x1800d6e7d  mov     rcx, rdi
0x1800d6e80  mov     rax, [rax+30h]
0x1800d6e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6e89  mov     ebx, eax
0x1800d6e8b  test    eax, eax
0x1800d6e8d  jz      short loc_1800D6E94
0x1800d6e8f  cmp     eax, 7
0x1800d6e92  jnz     short loc_1800D6ECD
0x1800d6e94  mov     rax, [rdi]
0x1800d6e97  mov     rdx, r12
0x1800d6e9a  mov     rcx, rdi
0x1800d6e9d  mov     rax, [rax+28h]
0x1800d6ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6ea6  mov     ebx, eax
0x1800d6ea8  test    eax, eax
0x1800d6eaa  jz      short loc_1800D6EB1
0x1800d6eac  cmp     eax, 7
0x1800d6eaf  jnz     short loc_1800D6ECD
0x1800d6eb1  mov     rax, [rdi]
0x1800d6eb4  mov     rdx, r12
0x1800d6eb7  mov     rcx, rdi
0x1800d6eba  mov     rax, [rax+38h]
0x1800d6ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6ec3  jmp     loc_1800D6D74
0x1800d6ec8  mov     ebx, 4
0x1800d6ecd  mov     rax, [rdi]
0x1800d6ed0  mov     edx, 1
0x1800d6ed5  mov     rcx, rdi
0x1800d6ed8  mov     rax, [rax]
0x1800d6edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6ee0  test    r15, r15
0x1800d6ee3  jz      short loc_1800D6EF2
0x1800d6ee5  mov     edx, 10h
0x1800d6eea  mov     rcx, r15; Block
0x1800d6eed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d6ef2  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d6ef6  test    rcx, rcx
0x1800d6ef9  jz      short loc_1800D6F07
0x1800d6efb  call    cs:__imp_CloseHandle
0x1800d6f02  nop     dword ptr [rax+rax+00h]
0x1800d6f07  test    r14, r14
0x1800d6f0a  jz      short loc_1800D6F1B
0x1800d6f0c  mov     rcx, r14; pwk
0x1800d6f0f  call    cs:__imp_CloseThreadpoolWork
0x1800d6f16  nop     dword ptr [rax+rax+00h]
0x1800d6f1b  mov     eax, ebx
0x1800d6f1d  mov     rcx, [rbp+var_8]
0x1800d6f21  xor     rcx, rsp; StackCookie
0x1800d6f24  call    __security_check_cookie
0x1800d6f29  mov     rbx, [rsp+80h+arg_18]
0x1800d6f31  add     rsp, 80h
0x1800d6f38  pop     r15
0x1800d6f3a  pop     r14
0x1800d6f3c  pop     r13
0x1800d6f3e  pop     r12
0x1800d6f40  pop     rdi
0x1800d6f41  pop     rsi
0x1800d6f42  pop     rbp
0x1800d6f43  retn
```
