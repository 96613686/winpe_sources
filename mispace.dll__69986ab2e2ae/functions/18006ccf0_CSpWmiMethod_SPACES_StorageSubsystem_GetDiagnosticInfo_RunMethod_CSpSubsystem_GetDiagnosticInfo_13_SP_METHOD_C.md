# CSpWmiMethod<_SPACES_StorageSubsystem_GetDiagnosticInfo>::RunMethod<CSpSubsystem::GetDiagnosticInfo,13>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18006ccf0`
- end: `0x18006d06d`
- name: `??$RunMethod@VGetDiagnosticInfo@CSpSubsystem@@$0N@@?$CSpWmiMethod@U_SPACES_StorageSubsystem_GetDiagnosticInfo@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x18006ccf0`
- `0x18006e318`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cece`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006cea3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006cea3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006cebe`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006cebe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006ce83`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006ce83`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006cf78`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006cf78`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006d037`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006d037`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d023`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d023`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageSubsystem_GetDiagnosticInfo>::RunMethod<CSpSubsystem::GetDiagnosticInfo,13>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 DiagnosticInfo; // rax
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
  CSpSubsystem::GetDiagnosticInfo *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpSubsystem::GetDiagnosticInfo *)operator new(0x160u);
  DiagnosticInfo = CSpSubsystem::GetDiagnosticInfo::GetDiagnosticInfo(v25);
  v8 = DiagnosticInfo;
  if ( DiagnosticInfo )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)DiagnosticInfo + 8LL))(DiagnosticInfo, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpSubsystem::GetDiagnosticInfo *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_180318424,
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
0x18006ccf0  mov     [rsp-38h+arg_18], rbx
0x18006ccf5  push    rbp
0x18006ccf6  push    rsi
0x18006ccf7  push    rdi
0x18006ccf8  push    r12
0x18006ccfa  push    r13
0x18006ccfc  push    r14
0x18006ccfe  push    r15
0x18006cd00  mov     rbp, rsp
0x18006cd03  sub     rsp, 80h
0x18006cd0a  mov     rax, cs:__security_cookie
0x18006cd11  xor     rax, rsp
0x18006cd14  mov     [rbp+var_8], rax
0x18006cd18  xor     eax, eax
0x18006cd1a  mov     rsi, rcx
0x18006cd1d  xorps   xmm0, xmm0
0x18006cd20  mov     [rbp+var_10], eax
0x18006cd23  mov     ecx, 160h; Size
0x18006cd28  mov     [rbp+var_40], eax
0x18006cd2b  movups  [rbp+var_20], xmm0
0x18006cd2f  mov     [rbp+TokenHandle], rax
0x18006cd33  mov     r12, r8
0x18006cd36  mov     r13, rdx
0x18006cd39  xor     r14d, r14d
0x18006cd3c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006cd41  mov     rcx, rax; this
0x18006cd44  mov     [rbp+var_28], rax
0x18006cd48  call    ??0GetDiagnosticInfo@CSpSubsystem@@QEAA@XZ; CSpSubsystem::GetDiagnosticInfo::GetDiagnosticInfo(void)
0x18006cd4d  mov     rdi, rax
0x18006cd50  test    rax, rax
0x18006cd53  jnz     short loc_18006CD5D
0x18006cd55  lea     ebx, [rax+1Bh]
0x18006cd58  jmp     loc_18006D01A
0x18006cd5d  mov     rax, [rax]
0x18006cd60  mov     rdx, rsi
0x18006cd63  mov     rcx, rdi
0x18006cd66  xor     r15d, r15d
0x18006cd69  mov     rax, [rax+8]
0x18006cd6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cd72  lea     rcx, [rbp+var_40]
0x18006cd76  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18006cd7b  mov     [rdi+1Ch], eax
0x18006cd7e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18006cd82  mov     ecx, [rsi+14h]; unsigned int
0x18006cd85  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18006cd8a  mov     eax, cs:dword_18039EB68
0x18006cd90  cmp     eax, 5
0x18006cd93  jbe     short loc_18006CE03
0x18006cd95  mov     rdx, 400000000000h
0x18006cd9f  lea     rcx, dword_18039EB68
0x18006cda6  call    _tlgKeywordOn
0x18006cdab  test    al, al
0x18006cdad  jz      short loc_18006CE03
0x18006cdaf  mov     eax, [rbp+var_40]
0x18006cdb2  lea     rdx, dword_180318424
0x18006cdb9  xor     ecx, ecx
0x18006cdbb  cmp     [rdi+1Ch], eax
0x18006cdbe  movzx   eax, word ptr [rbp+var_10]
0x18006cdc2  mov     word ptr [rbp+var_40], ax
0x18006cdc6  setnz   cl
0x18006cdc9  mov     eax, [rsi+14h]
0x18006cdcc  mov     [rbp+var_38], eax
0x18006cdcf  lea     rax, [rbp+var_20]
0x18006cdd3  mov     [rbp+var_28], rax
0x18006cdd7  lea     rax, [rbp+var_3C]
0x18006cddb  mov     [rsp+80h+var_48], rax
0x18006cde0  lea     rax, [rbp+var_40]
0x18006cde4  mov     [rsp+80h+var_50], rax
0x18006cde9  lea     rax, [rbp+var_38]
0x18006cded  mov     [rsp+80h+var_58], rax
0x18006cdf2  lea     rax, [rbp+var_28]
0x18006cdf6  mov     [rsp+80h+var_60], rax
0x18006cdfb  mov     [rbp+var_3C], ecx
0x18006cdfe  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18006ce03  mov     rcx, [rsi]
0x18006ce06  test    rcx, rcx
0x18006ce09  jz      loc_18006CFF0
0x18006ce0f  mov     rax, [rcx]
0x18006ce12  test    rax, rax
0x18006ce15  jz      loc_18006CFF0
0x18006ce1b  mov     rax, [rax+18h]
0x18006ce1f  lea     r8, [rdi+20h]
0x18006ce23  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18006ce2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ce2f  mov     ebx, eax
0x18006ce31  test    eax, eax
0x18006ce33  jnz     loc_18006CFF5
0x18006ce39  cmp     [rsi+10h], r14d
0x18006ce3d  jz      loc_18006CF89
0x18006ce43  lea     rbx, [rdi+148h]
0x18006ce4a  mov     rcx, rbx
0x18006ce4d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18006ce52  mov     rcx, rbx; struct CSpJobMgr **
0x18006ce55  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18006ce5a  test    eax, eax
0x18006ce5c  jnz     short loc_18006CE66
0x18006ce5e  lea     ebx, [rax+1Ch]
0x18006ce61  jmp     loc_18006CFF5
0x18006ce66  mov     ecx, 10h; Size
0x18006ce6b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006ce70  xor     r8d, r8d; pcbe
0x18006ce73  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006ce7a  mov     rdx, rax; pv
0x18006ce7d  mov     r15, rax
0x18006ce80  mov     [rax], rdi
0x18006ce83  call    cs:__imp_CreateThreadpoolWork
0x18006ce8a  nop     dword ptr [rax+rax+00h]
0x18006ce8f  mov     r14, rax
0x18006ce92  test    rax, rax
0x18006ce95  jnz     short loc_18006CEA3
0x18006ce97  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18006ce9c  mov     ebx, eax
0x18006ce9e  jmp     loc_18006CFF5
0x18006cea3  call    cs:__imp_GetCurrentThread
0x18006ceaa  nop     dword ptr [rax+rax+00h]
0x18006ceaf  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18006ceb3  xor     r8d, r8d; OpenAsSelf
0x18006ceb6  mov     rcx, rax; ThreadHandle
0x18006ceb9  mov     edx, 2000Ch; DesiredAccess
0x18006cebe  call    cs:__imp_OpenThreadToken
0x18006cec5  nop     dword ptr [rax+rax+00h]
0x18006ceca  test    eax, eax
0x18006cecc  jnz     short loc_18006CEE1
0x18006cece  call    cs:__imp_GetLastError
0x18006ced5  nop     dword ptr [rax+rax+00h]
0x18006ceda  cmp     eax, 3F0h
0x18006cedf  jnz     short loc_18006CE97
0x18006cee1  mov     rax, [rbp+TokenHandle]
0x18006cee5  mov     r8, r13
0x18006cee8  mov     [r15+8], rax
0x18006ceec  mov     rcx, rdi
0x18006ceef  mov     rax, [rdi]
0x18006cef2  mov     rdx, [rsi+8]
0x18006cef6  mov     rax, [rax+18h]
0x18006cefa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ceff  mov     rax, [rdi]
0x18006cf02  mov     rdx, r12
0x18006cf05  mov     rcx, rdi
0x18006cf08  mov     rax, [rax+28h]
0x18006cf0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf11  mov     ebx, eax
0x18006cf13  test    eax, eax
0x18006cf15  jz      short loc_18006CF20
0x18006cf17  cmp     eax, 7
0x18006cf1a  jnz     loc_18006CFF5
0x18006cf20  mov     rax, [rdi]
0x18006cf23  mov     rdx, r12
0x18006cf26  mov     rcx, rdi
0x18006cf29  mov     rax, [rax+38h]
0x18006cf2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf32  mov     ebx, eax
0x18006cf34  test    eax, eax
0x18006cf36  jnz     loc_18006CFF5
0x18006cf3c  mov     rax, [rdi+150h]
0x18006cf43  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18006cf4a  jnz     short loc_18006CF60
0x18006cf4c  mov     rax, [rdi+158h]
0x18006cf53  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18006cf5a  jz      loc_18006CFF5
0x18006cf60  mov     rdx, r12
0x18006cf63  mov     rcx, rdi
0x18006cf66  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18006cf6b  mov     ebx, eax
0x18006cf6d  test    eax, eax
0x18006cf6f  jnz     loc_18006CFF5
0x18006cf75  mov     rcx, r14; pwk
0x18006cf78  call    cs:__imp_SubmitThreadpoolWork
0x18006cf7f  nop     dword ptr [rax+rax+00h]
0x18006cf84  jmp     loc_18006D043
0x18006cf89  mov     rax, [rdi]
0x18006cf8c  mov     r8, r13
0x18006cf8f  mov     rdx, [rsi+8]
0x18006cf93  mov     rcx, rdi
0x18006cf96  mov     rax, [rax+10h]
0x18006cf9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf9f  mov     rax, [rdi]
0x18006cfa2  mov     rdx, r12
0x18006cfa5  mov     rcx, rdi
0x18006cfa8  mov     rax, [rax+30h]
0x18006cfac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cfb1  mov     ebx, eax
0x18006cfb3  test    eax, eax
0x18006cfb5  jz      short loc_18006CFBC
0x18006cfb7  cmp     eax, 7
0x18006cfba  jnz     short loc_18006CFF5
0x18006cfbc  mov     rax, [rdi]
0x18006cfbf  mov     rdx, r12
0x18006cfc2  mov     rcx, rdi
0x18006cfc5  mov     rax, [rax+28h]
0x18006cfc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cfce  mov     ebx, eax
0x18006cfd0  test    eax, eax
0x18006cfd2  jz      short loc_18006CFD9
0x18006cfd4  cmp     eax, 7
0x18006cfd7  jnz     short loc_18006CFF5
0x18006cfd9  mov     rax, [rdi]
0x18006cfdc  mov     rdx, r12
0x18006cfdf  mov     rcx, rdi
0x18006cfe2  mov     rax, [rax+38h]
0x18006cfe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cfeb  jmp     loc_18006CE9C
0x18006cff0  mov     ebx, 4
0x18006cff5  mov     rax, [rdi]
0x18006cff8  mov     edx, 1
0x18006cffd  mov     rcx, rdi
0x18006d000  mov     rax, [rax]
0x18006d003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d008  test    r15, r15
0x18006d00b  jz      short loc_18006D01A
0x18006d00d  mov     edx, 10h
0x18006d012  mov     rcx, r15; Block
0x18006d015  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006d01a  mov     rcx, [rbp+TokenHandle]; hObject
0x18006d01e  test    rcx, rcx
0x18006d021  jz      short loc_18006D02F
0x18006d023  call    cs:__imp_CloseHandle
0x18006d02a  nop     dword ptr [rax+rax+00h]
0x18006d02f  test    r14, r14
0x18006d032  jz      short loc_18006D043
0x18006d034  mov     rcx, r14; pwk
0x18006d037  call    cs:__imp_CloseThreadpoolWork
0x18006d03e  nop     dword ptr [rax+rax+00h]
0x18006d043  mov     eax, ebx
0x18006d045  mov     rcx, [rbp+var_8]
0x18006d049  xor     rcx, rsp; StackCookie
0x18006d04c  call    __security_check_cookie
0x18006d051  mov     rbx, [rsp+80h+arg_18]
0x18006d059  add     rsp, 80h
0x18006d060  pop     r15
0x18006d062  pop     r14
0x18006d064  pop     r13
0x18006d066  pop     r12
0x18006d068  pop     rdi
0x18006d069  pop     rsi
0x18006d06a  pop     rbp
0x18006d06b  retn
```
