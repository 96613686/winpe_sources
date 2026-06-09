# SQLRemoveTranslatorW

- ea: `0x180009cf0`
- end: `0x180009d39`
- name: `SQLRemoveTranslatorW`
- size: `73`
- prototype: `BOOL __stdcall(LPCWSTR lpszTranslator, LPDWORD lpdwUsageCount)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000fb70`

## callees

- `0x180001740`
- `0x180009c30`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180009d26`
- `KERNEL32!LeaveCriticalSection` at `0x180009d26`
- `KERNEL32!EnterCriticalSection` at `0x180009d07`
- `KERNEL32!EnterCriticalSection` at `0x180009d07`

## pseudocode

```c
BOOL __stdcall SQLRemoveTranslatorW(LPCWSTR lpszTranslator, LPDWORD lpdwUsageCount)
{
  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  LODWORD(lpdwUsageCount) = SQLRemoveTranslatorCover(lpszTranslator, lpdwUsageCount);
  LeaveCriticalSection(&g_csInstaller);
  return (int)lpdwUsageCount;
}

```

## disassembly

```asm
0x180009cf0  mov     [rsp+arg_0], rbx
0x180009cf5  push    rdi
0x180009cf6  sub     rsp, 20h
0x180009cfa  mov     rdi, rcx
0x180009cfd  mov     rbx, rdx
0x180009d00  lea     rcx, g_csInstaller; lpCriticalSection
0x180009d07  call    cs:__imp_EnterCriticalSection
0x180009d0d  call    FreeErrorQueue
0x180009d12  mov     rdx, rbx
0x180009d15  mov     rcx, rdi
0x180009d18  call    SQLRemoveTranslatorCover
0x180009d1d  lea     rcx, g_csInstaller; lpCriticalSection
0x180009d24  mov     ebx, eax
0x180009d26  call    cs:__imp_LeaveCriticalSection
0x180009d2c  mov     eax, ebx
0x180009d2e  mov     rbx, [rsp+28h+arg_0]
0x180009d33  add     rsp, 20h
0x180009d37  pop     rdi
0x180009d38  retn
```
