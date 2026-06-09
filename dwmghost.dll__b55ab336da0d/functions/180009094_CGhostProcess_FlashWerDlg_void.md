# CGhostProcess::FlashWerDlg(void)

- ea: `0x180009094`
- end: `0x180009189`
- name: `?FlashWerDlg@CGhostProcess@@QEAAHXZ`
- size: `245`
- prototype: `__int64 __fastcall(CGhostProcess *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006bb8`

## callees

- `0x180009094`
- `0x180009f60`
- `0x180009f70`

## import_xrefs

- `USER32!MessageBeep` at `0x18000916e`
- `USER32!MessageBeep` at `0x18000916e`
- `USER32!FlashWindowEx` at `0x180009164`
- `USER32!FlashWindowEx` at `0x180009164`
- `USER32!GetCaretBlinkTime` at `0x180009147`
- `USER32!GetCaretBlinkTime` at `0x180009147`
- `USER32!SystemParametersInfoW` at `0x180009136`
- `USER32!SystemParametersInfoW` at `0x180009136`
- `ext-ms-win-ntuser-window-l1-1-4!IsWindowEnabled` at `0x1800090e9`
- `ext-ms-win-ntuser-window-l1-1-4!IsWindowEnabled` at `0x1800090e9`
- `ext-ms-win-ntuser-window-l1-1-0!EnumWindows` at `0x1800090fe`
- `ext-ms-win-ntuser-window-l1-1-0!EnumWindows` at `0x1800090fe`
- `ext-ms-win-ntuser-window-l1-1-0!SetForegroundWindow` at `0x180009178`
- `ext-ms-win-ntuser-window-l1-1-0!SetForegroundWindow` at `0x180009178`
- `ext-ms-win-ntuser-window-l1-1-1!IsWindowVisible` at `0x1800090be`
- `ext-ms-win-ntuser-window-l1-1-1!IsWindowVisible` at `0x1800090be`

## pseudocode

```c
__int64 __fastcall CGhostProcess::FlashWerDlg(CGhostProcess *this)
{
  unsigned int v2; // edi
  HWND v3; // rcx
  BOOL v4; // eax
  UINT uCount; // ecx
  UINT CaretBlinkTime; // eax
  $C811A85A3CBAF233E045382DA27E29BF pfwi; // [rsp+20h] [rbp-28h] BYREF
  HWND hWnd; // [rsp+70h] [rbp+28h] BYREF

  v2 = 0;
  hWnd = 0;
  CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
  v3 = (HWND)*((_QWORD *)this + 16);
  if ( v3 && IsWindowVisible(v3) )
    hWnd = (HWND)*((_QWORD *)this + 16);
  CLock::Release((LPCRITICAL_SECTION)((char *)this + 16));
  if ( hWnd )
  {
    if ( !IsWindowEnabled(hWnd) )
      EnumWindows(CGhostProcess::s_FindWerDlgOwnerEnumProc, (LPARAM)&hWnd);
    if ( hWnd )
    {
      *(_QWORD *)&pfwi.cbSize = 32;
      pfwi.dwFlags = 3;
      *(_QWORD *)&pfwi.uCount = 0;
      *(&pfwi.dwTimeout + 1) = 0;
      pfwi.hwnd = hWnd;
      v4 = SystemParametersInfoW(0x2004u, 0, &pfwi.uCount, 0);
      uCount = pfwi.uCount;
      if ( !v4 )
        uCount = 3;
      pfwi.uCount = uCount;
      CaretBlinkTime = GetCaretBlinkTime();
      if ( CaretBlinkTime )
        pfwi.dwTimeout = CaretBlinkTime >> 3;
      else
        pfwi.dwTimeout = 62;
      v2 = FlashWindowEx(&pfwi);
      MessageBeep(0);
      SetForegroundWindow(hWnd);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180009094  push    rbp
0x180009096  push    rbx
0x180009097  push    rsi
0x180009098  push    rdi
0x180009099  mov     rbp, rsp
0x18000909c  sub     rsp, 48h
0x1800090a0  mov     rbx, rcx
0x1800090a3  xor     edi, edi
0x1800090a5  add     rcx, 10h; lpCriticalSection
0x1800090a9  mov     [rbp+hWnd], rdi
0x1800090ad  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x1800090b2  mov     rcx, [rbx+80h]; hWnd
0x1800090b9  test    rcx, rcx
0x1800090bc  jz      short loc_1800090D3
0x1800090be  call    cs:__imp_IsWindowVisible
0x1800090c4  test    eax, eax
0x1800090c6  jz      short loc_1800090D3
0x1800090c8  mov     rax, [rbx+80h]
0x1800090cf  mov     [rbp+hWnd], rax
0x1800090d3  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800090d7  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x1800090dc  mov     rcx, [rbp+hWnd]; hWnd
0x1800090e0  test    rcx, rcx
0x1800090e3  jz      loc_18000917E
0x1800090e9  call    cs:__imp_IsWindowEnabled
0x1800090ef  test    eax, eax
0x1800090f1  jnz     short loc_180009104
0x1800090f3  lea     rdx, [rbp+hWnd]; lParam
0x1800090f7  lea     rcx, ?s_FindWerDlgOwnerEnumProc@CGhostProcess@@CAHPEAUHWND__@@_J@Z; lpEnumFunc
0x1800090fe  call    cs:__imp_EnumWindows
0x180009104  mov     rax, [rbp+hWnd]
0x180009108  test    rax, rax
0x18000910b  jz      short loc_18000917E
0x18000910d  mov     ebx, 3
0x180009112  mov     qword ptr [rbp+pfwi.cbSize], 20h ; ' '
0x18000911a  xor     r9d, r9d; fWinIni
0x18000911d  mov     [rbp+pfwi.dwFlags], ebx
0x180009120  lea     r8, [rbp+pfwi.uCount]; pvParam
0x180009124  mov     qword ptr [rbp+pfwi.uCount], rdi
0x180009128  xor     edx, edx; uiParam
0x18000912a  mov     dword ptr [rbp+pfwi+1Ch], edi
0x18000912d  mov     ecx, 2004h; uiAction
0x180009132  mov     [rbp+pfwi.hwnd], rax
0x180009136  call    cs:__imp_SystemParametersInfoW
0x18000913c  mov     ecx, [rbp+pfwi.uCount]
0x18000913f  test    eax, eax
0x180009141  cmovz   ecx, ebx
0x180009144  mov     [rbp+pfwi.uCount], ecx
0x180009147  call    cs:__imp_GetCaretBlinkTime
0x18000914d  test    eax, eax
0x18000914f  jz      short loc_180009159
0x180009151  shr     eax, 3
0x180009154  mov     [rbp+pfwi.dwTimeout], eax
0x180009157  jmp     short loc_180009160
0x180009159  mov     [rbp+pfwi.dwTimeout], 3Eh ; '>'
0x180009160  lea     rcx, [rbp+pfwi]; pfwi
0x180009164  call    cs:__imp_FlashWindowEx
0x18000916a  xor     ecx, ecx; uType
0x18000916c  mov     edi, eax
0x18000916e  call    cs:__imp_MessageBeep
0x180009174  mov     rcx, [rbp+hWnd]; hWnd
0x180009178  call    cs:__imp_SetForegroundWindow
0x18000917e  mov     eax, edi
0x180009180  add     rsp, 48h
0x180009184  pop     rdi
0x180009185  pop     rsi
0x180009186  pop     rbx
0x180009187  pop     rbp
0x180009188  retn
```
