# CSpWmiMethod<_SPACES_StoragePool_SetFriendlyName>::RunMethod<CSpStoragePool::SetFriendlyName,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bca38`
- end: `0x1800bcd86`
- name: `??$RunMethod@VSetFriendlyName@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_SetFriendlyName@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800bca38`
- `0x1800be248`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcc04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcc04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bcbe5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bcbe5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bcbfa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bcbfa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bcbcb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bcbcb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bcca4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bcca4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bcd57`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bcd57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bcd49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bcd49`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_SetFriendlyName>::RunMethod<CSpStoragePool::SetFriendlyName,11>(
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
  CSpStoragePool::SetFriendlyName *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::SetFriendlyName *)operator new(0x160u);
  v7 = CSpStoragePool::SetFriendlyName::SetFriendlyName(v25);
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
      v25 = (CSpStoragePool::SetFriendlyName *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18032782B,
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
0x1800bca38  mov     [rsp-38h+arg_18], rbx
0x1800bca3d  push    rbp
0x1800bca3e  push    rsi
0x1800bca3f  push    rdi
0x1800bca40  push    r12
0x1800bca42  push    r13
0x1800bca44  push    r14
0x1800bca46  push    r15
0x1800bca48  mov     rbp, rsp
0x1800bca4b  sub     rsp, 80h
0x1800bca52  mov     rax, cs:__security_cookie
0x1800bca59  xor     rax, rsp
0x1800bca5c  mov     [rbp+var_8], rax
0x1800bca60  xor     eax, eax
0x1800bca62  mov     rsi, rcx
0x1800bca65  xorps   xmm0, xmm0
0x1800bca68  mov     [rbp+var_10], eax
0x1800bca6b  mov     ecx, 160h; Size
0x1800bca70  mov     [rbp+var_40], eax
0x1800bca73  movups  [rbp+var_20], xmm0
0x1800bca77  mov     [rbp+TokenHandle], rax
0x1800bca7b  mov     r12, r8
0x1800bca7e  mov     r13, rdx
0x1800bca81  xor     r14d, r14d
0x1800bca84  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bca89  mov     rcx, rax; this
0x1800bca8c  mov     [rbp+var_28], rax
0x1800bca90  call    ??0SetFriendlyName@CSpStoragePool@@QEAA@XZ; CSpStoragePool::SetFriendlyName::SetFriendlyName(void)
0x1800bca95  mov     rdi, rax
0x1800bca98  test    rax, rax
0x1800bca9b  jnz     short loc_1800BCAA5
0x1800bca9d  lea     ebx, [rax+1Bh]
0x1800bcaa0  jmp     loc_1800BCD40
0x1800bcaa5  mov     rax, [rax]
0x1800bcaa8  mov     rdx, rsi
0x1800bcaab  mov     rcx, rdi
0x1800bcaae  xor     r15d, r15d
0x1800bcab1  mov     rax, [rax+8]
0x1800bcab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcaba  lea     rcx, [rbp+var_40]
0x1800bcabe  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bcac3  mov     [rdi+1Ch], eax
0x1800bcac6  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bcaca  mov     ecx, [rsi+14h]; unsigned int
0x1800bcacd  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bcad2  mov     eax, cs:dword_180397B68
0x1800bcad8  cmp     eax, 5
0x1800bcadb  jbe     short loc_1800BCB4B
0x1800bcadd  mov     rdx, 400000000000h
0x1800bcae7  lea     rcx, dword_180397B68
0x1800bcaee  call    _tlgKeywordOn
0x1800bcaf3  test    al, al
0x1800bcaf5  jz      short loc_1800BCB4B
0x1800bcaf7  mov     eax, [rbp+var_40]
0x1800bcafa  lea     rdx, byte_18032782B
0x1800bcb01  xor     ecx, ecx
0x1800bcb03  cmp     [rdi+1Ch], eax
0x1800bcb06  movzx   eax, word ptr [rbp+var_10]
0x1800bcb0a  mov     word ptr [rbp+var_40], ax
0x1800bcb0e  setnz   cl
0x1800bcb11  mov     eax, [rsi+14h]
0x1800bcb14  mov     [rbp+var_38], eax
0x1800bcb17  lea     rax, [rbp+var_20]
0x1800bcb1b  mov     [rbp+var_28], rax
0x1800bcb1f  lea     rax, [rbp+var_3C]
0x1800bcb23  mov     [rsp+80h+var_48], rax
0x1800bcb28  lea     rax, [rbp+var_40]
0x1800bcb2c  mov     [rsp+80h+var_50], rax
0x1800bcb31  lea     rax, [rbp+var_38]
0x1800bcb35  mov     [rsp+80h+var_58], rax
0x1800bcb3a  lea     rax, [rbp+var_28]
0x1800bcb3e  mov     [rsp+80h+var_60], rax
0x1800bcb43  mov     [rbp+var_3C], ecx
0x1800bcb46  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bcb4b  mov     rcx, [rsi]
0x1800bcb4e  test    rcx, rcx
0x1800bcb51  jz      loc_1800BCD16
0x1800bcb57  mov     rax, [rcx]
0x1800bcb5a  test    rax, rax
0x1800bcb5d  jz      loc_1800BCD16
0x1800bcb63  mov     rax, [rax+18h]
0x1800bcb67  lea     r8, [rdi+20h]
0x1800bcb6b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bcb72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcb77  mov     ebx, eax
0x1800bcb79  test    eax, eax
0x1800bcb7b  jnz     loc_1800BCD1B
0x1800bcb81  cmp     [rsi+10h], r14d
0x1800bcb85  jz      loc_1800BCCAF
0x1800bcb8b  lea     rbx, [rdi+148h]
0x1800bcb92  mov     rcx, rbx
0x1800bcb95  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bcb9a  mov     rcx, rbx; struct CSpJobMgr **
0x1800bcb9d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bcba2  test    eax, eax
0x1800bcba4  jnz     short loc_1800BCBAE
0x1800bcba6  lea     ebx, [rax+1Ch]
0x1800bcba9  jmp     loc_1800BCD1B
0x1800bcbae  mov     ecx, 10h; Size
0x1800bcbb3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bcbb8  xor     r8d, r8d; pcbe
0x1800bcbbb  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bcbc2  mov     rdx, rax; pv
0x1800bcbc5  mov     r15, rax
0x1800bcbc8  mov     [rax], rdi
0x1800bcbcb  call    cs:__imp_CreateThreadpoolWork
0x1800bcbd1  mov     r14, rax
0x1800bcbd4  test    rax, rax
0x1800bcbd7  jnz     short loc_1800BCBE5
0x1800bcbd9  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bcbde  mov     ebx, eax
0x1800bcbe0  jmp     loc_1800BCD1B
0x1800bcbe5  call    cs:__imp_GetCurrentThread
0x1800bcbeb  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bcbef  xor     r8d, r8d; OpenAsSelf
0x1800bcbf2  mov     rcx, rax; ThreadHandle
0x1800bcbf5  mov     edx, 2000Ch; DesiredAccess
0x1800bcbfa  call    cs:__imp_OpenThreadToken
0x1800bcc00  test    eax, eax
0x1800bcc02  jnz     short loc_1800BCC11
0x1800bcc04  call    cs:__imp_GetLastError
0x1800bcc0a  cmp     eax, 3F0h
0x1800bcc0f  jnz     short loc_1800BCBD9
0x1800bcc11  mov     rax, [rbp+TokenHandle]
0x1800bcc15  mov     r8, r13
0x1800bcc18  mov     [r15+8], rax
0x1800bcc1c  mov     rcx, rdi
0x1800bcc1f  mov     rax, [rdi]
0x1800bcc22  mov     rdx, [rsi+8]
0x1800bcc26  mov     rax, [rax+18h]
0x1800bcc2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcc2f  mov     rax, [rdi]
0x1800bcc32  mov     rdx, r12
0x1800bcc35  mov     rcx, rdi
0x1800bcc38  mov     rax, [rax+28h]
0x1800bcc3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcc41  mov     ebx, eax
0x1800bcc43  test    eax, eax
0x1800bcc45  jz      short loc_1800BCC50
0x1800bcc47  cmp     eax, 7
0x1800bcc4a  jnz     loc_1800BCD1B
0x1800bcc50  mov     rax, [rdi]
0x1800bcc53  mov     rdx, r12
0x1800bcc56  mov     rcx, rdi
0x1800bcc59  mov     rax, [rax+38h]
0x1800bcc5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcc62  mov     ebx, eax
0x1800bcc64  test    eax, eax
0x1800bcc66  jnz     loc_1800BCD1B
0x1800bcc6c  mov     rax, [rdi+150h]
0x1800bcc73  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bcc7a  jnz     short loc_1800BCC90
0x1800bcc7c  mov     rax, [rdi+158h]
0x1800bcc83  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bcc8a  jz      loc_1800BCD1B
0x1800bcc90  mov     rdx, r12
0x1800bcc93  mov     rcx, rdi
0x1800bcc96  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bcc9b  mov     ebx, eax
0x1800bcc9d  test    eax, eax
0x1800bcc9f  jnz     short loc_1800BCD1B
0x1800bcca1  mov     rcx, r14; pwk
0x1800bcca4  call    cs:__imp_SubmitThreadpoolWork
0x1800bccaa  jmp     loc_1800BCD5D
0x1800bccaf  mov     rax, [rdi]
0x1800bccb2  mov     r8, r13
0x1800bccb5  mov     rdx, [rsi+8]
0x1800bccb9  mov     rcx, rdi
0x1800bccbc  mov     rax, [rax+10h]
0x1800bccc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bccc5  mov     rax, [rdi]
0x1800bccc8  mov     rdx, r12
0x1800bcccb  mov     rcx, rdi
0x1800bccce  mov     rax, [rax+30h]
0x1800bccd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bccd7  mov     ebx, eax
0x1800bccd9  test    eax, eax
0x1800bccdb  jz      short loc_1800BCCE2
0x1800bccdd  cmp     eax, 7
0x1800bcce0  jnz     short loc_1800BCD1B
0x1800bcce2  mov     rax, [rdi]
0x1800bcce5  mov     rdx, r12
0x1800bcce8  mov     rcx, rdi
0x1800bcceb  mov     rax, [rax+28h]
0x1800bccef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bccf4  mov     ebx, eax
0x1800bccf6  test    eax, eax
0x1800bccf8  jz      short loc_1800BCCFF
0x1800bccfa  cmp     eax, 7
0x1800bccfd  jnz     short loc_1800BCD1B
0x1800bccff  mov     rax, [rdi]
0x1800bcd02  mov     rdx, r12
0x1800bcd05  mov     rcx, rdi
0x1800bcd08  mov     rax, [rax+38h]
0x1800bcd0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcd11  jmp     loc_1800BCBDE
0x1800bcd16  mov     ebx, 4
0x1800bcd1b  mov     rax, [rdi]
0x1800bcd1e  mov     edx, 1
0x1800bcd23  mov     rcx, rdi
0x1800bcd26  mov     rax, [rax]
0x1800bcd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcd2e  test    r15, r15
0x1800bcd31  jz      short loc_1800BCD40
0x1800bcd33  mov     edx, 10h
0x1800bcd38  mov     rcx, r15; Block
0x1800bcd3b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bcd40  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bcd44  test    rcx, rcx
0x1800bcd47  jz      short loc_1800BCD4F
0x1800bcd49  call    cs:__imp_CloseHandle
0x1800bcd4f  test    r14, r14
0x1800bcd52  jz      short loc_1800BCD5D
0x1800bcd54  mov     rcx, r14; pwk
0x1800bcd57  call    cs:__imp_CloseThreadpoolWork
0x1800bcd5d  mov     eax, ebx
0x1800bcd5f  mov     rcx, [rbp+var_8]
0x1800bcd63  xor     rcx, rsp; StackCookie
0x1800bcd66  call    __security_check_cookie
0x1800bcd6b  mov     rbx, [rsp+80h+arg_18]
0x1800bcd73  add     rsp, 80h
0x1800bcd7a  pop     r15
0x1800bcd7c  pop     r14
0x1800bcd7e  pop     r13
0x1800bcd80  pop     r12
0x1800bcd82  pop     rdi
0x1800bcd83  pop     rsi
0x1800bcd84  pop     rbp
0x1800bcd85  retn
```
