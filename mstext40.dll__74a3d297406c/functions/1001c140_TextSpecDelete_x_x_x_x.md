# TextSpecDelete(x,x,x,x)

- ea: `0x1001c140`
- end: `0x1001c1d2`
- name: `_TextSpecDelete@16`
- size: `146`
- prototype: `int __stdcall(LPCWCH lpFileName, LPCWCH lpWideCharStr, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x100113f0`
- `0x100133f0`

## callees

- `0x10008f90`
- `0x1000b5f0`
- `0x1000b640`
- `0x1001c140`
- `0x1002b81a`

## import_xrefs

- `KERNEL32!WritePrivateProfileStringA` at `0x1001c195`
- `KERNEL32!WritePrivateProfileStringA` at `0x1001c195`

## pseudocode

```c
int __stdcall TextSpecDelete(LPCWCH lpFileName, LPCWCH lpWideCharStr, int a3, int a4)
{
  int v5; // [esp+4h] [ebp-14Ch] BYREF
  CHAR AppName[68]; // [esp+8h] [ebp-148h] BYREF
  CHAR FileName[256]; // [esp+4Ch] [ebp-104h] BYREF

  ErrWideNToMultiByteCb(lpWideCharStr, 65, AppName, 65);
  ErrWideNToMultiByteCb(lpFileName, 256, FileName, 256);
  WritePrivateProfileStringA(AppName, 0, 0, FileName);
  if ( DOSFileSize(lpFileName, (DWORD *)&v5) == 1 && !v5 )
    DOSFileDelete(lpFileName);
  return 0;
}

```

## disassembly

```asm
0x1001c140  sub     esp, 14Ch
0x1001c146  mov     eax, ___security_cookie
0x1001c14b  xor     eax, esp
0x1001c14d  mov     [esp+14Ch+var_4], eax
0x1001c154  mov     eax, [esp+14Ch+lpWideCharStr]
0x1001c15b  lea     ecx, [esp+14Ch+AppName]
0x1001c15f  push    esi
0x1001c160  mov     esi, [esp+150h+lpFileName]
0x1001c167  push    41h ; 'A'; int
0x1001c169  push    ecx; lpMultiByteStr
0x1001c16a  push    41h ; 'A'; cchWideChar
0x1001c16c  push    eax; lpWideCharStr
0x1001c16d  call    _ErrWideNToMultiByteCb@16; ErrWideNToMultiByteCb(x,x,x,x)
0x1001c172  push    100h; int
0x1001c177  lea     eax, [esp+154h+FileName]
0x1001c17b  push    eax; lpMultiByteStr
0x1001c17c  push    100h; cchWideChar
0x1001c181  push    esi; lpWideCharStr
0x1001c182  call    _ErrWideNToMultiByteCb@16; ErrWideNToMultiByteCb(x,x,x,x)
0x1001c187  lea     eax, [esp+150h+FileName]
0x1001c18b  push    eax; lpFileName
0x1001c18c  push    0; lpString
0x1001c18e  push    0; lpKeyName
0x1001c190  lea     eax, [esp+15Ch+AppName]
0x1001c194  push    eax; lpAppName
0x1001c195  call    ds:__imp__WritePrivateProfileStringA@16; WritePrivateProfileStringA(x,x,x,x)
0x1001c19b  lea     eax, [esp+150h+var_14C]
0x1001c19f  push    eax; int
0x1001c1a0  push    esi; lpFileName
0x1001c1a1  call    _DOSFileSize@8; DOSFileSize(x,x)
0x1001c1a6  cmp     eax, 1
0x1001c1a9  jnz     short loc_1001C1B8
0x1001c1ab  cmp     [esp+150h+var_14C], 0
0x1001c1b0  jnz     short loc_1001C1B8
0x1001c1b2  push    esi
0x1001c1b3  call    _DOSFileDelete@4; DOSFileDelete(x)
0x1001c1b8  mov     ecx, [esp+150h+var_4]
0x1001c1bf  xor     eax, eax
0x1001c1c1  pop     esi
0x1001c1c2  xor     ecx, esp; StackCookie
0x1001c1c4  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001c1c9  add     esp, 14Ch
0x1001c1cf  retn    10h
```
