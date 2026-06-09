# CSpWmiMethod<_SPACES_PhysicalDisk_SetFriendlyName>::RunMethod<CSpPhysicalDisk::SetFriendlyName,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800f2f8c`
- end: `0x1800f3309`
- name: `??$RunMethod@VSetFriendlyName@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_SetFriendlyName@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800f77c0`

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
- `0x1800f2f8c`
- `0x1800f3dd8`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f316a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f316a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f313f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f313f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f315a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f315a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f311f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f311f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f3214`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f3214`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f32d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f32d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f32bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f32bf`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_SetFriendlyName>::RunMethod<CSpPhysicalDisk::SetFriendlyName,4>(
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
  CSpPhysicalDisk::SetFriendlyName *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::SetFriendlyName *)operator new(0x160u);
  v7 = CSpPhysicalDisk::SetFriendlyName::SetFriendlyName(v25);
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
      v25 = (CSpPhysicalDisk::SetFriendlyName *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_18033BE80,
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
0x1800f2f8c  mov     [rsp-38h+arg_18], rbx
0x1800f2f91  push    rbp
0x1800f2f92  push    rsi
0x1800f2f93  push    rdi
0x1800f2f94  push    r12
0x1800f2f96  push    r13
0x1800f2f98  push    r14
0x1800f2f9a  push    r15
0x1800f2f9c  mov     rbp, rsp
0x1800f2f9f  sub     rsp, 80h
0x1800f2fa6  mov     rax, cs:__security_cookie
0x1800f2fad  xor     rax, rsp
0x1800f2fb0  mov     [rbp+var_8], rax
0x1800f2fb4  xor     eax, eax
0x1800f2fb6  mov     rsi, rcx
0x1800f2fb9  xorps   xmm0, xmm0
0x1800f2fbc  mov     [rbp+var_10], eax
0x1800f2fbf  mov     ecx, 160h; Size
0x1800f2fc4  mov     [rbp+var_40], eax
0x1800f2fc7  movups  [rbp+var_20], xmm0
0x1800f2fcb  mov     [rbp+TokenHandle], rax
0x1800f2fcf  mov     r12, r8
0x1800f2fd2  mov     r13, rdx
0x1800f2fd5  xor     r14d, r14d
0x1800f2fd8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f2fdd  mov     rcx, rax; this
0x1800f2fe0  mov     [rbp+var_28], rax
0x1800f2fe4  call    ??0SetFriendlyName@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::SetFriendlyName::SetFriendlyName(void)
0x1800f2fe9  mov     rdi, rax
0x1800f2fec  test    rax, rax
0x1800f2fef  jnz     short loc_1800F2FF9
0x1800f2ff1  lea     ebx, [rax+1Bh]
0x1800f2ff4  jmp     loc_1800F32B6
0x1800f2ff9  mov     rax, [rax]
0x1800f2ffc  mov     rdx, rsi
0x1800f2fff  mov     rcx, rdi
0x1800f3002  xor     r15d, r15d
0x1800f3005  mov     rax, [rax+8]
0x1800f3009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f300e  lea     rcx, [rbp+var_40]
0x1800f3012  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800f3017  mov     [rdi+1Ch], eax
0x1800f301a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800f301e  mov     ecx, [rsi+14h]; unsigned int
0x1800f3021  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800f3026  mov     eax, cs:dword_18039EB68
0x1800f302c  cmp     eax, 5
0x1800f302f  jbe     short loc_1800F309F
0x1800f3031  mov     rdx, 400000000000h
0x1800f303b  lea     rcx, dword_18039EB68
0x1800f3042  call    _tlgKeywordOn
0x1800f3047  test    al, al
0x1800f3049  jz      short loc_1800F309F
0x1800f304b  mov     eax, [rbp+var_40]
0x1800f304e  lea     rdx, unk_18033BE80
0x1800f3055  xor     ecx, ecx
0x1800f3057  cmp     [rdi+1Ch], eax
0x1800f305a  movzx   eax, word ptr [rbp+var_10]
0x1800f305e  mov     word ptr [rbp+var_40], ax
0x1800f3062  setnz   cl
0x1800f3065  mov     eax, [rsi+14h]
0x1800f3068  mov     [rbp+var_38], eax
0x1800f306b  lea     rax, [rbp+var_20]
0x1800f306f  mov     [rbp+var_28], rax
0x1800f3073  lea     rax, [rbp+var_3C]
0x1800f3077  mov     [rsp+80h+var_48], rax
0x1800f307c  lea     rax, [rbp+var_40]
0x1800f3080  mov     [rsp+80h+var_50], rax
0x1800f3085  lea     rax, [rbp+var_38]
0x1800f3089  mov     [rsp+80h+var_58], rax
0x1800f308e  lea     rax, [rbp+var_28]
0x1800f3092  mov     [rsp+80h+var_60], rax
0x1800f3097  mov     [rbp+var_3C], ecx
0x1800f309a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800f309f  mov     rcx, [rsi]
0x1800f30a2  test    rcx, rcx
0x1800f30a5  jz      loc_1800F328C
0x1800f30ab  mov     rax, [rcx]
0x1800f30ae  test    rax, rax
0x1800f30b1  jz      loc_1800F328C
0x1800f30b7  mov     rax, [rax+18h]
0x1800f30bb  lea     r8, [rdi+20h]
0x1800f30bf  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800f30c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f30cb  mov     ebx, eax
0x1800f30cd  test    eax, eax
0x1800f30cf  jnz     loc_1800F3291
0x1800f30d5  cmp     [rsi+10h], r14d
0x1800f30d9  jz      loc_1800F3225
0x1800f30df  lea     rbx, [rdi+148h]
0x1800f30e6  mov     rcx, rbx
0x1800f30e9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800f30ee  mov     rcx, rbx; struct CSpJobMgr **
0x1800f30f1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800f30f6  test    eax, eax
0x1800f30f8  jnz     short loc_1800F3102
0x1800f30fa  lea     ebx, [rax+1Ch]
0x1800f30fd  jmp     loc_1800F3291
0x1800f3102  mov     ecx, 10h; Size
0x1800f3107  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f310c  xor     r8d, r8d; pcbe
0x1800f310f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f3116  mov     rdx, rax; pv
0x1800f3119  mov     r15, rax
0x1800f311c  mov     [rax], rdi
0x1800f311f  call    cs:__imp_CreateThreadpoolWork
0x1800f3126  nop     dword ptr [rax+rax+00h]
0x1800f312b  mov     r14, rax
0x1800f312e  test    rax, rax
0x1800f3131  jnz     short loc_1800F313F
0x1800f3133  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800f3138  mov     ebx, eax
0x1800f313a  jmp     loc_1800F3291
0x1800f313f  call    cs:__imp_GetCurrentThread
0x1800f3146  nop     dword ptr [rax+rax+00h]
0x1800f314b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f314f  xor     r8d, r8d; OpenAsSelf
0x1800f3152  mov     rcx, rax; ThreadHandle
0x1800f3155  mov     edx, 2000Ch; DesiredAccess
0x1800f315a  call    cs:__imp_OpenThreadToken
0x1800f3161  nop     dword ptr [rax+rax+00h]
0x1800f3166  test    eax, eax
0x1800f3168  jnz     short loc_1800F317D
0x1800f316a  call    cs:__imp_GetLastError
0x1800f3171  nop     dword ptr [rax+rax+00h]
0x1800f3176  cmp     eax, 3F0h
0x1800f317b  jnz     short loc_1800F3133
0x1800f317d  mov     rax, [rbp+TokenHandle]
0x1800f3181  mov     r8, r13
0x1800f3184  mov     [r15+8], rax
0x1800f3188  mov     rcx, rdi
0x1800f318b  mov     rax, [rdi]
0x1800f318e  mov     rdx, [rsi+8]
0x1800f3192  mov     rax, [rax+18h]
0x1800f3196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f319b  mov     rax, [rdi]
0x1800f319e  mov     rdx, r12
0x1800f31a1  mov     rcx, rdi
0x1800f31a4  mov     rax, [rax+28h]
0x1800f31a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f31ad  mov     ebx, eax
0x1800f31af  test    eax, eax
0x1800f31b1  jz      short loc_1800F31BC
0x1800f31b3  cmp     eax, 7
0x1800f31b6  jnz     loc_1800F3291
0x1800f31bc  mov     rax, [rdi]
0x1800f31bf  mov     rdx, r12
0x1800f31c2  mov     rcx, rdi
0x1800f31c5  mov     rax, [rax+38h]
0x1800f31c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f31ce  mov     ebx, eax
0x1800f31d0  test    eax, eax
0x1800f31d2  jnz     loc_1800F3291
0x1800f31d8  mov     rax, [rdi+150h]
0x1800f31df  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800f31e6  jnz     short loc_1800F31FC
0x1800f31e8  mov     rax, [rdi+158h]
0x1800f31ef  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800f31f6  jz      loc_1800F3291
0x1800f31fc  mov     rdx, r12
0x1800f31ff  mov     rcx, rdi
0x1800f3202  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800f3207  mov     ebx, eax
0x1800f3209  test    eax, eax
0x1800f320b  jnz     loc_1800F3291
0x1800f3211  mov     rcx, r14; pwk
0x1800f3214  call    cs:__imp_SubmitThreadpoolWork
0x1800f321b  nop     dword ptr [rax+rax+00h]
0x1800f3220  jmp     loc_1800F32DF
0x1800f3225  mov     rax, [rdi]
0x1800f3228  mov     r8, r13
0x1800f322b  mov     rdx, [rsi+8]
0x1800f322f  mov     rcx, rdi
0x1800f3232  mov     rax, [rax+10h]
0x1800f3236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f323b  mov     rax, [rdi]
0x1800f323e  mov     rdx, r12
0x1800f3241  mov     rcx, rdi
0x1800f3244  mov     rax, [rax+30h]
0x1800f3248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f324d  mov     ebx, eax
0x1800f324f  test    eax, eax
0x1800f3251  jz      short loc_1800F3258
0x1800f3253  cmp     eax, 7
0x1800f3256  jnz     short loc_1800F3291
0x1800f3258  mov     rax, [rdi]
0x1800f325b  mov     rdx, r12
0x1800f325e  mov     rcx, rdi
0x1800f3261  mov     rax, [rax+28h]
0x1800f3265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f326a  mov     ebx, eax
0x1800f326c  test    eax, eax
0x1800f326e  jz      short loc_1800F3275
0x1800f3270  cmp     eax, 7
0x1800f3273  jnz     short loc_1800F3291
0x1800f3275  mov     rax, [rdi]
0x1800f3278  mov     rdx, r12
0x1800f327b  mov     rcx, rdi
0x1800f327e  mov     rax, [rax+38h]
0x1800f3282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f3287  jmp     loc_1800F3138
0x1800f328c  mov     ebx, 4
0x1800f3291  mov     rax, [rdi]
0x1800f3294  mov     edx, 1
0x1800f3299  mov     rcx, rdi
0x1800f329c  mov     rax, [rax]
0x1800f329f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f32a4  test    r15, r15
0x1800f32a7  jz      short loc_1800F32B6
0x1800f32a9  mov     edx, 10h
0x1800f32ae  mov     rcx, r15; Block
0x1800f32b1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f32b6  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f32ba  test    rcx, rcx
0x1800f32bd  jz      short loc_1800F32CB
0x1800f32bf  call    cs:__imp_CloseHandle
0x1800f32c6  nop     dword ptr [rax+rax+00h]
0x1800f32cb  test    r14, r14
0x1800f32ce  jz      short loc_1800F32DF
0x1800f32d0  mov     rcx, r14; pwk
0x1800f32d3  call    cs:__imp_CloseThreadpoolWork
0x1800f32da  nop     dword ptr [rax+rax+00h]
0x1800f32df  mov     eax, ebx
0x1800f32e1  mov     rcx, [rbp+var_8]
0x1800f32e5  xor     rcx, rsp; StackCookie
0x1800f32e8  call    __security_check_cookie
0x1800f32ed  mov     rbx, [rsp+80h+arg_18]
0x1800f32f5  add     rsp, 80h
0x1800f32fc  pop     r15
0x1800f32fe  pop     r14
0x1800f3300  pop     r13
0x1800f3302  pop     r12
0x1800f3304  pop     rdi
0x1800f3305  pop     rsi
0x1800f3306  pop     rbp
0x1800f3307  retn
```
