# SQLGetTranslatorW

- ea: `0x180008fc0`
- end: `0x180009048`
- name: `SQLGetTranslatorW`
- size: `136`
- prototype: `BOOL __stdcall(HWND hwnd, LPWSTR lpszName, WORD cchNameMax, WORD *pcchNameOut, LPWSTR lpszPath, WORD cchPathMax, WORD *pcchPathOut, DWORD *pvOption)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000f100`

## callees

- `0x180001740`
- `0x180008e78`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180009037`
- `KERNEL32!LeaveCriticalSection` at `0x180009037`
- `KERNEL32!EnterCriticalSection` at `0x180008fdd`
- `KERNEL32!EnterCriticalSection` at `0x180008fdd`

## pseudocode

```c
BOOL __stdcall SQLGetTranslatorW(
        HWND hwnd,
        LPWSTR lpszName,
        WORD cchNameMax,
        WORD *pcchNameOut,
        LPWSTR lpszPath,
        WORD cchPathMax,
        WORD *pcchPathOut,
        DWORD *pvOption)
{
  int v9; // ebx

  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  v9 = SQLGetTranslatorCover(hwnd, (__int64)lpszPath, cchPathMax, (__int64)pcchPathOut, (__int64)pvOption);
  LeaveCriticalSection(&g_csInstaller);
  return v9;
}

```

## disassembly

```asm
0x180008fc0  push    rbx
0x180008fc2  push    rbp
0x180008fc3  push    rsi
0x180008fc4  push    rdi
0x180008fc5  sub     rsp, 48h
0x180008fc9  mov     rbp, rcx
0x180008fcc  mov     rbx, r9
0x180008fcf  lea     rcx, g_csInstaller; lpCriticalSection
0x180008fd6  movzx   edi, r8w
0x180008fda  mov     rsi, rdx
0x180008fdd  call    cs:__imp_EnterCriticalSection
0x180008fe3  call    FreeErrorQueue
0x180008fe8  mov     rax, [rsp+68h+pvOption]
0x180008ff0  mov     r9, rbx
0x180008ff3  mov     [rsp+68h+var_30], rax; __int64
0x180008ff8  movzx   r8d, di
0x180008ffc  mov     rax, [rsp+68h+pcchPathOut]
0x180009004  mov     rdx, rsi
0x180009007  mov     [rsp+68h+var_38], rax; __int64
0x18000900c  mov     rcx, rbp; hWndParent
0x18000900f  movzx   eax, [rsp+68h+cchPathMax]
0x180009017  mov     [rsp+68h+var_40], ax; __int16
0x18000901c  mov     rax, [rsp+68h+lpszPath]
0x180009024  mov     [rsp+68h+var_48], rax; __int64
0x180009029  call    SQLGetTranslatorCover
0x18000902e  lea     rcx, g_csInstaller; lpCriticalSection
0x180009035  mov     ebx, eax
0x180009037  call    cs:__imp_LeaveCriticalSection
0x18000903d  mov     eax, ebx
0x18000903f  add     rsp, 48h
0x180009043  pop     rdi
0x180009044  pop     rsi
0x180009045  pop     rbp
0x180009046  pop     rbx
0x180009047  retn
```
