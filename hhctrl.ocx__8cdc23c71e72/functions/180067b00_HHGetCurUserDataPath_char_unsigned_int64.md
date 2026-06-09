# HHGetCurUserDataPath(char *,unsigned __int64)

- ea: `0x180067b00`
- end: `0x180067c1a`
- name: `?HHGetCurUserDataPath@@YAJPEAD_K@Z`
- size: `282`
- prototype: `__int64 __fastcall(LPSTR lpMultiByteStr, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800629bc`
- `0x180062aa4`

## callees

- `0x18004e6a8`
- `0x18004f514`
- `0x180065d30`
- `0x180067b00`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `KERNEL32!CreateDirectoryA` at `0x180067bbb`
- `KERNEL32!CreateDirectoryA` at `0x180067bee`
- `KERNEL32!CreateDirectoryA` at `0x180067bbb`
- `KERNEL32!CreateDirectoryA` at `0x180067bee`
- `SHELL32!SHGetFolderPathW` at `0x180067b5c`
- `SHELL32!SHGetFolderPathW` at `0x180067b5c`

## pseudocode

```c
HRESULT __fastcall HHGetCurUserDataPath(LPSTR lpMultiByteStr)
{
  HRESULT result; // eax
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+30h] [rbp-248h] BYREF
  WCHAR szLongPath[264]; // [rsp+50h] [rbp-228h] BYREF

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  memset_0(szLongPath, 0, 0x208u);
  result = SHGetFolderPathW(0, 32794, 0, 0, szLongPath);
  if ( result >= 0 )
  {
    if ( szLongPath[0]
      && ConvertPathToAnsiWithNoBestFitMatching(szLongPath, lpMultiByteStr, 0x104u)
      && *lpMultiByteStr
      && ((CatPath(lpMultiByteStr, "Microsoft", 0x104u), (unsigned int)IsDirectory(lpMultiByteStr))
       || CreateDirectoryA(lpMultiByteStr, &SecurityAttributes))
      && ((CatPath(lpMultiByteStr, "HTML Help", 0x104u), (unsigned int)IsDirectory(lpMultiByteStr))
       || CreateDirectoryA(lpMultiByteStr, &SecurityAttributes)) )
    {
      return 0;
    }
    else
    {
      return -2147287037;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180067b00  push    rbx
0x180067b02  sub     rsp, 270h
0x180067b09  mov     rax, cs:__security_cookie
0x180067b10  xor     rax, rsp
0x180067b13  mov     [rsp+278h+var_18], rax
0x180067b1b  xor     eax, eax
0x180067b1d  mov     qword ptr [rsp+278h+SecurityAttributes.nLength], 18h
0x180067b26  mov     rbx, rcx
0x180067b29  mov     qword ptr [rsp+278h+SecurityAttributes.bInheritHandle], rax
0x180067b2e  lea     rcx, [rsp+278h+szLongPath]; void *
0x180067b33  mov     [rsp+278h+SecurityAttributes.lpSecurityDescriptor], rax
0x180067b38  xor     edx, edx; Val
0x180067b3a  mov     r8d, 208h; Size
0x180067b40  call    memset_0
0x180067b45  lea     rax, [rsp+278h+szLongPath]
0x180067b4a  xor     r9d, r9d; dwFlags
0x180067b4d  xor     r8d, r8d; hToken
0x180067b50  mov     [rsp+278h+pszPath], rax; pszPath
0x180067b55  mov     edx, 801Ah; csidl
0x180067b5a  xor     ecx, ecx; hwnd
0x180067b5c  call    cs:__imp_SHGetFolderPathW
0x180067b62  test    eax, eax
0x180067b64  js      loc_180067C01
0x180067b6a  cmp     [rsp+278h+szLongPath], 0
0x180067b70  jz      loc_180067BFC
0x180067b76  mov     r8d, 104h; unsigned int
0x180067b7c  lea     rcx, [rsp+278h+szLongPath]; lpszLongPath
0x180067b81  mov     rdx, rbx; lpMultiByteStr
0x180067b84  call    ?ConvertPathToAnsiWithNoBestFitMatching@@YA_NPEBGPEADK@Z; ConvertPathToAnsiWithNoBestFitMatching(ushort const *,char *,ulong)
0x180067b89  test    al, al
0x180067b8b  jz      short loc_180067BFC
0x180067b8d  cmp     byte ptr [rbx], 0
0x180067b90  jz      short loc_180067BFC
0x180067b92  mov     r8d, 104h; unsigned __int64
0x180067b98  lea     rdx, aMicrosoft_0; "Microsoft"
0x180067b9f  mov     rcx, rbx; char *
0x180067ba2  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180067ba7  mov     rcx, rbx; char *
0x180067baa  call    ?IsDirectory@@YAHPEBD@Z; IsDirectory(char const *)
0x180067baf  test    eax, eax
0x180067bb1  jnz     short loc_180067BC5
0x180067bb3  lea     rdx, [rsp+278h+SecurityAttributes]; lpSecurityAttributes
0x180067bb8  mov     rcx, rbx; lpPathName
0x180067bbb  call    cs:__imp_CreateDirectoryA
0x180067bc1  test    eax, eax
0x180067bc3  jz      short loc_180067BFC
0x180067bc5  mov     r8d, 104h; unsigned __int64
0x180067bcb  lea     rdx, aHtmlHelp_1; "HTML Help"
0x180067bd2  mov     rcx, rbx; char *
0x180067bd5  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180067bda  mov     rcx, rbx; char *
0x180067bdd  call    ?IsDirectory@@YAHPEBD@Z; IsDirectory(char const *)
0x180067be2  test    eax, eax
0x180067be4  jnz     short loc_180067BF8
0x180067be6  lea     rdx, [rsp+278h+SecurityAttributes]; lpSecurityAttributes
0x180067beb  mov     rcx, rbx; lpPathName
0x180067bee  call    cs:__imp_CreateDirectoryA
0x180067bf4  test    eax, eax
0x180067bf6  jz      short loc_180067BFC
0x180067bf8  xor     eax, eax
0x180067bfa  jmp     short loc_180067C01
0x180067bfc  mov     eax, 80030003h
0x180067c01  mov     rcx, [rsp+278h+var_18]
0x180067c09  xor     rcx, rsp; StackCookie
0x180067c0c  call    __security_check_cookie
0x180067c11  add     rsp, 270h
0x180067c18  pop     rbx
0x180067c19  retn
```
