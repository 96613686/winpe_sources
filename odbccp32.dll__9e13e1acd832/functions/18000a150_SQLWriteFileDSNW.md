# SQLWriteFileDSNW

- ea: `0x18000a150`
- end: `0x18000a1ad`
- name: `SQLWriteFileDSNW`
- size: `93`
- prototype: `BOOL __stdcall(LPCWSTR lpszFileName, LPCWSTR lpszAppName, LPCWSTR lpszKeyName, LPCWSTR lpszString)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18000fcd0`

## callees

- `0x180001740`
- `0x1800136b0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000a194`
- `KERNEL32!LeaveCriticalSection` at `0x18000a194`
- `KERNEL32!EnterCriticalSection` at `0x18000a16c`
- `KERNEL32!EnterCriticalSection` at `0x18000a16c`

## pseudocode

```c
BOOL __stdcall SQLWriteFileDSNW(LPCWSTR lpszFileName, LPCWSTR lpszAppName, LPCWSTR lpszKeyName, LPCWSTR lpszString)
{
  __int64 v8; // rcx

  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  LOWORD(lpszString) = WriteFileDSNW(v8, lpszFileName, lpszAppName, lpszKeyName, lpszString);
  LeaveCriticalSection(&g_csInstaller);
  return (_WORD)lpszString == 0;
}

```

## disassembly

```asm
0x18000a150  push    rbx
0x18000a152  push    rbp
0x18000a153  push    rsi
0x18000a154  push    rdi
0x18000a155  sub     rsp, 38h
0x18000a159  mov     rbp, rcx
0x18000a15c  mov     rbx, r9
0x18000a15f  lea     rcx, g_csInstaller; lpCriticalSection
0x18000a166  mov     rdi, r8
0x18000a169  mov     rsi, rdx
0x18000a16c  call    cs:__imp_EnterCriticalSection
0x18000a172  call    FreeErrorQueue
0x18000a177  mov     r9, rdi
0x18000a17a  mov     [rsp+58h+var_38], rbx
0x18000a17f  mov     r8, rsi
0x18000a182  mov     rdx, rbp
0x18000a185  call    WriteFileDSNW
0x18000a18a  lea     rcx, g_csInstaller; lpCriticalSection
0x18000a191  movzx   ebx, ax
0x18000a194  call    cs:__imp_LeaveCriticalSection
0x18000a19a  xor     ecx, ecx
0x18000a19c  test    bx, bx
0x18000a19f  mov     eax, ecx
0x18000a1a1  setz    al
0x18000a1a4  add     rsp, 38h
0x18000a1a8  pop     rdi
0x18000a1a9  pop     rsi
0x18000a1aa  pop     rbp
0x18000a1ab  pop     rbx
0x18000a1ac  retn
```
