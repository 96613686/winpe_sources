# Ext3MFThumbnailProvider::CreatePreviewWindow(HBITMAP__ *)

- ea: `0x180003e64`
- end: `0x180003f2d`
- name: `?CreatePreviewWindow@Ext3MFThumbnailProvider@@AEAAJPEAUHBITMAP__@@@Z`
- size: `201`
- prototype: `int(Ext3MFThumbnailProvider *__hidden this, HBITMAP)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f40`

## callees

- `0x180003e64`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003ea0`
- `KERNEL32!GetLastError` at `0x180003ea0`
- `USER32!ShowWindow` at `0x180003f15`
- `USER32!ShowWindow` at `0x180003f15`
- `USER32!GetDlgItem` at `0x180003ef2`
- `USER32!GetDlgItem` at `0x180003ef2`
- `USER32!SendMessageW` at `0x180003f06`
- `USER32!SendMessageW` at `0x180003f06`
- `USER32!SetWindowPos` at `0x180003ee3`
- `USER32!SetWindowPos` at `0x180003ee3`
- `USER32!CreateDialogParamW` at `0x180003e91`
- `USER32!CreateDialogParamW` at `0x180003e91`

## pseudocode

```c
__int64 __fastcall Ext3MFThumbnailProvider::CreatePreviewWindow(Ext3MFThumbnailProvider *this, LPARAM a2)
{
  signed int v2; // ebx
  HWND DialogParamW; // rax
  signed int LastError; // eax
  HWND DlgItem; // rax

  v2 = 0;
  DialogParamW = CreateDialogParamW(g_hInst, (LPCWSTR)0x65, *((HWND *)this + 8), 0, 0);
  *((_QWORD *)this + 11) = DialogParamW;
  if ( DialogParamW )
    goto LABEL_5;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_5:
    SetWindowPos(
      *((HWND *)this + 11),
      0,
      *((_DWORD *)this + 18),
      *((_DWORD *)this + 19),
      *((_DWORD *)this + 20) - *((_DWORD *)this + 18),
      *((_DWORD *)this + 21) - *((_DWORD *)this + 19),
      0x16u);
    DlgItem = GetDlgItem(*((HWND *)this + 11), 1002);
    SendMessageW(DlgItem, 0x172u, 0, a2);
    ShowWindow(*((HWND *)this + 11), 5);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003e64  mov     [rsp+arg_0], rbx
0x180003e69  mov     [rsp+arg_8], rsi
0x180003e6e  push    rdi
0x180003e6f  sub     rsp, 40h
0x180003e73  mov     r8, [rcx+40h]; hWndParent
0x180003e77  xor     ebx, ebx
0x180003e79  mov     rsi, rdx
0x180003e7c  mov     [rsp+48h+dwInitParam], rbx; dwInitParam
0x180003e81  mov     rdi, rcx
0x180003e84  xor     r9d, r9d; lpDialogFunc
0x180003e87  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x180003e8e  lea     edx, [rbx+65h]; lpTemplateName
0x180003e91  call    cs:__imp_CreateDialogParamW
0x180003e97  mov     [rdi+58h], rax
0x180003e9b  test    rax, rax
0x180003e9e  jnz     short loc_180003EB9
0x180003ea0  call    cs:__imp_GetLastError
0x180003ea6  mov     ebx, eax
0x180003ea8  test    eax, eax
0x180003eaa  jle     short loc_180003EB5
0x180003eac  movzx   ebx, ax
0x180003eaf  or      ebx, 80070000h
0x180003eb5  test    ebx, ebx
0x180003eb7  js      short loc_180003F1B
0x180003eb9  mov     ecx, [rdi+54h]
0x180003ebc  xor     edx, edx; hWndInsertAfter
0x180003ebe  mov     r9d, [rdi+4Ch]; Y
0x180003ec2  sub     ecx, r9d
0x180003ec5  mov     eax, [rdi+50h]
0x180003ec8  mov     r8d, [rdi+48h]; X
0x180003ecc  sub     eax, r8d
0x180003ecf  mov     [rsp+48h+uFlags], 16h; uFlags
0x180003ed7  mov     [rsp+48h+cy], ecx; cy
0x180003edb  mov     rcx, [rdi+58h]; hWnd
0x180003edf  mov     dword ptr [rsp+48h+dwInitParam], eax; cx
0x180003ee3  call    cs:__imp_SetWindowPos
0x180003ee9  mov     rcx, [rdi+58h]; hDlg
0x180003eed  mov     edx, 3EAh; nIDDlgItem
0x180003ef2  call    cs:__imp_GetDlgItem
0x180003ef8  mov     r9, rsi; lParam
0x180003efb  xor     r8d, r8d; wParam
0x180003efe  mov     rcx, rax; hWnd
0x180003f01  mov     edx, 172h; Msg
0x180003f06  call    cs:__imp_SendMessageW
0x180003f0c  mov     rcx, [rdi+58h]; hWnd
0x180003f10  mov     edx, 5; nCmdShow
0x180003f15  call    cs:__imp_ShowWindow
0x180003f1b  mov     rsi, [rsp+48h+arg_8]
0x180003f20  mov     eax, ebx
0x180003f22  mov     rbx, [rsp+48h+arg_0]
0x180003f27  add     rsp, 40h
0x180003f2b  pop     rdi
0x180003f2c  retn
```
