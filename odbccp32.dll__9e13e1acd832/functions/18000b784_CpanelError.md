# CpanelError

- ea: `0x18000b784`
- end: `0x18000b84a`
- name: `CpanelError`
- size: `198`
- prototype: `int __fastcall(HWND hWnd, UINT, UINT, __int64, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002f80`
- `0x18000c440`
- `0x18000d0f0`
- `0x18000dc70`
- `0x18000e97c`

## callees

- `0x180002e4c`
- `0x18000b784`
- `0x180014ae0`

## import_xrefs

- `USER32!MessageBoxW` at `0x18000b829`
- `USER32!MessageBoxW` at `0x18000b829`
- `USER32!LoadStringW` at `0x18000b7bc`
- `USER32!LoadStringW` at `0x18000b7dd`
- `USER32!LoadStringW` at `0x18000b7bc`
- `USER32!LoadStringW` at `0x18000b7dd`

## pseudocode

```c
int __fastcall CpanelError(HWND hWnd, UINT a2, UINT a3, __int64 a4, int a5)
{
  WCHAR Buffer[128]; // [rsp+30h] [rbp-538h] BYREF
  WCHAR v11[128]; // [rsp+130h] [rbp-438h] BYREF
  wchar_t pszDest[392]; // [rsp+230h] [rbp-338h] BYREF

  LoadStringW(g_hResDLL, a2, Buffer, 128);
  if ( a3 )
    LoadStringW(g_hResDLL, a3, v11, 128);
  StringCchPrintfW(pszDest, 0x185u, Buffer, a4, a5);
  return MessageBoxW(hWnd, pszDest, (LPCWSTR)((unsigned __int64)v11 & -(__int64)(a3 != 0)), 0x10u);
}

```

## disassembly

```asm
0x18000b784  push    rbx
0x18000b786  push    rsi
0x18000b787  push    rdi
0x18000b788  sub     rsp, 550h
0x18000b78f  mov     rax, cs:__security_cookie
0x18000b796  xor     rax, rsp
0x18000b799  mov     [rsp+568h+var_28], rax
0x18000b7a1  mov     rsi, r9
0x18000b7a4  mov     ebx, r8d
0x18000b7a7  mov     rdi, rcx
0x18000b7aa  lea     r8, [rsp+568h+Buffer]; lpBuffer
0x18000b7af  mov     rcx, cs:g_hResDLL; hInstance
0x18000b7b6  mov     r9d, 80h; cchBufferMax
0x18000b7bc  call    cs:__imp_LoadStringW
0x18000b7c2  test    ebx, ebx
0x18000b7c4  jz      short loc_18000B7E3
0x18000b7c6  mov     rcx, cs:g_hResDLL; hInstance
0x18000b7cd  lea     r8, [rsp+568h+var_438]; lpBuffer
0x18000b7d5  mov     r9d, 80h; cchBufferMax
0x18000b7db  mov     edx, ebx; uID
0x18000b7dd  call    cs:__imp_LoadStringW
0x18000b7e3  mov     eax, [rsp+568h+arg_20]
0x18000b7ea  lea     r8, [rsp+568h+Buffer]; pszFormat
0x18000b7ef  mov     r9, rsi
0x18000b7f2  mov     [rsp+568h+var_548], eax
0x18000b7f6  mov     edx, 185h; cchDest
0x18000b7fb  lea     rcx, [rsp+568h+pszDest]; pszDest
0x18000b803  call    StringCchPrintfW
0x18000b808  neg     ebx
0x18000b80a  lea     rax, [rsp+568h+var_438]
0x18000b812  mov     r9d, 10h; uType
0x18000b818  lea     rdx, [rsp+568h+pszDest]; lpText
0x18000b820  sbb     r8, r8
0x18000b823  mov     rcx, rdi; hWnd
0x18000b826  and     r8, rax; lpCaption
0x18000b829  call    cs:__imp_MessageBoxW
0x18000b82f  mov     rcx, [rsp+568h+var_28]
0x18000b837  xor     rcx, rsp; StackCookie
0x18000b83a  call    __security_check_cookie
0x18000b83f  add     rsp, 550h
0x18000b846  pop     rdi
0x18000b847  pop     rsi
0x18000b848  pop     rbx
0x18000b849  retn
```
