# PuDeleteDebugPrintsObject

- ea: `0x18000290c`
- end: `0x18000298d`
- name: `PuDeleteDebugPrintsObject`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001948`
- `0x180002170`

## callees

- `0x18000244c`
- `0x18000290c`
- `0x180002a50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000295e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000295e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002939`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002939`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000296f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000296f`

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
0x18000290c  mov     [rsp+arg_0], rbx
0x180002911  push    rdi
0x180002912  sub     rsp, 20h
0x180002916  mov     rbx, cs:g_pDebug
0x18000291d  test    rbx, rbx
0x180002920  jz      short loc_18000297E
0x180002922  mov     rdi, [rbx+290h]
0x180002929  test    rdi, rdi
0x18000292c  jz      short loc_180002950
0x18000292e  mov     rcx, rdi; this
0x180002931  call    ??1CMemoryLog@@QEAA@XZ; CMemoryLog::~CMemoryLog(void)
0x180002936  mov     rcx, rdi; hMem
0x180002939  call    cs:__imp_LocalFree
0x180002940  nop     dword ptr [rax+rax+00h]
0x180002945  mov     qword ptr [rbx+290h], 0
0x180002950  mov     rcx, rbx
0x180002953  call    PuCloseDbgPrintFile
0x180002958  test    eax, eax
0x18000295a  jz      short loc_18000296C
0x18000295c  mov     ecx, eax; dwErrCode
0x18000295e  call    cs:__imp_SetLastError
0x180002965  nop     dword ptr [rax+rax+00h]
0x18000296a  jmp     short loc_18000297E
0x18000296c  mov     rcx, rbx; hMem
0x18000296f  call    cs:__imp_GlobalFree
0x180002976  nop     dword ptr [rax+rax+00h]
0x18000297b  mov     rbx, rax
0x18000297e  mov     rax, rbx
0x180002981  mov     rbx, [rsp+28h+arg_0]
0x180002986  add     rsp, 20h
0x18000298a  pop     rdi
0x18000298b  retn
```
