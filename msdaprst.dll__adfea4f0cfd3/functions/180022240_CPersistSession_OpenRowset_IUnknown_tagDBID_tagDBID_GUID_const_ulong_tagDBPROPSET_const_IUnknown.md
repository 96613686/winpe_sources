# CPersistSession::OpenRowset(IUnknown *,tagDBID *,tagDBID *,_GUID const &,ulong,tagDBPROPSET * const,IUnknown * *)

- ea: `0x180022240`
- end: `0x180022d47`
- name: `?OpenRowset@CPersistSession@@UEAAJPEAUIUnknown@@PEAUtagDBID@@1AEBU_GUID@@KQEAUtagDBPROPSET@@PEAPEAU2@@Z`
- size: `2823`
- prototype: `__int64 __fastcall(CPersistSession *__hidden this, struct IUnknown *, struct tagDBID *, struct tagDBID *, const struct _GUID *, unsigned int, struct tagDBPROPSET *const, struct IUnknown **)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001dd4`
- `0x180002770`
- `0x180014ad0`
- `0x1800158e0`
- `0x180015e94`
- `0x1800164dc`
- `0x180016584`
- `0x1800190bc`
- `0x18001b008`
- `0x180021674`
- `0x1800219d4`
- `0x180021be8`
- `0x180022240`
- `0x180022d50`
- `0x180023484`
- `0x1800239ec`
- `0x18002dca4`
- `0x18002e554`
- `0x180031010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800224b3`
- `msvcrt!_wcsnicmp` at `0x1800224d4`
- `msvcrt!_wcsnicmp` at `0x1800224f5`
- `msvcrt!_wcsnicmp` at `0x180022659`
- `msvcrt!_wcsnicmp` at `0x1800226ad`
- `msvcrt!_wcsnicmp` at `0x1800226db`
- `msvcrt!_wcsnicmp` at `0x1800224b3`
- `msvcrt!_wcsnicmp` at `0x1800224d4`
- `msvcrt!_wcsnicmp` at `0x1800224f5`
- `msvcrt!_wcsnicmp` at `0x180022659`
- `msvcrt!_wcsnicmp` at `0x1800226ad`
- `msvcrt!_wcsnicmp` at `0x1800226db`
- `msvcrt!_wfsopen` at `0x180022700`
- `msvcrt!_wfsopen` at `0x180022700`
- `msvcrt!_get_osfhandle` at `0x180022729`
- `msvcrt!_get_osfhandle` at `0x180022729`
- `msvcrt!_fileno` at `0x18002271b`
- `msvcrt!_fileno` at `0x18002271b`
- `msvcrt!fclose` at `0x180022758`
- `msvcrt!fclose` at `0x180022758`
- `KERNEL32!GetFileType` at `0x18002273e`
- `KERNEL32!GetFileType` at `0x18002273e`
- `KERNEL32!GetCurrentThreadId` at `0x18002228f`
- `KERNEL32!GetCurrentThreadId` at `0x18002228f`
- `KERNEL32!LeaveCriticalSection` at `0x18002231a`
- `KERNEL32!LeaveCriticalSection` at `0x1800223bb`
- `KERNEL32!LeaveCriticalSection` at `0x180022428`
- `KERNEL32!LeaveCriticalSection` at `0x180022492`
- `KERNEL32!LeaveCriticalSection` at `0x180022cc4`
- `KERNEL32!LeaveCriticalSection` at `0x180022d22`
- `KERNEL32!LeaveCriticalSection` at `0x18002231a`
- `KERNEL32!LeaveCriticalSection` at `0x1800223bb`
- `KERNEL32!LeaveCriticalSection` at `0x180022428`
- `KERNEL32!LeaveCriticalSection` at `0x180022492`
- `KERNEL32!LeaveCriticalSection` at `0x180022cc4`
- `KERNEL32!LeaveCriticalSection` at `0x180022d22`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180022845`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180022c32`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180022845`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180022c32`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800222cf`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800222cf`
- `MSDART!UMSEnterCSWraper` at `0x180022271`
- `MSDART!UMSEnterCSWraper` at `0x180022271`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CPersistSession::OpenRowset(
        CPersistSession *this,
        struct IUnknown *a2,
        struct tagDBID *a3,
        struct tagDBID *a4,
        struct _GUID *a5,
        unsigned int a6,
        struct tagDBPROPSET *const a7,
        struct IUnknown **a8)
{
  char *v11; // r15
  _DWORD *v12; // rbx
  DWORD *v13; // rsi
  _DWORD *v14; // rdi
  int v15; // ecx
  unsigned int v16; // r14d
  bool v17; // zf
  __int64 v18; // rcx
  LPOLESTR pwszName; // rcx
  CStreamWrapper *v21; // rax
  _QWORD *v22; // rdx
  HINSTANCE ResourceInstance; // rax
  CPersistSession *v24; // rcx
  int v25; // r12d
  int v26; // eax
  const wchar_t *v27; // rcx
  FILE *v28; // rax
  FILE *v29; // r14
  int v30; // eax
  void *osfhandle; // rax
  int Instance; // eax
  int v33; // r14d
  CFileStream *v34; // r12
  const unsigned __int16 *v35; // r8
  int v36; // r14d
  unsigned int v37; // edx
  CPersistSession *v38; // rcx
  CStreamWrapper *v39; // r12
  HINSTANCE v40; // rdx
  unsigned int v41; // r9d
  CStreamWrapper *v42; // rax
  int v43; // eax
  int v44; // r13d
  int v45; // eax
  int v46; // r13d
  int v47; // eax
  int v48; // r12d
  int v49; // eax
  int v50; // r12d
  int v51; // eax
  int v52; // r12d
  int v53; // eax
  int v54; // r12d
  int v55; // eax
  int v56; // r12d
  __int64 v57; // [rsp+30h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v58)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-B0h] BYREF
  struct IUnknown *v59; // [rsp+40h] [rbp-A8h] BYREF
  _QWORD v60[2]; // [rsp+48h] [rbp-A0h] BYREF
  struct IUnknown *v61[4]; // [rsp+58h] [rbp-90h] BYREF
  char v62[8]; // [rsp+78h] [rbp-70h] BYREF
  IErrorInfo *pperrinfo; // [rsp+80h] [rbp-68h] BYREF
  int v64; // [rsp+88h] [rbp-60h]
  __int64 v65; // [rsp+90h] [rbp-58h]
  _QWORD *v66; // [rsp+A0h] [rbp-48h]
  char *v67; // [rsp+A8h] [rbp-40h]
  CStreamWrapper *v70; // [rsp+108h] [rbp+20h] BYREF

  v11 = (char *)this + 48;
  v61[3] = (struct IUnknown *)((char *)this + 48);
  UMSEnterCSWraper((char *)this + 48);
  v12 = v11 + 12;
  v61[2] = (struct IUnknown *)(v11 + 12);
  v13 = (DWORD *)(v11 + 8);
  if ( !*((_DWORD *)v11 + 3) )
    *v13 = GetCurrentThreadId();
  v60[1] = v11 + 8;
  ++*v12;
  v14 = v11 + 16;
  v61[1] = (struct IUnknown *)(v11 + 16);
  ++*((_DWORD *)v11 + 4);
  v67 = v11;
  v70 = (CStreamWrapper *)*((_QWORD *)this + 565);
  SetErrorInfo(0, 0);
  *((GUID *)this + 6) = IID_IOpenRowset;
  *((_DWORD *)this + 1053) = 0;
  if ( a4 )
  {
    v15 = -2147217867;
    goto LABEL_5;
  }
  if ( !a3 )
  {
    v15 = -2147024809;
    goto LABEL_5;
  }
  if ( a2 )
  {
    v15 = -2147217886;
LABEL_5:
    v16 = Exit(v15, 0);
    --*v14;
    v17 = (*v12)-- == 1;
    if ( v17 )
      *v13 = -1;
    goto LABEL_7;
  }
  v59 = 0;
  v61[0] = 0;
  v60[0] = 0;
  v58 = 0;
  v57 = 0;
  if ( a3->eKind != 2 )
  {
    v16 = Exit(-2147217865, 0);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v57);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v58);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v60);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v59);
    --*v14;
    v17 = (*v12)-- == 1;
    if ( v17 )
      *v13 = -1;
    goto LABEL_7;
  }
  pwszName = a3->uName.pwszName;
  if ( !pwszName )
  {
    v16 = Exit(-2147217865, 0);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v57);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v58);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v60);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v59);
    --*v14;
    v17 = (*v12)-- == 1;
    if ( v17 )
      *v13 = -1;
    goto LABEL_7;
  }
  if ( !*pwszName )
  {
    v16 = Exit(-2147217865, 0);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v57);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v58);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v60);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v59);
    --*v14;
    v17 = (*v12)-- == 1;
    if ( v17 )
      *v13 = -1;
    goto LABEL_7;
  }
  if ( !_wcsnicmp(pwszName, L"http://", 7u)
    || !_wcsnicmp(a3->uName.pwszName, L"https://", 8u)
    || !_wcsnicmp(a3->uName.pwszName, L"ftp://", 6u) )
  {
    LODWORD(a4) = 1;
  }
  v21 = *(CStreamWrapper **)v70;
  v70 = v21;
  v22 = *(_QWORD **)v21;
  v66 = *(_QWORD **)v21;
  if ( (_DWORD)a4 == 1 )
  {
    ResourceInstance = GetResourceInstance(g_hInstancePersistMain);
    v25 = 0;
    if ( !((unsigned int (__fastcall *)(CStreamWrapper *, LPOLESTR, HINSTANCE, __int64, int))v66[6])(
            v70,
            a3->uName.pwszName,
            ResourceInstance,
            2001,
            2002) )
    {
      CError::PostError((CPersistSession *)((char *)this + 80), -2147467259, 0x7D0u);
      if ( (bidGblFlags & 2) != 0 && off_180049C70[0] )
        bidTraceW(off_1800491F8[0], 122880, off_180049C70[0], 2147500037LL, 120);
      ThrowHR(-2147467259);
    }
    LODWORD(v70) = 0;
  }
  else
  {
    if ( !((unsigned int (__fastcall *)(CStreamWrapper *))v22[9])(v21) )
    {
      CError::PostError((CPersistSession *)((char *)this + 80), -2147467259, 0x7D0u);
      if ( (bidGblFlags & 2) != 0 && off_180049C68[0] )
        bidTraceW(off_1800491F8[0], 133120, off_180049C68[0], 2147500037LL, 130);
      ThrowHR(-2147467259);
    }
    LODWORD(v70) = 0;
    v25 = 0;
    if ( _wcsnicmp(a3->uName.pwszName, L"file://", 7u) )
      goto LABEL_46;
  }
  if ( !(unsigned int)CPersistSession::GetURLMonDLL(v24) )
  {
    if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, LPOLESTR, _QWORD))CPersistSession::m_pIsValidURL)(
                         0,
                         a3->uName.pwszName,
                         0) )
    {
      LODWORD(v70) = 0;
    }
    else
    {
      LODWORD(v70) = 1;
      if ( _wcsnicmp(a3->uName.pwszName, L"file://", 7u) )
        goto LABEL_53;
    }
  }
LABEL_46:
  v26 = _wcsnicmp(a3->uName.pwszName, L"file://", 7u);
  v27 = a3->uName.pwszName;
  if ( !v26 )
    v27 += 7;
  v28 = _wfsopen(v27, L"r", 64);
  v29 = v28;
  if ( v28 )
  {
    v30 = _fileno(v28);
    osfhandle = (void *)_get_osfhandle(v30);
    if ( osfhandle != (void *)-1LL && GetFileType(osfhandle) == 1 )
      v25 = 1;
    fclose(v29);
    if ( v25 )
    {
LABEL_53:
      Instance = ATL::CComObject<CFileStream>::CreateInstance(v61);
      v33 = Instance;
      if ( Instance < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049C60[0] )
          bidTraceW(off_1800491F8[0], 188416, off_180049C60[0], (unsigned int)Instance, 184);
        ThrowHR(v33);
      }
      v34 = (CFileStream *)v61[0];
      ((void (__fastcall *)(struct IUnknown *))v61[0]->lpVtbl->AddRef)(v61[0]);
      v36 = CFileStream::Open(v34, a3->uName.pwszName, v35);
      if ( v36 >= 0 )
        ATL::AtlComPtrAssign(&v59, (struct IUnknown *)v34);
      (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v34 + 16LL))(v34);
      v39 = 0;
      if ( v36 < 0 )
      {
        if ( v36 == -2147024864 || !(_DWORD)v70 )
          goto LABEL_67;
        v36 = CPersistSession::OpenStreamFromURL(v38, a3->uName.pwszName, (struct IStream **)&v59);
        if ( v36 < 0 )
        {
          GetErrorInfo(0, &pperrinfo);
          v64 = 0;
          v65 = 0;
          if ( !pperrinfo )
            CPersistErrorCache::AddHMODULEError((CPersistErrorCache *)v62, v40, v36, v41);
          CPersistErrorCache::~CPersistErrorCache((CPersistErrorCache *)v62);
LABEL_67:
          if ( (bidGblFlags & 2) != 0 && off_180049C58[0] )
            bidTraceW(off_1800491F8[0], 207872, off_180049C58[0], (unsigned int)v36, 203);
          ThrowHR(v36);
        }
      }
      v42 = (CStreamWrapper *)MMMAlloc(0x30u, v37);
      v70 = v42;
      if ( v42 )
        v39 = CStreamWrapper::CStreamWrapper(v42, 1);
      v70 = v39;
      if ( !v39 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049C50[0] )
          bidTraceW(off_1800491F8[0], 216064, off_180049C50[0], 2147942414LL, 211);
        ThrowHR(-2147024882);
      }
      v43 = CStreamWrapper::SetStream(v39, v59);
      v44 = v43;
      if ( v43 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049C48[0] )
          bidTraceW(off_1800491F8[0], 219136, off_180049C48[0], (unsigned int)v43, 214);
        ThrowHR(v44);
      }
      v45 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))this + 9))(
              *((_QWORD *)this + 9),
              &IID_IRDSService,
              v60);
      v46 = v45;
      if ( v45 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049C40[0] )
          bidTraceW(off_1800491F8[0], 222208, off_180049C40[0], (unsigned int)v45, 217);
        ThrowHR(v46);
      }
      v47 = (*(__int64 (__fastcall **)(_QWORD, GUID *, CStreamWrapper *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v60[0] + 32LL))(
              v60[0],
              &IID_IRowset,
              v39,
              &v58);
      v48 = v47;
      if ( v47 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049C38[0] )
          bidTraceW(off_1800491F8[0], 223232, off_180049C38[0], (unsigned int)v47, 218);
        ThrowHR(v48);
      }
      v49 = (**v58)(v58, &IID_IRowsetConnection, &v57);
      v50 = v49;
      if ( v49 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049C30[0] )
          bidTraceW(off_1800491F8[0], 224256, off_180049C30[0], (unsigned int)v49, 219);
        ThrowHR(v50);
      }
      v51 = (*(__int64 (__fastcall **)(__int64, CPersistSession *))(*(_QWORD *)v57 + 24LL))(v57, this);
      v52 = v51;
      if ( v51 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049C28[0] )
          bidTraceW(off_1800491F8[0], 226304, off_180049C28[0], (unsigned int)v51, 221);
        ThrowHR(v52);
      }
      v53 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v57 + 56LL))(v57, 0);
      v54 = v53;
      if ( v53 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049C20[0] )
          bidTraceW(off_1800491F8[0], 227328, off_180049C20[0], (unsigned int)v53, 222);
        ThrowHR(v54);
      }
      v55 = (**v58)(v58, a5, (__int64 *)a8);
      v56 = v55;
      if ( v55 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049C18[0] )
          bidTraceW(off_1800491F8[0], 228352, off_180049C18[0], (unsigned int)v55, 223);
        ThrowHR(v56);
      }
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v70);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v57);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v58);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v60);
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v59);
      v15 = v36;
      goto LABEL_5;
    }
  }
  GetErrorInfo(0, &pperrinfo);
  v64 = 0;
  v65 = 0;
  CPersistErrorCache::AddInternalError((CPersistErrorCache *)v62, -2147287038, a3->uName.pwszName, 0x82u);
  v16 = Exit(-2147287038, 0);
  CPersistErrorCache::~CPersistErrorCache((CPersistErrorCache *)v62);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v57);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v58);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v60);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v59);
  --*v14;
  v17 = (*v12)-- == 1;
  if ( v17 )
    *v13 = -1;
LABEL_7:
  v18 = *(_QWORD *)v11;
  --*(_DWORD *)(v18 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 8));
  return v16;
}

```

## disassembly

```asm
0x180022240  mov     [rsp+arg_8], rdx
0x180022245  mov     [rsp+arg_0], rcx
0x18002224a  push    rbx
0x18002224b  push    rsi
0x18002224c  push    rdi
0x18002224d  push    r12
0x18002224f  push    r13
0x180022251  push    r14
0x180022253  push    r15
0x180022255  sub     rsp, 0B0h
0x18002225c  mov     r12, r9
0x18002225f  mov     r13, r8
0x180022262  mov     r14, rcx
0x180022265  lea     r15, [rcx+30h]
0x180022269  mov     [rsp+0E8h+var_78], r15
0x18002226e  mov     rcx, r15
0x180022271  call    cs:__imp_UMSEnterCSWraper
0x180022278  nop     dword ptr [rax+rax+00h]
0x18002227d  lea     rbx, [r15+0Ch]
0x180022281  mov     [rsp+0E8h+var_80], rbx
0x180022286  lea     rsi, [r15+8]
0x18002228a  cmp     dword ptr [rbx], 0
0x18002228d  jnz     short loc_18002229D
0x18002228f  call    cs:__imp_GetCurrentThreadId
0x180022296  nop     dword ptr [rax+rax+00h]
0x18002229b  mov     [rsi], eax
0x18002229d  mov     [rsp+0E8h+var_98], rsi
0x1800222a2  mov     eax, 1
0x1800222a7  add     [rbx], eax
0x1800222a9  lea     rdi, [r15+10h]
0x1800222ad  mov     [rsp+0E8h+var_88], rdi
0x1800222b2  add     [rdi], eax
0x1800222b4  mov     [rsp+0E8h+var_40], r15
0x1800222bc  mov     rax, [r14+11A8h]
0x1800222c3  mov     [rsp+0E8h+arg_18], rax
0x1800222cb  xor     edx, edx; perrinfo
0x1800222cd  xor     ecx, ecx; dwReserved
0x1800222cf  call    cs:__imp_SetErrorInfo
0x1800222d6  nop     dword ptr [rax+rax+00h]
0x1800222db  movups  xmm0, xmmword ptr cs:IID_IOpenRowset.Data1
0x1800222e2  movdqu  xmmword ptr [r14+60h], xmm0
0x1800222e8  xor     ecx, ecx
0x1800222ea  mov     [r14+1074h], ecx
0x1800222f1  test    r12, r12
0x1800222f4  jz      short loc_18002232E
0x1800222f6  mov     ecx, 80040E35h; int
0x1800222fb  xor     edx, edx; unsigned int
0x1800222fd  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180022302  mov     r14d, eax
0x180022305  or      edx, 0FFFFFFFFh
0x180022308  add     [rdi], edx
0x18002230a  add     [rbx], edx
0x18002230c  jnz     short loc_180022310
0x18002230e  mov     [rsi], edx
0x180022310  mov     rcx, [r15]
0x180022313  dec     dword ptr [rcx+30h]
0x180022316  add     rcx, 8; lpCriticalSection
0x18002231a  call    cs:__imp_LeaveCriticalSection
0x180022321  nop     dword ptr [rax+rax+00h]
0x180022326  mov     eax, r14d
0x180022329  jmp     loc_180022D33
0x18002232e  test    r13, r13
0x180022331  jnz     short loc_18002233A
0x180022333  mov     ecx, 80070057h
0x180022338  jmp     short loc_1800222FB
0x18002233a  cmp     [rsp+0E8h+arg_8], r12
0x180022342  jz      short loc_18002234B
0x180022344  mov     ecx, 80040E22h
0x180022349  jmp     short loc_1800222FB
0x18002234b  mov     [rsp+0E8h+var_A8], r12
0x180022350  mov     [rsp+0E8h+var_90], r12
0x180022355  mov     [rsp+0E8h+var_A0], r12
0x18002235a  mov     [rsp+0E8h+var_B0], r12
0x18002235f  mov     [rsp+0E8h+var_B8], r12
0x180022364  cmp     dword ptr [r13+10h], 2
0x180022369  jz      short loc_1800223CF
0x18002236b  xor     edx, edx; unsigned int
0x18002236d  mov     ecx, 80040E37h; int
0x180022372  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180022377  mov     r14d, eax
0x18002237a  lea     rcx, [rsp+0E8h+var_B8]
0x18002237f  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180022384  nop
0x180022385  lea     rcx, [rsp+0E8h+var_B0]
0x18002238a  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002238f  nop
0x180022390  lea     rcx, [rsp+0E8h+var_A0]
0x180022395  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002239a  nop
0x18002239b  lea     rcx, [rsp+0E8h+var_A8]
0x1800223a0  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800223a5  nop
0x1800223a6  or      edx, 0FFFFFFFFh
0x1800223a9  add     [rdi], edx
0x1800223ab  add     [rbx], edx
0x1800223ad  jnz     short loc_1800223B1
0x1800223af  mov     [rsi], edx
0x1800223b1  mov     rcx, [r15]
0x1800223b4  dec     dword ptr [rcx+30h]
0x1800223b7  add     rcx, 8; lpCriticalSection
0x1800223bb  call    cs:__imp_LeaveCriticalSection
0x1800223c2  nop     dword ptr [rax+rax+00h]
0x1800223c7  mov     eax, r14d
0x1800223ca  jmp     loc_180022D33
0x1800223cf  mov     rcx, [r13+18h]; String1
0x1800223d3  test    rcx, rcx
0x1800223d6  jnz     short loc_18002243C
0x1800223d8  xor     edx, edx; unsigned int
0x1800223da  mov     ecx, 80040E37h; int
0x1800223df  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800223e4  mov     r14d, eax
0x1800223e7  lea     rcx, [rsp+0E8h+var_B8]
0x1800223ec  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800223f1  nop
0x1800223f2  lea     rcx, [rsp+0E8h+var_B0]
0x1800223f7  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800223fc  nop
0x1800223fd  lea     rcx, [rsp+0E8h+var_A0]
0x180022402  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180022407  nop
0x180022408  lea     rcx, [rsp+0E8h+var_A8]
0x18002240d  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180022412  nop
0x180022413  or      edx, 0FFFFFFFFh
0x180022416  add     [rdi], edx
0x180022418  add     [rbx], edx
0x18002241a  jnz     short loc_18002241E
0x18002241c  mov     [rsi], edx
0x18002241e  mov     rcx, [r15]
0x180022421  dec     dword ptr [rcx+30h]
0x180022424  add     rcx, 8; lpCriticalSection
0x180022428  call    cs:__imp_LeaveCriticalSection
0x18002242f  nop     dword ptr [rax+rax+00h]
0x180022434  mov     eax, r14d
0x180022437  jmp     loc_180022D33
0x18002243c  cmp     [rcx], r12w
0x180022440  jnz     short loc_1800224A6
0x180022442  xor     edx, edx; unsigned int
0x180022444  mov     ecx, 80040E37h; int
0x180022449  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18002244e  mov     r14d, eax
0x180022451  lea     rcx, [rsp+0E8h+var_B8]
0x180022456  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002245b  nop
0x18002245c  lea     rcx, [rsp+0E8h+var_B0]
0x180022461  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180022466  nop
0x180022467  lea     rcx, [rsp+0E8h+var_A0]
0x18002246c  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180022471  nop
0x180022472  lea     rcx, [rsp+0E8h+var_A8]
0x180022477  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002247c  nop
0x18002247d  or      edx, 0FFFFFFFFh
0x180022480  add     [rdi], edx
0x180022482  add     [rbx], edx
0x180022484  jnz     short loc_180022488
0x180022486  mov     [rsi], edx
0x180022488  mov     rcx, [r15]
0x18002248b  dec     dword ptr [rcx+30h]
0x18002248e  add     rcx, 8; lpCriticalSection
0x180022492  call    cs:__imp_LeaveCriticalSection
0x180022499  nop     dword ptr [rax+rax+00h]
0x18002249e  mov     eax, r14d
0x1800224a1  jmp     loc_180022D33
0x1800224a6  mov     r8d, 7; MaxCount
0x1800224ac  lea     rdx, aHttp; "http://"
0x1800224b3  call    cs:__imp__wcsnicmp
0x1800224ba  nop     dword ptr [rax+rax+00h]
0x1800224bf  test    eax, eax
0x1800224c1  jz      short loc_180022505
0x1800224c3  mov     r8d, 8; MaxCount
0x1800224c9  lea     rdx, aHttps; "https://"
0x1800224d0  mov     rcx, [r13+18h]; String1
0x1800224d4  call    cs:__imp__wcsnicmp
0x1800224db  nop     dword ptr [rax+rax+00h]
0x1800224e0  test    eax, eax
0x1800224e2  jz      short loc_180022505
0x1800224e4  mov     r8d, 6; MaxCount
0x1800224ea  lea     rdx, aFtp; "ftp://"
0x1800224f1  mov     rcx, [r13+18h]; String1
0x1800224f5  call    cs:__imp__wcsnicmp
0x1800224fc  nop     dword ptr [rax+rax+00h]
0x180022501  test    eax, eax
0x180022503  jnz     short loc_18002250B
0x180022505  mov     r12d, 1
0x18002250b  mov     rax, [rsp+0E8h+arg_18]
0x180022513  mov     rax, [rax]
0x180022516  mov     [rsp+0E8h+arg_18], rax
0x18002251e  mov     rdx, [rax]
0x180022521  mov     [rsp+0E8h+var_48], rdx
0x180022529  cmp     r12d, 1
0x18002252d  jnz     loc_1800225D6
0x180022533  mov     rcx, cs:?g_hInstancePersistMain@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18002253a  call    ?GetResourceInstance@@YAPEAUHINSTANCE__@@PEAU1@@Z; GetResourceInstance(HINSTANCE__ *)
0x18002253f  mov     [rsp+0E8h+var_C8], 7D2h
0x180022547  mov     r9d, 7D1h
0x18002254d  mov     r8, rax
0x180022550  mov     rdx, [r13+18h]
0x180022554  mov     rcx, [rsp+0E8h+arg_18]
0x18002255c  mov     rax, [rsp+0E8h+var_48]
0x180022564  mov     rax, [rax+30h]
0x180022568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002256d  xor     r12d, r12d
0x180022570  test    eax, eax
0x180022572  jnz     short loc_1800225C9
0x180022574  mov     ebx, 80004005h
0x180022579  mov     r8d, 7D0h; unsigned int
0x18002257f  mov     edx, ebx; int
0x180022581  lea     rcx, [r14+50h]; this
0x180022585  call    ?PostError@CError@@QEAAXJK@Z; CError::PostError(long,ulong)
0x18002258a  test    byte ptr cs:_bidGblFlags, 2
0x180022591  jz      short loc_1800225C2
0x180022593  mov     rax, cs:off_180049C70; "<CPersistSession::OpenRowset|ADO|ERR>  "...
0x18002259a  test    rax, rax
0x18002259d  jz      short loc_1800225C2
0x18002259f  mov     [rsp+0E8h+var_C8], 78h ; 'x'
0x1800225a7  mov     r9d, ebx
0x1800225aa  mov     r8, cs:off_180049C70; "<CPersistSession::OpenRowset|ADO|ERR>  "...
0x1800225b1  mov     edx, 1E000h
0x1800225b6  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800225bd  call    _bidTraceW
0x1800225c2  mov     ecx, ebx; int
0x1800225c4  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800225c9  mov     dword ptr [rsp+0E8h+arg_18], r12d
0x1800225d1  jmp     loc_180022671
0x1800225d6  mov     rcx, rax
0x1800225d9  mov     rax, [rdx+48h]
0x1800225dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225e2  xor     ecx, ecx; this
0x1800225e4  test    eax, eax
0x1800225e6  jnz     short loc_18002263D
0x1800225e8  mov     ebx, 80004005h
0x1800225ed  mov     r8d, 7D0h; unsigned int
0x1800225f3  mov     edx, ebx; int
0x1800225f5  lea     rcx, [r14+50h]; this
0x1800225f9  call    ?PostError@CError@@QEAAXJK@Z; CError::PostError(long,ulong)
0x1800225fe  test    byte ptr cs:_bidGblFlags, 2
0x180022605  jz      short loc_180022636
0x180022607  mov     rax, cs:off_180049C68; "<CPersistSession::OpenRowset|ADO|ERR>  "...
0x18002260e  test    rax, rax
0x180022611  jz      short loc_180022636
0x180022613  mov     [rsp+0E8h+var_C8], 82h
0x18002261b  mov     r9d, ebx
0x18002261e  mov     r8, cs:off_180049C68; "<CPersistSession::OpenRowset|ADO|ERR>  "...
0x180022625  mov     edx, 20800h
0x18002262a  mov     rcx, cs:off_1800491F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180022631  call    _bidTraceW
0x180022636  mov     ecx, ebx; int
0x180022638  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002263d  mov     dword ptr [rsp+0E8h+arg_18], ecx
0x180022644  test    r12d, r12d
0x180022647  jnz     short loc_18002266E
0x180022649  lea     r8d, [r12+7]; MaxCount
0x18002264e  lea     rdx, aFile; "file://"
0x180022655  mov     rcx, [r13+18h]; String1
0x180022659  call    cs:__imp__wcsnicmp
0x180022660  nop     dword ptr [rax+rax+00h]
0x180022665  xor     r12d, r12d
0x180022668  test    eax, eax
0x18002266a  jnz     short loc_1800226CA
0x18002266c  jmp     short loc_180022671
0x18002266e  xor     r12d, r12d
0x180022671  call    ?GetURLMonDLL@CPersistSession@@AEAAJXZ; CPersistSession::GetURLMonDLL(void)
0x180022676  test    eax, eax
0x180022678  jnz     short loc_1800226CA
0x18002267a  xor     r8d, r8d
0x18002267d  mov     rdx, [r13+18h]
0x180022681  xor     ecx, ecx
0x180022683  mov     rax, cs:?m_pIsValidURL@CPersistSession@@0P6AJPEAUIBindCtx@@PEBGK@ZEA; long (*CPersistSession::m_pIsValidURL)(IBindCtx *,ushort const *,ulong)
0x18002268a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002268f  test    eax, eax
0x180022691  jnz     short loc_1800226C2
0x180022693  mov     dword ptr [rsp+0E8h+arg_18], 1
0x18002269e  lea     r8d, [rax+7]; MaxCount
0x1800226a2  lea     rdx, aFile; "file://"
0x1800226a9  mov     rcx, [r13+18h]; String1
0x1800226ad  call    cs:__imp__wcsnicmp
0x1800226b4  nop     dword ptr [rax+rax+00h]
0x1800226b9  test    eax, eax
0x1800226bb  jz      short loc_1800226CA
0x1800226bd  jmp     loc_18002276D
0x1800226c2  mov     dword ptr [rsp+0E8h+arg_18], r12d
0x1800226ca  mov     r8d, 7; MaxCount
0x1800226d0  lea     rdx, aFile; "file://"
0x1800226d7  mov     rcx, [r13+18h]; String1
0x1800226db  call    cs:__imp__wcsnicmp
0x1800226e2  nop     dword ptr [rax+rax+00h]
0x1800226e7  mov     rcx, [r13+18h]
0x1800226eb  mov     r8d, 40h ; '@'; ShFlag
0x1800226f1  lea     rdx, aR; "r"
0x1800226f8  test    eax, eax
0x1800226fa  jnz     short loc_180022700
0x1800226fc  add     rcx, 0Eh; FileName
0x180022700  call    cs:__imp__wfsopen
0x180022707  nop     dword ptr [rax+rax+00h]
0x18002270c  mov     r14, rax
0x18002270f  test    rax, rax
0x180022712  jz      loc_180022C28
0x180022718  mov     rcx, rax; Stream
  ... truncated ...
```
