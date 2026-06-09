# SQLReadFileDSNW

- ea: `0x180009750`
- end: `0x1800097c7`
- name: `SQLReadFileDSNW`
- size: `119`
- prototype: `BOOL __stdcall(LPCWSTR lpszFileName, LPCWSTR lpszAppName, LPCWSTR lpszKeyName, LPWSTR lpszString, WORD cchString, WORD *pcchString)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18000f930`

## callees

- `0x180001740`
- `0x180012e90`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800097ae`
- `KERNEL32!LeaveCriticalSection` at `0x1800097ae`
- `KERNEL32!EnterCriticalSection` at `0x18000976c`
- `KERNEL32!EnterCriticalSection` at `0x18000976c`

## pseudocode

```c
BOOL __stdcall SQLReadFileDSNW(
        LPCWSTR lpszFileName,
        LPCWSTR lpszAppName,
        LPCWSTR lpszKeyName,
        LPWSTR lpszString,
        WORD cchString,
        WORD *pcchString)
{
  __int64 v10; // rcx

  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  LOWORD(lpszString) = ReadFileDSNW(v10, lpszFileName, lpszAppName, lpszKeyName, lpszString, cchString, pcchString);
  LeaveCriticalSection(&g_csInstaller);
  return (_WORD)lpszString == 0;
}

```

## disassembly

```asm
0x180009750  push    rbx
0x180009752  push    rbp
0x180009753  push    rsi
0x180009754  push    rdi
0x180009755  sub     rsp, 48h
0x180009759  mov     rbp, rcx
0x18000975c  mov     rbx, r9
0x18000975f  lea     rcx, g_csInstaller; lpCriticalSection
0x180009766  mov     rdi, r8
0x180009769  mov     rsi, rdx
0x18000976c  call    cs:__imp_EnterCriticalSection
0x180009772  call    FreeErrorQueue
0x180009777  mov     rax, [rsp+68h+pcchString]
0x18000977f  mov     r9, rdi
0x180009782  mov     [rsp+68h+var_38], rax
0x180009787  mov     r8, rsi
0x18000978a  movzx   eax, [rsp+68h+cchString]
0x180009792  mov     rdx, rbp
0x180009795  mov     [rsp+68h+var_40], ax
0x18000979a  mov     [rsp+68h+var_48], rbx
0x18000979f  call    ReadFileDSNW
0x1800097a4  lea     rcx, g_csInstaller; lpCriticalSection
0x1800097ab  movzx   ebx, ax
0x1800097ae  call    cs:__imp_LeaveCriticalSection
0x1800097b4  xor     ecx, ecx
0x1800097b6  test    bx, bx
0x1800097b9  mov     eax, ecx
0x1800097bb  setz    al
0x1800097be  add     rsp, 48h
0x1800097c2  pop     rdi
0x1800097c3  pop     rsi
0x1800097c4  pop     rbp
0x1800097c5  pop     rbx
0x1800097c6  retn
```
