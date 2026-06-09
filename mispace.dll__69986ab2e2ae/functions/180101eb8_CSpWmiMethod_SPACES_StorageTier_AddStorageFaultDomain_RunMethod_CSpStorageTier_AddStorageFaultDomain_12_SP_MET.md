# CSpWmiMethod<_SPACES_StorageTier_AddStorageFaultDomain>::RunMethod<CSpStorageTier::AddStorageFaultDomain,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x180101eb8`
- end: `0x180102235`
- name: `??$RunMethod@VAddStorageFaultDomain@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_AddStorageFaultDomain@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x180101eb8`
- `0x180103e60`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102096`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010206b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18010206b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180102086`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180102086`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18010204b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18010204b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180102140`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180102140`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801021ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1801021ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801021eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801021eb`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_AddStorageFaultDomain>::RunMethod<CSpStorageTier::AddStorageFaultDomain,12>(
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
  CSpStorageTier::AddStorageFaultDomain *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::AddStorageFaultDomain *)operator new(0x160u);
  v7 = CSpStorageTier::AddStorageFaultDomain::AddStorageFaultDomain(v25);
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
      v25 = (CSpStorageTier::AddStorageFaultDomain *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_180340AB1,
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
0x180101eb8  mov     [rsp-38h+arg_18], rbx
0x180101ebd  push    rbp
0x180101ebe  push    rsi
0x180101ebf  push    rdi
0x180101ec0  push    r12
0x180101ec2  push    r13
0x180101ec4  push    r14
0x180101ec6  push    r15
0x180101ec8  mov     rbp, rsp
0x180101ecb  sub     rsp, 80h
0x180101ed2  mov     rax, cs:__security_cookie
0x180101ed9  xor     rax, rsp
0x180101edc  mov     [rbp+var_8], rax
0x180101ee0  xor     eax, eax
0x180101ee2  mov     rsi, rcx
0x180101ee5  xorps   xmm0, xmm0
0x180101ee8  mov     [rbp+var_10], eax
0x180101eeb  mov     ecx, 160h; Size
0x180101ef0  mov     [rbp+var_40], eax
0x180101ef3  movups  [rbp+var_20], xmm0
0x180101ef7  mov     [rbp+TokenHandle], rax
0x180101efb  mov     r12, r8
0x180101efe  mov     r13, rdx
0x180101f01  xor     r14d, r14d
0x180101f04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180101f09  mov     rcx, rax; this
0x180101f0c  mov     [rbp+var_28], rax
0x180101f10  call    ??0AddStorageFaultDomain@CSpStorageTier@@QEAA@XZ; CSpStorageTier::AddStorageFaultDomain::AddStorageFaultDomain(void)
0x180101f15  mov     rdi, rax
0x180101f18  test    rax, rax
0x180101f1b  jnz     short loc_180101F25
0x180101f1d  lea     ebx, [rax+1Bh]
0x180101f20  jmp     loc_1801021E2
0x180101f25  mov     rax, [rax]
0x180101f28  mov     rdx, rsi
0x180101f2b  mov     rcx, rdi
0x180101f2e  xor     r15d, r15d
0x180101f31  mov     rax, [rax+8]
0x180101f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101f3a  lea     rcx, [rbp+var_40]
0x180101f3e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180101f43  mov     [rdi+1Ch], eax
0x180101f46  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x180101f4a  mov     ecx, [rsi+14h]; unsigned int
0x180101f4d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180101f52  mov     eax, cs:dword_18039EB68
0x180101f58  cmp     eax, 5
0x180101f5b  jbe     short loc_180101FCB
0x180101f5d  mov     rdx, 400000000000h
0x180101f67  lea     rcx, dword_18039EB68
0x180101f6e  call    _tlgKeywordOn
0x180101f73  test    al, al
0x180101f75  jz      short loc_180101FCB
0x180101f77  mov     eax, [rbp+var_40]
0x180101f7a  lea     rdx, byte_180340AB1
0x180101f81  xor     ecx, ecx
0x180101f83  cmp     [rdi+1Ch], eax
0x180101f86  movzx   eax, word ptr [rbp+var_10]
0x180101f8a  mov     word ptr [rbp+var_40], ax
0x180101f8e  setnz   cl
0x180101f91  mov     eax, [rsi+14h]
0x180101f94  mov     [rbp+var_38], eax
0x180101f97  lea     rax, [rbp+var_20]
0x180101f9b  mov     [rbp+var_28], rax
0x180101f9f  lea     rax, [rbp+var_3C]
0x180101fa3  mov     [rsp+80h+var_48], rax
0x180101fa8  lea     rax, [rbp+var_40]
0x180101fac  mov     [rsp+80h+var_50], rax
0x180101fb1  lea     rax, [rbp+var_38]
0x180101fb5  mov     [rsp+80h+var_58], rax
0x180101fba  lea     rax, [rbp+var_28]
0x180101fbe  mov     [rsp+80h+var_60], rax
0x180101fc3  mov     [rbp+var_3C], ecx
0x180101fc6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x180101fcb  mov     rcx, [rsi]
0x180101fce  test    rcx, rcx
0x180101fd1  jz      loc_1801021B8
0x180101fd7  mov     rax, [rcx]
0x180101fda  test    rax, rax
0x180101fdd  jz      loc_1801021B8
0x180101fe3  mov     rax, [rax+18h]
0x180101fe7  lea     r8, [rdi+20h]
0x180101feb  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180101ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101ff7  mov     ebx, eax
0x180101ff9  test    eax, eax
0x180101ffb  jnz     loc_1801021BD
0x180102001  cmp     [rsi+10h], r14d
0x180102005  jz      loc_180102151
0x18010200b  lea     rbx, [rdi+148h]
0x180102012  mov     rcx, rbx
0x180102015  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18010201a  mov     rcx, rbx; struct CSpJobMgr **
0x18010201d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x180102022  test    eax, eax
0x180102024  jnz     short loc_18010202E
0x180102026  lea     ebx, [rax+1Ch]
0x180102029  jmp     loc_1801021BD
0x18010202e  mov     ecx, 10h; Size
0x180102033  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180102038  xor     r8d, r8d; pcbe
0x18010203b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180102042  mov     rdx, rax; pv
0x180102045  mov     r15, rax
0x180102048  mov     [rax], rdi
0x18010204b  call    cs:__imp_CreateThreadpoolWork
0x180102052  nop     dword ptr [rax+rax+00h]
0x180102057  mov     r14, rax
0x18010205a  test    rax, rax
0x18010205d  jnz     short loc_18010206B
0x18010205f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180102064  mov     ebx, eax
0x180102066  jmp     loc_1801021BD
0x18010206b  call    cs:__imp_GetCurrentThread
0x180102072  nop     dword ptr [rax+rax+00h]
0x180102077  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18010207b  xor     r8d, r8d; OpenAsSelf
0x18010207e  mov     rcx, rax; ThreadHandle
0x180102081  mov     edx, 2000Ch; DesiredAccess
0x180102086  call    cs:__imp_OpenThreadToken
0x18010208d  nop     dword ptr [rax+rax+00h]
0x180102092  test    eax, eax
0x180102094  jnz     short loc_1801020A9
0x180102096  call    cs:__imp_GetLastError
0x18010209d  nop     dword ptr [rax+rax+00h]
0x1801020a2  cmp     eax, 3F0h
0x1801020a7  jnz     short loc_18010205F
0x1801020a9  mov     rax, [rbp+TokenHandle]
0x1801020ad  mov     r8, r13
0x1801020b0  mov     [r15+8], rax
0x1801020b4  mov     rcx, rdi
0x1801020b7  mov     rax, [rdi]
0x1801020ba  mov     rdx, [rsi+8]
0x1801020be  mov     rax, [rax+18h]
0x1801020c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801020c7  mov     rax, [rdi]
0x1801020ca  mov     rdx, r12
0x1801020cd  mov     rcx, rdi
0x1801020d0  mov     rax, [rax+28h]
0x1801020d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801020d9  mov     ebx, eax
0x1801020db  test    eax, eax
0x1801020dd  jz      short loc_1801020E8
0x1801020df  cmp     eax, 7
0x1801020e2  jnz     loc_1801021BD
0x1801020e8  mov     rax, [rdi]
0x1801020eb  mov     rdx, r12
0x1801020ee  mov     rcx, rdi
0x1801020f1  mov     rax, [rax+38h]
0x1801020f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801020fa  mov     ebx, eax
0x1801020fc  test    eax, eax
0x1801020fe  jnz     loc_1801021BD
0x180102104  mov     rax, [rdi+150h]
0x18010210b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180102112  jnz     short loc_180102128
0x180102114  mov     rax, [rdi+158h]
0x18010211b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180102122  jz      loc_1801021BD
0x180102128  mov     rdx, r12
0x18010212b  mov     rcx, rdi
0x18010212e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x180102133  mov     ebx, eax
0x180102135  test    eax, eax
0x180102137  jnz     loc_1801021BD
0x18010213d  mov     rcx, r14; pwk
0x180102140  call    cs:__imp_SubmitThreadpoolWork
0x180102147  nop     dword ptr [rax+rax+00h]
0x18010214c  jmp     loc_18010220B
0x180102151  mov     rax, [rdi]
0x180102154  mov     r8, r13
0x180102157  mov     rdx, [rsi+8]
0x18010215b  mov     rcx, rdi
0x18010215e  mov     rax, [rax+10h]
0x180102162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102167  mov     rax, [rdi]
0x18010216a  mov     rdx, r12
0x18010216d  mov     rcx, rdi
0x180102170  mov     rax, [rax+30h]
0x180102174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102179  mov     ebx, eax
0x18010217b  test    eax, eax
0x18010217d  jz      short loc_180102184
0x18010217f  cmp     eax, 7
0x180102182  jnz     short loc_1801021BD
0x180102184  mov     rax, [rdi]
0x180102187  mov     rdx, r12
0x18010218a  mov     rcx, rdi
0x18010218d  mov     rax, [rax+28h]
0x180102191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102196  mov     ebx, eax
0x180102198  test    eax, eax
0x18010219a  jz      short loc_1801021A1
0x18010219c  cmp     eax, 7
0x18010219f  jnz     short loc_1801021BD
0x1801021a1  mov     rax, [rdi]
0x1801021a4  mov     rdx, r12
0x1801021a7  mov     rcx, rdi
0x1801021aa  mov     rax, [rax+38h]
0x1801021ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801021b3  jmp     loc_180102064
0x1801021b8  mov     ebx, 4
0x1801021bd  mov     rax, [rdi]
0x1801021c0  mov     edx, 1
0x1801021c5  mov     rcx, rdi
0x1801021c8  mov     rax, [rax]
0x1801021cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801021d0  test    r15, r15
0x1801021d3  jz      short loc_1801021E2
0x1801021d5  mov     edx, 10h
0x1801021da  mov     rcx, r15; Block
0x1801021dd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801021e2  mov     rcx, [rbp+TokenHandle]; hObject
0x1801021e6  test    rcx, rcx
0x1801021e9  jz      short loc_1801021F7
0x1801021eb  call    cs:__imp_CloseHandle
0x1801021f2  nop     dword ptr [rax+rax+00h]
0x1801021f7  test    r14, r14
0x1801021fa  jz      short loc_18010220B
0x1801021fc  mov     rcx, r14; pwk
0x1801021ff  call    cs:__imp_CloseThreadpoolWork
0x180102206  nop     dword ptr [rax+rax+00h]
0x18010220b  mov     eax, ebx
0x18010220d  mov     rcx, [rbp+var_8]
0x180102211  xor     rcx, rsp; StackCookie
0x180102214  call    __security_check_cookie
0x180102219  mov     rbx, [rsp+80h+arg_18]
0x180102221  add     rsp, 80h
0x180102228  pop     r15
0x18010222a  pop     r14
0x18010222c  pop     r13
0x18010222e  pop     r12
0x180102230  pop     rdi
0x180102231  pop     rsi
0x180102232  pop     rbp
0x180102233  retn
```
