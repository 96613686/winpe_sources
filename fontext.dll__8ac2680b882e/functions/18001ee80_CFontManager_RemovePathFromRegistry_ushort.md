# CFontManager::_RemovePathFromRegistry(ushort *)

- ea: `0x18001ee80`
- end: `0x18001f09a`
- name: `?_RemovePathFromRegistry@CFontManager@@AEAAXPEAG@Z`
- size: `538`
- prototype: `void(CFontManager *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d490`

## callees

- `0x1800139f4`
- `0x18001ed10`
- `0x18001ee80`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18001eeca`
- `SHLWAPI!PathFindFileNameW` at `0x18001eeca`
- `SHLWAPI!PathFindExtensionW` at `0x18001eee4`
- `SHLWAPI!PathFindExtensionW` at `0x18001ef0d`
- `SHLWAPI!PathFindExtensionW` at `0x18001eee4`
- `SHLWAPI!PathFindExtensionW` at `0x18001ef0d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001eeff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001ef28`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f077`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001eeff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001ef28`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001f077`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001f019`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001f019`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001efe5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001efe5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f024`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f024`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ef68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ef68`

## string_xrefs

- `0x18001f02e`: `TaskDialogIndirect`
- `0x18001ef3f`: `Software\Microsoft\Windows NT\CurrentVersion\Type 1 Installer\Type 1 Fonts`

## pseudocode

```c
void __fastcall CFontManager::_RemovePathFromRegistry(CFontManager *this, unsigned __int16 *a2)
{
  WCHAR *FileNameW; // rbx
  char *v3; // rdi
  HKEY v4; // rsi
  const WCHAR *ExtensionW; // rax
  const WCHAR *v6; // rax
  const WCHAR *v7; // rdx
  int v8; // r14d
  DWORD i; // esi
  CFontManager *v10; // rcx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR ValueName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Data[528]; // [rsp+260h] [rbp+160h] BYREF

  FileNameW = a2;
  if ( PathIsInFontsDirectory(1, a2) )
    FileNameW = PathFindFileNameW(FileNameW);
  v3 = (char *)qword_180038870;
  do
  {
    v4 = *(HKEY *)v3;
    ExtensionW = PathFindExtensionW(FileNameW);
    if ( CompareStringOrdinal(L".pfm", -1, ExtensionW, -1, 1) == 2
      || (v6 = PathFindExtensionW(FileNameW), CompareStringOrdinal(L".pfb", -1, v6, -1, 1) == 2) )
    {
      v7 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Type 1 Installer\\Type 1 Fonts";
      v8 = 1;
    }
    else
    {
      v7 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Fonts";
      v8 = 0;
    }
    phkResult = 0;
    if ( !RegOpenKeyExW(v4, v7, 0, 0x2001Fu, &phkResult) )
    {
      memset_0(ValueName, 0, 0x208u);
      cchValueName = 260;
      memset_0(Data, 0, 0x414u);
      cbData = 1044;
      for ( i = 0; !RegEnumValueW(phkResult, i, ValueName, &cchValueName, 0, 0, (LPBYTE)Data, &cbData); ++i )
      {
        if ( v8 )
        {
          if ( CFontManager::_PathExistsInDblNullSet(v10, FileNameW, Data, cbData >> 1) )
            goto LABEL_13;
        }
        else if ( CompareStringOrdinal(FileNameW, -1, Data, -1, 1) == 2 )
        {
LABEL_13:
          RegDeleteValueW(phkResult, ValueName);
          break;
        }
        cchValueName = 260;
        cbData = 1044;
      }
      RegCloseKey(phkResult);
    }
    v3 += 8;
  }
  while ( v3 != "TaskDialogIndirect" );
}

```

## disassembly

```asm
0x18001ee80  mov     [rsp-8+arg_0], rbx
0x18001ee85  mov     [rsp-8+arg_10], rsi
0x18001ee8a  push    rbp
0x18001ee8b  push    rdi
0x18001ee8c  push    r12
0x18001ee8e  push    r13
0x18001ee90  push    r14
0x18001ee92  lea     rbp, [rsp-590h]
0x18001ee9a  sub     rsp, 690h
0x18001eea1  mov     rax, cs:__security_cookie
0x18001eea8  xor     rax, rsp
0x18001eeab  mov     [rbp+5B0h+var_30], rax
0x18001eeb2  mov     r12d, 1
0x18001eeb8  mov     rbx, rdx
0x18001eebb  mov     ecx, r12d; int
0x18001eebe  call    ?PathIsInFontsDirectory@@YA_NHPEBG@Z; PathIsInFontsDirectory(int,ushort const *)
0x18001eec3  test    al, al
0x18001eec5  jz      short loc_18001EED3
0x18001eec7  mov     rcx, rbx; pszPath
0x18001eeca  call    cs:__imp_PathFindFileNameW
0x18001eed0  mov     rbx, rax
0x18001eed3  lea     rdi, qword_180038870
0x18001eeda  or      r13d, 0FFFFFFFFh
0x18001eede  mov     rsi, [rdi]
0x18001eee1  mov     rcx, rbx; pszPath
0x18001eee4  call    cs:__imp_PathFindExtensionW
0x18001eeea  mov     r9d, r13d; cchCount2
0x18001eeed  mov     [rsp+6B0h+bIgnoreCase], r12d; bIgnoreCase
0x18001eef2  mov     r8, rax; lpString2
0x18001eef5  lea     rcx, aPfm_0; ".pfm"
0x18001eefc  mov     edx, r13d; cchCount1
0x18001eeff  call    cs:__imp_CompareStringOrdinal
0x18001ef05  cmp     eax, 2
0x18001ef08  jz      short loc_18001EF3F
0x18001ef0a  mov     rcx, rbx; pszPath
0x18001ef0d  call    cs:__imp_PathFindExtensionW
0x18001ef13  mov     r9d, r13d; cchCount2
0x18001ef16  mov     [rsp+6B0h+bIgnoreCase], r12d; bIgnoreCase
0x18001ef1b  mov     r8, rax; lpString2
0x18001ef1e  lea     rcx, aPfb; ".pfb"
0x18001ef25  mov     edx, r13d; cchCount1
0x18001ef28  call    cs:__imp_CompareStringOrdinal
0x18001ef2e  cmp     eax, 2
0x18001ef31  jz      short loc_18001EF3F
0x18001ef33  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001ef3a  xor     r14d, r14d
0x18001ef3d  jmp     short loc_18001EF49
0x18001ef3f  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001ef46  mov     r14d, r12d
0x18001ef49  lea     rax, [rsp+6B0h+phkResult]
0x18001ef4e  mov     [rsp+6B0h+phkResult], 0
0x18001ef57  mov     r9d, 2001Fh; samDesired
0x18001ef5d  mov     qword ptr [rsp+6B0h+bIgnoreCase], rax; phkResult
0x18001ef62  xor     r8d, r8d; ulOptions
0x18001ef65  mov     rcx, rsi; hKey
0x18001ef68  call    cs:__imp_RegOpenKeyExW
0x18001ef6e  test    eax, eax
0x18001ef70  jnz     loc_18001F02A
0x18001ef76  xor     edx, edx; Val
0x18001ef78  lea     rcx, [rsp+6B0h+ValueName]; void *
0x18001ef7d  mov     r8d, 208h; Size
0x18001ef83  call    memset_0
0x18001ef88  mov     esi, 414h
0x18001ef8d  mov     [rsp+6B0h+cchValueName], 104h
0x18001ef95  mov     r8d, esi; Size
0x18001ef98  lea     rcx, [rbp+5B0h+Data]; void *
0x18001ef9f  xor     edx, edx; Val
0x18001efa1  call    memset_0
0x18001efa6  mov     [rsp+6B0h+cbData], esi
0x18001efaa  xor     esi, esi
0x18001efac  mov     rcx, [rsp+6B0h+phkResult]; hKey
0x18001efb1  lea     rax, [rsp+6B0h+cbData]
0x18001efb6  mov     [rsp+6B0h+lpcbData], rax; lpcbData
0x18001efbb  lea     r9, [rsp+6B0h+cchValueName]; lpcchValueName
0x18001efc0  lea     rax, [rbp+5B0h+Data]
0x18001efc7  mov     edx, esi; dwIndex
0x18001efc9  mov     [rsp+6B0h+lpData], rax; lpData
0x18001efce  lea     r8, [rsp+6B0h+ValueName]; lpValueName
0x18001efd3  mov     [rsp+6B0h+lpType], 0; lpType
0x18001efdc  mov     qword ptr [rsp+6B0h+bIgnoreCase], 0; lpReserved
0x18001efe5  call    cs:__imp_RegEnumValueW
0x18001efeb  test    eax, eax
0x18001efed  jnz     short loc_18001F01F
0x18001efef  lea     r8, [rbp+5B0h+Data]; unsigned __int16 *
0x18001eff6  test    r14d, r14d
0x18001eff9  jz      short loc_18001F069
0x18001effb  mov     r9d, [rsp+6B0h+cbData]
0x18001f000  mov     rdx, rbx; unsigned __int16 *
0x18001f003  shr     r9d, 1; unsigned int
0x18001f006  call    ?_PathExistsInDblNullSet@CFontManager@@AEAAHPEAGPEBGI@Z; CFontManager::_PathExistsInDblNullSet(ushort *,ushort const *,uint)
0x18001f00b  test    eax, eax
0x18001f00d  jz      short loc_18001F082
0x18001f00f  mov     rcx, [rsp+6B0h+phkResult]; hKey
0x18001f014  lea     rdx, [rsp+6B0h+ValueName]; lpValueName
0x18001f019  call    cs:__imp_RegDeleteValueW
0x18001f01f  mov     rcx, [rsp+6B0h+phkResult]; hKey
0x18001f024  call    cs:__imp_RegCloseKey
0x18001f02a  add     rdi, 8
0x18001f02e  lea     rax, aTaskdialogindi; "TaskDialogIndirect"
0x18001f035  cmp     rdi, rax
0x18001f038  jnz     loc_18001EEDE
0x18001f03e  mov     rcx, [rbp+5B0h+var_30]
0x18001f045  xor     rcx, rsp; StackCookie
0x18001f048  call    __security_check_cookie
0x18001f04d  lea     r11, [rsp+6B0h+var_20]
0x18001f055  mov     rbx, [r11+30h]
0x18001f059  mov     rsi, [r11+40h]
0x18001f05d  mov     rsp, r11
0x18001f060  pop     r14
0x18001f062  pop     r13
0x18001f064  pop     r12
0x18001f066  pop     rdi
0x18001f067  pop     rbp
0x18001f068  retn
0x18001f069  mov     r9d, r13d; cchCount2
0x18001f06c  mov     [rsp+6B0h+bIgnoreCase], r12d; bIgnoreCase
0x18001f071  mov     edx, r13d; cchCount1
0x18001f074  mov     rcx, rbx; lpString1
0x18001f077  call    cs:__imp_CompareStringOrdinal
0x18001f07d  cmp     eax, 2
0x18001f080  jz      short loc_18001F00F
0x18001f082  mov     [rsp+6B0h+cchValueName], 104h
0x18001f08a  add     esi, r12d
0x18001f08d  mov     [rsp+6B0h+cbData], 414h
0x18001f095  jmp     loc_18001EFAC
```
