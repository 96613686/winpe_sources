# InitDevTreeDlgProc(HWND__ *,_DeviceTreeData *)

- ea: `0x180004114`
- end: `0x180004429`
- name: `?InitDevTreeDlgProc@@YAHPEAUHWND__@@PEAU_DeviceTreeData@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(HWND hWnd, struct _DeviceTreeData *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180003d70`

## callees

- `0x1800039b8`
- `0x180004114`
- `0x1800045a8`
- `0x180005b2c`
- `0x180006078`
- `0x180006514`
- `0x18000873a`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000422b`
- `KERNEL32!GetProcAddress` at `0x18000422b`
- `KERNEL32!LoadLibraryW` at `0x18000420f`
- `KERNEL32!LoadLibraryW` at `0x18000420f`
- `USER32!RegisterClassW` at `0x1800041ab`
- `USER32!RegisterClassW` at `0x1800041ab`
- `USER32!GetClassInfoW` at `0x180004166`
- `USER32!GetClassInfoW` at `0x180004166`
- `USER32!ShowWindow` at `0x180004400`
- `USER32!ShowWindow` at `0x180004400`
- `USER32!CreateWindowExW` at `0x1800041fb`
- `USER32!CreateWindowExW` at `0x1800041fb`
- `USER32!PostMessageW` at `0x1800043f0`
- `USER32!PostMessageW` at `0x1800043f0`
- `USER32!LoadIconW` at `0x180004244`
- `USER32!LoadIconW` at `0x180004244`
- `USER32!SendMessageW` at `0x18000425e`
- `USER32!SendMessageW` at `0x180004270`
- `USER32!SendMessageW` at `0x180004293`
- `USER32!SendMessageW` at `0x1800042a5`
- `USER32!SendMessageW` at `0x180004333`
- `USER32!SendMessageW` at `0x1800043dc`
- `USER32!SendMessageW` at `0x18000425e`
- `USER32!SendMessageW` at `0x180004270`
- `USER32!SendMessageW` at `0x180004293`
- `USER32!SendMessageW` at `0x1800042a5`
- `USER32!SendMessageW` at `0x180004333`
- `USER32!SendMessageW` at `0x1800043dc`
- `USER32!GetDlgItem` at `0x1800042b7`
- `USER32!GetDlgItem` at `0x1800042ec`
- `USER32!GetDlgItem` at `0x180004306`
- `USER32!GetDlgItem` at `0x1800042b7`
- `USER32!GetDlgItem` at `0x1800042ec`
- `USER32!GetDlgItem` at `0x180004306`
- `USER32!CheckDlgButton` at `0x180004364`
- `USER32!CheckDlgButton` at `0x180004364`
- `USER32!GetParent` at `0x180004279`
- `USER32!GetParent` at `0x180004279`
- `USER32!EnableWindow` at `0x1800042f7`
- `USER32!EnableWindow` at `0x180004311`
- `USER32!EnableWindow` at `0x1800042f7`
- `USER32!EnableWindow` at `0x180004311`
- `USER32!LoadStringW` at `0x1800042dd`
- `USER32!LoadStringW` at `0x1800042dd`
- `CFGMGR32!CM_Locate_DevNode_ExW` at `0x180004376`
- `CFGMGR32!CM_Locate_DevNode_ExW` at `0x1800043ab`
- `CFGMGR32!CM_Locate_DevNode_ExW` at `0x180004376`
- `CFGMGR32!CM_Locate_DevNode_ExW` at `0x1800043ab`

## string_xrefs

- `0x180004208`: `devmgr.dll`

## pseudocode

```c
__int64 __fastcall InitDevTreeDlgProc(HWND hWnd, struct _DeviceTreeData *a2)
{
  HMODULE LibraryW; // rax
  HICON IconW; // rax
  LPARAM v6; // rsi
  HWND Parent; // rax
  HWND v8; // rbp
  HWND DlgItem; // rax
  HINSTANCE v10; // rcx
  HWND v11; // rsi
  HWND v12; // rax
  HWND v13; // rax
  struct _IMAGELIST *DeviceImageList; // rax
  HWND v15; // rcx
  UINT v16; // r8d
  WCHAR *v17; // rdx
  struct _DeviceTreeNode *v18; // rax
  tagWNDCLASSW WndClass; // [rsp+60h] [rbp-78h] BYREF
  DEVNODE pdnDevInst; // [rsp+E0h] [rbp+8h] BYREF

  *((_BYTE *)a2 + 98) = 1;
  memset_0(&WndClass, 0, sizeof(WndClass));
  if ( GetClassInfoW(hHotPlug, HOTPLUG_NOTIFY_CLASS_NAME, &WndClass)
    || (memset_0(&WndClass, 0, sizeof(WndClass)),
        WndClass.lpszClassName = HOTPLUG_NOTIFY_CLASS_NAME,
        WndClass.lpfnWndProc = (WNDPROC)hotplugNotifyWndProc,
        WndClass.hInstance = hHotPlug,
        RegisterClassW(&WndClass)) )
  {
    g_hwndNotify = CreateWindowExW(
                     0x80u,
                     HOTPLUG_NOTIFY_CLASS_NAME,
                     &String,
                     0x8C00000u,
                     0x80000000,
                     0x80000000,
                     0,
                     0,
                     0,
                     0,
                     hHotPlug,
                     hWnd);
  }
  LibraryW = LoadLibraryW(L"devmgr.dll");
  hDevMgr = LibraryW;
  if ( LibraryW )
    pDeviceProperties = (int (*)(HWND, unsigned __int16 *, unsigned __int16 *, int))GetProcAddress(
                                                                                      LibraryW,
                                                                                      "DevicePropertiesW");
  IconW = LoadIconW(hHotPlug, (LPCWSTR)0x64);
  v6 = (LPARAM)IconW;
  if ( IconW )
  {
    SendMessageW(hWnd, 0x80u, 0, (LPARAM)IconW);
    SendMessageW(hWnd, 0x80u, 1u, v6);
  }
  Parent = GetParent(hWnd);
  v8 = Parent;
  if ( Parent )
  {
    SendMessageW(Parent, 0x80u, 0, v6);
    SendMessageW(v8, 0x80u, 1u, v6);
  }
  *((_QWORD *)a2 + 2) = hWnd;
  DlgItem = GetDlgItem(hWnd, 301);
  v10 = hHotPlug;
  *((_QWORD *)a2 + 1) = DlgItem;
  v11 = DlgItem;
  LoadStringW(v10, 0x3EBu, &szUnknown, 64);
  v12 = GetDlgItem(*((HWND *)a2 + 2), 305);
  EnableWindow(v12, 0);
  v13 = GetDlgItem(*((HWND *)a2 + 2), 311);
  EnableWindow(v13, 0);
  DeviceImageList = CreateDeviceImageList();
  *((_QWORD *)a2 + 11) = DeviceImageList;
  if ( DeviceImageList )
    SendMessageW(v11, 0x1109u, 0, (LPARAM)DeviceImageList);
  OnSysColorChange(v15, a2);
  if ( (GetHotPlugFlags(0) & 2) != 0 )
  {
    *((_BYTE *)a2 + 96) = 1;
    v16 = 1;
  }
  else
  {
    *((_BYTE *)a2 + 96) = 0;
    v16 = 0;
  }
  CheckDlgButton(hWnd, 307, v16);
  if ( !CM_Locate_DevNode_ExW((PDEVINST)a2 + 18, 0, 0, 0) )
  {
    RefreshTree(a2);
    v17 = (WCHAR *)*((_QWORD *)a2 + 10);
    if ( !v17 )
    {
      ShowWindow(hWnd, 5);
      return 1;
    }
    pdnDevInst = 0;
    if ( !CM_Locate_DevNode_ExW(&pdnDevInst, v17, 0, 0) )
    {
      v18 = DevTreeNodeByDevNode(pdnDevInst, (struct _LIST_ENTRY *)((char *)a2 + 56));
      if ( v18 )
      {
        SendMessageW(v11, 0x110Bu, 9u, *((_QWORD *)v18 + 11));
        PostMessageW(hWnd, 0x517u, 0, 0);
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004114  mov     [rsp+arg_8], rbx
0x180004119  mov     [rsp+arg_10], rbp
0x18000411e  push    rsi
0x18000411f  push    rdi
0x180004120  push    r12
0x180004122  push    r14
0x180004124  push    r15
0x180004126  sub     rsp, 0B0h
0x18000412d  mov     r15d, 1
0x180004133  mov     rbx, rdx
0x180004136  mov     rdi, rcx
0x180004139  mov     [rdx+62h], r15b
0x18000413d  xor     edx, edx; Val
0x18000413f  lea     rcx, [rsp+0D8h+WndClass]; void *
0x180004144  lea     ebp, [r15+47h]
0x180004148  mov     r8d, ebp; Size
0x18000414b  call    memset_0
0x180004150  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x180004157  lea     rsi, ?HOTPLUG_NOTIFY_CLASS_NAME@@3PAGA; "HotPlugNotifyClass"
0x18000415e  mov     rdx, rsi; lpClassName
0x180004161  lea     r8, [rsp+0D8h+WndClass]; lpWndClass
0x180004166  call    cs:__imp_GetClassInfoW
0x18000416c  xor     r14d, r14d
0x18000416f  lea     r12d, [r15+7Fh]
0x180004173  test    eax, eax
0x180004175  jnz     short loc_1800041B6
0x180004177  mov     r8d, ebp; Size
0x18000417a  lea     rcx, [rsp+0D8h+WndClass]; void *
0x18000417f  xor     edx, edx; Val
0x180004181  call    memset_0
0x180004186  lea     rax, ?hotplugNotifyWndProc@@YA_JPEAUHWND__@@I_K_J@Z; hotplugNotifyWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000418d  mov     [rsp+0D8h+WndClass.lpszClassName], rsi
0x180004195  mov     [rsp+0D8h+WndClass.lpfnWndProc], rax
0x18000419a  lea     rcx, [rsp+0D8h+WndClass]; lpWndClass
0x18000419f  mov     rax, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hHotPlug
0x1800041a6  mov     [rsp+0D8h+WndClass.hInstance], rax
0x1800041ab  call    cs:__imp_RegisterClassW
0x1800041b1  test    ax, ax
0x1800041b4  jz      short loc_180004208
0x1800041b6  mov     rax, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hHotPlug
0x1800041bd  lea     r8, String; lpWindowName
0x1800041c4  mov     [rsp+0D8h+lpParam], rdi; lpParam
0x1800041c9  mov     r9d, 8C00000h; dwStyle
0x1800041cf  mov     [rsp+0D8h+hInstance], rax; hInstance
0x1800041d4  mov     rdx, rsi; lpClassName
0x1800041d7  mov     [rsp+0D8h+hMenu], r14; hMenu
0x1800041dc  mov     eax, 80000000h
0x1800041e1  mov     [rsp+0D8h+hWndParent], r14; hWndParent
0x1800041e6  mov     ecx, r12d; dwExStyle
0x1800041e9  mov     [rsp+0D8h+nHeight], r14d; nHeight
0x1800041ee  mov     [rsp+0D8h+nWidth], r14d; nWidth
0x1800041f3  mov     [rsp+0D8h+Y], eax; Y
0x1800041f7  mov     [rsp+0D8h+X], eax; X
0x1800041fb  call    cs:__imp_CreateWindowExW
0x180004201  mov     cs:?g_hwndNotify@@3PEAUHWND__@@EA, rax; HWND__ * g_hwndNotify
0x180004208  lea     rcx, LibFileName; "devmgr.dll"
0x18000420f  call    cs:__imp_LoadLibraryW
0x180004215  mov     cs:?hDevMgr@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * hDevMgr
0x18000421c  test    rax, rax
0x18000421f  jz      short loc_180004238
0x180004221  lea     rdx, ProcName; "DevicePropertiesW"
0x180004228  mov     rcx, rax; hModule
0x18000422b  call    cs:__imp_GetProcAddress
0x180004231  mov     cs:?pDeviceProperties@@3P6AHPEAUHWND__@@PEAG1H@ZEA, rax; int (*pDeviceProperties)(HWND__ *,ushort *,ushort *,int)
0x180004238  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x18000423f  mov     edx, 64h ; 'd'; lpIconName
0x180004244  call    cs:__imp_LoadIconW
0x18000424a  mov     rsi, rax
0x18000424d  test    rax, rax
0x180004250  jz      short loc_180004276
0x180004252  mov     r9, rax; lParam
0x180004255  xor     r8d, r8d; wParam
0x180004258  mov     edx, r12d; Msg
0x18000425b  mov     rcx, rdi; hWnd
0x18000425e  call    cs:__imp_SendMessageW
0x180004264  mov     r9, rsi; lParam
0x180004267  mov     r8, r15; wParam
0x18000426a  mov     edx, r12d; Msg
0x18000426d  mov     rcx, rdi; hWnd
0x180004270  call    cs:__imp_SendMessageW
0x180004276  mov     rcx, rdi; hWnd
0x180004279  call    cs:__imp_GetParent
0x18000427f  mov     rbp, rax
0x180004282  test    rax, rax
0x180004285  jz      short loc_1800042AB
0x180004287  mov     r9, rsi; lParam
0x18000428a  xor     r8d, r8d; wParam
0x18000428d  mov     edx, r12d; Msg
0x180004290  mov     rcx, rax; hWnd
0x180004293  call    cs:__imp_SendMessageW
0x180004299  mov     r9, rsi; lParam
0x18000429c  mov     r8, r15; wParam
0x18000429f  mov     edx, r12d; Msg
0x1800042a2  mov     rcx, rbp; hWnd
0x1800042a5  call    cs:__imp_SendMessageW
0x1800042ab  mov     edx, 12Dh; nIDDlgItem
0x1800042b0  mov     [rbx+10h], rdi
0x1800042b4  mov     rcx, rdi; hDlg
0x1800042b7  call    cs:__imp_GetDlgItem
0x1800042bd  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x1800042c4  lea     r8, ?szUnknown@@3PAGA; lpBuffer
0x1800042cb  mov     r9d, 40h ; '@'; cchBufferMax
0x1800042d1  mov     [rbx+8], rax
0x1800042d5  mov     edx, 3EBh; uID
0x1800042da  mov     rsi, rax
0x1800042dd  call    cs:__imp_LoadStringW
0x1800042e3  mov     rcx, [rbx+10h]; hDlg
0x1800042e7  mov     edx, 131h; nIDDlgItem
0x1800042ec  call    cs:__imp_GetDlgItem
0x1800042f2  mov     rcx, rax; hWnd
0x1800042f5  xor     edx, edx; bEnable
0x1800042f7  call    cs:__imp_EnableWindow
0x1800042fd  mov     rcx, [rbx+10h]; hDlg
0x180004301  mov     edx, 137h; nIDDlgItem
0x180004306  call    cs:__imp_GetDlgItem
0x18000430c  mov     rcx, rax; hWnd
0x18000430f  xor     edx, edx; bEnable
0x180004311  call    cs:__imp_EnableWindow
0x180004317  call    ?CreateDeviceImageList@@YAPEAU_IMAGELIST@@XZ; CreateDeviceImageList(void)
0x18000431c  mov     [rbx+58h], rax
0x180004320  test    rax, rax
0x180004323  jz      short loc_180004339
0x180004325  mov     r9, rax; lParam
0x180004328  xor     r8d, r8d; wParam
0x18000432b  mov     edx, 1109h; Msg
0x180004330  mov     rcx, rsi; hWnd
0x180004333  call    cs:__imp_SendMessageW
0x180004339  mov     rdx, rbx; struct _DeviceTreeData *
0x18000433c  call    ?OnSysColorChange@@YAXPEAUHWND__@@PEAU_DeviceTreeData@@@Z; OnSysColorChange(HWND__ *,_DeviceTreeData *)
0x180004341  xor     ecx, ecx; HKEY *
0x180004343  call    ?GetHotPlugFlags@@YAKPEAPEAUHKEY__@@@Z; GetHotPlugFlags(HKEY__ * *)
0x180004348  mov     edx, 133h; nIDButton
0x18000434d  mov     rcx, rdi; hDlg
0x180004350  test    al, 2
0x180004352  jz      short loc_18000435D
0x180004354  mov     [rbx+60h], r15b
0x180004358  mov     r8d, r15d
0x18000435b  jmp     short loc_180004364
0x18000435d  mov     [rbx+60h], r14b
0x180004361  xor     r8d, r8d; uCheck
0x180004364  call    cs:__imp_CheckDlgButton
0x18000436a  lea     rcx, [rbx+48h]; pdnDevInst
0x18000436e  xor     r9d, r9d; hMachine
0x180004371  xor     r8d, r8d; ulFlags
0x180004374  xor     edx, edx; pDeviceID
0x180004376  call    cs:__imp_CM_Locate_DevNode_ExW
0x18000437c  test    eax, eax
0x18000437e  jnz     loc_18000440B
0x180004384  mov     rcx, rbx; struct _DeviceTreeData *
0x180004387  call    ?RefreshTree@@YAHPEAU_DeviceTreeData@@@Z; RefreshTree(_DeviceTreeData *)
0x18000438c  mov     rdx, [rbx+50h]; pDeviceID
0x180004390  test    rdx, rdx
0x180004393  jz      short loc_1800043F8
0x180004395  xor     r9d, r9d; hMachine
0x180004398  mov     [rsp+0D8h+pdnDevInst], r14d
0x1800043a0  xor     r8d, r8d; ulFlags
0x1800043a3  lea     rcx, [rsp+0D8h+pdnDevInst]; pdnDevInst
0x1800043ab  call    cs:__imp_CM_Locate_DevNode_ExW
0x1800043b1  test    eax, eax
0x1800043b3  jnz     short loc_18000440B
0x1800043b5  mov     ecx, [rsp+0D8h+pdnDevInst]; unsigned int
0x1800043bc  lea     rdx, [rbx+38h]; struct _LIST_ENTRY *
0x1800043c0  call    ?DevTreeNodeByDevNode@@YAPEAU_DeviceTreeNode@@KPEAU_LIST_ENTRY@@@Z; DevTreeNodeByDevNode(ulong,_LIST_ENTRY *)
0x1800043c5  test    rax, rax
0x1800043c8  jz      short loc_18000440B
0x1800043ca  mov     r9, [rax+58h]; lParam
0x1800043ce  mov     edx, 110Bh; Msg
0x1800043d3  mov     r8d, 9; wParam
0x1800043d9  mov     rcx, rsi; hWnd
0x1800043dc  call    cs:__imp_SendMessageW
0x1800043e2  xor     r9d, r9d; lParam
0x1800043e5  xor     r8d, r8d; wParam
0x1800043e8  mov     edx, 517h; Msg
0x1800043ed  mov     rcx, rdi; hWnd
0x1800043f0  call    cs:__imp_PostMessageW
0x1800043f6  jmp     short loc_180004406
0x1800043f8  mov     edx, 5; nCmdShow
0x1800043fd  mov     rcx, rdi; hWnd
0x180004400  call    cs:__imp_ShowWindow
0x180004406  mov     eax, r15d
0x180004409  jmp     short loc_18000440D
0x18000440b  xor     eax, eax
0x18000440d  lea     r11, [rsp+0D8h+var_28]
0x180004415  mov     rbx, [r11+38h]
0x180004419  mov     rbp, [r11+40h]
0x18000441d  mov     rsp, r11
0x180004420  pop     r15
0x180004422  pop     r14
0x180004424  pop     r12
0x180004426  pop     rdi
0x180004427  pop     rsi
0x180004428  retn
```
