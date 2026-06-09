# CSpWmiMethod<_SPACES_VirtualDisk_Resize>::RunMethod<CSpVirtualDisk::Resize,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e2778`
- end: `0x1800e2af5`
- name: `??$RunMethod@VResize@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_Resize@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800e7d60`

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
- `0x1800e2778`
- `0x1800e411c`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e2956`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e292b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e292b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e2946`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e2946`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e290b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e290b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e2a00`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e2a00`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e2abf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e2abf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e2aab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e2aab`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_Resize>::RunMethod<CSpVirtualDisk::Resize,16>(
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
  CSpVirtualDisk::Resize *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::Resize *)operator new(0x160u);
  v7 = CSpVirtualDisk::Resize::Resize(v25);
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
      v25 = (CSpVirtualDisk::Resize *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_180338F3C,
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
0x1800e2778  mov     [rsp-38h+arg_18], rbx
0x1800e277d  push    rbp
0x1800e277e  push    rsi
0x1800e277f  push    rdi
0x1800e2780  push    r12
0x1800e2782  push    r13
0x1800e2784  push    r14
0x1800e2786  push    r15
0x1800e2788  mov     rbp, rsp
0x1800e278b  sub     rsp, 80h
0x1800e2792  mov     rax, cs:__security_cookie
0x1800e2799  xor     rax, rsp
0x1800e279c  mov     [rbp+var_8], rax
0x1800e27a0  xor     eax, eax
0x1800e27a2  mov     rsi, rcx
0x1800e27a5  xorps   xmm0, xmm0
0x1800e27a8  mov     [rbp+var_10], eax
0x1800e27ab  mov     ecx, 160h; Size
0x1800e27b0  mov     [rbp+var_40], eax
0x1800e27b3  movups  [rbp+var_20], xmm0
0x1800e27b7  mov     [rbp+TokenHandle], rax
0x1800e27bb  mov     r12, r8
0x1800e27be  mov     r13, rdx
0x1800e27c1  xor     r14d, r14d
0x1800e27c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e27c9  mov     rcx, rax; this
0x1800e27cc  mov     [rbp+var_28], rax
0x1800e27d0  call    ??0Resize@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::Resize::Resize(void)
0x1800e27d5  mov     rdi, rax
0x1800e27d8  test    rax, rax
0x1800e27db  jnz     short loc_1800E27E5
0x1800e27dd  lea     ebx, [rax+1Bh]
0x1800e27e0  jmp     loc_1800E2AA2
0x1800e27e5  mov     rax, [rax]
0x1800e27e8  mov     rdx, rsi
0x1800e27eb  mov     rcx, rdi
0x1800e27ee  xor     r15d, r15d
0x1800e27f1  mov     rax, [rax+8]
0x1800e27f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e27fa  lea     rcx, [rbp+var_40]
0x1800e27fe  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e2803  mov     [rdi+1Ch], eax
0x1800e2806  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e280a  mov     ecx, [rsi+14h]; unsigned int
0x1800e280d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e2812  mov     eax, cs:dword_18039EB68
0x1800e2818  cmp     eax, 5
0x1800e281b  jbe     short loc_1800E288B
0x1800e281d  mov     rdx, 400000000000h
0x1800e2827  lea     rcx, dword_18039EB68
0x1800e282e  call    _tlgKeywordOn
0x1800e2833  test    al, al
0x1800e2835  jz      short loc_1800E288B
0x1800e2837  mov     eax, [rbp+var_40]
0x1800e283a  lea     rdx, dword_180338F3C
0x1800e2841  xor     ecx, ecx
0x1800e2843  cmp     [rdi+1Ch], eax
0x1800e2846  movzx   eax, word ptr [rbp+var_10]
0x1800e284a  mov     word ptr [rbp+var_40], ax
0x1800e284e  setnz   cl
0x1800e2851  mov     eax, [rsi+14h]
0x1800e2854  mov     [rbp+var_38], eax
0x1800e2857  lea     rax, [rbp+var_20]
0x1800e285b  mov     [rbp+var_28], rax
0x1800e285f  lea     rax, [rbp+var_3C]
0x1800e2863  mov     [rsp+80h+var_48], rax
0x1800e2868  lea     rax, [rbp+var_40]
0x1800e286c  mov     [rsp+80h+var_50], rax
0x1800e2871  lea     rax, [rbp+var_38]
0x1800e2875  mov     [rsp+80h+var_58], rax
0x1800e287a  lea     rax, [rbp+var_28]
0x1800e287e  mov     [rsp+80h+var_60], rax
0x1800e2883  mov     [rbp+var_3C], ecx
0x1800e2886  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e288b  mov     rcx, [rsi]
0x1800e288e  test    rcx, rcx
0x1800e2891  jz      loc_1800E2A78
0x1800e2897  mov     rax, [rcx]
0x1800e289a  test    rax, rax
0x1800e289d  jz      loc_1800E2A78
0x1800e28a3  mov     rax, [rax+18h]
0x1800e28a7  lea     r8, [rdi+20h]
0x1800e28ab  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e28b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e28b7  mov     ebx, eax
0x1800e28b9  test    eax, eax
0x1800e28bb  jnz     loc_1800E2A7D
0x1800e28c1  cmp     [rsi+10h], r14d
0x1800e28c5  jz      loc_1800E2A11
0x1800e28cb  lea     rbx, [rdi+148h]
0x1800e28d2  mov     rcx, rbx
0x1800e28d5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e28da  mov     rcx, rbx; struct CSpJobMgr **
0x1800e28dd  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e28e2  test    eax, eax
0x1800e28e4  jnz     short loc_1800E28EE
0x1800e28e6  lea     ebx, [rax+1Ch]
0x1800e28e9  jmp     loc_1800E2A7D
0x1800e28ee  mov     ecx, 10h; Size
0x1800e28f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e28f8  xor     r8d, r8d; pcbe
0x1800e28fb  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e2902  mov     rdx, rax; pv
0x1800e2905  mov     r15, rax
0x1800e2908  mov     [rax], rdi
0x1800e290b  call    cs:__imp_CreateThreadpoolWork
0x1800e2912  nop     dword ptr [rax+rax+00h]
0x1800e2917  mov     r14, rax
0x1800e291a  test    rax, rax
0x1800e291d  jnz     short loc_1800E292B
0x1800e291f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e2924  mov     ebx, eax
0x1800e2926  jmp     loc_1800E2A7D
0x1800e292b  call    cs:__imp_GetCurrentThread
0x1800e2932  nop     dword ptr [rax+rax+00h]
0x1800e2937  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e293b  xor     r8d, r8d; OpenAsSelf
0x1800e293e  mov     rcx, rax; ThreadHandle
0x1800e2941  mov     edx, 2000Ch; DesiredAccess
0x1800e2946  call    cs:__imp_OpenThreadToken
0x1800e294d  nop     dword ptr [rax+rax+00h]
0x1800e2952  test    eax, eax
0x1800e2954  jnz     short loc_1800E2969
0x1800e2956  call    cs:__imp_GetLastError
0x1800e295d  nop     dword ptr [rax+rax+00h]
0x1800e2962  cmp     eax, 3F0h
0x1800e2967  jnz     short loc_1800E291F
0x1800e2969  mov     rax, [rbp+TokenHandle]
0x1800e296d  mov     r8, r13
0x1800e2970  mov     [r15+8], rax
0x1800e2974  mov     rcx, rdi
0x1800e2977  mov     rax, [rdi]
0x1800e297a  mov     rdx, [rsi+8]
0x1800e297e  mov     rax, [rax+18h]
0x1800e2982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2987  mov     rax, [rdi]
0x1800e298a  mov     rdx, r12
0x1800e298d  mov     rcx, rdi
0x1800e2990  mov     rax, [rax+28h]
0x1800e2994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2999  mov     ebx, eax
0x1800e299b  test    eax, eax
0x1800e299d  jz      short loc_1800E29A8
0x1800e299f  cmp     eax, 7
0x1800e29a2  jnz     loc_1800E2A7D
0x1800e29a8  mov     rax, [rdi]
0x1800e29ab  mov     rdx, r12
0x1800e29ae  mov     rcx, rdi
0x1800e29b1  mov     rax, [rax+38h]
0x1800e29b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e29ba  mov     ebx, eax
0x1800e29bc  test    eax, eax
0x1800e29be  jnz     loc_1800E2A7D
0x1800e29c4  mov     rax, [rdi+150h]
0x1800e29cb  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e29d2  jnz     short loc_1800E29E8
0x1800e29d4  mov     rax, [rdi+158h]
0x1800e29db  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e29e2  jz      loc_1800E2A7D
0x1800e29e8  mov     rdx, r12
0x1800e29eb  mov     rcx, rdi
0x1800e29ee  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e29f3  mov     ebx, eax
0x1800e29f5  test    eax, eax
0x1800e29f7  jnz     loc_1800E2A7D
0x1800e29fd  mov     rcx, r14; pwk
0x1800e2a00  call    cs:__imp_SubmitThreadpoolWork
0x1800e2a07  nop     dword ptr [rax+rax+00h]
0x1800e2a0c  jmp     loc_1800E2ACB
0x1800e2a11  mov     rax, [rdi]
0x1800e2a14  mov     r8, r13
0x1800e2a17  mov     rdx, [rsi+8]
0x1800e2a1b  mov     rcx, rdi
0x1800e2a1e  mov     rax, [rax+10h]
0x1800e2a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2a27  mov     rax, [rdi]
0x1800e2a2a  mov     rdx, r12
0x1800e2a2d  mov     rcx, rdi
0x1800e2a30  mov     rax, [rax+30h]
0x1800e2a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2a39  mov     ebx, eax
0x1800e2a3b  test    eax, eax
0x1800e2a3d  jz      short loc_1800E2A44
0x1800e2a3f  cmp     eax, 7
0x1800e2a42  jnz     short loc_1800E2A7D
0x1800e2a44  mov     rax, [rdi]
0x1800e2a47  mov     rdx, r12
0x1800e2a4a  mov     rcx, rdi
0x1800e2a4d  mov     rax, [rax+28h]
0x1800e2a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2a56  mov     ebx, eax
0x1800e2a58  test    eax, eax
0x1800e2a5a  jz      short loc_1800E2A61
0x1800e2a5c  cmp     eax, 7
0x1800e2a5f  jnz     short loc_1800E2A7D
0x1800e2a61  mov     rax, [rdi]
0x1800e2a64  mov     rdx, r12
0x1800e2a67  mov     rcx, rdi
0x1800e2a6a  mov     rax, [rax+38h]
0x1800e2a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2a73  jmp     loc_1800E2924
0x1800e2a78  mov     ebx, 4
0x1800e2a7d  mov     rax, [rdi]
0x1800e2a80  mov     edx, 1
0x1800e2a85  mov     rcx, rdi
0x1800e2a88  mov     rax, [rax]
0x1800e2a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2a90  test    r15, r15
0x1800e2a93  jz      short loc_1800E2AA2
0x1800e2a95  mov     edx, 10h
0x1800e2a9a  mov     rcx, r15; Block
0x1800e2a9d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e2aa2  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e2aa6  test    rcx, rcx
0x1800e2aa9  jz      short loc_1800E2AB7
0x1800e2aab  call    cs:__imp_CloseHandle
0x1800e2ab2  nop     dword ptr [rax+rax+00h]
0x1800e2ab7  test    r14, r14
0x1800e2aba  jz      short loc_1800E2ACB
0x1800e2abc  mov     rcx, r14; pwk
0x1800e2abf  call    cs:__imp_CloseThreadpoolWork
0x1800e2ac6  nop     dword ptr [rax+rax+00h]
0x1800e2acb  mov     eax, ebx
0x1800e2acd  mov     rcx, [rbp+var_8]
0x1800e2ad1  xor     rcx, rsp; StackCookie
0x1800e2ad4  call    __security_check_cookie
0x1800e2ad9  mov     rbx, [rsp+80h+arg_18]
0x1800e2ae1  add     rsp, 80h
0x1800e2ae8  pop     r15
0x1800e2aea  pop     r14
0x1800e2aec  pop     r13
0x1800e2aee  pop     r12
0x1800e2af0  pop     rdi
0x1800e2af1  pop     rsi
0x1800e2af2  pop     rbp
0x1800e2af3  retn
```
