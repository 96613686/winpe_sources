# CSpWmiMethod<_MI_Instance>::RunMethod<CSpPhysicalDisk::Maintenance,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800f2164`
- end: `0x1800f24f4`
- name: `??$RunMethod@VMaintenance@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `912`
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
- `0x18006de84`
- `0x1800f2164`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2353`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f2328`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f2328`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f2343`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f2343`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f2308`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f2308`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f23fe`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f23fe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f24be`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f24be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f24aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f24aa`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpPhysicalDisk::Maintenance,4>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int128 **v4; // r14
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int128 *v8; // rdi
  int v9; // r8d
  int v10; // r9d
  bool v11; // zf
  __int64 v12; // rcx
  unsigned int v13; // ebx
  enum _MI_Result v14; // eax
  HANDLE CurrentThread; // rax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  int v20; // [rsp+40h] [rbp-40h] BYREF
  BOOL v21; // [rsp+44h] [rbp-3Ch] BYREF
  int v22; // [rsp+48h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-30h] BYREF
  __int128 *v24; // [rsp+58h] [rbp-28h] BYREF
  __int128 v25; // [rsp+60h] [rbp-20h] BYREF
  int v26; // [rsp+70h] [rbp-10h]

  v20 = 0;
  TokenHandle = 0;
  v26 = 0;
  v4 = 0;
  ThreadpoolWork = 0;
  v25 = 0;
  v24 = (__int128 *)operator new(0x178u);
  v8 = v24;
  CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(v24);
  *(_QWORD *)v24 = &CSpPhysicalDisk::Maintenance::`vftable';
  *((_DWORD *)v8 + 90) = 0;
  *((_WORD *)v8 + 182) = 0;
  (*(void (__fastcall **)(__int128 *, __int64 *))(*(_QWORD *)v8 + 8LL))(v8, a1);
  *((_DWORD *)v8 + 7) = _GetSubsystemVersion(&v20);
  WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v25);
  if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
  {
    v11 = *((_DWORD *)v8 + 7) == v20;
    LOWORD(v20) = v26;
    v22 = *((_DWORD *)a1 + 5);
    v24 = &v25;
    v21 = !v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v21,
      (unsigned int)byte_18033D55D,
      v9,
      v10,
      (__int64)&v24,
      (__int64)&v22,
      (__int64)&v20,
      (__int64)&v21);
  }
  v12 = *a1;
  if ( !*a1 || !*(_QWORD *)v12 )
  {
    v13 = 4;
    goto LABEL_28;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD *))(*(_QWORD *)v12 + 24LL))(
          v12,
          &MSFT_StorageExtendedStatus_rtti,
          (_QWORD *)v8 + 4);
  if ( !v13 )
  {
    if ( *((_DWORD *)a1 + 4) )
    {
      CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release((char *)v8 + 328);
      if ( !(unsigned int)CSpJobMgr::GetInstance((struct CSpJobMgr **)v8 + 41) )
      {
        v13 = 28;
        goto LABEL_28;
      }
      v4 = (__int128 **)operator new(0x10u);
      *v4 = v8;
      ThreadpoolWork = CreateThreadpoolWork(
                         CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::ResumeMethodWorker,
                         v4,
                         0);
      if ( ThreadpoolWork )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) || GetLastError() == 1008 )
        {
          v4[1] = (__int128 *)TokenHandle;
          (*(void (__fastcall **)(__int128 *, __int64, __int64))(*(_QWORD *)v8 + 24LL))(v8, a1[1], a2);
          v16 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
          v13 = v16;
          if ( !v16 || v16 == 7 )
          {
            v13 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
            if ( !v13
              && (*((_QWORD *)v8 + 42) != *(_QWORD *)&GUID_NULL.Data1
               || *((_QWORD *)v8 + 43) != *(_QWORD *)GUID_NULL.Data4) )
            {
              v13 = CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(v8, a3);
              if ( !v13 )
              {
                SubmitThreadpoolWork(ThreadpoolWork);
                return v13;
              }
            }
          }
          goto LABEL_28;
        }
      }
      v14 = GleToMiResult();
    }
    else
    {
      (*(void (__fastcall **)(__int128 *, __int64, __int64))(*(_QWORD *)v8 + 16LL))(v8, a1[1], a2);
      v17 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 48LL))(v8, a3);
      v13 = v17;
      if ( v17 && v17 != 7 )
        goto LABEL_28;
      v18 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
      v13 = v18;
      if ( v18 )
      {
        if ( v18 != 7 )
          goto LABEL_28;
      }
      v14 = (*(unsigned int (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
    }
    v13 = v14;
  }
LABEL_28:
  (**(void (__fastcall ***)(__int128 *, __int64))v8)(v8, 1);
  if ( v4 )
    operator delete(v4);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v13;
}

```

## disassembly

```asm
0x1800f2164  mov     [rsp-38h+arg_18], rbx
0x1800f2169  push    rbp
0x1800f216a  push    rsi
0x1800f216b  push    rdi
0x1800f216c  push    r12
0x1800f216e  push    r13
0x1800f2170  push    r14
0x1800f2172  push    r15
0x1800f2174  mov     rbp, rsp
0x1800f2177  sub     rsp, 80h
0x1800f217e  mov     rax, cs:__security_cookie
0x1800f2185  xor     rax, rsp
0x1800f2188  mov     [rbp+var_8], rax
0x1800f218c  xor     ebx, ebx
0x1800f218e  mov     r12, rcx
0x1800f2191  xorps   xmm0, xmm0
0x1800f2194  mov     [rbp+var_40], ebx
0x1800f2197  xor     eax, eax
0x1800f2199  mov     [rbp+TokenHandle], rbx
0x1800f219d  mov     ecx, 178h; Size
0x1800f21a2  mov     [rbp+var_10], eax
0x1800f21a5  mov     r14d, ebx
0x1800f21a8  mov     esi, ebx
0x1800f21aa  movups  [rbp+var_20], xmm0
0x1800f21ae  mov     r15, r8
0x1800f21b1  mov     r13, rdx
0x1800f21b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f21b9  mov     rcx, rax
0x1800f21bc  mov     [rbp+var_28], rax
0x1800f21c0  mov     rdi, rax
0x1800f21c3  call    ??0?$CSpWmiMethod@U_MI_Instance@@@@QEAA@XZ; CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(void)
0x1800f21c8  lea     rax, ??_7Maintenance@CSpPhysicalDisk@@6B@; const CSpPhysicalDisk::Maintenance::`vftable'
0x1800f21cf  mov     rdx, r12
0x1800f21d2  mov     [rdi], rax
0x1800f21d5  mov     rcx, rdi
0x1800f21d8  mov     [rdi+168h], ebx
0x1800f21de  mov     [rdi+16Ch], bx
0x1800f21e5  mov     rax, [rdi]
0x1800f21e8  mov     rax, [rax+8]
0x1800f21ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f21f1  lea     rcx, [rbp+var_40]
0x1800f21f5  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800f21fa  mov     [rdi+1Ch], eax
0x1800f21fd  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800f2201  mov     ecx, [r12+14h]; unsigned int
0x1800f2206  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800f220b  mov     eax, cs:dword_18039EB68
0x1800f2211  cmp     eax, 5
0x1800f2214  jbe     short loc_1800F2286
0x1800f2216  mov     rdx, 400000000000h
0x1800f2220  lea     rcx, dword_18039EB68
0x1800f2227  call    _tlgKeywordOn
0x1800f222c  test    al, al
0x1800f222e  jz      short loc_1800F2286
0x1800f2230  mov     eax, [rbp+var_40]
0x1800f2233  lea     rdx, byte_18033D55D
0x1800f223a  cmp     [rdi+1Ch], eax
0x1800f223d  mov     ecx, ebx
0x1800f223f  movzx   eax, word ptr [rbp+var_10]
0x1800f2243  mov     word ptr [rbp+var_40], ax
0x1800f2247  setnz   cl
0x1800f224a  mov     eax, [r12+14h]
0x1800f224f  mov     [rbp+var_38], eax
0x1800f2252  lea     rax, [rbp+var_20]
0x1800f2256  mov     [rbp+var_28], rax
0x1800f225a  lea     rax, [rbp+var_3C]
0x1800f225e  mov     [rsp+80h+var_48], rax
0x1800f2263  lea     rax, [rbp+var_40]
0x1800f2267  mov     [rsp+80h+var_50], rax
0x1800f226c  lea     rax, [rbp+var_38]
0x1800f2270  mov     [rsp+80h+var_58], rax
0x1800f2275  lea     rax, [rbp+var_28]
0x1800f2279  mov     [rsp+80h+var_60], rax
0x1800f227e  mov     [rbp+var_3C], ecx
0x1800f2281  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800f2286  mov     rcx, [r12]
0x1800f228a  test    rcx, rcx
0x1800f228d  jz      loc_1800F2477
0x1800f2293  mov     rax, [rcx]
0x1800f2296  test    rax, rax
0x1800f2299  jz      loc_1800F2477
0x1800f229f  mov     rax, [rax+18h]
0x1800f22a3  lea     r8, [rdi+20h]
0x1800f22a7  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800f22ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f22b3  mov     ebx, eax
0x1800f22b5  test    eax, eax
0x1800f22b7  jnz     loc_1800F247C
0x1800f22bd  cmp     [r12+10h], esi
0x1800f22c2  jz      loc_1800F240F
0x1800f22c8  lea     rbx, [rdi+148h]
0x1800f22cf  mov     rcx, rbx
0x1800f22d2  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800f22d7  mov     rcx, rbx; struct CSpJobMgr **
0x1800f22da  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800f22df  test    eax, eax
0x1800f22e1  jnz     short loc_1800F22EB
0x1800f22e3  lea     ebx, [rax+1Ch]
0x1800f22e6  jmp     loc_1800F247C
0x1800f22eb  mov     ecx, 10h; Size
0x1800f22f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f22f5  xor     r8d, r8d; pcbe
0x1800f22f8  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f22ff  mov     rdx, rax; pv
0x1800f2302  mov     r14, rax
0x1800f2305  mov     [rax], rdi
0x1800f2308  call    cs:__imp_CreateThreadpoolWork
0x1800f230f  nop     dword ptr [rax+rax+00h]
0x1800f2314  mov     rsi, rax
0x1800f2317  test    rax, rax
0x1800f231a  jnz     short loc_1800F2328
0x1800f231c  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800f2321  mov     ebx, eax
0x1800f2323  jmp     loc_1800F247C
0x1800f2328  call    cs:__imp_GetCurrentThread
0x1800f232f  nop     dword ptr [rax+rax+00h]
0x1800f2334  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f2338  xor     r8d, r8d; OpenAsSelf
0x1800f233b  mov     rcx, rax; ThreadHandle
0x1800f233e  mov     edx, 2000Ch; DesiredAccess
0x1800f2343  call    cs:__imp_OpenThreadToken
0x1800f234a  nop     dword ptr [rax+rax+00h]
0x1800f234f  test    eax, eax
0x1800f2351  jnz     short loc_1800F2366
0x1800f2353  call    cs:__imp_GetLastError
0x1800f235a  nop     dword ptr [rax+rax+00h]
0x1800f235f  cmp     eax, 3F0h
0x1800f2364  jnz     short loc_1800F231C
0x1800f2366  mov     rax, [rbp+TokenHandle]
0x1800f236a  mov     r8, r13
0x1800f236d  mov     [r14+8], rax
0x1800f2371  mov     rcx, rdi
0x1800f2374  mov     rax, [rdi]
0x1800f2377  mov     rdx, [r12+8]
0x1800f237c  mov     rax, [rax+18h]
0x1800f2380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2385  mov     rax, [rdi]
0x1800f2388  mov     rdx, r15
0x1800f238b  mov     rcx, rdi
0x1800f238e  mov     rax, [rax+28h]
0x1800f2392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2397  mov     ebx, eax
0x1800f2399  test    eax, eax
0x1800f239b  jz      short loc_1800F23A6
0x1800f239d  cmp     eax, 7
0x1800f23a0  jnz     loc_1800F247C
0x1800f23a6  mov     rax, [rdi]
0x1800f23a9  mov     rdx, r15
0x1800f23ac  mov     rcx, rdi
0x1800f23af  mov     rax, [rax+38h]
0x1800f23b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f23b8  mov     ebx, eax
0x1800f23ba  test    eax, eax
0x1800f23bc  jnz     loc_1800F247C
0x1800f23c2  mov     rax, [rdi+150h]
0x1800f23c9  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800f23d0  jnz     short loc_1800F23E6
0x1800f23d2  mov     rax, [rdi+158h]
0x1800f23d9  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800f23e0  jz      loc_1800F247C
0x1800f23e6  mov     rdx, r15
0x1800f23e9  mov     rcx, rdi
0x1800f23ec  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800f23f1  mov     ebx, eax
0x1800f23f3  test    eax, eax
0x1800f23f5  jnz     loc_1800F247C
0x1800f23fb  mov     rcx, rsi; pwk
0x1800f23fe  call    cs:__imp_SubmitThreadpoolWork
0x1800f2405  nop     dword ptr [rax+rax+00h]
0x1800f240a  jmp     loc_1800F24CA
0x1800f240f  mov     rax, [rdi]
0x1800f2412  mov     r8, r13
0x1800f2415  mov     rdx, [r12+8]
0x1800f241a  mov     rcx, rdi
0x1800f241d  mov     rax, [rax+10h]
0x1800f2421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2426  mov     rax, [rdi]
0x1800f2429  mov     rdx, r15
0x1800f242c  mov     rcx, rdi
0x1800f242f  mov     rax, [rax+30h]
0x1800f2433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2438  mov     ebx, eax
0x1800f243a  test    eax, eax
0x1800f243c  jz      short loc_1800F2443
0x1800f243e  cmp     eax, 7
0x1800f2441  jnz     short loc_1800F247C
0x1800f2443  mov     rax, [rdi]
0x1800f2446  mov     rdx, r15
0x1800f2449  mov     rcx, rdi
0x1800f244c  mov     rax, [rax+28h]
0x1800f2450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2455  mov     ebx, eax
0x1800f2457  test    eax, eax
0x1800f2459  jz      short loc_1800F2460
0x1800f245b  cmp     eax, 7
0x1800f245e  jnz     short loc_1800F247C
0x1800f2460  mov     rax, [rdi]
0x1800f2463  mov     rdx, r15
0x1800f2466  mov     rcx, rdi
0x1800f2469  mov     rax, [rax+38h]
0x1800f246d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2472  jmp     loc_1800F2321
0x1800f2477  mov     ebx, 4
0x1800f247c  mov     rax, [rdi]
0x1800f247f  mov     edx, 1
0x1800f2484  mov     rcx, rdi
0x1800f2487  mov     rax, [rax]
0x1800f248a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f248f  test    r14, r14
0x1800f2492  jz      short loc_1800F24A1
0x1800f2494  mov     edx, 10h
0x1800f2499  mov     rcx, r14; Block
0x1800f249c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f24a1  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f24a5  test    rcx, rcx
0x1800f24a8  jz      short loc_1800F24B6
0x1800f24aa  call    cs:__imp_CloseHandle
0x1800f24b1  nop     dword ptr [rax+rax+00h]
0x1800f24b6  test    rsi, rsi
0x1800f24b9  jz      short loc_1800F24CA
0x1800f24bb  mov     rcx, rsi; pwk
0x1800f24be  call    cs:__imp_CloseThreadpoolWork
0x1800f24c5  nop     dword ptr [rax+rax+00h]
0x1800f24ca  mov     eax, ebx
0x1800f24cc  mov     rcx, [rbp+var_8]
0x1800f24d0  xor     rcx, rsp; StackCookie
0x1800f24d3  call    __security_check_cookie
0x1800f24d8  mov     rbx, [rsp+80h+arg_18]
0x1800f24e0  add     rsp, 80h
0x1800f24e7  pop     r15
0x1800f24e9  pop     r14
0x1800f24eb  pop     r13
0x1800f24ed  pop     r12
0x1800f24ef  pop     rdi
0x1800f24f0  pop     rsi
0x1800f24f1  pop     rbp
0x1800f24f2  retn
```
