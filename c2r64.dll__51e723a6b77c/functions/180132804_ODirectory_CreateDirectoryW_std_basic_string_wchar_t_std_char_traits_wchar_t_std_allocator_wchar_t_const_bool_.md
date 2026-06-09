# ODirectory::CreateDirectoryW(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool,_SECURITY_ATTRIBUTES *)

- ea: `0x180132804`
- end: `0x18013289c`
- name: `?CreateDirectoryW@ODirectory@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004660`

## callees

- `0x18003e690`
- `0x1800409e0`
- `0x1801325f4`
- `0x180132804`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18013283f`
- `KERNEL32!GetLastError` at `0x18013283f`
- `KERNEL32!CreateDirectoryW` at `0x180132835`
- `KERNEL32!CreateDirectoryW` at `0x180132835`

## pseudocode

```c
char __fastcall ODirectory::CreateDirectoryW(__int64 a1, char a2)
{
  __int64 v3; // rbx
  DWORD LastError; // eax
  int v5; // edx
  int v6; // r9d
  _BYTE pExceptionObject[912]; // [rsp+30h] [rbp-3A8h] BYREF

  v3 = a1;
  if ( *(_QWORD *)(a1 + 24) > 7u )
    a1 = *(_QWORD *)a1;
  if ( CreateDirectoryW((LPCWSTR)a1, 0) )
    return 1;
  LastError = GetLastError();
  if ( LastError == 183 )
    return 1;
  if ( a2 )
  {
    OException::OException((unsigned int)pExceptionObject, v5, LastError, v6, v3);
    throw (OException *)pExceptionObject;
  }
  return 0;
}

```

## disassembly

```asm
0x180132804  mov     [rsp+arg_8], rbx
0x180132809  push    rdi
0x18013280a  sub     rsp, 3D0h
0x180132811  mov     rax, cs:__security_cookie
0x180132818  xor     rax, rsp
0x18013281b  mov     [rsp+3D8h+var_18], rax
0x180132823  cmp     qword ptr [rcx+18h], 7
0x180132828  mov     dil, dl
0x18013282b  mov     rbx, rcx
0x18013282e  jbe     short loc_180132833
0x180132830  mov     rcx, [rcx]; lpPathName
0x180132833  xor     edx, edx; lpSecurityAttributes
0x180132835  call    cs:__imp_CreateDirectoryW
0x18013283b  test    eax, eax
0x18013283d  jnz     short loc_180132879
0x18013283f  call    cs:__imp_GetLastError
0x180132845  cmp     eax, 0B7h
0x18013284a  jz      short loc_180132879
0x18013284c  test    dil, dil
0x18013284f  jz      short loc_180132875
0x180132851  mov     r8d, eax
0x180132854  mov     [rsp+3D8h+var_3B8], rbx
0x180132859  lea     rcx, [rsp+3D8h+pExceptionObject]
0x18013285e  call    ??$?0$0CJ@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@OException@@QEAA@W4exceptionType@et@@IAEAY0CJ@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[41],std::wstring const &)
0x180132863  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18013286a  lea     rcx, [rsp+3D8h+pExceptionObject]; pExceptionObject
0x18013286f  call    _CxxThrowException
0x180132875  xor     al, al
0x180132877  jmp     short loc_18013287B
0x180132879  mov     al, 1
0x18013287b  mov     rcx, [rsp+3D8h+var_18]
0x180132883  xor     rcx, rsp; StackCookie
0x180132886  call    __security_check_cookie
0x18013288b  mov     rbx, [rsp+3D8h+arg_8]
0x180132893  add     rsp, 3D0h
0x18013289a  pop     rdi
0x18013289b  retn
```
