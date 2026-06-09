# CDragOperation::~CDragOperation(void)

- ea: `0x18003a500`
- end: `0x18003a726`
- name: `??1CDragOperation@@UEAA@XZ`
- size: `550`
- prototype: `void __fastcall(CDragOperation *this)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c430`
- `0x1800936f0`

## callees

- `0x18000a0e8`
- `0x18000ac30`
- `0x1800293b8`
- `0x18003a500`
- `0x18003fd50`
- `0x18004777c`
- `0x180059088`
- `0x180073994`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a5fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a5fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a539`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a681`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a693`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a539`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a681`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a693`
- `USER32!SetCursor` at `0x18003a52a`
- `USER32!SetCursor` at `0x18003a52a`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18003a594`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18003a594`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a6b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a6cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a6b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a6cb`

## string_xrefs

- `0x18003a5e1`: `com\ole32\ole232\drag\drag.cpp`

## pseudocode

```c
void __fastcall CDragOperation::~CDragOperation(CDragOperation *this)
{
  void *hFormats; // rcx
  tagMInterfacePointer *v3; // r8
  int v4; // r10d
  TraceLevel LevelPlus1; // ecx
  IDropSourceNotify *pDSNotify; // rcx
  IDropSource *pDropSource; // rcx
  IDataObject *pDataObject; // rcx
  void *hDragSourceToken; // rcx
  void *hDragInProgress; // rcx
  wchar_t *m_ptr; // rcx
  wchar_t *v12; // rcx
  CReadInterfaceDataFromInternalSourceMarshalingStream objectStream; // [rsp+30h] [rbp-38h] BYREF

  this->lpVtbl = (struct IUnknownVtbl *)CDragOperation::`vftable';
  CDragOperation::ReleaseCapture(this);
  if ( !this->_fWinRTDrag )
    SetCursor(this->_curOld);
  hFormats = this->_hFormats;
  if ( hFormats )
  {
    CloseHandle(hFormats);
    this->_hFormats = 0;
  }
  if ( this->_DOBuffer )
  {
    objectStream.CAbstractMarshalingStream = 0;
    CAbstractMarshalingStream::CAbstractMarshalingStream(&objectStream);
    *(_QWORD *)&objectStream._lOffset = 0;
    objectStream.lpVtbl = (struct IStreamVtbl *)CBaseMInterfacePointerMarshalingStream::`vftable';
    objectStream._pMInterfacePointer = v3;
    objectStream._fFree = 0;
    objectStream._cbBufferSize = v3->ulCntData;
    objectStream.lpVtbl = (struct IStreamVtbl *)CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable';
    v4 = CoReleaseMarshalData(&objectStream);
    if ( v4 >= 0 )
    {
      if ( !gfEnableTracing )
        goto LABEL_11;
      LevelPlus1 = VERBOSE;
    }
    else
    {
      LevelPlus1 = Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 )
      {
LABEL_10:
        ComTraceHr(
          v4,
          "com\\ole32\\ole232\\drag\\drag.cpp",
          "CDragOperation::~CDragOperation",
          1590,
          L"CoReleaseMarshalData: %!HRESULT!",
          v4);
        goto LABEL_11;
      }
      if ( !gfEnableTracing )
      {
LABEL_11:
        HeapFree(g_hHeap, 0, this->_DOBuffer);
        CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(&objectStream);
        goto LABEL_12;
      }
    }
    if ( IsWppLevelEnabled(LevelPlus1) )
      goto LABEL_10;
    goto LABEL_11;
  }
LABEL_12:
  if ( !this->_fConcurrentDrag && !this->_fWinRTDrag )
    CDragOperation::s_fDoDragDropInFlight = 0;
  pDSNotify = this->_pDSNotify;
  if ( pDSNotify )
  {
    ((void (__fastcall *)(IDropSourceNotify *))pDSNotify->lpVtbl->Release)(pDSNotify);
    this->_pDSNotify = 0;
  }
  if ( this->_fWinRTDrag )
  {
    pDropSource = this->_pDropSource;
    if ( pDropSource )
    {
      ((void (__fastcall *)(IDropSource *))pDropSource->lpVtbl->Release)(pDropSource);
      this->_pDropSource = 0;
    }
  }
  pDataObject = this->_pDataObject;
  if ( pDataObject )
  {
    ((void (__fastcall *)(IDataObject *))pDataObject->lpVtbl->Release)(pDataObject);
    this->_pDataObject = 0;
  }
  hDragSourceToken = this->_hDragSourceToken;
  if ( hDragSourceToken )
    CloseHandle(hDragSourceToken);
  hDragInProgress = this->_hDragInProgress;
  if ( hDragInProgress )
  {
    CloseHandle(hDragInProgress);
    this->_hDragInProgress = 0;
  }
  g_forcedDropTarget._fDragDropActive = 0;
  g_forcedDropTarget._hwndFDTCurrent = 0;
  m_ptr = this->m_dataObjectEnterpriseId.m_ptr;
  if ( m_ptr )
    CoTaskMemFree(m_ptr);
  v12 = this->m_sourceEnterpriseId.m_ptr;
  if ( v12 )
    CoTaskMemFree(v12);
  DragDropTelemetry::DragDropSession::~DragDropSession(&this->_telemetrySession);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&this->_spWinRtExclusionToken);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&this->_spWinRtExtension);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&this->m_nonRPCSSRegisteredDropTarget);
  this->refcount_ = -1073741823;
}

```

## disassembly

```asm
0x18003a500  mov     [rsp+arg_0], rbx
0x18003a505  push    rdi
0x18003a506  sub     rsp, 60h
0x18003a50a  lea     rax, ??_7CDragOperation@@6B@; const CDragOperation::`vftable'
0x18003a511  mov     rbx, this
0x18003a514  mov     [this], rax
0x18003a517  call    ?ReleaseCapture@CDragOperation@@QEAAXXZ; CDragOperation::ReleaseCapture(void)
0x18003a51c  xor     edi, edi
0x18003a51e  cmp     [rbx+0A8h], edi
0x18003a524  jnz     short loc_18003A530
0x18003a526  mov     this, [rbx+70h]; hCursor
0x18003a52a  call    cs:__imp_SetCursor
0x18003a530  mov     this, [rbx+48h]; hObject
0x18003a534  test    this, this
0x18003a537  jz      short loc_18003A543
0x18003a539  call    cs:__imp_CloseHandle
0x18003a53f  mov     [rbx+48h], rdi
0x18003a543  mov     r8, [rbx+18h]
0x18003a547  test    r8, r8
0x18003a54a  jz      loc_18003A60A
0x18003a550  xorps   xmm0, xmm0
0x18003a553  lea     this, [rsp+68h+objectStream]; this
0x18003a558  movups  xmmword ptr [rsp+68h+objectStream.lpVtbl], xmm0
0x18003a55d  call    ??0CAbstractMarshalingStream@@QEAA@XZ; CAbstractMarshalingStream::CAbstractMarshalingStream(void)
0x18003a562  lea     this, ??_7CBaseMInterfacePointerMarshalingStream@@6B@; const CBaseMInterfacePointerMarshalingStream::`vftable'
0x18003a569  mov     qword ptr [rsp+68h+objectStream._lOffset], rdi
0x18003a56e  mov     [rsp+68h+objectStream.lpVtbl], this
0x18003a573  lea     this, [rsp+68h+objectStream]; pStm
0x18003a578  mov     [rsp+68h+objectStream._pMInterfacePointer], r8
0x18003a57d  mov     [rsp+68h+objectStream._fFree], edi
0x18003a581  mov     eax, [r8]
0x18003a584  mov     [rsp+68h+objectStream._cbBufferSize], eax
0x18003a588  lea     rax, ??_7CReadInterfaceDataFromInternalSourceMarshalingStream@@6B@; const CReadInterfaceDataFromInternalSourceMarshalingStream::`vftable'
0x18003a58f  mov     [rsp+68h+objectStream.lpVtbl], rax
0x18003a594  call    cs:__imp_CoReleaseMarshalData
0x18003a59a  mov     r10d, eax
0x18003a59d  test    eax, eax
0x18003a59f  jns     loc_18003A710
0x18003a5a5  mov     ecx, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1; level
0x18003a5ab  test    ecx, ecx
0x18003a5ad  jnz     short loc_18003A5C0
0x18003a5af  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18003a5b5  jz      short loc_18003A5ED
0x18003a5b7  call    IsWppLevelEnabled
0x18003a5bc  test    al, al
0x18003a5be  jz      short loc_18003A5ED
0x18003a5c0  lea     rax, aCoreleasemarsh_1; "CoReleaseMarshalData: %!HRESULT!"
0x18003a5c7  mov     [rsp+68h+var_40], r10d
0x18003a5cc  mov     r9d, 636h; line
0x18003a5d2  mov     [rsp+68h+format], rax; format
0x18003a5d7  lea     r8, aCdragoperation; "CDragOperation::~CDragOperation"
0x18003a5de  mov     ecx, r10d; hr
0x18003a5e1  lea     rdx, aComOle32Ole232_4; "com\\ole32\\ole232\\drag\\drag.cpp"
0x18003a5e8  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x18003a5ed  mov     r8, [rbx+18h]; lpMem
0x18003a5f1  xor     edx, edx; dwFlags
0x18003a5f3  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x18003a5fa  call    cs:__imp_HeapFree
0x18003a600  lea     this, [rsp+68h+objectStream]; this
0x18003a605  call    ??1CBaseMInterfacePointerMarshalingStream@@MEAA@XZ; CBaseMInterfacePointerMarshalingStream::~CBaseMInterfacePointerMarshalingStream(void)
0x18003a60a  cmp     [rbx+0CCh], dil
0x18003a611  jnz     short loc_18003A622
0x18003a613  cmp     [rbx+0A8h], edi
0x18003a619  jnz     short loc_18003A622
0x18003a61b  mov     cs:?s_fDoDragDropInFlight@CDragOperation@@0_NA, dil; bool CDragOperation::s_fDoDragDropInFlight
0x18003a622  mov     this, [rbx+28h]
0x18003a626  test    this, this
0x18003a629  jz      short loc_18003A63B
0x18003a62b  mov     rax, [this]
0x18003a62e  mov     rax, [rax+10h]
0x18003a632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a637  mov     [rbx+28h], rdi
0x18003a63b  cmp     [rbx+0A8h], edi
0x18003a641  jz      short loc_18003A65C
0x18003a643  mov     this, [rbx+20h]
0x18003a647  test    this, this
0x18003a64a  jz      short loc_18003A65C
0x18003a64c  mov     rax, [this]
0x18003a64f  mov     rax, [rax+10h]
0x18003a653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a658  mov     [rbx+20h], rdi
0x18003a65c  mov     this, [rbx+10h]
0x18003a660  test    this, this
0x18003a663  jz      short loc_18003A675
0x18003a665  mov     rax, [this]
0x18003a668  mov     rax, [rax+10h]
0x18003a66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a671  mov     [rbx+10h], rdi
0x18003a675  mov     this, [rbx+0C0h]; hObject
0x18003a67c  test    this, this
0x18003a67f  jz      short loc_18003A687
0x18003a681  call    cs:__imp_CloseHandle
0x18003a687  mov     this, [rbx+0B0h]; hObject
0x18003a68e  test    this, this
0x18003a691  jz      short loc_18003A6A0
0x18003a693  call    cs:__imp_CloseHandle
0x18003a699  mov     [rbx+0B0h], rdi
0x18003a6a0  mov     cs:?g_forcedDropTarget@@3VCForcedDropTarget@@A._fDragDropActive, edi; CForcedDropTarget g_forcedDropTarget ...
0x18003a6a6  mov     cs:?g_forcedDropTarget@@3VCForcedDropTarget@@A._hwndFDTCurrent, rdi; CForcedDropTarget g_forcedDropTarget ...
0x18003a6ad  mov     this, [rbx+240h]; pv
0x18003a6b4  test    this, this
0x18003a6b7  jz      short loc_18003A6BF
0x18003a6b9  call    cs:__imp_CoTaskMemFree
0x18003a6bf  mov     this, [rbx+238h]; pv
0x18003a6c6  test    this, this
0x18003a6c9  jz      short loc_18003A6D1
0x18003a6cb  call    cs:__imp_CoTaskMemFree
0x18003a6d1  lea     this, [rbx+0E0h]; this
0x18003a6d8  call    ??1DragDropSession@DragDropTelemetry@@QEAA@XZ; DragDropTelemetry::DragDropSession::~DragDropSession(void)
0x18003a6dd  lea     this, [rbx+0D8h]; this
0x18003a6e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a6e9  lea     this, [rbx+0D0h]; this
0x18003a6f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a6f5  lea     this, [rbx+40h]; this
0x18003a6f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a6fe  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18003a705  mov     rbx, [rsp+68h+arg_0]
0x18003a70a  add     rsp, 60h
0x18003a70e  pop     rdi
0x18003a70f  retn
0x18003a710  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x18003a716  jz      loc_18003A5ED
0x18003a71c  mov     ecx, 3
0x18003a721  jmp     loc_18003A5B7
```
