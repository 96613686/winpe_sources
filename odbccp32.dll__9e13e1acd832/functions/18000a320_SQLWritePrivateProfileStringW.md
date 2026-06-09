# SQLWritePrivateProfileStringW

- ea: `0x18000a320`
- end: `0x18000a372`
- name: `SQLWritePrivateProfileStringW`
- size: `82`
- prototype: `BOOL __stdcall(LPCWSTR lpszSection, LPCWSTR lpszEntry, LPCWSTR lpszString, LPCWSTR lpszFilename)`
- caller_count: `10`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180006184`
- `0x180006afc`
- `0x180007200`
- `0x180007628`
- `0x1800097d0`
- `0x1800099a0`
- `0x180009e8c`
- `0x18000af80`
- `0x18000fdd0`
- `0x1800117e8`

## callees

- `0x180001740`
- `0x18000a1b4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000a361`
- `KERNEL32!LeaveCriticalSection` at `0x18000a361`
- `KERNEL32!EnterCriticalSection` at `0x18000a33c`
- `KERNEL32!EnterCriticalSection` at `0x18000a33c`

## pseudocode

```c
BOOL __stdcall SQLWritePrivateProfileStringW(
        LPCWSTR lpszSection,
        LPCWSTR lpszEntry,
        LPCWSTR lpszString,
        LPCWSTR lpszFilename)
{
  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  LODWORD(lpszFilename) = SQLWritePrivateProfileStringCover(lpszSection, lpszEntry, (BYTE *)lpszString, lpszFilename);
  LeaveCriticalSection(&g_csInstaller);
  return (int)lpszFilename;
}

```

## disassembly

```asm
0x18000a320  push    rbx
0x18000a322  push    rbp
0x18000a323  push    rsi
0x18000a324  push    rdi
0x18000a325  sub     rsp, 28h
0x18000a329  mov     rbp, rcx
0x18000a32c  mov     rbx, r9
0x18000a32f  lea     rcx, g_csInstaller; lpCriticalSection
0x18000a336  mov     rdi, r8
0x18000a339  mov     rsi, rdx
0x18000a33c  call    cs:__imp_EnterCriticalSection
0x18000a342  call    FreeErrorQueue
0x18000a347  mov     r9, rbx
0x18000a34a  mov     r8, rdi
0x18000a34d  mov     rdx, rsi
0x18000a350  mov     rcx, rbp
0x18000a353  call    SQLWritePrivateProfileStringCover
0x18000a358  lea     rcx, g_csInstaller; lpCriticalSection
0x18000a35f  mov     ebx, eax
0x18000a361  call    cs:__imp_LeaveCriticalSection
0x18000a367  mov     eax, ebx
0x18000a369  add     rsp, 28h
0x18000a36d  pop     rdi
0x18000a36e  pop     rsi
0x18000a36f  pop     rbp
0x18000a370  pop     rbx
0x18000a371  retn
```
