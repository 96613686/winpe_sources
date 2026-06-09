# FtpSetCurrentDirectoryWrap(void *,char const *)

- ea: `0x18000cd98`
- end: `0x18000cdc7`
- name: `?FtpSetCurrentDirectoryWrap@@YAJPEAXPEBD@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cca4`
- `0x18000ff90`
- `0x180013108`
- `0x1800157fc`
- `0x18001e2d4`

## callees

- `0x18000cd98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdaa`
- `WININET!FtpSetCurrentDirectoryA` at `0x18000cda0`
- `WININET!FtpSetCurrentDirectoryA` at `0x18000cda0`

## pseudocode

```c
__int64 __fastcall FtpSetCurrentDirectoryWrap(void *a1, const char *a2)
{
  unsigned int v2; // ebx
  signed int LastError; // eax

  v2 = 0;
  if ( !FtpSetCurrentDirectoryA(a1, a2) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v2;
}

```

## disassembly

```asm
0x18000cd98  push    rbx
0x18000cd9a  sub     rsp, 20h
0x18000cd9e  xor     ebx, ebx
0x18000cda0  call    cs:__imp_FtpSetCurrentDirectoryA
0x18000cda6  test    eax, eax
0x18000cda8  jnz     short loc_18000CDBF
0x18000cdaa  call    cs:__imp_GetLastError
0x18000cdb0  mov     ebx, eax
0x18000cdb2  test    eax, eax
0x18000cdb4  jle     short loc_18000CDBF
0x18000cdb6  movzx   ebx, ax
0x18000cdb9  or      ebx, 80070000h
0x18000cdbf  mov     eax, ebx
0x18000cdc1  add     rsp, 20h
0x18000cdc5  pop     rbx
0x18000cdc6  retn
```
