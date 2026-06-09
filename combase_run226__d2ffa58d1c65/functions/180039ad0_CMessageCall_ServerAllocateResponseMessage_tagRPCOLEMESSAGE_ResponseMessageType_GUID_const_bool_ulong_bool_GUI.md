# CMessageCall::ServerAllocateResponseMessage(tagRPCOLEMESSAGE *,ResponseMessageType,_GUID const &,bool,ulong,bool,_GUID const *)

- ea: `0x180039ad0`
- end: `0x18003a621`
- name: `?ServerAllocateResponseMessage@CMessageCall@@QEAAJPEAUtagRPCOLEMESSAGE@@W4ResponseMessageType@@AEBU_GUID@@_NK3PEBU4@@Z`
- size: `2897`
- prototype: `__int64 __fastcall(CMessageCall *this, tagRPCOLEMESSAGE *pMessage, ResponseMessageType responseMessageType, const _GUID *moidForTracing, bool isWinrtAsyncCall, unsigned int winrtAsyncResponseBlockSize, bool bForceNoExtensions, _GUID *pSingleEnabledExtensionId)`
- caller_count: `3`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b8d0`
- `0x180038090`
- `0x1800c21c4`

## callees

- `0x18000712c`
- `0x18000833c`
- `0x18000b408`
- `0x180010250`
- `0x1800188a0`
- `0x18001bbc0`
- `0x180039ad0`
- `0x18003a8bc`
- `0x1800a09a0`
- `0x180106f00`
- `0x180107214`
- `0x180107320`
- `0x18010fde8`
- `0x180179024`
- `0x18017a264`
- `0x180182e0c`
- `0x1801860c4`
- `0x1802135dd`
- `0x1802135e9`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a245`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a262`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a262`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a22c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a22c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039d84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039f3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a25a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a2d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a2f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a30b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a48e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039d84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039f3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a25a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a2d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a2f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a30b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a48e`

## string_xrefs

- `0x180039ca4`: `onecore\com\combase\callheaders\localcallheaders.cpp`
- `0x180039ebf`: `onecore\com\combase\callheaders\localcallheaders.cpp`
- `0x180039f99`: `onecore\com\combase\callheaders\localcallheaders.cpp`
- `0x18003a4b6`: `onecore\com\combase\callheaders\localcallheaders.cpp`
- `0x18003a4d2`: `onecore\com\combase\callheaders\localcallheaders.cpp`
- `0x18003a4f1`: `onecore\com\combase\callheaders\localcallheaders.cpp`
- `0x18003a5df`: `onecore\com\combase\callheaders\localcallheaders.cpp`
- `0x18003a601`: `onecore\com\combase\callheaders\localcallheaders.cpp`
- `0x18003a0cd`: `onecore\com\combase\callheaders\containercallheaders.cpp`
- `0x18003a185`: `onecore\com\combase\callheaders\containercallheaders.cpp`
- `0x18003a1b2`: `onecore\com\combase\callheaders\containercallheaders.cpp`
- `0x18003a1c8`: `onecore\com\combase\callheaders\containercallheaders.cpp`
- `0x18003a1de`: `onecore\com\combase\callheaders\containercallheaders.cpp`
- `0x18003a1f4`: `onecore\com\combase\callheaders\containercallheaders.cpp`
- `0x18003a51d`: `onecore\com\combase\callheaders\containercallheaders.cpp`
- `0x18003a585`: `onecore\com\combase\callheaders\containercallheaders.cpp`
- `0x180246a2f`: `onecore\com\combase\callheaders\containercallheaders.cpp`
- `0x180039cd9`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x180039d02`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x180039d5b`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x18003a0f9`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x18003a3fd`: `onecore\com\combase\dcomrem\channelb.cxx`
- `0x18003a29b`: `onecore\com\combase\dcomrem\call.cxx`

## pseudocode

```c
__int64 __fastcall CMessageCall::ServerAllocateResponseMessage(
        CMessageCall *this,
        tagRPCOLEMESSAGE *pMessage,
        ResponseMessageType responseMessageType,
        const _GUID *moidForTracing,
        bool isWinrtAsyncCall,
        unsigned int winrtAsyncResponseBlockSize,
        bool bForceNoExtensions,
        _GUID *pSingleEnabledExtensionId)
{
  tagRPCOLEMESSAGE *v8; // r14
  tagSOleTlsData *ReservedForOle; // rbx
  unsigned int responseContainerPassthroughDataSize; // eax
  WireContainerThat *responseContainerPassthroughData; // rdi
  CDestObject_vtbl *v13; // rax
  unsigned int v14; // r12d
  unsigned int v15; // r13d
  unsigned int (__fastcall *GetDestCtx)(IDestInfo *); // rax
  const SHookList *pNext; // rbx
  int v18; // r15d
  const _GUID *v19; // rdi
  unsigned int *v20; // rbx
  unsigned int v21; // ecx
  unsigned int v22; // eax
  HRESULT v23; // r14d
  unsigned int v24; // edx
  unsigned int *v25; // rax
  unsigned int *v26; // r8
  unsigned int sizeOfOrpcThat; // ecx
  unsigned int v28; // r15d
  unsigned int v29; // edx
  unsigned int v31; // eax
  __int64 v32; // rcx
  bool v33; // zf
  HRESULT v34; // ebx
  void **p_Buffer; // rbx
  unsigned int v36; // eax
  __int64 v37; // rcx
  char *v38; // rbx
  ResponseMessageType v39; // edx
  BOOL v40; // ecx
  const WireLocalThat **v41; // r14
  const WireLocalThat *v42; // r15
  const WireLocalThat *v43; // rax
  const WireLocalThat *v44; // rbx
  const WireLocalThat *v45; // rax
  unsigned int sizeOfLocalThat; // r12d
  unsigned int v47; // r13d
  void *v48; // r13
  unsigned int v49; // ecx
  unsigned __int64 preGetBufferOutOfProcMarshalingSetId; // rax
  unsigned int v51; // r15d
  __int64 sizeOfContainerThat; // rax
  unsigned __int64 v53; // r12
  const WireContainerThat *v54; // rdx
  WireContainerExtent *v55; // r10
  unsigned int v56; // eax
  unsigned int v57; // r8d
  WireContainerExtent *v58; // r9
  HRESULT v59; // eax
  HRESULT v60; // eax
  unsigned int v61; // ebx
  unsigned int pData; // eax
  unsigned int v63; // r8d
  WireContainerExtent *value; // r9
  unsigned int v65; // ecx
  unsigned int v66; // edx
  void *v67; // r14
  DWORD LastError; // ebx
  unsigned int v69; // edx
  void *v70; // rdx
  unsigned int v71; // ecx
  __int32 v72; // edx
  __int32 v73; // edx
  int v74; // ecx
  IUnknown *punkError; // rbx
  HRESULT v76; // eax
  IErrorInfo *ptr; // rcx
  unsigned int v78; // ecx
  HRESULT ContainerExtent; // eax
  unsigned int v80; // ecx
  const void *v81; // rdx
  size_t pData_low; // r8
  _GUID *v83; // [rsp+28h] [rbp-41h]
  Microsoft::WRL::ComPtr<IErrorInfo> errorInfo; // [rsp+30h] [rbp-39h] BYREF
  unsigned int cbBuffer; // [rsp+38h] [rbp-31h]
  LPVOID Src; // [rsp+40h] [rbp-29h]
  wistd::unique_ptr<WireContainerExtent,wil::function_deleter<void (__cdecl*)(void *),&MIDL_user_free> > containerErrorInformation; // [rsp+48h] [rbp-21h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-19h]
  void *retaddr; // [rsp+A8h] [rbp+3Fh]
  COleTls tls; // [rsp+B0h] [rbp+47h] BYREF
  tagRPCOLEMESSAGE *v91; // [rsp+B8h] [rbp+4Fh]
  ResponseMessageType v92; // [rsp+C0h] [rbp+57h]
  const _GUID *v93; // [rsp+C8h] [rbp+5Fh]

  v93 = moidForTracing;
  v92 = responseMessageType;
  v91 = pMessage;
  v8 = pMessage;
  if ( (this->gap8[12] & 0x24) == 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  ReservedForOle = (tagSOleTlsData *)NtCurrentTeb()->ReservedForOle;
  tls._pData = ReservedForOle;
  if ( !ReservedForOle )
  {
    v60 = COleTls::TLSAllocData(&tls);
    v61 = v60;
    if ( v60 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0xEFAu, "onecore\\com\\combase\\dcomrem\\channelb.cxx", v60);
      return v61;
    }
    ReservedForOle = tls._pData;
  }
  this->message.iMethod |= 0x8000u;
  cbBuffer = v8->cbBuffer;
  responseContainerPassthroughDataSize = ReservedForOle->responseContainerPassthroughDataSize;
  responseContainerPassthroughData = ReservedForOle->responseContainerPassthroughData;
  ReservedForOle->responseContainerPassthroughData = 0;
  ReservedForOle->responseContainerPassthroughDataSize = 0;
  LODWORD(tls._pData) = responseContainerPassthroughDataSize;
  v13 = this->_destObj.__vftable;
  v14 = 0;
  v15 = 0;
  Src = 0;
  GetDestCtx = v13->GetDestCtx;
  containerErrorInformation.__ptr_.__value_ = 0;
  lpMem = responseContainerPassthroughData;
  if ( GetDestCtx(&this->_destObj) == 5 || this->_useContainerErrorInformationLocalPropagation )
  {
    punkError = ReservedForOle->punkError;
    if ( punkError )
    {
      punkError->AddRef(punkError);
      errorInfo.ptr_ = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&errorInfo);
      if ( CarefullyQueryNewInterface(punkError, &GUID_1cf2b120_547d_101b_8e65_08002b2bd119, (void **)&errorInfo.ptr_) >= 0 )
      {
        v76 = GenerateContainerErrorInformationAsContainerExtent(errorInfo.ptr_, &containerErrorInformation);
        if ( v76 < 0 )
          wil::details::in1diag3::_Log_Hr(retaddr, 0xF26u, "onecore\\com\\combase\\dcomrem\\channelb.cxx", v76);
        Src = containerErrorInformation.__ptr_.__value_;
      }
    }
    else
    {
      errorInfo.ptr_ = 0;
    }
    TlsClearErrorInfo();
    ptr = errorInfo.ptr_;
    if ( errorInfo.ptr_ )
    {
      errorInfo.ptr_ = 0;
      ptr->Release(ptr);
    }
    if ( punkError )
      punkError->Release(punkError);
  }
  if ( this->_destObj.GetDestCtx(&this->_destObj) == 5 )
  {
    pData = (unsigned int)tls._pData;
    this->_sizeOfContainerThat = 0;
    v63 = 0;
    LODWORD(errorInfo.ptr_) = 0;
    value = 0;
    containerErrorInformation.__ptr_.__value_ = 0;
    if ( pData > 0xD0 )
    {
      if ( pData < 0xE0 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          0x8BAu,
          "onecore\\com\\combase\\callheaders\\containercallheaders.cpp");
      if ( !responseContainerPassthroughData->part1.unique )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          0x8BBu,
          "onecore\\com\\combase\\callheaders\\containercallheaders.cpp");
      ContainerExtent = GetContainerExtentArray<WireContainerThat>(
                          pData,
                          responseContainerPassthroughData,
                          (unsigned int *)&errorInfo,
                          (const WireContainerExtentArray **)&containerErrorInformation);
      if ( ContainerExtent < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          0x8BDu,
          "onecore\\com\\combase\\callheaders\\containercallheaders.cpp",
          ContainerExtent);
      v63 = (unsigned int)errorInfo.ptr_;
      value = containerErrorInformation.__ptr_.__value_;
    }
    v20 = (unsigned int *)Src;
    v65 = 0;
    containerErrorInformation.__ptr_.__value_ = 0;
    if ( Src )
    {
      containerErrorInformation.__ptr_.__value_ = (WireContainerExtent *)Src;
      v65 = 1;
    }
    LODWORD(errorInfo.ptr_) = 0;
    v23 = CalculateSizeForMergedContainerExtentArray(
            v65,
            (const WireContainerExtent **)&containerErrorInformation.__ptr_.__value_,
            v63,
            (const WireContainerExtentArray *)value,
            (unsigned int *)&errorInfo,
            0);
    if ( v23 >= 0 )
    {
      v28 = LODWORD(errorInfo.ptr_) + 208;
      if ( LODWORD(errorInfo.ptr_) < 0xFFFFFF30 )
      {
        this->_sizeOfContainerThat = v28;
        v8 = v91;
        goto LABEL_35;
      }
      this->_sizeOfContainerThat = -1;
      v23 = -2147024362;
      v66 = 2254;
    }
    else
    {
      v66 = 2252;
    }
    wil::details::in1diag3::Return_Hr(retaddr, v66, "onecore\\com\\combase\\callheaders\\containercallheaders.cpp", v23);
    v29 = 3917;
LABEL_31:
    wil::details::in1diag3::Return_Hr(retaddr, v29, "onecore\\com\\combase\\dcomrem\\channelb.cxx", v23);
    if ( v20 )
    {
      v26 = v20;
      goto LABEL_100;
    }
    goto LABEL_32;
  }
  if ( !bForceNoExtensions )
  {
    pNext = gHookList.pNext;
    v18 = 16;
    LODWORD(errorInfo.ptr_) = 0;
    if ( gHookList.pNext != &gHookList )
    {
      v19 = pSingleEnabledExtensionId;
      do
      {
        if ( !v19 || !memcmp_0(&pNext->uExtension, v19, 0x10u) )
        {
          pNext->pHook->ServerGetSize(pNext->pHook, &pNext->uExtension, &this->_iidWire, 0, (unsigned int *)&errorInfo);
          if ( LODWORD(errorInfo.ptr_) )
          {
            v18 += ((LODWORD(errorInfo.ptr_) + 7) & 0xFFFFFFF8) + 24;
            LODWORD(errorInfo.ptr_) = ((LODWORD(errorInfo.ptr_) + 7) & 0xFFFFFFF8) + 24;
            ++v14;
          }
        }
        pNext = pNext->pNext;
      }
      while ( pNext != &gHookList );
      responseContainerPassthroughData = (WireContainerThat *)lpMem;
      v8 = v91;
    }
    v14 = (v14 + 1) & 0xFFFFFFFE;
    if ( v14 )
      v15 = v18 + 4 * v14;
    else
      v15 = 0;
  }
  if ( v15 >= 0xFFFFFFF8 )
  {
    v23 = -2147024362;
    this->_sizeOfOrpcThat = -1;
    wil::details::in1diag3::Return_Hr(retaddr, 0xF3Cu, "onecore\\com\\combase\\dcomrem\\channelb.cxx", -2147024362);
    v25 = (unsigned int *)Src;
    if ( !Src )
      goto LABEL_32;
    goto LABEL_25;
  }
  v20 = (unsigned int *)Src;
  this->_sizeOfOrpcThat = v15 + 8;
  if ( this->_destObj._dwDestCtx != 2 )
  {
    if ( v20 )
      v21 = RoundUpToPowerOfTwo<unsigned int,unsigned long>(v20[3], 8u) + 16;
    else
      v21 = 0;
    v22 = winrtAsyncResponseBlockSize + 24;
    this->_sizeOfLocalThat = 0;
    if ( v22 < 0x18 )
    {
      v23 = -2147024362;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0xEFu,
        "onecore\\com\\combase\\callheaders\\localcallheaders.cpp",
        -2147024362);
      v24 = 251;
      goto LABEL_24;
    }
    v78 = v22 + v21;
    if ( v78 < v22 )
    {
      v24 = 257;
      v23 = -2147024362;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        v24,
        "onecore\\com\\combase\\callheaders\\localcallheaders.cpp",
        -2147024362);
      wil::details::in1diag3::Return_Hr(retaddr, 0xF44u, "onecore\\com\\combase\\dcomrem\\channelb.cxx", -2147024362);
      v25 = (unsigned int *)Src;
      if ( Src )
      {
LABEL_25:
        v26 = v25;
LABEL_100:
        HeapFree(g_hHeap, 0, v26);
      }
LABEL_32:
      if ( responseContainerPassthroughData )
        HeapFree(g_hHeap, 0, responseContainerPassthroughData);
      return (unsigned int)v23;
    }
    if ( v78 + LODWORD(tls._pData) < v78 )
    {
      this->_sizeOfLocalThat = -1;
      v24 = 260;
      v23 = -2147024362;
      goto LABEL_24;
    }
    this->_sizeOfLocalThat = v78 + LODWORD(tls._pData);
  }
  sizeOfOrpcThat = this->_sizeOfOrpcThat;
  v28 = sizeOfOrpcThat + this->_sizeOfLocalThat;
  if ( v28 < sizeOfOrpcThat )
  {
    v23 = -2147024362;
    v29 = 3911;
    goto LABEL_31;
  }
LABEL_35:
  v31 = v8->cbBuffer;
  v32 = v31 + v28;
  if ( (unsigned int)v32 < v31 )
  {
    v23 = -2147024362;
    v29 = 3922;
    goto LABEL_31;
  }
  v33 = (this->gap8[12] & 0x20) == 0;
  this->message.cbBuffer = v32;
  if ( v33 )
  {
    v34 = this->OutofprocServerAllocateResponseBuffer(this, v93);
    if ( v34 >= 0 )
    {
      p_Buffer = &this->message.Buffer;
      goto LABEL_39;
    }
    v69 = 4148;
  }
  else
  {
    this->message.dataRepresentation = 16;
    if ( (unsigned int)v32 > (unsigned __int64)(v32 + 7) )
      v67 = 0;
    else
      v67 = HeapAlloc(g_hHeap, 0, (v32 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
    lpMem = this->_processLocalResponseBuffer.m_ptr;
    if ( lpMem )
    {
      LastError = GetLastError();
      HeapFree(g_hHeap, 0, lpMem);
      SetLastError(LastError);
    }
    this->_processLocalResponseBuffer.m_ptr = v67;
    p_Buffer = &this->message.Buffer;
    this->message.Buffer = v67;
    v33 = v67 == 0;
    v8 = v91;
    if ( !v33 )
    {
LABEL_39:
      v8->cbBuffer = cbBuffer;
      this->_responseMessageType = v92;
      v36 = this->_destObj.GetDestCtx(&this->_destObj);
      v38 = (char *)*p_Buffer;
      if ( v36 != 5 )
      {
        v39 = v92;
        v33 = this->_destObj._dwDestCtx == 2;
        this->_orpcThat = (const WireThat *)v38;
        v40 = !v33;
        *(_DWORD *)v38 = v40;
        if ( v39 == Normal )
          goto LABEL_41;
        v72 = v39 - 1;
        if ( v72 )
        {
          v73 = v72 - 1;
          if ( !v73 )
          {
            *(_DWORD *)v38 = v40 | 4;
LABEL_41:
            v41 = (const WireLocalThat **)&v8->Buffer;
            v42 = (const WireLocalThat *)(v38 + 8);
            if ( v15 )
            {
              v83 = pSingleEnabledExtensionId;
              *((_DWORD *)v38 + 1) = 2003069011;
              v43 = (const WireLocalThat *)FillBuffer((WireExtentArray *)(v38 + 8), v15, v14, 0, this, v83);
              *v41 = v43;
              if ( v43 != v42 )
                goto LABEL_45;
            }
            else
            {
              *v41 = v42;
            }
            *((_DWORD *)v38 + 1) = 0;
LABEL_45:
            this->_sizeOfOrpcThat = *(_DWORD *)v41 - (_DWORD)v38;
            if ( this->_destObj._dwDestCtx != 2 )
            {
              v44 = *v41;
              v45 = (const WireLocalThat *)((char *)*v41 + this->_sizeOfLocalThat);
              this->_localThat = *v41;
              *v41 = v45;
              this->_pointerToServerMarshalingSetId = &v44->part1.marshalingSetId;
              if ( isWinrtAsyncCall )
                this->_serverWinrtAsyncResponseBlock = &v44->asyncResponseBlock;
              sizeOfLocalThat = this->_sizeOfLocalThat;
              if ( sizeOfLocalThat < 0x18 )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  0x10Fu,
                  "onecore\\com\\combase\\callheaders\\localcallheaders.cpp");
              v49 = winrtAsyncResponseBlockSize;
              preGetBufferOutOfProcMarshalingSetId = this->_preGetBufferOutOfProcMarshalingSetId;
              v44->part1.reserved = 0;
              v51 = v49 + 24;
              if ( v49 >= 0xFFFFFFE8 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  0xEFu,
                  "onecore\\com\\combase\\callheaders\\localcallheaders.cpp",
                  -2147024362);
                wil::details::in1diag3::FailFast_Hr(
                  retaddr,
                  0x115u,
                  "onecore\\com\\combase\\callheaders\\localcallheaders.cpp",
                  -2147024362);
              }
              if ( sizeOfLocalThat < v51 )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  0x116u,
                  "onecore\\com\\combase\\callheaders\\localcallheaders.cpp");
              v44->part1.marshalingSetId = preGetBufferOutOfProcMarshalingSetId;
              v44->part1.unique_pAsyncResponseBlock = v49 != 0;
              if ( Src )
              {
                v80 = RoundUpToPowerOfTwo<unsigned int,unsigned long>(*((_DWORD *)Src + 3), 8u) + 16;
                if ( sizeOfLocalThat - v51 < v80 )
                  wil::details::in1diag3::_FailFast_Unexpected(
                    retaddr,
                    0x121u,
                    "onecore\\com\\combase\\callheaders\\localcallheaders.cpp");
                v81 = Src;
                v47 = v80 + v51;
                v44->part1.unique_containerErrorInformation = 1;
                memcpy_0((char *)v44 + v51, v81, v80);
              }
              else
              {
                v47 = v49 + 24;
                v44->part1.unique_containerErrorInformation = 0;
              }
              if ( LODWORD(tls._pData) )
              {
                if ( sizeOfLocalThat - v47 < LODWORD(tls._pData) )
                  wil::details::in1diag3::_FailFast_Unexpected(
                    retaddr,
                    0x131u,
                    "onecore\\com\\combase\\callheaders\\localcallheaders.cpp");
                pData_low = LODWORD(tls._pData);
                v44->part1.unique_containerPassthroughData = 1;
                memcpy_0((char *)v44 + v47, responseContainerPassthroughData, pData_low);
              }
              else
              {
                v44->part1.unique_containerPassthroughData = 0;
              }
            }
            v48 = Src;
            goto LABEL_55;
          }
          if ( v73 != 1 )
            goto LABEL_41;
          v74 = v40 | 0x10;
        }
        else
        {
          v74 = v40 | 2;
        }
        *(_DWORD *)v38 = v74;
        goto LABEL_41;
      }
      sizeOfContainerThat = this->_sizeOfContainerThat;
      v41 = (const WireLocalThat **)&v8->Buffer;
      this->_containerThat = (const WireContainerThat *)v38;
      *v41 = (const WireLocalThat *)&v38[sizeOfContainerThat];
      v53 = this->_preGetBufferOutOfProcMarshalingSetId;
      this->_pointerToServerMarshalingSetId = (unsigned __int64 *)(v38 + 168);
      if ( this->_destObj._dwDestCtx != 5 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v37);
      if ( v28 < 0xD0 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          0x8F9u,
          "onecore\\com\\combase\\callheaders\\containercallheaders.cpp");
      *(_QWORD *)v38 = 0;
      if ( this->_destObj._containerVersion.version < 3 )
      {
        if ( v53 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            0x904u,
            "onecore\\com\\combase\\callheaders\\containercallheaders.cpp");
        v53 = 0;
      }
      *((_QWORD *)v38 + 21) = v53;
      SetReservedAndPassthroughTopLevelFieldsInContainerThat<WireContainerThatPart1>(
        (WireContainerThatPart1 *)v38,
        &responseContainerPassthroughData->part1);
      v56 = (unsigned int)tls._pData;
      v57 = (unsigned int)v55;
      LODWORD(errorInfo.ptr_) = (_DWORD)v55;
      v58 = v55;
      containerErrorInformation.__ptr_.__value_ = v55;
      *(GUID *)(v38 + 72) = GUID_NULL;
      *(GUID *)(v38 + 88) = GUID_NULL;
      *(GUID *)(v38 + 104) = GUID_NULL;
      *((_QWORD *)v38 + 22) = v55;
      *((_QWORD *)v38 + 23) = v55;
      *((_QWORD *)v38 + 24) = v55;
      *((_QWORD *)v38 + 25) = v55;
      *(GUID *)(v38 + 120) = GUID_NULL;
      if ( v56 > 0xD0 )
      {
        if ( v56 < 0xE0 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            0x916u,
            "onecore\\com\\combase\\callheaders\\containercallheaders.cpp");
        if ( responseContainerPassthroughData->part1.unique == (_DWORD)v55 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            0x917u,
            "onecore\\com\\combase\\callheaders\\containercallheaders.cpp");
        v59 = GetContainerExtentArray<WireContainerThat>(
                v56,
                v54,
                (unsigned int *)&errorInfo,
                (const WireContainerExtentArray **)&containerErrorInformation);
        if ( v59 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            0x919u,
            "onecore\\com\\combase\\callheaders\\containercallheaders.cpp",
            v59);
        v57 = (unsigned int)errorInfo.ptr_;
        v55 = 0;
        v58 = containerErrorInformation.__ptr_.__value_;
      }
      v48 = Src;
      tls._pData = (tagSOleTlsData *)v55;
      if ( Src )
      {
        tls._pData = (tagSOleTlsData *)Src;
        v71 = 1;
      }
      else
      {
        v71 = (unsigned int)v55;
        if ( !v58 )
        {
LABEL_55:
          this->_responseStubData = *v41;
          this->_sizeOfResponseStubData = v91->cbBuffer;
          this->_serverResponseStubData = (void *)*v41;
          if ( v48 )
            HeapFree(g_hHeap, 0, v48);
          if ( responseContainerPassthroughData )
            HeapFree(g_hHeap, 0, responseContainerPassthroughData);
          return 0;
        }
      }
      *((_DWORD *)v38 + 51) = 1;
      WriteMergedContainerExtentArray(
        v71,
        (const WireContainerExtent **)&tls,
        v57,
        (const WireContainerExtentArray *)v58,
        v28 - 208,
        (WireContainerExtentArray *)v38 + 13);
      goto LABEL_55;
    }
    v34 = -2147024882;
    v69 = 4144;
  }
  wil::details::in1diag3::Return_Hr(retaddr, v69, "onecore\\com\\combase\\dcomrem\\call.cxx", v34);
  v70 = Src;
  v8->cbBuffer = 0;
  v8->Buffer = 0;
  if ( v70 )
    HeapFree(g_hHeap, 0, v70);
  if ( responseContainerPassthroughData )
    HeapFree(g_hHeap, 0, responseContainerPassthroughData);
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x180039ad0  mov     [rsp-8+arg_18], moidForTracing
0x180039ad5  mov     [rsp-8+arg_10], responseMessageType
0x180039ada  mov     [rsp-8+arg_8], pMessage
0x180039adf  push    rbp
0x180039ae0  push    rbx
0x180039ae1  push    rsi
0x180039ae2  push    r14
0x180039ae4  lea     rbp, [rsp-1Fh]
0x180039ae9  sub     rsp, 88h
0x180039af0  test    byte ptr [this+14h], 24h
0x180039af4  mov     r14, pMessage
0x180039af7  mov     rsi, this
0x180039afa  jz      loc_18003A39B
0x180039b00  mov     rbx, gs:30h
0x180039b09  mov     rbx, [rbx+1758h]
0x180039b10  mov     [rbp+37h+tls._pData], rbx
0x180039b14  test    rbx, rbx
0x180039b17  jz      loc_18003A0E2
0x180039b1d  or      dword ptr [rsi+0ACh], 8000h
0x180039b27  xor     ecx, ecx
0x180039b29  mov     eax, [r14+18h]
0x180039b2d  mov     [rbp+37h+var_68], eax
0x180039b30  mov     eax, [rbx+238h]
0x180039b36  mov     [rsp+0A0h+var_20], rdi
0x180039b3e  mov     rdi, [rbx+230h]
0x180039b45  mov     [rbx+230h], this
0x180039b4c  mov     [rbx+238h], ecx
0x180039b52  mov     dword ptr [rbp+37h+tls._pData], eax
0x180039b55  mov     rax, [rsi+38h]
0x180039b59  mov     [rsp+0A0h+var_28], r12
0x180039b5e  mov     r12d, ecx
0x180039b61  mov     [rsp+0A0h+var_30], r13
0x180039b66  mov     r13d, ecx
0x180039b69  mov     [rbp+37h+Src], this
0x180039b6d  mov     rax, [rax+30h]
0x180039b71  mov     [rbp+37h+containerErrorInformation.__ptr_.__value_], this
0x180039b75  lea     this, [rsi+38h]
0x180039b79  mov     [rsp+0A0h+var_38], r15
0x180039b7e  mov     [rbp+37h+lpMem], rdi
0x180039b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b87  cmp     eax, 5
0x180039b8a  jz      loc_18003A3A5
0x180039b90  cmp     [rsi+1ACh], r12b
0x180039b97  jnz     loc_18003A3A5
0x180039b9d  mov     rax, [rsi+38h]
0x180039ba1  lea     this, [rsi+38h]
0x180039ba5  mov     rax, [rax+30h]
0x180039ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039bae  cmp     eax, 5
0x180039bb1  jz      loc_18003A11C
0x180039bb7  cmp     [rbp+37h+arg_30], r12b
0x180039bbb  jnz     loc_180039C5B
0x180039bc1  mov     rbx, cs:?gHookList@@3USHookList@@A.pNext; SHookList gHookList ...
0x180039bc8  lea     r13, ?gHookList@@3USHookList@@A; SHookList gHookList
0x180039bcf  nop
0x180039bd0  mov     r15d, 10h
0x180039bd6  mov     dword ptr [rbp+37h+errorInfo.ptr_], r12d
0x180039bda  cmp     rbx, r13
0x180039bdd  jz      short loc_180039C4B
0x180039bdf  mov     rdi, [rbp+37h+Buf2]
0x180039be3  test    rdi, rdi
0x180039be6  jz      short loc_180039BFE
0x180039be8  mov     responseMessageType, 10h; Size
0x180039bee  lea     this, [rbx+10h]; Buf1
0x180039bf2  mov     pMessage, rdi; Buf2
0x180039bf5  call    memcmp_0
0x180039bfa  test    eax, eax
0x180039bfc  jnz     short loc_180039C3B
0x180039bfe  mov     this, [rbx+8]
0x180039c02  lea     pMessage, [rbp+37h+errorInfo]
0x180039c06  mov     [rsp+0A0h+pCall], pMessage
0x180039c0b  lea     r8, [rsi+78h]
0x180039c0f  xor     r9d, r9d
0x180039c12  lea     pMessage, [rbx+10h]
0x180039c16  mov     rax, [this]
0x180039c19  mov     rax, [rax+38h]
0x180039c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c22  mov     eax, dword ptr [rbp+37h+errorInfo.ptr_]
0x180039c25  test    eax, eax
0x180039c27  jz      short loc_180039C3B
0x180039c29  add     eax, 7
0x180039c2c  and     eax, 0FFFFFFF8h
0x180039c2f  add     eax, 18h
0x180039c32  add     r15d, eax
0x180039c35  mov     dword ptr [rbp+37h+errorInfo.ptr_], eax
0x180039c38  inc     r12d
0x180039c3b  mov     rbx, [rbx]
0x180039c3e  cmp     rbx, r13
0x180039c41  jnz     short loc_180039BE3
0x180039c43  mov     rdi, [rbp+37h+lpMem]
0x180039c47  mov     r14, [rbp+37h+arg_8]
0x180039c4b  inc     r12d
0x180039c4e  and     r12d, 0FFFFFFFEh
0x180039c52  jnz     loc_18003A36D
0x180039c58  xor     r13d, r13d
0x180039c5b  lea     eax, [r13+8]
0x180039c5f  cmp     eax, 8
0x180039c62  jb      loc_180039CFE
0x180039c68  mov     rbx, [rbp+37h+Src]
0x180039c6c  mov     [rsi+230h], eax
0x180039c72  cmp     dword ptr [rsi+40h], 2
0x180039c76  jz      loc_180039D37
0x180039c7c  test    rbx, rbx
0x180039c7f  jnz     loc_18003A466
0x180039c85  xor     ecx, ecx
0x180039c87  mov     eax, [rbp+37h+arg_28]
0x180039c8a  add     eax, 18h
0x180039c8d  mov     dword ptr [rsi+240h], 0
0x180039c97  cmp     eax, 18h
0x180039c9a  jnb     loc_18003A499
0x180039ca0  mov     this, [rbp+3Fh]; callerReturnAddress
0x180039ca4  lea     rbx, aOnecoreComComb_118; "onecore\\com\\combase\\callheaders\\loc"...
0x180039cab  mov     r14d, 80070216h
0x180039cb1  mov     r8, rbx; fileName
0x180039cb4  mov     r9d, r14d; hr
0x180039cb7  mov     edx, 0EFh; lineNumber
0x180039cbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039cc1  mov     edx, 0FBh; lineNumber
0x180039cc6  mov     this, [rbp+3Fh]; callerReturnAddress
0x180039cca  mov     r9d, r14d; hr
0x180039ccd  mov     r8, rbx; fileName
0x180039cd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039cd5  mov     this, [rbp+3Fh]; callerReturnAddress
0x180039cd9  lea     r8, file; "onecore\\com\\combase\\dcomrem\\channel"...
0x180039ce0  mov     r9d, r14d; hr
0x180039ce3  mov     edx, 0F44h; lineNumber
0x180039ce8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ced  mov     rax, [rbp+37h+Src]
0x180039cf1  test    rax, rax
0x180039cf4  jz      short loc_180039D73
0x180039cf6  mov     r8, rax
0x180039cf9  jmp     loc_18003A302
0x180039cfe  mov     this, [rbp+3Fh]; callerReturnAddress
0x180039d02  lea     r8, file; "onecore\\com\\combase\\dcomrem\\channel"...
0x180039d09  mov     r14d, 80070216h
0x180039d0f  mov     dword ptr [rsi+230h], 0FFFFFFFFh
0x180039d19  mov     r9d, r14d; hr
0x180039d1c  mov     edx, 0F3Ch; lineNumber
0x180039d21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d26  mov     rax, [rbp+37h+Src]
0x180039d2a  test    rax, rax
0x180039d2d  jnz     short loc_180039CF6
0x180039d2f  jmp     short loc_180039D73
0x180039d31  mov     [rsi+240h], eax
0x180039d37  mov     ecx, [rsi+230h]
0x180039d3d  mov     r15d, [rsi+240h]
0x180039d44  add     r15d, ecx
0x180039d47  cmp     r15d, ecx
0x180039d4a  jnb     short loc_180039D92
0x180039d4c  mov     r14d, 80070216h
0x180039d52  mov     edx, 0F47h; lineNumber
0x180039d57  mov     this, [rbp+3Fh]; callerReturnAddress
0x180039d5b  lea     r8, file; "onecore\\com\\combase\\dcomrem\\channel"...
0x180039d62  mov     r9d, r14d; hr
0x180039d65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d6a  test    rbx, rbx
0x180039d6d  jnz     loc_18003A2FF
0x180039d73  test    rdi, rdi
0x180039d76  jz      short loc_180039D8A
0x180039d78  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180039d7f  mov     r8, rdi; lpMem
0x180039d82  xor     edx, edx; dwFlags
0x180039d84  call    cs:__imp_HeapFree
0x180039d8a  mov     eax, r14d
0x180039d8d  jmp     loc_180039F46
0x180039d92  mov     eax, [r14+18h]
0x180039d96  lea     ecx, [rax+r15]
0x180039d9a  cmp     ecx, eax
0x180039d9c  jb      loc_180039F6A
0x180039da2  test    byte ptr [rsi+14h], 20h
0x180039da6  mov     [rsi+0A8h], ecx
0x180039dac  jnz     loc_18003A206
0x180039db2  mov     rax, [rsi]
0x180039db5  mov     this, rsi
0x180039db8  mov     pMessage, [rbp+37h+arg_18]
0x180039dbc  mov     rax, [rax+0B8h]
0x180039dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039dc8  mov     ebx, eax
0x180039dca  test    eax, eax
0x180039dcc  js      loc_18003A292
0x180039dd2  lea     rbx, [rsi+0A0h]
0x180039dd9  mov     eax, [rbp+37h+var_68]
0x180039ddc  lea     this, [rsi+38h]
0x180039de0  mov     [r14+18h], eax
0x180039de4  mov     eax, [rbp+37h+arg_10]
0x180039de7  mov     [rsi+1B0h], eax
0x180039ded  mov     rax, [this]
0x180039df0  mov     rax, [rax+30h]
0x180039df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039df9  mov     rbx, [rbx]
0x180039dfc  cmp     eax, 5
0x180039dff  jz      loc_180039FCB
0x180039e05  mov     edx, [rbp+37h+arg_10]
0x180039e08  xor     ecx, ecx
0x180039e0a  cmp     dword ptr [rsi+40h], 2
0x180039e0e  mov     [rsi+228h], rbx
0x180039e15  setnz   cl
0x180039e18  mov     [rbx], ecx
0x180039e1a  test    edx, edx
0x180039e1c  jnz     loc_18003A376
0x180039e22  add     r14, 10h
0x180039e26  lea     r15, [rbx+8]
0x180039e2a  test    r13d, r13d
0x180039e2d  jnz     short loc_180039E34
0x180039e2f  mov     [r14], r15
0x180039e32  jmp     short loc_180039E66
0x180039e34  mov     rax, [rbp+37h+Buf2]
0x180039e38  xor     r9d, r9d; fClient
0x180039e3b  mov     [rsp+0A0h+var_78], rax; pSingleEnabledExtensionId
0x180039e40  mov     responseMessageType, r12d; cNumExtent
0x180039e43  mov     edx, r13d; cMax
0x180039e46  mov     [rsp+0A0h+pCall], rsi; pCall
0x180039e4b  mov     this, r15; pArray
0x180039e4e  mov     dword ptr [rbx+4], 77646853h
0x180039e55  call    ?FillBuffer@@YAPEAXPEAUWireExtentArray@@KIHPEBVCMessageCall@@PEBU_GUID@@@Z; FillBuffer(WireExtentArray *,ulong,uint,int,CMessageCall const *,_GUID const *)
0x180039e5a  mov     [r14], rax
0x180039e5d  cmp     rax, r15
0x180039e60  jnz     loc_18003A47B
0x180039e66  xor     edx, edx
0x180039e68  mov     [rbx+4], edx
0x180039e6b  mov     eax, [r14]
0x180039e6e  sub     eax, ebx
0x180039e70  mov     [rsi+230h], eax
0x180039e76  test    dl, dl
0x180039e78  jnz     loc_180039EFF
0x180039e7e  cmp     dword ptr [rsi+40h], 2
0x180039e82  jz      short loc_180039EFF
0x180039e84  mov     rbx, [r14]
0x180039e87  mov     eax, [rsi+240h]
0x180039e8d  add     rax, rbx
0x180039e90  mov     [rsi+238h], rbx
0x180039e97  mov     [r14], rax
0x180039e9a  mov     [rsi+268h], rbx
0x180039ea1  cmp     [rbp+37h+arg_20], dl
0x180039ea4  jnz     loc_18003A19E
0x180039eaa  mov     r12d, [rsi+240h]
0x180039eb1  cmp     r12d, 18h
0x180039eb5  jnb     loc_180039F7A
0x180039ebb  mov     this, [rbp+3Fh]; callerReturnAddress
0x180039ebf  lea     r8, aOnecoreComComb_118; "onecore\\com\\combase\\callheaders\\loc"...
0x180039ec6  mov     edx, 10Fh; lineNumber
0x180039ecb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180039ed1  mov     [rbx], rax
0x180039ed4  test    ecx, ecx
0x180039ed6  mov     eax, edx
0x180039ed8  setnz   al
0x180039edb  mov     [rbx+0Ch], eax
0x180039ede  mov     rax, [rbp+37h+Src]
0x180039ee2  test    rax, rax
0x180039ee5  jnz     loc_18003A5BD
0x180039eeb  mov     r13d, r15d
0x180039eee  mov     [rbx+10h], edx
0x180039ef1  mov     eax, dword ptr [rbp+37h+tls._pData]
0x180039ef4  test    eax, eax
0x180039ef6  jnz     loc_18003A5F1
0x180039efc  mov     [rbx+14h], edx
0x180039eff  mov     r13, [rbp+37h+Src]
0x180039f03  mov     rax, [r14]
0x180039f06  mov     [rsi+258h], rax
0x180039f0d  mov     rax, [rbp+37h+arg_8]
0x180039f11  mov     eax, [rax+18h]
0x180039f14  mov     [rsi+260h], eax
0x180039f1a  mov     rax, [r14]
0x180039f1d  mov     [rsi+278h], rax
0x180039f24  test    r13, r13
0x180039f27  jnz     loc_18003A2E8
0x180039f2d  test    rdi, rdi
0x180039f30  jz      short loc_180039F44
0x180039f32  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180039f39  mov     r8, rdi; lpMem
0x180039f3c  xor     edx, edx; dwFlags
0x180039f3e  call    cs:__imp_HeapFree
0x180039f44  xor     eax, eax
0x180039f46  mov     r13, [rsp+0A0h+var_30]
0x180039f4b  mov     r12, [rsp+0A0h+var_28]
0x180039f50  mov     rdi, [rsp+0A0h+var_20]
0x180039f58  mov     r15, [rsp+0A0h+var_38]
0x180039f5d  add     rsp, 88h
0x180039f64  pop     r14
0x180039f66  pop     rsi
0x180039f67  pop     rbx
0x180039f68  pop     rbp
0x180039f69  retn
0x180039f6a  mov     r14d, 80070216h
0x180039f70  mov     edx, 0F52h
0x180039f75  jmp     loc_180039D57
0x180039f7a  mov     ecx, [rbp+37h+arg_28]
0x180039f7d  mov     rax, [rsi+150h]
0x180039f84  mov     [rbx+8], edx
0x180039f87  lea     r15d, [this+18h]
0x180039f8b  cmp     r15d, 18h
0x180039f8f  jnb     loc_18003A4E4
0x180039f95  mov     this, [rbp+3Fh]; callerReturnAddress
0x180039f99  lea     rbx, aOnecoreComComb_118; "onecore\\com\\combase\\callheaders\\loc"...
0x180039fa0  mov     r14d, 80070216h
0x180039fa6  mov     r8, rbx; fileName
0x180039fa9  mov     r9d, r14d; hr
0x180039fac  mov     edx, 0EFh; lineNumber
0x180039fb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039fb6  mov     this, [rbp+3Fh]; callerReturnAddress
  ... truncated ...
```
