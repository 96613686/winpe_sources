# pSpUtilsSetLogPath

- ea: `0x1800202d0`
- end: `0x18002037b`
- name: `pSpUtilsSetLogPath`
- size: `171`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001fd5c`

## callees

- `0x180007188`
- `0x180007f30`
- `0x18000be40`
- `0x1800202d0`
- `0x180021124`
- `0x180021288`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002034b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002034b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020355`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020355`

## pseudocode

```c
_BOOL8 __fastcall pSpUtilsSetLogPath(STRSAFE_LPCWSTR pszSrc)
{
  DWORD LastError; // ebx
  unsigned int v2; // r10d
  wchar_t pszDest[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( pszSrc && StringCchCopyW(pszDest, 0x104u, pszSrc) >= 0 )
  {
    if ( !pSetupConcatenatePaths((__int64)pszDest, L"INF", v2)
      || !(unsigned int)pSpUtilsSetTextLogPath(pszDest)
      || (LastError = 0, !(unsigned int)pSpUtilsLogSetPath(pszDest)) )
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 87;
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x1800202d0  push    rbx
0x1800202d2  sub     rsp, 240h
0x1800202d9  mov     rax, cs:__security_cookie
0x1800202e0  xor     rax, rsp
0x1800202e3  mov     [rsp+248h+var_18], rax
0x1800202eb  mov     ebx, edx
0x1800202ed  test    rcx, rcx
0x1800202f0  jnz     short loc_1800202F9
0x1800202f2  mov     ebx, 57h ; 'W'
0x1800202f7  jmp     short loc_180020353
0x1800202f9  mov     r8, rcx; pszSrc
0x1800202fc  mov     r10d, 104h
0x180020302  mov     edx, r10d; cchDest
0x180020305  lea     rcx, [rsp+248h+pszDest]; pszDest
0x18002030a  call    StringCchCopyW
0x18002030f  test    eax, eax
0x180020311  js      short loc_1800202F2
0x180020313  mov     r8d, r10d
0x180020316  lea     rdx, aInf; "INF"
0x18002031d  lea     rcx, [rsp+248h+pszDest]
0x180020322  call    pSetupConcatenatePaths
0x180020327  test    eax, eax
0x180020329  jz      short loc_18002034B
0x18002032b  mov     edx, ebx
0x18002032d  lea     rcx, [rsp+248h+pszDest]; pszSrc
0x180020332  call    _pSpUtilsSetTextLogPath
0x180020337  test    eax, eax
0x180020339  jz      short loc_18002034B
0x18002033b  lea     rcx, [rsp+248h+pszDest]; pszSrc
0x180020340  xor     ebx, ebx
0x180020342  call    _pSpUtilsLogSetPath
0x180020347  test    eax, eax
0x180020349  jnz     short loc_180020353
0x18002034b  call    cs:__imp_GetLastError
0x180020351  mov     ebx, eax
0x180020353  mov     ecx, ebx; dwErrCode
0x180020355  call    cs:__imp_SetLastError
0x18002035b  xor     eax, eax
0x18002035d  test    ebx, ebx
0x18002035f  setz    al
0x180020362  mov     rcx, [rsp+248h+var_18]
0x18002036a  xor     rcx, rsp; StackCookie
0x18002036d  call    __security_check_cookie
0x180020372  add     rsp, 240h
0x180020379  pop     rbx
0x18002037a  retn
```
