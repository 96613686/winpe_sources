# CDocHostUIHandler::ShowPropertysheetDialog(tagVARIANT *,tagVARIANT *,ulong)

- ea: `0x180127958`
- end: `0x180127cb3`
- name: `?ShowPropertysheetDialog@CDocHostUIHandler@@IEAAJPEAUtagVARIANT@@0K@Z`
- size: `859`
- prototype: `__int64 __fastcall(CDocHostUIHandler *__hidden this, struct tagVARIANT *, struct tagVARIANT *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180122880`

## callees

- `0x18001546c`
- `0x18003b368`
- `0x18007e4c4`
- `0x180121a80`
- `0x180122c2c`
- `0x180122cdc`
- `0x180123004`
- `0x180123424`
- `0x180127958`
- `0x180591ef6`
- `0x180591f80`

## import_xrefs

- `KERNEL32!GetUserDefaultLCID` at `0x180127bbd`
- `KERNEL32!GetUserDefaultLCID` at `0x180127bbd`
- `USER32!GetWindowRect` at `0x180127b26`
- `USER32!GetWindowRect` at `0x180127b3b`
- `USER32!GetWindowRect` at `0x180127b26`
- `USER32!GetWindowRect` at `0x180127b3b`
- `USER32!SetThreadDpiAwarenessContext` at `0x180127be9`
- `USER32!SetThreadDpiAwarenessContext` at `0x180127c0b`
- `USER32!SetThreadDpiAwarenessContext` at `0x180127be9`
- `USER32!SetThreadDpiAwarenessContext` at `0x180127c0b`
- `USER32!GetDesktopWindow` at `0x180127b13`
- `USER32!GetDesktopWindow` at `0x180127b13`
- `USER32!GetParent` at `0x180127b02`
- `USER32!GetParent` at `0x180127b02`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180127a61`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180127a61`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180127a80`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180127a80`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180127aab`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180127aab`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180127c50`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180127c50`
- `OLEAUT32!__imp_OleCreatePropertyFrameIndirect` at `0x180127bfc`
- `OLEAUT32!__imp_OleCreatePropertyFrameIndirect` at `0x180127bfc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180127c35`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180127c35`
- `PROPSYS!ClearVariantArray` at `0x180127c76`
- `PROPSYS!ClearVariantArray` at `0x180127c76`

## pseudocode

```c
__int64 __fastcall CDocHostUIHandler::ShowPropertysheetDialog(
        CDocHostUIHandler *this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3)
{
  SAFEARRAY *parray; // rdi
  struct IUnknown *punkVal; // rcx
  unsigned int HwndFromUnknown; // ebx
  CDocHostUIHandler *v8; // rcx
  LONG v9; // edx
  struct IUnknown **v10; // r8
  HWND i; // rcx
  HWND Parent; // rax
  HWND DesktopWindow; // rax
  LCID UserDefaultLCID; // eax
  __int64 v15; // rbx
  LONG plUbound; // [rsp+30h] [rbp-D0h] BYREF
  HWND hWnd; // [rsp+38h] [rbp-C8h] BYREF
  void *ppvData; // [rsp+40h] [rbp-C0h] BYREF
  struct tagSIZE v20; // [rsp+48h] [rbp-B8h] BYREF
  struct tagSIZE v21; // [rsp+50h] [rbp-B0h] BYREF
  struct IUnknown *v22; // [rsp+58h] [rbp-A8h] BYREF
  struct IHTMLEventObj *v23; // [rsp+60h] [rbp-A0h] BYREF
  tagCAUUID v24; // [rsp+68h] [rbp-98h] BYREF
  ULONG_PTR ulCookie; // [rsp+78h] [rbp-88h] BYREF
  int v26; // [rsp+80h] [rbp-80h] BYREF
  VARIANT psa; // [rsp+88h] [rbp-78h] BYREF
  tagOCPFIPARAMS Params; // [rsp+A0h] [rbp-60h] BYREF
  struct tagRECT Rect; // [rsp+F0h] [rbp-10h] BYREF
  struct tagRECT v30; // [rsp+100h] [rbp+0h] BYREF

  hWnd = 0;
  v22 = 0;
  plUbound = 0;
  ppvData = 0;
  memset_0(&Params, 0, sizeof(Params));
  *(_QWORD *)&v24.cElems = 0;
  v24.pElems = 0;
  v20 = 0;
  v23 = 0;
  parray = 0;
  v30 = 0;
  Rect = 0;
  memset(&psa, 0, sizeof(psa));
  if ( !a2 )
    goto LABEL_19;
  if ( a2->vt != 13 )
    goto LABEL_19;
  punkVal = a2->punkVal;
  if ( !punkVal )
    goto LABEL_19;
  v22 = a2->punkVal;
  HwndFromUnknown = GetHwndFromUnknown(punkVal, &hWnd);
  if ( HwndFromUnknown )
    goto LABEL_20;
  HwndFromUnknown = GetEventFromUnknown(v22, &v23);
  if ( HwndFromUnknown )
    goto LABEL_20;
  HwndFromUnknown = GetParamsFromEvent(v23, 1u, &v26, &psa, (const struct SExpandoInfo *const)&off_1805DF0B0);
  if ( HwndFromUnknown )
    goto LABEL_20;
  parray = psa.parray;
  if ( SafeArrayGetDim(psa.parray) != 1 )
  {
LABEL_19:
    HwndFromUnknown = -2147024809;
    goto LABEL_20;
  }
  HwndFromUnknown = SafeArrayGetUBound(parray, 1u, &plUbound);
  if ( !HwndFromUnknown )
  {
    if ( ++plUbound )
    {
      HwndFromUnknown = SafeArrayAccessData(parray, &ppvData);
      if ( HwndFromUnknown )
        goto LABEL_20;
      v9 = plUbound;
      v10 = (struct IUnknown **)ppvData;
    }
    else
    {
      v9 = 1;
      v10 = &v22;
      plUbound = 1;
      ppvData = &v22;
    }
    HwndFromUnknown = CDocHostUIHandler::GetCommonPages(v8, v9, v10, &v24);
    if ( !HwndFromUnknown )
    {
      for ( i = hWnd; ; i = Parent )
      {
        Parent = GetParent(i);
        if ( !Parent )
          break;
        hWnd = Parent;
      }
      DesktopWindow = GetDesktopWindow();
      GetWindowRect(DesktopWindow, &Rect);
      GetWindowRect(hWnd, &v30);
      v21.cx = (Rect.right - Rect.left) / 2 - v30.left;
      v21.cy = (Rect.bottom - Rect.top) / 2 - v30.top;
      ATL::AtlPixelToHiMetric(&v21, &v20);
      Params.hWndOwner = hWnd;
      *(struct tagSIZE *)&Params.x = v20;
      Params.cObjects = plUbound;
      Params.lplpUnk = (LPUNKNOWN *)ppvData;
      Params.cPages = v24.cElems;
      Params.lpPages = v24.pElems;
      Params.cbStructSize = 72;
      Params.lpszCaption = 0;
      UserDefaultLCID = GetUserDefaultLCID();
      Params.dispidInitialProperty = -1;
      Params.lcid = UserDefaultLCID;
      ulCookie = 0;
      SHActivateContext(&ulCookie);
      v15 = SetThreadDpiAwarenessContext(-2);
      OleCreatePropertyFrameIndirect(&Params);
      SetThreadDpiAwarenessContext(v15);
      HwndFromUnknown = 0;
      if ( ulCookie )
        SHDeactivateContext(ulCookie);
    }
  }
LABEL_20:
  CoTaskMemFree(v24.pElems);
  if ( parray && ppvData )
    SafeArrayUnaccessData(parray);
  if ( a3 )
  {
    *(_OWORD *)&a3->vt = 0;
    a3->pRecInfo = 0;
  }
  ClearVariantArray(&psa, 1u);
  ATL::CComPtr<IPrivacIEDatabase>::Release(&v23);
  return HwndFromUnknown;
}

```

## disassembly

```asm
0x180127958  mov     [rsp-8+arg_0], rbx
0x18012795d  mov     [rsp-8+arg_18], rsi
0x180127962  push    rbp
0x180127963  push    rdi
0x180127964  push    r14
0x180127966  lea     rbp, [rsp-20h]
0x18012796b  sub     rsp, 120h
0x180127972  mov     rax, cs:__security_cookie
0x180127979  xor     rax, rsp
0x18012797c  mov     [rbp+30h+var_20], rax
0x180127980  xor     r14d, r14d
0x180127983  lea     rcx, [rbp+30h+Params]; void *
0x180127987  mov     rsi, r8
0x18012798a  mov     [rsp+130h+hWnd], r14
0x18012798f  mov     rbx, rdx
0x180127992  mov     [rsp+130h+var_D8], r14
0x180127997  xor     edx, edx; Val
0x180127999  mov     [rsp+130h+plUbound], r14d
0x18012799e  lea     r8d, [r14+48h]; Size
0x1801279a2  mov     [rsp+130h+ppvData], r14
0x1801279a7  call    memset_0
0x1801279ac  xor     eax, eax
0x1801279ae  mov     qword ptr [rsp+130h+var_C8.cElems], r14
0x1801279b3  mov     [rsp+130h+var_C8.pElems], r14
0x1801279b8  xorps   xmm0, xmm0
0x1801279bb  mov     qword ptr [rsp+130h+var_E8.cx], r14
0x1801279c0  xorps   xmm1, xmm1
0x1801279c3  mov     [rsp+130h+var_D0], r14
0x1801279c8  mov     edi, r14d
0x1801279cb  mov     [rbp+30h+var_98], rax
0x1801279cf  movdqu  xmmword ptr [rbp+30h+var_30.left], xmm0
0x1801279d4  movdqu  xmmword ptr [rbp+30h+Rect.left], xmm1
0x1801279d9  movups  xmmword ptr [rbp+30h+psa], xmm0
0x1801279dd  test    rbx, rbx
0x1801279e0  jz      loc_180127C2B
0x1801279e6  cmp     word ptr [rbx], 0Dh
0x1801279ea  jnz     loc_180127C2B
0x1801279f0  mov     rcx, [rbx+8]; struct IUnknown *
0x1801279f4  test    rcx, rcx
0x1801279f7  jz      loc_180127C2B
0x1801279fd  lea     rdx, [rsp+130h+hWnd]; HWND *
0x180127a02  mov     [rsp+130h+var_D8], rcx
0x180127a07  call    ?GetHwndFromUnknown@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; GetHwndFromUnknown(IUnknown *,HWND__ * *)
0x180127a0c  mov     ebx, eax
0x180127a0e  test    eax, eax
0x180127a10  jnz     loc_180127C30
0x180127a16  mov     rcx, [rsp+130h+var_D8]; struct IUnknown *
0x180127a1b  lea     rdx, [rsp+130h+var_D0]; struct IHTMLEventObj **
0x180127a20  call    ?GetEventFromUnknown@@YAJPEAUIUnknown@@PEAPEAUIHTMLEventObj@@@Z; GetEventFromUnknown(IUnknown *,IHTMLEventObj * *)
0x180127a25  mov     ebx, eax
0x180127a27  test    eax, eax
0x180127a29  jnz     loc_180127C30
0x180127a2f  mov     rcx, [rsp+130h+var_D0]; struct IHTMLEventObj *
0x180127a34  lea     rax, off_1805DF0B0; "propertysheetPunks"
0x180127a3b  lea     r9, [rbp+30h+psa]; struct tagVARIANT *
0x180127a3f  mov     [rsp+130h+var_110], rax; struct SExpandoInfo *
0x180127a44  lea     r8, [rbp+30h+var_B0]; int *
0x180127a48  lea     edx, [rbx+1]; unsigned int
0x180127a4b  call    ?GetParamsFromEvent@@YAJPEAUIHTMLEventObj@@IQEAJQEAUtagVARIANT@@QEBUSExpandoInfo@@@Z; GetParamsFromEvent(IHTMLEventObj *,uint,long * const,tagVARIANT * const,SExpandoInfo const * const)
0x180127a50  mov     ebx, eax
0x180127a52  test    eax, eax
0x180127a54  jnz     loc_180127C30
0x180127a5a  mov     rdi, [rbp+30h+psa+8]
0x180127a5e  mov     rcx, rdi; psa
0x180127a61  call    cs:__imp_SafeArrayGetDim
0x180127a68  nop     dword ptr [rax+rax+00h]
0x180127a6d  cmp     eax, 1
0x180127a70  jnz     loc_180127C2B
0x180127a76  lea     r8, [rsp+130h+plUbound]; plUbound
0x180127a7b  mov     edx, eax; nDim
0x180127a7d  mov     rcx, rdi; psa
0x180127a80  call    cs:__imp_SafeArrayGetUBound
0x180127a87  nop     dword ptr [rax+rax+00h]
0x180127a8c  mov     ebx, eax
0x180127a8e  test    eax, eax
0x180127a90  jnz     loc_180127C30
0x180127a96  mov     eax, [rsp+130h+plUbound]
0x180127a9a  add     eax, 1
0x180127a9d  mov     [rsp+130h+plUbound], eax
0x180127aa1  jz      short loc_180127ACC
0x180127aa3  lea     rdx, [rsp+130h+ppvData]; ppvData
0x180127aa8  mov     rcx, rdi; psa
0x180127aab  call    cs:__imp_SafeArrayAccessData
0x180127ab2  nop     dword ptr [rax+rax+00h]
0x180127ab7  mov     ebx, eax
0x180127ab9  test    eax, eax
0x180127abb  jnz     loc_180127C30
0x180127ac1  mov     edx, [rsp+130h+plUbound]
0x180127ac5  mov     r8, [rsp+130h+ppvData]
0x180127aca  jmp     short loc_180127ADF
0x180127acc  mov     edx, 1; int
0x180127ad1  lea     r8, [rsp+130h+var_D8]; struct IUnknown **
0x180127ad6  mov     [rsp+130h+plUbound], edx
0x180127ada  mov     [rsp+130h+ppvData], r8
0x180127adf  lea     r9, [rsp+130h+var_C8]; struct tagCAUUID *
0x180127ae4  call    ?GetCommonPages@CDocHostUIHandler@@IEAAJHPEAPEAUIUnknown@@PEAUtagCAUUID@@@Z; CDocHostUIHandler::GetCommonPages(int,IUnknown * *,tagCAUUID *)
0x180127ae9  mov     ebx, eax
0x180127aeb  test    eax, eax
0x180127aed  jnz     loc_180127C30
0x180127af3  mov     rcx, [rsp+130h+hWnd]
0x180127af8  jmp     short loc_180127B02
0x180127afa  mov     [rsp+130h+hWnd], rax
0x180127aff  mov     rcx, rax; hWnd
0x180127b02  call    cs:__imp_GetParent
0x180127b09  nop     dword ptr [rax+rax+00h]
0x180127b0e  test    rax, rax
0x180127b11  jnz     short loc_180127AFA
0x180127b13  call    cs:__imp_GetDesktopWindow
0x180127b1a  nop     dword ptr [rax+rax+00h]
0x180127b1f  mov     rcx, rax; hWnd
0x180127b22  lea     rdx, [rbp+30h+Rect]; lpRect
0x180127b26  call    cs:__imp_GetWindowRect
0x180127b2d  nop     dword ptr [rax+rax+00h]
0x180127b32  mov     rcx, [rsp+130h+hWnd]; hWnd
0x180127b37  lea     rdx, [rbp+30h+var_30]; lpRect
0x180127b3b  call    cs:__imp_GetWindowRect
0x180127b42  nop     dword ptr [rax+rax+00h]
0x180127b47  mov     eax, [rbp+30h+Rect.right]
0x180127b4a  mov     ecx, 2
0x180127b4f  sub     eax, [rbp+30h+Rect.left]
0x180127b52  cdq
0x180127b53  idiv    ecx
0x180127b55  sub     eax, [rbp+30h+var_30.left]
0x180127b58  mov     [rsp+130h+var_E0.cx], eax
0x180127b5c  mov     eax, [rbp+30h+Rect.bottom]
0x180127b5f  sub     eax, [rbp+30h+Rect.top]
0x180127b62  cdq
0x180127b63  idiv    ecx
0x180127b65  lea     rdx, [rsp+130h+var_E8]; struct tagSIZE *
0x180127b6a  sub     eax, [rbp+30h+var_30.top]
0x180127b6d  lea     rcx, [rsp+130h+var_E0]; struct tagSIZE *
0x180127b72  mov     [rsp+130h+var_E0.cy], eax
0x180127b76  call    ?AtlPixelToHiMetric@ATL@@YAXPEBUtagSIZE@@PEAU2@@Z; ATL::AtlPixelToHiMetric(tagSIZE const *,tagSIZE *)
0x180127b7b  mov     rax, [rsp+130h+hWnd]
0x180127b80  mov     [rbp+30h+Params.hWndOwner], rax
0x180127b84  mov     eax, [rsp+130h+var_E8.cx]
0x180127b88  mov     [rbp+30h+Params.x], eax
0x180127b8b  mov     eax, [rsp+130h+var_E8.cy]
0x180127b8f  mov     [rbp+30h+Params.y], eax
0x180127b92  mov     eax, [rsp+130h+plUbound]
0x180127b96  mov     [rbp+30h+Params.cObjects], eax
0x180127b99  mov     rax, [rsp+130h+ppvData]
0x180127b9e  mov     [rbp+30h+Params.lplpUnk], rax
0x180127ba2  mov     eax, [rsp+130h+var_C8.cElems]
0x180127ba6  mov     [rbp+30h+Params.cPages], eax
0x180127ba9  mov     rax, [rsp+130h+var_C8.pElems]
0x180127bae  mov     [rbp+30h+Params.lpPages], rax
0x180127bb2  mov     [rbp+30h+Params.cbStructSize], 48h ; 'H'
0x180127bb9  mov     [rbp+30h+Params.lpszCaption], r14
0x180127bbd  call    cs:__imp_GetUserDefaultLCID
0x180127bc4  nop     dword ptr [rax+rax+00h]
0x180127bc9  lea     rcx, [rsp+130h+ulCookie]
0x180127bce  mov     [rbp+30h+Params.dispidInitialProperty], 0FFFFFFFFh
0x180127bd5  mov     [rbp+30h+Params.lcid], eax
0x180127bd8  mov     [rsp+130h+ulCookie], r14
0x180127bdd  call    SHActivateContext
0x180127be2  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180127be9  call    cs:__imp_SetThreadDpiAwarenessContext
0x180127bf0  nop     dword ptr [rax+rax+00h]
0x180127bf5  lea     rcx, [rbp+30h+Params]; lpParams
0x180127bf9  mov     rbx, rax
0x180127bfc  call    cs:__imp_OleCreatePropertyFrameIndirect
0x180127c03  nop     dword ptr [rax+rax+00h]
0x180127c08  mov     rcx, rbx
0x180127c0b  call    cs:__imp_SetThreadDpiAwarenessContext
0x180127c12  nop     dword ptr [rax+rax+00h]
0x180127c17  mov     rcx, [rsp+130h+ulCookie]; ulCookie
0x180127c1c  mov     ebx, r14d
0x180127c1f  test    rcx, rcx
0x180127c22  jz      short loc_180127C30
0x180127c24  call    SHDeactivateContext
0x180127c29  jmp     short loc_180127C30
0x180127c2b  mov     ebx, 80070057h
0x180127c30  mov     rcx, [rsp+130h+var_C8.pElems]; pv
0x180127c35  call    cs:__imp_CoTaskMemFree
0x180127c3c  nop     dword ptr [rax+rax+00h]
0x180127c41  test    rdi, rdi
0x180127c44  jz      short loc_180127C5C
0x180127c46  cmp     [rsp+130h+ppvData], r14
0x180127c4b  jz      short loc_180127C5C
0x180127c4d  mov     rcx, rdi; psa
0x180127c50  call    cs:__imp_SafeArrayUnaccessData
0x180127c57  nop     dword ptr [rax+rax+00h]
0x180127c5c  test    rsi, rsi
0x180127c5f  jz      short loc_180127C6D
0x180127c61  xorps   xmm0, xmm0
0x180127c64  xor     eax, eax
0x180127c66  movups  xmmword ptr [rsi], xmm0
0x180127c69  mov     [rsi+10h], rax
0x180127c6d  mov     edx, 1; cvars
0x180127c72  lea     rcx, [rbp+30h+psa]; pvars
0x180127c76  call    cs:__imp_ClearVariantArray
0x180127c7d  nop     dword ptr [rax+rax+00h]
0x180127c82  lea     rcx, [rsp+130h+var_D0]
0x180127c87  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x180127c8c  mov     eax, ebx
0x180127c8e  mov     rcx, [rbp+30h+var_20]
0x180127c92  xor     rcx, rsp; StackCookie
0x180127c95  call    __security_check_cookie
0x180127c9a  lea     r11, [rsp+130h+var_10]
0x180127ca2  mov     rbx, [r11+20h]
0x180127ca6  mov     rsi, [r11+38h]
0x180127caa  mov     rsp, r11
0x180127cad  pop     r14
0x180127caf  pop     rdi
0x180127cb0  pop     rbp
0x180127cb1  retn
```
