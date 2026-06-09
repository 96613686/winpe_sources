# CSpWmiMethod<_MI_Instance>::RunMethod<CSpResiliency::SetDefaults,7>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18010a7d4`
- end: `0x18010ab55`
- name: `??$RunMethod@VSetDefaults@CSpResiliency@@$06@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `897`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18010b190`

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
- `0x18010a7d4`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010a9b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010a9b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010a989`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010a989`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010a9a4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010a9a4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18010a969`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18010a969`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18010aa5f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18010aa5f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010ab1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18010ab1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010ab0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010ab0b`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpResiliency::SetDefaults,7>(
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
  *(_QWORD *)v24 = &CSpResiliency::SetDefaults::`vftable';
  ((void (__fastcall *)(__int128 *, __int64 *))CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::SetContext)(v8, a1);
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
      (unsigned int)byte_180341E05,
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
0x18010a7d4  mov     [rsp-38h+arg_18], rbx
0x18010a7d9  push    rbp
0x18010a7da  push    rsi
0x18010a7db  push    rdi
0x18010a7dc  push    r12
0x18010a7de  push    r13
0x18010a7e0  push    r14
0x18010a7e2  push    r15
0x18010a7e4  mov     rbp, rsp
0x18010a7e7  sub     rsp, 80h
0x18010a7ee  mov     rax, cs:__security_cookie
0x18010a7f5  xor     rax, rsp
0x18010a7f8  mov     [rbp+var_8], rax
0x18010a7fc  xor     eax, eax
0x18010a7fe  mov     r12, rcx
0x18010a801  xorps   xmm0, xmm0
0x18010a804  mov     [rbp+var_10], eax
0x18010a807  mov     ecx, 160h; Size
0x18010a80c  mov     [rbp+var_40], eax
0x18010a80f  movups  [rbp+var_20], xmm0
0x18010a813  mov     [rbp+TokenHandle], rax
0x18010a817  mov     r15, r8
0x18010a81a  mov     r13, rdx
0x18010a81d  xor     r14d, r14d
0x18010a820  xor     esi, esi
0x18010a822  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18010a827  mov     rcx, rax
0x18010a82a  mov     [rbp+var_28], rax
0x18010a82e  mov     rdi, rax
0x18010a831  call    ??0?$CSpWmiMethod@U_MI_Instance@@@@QEAA@XZ; CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(void)
0x18010a836  lea     rax, ??_7SetDefaults@CSpResiliency@@6B@; const CSpResiliency::SetDefaults::`vftable'
0x18010a83d  mov     rdx, r12
0x18010a840  mov     [rdi], rax
0x18010a843  mov     rcx, rdi
0x18010a846  mov     rax, cs:off_18020A8D0
0x18010a84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a852  lea     rcx, [rbp+var_40]
0x18010a856  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18010a85b  mov     [rdi+1Ch], eax
0x18010a85e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18010a862  mov     ecx, [r12+14h]; unsigned int
0x18010a867  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18010a86c  mov     eax, cs:dword_18039EB68
0x18010a872  cmp     eax, 5
0x18010a875  jbe     short loc_18010A8E7
0x18010a877  mov     rdx, 400000000000h
0x18010a881  lea     rcx, dword_18039EB68
0x18010a888  call    _tlgKeywordOn
0x18010a88d  test    al, al
0x18010a88f  jz      short loc_18010A8E7
0x18010a891  mov     eax, [rbp+var_40]
0x18010a894  lea     rdx, byte_180341E05
0x18010a89b  xor     ecx, ecx
0x18010a89d  cmp     [rdi+1Ch], eax
0x18010a8a0  movzx   eax, word ptr [rbp+var_10]
0x18010a8a4  mov     word ptr [rbp+var_40], ax
0x18010a8a8  setnz   cl
0x18010a8ab  mov     eax, [r12+14h]
0x18010a8b0  mov     [rbp+var_38], eax
0x18010a8b3  lea     rax, [rbp+var_20]
0x18010a8b7  mov     [rbp+var_28], rax
0x18010a8bb  lea     rax, [rbp+var_3C]
0x18010a8bf  mov     [rsp+80h+var_48], rax
0x18010a8c4  lea     rax, [rbp+var_40]
0x18010a8c8  mov     [rsp+80h+var_50], rax
0x18010a8cd  lea     rax, [rbp+var_38]
0x18010a8d1  mov     [rsp+80h+var_58], rax
0x18010a8d6  lea     rax, [rbp+var_28]
0x18010a8da  mov     [rsp+80h+var_60], rax
0x18010a8df  mov     [rbp+var_3C], ecx
0x18010a8e2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18010a8e7  mov     rcx, [r12]
0x18010a8eb  test    rcx, rcx
0x18010a8ee  jz      loc_18010AAD8
0x18010a8f4  mov     rax, [rcx]
0x18010a8f7  test    rax, rax
0x18010a8fa  jz      loc_18010AAD8
0x18010a900  mov     rax, [rax+18h]
0x18010a904  lea     r8, [rdi+20h]
0x18010a908  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18010a90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a914  mov     ebx, eax
0x18010a916  test    eax, eax
0x18010a918  jnz     loc_18010AADD
0x18010a91e  cmp     [r12+10h], esi
0x18010a923  jz      loc_18010AA70
0x18010a929  lea     rbx, [rdi+148h]
0x18010a930  mov     rcx, rbx
0x18010a933  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18010a938  mov     rcx, rbx; struct CSpJobMgr **
0x18010a93b  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18010a940  test    eax, eax
0x18010a942  jnz     short loc_18010A94C
0x18010a944  lea     ebx, [rax+1Ch]
0x18010a947  jmp     loc_18010AADD
0x18010a94c  mov     ecx, 10h; Size
0x18010a951  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18010a956  xor     r8d, r8d; pcbe
0x18010a959  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18010a960  mov     rdx, rax; pv
0x18010a963  mov     r14, rax
0x18010a966  mov     [rax], rdi
0x18010a969  call    cs:__imp_CreateThreadpoolWork
0x18010a970  nop     dword ptr [rax+rax+00h]
0x18010a975  mov     rsi, rax
0x18010a978  test    rax, rax
0x18010a97b  jnz     short loc_18010A989
0x18010a97d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18010a982  mov     ebx, eax
0x18010a984  jmp     loc_18010AADD
0x18010a989  call    cs:__imp_GetCurrentThread
0x18010a990  nop     dword ptr [rax+rax+00h]
0x18010a995  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18010a999  xor     r8d, r8d; OpenAsSelf
0x18010a99c  mov     rcx, rax; ThreadHandle
0x18010a99f  mov     edx, 2000Ch; DesiredAccess
0x18010a9a4  call    cs:__imp_OpenThreadToken
0x18010a9ab  nop     dword ptr [rax+rax+00h]
0x18010a9b0  test    eax, eax
0x18010a9b2  jnz     short loc_18010A9C7
0x18010a9b4  call    cs:__imp_GetLastError
0x18010a9bb  nop     dword ptr [rax+rax+00h]
0x18010a9c0  cmp     eax, 3F0h
0x18010a9c5  jnz     short loc_18010A97D
0x18010a9c7  mov     rax, [rbp+TokenHandle]
0x18010a9cb  mov     r8, r13
0x18010a9ce  mov     [r14+8], rax
0x18010a9d2  mov     rcx, rdi
0x18010a9d5  mov     rax, [rdi]
0x18010a9d8  mov     rdx, [r12+8]
0x18010a9dd  mov     rax, [rax+18h]
0x18010a9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a9e6  mov     rax, [rdi]
0x18010a9e9  mov     rdx, r15
0x18010a9ec  mov     rcx, rdi
0x18010a9ef  mov     rax, [rax+28h]
0x18010a9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a9f8  mov     ebx, eax
0x18010a9fa  test    eax, eax
0x18010a9fc  jz      short loc_18010AA07
0x18010a9fe  cmp     eax, 7
0x18010aa01  jnz     loc_18010AADD
0x18010aa07  mov     rax, [rdi]
0x18010aa0a  mov     rdx, r15
0x18010aa0d  mov     rcx, rdi
0x18010aa10  mov     rax, [rax+38h]
0x18010aa14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010aa19  mov     ebx, eax
0x18010aa1b  test    eax, eax
0x18010aa1d  jnz     loc_18010AADD
0x18010aa23  mov     rax, [rdi+150h]
0x18010aa2a  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18010aa31  jnz     short loc_18010AA47
0x18010aa33  mov     rax, [rdi+158h]
0x18010aa3a  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18010aa41  jz      loc_18010AADD
0x18010aa47  mov     rdx, r15
0x18010aa4a  mov     rcx, rdi
0x18010aa4d  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18010aa52  mov     ebx, eax
0x18010aa54  test    eax, eax
0x18010aa56  jnz     loc_18010AADD
0x18010aa5c  mov     rcx, rsi; pwk
0x18010aa5f  call    cs:__imp_SubmitThreadpoolWork
0x18010aa66  nop     dword ptr [rax+rax+00h]
0x18010aa6b  jmp     loc_18010AB2B
0x18010aa70  mov     rax, [rdi]
0x18010aa73  mov     r8, r13
0x18010aa76  mov     rdx, [r12+8]
0x18010aa7b  mov     rcx, rdi
0x18010aa7e  mov     rax, [rax+10h]
0x18010aa82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010aa87  mov     rax, [rdi]
0x18010aa8a  mov     rdx, r15
0x18010aa8d  mov     rcx, rdi
0x18010aa90  mov     rax, [rax+30h]
0x18010aa94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010aa99  mov     ebx, eax
0x18010aa9b  test    eax, eax
0x18010aa9d  jz      short loc_18010AAA4
0x18010aa9f  cmp     eax, 7
0x18010aaa2  jnz     short loc_18010AADD
0x18010aaa4  mov     rax, [rdi]
0x18010aaa7  mov     rdx, r15
0x18010aaaa  mov     rcx, rdi
0x18010aaad  mov     rax, [rax+28h]
0x18010aab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010aab6  mov     ebx, eax
0x18010aab8  test    eax, eax
0x18010aaba  jz      short loc_18010AAC1
0x18010aabc  cmp     eax, 7
0x18010aabf  jnz     short loc_18010AADD
0x18010aac1  mov     rax, [rdi]
0x18010aac4  mov     rdx, r15
0x18010aac7  mov     rcx, rdi
0x18010aaca  mov     rax, [rax+38h]
0x18010aace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010aad3  jmp     loc_18010A982
0x18010aad8  mov     ebx, 4
0x18010aadd  mov     rax, [rdi]
0x18010aae0  mov     edx, 1
0x18010aae5  mov     rcx, rdi
0x18010aae8  mov     rax, [rax]
0x18010aaeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010aaf0  test    r14, r14
0x18010aaf3  jz      short loc_18010AB02
0x18010aaf5  mov     edx, 10h
0x18010aafa  mov     rcx, r14; Block
0x18010aafd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18010ab02  mov     rcx, [rbp+TokenHandle]; hObject
0x18010ab06  test    rcx, rcx
0x18010ab09  jz      short loc_18010AB17
0x18010ab0b  call    cs:__imp_CloseHandle
0x18010ab12  nop     dword ptr [rax+rax+00h]
0x18010ab17  test    rsi, rsi
0x18010ab1a  jz      short loc_18010AB2B
0x18010ab1c  mov     rcx, rsi; pwk
0x18010ab1f  call    cs:__imp_CloseThreadpoolWork
0x18010ab26  nop     dword ptr [rax+rax+00h]
0x18010ab2b  mov     eax, ebx
0x18010ab2d  mov     rcx, [rbp+var_8]
0x18010ab31  xor     rcx, rsp; StackCookie
0x18010ab34  call    __security_check_cookie
0x18010ab39  mov     rbx, [rsp+80h+arg_18]
0x18010ab41  add     rsp, 80h
0x18010ab48  pop     r15
0x18010ab4a  pop     r14
0x18010ab4c  pop     r13
0x18010ab4e  pop     r12
0x18010ab50  pop     rdi
0x18010ab51  pop     rsi
0x18010ab52  pop     rbp
0x18010ab53  retn
```
