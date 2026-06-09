# CRunningObjectTable::Register(ulong,IUnknown *,IMoniker *,ulong *)

- ea: `0x18001ca60`
- end: `0x18001d027`
- name: `?Register@CRunningObjectTable@@UEAAJKPEAUIUnknown@@PEAUIMoniker@@PEAK@Z`
- size: `1479`
- prototype: `HRESULT __fastcall(CRunningObjectTable *this, unsigned int grfFlags, IUnknown *punkObject, IMoniker *pmkObjectName, unsigned int *pdwRegister)`
- caller_count: `0`
- callee_count: `17`
- tags: `reparse_path, service_task, installer_update, broker_com_uri`

## callees

- `0x180008280`
- `0x1800082c8`
- `0x180008f0c`
- `0x18000a70c`
- `0x18001bb48`
- `0x18001bc24`
- `0x18001c300`
- `0x18001c34c`
- `0x18001ca60`
- `0x18001d030`
- `0x18001d110`
- `0x180046460`
- `0x18004d474`
- `0x18006b264`
- `0x18006b2b0`
- `0x18006b50c`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cd1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cf80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cd1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cf80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cbfd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cbfd`
- `api-ms-win-core-com-l1-1-0!CoGetCurrentProcess` at `0x18001ce27`
- `api-ms-win-core-com-l1-1-0!CoGetCurrentProcess` at `0x18001ce27`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18001cbb3`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18001cbb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd62`
- `api-ms-win-core-com-private-l1-1-0!InternalIrotRegister` at `0x18001ce55`
- `api-ms-win-core-com-private-l1-1-0!InternalIrotRegister` at `0x18001ce55`
- `api-ms-win-core-com-private-l1-1-0!InternalCoRegisterDisconnectCallback` at `0x18001ce05`
- `api-ms-win-core-com-private-l1-1-0!InternalCoRegisterDisconnectCallback` at `0x18001ce05`
- `api-ms-win-core-com-private-l1-1-0!InternalCoUnregisterDisconnectCallback` at `0x18001ccb9`
- `api-ms-win-core-com-private-l1-1-0!InternalCoUnregisterDisconnectCallback` at `0x18001ccb9`

## string_xrefs

- `0x18001d011`: `Register object in ROT %p completed with status %08x`

## pseudocode

```c
__int64 __fastcall CRunningObjectTable::Register(
        CRunningObjectTable *this,
        unsigned int grfFlags,
        IUnknown *punkObject,
        IMoniker *pmkObjectName,
        unsigned int *pdwRegister)
{
  CROTItem *v5; // rbx
  tagMInterfacePointer *v6; // rsi
  tagMInterfacePointer *pMInterfacePointer; // r12
  int v10; // r14d
  unsigned int v11; // edx
  const char *v12; // r9
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT function; // edi
  HRESULT v15; // eax
  unsigned int cbBufferSize; // ecx
  CROTItem *v17; // rax
  const char *v18; // r9
  unsigned int CurrentApartmentId; // eax
  CRunningObjectTable *v20; // r8
  utl::vector<CROTItem *,utl::allocator<CROTItem *> > *p_rotList; // rdi
  CROTItem **MyBegin; // rdx
  CROTItem **MyEnd; // rcx
  CROTItem **v24; // rax
  signed __int64 v25; // rax
  unsigned __int64 v27; // rax
  unsigned int v28; // r15d
  DWORD CurrentProcess; // eax
  unsigned __int64 v30; // rcx
  const char *v31; // rcx
  TraceLevel v32; // r9d
  CROTItem *protitm; // [rsp+48h] [rbp-B8h] BYREF
  tagInterfaceData *pifdMoniker; // [rsp+50h] [rbp-B0h] BYREF
  CRunningObjectTable *file; // [rsp+58h] [rbp-A8h]
  CReadInterfaceDataFromInternalSourceMarshalingStream monikerStream; // [rsp+60h] [rbp-A0h] BYREF
  IProxyManager *pProxyManager; // [rsp+90h] [rbp-70h] BYREF
  void *pvNotifyCookie; // [rsp+98h] [rbp-68h] BYREF
  _FILETIME filetime; // [rsp+A0h] [rbp-60h] BYREF
  IUnknown *v41; // [rsp+A8h] [rbp-58h]
  unsigned int *v42; // [rsp+B0h] [rbp-50h]
  CBaseMInterfacePointerMarshalingStream v43; // [rsp+B8h] [rbp-48h] BYREF
  CTmpMkEqBuf tmeb; // [rsp+F0h] [rbp-10h] BYREF

  v5 = 0;
  file = this;
  v6 = 0;
  v41 = punkObject;
  v42 = pdwRegister;
  protitm = 0;
  pMInterfacePointer = 0;
  pifdMoniker = 0;
  v10 = -1;
  CheckInitDde(1);
  if ( (grfFlags & 0xFFFFFFFC) != 0
    || !IsValidInterface(punkObject)
    || !IsValidInterface(pmkObjectName)
    || !IsValidPtrOut(pdwRegister, 4u) )
  {
    function = -2147024809;
    goto LABEL_18;
  }
  lpVtbl = punkObject->lpVtbl;
  pProxyManager = 0;
  if ( !((unsigned int (__fastcall *)(IUnknown *, GUID *, IProxyManager **))lpVtbl->QueryInterface)(
          punkObject,
          &IID_IProxyManager,
          &pProxyManager) )
  {
    ((void (__fastcall *)(IProxyManager *))pProxyManager->lpVtbl->Release)(pProxyManager);
    function = -2147024809;
    goto LABEL_27;
  }
  *pdwRegister = 0;
  filetime = 0;
  function = GetMonikerCompareBuffer(pmkObjectName, &tmeb, &filetime, &pifdMoniker);
  if ( function >= 0 )
  {
    monikerStream.CAbstractMarshalingStream = 0;
    CAbstractMarshalingStream::CAbstractMarshalingStream(&monikerStream);
    monikerStream._fFree = 1;
    *(_QWORD *)&monikerStream._lOffset = 0;
    monikerStream._cbBufferSize = 0;
    monikerStream._pMInterfacePointer = 0;
    monikerStream.lpVtbl = (struct IStreamVtbl *)CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable';
    v15 = CoMarshalInterface(&monikerStream, &IID_IUnknown, punkObject, 1u, 0, ((grfFlags & 1) == 0) + 1);
    v6 = (tagMInterfacePointer *)pifdMoniker;
    function = v15;
    if ( v15 )
      goto LABEL_25;
    cbBufferSize = monikerStream._cbBufferSize;
    if ( monikerStream._cbDataSize )
      cbBufferSize = monikerStream._cbDataSize;
    monikerStream._pMInterfacePointer->ulCntData = cbBufferSize;
    pMInterfacePointer = monikerStream._pMInterfacePointer;
    monikerStream._pMInterfacePointer = 0;
    monikerStream._fFree = 0;
    v17 = (CROTItem *)HeapAlloc(g_hHeap, 0, 0x28u);
    v5 = v17;
    if ( v17 )
    {
      v17->_fDontCallApp = 0;
      CurrentApartmentId = GetCurrentApartmentId();
      v5->_scmregkey.dwEntryLoc = -1;
      v5->_hApt = CurrentApartmentId;
      v5->_pvStubRegistration = 0;
    }
    else
    {
      v5 = 0;
    }
    protitm = v5;
    if ( !v5 )
    {
      function = -2147024882;
      CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&monikerStream);
LABEL_22:
      if ( pMInterfacePointer )
      {
        v43.CAbstractMarshalingStream = 0;
        CAbstractMarshalingStream::CAbstractMarshalingStream(&v43);
        *(_QWORD *)&v43._lOffset = 0;
        v43._pMInterfacePointer = pMInterfacePointer;
        v43._fFree = 0;
        v43._cbBufferSize = pMInterfacePointer->ulCntData;
        v43.lpVtbl = (struct IStreamVtbl *)CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable';
        ReleaseMarshalingData(&v43);
        HeapFree(g_hHeap, 0, pMInterfacePointer);
        CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&v43);
      }
      goto LABEL_45;
    }
    COleStaticMutexSem::Request(&g_RotSem, "Unknown File", 0, v18);
    v20 = file;
    ++file->_wSigRotItem;
    p_rotList = &v20->_rotList;
    v5->_wItemSig = v20->_wSigRotItem;
    MyBegin = v20->_rotList._MyBegin;
    MyEnd = v20->_rotList._MyEnd;
    if ( MyBegin != MyEnd )
    {
      v27 = 0;
      v30 = MyEnd - MyBegin;
      while ( v27 < v30 )
      {
        if ( !MyBegin[v27] )
        {
          MyBegin[v27] = v5;
          v10 = v27;
          if ( (_DWORD)v27 == -1 )
            break;
          goto LABEL_33;
        }
        ++v27;
      }
    }
    v24 = v20->_rotList._MyEnd;
    if ( v24 == v20->_rotList._MyLimit )
    {
      if ( !utl::vector<CROTItem *,utl::allocator<CROTItem *>>::_PushBackOne2<CROTItem * const &>(
              (utl::vector<unsigned __int64,utl::allocator<unsigned __int64> > *)&v20->_rotList,
              (const unsigned __int64 *)&protitm) )
      {
        function = -2147024882;
        COleStaticMutexSem::Release(&g_RotSem);
        CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&monikerStream);
        v5 = protitm;
        goto LABEL_18;
      }
      v5 = protitm;
      v20 = file;
    }
    else
    {
      *v24 = v5;
      ++v20->_rotList._MyEnd;
    }
    v10 = p_rotList->_MyEnd - p_rotList->_MyBegin - 1;
LABEL_33:
    v28 = v10 | (v20->_wSigRotItem << 16);
    COleStaticMutexSem::Release(&g_RotSem);
    pvNotifyCookie = 0;
    function = InternalCoRegisterDisconnectCallback(
                 v41,
                 (unsigned int)((grfFlags & 1) == 0) + 1,
                 &file->IDisconnectSink,
                 v28,
                 &pvNotifyCookie);
    if ( function >= 0 )
    {
      v5->_pvStubRegistration = pvNotifyCookie;
      CurrentProcess = CoGetCurrentProcess();
      function = InternalIrotRegister(
                   &tmeb,
                   pMInterfacePointer,
                   v6,
                   &filetime,
                   CurrentProcess,
                   grfFlags & 2,
                   &v5->_scmregkey);
      if ( function < 0 )
        v5->_scmregkey.dwEntryLoc = -1;
      else
        *v42 = v28;
LABEL_25:
      CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&monikerStream);
      if ( function >= 0 )
      {
        CoTaskMemFree(v6);
        CoTaskMemFree(pMInterfacePointer);
        goto LABEL_27;
      }
      goto LABEL_18;
    }
    CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&monikerStream);
LABEL_18:
    if ( v5 )
    {
      v25 = _InterlockedCompareExchange64(
              (volatile signed __int64 *)&v5->_pvStubRegistration,
              0,
              (signed __int64)v5->_pvStubRegistration);
      if ( v25 )
        InternalCoUnregisterDisconnectCallback(v25);
      v6 = (tagMInterfacePointer *)pifdMoniker;
      v5 = protitm;
    }
    goto LABEL_22;
  }
  v6 = (tagMInterfacePointer *)pifdMoniker;
LABEL_45:
  if ( v6 )
  {
    monikerStream.CAbstractMarshalingStream = 0;
    CAbstractMarshalingStream::CAbstractMarshalingStream(&monikerStream);
    *(_QWORD *)&monikerStream._lOffset = 0;
    monikerStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
    monikerStream._pMInterfacePointer = v6;
    monikerStream._fFree = 0;
    monikerStream._cbBufferSize = v6->ulCntData;
    monikerStream.lpVtbl = (struct IStreamVtbl *)CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable';
    ReleaseMarshalingData(&monikerStream);
    HeapFree(g_hHeap, 0, v6);
    CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&monikerStream);
  }
  if ( v5 )
  {
    if ( v10 != -1 )
    {
      COleStaticMutexSem::Request(&g_RotSem, "Unknown File", 0, v12);
      file->_rotList._MyBegin[v10] = 0;
      COleStaticMutexSem::Release(&g_RotSem);
    }
    CROTItem::`scalar deleting destructor'(v5, v11);
  }
LABEL_27:
  if ( gfEnableTracing && IsWppLevelEnabled(INFO) )
    ComTraceMessageT<CFilteredRunningObjectTable *,long>(
      v31,
      "CRunningObjectTable::Register",
      785,
      v32,
      L"Register object in ROT %p completed with status %08x",
      file,
      function);
  return (unsigned int)function;
}

```

## disassembly

```asm
0x18001ca60  mov     [rsp-8+arg_8], rbx
0x18001ca65  push    rbp
0x18001ca66  push    rsi
0x18001ca67  push    rdi
0x18001ca68  push    r12
0x18001ca6a  push    r13
0x18001ca6c  push    r14
0x18001ca6e  push    r15
0x18001ca70  lea     rbp, [rsp-810h]
0x18001ca78  sub     rsp, 910h
0x18001ca7f  mov     rax, cs:__security_cookie
0x18001ca86  xor     rax, rsp
0x18001ca89  mov     [rbp+840h+var_40], rax
0x18001ca90  mov     r13, [rbp+840h+pv]
0x18001ca97  xor     ebx, ebx
0x18001ca99  mov     [rsp+940h+file], this
0x18001ca9e  xor     esi, esi
0x18001caa0  mov     rdi, pmkObjectName
0x18001caa3  mov     [rbp+840h+var_898], punkObject
0x18001caa7  mov     r15, punkObject
0x18001caaa  mov     [rsp+940h+var_900], grfFlags
0x18001caae  lea     ecx, [rbx+1]; fRegisteringServerObject
0x18001cab1  mov     [rbp+840h+var_890], r13
0x18001cab5  mov     [rsp+940h+protitm], rbx
0x18001caba  xor     r12d, r12d
0x18001cabd  mov     [rsp+940h+pifdMoniker], rsi
0x18001cac2  or      r14d, 0FFFFFFFFh
0x18001cac6  call    CheckInitDde
0x18001cacb  test    [rsp+940h+var_900], 0FFFFFFFCh
0x18001cad3  jnz     loc_18001CC9A
0x18001cad9  mov     this, r15; pv
0x18001cadc  call    IsValidInterface
0x18001cae1  test    eax, eax
0x18001cae3  jz      loc_18001CC9A
0x18001cae9  mov     this, rdi; pv
0x18001caec  call    IsValidInterface
0x18001caf1  test    eax, eax
0x18001caf3  jz      loc_18001CC9A
0x18001caf9  lea     grfFlags, [rbx+4]; cb
0x18001cafc  mov     this, r13; pv
0x18001caff  call    ?IsValidPtrOut@@YAHPEAX_K@Z; IsValidPtrOut(void *,unsigned __int64)
0x18001cb04  test    eax, eax
0x18001cb06  jz      loc_18001CC9A
0x18001cb0c  mov     rax, [r15]
0x18001cb0f  lea     punkObject, [rbp+840h+pProxyManager]
0x18001cb13  lea     rdx, IID_IProxyManager
0x18001cb1a  mov     [rbp+840h+pProxyManager], rsi
0x18001cb1e  mov     this, r15
0x18001cb21  mov     rax, [rax]
0x18001cb24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb29  test    eax, eax
0x18001cb2b  jz      loc_18001CE77
0x18001cb31  lea     pmkObjectName, [rsp+940h+pifdMoniker]; ppifdMoniker
0x18001cb36  mov     [r13+0], esi
0x18001cb3a  lea     punkObject, [rbp+840h+filetime]; pfiletime
0x18001cb3e  mov     qword ptr [rbp+840h+filetime.dwLowDateTime], rsi
0x18001cb42  lea     rdx, [rbp+840h+tmeb]; ptmpmkeqbuf
0x18001cb46  mov     this, rdi; pmk
0x18001cb49  call    ?GetMonikerCompareBuffer@@YAJPEAUIMoniker@@PEAVCTmpMkEqBuf@@PEAU_FILETIME@@PEAPEAUtagInterfaceData@@@Z; GetMonikerCompareBuffer(IMoniker *,CTmpMkEqBuf *,_FILETIME *,tagInterfaceData * *)
0x18001cb4e  mov     edi, eax
0x18001cb50  test    eax, eax
0x18001cb52  js      loc_18001CF1F
0x18001cb58  xorps   xmm0, xmm0
0x18001cb5b  lea     this, [rsp+940h+monikerStream]; this
0x18001cb60  movups  xmmword ptr [rsp+940h+monikerStream.lpVtbl], xmm0
0x18001cb65  call    ??0CAbstractMarshalingStream@@QEAA@XZ; CAbstractMarshalingStream::CAbstractMarshalingStream(void)
0x18001cb6a  mov     r13d, [rsp+940h+var_900]
0x18001cb6f  lea     ecx, [rbx+1]
0x18001cb72  not     r13d
0x18001cb75  mov     [rbp+840h+monikerStream._fFree], ecx
0x18001cb78  and     r13d, ecx
0x18001cb7b  mov     qword ptr [rsp+940h+monikerStream._lOffset], rsi
0x18001cb80  add     r13d, ecx
0x18001cb83  mov     [rsp+940h+monikerStream._cbBufferSize], esi
0x18001cb87  lea     rax, ??_7CReadInterfaceDataFromInternalSourceMarshalingStream@@6B@; const CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable'
0x18001cb8e  mov     [rsp+940h+mshlflags], r13d; mshlflags
0x18001cb93  mov     r9d, ecx; dwDestContext
0x18001cb96  mov     [rsp+940h+pvDestContext], rsi; pvDestContext
0x18001cb9b  mov     punkObject, r15; pUnk
0x18001cb9e  mov     [rbp+840h+monikerStream._pMInterfacePointer], rsi
0x18001cba2  lea     rdx, IID_IUnknown; riid
0x18001cba9  mov     [rsp+940h+monikerStream.lpVtbl], rax
0x18001cbae  lea     this, [rsp+940h+monikerStream]; pStm
0x18001cbb3  call    cs:__imp_CoMarshalInterface
0x18001cbba  nop     dword ptr [rax+rax+00h]
0x18001cbbf  mov     rsi, [rsp+940h+pifdMoniker]
0x18001cbc4  xor     r15d, r15d
0x18001cbc7  mov     edi, eax
0x18001cbc9  test    eax, eax
0x18001cbcb  jnz     loc_18001CD3E
0x18001cbd1  mov     eax, [rsp+940h+monikerStream._cbDataSize]
0x18001cbd5  lea     r8d, [rbx+28h]; dwBytes
0x18001cbd9  mov     ecx, [rsp+940h+monikerStream._cbBufferSize]
0x18001cbdd  test    eax, eax
0x18001cbdf  cmovnz  ecx, eax
0x18001cbe2  mov     rax, [rbp+840h+monikerStream._pMInterfacePointer]
0x18001cbe6  xor     grfFlags, grfFlags; dwFlags
0x18001cbe8  mov     [rax], ecx
0x18001cbea  mov     r12, [rbp+840h+monikerStream._pMInterfacePointer]
0x18001cbee  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001cbf5  mov     [rbp+840h+monikerStream._pMInterfacePointer], r15
0x18001cbf9  mov     [rbp+840h+monikerStream._fFree], r15d
0x18001cbfd  call    cs:__imp_HeapAlloc
0x18001cc04  nop     dword ptr [rax+rax+00h]
0x18001cc09  mov     rbx, rax
0x18001cc0c  test    rax, rax
0x18001cc0f  jz      loc_18001CC95
0x18001cc15  mov     [rax+4], r15d
0x18001cc19  call    ?GetCurrentApartmentId@@YAKXZ; GetCurrentApartmentId(void)
0x18001cc1e  or      qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x18001cc23  mov     [rbx+18h], eax
0x18001cc26  mov     [rbx+20h], r15
0x18001cc2a  mov     [rsp+940h+protitm], rbx
0x18001cc2f  test    rbx, rbx
0x18001cc32  jz      loc_18001CE94
0x18001cc38  xor     r8d, r8d; dwLine
0x18001cc3b  lea     rdx, pszFile; "Unknown File"
0x18001cc42  lea     this, ?g_RotSem@@3VCOleStaticMutexSem@@A; this
0x18001cc49  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x18001cc4e  mov     punkObject, [rsp+940h+file]
0x18001cc53  mov     r9d, 1
0x18001cc59  add     [punkObject+38h], r9w
0x18001cc5e  lea     rdi, [punkObject+10h]
0x18001cc62  movzx   eax, word ptr [punkObject+38h]
0x18001cc67  mov     [rbx], ax
0x18001cc6a  mov     rdx, [rdi]
0x18001cc6d  mov     this, [rdi+8]
0x18001cc71  cmp     rdx, this
0x18001cc74  jnz     loc_18001CEA8
0x18001cc7a  mov     rax, [rdi+8]
0x18001cc7e  cmp     rax, [rdi+10h]
0x18001cc82  jz      loc_18001CEB7
0x18001cc88  mov     [rax], rbx
0x18001cc8b  add     qword ptr [rdi+8], 8
0x18001cc90  jmp     loc_18001CEFD
0x18001cc95  mov     rbx, r15
0x18001cc98  jmp     short loc_18001CC2A
0x18001cc9a  mov     edi, 80070057h
0x18001cc9f  xor     r15d, r15d
0x18001cca2  test    rbx, rbx
0x18001cca5  jz      short loc_18001CCCF
0x18001cca7  mov     rax, [rbx+20h]
0x18001ccab  lock cmpxchg [rbx+20h], r15
0x18001ccb1  test    rax, rax
0x18001ccb4  jz      short loc_18001CCC5
0x18001ccb6  mov     this, rax
0x18001ccb9  call    cs:__imp_InternalCoUnregisterDisconnectCallback
0x18001ccc0  nop     dword ptr [rax+rax+00h]
0x18001ccc5  mov     rsi, [rsp+940h+pifdMoniker]
0x18001ccca  mov     rbx, [rsp+940h+protitm]
0x18001cccf  test    r12, r12
0x18001ccd2  jz      loc_18001CF27
0x18001ccd8  xorps   xmm0, xmm0
0x18001ccdb  lea     this, [rbp+840h+var_888]; this
0x18001ccdf  movups  xmmword ptr [rbp+840h+var_888.lpVtbl], xmm0
0x18001cce3  call    ??0CAbstractMarshalingStream@@QEAA@XZ; CAbstractMarshalingStream::CAbstractMarshalingStream(void)
0x18001cce8  and     [rbp+840h+var_878], 0
0x18001cced  lea     r13, ??_7CReadInterfaceDataFromInternalSourceMarshalingStream@@6B@; const CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable'
0x18001ccf4  mov     [rbp+840h+var_868], r12
0x18001ccf8  lea     this, [rbp+840h+var_888]; pStream
0x18001ccfc  mov     [rbp+840h+var_860], r15d
0x18001cd00  mov     eax, [r12]
0x18001cd04  mov     [rbp+840h+var_870], eax
0x18001cd07  mov     [rbp+840h+var_888.lpVtbl], r13
0x18001cd0b  call    ?ReleaseMarshalingData@@YAXPEAUIStream@@@Z; ReleaseMarshalingData(IStream *)
0x18001cd10  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18001cd17  mov     punkObject, r12; lpMem
0x18001cd1a  xor     grfFlags, grfFlags; dwFlags
0x18001cd1c  call    cs:__imp_HeapFree
0x18001cd23  nop     dword ptr [rax+rax+00h]
0x18001cd28  lea     this, [rbp+840h+var_888]; this
0x18001cd2c  call    ??1CBaseMInterfacePointerMarshalingStream@@MEAA@XZ; CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(void)
0x18001cd31  jmp     loc_18001CF2E
0x18001cd36  or      qword ptr [r13+0], 0FFFFFFFFFFFFFFFFh
0x18001cd3b  xor     r15d, r15d
0x18001cd3e  lea     this, [rsp+940h+monikerStream]; this
0x18001cd43  call    ??1CBaseMInterfacePointerMarshalingStream@@MEAA@XZ; CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(void)
0x18001cd48  test    edi, edi
0x18001cd4a  js      loc_18001CCA2
0x18001cd50  mov     this, rsi; pv
0x18001cd53  call    cs:__imp_CoTaskMemFree
0x18001cd5a  nop     dword ptr [rax+rax+00h]
0x18001cd5f  mov     this, r12; pv
0x18001cd62  call    cs:__imp_CoTaskMemFree
0x18001cd69  nop     dword ptr [rax+rax+00h]
0x18001cd6e  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18001cd75  jnz     loc_18001CFE4
0x18001cd7b  mov     eax, edi
0x18001cd7d  mov     this, [rbp+840h+var_40]
0x18001cd84  xor     this, rsp; StackCookie
0x18001cd87  call    __security_check_cookie
0x18001cd8c  mov     rbx, [rsp+940h+arg_8]
0x18001cd94  add     rsp, 910h
0x18001cd9b  pop     r15
0x18001cd9d  pop     r14
0x18001cd9f  pop     r13
0x18001cda1  pop     r12
0x18001cda3  pop     rdi
0x18001cda4  pop     rsi
0x18001cda5  pop     rbp
0x18001cda6  retn
0x18001cda8  cmp     rax, this
0x18001cdab  jnb     loc_18001CC7A
0x18001cdb1  cmp     [rdx+rax*8], r15
0x18001cdb5  jz      short loc_18001CDBC
0x18001cdb7  add     rax, pmkObjectName
0x18001cdba  jmp     short loc_18001CDA8
0x18001cdbc  mov     [rdx+rax*8], rbx
0x18001cdc0  mov     r14d, eax
0x18001cdc3  cmp     eax, 0FFFFFFFFh
0x18001cdc6  jz      loc_18001CC7A
0x18001cdcc  movzx   r15d, word ptr [punkObject+38h]
0x18001cdd1  lea     this, ?g_RotSem@@3VCOleStaticMutexSem@@A; this
0x18001cdd8  shl     r15d, 10h
0x18001cddc  or      r15d, r14d
0x18001cddf  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x18001cde4  mov     punkObject, [rsp+940h+file]
0x18001cde9  lea     rax, [rbp+840h+pvNotifyCookie]
0x18001cded  mov     this, [rbp+840h+var_898]
0x18001cdf1  add     punkObject, 8
0x18001cdf5  and     [rbp+840h+pvNotifyCookie], 0
0x18001cdfa  mov     grfFlags, r13d
0x18001cdfd  mov     r9d, r15d
0x18001ce00  mov     [rsp+940h+pvDestContext], rax
0x18001ce05  call    cs:__imp_InternalCoRegisterDisconnectCallback
0x18001ce0c  nop     dword ptr [rax+rax+00h]
0x18001ce11  mov     edi, eax
0x18001ce13  test    eax, eax
0x18001ce15  js      loc_18001CF10
0x18001ce1b  mov     rax, [rbp+840h+pvNotifyCookie]
0x18001ce1f  lea     r13, [rbx+8]
0x18001ce23  mov     [rbx+20h], rax
0x18001ce27  call    cs:__imp_CoGetCurrentProcess
0x18001ce2e  nop     dword ptr [rax+rax+00h]
0x18001ce33  mov     ecx, [rsp+940h+var_900]
0x18001ce37  lea     pmkObjectName, [rbp+840h+filetime]
0x18001ce3b  and     ecx, 2
0x18001ce3e  mov     qword ptr [rsp+940h+function], r13
0x18001ce43  mov     [rsp+940h+mshlflags], ecx
0x18001ce47  mov     punkObject, rsi
0x18001ce4a  lea     this, [rbp+840h+tmeb]
0x18001ce4e  mov     dword ptr [rsp+940h+pvDestContext], eax
0x18001ce52  mov     rdx, r12
0x18001ce55  call    cs:__imp_InternalIrotRegister
0x18001ce5c  nop     dword ptr [rax+rax+00h]
0x18001ce61  mov     edi, eax
0x18001ce63  test    eax, eax
0x18001ce65  js      loc_18001CD36
0x18001ce6b  mov     rax, [rbp+840h+var_890]
0x18001ce6f  mov     [rax], r15d
0x18001ce72  jmp     loc_18001CD3B
0x18001ce77  mov     this, [rbp+840h+pProxyManager]
0x18001ce7b  mov     rax, [this]
0x18001ce7e  mov     rax, [rax+10h]
0x18001ce82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce87  xor     r15d, r15d
0x18001ce8a  mov     edi, 80070057h
0x18001ce8f  jmp     loc_18001CD6E
0x18001ce94  lea     this, [rsp+940h+monikerStream]; this
0x18001ce99  mov     edi, 8007000Eh
0x18001ce9e  call    ??1CBaseMInterfacePointerMarshalingStream@@MEAA@XZ; CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(void)
0x18001cea3  jmp     loc_18001CCCF
0x18001cea8  sub     this, rdx
0x18001ceab  mov     rax, r15
0x18001ceae  sar     this, 3
0x18001ceb2  jmp     loc_18001CDA8
0x18001ceb7  lea     rdx, [rsp+940h+protitm]; _Val
0x18001cebc  mov     this, rdi; this
0x18001cebf  call    ??$_PushBackOne2@AEBQEAVCROTItem@@@?$vector@PEAVCROTItem@@V?$allocator@PEAVCROTItem@@@utl@@@utl@@AEAA_NAEBQEAVCROTItem@@@Z; utl::vector<CROTItem *,utl::allocator<CROTItem *>>::_PushBackOne2<CROTItem * const &>(CROTItem * const &)
0x18001cec4  test    al, al
0x18001cec6  jnz     short loc_18001CEED
0x18001cec8  lea     this, ?g_RotSem@@3VCOleStaticMutexSem@@A; this
0x18001cecf  mov     edi, 8007000Eh
0x18001ced4  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x18001ced9  lea     this, [rsp+940h+monikerStream]; this
0x18001cede  call    ??1CBaseMInterfacePointerMarshalingStream@@MEAA@XZ; CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(void)
0x18001cee3  mov     rbx, [rsp+940h+protitm]
0x18001cee8  jmp     loc_18001CCA2
0x18001ceed  mov     rbx, [rsp+940h+protitm]
0x18001cef2  mov     r9d, 1
0x18001cef8  mov     punkObject, [rsp+940h+file]
0x18001cefd  mov     r14, [rdi+8]
0x18001cf01  sub     r14, [rdi]
0x18001cf04  sar     r14, 3
0x18001cf08  sub     r14d, r9d
0x18001cf0b  jmp     loc_18001CDCC
0x18001cf10  lea     this, [rsp+940h+monikerStream]; this
0x18001cf15  call    ??1CBaseMInterfacePointerMarshalingStream@@MEAA@XZ; CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(void)
0x18001cf1a  jmp     loc_18001CC9F
0x18001cf1f  mov     rsi, [rsp+940h+pifdMoniker]
0x18001cf24  xor     r15d, r15d
0x18001cf27  lea     r13, ??_7CReadInterfaceDataFromInternalSourceMarshalingStream@@6B@; const CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable'
0x18001cf2e  test    rsi, rsi
0x18001cf31  jz      short loc_18001CF96
0x18001cf33  xorps   xmm0, xmm0
0x18001cf36  lea     this, [rsp+940h+monikerStream]; this
0x18001cf3b  movups  xmmword ptr [rsp+940h+monikerStream.lpVtbl], xmm0
0x18001cf40  call    ??0CAbstractMarshalingStream@@QEAA@XZ; CAbstractMarshalingStream::CAbstractMarshalingStream(void)
0x18001cf45  and     qword ptr [rsp+940h+monikerStream._lOffset], 0
0x18001cf4b  lea     this, ??_7CBaseMInterfacePointerMarshalingStream@@6B@; const CBaseMInterfacePointerMarshalingStream::`vftable'
  ... truncated ...
```
