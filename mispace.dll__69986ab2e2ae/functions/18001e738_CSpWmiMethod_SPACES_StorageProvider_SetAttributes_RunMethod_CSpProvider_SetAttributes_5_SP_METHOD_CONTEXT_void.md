# CSpWmiMethod<_SPACES_StorageProvider_SetAttributes>::RunMethod<CSpProvider::SetAttributes,5>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18001e738`
- end: `0x18001eab5`
- name: `??$RunMethod@VSetAttributes@CSpProvider@@$04@?$CSpWmiMethod@U_SPACES_StorageProvider_SetAttributes@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180023030`

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
- `0x18001e738`
- `0x18001f258`
- `0x1800257fc`
- `0x18005f41c`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e916`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e8eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e8eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e906`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e906`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001e8cb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001e8cb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e9c0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e9c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001ea7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001ea7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea6b`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageProvider_SetAttributes>::RunMethod<CSpProvider::SetAttributes,5>(
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
  CSpProvider::SetAttributes *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpProvider::SetAttributes *)operator new(0x160u);
  v7 = CSpProvider::SetAttributes::SetAttributes(v25);
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
      v25 = (CSpProvider::SetAttributes *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_1802FB679,
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
0x18001e738  mov     [rsp-38h+arg_18], rbx
0x18001e73d  push    rbp
0x18001e73e  push    rsi
0x18001e73f  push    rdi
0x18001e740  push    r12
0x18001e742  push    r13
0x18001e744  push    r14
0x18001e746  push    r15
0x18001e748  mov     rbp, rsp
0x18001e74b  sub     rsp, 80h
0x18001e752  mov     rax, cs:__security_cookie
0x18001e759  xor     rax, rsp
0x18001e75c  mov     [rbp+var_8], rax
0x18001e760  xor     eax, eax
0x18001e762  mov     rsi, rcx
0x18001e765  xorps   xmm0, xmm0
0x18001e768  mov     [rbp+var_10], eax
0x18001e76b  mov     ecx, 160h; Size
0x18001e770  mov     [rbp+var_40], eax
0x18001e773  movups  [rbp+var_20], xmm0
0x18001e777  mov     [rbp+TokenHandle], rax
0x18001e77b  mov     r12, r8
0x18001e77e  mov     r13, rdx
0x18001e781  xor     r14d, r14d
0x18001e784  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e789  mov     rcx, rax; this
0x18001e78c  mov     [rbp+var_28], rax
0x18001e790  call    ??0SetAttributes@CSpProvider@@QEAA@XZ; CSpProvider::SetAttributes::SetAttributes(void)
0x18001e795  mov     rdi, rax
0x18001e798  test    rax, rax
0x18001e79b  jnz     short loc_18001E7A5
0x18001e79d  lea     ebx, [rax+1Bh]
0x18001e7a0  jmp     loc_18001EA62
0x18001e7a5  mov     rax, [rax]
0x18001e7a8  mov     rdx, rsi
0x18001e7ab  mov     rcx, rdi
0x18001e7ae  xor     r15d, r15d
0x18001e7b1  mov     rax, [rax+8]
0x18001e7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7ba  lea     rcx, [rbp+var_40]
0x18001e7be  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18001e7c3  mov     [rdi+1Ch], eax
0x18001e7c6  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18001e7ca  mov     ecx, [rsi+14h]; unsigned int
0x18001e7cd  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18001e7d2  mov     eax, cs:dword_18039EB68
0x18001e7d8  cmp     eax, 5
0x18001e7db  jbe     short loc_18001E84B
0x18001e7dd  mov     rdx, 400000000000h
0x18001e7e7  lea     rcx, dword_18039EB68
0x18001e7ee  call    _tlgKeywordOn
0x18001e7f3  test    al, al
0x18001e7f5  jz      short loc_18001E84B
0x18001e7f7  mov     eax, [rbp+var_40]
0x18001e7fa  lea     rdx, byte_1802FB679
0x18001e801  xor     ecx, ecx
0x18001e803  cmp     [rdi+1Ch], eax
0x18001e806  movzx   eax, word ptr [rbp+var_10]
0x18001e80a  mov     word ptr [rbp+var_40], ax
0x18001e80e  setnz   cl
0x18001e811  mov     eax, [rsi+14h]
0x18001e814  mov     [rbp+var_38], eax
0x18001e817  lea     rax, [rbp+var_20]
0x18001e81b  mov     [rbp+var_28], rax
0x18001e81f  lea     rax, [rbp+var_3C]
0x18001e823  mov     [rsp+80h+var_48], rax
0x18001e828  lea     rax, [rbp+var_40]
0x18001e82c  mov     [rsp+80h+var_50], rax
0x18001e831  lea     rax, [rbp+var_38]
0x18001e835  mov     [rsp+80h+var_58], rax
0x18001e83a  lea     rax, [rbp+var_28]
0x18001e83e  mov     [rsp+80h+var_60], rax
0x18001e843  mov     [rbp+var_3C], ecx
0x18001e846  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18001e84b  mov     rcx, [rsi]
0x18001e84e  test    rcx, rcx
0x18001e851  jz      loc_18001EA38
0x18001e857  mov     rax, [rcx]
0x18001e85a  test    rax, rax
0x18001e85d  jz      loc_18001EA38
0x18001e863  mov     rax, [rax+18h]
0x18001e867  lea     r8, [rdi+20h]
0x18001e86b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18001e872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e877  mov     ebx, eax
0x18001e879  test    eax, eax
0x18001e87b  jnz     loc_18001EA3D
0x18001e881  cmp     [rsi+10h], r14d
0x18001e885  jz      loc_18001E9D1
0x18001e88b  lea     rbx, [rdi+148h]
0x18001e892  mov     rcx, rbx
0x18001e895  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18001e89a  mov     rcx, rbx; struct CSpJobMgr **
0x18001e89d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18001e8a2  test    eax, eax
0x18001e8a4  jnz     short loc_18001E8AE
0x18001e8a6  lea     ebx, [rax+1Ch]
0x18001e8a9  jmp     loc_18001EA3D
0x18001e8ae  mov     ecx, 10h; Size
0x18001e8b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e8b8  xor     r8d, r8d; pcbe
0x18001e8bb  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001e8c2  mov     rdx, rax; pv
0x18001e8c5  mov     r15, rax
0x18001e8c8  mov     [rax], rdi
0x18001e8cb  call    cs:__imp_CreateThreadpoolWork
0x18001e8d2  nop     dword ptr [rax+rax+00h]
0x18001e8d7  mov     r14, rax
0x18001e8da  test    rax, rax
0x18001e8dd  jnz     short loc_18001E8EB
0x18001e8df  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18001e8e4  mov     ebx, eax
0x18001e8e6  jmp     loc_18001EA3D
0x18001e8eb  call    cs:__imp_GetCurrentThread
0x18001e8f2  nop     dword ptr [rax+rax+00h]
0x18001e8f7  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001e8fb  xor     r8d, r8d; OpenAsSelf
0x18001e8fe  mov     rcx, rax; ThreadHandle
0x18001e901  mov     edx, 2000Ch; DesiredAccess
0x18001e906  call    cs:__imp_OpenThreadToken
0x18001e90d  nop     dword ptr [rax+rax+00h]
0x18001e912  test    eax, eax
0x18001e914  jnz     short loc_18001E929
0x18001e916  call    cs:__imp_GetLastError
0x18001e91d  nop     dword ptr [rax+rax+00h]
0x18001e922  cmp     eax, 3F0h
0x18001e927  jnz     short loc_18001E8DF
0x18001e929  mov     rax, [rbp+TokenHandle]
0x18001e92d  mov     r8, r13
0x18001e930  mov     [r15+8], rax
0x18001e934  mov     rcx, rdi
0x18001e937  mov     rax, [rdi]
0x18001e93a  mov     rdx, [rsi+8]
0x18001e93e  mov     rax, [rax+18h]
0x18001e942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e947  mov     rax, [rdi]
0x18001e94a  mov     rdx, r12
0x18001e94d  mov     rcx, rdi
0x18001e950  mov     rax, [rax+28h]
0x18001e954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e959  mov     ebx, eax
0x18001e95b  test    eax, eax
0x18001e95d  jz      short loc_18001E968
0x18001e95f  cmp     eax, 7
0x18001e962  jnz     loc_18001EA3D
0x18001e968  mov     rax, [rdi]
0x18001e96b  mov     rdx, r12
0x18001e96e  mov     rcx, rdi
0x18001e971  mov     rax, [rax+38h]
0x18001e975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e97a  mov     ebx, eax
0x18001e97c  test    eax, eax
0x18001e97e  jnz     loc_18001EA3D
0x18001e984  mov     rax, [rdi+150h]
0x18001e98b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18001e992  jnz     short loc_18001E9A8
0x18001e994  mov     rax, [rdi+158h]
0x18001e99b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18001e9a2  jz      loc_18001EA3D
0x18001e9a8  mov     rdx, r12
0x18001e9ab  mov     rcx, rdi
0x18001e9ae  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18001e9b3  mov     ebx, eax
0x18001e9b5  test    eax, eax
0x18001e9b7  jnz     loc_18001EA3D
0x18001e9bd  mov     rcx, r14; pwk
0x18001e9c0  call    cs:__imp_SubmitThreadpoolWork
0x18001e9c7  nop     dword ptr [rax+rax+00h]
0x18001e9cc  jmp     loc_18001EA8B
0x18001e9d1  mov     rax, [rdi]
0x18001e9d4  mov     r8, r13
0x18001e9d7  mov     rdx, [rsi+8]
0x18001e9db  mov     rcx, rdi
0x18001e9de  mov     rax, [rax+10h]
0x18001e9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9e7  mov     rax, [rdi]
0x18001e9ea  mov     rdx, r12
0x18001e9ed  mov     rcx, rdi
0x18001e9f0  mov     rax, [rax+30h]
0x18001e9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9f9  mov     ebx, eax
0x18001e9fb  test    eax, eax
0x18001e9fd  jz      short loc_18001EA04
0x18001e9ff  cmp     eax, 7
0x18001ea02  jnz     short loc_18001EA3D
0x18001ea04  mov     rax, [rdi]
0x18001ea07  mov     rdx, r12
0x18001ea0a  mov     rcx, rdi
0x18001ea0d  mov     rax, [rax+28h]
0x18001ea11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea16  mov     ebx, eax
0x18001ea18  test    eax, eax
0x18001ea1a  jz      short loc_18001EA21
0x18001ea1c  cmp     eax, 7
0x18001ea1f  jnz     short loc_18001EA3D
0x18001ea21  mov     rax, [rdi]
0x18001ea24  mov     rdx, r12
0x18001ea27  mov     rcx, rdi
0x18001ea2a  mov     rax, [rax+38h]
0x18001ea2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea33  jmp     loc_18001E8E4
0x18001ea38  mov     ebx, 4
0x18001ea3d  mov     rax, [rdi]
0x18001ea40  mov     edx, 1
0x18001ea45  mov     rcx, rdi
0x18001ea48  mov     rax, [rax]
0x18001ea4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea50  test    r15, r15
0x18001ea53  jz      short loc_18001EA62
0x18001ea55  mov     edx, 10h
0x18001ea5a  mov     rcx, r15; Block
0x18001ea5d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ea62  mov     rcx, [rbp+TokenHandle]; hObject
0x18001ea66  test    rcx, rcx
0x18001ea69  jz      short loc_18001EA77
0x18001ea6b  call    cs:__imp_CloseHandle
0x18001ea72  nop     dword ptr [rax+rax+00h]
0x18001ea77  test    r14, r14
0x18001ea7a  jz      short loc_18001EA8B
0x18001ea7c  mov     rcx, r14; pwk
0x18001ea7f  call    cs:__imp_CloseThreadpoolWork
0x18001ea86  nop     dword ptr [rax+rax+00h]
0x18001ea8b  mov     eax, ebx
0x18001ea8d  mov     rcx, [rbp+var_8]
0x18001ea91  xor     rcx, rsp; StackCookie
0x18001ea94  call    __security_check_cookie
0x18001ea99  mov     rbx, [rsp+80h+arg_18]
0x18001eaa1  add     rsp, 80h
0x18001eaa8  pop     r15
0x18001eaaa  pop     r14
0x18001eaac  pop     r13
0x18001eaae  pop     r12
0x18001eab0  pop     rdi
0x18001eab1  pop     rsi
0x18001eab2  pop     rbp
0x18001eab3  retn
```
