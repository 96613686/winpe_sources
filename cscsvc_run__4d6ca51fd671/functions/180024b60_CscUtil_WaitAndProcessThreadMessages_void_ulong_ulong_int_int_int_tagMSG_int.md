# CscUtil_WaitAndProcessThreadMessages(void * *,ulong,ulong,int,int,int (*)(tagMSG *),int *)

- ea: `0x180024b60`
- end: `0x180024c7b`
- name: `?CscUtil_WaitAndProcessThreadMessages@@YAKPEAPEAXKKHHP6AHPEAUtagMSG@@@ZPEAH@Z`
- size: `283`
- prototype: `unsigned int __usercall@<eax>(HANDLE *pHandles@<rcx>, DWORD nCount@<edx>, DWORD dwMilliseconds@<r8d>, int@<r9d>, int, int (*)(struct tagMSG *), int *)`
- caller_count: `6`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000ed20`
- `0x180024880`
- `0x180033f68`
- `0x18003e2d4`
- `0x18003e4d4`
- `0x18003e578`

## callees

- `0x180024b60`
- `0x180089010`

## import_xrefs

- `USER32!PeekMessageW` at `0x180024bfd`
- `USER32!PeekMessageW` at `0x180024c64`
- `USER32!PeekMessageW` at `0x180024bfd`
- `USER32!PeekMessageW` at `0x180024c64`
- `USER32!DispatchMessageW` at `0x180024c49`
- `USER32!DispatchMessageW` at `0x180024c49`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180024ba2`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180024ba2`
- `USER32!TranslateMessage` at `0x180024c3e`
- `USER32!TranslateMessage` at `0x180024c3e`

## pseudocode

```c

```
