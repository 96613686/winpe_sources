# GetRouterPhoneBook

- ea: `0x18001165c`
- end: `0x18001173f`
- name: `GetRouterPhoneBook`
- size: `227`
- prototype: `DWORD __fastcall(CHAR **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015a80`

## callees

- `0x18001165c`
- `0x180014a14`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800116ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800116ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800116c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800116c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011686`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x18001166d`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x1800116da`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x18001166d`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryA` at `0x1800116da`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18001169e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x18001169e`

## string_xrefs

- `0x180011697`: `\system32\ras\router.pbk`
- `0x180011716`: `system32\ras\router.pbk`

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
0x18001165c  push    rbx
0x18001165e  push    rsi
0x18001165f  push    rdi
0x180011660  push    r14
0x180011662  sub     rsp, 28h
0x180011666  mov     r14, rcx
0x180011669  xor     edx, edx; uSize
0x18001166b  xor     ecx, ecx; lpBuffer
0x18001166d  call    cs:__imp_GetWindowsDirectoryA
0x180011674  nop     dword ptr [rax+rax+00h]
0x180011679  mov     qword ptr [r14], 0
0x180011680  mov     edi, eax
0x180011682  test    eax, eax
0x180011684  jnz     short loc_180011697
0x180011686  call    cs:__imp_GetLastError
0x18001168d  nop     dword ptr [rax+rax+00h]
0x180011692  jmp     loc_180011734
0x180011697  lea     rcx, String; "\\system32\\ras\\router.pbk"
0x18001169e  call    cs:__imp_lstrlenA
0x1800116a5  nop     dword ptr [rax+rax+00h]
0x1800116aa  lea     ecx, [rax+1]
0x1800116ad  cmp     ecx, eax
0x1800116af  jb      short loc_18001172F
0x1800116b1  lea     eax, [rcx+rdi]
0x1800116b4  cmp     eax, ecx
0x1800116b6  jb      short loc_18001172F
0x1800116b8  mov     edx, eax; uBytes
0x1800116ba  mov     ecx, 40h ; '@'; uFlags
0x1800116bf  mov     esi, eax
0x1800116c1  call    cs:__imp_LocalAlloc
0x1800116c8  nop     dword ptr [rax+rax+00h]
0x1800116cd  mov     rbx, rax
0x1800116d0  test    rax, rax
0x1800116d3  jz      short loc_180011686
0x1800116d5  mov     edx, edi; uSize
0x1800116d7  mov     rcx, rax; lpBuffer
0x1800116da  call    cs:__imp_GetWindowsDirectoryA
0x1800116e1  nop     dword ptr [rax+rax+00h]
0x1800116e6  test    eax, eax
0x1800116e8  jnz     short loc_1800116FB
0x1800116ea  mov     rcx, rbx; hMem
0x1800116ed  call    cs:__imp_LocalFree
0x1800116f4  nop     dword ptr [rax+rax+00h]
0x1800116f9  jmp     short loc_180011686
0x1800116fb  lea     eax, [rdi-1]
0x1800116fe  cmp     byte ptr [rax+rbx], 5Ch ; '\'
0x180011702  jz      short loc_180011716
0x180011704  lea     r8, pszSrc; "\\"
0x18001170b  mov     rdx, rsi; cbDest
0x18001170e  mov     rcx, rbx; pszDest
0x180011711  call    StringCbCatA
0x180011716  lea     r8, aSystem32RasRou_0; "system32\\ras\\router.pbk"
0x18001171d  mov     rdx, rsi; cbDest
0x180011720  mov     rcx, rbx; pszDest
0x180011723  call    StringCbCatA
0x180011728  xor     eax, eax
0x18001172a  mov     [r14], rbx
0x18001172d  jmp     short loc_180011734
0x18001172f  mov     eax, 216h
0x180011734  add     rsp, 28h
0x180011738  pop     r14
0x18001173a  pop     rdi
0x18001173b  pop     rsi
0x18001173c  pop     rbx
0x18001173d  retn
```
