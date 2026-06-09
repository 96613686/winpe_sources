# SQLInstallDriverExW

- ea: `0x180009160`
- end: `0x1800091db`
- name: `SQLInstallDriverExW`
- size: `123`
- prototype: `BOOL __stdcall(LPCWSTR lpszDriver, LPCWSTR lpszPathIn, LPWSTR lpszPathOut, WORD cchPathOutMax, WORD *pcchPathOut, WORD fRequest, LPDWORD lpdwUsageCount)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000f3e0`

## callees

- `0x180001740`
- `0x180009050`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800091ca`
- `KERNEL32!LeaveCriticalSection` at `0x1800091ca`
- `KERNEL32!EnterCriticalSection` at `0x18000917d`
- `KERNEL32!EnterCriticalSection` at `0x18000917d`

## pseudocode

```c
BOOL __stdcall SQLInstallDriverExW(
        LPCWSTR lpszDriver,
        LPCWSTR lpszPathIn,
        LPWSTR lpszPathOut,
        WORD cchPathOutMax,
        WORD *pcchPathOut,
        WORD fRequest,
        LPDWORD lpdwUsageCount)
{
  BOOL v11; // ebx

  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  v11 = SQLInstallDriverCover(
          (wchar_t *)lpszDriver,
          (wchar_t *)lpszPathIn,
          lpszPathOut,
          cchPathOutMax,
          (__int16 *)pcchPathOut,
          fRequest,
          (int *)lpdwUsageCount);
  LeaveCriticalSection(&g_csInstaller);
  return v11;
}

```

## disassembly

```asm
0x180009160  push    rbx
0x180009162  push    rbp
0x180009163  push    rsi
0x180009164  push    rdi
0x180009165  sub     rsp, 48h
0x180009169  mov     rbp, rcx
0x18000916c  movzx   ebx, r9w
0x180009170  lea     rcx, g_csInstaller; lpCriticalSection
0x180009177  mov     rdi, r8
0x18000917a  mov     rsi, rdx
0x18000917d  call    cs:__imp_EnterCriticalSection
0x180009183  call    FreeErrorQueue
0x180009188  mov     rax, [rsp+68h+lpdwUsageCount]
0x180009190  movzx   r9d, bx
0x180009194  mov     [rsp+68h+var_38], rax; __int64
0x180009199  mov     r8, rdi
0x18000919c  movzx   eax, [rsp+68h+fRequest]
0x1800091a4  mov     rdx, rsi; wchar_t *
0x1800091a7  mov     [rsp+68h+var_40], ax; __int16
0x1800091ac  mov     rcx, rbp; String1
0x1800091af  mov     rax, [rsp+68h+pcchPathOut]
0x1800091b7  mov     [rsp+68h+var_48], rax; __int64
0x1800091bc  call    SQLInstallDriverCover
0x1800091c1  lea     rcx, g_csInstaller; lpCriticalSection
0x1800091c8  mov     ebx, eax
0x1800091ca  call    cs:__imp_LeaveCriticalSection
0x1800091d0  mov     eax, ebx
0x1800091d2  add     rsp, 48h
0x1800091d6  pop     rdi
0x1800091d7  pop     rsi
0x1800091d8  pop     rbp
0x1800091d9  pop     rbx
0x1800091da  retn
```
