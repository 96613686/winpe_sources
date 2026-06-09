# RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180010048`
- end: `0x180010210`
- name: `?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `456`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180013084`

## callees

- `0x180010048`
- `0x180010218`
- `0x18001029c`
- `0x180010320`
- `0x1800240ec`
- `0x180024398`
- `0x180024618`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180010189`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180010189`

## string_xrefs

- `0x18001008d`: `GetwinDirectoryWinPE`
- `0x1800101d3`: `%s: GetWindowsDirectoryWinPE returns an empty path.`
- `0x1800101be`: `%s: File "%s" loaded into registry key "%s".`
- `0x1800101a6`: `%s: Cannot load file "%s" into registry key "%s". RegLoadKeyW error code: 0x%08x.`
- `0x180010162`: `system32\config\software`

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
0x180010048  mov     rax, rsp
0x18001004b  mov     [rax+8], rbx
0x18001004f  mov     [rax+20h], r9
0x180010053  mov     [rax+18h], r8
0x180010057  mov     [rax+10h], rdx
0x18001005b  push    rbp
0x18001005c  push    rsi
0x18001005d  push    rdi
0x18001005e  push    r14
0x180010060  push    r15
0x180010062  mov     rbp, rsp
0x180010065  sub     rsp, 30h
0x180010069  xor     r15d, r15d
0x18001006c  lea     rcx, [rbp+arg_10]; unsigned __int16 **
0x180010070  mov     [rbp+arg_10], r15
0x180010074  mov     r14d, r15d
0x180010077  mov     [rbp+lpFile], r15
0x18001007b  mov     [rbp+arg_8], r15
0x18001007f  call    ?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z; GetWindowsDirectoryWinPE(ushort * *)
0x180010084  mov     esi, eax
0x180010086  test    eax, eax
0x180010088  jz      short loc_1800100B0
0x18001008a  mov     r9d, eax
0x18001008d  lea     r8, aGetwindirector; "GetwinDirectoryWinPE"
0x180010094  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18001009b  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x1800100a2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800100a7  mov     rdi, [rbp+arg_10]
0x1800100ab  jmp     loc_1800101B6
0x1800100b0  mov     rdi, [rbp+arg_10]
0x1800100b4  test    rdi, rdi
0x1800100b7  jz      loc_1800101CC
0x1800100bd  cmp     [rdi], r15w
0x1800100c1  jz      loc_1800101CC
0x1800100c7  lea     rdx, [rbp+arg_8]; unsigned __int64 *
0x1800100cb  mov     rcx, rdi; unsigned __int16 *
0x1800100ce  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x1800100d3  mov     ebx, eax
0x1800100d5  test    eax, eax
0x1800100d7  jns     short loc_1800100FB
0x1800100d9  mov     r9d, eax
0x1800100dc  lea     r8, aStringlen; "StringLen"
0x1800100e3  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x1800100ea  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x1800100f1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800100f6  jmp     loc_1800101ED
0x1800100fb  mov     rax, [rbp+arg_8]
0x1800100ff  test    rax, rax
0x180010102  jz      short loc_18001015B
0x180010104  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x18001010a  jz      short loc_18001015B
0x18001010c  lea     r8, [rbp+lpFile]; unsigned __int16 **
0x180010110  mov     rcx, rdi; unsigned __int16 *
0x180010113  lea     rdx, asc_180029FA8; "\\"
0x18001011a  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x18001011f  mov     ebx, eax
0x180010121  test    eax, eax
0x180010123  jns     short loc_18001014B
0x180010125  mov     r9d, eax
0x180010128  lea     r8, aStringcat; "StringCat"
0x18001012f  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x180010136  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18001013d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010142  mov     r14, [rbp+lpFile]
0x180010146  jmp     loc_1800101ED
0x18001014b  mov     rcx, rdi; void *
0x18001014e  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180010153  mov     rdi, [rbp+lpFile]
0x180010157  mov     [rbp+lpFile], r15
0x18001015b  lea     r8, [rbp+lpFile]; unsigned __int16 **
0x18001015f  mov     rcx, rdi; unsigned __int16 *
0x180010162  lea     rdx, aSystem32Config; "system32\\config\\software"
0x180010169  call    ?StringCat@@YAJPEBG0PEAPEAG@Z; StringCat(ushort const *,ushort const *,ushort * *)
0x18001016e  mov     ebx, eax
0x180010170  test    eax, eax
0x180010172  js      short loc_180010125
0x180010174  mov     r14, [rbp+lpFile]
0x180010178  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x18001017f  mov     r8, r14; lpFile
0x180010182  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010189  call    cs:__imp_RegLoadKeyW
0x18001018f  lea     r9, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x180010196  mov     r8, r14
0x180010199  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x1800101a0  mov     esi, eax
0x1800101a2  test    eax, eax
0x1800101a4  jz      short loc_1800101BE
0x1800101a6  lea     rcx, aSCannotLoadFil; "%s: Cannot load file \"%s\" into regist"...
0x1800101ad  mov     [rsp+30h+var_10], eax
0x1800101b1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800101b6  test    esi, esi
0x1800101b8  jg      short loc_1800101E4
0x1800101ba  mov     ebx, esi
0x1800101bc  jmp     short loc_1800101ED
0x1800101be  lea     rcx, aSFileSLoadedIn; "%s: File \"%s\" loaded into registry ke"...
0x1800101c5  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800101ca  jmp     short loc_1800101ED
0x1800101cc  lea     rdx, aRegloadkeywinp; "RegLoadKeyWinPE"
0x1800101d3  lea     rcx, aSGetwindowsdir; "%s: GetWindowsDirectoryWinPE returns an"...
0x1800101da  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800101df  mov     esi, 2
0x1800101e4  movzx   ebx, si
0x1800101e7  or      ebx, 80070000h
0x1800101ed  mov     rcx, rdi; void *
0x1800101f0  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800101f5  mov     rcx, r14; void *
0x1800101f8  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800101fd  mov     eax, ebx
0x1800101ff  mov     rbx, [rsp+30h+arg_0]
0x180010204  add     rsp, 30h
0x180010208  pop     r15
0x18001020a  pop     r14
0x18001020c  pop     rdi
0x18001020d  pop     rsi
0x18001020e  pop     rbp
0x18001020f  retn
```
