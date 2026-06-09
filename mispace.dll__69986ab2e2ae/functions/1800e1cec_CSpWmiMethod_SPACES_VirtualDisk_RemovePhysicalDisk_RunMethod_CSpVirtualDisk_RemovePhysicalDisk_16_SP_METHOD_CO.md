# CSpWmiMethod<_SPACES_VirtualDisk_RemovePhysicalDisk>::RunMethod<CSpVirtualDisk::RemovePhysicalDisk,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e1cec`
- end: `0x1800e2069`
- name: `??$RunMethod@VRemovePhysicalDisk@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_RemovePhysicalDisk@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800e1cec`
- `0x1800e3fc4`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1eca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e1e9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e1e9f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e1eba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e1eba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e1e7f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e1e7f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e1f74`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e1f74`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e2033`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e2033`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e201f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e201f`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_RemovePhysicalDisk>::RunMethod<CSpVirtualDisk::RemovePhysicalDisk,16>(
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
  CSpVirtualDisk::RemovePhysicalDisk *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::RemovePhysicalDisk *)operator new(0x160u);
  v7 = CSpVirtualDisk::RemovePhysicalDisk::RemovePhysicalDisk(v25);
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
      v25 = (CSpVirtualDisk::RemovePhysicalDisk *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_18033AC4C,
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
0x1800e1cec  mov     [rsp-38h+arg_18], rbx
0x1800e1cf1  push    rbp
0x1800e1cf2  push    rsi
0x1800e1cf3  push    rdi
0x1800e1cf4  push    r12
0x1800e1cf6  push    r13
0x1800e1cf8  push    r14
0x1800e1cfa  push    r15
0x1800e1cfc  mov     rbp, rsp
0x1800e1cff  sub     rsp, 80h
0x1800e1d06  mov     rax, cs:__security_cookie
0x1800e1d0d  xor     rax, rsp
0x1800e1d10  mov     [rbp+var_8], rax
0x1800e1d14  xor     eax, eax
0x1800e1d16  mov     rsi, rcx
0x1800e1d19  xorps   xmm0, xmm0
0x1800e1d1c  mov     [rbp+var_10], eax
0x1800e1d1f  mov     ecx, 160h; Size
0x1800e1d24  mov     [rbp+var_40], eax
0x1800e1d27  movups  [rbp+var_20], xmm0
0x1800e1d2b  mov     [rbp+TokenHandle], rax
0x1800e1d2f  mov     r12, r8
0x1800e1d32  mov     r13, rdx
0x1800e1d35  xor     r14d, r14d
0x1800e1d38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e1d3d  mov     rcx, rax; this
0x1800e1d40  mov     [rbp+var_28], rax
0x1800e1d44  call    ??0RemovePhysicalDisk@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::RemovePhysicalDisk::RemovePhysicalDisk(void)
0x1800e1d49  mov     rdi, rax
0x1800e1d4c  test    rax, rax
0x1800e1d4f  jnz     short loc_1800E1D59
0x1800e1d51  lea     ebx, [rax+1Bh]
0x1800e1d54  jmp     loc_1800E2016
0x1800e1d59  mov     rax, [rax]
0x1800e1d5c  mov     rdx, rsi
0x1800e1d5f  mov     rcx, rdi
0x1800e1d62  xor     r15d, r15d
0x1800e1d65  mov     rax, [rax+8]
0x1800e1d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1d6e  lea     rcx, [rbp+var_40]
0x1800e1d72  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e1d77  mov     [rdi+1Ch], eax
0x1800e1d7a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e1d7e  mov     ecx, [rsi+14h]; unsigned int
0x1800e1d81  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e1d86  mov     eax, cs:dword_18039EB68
0x1800e1d8c  cmp     eax, 5
0x1800e1d8f  jbe     short loc_1800E1DFF
0x1800e1d91  mov     rdx, 400000000000h
0x1800e1d9b  lea     rcx, dword_18039EB68
0x1800e1da2  call    _tlgKeywordOn
0x1800e1da7  test    al, al
0x1800e1da9  jz      short loc_1800E1DFF
0x1800e1dab  mov     eax, [rbp+var_40]
0x1800e1dae  lea     rdx, dword_18033AC4C
0x1800e1db5  xor     ecx, ecx
0x1800e1db7  cmp     [rdi+1Ch], eax
0x1800e1dba  movzx   eax, word ptr [rbp+var_10]
0x1800e1dbe  mov     word ptr [rbp+var_40], ax
0x1800e1dc2  setnz   cl
0x1800e1dc5  mov     eax, [rsi+14h]
0x1800e1dc8  mov     [rbp+var_38], eax
0x1800e1dcb  lea     rax, [rbp+var_20]
0x1800e1dcf  mov     [rbp+var_28], rax
0x1800e1dd3  lea     rax, [rbp+var_3C]
0x1800e1dd7  mov     [rsp+80h+var_48], rax
0x1800e1ddc  lea     rax, [rbp+var_40]
0x1800e1de0  mov     [rsp+80h+var_50], rax
0x1800e1de5  lea     rax, [rbp+var_38]
0x1800e1de9  mov     [rsp+80h+var_58], rax
0x1800e1dee  lea     rax, [rbp+var_28]
0x1800e1df2  mov     [rsp+80h+var_60], rax
0x1800e1df7  mov     [rbp+var_3C], ecx
0x1800e1dfa  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e1dff  mov     rcx, [rsi]
0x1800e1e02  test    rcx, rcx
0x1800e1e05  jz      loc_1800E1FEC
0x1800e1e0b  mov     rax, [rcx]
0x1800e1e0e  test    rax, rax
0x1800e1e11  jz      loc_1800E1FEC
0x1800e1e17  mov     rax, [rax+18h]
0x1800e1e1b  lea     r8, [rdi+20h]
0x1800e1e1f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e1e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1e2b  mov     ebx, eax
0x1800e1e2d  test    eax, eax
0x1800e1e2f  jnz     loc_1800E1FF1
0x1800e1e35  cmp     [rsi+10h], r14d
0x1800e1e39  jz      loc_1800E1F85
0x1800e1e3f  lea     rbx, [rdi+148h]
0x1800e1e46  mov     rcx, rbx
0x1800e1e49  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e1e4e  mov     rcx, rbx; struct CSpJobMgr **
0x1800e1e51  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e1e56  test    eax, eax
0x1800e1e58  jnz     short loc_1800E1E62
0x1800e1e5a  lea     ebx, [rax+1Ch]
0x1800e1e5d  jmp     loc_1800E1FF1
0x1800e1e62  mov     ecx, 10h; Size
0x1800e1e67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e1e6c  xor     r8d, r8d; pcbe
0x1800e1e6f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e1e76  mov     rdx, rax; pv
0x1800e1e79  mov     r15, rax
0x1800e1e7c  mov     [rax], rdi
0x1800e1e7f  call    cs:__imp_CreateThreadpoolWork
0x1800e1e86  nop     dword ptr [rax+rax+00h]
0x1800e1e8b  mov     r14, rax
0x1800e1e8e  test    rax, rax
0x1800e1e91  jnz     short loc_1800E1E9F
0x1800e1e93  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e1e98  mov     ebx, eax
0x1800e1e9a  jmp     loc_1800E1FF1
0x1800e1e9f  call    cs:__imp_GetCurrentThread
0x1800e1ea6  nop     dword ptr [rax+rax+00h]
0x1800e1eab  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e1eaf  xor     r8d, r8d; OpenAsSelf
0x1800e1eb2  mov     rcx, rax; ThreadHandle
0x1800e1eb5  mov     edx, 2000Ch; DesiredAccess
0x1800e1eba  call    cs:__imp_OpenThreadToken
0x1800e1ec1  nop     dword ptr [rax+rax+00h]
0x1800e1ec6  test    eax, eax
0x1800e1ec8  jnz     short loc_1800E1EDD
0x1800e1eca  call    cs:__imp_GetLastError
0x1800e1ed1  nop     dword ptr [rax+rax+00h]
0x1800e1ed6  cmp     eax, 3F0h
0x1800e1edb  jnz     short loc_1800E1E93
0x1800e1edd  mov     rax, [rbp+TokenHandle]
0x1800e1ee1  mov     r8, r13
0x1800e1ee4  mov     [r15+8], rax
0x1800e1ee8  mov     rcx, rdi
0x1800e1eeb  mov     rax, [rdi]
0x1800e1eee  mov     rdx, [rsi+8]
0x1800e1ef2  mov     rax, [rax+18h]
0x1800e1ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1efb  mov     rax, [rdi]
0x1800e1efe  mov     rdx, r12
0x1800e1f01  mov     rcx, rdi
0x1800e1f04  mov     rax, [rax+28h]
0x1800e1f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1f0d  mov     ebx, eax
0x1800e1f0f  test    eax, eax
0x1800e1f11  jz      short loc_1800E1F1C
0x1800e1f13  cmp     eax, 7
0x1800e1f16  jnz     loc_1800E1FF1
0x1800e1f1c  mov     rax, [rdi]
0x1800e1f1f  mov     rdx, r12
0x1800e1f22  mov     rcx, rdi
0x1800e1f25  mov     rax, [rax+38h]
0x1800e1f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1f2e  mov     ebx, eax
0x1800e1f30  test    eax, eax
0x1800e1f32  jnz     loc_1800E1FF1
0x1800e1f38  mov     rax, [rdi+150h]
0x1800e1f3f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e1f46  jnz     short loc_1800E1F5C
0x1800e1f48  mov     rax, [rdi+158h]
0x1800e1f4f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e1f56  jz      loc_1800E1FF1
0x1800e1f5c  mov     rdx, r12
0x1800e1f5f  mov     rcx, rdi
0x1800e1f62  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e1f67  mov     ebx, eax
0x1800e1f69  test    eax, eax
0x1800e1f6b  jnz     loc_1800E1FF1
0x1800e1f71  mov     rcx, r14; pwk
0x1800e1f74  call    cs:__imp_SubmitThreadpoolWork
0x1800e1f7b  nop     dword ptr [rax+rax+00h]
0x1800e1f80  jmp     loc_1800E203F
0x1800e1f85  mov     rax, [rdi]
0x1800e1f88  mov     r8, r13
0x1800e1f8b  mov     rdx, [rsi+8]
0x1800e1f8f  mov     rcx, rdi
0x1800e1f92  mov     rax, [rax+10h]
0x1800e1f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1f9b  mov     rax, [rdi]
0x1800e1f9e  mov     rdx, r12
0x1800e1fa1  mov     rcx, rdi
0x1800e1fa4  mov     rax, [rax+30h]
0x1800e1fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1fad  mov     ebx, eax
0x1800e1faf  test    eax, eax
0x1800e1fb1  jz      short loc_1800E1FB8
0x1800e1fb3  cmp     eax, 7
0x1800e1fb6  jnz     short loc_1800E1FF1
0x1800e1fb8  mov     rax, [rdi]
0x1800e1fbb  mov     rdx, r12
0x1800e1fbe  mov     rcx, rdi
0x1800e1fc1  mov     rax, [rax+28h]
0x1800e1fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1fca  mov     ebx, eax
0x1800e1fcc  test    eax, eax
0x1800e1fce  jz      short loc_1800E1FD5
0x1800e1fd0  cmp     eax, 7
0x1800e1fd3  jnz     short loc_1800E1FF1
0x1800e1fd5  mov     rax, [rdi]
0x1800e1fd8  mov     rdx, r12
0x1800e1fdb  mov     rcx, rdi
0x1800e1fde  mov     rax, [rax+38h]
0x1800e1fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1fe7  jmp     loc_1800E1E98
0x1800e1fec  mov     ebx, 4
0x1800e1ff1  mov     rax, [rdi]
0x1800e1ff4  mov     edx, 1
0x1800e1ff9  mov     rcx, rdi
0x1800e1ffc  mov     rax, [rax]
0x1800e1fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2004  test    r15, r15
0x1800e2007  jz      short loc_1800E2016
0x1800e2009  mov     edx, 10h
0x1800e200e  mov     rcx, r15; Block
0x1800e2011  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e2016  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e201a  test    rcx, rcx
0x1800e201d  jz      short loc_1800E202B
0x1800e201f  call    cs:__imp_CloseHandle
0x1800e2026  nop     dword ptr [rax+rax+00h]
0x1800e202b  test    r14, r14
0x1800e202e  jz      short loc_1800E203F
0x1800e2030  mov     rcx, r14; pwk
0x1800e2033  call    cs:__imp_CloseThreadpoolWork
0x1800e203a  nop     dword ptr [rax+rax+00h]
0x1800e203f  mov     eax, ebx
0x1800e2041  mov     rcx, [rbp+var_8]
0x1800e2045  xor     rcx, rsp; StackCookie
0x1800e2048  call    __security_check_cookie
0x1800e204d  mov     rbx, [rsp+80h+arg_18]
0x1800e2055  add     rsp, 80h
0x1800e205c  pop     r15
0x1800e205e  pop     r14
0x1800e2060  pop     r13
0x1800e2062  pop     r12
0x1800e2064  pop     rdi
0x1800e2065  pop     rsi
0x1800e2066  pop     rbp
0x1800e2067  retn
```
