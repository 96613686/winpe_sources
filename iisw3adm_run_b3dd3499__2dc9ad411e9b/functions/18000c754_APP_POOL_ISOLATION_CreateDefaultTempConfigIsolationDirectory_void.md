# APP_POOL_ISOLATION::CreateDefaultTempConfigIsolationDirectory(void)

- ea: `0x18000c754`
- end: `0x18000c83b`
- name: `?CreateDefaultTempConfigIsolationDirectory@APP_POOL_ISOLATION@@AEBAJXZ`
- size: `231`
- prototype: `__int64 __fastcall(APP_POOL_ISOLATION *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18000d2a0`

## callees

- `0x18000c754`
- `0x180061060`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000c78a`
- `msvcrt!wcsrchr` at `0x18000c78a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7fa`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000c7d3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000c7e6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000c7d3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000c7e6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c7b6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000c7b6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c81b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c81b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c775`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c775`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000c7a5`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000c7a5`

## pseudocode

```c
__int64 __fastcall APP_POOL_ISOLATION::CreateDefaultTempConfigIsolationDirectory(APP_POOL_ISOLATION *this)
{
  const wchar_t *v2; // rbx
  wchar_t *v3; // rax
  signed int v4; // ebx
  signed int LastError; // eax
  _BYTE v7[32]; // [rsp+20h] [rbp-48h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-28h]

  STRU::STRU((STRU *)v7);
  v2 = (const wchar_t *)*((_QWORD *)this + 16);
  v3 = wcsrchr(v2, 0x5Cu);
  v4 = STRU::Copy((STRU *)v7, *((const unsigned __int16 **)this + 16), v3 - v2);
  if ( v4 >= 0
    && (GetFileAttributesW(lpFileName) == -1 && (GetLastError() != 2 || !CreateDirectoryW(lpFileName, 0))
     || !CreateDirectoryW(*((LPCWSTR *)this + 16), 0)) )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
  }
  STRU::~STRU((STRU *)v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c754  mov     [rsp+arg_8], rbx
0x18000c759  push    rdi
0x18000c75a  sub     rsp, 60h
0x18000c75e  mov     rax, cs:__security_cookie
0x18000c765  xor     rax, rsp
0x18000c768  mov     [rsp+68h+var_10], rax
0x18000c76d  mov     rdi, rcx
0x18000c770  lea     rcx, [rsp+68h+var_48]
0x18000c775  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000c77b  mov     rbx, [rdi+80h]
0x18000c782  mov     edx, 5Ch ; '\'; Ch
0x18000c787  mov     rcx, rbx; Str
0x18000c78a  call    cs:__imp_wcsrchr
0x18000c790  mov     rdx, [rdi+80h]
0x18000c797  lea     rcx, [rsp+68h+var_48]
0x18000c79c  sub     rax, rbx
0x18000c79f  sar     rax, 1
0x18000c7a2  mov     r8d, eax
0x18000c7a5  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000c7ab  mov     ebx, eax
0x18000c7ad  test    eax, eax
0x18000c7af  js      short loc_18000C816
0x18000c7b1  mov     rcx, [rsp+68h+lpFileName]; lpFileName
0x18000c7b6  call    cs:__imp_GetFileAttributesW
0x18000c7bc  cmp     eax, 0FFFFFFFFh
0x18000c7bf  jnz     short loc_18000C7DD
0x18000c7c1  call    cs:__imp_GetLastError
0x18000c7c7  cmp     eax, 2
0x18000c7ca  jnz     short loc_18000C7F0
0x18000c7cc  mov     rcx, [rsp+68h+lpFileName]; lpPathName
0x18000c7d1  xor     edx, edx; lpSecurityAttributes
0x18000c7d3  call    cs:__imp_CreateDirectoryW
0x18000c7d9  test    eax, eax
0x18000c7db  jz      short loc_18000C7F0
0x18000c7dd  mov     rcx, [rdi+80h]; lpPathName
0x18000c7e4  xor     edx, edx; lpSecurityAttributes
0x18000c7e6  call    cs:__imp_CreateDirectoryW
0x18000c7ec  test    eax, eax
0x18000c7ee  jnz     short loc_18000C816
0x18000c7f0  call    cs:__imp_GetLastError
0x18000c7f6  test    eax, eax
0x18000c7f8  jz      short loc_18000C811
0x18000c7fa  call    cs:__imp_GetLastError
0x18000c800  mov     ebx, eax
0x18000c802  test    eax, eax
0x18000c804  jle     short loc_18000C816
0x18000c806  movzx   ebx, ax
0x18000c809  or      ebx, 80070000h
0x18000c80f  jmp     short loc_18000C816
0x18000c811  mov     ebx, 80004005h
0x18000c816  lea     rcx, [rsp+68h+var_48]
0x18000c81b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c821  mov     eax, ebx
0x18000c823  mov     rcx, [rsp+68h+var_10]
0x18000c828  xor     rcx, rsp; StackCookie
0x18000c82b  call    __security_check_cookie
0x18000c830  mov     rbx, [rsp+68h+arg_8]
0x18000c835  add     rsp, 60h
0x18000c839  pop     rdi
0x18000c83a  retn
```
