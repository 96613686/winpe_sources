# OFile::Write(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180036038`
- end: `0x1800360fd`
- name: `?Write@OFile@@QEAA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180036024`

## callees

- `0x180036038`
- `0x18003e690`
- `0x1800409e0`
- `0x18004a3dc`
- `0x1801329b8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800360b2`
- `KERNEL32!GetLastError` at `0x1800360b2`
- `KERNEL32!WriteFile` at `0x1800360a8`
- `KERNEL32!WriteFile` at `0x1800360a8`

## string_xrefs

- `0x1800360b8`: `write to file failed`
- `0x18003605b`: `trying to write to a from a file that's not open`

## pseudocode

```c
char __fastcall OFile::Write(__int64 a1, const void **a2)
{
  void *v2; // rcx
  bool v3; // cc
  const void *v4; // rax
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-3B8h] BYREF
  _BYTE pExceptionObject[912]; // [rsp+40h] [rbp-3A8h] BYREF

  v2 = *(void **)(a1 + 48);
  if ( v2 == (void *)-1LL )
  {
    OException::OException(pExceptionObject, a2, L"trying to write to a from a file that's not open");
    throw (OException *)pExceptionObject;
  }
  v3 = (unsigned __int64)a2[3] <= 0xF;
  v4 = a2;
  NumberOfBytesWritten = 0;
  if ( !v3 )
    v4 = *a2;
  if ( !WriteFile(v2, v4, *((_DWORD *)a2 + 4), &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    OException::OException(pExceptionObject, 15, LastError, L"write to file failed");
    throw (OException *)pExceptionObject;
  }
  return 1;
}

```

## disassembly

```asm
0x180036038  sub     rsp, 3E8h
0x18003603f  mov     rax, cs:__security_cookie
0x180036046  xor     rax, rsp
0x180036049  mov     [rsp+3E8h+var_18], rax
0x180036051  mov     rcx, [rcx+30h]; hFile
0x180036055  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180036059  jnz     short loc_18003607E
0x18003605b  lea     r8, aTryingToWriteT; "trying to write to a from a file that's"...
0x180036062  lea     rcx, [rsp+3E8h+pExceptionObject]
0x180036067  call    ??$?0$0DB@@OException@@QEAA@W4exceptionType@et@@AEAY0DB@$$CB_W@Z; OException::OException(et::exceptionType,wchar_t const (&)[49])
0x18003606c  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180036073  lea     rcx, [rsp+3E8h+pExceptionObject]; pExceptionObject
0x180036078  call    _CxxThrowException
0x18003607e  cmp     qword ptr [rdx+18h], 0Fh
0x180036083  mov     rax, rdx
0x180036086  mov     [rsp+3E8h+NumberOfBytesWritten], 0
0x18003608e  jbe     short loc_180036093
0x180036090  mov     rax, [rdx]
0x180036093  mov     r8d, [rdx+10h]; nNumberOfBytesToWrite
0x180036097  lea     r9, [rsp+3E8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003609c  mov     rdx, rax; lpBuffer
0x18003609f  mov     [rsp+3E8h+lpOverlapped], 0; lpOverlapped
0x1800360a8  call    cs:__imp_WriteFile
0x1800360ae  test    eax, eax
0x1800360b0  jnz     short loc_1800360E3
0x1800360b2  call    cs:__imp_GetLastError
0x1800360b8  lea     r9, aWriteToFileFai; "write to file failed"
0x1800360bf  mov     edx, 0Fh
0x1800360c4  mov     r8d, eax
0x1800360c7  lea     rcx, [rsp+3E8h+pExceptionObject]
0x1800360cc  call    ??$?0$0BF@@OException@@QEAA@W4exceptionType@et@@IAEAY0BF@$$CB_W@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[21])
0x1800360d1  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x1800360d8  lea     rcx, [rsp+3E8h+pExceptionObject]; pExceptionObject
0x1800360dd  call    _CxxThrowException
0x1800360e3  mov     al, 1
0x1800360e5  mov     rcx, [rsp+3E8h+var_18]
0x1800360ed  xor     rcx, rsp; StackCookie
0x1800360f0  call    __security_check_cookie
0x1800360f5  add     rsp, 3E8h
0x1800360fc  retn
```
