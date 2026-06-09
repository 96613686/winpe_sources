# CFileStream::Write(void const *,ulong,ulong *)

- ea: `0x1800236c0`
- end: `0x180023725`
- name: `?Write@CFileStream@@UEAAJPEBXKPEAK@Z`
- size: `101`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800236c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236fe`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800236f4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800236f4`

## pseudocode

```c
signed int __fastcall CFileStream::Write(HANDLE *this, const void *a2, DWORD a3, unsigned int *a4)
{
  signed int result; // eax
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp+18h] BYREF

  NumberOfBytesWritten = 0;
  if ( !a3 )
    return 0;
  if ( !a2 )
    return -2147467261;
  if ( WriteFile(this[3], a2, a3, &NumberOfBytesWritten, 0) )
  {
    if ( a4 )
      *a4 = NumberOfBytesWritten;
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800236c0  push    rbx
0x1800236c2  sub     rsp, 30h
0x1800236c6  mov     [rsp+38h+NumberOfBytesWritten], 0
0x1800236ce  mov     rbx, r9
0x1800236d1  test    r8d, r8d
0x1800236d4  jz      short loc_18002371D
0x1800236d6  test    rdx, rdx
0x1800236d9  jnz     short loc_1800236E2
0x1800236db  mov     eax, 80004003h
0x1800236e0  jmp     short loc_18002371F
0x1800236e2  mov     rcx, [rcx+18h]; hFile
0x1800236e6  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800236eb  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800236f4  call    cs:__imp_WriteFile
0x1800236fa  test    eax, eax
0x1800236fc  jnz     short loc_180023712
0x1800236fe  call    cs:__imp_GetLastError
0x180023704  test    eax, eax
0x180023706  jle     short loc_18002371F
0x180023708  movzx   eax, ax
0x18002370b  or      eax, 80070000h
0x180023710  jmp     short loc_18002371F
0x180023712  test    rbx, rbx
0x180023715  jz      short loc_18002371D
0x180023717  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x18002371b  mov     [rbx], eax
0x18002371d  xor     eax, eax
0x18002371f  add     rsp, 30h
0x180023723  pop     rbx
0x180023724  retn
```
