# CViewExpiringCertificatesDialog::SetCheckboxImageList(void)

- ea: `0x180014e5c`
- end: `0x180014f10`
- name: `?SetCheckboxImageList@CViewExpiringCertificatesDialog@@AEAAXXZ`
- size: `180`
- prototype: `void __fastcall(CViewExpiringCertificatesDialog *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014aac`

## callees

- `0x180007938`
- `0x180015884`

## import_xrefs

- `GDI32!CreateCompatibleBitmap` at `0x180014ed8`
- `GDI32!CreateCompatibleBitmap` at `0x180014ed8`
- `GDI32!DeleteObject` at `0x180014eef`
- `GDI32!DeleteObject` at `0x180014eef`
- `USER32!GetDC` at `0x180014ea1`
- `USER32!GetDC` at `0x180014ea1`
- `USER32!ReleaseDC` at `0x180014efa`
- `USER32!ReleaseDC` at `0x180014efa`
- `USER32!SendMessageW` at `0x180014e80`
- `USER32!SendMessageW` at `0x180014e96`
- `USER32!SendMessageW` at `0x180014e80`
- `USER32!SendMessageW` at `0x180014e96`

## pseudocode

```c
void __fastcall CViewExpiringCertificatesDialog::SetCheckboxImageList(HWND *this)
{
  LRESULT v2; // rbx
  HDC DC; // rax
  HDC v4; // rsi
  HBITMAP CompatibleBitmap; // rdi
  int cy; // [rsp+30h] [rbp+8h] BYREF
  int v7; // [rsp+38h] [rbp+10h] BYREF

  SendMessageW(this[8], 0x1036u, 0, 4);
  v2 = SendMessageW(this[8], 0x1002u, 2u, 0);
  DC = GetDC(0);
  v7 = 0;
  cy = 0;
  v4 = DC;
  IsolationAwareImageList_GetIconSize(v2, &v7, &cy);
  CompatibleBitmap = CreateCompatibleBitmap(v4, v7, cy);
  IsolationAwareImageList_AddMasked(v2, CompatibleBitmap);
  DeleteObject(CompatibleBitmap);
  ReleaseDC(0, v4);
}

```

## disassembly

```asm
0x180014e5c  mov     [rsp+arg_10], rbx
0x180014e61  mov     [rsp+arg_18], rsi
0x180014e66  push    rdi
0x180014e67  sub     rsp, 20h
0x180014e6b  mov     rbx, rcx
0x180014e6e  mov     r9d, 4; lParam
0x180014e74  mov     rcx, [rcx+40h]; hWnd
0x180014e78  xor     r8d, r8d; wParam
0x180014e7b  mov     edx, 1036h; Msg
0x180014e80  call    cs:__imp_SendMessageW
0x180014e86  mov     rcx, [rbx+40h]; hWnd
0x180014e8a  xor     r9d, r9d; lParam
0x180014e8d  mov     edx, 1002h; Msg
0x180014e92  lea     r8d, [r9+2]; wParam
0x180014e96  call    cs:__imp_SendMessageW
0x180014e9c  xor     ecx, ecx; hWnd
0x180014e9e  mov     rbx, rax
0x180014ea1  call    cs:__imp_GetDC
0x180014ea7  lea     r8, [rsp+28h+cy]
0x180014eac  mov     [rsp+28h+arg_8], 0
0x180014eb4  lea     rdx, [rsp+28h+arg_8]
0x180014eb9  mov     [rsp+28h+cy], 0
0x180014ec1  mov     rcx, rbx
0x180014ec4  mov     rsi, rax
0x180014ec7  call    IsolationAwareImageList_GetIconSize
0x180014ecc  mov     r8d, [rsp+28h+cy]; cy
0x180014ed1  mov     rcx, rsi; hdc
0x180014ed4  mov     edx, [rsp+28h+arg_8]; cx
0x180014ed8  call    cs:__imp_CreateCompatibleBitmap
0x180014ede  mov     rdx, rax
0x180014ee1  mov     rcx, rbx
0x180014ee4  mov     rdi, rax
0x180014ee7  call    IsolationAwareImageList_AddMasked
0x180014eec  mov     rcx, rdi; ho
0x180014eef  call    cs:__imp_DeleteObject
0x180014ef5  mov     rdx, rsi; hDC
0x180014ef8  xor     ecx, ecx; hWnd
0x180014efa  call    cs:__imp_ReleaseDC
0x180014f00  mov     rbx, [rsp+28h+arg_10]
0x180014f05  mov     rsi, [rsp+28h+arg_18]
0x180014f0a  add     rsp, 20h
0x180014f0e  pop     rdi
0x180014f0f  retn
```
