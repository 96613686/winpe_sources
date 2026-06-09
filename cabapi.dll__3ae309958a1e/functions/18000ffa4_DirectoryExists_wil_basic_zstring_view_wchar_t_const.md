# DirectoryExists(wil::basic_zstring_view<wchar_t> const &)

- ea: `0x18000ffa4`
- end: `0x18001000b`
- name: `?DirectoryExists@@YA_NAEBV?$basic_zstring_view@_W@wil@@@Z`
- size: `103`
- prototype: `bool __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180010124`

## callees

- `0x180001540`
- `0x180003648`
- `0x18000ffa4`
- `0x1800104d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000ffd7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000ffd7`

## pseudocode

```c
bool __fastcall DirectoryExists(__int64 a1)
{
  const WCHAR *v1; // rcx
  DWORD FileAttributesW; // eax
  bool v3; // bl
  LPCWSTR lpFileName[4]; // [rsp+20h] [rbp-38h] BYREF

  GetCanonicalUNCPath(lpFileName, a1);
  v1 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v1 = lpFileName[0];
  FileAttributesW = GetFileAttributesW(v1);
  v3 = FileAttributesW != -1 && (FileAttributesW & 0x10) != 0;
  std::wstring::~wstring((char **)lpFileName);
  return v3;
}

```

## disassembly

```asm
0x18000ffa4  push    rbx
0x18000ffa6  sub     rsp, 50h
0x18000ffaa  mov     rax, cs:__security_cookie
0x18000ffb1  xor     rax, rsp
0x18000ffb4  mov     [rsp+58h+var_18], rax
0x18000ffb9  mov     rdx, rcx
0x18000ffbc  lea     rcx, [rsp+58h+lpFileName]
0x18000ffc1  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x18000ffc6  cmp     [rsp+58h+var_20], 7
0x18000ffcc  lea     rcx, [rsp+58h+lpFileName]
0x18000ffd1  cmova   rcx, [rsp+58h+lpFileName]; lpFileName
0x18000ffd7  call    cs:__imp_GetFileAttributesW
0x18000ffdd  cmp     eax, 0FFFFFFFFh
0x18000ffe0  jz      short loc_18000FFEA
0x18000ffe2  test    al, 10h
0x18000ffe4  jz      short loc_18000FFEA
0x18000ffe6  mov     bl, 1
0x18000ffe8  jmp     short loc_18000FFEC
0x18000ffea  xor     bl, bl
0x18000ffec  lea     rcx, [rsp+58h+lpFileName]
0x18000fff1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000fff6  mov     al, bl
0x18000fff8  mov     rcx, [rsp+58h+var_18]
0x18000fffd  xor     rcx, rsp; StackCookie
0x180010000  call    __security_check_cookie
0x180010005  add     rsp, 50h
0x180010009  pop     rbx
0x18001000a  retn
```
