# CSpWmiMethod<_SPACES_PhysicalDisk_IsDeviceCacheEnabled>::RunMethod<CSpPhysicalDisk::IsDeviceCacheEnabled,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800f1a5c`
- end: `0x1800f1dd9`
- name: `??$RunMethod@VIsDeviceCacheEnabled@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_IsDeviceCacheEnabled@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800f1a5c`
- `0x1800f3bf8`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1c3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f1c0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f1c0f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f1c2a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f1c2a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f1bef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f1bef`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f1ce4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f1ce4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f1da3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f1da3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1d8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1d8f`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_IsDeviceCacheEnabled>::RunMethod<CSpPhysicalDisk::IsDeviceCacheEnabled,4>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 IsDeviceCacheEnabled; // rax
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
  CSpPhysicalDisk::IsDeviceCacheEnabled *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::IsDeviceCacheEnabled *)operator new(0x168u);
  IsDeviceCacheEnabled = CSpPhysicalDisk::IsDeviceCacheEnabled::IsDeviceCacheEnabled(v25);
  v8 = IsDeviceCacheEnabled;
  if ( IsDeviceCacheEnabled )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)IsDeviceCacheEnabled + 8LL))(IsDeviceCacheEnabled, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpPhysicalDisk::IsDeviceCacheEnabled *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_18033B69F,
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
0x1800f1a5c  mov     [rsp-38h+arg_18], rbx
0x1800f1a61  push    rbp
0x1800f1a62  push    rsi
0x1800f1a63  push    rdi
0x1800f1a64  push    r12
0x1800f1a66  push    r13
0x1800f1a68  push    r14
0x1800f1a6a  push    r15
0x1800f1a6c  mov     rbp, rsp
0x1800f1a6f  sub     rsp, 80h
0x1800f1a76  mov     rax, cs:__security_cookie
0x1800f1a7d  xor     rax, rsp
0x1800f1a80  mov     [rbp+var_8], rax
0x1800f1a84  xor     eax, eax
0x1800f1a86  mov     rsi, rcx
0x1800f1a89  xorps   xmm0, xmm0
0x1800f1a8c  mov     [rbp+var_10], eax
0x1800f1a8f  mov     ecx, 168h; Size
0x1800f1a94  mov     [rbp+var_40], eax
0x1800f1a97  movups  [rbp+var_20], xmm0
0x1800f1a9b  mov     [rbp+TokenHandle], rax
0x1800f1a9f  mov     r12, r8
0x1800f1aa2  mov     r13, rdx
0x1800f1aa5  xor     r14d, r14d
0x1800f1aa8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f1aad  mov     rcx, rax; this
0x1800f1ab0  mov     [rbp+var_28], rax
0x1800f1ab4  call    ??0IsDeviceCacheEnabled@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::IsDeviceCacheEnabled::IsDeviceCacheEnabled(void)
0x1800f1ab9  mov     rdi, rax
0x1800f1abc  test    rax, rax
0x1800f1abf  jnz     short loc_1800F1AC9
0x1800f1ac1  lea     ebx, [rax+1Bh]
0x1800f1ac4  jmp     loc_1800F1D86
0x1800f1ac9  mov     rax, [rax]
0x1800f1acc  mov     rdx, rsi
0x1800f1acf  mov     rcx, rdi
0x1800f1ad2  xor     r15d, r15d
0x1800f1ad5  mov     rax, [rax+8]
0x1800f1ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1ade  lea     rcx, [rbp+var_40]
0x1800f1ae2  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800f1ae7  mov     [rdi+1Ch], eax
0x1800f1aea  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800f1aee  mov     ecx, [rsi+14h]; unsigned int
0x1800f1af1  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800f1af6  mov     eax, cs:dword_18039EB68
0x1800f1afc  cmp     eax, 5
0x1800f1aff  jbe     short loc_1800F1B6F
0x1800f1b01  mov     rdx, 400000000000h
0x1800f1b0b  lea     rcx, dword_18039EB68
0x1800f1b12  call    _tlgKeywordOn
0x1800f1b17  test    al, al
0x1800f1b19  jz      short loc_1800F1B6F
0x1800f1b1b  mov     eax, [rbp+var_40]
0x1800f1b1e  lea     rdx, byte_18033B69F
0x1800f1b25  xor     ecx, ecx
0x1800f1b27  cmp     [rdi+1Ch], eax
0x1800f1b2a  movzx   eax, word ptr [rbp+var_10]
0x1800f1b2e  mov     word ptr [rbp+var_40], ax
0x1800f1b32  setnz   cl
0x1800f1b35  mov     eax, [rsi+14h]
0x1800f1b38  mov     [rbp+var_38], eax
0x1800f1b3b  lea     rax, [rbp+var_20]
0x1800f1b3f  mov     [rbp+var_28], rax
0x1800f1b43  lea     rax, [rbp+var_3C]
0x1800f1b47  mov     [rsp+80h+var_48], rax
0x1800f1b4c  lea     rax, [rbp+var_40]
0x1800f1b50  mov     [rsp+80h+var_50], rax
0x1800f1b55  lea     rax, [rbp+var_38]
0x1800f1b59  mov     [rsp+80h+var_58], rax
0x1800f1b5e  lea     rax, [rbp+var_28]
0x1800f1b62  mov     [rsp+80h+var_60], rax
0x1800f1b67  mov     [rbp+var_3C], ecx
0x1800f1b6a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800f1b6f  mov     rcx, [rsi]
0x1800f1b72  test    rcx, rcx
0x1800f1b75  jz      loc_1800F1D5C
0x1800f1b7b  mov     rax, [rcx]
0x1800f1b7e  test    rax, rax
0x1800f1b81  jz      loc_1800F1D5C
0x1800f1b87  mov     rax, [rax+18h]
0x1800f1b8b  lea     r8, [rdi+20h]
0x1800f1b8f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800f1b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1b9b  mov     ebx, eax
0x1800f1b9d  test    eax, eax
0x1800f1b9f  jnz     loc_1800F1D61
0x1800f1ba5  cmp     [rsi+10h], r14d
0x1800f1ba9  jz      loc_1800F1CF5
0x1800f1baf  lea     rbx, [rdi+148h]
0x1800f1bb6  mov     rcx, rbx
0x1800f1bb9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800f1bbe  mov     rcx, rbx; struct CSpJobMgr **
0x1800f1bc1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800f1bc6  test    eax, eax
0x1800f1bc8  jnz     short loc_1800F1BD2
0x1800f1bca  lea     ebx, [rax+1Ch]
0x1800f1bcd  jmp     loc_1800F1D61
0x1800f1bd2  mov     ecx, 10h; Size
0x1800f1bd7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f1bdc  xor     r8d, r8d; pcbe
0x1800f1bdf  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f1be6  mov     rdx, rax; pv
0x1800f1be9  mov     r15, rax
0x1800f1bec  mov     [rax], rdi
0x1800f1bef  call    cs:__imp_CreateThreadpoolWork
0x1800f1bf6  nop     dword ptr [rax+rax+00h]
0x1800f1bfb  mov     r14, rax
0x1800f1bfe  test    rax, rax
0x1800f1c01  jnz     short loc_1800F1C0F
0x1800f1c03  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800f1c08  mov     ebx, eax
0x1800f1c0a  jmp     loc_1800F1D61
0x1800f1c0f  call    cs:__imp_GetCurrentThread
0x1800f1c16  nop     dword ptr [rax+rax+00h]
0x1800f1c1b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f1c1f  xor     r8d, r8d; OpenAsSelf
0x1800f1c22  mov     rcx, rax; ThreadHandle
0x1800f1c25  mov     edx, 2000Ch; DesiredAccess
0x1800f1c2a  call    cs:__imp_OpenThreadToken
0x1800f1c31  nop     dword ptr [rax+rax+00h]
0x1800f1c36  test    eax, eax
0x1800f1c38  jnz     short loc_1800F1C4D
0x1800f1c3a  call    cs:__imp_GetLastError
0x1800f1c41  nop     dword ptr [rax+rax+00h]
0x1800f1c46  cmp     eax, 3F0h
0x1800f1c4b  jnz     short loc_1800F1C03
0x1800f1c4d  mov     rax, [rbp+TokenHandle]
0x1800f1c51  mov     r8, r13
0x1800f1c54  mov     [r15+8], rax
0x1800f1c58  mov     rcx, rdi
0x1800f1c5b  mov     rax, [rdi]
0x1800f1c5e  mov     rdx, [rsi+8]
0x1800f1c62  mov     rax, [rax+18h]
0x1800f1c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1c6b  mov     rax, [rdi]
0x1800f1c6e  mov     rdx, r12
0x1800f1c71  mov     rcx, rdi
0x1800f1c74  mov     rax, [rax+28h]
0x1800f1c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1c7d  mov     ebx, eax
0x1800f1c7f  test    eax, eax
0x1800f1c81  jz      short loc_1800F1C8C
0x1800f1c83  cmp     eax, 7
0x1800f1c86  jnz     loc_1800F1D61
0x1800f1c8c  mov     rax, [rdi]
0x1800f1c8f  mov     rdx, r12
0x1800f1c92  mov     rcx, rdi
0x1800f1c95  mov     rax, [rax+38h]
0x1800f1c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1c9e  mov     ebx, eax
0x1800f1ca0  test    eax, eax
0x1800f1ca2  jnz     loc_1800F1D61
0x1800f1ca8  mov     rax, [rdi+150h]
0x1800f1caf  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800f1cb6  jnz     short loc_1800F1CCC
0x1800f1cb8  mov     rax, [rdi+158h]
0x1800f1cbf  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800f1cc6  jz      loc_1800F1D61
0x1800f1ccc  mov     rdx, r12
0x1800f1ccf  mov     rcx, rdi
0x1800f1cd2  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800f1cd7  mov     ebx, eax
0x1800f1cd9  test    eax, eax
0x1800f1cdb  jnz     loc_1800F1D61
0x1800f1ce1  mov     rcx, r14; pwk
0x1800f1ce4  call    cs:__imp_SubmitThreadpoolWork
0x1800f1ceb  nop     dword ptr [rax+rax+00h]
0x1800f1cf0  jmp     loc_1800F1DAF
0x1800f1cf5  mov     rax, [rdi]
0x1800f1cf8  mov     r8, r13
0x1800f1cfb  mov     rdx, [rsi+8]
0x1800f1cff  mov     rcx, rdi
0x1800f1d02  mov     rax, [rax+10h]
0x1800f1d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1d0b  mov     rax, [rdi]
0x1800f1d0e  mov     rdx, r12
0x1800f1d11  mov     rcx, rdi
0x1800f1d14  mov     rax, [rax+30h]
0x1800f1d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1d1d  mov     ebx, eax
0x1800f1d1f  test    eax, eax
0x1800f1d21  jz      short loc_1800F1D28
0x1800f1d23  cmp     eax, 7
0x1800f1d26  jnz     short loc_1800F1D61
0x1800f1d28  mov     rax, [rdi]
0x1800f1d2b  mov     rdx, r12
0x1800f1d2e  mov     rcx, rdi
0x1800f1d31  mov     rax, [rax+28h]
0x1800f1d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1d3a  mov     ebx, eax
0x1800f1d3c  test    eax, eax
0x1800f1d3e  jz      short loc_1800F1D45
0x1800f1d40  cmp     eax, 7
0x1800f1d43  jnz     short loc_1800F1D61
0x1800f1d45  mov     rax, [rdi]
0x1800f1d48  mov     rdx, r12
0x1800f1d4b  mov     rcx, rdi
0x1800f1d4e  mov     rax, [rax+38h]
0x1800f1d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1d57  jmp     loc_1800F1C08
0x1800f1d5c  mov     ebx, 4
0x1800f1d61  mov     rax, [rdi]
0x1800f1d64  mov     edx, 1
0x1800f1d69  mov     rcx, rdi
0x1800f1d6c  mov     rax, [rax]
0x1800f1d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1d74  test    r15, r15
0x1800f1d77  jz      short loc_1800F1D86
0x1800f1d79  mov     edx, 10h
0x1800f1d7e  mov     rcx, r15; Block
0x1800f1d81  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f1d86  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f1d8a  test    rcx, rcx
0x1800f1d8d  jz      short loc_1800F1D9B
0x1800f1d8f  call    cs:__imp_CloseHandle
0x1800f1d96  nop     dword ptr [rax+rax+00h]
0x1800f1d9b  test    r14, r14
0x1800f1d9e  jz      short loc_1800F1DAF
0x1800f1da0  mov     rcx, r14; pwk
0x1800f1da3  call    cs:__imp_CloseThreadpoolWork
0x1800f1daa  nop     dword ptr [rax+rax+00h]
0x1800f1daf  mov     eax, ebx
0x1800f1db1  mov     rcx, [rbp+var_8]
0x1800f1db5  xor     rcx, rsp; StackCookie
0x1800f1db8  call    __security_check_cookie
0x1800f1dbd  mov     rbx, [rsp+80h+arg_18]
0x1800f1dc5  add     rsp, 80h
0x1800f1dcc  pop     r15
0x1800f1dce  pop     r14
0x1800f1dd0  pop     r13
0x1800f1dd2  pop     r12
0x1800f1dd4  pop     rdi
0x1800f1dd5  pop     rsi
0x1800f1dd6  pop     rbp
0x1800f1dd7  retn
```
