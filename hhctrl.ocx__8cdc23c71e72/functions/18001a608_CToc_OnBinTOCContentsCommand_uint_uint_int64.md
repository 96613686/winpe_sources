# CToc::OnBinTOCContentsCommand(uint,uint,__int64)

- ea: `0x18001a608`
- end: `0x18001acb8`
- name: `?OnBinTOCContentsCommand@CToc@@QEAA_JII_J@Z`
- size: `1712`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b410`

## callees

- `0x1800038f4`
- `0x180003fc0`
- `0x180011104`
- `0x1800112f0`
- `0x180011e94`
- `0x1800123d0`
- `0x180018dec`
- `0x1800191b8`
- `0x1800194cc`
- `0x1800197c8`
- `0x18001a608`
- `0x18001d394`
- `0x18001f1cc`
- `0x18001f4b8`
- `0x180020100`
- `0x18002f3e8`
- `0x18002f6d8`
- `0x1800301f8`
- `0x180037448`
- `0x1800535d0`
- `0x18006e4b8`
- `0x18007225c`
- `0x180075c5a`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `USER32!RemovePropA` at `0x18001a8da`
- `USER32!RemovePropA` at `0x18001a8da`
- `USER32!SetCursor` at `0x18001aa85`
- `USER32!SetCursor` at `0x18001ac88`
- `USER32!SetCursor` at `0x18001aa85`
- `USER32!SetCursor` at `0x18001ac88`
- `USER32!DestroyWindow` at `0x18001a8e7`
- `USER32!DestroyWindow` at `0x18001a8e7`
- `USER32!SendMessageA` at `0x18001a7b8`
- `USER32!SendMessageA` at `0x18001a92b`
- `USER32!SendMessageA` at `0x18001a95b`
- `USER32!SendMessageA` at `0x18001a9d2`
- `USER32!SendMessageA` at `0x18001aa0d`
- `USER32!SendMessageA` at `0x18001aa49`
- `USER32!SendMessageA` at `0x18001aa66`
- `USER32!SendMessageA` at `0x18001aa9b`
- `USER32!SendMessageA` at `0x18001aab9`
- `USER32!SendMessageA` at `0x18001ab04`
- `USER32!SendMessageA` at `0x18001ab8c`
- `USER32!SendMessageA` at `0x18001abca`
- `USER32!SendMessageA` at `0x18001ac10`
- `USER32!SendMessageA` at `0x18001ac56`
- `USER32!SendMessageA` at `0x18001ac73`
- `USER32!SendMessageA` at `0x18001a7b8`
- `USER32!SendMessageA` at `0x18001a92b`
- `USER32!SendMessageA` at `0x18001a95b`
- `USER32!SendMessageA` at `0x18001a9d2`
- `USER32!SendMessageA` at `0x18001aa0d`
- `USER32!SendMessageA` at `0x18001aa49`
- `USER32!SendMessageA` at `0x18001aa66`
- `USER32!SendMessageA` at `0x18001aa9b`
- `USER32!SendMessageA` at `0x18001aab9`
- `USER32!SendMessageA` at `0x18001ab04`
- `USER32!SendMessageA` at `0x18001ab8c`
- `USER32!SendMessageA` at `0x18001abca`
- `USER32!SendMessageA` at `0x18001ac10`
- `USER32!SendMessageA` at `0x18001ac56`
- `USER32!SendMessageA` at `0x18001ac73`
- `USER32!GetParent` at `0x18001a6d6`
- `USER32!GetParent` at `0x18001a78e`
- `USER32!GetParent` at `0x18001a7fd`
- `USER32!GetParent` at `0x18001a8c3`
- `USER32!GetParent` at `0x18001a6d6`
- `USER32!GetParent` at `0x18001a78e`
- `USER32!GetParent` at `0x18001a7fd`
- `USER32!GetParent` at `0x18001a8c3`
- `urlmon!HlinkSimpleNavigateToString` at `0x18001a77f`
- `urlmon!HlinkSimpleNavigateToString` at `0x18001a77f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CToc::OnBinTOCContentsCommand(LONG_PTR dwNewLong, int a2)
{
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  CHtmlHelpControl *v7; // rcx
  const char *v8; // rbx
  HWND Parent; // rax
  unsigned __int64 v10; // r9
  HWND v11; // rax
  CHHWinType *v12; // rcx
  HWND v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  CHHWinType *v16; // rcx
  HWND v17; // rbx
  struct _TREEITEM *v18; // rax
  LPARAM v19; // r14
  LPARAM v20; // r9
  __int64 v21; // r14
  LPARAM v22; // r13
  struct _TREEITEM *v23; // rax
  HTREEITEM i; // r9
  LPARAM v25; // r9
  HCURSOR hCursor; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR szTarget; // [rsp+48h] [rbp-B8h] BYREF
  struct tagTVITEMW lParam; // [rsp+50h] [rbp-B0h] BYREF
  LPARAM v30[273]; // [rsp+90h] [rbp-70h] BYREF
  int v31; // [rsp+918h] [rbp+818h]

  v3 = a2 - 250;
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      v5 = v4 - 1;
      if ( v5 )
      {
        v6 = v5 - 1;
        if ( v6 )
        {
          if ( v6 == 61186 )
          {
            hCursor = 0;
            v7 = *(CHtmlHelpControl **)(dwNewLong + 496);
            if ( v7 )
              CHtmlHelpControl::GetCurrentUrl(v7, (struct CStr *)&hCursor);
            else
              COleDispatchDriver::InvokeHelper(
                *(COleDispatchDriver **)(*(_QWORD *)(*(_QWORD *)(dwNewLong + 536) + 600LL) + 152LL),
                211,
                2u,
                8u,
                &hCursor,
                0);
            v8 = (const char *)hCursor;
            Parent = GetParent(*(HWND *)(dwNewLong + 424));
            if ( (unsigned int)doJumpUrl(Parent, v8, (char *)v30, v10) )
            {
              if ( *(_QWORD *)(dwNewLong + 496) )
              {
                szTarget = 0;
                CWStr::operator=(&szTarget, v30);
                if ( !(unsigned int)CHtmlHelpControl::CheckDestUrlSafetyThruMoniker(
                                      *(CHtmlHelpControl **)(dwNewLong + 496),
                                      szTarget,
                                      *(struct IUnknown **)(*(_QWORD *)(dwNewLong + 496) + 8LL)) )
                  HlinkSimpleNavigateToString(
                    szTarget,
                    0,
                    0,
                    *(IUnknown **)(*(_QWORD *)(dwNewLong + 496) + 8LL),
                    0,
                    0,
                    0,
                    0);
                CWStr::~CWStr((CWStr *)&szTarget);
              }
              else
              {
                v11 = GetParent(*(HWND *)(dwNewLong + 424));
                ChangeHtmlTopic((const char *)v30, v11, 0);
              }
            }
            CWStr::~CWStr((CWStr *)&hCursor);
          }
        }
        else if ( SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Au, 9u, 0) )
        {
          v12 = *(CHHWinType **)(dwNewLong + 536);
          if ( v12 )
          {
            if ( !(unsigned int)CHHWinType::OnTrackNotifyCaller(v12, 14) )
              CHHWinType::OnPrint(*(CHHWinType **)(dwNewLong + 536));
          }
          else
          {
            v13 = GetParent(*(HWND *)(dwNewLong + 424));
            CPrint::CPrint((CPrint *)v30, v13);
            v31 = 1;
            if ( (unsigned int)CDlg::DoModal((LPARAM)v30) )
              PrintTopics(
                v31,
                (struct CToc *)dwNewLong,
                *(struct IWebBrowserAppImpl **)(*(_QWORD *)(dwNewLong + 496) + 496LL),
                *(HWND *)(*(_QWORD *)(dwNewLong + 496) + 448LL));
            CDlg::~CDlg((CDlg *)v30);
          }
        }
      }
      else
      {
        v14 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(dwNewLong + 536) + 608LL) + 128LL) + 40LL);
        v15 = *(_QWORD *)(v14 + 88);
        if ( v15 )
          *(_QWORD *)(v14 + 120) = v15;
        if ( (unsigned int)ChooseInformationTypes(
                             *(struct CInfoType **)(dwNewLong + 560),
                             (struct CSiteMap *)(dwNewLong + 32),
                             *(HWND *)(dwNewLong + 424),
                             *(struct CHtmlHelpControl **)(dwNewLong + 496)) )
        {
          v16 = *(CHHWinType **)(dwNewLong + 536);
          if ( v16 )
          {
            CHHWinType::UpdateInformationTypes(v16);
          }
          else
          {
            v17 = GetParent(*(HWND *)(dwNewLong + 424));
            RemovePropA(*(HWND *)(dwNewLong + 424), "HHDefProc");
            DestroyWindow(*(HWND *)(dwNewLong + 424));
            (*(void (__fastcall **)(LONG_PTR, HWND))(*(_QWORD *)dwNewLong + 8LL))(dwNewLong, v17);
            CToc::InitTreeView(dwNewLong);
          }
        }
      }
    }
    else
    {
      CHourGlass::CHourGlass((CHourGlass *)&hCursor);
      SendMessageA(*(HWND *)(dwNewLong + 424), 0xBu, 0, 0);
      memset(&lParam, 0, sizeof(lParam));
      v18 = (struct _TREEITEM *)SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Au, 0, 0);
      *(_QWORD *)(dwNewLong + 400) = v18;
      while ( 1 )
      {
        lParam.hItem = v18;
        if ( !v18 )
          break;
        lParam.mask = 102;
        W_TreeView_GetItem_fn(*(HWND *)(dwNewLong + 424), &lParam);
        v19 = lParam.lParam;
        if ( (*(unsigned int (__fastcall **)(LPARAM))(*(_QWORD *)lParam.lParam + 56LL))(lParam.lParam)
          && *(_BYTE *)(v19 + 8) )
        {
          *(_BYTE *)(v19 + 8) = 0;
          DeleteChildren(&lParam, *(HWND *)(dwNewLong + 424));
          SendMessageA(*(HWND *)(dwNewLong + 424), 0x1102u, 1u, (LPARAM)lParam.hItem);
          --lParam.iImage;
          --lParam.iSelectedImage;
          lParam.mask = 34;
          W_TreeView_SetItem_fn(*(HWND *)(dwNewLong + 424), (LPARAM)&lParam);
        }
        v18 = (struct _TREEITEM *)SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Au, 1u, (LPARAM)lParam.hItem);
      }
      v20 = *(_QWORD *)(dwNewLong + 400);
      if ( v20 )
      {
        *(_DWORD *)(dwNewLong + 408) = 1;
        SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Bu, 5u, v20);
        SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Bu, 9u, *(_QWORD *)(dwNewLong + 400));
        *(_DWORD *)(dwNewLong + 408) = 0;
      }
      *(_DWORD *)(dwNewLong + 512) = 0;
      SetCursor(hCursor);
      SendMessageA(*(HWND *)(dwNewLong + 424), 0xBu, 1u, 0);
    }
  }
  else
  {
    *(_QWORD *)(dwNewLong + 400) = SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Au, 9u, 0);
    memset(&lParam, 0, sizeof(lParam));
    v21 = 0;
    memset_0(v30, 0, 0x190u);
    lParam.hItem = (HTREEITEM)SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Au, 0, 0);
    CHourGlass::CHourGlass((CHourGlass *)&hCursor);
    if ( lParam.hItem )
    {
      while ( 1 )
      {
        lParam.mask = 102;
        W_TreeView_GetItem_fn(*(HWND *)(dwNewLong + 424), &lParam);
        v22 = lParam.lParam;
        if ( (*(unsigned int (__fastcall **)(LPARAM))(*(_QWORD *)lParam.lParam + 56LL))(lParam.lParam)
          && *(_BYTE *)(v22 + 8) != 1 )
        {
          *(_BYTE *)(v22 + 8) = 1;
          AddChildren(&lParam, *(HWND *)(dwNewLong + 424));
          SendMessageA(*(HWND *)(dwNewLong + 424), 0x1102u, 2u, (LPARAM)lParam.hItem);
          ++lParam.iImage;
          ++lParam.iSelectedImage;
          lParam.mask = 34;
          W_TreeView_SetItem_fn(*(HWND *)(dwNewLong + 424), (LPARAM)&lParam);
        }
        v23 = (struct _TREEITEM *)SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Au, 4u, (LPARAM)lParam.hItem);
        if ( !v23 )
          break;
        if ( (unsigned int)v21 < 0x32 )
        {
          v30[v21] = (LPARAM)lParam.hItem;
          v21 = (unsigned int)(v21 + 1);
        }
LABEL_49:
        lParam.hItem = v23;
      }
      for ( i = lParam.hItem; ; i = (HTREEITEM)v30[v21] )
      {
        v23 = (struct _TREEITEM *)SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Au, 1u, (LPARAM)i);
        if ( v23 )
          goto LABEL_49;
        v21 = (unsigned int)(v21 - 1);
        if ( (_DWORD)v21 == -1 )
          break;
      }
      lParam.hItem = 0;
    }
    v25 = *(_QWORD *)(dwNewLong + 400);
    if ( v25 )
    {
      *(_DWORD *)(dwNewLong + 408) = 1;
      SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Bu, 5u, v25);
      SendMessageA(*(HWND *)(dwNewLong + 424), 0x110Bu, 9u, *(_QWORD *)(dwNewLong + 400));
      *(_DWORD *)(dwNewLong + 408) = 0;
    }
    SetCursor(hCursor);
  }
  return 0;
}

```

## disassembly

```asm
0x18001a608  mov     [rsp-8+arg_8], rbx
0x18001a60d  mov     [rsp-8+arg_10], rdi
0x18001a612  push    rbp
0x18001a613  push    r13
0x18001a615  push    r14
0x18001a617  lea     rbp, [rsp-830h]
0x18001a61f  sub     rsp, 930h
0x18001a626  mov     rax, cs:__security_cookie
0x18001a62d  xor     rax, rsp
0x18001a630  mov     [rbp+840h+var_20], rax
0x18001a637  mov     rdi, rcx
0x18001a63a  sub     edx, 0FAh
0x18001a640  jz      loc_18001AAA6
0x18001a646  sub     edx, 1
0x18001a649  jz      loc_18001A90C
0x18001a64f  sub     edx, 1
0x18001a652  jz      loc_18001A85A
0x18001a658  sub     edx, 1
0x18001a65b  jz      loc_18001A7A5
0x18001a661  cmp     edx, 0EF02h
0x18001a667  jnz     loc_18001AC8E
0x18001a66d  mov     [rsp+940h+hCursor], 0
0x18001a676  mov     rcx, [rcx+1F0h]; this
0x18001a67d  test    rcx, rcx
0x18001a680  jz      short loc_18001A68E
0x18001a682  lea     rdx, [rsp+940h+hCursor]; struct CStr *
0x18001a687  call    ?GetCurrentUrl@CHtmlHelpControl@@QEAA_NAEAVCStr@@@Z; CHtmlHelpControl::GetCurrentUrl(CStr &)
0x18001a68c  jmp     short loc_18001A6CA
0x18001a68e  mov     r9d, 8; unsigned __int16
0x18001a694  lea     r8d, [r9-6]; unsigned __int16
0x18001a698  mov     rax, [rdi+218h]
0x18001a69f  mov     rcx, [rax+258h]
0x18001a6a6  mov     [rsp+940h+var_918], 0; unsigned __int8 *
0x18001a6af  lea     rax, [rsp+940h+hCursor]
0x18001a6b4  mov     [rsp+940h+pbc], rax; void *
0x18001a6b9  mov     edx, 0D3h; int
0x18001a6be  mov     rcx, [rcx+98h]; this
0x18001a6c5  call    ?InvokeHelper@COleDispatchDriver@@QEAAXJGGPEAXPEBEZZ; COleDispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x18001a6ca  mov     rbx, [rsp+940h+hCursor]
0x18001a6cf  mov     rcx, [rdi+1A8h]; hWnd
0x18001a6d6  call    cs:__imp_GetParent
0x18001a6dc  lea     r8, [rbp+840h+var_8B0]; char *
0x18001a6e0  mov     rdx, rbx; char *
0x18001a6e3  mov     rcx, rax; HWND
0x18001a6e6  call    ?doJumpUrl@@YAHPEAUHWND__@@PEBDPEAD_K@Z; doJumpUrl(HWND__ *,char const *,char *,unsigned __int64)
0x18001a6eb  test    eax, eax
0x18001a6ed  jz      short loc_18001A739
0x18001a6ef  cmp     qword ptr [rdi+1F0h], 0
0x18001a6f7  jz      loc_18001A787
0x18001a6fd  mov     [rsp+940h+szTarget], 0
0x18001a706  lea     rdx, [rbp+840h+var_8B0]
0x18001a70a  lea     rcx, [rsp+940h+szTarget]
0x18001a70f  call    ??4CWStr@@QEAAXPEBD@Z; CWStr::operator=(char const *)
0x18001a714  nop
0x18001a715  mov     rcx, [rdi+1F0h]; this
0x18001a71c  mov     r8, [rcx+8]; struct IUnknown *
0x18001a720  mov     rdx, [rsp+940h+szTarget]; unsigned __int16 *
0x18001a725  call    ?CheckDestUrlSafetyThruMoniker@CHtmlHelpControl@@QEAAJPEBGPEAUIUnknown@@@Z; CHtmlHelpControl::CheckDestUrlSafetyThruMoniker(ushort const *,IUnknown *)
0x18001a72a  test    eax, eax
0x18001a72c  jz      short loc_18001A748
0x18001a72e  lea     rcx, [rsp+940h+szTarget]; this
0x18001a733  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18001a738  nop
0x18001a739  lea     rcx, [rsp+940h+hCursor]; this
0x18001a73e  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18001a743  jmp     loc_18001AC8E
0x18001a748  mov     r9, [rdi+1F0h]
0x18001a74f  mov     [rsp+940h+dwReserved], 0; dwReserved
0x18001a757  mov     [rsp+940h+grfHLNF], 0; grfHLNF
0x18001a75f  mov     [rsp+940h+var_918], 0; IBindStatusCallback *
0x18001a768  mov     [rsp+940h+pbc], 0; pbc
0x18001a771  mov     r9, [r9+8]; pUnk
0x18001a775  xor     r8d, r8d; szTargetFrameName
0x18001a778  xor     edx, edx; szLocation
0x18001a77a  mov     rcx, [rsp+940h+szTarget]; szTarget
0x18001a77f  call    cs:__imp_HlinkSimpleNavigateToString
0x18001a785  jmp     short loc_18001A72E
0x18001a787  mov     rcx, [rdi+1A8h]; hWnd
0x18001a78e  call    cs:__imp_GetParent
0x18001a794  mov     rdx, rax; hWnd
0x18001a797  xor     r8d, r8d; int
0x18001a79a  lea     rcx, [rbp+840h+var_8B0]; char *
0x18001a79e  call    ?ChangeHtmlTopic@@YAPEAUHWND__@@PEBDPEAU1@H@Z; ChangeHtmlTopic(char const *,HWND__ *,int)
0x18001a7a3  jmp     short loc_18001A739
0x18001a7a5  xor     r9d, r9d; lParam
0x18001a7a8  mov     edx, 110Ah; Msg
0x18001a7ad  lea     r8d, [r9+9]; wParam
0x18001a7b1  mov     rcx, [rcx+1A8h]; hWnd
0x18001a7b8  call    cs:__imp_SendMessageA
0x18001a7be  test    rax, rax
0x18001a7c1  jz      loc_18001AC8E
0x18001a7c7  mov     rcx, [rdi+218h]; this
0x18001a7ce  test    rcx, rcx
0x18001a7d1  jz      short loc_18001A7F6
0x18001a7d3  mov     edx, 0Eh; int
0x18001a7d8  call    ?OnTrackNotifyCaller@CHHWinType@@QEAAHH@Z; CHHWinType::OnTrackNotifyCaller(int)
0x18001a7dd  test    eax, eax
0x18001a7df  jnz     loc_18001AC8E
0x18001a7e5  mov     rcx, [rdi+218h]; this
0x18001a7ec  call    ?OnPrint@CHHWinType@@QEAAXXZ; CHHWinType::OnPrint(void)
0x18001a7f1  jmp     loc_18001AC8E
0x18001a7f6  mov     rcx, [rdi+1A8h]; hWnd
0x18001a7fd  call    cs:__imp_GetParent
0x18001a803  mov     rdx, rax; HWND
0x18001a806  lea     rcx, [rbp+840h+var_8B0]; this
0x18001a80a  call    ??0CPrint@@QEAA@PEAUHWND__@@@Z; CPrint::CPrint(HWND__ *)
0x18001a80f  nop
0x18001a810  mov     ebx, 1
0x18001a815  mov     [rbp+840h+var_28], ebx
0x18001a81b  lea     rcx, [rbp+840h+var_8B0]; this
0x18001a81f  call    ?DoModal@CDlg@@QEAAHXZ; CDlg::DoModal(void)
0x18001a824  test    eax, eax
0x18001a826  jz      short loc_18001A84C
0x18001a828  mov     r8, [rdi+1F0h]
0x18001a82f  mov     r9, [r8+1C0h]; HWND
0x18001a836  mov     r8, [r8+1F0h]; this
0x18001a83d  mov     rdx, rdi; struct CToc *
0x18001a840  mov     ecx, [rbp+840h+var_28]; int
0x18001a846  call    ?PrintTopics@@YAXHPEAVCToc@@PEAVIWebBrowserAppImpl@@PEAUHWND__@@@Z; PrintTopics(int,CToc *,IWebBrowserAppImpl *,HWND__ *)
0x18001a84b  nop
0x18001a84c  lea     rcx, [rbp+840h+var_8B0]; this
0x18001a850  call    ??1CDlg@@QEAA@XZ; CDlg::~CDlg(void)
0x18001a855  jmp     loc_18001AC8E
0x18001a85a  mov     rax, [rcx+218h]
0x18001a861  mov     rcx, [rax+260h]
0x18001a868  mov     rax, [rcx+80h]
0x18001a86f  mov     rcx, [rax+28h]
0x18001a873  mov     rax, [rcx+58h]
0x18001a877  test    rax, rax
0x18001a87a  jz      short loc_18001A880
0x18001a87c  mov     [rcx+78h], rax
0x18001a880  lea     rdx, [rdi+20h]; struct CSiteMap *
0x18001a884  mov     r9, [rdi+1F0h]; struct CHtmlHelpControl *
0x18001a88b  mov     r8, [rdi+1A8h]; HWND
0x18001a892  mov     rcx, [rdi+230h]; struct CInfoType *
0x18001a899  call    ?ChooseInformationTypes@@YAHPEAVCInfoType@@PEAVCSiteMap@@PEAUHWND__@@PEAVCHtmlHelpControl@@@Z; ChooseInformationTypes(CInfoType *,CSiteMap *,HWND__ *,CHtmlHelpControl *)
0x18001a89e  test    eax, eax
0x18001a8a0  jz      loc_18001AC8E
0x18001a8a6  mov     rcx, [rdi+218h]; this
0x18001a8ad  test    rcx, rcx
0x18001a8b0  jz      short loc_18001A8BC
0x18001a8b2  call    ?UpdateInformationTypes@CHHWinType@@QEAAXXZ; CHHWinType::UpdateInformationTypes(void)
0x18001a8b7  jmp     loc_18001AC8E
0x18001a8bc  mov     rcx, [rdi+1A8h]; hWnd
0x18001a8c3  call    cs:__imp_GetParent
0x18001a8c9  mov     rbx, rax
0x18001a8cc  lea     rdx, aHhdefproc; "HHDefProc"
0x18001a8d3  mov     rcx, [rdi+1A8h]; hWnd
0x18001a8da  call    cs:__imp_RemovePropA
0x18001a8e0  mov     rcx, [rdi+1A8h]; hWnd
0x18001a8e7  call    cs:__imp_DestroyWindow
0x18001a8ed  mov     rcx, [rdi]
0x18001a8f0  mov     rax, [rcx+8]
0x18001a8f4  mov     rdx, rbx
0x18001a8f7  mov     rcx, rdi
0x18001a8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8ff  mov     rcx, rdi; dwNewLong
0x18001a902  call    ?InitTreeView@CToc@@QEAAHXZ; CToc::InitTreeView(void)
0x18001a907  jmp     loc_18001AC8E
0x18001a90c  lea     rcx, [rsp+940h+hCursor]; this
0x18001a911  call    ??0CHourGlass@@QEAA@XZ; CHourGlass::CHourGlass(void)
0x18001a916  nop
0x18001a917  xor     r9d, r9d; lParam
0x18001a91a  xor     r8d, r8d; wParam
0x18001a91d  lea     r13d, [r9+0Bh]
0x18001a921  mov     edx, r13d; Msg
0x18001a924  mov     rcx, [rdi+1A8h]; hWnd
0x18001a92b  call    cs:__imp_SendMessageA
0x18001a931  xorps   xmm0, xmm0
0x18001a934  xor     eax, eax
0x18001a936  movups  xmmword ptr [rsp+940h+lParam], xmm0
0x18001a93b  movups  [rsp+940h+var_8E0], xmm0
0x18001a940  movups  [rsp+940h+var_8D0], xmm0
0x18001a945  mov     [rbp+840h+var_8C0], rax
0x18001a949  xor     r9d, r9d; lParam
0x18001a94c  xor     r8d, r8d; wParam
0x18001a94f  mov     edx, 110Ah; Msg
0x18001a954  mov     rcx, [rdi+1A8h]; hWnd
0x18001a95b  call    cs:__imp_SendMessageA
0x18001a961  mov     [rdi+190h], rax
0x18001a968  lea     ebx, [r13-0Ah]
0x18001a96c  jmp     loc_18001AA13
0x18001a971  mov     dword ptr [rsp+940h+lParam], 66h ; 'f'
0x18001a979  lea     rdx, [rsp+940h+lParam]; struct tagTVITEMW *
0x18001a97e  mov     rcx, [rdi+1A8h]; HWND
0x18001a985  call    ?W_TreeView_GetItem_fn@@YAHPEAUHWND__@@PEAUtagTVITEMW@@@Z; W_TreeView_GetItem_fn(HWND__ *,tagTVITEMW *)
0x18001a98a  mov     r14, [rbp+840h+var_8C0]
0x18001a98e  mov     rax, [r14]
0x18001a991  mov     rcx, r14
0x18001a994  mov     rax, [rax+38h]
0x18001a998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a99d  test    eax, eax
0x18001a99f  jz      short loc_18001A9F9
0x18001a9a1  cmp     byte ptr [r14+8], 0
0x18001a9a6  jz      short loc_18001A9F9
0x18001a9a8  mov     byte ptr [r14+8], 0
0x18001a9ad  mov     rdx, [rdi+1A8h]; HWND
0x18001a9b4  lea     rcx, [rsp+940h+lParam]; struct tagTVITEMW *
0x18001a9b9  call    ?DeleteChildren@@YAXPEAUtagTVITEMW@@PEAUHWND__@@@Z; DeleteChildren(tagTVITEMW *,HWND__ *)
0x18001a9be  mov     r9, [rsp+940h+lParam+8]; lParam
0x18001a9c3  mov     r8, rbx; wParam
0x18001a9c6  mov     edx, 1102h; Msg
0x18001a9cb  mov     rcx, [rdi+1A8h]; hWnd
0x18001a9d2  call    cs:__imp_SendMessageA
0x18001a9d8  sub     dword ptr [rsp+940h+var_8D0+4], ebx
0x18001a9dc  sub     dword ptr [rsp+940h+var_8D0+8], ebx
0x18001a9e0  mov     dword ptr [rsp+940h+lParam], 22h ; '"'
0x18001a9e8  lea     rdx, [rsp+940h+lParam]; lParam
0x18001a9ed  mov     rcx, [rdi+1A8h]; hWnd
0x18001a9f4  call    ?W_TreeView_SetItem_fn@@YAHPEAUHWND__@@PEAUtagTVITEMW@@@Z; W_TreeView_SetItem_fn(HWND__ *,tagTVITEMW *)
0x18001a9f9  mov     r9, [rsp+940h+lParam+8]; lParam
0x18001a9fe  mov     r8, rbx; wParam
0x18001aa01  mov     edx, 110Ah; Msg
0x18001aa06  mov     rcx, [rdi+1A8h]; hWnd
0x18001aa0d  call    cs:__imp_SendMessageA
0x18001aa13  test    rax, rax
0x18001aa16  mov     [rsp+940h+lParam+8], rax
0x18001aa1b  jnz     loc_18001A971
0x18001aa21  mov     r9, [rdi+190h]; lParam
0x18001aa28  test    r9, r9
0x18001aa2b  jz      short loc_18001AA76
0x18001aa2d  mov     [rdi+198h], ebx
0x18001aa33  mov     r8d, 5; wParam
0x18001aa39  mov     r14d, 110Bh
0x18001aa3f  mov     edx, r14d; Msg
0x18001aa42  mov     rcx, [rdi+1A8h]; hWnd
0x18001aa49  call    cs:__imp_SendMessageA
0x18001aa4f  mov     r9, [rdi+190h]; lParam
0x18001aa56  mov     r8d, 9; wParam
0x18001aa5c  mov     edx, r14d; Msg
0x18001aa5f  mov     rcx, [rdi+1A8h]; hWnd
0x18001aa66  call    cs:__imp_SendMessageA
0x18001aa6c  mov     dword ptr [rdi+198h], 0
0x18001aa76  mov     dword ptr [rdi+200h], 0
0x18001aa80  mov     rcx, [rsp+940h+hCursor]; hCursor
0x18001aa85  call    cs:__imp_SetCursor
0x18001aa8b  xor     r9d, r9d; lParam
0x18001aa8e  mov     r8, rbx; wParam
0x18001aa91  mov     edx, r13d; Msg
0x18001aa94  mov     rcx, [rdi+1A8h]; hWnd
0x18001aa9b  call    cs:__imp_SendMessageA
0x18001aaa1  jmp     loc_18001AC8E
0x18001aaa6  xor     r9d, r9d; lParam
0x18001aaa9  mov     edx, 110Ah; Msg
0x18001aaae  lea     r8d, [r9+9]; wParam
0x18001aab2  mov     rcx, [rcx+1A8h]; hWnd
0x18001aab9  call    cs:__imp_SendMessageA
0x18001aabf  mov     [rdi+190h], rax
0x18001aac6  xorps   xmm0, xmm0
0x18001aac9  xor     eax, eax
0x18001aacb  movups  xmmword ptr [rsp+940h+lParam], xmm0
0x18001aad0  movups  [rsp+940h+var_8E0], xmm0
0x18001aad5  movups  [rsp+940h+var_8D0], xmm0
0x18001aada  mov     [rbp+840h+var_8C0], rax
0x18001aade  xor     r14d, r14d
0x18001aae1  xor     edx, edx; Val
0x18001aae3  mov     r8d, 190h; Size
0x18001aae9  lea     rcx, [rbp+840h+var_8B0]; void *
0x18001aaed  call    memset_0
0x18001aaf2  xor     r9d, r9d; lParam
0x18001aaf5  xor     r8d, r8d; wParam
0x18001aaf8  mov     edx, 110Ah; Msg
0x18001aafd  mov     rcx, [rdi+1A8h]; hWnd
0x18001ab04  call    cs:__imp_SendMessageA
0x18001ab0a  mov     [rsp+940h+lParam+8], rax
0x18001ab0f  lea     rcx, [rsp+940h+hCursor]; this
0x18001ab14  call    ??0CHourGlass@@QEAA@XZ; CHourGlass::CHourGlass(void)
0x18001ab19  nop
0x18001ab1a  lea     ebx, [r14+1]
0x18001ab1e  cmp     [rsp+940h+lParam+8], r14
0x18001ab23  jz      loc_18001AC2E
0x18001ab29  mov     dword ptr [rsp+940h+lParam], 66h ; 'f'
0x18001ab31  lea     rdx, [rsp+940h+lParam]; struct tagTVITEMW *
0x18001ab36  mov     rcx, [rdi+1A8h]; HWND
0x18001ab3d  call    ?W_TreeView_GetItem_fn@@YAHPEAUHWND__@@PEAUtagTVITEMW@@@Z; W_TreeView_GetItem_fn(HWND__ *,tagTVITEMW *)
0x18001ab42  mov     r13, [rbp+840h+var_8C0]
0x18001ab46  mov     rax, [r13+0]
0x18001ab4a  mov     rcx, r13
0x18001ab4d  mov     rax, [rax+38h]
0x18001ab51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab56  test    eax, eax
0x18001ab58  jz      short loc_18001ABB3
0x18001ab5a  cmp     [r13+8], bl
0x18001ab5e  jz      short loc_18001ABB3
0x18001ab60  mov     [r13+8], bl
0x18001ab64  mov     rdx, [rdi+1A8h]; HWND
0x18001ab6b  lea     rcx, [rsp+940h+lParam]; struct tagTVITEMW *
0x18001ab70  call    ?AddChildren@@YAXPEAUtagTVITEMW@@PEAUHWND__@@@Z; AddChildren(tagTVITEMW *,HWND__ *)
0x18001ab75  mov     r9, [rsp+940h+lParam+8]; lParam
0x18001ab7a  mov     edx, 1102h; Msg
0x18001ab7f  mov     r8d, 2; wParam
0x18001ab85  mov     rcx, [rdi+1A8h]; hWnd
0x18001ab8c  call    cs:__imp_SendMessageA
0x18001ab92  add     dword ptr [rsp+940h+var_8D0+4], ebx
0x18001ab96  add     dword ptr [rsp+940h+var_8D0+8], ebx
0x18001ab9a  mov     dword ptr [rsp+940h+lParam], 22h ; '"'
0x18001aba2  lea     rdx, [rsp+940h+lParam]; lParam
0x18001aba7  mov     rcx, [rdi+1A8h]; hWnd
0x18001abae  call    ?W_TreeView_SetItem_fn@@YAHPEAUHWND__@@PEAUtagTVITEMW@@@Z; W_TreeView_SetItem_fn(HWND__ *,tagTVITEMW *)
0x18001abb3  mov     r9, [rsp+940h+lParam+8]; lParam
  ... truncated ...
```
