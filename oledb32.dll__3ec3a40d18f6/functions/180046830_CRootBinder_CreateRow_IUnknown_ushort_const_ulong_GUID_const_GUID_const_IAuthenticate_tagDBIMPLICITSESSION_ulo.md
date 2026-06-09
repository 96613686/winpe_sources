# CRootBinder::CreateRow(IUnknown *,ushort const *,ulong,_GUID const &,_GUID const &,IAuthenticate *,tagDBIMPLICITSESSION *,ulong *,ushort * *,IUnknown * *)

- ea: `0x180046830`
- end: `0x180046db1`
- name: `?CreateRow@CRootBinder@@UEAAJPEAUIUnknown@@PEBGKAEBU_GUID@@2PEAUIAuthenticate@@PEAUtagDBIMPLICITSESSION@@PEAKPEAPEAGPEAPEAU2@@Z`
- size: `1409`
- prototype: `int(CRootBinder *__hidden this, struct IUnknown *, const unsigned __int16 *, unsigned int, const struct _GUID *, const struct _GUID *, struct IAuthenticate *, struct tagDBIMPLICITSESSION *, unsigned int *, unsigned __int16 **, struct IUnknown **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180013870`
- `0x180029560`
- `0x180044114`
- `0x180046740`
- `0x18004678c`
- `0x180046830`
- `0x180047bb0`
- `0x1800482a4`
- `0x1800492c8`
- `0x180061814`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180046908`
- `KERNEL32!EnterCriticalSection` at `0x180046908`
- `KERNEL32!LeaveCriticalSection` at `0x180046d75`
- `KERNEL32!LeaveCriticalSection` at `0x180046d75`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800468f3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800468f3`

## string_xrefs

- `0x18004694a`: `<CRootBinder::CreateRow|OLEDB|ERR> `
- `0x18004698d`: `<CRootBinder::CreateRow|OLEDB|ERR> `
- `0x180046a1c`: `<CRootBinder::CreateRow|OLEDB|ERR> `
- `0x180046a92`: `<CRootBinder::CreateRow|OLEDB|ERR> `
- `0x180046b28`: `<CRootBinder::CreateRow|OLEDB|ERR> `
- `0x180046bfb`: `<CRootBinder::CreateRow|OLEDB|ERR> `
- `0x1800469a8`: `<CRootBinder::CreateRow|Trace|HR> `
- `0x180046a37`: `<CRootBinder::CreateRow|Trace|HR> `
- `0x180046aad`: `<CRootBinder::CreateRow|Trace|HR> `

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CRootBinder::CreateRow(
        CMatchMaker **this,
        struct IUnknown *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        const struct _GUID *a5,
        const struct _GUID *a6,
        struct IAuthenticate *a7,
        struct tagDBIMPLICITSESSION *a8,
        unsigned int *a9,
        unsigned __int16 **a10,
        struct IUnknown **a11)
{
  int v13; // r14d
  struct _RTL_CRITICAL_SECTION *v14; // r12
  unsigned int v15; // r8d
  int URLMapping; // ebx
  int v17; // eax
  BOOL v18; // r12d
  __int64 v19; // rcx
  int v20; // r14d
  int v21; // eax
  unsigned int v23; // [rsp+60h] [rbp-E8h] BYREF
  unsigned int v24; // [rsp+64h] [rbp-E4h] BYREF
  unsigned int v25; // [rsp+68h] [rbp-E0h]
  __int64 v26; // [rsp+70h] [rbp-D8h] BYREF
  void *v27; // [rsp+78h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+80h] [rbp-C8h] BYREF
  struct _RTL_CRITICAL_SECTION *v29; // [rsp+88h] [rbp-C0h]
  struct IUnknown **v30; // [rsp+90h] [rbp-B8h]
  unsigned __int16 **v31; // [rsp+98h] [rbp-B0h]
  struct tagDBIMPLICITSESSION *v32; // [rsp+A0h] [rbp-A8h]
  struct IAuthenticate *v33; // [rsp+A8h] [rbp-A0h]
  const struct _GUID *v34; // [rsp+B0h] [rbp-98h]
  const struct _GUID *v35; // [rsp+B8h] [rbp-90h]
  const unsigned __int16 *v36; // [rsp+C0h] [rbp-88h]
  struct IUnknown *v37; // [rsp+C8h] [rbp-80h]
  struct _GUID v38; // [rsp+D0h] [rbp-78h] BYREF
  __int64 v39; // [rsp+E0h] [rbp-68h] BYREF
  int v40; // [rsp+E8h] [rbp-60h]
  GUID v41; // [rsp+ECh] [rbp-5Ch]

  v25 = a4;
  v36 = a3;
  v37 = a2;
  v35 = a5;
  v34 = a6;
  v33 = a7;
  v32 = a8;
  v31 = a10;
  v30 = a11;
  v13 = 0;
  v27 = 0;
  v26 = 0;
  v38 = 0;
  SetErrorInfo(0, 0);
  v14 = (struct _RTL_CRITICAL_SECTION *)(this + 12);
  v29 = (struct _RTL_CRITICAL_SECTION *)(this + 12);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 12));
  URLMapping = CMatchMaker::GetURLMapping(this[48], a3, v15, &v38);
  if ( URLMapping )
  {
    if ( URLMapping == 1 )
      URLMapping = -2147217895;
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(URLMapping, L"<CRootBinder::CreateRow|OLEDB|ERR> ", 0x17Cu);
    goto LABEL_43;
  }
  URLMapping = GetProviderBinder(&v38, &IID_ICreateRow, &v27);
  if ( URLMapping < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(URLMapping, L"<CRootBinder::CreateRow|OLEDB|ERR> ", 0x180u);
      if ( (bidGblFlags & 2) != 0 )
        bidTraceHR(off_1800C83B0[0], 393225, L"<CRootBinder::CreateRow|Trace|HR> ", (unsigned int)URLMapping);
    }
    goto LABEL_43;
  }
  CRootBinder::CleanPropInErr((CRootBinder *)(this - 1));
  v23 = 0;
  v28 = 0;
  URLMapping = TUtlSetArray<tagDBPROPSET,_GUID,CPropSet>::HrGetCopyImpl(
                 (int)this + 136,
                 (unsigned int)&v28,
                 (unsigned int)&v23,
                 0,
                 0);
  if ( URLMapping < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(URLMapping, L"<CRootBinder::CreateRow|OLEDB|ERR> ", 0x18Cu);
      if ( (bidGblFlags & 2) != 0 )
        bidTraceHR(off_1800C83B0[0], 405513, L"<CRootBinder::CreateRow|Trace|HR> ", (unsigned int)URLMapping);
    }
    goto LABEL_43;
  }
  if ( !v23 )
  {
LABEL_26:
    v24 = 0;
    URLMapping = (*(__int64 (__fastcall **)(void *, struct IUnknown *, const unsigned __int16 *, _QWORD, const struct _GUID *, const struct _GUID *, struct IAuthenticate *, struct tagDBIMPLICITSESSION *, unsigned int *, unsigned __int16 **, struct IUnknown **))(*(_QWORD *)v27 + 24LL))(
                   v27,
                   v37,
                   v36,
                   v25,
                   v35,
                   v34,
                   v33,
                   v32,
                   &v24,
                   v31,
                   v30);
    if ( a9 )
      *a9 = v24;
    if ( URLMapping )
    {
      if ( URLMapping != 265946 )
      {
        CRootBinder::CleanPropSetErr((CRootBinder *)(this - 1));
        v14 = v29;
        goto LABEL_43;
      }
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(265946, L"<CRootBinder::CreateRow|OLEDB|ERR> ", 0x1D0u);
      v18 = v24 != 0;
      v23 = 0;
      v28 = 0;
      v40 = 0;
      v41 = DBPROPSET_PROPERTIESINERROR;
      v39 = 0;
      v19 = v26;
      if ( !v26 )
      {
        if ( (**(int (__fastcall ***)(void *, GUID *, __int64 *))v27)(v27, &IID_IDBProperties, &v26) < 0 )
        {
          CRootBinder::CleanPropSetErr((CRootBinder *)(this - 1));
          *((_DWORD *)this + 88) = -2147467259;
          *((_DWORD *)this + 87) = 2;
          v14 = v29;
          goto LABEL_43;
        }
        v19 = v26;
      }
      v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, unsigned int *, __int64 *))(*(_QWORD *)v19 + 24LL))(
              v19,
              1,
              &v39,
              &v23,
              &v28);
      if ( v20 )
      {
        CRootBinder::CleanPropSetErr((CRootBinder *)(this - 1));
        v21 = -2147467259;
        if ( !v18 )
          v21 = v20;
        *((_DWORD *)this + 88) = v21;
        *((_DWORD *)this + 87) = 2;
      }
      else
      {
        TUtlSetArray<tagDBPROPSET,_GUID,CPropSet>::HrInitImpl(this + 30, v28, v23);
        *((_DWORD *)this + 87) = 1;
      }
    }
    else
    {
      URLMapping = v13;
    }
    v14 = v29;
    goto LABEL_43;
  }
  URLMapping = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v27)(v27, &IID_IDBProperties, &v26);
  if ( URLMapping < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(URLMapping, L"<CRootBinder::CreateRow|OLEDB|ERR> ", 0x191u);
      if ( (bidGblFlags & 2) != 0 )
        bidTraceHR(off_1800C83B0[0], 410633, L"<CRootBinder::CreateRow|Trace|HR> ", (unsigned int)URLMapping);
    }
    goto LABEL_43;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v26 + 40LL))(v26, v23, v28);
  v13 = v17;
  if ( v17 >= 0 )
  {
    if ( v17 == 265946 )
      *((_DWORD *)this + 86) = 1;
    goto LABEL_26;
  }
  URLMapping = v17;
  if ( v17 == -2147217887 )
    *((_DWORD *)this + 86) = 1;
  if ( (bidGblFlags & 2) != 0 )
    OLEDBTraceErr(v17, L"<CRootBinder::CreateRow|OLEDB|ERR> ", 0x1ABu);
LABEL_43:
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v27 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v27 + 16LL))(v27);
  LeaveCriticalSection(v14);
  if ( URLMapping < 0 )
    PostHResult(URLMapping, &IID_ICreateRow);
  return (unsigned int)URLMapping;
}

```

## disassembly

```asm
0x180046830  push    rbx
0x180046832  push    rsi
0x180046833  push    r12
0x180046835  push    r13
0x180046837  push    r14
0x180046839  push    r15
0x18004683b  sub     rsp, 118h
0x180046842  mov     rax, cs:__security_cookie
0x180046849  xor     rax, rsp
0x18004684c  mov     [rsp+148h+var_48], rax
0x180046854  mov     [rsp+148h+var_E0], r9d
0x180046859  mov     rbx, r8
0x18004685c  mov     [rsp+148h+var_88], rbx
0x180046864  mov     [rsp+148h+var_80], rdx
0x18004686c  mov     rsi, rcx
0x18004686f  mov     rax, [rsp+148h+arg_20]
0x180046877  mov     [rsp+148h+var_90], rax
0x18004687f  mov     rax, [rsp+148h+arg_28]
0x180046887  mov     [rsp+148h+var_98], rax
0x18004688f  mov     rax, [rsp+148h+arg_30]
0x180046897  mov     [rsp+148h+var_A0], rax
0x18004689f  mov     rax, [rsp+148h+arg_38]
0x1800468a7  mov     [rsp+148h+var_A8], rax
0x1800468af  mov     r13, [rsp+148h+arg_40]
0x1800468b7  mov     rax, [rsp+148h+arg_48]
0x1800468bf  mov     [rsp+148h+var_B0], rax
0x1800468c7  mov     rax, [rsp+148h+arg_50]
0x1800468cf  mov     [rsp+148h+var_B8], rax
0x1800468d7  xor     r14d, r14d
0x1800468da  mov     [rsp+148h+var_D0], r14
0x1800468df  mov     [rsp+148h+var_D8], r14
0x1800468e4  xorps   xmm0, xmm0
0x1800468e7  movups  xmmword ptr [rsp+148h+var_78.Data1], xmm0
0x1800468ef  xor     edx, edx; perrinfo
0x1800468f1  xor     ecx, ecx; dwReserved
0x1800468f3  call    cs:__imp_SetErrorInfo
0x1800468f9  lea     r12, [rsi+60h]
0x1800468fd  mov     [rsp+148h+var_C0], r12
0x180046905  mov     rcx, r12; lpCriticalSection
0x180046908  call    cs:__imp_EnterCriticalSection
0x18004690e  nop
0x18004690f  lea     r15, [rsi-8]
0x180046913  lea     r9, [rsp+148h+var_78]; struct _GUID *
0x18004691b  mov     rdx, rbx; unsigned __int16 *
0x18004691e  mov     rcx, [r15+188h]; this
0x180046925  call    ?GetURLMapping@CMatchMaker@@QEAAJPEBGKPEAU_GUID@@@Z; CMatchMaker::GetURLMapping(ushort const *,ulong,_GUID *)
0x18004692a  mov     ebx, eax
0x18004692c  test    eax, eax
0x18004692e  jz      short loc_18004695E
0x180046930  mov     eax, 80040E19h
0x180046935  cmp     ebx, 1
0x180046938  cmovz   ebx, eax
0x18004693b  test    byte ptr cs:_bidGblFlags, 2
0x180046942  jz      short loc_180046959
0x180046944  mov     r8d, 17Ch; unsigned int
0x18004694a  lea     rdx, aCrootbinderCre_1; "<CRootBinder::CreateRow|OLEDB|ERR> "
0x180046951  mov     ecx, ebx; int
0x180046953  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180046958  nop
0x180046959  jmp     loc_180046D46
0x18004695e  lea     r8, [rsp+148h+var_D0]; void **
0x180046963  lea     rdx, IID_ICreateRow; struct _GUID *
0x18004696a  lea     rcx, [rsp+148h+var_78]; struct _GUID *
0x180046972  call    ?GetProviderBinder@@YAJAEBU_GUID@@0PEAPEAX@Z; GetProviderBinder(_GUID const &,_GUID const &,void * *)
0x180046977  mov     ebx, eax
0x180046979  test    eax, eax
0x18004697b  jns     short loc_1800469C6
0x18004697d  mov     eax, cs:_bidGblFlags
0x180046983  test    al, 2
0x180046985  jz      short loc_1800469C1
0x180046987  mov     r8d, 180h; unsigned int
0x18004698d  lea     rdx, aCrootbinderCre_1; "<CRootBinder::CreateRow|OLEDB|ERR> "
0x180046994  mov     ecx, ebx; int
0x180046996  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004699b  mov     eax, cs:_bidGblFlags
0x1800469a1  test    al, 2
0x1800469a3  jz      short loc_1800469C1
0x1800469a5  mov     r9d, ebx
0x1800469a8  lea     r8, aCrootbinderCre_0; "<CRootBinder::CreateRow|Trace|HR> "
0x1800469af  mov     edx, 60009h
0x1800469b4  mov     rcx, cs:off_1800C83B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800469bb  call    _bidTraceHR
0x1800469c0  nop
0x1800469c1  jmp     loc_180046D46
0x1800469c6  mov     rcx, r15; this
0x1800469c9  call    ?CleanPropInErr@CRootBinder@@AEAAXXZ; CRootBinder::CleanPropInErr(void)
0x1800469ce  mov     [rsp+148h+var_E8], 0
0x1800469d6  mov     [rsp+148h+var_C8], 0
0x1800469e2  lea     rcx, [rsi+88h]
0x1800469e9  mov     dword ptr [rsp+148h+var_128], 0
0x1800469f1  xor     r9d, r9d
0x1800469f4  lea     r8, [rsp+148h+var_E8]
0x1800469f9  lea     rdx, [rsp+148h+var_C8]
0x180046a01  call    ?HrGetCopyImpl@?$TUtlSetArray@UtagDBPROPSET@@U_GUID@@VCPropSet@@@@AEAAJPEAPEAUtagDBPROPSET@@PEAKKK@Z; TUtlSetArray<tagDBPROPSET,_GUID,CPropSet>::HrGetCopyImpl(tagDBPROPSET * *,ulong *,ulong,ulong)
0x180046a06  mov     ebx, eax
0x180046a08  test    eax, eax
0x180046a0a  jns     short loc_180046A55
0x180046a0c  mov     eax, cs:_bidGblFlags
0x180046a12  test    al, 2
0x180046a14  jz      short loc_180046A50
0x180046a16  mov     r8d, 18Ch; unsigned int
0x180046a1c  lea     rdx, aCrootbinderCre_1; "<CRootBinder::CreateRow|OLEDB|ERR> "
0x180046a23  mov     ecx, ebx; int
0x180046a25  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180046a2a  mov     eax, cs:_bidGblFlags
0x180046a30  test    al, 2
0x180046a32  jz      short loc_180046A50
0x180046a34  mov     r9d, ebx
0x180046a37  lea     r8, aCrootbinderCre_0; "<CRootBinder::CreateRow|Trace|HR> "
0x180046a3e  mov     edx, 63009h
0x180046a43  mov     rcx, cs:off_1800C83B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180046a4a  call    _bidTraceHR
0x180046a4f  nop
0x180046a50  jmp     loc_180046D46
0x180046a55  cmp     [rsp+148h+var_E8], 0
0x180046a5a  jz      loc_180046B3C
0x180046a60  mov     rcx, [rsp+148h+var_D0]
0x180046a65  mov     rax, [rcx]
0x180046a68  lea     r8, [rsp+148h+var_D8]
0x180046a6d  lea     rdx, IID_IDBProperties
0x180046a74  mov     rax, [rax]
0x180046a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a7c  mov     ebx, eax
0x180046a7e  test    eax, eax
0x180046a80  jns     short loc_180046ACB
0x180046a82  mov     eax, cs:_bidGblFlags
0x180046a88  test    al, 2
0x180046a8a  jz      short loc_180046AC6
0x180046a8c  mov     r8d, 191h; unsigned int
0x180046a92  lea     rdx, aCrootbinderCre_1; "<CRootBinder::CreateRow|OLEDB|ERR> "
0x180046a99  mov     ecx, ebx; int
0x180046a9b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180046aa0  mov     eax, cs:_bidGblFlags
0x180046aa6  test    al, 2
0x180046aa8  jz      short loc_180046AC6
0x180046aaa  mov     r9d, ebx
0x180046aad  lea     r8, aCrootbinderCre_0; "<CRootBinder::CreateRow|Trace|HR> "
0x180046ab4  mov     edx, 64409h
0x180046ab9  mov     rcx, cs:off_1800C83B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180046ac0  call    _bidTraceHR
0x180046ac5  nop
0x180046ac6  jmp     loc_180046D46
0x180046acb  mov     rcx, [rsp+148h+var_D8]
0x180046ad0  mov     rax, [rcx]
0x180046ad3  mov     r8, [rsp+148h+var_C8]
0x180046adb  mov     edx, [rsp+148h+var_E8]
0x180046adf  mov     rax, [rax+28h]
0x180046ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ae8  mov     r14d, eax
0x180046aeb  test    eax, eax
0x180046aed  js      short loc_180046B06
0x180046aef  mov     r12d, 40EDAh
0x180046af5  cmp     eax, r12d
0x180046af8  jnz     short loc_180046B42
0x180046afa  mov     dword ptr [rsi+158h], 1
0x180046b04  jmp     short loc_180046B42
0x180046b06  mov     ebx, eax
0x180046b08  cmp     eax, 80040E21h
0x180046b0d  jnz     short loc_180046B19
0x180046b0f  mov     dword ptr [rsi+158h], 1
0x180046b19  test    byte ptr cs:_bidGblFlags, 2
0x180046b20  jz      short loc_180046B37
0x180046b22  mov     r8d, 1ABh; unsigned int
0x180046b28  lea     rdx, aCrootbinderCre_1; "<CRootBinder::CreateRow|OLEDB|ERR> "
0x180046b2f  mov     ecx, eax; int
0x180046b31  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180046b36  nop
0x180046b37  jmp     loc_180046D46
0x180046b3c  mov     r12d, 40EDAh
0x180046b42  mov     [rsp+148h+var_E4], 0
0x180046b4a  mov     rcx, [rsp+148h+var_D0]
0x180046b4f  mov     rax, [rcx]
0x180046b52  mov     rdx, [rsp+148h+var_B8]
0x180046b5a  mov     [rsp+148h+var_F8], rdx
0x180046b5f  mov     rdx, [rsp+148h+var_B0]
0x180046b67  mov     [rsp+148h+var_100], rdx
0x180046b6c  lea     rdx, [rsp+148h+var_E4]
0x180046b71  mov     [rsp+148h+var_108], rdx
0x180046b76  mov     rdx, [rsp+148h+var_A8]
0x180046b7e  mov     [rsp+148h+var_110], rdx
0x180046b83  mov     rdx, [rsp+148h+var_A0]
0x180046b8b  mov     [rsp+148h+var_118], rdx
0x180046b90  mov     rdx, [rsp+148h+var_98]
0x180046b98  mov     [rsp+148h+var_120], rdx
0x180046b9d  mov     rdx, [rsp+148h+var_90]
0x180046ba5  mov     [rsp+148h+var_128], rdx
0x180046baa  mov     r9d, [rsp+148h+var_E0]
0x180046baf  mov     r8, [rsp+148h+var_88]
0x180046bb7  mov     rdx, [rsp+148h+var_80]
0x180046bbf  mov     rax, [rax+18h]
0x180046bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046bc8  mov     ebx, eax
0x180046bca  test    r13, r13
0x180046bcd  jz      short loc_180046BD7
0x180046bcf  mov     eax, [rsp+148h+var_E4]
0x180046bd3  mov     [r13+0], eax
0x180046bd7  test    ebx, ebx
0x180046bd9  jnz     short loc_180046BE3
0x180046bdb  mov     ebx, r14d
0x180046bde  jmp     loc_180046D25
0x180046be3  cmp     ebx, r12d
0x180046be6  jnz     loc_180046D27
0x180046bec  test    byte ptr cs:_bidGblFlags, 2
0x180046bf3  jz      short loc_180046C0A
0x180046bf5  mov     r8d, 1D0h; unsigned int
0x180046bfb  lea     rdx, aCrootbinderCre_1; "<CRootBinder::CreateRow|OLEDB|ERR> "
0x180046c02  mov     ecx, r12d; int
0x180046c05  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180046c0a  xor     r12d, r12d
0x180046c0d  cmp     [rsp+148h+var_E4], r12d
0x180046c12  setnz   r12b
0x180046c16  mov     [rsp+148h+var_E8], 0
0x180046c1e  mov     [rsp+148h+var_C8], 0
0x180046c2a  mov     [rsp+148h+var_60], 0
0x180046c35  movups  xmm0, xmmword ptr cs:DBPROPSET_PROPERTIESINERROR.Data1
0x180046c3c  movdqu  [rsp+148h+var_5C], xmm0
0x180046c45  mov     [rsp+148h+var_68], 0
0x180046c51  mov     rcx, [rsp+148h+var_D8]
0x180046c56  test    rcx, rcx
0x180046c59  jnz     short loc_180046CA9
0x180046c5b  mov     rcx, [rsp+148h+var_D0]
0x180046c60  mov     rax, [rcx]
0x180046c63  lea     r8, [rsp+148h+var_D8]
0x180046c68  lea     rdx, IID_IDBProperties
0x180046c6f  mov     rax, [rax]
0x180046c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c77  test    eax, eax
0x180046c79  jns     short loc_180046CA4
0x180046c7b  mov     rcx, r15; this
0x180046c7e  call    ?CleanPropSetErr@CRootBinder@@AEAAXXZ; CRootBinder::CleanPropSetErr(void)
0x180046c83  mov     dword ptr [rsi+160h], 80004005h
0x180046c8d  mov     dword ptr [rsi+15Ch], 2
0x180046c97  mov     r12, [rsp+148h+var_C0]
0x180046c9f  jmp     loc_180046D46
0x180046ca4  mov     rcx, [rsp+148h+var_D8]
0x180046ca9  mov     rax, [rcx]
0x180046cac  lea     rdx, [rsp+148h+var_C8]
0x180046cb4  mov     [rsp+148h+var_128], rdx
0x180046cb9  lea     r9, [rsp+148h+var_E8]
0x180046cbe  lea     r8, [rsp+148h+var_68]
0x180046cc6  mov     edx, 1
0x180046ccb  mov     rax, [rax+18h]
0x180046ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cd4  mov     r14d, eax
0x180046cd7  test    eax, eax
0x180046cd9  jnz     short loc_180046D00
0x180046cdb  lea     rcx, [rsi+0F0h]
0x180046ce2  mov     r8d, [rsp+148h+var_E8]
0x180046ce7  mov     rdx, [rsp+148h+var_C8]
0x180046cef  call    ?HrInitImpl@?$TUtlSetArray@UtagDBPROPSET@@U_GUID@@VCPropSet@@@@AEAAJPEAUtagDBPROPSET@@KKK@Z; TUtlSetArray<tagDBPROPSET,_GUID,CPropSet>::HrInitImpl(tagDBPROPSET *,ulong,ulong,ulong)
0x180046cf4  mov     dword ptr [rsi+15Ch], 1
0x180046cfe  jmp     short loc_180046D25
0x180046d00  mov     rcx, r15; this
0x180046d03  call    ?CleanPropSetErr@CRootBinder@@AEAAXXZ; CRootBinder::CleanPropSetErr(void)
0x180046d08  mov     eax, 80004005h
0x180046d0d  test    r12d, r12d
0x180046d10  cmovz   eax, r14d
0x180046d14  mov     [r15+168h], eax
0x180046d1b  mov     dword ptr [rsi+15Ch], 2
0x180046d25  jmp     short loc_180046D3E
0x180046d27  mov     rcx, r15; this
0x180046d2a  call    ?CleanPropSetErr@CRootBinder@@AEAAXXZ; CRootBinder::CleanPropSetErr(void)
0x180046d2f  nop
0x180046d30  mov     r12, [rsp+148h+var_C0]
0x180046d38  jmp     short loc_180046D46
0x180046d3a  mov     ebx, [rsp+148h+var_E0]
0x180046d3e  mov     r12, [rsp+148h+var_C0]
0x180046d46  mov     rcx, [rsp+148h+var_D8]
0x180046d4b  test    rcx, rcx
0x180046d4e  jz      short loc_180046D5C
0x180046d50  mov     rax, [rcx]
0x180046d53  mov     rax, [rax+10h]
0x180046d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d5c  mov     rcx, [rsp+148h+var_D0]
0x180046d61  test    rcx, rcx
0x180046d64  jz      short loc_180046D72
0x180046d66  mov     rax, [rcx]
0x180046d69  mov     rax, [rax+10h]
0x180046d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d72  mov     rcx, r12; lpCriticalSection
0x180046d75  call    cs:__imp_LeaveCriticalSection
0x180046d7b  test    ebx, ebx
0x180046d7d  jns     short loc_180046D8D
0x180046d7f  lea     rdx, IID_ICreateRow; struct _GUID *
0x180046d86  mov     ecx, ebx; int
0x180046d88  call    ?PostHResult@@YAJJPEBU_GUID@@@Z; PostHResult(long,_GUID const *)
0x180046d8d  mov     eax, ebx
0x180046d8f  mov     rcx, [rsp+148h+var_48]
0x180046d97  xor     rcx, rsp; StackCookie
0x180046d9a  call    __security_check_cookie
0x180046d9f  add     rsp, 118h
0x180046da6  pop     r15
0x180046da8  pop     r14
0x180046daa  pop     r13
0x180046dac  pop     r12
0x180046dae  pop     rsi
0x180046daf  pop     rbx
0x180046db0  retn
```
