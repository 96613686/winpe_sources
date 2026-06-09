# CSpWmiMethod<_SPACES_StorageJob_GetOutParameters>::RunMethod<CSpStorageJob::GetOutParameters,9>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x180062164`
- end: `0x18006244b`
- name: `??$RunMethod@VGetOutParameters@CSpStorageJob@@$08@?$CSpWmiMethod@U_SPACES_StorageJob_GetOutParameters@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x180062164`
- `0x18006287c`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800622b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800622b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180062289`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180062289`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800622a5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800622a5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180062269`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180062269`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180062360`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180062360`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180062420`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180062420`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006240c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006240c`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageJob_GetOutParameters>::RunMethod<CSpStorageJob::GetOutParameters,9>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 OutParameters; // rax
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
  CSpStorageJob::GetOutParameters *v19; // [rsp+28h] [rbp-60h] BYREF
  __int128 v20; // [rsp+30h] [rbp-58h]
  int v21; // [rsp+40h] [rbp-48h]

  v21 = 0;
  TokenHandle = 0;
  v20 = 0;
  ThreadpoolWork = 0;
  v19 = (CSpStorageJob::GetOutParameters *)operator new(0x168u);
  OutParameters = CSpStorageJob::GetOutParameters::GetOutParameters(v19);
  v8 = OutParameters;
  if ( OutParameters )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)OutParameters + 8LL))(OutParameters, a1);
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
0x180062164  push    rbx
0x180062166  push    rbp
0x180062167  push    rsi
0x180062168  push    rdi
0x180062169  push    r12
0x18006216b  push    r14
0x18006216d  push    r15
0x18006216f  sub     rsp, 50h
0x180062173  mov     rax, cs:__security_cookie
0x18006217a  xor     rax, rsp
0x18006217d  mov     [rsp+88h+var_40], rax
0x180062182  xor     eax, eax
0x180062184  mov     r15, rcx
0x180062187  xorps   xmm0, xmm0
0x18006218a  mov     [rsp+88h+var_48], eax
0x18006218e  mov     ecx, 168h; Size
0x180062193  mov     [rsp+88h+TokenHandle], rax
0x180062198  movups  [rsp+88h+var_58], xmm0
0x18006219d  mov     rbp, r8
0x1800621a0  mov     r12, rdx
0x1800621a3  xor     esi, esi
0x1800621a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800621aa  mov     rcx, rax; this
0x1800621ad  mov     [rsp+88h+var_60], rax
0x1800621b2  call    ??0GetOutParameters@CSpStorageJob@@QEAA@XZ; CSpStorageJob::GetOutParameters::GetOutParameters(void)
0x1800621b7  mov     rdi, rax
0x1800621ba  test    rax, rax
0x1800621bd  jnz     short loc_1800621C7
0x1800621bf  lea     ebx, [rsi+1Bh]
0x1800621c2  jmp     loc_180062402
0x1800621c7  mov     rax, [rax]
0x1800621ca  mov     rdx, r15
0x1800621cd  mov     rcx, rdi
0x1800621d0  xor     r14d, r14d
0x1800621d3  mov     rax, [rax+8]
0x1800621d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800621dc  lea     rcx, [rsp+88h+var_60]
0x1800621e1  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800621e6  mov     [rdi+1Ch], eax
0x1800621e9  mov     rcx, [r15]
0x1800621ec  test    rcx, rcx
0x1800621ef  jz      loc_1800623D8
0x1800621f5  mov     rax, [rcx]
0x1800621f8  test    rax, rax
0x1800621fb  jz      loc_1800623D8
0x180062201  mov     rax, [rax+18h]
0x180062205  lea     r8, [rdi+20h]
0x180062209  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180062210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062215  mov     ebx, eax
0x180062217  test    eax, eax
0x180062219  jnz     loc_1800623DD
0x18006221f  cmp     [r15+10h], esi
0x180062223  jz      loc_180062371
0x180062229  lea     rbx, [rdi+148h]
0x180062230  mov     rcx, rbx
0x180062233  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180062238  mov     rcx, rbx; struct CSpJobMgr **
0x18006223b  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x180062240  test    eax, eax
0x180062242  jnz     short loc_18006224C
0x180062244  lea     ebx, [rax+1Ch]
0x180062247  jmp     loc_1800623DD
0x18006224c  mov     ecx, 10h; Size
0x180062251  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180062256  xor     r8d, r8d; pcbe
0x180062259  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180062260  mov     rdx, rax; pv
0x180062263  mov     r14, rax
0x180062266  mov     [rax], rdi
0x180062269  call    cs:__imp_CreateThreadpoolWork
0x180062270  nop     dword ptr [rax+rax+00h]
0x180062275  mov     rsi, rax
0x180062278  test    rax, rax
0x18006227b  jnz     short loc_180062289
0x18006227d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180062282  mov     ebx, eax
0x180062284  jmp     loc_1800623DD
0x180062289  call    cs:__imp_GetCurrentThread
0x180062290  nop     dword ptr [rax+rax+00h]
0x180062295  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x18006229a  xor     r8d, r8d; OpenAsSelf
0x18006229d  mov     rcx, rax; ThreadHandle
0x1800622a0  mov     edx, 2000Ch; DesiredAccess
0x1800622a5  call    cs:__imp_OpenThreadToken
0x1800622ac  nop     dword ptr [rax+rax+00h]
0x1800622b1  test    eax, eax
0x1800622b3  jnz     short loc_1800622C8
0x1800622b5  call    cs:__imp_GetLastError
0x1800622bc  nop     dword ptr [rax+rax+00h]
0x1800622c1  cmp     eax, 3F0h
0x1800622c6  jnz     short loc_18006227D
0x1800622c8  mov     rax, [rsp+88h+TokenHandle]
0x1800622cd  mov     r8, r12
0x1800622d0  mov     [r14+8], rax
0x1800622d4  mov     rcx, rdi
0x1800622d7  mov     rax, [rdi]
0x1800622da  mov     rdx, [r15+8]
0x1800622de  mov     rax, [rax+18h]
0x1800622e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800622e7  mov     rax, [rdi]
0x1800622ea  mov     rdx, rbp
0x1800622ed  mov     rcx, rdi
0x1800622f0  mov     rax, [rax+28h]
0x1800622f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800622f9  mov     ebx, eax
0x1800622fb  test    eax, eax
0x1800622fd  jz      short loc_180062308
0x1800622ff  cmp     eax, 7
0x180062302  jnz     loc_1800623DD
0x180062308  mov     rax, [rdi]
0x18006230b  mov     rdx, rbp
0x18006230e  mov     rcx, rdi
0x180062311  mov     rax, [rax+38h]
0x180062315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006231a  mov     ebx, eax
0x18006231c  test    eax, eax
0x18006231e  jnz     loc_1800623DD
0x180062324  mov     rax, [rdi+150h]
0x18006232b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180062332  jnz     short loc_180062348
0x180062334  mov     rax, [rdi+158h]
0x18006233b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180062342  jz      loc_1800623DD
0x180062348  mov     rdx, rbp
0x18006234b  mov     rcx, rdi
0x18006234e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x180062353  mov     ebx, eax
0x180062355  test    eax, eax
0x180062357  jnz     loc_1800623DD
0x18006235d  mov     rcx, rsi; pwk
0x180062360  call    cs:__imp_SubmitThreadpoolWork
0x180062367  nop     dword ptr [rax+rax+00h]
0x18006236c  jmp     loc_18006242C
0x180062371  mov     rax, [rdi]
0x180062374  mov     r8, r12
0x180062377  mov     rdx, [r15+8]
0x18006237b  mov     rcx, rdi
0x18006237e  mov     rax, [rax+10h]
0x180062382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062387  mov     rax, [rdi]
0x18006238a  mov     rdx, rbp
0x18006238d  mov     rcx, rdi
0x180062390  mov     rax, [rax+30h]
0x180062394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062399  mov     ebx, eax
0x18006239b  test    eax, eax
0x18006239d  jz      short loc_1800623A4
0x18006239f  cmp     eax, 7
0x1800623a2  jnz     short loc_1800623DD
0x1800623a4  mov     rax, [rdi]
0x1800623a7  mov     rdx, rbp
0x1800623aa  mov     rcx, rdi
0x1800623ad  mov     rax, [rax+28h]
0x1800623b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800623b6  mov     ebx, eax
0x1800623b8  test    eax, eax
0x1800623ba  jz      short loc_1800623C1
0x1800623bc  cmp     eax, 7
0x1800623bf  jnz     short loc_1800623DD
0x1800623c1  mov     rax, [rdi]
0x1800623c4  mov     rdx, rbp
0x1800623c7  mov     rcx, rdi
0x1800623ca  mov     rax, [rax+38h]
0x1800623ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800623d3  jmp     loc_180062282
0x1800623d8  mov     ebx, 4
0x1800623dd  mov     rax, [rdi]
0x1800623e0  mov     edx, 1
0x1800623e5  mov     rcx, rdi
0x1800623e8  mov     rax, [rax]
0x1800623eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800623f0  test    r14, r14
0x1800623f3  jz      short loc_180062402
0x1800623f5  mov     edx, 10h
0x1800623fa  mov     rcx, r14; Block
0x1800623fd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180062402  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x180062407  test    rcx, rcx
0x18006240a  jz      short loc_180062418
0x18006240c  call    cs:__imp_CloseHandle
0x180062413  nop     dword ptr [rax+rax+00h]
0x180062418  test    rsi, rsi
0x18006241b  jz      short loc_18006242C
0x18006241d  mov     rcx, rsi; pwk
0x180062420  call    cs:__imp_CloseThreadpoolWork
0x180062427  nop     dword ptr [rax+rax+00h]
0x18006242c  mov     eax, ebx
0x18006242e  mov     rcx, [rsp+88h+var_40]
0x180062433  xor     rcx, rsp; StackCookie
0x180062436  call    __security_check_cookie
0x18006243b  add     rsp, 50h
0x18006243f  pop     r15
0x180062441  pop     r14
0x180062443  pop     r12
0x180062445  pop     rdi
0x180062446  pop     rsi
0x180062447  pop     rbp
0x180062448  pop     rbx
0x180062449  retn
```
