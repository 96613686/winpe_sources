# RegisterDragDropImpl

- ea: `0x18000ad74`
- end: `0x18000af0c`
- name: `RegisterDragDropImpl`
- size: `408`
- prototype: `HRESULT __fastcall(HWND__ *hwnd, IDropTarget *pDropTarget, bool fBrokered)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ac70`
- `0x18008eb80`
- `0x1800959f0`

## callees

- `0x180009de0`
- `0x18000a0e8`
- `0x18000ad74`
- `0x18000af14`
- `0x18000b7a0`
- `0x18000d38c`
- `0x1800ce010`

## import_xrefs

- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x18000adb7`
- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x18000adb7`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x18000ae03`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x18000ae03`
- `USER32!IsWindow` at `0x18000ad99`
- `USER32!IsWindow` at `0x18000ad99`
- `USER32!PostMessageW` at `0x18000aeea`
- `USER32!PostMessageW` at `0x18000aeea`
- `USER32!GetPropW` at `0x18000add2`
- `USER32!GetPropW` at `0x18000add2`
- `USER32!RemovePropW` at `0x18000aefc`
- `USER32!RemovePropW` at `0x18000aefc`
- `USER32!SetPropW` at `0x18000adee`
- `USER32!SetPropW` at `0x18000adee`

## pseudocode

```c
__int64 __fastcall RegisterDragDropImpl(
        HWND hwnd,
        Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *pDropTarget,
        wil::ReportingKind fBrokered)
{
  ULONG IsCriticalSectionLockedByThread; // ebx
  unsigned __int64 v7; // r9
  int v8; // ebx
  IDragDropExtensionForOLE *ptr; // rcx
  HWND PrivateClipboardWindow; // rbp
  Microsoft::WRL::ComPtr<IDragDropExtensionForOLE> spExtension; // [rsp+68h] [rbp+20h] BYREF

  if ( !IsValidInterface(pDropTarget) )
    return (unsigned int)-2147024809;
  if ( !IsWindow(hwnd) )
    return (unsigned int)-2147221246;
  IsCriticalSectionLockedByThread = RtlIsCriticalSectionLockedByThread(NtCurrentPeb()->LoaderLock);
  if ( fBrokered == None || !IsCriticalSectionLockedByThread )
  {
    if ( GetPropW(hwnd, (LPCWSTR)g_aDropTarget) )
    {
      return (unsigned int)-2147221247;
    }
    else if ( SetPropW(hwnd, (LPCWSTR)g_aDropTarget, pDropTarget) )
    {
      g_aEndPointAtom = GlobalAddAtomW(L"OleEndPointID");
      if ( IsCriticalSectionLockedByThread )
      {
        PrivateClipboardWindow = GetPrivateClipboardWindow(CLIP_CREATEIFNOTTHERE);
        if ( PrivateClipboardWindow )
        {
          v8 = 0;
          ((void (__fastcall *)(Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *))pDropTarget->lpVtbl->AddRef)(pDropTarget);
          PostMessageW(PrivateClipboardWindow, 0x400u, 0, (LPARAM)hwnd);
        }
        else
        {
          RemovePropW(hwnd, (LPCWSTR)g_aDropTarget);
          return (unsigned int)-2147467259;
        }
      }
      else
      {
        v8 = AssignDragDropEndpointProperty(hwnd, pDropTarget, fBrokered, v7);
        if ( v8 >= 0 )
        {
          spExtension.ptr_ = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&spExtension);
          if ( (int)GetDragDropExtensionPoint((LPVOID *)&spExtension.ptr_) >= 0 )
            ((void (__fastcall *)(IDragDropExtensionForOLE *, HWND, Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *))spExtension.ptr_->lpVtbl[1].QueryInterface)(
              spExtension.ptr_,
              hwnd,
              pDropTarget);
          ptr = spExtension.ptr_;
          if ( spExtension.ptr_ )
          {
            spExtension.ptr_ = 0;
            ((void (__fastcall *)(IDragDropExtensionForOLE *))ptr->lpVtbl->Release)(ptr);
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
    return (unsigned int)v8;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000ad74  push    rbx
0x18000ad76  push    rbp
0x18000ad77  push    rsi
0x18000ad78  push    rdi
0x18000ad79  sub     rsp, 28h
0x18000ad7d  mov     rdi, hwnd
0x18000ad80  mov     bpl, fBrokered
0x18000ad83  mov     hwnd, pDropTarget; pv
0x18000ad86  mov     rsi, pDropTarget
0x18000ad89  call    IsValidInterface
0x18000ad8e  test    eax, eax
0x18000ad90  jz      loc_18000AE95
0x18000ad96  mov     hwnd, rdi; hWnd
0x18000ad99  call    cs:__imp_IsWindow
0x18000ad9f  test    eax, eax
0x18000ada1  jz      loc_18000AE9C
0x18000ada7  mov     hwnd, gs:60h
0x18000adb0  mov     hwnd, [hwnd+110h]; CriticalSection
0x18000adb7  call    cs:__imp_RtlIsCriticalSectionLockedByThread
0x18000adbd  mov     ebx, eax
0x18000adbf  test    bpl, bpl
0x18000adc2  jnz     loc_18000AEA3
0x18000adc8  movzx   edx, cs:?g_aDropTarget@@3GA; lpString
0x18000adcf  mov     hwnd, rdi; hWnd
0x18000add2  call    cs:__imp_GetPropW
0x18000add8  test    rax, rax
0x18000addb  jnz     loc_18000AEB2
0x18000ade1  movzx   edx, cs:?g_aDropTarget@@3GA; lpString
0x18000ade8  mov     r8, rsi; hData
0x18000adeb  mov     hwnd, rdi; hWnd
0x18000adee  call    cs:__imp_SetPropW
0x18000adf4  test    eax, eax
0x18000adf6  jz      loc_18000AE8E
0x18000adfc  lea     hwnd, aOleendpointid; "OleEndPointID"
0x18000ae03  call    cs:__imp_GlobalAddAtomW
0x18000ae09  mov     cs:?g_aEndPointAtom@@3GA, ax; ushort g_aEndPointAtom
0x18000ae10  test    ebx, ebx
0x18000ae12  jnz     loc_18000AEB9
0x18000ae18  mov     fBrokered, bpl; fBrokeredInstance
0x18000ae1b  mov     pDropTarget, rsi; pDropTarget
0x18000ae1e  mov     hwnd, rdi; hWnd
0x18000ae21  call    ?AssignDragDropEndpointProperty@@YAJPEAUHWND__@@PEAUIDropTarget@@_N@Z; AssignDragDropEndpointProperty(HWND__ *,IDropTarget *,bool)
0x18000ae26  mov     ebx, eax
0x18000ae28  test    eax, eax
0x18000ae2a  js      short loc_18000AE83
0x18000ae2c  lea     hwnd, [rsp+48h+spExtension]; this
0x18000ae31  mov     [rsp+48h+spExtension.ptr_], 0
0x18000ae3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ae3f  lea     hwnd, [rsp+48h+spExtension]; ppExtension
0x18000ae44  call    ?GetDragDropExtensionPoint@@YAJPEAPEAUIDragDropExtensionForOLE@@@Z; GetDragDropExtensionPoint(IDragDropExtensionForOLE * *)
0x18000ae49  test    eax, eax
0x18000ae4b  js      short loc_18000AE64
0x18000ae4d  mov     hwnd, [rsp+48h+spExtension.ptr_]
0x18000ae52  mov     r8, rsi
0x18000ae55  mov     pDropTarget, [hwnd]
0x18000ae58  mov     rax, [pDropTarget+18h]
0x18000ae5c  mov     pDropTarget, rdi
0x18000ae5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae64  mov     hwnd, [rsp+48h+spExtension.ptr_]
0x18000ae69  test    hwnd, hwnd
0x18000ae6c  jz      short loc_18000AE83
0x18000ae6e  mov     [rsp+48h+spExtension.ptr_], 0
0x18000ae77  mov     rax, [hwnd]
0x18000ae7a  mov     rax, [rax+10h]
0x18000ae7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae83  mov     eax, ebx
0x18000ae85  add     rsp, 28h
0x18000ae89  pop     rdi
0x18000ae8a  pop     rsi
0x18000ae8b  pop     rbp
0x18000ae8c  pop     rbx
0x18000ae8d  retn
0x18000ae8e  mov     ebx, 8007000Eh
0x18000ae93  jmp     short loc_18000AE83
0x18000ae95  mov     ebx, 80070057h
0x18000ae9a  jmp     short loc_18000AE83
0x18000ae9c  mov     ebx, 80040102h
0x18000aea1  jmp     short loc_18000AE83
0x18000aea3  test    ebx, ebx
0x18000aea5  jz      loc_18000ADC8
0x18000aeab  mov     eax, 80004005h
0x18000aeb0  jmp     short loc_18000AE85
0x18000aeb2  mov     ebx, 80040101h
0x18000aeb7  jmp     short loc_18000AE83
0x18000aeb9  mov     ecx, 1; fFlags
0x18000aebe  call    ?GetPrivateClipboardWindow@@YAPEAUHWND__@@W4tagCLIPWINDOWFLAGS@@@Z; GetPrivateClipboardWindow(tagCLIPWINDOWFLAGS)
0x18000aec3  mov     rbp, rax
0x18000aec6  test    rax, rax
0x18000aec9  jz      short loc_18000AEF2
0x18000aecb  mov     hwnd, [rsi]
0x18000aece  xor     ebx, ebx
0x18000aed0  mov     rax, [hwnd+8]
0x18000aed4  mov     hwnd, rsi
0x18000aed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aedc  mov     r9, rdi; lParam
0x18000aedf  xor     r8d, r8d; wParam
0x18000aee2  mov     edx, 400h; Msg
0x18000aee7  mov     hwnd, rbp; hWnd
0x18000aeea  call    cs:__imp_PostMessageW
0x18000aef0  jmp     short loc_18000AE83
0x18000aef2  movzx   edx, cs:?g_aDropTarget@@3GA; lpString
0x18000aef9  mov     hwnd, rdi; hWnd
0x18000aefc  call    cs:__imp_RemovePropW
0x18000af02  mov     ebx, 80004005h
0x18000af07  jmp     loc_18000AE83
```
