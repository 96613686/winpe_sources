# CSpWmiMethod<_SPACES_StorageSubsystem_GetActions>::RunMethod<CSpSubsystem::GetActions,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006c96c`
- end: `0x18006cce9`
- name: `??$RunMethod@VGetActions@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_GetActions@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800743e0`

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
- `0x18006c96c`
- `0x18006e2a8`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cb4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cb4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006cb1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006cb1f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006cb3a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006cb3a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006caff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006caff`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006cbf4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006cbf4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006ccb3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006ccb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cc9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cc9f`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_GetActions>::RunMethod<CSpSubsystem::GetActions,13>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 Actions; // rax
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
  CSpSubsystem::GetActions *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::GetActions *)operator new(0x168u);
  Actions = CSpSubsystem::GetActions::GetActions(v25);
  v8 = Actions;
  if ( Actions )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)Actions + 8LL))(Actions, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpSubsystem::GetActions *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_18031621C,
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
0x18006c96c  mov     [rsp-38h+arg_18], rbx
0x18006c971  push    rbp
0x18006c972  push    rsi
0x18006c973  push    rdi
0x18006c974  push    r12
0x18006c976  push    r13
0x18006c978  push    r14
0x18006c97a  push    r15
0x18006c97c  mov     rbp, rsp
0x18006c97f  sub     rsp, 80h
0x18006c986  mov     rax, cs:__security_cookie
0x18006c98d  xor     rax, rsp
0x18006c990  mov     [rbp+var_8], rax
0x18006c994  xor     eax, eax
0x18006c996  mov     rsi, rcx
0x18006c999  xorps   xmm0, xmm0
0x18006c99c  mov     [rbp+var_10], eax
0x18006c99f  mov     ecx, 168h; Size
0x18006c9a4  mov     [rbp+var_40], eax
0x18006c9a7  movups  [rbp+var_20], xmm0
0x18006c9ab  mov     [rbp+TokenHandle], rax
0x18006c9af  mov     r12, r8
0x18006c9b2  mov     r13, rdx
0x18006c9b5  xor     r14d, r14d
0x18006c9b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006c9bd  mov     rcx, rax; this
0x18006c9c0  mov     [rbp+var_28], rax
0x18006c9c4  call    ??0GetActions@CSpSubsystem@@QEAA@XZ; CSpSubsystem::GetActions::GetActions(void)
0x18006c9c9  mov     rdi, rax
0x18006c9cc  test    rax, rax
0x18006c9cf  jnz     short loc_18006C9D9
0x18006c9d1  lea     ebx, [rax+1Bh]
0x18006c9d4  jmp     loc_18006CC96
0x18006c9d9  mov     rax, [rax]
0x18006c9dc  mov     rdx, rsi
0x18006c9df  mov     rcx, rdi
0x18006c9e2  xor     r15d, r15d
0x18006c9e5  mov     rax, [rax+8]
0x18006c9e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c9ee  lea     rcx, [rbp+var_40]
0x18006c9f2  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006c9f7  mov     [rdi+1Ch], eax
0x18006c9fa  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006c9fe  mov     ecx, [rsi+14h]; unsigned int
0x18006ca01  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006ca06  mov     eax, cs:dword_18039EB68
0x18006ca0c  cmp     eax, 5
0x18006ca0f  jbe     short loc_18006CA7F
0x18006ca11  mov     rdx, 400000000000h
0x18006ca1b  lea     rcx, dword_18039EB68
0x18006ca22  call    _tlgKeywordOn
0x18006ca27  test    al, al
0x18006ca29  jz      short loc_18006CA7F
0x18006ca2b  mov     eax, [rbp+var_40]
0x18006ca2e  lea     rdx, dword_18031621C
0x18006ca35  xor     ecx, ecx
0x18006ca37  cmp     [rdi+1Ch], eax
0x18006ca3a  movzx   eax, word ptr [rbp+var_10]
0x18006ca3e  mov     word ptr [rbp+var_40], ax
0x18006ca42  setnz   cl
0x18006ca45  mov     eax, [rsi+14h]
0x18006ca48  mov     [rbp+var_38], eax
0x18006ca4b  lea     rax, [rbp+var_20]
0x18006ca4f  mov     [rbp+var_28], rax
0x18006ca53  lea     rax, [rbp+var_3C]
0x18006ca57  mov     [rsp+80h+var_48], rax
0x18006ca5c  lea     rax, [rbp+var_40]
0x18006ca60  mov     [rsp+80h+var_50], rax
0x18006ca65  lea     rax, [rbp+var_38]
0x18006ca69  mov     [rsp+80h+var_58], rax
0x18006ca6e  lea     rax, [rbp+var_28]
0x18006ca72  mov     [rsp+80h+var_60], rax
0x18006ca77  mov     [rbp+var_3C], ecx
0x18006ca7a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006ca7f  mov     rcx, [rsi]
0x18006ca82  test    rcx, rcx
0x18006ca85  jz      loc_18006CC6C
0x18006ca8b  mov     rax, [rcx]
0x18006ca8e  test    rax, rax
0x18006ca91  jz      loc_18006CC6C
0x18006ca97  mov     rax, [rax+18h]
0x18006ca9b  lea     r8, [rdi+20h]
0x18006ca9f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006caa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006caab  mov     ebx, eax
0x18006caad  test    eax, eax
0x18006caaf  jnz     loc_18006CC71
0x18006cab5  cmp     [rsi+10h], r14d
0x18006cab9  jz      loc_18006CC05
0x18006cabf  lea     rbx, [rdi+148h]
0x18006cac6  mov     rcx, rbx
0x18006cac9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006cace  mov     rcx, rbx; struct CSpJobMgr **
0x18006cad1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006cad6  test    eax, eax
0x18006cad8  jnz     short loc_18006CAE2
0x18006cada  lea     ebx, [rax+1Ch]
0x18006cadd  jmp     loc_18006CC71
0x18006cae2  mov     ecx, 10h; Size
0x18006cae7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006caec  xor     r8d, r8d; pcbe
0x18006caef  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006caf6  mov     rdx, rax; pv
0x18006caf9  mov     r15, rax
0x18006cafc  mov     [rax], rdi
0x18006caff  call    cs:__imp_CreateThreadpoolWork
0x18006cb06  nop     dword ptr [rax+rax+00h]
0x18006cb0b  mov     r14, rax
0x18006cb0e  test    rax, rax
0x18006cb11  jnz     short loc_18006CB1F
0x18006cb13  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006cb18  mov     ebx, eax
0x18006cb1a  jmp     loc_18006CC71
0x18006cb1f  call    cs:__imp_GetCurrentThread
0x18006cb26  nop     dword ptr [rax+rax+00h]
0x18006cb2b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006cb2f  xor     r8d, r8d; OpenAsSelf
0x18006cb32  mov     rcx, rax; ThreadHandle
0x18006cb35  mov     edx, 2000Ch; DesiredAccess
0x18006cb3a  call    cs:__imp_OpenThreadToken
0x18006cb41  nop     dword ptr [rax+rax+00h]
0x18006cb46  test    eax, eax
0x18006cb48  jnz     short loc_18006CB5D
0x18006cb4a  call    cs:__imp_GetLastError
0x18006cb51  nop     dword ptr [rax+rax+00h]
0x18006cb56  cmp     eax, 3F0h
0x18006cb5b  jnz     short loc_18006CB13
0x18006cb5d  mov     rax, [rbp+TokenHandle]
0x18006cb61  mov     r8, r13
0x18006cb64  mov     [r15+8], rax
0x18006cb68  mov     rcx, rdi
0x18006cb6b  mov     rax, [rdi]
0x18006cb6e  mov     rdx, [rsi+8]
0x18006cb72  mov     rax, [rax+18h]
0x18006cb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cb7b  mov     rax, [rdi]
0x18006cb7e  mov     rdx, r12
0x18006cb81  mov     rcx, rdi
0x18006cb84  mov     rax, [rax+28h]
0x18006cb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cb8d  mov     ebx, eax
0x18006cb8f  test    eax, eax
0x18006cb91  jz      short loc_18006CB9C
0x18006cb93  cmp     eax, 7
0x18006cb96  jnz     loc_18006CC71
0x18006cb9c  mov     rax, [rdi]
0x18006cb9f  mov     rdx, r12
0x18006cba2  mov     rcx, rdi
0x18006cba5  mov     rax, [rax+38h]
0x18006cba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cbae  mov     ebx, eax
0x18006cbb0  test    eax, eax
0x18006cbb2  jnz     loc_18006CC71
0x18006cbb8  mov     rax, [rdi+150h]
0x18006cbbf  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006cbc6  jnz     short loc_18006CBDC
0x18006cbc8  mov     rax, [rdi+158h]
0x18006cbcf  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006cbd6  jz      loc_18006CC71
0x18006cbdc  mov     rdx, r12
0x18006cbdf  mov     rcx, rdi
0x18006cbe2  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006cbe7  mov     ebx, eax
0x18006cbe9  test    eax, eax
0x18006cbeb  jnz     loc_18006CC71
0x18006cbf1  mov     rcx, r14; pwk
0x18006cbf4  call    cs:__imp_SubmitThreadpoolWork
0x18006cbfb  nop     dword ptr [rax+rax+00h]
0x18006cc00  jmp     loc_18006CCBF
0x18006cc05  mov     rax, [rdi]
0x18006cc08  mov     r8, r13
0x18006cc0b  mov     rdx, [rsi+8]
0x18006cc0f  mov     rcx, rdi
0x18006cc12  mov     rax, [rax+10h]
0x18006cc16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cc1b  mov     rax, [rdi]
0x18006cc1e  mov     rdx, r12
0x18006cc21  mov     rcx, rdi
0x18006cc24  mov     rax, [rax+30h]
0x18006cc28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cc2d  mov     ebx, eax
0x18006cc2f  test    eax, eax
0x18006cc31  jz      short loc_18006CC38
0x18006cc33  cmp     eax, 7
0x18006cc36  jnz     short loc_18006CC71
0x18006cc38  mov     rax, [rdi]
0x18006cc3b  mov     rdx, r12
0x18006cc3e  mov     rcx, rdi
0x18006cc41  mov     rax, [rax+28h]
0x18006cc45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cc4a  mov     ebx, eax
0x18006cc4c  test    eax, eax
0x18006cc4e  jz      short loc_18006CC55
0x18006cc50  cmp     eax, 7
0x18006cc53  jnz     short loc_18006CC71
0x18006cc55  mov     rax, [rdi]
0x18006cc58  mov     rdx, r12
0x18006cc5b  mov     rcx, rdi
0x18006cc5e  mov     rax, [rax+38h]
0x18006cc62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cc67  jmp     loc_18006CB18
0x18006cc6c  mov     ebx, 4
0x18006cc71  mov     rax, [rdi]
0x18006cc74  mov     edx, 1
0x18006cc79  mov     rcx, rdi
0x18006cc7c  mov     rax, [rax]
0x18006cc7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cc84  test    r15, r15
0x18006cc87  jz      short loc_18006CC96
0x18006cc89  mov     edx, 10h
0x18006cc8e  mov     rcx, r15; Block
0x18006cc91  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006cc96  mov     rcx, [rbp+TokenHandle]; hObject
0x18006cc9a  test    rcx, rcx
0x18006cc9d  jz      short loc_18006CCAB
0x18006cc9f  call    cs:__imp_CloseHandle
0x18006cca6  nop     dword ptr [rax+rax+00h]
0x18006ccab  test    r14, r14
0x18006ccae  jz      short loc_18006CCBF
0x18006ccb0  mov     rcx, r14; pwk
0x18006ccb3  call    cs:__imp_CloseThreadpoolWork
0x18006ccba  nop     dword ptr [rax+rax+00h]
0x18006ccbf  mov     eax, ebx
0x18006ccc1  mov     rcx, [rbp+var_8]
0x18006ccc5  xor     rcx, rsp; StackCookie
0x18006ccc8  call    __security_check_cookie
0x18006cccd  mov     rbx, [rsp+80h+arg_18]
0x18006ccd5  add     rsp, 80h
0x18006ccdc  pop     r15
0x18006ccde  pop     r14
0x18006cce0  pop     r13
0x18006cce2  pop     r12
0x18006cce4  pop     rdi
0x18006cce5  pop     rsi
0x18006cce6  pop     rbp
0x18006cce7  retn
```
