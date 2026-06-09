# CPhishingActionBar::Init(HWND__ *,HWND__ *,HFONT__ *,ushort *)

- ea: `0x18006ffb0`
- end: `0x180070603`
- name: `?Init@CPhishingActionBar@@QEAAJPEAUHWND__@@0PEAUHFONT__@@PEAG@Z`
- size: `1619`
- prototype: `__int64 __fastcall(CPhishingActionBar *__hidden this, HWND, HWND, HFONT, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18006fd10`

## callees

- `0x18000910c`
- `0x1800247c8`
- `0x18006ffb0`
- `0x180071860`
- `0x1800cb0bc`
- `0x1800cb0ec`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cca90`
- `0x1800cd010`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x180070067`
- `GDI32!CreateSolidBrush` at `0x180070067`
- `USER32!LoadStringW` at `0x18007029b`
- `USER32!LoadStringW` at `0x1800702ba`
- `USER32!LoadStringW` at `0x1800702d9`
- `USER32!LoadStringW` at `0x1800703cc`
- `USER32!LoadStringW` at `0x18007046e`
- `USER32!LoadStringW` at `0x18007029b`
- `USER32!LoadStringW` at `0x1800702ba`
- `USER32!LoadStringW` at `0x1800702d9`
- `USER32!LoadStringW` at `0x1800703cc`
- `USER32!LoadStringW` at `0x18007046e`
- `USER32!SendMessageA` at `0x1800701b0`
- `USER32!SendMessageA` at `0x1800701b0`
- `USER32!SetWindowLongPtrA` at `0x180070390`
- `USER32!SetWindowLongPtrA` at `0x1800703a2`
- `USER32!SetWindowLongPtrA` at `0x18007059f`
- `USER32!SetWindowLongPtrA` at `0x1800705b2`
- `USER32!SetWindowLongPtrA` at `0x180070390`
- `USER32!SetWindowLongPtrA` at `0x1800703a2`
- `USER32!SetWindowLongPtrA` at `0x18007059f`
- `USER32!SetWindowLongPtrA` at `0x1800705b2`
- `USER32!GetWindowLongPtrA` at `0x180070381`
- `USER32!GetWindowLongPtrA` at `0x180070381`
- `USER32!LoadCursorA` at `0x180070054`
- `USER32!LoadCursorA` at `0x180070054`
- `USER32!CreateWindowExW` at `0x1800700e8`
- `USER32!CreateWindowExW` at `0x18007017d`
- `USER32!CreateWindowExW` at `0x18007023d`
- `USER32!CreateWindowExW` at `0x180070365`
- `USER32!CreateWindowExW` at `0x180070432`
- `USER32!CreateWindowExW` at `0x1800704d4`
- `USER32!CreateWindowExW` at `0x180070538`
- `USER32!CreateWindowExW` at `0x1800700e8`
- `USER32!CreateWindowExW` at `0x18007017d`
- `USER32!CreateWindowExW` at `0x18007023d`
- `USER32!CreateWindowExW` at `0x180070365`
- `USER32!CreateWindowExW` at `0x180070432`
- `USER32!CreateWindowExW` at `0x1800704d4`
- `USER32!CreateWindowExW` at `0x180070538`
- `USER32!GetSystemMetrics` at `0x180070123`
- `USER32!GetSystemMetrics` at `0x180070130`
- `USER32!GetSystemMetrics` at `0x1800701e0`
- `USER32!GetSystemMetrics` at `0x180070123`
- `USER32!GetSystemMetrics` at `0x180070130`
- `USER32!GetSystemMetrics` at `0x1800701e0`
- `USER32!UpdateWindow` at `0x1800705d0`
- `USER32!UpdateWindow` at `0x1800705d0`
- `USER32!RegisterClassW` at `0x180070087`
- `USER32!RegisterClassW` at `0x180070087`
- `USER32!LoadIconA` at `0x18007019b`
- `USER32!LoadIconA` at `0x18007019b`
- `USER32!GetClassInfoW` at `0x180070038`
- `USER32!GetClassInfoW` at `0x180070038`

## string_xrefs

- `0x18007032f`: `SysLink`

## pseudocode

```c
__int64 __fastcall CPhishingActionBar::Init(CPhishingActionBar *this, HWND a2, HWND a3, HFONT a4, unsigned __int16 *a5)
{
  int LastError; // r15d
  HCURSOR CursorA; // rax
  HBRUSH SolidBrush; // rax
  HWND Window; // rax
  HINSTANCE v12; // rdi
  HWND v13; // rsi
  int nHeight; // ebx
  int nWidth; // eax
  HWND v16; // rax
  HICON IconA; // rax
  int X; // r13d
  HWND v19; // rax
  __int64 v20; // rcx
  HINSTANCE v21; // rbx
  HWND v22; // rdi
  int v23; // ecx
  int v24; // eax
  HWND v25; // rax
  HWND v26; // rbx
  LONG_PTR WindowLongPtrA; // rax
  HINSTANCE v28; // rbx
  HWND v29; // rsi
  int v30; // ecx
  int v31; // edi
  int v32; // eax
  HINSTANCE v33; // rbx
  HWND v34; // rsi
  int v35; // ecx
  int v36; // edi
  int v37; // eax
  HWND v38; // rax
  __int64 v39; // rcx
  HWND hWndParent; // [rsp+40h] [rbp-C0h]
  HINSTANCE hInstance; // [rsp+50h] [rbp-B0h]
  int v43; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+64h] [rbp-9Ch] BYREF
  int v45; // [rsp+68h] [rbp-98h] BYREF
  GUID v46; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v47; // [rsp+80h] [rbp-80h]
  HFONT v48; // [rsp+88h] [rbp-78h]
  tagWNDCLASSW WndClass; // [rsp+90h] [rbp-70h] BYREF
  WCHAR WindowName[512]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR v51[512]; // [rsp+4E0h] [rbp+3E0h] BYREF
  WCHAR v52[512]; // [rsp+8E0h] [rbp+7E0h] BYREF
  WCHAR Buffer[512]; // [rsp+CE0h] [rbp+BE0h] BYREF

  v48 = a4;
  v47 = a5;
  LastError = -2147024809;
  if ( a2 )
  {
    *((_QWORD *)this + 3) = a2;
    memset_0(&WndClass, 0, sizeof(WndClass));
    if ( GetClassInfoW(g_hInst, L"Phishing Action Bar", &WndClass) )
      goto LABEL_5;
    WndClass.lpfnWndProc = (WNDPROC)CPhishingActionBar::s_WndProc;
    CursorA = LoadCursorA(0, (LPCSTR)0x7F00);
    WndClass.lpszClassName = L"Phishing Action Bar";
    WndClass.hCursor = CursorA;
    SolidBrush = CreateSolidBrush(0xB9AEFFu);
    WndClass.style = 3;
    WndClass.hbrBackground = SolidBrush;
    WndClass.hInstance = g_hInst;
    if ( RegisterClassW(&WndClass) || (LastError = HrGetLastError(), LastError >= 0) )
    {
LABEL_5:
      Window = CreateWindowExW(
                 0x10000u,
                 L"Phishing Action Bar",
                 L"Phishing Action Bar",
                 0x52810000u,
                 0,
                 0,
                 705,
                 81,
                 a2,
                 0,
                 g_hInst,
                 this);
      *((_QWORD *)this + 5) = Window;
      v46 = PROPID_ACC_NAME;
      SetAccessibilityProperty(Window, &v46, L"Phishing Action Bar Main");
      v12 = g_hInst;
      v13 = (HWND)*((_QWORD *)this + 5);
      nHeight = GetSystemMetrics(12);
      nWidth = GetSystemMetrics(11);
      v16 = CreateWindowExW(
              0,
              L"STATIC",
              L"Phishing Action Bar Icon",
              0x50000203u,
              4,
              7,
              nWidth,
              nHeight,
              v13,
              (HMENU)0x80,
              v12,
              0);
      *((_QWORD *)this + 6) = v16;
      if ( v16 )
      {
        IconA = LoadIconA(g_hLocRes, (LPCSTR)3);
        SendMessageA(*((HWND *)this + 6), 0x172u, 1u, (LPARAM)IconA);
      }
      LastError = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, __int64))(**((_QWORD **)this + 14) + 40LL))(
                    *((_QWORD *)this + 14),
                    WindowName,
                    512);
      if ( LastError >= 0 )
      {
        X = GetSystemMetrics(11) + 11;
        v19 = CreateWindowExW(
                0,
                L"STATIC",
                WindowName,
                0x5000000Du,
                X,
                4,
                701 - X,
                36,
                *((HWND *)this + 5),
                (HMENU)0x81,
                g_hInst,
                0);
        v20 = *((_QWORD *)this + 14);
        *((_QWORD *)this + 7) = v19;
        v43 = 0;
        v44 = 0;
        v45 = 0;
        if ( (*(int (__fastcall **)(__int64, int *, int *, int *))(*(_QWORD *)v20 + 48LL))(v20, &v44, &v45, &v43) < 0 )
        {
          v43 = 1;
          v44 = 1;
          v45 = 1;
        }
        LoadStringW(g_hLocRes, 0x536u, Buffer, 512);
        LoadStringW(g_hLocRes, 0x538u, v52, 512);
        LoadStringW(g_hLocRes, 0x537u, v51, 512);
        if ( v43 )
        {
          StringCchPrintfW(WindowName, 0x200u, Buffer, v52, v51);
          v21 = g_hInst;
          v22 = (HWND)*((_QWORD *)this + 5);
          v24 = DPIScale_IntDialogUnitToPixelY(v23);
          v25 = CreateWindowExW(0, L"SysLink", WindowName, 0x50010000u, X, 47, 120, v24, v22, (HMENU)0x82, v21, 0);
          *((_QWORD *)this + 8) = v25;
          v26 = v25;
          if ( v25 )
          {
            WindowLongPtrA = GetWindowLongPtrA(v25, -4);
            SetWindowLongPtrA(v26, -21, WindowLongPtrA);
            SetWindowLongPtrA(v26, -4, (LONG_PTR)DeflashifierWndProc);
            X += 127;
          }
        }
        if ( v44 )
        {
          LoadStringW(g_hLocRes, 0x539u, WindowName, 512);
          v28 = g_hInst;
          v29 = (HWND)*((_QWORD *)this + 5);
          v31 = DPIScale_IntDialogUnitToPixelY(v30);
          v32 = DPIScale_IntDialogUnitToPixelX(80);
          *((_QWORD *)this + 9) = CreateWindowExW(
                                    0,
                                    L"BUTTON",
                                    WindowName,
                                    0x50010300u,
                                    X,
                                    47,
                                    v32,
                                    v31,
                                    v29,
                                    (HMENU)0x83,
                                    v28,
                                    0);
          X += DPIScale_IntDialogUnitToPixelX(80) + 7;
        }
        if ( v45 )
        {
          LoadStringW(g_hLocRes, 0x53Au, WindowName, 512);
          v33 = g_hInst;
          v34 = (HWND)*((_QWORD *)this + 5);
          v36 = DPIScale_IntDialogUnitToPixelY(v35);
          v37 = DPIScale_IntDialogUnitToPixelX(80);
          *((_QWORD *)this + 10) = CreateWindowExW(
                                     0,
                                     L"BUTTON",
                                     WindowName,
                                     0x50010300u,
                                     X,
                                     47,
                                     v37,
                                     v36,
                                     v34,
                                     (HMENU)0x84,
                                     v33,
                                     0);
        }
        if ( a3 )
        {
          hInstance = g_hInst;
          hWndParent = (HWND)*((_QWORD *)this + 3);
          *((_QWORD *)this + 4) = a3;
          v38 = CreateWindowExW(
                  0x120u,
                  L"STATIC",
                  &cchOriginalDestLength,
                  0x50000000u,
                  0,
                  0,
                  300,
                  300,
                  hWndParent,
                  0,
                  hInstance,
                  0);
          *((_QWORD *)this + 11) = v38;
          if ( v38 )
          {
            v46 = PROPID_ACC_NAME;
            SetAccessibilityProperty(v38, &v46, L"Phishing Document Barrier");
            if ( v47 )
            {
              v39 = *((_QWORD *)this + 11);
              v46 = PROPID_ACC_VALUE;
              SetAccessibilityProperty(v39, &v46, v47);
            }
            SetWindowLongPtrA(*((HWND *)this + 11), -4, (LONG_PTR)BlockerWndProc);
            SetWindowLongPtrA(*((HWND *)this + 11), -21, *((_QWORD *)this + 4));
          }
        }
        (*(void (__fastcall **)(char *, HFONT))(*((_QWORD *)this + 1) + 48LL))((char *)this + 8, v48);
        UpdateWindow(*((HWND *)this + 3));
      }
    }
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18006ffb0  mov     [rsp-8+arg_10], rbx
0x18006ffb5  push    rbp
0x18006ffb6  push    rsi
0x18006ffb7  push    rdi
0x18006ffb8  push    r12
0x18006ffba  push    r13
0x18006ffbc  push    r14
0x18006ffbe  push    r15
0x18006ffc0  lea     rbp, [rsp-0FF0h]
0x18006ffc8  mov     eax, 10F0h
0x18006ffcd  call    _alloca_probe
0x18006ffd2  sub     rsp, rax
0x18006ffd5  mov     rax, cs:__security_cookie
0x18006ffdc  xor     rax, rsp
0x18006ffdf  mov     [rbp+1020h+var_40], rax
0x18006ffe6  mov     rax, [rbp+1020h+arg_20]
0x18006ffed  xor     r13d, r13d
0x18006fff0  mov     [rbp+1020h+var_1098], r9
0x18006fff4  mov     r12, r8
0x18006fff7  mov     [rbp+1020h+var_10A0], rax
0x18006fffb  mov     rbx, rdx
0x18006fffe  mov     r14, rcx
0x180070001  mov     r15d, 80070057h
0x180070007  test    rdx, rdx
0x18007000a  jz      loc_1800705D6
0x180070010  mov     [rcx+18h], rdx
0x180070014  lea     r8d, [r13+48h]; Size
0x180070018  xor     edx, edx; Val
0x18007001a  lea     rcx, [rbp+1020h+WndClass]; void *
0x18007001e  call    memset_0
0x180070023  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x18007002a  lea     rdi, WindowName; "Phishing Action Bar"
0x180070031  mov     rdx, rdi; lpClassName
0x180070034  lea     r8, [rbp+1020h+WndClass]; lpWndClass
0x180070038  call    cs:__imp_GetClassInfoW
0x18007003e  test    eax, eax
0x180070040  jnz     short loc_1800700A2
0x180070042  lea     rax, ?s_WndProc@CPhishingActionBar@@SA_JPEAUHWND__@@I_K_J@Z; CPhishingActionBar::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180070049  mov     edx, 7F00h; lpCursorName
0x18007004e  xor     ecx, ecx; hInstance
0x180070050  mov     [rbp+1020h+WndClass.lpfnWndProc], rax
0x180070054  call    cs:__imp_LoadCursorA
0x18007005a  mov     ecx, 0B9AEFFh; color
0x18007005f  mov     [rbp+1020h+WndClass.lpszClassName], rdi
0x180070063  mov     [rbp+1020h+WndClass.hCursor], rax
0x180070067  call    cs:__imp_CreateSolidBrush
0x18007006d  lea     rcx, [rbp+1020h+WndClass]; lpWndClass
0x180070071  mov     [rbp+1020h+WndClass.style], 3
0x180070078  mov     [rbp+1020h+WndClass.hbrBackground], rax
0x18007007c  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180070083  mov     [rbp+1020h+WndClass.hInstance], rax
0x180070087  call    cs:__imp_RegisterClassW
0x18007008d  test    ax, ax
0x180070090  jnz     short loc_1800700A2
0x180070092  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180070097  mov     r15d, eax
0x18007009a  test    eax, eax
0x18007009c  js      loc_1800705D6
0x1800700a2  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x1800700a9  mov     r9d, 52810000h; dwStyle
0x1800700af  mov     [rsp+1120h+lpParam], r14; lpParam
0x1800700b4  mov     r8, rdi; lpWindowName
0x1800700b7  mov     [rsp+1120h+hInstance], rax; hInstance
0x1800700bc  mov     rdx, rdi; lpClassName
0x1800700bf  mov     [rsp+1120h+hMenu], r13; hMenu
0x1800700c4  mov     ecx, 10000h; dwExStyle
0x1800700c9  mov     [rsp+1120h+hWndParent], rbx; hWndParent
0x1800700ce  mov     [rsp+1120h+nHeight], 51h ; 'Q'; nHeight
0x1800700d6  mov     [rsp+1120h+nWidth], 2C1h; nWidth
0x1800700de  mov     [rsp+1120h+Y], r13d; Y
0x1800700e3  mov     [rsp+1120h+X], r13d; X
0x1800700e8  call    cs:__imp_CreateWindowExW
0x1800700ee  movups  xmm0, xmmword ptr cs:PROPID_ACC_NAME.Data1
0x1800700f5  lea     r8, aPhishingAction_1; "Phishing Action Bar Main"
0x1800700fc  mov     [r14+28h], rax
0x180070100  lea     rdx, [rsp+1120h+var_10B0]
0x180070105  mov     rcx, rax
0x180070108  movdqu  [rsp+1120h+var_10B0], xmm0
0x18007010e  call    _SetAccessibilityProperty
0x180070113  mov     rdi, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x18007011a  mov     ecx, 0Ch; nIndex
0x18007011f  mov     rsi, [r14+28h]
0x180070123  call    cs:__imp_GetSystemMetrics
0x180070129  mov     ecx, 0Bh; nIndex
0x18007012e  mov     ebx, eax
0x180070130  call    cs:__imp_GetSystemMetrics
0x180070136  mov     [rsp+1120h+lpParam], r13; lpParam
0x18007013b  lea     r8, aPhishingAction_0; "Phishing Action Bar Icon"
0x180070142  mov     [rsp+1120h+hInstance], rdi; hInstance
0x180070147  lea     rdx, aStatic; "STATIC"
0x18007014e  mov     [rsp+1120h+hMenu], 80h; hMenu
0x180070157  mov     edi, 4
0x18007015c  mov     [rsp+1120h+hWndParent], rsi; hWndParent
0x180070161  mov     r9d, 50000203h; dwStyle
0x180070167  mov     [rsp+1120h+nHeight], ebx; nHeight
0x18007016b  xor     ecx, ecx; dwExStyle
0x18007016d  mov     [rsp+1120h+nWidth], eax; nWidth
0x180070171  mov     [rsp+1120h+Y], 7; Y
0x180070179  mov     [rsp+1120h+X], edi; X
0x18007017d  call    cs:__imp_CreateWindowExW
0x180070183  xor     esi, esi
0x180070185  mov     [r14+30h], rax
0x180070189  lea     ebx, [rdi-3]
0x18007018c  test    rax, rax
0x18007018f  jz      short loc_1800701B6
0x180070191  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x180070198  lea     edx, [rdi-1]; lpIconName
0x18007019b  call    cs:__imp_LoadIconA
0x1800701a1  mov     rcx, [r14+30h]; hWnd
0x1800701a5  mov     r8d, ebx; wParam
0x1800701a8  mov     r9, rax; lParam
0x1800701ab  mov     edx, 172h; Msg
0x1800701b0  call    cs:__imp_SendMessageA
0x1800701b6  mov     rcx, [r14+70h]
0x1800701ba  lea     rdx, [rbp+1020h+WindowName]
0x1800701be  mov     r8d, 200h
0x1800701c4  mov     rax, [rcx]
0x1800701c7  mov     rax, [rax+28h]
0x1800701cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800701d0  mov     r15d, eax
0x1800701d3  test    eax, eax
0x1800701d5  js      loc_1800705D6
0x1800701db  mov     ecx, 0Bh; nIndex
0x1800701e0  call    cs:__imp_GetSystemMetrics
0x1800701e6  mov     [rsp+1120h+lpParam], rsi; lpParam
0x1800701eb  lea     r8, [rbp+1020h+WindowName]; lpWindowName
0x1800701ef  mov     ecx, 2BDh
0x1800701f4  lea     rdx, aStatic; "STATIC"
0x1800701fb  mov     r9d, 5000000Dh; dwStyle
0x180070201  lea     r13d, [rax+0Bh]
0x180070205  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x18007020c  mov     [rsp+1120h+hInstance], rax; hInstance
0x180070211  sub     ecx, r13d
0x180070214  mov     rax, [r14+28h]
0x180070218  mov     [rsp+1120h+hMenu], 81h; hMenu
0x180070221  mov     [rsp+1120h+hWndParent], rax; hWndParent
0x180070226  mov     [rsp+1120h+nHeight], 24h ; '$'; nHeight
0x18007022e  mov     [rsp+1120h+nWidth], ecx; nWidth
0x180070232  xor     ecx, ecx; dwExStyle
0x180070234  mov     [rsp+1120h+Y], edi; Y
0x180070238  mov     [rsp+1120h+X], r13d; X
0x18007023d  call    cs:__imp_CreateWindowExW
0x180070243  mov     rcx, [r14+70h]
0x180070247  lea     r9, [rsp+1120h+var_10C0]
0x18007024c  mov     [r14+38h], rax
0x180070250  lea     r8, [rsp+1120h+var_10B8]
0x180070255  mov     [rsp+1120h+var_10C0], esi
0x180070259  lea     rdx, [rsp+1120h+var_10BC]
0x18007025e  mov     [rsp+1120h+var_10BC], esi
0x180070262  mov     [rsp+1120h+var_10B8], esi
0x180070266  mov     rax, [rcx]
0x180070269  mov     rax, [rax+30h]
0x18007026d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070272  test    eax, eax
0x180070274  jns     short loc_180070282
0x180070276  mov     [rsp+1120h+var_10C0], ebx
0x18007027a  mov     [rsp+1120h+var_10BC], ebx
0x18007027e  mov     [rsp+1120h+var_10B8], ebx
0x180070282  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x180070289  lea     r8, [rbp+1020h+Buffer]; lpBuffer
0x180070290  mov     r9d, 200h; cchBufferMax
0x180070296  mov     edx, 536h; uID
0x18007029b  call    cs:__imp_LoadStringW
0x1800702a1  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x1800702a8  lea     r8, [rbp+1020h+var_840]; lpBuffer
0x1800702af  mov     r9d, 200h; cchBufferMax
0x1800702b5  mov     edx, 538h; uID
0x1800702ba  call    cs:__imp_LoadStringW
0x1800702c0  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x1800702c7  lea     r8, [rbp+1020h+var_C40]; lpBuffer
0x1800702ce  mov     r9d, 200h; cchBufferMax
0x1800702d4  mov     edx, 537h; uID
0x1800702d9  call    cs:__imp_LoadStringW
0x1800702df  cmp     [rsp+1120h+var_10C0], esi
0x1800702e3  jz      loc_1800703AC
0x1800702e9  lea     rax, [rbp+1020h+var_C40]
0x1800702f0  mov     edx, 200h; unsigned __int64
0x1800702f5  lea     r9, [rbp+1020h+var_840]
0x1800702fc  mov     qword ptr [rsp+1120h+X], rax
0x180070301  lea     r8, [rbp+1020h+Buffer]; unsigned __int16 *
0x180070308  lea     rcx, [rbp+1020h+WindowName]; unsigned __int16 *
0x18007030c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180070311  mov     rbx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180070318  mov     rdi, [r14+28h]
0x18007031c  call    ?DPIScale_IntDialogUnitToPixelY@@YAHH@Z; DPIScale_IntDialogUnitToPixelY(int)
0x180070321  mov     [rsp+1120h+lpParam], rsi; lpParam
0x180070326  lea     r8, [rbp+1020h+WindowName]; lpWindowName
0x18007032a  mov     [rsp+1120h+hInstance], rbx; hInstance
0x18007032f  lea     rdx, aSyslink; "SysLink"
0x180070336  mov     [rsp+1120h+hMenu], 82h; hMenu
0x18007033f  mov     r9d, 50010000h; dwStyle
0x180070345  mov     [rsp+1120h+hWndParent], rdi; hWndParent
0x18007034a  xor     ecx, ecx; dwExStyle
0x18007034c  mov     [rsp+1120h+nHeight], eax; nHeight
0x180070350  mov     [rsp+1120h+nWidth], 78h ; 'x'; nWidth
0x180070358  mov     [rsp+1120h+Y], 2Fh ; '/'; Y
0x180070360  mov     [rsp+1120h+X], r13d; X
0x180070365  call    cs:__imp_CreateWindowExW
0x18007036b  mov     [r14+40h], rax
0x18007036f  mov     rbx, rax
0x180070372  test    rax, rax
0x180070375  jz      short loc_1800703AC
0x180070377  mov     edi, 0FFFFFFFCh
0x18007037c  mov     rcx, rax; hWnd
0x18007037f  mov     edx, edi; nIndex
0x180070381  call    cs:__imp_GetWindowLongPtrA
0x180070387  lea     edx, [rdi-11h]; nIndex
0x18007038a  mov     rcx, rbx; hWnd
0x18007038d  mov     r8, rax; dwNewLong
0x180070390  call    cs:__imp_SetWindowLongPtrA
0x180070396  lea     r8, _DeflashifierWndProc; dwNewLong
0x18007039d  mov     edx, edi; nIndex
0x18007039f  mov     rcx, rbx; hWnd
0x1800703a2  call    cs:__imp_SetWindowLongPtrA
0x1800703a8  add     r13d, 7Fh
0x1800703ac  cmp     [rsp+1120h+var_10BC], esi
0x1800703b0  jz      loc_18007044E
0x1800703b6  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x1800703bd  lea     r8, [rbp+1020h+WindowName]; lpBuffer
0x1800703c1  mov     r9d, 200h; cchBufferMax
0x1800703c7  mov     edx, 539h; uID
0x1800703cc  call    cs:__imp_LoadStringW
0x1800703d2  mov     rbx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x1800703d9  mov     rsi, [r14+28h]
0x1800703dd  call    ?DPIScale_IntDialogUnitToPixelY@@YAHH@Z; DPIScale_IntDialogUnitToPixelY(int)
0x1800703e2  mov     ecx, 50h ; 'P'; int
0x1800703e7  mov     edi, eax
0x1800703e9  call    ?DPIScale_IntDialogUnitToPixelX@@YAHH@Z; DPIScale_IntDialogUnitToPixelX(int)
0x1800703ee  mov     [rsp+1120h+lpParam], 0; lpParam
0x1800703f7  lea     r8, [rbp+1020h+WindowName]; lpWindowName
0x1800703fb  mov     [rsp+1120h+hInstance], rbx; hInstance
0x180070400  lea     rdx, aButton; "BUTTON"
0x180070407  mov     [rsp+1120h+hMenu], 83h; hMenu
0x180070410  mov     r9d, 50010300h; dwStyle
0x180070416  mov     [rsp+1120h+hWndParent], rsi; hWndParent
0x18007041b  xor     ecx, ecx; dwExStyle
0x18007041d  mov     [rsp+1120h+nHeight], edi; nHeight
0x180070421  mov     [rsp+1120h+nWidth], eax; nWidth
0x180070425  mov     [rsp+1120h+Y], 2Fh ; '/'; Y
0x18007042d  mov     [rsp+1120h+X], r13d; X
0x180070432  call    cs:__imp_CreateWindowExW
0x180070438  mov     ecx, 50h ; 'P'; int
0x18007043d  mov     [r14+48h], rax
0x180070441  call    ?DPIScale_IntDialogUnitToPixelX@@YAHH@Z; DPIScale_IntDialogUnitToPixelX(int)
0x180070446  add     eax, 7
0x180070449  add     r13d, eax
0x18007044c  xor     esi, esi
0x18007044e  cmp     [rsp+1120h+var_10B8], esi
0x180070452  jz      loc_1800704E0
0x180070458  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18007045f  lea     r8, [rbp+1020h+WindowName]; lpBuffer
0x180070463  mov     r9d, 200h; cchBufferMax
0x180070469  mov     edx, 53Ah; uID
0x18007046e  call    cs:__imp_LoadStringW
0x180070474  mov     rbx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x18007047b  mov     rsi, [r14+28h]
0x18007047f  call    ?DPIScale_IntDialogUnitToPixelY@@YAHH@Z; DPIScale_IntDialogUnitToPixelY(int)
0x180070484  mov     ecx, 50h ; 'P'; int
0x180070489  mov     edi, eax
0x18007048b  call    ?DPIScale_IntDialogUnitToPixelX@@YAHH@Z; DPIScale_IntDialogUnitToPixelX(int)
0x180070490  mov     [rsp+1120h+lpParam], 0; lpParam
0x180070499  lea     r8, [rbp+1020h+WindowName]; lpWindowName
0x18007049d  mov     [rsp+1120h+hInstance], rbx; hInstance
0x1800704a2  lea     rdx, aButton; "BUTTON"
0x1800704a9  mov     [rsp+1120h+hMenu], 84h; hMenu
0x1800704b2  mov     r9d, 50010300h; dwStyle
0x1800704b8  mov     [rsp+1120h+hWndParent], rsi; hWndParent
0x1800704bd  xor     ecx, ecx; dwExStyle
0x1800704bf  mov     [rsp+1120h+nHeight], edi; nHeight
0x1800704c3  mov     [rsp+1120h+nWidth], eax; nWidth
0x1800704c7  mov     [rsp+1120h+Y], 2Fh ; '/'; Y
0x1800704cf  mov     [rsp+1120h+X], r13d; X
0x1800704d4  call    cs:__imp_CreateWindowExW
0x1800704da  mov     [r14+50h], rax
0x1800704de  xor     esi, esi
0x1800704e0  test    r12, r12
0x1800704e3  jz      loc_1800705B8
0x1800704e9  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x1800704f0  lea     r8, cchOriginalDestLength; lpWindowName
0x1800704f7  mov     [rsp+1120h+lpParam], rsi; lpParam
0x1800704fc  lea     rdx, aStatic; "STATIC"
0x180070503  mov     [rsp+1120h+hInstance], rax; hInstance
0x180070508  mov     r9d, 50000000h; dwStyle
0x18007050e  mov     rax, [r14+18h]
0x180070512  mov     [rsp+1120h+hMenu], rsi; hMenu
0x180070517  mov     [rsp+1120h+hWndParent], rax; hWndParent
0x18007051c  mov     eax, 12Ch
0x180070521  mov     [rsp+1120h+nHeight], eax; nHeight
0x180070525  mov     [rsp+1120h+nWidth], eax; nWidth
0x180070529  mov     [rsp+1120h+Y], esi; Y
0x18007052d  lea     ecx, [rax-0Ch]; dwExStyle
0x180070530  mov     [r14+20h], r12
0x180070534  mov     [rsp+1120h+X], esi; X
0x180070538  call    cs:__imp_CreateWindowExW
0x18007053e  mov     [r14+58h], rax
0x180070542  test    rax, rax
0x180070545  jz      short loc_1800705B8
0x180070547  movups  xmm0, xmmword ptr cs:PROPID_ACC_NAME.Data1
0x18007054e  lea     r8, aPhishingDocume; "Phishing Document Barrier"
0x180070555  mov     rcx, rax
  ... truncated ...
```
