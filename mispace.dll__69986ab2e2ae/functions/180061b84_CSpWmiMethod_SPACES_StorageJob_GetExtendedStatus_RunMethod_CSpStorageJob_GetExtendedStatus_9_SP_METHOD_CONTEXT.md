# CSpWmiMethod<_SPACES_StorageJob_GetExtendedStatus>::RunMethod<CSpStorageJob::GetExtendedStatus,9>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x180061b84`
- end: `0x180061e6b`
- name: `??$RunMethod@VGetExtendedStatus@CSpStorageJob@@$08@?$CSpWmiMethod@U_SPACES_StorageJob_GetExtendedStatus@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `743`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180064210`

## callees

- `0x180006350`
- `0x1800063a0`
- `0x1800063ac`
- `0x18000c644`
- `0x180013b4c`
- `0x180014a54`
- `0x1800257fc`
- `0x18005f41c`
- `0x180061b84`
- `0x18006278c`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061cd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061cd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180061ca9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180061ca9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180061cc5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180061cc5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180061c89`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180061c89`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180061d80`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180061d80`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180061e40`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180061e40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061e2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061e2c`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageJob_GetExtendedStatus>::RunMethod<CSpStorageJob::GetExtendedStatus,9>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 ExtendedStatus; // rax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  __int64 *v10; // r14
  __int64 v11; // rcx
  enum _MI_Result v12; // eax
  HANDLE CurrentThread; // rax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  void *TokenHandle; // [rsp+20h] [rbp-68h] BYREF
  CSpStorageJob::GetExtendedStatus *v19; // [rsp+28h] [rbp-60h] BYREF
  __int128 v20; // [rsp+30h] [rbp-58h]
  int v21; // [rsp+40h] [rbp-48h]

  v21 = 0;
  TokenHandle = 0;
  v20 = 0;
  ThreadpoolWork = 0;
  v19 = (CSpStorageJob::GetExtendedStatus *)operator new(0x160u);
  ExtendedStatus = CSpStorageJob::GetExtendedStatus::GetExtendedStatus(v19);
  v8 = ExtendedStatus;
  if ( ExtendedStatus )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)ExtendedStatus + 8LL))(ExtendedStatus, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v19);
    v11 = *a1;
    if ( *a1 && *(_QWORD *)v11 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v11 + 24LL))(
             v11,
             &MSFT_StorageExtendedStatus_rtti,
             v8 + 32);
      if ( v9 )
        goto LABEL_27;
      if ( *((_DWORD *)a1 + 4) )
      {
        CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(v8 + 328);
        if ( !(unsigned int)CSpJobMgr::GetInstance((struct CSpJobMgr **)(v8 + 328)) )
        {
          v9 = 28;
          goto LABEL_27;
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
            v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
            v9 = v14;
            if ( !v14 || v14 == 7 )
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
            goto LABEL_27;
          }
        }
        v12 = GleToMiResult();
        goto LABEL_11;
      }
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 16LL))(v8, a1[1], a2);
      v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 48LL))(v8, a3);
      v9 = v15;
      if ( !v15 || v15 == 7 )
      {
        v16 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
        v9 = v16;
        if ( !v16 || v16 == 7 )
        {
          v12 = (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
LABEL_11:
          v9 = v12;
        }
      }
    }
    else
    {
      v9 = 4;
    }
LABEL_27:
    (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
    if ( v10 )
      operator delete(v10);
    goto LABEL_29;
  }
  v9 = 27;
LABEL_29:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v9;
}

```

## disassembly

```asm
0x180061b84  push    rbx
0x180061b86  push    rbp
0x180061b87  push    rsi
0x180061b88  push    rdi
0x180061b89  push    r12
0x180061b8b  push    r14
0x180061b8d  push    r15
0x180061b8f  sub     rsp, 50h
0x180061b93  mov     rax, cs:__security_cookie
0x180061b9a  xor     rax, rsp
0x180061b9d  mov     [rsp+88h+var_40], rax
0x180061ba2  xor     eax, eax
0x180061ba4  mov     r15, rcx
0x180061ba7  xorps   xmm0, xmm0
0x180061baa  mov     [rsp+88h+var_48], eax
0x180061bae  mov     ecx, 160h; Size
0x180061bb3  mov     [rsp+88h+TokenHandle], rax
0x180061bb8  movups  [rsp+88h+var_58], xmm0
0x180061bbd  mov     rbp, r8
0x180061bc0  mov     r12, rdx
0x180061bc3  xor     esi, esi
0x180061bc5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180061bca  mov     rcx, rax; this
0x180061bcd  mov     [rsp+88h+var_60], rax
0x180061bd2  call    ??0GetExtendedStatus@CSpStorageJob@@QEAA@XZ; CSpStorageJob::GetExtendedStatus::GetExtendedStatus(void)
0x180061bd7  mov     rdi, rax
0x180061bda  test    rax, rax
0x180061bdd  jnz     short loc_180061BE7
0x180061bdf  lea     ebx, [rsi+1Bh]
0x180061be2  jmp     loc_180061E22
0x180061be7  mov     rax, [rax]
0x180061bea  mov     rdx, r15
0x180061bed  mov     rcx, rdi
0x180061bf0  xor     r14d, r14d
0x180061bf3  mov     rax, [rax+8]
0x180061bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061bfc  lea     rcx, [rsp+88h+var_60]
0x180061c01  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180061c06  mov     [rdi+1Ch], eax
0x180061c09  mov     rcx, [r15]
0x180061c0c  test    rcx, rcx
0x180061c0f  jz      loc_180061DF8
0x180061c15  mov     rax, [rcx]
0x180061c18  test    rax, rax
0x180061c1b  jz      loc_180061DF8
0x180061c21  mov     rax, [rax+18h]
0x180061c25  lea     r8, [rdi+20h]
0x180061c29  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180061c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c35  mov     ebx, eax
0x180061c37  test    eax, eax
0x180061c39  jnz     loc_180061DFD
0x180061c3f  cmp     [r15+10h], esi
0x180061c43  jz      loc_180061D91
0x180061c49  lea     rbx, [rdi+148h]
0x180061c50  mov     rcx, rbx
0x180061c53  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180061c58  mov     rcx, rbx; struct CSpJobMgr **
0x180061c5b  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x180061c60  test    eax, eax
0x180061c62  jnz     short loc_180061C6C
0x180061c64  lea     ebx, [rax+1Ch]
0x180061c67  jmp     loc_180061DFD
0x180061c6c  mov     ecx, 10h; Size
0x180061c71  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180061c76  xor     r8d, r8d; pcbe
0x180061c79  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180061c80  mov     rdx, rax; pv
0x180061c83  mov     r14, rax
0x180061c86  mov     [rax], rdi
0x180061c89  call    cs:__imp_CreateThreadpoolWork
0x180061c90  nop     dword ptr [rax+rax+00h]
0x180061c95  mov     rsi, rax
0x180061c98  test    rax, rax
0x180061c9b  jnz     short loc_180061CA9
0x180061c9d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180061ca2  mov     ebx, eax
0x180061ca4  jmp     loc_180061DFD
0x180061ca9  call    cs:__imp_GetCurrentThread
0x180061cb0  nop     dword ptr [rax+rax+00h]
0x180061cb5  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x180061cba  xor     r8d, r8d; OpenAsSelf
0x180061cbd  mov     rcx, rax; ThreadHandle
0x180061cc0  mov     edx, 2000Ch; DesiredAccess
0x180061cc5  call    cs:__imp_OpenThreadToken
0x180061ccc  nop     dword ptr [rax+rax+00h]
0x180061cd1  test    eax, eax
0x180061cd3  jnz     short loc_180061CE8
0x180061cd5  call    cs:__imp_GetLastError
0x180061cdc  nop     dword ptr [rax+rax+00h]
0x180061ce1  cmp     eax, 3F0h
0x180061ce6  jnz     short loc_180061C9D
0x180061ce8  mov     rax, [rsp+88h+TokenHandle]
0x180061ced  mov     r8, r12
0x180061cf0  mov     [r14+8], rax
0x180061cf4  mov     rcx, rdi
0x180061cf7  mov     rax, [rdi]
0x180061cfa  mov     rdx, [r15+8]
0x180061cfe  mov     rax, [rax+18h]
0x180061d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061d07  mov     rax, [rdi]
0x180061d0a  mov     rdx, rbp
0x180061d0d  mov     rcx, rdi
0x180061d10  mov     rax, [rax+28h]
0x180061d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061d19  mov     ebx, eax
0x180061d1b  test    eax, eax
0x180061d1d  jz      short loc_180061D28
0x180061d1f  cmp     eax, 7
0x180061d22  jnz     loc_180061DFD
0x180061d28  mov     rax, [rdi]
0x180061d2b  mov     rdx, rbp
0x180061d2e  mov     rcx, rdi
0x180061d31  mov     rax, [rax+38h]
0x180061d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061d3a  mov     ebx, eax
0x180061d3c  test    eax, eax
0x180061d3e  jnz     loc_180061DFD
0x180061d44  mov     rax, [rdi+150h]
0x180061d4b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180061d52  jnz     short loc_180061D68
0x180061d54  mov     rax, [rdi+158h]
0x180061d5b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180061d62  jz      loc_180061DFD
0x180061d68  mov     rdx, rbp
0x180061d6b  mov     rcx, rdi
0x180061d6e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x180061d73  mov     ebx, eax
0x180061d75  test    eax, eax
0x180061d77  jnz     loc_180061DFD
0x180061d7d  mov     rcx, rsi; pwk
0x180061d80  call    cs:__imp_SubmitThreadpoolWork
0x180061d87  nop     dword ptr [rax+rax+00h]
0x180061d8c  jmp     loc_180061E4C
0x180061d91  mov     rax, [rdi]
0x180061d94  mov     r8, r12
0x180061d97  mov     rdx, [r15+8]
0x180061d9b  mov     rcx, rdi
0x180061d9e  mov     rax, [rax+10h]
0x180061da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061da7  mov     rax, [rdi]
0x180061daa  mov     rdx, rbp
0x180061dad  mov     rcx, rdi
0x180061db0  mov     rax, [rax+30h]
0x180061db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061db9  mov     ebx, eax
0x180061dbb  test    eax, eax
0x180061dbd  jz      short loc_180061DC4
0x180061dbf  cmp     eax, 7
0x180061dc2  jnz     short loc_180061DFD
0x180061dc4  mov     rax, [rdi]
0x180061dc7  mov     rdx, rbp
0x180061dca  mov     rcx, rdi
0x180061dcd  mov     rax, [rax+28h]
0x180061dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061dd6  mov     ebx, eax
0x180061dd8  test    eax, eax
0x180061dda  jz      short loc_180061DE1
0x180061ddc  cmp     eax, 7
0x180061ddf  jnz     short loc_180061DFD
0x180061de1  mov     rax, [rdi]
0x180061de4  mov     rdx, rbp
0x180061de7  mov     rcx, rdi
0x180061dea  mov     rax, [rax+38h]
0x180061dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061df3  jmp     loc_180061CA2
0x180061df8  mov     ebx, 4
0x180061dfd  mov     rax, [rdi]
0x180061e00  mov     edx, 1
0x180061e05  mov     rcx, rdi
0x180061e08  mov     rax, [rax]
0x180061e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061e10  test    r14, r14
0x180061e13  jz      short loc_180061E22
0x180061e15  mov     edx, 10h
0x180061e1a  mov     rcx, r14; Block
0x180061e1d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180061e22  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x180061e27  test    rcx, rcx
0x180061e2a  jz      short loc_180061E38
0x180061e2c  call    cs:__imp_CloseHandle
0x180061e33  nop     dword ptr [rax+rax+00h]
0x180061e38  test    rsi, rsi
0x180061e3b  jz      short loc_180061E4C
0x180061e3d  mov     rcx, rsi; pwk
0x180061e40  call    cs:__imp_CloseThreadpoolWork
0x180061e47  nop     dword ptr [rax+rax+00h]
0x180061e4c  mov     eax, ebx
0x180061e4e  mov     rcx, [rsp+88h+var_40]
0x180061e53  xor     rcx, rsp; StackCookie
0x180061e56  call    __security_check_cookie
0x180061e5b  add     rsp, 50h
0x180061e5f  pop     r15
0x180061e61  pop     r14
0x180061e63  pop     r12
0x180061e65  pop     rdi
0x180061e66  pop     rsi
0x180061e67  pop     rbp
0x180061e68  pop     rbx
0x180061e69  retn
```
