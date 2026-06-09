# CMFCBaseVisualManager::UpdateSystemColors(void)

- ea: `0x180196e50`
- end: `0x1801972fb`
- name: `?UpdateSystemColors@CMFCBaseVisualManager@@IEAAXXZ`
- size: `1195`
- prototype: `void __fastcall(CMFCBaseVisualManager *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180196d70`
- `0x180199f60`
- `0x1801c0d20`

## callees

- `0x180139950`
- `0x180196e50`
- `0x1802c7020`

## import_xrefs

- `UxTheme!OpenThemeData` at `0x180196e92`
- `UxTheme!OpenThemeData` at `0x180196ecf`
- `UxTheme!OpenThemeData` at `0x180196f0c`
- `UxTheme!OpenThemeData` at `0x180196f49`
- `UxTheme!OpenThemeData` at `0x180196f86`
- `UxTheme!OpenThemeData` at `0x180196fc3`
- `UxTheme!OpenThemeData` at `0x180197000`
- `UxTheme!OpenThemeData` at `0x18019703d`
- `UxTheme!OpenThemeData` at `0x18019707a`
- `UxTheme!OpenThemeData` at `0x1801970b7`
- `UxTheme!OpenThemeData` at `0x1801970f4`
- `UxTheme!OpenThemeData` at `0x180197131`
- `UxTheme!OpenThemeData` at `0x18019716e`
- `UxTheme!OpenThemeData` at `0x1801971ab`
- `UxTheme!OpenThemeData` at `0x1801971e8`
- `UxTheme!OpenThemeData` at `0x180197225`
- `UxTheme!OpenThemeData` at `0x180197265`
- `UxTheme!OpenThemeData` at `0x1801972a5`
- `UxTheme!OpenThemeData` at `0x1801972e3`
- `UxTheme!OpenThemeData` at `0x180196e92`
- `UxTheme!OpenThemeData` at `0x180196ecf`
- `UxTheme!OpenThemeData` at `0x180196f0c`
- `UxTheme!OpenThemeData` at `0x180196f49`
- `UxTheme!OpenThemeData` at `0x180196f86`
- `UxTheme!OpenThemeData` at `0x180196fc3`
- `UxTheme!OpenThemeData` at `0x180197000`
- `UxTheme!OpenThemeData` at `0x18019703d`
- `UxTheme!OpenThemeData` at `0x18019707a`
- `UxTheme!OpenThemeData` at `0x1801970b7`
- `UxTheme!OpenThemeData` at `0x1801970f4`
- `UxTheme!OpenThemeData` at `0x180197131`
- `UxTheme!OpenThemeData` at `0x18019716e`
- `UxTheme!OpenThemeData` at `0x1801971ab`
- `UxTheme!OpenThemeData` at `0x1801971e8`
- `UxTheme!OpenThemeData` at `0x180197225`
- `UxTheme!OpenThemeData` at `0x180197265`
- `UxTheme!OpenThemeData` at `0x1801972a5`
- `UxTheme!OpenThemeData` at `0x1801972e3`

## string_xrefs

- `0x180196fbc`: `COMBOBOX`
- `0x180197167`: `TASKBAND`
- `0x1801971a4`: `TASKBAR`

## pseudocode

```c
void __fastcall CMFCBaseVisualManager::UpdateSystemColors(CMFCBaseVisualManager *this)
{
  HWND v2; // rbx
  CWinThread *m_pCurrentWinThread; // rcx
  __int64 v4; // rax
  HWND v5; // rcx
  CWinThread *v6; // rcx
  __int64 v7; // rax
  HWND v8; // rcx
  CWinThread *v9; // rcx
  __int64 v10; // rax
  HWND v11; // rcx
  CWinThread *v12; // rcx
  __int64 v13; // rax
  HWND v14; // rcx
  CWinThread *v15; // rcx
  __int64 v16; // rax
  HWND v17; // rcx
  CWinThread *v18; // rcx
  __int64 v19; // rax
  HWND v20; // rcx
  CWinThread *v21; // rcx
  __int64 v22; // rax
  HWND v23; // rcx
  CWinThread *v24; // rcx
  __int64 v25; // rax
  HWND v26; // rcx
  CWinThread *v27; // rcx
  __int64 v28; // rax
  HWND v29; // rcx
  CWinThread *v30; // rcx
  __int64 v31; // rax
  HWND v32; // rcx
  CWinThread *v33; // rcx
  __int64 v34; // rax
  HWND v35; // rcx
  CWinThread *v36; // rcx
  __int64 v37; // rax
  HWND v38; // rcx
  CWinThread *v39; // rcx
  __int64 v40; // rax
  HWND v41; // rcx
  CWinThread *v42; // rcx
  __int64 v43; // rax
  HWND v44; // rcx
  CWinThread *v45; // rcx
  __int64 v46; // rax
  HWND v47; // rcx
  CWinThread *v48; // rcx
  __int64 v49; // rax
  HWND v50; // rcx
  CWinThread *v51; // rcx
  __int64 v52; // rax
  HWND v53; // rcx
  CWinThread *v54; // rcx
  __int64 v55; // rax
  HWND v56; // rcx
  CWinThread *v57; // rcx
  __int64 v58; // rax

  v2 = 0;
  m_pCurrentWinThread = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( m_pCurrentWinThread && (v4 = (__int64)m_pCurrentWinThread->GetMainWnd(m_pCurrentWinThread)) != 0 )
    v5 = *(HWND *)(v4 + 64);
  else
    v5 = 0;
  this->m_hThemeWindow = OpenThemeData(v5, L"WINDOW");
  v6 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v6 && (v7 = (__int64)v6->GetMainWnd(v6)) != 0 )
    v8 = *(HWND *)(v7 + 64);
  else
    v8 = 0;
  this->m_hThemeToolBar = OpenThemeData(v8, L"TOOLBAR");
  v9 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v9 && (v10 = (__int64)v9->GetMainWnd(v9)) != 0 )
    v11 = *(HWND *)(v10 + 64);
  else
    v11 = 0;
  this->m_hThemeButton = OpenThemeData(v11, L"BUTTON");
  v12 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v12 && (v13 = (__int64)v12->GetMainWnd(v12)) != 0 )
    v14 = *(HWND *)(v13 + 64);
  else
    v14 = 0;
  this->m_hThemeStatusBar = OpenThemeData(v14, L"STATUS");
  v15 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v15 && (v16 = (__int64)v15->GetMainWnd(v15)) != 0 )
    v17 = *(HWND *)(v16 + 64);
  else
    v17 = 0;
  this->m_hThemeRebar = OpenThemeData(v17, L"REBAR");
  v18 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v18 && (v19 = (__int64)v18->GetMainWnd(v18)) != 0 )
    v20 = *(HWND *)(v19 + 64);
  else
    v20 = 0;
  this->m_hThemeComboBox = OpenThemeData(v20, L"COMBOBOX");
  v21 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v21 && (v22 = (__int64)v21->GetMainWnd(v21)) != 0 )
    v23 = *(HWND *)(v22 + 64);
  else
    v23 = 0;
  this->m_hThemeProgress = OpenThemeData(v23, L"PROGRESS");
  v24 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v24 && (v25 = (__int64)v24->GetMainWnd(v24)) != 0 )
    v26 = *(HWND *)(v25 + 64);
  else
    v26 = 0;
  this->m_hThemeHeader = OpenThemeData(v26, L"HEADER");
  v27 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v27 && (v28 = (__int64)v27->GetMainWnd(v27)) != 0 )
    v29 = *(HWND *)(v28 + 64);
  else
    v29 = 0;
  this->m_hThemeScrollBar = OpenThemeData(v29, L"SCROLLBAR");
  v30 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v30 && (v31 = (__int64)v30->GetMainWnd(v30)) != 0 )
    v32 = *(HWND *)(v31 + 64);
  else
    v32 = 0;
  this->m_hThemeExplorerBar = OpenThemeData(v32, L"EXPLORERBAR");
  v33 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v33 && (v34 = (__int64)v33->GetMainWnd(v33)) != 0 )
    v35 = *(HWND *)(v34 + 64);
  else
    v35 = 0;
  this->m_hThemeTree = OpenThemeData(v35, L"TREEVIEW");
  v36 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v36 && (v37 = (__int64)v36->GetMainWnd(v36)) != 0 )
    v38 = *(HWND *)(v37 + 64);
  else
    v38 = 0;
  this->m_hThemeStartPanel = OpenThemeData(v38, L"STARTPANEL");
  v39 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v39 && (v40 = (__int64)v39->GetMainWnd(v39)) != 0 )
    v41 = *(HWND *)(v40 + 64);
  else
    v41 = 0;
  this->m_hThemeTaskBand = OpenThemeData(v41, L"TASKBAND");
  v42 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v42 && (v43 = (__int64)v42->GetMainWnd(v42)) != 0 )
    v44 = *(HWND *)(v43 + 64);
  else
    v44 = 0;
  this->m_hThemeTaskBar = OpenThemeData(v44, L"TASKBAR");
  v45 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v45 && (v46 = (__int64)v45->GetMainWnd(v45)) != 0 )
    v47 = *(HWND *)(v46 + 64);
  else
    v47 = 0;
  this->m_hThemeSpin = OpenThemeData(v47, L"SPIN");
  v48 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v48 && (v49 = (__int64)v48->GetMainWnd(v48)) != 0 )
    v50 = *(HWND *)(v49 + 64);
  else
    v50 = 0;
  this->m_hThemeTab = OpenThemeData(v50, L"TAB");
  v51 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v51 && (v52 = (__int64)v51->GetMainWnd(v51)) != 0 )
    v53 = *(HWND *)(v52 + 64);
  else
    v53 = 0;
  this->m_hThemeToolTip = OpenThemeData(v53, L"TOOLTIP");
  v54 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v54 && (v55 = (__int64)v54->GetMainWnd(v54)) != 0 )
    v56 = *(HWND *)(v55 + 64);
  else
    v56 = 0;
  this->m_hThemeTrack = OpenThemeData(v56, L"TRACKBAR");
  v57 = AfxGetModuleThreadState()->m_pCurrentWinThread;
  if ( v57 )
  {
    v58 = (__int64)v57->GetMainWnd(v57);
    if ( v58 )
      v2 = *(HWND *)(v58 + 64);
  }
  this->m_hThemeMenu = OpenThemeData(v2, L"MENU");
}

```

## disassembly

```asm
0x180196e50  mov     [rsp+arg_0], rbx
0x180196e55  push    rdi
0x180196e56  sub     rsp, 20h
0x180196e5a  mov     rdi, this
0x180196e5d  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180196e62  xor     ebx, ebx
0x180196e64  mov     this, [rax+8]
0x180196e68  test    this, this
0x180196e6b  jz      short loc_180196E88
0x180196e6d  mov     rax, [this]
0x180196e70  mov     rax, [rax+0F8h]
0x180196e77  call    cs:__guard_dispatch_icall_fptr
0x180196e7d  test    rax, rax
0x180196e80  jz      short loc_180196E88
0x180196e82  mov     this, [rax+40h]
0x180196e86  jmp     short loc_180196E8B
0x180196e88  mov     this, rbx; hwnd
0x180196e8b  lea     rdx, aWindow; "WINDOW"
0x180196e92  call    cs:__imp_OpenThemeData
0x180196e98  mov     [rdi+8], rax
0x180196e9c  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180196ea1  mov     this, [rax+8]
0x180196ea5  test    this, this
0x180196ea8  jz      short loc_180196EC5
0x180196eaa  mov     rax, [this]
0x180196ead  mov     rax, [rax+0F8h]
0x180196eb4  call    cs:__guard_dispatch_icall_fptr
0x180196eba  test    rax, rax
0x180196ebd  jz      short loc_180196EC5
0x180196ebf  mov     this, [rax+40h]
0x180196ec3  jmp     short loc_180196EC8
0x180196ec5  mov     this, rbx; hwnd
0x180196ec8  lea     rdx, aToolbar; "TOOLBAR"
0x180196ecf  call    cs:__imp_OpenThemeData
0x180196ed5  mov     [rdi+10h], rax
0x180196ed9  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180196ede  mov     this, [rax+8]
0x180196ee2  test    this, this
0x180196ee5  jz      short loc_180196F02
0x180196ee7  mov     rax, [this]
0x180196eea  mov     rax, [rax+0F8h]
0x180196ef1  call    cs:__guard_dispatch_icall_fptr
0x180196ef7  test    rax, rax
0x180196efa  jz      short loc_180196F02
0x180196efc  mov     this, [rax+40h]
0x180196f00  jmp     short loc_180196F05
0x180196f02  mov     this, rbx; hwnd
0x180196f05  lea     rdx, aButton; "BUTTON"
0x180196f0c  call    cs:__imp_OpenThemeData
0x180196f12  mov     [rdi+20h], rax
0x180196f16  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180196f1b  mov     this, [rax+8]
0x180196f1f  test    this, this
0x180196f22  jz      short loc_180196F3F
0x180196f24  mov     rax, [this]
0x180196f27  mov     rax, [rax+0F8h]
0x180196f2e  call    cs:__guard_dispatch_icall_fptr
0x180196f34  test    rax, rax
0x180196f37  jz      short loc_180196F3F
0x180196f39  mov     this, [rax+40h]
0x180196f3d  jmp     short loc_180196F42
0x180196f3f  mov     this, rbx; hwnd
0x180196f42  lea     rdx, aStatus; "STATUS"
0x180196f49  call    cs:__imp_OpenThemeData
0x180196f4f  mov     [rdi+28h], rax
0x180196f53  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180196f58  mov     this, [rax+8]
0x180196f5c  test    this, this
0x180196f5f  jz      short loc_180196F7C
0x180196f61  mov     rax, [this]
0x180196f64  mov     rax, [rax+0F8h]
0x180196f6b  call    cs:__guard_dispatch_icall_fptr
0x180196f71  test    rax, rax
0x180196f74  jz      short loc_180196F7C
0x180196f76  mov     this, [rax+40h]
0x180196f7a  jmp     short loc_180196F7F
0x180196f7c  mov     this, rbx; hwnd
0x180196f7f  lea     rdx, aRebar; "REBAR"
0x180196f86  call    cs:__imp_OpenThemeData
0x180196f8c  mov     [rdi+18h], rax
0x180196f90  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180196f95  mov     this, [rax+8]
0x180196f99  test    this, this
0x180196f9c  jz      short loc_180196FB9
0x180196f9e  mov     rax, [this]
0x180196fa1  mov     rax, [rax+0F8h]
0x180196fa8  call    cs:__guard_dispatch_icall_fptr
0x180196fae  test    rax, rax
0x180196fb1  jz      short loc_180196FB9
0x180196fb3  mov     this, [rax+40h]
0x180196fb7  jmp     short loc_180196FBC
0x180196fb9  mov     this, rbx; hwnd
0x180196fbc  lea     rdx, aCombobox_1; "COMBOBOX"
0x180196fc3  call    cs:__imp_OpenThemeData
0x180196fc9  mov     [rdi+30h], rax
0x180196fcd  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180196fd2  mov     this, [rax+8]
0x180196fd6  test    this, this
0x180196fd9  jz      short loc_180196FF6
0x180196fdb  mov     rax, [this]
0x180196fde  mov     rax, [rax+0F8h]
0x180196fe5  call    cs:__guard_dispatch_icall_fptr
0x180196feb  test    rax, rax
0x180196fee  jz      short loc_180196FF6
0x180196ff0  mov     this, [rax+40h]
0x180196ff4  jmp     short loc_180196FF9
0x180196ff6  mov     this, rbx; hwnd
0x180196ff9  lea     rdx, aProgress_0; "PROGRESS"
0x180197000  call    cs:__imp_OpenThemeData
0x180197006  mov     [rdi+38h], rax
0x18019700a  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x18019700f  mov     this, [rax+8]
0x180197013  test    this, this
0x180197016  jz      short loc_180197033
0x180197018  mov     rax, [this]
0x18019701b  mov     rax, [rax+0F8h]
0x180197022  call    cs:__guard_dispatch_icall_fptr
0x180197028  test    rax, rax
0x18019702b  jz      short loc_180197033
0x18019702d  mov     this, [rax+40h]
0x180197031  jmp     short loc_180197036
0x180197033  mov     this, rbx; hwnd
0x180197036  lea     rdx, aHeader; "HEADER"
0x18019703d  call    cs:__imp_OpenThemeData
0x180197043  mov     [rdi+40h], rax
0x180197047  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x18019704c  mov     this, [rax+8]
0x180197050  test    this, this
0x180197053  jz      short loc_180197070
0x180197055  mov     rax, [this]
0x180197058  mov     rax, [rax+0F8h]
0x18019705f  call    cs:__guard_dispatch_icall_fptr
0x180197065  test    rax, rax
0x180197068  jz      short loc_180197070
0x18019706a  mov     this, [rax+40h]
0x18019706e  jmp     short loc_180197073
0x180197070  mov     this, rbx; hwnd
0x180197073  lea     rdx, aScrollbar; "SCROLLBAR"
0x18019707a  call    cs:__imp_OpenThemeData
0x180197080  mov     [rdi+48h], rax
0x180197084  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180197089  mov     this, [rax+8]
0x18019708d  test    this, this
0x180197090  jz      short loc_1801970AD
0x180197092  mov     rax, [this]
0x180197095  mov     rax, [rax+0F8h]
0x18019709c  call    cs:__guard_dispatch_icall_fptr
0x1801970a2  test    rax, rax
0x1801970a5  jz      short loc_1801970AD
0x1801970a7  mov     this, [rax+40h]
0x1801970ab  jmp     short loc_1801970B0
0x1801970ad  mov     this, rbx; hwnd
0x1801970b0  lea     rdx, aExplorerbar; "EXPLORERBAR"
0x1801970b7  call    cs:__imp_OpenThemeData
0x1801970bd  mov     [rdi+50h], rax
0x1801970c1  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x1801970c6  mov     this, [rax+8]
0x1801970ca  test    this, this
0x1801970cd  jz      short loc_1801970EA
0x1801970cf  mov     rax, [this]
0x1801970d2  mov     rax, [rax+0F8h]
0x1801970d9  call    cs:__guard_dispatch_icall_fptr
0x1801970df  test    rax, rax
0x1801970e2  jz      short loc_1801970EA
0x1801970e4  mov     this, [rax+40h]
0x1801970e8  jmp     short loc_1801970ED
0x1801970ea  mov     this, rbx; hwnd
0x1801970ed  lea     rdx, aTreeview; "TREEVIEW"
0x1801970f4  call    cs:__imp_OpenThemeData
0x1801970fa  mov     [rdi+58h], rax
0x1801970fe  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180197103  mov     this, [rax+8]
0x180197107  test    this, this
0x18019710a  jz      short loc_180197127
0x18019710c  mov     rax, [this]
0x18019710f  mov     rax, [rax+0F8h]
0x180197116  call    cs:__guard_dispatch_icall_fptr
0x18019711c  test    rax, rax
0x18019711f  jz      short loc_180197127
0x180197121  mov     this, [rax+40h]
0x180197125  jmp     short loc_18019712A
0x180197127  mov     this, rbx; hwnd
0x18019712a  lea     rdx, aStartpanel; "STARTPANEL"
0x180197131  call    cs:__imp_OpenThemeData
0x180197137  mov     [rdi+60h], rax
0x18019713b  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180197140  mov     this, [rax+8]
0x180197144  test    this, this
0x180197147  jz      short loc_180197164
0x180197149  mov     rax, [this]
0x18019714c  mov     rax, [rax+0F8h]
0x180197153  call    cs:__guard_dispatch_icall_fptr
0x180197159  test    rax, rax
0x18019715c  jz      short loc_180197164
0x18019715e  mov     this, [rax+40h]
0x180197162  jmp     short loc_180197167
0x180197164  mov     this, rbx; hwnd
0x180197167  lea     rdx, aTaskband; "TASKBAND"
0x18019716e  call    cs:__imp_OpenThemeData
0x180197174  mov     [rdi+68h], rax
0x180197178  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x18019717d  mov     this, [rax+8]
0x180197181  test    this, this
0x180197184  jz      short loc_1801971A1
0x180197186  mov     rax, [this]
0x180197189  mov     rax, [rax+0F8h]
0x180197190  call    cs:__guard_dispatch_icall_fptr
0x180197196  test    rax, rax
0x180197199  jz      short loc_1801971A1
0x18019719b  mov     this, [rax+40h]
0x18019719f  jmp     short loc_1801971A4
0x1801971a1  mov     this, rbx; hwnd
0x1801971a4  lea     rdx, aTaskbar; "TASKBAR"
0x1801971ab  call    cs:__imp_OpenThemeData
0x1801971b1  mov     [rdi+70h], rax
0x1801971b5  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x1801971ba  mov     this, [rax+8]
0x1801971be  test    this, this
0x1801971c1  jz      short loc_1801971DE
0x1801971c3  mov     rax, [this]
0x1801971c6  mov     rax, [rax+0F8h]
0x1801971cd  call    cs:__guard_dispatch_icall_fptr
0x1801971d3  test    rax, rax
0x1801971d6  jz      short loc_1801971DE
0x1801971d8  mov     this, [rax+40h]
0x1801971dc  jmp     short loc_1801971E1
0x1801971de  mov     this, rbx; hwnd
0x1801971e1  lea     rdx, aSpin; "SPIN"
0x1801971e8  call    cs:__imp_OpenThemeData
0x1801971ee  mov     [rdi+78h], rax
0x1801971f2  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x1801971f7  mov     this, [rax+8]
0x1801971fb  test    this, this
0x1801971fe  jz      short loc_18019721B
0x180197200  mov     rax, [this]
0x180197203  mov     rax, [rax+0F8h]
0x18019720a  call    cs:__guard_dispatch_icall_fptr
0x180197210  test    rax, rax
0x180197213  jz      short loc_18019721B
0x180197215  mov     this, [rax+40h]
0x180197219  jmp     short loc_18019721E
0x18019721b  mov     this, rbx; hwnd
0x18019721e  lea     rdx, aTab; "TAB"
0x180197225  call    cs:__imp_OpenThemeData
0x18019722b  mov     [rdi+80h], rax
0x180197232  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180197237  mov     this, [rax+8]
0x18019723b  test    this, this
0x18019723e  jz      short loc_18019725B
0x180197240  mov     rax, [this]
0x180197243  mov     rax, [rax+0F8h]
0x18019724a  call    cs:__guard_dispatch_icall_fptr
0x180197250  test    rax, rax
0x180197253  jz      short loc_18019725B
0x180197255  mov     this, [rax+40h]
0x180197259  jmp     short loc_18019725E
0x18019725b  mov     this, rbx; hwnd
0x18019725e  lea     rdx, aTooltip; "TOOLTIP"
0x180197265  call    cs:__imp_OpenThemeData
0x18019726b  mov     [rdi+88h], rax
0x180197272  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180197277  mov     this, [rax+8]
0x18019727b  test    this, this
0x18019727e  jz      short loc_18019729B
0x180197280  mov     rax, [this]
0x180197283  mov     rax, [rax+0F8h]
0x18019728a  call    cs:__guard_dispatch_icall_fptr
0x180197290  test    rax, rax
0x180197293  jz      short loc_18019729B
0x180197295  mov     this, [rax+40h]
0x180197299  jmp     short loc_18019729E
0x18019729b  mov     this, rbx; hwnd
0x18019729e  lea     rdx, aTrackbar; "TRACKBAR"
0x1801972a5  call    cs:__imp_OpenThemeData
0x1801972ab  mov     [rdi+90h], rax
0x1801972b2  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x1801972b7  mov     this, [rax+8]
0x1801972bb  test    this, this
0x1801972be  jz      short loc_1801972D9
0x1801972c0  mov     rax, [this]
0x1801972c3  mov     rax, [rax+0F8h]
0x1801972ca  call    cs:__guard_dispatch_icall_fptr
0x1801972d0  test    rax, rax
0x1801972d3  jz      short loc_1801972D9
0x1801972d5  mov     rbx, [rax+40h]
0x1801972d9  lea     rdx, aMenu; "MENU"
0x1801972e0  mov     this, rbx; hwnd
0x1801972e3  call    cs:__imp_OpenThemeData
0x1801972e9  mov     rbx, [rsp+28h+arg_0]
0x1801972ee  mov     [rdi+98h], rax
0x1801972f5  add     rsp, 20h
0x1801972f9  pop     rdi
0x1801972fa  retn
```
