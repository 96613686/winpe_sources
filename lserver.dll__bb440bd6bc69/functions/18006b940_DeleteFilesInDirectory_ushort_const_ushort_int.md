# DeleteFilesInDirectory(ushort const *,ushort *,int)

- ea: `0x18006b940`
- end: `0x18006bb16`
- name: `?DeleteFilesInDirectory@@YAKPEBGPEAGH@Z`
- size: `470`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18006c1f4`
- `0x18006c2d8`

## callees

- `0x180005665`
- `0x18000d028`
- `0x18000d060`
- `0x18006b940`
- `0x1800a0fb0`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18006ba93`
- `KERNEL32!DeleteFileW` at `0x18006ba93`
- `KERNEL32!FindNextFileW` at `0x18006baac`
- `KERNEL32!FindNextFileW` at `0x18006baac`
- `KERNEL32!FindFirstFileW` at `0x18006ba24`
- `KERNEL32!FindFirstFileW` at `0x18006ba24`
- `KERNEL32!FindClose` at `0x18006bace`
- `KERNEL32!FindClose` at `0x18006bace`
- `KERNEL32!GetLastError` at `0x18006ba39`
- `KERNEL32!GetLastError` at `0x18006babd`
- `KERNEL32!GetLastError` at `0x18006ba39`
- `KERNEL32!GetLastError` at `0x18006babd`

## pseudocode

```c
DWORD __fastcall DeleteFilesInDirectory(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned int v4; // r11d
  int v5; // r11d
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r12
  HANDLE FirstFileW; // r14
  __int64 v10; // rax
  DWORD LastError; // ebx
  unsigned __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 )
    return 13;
  if ( !a2 )
    return 13;
  v12 = 0;
  v13 = 0;
  if ( (int)StringCchLengthW(a1, 0x104u, &v12) < 0 )
    return 13;
  if ( (int)StringCchLengthW(a2, v4, &v13) < 0 )
    return 13;
  v6 = v12;
  v7 = (unsigned int)(v5 + 1);
  if ( v13 + v12 + 2 > v7 )
    return 13;
  StringCchPrintfW(FileName, (unsigned int)v7, L"%s\\%s", a1, a2);
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    return GetLastError();
  do
  {
    v10 = -1;
    do
      ++v10;
    while ( FindFileData.cFileName[v10] );
    if ( v6 + v10 + 2 <= v7 )
    {
      StringCchPrintfW(FileName, v7, L"%s\\%s", a1, FindFileData.cFileName);
      if ( !DeleteFileW(FileName) )
        break;
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  LastError = GetLastError();
  FindClose(FirstFileW);
  if ( LastError == 18 )
    return 0;
  return LastError;
}

```

## disassembly

```asm
0x18006b940  mov     [rsp-8+arg_10], rbx
0x18006b945  mov     [rsp-8+arg_18], rsi
0x18006b94a  push    rbp
0x18006b94b  push    rdi
0x18006b94c  push    r12
0x18006b94e  push    r14
0x18006b950  push    r15
0x18006b952  lea     rbp, [rsp-3B0h]
0x18006b95a  sub     rsp, 4B0h
0x18006b961  mov     rax, cs:__security_cookie
0x18006b968  xor     rax, rsp
0x18006b96b  mov     [rbp+3D0h+var_30], rax
0x18006b972  mov     rbx, rdx
0x18006b975  mov     rdi, rcx
0x18006b978  xor     edx, edx; Val
0x18006b97a  lea     rcx, [rsp+4D0h+FindFileData]; void *
0x18006b97f  mov     r8d, 250h; Size
0x18006b985  call    memset_0
0x18006b98a  xor     r15d, r15d
0x18006b98d  test    rdi, rdi
0x18006b990  jz      loc_18006BAE5
0x18006b996  test    rbx, rbx
0x18006b999  jz      loc_18006BAE5
0x18006b99f  mov     r11d, 104h
0x18006b9a5  mov     [rsp+4D0h+var_4A0], r15
0x18006b9aa  mov     edx, r11d; unsigned __int64
0x18006b9ad  mov     [rsp+4D0h+var_498], r15
0x18006b9b2  lea     r8, [rsp+4D0h+var_4A0]; unsigned __int64 *
0x18006b9b7  mov     rcx, rdi; unsigned __int16 *
0x18006b9ba  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006b9bf  test    eax, eax
0x18006b9c1  js      loc_18006BAE5
0x18006b9c7  lea     r8, [rsp+4D0h+var_498]; unsigned __int64 *
0x18006b9cc  mov     edx, r11d; unsigned __int64
0x18006b9cf  mov     rcx, rbx; unsigned __int16 *
0x18006b9d2  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006b9d7  test    eax, eax
0x18006b9d9  js      loc_18006BAE5
0x18006b9df  mov     rsi, [rsp+4D0h+var_4A0]
0x18006b9e4  lea     r12d, [r11+1]
0x18006b9e8  lea     rcx, [rsi+2]
0x18006b9ec  add     rcx, [rsp+4D0h+var_498]
0x18006b9f1  cmp     rcx, r12
0x18006b9f4  ja      loc_18006BAE5
0x18006b9fa  mov     r9, rdi
0x18006b9fd  mov     [rsp+4D0h+var_4B0], rbx
0x18006ba02  lea     r8, aSS_0; "%s\\%s"
0x18006ba09  mov     edx, r12d; unsigned __int64
0x18006ba0c  lea     rcx, [rbp+3D0h+FileName]; unsigned __int16 *
0x18006ba13  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006ba18  lea     rdx, [rsp+4D0h+FindFileData]; lpFindFileData
0x18006ba1d  lea     rcx, [rbp+3D0h+FileName]; lpFileName
0x18006ba24  call    cs:__imp_FindFirstFileW
0x18006ba2b  nop     dword ptr [rax+rax+00h]
0x18006ba30  mov     r14, rax
0x18006ba33  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006ba37  jnz     short loc_18006BA4A
0x18006ba39  call    cs:__imp_GetLastError
0x18006ba40  nop     dword ptr [rax+rax+00h]
0x18006ba45  jmp     loc_18006BAEA
0x18006ba4a  lea     rcx, [rsp+4D0h+FindFileData.cFileName]
0x18006ba4f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006ba53  inc     rax
0x18006ba56  cmp     [rcx+rax*2], r15w
0x18006ba5b  jnz     short loc_18006BA53
0x18006ba5d  add     rax, 2
0x18006ba61  add     rax, rsi
0x18006ba64  cmp     rax, r12
0x18006ba67  ja      short loc_18006BAA4
0x18006ba69  lea     rax, [rsp+4D0h+FindFileData.cFileName]
0x18006ba6e  mov     r9, rdi
0x18006ba71  lea     r8, aSS_0; "%s\\%s"
0x18006ba78  mov     [rsp+4D0h+var_4B0], rax
0x18006ba7d  mov     rdx, r12; unsigned __int64
0x18006ba80  lea     rcx, [rbp+3D0h+FileName]; unsigned __int16 *
0x18006ba87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006ba8c  lea     rcx, [rbp+3D0h+FileName]; lpFileName
0x18006ba93  call    cs:__imp_DeleteFileW
0x18006ba9a  nop     dword ptr [rax+rax+00h]
0x18006ba9f  cmp     eax, 1
0x18006baa2  jnz     short loc_18006BABD
0x18006baa4  lea     rdx, [rsp+4D0h+FindFileData]; lpFindFileData
0x18006baa9  mov     rcx, r14; hFindFile
0x18006baac  call    cs:__imp_FindNextFileW
0x18006bab3  nop     dword ptr [rax+rax+00h]
0x18006bab8  cmp     eax, 1
0x18006babb  jz      short loc_18006BA4A
0x18006babd  call    cs:__imp_GetLastError
0x18006bac4  nop     dword ptr [rax+rax+00h]
0x18006bac9  mov     rcx, r14; hFindFile
0x18006bacc  mov     ebx, eax
0x18006bace  call    cs:__imp_FindClose
0x18006bad5  nop     dword ptr [rax+rax+00h]
0x18006bada  cmp     ebx, 12h
0x18006badd  cmovz   ebx, r15d
0x18006bae1  mov     eax, ebx
0x18006bae3  jmp     short loc_18006BAEA
0x18006bae5  mov     eax, 0Dh
0x18006baea  mov     rcx, [rbp+3D0h+var_30]
0x18006baf1  xor     rcx, rsp; StackCookie
0x18006baf4  call    __security_check_cookie
0x18006baf9  lea     r11, [rsp+4D0h+var_20]
0x18006bb01  mov     rbx, [r11+40h]
0x18006bb05  mov     rsi, [r11+48h]
0x18006bb09  mov     rsp, r11
0x18006bb0c  pop     r15
0x18006bb0e  pop     r14
0x18006bb10  pop     r12
0x18006bb12  pop     rdi
0x18006bb13  pop     rbp
0x18006bb14  retn
```
