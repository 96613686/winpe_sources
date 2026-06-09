# SQLInstallTranslatorExW

- ea: `0x180009610`
- end: `0x180009650`
- name: `SQLInstallTranslatorExW`
- size: `64`
- prototype: `BOOL __stdcall(LPCWSTR lpszTranslator, LPCWSTR lpszPathIn, LPWSTR lpszPathOut, WORD cchPathOutMax, WORD *pcchPathOut, WORD fRequest, LPDWORD lpdwUsageCount)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180009660`

## pseudocode

```c
BOOL __stdcall SQLInstallTranslatorExW(
        LPCWSTR lpszTranslator,
        LPCWSTR lpszPathIn,
        LPWSTR lpszPathOut,
        WORD cchPathOutMax,
        WORD *pcchPathOut,
        WORD fRequest,
        LPDWORD lpdwUsageCount)
{
  return SQLInstallTranslatorW(
           0,
           lpszTranslator,
           lpszPathIn,
           lpszPathOut,
           cchPathOutMax,
           pcchPathOut,
           fRequest,
           lpdwUsageCount);
}

```

## disassembly

```asm
0x180009610  sub     rsp, 48h
0x180009614  mov     rax, [rsp+48h+lpdwUsageCount]
0x18000961c  mov     [rsp+48h+var_10], rax; lpdwUsageCount
0x180009621  movzx   eax, [rsp+48h+fRequest]
0x180009626  mov     [rsp+48h+var_18], ax; fRequest
0x18000962b  mov     rax, [rsp+48h+pcchPathOut]
0x180009630  mov     [rsp+48h+var_20], rax; pcchPathOut
0x180009635  mov     [rsp+48h+cchPathOutMax], r9w; cchPathOutMax
0x18000963b  mov     r9, r8; lpszPathOut
0x18000963e  mov     r8, rdx; lpszPathIn
0x180009641  mov     rdx, rcx; lpszTranslator
0x180009644  xor     ecx, ecx; lpszInfFile
0x180009646  call    SQLInstallTranslatorW
0x18000964b  add     rsp, 48h
0x18000964f  retn
```
