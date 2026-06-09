# CSpWmiMethod<_SPACES_StorageEnclosure_GetFirmwareInformation>::RunMethod<CSpStorageEnclosure::GetFirmwareInformation,8>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800d8e68`
- end: `0x1800d91e5`
- name: `??$RunMethod@VGetFirmwareInformation@CSpStorageEnclosure@@$07@?$CSpWmiMethod@U_SPACES_StorageEnclosure_GetFirmwareInformation@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

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
- `0x1800d8e68`
- `0x1800da380`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9046`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d901b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d901b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d9036`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d9036`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d8ffb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d8ffb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d90f0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d90f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d91af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d91af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d919b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d919b`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageEnclosure_GetFirmwareInformation>::RunMethod<CSpStorageEnclosure::GetFirmwareInformation,8>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 FirmwareInformation; // rax
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
  CSpStorageEnclosure::GetFirmwareInformation *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageEnclosure::GetFirmwareInformation *)operator new(0x168u);
  FirmwareInformation = CSpStorageEnclosure::GetFirmwareInformation::GetFirmwareInformation(v25);
  v8 = FirmwareInformation;
  if ( FirmwareInformation )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)FirmwareInformation + 8LL))(FirmwareInformation, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageEnclosure::GetFirmwareInformation *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_1803356D8,
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
0x1800d8e68  mov     [rsp-38h+arg_18], rbx
0x1800d8e6d  push    rbp
0x1800d8e6e  push    rsi
0x1800d8e6f  push    rdi
0x1800d8e70  push    r12
0x1800d8e72  push    r13
0x1800d8e74  push    r14
0x1800d8e76  push    r15
0x1800d8e78  mov     rbp, rsp
0x1800d8e7b  sub     rsp, 80h
0x1800d8e82  mov     rax, cs:__security_cookie
0x1800d8e89  xor     rax, rsp
0x1800d8e8c  mov     [rbp+var_8], rax
0x1800d8e90  xor     eax, eax
0x1800d8e92  mov     rsi, rcx
0x1800d8e95  xorps   xmm0, xmm0
0x1800d8e98  mov     [rbp+var_10], eax
0x1800d8e9b  mov     ecx, 168h; Size
0x1800d8ea0  mov     [rbp+var_40], eax
0x1800d8ea3  movups  [rbp+var_20], xmm0
0x1800d8ea7  mov     [rbp+TokenHandle], rax
0x1800d8eab  mov     r12, r8
0x1800d8eae  mov     r13, rdx
0x1800d8eb1  xor     r14d, r14d
0x1800d8eb4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d8eb9  mov     rcx, rax; this
0x1800d8ebc  mov     [rbp+var_28], rax
0x1800d8ec0  call    ??0GetFirmwareInformation@CSpStorageEnclosure@@QEAA@XZ; CSpStorageEnclosure::GetFirmwareInformation::GetFirmwareInformation(void)
0x1800d8ec5  mov     rdi, rax
0x1800d8ec8  test    rax, rax
0x1800d8ecb  jnz     short loc_1800D8ED5
0x1800d8ecd  lea     ebx, [rax+1Bh]
0x1800d8ed0  jmp     loc_1800D9192
0x1800d8ed5  mov     rax, [rax]
0x1800d8ed8  mov     rdx, rsi
0x1800d8edb  mov     rcx, rdi
0x1800d8ede  xor     r15d, r15d
0x1800d8ee1  mov     rax, [rax+8]
0x1800d8ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8eea  lea     rcx, [rbp+var_40]
0x1800d8eee  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800d8ef3  mov     [rdi+1Ch], eax
0x1800d8ef6  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800d8efa  mov     ecx, [rsi+14h]; unsigned int
0x1800d8efd  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800d8f02  mov     eax, cs:dword_18039EB68
0x1800d8f08  cmp     eax, 5
0x1800d8f0b  jbe     short loc_1800D8F7B
0x1800d8f0d  mov     rdx, 400000000000h
0x1800d8f17  lea     rcx, dword_18039EB68
0x1800d8f1e  call    _tlgKeywordOn
0x1800d8f23  test    al, al
0x1800d8f25  jz      short loc_1800D8F7B
0x1800d8f27  mov     eax, [rbp+var_40]
0x1800d8f2a  lea     rdx, unk_1803356D8
0x1800d8f31  xor     ecx, ecx
0x1800d8f33  cmp     [rdi+1Ch], eax
0x1800d8f36  movzx   eax, word ptr [rbp+var_10]
0x1800d8f3a  mov     word ptr [rbp+var_40], ax
0x1800d8f3e  setnz   cl
0x1800d8f41  mov     eax, [rsi+14h]
0x1800d8f44  mov     [rbp+var_38], eax
0x1800d8f47  lea     rax, [rbp+var_20]
0x1800d8f4b  mov     [rbp+var_28], rax
0x1800d8f4f  lea     rax, [rbp+var_3C]
0x1800d8f53  mov     [rsp+80h+var_48], rax
0x1800d8f58  lea     rax, [rbp+var_40]
0x1800d8f5c  mov     [rsp+80h+var_50], rax
0x1800d8f61  lea     rax, [rbp+var_38]
0x1800d8f65  mov     [rsp+80h+var_58], rax
0x1800d8f6a  lea     rax, [rbp+var_28]
0x1800d8f6e  mov     [rsp+80h+var_60], rax
0x1800d8f73  mov     [rbp+var_3C], ecx
0x1800d8f76  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800d8f7b  mov     rcx, [rsi]
0x1800d8f7e  test    rcx, rcx
0x1800d8f81  jz      loc_1800D9168
0x1800d8f87  mov     rax, [rcx]
0x1800d8f8a  test    rax, rax
0x1800d8f8d  jz      loc_1800D9168
0x1800d8f93  mov     rax, [rax+18h]
0x1800d8f97  lea     r8, [rdi+20h]
0x1800d8f9b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800d8fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8fa7  mov     ebx, eax
0x1800d8fa9  test    eax, eax
0x1800d8fab  jnz     loc_1800D916D
0x1800d8fb1  cmp     [rsi+10h], r14d
0x1800d8fb5  jz      loc_1800D9101
0x1800d8fbb  lea     rbx, [rdi+148h]
0x1800d8fc2  mov     rcx, rbx
0x1800d8fc5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800d8fca  mov     rcx, rbx; struct CSpJobMgr **
0x1800d8fcd  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800d8fd2  test    eax, eax
0x1800d8fd4  jnz     short loc_1800D8FDE
0x1800d8fd6  lea     ebx, [rax+1Ch]
0x1800d8fd9  jmp     loc_1800D916D
0x1800d8fde  mov     ecx, 10h; Size
0x1800d8fe3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d8fe8  xor     r8d, r8d; pcbe
0x1800d8feb  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800d8ff2  mov     rdx, rax; pv
0x1800d8ff5  mov     r15, rax
0x1800d8ff8  mov     [rax], rdi
0x1800d8ffb  call    cs:__imp_CreateThreadpoolWork
0x1800d9002  nop     dword ptr [rax+rax+00h]
0x1800d9007  mov     r14, rax
0x1800d900a  test    rax, rax
0x1800d900d  jnz     short loc_1800D901B
0x1800d900f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800d9014  mov     ebx, eax
0x1800d9016  jmp     loc_1800D916D
0x1800d901b  call    cs:__imp_GetCurrentThread
0x1800d9022  nop     dword ptr [rax+rax+00h]
0x1800d9027  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d902b  xor     r8d, r8d; OpenAsSelf
0x1800d902e  mov     rcx, rax; ThreadHandle
0x1800d9031  mov     edx, 2000Ch; DesiredAccess
0x1800d9036  call    cs:__imp_OpenThreadToken
0x1800d903d  nop     dword ptr [rax+rax+00h]
0x1800d9042  test    eax, eax
0x1800d9044  jnz     short loc_1800D9059
0x1800d9046  call    cs:__imp_GetLastError
0x1800d904d  nop     dword ptr [rax+rax+00h]
0x1800d9052  cmp     eax, 3F0h
0x1800d9057  jnz     short loc_1800D900F
0x1800d9059  mov     rax, [rbp+TokenHandle]
0x1800d905d  mov     r8, r13
0x1800d9060  mov     [r15+8], rax
0x1800d9064  mov     rcx, rdi
0x1800d9067  mov     rax, [rdi]
0x1800d906a  mov     rdx, [rsi+8]
0x1800d906e  mov     rax, [rax+18h]
0x1800d9072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9077  mov     rax, [rdi]
0x1800d907a  mov     rdx, r12
0x1800d907d  mov     rcx, rdi
0x1800d9080  mov     rax, [rax+28h]
0x1800d9084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9089  mov     ebx, eax
0x1800d908b  test    eax, eax
0x1800d908d  jz      short loc_1800D9098
0x1800d908f  cmp     eax, 7
0x1800d9092  jnz     loc_1800D916D
0x1800d9098  mov     rax, [rdi]
0x1800d909b  mov     rdx, r12
0x1800d909e  mov     rcx, rdi
0x1800d90a1  mov     rax, [rax+38h]
0x1800d90a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d90aa  mov     ebx, eax
0x1800d90ac  test    eax, eax
0x1800d90ae  jnz     loc_1800D916D
0x1800d90b4  mov     rax, [rdi+150h]
0x1800d90bb  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800d90c2  jnz     short loc_1800D90D8
0x1800d90c4  mov     rax, [rdi+158h]
0x1800d90cb  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800d90d2  jz      loc_1800D916D
0x1800d90d8  mov     rdx, r12
0x1800d90db  mov     rcx, rdi
0x1800d90de  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800d90e3  mov     ebx, eax
0x1800d90e5  test    eax, eax
0x1800d90e7  jnz     loc_1800D916D
0x1800d90ed  mov     rcx, r14; pwk
0x1800d90f0  call    cs:__imp_SubmitThreadpoolWork
0x1800d90f7  nop     dword ptr [rax+rax+00h]
0x1800d90fc  jmp     loc_1800D91BB
0x1800d9101  mov     rax, [rdi]
0x1800d9104  mov     r8, r13
0x1800d9107  mov     rdx, [rsi+8]
0x1800d910b  mov     rcx, rdi
0x1800d910e  mov     rax, [rax+10h]
0x1800d9112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9117  mov     rax, [rdi]
0x1800d911a  mov     rdx, r12
0x1800d911d  mov     rcx, rdi
0x1800d9120  mov     rax, [rax+30h]
0x1800d9124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9129  mov     ebx, eax
0x1800d912b  test    eax, eax
0x1800d912d  jz      short loc_1800D9134
0x1800d912f  cmp     eax, 7
0x1800d9132  jnz     short loc_1800D916D
0x1800d9134  mov     rax, [rdi]
0x1800d9137  mov     rdx, r12
0x1800d913a  mov     rcx, rdi
0x1800d913d  mov     rax, [rax+28h]
0x1800d9141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9146  mov     ebx, eax
0x1800d9148  test    eax, eax
0x1800d914a  jz      short loc_1800D9151
0x1800d914c  cmp     eax, 7
0x1800d914f  jnz     short loc_1800D916D
0x1800d9151  mov     rax, [rdi]
0x1800d9154  mov     rdx, r12
0x1800d9157  mov     rcx, rdi
0x1800d915a  mov     rax, [rax+38h]
0x1800d915e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9163  jmp     loc_1800D9014
0x1800d9168  mov     ebx, 4
0x1800d916d  mov     rax, [rdi]
0x1800d9170  mov     edx, 1
0x1800d9175  mov     rcx, rdi
0x1800d9178  mov     rax, [rax]
0x1800d917b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9180  test    r15, r15
0x1800d9183  jz      short loc_1800D9192
0x1800d9185  mov     edx, 10h
0x1800d918a  mov     rcx, r15; Block
0x1800d918d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d9192  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d9196  test    rcx, rcx
0x1800d9199  jz      short loc_1800D91A7
0x1800d919b  call    cs:__imp_CloseHandle
0x1800d91a2  nop     dword ptr [rax+rax+00h]
0x1800d91a7  test    r14, r14
0x1800d91aa  jz      short loc_1800D91BB
0x1800d91ac  mov     rcx, r14; pwk
0x1800d91af  call    cs:__imp_CloseThreadpoolWork
0x1800d91b6  nop     dword ptr [rax+rax+00h]
0x1800d91bb  mov     eax, ebx
0x1800d91bd  mov     rcx, [rbp+var_8]
0x1800d91c1  xor     rcx, rsp; StackCookie
0x1800d91c4  call    __security_check_cookie
0x1800d91c9  mov     rbx, [rsp+80h+arg_18]
0x1800d91d1  add     rsp, 80h
0x1800d91d8  pop     r15
0x1800d91da  pop     r14
0x1800d91dc  pop     r13
0x1800d91de  pop     r12
0x1800d91e0  pop     rdi
0x1800d91e1  pop     rsi
0x1800d91e2  pop     rbp
0x1800d91e3  retn
```
