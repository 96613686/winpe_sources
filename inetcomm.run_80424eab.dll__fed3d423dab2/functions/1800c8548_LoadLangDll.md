# LoadLangDll

- ea: `0x1800c8548`
- end: `0x1800c85d0`
- name: `LoadLangDll`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1800212e0`

## callees

- `0x1800c8548`
- `0x1800cca00`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x1800c8586`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800c8586`
- `SHLWAPI!PathAppendW` at `0x1800c859c`
- `SHLWAPI!PathAppendW` at `0x1800c859c`
- `KERNEL32!GetModuleFileNameW` at `0x1800c8577`
- `KERNEL32!GetModuleFileNameW` at `0x1800c8577`
- `KERNEL32!LoadLibraryW` at `0x1800c85ab`
- `KERNEL32!LoadLibraryW` at `0x1800c85ab`

## string_xrefs

- `0x1800c8590`: `inetres.dll`

## pseudocode

```c
HMODULE LoadLangDll()
{
  __int64 v0; // rbx
  WCHAR Filename[264]; // [rsp+20h] [rbp-228h] BYREF

  v0 = 0;
  if ( GetModuleFileNameW(g_hInst, Filename, 0x104u)
    && PathRemoveFileSpecW(Filename)
    && PathAppendW(Filename, L"inetres.dll") )
  {
    return LoadLibraryW(Filename);
  }
  return (HMODULE)v0;
}

```

## disassembly

```asm
0x1800c8548  push    rbx
0x1800c854a  sub     rsp, 240h
0x1800c8551  mov     rax, cs:__security_cookie
0x1800c8558  xor     rax, rsp
0x1800c855b  mov     [rsp+248h+var_18], rax
0x1800c8563  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x1800c856a  lea     rdx, [rsp+248h+Filename]; lpFilename
0x1800c856f  mov     r8d, 104h; nSize
0x1800c8575  xor     ebx, ebx
0x1800c8577  call    cs:__imp_GetModuleFileNameW
0x1800c857d  test    eax, eax
0x1800c857f  jz      short loc_1800C85B4
0x1800c8581  lea     rcx, [rsp+248h+Filename]; pszPath
0x1800c8586  call    cs:__imp_PathRemoveFileSpecW
0x1800c858c  test    eax, eax
0x1800c858e  jz      short loc_1800C85B4
0x1800c8590  lea     rdx, c_szInetResDll; "inetres.dll"
0x1800c8597  lea     rcx, [rsp+248h+Filename]; pszPath
0x1800c859c  call    cs:__imp_PathAppendW
0x1800c85a2  test    eax, eax
0x1800c85a4  jz      short loc_1800C85B4
0x1800c85a6  lea     rcx, [rsp+248h+Filename]; lpLibFileName
0x1800c85ab  call    cs:__imp_LoadLibraryW
0x1800c85b1  mov     rbx, rax
0x1800c85b4  mov     rax, rbx
0x1800c85b7  mov     rcx, [rsp+248h+var_18]
0x1800c85bf  xor     rcx, rsp; StackCookie
0x1800c85c2  call    __security_check_cookie
0x1800c85c7  add     rsp, 240h
0x1800c85ce  pop     rbx
0x1800c85cf  retn
```
