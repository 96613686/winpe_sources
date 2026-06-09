# CSpWmiMethod<_SPACES_StorageEnclosure_GetFirmwareInformation>::RunMethod<CSpStorageEnclosure::GetFirmwareInformation,8>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800d5cd4`
- end: `0x1800d6022`
- name: `??$RunMethod@VGetFirmwareInformation@CSpStorageEnclosure@@$07@?$CSpWmiMethod@U_SPACES_StorageEnclosure_GetFirmwareInformation@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800d5cd4`
- `0x1800d70cc`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5ea0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d5e81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d5e81`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d5e96`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d5e96`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d5e67`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d5e67`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d5f40`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d5f40`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d5ff3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d5ff3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d5fe5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d5fe5`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageEnclosure_GetFirmwareInformation>::RunMethod<CSpStorageEnclosure::GetFirmwareInformation,8>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 FirmwareInformation; // rax
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
  CSpStorageEnclosure::GetFirmwareInformation *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageEnclosure::GetFirmwareInformation *)operator new(0x168u);
  FirmwareInformation = CSpStorageEnclosure::GetFirmwareInformation::GetFirmwareInformation(v25);
  v8 = FirmwareInformation;
  if ( FirmwareInformation )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)FirmwareInformation + 8LL))(FirmwareInformation, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageEnclosure::GetFirmwareInformation *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18032E6B3,
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
0x1800d5cd4  mov     [rsp-38h+arg_18], rbx
0x1800d5cd9  push    rbp
0x1800d5cda  push    rsi
0x1800d5cdb  push    rdi
0x1800d5cdc  push    r12
0x1800d5cde  push    r13
0x1800d5ce0  push    r14
0x1800d5ce2  push    r15
0x1800d5ce4  mov     rbp, rsp
0x1800d5ce7  sub     rsp, 80h
0x1800d5cee  mov     rax, cs:__security_cookie
0x1800d5cf5  xor     rax, rsp
0x1800d5cf8  mov     [rbp+var_8], rax
0x1800d5cfc  xor     eax, eax
0x1800d5cfe  mov     rsi, rcx
0x1800d5d01  xorps   xmm0, xmm0
0x1800d5d04  mov     [rbp+var_10], eax
0x1800d5d07  mov     ecx, 168h; Size
0x1800d5d0c  mov     [rbp+var_40], eax
0x1800d5d0f  movups  [rbp+var_20], xmm0
0x1800d5d13  mov     [rbp+TokenHandle], rax
0x1800d5d17  mov     r12, r8
0x1800d5d1a  mov     r13, rdx
0x1800d5d1d  xor     r14d, r14d
0x1800d5d20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d5d25  mov     rcx, rax; this
0x1800d5d28  mov     [rbp+var_28], rax
0x1800d5d2c  call    ??0GetFirmwareInformation@CSpStorageEnclosure@@QEAA@XZ; CSpStorageEnclosure::GetFirmwareInformation::GetFirmwareInformation(void)
0x1800d5d31  mov     rdi, rax
0x1800d5d34  test    rax, rax
0x1800d5d37  jnz     short loc_1800D5D41
0x1800d5d39  lea     ebx, [rax+1Bh]
0x1800d5d3c  jmp     loc_1800D5FDC
0x1800d5d41  mov     rax, [rax]
0x1800d5d44  mov     rdx, rsi
0x1800d5d47  mov     rcx, rdi
0x1800d5d4a  xor     r15d, r15d
0x1800d5d4d  mov     rax, [rax+8]
0x1800d5d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5d56  lea     rcx, [rbp+var_40]
0x1800d5d5a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800d5d5f  mov     [rdi+1Ch], eax
0x1800d5d62  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800d5d66  mov     ecx, [rsi+14h]; unsigned int
0x1800d5d69  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800d5d6e  mov     eax, cs:dword_180397B68
0x1800d5d74  cmp     eax, 5
0x1800d5d77  jbe     short loc_1800D5DE7
0x1800d5d79  mov     rdx, 400000000000h
0x1800d5d83  lea     rcx, dword_180397B68
0x1800d5d8a  call    _tlgKeywordOn
0x1800d5d8f  test    al, al
0x1800d5d91  jz      short loc_1800D5DE7
0x1800d5d93  mov     eax, [rbp+var_40]
0x1800d5d96  lea     rdx, byte_18032E6B3
0x1800d5d9d  xor     ecx, ecx
0x1800d5d9f  cmp     [rdi+1Ch], eax
0x1800d5da2  movzx   eax, word ptr [rbp+var_10]
0x1800d5da6  mov     word ptr [rbp+var_40], ax
0x1800d5daa  setnz   cl
0x1800d5dad  mov     eax, [rsi+14h]
0x1800d5db0  mov     [rbp+var_38], eax
0x1800d5db3  lea     rax, [rbp+var_20]
0x1800d5db7  mov     [rbp+var_28], rax
0x1800d5dbb  lea     rax, [rbp+var_3C]
0x1800d5dbf  mov     [rsp+80h+var_48], rax
0x1800d5dc4  lea     rax, [rbp+var_40]
0x1800d5dc8  mov     [rsp+80h+var_50], rax
0x1800d5dcd  lea     rax, [rbp+var_38]
0x1800d5dd1  mov     [rsp+80h+var_58], rax
0x1800d5dd6  lea     rax, [rbp+var_28]
0x1800d5dda  mov     [rsp+80h+var_60], rax
0x1800d5ddf  mov     [rbp+var_3C], ecx
0x1800d5de2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800d5de7  mov     rcx, [rsi]
0x1800d5dea  test    rcx, rcx
0x1800d5ded  jz      loc_1800D5FB2
0x1800d5df3  mov     rax, [rcx]
0x1800d5df6  test    rax, rax
0x1800d5df9  jz      loc_1800D5FB2
0x1800d5dff  mov     rax, [rax+18h]
0x1800d5e03  lea     r8, [rdi+20h]
0x1800d5e07  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800d5e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5e13  mov     ebx, eax
0x1800d5e15  test    eax, eax
0x1800d5e17  jnz     loc_1800D5FB7
0x1800d5e1d  cmp     [rsi+10h], r14d
0x1800d5e21  jz      loc_1800D5F4B
0x1800d5e27  lea     rbx, [rdi+148h]
0x1800d5e2e  mov     rcx, rbx
0x1800d5e31  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800d5e36  mov     rcx, rbx; struct CSpJobMgr **
0x1800d5e39  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800d5e3e  test    eax, eax
0x1800d5e40  jnz     short loc_1800D5E4A
0x1800d5e42  lea     ebx, [rax+1Ch]
0x1800d5e45  jmp     loc_1800D5FB7
0x1800d5e4a  mov     ecx, 10h; Size
0x1800d5e4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d5e54  xor     r8d, r8d; pcbe
0x1800d5e57  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800d5e5e  mov     rdx, rax; pv
0x1800d5e61  mov     r15, rax
0x1800d5e64  mov     [rax], rdi
0x1800d5e67  call    cs:__imp_CreateThreadpoolWork
0x1800d5e6d  mov     r14, rax
0x1800d5e70  test    rax, rax
0x1800d5e73  jnz     short loc_1800D5E81
0x1800d5e75  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800d5e7a  mov     ebx, eax
0x1800d5e7c  jmp     loc_1800D5FB7
0x1800d5e81  call    cs:__imp_GetCurrentThread
0x1800d5e87  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d5e8b  xor     r8d, r8d; OpenAsSelf
0x1800d5e8e  mov     rcx, rax; ThreadHandle
0x1800d5e91  mov     edx, 2000Ch; DesiredAccess
0x1800d5e96  call    cs:__imp_OpenThreadToken
0x1800d5e9c  test    eax, eax
0x1800d5e9e  jnz     short loc_1800D5EAD
0x1800d5ea0  call    cs:__imp_GetLastError
0x1800d5ea6  cmp     eax, 3F0h
0x1800d5eab  jnz     short loc_1800D5E75
0x1800d5ead  mov     rax, [rbp+TokenHandle]
0x1800d5eb1  mov     r8, r13
0x1800d5eb4  mov     [r15+8], rax
0x1800d5eb8  mov     rcx, rdi
0x1800d5ebb  mov     rax, [rdi]
0x1800d5ebe  mov     rdx, [rsi+8]
0x1800d5ec2  mov     rax, [rax+18h]
0x1800d5ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5ecb  mov     rax, [rdi]
0x1800d5ece  mov     rdx, r12
0x1800d5ed1  mov     rcx, rdi
0x1800d5ed4  mov     rax, [rax+28h]
0x1800d5ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5edd  mov     ebx, eax
0x1800d5edf  test    eax, eax
0x1800d5ee1  jz      short loc_1800D5EEC
0x1800d5ee3  cmp     eax, 7
0x1800d5ee6  jnz     loc_1800D5FB7
0x1800d5eec  mov     rax, [rdi]
0x1800d5eef  mov     rdx, r12
0x1800d5ef2  mov     rcx, rdi
0x1800d5ef5  mov     rax, [rax+38h]
0x1800d5ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5efe  mov     ebx, eax
0x1800d5f00  test    eax, eax
0x1800d5f02  jnz     loc_1800D5FB7
0x1800d5f08  mov     rax, [rdi+150h]
0x1800d5f0f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800d5f16  jnz     short loc_1800D5F2C
0x1800d5f18  mov     rax, [rdi+158h]
0x1800d5f1f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800d5f26  jz      loc_1800D5FB7
0x1800d5f2c  mov     rdx, r12
0x1800d5f2f  mov     rcx, rdi
0x1800d5f32  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800d5f37  mov     ebx, eax
0x1800d5f39  test    eax, eax
0x1800d5f3b  jnz     short loc_1800D5FB7
0x1800d5f3d  mov     rcx, r14; pwk
0x1800d5f40  call    cs:__imp_SubmitThreadpoolWork
0x1800d5f46  jmp     loc_1800D5FF9
0x1800d5f4b  mov     rax, [rdi]
0x1800d5f4e  mov     r8, r13
0x1800d5f51  mov     rdx, [rsi+8]
0x1800d5f55  mov     rcx, rdi
0x1800d5f58  mov     rax, [rax+10h]
0x1800d5f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5f61  mov     rax, [rdi]
0x1800d5f64  mov     rdx, r12
0x1800d5f67  mov     rcx, rdi
0x1800d5f6a  mov     rax, [rax+30h]
0x1800d5f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5f73  mov     ebx, eax
0x1800d5f75  test    eax, eax
0x1800d5f77  jz      short loc_1800D5F7E
0x1800d5f79  cmp     eax, 7
0x1800d5f7c  jnz     short loc_1800D5FB7
0x1800d5f7e  mov     rax, [rdi]
0x1800d5f81  mov     rdx, r12
0x1800d5f84  mov     rcx, rdi
0x1800d5f87  mov     rax, [rax+28h]
0x1800d5f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5f90  mov     ebx, eax
0x1800d5f92  test    eax, eax
0x1800d5f94  jz      short loc_1800D5F9B
0x1800d5f96  cmp     eax, 7
0x1800d5f99  jnz     short loc_1800D5FB7
0x1800d5f9b  mov     rax, [rdi]
0x1800d5f9e  mov     rdx, r12
0x1800d5fa1  mov     rcx, rdi
0x1800d5fa4  mov     rax, [rax+38h]
0x1800d5fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5fad  jmp     loc_1800D5E7A
0x1800d5fb2  mov     ebx, 4
0x1800d5fb7  mov     rax, [rdi]
0x1800d5fba  mov     edx, 1
0x1800d5fbf  mov     rcx, rdi
0x1800d5fc2  mov     rax, [rax]
0x1800d5fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5fca  test    r15, r15
0x1800d5fcd  jz      short loc_1800D5FDC
0x1800d5fcf  mov     edx, 10h
0x1800d5fd4  mov     rcx, r15; Block
0x1800d5fd7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d5fdc  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d5fe0  test    rcx, rcx
0x1800d5fe3  jz      short loc_1800D5FEB
0x1800d5fe5  call    cs:__imp_CloseHandle
0x1800d5feb  test    r14, r14
0x1800d5fee  jz      short loc_1800D5FF9
0x1800d5ff0  mov     rcx, r14; pwk
0x1800d5ff3  call    cs:__imp_CloseThreadpoolWork
0x1800d5ff9  mov     eax, ebx
0x1800d5ffb  mov     rcx, [rbp+var_8]
0x1800d5fff  xor     rcx, rsp; StackCookie
0x1800d6002  call    __security_check_cookie
0x1800d6007  mov     rbx, [rsp+80h+arg_18]
0x1800d600f  add     rsp, 80h
0x1800d6016  pop     r15
0x1800d6018  pop     r14
0x1800d601a  pop     r13
0x1800d601c  pop     r12
0x1800d601e  pop     rdi
0x1800d601f  pop     rsi
0x1800d6020  pop     rbp
0x1800d6021  retn
```
