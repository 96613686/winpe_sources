# GetRouterPhoneBook

- ea: `0x1800110e8`
- end: `0x1800111a6`
- name: `GetRouterPhoneBook`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015320`

## callees

- `0x1800110e8`
- `0x180014330`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001115b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001115b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001113b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001113b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001110c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001110c`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x1800110f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x18001114e`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x1800110f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x18001114e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18001111e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18001111e`

## string_xrefs

- `0x180011117`: `\system32\ras\router.pbk`
- `0x18001117e`: `system32\ras\router.pbk`

## pseudocode

```c
DWORD __fastcall GetRouterPhoneBook(CHAR **a1)
{
  UINT WindowsDirectoryA; // eax
  UINT v3; // edi
  DWORD result; // eax
  unsigned int v5; // eax
  unsigned int v6; // ecx
  unsigned int v7; // eax
  size_t v8; // rsi
  CHAR *v9; // rax
  CHAR *v10; // rbx

  WindowsDirectoryA = GetWindowsDirectoryA(0, 0);
  *a1 = 0;
  v3 = WindowsDirectoryA;
  if ( !WindowsDirectoryA )
    return GetLastError();
  v5 = lstrlenA("\\system32\\ras\\router.pbk");
  v6 = v5 + 1;
  if ( v5 + 1 < v5 )
    return 534;
  v7 = v6 + v3;
  if ( v6 + v3 < v6 )
    return 534;
  v8 = v7;
  v9 = (CHAR *)LocalAlloc(0x40u, v7);
  v10 = v9;
  if ( !v9 )
    return GetLastError();
  if ( !GetWindowsDirectoryA(v9, v3) )
  {
    LocalFree(v10);
    return GetLastError();
  }
  if ( v10[v3 - 1] != 92 )
    StringCbCatA(v10, v8, "\\");
  StringCbCatA(v10, v8, "system32\\ras\\router.pbk");
  result = 0;
  *a1 = v10;
  return result;
}

```

## disassembly

```asm
0x1800110e8  push    rbx
0x1800110ea  push    rsi
0x1800110eb  push    rdi
0x1800110ec  push    r14
0x1800110ee  sub     rsp, 28h
0x1800110f2  mov     r14, rcx
0x1800110f5  xor     edx, edx; uSize
0x1800110f7  xor     ecx, ecx; lpBuffer
0x1800110f9  call    cs:__imp_GetWindowsDirectoryA
0x1800110ff  mov     qword ptr [r14], 0
0x180011106  mov     edi, eax
0x180011108  test    eax, eax
0x18001110a  jnz     short loc_180011117
0x18001110c  call    cs:__imp_GetLastError
0x180011112  jmp     loc_18001119C
0x180011117  lea     rcx, String; "\\system32\\ras\\router.pbk"
0x18001111e  call    cs:__imp_lstrlenA
0x180011124  lea     ecx, [rax+1]
0x180011127  cmp     ecx, eax
0x180011129  jb      short loc_180011197
0x18001112b  lea     eax, [rcx+rdi]
0x18001112e  cmp     eax, ecx
0x180011130  jb      short loc_180011197
0x180011132  mov     edx, eax; uBytes
0x180011134  mov     ecx, 40h ; '@'; uFlags
0x180011139  mov     esi, eax
0x18001113b  call    cs:__imp_LocalAlloc
0x180011141  mov     rbx, rax
0x180011144  test    rax, rax
0x180011147  jz      short loc_18001110C
0x180011149  mov     edx, edi; uSize
0x18001114b  mov     rcx, rax; lpBuffer
0x18001114e  call    cs:__imp_GetWindowsDirectoryA
0x180011154  test    eax, eax
0x180011156  jnz     short loc_180011163
0x180011158  mov     rcx, rbx; hMem
0x18001115b  call    cs:__imp_LocalFree
0x180011161  jmp     short loc_18001110C
0x180011163  lea     eax, [rdi-1]
0x180011166  cmp     byte ptr [rax+rbx], 5Ch ; '\'
0x18001116a  jz      short loc_18001117E
0x18001116c  lea     r8, pszSrc; "\\"
0x180011173  mov     rdx, rsi; cbDest
0x180011176  mov     rcx, rbx; pszDest
0x180011179  call    StringCbCatA
0x18001117e  lea     r8, aSystem32RasRou_0; "system32\\ras\\router.pbk"
0x180011185  mov     rdx, rsi; cbDest
0x180011188  mov     rcx, rbx; pszDest
0x18001118b  call    StringCbCatA
0x180011190  xor     eax, eax
0x180011192  mov     [r14], rbx
0x180011195  jmp     short loc_18001119C
0x180011197  mov     eax, 216h
0x18001119c  add     rsp, 28h
0x1800111a0  pop     r14
0x1800111a2  pop     rdi
0x1800111a3  pop     rsi
0x1800111a4  pop     rbx
0x1800111a5  retn
```
