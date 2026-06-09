# CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::GetSupportedSize,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800be824`
- end: `0x1800bebbb`
- name: `??$RunMethod@VGetSupportedSize@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `919`
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
- `0x18006de84`
- `0x1800be824`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bea1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bea1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800be9ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800be9ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bea0a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bea0a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800be9cf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800be9cf`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800beac5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800beac5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800beb85`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800beb85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800beb71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800beb71`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpStoragePool::GetSupportedSize,11>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int128 **v4; // r14
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int128 *v8; // rdi
  int v9; // r8d
  int v10; // r9d
  bool v11; // zf
  __int64 v12; // rcx
  unsigned int v13; // ebx
  enum _MI_Result v14; // eax
  HANDLE CurrentThread; // rax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  int v20; // [rsp+40h] [rbp-40h] BYREF
  BOOL v21; // [rsp+44h] [rbp-3Ch] BYREF
  int v22; // [rsp+48h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-30h] BYREF
  __int128 *v24; // [rsp+58h] [rbp-28h] BYREF
  __int128 v25; // [rsp+60h] [rbp-20h] BYREF
  int v26; // [rsp+70h] [rbp-10h]

  v20 = 0;
  TokenHandle = 0;
  v26 = 0;
  v4 = 0;
  ThreadpoolWork = 0;
  v25 = 0;
  v24 = (__int128 *)operator new(0x188u);
  v8 = v24;
  CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(v24);
  *((_QWORD *)v24 + 44) = 0;
  *(_QWORD *)v8 = &CSpStoragePool::GetSupportedSize::`vftable';
  *((_BYTE *)v8 + 360) = 0;
  *((_WORD *)v8 + 181) = 0;
  (*(void (__fastcall **)(__int128 *, __int64 *))(*(_QWORD *)v8 + 8LL))(v8, a1);
  *((_DWORD *)v8 + 7) = _GetSubsystemVersion(&v20);
  WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v25);
  if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
  {
    v11 = *((_DWORD *)v8 + 7) == v20;
    LOWORD(v20) = v26;
    v22 = *((_DWORD *)a1 + 5);
    v24 = &v25;
    v21 = !v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v21,
      (unsigned int)&word_180333056,
      v9,
      v10,
      (__int64)&v24,
      (__int64)&v22,
      (__int64)&v20,
      (__int64)&v21);
  }
  v12 = *a1;
  if ( !*a1 || !*(_QWORD *)v12 )
  {
    v13 = 4;
    goto LABEL_28;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 *))(*(_QWORD *)v12 + 24LL))(
          v12,
          &MSFT_StorageExtendedStatus_rtti,
          v8 + 2);
  if ( !v13 )
  {
    if ( *((_DWORD *)a1 + 4) )
    {
      CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release((char *)v8 + 328);
      if ( !(unsigned int)CSpJobMgr::GetInstance((struct CSpJobMgr **)v8 + 41) )
      {
        v13 = 28;
        goto LABEL_28;
      }
      v4 = (__int128 **)operator new(0x10u);
      *v4 = v8;
      ThreadpoolWork = CreateThreadpoolWork(
                         CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::ResumeMethodWorker,
                         v4,
                         0);
      if ( ThreadpoolWork )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) || GetLastError() == 1008 )
        {
          v4[1] = (__int128 *)TokenHandle;
          (*(void (__fastcall **)(__int128 *, __int64, __int64))(*(_QWORD *)v8 + 24LL))(v8, a1[1], a2);
          v16 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
          v13 = v16;
          if ( !v16 || v16 == 7 )
          {
            v13 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
            if ( !v13
              && (*((_QWORD *)v8 + 42) != *(_QWORD *)&GUID_NULL.Data1
               || *((_QWORD *)v8 + 43) != *(_QWORD *)GUID_NULL.Data4) )
            {
              v13 = CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(v8, a3);
              if ( !v13 )
              {
                SubmitThreadpoolWork(ThreadpoolWork);
                return v13;
              }
            }
          }
          goto LABEL_28;
        }
      }
      v14 = GleToMiResult();
    }
    else
    {
      (*(void (__fastcall **)(__int128 *, __int64, __int64))(*(_QWORD *)v8 + 16LL))(v8, a1[1], a2);
      v17 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 48LL))(v8, a3);
      v13 = v17;
      if ( v17 && v17 != 7 )
        goto LABEL_28;
      v18 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
      v13 = v18;
      if ( v18 )
      {
        if ( v18 != 7 )
          goto LABEL_28;
      }
      v14 = (*(unsigned int (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
    }
    v13 = v14;
  }
LABEL_28:
  (**(void (__fastcall ***)(__int128 *, __int64))v8)(v8, 1);
  if ( v4 )
    operator delete(v4);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v13;
}

```

## disassembly

```asm
0x1800be824  mov     [rsp-38h+arg_18], rbx
0x1800be829  push    rbp
0x1800be82a  push    rsi
0x1800be82b  push    rdi
0x1800be82c  push    r12
0x1800be82e  push    r13
0x1800be830  push    r14
0x1800be832  push    r15
0x1800be834  mov     rbp, rsp
0x1800be837  sub     rsp, 80h
0x1800be83e  mov     rax, cs:__security_cookie
0x1800be845  xor     rax, rsp
0x1800be848  mov     [rbp+var_8], rax
0x1800be84c  xor     ebx, ebx
0x1800be84e  mov     r12, rcx
0x1800be851  xorps   xmm0, xmm0
0x1800be854  mov     [rbp+var_40], ebx
0x1800be857  xor     eax, eax
0x1800be859  mov     [rbp+TokenHandle], rbx
0x1800be85d  mov     ecx, 188h; Size
0x1800be862  mov     [rbp+var_10], eax
0x1800be865  mov     r14d, ebx
0x1800be868  mov     esi, ebx
0x1800be86a  movups  [rbp+var_20], xmm0
0x1800be86e  mov     r15, r8
0x1800be871  mov     r13, rdx
0x1800be874  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800be879  mov     rcx, rax
0x1800be87c  mov     [rbp+var_28], rax
0x1800be880  mov     rdi, rax
0x1800be883  call    ??0?$CSpWmiMethod@U_MI_Instance@@@@QEAA@XZ; CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(void)
0x1800be888  mov     [rdi+160h], rbx
0x1800be88f  lea     rax, ??_7GetSupportedSize@CSpStoragePool@@6B@; const CSpStoragePool::GetSupportedSize::`vftable'
0x1800be896  mov     [rdi], rax
0x1800be899  mov     rdx, r12
0x1800be89c  mov     [rdi+168h], bl
0x1800be8a2  mov     rcx, rdi
0x1800be8a5  mov     [rdi+16Ah], bx
0x1800be8ac  mov     rax, [rdi]
0x1800be8af  mov     rax, [rax+8]
0x1800be8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be8b8  lea     rcx, [rbp+var_40]
0x1800be8bc  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800be8c1  mov     [rdi+1Ch], eax
0x1800be8c4  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800be8c8  mov     ecx, [r12+14h]; unsigned int
0x1800be8cd  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800be8d2  mov     eax, cs:dword_18039EB68
0x1800be8d8  cmp     eax, 5
0x1800be8db  jbe     short loc_1800BE94D
0x1800be8dd  mov     rdx, 400000000000h
0x1800be8e7  lea     rcx, dword_18039EB68
0x1800be8ee  call    _tlgKeywordOn
0x1800be8f3  test    al, al
0x1800be8f5  jz      short loc_1800BE94D
0x1800be8f7  mov     eax, [rbp+var_40]
0x1800be8fa  lea     rdx, word_180333056
0x1800be901  cmp     [rdi+1Ch], eax
0x1800be904  mov     ecx, ebx
0x1800be906  movzx   eax, word ptr [rbp+var_10]
0x1800be90a  mov     word ptr [rbp+var_40], ax
0x1800be90e  setnz   cl
0x1800be911  mov     eax, [r12+14h]
0x1800be916  mov     [rbp+var_38], eax
0x1800be919  lea     rax, [rbp+var_20]
0x1800be91d  mov     [rbp+var_28], rax
0x1800be921  lea     rax, [rbp+var_3C]
0x1800be925  mov     [rsp+80h+var_48], rax
0x1800be92a  lea     rax, [rbp+var_40]
0x1800be92e  mov     [rsp+80h+var_50], rax
0x1800be933  lea     rax, [rbp+var_38]
0x1800be937  mov     [rsp+80h+var_58], rax
0x1800be93c  lea     rax, [rbp+var_28]
0x1800be940  mov     [rsp+80h+var_60], rax
0x1800be945  mov     [rbp+var_3C], ecx
0x1800be948  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800be94d  mov     rcx, [r12]
0x1800be951  test    rcx, rcx
0x1800be954  jz      loc_1800BEB3E
0x1800be95a  mov     rax, [rcx]
0x1800be95d  test    rax, rax
0x1800be960  jz      loc_1800BEB3E
0x1800be966  mov     rax, [rax+18h]
0x1800be96a  lea     r8, [rdi+20h]
0x1800be96e  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800be975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be97a  mov     ebx, eax
0x1800be97c  test    eax, eax
0x1800be97e  jnz     loc_1800BEB43
0x1800be984  cmp     [r12+10h], esi
0x1800be989  jz      loc_1800BEAD6
0x1800be98f  lea     rbx, [rdi+148h]
0x1800be996  mov     rcx, rbx
0x1800be999  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800be99e  mov     rcx, rbx; struct CSpJobMgr **
0x1800be9a1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800be9a6  test    eax, eax
0x1800be9a8  jnz     short loc_1800BE9B2
0x1800be9aa  lea     ebx, [rax+1Ch]
0x1800be9ad  jmp     loc_1800BEB43
0x1800be9b2  mov     ecx, 10h; Size
0x1800be9b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800be9bc  xor     r8d, r8d; pcbe
0x1800be9bf  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800be9c6  mov     rdx, rax; pv
0x1800be9c9  mov     r14, rax
0x1800be9cc  mov     [rax], rdi
0x1800be9cf  call    cs:__imp_CreateThreadpoolWork
0x1800be9d6  nop     dword ptr [rax+rax+00h]
0x1800be9db  mov     rsi, rax
0x1800be9de  test    rax, rax
0x1800be9e1  jnz     short loc_1800BE9EF
0x1800be9e3  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800be9e8  mov     ebx, eax
0x1800be9ea  jmp     loc_1800BEB43
0x1800be9ef  call    cs:__imp_GetCurrentThread
0x1800be9f6  nop     dword ptr [rax+rax+00h]
0x1800be9fb  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800be9ff  xor     r8d, r8d; OpenAsSelf
0x1800bea02  mov     rcx, rax; ThreadHandle
0x1800bea05  mov     edx, 2000Ch; DesiredAccess
0x1800bea0a  call    cs:__imp_OpenThreadToken
0x1800bea11  nop     dword ptr [rax+rax+00h]
0x1800bea16  test    eax, eax
0x1800bea18  jnz     short loc_1800BEA2D
0x1800bea1a  call    cs:__imp_GetLastError
0x1800bea21  nop     dword ptr [rax+rax+00h]
0x1800bea26  cmp     eax, 3F0h
0x1800bea2b  jnz     short loc_1800BE9E3
0x1800bea2d  mov     rax, [rbp+TokenHandle]
0x1800bea31  mov     r8, r13
0x1800bea34  mov     [r14+8], rax
0x1800bea38  mov     rcx, rdi
0x1800bea3b  mov     rax, [rdi]
0x1800bea3e  mov     rdx, [r12+8]
0x1800bea43  mov     rax, [rax+18h]
0x1800bea47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bea4c  mov     rax, [rdi]
0x1800bea4f  mov     rdx, r15
0x1800bea52  mov     rcx, rdi
0x1800bea55  mov     rax, [rax+28h]
0x1800bea59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bea5e  mov     ebx, eax
0x1800bea60  test    eax, eax
0x1800bea62  jz      short loc_1800BEA6D
0x1800bea64  cmp     eax, 7
0x1800bea67  jnz     loc_1800BEB43
0x1800bea6d  mov     rax, [rdi]
0x1800bea70  mov     rdx, r15
0x1800bea73  mov     rcx, rdi
0x1800bea76  mov     rax, [rax+38h]
0x1800bea7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bea7f  mov     ebx, eax
0x1800bea81  test    eax, eax
0x1800bea83  jnz     loc_1800BEB43
0x1800bea89  mov     rax, [rdi+150h]
0x1800bea90  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bea97  jnz     short loc_1800BEAAD
0x1800bea99  mov     rax, [rdi+158h]
0x1800beaa0  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800beaa7  jz      loc_1800BEB43
0x1800beaad  mov     rdx, r15
0x1800beab0  mov     rcx, rdi
0x1800beab3  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800beab8  mov     ebx, eax
0x1800beaba  test    eax, eax
0x1800beabc  jnz     loc_1800BEB43
0x1800beac2  mov     rcx, rsi; pwk
0x1800beac5  call    cs:__imp_SubmitThreadpoolWork
0x1800beacc  nop     dword ptr [rax+rax+00h]
0x1800bead1  jmp     loc_1800BEB91
0x1800bead6  mov     rax, [rdi]
0x1800bead9  mov     r8, r13
0x1800beadc  mov     rdx, [r12+8]
0x1800beae1  mov     rcx, rdi
0x1800beae4  mov     rax, [rax+10h]
0x1800beae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beaed  mov     rax, [rdi]
0x1800beaf0  mov     rdx, r15
0x1800beaf3  mov     rcx, rdi
0x1800beaf6  mov     rax, [rax+30h]
0x1800beafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beaff  mov     ebx, eax
0x1800beb01  test    eax, eax
0x1800beb03  jz      short loc_1800BEB0A
0x1800beb05  cmp     eax, 7
0x1800beb08  jnz     short loc_1800BEB43
0x1800beb0a  mov     rax, [rdi]
0x1800beb0d  mov     rdx, r15
0x1800beb10  mov     rcx, rdi
0x1800beb13  mov     rax, [rax+28h]
0x1800beb17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beb1c  mov     ebx, eax
0x1800beb1e  test    eax, eax
0x1800beb20  jz      short loc_1800BEB27
0x1800beb22  cmp     eax, 7
0x1800beb25  jnz     short loc_1800BEB43
0x1800beb27  mov     rax, [rdi]
0x1800beb2a  mov     rdx, r15
0x1800beb2d  mov     rcx, rdi
0x1800beb30  mov     rax, [rax+38h]
0x1800beb34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beb39  jmp     loc_1800BE9E8
0x1800beb3e  mov     ebx, 4
0x1800beb43  mov     rax, [rdi]
0x1800beb46  mov     edx, 1
0x1800beb4b  mov     rcx, rdi
0x1800beb4e  mov     rax, [rax]
0x1800beb51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beb56  test    r14, r14
0x1800beb59  jz      short loc_1800BEB68
0x1800beb5b  mov     edx, 10h
0x1800beb60  mov     rcx, r14; Block
0x1800beb63  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800beb68  mov     rcx, [rbp+TokenHandle]; hObject
0x1800beb6c  test    rcx, rcx
0x1800beb6f  jz      short loc_1800BEB7D
0x1800beb71  call    cs:__imp_CloseHandle
0x1800beb78  nop     dword ptr [rax+rax+00h]
0x1800beb7d  test    rsi, rsi
0x1800beb80  jz      short loc_1800BEB91
0x1800beb82  mov     rcx, rsi; pwk
0x1800beb85  call    cs:__imp_CloseThreadpoolWork
0x1800beb8c  nop     dword ptr [rax+rax+00h]
0x1800beb91  mov     eax, ebx
0x1800beb93  mov     rcx, [rbp+var_8]
0x1800beb97  xor     rcx, rsp; StackCookie
0x1800beb9a  call    __security_check_cookie
0x1800beb9f  mov     rbx, [rsp+80h+arg_18]
0x1800beba7  add     rsp, 80h
0x1800bebae  pop     r15
0x1800bebb0  pop     r14
0x1800bebb2  pop     r13
0x1800bebb4  pop     r12
0x1800bebb6  pop     rdi
0x1800bebb7  pop     rsi
0x1800bebb8  pop     rbp
0x1800bebb9  retn
```
