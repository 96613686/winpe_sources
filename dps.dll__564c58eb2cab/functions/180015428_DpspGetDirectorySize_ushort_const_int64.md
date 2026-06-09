# DpspGetDirectorySize(ushort const *,__int64 *)

- ea: `0x180015428`
- end: `0x180015713`
- name: `?DpspGetDirectorySize@@YAJPEBGPEA_J@Z`
- size: `747`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180015428`
- `0x18001585c`

## callees

- `0x180009090`
- `0x180009fb0`
- `0x180009ff0`
- `0x18000a856`
- `0x18000c93c`
- `0x180015428`
- `0x18001571c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015521`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800154e1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800156c1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800154e1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800156c1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800154c9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800155b9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800154c9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800155b9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800156b0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800156b0`

## string_xrefs

- `0x180015499`: `DpspGetDirectorySize`
- `0x180015672`: `DpspGetDirectorySize`

## pseudocode

```c
__int64 __fastcall DpspGetDirectorySize(const unsigned __int16 *a1, __int64 *a2)
{
  int v4; // r8d
  unsigned int Args; // ebx
  char *FirstFileW; // rdi
  unsigned __int64 v7; // rdi
  signed int LastError; // eax
  unsigned __int64 v9; // rcx
  HANDLE v10; // rax
  void *v11; // r14
  unsigned __int64 v12; // rdi
  __int64 v13; // r9
  int DirectorySize; // eax
  __int64 EffectiveFileSize; // rax
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v17 = 0;
  if ( !a1 )
  {
    v4 = 208;
LABEL_3:
    Args = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
      (int)L"DpspGetDirectorySize",
      v4,
      (int)L"Error = %d",
      87);
    return Args;
  }
  if ( !a2 )
  {
    v4 = 209;
    goto LABEL_3;
  }
  *a2 = 0;
  FirstFileW = (char *)FindFirstFileW(a1, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    Args = LastError;
    if ( LastError > 0 )
      Args = (unsigned __int16)LastError | 0x80070000;
    if ( (Args & 0x80000000) != 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
        (int)L"DpspGetDirectorySize",
        214,
        (int)L"Error = %d",
        Args);
      return Args;
    }
  }
  else
  {
    Args = 0;
  }
  FindClose(FirstFileW);
  if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
  {
    *a2 += DpspGetEffectiveFileSize(FindFileData.nFileSizeLow + ((unsigned __int64)FindFileData.nFileSizeHigh << 32));
    return Args;
  }
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  if ( v7 >= 0x101 )
  {
    Args = -2147024362;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
      (int)L"DpspGetDirectorySize",
      229,
      (int)L"Error = %d",
      22);
    return Args;
  }
  if ( memcpy_s(FileName, 0x104u, a1, 2 * v7) )
  {
    Args = -2147020579;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
      (int)L"DpspGetDirectorySize",
      235,
      (int)L"Error = %d",
      221);
    return Args;
  }
  v9 = 2 * v7 + 4;
  *(_DWORD *)&FileName[v7] = 2752604;
  if ( v9 >= 0x208 )
    _report_rangecheckfailure();
  *(WCHAR *)((char *)FileName + v9) = 0;
  v10 = FindFirstFileW(FileName, &FindFileData);
  v11 = v10;
  if ( v10 )
  {
    v12 = v7 + 1;
    if ( v10 != (HANDLE)-1LL )
    {
      while ( 1 )
      {
        if ( FindFileData.cFileName[0] == 46
          && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
        {
          goto LABEL_34;
        }
        v13 = -1;
        do
          ++v13;
        while ( FindFileData.cFileName[v13] );
        memcpy_s(&FileName[v12], 260 - v12, FindFileData.cFileName, 2 * v13 + 2);
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
          break;
        DirectorySize = DpspGetDirectorySize(FileName, &v17);
        Args = DirectorySize;
        if ( DirectorySize >= 0 )
        {
          EffectiveFileSize = v17;
LABEL_33:
          *a2 += EffectiveFileSize;
          goto LABEL_34;
        }
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
          (int)L"DpspGetDirectorySize",
          273,
          (int)L"Error = %d",
          DirectorySize);
        Args = 0;
LABEL_34:
        if ( !FindNextFileW(v11, &FindFileData) )
        {
          FindClose(v11);
          return Args;
        }
      }
      EffectiveFileSize = DpspGetEffectiveFileSize(FindFileData.nFileSizeLow + ((unsigned __int64)FindFileData.nFileSizeHigh << 32));
      goto LABEL_33;
    }
  }
  return Args;
}

```

## disassembly

```asm
0x180015428  mov     [rsp-8+arg_10], rbx
0x18001542d  mov     [rsp-8+arg_18], rsi
0x180015432  push    rbp
0x180015433  push    rdi
0x180015434  push    r12
0x180015436  push    r14
0x180015438  push    r15
0x18001543a  lea     rbp, [rsp-3B0h]
0x180015442  sub     rsp, 4B0h
0x180015449  mov     rax, cs:__security_cookie
0x180015450  xor     rax, rsp
0x180015453  mov     [rbp+3D0h+var_30], rax
0x18001545a  mov     rsi, rdx
0x18001545d  mov     r14, rcx
0x180015460  xor     edx, edx; Val
0x180015462  lea     rcx, [rsp+4D0h+FindFileData]; void *
0x180015467  mov     r8d, 250h; Size
0x18001546d  call    memset_0
0x180015472  xor     r12d, r12d
0x180015475  mov     [rsp+4D0h+var_4A0], r12
0x18001547a  test    r14, r14
0x18001547d  jnz     short loc_1800154B1
0x18001547f  mov     r8d, 0D0h; int
0x180015485  mov     dword ptr [rsp+4D0h+Args], 57h ; 'W'; Args
0x18001548d  mov     ebx, 80070057h
0x180015492  lea     r9, aErrorD; "Error = %d"
0x180015499  lea     rdx, aDpspgetdirecto; "DpspGetDirectorySize"
0x1800154a0  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800154a7  call    WdipTraceError
0x1800154ac  jmp     loc_1800156E0
0x1800154b1  test    rsi, rsi
0x1800154b4  jnz     short loc_1800154BE
0x1800154b6  mov     r8d, 0D1h
0x1800154bc  jmp     short loc_180015485
0x1800154be  lea     rdx, [rsp+4D0h+FindFileData]; lpFindFileData
0x1800154c3  mov     [rsi], r12
0x1800154c6  mov     rcx, r14; lpFileName
0x1800154c9  call    cs:__imp_FindFirstFileW
0x1800154cf  mov     rdi, rax
0x1800154d2  dec     rax
0x1800154d5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800154d9  ja      short loc_180015521
0x1800154db  mov     ebx, r12d
0x1800154de  mov     rcx, rdi; hFindFile
0x1800154e1  call    cs:__imp_FindClose
0x1800154e7  test    byte ptr [rsp+4D0h+FindFileData.dwFileAttributes], 10h
0x1800154ec  jz      loc_1800156C9
0x1800154f2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800154f6  inc     rdi
0x1800154f9  cmp     [r14+rdi*2], r12w
0x1800154fe  jnz     short loc_1800154F6
0x180015500  cmp     rdi, 101h
0x180015507  jb      short loc_18001554C
0x180015509  mov     ebx, 80070216h
0x18001550e  mov     dword ptr [rsp+4D0h+Args], 216h
0x180015516  mov     r8d, 0E5h
0x18001551c  jmp     loc_180015492
0x180015521  call    cs:__imp_GetLastError
0x180015527  mov     ebx, eax
0x180015529  test    eax, eax
0x18001552b  jle     short loc_180015536
0x18001552d  movzx   ebx, ax
0x180015530  or      ebx, 80070000h
0x180015536  test    ebx, ebx
0x180015538  jns     short loc_1800154DE
0x18001553a  movzx   eax, bx
0x18001553d  mov     r8d, 0D6h
0x180015543  mov     dword ptr [rsp+4D0h+Args], eax
0x180015547  jmp     loc_180015492
0x18001554c  lea     r15, [rdi+rdi]
0x180015550  mov     r8, r14; Source
0x180015553  mov     r9, r15; SourceSize
0x180015556  lea     rcx, [rbp+3D0h+FileName]; Destination
0x18001555d  mov     edx, 104h; DestinationSize
0x180015562  call    memcpy_s
0x180015567  test    eax, eax
0x180015569  jz      short loc_180015583
0x18001556b  mov     ebx, 800710DDh
0x180015570  mov     dword ptr [rsp+4D0h+Args], 10DDh
0x180015578  mov     r8d, 0EBh
0x18001557e  jmp     loc_180015492
0x180015583  lea     rcx, ds:4[rdi*2]
0x18001558b  mov     dword ptr [rbp+r15+3D0h+FileName], 2A005Ch
0x180015597  cmp     rcx, 208h
0x18001559e  jnb     loc_18001570D
0x1800155a4  mov     [rbp+rcx+3D0h+FileName], r12w
0x1800155ad  lea     rdx, [rsp+4D0h+FindFileData]; lpFindFileData
0x1800155b2  lea     rcx, [rbp+3D0h+FileName]; lpFileName
0x1800155b9  call    cs:__imp_FindFirstFileW
0x1800155bf  mov     r14, rax
0x1800155c2  test    rax, rax
0x1800155c5  jz      loc_1800156E0
0x1800155cb  inc     rdi
0x1800155ce  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800155d2  jz      loc_1800156E0
0x1800155d8  cmp     [rsp+4D0h+FindFileData.cFileName], 2Eh ; '.'
0x1800155de  movzx   eax, [rsp+4D0h+FindFileData.cFileName+2]
0x1800155e3  jnz     short loc_180015608
0x1800155e5  test    ax, ax
0x1800155e8  jz      loc_1800156A8
0x1800155ee  cmp     [rsp+4D0h+FindFileData.cFileName], 2Eh ; '.'
0x1800155f4  jnz     short loc_180015608
0x1800155f6  cmp     ax, 2Eh ; '.'
0x1800155fa  jnz     short loc_180015608
0x1800155fc  cmp     [rsp+4D0h+FindFileData.cFileName+4], r12w
0x180015602  jz      loc_1800156A8
0x180015608  lea     rax, [rsp+4D0h+FindFileData.cFileName]
0x18001560d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180015611  inc     r9
0x180015614  cmp     [rax+r9*2], r12w
0x180015619  jnz     short loc_180015611
0x18001561b  mov     edx, 104h
0x180015620  lea     rcx, [rbp+3D0h+FileName]
0x180015627  sub     rdx, rdi; DestinationSize
0x18001562a  lea     rcx, [rcx+rdi*2]; Destination
0x18001562e  lea     r9, ds:2[r9*2]; SourceSize
0x180015636  lea     r8, [rsp+4D0h+FindFileData.cFileName]; Source
0x18001563b  call    memcpy_s
0x180015640  test    byte ptr [rsp+4D0h+FindFileData.dwFileAttributes], 10h
0x180015645  jz      short loc_180015691
0x180015647  lea     rdx, [rsp+4D0h+var_4A0]; __int64 *
0x18001564c  lea     rcx, [rbp+3D0h+FileName]; unsigned __int16 *
0x180015653  call    ?DpspGetDirectorySize@@YAJPEBGPEA_J@Z; DpspGetDirectorySize(ushort const *,__int64 *)
0x180015658  mov     ebx, eax
0x18001565a  test    eax, eax
0x18001565c  jns     short loc_18001568A
0x18001565e  movzx   eax, ax
0x180015661  lea     r9, aErrorD; "Error = %d"
0x180015668  mov     r8d, 111h; int
0x18001566e  mov     dword ptr [rsp+4D0h+Args], eax; Args
0x180015672  lea     rdx, aDpspgetdirecto; "DpspGetDirectorySize"
0x180015679  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180015680  call    WdipTraceError
0x180015685  mov     ebx, r12d
0x180015688  jmp     short loc_1800156A8
0x18001568a  mov     rax, [rsp+4D0h+var_4A0]
0x18001568f  jmp     short loc_1800156A5
0x180015691  mov     eax, [rsp+4D0h+FindFileData.nFileSizeLow]
0x180015695  mov     ecx, [rsp+4D0h+FindFileData.nFileSizeHigh]
0x180015699  shl     rcx, 20h
0x18001569d  add     rcx, rax; unsigned __int64
0x1800156a0  call    ?DpspGetEffectiveFileSize@@YA_J_K@Z; DpspGetEffectiveFileSize(unsigned __int64)
0x1800156a5  add     [rsi], rax
0x1800156a8  lea     rdx, [rsp+4D0h+FindFileData]; lpFindFileData
0x1800156ad  mov     rcx, r14; hFindFile
0x1800156b0  call    cs:__imp_FindNextFileW
0x1800156b6  test    eax, eax
0x1800156b8  jnz     loc_1800155D8
0x1800156be  mov     rcx, r14; hFindFile
0x1800156c1  call    cs:__imp_FindClose
0x1800156c7  jmp     short loc_1800156E0
0x1800156c9  mov     eax, [rsp+4D0h+FindFileData.nFileSizeLow]
0x1800156cd  mov     ecx, [rsp+4D0h+FindFileData.nFileSizeHigh]
0x1800156d1  shl     rcx, 20h
0x1800156d5  add     rcx, rax; unsigned __int64
0x1800156d8  call    ?DpspGetEffectiveFileSize@@YA_J_K@Z; DpspGetEffectiveFileSize(unsigned __int64)
0x1800156dd  add     [rsi], rax
0x1800156e0  mov     eax, ebx
0x1800156e2  mov     rcx, [rbp+3D0h+var_30]
0x1800156e9  xor     rcx, rsp; StackCookie
0x1800156ec  call    __security_check_cookie
0x1800156f1  lea     r11, [rsp+4D0h+var_20]
0x1800156f9  mov     rbx, [r11+40h]
0x1800156fd  mov     rsi, [r11+48h]
0x180015701  mov     rsp, r11
0x180015704  pop     r15
0x180015706  pop     r14
0x180015708  pop     r12
0x18001570a  pop     rdi
0x18001570b  pop     rbp
0x18001570c  retn
0x18001570d  call    __report_rangecheckfailure
```
