# CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::CreateVolume,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bdd98`
- end: `0x1800be115`
- name: `??$RunMethod@VCreateVolume@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800bdd98`
- `0x1800c0ee8`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdf76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdf76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bdf4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bdf4b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bdf66`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bdf66`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bdf2b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bdf2b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800be020`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800be020`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800be0df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800be0df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be0cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be0cb`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::CreateVolume,11>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 Volume; // rax
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
  CSpStoragePool::CreateVolume *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::CreateVolume *)operator new(0x240u);
  Volume = CSpStoragePool::CreateVolume::CreateVolume(v25);
  v8 = Volume;
  if ( Volume )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)Volume + 8LL))(Volume, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStoragePool::CreateVolume *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_180332358,
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
0x1800bdd98  mov     [rsp-38h+arg_18], rbx
0x1800bdd9d  push    rbp
0x1800bdd9e  push    rsi
0x1800bdd9f  push    rdi
0x1800bdda0  push    r12
0x1800bdda2  push    r13
0x1800bdda4  push    r14
0x1800bdda6  push    r15
0x1800bdda8  mov     rbp, rsp
0x1800bddab  sub     rsp, 80h
0x1800bddb2  mov     rax, cs:__security_cookie
0x1800bddb9  xor     rax, rsp
0x1800bddbc  mov     [rbp+var_8], rax
0x1800bddc0  xor     eax, eax
0x1800bddc2  mov     rsi, rcx
0x1800bddc5  xorps   xmm0, xmm0
0x1800bddc8  mov     [rbp+var_10], eax
0x1800bddcb  mov     ecx, 240h; Size
0x1800bddd0  mov     [rbp+var_40], eax
0x1800bddd3  movups  [rbp+var_20], xmm0
0x1800bddd7  mov     [rbp+TokenHandle], rax
0x1800bdddb  mov     r12, r8
0x1800bddde  mov     r13, rdx
0x1800bdde1  xor     r14d, r14d
0x1800bdde4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bdde9  mov     rcx, rax; this
0x1800bddec  mov     [rbp+var_28], rax
0x1800bddf0  call    ??0CreateVolume@CSpStoragePool@@QEAA@XZ; CSpStoragePool::CreateVolume::CreateVolume(void)
0x1800bddf5  mov     rdi, rax
0x1800bddf8  test    rax, rax
0x1800bddfb  jnz     short loc_1800BDE05
0x1800bddfd  lea     ebx, [rax+1Bh]
0x1800bde00  jmp     loc_1800BE0C2
0x1800bde05  mov     rax, [rax]
0x1800bde08  mov     rdx, rsi
0x1800bde0b  mov     rcx, rdi
0x1800bde0e  xor     r15d, r15d
0x1800bde11  mov     rax, [rax+8]
0x1800bde15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bde1a  lea     rcx, [rbp+var_40]
0x1800bde1e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bde23  mov     [rdi+1Ch], eax
0x1800bde26  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bde2a  mov     ecx, [rsi+14h]; unsigned int
0x1800bde2d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bde32  mov     eax, cs:dword_18039EB68
0x1800bde38  cmp     eax, 5
0x1800bde3b  jbe     short loc_1800BDEAB
0x1800bde3d  mov     rdx, 400000000000h
0x1800bde47  lea     rcx, dword_18039EB68
0x1800bde4e  call    _tlgKeywordOn
0x1800bde53  test    al, al
0x1800bde55  jz      short loc_1800BDEAB
0x1800bde57  mov     eax, [rbp+var_40]
0x1800bde5a  lea     rdx, unk_180332358
0x1800bde61  xor     ecx, ecx
0x1800bde63  cmp     [rdi+1Ch], eax
0x1800bde66  movzx   eax, word ptr [rbp+var_10]
0x1800bde6a  mov     word ptr [rbp+var_40], ax
0x1800bde6e  setnz   cl
0x1800bde71  mov     eax, [rsi+14h]
0x1800bde74  mov     [rbp+var_38], eax
0x1800bde77  lea     rax, [rbp+var_20]
0x1800bde7b  mov     [rbp+var_28], rax
0x1800bde7f  lea     rax, [rbp+var_3C]
0x1800bde83  mov     [rsp+80h+var_48], rax
0x1800bde88  lea     rax, [rbp+var_40]
0x1800bde8c  mov     [rsp+80h+var_50], rax
0x1800bde91  lea     rax, [rbp+var_38]
0x1800bde95  mov     [rsp+80h+var_58], rax
0x1800bde9a  lea     rax, [rbp+var_28]
0x1800bde9e  mov     [rsp+80h+var_60], rax
0x1800bdea3  mov     [rbp+var_3C], ecx
0x1800bdea6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bdeab  mov     rcx, [rsi]
0x1800bdeae  test    rcx, rcx
0x1800bdeb1  jz      loc_1800BE098
0x1800bdeb7  mov     rax, [rcx]
0x1800bdeba  test    rax, rax
0x1800bdebd  jz      loc_1800BE098
0x1800bdec3  mov     rax, [rax+18h]
0x1800bdec7  lea     r8, [rdi+20h]
0x1800bdecb  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bded2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bded7  mov     ebx, eax
0x1800bded9  test    eax, eax
0x1800bdedb  jnz     loc_1800BE09D
0x1800bdee1  cmp     [rsi+10h], r14d
0x1800bdee5  jz      loc_1800BE031
0x1800bdeeb  lea     rbx, [rdi+148h]
0x1800bdef2  mov     rcx, rbx
0x1800bdef5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bdefa  mov     rcx, rbx; struct CSpJobMgr **
0x1800bdefd  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bdf02  test    eax, eax
0x1800bdf04  jnz     short loc_1800BDF0E
0x1800bdf06  lea     ebx, [rax+1Ch]
0x1800bdf09  jmp     loc_1800BE09D
0x1800bdf0e  mov     ecx, 10h; Size
0x1800bdf13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bdf18  xor     r8d, r8d; pcbe
0x1800bdf1b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bdf22  mov     rdx, rax; pv
0x1800bdf25  mov     r15, rax
0x1800bdf28  mov     [rax], rdi
0x1800bdf2b  call    cs:__imp_CreateThreadpoolWork
0x1800bdf32  nop     dword ptr [rax+rax+00h]
0x1800bdf37  mov     r14, rax
0x1800bdf3a  test    rax, rax
0x1800bdf3d  jnz     short loc_1800BDF4B
0x1800bdf3f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bdf44  mov     ebx, eax
0x1800bdf46  jmp     loc_1800BE09D
0x1800bdf4b  call    cs:__imp_GetCurrentThread
0x1800bdf52  nop     dword ptr [rax+rax+00h]
0x1800bdf57  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bdf5b  xor     r8d, r8d; OpenAsSelf
0x1800bdf5e  mov     rcx, rax; ThreadHandle
0x1800bdf61  mov     edx, 2000Ch; DesiredAccess
0x1800bdf66  call    cs:__imp_OpenThreadToken
0x1800bdf6d  nop     dword ptr [rax+rax+00h]
0x1800bdf72  test    eax, eax
0x1800bdf74  jnz     short loc_1800BDF89
0x1800bdf76  call    cs:__imp_GetLastError
0x1800bdf7d  nop     dword ptr [rax+rax+00h]
0x1800bdf82  cmp     eax, 3F0h
0x1800bdf87  jnz     short loc_1800BDF3F
0x1800bdf89  mov     rax, [rbp+TokenHandle]
0x1800bdf8d  mov     r8, r13
0x1800bdf90  mov     [r15+8], rax
0x1800bdf94  mov     rcx, rdi
0x1800bdf97  mov     rax, [rdi]
0x1800bdf9a  mov     rdx, [rsi+8]
0x1800bdf9e  mov     rax, [rax+18h]
0x1800bdfa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdfa7  mov     rax, [rdi]
0x1800bdfaa  mov     rdx, r12
0x1800bdfad  mov     rcx, rdi
0x1800bdfb0  mov     rax, [rax+28h]
0x1800bdfb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdfb9  mov     ebx, eax
0x1800bdfbb  test    eax, eax
0x1800bdfbd  jz      short loc_1800BDFC8
0x1800bdfbf  cmp     eax, 7
0x1800bdfc2  jnz     loc_1800BE09D
0x1800bdfc8  mov     rax, [rdi]
0x1800bdfcb  mov     rdx, r12
0x1800bdfce  mov     rcx, rdi
0x1800bdfd1  mov     rax, [rax+38h]
0x1800bdfd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdfda  mov     ebx, eax
0x1800bdfdc  test    eax, eax
0x1800bdfde  jnz     loc_1800BE09D
0x1800bdfe4  mov     rax, [rdi+150h]
0x1800bdfeb  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bdff2  jnz     short loc_1800BE008
0x1800bdff4  mov     rax, [rdi+158h]
0x1800bdffb  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800be002  jz      loc_1800BE09D
0x1800be008  mov     rdx, r12
0x1800be00b  mov     rcx, rdi
0x1800be00e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800be013  mov     ebx, eax
0x1800be015  test    eax, eax
0x1800be017  jnz     loc_1800BE09D
0x1800be01d  mov     rcx, r14; pwk
0x1800be020  call    cs:__imp_SubmitThreadpoolWork
0x1800be027  nop     dword ptr [rax+rax+00h]
0x1800be02c  jmp     loc_1800BE0EB
0x1800be031  mov     rax, [rdi]
0x1800be034  mov     r8, r13
0x1800be037  mov     rdx, [rsi+8]
0x1800be03b  mov     rcx, rdi
0x1800be03e  mov     rax, [rax+10h]
0x1800be042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be047  mov     rax, [rdi]
0x1800be04a  mov     rdx, r12
0x1800be04d  mov     rcx, rdi
0x1800be050  mov     rax, [rax+30h]
0x1800be054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be059  mov     ebx, eax
0x1800be05b  test    eax, eax
0x1800be05d  jz      short loc_1800BE064
0x1800be05f  cmp     eax, 7
0x1800be062  jnz     short loc_1800BE09D
0x1800be064  mov     rax, [rdi]
0x1800be067  mov     rdx, r12
0x1800be06a  mov     rcx, rdi
0x1800be06d  mov     rax, [rax+28h]
0x1800be071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be076  mov     ebx, eax
0x1800be078  test    eax, eax
0x1800be07a  jz      short loc_1800BE081
0x1800be07c  cmp     eax, 7
0x1800be07f  jnz     short loc_1800BE09D
0x1800be081  mov     rax, [rdi]
0x1800be084  mov     rdx, r12
0x1800be087  mov     rcx, rdi
0x1800be08a  mov     rax, [rax+38h]
0x1800be08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be093  jmp     loc_1800BDF44
0x1800be098  mov     ebx, 4
0x1800be09d  mov     rax, [rdi]
0x1800be0a0  mov     edx, 1
0x1800be0a5  mov     rcx, rdi
0x1800be0a8  mov     rax, [rax]
0x1800be0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be0b0  test    r15, r15
0x1800be0b3  jz      short loc_1800BE0C2
0x1800be0b5  mov     edx, 10h
0x1800be0ba  mov     rcx, r15; Block
0x1800be0bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800be0c2  mov     rcx, [rbp+TokenHandle]; hObject
0x1800be0c6  test    rcx, rcx
0x1800be0c9  jz      short loc_1800BE0D7
0x1800be0cb  call    cs:__imp_CloseHandle
0x1800be0d2  nop     dword ptr [rax+rax+00h]
0x1800be0d7  test    r14, r14
0x1800be0da  jz      short loc_1800BE0EB
0x1800be0dc  mov     rcx, r14; pwk
0x1800be0df  call    cs:__imp_CloseThreadpoolWork
0x1800be0e6  nop     dword ptr [rax+rax+00h]
0x1800be0eb  mov     eax, ebx
0x1800be0ed  mov     rcx, [rbp+var_8]
0x1800be0f1  xor     rcx, rsp; StackCookie
0x1800be0f4  call    __security_check_cookie
0x1800be0f9  mov     rbx, [rsp+80h+arg_18]
0x1800be101  add     rsp, 80h
0x1800be108  pop     r15
0x1800be10a  pop     r14
0x1800be10c  pop     r13
0x1800be10e  pop     r12
0x1800be110  pop     rdi
0x1800be111  pop     rsi
0x1800be112  pop     rbp
0x1800be113  retn
```
