# CSpWmiMethod<_SPACES_VirtualDisk_SetFriendlyName>::RunMethod<CSpVirtualDisk::SetFriendlyName,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e2e80`
- end: `0x1800e31fd`
- name: `??$RunMethod@VSetFriendlyName@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_SetFriendlyName@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800e2e80`
- `0x1800e41fc`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e305e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e305e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e3033`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e3033`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e304e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e304e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e3013`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e3013`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e3108`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e3108`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e31c7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e31c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e31b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e31b3`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_SetFriendlyName>::RunMethod<CSpVirtualDisk::SetFriendlyName,16>(
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
  CSpVirtualDisk::SetFriendlyName *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::SetFriendlyName *)operator new(0x160u);
  v7 = CSpVirtualDisk::SetFriendlyName::SetFriendlyName(v25);
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
      v25 = (CSpVirtualDisk::SetFriendlyName *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_180339C4E,
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
0x1800e2e80  mov     [rsp-38h+arg_18], rbx
0x1800e2e85  push    rbp
0x1800e2e86  push    rsi
0x1800e2e87  push    rdi
0x1800e2e88  push    r12
0x1800e2e8a  push    r13
0x1800e2e8c  push    r14
0x1800e2e8e  push    r15
0x1800e2e90  mov     rbp, rsp
0x1800e2e93  sub     rsp, 80h
0x1800e2e9a  mov     rax, cs:__security_cookie
0x1800e2ea1  xor     rax, rsp
0x1800e2ea4  mov     [rbp+var_8], rax
0x1800e2ea8  xor     eax, eax
0x1800e2eaa  mov     rsi, rcx
0x1800e2ead  xorps   xmm0, xmm0
0x1800e2eb0  mov     [rbp+var_10], eax
0x1800e2eb3  mov     ecx, 160h; Size
0x1800e2eb8  mov     [rbp+var_40], eax
0x1800e2ebb  movups  [rbp+var_20], xmm0
0x1800e2ebf  mov     [rbp+TokenHandle], rax
0x1800e2ec3  mov     r12, r8
0x1800e2ec6  mov     r13, rdx
0x1800e2ec9  xor     r14d, r14d
0x1800e2ecc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e2ed1  mov     rcx, rax; this
0x1800e2ed4  mov     [rbp+var_28], rax
0x1800e2ed8  call    ??0SetFriendlyName@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::SetFriendlyName::SetFriendlyName(void)
0x1800e2edd  mov     rdi, rax
0x1800e2ee0  test    rax, rax
0x1800e2ee3  jnz     short loc_1800E2EED
0x1800e2ee5  lea     ebx, [rax+1Bh]
0x1800e2ee8  jmp     loc_1800E31AA
0x1800e2eed  mov     rax, [rax]
0x1800e2ef0  mov     rdx, rsi
0x1800e2ef3  mov     rcx, rdi
0x1800e2ef6  xor     r15d, r15d
0x1800e2ef9  mov     rax, [rax+8]
0x1800e2efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2f02  lea     rcx, [rbp+var_40]
0x1800e2f06  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e2f0b  mov     [rdi+1Ch], eax
0x1800e2f0e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e2f12  mov     ecx, [rsi+14h]; unsigned int
0x1800e2f15  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e2f1a  mov     eax, cs:dword_18039EB68
0x1800e2f20  cmp     eax, 5
0x1800e2f23  jbe     short loc_1800E2F93
0x1800e2f25  mov     rdx, 400000000000h
0x1800e2f2f  lea     rcx, dword_18039EB68
0x1800e2f36  call    _tlgKeywordOn
0x1800e2f3b  test    al, al
0x1800e2f3d  jz      short loc_1800E2F93
0x1800e2f3f  mov     eax, [rbp+var_40]
0x1800e2f42  lea     rdx, word_180339C4E
0x1800e2f49  xor     ecx, ecx
0x1800e2f4b  cmp     [rdi+1Ch], eax
0x1800e2f4e  movzx   eax, word ptr [rbp+var_10]
0x1800e2f52  mov     word ptr [rbp+var_40], ax
0x1800e2f56  setnz   cl
0x1800e2f59  mov     eax, [rsi+14h]
0x1800e2f5c  mov     [rbp+var_38], eax
0x1800e2f5f  lea     rax, [rbp+var_20]
0x1800e2f63  mov     [rbp+var_28], rax
0x1800e2f67  lea     rax, [rbp+var_3C]
0x1800e2f6b  mov     [rsp+80h+var_48], rax
0x1800e2f70  lea     rax, [rbp+var_40]
0x1800e2f74  mov     [rsp+80h+var_50], rax
0x1800e2f79  lea     rax, [rbp+var_38]
0x1800e2f7d  mov     [rsp+80h+var_58], rax
0x1800e2f82  lea     rax, [rbp+var_28]
0x1800e2f86  mov     [rsp+80h+var_60], rax
0x1800e2f8b  mov     [rbp+var_3C], ecx
0x1800e2f8e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e2f93  mov     rcx, [rsi]
0x1800e2f96  test    rcx, rcx
0x1800e2f99  jz      loc_1800E3180
0x1800e2f9f  mov     rax, [rcx]
0x1800e2fa2  test    rax, rax
0x1800e2fa5  jz      loc_1800E3180
0x1800e2fab  mov     rax, [rax+18h]
0x1800e2faf  lea     r8, [rdi+20h]
0x1800e2fb3  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e2fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2fbf  mov     ebx, eax
0x1800e2fc1  test    eax, eax
0x1800e2fc3  jnz     loc_1800E3185
0x1800e2fc9  cmp     [rsi+10h], r14d
0x1800e2fcd  jz      loc_1800E3119
0x1800e2fd3  lea     rbx, [rdi+148h]
0x1800e2fda  mov     rcx, rbx
0x1800e2fdd  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e2fe2  mov     rcx, rbx; struct CSpJobMgr **
0x1800e2fe5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e2fea  test    eax, eax
0x1800e2fec  jnz     short loc_1800E2FF6
0x1800e2fee  lea     ebx, [rax+1Ch]
0x1800e2ff1  jmp     loc_1800E3185
0x1800e2ff6  mov     ecx, 10h; Size
0x1800e2ffb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e3000  xor     r8d, r8d; pcbe
0x1800e3003  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e300a  mov     rdx, rax; pv
0x1800e300d  mov     r15, rax
0x1800e3010  mov     [rax], rdi
0x1800e3013  call    cs:__imp_CreateThreadpoolWork
0x1800e301a  nop     dword ptr [rax+rax+00h]
0x1800e301f  mov     r14, rax
0x1800e3022  test    rax, rax
0x1800e3025  jnz     short loc_1800E3033
0x1800e3027  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e302c  mov     ebx, eax
0x1800e302e  jmp     loc_1800E3185
0x1800e3033  call    cs:__imp_GetCurrentThread
0x1800e303a  nop     dword ptr [rax+rax+00h]
0x1800e303f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e3043  xor     r8d, r8d; OpenAsSelf
0x1800e3046  mov     rcx, rax; ThreadHandle
0x1800e3049  mov     edx, 2000Ch; DesiredAccess
0x1800e304e  call    cs:__imp_OpenThreadToken
0x1800e3055  nop     dword ptr [rax+rax+00h]
0x1800e305a  test    eax, eax
0x1800e305c  jnz     short loc_1800E3071
0x1800e305e  call    cs:__imp_GetLastError
0x1800e3065  nop     dword ptr [rax+rax+00h]
0x1800e306a  cmp     eax, 3F0h
0x1800e306f  jnz     short loc_1800E3027
0x1800e3071  mov     rax, [rbp+TokenHandle]
0x1800e3075  mov     r8, r13
0x1800e3078  mov     [r15+8], rax
0x1800e307c  mov     rcx, rdi
0x1800e307f  mov     rax, [rdi]
0x1800e3082  mov     rdx, [rsi+8]
0x1800e3086  mov     rax, [rax+18h]
0x1800e308a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e308f  mov     rax, [rdi]
0x1800e3092  mov     rdx, r12
0x1800e3095  mov     rcx, rdi
0x1800e3098  mov     rax, [rax+28h]
0x1800e309c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e30a1  mov     ebx, eax
0x1800e30a3  test    eax, eax
0x1800e30a5  jz      short loc_1800E30B0
0x1800e30a7  cmp     eax, 7
0x1800e30aa  jnz     loc_1800E3185
0x1800e30b0  mov     rax, [rdi]
0x1800e30b3  mov     rdx, r12
0x1800e30b6  mov     rcx, rdi
0x1800e30b9  mov     rax, [rax+38h]
0x1800e30bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e30c2  mov     ebx, eax
0x1800e30c4  test    eax, eax
0x1800e30c6  jnz     loc_1800E3185
0x1800e30cc  mov     rax, [rdi+150h]
0x1800e30d3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e30da  jnz     short loc_1800E30F0
0x1800e30dc  mov     rax, [rdi+158h]
0x1800e30e3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e30ea  jz      loc_1800E3185
0x1800e30f0  mov     rdx, r12
0x1800e30f3  mov     rcx, rdi
0x1800e30f6  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e30fb  mov     ebx, eax
0x1800e30fd  test    eax, eax
0x1800e30ff  jnz     loc_1800E3185
0x1800e3105  mov     rcx, r14; pwk
0x1800e3108  call    cs:__imp_SubmitThreadpoolWork
0x1800e310f  nop     dword ptr [rax+rax+00h]
0x1800e3114  jmp     loc_1800E31D3
0x1800e3119  mov     rax, [rdi]
0x1800e311c  mov     r8, r13
0x1800e311f  mov     rdx, [rsi+8]
0x1800e3123  mov     rcx, rdi
0x1800e3126  mov     rax, [rax+10h]
0x1800e312a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e312f  mov     rax, [rdi]
0x1800e3132  mov     rdx, r12
0x1800e3135  mov     rcx, rdi
0x1800e3138  mov     rax, [rax+30h]
0x1800e313c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3141  mov     ebx, eax
0x1800e3143  test    eax, eax
0x1800e3145  jz      short loc_1800E314C
0x1800e3147  cmp     eax, 7
0x1800e314a  jnz     short loc_1800E3185
0x1800e314c  mov     rax, [rdi]
0x1800e314f  mov     rdx, r12
0x1800e3152  mov     rcx, rdi
0x1800e3155  mov     rax, [rax+28h]
0x1800e3159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e315e  mov     ebx, eax
0x1800e3160  test    eax, eax
0x1800e3162  jz      short loc_1800E3169
0x1800e3164  cmp     eax, 7
0x1800e3167  jnz     short loc_1800E3185
0x1800e3169  mov     rax, [rdi]
0x1800e316c  mov     rdx, r12
0x1800e316f  mov     rcx, rdi
0x1800e3172  mov     rax, [rax+38h]
0x1800e3176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e317b  jmp     loc_1800E302C
0x1800e3180  mov     ebx, 4
0x1800e3185  mov     rax, [rdi]
0x1800e3188  mov     edx, 1
0x1800e318d  mov     rcx, rdi
0x1800e3190  mov     rax, [rax]
0x1800e3193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3198  test    r15, r15
0x1800e319b  jz      short loc_1800E31AA
0x1800e319d  mov     edx, 10h
0x1800e31a2  mov     rcx, r15; Block
0x1800e31a5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e31aa  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e31ae  test    rcx, rcx
0x1800e31b1  jz      short loc_1800E31BF
0x1800e31b3  call    cs:__imp_CloseHandle
0x1800e31ba  nop     dword ptr [rax+rax+00h]
0x1800e31bf  test    r14, r14
0x1800e31c2  jz      short loc_1800E31D3
0x1800e31c4  mov     rcx, r14; pwk
0x1800e31c7  call    cs:__imp_CloseThreadpoolWork
0x1800e31ce  nop     dword ptr [rax+rax+00h]
0x1800e31d3  mov     eax, ebx
0x1800e31d5  mov     rcx, [rbp+var_8]
0x1800e31d9  xor     rcx, rsp; StackCookie
0x1800e31dc  call    __security_check_cookie
0x1800e31e1  mov     rbx, [rsp+80h+arg_18]
0x1800e31e9  add     rsp, 80h
0x1800e31f0  pop     r15
0x1800e31f2  pop     r14
0x1800e31f4  pop     r13
0x1800e31f6  pop     r12
0x1800e31f8  pop     rdi
0x1800e31f9  pop     rsi
0x1800e31fa  pop     rbp
0x1800e31fb  retn
```
