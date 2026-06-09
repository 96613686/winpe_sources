# InternetReadFileWrap(void *,void *,ulong,ulong *)

- ea: `0x18000d020`
- end: `0x18000d04f`
- name: `?InternetReadFileWrap@@YAJPEAX0KPEAK@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000d020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d032`
- `WININET!InternetReadFile` at `0x18000d028`
- `WININET!InternetReadFile` at `0x18000d028`

## pseudocode

```c
__int64 __fastcall InternetReadFileWrap(void *a1, void *a2, DWORD a3, unsigned int *a4)
{
  unsigned int v4; // ebx
  signed int LastError; // eax

  v4 = 0;
  if ( !InternetReadFile(a1, a2, a3, a4) )
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
0x18000d020  push    rbx
0x18000d022  sub     rsp, 20h
0x18000d026  xor     ebx, ebx
0x18000d028  call    cs:__imp_InternetReadFile
0x18000d02e  test    eax, eax
0x18000d030  jnz     short loc_18000D047
0x18000d032  call    cs:__imp_GetLastError
0x18000d038  mov     ebx, eax
0x18000d03a  test    eax, eax
0x18000d03c  jle     short loc_18000D047
0x18000d03e  movzx   ebx, ax
0x18000d041  or      ebx, 80070000h
0x18000d047  mov     eax, ebx
0x18000d049  add     rsp, 20h
0x18000d04d  pop     rbx
0x18000d04e  retn
```
