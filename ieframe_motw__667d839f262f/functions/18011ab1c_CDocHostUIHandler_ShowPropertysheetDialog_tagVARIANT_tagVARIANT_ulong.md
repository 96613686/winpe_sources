# CDocHostUIHandler::ShowPropertysheetDialog(tagVARIANT *,tagVARIANT *,ulong)

- ea: `0x18011ab1c`
- end: `0x18011ae72`
- name: `?ShowPropertysheetDialog@CDocHostUIHandler@@IEAAJPEAUtagVARIANT@@0K@Z`
- size: `854`
- prototype: `__int64 __fastcall(CDocHostUIHandler *__hidden this, struct tagVARIANT *, struct tagVARIANT *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180115fe0`

## callees

- `0x180012140`
- `0x1800396ec`
- `0x180078ec4`
- `0x18011637c`
- `0x18011642c`
- `0x180116738`
- `0x180116b44`
- `0x18011ab1c`
- `0x18054e286`
- `0x18054e310`

## import_xrefs

- `KERNEL32!GetUserDefaultLCID` at `0x18011ada6`
- `KERNEL32!GetUserDefaultLCID` at `0x18011ada6`
- `GDI32!GetDeviceCaps` at `0x18011ad1b`
- `GDI32!GetDeviceCaps` at `0x18011ad2c`
- `GDI32!GetDeviceCaps` at `0x18011ad1b`
- `GDI32!GetDeviceCaps` at `0x18011ad2c`
- `USER32!GetWindowRect` at `0x18011acc9`
- `USER32!GetWindowRect` at `0x18011acd8`
- `USER32!GetWindowRect` at `0x18011acc9`
- `USER32!GetWindowRect` at `0x18011acd8`
- `USER32!SetThreadDpiAwarenessContext` at `0x18011adc9`
- `USER32!SetThreadDpiAwarenessContext` at `0x18011addf`
- `USER32!SetThreadDpiAwarenessContext` at `0x18011adc9`
- `USER32!SetThreadDpiAwarenessContext` at `0x18011addf`
- `USER32!GetDesktopWindow` at `0x18011acbc`
- `USER32!GetDesktopWindow` at `0x18011acbc`
- `USER32!GetParent` at `0x18011acb1`
- `USER32!GetParent` at `0x18011acb1`
- `USER32!ReleaseDC` at `0x18011ad3a`
- `USER32!ReleaseDC` at `0x18011ad3a`
- `USER32!GetDC` at `0x18011ad05`
- `USER32!GetDC` at `0x18011ad05`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18011ac29`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18011ac29`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18011ac43`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18011ac43`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18011ac62`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18011ac62`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011ae18`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18011ae18`
- `OLEAUT32!__imp_OleCreatePropertyFrameIndirect` at `0x18011add6`
- `OLEAUT32!__imp_OleCreatePropertyFrameIndirect` at `0x18011add6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18011ae03`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18011ae03`
- `PROPSYS!ClearVariantArray` at `0x18011ae39`
- `PROPSYS!ClearVariantArray` at `0x18011ae39`

## pseudocode

```c
__int64 __fastcall CDocHostUIHandler::ShowPropertysheetDialog(
        CDocHostUIHandler *this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3)
{
  SAFEARRAY *parray; // rdi
  int v6; // r15d
  struct IUnknown *punkVal; // rcx
  unsigned int HwndFromUnknown; // ebx
  CDocHostUIHandler *v9; // rcx
  LONG v10; // edx
  struct IUnknown **v11; // r8
  HWND i; // rcx
  HWND Parent; // rax
  HWND DesktopWindow; // rax
  int v15; // r12d
  int v16; // r13d
  HDC DC; // rax
  HDC v18; // rbx
  int DeviceCaps; // r14d
  LCID UserDefaultLCID; // eax
  __int64 v21; // rbx
  LONG plUbound; // [rsp+30h] [rbp-D0h] BYREF
  HWND hWnd; // [rsp+38h] [rbp-C8h] BYREF
  void *ppvData; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v26; // [rsp+48h] [rbp-B8h] BYREF
  struct IHTMLEventObj *v27; // [rsp+50h] [rbp-B0h] BYREF
  tagCAUUID v28; // [rsp+58h] [rbp-A8h] BYREF
  ULONG_PTR ulCookie; // [rsp+68h] [rbp-98h] BYREF
  int v30; // [rsp+70h] [rbp-90h] BYREF
  VARIANT psa; // [rsp+78h] [rbp-88h] BYREF
  tagOCPFIPARAMS Params; // [rsp+90h] [rbp-70h] BYREF
  struct tagRECT Rect; // [rsp+E0h] [rbp-20h] BYREF
  struct tagRECT v34; // [rsp+F0h] [rbp-10h] BYREF

  hWnd = 0;
  v26 = 0;
  plUbound = 0;
  ppvData = 0;
  memset_0(&Params, 0, sizeof(Params));
  *(_QWORD *)&v28.cElems = 0;
  v28.pElems = 0;
  v27 = 0;
  parray = 0;
  v6 = 1;
  v34 = 0;
  Rect = 0;
  memset(&psa, 0, sizeof(psa));
  if ( !a2 )
    goto LABEL_22;
  if ( a2->vt != 13 )
    goto LABEL_22;
  punkVal = a2->punkVal;
  if ( !punkVal )
    goto LABEL_22;
  v26 = a2->punkVal;
  HwndFromUnknown = GetHwndFromUnknown(punkVal, &hWnd);
  if ( HwndFromUnknown )
    goto LABEL_23;
  HwndFromUnknown = GetEventFromUnknown(v26, &v27);
  if ( HwndFromUnknown )
    goto LABEL_23;
  HwndFromUnknown = GetParamsFromEvent(v27, 1u, &v30, &psa, (const struct SExpandoInfo *const)&off_18059AF60);
  if ( HwndFromUnknown )
    goto LABEL_23;
  parray = psa.parray;
  if ( SafeArrayGetDim(psa.parray) != 1 )
  {
LABEL_22:
    HwndFromUnknown = -2147024809;
    goto LABEL_23;
  }
  HwndFromUnknown = SafeArrayGetUBound(parray, 1u, &plUbound);
  if ( !HwndFromUnknown )
  {
    if ( ++plUbound )
    {
      HwndFromUnknown = SafeArrayAccessData(parray, &ppvData);
      if ( HwndFromUnknown )
        goto LABEL_23;
      v10 = plUbound;
      v11 = (struct IUnknown **)ppvData;
    }
    else
    {
      v10 = 1;
      v11 = &v26;
      plUbound = 1;
      ppvData = &v26;
    }
    HwndFromUnknown = CDocHostUIHandler::GetCommonPages(v9, v10, v11, &v28);
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
      GetWindowRect(hWnd, &v34);
      v15 = (Rect.right - Rect.left) / 2 - v34.left;
      v16 = (Rect.bottom - Rect.top) / 2 - v34.top;
      DC = GetDC(0);
      v18 = DC;
      if ( DC )
      {
        DeviceCaps = GetDeviceCaps(DC, 88);
        v6 = GetDeviceCaps(v18, 90);
        ReleaseDC(0, v18);
      }
      else
      {
        DeviceCaps = 1;
      }
      Params.hWndOwner = hWnd;
      Params.cbStructSize = 72;
      Params.x = ((DeviceCaps >> 1) + 2540 * v15) / DeviceCaps;
      HIDWORD(Params.lpszCaption) = 0;
      *(_QWORD *)&Params.y = (unsigned int)(((v6 >> 1) + 2540 * v16) / v6);
      Params.cObjects = plUbound;
      Params.lplpUnk = (LPUNKNOWN *)ppvData;
      Params.cPages = v28.cElems;
      Params.lpPages = v28.pElems;
      UserDefaultLCID = GetUserDefaultLCID();
      Params.dispidInitialProperty = -1;
      Params.lcid = UserDefaultLCID;
      ulCookie = 0;
      SHActivateContext(&ulCookie);
      v21 = SetThreadDpiAwarenessContext(-2);
      OleCreatePropertyFrameIndirect(&Params);
      SetThreadDpiAwarenessContext(v21);
      HwndFromUnknown = 0;
      if ( ulCookie )
        SHDeactivateContext(ulCookie);
    }
  }
LABEL_23:
  CoTaskMemFree(v28.pElems);
  if ( parray && ppvData )
    SafeArrayUnaccessData(parray);
  if ( a3 )
  {
    *(_OWORD *)&a3->vt = 0;
    a3->pRecInfo = 0;
  }
  ClearVariantArray(&psa, 1u);
  ATL::CComPtr<IPrivacIEDatabase>::Release(&v27);
  return HwndFromUnknown;
}

```

## disassembly

```asm
0x18011ab1c  mov     [rsp-8+arg_0], rbx
0x18011ab21  push    rbp
0x18011ab22  push    rsi
0x18011ab23  push    rdi
0x18011ab24  push    r12
0x18011ab26  push    r13
0x18011ab28  push    r14
0x18011ab2a  push    r15
0x18011ab2c  lea     rbp, [rsp-10h]
0x18011ab31  sub     rsp, 110h
0x18011ab38  mov     rax, cs:__security_cookie
0x18011ab3f  xor     rax, rsp
0x18011ab42  mov     [rbp+40h+var_40], rax
0x18011ab46  xor     r14d, r14d
0x18011ab49  lea     rcx, [rbp+40h+Params]; void *
0x18011ab4d  mov     rsi, r8
0x18011ab50  mov     [rsp+140h+hWnd], r14
0x18011ab55  mov     rbx, rdx
0x18011ab58  mov     [rsp+140h+var_F8], r14
0x18011ab5d  xor     edx, edx; Val
0x18011ab5f  mov     [rsp+140h+plUbound], r14d
0x18011ab64  lea     r8d, [r14+48h]; Size
0x18011ab68  mov     [rsp+140h+ppvData], r14
0x18011ab6d  call    memset_0
0x18011ab72  xor     eax, eax
0x18011ab74  mov     qword ptr [rsp+140h+var_E8.cElems], r14
0x18011ab79  mov     [rsp+140h+var_E8.pElems], r14
0x18011ab7e  xorps   xmm0, xmm0
0x18011ab81  mov     [rsp+140h+var_F0], r14
0x18011ab86  xorps   xmm1, xmm1
0x18011ab89  mov     [rbp+40h+var_B8], rax
0x18011ab8d  mov     edi, r14d
0x18011ab90  lea     r15d, [r14+1]
0x18011ab94  movdqu  xmmword ptr [rbp+40h+var_50.left], xmm0
0x18011ab99  movdqu  xmmword ptr [rbp+40h+Rect.left], xmm1
0x18011ab9e  movups  xmmword ptr [rsp+140h+psa], xmm0
0x18011aba3  test    rbx, rbx
0x18011aba6  jz      loc_18011ADF9
0x18011abac  cmp     word ptr [rbx], 0Dh
0x18011abb0  jnz     loc_18011ADF9
0x18011abb6  mov     rcx, [rbx+8]; struct IUnknown *
0x18011abba  test    rcx, rcx
0x18011abbd  jz      loc_18011ADF9
0x18011abc3  lea     rdx, [rsp+140h+hWnd]; HWND *
0x18011abc8  mov     [rsp+140h+var_F8], rcx
0x18011abcd  call    ?GetHwndFromUnknown@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; GetHwndFromUnknown(IUnknown *,HWND__ * *)
0x18011abd2  mov     ebx, eax
0x18011abd4  test    eax, eax
0x18011abd6  jnz     loc_18011ADFE
0x18011abdc  mov     rcx, [rsp+140h+var_F8]; struct IUnknown *
0x18011abe1  lea     rdx, [rsp+140h+var_F0]; struct IHTMLEventObj **
0x18011abe6  call    ?GetEventFromUnknown@@YAJPEAUIUnknown@@PEAPEAUIHTMLEventObj@@@Z; GetEventFromUnknown(IUnknown *,IHTMLEventObj * *)
0x18011abeb  mov     ebx, eax
0x18011abed  test    eax, eax
0x18011abef  jnz     loc_18011ADFE
0x18011abf5  mov     rcx, [rsp+140h+var_F0]; struct IHTMLEventObj *
0x18011abfa  lea     rax, off_18059AF60; "propertysheetPunks"
0x18011ac01  lea     r9, [rsp+140h+psa]; struct tagVARIANT *
0x18011ac06  mov     [rsp+140h+var_120], rax; struct SExpandoInfo *
0x18011ac0b  lea     r8, [rsp+140h+var_D0]; int *
0x18011ac10  mov     edx, r15d; unsigned int
0x18011ac13  call    ?GetParamsFromEvent@@YAJPEAUIHTMLEventObj@@IQEAJQEAUtagVARIANT@@QEBUSExpandoInfo@@@Z; GetParamsFromEvent(IHTMLEventObj *,uint,long * const,tagVARIANT * const,SExpandoInfo const * const)
0x18011ac18  mov     ebx, eax
0x18011ac1a  test    eax, eax
0x18011ac1c  jnz     loc_18011ADFE
0x18011ac22  mov     rdi, [rbp+40h+psa+8]
0x18011ac26  mov     rcx, rdi; psa
0x18011ac29  call    cs:__imp_SafeArrayGetDim
0x18011ac2f  cmp     eax, r15d
0x18011ac32  jnz     loc_18011ADF9
0x18011ac38  lea     r8, [rsp+140h+plUbound]; plUbound
0x18011ac3d  mov     edx, r15d; nDim
0x18011ac40  mov     rcx, rdi; psa
0x18011ac43  call    cs:__imp_SafeArrayGetUBound
0x18011ac49  mov     ebx, eax
0x18011ac4b  test    eax, eax
0x18011ac4d  jnz     loc_18011ADFE
0x18011ac53  add     [rsp+140h+plUbound], r15d
0x18011ac58  jz      short loc_18011AC7D
0x18011ac5a  lea     rdx, [rsp+140h+ppvData]; ppvData
0x18011ac5f  mov     rcx, rdi; psa
0x18011ac62  call    cs:__imp_SafeArrayAccessData
0x18011ac68  mov     ebx, eax
0x18011ac6a  test    eax, eax
0x18011ac6c  jnz     loc_18011ADFE
0x18011ac72  mov     edx, [rsp+140h+plUbound]
0x18011ac76  mov     r8, [rsp+140h+ppvData]
0x18011ac7b  jmp     short loc_18011AC8E
0x18011ac7d  mov     edx, r15d; int
0x18011ac80  lea     r8, [rsp+140h+var_F8]; struct IUnknown **
0x18011ac85  mov     [rsp+140h+plUbound], edx
0x18011ac89  mov     [rsp+140h+ppvData], r8
0x18011ac8e  lea     r9, [rsp+140h+var_E8]; struct tagCAUUID *
0x18011ac93  call    ?GetCommonPages@CDocHostUIHandler@@IEAAJHPEAPEAUIUnknown@@PEAUtagCAUUID@@@Z; CDocHostUIHandler::GetCommonPages(int,IUnknown * *,tagCAUUID *)
0x18011ac98  mov     ebx, eax
0x18011ac9a  test    eax, eax
0x18011ac9c  jnz     loc_18011ADFE
0x18011aca2  mov     rcx, [rsp+140h+hWnd]
0x18011aca7  jmp     short loc_18011ACB1
0x18011aca9  mov     [rsp+140h+hWnd], rax
0x18011acae  mov     rcx, rax; hWnd
0x18011acb1  call    cs:__imp_GetParent
0x18011acb7  test    rax, rax
0x18011acba  jnz     short loc_18011ACA9
0x18011acbc  call    cs:__imp_GetDesktopWindow
0x18011acc2  mov     rcx, rax; hWnd
0x18011acc5  lea     rdx, [rbp+40h+Rect]; lpRect
0x18011acc9  call    cs:__imp_GetWindowRect
0x18011accf  mov     rcx, [rsp+140h+hWnd]; hWnd
0x18011acd4  lea     rdx, [rbp+40h+var_50]; lpRect
0x18011acd8  call    cs:__imp_GetWindowRect
0x18011acde  mov     eax, [rbp+40h+Rect.right]
0x18011ace1  mov     ecx, 2
0x18011ace6  sub     eax, [rbp+40h+Rect.left]
0x18011ace9  cdq
0x18011acea  idiv    ecx
0x18011acec  mov     r12d, eax
0x18011acef  mov     eax, [rbp+40h+Rect.bottom]
0x18011acf2  sub     eax, [rbp+40h+Rect.top]
0x18011acf5  sub     r12d, [rbp+40h+var_50.left]
0x18011acf9  cdq
0x18011acfa  idiv    ecx
0x18011acfc  xor     ecx, ecx; hWnd
0x18011acfe  mov     r13d, eax
0x18011ad01  sub     r13d, [rbp+40h+var_50.top]
0x18011ad05  call    cs:__imp_GetDC
0x18011ad0b  mov     rbx, rax
0x18011ad0e  test    rax, rax
0x18011ad11  jz      short loc_18011AD42
0x18011ad13  mov     edx, 58h ; 'X'; index
0x18011ad18  mov     rcx, rax; hdc
0x18011ad1b  call    cs:__imp_GetDeviceCaps
0x18011ad21  mov     edx, 5Ah ; 'Z'; index
0x18011ad26  mov     rcx, rbx; hdc
0x18011ad29  mov     r14d, eax
0x18011ad2c  call    cs:__imp_GetDeviceCaps
0x18011ad32  mov     rdx, rbx; hDC
0x18011ad35  xor     ecx, ecx; hWnd
0x18011ad37  mov     r15d, eax
0x18011ad3a  call    cs:__imp_ReleaseDC
0x18011ad40  jmp     short loc_18011AD45
0x18011ad42  mov     r14d, r15d
0x18011ad45  mov     rax, [rsp+140h+hWnd]
0x18011ad4a  mov     ecx, r14d
0x18011ad4d  mov     [rbp+40h+Params.hWndOwner], rax
0x18011ad51  sar     ecx, 1
0x18011ad53  imul    eax, r12d, 9ECh
0x18011ad5a  mov     [rbp+40h+Params.cbStructSize], 48h ; 'H'
0x18011ad61  add     eax, ecx
0x18011ad63  mov     ecx, r15d
0x18011ad66  cdq
0x18011ad67  sar     ecx, 1
0x18011ad69  idiv    r14d
0x18011ad6c  xor     r14d, r14d
0x18011ad6f  mov     [rbp+40h+Params.x], eax
0x18011ad72  imul    eax, r13d, 9ECh
0x18011ad79  mov     [rbp+40h+Params.lpszCaption], r14
0x18011ad7d  add     eax, ecx
0x18011ad7f  cdq
0x18011ad80  idiv    r15d
0x18011ad83  mov     [rbp+40h+Params.y], eax
0x18011ad86  mov     eax, [rsp+140h+plUbound]
0x18011ad8a  mov     [rbp+40h+Params.cObjects], eax
0x18011ad8d  mov     rax, [rsp+140h+ppvData]
0x18011ad92  mov     [rbp+40h+Params.lplpUnk], rax
0x18011ad96  mov     eax, [rsp+140h+var_E8.cElems]
0x18011ad9a  mov     [rbp+40h+Params.cPages], eax
0x18011ad9d  mov     rax, [rsp+140h+var_E8.pElems]
0x18011ada2  mov     [rbp+40h+Params.lpPages], rax
0x18011ada6  call    cs:__imp_GetUserDefaultLCID
0x18011adac  lea     rcx, [rsp+140h+ulCookie]
0x18011adb1  mov     [rbp+40h+Params.dispidInitialProperty], 0FFFFFFFFh
0x18011adb8  mov     [rbp+40h+Params.lcid], eax
0x18011adbb  mov     [rsp+140h+ulCookie], r14
0x18011adc0  call    SHActivateContext
0x18011adc5  lea     rcx, [r14-2]
0x18011adc9  call    cs:__imp_SetThreadDpiAwarenessContext
0x18011adcf  lea     rcx, [rbp+40h+Params]; lpParams
0x18011add3  mov     rbx, rax
0x18011add6  call    cs:__imp_OleCreatePropertyFrameIndirect
0x18011addc  mov     rcx, rbx
0x18011addf  call    cs:__imp_SetThreadDpiAwarenessContext
0x18011ade5  mov     rcx, [rsp+140h+ulCookie]; ulCookie
0x18011adea  mov     ebx, r14d
0x18011aded  test    rcx, rcx
0x18011adf0  jz      short loc_18011ADFE
0x18011adf2  call    SHDeactivateContext
0x18011adf7  jmp     short loc_18011ADFE
0x18011adf9  mov     ebx, 80070057h
0x18011adfe  mov     rcx, [rsp+140h+var_E8.pElems]; pv
0x18011ae03  call    cs:__imp_CoTaskMemFree
0x18011ae09  test    rdi, rdi
0x18011ae0c  jz      short loc_18011AE1E
0x18011ae0e  cmp     [rsp+140h+ppvData], r14
0x18011ae13  jz      short loc_18011AE1E
0x18011ae15  mov     rcx, rdi; psa
0x18011ae18  call    cs:__imp_SafeArrayUnaccessData
0x18011ae1e  test    rsi, rsi
0x18011ae21  jz      short loc_18011AE2F
0x18011ae23  xorps   xmm0, xmm0
0x18011ae26  xor     eax, eax
0x18011ae28  movups  xmmword ptr [rsi], xmm0
0x18011ae2b  mov     [rsi+10h], rax
0x18011ae2f  mov     edx, 1; cvars
0x18011ae34  lea     rcx, [rsp+140h+psa]; pvars
0x18011ae39  call    cs:__imp_ClearVariantArray
0x18011ae3f  lea     rcx, [rsp+140h+var_F0]
0x18011ae44  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x18011ae49  mov     eax, ebx
0x18011ae4b  mov     rcx, [rbp+40h+var_40]
0x18011ae4f  xor     rcx, rsp; StackCookie
0x18011ae52  call    __security_check_cookie
0x18011ae57  mov     rbx, [rsp+140h+arg_0]
0x18011ae5f  add     rsp, 110h
0x18011ae66  pop     r15
0x18011ae68  pop     r14
0x18011ae6a  pop     r13
0x18011ae6c  pop     r12
0x18011ae6e  pop     rdi
0x18011ae6f  pop     rsi
0x18011ae70  pop     rbp
0x18011ae71  retn
```
