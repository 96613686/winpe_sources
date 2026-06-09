# RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x18002c978`
- end: `0x18002cb40`
- name: `?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `456`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180077838`

## callees

- `0x18002c978`
- `0x18002cb48`
- `0x18002cca4`
- `0x18002ce0c`
- `0x180076f80`
- `0x18007722c`
- `0x1800773c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18002cab9`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18002cab9`

## string_xrefs

- `0x18002cb03`: `%s: GetWindowsDirectoryWinPE returns an empty path.`
- `0x18002cad6`: `%s: Cannot load file "%s" into registry key "%s". RegLoadKeyW error code: 0x%08x.`
- `0x18002c9bd`: `GetwinDirectoryWinPE`
- `0x18002caee`: `%s: File "%s" loaded into registry key "%s".`
- `0x18002ca92`: `system32\config\software`

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
0x18002c978  mov     rax, rsp
0x18002c97b  mov     [rax+8], rbx
0x18002c97f  mov     [rax+20h], r9
0x18002c983  mov     [rax+18h], r8
0x18002c987  mov     [rax+10h], rdx
0x18002c98b  push    rbp
0x18002c98c  push    rsi
0x18002c98d  push    rdi
0x18002c98e  push    r14
0x18002c990  push    r15
0x18002c992  mov     rbp, rsp
0x18002c995  sub     rsp, 30h
0x18002c999  xor     r15d, r15d
0x18002c99c  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x18002c9a0  mov     [rbp+arg_10], r15
0x18002c9a4  mov     r14d, r15d
0x18002c9a7  mov     [rbp+lpFile], r15
0x18002c9ab  mov     [rbp+arg_8], r15
0x18002c9af  call    ?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z; GetWindowsDirectoryWinPE(ushort * *)
0x18002c9b4  mov     esi, eax
0x18002c9b6  test    eax, eax
0x18002c9b8  jz      short loc_18002C9E0
0x18002c9ba  mov     r9d, eax
0x18002c9bd  lea     r8, aGetwindirector; "GetwinDirectoryWinPE"
0x18002c9c4  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18002c9cb  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18002c9d2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002c9d7  mov     rdi, [rbp+arg_10]
0x18002c9db  jmp     loc_18002CAE6
0x18002c9e0  mov     rdi, [rbp+arg_10]
0x18002c9e4  test    rdi, rdi
0x18002c9e7  jz      loc_18002CAFC
0x18002c9ed  cmp     [rdi], r15w
0x18002c9f1  jz      loc_18002CAFC
0x18002c9f7  lea     rdx, [rbp+arg_8]; unsigned __int64 *
0x18002c9fb  mov     rcx, rdi; unsigned __int16 *
0x18002c9fe  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x18002ca03  mov     ebx, eax
0x18002ca05  test    eax, eax
0x18002ca07  jns     short loc_18002CA2B
0x18002ca09  mov     r9d, eax
0x18002ca0c  lea     r8, aStringlen; "StringLen"
0x18002ca13  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18002ca1a  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18002ca21  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002ca26  jmp     loc_18002CB1D
0x18002ca2b  mov     rax, [rbp+arg_8]
0x18002ca2f  test    rax, rax
0x18002ca32  jz      short loc_18002CA8B
0x18002ca34  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x18002ca3a  jz      short loc_18002CA8B
0x18002ca3c  lea     r8, [rbp+lpFile]; unsigned __int16 **
0x18002ca40  mov     rcx, rdi; unsigned __int16 *
0x18002ca43  lea     rdx, asc_180081834; "\\"
0x18002ca4a  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x18002ca4f  mov     ebx, eax
0x18002ca51  test    eax, eax
0x18002ca53  jns     short loc_18002CA7B
0x18002ca55  mov     r9d, eax
0x18002ca58  lea     r8, aStringcat; "StringCat"
0x18002ca5f  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18002ca66  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18002ca6d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002ca72  mov     r14, [rbp+lpFile]
0x18002ca76  jmp     loc_18002CB1D
0x18002ca7b  mov     rcx, rdi; void *
0x18002ca7e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002ca83  mov     rdi, [rbp+lpFile]
0x18002ca87  mov     [rbp+lpFile], r15
0x18002ca8b  lea     r8, [rbp+lpFile]; unsigned __int16 **
0x18002ca8f  mov     rcx, rdi; unsigned __int16 *
0x18002ca92  lea     rdx, aSystem32Config; "system32\\config\\software"
0x18002ca99  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x18002ca9e  mov     ebx, eax
0x18002caa0  test    eax, eax
0x18002caa2  js      short loc_18002CA55
0x18002caa4  mov     r14, [rbp+lpFile]
0x18002caa8  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x18002caaf  mov     r8, r14; lpFile
0x18002cab2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002cab9  call    cs:__imp_RegLoadKeyW
0x18002cabf  lea     r9, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x18002cac6  mov     r8, r14
0x18002cac9  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18002cad0  mov     esi, eax
0x18002cad2  test    eax, eax
0x18002cad4  jz      short loc_18002CAEE
0x18002cad6  lea     rcx, aSCannotLoadFil; "%s: Cannot load file \"%s\" into regist"...
0x18002cadd  mov     [rsp+30h+var_10], eax
0x18002cae1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002cae6  test    esi, esi
0x18002cae8  jg      short loc_18002CB14
0x18002caea  mov     ebx, esi
0x18002caec  jmp     short loc_18002CB1D
0x18002caee  lea     rcx, aSFileSLoadedIn; "%s: File \"%s\" loaded into registry ke"...
0x18002caf5  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18002cafa  jmp     short loc_18002CB1D
0x18002cafc  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18002cb03  lea     rcx, aSGetwindowsdir; "%s: GetWindowsDirectoryWinPE returns an"...
0x18002cb0a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002cb0f  mov     esi, 2
0x18002cb14  movzx   ebx, si
0x18002cb17  or      ebx, 80070000h
0x18002cb1d  mov     rcx, rdi; void *
0x18002cb20  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002cb25  mov     rcx, r14; void *
0x18002cb28  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002cb2d  mov     eax, ebx
0x18002cb2f  mov     rbx, [rsp+30h+arg_0]
0x18002cb34  add     rsp, 30h
0x18002cb38  pop     r15
0x18002cb3a  pop     r14
0x18002cb3c  pop     rdi
0x18002cb3d  pop     rsi
0x18002cb3e  pop     rbp
0x18002cb3f  retn
```
