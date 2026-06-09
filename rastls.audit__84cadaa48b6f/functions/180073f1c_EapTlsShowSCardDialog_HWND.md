# EapTlsShowSCardDialog(HWND__ *)

- ea: `0x180073f1c`
- end: `0x180073f99`
- name: `?EapTlsShowSCardDialog@@YAPEAUHWND__@@PEAU1@@Z`
- size: `125`
- prototype: `HWND __fastcall(HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180074358`

## callees

- `0x1800730a4`
- `0x180073f1c`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x180073f6f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x180073f6f`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!CreateDialogParamW` at `0x180073f48`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!CreateDialogParamW` at `0x180073f48`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x180073f7e`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x180073f7e`

## pseudocode

```c
HWND __fastcall EapTlsShowSCardDialog(HWND a1)
{
  HWND DialogParamW; // rax
  int v3; // r8d
  HWND v4; // rbx

  DialogParamW = CreateDialogParamW(g_hInstance, (LPCWSTR)0x68, a1, StatusDialogProc, 1);
  v4 = DialogParamW;
  if ( DialogParamW )
  {
    CenterWindow(DialogParamW, a1, v3);
    ShowWindow(v4, 5);
    UpdateWindow(v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180073f1c  mov     [rsp+arg_0], rbx
0x180073f21  push    rdi
0x180073f22  sub     rsp, 30h
0x180073f26  mov     rdi, rcx
0x180073f29  mov     [rsp+38h+dwInitParam], 1; dwInitParam
0x180073f32  mov     r8, rcx; hWndParent
0x180073f35  lea     r9, ?StatusDialogProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180073f3c  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180073f43  mov     edx, 68h ; 'h'; lpTemplateName
0x180073f48  call    cs:__imp_CreateDialogParamW
0x180073f4f  nop     dword ptr [rax+rax+00h]
0x180073f54  mov     rbx, rax
0x180073f57  test    rax, rax
0x180073f5a  jz      short loc_180073F8A
0x180073f5c  mov     rdx, rdi; HWND
0x180073f5f  mov     rcx, rax; hWnd
0x180073f62  call    ?CenterWindow@@YAXPEAUHWND__@@0H@Z; CenterWindow(HWND__ *,HWND__ *,int)
0x180073f67  mov     edx, 5; nCmdShow
0x180073f6c  mov     rcx, rbx; hWnd
0x180073f6f  call    cs:__imp_ShowWindow
0x180073f76  nop     dword ptr [rax+rax+00h]
0x180073f7b  mov     rcx, rbx; hWnd
0x180073f7e  call    cs:__imp_UpdateWindow
0x180073f85  nop     dword ptr [rax+rax+00h]
0x180073f8a  mov     rax, rbx
0x180073f8d  mov     rbx, [rsp+38h+arg_0]
0x180073f92  add     rsp, 30h
0x180073f96  pop     rdi
0x180073f97  retn
```
