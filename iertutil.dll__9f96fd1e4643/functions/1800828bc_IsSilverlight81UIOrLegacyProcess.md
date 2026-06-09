# IsSilverlight81UIOrLegacyProcess

- ea: `0x1800828bc`
- end: `0x180082960`
- name: `IsSilverlight81UIOrLegacyProcess`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180082790`

## callees

- `0x1800828bc`
- `0x180083bc2`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800828ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800828ff`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18008290e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18008290e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180082921`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180082935`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180082921`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180082935`

## string_xrefs

- `0x18008292b`: `TASKHOST.EXE`

## pseudocode

```c
bool IsSilverlight81UIOrLegacyProcess()
{
  char v0; // bl
  const WCHAR *FileNameW; // rbx
  WCHAR Filename; // [rsp+20h] [rbp-228h] BYREF
  _BYTE v4[526]; // [rsp+22h] [rbp-226h] BYREF

  Filename = 0;
  v0 = 0;
  memset_0(v4, 0, 0x206u);
  if ( GetModuleFileNameW(0, &Filename, 0x104u) )
  {
    FileNameW = PathFindFileNameW(&Filename);
    return !StrCmpICW(FileNameW, L"AGHOST.EXE") || !StrCmpICW(FileNameW, L"TASKHOST.EXE");
  }
  return v0;
}

```

## disassembly

```asm
0x1800828bc  push    rbx
0x1800828be  sub     rsp, 240h
0x1800828c5  mov     rax, cs:__security_cookie
0x1800828cc  xor     rax, rsp
0x1800828cf  mov     [rsp+248h+var_18], rax
0x1800828d7  xor     eax, eax
0x1800828d9  lea     rcx, [rsp+248h+var_226]; void *
0x1800828de  xor     edx, edx; Val
0x1800828e0  mov     [rsp+248h+Filename], ax
0x1800828e5  mov     r8d, 206h; Size
0x1800828eb  xor     bl, bl
0x1800828ed  call    memset_0
0x1800828f2  mov     r8d, 104h; nSize
0x1800828f8  lea     rdx, [rsp+248h+Filename]; lpFilename
0x1800828fd  xor     ecx, ecx; hModule
0x1800828ff  call    cs:__imp_GetModuleFileNameW
0x180082905  test    eax, eax
0x180082907  jz      short loc_180082945
0x180082909  lea     rcx, [rsp+248h+Filename]; pszPath
0x18008290e  call    cs:__imp_PathFindFileNameW
0x180082914  mov     rcx, rax; pszStr1
0x180082917  lea     rdx, aAghostExe; "AGHOST.EXE"
0x18008291e  mov     rbx, rax
0x180082921  call    cs:__imp_StrCmpICW
0x180082927  test    eax, eax
0x180082929  jz      short loc_180082943
0x18008292b  lea     rdx, aTaskhostExe_0; "TASKHOST.EXE"
0x180082932  mov     rcx, rbx; pszStr1
0x180082935  call    cs:__imp_StrCmpICW
0x18008293b  test    eax, eax
0x18008293d  jz      short loc_180082943
0x18008293f  xor     bl, bl
0x180082941  jmp     short loc_180082945
0x180082943  mov     bl, 1
0x180082945  mov     al, bl
0x180082947  mov     rcx, [rsp+248h+var_18]
0x18008294f  xor     rcx, rsp; StackCookie
0x180082952  call    __security_check_cookie
0x180082957  add     rsp, 240h
0x18008295e  pop     rbx
0x18008295f  retn
```
