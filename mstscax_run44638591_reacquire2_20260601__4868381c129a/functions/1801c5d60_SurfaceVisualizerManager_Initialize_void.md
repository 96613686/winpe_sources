# SurfaceVisualizerManager::Initialize(void)

- ea: `0x1801c5d60`
- end: `0x1801c612e`
- name: `?Initialize@SurfaceVisualizerManager@@EEAAJXZ`
- size: `974`
- prototype: `__int64 __fastcall(SurfaceVisualizerManager *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800172ec`
- `0x180039c98`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x1801c5d60`
- `0x180688f3e`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x1801c5e9f`
- `USER32!GetWindowLongPtrW` at `0x1801c5f56`
- `USER32!GetWindowLongPtrW` at `0x1801c6011`
- `USER32!GetWindowLongPtrW` at `0x1801c5e9f`
- `USER32!GetWindowLongPtrW` at `0x1801c5f56`
- `USER32!GetWindowLongPtrW` at `0x1801c6011`
- `USER32!LoadCursorW` at `0x1801c5da3`
- `USER32!LoadCursorW` at `0x1801c5da3`
- `USER32!CreateWindowExW` at `0x1801c5e1b`
- `USER32!CreateWindowExW` at `0x1801c5ef5`
- `USER32!CreateWindowExW` at `0x1801c5fb0`
- `USER32!CreateWindowExW` at `0x1801c606a`
- `USER32!CreateWindowExW` at `0x1801c5e1b`
- `USER32!CreateWindowExW` at `0x1801c5ef5`
- `USER32!CreateWindowExW` at `0x1801c5fb0`
- `USER32!CreateWindowExW` at `0x1801c606a`
- `USER32!RegisterClassExW` at `0x1801c5dc5`
- `USER32!RegisterClassExW` at `0x1801c5dc5`

## string_xrefs

- `0x1801c5e64`: `Create m_hwnd failed`
- `0x1801c5f41`: `Create m_hwndSurfaceList failed`
- `0x1801c5ffc`: `Create m_hwndButtonTogglePause failed`
- `0x1801c60ae`: `Create m_hwndButtonSingleStep failed`

## pseudocode

```c
__int64 __fastcall SurfaceVisualizerManager::Initialize(SurfaceVisualizerManager *this)
{
  HWND Window; // rax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  int v5; // edx
  const char *v6; // rcx
  HINSTANCE hInstance; // rax
  HWND v8; // rax
  HINSTANCE WindowLongPtrW; // rax
  HWND v10; // rax
  HINSTANCE v11; // rax
  HWND v12; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  WNDCLASSEXW v15; // [rsp+60h] [rbp-58h] BYREF

  v15.cbSize = 80;
  memset_0(&v15.style, 0, 0x4Cu);
  v15.cbWndExtra = 8;
  v15.lpfnWndProc = (WNDPROC)SurfaceVisualizerManager::WndProc;
  v15.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  v15.lpszClassName = L"SurfaceVisualizerManager";
  RegisterClassExW(&v15);
  Window = CreateWindowExW(
             0,
             L"SurfaceVisualizerManager",
             L"RDP Debug Visualizer Surface Selector",
             0,
             0x80000000,
             0x80000000,
             400,
             450,
             0,
             0,
             0,
             (char *)this - 8);
  *((_QWORD *)this + 15) = Window;
  if ( Window )
  {
    hInstance = (HINSTANCE)GetWindowLongPtrW(Window, -6);
    v8 = CreateWindowExW(
           0,
           L"ListBox",
           &sourceString,
           0x50210001u,
           10,
           10,
           350,
           350,
           *((HWND *)this + 15),
           0,
           hInstance,
           0);
    *((_QWORD *)this + 16) = v8;
    if ( v8 )
    {
      WindowLongPtrW = (HINSTANCE)GetWindowLongPtrW(*((HWND *)this + 15), -6);
      v10 = CreateWindowExW(
              0,
              L"Button",
              L"Pause/Play",
              0x50010000u,
              10,
              360,
              100,
              40,
              *((HWND *)this + 15),
              0,
              WindowLongPtrW,
              0);
      *((_QWORD *)this + 17) = v10;
      if ( v10 )
      {
        v11 = (HINSTANCE)GetWindowLongPtrW(*((HWND *)this + 15), -6);
        v12 = CreateWindowExW(
                0,
                L"Button",
                L"Single Step",
                0x50010000u,
                120,
                360,
                100,
                40,
                *((HWND *)this + 15),
                0,
                v11,
                0);
        *((_QWORD *)this + 18) = v12;
        if ( v12 )
        {
          *((_DWORD *)this + 5) |= 2u;
          v3 = 0;
          if ( !(unsigned int)CTSCriticalSection::Initialize((SurfaceVisualizerManager *)((char *)this + 48)) )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                18,
                WPP_4d5a5627f3d8365be3708374c27c1cec_Traceguids,
                CurrentThreadActivityIdPrefix,
                -2147467259);
            }
            return (unsigned int)-2147467259;
          }
        }
        else
        {
          v3 = -2147467259;
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v4 = RdpWppGetCurrentThreadActivityIdPrefix();
            v5 = 17;
            v6 = "Create m_hwndButtonSingleStep failed";
            goto LABEL_6;
          }
        }
      }
      else
      {
        v3 = -2147467259;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v4 = RdpWppGetCurrentThreadActivityIdPrefix();
          v5 = 16;
          v6 = "Create m_hwndButtonTogglePause failed";
          goto LABEL_6;
        }
      }
    }
    else
    {
      v3 = -2147467259;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v4 = RdpWppGetCurrentThreadActivityIdPrefix();
        v5 = 15;
        v6 = "Create m_hwndSurfaceList failed";
        goto LABEL_6;
      }
    }
  }
  else
  {
    v3 = -2147467259;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpWppGetCurrentThreadActivityIdPrefix();
      v5 = 14;
      v6 = "Create m_hwnd failed";
LABEL_6:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        (unsigned int)WPP_4d5a5627f3d8365be3708374c27c1cec_Traceguids,
        v4,
        (__int64)v6,
        5);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1801c5d60  mov     [rsp+arg_0], rbx
0x1801c5d65  push    rdi
0x1801c5d66  sub     rsp, 0B0h
0x1801c5d6d  xor     edx, edx; Val
0x1801c5d6f  mov     [rsp+0B8h+var_58.cbSize], 50h ; 'P'
0x1801c5d77  mov     rdi, rcx
0x1801c5d7a  lea     rcx, [rsp+0B8h+var_58.style]; void *
0x1801c5d7f  lea     r8d, [rdx+4Ch]; Size
0x1801c5d83  call    memset_0
0x1801c5d88  lea     rax, ?WndProc@SurfaceVisualizerManager@@CA_JPEAUHWND__@@I_K_J@Z; SurfaceVisualizerManager::WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1801c5d8f  mov     [rsp+0B8h+var_58.cbWndExtra], 8
0x1801c5d97  mov     edx, 7F00h; lpCursorName
0x1801c5d9c  mov     [rsp+0B8h+var_58.lpfnWndProc], rax
0x1801c5da1  xor     ecx, ecx; hInstance
0x1801c5da3  call    cs:__imp_LoadCursorW
0x1801c5da9  lea     rbx, aSurfacevisuali_1; "SurfaceVisualizerManager"
0x1801c5db0  mov     [rsp+0B8h+var_58.hCursor], rax
0x1801c5db8  lea     rcx, [rsp+0B8h+var_58]; WNDCLASSEXW *
0x1801c5dbd  mov     [rsp+0B8h+var_58.lpszClassName], rbx
0x1801c5dc5  call    cs:__imp_RegisterClassExW
0x1801c5dcb  lea     rax, [rdi-8]
0x1801c5dcf  xor     r9d, r9d; dwStyle
0x1801c5dd2  mov     [rsp+0B8h+lpParam], rax; lpParam
0x1801c5dd7  lea     r8, aRdpDebugVisual; "RDP Debug Visualizer Surface Selector"
0x1801c5dde  mov     [rsp+0B8h+hInstance], 0; hInstance
0x1801c5de7  mov     eax, 80000000h
0x1801c5dec  mov     [rsp+0B8h+hMenu], 0; hMenu
0x1801c5df5  mov     rdx, rbx; lpClassName
0x1801c5df8  mov     [rsp+0B8h+hWndParent], 0; hWndParent
0x1801c5e01  xor     ecx, ecx; dwExStyle
0x1801c5e03  mov     [rsp+0B8h+nHeight], 1C2h; nHeight
0x1801c5e0b  mov     [rsp+0B8h+nWidth], 190h; nWidth
0x1801c5e13  mov     [rsp+0B8h+Y], eax; Y
0x1801c5e17  mov     [rsp+0B8h+X], eax; X
0x1801c5e1b  call    cs:__imp_CreateWindowExW
0x1801c5e21  mov     [rdi+78h], rax
0x1801c5e25  test    rax, rax
0x1801c5e28  jnz     short loc_1801C5E97
0x1801c5e2a  mov     ebx, 80004005h
0x1801c5e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5e36  lea     rax, WPP_GLOBAL_Control
0x1801c5e3d  cmp     rcx, rax
0x1801c5e40  jz      loc_1801C611B
0x1801c5e46  test    byte ptr [rcx+1Ch], 8
0x1801c5e4a  jz      loc_1801C611B
0x1801c5e50  cmp     byte ptr [rcx+19h], 2
0x1801c5e54  jb      loc_1801C611B
0x1801c5e5a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801c5e5f  mov     edx, 0Eh
0x1801c5e64  lea     rcx, aCreateMHwndFai; "Create m_hwnd failed"
0x1801c5e6b  mov     [rsp+0B8h+Y], 80004005h
0x1801c5e73  lea     r8, WPP_4d5a5627f3d8365be3708374c27c1cec_Traceguids
0x1801c5e7a  mov     qword ptr [rsp+0B8h+X], rcx
0x1801c5e7f  mov     r9d, eax
0x1801c5e82  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5e89  mov     rcx, [rcx+10h]
0x1801c5e8d  call    WPP_SF_DsD
0x1801c5e92  jmp     loc_1801C611B
0x1801c5e97  mov     edx, 0FFFFFFFAh; nIndex
0x1801c5e9c  mov     rcx, rax; hWnd
0x1801c5e9f  call    cs:__imp_GetWindowLongPtrW
0x1801c5ea5  mov     [rsp+0B8h+lpParam], 0; lpParam
0x1801c5eae  lea     r8, sourceString; lpWindowName
0x1801c5eb5  mov     [rsp+0B8h+hInstance], rax; hInstance
0x1801c5eba  lea     rdx, aListbox; "ListBox"
0x1801c5ec1  mov     rax, [rdi+78h]
0x1801c5ec5  mov     ebx, 0Ah
0x1801c5eca  mov     [rsp+0B8h+hMenu], 0; hMenu
0x1801c5ed3  mov     r9d, 50210001h; dwStyle
0x1801c5ed9  mov     [rsp+0B8h+hWndParent], rax; hWndParent
0x1801c5ede  xor     ecx, ecx; dwExStyle
0x1801c5ee0  mov     eax, 15Eh
0x1801c5ee5  mov     [rsp+0B8h+nHeight], eax; nHeight
0x1801c5ee9  mov     [rsp+0B8h+nWidth], eax; nWidth
0x1801c5eed  mov     [rsp+0B8h+Y], ebx; Y
0x1801c5ef1  mov     [rsp+0B8h+X], ebx; X
0x1801c5ef5  call    cs:__imp_CreateWindowExW
0x1801c5efb  mov     [rdi+80h], rax
0x1801c5f02  test    rax, rax
0x1801c5f05  jnz     short loc_1801C5F4D
0x1801c5f07  mov     ebx, 80004005h
0x1801c5f0c  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5f13  lea     rax, WPP_GLOBAL_Control
0x1801c5f1a  cmp     rcx, rax
0x1801c5f1d  jz      loc_1801C611B
0x1801c5f23  test    byte ptr [rcx+1Ch], 8
0x1801c5f27  jz      loc_1801C611B
0x1801c5f2d  cmp     byte ptr [rcx+19h], 2
0x1801c5f31  jb      loc_1801C611B
0x1801c5f37  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801c5f3c  mov     edx, 0Fh
0x1801c5f41  lea     rcx, aCreateMHwndsur; "Create m_hwndSurfaceList failed"
0x1801c5f48  jmp     loc_1801C5E6B
0x1801c5f4d  mov     rcx, [rdi+78h]; hWnd
0x1801c5f51  mov     edx, 0FFFFFFFAh; nIndex
0x1801c5f56  call    cs:__imp_GetWindowLongPtrW
0x1801c5f5c  mov     [rsp+0B8h+lpParam], 0; lpParam
0x1801c5f65  lea     r8, aPausePlay; "Pause/Play"
0x1801c5f6c  mov     [rsp+0B8h+hInstance], rax; hInstance
0x1801c5f71  lea     rdx, aButton_0; "Button"
0x1801c5f78  mov     rax, [rdi+78h]
0x1801c5f7c  xor     ecx, ecx; dwExStyle
0x1801c5f7e  mov     [rsp+0B8h+hMenu], 0; hMenu
0x1801c5f87  mov     [rsp+0B8h+hWndParent], rax; hWndParent
0x1801c5f8c  mov     [rsp+0B8h+nHeight], 28h ; '('; nHeight
0x1801c5f94  mov     [rsp+0B8h+nWidth], 64h ; 'd'; nWidth
0x1801c5f9c  mov     [rsp+0B8h+Y], 168h; Y
0x1801c5fa4  mov     [rsp+0B8h+X], ebx; X
0x1801c5fa8  mov     ebx, 50010000h
0x1801c5fad  mov     r9d, ebx; dwStyle
0x1801c5fb0  call    cs:__imp_CreateWindowExW
0x1801c5fb6  mov     [rdi+88h], rax
0x1801c5fbd  test    rax, rax
0x1801c5fc0  jnz     short loc_1801C6008
0x1801c5fc2  mov     ebx, 80004005h
0x1801c5fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c5fce  lea     rax, WPP_GLOBAL_Control
0x1801c5fd5  cmp     rcx, rax
0x1801c5fd8  jz      loc_1801C611B
0x1801c5fde  test    byte ptr [rcx+1Ch], 8
0x1801c5fe2  jz      loc_1801C611B
0x1801c5fe8  cmp     byte ptr [rcx+19h], 2
0x1801c5fec  jb      loc_1801C611B
0x1801c5ff2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801c5ff7  mov     edx, 10h
0x1801c5ffc  lea     rcx, aCreateMHwndbut; "Create m_hwndButtonTogglePause failed"
0x1801c6003  jmp     loc_1801C5E6B
0x1801c6008  mov     rcx, [rdi+78h]; hWnd
0x1801c600c  mov     edx, 0FFFFFFFAh; nIndex
0x1801c6011  call    cs:__imp_GetWindowLongPtrW
0x1801c6017  mov     [rsp+0B8h+lpParam], 0; lpParam
0x1801c6020  lea     r8, aSingleStep; "Single Step"
0x1801c6027  mov     [rsp+0B8h+hInstance], rax; hInstance
0x1801c602c  lea     rdx, aButton_0; "Button"
0x1801c6033  mov     rax, [rdi+78h]
0x1801c6037  mov     r9d, ebx; dwStyle
0x1801c603a  mov     [rsp+0B8h+hMenu], 0; hMenu
0x1801c6043  xor     ecx, ecx; dwExStyle
0x1801c6045  mov     [rsp+0B8h+hWndParent], rax; hWndParent
0x1801c604a  mov     [rsp+0B8h+nHeight], 28h ; '('; nHeight
0x1801c6052  mov     [rsp+0B8h+nWidth], 64h ; 'd'; nWidth
0x1801c605a  mov     [rsp+0B8h+Y], 168h; Y
0x1801c6062  mov     [rsp+0B8h+X], 78h ; 'x'; X
0x1801c606a  call    cs:__imp_CreateWindowExW
0x1801c6070  mov     [rdi+90h], rax
0x1801c6077  test    rax, rax
0x1801c607a  jnz     short loc_1801C60BA
0x1801c607c  mov     ebx, 80004005h
0x1801c6081  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c6088  lea     rax, WPP_GLOBAL_Control
0x1801c608f  cmp     rcx, rax
0x1801c6092  jz      loc_1801C611B
0x1801c6098  test    byte ptr [rcx+1Ch], 8
0x1801c609c  jz      short loc_1801C611B
0x1801c609e  cmp     byte ptr [rcx+19h], 2
0x1801c60a2  jb      short loc_1801C611B
0x1801c60a4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801c60a9  mov     edx, 11h
0x1801c60ae  lea     rcx, aCreateMHwndbut_0; "Create m_hwndButtonSingleStep failed"
0x1801c60b5  jmp     loc_1801C5E6B
0x1801c60ba  or      dword ptr [rdi+14h], 2
0x1801c60be  lea     rcx, [rdi+30h]; this
0x1801c60c2  xor     ebx, ebx
0x1801c60c4  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1801c60c9  test    eax, eax
0x1801c60cb  jnz     short loc_1801C611B
0x1801c60cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c60d4  lea     rax, WPP_GLOBAL_Control
0x1801c60db  cmp     rcx, rax
0x1801c60de  jz      short loc_1801C6116
0x1801c60e0  test    byte ptr [rcx+1Ch], 8
0x1801c60e4  jz      short loc_1801C6116
0x1801c60e6  cmp     byte ptr [rcx+19h], 2
0x1801c60ea  jb      short loc_1801C6116
0x1801c60ec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801c60f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c60f8  lea     edx, [rbx+12h]
0x1801c60fb  mov     r9d, eax
0x1801c60fe  mov     [rsp+0B8h+X], 80004005h
0x1801c6106  lea     r8, WPP_4d5a5627f3d8365be3708374c27c1cec_Traceguids
0x1801c610d  mov     rcx, [rcx+10h]
0x1801c6111  call    WPP_SF_Dd
0x1801c6116  mov     ebx, 80004005h
0x1801c611b  mov     eax, ebx
0x1801c611d  mov     rbx, [rsp+0B8h+arg_0]
0x1801c6125  add     rsp, 0B0h
0x1801c612c  pop     rdi
0x1801c612d  retn
```
