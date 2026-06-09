# CSpWmiMethod<_SPACES_StorageSubsystem_StopDiagnosticLog>::RunMethod<CSpSubsystem::StopDiagnosticLog,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006db00`
- end: `0x18006de7d`
- name: `??$RunMethod@VStopDiagnosticLog@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_StopDiagnosticLog@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180057100`
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
- `0x18006db00`
- `0x18006e4b4`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dcde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dcde`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006dcb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006dcb3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006dcce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006dcce`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006dc93`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006dc93`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006dd88`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006dd88`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006de47`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006de47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006de33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006de33`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_StopDiagnosticLog>::RunMethod<CSpSubsystem::StopDiagnosticLog,13>(
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
  CSpSubsystem::StopDiagnosticLog *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::StopDiagnosticLog *)operator new(0x160u);
  v7 = CSpSubsystem::StopDiagnosticLog::StopDiagnosticLog(v25);
  v8 = v7;
  if ( v7 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 8LL))(v7, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpSubsystem::StopDiagnosticLog *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_1803179BB,
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
0x18006db00  mov     [rsp-38h+arg_18], rbx
0x18006db05  push    rbp
0x18006db06  push    rsi
0x18006db07  push    rdi
0x18006db08  push    r12
0x18006db0a  push    r13
0x18006db0c  push    r14
0x18006db0e  push    r15
0x18006db10  mov     rbp, rsp
0x18006db13  sub     rsp, 80h
0x18006db1a  mov     rax, cs:__security_cookie
0x18006db21  xor     rax, rsp
0x18006db24  mov     [rbp+var_8], rax
0x18006db28  xor     eax, eax
0x18006db2a  mov     rsi, rcx
0x18006db2d  xorps   xmm0, xmm0
0x18006db30  mov     [rbp+var_10], eax
0x18006db33  mov     ecx, 160h; Size
0x18006db38  mov     [rbp+var_40], eax
0x18006db3b  movups  [rbp+var_20], xmm0
0x18006db3f  mov     [rbp+TokenHandle], rax
0x18006db43  mov     r12, r8
0x18006db46  mov     r13, rdx
0x18006db49  xor     r14d, r14d
0x18006db4c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006db51  mov     rcx, rax; this
0x18006db54  mov     [rbp+var_28], rax
0x18006db58  call    ??0StopDiagnosticLog@CSpSubsystem@@QEAA@XZ; CSpSubsystem::StopDiagnosticLog::StopDiagnosticLog(void)
0x18006db5d  mov     rdi, rax
0x18006db60  test    rax, rax
0x18006db63  jnz     short loc_18006DB6D
0x18006db65  lea     ebx, [rax+1Bh]
0x18006db68  jmp     loc_18006DE2A
0x18006db6d  mov     rax, [rax]
0x18006db70  mov     rdx, rsi
0x18006db73  mov     rcx, rdi
0x18006db76  xor     r15d, r15d
0x18006db79  mov     rax, [rax+8]
0x18006db7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006db82  lea     rcx, [rbp+var_40]
0x18006db86  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006db8b  mov     [rdi+1Ch], eax
0x18006db8e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006db92  mov     ecx, [rsi+14h]; unsigned int
0x18006db95  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006db9a  mov     eax, cs:dword_18039EB68
0x18006dba0  cmp     eax, 5
0x18006dba3  jbe     short loc_18006DC13
0x18006dba5  mov     rdx, 400000000000h
0x18006dbaf  lea     rcx, dword_18039EB68
0x18006dbb6  call    _tlgKeywordOn
0x18006dbbb  test    al, al
0x18006dbbd  jz      short loc_18006DC13
0x18006dbbf  mov     eax, [rbp+var_40]
0x18006dbc2  lea     rdx, byte_1803179BB
0x18006dbc9  xor     ecx, ecx
0x18006dbcb  cmp     [rdi+1Ch], eax
0x18006dbce  movzx   eax, word ptr [rbp+var_10]
0x18006dbd2  mov     word ptr [rbp+var_40], ax
0x18006dbd6  setnz   cl
0x18006dbd9  mov     eax, [rsi+14h]
0x18006dbdc  mov     [rbp+var_38], eax
0x18006dbdf  lea     rax, [rbp+var_20]
0x18006dbe3  mov     [rbp+var_28], rax
0x18006dbe7  lea     rax, [rbp+var_3C]
0x18006dbeb  mov     [rsp+80h+var_48], rax
0x18006dbf0  lea     rax, [rbp+var_40]
0x18006dbf4  mov     [rsp+80h+var_50], rax
0x18006dbf9  lea     rax, [rbp+var_38]
0x18006dbfd  mov     [rsp+80h+var_58], rax
0x18006dc02  lea     rax, [rbp+var_28]
0x18006dc06  mov     [rsp+80h+var_60], rax
0x18006dc0b  mov     [rbp+var_3C], ecx
0x18006dc0e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006dc13  mov     rcx, [rsi]
0x18006dc16  test    rcx, rcx
0x18006dc19  jz      loc_18006DE00
0x18006dc1f  mov     rax, [rcx]
0x18006dc22  test    rax, rax
0x18006dc25  jz      loc_18006DE00
0x18006dc2b  mov     rax, [rax+18h]
0x18006dc2f  lea     r8, [rdi+20h]
0x18006dc33  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006dc3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dc3f  mov     ebx, eax
0x18006dc41  test    eax, eax
0x18006dc43  jnz     loc_18006DE05
0x18006dc49  cmp     [rsi+10h], r14d
0x18006dc4d  jz      loc_18006DD99
0x18006dc53  lea     rbx, [rdi+148h]
0x18006dc5a  mov     rcx, rbx
0x18006dc5d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006dc62  mov     rcx, rbx; struct CSpJobMgr **
0x18006dc65  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006dc6a  test    eax, eax
0x18006dc6c  jnz     short loc_18006DC76
0x18006dc6e  lea     ebx, [rax+1Ch]
0x18006dc71  jmp     loc_18006DE05
0x18006dc76  mov     ecx, 10h; Size
0x18006dc7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006dc80  xor     r8d, r8d; pcbe
0x18006dc83  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006dc8a  mov     rdx, rax; pv
0x18006dc8d  mov     r15, rax
0x18006dc90  mov     [rax], rdi
0x18006dc93  call    cs:__imp_CreateThreadpoolWork
0x18006dc9a  nop     dword ptr [rax+rax+00h]
0x18006dc9f  mov     r14, rax
0x18006dca2  test    rax, rax
0x18006dca5  jnz     short loc_18006DCB3
0x18006dca7  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006dcac  mov     ebx, eax
0x18006dcae  jmp     loc_18006DE05
0x18006dcb3  call    cs:__imp_GetCurrentThread
0x18006dcba  nop     dword ptr [rax+rax+00h]
0x18006dcbf  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006dcc3  xor     r8d, r8d; OpenAsSelf
0x18006dcc6  mov     rcx, rax; ThreadHandle
0x18006dcc9  mov     edx, 2000Ch; DesiredAccess
0x18006dcce  call    cs:__imp_OpenThreadToken
0x18006dcd5  nop     dword ptr [rax+rax+00h]
0x18006dcda  test    eax, eax
0x18006dcdc  jnz     short loc_18006DCF1
0x18006dcde  call    cs:__imp_GetLastError
0x18006dce5  nop     dword ptr [rax+rax+00h]
0x18006dcea  cmp     eax, 3F0h
0x18006dcef  jnz     short loc_18006DCA7
0x18006dcf1  mov     rax, [rbp+TokenHandle]
0x18006dcf5  mov     r8, r13
0x18006dcf8  mov     [r15+8], rax
0x18006dcfc  mov     rcx, rdi
0x18006dcff  mov     rax, [rdi]
0x18006dd02  mov     rdx, [rsi+8]
0x18006dd06  mov     rax, [rax+18h]
0x18006dd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd0f  mov     rax, [rdi]
0x18006dd12  mov     rdx, r12
0x18006dd15  mov     rcx, rdi
0x18006dd18  mov     rax, [rax+28h]
0x18006dd1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd21  mov     ebx, eax
0x18006dd23  test    eax, eax
0x18006dd25  jz      short loc_18006DD30
0x18006dd27  cmp     eax, 7
0x18006dd2a  jnz     loc_18006DE05
0x18006dd30  mov     rax, [rdi]
0x18006dd33  mov     rdx, r12
0x18006dd36  mov     rcx, rdi
0x18006dd39  mov     rax, [rax+38h]
0x18006dd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd42  mov     ebx, eax
0x18006dd44  test    eax, eax
0x18006dd46  jnz     loc_18006DE05
0x18006dd4c  mov     rax, [rdi+150h]
0x18006dd53  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006dd5a  jnz     short loc_18006DD70
0x18006dd5c  mov     rax, [rdi+158h]
0x18006dd63  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006dd6a  jz      loc_18006DE05
0x18006dd70  mov     rdx, r12
0x18006dd73  mov     rcx, rdi
0x18006dd76  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006dd7b  mov     ebx, eax
0x18006dd7d  test    eax, eax
0x18006dd7f  jnz     loc_18006DE05
0x18006dd85  mov     rcx, r14; pwk
0x18006dd88  call    cs:__imp_SubmitThreadpoolWork
0x18006dd8f  nop     dword ptr [rax+rax+00h]
0x18006dd94  jmp     loc_18006DE53
0x18006dd99  mov     rax, [rdi]
0x18006dd9c  mov     r8, r13
0x18006dd9f  mov     rdx, [rsi+8]
0x18006dda3  mov     rcx, rdi
0x18006dda6  mov     rax, [rax+10h]
0x18006ddaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ddaf  mov     rax, [rdi]
0x18006ddb2  mov     rdx, r12
0x18006ddb5  mov     rcx, rdi
0x18006ddb8  mov     rax, [rax+30h]
0x18006ddbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ddc1  mov     ebx, eax
0x18006ddc3  test    eax, eax
0x18006ddc5  jz      short loc_18006DDCC
0x18006ddc7  cmp     eax, 7
0x18006ddca  jnz     short loc_18006DE05
0x18006ddcc  mov     rax, [rdi]
0x18006ddcf  mov     rdx, r12
0x18006ddd2  mov     rcx, rdi
0x18006ddd5  mov     rax, [rax+28h]
0x18006ddd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ddde  mov     ebx, eax
0x18006dde0  test    eax, eax
0x18006dde2  jz      short loc_18006DDE9
0x18006dde4  cmp     eax, 7
0x18006dde7  jnz     short loc_18006DE05
0x18006dde9  mov     rax, [rdi]
0x18006ddec  mov     rdx, r12
0x18006ddef  mov     rcx, rdi
0x18006ddf2  mov     rax, [rax+38h]
0x18006ddf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ddfb  jmp     loc_18006DCAC
0x18006de00  mov     ebx, 4
0x18006de05  mov     rax, [rdi]
0x18006de08  mov     edx, 1
0x18006de0d  mov     rcx, rdi
0x18006de10  mov     rax, [rax]
0x18006de13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de18  test    r15, r15
0x18006de1b  jz      short loc_18006DE2A
0x18006de1d  mov     edx, 10h
0x18006de22  mov     rcx, r15; Block
0x18006de25  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006de2a  mov     rcx, [rbp+TokenHandle]; hObject
0x18006de2e  test    rcx, rcx
0x18006de31  jz      short loc_18006DE3F
0x18006de33  call    cs:__imp_CloseHandle
0x18006de3a  nop     dword ptr [rax+rax+00h]
0x18006de3f  test    r14, r14
0x18006de42  jz      short loc_18006DE53
0x18006de44  mov     rcx, r14; pwk
0x18006de47  call    cs:__imp_CloseThreadpoolWork
0x18006de4e  nop     dword ptr [rax+rax+00h]
0x18006de53  mov     eax, ebx
0x18006de55  mov     rcx, [rbp+var_8]
0x18006de59  xor     rcx, rsp; StackCookie
0x18006de5c  call    __security_check_cookie
0x18006de61  mov     rbx, [rsp+80h+arg_18]
0x18006de69  add     rsp, 80h
0x18006de70  pop     r15
0x18006de72  pop     r14
0x18006de74  pop     r13
0x18006de76  pop     r12
0x18006de78  pop     rdi
0x18006de79  pop     rsi
0x18006de7a  pop     rbp
0x18006de7b  retn
```
