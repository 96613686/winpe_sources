# OFile::Delete(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180004ba8`
- end: `0x180004c5c`
- name: `?Delete@OFile@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180004b94`

## callees

- `0x180004ba8`
- `0x18003e690`
- `0x1800409e0`
- `0x180132398`
- `0x18013289c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004bda`
- `KERNEL32!GetLastError` at `0x180004c53`
- `KERNEL32!GetLastError` at `0x180004bda`
- `KERNEL32!GetLastError` at `0x180004c53`
- `KERNEL32!DeleteFileW` at `0x180004bd0`
- `KERNEL32!DeleteFileW` at `0x180004c49`
- `KERNEL32!DeleteFileW` at `0x180004bd0`
- `KERNEL32!DeleteFileW` at `0x180004c49`

## string_xrefs

- `0x180004c09`: `failed to delete file %s`

## pseudocode

```c
char __fastcall OFile::Delete(const WCHAR *a1)
{
  __int64 v1; // rbx
  DWORD LastError; // eax
  __int64 v3; // rdx
  const WCHAR *v5; // rcx
  _BYTE pExceptionObject[912]; // [rsp+30h] [rbp-3A8h] BYREF

  v1 = (__int64)a1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  if ( !DeleteFileW(a1) )
  {
    LastError = GetLastError();
    if ( LastError != 2 )
    {
      if ( LastError == 5 )
      {
        OFile::SetFileAttributesW(v1);
        v5 = (const WCHAR *)v1;
        if ( *(_QWORD *)(v1 + 24) > 7u )
          v5 = *(const WCHAR **)v1;
        if ( DeleteFileW(v5) )
          return 1;
        LastError = GetLastError();
      }
      if ( LastError )
      {
        OException::OException(pExceptionObject, v3, LastError, L"failed to delete file %s", v1);
        throw (OException *)pExceptionObject;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180004ba8  push    rbx
0x180004baa  sub     rsp, 3D0h
0x180004bb1  mov     rax, cs:__security_cookie
0x180004bb8  xor     rax, rsp
0x180004bbb  mov     [rsp+3D8h+var_18], rax
0x180004bc3  cmp     qword ptr [rcx+18h], 7
0x180004bc8  mov     rbx, rcx
0x180004bcb  jbe     short loc_180004BD0
0x180004bcd  mov     rcx, [rcx]; lpFileName
0x180004bd0  call    cs:__imp_DeleteFileW
0x180004bd6  test    eax, eax
0x180004bd8  jnz     short loc_180004BE5
0x180004bda  call    cs:__imp_GetLastError
0x180004be0  cmp     eax, 2
0x180004be3  jnz     short loc_180004C00
0x180004be5  mov     al, 1
0x180004be7  mov     rcx, [rsp+3D8h+var_18]
0x180004bef  xor     rcx, rsp; StackCookie
0x180004bf2  call    __security_check_cookie
0x180004bf7  add     rsp, 3D0h
0x180004bfe  pop     rbx
0x180004bff  retn
0x180004c00  cmp     eax, 5
0x180004c03  jz      short loc_180004C34
0x180004c05  test    eax, eax
0x180004c07  jz      short loc_180004BE5
0x180004c09  lea     r9, aFailedToDelete; "failed to delete file %s"
0x180004c10  mov     [rsp+3D8h+var_3B8], rbx
0x180004c15  mov     r8d, eax
0x180004c18  lea     rcx, [rsp+3D8h+pExceptionObject]
0x180004c1d  call    ??$?0$0BJ@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@OException@@QEAA@W4exceptionType@et@@IAEAY0BJ@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[25],std::wstring const &)
0x180004c22  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180004c29  lea     rcx, [rsp+3D8h+pExceptionObject]; pExceptionObject
0x180004c2e  call    _CxxThrowException
0x180004c34  mov     rcx, rbx
0x180004c37  call    ?SetFileAttributesW@OFile@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; OFile::SetFileAttributesW(std::wstring const &,ulong)
0x180004c3c  cmp     qword ptr [rbx+18h], 7
0x180004c41  mov     rcx, rbx
0x180004c44  jbe     short loc_180004C49
0x180004c46  mov     rcx, [rbx]; lpFileName
0x180004c49  call    cs:__imp_DeleteFileW
0x180004c4f  test    eax, eax
0x180004c51  jnz     short loc_180004BE5
0x180004c53  call    cs:__imp_GetLastError
0x180004c59  jmp     short loc_180004C05
```
