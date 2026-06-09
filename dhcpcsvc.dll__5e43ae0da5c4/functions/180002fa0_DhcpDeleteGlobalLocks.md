# DhcpDeleteGlobalLocks

- ea: `0x180002fa0`
- end: `0x180003004`
- name: `DhcpDeleteGlobalLocks`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002f40`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180002fab`
- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180002fb8`
- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180002fc5`
- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180002fd2`
- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180002fdf`
- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180002fec`
- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180002fab`
- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180002fb8`
- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180002fc5`
- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180002fd2`
- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180002fdf`
- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180002fec`
- `api-ms-win-downlevel-kernel32-l1-1-0!DeleteCriticalSection` at `0x180002ffd`

## pseudocode

```c
void DhcpDeleteGlobalLocks()
{
  DeleteCriticalSection(&DhcpGlobalListCritSect);
  DeleteCriticalSection(&DhcpGlobalRecvFromCritSect);
  DeleteCriticalSection(&DhcpGlobalZeroAddressCritSect);
  DeleteCriticalSection(&DhcpGlobalApiCritSect);
  DeleteCriticalSection(&DhcpGlobalNicListCritSect);
  DeleteCriticalSection(&DhcpHandleErrorQCritSect);
  DeleteCriticalSection((LPCRITICAL_SECTION)DhcpGlobalNotificationListCritSect);
}

```

## disassembly

```asm
0x180002fa0  sub     rsp, 28h
0x180002fa4  lea     rcx, DhcpGlobalListCritSect; lpCriticalSection
0x180002fab  call    cs:__imp_DeleteCriticalSection
0x180002fb1  lea     rcx, DhcpGlobalRecvFromCritSect; lpCriticalSection
0x180002fb8  call    cs:__imp_DeleteCriticalSection
0x180002fbe  lea     rcx, DhcpGlobalZeroAddressCritSect; lpCriticalSection
0x180002fc5  call    cs:__imp_DeleteCriticalSection
0x180002fcb  lea     rcx, DhcpGlobalApiCritSect; lpCriticalSection
0x180002fd2  call    cs:__imp_DeleteCriticalSection
0x180002fd8  lea     rcx, DhcpGlobalNicListCritSect; lpCriticalSection
0x180002fdf  call    cs:__imp_DeleteCriticalSection
0x180002fe5  lea     rcx, DhcpHandleErrorQCritSect; lpCriticalSection
0x180002fec  call    cs:__imp_DeleteCriticalSection
0x180002ff2  lea     rcx, DhcpGlobalNotificationListCritSect
0x180002ff9  add     rsp, 28h
0x180002ffd  jmp     cs:__imp_DeleteCriticalSection
```
