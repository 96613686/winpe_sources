# CIncomingConnectionSummaryPage::InitDialogControls(HWND__ *)

- ea: `0x18001cea0`
- end: `0x18001cf89`
- name: `?InitDialogControls@CIncomingConnectionSummaryPage@@AEAAXPEAUHWND__@@@Z`
- size: `233`
- prototype: `void(CIncomingConnectionSummaryPage *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001cf90`

## callees

- `0x1800116e4`
- `0x18001cea0`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001cef4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001cef4`
- `USER32!LoadImageW` at `0x18001cf4a`
- `USER32!LoadImageW` at `0x18001cf4a`
- `USER32!SetWindowTextW` at `0x18001cf04`
- `USER32!SetWindowTextW` at `0x18001cf04`
- `USER32!GetDlgItem` at `0x18001ceb7`
- `USER32!GetDlgItem` at `0x18001cec8`
- `USER32!GetDlgItem` at `0x18001ceb7`
- `USER32!GetDlgItem` at `0x18001cec8`
- `USER32!GetSystemMetrics` at `0x18001cf14`
- `USER32!GetSystemMetrics` at `0x18001cf21`
- `USER32!GetSystemMetrics` at `0x18001cf14`
- `USER32!GetSystemMetrics` at `0x18001cf21`
- `rtutils!TracePrintfExA` at `0x18001cf7a`
- `rtutils!TracePrintfExA` at `0x18001cf7a`

## pseudocode

```c
void __fastcall CIncomingConnectionSummaryPage::InitDialogControls(CIncomingConnectionSummaryPage *this, HWND a2)
{
  HWND DlgItem; // rdi
  HWND v5; // rsi
  int cy; // ebx
  int SystemMetrics; // eax
  HICON ImageW; // rax
  int v9; // eax
  DWORD nSize; // [rsp+70h] [rbp+18h] BYREF

  DlgItem = GetDlgItem(a2, 2043);
  v5 = GetDlgItem(a2, 2044);
  if ( DlgItem )
  {
    nSize = 16;
    *(_OWORD *)((char *)this + 88) = 0;
    *(_OWORD *)((char *)this + 104) = 0;
    if ( GetComputerNameW((LPWSTR)this + 44, &nSize) )
      SetWindowTextW(DlgItem, (LPCWSTR)this + 44);
  }
  if ( v5 )
  {
    cy = GetSystemMetrics(50);
    SystemMetrics = GetSystemMetrics(49);
    ImageW = (HICON)LoadImageW(hInst, (LPCWSTR)0x2711, 1u, SystemMetrics, cy, 0x8000u);
    v9 = HrReplaceAllImagesForCommandLinkButton(v5, ImageW);
    if ( v9 < 0 && g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Unable to add printer icon. hr = %#x", v9);
  }
}

```

## disassembly

```asm
0x18001cea0  push    rbx
0x18001cea2  push    rbp
0x18001cea3  push    rsi
0x18001cea4  push    rdi
0x18001cea5  sub     rsp, 38h
0x18001cea9  mov     rbx, rdx
0x18001ceac  mov     rbp, rcx
0x18001ceaf  mov     rcx, rbx; hDlg
0x18001ceb2  mov     edx, 7FBh; nIDDlgItem
0x18001ceb7  call    cs:__imp_GetDlgItem
0x18001cebd  mov     edx, 7FCh; nIDDlgItem
0x18001cec2  mov     rcx, rbx; hDlg
0x18001cec5  mov     rdi, rax
0x18001cec8  call    cs:__imp_GetDlgItem
0x18001cece  mov     rsi, rax
0x18001ced1  test    rdi, rdi
0x18001ced4  jz      short loc_18001CF0A
0x18001ced6  lea     rbx, [rbp+58h]
0x18001ceda  mov     [rsp+58h+nSize], 10h
0x18001cee2  xorps   xmm0, xmm0
0x18001cee5  lea     rdx, [rsp+58h+nSize]; nSize
0x18001ceea  movups  xmmword ptr [rbx], xmm0
0x18001ceed  mov     rcx, rbx; lpBuffer
0x18001cef0  movups  xmmword ptr [rbx+10h], xmm0
0x18001cef4  call    cs:__imp_GetComputerNameW
0x18001cefa  test    eax, eax
0x18001cefc  jz      short loc_18001CF0A
0x18001cefe  mov     rdx, rbx; lpString
0x18001cf01  mov     rcx, rdi; hWnd
0x18001cf04  call    cs:__imp_SetWindowTextW
0x18001cf0a  test    rsi, rsi
0x18001cf0d  jz      short loc_18001CF80
0x18001cf0f  mov     ecx, 32h ; '2'; nIndex
0x18001cf14  call    cs:__imp_GetSystemMetrics
0x18001cf1a  mov     ecx, 31h ; '1'; nIndex
0x18001cf1f  mov     ebx, eax
0x18001cf21  call    cs:__imp_GetSystemMetrics
0x18001cf27  mov     rcx, cs:hInst; hInst
0x18001cf2e  mov     edx, 2711h; name
0x18001cf33  mov     [rsp+58h+fuLoad], 8000h; fuLoad
0x18001cf3b  mov     r9d, eax; cx
0x18001cf3e  mov     [rsp+58h+cy], ebx; cy
0x18001cf42  mov     ebx, 1
0x18001cf47  mov     r8d, ebx; type
0x18001cf4a  call    cs:__imp_LoadImageW
0x18001cf50  mov     r8d, ebx
0x18001cf53  mov     rcx, rsi; hWnd
0x18001cf56  mov     rdx, rax; hicon
0x18001cf59  call    HrReplaceAllImagesForCommandLinkButton
0x18001cf5e  test    eax, eax
0x18001cf60  jns     short loc_18001CF80
0x18001cf62  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001cf68  cmp     ecx, 0FFFFFFFFh
0x18001cf6b  jz      short loc_18001CF80
0x18001cf6d  mov     r9d, eax
0x18001cf70  lea     r8, aUnableToAddPri; "Unable to add printer icon. hr = %#x"
0x18001cf77  lea     edx, [rbx+0Bh]; dwFlags
0x18001cf7a  call    cs:__imp_TracePrintfExA
0x18001cf80  add     rsp, 38h
0x18001cf84  pop     rdi
0x18001cf85  pop     rsi
0x18001cf86  pop     rbp
0x18001cf87  pop     rbx
0x18001cf88  retn
```
