# GetLocalPDMPath(ushort *,ulong)

- ea: `0x180092b10`
- end: `0x180092bcc`
- name: `?GetLocalPDMPath@@YAJPEAGK@Z`
- size: `188`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180092cf0`

## callees

- `0x180092b10`
- `0x1800936f4`
- `0x180093b44`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180092b28`
- `KERNEL32!GetModuleFileNameW` at `0x180092b28`
- `KERNEL32!GetSystemDirectoryW` at `0x180092b86`
- `KERNEL32!GetSystemDirectoryW` at `0x180092b86`
- `KERNEL32!GetLastError` at `0x180092b58`
- `KERNEL32!GetLastError` at `0x180092bb9`
- `KERNEL32!GetLastError` at `0x180092b58`
- `KERNEL32!GetLastError` at `0x180092bb9`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180092b38`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180092b38`
- `SHLWAPI!PathFileExistsW` at `0x180092b74`
- `SHLWAPI!PathFileExistsW` at `0x180092b74`

## string_xrefs

- `0x180092b42`: `pdm.dll`
- `0x180092b99`: `F12\pdm.dll`
- `0x180092ba5`: `F12\pdm.dll`

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
0x180092b10  mov     [rsp+arg_0], rbx
0x180092b15  push    rdi
0x180092b16  sub     rsp, 30h
0x180092b1a  mov     rdi, rcx
0x180092b1d  mov     rdx, rcx; lpFilename
0x180092b20  xor     ecx, ecx; hModule
0x180092b22  mov     r8d, 104h; nSize
0x180092b28  call    cs:__imp_GetModuleFileNameW
0x180092b2e  cmp     eax, 104h
0x180092b33  jnb     short loc_180092B58
0x180092b35  mov     rcx, rdi; pszPath
0x180092b38  call    cs:__imp_PathRemoveFileSpecW
0x180092b3e  test    eax, eax
0x180092b40  jz      short loc_180092B58
0x180092b42  lea     r9, pszMore; "pdm.dll"
0x180092b49  mov     r8, rdi; pszPathIn
0x180092b4c  mov     rcx, rdi; pszPathOut
0x180092b4f  call    PathCchCombineEx
0x180092b54  mov     ebx, eax
0x180092b56  jmp     short loc_180092B6D
0x180092b58  call    cs:__imp_GetLastError
0x180092b5e  mov     ebx, eax
0x180092b60  test    eax, eax
0x180092b62  jle     short loc_180092B6D
0x180092b64  movzx   ebx, ax
0x180092b67  or      ebx, 80070000h
0x180092b6d  test    ebx, ebx
0x180092b6f  js      short loc_180092B7E
0x180092b71  mov     rcx, rdi; pszPath
0x180092b74  call    cs:__imp_PathFileExistsW
0x180092b7a  test    eax, eax
0x180092b7c  jnz     short loc_180092BBF
0x180092b7e  mov     edx, 104h; uSize
0x180092b83  mov     rcx, rdi; lpBuffer
0x180092b86  call    cs:__imp_GetSystemDirectoryW
0x180092b8c  test    eax, eax
0x180092b8e  js      short loc_180092BB9
0x180092b90  lea     r8, IsBackslash
0x180092b97  xor     edx, edx
0x180092b99  lea     rcx, aF12PdmDll; "F12\\pdm.dll"
0x180092ba0  call    PathIsUnc2
0x180092ba5  lea     r9, aF12PdmDll; "F12\\pdm.dll"
0x180092bac  mov     r8, rdi; pszPathIn
0x180092baf  mov     rcx, rdi; pszPathOut
0x180092bb2  call    PathCchCombineEx
0x180092bb7  jmp     short loc_180092BBF
0x180092bb9  call    cs:__imp_GetLastError
0x180092bbf  mov     eax, ebx
0x180092bc1  mov     rbx, [rsp+38h+arg_0]
0x180092bc6  add     rsp, 30h
0x180092bca  pop     rdi
0x180092bcb  retn
```
