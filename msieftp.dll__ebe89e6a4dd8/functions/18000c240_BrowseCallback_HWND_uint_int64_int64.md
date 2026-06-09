# BrowseCallback(HWND__ *,uint,__int64,__int64)

- ea: `0x18000c240`
- end: `0x18000c33c`
- name: `?BrowseCallback@@YAHPEAUHWND__@@I_J1@Z`
- size: `252`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002240`
- `0x18000c240`
- `0x180025830`

## import_xrefs

- `SHELL32!SHGetPathFromIDListW` at `0x18000c2f1`
- `SHELL32!SHGetPathFromIDListW` at `0x18000c2f1`
- `SHLWAPI!PathIsRootW` at `0x18000c27c`
- `SHLWAPI!PathIsRootW` at `0x18000c27c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c2a7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c2c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c2a7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c2c1`
- `USER32!SendMessageW` at `0x18000c319`
- `USER32!SendMessageW` at `0x18000c319`

## pseudocode

```c
__int64 __fastcall BrowseCallback(HWND hWnd, int a2, const ITEMIDLIST *a3, LPARAM a4)
{
  unsigned int v4; // edi
  HWND v5; // rsi
  int v6; // edx
  int v7; // edx
  _BOOL8 v8; // rbx
  UINT v9; // edx
  WCHAR pszPath[264]; // [rsp+20h] [rbp-448h] BYREF
  WCHAR Buffer[264]; // [rsp+230h] [rbp-238h] BYREF

  v4 = 0;
  v5 = hWnd;
  v6 = a2 - 1;
  if ( !v6 )
  {
    if ( !a4 )
      return v4;
    v9 = 1126;
LABEL_11:
    SendMessageW(hWnd, v9, 0, a4);
    return v4;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v8 = 0;
    if ( a3 )
      v8 = SHGetPathFromIDListW(a3, pszPath);
    a4 = v8;
    v9 = 1125;
    hWnd = v5;
    goto LABEL_11;
  }
  if ( v7 == 2 && !PathIsRootW(&a3->mkid.cb) )
  {
    v4 = 1;
    LoadStringW(g_hinst, 0x102u, Buffer, 260);
    LoadStringW(g_hinst, 0x1A8u, pszPath, 260);
    _SHFusionMessageBox(v5, pszPath, Buffer, 0x10u);
  }
  return v4;
}

```

## disassembly

```asm
0x18000c240  push    rbx
0x18000c242  push    rsi
0x18000c243  push    rdi
0x18000c244  sub     rsp, 450h
0x18000c24b  mov     rax, cs:__security_cookie
0x18000c252  xor     rax, rsp
0x18000c255  mov     [rsp+468h+var_28], rax
0x18000c25d  xor     edi, edi
0x18000c25f  mov     rsi, rcx
0x18000c262  sub     edx, 1
0x18000c265  jz      loc_18000C30C
0x18000c26b  sub     edx, 1
0x18000c26e  jz      short loc_18000C2E2
0x18000c270  cmp     edx, 2
0x18000c273  jnz     loc_18000C31F
0x18000c279  mov     rcx, r8; pszPath
0x18000c27c  call    cs:__imp_PathIsRootW
0x18000c282  test    eax, eax
0x18000c284  jnz     loc_18000C31F
0x18000c28a  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000c291  lea     r8, [rsp+468h+Buffer]; lpBuffer
0x18000c299  mov     ebx, 104h
0x18000c29e  lea     edi, [rax+1]
0x18000c2a1  mov     r9d, ebx; cchBufferMax
0x18000c2a4  lea     edx, [rbx-2]; uID
0x18000c2a7  call    cs:__imp_LoadStringW
0x18000c2ad  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000c2b4  lea     r8, [rsp+468h+pszPath]; lpBuffer
0x18000c2b9  mov     r9d, ebx; cchBufferMax
0x18000c2bc  mov     edx, 1A8h; uID
0x18000c2c1  call    cs:__imp_LoadStringW
0x18000c2c7  lea     r9d, [rdi+0Fh]; unsigned int
0x18000c2cb  mov     rcx, rsi; HWND
0x18000c2ce  lea     r8, [rsp+468h+Buffer]; unsigned __int16 *
0x18000c2d6  lea     rdx, [rsp+468h+pszPath]; unsigned __int16 *
0x18000c2db  call    ?_SHFusionMessageBox@@YAHPEAUHWND__@@PEBG1I@Z; _SHFusionMessageBox(HWND__ *,ushort const *,ushort const *,uint)
0x18000c2e0  jmp     short loc_18000C31F
0x18000c2e2  xor     ebx, ebx
0x18000c2e4  test    r8, r8
0x18000c2e7  jz      short loc_18000C2FF
0x18000c2e9  lea     rdx, [rsp+468h+pszPath]; pszPath
0x18000c2ee  mov     rcx, r8; pidl
0x18000c2f1  call    cs:__imp_SHGetPathFromIDListW
0x18000c2f7  test    eax, eax
0x18000c2f9  lea     ecx, [rbx+1]
0x18000c2fc  cmovnz  ebx, ecx
0x18000c2ff  mov     r9, rbx; lParam
0x18000c302  mov     edx, 465h
0x18000c307  mov     rcx, rsi; hWnd
0x18000c30a  jmp     short loc_18000C316
0x18000c30c  test    r9, r9
0x18000c30f  jz      short loc_18000C31F
0x18000c311  mov     edx, 466h; Msg
0x18000c316  xor     r8d, r8d; wParam
0x18000c319  call    cs:__imp_SendMessageW
0x18000c31f  mov     eax, edi
0x18000c321  mov     rcx, [rsp+468h+var_28]
0x18000c329  xor     rcx, rsp; StackCookie
0x18000c32c  call    __security_check_cookie
0x18000c331  add     rsp, 450h
0x18000c338  pop     rdi
0x18000c339  pop     rsi
0x18000c33a  pop     rbx
0x18000c33b  retn
```
