# GetLocalPDMPath(ushort *,ulong)

- ea: `0x180094e60`
- end: `0x180094f41`
- name: `?GetLocalPDMPath@@YAJPEAGK@Z`
- size: `225`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180095084`

## callees

- `0x180094e60`
- `0x180095ac8`
- `0x180095f20`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180094e78`
- `KERNEL32!GetModuleFileNameW` at `0x180094e78`
- `KERNEL32!GetSystemDirectoryW` at `0x180094eee`
- `KERNEL32!GetSystemDirectoryW` at `0x180094eee`
- `KERNEL32!GetLastError` at `0x180094eb4`
- `KERNEL32!GetLastError` at `0x180094f27`
- `KERNEL32!GetLastError` at `0x180094eb4`
- `KERNEL32!GetLastError` at `0x180094f27`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180094e8e`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180094e8e`
- `SHLWAPI!PathFileExistsW` at `0x180094ed6`
- `SHLWAPI!PathFileExistsW` at `0x180094ed6`

## string_xrefs

- `0x180094f07`: `F12\pdm.dll`
- `0x180094f13`: `F12\pdm.dll`
- `0x180094e9e`: `pdm.dll`

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
      PathIsUnc2(L"F12\\pdm.dll");
      PathCchCombineEx(pszPathIn, v5, pszPathIn, L"F12\\pdm.dll", v7);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180094e60  mov     [rsp+arg_0], rbx
0x180094e65  push    rdi
0x180094e66  sub     rsp, 30h
0x180094e6a  mov     rdi, rcx
0x180094e6d  mov     rdx, rcx; lpFilename
0x180094e70  xor     ecx, ecx; hModule
0x180094e72  mov     r8d, 104h; nSize
0x180094e78  call    cs:__imp_GetModuleFileNameW
0x180094e7f  nop     dword ptr [rax+rax+00h]
0x180094e84  cmp     eax, 104h
0x180094e89  jnb     short loc_180094EB4
0x180094e8b  mov     rcx, rdi; pszPath
0x180094e8e  call    cs:__imp_PathRemoveFileSpecW
0x180094e95  nop     dword ptr [rax+rax+00h]
0x180094e9a  test    eax, eax
0x180094e9c  jz      short loc_180094EB4
0x180094e9e  lea     r9, pszMore; "pdm.dll"
0x180094ea5  mov     r8, rdi; pszPathIn
0x180094ea8  mov     rcx, rdi; pszPathOut
0x180094eab  call    PathCchCombineEx
0x180094eb0  mov     ebx, eax
0x180094eb2  jmp     short loc_180094ECF
0x180094eb4  call    cs:__imp_GetLastError
0x180094ebb  nop     dword ptr [rax+rax+00h]
0x180094ec0  mov     ebx, eax
0x180094ec2  test    eax, eax
0x180094ec4  jle     short loc_180094ECF
0x180094ec6  movzx   ebx, ax
0x180094ec9  or      ebx, 80070000h
0x180094ecf  test    ebx, ebx
0x180094ed1  js      short loc_180094EE6
0x180094ed3  mov     rcx, rdi; pszPath
0x180094ed6  call    cs:__imp_PathFileExistsW
0x180094edd  nop     dword ptr [rax+rax+00h]
0x180094ee2  test    eax, eax
0x180094ee4  jnz     short loc_180094F33
0x180094ee6  mov     edx, 104h; uSize
0x180094eeb  mov     rcx, rdi; lpBuffer
0x180094eee  call    cs:__imp_GetSystemDirectoryW
0x180094ef5  nop     dword ptr [rax+rax+00h]
0x180094efa  test    eax, eax
0x180094efc  js      short loc_180094F27
0x180094efe  lea     r8, IsBackslash
0x180094f05  xor     edx, edx
0x180094f07  lea     rcx, aF12PdmDll; "F12\\pdm.dll"
0x180094f0e  call    PathIsUnc2
0x180094f13  lea     r9, aF12PdmDll; "F12\\pdm.dll"
0x180094f1a  mov     r8, rdi; pszPathIn
0x180094f1d  mov     rcx, rdi; pszPathOut
0x180094f20  call    PathCchCombineEx
0x180094f25  jmp     short loc_180094F33
0x180094f27  call    cs:__imp_GetLastError
0x180094f2e  nop     dword ptr [rax+rax+00h]
0x180094f33  mov     eax, ebx
0x180094f35  mov     rbx, [rsp+38h+arg_0]
0x180094f3a  add     rsp, 30h
0x180094f3e  pop     rdi
0x180094f3f  retn
```
