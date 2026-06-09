# COCXHostView::SetAmbientFont(IAxWinAmbientDispatch *)

- ea: `0x140035920`
- end: `0x140035bbd`
- name: `?SetAmbientFont@COCXHostView@@AEAAXPEAUIAxWinAmbientDispatch@@@Z`
- size: `669`
- prototype: `void __fastcall(COCXHostView *__hidden this, struct IAxWinAmbientDispatch *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140035880`
- `0x1400499e8`

## callees

- `0x14000c1d0`
- `0x140035920`
- `0x14003ce40`
- `0x140062455`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x140035ab7`
- `GDI32!GetDeviceCaps` at `0x140035ab7`
- `USER32!SendMessageW` at `0x1400359c9`
- `USER32!SendMessageW` at `0x1400359c9`
- `USER32!SystemParametersInfoW` at `0x140035a8c`
- `USER32!SystemParametersInfoW` at `0x140035a8c`
- `USER32!GetDesktopWindow` at `0x140035a92`
- `USER32!GetDesktopWindow` at `0x140035a92`
- `MFC42u!__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z` at `0x140035aa9`
- `MFC42u!__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z` at `0x140035aa9`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x140035b7f`
- `MFC42u!__imp_??1CWindowDC@@UEAA@XZ` at `0x140035b7f`
- `MFC42u!__imp_?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z` at `0x140035a9b`
- `MFC42u!__imp_?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z` at `0x140035a9b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140035a54`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140035b96`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140035a54`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140035b96`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140035a1b`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140035a5f`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140035b4d`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140035a1b`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140035a5f`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140035b4d`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140035952`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140035952`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140035a10`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140035b42`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140035a10`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x140035b42`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140035a49`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140035a49`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140035965`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140035965`
- `OLEAUT32!__imp_OleCreateFontIndirect` at `0x140035b35`
- `OLEAUT32!__imp_OleCreateFontIndirect` at `0x140035b35`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall COCXHostView::SetAmbientFont(COCXHostView *this, struct IAxWinAmbientDispatch *a2)
{
  __int64 v4; // rax
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rax
  unsigned int v6; // ebx
  __int64 v7; // rax
  HWND DesktopWindow; // rax
  struct CWnd *v9; // rax
  int DeviceCaps; // r8d
  int v11; // eax
  unsigned int v12; // eax
  struct IAxWinAmbientDispatch *v13; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpvObj; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v15[24]; // [rsp+30h] [rbp-D0h] BYREF
  tagFONTDESC FontDesc; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[16]; // [rsp+78h] [rbp-88h] BYREF
  HDC hdc; // [rsp+88h] [rbp-78h]
  _BYTE v20[32]; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD pvParam[4]; // [rsp+C0h] [rbp-40h] BYREF
  SHORT v22; // [rsp+D0h] [rbp-30h]
  unsigned __int8 v23; // [rsp+D4h] [rbp-2Ch]
  unsigned __int8 v24; // [rsp+D5h] [rbp-2Bh]
  unsigned __int8 v25; // [rsp+D6h] [rbp-2Ah]
  unsigned __int8 v26; // [rsp+D7h] [rbp-29h]
  char v27; // [rsp+DCh] [rbp-24h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v15, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v15, L"COCXHostView::SetAmbientFont");
  v13 = 0;
  if ( a2 )
    goto LABEL_8;
  v4 = (*(__int64 (__fastcall **)(COCXHostView *))(*(_QWORD *)this + 544LL))(this);
  if ( v4 )
  {
    v13 = 0;
    v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))SendMessageW(*(HWND *)(v4 + 8), ATL::WM_ATLGETHOST, 0, 0);
    v17 = v5;
    if ( v5 )
      v6 = (**v5)(v5, &IID_IAxWinAmbientDispatch, &v13);
    else
      v6 = -2147467259;
    _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(&v17);
    mmcerror::SC::operator=(v15, v6);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v15)
      || (a2 = v13,
          v7 = ScCheckPointers(v20, v13, 2147549183LL),
          mmcerror::SC::operator=(v15, v7),
          mmcerror::SC::~SC((mmcerror::SC *)v20),
          (unsigned __int8)mmcerror::SC::operator bool(v15)) )
    {
LABEL_13:
      _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(&v13);
      goto LABEL_14;
    }
LABEL_8:
    memset_0(pvParam, 0, 0x5Cu);
    SystemParametersInfoW(0x1Fu, 0x5Cu, pvParam, 0);
    DesktopWindow = GetDesktopWindow();
    v9 = CWnd::FromHandle(DesktopWindow);
    CWindowDC::CWindowDC((CWindowDC *)v18, v9);
    DeviceCaps = GetDeviceCaps(hdc, 90);
    *(_QWORD *)&FontDesc.cbSizeofstruct = 40;
    FontDesc.lpstrName = (LPOLESTR)&v27;
    FontDesc.sWeight = v22;
    FontDesc.sCharset = v26;
    FontDesc.fItalic = v23;
    FontDesc.fUnderline = v24;
    FontDesc.fStrikethrough = v25;
    v11 = -pvParam[0];
    if ( pvParam[0] > 0 )
      v11 = pvParam[0];
    FontDesc.cySize.int64 = (unsigned int)(720000 * v11 / DeviceCaps);
    lpvObj = 0;
    v12 = OleCreateFontIndirect(&FontDesc, &IID_IFontDisp, &lpvObj);
    mmcerror::SC::operator=(v15, v12);
    if ( !(unsigned __int8)mmcerror::SC::operator bool(v15) )
      (*(void (__fastcall **)(struct IAxWinAmbientDispatch *, LPVOID))(*(_QWORD *)a2 + 152LL))(a2, lpvObj);
    _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(&lpvObj);
    CWindowDC::~CWindowDC((CWindowDC *)v18);
    goto LABEL_13;
  }
LABEL_14:
  mmcerror::SC::~SC((mmcerror::SC *)v15);
}

```

## disassembly

```asm
0x140035920  mov     [rsp-8+arg_10], rbx
0x140035925  mov     [rsp-8+arg_18], rdi
0x14003592a  push    rbp
0x14003592b  lea     rbp, [rsp-30h]
0x140035930  sub     rsp, 130h
0x140035937  mov     rax, cs:__security_cookie
0x14003593e  xor     rax, rsp
0x140035941  mov     [rbp+30h+var_10], rax
0x140035945  mov     rbx, rdx
0x140035948  mov     rdi, rcx
0x14003594b  xor     edx, edx
0x14003594d  lea     rcx, [rsp+130h+var_100]
0x140035952  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x140035958  nop
0x140035959  lea     rdx, aCocxhostviewSe; "COCXHostView::SetAmbientFont"
0x140035960  lea     rcx, [rsp+130h+var_100]
0x140035965  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14003596b  mov     [rsp+130h+var_110], 0
0x140035974  test    rbx, rbx
0x140035977  jnz     loc_140035A6D
0x14003597d  mov     rax, [rdi]
0x140035980  mov     rcx, rdi
0x140035983  mov     rax, [rax+220h]
0x14003598a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003598f  test    rax, rax
0x140035992  jnz     short loc_1400359B0
0x140035994  mov     rcx, [rsp+130h+var_110]
0x140035999  test    rcx, rcx
0x14003599c  jz      short loc_1400359AB
0x14003599e  mov     rax, [rcx]
0x1400359a1  mov     rax, [rax+10h]
0x1400359a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400359aa  nop
0x1400359ab  jmp     loc_140035B91
0x1400359b0  mov     [rsp+130h+var_110], 0
0x1400359b9  xor     r9d, r9d; lParam
0x1400359bc  xor     r8d, r8d; wParam
0x1400359bf  mov     edx, cs:?WM_ATLGETHOST@ATL@@3IA; Msg
0x1400359c5  mov     rcx, [rax+8]; hWnd
0x1400359c9  call    cs:__imp_SendMessageW
0x1400359cf  mov     r9, rax
0x1400359d2  mov     [rsp+130h+var_C0], rax
0x1400359d7  test    rax, rax
0x1400359da  jz      short loc_1400359FA
0x1400359dc  mov     rcx, [rax]
0x1400359df  mov     rax, [rcx]
0x1400359e2  lea     r8, [rsp+130h+var_110]
0x1400359e7  lea     rdx, IID_IAxWinAmbientDispatch
0x1400359ee  mov     rcx, r9
0x1400359f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400359f6  mov     ebx, eax
0x1400359f8  jmp     short loc_1400359FF
0x1400359fa  mov     ebx, 80004005h
0x1400359ff  lea     rcx, [rsp+130h+var_C0]
0x140035a04  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x140035a09  mov     edx, ebx
0x140035a0b  lea     rcx, [rsp+130h+var_100]
0x140035a10  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140035a16  lea     rcx, [rsp+130h+var_100]
0x140035a1b  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140035a21  test    al, al
0x140035a23  jnz     loc_140035B86
0x140035a29  mov     rbx, [rsp+130h+var_110]
0x140035a2e  mov     r8d, 8000FFFFh
0x140035a34  mov     rdx, rbx
0x140035a37  lea     rcx, [rbp+30h+var_90]
0x140035a3b  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x140035a40  nop
0x140035a41  mov     rdx, rax
0x140035a44  lea     rcx, [rsp+130h+var_100]
0x140035a49  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140035a4f  nop
0x140035a50  lea     rcx, [rbp+30h+var_90]
0x140035a54  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140035a5a  lea     rcx, [rsp+130h+var_100]
0x140035a5f  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140035a65  test    al, al
0x140035a67  jnz     loc_140035B86
0x140035a6d  mov     edi, 5Ch ; '\'
0x140035a72  mov     r8d, edi; Size
0x140035a75  xor     edx, edx; Val
0x140035a77  lea     rcx, [rbp+30h+pvParam]; void *
0x140035a7b  call    memset_0
0x140035a80  xor     r9d, r9d; fWinIni
0x140035a83  lea     r8, [rbp+30h+pvParam]; pvParam
0x140035a87  mov     edx, edi; uiParam
0x140035a89  lea     ecx, [rdi-3Dh]; uiAction
0x140035a8c  call    cs:__imp_SystemParametersInfoW
0x140035a92  call    cs:__imp_GetDesktopWindow
0x140035a98  mov     rcx, rax
0x140035a9b  call    cs:__imp_?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x140035aa1  mov     rdx, rax
0x140035aa4  lea     rcx, [rsp+130h+var_B8]
0x140035aa9  call    cs:__imp_??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x140035aaf  nop
0x140035ab0  lea     edx, [rdi-2]; index
0x140035ab3  mov     rcx, [rbp+30h+hdc]; hdc
0x140035ab7  call    cs:__imp_GetDeviceCaps
0x140035abd  mov     r8d, eax
0x140035ac0  mov     qword ptr [rsp+130h+FontDesc.cbSizeofstruct], 28h ; '('
0x140035ac9  lea     rax, [rbp+30h+var_54]
0x140035acd  mov     [rsp+130h+FontDesc.lpstrName], rax
0x140035ad2  movzx   ecx, [rbp+30h+var_60]
0x140035ad6  mov     [rsp+130h+FontDesc.sWeight], cx
0x140035adb  movzx   ecx, [rbp+30h+var_59]
0x140035adf  mov     [rsp+130h+FontDesc.sCharset], cx
0x140035ae4  movzx   ecx, [rbp+30h+var_5C]
0x140035ae8  mov     [rsp+130h+FontDesc.fItalic], ecx
0x140035aec  movzx   ecx, [rbp+30h+var_5B]
0x140035af0  mov     [rsp+130h+FontDesc.fUnderline], ecx
0x140035af4  movzx   ecx, [rbp+30h+var_5A]
0x140035af8  mov     [rsp+130h+FontDesc.fStrikethrough], ecx
0x140035afc  mov     eax, [rbp+30h+pvParam]
0x140035aff  neg     eax
0x140035b01  cmovs   eax, [rbp+30h+pvParam]
0x140035b05  imul    eax, 0AFC80h
0x140035b0b  cdq
0x140035b0c  idiv    r8d
0x140035b0f  mov     dword ptr [rsp+130h+FontDesc.cySize], eax
0x140035b13  mov     dword ptr [rsp+130h+FontDesc.cySize+4], 0
0x140035b1b  mov     [rsp+130h+lpvObj], 0
0x140035b24  lea     r8, [rsp+130h+lpvObj]; lplpvObj
0x140035b29  lea     rdx, IID_IFontDisp; riid
0x140035b30  lea     rcx, [rsp+130h+FontDesc]; lpFontDesc
0x140035b35  call    cs:__imp_OleCreateFontIndirect
0x140035b3b  mov     edx, eax
0x140035b3d  lea     rcx, [rsp+130h+var_100]
0x140035b42  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140035b48  lea     rcx, [rsp+130h+var_100]
0x140035b4d  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140035b53  test    al, al
0x140035b55  jnz     short loc_140035B6F
0x140035b57  mov     rax, [rbx]
0x140035b5a  mov     rdx, [rsp+130h+lpvObj]
0x140035b5f  mov     rcx, rbx
0x140035b62  mov     rax, [rax+98h]
0x140035b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035b6e  nop
0x140035b6f  lea     rcx, [rsp+130h+lpvObj]
0x140035b74  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x140035b79  nop
0x140035b7a  lea     rcx, [rsp+130h+var_B8]
0x140035b7f  call    cs:__imp_??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x140035b85  nop
0x140035b86  lea     rcx, [rsp+130h+var_110]
0x140035b8b  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x140035b90  nop
0x140035b91  lea     rcx, [rsp+130h+var_100]
0x140035b96  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140035b9c  mov     rcx, [rbp+30h+var_10]
0x140035ba0  xor     rcx, rsp; StackCookie
0x140035ba3  call    __security_check_cookie
0x140035ba8  lea     r11, [rsp+130h+var_s0]
0x140035bb0  mov     rbx, [r11+20h]
0x140035bb4  mov     rdi, [r11+28h]
0x140035bb8  mov     rsp, r11
0x140035bbb  pop     rbp
0x140035bbc  retn
```
