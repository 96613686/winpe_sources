# CXaSynch_State_RegisterResourceManager::Enter_State(CXaSynch *)

- ea: `0x1800a2280`
- end: `0x1800a26ae`
- name: `?Enter_State@CXaSynch_State_RegisterResourceManager@@UEAAXPEAVCXaSynch@@@Z`
- size: `1070`
- prototype: `void __fastcall(CXaSynch_State_RegisterResourceManager *__hidden this, struct CXaSynch *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a11ac`

## callees

- `0x1800063b0`
- `0x1800240b0`
- `0x1800846c0`
- `0x18009abb8`
- `0x18009dfc0`
- `0x18009e2d0`
- `0x1800a0fc4`
- `0x1800a109c`
- `0x1800a10d4`
- `0x1800a2280`
- `0x1800a26c0`
- `0x1800a2ce0`
- `0x1800a2d94`
- `0x1800a327c`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a263f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a263f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a25b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a25b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2387`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a23d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2387`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a23d8`
- `MTXCLU!MtxCluGetResourceId` at `0x1800a2377`
- `MTXCLU!MtxCluGetResourceId` at `0x1800a2377`
- `XOLEHLP!DtcGetTransactionManagerExA` at `0x1800a23ce`
- `XOLEHLP!DtcGetTransactionManagerExA` at `0x1800a23ce`

## string_xrefs

- `0x1800a2658`: `com\complus\dtc\dtc\xatm\src\xasynch.cpp`
- `0x1800a2665`: `COpenTask`
- `0x1800a22d6`: `CXaSynch_State_RegisterResourceManager::Enter_State (com\complus\dtc\dtc\xatm\src\xasynch.cpp@3548): g_pCoreTmInstance is NULL`
- `0x1800a2350`: `com\complus\dtc\dtc\xatm\src\xasynch.cpp`

## pseudocode

```c
void __fastcall CXaSynch_State_RegisterResourceManager::Enter_State(
        CXaSynch_State_RegisterResourceManager *this,
        struct CXaSynch *a2)
{
  __int64 v4; // r13
  int v5; // eax
  __int64 v6; // r9
  int ResourceId; // ebx
  unsigned int v8; // ecx
  char *v9; // r8
  int v10; // r9d
  __int64 v11; // rsi
  __int64 v12; // rbx
  unsigned int (__fastcall *v13)(__int64, __int64, __int64, __int64, char *); // rdi
  __int64 v14; // rax
  bool v15; // zf
  void (*v16)(void); // rax
  unsigned int v17; // ecx
  char *v18; // r8
  struct IXaNotifySink *v19; // rax
  COpenTask *v20; // rdi
  unsigned __int64 v21; // rsi
  unsigned int v22; // ebx
  int o_ppvObject; // [rsp+28h] [rbp-41h]
  const wchar_t *v24; // [rsp+30h] [rbp-39h]
  __int64 v25; // [rsp+40h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-21h] BYREF
  struct IXaNotifySink *v27[2]; // [rsp+50h] [rbp-19h] BYREF
  int i_pvConfigParams; // [rsp+60h] [rbp-9h] BYREF
  __int128 v29; // [rsp+64h] [rbp-5h] BYREF
  __int64 v30; // [rsp+74h] [rbp+Bh]

  v27[0] = 0;
  v25 = 0;
  v30 = 0;
  pv = 0;
  v29 = 0;
  if ( !g_pCoreTmInstance )
    DtcInternalErrorW(
      L"CXaSynch_State_RegisterResourceManager::Enter_State (com\\complus\\dtc\\dtc\\xatm\\src\\xasynch.cpp@3548): g_pCore"
       "TmInstance is NULL");
  v4 = *((_QWORD *)a2 + 69);
  i_pvConfigParams = 2;
  if ( (*(unsigned int (__fastcall **)(struct ITmInstance *))(*(_QWORD *)g_pCoreTmInstance + 24LL))(g_pCoreTmInstance) )
  {
    DWORD1(v29) = 1;
    v5 = (*(__int64 (__fastcall **)(struct ITmInstance *, LPVOID *))(*(_QWORD *)g_pCoreTmInstance + 64LL))(
           g_pCoreTmInstance,
           &pv);
    if ( v5 < 0 )
    {
      v6 = 3560;
      v24 = L"Failed to get the resource name.";
      o_ppvObject = v5;
LABEL_6:
      *((_DWORD *)a2 + 147) = -3;
      TraceStringInline(
        13,
        1,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xasynch.cpp",
        v6,
        L"CXaSynch_State_RegisterResourceManager::Enter_State",
        o_ppvObject,
        v24);
LABEL_29:
      CXaSynch_State::Change_State_OpenComplete(this, a2);
      return;
    }
    ResourceId = MtxCluGetResourceId(0, pv, (char *)&v29 + 8);
    if ( ResourceId < 0 )
    {
      CoTaskMemFree(pv);
      v6 = 3570;
      v24 = L"Failed to get the resource id.";
      o_ppvObject = ResourceId;
      goto LABEL_6;
    }
  }
  else
  {
    DWORD1(v29) = 0;
  }
  DtcGetTransactionManagerExA(
    0,
    0,
    &GUID_13741d20_87eb_11ce_8081_0080c758527e,
    0x40000000u,
    &i_pvConfigParams,
    (void **)a2 + 66);
  CoTaskMemFree(pv);
  if ( !*((_QWORD *)a2 + 66) )
  {
LABEL_28:
    *((_DWORD *)a2 + 147) = -3;
    goto LABEL_29;
  }
  (***((void (__fastcall ****)(_QWORD, GUID *, char *))a2 + 66))(
    *((_QWORD *)a2 + 66),
    &GUID_e1cf9b5a_8745_11ce_a9ba_00aa006c3706,
    (char *)a2 + 536);
  if ( !*((_QWORD *)a2 + 67) )
  {
    v10 = 3611;
LABEL_13:
    *((_DWORD *)a2 + 147) = -3;
    XA_TRACE_DSNWARNING(v8, (char *)a2 + 648, v9, v10);
    goto LABEL_29;
  }
  (**(void (__fastcall ***)(struct CXaSynch *, GUID *, __int64 *))a2)(
    a2,
    &GUID_0d563181_defb_11ce_aed1_00aa0051e2c4,
    &v25);
  v11 = *((_QWORD *)a2 + 66);
  v12 = v25;
  v13 = *(unsigned int (__fastcall **)(__int64, __int64, __int64, __int64, char *))(*(_QWORD *)v11 + 24LL);
  v14 = (**((__int64 (__fastcall ***)(char *))a2 + 52))((char *)a2 + 416);
  v15 = v13(v11, v14, v4, v12, (char *)a2 + 520) == -2147167998;
  v16 = *(void (**)(void))(*(_QWORD *)v25 + 16LL);
  if ( v15 )
  {
    v16();
    v25 = 0;
    XA_TRACE_DSNWARNING(v17, (char *)a2 + 648, v18, 3636);
    (*(void (__fastcall **)(CXaSynch_State_RegisterResourceManager *, struct CXaSynch *))(*(_QWORD *)this + 88LL))(
      this,
      a2);
    *((_QWORD *)a2 + 61) = g_CXaSynch_State_RetryOpen;
    CXaSynch_State_RetryOpen::Enter_State((CXaSynch_State_RetryOpen *)g_CXaSynch_State_RetryOpen, a2);
    return;
  }
  if ( !*((_QWORD *)a2 + 65) )
  {
    v16();
    v10 = 3653;
    v25 = 0;
    goto LABEL_13;
  }
  v16();
  v15 = *((_DWORD *)a2 + 143) == 1;
  v25 = 0;
  if ( v15 )
  {
    CXaSynch_State::Change_State_AtomicRecovery(this, a2);
    return;
  }
  v19 = (struct IXaNotifySink *)operator new(0x78u);
  v27[1] = v19;
  v20 = v19;
  if ( !v19 )
  {
    COMMON_TRACE("COpenTask", "com\\complus\\dtc\\dtc\\xatm\\src\\xasynch.cpp", 3674, 0xC000110B);
    goto LABEL_28;
  }
  *((_QWORD *)v19 + 4) = 0;
  *((_QWORD *)v19 + 1) = &UTLink<_IOMGROVERLAP *>::`vftable';
  *((_QWORD *)v19 + 3) = 0;
  *((_DWORD *)v19 + 10) = 0;
  *((_QWORD *)v19 + 6) = 0;
  *(_QWORD *)v19 = &COpenTask::`vftable';
  *((_DWORD *)v19 + 14) = 0;
  *((_QWORD *)v19 + 9) = 0;
  *((_DWORD *)v19 + 20) = 0;
  (**(void (__fastcall ***)(struct CXaSynch *, GUID *, struct IXaNotifySink **))a2)(a2, &IID_IXaNotifySink, v27);
  if ( !v27[0] )
  {
    (*(void (__fastcall **)(COpenTask *, __int64))(*(_QWORD *)v20 + 48LL))(v20, 1);
    goto LABEL_28;
  }
  EnterCriticalSection(&stru_180153898);
  if ( *((_DWORD *)a2 + 143) )
    v21 = 0;
  else
    v21 = CTaskManager::IncrementTaskClock();
  COpenTask::Init(
    v20,
    v27[0],
    *((_DWORD *)a2 + 110),
    *((struct xa_switch_t **)a2 + 69),
    *((char **)a2 + 80),
    (unsigned int *)a2 + 147,
    v21,
    (char *)a2 + 648);
  v22 = *((_DWORD *)a2 + 143) != 0;
  CXaSynch::MarkXaOpenStateListOpen(a2, v21);
  CTaskManager::Enqueue(v20, v22);
  LeaveCriticalSection(&stru_180153898);
  CXaSynch_State::Change_State_Opening(this, a2);
}

```

## disassembly

```asm
0x1800a2280  mov     [rsp-8+arg_10], rbx
0x1800a2285  push    rbp
0x1800a2286  push    rsi
0x1800a2287  push    rdi
0x1800a2288  push    r12
0x1800a228a  push    r13
0x1800a228c  push    r14
0x1800a228e  push    r15
0x1800a2290  lea     rbp, [rsp-27h]
0x1800a2295  sub     rsp, 90h
0x1800a229c  mov     rax, cs:__security_cookie
0x1800a22a3  xor     rax, rsp
0x1800a22a6  mov     [rbp+57h+var_40], rax
0x1800a22aa  xor     edi, edi
0x1800a22ac  mov     r15, rcx
0x1800a22af  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x1800a22b6  xorps   xmm0, xmm0
0x1800a22b9  mov     [rbp+57h+var_70], rdi
0x1800a22bd  mov     r14, rdx
0x1800a22c0  mov     [rbp+57h+var_80], rdi
0x1800a22c4  mov     [rbp+57h+var_4C], rdi
0x1800a22c8  mov     [rbp+57h+pv], rdi
0x1800a22cc  movdqu  [rbp+57h+var_5C], xmm0
0x1800a22d1  test    rcx, rcx
0x1800a22d4  jnz     short loc_1800A22E3
0x1800a22d6  lea     rcx, aCxasynchStateR; "CXaSynch_State_RegisterResourceManager:"...
0x1800a22dd  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800a22e3  mov     r13, [rdx+228h]
0x1800a22ea  mov     [rbp+57h+var_60], 2
0x1800a22f1  mov     rax, [rcx]
0x1800a22f4  mov     rax, [rax+18h]
0x1800a22f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a22fd  mov     esi, 1
0x1800a2302  test    eax, eax
0x1800a2304  jz      loc_1800A23A5
0x1800a230a  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x1800a2311  lea     rdx, [rbp+57h+pv]
0x1800a2315  mov     dword ptr [rbp+57h+var_5C+4], esi
0x1800a2318  mov     rax, [rcx]
0x1800a231b  mov     rax, [rax+40h]
0x1800a231f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2324  test    eax, eax
0x1800a2326  jns     short loc_1800A236D
0x1800a2328  lea     rcx, aFailedToGetThe_4; "Failed to get the resource name."
0x1800a232f  mov     r9d, 0DE8h
0x1800a2335  mov     [rsp+0C0h+var_90], rcx
0x1800a233a  mov     dword ptr [rsp+0C0h+o_ppvObject], eax
0x1800a233e  lea     rax, aCxasynchStateR_0; "CXaSynch_State_RegisterResourceManager:"...
0x1800a2345  mov     dword ptr [r14+24Ch], 0FFFFFFFDh
0x1800a2350  lea     r8, aComComplusDtcD_74; "com\\complus\\dtc\\dtc\\xatm\\src\\xasy"...
0x1800a2357  mov     [rsp+0C0h+i_pvConfigParams], rax
0x1800a235c  mov     edx, esi
0x1800a235e  mov     ecx, 0Dh
0x1800a2363  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800a2368  jmp     loc_1800A267C
0x1800a236d  mov     rdx, [rbp+57h+pv]
0x1800a2371  lea     r8, [rbp+57h+var_5C+8]
0x1800a2375  xor     ecx, ecx
0x1800a2377  call    cs:__imp_MtxCluGetResourceId
0x1800a237d  mov     ebx, eax
0x1800a237f  test    eax, eax
0x1800a2381  jns     short loc_1800A23A8
0x1800a2383  mov     rcx, [rbp+57h+pv]; pv
0x1800a2387  call    cs:__imp_CoTaskMemFree
0x1800a238d  lea     rax, aFailedToGetThe_5; "Failed to get the resource id."
0x1800a2394  mov     r9d, 0DF2h
0x1800a239a  mov     [rsp+0C0h+var_90], rax
0x1800a239f  mov     dword ptr [rsp+0C0h+o_ppvObject], ebx
0x1800a23a3  jmp     short loc_1800A233E
0x1800a23a5  mov     dword ptr [rbp+57h+var_5C+4], edi
0x1800a23a8  lea     rax, [rbp+57h+var_60]
0x1800a23ac  mov     r9d, 40000000h; i_grfOptions
0x1800a23b2  lea     rsi, [r14+210h]
0x1800a23b9  xor     edx, edx; i_pszTmName
0x1800a23bb  mov     [rsp+0C0h+o_ppvObject], rsi; o_ppvObject
0x1800a23c0  lea     r8, _GUID_13741d20_87eb_11ce_8081_0080c758527e; i_riid
0x1800a23c7  xor     ecx, ecx; i_pszHost
0x1800a23c9  mov     [rsp+0C0h+i_pvConfigParams], rax; i_pvConfigParams
0x1800a23ce  call    cs:__imp_DtcGetTransactionManagerExA
0x1800a23d4  mov     rcx, [rbp+57h+pv]; pv
0x1800a23d8  call    cs:__imp_CoTaskMemFree
0x1800a23de  mov     rcx, [rsi]
0x1800a23e1  test    rcx, rcx
0x1800a23e4  jz      loc_1800A2671
0x1800a23ea  mov     rax, [rcx]
0x1800a23ed  lea     rbx, [r14+218h]
0x1800a23f4  mov     r8, rbx
0x1800a23f7  lea     rdx, _GUID_e1cf9b5a_8745_11ce_a9ba_00aa006c3706
0x1800a23fe  mov     rax, [rax]
0x1800a2401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2406  cmp     [rbx], rdi
0x1800a2409  jnz     short loc_1800A242D
0x1800a240b  mov     r9d, 0E1Bh; int
0x1800a2411  lea     rdx, [r14+288h]; char *
0x1800a2418  mov     dword ptr [r14+24Ch], 0FFFFFFFDh
0x1800a2423  call    ?XA_TRACE_DSNWARNING@@YAXKPEAD0H@Z; XA_TRACE_DSNWARNING(ulong,char *,char *,int)
0x1800a2428  jmp     loc_1800A267C
0x1800a242d  mov     rax, [r14]
0x1800a2430  lea     r8, [rbp+57h+var_80]
0x1800a2434  lea     rdx, _GUID_0d563181_defb_11ce_aed1_00aa0051e2c4
0x1800a243b  mov     rcx, r14
0x1800a243e  mov     rax, [rax]
0x1800a2441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2446  mov     rsi, [rsi]
0x1800a2449  lea     rcx, [r14+1A0h]
0x1800a2450  mov     rdx, [rcx]
0x1800a2453  mov     rbx, [rbp+57h+var_80]
0x1800a2457  mov     rax, [rsi]
0x1800a245a  mov     rdi, [rax+18h]
0x1800a245e  mov     rax, [rdx]
0x1800a2461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2466  mov     rdx, rax
0x1800a2469  lea     r12, [r14+208h]
0x1800a2470  mov     rax, rdi
0x1800a2473  mov     [rsp+0C0h+i_pvConfigParams], r12
0x1800a2478  mov     r9, rbx
0x1800a247b  mov     r8, r13
0x1800a247e  mov     rcx, rsi
0x1800a2481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2486  mov     rcx, [rbp+57h+var_80]
0x1800a248a  cmp     eax, 8004D102h
0x1800a248f  mov     rax, [rcx]
0x1800a2492  mov     rax, [rax+10h]
0x1800a2496  jnz     short loc_1800A24E4
0x1800a2498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a249d  lea     rdx, [r14+288h]; char *
0x1800a24a4  mov     [rbp+57h+var_80], 0
0x1800a24ac  mov     r9d, 0E34h; int
0x1800a24b2  call    ?XA_TRACE_DSNWARNING@@YAXKPEAD0H@Z; XA_TRACE_DSNWARNING(ulong,char *,char *,int)
0x1800a24b7  mov     rax, [r15]
0x1800a24ba  mov     rdx, r14
0x1800a24bd  mov     rcx, r15
0x1800a24c0  mov     rax, [rax+58h]
0x1800a24c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a24c9  lea     rcx, ?g_CXaSynch_State_RetryOpen@@3VCXaSynch_State_RetryOpen@@A; this
0x1800a24d0  mov     rdx, r14; struct CXaSynch *
0x1800a24d3  mov     [r14+1E8h], rcx
0x1800a24da  call    ?Enter_State@CXaSynch_State_RetryOpen@@UEAAXPEAVCXaSynch@@@Z; CXaSynch_State_RetryOpen::Enter_State(CXaSynch *)
0x1800a24df  jmp     loc_1800A2687
0x1800a24e4  xor     r13d, r13d
0x1800a24e7  cmp     [r12], r13
0x1800a24eb  jnz     short loc_1800A2501
0x1800a24ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a24f2  mov     r9d, 0E45h
0x1800a24f8  mov     [rbp+57h+var_80], r13
0x1800a24fc  jmp     loc_1800A2411
0x1800a2501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2506  cmp     dword ptr [r14+23Ch], 1
0x1800a250e  mov     [rbp+57h+var_80], r13
0x1800a2512  jnz     short loc_1800A2524
0x1800a2514  mov     rdx, r14; struct CXaSynch *
0x1800a2517  mov     rcx, r15; this
0x1800a251a  call    ?Change_State_AtomicRecovery@CXaSynch_State@@QEAAXPEAVCXaSynch@@@Z; CXaSynch_State::Change_State_AtomicRecovery(CXaSynch *)
0x1800a251f  jmp     loc_1800A2687
0x1800a2524  mov     ecx, 78h ; 'x'; Size
0x1800a2529  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a252e  mov     [rbp+57h+var_68], rax
0x1800a2532  mov     rdi, rax
0x1800a2535  test    rax, rax
0x1800a2538  jz      loc_1800A2652
0x1800a253e  mov     [rdi+20h], r13
0x1800a2542  lea     rax, ??_7?$UTLink@PEAU_IOMGROVERLAP@@@@6B@; const UTLink<_IOMGROVERLAP *>::`vftable'
0x1800a2549  mov     [rdi+8], rax
0x1800a254d  lea     rax, ??_7COpenTask@@6B@; const COpenTask::`vftable'
0x1800a2554  mov     [rdi+18h], r13
0x1800a2558  mov     [rdi+28h], r13d
0x1800a255c  mov     [rdi+30h], r13
0x1800a2560  mov     [rdi], rax
0x1800a2563  mov     [rdi+38h], r13d
0x1800a2567  mov     [rdi+48h], r13
0x1800a256b  mov     [rdi+50h], r13d
0x1800a256f  test    rdi, rdi
0x1800a2572  jz      loc_1800A2652
0x1800a2578  mov     rax, [r14]
0x1800a257b  lea     r8, [rbp+57h+var_70]
0x1800a257f  lea     rdx, IID_IXaNotifySink
0x1800a2586  mov     rcx, r14
0x1800a2589  mov     rax, [rax]
0x1800a258c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2591  cmp     [rbp+57h+var_70], r13
0x1800a2595  jnz     short loc_1800A25B0
0x1800a2597  mov     rax, [rdi]
0x1800a259a  mov     edx, 1
0x1800a259f  mov     rcx, rdi
0x1800a25a2  mov     rax, [rax+30h]
0x1800a25a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a25ab  jmp     loc_1800A2671
0x1800a25b0  lea     rcx, stru_180153898; lpCriticalSection
0x1800a25b7  call    cs:__imp_EnterCriticalSection
0x1800a25bd  cmp     [r14+23Ch], r13d
0x1800a25c4  jz      short loc_1800A25CB
0x1800a25c6  mov     rsi, r13
0x1800a25c9  jmp     short loc_1800A25D3
0x1800a25cb  call    ?IncrementTaskClock@CTaskManager@@SA_KXZ; CTaskManager::IncrementTaskClock(void)
0x1800a25d0  mov     rsi, rax
0x1800a25d3  mov     r9, [r14+228h]; struct xa_switch_t *
0x1800a25da  lea     rcx, [r14+288h]
0x1800a25e1  mov     r8d, [r14+1B8h]; unsigned int
0x1800a25e8  lea     rdx, [r14+24Ch]
0x1800a25ef  mov     [rsp+0C0h+var_88], rcx; char *
0x1800a25f4  mov     rcx, [r14+280h]
0x1800a25fb  mov     [rsp+0C0h+var_90], rsi; unsigned __int64
0x1800a2600  mov     [rsp+0C0h+o_ppvObject], rdx; unsigned int *
0x1800a2605  mov     rdx, [rbp+57h+var_70]; struct IXaNotifySink *
0x1800a2609  mov     [rsp+0C0h+i_pvConfigParams], rcx; char *
0x1800a260e  mov     rcx, rdi; this
0x1800a2611  call    ?Init@COpenTask@@QEAAXPEAUIXaNotifySink@@IPEAUxa_switch_t@@PEADPEAK_K2@Z; COpenTask::Init(IXaNotifySink *,uint,xa_switch_t *,char *,ulong *,unsigned __int64,char *)
0x1800a2616  cmp     [r14+23Ch], r13d
0x1800a261d  mov     ebx, r13d
0x1800a2620  mov     rdx, rsi; unsigned __int64
0x1800a2623  mov     rcx, r14; this
0x1800a2626  setnz   bl
0x1800a2629  call    ?MarkXaOpenStateListOpen@CXaSynch@@AEAAX_K@Z; CXaSynch::MarkXaOpenStateListOpen(unsigned __int64)
0x1800a262e  mov     edx, ebx; unsigned int
0x1800a2630  mov     rcx, rdi; struct CWorkerTask *
0x1800a2633  call    ?Enqueue@CTaskManager@@SAXPEAVCWorkerTask@@K@Z; CTaskManager::Enqueue(CWorkerTask *,ulong)
0x1800a2638  lea     rcx, stru_180153898; lpCriticalSection
0x1800a263f  call    cs:__imp_LeaveCriticalSection
0x1800a2645  mov     rdx, r14; struct CXaSynch *
0x1800a2648  mov     rcx, r15; this
0x1800a264b  call    ?Change_State_Opening@CXaSynch_State@@QEAAXPEAVCXaSynch@@@Z; CXaSynch_State::Change_State_Opening(CXaSynch *)
0x1800a2650  jmp     short loc_1800A2687
0x1800a2652  mov     r9d, 0C000110Bh; unsigned int
0x1800a2658  lea     rdx, aComComplusDtcD_1; "com\\complus\\dtc\\dtc\\xatm\\src\\xasy"...
0x1800a265f  mov     r8d, 0E5Ah; int
0x1800a2665  lea     rcx, aCopentask; "COpenTask"
0x1800a266c  call    ?COMMON_TRACE@@YAXPEAD0HK@Z; COMMON_TRACE(char *,char *,int,ulong)
0x1800a2671  mov     dword ptr [r14+24Ch], 0FFFFFFFDh
0x1800a267c  mov     rdx, r14; struct CXaSynch *
0x1800a267f  mov     rcx, r15; this
0x1800a2682  call    ?Change_State_OpenComplete@CXaSynch_State@@QEAAXPEAVCXaSynch@@@Z; CXaSynch_State::Change_State_OpenComplete(CXaSynch *)
0x1800a2687  mov     rcx, [rbp+57h+var_40]
0x1800a268b  xor     rcx, rsp; StackCookie
0x1800a268e  call    __security_check_cookie
0x1800a2693  mov     rbx, [rsp+0C0h+arg_10]
0x1800a269b  add     rsp, 90h
0x1800a26a2  pop     r15
0x1800a26a4  pop     r14
0x1800a26a6  pop     r13
0x1800a26a8  pop     r12
0x1800a26aa  pop     rdi
0x1800a26ab  pop     rsi
0x1800a26ac  pop     rbp
0x1800a26ad  retn
```
