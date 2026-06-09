# DevicesPage::GetReadSettingsScope(void)

- ea: `0x18000ccc0`
- end: `0x18000cd01`
- name: `?GetReadSettingsScope@DevicesPage@@AEAA?AW4WCS_PROFILE_MANAGEMENT_SCOPE@@XZ`
- size: `65`
- prototype: `__int64 __fastcall(DevicesPage *this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000e3fc`
- `0x18000e558`
- `0x18000e7ac`

## callees

- `0x18000ccc0`

## import_xrefs

- `USER32!SendMessageW` at `0x18000cceb`
- `USER32!SendMessageW` at `0x18000cceb`
- `USER32!GetDlgItem` at `0x18000ccd7`
- `USER32!GetDlgItem` at `0x18000ccd7`

## pseudocode

```c
__int64 __fastcall DevicesPage::GetReadSettingsScope(DevicesPage *this)
{
  unsigned int v1; // ebx
  HWND DlgItem; // rax

  v1 = *((_DWORD *)this + 18);
  if ( v1 == 1 )
  {
    DlgItem = GetDlgItem(*((HWND *)this + 1), 1104);
    return SendMessageW(DlgItem, 0xF0u, 0, 0) != 0;
  }
  return v1;
}

```

## disassembly

```asm
0x18000ccc0  push    rbx
0x18000ccc2  sub     rsp, 20h
0x18000ccc6  mov     ebx, [rcx+48h]
0x18000ccc9  cmp     ebx, 1
0x18000cccc  jnz     short loc_18000CCF9
0x18000ccce  mov     rcx, [rcx+8]; hDlg
0x18000ccd2  mov     edx, 450h; nIDDlgItem
0x18000ccd7  call    cs:__imp_GetDlgItem
0x18000ccdd  xor     r9d, r9d; lParam
0x18000cce0  xor     r8d, r8d; wParam
0x18000cce3  mov     rcx, rax; hWnd
0x18000cce6  mov     edx, 0F0h; Msg
0x18000cceb  call    cs:__imp_SendMessageW
0x18000ccf1  xor     ecx, ecx
0x18000ccf3  test    rax, rax
0x18000ccf6  cmovz   ebx, ecx
0x18000ccf9  mov     eax, ebx
0x18000ccfb  add     rsp, 20h
0x18000ccff  pop     rbx
0x18000cd00  retn
```
