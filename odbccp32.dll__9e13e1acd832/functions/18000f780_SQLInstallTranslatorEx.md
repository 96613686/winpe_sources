# SQLInstallTranslatorEx

- ea: `0x18000f780`
- end: `0x18000f7c0`
- name: `SQLInstallTranslatorEx`
- size: `64`
- prototype: `BOOL __stdcall(LPCSTR lpszTranslator, LPCSTR lpszPathIn, LPSTR lpszPathOut, WORD cchPathOutMax, WORD *pcchPathOut, WORD fRequest, LPDWORD lpdwUsageCount)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000f600`

## pseudocode

```c
BOOL __stdcall SQLInstallTranslatorEx(
        LPCSTR lpszTranslator,
        LPCSTR lpszPathIn,
        LPSTR lpszPathOut,
        WORD cchPathOutMax,
        WORD *pcchPathOut,
        WORD fRequest,
        LPDWORD lpdwUsageCount)
{
  return SQLInstallTranslator(
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
0x18000f780  sub     rsp, 48h
0x18000f784  mov     rax, [rsp+48h+lpdwUsageCount]
0x18000f78c  mov     [rsp+48h+var_10], rax; lpdwUsageCount
0x18000f791  movzx   eax, [rsp+48h+fRequest]
0x18000f796  mov     [rsp+48h+var_18], ax; fRequest
0x18000f79b  mov     rax, [rsp+48h+pcchPathOut]
0x18000f7a0  mov     [rsp+48h+var_20], rax; pcchPathOut
0x18000f7a5  mov     [rsp+48h+cchPathOutMax], r9w; cchPathOutMax
0x18000f7ab  mov     r9, r8; lpszPathOut
0x18000f7ae  mov     r8, rdx; lpszPathIn
0x18000f7b1  mov     rdx, rcx; lpszTranslator
0x18000f7b4  xor     ecx, ecx; lpszInfFile
0x18000f7b6  call    SQLInstallTranslator
0x18000f7bb  add     rsp, 48h
0x18000f7bf  retn
```
