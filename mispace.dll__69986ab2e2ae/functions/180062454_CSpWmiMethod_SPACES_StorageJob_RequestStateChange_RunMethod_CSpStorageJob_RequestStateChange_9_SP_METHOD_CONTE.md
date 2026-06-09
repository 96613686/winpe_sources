# CSpWmiMethod<_SPACES_StorageJob_RequestStateChange>::RunMethod<CSpStorageJob::RequestStateChange,9>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x180062454`
- end: `0x18006273b`
- name: `??$RunMethod@VRequestStateChange@CSpStorageJob@@$08@?$CSpWmiMethod@U_SPACES_StorageJob_RequestStateChange@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x180062454`
- `0x180062930`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800625a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800625a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180062579`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180062579`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180062595`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180062595`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180062559`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180062559`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180062650`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180062650`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180062710`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180062710`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800626fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800626fc`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageJob_RequestStateChange>::RunMethod<CSpStorageJob::RequestStateChange,9>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 v7; // rax
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
  CSpStorageJob::RequestStateChange *v19; // [rsp+28h] [rbp-60h] BYREF
  __int128 v20; // [rsp+30h] [rbp-58h]
  int v21; // [rsp+40h] [rbp-48h]

  v21 = 0;
  TokenHandle = 0;
  v20 = 0;
  ThreadpoolWork = 0;
  v19 = (CSpStorageJob::RequestStateChange *)operator new(0x160u);
  v7 = CSpStorageJob::RequestStateChange::RequestStateChange(v19);
  v8 = v7;
  if ( v7 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 8LL))(v7, a1);
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
0x180062454  push    rbx
0x180062456  push    rbp
0x180062457  push    rsi
0x180062458  push    rdi
0x180062459  push    r12
0x18006245b  push    r14
0x18006245d  push    r15
0x18006245f  sub     rsp, 50h
0x180062463  mov     rax, cs:__security_cookie
0x18006246a  xor     rax, rsp
0x18006246d  mov     [rsp+88h+var_40], rax
0x180062472  xor     eax, eax
0x180062474  mov     r15, rcx
0x180062477  xorps   xmm0, xmm0
0x18006247a  mov     [rsp+88h+var_48], eax
0x18006247e  mov     ecx, 160h; Size
0x180062483  mov     [rsp+88h+TokenHandle], rax
0x180062488  movups  [rsp+88h+var_58], xmm0
0x18006248d  mov     rbp, r8
0x180062490  mov     r12, rdx
0x180062493  xor     esi, esi
0x180062495  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006249a  mov     rcx, rax; this
0x18006249d  mov     [rsp+88h+var_60], rax
0x1800624a2  call    ??0RequestStateChange@CSpStorageJob@@QEAA@XZ; CSpStorageJob::RequestStateChange::RequestStateChange(void)
0x1800624a7  mov     rdi, rax
0x1800624aa  test    rax, rax
0x1800624ad  jnz     short loc_1800624B7
0x1800624af  lea     ebx, [rsi+1Bh]
0x1800624b2  jmp     loc_1800626F2
0x1800624b7  mov     rax, [rax]
0x1800624ba  mov     rdx, r15
0x1800624bd  mov     rcx, rdi
0x1800624c0  xor     r14d, r14d
0x1800624c3  mov     rax, [rax+8]
0x1800624c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624cc  lea     rcx, [rsp+88h+var_60]
0x1800624d1  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800624d6  mov     [rdi+1Ch], eax
0x1800624d9  mov     rcx, [r15]
0x1800624dc  test    rcx, rcx
0x1800624df  jz      loc_1800626C8
0x1800624e5  mov     rax, [rcx]
0x1800624e8  test    rax, rax
0x1800624eb  jz      loc_1800626C8
0x1800624f1  mov     rax, [rax+18h]
0x1800624f5  lea     r8, [rdi+20h]
0x1800624f9  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180062500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062505  mov     ebx, eax
0x180062507  test    eax, eax
0x180062509  jnz     loc_1800626CD
0x18006250f  cmp     [r15+10h], esi
0x180062513  jz      loc_180062661
0x180062519  lea     rbx, [rdi+148h]
0x180062520  mov     rcx, rbx
0x180062523  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180062528  mov     rcx, rbx; struct CSpJobMgr **
0x18006252b  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x180062530  test    eax, eax
0x180062532  jnz     short loc_18006253C
0x180062534  lea     ebx, [rax+1Ch]
0x180062537  jmp     loc_1800626CD
0x18006253c  mov     ecx, 10h; Size
0x180062541  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180062546  xor     r8d, r8d; pcbe
0x180062549  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180062550  mov     rdx, rax; pv
0x180062553  mov     r14, rax
0x180062556  mov     [rax], rdi
0x180062559  call    cs:__imp_CreateThreadpoolWork
0x180062560  nop     dword ptr [rax+rax+00h]
0x180062565  mov     rsi, rax
0x180062568  test    rax, rax
0x18006256b  jnz     short loc_180062579
0x18006256d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180062572  mov     ebx, eax
0x180062574  jmp     loc_1800626CD
0x180062579  call    cs:__imp_GetCurrentThread
0x180062580  nop     dword ptr [rax+rax+00h]
0x180062585  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x18006258a  xor     r8d, r8d; OpenAsSelf
0x18006258d  mov     rcx, rax; ThreadHandle
0x180062590  mov     edx, 2000Ch; DesiredAccess
0x180062595  call    cs:__imp_OpenThreadToken
0x18006259c  nop     dword ptr [rax+rax+00h]
0x1800625a1  test    eax, eax
0x1800625a3  jnz     short loc_1800625B8
0x1800625a5  call    cs:__imp_GetLastError
0x1800625ac  nop     dword ptr [rax+rax+00h]
0x1800625b1  cmp     eax, 3F0h
0x1800625b6  jnz     short loc_18006256D
0x1800625b8  mov     rax, [rsp+88h+TokenHandle]
0x1800625bd  mov     r8, r12
0x1800625c0  mov     [r14+8], rax
0x1800625c4  mov     rcx, rdi
0x1800625c7  mov     rax, [rdi]
0x1800625ca  mov     rdx, [r15+8]
0x1800625ce  mov     rax, [rax+18h]
0x1800625d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800625d7  mov     rax, [rdi]
0x1800625da  mov     rdx, rbp
0x1800625dd  mov     rcx, rdi
0x1800625e0  mov     rax, [rax+28h]
0x1800625e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800625e9  mov     ebx, eax
0x1800625eb  test    eax, eax
0x1800625ed  jz      short loc_1800625F8
0x1800625ef  cmp     eax, 7
0x1800625f2  jnz     loc_1800626CD
0x1800625f8  mov     rax, [rdi]
0x1800625fb  mov     rdx, rbp
0x1800625fe  mov     rcx, rdi
0x180062601  mov     rax, [rax+38h]
0x180062605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006260a  mov     ebx, eax
0x18006260c  test    eax, eax
0x18006260e  jnz     loc_1800626CD
0x180062614  mov     rax, [rdi+150h]
0x18006261b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180062622  jnz     short loc_180062638
0x180062624  mov     rax, [rdi+158h]
0x18006262b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180062632  jz      loc_1800626CD
0x180062638  mov     rdx, rbp
0x18006263b  mov     rcx, rdi
0x18006263e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x180062643  mov     ebx, eax
0x180062645  test    eax, eax
0x180062647  jnz     loc_1800626CD
0x18006264d  mov     rcx, rsi; pwk
0x180062650  call    cs:__imp_SubmitThreadpoolWork
0x180062657  nop     dword ptr [rax+rax+00h]
0x18006265c  jmp     loc_18006271C
0x180062661  mov     rax, [rdi]
0x180062664  mov     r8, r12
0x180062667  mov     rdx, [r15+8]
0x18006266b  mov     rcx, rdi
0x18006266e  mov     rax, [rax+10h]
0x180062672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062677  mov     rax, [rdi]
0x18006267a  mov     rdx, rbp
0x18006267d  mov     rcx, rdi
0x180062680  mov     rax, [rax+30h]
0x180062684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062689  mov     ebx, eax
0x18006268b  test    eax, eax
0x18006268d  jz      short loc_180062694
0x18006268f  cmp     eax, 7
0x180062692  jnz     short loc_1800626CD
0x180062694  mov     rax, [rdi]
0x180062697  mov     rdx, rbp
0x18006269a  mov     rcx, rdi
0x18006269d  mov     rax, [rax+28h]
0x1800626a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626a6  mov     ebx, eax
0x1800626a8  test    eax, eax
0x1800626aa  jz      short loc_1800626B1
0x1800626ac  cmp     eax, 7
0x1800626af  jnz     short loc_1800626CD
0x1800626b1  mov     rax, [rdi]
0x1800626b4  mov     rdx, rbp
0x1800626b7  mov     rcx, rdi
0x1800626ba  mov     rax, [rax+38h]
0x1800626be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626c3  jmp     loc_180062572
0x1800626c8  mov     ebx, 4
0x1800626cd  mov     rax, [rdi]
0x1800626d0  mov     edx, 1
0x1800626d5  mov     rcx, rdi
0x1800626d8  mov     rax, [rax]
0x1800626db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800626e0  test    r14, r14
0x1800626e3  jz      short loc_1800626F2
0x1800626e5  mov     edx, 10h
0x1800626ea  mov     rcx, r14; Block
0x1800626ed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800626f2  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x1800626f7  test    rcx, rcx
0x1800626fa  jz      short loc_180062708
0x1800626fc  call    cs:__imp_CloseHandle
0x180062703  nop     dword ptr [rax+rax+00h]
0x180062708  test    rsi, rsi
0x18006270b  jz      short loc_18006271C
0x18006270d  mov     rcx, rsi; pwk
0x180062710  call    cs:__imp_CloseThreadpoolWork
0x180062717  nop     dword ptr [rax+rax+00h]
0x18006271c  mov     eax, ebx
0x18006271e  mov     rcx, [rsp+88h+var_40]
0x180062723  xor     rcx, rsp; StackCookie
0x180062726  call    __security_check_cookie
0x18006272b  add     rsp, 50h
0x18006272f  pop     r15
0x180062731  pop     r14
0x180062733  pop     r12
0x180062735  pop     rdi
0x180062736  pop     rsi
0x180062737  pop     rbp
0x180062738  pop     rbx
0x180062739  retn
```
