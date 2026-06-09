# MCIWndCreateA

- ea: `0x180010690`
- end: `0x18001071b`
- name: `MCIWndCreateA`
- size: `139`
- prototype: `HWND __cdecl(HWND hwndParent, HINSTANCE hInstance, DWORD dwStyle, LPCSTR szFile)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800100e4`
- `0x180010690`
- `0x180010730`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010705`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010705`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800106d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800106d2`

## pseudocode

```c
HWND __cdecl MCIWndCreateA(HWND hwndParent, HINSTANCE hInstance, DWORD dwStyle, LPCSTR szFile)
{
  HWND result; // rax
  __int64 v9; // rax
  int v10; // r15d
  WCHAR *v11; // rdi
  HWND v12; // rbx

  if ( !szFile )
    return MCIWndCreateW(hwndParent, hInstance, dwStyle, 0);
  v9 = -1;
  do
    ++v9;
  while ( szFile[v9] );
  v10 = v9 + 1;
  result = (HWND)LocalAlloc(0x40u, 2LL * ((int)v9 + 1));
  v11 = (WCHAR *)result;
  if ( result )
  {
    Imbstowcs((LPWSTR)result, szFile, v10);
    v12 = MCIWndCreateW(hwndParent, hInstance, dwStyle, v11);
    LocalFree(v11);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x180010690  push    rbx; MCIWndCreate
0x180010692  push    rbp
0x180010693  push    rsi
0x180010694  push    rdi
0x180010695  push    r14
0x180010697  push    r15
0x180010699  sub     rsp, 28h
0x18001069d  mov     rbx, r9
0x1800106a0  mov     esi, r8d
0x1800106a3  mov     rbp, rdx
0x1800106a6  mov     r14, rcx
0x1800106a9  test    r9, r9
0x1800106ac  jnz     short loc_1800106B5
0x1800106ae  call    MCIWndCreateW
0x1800106b3  jmp     short loc_18001070E
0x1800106b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800106b9  inc     rax
0x1800106bc  cmp     byte ptr [r9+rax], 0
0x1800106c1  jnz     short loc_1800106B9
0x1800106c3  lea     r15d, [rax+1]
0x1800106c7  mov     ecx, 40h ; '@'; uFlags
0x1800106cc  movsxd  rdx, r15d
0x1800106cf  add     rdx, rdx; uBytes
0x1800106d2  call    cs:__imp_LocalAlloc
0x1800106d8  mov     rdi, rax
0x1800106db  test    rax, rax
0x1800106de  jz      short loc_18001070E
0x1800106e0  mov     r8d, r15d; cchWideChar
0x1800106e3  mov     rdx, rbx; lpMultiByteStr
0x1800106e6  mov     rcx, rdi; lpWideCharStr
0x1800106e9  call    Imbstowcs
0x1800106ee  mov     r9, rdi; szFile
0x1800106f1  mov     r8d, esi; dwStyle
0x1800106f4  mov     rdx, rbp; hInstance
0x1800106f7  mov     rcx, r14; hwndParent
0x1800106fa  call    MCIWndCreateW
0x1800106ff  mov     rcx, rdi; hMem
0x180010702  mov     rbx, rax
0x180010705  call    cs:__imp_LocalFree
0x18001070b  mov     rax, rbx
0x18001070e  add     rsp, 28h
0x180010712  pop     r15
0x180010714  pop     r14
0x180010716  pop     rdi
0x180010717  pop     rsi
0x180010718  pop     rbp
0x180010719  pop     rbx
0x18001071a  retn
```
