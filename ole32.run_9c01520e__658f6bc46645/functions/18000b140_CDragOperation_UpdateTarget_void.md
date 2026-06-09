# CDragOperation::UpdateTarget(void)

- ea: `0x18000b140`
- end: `0x18000b851`
- name: `?UpdateTarget@CDragOperation@@QEAAHXZ`
- size: `1809`
- prototype: `int __fastcall(CDragOperation *this)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000aaf0`
- `0x180094350`

## callees

- `0x1800085a8`
- `0x18000a690`
- `0x18000b140`
- `0x18000b894`
- `0x18000be18`
- `0x18000cf64`
- `0x18003674c`
- `0x18003967c`
- `0x1800423f8`
- `0x180043524`
- `0x180044db0`
- `0x18004516c`
- `0x180046460`
- `0x180047484`
- `0x18009217c`
- `0x1800d8010`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x18000b37e`
- `USER32!GetWindowThreadProcessId` at `0x18000b64b`
- `USER32!GetWindowThreadProcessId` at `0x18000b6c0`
- `USER32!GetWindowThreadProcessId` at `0x18000b6d8`
- `USER32!GetWindowThreadProcessId` at `0x18000b37e`
- `USER32!GetWindowThreadProcessId` at `0x18000b64b`
- `USER32!GetWindowThreadProcessId` at `0x18000b6c0`
- `USER32!GetWindowThreadProcessId` at `0x18000b6d8`
- `USER32!GetPropW` at `0x18000b3e0`
- `USER32!GetPropW` at `0x18000b682`
- `USER32!GetPropW` at `0x18000b3e0`
- `USER32!GetPropW` at `0x18000b682`
- `USER32!SetCursor` at `0x18000b556`
- `USER32!SetCursor` at `0x18000b70a`
- `USER32!SetCursor` at `0x18000b840`
- `USER32!SetCursor` at `0x18000b556`
- `USER32!SetCursor` at `0x18000b70a`
- `USER32!SetCursor` at `0x18000b840`
- `USER32!LoadCursorW` at `0x18000b6fb`
- `USER32!LoadCursorW` at `0x18000b6fb`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000b1bc`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000b21e`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000b586`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000b1bc`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000b21e`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000b586`
- `USER32!RealChildWindowFromPoint` at `0x18000b5ab`
- `USER32!RealChildWindowFromPoint` at `0x18000b5ab`
- `USER32!WindowFromPoint` at `0x18000b20b`
- `USER32!WindowFromPoint` at `0x18000b20b`
- `USER32!GetParent` at `0x18000b35f`
- `USER32!GetParent` at `0x18000b6a1`
- `USER32!GetParent` at `0x18000b35f`
- `USER32!GetParent` at `0x18000b6a1`
- `USER32!AllowSetForegroundWindow` at `0x18000b79e`
- `USER32!AllowSetForegroundWindow` at `0x18000b79e`
- `USER32!__imp_CompositionInputSinkLuidFromPoint` at `0x18000b1f7`
- `USER32!__imp_CompositionInputSinkLuidFromPoint` at `0x18000b1f7`

## pseudocode

```c
__int64 __fastcall CDragOperation::UpdateTarget(CDragOperation *this)
{
  unsigned int v2; // r15d
  __int64 v3; // rbx
  __int64 v4; // rcx
  IDropSource *pDropSource; // rcx
  HRESULT LowPart; // r12d
  int v7; // eax
  ITypeLibRegistrationReader *v8; // rcx
  HWND__ *hwndLast; // rbx
  HWND__ *v11; // r13
  HANDLE PropW; // rdi
  int ptr_high; // eax
  HWND__ *v14; // r14
  int v15; // eax
  IDragDropExtensionForOLE *v16; // rbx
  int v17; // r12d
  HWND v18; // rax
  CDropTargetAdapter *pDropTargetAdapter; // rax
  const wchar_t *v20; // rdx
  ITypeLibRegistrationReader *v21; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // rdi
  ITypeLibRegistrationReader *v23; // rcx
  IDragDropExtensionForOLE *v24; // rbx
  HWND__ *v25; // rdi
  HWND__ *v26; // rax
  IDragDropExtensionForOLE *v27; // rbx
  CDropTargetAdapter *v28; // rcx
  int v29; // ebx
  IDropSourceNotify *v30; // rcx
  HRESULT DropTarget; // eax
  CPoint cpt; // rbx
  __int64 v33; // rax
  IDropTarget *ptr; // rcx
  __int64 v35; // rdi
  IDropTarget *v36; // rax
  HRESULT v37; // edx
  HWND__ *v38; // rax
  HWND Parent; // rax
  HCURSOR CursorW; // rax
  IDropTarget *v41; // rax
  IDropSourceNotify *pDSNotify; // rcx
  unsigned int v43; // edx
  CDropTargetAdapter *v44; // rcx
  IDropSource *v45; // rcx
  Microsoft::WRL::ComPtr<IDragDropContainerProxy> proxy; // [rsp+38h] [rbp-59h] BYREF
  HWND__ *hwndCur; // [rsp+40h] [rbp-51h] BYREF
  Microsoft::WRL::ComPtr<IDropTarget> nonRPCSSRegisteredDropTarget; // [rsp+48h] [rbp-49h] BYREF
  Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> v49; // [rsp+50h] [rbp-41h] BYREF
  Microsoft::WRL::ComPtr<IDragDropExtensionForOLE> spExtension; // [rsp+58h] [rbp-39h] BYREF
  Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> v51; // [rsp+60h] [rbp-31h] BYREF
  _LUID luid; // [rsp+68h] [rbp-29h]
  tagINPUT_TRANSFORM transform; // [rsp+70h] [rbp-21h] BYREF

  v2 = 1;
  v49.ptr_ = 0;
  spExtension.ptr_ = 0;
  nonRPCSSRegisteredDropTarget.ptr_ = (IDropTarget *)g_forcedDropTarget._hwndFDTCurrent;
  if ( this->m_backgroundContainerDrag )
  {
    if ( !g_forcedDropTarget._hwndFDTCurrent )
    {
      this->_hrDragResult = 262401;
      goto LABEL_11;
    }
    cpt = this->_cpt;
    v33 = SetThreadDpiAwarenessContext(-3);
    ptr = nonRPCSSRegisteredDropTarget.ptr_;
    v35 = v33;
    while ( 1 )
    {
      v36 = (IDropTarget *)RealChildWindowFromPoint((HWND)ptr, cpt._pt);
      if ( !v36 || v36 == nonRPCSSRegisteredDropTarget.ptr_ )
        break;
      nonRPCSSRegisteredDropTarget.ptr_ = v36;
      ptr = v36;
    }
    v4 = v35;
    goto LABEL_7;
  }
  if ( IsContainerDragOperation() )
  {
    Microsoft::WRL::ComPtr<IDropTarget>::operator=(
      (Microsoft::WRL::ComPtr<IDropTarget> *)&v49,
      &this->m_nonRPCSSRegisteredDropTarget);
    goto LABEL_8;
  }
  if ( !nonRPCSSRegisteredDropTarget.ptr_ )
  {
    hwndCur = (HWND__ *)this->_cpt;
    *(_QWORD *)&transform._11 = 0;
    v3 = SetThreadDpiAwarenessContext(-3);
    memset_0(&transform.m[0][2], 0, sizeof(tagINPUT_TRANSFORM));
    if ( !(unsigned int)CompositionInputSinkLuidFromPoint(
                          6,
                          &hwndCur,
                          &transform,
                          &nonRPCSSRegisteredDropTarget,
                          &transform.m[0][2]) )
      nonRPCSSRegisteredDropTarget.ptr_ = (IDropTarget *)WindowFromPoint((POINT)hwndCur);
    v4 = v3;
LABEL_7:
    SetThreadDpiAwarenessContext(v4);
  }
LABEL_8:
  pDropSource = this->_pDropSource;
  LowPart = 0;
  luid.LowPart = 0;
  if ( pDropSource )
  {
    v7 = ((__int64 (__fastcall *)(IDropSource *, _QWORD, _QWORD))pDropSource->lpVtbl[1].QueryInterface)(
           pDropSource,
           (unsigned int)this->_fEscapePressed,
           this->_grfKeyState);
    luid.LowPart = v7;
    LowPart = v7;
    if ( v7 < 0 || v7 == 262401 )
      goto LABEL_10;
  }
  if ( !IsContainerDragOperation() || this->m_backgroundContainerDrag )
  {
LABEL_16:
    hwndLast = this->_hwndLast;
    if ( (HWND__ *)nonRPCSSRegisteredDropTarget.ptr_ == hwndLast )
    {
LABEL_17:
      if ( !LowPart )
        goto $UpdateTarget_exit;
      this->_hrDragResult = LowPart;
LABEL_11:
      v2 = 0;
      goto $UpdateTarget_exit;
    }
    hwndCur = 0;
    v11 = 0;
    *(_QWORD *)&transform._11 = 0;
    PropW = 0;
    LODWORD(proxy.ptr_) = 0;
    if ( hwndLast != (HWND__ *)-1LL )
      GetWindowThreadProcessId(hwndLast, (LPDWORD)&proxy);
    ptr_high = (int)proxy.ptr_;
    HIDWORD(proxy.ptr_) = proxy.ptr_;
    if ( hwndLast )
    {
      while ( !PropW && hwndLast != (HWND__ *)-1LL && ptr_high == LODWORD(proxy.ptr_) )
      {
        PropW = GetPropW(hwndLast, (LPCWSTR)g_aDropTarget);
        v38 = hwndLast;
        if ( !PropW )
          v38 = v11;
        v11 = v38;
        Parent = GetParent(hwndLast);
        hwndLast = Parent;
        if ( !Parent )
          break;
        GetWindowThreadProcessId(Parent, (LPDWORD)&proxy.ptr_ + 1);
        ptr_high = HIDWORD(proxy.ptr_);
      }
    }
    v14 = (HWND__ *)nonRPCSSRegisteredDropTarget.ptr_;
    if ( nonRPCSSRegisteredDropTarget.ptr_ != (IDropTarget *)-1LL )
      GetWindowThreadProcessId((HWND)nonRPCSSRegisteredDropTarget.ptr_, (LPDWORD)&proxy);
    v15 = (int)proxy.ptr_;
    HIDWORD(proxy.ptr_) = proxy.ptr_;
    if ( v14 )
    {
      v16 = 0;
      v17 = 0;
      while ( v15 == LODWORD(proxy.ptr_) )
      {
        if ( !v16 && !v49.ptr_ )
        {
          v20 = (const wchar_t *)g_aDropTarget;
          this->m_isTargetWinRt = 0;
          spExtension.ptr_ = (IDragDropExtensionForOLE *)GetPropW(v14, v20);
          v16 = spExtension.ptr_;
          if ( spExtension.ptr_ )
          {
            hwndCur = v14;
          }
          else
          {
            v51.ptr_ = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
            if ( CDragOperation::GetWinRtExtension(this, (IDragDropExtensionForOLE **)&v51) >= 0 )
            {
              v21 = v51.ptr_;
              Release = v51.ptr_->lpVtbl[1].Release;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
              if ( ((int (__fastcall *)(ITypeLibRegistrationReader *, HWND__ *, wchar_t *, Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *))Release)(
                     v21,
                     v14,
                     this->m_sourceEnterpriseId.m_ptr,
                     &v49) >= 0 )
              {
                hwndCur = v14;
                this->m_isTargetWinRt = 1;
                CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
                SetCursor(CursorW);
              }
              v16 = spExtension.ptr_;
            }
            v23 = v51.ptr_;
            if ( v51.ptr_ )
            {
              v51.ptr_ = 0;
              ((void (__fastcall *)(ITypeLibRegistrationReader *))v23->lpVtbl->Release)(v23);
            }
          }
        }
        if ( !v17 )
        {
          if ( IsWin31DropTarget(v14) )
          {
            if ( this->m_hasHDROPClipboardFormat )
            {
              pDropTargetAdapter = this->_pDropTargetAdapter;
              v17 = 1;
              *(_QWORD *)&transform._11 = v14;
              if ( pDropTargetAdapter )
                pDropTargetAdapter->_hwnd31 = v14;
            }
          }
        }
        if ( (v16 || v49.ptr_) && (!this->m_hasHDROPClipboardFormat || v17) )
          break;
        v18 = GetParent(v14);
        v14 = v18;
        if ( !v18 )
          break;
        GetWindowThreadProcessId(v18, (LPDWORD)&proxy.ptr_ + 1);
        v15 = HIDWORD(proxy.ptr_);
      }
      LowPart = luid.LowPart;
    }
    v24 = spExtension.ptr_;
    v25 = hwndCur;
    if ( spExtension.ptr_ == this->m_dropTargetFromWindowProperty )
    {
      v41 = this->m_nonRPCSSRegisteredDropTarget.ptr_;
      if ( (IDropTarget *)v49.ptr_ == v41
        && this->_hwndLast != (HWND__ *)-1LL
        && hwndCur == v11
        && (this->m_dropTargetFromWindowProperty || v41) )
      {
        this->_hwndLast = (HWND__ *)nonRPCSSRegisteredDropTarget.ptr_;
        goto LABEL_17;
      }
    }
    OleDragDropTracing::CDragOperation_DropTargetChanged((unsigned int)proxy.ptr_);
    if ( this->_hwndLast != (HWND__ *)-1LL )
    {
      pDSNotify = this->_pDSNotify;
      if ( pDSNotify )
        ((void (__fastcall *)(IDropSourceNotify *))pDSNotify->lpVtbl[1].AddRef)(pDSNotify);
    }
    v26 = (HWND__ *)nonRPCSSRegisteredDropTarget.ptr_;
    this->m_dropTargetFromWindowProperty = v24;
    v27 = (IDragDropExtensionForOLE *)v49.ptr_;
    this->_hwndLast = v26;
    if ( (IDragDropExtensionForOLE *)this->m_nonRPCSSRegisteredDropTarget.ptr_ != v27 )
    {
      spExtension.ptr_ = v27;
      Microsoft::WRL::ComPtr<IDataObject>::InternalAddRef((Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> > *)&spExtension);
      spExtension.ptr_ = (IDragDropExtensionForOLE *)this->m_nonRPCSSRegisteredDropTarget.ptr_;
      this->m_nonRPCSSRegisteredDropTarget.ptr_ = (IDropTarget *)v27;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&spExtension);
    }
    if ( LODWORD(proxy.ptr_) )
      AllowSetForegroundWindow((DWORD)proxy.ptr_);
    v28 = this->_pDropTargetAdapter;
    v29 = 1;
    if ( v28 )
    {
      v29 = 0;
      CDropTargetAdapter::DragLeave(v28);
      v44 = this->_pDropTargetAdapter;
      if ( v44 )
        CDropTargetAdapter::`scalar deleting destructor'(v44, v43);
      this->_pDropTargetAdapter = 0;
    }
    *this->_pdwEffect = this->_dwOKEffects;
    v30 = this->_pDSNotify;
    if ( v30 )
      ((void (__fastcall *)(IDropSourceNotify *, HWND__ *))v30->lpVtbl[1].QueryInterface)(v30, this->_hwndLast);
    DropTarget = CDragOperation::GetDropTarget(this, *(HWND__ **)&transform._11, v25, (IDropTarget *)v49.ptr_);
    if ( this->_pDropTargetAdapter )
    {
      if ( !CDragOperation::HandleFeedBack(this, DropTarget) )
        goto $UpdateTarget_exit;
      goto LABEL_17;
    }
    *this->_pdwEffect = 0;
    v45 = this->_pDropSource;
    if ( !v45
      || (v7 = ((__int64 (__fastcall *)(IDropSource *, _QWORD))v45->lpVtbl[1].AddRef)(v45, *this->_pdwEffect)) == 0
      || this->_fWinRTDrag
      || this->m_isTargetWinRt )
    {
LABEL_64:
      if ( v29 && !this->_fWinRTDrag && !this->m_isTargetWinRt )
        SetCursor(this->_pcddcDefault->ahcursorDefaults[0][0]);
      goto LABEL_17;
    }
    if ( v7 == 262402 )
    {
      SetCursor(this->_pcddcDefault->ahcursorDefaults[0][0]);
      goto LABEL_64;
    }
LABEL_10:
    this->_hrDragResult = v7;
    goto LABEL_11;
  }
  hwndCur = 0;
  if ( Microsoft::WRL::ComPtr<IDropTarget>::As<IDragDropContainerProxy>(
         &this->m_nonRPCSSRegisteredDropTarget,
         (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDragDropContainerProxy> >)&hwndCur) < 0
    || (HIDWORD(proxy.ptr_) = 0,
        v37 = (*(__int64 (__fastcall **)(HWND__ *, char *))(*(_QWORD *)hwndCur + 40LL))(
                hwndCur,
                (char *)&proxy.ptr_ + 4),
        v37 < 0) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&hwndCur);
    goto LABEL_16;
  }
  v2 = 0;
  *this->_pdwEffect = HIDWORD(proxy.ptr_);
  this->_hrDragResult = v37;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&hwndCur);
$UpdateTarget_exit:
  v8 = v49.ptr_;
  if ( v49.ptr_ )
  {
    v49.ptr_ = 0;
    ((void (__fastcall *)(ITypeLibRegistrationReader *))v8->lpVtbl->Release)(v8);
  }
  return v2;
}

```

## disassembly

```asm
0x18000b140  mov     rax, rsp
0x18000b143  mov     [rax+10h], rbx
0x18000b147  mov     [rax+18h], rsi
0x18000b14b  mov     [rax+20h], rdi
0x18000b14f  push    rbp
0x18000b150  push    r12
0x18000b152  push    r13
0x18000b154  push    r14
0x18000b156  push    r15
0x18000b158  lea     rbp, [rax-5Fh]
0x18000b15c  sub     rsp, 0C0h
0x18000b163  mov     rax, cs:__security_cookie
0x18000b16a  xor     rax, rsp
0x18000b16d  mov     [rbp+57h+var_30], rax
0x18000b171  mov     rax, cs:?g_forcedDropTarget@@3VCForcedDropTarget@@A._hwndFDTCurrent; CForcedDropTarget g_forcedDropTarget ...
0x18000b178  xor     r14d, r14d
0x18000b17b  mov     rsi, this
0x18000b17e  mov     r15d, 1
0x18000b184  mov     [rbp+57h+var_98.ptr_], r14
0x18000b188  mov     [rbp+57h+spExtension.ptr_], r14
0x18000b18c  mov     [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_], rax
0x18000b190  cmp     [this+241h], r14b
0x18000b197  jnz     loc_18000B567
0x18000b19d  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x18000b1a2  test    al, al
0x18000b1a4  jnz     loc_18000B5C4
0x18000b1aa  cmp     [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_], r14
0x18000b1ae  jnz     short loc_18000B22A
0x18000b1b0  mov     rax, [rsi+50h]
0x18000b1b4  lea     this, [r14-3]
0x18000b1b8  mov     [rbp+57h+hwndCur], rax
0x18000b1bc  call    cs:__imp_SetThreadDpiAwarenessContext
0x18000b1c3  nop     dword ptr [rax+rax+00h]
0x18000b1c8  xor     edx, edx; Val
0x18000b1ca  mov     qword ptr [rbp+57h+transform.___u0], r14
0x18000b1ce  lea     r8d, [r15+3Fh]; Size
0x18000b1d2  mov     rbx, rax
0x18000b1d5  lea     this, [rbp+57h+transform.___u0+8]; void *
0x18000b1d9  call    memset_0
0x18000b1de  lea     rax, [rbp+57h+transform.___u0+8]
0x18000b1e2  lea     r9, [rbp+57h+nonRPCSSRegisteredDropTarget]
0x18000b1e6  mov     [rsp+0E0h+var_C0], rax
0x18000b1eb  lea     r8, [rbp+57h+transform]
0x18000b1ef  lea     rdx, [rbp+57h+hwndCur]
0x18000b1f3  lea     ecx, [r15+5]
0x18000b1f7  call    cs:__imp_CompositionInputSinkLuidFromPoint
0x18000b1fe  nop     dword ptr [rax+rax+00h]
0x18000b203  test    eax, eax
0x18000b205  jnz     short loc_18000B21B
0x18000b207  mov     this, [rbp+57h+hwndCur]; Point
0x18000b20b  call    cs:__imp_WindowFromPoint
0x18000b212  nop     dword ptr [rax+rax+00h]
0x18000b217  mov     [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_], rax
0x18000b21b  mov     this, rbx
0x18000b21e  call    cs:__imp_SetThreadDpiAwarenessContext
0x18000b225  nop     dword ptr [rax+rax+00h]
0x18000b22a  mov     this, [rsi+20h]
0x18000b22e  mov     r12d, r14d
0x18000b231  mov     [rbp+57h+luid.LowPart], r14d
0x18000b235  test    this, this
0x18000b238  jz      short loc_18000B2AD
0x18000b23a  mov     rax, [this]
0x18000b23d  mov     r8d, [rsi+80h]
0x18000b244  mov     edx, [rsi+68h]
0x18000b247  mov     rax, [rax+18h]
0x18000b24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b250  mov     [rbp+57h+luid.LowPart], eax
0x18000b253  mov     r12d, eax
0x18000b256  test    eax, eax
0x18000b258  jns     short loc_18000B2D2
0x18000b25a  mov     [rsi+84h], eax
0x18000b260  mov     r15d, r14d
0x18000b263  mov     this, [rbp+57h+var_98.ptr_]
0x18000b267  test    this, this
0x18000b26a  jz      short loc_18000B27C
0x18000b26c  mov     [rbp+57h+var_98.ptr_], r14
0x18000b270  mov     rdx, [this]
0x18000b273  mov     rax, [rdx+10h]
0x18000b277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b27c  mov     eax, r15d
0x18000b27f  mov     this, [rbp+57h+var_30]
0x18000b283  xor     this, rsp; StackCookie
0x18000b286  call    __security_check_cookie
0x18000b28b  lea     r11, [rsp+0E0h+var_20]
0x18000b293  mov     rbx, [r11+38h]
0x18000b297  mov     rsi, [r11+40h]
0x18000b29b  mov     rdi, [r11+48h]
0x18000b29f  mov     rsp, r11
0x18000b2a2  pop     r15
0x18000b2a4  pop     r14
0x18000b2a6  pop     r13
0x18000b2a8  pop     r12
0x18000b2aa  pop     rbp
0x18000b2ab  retn
0x18000b2ad  call    ?IsContainerDragOperation@@YA_NXZ; IsContainerDragOperation(void)
0x18000b2b2  test    al, al
0x18000b2b4  jnz     loc_18000B5D6
0x18000b2ba  mov     rbx, [rsi+78h]
0x18000b2be  cmp     [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_], rbx
0x18000b2c2  jnz     short loc_18000B2DB
0x18000b2c4  test    r12d, r12d
0x18000b2c7  jz      short $UpdateTarget_exit
0x18000b2c9  mov     [rsi+84h], r12d
0x18000b2d0  jmp     short loc_18000B260
0x18000b2d2  cmp     eax, 40101h
0x18000b2d7  jz      short loc_18000B25A
0x18000b2d9  jmp     short loc_18000B2AD
0x18000b2db  mov     [rbp+57h+hwndCur], r14
0x18000b2df  mov     r13, r14
0x18000b2e2  mov     qword ptr [rbp+57h+transform.___u0], r14
0x18000b2e6  mov     rdi, r14
0x18000b2e9  mov     dword ptr [rbp+57h+proxy.ptr_], r14d
0x18000b2ed  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b2f1  jnz     loc_18000B644
0x18000b2f7  mov     eax, dword ptr [rbp+57h+proxy.ptr_]
0x18000b2fa  mov     dword ptr [rbp+57h+proxy.ptr_+4], eax
0x18000b2fd  test    rbx, rbx
0x18000b300  jnz     loc_18000B65C
0x18000b306  mov     r14, [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_]
0x18000b30a  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18000b30e  jnz     loc_18000B6D1
0x18000b314  mov     eax, dword ptr [rbp+57h+proxy.ptr_]
0x18000b317  xor     edi, edi
0x18000b319  mov     dword ptr [rbp+57h+proxy.ptr_+4], eax
0x18000b31c  test    r14, r14
0x18000b31f  jz      loc_18000B47A
0x18000b325  mov     ebx, edi
0x18000b327  mov     r12d, ebx
0x18000b32a  cmp     eax, dword ptr [rbp+57h+proxy.ptr_]
0x18000b32d  jnz     loc_18000B476
0x18000b333  test    rbx, rbx
0x18000b336  jz      loc_18000B3C5
0x18000b33c  test    r12d, r12d
0x18000b33f  jz      short loc_18000B397
0x18000b341  test    rbx, rbx
0x18000b344  jz      short loc_18000B38F
0x18000b346  cmp     [rsi+98h], dil
0x18000b34d  jz      loc_18000B476
0x18000b353  test    r12d, r12d
0x18000b356  jnz     loc_18000B476
0x18000b35c  mov     this, r14; hWnd
0x18000b35f  call    cs:__imp_GetParent
0x18000b366  nop     dword ptr [rax+rax+00h]
0x18000b36b  mov     r14, rax
0x18000b36e  test    rax, rax
0x18000b371  jz      loc_18000B476
0x18000b377  lea     rdx, [rbp+57h+proxy.ptr_+4]; lpdwProcessId
0x18000b37b  mov     this, rax; hWnd
0x18000b37e  call    cs:__imp_GetWindowThreadProcessId
0x18000b385  nop     dword ptr [rax+rax+00h]
0x18000b38a  mov     eax, dword ptr [rbp+57h+proxy.ptr_+4]
0x18000b38d  jmp     short loc_18000B32A
0x18000b38f  cmp     [rbp+57h+var_98.ptr_], rdi
0x18000b393  jz      short loc_18000B35C
0x18000b395  jmp     short loc_18000B346
0x18000b397  mov     this, r14; hwnd
0x18000b39a  call    ?IsWin31DropTarget@@YAHPEAUHWND__@@@Z; IsWin31DropTarget(HWND__ *)
0x18000b39f  test    eax, eax
0x18000b3a1  jz      short loc_18000B341
0x18000b3a3  cmp     [rsi+98h], dil
0x18000b3aa  jz      short loc_18000B341
0x18000b3ac  mov     rax, [rsi+30h]
0x18000b3b0  mov     r12d, r15d
0x18000b3b3  mov     qword ptr [rbp+57h+transform.___u0], r14
0x18000b3b7  test    rax, rax
0x18000b3ba  jz      short loc_18000B341
0x18000b3bc  mov     [rax+8], r14
0x18000b3c0  jmp     loc_18000B341
0x18000b3c5  cmp     [rbp+57h+var_98.ptr_], rdi
0x18000b3c9  jnz     loc_18000B33C
0x18000b3cf  movzx   edx, cs:?g_aDropTarget@@3GA; lpString
0x18000b3d6  mov     this, r14; hWnd
0x18000b3d9  mov     [rsi+229h], dil
0x18000b3e0  call    cs:__imp_GetPropW
0x18000b3e7  nop     dword ptr [rax+rax+00h]
0x18000b3ec  mov     [rbp+57h+spExtension.ptr_], rax
0x18000b3f0  mov     rbx, rax
0x18000b3f3  test    rax, rax
0x18000b3f6  jnz     loc_18000B521
0x18000b3fc  lea     this, [rbp+57h+var_88]; this
0x18000b400  mov     [rbp+57h+var_88.ptr_], rdi
0x18000b404  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b409  lea     rdx, [rbp+57h+var_88]; ppExtension
0x18000b40d  mov     this, rsi; this
0x18000b410  call    ?GetWinRtExtension@CDragOperation@@AEAAJPEAPEAUIDragDropExtensionForOLE@@@Z; CDragOperation::GetWinRtExtension(IDragDropExtensionForOLE * *)
0x18000b415  test    eax, eax
0x18000b417  js      short loc_18000B454
0x18000b419  mov     rbx, [rbp+57h+var_88.ptr_]
0x18000b41d  lea     this, [rbp+57h+var_98]; this
0x18000b421  mov     rax, [rbx]
0x18000b424  mov     rdi, [rax+28h]
0x18000b428  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000b42d  mov     r8, [rsi+230h]
0x18000b434  lea     r9, [rbp+57h+var_98]
0x18000b438  mov     rdx, r14
0x18000b43b  mov     this, rbx
0x18000b43e  mov     rax, rdi
0x18000b441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b446  xor     edi, edi
0x18000b448  test    eax, eax
0x18000b44a  jns     loc_18000B6E9
0x18000b450  mov     rbx, [rbp+57h+spExtension.ptr_]
0x18000b454  mov     this, [rbp+57h+var_88.ptr_]
0x18000b458  test    this, this
0x18000b45b  jz      loc_18000B33C
0x18000b461  mov     [rbp+57h+var_88.ptr_], rdi
0x18000b465  mov     rax, [this]
0x18000b468  mov     rax, [rax+10h]
0x18000b46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b471  jmp     loc_18000B33C
0x18000b476  mov     r12d, [rbp+57h+luid.LowPart]
0x18000b47a  mov     rbx, [rbp+57h+spExtension.ptr_]
0x18000b47e  xor     r14d, r14d
0x18000b481  mov     rdi, [rbp+57h+hwndCur]
0x18000b485  cmp     rbx, [rsi+38h]
0x18000b489  jz      loc_18000B71B
0x18000b48f  mov     ecx, dword ptr [rbp+57h+proxy.ptr_]; processId
0x18000b492  call    ?CDragOperation_DropTargetChanged@OleDragDropTracing@@SAXI@Z; OleDragDropTracing::CDragOperation_DropTargetChanged(uint)
0x18000b497  cmp     qword ptr [rsi+78h], 0FFFFFFFFFFFFFFFFh
0x18000b49c  jnz     loc_18000B759
0x18000b4a2  mov     rax, [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_]
0x18000b4a6  mov     [rsi+38h], rbx
0x18000b4aa  mov     rbx, [rbp+57h+var_98.ptr_]
0x18000b4ae  mov     [rsi+78h], rax
0x18000b4b2  cmp     [rsi+40h], rbx
0x18000b4b6  jnz     loc_18000B777
0x18000b4bc  mov     ecx, dword ptr [rbp+57h+proxy.ptr_]; dwProcessId
0x18000b4bf  test    ecx, ecx
0x18000b4c1  jnz     loc_18000B79E
0x18000b4c7  mov     this, [rsi+30h]; this
0x18000b4cb  mov     ebx, r15d
0x18000b4ce  test    this, this
0x18000b4d1  jnz     loc_18000B7AF
0x18000b4d7  mov     this, [rsi+60h]
0x18000b4db  mov     eax, [rsi+58h]
0x18000b4de  mov     [this], eax
0x18000b4e0  mov     this, [rsi+28h]
0x18000b4e4  test    this, this
0x18000b4e7  jnz     loc_18000B7CE
0x18000b4ed  mov     r9, [rbp+57h+var_98.ptr_]; nonRPCSSRegisteredDropTarget
0x18000b4f1  mov     r8, rdi; hwndDropTarget
0x18000b4f4  mov     rdx, qword ptr [rbp+57h+transform.___u0]; hwnd31
0x18000b4f8  mov     this, rsi; this
0x18000b4fb  call    ?GetDropTarget@CDragOperation@@AEAAJPEAUHWND__@@0PEAUIDropTarget@@@Z; CDragOperation::GetDropTarget(HWND__ *,HWND__ *,IDropTarget *)
0x18000b500  cmp     [rsi+30h], r14
0x18000b504  jz      loc_18000B7E3
0x18000b50a  mov     edx, eax; hr
0x18000b50c  mov     this, rsi; this
0x18000b50f  call    ?HandleFeedBack@CDragOperation@@QEAAHJ@Z; CDragOperation::HandleFeedBack(long)
0x18000b514  test    eax, eax
0x18000b516  jz      $UpdateTarget_exit
0x18000b51c  jmp     loc_18000B2C4
0x18000b521  mov     [rbp+57h+hwndCur], r14
0x18000b525  jmp     loc_18000B33C
0x18000b52a  test    ebx, ebx
0x18000b52c  jz      loc_18000B2C4
0x18000b532  cmp     [rsi+0A8h], r14d
0x18000b539  jnz     loc_18000B2C4
0x18000b53f  cmp     [rsi+229h], r14b
0x18000b546  jnz     loc_18000B2C4
0x18000b54c  mov     this, [rsi+90h]
0x18000b553  mov     this, [this]; hCursor
0x18000b556  call    cs:__imp_SetCursor
0x18000b55d  nop     dword ptr [rax+rax+00h]
0x18000b562  jmp     loc_18000B2C4
0x18000b567  test    rax, rax
0x18000b56a  jnz     short loc_18000B57B
0x18000b56c  mov     dword ptr [this+84h], 40101h
0x18000b576  jmp     loc_18000B260
0x18000b57b  mov     rbx, [this+50h]
0x18000b57f  mov     this, 0FFFFFFFFFFFFFFFDh
0x18000b586  call    cs:__imp_SetThreadDpiAwarenessContext
0x18000b58d  nop     dword ptr [rax+rax+00h]
0x18000b592  mov     this, [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_]
0x18000b596  mov     rdi, rax
0x18000b599  jmp     short loc_18000B5A8
0x18000b59b  cmp     rax, [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_]
0x18000b59f  jz      short loc_18000B5BC
0x18000b5a1  mov     [rbp+57h+nonRPCSSRegisteredDropTarget.ptr_], rax
0x18000b5a5  mov     this, rax; hwndParent
0x18000b5a8  mov     rdx, rbx; ptParentClientCoords
0x18000b5ab  call    cs:__imp_RealChildWindowFromPoint
0x18000b5b2  nop     dword ptr [rax+rax+00h]
0x18000b5b7  test    rax, rax
0x18000b5ba  jnz     short loc_18000B59B
0x18000b5bc  mov     this, rdi
0x18000b5bf  jmp     loc_18000B21E
0x18000b5c4  lea     rdx, [rsi+40h]; other
0x18000b5c8  lea     this, [rbp+57h+var_98]; this
0x18000b5cc  call    ??4?$ComPtr@UIDropTarget@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IDropTarget>::operator=(Microsoft::WRL::ComPtr<IDropTarget> const &)
0x18000b5d1  jmp     loc_18000B22A
0x18000b5d6  cmp     [rsi+241h], r14b
0x18000b5dd  jnz     loc_18000B2BA
0x18000b5e3  lea     this, [rsi+40h]; this
0x18000b5e7  mov     [rbp+57h+hwndCur], r14
0x18000b5eb  lea     rdx, [rbp+57h+hwndCur]; p
0x18000b5ef  call    ??$As@UIDragDropContainerProxy@@@?$ComPtr@UIDropTarget@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDragDropContainerProxy@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IDropTarget>::As<IDragDropContainerProxy>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDragDropContainerProxy>>)
0x18000b5f4  test    eax, eax
0x18000b5f6  js      short loc_18000B636
0x18000b5f8  mov     this, [rbp+57h+hwndCur]
  ... truncated ...
```
