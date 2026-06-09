# CBookmarksNavPane::Create(HWND__ *)

- ea: `0x18000da10`
- end: `0x18000dd8e`
- name: `?Create@CBookmarksNavPane@@UEAAHPEAUHWND__@@@Z`
- size: `894`
- prototype: `__int64 __fastcall(CBookmarksNavPane *__hidden this, HWND hWndParent)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005a4c`
- `0x18000ad54`
- `0x18000ae1c`
- `0x18000da10`
- `0x18000e190`
- `0x18000e784`
- `0x1800107d8`
- `0x180010b14`
- `0x180010bc0`
- `0x180010fcc`
- `0x180051cfc`
- `0x180078010`

## import_xrefs

- `USER32!SetWindowLongPtrA` at `0x18000db9a`
- `USER32!SetWindowLongPtrA` at `0x18000dbf1`
- `USER32!SetWindowLongPtrA` at `0x18000dc32`
- `USER32!SetWindowLongPtrA` at `0x18000dc56`
- `USER32!SetWindowLongPtrA` at `0x18000dc7a`
- `USER32!SetWindowLongPtrA` at `0x18000db9a`
- `USER32!SetWindowLongPtrA` at `0x18000dbf1`
- `USER32!SetWindowLongPtrA` at `0x18000dc32`
- `USER32!SetWindowLongPtrA` at `0x18000dc56`
- `USER32!SetWindowLongPtrA` at `0x18000dc7a`
- `USER32!SendMessageA` at `0x18000dbb3`
- `USER32!SendMessageA` at `0x18000dc9e`
- `USER32!SendMessageA` at `0x18000dcbc`
- `USER32!SendMessageA` at `0x18000dcdd`
- `USER32!SendMessageA` at `0x18000dcfe`
- `USER32!SendMessageA` at `0x18000dd1f`
- `USER32!SendMessageA` at `0x18000dd40`
- `USER32!SendMessageA` at `0x18000dd61`
- `USER32!SendMessageA` at `0x18000dbb3`
- `USER32!SendMessageA` at `0x18000dc9e`
- `USER32!SendMessageA` at `0x18000dcbc`
- `USER32!SendMessageA` at `0x18000dcdd`
- `USER32!SendMessageA` at `0x18000dcfe`
- `USER32!SendMessageA` at `0x18000dd1f`
- `USER32!SendMessageA` at `0x18000dd40`
- `USER32!SendMessageA` at `0x18000dd61`
- `ADVAPI32!RegCloseKey` at `0x18000daaf`
- `ADVAPI32!RegCloseKey` at `0x18000daaf`
- `ADVAPI32!RegQueryValueExA` at `0x18000da97`
- `ADVAPI32!RegQueryValueExA` at `0x18000da97`
- `ADVAPI32!RegOpenKeyExA` at `0x18000da6a`
- `ADVAPI32!RegOpenKeyExA` at `0x18000da6a`

## string_xrefs

- `0x18000da50`: `Software\Microsoft\Accessibility`

## pseudocode

```c
__int64 __fastcall CBookmarksNavPane::Create(CBookmarksNavPane *this, HWND hWndParent)
{
  __int64 v4; // rbx
  HINSTANCE ResourceInstance; // rax
  __int64 DialogParamW; // rax
  int v7; // r14d
  HINSTANCE v8; // rax
  __int64 result; // rax
  __int64 v10; // rcx
  LRESULT (__stdcall *WndProc)(HWND, UINT, WPARAM, LPARAM); // rax
  HWND v12; // rcx
  LRESULT (__stdcall *v13)(HWND, UINT, WPARAM, LPARAM); // rax
  HWND v14; // rcx
  LRESULT (__stdcall *v15)(HWND, UINT, WPARAM, LPARAM); // rax
  HWND v16; // rcx
  HFONT AccessableContentFont; // rax
  HFONT v18; // rax
  HFONT v19; // rax
  HFONT v20; // rax
  HFONT v21; // rax
  HFONT v22; // rax
  HFONT v23; // rax
  tagLVCOLUMNW v24; // [rsp+30h] [rbp-40h] BYREF
  unsigned int Data; // [rsp+A0h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+48h] BYREF

  if ( *((_QWORD *)this + 1) )
    return 1;
  hKey = 0;
  Data = 100;
  cbData = 4;
  v4 = 2020;
  if ( !RegOpenKeyExA(HKEY_CURRENT_USER, "Software\\Microsoft\\Accessibility", 0, 0x20019u, &hKey) )
  {
    if ( !RegQueryValueExA(hKey, "TextScaleFactor", 0, 0, (LPBYTE)&Data, &cbData) && Data > 0x64 )
      v4 = 2021;
    RegCloseKey(hKey);
  }
  ResourceInstance = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
  DialogParamW = IsolationAwareCreateDialogParamW(
                   ResourceInstance,
                   (LPCWSTR)v4,
                   hWndParent,
                   (DLGPROC)CBookmarksNavPane::s_DialogProc,
                   (LPARAM)this);
  *((_QWORD *)this + 1) = DialogParamW;
  v7 = 1;
  if ( DialogParamW
    || (v8 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module),
        result = IsolationAwareCreateDialogParamA(
                   v8,
                   (LPCSTR)v4,
                   hWndParent,
                   (DLGPROC)CBookmarksNavPane::s_DialogProc,
                   (LPARAM)this),
        v7 = 0,
        (*((_QWORD *)this + 1) = result) != 0) )
  {
    CBookmarksNavPane::InitDlgItemArray(this);
    v10 = *((_QWORD *)this + 4);
    memset(&v24.cx + 1, 0, 44);
    *(_QWORD *)&v24.mask = 3;
    v24.cx = 1500;
    W_EnableUnicode(v10, 0);
    W_ListView_InsertColumn_fn(*((HWND *)this + 4), 0, &v24);
    WndProc = W_GetWndProc(*((HWND *)this + 4), v7);
    v12 = (HWND)*((_QWORD *)this + 4);
    CBookmarksNavPane::s_lpfnlListViewWndProc = WndProc;
    W_SubClassWindow(v12, (__int64)CBookmarksNavPane::s_ListViewProc, v7);
    SetWindowLongPtrA(*((HWND *)this + 4), -21, (LONG_PTR)this);
    SendMessageA(*((HWND *)this + 52), 0xC5u, 0x103u, 0);
    v13 = W_GetWndProc(*((HWND *)this + 52), v7);
    v14 = (HWND)*((_QWORD *)this + 52);
    CBookmarksNavPane::s_lpfnlCurrentTopicEditProc = v13;
    W_SubClassWindow(v14, (__int64)CBookmarksNavPane::s_CurrentTopicEditProc, v7);
    SetWindowLongPtrA(*((HWND *)this + 52), -21, (LONG_PTR)this);
    v15 = W_GetWndProc(*((HWND *)this + 16), v7);
    v16 = (HWND)*((_QWORD *)this + 16);
    CBookmarksNavPane::s_lpfnlGenericBtnProc = v15;
    W_SubClassWindow(v16, (__int64)CBookmarksNavPane::s_GenericBtnProc, v7);
    SetWindowLongPtrA(*((HWND *)this + 16), -21, (LONG_PTR)this);
    W_SubClassWindow(*((HWND *)this + 28), (__int64)CBookmarksNavPane::s_GenericBtnProc, v7);
    SetWindowLongPtrA(*((HWND *)this + 28), -21, (LONG_PTR)this);
    W_SubClassWindow(*((HWND *)this + 64), (__int64)CBookmarksNavPane::s_GenericBtnProc, v7);
    SetWindowLongPtrA(*((HWND *)this + 64), -21, (LONG_PTR)this);
    AccessableContentFont = CHHWinType::GetAccessableContentFont(*((CHHWinType **)this + 89));
    SendMessageA(*((HWND *)this + 52), 0x30u, (WPARAM)AccessableContentFont, 0);
    v18 = CHHWinType::GetAccessableContentFont(*((CHHWinType **)this + 89));
    SendMessageA(*((HWND *)this + 4), 0x30u, (WPARAM)v18, 0);
    v19 = CHHWinType::GetAccessableContentFont(*((CHHWinType **)this + 89));
    SendMessageA(*((HWND *)this + 16), 0x30u, (WPARAM)v19, 0);
    v20 = CHHWinType::GetAccessableContentFont(*((CHHWinType **)this + 89));
    SendMessageA(*((HWND *)this + 28), 0x30u, (WPARAM)v20, 0);
    v21 = CHHWinType::GetAccessableContentFont(*((CHHWinType **)this + 89));
    SendMessageA(*((HWND *)this + 64), 0x30u, (WPARAM)v21, 0);
    v22 = CHHWinType::GetAccessableContentFont(*((CHHWinType **)this + 89));
    SendMessageA(*((HWND *)this + 76), 0x30u, (WPARAM)v22, 0);
    v23 = CHHWinType::GetAccessableContentFont(*((CHHWinType **)this + 89));
    SendMessageA(*((HWND *)this + 40), 0x30u, (WPARAM)v23, 0);
    CBookmarksNavPane::LoadBookmarks(this);
    (*(void (__fastcall **)(CBookmarksNavPane *))(*(_QWORD *)this + 64LL))(this);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000da10  push    rbp
0x18000da12  push    rbx
0x18000da13  push    rsi
0x18000da14  push    rdi
0x18000da15  push    r14
0x18000da17  mov     rbp, rsp
0x18000da1a  sub     rsp, 70h
0x18000da1e  cmp     qword ptr [rcx+8], 0
0x18000da23  mov     rsi, rdx
0x18000da26  mov     rdi, rcx
0x18000da29  jnz     loc_18000DD7E
0x18000da2f  lea     rax, [rbp+hKey]
0x18000da33  mov     [rbp+hKey], 0
0x18000da3b  mov     r9d, 20019h; samDesired
0x18000da41  mov     [rsp+70h+phkResult], rax; phkResult
0x18000da46  xor     r8d, r8d; ulOptions
0x18000da49  mov     [rbp+Data], 64h ; 'd'
0x18000da50  lea     rdx, SubKey; "Software\\Microsoft\\Accessibility"
0x18000da57  mov     [rbp+cbData], 4
0x18000da5e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000da65  mov     ebx, 7E4h
0x18000da6a  call    cs:__imp_RegOpenKeyExA
0x18000da70  test    eax, eax
0x18000da72  jnz     short loc_18000DAB5
0x18000da74  mov     rcx, [rbp+hKey]; hKey
0x18000da78  lea     rax, [rbp+cbData]
0x18000da7c  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18000da81  lea     rdx, ValueName; "TextScaleFactor"
0x18000da88  lea     rax, [rbp+Data]
0x18000da8c  xor     r9d, r9d; lpType
0x18000da8f  xor     r8d, r8d; lpReserved
0x18000da92  mov     [rsp+70h+phkResult], rax; lpData
0x18000da97  call    cs:__imp_RegQueryValueExA
0x18000da9d  test    eax, eax
0x18000da9f  jnz     short loc_18000DAAB
0x18000daa1  cmp     [rbp+Data], 64h ; 'd'
0x18000daa5  lea     eax, [rbx+1]
0x18000daa8  cmova   ebx, eax
0x18000daab  mov     rcx, [rbp+hKey]; hKey
0x18000daaf  call    cs:__imp_RegCloseKey
0x18000dab5  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x18000dabc  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18000dac1  mov     rcx, rax; hInstance
0x18000dac4  mov     [rsp+70h+phkResult], rdi; LPARAM
0x18000dac9  lea     r9, ?s_DialogProc@CBookmarksNavPane@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18000dad0  mov     r8, rsi; hWndParent
0x18000dad3  mov     rdx, rbx; lpTemplateName
0x18000dad6  call    IsolationAwareCreateDialogParamW
0x18000dadb  mov     [rdi+8], rax
0x18000dadf  mov     r14d, 1
0x18000dae5  test    rax, rax
0x18000dae8  jnz     short loc_18000DB20
0x18000daea  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x18000daf1  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18000daf6  mov     rcx, rax; hInstance
0x18000daf9  mov     [rsp+70h+phkResult], rdi; LPARAM
0x18000dafe  lea     r9, ?s_DialogProc@CBookmarksNavPane@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18000db05  mov     r8, rsi; hWndParent
0x18000db08  mov     rdx, rbx; lpTemplateName
0x18000db0b  call    IsolationAwareCreateDialogParamA
0x18000db10  xor     r14d, r14d
0x18000db13  mov     [rdi+8], rax
0x18000db17  test    rax, rax
0x18000db1a  jz      loc_18000DD83
0x18000db20  mov     rcx, rdi; this
0x18000db23  call    ?InitDlgItemArray@CBookmarksNavPane@@AEAAXXZ; CBookmarksNavPane::InitDlgItemArray(void)
0x18000db28  mov     rcx, [rdi+20h]
0x18000db2c  xorps   xmm0, xmm0
0x18000db2f  movups  xmmword ptr [rbp+var_40.mask], xmm0
0x18000db33  xor     eax, eax
0x18000db35  mov     qword ptr [rbp+var_40.mask], 3
0x18000db3d  xor     edx, edx
0x18000db3f  mov     [rbp+var_40.cx], 5DCh
0x18000db46  movups  xmmword ptr [rbp+var_40.pszText], xmm0
0x18000db4a  mov     qword ptr [rbp+var_40.cxIdeal], rax
0x18000db4e  movups  xmmword ptr [rbp+var_40.iImage], xmm0
0x18000db52  call    ?W_EnableUnicode@@YAHPEAUHWND__@@W4CCTLWINTYPE@@@Z; W_EnableUnicode(HWND__ *,CCTLWINTYPE)
0x18000db57  mov     rcx, [rdi+20h]; hWnd
0x18000db5b  lea     r8, [rbp+var_40]; struct tagLVCOLUMNW *
0x18000db5f  xor     edx, edx; int
0x18000db61  call    ?W_ListView_InsertColumn_fn@@YAHPEAUHWND__@@HPEAUtagLVCOLUMNW@@@Z; W_ListView_InsertColumn_fn(HWND__ *,int,tagLVCOLUMNW *)
0x18000db66  mov     rcx, [rdi+20h]; HWND
0x18000db6a  mov     edx, r14d; int
0x18000db6d  call    ?W_GetWndProc@@YAP6A_JPEAUHWND__@@I_K_J@Z0H@Z; W_GetWndProc(HWND__ *,int)
0x18000db72  mov     rcx, [rdi+20h]; HWND
0x18000db76  lea     rdx, ?s_ListViewProc@CBookmarksNavPane@@CA_JPEAUHWND__@@I_K_J@Z; __int64
0x18000db7d  mov     r8d, r14d; int
0x18000db80  mov     cs:?s_lpfnlListViewWndProc@CBookmarksNavPane@@1P6A_JPEAUHWND__@@I_K_J@ZEA, rax; __int64 (*CBookmarksNavPane::s_lpfnlListViewWndProc)(HWND__ *,uint,unsigned __int64,__int64)
0x18000db87  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x18000db8c  mov     rcx, [rdi+20h]; hWnd
0x18000db90  mov     esi, 0FFFFFFEBh
0x18000db95  mov     edx, esi; nIndex
0x18000db97  mov     r8, rdi; dwNewLong
0x18000db9a  call    cs:__imp_SetWindowLongPtrA
0x18000dba0  mov     rcx, [rdi+1A0h]; hWnd
0x18000dba7  mov     edx, 0C5h; Msg
0x18000dbac  xor     r9d, r9d; lParam
0x18000dbaf  lea     r8d, [rdx+3Eh]; wParam
0x18000dbb3  call    cs:__imp_SendMessageA
0x18000dbb9  mov     rcx, [rdi+1A0h]; HWND
0x18000dbc0  mov     edx, r14d; int
0x18000dbc3  call    ?W_GetWndProc@@YAP6A_JPEAUHWND__@@I_K_J@Z0H@Z; W_GetWndProc(HWND__ *,int)
0x18000dbc8  mov     rcx, [rdi+1A0h]; HWND
0x18000dbcf  lea     rdx, ?s_CurrentTopicEditProc@CBookmarksNavPane@@CA_JPEAUHWND__@@I_K_J@Z; __int64
0x18000dbd6  mov     r8d, r14d; int
0x18000dbd9  mov     cs:?s_lpfnlCurrentTopicEditProc@CBookmarksNavPane@@1P6A_JPEAUHWND__@@I_K_J@ZEA, rax; __int64 (*CBookmarksNavPane::s_lpfnlCurrentTopicEditProc)(HWND__ *,uint,unsigned __int64,__int64)
0x18000dbe0  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x18000dbe5  mov     rcx, [rdi+1A0h]; hWnd
0x18000dbec  mov     r8, rdi; dwNewLong
0x18000dbef  mov     edx, esi; nIndex
0x18000dbf1  call    cs:__imp_SetWindowLongPtrA
0x18000dbf7  mov     rcx, [rdi+80h]; HWND
0x18000dbfe  mov     edx, r14d; int
0x18000dc01  call    ?W_GetWndProc@@YAP6A_JPEAUHWND__@@I_K_J@Z0H@Z; W_GetWndProc(HWND__ *,int)
0x18000dc06  mov     rcx, [rdi+80h]; HWND
0x18000dc0d  lea     rbx, ?s_GenericBtnProc@CBookmarksNavPane@@CA_JPEAUHWND__@@I_K_J@Z; CBookmarksNavPane::s_GenericBtnProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000dc14  mov     rdx, rbx; __int64
0x18000dc17  mov     cs:?s_lpfnlGenericBtnProc@CBookmarksNavPane@@1P6A_JPEAUHWND__@@I_K_J@ZEA, rax; __int64 (*CBookmarksNavPane::s_lpfnlGenericBtnProc)(HWND__ *,uint,unsigned __int64,__int64)
0x18000dc1e  mov     r8d, r14d; int
0x18000dc21  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x18000dc26  mov     rcx, [rdi+80h]; hWnd
0x18000dc2d  mov     r8, rdi; dwNewLong
0x18000dc30  mov     edx, esi; nIndex
0x18000dc32  call    cs:__imp_SetWindowLongPtrA
0x18000dc38  mov     rcx, [rdi+0E0h]; HWND
0x18000dc3f  mov     r8d, r14d; int
0x18000dc42  mov     rdx, rbx; __int64
0x18000dc45  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x18000dc4a  mov     rcx, [rdi+0E0h]; hWnd
0x18000dc51  mov     r8, rdi; dwNewLong
0x18000dc54  mov     edx, esi; nIndex
0x18000dc56  call    cs:__imp_SetWindowLongPtrA
0x18000dc5c  mov     rcx, [rdi+200h]; HWND
0x18000dc63  mov     r8d, r14d; int
0x18000dc66  mov     rdx, rbx; __int64
0x18000dc69  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x18000dc6e  mov     rcx, [rdi+200h]; hWnd
0x18000dc75  mov     r8, rdi; dwNewLong
0x18000dc78  mov     edx, esi; nIndex
0x18000dc7a  call    cs:__imp_SetWindowLongPtrA
0x18000dc80  mov     rcx, [rdi+2C8h]; this
0x18000dc87  call    ?GetAccessableContentFont@CHHWinType@@QEAAPEAUHFONT__@@XZ; CHHWinType::GetAccessableContentFont(void)
0x18000dc8c  xor     r9d, r9d; lParam
0x18000dc8f  lea     ebx, [rsi+45h]
0x18000dc92  mov     r8, rax; wParam
0x18000dc95  mov     rcx, [rdi+1A0h]; hWnd
0x18000dc9c  mov     edx, ebx; Msg
0x18000dc9e  call    cs:__imp_SendMessageA
0x18000dca4  mov     rcx, [rdi+2C8h]; this
0x18000dcab  call    ?GetAccessableContentFont@CHHWinType@@QEAAPEAUHFONT__@@XZ; CHHWinType::GetAccessableContentFont(void)
0x18000dcb0  mov     rcx, [rdi+20h]; hWnd
0x18000dcb4  xor     r9d, r9d; lParam
0x18000dcb7  mov     r8, rax; wParam
0x18000dcba  mov     edx, ebx; Msg
0x18000dcbc  call    cs:__imp_SendMessageA
0x18000dcc2  mov     rcx, [rdi+2C8h]; this
0x18000dcc9  call    ?GetAccessableContentFont@CHHWinType@@QEAAPEAUHFONT__@@XZ; CHHWinType::GetAccessableContentFont(void)
0x18000dcce  mov     rcx, [rdi+80h]; hWnd
0x18000dcd5  xor     r9d, r9d; lParam
0x18000dcd8  mov     r8, rax; wParam
0x18000dcdb  mov     edx, ebx; Msg
0x18000dcdd  call    cs:__imp_SendMessageA
0x18000dce3  mov     rcx, [rdi+2C8h]; this
0x18000dcea  call    ?GetAccessableContentFont@CHHWinType@@QEAAPEAUHFONT__@@XZ; CHHWinType::GetAccessableContentFont(void)
0x18000dcef  mov     rcx, [rdi+0E0h]; hWnd
0x18000dcf6  xor     r9d, r9d; lParam
0x18000dcf9  mov     r8, rax; wParam
0x18000dcfc  mov     edx, ebx; Msg
0x18000dcfe  call    cs:__imp_SendMessageA
0x18000dd04  mov     rcx, [rdi+2C8h]; this
0x18000dd0b  call    ?GetAccessableContentFont@CHHWinType@@QEAAPEAUHFONT__@@XZ; CHHWinType::GetAccessableContentFont(void)
0x18000dd10  mov     rcx, [rdi+200h]; hWnd
0x18000dd17  xor     r9d, r9d; lParam
0x18000dd1a  mov     r8, rax; wParam
0x18000dd1d  mov     edx, ebx; Msg
0x18000dd1f  call    cs:__imp_SendMessageA
0x18000dd25  mov     rcx, [rdi+2C8h]; this
0x18000dd2c  call    ?GetAccessableContentFont@CHHWinType@@QEAAPEAUHFONT__@@XZ; CHHWinType::GetAccessableContentFont(void)
0x18000dd31  mov     rcx, [rdi+260h]; hWnd
0x18000dd38  xor     r9d, r9d; lParam
0x18000dd3b  mov     r8, rax; wParam
0x18000dd3e  mov     edx, ebx; Msg
0x18000dd40  call    cs:__imp_SendMessageA
0x18000dd46  mov     rcx, [rdi+2C8h]; this
0x18000dd4d  call    ?GetAccessableContentFont@CHHWinType@@QEAAPEAUHFONT__@@XZ; CHHWinType::GetAccessableContentFont(void)
0x18000dd52  mov     rcx, [rdi+140h]; hWnd
0x18000dd59  xor     r9d, r9d; lParam
0x18000dd5c  mov     r8, rax; wParam
0x18000dd5f  mov     edx, ebx; Msg
0x18000dd61  call    cs:__imp_SendMessageA
0x18000dd67  mov     rcx, rdi; this
0x18000dd6a  call    ?LoadBookmarks@CBookmarksNavPane@@AEAAXXZ; CBookmarksNavPane::LoadBookmarks(void)
0x18000dd6f  mov     rax, [rdi]
0x18000dd72  mov     rcx, rdi
0x18000dd75  mov     rax, [rax+40h]
0x18000dd79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd7e  mov     eax, 1
0x18000dd83  add     rsp, 70h
0x18000dd87  pop     r14
0x18000dd89  pop     rdi
0x18000dd8a  pop     rsi
0x18000dd8b  pop     rbx
0x18000dd8c  pop     rbp
0x18000dd8d  retn
```
