# FtpGetCurrentDirectoryWrap(void *,char *,ulong)

- ea: `0x18000cc64`
- end: `0x18000cc9c`
- name: `?FtpGetCurrentDirectoryWrap@@YAJPEAXPEADK@Z`
- size: `56`
- prototype: `__int64 __fastcall(void *, char *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cbfc`
- `0x18000ff90`
- `0x180013108`
- `0x1800157fc`

## callees

- `0x18000cc64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc7f`
- `WININET!FtpGetCurrentDirectoryA` at `0x18000cc75`
- `WININET!FtpGetCurrentDirectoryA` at `0x18000cc75`

## pseudocode

```c
__int64 __fastcall FtpGetCurrentDirectoryWrap(void *a1, char *a2, DWORD a3)
{
  unsigned int v3; // ebx
  signed int LastError; // eax
  DWORD dwCurrentDirectory; // [rsp+40h] [rbp+18h] BYREF

  dwCurrentDirectory = a3;
  v3 = 0;
  if ( !FtpGetCurrentDirectoryA(a1, a2, &dwCurrentDirectory) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x18000cc64  mov     [rsp+dwCurrentDirectory], r8d
0x18000cc69  push    rbx
0x18000cc6a  sub     rsp, 20h
0x18000cc6e  lea     r8, [rsp+28h+dwCurrentDirectory]; lpdwCurrentDirectory
0x18000cc73  xor     ebx, ebx
0x18000cc75  call    cs:__imp_FtpGetCurrentDirectoryA
0x18000cc7b  test    eax, eax
0x18000cc7d  jnz     short loc_18000CC94
0x18000cc7f  call    cs:__imp_GetLastError
0x18000cc85  mov     ebx, eax
0x18000cc87  test    eax, eax
0x18000cc89  jle     short loc_18000CC94
0x18000cc8b  movzx   ebx, ax
0x18000cc8e  or      ebx, 80070000h
0x18000cc94  mov     eax, ebx
0x18000cc96  add     rsp, 20h
0x18000cc9a  pop     rbx
0x18000cc9b  retn
```
