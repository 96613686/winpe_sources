# JetCreateFileW(x,x,x,x,x,x,x)

- ea: `0x10032deb`
- end: `0x10032ea2`
- name: `_JetCreateFileW@28`
- size: `183`
- prototype: `int __stdcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, int, DWORD dwCreationDisposition, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100268d8`
- `0x10026925`

## callees

- `0x10032925`
- `0x10032956`
- `0x10032deb`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x10032e7c`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x10032e7c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x10032e4b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x10032e4b`

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
  _BYTE v9[4]; // [esp+18h] [ebp-218h] BYREF
  LPCSTR v10; // [esp+1Ch] [ebp-214h]

  if ( wrap )
    return CreateFileW(lpFileName, dwDesiredAccess, dwShareMode, a4, dwCreationDisposition, a6 | 0x110000, a7);
  CStrIn::CStrIn((CStrIn *)v9, lpFileName);
  FileA = CreateFileA(v10, dwDesiredAccess, dwShareMode, a4, dwCreationDisposition, a6 | 0x110000, a7);
  CConvertStr::Free((CConvertStr *)v9);
  return FileA;
}

```

## disassembly

```asm
0x10032deb  mov     edi, edi
0x10032ded  push    ebp
0x10032dee  mov     ebp, esp
0x10032df0  sub     esp, 224h
0x10032df6  mov     eax, ___security_cookie
0x10032dfb  xor     eax, ebp
0x10032dfd  mov     [ebp+var_4], eax
0x10032e00  mov     ecx, [ebp+arg_C]
0x10032e03  mov     edx, [ebp+dwCreationDisposition]
0x10032e06  mov     eax, [ebp+lpFileName]
0x10032e09  push    ebx
0x10032e0a  mov     ebx, [ebp+dwShareMode]
0x10032e0d  push    esi
0x10032e0e  mov     esi, [ebp+arg_14]
0x10032e11  mov     [ebp+lpSecurityAttributes], ecx
0x10032e17  or      esi, 110000h
0x10032e1d  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10032e24  mov     ecx, [ebp+arg_18]
0x10032e27  push    edi
0x10032e28  mov     edi, [ebp+dwDesiredAccess]
0x10032e2b  mov     [ebp+hTemplateFile], ecx
0x10032e31  mov     ecx, [ebp+lpSecurityAttributes]
0x10032e37  mov     [ebp+var_224], edx
0x10032e3d  jz      short loc_10032E55
0x10032e3f  push    [ebp+hTemplateFile]; hTemplateFile
0x10032e45  push    esi; dwFlagsAndAttributes
0x10032e46  push    edx; dwCreationDisposition
0x10032e47  push    ecx; lpSecurityAttributes
0x10032e48  push    ebx; dwShareMode
0x10032e49  push    edi; dwDesiredAccess
0x10032e4a  push    eax; lpFileName
0x10032e4b  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x10032e51  mov     esi, eax
0x10032e53  jmp     short loc_10032E8F
0x10032e55  push    eax; unsigned __int16 *
0x10032e56  lea     ecx, [ebp+var_218]; this
0x10032e5c  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10032e61  push    [ebp+hTemplateFile]; hTemplateFile
0x10032e67  push    esi; dwFlagsAndAttributes
0x10032e68  push    [ebp+var_224]; dwCreationDisposition
0x10032e6e  push    [ebp+lpSecurityAttributes]; lpSecurityAttributes
0x10032e74  push    ebx; dwShareMode
0x10032e75  push    edi; dwDesiredAccess
0x10032e76  push    [ebp+var_214]; lpFileName
0x10032e7c  call    ds:__imp__CreateFileA@28; CreateFileA(x,x,x,x,x,x,x)
0x10032e82  lea     ecx, [ebp+var_218]; this
0x10032e88  mov     esi, eax
0x10032e8a  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10032e8f  mov     ecx, [ebp+var_4]
0x10032e92  mov     eax, esi
0x10032e94  pop     edi
0x10032e95  pop     esi
0x10032e96  xor     ecx, ebp; StackCookie
0x10032e98  pop     ebx
0x10032e99  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032e9e  leave
0x10032e9f  retn    1Ch
```
