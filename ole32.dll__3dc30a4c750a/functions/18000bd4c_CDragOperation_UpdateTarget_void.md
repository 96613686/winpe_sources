# CDragOperation::UpdateTarget(void)

- ea: `0x18000bd4c`
- end: `0x18000c3d4`
- name: `?UpdateTarget@CDragOperation@@QEAAHXZ`
- size: `1672`
- prototype: `int __fastcall(CDragOperation *this)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000c430`
- `0x180095650`

## callees

- `0x18000a0e8`
- `0x18000bd4c`
- `0x18000c3dc`
- `0x18000caf4`
- `0x18000ce98`
- `0x1800340d8`
- `0x180035978`
- `0x180041178`
- `0x180042690`
- `0x180046f30`
- `0x180052390`
- `0x180053014`
- `0x18009325c`
- `0x18009372c`
- `0x1800ce010`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x18000bf50`
- `USER32!GetWindowThreadProcessId` at `0x18000c1d8`
- `USER32!GetWindowThreadProcessId` at `0x18000c23b`
- `USER32!GetWindowThreadProcessId` at `0x18000c256`
- `USER32!GetWindowThreadProcessId` at `0x18000bf50`
- `USER32!GetWindowThreadProcessId` at `0x18000c1d8`
- `USER32!GetWindowThreadProcessId` at `0x18000c23b`
- `USER32!GetWindowThreadProcessId` at `0x18000c256`
- `USER32!GetPropW` at `0x18000bfc8`
- `USER32!GetPropW` at `0x18000c209`
- `USER32!GetPropW` at `0x18000bfc8`
- `USER32!GetPropW` at `0x18000c209`
- `USER32!SetCursor` at `0x18000c27c`
- `USER32!SetCursor` at `0x18000c397`
- `USER32!SetCursor` at `0x18000c3c9`
- `USER32!SetCursor` at `0x18000c27c`
- `USER32!SetCursor` at `0x18000c397`
- `USER32!SetCursor` at `0x18000c3c9`
- `USER32!LoadCursorW` at `0x18000c273`
- `USER32!LoadCursorW` at `0x18000c273`
- `USER32!GetWindowLongW` at `0x18000bf6b`
- `USER32!GetWindowLongW` at `0x18000bf7d`
- `USER32!GetWindowLongW` at `0x18000bf6b`
- `USER32!GetWindowLongW` at `0x18000bf7d`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000bdb4`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000be04`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000c11f`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000bdb4`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000be04`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000c11f`
- `USER32!RealChildWindowFromPoint` at `0x18000c13e`
- `USER32!RealChildWindowFromPoint` at `0x18000c13e`
- `USER32!WindowFromPoint` at `0x18000bdf7`
- `USER32!WindowFromPoint` at `0x18000bdf7`
- `USER32!GetParent` at `0x18000bf37`
- `USER32!GetParent` at `0x18000c226`
- `USER32!GetParent` at `0x18000bf37`
- `USER32!GetParent` at `0x18000c226`
- `USER32!AllowSetForegroundWindow` at `0x18000c30b`
- `USER32!AllowSetForegroundWindow` at `0x18000c30b`
- `USER32!__imp_CompositionInputSinkLuidFromPoint` at `0x18000bde9`
- `USER32!__imp_CompositionInputSinkLuidFromPoint` at `0x18000bde9`

## pseudocode

```c
__int64 __fastcall CDragOperation::UpdateTarget(CDragOperation *this)
{
  tagPOINT v1; // r14
  __int64 v3; // rbx
  __int64 v4; // rcx
  IDropSource *pDropSource; // rcx
  HRESULT v6; // r12d
  HRESULT v7; // eax
  unsigned int v8; // r15d
  IDropTarget *v9; // rcx
  HWND__ *hwndLast; // rbx
  HANDLE PropW; // rdi
  HANDLE v13; // r13
  unsigned int v14; // eax
  HWND__ *v15; // r14
  unsigned int v16; // eax
  int v17; // r12d
  HWND v18; // rax
  CDropTargetAdapter *pDropTargetAdapter; // rax
  const wchar_t *v20; // rdx
  IDragDropExtensionForOLE *ptr; // rdi
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  IDragDropExtensionForOLE *v23; // rcx
  IDragDropContainerProxy *v24; // rdi
  IDropTarget *v25; // rbx
  CDropTargetAdapter *v26; // rcx
  int v27; // ebx
  IDropSourceNotify *v28; // rcx
  HRESULT DropTarget; // eax
  CPoint cpt; // rbx
  __int64 v31; // rax
  HWND__ *v32; // rcx
  __int64 v33; // rdi
  HWND__ *v34; // rax
  HRESULT v35; // edx
  tagPOINT v36; // rax
  HWND Parent; // rax
  HCURSOR CursorW; // rax
  IDropTarget *v39; // rax
  IDropSourceNotify *pDSNotify; // rcx
  unsigned int v41; // edx
  CDropTargetAdapter *v42; // rcx
  IDropSource *v43; // rcx
  unsigned int dwCurrentProcessId; // [rsp+30h] [rbp-79h] BYREF
  unsigned int dwTempProcessID; // [rsp+34h] [rbp-75h] BYREF
  Microsoft::WRL::ComPtr<IDragDropContainerProxy> proxy; // [rsp+38h] [rbp-71h] BYREF
  HWND__ *hwndCur; // [rsp+40h] [rbp-69h] BYREF
  Microsoft::WRL::ComPtr<IDropTarget> nonRPCSSRegisteredDropTarget; // [rsp+48h] [rbp-61h] BYREF
  tagPOINT point; // [rsp+50h] [rbp-59h] BYREF
  Microsoft::WRL::ComPtr<IDragDropExtensionForOLE> spExtension; // [rsp+58h] [rbp-51h] BYREF
  HRESULT v51; // [rsp+60h] [rbp-49h]
  _LUID luid; // [rsp+68h] [rbp-41h] BYREF
  tagINPUT_TRANSFORM transform; // [rsp+70h] [rbp-39h] BYREF

  v1 = 0;
  nonRPCSSRegisteredDropTarget.ptr_ = 0;
  hwndCur = g_forcedDropTarget._hwndFDTCurrent;
  if ( this->m_backgroundContainerDrag )
  {
    if ( !g_forcedDropTarget._hwndFDTCurrent )
    {
      this->_hrDragResult = 262401;
      goto LABEL_11;
    }
    cpt = this->_cpt;
    v31 = SetThreadDpiAwarenessContext(-3);
    v32 = hwndCur;
    v33 = v31;
    while ( 1 )
    {
      v34 = RealChildWindowFromPoint(v32, cpt._pt);
      if ( !v34 || v34 == hwndCur )
        break;
      hwndCur = v34;
      v32 = v34;
    }
    v4 = v33;
    goto LABEL_7;
  }
  if ( IsContainerDragOperation() )
  {
    Microsoft::WRL::ComPtr<IDropTarget>::operator=(&nonRPCSSRegisteredDropTarget, &this->m_nonRPCSSRegisteredDropTarget);
    goto LABEL_8;
  }
  if ( !hwndCur )
  {
    point = (tagPOINT)this->_cpt;
    luid = 0;
    v3 = SetThreadDpiAwarenessContext(-3);
    memset_0(&transform, 0, sizeof(transform));
    if ( !(unsigned int)CompositionInputSinkLuidFromPoint(6, &point, &luid, &hwndCur, &transform) )
      hwndCur = WindowFromPoint(point);
    v4 = v3;
LABEL_7:
    SetThreadDpiAwarenessContext(v4);
  }
LABEL_8:
  pDropSource = this->_pDropSource;
  v6 = 0;
  v51 = 0;
  if ( pDropSource )
  {
    v7 = ((__int64 (__fastcall *)(IDropSource *, _QWORD, _QWORD))pDropSource->lpVtbl[1].QueryInterface)(
           pDropSource,
           (unsigned int)this->_fEscapePressed,
           this->_grfKeyState);
    v51 = v7;
    v6 = v7;
    if ( v7 < 0 || v7 == 262401 )
      goto LABEL_10;
  }
  if ( !IsContainerDragOperation() || this->m_backgroundContainerDrag )
  {
LABEL_16:
    hwndLast = this->_hwndLast;
    v8 = 1;
    if ( hwndCur == hwndLast )
    {
LABEL_17:
      if ( !v6 )
        goto $UpdateTarget_exit;
      this->_hrDragResult = v6;
LABEL_11:
      v8 = 0;
      goto $UpdateTarget_exit;
    }
    PropW = 0;
    point = 0;
    proxy.ptr_ = 0;
    v13 = 0;
    luid = 0;
    dwCurrentProcessId = 0;
    if ( hwndLast != (HWND__ *)-1LL )
      GetWindowThreadProcessId(hwndLast, &dwCurrentProcessId);
    v14 = dwCurrentProcessId;
    dwTempProcessID = dwCurrentProcessId;
    if ( hwndLast )
    {
      while ( !PropW && hwndLast != (HWND__ *)-1LL && v14 == dwCurrentProcessId )
      {
        PropW = GetPropW(hwndLast, (LPCWSTR)g_aDropTarget);
        v36 = (tagPOINT)hwndLast;
        if ( !PropW )
          v36 = v1;
        v1 = v36;
        point = v36;
        Parent = GetParent(hwndLast);
        hwndLast = Parent;
        if ( !Parent )
        {
          point = v1;
          break;
        }
        GetWindowThreadProcessId(Parent, &dwTempProcessID);
        v14 = dwTempProcessID;
      }
    }
    v15 = hwndCur;
    if ( hwndCur != (HWND__ *)-1LL )
      GetWindowThreadProcessId(hwndCur, &dwCurrentProcessId);
    v16 = dwCurrentProcessId;
    dwTempProcessID = dwCurrentProcessId;
    if ( v15 )
    {
      v17 = 0;
      while ( v16 == dwCurrentProcessId )
      {
        if ( !v13 && !nonRPCSSRegisteredDropTarget.ptr_ )
        {
          v20 = (const wchar_t *)g_aDropTarget;
          this->m_isTargetWinRt = 0;
          v13 = GetPropW(v15, v20);
          if ( v13 )
          {
            proxy.ptr_ = (IDragDropContainerProxy *)v15;
          }
          else
          {
            spExtension.ptr_ = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&spExtension);
            if ( CDragOperation::GetWinRtExtension(this, &spExtension.ptr_) >= 0 )
            {
              ptr = spExtension.ptr_;
              Release = spExtension.ptr_->lpVtbl[1].Release;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&nonRPCSSRegisteredDropTarget);
              if ( ((int (__fastcall *)(IDragDropExtensionForOLE *, HWND__ *, wchar_t *, Microsoft::WRL::ComPtr<IDropTarget> *))Release)(
                     ptr,
                     v15,
                     this->m_sourceEnterpriseId.m_ptr,
                     &nonRPCSSRegisteredDropTarget) >= 0 )
              {
                proxy.ptr_ = (IDragDropContainerProxy *)v15;
                this->m_isTargetWinRt = 1;
                CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
                SetCursor(CursorW);
              }
            }
            v23 = spExtension.ptr_;
            if ( spExtension.ptr_ )
            {
              spExtension.ptr_ = 0;
              ((void (__fastcall *)(IDragDropExtensionForOLE *))v23->lpVtbl->Release)(v23);
            }
          }
        }
        if ( !v17
          && (GetWindowLongW(v15, -20) & 0x10) != 0
          && (GetWindowLongW(v15, -16) & 0x8000000) == 0
          && this->m_hasHDROPClipboardFormat )
        {
          pDropTargetAdapter = this->_pDropTargetAdapter;
          v17 = 1;
          luid = (_LUID)v15;
          if ( pDropTargetAdapter )
            pDropTargetAdapter->_hwnd31 = v15;
        }
        if ( (v13 || nonRPCSSRegisteredDropTarget.ptr_) && (!this->m_hasHDROPClipboardFormat || v17) )
          break;
        v18 = GetParent(v15);
        v15 = v18;
        if ( !v18 )
          break;
        GetWindowThreadProcessId(v18, &dwTempProcessID);
        v16 = dwTempProcessID;
      }
      v6 = v51;
    }
    v24 = proxy.ptr_;
    if ( v13 == this->m_dropTargetFromWindowProperty )
    {
      v39 = this->m_nonRPCSSRegisteredDropTarget.ptr_;
      if ( nonRPCSSRegisteredDropTarget.ptr_ == v39
        && this->_hwndLast != (HWND__ *)-1LL
        && proxy.ptr_ == *(IDragDropContainerProxy **)&point
        && (this->m_dropTargetFromWindowProperty || v39) )
      {
        this->_hwndLast = hwndCur;
        goto LABEL_17;
      }
    }
    OleDragDropTracing::CDragOperation_DropTargetChanged(dwCurrentProcessId);
    if ( this->_hwndLast != (HWND__ *)-1LL )
    {
      pDSNotify = this->_pDSNotify;
      if ( pDSNotify )
        ((void (__fastcall *)(IDropSourceNotify *))pDSNotify->lpVtbl[1].AddRef)(pDSNotify);
    }
    v25 = nonRPCSSRegisteredDropTarget.ptr_;
    this->_hwndLast = hwndCur;
    this->m_dropTargetFromWindowProperty = v13;
    if ( this->m_nonRPCSSRegisteredDropTarget.ptr_ != v25 )
    {
      point = (tagPOINT)v25;
      Microsoft::WRL::ComPtr<IDataObject>::InternalAddRef((Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> > *)&point);
      point = (tagPOINT)this->m_nonRPCSSRegisteredDropTarget.ptr_;
      this->m_nonRPCSSRegisteredDropTarget.ptr_ = v25;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&point);
    }
    if ( dwCurrentProcessId )
      AllowSetForegroundWindow(dwCurrentProcessId);
    v26 = this->_pDropTargetAdapter;
    v27 = 1;
    if ( v26 )
    {
      v27 = 0;
      CDropTargetAdapter::DragLeave(v26);
      v42 = this->_pDropTargetAdapter;
      if ( v42 )
        CDropTargetAdapter::`scalar deleting destructor'(v42, v41);
      this->_pDropTargetAdapter = 0;
    }
    *this->_pdwEffect = this->_dwOKEffects;
    v28 = this->_pDSNotify;
    if ( v28 )
      ((void (__fastcall *)(IDropSourceNotify *, HWND__ *))v28->lpVtbl[1].QueryInterface)(v28, this->_hwndLast);
    DropTarget = CDragOperation::GetDropTarget(
                   this,
                   *(HWND__ **)&luid,
                   (HWND__ *)v24,
                   nonRPCSSRegisteredDropTarget.ptr_);
    if ( this->_pDropTargetAdapter )
    {
      if ( !CDragOperation::HandleFeedBack(this, DropTarget) )
        goto $UpdateTarget_exit;
      goto LABEL_17;
    }
    *this->_pdwEffect = 0;
    v43 = this->_pDropSource;
    if ( !v43
      || (v7 = ((__int64 (__fastcall *)(IDropSource *, _QWORD))v43->lpVtbl[1].AddRef)(v43, *this->_pdwEffect)) == 0
      || this->_fWinRTDrag
      || this->m_isTargetWinRt )
    {
LABEL_102:
      if ( v27 && !this->_fWinRTDrag && !this->m_isTargetWinRt )
        SetCursor(this->_pcddcDefault->ahcursorDefaults[0][0]);
      goto LABEL_17;
    }
    if ( v7 == 262402 )
    {
      SetCursor(this->_pcddcDefault->ahcursorDefaults[0][0]);
      goto LABEL_102;
    }
LABEL_10:
    this->_hrDragResult = v7;
    goto LABEL_11;
  }
  proxy.ptr_ = 0;
  if ( (int)Microsoft::WRL::ComPtr<IDropTarget>::As<IDragDropContainerProxy>(
              &this->m_nonRPCSSRegisteredDropTarget,
              (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDragDropContainerProxy> >)&proxy) < 0
    || (dwTempProcessID = 0,
        v35 = ((__int64 (__fastcall *)(IDragDropContainerProxy *, unsigned int *))proxy.ptr_->lpVtbl[1].Release)(
                proxy.ptr_,
                &dwTempProcessID),
        v35 < 0) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&proxy);
    goto LABEL_16;
  }
  v8 = 0;
  *this->_pdwEffect = dwTempProcessID;
  this->_hrDragResult = v35;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&proxy);
$UpdateTarget_exit:
  v9 = nonRPCSSRegisteredDropTarget.ptr_;
  if ( nonRPCSSRegisteredDropTarget.ptr_ )
  {
    nonRPCSSRegisteredDropTarget.ptr_ = 0;
    ((void (__fastcall *)(IDropTarget *))v9->lpVtbl->Release)(v9);
  }
  return v8;
}

```

## disassembly

```asm
0x18000bd4c  push    rbp
0x18000bd4e  push    rbx
0x18000bd4f  push    rsi
0x18000bd50  push    rdi
0x18000bd51  push    r12
0x18000bd53  push    r13
0x18000bd55  push    r14
0x18000bd57  push    r15
0x18000bd59  lea     rbp, [rsp-1Fh]
0x18000bd5e  sub     rsp, 0C8h
0x18000bd65  mov     rax, cs:__security_cookie
0x18000bd6c  xor     rax, rsp
0x18000bd6f  mov     [rbp+57h+var_50], rax
0x18000bd73  mov     rax, cs:?g_forcedDropTarget@@3VCForcedDropTarget@@A._hwndFDTCurrent; CForcedDropTarget g_forcedDropTarget ...
0x18000bd7a  xor     r14d, r14d
0x18000bd7d  mov     rsi, this
0x18000bd80  mov     [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_], r14
0x18000bd84  mov     [rbp+57h+hwndCur], rax
0x18000bd88  cmp     [this+249h], r14b
0x18000bd8f  jnz     loc_18000C100
0x18000bd95  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x18000bd9a  test    al, al
0x18000bd9c  jnz     loc_18000C151
0x18000bda2  cmp     [rbp+57h+hwndCur], r14
0x18000bda6  jnz     short loc_18000BE0A
0x18000bda8  mov     rax, [rsi+50h]
0x18000bdac  lea     this, [r14-3]
0x18000bdb0  mov     qword ptr [rbp+57h+point.x], rax
0x18000bdb4  call    cs:__imp_SetThreadDpiAwarenessContext
0x18000bdba  xor     edx, edx; Val
0x18000bdbc  mov     qword ptr [rbp+57h+luid.LowPart], r14
0x18000bdc0  lea     r8d, [r14+40h]; Size
0x18000bdc4  mov     rbx, rax
0x18000bdc7  lea     this, [rbp+57h+transform]; void *
0x18000bdcb  call    memset_0
0x18000bdd0  lea     rax, [rbp+57h+transform]
0x18000bdd4  lea     r9, [rbp+57h+hwndCur]
0x18000bdd8  mov     [rsp+100h+var_E0], rax
0x18000bddd  lea     r8, [rbp+57h+luid]
0x18000bde1  lea     rdx, [rbp+57h+point]
0x18000bde5  lea     ecx, [r14+6]
0x18000bde9  call    cs:__imp_CompositionInputSinkLuidFromPoint
0x18000bdef  test    eax, eax
0x18000bdf1  jnz     short loc_18000BE01
0x18000bdf3  mov     this, qword ptr [rbp+57h+point.x]; Point
0x18000bdf7  call    cs:__imp_WindowFromPoint
0x18000bdfd  mov     [rbp+57h+hwndCur], rax
0x18000be01  mov     this, rbx
0x18000be04  call    cs:__imp_SetThreadDpiAwarenessContext
0x18000be0a  mov     this, [rsi+20h]
0x18000be0e  mov     r12d, r14d
0x18000be11  mov     [rbp+57h+var_A0], r14d
0x18000be15  test    this, this
0x18000be18  jz      short loc_18000BE7F
0x18000be1a  mov     rax, [this]
0x18000be1d  mov     r8d, [rsi+80h]
0x18000be24  mov     edx, [rsi+68h]
0x18000be27  mov     rax, [rax+18h]
0x18000be2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be30  mov     [rbp+57h+var_A0], eax
0x18000be33  mov     r12d, eax
0x18000be36  test    eax, eax
0x18000be38  jns     short loc_18000BEAA
0x18000be3a  mov     [rsi+84h], eax
0x18000be40  mov     r15d, r14d
0x18000be43  mov     this, [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_]
0x18000be47  test    this, this
0x18000be4a  jz      short loc_18000BE5C
0x18000be4c  mov     [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_], r14
0x18000be50  mov     rdx, [this]
0x18000be53  mov     rax, [rdx+10h]
0x18000be57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be5c  mov     eax, r15d
0x18000be5f  mov     this, [rbp+57h+var_50]
0x18000be63  xor     this, rsp; StackCookie
0x18000be66  call    __security_check_cookie
0x18000be6b  add     rsp, 0C8h
0x18000be72  pop     r15
0x18000be74  pop     r14
0x18000be76  pop     r13
0x18000be78  pop     r12
0x18000be7a  pop     rdi
0x18000be7b  pop     rsi
0x18000be7c  pop     rbx
0x18000be7d  pop     rbp
0x18000be7e  retn
0x18000be7f  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x18000be84  test    al, al
0x18000be86  jnz     loc_18000C163
0x18000be8c  mov     rbx, [rsi+78h]
0x18000be90  mov     r15d, 1
0x18000be96  cmp     [rbp+57h+hwndCur], rbx
0x18000be9a  jnz     short loc_18000BEB3
0x18000be9c  test    r12d, r12d
0x18000be9f  jz      short $UpdateTarget_exit
0x18000bea1  mov     [rsi+84h], r12d
0x18000bea8  jmp     short loc_18000BE40
0x18000beaa  cmp     eax, 40101h
0x18000beaf  jz      short loc_18000BE3A
0x18000beb1  jmp     short loc_18000BE7F
0x18000beb3  xor     edi, edi
0x18000beb5  mov     qword ptr [rbp+57h+point.x], r14
0x18000beb9  mov     [rbp+57h+proxy.ptr_], r14
0x18000bebd  mov     r13, r14
0x18000bec0  mov     qword ptr [rbp+57h+luid.LowPart], r14
0x18000bec4  mov     [rbp+57h+dwCurrentProcessId], r13d
0x18000bec8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000becc  jnz     loc_18000C1D1
0x18000bed2  mov     eax, [rbp+57h+dwCurrentProcessId]
0x18000bed5  mov     [rbp+57h+dwTempProcessID], eax
0x18000bed8  test    rbx, rbx
0x18000bedb  jnz     loc_18000C1E3
0x18000bee1  mov     r14, [rbp+57h+hwndCur]
0x18000bee5  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18000bee9  jnz     loc_18000C24F
0x18000beef  mov     eax, [rbp+57h+dwCurrentProcessId]
0x18000bef2  xor     ebx, ebx
0x18000bef4  mov     [rbp+57h+dwTempProcessID], eax
0x18000bef7  test    r14, r14
0x18000befa  jz      loc_18000C054
0x18000bf00  mov     r12d, ebx
0x18000bf03  cmp     eax, [rbp+57h+dwCurrentProcessId]
0x18000bf06  jnz     loc_18000C050
0x18000bf0c  test    r13, r13
0x18000bf0f  jz      loc_18000BFAE
0x18000bf15  test    r12d, r12d
0x18000bf18  jz      short loc_18000BF63
0x18000bf1a  test    r13, r13
0x18000bf1d  jz      short loc_18000BF5B
0x18000bf1f  cmp     [rsi+98h], bl
0x18000bf25  jz      loc_18000C050
0x18000bf2b  test    r12d, r12d
0x18000bf2e  jnz     loc_18000C050
0x18000bf34  mov     this, r14; hWnd
0x18000bf37  call    cs:__imp_GetParent
0x18000bf3d  mov     r14, rax
0x18000bf40  test    rax, rax
0x18000bf43  jz      loc_18000C050
0x18000bf49  lea     rdx, [rbp+57h+dwTempProcessID]; lpdwProcessId
0x18000bf4d  mov     this, rax; hWnd
0x18000bf50  call    cs:__imp_GetWindowThreadProcessId
0x18000bf56  mov     eax, [rbp+57h+dwTempProcessID]
0x18000bf59  jmp     short loc_18000BF03
0x18000bf5b  cmp     [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_], rbx
0x18000bf5f  jz      short loc_18000BF34
0x18000bf61  jmp     short loc_18000BF1F
0x18000bf63  mov     edx, 0FFFFFFECh; nIndex
0x18000bf68  mov     this, r14; hWnd
0x18000bf6b  call    cs:__imp_GetWindowLongW
0x18000bf71  test    al, 10h
0x18000bf73  jz      short loc_18000BF1A
0x18000bf75  mov     edx, 0FFFFFFF0h; nIndex
0x18000bf7a  mov     this, r14; hWnd
0x18000bf7d  call    cs:__imp_GetWindowLongW
0x18000bf83  bt      eax, 1Bh
0x18000bf87  jb      short loc_18000BF1A
0x18000bf89  cmp     [rsi+98h], bl
0x18000bf8f  jz      short loc_18000BF1A
0x18000bf91  mov     rax, [rsi+30h]
0x18000bf95  mov     r12d, r15d
0x18000bf98  mov     qword ptr [rbp+57h+luid.LowPart], r14
0x18000bf9c  test    rax, rax
0x18000bf9f  jz      loc_18000BF1A
0x18000bfa5  mov     [rax+8], r14
0x18000bfa9  jmp     loc_18000BF1A
0x18000bfae  cmp     [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_], rbx
0x18000bfb2  jnz     loc_18000BF15
0x18000bfb8  movzx   edx, cs:?g_aDropTarget@@3GA; lpString
0x18000bfbf  mov     this, r14; hWnd
0x18000bfc2  mov     [rsi+231h], bl
0x18000bfc8  call    cs:__imp_GetPropW
0x18000bfce  mov     r13, rax
0x18000bfd1  test    rax, rax
0x18000bfd4  jnz     loc_18000C0F7
0x18000bfda  lea     this, [rbp+57h+spExtension]; this
0x18000bfde  mov     [rbp+57h+spExtension.ptr_], rbx
0x18000bfe2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000bfe7  lea     rdx, [rbp+57h+spExtension]; ppExtension
0x18000bfeb  mov     this, rsi; this
0x18000bfee  call    ?GetWinRtExtension@CDragOperation@@AEAAJPEAPEAUIDragDropExtensionForOLE@@@Z; CDragOperation::GetWinRtExtension(IDragDropExtensionForOLE * *)
0x18000bff3  test    eax, eax
0x18000bff5  js      short loc_18000C02E
0x18000bff7  mov     rdi, [rbp+57h+spExtension.ptr_]
0x18000bffb  lea     this, [rbp+57h+nonRPCSSRegisteredDropTarget]; this
0x18000bfff  mov     rax, [rdi]
0x18000c002  mov     rbx, [rax+28h]
0x18000c006  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c00b  mov     r8, [rsi+238h]
0x18000c012  lea     r9, [rbp+57h+nonRPCSSRegisteredDropTarget]
0x18000c016  mov     rdx, r14
0x18000c019  mov     this, rdi
0x18000c01c  mov     rax, rbx
0x18000c01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c024  xor     ebx, ebx
0x18000c026  test    eax, eax
0x18000c028  jns     loc_18000C261
0x18000c02e  mov     this, [rbp+57h+spExtension.ptr_]
0x18000c032  test    this, this
0x18000c035  jz      loc_18000BF15
0x18000c03b  mov     [rbp+57h+spExtension.ptr_], rbx
0x18000c03f  mov     rax, [this]
0x18000c042  mov     rax, [rax+10h]
0x18000c046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c04b  jmp     loc_18000BF15
0x18000c050  mov     r12d, [rbp+57h+var_A0]
0x18000c054  mov     rdi, [rbp+57h+proxy.ptr_]
0x18000c058  xor     r14d, r14d
0x18000c05b  cmp     r13, [rsi+38h]
0x18000c05f  jz      loc_18000C287
0x18000c065  mov     ecx, [rbp+57h+dwCurrentProcessId]; processId
0x18000c068  call    ?CDragOperation_DropTargetChanged@OleDragDropTracing@@SAXI@Z; OleDragDropTracing::CDragOperation_DropTargetChanged(uint)
0x18000c06d  cmp     qword ptr [rsi+78h], 0FFFFFFFFFFFFFFFFh
0x18000c072  jnz     loc_18000C2C6
0x18000c078  mov     rax, [rbp+57h+hwndCur]
0x18000c07c  mov     rbx, [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_]
0x18000c080  mov     [rsi+78h], rax
0x18000c084  mov     [rsi+38h], r13
0x18000c088  cmp     [rsi+40h], rbx
0x18000c08c  jnz     loc_18000C2E4
0x18000c092  mov     ecx, [rbp+57h+dwCurrentProcessId]; dwProcessId
0x18000c095  test    ecx, ecx
0x18000c097  jnz     loc_18000C30B
0x18000c09d  mov     this, [rsi+30h]; this
0x18000c0a1  mov     ebx, r15d
0x18000c0a4  test    this, this
0x18000c0a7  jnz     loc_18000C316
0x18000c0ad  mov     this, [rsi+60h]
0x18000c0b1  mov     eax, [rsi+58h]
0x18000c0b4  mov     [this], eax
0x18000c0b6  mov     this, [rsi+28h]
0x18000c0ba  test    this, this
0x18000c0bd  jnz     loc_18000C335
0x18000c0c3  mov     r9, [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_]; nonRPCSSRegisteredDropTarget
0x18000c0c7  mov     r8, rdi; hwndDropTarget
0x18000c0ca  mov     rdx, qword ptr [rbp+57h+luid.LowPart]; hwnd31
0x18000c0ce  mov     this, rsi; this
0x18000c0d1  call    ?GetDropTarget@CDragOperation@@AEAAJPEAUHWND__@@0PEAUIDropTarget@@@Z; CDragOperation::GetDropTarget(HWND__ *,HWND__ *,IDropTarget *)
0x18000c0d6  cmp     [rsi+30h], r14
0x18000c0da  jz      loc_18000C34A
0x18000c0e0  mov     edx, eax; hr
0x18000c0e2  mov     this, rsi; this
0x18000c0e5  call    ?HandleFeedBack@CDragOperation@@QEAAHJ@Z; CDragOperation::HandleFeedBack(long)
0x18000c0ea  test    eax, eax
0x18000c0ec  jz      $UpdateTarget_exit
0x18000c0f2  jmp     loc_18000BE9C
0x18000c0f7  mov     [rbp+57h+proxy.ptr_], r14
0x18000c0fb  jmp     loc_18000BF15
0x18000c100  test    rax, rax
0x18000c103  jnz     short loc_18000C114
0x18000c105  mov     dword ptr [this+84h], 40101h
0x18000c10f  jmp     loc_18000BE40
0x18000c114  mov     rbx, [this+50h]
0x18000c118  mov     this, 0FFFFFFFFFFFFFFFDh
0x18000c11f  call    cs:__imp_SetThreadDpiAwarenessContext
0x18000c125  mov     this, [rbp+57h+hwndCur]
0x18000c129  mov     rdi, rax
0x18000c12c  jmp     short loc_18000C13B
0x18000c12e  cmp     rax, [rbp+57h+hwndCur]
0x18000c132  jz      short loc_18000C149
0x18000c134  mov     [rbp+57h+hwndCur], rax
0x18000c138  mov     this, rax; hwndParent
0x18000c13b  mov     rdx, rbx; ptParentClientCoords
0x18000c13e  call    cs:__imp_RealChildWindowFromPoint
0x18000c144  test    rax, rax
0x18000c147  jnz     short loc_18000C12E
0x18000c149  mov     this, rdi
0x18000c14c  jmp     loc_18000BE04
0x18000c151  lea     rdx, [rsi+40h]; other
0x18000c155  lea     this, [rbp+57h+nonRPCSSRegisteredDropTarget]; this
0x18000c159  call    ??4?$ComPtr@UIDropTarget@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IDropTarget>::operator=(Microsoft::WRL::ComPtr<IDropTarget> const &)
0x18000c15e  jmp     loc_18000BE0A
0x18000c163  cmp     [rsi+249h], r14b
0x18000c16a  jnz     loc_18000BE8C
0x18000c170  lea     this, [rsi+40h]; this
0x18000c174  mov     [rbp+57h+proxy.ptr_], r14
0x18000c178  lea     rdx, [rbp+57h+proxy]; p
0x18000c17c  call    ??$As@UIDragDropContainerProxy@@@?$ComPtr@UIDropTarget@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDragDropContainerProxy@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IDropTarget>::As<IDragDropContainerProxy>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDragDropContainerProxy>>)
0x18000c181  test    eax, eax
0x18000c183  js      short loc_18000C1C3
0x18000c185  mov     this, [rbp+57h+proxy.ptr_]
0x18000c189  lea     rdx, [rbp+57h+dwTempProcessID]
0x18000c18d  mov     [rbp+57h+dwTempProcessID], r14d
0x18000c191  mov     rax, [this]
0x18000c194  mov     rax, [rax+28h]
0x18000c198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c19d  mov     edx, eax
0x18000c19f  test    eax, eax
0x18000c1a1  js      short loc_18000C1C3
0x18000c1a3  mov     this, [rsi+60h]
0x18000c1a7  mov     r15d, r14d
0x18000c1aa  mov     eax, [rbp+57h+dwTempProcessID]
0x18000c1ad  mov     [this], eax
0x18000c1af  lea     this, [rbp+57h+proxy]; this
0x18000c1b3  mov     [rsi+84h], edx
0x18000c1b9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c1be  jmp     $UpdateTarget_exit
0x18000c1c3  lea     this, [rbp+57h+proxy]; this
0x18000c1c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c1cc  jmp     loc_18000BE8C
0x18000c1d1  lea     rdx, [rbp+57h+dwCurrentProcessId]; lpdwProcessId
  ... truncated ...
```
