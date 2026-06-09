# CSpWmiMethod<_SPACES_StorageScaleUnit_Maintenance>::RunMethod<CSpStorageScaleUnit::Maintenance,39>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800d3a94`
- end: `0x1800d3de2`
- name: `??$RunMethod@VMaintenance@CSpStorageScaleUnit@@$0CH@@?$CSpWmiMethod@U_SPACES_StorageScaleUnit_Maintenance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800d4630`

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
- `0x18005d58c`
- `0x1800d3a94`
- `0x1800d3ea4`
- `0x1800d4ad8`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3c60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3c60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d3c41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d3c41`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d3c56`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d3c56`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d3c27`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d3c27`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d3d00`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d3d00`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d3db3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d3db3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d3da5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d3da5`

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
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageScaleUnit::Maintenance *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_18032DFC7,
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
0x1800d3a94  mov     [rsp-38h+arg_18], rbx
0x1800d3a99  push    rbp
0x1800d3a9a  push    rsi
0x1800d3a9b  push    rdi
0x1800d3a9c  push    r12
0x1800d3a9e  push    r13
0x1800d3aa0  push    r14
0x1800d3aa2  push    r15
0x1800d3aa4  mov     rbp, rsp
0x1800d3aa7  sub     rsp, 80h
0x1800d3aae  mov     rax, cs:__security_cookie
0x1800d3ab5  xor     rax, rsp
0x1800d3ab8  mov     [rbp+var_8], rax
0x1800d3abc  xor     eax, eax
0x1800d3abe  mov     rsi, rcx
0x1800d3ac1  xorps   xmm0, xmm0
0x1800d3ac4  mov     [rbp+var_10], eax
0x1800d3ac7  mov     ecx, 180h; Size
0x1800d3acc  mov     [rbp+var_40], eax
0x1800d3acf  movups  [rbp+var_20], xmm0
0x1800d3ad3  mov     [rbp+TokenHandle], rax
0x1800d3ad7  mov     r12, r8
0x1800d3ada  mov     r13, rdx
0x1800d3add  xor     r14d, r14d
0x1800d3ae0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d3ae5  mov     rcx, rax; this
0x1800d3ae8  mov     [rbp+var_28], rax
0x1800d3aec  call    ??0Maintenance@CSpStorageScaleUnit@@QEAA@XZ; CSpStorageScaleUnit::Maintenance::Maintenance(void)
0x1800d3af1  mov     rdi, rax
0x1800d3af4  test    rax, rax
0x1800d3af7  jnz     short loc_1800D3B01
0x1800d3af9  lea     ebx, [rax+1Bh]
0x1800d3afc  jmp     loc_1800D3D9C
0x1800d3b01  mov     rax, [rax]
0x1800d3b04  mov     rdx, rsi
0x1800d3b07  mov     rcx, rdi
0x1800d3b0a  xor     r15d, r15d
0x1800d3b0d  mov     rax, [rax+8]
0x1800d3b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3b16  lea     rcx, [rbp+var_40]
0x1800d3b1a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800d3b1f  mov     [rdi+1Ch], eax
0x1800d3b22  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800d3b26  mov     ecx, [rsi+14h]; unsigned int
0x1800d3b29  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800d3b2e  mov     eax, cs:dword_180397B68
0x1800d3b34  cmp     eax, 5
0x1800d3b37  jbe     short loc_1800D3BA7
0x1800d3b39  mov     rdx, 400000000000h
0x1800d3b43  lea     rcx, dword_180397B68
0x1800d3b4a  call    _tlgKeywordOn
0x1800d3b4f  test    al, al
0x1800d3b51  jz      short loc_1800D3BA7
0x1800d3b53  mov     eax, [rbp+var_40]
0x1800d3b56  lea     rdx, byte_18032DFC7
0x1800d3b5d  xor     ecx, ecx
0x1800d3b5f  cmp     [rdi+1Ch], eax
0x1800d3b62  movzx   eax, word ptr [rbp+var_10]
0x1800d3b66  mov     word ptr [rbp+var_40], ax
0x1800d3b6a  setnz   cl
0x1800d3b6d  mov     eax, [rsi+14h]
0x1800d3b70  mov     [rbp+var_38], eax
0x1800d3b73  lea     rax, [rbp+var_20]
0x1800d3b77  mov     [rbp+var_28], rax
0x1800d3b7b  lea     rax, [rbp+var_3C]
0x1800d3b7f  mov     [rsp+80h+var_48], rax
0x1800d3b84  lea     rax, [rbp+var_40]
0x1800d3b88  mov     [rsp+80h+var_50], rax
0x1800d3b8d  lea     rax, [rbp+var_38]
0x1800d3b91  mov     [rsp+80h+var_58], rax
0x1800d3b96  lea     rax, [rbp+var_28]
0x1800d3b9a  mov     [rsp+80h+var_60], rax
0x1800d3b9f  mov     [rbp+var_3C], ecx
0x1800d3ba2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800d3ba7  mov     rcx, [rsi]
0x1800d3baa  test    rcx, rcx
0x1800d3bad  jz      loc_1800D3D72
0x1800d3bb3  mov     rax, [rcx]
0x1800d3bb6  test    rax, rax
0x1800d3bb9  jz      loc_1800D3D72
0x1800d3bbf  mov     rax, [rax+18h]
0x1800d3bc3  lea     r8, [rdi+20h]
0x1800d3bc7  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800d3bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3bd3  mov     ebx, eax
0x1800d3bd5  test    eax, eax
0x1800d3bd7  jnz     loc_1800D3D77
0x1800d3bdd  cmp     [rsi+10h], r14d
0x1800d3be1  jz      loc_1800D3D0B
0x1800d3be7  lea     rbx, [rdi+148h]
0x1800d3bee  mov     rcx, rbx
0x1800d3bf1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800d3bf6  mov     rcx, rbx; struct CSpJobMgr **
0x1800d3bf9  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800d3bfe  test    eax, eax
0x1800d3c00  jnz     short loc_1800D3C0A
0x1800d3c02  lea     ebx, [rax+1Ch]
0x1800d3c05  jmp     loc_1800D3D77
0x1800d3c0a  mov     ecx, 10h; Size
0x1800d3c0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d3c14  xor     r8d, r8d; pcbe
0x1800d3c17  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800d3c1e  mov     rdx, rax; pv
0x1800d3c21  mov     r15, rax
0x1800d3c24  mov     [rax], rdi
0x1800d3c27  call    cs:__imp_CreateThreadpoolWork
0x1800d3c2d  mov     r14, rax
0x1800d3c30  test    rax, rax
0x1800d3c33  jnz     short loc_1800D3C41
0x1800d3c35  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800d3c3a  mov     ebx, eax
0x1800d3c3c  jmp     loc_1800D3D77
0x1800d3c41  call    cs:__imp_GetCurrentThread
0x1800d3c47  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d3c4b  xor     r8d, r8d; OpenAsSelf
0x1800d3c4e  mov     rcx, rax; ThreadHandle
0x1800d3c51  mov     edx, 2000Ch; DesiredAccess
0x1800d3c56  call    cs:__imp_OpenThreadToken
0x1800d3c5c  test    eax, eax
0x1800d3c5e  jnz     short loc_1800D3C6D
0x1800d3c60  call    cs:__imp_GetLastError
0x1800d3c66  cmp     eax, 3F0h
0x1800d3c6b  jnz     short loc_1800D3C35
0x1800d3c6d  mov     rax, [rbp+TokenHandle]
0x1800d3c71  mov     r8, r13
0x1800d3c74  mov     [r15+8], rax
0x1800d3c78  mov     rcx, rdi
0x1800d3c7b  mov     rax, [rdi]
0x1800d3c7e  mov     rdx, [rsi+8]
0x1800d3c82  mov     rax, [rax+18h]
0x1800d3c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3c8b  mov     rax, [rdi]
0x1800d3c8e  mov     rdx, r12
0x1800d3c91  mov     rcx, rdi
0x1800d3c94  mov     rax, [rax+28h]
0x1800d3c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3c9d  mov     ebx, eax
0x1800d3c9f  test    eax, eax
0x1800d3ca1  jz      short loc_1800D3CAC
0x1800d3ca3  cmp     eax, 7
0x1800d3ca6  jnz     loc_1800D3D77
0x1800d3cac  mov     rax, [rdi]
0x1800d3caf  mov     rdx, r12
0x1800d3cb2  mov     rcx, rdi
0x1800d3cb5  mov     rax, [rax+38h]
0x1800d3cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3cbe  mov     ebx, eax
0x1800d3cc0  test    eax, eax
0x1800d3cc2  jnz     loc_1800D3D77
0x1800d3cc8  mov     rax, [rdi+150h]
0x1800d3ccf  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800d3cd6  jnz     short loc_1800D3CEC
0x1800d3cd8  mov     rax, [rdi+158h]
0x1800d3cdf  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800d3ce6  jz      loc_1800D3D77
0x1800d3cec  mov     rdx, r12
0x1800d3cef  mov     rcx, rdi
0x1800d3cf2  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StorageReliabilityCounter_Reset@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StorageReliabilityCounter_Reset@@@Z; CSpWmiMethod<_SPACES_StorageReliabilityCounter_Reset>::SetCreatedJob(_SPACES_StorageReliabilityCounter_Reset *)
0x1800d3cf7  mov     ebx, eax
0x1800d3cf9  test    eax, eax
0x1800d3cfb  jnz     short loc_1800D3D77
0x1800d3cfd  mov     rcx, r14; pwk
0x1800d3d00  call    cs:__imp_SubmitThreadpoolWork
0x1800d3d06  jmp     loc_1800D3DB9
0x1800d3d0b  mov     rax, [rdi]
0x1800d3d0e  mov     r8, r13
0x1800d3d11  mov     rdx, [rsi+8]
0x1800d3d15  mov     rcx, rdi
0x1800d3d18  mov     rax, [rax+10h]
0x1800d3d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3d21  mov     rax, [rdi]
0x1800d3d24  mov     rdx, r12
0x1800d3d27  mov     rcx, rdi
0x1800d3d2a  mov     rax, [rax+30h]
0x1800d3d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3d33  mov     ebx, eax
0x1800d3d35  test    eax, eax
0x1800d3d37  jz      short loc_1800D3D3E
0x1800d3d39  cmp     eax, 7
0x1800d3d3c  jnz     short loc_1800D3D77
0x1800d3d3e  mov     rax, [rdi]
0x1800d3d41  mov     rdx, r12
0x1800d3d44  mov     rcx, rdi
0x1800d3d47  mov     rax, [rax+28h]
0x1800d3d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3d50  mov     ebx, eax
0x1800d3d52  test    eax, eax
0x1800d3d54  jz      short loc_1800D3D5B
0x1800d3d56  cmp     eax, 7
0x1800d3d59  jnz     short loc_1800D3D77
0x1800d3d5b  mov     rax, [rdi]
0x1800d3d5e  mov     rdx, r12
0x1800d3d61  mov     rcx, rdi
0x1800d3d64  mov     rax, [rax+38h]
0x1800d3d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3d6d  jmp     loc_1800D3C3A
0x1800d3d72  mov     ebx, 4
0x1800d3d77  mov     rax, [rdi]
0x1800d3d7a  mov     edx, 1
0x1800d3d7f  mov     rcx, rdi
0x1800d3d82  mov     rax, [rax]
0x1800d3d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3d8a  test    r15, r15
0x1800d3d8d  jz      short loc_1800D3D9C
0x1800d3d8f  mov     edx, 10h
0x1800d3d94  mov     rcx, r15; Block
0x1800d3d97  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d3d9c  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d3da0  test    rcx, rcx
0x1800d3da3  jz      short loc_1800D3DAB
0x1800d3da5  call    cs:__imp_CloseHandle
0x1800d3dab  test    r14, r14
0x1800d3dae  jz      short loc_1800D3DB9
0x1800d3db0  mov     rcx, r14; pwk
0x1800d3db3  call    cs:__imp_CloseThreadpoolWork
0x1800d3db9  mov     eax, ebx
0x1800d3dbb  mov     rcx, [rbp+var_8]
0x1800d3dbf  xor     rcx, rsp; StackCookie
0x1800d3dc2  call    __security_check_cookie
0x1800d3dc7  mov     rbx, [rsp+80h+arg_18]
0x1800d3dcf  add     rsp, 80h
0x1800d3dd6  pop     r15
0x1800d3dd8  pop     r14
0x1800d3dda  pop     r13
0x1800d3ddc  pop     r12
0x1800d3dde  pop     rdi
0x1800d3ddf  pop     rsi
0x1800d3de0  pop     rbp
0x1800d3de1  retn
```
