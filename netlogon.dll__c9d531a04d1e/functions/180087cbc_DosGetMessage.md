# DosGetMessage

- ea: `0x180087cbc`
- end: `0x180087f15`
- name: `DosGetMessage`
- size: `601`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180034fa8`

## callees

- `0x180003200`
- `0x180003670`
- `0x18000e270`
- `0x18000eca2`
- `0x18000ed10`
- `0x18000ed34`
- `0x180087cbc`
- `0x180087f1c`
- `0x180087fc4`
- `0x180089a84`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180087d90`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180087d90`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180087d6d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180087d6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087df1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087df1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087ed3`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180087dda`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180087e80`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180087dda`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180087e80`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180087ec4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180087ec4`

## pseudocode

```c
__int64 __fastcall DosGetMessage(__int64 a1, __int64 a2, CHAR *a3, __int64 a4, __int64 a5, __int64 a6, _WORD *a7)
{
  WCHAR *lpBuffer; // rdi
  HMODULE v10; // rsi
  unsigned __int16 v11; // bx
  __int16 v12; // ax
  DWORD LastError; // eax
  int v14; // eax
  __int16 v15; // ax
  __int16 v16; // ax
  WINBOOL UsedDefaultChar[4]; // [rsp+40h] [rbp-C0h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v19; // [rsp+58h] [rbp-A8h]
  char Buffer[24]; // [rsp+370h] [rbp+270h] BYREF

  memset_0(&Arguments, 0, 0x320u);
  *(_QWORD *)UsedDefaultChar = 0;
  *a3 = 0;
  if ( a7 )
    *a7 = 0;
  lpBuffer = (WCHAR *)NetpMemoryAllocate(162);
  if ( !lpBuffer )
    return 8;
  memset_0(&Arguments, 0, 0x320u);
  v10 = lpSource;
  if ( lpSource )
  {
    if ( !wcscmp_0(&String1, L"NETMSG") )
    {
LABEL_10:
      v11 = 0;
      v12 = FormatMessageW(0x2A00u, v10, 0xCE7u, 0, lpBuffer, 0x51u, &Arguments);
      *a7 = v12;
      if ( !v12 )
      {
        *lpBuffer = 0;
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError == 317 )
        {
          itoa_s(3303, Buffer, 0x12u, 16);
          v14 = MyAllocUnicode(Buffer);
          v11 = v14;
          if ( v14 )
            goto LABEL_17;
          MyFreeUnicodeVector(&Arguments, 0);
          Arguments = *(va_list *)UsedDefaultChar;
          v19 = L"NETMSG";
          v15 = FormatMessageW(0x3000u, lpSource, 0x13Du, 0, lpBuffer, 0x51u, &Arguments);
          v19 = 0;
          v11 = 317;
          *a7 = v15;
        }
      }
      if ( *lpBuffer )
      {
        UsedDefaultChar[0] = 0;
        v16 = WideCharToMultiByte(1u, 0, lpBuffer, -1, a3, 81, 0, UsedDefaultChar);
        *a7 = v16;
        if ( !v16 )
          v11 = GetLastError();
      }
      goto LABEL_17;
    }
    FreeLibrary(v10);
  }
  wcscpy_s(&String1, 0x104u, L"NETMSG");
  lpSource = LoadLibraryExW(L"NETMSG", 0, 2u);
  v10 = lpSource;
  if ( lpSource )
    goto LABEL_10;
  v11 = 318;
LABEL_17:
  NetpMemoryFree(lpBuffer);
  MyFreeUnicodeVector(&Arguments, 0);
  return v11;
}

```

## disassembly

```asm
0x180087cbc  push    rbp
0x180087cbe  push    rbx
0x180087cbf  push    rsi
0x180087cc0  push    rdi
0x180087cc1  push    r12
0x180087cc3  push    r13
0x180087cc5  push    r14
0x180087cc7  push    r15
0x180087cc9  lea     rbp, [rsp-298h]
0x180087cd1  sub     rsp, 398h
0x180087cd8  mov     rax, cs:__security_cookie
0x180087cdf  xor     rax, rsp
0x180087ce2  mov     [rbp+2D0h+var_48], rax
0x180087ce9  mov     r14, [rbp+2D0h+arg_30]
0x180087cf0  lea     rcx, [rsp+3D0h+var_380]; void *
0x180087cf5  mov     r15, r8
0x180087cf8  mov     ebx, 320h
0x180087cfd  mov     r8d, ebx; Size
0x180087d00  xor     edx, edx; Val
0x180087d02  call    memset_0
0x180087d07  xor     r12d, r12d
0x180087d0a  mov     qword ptr [rsp+3D0h+UsedDefaultChar], r12
0x180087d0f  mov     [r15], r12b
0x180087d12  test    r14, r14
0x180087d15  jz      short loc_180087D1B
0x180087d17  mov     [r14], r12w
0x180087d1b  mov     ecx, 0A2h
0x180087d20  call    NetpMemoryAllocate
0x180087d25  mov     rdi, rax
0x180087d28  test    rax, rax
0x180087d2b  jnz     short loc_180087D35
0x180087d2d  lea     eax, [rdi+8]
0x180087d30  jmp     loc_180087EF2
0x180087d35  mov     r8, rbx; Size
0x180087d38  lea     rcx, [rsp+3D0h+var_380]; void *
0x180087d3d  xor     edx, edx; Val
0x180087d3f  call    memset_0
0x180087d44  mov     rsi, cs:lpSource
0x180087d4b  lea     r13, aNetmsg; "NETMSG"
0x180087d52  test    rsi, rsi
0x180087d55  jz      short loc_180087D73
0x180087d57  mov     rdx, r13; String2
0x180087d5a  lea     rcx, String1; String1
0x180087d61  call    wcscmp_0
0x180087d66  test    eax, eax
0x180087d68  jz      short loc_180087DAF
0x180087d6a  mov     rcx, rsi; hLibModule
0x180087d6d  call    cs:__imp_FreeLibrary
0x180087d73  mov     r8, r13; Source
0x180087d76  lea     rcx, String1; Destination
0x180087d7d  mov     edx, 104h; SizeInWords
0x180087d82  call    wcscpy_s
0x180087d87  xor     edx, edx; hFile
0x180087d89  mov     rcx, r13; lpLibFileName
0x180087d8c  lea     r8d, [rdx+2]; dwFlags
0x180087d90  call    cs:__imp_LoadLibraryExW
0x180087d96  mov     cs:lpSource, rax
0x180087d9d  mov     rsi, rax
0x180087da0  test    rax, rax
0x180087da3  jnz     short loc_180087DAF
0x180087da5  mov     ebx, 13Eh
0x180087daa  jmp     loc_180087EDB
0x180087daf  lea     rax, [rsp+3D0h+var_380]
0x180087db4  xor     r9d, r9d; dwLanguageId
0x180087db7  mov     [rsp+3D0h+Arguments], rax; Arguments
0x180087dbc  mov     r8d, 0CE7h; dwMessageId
0x180087dc2  mov     [rsp+3D0h+nSize], 51h ; 'Q'; nSize
0x180087dca  mov     rdx, rsi; lpSource
0x180087dcd  mov     ecx, 2A00h; dwFlags
0x180087dd2  mov     [rsp+3D0h+lpBuffer], rdi; lpBuffer
0x180087dd7  mov     ebx, r12d
0x180087dda  call    cs:__imp_FormatMessageW
0x180087de0  mov     [r14], ax
0x180087de4  test    ax, ax
0x180087de7  jnz     loc_180087E91
0x180087ded  mov     [rdi], r12w
0x180087df1  call    cs:__imp_GetLastError
0x180087df7  mov     esi, 13Dh
0x180087dfc  mov     ebx, eax
0x180087dfe  cmp     eax, esi
0x180087e00  jnz     loc_180087E91
0x180087e06  mov     r9d, 10h; Radix
0x180087e0c  lea     rdx, [rbp+2D0h+Buffer]; Buffer
0x180087e13  mov     ecx, 0CE7h; Value
0x180087e18  lea     r8d, [r9+2]; BufferCount
0x180087e1c  call    _itoa_s
0x180087e21  lea     rdx, [rsp+3D0h+UsedDefaultChar]
0x180087e26  lea     rcx, [rbp+2D0h+Buffer]; lpMultiByteStr
0x180087e2d  call    MyAllocUnicode
0x180087e32  mov     ebx, eax
0x180087e34  test    eax, eax
0x180087e36  jnz     loc_180087EDB
0x180087e3c  xor     edx, edx
0x180087e3e  lea     rcx, [rsp+3D0h+var_380]
0x180087e43  call    MyFreeUnicodeVector
0x180087e48  mov     rax, qword ptr [rsp+3D0h+UsedDefaultChar]
0x180087e4d  xor     r9d, r9d; dwLanguageId
0x180087e50  mov     rdx, cs:lpSource; lpSource
0x180087e57  mov     r8d, esi; dwMessageId
0x180087e5a  mov     [rsp+3D0h+var_380], rax
0x180087e5f  mov     ecx, 3000h; dwFlags
0x180087e64  lea     rax, [rsp+3D0h+var_380]
0x180087e69  mov     [rsp+3D0h+var_378], r13
0x180087e6e  mov     [rsp+3D0h+Arguments], rax; Arguments
0x180087e73  mov     [rsp+3D0h+nSize], 51h ; 'Q'; nSize
0x180087e7b  mov     [rsp+3D0h+lpBuffer], rdi; lpBuffer
0x180087e80  call    cs:__imp_FormatMessageW
0x180087e86  mov     [rsp+3D0h+var_378], r12
0x180087e8b  mov     ebx, esi
0x180087e8d  mov     [r14], ax
0x180087e91  cmp     [rdi], r12w
0x180087e95  jz      short loc_180087EDB
0x180087e97  xor     edx, edx; dwFlags
0x180087e99  mov     [rsp+3D0h+UsedDefaultChar], r12d
0x180087e9e  lea     rax, [rsp+3D0h+UsedDefaultChar]
0x180087ea3  or      r9d, 0FFFFFFFFh; cchWideChar
0x180087ea7  mov     [rsp+3D0h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180087eac  mov     r8, rdi; lpWideCharStr
0x180087eaf  mov     [rsp+3D0h+Arguments], r12; lpDefaultChar
0x180087eb4  lea     ecx, [rdx+1]; CodePage
0x180087eb7  mov     [rsp+3D0h+nSize], 51h ; 'Q'; cbMultiByte
0x180087ebf  mov     [rsp+3D0h+lpBuffer], r15; lpMultiByteStr
0x180087ec4  call    cs:__imp_WideCharToMultiByte
0x180087eca  mov     [r14], ax
0x180087ece  test    ax, ax
0x180087ed1  jnz     short loc_180087EDB
0x180087ed3  call    cs:__imp_GetLastError
0x180087ed9  mov     ebx, eax
0x180087edb  mov     rcx, rdi
0x180087ede  call    NetpMemoryFree
0x180087ee3  xor     edx, edx
0x180087ee5  lea     rcx, [rsp+3D0h+var_380]
0x180087eea  call    MyFreeUnicodeVector
0x180087eef  movzx   eax, bx
0x180087ef2  mov     rcx, [rbp+2D0h+var_48]
0x180087ef9  xor     rcx, rsp; StackCookie
0x180087efc  call    __security_check_cookie
0x180087f01  add     rsp, 398h
0x180087f08  pop     r15
0x180087f0a  pop     r14
0x180087f0c  pop     r13
0x180087f0e  pop     r12
0x180087f10  pop     rdi
0x180087f11  pop     rsi
0x180087f12  pop     rbx
0x180087f13  pop     rbp
0x180087f14  retn
```
