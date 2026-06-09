# CSpWmiMethod<_SPACES_StorageEnclosure_GetVendorData>::RunMethod<CSpStorageEnclosure::GetVendorData,8>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800d91ec`
- end: `0x1800d9569`
- name: `??$RunMethod@VGetVendorData@CSpStorageEnclosure@@$07@?$CSpWmiMethod@U_SPACES_StorageEnclosure_GetVendorData@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800d91ec`
- `0x1800da3f8`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d93ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d93ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d939f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d939f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d93ba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d93ba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d937f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d937f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d9474`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d9474`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d9533`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d9533`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d951f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d951f`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageEnclosure_GetVendorData>::RunMethod<CSpStorageEnclosure::GetVendorData,8>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 VendorData; // rax
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
  CSpStorageEnclosure::GetVendorData *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageEnclosure::GetVendorData *)operator new(0x168u);
  VendorData = CSpStorageEnclosure::GetVendorData::GetVendorData(v25);
  v8 = VendorData;
  if ( VendorData )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)VendorData + 8LL))(VendorData, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageEnclosure::GetVendorData *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_180336186,
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
0x1800d91ec  mov     [rsp-38h+arg_18], rbx
0x1800d91f1  push    rbp
0x1800d91f2  push    rsi
0x1800d91f3  push    rdi
0x1800d91f4  push    r12
0x1800d91f6  push    r13
0x1800d91f8  push    r14
0x1800d91fa  push    r15
0x1800d91fc  mov     rbp, rsp
0x1800d91ff  sub     rsp, 80h
0x1800d9206  mov     rax, cs:__security_cookie
0x1800d920d  xor     rax, rsp
0x1800d9210  mov     [rbp+var_8], rax
0x1800d9214  xor     eax, eax
0x1800d9216  mov     rsi, rcx
0x1800d9219  xorps   xmm0, xmm0
0x1800d921c  mov     [rbp+var_10], eax
0x1800d921f  mov     ecx, 168h; Size
0x1800d9224  mov     [rbp+var_40], eax
0x1800d9227  movups  [rbp+var_20], xmm0
0x1800d922b  mov     [rbp+TokenHandle], rax
0x1800d922f  mov     r12, r8
0x1800d9232  mov     r13, rdx
0x1800d9235  xor     r14d, r14d
0x1800d9238  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d923d  mov     rcx, rax; this
0x1800d9240  mov     [rbp+var_28], rax
0x1800d9244  call    ??0GetVendorData@CSpStorageEnclosure@@QEAA@XZ; CSpStorageEnclosure::GetVendorData::GetVendorData(void)
0x1800d9249  mov     rdi, rax
0x1800d924c  test    rax, rax
0x1800d924f  jnz     short loc_1800D9259
0x1800d9251  lea     ebx, [rax+1Bh]
0x1800d9254  jmp     loc_1800D9516
0x1800d9259  mov     rax, [rax]
0x1800d925c  mov     rdx, rsi
0x1800d925f  mov     rcx, rdi
0x1800d9262  xor     r15d, r15d
0x1800d9265  mov     rax, [rax+8]
0x1800d9269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d926e  lea     rcx, [rbp+var_40]
0x1800d9272  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800d9277  mov     [rdi+1Ch], eax
0x1800d927a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800d927e  mov     ecx, [rsi+14h]; unsigned int
0x1800d9281  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800d9286  mov     eax, cs:dword_18039EB68
0x1800d928c  cmp     eax, 5
0x1800d928f  jbe     short loc_1800D92FF
0x1800d9291  mov     rdx, 400000000000h
0x1800d929b  lea     rcx, dword_18039EB68
0x1800d92a2  call    _tlgKeywordOn
0x1800d92a7  test    al, al
0x1800d92a9  jz      short loc_1800D92FF
0x1800d92ab  mov     eax, [rbp+var_40]
0x1800d92ae  lea     rdx, word_180336186
0x1800d92b5  xor     ecx, ecx
0x1800d92b7  cmp     [rdi+1Ch], eax
0x1800d92ba  movzx   eax, word ptr [rbp+var_10]
0x1800d92be  mov     word ptr [rbp+var_40], ax
0x1800d92c2  setnz   cl
0x1800d92c5  mov     eax, [rsi+14h]
0x1800d92c8  mov     [rbp+var_38], eax
0x1800d92cb  lea     rax, [rbp+var_20]
0x1800d92cf  mov     [rbp+var_28], rax
0x1800d92d3  lea     rax, [rbp+var_3C]
0x1800d92d7  mov     [rsp+80h+var_48], rax
0x1800d92dc  lea     rax, [rbp+var_40]
0x1800d92e0  mov     [rsp+80h+var_50], rax
0x1800d92e5  lea     rax, [rbp+var_38]
0x1800d92e9  mov     [rsp+80h+var_58], rax
0x1800d92ee  lea     rax, [rbp+var_28]
0x1800d92f2  mov     [rsp+80h+var_60], rax
0x1800d92f7  mov     [rbp+var_3C], ecx
0x1800d92fa  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800d92ff  mov     rcx, [rsi]
0x1800d9302  test    rcx, rcx
0x1800d9305  jz      loc_1800D94EC
0x1800d930b  mov     rax, [rcx]
0x1800d930e  test    rax, rax
0x1800d9311  jz      loc_1800D94EC
0x1800d9317  mov     rax, [rax+18h]
0x1800d931b  lea     r8, [rdi+20h]
0x1800d931f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800d9326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d932b  mov     ebx, eax
0x1800d932d  test    eax, eax
0x1800d932f  jnz     loc_1800D94F1
0x1800d9335  cmp     [rsi+10h], r14d
0x1800d9339  jz      loc_1800D9485
0x1800d933f  lea     rbx, [rdi+148h]
0x1800d9346  mov     rcx, rbx
0x1800d9349  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800d934e  mov     rcx, rbx; struct CSpJobMgr **
0x1800d9351  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800d9356  test    eax, eax
0x1800d9358  jnz     short loc_1800D9362
0x1800d935a  lea     ebx, [rax+1Ch]
0x1800d935d  jmp     loc_1800D94F1
0x1800d9362  mov     ecx, 10h; Size
0x1800d9367  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d936c  xor     r8d, r8d; pcbe
0x1800d936f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800d9376  mov     rdx, rax; pv
0x1800d9379  mov     r15, rax
0x1800d937c  mov     [rax], rdi
0x1800d937f  call    cs:__imp_CreateThreadpoolWork
0x1800d9386  nop     dword ptr [rax+rax+00h]
0x1800d938b  mov     r14, rax
0x1800d938e  test    rax, rax
0x1800d9391  jnz     short loc_1800D939F
0x1800d9393  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800d9398  mov     ebx, eax
0x1800d939a  jmp     loc_1800D94F1
0x1800d939f  call    cs:__imp_GetCurrentThread
0x1800d93a6  nop     dword ptr [rax+rax+00h]
0x1800d93ab  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d93af  xor     r8d, r8d; OpenAsSelf
0x1800d93b2  mov     rcx, rax; ThreadHandle
0x1800d93b5  mov     edx, 2000Ch; DesiredAccess
0x1800d93ba  call    cs:__imp_OpenThreadToken
0x1800d93c1  nop     dword ptr [rax+rax+00h]
0x1800d93c6  test    eax, eax
0x1800d93c8  jnz     short loc_1800D93DD
0x1800d93ca  call    cs:__imp_GetLastError
0x1800d93d1  nop     dword ptr [rax+rax+00h]
0x1800d93d6  cmp     eax, 3F0h
0x1800d93db  jnz     short loc_1800D9393
0x1800d93dd  mov     rax, [rbp+TokenHandle]
0x1800d93e1  mov     r8, r13
0x1800d93e4  mov     [r15+8], rax
0x1800d93e8  mov     rcx, rdi
0x1800d93eb  mov     rax, [rdi]
0x1800d93ee  mov     rdx, [rsi+8]
0x1800d93f2  mov     rax, [rax+18h]
0x1800d93f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d93fb  mov     rax, [rdi]
0x1800d93fe  mov     rdx, r12
0x1800d9401  mov     rcx, rdi
0x1800d9404  mov     rax, [rax+28h]
0x1800d9408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d940d  mov     ebx, eax
0x1800d940f  test    eax, eax
0x1800d9411  jz      short loc_1800D941C
0x1800d9413  cmp     eax, 7
0x1800d9416  jnz     loc_1800D94F1
0x1800d941c  mov     rax, [rdi]
0x1800d941f  mov     rdx, r12
0x1800d9422  mov     rcx, rdi
0x1800d9425  mov     rax, [rax+38h]
0x1800d9429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d942e  mov     ebx, eax
0x1800d9430  test    eax, eax
0x1800d9432  jnz     loc_1800D94F1
0x1800d9438  mov     rax, [rdi+150h]
0x1800d943f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800d9446  jnz     short loc_1800D945C
0x1800d9448  mov     rax, [rdi+158h]
0x1800d944f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800d9456  jz      loc_1800D94F1
0x1800d945c  mov     rdx, r12
0x1800d945f  mov     rcx, rdi
0x1800d9462  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800d9467  mov     ebx, eax
0x1800d9469  test    eax, eax
0x1800d946b  jnz     loc_1800D94F1
0x1800d9471  mov     rcx, r14; pwk
0x1800d9474  call    cs:__imp_SubmitThreadpoolWork
0x1800d947b  nop     dword ptr [rax+rax+00h]
0x1800d9480  jmp     loc_1800D953F
0x1800d9485  mov     rax, [rdi]
0x1800d9488  mov     r8, r13
0x1800d948b  mov     rdx, [rsi+8]
0x1800d948f  mov     rcx, rdi
0x1800d9492  mov     rax, [rax+10h]
0x1800d9496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d949b  mov     rax, [rdi]
0x1800d949e  mov     rdx, r12
0x1800d94a1  mov     rcx, rdi
0x1800d94a4  mov     rax, [rax+30h]
0x1800d94a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d94ad  mov     ebx, eax
0x1800d94af  test    eax, eax
0x1800d94b1  jz      short loc_1800D94B8
0x1800d94b3  cmp     eax, 7
0x1800d94b6  jnz     short loc_1800D94F1
0x1800d94b8  mov     rax, [rdi]
0x1800d94bb  mov     rdx, r12
0x1800d94be  mov     rcx, rdi
0x1800d94c1  mov     rax, [rax+28h]
0x1800d94c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d94ca  mov     ebx, eax
0x1800d94cc  test    eax, eax
0x1800d94ce  jz      short loc_1800D94D5
0x1800d94d0  cmp     eax, 7
0x1800d94d3  jnz     short loc_1800D94F1
0x1800d94d5  mov     rax, [rdi]
0x1800d94d8  mov     rdx, r12
0x1800d94db  mov     rcx, rdi
0x1800d94de  mov     rax, [rax+38h]
0x1800d94e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d94e7  jmp     loc_1800D9398
0x1800d94ec  mov     ebx, 4
0x1800d94f1  mov     rax, [rdi]
0x1800d94f4  mov     edx, 1
0x1800d94f9  mov     rcx, rdi
0x1800d94fc  mov     rax, [rax]
0x1800d94ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9504  test    r15, r15
0x1800d9507  jz      short loc_1800D9516
0x1800d9509  mov     edx, 10h
0x1800d950e  mov     rcx, r15; Block
0x1800d9511  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d9516  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d951a  test    rcx, rcx
0x1800d951d  jz      short loc_1800D952B
0x1800d951f  call    cs:__imp_CloseHandle
0x1800d9526  nop     dword ptr [rax+rax+00h]
0x1800d952b  test    r14, r14
0x1800d952e  jz      short loc_1800D953F
0x1800d9530  mov     rcx, r14; pwk
0x1800d9533  call    cs:__imp_CloseThreadpoolWork
0x1800d953a  nop     dword ptr [rax+rax+00h]
0x1800d953f  mov     eax, ebx
0x1800d9541  mov     rcx, [rbp+var_8]
0x1800d9545  xor     rcx, rsp; StackCookie
0x1800d9548  call    __security_check_cookie
0x1800d954d  mov     rbx, [rsp+80h+arg_18]
0x1800d9555  add     rsp, 80h
0x1800d955c  pop     r15
0x1800d955e  pop     r14
0x1800d9560  pop     r13
0x1800d9562  pop     r12
0x1800d9564  pop     rdi
0x1800d9565  pop     rsi
0x1800d9566  pop     rbp
0x1800d9567  retn
```
