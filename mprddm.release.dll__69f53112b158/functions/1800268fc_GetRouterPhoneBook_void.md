# GetRouterPhoneBook(void)

- ea: `0x1800268fc`
- end: `0x180026a19`
- name: `?GetRouterPhoneBook@@YAKXZ`
- size: `285`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001bf40`

## callees

- `0x180019c88`
- `0x1800268fc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002694f`
- `KERNEL32!SetLastError` at `0x18002694f`
- `KERNEL32!GetWindowsDirectoryW` at `0x18002690a`
- `KERNEL32!GetWindowsDirectoryW` at `0x1800269c3`
- `KERNEL32!GetWindowsDirectoryW` at `0x18002690a`
- `KERNEL32!GetWindowsDirectoryW` at `0x1800269c3`
- `KERNEL32!HeapAlloc` at `0x1800269a2`
- `KERNEL32!HeapAlloc` at `0x1800269a2`
- `KERNEL32!GetLastError` at `0x18002691c`
- `KERNEL32!GetLastError` at `0x18002691c`

## string_xrefs

- `0x1800269f9`: `SYSTEM32\RAS\ROUTER.PBK`

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
  unsigned int v8; // eax
  unsigned __int64 v9; // rcx
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
  v8 = -1;
  v9 = 2LL * v7;
  if ( v9 <= 0xFFFFFFFF )
    v8 = 2 * v7;
  v5 = v9 > 0xFFFFFFFF ? 0x216 : 0;
  if ( v9 > 0xFFFFFFFF )
  {
LABEL_6:
    SetLastError(v5);
    return v5;
  }
  else
  {
    v10 = v8;
    v11 = (WCHAR *)HeapAlloc(hHeap, 8u, v8);
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
0x1800268fc  mov     [rsp+arg_0], rbx
0x180026901  push    rdi
0x180026902  sub     rsp, 20h
0x180026906  xor     edx, edx; uSize
0x180026908  xor     ecx, ecx; lpBuffer
0x18002690a  call    cs:__imp_GetWindowsDirectoryW
0x180026911  nop     dword ptr [rax+rax+00h]
0x180026916  mov     ebx, eax
0x180026918  test    eax, eax
0x18002691a  jnz     short loc_18002692D
0x18002691c  call    cs:__imp_GetLastError
0x180026923  nop     dword ptr [rax+rax+00h]
0x180026928  jmp     loc_180026A0D
0x18002692d  lea     ecx, [rax+18h]
0x180026930  mov     r8d, 0FFFFFFFFh
0x180026936  cmp     ecx, ebx
0x180026938  mov     eax, r8d
0x18002693b  mov     r9d, 216h
0x180026941  cmovnb  eax, ecx
0x180026944  sbb     edi, edi
0x180026946  and     edi, r9d
0x180026949  cmp     ecx, ebx
0x18002694b  jnb     short loc_180026962
0x18002694d  mov     ecx, edi; dwErrCode
0x18002694f  call    cs:__imp_SetLastError
0x180026956  nop     dword ptr [rax+rax+00h]
0x18002695b  mov     eax, edi
0x18002695d  jmp     loc_180026A0D
0x180026962  lea     ecx, [rax+1]
0x180026965  mov     edx, r8d
0x180026968  cmp     ecx, eax
0x18002696a  cmovnb  edx, ecx
0x18002696d  sbb     edi, edi
0x18002696f  and     edi, r9d
0x180026972  cmp     ecx, eax
0x180026974  jb      short loc_18002694D
0x180026976  mov     ecx, edx
0x180026978  mov     eax, r8d
0x18002697b  add     rcx, rcx
0x18002697e  cmp     rcx, r8
0x180026981  cmovbe  eax, ecx
0x180026984  cmp     r8, rcx
0x180026987  sbb     edi, edi
0x180026989  and     edi, r9d
0x18002698c  cmp     rcx, r8
0x18002698f  ja      short loc_18002694D
0x180026991  mov     rcx, cs:hHeap; hHeap
0x180026998  mov     edx, 8; dwFlags
0x18002699d  mov     r8d, eax; dwBytes
0x1800269a0  mov     edi, eax
0x1800269a2  call    cs:__imp_HeapAlloc
0x1800269a9  nop     dword ptr [rax+rax+00h]
0x1800269ae  mov     cs:gblpRouterPhoneBook, rax
0x1800269b5  test    rax, rax
0x1800269b8  jz      loc_18002691C
0x1800269be  mov     edx, ebx; uSize
0x1800269c0  mov     rcx, rax; lpBuffer
0x1800269c3  call    cs:__imp_GetWindowsDirectoryW
0x1800269ca  nop     dword ptr [rax+rax+00h]
0x1800269cf  test    eax, eax
0x1800269d1  jz      loc_18002691C
0x1800269d7  lea     eax, [rbx-1]
0x1800269da  mov     rbx, cs:gblpRouterPhoneBook
0x1800269e1  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x1800269e6  jz      short loc_1800269F9
0x1800269e8  lea     r8, asc_180098AD8; "\\"
0x1800269ef  mov     edx, edi; cbDest
0x1800269f1  mov     rcx, rbx; pszDest
0x1800269f4  call    StringCbCatW
0x1800269f9  lea     r8, aSystem32RasRou; "SYSTEM32\\RAS\\ROUTER.PBK"
0x180026a00  mov     rdx, rdi; cbDest
0x180026a03  mov     rcx, rbx; pszDest
0x180026a06  call    StringCbCatW
0x180026a0b  xor     eax, eax
0x180026a0d  mov     rbx, [rsp+28h+arg_0]
0x180026a12  add     rsp, 20h
0x180026a16  pop     rdi
0x180026a17  retn
```
