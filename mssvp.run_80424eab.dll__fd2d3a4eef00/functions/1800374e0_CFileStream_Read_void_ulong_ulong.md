# CFileStream::Read(void *,ulong,ulong *)

- ea: `0x1800374e0`
- end: `0x18003753f`
- name: `?Read@CFileStream@@UEAAJPEAXKPEAK@Z`
- size: `95`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800374e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037518`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037518`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003750e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003750e`

## pseudocode

```c
signed int __fastcall CFileStream::Read(HANDLE *this, void *a2, DWORD a3, unsigned int *a4)
{
  DWORD v4; // eax
  signed int result; // eax
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  NumberOfBytesRead = 0;
  if ( !a2 )
    return -2147467261;
  if ( a3 )
  {
    if ( !ReadFile(this[3], a2, a3, &NumberOfBytesRead, 0) )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    v4 = NumberOfBytesRead;
  }
  if ( a4 )
    *a4 = v4;
  return 0;
}

```

## disassembly

```asm
0x1800374e0  push    rbx
0x1800374e2  sub     rsp, 30h
0x1800374e6  xor     eax, eax
0x1800374e8  mov     rbx, r9
0x1800374eb  mov     [rsp+38h+NumberOfBytesRead], eax
0x1800374ef  test    rdx, rdx
0x1800374f2  jnz     short loc_1800374FB
0x1800374f4  mov     eax, 80004003h
0x1800374f9  jmp     short loc_180037539
0x1800374fb  test    r8d, r8d
0x1800374fe  jz      short loc_180037530
0x180037500  mov     rcx, [rcx+18h]; hFile
0x180037504  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180037509  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x18003750e  call    cs:__imp_ReadFile
0x180037514  test    eax, eax
0x180037516  jnz     short loc_18003752C
0x180037518  call    cs:__imp_GetLastError
0x18003751e  test    eax, eax
0x180037520  jle     short loc_180037539
0x180037522  movzx   eax, ax
0x180037525  or      eax, 80070000h
0x18003752a  jmp     short loc_180037539
0x18003752c  mov     eax, [rsp+38h+NumberOfBytesRead]
0x180037530  test    rbx, rbx
0x180037533  jz      short loc_180037537
0x180037535  mov     [rbx], eax
0x180037537  xor     eax, eax
0x180037539  add     rsp, 30h
0x18003753d  pop     rbx
0x18003753e  retn
```
