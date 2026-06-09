# JetCreateFileW(x,x,x,x,x,x,x)

- ea: `0x10046be9`
- end: `0x10046c95`
- name: `_JetCreateFileW@28`
- size: `172`
- prototype: `int __stdcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, int, DWORD dwCreationDisposition, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100514d4`

## callees

- `0x100466b3`
- `0x100466e4`
- `0x10046be9`
- `0x10122f60`
- `0x10123e98`
- `0x10123f79`
- `0x10123fc7`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x10046c71`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x10046c71`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x10046c40`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x10046c40`

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
0x10046be9  push    224h
0x10046bee  mov     eax, offset loc_10124B19
0x10046bf3  call    __EH_prolog3_GS
0x10046bf8  mov     ecx, [ebp+arg_C]
0x10046bfb  mov     esi, [ebp+arg_14]
0x10046bfe  mov     edx, [ebp+dwCreationDisposition]
0x10046c01  or      esi, 110000h
0x10046c07  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10046c0e  mov     eax, [ebp+lpFileName]
0x10046c11  mov     edi, [ebp+dwDesiredAccess]
0x10046c14  mov     ebx, [ebp+dwShareMode]
0x10046c17  mov     [ebp+lpSecurityAttributes], ecx
0x10046c1d  mov     ecx, [ebp+arg_18]
0x10046c20  mov     [ebp+hTemplateFile], ecx
0x10046c26  mov     ecx, [ebp+lpSecurityAttributes]
0x10046c2c  mov     [ebp+var_230], edx
0x10046c32  jz      short loc_10046C4A
0x10046c34  push    [ebp+hTemplateFile]; hTemplateFile
0x10046c3a  push    esi; dwFlagsAndAttributes
0x10046c3b  push    edx; dwCreationDisposition
0x10046c3c  push    ecx; lpSecurityAttributes
0x10046c3d  push    ebx; dwShareMode
0x10046c3e  push    edi; dwDesiredAccess
0x10046c3f  push    eax; lpFileName
0x10046c40  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x10046c46  mov     esi, eax
0x10046c48  jmp     short loc_10046C8B
0x10046c4a  push    eax; unsigned __int16 *
0x10046c4b  lea     ecx, [ebp+var_224]; this
0x10046c51  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10046c56  push    [ebp+hTemplateFile]; hTemplateFile
0x10046c5c  push    esi; dwFlagsAndAttributes
0x10046c5d  push    [ebp+var_230]; dwCreationDisposition
0x10046c63  push    [ebp+lpSecurityAttributes]; lpSecurityAttributes
0x10046c69  push    ebx; dwShareMode
0x10046c6a  push    edi; dwDesiredAccess
0x10046c6b  push    [ebp+var_220]; lpFileName
0x10046c71  call    ds:__imp__CreateFileA@28; CreateFileA(x,x,x,x,x,x,x)
0x10046c77  mov     esi, eax
0x10046c79  lea     ecx, [ebp+var_224]; this
0x10046c7f  mov     [ebp+var_4], 0
0x10046c86  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10046c8b  mov     eax, esi
0x10046c8d  call    __EH_epilog3_GS
0x10046c92  retn    1Ch
0x10123eb0  jmp     ds:__imp____std_terminate
0x10124b19  nop
0x10124b1a  nop
0x10124b1b  mov     edx, [esp-4+dwDesiredAccess]
0x10124b1f  lea     eax, [edx+0Ch]
0x10124b22  mov     ecx, [edx-234h]
0x10124b28  xor     ecx, eax; StackCookie
0x10124b2a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124b2f  mov     ecx, [edx-4]
0x10124b32  xor     ecx, eax; StackCookie
0x10124b34  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124b39  mov     eax, offset stru_101278F8
0x10124b3e  jmp     ___CxxFrameHandler3
```
