# PuDeleteDebugPrintsObject

- ea: `0x180002788`
- end: `0x1800027f6`
- name: `PuDeleteDebugPrintsObject`
- size: `110`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001948`
- `0x1800020b0`

## callees

- `0x180002340`
- `0x180002788`
- `0x1800028a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800027d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800027d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800027b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800027b5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800027df`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800027df`

## pseudocode

```c
_QWORD *PuDeleteDebugPrintsObject()
{
  _QWORD *v0; // rbx
  void *v1; // rdi
  DWORD v2; // eax

  v0 = g_pDebug;
  if ( g_pDebug )
  {
    v1 = (void *)*((_QWORD *)g_pDebug + 82);
    if ( v1 )
    {
      CMemoryLog::~CMemoryLog(*((struct _RTL_CRITICAL_SECTION **)g_pDebug + 82));
      LocalFree(v1);
      v0[82] = 0;
    }
    v2 = PuCloseDbgPrintFile(v0);
    if ( v2 )
      SetLastError(v2);
    else
      return GlobalFree(v0);
  }
  return v0;
}

```

## disassembly

```asm
0x180002788  mov     [rsp+arg_0], rbx
0x18000278d  push    rdi
0x18000278e  sub     rsp, 20h
0x180002792  mov     rbx, cs:g_pDebug
0x180002799  test    rbx, rbx
0x18000279c  jz      short loc_1800027E8
0x18000279e  mov     rdi, [rbx+290h]
0x1800027a5  test    rdi, rdi
0x1800027a8  jz      short loc_1800027C6
0x1800027aa  mov     rcx, rdi; this
0x1800027ad  call    ??1CMemoryLog@@QEAA@XZ; CMemoryLog::~CMemoryLog(void)
0x1800027b2  mov     rcx, rdi; hMem
0x1800027b5  call    cs:__imp_LocalFree
0x1800027bb  mov     qword ptr [rbx+290h], 0
0x1800027c6  mov     rcx, rbx
0x1800027c9  call    PuCloseDbgPrintFile
0x1800027ce  test    eax, eax
0x1800027d0  jz      short loc_1800027DC
0x1800027d2  mov     ecx, eax; dwErrCode
0x1800027d4  call    cs:__imp_SetLastError
0x1800027da  jmp     short loc_1800027E8
0x1800027dc  mov     rcx, rbx; hMem
0x1800027df  call    cs:__imp_GlobalFree
0x1800027e5  mov     rbx, rax
0x1800027e8  mov     rax, rbx
0x1800027eb  mov     rbx, [rsp+28h+arg_0]
0x1800027f0  add     rsp, 20h
0x1800027f4  pop     rdi
0x1800027f5  retn
```
