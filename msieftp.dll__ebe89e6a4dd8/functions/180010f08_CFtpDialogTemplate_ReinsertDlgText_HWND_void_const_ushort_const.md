# CFtpDialogTemplate::_ReinsertDlgText(HWND__ *,void const *,ushort const *)

- ea: `0x180010f08`
- end: `0x180010fca`
- name: `?_ReinsertDlgText@CFtpDialogTemplate@@AEAAJPEAUHWND__@@PEBXPEBG@Z`
- size: `194`
- prototype: `int(CFtpDialogTemplate *__hidden this, HWND, const void *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180010390`
- `0x1800109dc`
- `0x180010ad4`
- `0x180010cd4`
- `0x180010e2c`

## callees

- `0x180002240`
- `0x1800096c4`
- `0x180010f08`

## import_xrefs

- `SHLWAPI!StrCmpW` at `0x180010f70`
- `SHLWAPI!StrCmpW` at `0x180010f70`
- `USER32!GetWindowTextW` at `0x180010f43`
- `USER32!GetWindowTextW` at `0x180010f43`
- `USER32!SetWindowTextW` at `0x180010f9d`
- `USER32!SetWindowTextW` at `0x180010f9d`

## pseudocode

```c
__int64 __fastcall CFtpDialogTemplate::_ReinsertDlgText(
        CFtpDialogTemplate *this,
        HWND a2,
        const void *a3,
        const unsigned __int16 *a4)
{
  WCHAR String[256]; // [rsp+20h] [rbp-A18h] BYREF
  WCHAR psz2[1024]; // [rsp+220h] [rbp-818h] BYREF

  GetWindowTextW(a2, String, 256);
  StringCchPrintfW(psz2, 0x400u, String, a3);
  if ( !StrCmpW(String, psz2) )
    StringCchPrintfW(psz2, 0x400u, a4, a3);
  SetWindowTextW(a2, psz2);
  return 0;
}

```

## disassembly

```asm
0x180010f08  mov     [rsp+arg_0], rbx
0x180010f0d  mov     [rsp+arg_18], rsi
0x180010f12  push    rdi
0x180010f13  sub     rsp, 0A30h
0x180010f1a  mov     rax, cs:__security_cookie
0x180010f21  xor     rax, rsp
0x180010f24  mov     [rsp+0A38h+var_18], rax
0x180010f2c  mov     rbx, rdx
0x180010f2f  mov     rdi, r8
0x180010f32  mov     rcx, rbx; hWnd
0x180010f35  lea     rdx, [rsp+0A38h+String]; lpString
0x180010f3a  mov     r8d, 100h; nMaxCount
0x180010f40  mov     rsi, r9
0x180010f43  call    cs:__imp_GetWindowTextW
0x180010f49  mov     r9, rdi
0x180010f4c  lea     r8, [rsp+0A38h+String]; unsigned __int16 *
0x180010f51  mov     edx, 400h; unsigned __int64
0x180010f56  lea     rcx, [rsp+0A38h+psz2]; unsigned __int16 *
0x180010f5e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010f63  lea     rdx, [rsp+0A38h+psz2]; psz2
0x180010f6b  lea     rcx, [rsp+0A38h+String]; psz1
0x180010f70  call    cs:__imp_StrCmpW
0x180010f76  test    eax, eax
0x180010f78  jnz     short loc_180010F92
0x180010f7a  mov     r9, rdi
0x180010f7d  lea     rcx, [rsp+0A38h+psz2]; unsigned __int16 *
0x180010f85  mov     r8, rsi; unsigned __int16 *
0x180010f88  mov     edx, 400h; unsigned __int64
0x180010f8d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010f92  lea     rdx, [rsp+0A38h+psz2]; lpString
0x180010f9a  mov     rcx, rbx; hWnd
0x180010f9d  call    cs:__imp_SetWindowTextW
0x180010fa3  xor     eax, eax
0x180010fa5  mov     rcx, [rsp+0A38h+var_18]
0x180010fad  xor     rcx, rsp; StackCookie
0x180010fb0  call    __security_check_cookie
0x180010fb5  lea     r11, [rsp+0A38h+var_8]
0x180010fbd  mov     rbx, [r11+10h]
0x180010fc1  mov     rsi, [r11+28h]
0x180010fc5  mov     rsp, r11
0x180010fc8  pop     rdi
0x180010fc9  retn
```
