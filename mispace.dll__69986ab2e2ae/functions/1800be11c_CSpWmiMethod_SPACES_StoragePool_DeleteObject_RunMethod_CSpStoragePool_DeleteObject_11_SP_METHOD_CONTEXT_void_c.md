# CSpWmiMethod<_SPACES_StoragePool_DeleteObject>::RunMethod<CSpStoragePool::DeleteObject,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800be11c`
- end: `0x1800be499`
- name: `??$RunMethod@VDeleteObject@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_DeleteObject@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800c5060`

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
- `0x1800be11c`
- `0x1800c0fd4`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be2fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be2fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800be2cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800be2cf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800be2ea`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800be2ea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800be2af`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800be2af`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800be3a4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800be3a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800be463`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800be463`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be44f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be44f`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_DeleteObject>::RunMethod<CSpStoragePool::DeleteObject,11>(
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
  CSpStoragePool::DeleteObject *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::DeleteObject *)operator new(0x168u);
  v7 = CSpStoragePool::DeleteObject::DeleteObject(v25);
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
      v25 = (CSpStoragePool::DeleteObject *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18032FDCB,
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
0x1800be11c  mov     [rsp-38h+arg_18], rbx
0x1800be121  push    rbp
0x1800be122  push    rsi
0x1800be123  push    rdi
0x1800be124  push    r12
0x1800be126  push    r13
0x1800be128  push    r14
0x1800be12a  push    r15
0x1800be12c  mov     rbp, rsp
0x1800be12f  sub     rsp, 80h
0x1800be136  mov     rax, cs:__security_cookie
0x1800be13d  xor     rax, rsp
0x1800be140  mov     [rbp+var_8], rax
0x1800be144  xor     eax, eax
0x1800be146  mov     rsi, rcx
0x1800be149  xorps   xmm0, xmm0
0x1800be14c  mov     [rbp+var_10], eax
0x1800be14f  mov     ecx, 168h; Size
0x1800be154  mov     [rbp+var_40], eax
0x1800be157  movups  [rbp+var_20], xmm0
0x1800be15b  mov     [rbp+TokenHandle], rax
0x1800be15f  mov     r12, r8
0x1800be162  mov     r13, rdx
0x1800be165  xor     r14d, r14d
0x1800be168  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800be16d  mov     rcx, rax; this
0x1800be170  mov     [rbp+var_28], rax
0x1800be174  call    ??0DeleteObject@CSpStoragePool@@QEAA@XZ; CSpStoragePool::DeleteObject::DeleteObject(void)
0x1800be179  mov     rdi, rax
0x1800be17c  test    rax, rax
0x1800be17f  jnz     short loc_1800BE189
0x1800be181  lea     ebx, [rax+1Bh]
0x1800be184  jmp     loc_1800BE446
0x1800be189  mov     rax, [rax]
0x1800be18c  mov     rdx, rsi
0x1800be18f  mov     rcx, rdi
0x1800be192  xor     r15d, r15d
0x1800be195  mov     rax, [rax+8]
0x1800be199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be19e  lea     rcx, [rbp+var_40]
0x1800be1a2  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800be1a7  mov     [rdi+1Ch], eax
0x1800be1aa  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800be1ae  mov     ecx, [rsi+14h]; unsigned int
0x1800be1b1  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800be1b6  mov     eax, cs:dword_18039EB68
0x1800be1bc  cmp     eax, 5
0x1800be1bf  jbe     short loc_1800BE22F
0x1800be1c1  mov     rdx, 400000000000h
0x1800be1cb  lea     rcx, dword_18039EB68
0x1800be1d2  call    _tlgKeywordOn
0x1800be1d7  test    al, al
0x1800be1d9  jz      short loc_1800BE22F
0x1800be1db  mov     eax, [rbp+var_40]
0x1800be1de  lea     rdx, byte_18032FDCB
0x1800be1e5  xor     ecx, ecx
0x1800be1e7  cmp     [rdi+1Ch], eax
0x1800be1ea  movzx   eax, word ptr [rbp+var_10]
0x1800be1ee  mov     word ptr [rbp+var_40], ax
0x1800be1f2  setnz   cl
0x1800be1f5  mov     eax, [rsi+14h]
0x1800be1f8  mov     [rbp+var_38], eax
0x1800be1fb  lea     rax, [rbp+var_20]
0x1800be1ff  mov     [rbp+var_28], rax
0x1800be203  lea     rax, [rbp+var_3C]
0x1800be207  mov     [rsp+80h+var_48], rax
0x1800be20c  lea     rax, [rbp+var_40]
0x1800be210  mov     [rsp+80h+var_50], rax
0x1800be215  lea     rax, [rbp+var_38]
0x1800be219  mov     [rsp+80h+var_58], rax
0x1800be21e  lea     rax, [rbp+var_28]
0x1800be222  mov     [rsp+80h+var_60], rax
0x1800be227  mov     [rbp+var_3C], ecx
0x1800be22a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800be22f  mov     rcx, [rsi]
0x1800be232  test    rcx, rcx
0x1800be235  jz      loc_1800BE41C
0x1800be23b  mov     rax, [rcx]
0x1800be23e  test    rax, rax
0x1800be241  jz      loc_1800BE41C
0x1800be247  mov     rax, [rax+18h]
0x1800be24b  lea     r8, [rdi+20h]
0x1800be24f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800be256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be25b  mov     ebx, eax
0x1800be25d  test    eax, eax
0x1800be25f  jnz     loc_1800BE421
0x1800be265  cmp     [rsi+10h], r14d
0x1800be269  jz      loc_1800BE3B5
0x1800be26f  lea     rbx, [rdi+148h]
0x1800be276  mov     rcx, rbx
0x1800be279  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800be27e  mov     rcx, rbx; struct CSpJobMgr **
0x1800be281  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800be286  test    eax, eax
0x1800be288  jnz     short loc_1800BE292
0x1800be28a  lea     ebx, [rax+1Ch]
0x1800be28d  jmp     loc_1800BE421
0x1800be292  mov     ecx, 10h; Size
0x1800be297  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800be29c  xor     r8d, r8d; pcbe
0x1800be29f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800be2a6  mov     rdx, rax; pv
0x1800be2a9  mov     r15, rax
0x1800be2ac  mov     [rax], rdi
0x1800be2af  call    cs:__imp_CreateThreadpoolWork
0x1800be2b6  nop     dword ptr [rax+rax+00h]
0x1800be2bb  mov     r14, rax
0x1800be2be  test    rax, rax
0x1800be2c1  jnz     short loc_1800BE2CF
0x1800be2c3  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800be2c8  mov     ebx, eax
0x1800be2ca  jmp     loc_1800BE421
0x1800be2cf  call    cs:__imp_GetCurrentThread
0x1800be2d6  nop     dword ptr [rax+rax+00h]
0x1800be2db  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800be2df  xor     r8d, r8d; OpenAsSelf
0x1800be2e2  mov     rcx, rax; ThreadHandle
0x1800be2e5  mov     edx, 2000Ch; DesiredAccess
0x1800be2ea  call    cs:__imp_OpenThreadToken
0x1800be2f1  nop     dword ptr [rax+rax+00h]
0x1800be2f6  test    eax, eax
0x1800be2f8  jnz     short loc_1800BE30D
0x1800be2fa  call    cs:__imp_GetLastError
0x1800be301  nop     dword ptr [rax+rax+00h]
0x1800be306  cmp     eax, 3F0h
0x1800be30b  jnz     short loc_1800BE2C3
0x1800be30d  mov     rax, [rbp+TokenHandle]
0x1800be311  mov     r8, r13
0x1800be314  mov     [r15+8], rax
0x1800be318  mov     rcx, rdi
0x1800be31b  mov     rax, [rdi]
0x1800be31e  mov     rdx, [rsi+8]
0x1800be322  mov     rax, [rax+18h]
0x1800be326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be32b  mov     rax, [rdi]
0x1800be32e  mov     rdx, r12
0x1800be331  mov     rcx, rdi
0x1800be334  mov     rax, [rax+28h]
0x1800be338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be33d  mov     ebx, eax
0x1800be33f  test    eax, eax
0x1800be341  jz      short loc_1800BE34C
0x1800be343  cmp     eax, 7
0x1800be346  jnz     loc_1800BE421
0x1800be34c  mov     rax, [rdi]
0x1800be34f  mov     rdx, r12
0x1800be352  mov     rcx, rdi
0x1800be355  mov     rax, [rax+38h]
0x1800be359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be35e  mov     ebx, eax
0x1800be360  test    eax, eax
0x1800be362  jnz     loc_1800BE421
0x1800be368  mov     rax, [rdi+150h]
0x1800be36f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800be376  jnz     short loc_1800BE38C
0x1800be378  mov     rax, [rdi+158h]
0x1800be37f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800be386  jz      loc_1800BE421
0x1800be38c  mov     rdx, r12
0x1800be38f  mov     rcx, rdi
0x1800be392  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800be397  mov     ebx, eax
0x1800be399  test    eax, eax
0x1800be39b  jnz     loc_1800BE421
0x1800be3a1  mov     rcx, r14; pwk
0x1800be3a4  call    cs:__imp_SubmitThreadpoolWork
0x1800be3ab  nop     dword ptr [rax+rax+00h]
0x1800be3b0  jmp     loc_1800BE46F
0x1800be3b5  mov     rax, [rdi]
0x1800be3b8  mov     r8, r13
0x1800be3bb  mov     rdx, [rsi+8]
0x1800be3bf  mov     rcx, rdi
0x1800be3c2  mov     rax, [rax+10h]
0x1800be3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be3cb  mov     rax, [rdi]
0x1800be3ce  mov     rdx, r12
0x1800be3d1  mov     rcx, rdi
0x1800be3d4  mov     rax, [rax+30h]
0x1800be3d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be3dd  mov     ebx, eax
0x1800be3df  test    eax, eax
0x1800be3e1  jz      short loc_1800BE3E8
0x1800be3e3  cmp     eax, 7
0x1800be3e6  jnz     short loc_1800BE421
0x1800be3e8  mov     rax, [rdi]
0x1800be3eb  mov     rdx, r12
0x1800be3ee  mov     rcx, rdi
0x1800be3f1  mov     rax, [rax+28h]
0x1800be3f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be3fa  mov     ebx, eax
0x1800be3fc  test    eax, eax
0x1800be3fe  jz      short loc_1800BE405
0x1800be400  cmp     eax, 7
0x1800be403  jnz     short loc_1800BE421
0x1800be405  mov     rax, [rdi]
0x1800be408  mov     rdx, r12
0x1800be40b  mov     rcx, rdi
0x1800be40e  mov     rax, [rax+38h]
0x1800be412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be417  jmp     loc_1800BE2C8
0x1800be41c  mov     ebx, 4
0x1800be421  mov     rax, [rdi]
0x1800be424  mov     edx, 1
0x1800be429  mov     rcx, rdi
0x1800be42c  mov     rax, [rax]
0x1800be42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be434  test    r15, r15
0x1800be437  jz      short loc_1800BE446
0x1800be439  mov     edx, 10h
0x1800be43e  mov     rcx, r15; Block
0x1800be441  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800be446  mov     rcx, [rbp+TokenHandle]; hObject
0x1800be44a  test    rcx, rcx
0x1800be44d  jz      short loc_1800BE45B
0x1800be44f  call    cs:__imp_CloseHandle
0x1800be456  nop     dword ptr [rax+rax+00h]
0x1800be45b  test    r14, r14
0x1800be45e  jz      short loc_1800BE46F
0x1800be460  mov     rcx, r14; pwk
0x1800be463  call    cs:__imp_CloseThreadpoolWork
0x1800be46a  nop     dword ptr [rax+rax+00h]
0x1800be46f  mov     eax, ebx
0x1800be471  mov     rcx, [rbp+var_8]
0x1800be475  xor     rcx, rsp; StackCookie
0x1800be478  call    __security_check_cookie
0x1800be47d  mov     rbx, [rsp+80h+arg_18]
0x1800be485  add     rsp, 80h
0x1800be48c  pop     r15
0x1800be48e  pop     r14
0x1800be490  pop     r13
0x1800be492  pop     r12
0x1800be494  pop     rdi
0x1800be495  pop     rsi
0x1800be496  pop     rbp
0x1800be497  retn
```
