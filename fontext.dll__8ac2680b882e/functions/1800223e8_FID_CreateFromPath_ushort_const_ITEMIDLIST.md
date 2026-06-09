# FID_CreateFromPath(ushort const *,_ITEMIDLIST * *)

- ea: `0x1800223e8`
- end: `0x1800224e5`
- name: `?FID_CreateFromPath@@YAJPEBGPEAPEFAU_ITEMIDLIST@@@Z`
- size: `253`
- prototype: `signed int __fastcall(const unsigned __int16 *, struct _ITEMIDLIST **)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180007154`
- `0x180007470`
- `0x18001e31c`
- `0x180023e40`
- `0x180026ef0`

## callees

- `0x180006624`
- `0x180022350`
- `0x1800223e8`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180022474`
- `SHLWAPI!PathFindFileNameW` at `0x180022474`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180022495`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180022495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800224b2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180022427`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180022427`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180022436`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180022436`

## pseudocode

```c
signed int __fastcall FID_CreateFromPath(const unsigned __int16 *a1, struct _ITEMIDLIST **a2)
{
  HANDLE FirstFileW; // rax
  signed int result; // eax
  const unsigned __int16 *FileNameW; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-478h] BYREF
  WCHAR pszPath[264]; // [rsp+270h] [rbp-228h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(a1, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    FindClose(FirstFileW);
    memset_0(pszPath, 0, 0x208u);
    result = StringCchCopyW(pszPath, 0x104u, a1);
    if ( result >= 0 )
    {
      FileNameW = PathFindFileNameW(pszPath);
      result = StringCchCopyW(FindFileData.cFileName, 0x104u, FileNameW);
      if ( result >= 0 )
      {
        PathRemoveFileSpecW(pszPath);
        return FID_CreateFromFindData(pszPath, &FindFileData, a2);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800223e8  mov     [rsp+arg_10], rbx
0x1800223ed  push    rdi
0x1800223ee  sub     rsp, 490h
0x1800223f5  mov     rax, cs:__security_cookie
0x1800223fc  xor     rax, rsp
0x1800223ff  mov     [rsp+498h+var_18], rax
0x180022407  mov     rdi, rdx
0x18002240a  mov     rbx, rcx
0x18002240d  xor     edx, edx; Val
0x18002240f  lea     rcx, [rsp+498h+FindFileData]; void *
0x180022414  mov     r8d, 250h; Size
0x18002241a  call    memset_0
0x18002241f  lea     rdx, [rsp+498h+FindFileData]; lpFindFileData
0x180022424  mov     rcx, rbx; lpFileName
0x180022427  call    cs:__imp_FindFirstFileW
0x18002242d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022431  jz      short loc_1800224B2
0x180022433  mov     rcx, rax; hFindFile
0x180022436  call    cs:__imp_FindClose
0x18002243c  xor     edx, edx; Val
0x18002243e  lea     rcx, [rsp+498h+pszPath]; void *
0x180022446  mov     r8d, 208h; Size
0x18002244c  call    memset_0
0x180022451  mov     r8, rbx; unsigned __int16 *
0x180022454  lea     rcx, [rsp+498h+pszPath]; unsigned __int16 *
0x18002245c  mov     ebx, 104h
0x180022461  mov     edx, ebx; unsigned __int64
0x180022463  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022468  test    eax, eax
0x18002246a  js      short loc_1800224C4
0x18002246c  lea     rcx, [rsp+498h+pszPath]; pszPath
0x180022474  call    cs:__imp_PathFindFileNameW
0x18002247a  mov     edx, ebx; unsigned __int64
0x18002247c  lea     rcx, [rsp+498h+FindFileData.cFileName]; unsigned __int16 *
0x180022481  mov     r8, rax; unsigned __int16 *
0x180022484  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022489  test    eax, eax
0x18002248b  js      short loc_1800224C4
0x18002248d  lea     rcx, [rsp+498h+pszPath]; pszPath
0x180022495  call    cs:__imp_PathRemoveFileSpecW
0x18002249b  mov     r8, rdi; struct _ITEMIDLIST **
0x18002249e  lea     rdx, [rsp+498h+FindFileData]; struct _WIN32_FIND_DATAW *
0x1800224a3  lea     rcx, [rsp+498h+pszPath]; pszDir
0x1800224ab  call    ?FID_CreateFromFindData@@YAJPEBGAEBU_WIN32_FIND_DATAW@@PEAPEFAU_ITEMIDLIST@@@Z; FID_CreateFromFindData(ushort const *,_WIN32_FIND_DATAW const &,_ITEMIDLIST * *)
0x1800224b0  jmp     short loc_1800224C4
0x1800224b2  call    cs:__imp_GetLastError
0x1800224b8  test    eax, eax
0x1800224ba  jle     short loc_1800224C4
0x1800224bc  movzx   eax, ax
0x1800224bf  or      eax, 80070000h
0x1800224c4  mov     rcx, [rsp+498h+var_18]
0x1800224cc  xor     rcx, rsp; StackCookie
0x1800224cf  call    __security_check_cookie
0x1800224d4  mov     rbx, [rsp+498h+arg_10]
0x1800224dc  add     rsp, 490h
0x1800224e3  pop     rdi
0x1800224e4  retn
```
