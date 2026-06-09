# Imbstowcs

- ea: `0x1800100e4`
- end: `0x18001012e`
- name: `Imbstowcs`
- size: `74`
- prototype: `__int64 __fastcall(LPWSTR lpWideCharStr, LPCCH lpMultiByteStr, int cchWideChar)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180010690`
- `0x180010cc0`
- `0x180014414`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x1800100fc`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x1800100fc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180010118`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180010118`

## pseudocode

```c
int __fastcall Imbstowcs(LPWSTR lpWideCharStr, LPCCH lpMultiByteStr, int cchWideChar)
{
  UINT ACP; // eax

  ACP = GetACP();
  return MultiByteToWideChar(ACP, 1u, lpMultiByteStr, -1, lpWideCharStr, cchWideChar);
}

```

## disassembly

```asm
0x1800100e4  mov     [rsp+arg_0], rbx
0x1800100e9  mov     [rsp+arg_8], rsi
0x1800100ee  push    rdi
0x1800100ef  sub     rsp, 30h
0x1800100f3  mov     edi, r8d
0x1800100f6  mov     rsi, rdx
0x1800100f9  mov     rbx, rcx
0x1800100fc  call    cs:__imp_GetACP
0x180010102  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180010106  mov     [rsp+38h+cchWideChar], edi; cchWideChar
0x18001010a  mov     ecx, eax; CodePage
0x18001010c  mov     [rsp+38h+lpWideCharStr], rbx; lpWideCharStr
0x180010111  mov     r8, rsi; lpMultiByteStr
0x180010114  lea     edx, [r9+2]; dwFlags
0x180010118  call    cs:__imp_MultiByteToWideChar
0x18001011e  mov     rbx, [rsp+38h+arg_0]
0x180010123  mov     rsi, [rsp+38h+arg_8]
0x180010128  add     rsp, 30h
0x18001012c  pop     rdi
0x18001012d  retn
```
