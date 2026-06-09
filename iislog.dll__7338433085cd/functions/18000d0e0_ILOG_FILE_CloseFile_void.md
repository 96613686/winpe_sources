# ILOG_FILE::CloseFile(void)

- ea: `0x18000d0e0`
- end: `0x18000d136`
- name: `?CloseFile@ILOG_FILE@@QEAAHXZ`
- size: `86`
- prototype: `__int64 __fastcall(ILOG_FILE *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002c8c`
- `0x180003240`
- `0x18000d2f8`
- `0x18000d598`

## callees

- `0x18000d0e0`
- `0x18000d1e8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d10c`
- `KERNEL32!GetLastError` at `0x18000d10c`
- `KERNEL32!CloseHandle` at `0x18000d11e`
- `KERNEL32!CloseHandle` at `0x18000d11e`
- `KERNEL32!SetFilePointer` at `0x18000d101`
- `KERNEL32!SetFilePointer` at `0x18000d101`
- `KERNEL32!SetEndOfFile` at `0x18000d115`
- `KERNEL32!SetEndOfFile` at `0x18000d115`

## pseudocode

```c
__int64 __fastcall ILOG_FILE::CloseFile(LONG *this)
{
  ILOG_FILE::DestroyMapping((ILOG_FILE *)this);
  if ( *(_QWORD *)this != -1 )
  {
    if ( SetFilePointer(*(HANDLE *)this, this[10], this + 11, 0) == -1 )
      GetLastError();
    SetEndOfFile(*(HANDLE *)this);
    CloseHandle(*(HANDLE *)this);
    *(_QWORD *)this = -1;
  }
  return 1;
}

```

## disassembly

```asm
0x18000d0e0  push    rbx
0x18000d0e2  sub     rsp, 20h
0x18000d0e6  mov     rbx, rcx
0x18000d0e9  call    ?DestroyMapping@ILOG_FILE@@AEAAXXZ; ILOG_FILE::DestroyMapping(void)
0x18000d0ee  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000d0f2  jz      short loc_18000D12B
0x18000d0f4  mov     edx, [rbx+28h]; lDistanceToMove
0x18000d0f7  lea     r8, [rbx+2Ch]; lpDistanceToMoveHigh
0x18000d0fb  mov     rcx, [rbx]; hFile
0x18000d0fe  xor     r9d, r9d; dwMoveMethod
0x18000d101  call    cs:__imp_SetFilePointer
0x18000d107  cmp     eax, 0FFFFFFFFh
0x18000d10a  jnz     short loc_18000D112
0x18000d10c  call    cs:__imp_GetLastError
0x18000d112  mov     rcx, [rbx]; hFile
0x18000d115  call    cs:__imp_SetEndOfFile
0x18000d11b  mov     rcx, [rbx]; hObject
0x18000d11e  call    cs:__imp_CloseHandle
0x18000d124  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18000d12b  mov     eax, 1
0x18000d130  add     rsp, 20h
0x18000d134  pop     rbx
0x18000d135  retn
```
