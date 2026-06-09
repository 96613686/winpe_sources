# CHHWinType::ToggleExpansion(bool)

- ea: `0x180053170`
- end: `0x1800534a2`
- name: `?ToggleExpansion@CHHWinType@@QEAAX_N@Z`
- size: `818`
- prototype: `void __fastcall(CHHWinType *__hidden this, bool)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x180052c7c`
- `0x1800539e0`
- `0x18006eaf4`
- `0x180070230`

## callees

- `0x180001728`
- `0x180006708`
- `0x180050158`
- `0x18005176c`
- `0x180053170`
- `0x1800586d0`
- `0x18006f780`
- `0x18007225c`
- `0x180075c90`

## import_xrefs

- `USER32!MoveWindow` at `0x180053311`
- `USER32!MoveWindow` at `0x180053430`
- `USER32!MoveWindow` at `0x180053311`
- `USER32!MoveWindow` at `0x180053430`
- `USER32!ShowWindow` at `0x180053226`
- `USER32!ShowWindow` at `0x180053365`
- `USER32!ShowWindow` at `0x180053379`
- `USER32!ShowWindow` at `0x180053392`
- `USER32!ShowWindow` at `0x1800533aa`
- `USER32!ShowWindow` at `0x180053226`
- `USER32!ShowWindow` at `0x180053365`
- `USER32!ShowWindow` at `0x180053379`
- `USER32!ShowWindow` at `0x180053392`
- `USER32!ShowWindow` at `0x1800533aa`
- `USER32!GetSystemMetrics` at `0x180053250`
- `USER32!GetSystemMetrics` at `0x1800533dd`
- `USER32!GetSystemMetrics` at `0x1800533ff`
- `USER32!GetSystemMetrics` at `0x180053250`
- `USER32!GetSystemMetrics` at `0x1800533dd`
- `USER32!GetSystemMetrics` at `0x1800533ff`
- `USER32!GetWindowRect` at `0x180053239`
- `USER32!GetWindowRect` at `0x1800533bd`
- `USER32!GetWindowRect` at `0x180053239`
- `USER32!GetWindowRect` at `0x1800533bd`
- `USER32!SendMessageA` at `0x18005333c`
- `USER32!SendMessageA` at `0x18005344f`
- `USER32!SendMessageA` at `0x180053466`
- `USER32!SendMessageA` at `0x18005347b`
- `USER32!SendMessageA` at `0x18005333c`
- `USER32!SendMessageA` at `0x18005344f`
- `USER32!SendMessageA` at `0x180053466`
- `USER32!SendMessageA` at `0x18005347b`

## pseudocode

```c
void __fastcall CHHWinType::ToggleExpansion(HWND *this, char a2)
{
  _DWORD *v4; // rbx
  int v5; // eax
  int v6; // eax
  bool v7; // zf
  int v8; // edi
  int v9; // ebx
  LONG left; // r10d
  LONG right; // edx
  HWND v12; // rax
  HWND v13; // rcx
  WPARAM v14; // rdi
  HWND v15; // rcx
  HWND v16; // rcx
  int v17; // ebx
  int v18; // edi
  int v19; // edx
  HWND v20; // rcx
  struct tagRECT Rect; // [rsp+38h] [rbp-18h] BYREF

  if ( (unsigned int)IsValidWindow(this[8]) )
  {
    v4 = (_DWORD *)this + 43;
    if ( a2 )
      CHHWinType::OnTrackNotifyCaller((CHHWinType *)this, 6 - (*v4 != 0));
    v5 = *((_DWORD *)this + 130) - *((_DWORD *)this + 128);
    Rect = 0;
    if ( v5 <= 0 )
    {
      v6 = 290;
      if ( *((_DWORD *)this + 28) )
        v6 = *((_DWORD *)this + 28);
      *((_DWORD *)this + 130) = v6;
    }
    if ( *v4 )
    {
      v7 = (*((_DWORD *)this + 5) & 0x4000) == 0;
      *v4 = 0;
      if ( v7 )
      {
        GetWindowRect(this[8], &Rect);
        v8 = *((_DWORD *)this + 128);
        v9 = *((_DWORD *)this + 130);
        Rect.left += v8 - v9 - GetSystemMetrics(32);
        GetWorkArea();
        left = Rect.left;
        right = Rect.right;
        if ( Rect.left < g_rcWorkArea.left )
          left = g_rcWorkArea.left;
        Rect.left = left;
        if ( Rect.right > g_rcWorkArea.right )
          right = g_rcWorkArea.right;
        v7 = this[40] == 0;
        Rect.right = right;
        if ( v7 )
        {
          if ( (unsigned int)IsValidWindow(this[13]) )
          {
            v12 = (HWND)operator new(0x20u);
            if ( v12 )
            {
              *(_QWORD *)v12 = 0;
              *((_QWORD *)v12 + 1) = 0;
              *((_QWORD *)v12 + 2) = 0;
              *((_BYTE *)v12 + 28) = 0;
            }
            this[40] = v12;
            CSizeBar::Create((LONG_PTR)v12, (struct CHHWinType *)this);
          }
          left = Rect.left;
        }
        if ( !*((_DWORD *)this + 143) )
          MoveWindow(this[8], left, Rect.top, Rect.right - left, Rect.bottom - Rect.top, 1);
      }
      else if ( (unsigned int)IsValidWindow(this[13]) )
      {
        ShowWindow(this[13], 0);
      }
      CHHWinType::CreateOrShowNavPane((CHHWinType *)this);
      v13 = this[11];
      if ( v13 )
      {
        SendMessageA(v13, 0x404u, 0xC8u, 1);
        v14 = 201;
LABEL_41:
        SendMessageA(this[11], 0x404u, v14, 0);
        SendMessageA(this[11], 0x401u, v14, 1);
      }
    }
    else
    {
      *v4 = 1;
      CHHWinType::DestroySizeBar((CHHWinType *)this);
      v15 = this[81];
      if ( v15 )
        ShowWindow(v15, 0);
      v16 = this[80];
      if ( v16 )
        ShowWindow(v16, 0);
      if ( (unsigned int)IsValidWindow(this[12]) )
        ShowWindow(this[12], 0);
      if ( (*((_DWORD *)this + 5) & 0x4000) != 0 )
      {
        ShowWindow(this[13], 5);
      }
      else
      {
        GetWindowRect(this[8], &Rect);
        if ( !*((_DWORD *)this + 143) )
        {
          v17 = *((_DWORD *)this + 128);
          v18 = *((_DWORD *)this + 130);
          Rect.left += GetSystemMetrics(32) + v18 - v17;
        }
        GetWorkArea();
        v19 = Rect.left;
        if ( Rect.left > g_rcWorkArea.right )
        {
          v19 = g_rcWorkArea.right - 2 * GetSystemMetrics(10);
          Rect.left = v19;
        }
        MoveWindow(this[8], v19, Rect.top, Rect.right - v19, Rect.bottom - Rect.top, 1);
      }
      v20 = this[11];
      if ( v20 )
      {
        SendMessageA(v20, 0x404u, 0xC9u, 1);
        v14 = 200;
        goto LABEL_41;
      }
    }
  }
}

```

## disassembly

```asm
0x180053170  mov     [rsp-18h+arg_8], rbx
0x180053175  mov     [rsp-18h+arg_10], rsi
0x18005317a  push    rbp
0x18005317b  push    rdi
0x18005317c  push    r14
0x18005317e  mov     rbp, rsp
0x180053181  sub     rsp, 50h
0x180053185  mov     rax, cs:__security_cookie
0x18005318c  xor     rax, rsp
0x18005318f  mov     [rbp+var_8], rax
0x180053193  mov     rsi, rcx
0x180053196  mov     dil, dl
0x180053199  mov     rcx, [rcx+40h]; HWND
0x18005319d  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x1800531a2  test    eax, eax
0x1800531a4  jz      loc_180053481
0x1800531aa  lea     rbx, [rsi+0ACh]
0x1800531b1  test    dil, dil
0x1800531b4  jz      short loc_1800531C7
0x1800531b6  mov     eax, [rbx]
0x1800531b8  mov     rcx, rsi; this
0x1800531bb  neg     eax
0x1800531bd  sbb     edx, edx
0x1800531bf  add     edx, 6; int
0x1800531c2  call    ?OnTrackNotifyCaller@CHHWinType@@QEAAHH@Z; CHHWinType::OnTrackNotifyCaller(int)
0x1800531c7  mov     eax, [rsi+208h]
0x1800531cd  xorps   xmm0, xmm0
0x1800531d0  sub     eax, [rsi+200h]
0x1800531d6  movups  xmmword ptr [rbp+Rect.left], xmm0
0x1800531da  test    eax, eax
0x1800531dc  jg      short loc_1800531F1
0x1800531de  cmp     dword ptr [rsi+70h], 0
0x1800531e2  mov     eax, 122h
0x1800531e7  cmovnz  eax, [rsi+70h]
0x1800531eb  mov     [rsi+208h], eax
0x1800531f1  cmp     dword ptr [rbx], 0
0x1800531f4  mov     r14d, 1
0x1800531fa  jz      loc_18005334C
0x180053200  test    dword ptr [rsi+14h], 4000h
0x180053207  mov     dword ptr [rbx], 0
0x18005320d  jz      short loc_180053231
0x18005320f  mov     rcx, [rsi+68h]; HWND
0x180053213  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x180053218  test    eax, eax
0x18005321a  jz      loc_180053317
0x180053220  mov     rcx, [rsi+68h]; hWnd
0x180053224  xor     edx, edx; nCmdShow
0x180053226  call    cs:__imp_ShowWindow
0x18005322c  jmp     loc_180053317
0x180053231  mov     rcx, [rsi+40h]; hWnd
0x180053235  lea     rdx, [rbp+Rect]; lpRect
0x180053239  call    cs:__imp_GetWindowRect
0x18005323f  mov     edi, [rsi+200h]
0x180053245  mov     ecx, 20h ; ' '; nIndex
0x18005324a  mov     ebx, [rsi+208h]
0x180053250  call    cs:__imp_GetSystemMetrics
0x180053256  sub     edi, ebx
0x180053258  sub     edi, eax
0x18005325a  add     [rbp+Rect.left], edi
0x18005325d  call    ?GetWorkArea@@YAXXZ; GetWorkArea(void)
0x180053262  mov     r10d, [rbp+Rect.left]
0x180053266  cmp     r10d, cs:?g_rcWorkArea@@3UtagRECT@@A.left; tagRECT g_rcWorkArea ...
0x18005326d  mov     edx, [rbp+Rect.right]
0x180053270  cmovl   r10d, cs:?g_rcWorkArea@@3UtagRECT@@A.left; tagRECT g_rcWorkArea ...
0x180053278  cmp     edx, cs:?g_rcWorkArea@@3UtagRECT@@A.right; tagRECT g_rcWorkArea ...
0x18005327e  mov     [rbp+Rect.left], r10d
0x180053282  cmovg   edx, cs:?g_rcWorkArea@@3UtagRECT@@A.right; tagRECT g_rcWorkArea ...
0x180053289  cmp     qword ptr [rsi+140h], 0
0x180053291  mov     [rbp+Rect.right], edx
0x180053294  jnz     short loc_1800532E7
0x180053296  mov     rcx, [rsi+68h]; HWND
0x18005329a  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x18005329f  test    eax, eax
0x1800532a1  jz      short loc_1800532E3
0x1800532a3  mov     ecx, 20h ; ' '; Size
0x1800532a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800532ad  mov     [rbp+var_20], rax
0x1800532b1  test    rax, rax
0x1800532b4  jz      short loc_1800532D1
0x1800532b6  mov     qword ptr [rax], 0
0x1800532bd  mov     qword ptr [rax+8], 0
0x1800532c5  mov     qword ptr [rax+10h], 0
0x1800532cd  mov     byte ptr [rax+1Ch], 0
0x1800532d1  mov     rdx, rsi; struct CHHWinType *
0x1800532d4  mov     [rsi+140h], rax
0x1800532db  mov     rcx, rax; dwNewLong
0x1800532de  call    ?Create@CSizeBar@@QEAA_NPEAVCHHWinType@@@Z; CSizeBar::Create(CHHWinType *)
0x1800532e3  mov     r10d, [rbp+Rect.left]
0x1800532e7  cmp     dword ptr [rsi+23Ch], 0
0x1800532ee  jnz     short loc_180053317
0x1800532f0  mov     eax, [rbp+Rect.bottom]
0x1800532f3  mov     edx, r10d; X
0x1800532f6  mov     r8d, [rbp+Rect.top]; Y
0x1800532fa  sub     eax, r8d
0x1800532fd  mov     r9d, [rbp+Rect.right]
0x180053301  mov     rcx, [rsi+40h]; hWnd
0x180053305  sub     r9d, r10d; nWidth
0x180053308  mov     [rsp+50h+bRepaint], r14d; bRepaint
0x18005330d  mov     [rsp+50h+nHeight], eax; nHeight
0x180053311  call    cs:__imp_MoveWindow
0x180053317  mov     rcx, rsi; this
0x18005331a  call    ?CreateOrShowNavPane@CHHWinType@@QEAAXXZ; CHHWinType::CreateOrShowNavPane(void)
0x18005331f  mov     rcx, [rsi+58h]; hWnd
0x180053323  test    rcx, rcx
0x180053326  jz      loc_180053481
0x18005332c  mov     ebx, 404h
0x180053331  mov     r9, r14; lParam
0x180053334  mov     edx, ebx; Msg
0x180053336  mov     r8d, 0C8h; wParam
0x18005333c  call    cs:__imp_SendMessageA
0x180053342  mov     edi, 0C9h
0x180053347  jmp     loc_18005345A
0x18005334c  mov     rcx, rsi; this
0x18005334f  mov     [rbx], r14d
0x180053352  call    ?DestroySizeBar@CHHWinType@@QEAAXXZ; CHHWinType::DestroySizeBar(void)
0x180053357  mov     rcx, [rsi+288h]; hWnd
0x18005335e  test    rcx, rcx
0x180053361  jz      short loc_18005336B
0x180053363  xor     edx, edx; nCmdShow
0x180053365  call    cs:__imp_ShowWindow
0x18005336b  mov     rcx, [rsi+280h]; hWnd
0x180053372  test    rcx, rcx
0x180053375  jz      short loc_18005337F
0x180053377  xor     edx, edx; nCmdShow
0x180053379  call    cs:__imp_ShowWindow
0x18005337f  mov     rcx, [rsi+60h]; HWND
0x180053383  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x180053388  test    eax, eax
0x18005338a  jz      short loc_180053398
0x18005338c  mov     rcx, [rsi+60h]; hWnd
0x180053390  xor     edx, edx; nCmdShow
0x180053392  call    cs:__imp_ShowWindow
0x180053398  test    dword ptr [rsi+14h], 4000h
0x18005339f  jz      short loc_1800533B5
0x1800533a1  mov     rcx, [rsi+68h]; hWnd
0x1800533a5  mov     edx, 5; nCmdShow
0x1800533aa  call    cs:__imp_ShowWindow
0x1800533b0  jmp     loc_180053436
0x1800533b5  mov     rcx, [rsi+40h]; hWnd
0x1800533b9  lea     rdx, [rbp+Rect]; lpRect
0x1800533bd  call    cs:__imp_GetWindowRect
0x1800533c3  cmp     dword ptr [rsi+23Ch], 0
0x1800533ca  jnz     short loc_1800533EA
0x1800533cc  mov     ebx, [rsi+200h]
0x1800533d2  mov     ecx, 20h ; ' '; nIndex
0x1800533d7  mov     edi, [rsi+208h]
0x1800533dd  call    cs:__imp_GetSystemMetrics
0x1800533e3  sub     edi, ebx
0x1800533e5  add     edi, eax
0x1800533e7  add     [rbp+Rect.left], edi
0x1800533ea  call    ?GetWorkArea@@YAXXZ; GetWorkArea(void)
0x1800533ef  mov     edx, [rbp+Rect.left]
0x1800533f2  cmp     edx, cs:?g_rcWorkArea@@3UtagRECT@@A.right; tagRECT g_rcWorkArea ...
0x1800533f8  jle     short loc_180053412
0x1800533fa  mov     ecx, 0Ah; nIndex
0x1800533ff  call    cs:__imp_GetSystemMetrics
0x180053405  mov     edx, cs:?g_rcWorkArea@@3UtagRECT@@A.right; tagRECT g_rcWorkArea ...
0x18005340b  add     eax, eax
0x18005340d  sub     edx, eax; X
0x18005340f  mov     [rbp+Rect.left], edx
0x180053412  mov     eax, [rbp+Rect.bottom]
0x180053415  mov     r8d, [rbp+Rect.top]; Y
0x180053419  sub     eax, r8d
0x18005341c  mov     r9d, [rbp+Rect.right]
0x180053420  mov     rcx, [rsi+40h]; hWnd
0x180053424  sub     r9d, edx; nWidth
0x180053427  mov     [rsp+50h+bRepaint], r14d; bRepaint
0x18005342c  mov     [rsp+50h+nHeight], eax; nHeight
0x180053430  call    cs:__imp_MoveWindow
0x180053436  mov     rcx, [rsi+58h]; hWnd
0x18005343a  test    rcx, rcx
0x18005343d  jz      short loc_180053481
0x18005343f  mov     ebx, 404h
0x180053444  mov     r9, r14; lParam
0x180053447  mov     edx, ebx; Msg
0x180053449  mov     r8d, 0C9h; wParam
0x18005344f  call    cs:__imp_SendMessageA
0x180053455  mov     edi, 0C8h
0x18005345a  mov     rcx, [rsi+58h]; hWnd
0x18005345e  xor     r9d, r9d; lParam
0x180053461  mov     r8, rdi; wParam
0x180053464  mov     edx, ebx; Msg
0x180053466  call    cs:__imp_SendMessageA
0x18005346c  mov     rcx, [rsi+58h]; hWnd
0x180053470  mov     r9, r14; lParam
0x180053473  mov     r8, rdi; wParam
0x180053476  mov     edx, 401h; Msg
0x18005347b  call    cs:__imp_SendMessageA
0x180053481  mov     rcx, [rbp+var_8]
0x180053485  xor     rcx, rsp; StackCookie
0x180053488  call    __security_check_cookie
0x18005348d  lea     r11, [rsp+50h+var_s0]
0x180053492  mov     rbx, [r11+28h]
0x180053496  mov     rsi, [r11+30h]
0x18005349a  mov     rsp, r11
0x18005349d  pop     r14
0x18005349f  pop     rdi
0x1800534a0  pop     rbp
0x1800534a1  retn
```
