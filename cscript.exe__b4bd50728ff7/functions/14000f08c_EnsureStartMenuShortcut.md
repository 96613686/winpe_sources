# EnsureStartMenuShortcut

- ea: `0x14000f08c`
- end: `0x14000f125`
- name: `EnsureStartMenuShortcut`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000f464`

## callees

- `0x14000c2ec`
- `0x14000ee7c`
- `0x14000f08c`
- `0x1400161d0`

## import_xrefs

- `SHELL32!SHGetFolderPathW` at `0x14000f0cb`
- `SHELL32!SHGetFolderPathW` at `0x14000f0cb`

## pseudocode

```c
HRESULT __fastcall EnsureStartMenuShortcut(__int64 a1, __int64 a2, const unsigned __int16 *a3)
{
  HRESULT result; // eax
  unsigned __int16 v7[264]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR pszPath[264]; // [rsp+240h] [rbp-238h] BYREF

  result = SHGetFolderPathW(0, 2, 0, 0, pszPath);
  if ( result >= 0 )
  {
    result = StringCchPrintfW(v7, 0x104u, L"%s.lnk", a1);
    if ( result >= 0 )
      return CreateShortcutForExe((__int64)pszPath, (__int64)v7, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x14000f08c  push    rbx
0x14000f08e  push    rsi
0x14000f08f  push    rdi
0x14000f090  sub     rsp, 460h
0x14000f097  mov     rax, cs:__security_cookie
0x14000f09e  xor     rax, rsp
0x14000f0a1  mov     [rsp+478h+var_28], rax
0x14000f0a9  xor     r9d, r9d; dwFlags
0x14000f0ac  lea     rax, [rsp+478h+var_238]
0x14000f0b4  mov     rdi, r8
0x14000f0b7  mov     [rsp+478h+pszPath], rax; pszPath
0x14000f0bc  mov     rbx, rdx
0x14000f0bf  mov     rsi, rcx
0x14000f0c2  xor     r8d, r8d; hToken
0x14000f0c5  xor     ecx, ecx; hwnd
0x14000f0c7  lea     edx, [r9+2]; csidl
0x14000f0cb  call    cs:__imp_SHGetFolderPathW
0x14000f0d1  test    eax, eax
0x14000f0d3  js      short loc_14000F10A
0x14000f0d5  mov     r9, rsi
0x14000f0d8  lea     r8, aSLnk; "%s.lnk"
0x14000f0df  mov     edx, 104h; unsigned __int64
0x14000f0e4  lea     rcx, [rsp+478h+var_448]; unsigned __int16 *
0x14000f0e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f0ee  test    eax, eax
0x14000f0f0  js      short loc_14000F10A
0x14000f0f2  mov     r9, rdi
0x14000f0f5  lea     rdx, [rsp+478h+var_448]
0x14000f0fa  mov     r8, rbx
0x14000f0fd  lea     rcx, [rsp+478h+var_238]
0x14000f105  call    CreateShortcutForExe
0x14000f10a  mov     rcx, [rsp+478h+var_28]
0x14000f112  xor     rcx, rsp; StackCookie
0x14000f115  call    __security_check_cookie
0x14000f11a  add     rsp, 460h
0x14000f121  pop     rdi
0x14000f122  pop     rsi
0x14000f123  pop     rbx
0x14000f124  retn
```
