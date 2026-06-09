# CFileStream::Read(void *,ulong,ulong *)

- ea: `0x180009fd0`
- end: `0x18000a033`
- name: `?Read@CFileStream@@UEAAJPEAXKPEAK@Z`
- size: `99`
- prototype: `signed int __fastcall(HANDLE *this, void *, DWORD, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180009fd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a001`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180009ff7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180009ff7`

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
0x180009fd0  push    rbx
0x180009fd2  sub     rsp, 30h
0x180009fd6  xor     eax, eax
0x180009fd8  mov     rbx, r9
0x180009fdb  mov     [rsp+38h+NumberOfBytesRead], eax
0x180009fdf  test    rdx, rdx
0x180009fe2  jz      short loc_18000A01E
0x180009fe4  test    r8d, r8d
0x180009fe7  jz      short loc_18000A015
0x180009fe9  mov     rcx, [rcx+18h]; hFile
0x180009fed  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180009ff2  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x180009ff7  call    cs:__imp_ReadFile
0x180009ffd  test    eax, eax
0x180009fff  jnz     short loc_18000A011
0x18000a001  call    cs:__imp_GetLastError
0x18000a007  test    eax, eax
0x18000a009  jg      short loc_18000A025
0x18000a00b  add     rsp, 30h
0x18000a00f  pop     rbx
0x18000a010  retn
0x18000a011  mov     eax, [rsp+38h+NumberOfBytesRead]
0x18000a015  test    rbx, rbx
0x18000a018  jnz     short loc_18000A02F
0x18000a01a  xor     eax, eax
0x18000a01c  jmp     short loc_18000A00B
0x18000a01e  mov     eax, 80004003h
0x18000a023  jmp     short loc_18000A00B
0x18000a025  movzx   eax, ax
0x18000a028  or      eax, 80070000h
0x18000a02d  jmp     short loc_18000A00B
0x18000a02f  mov     [rbx], eax
0x18000a031  jmp     short loc_18000A01A
```
