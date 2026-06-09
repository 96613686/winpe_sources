# CSpWmiMethod<_SPACES_StorageTier_SetFriendlyName>::RunMethod<CSpStorageTier::SetFriendlyName,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x180103adc`
- end: `0x180103e59`
- name: `??$RunMethod@VSetFriendlyName@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_SetFriendlyName@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180105a90`

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
- `0x180103adc`
- `0x180104184`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180103cba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180103c8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180103c8f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180103caa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180103caa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180103c6f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180103c6f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180103d64`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180103d64`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180103e23`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180103e23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180103e0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180103e0f`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_SetFriendlyName>::RunMethod<CSpStorageTier::SetFriendlyName,12>(
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
  CSpStorageTier::SetFriendlyName *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::SetFriendlyName *)operator new(0x160u);
  v7 = CSpStorageTier::SetFriendlyName::SetFriendlyName(v25);
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
      v25 = (CSpStorageTier::SetFriendlyName *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_1803415AC,
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
0x180103adc  mov     [rsp-38h+arg_18], rbx
0x180103ae1  push    rbp
0x180103ae2  push    rsi
0x180103ae3  push    rdi
0x180103ae4  push    r12
0x180103ae6  push    r13
0x180103ae8  push    r14
0x180103aea  push    r15
0x180103aec  mov     rbp, rsp
0x180103aef  sub     rsp, 80h
0x180103af6  mov     rax, cs:__security_cookie
0x180103afd  xor     rax, rsp
0x180103b00  mov     [rbp+var_8], rax
0x180103b04  xor     eax, eax
0x180103b06  mov     rsi, rcx
0x180103b09  xorps   xmm0, xmm0
0x180103b0c  mov     [rbp+var_10], eax
0x180103b0f  mov     ecx, 160h; Size
0x180103b14  mov     [rbp+var_40], eax
0x180103b17  movups  [rbp+var_20], xmm0
0x180103b1b  mov     [rbp+TokenHandle], rax
0x180103b1f  mov     r12, r8
0x180103b22  mov     r13, rdx
0x180103b25  xor     r14d, r14d
0x180103b28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180103b2d  mov     rcx, rax; this
0x180103b30  mov     [rbp+var_28], rax
0x180103b34  call    ??0SetFriendlyName@CSpStorageTier@@QEAA@XZ; CSpStorageTier::SetFriendlyName::SetFriendlyName(void)
0x180103b39  mov     rdi, rax
0x180103b3c  test    rax, rax
0x180103b3f  jnz     short loc_180103B49
0x180103b41  lea     ebx, [rax+1Bh]
0x180103b44  jmp     loc_180103E06
0x180103b49  mov     rax, [rax]
0x180103b4c  mov     rdx, rsi
0x180103b4f  mov     rcx, rdi
0x180103b52  xor     r15d, r15d
0x180103b55  mov     rax, [rax+8]
0x180103b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103b5e  lea     rcx, [rbp+var_40]
0x180103b62  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180103b67  mov     [rdi+1Ch], eax
0x180103b6a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x180103b6e  mov     ecx, [rsi+14h]; unsigned int
0x180103b71  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180103b76  mov     eax, cs:dword_18039EB68
0x180103b7c  cmp     eax, 5
0x180103b7f  jbe     short loc_180103BEF
0x180103b81  mov     rdx, 400000000000h
0x180103b8b  lea     rcx, dword_18039EB68
0x180103b92  call    _tlgKeywordOn
0x180103b97  test    al, al
0x180103b99  jz      short loc_180103BEF
0x180103b9b  mov     eax, [rbp+var_40]
0x180103b9e  lea     rdx, dword_1803415AC
0x180103ba5  xor     ecx, ecx
0x180103ba7  cmp     [rdi+1Ch], eax
0x180103baa  movzx   eax, word ptr [rbp+var_10]
0x180103bae  mov     word ptr [rbp+var_40], ax
0x180103bb2  setnz   cl
0x180103bb5  mov     eax, [rsi+14h]
0x180103bb8  mov     [rbp+var_38], eax
0x180103bbb  lea     rax, [rbp+var_20]
0x180103bbf  mov     [rbp+var_28], rax
0x180103bc3  lea     rax, [rbp+var_3C]
0x180103bc7  mov     [rsp+80h+var_48], rax
0x180103bcc  lea     rax, [rbp+var_40]
0x180103bd0  mov     [rsp+80h+var_50], rax
0x180103bd5  lea     rax, [rbp+var_38]
0x180103bd9  mov     [rsp+80h+var_58], rax
0x180103bde  lea     rax, [rbp+var_28]
0x180103be2  mov     [rsp+80h+var_60], rax
0x180103be7  mov     [rbp+var_3C], ecx
0x180103bea  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x180103bef  mov     rcx, [rsi]
0x180103bf2  test    rcx, rcx
0x180103bf5  jz      loc_180103DDC
0x180103bfb  mov     rax, [rcx]
0x180103bfe  test    rax, rax
0x180103c01  jz      loc_180103DDC
0x180103c07  mov     rax, [rax+18h]
0x180103c0b  lea     r8, [rdi+20h]
0x180103c0f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180103c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103c1b  mov     ebx, eax
0x180103c1d  test    eax, eax
0x180103c1f  jnz     loc_180103DE1
0x180103c25  cmp     [rsi+10h], r14d
0x180103c29  jz      loc_180103D75
0x180103c2f  lea     rbx, [rdi+148h]
0x180103c36  mov     rcx, rbx
0x180103c39  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180103c3e  mov     rcx, rbx; struct CSpJobMgr **
0x180103c41  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x180103c46  test    eax, eax
0x180103c48  jnz     short loc_180103C52
0x180103c4a  lea     ebx, [rax+1Ch]
0x180103c4d  jmp     loc_180103DE1
0x180103c52  mov     ecx, 10h; Size
0x180103c57  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180103c5c  xor     r8d, r8d; pcbe
0x180103c5f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180103c66  mov     rdx, rax; pv
0x180103c69  mov     r15, rax
0x180103c6c  mov     [rax], rdi
0x180103c6f  call    cs:__imp_CreateThreadpoolWork
0x180103c76  nop     dword ptr [rax+rax+00h]
0x180103c7b  mov     r14, rax
0x180103c7e  test    rax, rax
0x180103c81  jnz     short loc_180103C8F
0x180103c83  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180103c88  mov     ebx, eax
0x180103c8a  jmp     loc_180103DE1
0x180103c8f  call    cs:__imp_GetCurrentThread
0x180103c96  nop     dword ptr [rax+rax+00h]
0x180103c9b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180103c9f  xor     r8d, r8d; OpenAsSelf
0x180103ca2  mov     rcx, rax; ThreadHandle
0x180103ca5  mov     edx, 2000Ch; DesiredAccess
0x180103caa  call    cs:__imp_OpenThreadToken
0x180103cb1  nop     dword ptr [rax+rax+00h]
0x180103cb6  test    eax, eax
0x180103cb8  jnz     short loc_180103CCD
0x180103cba  call    cs:__imp_GetLastError
0x180103cc1  nop     dword ptr [rax+rax+00h]
0x180103cc6  cmp     eax, 3F0h
0x180103ccb  jnz     short loc_180103C83
0x180103ccd  mov     rax, [rbp+TokenHandle]
0x180103cd1  mov     r8, r13
0x180103cd4  mov     [r15+8], rax
0x180103cd8  mov     rcx, rdi
0x180103cdb  mov     rax, [rdi]
0x180103cde  mov     rdx, [rsi+8]
0x180103ce2  mov     rax, [rax+18h]
0x180103ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103ceb  mov     rax, [rdi]
0x180103cee  mov     rdx, r12
0x180103cf1  mov     rcx, rdi
0x180103cf4  mov     rax, [rax+28h]
0x180103cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103cfd  mov     ebx, eax
0x180103cff  test    eax, eax
0x180103d01  jz      short loc_180103D0C
0x180103d03  cmp     eax, 7
0x180103d06  jnz     loc_180103DE1
0x180103d0c  mov     rax, [rdi]
0x180103d0f  mov     rdx, r12
0x180103d12  mov     rcx, rdi
0x180103d15  mov     rax, [rax+38h]
0x180103d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103d1e  mov     ebx, eax
0x180103d20  test    eax, eax
0x180103d22  jnz     loc_180103DE1
0x180103d28  mov     rax, [rdi+150h]
0x180103d2f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180103d36  jnz     short loc_180103D4C
0x180103d38  mov     rax, [rdi+158h]
0x180103d3f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180103d46  jz      loc_180103DE1
0x180103d4c  mov     rdx, r12
0x180103d4f  mov     rcx, rdi
0x180103d52  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x180103d57  mov     ebx, eax
0x180103d59  test    eax, eax
0x180103d5b  jnz     loc_180103DE1
0x180103d61  mov     rcx, r14; pwk
0x180103d64  call    cs:__imp_SubmitThreadpoolWork
0x180103d6b  nop     dword ptr [rax+rax+00h]
0x180103d70  jmp     loc_180103E2F
0x180103d75  mov     rax, [rdi]
0x180103d78  mov     r8, r13
0x180103d7b  mov     rdx, [rsi+8]
0x180103d7f  mov     rcx, rdi
0x180103d82  mov     rax, [rax+10h]
0x180103d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103d8b  mov     rax, [rdi]
0x180103d8e  mov     rdx, r12
0x180103d91  mov     rcx, rdi
0x180103d94  mov     rax, [rax+30h]
0x180103d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103d9d  mov     ebx, eax
0x180103d9f  test    eax, eax
0x180103da1  jz      short loc_180103DA8
0x180103da3  cmp     eax, 7
0x180103da6  jnz     short loc_180103DE1
0x180103da8  mov     rax, [rdi]
0x180103dab  mov     rdx, r12
0x180103dae  mov     rcx, rdi
0x180103db1  mov     rax, [rax+28h]
0x180103db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103dba  mov     ebx, eax
0x180103dbc  test    eax, eax
0x180103dbe  jz      short loc_180103DC5
0x180103dc0  cmp     eax, 7
0x180103dc3  jnz     short loc_180103DE1
0x180103dc5  mov     rax, [rdi]
0x180103dc8  mov     rdx, r12
0x180103dcb  mov     rcx, rdi
0x180103dce  mov     rax, [rax+38h]
0x180103dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103dd7  jmp     loc_180103C88
0x180103ddc  mov     ebx, 4
0x180103de1  mov     rax, [rdi]
0x180103de4  mov     edx, 1
0x180103de9  mov     rcx, rdi
0x180103dec  mov     rax, [rax]
0x180103def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103df4  test    r15, r15
0x180103df7  jz      short loc_180103E06
0x180103df9  mov     edx, 10h
0x180103dfe  mov     rcx, r15; Block
0x180103e01  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180103e06  mov     rcx, [rbp+TokenHandle]; hObject
0x180103e0a  test    rcx, rcx
0x180103e0d  jz      short loc_180103E1B
0x180103e0f  call    cs:__imp_CloseHandle
0x180103e16  nop     dword ptr [rax+rax+00h]
0x180103e1b  test    r14, r14
0x180103e1e  jz      short loc_180103E2F
0x180103e20  mov     rcx, r14; pwk
0x180103e23  call    cs:__imp_CloseThreadpoolWork
0x180103e2a  nop     dword ptr [rax+rax+00h]
0x180103e2f  mov     eax, ebx
0x180103e31  mov     rcx, [rbp+var_8]
0x180103e35  xor     rcx, rsp; StackCookie
0x180103e38  call    __security_check_cookie
0x180103e3d  mov     rbx, [rsp+80h+arg_18]
0x180103e45  add     rsp, 80h
0x180103e4c  pop     r15
0x180103e4e  pop     r14
0x180103e50  pop     r13
0x180103e52  pop     r12
0x180103e54  pop     rdi
0x180103e55  pop     rsi
0x180103e56  pop     rbp
0x180103e57  retn
```
