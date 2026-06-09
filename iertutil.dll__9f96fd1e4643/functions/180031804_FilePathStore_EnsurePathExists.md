# FilePathStore::_EnsurePathExists

- ea: `0x180031804`
- end: `0x180031897`
- name: `FilePathStore::_EnsurePathExists`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x180030e9c`

## callees

- `0x180031804`
- `0x1800644ac`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003183e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18003183e`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18003182f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18003182f`
- `OLEAUT32!__imp_SysAllocString` at `0x180031813`
- `OLEAUT32!__imp_SysAllocString` at `0x180031813`
- `OLEAUT32!__imp_SysFreeString` at `0x18003184b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003184b`
- `OLEAUT32!__imp_SysStringLen` at `0x180031824`
- `OLEAUT32!__imp_SysStringLen` at `0x180031824`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x180031866`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x180031866`

## pseudocode

```c
__int64 __fastcall FilePathStore::_EnsurePathExists(const OLECHAR *a1)
{
  OLECHAR *v1; // rax
  int v2; // ecx
  WCHAR *v3; // rbx
  UINT v4; // eax
  int v5; // edi
  int v7; // eax

  if ( a1 )
  {
    v1 = SysAllocString(a1);
    v3 = v1;
    if ( !v1 )
      ATL::AtlThrowImpl(v2);
    v4 = SysStringLen(v1);
    v5 = PathCchRemoveFileSpec(v3, v4);
    if ( v5 >= 0 && !PathFileExistsW(v3) )
    {
      v7 = SHCreateDirectoryExW(0, v3, 0);
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      if ( v5 == -2147024713 )
        v5 = 0;
    }
  }
  else
  {
    v3 = 0;
    v5 = -2147024882;
  }
  SysFreeString(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180031804  mov     [rsp+arg_0], rbx
0x180031809  push    rdi
0x18003180a  sub     rsp, 20h
0x18003180e  test    rcx, rcx
0x180031811  jz      short loc_180031888
0x180031813  call    cs:__imp_SysAllocString
0x180031819  mov     rbx, rax
0x18003181c  test    rax, rax
0x18003181f  jz      short loc_180031891
0x180031821  mov     rcx, rax; pbstr
0x180031824  call    cs:__imp_SysStringLen
0x18003182a  mov     edx, eax; cchPath
0x18003182c  mov     rcx, rbx; pszPath
0x18003182f  call    cs:__imp_PathCchRemoveFileSpec
0x180031835  mov     edi, eax
0x180031837  test    eax, eax
0x180031839  js      short loc_180031848
0x18003183b  mov     rcx, rbx; pszPath
0x18003183e  call    cs:__imp_PathFileExistsW
0x180031844  test    eax, eax
0x180031846  jz      short loc_18003185E
0x180031848  mov     rcx, rbx; bstrString
0x18003184b  call    cs:__imp_SysFreeString
0x180031851  mov     rbx, [rsp+28h+arg_0]
0x180031856  mov     eax, edi
0x180031858  add     rsp, 20h
0x18003185c  pop     rdi
0x18003185d  retn
0x18003185e  xor     r8d, r8d; psa
0x180031861  mov     rdx, rbx; pszPath
0x180031864  xor     ecx, ecx; hwnd
0x180031866  call    cs:__imp_SHCreateDirectoryExW
0x18003186c  mov     edi, eax
0x18003186e  test    eax, eax
0x180031870  jle     short loc_18003187B
0x180031872  movzx   edi, ax
0x180031875  or      edi, 80070000h
0x18003187b  xor     eax, eax
0x18003187d  cmp     edi, 800700B7h
0x180031883  cmovz   edi, eax
0x180031886  jmp     short loc_180031848
0x180031888  xor     ebx, ebx
0x18003188a  mov     edi, 8007000Eh
0x18003188f  jmp     short loc_180031848
0x180031891  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
