# CSpWmiMethod<_SPACES_PhysicalDisk_Reset>::RunMethod<CSpPhysicalDisk::Reset,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800eeda8`
- end: `0x1800ef0f6`
- name: `??$RunMethod@VReset@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_Reset@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800eeda8`
- `0x1800f0484`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eef74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eef74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800eef55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800eef55`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800eef6a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800eef6a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800eef3b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800eef3b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ef014`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ef014`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ef0c7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ef0c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef0b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef0b9`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_Reset>::RunMethod<CSpPhysicalDisk::Reset,4>(
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
  CSpPhysicalDisk::Reset *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::Reset *)operator new(0x160u);
  v7 = CSpPhysicalDisk::Reset::Reset(v25);
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
      v25 = (CSpPhysicalDisk::Reset *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_180336065,
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
0x1800eeda8  mov     [rsp-38h+arg_18], rbx
0x1800eedad  push    rbp
0x1800eedae  push    rsi
0x1800eedaf  push    rdi
0x1800eedb0  push    r12
0x1800eedb2  push    r13
0x1800eedb4  push    r14
0x1800eedb6  push    r15
0x1800eedb8  mov     rbp, rsp
0x1800eedbb  sub     rsp, 80h
0x1800eedc2  mov     rax, cs:__security_cookie
0x1800eedc9  xor     rax, rsp
0x1800eedcc  mov     [rbp+var_8], rax
0x1800eedd0  xor     eax, eax
0x1800eedd2  mov     rsi, rcx
0x1800eedd5  xorps   xmm0, xmm0
0x1800eedd8  mov     [rbp+var_10], eax
0x1800eeddb  mov     ecx, 160h; Size
0x1800eede0  mov     [rbp+var_40], eax
0x1800eede3  movups  [rbp+var_20], xmm0
0x1800eede7  mov     [rbp+TokenHandle], rax
0x1800eedeb  mov     r12, r8
0x1800eedee  mov     r13, rdx
0x1800eedf1  xor     r14d, r14d
0x1800eedf4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800eedf9  mov     rcx, rax; this
0x1800eedfc  mov     [rbp+var_28], rax
0x1800eee00  call    ??0Reset@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::Reset::Reset(void)
0x1800eee05  mov     rdi, rax
0x1800eee08  test    rax, rax
0x1800eee0b  jnz     short loc_1800EEE15
0x1800eee0d  lea     ebx, [rax+1Bh]
0x1800eee10  jmp     loc_1800EF0B0
0x1800eee15  mov     rax, [rax]
0x1800eee18  mov     rdx, rsi
0x1800eee1b  mov     rcx, rdi
0x1800eee1e  xor     r15d, r15d
0x1800eee21  mov     rax, [rax+8]
0x1800eee25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eee2a  lea     rcx, [rbp+var_40]
0x1800eee2e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800eee33  mov     [rdi+1Ch], eax
0x1800eee36  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800eee3a  mov     ecx, [rsi+14h]; unsigned int
0x1800eee3d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800eee42  mov     eax, cs:dword_180397B68
0x1800eee48  cmp     eax, 5
0x1800eee4b  jbe     short loc_1800EEEBB
0x1800eee4d  mov     rdx, 400000000000h
0x1800eee57  lea     rcx, dword_180397B68
0x1800eee5e  call    _tlgKeywordOn
0x1800eee63  test    al, al
0x1800eee65  jz      short loc_1800EEEBB
0x1800eee67  mov     eax, [rbp+var_40]
0x1800eee6a  lea     rdx, byte_180336065
0x1800eee71  xor     ecx, ecx
0x1800eee73  cmp     [rdi+1Ch], eax
0x1800eee76  movzx   eax, word ptr [rbp+var_10]
0x1800eee7a  mov     word ptr [rbp+var_40], ax
0x1800eee7e  setnz   cl
0x1800eee81  mov     eax, [rsi+14h]
0x1800eee84  mov     [rbp+var_38], eax
0x1800eee87  lea     rax, [rbp+var_20]
0x1800eee8b  mov     [rbp+var_28], rax
0x1800eee8f  lea     rax, [rbp+var_3C]
0x1800eee93  mov     [rsp+80h+var_48], rax
0x1800eee98  lea     rax, [rbp+var_40]
0x1800eee9c  mov     [rsp+80h+var_50], rax
0x1800eeea1  lea     rax, [rbp+var_38]
0x1800eeea5  mov     [rsp+80h+var_58], rax
0x1800eeeaa  lea     rax, [rbp+var_28]
0x1800eeeae  mov     [rsp+80h+var_60], rax
0x1800eeeb3  mov     [rbp+var_3C], ecx
0x1800eeeb6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800eeebb  mov     rcx, [rsi]
0x1800eeebe  test    rcx, rcx
0x1800eeec1  jz      loc_1800EF086
0x1800eeec7  mov     rax, [rcx]
0x1800eeeca  test    rax, rax
0x1800eeecd  jz      loc_1800EF086
0x1800eeed3  mov     rax, [rax+18h]
0x1800eeed7  lea     r8, [rdi+20h]
0x1800eeedb  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800eeee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eeee7  mov     ebx, eax
0x1800eeee9  test    eax, eax
0x1800eeeeb  jnz     loc_1800EF08B
0x1800eeef1  cmp     [rsi+10h], r14d
0x1800eeef5  jz      loc_1800EF01F
0x1800eeefb  lea     rbx, [rdi+148h]
0x1800eef02  mov     rcx, rbx
0x1800eef05  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800eef0a  mov     rcx, rbx; struct CSpJobMgr **
0x1800eef0d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800eef12  test    eax, eax
0x1800eef14  jnz     short loc_1800EEF1E
0x1800eef16  lea     ebx, [rax+1Ch]
0x1800eef19  jmp     loc_1800EF08B
0x1800eef1e  mov     ecx, 10h; Size
0x1800eef23  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800eef28  xor     r8d, r8d; pcbe
0x1800eef2b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800eef32  mov     rdx, rax; pv
0x1800eef35  mov     r15, rax
0x1800eef38  mov     [rax], rdi
0x1800eef3b  call    cs:__imp_CreateThreadpoolWork
0x1800eef41  mov     r14, rax
0x1800eef44  test    rax, rax
0x1800eef47  jnz     short loc_1800EEF55
0x1800eef49  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800eef4e  mov     ebx, eax
0x1800eef50  jmp     loc_1800EF08B
0x1800eef55  call    cs:__imp_GetCurrentThread
0x1800eef5b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800eef5f  xor     r8d, r8d; OpenAsSelf
0x1800eef62  mov     rcx, rax; ThreadHandle
0x1800eef65  mov     edx, 2000Ch; DesiredAccess
0x1800eef6a  call    cs:__imp_OpenThreadToken
0x1800eef70  test    eax, eax
0x1800eef72  jnz     short loc_1800EEF81
0x1800eef74  call    cs:__imp_GetLastError
0x1800eef7a  cmp     eax, 3F0h
0x1800eef7f  jnz     short loc_1800EEF49
0x1800eef81  mov     rax, [rbp+TokenHandle]
0x1800eef85  mov     r8, r13
0x1800eef88  mov     [r15+8], rax
0x1800eef8c  mov     rcx, rdi
0x1800eef8f  mov     rax, [rdi]
0x1800eef92  mov     rdx, [rsi+8]
0x1800eef96  mov     rax, [rax+18h]
0x1800eef9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eef9f  mov     rax, [rdi]
0x1800eefa2  mov     rdx, r12
0x1800eefa5  mov     rcx, rdi
0x1800eefa8  mov     rax, [rax+28h]
0x1800eefac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eefb1  mov     ebx, eax
0x1800eefb3  test    eax, eax
0x1800eefb5  jz      short loc_1800EEFC0
0x1800eefb7  cmp     eax, 7
0x1800eefba  jnz     loc_1800EF08B
0x1800eefc0  mov     rax, [rdi]
0x1800eefc3  mov     rdx, r12
0x1800eefc6  mov     rcx, rdi
0x1800eefc9  mov     rax, [rax+38h]
0x1800eefcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eefd2  mov     ebx, eax
0x1800eefd4  test    eax, eax
0x1800eefd6  jnz     loc_1800EF08B
0x1800eefdc  mov     rax, [rdi+150h]
0x1800eefe3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800eefea  jnz     short loc_1800EF000
0x1800eefec  mov     rax, [rdi+158h]
0x1800eeff3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800eeffa  jz      loc_1800EF08B
0x1800ef000  mov     rdx, r12
0x1800ef003  mov     rcx, rdi
0x1800ef006  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800ef00b  mov     ebx, eax
0x1800ef00d  test    eax, eax
0x1800ef00f  jnz     short loc_1800EF08B
0x1800ef011  mov     rcx, r14; pwk
0x1800ef014  call    cs:__imp_SubmitThreadpoolWork
0x1800ef01a  jmp     loc_1800EF0CD
0x1800ef01f  mov     rax, [rdi]
0x1800ef022  mov     r8, r13
0x1800ef025  mov     rdx, [rsi+8]
0x1800ef029  mov     rcx, rdi
0x1800ef02c  mov     rax, [rax+10h]
0x1800ef030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef035  mov     rax, [rdi]
0x1800ef038  mov     rdx, r12
0x1800ef03b  mov     rcx, rdi
0x1800ef03e  mov     rax, [rax+30h]
0x1800ef042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef047  mov     ebx, eax
0x1800ef049  test    eax, eax
0x1800ef04b  jz      short loc_1800EF052
0x1800ef04d  cmp     eax, 7
0x1800ef050  jnz     short loc_1800EF08B
0x1800ef052  mov     rax, [rdi]
0x1800ef055  mov     rdx, r12
0x1800ef058  mov     rcx, rdi
0x1800ef05b  mov     rax, [rax+28h]
0x1800ef05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef064  mov     ebx, eax
0x1800ef066  test    eax, eax
0x1800ef068  jz      short loc_1800EF06F
0x1800ef06a  cmp     eax, 7
0x1800ef06d  jnz     short loc_1800EF08B
0x1800ef06f  mov     rax, [rdi]
0x1800ef072  mov     rdx, r12
0x1800ef075  mov     rcx, rdi
0x1800ef078  mov     rax, [rax+38h]
0x1800ef07c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef081  jmp     loc_1800EEF4E
0x1800ef086  mov     ebx, 4
0x1800ef08b  mov     rax, [rdi]
0x1800ef08e  mov     edx, 1
0x1800ef093  mov     rcx, rdi
0x1800ef096  mov     rax, [rax]
0x1800ef099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef09e  test    r15, r15
0x1800ef0a1  jz      short loc_1800EF0B0
0x1800ef0a3  mov     edx, 10h
0x1800ef0a8  mov     rcx, r15; Block
0x1800ef0ab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ef0b0  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ef0b4  test    rcx, rcx
0x1800ef0b7  jz      short loc_1800EF0BF
0x1800ef0b9  call    cs:__imp_CloseHandle
0x1800ef0bf  test    r14, r14
0x1800ef0c2  jz      short loc_1800EF0CD
0x1800ef0c4  mov     rcx, r14; pwk
0x1800ef0c7  call    cs:__imp_CloseThreadpoolWork
0x1800ef0cd  mov     eax, ebx
0x1800ef0cf  mov     rcx, [rbp+var_8]
0x1800ef0d3  xor     rcx, rsp; StackCookie
0x1800ef0d6  call    __security_check_cookie
0x1800ef0db  mov     rbx, [rsp+80h+arg_18]
0x1800ef0e3  add     rsp, 80h
0x1800ef0ea  pop     r15
0x1800ef0ec  pop     r14
0x1800ef0ee  pop     r13
0x1800ef0f0  pop     r12
0x1800ef0f2  pop     rdi
0x1800ef0f3  pop     rsi
0x1800ef0f4  pop     rbp
0x1800ef0f5  retn
```
