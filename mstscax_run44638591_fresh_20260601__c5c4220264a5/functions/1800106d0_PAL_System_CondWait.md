# PAL_System_CondWait

- ea: `0x1800106d0`
- end: `0x1800109dc`
- name: `PAL_System_CondWait`
- size: `780`
- prototype: `__int64 __usercall@<rax>(HANDLE *pHandles@<rcx>, DWORD nCount@<edx>, BOOL bWaitAll, int, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800105ac`
- `0x180010690`
- `0x180010a50`
- `0x1800db150`
- `0x1801b51b0`

## callees

- `0x1800011f4`
- `0x1800106d0`
- `0x1800829d4`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180010707`
- `KERNEL32!GetTickCount` at `0x18001081a`
- `KERNEL32!GetTickCount` at `0x180010707`
- `KERNEL32!GetTickCount` at `0x18001081a`
- `KERNEL32!GetCurrentThreadId` at `0x180010710`
- `KERNEL32!GetCurrentThreadId` at `0x180010710`
- `KERNEL32!WaitForMultipleObjects` at `0x180010761`
- `KERNEL32!WaitForMultipleObjects` at `0x180010761`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x1800107c2`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x1800107f7`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x1800107c2`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x1800107f7`
- `USER32!DispatchMessageW` at `0x1800107a3`
- `USER32!DispatchMessageW` at `0x1800107a3`
- `USER32!PeekMessageW` at `0x180010788`
- `USER32!PeekMessageW` at `0x180010788`

## string_xrefs

- `0x180010854`: `Thread: 0x%x got a WM_QUIT`
- `0x1800108b1`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x1800108f8`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18001090d`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`

## pseudocode

```c

```
