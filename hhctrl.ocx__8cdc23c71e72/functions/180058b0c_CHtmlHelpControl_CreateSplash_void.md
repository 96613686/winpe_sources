# CHtmlHelpControl::CreateSplash(void)

- ea: `0x180058b0c`
- end: `0x180058df5`
- name: `?CreateSplash@CHtmlHelpControl@@QEAAXXZ`
- size: `745`
- prototype: `void __fastcall(CHtmlHelpControl *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002efa0`

## callees

- `0x180005a4c`
- `0x180006708`
- `0x180011490`
- `0x1800229a4`
- `0x18002fb58`
- `0x18004f65c`
- `0x180058b0c`
- `0x180065438`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `USER32!LoadImageA` at `0x180058bfe`
- `USER32!LoadImageA` at `0x180058bfe`
- `USER32!SetTimer` at `0x180058dd0`
- `USER32!SetTimer` at `0x180058dd0`
- `USER32!GetWindowLongA` at `0x180058cd6`
- `USER32!GetWindowLongA` at `0x180058cd6`
- `USER32!GetWindowRect` at `0x180058ce9`
- `USER32!GetWindowRect` at `0x180058ce9`
- `USER32!GetParent` at `0x180058ca1`
- `USER32!GetParent` at `0x180058cb8`
- `USER32!GetParent` at `0x180058ca1`
- `USER32!GetParent` at `0x180058cb8`
- `USER32!LoadCursorA` at `0x180058c68`
- `USER32!LoadCursorA` at `0x180058c68`
- `GDI32!GetObjectA` at `0x180058c23`
- `GDI32!GetObjectA` at `0x180058c23`
- `GDI32!DeleteDC` at `0x180058b90`
- `GDI32!DeleteDC` at `0x180058b90`
- `GDI32!CreateICA` at `0x180058b6d`
- `GDI32!CreateICA` at `0x180058b6d`
- `GDI32!GetDeviceCaps` at `0x180058b82`
- `GDI32!GetDeviceCaps` at `0x180058b82`

## pseudocode

```c
void __fastcall CHtmlHelpControl::CreateSplash(CHtmlHelpControl *this)
{
  __int64 v1; // rax
  int v3; // eax
  HDC ICA; // rax
  HDC v5; // rbx
  HINSTANCE ResourceInstance; // rax
  HBITMAP ImageA; // rax
  HCURSOR CursorA; // rax
  HWND v9; // rcx
  HWND Parent; // rdi
  HWND i; // rcx
  HWND v12; // rbx
  HWND v13; // r10
  __int64 v14; // rcx
  UINT v15; // eax
  WNDCLASSA WndClass; // [rsp+60h] [rbp-A0h] BYREF
  struct tagRECT Rect; // [rsp+B0h] [rbp-50h] BYREF
  CHAR name[272]; // [rsp+C0h] [rbp-40h] BYREF

  v1 = *((_QWORD *)this + 63);
  if ( v1 )
  {
    v3 = *(_DWORD *)(v1 + 32) - 1;
    if ( v3 >= 1 )
    {
      if ( v3 > 2 )
      {
        ICA = CreateICA("DISPLAY", 0, 0, 0);
        v5 = ICA;
        if ( ICA )
        {
          if ( GetDeviceCaps(ICA, 12) <= 8 )
            DeleteDC(v5);
        }
      }
      if ( (unsigned int)CHtmlHelpControl::ConvertToCacheFile(
                           this,
                           *(const char **)(*(_QWORD *)(*((_QWORD *)this + 63) + 16LL) + 8LL),
                           name,
                           0x104u) )
      {
        if ( !HHStrStrIA(name, ".gif") )
        {
          ResourceInstance = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
          ImageA = (HBITMAP)LoadImageA(ResourceInstance, name, 0, 0, 0, 0x10u);
          g_hbmpSplash = ImageA;
          if ( ImageA )
          {
            GetObjectA(ImageA, 32, byte_18008C360);
            if ( !g_fRegisteredSpash )
            {
              memset_0(&WndClass, 0, sizeof(WndClass));
              WndClass.lpfnWndProc = (WNDPROC)SplashWndProc;
              WndClass.hInstance = hInstance;
              CursorA = LoadCursorA(0, (LPCSTR)0x7F00);
              WndClass.lpszClassName = "Splash";
              WndClass.hCursor = CursorA;
              if ( !(unsigned __int16)IsolationAwareRegisterClassA(&WndClass) )
                return;
              g_fRegisteredSpash = 1;
            }
            v9 = (HWND)*((_QWORD *)this + 28);
            Rect = 0;
            Parent = GetParent(v9);
            for ( i = Parent; (GetWindowLongA(i, -16) & 0x40000000) != 0; i = v12 )
            {
              v12 = GetParent(Parent);
              if ( !(unsigned int)IsValidWindow(v12) )
                break;
              Parent = v12;
            }
            GetWindowRect(Parent, &Rect);
            g_hwndSplash = (HWND)IsolationAwareCreateWindowExA(
                                   8u,
                                   "Splash",
                                   Class,
                                   0x90000000,
                                   Rect.left + (Rect.right - Rect.left) / 2 - dword_18008C364 / 2,
                                   Rect.top + (Rect.bottom - Rect.top) / 2 - cy / 2,
                                   dword_18008C364 + 10,
                                   cy + 10,
                                   0,
                                   0,
                                   hInstance,
                                   0);
            v13 = g_hwndSplash;
            if ( g_hwndSplash )
            {
              v14 = *((_QWORD *)this + 63);
              if ( *(_DWORD *)(v14 + 32) - 1 <= 1 )
                v15 = 2500;
              else
                v15 = Atoi(*(const char **)(*(_QWORD *)(v14 + 16) + 16LL));
              SetTimer(v13, 0x270Fu, v15, 0);
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180058b0c  push    rbp
0x180058b0e  push    rbx
0x180058b0f  push    rsi
0x180058b10  push    rdi
0x180058b11  push    r12
0x180058b13  push    r14
0x180058b15  lea     rbp, [rsp-0E8h]
0x180058b1d  sub     rsp, 1E8h
0x180058b24  mov     rax, cs:__security_cookie
0x180058b2b  xor     rax, rsp
0x180058b2e  mov     [rbp+110h+var_40], rax
0x180058b35  mov     rax, [rcx+1F8h]
0x180058b3c  xor     r14d, r14d
0x180058b3f  mov     rsi, rcx
0x180058b42  test    rax, rax
0x180058b45  jz      loc_180058DD6
0x180058b4b  mov     eax, [rax+20h]
0x180058b4e  dec     eax
0x180058b50  cmp     eax, 1
0x180058b53  jl      loc_180058DD6
0x180058b59  cmp     eax, 2
0x180058b5c  jle     short loc_180058B96
0x180058b5e  xor     r9d, r9d; pdm
0x180058b61  lea     rcx, pszDriver; "DISPLAY"
0x180058b68  xor     r8d, r8d; pszPort
0x180058b6b  xor     edx, edx; pszDevice
0x180058b6d  call    cs:__imp_CreateICA
0x180058b73  mov     rbx, rax
0x180058b76  test    rax, rax
0x180058b79  jz      short loc_180058B96
0x180058b7b  lea     edx, [r14+0Ch]; index
0x180058b7f  mov     rcx, rax; hdc
0x180058b82  call    cs:__imp_GetDeviceCaps
0x180058b88  cmp     eax, 8
0x180058b8b  jg      short loc_180058B96
0x180058b8d  mov     rcx, rbx; hdc
0x180058b90  call    cs:__imp_DeleteDC
0x180058b96  mov     rax, [rsi+1F8h]
0x180058b9d  lea     r8, [rbp+110h+name]; char *
0x180058ba1  mov     r9d, 104h; unsigned __int64
0x180058ba7  mov     rcx, rsi; this
0x180058baa  mov     rdx, [rax+10h]
0x180058bae  mov     rdx, [rdx+8]; char *
0x180058bb2  call    ?ConvertToCacheFile@CHtmlHelpControl@@QEAAHPEBDPEAD_K@Z; CHtmlHelpControl::ConvertToCacheFile(char const *,char *,unsigned __int64)
0x180058bb7  test    eax, eax
0x180058bb9  jz      loc_180058DD6
0x180058bbf  lea     rdx, aGif; ".gif"
0x180058bc6  lea     rcx, [rbp+110h+name]; pszStart
0x180058bca  call    HHStrStrIA
0x180058bcf  test    rax, rax
0x180058bd2  jnz     loc_180058DD6
0x180058bd8  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x180058bdf  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x180058be4  mov     rcx, rax; hInst
0x180058be7  mov     [rsp+210h+fuLoad], 10h; fuLoad
0x180058bef  xor     r9d, r9d; cx
0x180058bf2  mov     [rsp+210h+cy], r14d; cy
0x180058bf7  xor     r8d, r8d; type
0x180058bfa  lea     rdx, [rbp+110h+name]; name
0x180058bfe  call    cs:__imp_LoadImageA
0x180058c04  mov     cs:?g_hbmpSplash@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * g_hbmpSplash
0x180058c0b  test    rax, rax
0x180058c0e  jz      loc_180058DD6
0x180058c14  lea     r8, byte_18008C360; pv
0x180058c1b  mov     edx, 20h ; ' '; c
0x180058c20  mov     rcx, rax; h
0x180058c23  call    cs:__imp_GetObjectA
0x180058c29  cmp     cs:?g_fRegisteredSpash@@3HA, r14d; int g_fRegisteredSpash
0x180058c30  lea     rbx, aSplash_0; "Splash"
0x180058c37  jnz     short loc_180058C93
0x180058c39  xor     edx, edx; Val
0x180058c3b  lea     rcx, [rsp+210h+WndClass]; void *
0x180058c40  lea     r8d, [rdx+48h]; Size
0x180058c44  call    memset_0
0x180058c49  lea     rax, ?SplashWndProc@@YA_JPEAUHWND__@@I_K_J@Z; SplashWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180058c50  mov     edx, 7F00h; lpCursorName
0x180058c55  mov     [rsp+210h+WndClass.lpfnWndProc], rax
0x180058c5a  xor     ecx, ecx; hInstance
0x180058c5c  mov     rax, cs:hInstance
0x180058c63  mov     [rsp+210h+WndClass.hInstance], rax
0x180058c68  call    cs:__imp_LoadCursorA
0x180058c6e  lea     rcx, [rsp+210h+WndClass]; lpWndClass
0x180058c73  mov     [rbp+110h+WndClass.lpszClassName], rbx
0x180058c77  mov     [rbp+110h+WndClass.hCursor], rax
0x180058c7b  call    IsolationAwareRegisterClassA
0x180058c80  test    ax, ax
0x180058c83  jz      loc_180058DD6
0x180058c89  mov     cs:?g_fRegisteredSpash@@3HA, 1; int g_fRegisteredSpash
0x180058c93  mov     rcx, [rsi+0E0h]; hWnd
0x180058c9a  xorps   xmm0, xmm0
0x180058c9d  movups  xmmword ptr [rbp+110h+Rect.left], xmm0
0x180058ca1  call    cs:__imp_GetParent
0x180058ca7  mov     rdi, rax
0x180058caa  mov     rcx, rax
0x180058cad  mov     r12d, 0FFFFFFF0h
0x180058cb3  jmp     short loc_180058CD3
0x180058cb5  mov     rcx, rdi; hWnd
0x180058cb8  call    cs:__imp_GetParent
0x180058cbe  mov     rcx, rax; HWND
0x180058cc1  mov     rbx, rax
0x180058cc4  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x180058cc9  test    eax, eax
0x180058ccb  jz      short loc_180058CE2
0x180058ccd  mov     rdi, rbx
0x180058cd0  mov     rcx, rbx; hWnd
0x180058cd3  mov     edx, r12d; nIndex
0x180058cd6  call    cs:__imp_GetWindowLongA
0x180058cdc  bt      eax, 1Eh
0x180058ce0  jb      short loc_180058CB5
0x180058ce2  lea     rdx, [rbp+110h+Rect]; lpRect
0x180058ce6  mov     rcx, rdi; hWnd
0x180058ce9  call    cs:__imp_GetWindowRect
0x180058cef  mov     eax, [rbp+110h+Rect.bottom]
0x180058cf2  mov     r12d, 2
0x180058cf8  sub     eax, [rbp+110h+Rect.top]
0x180058cfb  mov     ecx, cs:cy
0x180058d01  cdq
0x180058d02  mov     r8d, [rbp+110h+Rect.right]
0x180058d06  sub     r8d, [rbp+110h+Rect.left]
0x180058d0a  mov     r10d, cs:dword_18008C364
0x180058d11  idiv    r12d
0x180058d14  mov     [rsp+210h+var_1B8], r14; LPVOID
0x180058d19  lea     edi, [rcx+0Ah]
0x180058d1c  mov     r11d, eax
0x180058d1f  lea     ebx, [r10+0Ah]
0x180058d23  mov     eax, ecx
0x180058d25  lea     ecx, [r12+6]; dwExStyle
0x180058d2a  cdq
0x180058d2b  idiv    r12d
0x180058d2e  sub     r11d, eax
0x180058d31  mov     eax, r8d
0x180058d34  mov     r8, cs:hInstance
0x180058d3b  cdq
0x180058d3c  add     r11d, [rbp+110h+Rect.top]
0x180058d40  idiv    r12d
0x180058d43  mov     [rsp+210h+var_1C0], r8; HINSTANCE
0x180058d48  lea     r8, Class; lpWindowName
0x180058d4f  mov     r9d, eax
0x180058d52  mov     [rsp+210h+var_1C8], r14; HMENU
0x180058d57  mov     [rsp+210h+var_1D0], r14; HWND
0x180058d5c  mov     eax, r10d
0x180058d5f  cdq
0x180058d60  mov     [rsp+210h+var_1D8], edi; int
0x180058d64  idiv    r12d
0x180058d67  mov     [rsp+210h+var_1E0], ebx; int
0x180058d6b  lea     rdx, aSplash_0; "Splash"
0x180058d72  sub     r9d, eax
0x180058d75  mov     [rsp+210h+fuLoad], r11d; int
0x180058d7a  add     r9d, [rbp+110h+Rect.left]
0x180058d7e  mov     [rsp+210h+cy], r9d; int
0x180058d83  mov     r9d, 90000000h; dwStyle
0x180058d89  call    IsolationAwareCreateWindowExA
0x180058d8e  mov     cs:?g_hwndSplash@@3PEAUHWND__@@EA, rax; HWND__ * g_hwndSplash
0x180058d95  mov     r10, rax
0x180058d98  test    rax, rax
0x180058d9b  jz      short loc_180058DD6
0x180058d9d  mov     rcx, [rsi+1F8h]
0x180058da4  mov     eax, [rcx+20h]
0x180058da7  dec     eax
0x180058da9  cmp     eax, 1
0x180058dac  jle     short loc_180058DBD
0x180058dae  mov     rcx, [rcx+10h]
0x180058db2  mov     rcx, [rcx+10h]; char *
0x180058db6  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x180058dbb  jmp     short loc_180058DC2
0x180058dbd  mov     eax, 9C4h
0x180058dc2  xor     r9d, r9d; lpTimerFunc
0x180058dc5  mov     r8d, eax; uElapse
0x180058dc8  mov     edx, 270Fh; nIDEvent
0x180058dcd  mov     rcx, r10; hWnd
0x180058dd0  call    cs:__imp_SetTimer
0x180058dd6  mov     rcx, [rbp+110h+var_40]
0x180058ddd  xor     rcx, rsp; StackCookie
0x180058de0  call    __security_check_cookie
0x180058de5  add     rsp, 1E8h
0x180058dec  pop     r14
0x180058dee  pop     r12
0x180058df0  pop     rdi
0x180058df1  pop     rsi
0x180058df2  pop     rbx
0x180058df3  pop     rbp
0x180058df4  retn
```
