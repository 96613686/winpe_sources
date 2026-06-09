# CDeviceSettingsDialog::OpenSelectFolderDialog(HWND__ *)

- ea: `0x1800117e0`
- end: `0x18001189e`
- name: `?OpenSelectFolderDialog@CDeviceSettingsDialog@@AEBAKPEAUHWND__@@@Z`
- size: `190`
- prototype: `unsigned int(CDeviceSettingsDialog *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180011310`

## callees

- `0x18000d450`
- `0x18000edb0`
- `0x1800117e0`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180011828`
- `KERNEL32!GetLastError` at `0x18001184c`
- `KERNEL32!GetLastError` at `0x180011828`
- `KERNEL32!GetLastError` at `0x18001184c`
- `USER32!LoadStringW` at `0x18001181e`
- `USER32!LoadStringW` at `0x18001181e`

## pseudocode

```c
DWORD __fastcall CDeviceSettingsDialog::OpenSelectFolderDialog(HINSTANCE *this, HWND a2)
{
  __int64 v4; // r8
  DWORD LastError; // ebx
  WCHAR Buffer[64]; // [rsp+30h] [rbp-98h] BYREF

  if ( !LoadStringW(this[1], 0x1231u, Buffer, 60) )
    return GetLastError();
  LastError = 0;
  if ( !(unsigned int)BrowseForDirectory(a2, 4549, v4, Buffer, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 122 )
      FaxMsgBox(a2, this[1], 4656);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800117e0  mov     [rsp+arg_10], rbx
0x1800117e5  mov     [rsp+arg_18], rsi
0x1800117ea  push    rdi
0x1800117eb  sub     rsp, 0C0h
0x1800117f2  mov     rax, cs:__security_cookie
0x1800117f9  xor     rax, rsp
0x1800117fc  mov     [rsp+0C8h+var_18], rax
0x180011804  mov     rdi, rdx
0x180011807  lea     r8, [rsp+0C8h+Buffer]; lpBuffer
0x18001180c  mov     rsi, rcx
0x18001180f  mov     edx, 1231h; uID
0x180011814  mov     rcx, [rcx+8]; hInstance
0x180011818  mov     r9d, 3Ch ; '<'; cchBufferMax
0x18001181e  call    cs:__imp_LoadStringW
0x180011824  test    eax, eax
0x180011826  jnz     short loc_180011830
0x180011828  call    cs:__imp_GetLastError
0x18001182e  jmp     short loc_180011879
0x180011830  xor     ebx, ebx
0x180011832  lea     r9, [rsp+0C8h+Buffer]
0x180011837  mov     edx, 11C5h; nIDDlgItem
0x18001183c  mov     [rsp+0C8h+var_A8], ebx; int
0x180011840  mov     rcx, rdi; hDlg
0x180011843  call    BrowseForDirectory
0x180011848  test    eax, eax
0x18001184a  jnz     short loc_180011877
0x18001184c  call    cs:__imp_GetLastError
0x180011852  mov     ebx, eax
0x180011854  cmp     eax, 7Ah ; 'z'
0x180011857  jnz     short loc_180011877
0x180011859  mov     rdx, [rsi+8]
0x18001185d  mov     r9d, 1234h
0x180011863  mov     rcx, rdi
0x180011866  mov     [rsp+0C8h+var_A8], 10h
0x18001186e  lea     r8d, [r9-4]
0x180011872  call    FaxMsgBox
0x180011877  mov     eax, ebx
0x180011879  mov     rcx, [rsp+0C8h+var_18]
0x180011881  xor     rcx, rsp; StackCookie
0x180011884  call    __security_check_cookie
0x180011889  lea     r11, [rsp+0C8h+var_8]
0x180011891  mov     rbx, [r11+20h]
0x180011895  mov     rsi, [r11+28h]
0x180011899  mov     rsp, r11
0x18001189c  pop     rdi
0x18001189d  retn
```
