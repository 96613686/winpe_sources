# IntroPage::SetupPackageList(void)

- ea: `0x140018f6c`
- end: `0x14001961e`
- name: `?SetupPackageList@IntroPage@@IEAAJXZ`
- size: `1714`
- prototype: `__int64 __fastcall(IntroPage *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140015580`
- `0x140017c80`

## callees

- `0x1400039b1`
- `0x14000e6bc`
- `0x14000e72c`
- `0x140015490`
- `0x140018f6c`
- `0x140020420`
- `0x140041c54`
- `0x140041e30`
- `0x140049770`
- `0x14004ce74`
- `0x14004cf10`
- `0x14004cfe4`
- `0x14004d148`
- `0x140061c90`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140019122`
- `KERNEL32!GetLastError` at `0x14001933c`
- `KERNEL32!GetLastError` at `0x140019372`
- `KERNEL32!GetLastError` at `0x1400195d8`
- `KERNEL32!GetLastError` at `0x1400195fb`
- `KERNEL32!GetLastError` at `0x140019122`
- `KERNEL32!GetLastError` at `0x14001933c`
- `KERNEL32!GetLastError` at `0x140019372`
- `KERNEL32!GetLastError` at `0x1400195d8`
- `KERNEL32!GetLastError` at `0x1400195fb`
- `KERNEL32!HeapAlloc` at `0x140018fec`
- `KERNEL32!HeapAlloc` at `0x140018fec`
- `KERNEL32!HeapFree` at `0x1400195a9`
- `KERNEL32!HeapFree` at `0x1400195a9`
- `KERNEL32!GetProcessHeap` at `0x140018fd5`
- `KERNEL32!GetProcessHeap` at `0x140019595`
- `KERNEL32!GetProcessHeap` at `0x140018fd5`
- `KERNEL32!GetProcessHeap` at `0x140019595`
- `KERNEL32!SetDllDirectoryW` at `0x14001932c`
- `KERNEL32!SetDllDirectoryW` at `0x140019362`
- `KERNEL32!SetDllDirectoryW` at `0x14001932c`
- `KERNEL32!SetDllDirectoryW` at `0x140019362`
- `USER32!GetWindowLongPtrW` at `0x1400190e1`
- `USER32!GetWindowLongPtrW` at `0x1400190e1`
- `USER32!SetWindowLongPtrW` at `0x1400190f9`
- `USER32!SetWindowLongPtrW` at `0x1400190f9`
- `USER32!LoadImageW` at `0x14001927e`
- `USER32!LoadImageW` at `0x14001927e`
- `USER32!GetWindowLongW` at `0x14001907d`
- `USER32!GetWindowLongW` at `0x14001907d`
- `USER32!GetSystemMetrics` at `0x1400191f3`
- `USER32!GetSystemMetrics` at `0x140019206`
- `USER32!GetSystemMetrics` at `0x140019244`
- `USER32!GetSystemMetrics` at `0x140019257`
- `USER32!GetSystemMetrics` at `0x1400191f3`
- `USER32!GetSystemMetrics` at `0x140019206`
- `USER32!GetSystemMetrics` at `0x140019244`
- `USER32!GetSystemMetrics` at `0x140019257`
- `USER32!GetClientRect` at `0x14001910c`
- `USER32!GetClientRect` at `0x14001910c`
- `USER32!SendMessageW` at `0x1400190af`
- `USER32!SendMessageW` at `0x1400190cd`
- `USER32!SendMessageW` at `0x140019195`
- `USER32!SendMessageW` at `0x1400191de`
- `USER32!SendMessageW` at `0x1400192cd`
- `USER32!SendMessageW` at `0x140019415`
- `USER32!SendMessageW` at `0x140019463`
- `USER32!SendMessageW` at `0x1400194b8`
- `USER32!SendMessageW` at `0x1400190af`
- `USER32!SendMessageW` at `0x1400190cd`
- `USER32!SendMessageW` at `0x140019195`
- `USER32!SendMessageW` at `0x1400191de`
- `USER32!SendMessageW` at `0x1400192cd`
- `USER32!SendMessageW` at `0x140019415`
- `USER32!SendMessageW` at `0x140019463`
- `USER32!SendMessageW` at `0x1400194b8`
- `COMCTL32!ImageList_ReplaceIcon` at `0x1400192ad`
- `COMCTL32!ImageList_ReplaceIcon` at `0x1400193b5`
- `COMCTL32!ImageList_ReplaceIcon` at `0x1400192ad`
- `COMCTL32!ImageList_ReplaceIcon` at `0x1400193b5`
- `COMCTL32!ImageList_Create` at `0x140019220`
- `COMCTL32!ImageList_Create` at `0x140019220`
- `OLEAUT32!__imp_SysFreeString` at `0x140019314`
- `OLEAUT32!__imp_SysFreeString` at `0x1400193ec`
- `OLEAUT32!__imp_SysFreeString` at `0x14001943a`
- `OLEAUT32!__imp_SysFreeString` at `0x14001955c`
- `OLEAUT32!__imp_SysFreeString` at `0x140019570`
- `OLEAUT32!__imp_SysFreeString` at `0x140019584`
- `OLEAUT32!__imp_SysFreeString` at `0x140019314`
- `OLEAUT32!__imp_SysFreeString` at `0x1400193ec`
- `OLEAUT32!__imp_SysFreeString` at `0x14001943a`
- `OLEAUT32!__imp_SysFreeString` at `0x14001955c`
- `OLEAUT32!__imp_SysFreeString` at `0x140019570`
- `OLEAUT32!__imp_SysFreeString` at `0x140019584`
- `DUI70!?SetNotifyHandler@CCBase@DirectUI@@QEAAXP6AHI_K_JPEA_JPEAX@Z3@Z` at `0x1400194fd`
- `DUI70!?SetNotifyHandler@CCBase@DirectUI@@QEAAXP6AHI_K_JPEA_JPEAX@Z3@Z` at `0x1400194fd`

## pseudocode

```c
__int64 __fastcall IntroPage::SetupPackageList(IntroPage *this)
{
  OLECHAR *v1; // r15
  HANDLE ProcessHeap; // rax
  void *v4; // rsi
  signed int v5; // ebx
  int NamedHandle; // eax
  int v7; // r9d
  HWND v8; // r13
  UINT v9; // r14d
  LONG_PTR WindowLongPtrW; // rax
  signed int LastError; // eax
  int LocalString; // eax
  int v13; // eax
  int SystemMetrics; // ebx
  int v15; // eax
  int v16; // ebx
  int v17; // eax
  HICON ImageW; // r8
  OLECHAR *v19; // r14
  OLECHAR *v20; // r12
  unsigned int i; // esi
  signed int v22; // eax
  signed int v23; // eax
  unsigned int v24; // eax
  WizardPage *v25; // rsi
  int NamedElement; // eax
  int v27; // r9d
  struct DirectUI::Element *v28; // rbx
  HANDLE v29; // rax
  signed int v31; // eax
  signed int v32; // eax
  int cGrow; // [rsp+20h] [rbp-E0h]
  HWND hWnd; // [rsp+30h] [rbp-D0h] BYREF
  HICON hicon; // [rsp+38h] [rbp-C8h] BYREF
  HIMAGELIST himl; // [rsp+40h] [rbp-C0h]
  struct DirectUI::Element *v37; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v38; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v39; // [rsp+58h] [rbp-A8h]
  WizardPage *v40; // [rsp+60h] [rbp-A0h]
  LPARAM lParam[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v42; // [rsp+78h] [rbp-88h]
  __int128 v43; // [rsp+88h] [rbp-78h]
  __int64 v44; // [rsp+98h] [rbp-68h]
  _DWORD v45[6]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v46; // [rsp+B8h] [rbp-48h]
  int v47; // [rsp+C4h] [rbp-3Ch]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  LPARAM v49; // [rsp+100h] [rbp+0h] BYREF
  int v50; // [rsp+10Ch] [rbp+Ch]
  int v51; // [rsp+110h] [rbp+10h]
  struct tagRECT Rect; // [rsp+160h] [rbp+60h] BYREF

  v1 = 0;
  v40 = this;
  hWnd = 0;
  memset_0(v45, 0, 0x58u);
  v37 = 0;
  *(_OWORD *)lParam = 0;
  v44 = 0;
  v42 = 0;
  v43 = 0;
  Rect = 0;
  ProcessHeap = GetProcessHeap();
  v38 = HeapAlloc(ProcessHeap, 0, 0x208u);
  v4 = v38;
  if ( v38 )
  {
    NamedHandle = WizardPage::GetNamedHandle(this, L"lstView", &hWnd);
    v5 = NamedHandle;
    if ( NamedHandle < 0 )
    {
      cGrow = NamedHandle;
      v7 = 536;
LABEL_5:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "IntroPage::SetupPackageList", v7, cGrow);
LABEL_53:
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v4);
      return (unsigned int)v5;
    }
    v8 = hWnd;
    v9 = (GetWindowLongW(hWnd, -20) & 0x400000 | 0x4200u) >> 9;
    SendMessageW(v8, 0x1036u, 0x10420u, 66592);
    SendMessageW(v8, 0x108Eu, 1u, 0);
    WindowLongPtrW = GetWindowLongPtrW(v8, -16);
    SetWindowLongPtrW(v8, -16, WindowLongPtrW | 4);
    if ( !GetClientRect(v8, &Rect) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 < 0 )
      {
        v7 = 555;
LABEL_11:
        cGrow = v5;
        goto LABEL_5;
      }
    }
    LocalString = DwzLoadLocalString(0x82u, (LPWSTR)v4, 0x104u);
    v5 = LocalString;
    if ( LocalString < 0 )
    {
      cGrow = LocalString;
      v7 = 561;
      goto LABEL_5;
    }
    LODWORD(lParam[0]) = 14;
    HIDWORD(v42) = 0;
    *(_QWORD *)&v42 = v4;
    SendMessageW(v8, 0x1061u, 0, (LPARAM)lParam);
    v13 = DwzLoadLocalString(0x83u, (LPWSTR)v4, 0x104u);
    v5 = v13;
    if ( v13 < 0 )
    {
      cGrow = v13;
      v7 = 573;
      goto LABEL_5;
    }
    HIDWORD(v42) = 1;
    *(_QWORD *)&v42 = v4;
    SendMessageW(v8, 0x1061u, 1u, (LPARAM)lParam);
    *(_QWORD *)&v45[1] = 0;
    SystemMetrics = GetSystemMetrics(50);
    v15 = GetSystemMetrics(49);
    himl = ImageList_Create(v15, SystemMetrics, v9, 1, 1);
    if ( (unsigned __int64)himl - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v32 = GetLastError();
      v5 = v32;
      if ( v32 > 0 )
        v5 = (unsigned __int16)v32 | 0x80070000;
      v7 = 591;
      goto LABEL_11;
    }
    v16 = GetSystemMetrics(50);
    v17 = GetSystemMetrics(49);
    ImageW = (HICON)LoadImageW(g_hInstance, (LPCWSTR)0x6B, 1u, v17, v16, 0);
    hicon = ImageW;
    if ( (unsigned __int64)ImageW - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v31 = GetLastError();
      v5 = v31;
      if ( v31 > 0 )
        v5 = (unsigned __int16)v31 | 0x80070000;
      v7 = 603;
      goto LABEL_11;
    }
    v19 = 0;
    v20 = 0;
    ImageList_ReplaceIcon(himl, -1, ImageW);
    LODWORD(hWnd) = 1;
    SendMessageW(v8, 0x1003u, 1u, (LPARAM)himl);
    for ( i = 0; i < Packages_GetNumber(); ++i )
    {
      v45[1] = Packages_GetNumber();
      v45[0] = 7;
      v39 = (unsigned __int16 *)Package_Icon(i);
      if ( !v39 )
        goto LABEL_33;
      if ( v19 )
        SysFreeString(v19);
      v19 = Package_PackageLocation(i);
      if ( !SetDllDirectoryW(0) )
      {
        v22 = GetLastError();
        v5 = v22;
        if ( v22 > 0 )
          v5 = (unsigned __int16)v22 | 0x80070000;
        if ( v5 < 0 )
        {
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "IntroPage::SetupPackageList", 629, v5);
          goto LABEL_46;
        }
      }
      if ( !SetDllDirectoryW(v19) )
      {
        v23 = GetLastError();
        v5 = v23;
        if ( v23 > 0 )
          v5 = (unsigned __int16)v23 | 0x80070000;
        if ( v5 < 0 )
        {
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "IntroPage::SetupPackageList", 632, v5);
          goto LABEL_46;
        }
      }
      if ( (int)DwzLoadSmallIcon(v39, &hicon) >= 0 )
      {
        ImageList_ReplaceIcon(himl, -1, hicon);
        v47 = (int)hWnd;
        LODWORD(hWnd) = (_DWORD)hWnd + 1;
      }
      else
      {
LABEL_33:
        v47 = 0;
      }
      v48 = i;
      v45[2] = 0;
      if ( v1 )
        SysFreeString(v1);
      v46 = Package_Name(i);
      v1 = v46;
      v24 = SendMessageW(v8, 0x104Du, 0, (LPARAM)v45);
      v45[0] = 1;
      *(_QWORD *)&v45[1] = v24 | 0x100000000LL;
      v48 = 0;
      if ( v20 )
        SysFreeString(v20);
      v46 = Package_Publisher(i);
      v20 = v46;
      SendMessageW(v8, 0x104Cu, 0, (LPARAM)v45);
    }
    memset_0(&v49, 0, 0x58u);
    v51 = 1;
    v50 = 1;
    SendMessageW(v8, 0x102Bu, 0, (LPARAM)&v49);
    v25 = v40;
    NamedElement = WizardPage::GetNamedElement(v40, L"lstView", &v37);
    v5 = NamedElement;
    if ( NamedElement >= 0 )
    {
      v28 = v37;
      DirectUI::CCBase::SetNotifyHandler(
        v37,
        (int (*)(unsigned int, unsigned __int64, __int64, __int64 *, void *))IntroPage::NotifyHandler,
        v25);
      (*(void (__fastcall **)(struct DirectUI::Element *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v28 + 416LL))(
        v28,
        (unsigned int)Rect.right,
        (unsigned int)Rect.bottom,
        0);
      NamedElement = IntroPage::EnablePrivacyButton(v25, 0);
      v5 = NamedElement;
      if ( NamedElement >= 0 )
      {
LABEL_46:
        if ( v1 )
          SysFreeString(v1);
        if ( v20 )
          SysFreeString(v20);
        if ( v19 )
          SysFreeString(v19);
        v4 = v38;
        goto LABEL_53;
      }
      v27 = 685;
    }
    else
    {
      v27 = 674;
    }
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "IntroPage::SetupPackageList", v27, NamedElement);
    goto LABEL_46;
  }
  v5 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "IntroPage::SetupPackageList", 533, -2147024882);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140018f6c  push    rbp
0x140018f6e  push    rbx
0x140018f6f  push    rsi
0x140018f70  push    rdi
0x140018f71  push    r12
0x140018f73  push    r13
0x140018f75  push    r14
0x140018f77  push    r15
0x140018f79  lea     rbp, [rsp-88h]
0x140018f81  sub     rsp, 188h
0x140018f88  mov     rax, cs:__security_cookie
0x140018f8f  xor     rax, rsp
0x140018f92  mov     [rbp+0C0h+var_50], rax
0x140018f96  xor     r15d, r15d
0x140018f99  mov     [rsp+1C0h+var_160], rcx
0x140018f9e  mov     rbx, rcx
0x140018fa1  mov     [rsp+1C0h+hWnd], r15
0x140018fa6  xor     edx, edx; Val
0x140018fa8  lea     rcx, [rbp+0C0h+var_120]; void *
0x140018fac  lea     r8d, [r15+58h]; Size
0x140018fb0  call    memset_0
0x140018fb5  xorps   xmm0, xmm0
0x140018fb8  mov     [rsp+1C0h+var_178], r15
0x140018fbd  xor     eax, eax
0x140018fbf  movups  xmmword ptr [rsp+1C0h+lParam], xmm0
0x140018fc4  mov     [rbp+0C0h+var_128], rax
0x140018fc8  movups  [rsp+1C0h+var_148], xmm0
0x140018fcd  movups  [rbp+0C0h+var_138], xmm0
0x140018fd1  movups  xmmword ptr [rbp+0C0h+Rect.left], xmm0
0x140018fd5  call    cs:__imp_GetProcessHeap
0x140018fdc  nop     dword ptr [rax+rax+00h]
0x140018fe1  xor     edx, edx; dwFlags
0x140018fe3  mov     r8d, 208h; dwBytes
0x140018fe9  mov     rcx, rax; hHeap
0x140018fec  call    cs:__imp_HeapAlloc
0x140018ff3  nop     dword ptr [rax+rax+00h]
0x140018ff8  mov     [rsp+1C0h+var_170], rax
0x140018ffd  mov     rsi, rax
0x140019000  test    rax, rax
0x140019003  jnz     short loc_14001902F
0x140019005  mov     ebx, 8007000Eh
0x14001900a  lea     r8, aIntropageSetup; "IntroPage::SetupPackageList"
0x140019011  mov     r9d, 215h
0x140019017  mov     [rsp+1C0h+cGrow], ebx
0x14001901b  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140019022  lea     ecx, [rax+1]; Level
0x140019025  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001902a  jmp     loc_1400195B5
0x14001902f  lea     r8, [rsp+1C0h+hWnd]; HWND *
0x140019034  mov     rcx, rbx; this
0x140019037  lea     rdx, aLstview; "lstView"
0x14001903e  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x140019043  mov     ebx, eax
0x140019045  test    eax, eax
0x140019047  jns     short loc_140019070
0x140019049  mov     [rsp+1C0h+cGrow], eax
0x14001904d  mov     r9d, 218h
0x140019053  mov     ecx, 1; Level
0x140019058  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001905f  lea     r8, aIntropageSetup; "IntroPage::SetupPackageList"
0x140019066  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001906b  jmp     loc_140019595
0x140019070  mov     r13, [rsp+1C0h+hWnd]
0x140019075  mov     edx, 0FFFFFFECh; nIndex
0x14001907a  mov     rcx, r13; hWnd
0x14001907d  call    cs:__imp_GetWindowLongW
0x140019084  nop     dword ptr [rax+rax+00h]
0x140019089  mov     r8d, 10420h; wParam
0x14001908f  mov     edx, 1036h; Msg
0x140019094  mov     r14d, eax
0x140019097  mov     r9d, r8d; lParam
0x14001909a  and     r14d, 400000h
0x1400190a1  mov     rcx, r13; hWnd
0x1400190a4  or      r14d, 4200h
0x1400190ab  shr     r14d, 9
0x1400190af  call    cs:__imp_SendMessageW
0x1400190b6  nop     dword ptr [rax+rax+00h]
0x1400190bb  xor     r9d, r9d; lParam
0x1400190be  mov     edx, 108Eh; Msg
0x1400190c3  mov     rcx, r13; hWnd
0x1400190c6  lea     edi, [r9+1]
0x1400190ca  mov     r8d, edi; wParam
0x1400190cd  call    cs:__imp_SendMessageW
0x1400190d4  nop     dword ptr [rax+rax+00h]
0x1400190d9  lea     ebx, [rdi-11h]
0x1400190dc  mov     rcx, r13; hWnd
0x1400190df  mov     edx, ebx; nIndex
0x1400190e1  call    cs:__imp_GetWindowLongPtrW
0x1400190e8  nop     dword ptr [rax+rax+00h]
0x1400190ed  mov     edx, ebx; nIndex
0x1400190ef  mov     rcx, r13; hWnd
0x1400190f2  or      rax, 4
0x1400190f6  mov     r8, rax; dwNewLong
0x1400190f9  call    cs:__imp_SetWindowLongPtrW
0x140019100  nop     dword ptr [rax+rax+00h]
0x140019105  lea     rdx, [rbp+0C0h+Rect]; lpRect
0x140019109  mov     rcx, r13; hWnd
0x14001910c  call    cs:__imp_GetClientRect
0x140019113  nop     dword ptr [rax+rax+00h]
0x140019118  mov     r12d, 80070000h
0x14001911e  test    eax, eax
0x140019120  jnz     short loc_14001914F
0x140019122  call    cs:__imp_GetLastError
0x140019129  nop     dword ptr [rax+rax+00h]
0x14001912e  mov     ebx, eax
0x140019130  test    eax, eax
0x140019132  jle     short loc_14001913A
0x140019134  movzx   ebx, ax
0x140019137  or      ebx, r12d
0x14001913a  test    ebx, ebx
0x14001913c  jns     short loc_14001914F
0x14001913e  mov     r9d, 22Bh
0x140019144  mov     [rsp+1C0h+cGrow], ebx
0x140019148  mov     ecx, edi
0x14001914a  jmp     loc_140019058
0x14001914f  mov     r8d, 104h; cchBufferMax
0x140019155  mov     rdx, rsi; lpBuffer
0x140019158  mov     ecx, 82h; uID
0x14001915d  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x140019162  mov     ebx, eax
0x140019164  test    eax, eax
0x140019166  jns     short loc_140019174
0x140019168  mov     [rsp+1C0h+cGrow], eax
0x14001916c  mov     r9d, 231h
0x140019172  jmp     short loc_140019148
0x140019174  lea     r9, [rsp+1C0h+lParam]; lParam
0x140019179  mov     dword ptr [rsp+1C0h+lParam], 0Eh
0x140019181  xor     r8d, r8d; wParam
0x140019184  mov     dword ptr [rbp+0C0h+var_148+0Ch], r15d
0x140019188  mov     edx, 1061h; Msg
0x14001918d  mov     qword ptr [rsp+1C0h+var_148], rsi
0x140019192  mov     rcx, r13; hWnd
0x140019195  call    cs:__imp_SendMessageW
0x14001919c  nop     dword ptr [rax+rax+00h]
0x1400191a1  mov     r8d, 104h; cchBufferMax
0x1400191a7  mov     rdx, rsi; lpBuffer
0x1400191aa  mov     ecx, 83h; uID
0x1400191af  call    ?DwzLoadLocalString@@YAJIPEAG_K@Z; DwzLoadLocalString(uint,ushort *,unsigned __int64)
0x1400191b4  mov     ebx, eax
0x1400191b6  test    eax, eax
0x1400191b8  jns     short loc_1400191C6
0x1400191ba  mov     [rsp+1C0h+cGrow], eax
0x1400191be  mov     r9d, 23Dh
0x1400191c4  jmp     short loc_140019148
0x1400191c6  lea     r9, [rsp+1C0h+lParam]; lParam
0x1400191cb  mov     dword ptr [rbp+0C0h+var_148+0Ch], edi
0x1400191ce  mov     r8, rdi; wParam
0x1400191d1  mov     qword ptr [rsp+1C0h+var_148], rsi
0x1400191d6  mov     edx, 1061h; Msg
0x1400191db  mov     rcx, r13; hWnd
0x1400191de  call    cs:__imp_SendMessageW
0x1400191e5  nop     dword ptr [rax+rax+00h]
0x1400191ea  mov     ecx, 32h ; '2'; nIndex
0x1400191ef  mov     qword ptr [rbp+0C0h+var_120+4], r15
0x1400191f3  call    cs:__imp_GetSystemMetrics
0x1400191fa  nop     dword ptr [rax+rax+00h]
0x1400191ff  mov     ecx, 31h ; '1'; nIndex
0x140019204  mov     ebx, eax
0x140019206  call    cs:__imp_GetSystemMetrics
0x14001920d  nop     dword ptr [rax+rax+00h]
0x140019212  mov     r9d, edi; cInitial
0x140019215  mov     [rsp+1C0h+cGrow], edi; cGrow
0x140019219  mov     ecx, eax; cx
0x14001921b  mov     r8d, r14d; flags
0x14001921e  mov     edx, ebx; cy
0x140019220  call    cs:__imp_ImageList_Create
0x140019227  nop     dword ptr [rax+rax+00h]
0x14001922c  mov     [rsp+1C0h+himl], rax
0x140019231  lea     rcx, [rax-1]
0x140019235  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140019239  ja      loc_1400195FB
0x14001923f  mov     ecx, 32h ; '2'; nIndex
0x140019244  call    cs:__imp_GetSystemMetrics
0x14001924b  nop     dword ptr [rax+rax+00h]
0x140019250  mov     ecx, 31h ; '1'; nIndex
0x140019255  mov     ebx, eax
0x140019257  call    cs:__imp_GetSystemMetrics
0x14001925e  nop     dword ptr [rax+rax+00h]
0x140019263  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInst
0x14001926a  mov     r8d, edi; type
0x14001926d  mov     r9d, eax; cx
0x140019270  mov     [rsp+1C0h+fuLoad], r15d; fuLoad
0x140019275  mov     edx, 6Bh ; 'k'; name
0x14001927a  mov     [rsp+1C0h+cGrow], ebx; cy
0x14001927e  call    cs:__imp_LoadImageW
0x140019285  nop     dword ptr [rax+rax+00h]
0x14001928a  mov     r8, rax; hicon
0x14001928d  mov     [rsp+1C0h+hicon], rax
0x140019292  dec     rax
0x140019295  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019299  ja      loc_1400195D8
0x14001929f  mov     rcx, [rsp+1C0h+himl]; himl
0x1400192a4  or      edx, 0FFFFFFFFh; i
0x1400192a7  mov     r14, r15
0x1400192aa  mov     r12, r15
0x1400192ad  call    cs:__imp_ImageList_ReplaceIcon
0x1400192b4  nop     dword ptr [rax+rax+00h]
0x1400192b9  mov     r9, [rsp+1C0h+himl]; lParam
0x1400192be  mov     r8, rdi; wParam
0x1400192c1  mov     edx, 1003h; Msg
0x1400192c6  mov     dword ptr [rsp+1C0h+hWnd], edi
0x1400192ca  mov     rcx, r13; hWnd
0x1400192cd  call    cs:__imp_SendMessageW
0x1400192d4  nop     dword ptr [rax+rax+00h]
0x1400192d9  xor     esi, esi
0x1400192db  call    ?Packages_GetNumber@@YAIXZ; Packages_GetNumber(void)
0x1400192e0  cmp     esi, eax
0x1400192e2  jnb     loc_140019494
0x1400192e8  call    ?Packages_GetNumber@@YAIXZ; Packages_GetNumber(void)
0x1400192ed  mov     ecx, esi; unsigned int
0x1400192ef  mov     [rbp+0C0h+var_120+4], eax
0x1400192f2  mov     [rbp+0C0h+var_120], 7
0x1400192f9  call    ?Package_Icon@@YAPEBGI@Z; Package_Icon(uint)
0x1400192fe  mov     [rsp+1C0h+var_168], rax
0x140019303  test    rax, rax
0x140019306  jz      loc_1400193D0
0x14001930c  test    r14, r14
0x14001930f  jz      short loc_140019320
0x140019311  mov     rcx, r14; bstrString
0x140019314  call    cs:__imp_SysFreeString
0x14001931b  nop     dword ptr [rax+rax+00h]
0x140019320  mov     ecx, esi; unsigned int
0x140019322  call    ?Package_PackageLocation@@YAPEAGI@Z; Package_PackageLocation(uint)
0x140019327  xor     ecx, ecx; lpPathName
0x140019329  mov     r14, rax
0x14001932c  call    cs:__imp_SetDllDirectoryW
0x140019333  nop     dword ptr [rax+rax+00h]
0x140019338  test    eax, eax
0x14001933a  jnz     short loc_14001935F
0x14001933c  call    cs:__imp_GetLastError
0x140019343  nop     dword ptr [rax+rax+00h]
0x140019348  mov     ebx, eax
0x14001934a  test    eax, eax
0x14001934c  jle     short loc_140019357
0x14001934e  movzx   ebx, ax
0x140019351  or      ebx, 80070000h
0x140019357  test    ebx, ebx
0x140019359  js      loc_140019476
0x14001935f  mov     rcx, r14; lpPathName
0x140019362  call    cs:__imp_SetDllDirectoryW
0x140019369  nop     dword ptr [rax+rax+00h]
0x14001936e  test    eax, eax
0x140019370  jnz     short loc_140019395
0x140019372  call    cs:__imp_GetLastError
0x140019379  nop     dword ptr [rax+rax+00h]
0x14001937e  mov     ebx, eax
0x140019380  test    eax, eax
0x140019382  jle     short loc_14001938D
0x140019384  movzx   ebx, ax
0x140019387  or      ebx, 80070000h
0x14001938d  test    ebx, ebx
0x14001938f  js      loc_140019485
0x140019395  mov     rcx, [rsp+1C0h+var_168]; unsigned __int16 *
0x14001939a  lea     rdx, [rsp+1C0h+hicon]; HICON *
0x14001939f  call    ?DwzLoadSmallIcon@@YAJPEBGPEAPEAUHICON__@@@Z; DwzLoadSmallIcon(ushort const *,HICON__ * *)
0x1400193a4  test    eax, eax
0x1400193a6  js      short loc_1400193D0
0x1400193a8  mov     r8, [rsp+1C0h+hicon]; hicon
0x1400193ad  or      edx, 0FFFFFFFFh; i
0x1400193b0  mov     rcx, [rsp+1C0h+himl]; himl
0x1400193b5  call    cs:__imp_ImageList_ReplaceIcon
0x1400193bc  nop     dword ptr [rax+rax+00h]
0x1400193c1  mov     ebx, dword ptr [rsp+1C0h+hWnd]
0x1400193c5  mov     [rbp+0C0h+var_FC], ebx
0x1400193c8  add     ebx, edi
0x1400193ca  mov     dword ptr [rsp+1C0h+hWnd], ebx
0x1400193ce  jmp     short loc_1400193D7
0x1400193d0  mov     [rbp+0C0h+var_FC], 0
0x1400193d7  mov     eax, esi
0x1400193d9  mov     [rbp+0C0h+var_F8], rax
0x1400193dd  mov     [rbp+0C0h+var_120+8], 0
0x1400193e4  test    r15, r15
0x1400193e7  jz      short loc_1400193F8
0x1400193e9  mov     rcx, r15; bstrString
0x1400193ec  call    cs:__imp_SysFreeString
0x1400193f3  nop     dword ptr [rax+rax+00h]
0x1400193f8  mov     ecx, esi; unsigned int
0x1400193fa  call    ?Package_Name@@YAPEAGI@Z; Package_Name(uint)
0x1400193ff  lea     r9, [rbp+0C0h+var_120]; lParam
0x140019403  mov     [rbp+0C0h+var_108], rax
0x140019407  xor     r8d, r8d; wParam
0x14001940a  mov     edx, 104Dh; Msg
0x14001940f  mov     rcx, r13; hWnd
0x140019412  mov     r15, rax
0x140019415  call    cs:__imp_SendMessageW
0x14001941c  nop     dword ptr [rax+rax+00h]
0x140019421  mov     [rbp+0C0h+var_120], edi
0x140019424  mov     [rbp+0C0h+var_120+4], eax
0x140019427  mov     [rbp+0C0h+var_120+8], edi
0x14001942a  mov     [rbp+0C0h+var_F8], 0
0x140019432  test    r12, r12
0x140019435  jz      short loc_140019446
0x140019437  mov     rcx, r12; bstrString
0x14001943a  call    cs:__imp_SysFreeString
0x140019441  nop     dword ptr [rax+rax+00h]
0x140019446  mov     ecx, esi; unsigned int
0x140019448  call    ?Package_Publisher@@YAPEAGI@Z; Package_Publisher(uint)
0x14001944d  lea     r9, [rbp+0C0h+var_120]; lParam
0x140019451  mov     [rbp+0C0h+var_108], rax
0x140019455  xor     r8d, r8d; wParam
  ... truncated ...
```
