# LuafvCopyStreamData

- ea: `0x140014cd0`
- end: `0x140014de8`
- name: `LuafvCopyStreamData`
- size: `280`
- prototype: `NTSTATUS __fastcall(PFLT_INSTANCE InitiatingInstance, PFILE_OBJECT FileObject, PFILE_OBJECT, __int64 *, PVOID Buffer, ULONG Length)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140023058`

## callees

- `0x140014cd0`

## import_xrefs

- `FLTMGR!FltWriteFile` at `0x140014dbf`
- `FLTMGR!FltWriteFile` at `0x140014dbf`
- `FLTMGR!FltReadFile` at `0x140014d6a`
- `FLTMGR!FltReadFile` at `0x140014d6a`
- `FLTMGR!FltSetInformationFile` at `0x140014d14`
- `FLTMGR!FltSetInformationFile` at `0x140014d14`

## pseudocode

```c
NTSTATUS __fastcall LuafvCopyStreamData(
        PFLT_INSTANCE InitiatingInstance,
        PFILE_OBJECT FileObject,
        PFILE_OBJECT a3,
        __int64 *a4,
        PVOID Buffer,
        ULONG Length)
{
  __int64 v6; // rax
  NTSTATUS result; // eax
  PVOID v11; // rdi
  __int64 v12; // rbx
  union _LARGE_INTEGER ByteOffset; // [rsp+50h] [rbp-18h] BYREF
  __int64 FileInformation; // [rsp+58h] [rbp-10h] BYREF
  ULONG BytesWritten; // [rsp+B8h] [rbp+50h] BYREF

  v6 = *a4;
  BytesWritten = 0;
  ByteOffset.QuadPart = 0;
  FileInformation = v6;
  result = FltSetInformationFile(InitiatingInstance, a3, &FileInformation, 8u, FileEndOfFileInformation);
  if ( result >= 0 )
  {
    v11 = Buffer;
    for ( ByteOffset.QuadPart = 0; ; ByteOffset.QuadPart += v12 )
    {
      result = FltReadFile(InitiatingInstance, FileObject, &ByteOffset, Length, v11, 0, &BytesWritten, 0, 0);
      if ( result == -1073741807 )
        break;
      if ( result < 0 )
        return result;
      if ( !BytesWritten )
        break;
      v12 = BytesWritten;
      result = FltWriteFile(InitiatingInstance, a3, &ByteOffset, BytesWritten, v11, 0, &BytesWritten, 0, 0);
      if ( result < 0 )
        return result;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140014cd0  push    rbp
0x140014cd2  push    rbx
0x140014cd3  push    rsi
0x140014cd4  push    rdi
0x140014cd5  push    r14
0x140014cd7  push    r15
0x140014cd9  mov     rbp, rsp
0x140014cdc  sub     rsp, 68h
0x140014ce0  mov     rax, [r9]
0x140014ce3  mov     r14, r8
0x140014ce6  mov     r15, rdx
0x140014ce9  mov     [rbp+BytesWritten], 0
0x140014cf0  mov     rdx, r14; FileObject
0x140014cf3  mov     qword ptr [rbp+ByteOffset], 0
0x140014cfb  mov     r9d, 8; Length
0x140014d01  mov     [rbp+FileInformation], rax
0x140014d05  lea     r8, [rbp+FileInformation]; FileInformation
0x140014d09  mov     [rsp+68h+FileInformationClass], 14h; FileInformationClass
0x140014d11  mov     rsi, rcx
0x140014d14  call    cs:__imp_FltSetInformationFile
0x140014d1b  nop     dword ptr [rax+rax+00h]
0x140014d20  test    eax, eax
0x140014d22  js      loc_140014DDA
0x140014d28  mov     rdi, [rbp+Buffer]
0x140014d2c  mov     qword ptr [rbp+ByteOffset], 0
0x140014d34  mov     r9d, [rbp+Length]; Length
0x140014d38  lea     rax, [rbp+BytesWritten]
0x140014d3c  mov     [rsp+68h+CallbackContext], 0; CallbackContext
0x140014d45  lea     r8, [rbp+ByteOffset]; ByteOffset
0x140014d49  mov     [rsp+68h+CallbackRoutine], 0; CallbackRoutine
0x140014d52  mov     rdx, r15; FileObject
0x140014d55  mov     [rsp+68h+BytesRead], rax; BytesRead
0x140014d5a  mov     rcx, rsi; InitiatingInstance
0x140014d5d  mov     [rsp+68h+Flags], 0; Flags
0x140014d65  mov     qword ptr [rsp+68h+FileInformationClass], rdi; Buffer
0x140014d6a  call    cs:__imp_FltReadFile
0x140014d71  nop     dword ptr [rax+rax+00h]
0x140014d76  cmp     eax, 0C0000011h
0x140014d7b  jz      short loc_140014DD8
0x140014d7d  test    eax, eax
0x140014d7f  js      short loc_140014DDA
0x140014d81  mov     eax, [rbp+BytesWritten]
0x140014d84  test    eax, eax
0x140014d86  jz      short loc_140014DD8
0x140014d88  mov     [rsp+68h+CallbackContext], 0; CallbackContext
0x140014d91  lea     r8, [rbp+ByteOffset]; ByteOffset
0x140014d95  mov     [rsp+68h+CallbackRoutine], 0; CallbackRoutine
0x140014d9e  mov     ebx, eax
0x140014da0  mov     r9d, eax; Length
0x140014da3  mov     rdx, r14; FileObject
0x140014da6  lea     rax, [rbp+BytesWritten]
0x140014daa  mov     rcx, rsi; InitiatingInstance
0x140014dad  mov     [rsp+68h+BytesRead], rax; BytesWritten
0x140014db2  mov     [rsp+68h+Flags], 0; Flags
0x140014dba  mov     qword ptr [rsp+68h+FileInformationClass], rdi; Buffer
0x140014dbf  call    cs:__imp_FltWriteFile
0x140014dc6  nop     dword ptr [rax+rax+00h]
0x140014dcb  test    eax, eax
0x140014dcd  js      short loc_140014DDA
0x140014dcf  add     qword ptr [rbp+ByteOffset], rbx
0x140014dd3  jmp     loc_140014D34
0x140014dd8  xor     eax, eax
0x140014dda  add     rsp, 68h
0x140014dde  pop     r15
0x140014de0  pop     r14
0x140014de2  pop     rdi
0x140014de3  pop     rsi
0x140014de4  pop     rbx
0x140014de5  pop     rbp
0x140014de6  retn
```
