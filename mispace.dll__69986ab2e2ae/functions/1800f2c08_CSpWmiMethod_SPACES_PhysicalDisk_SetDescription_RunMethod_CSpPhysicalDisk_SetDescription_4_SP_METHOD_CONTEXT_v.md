# CSpWmiMethod<_SPACES_PhysicalDisk_SetDescription>::RunMethod<CSpPhysicalDisk::SetDescription,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800f2c08`
- end: `0x1800f2f85`
- name: `??$RunMethod@VSetDescription@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_SetDescription@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800f2c08`
- `0x1800f3d68`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2de6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f2dbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f2dbb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f2dd6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f2dd6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f2d9b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f2d9b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f2e90`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f2e90`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f2f4f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f2f4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f2f3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f2f3b`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_SetDescription>::RunMethod<CSpPhysicalDisk::SetDescription,4>(
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
  CSpPhysicalDisk::SetDescription *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::SetDescription *)operator new(0x160u);
  v7 = CSpPhysicalDisk::SetDescription::SetDescription(v25);
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
      v25 = (CSpPhysicalDisk::SetDescription *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_18033DD3F,
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
0x1800f2c08  mov     [rsp-38h+arg_18], rbx
0x1800f2c0d  push    rbp
0x1800f2c0e  push    rsi
0x1800f2c0f  push    rdi
0x1800f2c10  push    r12
0x1800f2c12  push    r13
0x1800f2c14  push    r14
0x1800f2c16  push    r15
0x1800f2c18  mov     rbp, rsp
0x1800f2c1b  sub     rsp, 80h
0x1800f2c22  mov     rax, cs:__security_cookie
0x1800f2c29  xor     rax, rsp
0x1800f2c2c  mov     [rbp+var_8], rax
0x1800f2c30  xor     eax, eax
0x1800f2c32  mov     rsi, rcx
0x1800f2c35  xorps   xmm0, xmm0
0x1800f2c38  mov     [rbp+var_10], eax
0x1800f2c3b  mov     ecx, 160h; Size
0x1800f2c40  mov     [rbp+var_40], eax
0x1800f2c43  movups  [rbp+var_20], xmm0
0x1800f2c47  mov     [rbp+TokenHandle], rax
0x1800f2c4b  mov     r12, r8
0x1800f2c4e  mov     r13, rdx
0x1800f2c51  xor     r14d, r14d
0x1800f2c54  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f2c59  mov     rcx, rax; this
0x1800f2c5c  mov     [rbp+var_28], rax
0x1800f2c60  call    ??0SetDescription@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::SetDescription::SetDescription(void)
0x1800f2c65  mov     rdi, rax
0x1800f2c68  test    rax, rax
0x1800f2c6b  jnz     short loc_1800F2C75
0x1800f2c6d  lea     ebx, [rax+1Bh]
0x1800f2c70  jmp     loc_1800F2F32
0x1800f2c75  mov     rax, [rax]
0x1800f2c78  mov     rdx, rsi
0x1800f2c7b  mov     rcx, rdi
0x1800f2c7e  xor     r15d, r15d
0x1800f2c81  mov     rax, [rax+8]
0x1800f2c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2c8a  lea     rcx, [rbp+var_40]
0x1800f2c8e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800f2c93  mov     [rdi+1Ch], eax
0x1800f2c96  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800f2c9a  mov     ecx, [rsi+14h]; unsigned int
0x1800f2c9d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800f2ca2  mov     eax, cs:dword_18039EB68
0x1800f2ca8  cmp     eax, 5
0x1800f2cab  jbe     short loc_1800F2D1B
0x1800f2cad  mov     rdx, 400000000000h
0x1800f2cb7  lea     rcx, dword_18039EB68
0x1800f2cbe  call    _tlgKeywordOn
0x1800f2cc3  test    al, al
0x1800f2cc5  jz      short loc_1800F2D1B
0x1800f2cc7  mov     eax, [rbp+var_40]
0x1800f2cca  lea     rdx, byte_18033DD3F
0x1800f2cd1  xor     ecx, ecx
0x1800f2cd3  cmp     [rdi+1Ch], eax
0x1800f2cd6  movzx   eax, word ptr [rbp+var_10]
0x1800f2cda  mov     word ptr [rbp+var_40], ax
0x1800f2cde  setnz   cl
0x1800f2ce1  mov     eax, [rsi+14h]
0x1800f2ce4  mov     [rbp+var_38], eax
0x1800f2ce7  lea     rax, [rbp+var_20]
0x1800f2ceb  mov     [rbp+var_28], rax
0x1800f2cef  lea     rax, [rbp+var_3C]
0x1800f2cf3  mov     [rsp+80h+var_48], rax
0x1800f2cf8  lea     rax, [rbp+var_40]
0x1800f2cfc  mov     [rsp+80h+var_50], rax
0x1800f2d01  lea     rax, [rbp+var_38]
0x1800f2d05  mov     [rsp+80h+var_58], rax
0x1800f2d0a  lea     rax, [rbp+var_28]
0x1800f2d0e  mov     [rsp+80h+var_60], rax
0x1800f2d13  mov     [rbp+var_3C], ecx
0x1800f2d16  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800f2d1b  mov     rcx, [rsi]
0x1800f2d1e  test    rcx, rcx
0x1800f2d21  jz      loc_1800F2F08
0x1800f2d27  mov     rax, [rcx]
0x1800f2d2a  test    rax, rax
0x1800f2d2d  jz      loc_1800F2F08
0x1800f2d33  mov     rax, [rax+18h]
0x1800f2d37  lea     r8, [rdi+20h]
0x1800f2d3b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800f2d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2d47  mov     ebx, eax
0x1800f2d49  test    eax, eax
0x1800f2d4b  jnz     loc_1800F2F0D
0x1800f2d51  cmp     [rsi+10h], r14d
0x1800f2d55  jz      loc_1800F2EA1
0x1800f2d5b  lea     rbx, [rdi+148h]
0x1800f2d62  mov     rcx, rbx
0x1800f2d65  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800f2d6a  mov     rcx, rbx; struct CSpJobMgr **
0x1800f2d6d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800f2d72  test    eax, eax
0x1800f2d74  jnz     short loc_1800F2D7E
0x1800f2d76  lea     ebx, [rax+1Ch]
0x1800f2d79  jmp     loc_1800F2F0D
0x1800f2d7e  mov     ecx, 10h; Size
0x1800f2d83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f2d88  xor     r8d, r8d; pcbe
0x1800f2d8b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f2d92  mov     rdx, rax; pv
0x1800f2d95  mov     r15, rax
0x1800f2d98  mov     [rax], rdi
0x1800f2d9b  call    cs:__imp_CreateThreadpoolWork
0x1800f2da2  nop     dword ptr [rax+rax+00h]
0x1800f2da7  mov     r14, rax
0x1800f2daa  test    rax, rax
0x1800f2dad  jnz     short loc_1800F2DBB
0x1800f2daf  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800f2db4  mov     ebx, eax
0x1800f2db6  jmp     loc_1800F2F0D
0x1800f2dbb  call    cs:__imp_GetCurrentThread
0x1800f2dc2  nop     dword ptr [rax+rax+00h]
0x1800f2dc7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f2dcb  xor     r8d, r8d; OpenAsSelf
0x1800f2dce  mov     rcx, rax; ThreadHandle
0x1800f2dd1  mov     edx, 2000Ch; DesiredAccess
0x1800f2dd6  call    cs:__imp_OpenThreadToken
0x1800f2ddd  nop     dword ptr [rax+rax+00h]
0x1800f2de2  test    eax, eax
0x1800f2de4  jnz     short loc_1800F2DF9
0x1800f2de6  call    cs:__imp_GetLastError
0x1800f2ded  nop     dword ptr [rax+rax+00h]
0x1800f2df2  cmp     eax, 3F0h
0x1800f2df7  jnz     short loc_1800F2DAF
0x1800f2df9  mov     rax, [rbp+TokenHandle]
0x1800f2dfd  mov     r8, r13
0x1800f2e00  mov     [r15+8], rax
0x1800f2e04  mov     rcx, rdi
0x1800f2e07  mov     rax, [rdi]
0x1800f2e0a  mov     rdx, [rsi+8]
0x1800f2e0e  mov     rax, [rax+18h]
0x1800f2e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2e17  mov     rax, [rdi]
0x1800f2e1a  mov     rdx, r12
0x1800f2e1d  mov     rcx, rdi
0x1800f2e20  mov     rax, [rax+28h]
0x1800f2e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2e29  mov     ebx, eax
0x1800f2e2b  test    eax, eax
0x1800f2e2d  jz      short loc_1800F2E38
0x1800f2e2f  cmp     eax, 7
0x1800f2e32  jnz     loc_1800F2F0D
0x1800f2e38  mov     rax, [rdi]
0x1800f2e3b  mov     rdx, r12
0x1800f2e3e  mov     rcx, rdi
0x1800f2e41  mov     rax, [rax+38h]
0x1800f2e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2e4a  mov     ebx, eax
0x1800f2e4c  test    eax, eax
0x1800f2e4e  jnz     loc_1800F2F0D
0x1800f2e54  mov     rax, [rdi+150h]
0x1800f2e5b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800f2e62  jnz     short loc_1800F2E78
0x1800f2e64  mov     rax, [rdi+158h]
0x1800f2e6b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800f2e72  jz      loc_1800F2F0D
0x1800f2e78  mov     rdx, r12
0x1800f2e7b  mov     rcx, rdi
0x1800f2e7e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800f2e83  mov     ebx, eax
0x1800f2e85  test    eax, eax
0x1800f2e87  jnz     loc_1800F2F0D
0x1800f2e8d  mov     rcx, r14; pwk
0x1800f2e90  call    cs:__imp_SubmitThreadpoolWork
0x1800f2e97  nop     dword ptr [rax+rax+00h]
0x1800f2e9c  jmp     loc_1800F2F5B
0x1800f2ea1  mov     rax, [rdi]
0x1800f2ea4  mov     r8, r13
0x1800f2ea7  mov     rdx, [rsi+8]
0x1800f2eab  mov     rcx, rdi
0x1800f2eae  mov     rax, [rax+10h]
0x1800f2eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2eb7  mov     rax, [rdi]
0x1800f2eba  mov     rdx, r12
0x1800f2ebd  mov     rcx, rdi
0x1800f2ec0  mov     rax, [rax+30h]
0x1800f2ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2ec9  mov     ebx, eax
0x1800f2ecb  test    eax, eax
0x1800f2ecd  jz      short loc_1800F2ED4
0x1800f2ecf  cmp     eax, 7
0x1800f2ed2  jnz     short loc_1800F2F0D
0x1800f2ed4  mov     rax, [rdi]
0x1800f2ed7  mov     rdx, r12
0x1800f2eda  mov     rcx, rdi
0x1800f2edd  mov     rax, [rax+28h]
0x1800f2ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2ee6  mov     ebx, eax
0x1800f2ee8  test    eax, eax
0x1800f2eea  jz      short loc_1800F2EF1
0x1800f2eec  cmp     eax, 7
0x1800f2eef  jnz     short loc_1800F2F0D
0x1800f2ef1  mov     rax, [rdi]
0x1800f2ef4  mov     rdx, r12
0x1800f2ef7  mov     rcx, rdi
0x1800f2efa  mov     rax, [rax+38h]
0x1800f2efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2f03  jmp     loc_1800F2DB4
0x1800f2f08  mov     ebx, 4
0x1800f2f0d  mov     rax, [rdi]
0x1800f2f10  mov     edx, 1
0x1800f2f15  mov     rcx, rdi
0x1800f2f18  mov     rax, [rax]
0x1800f2f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2f20  test    r15, r15
0x1800f2f23  jz      short loc_1800F2F32
0x1800f2f25  mov     edx, 10h
0x1800f2f2a  mov     rcx, r15; Block
0x1800f2f2d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f2f32  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f2f36  test    rcx, rcx
0x1800f2f39  jz      short loc_1800F2F47
0x1800f2f3b  call    cs:__imp_CloseHandle
0x1800f2f42  nop     dword ptr [rax+rax+00h]
0x1800f2f47  test    r14, r14
0x1800f2f4a  jz      short loc_1800F2F5B
0x1800f2f4c  mov     rcx, r14; pwk
0x1800f2f4f  call    cs:__imp_CloseThreadpoolWork
0x1800f2f56  nop     dword ptr [rax+rax+00h]
0x1800f2f5b  mov     eax, ebx
0x1800f2f5d  mov     rcx, [rbp+var_8]
0x1800f2f61  xor     rcx, rsp; StackCookie
0x1800f2f64  call    __security_check_cookie
0x1800f2f69  mov     rbx, [rsp+80h+arg_18]
0x1800f2f71  add     rsp, 80h
0x1800f2f78  pop     r15
0x1800f2f7a  pop     r14
0x1800f2f7c  pop     r13
0x1800f2f7e  pop     r12
0x1800f2f80  pop     rdi
0x1800f2f81  pop     rsi
0x1800f2f82  pop     rbp
0x1800f2f83  retn
```
