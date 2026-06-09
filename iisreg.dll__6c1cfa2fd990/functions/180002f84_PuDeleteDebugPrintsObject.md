# PuDeleteDebugPrintsObject

- ea: `0x180002f84`
- end: `0x180002ff2`
- name: `PuDeleteDebugPrintsObject`
- size: `110`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800018e0`
- `0x180001a20`

## callees

- `0x180002ec8`
- `0x180002f84`
- `0x18000351c`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x180002fdb`
- `KERNEL32!GlobalFree` at `0x180002fdb`
- `KERNEL32!SetLastError` at `0x180002fd0`
- `KERNEL32!SetLastError` at `0x180002fd0`
- `KERNEL32!LocalFree` at `0x180002fb1`
- `KERNEL32!LocalFree` at `0x180002fb1`

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
0x180002f84  mov     [rsp+arg_0], rbx
0x180002f89  push    rdi
0x180002f8a  sub     rsp, 20h
0x180002f8e  mov     rbx, cs:g_pDebug
0x180002f95  test    rbx, rbx
0x180002f98  jz      short loc_180002FE4
0x180002f9a  mov     rdi, [rbx+290h]
0x180002fa1  test    rdi, rdi
0x180002fa4  jz      short loc_180002FC2
0x180002fa6  mov     rcx, rdi; this
0x180002fa9  call    ??1CMemoryLog@@QEAA@XZ; CMemoryLog::~CMemoryLog(void)
0x180002fae  mov     rcx, rdi; hMem
0x180002fb1  call    cs:__imp_LocalFree
0x180002fb7  mov     qword ptr [rbx+290h], 0
0x180002fc2  mov     rcx, rbx
0x180002fc5  call    PuCloseDbgPrintFile
0x180002fca  test    eax, eax
0x180002fcc  jz      short loc_180002FD8
0x180002fce  mov     ecx, eax; dwErrCode
0x180002fd0  call    cs:__imp_SetLastError
0x180002fd6  jmp     short loc_180002FE4
0x180002fd8  mov     rcx, rbx; hMem
0x180002fdb  call    cs:__imp_GlobalFree
0x180002fe1  mov     rbx, rax
0x180002fe4  mov     rax, rbx
0x180002fe7  mov     rbx, [rsp+28h+arg_0]
0x180002fec  add     rsp, 20h
0x180002ff0  pop     rdi
0x180002ff1  retn
```
