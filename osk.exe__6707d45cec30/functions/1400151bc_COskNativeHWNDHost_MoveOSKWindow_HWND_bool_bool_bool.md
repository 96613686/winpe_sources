# COskNativeHWNDHost::MoveOSKWindow(HWND__ *,bool,bool,bool)

- ea: `0x1400151bc`
- end: `0x1400154af`
- name: `?MoveOSKWindow@COskNativeHWNDHost@@AEAAXPEAUHWND__@@_N11@Z`
- size: `755`
- prototype: `void(COskNativeHWNDHost *__hidden this, HWND, bool, bool, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400156e0`
- `0x140016318`

## callees

- `0x14000def8`
- `0x14000df20`
- `0x1400121a0`
- `0x140013aa0`
- `0x1400151bc`
- `0x140016598`
- `0x140025d70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001530a`
- `KERNEL32!GetLastError` at `0x140015357`
- `KERNEL32!GetLastError` at `0x1400153e1`
- `KERNEL32!GetLastError` at `0x14001530a`
- `KERNEL32!GetLastError` at `0x140015357`
- `KERNEL32!GetLastError` at `0x1400153e1`
- `USER32!SetWindowPos` at `0x1400152db`
- `USER32!SetWindowPos` at `0x140015334`
- `USER32!SetWindowPos` at `0x1400153c5`
- `USER32!SetWindowPos` at `0x1400152db`
- `USER32!SetWindowPos` at `0x140015334`
- `USER32!SetWindowPos` at `0x1400153c5`
- `USER32!MonitorFromPoint` at `0x140015218`
- `USER32!MonitorFromPoint` at `0x140015218`
- `USER32!GetMonitorInfoW` at `0x140015257`
- `USER32!GetMonitorInfoW` at `0x140015257`
- `USER32!GetWindowRect` at `0x1400151fd`
- `USER32!GetWindowRect` at `0x1400151fd`
- `USER32!MonitorFromRect` at `0x140015229`
- `USER32!MonitorFromRect` at `0x140015229`

## pseudocode

```c
void __fastcall COskNativeHWNDHost::MoveOSKWindow(
        COskNativeHWNDHost *this,
        HWND a2,
        unsigned __int8 a3,
        char a4,
        bool a5)
{
  int v6; // r15d
  HMONITOR v9; // rax
  LONG top; // r9d
  bool IsNavKeyboardVisible; // al
  LONG left; // r8d
  int cy; // edx
  int v14; // eax
  DWORD LastError; // eax
  DWORD v16; // eax
  int v17; // edi
  PVOID *v18; // rcx
  DWORD v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  struct tagRECT Rect; // [rsp+48h] [rbp-19h] BYREF
  struct tagMONITORINFO mi; // [rsp+58h] [rbp-9h] BYREF

  v6 = a3;
  Rect = 0;
  GetWindowRect(a2, &Rect);
  if ( a4 )
    v9 = MonitorFromPoint(0, 1u);
  else
    v9 = MonitorFromRect(&Rect, 2u);
  if ( v9 )
  {
    memset(&mi, 0, sizeof(mi));
    mi.cbSize = 40;
    if ( GetMonitorInfoW(v9, &mi) )
    {
      top = mi.rcMonitor.top;
      if ( a5 )
      {
        IsNavKeyboardVisible = COSKKeyboardManager::IsNavKeyboardVisible();
        left = mi.rcMonitor.left;
        cy = (mi.rcMonitor.bottom - top) * (IsNavKeyboardVisible ? 6 : 30) / 100;
        v14 = mi.rcMonitor.right - mi.rcMonitor.left;
      }
      else
      {
        left = Rect.left;
        v14 = Rect.right - Rect.left;
        cy = Rect.bottom - Rect.top;
      }
      if ( !(_BYTE)v6 )
        top = mi.rcMonitor.bottom - cy;
      if ( !*((_BYTE *)this + 124) )
      {
        if ( !SetWindowPos(a2, 0, left, top, v14, cy, 0x14u)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_701f9d48580b340774086315e62b6ed1_Traceguids, LastError);
        }
        goto LABEL_30;
      }
      if ( !SetWindowPos(a2, 0, left, top, v14, cy, 0x14u)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_701f9d48580b340774086315e62b6ed1_Traceguids, v16);
      }
      v17 = COskNativeHWNDHost::SetOSKWindowDockedState(this, 0, 1, 1);
      if ( v17 >= 0 )
      {
        COSKKeyboardManager::ToggleDockKeyVisualState();
LABEL_30:
        *((_DWORD *)this + 30) = (v6 ^ 1) + 1;
        return;
      }
      if ( !SetWindowPos(a2, 0, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 0x14u) )
      {
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_30;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_27:
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
            WPP_SF_d(v18[2], 24, WPP_701f9d48580b340774086315e62b6ed1_Traceguids, (unsigned int)v17);
          goto LABEL_30;
        }
        v19 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_701f9d48580b340774086315e62b6ed1_Traceguids, v19);
      }
      v18 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_27;
    }
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v21 = 19;
LABEL_37:
      WPP_SF_(v20[2], v21, WPP_701f9d48580b340774086315e62b6ed1_Traceguids);
    }
  }
  else
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v21 = 20;
      goto LABEL_37;
    }
  }
}

```

## disassembly

```asm
0x1400151bc  mov     [rsp-8+arg_10], rbx
0x1400151c1  push    rbp
0x1400151c2  push    rsi
0x1400151c3  push    rdi
0x1400151c4  push    r14
0x1400151c6  push    r15
0x1400151c8  lea     rbp, [rsp-2Fh]
0x1400151cd  sub     rsp, 90h
0x1400151d4  mov     rax, cs:__security_cookie
0x1400151db  xor     rax, rsp
0x1400151de  mov     [rbp+4Fh+var_30], rax
0x1400151e2  mov     rsi, rdx
0x1400151e5  movzx   r15d, r8b
0x1400151e9  mov     r14, rcx
0x1400151ec  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x1400151f0  xorps   xmm0, xmm0
0x1400151f3  mov     rcx, rsi; hWnd
0x1400151f6  mov     bl, r9b
0x1400151f9  movups  xmmword ptr [rbp+4Fh+Rect.left], xmm0
0x1400151fd  call    cs:__imp_GetWindowRect
0x140015203  test    bl, bl
0x140015205  jz      short loc_140015220
0x140015207  mov     qword ptr [rbp+4Fh+pt.x], 0
0x14001520f  mov     edx, 1; dwFlags
0x140015214  mov     rcx, qword ptr [rbp+4Fh+pt.x]; pt
0x140015218  call    cs:__imp_MonitorFromPoint
0x14001521e  jmp     short loc_14001522F
0x140015220  mov     edx, 2; dwFlags
0x140015225  lea     rcx, [rbp+4Fh+Rect]; lprc
0x140015229  call    cs:__imp_MonitorFromRect
0x14001522f  test    rax, rax
0x140015232  jz      loc_14001545E
0x140015238  xor     ecx, ecx
0x14001523a  lea     rdx, [rbp+4Fh+mi]; lpmi
0x14001523e  xorps   xmm0, xmm0
0x140015241  mov     qword ptr [rbp+4Fh+mi.rcWork.bottom], rcx
0x140015245  movups  xmmword ptr [rbp+4Fh+mi.cbSize], xmm0
0x140015249  mov     rcx, rax; hMonitor
0x14001524c  mov     [rbp+4Fh+mi.cbSize], 28h ; '('
0x140015253  movups  xmmword ptr [rbp+4Fh+mi.rcMonitor.bottom], xmm0
0x140015257  call    cs:__imp_GetMonitorInfoW
0x14001525d  test    eax, eax
0x14001525f  jz      loc_14001543E
0x140015265  cmp     [rbp+4Fh+arg_20], 0
0x140015269  mov     r9d, [rbp+4Fh+mi.rcMonitor.top]
0x14001526d  jz      short loc_1400152A4
0x14001526f  call    ?IsNavKeyboardVisible@COSKKeyboardManager@@SA_NXZ; COSKKeyboardManager::IsNavKeyboardVisible(void)
0x140015274  mov     r8d, [rbp+4Fh+mi.rcMonitor.left]
0x140015278  neg     al
0x14001527a  mov     eax, [rbp+4Fh+mi.rcMonitor.bottom]
0x14001527d  sbb     ecx, ecx
0x14001527f  sub     eax, r9d
0x140015282  and     ecx, 0FFFFFFE8h
0x140015285  add     ecx, 1Eh
0x140015288  imul    ecx, eax
0x14001528b  mov     eax, 51EB851Fh
0x140015290  imul    ecx
0x140015292  sar     edx, 5
0x140015295  mov     eax, edx
0x140015297  shr     eax, 1Fh
0x14001529a  add     edx, eax
0x14001529c  mov     eax, [rbp+4Fh+mi.rcMonitor.right]
0x14001529f  sub     eax, r8d
0x1400152a2  jmp     short loc_1400152B4
0x1400152a4  mov     eax, [rbp+4Fh+Rect.right]
0x1400152a7  mov     r8d, [rbp+4Fh+Rect.left]; X
0x1400152ab  sub     eax, r8d
0x1400152ae  mov     edx, [rbp+4Fh+Rect.bottom]
0x1400152b1  sub     edx, [rbp+4Fh+Rect.top]
0x1400152b4  test    r15b, r15b
0x1400152b7  jnz     short loc_1400152C0
0x1400152b9  mov     r9d, [rbp+4Fh+mi.rcMonitor.bottom]
0x1400152bd  sub     r9d, edx; Y
0x1400152c0  mov     [rsp+0B0h+uFlags], 14h; uFlags
0x1400152c8  mov     rcx, rsi; hWnd
0x1400152cb  mov     [rsp+0B0h+cy], edx; cy
0x1400152cf  xor     edx, edx; hWndInsertAfter
0x1400152d1  mov     [rsp+0B0h+var_90], eax; cx
0x1400152d5  cmp     [r14+7Ch], dl
0x1400152d9  jnz     short loc_140015334
0x1400152db  call    cs:__imp_SetWindowPos
0x1400152e1  test    eax, eax
0x1400152e3  jnz     loc_140015430
0x1400152e9  mov     rax, cs:WPP_GLOBAL_Control
0x1400152f0  lea     rbx, WPP_GLOBAL_Control
0x1400152f7  cmp     rax, rbx
0x1400152fa  jz      loc_140015430
0x140015300  test    byte ptr [rax+1Ch], 1
0x140015304  jz      loc_140015430
0x14001530a  call    cs:__imp_GetLastError
0x140015310  mov     rcx, cs:WPP_GLOBAL_Control
0x140015317  lea     r8, WPP_701f9d48580b340774086315e62b6ed1_Traceguids
0x14001531e  mov     edx, 15h
0x140015323  mov     r9d, eax
0x140015326  mov     rcx, [rcx+10h]
0x14001532a  call    WPP_SF_d
0x14001532f  jmp     loc_140015430
0x140015334  call    cs:__imp_SetWindowPos
0x14001533a  lea     rbx, WPP_GLOBAL_Control
0x140015341  test    eax, eax
0x140015343  jnz     short loc_14001537C
0x140015345  mov     rax, cs:WPP_GLOBAL_Control
0x14001534c  cmp     rax, rbx
0x14001534f  jz      short loc_14001537C
0x140015351  test    byte ptr [rax+1Ch], 1
0x140015355  jz      short loc_14001537C
0x140015357  call    cs:__imp_GetLastError
0x14001535d  mov     rcx, cs:WPP_GLOBAL_Control
0x140015364  lea     r8, WPP_701f9d48580b340774086315e62b6ed1_Traceguids
0x14001536b  mov     edx, 16h
0x140015370  mov     r9d, eax
0x140015373  mov     rcx, [rcx+10h]
0x140015377  call    WPP_SF_d
0x14001537c  mov     r9b, 1; bool
0x14001537f  xor     edx, edx; bool
0x140015381  mov     r8b, r9b; bool
0x140015384  mov     rcx, r14; this
0x140015387  call    ?SetOSKWindowDockedState@COskNativeHWNDHost@@AEAAJ_N00@Z; COskNativeHWNDHost::SetOSKWindowDockedState(bool,bool,bool)
0x14001538c  mov     edi, eax
0x14001538e  test    eax, eax
0x140015390  js      short loc_14001539C
0x140015392  call    ?ToggleDockKeyVisualState@COSKKeyboardManager@@SAXXZ; COSKKeyboardManager::ToggleDockKeyVisualState(void)
0x140015397  jmp     loc_140015430
0x14001539c  mov     ecx, [rbp+4Fh+Rect.bottom]
0x14001539f  xor     edx, edx; hWndInsertAfter
0x1400153a1  mov     r9d, [rbp+4Fh+Rect.top]; Y
0x1400153a5  sub     ecx, r9d
0x1400153a8  mov     eax, [rbp+4Fh+Rect.right]
0x1400153ab  mov     r8d, [rbp+4Fh+Rect.left]; X
0x1400153af  sub     eax, r8d
0x1400153b2  mov     [rsp+0B0h+uFlags], 14h; uFlags
0x1400153ba  mov     [rsp+0B0h+cy], ecx; cy
0x1400153be  mov     rcx, rsi; hWnd
0x1400153c1  mov     [rsp+0B0h+var_90], eax; cx
0x1400153c5  call    cs:__imp_SetWindowPos
0x1400153cb  test    eax, eax
0x1400153cd  jnz     short loc_140015406
0x1400153cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400153d6  cmp     rcx, rbx
0x1400153d9  jz      short loc_140015430
0x1400153db  test    byte ptr [rcx+1Ch], 1
0x1400153df  jz      short loc_14001540D
0x1400153e1  call    cs:__imp_GetLastError
0x1400153e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400153ee  lea     r8, WPP_701f9d48580b340774086315e62b6ed1_Traceguids
0x1400153f5  mov     edx, 17h
0x1400153fa  mov     r9d, eax
0x1400153fd  mov     rcx, [rcx+10h]
0x140015401  call    WPP_SF_d
0x140015406  mov     rcx, cs:WPP_GLOBAL_Control
0x14001540d  cmp     rcx, rbx
0x140015410  jz      short loc_140015430
0x140015412  test    byte ptr [rcx+1Ch], 1
0x140015416  jz      short loc_140015430
0x140015418  mov     rcx, [rcx+10h]
0x14001541c  lea     r8, WPP_701f9d48580b340774086315e62b6ed1_Traceguids
0x140015423  mov     edx, 18h
0x140015428  mov     r9d, edi
0x14001542b  call    WPP_SF_d
0x140015430  mov     eax, r15d
0x140015433  xor     eax, 1
0x140015436  inc     eax
0x140015438  mov     [r14+78h], eax
0x14001543c  jmp     short loc_14001548C
0x14001543e  mov     rcx, cs:WPP_GLOBAL_Control
0x140015445  lea     rbx, WPP_GLOBAL_Control
0x14001544c  cmp     rcx, rbx
0x14001544f  jz      short loc_14001548C
0x140015451  test    byte ptr [rcx+1Ch], 1
0x140015455  jz      short loc_14001548C
0x140015457  mov     edx, 13h
0x14001545c  jmp     short loc_14001547C
0x14001545e  mov     rcx, cs:WPP_GLOBAL_Control
0x140015465  lea     rbx, WPP_GLOBAL_Control
0x14001546c  cmp     rcx, rbx
0x14001546f  jz      short loc_14001548C
0x140015471  test    byte ptr [rcx+1Ch], 1
0x140015475  jz      short loc_14001548C
0x140015477  mov     edx, 14h
0x14001547c  mov     rcx, [rcx+10h]
0x140015480  lea     r8, WPP_701f9d48580b340774086315e62b6ed1_Traceguids
0x140015487  call    WPP_SF_
0x14001548c  mov     rcx, [rbp+4Fh+var_30]
0x140015490  xor     rcx, rsp; StackCookie
0x140015493  call    __security_check_cookie
0x140015498  mov     rbx, [rsp+0B0h+arg_10]
0x1400154a0  add     rsp, 90h
0x1400154a7  pop     r15
0x1400154a9  pop     r14
0x1400154ab  pop     rdi
0x1400154ac  pop     rsi
0x1400154ad  pop     rbp
0x1400154ae  retn
```
