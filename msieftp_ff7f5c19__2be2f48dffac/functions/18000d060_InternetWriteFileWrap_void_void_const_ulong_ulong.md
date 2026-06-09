# InternetWriteFileWrap(void *,void const *,ulong,ulong *)

- ea: `0x18000d060`
- end: `0x18000d08f`
- name: `?InternetWriteFileWrap@@YAJPEAXPEBXKPEAK@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000d060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d072`
- `WININET!InternetWriteFile` at `0x18000d068`
- `WININET!InternetWriteFile` at `0x18000d068`

## pseudocode

```c
__int64 __fastcall InternetWriteFileWrap(void *a1, const void *a2, DWORD a3, unsigned int *a4)
{
  unsigned int v4; // ebx
  signed int LastError; // eax

  v4 = 0;
  if ( !InternetWriteFile(a1, a2, a3, a4) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x18000d060  push    rbx
0x18000d062  sub     rsp, 20h
0x18000d066  xor     ebx, ebx
0x18000d068  call    cs:__imp_InternetWriteFile
0x18000d06e  test    eax, eax
0x18000d070  jnz     short loc_18000D087
0x18000d072  call    cs:__imp_GetLastError
0x18000d078  mov     ebx, eax
0x18000d07a  test    eax, eax
0x18000d07c  jle     short loc_18000D087
0x18000d07e  movzx   ebx, ax
0x18000d081  or      ebx, 80070000h
0x18000d087  mov     eax, ebx
0x18000d089  add     rsp, 20h
0x18000d08d  pop     rbx
0x18000d08e  retn
```
