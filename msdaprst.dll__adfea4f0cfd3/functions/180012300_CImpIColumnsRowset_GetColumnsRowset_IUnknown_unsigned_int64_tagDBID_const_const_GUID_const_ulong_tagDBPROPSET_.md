# CImpIColumnsRowset::GetColumnsRowset(IUnknown *,unsigned __int64,tagDBID const * const,_GUID const &,ulong,tagDBPROPSET * const,IUnknown * *)

- ea: `0x180012300`
- end: `0x1800127d1`
- name: `?GetColumnsRowset@CImpIColumnsRowset@@UEAAJPEAUIUnknown@@_KQEBUtagDBID@@AEBU_GUID@@KQEAUtagDBPROPSET@@PEAPEAU2@@Z`
- size: `1233`
- prototype: `__int64 __fastcall(CImpIColumnsRowset *__hidden this, struct IUnknown *, unsigned __int64, const struct tagDBID *const, const struct _GUID *, unsigned int, struct tagDBPROPSET *const, struct IUnknown **)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180001db8`
- `0x180002728`
- `0x180002770`
- `0x180011fac`
- `0x180012300`
- `0x180012a7c`
- `0x180012d88`
- `0x180016584`
- `0x18001b008`
- `0x18002dca4`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180012358`
- `KERNEL32!GetCurrentThreadId` at `0x180012358`
- `KERNEL32!LeaveCriticalSection` at `0x18001246e`
- `KERNEL32!LeaveCriticalSection` at `0x180012735`
- `KERNEL32!LeaveCriticalSection` at `0x1800127af`
- `KERNEL32!LeaveCriticalSection` at `0x18001246e`
- `KERNEL32!LeaveCriticalSection` at `0x180012735`
- `KERNEL32!LeaveCriticalSection` at `0x1800127af`
- `ole32!CoCreateInstance` at `0x1800124a2`
- `ole32!CoCreateInstance` at `0x1800124a2`
- `ole32!CoTaskMemFree` at `0x18001241d`
- `ole32!CoTaskMemFree` at `0x18001269d`
- `ole32!CoTaskMemFree` at `0x1800126e3`
- `ole32!CoTaskMemFree` at `0x18001275e`
- `ole32!CoTaskMemFree` at `0x18001241d`
- `ole32!CoTaskMemFree` at `0x18001269d`
- `ole32!CoTaskMemFree` at `0x1800126e3`
- `ole32!CoTaskMemFree` at `0x18001275e`
- `OLEAUT32!__imp_VariantClear` at `0x180012685`
- `OLEAUT32!__imp_VariantClear` at `0x180012685`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800123b0`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800123b0`
- `MSDART!UMSEnterCSWraper` at `0x180012337`
- `MSDART!UMSEnterCSWraper` at `0x180012337`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CImpIColumnsRowset::GetColumnsRowset(
        CImpIColumnsRowset *this,
        struct IUnknown *a2,
        __int64 a3,
        struct tagDBID *a4,
        const struct _GUID *a5,
        unsigned int a6,
        struct tagDBPROPSET *const a7,
        struct IUnknown **a8)
{
  __int64 v9; // r15
  _DWORD *v10; // r12
  _DWORD *v11; // r13
  int v12; // ecx
  unsigned int v13; // ebx
  bool v14; // zf
  __int64 v15; // rcx
  HRESULT v17; // eax
  unsigned int v18; // eax
  CImpIColumnsRowset *v19; // rcx
  struct tagDBCOLUMNINFO *v20; // rsi
  char *v21; // rbx
  int v22; // eax
  int v23; // edi
  unsigned int *v24; // rdi
  int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // edi
  __int64 v28; // rsi
  unsigned int v29; // r14d
  __int64 v30; // rcx
  unsigned int v31; // edi
  __int64 v32; // rcx
  unsigned int v33; // [rsp+40h] [rbp-A8h] BYREF
  unsigned int v34; // [rsp+44h] [rbp-A4h] BYREF
  struct IRowset *v35; // [rsp+48h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-98h] BYREF
  int v37; // [rsp+58h] [rbp-90h]
  unsigned int *v38; // [rsp+60h] [rbp-88h] BYREF
  struct tagDBCOLUMNINFO *v39; // [rsp+68h] [rbp-80h] BYREF
  __int64 v40; // [rsp+70h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-70h] BYREF
  int v42; // [rsp+80h] [rbp-68h] BYREF
  __int64 v43; // [rsp+88h] [rbp-60h]
  _DWORD *v44; // [rsp+90h] [rbp-58h]
  _DWORD *v45; // [rsp+98h] [rbp-50h]
  __int64 v46; // [rsp+A0h] [rbp-48h]
  int v48; // [rsp+F0h] [rbp+8h]
  unsigned int v49; // [rsp+F0h] [rbp+8h]

  v9 = *((_QWORD *)this + 3) + 128LL;
  v43 = v9;
  UMSEnterCSWraper(v9);
  v10 = (_DWORD *)(v9 + 12);
  v44 = (_DWORD *)(v9 + 12);
  if ( !*(_DWORD *)(v9 + 12) )
    *(_DWORD *)(v9 + 8) = GetCurrentThreadId();
  ++*v10;
  v11 = (_DWORD *)(v9 + 16);
  v45 = (_DWORD *)(v9 + 16);
  ++*(_DWORD *)(v9 + 16);
  v46 = v9;
  ppv = 0;
  v35 = 0;
  v40 = 0;
  v39 = 0;
  v34 = 0;
  v33 = 0;
  pv = 0;
  v38 = 0;
  SetErrorInfo(0, 0);
  if ( a8 && (!a6 || a7) && (!a3 || a4) )
  {
    if ( a2 )
    {
      v12 = -2147217886;
LABEL_10:
      v13 = Exit(v12, 0);
      operator delete(0);
      CoTaskMemFree(0);
      operator delete(0);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v40);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v35);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&ppv);
      --*v11;
      v14 = (*v10)-- == 1;
      if ( v14 )
        *(_DWORD *)(v9 + 8) = -1;
      v15 = *(_QWORD *)v9;
      --*(_DWORD *)(v15 + 48);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
      return v13;
    }
    *a8 = 0;
    v17 = CoCreateInstance(&CLSID_FoxRowset, 0, 1u, &IID_ICreateRowset, &ppv);
    v37 = v17;
    if ( v17 < 0 )
    {
      v12 = v17;
      goto LABEL_10;
    }
    try
    {
      v18 = DownsizeToULONGThrow<unsigned __int64>(a3);
      CImpIColumnsRowset::SetupColumnsInfo((CImpIColumnsRowset *)a4, &v34, &v39, v18, a4, &v38);
      CImpIColumnsRowset::SetupProperties(v19, &v33, (struct tagDBPROPSET **)&pv, a6, a7);
      v20 = v39;
      v21 = (char *)pv;
      v22 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, LPVOID, _QWORD, struct tagDBCOLUMNINFO *, struct IRowset **))(*(_QWORD *)ppv + 24LL))(
              ppv,
              v33,
              pv,
              v34,
              v39,
              &v35);
      v23 = v22;
      if ( v22 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049948[0] )
          bidTraceW(off_1800491D0[0], 145408, off_180049948[0], (unsigned int)v22, 142);
        ThrowHR(v23);
      }
      v24 = v38;
      CImpIColumnsRowset::AddData(this, v35, v34, v20, v38);
      v25 = ((__int64 (__fastcall *)(struct IRowset *, const struct _GUID *, struct IUnknown **))v35->lpVtbl->QueryInterface)(
              v35,
              a5,
              a8);
      v48 = v25;
      if ( v25 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049940[0] )
        {
          bidTraceW(off_1800491D0[0], 149504, off_180049940[0], (unsigned int)v25, 146);
          v25 = v48;
        }
        ThrowHR(v25);
      }
    }
    catch ( long v42 )
    {
      v20 = v39;
      v37 = v42;
      v21 = (char *)pv;
      v24 = v38;
      v9 = v43;
      v10 = v44;
      v11 = v45;
    }
    v26 = 0;
    v49 = 0;
    if ( v33 )
    {
      do
      {
        v27 = 0;
        v28 = 32LL * v26;
        if ( *(_DWORD *)&v21[v28 + 8] )
        {
          do
            VariantClear((VARIANTARG *)(*(_QWORD *)&v21[v28] + 8 * (9LL * v27++ + 6)));
          while ( v27 < *(_DWORD *)&v21[v28 + 8] );
        }
        CoTaskMemFree(*(LPVOID *)&v21[v28]);
        v26 = v49 + 1;
        v49 = v26;
      }
      while ( v26 < v33 );
      v24 = v38;
      v20 = v39;
    }
    v29 = Exit(v37, 0);
    operator delete(v24);
    CoTaskMemFree(v21);
    operator delete(v20);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v40);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v35);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&ppv);
    --*v11;
    v14 = (*v10)-- == 1;
    if ( v14 )
      *(_DWORD *)(v9 + 8) = -1;
    v30 = *(_QWORD *)v9;
    --*(_DWORD *)(v30 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v30 + 8));
    return v29;
  }
  else
  {
    v31 = Exit(-2147024809, 0);
    operator delete(0);
    CoTaskMemFree(0);
    operator delete(0);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v40);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v35);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&ppv);
    --*v11;
    v14 = (*v10)-- == 1;
    if ( v14 )
      *(_DWORD *)(v9 + 8) = -1;
    v32 = *(_QWORD *)v9;
    --*(_DWORD *)(v32 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v32 + 8));
    return v31;
  }
}

```

## disassembly

```asm
0x180012300  mov     [rsp+arg_18], r9
0x180012305  mov     [rsp+arg_8], rdx
0x18001230a  mov     [rsp+arg_0], rcx
0x18001230f  push    rbx
0x180012310  push    rsi
0x180012311  push    rdi
0x180012312  push    r12
0x180012314  push    r13
0x180012316  push    r14
0x180012318  push    r15
0x18001231a  sub     rsp, 0B0h
0x180012321  mov     rsi, r8
0x180012324  mov     r15, [rcx+18h]
0x180012328  sub     r15, 0FFFFFFFFFFFFFF80h
0x18001232c  mov     [rsp+0E8h+var_60], r15
0x180012334  mov     rcx, r15
0x180012337  call    cs:__imp_UMSEnterCSWraper
0x18001233e  nop     dword ptr [rax+rax+00h]
0x180012343  lea     r12, [r15+0Ch]
0x180012347  mov     [rsp+0E8h+var_58], r12
0x18001234f  xor     r14d, r14d
0x180012352  cmp     [r12], r14d
0x180012356  jnz     short loc_180012368
0x180012358  call    cs:__imp_GetCurrentThreadId
0x18001235f  nop     dword ptr [rax+rax+00h]
0x180012364  mov     [r15+8], eax
0x180012368  inc     dword ptr [r12]
0x18001236c  lea     r13, [r15+10h]
0x180012370  mov     [rsp+0E8h+var_50], r13
0x180012378  inc     dword ptr [r13+0]
0x18001237c  mov     [rsp+0E8h+var_48], r15
0x180012384  mov     [rsp+0E8h+var_98], r14
0x180012389  mov     [rsp+0E8h+var_A0], r14
0x18001238e  mov     [rsp+0E8h+var_78], r14
0x180012393  mov     [rsp+0E8h+var_80], r14
0x180012398  mov     [rsp+0E8h+var_A4], r14d
0x18001239d  mov     [rsp+0E8h+var_A8], r14d
0x1800123a2  mov     [rsp+0E8h+pv], r14
0x1800123a7  mov     [rsp+0E8h+var_88], r14
0x1800123ac  xor     edx, edx; perrinfo
0x1800123ae  xor     ecx, ecx; dwReserved
0x1800123b0  call    cs:__imp_SetErrorInfo
0x1800123b7  nop     dword ptr [rax+rax+00h]
0x1800123bc  mov     rax, [rsp+0E8h+arg_38]
0x1800123c4  test    rax, rax
0x1800123c7  jz      loc_180012746
0x1800123cd  mov     rdi, [rsp+0E8h+arg_30]
0x1800123d5  cmp     [rsp+0E8h+arg_28], r14d
0x1800123dd  jbe     short loc_1800123E8
0x1800123df  test    rdi, rdi
0x1800123e2  jz      loc_180012746
0x1800123e8  test    rsi, rsi
0x1800123eb  jz      short loc_1800123FB
0x1800123ed  cmp     [rsp+0E8h+arg_18], r14
0x1800123f5  jz      loc_180012746
0x1800123fb  cmp     [rsp+0E8h+arg_8], r14
0x180012403  jz      short loc_180012481
0x180012405  mov     ecx, 80040E22h; int
0x18001240a  xor     edx, edx; unsigned int
0x18001240c  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180012411  mov     ebx, eax
0x180012413  xor     ecx, ecx; void *
0x180012415  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001241a  nop
0x18001241b  xor     ecx, ecx; pv
0x18001241d  call    cs:__imp_CoTaskMemFree
0x180012424  nop     dword ptr [rax+rax+00h]
0x180012429  nop
0x18001242a  xor     ecx, ecx; void *
0x18001242c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012431  nop
0x180012432  lea     rcx, [rsp+0E8h+var_78]
0x180012437  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18001243c  nop
0x18001243d  lea     rcx, [rsp+0E8h+var_A0]
0x180012442  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180012447  nop
0x180012448  lea     rcx, [rsp+0E8h+var_98]
0x18001244d  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180012452  nop
0x180012453  or      ecx, 0FFFFFFFFh
0x180012456  add     [r13+0], ecx
0x18001245a  add     [r12], ecx
0x18001245e  jnz     short loc_180012464
0x180012460  mov     [r15+8], ecx
0x180012464  mov     rcx, [r15]
0x180012467  dec     dword ptr [rcx+30h]
0x18001246a  add     rcx, 8; lpCriticalSection
0x18001246e  call    cs:__imp_LeaveCriticalSection
0x180012475  nop     dword ptr [rax+rax+00h]
0x18001247a  mov     eax, ebx
0x18001247c  jmp     loc_1800127BD
0x180012481  mov     [rax], r14
0x180012484  lea     rax, [rsp+0E8h+var_98]
0x180012489  mov     [rsp+0E8h+ppv], rax; ppv
0x18001248e  lea     r9, IID_ICreateRowset; riid
0x180012495  xor     edx, edx; pUnkOuter
0x180012497  lea     r8d, [rdx+1]; dwClsContext
0x18001249b  lea     rcx, ?CLSID_FoxRowset@@3U_GUID@@B; rclsid
0x1800124a2  call    cs:__imp_CoCreateInstance
0x1800124a9  nop     dword ptr [rax+rax+00h]
0x1800124ae  mov     [rsp+0E8h+var_90], eax
0x1800124b2  test    eax, eax
0x1800124b4  jns     short loc_1800124BD
0x1800124b6  mov     ecx, eax
0x1800124b8  jmp     loc_18001240A
0x1800124bd  mov     rcx, rsi
0x1800124c0  call    ??$DownsizeToULONGThrow@_K@@YAK_KJ@Z; DownsizeToULONGThrow<unsigned __int64>(unsigned __int64,long)
0x1800124c5  lea     rcx, [rsp+0E8h+var_88]
0x1800124ca  mov     [rsp+0E8h+var_C0], rcx; unsigned int **
0x1800124cf  mov     rcx, [rsp+0E8h+arg_18]; this
0x1800124d7  mov     [rsp+0E8h+ppv], rcx; struct tagDBID *
0x1800124dc  mov     r9d, eax; unsigned int
0x1800124df  lea     r8, [rsp+0E8h+var_80]; struct tagDBCOLUMNINFO **
0x1800124e4  lea     rdx, [rsp+0E8h+var_A4]; unsigned int *
0x1800124e9  call    ?SetupColumnsInfo@CImpIColumnsRowset@@AEAAXPEAKPEAPEAUtagDBCOLUMNINFO@@KPEAUtagDBID@@PEAPEAK@Z; CImpIColumnsRowset::SetupColumnsInfo(ulong *,tagDBCOLUMNINFO * *,ulong,tagDBID *,ulong * *)
0x1800124ee  mov     [rsp+0E8h+ppv], rdi; struct tagDBPROPSET *
0x1800124f3  mov     r9d, [rsp+0E8h+arg_28]; unsigned int
0x1800124fb  lea     r8, [rsp+0E8h+pv]; struct tagDBPROPSET **
0x180012500  lea     rdx, [rsp+0E8h+var_A8]; unsigned int *
0x180012505  call    ?SetupProperties@CImpIColumnsRowset@@AEAAXPEAKPEAPEAUtagDBPROPSET@@KPEAU2@@Z; CImpIColumnsRowset::SetupProperties(ulong *,tagDBPROPSET * *,ulong,tagDBPROPSET *)
0x18001250a  mov     rcx, [rsp+0E8h+var_98]
0x18001250f  mov     rax, [rcx]
0x180012512  lea     rdx, [rsp+0E8h+var_A0]
0x180012517  mov     [rsp+0E8h+var_C0], rdx
0x18001251c  mov     rsi, [rsp+0E8h+var_80]
0x180012521  mov     [rsp+0E8h+ppv], rsi
0x180012526  mov     r9d, [rsp+0E8h+var_A4]
0x18001252b  mov     rbx, [rsp+0E8h+pv]
0x180012530  mov     r8, rbx
0x180012533  mov     edx, [rsp+0E8h+var_A8]
0x180012537  mov     rax, [rax+18h]
0x18001253b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012540  mov     edi, eax
0x180012542  test    eax, eax
0x180012544  jns     short loc_180012585
0x180012546  test    byte ptr cs:_bidGblFlags, 2
0x18001254d  jz      short loc_18001257E
0x18001254f  mov     rcx, cs:off_180049948; "<CImpIColumnsRowset::GetColumnsRowset|A"...
0x180012556  test    rcx, rcx
0x180012559  jz      short loc_18001257E
0x18001255b  mov     dword ptr [rsp+0E8h+ppv], 8Eh
0x180012563  mov     r9d, eax
0x180012566  mov     r8, cs:off_180049948; "<CImpIColumnsRowset::GetColumnsRowset|A"...
0x18001256d  mov     edx, 23800h
0x180012572  mov     rcx, cs:off_1800491D0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180012579  call    _bidTraceW
0x18001257e  mov     ecx, edi; int
0x180012580  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180012585  mov     rdi, [rsp+0E8h+var_88]
0x18001258a  mov     [rsp+0E8h+ppv], rdi; unsigned int *
0x18001258f  mov     r9, rsi; struct tagDBCOLUMNINFO *
0x180012592  mov     r8d, [rsp+0E8h+var_A4]; unsigned int
0x180012597  mov     rdx, [rsp+0E8h+var_A0]; struct IRowset *
0x18001259c  mov     rcx, [rsp+0E8h+arg_0]; this
0x1800125a4  call    ?AddData@CImpIColumnsRowset@@AEAAXPEAUIRowset@@KPEAUtagDBCOLUMNINFO@@PEAK@Z; CImpIColumnsRowset::AddData(IRowset *,ulong,tagDBCOLUMNINFO *,ulong *)
0x1800125a9  mov     rcx, [rsp+0E8h+var_A0]
0x1800125ae  mov     rax, [rcx]
0x1800125b1  mov     r8, [rsp+0E8h+arg_38]
0x1800125b9  mov     rdx, [rsp+0E8h+arg_20]
0x1800125c1  mov     rax, [rax]
0x1800125c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125c9  mov     dword ptr [rsp+0E8h+arg_0], eax
0x1800125d0  test    eax, eax
0x1800125d2  jns     short loc_18001261B
0x1800125d4  test    byte ptr cs:_bidGblFlags, 2
0x1800125db  jz      short loc_180012613
0x1800125dd  mov     rcx, cs:off_180049940; "<CImpIColumnsRowset::GetColumnsRowset|A"...
0x1800125e4  test    rcx, rcx
0x1800125e7  jz      short loc_180012613
0x1800125e9  mov     dword ptr [rsp+0E8h+ppv], 92h
0x1800125f1  mov     r9d, eax
0x1800125f4  mov     r8, cs:off_180049940; "<CImpIColumnsRowset::GetColumnsRowset|A"...
0x1800125fb  mov     edx, 24800h
0x180012600  mov     rcx, cs:off_1800491D0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180012607  call    _bidTraceW
0x18001260c  mov     eax, dword ptr [rsp+0E8h+arg_0]
0x180012613  mov     ecx, eax; int
0x180012615  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18001261b  jmp     short loc_180012652
0x18001261d  xor     r14d, r14d
0x180012620  mov     rsi, [rsp+0E8h+var_80]
0x180012625  mov     eax, dword ptr [rsp+0E8h+arg_0]
0x18001262c  mov     [rsp+0E8h+var_90], eax
0x180012630  mov     rbx, [rsp+0E8h+pv]
0x180012635  mov     rdi, [rsp+0E8h+var_88]
0x18001263a  mov     r15, [rsp+0E8h+var_60]
0x180012642  mov     r12, [rsp+0E8h+var_58]
0x18001264a  mov     r13, [rsp+0E8h+var_50]
0x180012652  mov     eax, r14d
0x180012655  mov     dword ptr [rsp+0E8h+arg_0], eax
0x18001265c  cmp     [rsp+0E8h+var_A8], r14d
0x180012661  jbe     short loc_1800126C9
0x180012663  mov     edi, r14d
0x180012666  mov     esi, eax
0x180012668  shl     rsi, 5
0x18001266c  cmp     [rsi+rbx+8], r14d
0x180012671  jbe     short loc_180012699
0x180012673  mov     eax, edi
0x180012675  lea     rcx, [rax+rax*8]
0x180012679  mov     rax, [rsi+rbx]
0x18001267d  lea     rcx, [rcx+6]
0x180012681  lea     rcx, [rax+rcx*8]; pvarg
0x180012685  call    cs:__imp_VariantClear
0x18001268c  nop     dword ptr [rax+rax+00h]
0x180012691  inc     edi
0x180012693  cmp     edi, [rsi+rbx+8]
0x180012697  jb      short loc_180012673
0x180012699  mov     rcx, [rsi+rbx]; pv
0x18001269d  call    cs:__imp_CoTaskMemFree
0x1800126a4  nop     dword ptr [rax+rax+00h]
0x1800126a9  mov     eax, dword ptr [rsp+0E8h+arg_0]
0x1800126b0  inc     eax
0x1800126b2  mov     dword ptr [rsp+0E8h+arg_0], eax
0x1800126b9  cmp     eax, [rsp+0E8h+var_A8]
0x1800126bd  jb      short loc_180012663
0x1800126bf  mov     rdi, [rsp+0E8h+var_88]
0x1800126c4  mov     rsi, [rsp+0E8h+var_80]
0x1800126c9  xor     edx, edx; unsigned int
0x1800126cb  mov     ecx, [rsp+0E8h+var_90]; int
0x1800126cf  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800126d4  mov     r14d, eax
0x1800126d7  mov     rcx, rdi; void *
0x1800126da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800126df  nop
0x1800126e0  mov     rcx, rbx; pv
0x1800126e3  call    cs:__imp_CoTaskMemFree
0x1800126ea  nop     dword ptr [rax+rax+00h]
0x1800126ef  nop
0x1800126f0  mov     rcx, rsi; void *
0x1800126f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800126f8  nop
0x1800126f9  lea     rcx, [rsp+0E8h+var_78]
0x1800126fe  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180012703  nop
0x180012704  lea     rcx, [rsp+0E8h+var_A0]
0x180012709  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18001270e  nop
0x18001270f  lea     rcx, [rsp+0E8h+var_98]
0x180012714  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180012719  nop
0x18001271a  or      ecx, 0FFFFFFFFh
0x18001271d  add     [r13+0], ecx
0x180012721  add     [r12], ecx
0x180012725  jnz     short loc_18001272B
0x180012727  mov     [r15+8], ecx
0x18001272b  mov     rcx, [r15]
0x18001272e  dec     dword ptr [rcx+30h]
0x180012731  add     rcx, 8; lpCriticalSection
0x180012735  call    cs:__imp_LeaveCriticalSection
0x18001273c  nop     dword ptr [rax+rax+00h]
0x180012741  mov     eax, r14d
0x180012744  jmp     short loc_1800127BD
0x180012746  xor     edx, edx; unsigned int
0x180012748  mov     ecx, 80070057h; int
0x18001274d  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180012752  mov     edi, eax
0x180012754  xor     ecx, ecx; void *
0x180012756  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001275b  nop
0x18001275c  xor     ecx, ecx; pv
0x18001275e  call    cs:__imp_CoTaskMemFree
0x180012765  nop     dword ptr [rax+rax+00h]
0x18001276a  nop
0x18001276b  xor     ecx, ecx; void *
0x18001276d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012772  nop
0x180012773  lea     rcx, [rsp+0E8h+var_78]
0x180012778  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18001277d  nop
0x18001277e  lea     rcx, [rsp+0E8h+var_A0]
0x180012783  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180012788  nop
0x180012789  lea     rcx, [rsp+0E8h+var_98]
0x18001278e  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180012793  nop
0x180012794  or      ecx, 0FFFFFFFFh
0x180012797  add     [r13+0], ecx
0x18001279b  add     [r12], ecx
0x18001279f  jnz     short loc_1800127A5
0x1800127a1  mov     [r15+8], ecx
0x1800127a5  mov     rcx, [r15]
0x1800127a8  dec     dword ptr [rcx+30h]
0x1800127ab  add     rcx, 8; lpCriticalSection
0x1800127af  call    cs:__imp_LeaveCriticalSection
0x1800127b6  nop     dword ptr [rax+rax+00h]
0x1800127bb  mov     eax, edi
0x1800127bd  add     rsp, 0B0h
0x1800127c4  pop     r15
0x1800127c6  pop     r14
0x1800127c8  pop     r13
0x1800127ca  pop     r12
0x1800127cc  pop     rdi
0x1800127cd  pop     rsi
0x1800127ce  pop     rbx
0x1800127cf  retn
```
