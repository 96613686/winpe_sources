# ExtractFile(void *,ushort const *,ushort const *,int)

- ea: `0x18000e060`
- end: `0x18000e174`
- name: `?ExtractFile@@YAJPEAXPEBG1H@Z`
- size: `276`
- prototype: `int __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x180014870`
- `0x180014f8c`
- `0x180015530`
- `0x180015930`
- `0x180016560`
- `0x1800170d0`

## callees

- `0x180006014`
- `0x18000e060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e151`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000e080`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000e080`
- `WIMGAPI!WIMExtractImagePath` at `0x18000e0e5`
- `WIMGAPI!WIMExtractImagePath` at `0x18000e0e5`

## string_xrefs

- `0x18000e0c1`: `    File exists and overwrite is disallowed`

## pseudocode

```c
int __fastcall ExtractFile(void *a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  DWORD FileAttributesW; // eax
  int result; // eax
  signed int LastError; // eax
  bool v10; // sf
  signed int v11; // eax
  int v12; // [rsp+20h] [rbp-18h]
  int v13; // [rsp+20h] [rbp-18h]
  int v14; // [rsp+28h] [rbp-10h]
  signed int v15; // [rsp+28h] [rbp-10h]

  if ( a4 || (FileAttributesW = GetFileAttributesW(a3), FileAttributesW == -1) || (FileAttributesW & 0x10) != 0 )
  {
    if ( (unsigned int)WIMExtractImagePath(a1, a2, a3, 0x20000) )
      return 0;
    LastError = GetLastError();
    v10 = LastError < 0;
    if ( LastError > 0 )
      v10 = 1;
    if ( !v10 )
    {
      return 0;
    }
    else
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      v15 = v11;
      v13 = 290;
      ProvPackageLog(
        3,
        L"%hs (%hs:%d) - 0x%08x:",
        "ExtractFile",
        "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
        v13,
        v15);
      ProvPackageLog(3, L"    Failed to extract file");
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    v14 = -2147024816;
    v12 = 285;
    ProvPackageLog(
      3,
      L"%hs (%hs:%d) - 0x%08x:",
      "ExtractFile",
      "onecore\\base\\ntsetup\\provpackageapi\\lib\\helper.cpp",
      v12,
      v14);
    ProvPackageLog(3, L"    File exists and overwrite is disallowed");
    return -2147024816;
  }
  return result;
}

```

## disassembly

```asm
0x18000e060  mov     [rsp+arg_0], rbx
0x18000e065  mov     [rsp+arg_8], rsi
0x18000e06a  push    rdi
0x18000e06b  sub     rsp, 30h
0x18000e06f  mov     rbx, r8
0x18000e072  mov     rdi, rdx
0x18000e075  mov     rsi, rcx
0x18000e078  test    r9d, r9d
0x18000e07b  jnz     short loc_18000E0D6
0x18000e07d  mov     rcx, rbx; lpFileName
0x18000e080  call    cs:__imp_GetFileAttributesW
0x18000e086  cmp     eax, 0FFFFFFFFh
0x18000e089  jz      short loc_18000E0D6
0x18000e08b  test    al, 10h
0x18000e08d  jnz     short loc_18000E0D6
0x18000e08f  mov     edi, 80070050h
0x18000e094  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000e09b  mov     ebx, 3
0x18000e0a0  mov     [rsp+38h+var_10], edi
0x18000e0a4  mov     ecx, ebx
0x18000e0a6  mov     [rsp+38h+var_18], 11Dh
0x18000e0ae  lea     r8, aExtractfile; "ExtractFile"
0x18000e0b5  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000e0bc  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e0c1  lea     rdx, aFileExistsAndO; "    File exists and overwrite is disall"...
0x18000e0c8  mov     ecx, ebx
0x18000e0ca  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e0cf  mov     eax, edi
0x18000e0d1  jmp     loc_18000E164
0x18000e0d6  mov     r9d, 20000h
0x18000e0dc  mov     r8, rbx
0x18000e0df  mov     rdx, rdi
0x18000e0e2  mov     rcx, rsi
0x18000e0e5  call    cs:__imp_WIMExtractImagePath
0x18000e0eb  test    eax, eax
0x18000e0ed  jnz     short loc_18000E162
0x18000e0ef  call    cs:__imp_GetLastError
0x18000e0f5  mov     edi, 80070000h
0x18000e0fa  test    eax, eax
0x18000e0fc  jle     short loc_18000E105
0x18000e0fe  movzx   eax, ax
0x18000e101  or      eax, edi
0x18000e103  test    eax, eax
0x18000e105  jns     short loc_18000E162
0x18000e107  call    cs:__imp_GetLastError
0x18000e10d  test    eax, eax
0x18000e10f  jle     short loc_18000E116
0x18000e111  movzx   eax, ax
0x18000e114  or      eax, edi
0x18000e116  mov     [rsp+38h+var_10], eax
0x18000e11a  lea     r9, aOnecoreBaseNts_8; "onecore\\base\\ntsetup\\provpackageapi"...
0x18000e121  mov     ebx, 3
0x18000e126  mov     [rsp+38h+var_18], 122h
0x18000e12e  mov     ecx, ebx
0x18000e130  lea     r8, aExtractfile; "ExtractFile"
0x18000e137  lea     rdx, aHsHsD0x08x; "%hs (%hs:%d) - 0x%08x:"
0x18000e13e  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e143  lea     rdx, aFailedToExtrac; "    Failed to extract file"
0x18000e14a  mov     ecx, ebx
0x18000e14c  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18000e151  call    cs:__imp_GetLastError
0x18000e157  test    eax, eax
0x18000e159  jle     short loc_18000E164
0x18000e15b  movzx   eax, ax
0x18000e15e  or      eax, edi
0x18000e160  jmp     short loc_18000E164
0x18000e162  xor     eax, eax
0x18000e164  mov     rbx, [rsp+38h+arg_0]
0x18000e169  mov     rsi, [rsp+38h+arg_8]
0x18000e16e  add     rsp, 30h
0x18000e172  pop     rdi
0x18000e173  retn
```
