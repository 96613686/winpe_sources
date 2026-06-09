# CFileStream::Write(void const *,ulong,ulong *)

- ea: `0x180037710`
- end: `0x180037775`
- name: `?Write@CFileStream@@UEAAJPEBXKPEAK@Z`
- size: `101`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180037710`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003774e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003774e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180037744`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180037744`

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
0x180037710  push    rbx
0x180037712  sub     rsp, 30h
0x180037716  mov     [rsp+38h+NumberOfBytesWritten], 0
0x18003771e  mov     rbx, r9
0x180037721  test    r8d, r8d
0x180037724  jz      short loc_18003776D
0x180037726  test    rdx, rdx
0x180037729  jnz     short loc_180037732
0x18003772b  mov     eax, 80004003h
0x180037730  jmp     short loc_18003776F
0x180037732  mov     rcx, [rcx+18h]; hFile
0x180037736  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003773b  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180037744  call    cs:__imp_WriteFile
0x18003774a  test    eax, eax
0x18003774c  jnz     short loc_180037762
0x18003774e  call    cs:__imp_GetLastError
0x180037754  test    eax, eax
0x180037756  jle     short loc_18003776F
0x180037758  movzx   eax, ax
0x18003775b  or      eax, 80070000h
0x180037760  jmp     short loc_18003776F
0x180037762  test    rbx, rbx
0x180037765  jz      short loc_18003776D
0x180037767  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x18003776b  mov     [rbx], eax
0x18003776d  xor     eax, eax
0x18003776f  add     rsp, 30h
0x180037773  pop     rbx
0x180037774  retn
```
