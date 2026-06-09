# CSpWmiMethod<_SPACES_PhysicalDisk_UpdateFirmware>::RunMethod<CSpPhysicalDisk::UpdateFirmware,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800efe50`
- end: `0x1800f019e`
- name: `??$RunMethod@VUpdateFirmware@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_UpdateFirmware@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update`

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
- `0x1800efe50`
- `0x1800f0634`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f001c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f001c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800efffd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800efffd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f0012`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f0012`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800effe3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800effe3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f00bc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f00bc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f016f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f016f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f0161`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f0161`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_UpdateFirmware>::RunMethod<CSpPhysicalDisk::UpdateFirmware,4>(
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
  CSpPhysicalDisk::UpdateFirmware *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::UpdateFirmware *)operator new(0x160u);
  updated = CSpPhysicalDisk::UpdateFirmware::UpdateFirmware(v25);
  v8 = updated;
  if ( updated )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)updated + 8LL))(updated, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpPhysicalDisk::UpdateFirmware *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_18033590C,
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
0x1800efe50  mov     [rsp-38h+arg_18], rbx
0x1800efe55  push    rbp
0x1800efe56  push    rsi
0x1800efe57  push    rdi
0x1800efe58  push    r12
0x1800efe5a  push    r13
0x1800efe5c  push    r14
0x1800efe5e  push    r15
0x1800efe60  mov     rbp, rsp
0x1800efe63  sub     rsp, 80h
0x1800efe6a  mov     rax, cs:__security_cookie
0x1800efe71  xor     rax, rsp
0x1800efe74  mov     [rbp+var_8], rax
0x1800efe78  xor     eax, eax
0x1800efe7a  mov     rsi, rcx
0x1800efe7d  xorps   xmm0, xmm0
0x1800efe80  mov     [rbp+var_10], eax
0x1800efe83  mov     ecx, 160h; Size
0x1800efe88  mov     [rbp+var_40], eax
0x1800efe8b  movups  [rbp+var_20], xmm0
0x1800efe8f  mov     [rbp+TokenHandle], rax
0x1800efe93  mov     r12, r8
0x1800efe96  mov     r13, rdx
0x1800efe99  xor     r14d, r14d
0x1800efe9c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800efea1  mov     rcx, rax; this
0x1800efea4  mov     [rbp+var_28], rax
0x1800efea8  call    ??0UpdateFirmware@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::UpdateFirmware::UpdateFirmware(void)
0x1800efead  mov     rdi, rax
0x1800efeb0  test    rax, rax
0x1800efeb3  jnz     short loc_1800EFEBD
0x1800efeb5  lea     ebx, [rax+1Bh]
0x1800efeb8  jmp     loc_1800F0158
0x1800efebd  mov     rax, [rax]
0x1800efec0  mov     rdx, rsi
0x1800efec3  mov     rcx, rdi
0x1800efec6  xor     r15d, r15d
0x1800efec9  mov     rax, [rax+8]
0x1800efecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efed2  lea     rcx, [rbp+var_40]
0x1800efed6  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800efedb  mov     [rdi+1Ch], eax
0x1800efede  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800efee2  mov     ecx, [rsi+14h]; unsigned int
0x1800efee5  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800efeea  mov     eax, cs:dword_180397B68
0x1800efef0  cmp     eax, 5
0x1800efef3  jbe     short loc_1800EFF63
0x1800efef5  mov     rdx, 400000000000h
0x1800efeff  lea     rcx, dword_180397B68
0x1800eff06  call    _tlgKeywordOn
0x1800eff0b  test    al, al
0x1800eff0d  jz      short loc_1800EFF63
0x1800eff0f  mov     eax, [rbp+var_40]
0x1800eff12  lea     rdx, dword_18033590C
0x1800eff19  xor     ecx, ecx
0x1800eff1b  cmp     [rdi+1Ch], eax
0x1800eff1e  movzx   eax, word ptr [rbp+var_10]
0x1800eff22  mov     word ptr [rbp+var_40], ax
0x1800eff26  setnz   cl
0x1800eff29  mov     eax, [rsi+14h]
0x1800eff2c  mov     [rbp+var_38], eax
0x1800eff2f  lea     rax, [rbp+var_20]
0x1800eff33  mov     [rbp+var_28], rax
0x1800eff37  lea     rax, [rbp+var_3C]
0x1800eff3b  mov     [rsp+80h+var_48], rax
0x1800eff40  lea     rax, [rbp+var_40]
0x1800eff44  mov     [rsp+80h+var_50], rax
0x1800eff49  lea     rax, [rbp+var_38]
0x1800eff4d  mov     [rsp+80h+var_58], rax
0x1800eff52  lea     rax, [rbp+var_28]
0x1800eff56  mov     [rsp+80h+var_60], rax
0x1800eff5b  mov     [rbp+var_3C], ecx
0x1800eff5e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800eff63  mov     rcx, [rsi]
0x1800eff66  test    rcx, rcx
0x1800eff69  jz      loc_1800F012E
0x1800eff6f  mov     rax, [rcx]
0x1800eff72  test    rax, rax
0x1800eff75  jz      loc_1800F012E
0x1800eff7b  mov     rax, [rax+18h]
0x1800eff7f  lea     r8, [rdi+20h]
0x1800eff83  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800eff8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eff8f  mov     ebx, eax
0x1800eff91  test    eax, eax
0x1800eff93  jnz     loc_1800F0133
0x1800eff99  cmp     [rsi+10h], r14d
0x1800eff9d  jz      loc_1800F00C7
0x1800effa3  lea     rbx, [rdi+148h]
0x1800effaa  mov     rcx, rbx
0x1800effad  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800effb2  mov     rcx, rbx; struct CSpJobMgr **
0x1800effb5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800effba  test    eax, eax
0x1800effbc  jnz     short loc_1800EFFC6
0x1800effbe  lea     ebx, [rax+1Ch]
0x1800effc1  jmp     loc_1800F0133
0x1800effc6  mov     ecx, 10h; Size
0x1800effcb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800effd0  xor     r8d, r8d; pcbe
0x1800effd3  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800effda  mov     rdx, rax; pv
0x1800effdd  mov     r15, rax
0x1800effe0  mov     [rax], rdi
0x1800effe3  call    cs:__imp_CreateThreadpoolWork
0x1800effe9  mov     r14, rax
0x1800effec  test    rax, rax
0x1800effef  jnz     short loc_1800EFFFD
0x1800efff1  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800efff6  mov     ebx, eax
0x1800efff8  jmp     loc_1800F0133
0x1800efffd  call    cs:__imp_GetCurrentThread
0x1800f0003  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f0007  xor     r8d, r8d; OpenAsSelf
0x1800f000a  mov     rcx, rax; ThreadHandle
0x1800f000d  mov     edx, 2000Ch; DesiredAccess
0x1800f0012  call    cs:__imp_OpenThreadToken
0x1800f0018  test    eax, eax
0x1800f001a  jnz     short loc_1800F0029
0x1800f001c  call    cs:__imp_GetLastError
0x1800f0022  cmp     eax, 3F0h
0x1800f0027  jnz     short loc_1800EFFF1
0x1800f0029  mov     rax, [rbp+TokenHandle]
0x1800f002d  mov     r8, r13
0x1800f0030  mov     [r15+8], rax
0x1800f0034  mov     rcx, rdi
0x1800f0037  mov     rax, [rdi]
0x1800f003a  mov     rdx, [rsi+8]
0x1800f003e  mov     rax, [rax+18h]
0x1800f0042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0047  mov     rax, [rdi]
0x1800f004a  mov     rdx, r12
0x1800f004d  mov     rcx, rdi
0x1800f0050  mov     rax, [rax+28h]
0x1800f0054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0059  mov     ebx, eax
0x1800f005b  test    eax, eax
0x1800f005d  jz      short loc_1800F0068
0x1800f005f  cmp     eax, 7
0x1800f0062  jnz     loc_1800F0133
0x1800f0068  mov     rax, [rdi]
0x1800f006b  mov     rdx, r12
0x1800f006e  mov     rcx, rdi
0x1800f0071  mov     rax, [rax+38h]
0x1800f0075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f007a  mov     ebx, eax
0x1800f007c  test    eax, eax
0x1800f007e  jnz     loc_1800F0133
0x1800f0084  mov     rax, [rdi+150h]
0x1800f008b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800f0092  jnz     short loc_1800F00A8
0x1800f0094  mov     rax, [rdi+158h]
0x1800f009b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800f00a2  jz      loc_1800F0133
0x1800f00a8  mov     rdx, r12
0x1800f00ab  mov     rcx, rdi
0x1800f00ae  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800f00b3  mov     ebx, eax
0x1800f00b5  test    eax, eax
0x1800f00b7  jnz     short loc_1800F0133
0x1800f00b9  mov     rcx, r14; pwk
0x1800f00bc  call    cs:__imp_SubmitThreadpoolWork
0x1800f00c2  jmp     loc_1800F0175
0x1800f00c7  mov     rax, [rdi]
0x1800f00ca  mov     r8, r13
0x1800f00cd  mov     rdx, [rsi+8]
0x1800f00d1  mov     rcx, rdi
0x1800f00d4  mov     rax, [rax+10h]
0x1800f00d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f00dd  mov     rax, [rdi]
0x1800f00e0  mov     rdx, r12
0x1800f00e3  mov     rcx, rdi
0x1800f00e6  mov     rax, [rax+30h]
0x1800f00ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f00ef  mov     ebx, eax
0x1800f00f1  test    eax, eax
0x1800f00f3  jz      short loc_1800F00FA
0x1800f00f5  cmp     eax, 7
0x1800f00f8  jnz     short loc_1800F0133
0x1800f00fa  mov     rax, [rdi]
0x1800f00fd  mov     rdx, r12
0x1800f0100  mov     rcx, rdi
0x1800f0103  mov     rax, [rax+28h]
0x1800f0107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f010c  mov     ebx, eax
0x1800f010e  test    eax, eax
0x1800f0110  jz      short loc_1800F0117
0x1800f0112  cmp     eax, 7
0x1800f0115  jnz     short loc_1800F0133
0x1800f0117  mov     rax, [rdi]
0x1800f011a  mov     rdx, r12
0x1800f011d  mov     rcx, rdi
0x1800f0120  mov     rax, [rax+38h]
0x1800f0124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0129  jmp     loc_1800EFFF6
0x1800f012e  mov     ebx, 4
0x1800f0133  mov     rax, [rdi]
0x1800f0136  mov     edx, 1
0x1800f013b  mov     rcx, rdi
0x1800f013e  mov     rax, [rax]
0x1800f0141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0146  test    r15, r15
0x1800f0149  jz      short loc_1800F0158
0x1800f014b  mov     edx, 10h
0x1800f0150  mov     rcx, r15; Block
0x1800f0153  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f0158  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f015c  test    rcx, rcx
0x1800f015f  jz      short loc_1800F0167
0x1800f0161  call    cs:__imp_CloseHandle
0x1800f0167  test    r14, r14
0x1800f016a  jz      short loc_1800F0175
0x1800f016c  mov     rcx, r14; pwk
0x1800f016f  call    cs:__imp_CloseThreadpoolWork
0x1800f0175  mov     eax, ebx
0x1800f0177  mov     rcx, [rbp+var_8]
0x1800f017b  xor     rcx, rsp; StackCookie
0x1800f017e  call    __security_check_cookie
0x1800f0183  mov     rbx, [rsp+80h+arg_18]
0x1800f018b  add     rsp, 80h
0x1800f0192  pop     r15
0x1800f0194  pop     r14
0x1800f0196  pop     r13
0x1800f0198  pop     r12
0x1800f019a  pop     rdi
0x1800f019b  pop     rsi
0x1800f019c  pop     rbp
0x1800f019d  retn
```
