# StringCchPrintfW

- ea: `0x180002e4c`
- end: `0x180002e90`
- name: `StringCchPrintfW`
- size: `68`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x180001010`
- `0x18000295c`
- `0x180004260`
- `0x180004e80`
- `0x180005210`
- `0x1800052b8`
- `0x180005530`
- `0x180005aec`
- `0x180006afc`
- `0x180006db8`
- `0x180007c0c`
- `0x1800085c8`
- `0x180009e8c`
- `0x18000a3b0`
- `0x18000a66c`
- `0x18000af80`
- `0x18000b784`
- `0x18000b850`
- `0x18000b9c0`
- `0x18000c440`
- `0x18000cfc4`
- `0x18000d8c0`
- `0x18000e97c`
- `0x180011d48`
- `0x180011f34`
- `0x180013fa8`

## callees

- `0x180002e4c`
- `0x180002f00`
- `0x180002f60`

## pseudocode

```c
HRESULT StringCchPrintfW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  size_t v3; // rdx
  wchar_t *v4; // rcx
  size_t *v5; // r8
  int v6; // r9d
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, pszFormat);
  v6 = StringValidateDestW(pszDest, cchDest, (const size_t)pszFormat);
  if ( v6 >= 0 )
    return StringVPrintfWorkerW(v4, v3, v5, (STRSAFE_LPCWSTR)v5, va);
  if ( v3 )
    *v4 = 0;
  return v6;
}

```

## disassembly

```asm
0x180002e4c  mov     [rsp+arg_10], r8
0x180002e51  mov     qword ptr [rsp+arg_18], r9
0x180002e56  sub     rsp, 48h
0x180002e5a  call    StringValidateDestW
0x180002e5f  mov     r9d, eax
0x180002e62  xor     eax, eax
0x180002e64  test    r9d, r9d
0x180002e67  js      short loc_180002E80
0x180002e69  lea     rax, [rsp+48h+arg_18]
0x180002e6e  mov     r9, r8; pszFormat
0x180002e71  mov     [rsp+48h+argList], rax; argList
0x180002e76  call    StringVPrintfWorkerW
0x180002e7b  mov     r9d, eax
0x180002e7e  jmp     short loc_180002E88
0x180002e80  test    rdx, rdx
0x180002e83  jz      short loc_180002E88
0x180002e85  mov     [rcx], ax
0x180002e88  mov     eax, r9d
0x180002e8b  add     rsp, 48h
0x180002e8f  retn
```
