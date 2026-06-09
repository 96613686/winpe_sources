# RegisterDragDropImpl

- ea: `0x180009654`
- end: `0x180009824`
- name: `RegisterDragDropImpl`
- size: `464`
- prototype: `HRESULT __fastcall(HWND__ *hwnd, IDropTarget *pDropTarget, bool fBrokered)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009560`
- `0x18008a598`
- `0x1800946e0`

## callees

- `0x180008280`
- `0x1800085a8`
- `0x180009654`
- `0x18000982c`
- `0x18000a01c`
- `0x18001ad50`
- `0x1800d8010`

## import_xrefs

- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x1800096a8`
- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x1800096a8`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x180009706`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x180009706`
- `USER32!IsWindow` at `0x180009684`
- `USER32!IsWindow` at `0x180009684`
- `USER32!PostMessageW` at `0x1800097f6`
- `USER32!PostMessageW` at `0x1800097f6`
- `USER32!GetPropW` at `0x1800096c9`
- `USER32!GetPropW` at `0x1800096c9`
- `USER32!RemovePropW` at `0x18000980e`
- `USER32!RemovePropW` at `0x18000980e`
- `USER32!SetPropW` at `0x1800096eb`
- `USER32!SetPropW` at `0x1800096eb`

## pseudocode

```c
__int64 __fastcall RegisterDragDropImpl(HWND hwnd, IDropTarget *pDropTarget, wil::ReportingKind fBrokered)
{
  int v6; // ebx
  ULONG IsCriticalSectionLockedByThread; // ebp
  unsigned __int64 v8; // r9
  IDragDropExtensionForOLE *ptr; // rcx
  HWND PrivateClipboardWindow; // rbp
  Microsoft::WRL::ComPtr<IDragDropExtensionForOLE> spExtension; // [rsp+58h] [rbp+20h] BYREF

  v6 = 0;
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
          ((void (__fastcall *)(IDropTarget *))pDropTarget->lpVtbl->AddRef)(pDropTarget);
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
        v6 = AssignDragDropEndpointProperty(hwnd, pDropTarget, fBrokered, v8);
        if ( v6 >= 0 )
        {
          spExtension.ptr_ = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&spExtension);
          if ( (int)GetDragDropExtensionPoint((LPVOID *)&spExtension.ptr_) >= 0 )
            ((void (__fastcall *)(IDragDropExtensionForOLE *, HWND, IDropTarget *))spExtension.ptr_->lpVtbl[1].QueryInterface)(
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
    return (unsigned int)v6;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180009654  mov     [rsp+arg_0], rbx
0x180009659  mov     [rsp+arg_8], rbp
0x18000965e  push    rsi
0x18000965f  push    rdi
0x180009660  push    r14
0x180009662  sub     rsp, 20h
0x180009666  mov     rdi, hwnd
0x180009669  mov     r14b, fBrokered
0x18000966c  mov     hwnd, pDropTarget; pv
0x18000966f  mov     rsi, pDropTarget
0x180009672  xor     ebx, ebx
0x180009674  call    IsValidInterface
0x180009679  test    eax, eax
0x18000967b  jz      loc_1800097A3
0x180009681  mov     hwnd, rdi; hWnd
0x180009684  call    cs:__imp_IsWindow
0x18000968b  nop     dword ptr [rax+rax+00h]
0x180009690  test    eax, eax
0x180009692  jz      loc_1800097AA
0x180009698  mov     hwnd, gs:60h
0x1800096a1  mov     hwnd, [hwnd+110h]; CriticalSection
0x1800096a8  call    cs:__imp_RtlIsCriticalSectionLockedByThread
0x1800096af  nop     dword ptr [rax+rax+00h]
0x1800096b4  mov     ebp, eax
0x1800096b6  test    r14b, r14b
0x1800096b9  jnz     loc_1800097B1
0x1800096bf  movzx   edx, cs:?g_aDropTarget@@3GA; lpString
0x1800096c6  mov     hwnd, rdi; hWnd
0x1800096c9  call    cs:__imp_GetPropW
0x1800096d0  nop     dword ptr [rax+rax+00h]
0x1800096d5  test    rax, rax
0x1800096d8  jnz     loc_1800097C0
0x1800096de  movzx   edx, cs:?g_aDropTarget@@3GA; lpString
0x1800096e5  mov     r8, rsi; hData
0x1800096e8  mov     hwnd, rdi; hWnd
0x1800096eb  call    cs:__imp_SetPropW
0x1800096f2  nop     dword ptr [rax+rax+00h]
0x1800096f7  test    eax, eax
0x1800096f9  jz      loc_18000979C
0x1800096ff  lea     hwnd, aOleendpointid; "OleEndPointID"
0x180009706  call    cs:__imp_GlobalAddAtomW
0x18000970d  nop     dword ptr [rax+rax+00h]
0x180009712  mov     cs:?g_aEndPointAtom@@3GA, ax; ushort g_aEndPointAtom
0x180009719  test    ebp, ebp
0x18000971b  jnz     loc_1800097C7
0x180009721  mov     fBrokered, r14b; fBrokeredInstance
0x180009724  mov     pDropTarget, rsi; pDropTarget
0x180009727  mov     hwnd, rdi; hWnd
0x18000972a  call    ?AssignDragDropEndpointProperty@@YAJPEAUHWND__@@PEAUIDropTarget@@_N@Z; AssignDragDropEndpointProperty(HWND__ *,IDropTarget *,bool)
0x18000972f  mov     ebx, eax
0x180009731  test    eax, eax
0x180009733  js      short loc_180009786
0x180009735  and     [rsp+38h+spExtension.ptr_], 0
0x18000973b  lea     hwnd, [rsp+38h+spExtension]; this
0x180009740  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180009745  lea     hwnd, [rsp+38h+spExtension]; ppExtension
0x18000974a  call    ?GetDragDropExtensionPoint@@YAJPEAPEAUIDragDropExtensionForOLE@@@Z; GetDragDropExtensionPoint(IDragDropExtensionForOLE * *)
0x18000974f  test    eax, eax
0x180009751  js      short loc_18000976A
0x180009753  mov     hwnd, [rsp+38h+spExtension.ptr_]
0x180009758  mov     r8, rsi
0x18000975b  mov     pDropTarget, [hwnd]
0x18000975e  mov     rax, [pDropTarget+18h]
0x180009762  mov     pDropTarget, rdi
0x180009765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000976a  mov     hwnd, [rsp+38h+spExtension.ptr_]
0x18000976f  test    hwnd, hwnd
0x180009772  jz      short loc_180009786
0x180009774  and     [rsp+38h+spExtension.ptr_], 0
0x18000977a  mov     rax, [hwnd]
0x18000977d  mov     rax, [rax+10h]
0x180009781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009786  mov     eax, ebx
0x180009788  mov     rbx, [rsp+38h+arg_0]
0x18000978d  mov     rbp, [rsp+38h+arg_8]
0x180009792  add     rsp, 20h
0x180009796  pop     r14
0x180009798  pop     rdi
0x180009799  pop     rsi
0x18000979a  retn
0x18000979c  mov     ebx, 8007000Eh
0x1800097a1  jmp     short loc_180009786
0x1800097a3  mov     ebx, 80070057h
0x1800097a8  jmp     short loc_180009786
0x1800097aa  mov     ebx, 80040102h
0x1800097af  jmp     short loc_180009786
0x1800097b1  test    ebp, ebp
0x1800097b3  jz      loc_1800096BF
0x1800097b9  mov     eax, 80004005h
0x1800097be  jmp     short loc_180009788
0x1800097c0  mov     ebx, 80040101h
0x1800097c5  jmp     short loc_180009786
0x1800097c7  mov     ecx, 1; fFlags
0x1800097cc  call    ?GetPrivateClipboardWindow@@YAPEAUHWND__@@W4tagCLIPWINDOWFLAGS@@@Z; GetPrivateClipboardWindow(tagCLIPWINDOWFLAGS)
0x1800097d1  mov     rbp, rax
0x1800097d4  test    rax, rax
0x1800097d7  jz      short loc_180009804
0x1800097d9  mov     hwnd, [rsi]
0x1800097dc  mov     rax, [hwnd+8]
0x1800097e0  mov     hwnd, rsi
0x1800097e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097e8  mov     r9, rdi; lParam
0x1800097eb  xor     r8d, r8d; wParam
0x1800097ee  mov     edx, 400h; Msg
0x1800097f3  mov     hwnd, rbp; hWnd
0x1800097f6  call    cs:__imp_PostMessageW
0x1800097fd  nop     dword ptr [rax+rax+00h]
0x180009802  jmp     short loc_180009786
0x180009804  movzx   edx, cs:?g_aDropTarget@@3GA; lpString
0x18000980b  mov     hwnd, rdi; hWnd
0x18000980e  call    cs:__imp_RemovePropW
0x180009815  nop     dword ptr [rax+rax+00h]
0x18000981a  mov     ebx, 80004005h
0x18000981f  jmp     loc_180009786
```
