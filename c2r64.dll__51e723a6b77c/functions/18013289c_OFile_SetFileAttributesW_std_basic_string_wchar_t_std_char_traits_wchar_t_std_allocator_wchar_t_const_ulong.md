# OFile::SetFileAttributesW(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong)

- ea: `0x18013289c`
- end: `0x180132929`
- name: `?SetFileAttributesW@OFile@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180004ba8`

## callees

- `0x18003e690`
- `0x1800409e0`
- `0x180132460`
- `0x18013289c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801328d7`
- `KERNEL32!GetLastError` at `0x1801328d7`
- `KERNEL32!SetFileAttributesW` at `0x1801328cd`
- `KERNEL32!SetFileAttributesW` at `0x1801328cd`

## pseudocode

```c
BOOL __fastcall OFile::SetFileAttributesW(const WCHAR *a1)
{
  BOOL result; // eax
  DWORD LastError; // eax
  int v3; // r8d
  _BYTE pExceptionObject[912]; // [rsp+50h] [rbp-3A8h] BYREF

  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  result = SetFileAttributesW(a1, 0x80u);
  if ( !result )
  {
    LastError = GetLastError();
    OException::OException((unsigned int)pExceptionObject, 808464432, v3, LastError);
    throw (OException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18013289c  push    rbx
0x18013289e  sub     rsp, 3F0h
0x1801328a5  mov     rax, cs:__security_cookie
0x1801328ac  xor     rax, rsp
0x1801328af  mov     [rsp+3F8h+var_18], rax
0x1801328b7  cmp     qword ptr [rcx+18h], 7
0x1801328bc  mov     edx, 80h; dwFileAttributes
0x1801328c1  mov     [rsp+3F8h+var_3B8], edx
0x1801328c5  mov     rbx, rcx
0x1801328c8  jbe     short loc_1801328CD
0x1801328ca  mov     rcx, [rcx]; lpFileName
0x1801328cd  call    cs:__imp_SetFileAttributesW
0x1801328d3  test    eax, eax
0x1801328d5  jnz     short loc_180132910
0x1801328d7  call    cs:__imp_GetLastError
0x1801328dd  lea     rcx, [rsp+3F8h+var_3B8]
0x1801328e2  mov     edx, 30303030h
0x1801328e7  mov     [rsp+3F8h+var_3C8], rcx
0x1801328ec  mov     r9d, eax
0x1801328ef  lea     rcx, [rsp+3F8h+pExceptionObject]
0x1801328f4  mov     [rsp+3F8h+var_3D0], rbx
0x1801328f9  call    ??$?0$0CC@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@OException@@QEAA@Utag_t@0@W4exceptionType@et@@IAEAY0CC@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBK@Z; OException::OException(OException::tag_t,et::exceptionType,uint,wchar_t const (&)[34],std::wstring const &,ulong const &)
0x1801328fe  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180132905  lea     rcx, [rsp+3F8h+pExceptionObject]; pExceptionObject
0x18013290a  call    _CxxThrowException
0x180132910  mov     rcx, [rsp+3F8h+var_18]
0x180132918  xor     rcx, rsp; StackCookie
0x18013291b  call    __security_check_cookie
0x180132920  add     rsp, 3F0h
0x180132927  pop     rbx
0x180132928  retn
```
