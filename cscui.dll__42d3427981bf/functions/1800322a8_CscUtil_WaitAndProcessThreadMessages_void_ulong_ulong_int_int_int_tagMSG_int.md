# CscUtil_WaitAndProcessThreadMessages(void * *,ulong,ulong,int,int,int (*)(tagMSG *),int *)

- ea: `0x1800322a8`
- end: `0x180032354`
- name: `?CscUtil_WaitAndProcessThreadMessages@@YAKPEAPEAXKKHHP6AHPEAUtagMSG@@@ZPEAH@Z`
- size: `172`
- prototype: `unsigned int __fastcall(HANDLE *pHandles, unsigned int, unsigned int, int, int, int (*)(struct tagMSG *), int *)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180019a20`
- `0x180042148`
- `0x180043378`
- `0x180045d18`

## callees

- `0x1800322a8`

## import_xrefs

- `USER32!MsgWaitForMultipleObjectsEx` at `0x1800322d6`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x1800322d6`
- `USER32!TranslateMessage` at `0x18003230a`
- `USER32!TranslateMessage` at `0x18003230a`
- `USER32!PeekMessageW` at `0x180032330`
- `USER32!PeekMessageW` at `0x180032330`
- `USER32!DispatchMessageW` at `0x180032315`
- `USER32!DispatchMessageW` at `0x180032315`

## pseudocode

```c

```
