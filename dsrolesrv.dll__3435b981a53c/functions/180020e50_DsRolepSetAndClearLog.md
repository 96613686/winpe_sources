# DsRolepSetAndClearLog

- ea: `0x180020e50`
- end: `0x180020ebb`
- name: `DsRolepSetAndClearLog`
- size: `107`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180016d54`
- `0x180017890`
- `0x18001ff18`

## callees

- `0x180020e50`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180020e7a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180020e7a`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180020e94`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180020e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e9e`
- `ntdll!RtlLeaveCriticalSection` at `0x180020ead`
- `ntdll!RtlLeaveCriticalSection` at `0x180020ead`
- `ntdll!RtlEnterCriticalSection` at `0x180020e5f`
- `ntdll!RtlEnterCriticalSection` at `0x180020e5f`

## pseudocode

```c
__int64 DsRolepSetAndClearLog()
{
  DWORD LastError; // ebx

  LastError = 0;
  RtlEnterCriticalSection(&LogFileCriticalSection);
  if ( DsRolepLogFile )
  {
    if ( SetFilePointer(DsRolepLogFile, 0, 0, 2u) == -1 )
      LastError = GetLastError();
    if ( !FlushFileBuffers(DsRolepLogFile) )
      LastError = GetLastError();
  }
  RtlLeaveCriticalSection(&LogFileCriticalSection);
  return LastError;
}

```

## disassembly

```asm
0x180020e50  push    rbx
0x180020e52  sub     rsp, 20h
0x180020e56  lea     rcx, LogFileCriticalSection; CriticalSection
0x180020e5d  xor     ebx, ebx
0x180020e5f  call    cs:__imp_RtlEnterCriticalSection
0x180020e65  mov     rcx, cs:DsRolepLogFile; hFile
0x180020e6c  test    rcx, rcx
0x180020e6f  jz      short loc_180020EA6
0x180020e71  lea     r9d, [rbx+2]; dwMoveMethod
0x180020e75  xor     r8d, r8d; lpDistanceToMoveHigh
0x180020e78  xor     edx, edx; lDistanceToMove
0x180020e7a  call    cs:__imp_SetFilePointer
0x180020e80  cmp     eax, 0FFFFFFFFh
0x180020e83  jnz     short loc_180020E8D
0x180020e85  call    cs:__imp_GetLastError
0x180020e8b  mov     ebx, eax
0x180020e8d  mov     rcx, cs:DsRolepLogFile; hFile
0x180020e94  call    cs:__imp_FlushFileBuffers
0x180020e9a  test    eax, eax
0x180020e9c  jnz     short loc_180020EA6
0x180020e9e  call    cs:__imp_GetLastError
0x180020ea4  mov     ebx, eax
0x180020ea6  lea     rcx, LogFileCriticalSection; CriticalSection
0x180020ead  call    cs:__imp_RtlLeaveCriticalSection
0x180020eb3  mov     eax, ebx
0x180020eb5  add     rsp, 20h
0x180020eb9  pop     rbx
0x180020eba  retn
```
