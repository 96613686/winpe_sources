# IsBrowserProcess(void)

- ea: `0x180024eb0`
- end: `0x18002501b`
- name: `?IsBrowserProcess@@YAHXZ`
- size: `363`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022f94`
- `0x180023d98`
- `0x180024530`

## callees

- `0x180024eb0`
- `0x180083bda`
- `0x180083c10`

## import_xrefs

- `msvcrt!_wcslwr` at `0x180024f21`
- `msvcrt!_wcslwr` at `0x180024f21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180024eef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180024eef`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180024f02`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180024f02`

## pseudocode

```c
__int64 IsBrowserProcess(void)
{
  LPWSTR FileNameW; // rax
  const wchar_t *v1; // rbx
  int v2; // r14d
  int v3; // ebp
  int v4; // esi
  char v5; // di
  int v6; // eax
  __int64 result; // rax
  WCHAR Filename[264]; // [rsp+20h] [rbp-258h] BYREF

  if ( byte_18029A12A )
  {
    LOBYTE(result) = byte_18029A12B;
  }
  else
  {
    if ( !GetModuleFileNameW(0, Filename, 0x104u) )
      goto LABEL_15;
    FileNameW = PathFindFileNameW(Filename);
    v1 = FileNameW;
    if ( !FileNameW || !*FileNameW )
      goto LABEL_15;
    _wcslwr(FileNameW);
    v2 = wcscmp_0(v1, L"iexplore.exe");
    v3 = wcscmp_0(v1, L"ieuser.exe");
    v4 = wcscmp_0(v1, L"ieinstal.exe");
    if ( !wcscmp_0(v1, L"microsoftedge.exe")
      || !wcscmp_0(v1, L"microsoftedgecp.exe")
      || !wcscmp_0(v1, L"microsoftedgebchost.exe")
      || (v5 = 0, !wcscmp_0(v1, L"microsoftedgedevtools.exe")) )
    {
      v5 = 1;
    }
    v6 = wcscmp_0(v1, L"microsoftedgesh.exe");
    if ( !v2 || !v3 || !v4 || v5 || !v6 )
      LOBYTE(result) = 1;
    else
LABEL_15:
      LOBYTE(result) = 0;
    byte_18029A12B = result;
    byte_18029A12A = 1;
  }
  return (unsigned __int8)result;
}

```

## disassembly

```asm
0x180024eb0  push    rbx
0x180024eb2  push    rbp
0x180024eb3  push    rsi
0x180024eb4  push    rdi
0x180024eb5  push    r14
0x180024eb7  push    r15
0x180024eb9  sub     rsp, 248h
0x180024ec0  mov     rax, cs:__security_cookie
0x180024ec7  xor     rax, rsp
0x180024eca  mov     [rsp+278h+var_48], rax
0x180024ed2  xor     r15d, r15d
0x180024ed5  cmp     cs:byte_18029A12A, r15b
0x180024edc  jnz     loc_18002500E
0x180024ee2  mov     r8d, 104h; nSize
0x180024ee8  lea     rdx, [rsp+278h+Filename]; lpFilename
0x180024eed  xor     ecx, ecx; hModule
0x180024eef  call    cs:__imp_GetModuleFileNameW
0x180024ef5  test    eax, eax
0x180024ef7  jz      loc_180024FDB
0x180024efd  lea     rcx, [rsp+278h+Filename]; pszPath
0x180024f02  call    cs:__imp_PathFindFileNameW
0x180024f08  mov     rbx, rax
0x180024f0b  test    rax, rax
0x180024f0e  jz      loc_180024FDB
0x180024f14  cmp     [rax], r15w
0x180024f18  jz      loc_180024FDB
0x180024f1e  mov     rcx, rax; String
0x180024f21  call    cs:__imp__wcslwr
0x180024f27  lea     rdx, aIexploreExe; "iexplore.exe"
0x180024f2e  mov     rcx, rbx; String1
0x180024f31  call    wcscmp_0
0x180024f36  lea     rdx, aIeuserExe; "ieuser.exe"
0x180024f3d  mov     rcx, rbx; String1
0x180024f40  mov     r14d, eax
0x180024f43  call    wcscmp_0
0x180024f48  lea     rdx, aIeinstalExe; "ieinstal.exe"
0x180024f4f  mov     rcx, rbx; String1
0x180024f52  mov     ebp, eax
0x180024f54  call    wcscmp_0
0x180024f59  lea     rdx, aMicrosoftedgeE; "microsoftedge.exe"
0x180024f60  mov     rcx, rbx; String1
0x180024f63  mov     esi, eax
0x180024f65  call    wcscmp_0
0x180024f6a  test    eax, eax
0x180024f6c  jz      loc_180025016
0x180024f72  lea     rdx, aMicrosoftedgec; "microsoftedgecp.exe"
0x180024f79  mov     rcx, rbx; String1
0x180024f7c  call    wcscmp_0
0x180024f81  test    eax, eax
0x180024f83  jz      loc_180025016
0x180024f89  lea     rdx, aMicrosoftedgeb; "microsoftedgebchost.exe"
0x180024f90  mov     rcx, rbx; String1
0x180024f93  call    wcscmp_0
0x180024f98  test    eax, eax
0x180024f9a  jz      short loc_180025016
0x180024f9c  lea     rdx, aMicrosoftedged; "microsoftedgedevtools.exe"
0x180024fa3  mov     rcx, rbx; String1
0x180024fa6  call    wcscmp_0
0x180024fab  mov     dil, r15b
0x180024fae  test    eax, eax
0x180024fb0  jz      short loc_180025016
0x180024fb2  lea     rdx, aMicrosoftedges; "microsoftedgesh.exe"
0x180024fb9  mov     rcx, rbx; String1
0x180024fbc  call    wcscmp_0
0x180024fc1  test    r14d, r14d
0x180024fc4  jnz     short loc_180024FCA
0x180024fc6  mov     al, 1
0x180024fc8  jmp     short loc_180024FDE
0x180024fca  test    ebp, ebp
0x180024fcc  jz      short loc_180024FC6
0x180024fce  test    esi, esi
0x180024fd0  jz      short loc_180024FC6
0x180024fd2  test    dil, dil
0x180024fd5  jnz     short loc_180024FC6
0x180024fd7  test    eax, eax
0x180024fd9  jz      short loc_180024FC6
0x180024fdb  mov     al, r15b
0x180024fde  mov     cs:byte_18029A12B, al
0x180024fe4  mov     cs:byte_18029A12A, 1
0x180024feb  movzx   eax, al
0x180024fee  mov     rcx, [rsp+278h+var_48]
0x180024ff6  xor     rcx, rsp; StackCookie
0x180024ff9  call    __security_check_cookie
0x180024ffe  add     rsp, 248h
0x180025005  pop     r15
0x180025007  pop     r14
0x180025009  pop     rdi
0x18002500a  pop     rsi
0x18002500b  pop     rbp
0x18002500c  pop     rbx
0x18002500d  retn
0x18002500e  mov     al, cs:byte_18029A12B
0x180025014  jmp     short loc_180024FEB
0x180025016  mov     dil, 1
0x180025019  jmp     short loc_180024FB2
```
