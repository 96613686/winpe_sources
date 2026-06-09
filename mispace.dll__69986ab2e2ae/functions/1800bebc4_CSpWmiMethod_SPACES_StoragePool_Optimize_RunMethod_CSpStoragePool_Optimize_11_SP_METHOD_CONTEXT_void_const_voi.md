# CSpWmiMethod<_SPACES_StoragePool_Optimize>::RunMethod<CSpStoragePool::Optimize,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bebc4`
- end: `0x1800bef41`
- name: `??$RunMethod@VOptimize@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_Optimize@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800bebc4`
- `0x1800c10c4`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800beda2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800beda2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bed77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bed77`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bed92`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bed92`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bed57`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bed57`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bee4c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bee4c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bef0b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bef0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800beef7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800beef7`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_Optimize>::RunMethod<CSpStoragePool::Optimize,11>(
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
  CSpStoragePool::Optimize *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::Optimize *)operator new(0x168u);
  v7 = CSpStoragePool::Optimize::Optimize(v25);
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
      v25 = (CSpStoragePool::Optimize *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18033351D,
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
0x1800bebc4  mov     [rsp-38h+arg_18], rbx
0x1800bebc9  push    rbp
0x1800bebca  push    rsi
0x1800bebcb  push    rdi
0x1800bebcc  push    r12
0x1800bebce  push    r13
0x1800bebd0  push    r14
0x1800bebd2  push    r15
0x1800bebd4  mov     rbp, rsp
0x1800bebd7  sub     rsp, 80h
0x1800bebde  mov     rax, cs:__security_cookie
0x1800bebe5  xor     rax, rsp
0x1800bebe8  mov     [rbp+var_8], rax
0x1800bebec  xor     eax, eax
0x1800bebee  mov     rsi, rcx
0x1800bebf1  xorps   xmm0, xmm0
0x1800bebf4  mov     [rbp+var_10], eax
0x1800bebf7  mov     ecx, 168h; Size
0x1800bebfc  mov     [rbp+var_40], eax
0x1800bebff  movups  [rbp+var_20], xmm0
0x1800bec03  mov     [rbp+TokenHandle], rax
0x1800bec07  mov     r12, r8
0x1800bec0a  mov     r13, rdx
0x1800bec0d  xor     r14d, r14d
0x1800bec10  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bec15  mov     rcx, rax; this
0x1800bec18  mov     [rbp+var_28], rax
0x1800bec1c  call    ??0Optimize@CSpStoragePool@@QEAA@XZ; CSpStoragePool::Optimize::Optimize(void)
0x1800bec21  mov     rdi, rax
0x1800bec24  test    rax, rax
0x1800bec27  jnz     short loc_1800BEC31
0x1800bec29  lea     ebx, [rax+1Bh]
0x1800bec2c  jmp     loc_1800BEEEE
0x1800bec31  mov     rax, [rax]
0x1800bec34  mov     rdx, rsi
0x1800bec37  mov     rcx, rdi
0x1800bec3a  xor     r15d, r15d
0x1800bec3d  mov     rax, [rax+8]
0x1800bec41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bec46  lea     rcx, [rbp+var_40]
0x1800bec4a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bec4f  mov     [rdi+1Ch], eax
0x1800bec52  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bec56  mov     ecx, [rsi+14h]; unsigned int
0x1800bec59  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bec5e  mov     eax, cs:dword_18039EB68
0x1800bec64  cmp     eax, 5
0x1800bec67  jbe     short loc_1800BECD7
0x1800bec69  mov     rdx, 400000000000h
0x1800bec73  lea     rcx, dword_18039EB68
0x1800bec7a  call    _tlgKeywordOn
0x1800bec7f  test    al, al
0x1800bec81  jz      short loc_1800BECD7
0x1800bec83  mov     eax, [rbp+var_40]
0x1800bec86  lea     rdx, byte_18033351D
0x1800bec8d  xor     ecx, ecx
0x1800bec8f  cmp     [rdi+1Ch], eax
0x1800bec92  movzx   eax, word ptr [rbp+var_10]
0x1800bec96  mov     word ptr [rbp+var_40], ax
0x1800bec9a  setnz   cl
0x1800bec9d  mov     eax, [rsi+14h]
0x1800beca0  mov     [rbp+var_38], eax
0x1800beca3  lea     rax, [rbp+var_20]
0x1800beca7  mov     [rbp+var_28], rax
0x1800becab  lea     rax, [rbp+var_3C]
0x1800becaf  mov     [rsp+80h+var_48], rax
0x1800becb4  lea     rax, [rbp+var_40]
0x1800becb8  mov     [rsp+80h+var_50], rax
0x1800becbd  lea     rax, [rbp+var_38]
0x1800becc1  mov     [rsp+80h+var_58], rax
0x1800becc6  lea     rax, [rbp+var_28]
0x1800becca  mov     [rsp+80h+var_60], rax
0x1800beccf  mov     [rbp+var_3C], ecx
0x1800becd2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800becd7  mov     rcx, [rsi]
0x1800becda  test    rcx, rcx
0x1800becdd  jz      loc_1800BEEC4
0x1800bece3  mov     rax, [rcx]
0x1800bece6  test    rax, rax
0x1800bece9  jz      loc_1800BEEC4
0x1800becef  mov     rax, [rax+18h]
0x1800becf3  lea     r8, [rdi+20h]
0x1800becf7  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800becfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bed03  mov     ebx, eax
0x1800bed05  test    eax, eax
0x1800bed07  jnz     loc_1800BEEC9
0x1800bed0d  cmp     [rsi+10h], r14d
0x1800bed11  jz      loc_1800BEE5D
0x1800bed17  lea     rbx, [rdi+148h]
0x1800bed1e  mov     rcx, rbx
0x1800bed21  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bed26  mov     rcx, rbx; struct CSpJobMgr **
0x1800bed29  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bed2e  test    eax, eax
0x1800bed30  jnz     short loc_1800BED3A
0x1800bed32  lea     ebx, [rax+1Ch]
0x1800bed35  jmp     loc_1800BEEC9
0x1800bed3a  mov     ecx, 10h; Size
0x1800bed3f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bed44  xor     r8d, r8d; pcbe
0x1800bed47  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bed4e  mov     rdx, rax; pv
0x1800bed51  mov     r15, rax
0x1800bed54  mov     [rax], rdi
0x1800bed57  call    cs:__imp_CreateThreadpoolWork
0x1800bed5e  nop     dword ptr [rax+rax+00h]
0x1800bed63  mov     r14, rax
0x1800bed66  test    rax, rax
0x1800bed69  jnz     short loc_1800BED77
0x1800bed6b  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bed70  mov     ebx, eax
0x1800bed72  jmp     loc_1800BEEC9
0x1800bed77  call    cs:__imp_GetCurrentThread
0x1800bed7e  nop     dword ptr [rax+rax+00h]
0x1800bed83  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bed87  xor     r8d, r8d; OpenAsSelf
0x1800bed8a  mov     rcx, rax; ThreadHandle
0x1800bed8d  mov     edx, 2000Ch; DesiredAccess
0x1800bed92  call    cs:__imp_OpenThreadToken
0x1800bed99  nop     dword ptr [rax+rax+00h]
0x1800bed9e  test    eax, eax
0x1800beda0  jnz     short loc_1800BEDB5
0x1800beda2  call    cs:__imp_GetLastError
0x1800beda9  nop     dword ptr [rax+rax+00h]
0x1800bedae  cmp     eax, 3F0h
0x1800bedb3  jnz     short loc_1800BED6B
0x1800bedb5  mov     rax, [rbp+TokenHandle]
0x1800bedb9  mov     r8, r13
0x1800bedbc  mov     [r15+8], rax
0x1800bedc0  mov     rcx, rdi
0x1800bedc3  mov     rax, [rdi]
0x1800bedc6  mov     rdx, [rsi+8]
0x1800bedca  mov     rax, [rax+18h]
0x1800bedce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bedd3  mov     rax, [rdi]
0x1800bedd6  mov     rdx, r12
0x1800bedd9  mov     rcx, rdi
0x1800beddc  mov     rax, [rax+28h]
0x1800bede0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bede5  mov     ebx, eax
0x1800bede7  test    eax, eax
0x1800bede9  jz      short loc_1800BEDF4
0x1800bedeb  cmp     eax, 7
0x1800bedee  jnz     loc_1800BEEC9
0x1800bedf4  mov     rax, [rdi]
0x1800bedf7  mov     rdx, r12
0x1800bedfa  mov     rcx, rdi
0x1800bedfd  mov     rax, [rax+38h]
0x1800bee01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bee06  mov     ebx, eax
0x1800bee08  test    eax, eax
0x1800bee0a  jnz     loc_1800BEEC9
0x1800bee10  mov     rax, [rdi+150h]
0x1800bee17  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bee1e  jnz     short loc_1800BEE34
0x1800bee20  mov     rax, [rdi+158h]
0x1800bee27  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bee2e  jz      loc_1800BEEC9
0x1800bee34  mov     rdx, r12
0x1800bee37  mov     rcx, rdi
0x1800bee3a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bee3f  mov     ebx, eax
0x1800bee41  test    eax, eax
0x1800bee43  jnz     loc_1800BEEC9
0x1800bee49  mov     rcx, r14; pwk
0x1800bee4c  call    cs:__imp_SubmitThreadpoolWork
0x1800bee53  nop     dword ptr [rax+rax+00h]
0x1800bee58  jmp     loc_1800BEF17
0x1800bee5d  mov     rax, [rdi]
0x1800bee60  mov     r8, r13
0x1800bee63  mov     rdx, [rsi+8]
0x1800bee67  mov     rcx, rdi
0x1800bee6a  mov     rax, [rax+10h]
0x1800bee6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bee73  mov     rax, [rdi]
0x1800bee76  mov     rdx, r12
0x1800bee79  mov     rcx, rdi
0x1800bee7c  mov     rax, [rax+30h]
0x1800bee80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bee85  mov     ebx, eax
0x1800bee87  test    eax, eax
0x1800bee89  jz      short loc_1800BEE90
0x1800bee8b  cmp     eax, 7
0x1800bee8e  jnz     short loc_1800BEEC9
0x1800bee90  mov     rax, [rdi]
0x1800bee93  mov     rdx, r12
0x1800bee96  mov     rcx, rdi
0x1800bee99  mov     rax, [rax+28h]
0x1800bee9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beea2  mov     ebx, eax
0x1800beea4  test    eax, eax
0x1800beea6  jz      short loc_1800BEEAD
0x1800beea8  cmp     eax, 7
0x1800beeab  jnz     short loc_1800BEEC9
0x1800beead  mov     rax, [rdi]
0x1800beeb0  mov     rdx, r12
0x1800beeb3  mov     rcx, rdi
0x1800beeb6  mov     rax, [rax+38h]
0x1800beeba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beebf  jmp     loc_1800BED70
0x1800beec4  mov     ebx, 4
0x1800beec9  mov     rax, [rdi]
0x1800beecc  mov     edx, 1
0x1800beed1  mov     rcx, rdi
0x1800beed4  mov     rax, [rax]
0x1800beed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beedc  test    r15, r15
0x1800beedf  jz      short loc_1800BEEEE
0x1800beee1  mov     edx, 10h
0x1800beee6  mov     rcx, r15; Block
0x1800beee9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800beeee  mov     rcx, [rbp+TokenHandle]; hObject
0x1800beef2  test    rcx, rcx
0x1800beef5  jz      short loc_1800BEF03
0x1800beef7  call    cs:__imp_CloseHandle
0x1800beefe  nop     dword ptr [rax+rax+00h]
0x1800bef03  test    r14, r14
0x1800bef06  jz      short loc_1800BEF17
0x1800bef08  mov     rcx, r14; pwk
0x1800bef0b  call    cs:__imp_CloseThreadpoolWork
0x1800bef12  nop     dword ptr [rax+rax+00h]
0x1800bef17  mov     eax, ebx
0x1800bef19  mov     rcx, [rbp+var_8]
0x1800bef1d  xor     rcx, rsp; StackCookie
0x1800bef20  call    __security_check_cookie
0x1800bef25  mov     rbx, [rsp+80h+arg_18]
0x1800bef2d  add     rsp, 80h
0x1800bef34  pop     r15
0x1800bef36  pop     r14
0x1800bef38  pop     r13
0x1800bef3a  pop     r12
0x1800bef3c  pop     rdi
0x1800bef3d  pop     rsi
0x1800bef3e  pop     rbp
0x1800bef3f  retn
```
