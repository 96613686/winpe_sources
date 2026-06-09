# SQLConfigDataSourceW

- ea: `0x180008570`
- end: `0x1800085c2`
- name: `SQLConfigDataSourceW`
- size: `82`
- prototype: `BOOL __stdcall(HWND hwndParent, WORD fRequest, LPCWSTR lpszDriver, LPCWSTR lpszAttributes)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18000b5f0`
- `0x18000cfc4`
- `0x18000ec20`

## callees

- `0x180001740`
- `0x1800084c0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800085b1`
- `KERNEL32!LeaveCriticalSection` at `0x1800085b1`
- `KERNEL32!EnterCriticalSection` at `0x18000858c`
- `KERNEL32!EnterCriticalSection` at `0x18000858c`

## pseudocode

```c
BOOL __stdcall SQLConfigDataSourceW(HWND hwndParent, WORD fRequest, LPCWSTR lpszDriver, LPCWSTR lpszAttributes)
{
  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  LODWORD(lpszAttributes) = SQLConfigDataSourceCover(hwndParent, fRequest, lpszDriver, (__int64)lpszAttributes);
  LeaveCriticalSection(&g_csInstaller);
  return (int)lpszAttributes;
}

```

## disassembly

```asm
0x180008570  push    rbx
0x180008572  push    rbp
0x180008573  push    rsi
0x180008574  push    rdi
0x180008575  sub     rsp, 28h
0x180008579  mov     rbp, rcx
0x18000857c  mov     rbx, r9
0x18000857f  lea     rcx, g_csInstaller; lpCriticalSection
0x180008586  mov     rdi, r8
0x180008589  movzx   esi, dx
0x18000858c  call    cs:__imp_EnterCriticalSection
0x180008592  call    FreeErrorQueue
0x180008597  mov     r9, rbx
0x18000859a  mov     r8, rdi
0x18000859d  movzx   edx, si
0x1800085a0  mov     rcx, rbp
0x1800085a3  call    SQLConfigDataSourceCover
0x1800085a8  lea     rcx, g_csInstaller; lpCriticalSection
0x1800085af  mov     ebx, eax
0x1800085b1  call    cs:__imp_LeaveCriticalSection
0x1800085b7  mov     eax, ebx
0x1800085b9  add     rsp, 28h
0x1800085bd  pop     rdi
0x1800085be  pop     rsi
0x1800085bf  pop     rbp
0x1800085c0  pop     rbx
0x1800085c1  retn
```
