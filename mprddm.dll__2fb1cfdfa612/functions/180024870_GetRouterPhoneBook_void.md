# GetRouterPhoneBook(void)

- ea: `0x180024870`
- end: `0x18002496f`
- name: `?GetRouterPhoneBook@@YAKXZ`
- size: `255`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b570`

## callees

- `0x1800193a8`
- `0x180024870`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800248b7`
- `KERNEL32!SetLastError` at `0x1800248b7`
- `KERNEL32!GetWindowsDirectoryW` at `0x18002487e`
- `KERNEL32!GetWindowsDirectoryW` at `0x180024920`
- `KERNEL32!GetWindowsDirectoryW` at `0x18002487e`
- `KERNEL32!GetWindowsDirectoryW` at `0x180024920`
- `KERNEL32!HeapAlloc` at `0x180024905`
- `KERNEL32!HeapAlloc` at `0x180024905`
- `KERNEL32!GetLastError` at `0x18002488a`
- `KERNEL32!GetLastError` at `0x18002488a`

## string_xrefs

- `0x180024950`: `SYSTEM32\RAS\ROUTER.PBK`

## pseudocode

```c
DWORD GetRouterPhoneBook(void)
{
  UINT WindowsDirectoryW; // eax
  UINT v1; // ebx
  UINT v3; // ecx
  unsigned int v4; // eax
  DWORD v5; // edi
  unsigned int v6; // ecx
  unsigned int v7; // edx
  unsigned __int64 v8; // rax
  unsigned int v9; // ecx
  size_t v10; // rdi
  WCHAR *v11; // rax
  __int64 v12; // rax
  wchar_t *v13; // rbx

  WindowsDirectoryW = GetWindowsDirectoryW(0, 0);
  v1 = WindowsDirectoryW;
  if ( !WindowsDirectoryW )
    return GetLastError();
  v3 = WindowsDirectoryW + 24;
  v4 = -1;
  if ( v3 >= v1 )
    v4 = v3;
  v5 = v3 < v1 ? 0x216 : 0;
  if ( v3 < v1 )
    goto LABEL_6;
  v6 = v4 + 1;
  v7 = -1;
  if ( v4 + 1 >= v4 )
    v7 = v4 + 1;
  v5 = v6 < v4 ? 0x216 : 0;
  if ( v6 < v4 )
    goto LABEL_6;
  v8 = 2LL * v7;
  v9 = 2 * v7;
  if ( v8 > 0xFFFFFFFF )
    v9 = -1;
  v5 = v8 > 0xFFFFFFFF ? 0x216 : 0;
  if ( v8 > 0xFFFFFFFF )
  {
LABEL_6:
    SetLastError(v5);
    return v5;
  }
  else
  {
    v10 = v9;
    v11 = (WCHAR *)HeapAlloc(hHeap, 8u, v9);
    gblpRouterPhoneBook = v11;
    if ( !v11 || !GetWindowsDirectoryW(v11, v1) )
      return GetLastError();
    v12 = v1 - 1;
    v13 = (wchar_t *)gblpRouterPhoneBook;
    if ( gblpRouterPhoneBook[v12] != 92 )
      StringCbCatW((STRSAFE_LPWSTR)gblpRouterPhoneBook, (unsigned int)v10, L"\\");
    StringCbCatW(v13, v10, L"SYSTEM32\\RAS\\ROUTER.PBK");
    return 0;
  }
}

```

## disassembly

```asm
0x180024870  mov     [rsp+arg_0], rbx
0x180024875  push    rdi
0x180024876  sub     rsp, 20h
0x18002487a  xor     edx, edx; uSize
0x18002487c  xor     ecx, ecx; lpBuffer
0x18002487e  call    cs:__imp_GetWindowsDirectoryW
0x180024884  mov     ebx, eax
0x180024886  test    eax, eax
0x180024888  jnz     short loc_180024895
0x18002488a  call    cs:__imp_GetLastError
0x180024890  jmp     loc_180024964
0x180024895  lea     ecx, [rax+18h]
0x180024898  mov     r8d, 0FFFFFFFFh
0x18002489e  cmp     ecx, ebx
0x1800248a0  mov     eax, r8d
0x1800248a3  mov     r9d, 216h
0x1800248a9  cmovnb  eax, ecx
0x1800248ac  sbb     edi, edi
0x1800248ae  and     edi, r9d
0x1800248b1  cmp     ecx, ebx
0x1800248b3  jnb     short loc_1800248C4
0x1800248b5  mov     ecx, edi; dwErrCode
0x1800248b7  call    cs:__imp_SetLastError
0x1800248bd  mov     eax, edi
0x1800248bf  jmp     loc_180024964
0x1800248c4  lea     ecx, [rax+1]
0x1800248c7  mov     edx, r8d
0x1800248ca  cmp     ecx, eax
0x1800248cc  cmovnb  edx, ecx
0x1800248cf  sbb     edi, edi
0x1800248d1  and     edi, r9d
0x1800248d4  cmp     ecx, eax
0x1800248d6  jb      short loc_1800248B5
0x1800248d8  mov     eax, edx
0x1800248da  add     rax, rax
0x1800248dd  mov     ecx, eax
0x1800248df  cmp     rax, r8
0x1800248e2  jbe     short loc_1800248E7
0x1800248e4  mov     ecx, r8d
0x1800248e7  cmp     r8, rax
0x1800248ea  sbb     edi, edi
0x1800248ec  and     edi, r9d
0x1800248ef  cmp     rax, r8
0x1800248f2  ja      short loc_1800248B5
0x1800248f4  mov     edi, ecx
0x1800248f6  mov     edx, 8; dwFlags
0x1800248fb  mov     r8d, ecx; dwBytes
0x1800248fe  mov     rcx, cs:hHeap; hHeap
0x180024905  call    cs:__imp_HeapAlloc
0x18002490b  mov     cs:gblpRouterPhoneBook, rax
0x180024912  test    rax, rax
0x180024915  jz      loc_18002488A
0x18002491b  mov     edx, ebx; uSize
0x18002491d  mov     rcx, rax; lpBuffer
0x180024920  call    cs:__imp_GetWindowsDirectoryW
0x180024926  test    eax, eax
0x180024928  jz      loc_18002488A
0x18002492e  lea     eax, [rbx-1]
0x180024931  mov     rbx, cs:gblpRouterPhoneBook
0x180024938  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x18002493d  jz      short loc_180024950
0x18002493f  lea     r8, asc_180091AD8; "\\"
0x180024946  mov     edx, edi; cbDest
0x180024948  mov     rcx, rbx; pszDest
0x18002494b  call    StringCbCatW
0x180024950  lea     r8, aSystem32RasRou; "SYSTEM32\\RAS\\ROUTER.PBK"
0x180024957  mov     rdx, rdi; cbDest
0x18002495a  mov     rcx, rbx; pszDest
0x18002495d  call    StringCbCatW
0x180024962  xor     eax, eax
0x180024964  mov     rbx, [rsp+28h+arg_0]
0x180024969  add     rsp, 20h
0x18002496d  pop     rdi
0x18002496e  retn
```
