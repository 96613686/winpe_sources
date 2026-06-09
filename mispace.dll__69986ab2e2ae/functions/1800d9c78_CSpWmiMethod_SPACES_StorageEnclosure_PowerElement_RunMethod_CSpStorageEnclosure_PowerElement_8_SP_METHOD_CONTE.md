# CSpWmiMethod<_SPACES_StorageEnclosure_PowerElement>::RunMethod<CSpStorageEnclosure::PowerElement,8>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800d9c78`
- end: `0x1800d9ff5`
- name: `??$RunMethod@VPowerElement@CSpStorageEnclosure@@$07@?$CSpWmiMethod@U_SPACES_StorageEnclosure_PowerElement@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800dc240`

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
- `0x1800d9c78`
- `0x1800da550`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9e56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9e56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d9e2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d9e2b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d9e46`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d9e46`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d9e0b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d9e0b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d9f00`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d9f00`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d9fbf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d9fbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d9fab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d9fab`

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
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageEnclosure::PowerElement *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_1803369A8,
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
0x1800d9c78  mov     [rsp-38h+arg_18], rbx
0x1800d9c7d  push    rbp
0x1800d9c7e  push    rsi
0x1800d9c7f  push    rdi
0x1800d9c80  push    r12
0x1800d9c82  push    r13
0x1800d9c84  push    r14
0x1800d9c86  push    r15
0x1800d9c88  mov     rbp, rsp
0x1800d9c8b  sub     rsp, 80h
0x1800d9c92  mov     rax, cs:__security_cookie
0x1800d9c99  xor     rax, rsp
0x1800d9c9c  mov     [rbp+var_8], rax
0x1800d9ca0  xor     eax, eax
0x1800d9ca2  mov     rsi, rcx
0x1800d9ca5  xorps   xmm0, xmm0
0x1800d9ca8  mov     [rbp+var_10], eax
0x1800d9cab  mov     ecx, 160h; Size
0x1800d9cb0  mov     [rbp+var_40], eax
0x1800d9cb3  movups  [rbp+var_20], xmm0
0x1800d9cb7  mov     [rbp+TokenHandle], rax
0x1800d9cbb  mov     r12, r8
0x1800d9cbe  mov     r13, rdx
0x1800d9cc1  xor     r14d, r14d
0x1800d9cc4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d9cc9  mov     rcx, rax; this
0x1800d9ccc  mov     [rbp+var_28], rax
0x1800d9cd0  call    ??0PowerElement@CSpStorageEnclosure@@QEAA@XZ; CSpStorageEnclosure::PowerElement::PowerElement(void)
0x1800d9cd5  mov     rdi, rax
0x1800d9cd8  test    rax, rax
0x1800d9cdb  jnz     short loc_1800D9CE5
0x1800d9cdd  lea     ebx, [rax+1Bh]
0x1800d9ce0  jmp     loc_1800D9FA2
0x1800d9ce5  mov     rax, [rax]
0x1800d9ce8  mov     rdx, rsi
0x1800d9ceb  mov     rcx, rdi
0x1800d9cee  xor     r15d, r15d
0x1800d9cf1  mov     rax, [rax+8]
0x1800d9cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9cfa  lea     rcx, [rbp+var_40]
0x1800d9cfe  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800d9d03  mov     [rdi+1Ch], eax
0x1800d9d06  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800d9d0a  mov     ecx, [rsi+14h]; unsigned int
0x1800d9d0d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800d9d12  mov     eax, cs:dword_18039EB68
0x1800d9d18  cmp     eax, 5
0x1800d9d1b  jbe     short loc_1800D9D8B
0x1800d9d1d  mov     rdx, 400000000000h
0x1800d9d27  lea     rcx, dword_18039EB68
0x1800d9d2e  call    _tlgKeywordOn
0x1800d9d33  test    al, al
0x1800d9d35  jz      short loc_1800D9D8B
0x1800d9d37  mov     eax, [rbp+var_40]
0x1800d9d3a  lea     rdx, unk_1803369A8
0x1800d9d41  xor     ecx, ecx
0x1800d9d43  cmp     [rdi+1Ch], eax
0x1800d9d46  movzx   eax, word ptr [rbp+var_10]
0x1800d9d4a  mov     word ptr [rbp+var_40], ax
0x1800d9d4e  setnz   cl
0x1800d9d51  mov     eax, [rsi+14h]
0x1800d9d54  mov     [rbp+var_38], eax
0x1800d9d57  lea     rax, [rbp+var_20]
0x1800d9d5b  mov     [rbp+var_28], rax
0x1800d9d5f  lea     rax, [rbp+var_3C]
0x1800d9d63  mov     [rsp+80h+var_48], rax
0x1800d9d68  lea     rax, [rbp+var_40]
0x1800d9d6c  mov     [rsp+80h+var_50], rax
0x1800d9d71  lea     rax, [rbp+var_38]
0x1800d9d75  mov     [rsp+80h+var_58], rax
0x1800d9d7a  lea     rax, [rbp+var_28]
0x1800d9d7e  mov     [rsp+80h+var_60], rax
0x1800d9d83  mov     [rbp+var_3C], ecx
0x1800d9d86  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800d9d8b  mov     rcx, [rsi]
0x1800d9d8e  test    rcx, rcx
0x1800d9d91  jz      loc_1800D9F78
0x1800d9d97  mov     rax, [rcx]
0x1800d9d9a  test    rax, rax
0x1800d9d9d  jz      loc_1800D9F78
0x1800d9da3  mov     rax, [rax+18h]
0x1800d9da7  lea     r8, [rdi+20h]
0x1800d9dab  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800d9db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9db7  mov     ebx, eax
0x1800d9db9  test    eax, eax
0x1800d9dbb  jnz     loc_1800D9F7D
0x1800d9dc1  cmp     [rsi+10h], r14d
0x1800d9dc5  jz      loc_1800D9F11
0x1800d9dcb  lea     rbx, [rdi+148h]
0x1800d9dd2  mov     rcx, rbx
0x1800d9dd5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800d9dda  mov     rcx, rbx; struct CSpJobMgr **
0x1800d9ddd  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800d9de2  test    eax, eax
0x1800d9de4  jnz     short loc_1800D9DEE
0x1800d9de6  lea     ebx, [rax+1Ch]
0x1800d9de9  jmp     loc_1800D9F7D
0x1800d9dee  mov     ecx, 10h; Size
0x1800d9df3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d9df8  xor     r8d, r8d; pcbe
0x1800d9dfb  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800d9e02  mov     rdx, rax; pv
0x1800d9e05  mov     r15, rax
0x1800d9e08  mov     [rax], rdi
0x1800d9e0b  call    cs:__imp_CreateThreadpoolWork
0x1800d9e12  nop     dword ptr [rax+rax+00h]
0x1800d9e17  mov     r14, rax
0x1800d9e1a  test    rax, rax
0x1800d9e1d  jnz     short loc_1800D9E2B
0x1800d9e1f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800d9e24  mov     ebx, eax
0x1800d9e26  jmp     loc_1800D9F7D
0x1800d9e2b  call    cs:__imp_GetCurrentThread
0x1800d9e32  nop     dword ptr [rax+rax+00h]
0x1800d9e37  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d9e3b  xor     r8d, r8d; OpenAsSelf
0x1800d9e3e  mov     rcx, rax; ThreadHandle
0x1800d9e41  mov     edx, 2000Ch; DesiredAccess
0x1800d9e46  call    cs:__imp_OpenThreadToken
0x1800d9e4d  nop     dword ptr [rax+rax+00h]
0x1800d9e52  test    eax, eax
0x1800d9e54  jnz     short loc_1800D9E69
0x1800d9e56  call    cs:__imp_GetLastError
0x1800d9e5d  nop     dword ptr [rax+rax+00h]
0x1800d9e62  cmp     eax, 3F0h
0x1800d9e67  jnz     short loc_1800D9E1F
0x1800d9e69  mov     rax, [rbp+TokenHandle]
0x1800d9e6d  mov     r8, r13
0x1800d9e70  mov     [r15+8], rax
0x1800d9e74  mov     rcx, rdi
0x1800d9e77  mov     rax, [rdi]
0x1800d9e7a  mov     rdx, [rsi+8]
0x1800d9e7e  mov     rax, [rax+18h]
0x1800d9e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9e87  mov     rax, [rdi]
0x1800d9e8a  mov     rdx, r12
0x1800d9e8d  mov     rcx, rdi
0x1800d9e90  mov     rax, [rax+28h]
0x1800d9e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9e99  mov     ebx, eax
0x1800d9e9b  test    eax, eax
0x1800d9e9d  jz      short loc_1800D9EA8
0x1800d9e9f  cmp     eax, 7
0x1800d9ea2  jnz     loc_1800D9F7D
0x1800d9ea8  mov     rax, [rdi]
0x1800d9eab  mov     rdx, r12
0x1800d9eae  mov     rcx, rdi
0x1800d9eb1  mov     rax, [rax+38h]
0x1800d9eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9eba  mov     ebx, eax
0x1800d9ebc  test    eax, eax
0x1800d9ebe  jnz     loc_1800D9F7D
0x1800d9ec4  mov     rax, [rdi+150h]
0x1800d9ecb  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800d9ed2  jnz     short loc_1800D9EE8
0x1800d9ed4  mov     rax, [rdi+158h]
0x1800d9edb  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800d9ee2  jz      loc_1800D9F7D
0x1800d9ee8  mov     rdx, r12
0x1800d9eeb  mov     rcx, rdi
0x1800d9eee  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800d9ef3  mov     ebx, eax
0x1800d9ef5  test    eax, eax
0x1800d9ef7  jnz     loc_1800D9F7D
0x1800d9efd  mov     rcx, r14; pwk
0x1800d9f00  call    cs:__imp_SubmitThreadpoolWork
0x1800d9f07  nop     dword ptr [rax+rax+00h]
0x1800d9f0c  jmp     loc_1800D9FCB
0x1800d9f11  mov     rax, [rdi]
0x1800d9f14  mov     r8, r13
0x1800d9f17  mov     rdx, [rsi+8]
0x1800d9f1b  mov     rcx, rdi
0x1800d9f1e  mov     rax, [rax+10h]
0x1800d9f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f27  mov     rax, [rdi]
0x1800d9f2a  mov     rdx, r12
0x1800d9f2d  mov     rcx, rdi
0x1800d9f30  mov     rax, [rax+30h]
0x1800d9f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f39  mov     ebx, eax
0x1800d9f3b  test    eax, eax
0x1800d9f3d  jz      short loc_1800D9F44
0x1800d9f3f  cmp     eax, 7
0x1800d9f42  jnz     short loc_1800D9F7D
0x1800d9f44  mov     rax, [rdi]
0x1800d9f47  mov     rdx, r12
0x1800d9f4a  mov     rcx, rdi
0x1800d9f4d  mov     rax, [rax+28h]
0x1800d9f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f56  mov     ebx, eax
0x1800d9f58  test    eax, eax
0x1800d9f5a  jz      short loc_1800D9F61
0x1800d9f5c  cmp     eax, 7
0x1800d9f5f  jnz     short loc_1800D9F7D
0x1800d9f61  mov     rax, [rdi]
0x1800d9f64  mov     rdx, r12
0x1800d9f67  mov     rcx, rdi
0x1800d9f6a  mov     rax, [rax+38h]
0x1800d9f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f73  jmp     loc_1800D9E24
0x1800d9f78  mov     ebx, 4
0x1800d9f7d  mov     rax, [rdi]
0x1800d9f80  mov     edx, 1
0x1800d9f85  mov     rcx, rdi
0x1800d9f88  mov     rax, [rax]
0x1800d9f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9f90  test    r15, r15
0x1800d9f93  jz      short loc_1800D9FA2
0x1800d9f95  mov     edx, 10h
0x1800d9f9a  mov     rcx, r15; Block
0x1800d9f9d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d9fa2  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d9fa6  test    rcx, rcx
0x1800d9fa9  jz      short loc_1800D9FB7
0x1800d9fab  call    cs:__imp_CloseHandle
0x1800d9fb2  nop     dword ptr [rax+rax+00h]
0x1800d9fb7  test    r14, r14
0x1800d9fba  jz      short loc_1800D9FCB
0x1800d9fbc  mov     rcx, r14; pwk
0x1800d9fbf  call    cs:__imp_CloseThreadpoolWork
0x1800d9fc6  nop     dword ptr [rax+rax+00h]
0x1800d9fcb  mov     eax, ebx
0x1800d9fcd  mov     rcx, [rbp+var_8]
0x1800d9fd1  xor     rcx, rsp; StackCookie
0x1800d9fd4  call    __security_check_cookie
0x1800d9fd9  mov     rbx, [rsp+80h+arg_18]
0x1800d9fe1  add     rsp, 80h
0x1800d9fe8  pop     r15
0x1800d9fea  pop     r14
0x1800d9fec  pop     r13
0x1800d9fee  pop     r12
0x1800d9ff0  pop     rdi
0x1800d9ff1  pop     rsi
0x1800d9ff2  pop     rbp
0x1800d9ff3  retn
```
