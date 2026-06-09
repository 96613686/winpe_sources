# IASGetLocalDictionary

- ea: `0x180002ba0`
- end: `0x180002c9b`
- name: `IASGetLocalDictionary`
- size: `251`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800027a0`
- `0x180002ba0`
- `0x180014708`
- `0x1800181e0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180002c57`
- `KERNEL32!SetLastError` at `0x180002c57`
- `KERNEL32!EnterCriticalSection` at `0x180002bc2`
- `KERNEL32!EnterCriticalSection` at `0x180002bc2`
- `KERNEL32!LeaveCriticalSection` at `0x180002c64`
- `KERNEL32!LeaveCriticalSection` at `0x180002c75`
- `KERNEL32!LeaveCriticalSection` at `0x180002c64`
- `KERNEL32!LeaveCriticalSection` at `0x180002c75`

## string_xrefs

- `0x180002bec`: `\dnary.xml`

## pseudocode

```c
__int64 *IASGetLocalDictionary()
{
  signed int DatabasePath; // eax
  bool v1; // sf
  bool v2; // cc
  unsigned int v4[4]; // [rsp+30h] [rbp-428h] BYREF
  BYTE v5[512]; // [rsp+40h] [rbp-418h] BYREF
  BYTE Destination[512]; // [rsp+240h] [rbp-218h] BYREF

  EnterCriticalSection(&theGlobalLock);
  if ( theDictionaryStorage.vt )
    goto LABEL_10;
  v4[0] = 256;
  DatabasePath = anonymous_namespace_::GetDatabasePath((wchar_t *)L"\\dnary.xml", Destination, v4);
  v1 = DatabasePath < 0;
  v2 = DatabasePath <= 0;
  if ( DatabasePath
    || (v4[0] = 256,
        DatabasePath = anonymous_namespace_::GetDatabasePath((wchar_t *)L"\\dnary.xsd", v5, v4),
        v1 = DatabasePath < 0,
        v2 = DatabasePath <= 0,
        DatabasePath) )
  {
    if ( v2 )
      goto LABEL_8;
    DatabasePath = (unsigned __int16)DatabasePath | 0x80070000;
  }
  else
  {
    DatabasePath = IASGetDictionary(
                     0,
                     (__int64)Destination,
                     (__int64)v5,
                     (struct _IASTable *)qword_180025808,
                     &theDictionaryStorage);
  }
  v1 = DatabasePath < 0;
LABEL_8:
  if ( v1 )
  {
    SetLastError(DatabasePath);
    LeaveCriticalSection(&theGlobalLock);
    return 0;
  }
LABEL_10:
  LeaveCriticalSection(&theGlobalLock);
  return qword_180025808;
}

```

## disassembly

```asm
0x180002ba0  push    rbx
0x180002ba2  sub     rsp, 450h
0x180002ba9  mov     rax, cs:__security_cookie
0x180002bb0  xor     rax, rsp
0x180002bb3  mov     [rsp+458h+var_18], rax
0x180002bbb  lea     rcx, ?theGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002bc2  call    cs:__imp_EnterCriticalSection
0x180002bc8  xor     ebx, ebx
0x180002bca  cmp     word ptr cs:?theDictionaryStorage@@3UtagVARIANT@@A, bx; tagVARIANT theDictionaryStorage ...
0x180002bd1  jnz     loc_180002C6E
0x180002bd7  lea     r8, [rsp+458h+var_428]
0x180002bdc  mov     [rsp+458h+var_428], 100h
0x180002be4  lea     rdx, [rsp+458h+Destination]; Destination
0x180002bec  lea     rcx, aDnaryXml; "\\dnary.xml"
0x180002bf3  call    _anonymous_namespace___GetDatabasePath
0x180002bf8  test    eax, eax
0x180002bfa  jnz     short loc_180002C1E
0x180002bfc  lea     r8, [rsp+458h+var_428]
0x180002c01  mov     [rsp+458h+var_428], 100h
0x180002c09  lea     rdx, [rsp+458h+var_418]; Destination
0x180002c0e  lea     rcx, aDnaryXsd; "\\dnary.xsd"
0x180002c15  call    _anonymous_namespace___GetDatabasePath
0x180002c1a  test    eax, eax
0x180002c1c  jz      short loc_180002C2A
0x180002c1e  jle     short loc_180002C53
0x180002c20  movzx   eax, ax
0x180002c23  or      eax, 80070000h
0x180002c28  jmp     short loc_180002C51
0x180002c2a  lea     rax, ?theDictionaryStorage@@3UtagVARIANT@@A; tagVARIANT theDictionaryStorage
0x180002c31  xor     ecx, ecx; unsigned __int16 *
0x180002c33  lea     r9, qword_180025808
0x180002c3a  mov     [rsp+458h+pvarg], rax; pvarg
0x180002c3f  lea     r8, [rsp+458h+var_418]
0x180002c44  lea     rdx, [rsp+458h+Destination]
0x180002c4c  call    IASGetDictionary
0x180002c51  test    eax, eax
0x180002c53  jns     short loc_180002C6E
0x180002c55  mov     ecx, eax; dwErrCode
0x180002c57  call    cs:__imp_SetLastError
0x180002c5d  lea     rcx, ?theGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002c64  call    cs:__imp_LeaveCriticalSection
0x180002c6a  xor     eax, eax
0x180002c6c  jmp     short loc_180002C82
0x180002c6e  lea     rcx, ?theGlobalLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002c75  call    cs:__imp_LeaveCriticalSection
0x180002c7b  lea     rax, qword_180025808
0x180002c82  mov     rcx, [rsp+458h+var_18]
0x180002c8a  xor     rcx, rsp; StackCookie
0x180002c8d  call    __security_check_cookie
0x180002c92  add     rsp, 450h
0x180002c99  pop     rbx
0x180002c9a  retn
```
