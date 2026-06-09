# IsAppFTPCompatible(void)

- ea: `0x180017154`
- end: `0x18001723b`
- name: `?IsAppFTPCompatible@@YAHXZ`
- size: `231`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018dc0`

## callees

- `0x180002240`
- `0x180017154`

## import_xrefs

- `SHLWAPI!StrCmpIW` at `0x1800171de`
- `SHLWAPI!StrCmpIW` at `0x1800171de`
- `SHLWAPI!PathFindFileNameW` at `0x1800171a6`
- `SHLWAPI!PathFindFileNameW` at `0x1800171a6`
- `SHLWAPI!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x1800171bf`
- `SHLWAPI!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x1800171fe`
- `SHLWAPI!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x1800171bf`
- `SHLWAPI!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x1800171fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180017197`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180017197`

## string_xrefs

- `0x1800171b2`: `Software\Microsoft\Ftp\Compatible`
- `0x1800171f4`: `Software\Microsoft\Ftp\Compatible`

## pseudocode

```c
__int64 IsAppFTPCompatible(void)
{
  const CHAR *FileNameW; // rdi
  int v1; // ebx
  WCHAR Filename[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( !dword_180034A88 )
  {
    dword_180035B38 = 1;
    if ( GetModuleFileNameW(0, Filename, 0x104u) )
    {
      FileNameW = (const CHAR *)PathFindFileNameW(Filename);
      dword_180035B38 = SHRegGetBoolValueFromHKCUHKLM(L"Software\\Microsoft\\Ftp\\Compatible", FileNameW);
      v1 = 0;
      while ( StrCmpIW((PCWSTR)FileNameW, off_180029940[v1]) )
      {
        if ( (unsigned int)++v1 >= 5 )
          goto LABEL_8;
      }
      dword_180035B38 = SHRegGetBoolValueFromHKCUHKLM(L"Software\\Microsoft\\Ftp\\Compatible", FileNameW);
    }
LABEL_8:
    dword_180034A88 = 1;
  }
  return (unsigned int)dword_180035B38;
}

```

## disassembly

```asm
0x180017154  mov     [rsp+arg_0], rbx
0x180017159  push    rdi
0x18001715a  sub     rsp, 240h
0x180017161  mov     rax, cs:__security_cookie
0x180017168  xor     rax, rsp
0x18001716b  mov     [rsp+248h+var_18], rax
0x180017173  cmp     cs:dword_180034A88, 0
0x18001717a  jnz     loc_180017214
0x180017180  mov     r8d, 104h; nSize
0x180017186  mov     cs:dword_180035B38, 1
0x180017190  lea     rdx, [rsp+248h+Filename]; lpFilename
0x180017195  xor     ecx, ecx; hModule
0x180017197  call    cs:__imp_GetModuleFileNameW
0x18001719d  test    eax, eax
0x18001719f  jz      short loc_18001720A
0x1800171a1  lea     rcx, [rsp+248h+Filename]; pszPath
0x1800171a6  call    cs:__imp_PathFindFileNameW
0x1800171ac  mov     r8d, 1
0x1800171b2  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Ftp\\Compatible"
0x1800171b9  mov     rdx, rax; pszPath
0x1800171bc  mov     rdi, rax
0x1800171bf  call    cs:__imp_SHRegGetBoolValueFromHKCUHKLM
0x1800171c5  mov     cs:dword_180035B38, eax
0x1800171cb  xor     ebx, ebx
0x1800171cd  lea     rax, off_180029940; "aol.exe"
0x1800171d4  movsxd  rdx, ebx
0x1800171d7  mov     rcx, rdi; psz1
0x1800171da  mov     rdx, [rax+rdx*8]; psz2
0x1800171de  call    cs:__imp_StrCmpIW
0x1800171e4  test    eax, eax
0x1800171e6  jz      short loc_1800171F1
0x1800171e8  inc     ebx
0x1800171ea  cmp     ebx, 5
0x1800171ed  jb      short loc_1800171CD
0x1800171ef  jmp     short loc_18001720A
0x1800171f1  xor     r8d, r8d
0x1800171f4  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Ftp\\Compatible"
0x1800171fb  mov     rdx, rdi; pszPath
0x1800171fe  call    cs:__imp_SHRegGetBoolValueFromHKCUHKLM
0x180017204  mov     cs:dword_180035B38, eax
0x18001720a  mov     cs:dword_180034A88, 1
0x180017214  mov     eax, cs:dword_180035B38
0x18001721a  mov     rcx, [rsp+248h+var_18]
0x180017222  xor     rcx, rsp; StackCookie
0x180017225  call    __security_check_cookie
0x18001722a  mov     rbx, [rsp+248h+arg_0]
0x180017232  add     rsp, 240h
0x180017239  pop     rdi
0x18001723a  retn
```
