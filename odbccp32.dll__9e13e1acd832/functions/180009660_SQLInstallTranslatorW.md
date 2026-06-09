# SQLInstallTranslatorW

- ea: `0x180009660`
- end: `0x1800096e6`
- name: `SQLInstallTranslatorW`
- size: `134`
- prototype: `BOOL __stdcall(LPCWSTR lpszInfFile, LPCWSTR lpszTranslator, LPCWSTR lpszPathIn, LPWSTR lpszPathOut, WORD cchPathOutMax, WORD *pcchPathOut, WORD fRequest, LPDWORD lpdwUsageCount)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180009610`
- `0x18000f600`

## callees

- `0x180001740`
- `0x180009464`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800096d5`
- `KERNEL32!LeaveCriticalSection` at `0x1800096d5`
- `KERNEL32!EnterCriticalSection` at `0x18000967c`
- `KERNEL32!EnterCriticalSection` at `0x18000967c`

## pseudocode

```c
BOOL __stdcall SQLInstallTranslatorW(
        LPCWSTR lpszInfFile,
        LPCWSTR lpszTranslator,
        LPCWSTR lpszPathIn,
        LPWSTR lpszPathOut,
        WORD cchPathOutMax,
        WORD *pcchPathOut,
        WORD fRequest,
        LPDWORD lpdwUsageCount)
{
  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  LODWORD(lpszPathOut) = SQLInstallTranslatorCover(
                           lpszInfFile,
                           (WCHAR *)lpszTranslator,
                           (wchar_t *)lpszPathIn,
                           lpszPathOut,
                           cchPathOutMax,
                           (char *)pcchPathOut,
                           fRequest,
                           (int *)lpdwUsageCount);
  LeaveCriticalSection(&g_csInstaller);
  return (int)lpszPathOut;
}

```

## disassembly

```asm
0x180009660  push    rbx
0x180009662  push    rbp
0x180009663  push    rsi
0x180009664  push    rdi
0x180009665  sub     rsp, 48h
0x180009669  mov     rbp, rcx
0x18000966c  mov     rbx, r9
0x18000966f  lea     rcx, g_csInstaller; lpCriticalSection
0x180009676  mov     rdi, r8
0x180009679  mov     rsi, rdx
0x18000967c  call    cs:__imp_EnterCriticalSection
0x180009682  call    FreeErrorQueue
0x180009687  mov     rax, [rsp+68h+lpdwUsageCount]
0x18000968f  mov     r9, rbx
0x180009692  mov     [rsp+68h+var_30], rax
0x180009697  mov     r8, rdi
0x18000969a  movzx   eax, [rsp+68h+fRequest]
0x1800096a2  mov     rdx, rsi
0x1800096a5  mov     [rsp+68h+var_38], ax
0x1800096aa  mov     rcx, rbp
0x1800096ad  mov     rax, [rsp+68h+pcchPathOut]
0x1800096b5  mov     [rsp+68h+var_40], rax
0x1800096ba  movzx   eax, [rsp+68h+cchPathOutMax]
0x1800096c2  mov     [rsp+68h+var_48], ax
0x1800096c7  call    SQLInstallTranslatorCover
0x1800096cc  lea     rcx, g_csInstaller; lpCriticalSection
0x1800096d3  mov     ebx, eax
0x1800096d5  call    cs:__imp_LeaveCriticalSection
0x1800096db  mov     eax, ebx
0x1800096dd  add     rsp, 48h
0x1800096e1  pop     rdi
0x1800096e2  pop     rsi
0x1800096e3  pop     rbp
0x1800096e4  pop     rbx
0x1800096e5  retn
```
