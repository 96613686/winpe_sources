# GetLocalPDMPath(ushort *,ulong)

- ea: `0x180256820`
- end: `0x18025690a`
- name: `?GetLocalPDMPath@@YAJPEAGK@Z`
- size: `234`
- prototype: `__int64 __fastcall(WCHAR *pszPathIn)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180256a64`

## callees

- `0x180256820`
- `0x180344e58`
- `0x1803453e8`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveFileSpecW` at `0x180256857`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveFileSpecW` at `0x180256857`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18025689f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18025689f`
- `KERNEL32!GetSystemDirectoryW` at `0x1802568b7`
- `KERNEL32!GetSystemDirectoryW` at `0x1802568b7`
- `KERNEL32!GetModuleFileNameW` at `0x180256841`
- `KERNEL32!GetModuleFileNameW` at `0x180256841`
- `KERNEL32!GetLastError` at `0x18025687d`
- `KERNEL32!GetLastError` at `0x1802568f0`
- `KERNEL32!GetLastError` at `0x18025687d`
- `KERNEL32!GetLastError` at `0x1802568f0`

## string_xrefs

- `0x180256867`: `pdm.dll`
- `0x1802568d0`: `F12\pdm.dll`
- `0x1802568dc`: `F12\pdm.dll`

## pseudocode

```c
__int64 __fastcall GetLocalPDMPath(WCHAR *pszPathIn)
{
  size_t v2; // rdx
  int v3; // ebx
  signed int LastError; // eax
  size_t v5; // rdx
  ULONG v7; // [rsp+20h] [rbp-18h]

  if ( GetModuleFileNameW(0, pszPathIn, 0x104u) < 0x104 && PathRemoveFileSpecW(pszPathIn) )
  {
    v3 = PathCchCombineEx(pszPathIn, v2, pszPathIn, L"pdm.dll", v7);
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v3 < 0 || !PathFileExistsW(pszPathIn) )
  {
    if ( (GetSystemDirectoryW(pszPathIn, 0x104u) & 0x80000000) != 0 )
    {
      GetLastError();
    }
    else
    {
      PathIsUnc2(L"F12\\pdm.dll", 0, (unsigned __int8 (__fastcall *)(_QWORD))IsBackslash);
      PathCchCombineEx(pszPathIn, v5, pszPathIn, L"F12\\pdm.dll", v7);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180256820  mov     rax, rsp
0x180256823  mov     [rax+18h], rbx
0x180256827  mov     [rax+10h], edx
0x18025682a  mov     [rax+8], rcx
0x18025682e  push    rdi
0x18025682f  sub     rsp, 30h
0x180256833  mov     rdi, rcx
0x180256836  mov     rdx, rcx; lpFilename
0x180256839  xor     ecx, ecx; hModule
0x18025683b  mov     r8d, 104h; nSize
0x180256841  call    cs:__imp_GetModuleFileNameW
0x180256848  nop     dword ptr [rax+rax+00h]
0x18025684d  cmp     eax, 104h
0x180256852  jnb     short loc_18025687D
0x180256854  mov     rcx, rdi; pszPath
0x180256857  call    cs:__imp_PathRemoveFileSpecW
0x18025685e  nop     dword ptr [rax+rax+00h]
0x180256863  test    eax, eax
0x180256865  jz      short loc_18025687D
0x180256867  lea     r9, pszMore; "pdm.dll"
0x18025686e  mov     r8, rdi; pszPathIn
0x180256871  mov     rcx, rdi; pszPathOut
0x180256874  call    PathCchCombineEx
0x180256879  mov     ebx, eax
0x18025687b  jmp     short loc_180256898
0x18025687d  call    cs:__imp_GetLastError
0x180256884  nop     dword ptr [rax+rax+00h]
0x180256889  mov     ebx, eax
0x18025688b  test    eax, eax
0x18025688d  jle     short loc_180256898
0x18025688f  movzx   ebx, ax
0x180256892  or      ebx, 80070000h
0x180256898  test    ebx, ebx
0x18025689a  js      short loc_1802568AF
0x18025689c  mov     rcx, rdi; pszPath
0x18025689f  call    cs:__imp_PathFileExistsW
0x1802568a6  nop     dword ptr [rax+rax+00h]
0x1802568ab  test    eax, eax
0x1802568ad  jnz     short loc_1802568FC
0x1802568af  mov     edx, 104h; uSize
0x1802568b4  mov     rcx, rdi; lpBuffer
0x1802568b7  call    cs:__imp_GetSystemDirectoryW
0x1802568be  nop     dword ptr [rax+rax+00h]
0x1802568c3  test    eax, eax
0x1802568c5  js      short loc_1802568F0
0x1802568c7  lea     r8, IsBackslash
0x1802568ce  xor     edx, edx
0x1802568d0  lea     rcx, aF12PdmDll; "F12\\pdm.dll"
0x1802568d7  call    PathIsUnc2
0x1802568dc  lea     r9, aF12PdmDll; "F12\\pdm.dll"
0x1802568e3  mov     r8, rdi; pszPathIn
0x1802568e6  mov     rcx, rdi; pszPathOut
0x1802568e9  call    PathCchCombineEx
0x1802568ee  jmp     short loc_1802568FC
0x1802568f0  call    cs:__imp_GetLastError
0x1802568f7  nop     dword ptr [rax+rax+00h]
0x1802568fc  mov     eax, ebx
0x1802568fe  mov     rbx, [rsp+38h+arg_10]
0x180256903  add     rsp, 30h
0x180256907  pop     rdi
0x180256908  retn
```
