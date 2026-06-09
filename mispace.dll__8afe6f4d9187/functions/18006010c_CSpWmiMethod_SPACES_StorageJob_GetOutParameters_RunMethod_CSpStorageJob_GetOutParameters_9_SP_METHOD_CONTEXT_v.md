# CSpWmiMethod<_SPACES_StorageJob_GetOutParameters>::RunMethod<CSpStorageJob::GetOutParameters,9>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006010c`
- end: `0x1800603c4`
- name: `??$RunMethod@VGetOutParameters@CSpStorageJob@@$08@?$CSpWmiMethod@U_SPACES_StorageJob_GetOutParameters@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `696`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180062110`

## callees

- `0x180006290`
- `0x1800062e0`
- `0x1800062ec`
- `0x18000c704`
- `0x180013898`
- `0x180014720`
- `0x180024dfc`
- `0x18005d58c`
- `0x18006010c`
- `0x1800607c0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006024b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006024b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006022b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006022b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180060241`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180060241`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180060211`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180060211`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800602ec`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800602ec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800603a0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800603a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060392`

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
0x18006010c  push    rbx
0x18006010e  push    rbp
0x18006010f  push    rsi
0x180060110  push    rdi
0x180060111  push    r12
0x180060113  push    r14
0x180060115  push    r15
0x180060117  sub     rsp, 50h
0x18006011b  mov     rax, cs:__security_cookie
0x180060122  xor     rax, rsp
0x180060125  mov     [rsp+88h+var_40], rax
0x18006012a  xor     eax, eax
0x18006012c  mov     r15, rcx
0x18006012f  xorps   xmm0, xmm0
0x180060132  mov     [rsp+88h+var_48], eax
0x180060136  mov     ecx, 168h; Size
0x18006013b  mov     [rsp+88h+TokenHandle], rax
0x180060140  movups  [rsp+88h+var_58], xmm0
0x180060145  mov     rbp, r8
0x180060148  mov     r12, rdx
0x18006014b  xor     esi, esi
0x18006014d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180060152  mov     rcx, rax; this
0x180060155  mov     [rsp+88h+var_60], rax
0x18006015a  call    ??0GetOutParameters@CSpStorageJob@@QEAA@XZ; CSpStorageJob::GetOutParameters::GetOutParameters(void)
0x18006015f  mov     rdi, rax
0x180060162  test    rax, rax
0x180060165  jnz     short loc_18006016F
0x180060167  lea     ebx, [rsi+1Bh]
0x18006016a  jmp     loc_180060388
0x18006016f  mov     rax, [rax]
0x180060172  mov     rdx, r15
0x180060175  mov     rcx, rdi
0x180060178  xor     r14d, r14d
0x18006017b  mov     rax, [rax+8]
0x18006017f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060184  lea     rcx, [rsp+88h+var_60]
0x180060189  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006018e  mov     [rdi+1Ch], eax
0x180060191  mov     rcx, [r15]
0x180060194  test    rcx, rcx
0x180060197  jz      loc_18006035E
0x18006019d  mov     rax, [rcx]
0x1800601a0  test    rax, rax
0x1800601a3  jz      loc_18006035E
0x1800601a9  mov     rax, [rax+18h]
0x1800601ad  lea     r8, [rdi+20h]
0x1800601b1  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800601b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800601bd  mov     ebx, eax
0x1800601bf  test    eax, eax
0x1800601c1  jnz     loc_180060363
0x1800601c7  cmp     [r15+10h], esi
0x1800601cb  jz      loc_1800602F7
0x1800601d1  lea     rbx, [rdi+148h]
0x1800601d8  mov     rcx, rbx
0x1800601db  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800601e0  mov     rcx, rbx; struct CSpJobMgr **
0x1800601e3  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800601e8  test    eax, eax
0x1800601ea  jnz     short loc_1800601F4
0x1800601ec  lea     ebx, [rax+1Ch]
0x1800601ef  jmp     loc_180060363
0x1800601f4  mov     ecx, 10h; Size
0x1800601f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800601fe  xor     r8d, r8d; pcbe
0x180060201  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180060208  mov     rdx, rax; pv
0x18006020b  mov     r14, rax
0x18006020e  mov     [rax], rdi
0x180060211  call    cs:__imp_CreateThreadpoolWork
0x180060217  mov     rsi, rax
0x18006021a  test    rax, rax
0x18006021d  jnz     short loc_18006022B
0x18006021f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180060224  mov     ebx, eax
0x180060226  jmp     loc_180060363
0x18006022b  call    cs:__imp_GetCurrentThread
0x180060231  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x180060236  xor     r8d, r8d; OpenAsSelf
0x180060239  mov     rcx, rax; ThreadHandle
0x18006023c  mov     edx, 2000Ch; DesiredAccess
0x180060241  call    cs:__imp_OpenThreadToken
0x180060247  test    eax, eax
0x180060249  jnz     short loc_180060258
0x18006024b  call    cs:__imp_GetLastError
0x180060251  cmp     eax, 3F0h
0x180060256  jnz     short loc_18006021F
0x180060258  mov     rax, [rsp+88h+TokenHandle]
0x18006025d  mov     r8, r12
0x180060260  mov     [r14+8], rax
0x180060264  mov     rcx, rdi
0x180060267  mov     rax, [rdi]
0x18006026a  mov     rdx, [r15+8]
0x18006026e  mov     rax, [rax+18h]
0x180060272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060277  mov     rax, [rdi]
0x18006027a  mov     rdx, rbp
0x18006027d  mov     rcx, rdi
0x180060280  mov     rax, [rax+28h]
0x180060284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060289  mov     ebx, eax
0x18006028b  test    eax, eax
0x18006028d  jz      short loc_180060298
0x18006028f  cmp     eax, 7
0x180060292  jnz     loc_180060363
0x180060298  mov     rax, [rdi]
0x18006029b  mov     rdx, rbp
0x18006029e  mov     rcx, rdi
0x1800602a1  mov     rax, [rax+38h]
0x1800602a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800602aa  mov     ebx, eax
0x1800602ac  test    eax, eax
0x1800602ae  jnz     loc_180060363
0x1800602b4  mov     rax, [rdi+150h]
0x1800602bb  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800602c2  jnz     short loc_1800602D8
0x1800602c4  mov     rax, [rdi+158h]
0x1800602cb  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800602d2  jz      loc_180060363
0x1800602d8  mov     rdx, rbp
0x1800602db  mov     rcx, rdi
0x1800602de  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800602e3  mov     ebx, eax
0x1800602e5  test    eax, eax
0x1800602e7  jnz     short loc_180060363
0x1800602e9  mov     rcx, rsi; pwk
0x1800602ec  call    cs:__imp_SubmitThreadpoolWork
0x1800602f2  jmp     loc_1800603A6
0x1800602f7  mov     rax, [rdi]
0x1800602fa  mov     r8, r12
0x1800602fd  mov     rdx, [r15+8]
0x180060301  mov     rcx, rdi
0x180060304  mov     rax, [rax+10h]
0x180060308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006030d  mov     rax, [rdi]
0x180060310  mov     rdx, rbp
0x180060313  mov     rcx, rdi
0x180060316  mov     rax, [rax+30h]
0x18006031a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006031f  mov     ebx, eax
0x180060321  test    eax, eax
0x180060323  jz      short loc_18006032A
0x180060325  cmp     eax, 7
0x180060328  jnz     short loc_180060363
0x18006032a  mov     rax, [rdi]
0x18006032d  mov     rdx, rbp
0x180060330  mov     rcx, rdi
0x180060333  mov     rax, [rax+28h]
0x180060337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006033c  mov     ebx, eax
0x18006033e  test    eax, eax
0x180060340  jz      short loc_180060347
0x180060342  cmp     eax, 7
0x180060345  jnz     short loc_180060363
0x180060347  mov     rax, [rdi]
0x18006034a  mov     rdx, rbp
0x18006034d  mov     rcx, rdi
0x180060350  mov     rax, [rax+38h]
0x180060354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060359  jmp     loc_180060224
0x18006035e  mov     ebx, 4
0x180060363  mov     rax, [rdi]
0x180060366  mov     edx, 1
0x18006036b  mov     rcx, rdi
0x18006036e  mov     rax, [rax]
0x180060371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060376  test    r14, r14
0x180060379  jz      short loc_180060388
0x18006037b  mov     edx, 10h
0x180060380  mov     rcx, r14; Block
0x180060383  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180060388  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x18006038d  test    rcx, rcx
0x180060390  jz      short loc_180060398
0x180060392  call    cs:__imp_CloseHandle
0x180060398  test    rsi, rsi
0x18006039b  jz      short loc_1800603A6
0x18006039d  mov     rcx, rsi; pwk
0x1800603a0  call    cs:__imp_CloseThreadpoolWork
0x1800603a6  mov     eax, ebx
0x1800603a8  mov     rcx, [rsp+88h+var_40]
0x1800603ad  xor     rcx, rsp; StackCookie
0x1800603b0  call    __security_check_cookie
0x1800603b5  add     rsp, 50h
0x1800603b9  pop     r15
0x1800603bb  pop     r14
0x1800603bd  pop     r12
0x1800603bf  pop     rdi
0x1800603c0  pop     rsi
0x1800603c1  pop     rbp
0x1800603c2  pop     rbx
0x1800603c3  retn
```
