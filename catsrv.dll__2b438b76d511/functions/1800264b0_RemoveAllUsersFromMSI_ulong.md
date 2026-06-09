# RemoveAllUsersFromMSI(ulong)

- ea: `0x1800264b0`
- end: `0x180026583`
- name: `?RemoveAllUsersFromMSI@@YAJK@Z`
- size: `211`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x18002673c`

## callees

- `0x1800264b0`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026554`
- `msi!__imp_MsiCloseHandle` at `0x180026546`
- `msi!__imp_MsiCloseHandle` at `0x180026546`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002652c`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18002652c`
- `msi!__imp_MsiViewExecute` at `0x18002653b`
- `msi!__imp_MsiViewExecute` at `0x18002653b`

## string_xrefs

- `0x1800264d0`: `DELETE FROM Property WHERE Property = 'ALLUSERS'`

## pseudocode

```c
signed int __fastcall RemoveAllUsersFromMSI(MSIHANDLE a1)
{
  UINT v1; // ebx
  signed int result; // eax
  MSIHANDLE phView[4]; // [rsp+20h] [rbp-39h] BYREF
  WCHAR szQuery[56]; // [rsp+30h] [rbp-29h] BYREF

  wcscpy(szQuery, L"DELETE FROM Property WHERE Property = 'ALLUSERS'");
  phView[0] = 0;
  if ( !MsiDatabaseOpenViewW(a1, szQuery, phView) )
  {
    v1 = MsiViewExecute(phView[0], 0);
    MsiCloseHandle(phView[0]);
    if ( !v1 )
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
0x1800264b0  mov     [rsp-8+arg_8], rbx
0x1800264b5  push    rbp
0x1800264b6  lea     rbp, [rsp-57h]
0x1800264bb  sub     rsp, 0B0h
0x1800264c2  mov     rax, cs:__security_cookie
0x1800264c9  xor     rax, rsp
0x1800264cc  mov     [rbp+57h+var_10], rax
0x1800264d0  movaps  xmm0, xmmword ptr cs:aDeleteFromProp; "DELETE FROM Property WHERE Property = '"...
0x1800264d7  lea     r8, [rbp+57h+phView]; phView
0x1800264db  movaps  xmm1, xmmword ptr cs:aDeleteFromProp+10h; "ROM Property WHERE Property = 'ALLUSERS"...
0x1800264e2  lea     rdx, [rbp+57h+szQuery]; szQuery
0x1800264e6  movzx   eax, word ptr cs:aDeleteFromProp+60h; ""
0x1800264ed  movaps  xmmword ptr [rbp+57h+szQuery], xmm0
0x1800264f1  movaps  xmm0, xmmword ptr cs:aDeleteFromProp+20h; "erty WHERE Property = 'ALLUSERS'"
0x1800264f8  movaps  [rbp+57h+var_70], xmm1
0x1800264fc  movaps  xmm1, xmmword ptr cs:aDeleteFromProp+30h; "RE Property = 'ALLUSERS'"
0x180026503  movaps  [rbp+57h+var_60], xmm0
0x180026507  movaps  xmm0, xmmword ptr cs:aDeleteFromProp+40h; "rty = 'ALLUSERS'"
0x18002650e  movaps  [rbp+57h+var_50], xmm1
0x180026512  movaps  xmm1, xmmword ptr cs:aDeleteFromProp+50h; "LLUSERS'"
0x180026519  movaps  [rbp+57h+var_40], xmm0
0x18002651d  movaps  [rbp+57h+var_30], xmm1
0x180026521  mov     [rbp+57h+var_20], ax
0x180026525  mov     [rbp+57h+phView], 0
0x18002652c  call    cs:__imp_MsiDatabaseOpenViewW
0x180026532  test    eax, eax
0x180026534  jnz     short loc_180026554
0x180026536  mov     ecx, [rbp+57h+phView]; hView
0x180026539  xor     edx, edx; hRecord
0x18002653b  call    cs:__imp_MsiViewExecute
0x180026541  mov     ecx, [rbp+57h+phView]; hAny
0x180026544  mov     ebx, eax
0x180026546  call    cs:__imp_MsiCloseHandle
0x18002654c  test    ebx, ebx
0x18002654e  jnz     short loc_180026554
0x180026550  xor     eax, eax
0x180026552  jmp     short loc_180026566
0x180026554  call    cs:__imp_GetLastError
0x18002655a  test    eax, eax
0x18002655c  jle     short loc_180026566
0x18002655e  movzx   eax, ax
0x180026561  or      eax, 80070000h
0x180026566  mov     rcx, [rbp+57h+var_10]
0x18002656a  xor     rcx, rsp; StackCookie
0x18002656d  call    __security_check_cookie
0x180026572  mov     rbx, [rsp+0B0h+arg_8]
0x18002657a  add     rsp, 0B0h
0x180026581  pop     rbp
0x180026582  retn
```
