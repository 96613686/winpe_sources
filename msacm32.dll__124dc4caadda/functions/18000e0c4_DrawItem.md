# DrawItem

- ea: `0x18000e0c4`
- end: `0x18000e262`
- name: `DrawItem`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fba0`

## callees

- `0x180009270`
- `0x18000a250`
- `0x18000e0c4`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18000e154`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18000e154`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x18000e11d`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x18000e21b`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x18000e11d`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x18000e21b`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x18000e138`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x18000e227`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x18000e138`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x18000e227`
- `ext-ms-win-ntuser-draw-l1-1-0!DrawFocusRect` at `0x18000e184`
- `ext-ms-win-ntuser-draw-l1-1-0!DrawFocusRect` at `0x18000e184`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x18000e197`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x18000e197`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000e1ad`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000e1d0`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000e1ad`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000e1d0`
- `ext-ms-win-ntuser-misc-l1-1-0!TabbedTextOutW` at `0x18000e200`
- `ext-ms-win-ntuser-misc-l1-1-0!TabbedTextOutW` at `0x18000e200`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000e209`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000e209`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000e111`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000e12d`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000e14c`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000e111`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000e12d`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x18000e14c`

## pseudocode

```c
__int64 __fastcall DrawItem(__int64 a1, __int64 a2)
{
  DWORD SysColor; // eax
  COLORREF v5; // eax
  HDC v6; // rbx
  COLORREF v7; // esi
  DWORD v8; // eax
  COLORREF v9; // ebp
  int v10; // ecx
  DWORD v11; // eax
  HBRUSH SolidBrush; // rax
  HBRUSH v13; // rbx
  int chCount; // r15d
  WCHAR lParam[128]; // [rsp+40h] [rbp-138h] BYREF

  if ( !(unsigned __int8)IsSendMessageWPresent() )
    return 0;
  if ( (*(_BYTE *)(a2 + 16) & 1) != 0 )
  {
    SysColor = GetSysColor(13);
    v5 = SetBkColor(*(HDC *)(a2 + 32), SysColor);
    v6 = *(HDC *)(a2 + 32);
    v7 = v5;
    v8 = GetSysColor(14);
    v9 = SetTextColor(v6, v8);
    v10 = 13;
  }
  else
  {
    v7 = 0;
    v9 = 0;
    v10 = 5;
  }
  v11 = GetSysColor(v10);
  SolidBrush = CreateSolidBrush(v11);
  v13 = SolidBrush;
  if ( !SolidBrush )
    return 0;
  if ( *(_DWORD *)(a2 + 12) == 1 || *(_DWORD *)(a2 + 12) == 2 )
  {
    FillRect(*(HDC *)(a2 + 32), (const RECT *)(a2 + 40), SolidBrush);
    chCount = SendMessageW(*(HWND *)(a2 + 24), 0x149u, *(int *)(a2 + 8), 0);
    if ( (unsigned int)(chCount - 1) <= 0xFFFFFFFD )
    {
      SendMessageW(*(HWND *)(a2 + 24), 0x148u, *(int *)(a2 + 8), (LPARAM)lParam);
      TabbedTextOutW(
        *(HDC *)(a2 + 32),
        *(_DWORD *)(a2 + 40),
        *(_DWORD *)(a2 + 44),
        lParam,
        chCount,
        1,
        (const INT *)(a1 + 48),
        *(_DWORD *)(a2 + 40));
    }
  }
  else if ( *(_DWORD *)(a2 + 12) == 4 )
  {
    DrawFocusRect(*(HDC *)(a2 + 32), (const RECT *)(a2 + 40));
  }
  DeleteObject(v13);
  if ( (*(_BYTE *)(a2 + 16) & 1) != 0 )
  {
    SetBkColor(*(HDC *)(a2 + 32), v7);
    SetTextColor(*(HDC *)(a2 + 32), v9);
  }
  return 1;
}

```

## disassembly

```asm
0x18000e0c4  mov     [rsp+arg_10], rbx
0x18000e0c9  mov     [rsp+arg_18], rbp
0x18000e0ce  push    rsi
0x18000e0cf  push    rdi
0x18000e0d0  push    r13
0x18000e0d2  push    r14
0x18000e0d4  push    r15
0x18000e0d6  sub     rsp, 150h
0x18000e0dd  mov     rax, cs:__security_cookie
0x18000e0e4  xor     rax, rsp
0x18000e0e7  mov     [rsp+178h+var_38], rax
0x18000e0ef  mov     rdi, rdx
0x18000e0f2  mov     r13, rcx
0x18000e0f5  call    IsSendMessageWPresent
0x18000e0fa  test    al, al
0x18000e0fc  jz      loc_18000E234
0x18000e102  test    byte ptr [rdi+10h], 1
0x18000e106  jz      short loc_18000E145
0x18000e108  mov     r14d, 0Dh
0x18000e10e  mov     ecx, r14d; nIndex
0x18000e111  call    cs:__imp_GetSysColor
0x18000e117  mov     rcx, [rdi+20h]; hdc
0x18000e11b  mov     edx, eax; color
0x18000e11d  call    cs:__imp_SetBkColor
0x18000e123  mov     rbx, [rdi+20h]
0x18000e127  lea     ecx, [r14+1]; nIndex
0x18000e12b  mov     esi, eax
0x18000e12d  call    cs:__imp_GetSysColor
0x18000e133  mov     edx, eax; color
0x18000e135  mov     rcx, rbx; hdc
0x18000e138  call    cs:__imp_SetTextColor
0x18000e13e  mov     ebp, eax
0x18000e140  mov     ecx, r14d
0x18000e143  jmp     short loc_18000E14C
0x18000e145  xor     esi, esi
0x18000e147  xor     ebp, ebp
0x18000e149  lea     ecx, [rsi+5]; nIndex
0x18000e14c  call    cs:__imp_GetSysColor
0x18000e152  mov     ecx, eax; color
0x18000e154  call    cs:__imp_CreateSolidBrush
0x18000e15a  mov     rbx, rax
0x18000e15d  test    rax, rax
0x18000e160  jz      loc_18000E234
0x18000e166  mov     ecx, [rdi+0Ch]
0x18000e169  sub     ecx, 1
0x18000e16c  jz      short loc_18000E18C
0x18000e16e  sub     ecx, 1
0x18000e171  jz      short loc_18000E18C
0x18000e173  cmp     ecx, 2
0x18000e176  jnz     loc_18000E206
0x18000e17c  mov     rcx, [rdi+20h]; hDC
0x18000e180  lea     rdx, [rdi+28h]; lprc
0x18000e184  call    cs:__imp_DrawFocusRect
0x18000e18a  jmp     short loc_18000E206
0x18000e18c  mov     rcx, [rdi+20h]; hDC
0x18000e190  lea     rdx, [rdi+28h]; lprc
0x18000e194  mov     r8, rbx; hbr
0x18000e197  call    cs:__imp_FillRect
0x18000e19d  movsxd  r8, dword ptr [rdi+8]; wParam
0x18000e1a1  xor     r9d, r9d; lParam
0x18000e1a4  mov     rcx, [rdi+18h]; hWnd
0x18000e1a8  mov     edx, 149h; Msg
0x18000e1ad  call    cs:__imp_SendMessageW
0x18000e1b3  mov     r15, rax
0x18000e1b6  lea     ecx, [rax-1]
0x18000e1b9  cmp     ecx, 0FFFFFFFDh
0x18000e1bc  ja      short loc_18000E206
0x18000e1be  movsxd  r8, dword ptr [rdi+8]; wParam
0x18000e1c2  lea     r9, [rsp+178h+lParam]; lParam
0x18000e1c7  mov     rcx, [rdi+18h]; hWnd
0x18000e1cb  mov     edx, 148h; Msg
0x18000e1d0  call    cs:__imp_SendMessageW
0x18000e1d6  mov     edx, [rdi+28h]; x
0x18000e1d9  lea     rcx, [r13+30h]
0x18000e1dd  mov     r8d, [rdi+2Ch]; y
0x18000e1e1  lea     r9, [rsp+178h+lParam]; lpString
0x18000e1e6  mov     [rsp+178h+nTabOrigin], edx; nTabOrigin
0x18000e1ea  mov     [rsp+178h+lpnTabStopPositions], rcx; lpnTabStopPositions
0x18000e1ef  mov     rcx, [rdi+20h]; hdc
0x18000e1f3  mov     [rsp+178h+nTabPositions], 1; nTabPositions
0x18000e1fb  mov     [rsp+178h+chCount], r15d; chCount
0x18000e200  call    cs:__imp_TabbedTextOutW
0x18000e206  mov     rcx, rbx; ho
0x18000e209  call    cs:__imp_DeleteObject
0x18000e20f  test    byte ptr [rdi+10h], 1
0x18000e213  jz      short loc_18000E22D
0x18000e215  mov     rcx, [rdi+20h]; hdc
0x18000e219  mov     edx, esi; color
0x18000e21b  call    cs:__imp_SetBkColor
0x18000e221  mov     rcx, [rdi+20h]; hdc
0x18000e225  mov     edx, ebp; color
0x18000e227  call    cs:__imp_SetTextColor
0x18000e22d  mov     eax, 1
0x18000e232  jmp     short loc_18000E236
0x18000e234  xor     eax, eax
0x18000e236  mov     rcx, [rsp+178h+var_38]
0x18000e23e  xor     rcx, rsp; StackCookie
0x18000e241  call    __security_check_cookie
0x18000e246  lea     r11, [rsp+178h+var_28]
0x18000e24e  mov     rbx, [r11+40h]
0x18000e252  mov     rbp, [r11+48h]
0x18000e256  mov     rsp, r11
0x18000e259  pop     r15
0x18000e25b  pop     r14
0x18000e25d  pop     r13
0x18000e25f  pop     rdi
0x18000e260  pop     rsi
0x18000e261  retn
```
