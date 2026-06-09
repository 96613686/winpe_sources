# AdvancedPage::ConfigureCalibrationControls(int)

- ea: `0x18000fbb4`
- end: `0x18000fc28`
- name: `?ConfigureCalibrationControls@AdvancedPage@@AEAAXH@Z`
- size: `116`
- prototype: `void __fastcall(HWND *this, BOOL)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000fc80`
- `0x180010388`

## import_xrefs

- `USER32!SendMessageW` at `0x18000fc03`
- `USER32!SendMessageW` at `0x18000fc03`
- `USER32!RedrawWindow` at `0x18000fc21`
- `USER32!GetDlgItem` at `0x18000fbcc`
- `USER32!GetDlgItem` at `0x18000fbe6`
- `USER32!GetDlgItem` at `0x18000fbcc`
- `USER32!GetDlgItem` at `0x18000fbe6`
- `USER32!EnableWindow` at `0x18000fbd7`
- `USER32!EnableWindow` at `0x18000fbd7`

## pseudocode

```c
void __fastcall AdvancedPage::ConfigureCalibrationControls(HWND *this, BOOL a2)
{
  HWND DlgItem; // rax
  HWND v5; // rbx

  DlgItem = GetDlgItem(this[1], 1320);
  EnableWindow(DlgItem, a2);
  v5 = GetDlgItem(this[1], 1321);
  SendMessageW(v5, 0xF1u, a2, 0);
  RedrawWindow(v5, 0, 0, 0x101u);
}

```

## disassembly

```asm
0x18000fbb4  mov     [rsp+arg_0], rbx
0x18000fbb9  push    rdi
0x18000fbba  sub     rsp, 20h
0x18000fbbe  mov     edi, edx
0x18000fbc0  mov     rbx, rcx
0x18000fbc3  mov     rcx, [rcx+8]; hDlg
0x18000fbc7  mov     edx, 528h; nIDDlgItem
0x18000fbcc  call    cs:__imp_GetDlgItem
0x18000fbd2  mov     rcx, rax; hWnd
0x18000fbd5  mov     edx, edi; bEnable
0x18000fbd7  call    cs:__imp_EnableWindow
0x18000fbdd  mov     rcx, [rbx+8]; hDlg
0x18000fbe1  mov     edx, 529h; nIDDlgItem
0x18000fbe6  call    cs:__imp_GetDlgItem
0x18000fbec  xor     r8d, r8d
0x18000fbef  mov     edx, 0F1h; Msg
0x18000fbf4  test    edi, edi
0x18000fbf6  mov     rcx, rax; hWnd
0x18000fbf9  mov     rbx, rax
0x18000fbfc  setnz   r8b; wParam
0x18000fc00  xor     r9d, r9d; lParam
0x18000fc03  call    cs:__imp_SendMessageW
0x18000fc09  mov     r9d, 101h
0x18000fc0f  xor     r8d, r8d
0x18000fc12  xor     edx, edx
0x18000fc14  mov     rcx, rbx
0x18000fc17  mov     rbx, [rsp+28h+arg_0]
0x18000fc1c  add     rsp, 20h
0x18000fc20  pop     rdi
0x18000fc21  jmp     cs:__imp_RedrawWindow
```
