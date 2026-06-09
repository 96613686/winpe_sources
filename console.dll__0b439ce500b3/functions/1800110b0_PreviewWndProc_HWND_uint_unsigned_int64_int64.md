# PreviewWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800110b0`
- end: `0x1800112bd`
- name: `?PreviewWndProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `525`
- prototype: `__int64 __fastcall(HWND, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800015b0`
- `0x180002088`
- `0x180010680`
- `0x18001076c`
- `0x1800110b0`
- `0x1800112c4`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x18001118f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x18001118f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!MoveWindow` at `0x180011294`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!MoveWindow` at `0x180011294`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x18001113a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x18001113a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DefWindowProcW` at `0x180011118`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DefWindowProcW` at `0x180011118`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x1800111f1`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x1800111f1`
- `ext-ms-win-ntuser-draw-l1-1-0!BeginPaint` at `0x1800111ac`
- `ext-ms-win-ntuser-draw-l1-1-0!BeginPaint` at `0x1800111ac`
- `ext-ms-win-ntuser-draw-l1-1-0!EndPaint` at `0x1800111cb`
- `ext-ms-win-ntuser-draw-l1-1-0!EndPaint` at `0x1800111cb`
- `ext-ms-win-ntuser-window-l1-1-4!AdjustWindowRect` at `0x180011209`
- `ext-ms-win-ntuser-window-l1-1-4!AdjustWindowRect` at `0x180011209`

## pseudocode

```c
LRESULT __fastcall PreviewWndProc(HWND a1, UINT Msg, WPARAM wParam, _DWORD *lParam)
{
  int v9; // r9d
  int v10; // r8d
  struct tagRECT Rect; // [rsp+40h] [rbp-39h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+50h] [rbp-29h] BYREF

  memset_0(&Paint, 0, sizeof(Paint));
  Rect = 0;
  switch ( Msg )
  {
    case 1u:
      SetRect(&Rect, 0, 0, 50, 50);
      AdjustWindowRect(&Rect, 0xCF0000u, 0);
      NonClientSize.x = Rect.right - Rect.left - 50;
      NonClientSize.y = Rect.bottom - Rect.top - 50;
      UpdatePreviewRect();
      v9 = lParam[9];
      v10 = lParam[8];
      if ( ((gcxScreen >> 1) + gcyScreen * v9) / gcxScreen <= v10 )
        v10 = ((gcxScreen >> 1) + gcyScreen * lParam[9]) / gcxScreen;
      else
        v9 = ((gcyScreen >> 1) + gcxScreen * v10) / gcyScreen;
      MoveWindow(a1, lParam[11], lParam[10], v9, v10, 1);
      break;
    case 0xFu:
      BeginPaint(a1, &Paint);
      PreviewPaint(&Paint, a1);
      EndPaint(a1, &Paint);
      break;
    case 0x402u:
      InvalidatePreviewRect(a1);
      UpdatePreviewRect();
      GetWindowRect(a1, &Rect);
      if ( ((gcxScreen >> 1) + gcyScreen * (Rect.right - Rect.left)) / gcxScreen != Rect.bottom - Rect.top )
        SetWindowPos(
          a1,
          0,
          0,
          0,
          Rect.right - Rect.left,
          ((gcxScreen >> 1) + gcyScreen * (Rect.right - Rect.left)) / gcxScreen,
          0x16u);
      InvalidatePreviewRect(a1);
      break;
    default:
      return DefWindowProcW(a1, Msg, wParam, (LPARAM)lParam);
  }
  return 0;
}

```

## disassembly

```asm
0x1800110b0  push    rbp
0x1800110b2  push    rbx
0x1800110b3  push    rsi
0x1800110b4  push    rdi
0x1800110b5  push    r14
0x1800110b7  lea     rbp, [rsp-37h]
0x1800110bc  sub     rsp, 0B0h
0x1800110c3  mov     rax, cs:__security_cookie
0x1800110ca  xor     rax, rsp
0x1800110cd  mov     [rbp+57h+var_30], rax
0x1800110d1  mov     esi, edx
0x1800110d3  mov     r14, r8
0x1800110d6  xor     edx, edx; Val
0x1800110d8  mov     rbx, rcx
0x1800110db  lea     rcx, [rbp+57h+Paint]; void *
0x1800110df  mov     rdi, r9
0x1800110e2  lea     r8d, [rdx+48h]; Size
0x1800110e6  call    memset_0
0x1800110eb  mov     eax, esi
0x1800110ed  xorps   xmm0, xmm0
0x1800110f0  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x1800110f4  sub     eax, 1
0x1800110f7  jz      loc_1800111DC
0x1800110fd  mov     rcx, rbx; hWnd
0x180011100  sub     eax, 0Eh
0x180011103  jz      loc_1800111A8
0x180011109  cmp     eax, 3F3h
0x18001110e  jz      short loc_180011129
0x180011110  mov     r9, rdi; lParam
0x180011113  mov     r8, r14; wParam
0x180011116  mov     edx, esi; Msg
0x180011118  call    cs:__imp_DefWindowProcW
0x18001111f  nop     dword ptr [rax+rax+00h]
0x180011124  jmp     loc_1800112A2
0x180011129  call    ?InvalidatePreviewRect@@YAXPEAUHWND__@@@Z; InvalidatePreviewRect(HWND__ *)
0x18001112e  call    ?UpdatePreviewRect@@YAXXZ; UpdatePreviewRect(void)
0x180011133  lea     rdx, [rbp+57h+Rect]; lpRect
0x180011137  mov     rcx, rbx; hWnd
0x18001113a  call    cs:__imp_GetWindowRect
0x180011141  nop     dword ptr [rax+rax+00h]
0x180011146  mov     r9d, [rbp+57h+Rect.right]
0x18001114a  sub     r9d, [rbp+57h+Rect.left]
0x18001114e  mov     ecx, cs:?gcxScreen@@3JA; long gcxScreen
0x180011154  mov     eax, r9d
0x180011157  imul    eax, cs:?gcyScreen@@3JA; long gcyScreen
0x18001115e  sar     ecx, 1
0x180011160  add     eax, ecx
0x180011162  mov     ecx, [rbp+57h+Rect.bottom]
0x180011165  sub     ecx, [rbp+57h+Rect.top]
0x180011168  cdq
0x180011169  idiv    cs:?gcxScreen@@3JA; long gcxScreen
0x18001116f  cmp     eax, ecx
0x180011171  jz      short loc_18001119B
0x180011173  mov     [rsp+0D0h+uFlags], 16h; uFlags
0x18001117b  xor     r8d, r8d; X
0x18001117e  mov     [rsp+0D0h+cy], eax; cy
0x180011182  xor     edx, edx; hWndInsertAfter
0x180011184  mov     [rsp+0D0h+yBottom], r9d; cx
0x180011189  mov     rcx, rbx; hWnd
0x18001118c  xor     r9d, r9d; Y
0x18001118f  call    cs:__imp_SetWindowPos
0x180011196  nop     dword ptr [rax+rax+00h]
0x18001119b  mov     rcx, rbx; hWnd
0x18001119e  call    ?InvalidatePreviewRect@@YAXPEAUHWND__@@@Z; InvalidatePreviewRect(HWND__ *)
0x1800111a3  jmp     loc_1800112A0
0x1800111a8  lea     rdx, [rbp+57h+Paint]; lpPaint
0x1800111ac  call    cs:__imp_BeginPaint
0x1800111b3  nop     dword ptr [rax+rax+00h]
0x1800111b8  mov     rdx, rbx; HWND
0x1800111bb  lea     rcx, [rbp+57h+Paint]; struct tagPAINTSTRUCT *
0x1800111bf  call    ?PreviewPaint@@YAXPEAUtagPAINTSTRUCT@@PEAUHWND__@@@Z; PreviewPaint(tagPAINTSTRUCT *,HWND__ *)
0x1800111c4  lea     rdx, [rbp+57h+Paint]; lpPaint
0x1800111c8  mov     rcx, rbx; hWnd
0x1800111cb  call    cs:__imp_EndPaint
0x1800111d2  nop     dword ptr [rax+rax+00h]
0x1800111d7  jmp     loc_1800112A0
0x1800111dc  mov     esi, 32h ; '2'
0x1800111e1  lea     rcx, [rbp+57h+Rect]; lprc
0x1800111e5  mov     r9d, esi; xRight
0x1800111e8  mov     [rsp+0D0h+yBottom], esi; yBottom
0x1800111ec  xor     r8d, r8d; yTop
0x1800111ef  xor     edx, edx; xLeft
0x1800111f1  call    cs:__imp_SetRect
0x1800111f8  nop     dword ptr [rax+rax+00h]
0x1800111fd  xor     r8d, r8d; bMenu
0x180011200  lea     rcx, [rbp+57h+Rect]; lpRect
0x180011204  mov     edx, 0CF0000h; dwStyle
0x180011209  call    cs:__imp_AdjustWindowRect
0x180011210  nop     dword ptr [rax+rax+00h]
0x180011215  mov     eax, [rbp+57h+Rect.right]
0x180011218  sub     eax, [rbp+57h+Rect.left]
0x18001121b  sub     eax, esi
0x18001121d  mov     dword ptr cs:?NonClientSize@@3UtagPOINT@@A, eax; tagPOINT NonClientSize
0x180011223  mov     eax, [rbp+57h+Rect.bottom]
0x180011226  sub     eax, [rbp+57h+Rect.top]
0x180011229  sub     eax, esi
0x18001122b  mov     dword ptr cs:?NonClientSize@@3UtagPOINT@@A+4, eax; tagPOINT NonClientSize
0x180011231  call    ?UpdatePreviewRect@@YAXXZ; UpdatePreviewRect(void)
0x180011236  mov     r11d, cs:?gcxScreen@@3JA; long gcxScreen
0x18001123d  mov     ecx, r11d
0x180011240  mov     r9d, [rdi+24h]; nWidth
0x180011244  mov     eax, r9d
0x180011247  mov     r10d, cs:?gcyScreen@@3JA; long gcyScreen
0x18001124e  mov     r8d, [rdi+20h]
0x180011252  imul    eax, r10d
0x180011256  sar     ecx, 1
0x180011258  add     eax, ecx
0x18001125a  cdq
0x18001125b  idiv    r11d
0x18001125e  cmp     eax, r8d
0x180011261  jle     short loc_18001127A
0x180011263  mov     eax, r8d
0x180011266  mov     ecx, r10d
0x180011269  imul    eax, r11d
0x18001126d  sar     ecx, 1
0x18001126f  add     eax, ecx
0x180011271  cdq
0x180011272  idiv    r10d
0x180011275  mov     r9d, eax
0x180011278  jmp     short loc_18001127D
0x18001127a  mov     r8d, eax
0x18001127d  mov     edx, [rdi+2Ch]; X
0x180011280  mov     rcx, rbx; hWnd
0x180011283  mov     [rsp+0D0h+cy], 1; bRepaint
0x18001128b  mov     [rsp+0D0h+yBottom], r8d; nHeight
0x180011290  mov     r8d, [rdi+28h]; Y
0x180011294  call    cs:__imp_MoveWindow
0x18001129b  nop     dword ptr [rax+rax+00h]
0x1800112a0  xor     eax, eax
0x1800112a2  mov     rcx, [rbp+57h+var_30]
0x1800112a6  xor     rcx, rsp; StackCookie
0x1800112a9  call    __security_check_cookie
0x1800112ae  add     rsp, 0B0h
0x1800112b5  pop     r14
0x1800112b7  pop     rdi
0x1800112b8  pop     rsi
0x1800112b9  pop     rbx
0x1800112ba  pop     rbp
0x1800112bb  retn
```
