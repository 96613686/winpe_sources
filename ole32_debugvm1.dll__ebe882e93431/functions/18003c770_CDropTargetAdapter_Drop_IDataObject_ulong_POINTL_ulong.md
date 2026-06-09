# CDropTargetAdapter::Drop(IDataObject *,ulong,_POINTL,ulong *)

- ea: `0x18003c770`
- end: `0x18003ca61`
- name: `?Drop@CDropTargetAdapter@@QEAAJPEAUIDataObject@@KU_POINTL@@PEAK@Z`
- size: `753`
- prototype: `HRESULT __fastcall(CDropTargetAdapter *this, IDataObject *pDataObject, unsigned int grfKeyState, _POINTL ptl, unsigned int *pdwEffect)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f4f0`

## callees

- `0x18000c3dc`
- `0x18000ccac`
- `0x18000d38c`
- `0x18003c770`
- `0x18003ee7c`
- `0x180040a6c`
- `0x180040b1c`
- `0x180042690`
- `0x18008fd68`
- `0x18009443c`
- `0x180095754`
- `0x1800a4f50`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c824`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c85e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c824`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c85e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18003ca10`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18003ca10`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18003c9cc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18003c9cc`
- `USER32!PostMessageW` at `0x18003ca26`
- `USER32!PostMessageW` at `0x18003ca26`
- `USER32!SetThreadDpiAwarenessContext` at `0x18003c8c0`
- `USER32!SetThreadDpiAwarenessContext` at `0x18003ca3e`
- `USER32!SetThreadDpiAwarenessContext` at `0x18003c8c0`
- `USER32!SetThreadDpiAwarenessContext` at `0x18003ca3e`
- `USER32!GetWindowDpiAwarenessContext` at `0x18003c8b7`
- `USER32!GetWindowDpiAwarenessContext` at `0x18003c8b7`
- `USER32!GetThreadDpiAwarenessContext` at `0x18003c7b2`
- `USER32!GetThreadDpiAwarenessContext` at `0x18003c7b2`
- `USER32!ScreenToClient` at `0x18003c9f6`
- `USER32!ScreenToClient` at `0x18003c9f6`
- `USER32!__imp_PhysicalToLogicalDpiPointForWindow` at `0x18003c8ae`
- `USER32!__imp_PhysicalToLogicalDpiPointForWindow` at `0x18003c8ae`

## pseudocode

```c
__int64 __fastcall CDropTargetAdapter::Drop(
        CDropTargetAdapter *this,
        IDataObject *pDataObject,
        unsigned int grfKeyState,
        _POINTL ptl,
        unsigned int *pdwEffect)
{
  __int64 ThreadDpiAwarenessContext; // r12
  wil::ReportingKind v9; // r8
  unsigned __int64 v10; // r9
  int v11; // r15d
  HWND__ *hwndOLE; // rdi
  __int64 WindowDpiAwarenessContext; // rax
  unsigned int *v14; // r14
  HWND__ *hwndSource; // rax
  HRESULT v16; // eax
  unsigned int v17; // edi
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rax
  _DWORD *v20; // rax
  _DWORD *v21; // rsi
  unsigned int returnLength; // [rsp+50h] [rbp-31h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > tokenHandle; // [rsp+58h] [rbp-29h] BYREF
  tagSTGMEDIUM medium; // [rsp+60h] [rbp-21h] BYREF
  tagFORMATETC formatetc; // [rsp+78h] [rbp-9h] BYREF
  tagPOINT pt; // [rsp+E0h] [rbp+5Fh] BYREF
  _POINTL v28; // [rsp+F8h] [rbp+77h] BYREF

  v28 = ptl;
  memset(&medium, 0, sizeof(medium));
  memset(&formatetc, 0, sizeof(formatetc));
  ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext();
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloDragAndDrop>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_AppSiloDragAndDrop>::GetImpl'::`2'::impl,
    1,
    v9,
    v10);
  if ( this->_hwndOLE )
  {
    pt.x = 0;
    returnLength = 0;
    tokenHandle.m_ptr = 0;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixIncorrectReturnCheckInCDropTargetAdapter>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_FixIncorrectReturnCheckInCDropTargetAdapter>::GetImpl'::`2'::impl) )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &tokenHandle,
        0);
      if ( GetProcessTokenByHandle(this->_hwndOLE, &tokenHandle.m_ptr) < 0
        || !GetTokenInformation(tokenHandle.m_ptr, TokenIsAppSilo, &pt, 4u, &returnLength) )
      {
        goto LABEL_10;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &tokenHandle,
        0);
      if ( GetProcessTokenByHandle(this->_hwndOLE, &tokenHandle.m_ptr) < 0
        || GetTokenInformation(tokenHandle.m_ptr, TokenIsAppSilo, &pt, 4u, &returnLength) < 0 )
      {
        goto LABEL_10;
      }
    }
    if ( pt.x )
      BrokerDragDropFilesForAppSilos(tokenHandle.m_ptr, pDataObject);
LABEL_10:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&tokenHandle);
    if ( this->_hwndOLE )
      goto LABEL_14;
  }
  if ( !this->_hwnd31 && !IsContainerDragOperation() )
  {
    v11 = 0;
    goto LABEL_17;
  }
LABEL_14:
  hwndOLE = this->_hwndOLE;
  if ( !this->_hwndOLE )
    hwndOLE = this->_hwnd31;
  PhysicalToLogicalDpiPointForWindow(hwndOLE, &v28);
  WindowDpiAwarenessContext = GetWindowDpiAwarenessContext(hwndOLE);
  ThreadDpiAwarenessContext = SetThreadDpiAwarenessContext(WindowDpiAwarenessContext);
  v11 = 1;
LABEL_17:
  v14 = pdwEffect;
  if ( (this->_hwndOLE || IsContainerDragOperation()) && this->_dwEffectLast )
  {
    hwndSource = GetPrivateClipboardWindow(CLIP_QUERY);
    v16 = PrivDragDrop(
            this->_hwndOLE,
            0,
            (tagDRAGOP)(this->_pdo->_fSourceIsAppContainer != 0 ? DRAGOP_DROP_FROM_APPCONTAINER : DRAGOP_DROP),
            this->_pdo->_DOBuffer,
            pDataObject,
            grfKeyState,
            v28,
            v14,
            hwndSource,
            &this->_hDDInfo);
    goto LABEL_24;
  }
  if ( this->_hwndOLE || (v17 = -2147467259, IsContainerDragOperation()) )
  {
    *v14 = 0;
    v16 = CDropTargetAdapter::DragLeave(this);
LABEL_24:
    v17 = v16;
    if ( !v16 && *v14 || v16 == 1 )
      goto LABEL_34;
  }
  if ( this->_hwnd31 )
  {
    medium.tymed = 0;
    formatetc.cfFormat = 15;
    lpVtbl = pDataObject->lpVtbl;
    formatetc.ptd = 0;
    formatetc.lindex = -1;
    formatetc.dwAspect = 1;
    QueryInterface = lpVtbl[1].QueryInterface;
    formatetc.tymed = 1;
    v17 = ((__int64 (__fastcall *)(IDataObject *, tagFORMATETC *, tagSTGMEDIUM *))QueryInterface)(
            pDataObject,
            &formatetc,
            &medium);
    if ( !v17 )
    {
      v20 = GlobalLock(medium.hBitmap);
      v21 = v20;
      pt = (tagPOINT)v28;
      if ( v20 )
      {
        v20[3] = IsNCDrop(this->_hwnd31, (tagPOINT)v28);
        if ( ScreenToClient(this->_hwnd31, &pt) )
          *(tagPOINT *)(v21 + 1) = pt;
        GlobalUnlock(medium.hBitmap);
      }
      *v14 = PostMessageW(this->_hwnd31, 0x233u, (WPARAM)medium.hBitmap, 0);
    }
  }
LABEL_34:
  if ( v11 )
    SetThreadDpiAwarenessContext(ThreadDpiAwarenessContext);
  return v17;
}

```

## disassembly

```asm
0x18003c770  mov     [rsp-8+arg_8], rbx
0x18003c775  mov     qword ptr [rsp-8+arg_18.x], ptl
0x18003c77a  push    rbp
0x18003c77b  push    rsi
0x18003c77c  push    rdi
0x18003c77d  push    r12
0x18003c77f  push    r13
0x18003c781  push    r14
0x18003c783  push    r15
0x18003c785  lea     rbp, [rsp-1Fh]
0x18003c78a  sub     rsp, 0A0h
0x18003c791  xorps   xmm1, xmm1
0x18003c794  xorps   xmm0, xmm0
0x18003c797  xor     eax, eax
0x18003c799  mov     r13d, grfKeyState
0x18003c79c  movups  xmmword ptr [rbp+4Fh+medium.tymed], xmm0
0x18003c7a0  mov     [rbp+4Fh+medium.pUnkForRelease], rax
0x18003c7a4  mov     rsi, pDataObject
0x18003c7a7  movups  xmmword ptr [rbp+4Fh+formatetc.cfFormat], xmm1
0x18003c7ab  mov     rbx, this
0x18003c7ae  movups  xmmword ptr [rbp+4Fh+formatetc.dwAspect], xmm1
0x18003c7b2  call    cs:__imp_GetThreadDpiAwarenessContext
0x18003c7b8  mov     r12, rax
0x18003c7bb  mov     dl, 1; __annotation("WILSTG:|42932704|Feature_AppSiloDragAndDrop|AlwaysEnabled")
0x18003c7bd  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppSiloDragAndDrop@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloDragAndDrop@@@details@3@XZ@4V453@A; this
0x18003c7c4  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppSiloDragAndDrop@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppSiloDragAndDrop>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003c7c9  xor     edi, edi
0x18003c7cb  lea     r14d, [rdi+4]
0x18003c7cf  cmp     [rbx], rdi
0x18003c7d2  jz      loc_18003C887
0x18003c7d8  mov     [rbp+4Fh+pt.x], edi
0x18003c7db  mov     [rbp+4Fh+returnLength], edi
0x18003c7de  mov     [rbp+4Fh+tokenHandle.m_ptr], rdi
0x18003c7e2  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixIncorrectReturnCheckInCDropTargetAdapter@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixIncorrectReturnCheckInCDropTargetAdapter@@@details@3@XZ@4V453@A; __annotation("WILSTG:|61001778|Feature_FixIncorrectReturnCheckInCDropTargetAdapter|EnabledByDefault")
0x18003c7e9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixIncorrectReturnCheckInCDropTargetAdapter@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixIncorrectReturnCheckInCDropTargetAdapter>::__private_IsEnabled(void)
0x18003c7ee  xor     edx, edx; ptr
0x18003c7f0  lea     this, [rbp+4Fh+tokenHandle]; this
0x18003c7f4  test    al, al
0x18003c7f6  jz      short loc_18003C830
0x18003c7f8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003c7fd  mov     this, [rbx]; hwnd
0x18003c800  lea     pDataObject, [rbp+4Fh+tokenHandle]; tokenHandle
0x18003c804  call    ?GetProcessTokenByHandle@@YAJPEAUHWND__@@PEAPEAX@Z; GetProcessTokenByHandle(HWND__ *,void * *)
0x18003c809  test    eax, eax
0x18003c80b  js      short loc_18003C879
0x18003c80d  mov     this, [rbp+4Fh+tokenHandle.m_ptr]; TokenHandle
0x18003c811  lea     rax, [rbp+4Fh+returnLength]
0x18003c815  mov     r9d, r14d; TokenInformationLength
0x18003c818  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18003c81d  lea     r8, [rbp+4Fh+pt]; TokenInformation
0x18003c821  lea     edx, [rdi+30h]; TokenInformationClass
0x18003c824  call    cs:__imp_GetTokenInformation
0x18003c82a  test    eax, eax
0x18003c82c  jz      short loc_18003C879
0x18003c82e  jmp     short loc_18003C868
0x18003c830  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003c835  mov     this, [rbx]; hwnd
0x18003c838  lea     pDataObject, [rbp+4Fh+tokenHandle]; tokenHandle
0x18003c83c  call    ?GetProcessTokenByHandle@@YAJPEAUHWND__@@PEAPEAX@Z; GetProcessTokenByHandle(HWND__ *,void * *)
0x18003c841  test    eax, eax
0x18003c843  js      short loc_18003C879
0x18003c845  mov     this, [rbp+4Fh+tokenHandle.m_ptr]; TokenHandle
0x18003c849  lea     rax, [rbp+4Fh+returnLength]
0x18003c84d  mov     r9d, r14d; TokenInformationLength
0x18003c850  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18003c855  lea     r8, [rbp+4Fh+pt]; TokenInformation
0x18003c859  mov     edx, 30h ; '0'; TokenInformationClass
0x18003c85e  call    cs:__imp_GetTokenInformation
0x18003c864  test    eax, eax
0x18003c866  js      short loc_18003C879
0x18003c868  cmp     [rbp+4Fh+pt.x], edi
0x18003c86b  jz      short loc_18003C879
0x18003c86d  mov     this, [rbp+4Fh+tokenHandle.m_ptr]; tokenHandle
0x18003c871  mov     pDataObject, rsi; dataObject
0x18003c874  call    ?BrokerDragDropFilesForAppSilos@@YAJPEAXPEAUIDataObject@@@Z; BrokerDragDropFilesForAppSilos(void *,IDataObject *)
0x18003c879  lea     this, [rbp+4Fh+tokenHandle]; this
0x18003c87d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003c882  cmp     [rbx], rdi
0x18003c885  jnz     short loc_18003C89B
0x18003c887  cmp     [rbx+8], rdi
0x18003c88b  jnz     short loc_18003C89B
0x18003c88d  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x18003c892  test    al, al
0x18003c894  jnz     short loc_18003C89B
0x18003c896  mov     r15d, edi
0x18003c899  jmp     short loc_18003C8CF
0x18003c89b  mov     rdi, [rbx]
0x18003c89e  test    rdi, rdi
0x18003c8a1  jnz     short loc_18003C8A7
0x18003c8a3  mov     rdi, [rbx+8]
0x18003c8a7  lea     pDataObject, [rbp+4Fh+arg_18]
0x18003c8ab  mov     this, rdi
0x18003c8ae  call    cs:__imp_PhysicalToLogicalDpiPointForWindow
0x18003c8b4  mov     this, rdi
0x18003c8b7  call    cs:__imp_GetWindowDpiAwarenessContext
0x18003c8bd  mov     this, rax
0x18003c8c0  call    cs:__imp_SetThreadDpiAwarenessContext
0x18003c8c6  xor     edi, edi
0x18003c8c8  mov     r12, rax
0x18003c8cb  lea     r15d, [rdi+1]
0x18003c8cf  mov     r14, [rbp+4Fh+arg_20]
0x18003c8d3  cmp     [rbx], rdi
0x18003c8d6  jnz     short loc_18003C8E1
0x18003c8d8  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x18003c8dd  test    al, al
0x18003c8df  jz      short loc_18003C93B
0x18003c8e1  cmp     [rbx+10h], edi
0x18003c8e4  jz      short loc_18003C93B
0x18003c8e6  xor     ecx, ecx; fFlags
0x18003c8e8  call    ?GetPrivateClipboardWindow@@YAPEAUHWND__@@W4tagCLIPWINDOWFLAGS@@@Z; GetPrivateClipboardWindow(tagCLIPWINDOWFLAGS)
0x18003c8ed  mov     ptl, [rbx+18h]
0x18003c8f1  lea     r10, [rbx+20h]
0x18003c8f5  mov     this, qword ptr [rbp+4Fh+arg_18.x]
0x18003c8f9  mov     [rsp+0D0h+phDDInfo], r10; phDDInfo
0x18003c8fe  mov     [rsp+0D0h+hwndSource], rax; hwndSource
0x18003c903  mov     edx, [ptl+0C8h]
0x18003c90a  mov     ptl, [ptl+18h]; pIFDDataObject
0x18003c90e  neg     edx
0x18003c910  mov     [rsp+0D0h+var_98], r14; pdwEffect
0x18003c915  sbb     grfKeyState, grfKeyState
0x18003c918  mov     qword ptr [rsp+0D0h+var_A0.x], this; ptl
0x18003c91d  mov     this, [rbx]; hwnd
0x18003c920  and     grfKeyState, 2
0x18003c924  add     grfKeyState, 4; dop
0x18003c928  mov     [rsp+0D0h+var_A8], r13d; grfKeyState
0x18003c92d  xor     edx, edx; pWinRtTarget
0x18003c92f  mov     [rsp+0D0h+ReturnLength], rsi; pIDataObject
0x18003c934  call    ?PrivDragDrop@@YAJPEAUHWND__@@PEAUIDropTarget@@W4tagDRAGOP@@PEAUtagInterfaceData@@PEAUIDataObject@@KU_POINTL@@PEAK0PEAPEAX@Z; PrivDragDrop(HWND__ *,IDropTarget *,tagDRAGOP,tagInterfaceData *,IDataObject *,ulong,_POINTL,ulong *,HWND__ *,void * *)
0x18003c939  jmp     short loc_18003C95B
0x18003c93b  cmp     [rbx], rdi
0x18003c93e  jnz     short loc_18003C950
0x18003c940  mov     edi, 80004005h
0x18003c945  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x18003c94a  test    al, al
0x18003c94c  jz      short loc_18003C973
0x18003c94e  xor     edi, edi
0x18003c950  mov     this, rbx; this
0x18003c953  mov     [r14], edi
0x18003c956  call    ?DragLeave@CDropTargetAdapter@@QEAAJXZ; CDropTargetAdapter::DragLeave(void)
0x18003c95b  mov     edi, eax
0x18003c95d  test    eax, eax
0x18003c95f  jnz     short loc_18003C96A
0x18003c961  cmp     [r14], eax
0x18003c964  jnz     loc_18003CA36
0x18003c96a  cmp     edi, 1
0x18003c96d  jz      loc_18003CA36
0x18003c973  cmp     qword ptr [rbx+8], 0
0x18003c978  jz      loc_18003CA36
0x18003c97e  mov     eax, 0Fh
0x18003c983  mov     [rbp+4Fh+medium.tymed], 0
0x18003c98a  mov     [rbp+4Fh+formatetc.cfFormat], ax
0x18003c98e  lea     r8, [rbp+4Fh+medium]
0x18003c992  mov     rax, [rsi]
0x18003c995  lea     pDataObject, [rbp+4Fh+formatetc]
0x18003c999  mov     this, rsi
0x18003c99c  mov     [rbp+4Fh+formatetc.ptd], 0
0x18003c9a4  mov     [rbp+4Fh+formatetc.lindex], 0FFFFFFFFh
0x18003c9ab  mov     [rbp+4Fh+formatetc.dwAspect], 1
0x18003c9b2  mov     rax, [rax+18h]
0x18003c9b6  mov     [rbp+4Fh+formatetc.tymed], 1
0x18003c9bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9c2  mov     edi, eax
0x18003c9c4  test    eax, eax
0x18003c9c6  jnz     short loc_18003CA36
0x18003c9c8  mov     this, qword ptr [rbp+4Fh+medium.8]; hMem
0x18003c9cc  call    cs:__imp_GlobalLock
0x18003c9d2  mov     pDataObject, qword ptr [rbp+4Fh+arg_18.x]; pt
0x18003c9d6  mov     rsi, rax
0x18003c9d9  mov     qword ptr [rbp+4Fh+pt.x], pDataObject
0x18003c9dd  test    rax, rax
0x18003c9e0  jz      short loc_18003CA16
0x18003c9e2  mov     this, [rbx+8]; hwnd
0x18003c9e6  call    ?IsNCDrop@@YAHPEAUHWND__@@UtagPOINT@@@Z; IsNCDrop(HWND__ *,tagPOINT)
0x18003c9eb  mov     [rsi+0Ch], eax
0x18003c9ee  lea     pDataObject, [rbp+4Fh+pt]; lpPoint
0x18003c9f2  mov     this, [rbx+8]; hWnd
0x18003c9f6  call    cs:__imp_ScreenToClient
0x18003c9fc  test    eax, eax
0x18003c9fe  jz      short loc_18003CA0C
0x18003ca00  mov     eax, [rbp+4Fh+pt.x]
0x18003ca03  mov     [rsi+4], eax
0x18003ca06  mov     eax, [rbp+4Fh+pt.y]
0x18003ca09  mov     [rsi+8], eax
0x18003ca0c  mov     this, qword ptr [rbp+4Fh+medium.8]; hMem
0x18003ca10  call    cs:__imp_GlobalUnlock
0x18003ca16  mov     r8, qword ptr [rbp+4Fh+medium.8]; wParam
0x18003ca1a  xor     r9d, r9d; lParam
0x18003ca1d  mov     this, [rbx+8]; hWnd
0x18003ca21  mov     edx, 233h; Msg
0x18003ca26  call    cs:__imp_PostMessageW
0x18003ca2c  xor     ecx, ecx
0x18003ca2e  test    eax, eax
0x18003ca30  setnz   cl
0x18003ca33  mov     [r14], ecx
0x18003ca36  test    r15d, r15d
0x18003ca39  jz      short loc_18003CA44
0x18003ca3b  mov     this, r12
0x18003ca3e  call    cs:__imp_SetThreadDpiAwarenessContext
0x18003ca44  mov     rbx, [rsp+0D0h+arg_8]
0x18003ca4c  mov     eax, edi
0x18003ca4e  add     rsp, 0A0h
0x18003ca55  pop     r15
0x18003ca57  pop     r14
0x18003ca59  pop     r13
0x18003ca5b  pop     r12
0x18003ca5d  pop     rdi
0x18003ca5e  pop     rsi
0x18003ca5f  pop     rbp
0x18003ca60  retn
```
