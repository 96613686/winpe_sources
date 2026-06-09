# DosGetMessage

- ea: `0x18008e23c`
- end: `0x18008e4c0`
- name: `DosGetMessage`
- size: `644`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180036f50`

## callees

- `0x180003320`
- `0x1800037f0`
- `0x18000e910`
- `0x18000f352`
- `0x18000f3c0`
- `0x18000f3e4`
- `0x18008e23c`
- `0x18008e4c8`
- `0x18008e580`
- `0x1800901d4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008e316`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008e316`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008e2ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008e2ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e477`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18008e366`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18008e418`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18008e366`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18008e418`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18008e462`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18008e462`

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
0x18008e23c  push    rbp
0x18008e23e  push    rbx
0x18008e23f  push    rsi
0x18008e240  push    rdi
0x18008e241  push    r12
0x18008e243  push    r13
0x18008e245  push    r14
0x18008e247  push    r15
0x18008e249  lea     rbp, [rsp-298h]
0x18008e251  sub     rsp, 398h
0x18008e258  mov     rax, cs:__security_cookie
0x18008e25f  xor     rax, rsp
0x18008e262  mov     [rbp+2D0h+var_48], rax
0x18008e269  mov     r14, [rbp+2D0h+arg_30]
0x18008e270  lea     rcx, [rsp+3D0h+var_380]; void *
0x18008e275  mov     r15, r8
0x18008e278  mov     ebx, 320h
0x18008e27d  mov     r8d, ebx; Size
0x18008e280  xor     edx, edx; Val
0x18008e282  call    memset_0
0x18008e287  xor     r12d, r12d
0x18008e28a  mov     qword ptr [rsp+3D0h+UsedDefaultChar], r12
0x18008e28f  mov     [r15], r12b
0x18008e292  test    r14, r14
0x18008e295  jz      short loc_18008E29B
0x18008e297  mov     [r14], r12w
0x18008e29b  mov     ecx, 0A2h
0x18008e2a0  call    NetpMemoryAllocate
0x18008e2a5  mov     rdi, rax
0x18008e2a8  test    rax, rax
0x18008e2ab  jnz     short loc_18008E2B5
0x18008e2ad  lea     eax, [rdi+8]
0x18008e2b0  jmp     loc_18008E49C
0x18008e2b5  mov     r8, rbx; Size
0x18008e2b8  lea     rcx, [rsp+3D0h+var_380]; void *
0x18008e2bd  xor     edx, edx; Val
0x18008e2bf  call    memset_0
0x18008e2c4  mov     rsi, cs:lpSource
0x18008e2cb  lea     r13, aNetmsg; "NETMSG"
0x18008e2d2  test    rsi, rsi
0x18008e2d5  jz      short loc_18008E2F9
0x18008e2d7  mov     rdx, r13; String2
0x18008e2da  lea     rcx, String1; String1
0x18008e2e1  call    wcscmp_0
0x18008e2e6  test    eax, eax
0x18008e2e8  jz      short loc_18008E33B
0x18008e2ea  mov     rcx, rsi; hLibModule
0x18008e2ed  call    cs:__imp_FreeLibrary
0x18008e2f4  nop     dword ptr [rax+rax+00h]
0x18008e2f9  mov     r8, r13; Source
0x18008e2fc  lea     rcx, String1; Destination
0x18008e303  mov     edx, 104h; SizeInWords
0x18008e308  call    wcscpy_s
0x18008e30d  xor     edx, edx; hFile
0x18008e30f  mov     rcx, r13; lpLibFileName
0x18008e312  lea     r8d, [rdx+2]; dwFlags
0x18008e316  call    cs:__imp_LoadLibraryExW
0x18008e31d  nop     dword ptr [rax+rax+00h]
0x18008e322  mov     cs:lpSource, rax
0x18008e329  mov     rsi, rax
0x18008e32c  test    rax, rax
0x18008e32f  jnz     short loc_18008E33B
0x18008e331  mov     ebx, 13Eh
0x18008e336  jmp     loc_18008E485
0x18008e33b  lea     rax, [rsp+3D0h+var_380]
0x18008e340  xor     r9d, r9d; dwLanguageId
0x18008e343  mov     [rsp+3D0h+Arguments], rax; Arguments
0x18008e348  mov     r8d, 0CE7h; dwMessageId
0x18008e34e  mov     [rsp+3D0h+nSize], 51h ; 'Q'; nSize
0x18008e356  mov     rdx, rsi; lpSource
0x18008e359  mov     ecx, 2A00h; dwFlags
0x18008e35e  mov     [rsp+3D0h+lpBuffer], rdi; lpBuffer
0x18008e363  mov     ebx, r12d
0x18008e366  call    cs:__imp_FormatMessageW
0x18008e36d  nop     dword ptr [rax+rax+00h]
0x18008e372  mov     [r14], ax
0x18008e376  test    ax, ax
0x18008e379  jnz     loc_18008E42F
0x18008e37f  mov     [rdi], r12w
0x18008e383  call    cs:__imp_GetLastError
0x18008e38a  nop     dword ptr [rax+rax+00h]
0x18008e38f  mov     esi, 13Dh
0x18008e394  mov     ebx, eax
0x18008e396  cmp     eax, esi
0x18008e398  jnz     loc_18008E42F
0x18008e39e  mov     r9d, 10h; Radix
0x18008e3a4  lea     rdx, [rbp+2D0h+Buffer]; Buffer
0x18008e3ab  mov     ecx, 0CE7h; Value
0x18008e3b0  lea     r8d, [r9+2]; BufferCount
0x18008e3b4  call    _itoa_s
0x18008e3b9  lea     rdx, [rsp+3D0h+UsedDefaultChar]
0x18008e3be  lea     rcx, [rbp+2D0h+Buffer]; lpMultiByteStr
0x18008e3c5  call    MyAllocUnicode
0x18008e3ca  mov     ebx, eax
0x18008e3cc  test    eax, eax
0x18008e3ce  jnz     loc_18008E485
0x18008e3d4  xor     edx, edx
0x18008e3d6  lea     rcx, [rsp+3D0h+var_380]
0x18008e3db  call    MyFreeUnicodeVector
0x18008e3e0  mov     rax, qword ptr [rsp+3D0h+UsedDefaultChar]
0x18008e3e5  xor     r9d, r9d; dwLanguageId
0x18008e3e8  mov     rdx, cs:lpSource; lpSource
0x18008e3ef  mov     r8d, esi; dwMessageId
0x18008e3f2  mov     [rsp+3D0h+var_380], rax
0x18008e3f7  mov     ecx, 3000h; dwFlags
0x18008e3fc  lea     rax, [rsp+3D0h+var_380]
0x18008e401  mov     [rsp+3D0h+var_378], r13
0x18008e406  mov     [rsp+3D0h+Arguments], rax; Arguments
0x18008e40b  mov     [rsp+3D0h+nSize], 51h ; 'Q'; nSize
0x18008e413  mov     [rsp+3D0h+lpBuffer], rdi; lpBuffer
0x18008e418  call    cs:__imp_FormatMessageW
0x18008e41f  nop     dword ptr [rax+rax+00h]
0x18008e424  mov     [rsp+3D0h+var_378], r12
0x18008e429  mov     ebx, esi
0x18008e42b  mov     [r14], ax
0x18008e42f  cmp     [rdi], r12w
0x18008e433  jz      short loc_18008E485
0x18008e435  xor     edx, edx; dwFlags
0x18008e437  mov     [rsp+3D0h+UsedDefaultChar], r12d
0x18008e43c  lea     rax, [rsp+3D0h+UsedDefaultChar]
0x18008e441  or      r9d, 0FFFFFFFFh; cchWideChar
0x18008e445  mov     [rsp+3D0h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18008e44a  mov     r8, rdi; lpWideCharStr
0x18008e44d  mov     [rsp+3D0h+Arguments], r12; lpDefaultChar
0x18008e452  lea     ecx, [rdx+1]; CodePage
0x18008e455  mov     [rsp+3D0h+nSize], 51h ; 'Q'; cbMultiByte
0x18008e45d  mov     [rsp+3D0h+lpBuffer], r15; lpMultiByteStr
0x18008e462  call    cs:__imp_WideCharToMultiByte
0x18008e469  nop     dword ptr [rax+rax+00h]
0x18008e46e  mov     [r14], ax
0x18008e472  test    ax, ax
0x18008e475  jnz     short loc_18008E485
0x18008e477  call    cs:__imp_GetLastError
0x18008e47e  nop     dword ptr [rax+rax+00h]
0x18008e483  mov     ebx, eax
0x18008e485  mov     rcx, rdi
0x18008e488  call    NetpMemoryFree
0x18008e48d  xor     edx, edx
0x18008e48f  lea     rcx, [rsp+3D0h+var_380]
0x18008e494  call    MyFreeUnicodeVector
0x18008e499  movzx   eax, bx
0x18008e49c  mov     rcx, [rbp+2D0h+var_48]
0x18008e4a3  xor     rcx, rsp; StackCookie
0x18008e4a6  call    __security_check_cookie
0x18008e4ab  add     rsp, 398h
0x18008e4b2  pop     r15
0x18008e4b4  pop     r14
0x18008e4b6  pop     r13
0x18008e4b8  pop     r12
0x18008e4ba  pop     rdi
0x18008e4bb  pop     rsi
0x18008e4bc  pop     rbx
0x18008e4bd  pop     rbp
0x18008e4be  retn
```
