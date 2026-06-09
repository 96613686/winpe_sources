# SQLWriteDSNToIniW

- ea: `0x18000a100`
- end: `0x18000a149`
- name: `SQLWriteDSNToIniW`
- size: `73`
- prototype: `BOOL __stdcall(LPCWSTR lpszDSN, LPCWSTR lpszDriver)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000fc40`

## callees

- `0x180001740`
- `0x180009e8c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000a136`
- `KERNEL32!LeaveCriticalSection` at `0x18000a136`
- `KERNEL32!EnterCriticalSection` at `0x18000a117`
- `KERNEL32!EnterCriticalSection` at `0x18000a117`

## pseudocode

```c
BOOL __stdcall SQLWriteDSNToIniW(LPCWSTR lpszDSN, LPCWSTR lpszDriver)
{
  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  LODWORD(lpszDriver) = SQLWriteDSNToIniCover((wchar_t *)lpszDSN, lpszDriver);
  LeaveCriticalSection(&g_csInstaller);
  return (int)lpszDriver;
}

```

## disassembly

```asm
0x18000a100  mov     [rsp+arg_0], rbx
0x18000a105  push    rdi
0x18000a106  sub     rsp, 20h
0x18000a10a  mov     rdi, rcx
0x18000a10d  mov     rbx, rdx
0x18000a110  lea     rcx, g_csInstaller; lpCriticalSection
0x18000a117  call    cs:__imp_EnterCriticalSection
0x18000a11d  call    FreeErrorQueue
0x18000a122  mov     rdx, rbx; lpszString
0x18000a125  mov     rcx, rdi; lpAppName
0x18000a128  call    SQLWriteDSNToIniCover
0x18000a12d  lea     rcx, g_csInstaller; lpCriticalSection
0x18000a134  mov     ebx, eax
0x18000a136  call    cs:__imp_LeaveCriticalSection
0x18000a13c  mov     eax, ebx
0x18000a13e  mov     rbx, [rsp+28h+arg_0]
0x18000a143  add     rsp, 20h
0x18000a147  pop     rdi
0x18000a148  retn
```
