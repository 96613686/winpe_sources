# RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180044554`
- end: `0x18004470f`
- name: `?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `443`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002bcdc`

## callees

- `0x1800073c0`
- `0x18000c190`
- `0x18000ced0`
- `0x180027448`
- `0x18002c96c`
- `0x180044480`
- `0x180044554`
- `0x18004491c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800446ad`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800446ad`

## string_xrefs

- `0x180044595`: `GetwinDirectoryWinPE`
- `0x1800446ca`: `%s: Cannot load file "%s" into registry key "%s". RegLoadKeyW error code: 0x%08x.`
- `0x1800446e6`: `%s: File "%s" loaded into registry key "%s".`
- `0x1800445cf`: `%s: GetWindowsDirectoryWinPE returns an empty path.`
- `0x180044686`: `system32\config\software`

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
  const unsigned __int16 *v8; // rcx
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // eax
  LSTATUS KeyW; // eax
  unsigned __int64 v14; // [rsp+68h] [rbp+38h] BYREF
  unsigned __int16 *v15; // [rsp+70h] [rbp+40h] BYREF
  LPCWSTR lpFile; // [rsp+78h] [rbp+48h] BYREF

  v4 = 0;
  v15 = 0;
  lpFile = 0;
  v14 = 0;
  WindowsDirectoryWinPE = GetWindowsDirectoryWinPE(&v15);
  v6 = WindowsDirectoryWinPE;
  if ( WindowsDirectoryWinPE )
  {
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"RegLoadKeyWinPE",
      L"GetwinDirectoryWinPE",
      WindowsDirectoryWinPE);
    v7 = v15;
    goto LABEL_16;
  }
  v7 = v15;
  if ( !(unsigned int)IsEmptyString(v15) )
  {
    v10 = StringLen(v8, &v14);
    v9 = v10;
    if ( v10 < 0 )
    {
      Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"RegLoadKeyWinPE", L"StringLen", (unsigned int)v10);
      goto LABEL_19;
    }
    if ( v14 && v7[v14 - 1] != 92 )
    {
      v11 = StringCat(v7, L"\\", (unsigned __int16 **)&lpFile);
      v9 = v11;
      if ( v11 < 0 )
        goto LABEL_11;
      SafeFree(v7);
      v7 = (unsigned __int16 *)lpFile;
      lpFile = 0;
    }
    v11 = StringCat(v7, L"system32\\config\\software", (unsigned __int16 **)&lpFile);
    v9 = v11;
    if ( v11 >= 0 )
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
        goto LABEL_19;
      }
      Logger::TraceError(
        L"%s: Cannot load file \"%s\" into registry key \"%s\". RegLoadKeyW error code: 0x%08x.",
        L"RegLoadKeyWinPE",
        v4,
        L"HKEY_LOCAL_MACHINE\\TargetSoftware",
        KeyW);
LABEL_16:
      if ( v6 <= 0 )
      {
        v9 = v6;
        goto LABEL_19;
      }
      goto LABEL_5;
    }
LABEL_11:
    Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"RegLoadKeyWinPE", L"StringCat", (unsigned int)v11);
    v4 = (WCHAR *)lpFile;
    goto LABEL_19;
  }
  Logger::TraceError(L"%s: GetWindowsDirectoryWinPE returns an empty path.", L"RegLoadKeyWinPE");
  LOWORD(v6) = 2;
LABEL_5:
  v9 = (unsigned __int16)v6 | 0x80070000;
LABEL_19:
  SafeFree(v7);
  SafeFree(v4);
  return v9;
}

```

## disassembly

```asm
0x180044554  mov     [rsp-28h+lpFile], r9
0x180044559  mov     [rsp-28h+arg_10], r8
0x18004455e  mov     [rsp-28h+arg_8], rdx
0x180044563  push    rbp
0x180044564  push    rbx
0x180044565  push    rsi
0x180044566  push    rdi
0x180044567  push    r14
0x180044569  mov     rbp, rsp
0x18004456c  sub     rsp, 30h
0x180044570  xor     r14d, r14d
0x180044573  mov     [rbp+arg_10], 0
0x18004457b  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x18004457f  mov     [rbp+lpFile], r14
0x180044583  mov     [rbp+arg_8], r14
0x180044587  call    ?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z; GetWindowsDirectoryWinPE(ushort * *)
0x18004458c  mov     esi, eax
0x18004458e  test    eax, eax
0x180044590  jz      short loc_1800445B8
0x180044592  mov     r9d, eax
0x180044595  lea     r8, aGetwindirector; "GetwinDirectoryWinPE"
0x18004459c  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x1800445a3  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x1800445aa  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800445af  mov     rdi, [rbp+arg_10]
0x1800445b3  jmp     loc_1800446DA
0x1800445b8  mov     rdi, [rbp+arg_10]
0x1800445bc  mov     rcx, rdi; unsigned __int16 *
0x1800445bf  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800445c4  test    eax, eax
0x1800445c6  jz      short loc_1800445EE
0x1800445c8  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x1800445cf  lea     rcx, aSGetwindowsdir; "%s: GetWindowsDirectoryWinPE returns an"...
0x1800445d6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800445db  mov     esi, 2
0x1800445e0  movzx   ebx, si
0x1800445e3  or      ebx, 80070000h
0x1800445e9  jmp     loc_1800446F2
0x1800445ee  lea     rdx, [rbp+arg_8]; unsigned __int64 *
0x1800445f2  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x1800445f7  mov     ebx, eax
0x1800445f9  test    eax, eax
0x1800445fb  jns     short loc_18004461F
0x1800445fd  mov     r9d, eax
0x180044600  lea     r8, aStringlen; "StringLen"
0x180044607  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18004460e  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180044615  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18004461a  jmp     loc_1800446F2
0x18004461f  mov     rax, [rbp+arg_8]
0x180044623  test    rax, rax
0x180044626  jz      short loc_18004467F
0x180044628  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x18004462e  jz      short loc_18004467F
0x180044630  lea     r8, [rbp+lpFile]; unsigned __int16 **
0x180044634  mov     rcx, rdi; unsigned __int16 *
0x180044637  lea     rdx, asc_180050E74; "\\"
0x18004463e  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x180044643  mov     ebx, eax
0x180044645  test    eax, eax
0x180044647  jns     short loc_18004466F
0x180044649  mov     r9d, eax
0x18004464c  lea     r8, aStringcat; "StringCat"
0x180044653  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18004465a  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180044661  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180044666  mov     r14, [rbp+lpFile]
0x18004466a  jmp     loc_1800446F2
0x18004466f  mov     rcx, rdi; lpMem
0x180044672  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180044677  mov     rdi, [rbp+lpFile]
0x18004467b  mov     [rbp+lpFile], r14
0x18004467f  lea     r8, [rbp+lpFile]; unsigned __int16 **
0x180044683  mov     rcx, rdi; unsigned __int16 *
0x180044686  lea     rdx, aSystem32Config; "system32\\config\\software"
0x18004468d  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x180044692  mov     ebx, eax
0x180044694  test    eax, eax
0x180044696  js      short loc_180044649
0x180044698  mov     r14, [rbp+lpFile]
0x18004469c  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x1800446a3  mov     r8, r14; lpFile
0x1800446a6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800446ad  call    cs:__imp_RegLoadKeyW
0x1800446b3  lea     r9, aHkeyLocalMachi_3; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x1800446ba  mov     r8, r14
0x1800446bd  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x1800446c4  mov     esi, eax
0x1800446c6  test    eax, eax
0x1800446c8  jz      short loc_1800446E6
0x1800446ca  lea     rcx, aSCannotLoadFil; "%s: Cannot load file \"%s\" into regist"...
0x1800446d1  mov     [rsp+30h+var_10], eax
0x1800446d5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800446da  test    esi, esi
0x1800446dc  jg      loc_1800445E0
0x1800446e2  mov     ebx, esi
0x1800446e4  jmp     short loc_1800446F2
0x1800446e6  lea     rcx, aSFileSLoadedIn; "%s: File \"%s\" loaded into registry ke"...
0x1800446ed  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800446f2  mov     rcx, rdi; lpMem
0x1800446f5  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800446fa  mov     rcx, r14; lpMem
0x1800446fd  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180044702  mov     eax, ebx
0x180044704  add     rsp, 30h
0x180044708  pop     r14
0x18004470a  pop     rdi
0x18004470b  pop     rsi
0x18004470c  pop     rbx
0x18004470d  pop     rbp
0x18004470e  retn
```
