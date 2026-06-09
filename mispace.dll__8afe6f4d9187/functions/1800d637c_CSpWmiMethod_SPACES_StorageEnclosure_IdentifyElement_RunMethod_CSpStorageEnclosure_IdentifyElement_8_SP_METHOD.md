# CSpWmiMethod<_SPACES_StorageEnclosure_IdentifyElement>::RunMethod<CSpStorageEnclosure::IdentifyElement,8>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800d637c`
- end: `0x1800d66ca`
- name: `??$RunMethod@VIdentifyElement@CSpStorageEnclosure@@$07@?$CSpWmiMethod@U_SPACES_StorageEnclosure_IdentifyElement@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800d8f20`

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
- `0x1800d637c`
- `0x1800d71bc`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6548`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6548`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d6529`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d6529`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d653e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d653e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d650f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d650f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d65e8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d65e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d669b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d669b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d668d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d668d`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageEnclosure_IdentifyElement>::RunMethod<CSpStorageEnclosure::IdentifyElement,8>(
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
  CSpStorageEnclosure::IdentifyElement *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageEnclosure::IdentifyElement *)operator new(0x160u);
  v7 = CSpStorageEnclosure::IdentifyElement::IdentifyElement(v25);
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
      v25 = (CSpStorageEnclosure::IdentifyElement *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_18032EBA7,
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
0x1800d637c  mov     [rsp-38h+arg_18], rbx
0x1800d6381  push    rbp
0x1800d6382  push    rsi
0x1800d6383  push    rdi
0x1800d6384  push    r12
0x1800d6386  push    r13
0x1800d6388  push    r14
0x1800d638a  push    r15
0x1800d638c  mov     rbp, rsp
0x1800d638f  sub     rsp, 80h
0x1800d6396  mov     rax, cs:__security_cookie
0x1800d639d  xor     rax, rsp
0x1800d63a0  mov     [rbp+var_8], rax
0x1800d63a4  xor     eax, eax
0x1800d63a6  mov     rsi, rcx
0x1800d63a9  xorps   xmm0, xmm0
0x1800d63ac  mov     [rbp+var_10], eax
0x1800d63af  mov     ecx, 160h; Size
0x1800d63b4  mov     [rbp+var_40], eax
0x1800d63b7  movups  [rbp+var_20], xmm0
0x1800d63bb  mov     [rbp+TokenHandle], rax
0x1800d63bf  mov     r12, r8
0x1800d63c2  mov     r13, rdx
0x1800d63c5  xor     r14d, r14d
0x1800d63c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d63cd  mov     rcx, rax; this
0x1800d63d0  mov     [rbp+var_28], rax
0x1800d63d4  call    ??0IdentifyElement@CSpStorageEnclosure@@QEAA@XZ; CSpStorageEnclosure::IdentifyElement::IdentifyElement(void)
0x1800d63d9  mov     rdi, rax
0x1800d63dc  test    rax, rax
0x1800d63df  jnz     short loc_1800D63E9
0x1800d63e1  lea     ebx, [rax+1Bh]
0x1800d63e4  jmp     loc_1800D6684
0x1800d63e9  mov     rax, [rax]
0x1800d63ec  mov     rdx, rsi
0x1800d63ef  mov     rcx, rdi
0x1800d63f2  xor     r15d, r15d
0x1800d63f5  mov     rax, [rax+8]
0x1800d63f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d63fe  lea     rcx, [rbp+var_40]
0x1800d6402  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800d6407  mov     [rdi+1Ch], eax
0x1800d640a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800d640e  mov     ecx, [rsi+14h]; unsigned int
0x1800d6411  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800d6416  mov     eax, cs:dword_180397B68
0x1800d641c  cmp     eax, 5
0x1800d641f  jbe     short loc_1800D648F
0x1800d6421  mov     rdx, 400000000000h
0x1800d642b  lea     rcx, dword_180397B68
0x1800d6432  call    _tlgKeywordOn
0x1800d6437  test    al, al
0x1800d6439  jz      short loc_1800D648F
0x1800d643b  mov     eax, [rbp+var_40]
0x1800d643e  lea     rdx, byte_18032EBA7
0x1800d6445  xor     ecx, ecx
0x1800d6447  cmp     [rdi+1Ch], eax
0x1800d644a  movzx   eax, word ptr [rbp+var_10]
0x1800d644e  mov     word ptr [rbp+var_40], ax
0x1800d6452  setnz   cl
0x1800d6455  mov     eax, [rsi+14h]
0x1800d6458  mov     [rbp+var_38], eax
0x1800d645b  lea     rax, [rbp+var_20]
0x1800d645f  mov     [rbp+var_28], rax
0x1800d6463  lea     rax, [rbp+var_3C]
0x1800d6467  mov     [rsp+80h+var_48], rax
0x1800d646c  lea     rax, [rbp+var_40]
0x1800d6470  mov     [rsp+80h+var_50], rax
0x1800d6475  lea     rax, [rbp+var_38]
0x1800d6479  mov     [rsp+80h+var_58], rax
0x1800d647e  lea     rax, [rbp+var_28]
0x1800d6482  mov     [rsp+80h+var_60], rax
0x1800d6487  mov     [rbp+var_3C], ecx
0x1800d648a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800d648f  mov     rcx, [rsi]
0x1800d6492  test    rcx, rcx
0x1800d6495  jz      loc_1800D665A
0x1800d649b  mov     rax, [rcx]
0x1800d649e  test    rax, rax
0x1800d64a1  jz      loc_1800D665A
0x1800d64a7  mov     rax, [rax+18h]
0x1800d64ab  lea     r8, [rdi+20h]
0x1800d64af  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800d64b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d64bb  mov     ebx, eax
0x1800d64bd  test    eax, eax
0x1800d64bf  jnz     loc_1800D665F
0x1800d64c5  cmp     [rsi+10h], r14d
0x1800d64c9  jz      loc_1800D65F3
0x1800d64cf  lea     rbx, [rdi+148h]
0x1800d64d6  mov     rcx, rbx
0x1800d64d9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800d64de  mov     rcx, rbx; struct CSpJobMgr **
0x1800d64e1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800d64e6  test    eax, eax
0x1800d64e8  jnz     short loc_1800D64F2
0x1800d64ea  lea     ebx, [rax+1Ch]
0x1800d64ed  jmp     loc_1800D665F
0x1800d64f2  mov     ecx, 10h; Size
0x1800d64f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d64fc  xor     r8d, r8d; pcbe
0x1800d64ff  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800d6506  mov     rdx, rax; pv
0x1800d6509  mov     r15, rax
0x1800d650c  mov     [rax], rdi
0x1800d650f  call    cs:__imp_CreateThreadpoolWork
0x1800d6515  mov     r14, rax
0x1800d6518  test    rax, rax
0x1800d651b  jnz     short loc_1800D6529
0x1800d651d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800d6522  mov     ebx, eax
0x1800d6524  jmp     loc_1800D665F
0x1800d6529  call    cs:__imp_GetCurrentThread
0x1800d652f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d6533  xor     r8d, r8d; OpenAsSelf
0x1800d6536  mov     rcx, rax; ThreadHandle
0x1800d6539  mov     edx, 2000Ch; DesiredAccess
0x1800d653e  call    cs:__imp_OpenThreadToken
0x1800d6544  test    eax, eax
0x1800d6546  jnz     short loc_1800D6555
0x1800d6548  call    cs:__imp_GetLastError
0x1800d654e  cmp     eax, 3F0h
0x1800d6553  jnz     short loc_1800D651D
0x1800d6555  mov     rax, [rbp+TokenHandle]
0x1800d6559  mov     r8, r13
0x1800d655c  mov     [r15+8], rax
0x1800d6560  mov     rcx, rdi
0x1800d6563  mov     rax, [rdi]
0x1800d6566  mov     rdx, [rsi+8]
0x1800d656a  mov     rax, [rax+18h]
0x1800d656e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6573  mov     rax, [rdi]
0x1800d6576  mov     rdx, r12
0x1800d6579  mov     rcx, rdi
0x1800d657c  mov     rax, [rax+28h]
0x1800d6580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6585  mov     ebx, eax
0x1800d6587  test    eax, eax
0x1800d6589  jz      short loc_1800D6594
0x1800d658b  cmp     eax, 7
0x1800d658e  jnz     loc_1800D665F
0x1800d6594  mov     rax, [rdi]
0x1800d6597  mov     rdx, r12
0x1800d659a  mov     rcx, rdi
0x1800d659d  mov     rax, [rax+38h]
0x1800d65a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d65a6  mov     ebx, eax
0x1800d65a8  test    eax, eax
0x1800d65aa  jnz     loc_1800D665F
0x1800d65b0  mov     rax, [rdi+150h]
0x1800d65b7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800d65be  jnz     short loc_1800D65D4
0x1800d65c0  mov     rax, [rdi+158h]
0x1800d65c7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800d65ce  jz      loc_1800D665F
0x1800d65d4  mov     rdx, r12
0x1800d65d7  mov     rcx, rdi
0x1800d65da  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800d65df  mov     ebx, eax
0x1800d65e1  test    eax, eax
0x1800d65e3  jnz     short loc_1800D665F
0x1800d65e5  mov     rcx, r14; pwk
0x1800d65e8  call    cs:__imp_SubmitThreadpoolWork
0x1800d65ee  jmp     loc_1800D66A1
0x1800d65f3  mov     rax, [rdi]
0x1800d65f6  mov     r8, r13
0x1800d65f9  mov     rdx, [rsi+8]
0x1800d65fd  mov     rcx, rdi
0x1800d6600  mov     rax, [rax+10h]
0x1800d6604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6609  mov     rax, [rdi]
0x1800d660c  mov     rdx, r12
0x1800d660f  mov     rcx, rdi
0x1800d6612  mov     rax, [rax+30h]
0x1800d6616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d661b  mov     ebx, eax
0x1800d661d  test    eax, eax
0x1800d661f  jz      short loc_1800D6626
0x1800d6621  cmp     eax, 7
0x1800d6624  jnz     short loc_1800D665F
0x1800d6626  mov     rax, [rdi]
0x1800d6629  mov     rdx, r12
0x1800d662c  mov     rcx, rdi
0x1800d662f  mov     rax, [rax+28h]
0x1800d6633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6638  mov     ebx, eax
0x1800d663a  test    eax, eax
0x1800d663c  jz      short loc_1800D6643
0x1800d663e  cmp     eax, 7
0x1800d6641  jnz     short loc_1800D665F
0x1800d6643  mov     rax, [rdi]
0x1800d6646  mov     rdx, r12
0x1800d6649  mov     rcx, rdi
0x1800d664c  mov     rax, [rax+38h]
0x1800d6650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6655  jmp     loc_1800D6522
0x1800d665a  mov     ebx, 4
0x1800d665f  mov     rax, [rdi]
0x1800d6662  mov     edx, 1
0x1800d6667  mov     rcx, rdi
0x1800d666a  mov     rax, [rax]
0x1800d666d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6672  test    r15, r15
0x1800d6675  jz      short loc_1800D6684
0x1800d6677  mov     edx, 10h
0x1800d667c  mov     rcx, r15; Block
0x1800d667f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d6684  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d6688  test    rcx, rcx
0x1800d668b  jz      short loc_1800D6693
0x1800d668d  call    cs:__imp_CloseHandle
0x1800d6693  test    r14, r14
0x1800d6696  jz      short loc_1800D66A1
0x1800d6698  mov     rcx, r14; pwk
0x1800d669b  call    cs:__imp_CloseThreadpoolWork
0x1800d66a1  mov     eax, ebx
0x1800d66a3  mov     rcx, [rbp+var_8]
0x1800d66a7  xor     rcx, rsp; StackCookie
0x1800d66aa  call    __security_check_cookie
0x1800d66af  mov     rbx, [rsp+80h+arg_18]
0x1800d66b7  add     rsp, 80h
0x1800d66be  pop     r15
0x1800d66c0  pop     r14
0x1800d66c2  pop     r13
0x1800d66c4  pop     r12
0x1800d66c6  pop     rdi
0x1800d66c7  pop     rsi
0x1800d66c8  pop     rbp
0x1800d66c9  retn
```
