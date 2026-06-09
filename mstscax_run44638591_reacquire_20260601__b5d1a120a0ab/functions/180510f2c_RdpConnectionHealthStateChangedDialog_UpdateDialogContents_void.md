# RdpConnectionHealthStateChangedDialog::UpdateDialogContents(void)

- ea: `0x180510f2c`
- end: `0x18051124a`
- name: `?UpdateDialogContents@RdpConnectionHealthStateChangedDialog@@AEAAXXZ`
- size: `798`
- prototype: `void __fastcall(RdpConnectionHealthStateChangedDialog *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18050fd00`
- `0x18050ff60`
- `0x180510000`

## callees

- `0x18002a334`
- `0x180039ce4`
- `0x1800cfa74`
- `0x180510f2c`
- `0x180688fc0`

## import_xrefs

- `USER32!GetWindowRect` at `0x18051110c`
- `USER32!GetWindowRect` at `0x180511177`
- `USER32!GetWindowRect` at `0x1805111e2`
- `USER32!GetWindowRect` at `0x18051110c`
- `USER32!GetWindowRect` at `0x180511177`
- `USER32!GetWindowRect` at `0x1805111e2`
- `USER32!MapWindowPoints` at `0x180511127`
- `USER32!MapWindowPoints` at `0x180511192`
- `USER32!MapWindowPoints` at `0x1805111fd`
- `USER32!MapWindowPoints` at `0x180511127`
- `USER32!MapWindowPoints` at `0x180511192`
- `USER32!MapWindowPoints` at `0x1805111fd`
- `USER32!UpdateWindow` at `0x180511146`
- `USER32!UpdateWindow` at `0x1805111b1`
- `USER32!UpdateWindow` at `0x18051121c`
- `USER32!UpdateWindow` at `0x180511146`
- `USER32!UpdateWindow` at `0x1805111b1`
- `USER32!UpdateWindow` at `0x18051121c`
- `USER32!InvalidateRect` at `0x18051113c`
- `USER32!InvalidateRect` at `0x1805111a7`
- `USER32!InvalidateRect` at `0x180511212`
- `USER32!InvalidateRect` at `0x18051113c`
- `USER32!InvalidateRect` at `0x1805111a7`
- `USER32!InvalidateRect` at `0x180511212`
- `USER32!SetDlgItemTextW` at `0x1805110f1`
- `USER32!SetDlgItemTextW` at `0x18051115c`
- `USER32!SetDlgItemTextW` at `0x1805111c7`
- `USER32!SetDlgItemTextW` at `0x1805110f1`
- `USER32!SetDlgItemTextW` at `0x18051115c`
- `USER32!SetDlgItemTextW` at `0x1805111c7`
- `USER32!GetDlgItem` at `0x180510fd5`
- `USER32!GetDlgItem` at `0x180510fe7`
- `USER32!GetDlgItem` at `0x180510ff9`
- `USER32!GetDlgItem` at `0x180510fd5`
- `USER32!GetDlgItem` at `0x180510fe7`
- `USER32!GetDlgItem` at `0x180510ff9`

## pseudocode

```c
void __fastcall RdpConnectionHealthStateChangedDialog::UpdateDialogContents(
        RdpConnectionHealthStateChangedDialog *this)
{
  HWND v2; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HWND DlgItem; // r14
  HWND v5; // r15
  HWND v6; // rax
  unsigned __int64 v7; // r11
  HWND v8; // r12
  unsigned int v9; // r11d
  unsigned int v10; // r11d
  unsigned __int64 v11; // r11
  unsigned __int64 v12; // r11
  unsigned __int64 v13; // r11
  unsigned __int64 v14; // r11
  struct tagRECT Rect; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR String[256]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR v17[256]; // [rsp+230h] [rbp+130h] BYREF
  WCHAR v18[256]; // [rsp+430h] [rbp+330h] BYREF

  v2 = (HWND)*((_QWORD *)this + 7);
  String[0] = 0;
  v17[0] = 0;
  v18[0] = 0;
  if ( v2 )
  {
    DlgItem = GetDlgItem(v2, 13435);
    v5 = GetDlgItem(*((HWND *)this + 7), 13436);
    v6 = GetDlgItem(*((HWND *)this + 7), 13437);
    v7 = 256;
    v8 = v6;
    if ( *((_DWORD *)this + 36) == 1 )
    {
      StringCchCopyW(String, 0x100u, (const unsigned __int16 *)this + 74);
      StringCchCopyW(v17, v9, (const unsigned __int16 *)this + 330);
      StringCchCopyW(v18, v10, (const unsigned __int16 *)this + 586);
    }
    if ( *((_DWORD *)this + 36) == 2 )
    {
      StringCchCopyW(String, v7, (const unsigned __int16 *)this + 842);
      StringCchCopyW(v17, v11, (const unsigned __int16 *)this + 1098);
      StringCchCopyW(v18, v12, (const unsigned __int16 *)this + 1354);
    }
    if ( *((_DWORD *)this + 36) == 3 )
    {
      StringCchCopyW(String, v7, (const unsigned __int16 *)this + 1610);
      StringCchCopyW(v17, v13, (const unsigned __int16 *)this + 1866);
      StringCchCopyW(v18, v14, (const unsigned __int16 *)this + 2122);
    }
    SetDlgItemTextW(*((HWND *)this + 7), 13435, String);
    if ( DlgItem )
    {
      Rect = 0;
      if ( GetWindowRect(DlgItem, &Rect) )
      {
        MapWindowPoints(0, *((HWND *)this + 7), (LPPOINT)&Rect, 2u);
        InvalidateRect(*((HWND *)this + 7), &Rect, 1);
        UpdateWindow(*((HWND *)this + 7));
      }
    }
    SetDlgItemTextW(*((HWND *)this + 7), 13436, v17);
    if ( v5 )
    {
      Rect = 0;
      if ( GetWindowRect(v5, &Rect) )
      {
        MapWindowPoints(0, *((HWND *)this + 7), (LPPOINT)&Rect, 2u);
        InvalidateRect(*((HWND *)this + 7), &Rect, 1);
        UpdateWindow(*((HWND *)this + 7));
      }
    }
    SetDlgItemTextW(*((HWND *)this + 7), 13437, v18);
    if ( v8 )
    {
      Rect = 0;
      if ( GetWindowRect(v8, &Rect) )
      {
        MapWindowPoints(0, *((HWND *)this + 7), (LPPOINT)&Rect, 2u);
        InvalidateRect(*((HWND *)this + 7), &Rect, 1);
        UpdateWindow(*((HWND *)this + 7));
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
         && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      67,
      WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
}

```

## disassembly

```asm
0x180510f2c  mov     [rsp-8+arg_8], rbx
0x180510f31  mov     [rsp-8+arg_10], r12
0x180510f36  push    rbp
0x180510f37  push    r14
0x180510f39  push    r15
0x180510f3b  lea     rbp, [rsp-540h]
0x180510f43  sub     rsp, 640h
0x180510f4a  mov     rax, cs:__security_cookie
0x180510f51  xor     rax, rsp
0x180510f54  mov     [rbp+550h+var_20], rax
0x180510f5b  xor     eax, eax
0x180510f5d  mov     rbx, rcx
0x180510f60  mov     rcx, [rcx+38h]; hDlg
0x180510f64  mov     [rsp+650h+String], ax
0x180510f69  mov     [rbp+550h+var_420], ax
0x180510f70  mov     [rbp+550h+var_220], ax
0x180510f77  test    rcx, rcx
0x180510f7a  jnz     short loc_180510FD0
0x180510f7c  mov     rax, cs:WPP_GLOBAL_Control
0x180510f83  lea     rcx, WPP_GLOBAL_Control
0x180510f8a  cmp     rax, rcx
0x180510f8d  jz      loc_180511222
0x180510f93  test    byte ptr [rax+1Ch], 1
0x180510f97  jz      loc_180511222
0x180510f9d  cmp     byte ptr [rax+19h], 2
0x180510fa1  jb      loc_180511222
0x180510fa7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180510fac  mov     rcx, cs:WPP_GLOBAL_Control
0x180510fb3  lea     r8, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids
0x180510fba  mov     edx, 43h ; 'C'
0x180510fbf  mov     r9d, eax
0x180510fc2  mov     rcx, [rcx+10h]
0x180510fc6  call    WPP_SF_d
0x180510fcb  jmp     loc_180511222
0x180510fd0  mov     edx, 347Bh; nIDDlgItem
0x180510fd5  call    cs:__imp_GetDlgItem
0x180510fdb  mov     rcx, [rbx+38h]; hDlg
0x180510fdf  mov     edx, 347Ch; nIDDlgItem
0x180510fe4  mov     r14, rax
0x180510fe7  call    cs:__imp_GetDlgItem
0x180510fed  mov     rcx, [rbx+38h]; hDlg
0x180510ff1  mov     edx, 347Dh; nIDDlgItem
0x180510ff6  mov     r15, rax
0x180510ff9  call    cs:__imp_GetDlgItem
0x180510fff  cmp     dword ptr [rbx+90h], 1
0x180511006  mov     r11d, 100h
0x18051100c  mov     r12, rax
0x18051100f  jnz     short loc_180511051
0x180511011  lea     r8, [rbx+94h]; unsigned __int16 *
0x180511018  mov     edx, r11d; unsigned __int64
0x18051101b  lea     rcx, [rsp+650h+String]; unsigned __int16 *
0x180511020  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180511025  lea     r8, [rbx+294h]; unsigned __int16 *
0x18051102c  mov     edx, r11d; unsigned __int64
0x18051102f  lea     rcx, [rbp+550h+var_420]; unsigned __int16 *
0x180511036  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18051103b  lea     r8, [rbx+494h]; unsigned __int16 *
0x180511042  mov     edx, r11d; unsigned __int64
0x180511045  lea     rcx, [rbp+550h+var_220]; unsigned __int16 *
0x18051104c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180511051  cmp     dword ptr [rbx+90h], 2
0x180511058  jnz     short loc_18051109A
0x18051105a  lea     r8, [rbx+694h]; unsigned __int16 *
0x180511061  mov     rdx, r11; unsigned __int64
0x180511064  lea     rcx, [rsp+650h+String]; unsigned __int16 *
0x180511069  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18051106e  lea     r8, [rbx+894h]; unsigned __int16 *
0x180511075  mov     rdx, r11; unsigned __int64
0x180511078  lea     rcx, [rbp+550h+var_420]; unsigned __int16 *
0x18051107f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180511084  lea     r8, [rbx+0A94h]; unsigned __int16 *
0x18051108b  mov     rdx, r11; unsigned __int64
0x18051108e  lea     rcx, [rbp+550h+var_220]; unsigned __int16 *
0x180511095  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18051109a  cmp     dword ptr [rbx+90h], 3
0x1805110a1  jnz     short loc_1805110E3
0x1805110a3  lea     r8, [rbx+0C94h]; unsigned __int16 *
0x1805110aa  mov     rdx, r11; unsigned __int64
0x1805110ad  lea     rcx, [rsp+650h+String]; unsigned __int16 *
0x1805110b2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805110b7  lea     r8, [rbx+0E94h]; unsigned __int16 *
0x1805110be  mov     rdx, r11; unsigned __int64
0x1805110c1  lea     rcx, [rbp+550h+var_420]; unsigned __int16 *
0x1805110c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805110cd  lea     r8, [rbx+1094h]; unsigned __int16 *
0x1805110d4  mov     rdx, r11; unsigned __int64
0x1805110d7  lea     rcx, [rbp+550h+var_220]; unsigned __int16 *
0x1805110de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805110e3  mov     rcx, [rbx+38h]; hDlg
0x1805110e7  lea     r8, [rsp+650h+String]; lpString
0x1805110ec  mov     edx, 347Bh; nIDDlgItem
0x1805110f1  call    cs:__imp_SetDlgItemTextW
0x1805110f7  test    r14, r14
0x1805110fa  jz      short loc_18051114C
0x1805110fc  xorps   xmm0, xmm0
0x1805110ff  lea     rdx, [rsp+650h+Rect]; lpRect
0x180511104  mov     rcx, r14; hWnd
0x180511107  movups  xmmword ptr [rsp+650h+Rect.left], xmm0
0x18051110c  call    cs:__imp_GetWindowRect
0x180511112  test    eax, eax
0x180511114  jz      short loc_18051114C
0x180511116  mov     rdx, [rbx+38h]; hWndTo
0x18051111a  lea     r8, [rsp+650h+Rect]; lpPoints
0x18051111f  mov     r9d, 2; cPoints
0x180511125  xor     ecx, ecx; hWndFrom
0x180511127  call    cs:__imp_MapWindowPoints
0x18051112d  mov     rcx, [rbx+38h]; hWnd
0x180511131  lea     rdx, [rsp+650h+Rect]; lpRect
0x180511136  mov     r8d, 1; bErase
0x18051113c  call    cs:__imp_InvalidateRect
0x180511142  mov     rcx, [rbx+38h]; hWnd
0x180511146  call    cs:__imp_UpdateWindow
0x18051114c  mov     rcx, [rbx+38h]; hDlg
0x180511150  lea     r8, [rbp+550h+var_420]; lpString
0x180511157  mov     edx, 347Ch; nIDDlgItem
0x18051115c  call    cs:__imp_SetDlgItemTextW
0x180511162  test    r15, r15
0x180511165  jz      short loc_1805111B7
0x180511167  xorps   xmm0, xmm0
0x18051116a  lea     rdx, [rsp+650h+Rect]; lpRect
0x18051116f  mov     rcx, r15; hWnd
0x180511172  movups  xmmword ptr [rsp+650h+Rect.left], xmm0
0x180511177  call    cs:__imp_GetWindowRect
0x18051117d  test    eax, eax
0x18051117f  jz      short loc_1805111B7
0x180511181  mov     rdx, [rbx+38h]; hWndTo
0x180511185  lea     r8, [rsp+650h+Rect]; lpPoints
0x18051118a  mov     r9d, 2; cPoints
0x180511190  xor     ecx, ecx; hWndFrom
0x180511192  call    cs:__imp_MapWindowPoints
0x180511198  mov     rcx, [rbx+38h]; hWnd
0x18051119c  lea     rdx, [rsp+650h+Rect]; lpRect
0x1805111a1  mov     r8d, 1; bErase
0x1805111a7  call    cs:__imp_InvalidateRect
0x1805111ad  mov     rcx, [rbx+38h]; hWnd
0x1805111b1  call    cs:__imp_UpdateWindow
0x1805111b7  mov     rcx, [rbx+38h]; hDlg
0x1805111bb  lea     r8, [rbp+550h+var_220]; lpString
0x1805111c2  mov     edx, 347Dh; nIDDlgItem
0x1805111c7  call    cs:__imp_SetDlgItemTextW
0x1805111cd  test    r12, r12
0x1805111d0  jz      short loc_180511222
0x1805111d2  xorps   xmm0, xmm0
0x1805111d5  lea     rdx, [rsp+650h+Rect]; lpRect
0x1805111da  mov     rcx, r12; hWnd
0x1805111dd  movups  xmmword ptr [rsp+650h+Rect.left], xmm0
0x1805111e2  call    cs:__imp_GetWindowRect
0x1805111e8  test    eax, eax
0x1805111ea  jz      short loc_180511222
0x1805111ec  mov     rdx, [rbx+38h]; hWndTo
0x1805111f0  lea     r8, [rsp+650h+Rect]; lpPoints
0x1805111f5  mov     r9d, 2; cPoints
0x1805111fb  xor     ecx, ecx; hWndFrom
0x1805111fd  call    cs:__imp_MapWindowPoints
0x180511203  mov     rcx, [rbx+38h]; hWnd
0x180511207  lea     rdx, [rsp+650h+Rect]; lpRect
0x18051120c  mov     r8d, 1; bErase
0x180511212  call    cs:__imp_InvalidateRect
0x180511218  mov     rcx, [rbx+38h]; hWnd
0x18051121c  call    cs:__imp_UpdateWindow
0x180511222  mov     rcx, [rbp+550h+var_20]
0x180511229  xor     rcx, rsp; StackCookie
0x18051122c  call    __security_check_cookie
0x180511231  lea     r11, [rsp+650h+var_10]
0x180511239  mov     rbx, [r11+28h]
0x18051123d  mov     r12, [r11+30h]
0x180511241  mov     rsp, r11
0x180511244  pop     r15
0x180511246  pop     r14
0x180511248  pop     rbp
0x180511249  retn
```
