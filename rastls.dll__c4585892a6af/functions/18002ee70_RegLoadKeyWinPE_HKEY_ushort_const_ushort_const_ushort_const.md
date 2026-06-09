# RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x18002ee70`
- end: `0x18002f03f`
- name: `?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `463`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18007cc34`

## callees

- `0x18002ee70`
- `0x18002f048`
- `0x18002f1ac`
- `0x18002f324`
- `0x18007c340`
- `0x18007c610`
- `0x18007c7a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18002efb1`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18002efb1`

## string_xrefs

- `0x18002eeb5`: `GetwinDirectoryWinPE`
- `0x18002efd4`: `%s: Cannot load file "%s" into registry key "%s". RegLoadKeyW error code: 0x%08x.`
- `0x18002efec`: `%s: File "%s" loaded into registry key "%s".`
- `0x18002f001`: `%s: GetWindowsDirectoryWinPE returns an empty path.`
- `0x18002ef8a`: `system32\config\software`

## pseudocode

```c
__int64 __fastcall RegLoadKeyWinPE(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  WCHAR *v4; // r14
  unsigned int WindowsDirectoryWinPE; // eax
  int v6; // esi
  unsigned __int16 *v7; // rdi
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  LSTATUS KeyW; // eax
  unsigned __int64 v13; // [rsp+68h] [rbp+38h] BYREF
  unsigned __int16 *v14; // [rsp+70h] [rbp+40h] BYREF
  LPCWSTR lpFile; // [rsp+78h] [rbp+48h] BYREF

  v14 = 0;
  v4 = 0;
  lpFile = 0;
  v13 = 0;
  WindowsDirectoryWinPE = GetWindowsDirectoryWinPE(&v14);
  v6 = WindowsDirectoryWinPE;
  if ( WindowsDirectoryWinPE )
  {
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"RegLoadKeyWinPE",
      L"GetwinDirectoryWinPE",
      WindowsDirectoryWinPE);
    v7 = v14;
    goto LABEL_15;
  }
  v7 = v14;
  if ( !v14 || !*v14 )
  {
    Logger::TraceError(L"%s: GetWindowsDirectoryWinPE returns an empty path.", L"RegLoadKeyWinPE");
    LOWORD(v6) = 2;
    goto LABEL_19;
  }
  v8 = StringLen(v14, &v13);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( v13 && v7[v13 - 1] != 92 )
    {
      v10 = StringCat(v7, L"\\", (unsigned __int16 **)&lpFile);
      v9 = v10;
      if ( v10 < 0 )
      {
LABEL_10:
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"RegLoadKeyWinPE",
          L"StringCat",
          (unsigned int)v10);
        v4 = (WCHAR *)lpFile;
        goto LABEL_20;
      }
      SafeFree(v7);
      v7 = (unsigned __int16 *)lpFile;
      lpFile = 0;
    }
    v10 = StringCat(v7, L"system32\\config\\software", (unsigned __int16 **)&lpFile);
    v9 = v10;
    if ( v10 >= 0 )
    {
      v4 = (WCHAR *)lpFile;
      KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware", lpFile);
      v6 = KeyW;
      if ( !KeyW )
      {
        Logger::TraceVerbose(
          L"%s: File \"%s\" loaded into registry key \"%s\".",
          L"RegLoadKeyWinPE",
          v4,
          L"HKEY_LOCAL_MACHINE\\TargetSoftware");
        goto LABEL_20;
      }
      Logger::TraceError(
        L"%s: Cannot load file \"%s\" into registry key \"%s\". RegLoadKeyW error code: 0x%08x.",
        L"RegLoadKeyWinPE",
        v4,
        L"HKEY_LOCAL_MACHINE\\TargetSoftware",
        KeyW);
LABEL_15:
      if ( v6 <= 0 )
      {
        v9 = v6;
        goto LABEL_20;
      }
LABEL_19:
      v9 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_20;
    }
    goto LABEL_10;
  }
  Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"RegLoadKeyWinPE", L"StringLen", (unsigned int)v8);
LABEL_20:
  SafeFree(v7);
  SafeFree(v4);
  return v9;
}

```

## disassembly

```asm
0x18002ee70  mov     rax, rsp
0x18002ee73  mov     [rax+8], rbx
0x18002ee77  mov     [rax+20h], r9
0x18002ee7b  mov     [rax+18h], r8
0x18002ee7f  mov     [rax+10h], rdx
0x18002ee83  push    rbp
0x18002ee84  push    rsi
0x18002ee85  push    rdi
0x18002ee86  push    r14
0x18002ee88  push    r15
0x18002ee8a  mov     rbp, rsp
0x18002ee8d  sub     rsp, 30h
0x18002ee91  xor     r15d, r15d
0x18002ee94  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x18002ee98  mov     [rbp+arg_10], r15
0x18002ee9c  mov     r14d, r15d
0x18002ee9f  mov     [rbp+lpFile], r15
0x18002eea3  mov     [rbp+arg_8], r15
0x18002eea7  call    ?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z; GetWindowsDirectoryWinPE(ushort * *)
0x18002eeac  mov     esi, eax
0x18002eeae  test    eax, eax
0x18002eeb0  jz      short loc_18002EED8
0x18002eeb2  mov     r9d, eax
0x18002eeb5  lea     r8, aGetwindirector; "GetwinDirectoryWinPE"
0x18002eebc  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18002eec3  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18002eeca  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002eecf  mov     rdi, [rbp+arg_10]
0x18002eed3  jmp     loc_18002EFE4
0x18002eed8  mov     rdi, [rbp+arg_10]
0x18002eedc  test    rdi, rdi
0x18002eedf  jz      loc_18002EFFA
0x18002eee5  cmp     [rdi], r15w
0x18002eee9  jz      loc_18002EFFA
0x18002eeef  lea     rdx, [rbp+arg_8]; unsigned __int64 *
0x18002eef3  mov     rcx, rdi; unsigned __int16 *
0x18002eef6  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x18002eefb  mov     ebx, eax
0x18002eefd  test    eax, eax
0x18002eeff  jns     short loc_18002EF23
0x18002ef01  mov     r9d, eax
0x18002ef04  lea     r8, aStringlen; "StringLen"
0x18002ef0b  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18002ef12  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18002ef19  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002ef1e  jmp     loc_18002F01B
0x18002ef23  mov     rax, [rbp+arg_8]
0x18002ef27  test    rax, rax
0x18002ef2a  jz      short loc_18002EF83
0x18002ef2c  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x18002ef32  jz      short loc_18002EF83
0x18002ef34  lea     r8, [rbp+lpFile]; unsigned __int16 **
0x18002ef38  mov     rcx, rdi; unsigned __int16 *
0x18002ef3b  lea     rdx, asc_180087834; "\\"
0x18002ef42  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x18002ef47  mov     ebx, eax
0x18002ef49  test    eax, eax
0x18002ef4b  jns     short loc_18002EF73
0x18002ef4d  mov     r9d, eax
0x18002ef50  lea     r8, aStringcat; "StringCat"
0x18002ef57  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18002ef5e  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18002ef65  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002ef6a  mov     r14, [rbp+lpFile]
0x18002ef6e  jmp     loc_18002F01B
0x18002ef73  mov     rcx, rdi; void *
0x18002ef76  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002ef7b  mov     rdi, [rbp+lpFile]
0x18002ef7f  mov     [rbp+lpFile], r15
0x18002ef83  lea     r8, [rbp+lpFile]; unsigned __int16 **
0x18002ef87  mov     rcx, rdi; unsigned __int16 *
0x18002ef8a  lea     rdx, aSystem32Config; "system32\\config\\software"
0x18002ef91  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x18002ef96  mov     ebx, eax
0x18002ef98  test    eax, eax
0x18002ef9a  js      short loc_18002EF4D
0x18002ef9c  mov     r14, [rbp+lpFile]
0x18002efa0  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x18002efa7  mov     r8, r14; lpFile
0x18002efaa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002efb1  call    cs:__imp_RegLoadKeyW
0x18002efb8  nop     dword ptr [rax+rax+00h]
0x18002efbd  lea     r9, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x18002efc4  mov     r8, r14
0x18002efc7  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18002efce  mov     esi, eax
0x18002efd0  test    eax, eax
0x18002efd2  jz      short loc_18002EFEC
0x18002efd4  lea     rcx, aSCannotLoadFil; "%s: Cannot load file \"%s\" into regist"...
0x18002efdb  mov     [rsp+30h+var_10], eax
0x18002efdf  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002efe4  test    esi, esi
0x18002efe6  jg      short loc_18002F012
0x18002efe8  mov     ebx, esi
0x18002efea  jmp     short loc_18002F01B
0x18002efec  lea     rcx, aSFileSLoadedIn; "%s: File \"%s\" loaded into registry ke"...
0x18002eff3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18002eff8  jmp     short loc_18002F01B
0x18002effa  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18002f001  lea     rcx, aSGetwindowsdir; "%s: GetWindowsDirectoryWinPE returns an"...
0x18002f008  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002f00d  mov     esi, 2
0x18002f012  movzx   ebx, si
0x18002f015  or      ebx, 80070000h
0x18002f01b  mov     rcx, rdi; void *
0x18002f01e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002f023  mov     rcx, r14; void *
0x18002f026  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002f02b  mov     eax, ebx
0x18002f02d  mov     rbx, [rsp+30h+arg_0]
0x18002f032  add     rsp, 30h
0x18002f036  pop     r15
0x18002f038  pop     r14
0x18002f03a  pop     rdi
0x18002f03b  pop     rsi
0x18002f03c  pop     rbp
0x18002f03d  retn
```
