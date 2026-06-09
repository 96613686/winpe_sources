# CreateHelpWindow(char const *,char const *,HWND__ *,CHmData *)

- ea: `0x18006eaf4`
- end: `0x18006f5ac`
- name: `?CreateHelpWindow@@YAPEAVCHHWinType@@PEBD0PEAUHWND__@@PEAVCHmData@@@Z`
- size: `2744`
- prototype: `struct CHHWinType *__fastcall(const char *, const char *, HWND, struct CHmData *)`
- caller_count: `1`
- callee_count: `41`
- tags: `loader_planting`

## callers

- `0x180038640`

## callees

- `0x180001728`
- `0x180003fc0`
- `0x1800053b4`
- `0x180005a4c`
- `0x180006708`
- `0x18000f460`
- `0x180011490`
- `0x1800115b0`
- `0x180011b84`
- `0x1800139bc`
- `0x18001706c`
- `0x18001745c`
- `0x18002e344`
- `0x180042da8`
- `0x18004f8dc`
- `0x1800500b4`
- `0x180050158`
- `0x180050ca4`
- `0x1800519d4`
- `0x180051d4c`
- `0x1800521f4`
- `0x180052258`
- `0x180053170`
- `0x1800536a0`
- `0x180059018`
- `0x1800590a4`
- `0x1800590f0`
- `0x180064acc`
- `0x1800675c0`
- `0x180067798`
- `0x18006a480`
- `0x18006a7ac`
- `0x18006e9dc`
- `0x18006eaf4`
- `0x18006f6e4`
- `0x18006f804`
- `0x18006f994`
- `0x18006fb0c`
- `0x180075c5a`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18006f238`
- `msvcrt!_wtoi` at `0x18006f238`
- `KERNEL32!GetSystemDefaultLCID` at `0x18006f419`
- `KERNEL32!GetSystemDefaultLCID` at `0x18006f419`
- `USER32!CopyRect` at `0x18006ec4f`
- `USER32!CopyRect` at `0x18006ec4f`
- `USER32!AppendMenuW` at `0x18006ef0e`
- `USER32!AppendMenuW` at `0x18006ef5c`
- `USER32!AppendMenuW` at `0x18006f57a`
- `USER32!AppendMenuW` at `0x18006f598`
- `USER32!AppendMenuW` at `0x18006ef0e`
- `USER32!AppendMenuW` at `0x18006ef5c`
- `USER32!AppendMenuW` at `0x18006f57a`
- `USER32!AppendMenuW` at `0x18006f598`
- `USER32!AppendMenuA` at `0x18006eee7`
- `USER32!AppendMenuA` at `0x18006eee7`
- `USER32!LoadStringA` at `0x18006f078`
- `USER32!LoadStringA` at `0x18006f078`
- `USER32!LoadStringW` at `0x18006f22b`
- `USER32!LoadStringW` at `0x18006f22b`
- `USER32!IsRectEmpty` at `0x18006ec2a`
- `USER32!IsRectEmpty` at `0x18006ed2a`
- `USER32!IsRectEmpty` at `0x18006ec2a`
- `USER32!IsRectEmpty` at `0x18006ed2a`
- `USER32!GetSystemMenu` at `0x18006eecd`
- `USER32!GetSystemMenu` at `0x18006eecd`
- `USER32!SetMenu` at `0x18006ef8c`
- `USER32!SetMenu` at `0x18006ef8c`
- `USER32!GetMenu` at `0x18006f555`
- `USER32!GetMenu` at `0x18006f555`
- `USER32!SetWindowTextA` at `0x18006f089`
- `USER32!SetWindowTextA` at `0x18006f495`
- `USER32!SetWindowTextA` at `0x18006f4d3`
- `USER32!SetWindowTextA` at `0x18006f089`
- `USER32!SetWindowTextA` at `0x18006f495`
- `USER32!SetWindowTextA` at `0x18006f4d3`
- `USER32!ShowWindow` at `0x18006f27b`
- `USER32!ShowWindow` at `0x18006f4e0`
- `USER32!ShowWindow` at `0x18006f4fa`
- `USER32!ShowWindow` at `0x18006f514`
- `USER32!ShowWindow` at `0x18006f537`
- `USER32!ShowWindow` at `0x18006f27b`
- `USER32!ShowWindow` at `0x18006f4e0`
- `USER32!ShowWindow` at `0x18006f4fa`
- `USER32!ShowWindow` at `0x18006f514`
- `USER32!ShowWindow` at `0x18006f537`
- `USER32!GetWindowLongA` at `0x18006ee8e`
- `USER32!GetWindowLongA` at `0x18006ee8e`
- `USER32!SetWindowLongA` at `0x18006eea8`
- `USER32!SetWindowLongA` at `0x18006eea8`
- `USER32!DestroyWindow` at `0x18006f337`
- `USER32!DestroyWindow` at `0x18006f337`
- `USER32!IsWindow` at `0x18006ecca`
- `USER32!IsWindow` at `0x18006ed43`
- `USER32!IsWindow` at `0x18006ecca`
- `USER32!IsWindow` at `0x18006ed43`
- `USER32!SendMessageA` at `0x18006ece8`
- `USER32!SendMessageA` at `0x18006eec1`
- `USER32!SendMessageA` at `0x18006f0a8`
- `USER32!SendMessageA` at `0x18006f0bb`
- `USER32!SendMessageA` at `0x18006f0d0`
- `USER32!SendMessageA` at `0x18006f0e5`
- `USER32!SendMessageA` at `0x18006f0fe`
- `USER32!SendMessageA` at `0x18006f142`
- `USER32!SendMessageA` at `0x18006f181`
- `USER32!SendMessageA` at `0x18006f24d`
- `USER32!SendMessageA` at `0x18006ece8`
- `USER32!SendMessageA` at `0x18006eec1`
- `USER32!SendMessageA` at `0x18006f0a8`
- `USER32!SendMessageA` at `0x18006f0bb`
- `USER32!SendMessageA` at `0x18006f0d0`
- `USER32!SendMessageA` at `0x18006f0e5`
- `USER32!SendMessageA` at `0x18006f0fe`
- `USER32!SendMessageA` at `0x18006f142`
- `USER32!SendMessageA` at `0x18006f181`
- `USER32!SendMessageA` at `0x18006f24d`
- `USER32!SendMessageW` at `0x18006f1f6`
- `USER32!SendMessageW` at `0x18006f1f6`
- `USER32!GetSubMenu` at `0x18006f563`
- `USER32!GetSubMenu` at `0x18006f563`
- `USER32!LoadMenuA` at `0x18006ef7f`
- `USER32!LoadMenuA` at `0x18006ef7f`

## pseudocode

```c
struct CHHWinType *__fastcall CreateHelpWindow(char *a1, const char *a2, HWND a3, struct CHmData *a4)
{
  char *v7; // rbx
  int v8; // r9d
  struct CHHWinType *WindowSlot; // rax
  struct CHHWinType *v10; // rdi
  __int64 v11; // rax
  CState *v12; // r15
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rax
  int *v16; // rbx
  int v17; // edx
  int v18; // r8d
  int *v19; // r15
  int v20; // eax
  int *v21; // rcx
  int v22; // r8d
  int v23; // r8d
  int v24; // eax
  int v25; // r12d
  int v26; // ebx
  HINSTANCE v27; // r13
  int v28; // r9d
  int v29; // r10d
  DWORD v30; // r11d
  int v31; // eax
  HWND Window; // rax
  LONG WindowLongA; // eax
  __int64 v34; // rcx
  HFONT AccessableUIFont; // rax
  HMENU SystemMenu; // rbx
  const WCHAR *StringResourceW; // rax
  const char *v38; // rax
  unsigned int v39; // edx
  const WCHAR *v40; // rax
  HINSTANCE ResourceInstance; // rax
  HMENU MenuA; // rax
  int ToolBar; // eax
  WPARAM v44; // rbx
  __int64 v45; // rax
  HINSTANCE v46; // rax
  CResourceCache *v47; // rcx
  HFONT v48; // rax
  unsigned int v49; // eax
  int v50; // r9d
  LPARAM ImageA; // rax
  HWND v52; // rcx
  unsigned int v53; // eax
  int v54; // r9d
  LPARAM v55; // rax
  HWND v56; // rcx
  unsigned __int64 v57; // rdx
  __int64 v58; // rcx
  int v59; // ebx
  __int64 v60; // r8
  HINSTANCE v61; // rax
  int v62; // eax
  CHAR *v63; // rax
  char *v65; // rax
  const char *v66; // rdx
  char v67; // cl
  int v68; // ebx
  HWND v69; // rdx
  struct tagRECT *p_rcSrc; // r8
  int v71; // ebx
  __int16 v72; // bx
  __int16 SystemDefaultLCID; // r15
  __int64 v74; // r14
  __int16 v75; // r12
  CTitleInformation *v76; // r14
  const char *StringResource; // rax
  const CHAR *v78; // rdx
  __int64 v79; // rax
  HMENU Menu; // rax
  HMENU SubMenu; // rbx
  const WCHAR *v82; // rax
  unsigned __int64 *v83; // [rsp+20h] [rbp-E0h]
  unsigned int v84; // [rsp+28h] [rbp-D8h]
  unsigned int v85; // [rsp+28h] [rbp-D8h]
  unsigned int v86; // [rsp+28h] [rbp-D8h]
  LPCSTR lpString; // [rsp+60h] [rbp-A0h] BYREF
  RECT rcSrc; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v89[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _TBBUTTON lParam[18]; // [rsp+A0h] [rbp-60h] BYREF
  char v91[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  CHAR Buffer[112]; // [rsp+300h] [rbp+200h] BYREF
  wchar_t v93[256]; // [rsp+370h] [rbp+270h] BYREF

  v7 = a1;
  if ( !a1 || !*a1 )
  {
    v8 = dword_18008B6B4++;
    StringCchPrintfA(v91, 0x14u, "win%u", v8);
    v7 = v91;
  }
  if ( !a2 )
  {
    if ( a4 )
      a2 = (const char *)*((_QWORD *)a4 + 17);
    else
      a2 = 0;
  }
  WindowSlot = FindOrCreateWindowSlot(v7, a2);
  v10 = WindowSlot;
  if ( !WindowSlot )
    return 0;
  *((_QWORD *)WindowSlot + 76) = a4;
  if ( a4 )
  {
    v11 = *((_QWORD *)a4 + 16);
    ++*((_DWORD *)a4 + 36);
    memset(v89, 0, 28);
    rcSrc = 0;
    v12 = *(CState **)(v11 + 1336);
    if ( (int)CState::Open(v12, v7, 0) >= 0 )
    {
      LODWORD(lpString) = 0;
      CState::Read(v12, &rcSrc, 4u, (unsigned int *)&lpString);
      if ( rcSrc.left )
        CState::Read(v12, &rcSrc, rcSrc.left, (unsigned int *)&lpString);
      CState::Close(v12);
    }
    if ( rcSrc.left )
    {
      if ( IsRectEmpty((const RECT *)((char *)v10 + 40)) || (*((_DWORD *)v10 + 5) & 0x40000) != 0 )
      {
        *((_DWORD *)v10 + 43) = DWORD1(v89[1]);
        CopyRect((LPRECT)((char *)v10 + 40), (const RECT *)&rcSrc.top);
        v13 = DWORD1(v89[0]);
        *((_DWORD *)v10 + 28) = DWORD1(v89[0]);
        *((_DWORD *)v10 + 130) = v13;
        *((_DWORD *)v10 + 128) = 0;
      }
      v14 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v10 + 76) + 128LL) + 24LL);
      if ( v14 )
        *(_DWORD *)(v14 + 8) = DWORD2(v89[0]);
      *((_DWORD *)v10 + 143) = HIDWORD(v89[0]);
      *((_DWORD *)v10 + 146) = v89[1];
      *((_DWORD *)v10 + 44) = DWORD2(v89[1]);
    }
  }
  v15 = *((int *)v10 + 46);
  if ( (_DWORD)v15 )
  {
    *(_QWORD *)&rcSrc.left = 0;
    *(_QWORD *)&rcSrc.right = v15;
    *(_QWORD *)&v89[0] = 4294966434LL;
    *((_QWORD *)&v89[0] + 1) = v7;
    if ( IsWindow(a3) )
      SendMessageA(a3, 0x4Eu, *((int *)v10 + 46), (LPARAM)&rcSrc);
  }
  if ( !*((_QWORD *)v10 + 1) )
  {
    *((_QWORD *)v10 + 1) = lcStrDup(v7);
    *((_DWORD *)v10 + 14) = 5;
  }
  if ( !dword_18008C8A8 )
  {
    RegisterOurWindow();
    dword_18008C8A8 = 1;
  }
  v16 = (int *)((char *)v10 + 40);
  *((_QWORD *)v10 + 9) = a3;
  if ( IsRectEmpty((const RECT *)((char *)v10 + 40)) )
  {
    rcSrc = 0;
    if ( IsWindow(a3) )
    {
      GetMonitorRect(a3, &rcSrc, v18);
    }
    else
    {
      lpString = 0;
      multiMonitorRectFromPoint(0, &rcSrc, v18);
    }
    v19 = (int *)((char *)v10 + 44);
    v20 = rcSrc.top + 10;
    v21 = (int *)((char *)v10 + 112);
    *((_DWORD *)v10 + 11) = rcSrc.top + 10;
    *((_DWORD *)v10 + 13) = v20 + 450;
    if ( !*((_DWORD *)v10 + 43) && !*v21 )
      *v21 = 290;
    v17 = *((_DWORD *)v10 + 5) & 0x20;
    if ( v17 )
      v22 = *v21;
    else
      v22 = 0;
    v23 = rcSrc.right - v22 - 305;
    *v16 = v23;
    if ( v17 )
      v24 = *v21;
    else
      v24 = 0;
    *((_DWORD *)v10 + 12) = v23 + v24 + 300;
  }
  else
  {
    v19 = (int *)((char *)v10 + 44);
  }
  if ( (*((_DWORD *)v10 + 8) & 0x40000000) == 0 )
    CheckWindowPosition((struct tagRECT *)((char *)v10 + 40), v17);
  v25 = *v16;
  v26 = *v19;
  v27 = hInstance;
  v30 = CHHWinType::GetStyles(v10) | 0x2000000;
  if ( (*((_DWORD *)v10 + 5) & 0x10) != 0 )
    v31 = 0;
  else
    v31 = 4 * (*((_DWORD *)v10 + 5) & 2 | 0x10000);
  Window = (HWND)IsolationAwareCreateWindowExA(
                   (unsigned int)v31 | *((_DWORD *)v10 + 9),
                   "HH Parent",
                   0,
                   v30,
                   v25,
                   v26,
                   v29,
                   v28,
                   a3,
                   0,
                   v27,
                   0);
  *((_QWORD *)v10 + 8) = Window;
  if ( !(unsigned int)IsValidWindow(Window) )
    OOM();
  WindowLongA = GetWindowLongA(*((HWND *)v10 + 8), -20);
  v34 = 0x400000;
  if ( (WindowLongA & 0x400000) != 0 )
    SetWindowLongA(*((HWND *)v10 + 8), -20, WindowLongA ^ 0x400000);
  AccessableUIFont = CResourceCache::GetAccessableUIFont((CResourceCache *)v34);
  SendMessageA(*((HWND *)v10 + 8), 0x30u, (WPARAM)AccessableUIFont, 0);
  SystemMenu = GetSystemMenu(*((HWND *)v10 + 8), 0);
  AppendMenuA(SystemMenu, 0x800u, 0xFFFFFFFF, 0);
  if ( !(unsigned int)NoRun() )
  {
    StringResourceW = GetStringResourceW(0x455u);
    AppendMenuW(SystemMenu, 0, 0xEFFFu, StringResourceW);
  }
  if ( (unsigned int)IsHelpAuthor(a3) )
  {
    v38 = (const char *)((__int64 (__fastcall *)(__int64))pGetDllStringResource)(120623);
    HxAppendMenu(SystemMenu, v39, 0x3EDu, v38);
  }
  else
  {
    v40 = GetStringResourceW(0x1028u);
    AppendMenuW(SystemMenu, 0, 0x3EDu, v40);
  }
  if ( (*((_DWORD *)v10 + 5) & 0x10000) != 0 )
  {
    ResourceInstance = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    MenuA = LoadMenuA(ResourceInstance, (LPCSTR)0x1770);
    SetMenu(*((HWND *)v10 + 8), MenuA);
  }
  if ( (*((_DWORD *)v10 + 5) & 0x4020) != 0 )
  {
    if ( (*((_BYTE *)v10 + 20) & 0x40) != 0 )
      *((_DWORD *)v10 + 146) = 1;
    if ( (*((_DWORD *)v10 + 5) & 0x8000) == 0 )
    {
      memset_0(lParam, 0, sizeof(lParam));
      ToolBar = CHHWinType::CreateToolBar(v10, lParam);
      v44 = ToolBar;
      if ( ToolBar > 0 )
      {
        v45 = IsolationAwareCreateWindowExA(
                0,
                "ToolbarWindow32",
                0,
                ~(unsigned __int8)(*((_DWORD *)v10 + 5) >> 10) & 0x40 | 0x40000B0Du,
                0,
                0,
                100,
                30,
                *((HWND *)v10 + 8),
                (HMENU)0x3EE,
                hInstance,
                0);
        *((_QWORD *)v10 + 11) = v45;
        if ( !v45 )
          return 0;
        v46 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
        LoadStringA(v46, 0x45Fu, Buffer, 100);
        SetWindowTextA(*((HWND *)v10 + 11), Buffer);
        SendMessageA(*((HWND *)v10 + 11), 0x420u, 0, 1310740);
        SendMessageA(*((HWND *)v10 + 11), 0x420u, 0, 1310740);
        SendMessageA(*((HWND *)v10 + 11), 0x41Eu, 0x20u, 0);
        SendMessageA(*((HWND *)v10 + 11), 0x414u, v44, (LPARAM)lParam);
        v48 = CResourceCache::GetAccessableUIFont(v47);
        SendMessageA(*((HWND *)v10 + 11), 0x30u, (WPARAM)v48, 0);
        v49 = (unsigned int)CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
        ImageA = IsolationAwareImageList_LoadImageA(v49, 512, 20, v50, 16711935, v84, 0);
        v52 = (HWND)*((_QWORD *)v10 + 11);
        *((_QWORD *)v10 + 88) = ImageA;
        SendMessageA(v52, 0x430u, 0, ImageA);
        v53 = (unsigned int)CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
        v55 = IsolationAwareImageList_LoadImageA(v53, 513, 20, v54, 16711935, v85, 0);
        v56 = (HWND)*((_QWORD *)v10 + 11);
        *((_QWORD *)v10 + 89) = v55;
        SendMessageA(v56, 0x434u, 0, v55);
        if ( !*((_DWORD *)v10 + 146) )
        {
          v58 = *((_QWORD *)v10 + 72);
          if ( *(_DWORD *)(v58 + 32) - 1 >= 1 )
          {
            v59 = 1;
            do
            {
              v60 = *(_QWORD *)(v58 + 16);
              lpString = 0;
              if ( (int)StringCchCopyExW(
                          v93,
                          v57,
                          *(const unsigned __int16 **)(v60 + 8LL * v59),
                          (unsigned __int16 **)&lpString,
                          v83,
                          v86) < 0 )
                v93[1] = 0;
              else
                *((_WORD *)lpString + 1) = 0;
              SendMessageW(*((HWND *)v10 + 11), 0x44Du, 0, (LPARAM)v93);
              v58 = *((_QWORD *)v10 + 72);
              ++v59;
            }
            while ( v59 <= *(_DWORD *)(v58 + 32) - 1 );
          }
          v61 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
          LoadStringW(v61, 0x411u, v93, 256);
          v62 = _wtoi(v93);
          SendMessageA(*((HWND *)v10 + 11), 0x43Cu, v62, 0);
          CHHWinType::WrapTB(v10);
        }
      }
      else
      {
        *((_DWORD *)v10 + 5) &= ~0x8000u;
      }
    }
    CHHWinType::CalcHtmlPaneRect(v10);
    if ( (*((_DWORD *)v10 + 5) & 0x4000) != 0 )
    {
      CHHWinType::CreateOrShowNavPane(v10);
      ShowWindow(*((HWND *)v10 + 8), *((_DWORD *)v10 + 14));
    }
    else
    {
      CHHWinType::CreateOrShowHTMLPane(v10);
    }
  }
  if ( (unsigned int)IsValidWindow(*((HWND *)v10 + 8)) )
  {
    if ( (*((_DWORD *)v10 + 5) & 0x4000) != 0 )
      goto LABEL_94;
    v63 = (CHAR *)operator new(0xB8u);
    lpString = v63;
    if ( v63 )
    {
      *((_DWORD *)v63 + 3) = 0;
      *(_QWORD *)v63 = &CContainer::`vftable';
      *((_QWORD *)v63 + 2) = 0;
      *((_QWORD *)v63 + 3) = 0;
      *((_QWORD *)v63 + 6) = 0;
      *((_QWORD *)v63 + 7) = 0;
      *((_QWORD *)v63 + 8) = 0;
      *((_QWORD *)v63 + 9) = 0;
      *((_QWORD *)v63 + 12) = 0;
      *((_QWORD *)v63 + 18) = 0;
      *((_QWORD *)v63 + 19) = 0;
      *((_QWORD *)v63 + 11) = 0;
      *((_QWORD *)v63 + 10) = 0;
      *((_QWORD *)v63 + 21) = 0;
      *((_DWORD *)v63 + 34) = 0;
      *((_QWORD *)v63 + 20) = 0;
      *((_QWORD *)v63 + 13) = 0;
      *((_QWORD *)v63 + 14) = 0;
      *((_QWORD *)v63 + 15) = 0;
      *((_QWORD *)v63 + 16) = 0;
    }
    else
    {
      v63 = 0;
    }
    *((_QWORD *)v10 + 75) = v63;
    if ( v63 )
    {
      v65 = (char *)*((_QWORD *)v10 + 1);
      v66 = (const char *)("$global_hhPrint" - v65);
      while ( 1 )
      {
        v67 = *v65;
        if ( *v65 != v66[(_QWORD)v65] )
          break;
        ++v65;
        if ( !v67 )
        {
          v68 = 0;
          goto LABEL_89;
        }
      }
      v68 = (unsigned __int8)*v65 < (unsigned int)v66[(_QWORD)v65] ? -1 : 1;
LABEL_89:
      if ( (unsigned int)IsValidWindow(*((HWND *)v10 + 13)) )
      {
        v69 = (HWND)*((_QWORD *)v10 + 13);
        p_rcSrc = (struct tagRECT *)((char *)v10 + 116);
      }
      else
      {
        rcSrc = 0;
        CHHWinType::GetClientRect(v10, &rcSrc);
        v69 = (HWND)*((_QWORD *)v10 + 8);
        p_rcSrc = &rcSrc;
      }
      if ( (int)CContainer::Create(*((struct IUnknown **)v10 + 75), v69, p_rcSrc, v68) >= 0 )
      {
LABEL_94:
        if ( !*((_DWORD *)v10 + 43) && (unsigned int)CHHWinType::GetValidNavPane(v10) != -1 )
        {
          v71 = *((_DWORD *)v10 + 143);
          *((_DWORD *)v10 + 143) = 1;
          *((_DWORD *)v10 + 43) = 1;
          CHHWinType::ToggleExpansion(v10, 0);
          *((_DWORD *)v10 + 143) = v71;
        }
        v72 = -258;
        SystemDefaultLCID = GetSystemDefaultLCID();
        CLanguage::_Init((CLanguage *)&off_18008B4C0);
        v74 = *((_QWORD *)v10 + 76);
        v75 = word_18008B4C8;
        if ( v74 )
        {
          v76 = *(CTitleInformation **)(v74 + 192);
          if ( v76 )
          {
            CTitleInformation::Init(v76);
            v72 = *((_WORD *)v76 + 8);
          }
        }
        if ( v72 == SystemDefaultLCID || (v72 & 0x3FF) == 9 )
        {
          v78 = (const CHAR *)*((_QWORD *)v10 + 3);
          if ( v78 )
            goto LABEL_107;
          v79 = *((_QWORD *)v10 + 76);
          if ( v79 )
          {
            v78 = *(const CHAR **)(v79 + 176);
            if ( v78 )
              goto LABEL_107;
          }
        }
        else if ( v75 == SystemDefaultLCID )
        {
          StringResource = GetStringResource(0x1027u);
          CStr::CStr((CStr *)&lpString, StringResource);
          SetWindowTextA(*((HWND *)v10 + 8), lpString);
          CWStr::~CWStr((CWStr *)&lpString);
LABEL_108:
          ShowWindow(*((HWND *)v10 + 8), *((_DWORD *)v10 + 14));
          if ( (unsigned int)IsValidWindow(*((HWND *)v10 + 11)) )
            ShowWindow(*((HWND *)v10 + 11), *((_DWORD *)v10 + 14));
          if ( (unsigned int)IsValidWindow(*((HWND *)v10 + 13)) )
            ShowWindow(*((HWND *)v10 + 13), *((_DWORD *)v10 + 14));
          if ( !*((_DWORD *)v10 + 43) && (unsigned int)IsValidWindow(*((HWND *)v10 + 12)) )
            ShowWindow(*((HWND *)v10 + 12), *((_DWORD *)v10 + 14));
          if ( (*((_DWORD *)v10 + 5) & 0x10000) != 0 && a4 )
          {
            if ( *((_DWORD *)a4 + 29) )
            {
              Menu = GetMenu(*((HWND *)v10 + 8));
              SubMenu = GetSubMenu(Menu, 2);
              AppendMenuW(SubMenu, 0x800u, 0, 0);
              v82 = GetStringResourceW(0x4D2u);
              AppendMenuW(SubMenu, 0, 0x178Au, v82);
            }
          }
          return v10;
        }
        v78 = "HTML Help";
LABEL_107:
        SetWindowTextA(*((HWND *)v10 + 8), v78);
        goto LABEL_108;
      }
    }
    DestroyWindow(*((HWND *)v10 + 8));
    return 0;
  }
  return v10;
}

```

## disassembly

```asm
0x18006eaf4  push    rbp
0x18006eaf6  push    rbx
0x18006eaf7  push    rsi
0x18006eaf8  push    rdi
0x18006eaf9  push    r12
0x18006eafb  push    r13
0x18006eafd  push    r14
0x18006eaff  push    r15
0x18006eb01  lea     rbp, [rsp-488h]
0x18006eb09  sub     rsp, 588h
0x18006eb10  mov     rax, cs:__security_cookie
0x18006eb17  xor     rax, rsp
0x18006eb1a  mov     [rbp+4C0h+var_50], rax
0x18006eb21  xor     r12d, r12d
0x18006eb24  mov     rsi, r9
0x18006eb27  mov     r14, r8
0x18006eb2a  mov     rdi, rdx
0x18006eb2d  mov     rbx, rcx
0x18006eb30  test    rcx, rcx
0x18006eb33  jz      short loc_18006EB3A
0x18006eb35  cmp     [rcx], r12b
0x18006eb38  jnz     short loc_18006EB6A
0x18006eb3a  mov     r9d, cs:dword_18008B6B4
0x18006eb41  lea     r8, aWinU; "win%u"
0x18006eb48  mov     edx, 14h; unsigned __int64
0x18006eb4d  lea     rcx, [rbp+4C0h+var_2E0]; char *
0x18006eb54  lea     eax, [r9+1]
0x18006eb58  mov     cs:dword_18008B6B4, eax
0x18006eb5e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18006eb63  lea     rbx, [rbp+4C0h+var_2E0]
0x18006eb6a  test    rdi, rdi
0x18006eb6d  jnz     short loc_18006EB80
0x18006eb6f  test    rsi, rsi
0x18006eb72  jz      short loc_18006EB7D
0x18006eb74  mov     rdi, [rsi+88h]
0x18006eb7b  jmp     short loc_18006EB80
0x18006eb7d  mov     rdi, r12
0x18006eb80  mov     rdx, rdi; char *
0x18006eb83  mov     rcx, rbx; char *
0x18006eb86  call    ?FindOrCreateWindowSlot@@YAPEAVCHHWinType@@PEBD0@Z; FindOrCreateWindowSlot(char const *,char const *)
0x18006eb8b  mov     rdi, rax
0x18006eb8e  test    rax, rax
0x18006eb91  jz      loc_18006F33D
0x18006eb97  mov     [rax+260h], rsi
0x18006eb9e  test    rsi, rsi
0x18006eba1  jz      loc_18006ECA1
0x18006eba7  mov     rax, [rsi+80h]
0x18006ebae  xorps   xmm0, xmm0
0x18006ebb1  inc     dword ptr [rsi+90h]
0x18006ebb7  xor     r8d, r8d; unsigned int
0x18006ebba  movups  [rsp+5C0h+var_548], xmm0
0x18006ebbf  mov     rdx, rbx; char *
0x18006ebc2  movups  xmmword ptr [rsp+5C0h+rcSrc.left], xmm0
0x18006ebc7  movups  [rbp+4C0h+var_548+0Ch], xmm0
0x18006ebcb  mov     r15, [rax+538h]
0x18006ebd2  mov     rcx, r15; this
0x18006ebd5  call    ?Open@CState@@QEAAJPEBDK@Z; CState::Open(char const *,ulong)
0x18006ebda  test    eax, eax
0x18006ebdc  js      short loc_18006EC1F
0x18006ebde  lea     r9, [rsp+5C0h+lpString]; unsigned int *
0x18006ebe3  mov     dword ptr [rsp+5C0h+lpString], r12d
0x18006ebe8  mov     r8d, 4; unsigned int
0x18006ebee  lea     rdx, [rsp+5C0h+rcSrc]; void *
0x18006ebf3  mov     rcx, r15; this
0x18006ebf6  call    ?Read@CState@@QEAAJPEAXKPEAK@Z; CState::Read(void *,ulong,ulong *)
0x18006ebfb  mov     r8d, [rsp+5C0h+rcSrc.left]; unsigned int
0x18006ec00  test    r8d, r8d
0x18006ec03  jz      short loc_18006EC17
0x18006ec05  lea     r9, [rsp+5C0h+lpString]; unsigned int *
0x18006ec0a  mov     rcx, r15; this
0x18006ec0d  lea     rdx, [rsp+5C0h+rcSrc]; void *
0x18006ec12  call    ?Read@CState@@QEAAJPEAXKPEAK@Z; CState::Read(void *,ulong,ulong *)
0x18006ec17  mov     rcx, r15; this
0x18006ec1a  call    ?Close@CState@@QEAAXXZ; CState::Close(void)
0x18006ec1f  cmp     [rsp+5C0h+rcSrc.left], r12d
0x18006ec24  jz      short loc_18006ECA1
0x18006ec26  lea     rcx, [rdi+28h]; lprc
0x18006ec2a  call    cs:__imp_IsRectEmpty
0x18006ec30  test    eax, eax
0x18006ec32  jnz     short loc_18006EC3D
0x18006ec34  test    dword ptr [rdi+14h], 40000h
0x18006ec3b  jz      short loc_18006EC69
0x18006ec3d  mov     eax, [rbp+4C0h+var_534]
0x18006ec40  lea     rdx, [rsp+5C0h+rcSrc.top]; lprcSrc
0x18006ec45  lea     rcx, [rdi+28h]; lprcDst
0x18006ec49  mov     [rdi+0ACh], eax
0x18006ec4f  call    cs:__imp_CopyRect
0x18006ec55  mov     eax, dword ptr [rsp+5C0h+var_548+4]
0x18006ec59  mov     [rdi+70h], eax
0x18006ec5c  mov     [rdi+208h], eax
0x18006ec62  mov     [rdi+200h], r12d
0x18006ec69  mov     rax, [rdi+260h]
0x18006ec70  mov     rcx, [rax+80h]
0x18006ec77  mov     rdx, [rcx+18h]
0x18006ec7b  test    rdx, rdx
0x18006ec7e  jz      short loc_18006EC86
0x18006ec80  mov     eax, dword ptr [rbp+4C0h+var_548+8]
0x18006ec83  mov     [rdx+8], eax
0x18006ec86  mov     eax, dword ptr [rbp+4C0h+var_548+0Ch]
0x18006ec89  mov     [rdi+23Ch], eax
0x18006ec8f  mov     eax, [rbp+4C0h+var_538]
0x18006ec92  mov     [rdi+248h], eax
0x18006ec98  mov     eax, [rbp+4C0h+var_530]
0x18006ec9b  mov     [rdi+0B0h], eax
0x18006eca1  movsxd  rax, dword ptr [rdi+0B8h]
0x18006eca8  test    eax, eax
0x18006ecaa  jz      short loc_18006ECEE
0x18006ecac  mov     rcx, r14; hWnd
0x18006ecaf  mov     dword ptr [rsp+5C0h+var_548+4], r12d
0x18006ecb4  mov     qword ptr [rsp+5C0h+rcSrc.left], r12
0x18006ecb9  mov     qword ptr [rsp+5C0h+rcSrc.right], rax
0x18006ecbe  mov     dword ptr [rsp+5C0h+var_548], 0FFFFFCA2h
0x18006ecc6  mov     qword ptr [rbp+4C0h+var_548+8], rbx
0x18006ecca  call    cs:__imp_IsWindow
0x18006ecd0  test    eax, eax
0x18006ecd2  jz      short loc_18006ECEE
0x18006ecd4  movsxd  r8, dword ptr [rdi+0B8h]; wParam
0x18006ecdb  lea     r9, [rsp+5C0h+rcSrc]; lParam
0x18006ece0  mov     edx, 4Eh ; 'N'; Msg
0x18006ece5  mov     rcx, r14; hWnd
0x18006ece8  call    cs:__imp_SendMessageA
0x18006ecee  cmp     [rdi+8], r12
0x18006ecf2  jnz     short loc_18006ED07
0x18006ecf4  mov     rcx, rbx; char *
0x18006ecf7  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x18006ecfc  mov     [rdi+8], rax
0x18006ed00  mov     dword ptr [rdi+38h], 5
0x18006ed07  cmp     cs:dword_18008C8A8, r12d
0x18006ed0e  jnz     short loc_18006ED1F
0x18006ed10  call    ?RegisterOurWindow@@YAXXZ; RegisterOurWindow(void)
0x18006ed15  mov     cs:dword_18008C8A8, 1
0x18006ed1f  lea     rbx, [rdi+28h]
0x18006ed23  mov     [rdi+48h], r14
0x18006ed27  mov     rcx, rbx; lprc
0x18006ed2a  call    cs:__imp_IsRectEmpty
0x18006ed30  test    eax, eax
0x18006ed32  jz      loc_18006EDD0
0x18006ed38  xorps   xmm0, xmm0
0x18006ed3b  mov     rcx, r14; hWnd
0x18006ed3e  movups  xmmword ptr [rsp+5C0h+rcSrc.left], xmm0
0x18006ed43  call    cs:__imp_IsWindow
0x18006ed49  lea     rdx, [rsp+5C0h+rcSrc]; struct tagRECT *
0x18006ed4e  test    eax, eax
0x18006ed50  jz      short loc_18006ED5C
0x18006ed52  mov     rcx, r14; HWND
0x18006ed55  call    ?GetMonitorRect@@YAXPEAUHWND__@@PEAUtagRECT@@H@Z; GetMonitorRect(HWND__ *,tagRECT *,int)
0x18006ed5a  jmp     short loc_18006ED69
0x18006ed5c  mov     rcx, r12; struct tagPOINT
0x18006ed5f  mov     [rsp+5C0h+lpString], r12
0x18006ed64  call    ?multiMonitorRectFromPoint@@YAXUtagPOINT@@PEAUtagRECT@@H@Z; multiMonitorRectFromPoint(tagPOINT,tagRECT *,int)
0x18006ed69  mov     eax, [rsp+5C0h+rcSrc.top]
0x18006ed6d  lea     r15, [rdi+2Ch]
0x18006ed71  add     eax, 0Ah
0x18006ed74  lea     rcx, [rdi+70h]
0x18006ed78  mov     [r15], eax
0x18006ed7b  add     eax, 1C2h
0x18006ed80  mov     [rdi+34h], eax
0x18006ed83  cmp     [rdi+0ACh], r12d
0x18006ed8a  jnz     short loc_18006ED97
0x18006ed8c  cmp     [rcx], r12d
0x18006ed8f  jnz     short loc_18006ED97
0x18006ed91  mov     dword ptr [rcx], 122h
0x18006ed97  mov     edx, [rdi+14h]
0x18006ed9a  and     edx, 20h
0x18006ed9d  jz      short loc_18006EDA4
0x18006ed9f  mov     r8d, [rcx]
0x18006eda2  jmp     short loc_18006EDA7
0x18006eda4  mov     r8d, r12d
0x18006eda7  mov     eax, [rsp+5C0h+rcSrc.right]
0x18006edab  sub     eax, r8d
0x18006edae  lea     r8d, [rax-131h]
0x18006edb5  mov     [rbx], r8d
0x18006edb8  test    edx, edx
0x18006edba  jz      short loc_18006EDC0
0x18006edbc  mov     eax, [rcx]
0x18006edbe  jmp     short loc_18006EDC3
0x18006edc0  mov     eax, r12d
0x18006edc3  add     eax, 12Ch
0x18006edc8  add     eax, r8d
0x18006edcb  mov     [rdi+30h], eax
0x18006edce  jmp     short loc_18006EDD4
0x18006edd0  lea     r15, [rdi+2Ch]
0x18006edd4  test    dword ptr [rdi+20h], 40000000h
0x18006eddb  jnz     short loc_18006EDE5
0x18006eddd  mov     rcx, rbx; struct tagRECT *
0x18006ede0  call    ?CheckWindowPosition@@YAXPEAUtagRECT@@H@Z; CheckWindowPosition(tagRECT *,int)
0x18006ede5  mov     r9d, [rbx+0Ch]
0x18006ede9  mov     rcx, rdi; this
0x18006edec  mov     r10d, [rbx+8]
0x18006edf0  mov     r12d, [rbx]
0x18006edf3  sub     r10d, r12d
0x18006edf6  sub     r9d, [rbx+4]
0x18006edfa  mov     ebx, [r15]
0x18006edfd  mov     r13, cs:hInstance
0x18006ee04  call    ?GetStyles@CHHWinType@@QEBAKXZ; CHHWinType::GetStyles(void)
0x18006ee09  mov     ecx, [rdi+24h]
0x18006ee0c  mov     r11d, eax
0x18006ee0f  mov     eax, [rdi+14h]
0x18006ee12  bts     r11d, 19h
0x18006ee17  mov     r15d, 10000h
0x18006ee1d  test    al, 10h
0x18006ee1f  jz      short loc_18006EE25
0x18006ee21  xor     eax, eax
0x18006ee23  jmp     short loc_18006EE2E
0x18006ee25  and     eax, 2
0x18006ee28  or      eax, r15d
0x18006ee2b  shl     eax, 2
0x18006ee2e  mov     [rsp+5C0h+var_568], 0; LPVOID
0x18006ee37  lea     rdx, ?txtHtmlHelpWindowClass@@3QBDB; "HH Parent"
0x18006ee3e  mov     [rsp+5C0h+var_570], r13; HINSTANCE
0x18006ee43  or      ecx, eax; dwExStyle
0x18006ee45  xor     r13d, r13d
0x18006ee48  xor     r8d, r8d; lpWindowName
0x18006ee4b  mov     [rsp+5C0h+var_578], r13; HMENU
0x18006ee50  mov     [rsp+5C0h+var_580], r14; HWND
0x18006ee55  mov     [rsp+5C0h+var_588], r9d; int
0x18006ee5a  mov     r9d, r11d; dwStyle
0x18006ee5d  mov     [rsp+5C0h+var_590], r10d; int
0x18006ee62  mov     [rsp+5C0h+var_598], ebx; int
0x18006ee66  mov     dword ptr [rsp+5C0h+var_5A0], r12d; int
0x18006ee6b  call    IsolationAwareCreateWindowExA
0x18006ee70  mov     rcx, rax; HWND
0x18006ee73  mov     [rdi+40h], rax
0x18006ee77  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x18006ee7c  test    eax, eax
0x18006ee7e  jz      loc_18006F5A6
0x18006ee84  mov     rcx, [rdi+40h]; hWnd
0x18006ee88  lea     ebx, [r13-14h]
0x18006ee8c  mov     edx, ebx; nIndex
0x18006ee8e  call    cs:__imp_GetWindowLongA
0x18006ee94  mov     ecx, 400000h
0x18006ee99  test    ecx, eax
0x18006ee9b  jz      short loc_18006EEAE
0x18006ee9d  xor     eax, ecx
0x18006ee9f  mov     edx, ebx; nIndex
0x18006eea1  mov     rcx, [rdi+40h]; hWnd
0x18006eea5  mov     r8d, eax; dwNewLong
0x18006eea8  call    cs:__imp_SetWindowLongA
0x18006eeae  call    ?GetAccessableUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetAccessableUIFont(void)
0x18006eeb3  mov     rcx, [rdi+40h]; hWnd
0x18006eeb7  xor     r9d, r9d; lParam
0x18006eeba  mov     r8, rax; wParam
0x18006eebd  lea     edx, [r9+30h]; Msg
0x18006eec1  call    cs:__imp_SendMessageA
0x18006eec7  mov     rcx, [rdi+40h]; hWnd
0x18006eecb  xor     edx, edx; bRevert
0x18006eecd  call    cs:__imp_GetSystemMenu
0x18006eed3  xor     r9d, r9d; lpNewItem
0x18006eed6  mov     edx, 800h; uFlags
0x18006eedb  mov     rcx, rax; hMenu
0x18006eede  mov     r8d, 0FFFFFFFFh; uIDNewItem
0x18006eee4  mov     rbx, rax
0x18006eee7  call    cs:__imp_AppendMenuA
0x18006eeed  call    ?NoRun@@YAHXZ; NoRun(void)
0x18006eef2  test    eax, eax
0x18006eef4  jnz     short loc_18006EF14
0x18006eef6  mov     ecx, 455h; uID
0x18006eefb  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18006ef00  mov     r9, rax; lpNewItem
0x18006ef03  xor     edx, edx; uFlags
0x18006ef05  mov     r8d, 0EFFFh; uIDNewItem
0x18006ef0b  mov     rcx, rbx; hMenu
0x18006ef0e  call    cs:__imp_AppendMenuW
0x18006ef14  mov     rcx, r14; HWND
0x18006ef17  call    ?IsHelpAuthor@@YAHPEAUHWND__@@@Z; IsHelpAuthor(HWND__ *)
0x18006ef1c  test    eax, eax
0x18006ef1e  jz      short loc_18006EF44
0x18006ef20  mov     rax, cs:?pGetDllStringResource@@3P6APEBDH@ZEA; char const * (*pGetDllStringResource)(int)
0x18006ef27  mov     ecx, 1D72Fh
0x18006ef2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ef31  mov     r9, rax; char *
0x18006ef34  mov     r8d, 3EDh; unsigned int
0x18006ef3a  mov     rcx, rbx; hMenu
0x18006ef3d  call    ?HxAppendMenu@@YAHPEAUHMENU__@@IIPEBD@Z; HxAppendMenu(HMENU__ *,uint,uint,char const *)
0x18006ef42  jmp     short loc_18006EF62
0x18006ef44  mov     ecx, 1028h; uID
0x18006ef49  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18006ef4e  mov     r9, rax; lpNewItem
0x18006ef51  xor     edx, edx; uFlags
0x18006ef53  mov     r8d, 3EDh; uIDNewItem
0x18006ef59  mov     rcx, rbx; hMenu
0x18006ef5c  call    cs:__imp_AppendMenuW
0x18006ef62  lea     r12, ?_Module@@3VCHtmlHelpModule@@A; CHtmlHelpModule _Module
0x18006ef69  test    [rdi+14h], r15d
0x18006ef6d  jz      short loc_18006EF92
0x18006ef6f  mov     rcx, r12; this
0x18006ef72  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18006ef77  mov     rcx, rax; hInstance
0x18006ef7a  mov     edx, 1770h; lpMenuName
0x18006ef7f  call    cs:__imp_LoadMenuA
0x18006ef85  mov     rcx, [rdi+40h]; hWnd
0x18006ef89  mov     rdx, rax; hMenu
0x18006ef8c  call    cs:__imp_SetMenu
0x18006ef92  test    dword ptr [rdi+14h], 4020h
0x18006ef99  jz      loc_18006F288
0x18006ef9f  test    byte ptr [rdi+14h], 40h
0x18006efa3  jz      short loc_18006EFAF
0x18006efa5  mov     dword ptr [rdi+248h], 1
0x18006efaf  test    dword ptr [rdi+14h], 8000h
0x18006efb6  jnz     loc_18006F25B
  ... truncated ...
```
