# SQLRemoveDriverW

- ea: `0x180009bd0`
- end: `0x180009c27`
- name: `SQLRemoveDriverW`
- size: `87`
- prototype: `BOOL __stdcall(LPCWSTR lpszDriver, BOOL fRemoveDSN, LPDWORD lpdwUsageCount)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000fb00`

## callees

- `0x180001740`
- `0x180009a88`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180009c0f`
- `KERNEL32!LeaveCriticalSection` at `0x180009c0f`
- `KERNEL32!EnterCriticalSection` at `0x180009bee`
- `KERNEL32!EnterCriticalSection` at `0x180009bee`

## pseudocode

```c
BOOL __stdcall SQLRemoveDriverW(LPCWSTR lpszDriver, BOOL fRemoveDSN, LPDWORD lpdwUsageCount)
{
  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  LODWORD(lpdwUsageCount) = SQLRemoveDriverCover((wchar_t *)lpszDriver, fRemoveDSN, (char *)lpdwUsageCount);
  LeaveCriticalSection(&g_csInstaller);
  return (int)lpdwUsageCount;
}

```

## disassembly

```asm
0x180009bd0  mov     [rsp+arg_0], rbx
0x180009bd5  mov     [rsp+arg_8], rsi
0x180009bda  push    rdi
0x180009bdb  sub     rsp, 20h
0x180009bdf  mov     rsi, rcx
0x180009be2  mov     rbx, r8
0x180009be5  lea     rcx, g_csInstaller; lpCriticalSection
0x180009bec  mov     edi, edx
0x180009bee  call    cs:__imp_EnterCriticalSection
0x180009bf4  call    FreeErrorQueue
0x180009bf9  mov     r8, rbx
0x180009bfc  mov     edx, edi
0x180009bfe  mov     rcx, rsi; String1
0x180009c01  call    SQLRemoveDriverCover
0x180009c06  lea     rcx, g_csInstaller; lpCriticalSection
0x180009c0d  mov     ebx, eax
0x180009c0f  call    cs:__imp_LeaveCriticalSection
0x180009c15  mov     rsi, [rsp+28h+arg_8]
0x180009c1a  mov     eax, ebx
0x180009c1c  mov     rbx, [rsp+28h+arg_0]
0x180009c21  add     rsp, 20h
0x180009c25  pop     rdi
0x180009c26  retn
```
