# CSpWmiMethod<_SPACES_StorageProvider_UnregisterSubsystem>::RunMethod<CSpProvider::_UnregisterSubsystem,5>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x18001ee40`
- end: `0x18001f1bd`
- name: `??$RunMethod@V_UnregisterSubsystem@CSpProvider@@$04@?$CSpWmiMethod@U_SPACES_StorageProvider_UnregisterSubsystem@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x18001ee40`
- `0x18001f338`
- `0x1800257fc`
- `0x18005f41c`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f01e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f01e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001eff3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001eff3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f00e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f00e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001efd3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001efd3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001f0c8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001f0c8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001f187`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001f187`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f173`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f173`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageProvider_UnregisterSubsystem>::RunMethod<CSpProvider::_UnregisterSubsystem,5>(
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
  CSpProvider::_UnregisterSubsystem *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpProvider::_UnregisterSubsystem *)operator new(0x160u);
  v7 = CSpProvider::_UnregisterSubsystem::_UnregisterSubsystem(v25);
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
      v25 = (CSpProvider::_UnregisterSubsystem *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_1802F92CB,
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
0x18001ee40  mov     [rsp-38h+arg_18], rbx
0x18001ee45  push    rbp
0x18001ee46  push    rsi
0x18001ee47  push    rdi
0x18001ee48  push    r12
0x18001ee4a  push    r13
0x18001ee4c  push    r14
0x18001ee4e  push    r15
0x18001ee50  mov     rbp, rsp
0x18001ee53  sub     rsp, 80h
0x18001ee5a  mov     rax, cs:__security_cookie
0x18001ee61  xor     rax, rsp
0x18001ee64  mov     [rbp+var_8], rax
0x18001ee68  xor     eax, eax
0x18001ee6a  mov     rsi, rcx
0x18001ee6d  xorps   xmm0, xmm0
0x18001ee70  mov     [rbp+var_10], eax
0x18001ee73  mov     ecx, 160h; Size
0x18001ee78  mov     [rbp+var_40], eax
0x18001ee7b  movups  [rbp+var_20], xmm0
0x18001ee7f  mov     [rbp+TokenHandle], rax
0x18001ee83  mov     r12, r8
0x18001ee86  mov     r13, rdx
0x18001ee89  xor     r14d, r14d
0x18001ee8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ee91  mov     rcx, rax; this
0x18001ee94  mov     [rbp+var_28], rax
0x18001ee98  call    ??0_UnregisterSubsystem@CSpProvider@@QEAA@XZ; CSpProvider::_UnregisterSubsystem::_UnregisterSubsystem(void)
0x18001ee9d  mov     rdi, rax
0x18001eea0  test    rax, rax
0x18001eea3  jnz     short loc_18001EEAD
0x18001eea5  lea     ebx, [rax+1Bh]
0x18001eea8  jmp     loc_18001F16A
0x18001eead  mov     rax, [rax]
0x18001eeb0  mov     rdx, rsi
0x18001eeb3  mov     rcx, rdi
0x18001eeb6  xor     r15d, r15d
0x18001eeb9  mov     rax, [rax+8]
0x18001eebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eec2  lea     rcx, [rbp+var_40]
0x18001eec6  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18001eecb  mov     [rdi+1Ch], eax
0x18001eece  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x18001eed2  mov     ecx, [rsi+14h]; unsigned int
0x18001eed5  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18001eeda  mov     eax, cs:dword_18039EB68
0x18001eee0  cmp     eax, 5
0x18001eee3  jbe     short loc_18001EF53
0x18001eee5  mov     rdx, 400000000000h
0x18001eeef  lea     rcx, dword_18039EB68
0x18001eef6  call    _tlgKeywordOn
0x18001eefb  test    al, al
0x18001eefd  jz      short loc_18001EF53
0x18001eeff  mov     eax, [rbp+var_40]
0x18001ef02  lea     rdx, byte_1802F92CB
0x18001ef09  xor     ecx, ecx
0x18001ef0b  cmp     [rdi+1Ch], eax
0x18001ef0e  movzx   eax, word ptr [rbp+var_10]
0x18001ef12  mov     word ptr [rbp+var_40], ax
0x18001ef16  setnz   cl
0x18001ef19  mov     eax, [rsi+14h]
0x18001ef1c  mov     [rbp+var_38], eax
0x18001ef1f  lea     rax, [rbp+var_20]
0x18001ef23  mov     [rbp+var_28], rax
0x18001ef27  lea     rax, [rbp+var_3C]
0x18001ef2b  mov     [rsp+80h+var_48], rax
0x18001ef30  lea     rax, [rbp+var_40]
0x18001ef34  mov     [rsp+80h+var_50], rax
0x18001ef39  lea     rax, [rbp+var_38]
0x18001ef3d  mov     [rsp+80h+var_58], rax
0x18001ef42  lea     rax, [rbp+var_28]
0x18001ef46  mov     [rsp+80h+var_60], rax
0x18001ef4b  mov     [rbp+var_3C], ecx
0x18001ef4e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x18001ef53  mov     rcx, [rsi]
0x18001ef56  test    rcx, rcx
0x18001ef59  jz      loc_18001F140
0x18001ef5f  mov     rax, [rcx]
0x18001ef62  test    rax, rax
0x18001ef65  jz      loc_18001F140
0x18001ef6b  mov     rax, [rax+18h]
0x18001ef6f  lea     r8, [rdi+20h]
0x18001ef73  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18001ef7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef7f  mov     ebx, eax
0x18001ef81  test    eax, eax
0x18001ef83  jnz     loc_18001F145
0x18001ef89  cmp     [rsi+10h], r14d
0x18001ef8d  jz      loc_18001F0D9
0x18001ef93  lea     rbx, [rdi+148h]
0x18001ef9a  mov     rcx, rbx
0x18001ef9d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18001efa2  mov     rcx, rbx; struct CSpJobMgr **
0x18001efa5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18001efaa  test    eax, eax
0x18001efac  jnz     short loc_18001EFB6
0x18001efae  lea     ebx, [rax+1Ch]
0x18001efb1  jmp     loc_18001F145
0x18001efb6  mov     ecx, 10h; Size
0x18001efbb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001efc0  xor     r8d, r8d; pcbe
0x18001efc3  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001efca  mov     rdx, rax; pv
0x18001efcd  mov     r15, rax
0x18001efd0  mov     [rax], rdi
0x18001efd3  call    cs:__imp_CreateThreadpoolWork
0x18001efda  nop     dword ptr [rax+rax+00h]
0x18001efdf  mov     r14, rax
0x18001efe2  test    rax, rax
0x18001efe5  jnz     short loc_18001EFF3
0x18001efe7  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18001efec  mov     ebx, eax
0x18001efee  jmp     loc_18001F145
0x18001eff3  call    cs:__imp_GetCurrentThread
0x18001effa  nop     dword ptr [rax+rax+00h]
0x18001efff  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001f003  xor     r8d, r8d; OpenAsSelf
0x18001f006  mov     rcx, rax; ThreadHandle
0x18001f009  mov     edx, 2000Ch; DesiredAccess
0x18001f00e  call    cs:__imp_OpenThreadToken
0x18001f015  nop     dword ptr [rax+rax+00h]
0x18001f01a  test    eax, eax
0x18001f01c  jnz     short loc_18001F031
0x18001f01e  call    cs:__imp_GetLastError
0x18001f025  nop     dword ptr [rax+rax+00h]
0x18001f02a  cmp     eax, 3F0h
0x18001f02f  jnz     short loc_18001EFE7
0x18001f031  mov     rax, [rbp+TokenHandle]
0x18001f035  mov     r8, r13
0x18001f038  mov     [r15+8], rax
0x18001f03c  mov     rcx, rdi
0x18001f03f  mov     rax, [rdi]
0x18001f042  mov     rdx, [rsi+8]
0x18001f046  mov     rax, [rax+18h]
0x18001f04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f04f  mov     rax, [rdi]
0x18001f052  mov     rdx, r12
0x18001f055  mov     rcx, rdi
0x18001f058  mov     rax, [rax+28h]
0x18001f05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f061  mov     ebx, eax
0x18001f063  test    eax, eax
0x18001f065  jz      short loc_18001F070
0x18001f067  cmp     eax, 7
0x18001f06a  jnz     loc_18001F145
0x18001f070  mov     rax, [rdi]
0x18001f073  mov     rdx, r12
0x18001f076  mov     rcx, rdi
0x18001f079  mov     rax, [rax+38h]
0x18001f07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f082  mov     ebx, eax
0x18001f084  test    eax, eax
0x18001f086  jnz     loc_18001F145
0x18001f08c  mov     rax, [rdi+150h]
0x18001f093  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18001f09a  jnz     short loc_18001F0B0
0x18001f09c  mov     rax, [rdi+158h]
0x18001f0a3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18001f0aa  jz      loc_18001F145
0x18001f0b0  mov     rdx, r12
0x18001f0b3  mov     rcx, rdi
0x18001f0b6  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18001f0bb  mov     ebx, eax
0x18001f0bd  test    eax, eax
0x18001f0bf  jnz     loc_18001F145
0x18001f0c5  mov     rcx, r14; pwk
0x18001f0c8  call    cs:__imp_SubmitThreadpoolWork
0x18001f0cf  nop     dword ptr [rax+rax+00h]
0x18001f0d4  jmp     loc_18001F193
0x18001f0d9  mov     rax, [rdi]
0x18001f0dc  mov     r8, r13
0x18001f0df  mov     rdx, [rsi+8]
0x18001f0e3  mov     rcx, rdi
0x18001f0e6  mov     rax, [rax+10h]
0x18001f0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0ef  mov     rax, [rdi]
0x18001f0f2  mov     rdx, r12
0x18001f0f5  mov     rcx, rdi
0x18001f0f8  mov     rax, [rax+30h]
0x18001f0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f101  mov     ebx, eax
0x18001f103  test    eax, eax
0x18001f105  jz      short loc_18001F10C
0x18001f107  cmp     eax, 7
0x18001f10a  jnz     short loc_18001F145
0x18001f10c  mov     rax, [rdi]
0x18001f10f  mov     rdx, r12
0x18001f112  mov     rcx, rdi
0x18001f115  mov     rax, [rax+28h]
0x18001f119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f11e  mov     ebx, eax
0x18001f120  test    eax, eax
0x18001f122  jz      short loc_18001F129
0x18001f124  cmp     eax, 7
0x18001f127  jnz     short loc_18001F145
0x18001f129  mov     rax, [rdi]
0x18001f12c  mov     rdx, r12
0x18001f12f  mov     rcx, rdi
0x18001f132  mov     rax, [rax+38h]
0x18001f136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f13b  jmp     loc_18001EFEC
0x18001f140  mov     ebx, 4
0x18001f145  mov     rax, [rdi]
0x18001f148  mov     edx, 1
0x18001f14d  mov     rcx, rdi
0x18001f150  mov     rax, [rax]
0x18001f153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f158  test    r15, r15
0x18001f15b  jz      short loc_18001F16A
0x18001f15d  mov     edx, 10h
0x18001f162  mov     rcx, r15; Block
0x18001f165  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f16a  mov     rcx, [rbp+TokenHandle]; hObject
0x18001f16e  test    rcx, rcx
0x18001f171  jz      short loc_18001F17F
0x18001f173  call    cs:__imp_CloseHandle
0x18001f17a  nop     dword ptr [rax+rax+00h]
0x18001f17f  test    r14, r14
0x18001f182  jz      short loc_18001F193
0x18001f184  mov     rcx, r14; pwk
0x18001f187  call    cs:__imp_CloseThreadpoolWork
0x18001f18e  nop     dword ptr [rax+rax+00h]
0x18001f193  mov     eax, ebx
0x18001f195  mov     rcx, [rbp+var_8]
0x18001f199  xor     rcx, rsp; StackCookie
0x18001f19c  call    __security_check_cookie
0x18001f1a1  mov     rbx, [rsp+80h+arg_18]
0x18001f1a9  add     rsp, 80h
0x18001f1b0  pop     r15
0x18001f1b2  pop     r14
0x18001f1b4  pop     r13
0x18001f1b6  pop     r12
0x18001f1b8  pop     rdi
0x18001f1b9  pop     rsi
0x18001f1ba  pop     rbp
0x18001f1bb  retn
```
