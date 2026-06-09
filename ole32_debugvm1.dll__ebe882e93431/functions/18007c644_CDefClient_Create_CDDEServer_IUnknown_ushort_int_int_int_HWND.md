# CDefClient::Create(CDDEServer *,IUnknown *,ushort *,int,int,int,HWND__ * *)

- ea: `0x18007c644`
- end: `0x18007c849`
- name: `?Create@CDefClient@@SAJPEAVCDDEServer@@PEAUIUnknown@@PEAGHHHPEAPEAUHWND__@@@Z`
- size: `517`
- prototype: `HRESULT __fastcall(CDDEServer *lhOLESERVER, IUnknown *lpunkObj, wchar_t *lpdocName, const int fDoAdvise, const int fRunningInSDI, const int phwnd, HWND__ **lhOLESERVER)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007afc0`
- `0x18007b3d0`

## callees

- `0x180077cc8`
- `0x18007c614`
- `0x18007c644`
- `0x18007fee4`
- `0x180081004`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c67f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007c67f`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007c82b`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007c82b`
- `USER32!SetWindowLongPtrW` at `0x18007c793`
- `USER32!SetWindowLongPtrW` at `0x18007c7d3`
- `USER32!SetWindowLongPtrW` at `0x18007c7e8`
- `USER32!SetWindowLongPtrW` at `0x18007c808`
- `USER32!SetWindowLongPtrW` at `0x18007c793`
- `USER32!SetWindowLongPtrW` at `0x18007c7d3`
- `USER32!SetWindowLongPtrW` at `0x18007c7e8`
- `USER32!SetWindowLongPtrW` at `0x18007c808`
- `USER32!GetWindowLongPtrW` at `0x18007c7f9`
- `USER32!GetWindowLongPtrW` at `0x18007c7f9`
- `USER32!CreateWindowExW` at `0x18007c771`
- `USER32!CreateWindowExW` at `0x18007c771`
- `USER32!DestroyWindow` at `0x18007c81c`
- `USER32!DestroyWindow` at `0x18007c81c`
- `api-ms-win-core-com-l1-1-0!CoLockObjectExternal` at `0x18007c714`
- `api-ms-win-core-com-l1-1-0!CoLockObjectExternal` at `0x18007c714`

## pseudocode

```c
__int64 __fastcall CDefClient::Create(
        CDDEServer *lhOLESERVER,
        IUnknown *lpunkObj,
        wchar_t *lpdocName,
        const int fDoAdvise,
        const int fRunningInSDI,
        int phwnd,
        HWND__ **lhOLESERVER_0)
{
  CDefClient *v11; // rax
  IUnknown *v12; // rdx
  CDefClient *v13; // rax
  CDefClient *v14; // rbx
  unsigned __int16 v15; // ax
  unsigned int v16; // edx
  HRESULT v17; // eax
  const wchar_t *v18; // rdx
  HWND Window; // rax
  LONG_PTR WindowLongPtrW; // rax
  HWND m_hwnd; // rcx
  ATOM m_aItem; // cx
  HINSTANCE hInstance; // [rsp+50h] [rbp-38h]

  if ( lhOLESERVER && lhOLESERVER->m_bTerminate )
    return 2147549447LL;
  v11 = (CDefClient *)HeapAlloc(g_hHeap, 0, 0x148u);
  if ( !v11 )
    return 2147942414LL;
  CDefClient::CDefClient(v11, v12);
  v14 = v13;
  if ( !v13 )
    return 2147942414LL;
  v15 = wGlobalAddAtom(lpdocName);
  v14->m_fRunningInSDI = phwnd;
  v14->m_aItem = v15;
  v14->m_psrvrParent = lhOLESERVER;
  v14->m_pdoc = v14;
  if ( ((__int64 (__fastcall *)(IUnknown *, GUID *, IOleObject **))lpunkObj->lpVtbl->QueryInterface)(
         lpunkObj,
         &IID_IOleObject,
         &v14->m_lpoleObj)
    || ((__int64 (__fastcall *)(IUnknown *, GUID *, IDataObject **))lpunkObj->lpVtbl->QueryInterface)(
         lpunkObj,
         &IID_IDataObject,
         &v14->m_lpdataObj)
    || (v17 = CoLockObjectExternal(lpunkObj, 1, 0),
        v18 = gOleDdeWindowClass,
        hInstance = g_hinst,
        v14->m_fLocked = v17 == 0,
        Window = CreateWindowExW(0, v18, L"DDE ViewObj", 0x40000000u, 0, 0, 0, 0, lhOLESERVER->m_hwnd, 0, hInstance, 0),
        (v14->m_hwnd = Window) == 0)
    || (SetWindowLongPtrW(Window, -4, (LONG_PTR)DocWndProc), fRunningInSDI)
    && CDefClient::DoOle20Advise(v14, OLE_CLOSED, 0) )
  {
    m_hwnd = v14->m_hwnd;
    if ( m_hwnd )
      DestroyWindow(m_hwnd);
    m_aItem = v14->m_aItem;
    if ( m_aItem )
      GlobalDeleteAtom(m_aItem);
    CDefClient::`scalar deleting destructor'(v14, v16);
    return 2147942414LL;
  }
  if ( lhOLESERVER_0 )
    *lhOLESERVER_0 = v14->m_hwnd;
  SetWindowLongPtrW(v14->m_hwnd, 0, (LONG_PTR)v14);
  SetWindowLongPtrW(v14->m_hwnd, 8, 19525);
  WindowLongPtrW = GetWindowLongPtrW(lhOLESERVER->m_hwnd, 4);
  SetWindowLongPtrW(v14->m_hwnd, 4, WindowLongPtrW);
  return 0;
}

```

## disassembly

```asm
0x18007c644  push    rbx
0x18007c646  push    rbp
0x18007c647  push    rsi
0x18007c648  push    rdi
0x18007c649  push    r14
0x18007c64b  sub     rsp, 60h
0x18007c64f  xor     r14d, r14d
0x18007c652  mov     rbp, lpdocName
0x18007c655  mov     rsi, lpunkObj
0x18007c658  mov     rdi, lhOLESERVER
0x18007c65b  test    lhOLESERVER, lhOLESERVER
0x18007c65e  jz      short loc_18007C670
0x18007c660  cmp     [lhOLESERVER+48h], r14d
0x18007c664  jz      short loc_18007C670
0x18007c666  mov     eax, 80010107h
0x18007c66b  jmp     $exitRtn_14
0x18007c670  mov     lhOLESERVER, cs:?g_hHeap@@3QEAXEA; hHeap
0x18007c677  xor     edx, edx; dwFlags
0x18007c679  mov     r8d, 148h; dwBytes
0x18007c67f  call    cs:__imp_HeapAlloc
0x18007c685  test    rax, rax
0x18007c688  jz      loc_18007C839
0x18007c68e  mov     lhOLESERVER, rax; this
0x18007c691  call    ??0CDefClient@@AEAA@PEAUIUnknown@@@Z; CDefClient::CDefClient(IUnknown *)
0x18007c696  mov     rbx, rax
0x18007c699  test    rax, rax
0x18007c69c  jz      loc_18007C839
0x18007c6a2  mov     lhOLESERVER, rbp; sz
0x18007c6a5  call    ?wGlobalAddAtom@@YAGPEBG@Z; wGlobalAddAtom(ushort const *)
0x18007c6aa  mov     ecx, [rsp+88h+arg_28]
0x18007c6b1  lea     lpdocName, [rbx+40h]
0x18007c6b5  mov     [rbx+0E0h], ecx
0x18007c6bb  lea     lpunkObj, IID_IOleObject
0x18007c6c2  mov     [rbx+5Ch], ax
0x18007c6c6  mov     [rbx+0E8h], rdi
0x18007c6cd  mov     [rbx+110h], rbx
0x18007c6d4  mov     lhOLESERVER, [rsi]
0x18007c6d7  mov     rax, [lhOLESERVER]
0x18007c6da  mov     lhOLESERVER, rsi
0x18007c6dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c6e2  test    eax, eax
0x18007c6e4  jnz     $errRtn_89
0x18007c6ea  mov     rax, [rsi]
0x18007c6ed  lea     lpdocName, [rbx+48h]
0x18007c6f1  lea     lpunkObj, IID_IDataObject
0x18007c6f8  mov     lhOLESERVER, rsi
0x18007c6fb  mov     rax, [rax]
0x18007c6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c703  test    eax, eax
0x18007c705  jnz     $errRtn_89
0x18007c70b  xor     r8d, r8d; fLastUnlockReleases
0x18007c70e  lea     edx, [rax+1]; fLock
0x18007c711  mov     lhOLESERVER, rsi; pUnk
0x18007c714  call    cs:__imp_CoLockObjectExternal
0x18007c71a  mov     lpunkObj, cs:?gOleDdeWindowClass@@3PEAGEA; lpClassName
0x18007c721  lea     lpdocName, aDdeViewobj; "DDE ViewObj"
0x18007c728  mov     [rsp+88h+lpParam], r14; lpParam
0x18007c72d  test    eax, eax
0x18007c72f  mov     rax, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x18007c736  mov     ecx, r14d
0x18007c739  mov     [rsp+88h+hInstance], rax; hInstance
0x18007c73e  setz    cl
0x18007c741  mov     [rsp+88h+hMenu], r14; hMenu
0x18007c746  mov     r9d, 40000000h; dwStyle
0x18007c74c  mov     [rbx+100h], ecx
0x18007c752  xor     ecx, ecx; dwExStyle
0x18007c754  mov     rax, [rdi+50h]
0x18007c758  mov     [rsp+88h+hWndParent], rax; hWndParent
0x18007c75d  mov     [rsp+88h+nHeight], r14d; nHeight
0x18007c762  mov     [rsp+88h+nWidth], r14d; nWidth
0x18007c767  mov     [rsp+88h+Y], r14d; Y
0x18007c76c  mov     [rsp+88h+X], r14d; X
0x18007c771  call    cs:__imp_CreateWindowExW
0x18007c777  mov     [rbx+78h], rax
0x18007c77b  test    rax, rax
0x18007c77e  jz      $errRtn_89
0x18007c784  lea     lpdocName, DocWndProc; dwNewLong
0x18007c78b  mov     edx, 0FFFFFFFCh; nIndex
0x18007c790  mov     lhOLESERVER, rax; hWnd
0x18007c793  call    cs:__imp_SetWindowLongPtrW
0x18007c799  cmp     [rsp+88h+arg_20], r14d
0x18007c7a1  jz      short loc_18007C7B6
0x18007c7a3  xor     r8d, r8d; cf
0x18007c7a6  mov     lhOLESERVER, rbx; this
0x18007c7a9  lea     edx, [lpdocName+2]; options
0x18007c7ad  call    ?DoOle20Advise@CDefClient@@QEAAJW4OLE_NOTIFICATION@@G@Z; CDefClient::DoOle20Advise(OLE_NOTIFICATION,ushort)
0x18007c7b2  test    eax, eax
0x18007c7b4  jnz     short $errRtn_89
0x18007c7b6  mov     lhOLESERVER, [rsp+88h+lhOLESERVER_0]
0x18007c7be  test    lhOLESERVER, lhOLESERVER
0x18007c7c1  jz      short loc_18007C7CA
0x18007c7c3  mov     rax, [rbx+78h]
0x18007c7c7  mov     [lhOLESERVER], rax
0x18007c7ca  mov     lhOLESERVER, [rbx+78h]; hWnd
0x18007c7ce  mov     lpdocName, rbx; dwNewLong
0x18007c7d1  xor     edx, edx; nIndex
0x18007c7d3  call    cs:__imp_SetWindowLongPtrW
0x18007c7d9  mov     lhOLESERVER, [rbx+78h]; hWnd
0x18007c7dd  mov     edx, 8; nIndex
0x18007c7e2  mov     r8d, 4C45h; dwNewLong
0x18007c7e8  call    cs:__imp_SetWindowLongPtrW
0x18007c7ee  mov     lhOLESERVER, [rdi+50h]; hWnd
0x18007c7f2  mov     esi, 4
0x18007c7f7  mov     edx, esi; nIndex
0x18007c7f9  call    cs:__imp_GetWindowLongPtrW
0x18007c7ff  mov     lhOLESERVER, [rbx+78h]; hWnd
0x18007c803  mov     edx, esi; nIndex
0x18007c805  mov     lpdocName, rax; dwNewLong
0x18007c808  call    cs:__imp_SetWindowLongPtrW
0x18007c80e  mov     eax, r14d
0x18007c811  jmp     short $exitRtn_14
0x18007c813  mov     lhOLESERVER, [rbx+78h]; hWnd
0x18007c817  test    lhOLESERVER, lhOLESERVER
0x18007c81a  jz      short loc_18007C822
0x18007c81c  call    cs:__imp_DestroyWindow
0x18007c822  movzx   ecx, word ptr [rbx+5Ch]; nAtom
0x18007c826  test    cx, cx
0x18007c829  jz      short loc_18007C831
0x18007c82b  call    cs:__imp_GlobalDeleteAtom
0x18007c831  mov     lhOLESERVER, rbx; this
0x18007c834  call    ??_GCDefClient@@AEAAPEAXI@Z; CDefClient::`scalar deleting destructor'(uint)
0x18007c839  mov     eax, 8007000Eh
0x18007c83e  add     rsp, 60h
0x18007c842  pop     r14
0x18007c844  pop     rdi
0x18007c845  pop     rsi
0x18007c846  pop     rbp
0x18007c847  pop     rbx
0x18007c848  retn
```
