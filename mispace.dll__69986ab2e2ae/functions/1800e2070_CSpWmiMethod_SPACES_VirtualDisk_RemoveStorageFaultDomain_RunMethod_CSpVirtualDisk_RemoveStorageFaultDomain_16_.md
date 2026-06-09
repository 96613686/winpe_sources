# CSpWmiMethod<_SPACES_VirtualDisk_RemoveStorageFaultDomain>::RunMethod<CSpVirtualDisk::RemoveStorageFaultDomain,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e2070`
- end: `0x1800e23ed`
- name: `??$RunMethod@VRemoveStorageFaultDomain@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_RemoveStorageFaultDomain@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800e2070`
- `0x1800e4034`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e224e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e224e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e2223`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e2223`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e223e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e223e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e2203`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e2203`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e22f8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e22f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e23b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e23b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e23a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e23a3`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_RemoveStorageFaultDomain>::RunMethod<CSpVirtualDisk::RemoveStorageFaultDomain,16>(
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
  CSpVirtualDisk::RemoveStorageFaultDomain *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::RemoveStorageFaultDomain *)operator new(0x160u);
  v7 = CSpVirtualDisk::RemoveStorageFaultDomain::RemoveStorageFaultDomain(v25);
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
      v25 = (CSpVirtualDisk::RemoveStorageFaultDomain *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)word_1803379F2,
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
0x1800e2070  mov     [rsp-38h+arg_18], rbx
0x1800e2075  push    rbp
0x1800e2076  push    rsi
0x1800e2077  push    rdi
0x1800e2078  push    r12
0x1800e207a  push    r13
0x1800e207c  push    r14
0x1800e207e  push    r15
0x1800e2080  mov     rbp, rsp
0x1800e2083  sub     rsp, 80h
0x1800e208a  mov     rax, cs:__security_cookie
0x1800e2091  xor     rax, rsp
0x1800e2094  mov     [rbp+var_8], rax
0x1800e2098  xor     eax, eax
0x1800e209a  mov     rsi, rcx
0x1800e209d  xorps   xmm0, xmm0
0x1800e20a0  mov     [rbp+var_10], eax
0x1800e20a3  mov     ecx, 160h; Size
0x1800e20a8  mov     [rbp+var_40], eax
0x1800e20ab  movups  [rbp+var_20], xmm0
0x1800e20af  mov     [rbp+TokenHandle], rax
0x1800e20b3  mov     r12, r8
0x1800e20b6  mov     r13, rdx
0x1800e20b9  xor     r14d, r14d
0x1800e20bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e20c1  mov     rcx, rax; this
0x1800e20c4  mov     [rbp+var_28], rax
0x1800e20c8  call    ??0RemoveStorageFaultDomain@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::RemoveStorageFaultDomain::RemoveStorageFaultDomain(void)
0x1800e20cd  mov     rdi, rax
0x1800e20d0  test    rax, rax
0x1800e20d3  jnz     short loc_1800E20DD
0x1800e20d5  lea     ebx, [rax+1Bh]
0x1800e20d8  jmp     loc_1800E239A
0x1800e20dd  mov     rax, [rax]
0x1800e20e0  mov     rdx, rsi
0x1800e20e3  mov     rcx, rdi
0x1800e20e6  xor     r15d, r15d
0x1800e20e9  mov     rax, [rax+8]
0x1800e20ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e20f2  lea     rcx, [rbp+var_40]
0x1800e20f6  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e20fb  mov     [rdi+1Ch], eax
0x1800e20fe  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e2102  mov     ecx, [rsi+14h]; unsigned int
0x1800e2105  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e210a  mov     eax, cs:dword_18039EB68
0x1800e2110  cmp     eax, 5
0x1800e2113  jbe     short loc_1800E2183
0x1800e2115  mov     rdx, 400000000000h
0x1800e211f  lea     rcx, dword_18039EB68
0x1800e2126  call    _tlgKeywordOn
0x1800e212b  test    al, al
0x1800e212d  jz      short loc_1800E2183
0x1800e212f  mov     eax, [rbp+var_40]
0x1800e2132  lea     rdx, word_1803379F2
0x1800e2139  xor     ecx, ecx
0x1800e213b  cmp     [rdi+1Ch], eax
0x1800e213e  movzx   eax, word ptr [rbp+var_10]
0x1800e2142  mov     word ptr [rbp+var_40], ax
0x1800e2146  setnz   cl
0x1800e2149  mov     eax, [rsi+14h]
0x1800e214c  mov     [rbp+var_38], eax
0x1800e214f  lea     rax, [rbp+var_20]
0x1800e2153  mov     [rbp+var_28], rax
0x1800e2157  lea     rax, [rbp+var_3C]
0x1800e215b  mov     [rsp+80h+var_48], rax
0x1800e2160  lea     rax, [rbp+var_40]
0x1800e2164  mov     [rsp+80h+var_50], rax
0x1800e2169  lea     rax, [rbp+var_38]
0x1800e216d  mov     [rsp+80h+var_58], rax
0x1800e2172  lea     rax, [rbp+var_28]
0x1800e2176  mov     [rsp+80h+var_60], rax
0x1800e217b  mov     [rbp+var_3C], ecx
0x1800e217e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e2183  mov     rcx, [rsi]
0x1800e2186  test    rcx, rcx
0x1800e2189  jz      loc_1800E2370
0x1800e218f  mov     rax, [rcx]
0x1800e2192  test    rax, rax
0x1800e2195  jz      loc_1800E2370
0x1800e219b  mov     rax, [rax+18h]
0x1800e219f  lea     r8, [rdi+20h]
0x1800e21a3  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e21aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e21af  mov     ebx, eax
0x1800e21b1  test    eax, eax
0x1800e21b3  jnz     loc_1800E2375
0x1800e21b9  cmp     [rsi+10h], r14d
0x1800e21bd  jz      loc_1800E2309
0x1800e21c3  lea     rbx, [rdi+148h]
0x1800e21ca  mov     rcx, rbx
0x1800e21cd  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e21d2  mov     rcx, rbx; struct CSpJobMgr **
0x1800e21d5  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e21da  test    eax, eax
0x1800e21dc  jnz     short loc_1800E21E6
0x1800e21de  lea     ebx, [rax+1Ch]
0x1800e21e1  jmp     loc_1800E2375
0x1800e21e6  mov     ecx, 10h; Size
0x1800e21eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e21f0  xor     r8d, r8d; pcbe
0x1800e21f3  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e21fa  mov     rdx, rax; pv
0x1800e21fd  mov     r15, rax
0x1800e2200  mov     [rax], rdi
0x1800e2203  call    cs:__imp_CreateThreadpoolWork
0x1800e220a  nop     dword ptr [rax+rax+00h]
0x1800e220f  mov     r14, rax
0x1800e2212  test    rax, rax
0x1800e2215  jnz     short loc_1800E2223
0x1800e2217  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e221c  mov     ebx, eax
0x1800e221e  jmp     loc_1800E2375
0x1800e2223  call    cs:__imp_GetCurrentThread
0x1800e222a  nop     dword ptr [rax+rax+00h]
0x1800e222f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e2233  xor     r8d, r8d; OpenAsSelf
0x1800e2236  mov     rcx, rax; ThreadHandle
0x1800e2239  mov     edx, 2000Ch; DesiredAccess
0x1800e223e  call    cs:__imp_OpenThreadToken
0x1800e2245  nop     dword ptr [rax+rax+00h]
0x1800e224a  test    eax, eax
0x1800e224c  jnz     short loc_1800E2261
0x1800e224e  call    cs:__imp_GetLastError
0x1800e2255  nop     dword ptr [rax+rax+00h]
0x1800e225a  cmp     eax, 3F0h
0x1800e225f  jnz     short loc_1800E2217
0x1800e2261  mov     rax, [rbp+TokenHandle]
0x1800e2265  mov     r8, r13
0x1800e2268  mov     [r15+8], rax
0x1800e226c  mov     rcx, rdi
0x1800e226f  mov     rax, [rdi]
0x1800e2272  mov     rdx, [rsi+8]
0x1800e2276  mov     rax, [rax+18h]
0x1800e227a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e227f  mov     rax, [rdi]
0x1800e2282  mov     rdx, r12
0x1800e2285  mov     rcx, rdi
0x1800e2288  mov     rax, [rax+28h]
0x1800e228c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2291  mov     ebx, eax
0x1800e2293  test    eax, eax
0x1800e2295  jz      short loc_1800E22A0
0x1800e2297  cmp     eax, 7
0x1800e229a  jnz     loc_1800E2375
0x1800e22a0  mov     rax, [rdi]
0x1800e22a3  mov     rdx, r12
0x1800e22a6  mov     rcx, rdi
0x1800e22a9  mov     rax, [rax+38h]
0x1800e22ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e22b2  mov     ebx, eax
0x1800e22b4  test    eax, eax
0x1800e22b6  jnz     loc_1800E2375
0x1800e22bc  mov     rax, [rdi+150h]
0x1800e22c3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e22ca  jnz     short loc_1800E22E0
0x1800e22cc  mov     rax, [rdi+158h]
0x1800e22d3  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e22da  jz      loc_1800E2375
0x1800e22e0  mov     rdx, r12
0x1800e22e3  mov     rcx, rdi
0x1800e22e6  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e22eb  mov     ebx, eax
0x1800e22ed  test    eax, eax
0x1800e22ef  jnz     loc_1800E2375
0x1800e22f5  mov     rcx, r14; pwk
0x1800e22f8  call    cs:__imp_SubmitThreadpoolWork
0x1800e22ff  nop     dword ptr [rax+rax+00h]
0x1800e2304  jmp     loc_1800E23C3
0x1800e2309  mov     rax, [rdi]
0x1800e230c  mov     r8, r13
0x1800e230f  mov     rdx, [rsi+8]
0x1800e2313  mov     rcx, rdi
0x1800e2316  mov     rax, [rax+10h]
0x1800e231a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e231f  mov     rax, [rdi]
0x1800e2322  mov     rdx, r12
0x1800e2325  mov     rcx, rdi
0x1800e2328  mov     rax, [rax+30h]
0x1800e232c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2331  mov     ebx, eax
0x1800e2333  test    eax, eax
0x1800e2335  jz      short loc_1800E233C
0x1800e2337  cmp     eax, 7
0x1800e233a  jnz     short loc_1800E2375
0x1800e233c  mov     rax, [rdi]
0x1800e233f  mov     rdx, r12
0x1800e2342  mov     rcx, rdi
0x1800e2345  mov     rax, [rax+28h]
0x1800e2349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e234e  mov     ebx, eax
0x1800e2350  test    eax, eax
0x1800e2352  jz      short loc_1800E2359
0x1800e2354  cmp     eax, 7
0x1800e2357  jnz     short loc_1800E2375
0x1800e2359  mov     rax, [rdi]
0x1800e235c  mov     rdx, r12
0x1800e235f  mov     rcx, rdi
0x1800e2362  mov     rax, [rax+38h]
0x1800e2366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e236b  jmp     loc_1800E221C
0x1800e2370  mov     ebx, 4
0x1800e2375  mov     rax, [rdi]
0x1800e2378  mov     edx, 1
0x1800e237d  mov     rcx, rdi
0x1800e2380  mov     rax, [rax]
0x1800e2383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2388  test    r15, r15
0x1800e238b  jz      short loc_1800E239A
0x1800e238d  mov     edx, 10h
0x1800e2392  mov     rcx, r15; Block
0x1800e2395  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e239a  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e239e  test    rcx, rcx
0x1800e23a1  jz      short loc_1800E23AF
0x1800e23a3  call    cs:__imp_CloseHandle
0x1800e23aa  nop     dword ptr [rax+rax+00h]
0x1800e23af  test    r14, r14
0x1800e23b2  jz      short loc_1800E23C3
0x1800e23b4  mov     rcx, r14; pwk
0x1800e23b7  call    cs:__imp_CloseThreadpoolWork
0x1800e23be  nop     dword ptr [rax+rax+00h]
0x1800e23c3  mov     eax, ebx
0x1800e23c5  mov     rcx, [rbp+var_8]
0x1800e23c9  xor     rcx, rsp; StackCookie
0x1800e23cc  call    __security_check_cookie
0x1800e23d1  mov     rbx, [rsp+80h+arg_18]
0x1800e23d9  add     rsp, 80h
0x1800e23e0  pop     r15
0x1800e23e2  pop     r14
0x1800e23e4  pop     r13
0x1800e23e6  pop     r12
0x1800e23e8  pop     rdi
0x1800e23e9  pop     rsi
0x1800e23ea  pop     rbp
0x1800e23eb  retn
```
