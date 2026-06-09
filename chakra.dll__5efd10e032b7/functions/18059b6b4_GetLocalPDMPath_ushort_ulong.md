# GetLocalPDMPath(ushort *,ulong)

- ea: `0x18059b6b4`
- end: `0x18059b79e`
- name: `?GetLocalPDMPath@@YAJPEAGK@Z`
- size: `234`
- prototype: `__int64 __fastcall(PWSTR pszPath, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18059b8f8`

## callees

- `0x18059b6b4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18059b6db`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18059b6db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18059b71d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18059b77f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18059b71d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18059b77f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18059b754`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18059b754`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18059b6ee`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18059b6ee`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18059b73f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18059b73f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18059b70d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18059b70d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18059b771`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18059b771`

## string_xrefs

- `0x18059b764`: `F12\pdm.dll`
- `0x18059b6fe`: `pdm.dll`

## pseudocode

```c
__int64 __fastcall GetLocalPDMPath(PWSTR pszPath)
{
  int v2; // ebx
  signed int LastError; // eax

  if ( GetModuleFileNameW(0, pszPath, 0x104u) < 0x104 && PathRemoveFileSpecW(pszPath) )
  {
    v2 = PathCchCombine(pszPath, 0x104u, pszPath, L"pdm.dll");
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v2 < 0 || !PathFileExistsW(pszPath) )
  {
    if ( (GetSystemDirectoryW(pszPath, 0x104u) & 0x80000000) != 0 )
      GetLastError();
    else
      PathCchAppend(pszPath, 0x104u, L"F12\\pdm.dll");
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18059b6b4  mov     rax, rsp
0x18059b6b7  mov     [rax+18h], rbx
0x18059b6bb  mov     [rax+20h], rsi
0x18059b6bf  mov     [rax+10h], edx
0x18059b6c2  mov     [rax+8], rcx
0x18059b6c6  push    rdi
0x18059b6c7  sub     rsp, 20h
0x18059b6cb  mov     rdi, rcx
0x18059b6ce  mov     rdx, rcx; lpFilename
0x18059b6d1  mov     esi, 104h
0x18059b6d6  xor     ecx, ecx; hModule
0x18059b6d8  mov     r8d, esi; nSize
0x18059b6db  call    cs:__imp_GetModuleFileNameW
0x18059b6e2  nop     dword ptr [rax+rax+00h]
0x18059b6e7  cmp     eax, esi
0x18059b6e9  jnb     short loc_18059B71D
0x18059b6eb  mov     rcx, rdi; pszPath
0x18059b6ee  call    cs:__imp_PathRemoveFileSpecW
0x18059b6f5  nop     dword ptr [rax+rax+00h]
0x18059b6fa  test    eax, eax
0x18059b6fc  jz      short loc_18059B71D
0x18059b6fe  lea     r9, pszMore; "pdm.dll"
0x18059b705  mov     r8, rdi; pszPathIn
0x18059b708  mov     edx, esi; cchPathOut
0x18059b70a  mov     rcx, rdi; pszPathOut
0x18059b70d  call    cs:__imp_PathCchCombine
0x18059b714  nop     dword ptr [rax+rax+00h]
0x18059b719  mov     ebx, eax
0x18059b71b  jmp     short loc_18059B738
0x18059b71d  call    cs:__imp_GetLastError
0x18059b724  nop     dword ptr [rax+rax+00h]
0x18059b729  mov     ebx, eax
0x18059b72b  test    eax, eax
0x18059b72d  jle     short loc_18059B738
0x18059b72f  movzx   ebx, ax
0x18059b732  or      ebx, 80070000h
0x18059b738  test    ebx, ebx
0x18059b73a  js      short loc_18059B74F
0x18059b73c  mov     rcx, rdi; pszPath
0x18059b73f  call    cs:__imp_PathFileExistsW
0x18059b746  nop     dword ptr [rax+rax+00h]
0x18059b74b  test    eax, eax
0x18059b74d  jnz     short loc_18059B78B
0x18059b74f  mov     edx, esi; uSize
0x18059b751  mov     rcx, rdi; lpBuffer
0x18059b754  call    cs:__imp_GetSystemDirectoryW
0x18059b75b  nop     dword ptr [rax+rax+00h]
0x18059b760  test    eax, eax
0x18059b762  js      short loc_18059B77F
0x18059b764  lea     r8, aF12PdmDll; "F12\\pdm.dll"
0x18059b76b  mov     rdx, rsi; cchPath
0x18059b76e  mov     rcx, rdi; pszPath
0x18059b771  call    cs:__imp_PathCchAppend
0x18059b778  nop     dword ptr [rax+rax+00h]
0x18059b77d  jmp     short loc_18059B78B
0x18059b77f  call    cs:__imp_GetLastError
0x18059b786  nop     dword ptr [rax+rax+00h]
0x18059b78b  mov     rsi, [rsp+28h+arg_18]
0x18059b790  mov     eax, ebx
0x18059b792  mov     rbx, [rsp+28h+arg_10]
0x18059b797  add     rsp, 20h
0x18059b79b  pop     rdi
0x18059b79c  retn
```
