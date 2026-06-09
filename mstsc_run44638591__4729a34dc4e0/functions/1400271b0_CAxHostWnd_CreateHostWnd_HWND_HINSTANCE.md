# CAxHostWnd::CreateHostWnd(HWND__ *,HINSTANCE__ *)

- ea: `0x1400271b0`
- end: `0x14002740a`
- name: `?CreateHostWnd@CAxHostWnd@@QEAAHPEAUHWND__@@PEAUHINSTANCE__@@@Z`
- size: `602`
- prototype: `__int64 __fastcall(LONG_PTR dwNewLong, HWND hWndParent, HINSTANCE hInstance)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400128d0`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x1400271b0`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `USER32!ShowWindow` at `0x14002739e`
- `USER32!ShowWindow` at `0x14002739e`
- `USER32!GetClientRect` at `0x1400272dd`
- `USER32!GetClientRect` at `0x1400272dd`
- `USER32!LoadCursorW` at `0x14002721d`
- `USER32!LoadCursorW` at `0x14002721d`
- `USER32!SetWindowLongPtrW` at `0x140027347`
- `USER32!SetWindowLongPtrW` at `0x140027347`
- `USER32!RegisterClassExW` at `0x140027255`
- `USER32!RegisterClassExW` at `0x140027255`
- `USER32!CreateWindowExW` at `0x14002732d`
- `USER32!CreateWindowExW` at `0x14002732d`
- `KERNEL32!GetLastError` at `0x1400271e9`
- `KERNEL32!GetLastError` at `0x140027262`
- `KERNEL32!GetLastError` at `0x14002729a`
- `KERNEL32!GetLastError` at `0x1400271e9`
- `KERNEL32!GetLastError` at `0x140027262`
- `KERNEL32!GetLastError` at `0x14002729a`
- `GDI32!GetStockObject` at `0x14002722c`
- `GDI32!GetStockObject` at `0x14002722c`

## pseudocode

```c
__int64 __fastcall CAxHostWnd::CreateHostWnd(LONG_PTR dwNewLong, HWND hWndParent, HINSTANCE hInstance)
{
  HBRUSH StockObject; // rax
  DWORD LastError; // ebx
  unsigned int v8; // eax
  HWND Window; // rax
  __int64 v10; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  WNDCLASSEXW v13; // [rsp+60h] [rbp-39h] BYREF
  struct tagRECT Rect; // [rsp+B0h] [rbp+17h] BYREF

  memset_0(&v13, 0, sizeof(v13));
  GetLastError();
  *(_QWORD *)&v13.cbSize = 80;
  v13.lpfnWndProc = (WNDPROC)CAxHostWnd::StaticAxHostWndProc;
  *(_QWORD *)&v13.cbClsExtra = 0;
  v13.hInstance = hInstance;
  v13.hIcon = 0;
  v13.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  StockObject = (HBRUSH)GetStockObject(5);
  v13.lpszMenuName = 0;
  v13.hbrBackground = StockObject;
  v13.lpszClassName = L"TscShellAxHostClass";
  v13.hIconSm = 0;
  if ( RegisterClassExW(&v13) || GetLastError() == 1410 )
  {
    Rect = 0;
    GetClientRect(hWndParent, &Rect);
    Window = CreateWindowExW(
               0,
               L"TscShellAxHostClass",
               0,
               0x46000000u,
               0,
               0,
               Rect.right - Rect.left,
               Rect.bottom - Rect.top,
               hWndParent,
               0,
               hInstance,
               (LPVOID)dwNewLong);
    *(_QWORD *)(dwNewLong + 16) = Window;
    if ( Window )
    {
      SetWindowLongPtrW(Window, -21, dwNewLong);
      v10 = *(_QWORD *)(dwNewLong + 64);
      if ( v10 )
        *(_QWORD *)(v10 + 24) = *(_QWORD *)(dwNewLong + 16);
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, struct tagRECT *))(**(_QWORD **)(dwNewLong + 72) + 88LL))(
             *(_QWORD *)(dwNewLong + 72),
             0,
             0,
             *(_QWORD *)(dwNewLong + 56),
             0,
             *(_QWORD *)(dwNewLong + 16),
             &Rect) >= 0 )
      {
        ShowWindow(*(HWND *)(dwNewLong + 16), 1);
        return 1;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_397b24202ccc35f6d1972e544a06c8d6_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_397b24202ccc35f6d1972e544a06c8d6_Traceguids, v8, LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x1400271b0  push    rbp
0x1400271b2  push    rbx
0x1400271b3  push    rsi
0x1400271b4  push    rdi
0x1400271b5  push    r15
0x1400271b7  lea     rbp, [rsp-37h]
0x1400271bc  sub     rsp, 0D0h
0x1400271c3  mov     rax, cs:__security_cookie
0x1400271ca  xor     rax, rsp
0x1400271cd  mov     [rbp+57h+var_30], rax
0x1400271d1  mov     rdi, rdx
0x1400271d4  mov     rsi, r8
0x1400271d7  xor     edx, edx; Val
0x1400271d9  mov     rbx, rcx
0x1400271dc  lea     rcx, [rbp+57h+var_90]; void *
0x1400271e0  lea     r8d, [rdx+50h]; Size
0x1400271e4  call    memset_0
0x1400271e9  call    cs:__imp_GetLastError
0x1400271ef  lea     rax, ?StaticAxHostWndProc@CAxHostWnd@@SA_JPEAUHWND__@@I_K_J@Z; CAxHostWnd::StaticAxHostWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1400271f6  mov     qword ptr [rbp+57h+var_90.cbSize], 50h ; 'P'
0x1400271fe  mov     edx, 7F00h; lpCursorName
0x140027203  mov     [rbp+57h+var_90.lpfnWndProc], rax
0x140027207  xor     ecx, ecx; hInstance
0x140027209  mov     qword ptr [rbp+57h+var_90.cbClsExtra], 0
0x140027211  mov     [rbp+57h+var_90.hInstance], rsi
0x140027215  mov     [rbp+57h+var_90.hIcon], 0
0x14002721d  call    cs:__imp_LoadCursorW
0x140027223  mov     ecx, 5; i
0x140027228  mov     [rbp+57h+var_90.hCursor], rax
0x14002722c  call    cs:__imp_GetStockObject
0x140027232  lea     r15, aTscshellaxhost; "TscShellAxHostClass"
0x140027239  mov     [rbp+57h+var_90.lpszMenuName], 0
0x140027241  lea     rcx, [rbp+57h+var_90]; WNDCLASSEXW *
0x140027245  mov     [rbp+57h+var_90.hbrBackground], rax
0x140027249  mov     [rbp+57h+var_90.lpszClassName], r15
0x14002724d  mov     [rbp+57h+var_90.hIconSm], 0
0x140027255  call    cs:__imp_RegisterClassExW
0x14002725b  xor     ecx, ecx
0x14002725d  cmp     cx, ax
0x140027260  jnz     short loc_1400272CF
0x140027262  call    cs:__imp_GetLastError
0x140027268  cmp     eax, 582h
0x14002726d  jz      short loc_1400272CF
0x14002726f  mov     rax, cs:WPP_GLOBAL_Control
0x140027276  lea     rcx, WPP_GLOBAL_Control
0x14002727d  cmp     rax, rcx
0x140027280  jz      loc_1400273EE
0x140027286  test    byte ptr [rax+1Ch], 1
0x14002728a  jz      loc_1400273EE
0x140027290  cmp     byte ptr [rax+19h], 2
0x140027294  jb      loc_1400273EE
0x14002729a  call    cs:__imp_GetLastError
0x1400272a0  mov     ebx, eax
0x1400272a2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400272a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400272ae  lea     r8, WPP_397b24202ccc35f6d1972e544a06c8d6_Traceguids
0x1400272b5  mov     edx, 0Ah
0x1400272ba  mov     [rsp+0F0h+X], ebx
0x1400272be  mov     r9d, eax
0x1400272c1  mov     rcx, [rcx+10h]
0x1400272c5  call    WPP_SF_Dd
0x1400272ca  jmp     loc_1400273EE
0x1400272cf  xorps   xmm0, xmm0
0x1400272d2  lea     rdx, [rbp+57h+Rect]; lpRect
0x1400272d6  mov     rcx, rdi; hWnd
0x1400272d9  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x1400272dd  call    cs:__imp_GetClientRect
0x1400272e3  mov     ecx, [rbp+57h+Rect.bottom]
0x1400272e6  mov     r9d, 46000000h; dwStyle
0x1400272ec  sub     ecx, [rbp+57h+Rect.top]
0x1400272ef  xor     r8d, r8d; lpWindowName
0x1400272f2  mov     eax, [rbp+57h+Rect.right]
0x1400272f5  mov     rdx, r15; lpClassName
0x1400272f8  sub     eax, [rbp+57h+Rect.left]
0x1400272fb  mov     [rsp+0F0h+lpParam], rbx; lpParam
0x140027300  mov     [rsp+0F0h+hInstance], rsi; hInstance
0x140027305  mov     [rsp+0F0h+hMenu], 0; hMenu
0x14002730e  mov     [rsp+0F0h+hWndParent], rdi; hWndParent
0x140027313  mov     [rsp+0F0h+nHeight], ecx; nHeight
0x140027317  xor     ecx, ecx; dwExStyle
0x140027319  mov     [rsp+0F0h+nWidth], eax; nWidth
0x14002731d  mov     [rsp+0F0h+Y], 0; Y
0x140027325  mov     [rsp+0F0h+X], 0; X
0x14002732d  call    cs:__imp_CreateWindowExW
0x140027333  mov     [rbx+10h], rax
0x140027337  test    rax, rax
0x14002733a  jz      short loc_1400273AB
0x14002733c  mov     r8, rbx; dwNewLong
0x14002733f  mov     edx, 0FFFFFFEBh; nIndex
0x140027344  mov     rcx, rax; hWnd
0x140027347  call    cs:__imp_SetWindowLongPtrW
0x14002734d  mov     rcx, [rbx+40h]
0x140027351  test    rcx, rcx
0x140027354  jz      short loc_14002735E
0x140027356  mov     rax, [rbx+10h]
0x14002735a  mov     [rcx+18h], rax
0x14002735e  mov     rcx, [rbx+48h]
0x140027362  lea     rdx, [rbp+57h+Rect]
0x140027366  mov     r9, [rbx+38h]
0x14002736a  xor     r8d, r8d
0x14002736d  mov     qword ptr [rsp+0F0h+nWidth], rdx
0x140027372  mov     rdx, [rbx+10h]
0x140027376  mov     rax, [rcx]
0x140027379  mov     qword ptr [rsp+0F0h+Y], rdx
0x14002737e  xor     edx, edx
0x140027380  mov     [rsp+0F0h+X], 0
0x140027388  mov     rax, [rax+58h]
0x14002738c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027391  test    eax, eax
0x140027393  js      short loc_1400273EE
0x140027395  mov     rcx, [rbx+10h]; hWnd
0x140027399  mov     edx, 1; nCmdShow
0x14002739e  call    cs:__imp_ShowWindow
0x1400273a4  mov     eax, 1
0x1400273a9  jmp     short loc_1400273F0
0x1400273ab  mov     rax, cs:WPP_GLOBAL_Control
0x1400273b2  lea     rcx, WPP_GLOBAL_Control
0x1400273b9  cmp     rax, rcx
0x1400273bc  jz      short loc_1400273EE
0x1400273be  test    byte ptr [rax+1Ch], 1
0x1400273c2  jz      short loc_1400273EE
0x1400273c4  cmp     byte ptr [rax+19h], 2
0x1400273c8  jb      short loc_1400273EE
0x1400273ca  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400273cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400273d6  lea     r8, WPP_397b24202ccc35f6d1972e544a06c8d6_Traceguids
0x1400273dd  mov     edx, 0Bh
0x1400273e2  mov     r9d, eax
0x1400273e5  mov     rcx, [rcx+10h]
0x1400273e9  call    WPP_SF_d
0x1400273ee  xor     eax, eax
0x1400273f0  mov     rcx, [rbp+57h+var_30]
0x1400273f4  xor     rcx, rsp; StackCookie
0x1400273f7  call    __security_check_cookie
0x1400273fc  add     rsp, 0D0h
0x140027403  pop     r15
0x140027405  pop     rdi
0x140027406  pop     rsi
0x140027407  pop     rbx
0x140027408  pop     rbp
0x140027409  retn
```
