# SQLInstallerErrorW

- ea: `0x180004d40`
- end: `0x180004d9e`
- name: `SQLInstallerErrorW`
- size: `94`
- prototype: `SQLRETURN __stdcall(WORD iError, DWORD *pfErrorCode, LPWSTR lpszErrorMsg, WORD cchErrorMsgMax, WORD *pcchErrorMsg)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800097d0`
- `0x18000b850`
- `0x18000f7d0`

## callees

- `0x180004c14`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180004d8c`
- `KERNEL32!LeaveCriticalSection` at `0x180004d8c`
- `KERNEL32!EnterCriticalSection` at `0x180004d5d`
- `KERNEL32!EnterCriticalSection` at `0x180004d5d`

## pseudocode

```c
SQLRETURN __stdcall SQLInstallerErrorW(
        WORD iError,
        DWORD *pfErrorCode,
        LPWSTR lpszErrorMsg,
        WORD cchErrorMsgMax,
        WORD *pcchErrorMsg)
{
  SQLRETURN v9; // bx

  EnterCriticalSection(&g_csInstaller);
  v9 = SQLInstErrorCover(iError, pfErrorCode, lpszErrorMsg, cchErrorMsgMax, pcchErrorMsg);
  LeaveCriticalSection(&g_csInstaller);
  return v9;
}

```

## disassembly

```asm
0x180004d40  push    rbx
0x180004d42  push    rbp
0x180004d43  push    rsi
0x180004d44  push    rdi
0x180004d45  sub     rsp, 38h
0x180004d49  movzx   ebp, cx
0x180004d4c  movzx   ebx, r9w
0x180004d50  lea     rcx, g_csInstaller; lpCriticalSection
0x180004d57  mov     rdi, r8
0x180004d5a  mov     rsi, rdx
0x180004d5d  call    cs:__imp_EnterCriticalSection
0x180004d63  mov     rax, [rsp+58h+pcchErrorMsg]
0x180004d6b  movzx   r9d, bx
0x180004d6f  mov     r8, rdi
0x180004d72  mov     [rsp+58h+var_38], rax
0x180004d77  mov     rdx, rsi
0x180004d7a  movzx   ecx, bp
0x180004d7d  call    SQLInstErrorCover
0x180004d82  lea     rcx, g_csInstaller; lpCriticalSection
0x180004d89  movzx   ebx, ax
0x180004d8c  call    cs:__imp_LeaveCriticalSection
0x180004d92  movzx   eax, bx
0x180004d95  add     rsp, 38h
0x180004d99  pop     rdi
0x180004d9a  pop     rsi
0x180004d9b  pop     rbp
0x180004d9c  pop     rbx
0x180004d9d  retn
```
