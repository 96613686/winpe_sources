# _LoadImage

- ea: `0x180008a90`
- end: `0x180008c16`
- name: `_LoadImage`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007df4`

## callees

- `0x180008a90`
- `0x180008c1c`
- `0x18000a770`
- `0x18000d02c`
- `0x18000e120`
- `0x180014410`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180008b0b`
- `ntdll!RtlCompareUnicodeString` at `0x180008b0b`
- `ntdll!RtlInitUnicodeString` at `0x180008ad8`
- `ntdll!RtlInitUnicodeString` at `0x180008ad8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008b27`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008b27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008be0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008be0`

## string_xrefs

- `0x180008ab4`: `ncrypt.dll`
- `0x180008bab`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180008beb`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall LoadImage(__int64 a1, HMODULE *a2)
{
  PCWSTR *v3; // rdx
  int v4; // r14d
  int ImagePath; // eax
  int v6; // edx
  const WCHAR *v7; // rsi
  unsigned int v8; // ebx
  HMODULE Library; // rax
  int v10; // r8d
  UNICODE_STRING String2; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  LPCWSTR lpLibFileName; // [rsp+80h] [rbp+20h] BYREF

  *(_QWORD *)&String2.Length = 1441812;
  v3 = *(PCWSTR **)(a1 + 40);
  String2.Buffer = L"ncrypt.dll";
  v4 = a1;
  lpLibFileName = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, *v3);
  ImagePath = GetImagePath(&DestinationString, &lpLibFileName);
  v7 = lpLibFileName;
  v8 = ImagePath;
  if ( ImagePath < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        (unsigned int)"sResult",
        ImagePath,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        171);
  }
  else
  {
    *a2 = 0;
    if ( !RtlCompareUnicodeString(&DestinationString, &String2, 1u) )
      *a2 = (HMODULE)g_hInstance;
    if ( *a2 )
      goto LABEL_9;
    Library = LoadLibraryExW(v7, 0, 0);
    *a2 = Library;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_qSq(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)Library, v10, v4, (__int64)v7, (char)Library);
    if ( *a2 )
    {
LABEL_9:
      v8 = 0;
    }
    else
    {
      v8 = -1073741515;
      if ( GetLastError() != 126 )
        v8 = -1073741701;
      DebugTraceError(v8, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", 1224);
    }
  }
  if ( v7 )
    MSCryptFree(v7);
  return v8;
}

```

## disassembly

```asm
0x180008a90  mov     [rsp-18h+arg_8], rbx
0x180008a95  mov     [rsp-18h+arg_10], rsi
0x180008a9a  push    rbp
0x180008a9b  push    rdi
0x180008a9c  push    r14
0x180008a9e  mov     rbp, rsp
0x180008aa1  sub     rsp, 60h
0x180008aa5  mov     rdi, rdx
0x180008aa8  mov     qword ptr [rbp+String2.Length], 160014h
0x180008ab0  mov     rdx, [rcx+28h]
0x180008ab4  lea     rax, aNcryptDll_0; "ncrypt.dll"
0x180008abb  xorps   xmm0, xmm0
0x180008abe  mov     [rbp+String2.Buffer], rax
0x180008ac2  mov     r14, rcx
0x180008ac5  mov     [rbp+lpLibFileName], 0
0x180008acd  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180008ad1  mov     rdx, [rdx]; SourceString
0x180008ad4  lea     rcx, [rbp+DestinationString]; DestinationString
0x180008ad8  call    cs:__imp_RtlInitUnicodeString
0x180008ade  lea     rdx, [rbp+lpLibFileName]
0x180008ae2  lea     rcx, [rbp+DestinationString]
0x180008ae6  call    _GetImagePath
0x180008aeb  mov     rsi, [rbp+lpLibFileName]
0x180008aef  mov     ebx, eax
0x180008af1  test    eax, eax
0x180008af3  js      loc_180008B8E
0x180008af9  mov     r8b, 1; CaseInsensitive
0x180008afc  mov     qword ptr [rdi], 0
0x180008b03  lea     rdx, [rbp+String2]; String2
0x180008b07  lea     rcx, [rbp+DestinationString]; String1
0x180008b0b  call    cs:__imp_RtlCompareUnicodeString
0x180008b11  test    eax, eax
0x180008b13  jz      loc_180008BD1
0x180008b19  cmp     qword ptr [rdi], 0
0x180008b1d  jnz     short loc_180008B68
0x180008b1f  xor     r8d, r8d; dwFlags
0x180008b22  xor     edx, edx; hFile
0x180008b24  mov     rcx, rsi; lpLibFileName
0x180008b27  call    cs:__imp_LoadLibraryExW
0x180008b2d  mov     rdx, rax
0x180008b30  mov     [rdi], rax
0x180008b33  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b3a  lea     rax, WPP_GLOBAL_Control
0x180008b41  cmp     rcx, rax
0x180008b44  jz      short loc_180008B62
0x180008b46  test    byte ptr [rcx+1Ch], 20h
0x180008b4a  jz      short loc_180008B62
0x180008b4c  mov     rcx, [rcx+10h]
0x180008b50  mov     r9, r14
0x180008b53  mov     [rsp+60h+var_38], rdx
0x180008b58  mov     [rsp+60h+var_40], rsi
0x180008b5d  call    WPP_SF_qSq
0x180008b62  cmp     qword ptr [rdi], 0
0x180008b66  jz      short loc_180008BE0
0x180008b68  xor     ebx, ebx
0x180008b6a  test    rsi, rsi
0x180008b6d  jz      short loc_180008B77
0x180008b6f  mov     rcx, rsi
0x180008b72  call    MSCryptFree
0x180008b77  lea     r11, [rsp+60h+var_s0]
0x180008b7c  mov     eax, ebx
0x180008b7e  mov     rbx, [r11+28h]
0x180008b82  mov     rsi, [r11+30h]
0x180008b86  mov     rsp, r11
0x180008b89  pop     r14
0x180008b8b  pop     rdi
0x180008b8c  pop     rbp
0x180008b8d  retn
0x180008b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b95  lea     rax, WPP_GLOBAL_Control
0x180008b9c  cmp     rcx, rax
0x180008b9f  jz      short loc_180008B6A
0x180008ba1  test    byte ptr [rcx+1Ch], 1
0x180008ba5  jz      short loc_180008B6A
0x180008ba7  mov     rcx, [rcx+10h]
0x180008bab  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008bb2  mov     [rsp+60h+var_30], 4ABh
0x180008bba  lea     r9, aSresult; "sResult"
0x180008bc1  mov     [rsp+60h+var_38], r8
0x180008bc6  mov     dword ptr [rsp+60h+var_40], ebx
0x180008bca  call    WPP_SF_sDsd
0x180008bcf  jmp     short loc_180008B6A
0x180008bd1  mov     rax, cs:g_hInstance
0x180008bd8  mov     [rdi], rax
0x180008bdb  jmp     loc_180008B19
0x180008be0  call    cs:__imp_GetLastError
0x180008be6  mov     ecx, 0C000007Bh
0x180008beb  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008bf2  cmp     eax, 7Eh ; '~'
0x180008bf5  lea     rdx, aSresult; "sResult"
0x180008bfc  mov     ebx, 0C0000135h
0x180008c01  mov     r9d, 4C8h
0x180008c07  cmovnz  ebx, ecx
0x180008c0a  mov     ecx, ebx
0x180008c0c  call    DebugTraceError
0x180008c11  jmp     loc_180008B6A
```
