# SipFile::Write(unsigned __int64,ulong,void const *)

- ea: `0x180005220`
- end: `0x1800052ab`
- name: `?Write@SipFile@@QEAAK_KKPEBX@Z`
- size: `139`
- prototype: `unsigned int(SipFile *__hidden this, unsigned __int64, unsigned int, const void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800025b0`
- `0x180004fd4`

## callees

- `0x180005220`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x18000524c`
- `KERNEL32!SetFilePointerEx` at `0x18000524c`
- `KERNEL32!WriteFile` at `0x18000527e`
- `KERNEL32!WriteFile` at `0x18000527e`
- `KERNEL32!GetLastError` at `0x180005256`
- `KERNEL32!GetLastError` at `0x180005256`

## pseudocode

```c
unsigned int __fastcall SipFile::Write(HANDLE *this, LARGE_INTEGER a2, DWORD a3, const void *a4)
{
  unsigned int result; // eax
  HANDLE v8; // rcx
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp+18h] BYREF

  if ( !a3 || !a4 )
    return 87;
  if ( !SetFilePointerEx(this[4], a2, 0, 0) )
    return GetLastError();
  v8 = this[4];
  NumberOfBytesWritten = 0;
  if ( !WriteFile(v8, a4, a3, &NumberOfBytesWritten, 0) )
    return GetLastError();
  result = 0;
  if ( NumberOfBytesWritten != a3 )
    return 13;
  return result;
}

```

## disassembly

```asm
0x180005220  mov     [rsp+arg_0], rbx
0x180005225  mov     [rsp+arg_8], rsi
0x18000522a  push    rdi
0x18000522b  sub     rsp, 30h
0x18000522f  mov     rdi, r9
0x180005232  mov     ebx, r8d
0x180005235  mov     rsi, rcx
0x180005238  test    r8d, r8d
0x18000523b  jz      short loc_180005296
0x18000523d  test    r9, r9
0x180005240  jz      short loc_180005296
0x180005242  mov     rcx, [rcx+20h]; hFile
0x180005246  xor     r9d, r9d; dwMoveMethod
0x180005249  xor     r8d, r8d; lpNewFilePointer
0x18000524c  call    cs:__imp_SetFilePointerEx
0x180005252  test    eax, eax
0x180005254  jnz     short loc_18000525E
0x180005256  call    cs:__imp_GetLastError
0x18000525c  jmp     short loc_18000529B
0x18000525e  mov     rcx, [rsi+20h]; hFile
0x180005262  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180005267  mov     r8d, ebx; nNumberOfBytesToWrite
0x18000526a  mov     [rsp+38h+NumberOfBytesWritten], 0
0x180005272  mov     rdx, rdi; lpBuffer
0x180005275  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18000527e  call    cs:__imp_WriteFile
0x180005284  test    eax, eax
0x180005286  jz      short loc_180005256
0x180005288  xor     eax, eax
0x18000528a  cmp     [rsp+38h+NumberOfBytesWritten], ebx
0x18000528e  lea     ecx, [rax+0Dh]
0x180005291  cmovnz  eax, ecx
0x180005294  jmp     short loc_18000529B
0x180005296  mov     eax, 57h ; 'W'
0x18000529b  mov     rbx, [rsp+38h+arg_0]
0x1800052a0  mov     rsi, [rsp+38h+arg_8]
0x1800052a5  add     rsp, 30h
0x1800052a9  pop     rdi
0x1800052aa  retn
```
