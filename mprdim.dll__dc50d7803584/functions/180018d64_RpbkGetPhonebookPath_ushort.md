# RpbkGetPhonebookPath(ushort * *)

- ea: `0x180018d64`
- end: `0x180018e18`
- name: `?RpbkGetPhonebookPath@@YAKPEAPEAG@Z`
- size: `180`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800033c8`
- `0x180008510`
- `0x18000a004`
- `0x180018e20`
- `0x180018f28`
- `0x180024adc`
- `0x1800276d0`

## callees

- `0x18001851c`
- `0x180018d64`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180018d95`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180018d95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018db7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018db7`

## pseudocode

```c
__int64 __fastcall RpbkGetPhonebookPath(unsigned __int16 **a1)
{
  UINT SystemDirectoryW; // eax
  SIZE_T v3; // rdi
  wchar_t *v4; // rbx
  __int64 result; // rax
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( !SystemDirectoryW )
    return 8;
  v3 = 2 * SystemDirectoryW + 34;
  v4 = (wchar_t *)HeapAlloc(hHeap, 8u, v3);
  if ( !v4 )
    return 8;
  StringCbPrintfW(v4, (unsigned int)v3, L"%s%s", Buffer, L"\\ras\\Router.pbk");
  result = 0;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180018d64  mov     [rsp+arg_8], rbx
0x180018d69  mov     [rsp+arg_10], rsi
0x180018d6e  push    rdi
0x180018d6f  sub     rsp, 250h
0x180018d76  mov     rax, cs:__security_cookie
0x180018d7d  xor     rax, rsp
0x180018d80  mov     [rsp+258h+var_18], rax
0x180018d88  mov     rsi, rcx
0x180018d8b  mov     edx, 104h; uSize
0x180018d90  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180018d95  call    cs:__imp_GetSystemDirectoryW
0x180018d9b  test    eax, eax
0x180018d9d  jz      short loc_180018DEE
0x180018d9f  mov     rcx, cs:hHeap; hHeap
0x180018da6  lea     eax, ds:22h[rax*2]
0x180018dad  mov     r8d, eax; dwBytes
0x180018db0  mov     edx, 8; dwFlags
0x180018db5  mov     edi, eax
0x180018db7  call    cs:__imp_HeapAlloc
0x180018dbd  mov     rbx, rax
0x180018dc0  test    rax, rax
0x180018dc3  jz      short loc_180018DEE
0x180018dc5  lea     rax, aRasRouterPbk; "\\ras\\Router.pbk"
0x180018dcc  mov     edx, edi; cbDest
0x180018dce  lea     r9, [rsp+258h+Buffer]
0x180018dd3  mov     [rsp+258h+var_238], rax
0x180018dd8  lea     r8, aSS; "%s%s"
0x180018ddf  mov     rcx, rbx; pszDest
0x180018de2  call    StringCbPrintfW
0x180018de7  xor     eax, eax
0x180018de9  mov     [rsi], rbx
0x180018dec  jmp     short loc_180018DF3
0x180018dee  mov     eax, 8
0x180018df3  mov     rcx, [rsp+258h+var_18]
0x180018dfb  xor     rcx, rsp; StackCookie
0x180018dfe  call    __security_check_cookie
0x180018e03  lea     r11, [rsp+258h+var_8]
0x180018e0b  mov     rbx, [r11+18h]
0x180018e0f  mov     rsi, [r11+20h]
0x180018e13  mov     rsp, r11
0x180018e16  pop     rdi
0x180018e17  retn
```
