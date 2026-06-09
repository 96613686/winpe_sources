# CSpWmiMethod<_SPACES_PhysicalDisk_SetDescription>::RunMethod<CSpPhysicalDisk::SetDescription,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ef454`
- end: `0x1800ef7a2`
- name: `??$RunMethod@VSetDescription@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_SetDescription@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800f3f30`

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
- `0x1800ef454`
- `0x1800f04f0`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef620`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ef601`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ef601`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ef616`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ef616`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ef5e7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ef5e7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ef6c0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ef6c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ef773`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ef773`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef765`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef765`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_SetDescription>::RunMethod<CSpPhysicalDisk::SetDescription,4>(
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
  CSpPhysicalDisk::SetDescription *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::SetDescription *)operator new(0x160u);
  v7 = CSpPhysicalDisk::SetDescription::SetDescription(v25);
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
      v25 = (CSpPhysicalDisk::SetDescription *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_180336D7E,
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
0x1800ef454  mov     [rsp-38h+arg_18], rbx
0x1800ef459  push    rbp
0x1800ef45a  push    rsi
0x1800ef45b  push    rdi
0x1800ef45c  push    r12
0x1800ef45e  push    r13
0x1800ef460  push    r14
0x1800ef462  push    r15
0x1800ef464  mov     rbp, rsp
0x1800ef467  sub     rsp, 80h
0x1800ef46e  mov     rax, cs:__security_cookie
0x1800ef475  xor     rax, rsp
0x1800ef478  mov     [rbp+var_8], rax
0x1800ef47c  xor     eax, eax
0x1800ef47e  mov     rsi, rcx
0x1800ef481  xorps   xmm0, xmm0
0x1800ef484  mov     [rbp+var_10], eax
0x1800ef487  mov     ecx, 160h; Size
0x1800ef48c  mov     [rbp+var_40], eax
0x1800ef48f  movups  [rbp+var_20], xmm0
0x1800ef493  mov     [rbp+TokenHandle], rax
0x1800ef497  mov     r12, r8
0x1800ef49a  mov     r13, rdx
0x1800ef49d  xor     r14d, r14d
0x1800ef4a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ef4a5  mov     rcx, rax; this
0x1800ef4a8  mov     [rbp+var_28], rax
0x1800ef4ac  call    ??0SetDescription@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::SetDescription::SetDescription(void)
0x1800ef4b1  mov     rdi, rax
0x1800ef4b4  test    rax, rax
0x1800ef4b7  jnz     short loc_1800EF4C1
0x1800ef4b9  lea     ebx, [rax+1Bh]
0x1800ef4bc  jmp     loc_1800EF75C
0x1800ef4c1  mov     rax, [rax]
0x1800ef4c4  mov     rdx, rsi
0x1800ef4c7  mov     rcx, rdi
0x1800ef4ca  xor     r15d, r15d
0x1800ef4cd  mov     rax, [rax+8]
0x1800ef4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef4d6  lea     rcx, [rbp+var_40]
0x1800ef4da  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ef4df  mov     [rdi+1Ch], eax
0x1800ef4e2  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ef4e6  mov     ecx, [rsi+14h]; unsigned int
0x1800ef4e9  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ef4ee  mov     eax, cs:dword_180397B68
0x1800ef4f4  cmp     eax, 5
0x1800ef4f7  jbe     short loc_1800EF567
0x1800ef4f9  mov     rdx, 400000000000h
0x1800ef503  lea     rcx, dword_180397B68
0x1800ef50a  call    _tlgKeywordOn
0x1800ef50f  test    al, al
0x1800ef511  jz      short loc_1800EF567
0x1800ef513  mov     eax, [rbp+var_40]
0x1800ef516  lea     rdx, word_180336D7E
0x1800ef51d  xor     ecx, ecx
0x1800ef51f  cmp     [rdi+1Ch], eax
0x1800ef522  movzx   eax, word ptr [rbp+var_10]
0x1800ef526  mov     word ptr [rbp+var_40], ax
0x1800ef52a  setnz   cl
0x1800ef52d  mov     eax, [rsi+14h]
0x1800ef530  mov     [rbp+var_38], eax
0x1800ef533  lea     rax, [rbp+var_20]
0x1800ef537  mov     [rbp+var_28], rax
0x1800ef53b  lea     rax, [rbp+var_3C]
0x1800ef53f  mov     [rsp+80h+var_48], rax
0x1800ef544  lea     rax, [rbp+var_40]
0x1800ef548  mov     [rsp+80h+var_50], rax
0x1800ef54d  lea     rax, [rbp+var_38]
0x1800ef551  mov     [rsp+80h+var_58], rax
0x1800ef556  lea     rax, [rbp+var_28]
0x1800ef55a  mov     [rsp+80h+var_60], rax
0x1800ef55f  mov     [rbp+var_3C], ecx
0x1800ef562  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ef567  mov     rcx, [rsi]
0x1800ef56a  test    rcx, rcx
0x1800ef56d  jz      loc_1800EF732
0x1800ef573  mov     rax, [rcx]
0x1800ef576  test    rax, rax
0x1800ef579  jz      loc_1800EF732
0x1800ef57f  mov     rax, [rax+18h]
0x1800ef583  lea     r8, [rdi+20h]
0x1800ef587  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ef58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef593  mov     ebx, eax
0x1800ef595  test    eax, eax
0x1800ef597  jnz     loc_1800EF737
0x1800ef59d  cmp     [rsi+10h], r14d
0x1800ef5a1  jz      loc_1800EF6CB
0x1800ef5a7  lea     rbx, [rdi+148h]
0x1800ef5ae  mov     rcx, rbx
0x1800ef5b1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ef5b6  mov     rcx, rbx; struct CSpJobMgr **
0x1800ef5b9  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ef5be  test    eax, eax
0x1800ef5c0  jnz     short loc_1800EF5CA
0x1800ef5c2  lea     ebx, [rax+1Ch]
0x1800ef5c5  jmp     loc_1800EF737
0x1800ef5ca  mov     ecx, 10h; Size
0x1800ef5cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ef5d4  xor     r8d, r8d; pcbe
0x1800ef5d7  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ef5de  mov     rdx, rax; pv
0x1800ef5e1  mov     r15, rax
0x1800ef5e4  mov     [rax], rdi
0x1800ef5e7  call    cs:__imp_CreateThreadpoolWork
0x1800ef5ed  mov     r14, rax
0x1800ef5f0  test    rax, rax
0x1800ef5f3  jnz     short loc_1800EF601
0x1800ef5f5  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800ef5fa  mov     ebx, eax
0x1800ef5fc  jmp     loc_1800EF737
0x1800ef601  call    cs:__imp_GetCurrentThread
0x1800ef607  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ef60b  xor     r8d, r8d; OpenAsSelf
0x1800ef60e  mov     rcx, rax; ThreadHandle
0x1800ef611  mov     edx, 2000Ch; DesiredAccess
0x1800ef616  call    cs:__imp_OpenThreadToken
0x1800ef61c  test    eax, eax
0x1800ef61e  jnz     short loc_1800EF62D
0x1800ef620  call    cs:__imp_GetLastError
0x1800ef626  cmp     eax, 3F0h
0x1800ef62b  jnz     short loc_1800EF5F5
0x1800ef62d  mov     rax, [rbp+TokenHandle]
0x1800ef631  mov     r8, r13
0x1800ef634  mov     [r15+8], rax
0x1800ef638  mov     rcx, rdi
0x1800ef63b  mov     rax, [rdi]
0x1800ef63e  mov     rdx, [rsi+8]
0x1800ef642  mov     rax, [rax+18h]
0x1800ef646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef64b  mov     rax, [rdi]
0x1800ef64e  mov     rdx, r12
0x1800ef651  mov     rcx, rdi
0x1800ef654  mov     rax, [rax+28h]
0x1800ef658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef65d  mov     ebx, eax
0x1800ef65f  test    eax, eax
0x1800ef661  jz      short loc_1800EF66C
0x1800ef663  cmp     eax, 7
0x1800ef666  jnz     loc_1800EF737
0x1800ef66c  mov     rax, [rdi]
0x1800ef66f  mov     rdx, r12
0x1800ef672  mov     rcx, rdi
0x1800ef675  mov     rax, [rax+38h]
0x1800ef679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef67e  mov     ebx, eax
0x1800ef680  test    eax, eax
0x1800ef682  jnz     loc_1800EF737
0x1800ef688  mov     rax, [rdi+150h]
0x1800ef68f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800ef696  jnz     short loc_1800EF6AC
0x1800ef698  mov     rax, [rdi+158h]
0x1800ef69f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800ef6a6  jz      loc_1800EF737
0x1800ef6ac  mov     rdx, r12
0x1800ef6af  mov     rcx, rdi
0x1800ef6b2  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800ef6b7  mov     ebx, eax
0x1800ef6b9  test    eax, eax
0x1800ef6bb  jnz     short loc_1800EF737
0x1800ef6bd  mov     rcx, r14; pwk
0x1800ef6c0  call    cs:__imp_SubmitThreadpoolWork
0x1800ef6c6  jmp     loc_1800EF779
0x1800ef6cb  mov     rax, [rdi]
0x1800ef6ce  mov     r8, r13
0x1800ef6d1  mov     rdx, [rsi+8]
0x1800ef6d5  mov     rcx, rdi
0x1800ef6d8  mov     rax, [rax+10h]
0x1800ef6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef6e1  mov     rax, [rdi]
0x1800ef6e4  mov     rdx, r12
0x1800ef6e7  mov     rcx, rdi
0x1800ef6ea  mov     rax, [rax+30h]
0x1800ef6ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef6f3  mov     ebx, eax
0x1800ef6f5  test    eax, eax
0x1800ef6f7  jz      short loc_1800EF6FE
0x1800ef6f9  cmp     eax, 7
0x1800ef6fc  jnz     short loc_1800EF737
0x1800ef6fe  mov     rax, [rdi]
0x1800ef701  mov     rdx, r12
0x1800ef704  mov     rcx, rdi
0x1800ef707  mov     rax, [rax+28h]
0x1800ef70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef710  mov     ebx, eax
0x1800ef712  test    eax, eax
0x1800ef714  jz      short loc_1800EF71B
0x1800ef716  cmp     eax, 7
0x1800ef719  jnz     short loc_1800EF737
0x1800ef71b  mov     rax, [rdi]
0x1800ef71e  mov     rdx, r12
0x1800ef721  mov     rcx, rdi
0x1800ef724  mov     rax, [rax+38h]
0x1800ef728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef72d  jmp     loc_1800EF5FA
0x1800ef732  mov     ebx, 4
0x1800ef737  mov     rax, [rdi]
0x1800ef73a  mov     edx, 1
0x1800ef73f  mov     rcx, rdi
0x1800ef742  mov     rax, [rax]
0x1800ef745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef74a  test    r15, r15
0x1800ef74d  jz      short loc_1800EF75C
0x1800ef74f  mov     edx, 10h
0x1800ef754  mov     rcx, r15; Block
0x1800ef757  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ef75c  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ef760  test    rcx, rcx
0x1800ef763  jz      short loc_1800EF76B
0x1800ef765  call    cs:__imp_CloseHandle
0x1800ef76b  test    r14, r14
0x1800ef76e  jz      short loc_1800EF779
0x1800ef770  mov     rcx, r14; pwk
0x1800ef773  call    cs:__imp_CloseThreadpoolWork
0x1800ef779  mov     eax, ebx
0x1800ef77b  mov     rcx, [rbp+var_8]
0x1800ef77f  xor     rcx, rsp; StackCookie
0x1800ef782  call    __security_check_cookie
0x1800ef787  mov     rbx, [rsp+80h+arg_18]
0x1800ef78f  add     rsp, 80h
0x1800ef796  pop     r15
0x1800ef798  pop     r14
0x1800ef79a  pop     r13
0x1800ef79c  pop     r12
0x1800ef79e  pop     rdi
0x1800ef79f  pop     rsi
0x1800ef7a0  pop     rbp
0x1800ef7a1  retn
```
