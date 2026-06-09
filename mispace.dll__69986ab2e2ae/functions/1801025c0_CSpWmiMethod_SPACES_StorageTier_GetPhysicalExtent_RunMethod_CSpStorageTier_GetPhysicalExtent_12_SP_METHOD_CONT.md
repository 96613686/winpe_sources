# CSpWmiMethod<_SPACES_StorageTier_GetPhysicalExtent>::RunMethod<CSpStorageTier::GetPhysicalExtent,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1801025c0`
- end: `0x18010293d`
- name: `??$RunMethod@VGetPhysicalExtent@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_GetPhysicalExtent@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1801025c0`
- `0x180103f40`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010279e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010279e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180102773`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180102773`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010278e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18010278e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180102753`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180102753`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180102848`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180102848`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180102907`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180102907`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801028f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801028f3`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_GetPhysicalExtent>::RunMethod<CSpStorageTier::GetPhysicalExtent,12>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 PhysicalExtent; // rax
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
  CSpStorageTier::GetPhysicalExtent *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::GetPhysicalExtent *)operator new(0x170u);
  PhysicalExtent = CSpStorageTier::GetPhysicalExtent::GetPhysicalExtent(v25);
  v8 = PhysicalExtent;
  if ( PhysicalExtent )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)PhysicalExtent + 8LL))(PhysicalExtent, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageTier::GetPhysicalExtent *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18033F959,
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
0x1801025c0  mov     [rsp-38h+arg_18], rbx
0x1801025c5  push    rbp
0x1801025c6  push    rsi
0x1801025c7  push    rdi
0x1801025c8  push    r12
0x1801025ca  push    r13
0x1801025cc  push    r14
0x1801025ce  push    r15
0x1801025d0  mov     rbp, rsp
0x1801025d3  sub     rsp, 80h
0x1801025da  mov     rax, cs:__security_cookie
0x1801025e1  xor     rax, rsp
0x1801025e4  mov     [rbp+var_8], rax
0x1801025e8  xor     eax, eax
0x1801025ea  mov     rsi, rcx
0x1801025ed  xorps   xmm0, xmm0
0x1801025f0  mov     [rbp+var_10], eax
0x1801025f3  mov     ecx, 170h; Size
0x1801025f8  mov     [rbp+var_40], eax
0x1801025fb  movups  [rbp+var_20], xmm0
0x1801025ff  mov     [rbp+TokenHandle], rax
0x180102603  mov     r12, r8
0x180102606  mov     r13, rdx
0x180102609  xor     r14d, r14d
0x18010260c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180102611  mov     rcx, rax; this
0x180102614  mov     [rbp+var_28], rax
0x180102618  call    ??0GetPhysicalExtent@CSpStorageTier@@QEAA@XZ; CSpStorageTier::GetPhysicalExtent::GetPhysicalExtent(void)
0x18010261d  mov     rdi, rax
0x180102620  test    rax, rax
0x180102623  jnz     short loc_18010262D
0x180102625  lea     ebx, [rax+1Bh]
0x180102628  jmp     loc_1801028EA
0x18010262d  mov     rax, [rax]
0x180102630  mov     rdx, rsi
0x180102633  mov     rcx, rdi
0x180102636  xor     r15d, r15d
0x180102639  mov     rax, [rax+8]
0x18010263d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102642  lea     rcx, [rbp+var_40]
0x180102646  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x18010264b  mov     [rdi+1Ch], eax
0x18010264e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x180102652  mov     ecx, [rsi+14h]; unsigned int
0x180102655  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x18010265a  mov     eax, cs:dword_18039EB68
0x180102660  cmp     eax, 5
0x180102663  jbe     short loc_1801026D3
0x180102665  mov     rdx, 400000000000h
0x18010266f  lea     rcx, dword_18039EB68
0x180102676  call    _tlgKeywordOn
0x18010267b  test    al, al
0x18010267d  jz      short loc_1801026D3
0x18010267f  mov     eax, [rbp+var_40]
0x180102682  lea     rdx, byte_18033F959
0x180102689  xor     ecx, ecx
0x18010268b  cmp     [rdi+1Ch], eax
0x18010268e  movzx   eax, word ptr [rbp+var_10]
0x180102692  mov     word ptr [rbp+var_40], ax
0x180102696  setnz   cl
0x180102699  mov     eax, [rsi+14h]
0x18010269c  mov     [rbp+var_38], eax
0x18010269f  lea     rax, [rbp+var_20]
0x1801026a3  mov     [rbp+var_28], rax
0x1801026a7  lea     rax, [rbp+var_3C]
0x1801026ab  mov     [rsp+80h+var_48], rax
0x1801026b0  lea     rax, [rbp+var_40]
0x1801026b4  mov     [rsp+80h+var_50], rax
0x1801026b9  lea     rax, [rbp+var_38]
0x1801026bd  mov     [rsp+80h+var_58], rax
0x1801026c2  lea     rax, [rbp+var_28]
0x1801026c6  mov     [rsp+80h+var_60], rax
0x1801026cb  mov     [rbp+var_3C], ecx
0x1801026ce  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1801026d3  mov     rcx, [rsi]
0x1801026d6  test    rcx, rcx
0x1801026d9  jz      loc_1801028C0
0x1801026df  mov     rax, [rcx]
0x1801026e2  test    rax, rax
0x1801026e5  jz      loc_1801028C0
0x1801026eb  mov     rax, [rax+18h]
0x1801026ef  lea     r8, [rdi+20h]
0x1801026f3  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1801026fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801026ff  mov     ebx, eax
0x180102701  test    eax, eax
0x180102703  jnz     loc_1801028C5
0x180102709  cmp     [rsi+10h], r14d
0x18010270d  jz      loc_180102859
0x180102713  lea     rbx, [rdi+148h]
0x18010271a  mov     rcx, rbx
0x18010271d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180102722  mov     rcx, rbx; struct CSpJobMgr **
0x180102725  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x18010272a  test    eax, eax
0x18010272c  jnz     short loc_180102736
0x18010272e  lea     ebx, [rax+1Ch]
0x180102731  jmp     loc_1801028C5
0x180102736  mov     ecx, 10h; Size
0x18010273b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180102740  xor     r8d, r8d; pcbe
0x180102743  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18010274a  mov     rdx, rax; pv
0x18010274d  mov     r15, rax
0x180102750  mov     [rax], rdi
0x180102753  call    cs:__imp_CreateThreadpoolWork
0x18010275a  nop     dword ptr [rax+rax+00h]
0x18010275f  mov     r14, rax
0x180102762  test    rax, rax
0x180102765  jnz     short loc_180102773
0x180102767  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18010276c  mov     ebx, eax
0x18010276e  jmp     loc_1801028C5
0x180102773  call    cs:__imp_GetCurrentThread
0x18010277a  nop     dword ptr [rax+rax+00h]
0x18010277f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180102783  xor     r8d, r8d; OpenAsSelf
0x180102786  mov     rcx, rax; ThreadHandle
0x180102789  mov     edx, 2000Ch; DesiredAccess
0x18010278e  call    cs:__imp_OpenThreadToken
0x180102795  nop     dword ptr [rax+rax+00h]
0x18010279a  test    eax, eax
0x18010279c  jnz     short loc_1801027B1
0x18010279e  call    cs:__imp_GetLastError
0x1801027a5  nop     dword ptr [rax+rax+00h]
0x1801027aa  cmp     eax, 3F0h
0x1801027af  jnz     short loc_180102767
0x1801027b1  mov     rax, [rbp+TokenHandle]
0x1801027b5  mov     r8, r13
0x1801027b8  mov     [r15+8], rax
0x1801027bc  mov     rcx, rdi
0x1801027bf  mov     rax, [rdi]
0x1801027c2  mov     rdx, [rsi+8]
0x1801027c6  mov     rax, [rax+18h]
0x1801027ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801027cf  mov     rax, [rdi]
0x1801027d2  mov     rdx, r12
0x1801027d5  mov     rcx, rdi
0x1801027d8  mov     rax, [rax+28h]
0x1801027dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801027e1  mov     ebx, eax
0x1801027e3  test    eax, eax
0x1801027e5  jz      short loc_1801027F0
0x1801027e7  cmp     eax, 7
0x1801027ea  jnz     loc_1801028C5
0x1801027f0  mov     rax, [rdi]
0x1801027f3  mov     rdx, r12
0x1801027f6  mov     rcx, rdi
0x1801027f9  mov     rax, [rax+38h]
0x1801027fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102802  mov     ebx, eax
0x180102804  test    eax, eax
0x180102806  jnz     loc_1801028C5
0x18010280c  mov     rax, [rdi+150h]
0x180102813  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18010281a  jnz     short loc_180102830
0x18010281c  mov     rax, [rdi+158h]
0x180102823  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18010282a  jz      loc_1801028C5
0x180102830  mov     rdx, r12
0x180102833  mov     rcx, rdi
0x180102836  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x18010283b  mov     ebx, eax
0x18010283d  test    eax, eax
0x18010283f  jnz     loc_1801028C5
0x180102845  mov     rcx, r14; pwk
0x180102848  call    cs:__imp_SubmitThreadpoolWork
0x18010284f  nop     dword ptr [rax+rax+00h]
0x180102854  jmp     loc_180102913
0x180102859  mov     rax, [rdi]
0x18010285c  mov     r8, r13
0x18010285f  mov     rdx, [rsi+8]
0x180102863  mov     rcx, rdi
0x180102866  mov     rax, [rax+10h]
0x18010286a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010286f  mov     rax, [rdi]
0x180102872  mov     rdx, r12
0x180102875  mov     rcx, rdi
0x180102878  mov     rax, [rax+30h]
0x18010287c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102881  mov     ebx, eax
0x180102883  test    eax, eax
0x180102885  jz      short loc_18010288C
0x180102887  cmp     eax, 7
0x18010288a  jnz     short loc_1801028C5
0x18010288c  mov     rax, [rdi]
0x18010288f  mov     rdx, r12
0x180102892  mov     rcx, rdi
0x180102895  mov     rax, [rax+28h]
0x180102899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010289e  mov     ebx, eax
0x1801028a0  test    eax, eax
0x1801028a2  jz      short loc_1801028A9
0x1801028a4  cmp     eax, 7
0x1801028a7  jnz     short loc_1801028C5
0x1801028a9  mov     rax, [rdi]
0x1801028ac  mov     rdx, r12
0x1801028af  mov     rcx, rdi
0x1801028b2  mov     rax, [rax+38h]
0x1801028b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801028bb  jmp     loc_18010276C
0x1801028c0  mov     ebx, 4
0x1801028c5  mov     rax, [rdi]
0x1801028c8  mov     edx, 1
0x1801028cd  mov     rcx, rdi
0x1801028d0  mov     rax, [rax]
0x1801028d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801028d8  test    r15, r15
0x1801028db  jz      short loc_1801028EA
0x1801028dd  mov     edx, 10h
0x1801028e2  mov     rcx, r15; Block
0x1801028e5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801028ea  mov     rcx, [rbp+TokenHandle]; hObject
0x1801028ee  test    rcx, rcx
0x1801028f1  jz      short loc_1801028FF
0x1801028f3  call    cs:__imp_CloseHandle
0x1801028fa  nop     dword ptr [rax+rax+00h]
0x1801028ff  test    r14, r14
0x180102902  jz      short loc_180102913
0x180102904  mov     rcx, r14; pwk
0x180102907  call    cs:__imp_CloseThreadpoolWork
0x18010290e  nop     dword ptr [rax+rax+00h]
0x180102913  mov     eax, ebx
0x180102915  mov     rcx, [rbp+var_8]
0x180102919  xor     rcx, rsp; StackCookie
0x18010291c  call    __security_check_cookie
0x180102921  mov     rbx, [rsp+80h+arg_18]
0x180102929  add     rsp, 80h
0x180102930  pop     r15
0x180102932  pop     r14
0x180102934  pop     r13
0x180102936  pop     r12
0x180102938  pop     rdi
0x180102939  pop     rsi
0x18010293a  pop     rbp
0x18010293b  retn
```
