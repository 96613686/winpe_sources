# _pSpUtilsInstallLogUninitialize

- ea: `0x180008424`
- end: `0x1800084a4`
- name: `_pSpUtilsInstallLogUninitialize`
- size: `128`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800031c0`
- `0x1800084ac`

## callees

- `0x180008424`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000843d`
- `KERNEL32!HeapFree` at `0x180008463`
- `KERNEL32!HeapFree` at `0x180008489`
- `KERNEL32!HeapFree` at `0x18000843d`
- `KERNEL32!HeapFree` at `0x180008463`
- `KERNEL32!HeapFree` at `0x180008489`

## pseudocode

```c
__int64 pSpUtilsInstallLogUninitialize()
{
  if ( InstallLogFilePath )
  {
    HeapFree(hHeap, 0, InstallLogFilePath);
    InstallLogFilePath = 0;
  }
  if ( EventLogFilePath )
  {
    HeapFree(hHeap, 0, EventLogFilePath);
    EventLogFilePath = 0;
  }
  if ( StringLogFilePath )
  {
    HeapFree(hHeap, 0, StringLogFilePath);
    StringLogFilePath = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180008424  sub     rsp, 28h
0x180008428  mov     r8, cs:InstallLogFilePath; lpMem
0x18000842f  test    r8, r8
0x180008432  jz      short loc_18000844E
0x180008434  mov     rcx, cs:hHeap; hHeap
0x18000843b  xor     edx, edx; dwFlags
0x18000843d  call    cs:__imp_HeapFree
0x180008443  mov     cs:InstallLogFilePath, 0
0x18000844e  mov     r8, cs:EventLogFilePath; lpMem
0x180008455  test    r8, r8
0x180008458  jz      short loc_180008474
0x18000845a  mov     rcx, cs:hHeap; hHeap
0x180008461  xor     edx, edx; dwFlags
0x180008463  call    cs:__imp_HeapFree
0x180008469  mov     cs:EventLogFilePath, 0
0x180008474  mov     r8, cs:StringLogFilePath; lpMem
0x18000847b  test    r8, r8
0x18000847e  jz      short loc_18000849A
0x180008480  mov     rcx, cs:hHeap; hHeap
0x180008487  xor     edx, edx; dwFlags
0x180008489  call    cs:__imp_HeapFree
0x18000848f  mov     cs:StringLogFilePath, 0
0x18000849a  mov     eax, 1
0x18000849f  add     rsp, 28h
0x1800084a3  retn
```
