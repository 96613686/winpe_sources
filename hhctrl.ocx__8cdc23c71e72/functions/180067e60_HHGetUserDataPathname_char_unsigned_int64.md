# HHGetUserDataPathname(char *,unsigned __int64)

- ea: `0x180067e60`
- end: `0x180067fa6`
- name: `?HHGetUserDataPathname@@YAJPEAD_K@Z`
- size: `326`
- prototype: `__int64 __fastcall(char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800591ac`

## callees

- `0x1800029b8`
- `0x18004e6a8`
- `0x18004eea0`
- `0x18004f538`
- `0x180067c20`
- `0x180067e60`
- `0x180075c90`

## import_xrefs

- `KERNEL32!GetFileAttributesA` at `0x180067f59`
- `KERNEL32!GetFileAttributesA` at `0x180067f59`
- `KERNEL32!CopyFileA` at `0x180067f76`
- `KERNEL32!CopyFileA` at `0x180067f76`
- `USER32!CharPrevA` at `0x180067f15`
- `USER32!CharPrevA` at `0x180067f15`

## pseudocode

```c
__int64 __fastcall HHGetUserDataPathname(BYTE *a1)
{
  signed int v2; // ebx
  signed int v3; // eax
  __int64 v4; // rax
  CHAR v5; // cl
  DWORD FileAttributesA; // eax
  CHAR szStart[272]; // [rsp+20h] [rbp-128h] BYREF

  if ( (unsigned int)HHGetUserDataPath(a1, 0x824u) != 1 )
    return 2147680258LL;
  v2 = 0;
  CatPath((char *)a1, "hh.dat", 0x824u);
  if ( !(unsigned int)IsFile((const char *)a1) )
  {
    v3 = HHGetWindowsDirectory((LPBYTE)szStart, 260, 1);
    v2 = v3;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    if ( v2 >= 0 )
    {
      if ( szStart[0] )
      {
        v4 = -1;
        do
          ++v4;
        while ( szStart[v4] );
        v5 = *CharPrevA(szStart, &szStart[v4]);
        if ( v5 != 92 && v5 != 47 )
          StringCchCatA(szStart, 0x104u, "\\");
      }
      StringCchCatA(szStart, 0x104u, "hh.dat");
      FileAttributesA = GetFileAttributesA(szStart);
      if ( FileAttributesA != -1 && (FileAttributesA & 0x10) == 0 )
        CopyFileA(szStart, (LPCSTR)a1, 1);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180067e60  push    rdi
0x180067e62  sub     rsp, 140h
0x180067e69  mov     rax, cs:__security_cookie
0x180067e70  xor     rax, rsp
0x180067e73  mov     [rsp+148h+var_18], rax
0x180067e7b  mov     edx, 824h; unsigned __int64
0x180067e80  mov     rdi, rcx
0x180067e83  call    ?HHGetUserDataPath@@YAHPEAD_K@Z; HHGetUserDataPath(char *,unsigned __int64)
0x180067e88  cmp     eax, 1
0x180067e8b  jnz     loc_180067F9F
0x180067e91  mov     [rsp+148h+arg_8], rbx
0x180067e99  lea     rdx, aHhDat; "hh.dat"
0x180067ea0  mov     r8d, 824h; unsigned __int64
0x180067ea6  mov     rcx, rdi; char *
0x180067ea9  xor     ebx, ebx
0x180067eab  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180067eb0  mov     rcx, rdi; char *
0x180067eb3  call    ?IsFile@@YAHPEBD@Z; IsFile(char const *)
0x180067eb8  test    eax, eax
0x180067eba  jnz     loc_180067F7C
0x180067ec0  mov     edx, 104h; unsigned __int64
0x180067ec5  lea     rcx, [rsp+148h+szStart]; lpData
0x180067eca  mov     r8d, 1; unsigned int
0x180067ed0  call    ?HHGetWindowsDirectory@@YAKPEAD_KI@Z; HHGetWindowsDirectory(char *,unsigned __int64,uint)
0x180067ed5  mov     ebx, eax
0x180067ed7  test    eax, eax
0x180067ed9  jle     short loc_180067EE4
0x180067edb  movzx   ebx, ax
0x180067ede  or      ebx, 80070000h
0x180067ee4  test    ebx, ebx
0x180067ee6  js      loc_180067F7C
0x180067eec  cmp     [rsp+148h+szStart], 0
0x180067ef1  jz      short loc_180067F3E
0x180067ef3  lea     rcx, [rsp+148h+szStart]
0x180067ef8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180067eff  inc     rax
0x180067f02  cmp     byte ptr [rcx+rax], 0
0x180067f06  jnz     short loc_180067EFF
0x180067f08  lea     rdx, [rsp+148h+szStart]
0x180067f0d  add     rdx, rax; lpszCurrent
0x180067f10  lea     rcx, [rsp+148h+szStart]; lpszStart
0x180067f15  call    cs:__imp_CharPrevA
0x180067f1b  movzx   ecx, byte ptr [rax]
0x180067f1e  cmp     cl, 5Ch ; '\'
0x180067f21  jz      short loc_180067F3E
0x180067f23  cmp     cl, 2Fh ; '/'
0x180067f26  jz      short loc_180067F3E
0x180067f28  lea     r8, asc_18007E4A8; "\\"
0x180067f2f  mov     edx, 104h; unsigned __int64
0x180067f34  lea     rcx, [rsp+148h+szStart]; char *
0x180067f39  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180067f3e  lea     r8, aHhDat; "hh.dat"
0x180067f45  mov     edx, 104h; unsigned __int64
0x180067f4a  lea     rcx, [rsp+148h+szStart]; char *
0x180067f4f  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180067f54  lea     rcx, [rsp+148h+szStart]; lpFileName
0x180067f59  call    cs:__imp_GetFileAttributesA
0x180067f5f  cmp     eax, 0FFFFFFFFh
0x180067f62  jz      short loc_180067F7C
0x180067f64  test    al, 10h
0x180067f66  jnz     short loc_180067F7C
0x180067f68  mov     r8d, 1; bFailIfExists
0x180067f6e  lea     rcx, [rsp+148h+szStart]; lpExistingFileName
0x180067f73  mov     rdx, rdi; lpNewFileName
0x180067f76  call    cs:__imp_CopyFileA
0x180067f7c  mov     eax, ebx
0x180067f7e  mov     rbx, [rsp+148h+arg_8]
0x180067f86  mov     rcx, [rsp+148h+var_18]
0x180067f8e  xor     rcx, rsp; StackCookie
0x180067f91  call    __security_check_cookie
0x180067f96  add     rsp, 140h
0x180067f9d  pop     rdi
0x180067f9e  retn
0x180067f9f  mov     eax, 80030002h
0x180067fa4  jmp     short loc_180067F86
```
