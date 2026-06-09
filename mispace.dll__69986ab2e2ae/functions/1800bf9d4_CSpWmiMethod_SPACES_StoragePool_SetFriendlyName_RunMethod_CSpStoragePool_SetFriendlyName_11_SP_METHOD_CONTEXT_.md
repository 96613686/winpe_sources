# CSpWmiMethod<_SPACES_StoragePool_SetFriendlyName>::RunMethod<CSpStoragePool::SetFriendlyName,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bf9d4`
- end: `0x1800bfd51`
- name: `??$RunMethod@VSetFriendlyName@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_SetFriendlyName@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
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
- `0x1800bf9d4`
- `0x1800c12d0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfbb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bfbb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bfb87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bfb87`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bfba2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bfba2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bfb67`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bfb67`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bfc5c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bfc5c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bfd1b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bfd1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bfd07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bfd07`

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
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStoragePool::SetFriendlyName *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&byte_18032E817,
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
0x1800bf9d4  mov     [rsp-38h+arg_18], rbx
0x1800bf9d9  push    rbp
0x1800bf9da  push    rsi
0x1800bf9db  push    rdi
0x1800bf9dc  push    r12
0x1800bf9de  push    r13
0x1800bf9e0  push    r14
0x1800bf9e2  push    r15
0x1800bf9e4  mov     rbp, rsp
0x1800bf9e7  sub     rsp, 80h
0x1800bf9ee  mov     rax, cs:__security_cookie
0x1800bf9f5  xor     rax, rsp
0x1800bf9f8  mov     [rbp+var_8], rax
0x1800bf9fc  xor     eax, eax
0x1800bf9fe  mov     rsi, rcx
0x1800bfa01  xorps   xmm0, xmm0
0x1800bfa04  mov     [rbp+var_10], eax
0x1800bfa07  mov     ecx, 160h; Size
0x1800bfa0c  mov     [rbp+var_40], eax
0x1800bfa0f  movups  [rbp+var_20], xmm0
0x1800bfa13  mov     [rbp+TokenHandle], rax
0x1800bfa17  mov     r12, r8
0x1800bfa1a  mov     r13, rdx
0x1800bfa1d  xor     r14d, r14d
0x1800bfa20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bfa25  mov     rcx, rax; this
0x1800bfa28  mov     [rbp+var_28], rax
0x1800bfa2c  call    ??0SetFriendlyName@CSpStoragePool@@QEAA@XZ; CSpStoragePool::SetFriendlyName::SetFriendlyName(void)
0x1800bfa31  mov     rdi, rax
0x1800bfa34  test    rax, rax
0x1800bfa37  jnz     short loc_1800BFA41
0x1800bfa39  lea     ebx, [rax+1Bh]
0x1800bfa3c  jmp     loc_1800BFCFE
0x1800bfa41  mov     rax, [rax]
0x1800bfa44  mov     rdx, rsi
0x1800bfa47  mov     rcx, rdi
0x1800bfa4a  xor     r15d, r15d
0x1800bfa4d  mov     rax, [rax+8]
0x1800bfa51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfa56  lea     rcx, [rbp+var_40]
0x1800bfa5a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bfa5f  mov     [rdi+1Ch], eax
0x1800bfa62  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bfa66  mov     ecx, [rsi+14h]; unsigned int
0x1800bfa69  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bfa6e  mov     eax, cs:dword_18039EB68
0x1800bfa74  cmp     eax, 5
0x1800bfa77  jbe     short loc_1800BFAE7
0x1800bfa79  mov     rdx, 400000000000h
0x1800bfa83  lea     rcx, dword_18039EB68
0x1800bfa8a  call    _tlgKeywordOn
0x1800bfa8f  test    al, al
0x1800bfa91  jz      short loc_1800BFAE7
0x1800bfa93  mov     eax, [rbp+var_40]
0x1800bfa96  lea     rdx, byte_18032E817
0x1800bfa9d  xor     ecx, ecx
0x1800bfa9f  cmp     [rdi+1Ch], eax
0x1800bfaa2  movzx   eax, word ptr [rbp+var_10]
0x1800bfaa6  mov     word ptr [rbp+var_40], ax
0x1800bfaaa  setnz   cl
0x1800bfaad  mov     eax, [rsi+14h]
0x1800bfab0  mov     [rbp+var_38], eax
0x1800bfab3  lea     rax, [rbp+var_20]
0x1800bfab7  mov     [rbp+var_28], rax
0x1800bfabb  lea     rax, [rbp+var_3C]
0x1800bfabf  mov     [rsp+80h+var_48], rax
0x1800bfac4  lea     rax, [rbp+var_40]
0x1800bfac8  mov     [rsp+80h+var_50], rax
0x1800bfacd  lea     rax, [rbp+var_38]
0x1800bfad1  mov     [rsp+80h+var_58], rax
0x1800bfad6  lea     rax, [rbp+var_28]
0x1800bfada  mov     [rsp+80h+var_60], rax
0x1800bfadf  mov     [rbp+var_3C], ecx
0x1800bfae2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bfae7  mov     rcx, [rsi]
0x1800bfaea  test    rcx, rcx
0x1800bfaed  jz      loc_1800BFCD4
0x1800bfaf3  mov     rax, [rcx]
0x1800bfaf6  test    rax, rax
0x1800bfaf9  jz      loc_1800BFCD4
0x1800bfaff  mov     rax, [rax+18h]
0x1800bfb03  lea     r8, [rdi+20h]
0x1800bfb07  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bfb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfb13  mov     ebx, eax
0x1800bfb15  test    eax, eax
0x1800bfb17  jnz     loc_1800BFCD9
0x1800bfb1d  cmp     [rsi+10h], r14d
0x1800bfb21  jz      loc_1800BFC6D
0x1800bfb27  lea     rbx, [rdi+148h]
0x1800bfb2e  mov     rcx, rbx
0x1800bfb31  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bfb36  mov     rcx, rbx; struct CSpJobMgr **
0x1800bfb39  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bfb3e  test    eax, eax
0x1800bfb40  jnz     short loc_1800BFB4A
0x1800bfb42  lea     ebx, [rax+1Ch]
0x1800bfb45  jmp     loc_1800BFCD9
0x1800bfb4a  mov     ecx, 10h; Size
0x1800bfb4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bfb54  xor     r8d, r8d; pcbe
0x1800bfb57  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bfb5e  mov     rdx, rax; pv
0x1800bfb61  mov     r15, rax
0x1800bfb64  mov     [rax], rdi
0x1800bfb67  call    cs:__imp_CreateThreadpoolWork
0x1800bfb6e  nop     dword ptr [rax+rax+00h]
0x1800bfb73  mov     r14, rax
0x1800bfb76  test    rax, rax
0x1800bfb79  jnz     short loc_1800BFB87
0x1800bfb7b  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bfb80  mov     ebx, eax
0x1800bfb82  jmp     loc_1800BFCD9
0x1800bfb87  call    cs:__imp_GetCurrentThread
0x1800bfb8e  nop     dword ptr [rax+rax+00h]
0x1800bfb93  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bfb97  xor     r8d, r8d; OpenAsSelf
0x1800bfb9a  mov     rcx, rax; ThreadHandle
0x1800bfb9d  mov     edx, 2000Ch; DesiredAccess
0x1800bfba2  call    cs:__imp_OpenThreadToken
0x1800bfba9  nop     dword ptr [rax+rax+00h]
0x1800bfbae  test    eax, eax
0x1800bfbb0  jnz     short loc_1800BFBC5
0x1800bfbb2  call    cs:__imp_GetLastError
0x1800bfbb9  nop     dword ptr [rax+rax+00h]
0x1800bfbbe  cmp     eax, 3F0h
0x1800bfbc3  jnz     short loc_1800BFB7B
0x1800bfbc5  mov     rax, [rbp+TokenHandle]
0x1800bfbc9  mov     r8, r13
0x1800bfbcc  mov     [r15+8], rax
0x1800bfbd0  mov     rcx, rdi
0x1800bfbd3  mov     rax, [rdi]
0x1800bfbd6  mov     rdx, [rsi+8]
0x1800bfbda  mov     rax, [rax+18h]
0x1800bfbde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfbe3  mov     rax, [rdi]
0x1800bfbe6  mov     rdx, r12
0x1800bfbe9  mov     rcx, rdi
0x1800bfbec  mov     rax, [rax+28h]
0x1800bfbf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfbf5  mov     ebx, eax
0x1800bfbf7  test    eax, eax
0x1800bfbf9  jz      short loc_1800BFC04
0x1800bfbfb  cmp     eax, 7
0x1800bfbfe  jnz     loc_1800BFCD9
0x1800bfc04  mov     rax, [rdi]
0x1800bfc07  mov     rdx, r12
0x1800bfc0a  mov     rcx, rdi
0x1800bfc0d  mov     rax, [rax+38h]
0x1800bfc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfc16  mov     ebx, eax
0x1800bfc18  test    eax, eax
0x1800bfc1a  jnz     loc_1800BFCD9
0x1800bfc20  mov     rax, [rdi+150h]
0x1800bfc27  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bfc2e  jnz     short loc_1800BFC44
0x1800bfc30  mov     rax, [rdi+158h]
0x1800bfc37  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bfc3e  jz      loc_1800BFCD9
0x1800bfc44  mov     rdx, r12
0x1800bfc47  mov     rcx, rdi
0x1800bfc4a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bfc4f  mov     ebx, eax
0x1800bfc51  test    eax, eax
0x1800bfc53  jnz     loc_1800BFCD9
0x1800bfc59  mov     rcx, r14; pwk
0x1800bfc5c  call    cs:__imp_SubmitThreadpoolWork
0x1800bfc63  nop     dword ptr [rax+rax+00h]
0x1800bfc68  jmp     loc_1800BFD27
0x1800bfc6d  mov     rax, [rdi]
0x1800bfc70  mov     r8, r13
0x1800bfc73  mov     rdx, [rsi+8]
0x1800bfc77  mov     rcx, rdi
0x1800bfc7a  mov     rax, [rax+10h]
0x1800bfc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfc83  mov     rax, [rdi]
0x1800bfc86  mov     rdx, r12
0x1800bfc89  mov     rcx, rdi
0x1800bfc8c  mov     rax, [rax+30h]
0x1800bfc90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfc95  mov     ebx, eax
0x1800bfc97  test    eax, eax
0x1800bfc99  jz      short loc_1800BFCA0
0x1800bfc9b  cmp     eax, 7
0x1800bfc9e  jnz     short loc_1800BFCD9
0x1800bfca0  mov     rax, [rdi]
0x1800bfca3  mov     rdx, r12
0x1800bfca6  mov     rcx, rdi
0x1800bfca9  mov     rax, [rax+28h]
0x1800bfcad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfcb2  mov     ebx, eax
0x1800bfcb4  test    eax, eax
0x1800bfcb6  jz      short loc_1800BFCBD
0x1800bfcb8  cmp     eax, 7
0x1800bfcbb  jnz     short loc_1800BFCD9
0x1800bfcbd  mov     rax, [rdi]
0x1800bfcc0  mov     rdx, r12
0x1800bfcc3  mov     rcx, rdi
0x1800bfcc6  mov     rax, [rax+38h]
0x1800bfcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfccf  jmp     loc_1800BFB80
0x1800bfcd4  mov     ebx, 4
0x1800bfcd9  mov     rax, [rdi]
0x1800bfcdc  mov     edx, 1
0x1800bfce1  mov     rcx, rdi
0x1800bfce4  mov     rax, [rax]
0x1800bfce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfcec  test    r15, r15
0x1800bfcef  jz      short loc_1800BFCFE
0x1800bfcf1  mov     edx, 10h
0x1800bfcf6  mov     rcx, r15; Block
0x1800bfcf9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bfcfe  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bfd02  test    rcx, rcx
0x1800bfd05  jz      short loc_1800BFD13
0x1800bfd07  call    cs:__imp_CloseHandle
0x1800bfd0e  nop     dword ptr [rax+rax+00h]
0x1800bfd13  test    r14, r14
0x1800bfd16  jz      short loc_1800BFD27
0x1800bfd18  mov     rcx, r14; pwk
0x1800bfd1b  call    cs:__imp_CloseThreadpoolWork
0x1800bfd22  nop     dword ptr [rax+rax+00h]
0x1800bfd27  mov     eax, ebx
0x1800bfd29  mov     rcx, [rbp+var_8]
0x1800bfd2d  xor     rcx, rsp; StackCookie
0x1800bfd30  call    __security_check_cookie
0x1800bfd35  mov     rbx, [rsp+80h+arg_18]
0x1800bfd3d  add     rsp, 80h
0x1800bfd44  pop     r15
0x1800bfd46  pop     r14
0x1800bfd48  pop     r13
0x1800bfd4a  pop     r12
0x1800bfd4c  pop     rdi
0x1800bfd4d  pop     rsi
0x1800bfd4e  pop     rbp
0x1800bfd4f  retn
```
