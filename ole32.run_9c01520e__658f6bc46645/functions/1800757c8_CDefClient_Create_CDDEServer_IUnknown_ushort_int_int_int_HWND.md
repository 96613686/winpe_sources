# CDefClient::Create(CDDEServer *,IUnknown *,ushort *,int,int,int,HWND__ * *)

- ea: `0x1800757c8`
- end: `0x180075a1f`
- name: `?Create@CDefClient@@SAJPEAVCDDEServer@@PEAUIUnknown@@PEAGHHHPEAPEAUHWND__@@@Z`
- size: `599`
- prototype: `HRESULT __fastcall(CDDEServer *lhOLESERVER, IUnknown *lpunkObj, wchar_t *lpdocName, const int fDoAdvise, const int fRunningInSDI, const int phwnd, HWND__ **lhOLESERVER)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180073eec`
- `0x1800743c0`

## callees

- `0x180070514`
- `0x180075790`
- `0x1800757c8`
- `0x1800795bc`
- `0x18007a934`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007580f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007580f`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800759e8`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800759e8`
- `USER32!SetWindowLongPtrW` at `0x180075930`
- `USER32!SetWindowLongPtrW` at `0x180075975`
- `USER32!SetWindowLongPtrW` at `0x180075990`
- `USER32!SetWindowLongPtrW` at `0x1800759bc`
- `USER32!SetWindowLongPtrW` at `0x180075930`
- `USER32!SetWindowLongPtrW` at `0x180075975`
- `USER32!SetWindowLongPtrW` at `0x180075990`
- `USER32!SetWindowLongPtrW` at `0x1800759bc`
- `USER32!GetWindowLongPtrW` at `0x1800759a7`
- `USER32!GetWindowLongPtrW` at `0x1800759a7`
- `USER32!CreateWindowExW` at `0x180075908`
- `USER32!CreateWindowExW` at `0x180075908`
- `USER32!DestroyWindow` at `0x1800759d3`
- `USER32!DestroyWindow` at `0x1800759d3`
- `api-ms-win-core-com-l1-1-0!CoLockObjectExternal` at `0x1800758aa`
- `api-ms-win-core-com-l1-1-0!CoLockObjectExternal` at `0x1800758aa`

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
  unsigned int v7; // ebx
  CDefClient *v12; // rax
  IUnknown *v13; // rdx
  CDefClient *v14; // rax
  CDefClient *v15; // rdi
  unsigned int v16; // edx
  HRESULT v17; // eax
  const wchar_t *v18; // rdx
  HWND Window; // rax
  LONG_PTR WindowLongPtrW; // rax
  HWND m_hwnd; // rcx
  ATOM m_aItem; // cx
  HINSTANCE hInstance; // [rsp+50h] [rbp-18h]

  v7 = 0;
  if ( lhOLESERVER && lhOLESERVER->m_bTerminate )
    return 2147549447LL;
  v12 = (CDefClient *)HeapAlloc(g_hHeap, 0, 0x148u);
  if ( v12 )
  {
    CDefClient::CDefClient(v12, v13);
    v15 = v14;
    if ( v14 )
    {
      v14->m_aItem = wGlobalAddAtom(lpdocName);
      v15->m_fRunningInSDI = phwnd;
      v15->m_psrvrParent = lhOLESERVER;
      v15->m_pdoc = v15;
      if ( !((__int64 (__fastcall *)(IUnknown *, GUID *, IOleObject **))lpunkObj->lpVtbl->QueryInterface)(
              lpunkObj,
              &IID_IOleObject,
              &v15->m_lpoleObj)
        && !((__int64 (__fastcall *)(IUnknown *, GUID *, IDataObject **))lpunkObj->lpVtbl->QueryInterface)(
              lpunkObj,
              &IID_IDataObject,
              &v15->m_lpdataObj) )
      {
        v17 = CoLockObjectExternal(lpunkObj, 1, 0);
        v18 = gOleDdeWindowClass;
        hInstance = g_hinst;
        v15->m_fLocked = v17 == 0;
        Window = CreateWindowExW(0, v18, L"DDE ViewObj", 0x40000000u, 0, 0, 0, 0, lhOLESERVER->m_hwnd, 0, hInstance, 0);
        v15->m_hwnd = Window;
        if ( Window )
        {
          SetWindowLongPtrW(Window, -4, (LONG_PTR)DocWndProc);
          if ( !fRunningInSDI || !CDefClient::DoOle20Advise(v15, OLE_CLOSED, 0) )
          {
            if ( lhOLESERVER_0 )
              *lhOLESERVER_0 = v15->m_hwnd;
            SetWindowLongPtrW(v15->m_hwnd, 0, (LONG_PTR)v15);
            SetWindowLongPtrW(v15->m_hwnd, 8, 19525);
            WindowLongPtrW = GetWindowLongPtrW(lhOLESERVER->m_hwnd, 4);
            SetWindowLongPtrW(v15->m_hwnd, 4, WindowLongPtrW);
            return v7;
          }
        }
      }
      m_hwnd = v15->m_hwnd;
      if ( m_hwnd )
        DestroyWindow(m_hwnd);
      m_aItem = v15->m_aItem;
      if ( m_aItem )
        GlobalDeleteAtom(m_aItem);
      CDefClient::`scalar deleting destructor'(v15, v16);
    }
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x1800757c8  mov     rax, rsp
0x1800757cb  mov     [rax+8], rbx
0x1800757cf  mov     [rax+10h], rbp
0x1800757d3  mov     [rax+18h], rsi
0x1800757d7  mov     [rax+20h], rdi
0x1800757db  push    r14
0x1800757dd  sub     rsp, 60h
0x1800757e1  xor     ebx, ebx
0x1800757e3  mov     rbp, lpdocName
0x1800757e6  mov     r14, lpunkObj
0x1800757e9  mov     rsi, lhOLESERVER
0x1800757ec  test    lhOLESERVER, lhOLESERVER
0x1800757ef  jz      short loc_180075800
0x1800757f1  cmp     [lhOLESERVER+48h], ebx
0x1800757f4  jz      short loc_180075800
0x1800757f6  mov     eax, 80010107h
0x1800757fb  jmp     loc_180075A03
0x180075800  mov     lhOLESERVER, cs:?g_hHeap@@3QEAXEA; hHeap
0x180075807  xor     edx, edx; dwFlags
0x180075809  mov     r8d, 148h; dwBytes
0x18007580f  call    cs:__imp_HeapAlloc
0x180075816  nop     dword ptr [rax+rax+00h]
0x18007581b  test    rax, rax
0x18007581e  jz      loc_1800759FC
0x180075824  mov     lhOLESERVER, rax; this
0x180075827  call    ??0CDefClient@@AEAA@PEAUIUnknown@@@Z; CDefClient::CDefClient(IUnknown *)
0x18007582c  mov     rdi, rax
0x18007582f  test    rax, rax
0x180075832  jz      loc_1800759FC
0x180075838  mov     lhOLESERVER, rbp; sz
0x18007583b  call    ?wGlobalAddAtom@@YAGPEBG@Z; wGlobalAddAtom(ushort const *)
0x180075840  mov     [rdi+5Ch], ax
0x180075844  lea     lpdocName, [rdi+40h]
0x180075848  mov     eax, [rsp+68h+arg_28]
0x18007584f  lea     lpunkObj, IID_IOleObject
0x180075856  mov     [rdi+0E0h], eax
0x18007585c  mov     lhOLESERVER, r14
0x18007585f  mov     [rdi+0E8h], rsi
0x180075866  mov     [rdi+110h], rdi
0x18007586d  mov     rax, [r14]
0x180075870  mov     rax, [rax]
0x180075873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075878  test    eax, eax
0x18007587a  jnz     $errRtn_56
0x180075880  mov     rax, [r14]
0x180075883  lea     lpdocName, [rdi+48h]
0x180075887  lea     lpunkObj, IID_IDataObject
0x18007588e  mov     lhOLESERVER, r14
0x180075891  mov     rax, [rax]
0x180075894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075899  test    eax, eax
0x18007589b  jnz     $errRtn_56
0x1800758a1  xor     r8d, r8d; fLastUnlockReleases
0x1800758a4  lea     edx, [rax+1]; fLock
0x1800758a7  mov     lhOLESERVER, r14; pUnk
0x1800758aa  call    cs:__imp_CoLockObjectExternal
0x1800758b1  nop     dword ptr [rax+rax+00h]
0x1800758b6  mov     lpunkObj, cs:?gOleDdeWindowClass@@3PEAGEA; lpClassName
0x1800758bd  lea     lpdocName, aDdeViewobj; "DDE ViewObj"
0x1800758c4  mov     [rsp+68h+lpParam], rbx; lpParam
0x1800758c9  test    eax, eax
0x1800758cb  mov     rax, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x1800758d2  mov     ecx, ebx
0x1800758d4  mov     [rsp+68h+hInstance], rax; hInstance
0x1800758d9  setz    cl
0x1800758dc  mov     [rsp+68h+hMenu], rbx; hMenu
0x1800758e1  mov     r9d, 40000000h; dwStyle
0x1800758e7  mov     [rdi+100h], ecx
0x1800758ed  xor     ecx, ecx; dwExStyle
0x1800758ef  mov     rax, [rsi+50h]
0x1800758f3  mov     [rsp+68h+hWndParent], rax; hWndParent
0x1800758f8  mov     [rsp+68h+nHeight], ebx; nHeight
0x1800758fc  mov     [rsp+68h+nWidth], ebx; nWidth
0x180075900  mov     [rsp+68h+Y], ebx; Y
0x180075904  mov     [rsp+68h+X], ebx; X
0x180075908  call    cs:__imp_CreateWindowExW
0x18007590f  nop     dword ptr [rax+rax+00h]
0x180075914  mov     [rdi+78h], rax
0x180075918  test    rax, rax
0x18007591b  jz      $errRtn_56
0x180075921  lea     lpdocName, DocWndProc; dwNewLong
0x180075928  mov     edx, 0FFFFFFFCh; nIndex
0x18007592d  mov     lhOLESERVER, rax; hWnd
0x180075930  call    cs:__imp_SetWindowLongPtrW
0x180075937  nop     dword ptr [rax+rax+00h]
0x18007593c  cmp     [rsp+68h+arg_20], ebx
0x180075943  jz      short loc_180075958
0x180075945  xor     r8d, r8d; cf
0x180075948  mov     lhOLESERVER, rdi; this
0x18007594b  lea     edx, [lpdocName+2]; options
0x18007594f  call    ?DoOle20Advise@CDefClient@@QEAAJW4OLE_NOTIFICATION@@G@Z; CDefClient::DoOle20Advise(OLE_NOTIFICATION,ushort)
0x180075954  test    eax, eax
0x180075956  jnz     short $errRtn_56
0x180075958  mov     lhOLESERVER, [rsp+68h+lhOLESERVER_0]
0x180075960  test    lhOLESERVER, lhOLESERVER
0x180075963  jz      short loc_18007596C
0x180075965  mov     rax, [rdi+78h]
0x180075969  mov     [lhOLESERVER], rax
0x18007596c  mov     lhOLESERVER, [rdi+78h]; hWnd
0x180075970  mov     lpdocName, rdi; dwNewLong
0x180075973  xor     edx, edx; nIndex
0x180075975  call    cs:__imp_SetWindowLongPtrW
0x18007597c  nop     dword ptr [rax+rax+00h]
0x180075981  mov     lhOLESERVER, [rdi+78h]; hWnd
0x180075985  mov     edx, 8; nIndex
0x18007598a  mov     r8d, 4C45h; dwNewLong
0x180075990  call    cs:__imp_SetWindowLongPtrW
0x180075997  nop     dword ptr [rax+rax+00h]
0x18007599c  mov     lhOLESERVER, [rsi+50h]; hWnd
0x1800759a0  mov     ebp, 4
0x1800759a5  mov     edx, ebp; nIndex
0x1800759a7  call    cs:__imp_GetWindowLongPtrW
0x1800759ae  nop     dword ptr [rax+rax+00h]
0x1800759b3  mov     lhOLESERVER, [rdi+78h]; hWnd
0x1800759b7  mov     edx, ebp; nIndex
0x1800759b9  mov     lpdocName, rax; dwNewLong
0x1800759bc  call    cs:__imp_SetWindowLongPtrW
0x1800759c3  nop     dword ptr [rax+rax+00h]
0x1800759c8  jmp     short $exitRtn_13
0x1800759ca  mov     lhOLESERVER, [rdi+78h]; hWnd
0x1800759ce  test    lhOLESERVER, lhOLESERVER
0x1800759d1  jz      short loc_1800759DF
0x1800759d3  call    cs:__imp_DestroyWindow
0x1800759da  nop     dword ptr [rax+rax+00h]
0x1800759df  movzx   ecx, word ptr [rdi+5Ch]; nAtom
0x1800759e3  test    cx, cx
0x1800759e6  jz      short loc_1800759F4
0x1800759e8  call    cs:__imp_GlobalDeleteAtom
0x1800759ef  nop     dword ptr [rax+rax+00h]
0x1800759f4  mov     lhOLESERVER, rdi; this
0x1800759f7  call    ??_GCDefClient@@AEAAPEAXI@Z; CDefClient::`scalar deleting destructor'(uint)
0x1800759fc  mov     ebx, 8007000Eh
0x180075a01  mov     eax, ebx
0x180075a03  lea     r11, [rsp+68h+var_8]
0x180075a08  mov     rbx, [r11+10h]
0x180075a0c  mov     rbp, [r11+18h]
0x180075a10  mov     rsi, [r11+20h]
0x180075a14  mov     rdi, [r11+28h]
0x180075a18  mov     rsp, r11
0x180075a1b  pop     r14
0x180075a1d  retn
```
