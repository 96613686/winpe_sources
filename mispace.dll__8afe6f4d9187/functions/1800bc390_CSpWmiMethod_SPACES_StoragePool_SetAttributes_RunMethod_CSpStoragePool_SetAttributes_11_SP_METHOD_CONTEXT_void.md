# CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::RunMethod<CSpStoragePool::SetAttributes,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bc390`
- end: `0x1800bc6de`
- name: `??$RunMethod@VSetAttributes@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800c1f80`

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
- `0x1800bc390`
- `0x1800be164`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc55c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc55c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bc53d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bc53d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bc552`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bc552`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bc523`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bc523`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bc5fc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bc5fc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bc6af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bc6af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bc6a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bc6a1`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::RunMethod<CSpStoragePool::SetAttributes,11>(
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
  CSpStoragePool::SetAttributes *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::SetAttributes *)operator new(0x160u);
  v7 = CSpStoragePool::SetAttributes::SetAttributes(v25);
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
      v25 = (CSpStoragePool::SetAttributes *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_180327697,
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
0x1800bc390  mov     [rsp-38h+arg_18], rbx
0x1800bc395  push    rbp
0x1800bc396  push    rsi
0x1800bc397  push    rdi
0x1800bc398  push    r12
0x1800bc39a  push    r13
0x1800bc39c  push    r14
0x1800bc39e  push    r15
0x1800bc3a0  mov     rbp, rsp
0x1800bc3a3  sub     rsp, 80h
0x1800bc3aa  mov     rax, cs:__security_cookie
0x1800bc3b1  xor     rax, rsp
0x1800bc3b4  mov     [rbp+var_8], rax
0x1800bc3b8  xor     eax, eax
0x1800bc3ba  mov     rsi, rcx
0x1800bc3bd  xorps   xmm0, xmm0
0x1800bc3c0  mov     [rbp+var_10], eax
0x1800bc3c3  mov     ecx, 160h; Size
0x1800bc3c8  mov     [rbp+var_40], eax
0x1800bc3cb  movups  [rbp+var_20], xmm0
0x1800bc3cf  mov     [rbp+TokenHandle], rax
0x1800bc3d3  mov     r12, r8
0x1800bc3d6  mov     r13, rdx
0x1800bc3d9  xor     r14d, r14d
0x1800bc3dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bc3e1  mov     rcx, rax; this
0x1800bc3e4  mov     [rbp+var_28], rax
0x1800bc3e8  call    ??0SetAttributes@CSpStoragePool@@QEAA@XZ; CSpStoragePool::SetAttributes::SetAttributes(void)
0x1800bc3ed  mov     rdi, rax
0x1800bc3f0  test    rax, rax
0x1800bc3f3  jnz     short loc_1800BC3FD
0x1800bc3f5  lea     ebx, [rax+1Bh]
0x1800bc3f8  jmp     loc_1800BC698
0x1800bc3fd  mov     rax, [rax]
0x1800bc400  mov     rdx, rsi
0x1800bc403  mov     rcx, rdi
0x1800bc406  xor     r15d, r15d
0x1800bc409  mov     rax, [rax+8]
0x1800bc40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc412  lea     rcx, [rbp+var_40]
0x1800bc416  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bc41b  mov     [rdi+1Ch], eax
0x1800bc41e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bc422  mov     ecx, [rsi+14h]; unsigned int
0x1800bc425  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bc42a  mov     eax, cs:dword_180397B68
0x1800bc430  cmp     eax, 5
0x1800bc433  jbe     short loc_1800BC4A3
0x1800bc435  mov     rdx, 400000000000h
0x1800bc43f  lea     rcx, dword_180397B68
0x1800bc446  call    _tlgKeywordOn
0x1800bc44b  test    al, al
0x1800bc44d  jz      short loc_1800BC4A3
0x1800bc44f  mov     eax, [rbp+var_40]
0x1800bc452  lea     rdx, byte_180327697
0x1800bc459  xor     ecx, ecx
0x1800bc45b  cmp     [rdi+1Ch], eax
0x1800bc45e  movzx   eax, word ptr [rbp+var_10]
0x1800bc462  mov     word ptr [rbp+var_40], ax
0x1800bc466  setnz   cl
0x1800bc469  mov     eax, [rsi+14h]
0x1800bc46c  mov     [rbp+var_38], eax
0x1800bc46f  lea     rax, [rbp+var_20]
0x1800bc473  mov     [rbp+var_28], rax
0x1800bc477  lea     rax, [rbp+var_3C]
0x1800bc47b  mov     [rsp+80h+var_48], rax
0x1800bc480  lea     rax, [rbp+var_40]
0x1800bc484  mov     [rsp+80h+var_50], rax
0x1800bc489  lea     rax, [rbp+var_38]
0x1800bc48d  mov     [rsp+80h+var_58], rax
0x1800bc492  lea     rax, [rbp+var_28]
0x1800bc496  mov     [rsp+80h+var_60], rax
0x1800bc49b  mov     [rbp+var_3C], ecx
0x1800bc49e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bc4a3  mov     rcx, [rsi]
0x1800bc4a6  test    rcx, rcx
0x1800bc4a9  jz      loc_1800BC66E
0x1800bc4af  mov     rax, [rcx]
0x1800bc4b2  test    rax, rax
0x1800bc4b5  jz      loc_1800BC66E
0x1800bc4bb  mov     rax, [rax+18h]
0x1800bc4bf  lea     r8, [rdi+20h]
0x1800bc4c3  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bc4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc4cf  mov     ebx, eax
0x1800bc4d1  test    eax, eax
0x1800bc4d3  jnz     loc_1800BC673
0x1800bc4d9  cmp     [rsi+10h], r14d
0x1800bc4dd  jz      loc_1800BC607
0x1800bc4e3  lea     rbx, [rdi+148h]
0x1800bc4ea  mov     rcx, rbx
0x1800bc4ed  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bc4f2  mov     rcx, rbx; struct CSpJobMgr **
0x1800bc4f5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bc4fa  test    eax, eax
0x1800bc4fc  jnz     short loc_1800BC506
0x1800bc4fe  lea     ebx, [rax+1Ch]
0x1800bc501  jmp     loc_1800BC673
0x1800bc506  mov     ecx, 10h; Size
0x1800bc50b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bc510  xor     r8d, r8d; pcbe
0x1800bc513  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bc51a  mov     rdx, rax; pv
0x1800bc51d  mov     r15, rax
0x1800bc520  mov     [rax], rdi
0x1800bc523  call    cs:__imp_CreateThreadpoolWork
0x1800bc529  mov     r14, rax
0x1800bc52c  test    rax, rax
0x1800bc52f  jnz     short loc_1800BC53D
0x1800bc531  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bc536  mov     ebx, eax
0x1800bc538  jmp     loc_1800BC673
0x1800bc53d  call    cs:__imp_GetCurrentThread
0x1800bc543  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bc547  xor     r8d, r8d; OpenAsSelf
0x1800bc54a  mov     rcx, rax; ThreadHandle
0x1800bc54d  mov     edx, 2000Ch; DesiredAccess
0x1800bc552  call    cs:__imp_OpenThreadToken
0x1800bc558  test    eax, eax
0x1800bc55a  jnz     short loc_1800BC569
0x1800bc55c  call    cs:__imp_GetLastError
0x1800bc562  cmp     eax, 3F0h
0x1800bc567  jnz     short loc_1800BC531
0x1800bc569  mov     rax, [rbp+TokenHandle]
0x1800bc56d  mov     r8, r13
0x1800bc570  mov     [r15+8], rax
0x1800bc574  mov     rcx, rdi
0x1800bc577  mov     rax, [rdi]
0x1800bc57a  mov     rdx, [rsi+8]
0x1800bc57e  mov     rax, [rax+18h]
0x1800bc582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc587  mov     rax, [rdi]
0x1800bc58a  mov     rdx, r12
0x1800bc58d  mov     rcx, rdi
0x1800bc590  mov     rax, [rax+28h]
0x1800bc594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc599  mov     ebx, eax
0x1800bc59b  test    eax, eax
0x1800bc59d  jz      short loc_1800BC5A8
0x1800bc59f  cmp     eax, 7
0x1800bc5a2  jnz     loc_1800BC673
0x1800bc5a8  mov     rax, [rdi]
0x1800bc5ab  mov     rdx, r12
0x1800bc5ae  mov     rcx, rdi
0x1800bc5b1  mov     rax, [rax+38h]
0x1800bc5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc5ba  mov     ebx, eax
0x1800bc5bc  test    eax, eax
0x1800bc5be  jnz     loc_1800BC673
0x1800bc5c4  mov     rax, [rdi+150h]
0x1800bc5cb  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bc5d2  jnz     short loc_1800BC5E8
0x1800bc5d4  mov     rax, [rdi+158h]
0x1800bc5db  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bc5e2  jz      loc_1800BC673
0x1800bc5e8  mov     rdx, r12
0x1800bc5eb  mov     rcx, rdi
0x1800bc5ee  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bc5f3  mov     ebx, eax
0x1800bc5f5  test    eax, eax
0x1800bc5f7  jnz     short loc_1800BC673
0x1800bc5f9  mov     rcx, r14; pwk
0x1800bc5fc  call    cs:__imp_SubmitThreadpoolWork
0x1800bc602  jmp     loc_1800BC6B5
0x1800bc607  mov     rax, [rdi]
0x1800bc60a  mov     r8, r13
0x1800bc60d  mov     rdx, [rsi+8]
0x1800bc611  mov     rcx, rdi
0x1800bc614  mov     rax, [rax+10h]
0x1800bc618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc61d  mov     rax, [rdi]
0x1800bc620  mov     rdx, r12
0x1800bc623  mov     rcx, rdi
0x1800bc626  mov     rax, [rax+30h]
0x1800bc62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc62f  mov     ebx, eax
0x1800bc631  test    eax, eax
0x1800bc633  jz      short loc_1800BC63A
0x1800bc635  cmp     eax, 7
0x1800bc638  jnz     short loc_1800BC673
0x1800bc63a  mov     rax, [rdi]
0x1800bc63d  mov     rdx, r12
0x1800bc640  mov     rcx, rdi
0x1800bc643  mov     rax, [rax+28h]
0x1800bc647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc64c  mov     ebx, eax
0x1800bc64e  test    eax, eax
0x1800bc650  jz      short loc_1800BC657
0x1800bc652  cmp     eax, 7
0x1800bc655  jnz     short loc_1800BC673
0x1800bc657  mov     rax, [rdi]
0x1800bc65a  mov     rdx, r12
0x1800bc65d  mov     rcx, rdi
0x1800bc660  mov     rax, [rax+38h]
0x1800bc664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc669  jmp     loc_1800BC536
0x1800bc66e  mov     ebx, 4
0x1800bc673  mov     rax, [rdi]
0x1800bc676  mov     edx, 1
0x1800bc67b  mov     rcx, rdi
0x1800bc67e  mov     rax, [rax]
0x1800bc681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc686  test    r15, r15
0x1800bc689  jz      short loc_1800BC698
0x1800bc68b  mov     edx, 10h
0x1800bc690  mov     rcx, r15; Block
0x1800bc693  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bc698  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bc69c  test    rcx, rcx
0x1800bc69f  jz      short loc_1800BC6A7
0x1800bc6a1  call    cs:__imp_CloseHandle
0x1800bc6a7  test    r14, r14
0x1800bc6aa  jz      short loc_1800BC6B5
0x1800bc6ac  mov     rcx, r14; pwk
0x1800bc6af  call    cs:__imp_CloseThreadpoolWork
0x1800bc6b5  mov     eax, ebx
0x1800bc6b7  mov     rcx, [rbp+var_8]
0x1800bc6bb  xor     rcx, rsp; StackCookie
0x1800bc6be  call    __security_check_cookie
0x1800bc6c3  mov     rbx, [rsp+80h+arg_18]
0x1800bc6cb  add     rsp, 80h
0x1800bc6d2  pop     r15
0x1800bc6d4  pop     r14
0x1800bc6d6  pop     r13
0x1800bc6d8  pop     r12
0x1800bc6da  pop     rdi
0x1800bc6db  pop     rsi
0x1800bc6dc  pop     rbp
0x1800bc6dd  retn
```
