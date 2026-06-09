# CSpWmiMethod<_MI_Instance>::RunMethod<CSpStorageTier::SetAttributes,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ff994`
- end: `0x1800ffce6`
- name: `??$RunMethod@VSetAttributes@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `850`
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
- `0x18006baa8`
- `0x1800ff994`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffb62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffb62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ffb43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ffb43`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ffb58`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ffb58`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ffb29`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ffb29`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ffc03`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800ffc03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ffcb7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800ffcb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffca9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffca9`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpStorageTier::SetAttributes,12>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int128 **v6; // r14
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

  v26 = 0;
  v20 = 0;
  v25 = 0;
  TokenHandle = 0;
  v6 = 0;
  ThreadpoolWork = 0;
  v24 = (__int128 *)operator new(0x160u);
  v8 = v24;
  CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(v24);
  *(_QWORD *)v24 = &CSpStorageTier::SetAttributes::`vftable';
  ((void (__fastcall *)(__int128 *, __int64 *))CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::SetContext)(v8, a1);
  *((_DWORD *)v8 + 7) = _GetSubsystemVersion(&v20);
  WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v25);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v11 = *((_DWORD *)v8 + 7) == v20;
    LOWORD(v20) = v26;
    v22 = *((_DWORD *)a1 + 5);
    v24 = &v25;
    v21 = !v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v21,
      (unsigned int)byte_18033A091,
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
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD *))(*(_QWORD *)v12 + 24LL))(
          v12,
          &MSFT_StorageExtendedStatus_rtti,
          (_QWORD *)v8 + 4);
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
      v6 = (__int128 **)operator new(0x10u);
      *v6 = v8;
      ThreadpoolWork = CreateThreadpoolWork(
                         CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::ResumeMethodWorker,
                         v6,
                         0);
      if ( ThreadpoolWork )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) || GetLastError() == 1008 )
        {
          v6[1] = (__int128 *)TokenHandle;
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
  if ( v6 )
    operator delete(v6);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v13;
}

```

## disassembly

```asm
0x1800ff994  mov     [rsp-38h+arg_18], rbx
0x1800ff999  push    rbp
0x1800ff99a  push    rsi
0x1800ff99b  push    rdi
0x1800ff99c  push    r12
0x1800ff99e  push    r13
0x1800ff9a0  push    r14
0x1800ff9a2  push    r15
0x1800ff9a4  mov     rbp, rsp
0x1800ff9a7  sub     rsp, 80h
0x1800ff9ae  mov     rax, cs:__security_cookie
0x1800ff9b5  xor     rax, rsp
0x1800ff9b8  mov     [rbp+var_8], rax
0x1800ff9bc  xor     eax, eax
0x1800ff9be  mov     r12, rcx
0x1800ff9c1  xorps   xmm0, xmm0
0x1800ff9c4  mov     [rbp+var_10], eax
0x1800ff9c7  mov     ecx, 160h; Size
0x1800ff9cc  mov     [rbp+var_40], eax
0x1800ff9cf  movups  [rbp+var_20], xmm0
0x1800ff9d3  mov     [rbp+TokenHandle], rax
0x1800ff9d7  mov     r15, r8
0x1800ff9da  mov     r13, rdx
0x1800ff9dd  xor     r14d, r14d
0x1800ff9e0  xor     esi, esi
0x1800ff9e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ff9e7  mov     rcx, rax
0x1800ff9ea  mov     [rbp+var_28], rax
0x1800ff9ee  mov     rdi, rax
0x1800ff9f1  call    ??0?$CSpWmiMethod@U_MI_Instance@@@@QEAA@XZ; CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(void)
0x1800ff9f6  lea     rax, ??_7SetAttributes@CSpStorageTier@@6B@; const CSpStorageTier::SetAttributes::`vftable'
0x1800ff9fd  mov     rdx, r12
0x1800ffa00  mov     [rdi], rax
0x1800ffa03  mov     rcx, rdi
0x1800ffa06  mov     rax, cs:off_180203788
0x1800ffa0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffa12  lea     rcx, [rbp+var_40]
0x1800ffa16  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ffa1b  mov     [rdi+1Ch], eax
0x1800ffa1e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ffa22  mov     ecx, [r12+14h]; unsigned int
0x1800ffa27  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ffa2c  mov     eax, cs:dword_180397B68
0x1800ffa32  cmp     eax, 5
0x1800ffa35  jbe     short loc_1800FFAA7
0x1800ffa37  mov     rdx, 400000000000h
0x1800ffa41  lea     rcx, dword_180397B68
0x1800ffa48  call    _tlgKeywordOn
0x1800ffa4d  test    al, al
0x1800ffa4f  jz      short loc_1800FFAA7
0x1800ffa51  mov     eax, [rbp+var_40]
0x1800ffa54  lea     rdx, byte_18033A091
0x1800ffa5b  xor     ecx, ecx
0x1800ffa5d  cmp     [rdi+1Ch], eax
0x1800ffa60  movzx   eax, word ptr [rbp+var_10]
0x1800ffa64  mov     word ptr [rbp+var_40], ax
0x1800ffa68  setnz   cl
0x1800ffa6b  mov     eax, [r12+14h]
0x1800ffa70  mov     [rbp+var_38], eax
0x1800ffa73  lea     rax, [rbp+var_20]
0x1800ffa77  mov     [rbp+var_28], rax
0x1800ffa7b  lea     rax, [rbp+var_3C]
0x1800ffa7f  mov     [rsp+80h+var_48], rax
0x1800ffa84  lea     rax, [rbp+var_40]
0x1800ffa88  mov     [rsp+80h+var_50], rax
0x1800ffa8d  lea     rax, [rbp+var_38]
0x1800ffa91  mov     [rsp+80h+var_58], rax
0x1800ffa96  lea     rax, [rbp+var_28]
0x1800ffa9a  mov     [rsp+80h+var_60], rax
0x1800ffa9f  mov     [rbp+var_3C], ecx
0x1800ffaa2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ffaa7  mov     rcx, [r12]
0x1800ffaab  test    rcx, rcx
0x1800ffaae  jz      loc_1800FFC76
0x1800ffab4  mov     rax, [rcx]
0x1800ffab7  test    rax, rax
0x1800ffaba  jz      loc_1800FFC76
0x1800ffac0  mov     rax, [rax+18h]
0x1800ffac4  lea     r8, [rdi+20h]
0x1800ffac8  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ffacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffad4  mov     ebx, eax
0x1800ffad6  test    eax, eax
0x1800ffad8  jnz     loc_1800FFC7B
0x1800ffade  cmp     [r12+10h], esi
0x1800ffae3  jz      loc_1800FFC0E
0x1800ffae9  lea     rbx, [rdi+148h]
0x1800ffaf0  mov     rcx, rbx
0x1800ffaf3  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ffaf8  mov     rcx, rbx; struct CSpJobMgr **
0x1800ffafb  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ffb00  test    eax, eax
0x1800ffb02  jnz     short loc_1800FFB0C
0x1800ffb04  lea     ebx, [rax+1Ch]
0x1800ffb07  jmp     loc_1800FFC7B
0x1800ffb0c  mov     ecx, 10h; Size
0x1800ffb11  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ffb16  xor     r8d, r8d; pcbe
0x1800ffb19  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ffb20  mov     rdx, rax; pv
0x1800ffb23  mov     r14, rax
0x1800ffb26  mov     [rax], rdi
0x1800ffb29  call    cs:__imp_CreateThreadpoolWork
0x1800ffb2f  mov     rsi, rax
0x1800ffb32  test    rax, rax
0x1800ffb35  jnz     short loc_1800FFB43
0x1800ffb37  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800ffb3c  mov     ebx, eax
0x1800ffb3e  jmp     loc_1800FFC7B
0x1800ffb43  call    cs:__imp_GetCurrentThread
0x1800ffb49  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ffb4d  xor     r8d, r8d; OpenAsSelf
0x1800ffb50  mov     rcx, rax; ThreadHandle
0x1800ffb53  mov     edx, 2000Ch; DesiredAccess
0x1800ffb58  call    cs:__imp_OpenThreadToken
0x1800ffb5e  test    eax, eax
0x1800ffb60  jnz     short loc_1800FFB6F
0x1800ffb62  call    cs:__imp_GetLastError
0x1800ffb68  cmp     eax, 3F0h
0x1800ffb6d  jnz     short loc_1800FFB37
0x1800ffb6f  mov     rax, [rbp+TokenHandle]
0x1800ffb73  mov     r8, r13
0x1800ffb76  mov     [r14+8], rax
0x1800ffb7a  mov     rcx, rdi
0x1800ffb7d  mov     rax, [rdi]
0x1800ffb80  mov     rdx, [r12+8]
0x1800ffb85  mov     rax, [rax+18h]
0x1800ffb89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffb8e  mov     rax, [rdi]
0x1800ffb91  mov     rdx, r15
0x1800ffb94  mov     rcx, rdi
0x1800ffb97  mov     rax, [rax+28h]
0x1800ffb9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffba0  mov     ebx, eax
0x1800ffba2  test    eax, eax
0x1800ffba4  jz      short loc_1800FFBAF
0x1800ffba6  cmp     eax, 7
0x1800ffba9  jnz     loc_1800FFC7B
0x1800ffbaf  mov     rax, [rdi]
0x1800ffbb2  mov     rdx, r15
0x1800ffbb5  mov     rcx, rdi
0x1800ffbb8  mov     rax, [rax+38h]
0x1800ffbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffbc1  mov     ebx, eax
0x1800ffbc3  test    eax, eax
0x1800ffbc5  jnz     loc_1800FFC7B
0x1800ffbcb  mov     rax, [rdi+150h]
0x1800ffbd2  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800ffbd9  jnz     short loc_1800FFBEF
0x1800ffbdb  mov     rax, [rdi+158h]
0x1800ffbe2  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800ffbe9  jz      loc_1800FFC7B
0x1800ffbef  mov     rdx, r15
0x1800ffbf2  mov     rcx, rdi
0x1800ffbf5  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800ffbfa  mov     ebx, eax
0x1800ffbfc  test    eax, eax
0x1800ffbfe  jnz     short loc_1800FFC7B
0x1800ffc00  mov     rcx, rsi; pwk
0x1800ffc03  call    cs:__imp_SubmitThreadpoolWork
0x1800ffc09  jmp     loc_1800FFCBD
0x1800ffc0e  mov     rax, [rdi]
0x1800ffc11  mov     r8, r13
0x1800ffc14  mov     rdx, [r12+8]
0x1800ffc19  mov     rcx, rdi
0x1800ffc1c  mov     rax, [rax+10h]
0x1800ffc20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffc25  mov     rax, [rdi]
0x1800ffc28  mov     rdx, r15
0x1800ffc2b  mov     rcx, rdi
0x1800ffc2e  mov     rax, [rax+30h]
0x1800ffc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffc37  mov     ebx, eax
0x1800ffc39  test    eax, eax
0x1800ffc3b  jz      short loc_1800FFC42
0x1800ffc3d  cmp     eax, 7
0x1800ffc40  jnz     short loc_1800FFC7B
0x1800ffc42  mov     rax, [rdi]
0x1800ffc45  mov     rdx, r15
0x1800ffc48  mov     rcx, rdi
0x1800ffc4b  mov     rax, [rax+28h]
0x1800ffc4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffc54  mov     ebx, eax
0x1800ffc56  test    eax, eax
0x1800ffc58  jz      short loc_1800FFC5F
0x1800ffc5a  cmp     eax, 7
0x1800ffc5d  jnz     short loc_1800FFC7B
0x1800ffc5f  mov     rax, [rdi]
0x1800ffc62  mov     rdx, r15
0x1800ffc65  mov     rcx, rdi
0x1800ffc68  mov     rax, [rax+38h]
0x1800ffc6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffc71  jmp     loc_1800FFB3C
0x1800ffc76  mov     ebx, 4
0x1800ffc7b  mov     rax, [rdi]
0x1800ffc7e  mov     edx, 1
0x1800ffc83  mov     rcx, rdi
0x1800ffc86  mov     rax, [rax]
0x1800ffc89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffc8e  test    r14, r14
0x1800ffc91  jz      short loc_1800FFCA0
0x1800ffc93  mov     edx, 10h
0x1800ffc98  mov     rcx, r14; Block
0x1800ffc9b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ffca0  mov     rcx, [rbp+TokenHandle]; hObject
0x1800ffca4  test    rcx, rcx
0x1800ffca7  jz      short loc_1800FFCAF
0x1800ffca9  call    cs:__imp_CloseHandle
0x1800ffcaf  test    rsi, rsi
0x1800ffcb2  jz      short loc_1800FFCBD
0x1800ffcb4  mov     rcx, rsi; pwk
0x1800ffcb7  call    cs:__imp_CloseThreadpoolWork
0x1800ffcbd  mov     eax, ebx
0x1800ffcbf  mov     rcx, [rbp+var_8]
0x1800ffcc3  xor     rcx, rsp; StackCookie
0x1800ffcc6  call    __security_check_cookie
0x1800ffccb  mov     rbx, [rsp+80h+arg_18]
0x1800ffcd3  add     rsp, 80h
0x1800ffcda  pop     r15
0x1800ffcdc  pop     r14
0x1800ffcde  pop     r13
0x1800ffce0  pop     r12
0x1800ffce2  pop     rdi
0x1800ffce3  pop     rsi
0x1800ffce4  pop     rbp
0x1800ffce5  retn
```
