# SQLRemoveDSNFromIniW

- ea: `0x180009960`
- end: `0x18000999a`
- name: `SQLRemoveDSNFromIniW`
- size: `58`
- prototype: `BOOL __stdcall(LPCWSTR lpszDSN)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000b9c0`
- `0x18000fab0`

## callees

- `0x180001740`
- `0x1800097d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000998c`
- `KERNEL32!LeaveCriticalSection` at `0x18000998c`
- `KERNEL32!EnterCriticalSection` at `0x180009970`
- `KERNEL32!EnterCriticalSection` at `0x180009970`

## pseudocode

```c
BOOL __stdcall SQLRemoveDSNFromIniW(LPCWSTR lpszDSN)
{
  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  LODWORD(lpszDSN) = SQLRemoveDSNFromIniCover(lpszDSN);
  LeaveCriticalSection(&g_csInstaller);
  return (int)lpszDSN;
}

```

## disassembly

```asm
0x180009960  push    rbx
0x180009962  sub     rsp, 20h
0x180009966  mov     rbx, rcx
0x180009969  lea     rcx, g_csInstaller; lpCriticalSection
0x180009970  call    cs:__imp_EnterCriticalSection
0x180009976  call    FreeErrorQueue
0x18000997b  mov     rcx, rbx; lpAppName
0x18000997e  call    SQLRemoveDSNFromIniCover
0x180009983  lea     rcx, g_csInstaller; lpCriticalSection
0x18000998a  mov     ebx, eax
0x18000998c  call    cs:__imp_LeaveCriticalSection
0x180009992  mov     eax, ebx
0x180009994  add     rsp, 20h
0x180009998  pop     rbx
0x180009999  retn
```
