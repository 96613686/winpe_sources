# HHGetUserDataPath(char *,unsigned __int64)

- ea: `0x180067c20`
- end: `0x180067e51`
- name: `?HHGetUserDataPath@@YAHPEAD_K@Z`
- size: `561`
- prototype: `__int64 __fastcall(LPBYTE lpData, unsigned __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180060980`
- `0x180067e60`

## callees

- `0x18004e6a8`
- `0x18004eea0`
- `0x18004f514`
- `0x180065d30`
- `0x180067c20`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `KERNEL32!CreateDirectoryA` at `0x180067ceb`
- `KERNEL32!CreateDirectoryA` at `0x180067d89`
- `KERNEL32!CreateDirectoryA` at `0x180067dbd`
- `KERNEL32!CreateDirectoryA` at `0x180067ded`
- `KERNEL32!CreateDirectoryA` at `0x180067e1d`
- `KERNEL32!CreateDirectoryA` at `0x180067ceb`
- `KERNEL32!CreateDirectoryA` at `0x180067d89`
- `KERNEL32!CreateDirectoryA` at `0x180067dbd`
- `KERNEL32!CreateDirectoryA` at `0x180067ded`
- `KERNEL32!CreateDirectoryA` at `0x180067e1d`
- `ADVAPI32!GetUserNameA` at `0x180067d14`
- `ADVAPI32!GetUserNameA` at `0x180067d14`
- `SHELL32!SHGetSpecialFolderPathW` at `0x180067c82`
- `SHELL32!SHGetSpecialFolderPathW` at `0x180067c82`

## pseudocode

```c
__int64 __fastcall HHGetUserDataPath(LPBYTE lpData, unsigned __int64 a2)
{
  __int64 v4; // rdi
  __int64 v5; // rax
  const char *v6; // rdx
  CHAR *v7; // rcx
  CHAR *v8; // rax
  DWORD pcbBuffer; // [rsp+20h] [rbp-358h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+28h] [rbp-350h] BYREF
  CHAR Buffer[272]; // [rsp+40h] [rbp-338h] BYREF
  WCHAR pszPath[264]; // [rsp+150h] [rbp-228h] BYREF

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  memset_0(pszPath, 0, 0x208u);
  if ( !SHGetSpecialFolderPathW(0, pszPath, 26, 0)
    || !pszPath[0]
    || !ConvertPathToAnsiWithNoBestFitMatching(pszPath, (LPSTR)lpData, a2)
    || !*lpData )
  {
    HHGetWindowsDirectory(lpData, a2, 0);
    CatPath((char *)lpData, "Profiles", a2);
    if ( !(unsigned int)IsDirectory((const char *)lpData) && !CreateDirectoryA((LPCSTR)lpData, &SecurityAttributes) )
      return 0;
    v4 = 260;
    pcbBuffer = 260;
    if ( !GetUserNameA(Buffer, &pcbBuffer) )
    {
      v5 = 2147483646;
      v6 = "Default User";
      v7 = Buffer;
      do
      {
        if ( !v5 )
          break;
        if ( !*v6 )
          break;
        *v7++ = *v6++;
        --v5;
        --v4;
      }
      while ( v4 );
      v8 = v7 - 1;
      if ( v4 )
        v8 = v7;
      *v8 = 0;
    }
    CatPath((char *)lpData, Buffer, a2);
    if ( !(unsigned int)IsDirectory((const char *)lpData) && !CreateDirectoryA((LPCSTR)lpData, &SecurityAttributes) )
      return 0;
    CatPath((char *)lpData, "Application Data", a2);
    if ( !(unsigned int)IsDirectory((const char *)lpData) && !CreateDirectoryA((LPCSTR)lpData, &SecurityAttributes) )
      return 0;
  }
  if ( ((CatPath((char *)lpData, "Microsoft", a2), (unsigned int)IsDirectory((const char *)lpData))
     || CreateDirectoryA((LPCSTR)lpData, &SecurityAttributes))
    && ((CatPath((char *)lpData, "HTML Help", a2), (unsigned int)IsDirectory((const char *)lpData))
     || CreateDirectoryA((LPCSTR)lpData, &SecurityAttributes)) )
  {
    return 1;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180067c20  mov     [rsp+arg_18], rbx
0x180067c25  push    rsi
0x180067c26  sub     rsp, 370h
0x180067c2d  mov     rax, cs:__security_cookie
0x180067c34  xor     rax, rsp
0x180067c37  mov     [rsp+378h+var_18], rax
0x180067c3f  xor     eax, eax
0x180067c41  mov     qword ptr [rsp+378h+SecurityAttributes.nLength], 18h
0x180067c4a  mov     rsi, rdx
0x180067c4d  mov     qword ptr [rsp+378h+SecurityAttributes.bInheritHandle], rax
0x180067c52  mov     rbx, rcx
0x180067c55  mov     [rsp+378h+SecurityAttributes.lpSecurityDescriptor], rax
0x180067c5a  xor     edx, edx; Val
0x180067c5c  lea     rcx, [rsp+378h+pszPath]; void *
0x180067c64  mov     r8d, 208h; Size
0x180067c6a  call    memset_0
0x180067c6f  xor     r9d, r9d; fCreate
0x180067c72  lea     rdx, [rsp+378h+pszPath]; pszPath
0x180067c7a  mov     r8d, 1Ah; csidl
0x180067c80  xor     ecx, ecx; hwnd
0x180067c82  call    cs:__imp_SHGetSpecialFolderPathW
0x180067c88  test    eax, eax
0x180067c8a  jz      short loc_180067CB7
0x180067c8c  cmp     [rsp+378h+pszPath], 0
0x180067c95  jz      short loc_180067CB7
0x180067c97  mov     r8d, esi; unsigned int
0x180067c9a  lea     rcx, [rsp+378h+pszPath]; lpszLongPath
0x180067ca2  mov     rdx, rbx; lpMultiByteStr
0x180067ca5  call    ?ConvertPathToAnsiWithNoBestFitMatching@@YA_NPEBGPEADK@Z; ConvertPathToAnsiWithNoBestFitMatching(ushort const *,char *,ulong)
0x180067caa  test    al, al
0x180067cac  jz      short loc_180067CB7
0x180067cae  cmp     byte ptr [rbx], 0
0x180067cb1  jnz     loc_180067DC7
0x180067cb7  xor     r8d, r8d; unsigned int
0x180067cba  mov     rdx, rsi; unsigned __int64
0x180067cbd  mov     rcx, rbx; lpData
0x180067cc0  call    ?HHGetWindowsDirectory@@YAKPEAD_KI@Z; HHGetWindowsDirectory(char *,unsigned __int64,uint)
0x180067cc5  mov     r8, rsi; unsigned __int64
0x180067cc8  lea     rdx, aProfiles; "Profiles"
0x180067ccf  mov     rcx, rbx; char *
0x180067cd2  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180067cd7  mov     rcx, rbx; char *
0x180067cda  call    ?IsDirectory@@YAHPEBD@Z; IsDirectory(char const *)
0x180067cdf  test    eax, eax
0x180067ce1  jnz     short loc_180067CF9
0x180067ce3  lea     rdx, [rsp+378h+SecurityAttributes]; lpSecurityAttributes
0x180067ce8  mov     rcx, rbx; lpPathName
0x180067ceb  call    cs:__imp_CreateDirectoryA
0x180067cf1  test    eax, eax
0x180067cf3  jz      loc_180067E27
0x180067cf9  mov     [rsp+378h+arg_10], rdi
0x180067d01  lea     rdx, [rsp+378h+pcbBuffer]; pcbBuffer
0x180067d06  mov     edi, 104h
0x180067d0b  lea     rcx, [rsp+378h+Buffer]; lpBuffer
0x180067d10  mov     [rsp+378h+pcbBuffer], edi
0x180067d14  call    cs:__imp_GetUserNameA
0x180067d1a  test    eax, eax
0x180067d1c  jnz     short loc_180067D5D
0x180067d1e  mov     eax, 7FFFFFFEh
0x180067d23  lea     rdx, aDefaultUser; "Default User"
0x180067d2a  lea     rcx, [rsp+378h+Buffer]
0x180067d2f  test    rax, rax
0x180067d32  jz      short loc_180067D4F
0x180067d34  movzx   r8d, byte ptr [rdx]
0x180067d38  test    r8b, r8b
0x180067d3b  jz      short loc_180067D4F
0x180067d3d  mov     [rcx], r8b
0x180067d40  inc     rdx
0x180067d43  inc     rcx
0x180067d46  dec     rax
0x180067d49  sub     rdi, 1
0x180067d4d  jnz     short loc_180067D2F
0x180067d4f  test    rdi, rdi
0x180067d52  lea     rax, [rcx-1]
0x180067d56  cmovnz  rax, rcx
0x180067d5a  mov     byte ptr [rax], 0
0x180067d5d  mov     r8, rsi; unsigned __int64
0x180067d60  lea     rdx, [rsp+378h+Buffer]; char *
0x180067d65  mov     rcx, rbx; char *
0x180067d68  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180067d6d  mov     rcx, rbx; char *
0x180067d70  call    ?IsDirectory@@YAHPEBD@Z; IsDirectory(char const *)
0x180067d75  mov     rdi, [rsp+378h+arg_10]
0x180067d7d  test    eax, eax
0x180067d7f  jnz     short loc_180067D97
0x180067d81  lea     rdx, [rsp+378h+SecurityAttributes]; lpSecurityAttributes
0x180067d86  mov     rcx, rbx; lpPathName
0x180067d89  call    cs:__imp_CreateDirectoryA
0x180067d8f  test    eax, eax
0x180067d91  jz      loc_180067E27
0x180067d97  mov     r8, rsi; unsigned __int64
0x180067d9a  lea     rdx, aApplicationDat; "Application Data"
0x180067da1  mov     rcx, rbx; char *
0x180067da4  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180067da9  mov     rcx, rbx; char *
0x180067dac  call    ?IsDirectory@@YAHPEBD@Z; IsDirectory(char const *)
0x180067db1  test    eax, eax
0x180067db3  jnz     short loc_180067DC7
0x180067db5  lea     rdx, [rsp+378h+SecurityAttributes]; lpSecurityAttributes
0x180067dba  mov     rcx, rbx; lpPathName
0x180067dbd  call    cs:__imp_CreateDirectoryA
0x180067dc3  test    eax, eax
0x180067dc5  jz      short loc_180067E27
0x180067dc7  mov     r8, rsi; unsigned __int64
0x180067dca  lea     rdx, aMicrosoft_0; "Microsoft"
0x180067dd1  mov     rcx, rbx; char *
0x180067dd4  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180067dd9  mov     rcx, rbx; char *
0x180067ddc  call    ?IsDirectory@@YAHPEBD@Z; IsDirectory(char const *)
0x180067de1  test    eax, eax
0x180067de3  jnz     short loc_180067DF7
0x180067de5  lea     rdx, [rsp+378h+SecurityAttributes]; lpSecurityAttributes
0x180067dea  mov     rcx, rbx; lpPathName
0x180067ded  call    cs:__imp_CreateDirectoryA
0x180067df3  test    eax, eax
0x180067df5  jz      short loc_180067E27
0x180067df7  mov     r8, rsi; unsigned __int64
0x180067dfa  lea     rdx, aHtmlHelp_1; "HTML Help"
0x180067e01  mov     rcx, rbx; char *
0x180067e04  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180067e09  mov     rcx, rbx; char *
0x180067e0c  call    ?IsDirectory@@YAHPEBD@Z; IsDirectory(char const *)
0x180067e11  test    eax, eax
0x180067e13  jnz     short loc_180067E2B
0x180067e15  lea     rdx, [rsp+378h+SecurityAttributes]; lpSecurityAttributes
0x180067e1a  mov     rcx, rbx; lpPathName
0x180067e1d  call    cs:__imp_CreateDirectoryA
0x180067e23  test    eax, eax
0x180067e25  jnz     short loc_180067E2B
0x180067e27  xor     eax, eax
0x180067e29  jmp     short loc_180067E30
0x180067e2b  mov     eax, 1
0x180067e30  mov     rcx, [rsp+378h+var_18]
0x180067e38  xor     rcx, rsp; StackCookie
0x180067e3b  call    __security_check_cookie
0x180067e40  mov     rbx, [rsp+378h+arg_18]
0x180067e48  add     rsp, 370h
0x180067e4f  pop     rsi
0x180067e50  retn
```
