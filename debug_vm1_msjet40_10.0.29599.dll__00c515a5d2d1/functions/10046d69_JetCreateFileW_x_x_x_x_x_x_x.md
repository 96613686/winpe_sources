# JetCreateFileW(x,x,x,x,x,x,x)

- ea: `0x10046d69`
- end: `0x10046e15`
- name: `_JetCreateFileW@28`
- size: `172`
- prototype: `int __stdcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, int, DWORD dwCreationDisposition, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10051664`

## callees

- `0x10046833`
- `0x10046864`
- `0x10046d69`
- `0x10123110`
- `0x10124048`
- `0x10124129`
- `0x10124177`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x10046df1`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x10046df1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x10046dc0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x10046dc0`

## pseudocode

```c
HANDLE __stdcall JetCreateFileW(
        LPCWSTR lpFileName,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        struct _SECURITY_ATTRIBUTES *a4,
        DWORD dwCreationDisposition,
        int a6,
        void *a7)
{
  HANDLE FileA; // esi
  _BYTE v9[4]; // [esp+1Ch] [ebp-224h] BYREF
  LPCSTR v10; // [esp+20h] [ebp-220h]
  int v11; // [esp+23Ch] [ebp-4h]

  if ( wrap )
    return CreateFileW(lpFileName, dwDesiredAccess, dwShareMode, a4, dwCreationDisposition, a6 | 0x110000, a7);
  CStrIn::CStrIn((CStrIn *)v9, lpFileName);
  FileA = CreateFileA(v10, dwDesiredAccess, dwShareMode, a4, dwCreationDisposition, a6 | 0x110000, a7);
  v11 = 0;
  CConvertStr::Free((CConvertStr *)v9);
  return FileA;
}

```

## disassembly

```asm
0x10046d69  push    224h
0x10046d6e  mov     eax, offset loc_10124CC9
0x10046d73  call    __EH_prolog3_GS
0x10046d78  mov     ecx, [ebp+arg_C]
0x10046d7b  mov     esi, [ebp+arg_14]
0x10046d7e  mov     edx, [ebp+dwCreationDisposition]
0x10046d81  or      esi, 110000h
0x10046d87  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046d8e  mov     eax, [ebp+lpFileName]
0x10046d91  mov     edi, [ebp+dwDesiredAccess]
0x10046d94  mov     ebx, [ebp+dwShareMode]
0x10046d97  mov     [ebp+lpSecurityAttributes], ecx
0x10046d9d  mov     ecx, [ebp+arg_18]
0x10046da0  mov     [ebp+hTemplateFile], ecx
0x10046da6  mov     ecx, [ebp+lpSecurityAttributes]
0x10046dac  mov     [ebp+var_230], edx
0x10046db2  jz      short loc_10046DCA
0x10046db4  push    [ebp+hTemplateFile]; hTemplateFile
0x10046dba  push    esi; dwFlagsAndAttributes
0x10046dbb  push    edx; dwCreationDisposition
0x10046dbc  push    ecx; lpSecurityAttributes
0x10046dbd  push    ebx; dwShareMode
0x10046dbe  push    edi; dwDesiredAccess
0x10046dbf  push    eax; lpFileName
0x10046dc0  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x10046dc6  mov     esi, eax
0x10046dc8  jmp     short loc_10046E0B
0x10046dca  push    eax; unsigned __int16 *
0x10046dcb  lea     ecx, [ebp+var_224]; this
0x10046dd1  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10046dd6  push    [ebp+hTemplateFile]; hTemplateFile
0x10046ddc  push    esi; dwFlagsAndAttributes
0x10046ddd  push    [ebp+var_230]; dwCreationDisposition
0x10046de3  push    [ebp+lpSecurityAttributes]; lpSecurityAttributes
0x10046de9  push    ebx; dwShareMode
0x10046dea  push    edi; dwDesiredAccess
0x10046deb  push    [ebp+var_220]; lpFileName
0x10046df1  call    ds:__imp__CreateFileA@28; CreateFileA(x,x,x,x,x,x,x)
0x10046df7  mov     esi, eax
0x10046df9  lea     ecx, [ebp+var_224]; this
0x10046dff  mov     [ebp+var_4], 0
0x10046e06  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10046e0b  mov     eax, esi
0x10046e0d  call    __EH_epilog3_GS
0x10046e12  retn    1Ch
0x10124060  jmp     ds:__imp____std_terminate
0x10124cc9  nop
0x10124cca  nop
0x10124ccb  mov     edx, [esp-4+dwDesiredAccess]
0x10124ccf  lea     eax, [edx+0Ch]
0x10124cd2  mov     ecx, [edx-234h]
0x10124cd8  xor     ecx, eax; StackCookie
0x10124cda  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124cdf  mov     ecx, [edx-4]
0x10124ce2  xor     ecx, eax; StackCookie
0x10124ce4  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124ce9  mov     eax, offset stru_10127AA8
0x10124cee  jmp     ___CxxFrameHandler3
```
