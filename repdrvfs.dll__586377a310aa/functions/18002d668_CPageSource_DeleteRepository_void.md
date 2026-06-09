# CPageSource::DeleteRepository(void)

- ea: `0x18002d668`
- end: `0x18002d754`
- name: `?DeleteRepository@CPageSource@@AEAAKXZ`
- size: `236`
- prototype: `int __fastcall(CPageSource *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002fd70`

## callees

- `0x1800216c8`
- `0x18002cff8`
- `0x18002d668`
- `0x18003c16c`
- `0x180044420`

## import_xrefs

- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002d696`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002d6c3`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002d6f1`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002d696`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002d6c3`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x18002d6f1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d69f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d6cc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d715`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d69f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d6cc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d71f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d71f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall CPageSource::DeleteRepository(CPageSource *this)
{
  const WCHAR *v2; // rax
  int result; // eax
  const WCHAR *v4; // rax
  int v5; // ebx
  const unsigned __int16 *v6; // rax
  WCHAR FileName[264]; // [rsp+20h] [rbp-228h] BYREF

  CPageSource::CloseRepositoryFiles(this);
  v2 = (const WCHAR *)WString::operator unsigned short *((char *)this + 944);
  if ( !DeleteFileW(v2) && GetLastError() != 2 )
    return GetLastError();
  v4 = (const WCHAR *)WString::operator unsigned short *((char *)this + 952);
  if ( !DeleteFileW(v4) && GetLastError() != 2 )
    return GetLastError();
  v5 = 0;
  while ( v5 < 3 )
  {
    ++v5;
    v6 = (const unsigned __int16 *)WString::operator unsigned short *((char *)this + 960);
    result = StringCchPrintfW(FileName, 0x105u, v6, (unsigned int)v5);
    if ( result < 0 )
      return result;
    if ( !DeleteFileW(FileName) && GetLastError() != 2 )
      return GetLastError();
  }
  ReportFutureCorruption();
  return 0;
}

```

## disassembly

```asm
0x18002d668  mov     [rsp+arg_8], rbx
0x18002d66d  push    rdi
0x18002d66e  sub     rsp, 240h
0x18002d675  mov     rax, cs:__security_cookie
0x18002d67c  xor     rax, rsp
0x18002d67f  mov     [rsp+248h+var_18], rax
0x18002d687  mov     rdi, rcx
0x18002d68a  call    ?CloseRepositoryFiles@CPageSource@@AEAAKXZ; CPageSource::CloseRepositoryFiles(void)
0x18002d68f  lea     rcx, [rdi+3B0h]
0x18002d696  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x18002d69c  mov     rcx, rax; lpFileName
0x18002d69f  call    cs:__imp_DeleteFileW
0x18002d6a5  test    eax, eax
0x18002d6a7  jnz     short loc_18002D6BC
0x18002d6a9  call    cs:__imp_GetLastError
0x18002d6af  cmp     eax, 2
0x18002d6b2  jz      short loc_18002D6BC
0x18002d6b4  call    cs:__imp_GetLastError
0x18002d6ba  jmp     short loc_18002D733
0x18002d6bc  lea     rcx, [rdi+3B8h]
0x18002d6c3  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x18002d6c9  mov     rcx, rax; lpFileName
0x18002d6cc  call    cs:__imp_DeleteFileW
0x18002d6d2  test    eax, eax
0x18002d6d4  jnz     short loc_18002D6E1
0x18002d6d6  call    cs:__imp_GetLastError
0x18002d6dc  cmp     eax, 2
0x18002d6df  jnz     short loc_18002D6B4
0x18002d6e1  xor     ebx, ebx
0x18002d6e3  cmp     ebx, 3
0x18002d6e6  jge     short loc_18002D72C
0x18002d6e8  lea     rcx, [rdi+3C0h]
0x18002d6ef  inc     ebx
0x18002d6f1  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x18002d6f7  mov     r9d, ebx
0x18002d6fa  lea     rcx, [rsp+248h+FileName]; unsigned __int16 *
0x18002d6ff  mov     r8, rax; unsigned __int16 *
0x18002d702  mov     edx, 105h; unsigned __int64
0x18002d707  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d70c  test    eax, eax
0x18002d70e  js      short loc_18002D733
0x18002d710  lea     rcx, [rsp+248h+FileName]; lpFileName
0x18002d715  call    cs:__imp_DeleteFileW
0x18002d71b  test    eax, eax
0x18002d71d  jnz     short loc_18002D6E3
0x18002d71f  call    cs:__imp_GetLastError
0x18002d725  cmp     eax, 2
0x18002d728  jz      short loc_18002D6E3
0x18002d72a  jmp     short loc_18002D6B4
0x18002d72c  call    ?ReportFutureCorruption@@YAJXZ; ReportFutureCorruption(void)
0x18002d731  xor     eax, eax
0x18002d733  mov     rcx, [rsp+248h+var_18]
0x18002d73b  xor     rcx, rsp; StackCookie
0x18002d73e  call    __security_check_cookie
0x18002d743  mov     rbx, [rsp+248h+arg_8]
0x18002d74b  add     rsp, 240h
0x18002d752  pop     rdi
0x18002d753  retn
```
