# CAdvancedSearchNavPane::Create(HWND__ *)

- ea: `0x1800047d0`
- end: `0x180004d58`
- name: `?Create@CAdvancedSearchNavPane@@UEAAHPEAUHWND__@@@Z`
- size: `1416`
- prototype: `__int64 __fastcall(CAdvancedSearchNavPane *__hidden this, HWND hWndParent)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001728`
- `0x1800047d0`
- `0x1800053b4`
- `0x180005a4c`
- `0x180005ff4`
- `0x18000686c`
- `0x18000ad54`
- `0x18000ae1c`
- `0x1800107d8`
- `0x180010b14`
- `0x180010fcc`
- `0x180042e6c`
- `0x180051cfc`
- `0x180051e48`

## import_xrefs

- `USER32!EnumChildWindows` at `0x180004d31`
- `USER32!EnumChildWindows` at `0x180004d31`
- `USER32!GetWindowLongA` at `0x180004aed`
- `USER32!GetWindowLongA` at `0x180004b0e`
- `USER32!GetWindowLongA` at `0x180004b36`
- `USER32!GetWindowLongA` at `0x180004b4b`
- `USER32!GetWindowLongA` at `0x180004b76`
- `USER32!GetWindowLongA` at `0x180004aed`
- `USER32!GetWindowLongA` at `0x180004b0e`
- `USER32!GetWindowLongA` at `0x180004b36`
- `USER32!GetWindowLongA` at `0x180004b4b`
- `USER32!GetWindowLongA` at `0x180004b76`
- `USER32!SetWindowLongA` at `0x180004aff`
- `USER32!SetWindowLongA` at `0x180004b23`
- `USER32!SetWindowLongA` at `0x180004b62`
- `USER32!SetWindowLongA` at `0x180004b8b`
- `USER32!SetWindowLongA` at `0x180004aff`
- `USER32!SetWindowLongA` at `0x180004b23`
- `USER32!SetWindowLongA` at `0x180004b62`
- `USER32!SetWindowLongA` at `0x180004b8b`
- `USER32!SetWindowLongPtrA` at `0x180004a10`
- `USER32!SetWindowLongPtrA` at `0x180004a5b`
- `USER32!SetWindowLongPtrA` at `0x180004aab`
- `USER32!SetWindowLongPtrA` at `0x180004bcc`
- `USER32!SetWindowLongPtrA` at `0x180004bf1`
- `USER32!SetWindowLongPtrA` at `0x180004c16`
- `USER32!SetWindowLongPtrA` at `0x180004c70`
- `USER32!SetWindowLongPtrA` at `0x180004c95`
- `USER32!SetWindowLongPtrA` at `0x180004cba`
- `USER32!SetWindowLongPtrA` at `0x180004a10`
- `USER32!SetWindowLongPtrA` at `0x180004a5b`
- `USER32!SetWindowLongPtrA` at `0x180004aab`
- `USER32!SetWindowLongPtrA` at `0x180004bcc`
- `USER32!SetWindowLongPtrA` at `0x180004bf1`
- `USER32!SetWindowLongPtrA` at `0x180004c16`
- `USER32!SetWindowLongPtrA` at `0x180004c70`
- `USER32!SetWindowLongPtrA` at `0x180004c95`
- `USER32!SetWindowLongPtrA` at `0x180004cba`
- `USER32!SetWindowPos` at `0x18000496a`
- `USER32!SetWindowPos` at `0x18000496a`
- `USER32!GetSystemMetrics` at `0x18000492e`
- `USER32!GetSystemMetrics` at `0x18000493b`
- `USER32!GetSystemMetrics` at `0x18000492e`
- `USER32!GetSystemMetrics` at `0x18000493b`
- `USER32!LoadBitmapA` at `0x1800048e9`
- `USER32!LoadBitmapA` at `0x1800048e9`
- `USER32!SendMessageA` at `0x180004905`
- `USER32!SendMessageA` at `0x180004998`
- `USER32!SendMessageA` at `0x180004a26`
- `USER32!SendMessageA` at `0x180004ad1`
- `USER32!SendMessageA` at `0x180004c2f`
- `USER32!SendMessageA` at `0x180004ce7`
- `USER32!SendMessageA` at `0x180004d16`
- `USER32!SendMessageA` at `0x180004905`
- `USER32!SendMessageA` at `0x180004998`
- `USER32!SendMessageA` at `0x180004a26`
- `USER32!SendMessageA` at `0x180004ad1`
- `USER32!SendMessageA` at `0x180004c2f`
- `USER32!SendMessageA` at `0x180004ce7`
- `USER32!SendMessageA` at `0x180004d16`
- `USER32!GetDlgItem` at `0x180004a6a`
- `USER32!GetDlgItem` at `0x180004a6a`
- `GDI32!GetObjectA` at `0x180004923`
- `GDI32!GetObjectA` at `0x180004923`
- `ADVAPI32!RegCloseKey` at `0x180004874`
- `ADVAPI32!RegCloseKey` at `0x180004874`
- `ADVAPI32!RegQueryValueExA` at `0x18000485c`
- `ADVAPI32!RegQueryValueExA` at `0x18000485c`
- `ADVAPI32!RegOpenKeyExA` at `0x18000482f`
- `ADVAPI32!RegOpenKeyExA` at `0x18000482f`

## string_xrefs

- `0x180004821`: `Software\Microsoft\Accessibility`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAdvancedSearchNavPane::Create(CAdvancedSearchNavPane *this, HWND hWndParent)
{
  __int64 v4; // rbx
  HINSTANCE ResourceInstance; // rax
  __int64 DialogParamW; // rax
  int v7; // esi
  HINSTANCE v8; // rax
  HBITMAP BitmapA; // rax
  int SystemMetrics; // ebx
  int v11; // eax
  CFTSListView *v12; // rax
  HWND DlgItem; // rax
  HFONT ContentFont; // rax
  HWND v15; // rcx
  LONG WindowLongA; // eax
  LONG v17; // eax
  int v18; // ebx
  LONG v19; // eax
  LONG v20; // eax
  CResourceCache *v21; // rcx
  __int64 i; // rbx
  HFONT AccessableUIFont; // rax
  HFONT AccessableContentFont; // rax
  _OWORD pv[2]; // [rsp+48h] [rbp-28h] BYREF
  unsigned int Data; // [rsp+A0h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+48h] BYREF

  if ( !*((_QWORD *)this + 1) )
  {
    hKey = 0;
    Data = 100;
    cbData = 4;
    v4 = 2005;
    if ( !RegOpenKeyExA(HKEY_CURRENT_USER, "Software\\Microsoft\\Accessibility", 0, 0x20019u, &hKey) )
    {
      if ( !RegQueryValueExA(hKey, "TextScaleFactor", 0, 0, (LPBYTE)&Data, &cbData) && Data > 0x64 )
        v4 = 2009;
      RegCloseKey(hKey);
    }
    ResourceInstance = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    DialogParamW = IsolationAwareCreateDialogParamW(
                     ResourceInstance,
                     (LPCWSTR)v4,
                     hWndParent,
                     (DLGPROC)CAdvancedSearchNavPane::s_DialogProc,
                     (LPARAM)this);
    *((_QWORD *)this + 1) = DialogParamW;
    v7 = 1;
    if ( !DialogParamW )
    {
      v8 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
      *((_QWORD *)this + 1) = IsolationAwareCreateDialogParamA(
                                v8,
                                (LPCSTR)v4,
                                hWndParent,
                                (DLGPROC)CAdvancedSearchNavPane::s_DialogProc,
                                (LPARAM)this);
      v7 = 0;
    }
    CAdvancedSearchNavPane::InitDlgItemArray(this);
    BitmapA = LoadBitmapA(0, (LPCSTR)0x7FE3);
    *((_QWORD *)this + 4) = BitmapA;
    SendMessageA(*((HWND *)this + 17), 0xF7u, 0, (LPARAM)BitmapA);
    memset(pv, 0, sizeof(pv));
    GetObjectA(*((HANDLE *)this + 4), 32, pv);
    SystemMetrics = GetSystemMetrics(45);
    v11 = GetSystemMetrics(46);
    SetWindowPos(*((HWND *)this + 17), 0, 0, 0, SystemMetrics + DWORD1(pv[0]), v11 + DWORD2(pv[0]), 0x106u);
    W_EnableUnicode(*((_QWORD *)this + 65), 0);
    SendMessageA(*((HWND *)this + 65), 0x1036u, 0, g_RTL_Style | 0x20LL);
    v12 = (CFTSListView *)operator new(0x40u);
    if ( v12 )
      v12 = CFTSListView::CFTSListView(v12, *((struct CExCollection **)this + 137), *((HWND *)this + 65), 1);
    *((_QWORD *)this + 138) = v12;
    CAdvancedSearchNavPane::s_lpfnlListViewWndProc = W_GetWndProc(*((HWND *)this + 65), v7);
    W_SubClassWindow(*((HWND *)this + 65), (__int64)CAdvancedSearchNavPane::s_ListViewProc, v7);
    SetWindowLongPtrA(*((HWND *)this + 65), -21, (LONG_PTR)this);
    SendMessageA(*((HWND *)this + 5), 0x141u, 0xF9u, 0);
    CAdvancedSearchNavPane::s_lpfnlKeywordComboProc = W_GetWndProc(*((HWND *)this + 5), v7);
    W_SubClassWindow(*((HWND *)this + 5), (__int64)CAdvancedSearchNavPane::s_KeywordComboProc, v7);
    SetWindowLongPtrA(*((HWND *)this + 5), -21, (LONG_PTR)this);
    DlgItem = GetDlgItem(*((HWND *)this + 5), 1001);
    *((_QWORD *)this + 139) = DlgItem;
    CAdvancedSearchNavPane::s_lpfnlKeywordComboEditProc = W_GetWndProc(DlgItem, v7);
    W_SubClassWindow(*((HWND *)this + 139), (__int64)CAdvancedSearchNavPane::s_KeywordComboEditProc, v7);
    SetWindowLongPtrA(*((HWND *)this + 139), -21, (LONG_PTR)this);
    ContentFont = CHHWinType::GetContentFont(*((CHHWinType **)this + 141));
    SendMessageA(*((HWND *)this + 139), 0x30u, (WPARAM)ContentFont, 0);
    v15 = (HWND)*((_QWORD *)this + 139);
    if ( g_fBiDi )
    {
      WindowLongA = GetWindowLongA(v15, -16);
      SetWindowLongA(*((HWND *)this + 139), -16, WindowLongA);
      v17 = GetWindowLongA(*((HWND *)this + 139), -16);
      SetWindowLongA(*((HWND *)this + 139), -16, v17 | 2);
      v18 = -20;
      v19 = g_RTL_Style | GetWindowLongA(*((HWND *)this + 139), -20);
    }
    else
    {
      v20 = GetWindowLongA(v15, -20);
      SetWindowLongA(*((HWND *)this + 139), -20, v20 & 0xFFFFCFFF);
      v18 = -16;
      v19 = GetWindowLongA(*((HWND *)this + 139), -16) & 0xFFFFFFFD;
    }
    SetWindowLongA(*((HWND *)this + 139), v18, v19);
    CAdvancedSearchNavPane::s_lpfnlGenericBtnProc = W_GetWndProc(*((HWND *)this + 29), v7);
    W_SubClassWindow(*((HWND *)this + 29), (__int64)CAdvancedSearchNavPane::s_GenericBtnProc, v7);
    SetWindowLongPtrA(*((HWND *)this + 29), -21, (LONG_PTR)this);
    W_SubClassWindow(*((HWND *)this + 17), (__int64)CAdvancedSearchNavPane::s_GenericBtnProc, v7);
    SetWindowLongPtrA(*((HWND *)this + 17), -21, (LONG_PTR)this);
    W_SubClassWindow(*((HWND *)this + 41), (__int64)CAdvancedSearchNavPane::s_GenericBtnProc, v7);
    SetWindowLongPtrA(*((HWND *)this + 41), -21, (LONG_PTR)this);
    SendMessageA(*((HWND *)this + 89), 0xF1u, 1u, 0);
    CAdvancedSearchNavPane::s_lpfnlGenericKeyboardProc = W_GetWndProc(*((HWND *)this + 89), v7);
    W_SubClassWindow(*((HWND *)this + 89), (__int64)CAdvancedSearchNavPane::s_GenericKeyboardProc, v7);
    SetWindowLongPtrA(*((HWND *)this + 89), -21, (LONG_PTR)this);
    W_SubClassWindow(*((HWND *)this + 101), (__int64)CAdvancedSearchNavPane::s_GenericKeyboardProc, v7);
    SetWindowLongPtrA(*((HWND *)this + 101), -21, (LONG_PTR)this);
    W_SubClassWindow(*((HWND *)this + 77), (__int64)CAdvancedSearchNavPane::s_GenericKeyboardProc, v7);
    SetWindowLongPtrA(*((HWND *)this + 77), -21, (LONG_PTR)this);
    for ( i = 0; i != 11; ++i )
    {
      if ( *((_DWORD *)this + 24 * i + 12) != 1001 )
      {
        AccessableUIFont = CResourceCache::GetAccessableUIFont(v21);
        SendMessageA(*((HWND *)this + 12 * i + 5), 0x30u, (WPARAM)AccessableUIFont, 0);
      }
    }
    AccessableContentFont = CHHWinType::GetAccessableContentFont(*((CHHWinType **)this + 141));
    SendMessageA(*(HWND *)(*((_QWORD *)this + 138) + 16LL), 0x30u, (WPARAM)AccessableContentFont, 0);
    EnumChildWindows(*(HWND *)(*((_QWORD *)this + 138) + 16LL), EnumListViewFont, 0);
    CAdvancedSearchNavPane::LoadKeywordCombo(this);
  }
  return 1;
}

```

## disassembly

```asm
0x1800047d0  mov     [rsp-28h+arg_8], rbx
0x1800047d5  push    rbp
0x1800047d6  push    rsi
0x1800047d7  push    rdi
0x1800047d8  push    r13
0x1800047da  push    r14
0x1800047dc  mov     rbp, rsp
0x1800047df  sub     rsp, 70h
0x1800047e3  mov     r14, rdx
0x1800047e6  mov     rdi, rcx
0x1800047e9  cmp     qword ptr [rcx+8], 0
0x1800047ee  jnz     loc_180004D3F
0x1800047f4  mov     [rbp+hKey], 0
0x1800047fc  mov     [rbp+Data], 64h ; 'd'
0x180004803  mov     [rbp+cbData], 4
0x18000480a  mov     ebx, 7D5h
0x18000480f  lea     rax, [rbp+hKey]
0x180004813  mov     [rsp+70h+phkResult], rax; phkResult
0x180004818  mov     r9d, 20019h; samDesired
0x18000481e  xor     r8d, r8d; ulOptions
0x180004821  lea     rdx, SubKey; "Software\\Microsoft\\Accessibility"
0x180004828  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000482f  call    cs:__imp_RegOpenKeyExA
0x180004835  test    eax, eax
0x180004837  jnz     short loc_18000487A
0x180004839  lea     rax, [rbp+cbData]
0x18000483d  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180004842  lea     rax, [rbp+Data]
0x180004846  mov     [rsp+70h+phkResult], rax; lpData
0x18000484b  xor     r9d, r9d; lpType
0x18000484e  xor     r8d, r8d; lpReserved
0x180004851  lea     rdx, ValueName; "TextScaleFactor"
0x180004858  mov     rcx, [rbp+hKey]; hKey
0x18000485c  call    cs:__imp_RegQueryValueExA
0x180004862  test    eax, eax
0x180004864  jnz     short loc_180004870
0x180004866  lea     eax, [rbx+4]
0x180004869  cmp     [rbp+Data], 64h ; 'd'
0x18000486d  cmova   ebx, eax
0x180004870  mov     rcx, [rbp+hKey]; hKey
0x180004874  call    cs:__imp_RegCloseKey
0x18000487a  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x180004881  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x180004886  mov     rcx, rax; hInstance
0x180004889  mov     [rsp+70h+phkResult], rdi; LPARAM
0x18000488e  lea     r9, ?s_DialogProc@CAdvancedSearchNavPane@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180004895  mov     r8, r14; hWndParent
0x180004898  mov     rdx, rbx; lpTemplateName
0x18000489b  call    IsolationAwareCreateDialogParamW
0x1800048a0  mov     [rdi+8], rax
0x1800048a4  mov     esi, 1
0x1800048a9  test    rax, rax
0x1800048ac  jnz     short loc_1800048DA
0x1800048ae  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x1800048b5  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x1800048ba  mov     rcx, rax; hInstance
0x1800048bd  mov     [rsp+70h+phkResult], rdi; LPARAM
0x1800048c2  lea     r9, ?s_DialogProc@CAdvancedSearchNavPane@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1800048c9  mov     r8, r14; hWndParent
0x1800048cc  mov     rdx, rbx; lpTemplateName
0x1800048cf  call    IsolationAwareCreateDialogParamA
0x1800048d4  mov     [rdi+8], rax
0x1800048d8  xor     esi, esi
0x1800048da  mov     rcx, rdi; this
0x1800048dd  call    ?InitDlgItemArray@CAdvancedSearchNavPane@@AEAAXXZ; CAdvancedSearchNavPane::InitDlgItemArray(void)
0x1800048e2  mov     edx, 7FE3h; lpBitmapName
0x1800048e7  xor     ecx, ecx; hInstance
0x1800048e9  call    cs:__imp_LoadBitmapA
0x1800048ef  mov     [rdi+20h], rax
0x1800048f3  mov     r9, rax; lParam
0x1800048f6  xor     r8d, r8d; wParam
0x1800048f9  mov     edx, 0F7h; Msg
0x1800048fe  mov     rcx, [rdi+88h]; hWnd
0x180004905  call    cs:__imp_SendMessageA
0x18000490b  xorps   xmm0, xmm0
0x18000490e  movups  [rbp+pv], xmm0
0x180004912  movups  [rbp+var_18], xmm0
0x180004916  lea     r8, [rbp+pv]; pv
0x18000491a  mov     edx, 20h ; ' '; c
0x18000491f  mov     rcx, [rdi+20h]; h
0x180004923  call    cs:__imp_GetObjectA
0x180004929  mov     ecx, 2Dh ; '-'; nIndex
0x18000492e  call    cs:__imp_GetSystemMetrics
0x180004934  mov     ebx, eax
0x180004936  mov     ecx, 2Eh ; '.'; nIndex
0x18000493b  call    cs:__imp_GetSystemMetrics
0x180004941  mov     edx, dword ptr [rbp+pv+8]
0x180004944  add     edx, eax
0x180004946  mov     eax, dword ptr [rbp+pv+4]
0x180004949  add     eax, ebx
0x18000494b  mov     [rsp+70h+uFlags], 106h; uFlags
0x180004953  mov     dword ptr [rsp+70h+lpcbData], edx; cy
0x180004957  mov     dword ptr [rsp+70h+phkResult], eax; cx
0x18000495b  xor     r9d, r9d; Y
0x18000495e  xor     r8d, r8d; X
0x180004961  xor     edx, edx; hWndInsertAfter
0x180004963  mov     rcx, [rdi+88h]; hWnd
0x18000496a  call    cs:__imp_SetWindowPos
0x180004970  xor     edx, edx
0x180004972  mov     rcx, [rdi+208h]
0x180004979  call    ?W_EnableUnicode@@YAHPEAUHWND__@@W4CCTLWINTYPE@@@Z; W_EnableUnicode(HWND__ *,CCTLWINTYPE)
0x18000497e  mov     r9d, cs:?g_RTL_Style@@3KA; ulong g_RTL_Style
0x180004985  or      r9, 20h; lParam
0x180004989  xor     r8d, r8d; wParam
0x18000498c  mov     edx, 1036h; Msg
0x180004991  mov     rcx, [rdi+208h]; hWnd
0x180004998  call    cs:__imp_SendMessageA
0x18000499e  mov     ecx, 40h ; '@'; Size
0x1800049a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800049a8  mov     [rbp+var_30], rax
0x1800049ac  test    rax, rax
0x1800049af  jz      short loc_1800049CB
0x1800049b1  mov     r9b, 1; bool
0x1800049b4  mov     r8, [rdi+208h]; HWND
0x1800049bb  mov     rdx, [rdi+448h]; struct CExCollection *
0x1800049c2  mov     rcx, rax; this
0x1800049c5  call    ??0CFTSListView@@QEAA@PEAVCExCollection@@PEAUHWND__@@_N@Z; CFTSListView::CFTSListView(CExCollection *,HWND__ *,bool)
0x1800049ca  nop
0x1800049cb  mov     [rdi+450h], rax
0x1800049d2  mov     edx, esi; int
0x1800049d4  mov     rcx, [rdi+208h]; HWND
0x1800049db  call    ?W_GetWndProc@@YAP6A_JPEAUHWND__@@I_K_J@Z0H@Z; W_GetWndProc(HWND__ *,int)
0x1800049e0  mov     cs:?s_lpfnlListViewWndProc@CAdvancedSearchNavPane@@1P6A_JPEAUHWND__@@I_K_J@ZEA, rax; __int64 (*CAdvancedSearchNavPane::s_lpfnlListViewWndProc)(HWND__ *,uint,unsigned __int64,__int64)
0x1800049e7  mov     r8d, esi; int
0x1800049ea  lea     rdx, ?s_ListViewProc@CAdvancedSearchNavPane@@CA_JPEAUHWND__@@I_K_J@Z; __int64
0x1800049f1  mov     rcx, [rdi+208h]; HWND
0x1800049f8  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x1800049fd  mov     r8, rdi; dwNewLong
0x180004a00  mov     r13d, 0FFFFFFEBh
0x180004a06  mov     edx, r13d; nIndex
0x180004a09  mov     rcx, [rdi+208h]; hWnd
0x180004a10  call    cs:__imp_SetWindowLongPtrA
0x180004a16  xor     r9d, r9d; lParam
0x180004a19  mov     edx, 141h; Msg
0x180004a1e  lea     r8d, [rdx-48h]; wParam
0x180004a22  mov     rcx, [rdi+28h]; hWnd
0x180004a26  call    cs:__imp_SendMessageA
0x180004a2c  mov     edx, esi; int
0x180004a2e  mov     rcx, [rdi+28h]; HWND
0x180004a32  call    ?W_GetWndProc@@YAP6A_JPEAUHWND__@@I_K_J@Z0H@Z; W_GetWndProc(HWND__ *,int)
0x180004a37  mov     cs:?s_lpfnlKeywordComboProc@CAdvancedSearchNavPane@@1P6A_JPEAUHWND__@@I_K_J@ZEA, rax; __int64 (*CAdvancedSearchNavPane::s_lpfnlKeywordComboProc)(HWND__ *,uint,unsigned __int64,__int64)
0x180004a3e  mov     r8d, esi; int
0x180004a41  lea     rdx, ?s_KeywordComboProc@CAdvancedSearchNavPane@@CA_JPEAUHWND__@@I_K_J@Z; __int64
0x180004a48  mov     rcx, [rdi+28h]; HWND
0x180004a4c  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x180004a51  mov     r8, rdi; dwNewLong
0x180004a54  mov     edx, r13d; nIndex
0x180004a57  mov     rcx, [rdi+28h]; hWnd
0x180004a5b  call    cs:__imp_SetWindowLongPtrA
0x180004a61  mov     edx, 3E9h; nIDDlgItem
0x180004a66  mov     rcx, [rdi+28h]; hDlg
0x180004a6a  call    cs:__imp_GetDlgItem
0x180004a70  mov     [rdi+458h], rax
0x180004a77  mov     edx, esi; int
0x180004a79  mov     rcx, rax; HWND
0x180004a7c  call    ?W_GetWndProc@@YAP6A_JPEAUHWND__@@I_K_J@Z0H@Z; W_GetWndProc(HWND__ *,int)
0x180004a81  mov     cs:?s_lpfnlKeywordComboEditProc@CAdvancedSearchNavPane@@1P6A_JPEAUHWND__@@I_K_J@ZEA, rax; __int64 (*CAdvancedSearchNavPane::s_lpfnlKeywordComboEditProc)(HWND__ *,uint,unsigned __int64,__int64)
0x180004a88  mov     r8d, esi; int
0x180004a8b  lea     rdx, ?s_KeywordComboEditProc@CAdvancedSearchNavPane@@CA_JPEAUHWND__@@I_K_J@Z; __int64
0x180004a92  mov     rcx, [rdi+458h]; HWND
0x180004a99  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x180004a9e  mov     r8, rdi; dwNewLong
0x180004aa1  mov     edx, r13d; nIndex
0x180004aa4  mov     rcx, [rdi+458h]; hWnd
0x180004aab  call    cs:__imp_SetWindowLongPtrA
0x180004ab1  mov     rcx, [rdi+468h]; this
0x180004ab8  call    ?GetContentFont@CHHWinType@@QEAAPEAUHFONT__@@XZ; CHHWinType::GetContentFont(void)
0x180004abd  xor     r9d, r9d; lParam
0x180004ac0  mov     r8, rax; wParam
0x180004ac3  lea     r14d, [r13+45h]
0x180004ac7  mov     edx, r14d; Msg
0x180004aca  mov     rcx, [rdi+458h]; hWnd
0x180004ad1  call    cs:__imp_SendMessageA
0x180004ad7  mov     rcx, [rdi+458h]; hWnd
0x180004ade  cmp     cs:?g_fBiDi@@3HA, 0; int g_fBiDi
0x180004ae5  jz      short loc_180004B44
0x180004ae7  lea     ebx, [r13+5]
0x180004aeb  mov     edx, ebx; nIndex
0x180004aed  call    cs:__imp_GetWindowLongA
0x180004af3  mov     r8d, eax; dwNewLong
0x180004af6  mov     edx, ebx; nIndex
0x180004af8  mov     rcx, [rdi+458h]; hWnd
0x180004aff  call    cs:__imp_SetWindowLongA
0x180004b05  mov     edx, ebx; nIndex
0x180004b07  mov     rcx, [rdi+458h]; hWnd
0x180004b0e  call    cs:__imp_GetWindowLongA
0x180004b14  or      eax, 2
0x180004b17  mov     r8d, eax; dwNewLong
0x180004b1a  mov     edx, ebx; nIndex
0x180004b1c  mov     rcx, [rdi+458h]; hWnd
0x180004b23  call    cs:__imp_SetWindowLongA
0x180004b29  lea     ebx, [r13+1]
0x180004b2d  mov     edx, ebx; nIndex
0x180004b2f  mov     rcx, [rdi+458h]; hWnd
0x180004b36  call    cs:__imp_GetWindowLongA
0x180004b3c  or      eax, cs:?g_RTL_Style@@3KA; ulong g_RTL_Style
0x180004b42  jmp     short loc_180004B7F
0x180004b44  mov     ebx, 0FFFFFFECh
0x180004b49  mov     edx, ebx; nIndex
0x180004b4b  call    cs:__imp_GetWindowLongA
0x180004b51  and     eax, 0FFFFCFFFh
0x180004b56  mov     r8d, eax; dwNewLong
0x180004b59  mov     edx, ebx; nIndex
0x180004b5b  mov     rcx, [rdi+458h]; hWnd
0x180004b62  call    cs:__imp_SetWindowLongA
0x180004b68  mov     ebx, 0FFFFFFF0h
0x180004b6d  mov     edx, ebx; nIndex
0x180004b6f  mov     rcx, [rdi+458h]; hWnd
0x180004b76  call    cs:__imp_GetWindowLongA
0x180004b7c  and     eax, 0FFFFFFFDh
0x180004b7f  mov     r8d, eax; dwNewLong
0x180004b82  mov     edx, ebx; nIndex
0x180004b84  mov     rcx, [rdi+458h]; hWnd
0x180004b8b  call    cs:__imp_SetWindowLongA
0x180004b91  mov     edx, esi; int
0x180004b93  mov     rcx, [rdi+0E8h]; HWND
0x180004b9a  call    ?W_GetWndProc@@YAP6A_JPEAUHWND__@@I_K_J@Z0H@Z; W_GetWndProc(HWND__ *,int)
0x180004b9f  mov     cs:?s_lpfnlGenericBtnProc@CAdvancedSearchNavPane@@1P6A_JPEAUHWND__@@I_K_J@ZEA, rax; __int64 (*CAdvancedSearchNavPane::s_lpfnlGenericBtnProc)(HWND__ *,uint,unsigned __int64,__int64)
0x180004ba6  mov     r8d, esi; int
0x180004ba9  lea     rbx, ?s_GenericBtnProc@CAdvancedSearchNavPane@@CA_JPEAUHWND__@@I_K_J@Z; CAdvancedSearchNavPane::s_GenericBtnProc(HWND__ *,uint,unsigned __int64,__int64)
0x180004bb0  mov     rdx, rbx; __int64
0x180004bb3  mov     rcx, [rdi+0E8h]; HWND
0x180004bba  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x180004bbf  mov     r8, rdi; dwNewLong
0x180004bc2  mov     edx, r13d; nIndex
0x180004bc5  mov     rcx, [rdi+0E8h]; hWnd
0x180004bcc  call    cs:__imp_SetWindowLongPtrA
0x180004bd2  mov     r8d, esi; int
0x180004bd5  mov     rdx, rbx; __int64
0x180004bd8  mov     rcx, [rdi+88h]; HWND
0x180004bdf  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x180004be4  mov     r8, rdi; dwNewLong
0x180004be7  mov     edx, r13d; nIndex
0x180004bea  mov     rcx, [rdi+88h]; hWnd
0x180004bf1  call    cs:__imp_SetWindowLongPtrA
0x180004bf7  mov     r8d, esi; int
0x180004bfa  mov     rdx, rbx; __int64
0x180004bfd  mov     rcx, [rdi+148h]; HWND
0x180004c04  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x180004c09  mov     r8, rdi; dwNewLong
0x180004c0c  mov     edx, r13d; nIndex
0x180004c0f  mov     rcx, [rdi+148h]; hWnd
0x180004c16  call    cs:__imp_SetWindowLongPtrA
0x180004c1c  xor     r9d, r9d; lParam
0x180004c1f  mov     edx, 0F1h; Msg
0x180004c24  lea     r8d, [r9+1]; wParam
0x180004c28  mov     rcx, [rdi+2C8h]; hWnd
0x180004c2f  call    cs:__imp_SendMessageA
0x180004c35  mov     edx, esi; int
0x180004c37  mov     rcx, [rdi+2C8h]; HWND
0x180004c3e  call    ?W_GetWndProc@@YAP6A_JPEAUHWND__@@I_K_J@Z0H@Z; W_GetWndProc(HWND__ *,int)
0x180004c43  mov     cs:?s_lpfnlGenericKeyboardProc@CAdvancedSearchNavPane@@1P6A_JPEAUHWND__@@I_K_J@ZEA, rax; __int64 (*CAdvancedSearchNavPane::s_lpfnlGenericKeyboardProc)(HWND__ *,uint,unsigned __int64,__int64)
0x180004c4a  mov     r8d, esi; int
0x180004c4d  lea     rbx, ?s_GenericKeyboardProc@CAdvancedSearchNavPane@@CA_JPEAUHWND__@@I_K_J@Z; CAdvancedSearchNavPane::s_GenericKeyboardProc(HWND__ *,uint,unsigned __int64,__int64)
0x180004c54  mov     rdx, rbx; __int64
0x180004c57  mov     rcx, [rdi+2C8h]; HWND
0x180004c5e  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x180004c63  mov     r8, rdi; dwNewLong
0x180004c66  mov     edx, r13d; nIndex
0x180004c69  mov     rcx, [rdi+2C8h]; hWnd
0x180004c70  call    cs:__imp_SetWindowLongPtrA
0x180004c76  mov     r8d, esi; int
0x180004c79  mov     rdx, rbx; __int64
0x180004c7c  mov     rcx, [rdi+328h]; HWND
0x180004c83  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x180004c88  mov     r8, rdi; dwNewLong
0x180004c8b  mov     edx, r13d; nIndex
0x180004c8e  mov     rcx, [rdi+328h]; hWnd
0x180004c95  call    cs:__imp_SetWindowLongPtrA
0x180004c9b  mov     r8d, esi; int
0x180004c9e  mov     rdx, rbx; __int64
0x180004ca1  mov     rcx, [rdi+268h]; HWND
0x180004ca8  call    ?W_SubClassWindow@@YAXPEAUHWND__@@_JH@Z; W_SubClassWindow(HWND__ *,__int64,int)
0x180004cad  mov     r8, rdi; dwNewLong
0x180004cb0  mov     edx, r13d; nIndex
0x180004cb3  mov     rcx, [rdi+268h]; hWnd
0x180004cba  call    cs:__imp_SetWindowLongPtrA
0x180004cc0  xor     ebx, ebx
0x180004cc2  lea     rsi, [rbx+rbx*2]
0x180004cc6  shl     rsi, 5
0x180004cca  cmp     dword ptr [rsi+rdi+30h], 3E9h
0x180004cd2  jz      short loc_180004CED
0x180004cd4  call    ?GetAccessableUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetAccessableUIFont(void)
0x180004cd9  xor     r9d, r9d; lParam
0x180004cdc  mov     r8, rax; wParam
0x180004cdf  mov     edx, r14d; Msg
0x180004ce2  mov     rcx, [rsi+rdi+28h]; hWnd
0x180004ce7  call    cs:__imp_SendMessageA
0x180004ced  inc     rbx
0x180004cf0  cmp     rbx, 0Bh
0x180004cf4  jnz     short loc_180004CC2
0x180004cf6  mov     rcx, [rdi+468h]; this
0x180004cfd  call    ?GetAccessableContentFont@CHHWinType@@QEAAPEAUHFONT__@@XZ; CHHWinType::GetAccessableContentFont(void)
0x180004d02  mov     rcx, [rdi+450h]
0x180004d09  xor     r9d, r9d; lParam
0x180004d0c  mov     r8, rax; wParam
0x180004d0f  mov     edx, r14d; Msg
0x180004d12  mov     rcx, [rcx+10h]; hWnd
0x180004d16  call    cs:__imp_SendMessageA
0x180004d1c  mov     rcx, [rdi+450h]
  ... truncated ...
```
