# GetTemporaryFolder(ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> *)

- ea: `0x18000e7b0`
- end: `0x18000e8fe`
- name: `?GetTemporaryFolder@@YAJPEBGPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z`
- size: `334`
- prototype: `signed int __fastcall(__int64, LPCWSTR *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x1800068b8`
- `0x180007f78`

## callees

- `0x180006014`
- `0x18000e4b0`
- `0x18000e7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e81c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e82f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e81c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e82f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e879`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8ac`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000e88f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000e88f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e80d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e80d`

## string_xrefs

- `0x18000e7f5`: `    Failed to get temporary file`
- `0x18000e7e2`: `GetTemporaryFolder`
- `0x18000e858`: `GetTemporaryFolder`
- `0x18000e8d5`: `GetTemporaryFolder`
- `0x18000e86b`: `    Failed to delete temporary file`
- `0x18000e8e8`: `    Failed to create temporary directory`

## pseudocode

```c
signed int __fastcall GetTemporaryFolder(__int64 a1, LPCWSTR *a2)
{
  int TemporaryFile; // eax
  int v4; // edi
  signed int result; // eax
  signed int LastError; // eax
  bool v7; // sf
  signed int v8; // eax
  signed int v9; // eax
  bool v10; // sf
  signed int v11; // eax
  int v12; // [rsp+20h] [rbp-18h]
  int v13; // [rsp+20h] [rbp-18h]
  int v14; // [rsp+20h] [rbp-18h]
  int v15; // [rsp+28h] [rbp-10h]
  signed int v16; // [rsp+28h] [rbp-10h]
  signed int v17; // [rsp+28h] [rbp-10h]

  TemporaryFile = GetTemporaryFile();
  v4 = TemporaryFile;
  if ( TemporaryFile < 0 )
  {
    v15 = TemporaryFile;
    v12 = 262;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "GetTemporaryFolder",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
      v12,
      v15);
    ProvPackageLog(3, L"    Failed to get temporary file");
    return v4;
  }
  if ( DeleteFileW(*a2) )
    goto LABEL_15;
  LastError = GetLastError();
  v7 = LastError < 0;
  if ( LastError > 0 )
    v7 = 1;
  if ( !v7 )
  {
LABEL_15:
    if ( CreateDirectoryW(*a2, 0) )
      return 0;
    v9 = GetLastError();
    v10 = v9 < 0;
    if ( v9 > 0 )
      v10 = 1;
    if ( !v10 )
      return 0;
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    v17 = v11;
    v14 = 268;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "GetTemporaryFolder",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
      v14,
      v17);
    ProvPackageLog(3, L"    Failed to create temporary directory");
  }
  else
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    v16 = v8;
    v13 = 265;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "GetTemporaryFolder",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
      v13,
      v16);
    ProvPackageLog(3, L"    Failed to delete temporary file");
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000e7b0  mov     [rsp+arg_0], rbx
0x18000e7b5  push    rdi
0x18000e7b6  sub     rsp, 30h
0x18000e7ba  mov     rbx, rdx
0x18000e7bd  call    ?GetTemporaryFile@@YAJPEBGPEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; GetTemporaryFile(ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> *)
0x18000e7c2  mov     edi, eax
0x18000e7c4  test    eax, eax
0x18000e7c6  jns     short loc_18000E80A
0x18000e7c8  mov     [rsp+38h+var_10], eax
0x18000e7cc  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000e7d3  mov     ebx, 3
0x18000e7d8  mov     [rsp+38h+var_18], 106h
0x18000e7e0  mov     ecx, ebx
0x18000e7e2  lea     r8, aGettemporaryfo; "GetTemporaryFolder"
0x18000e7e9  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000e7f0  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e7f5  lea     rdx, aFailedToGetTem_0; "    Failed to get temporary file"
0x18000e7fc  mov     ecx, ebx
0x18000e7fe  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e803  mov     eax, edi
0x18000e805  jmp     loc_18000E8F3
0x18000e80a  mov     rcx, [rbx]; lpFileName
0x18000e80d  call    cs:__imp_DeleteFileW
0x18000e813  mov     edi, 80070000h
0x18000e818  test    eax, eax
0x18000e81a  jnz     short loc_18000E88A
0x18000e81c  call    cs:__imp_GetLastError
0x18000e822  test    eax, eax
0x18000e824  jle     short loc_18000E82D
0x18000e826  movzx   eax, ax
0x18000e829  or      eax, edi
0x18000e82b  test    eax, eax
0x18000e82d  jns     short loc_18000E88A
0x18000e82f  call    cs:__imp_GetLastError
0x18000e835  test    eax, eax
0x18000e837  jle     short loc_18000E83E
0x18000e839  movzx   eax, ax
0x18000e83c  or      eax, edi
0x18000e83e  mov     [rsp+38h+var_10], eax
0x18000e842  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000e849  mov     ebx, 3
0x18000e84e  mov     [rsp+38h+var_18], 109h
0x18000e856  mov     ecx, ebx
0x18000e858  lea     r8, aGettemporaryfo; "GetTemporaryFolder"
0x18000e85f  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000e866  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e86b  lea     rdx, aFailedToDelete_1; "    Failed to delete temporary file"
0x18000e872  mov     ecx, ebx
0x18000e874  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e879  call    cs:__imp_GetLastError
0x18000e87f  test    eax, eax
0x18000e881  jle     short loc_18000E8F3
0x18000e883  movzx   eax, ax
0x18000e886  or      eax, edi
0x18000e888  jmp     short loc_18000E8F3
0x18000e88a  mov     rcx, [rbx]; lpPathName
0x18000e88d  xor     edx, edx; lpSecurityAttributes
0x18000e88f  call    cs:__imp_CreateDirectoryW
0x18000e895  test    eax, eax
0x18000e897  jnz     short loc_18000E8F1
0x18000e899  call    cs:__imp_GetLastError
0x18000e89f  test    eax, eax
0x18000e8a1  jle     short loc_18000E8AA
0x18000e8a3  movzx   eax, ax
0x18000e8a6  or      eax, edi
0x18000e8a8  test    eax, eax
0x18000e8aa  jns     short loc_18000E8F1
0x18000e8ac  call    cs:__imp_GetLastError
0x18000e8b2  test    eax, eax
0x18000e8b4  jle     short loc_18000E8BB
0x18000e8b6  movzx   eax, ax
0x18000e8b9  or      eax, edi
0x18000e8bb  mov     [rsp+38h+var_10], eax
0x18000e8bf  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000e8c6  mov     ebx, 3
0x18000e8cb  mov     [rsp+38h+var_18], 10Ch
0x18000e8d3  mov     ecx, ebx
0x18000e8d5  lea     r8, aGettemporaryfo; "GetTemporaryFolder"
0x18000e8dc  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000e8e3  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e8e8  lea     rdx, aFailedToCreate_15; "    Failed to create temporary director"...
0x18000e8ef  jmp     short loc_18000E872
0x18000e8f1  xor     eax, eax
0x18000e8f3  mov     rbx, [rsp+38h+arg_0]
0x18000e8f8  add     rsp, 30h
0x18000e8fc  pop     rdi
0x18000e8fd  retn
```
