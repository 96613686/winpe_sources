# CSpWmiMethod<_SPACES_PhysicalDisk_IsPowerProtected>::RunMethod<CSpPhysicalDisk::IsPowerProtected,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800f1de0`
- end: `0x1800f215d`
- name: `??$RunMethod@VIsPowerProtected@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_IsPowerProtected@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800f1de0`
- `0x1800f3c78`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1fbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1fbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f1f93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f1f93`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f1fae`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f1fae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f1f73`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f1f73`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f2068`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f2068`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f2127`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f2127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f2113`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f2113`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_IsPowerProtected>::RunMethod<CSpPhysicalDisk::IsPowerProtected,4>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 IsPowerProtected; // rax
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
  CSpPhysicalDisk::IsPowerProtected *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::IsPowerProtected *)operator new(0x168u);
  IsPowerProtected = CSpPhysicalDisk::IsPowerProtected::IsPowerProtected(v25);
  v8 = IsPowerProtected;
  if ( IsPowerProtected )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)IsPowerProtected + 8LL))(IsPowerProtected, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpPhysicalDisk::IsPowerProtected *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_18033C2B4,
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
0x1800f1de0  mov     [rsp-38h+arg_18], rbx
0x1800f1de5  push    rbp
0x1800f1de6  push    rsi
0x1800f1de7  push    rdi
0x1800f1de8  push    r12
0x1800f1dea  push    r13
0x1800f1dec  push    r14
0x1800f1dee  push    r15
0x1800f1df0  mov     rbp, rsp
0x1800f1df3  sub     rsp, 80h
0x1800f1dfa  mov     rax, cs:__security_cookie
0x1800f1e01  xor     rax, rsp
0x1800f1e04  mov     [rbp+var_8], rax
0x1800f1e08  xor     eax, eax
0x1800f1e0a  mov     rsi, rcx
0x1800f1e0d  xorps   xmm0, xmm0
0x1800f1e10  mov     [rbp+var_10], eax
0x1800f1e13  mov     ecx, 168h; Size
0x1800f1e18  mov     [rbp+var_40], eax
0x1800f1e1b  movups  [rbp+var_20], xmm0
0x1800f1e1f  mov     [rbp+TokenHandle], rax
0x1800f1e23  mov     r12, r8
0x1800f1e26  mov     r13, rdx
0x1800f1e29  xor     r14d, r14d
0x1800f1e2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f1e31  mov     rcx, rax; this
0x1800f1e34  mov     [rbp+var_28], rax
0x1800f1e38  call    ??0IsPowerProtected@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::IsPowerProtected::IsPowerProtected(void)
0x1800f1e3d  mov     rdi, rax
0x1800f1e40  test    rax, rax
0x1800f1e43  jnz     short loc_1800F1E4D
0x1800f1e45  lea     ebx, [rax+1Bh]
0x1800f1e48  jmp     loc_1800F210A
0x1800f1e4d  mov     rax, [rax]
0x1800f1e50  mov     rdx, rsi
0x1800f1e53  mov     rcx, rdi
0x1800f1e56  xor     r15d, r15d
0x1800f1e59  mov     rax, [rax+8]
0x1800f1e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1e62  lea     rcx, [rbp+var_40]
0x1800f1e66  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800f1e6b  mov     [rdi+1Ch], eax
0x1800f1e6e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800f1e72  mov     ecx, [rsi+14h]; unsigned int
0x1800f1e75  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800f1e7a  mov     eax, cs:dword_18039EB68
0x1800f1e80  cmp     eax, 5
0x1800f1e83  jbe     short loc_1800F1EF3
0x1800f1e85  mov     rdx, 400000000000h
0x1800f1e8f  lea     rcx, dword_18039EB68
0x1800f1e96  call    _tlgKeywordOn
0x1800f1e9b  test    al, al
0x1800f1e9d  jz      short loc_1800F1EF3
0x1800f1e9f  mov     eax, [rbp+var_40]
0x1800f1ea2  lea     rdx, dword_18033C2B4
0x1800f1ea9  xor     ecx, ecx
0x1800f1eab  cmp     [rdi+1Ch], eax
0x1800f1eae  movzx   eax, word ptr [rbp+var_10]
0x1800f1eb2  mov     word ptr [rbp+var_40], ax
0x1800f1eb6  setnz   cl
0x1800f1eb9  mov     eax, [rsi+14h]
0x1800f1ebc  mov     [rbp+var_38], eax
0x1800f1ebf  lea     rax, [rbp+var_20]
0x1800f1ec3  mov     [rbp+var_28], rax
0x1800f1ec7  lea     rax, [rbp+var_3C]
0x1800f1ecb  mov     [rsp+80h+var_48], rax
0x1800f1ed0  lea     rax, [rbp+var_40]
0x1800f1ed4  mov     [rsp+80h+var_50], rax
0x1800f1ed9  lea     rax, [rbp+var_38]
0x1800f1edd  mov     [rsp+80h+var_58], rax
0x1800f1ee2  lea     rax, [rbp+var_28]
0x1800f1ee6  mov     [rsp+80h+var_60], rax
0x1800f1eeb  mov     [rbp+var_3C], ecx
0x1800f1eee  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800f1ef3  mov     rcx, [rsi]
0x1800f1ef6  test    rcx, rcx
0x1800f1ef9  jz      loc_1800F20E0
0x1800f1eff  mov     rax, [rcx]
0x1800f1f02  test    rax, rax
0x1800f1f05  jz      loc_1800F20E0
0x1800f1f0b  mov     rax, [rax+18h]
0x1800f1f0f  lea     r8, [rdi+20h]
0x1800f1f13  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800f1f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1f1f  mov     ebx, eax
0x1800f1f21  test    eax, eax
0x1800f1f23  jnz     loc_1800F20E5
0x1800f1f29  cmp     [rsi+10h], r14d
0x1800f1f2d  jz      loc_1800F2079
0x1800f1f33  lea     rbx, [rdi+148h]
0x1800f1f3a  mov     rcx, rbx
0x1800f1f3d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800f1f42  mov     rcx, rbx; struct CSpJobMgr **
0x1800f1f45  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800f1f4a  test    eax, eax
0x1800f1f4c  jnz     short loc_1800F1F56
0x1800f1f4e  lea     ebx, [rax+1Ch]
0x1800f1f51  jmp     loc_1800F20E5
0x1800f1f56  mov     ecx, 10h; Size
0x1800f1f5b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f1f60  xor     r8d, r8d; pcbe
0x1800f1f63  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f1f6a  mov     rdx, rax; pv
0x1800f1f6d  mov     r15, rax
0x1800f1f70  mov     [rax], rdi
0x1800f1f73  call    cs:__imp_CreateThreadpoolWork
0x1800f1f7a  nop     dword ptr [rax+rax+00h]
0x1800f1f7f  mov     r14, rax
0x1800f1f82  test    rax, rax
0x1800f1f85  jnz     short loc_1800F1F93
0x1800f1f87  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800f1f8c  mov     ebx, eax
0x1800f1f8e  jmp     loc_1800F20E5
0x1800f1f93  call    cs:__imp_GetCurrentThread
0x1800f1f9a  nop     dword ptr [rax+rax+00h]
0x1800f1f9f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f1fa3  xor     r8d, r8d; OpenAsSelf
0x1800f1fa6  mov     rcx, rax; ThreadHandle
0x1800f1fa9  mov     edx, 2000Ch; DesiredAccess
0x1800f1fae  call    cs:__imp_OpenThreadToken
0x1800f1fb5  nop     dword ptr [rax+rax+00h]
0x1800f1fba  test    eax, eax
0x1800f1fbc  jnz     short loc_1800F1FD1
0x1800f1fbe  call    cs:__imp_GetLastError
0x1800f1fc5  nop     dword ptr [rax+rax+00h]
0x1800f1fca  cmp     eax, 3F0h
0x1800f1fcf  jnz     short loc_1800F1F87
0x1800f1fd1  mov     rax, [rbp+TokenHandle]
0x1800f1fd5  mov     r8, r13
0x1800f1fd8  mov     [r15+8], rax
0x1800f1fdc  mov     rcx, rdi
0x1800f1fdf  mov     rax, [rdi]
0x1800f1fe2  mov     rdx, [rsi+8]
0x1800f1fe6  mov     rax, [rax+18h]
0x1800f1fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1fef  mov     rax, [rdi]
0x1800f1ff2  mov     rdx, r12
0x1800f1ff5  mov     rcx, rdi
0x1800f1ff8  mov     rax, [rax+28h]
0x1800f1ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2001  mov     ebx, eax
0x1800f2003  test    eax, eax
0x1800f2005  jz      short loc_1800F2010
0x1800f2007  cmp     eax, 7
0x1800f200a  jnz     loc_1800F20E5
0x1800f2010  mov     rax, [rdi]
0x1800f2013  mov     rdx, r12
0x1800f2016  mov     rcx, rdi
0x1800f2019  mov     rax, [rax+38h]
0x1800f201d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2022  mov     ebx, eax
0x1800f2024  test    eax, eax
0x1800f2026  jnz     loc_1800F20E5
0x1800f202c  mov     rax, [rdi+150h]
0x1800f2033  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800f203a  jnz     short loc_1800F2050
0x1800f203c  mov     rax, [rdi+158h]
0x1800f2043  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800f204a  jz      loc_1800F20E5
0x1800f2050  mov     rdx, r12
0x1800f2053  mov     rcx, rdi
0x1800f2056  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800f205b  mov     ebx, eax
0x1800f205d  test    eax, eax
0x1800f205f  jnz     loc_1800F20E5
0x1800f2065  mov     rcx, r14; pwk
0x1800f2068  call    cs:__imp_SubmitThreadpoolWork
0x1800f206f  nop     dword ptr [rax+rax+00h]
0x1800f2074  jmp     loc_1800F2133
0x1800f2079  mov     rax, [rdi]
0x1800f207c  mov     r8, r13
0x1800f207f  mov     rdx, [rsi+8]
0x1800f2083  mov     rcx, rdi
0x1800f2086  mov     rax, [rax+10h]
0x1800f208a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f208f  mov     rax, [rdi]
0x1800f2092  mov     rdx, r12
0x1800f2095  mov     rcx, rdi
0x1800f2098  mov     rax, [rax+30h]
0x1800f209c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f20a1  mov     ebx, eax
0x1800f20a3  test    eax, eax
0x1800f20a5  jz      short loc_1800F20AC
0x1800f20a7  cmp     eax, 7
0x1800f20aa  jnz     short loc_1800F20E5
0x1800f20ac  mov     rax, [rdi]
0x1800f20af  mov     rdx, r12
0x1800f20b2  mov     rcx, rdi
0x1800f20b5  mov     rax, [rax+28h]
0x1800f20b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f20be  mov     ebx, eax
0x1800f20c0  test    eax, eax
0x1800f20c2  jz      short loc_1800F20C9
0x1800f20c4  cmp     eax, 7
0x1800f20c7  jnz     short loc_1800F20E5
0x1800f20c9  mov     rax, [rdi]
0x1800f20cc  mov     rdx, r12
0x1800f20cf  mov     rcx, rdi
0x1800f20d2  mov     rax, [rax+38h]
0x1800f20d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f20db  jmp     loc_1800F1F8C
0x1800f20e0  mov     ebx, 4
0x1800f20e5  mov     rax, [rdi]
0x1800f20e8  mov     edx, 1
0x1800f20ed  mov     rcx, rdi
0x1800f20f0  mov     rax, [rax]
0x1800f20f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f20f8  test    r15, r15
0x1800f20fb  jz      short loc_1800F210A
0x1800f20fd  mov     edx, 10h
0x1800f2102  mov     rcx, r15; Block
0x1800f2105  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f210a  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f210e  test    rcx, rcx
0x1800f2111  jz      short loc_1800F211F
0x1800f2113  call    cs:__imp_CloseHandle
0x1800f211a  nop     dword ptr [rax+rax+00h]
0x1800f211f  test    r14, r14
0x1800f2122  jz      short loc_1800F2133
0x1800f2124  mov     rcx, r14; pwk
0x1800f2127  call    cs:__imp_CloseThreadpoolWork
0x1800f212e  nop     dword ptr [rax+rax+00h]
0x1800f2133  mov     eax, ebx
0x1800f2135  mov     rcx, [rbp+var_8]
0x1800f2139  xor     rcx, rsp; StackCookie
0x1800f213c  call    __security_check_cookie
0x1800f2141  mov     rbx, [rsp+80h+arg_18]
0x1800f2149  add     rsp, 80h
0x1800f2150  pop     r15
0x1800f2152  pop     r14
0x1800f2154  pop     r13
0x1800f2156  pop     r12
0x1800f2158  pop     rdi
0x1800f2159  pop     rsi
0x1800f215a  pop     rbp
0x1800f215b  retn
```
