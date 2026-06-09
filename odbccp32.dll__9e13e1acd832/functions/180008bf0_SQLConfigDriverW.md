# SQLConfigDriverW

- ea: `0x180008bf0`
- end: `0x180008c69`
- name: `SQLConfigDriverW`
- size: `121`
- prototype: `BOOL __stdcall(HWND hwndParent, WORD fRequest, LPCWSTR lpszDriver, LPCWSTR lpszArgs, LPWSTR lpszMsg, WORD cchMsgMax, WORD *pcchMsgOut)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18000ecc0`

## callees

- `0x180001740`
- `0x1800085c8`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180008c58`
- `KERNEL32!LeaveCriticalSection` at `0x180008c58`
- `KERNEL32!EnterCriticalSection` at `0x180008c0c`
- `KERNEL32!EnterCriticalSection` at `0x180008c0c`

## pseudocode

```c
BOOL __stdcall SQLConfigDriverW(
        HWND hwndParent,
        WORD fRequest,
        LPCWSTR lpszDriver,
        LPCWSTR lpszArgs,
        LPWSTR lpszMsg,
        WORD cchMsgMax,
        WORD *pcchMsgOut)
{
  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  LODWORD(lpszArgs) = SQLConfigDriverCover(
                        hwndParent,
                        fRequest,
                        lpszDriver,
                        lpszArgs,
                        lpszMsg,
                        cchMsgMax,
                        (__int16 *)pcchMsgOut);
  LeaveCriticalSection(&g_csInstaller);
  return (int)lpszArgs;
}

```

## disassembly

```asm
0x180008bf0  push    rbx
0x180008bf2  push    rbp
0x180008bf3  push    rsi
0x180008bf4  push    rdi
0x180008bf5  sub     rsp, 48h
0x180008bf9  mov     rbp, rcx
0x180008bfc  mov     rbx, r9
0x180008bff  lea     rcx, g_csInstaller; lpCriticalSection
0x180008c06  mov     rdi, r8
0x180008c09  movzx   esi, dx
0x180008c0c  call    cs:__imp_EnterCriticalSection
0x180008c12  call    FreeErrorQueue
0x180008c17  mov     rax, [rsp+68h+pcchMsgOut]
0x180008c1f  mov     r9, rbx
0x180008c22  mov     [rsp+68h+var_38], rax; __int64
0x180008c27  mov     r8, rdi
0x180008c2a  movzx   eax, [rsp+68h+cchMsgMax]
0x180008c32  movzx   edx, si
0x180008c35  mov     [rsp+68h+var_40], ax; __int16
0x180008c3a  mov     rcx, rbp; hWnd
0x180008c3d  mov     rax, [rsp+68h+lpszMsg]
0x180008c45  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x180008c4a  call    SQLConfigDriverCover
0x180008c4f  lea     rcx, g_csInstaller; lpCriticalSection
0x180008c56  mov     ebx, eax
0x180008c58  call    cs:__imp_LeaveCriticalSection
0x180008c5e  mov     eax, ebx
0x180008c60  add     rsp, 48h
0x180008c64  pop     rdi
0x180008c65  pop     rsi
0x180008c66  pop     rbp
0x180008c67  pop     rbx
0x180008c68  retn
```
