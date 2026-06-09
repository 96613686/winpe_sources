# CSpWmiMethod<_SPACES_StorageTier_SetDescription>::RunMethod<CSpStorageTier::SetDescription,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ffcec`
- end: `0x18010003a`
- name: `??$RunMethod@VSetDescription@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_SetDescription@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180102030`

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
- `0x1800ffcec`
- `0x180100634`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffeb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffeb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ffe99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ffe99`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ffeae`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ffeae`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ffe7f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ffe7f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800fff58`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800fff58`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010000b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010000b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffffd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffffd`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_SetDescription>::RunMethod<CSpStorageTier::SetDescription,12>(
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
  CSpStorageTier::SetDescription *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::SetDescription *)operator new(0x160u);
  v7 = CSpStorageTier::SetDescription::SetDescription(v25);
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
      v25 = (CSpStorageTier::SetDescription *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_180338804,
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
0x1800ffcec  mov     [rsp-38h+arg_18], rbx
0x1800ffcf1  push    rbp
0x1800ffcf2  push    rsi
0x1800ffcf3  push    rdi
0x1800ffcf4  push    r12
0x1800ffcf6  push    r13
0x1800ffcf8  push    r14
0x1800ffcfa  push    r15
0x1800ffcfc  mov     rbp, rsp
0x1800ffcff  sub     rsp, 80h
0x1800ffd06  mov     rax, cs:__security_cookie
0x1800ffd0d  xor     rax, rsp
0x1800ffd10  mov     [rbp+var_8], rax
0x1800ffd14  xor     eax, eax
0x1800ffd16  mov     rsi, rcx
0x1800ffd19  xorps   xmm0, xmm0
0x1800ffd1c  mov     [rbp+var_10], eax
0x1800ffd1f  mov     ecx, 160h; Size
0x1800ffd24  mov     [rbp+var_40], eax
0x1800ffd27  movups  [rbp+var_20], xmm0
0x1800ffd2b  mov     [rbp+TokenHandle], rax
0x1800ffd2f  mov     r12, r8
0x1800ffd32  mov     r13, rdx
0x1800ffd35  xor     r14d, r14d
0x1800ffd38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ffd3d  mov     rcx, rax; this
0x1800ffd40  mov     [rbp+var_28], rax
0x1800ffd44  call    ??0SetDescription@CSpStorageTier@@QEAA@XZ; CSpStorageTier::SetDescription::SetDescription(void)
0x1800ffd49  mov     rdi, rax
0x1800ffd4c  test    rax, rax
0x1800ffd4f  jnz     short loc_1800FFD59
0x1800ffd51  lea     ebx, [rax+1Bh]
0x1800ffd54  jmp     loc_1800FFFF4
0x1800ffd59  mov     rax, [rax]
0x1800ffd5c  mov     rdx, rsi
0x1800ffd5f  mov     rcx, rdi
0x1800ffd62  xor     r15d, r15d
0x1800ffd65  mov     rax, [rax+8]
0x1800ffd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffd6e  lea     rcx, [rbp+var_40]
0x1800ffd72  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ffd77  mov     [rdi+1Ch], eax
0x1800ffd7a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ffd7e  mov     ecx, [rsi+14h]; unsigned int
0x1800ffd81  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ffd86  mov     eax, cs:dword_180397B68
0x1800ffd8c  cmp     eax, 5
0x1800ffd8f  jbe     short loc_1800FFDFF
0x1800ffd91  mov     rdx, 400000000000h
0x1800ffd9b  lea     rcx, dword_180397B68
0x1800ffda2  call    _tlgKeywordOn
0x1800ffda7  test    al, al
0x1800ffda9  jz      short loc_1800FFDFF
0x1800ffdab  mov     eax, [rbp+var_40]
0x1800ffdae  lea     rdx, dword_180338804
0x1800ffdb5  xor     ecx, ecx
0x1800ffdb7  cmp     [rdi+1Ch], eax
0x1800ffdba  movzx   eax, word ptr [rbp+var_10]
0x1800ffdbe  mov     word ptr [rbp+var_40], ax
0x1800ffdc2  setnz   cl
0x1800ffdc5  mov     eax, [rsi+14h]
0x1800ffdc8  mov     [rbp+var_38], eax
0x1800ffdcb  lea     rax, [rbp+var_20]
0x1800ffdcf  mov     [rbp+var_28], rax
0x1800ffdd3  lea     rax, [rbp+var_3C]
0x1800ffdd7  mov     [rsp+80h+var_48], rax
0x1800ffddc  lea     rax, [rbp+var_40]
0x1800ffde0  mov     [rsp+80h+var_50], rax
0x1800ffde5  lea     rax, [rbp+var_38]
0x1800ffde9  mov     [rsp+80h+var_58], rax
0x1800ffdee  lea     rax, [rbp+var_28]
0x1800ffdf2  mov     [rsp+80h+var_60], rax
0x1800ffdf7  mov     [rbp+var_3C], ecx
0x1800ffdfa  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ffdff  mov     rcx, [rsi]
0x1800ffe02  test    rcx, rcx
0x1800ffe05  jz      loc_1800FFFCA
0x1800ffe0b  mov     rax, [rcx]
0x1800ffe0e  test    rax, rax
0x1800ffe11  jz      loc_1800FFFCA
0x1800ffe17  mov     rax, [rax+18h]
0x1800ffe1b  lea     r8, [rdi+20h]
0x1800ffe1f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ffe26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffe2b  mov     ebx, eax
0x1800ffe2d  test    eax, eax
0x1800ffe2f  jnz     loc_1800FFFCF
0x1800ffe35  cmp     [rsi+10h], r14d
0x1800ffe39  jz      loc_1800FFF63
0x1800ffe3f  lea     rbx, [rdi+148h]
0x1800ffe46  mov     rcx, rbx
0x1800ffe49  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ffe4e  mov     rcx, rbx; struct CSpJobMgr **
0x1800ffe51  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ffe56  test    eax, eax
0x1800ffe58  jnz     short loc_1800FFE62
0x1800ffe5a  lea     ebx, [rax+1Ch]
0x1800ffe5d  jmp     loc_1800FFFCF
0x1800ffe62  mov     ecx, 10h; Size
0x1800ffe67  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ffe6c  xor     r8d, r8d; pcbe
0x1800ffe6f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ffe76  mov     rdx, rax; pv
0x1800ffe79  mov     r15, rax
0x1800ffe7c  mov     [rax], rdi
0x1800ffe7f  call    cs:__imp_CreateThreadpoolWork
0x1800ffe85  mov     r14, rax
0x1800ffe88  test    rax, rax
0x1800ffe8b  jnz     short loc_1800FFE99
0x1800ffe8d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800ffe92  mov     ebx, eax
0x1800ffe94  jmp     loc_1800FFFCF
0x1800ffe99  call    cs:__imp_GetCurrentThread
0x1800ffe9f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ffea3  xor     r8d, r8d; OpenAsSelf
0x1800ffea6  mov     rcx, rax; ThreadHandle
0x1800ffea9  mov     edx, 2000Ch; DesiredAccess
0x1800ffeae  call    cs:__imp_OpenThreadToken
0x1800ffeb4  test    eax, eax
0x1800ffeb6  jnz     short loc_1800FFEC5
0x1800ffeb8  call    cs:__imp_GetLastError
0x1800ffebe  cmp     eax, 3F0h
0x1800ffec3  jnz     short loc_1800FFE8D
0x1800ffec5  mov     rax, [rbp+TokenHandle]
0x1800ffec9  mov     r8, r13
0x1800ffecc  mov     [r15+8], rax
0x1800ffed0  mov     rcx, rdi
0x1800ffed3  mov     rax, [rdi]
0x1800ffed6  mov     rdx, [rsi+8]
0x1800ffeda  mov     rax, [rax+18h]
0x1800ffede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffee3  mov     rax, [rdi]
0x1800ffee6  mov     rdx, r12
0x1800ffee9  mov     rcx, rdi
0x1800ffeec  mov     rax, [rax+28h]
0x1800ffef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffef5  mov     ebx, eax
0x1800ffef7  test    eax, eax
0x1800ffef9  jz      short loc_1800FFF04
0x1800ffefb  cmp     eax, 7
0x1800ffefe  jnz     loc_1800FFFCF
0x1800fff04  mov     rax, [rdi]
0x1800fff07  mov     rdx, r12
0x1800fff0a  mov     rcx, rdi
0x1800fff0d  mov     rax, [rax+38h]
0x1800fff11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fff16  mov     ebx, eax
0x1800fff18  test    eax, eax
0x1800fff1a  jnz     loc_1800FFFCF
0x1800fff20  mov     rax, [rdi+150h]
0x1800fff27  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800fff2e  jnz     short loc_1800FFF44
0x1800fff30  mov     rax, [rdi+158h]
0x1800fff37  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800fff3e  jz      loc_1800FFFCF
0x1800fff44  mov     rdx, r12
0x1800fff47  mov     rcx, rdi
0x1800fff4a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800fff4f  mov     ebx, eax
0x1800fff51  test    eax, eax
0x1800fff53  jnz     short loc_1800FFFCF
0x1800fff55  mov     rcx, r14; pwk
0x1800fff58  call    cs:__imp_SubmitThreadpoolWork
0x1800fff5e  jmp     loc_180100011
0x1800fff63  mov     rax, [rdi]
0x1800fff66  mov     r8, r13
0x1800fff69  mov     rdx, [rsi+8]
0x1800fff6d  mov     rcx, rdi
0x1800fff70  mov     rax, [rax+10h]
0x1800fff74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fff79  mov     rax, [rdi]
0x1800fff7c  mov     rdx, r12
0x1800fff7f  mov     rcx, rdi
0x1800fff82  mov     rax, [rax+30h]
0x1800fff86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fff8b  mov     ebx, eax
0x1800fff8d  test    eax, eax
0x1800fff8f  jz      short loc_1800FFF96
0x1800fff91  cmp     eax, 7
0x1800fff94  jnz     short loc_1800FFFCF
0x1800fff96  mov     rax, [rdi]
0x1800fff99  mov     rdx, r12
0x1800fff9c  mov     rcx, rdi
0x1800fff9f  mov     rax, [rax+28h]
0x1800fffa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fffa8  mov     ebx, eax
0x1800fffaa  test    eax, eax
0x1800fffac  jz      short loc_1800FFFB3
0x1800fffae  cmp     eax, 7
0x1800fffb1  jnz     short loc_1800FFFCF
0x1800fffb3  mov     rax, [rdi]
0x1800fffb6  mov     rdx, r12
0x1800fffb9  mov     rcx, rdi
0x1800fffbc  mov     rax, [rax+38h]
0x1800fffc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fffc5  jmp     loc_1800FFE92
0x1800fffca  mov     ebx, 4
0x1800fffcf  mov     rax, [rdi]
0x1800fffd2  mov     edx, 1
0x1800fffd7  mov     rcx, rdi
0x1800fffda  mov     rax, [rax]
0x1800fffdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fffe2  test    r15, r15
0x1800fffe5  jz      short loc_1800FFFF4
0x1800fffe7  mov     edx, 10h
0x1800fffec  mov     rcx, r15; Block
0x1800fffef  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ffff4  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ffff8  test    rcx, rcx
0x1800ffffb  jz      short loc_180100003
0x1800ffffd  call    cs:__imp_CloseHandle
0x180100003  test    r14, r14
0x180100006  jz      short loc_180100011
0x180100008  mov     rcx, r14; pwk
0x18010000b  call    cs:__imp_CloseThreadpoolWork
0x180100011  mov     eax, ebx
0x180100013  mov     rcx, [rbp+var_8]
0x180100017  xor     rcx, rsp; StackCookie
0x18010001a  call    __security_check_cookie
0x18010001f  mov     rbx, [rsp+80h+arg_18]
0x180100027  add     rsp, 80h
0x18010002e  pop     r15
0x180100030  pop     r14
0x180100032  pop     r13
0x180100034  pop     r12
0x180100036  pop     rdi
0x180100037  pop     rsi
0x180100038  pop     rbp
0x180100039  retn
```
