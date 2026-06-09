# IsLocalHost(ushort const *)

- ea: `0x100413da8`
- end: `0x100413e28`
- name: `?IsLocalHost@@YA_NPEBG@Z`
- size: `128`
- prototype: `bool __fastcall(LPCWCH lpString2)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10041470c`
- `0x10043ebd8`
- `0x100440ee8`
- `0x100441a7c`

## callees

- `0x100413da8`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x100413e0d`
- `KERNEL32!CompareStringOrdinal` at `0x100413e0d`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x100413dd4`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x100413deb`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x100413dd4`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp_l` at `0x100413deb`

## pseudocode

```c
bool __fastcall IsLocalHost(LPCWCH lpString2)
{
  return *lpString2 == 46 && !lpString2[1]
      || !_wcsicmp_l(L"(local)", lpString2, 0)
      || !_wcsicmp_l(L"localhost", lpString2, 0)
      || CompareStringOrdinal(&gwszComputerName, -1, lpString2, -1, 1) == 2;
}

```

## disassembly

```asm
0x100413da8  mov     [rsp+arg_0], rbx
0x100413dad  push    rdi
0x100413dae  sub     rsp, 30h
0x100413db2  mov     eax, 2Eh ; '.'
0x100413db7  xor     edi, edi
0x100413db9  mov     rbx, rcx
0x100413dbc  cmp     ax, [rcx]
0x100413dbf  jnz     short loc_100413DC7
0x100413dc1  cmp     di, [rcx+2]
0x100413dc5  jz      short loc_100413E1B
0x100413dc7  xor     r8d, r8d; Locale
0x100413dca  lea     rcx, aLocal; "(local)"
0x100413dd1  mov     rdx, rbx; String2
0x100413dd4  call    cs:__imp__wcsicmp_l
0x100413dda  test    eax, eax
0x100413ddc  jz      short loc_100413E1B
0x100413dde  xor     r8d, r8d; Locale
0x100413de1  lea     rcx, aLocalhost; "localhost"
0x100413de8  mov     rdx, rbx; String2
0x100413deb  call    cs:__imp__wcsicmp_l
0x100413df1  test    eax, eax
0x100413df3  jz      short loc_100413E1B
0x100413df5  or      edx, 0FFFFFFFFh; cchCount1
0x100413df8  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x100413e00  mov     r9d, edx; cchCount2
0x100413e03  lea     rcx, ?gwszComputerName@@3PAGA; lpString1
0x100413e0a  mov     r8, rbx; lpString2
0x100413e0d  call    cs:__imp_CompareStringOrdinal
0x100413e13  cmp     eax, 2
0x100413e16  setz    al
0x100413e19  jmp     short loc_100413E1D
0x100413e1b  mov     al, 1
0x100413e1d  mov     rbx, [rsp+38h+arg_0]
0x100413e22  add     rsp, 30h
0x100413e26  pop     rdi
0x100413e27  retn
```
