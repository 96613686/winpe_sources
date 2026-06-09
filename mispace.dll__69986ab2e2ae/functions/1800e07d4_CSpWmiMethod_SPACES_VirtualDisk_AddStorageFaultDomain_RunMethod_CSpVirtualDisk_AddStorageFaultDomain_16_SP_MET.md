# CSpWmiMethod<_SPACES_VirtualDisk_AddStorageFaultDomain>::RunMethod<CSpVirtualDisk::AddStorageFaultDomain,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e07d4`
- end: `0x1800e0b51`
- name: `??$RunMethod@VAddStorageFaultDomain@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_AddStorageFaultDomain@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800e07d4`
- `0x1800e3d00`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e09b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e09b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0987`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e0987`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e09a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e09a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e0967`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e0967`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e0a5c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e0a5c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e0b1b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e0b1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0b07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e0b07`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_AddStorageFaultDomain>::RunMethod<CSpVirtualDisk::AddStorageFaultDomain,16>(
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
  CSpVirtualDisk::AddStorageFaultDomain *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::AddStorageFaultDomain *)operator new(0x160u);
  v7 = CSpVirtualDisk::AddStorageFaultDomain::AddStorageFaultDomain(v25);
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
      v25 = (CSpVirtualDisk::AddStorageFaultDomain *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_18033A9AC,
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
0x1800e07d4  mov     [rsp-38h+arg_18], rbx
0x1800e07d9  push    rbp
0x1800e07da  push    rsi
0x1800e07db  push    rdi
0x1800e07dc  push    r12
0x1800e07de  push    r13
0x1800e07e0  push    r14
0x1800e07e2  push    r15
0x1800e07e4  mov     rbp, rsp
0x1800e07e7  sub     rsp, 80h
0x1800e07ee  mov     rax, cs:__security_cookie
0x1800e07f5  xor     rax, rsp
0x1800e07f8  mov     [rbp+var_8], rax
0x1800e07fc  xor     eax, eax
0x1800e07fe  mov     rsi, rcx
0x1800e0801  xorps   xmm0, xmm0
0x1800e0804  mov     [rbp+var_10], eax
0x1800e0807  mov     ecx, 160h; Size
0x1800e080c  mov     [rbp+var_40], eax
0x1800e080f  movups  [rbp+var_20], xmm0
0x1800e0813  mov     [rbp+TokenHandle], rax
0x1800e0817  mov     r12, r8
0x1800e081a  mov     r13, rdx
0x1800e081d  xor     r14d, r14d
0x1800e0820  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e0825  mov     rcx, rax; this
0x1800e0828  mov     [rbp+var_28], rax
0x1800e082c  call    ??0AddStorageFaultDomain@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::AddStorageFaultDomain::AddStorageFaultDomain(void)
0x1800e0831  mov     rdi, rax
0x1800e0834  test    rax, rax
0x1800e0837  jnz     short loc_1800E0841
0x1800e0839  lea     ebx, [rax+1Bh]
0x1800e083c  jmp     loc_1800E0AFE
0x1800e0841  mov     rax, [rax]
0x1800e0844  mov     rdx, rsi
0x1800e0847  mov     rcx, rdi
0x1800e084a  xor     r15d, r15d
0x1800e084d  mov     rax, [rax+8]
0x1800e0851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0856  lea     rcx, [rbp+var_40]
0x1800e085a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e085f  mov     [rdi+1Ch], eax
0x1800e0862  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e0866  mov     ecx, [rsi+14h]; unsigned int
0x1800e0869  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e086e  mov     eax, cs:dword_18039EB68
0x1800e0874  cmp     eax, 5
0x1800e0877  jbe     short loc_1800E08E7
0x1800e0879  mov     rdx, 400000000000h
0x1800e0883  lea     rcx, dword_18039EB68
0x1800e088a  call    _tlgKeywordOn
0x1800e088f  test    al, al
0x1800e0891  jz      short loc_1800E08E7
0x1800e0893  mov     eax, [rbp+var_40]
0x1800e0896  lea     rdx, dword_18033A9AC
0x1800e089d  xor     ecx, ecx
0x1800e089f  cmp     [rdi+1Ch], eax
0x1800e08a2  movzx   eax, word ptr [rbp+var_10]
0x1800e08a6  mov     word ptr [rbp+var_40], ax
0x1800e08aa  setnz   cl
0x1800e08ad  mov     eax, [rsi+14h]
0x1800e08b0  mov     [rbp+var_38], eax
0x1800e08b3  lea     rax, [rbp+var_20]
0x1800e08b7  mov     [rbp+var_28], rax
0x1800e08bb  lea     rax, [rbp+var_3C]
0x1800e08bf  mov     [rsp+80h+var_48], rax
0x1800e08c4  lea     rax, [rbp+var_40]
0x1800e08c8  mov     [rsp+80h+var_50], rax
0x1800e08cd  lea     rax, [rbp+var_38]
0x1800e08d1  mov     [rsp+80h+var_58], rax
0x1800e08d6  lea     rax, [rbp+var_28]
0x1800e08da  mov     [rsp+80h+var_60], rax
0x1800e08df  mov     [rbp+var_3C], ecx
0x1800e08e2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e08e7  mov     rcx, [rsi]
0x1800e08ea  test    rcx, rcx
0x1800e08ed  jz      loc_1800E0AD4
0x1800e08f3  mov     rax, [rcx]
0x1800e08f6  test    rax, rax
0x1800e08f9  jz      loc_1800E0AD4
0x1800e08ff  mov     rax, [rax+18h]
0x1800e0903  lea     r8, [rdi+20h]
0x1800e0907  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e090e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0913  mov     ebx, eax
0x1800e0915  test    eax, eax
0x1800e0917  jnz     loc_1800E0AD9
0x1800e091d  cmp     [rsi+10h], r14d
0x1800e0921  jz      loc_1800E0A6D
0x1800e0927  lea     rbx, [rdi+148h]
0x1800e092e  mov     rcx, rbx
0x1800e0931  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e0936  mov     rcx, rbx; struct CSpJobMgr **
0x1800e0939  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e093e  test    eax, eax
0x1800e0940  jnz     short loc_1800E094A
0x1800e0942  lea     ebx, [rax+1Ch]
0x1800e0945  jmp     loc_1800E0AD9
0x1800e094a  mov     ecx, 10h; Size
0x1800e094f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e0954  xor     r8d, r8d; pcbe
0x1800e0957  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e095e  mov     rdx, rax; pv
0x1800e0961  mov     r15, rax
0x1800e0964  mov     [rax], rdi
0x1800e0967  call    cs:__imp_CreateThreadpoolWork
0x1800e096e  nop     dword ptr [rax+rax+00h]
0x1800e0973  mov     r14, rax
0x1800e0976  test    rax, rax
0x1800e0979  jnz     short loc_1800E0987
0x1800e097b  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e0980  mov     ebx, eax
0x1800e0982  jmp     loc_1800E0AD9
0x1800e0987  call    cs:__imp_GetCurrentThread
0x1800e098e  nop     dword ptr [rax+rax+00h]
0x1800e0993  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e0997  xor     r8d, r8d; OpenAsSelf
0x1800e099a  mov     rcx, rax; ThreadHandle
0x1800e099d  mov     edx, 2000Ch; DesiredAccess
0x1800e09a2  call    cs:__imp_OpenThreadToken
0x1800e09a9  nop     dword ptr [rax+rax+00h]
0x1800e09ae  test    eax, eax
0x1800e09b0  jnz     short loc_1800E09C5
0x1800e09b2  call    cs:__imp_GetLastError
0x1800e09b9  nop     dword ptr [rax+rax+00h]
0x1800e09be  cmp     eax, 3F0h
0x1800e09c3  jnz     short loc_1800E097B
0x1800e09c5  mov     rax, [rbp+TokenHandle]
0x1800e09c9  mov     r8, r13
0x1800e09cc  mov     [r15+8], rax
0x1800e09d0  mov     rcx, rdi
0x1800e09d3  mov     rax, [rdi]
0x1800e09d6  mov     rdx, [rsi+8]
0x1800e09da  mov     rax, [rax+18h]
0x1800e09de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e09e3  mov     rax, [rdi]
0x1800e09e6  mov     rdx, r12
0x1800e09e9  mov     rcx, rdi
0x1800e09ec  mov     rax, [rax+28h]
0x1800e09f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e09f5  mov     ebx, eax
0x1800e09f7  test    eax, eax
0x1800e09f9  jz      short loc_1800E0A04
0x1800e09fb  cmp     eax, 7
0x1800e09fe  jnz     loc_1800E0AD9
0x1800e0a04  mov     rax, [rdi]
0x1800e0a07  mov     rdx, r12
0x1800e0a0a  mov     rcx, rdi
0x1800e0a0d  mov     rax, [rax+38h]
0x1800e0a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0a16  mov     ebx, eax
0x1800e0a18  test    eax, eax
0x1800e0a1a  jnz     loc_1800E0AD9
0x1800e0a20  mov     rax, [rdi+150h]
0x1800e0a27  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e0a2e  jnz     short loc_1800E0A44
0x1800e0a30  mov     rax, [rdi+158h]
0x1800e0a37  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e0a3e  jz      loc_1800E0AD9
0x1800e0a44  mov     rdx, r12
0x1800e0a47  mov     rcx, rdi
0x1800e0a4a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e0a4f  mov     ebx, eax
0x1800e0a51  test    eax, eax
0x1800e0a53  jnz     loc_1800E0AD9
0x1800e0a59  mov     rcx, r14; pwk
0x1800e0a5c  call    cs:__imp_SubmitThreadpoolWork
0x1800e0a63  nop     dword ptr [rax+rax+00h]
0x1800e0a68  jmp     loc_1800E0B27
0x1800e0a6d  mov     rax, [rdi]
0x1800e0a70  mov     r8, r13
0x1800e0a73  mov     rdx, [rsi+8]
0x1800e0a77  mov     rcx, rdi
0x1800e0a7a  mov     rax, [rax+10h]
0x1800e0a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0a83  mov     rax, [rdi]
0x1800e0a86  mov     rdx, r12
0x1800e0a89  mov     rcx, rdi
0x1800e0a8c  mov     rax, [rax+30h]
0x1800e0a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0a95  mov     ebx, eax
0x1800e0a97  test    eax, eax
0x1800e0a99  jz      short loc_1800E0AA0
0x1800e0a9b  cmp     eax, 7
0x1800e0a9e  jnz     short loc_1800E0AD9
0x1800e0aa0  mov     rax, [rdi]
0x1800e0aa3  mov     rdx, r12
0x1800e0aa6  mov     rcx, rdi
0x1800e0aa9  mov     rax, [rax+28h]
0x1800e0aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0ab2  mov     ebx, eax
0x1800e0ab4  test    eax, eax
0x1800e0ab6  jz      short loc_1800E0ABD
0x1800e0ab8  cmp     eax, 7
0x1800e0abb  jnz     short loc_1800E0AD9
0x1800e0abd  mov     rax, [rdi]
0x1800e0ac0  mov     rdx, r12
0x1800e0ac3  mov     rcx, rdi
0x1800e0ac6  mov     rax, [rax+38h]
0x1800e0aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0acf  jmp     loc_1800E0980
0x1800e0ad4  mov     ebx, 4
0x1800e0ad9  mov     rax, [rdi]
0x1800e0adc  mov     edx, 1
0x1800e0ae1  mov     rcx, rdi
0x1800e0ae4  mov     rax, [rax]
0x1800e0ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0aec  test    r15, r15
0x1800e0aef  jz      short loc_1800E0AFE
0x1800e0af1  mov     edx, 10h
0x1800e0af6  mov     rcx, r15; Block
0x1800e0af9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e0afe  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e0b02  test    rcx, rcx
0x1800e0b05  jz      short loc_1800E0B13
0x1800e0b07  call    cs:__imp_CloseHandle
0x1800e0b0e  nop     dword ptr [rax+rax+00h]
0x1800e0b13  test    r14, r14
0x1800e0b16  jz      short loc_1800E0B27
0x1800e0b18  mov     rcx, r14; pwk
0x1800e0b1b  call    cs:__imp_CloseThreadpoolWork
0x1800e0b22  nop     dword ptr [rax+rax+00h]
0x1800e0b27  mov     eax, ebx
0x1800e0b29  mov     rcx, [rbp+var_8]
0x1800e0b2d  xor     rcx, rsp; StackCookie
0x1800e0b30  call    __security_check_cookie
0x1800e0b35  mov     rbx, [rsp+80h+arg_18]
0x1800e0b3d  add     rsp, 80h
0x1800e0b44  pop     r15
0x1800e0b46  pop     r14
0x1800e0b48  pop     r13
0x1800e0b4a  pop     r12
0x1800e0b4c  pop     rdi
0x1800e0b4d  pop     rsi
0x1800e0b4e  pop     rbp
0x1800e0b4f  retn
```
