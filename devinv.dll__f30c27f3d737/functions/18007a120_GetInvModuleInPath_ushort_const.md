# GetInvModuleInPath(ushort const *)

- ea: `0x18007a120`
- end: `0x18007a248`
- name: `?GetInvModuleInPath@@YAJPEBG@Z`
- size: `296`
- prototype: `__int64 __fastcall(LPCWSTR pszFile2)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002a500`
- `0x180079de0`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x180066c10`
- `0x18007a120`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007a1a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007a1a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18007a16a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18007a16a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a1b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a1ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a1b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a1ee`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCommonPrefixW` at `0x18007a1cf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCommonPrefixW` at `0x18007a1cf`

## string_xrefs

- `0x18007a210`: `GetInvModuleInPath`

## pseudocode

```c
__int64 __fastcall GetInvModuleInPath(LPCWSTR pszFile2)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 v5; // r8
  DWORD ModuleFileNameW; // eax
  int v7; // eax
  __int64 v8; // rcx
  signed int v9; // eax
  unsigned int v11; // [rsp+20h] [rbp-248h]
  HMODULE phModule; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(Filename, 0, 0x208u);
  phModule = 0;
  if ( !GetModuleHandleExW(6u, (LPCWSTR)GetInvModuleInPath, &phModule) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v4 = "GetModuleHandleEx failed %#x";
    v5 = 387;
LABEL_14:
    v11 = v3;
    AslLogCallPrintf(1, "GetInvModuleInPath", v5, v4, v11);
    return v3;
  }
  ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x104u);
  if ( !ModuleFileNameW || ModuleFileNameW >= 0x104 && GetLastError() == 122 )
  {
    v9 = GetLastError();
    v3 = v9;
    if ( v9 > 0 )
      v3 = (unsigned __int16)v9 | 0x80070000;
    v4 = "GetModuleFileName failed %#x";
    v5 = 396;
    goto LABEL_14;
  }
  v7 = PathCommonPrefixW(Filename, pszFile2, 0);
  v8 = -1;
  do
    ++v8;
  while ( pszFile2[v8] );
  return v7 != v8;
}

```

## disassembly

```asm
0x18007a120  mov     [rsp+arg_8], rbx
0x18007a125  push    rdi
0x18007a126  sub     rsp, 260h
0x18007a12d  mov     rax, cs:__security_cookie
0x18007a134  xor     rax, rsp
0x18007a137  mov     [rsp+268h+var_18], rax
0x18007a13f  mov     rbx, rcx
0x18007a142  xor     edx, edx; Val
0x18007a144  lea     rcx, [rsp+268h+Filename]; void *
0x18007a149  mov     r8d, 208h; Size
0x18007a14f  call    memset_0
0x18007a154  xor     edi, edi
0x18007a156  lea     r8, [rsp+268h+phModule]; phModule
0x18007a15b  lea     rdx, ?GetInvModuleInPath@@YAJPEBG@Z; lpModuleName
0x18007a162  mov     [rsp+268h+phModule], rdi
0x18007a167  lea     ecx, [rdi+6]; dwFlags
0x18007a16a  call    cs:__imp_GetModuleHandleExW
0x18007a170  test    eax, eax
0x18007a172  jnz     short loc_18007A198
0x18007a174  call    cs:__imp_GetLastError
0x18007a17a  mov     ebx, eax
0x18007a17c  test    eax, eax
0x18007a17e  jle     short loc_18007A189
0x18007a180  movzx   ebx, ax
0x18007a183  or      ebx, 80070000h
0x18007a189  lea     r9, aGetmodulehandl_0; "GetModuleHandleEx failed %#x"
0x18007a190  mov     r8d, 183h
0x18007a196  jmp     short loc_18007A210
0x18007a198  mov     rcx, [rsp+268h+phModule]; hModule
0x18007a19d  lea     rdx, [rsp+268h+Filename]; lpFilename
0x18007a1a2  mov     r8d, 104h; nSize
0x18007a1a8  call    cs:__imp_GetModuleFileNameW
0x18007a1ae  test    eax, eax
0x18007a1b0  jz      short loc_18007A1EE
0x18007a1b2  cmp     eax, 104h
0x18007a1b7  jb      short loc_18007A1C4
0x18007a1b9  call    cs:__imp_GetLastError
0x18007a1bf  cmp     eax, 7Ah ; 'z'
0x18007a1c2  jz      short loc_18007A1EE
0x18007a1c4  xor     r8d, r8d; achPath
0x18007a1c7  lea     rcx, [rsp+268h+Filename]; pszFile1
0x18007a1cc  mov     rdx, rbx; pszFile2
0x18007a1cf  call    cs:__imp_PathCommonPrefixW
0x18007a1d5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007a1d9  inc     rcx
0x18007a1dc  cmp     [rbx+rcx*2], di
0x18007a1e0  jnz     short loc_18007A1D9
0x18007a1e2  mov     eax, eax
0x18007a1e4  mov     ebx, edi
0x18007a1e6  cmp     rax, rcx
0x18007a1e9  setnz   bl
0x18007a1ec  jmp     short loc_18007A225
0x18007a1ee  call    cs:__imp_GetLastError
0x18007a1f4  mov     ebx, eax
0x18007a1f6  test    eax, eax
0x18007a1f8  jle     short loc_18007A203
0x18007a1fa  movzx   ebx, ax
0x18007a1fd  or      ebx, 80070000h
0x18007a203  lea     r9, aGetmodulefilen; "GetModuleFileName failed %#x"
0x18007a20a  mov     r8d, 18Ch
0x18007a210  lea     rdx, aGetinvmodulein_0; "GetInvModuleInPath"
0x18007a217  mov     [rsp+268h+var_248], ebx
0x18007a21b  mov     ecx, 1
0x18007a220  call    AslLogCallPrintf
0x18007a225  mov     eax, ebx
0x18007a227  mov     rcx, [rsp+268h+var_18]
0x18007a22f  xor     rcx, rsp; StackCookie
0x18007a232  call    __security_check_cookie
0x18007a237  mov     rbx, [rsp+268h+arg_8]
0x18007a23f  add     rsp, 260h
0x18007a246  pop     rdi
0x18007a247  retn
```
