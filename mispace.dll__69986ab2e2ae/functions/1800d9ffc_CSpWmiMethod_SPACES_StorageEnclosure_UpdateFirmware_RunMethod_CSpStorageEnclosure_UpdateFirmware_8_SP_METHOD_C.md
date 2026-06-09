# CSpWmiMethod<_SPACES_StorageEnclosure_UpdateFirmware>::RunMethod<CSpStorageEnclosure::UpdateFirmware,8>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800d9ffc`
- end: `0x1800da379`
- name: `??$RunMethod@VUpdateFirmware@CSpStorageEnclosure@@$07@?$CSpWmiMethod@U_SPACES_StorageEnclosure_UpdateFirmware@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update`

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
- `0x1800d9ffc`
- `0x1800da5c0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da1da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800da1da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800da1af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800da1af`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800da1ca`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800da1ca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800da18f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800da18f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800da284`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800da284`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800da343`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800da343`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800da32f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800da32f`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageEnclosure_UpdateFirmware>::RunMethod<CSpStorageEnclosure::UpdateFirmware,8>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 updated; // rax
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
  CSpStorageEnclosure::UpdateFirmware *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageEnclosure::UpdateFirmware *)operator new(0x160u);
  updated = CSpStorageEnclosure::UpdateFirmware::UpdateFirmware(v25);
  v8 = updated;
  if ( updated )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)updated + 8LL))(updated, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageEnclosure::UpdateFirmware *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_180336556,
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
0x1800d9ffc  mov     [rsp-38h+arg_18], rbx
0x1800da001  push    rbp
0x1800da002  push    rsi
0x1800da003  push    rdi
0x1800da004  push    r12
0x1800da006  push    r13
0x1800da008  push    r14
0x1800da00a  push    r15
0x1800da00c  mov     rbp, rsp
0x1800da00f  sub     rsp, 80h
0x1800da016  mov     rax, cs:__security_cookie
0x1800da01d  xor     rax, rsp
0x1800da020  mov     [rbp+var_8], rax
0x1800da024  xor     eax, eax
0x1800da026  mov     rsi, rcx
0x1800da029  xorps   xmm0, xmm0
0x1800da02c  mov     [rbp+var_10], eax
0x1800da02f  mov     ecx, 160h; Size
0x1800da034  mov     [rbp+var_40], eax
0x1800da037  movups  [rbp+var_20], xmm0
0x1800da03b  mov     [rbp+TokenHandle], rax
0x1800da03f  mov     r12, r8
0x1800da042  mov     r13, rdx
0x1800da045  xor     r14d, r14d
0x1800da048  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800da04d  mov     rcx, rax; this
0x1800da050  mov     [rbp+var_28], rax
0x1800da054  call    ??0UpdateFirmware@CSpStorageEnclosure@@QEAA@XZ; CSpStorageEnclosure::UpdateFirmware::UpdateFirmware(void)
0x1800da059  mov     rdi, rax
0x1800da05c  test    rax, rax
0x1800da05f  jnz     short loc_1800DA069
0x1800da061  lea     ebx, [rax+1Bh]
0x1800da064  jmp     loc_1800DA326
0x1800da069  mov     rax, [rax]
0x1800da06c  mov     rdx, rsi
0x1800da06f  mov     rcx, rdi
0x1800da072  xor     r15d, r15d
0x1800da075  mov     rax, [rax+8]
0x1800da079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da07e  lea     rcx, [rbp+var_40]
0x1800da082  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800da087  mov     [rdi+1Ch], eax
0x1800da08a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800da08e  mov     ecx, [rsi+14h]; unsigned int
0x1800da091  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800da096  mov     eax, cs:dword_18039EB68
0x1800da09c  cmp     eax, 5
0x1800da09f  jbe     short loc_1800DA10F
0x1800da0a1  mov     rdx, 400000000000h
0x1800da0ab  lea     rcx, dword_18039EB68
0x1800da0b2  call    _tlgKeywordOn
0x1800da0b7  test    al, al
0x1800da0b9  jz      short loc_1800DA10F
0x1800da0bb  mov     eax, [rbp+var_40]
0x1800da0be  lea     rdx, word_180336556
0x1800da0c5  xor     ecx, ecx
0x1800da0c7  cmp     [rdi+1Ch], eax
0x1800da0ca  movzx   eax, word ptr [rbp+var_10]
0x1800da0ce  mov     word ptr [rbp+var_40], ax
0x1800da0d2  setnz   cl
0x1800da0d5  mov     eax, [rsi+14h]
0x1800da0d8  mov     [rbp+var_38], eax
0x1800da0db  lea     rax, [rbp+var_20]
0x1800da0df  mov     [rbp+var_28], rax
0x1800da0e3  lea     rax, [rbp+var_3C]
0x1800da0e7  mov     [rsp+80h+var_48], rax
0x1800da0ec  lea     rax, [rbp+var_40]
0x1800da0f0  mov     [rsp+80h+var_50], rax
0x1800da0f5  lea     rax, [rbp+var_38]
0x1800da0f9  mov     [rsp+80h+var_58], rax
0x1800da0fe  lea     rax, [rbp+var_28]
0x1800da102  mov     [rsp+80h+var_60], rax
0x1800da107  mov     [rbp+var_3C], ecx
0x1800da10a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800da10f  mov     rcx, [rsi]
0x1800da112  test    rcx, rcx
0x1800da115  jz      loc_1800DA2FC
0x1800da11b  mov     rax, [rcx]
0x1800da11e  test    rax, rax
0x1800da121  jz      loc_1800DA2FC
0x1800da127  mov     rax, [rax+18h]
0x1800da12b  lea     r8, [rdi+20h]
0x1800da12f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800da136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da13b  mov     ebx, eax
0x1800da13d  test    eax, eax
0x1800da13f  jnz     loc_1800DA301
0x1800da145  cmp     [rsi+10h], r14d
0x1800da149  jz      loc_1800DA295
0x1800da14f  lea     rbx, [rdi+148h]
0x1800da156  mov     rcx, rbx
0x1800da159  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800da15e  mov     rcx, rbx; struct CSpJobMgr **
0x1800da161  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800da166  test    eax, eax
0x1800da168  jnz     short loc_1800DA172
0x1800da16a  lea     ebx, [rax+1Ch]
0x1800da16d  jmp     loc_1800DA301
0x1800da172  mov     ecx, 10h; Size
0x1800da177  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800da17c  xor     r8d, r8d; pcbe
0x1800da17f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800da186  mov     rdx, rax; pv
0x1800da189  mov     r15, rax
0x1800da18c  mov     [rax], rdi
0x1800da18f  call    cs:__imp_CreateThreadpoolWork
0x1800da196  nop     dword ptr [rax+rax+00h]
0x1800da19b  mov     r14, rax
0x1800da19e  test    rax, rax
0x1800da1a1  jnz     short loc_1800DA1AF
0x1800da1a3  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800da1a8  mov     ebx, eax
0x1800da1aa  jmp     loc_1800DA301
0x1800da1af  call    cs:__imp_GetCurrentThread
0x1800da1b6  nop     dword ptr [rax+rax+00h]
0x1800da1bb  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800da1bf  xor     r8d, r8d; OpenAsSelf
0x1800da1c2  mov     rcx, rax; ThreadHandle
0x1800da1c5  mov     edx, 2000Ch; DesiredAccess
0x1800da1ca  call    cs:__imp_OpenThreadToken
0x1800da1d1  nop     dword ptr [rax+rax+00h]
0x1800da1d6  test    eax, eax
0x1800da1d8  jnz     short loc_1800DA1ED
0x1800da1da  call    cs:__imp_GetLastError
0x1800da1e1  nop     dword ptr [rax+rax+00h]
0x1800da1e6  cmp     eax, 3F0h
0x1800da1eb  jnz     short loc_1800DA1A3
0x1800da1ed  mov     rax, [rbp+TokenHandle]
0x1800da1f1  mov     r8, r13
0x1800da1f4  mov     [r15+8], rax
0x1800da1f8  mov     rcx, rdi
0x1800da1fb  mov     rax, [rdi]
0x1800da1fe  mov     rdx, [rsi+8]
0x1800da202  mov     rax, [rax+18h]
0x1800da206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da20b  mov     rax, [rdi]
0x1800da20e  mov     rdx, r12
0x1800da211  mov     rcx, rdi
0x1800da214  mov     rax, [rax+28h]
0x1800da218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da21d  mov     ebx, eax
0x1800da21f  test    eax, eax
0x1800da221  jz      short loc_1800DA22C
0x1800da223  cmp     eax, 7
0x1800da226  jnz     loc_1800DA301
0x1800da22c  mov     rax, [rdi]
0x1800da22f  mov     rdx, r12
0x1800da232  mov     rcx, rdi
0x1800da235  mov     rax, [rax+38h]
0x1800da239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da23e  mov     ebx, eax
0x1800da240  test    eax, eax
0x1800da242  jnz     loc_1800DA301
0x1800da248  mov     rax, [rdi+150h]
0x1800da24f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800da256  jnz     short loc_1800DA26C
0x1800da258  mov     rax, [rdi+158h]
0x1800da25f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800da266  jz      loc_1800DA301
0x1800da26c  mov     rdx, r12
0x1800da26f  mov     rcx, rdi
0x1800da272  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800da277  mov     ebx, eax
0x1800da279  test    eax, eax
0x1800da27b  jnz     loc_1800DA301
0x1800da281  mov     rcx, r14; pwk
0x1800da284  call    cs:__imp_SubmitThreadpoolWork
0x1800da28b  nop     dword ptr [rax+rax+00h]
0x1800da290  jmp     loc_1800DA34F
0x1800da295  mov     rax, [rdi]
0x1800da298  mov     r8, r13
0x1800da29b  mov     rdx, [rsi+8]
0x1800da29f  mov     rcx, rdi
0x1800da2a2  mov     rax, [rax+10h]
0x1800da2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da2ab  mov     rax, [rdi]
0x1800da2ae  mov     rdx, r12
0x1800da2b1  mov     rcx, rdi
0x1800da2b4  mov     rax, [rax+30h]
0x1800da2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da2bd  mov     ebx, eax
0x1800da2bf  test    eax, eax
0x1800da2c1  jz      short loc_1800DA2C8
0x1800da2c3  cmp     eax, 7
0x1800da2c6  jnz     short loc_1800DA301
0x1800da2c8  mov     rax, [rdi]
0x1800da2cb  mov     rdx, r12
0x1800da2ce  mov     rcx, rdi
0x1800da2d1  mov     rax, [rax+28h]
0x1800da2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da2da  mov     ebx, eax
0x1800da2dc  test    eax, eax
0x1800da2de  jz      short loc_1800DA2E5
0x1800da2e0  cmp     eax, 7
0x1800da2e3  jnz     short loc_1800DA301
0x1800da2e5  mov     rax, [rdi]
0x1800da2e8  mov     rdx, r12
0x1800da2eb  mov     rcx, rdi
0x1800da2ee  mov     rax, [rax+38h]
0x1800da2f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da2f7  jmp     loc_1800DA1A8
0x1800da2fc  mov     ebx, 4
0x1800da301  mov     rax, [rdi]
0x1800da304  mov     edx, 1
0x1800da309  mov     rcx, rdi
0x1800da30c  mov     rax, [rax]
0x1800da30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da314  test    r15, r15
0x1800da317  jz      short loc_1800DA326
0x1800da319  mov     edx, 10h
0x1800da31e  mov     rcx, r15; Block
0x1800da321  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800da326  mov     rcx, [rbp+TokenHandle]; hObject
0x1800da32a  test    rcx, rcx
0x1800da32d  jz      short loc_1800DA33B
0x1800da32f  call    cs:__imp_CloseHandle
0x1800da336  nop     dword ptr [rax+rax+00h]
0x1800da33b  test    r14, r14
0x1800da33e  jz      short loc_1800DA34F
0x1800da340  mov     rcx, r14; pwk
0x1800da343  call    cs:__imp_CloseThreadpoolWork
0x1800da34a  nop     dword ptr [rax+rax+00h]
0x1800da34f  mov     eax, ebx
0x1800da351  mov     rcx, [rbp+var_8]
0x1800da355  xor     rcx, rsp; StackCookie
0x1800da358  call    __security_check_cookie
0x1800da35d  mov     rbx, [rsp+80h+arg_18]
0x1800da365  add     rsp, 80h
0x1800da36c  pop     r15
0x1800da36e  pop     r14
0x1800da370  pop     r13
0x1800da372  pop     r12
0x1800da374  pop     rdi
0x1800da375  pop     rsi
0x1800da376  pop     rbp
0x1800da377  retn
```
