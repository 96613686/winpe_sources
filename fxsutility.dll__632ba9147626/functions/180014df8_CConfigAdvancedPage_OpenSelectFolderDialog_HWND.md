# CConfigAdvancedPage::OpenSelectFolderDialog(HWND__ *)

- ea: `0x180014df8`
- end: `0x180014ee8`
- name: `?OpenSelectFolderDialog@CConfigAdvancedPage@@AEBAKPEAUHWND__@@@Z`
- size: `240`
- prototype: `unsigned int(CConfigAdvancedPage *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180014ad0`

## callees

- `0x18000d450`
- `0x18000edb0`
- `0x180014df8`
- `0x180015cf0`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180014e40`
- `KERNEL32!GetLastError` at `0x180014e7c`
- `KERNEL32!GetLastError` at `0x180014e40`
- `KERNEL32!GetLastError` at `0x180014e7c`
- `USER32!LoadStringW` at `0x180014e36`
- `USER32!LoadStringW` at `0x180014e36`

## pseudocode

```c
DWORD __fastcall CConfigAdvancedPage::OpenSelectFolderDialog(HINSTANCE *this, HWND a2)
{
  __int64 v4; // r8
  DWORD LastError; // ebx
  WCHAR Buffer[64]; // [rsp+30h] [rbp-98h] BYREF

  if ( !LoadStringW(this[1], 0x1231u, Buffer, 60) )
    return GetLastError();
  if ( (unsigned int)BrowseForDirectory(a2, 4521, v4, Buffer, 0x51u) )
  {
    LastError = 0;
    (*((void (__fastcall **)(HINSTANCE *, HWND))*this + 10))(this, a2);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      (*((void (__fastcall **)(HINSTANCE *))*this + 6))(this);
      FaxMsgBox(a2, this[1], 4656);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180014df8  mov     [rsp+arg_10], rbx
0x180014dfd  mov     [rsp+arg_18], rsi
0x180014e02  push    rdi
0x180014e03  sub     rsp, 0C0h
0x180014e0a  mov     rax, cs:__security_cookie
0x180014e11  xor     rax, rsp
0x180014e14  mov     [rsp+0C8h+var_18], rax
0x180014e1c  mov     rsi, rdx
0x180014e1f  lea     r8, [rsp+0C8h+Buffer]; lpBuffer
0x180014e24  mov     rdi, rcx
0x180014e27  mov     edx, 1231h; uID
0x180014e2c  mov     rcx, [rcx+8]; hInstance
0x180014e30  mov     r9d, 3Ch ; '<'; cchBufferMax
0x180014e36  call    cs:__imp_LoadStringW
0x180014e3c  test    eax, eax
0x180014e3e  jnz     short loc_180014E48
0x180014e40  call    cs:__imp_GetLastError
0x180014e46  jmp     short loc_180014EC3
0x180014e48  lea     r9, [rsp+0C8h+Buffer]
0x180014e4d  mov     [rsp+0C8h+var_A8], 51h ; 'Q'; int
0x180014e55  mov     edx, 11A9h; nIDDlgItem
0x180014e5a  mov     rcx, rsi; hDlg
0x180014e5d  call    BrowseForDirectory
0x180014e62  test    eax, eax
0x180014e64  jz      short loc_180014E7C
0x180014e66  mov     rax, [rdi]
0x180014e69  xor     ebx, ebx
0x180014e6b  mov     rdx, rsi
0x180014e6e  mov     rcx, rdi
0x180014e71  mov     rax, [rax+50h]
0x180014e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e7a  jmp     short loc_180014EC1
0x180014e7c  call    cs:__imp_GetLastError
0x180014e82  mov     edx, 7Ah ; 'z'
0x180014e87  mov     ebx, eax
0x180014e89  cmp     eax, edx
0x180014e8b  jnz     short loc_180014EC1
0x180014e8d  mov     rcx, [rdi]
0x180014e90  mov     rax, [rcx+30h]
0x180014e94  mov     rcx, rdi
0x180014e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e9c  mov     rdx, [rdi+8]
0x180014ea0  mov     ecx, 1234h
0x180014ea5  test    eax, eax
0x180014ea7  mov     [rsp+0C8h+var_A8], 10h
0x180014eaf  cmovz   eax, ecx
0x180014eb2  lea     r8d, [rcx-4]
0x180014eb6  mov     r9d, eax
0x180014eb9  mov     rcx, rsi
0x180014ebc  call    FaxMsgBox
0x180014ec1  mov     eax, ebx
0x180014ec3  mov     rcx, [rsp+0C8h+var_18]
0x180014ecb  xor     rcx, rsp; StackCookie
0x180014ece  call    __security_check_cookie
0x180014ed3  lea     r11, [rsp+0C8h+var_8]
0x180014edb  mov     rbx, [r11+20h]
0x180014edf  mov     rsi, [r11+28h]
0x180014ee3  mov     rsp, r11
0x180014ee6  pop     rdi
0x180014ee7  retn
```
