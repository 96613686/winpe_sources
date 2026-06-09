# CCplAppletPage_DiskLimitsDlg::_OnInitDialog(HWND__ *)

- ea: `0x18002f0c0`
- end: `0x18002f1f2`
- name: `?_OnInitDialog@CCplAppletPage_DiskLimitsDlg@@AEAAXPEAUHWND__@@@Z`
- size: `306`
- prototype: `void(CCplAppletPage_DiskLimitsDlg *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18002ee10`

## callees

- `0x18002e140`
- `0x18002e7b0`
- `0x18002f0c0`
- `0x18004c670`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x18002f122`
- `USER32!SystemParametersInfoW` at `0x18002f122`
- `USER32!GetWindowRect` at `0x18002f0f7`
- `USER32!GetWindowRect` at `0x18002f0f7`
- `USER32!SetWindowPos` at `0x18002f16f`
- `USER32!SetWindowPos` at `0x18002f16f`

## pseudocode

```c
void __fastcall CCplAppletPage_DiskLimitsDlg::_OnInitDialog(CCplAppletPage_DiskLimitsDlg *this, HWND a2)
{
  int v4; // ebx
  int v5; // r14d
  int v6; // r9d
  int v7; // r8d
  struct tagRECT Rect; // [rsp+40h] [rbp-30h] BYREF
  __int128 pvParam; // [rsp+50h] [rbp-20h] BYREF

  Rect = 0;
  if ( GetWindowRect(a2, &Rect) )
  {
    v4 = Rect.right - Rect.left;
    v5 = Rect.bottom - Rect.top;
    pvParam = 0;
    if ( SystemParametersInfoW(0x30u, 0, &pvParam, 0) )
    {
      v6 = *((_DWORD *)this + 1);
      v7 = *(_DWORD *)this;
      if ( v6 >= HIDWORD(pvParam) - v5 - DWORD1(pvParam) )
        v6 = HIDWORD(pvParam) - v5 - DWORD1(pvParam);
      if ( v7 >= DWORD2(pvParam) - v4 - (int)pvParam )
        v7 = DWORD2(pvParam) - v4 - pvParam;
      SetWindowPos(a2, 0, v7, v6, 0, 0, 5u);
    }
  }
  CCplAppletPage_DiskLimitsDlg::CLimitTrackBar::Initialize(
    (char *)this + 48,
    a2,
    *((_QWORD *)this + 3),
    *((_QWORD *)this + 4),
    *((_QWORD *)this + 1),
    3);
  CCplAppletPage_DiskLimitsDlg::CLimitTrackBar::UpdateText((CCplAppletPage_DiskLimitsDlg *)((char *)this + 48));
  CCplAppletPage_DiskLimitsDlg::CLimitTrackBar::Initialize(
    (char *)this + 96,
    a2,
    *((_QWORD *)this + 3),
    *((_QWORD *)this + 4),
    *((_QWORD *)this + 2),
    2);
  CCplAppletPage_DiskLimitsDlg::CLimitTrackBar::UpdateText((CCplAppletPage_DiskLimitsDlg *)((char *)this + 96));
}

```

## disassembly

```asm
0x18002f0c0  mov     [rsp-18h+arg_10], rbx
0x18002f0c5  mov     [rsp-18h+arg_18], rsi
0x18002f0ca  push    rbp
0x18002f0cb  push    rdi
0x18002f0cc  push    r14
0x18002f0ce  mov     rbp, rsp
0x18002f0d1  sub     rsp, 70h
0x18002f0d5  mov     rax, cs:__security_cookie
0x18002f0dc  xor     rax, rsp
0x18002f0df  mov     [rbp+var_10], rax
0x18002f0e3  mov     rsi, rdx
0x18002f0e6  mov     rdi, rcx
0x18002f0e9  xorps   xmm0, xmm0
0x18002f0ec  lea     rdx, [rbp+Rect]; lpRect
0x18002f0f0  mov     rcx, rsi; hWnd
0x18002f0f3  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18002f0f7  call    cs:__imp_GetWindowRect
0x18002f0fd  test    eax, eax
0x18002f0ff  jz      short loc_18002F175
0x18002f101  mov     ebx, [rbp+Rect.right]
0x18002f104  lea     r8, [rbp+pvParam]; pvParam
0x18002f108  mov     r14d, [rbp+Rect.bottom]
0x18002f10c  xor     edx, edx; uiParam
0x18002f10e  sub     ebx, [rbp+Rect.left]
0x18002f111  xorps   xmm0, xmm0
0x18002f114  sub     r14d, [rbp+Rect.top]
0x18002f118  xor     r9d, r9d; fWinIni
0x18002f11b  movups  [rbp+pvParam], xmm0
0x18002f11f  lea     ecx, [rdx+30h]; uiAction
0x18002f122  call    cs:__imp_SystemParametersInfoW
0x18002f128  test    eax, eax
0x18002f12a  jz      short loc_18002F175
0x18002f12c  mov     ecx, dword ptr [rbp+pvParam+8]
0x18002f12f  mov     r9d, [rdi+4]
0x18002f133  sub     ecx, ebx
0x18002f135  sub     ecx, dword ptr [rbp+pvParam]
0x18002f138  mov     r8d, [rdi]
0x18002f13b  mov     eax, dword ptr [rbp+pvParam+0Ch]
0x18002f13e  sub     eax, r14d
0x18002f141  mov     [rsp+70h+uFlags], 5; uFlags
0x18002f149  sub     eax, dword ptr [rbp+pvParam+4]
0x18002f14c  cmp     r9d, eax
0x18002f14f  mov     [rsp+70h+cy], 0; cy
0x18002f157  mov     [rsp+70h+var_50], 0; cx
0x18002f15f  cmovge  r9d, eax; Y
0x18002f163  cmp     r8d, ecx
0x18002f166  cmovge  r8d, ecx; X
0x18002f16a  xor     edx, edx; hWndInsertAfter
0x18002f16c  mov     rcx, rsi; hWnd
0x18002f16f  call    cs:__imp_SetWindowPos
0x18002f175  mov     rax, [rdi+8]
0x18002f179  lea     rcx, [rdi+30h]
0x18002f17d  mov     r9, [rdi+20h]
0x18002f181  mov     rdx, rsi
0x18002f184  mov     r8, [rdi+18h]
0x18002f188  mov     [rsp+70h+cy], 3
0x18002f190  mov     qword ptr [rsp+70h+var_50], rax
0x18002f195  call    ?Initialize@CLimitTrackBar@CCplAppletPage_DiskLimitsDlg@@QEAAJPEAUHWND__@@_K11W4CSC_SETTING_ID@@@Z; CCplAppletPage_DiskLimitsDlg::CLimitTrackBar::Initialize(HWND__ *,unsigned __int64,unsigned __int64,unsigned __int64,CSC_SETTING_ID)
0x18002f19a  lea     rcx, [rdi+30h]; this
0x18002f19e  call    ?UpdateText@CLimitTrackBar@CCplAppletPage_DiskLimitsDlg@@QEAAXXZ; CCplAppletPage_DiskLimitsDlg::CLimitTrackBar::UpdateText(void)
0x18002f1a3  mov     rax, [rdi+10h]
0x18002f1a7  lea     rcx, [rdi+60h]
0x18002f1ab  mov     r9, [rdi+20h]
0x18002f1af  mov     rdx, rsi
0x18002f1b2  mov     r8, [rdi+18h]
0x18002f1b6  mov     [rsp+70h+cy], 2
0x18002f1be  mov     qword ptr [rsp+70h+var_50], rax
0x18002f1c3  call    ?Initialize@CLimitTrackBar@CCplAppletPage_DiskLimitsDlg@@QEAAJPEAUHWND__@@_K11W4CSC_SETTING_ID@@@Z; CCplAppletPage_DiskLimitsDlg::CLimitTrackBar::Initialize(HWND__ *,unsigned __int64,unsigned __int64,unsigned __int64,CSC_SETTING_ID)
0x18002f1c8  lea     rcx, [rdi+60h]; this
0x18002f1cc  call    ?UpdateText@CLimitTrackBar@CCplAppletPage_DiskLimitsDlg@@QEAAXXZ; CCplAppletPage_DiskLimitsDlg::CLimitTrackBar::UpdateText(void)
0x18002f1d1  mov     rcx, [rbp+var_10]
0x18002f1d5  xor     rcx, rsp; StackCookie
0x18002f1d8  call    __security_check_cookie
0x18002f1dd  lea     r11, [rsp+70h+var_s0]
0x18002f1e2  mov     rbx, [r11+30h]
0x18002f1e6  mov     rsi, [r11+38h]
0x18002f1ea  mov     rsp, r11
0x18002f1ed  pop     r14
0x18002f1ef  pop     rdi
0x18002f1f0  pop     rbp
0x18002f1f1  retn
```
