# WriteIntKey

- ea: `0x1001c3d0`
- end: `0x1001c41f`
- name: `WriteIntKey`
- size: `79`
- prototype: `int __stdcall(HANDLE hFile, LPCWCH lpWideCharStr, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1001ad40`

## callees

- `0x1001bf40`
- `0x1001c420`
- `0x1002b81a`

## pseudocode

```c
int __stdcall WriteIntKey(HANDLE hFile, LPCWCH lpWideCharStr, int a3)
{
  wchar_t pszDest[8]; // [esp+8h] [ebp-14h] BYREF

  StringCchPrintfW(pszDest, 8u, L"%d", a3);
  return WriteStringKey(hFile, lpWideCharStr, pszDest);
}

```

## disassembly

```asm
0x1001c3d0  sub     esp, 14h
0x1001c3d3  mov     eax, ___security_cookie
0x1001c3d8  xor     eax, esp
0x1001c3da  mov     [esp+14h+var_4], eax
0x1001c3de  push    esi
0x1001c3df  mov     esi, [esp+18h+lpWideCharStr]
0x1001c3e3  lea     eax, [esp+18h+pszDest]
0x1001c3e7  push    edi
0x1001c3e8  push    [esp+1Ch+arg_8]
0x1001c3ec  mov     edi, [esp+20h+hFile]
0x1001c3f0  push    offset aD; "%d"
0x1001c3f5  push    8; cchDest
0x1001c3f7  push    eax; pszDest
0x1001c3f8  call    _StringCchPrintfW
0x1001c3fd  add     esp, 10h
0x1001c400  lea     eax, [esp+1Ch+pszDest]
0x1001c404  push    eax; LPCWCH
0x1001c405  push    esi; lpWideCharStr
0x1001c406  push    edi; hFile
0x1001c407  call    WriteStringKey
0x1001c40c  mov     ecx, [esp+1Ch+var_4]
0x1001c410  pop     edi
0x1001c411  pop     esi
0x1001c412  xor     ecx, esp; StackCookie
0x1001c414  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001c419  add     esp, 14h
0x1001c41c  retn    0Ch
```
