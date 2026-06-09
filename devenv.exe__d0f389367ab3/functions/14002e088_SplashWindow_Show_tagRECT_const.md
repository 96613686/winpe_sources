# SplashWindow::Show(tagRECT const &)

- ea: `0x14002e088`
- end: `0x14002e3d6`
- name: `?Show@SplashWindow@@AEAA_NAEBUtagRECT@@@Z`
- size: `846`
- prototype: `bool __fastcall(SplashWindow *__hidden this, const struct tagRECT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000a8f0`
- `0x14002e9c0`

## callees

- `0x140001020`
- `0x140001040`
- `0x14001cbec`
- `0x14002e088`
- `0x14002f440`

## import_xrefs

- `KERNEL32!MulDiv` at `0x14002e287`
- `KERNEL32!MulDiv` at `0x14002e297`
- `KERNEL32!MulDiv` at `0x14002e287`
- `KERNEL32!MulDiv` at `0x14002e297`
- `USER32!RegisterClassW` at `0x14002e114`
- `USER32!RegisterClassW` at `0x14002e114`
- `USER32!CreateWindowExW` at `0x14002e257`
- `USER32!CreateWindowExW` at `0x14002e2f1`
- `USER32!CreateWindowExW` at `0x14002e364`
- `USER32!CreateWindowExW` at `0x14002e257`
- `USER32!CreateWindowExW` at `0x14002e2f1`
- `USER32!CreateWindowExW` at `0x14002e364`
- `USER32!SendMessageW` at `0x14002e37e`
- `USER32!SendMessageW` at `0x14002e37e`
- `USER32!ShowWindow` at `0x14002e399`
- `USER32!ShowWindow` at `0x14002e399`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14002e310`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14002e310`
- `IMM32!ImmAssociateContext` at `0x14002e38a`
- `IMM32!ImmAssociateContext` at `0x14002e38a`
- `GDI32!GetObjectW` at `0x14002e16f`
- `GDI32!GetObjectW` at `0x14002e16f`

## pseudocode

```c
char __fastcall SplashWindow::Show(SplashWindow *this, const struct tagRECT *a2)
{
  SplashWindow *v2; // rdi
  ATOM v4; // ax
  char v5; // cl
  int v6; // r15d
  DWORD v7; // r12d
  int nWidth; // ebp
  int nHeight; // r14d
  LONG X; // r13d
  int *v11; // rsi
  int *v12; // rbx
  HWND Window; // rax
  int v14; // ebx
  int v15; // eax
  HWND v16; // rax
  HWND v17; // rax
  POINT v19; // [rsp+60h] [rbp-B8h]
  HMONITOR v20; // [rsp+60h] [rbp-B8h]
  LONG Y; // [rsp+68h] [rbp-B0h]
  WNDCLASSW WndClass; // [rsp+70h] [rbp-A8h] BYREF
  _OWORD pv[2]; // [rsp+C0h] [rbp-58h] BYREF

  v2 = SplashWindow::sm_pThis;
  if ( *((_QWORD *)SplashWindow::sm_pThis + 1) )
    return 0;
  if ( !*((_WORD *)SplashWindow::sm_pThis + 12) )
  {
    memset_0(&WndClass, 0, sizeof(WndClass));
    WndClass.hInstance = (HINSTANCE)IMM32_NULL_THUNK_DATA;
    WndClass.lpfnWndProc = (WNDPROC)SplashWindow::WndProc;
    WndClass.lpszClassName = L"VSSplash";
    v4 = RegisterClassW(&WndClass);
    *((_WORD *)v2 + 12) = v4;
    if ( !v4 )
      return 0;
  }
  v5 = *((_BYTE *)v2 + 72);
  memset(pv, 0, sizeof(pv));
  v6 = v5 != 0 ? 0x2000000 : 0;
  v7 = v5 != 0 ? 12582912 : 0x80000000;
  GetObjectW(*((HANDLE *)v2 + 4), 32, pv);
  nWidth = DWORD1(pv[0]);
  nHeight = DWORD2(pv[0]);
  X = a2->left + (a2->right - a2->left - DWORD1(pv[0])) / 2;
  v19.x = X;
  v19.y = a2->top + (a2->bottom - a2->top - DWORD2(pv[0])) / 2;
  Y = v19.y;
  v20 = xMonitorFromPoint(v19, 2u);
  v11 = (int *)((char *)v2 + 68);
  v12 = (int *)((char *)v2 + 64);
  if ( v20 && v2 != (SplashWindow *)-64LL && v2 != (SplashWindow *)-68LL )
  {
    VsUI::CDpiAwareness::Initialize();
    if ( VsUI::CDpiAwareness::s_pGetDFM )
    {
      VsUI::CDpiAwareness::s_pGetDFM(v20, 0, (char *)v2 + 64, (char *)v2 + 68);
    }
    else
    {
      *v12 = VsUI::CDpiAwareness::s_DeviceDpiX;
      *v11 = VsUI::CDpiAwareness::s_DeviceDpiY;
    }
  }
  Window = CreateWindowExW(
             v6 + 128,
             (LPCWSTR)*((unsigned __int16 *)v2 + 12),
             *((LPCWSTR *)v2 + 6),
             v7,
             X,
             Y,
             nWidth,
             nHeight,
             0,
             0,
             (HINSTANCE)IMM32_NULL_THUNK_DATA,
             0);
  *((_QWORD *)v2 + 1) = Window;
  if ( !Window )
    return 0;
  if ( *((_BYTE *)v2 + 72) )
  {
    v14 = MulDiv(28, *v12, 96);
    v15 = MulDiv(28, *v11, 96);
    v16 = CreateWindowExW(
            0,
            L"BUTTON",
            &WindowName,
            0x50000000u,
            nWidth - v14 - 2,
            1,
            v14,
            v15,
            *((HWND *)v2 + 1),
            (HMENU)0x64,
            (HINSTANCE)IMM32_NULL_THUNK_DATA,
            0);
    *((_QWORD *)v2 + 2) = v16;
    if ( v16 )
      SetWindowSubclass(v16, SplashWindow::ButtonWndProc, 0, 0);
  }
  v17 = CreateWindowExW(
          0,
          L"STATIC",
          &WindowName,
          0x5000000Eu,
          -(*((_BYTE *)v2 + 72) != 0),
          0,
          nWidth,
          nHeight,
          *((HWND *)v2 + 1),
          0,
          (HINSTANCE)IMM32_NULL_THUNK_DATA,
          0);
  if ( !v17 )
    return 0;
  SendMessageW(v17, 0x172u, 0, *((_QWORD *)v2 + 4));
  ImmAssociateContext(*((HWND *)v2 + 1), 0);
  ShowWindow(*((HWND *)v2 + 1), 5);
  return 1;
}

```

## disassembly

```asm
0x14002e088  mov     [rsp+arg_0], rbx
0x14002e08d  mov     [rsp+arg_10], rbp
0x14002e092  mov     [rsp+arg_18], rsi
0x14002e097  push    rdi
0x14002e098  push    r12
0x14002e09a  push    r13
0x14002e09c  push    r14
0x14002e09e  push    r15
0x14002e0a0  sub     rsp, 0F0h
0x14002e0a7  mov     rax, cs:__security_cookie
0x14002e0ae  xor     rax, rsp
0x14002e0b1  mov     [rsp+118h+var_38], rax
0x14002e0b9  mov     rdi, cs:?sm_pThis@SplashWindow@@0PEAV1@EA; SplashWindow * SplashWindow::sm_pThis
0x14002e0c0  xor     esi, esi
0x14002e0c2  mov     rbx, rdx
0x14002e0c5  cmp     [rdi+8], rsi
0x14002e0c9  jnz     loc_14002E3A3
0x14002e0cf  lea     rbp, _IMM32_NULL_THUNK_DATA; "MZ"
0x14002e0d6  cmp     [rdi+18h], si
0x14002e0da  jnz     short loc_14002E127
0x14002e0dc  xor     edx, edx; Val
0x14002e0de  lea     r8d, [rsi+48h]; Size
0x14002e0e2  lea     rcx, [rsp+118h+WndClass]; void *
0x14002e0e7  call    memset_0
0x14002e0ec  lea     rax, ?WndProc@SplashWindow@@CA_JPEAUHWND__@@I_K_J@Z; SplashWindow::WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x14002e0f3  mov     [rsp+118h+WndClass.hInstance], rbp
0x14002e0fb  mov     [rsp+118h+WndClass.lpfnWndProc], rax
0x14002e100  lea     rcx, [rsp+118h+WndClass]; lpWndClass
0x14002e105  lea     rax, aVssplash; "VSSplash"
0x14002e10c  mov     [rsp+118h+WndClass.lpszClassName], rax
0x14002e114  call    cs:__imp_RegisterClassW
0x14002e11a  mov     [rdi+18h], ax
0x14002e11e  test    ax, ax
0x14002e121  jz      loc_14002E3A3
0x14002e127  mov     cl, [rdi+48h]
0x14002e12a  lea     r8, [rsp+118h+pv]; pv
0x14002e132  mov     al, cl
0x14002e134  xorps   xmm0, xmm0
0x14002e137  neg     al
0x14002e139  mov     edx, 20h ; ' '; c
0x14002e13e  movups  [rsp+118h+pv], xmm0
0x14002e146  sbb     r15d, r15d
0x14002e149  and     r15d, 2000000h
0x14002e150  neg     cl
0x14002e152  mov     rcx, [rdi+20h]; h
0x14002e156  sbb     r12d, r12d
0x14002e159  and     r12d, 80C00000h
0x14002e160  add     r12d, 80000000h
0x14002e167  movups  [rsp+118h+var_48], xmm0
0x14002e16f  call    cs:__imp_GetObjectW
0x14002e175  mov     eax, [rbx+8]
0x14002e178  sub     eax, [rbx]
0x14002e17a  mov     ebp, dword ptr [rsp+118h+pv+4]
0x14002e181  sub     eax, ebp
0x14002e183  mov     r14d, dword ptr [rsp+118h+pv+8]
0x14002e18b  cdq
0x14002e18c  sub     eax, edx
0x14002e18e  sar     eax, 1
0x14002e190  mov     r13d, eax
0x14002e193  mov     eax, [rbx+0Ch]
0x14002e196  sub     eax, [rbx+4]
0x14002e199  add     r13d, [rbx]
0x14002e19c  sub     eax, r14d
0x14002e19f  cdq
0x14002e1a0  mov     [rsp+118h+var_B8.x], r13d
0x14002e1a5  sub     eax, edx
0x14002e1a7  mov     edx, 2; DWORD
0x14002e1ac  sar     eax, 1
0x14002e1ae  add     eax, [rbx+4]
0x14002e1b1  mov     [rsp+118h+var_B8.y], eax
0x14002e1b5  mov     rcx, qword ptr [rsp+118h+var_B8.x]; POINT
0x14002e1ba  mov     [rsp+118h+var_B0], eax
0x14002e1be  call    xMonitorFromPoint
0x14002e1c3  mov     qword ptr [rsp+118h+var_B8.x], rax
0x14002e1c8  lea     rsi, [rdi+44h]
0x14002e1cc  lea     rbx, [rdi+40h]
0x14002e1d0  test    rax, rax
0x14002e1d3  jz      short loc_14002E211
0x14002e1d5  test    rbx, rbx
0x14002e1d8  jz      short loc_14002E211
0x14002e1da  test    rsi, rsi
0x14002e1dd  jz      short loc_14002E211
0x14002e1df  call    ?Initialize@CDpiAwareness@VsUI@@CAXXZ; VsUI::CDpiAwareness::Initialize(void)
0x14002e1e4  mov     rax, cs:?s_pGetDFM@CDpiAwareness@VsUI@@0P6AJPEAUHMONITOR__@@W4_MONITOR_DPI_TYPE@@PEAI2@ZEA; long (*VsUI::CDpiAwareness::s_pGetDFM)(HMONITOR__ *,_MONITOR_DPI_TYPE,uint *,uint *)
0x14002e1eb  test    rax, rax
0x14002e1ee  jnz     short loc_14002E202
0x14002e1f0  mov     eax, cs:?s_DeviceDpiX@CDpiAwareness@VsUI@@0HA; int VsUI::CDpiAwareness::s_DeviceDpiX
0x14002e1f6  mov     [rbx], eax
0x14002e1f8  mov     eax, cs:?s_DeviceDpiY@CDpiAwareness@VsUI@@0HA; int VsUI::CDpiAwareness::s_DeviceDpiY
0x14002e1fe  mov     [rsi], eax
0x14002e200  jmp     short loc_14002E211
0x14002e202  mov     rcx, qword ptr [rsp+118h+var_B8.x]
0x14002e207  mov     r9, rsi
0x14002e20a  mov     r8, rbx
0x14002e20d  xor     edx, edx
0x14002e20f  call    rax ; long (*VsUI::CDpiAwareness::s_pGetDFM)(HMONITOR__ *,_MONITOR_DPI_TYPE,uint *,uint *)
0x14002e211  and     [rsp+118h+lpParam], 0
0x14002e217  lea     rax, _IMM32_NULL_THUNK_DATA; "MZ"
0x14002e21e  movzx   edx, word ptr [rdi+18h]; lpClassName
0x14002e222  lea     ecx, [r15+80h]; dwExStyle
0x14002e229  mov     r8, [rdi+30h]; lpWindowName
0x14002e22d  mov     r9d, r12d; dwStyle
0x14002e230  mov     [rsp+118h+hInstance], rax; hInstance
0x14002e235  and     [rsp+118h+hMenu], 0
0x14002e23b  and     [rsp+118h+hWndParent], 0
0x14002e241  mov     eax, [rsp+118h+var_B0]
0x14002e245  mov     [rsp+118h+nHeight], r14d; nHeight
0x14002e24a  mov     [rsp+118h+nWidth], ebp; nWidth
0x14002e24e  mov     [rsp+118h+Y], eax; Y
0x14002e252  mov     [rsp+118h+X], r13d; X
0x14002e257  call    cs:__imp_CreateWindowExW
0x14002e25d  xor     r13d, r13d
0x14002e260  mov     [rdi+8], rax
0x14002e264  test    rax, rax
0x14002e267  jz      loc_14002E3A3
0x14002e26d  cmp     [rdi+48h], r13b
0x14002e271  jz      loc_14002E316
0x14002e277  mov     edx, [rbx]; nNumerator
0x14002e279  lea     r12d, [r13+60h]
0x14002e27d  lea     r15d, [r13+1Ch]
0x14002e281  mov     r8d, r12d; nDenominator
0x14002e284  mov     ecx, r15d; nNumber
0x14002e287  call    cs:__imp_MulDiv
0x14002e28d  mov     edx, [rsi]; nNumerator
0x14002e28f  mov     r8d, r12d; nDenominator
0x14002e292  mov     ecx, r15d; nNumber
0x14002e295  mov     ebx, eax
0x14002e297  call    cs:__imp_MulDiv
0x14002e29d  mov     [rsp+118h+lpParam], r13; lpParam
0x14002e2a2  lea     rcx, _IMM32_NULL_THUNK_DATA; "MZ"
0x14002e2a9  mov     [rsp+118h+hInstance], rcx; hInstance
0x14002e2ae  lea     r8, WindowName; lpWindowName
0x14002e2b5  mov     rcx, [rdi+8]
0x14002e2b9  mov     edx, ebp
0x14002e2bb  mov     [rsp+118h+hMenu], 64h ; 'd'; hMenu
0x14002e2c4  sub     edx, ebx
0x14002e2c6  mov     [rsp+118h+hWndParent], rcx; hWndParent
0x14002e2cb  sub     edx, 2
0x14002e2ce  mov     [rsp+118h+nHeight], eax; nHeight
0x14002e2d2  mov     r9d, 50000000h; dwStyle
0x14002e2d8  mov     [rsp+118h+nWidth], ebx; nWidth
0x14002e2dc  xor     ecx, ecx; dwExStyle
0x14002e2de  mov     [rsp+118h+Y], 1; Y
0x14002e2e6  mov     [rsp+118h+X], edx; X
0x14002e2ea  lea     rdx, ClassName; "BUTTON"
0x14002e2f1  call    cs:__imp_CreateWindowExW
0x14002e2f7  mov     [rdi+10h], rax
0x14002e2fb  test    rax, rax
0x14002e2fe  jz      short loc_14002E316
0x14002e300  xor     r9d, r9d; dwRefData
0x14002e303  lea     rdx, ?ButtonWndProc@SplashWindow@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x14002e30a  xor     r8d, r8d; uIdSubclass
0x14002e30d  mov     rcx, rax; hWnd
0x14002e310  call    cs:__imp_SetWindowSubclass
0x14002e316  mov     al, [rdi+48h]
0x14002e319  lea     r8, WindowName; lpWindowName
0x14002e320  mov     [rsp+118h+lpParam], r13; lpParam
0x14002e325  lea     rdx, aStatic; "STATIC"
0x14002e32c  neg     al
0x14002e32e  mov     r9d, 5000000Eh; dwStyle
0x14002e334  lea     rax, _IMM32_NULL_THUNK_DATA; "MZ"
0x14002e33b  mov     [rsp+118h+hInstance], rax; hInstance
0x14002e340  sbb     ecx, ecx
0x14002e342  mov     rax, [rdi+8]
0x14002e346  mov     [rsp+118h+hMenu], r13; hMenu
0x14002e34b  mov     [rsp+118h+hWndParent], rax; hWndParent
0x14002e350  mov     [rsp+118h+nHeight], r14d; nHeight
0x14002e355  mov     [rsp+118h+nWidth], ebp; nWidth
0x14002e359  mov     [rsp+118h+Y], r13d; Y
0x14002e35e  mov     [rsp+118h+X], ecx; X
0x14002e362  xor     ecx, ecx; dwExStyle
0x14002e364  call    cs:__imp_CreateWindowExW
0x14002e36a  test    rax, rax
0x14002e36d  jz      short loc_14002E3A3
0x14002e36f  mov     r9, [rdi+20h]; lParam
0x14002e373  xor     r8d, r8d; wParam
0x14002e376  mov     edx, 172h; Msg
0x14002e37b  mov     rcx, rax; hWnd
0x14002e37e  call    cs:__imp_SendMessageW
0x14002e384  mov     rcx, [rdi+8]; HWND
0x14002e388  xor     edx, edx; HIMC
0x14002e38a  call    cs:__imp_ImmAssociateContext
0x14002e390  mov     rcx, [rdi+8]; hWnd
0x14002e394  mov     edx, 5; nCmdShow
0x14002e399  call    cs:__imp_ShowWindow
0x14002e39f  mov     al, 1
0x14002e3a1  jmp     short loc_14002E3A5
0x14002e3a3  xor     al, al
0x14002e3a5  mov     rcx, [rsp+118h+var_38]
0x14002e3ad  xor     rcx, rsp; StackCookie
0x14002e3b0  call    __security_check_cookie
0x14002e3b5  lea     r11, [rsp+118h+var_28]
0x14002e3bd  mov     rbx, [r11+30h]
0x14002e3c1  mov     rbp, [r11+40h]
0x14002e3c5  mov     rsi, [r11+48h]
0x14002e3c9  mov     rsp, r11
0x14002e3cc  pop     r15
0x14002e3ce  pop     r14
0x14002e3d0  pop     r13
0x14002e3d2  pop     r12
0x14002e3d4  pop     rdi
0x14002e3d5  retn
```
