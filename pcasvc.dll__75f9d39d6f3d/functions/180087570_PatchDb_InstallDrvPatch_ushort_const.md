# PatchDb_InstallDrvPatch(ushort const *)

- ea: `0x180087570`
- end: `0x1800877c7`
- name: `?PatchDb_InstallDrvPatch@@YAKPEBG@Z`
- size: `599`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x18000dc08`
- `0x180012920`
- `0x180087570`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x180087600`
- `ntdll!RtlDoesFileExists_U` at `0x180087656`
- `ntdll!RtlDoesFileExists_U` at `0x180087600`
- `ntdll!RtlDoesFileExists_U` at `0x180087656`
- `ntdll!RtlGetNtSystemRoot` at `0x18008760e`
- `ntdll!RtlGetNtSystemRoot` at `0x180087667`
- `ntdll!RtlGetNtSystemRoot` at `0x18008760e`
- `ntdll!RtlGetNtSystemRoot` at `0x180087667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800876cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800876cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087777`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008776d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008776d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800876c2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18008773c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800876c2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18008773c`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800876f8`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800876f8`

## string_xrefs

- `0x1800875d2`: `Failed to expand drv patch extract path %d`
- `0x180087640`: `Failed to expand drv patch path %d`
- `0x1800875e8`: `PatchDb_InstallDrvPatch`
- `0x180087715`: `PatchDb_InstallDrvPatch`
- `0x18008778a`: `PatchDb_InstallDrvPatch`
- `0x18008769f`: `Failed to expand drv patch temp path string %d`
- `0x180087708`: `Failed to copy extracted drvpatch.sdb to the destination %d`
- `0x1800876d6`: `Failed to move the old drvpatch.sdb to a temp location %d`
- `0x18008777d`: `Failed to delete temp drvpatch.sdb %d`
- `0x180087750`: `Failed to move backup drvpatch.sdb to drvpatch.sdb %d`

## pseudocode

```c
__int64 __fastcall PatchDb_InstallDrvPatch(const unsigned __int16 *a1)
{
  int v1; // eax
  DWORD v2; // ebx
  const char *v3; // r9
  int v4; // r8d
  __int64 v5; // rcx
  __int64 NtSystemRoot; // rax
  int v7; // eax
  int v8; // esi
  __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  DWORD LastError; // [rsp+20h] [rbp-E0h]
  WCHAR ExistingFileName[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR NewFileName[264]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR FileName[264]; // [rsp+450h] [rbp+350h] BYREF

  v1 = StringCchPrintfW(FileName, 0x104u, L"%s\\drvpatch.sdb", a1);
  v2 = v1;
  if ( v1 < 0 )
  {
    if ( (v1 & 0x1FFF0000) == 0x70000 )
      v2 = (unsigned __int16)v1;
    v3 = "Failed to expand drv patch extract path %d";
    v4 = 1879;
    goto LABEL_5;
  }
  if ( !RtlDoesFileExists_U(FileName) )
    return 0;
  NtSystemRoot = RtlGetNtSystemRoot(v5);
  v7 = StringCchPrintfW(ExistingFileName, 0x104u, L"%s\\apppatch\\drvpatch.sdb", NtSystemRoot);
  v2 = v7;
  if ( v7 < 0 )
  {
    if ( (v7 & 0x1FFF0000) == 0x70000 )
      v2 = (unsigned __int16)v7;
    v3 = "Failed to expand drv patch path %d";
    v4 = 1903;
    goto LABEL_5;
  }
  v8 = 0;
  if ( RtlDoesFileExists_U(ExistingFileName) )
  {
    v10 = RtlGetNtSystemRoot(v9);
    v11 = StringCchPrintfW(NewFileName, 0x104u, L"%s\\apppatch\\drvpatch.sdb.bak", v10);
    v2 = v11;
    if ( v11 < 0 )
    {
      if ( (v11 & 0x1FFF0000) == 0x70000 )
        v2 = (unsigned __int16)v11;
      v3 = "Failed to expand drv patch temp path string %d";
      v4 = 1916;
      goto LABEL_5;
    }
    if ( !MoveFileExW(ExistingFileName, NewFileName, 1u) )
    {
      LastError = GetLastError();
      v3 = "Failed to move the old drvpatch.sdb to a temp location %d";
      v2 = LastError;
      v4 = 1922;
LABEL_5:
      AslLogCallPrintf(1, (unsigned int)"PatchDb_InstallDrvPatch", v4, (_DWORD)v3);
      return v2;
    }
    v8 = 1;
  }
  if ( CopyFileW(FileName, ExistingFileName, 0) )
  {
    if ( v8 && !DeleteFileW(NewFileName) )
    {
      GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"PatchDb_InstallDrvPatch",
        1945,
        (unsigned int)"Failed to delete temp drvpatch.sdb %d");
    }
    return 0;
  }
  v2 = GetLastError();
  AslLogCallPrintf(
    1,
    (unsigned int)"PatchDb_InstallDrvPatch",
    1933,
    (unsigned int)"Failed to copy extracted drvpatch.sdb to the destination %d");
  if ( v8 && !MoveFileExW(NewFileName, ExistingFileName, 0) )
  {
    GetLastError();
    v3 = "Failed to move backup drvpatch.sdb to drvpatch.sdb %d";
    v4 = 1938;
    goto LABEL_5;
  }
  return v2;
}

```

## disassembly

```asm
0x180087570  mov     [rsp-8+arg_8], rbx
0x180087575  mov     [rsp-8+arg_10], rsi
0x18008757a  push    rbp
0x18008757b  push    rdi
0x18008757c  push    r14
0x18008757e  lea     rbp, [rsp-570h]
0x180087586  sub     rsp, 670h
0x18008758d  mov     rax, cs:__security_cookie
0x180087594  xor     rax, rsp
0x180087597  mov     [rbp+580h+var_20], rax
0x18008759e  mov     r9, rcx
0x1800875a1  lea     r8, aSDrvpatchSdb; "%s\\drvpatch.sdb"
0x1800875a8  mov     r14d, 104h
0x1800875ae  lea     rcx, [rbp+580h+FileName]; unsigned __int16 *
0x1800875b5  mov     edx, r14d; unsigned __int64
0x1800875b8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800875bd  mov     ebx, eax
0x1800875bf  test    eax, eax
0x1800875c1  jns     short loc_1800875F9
0x1800875c3  and     eax, 1FFF0000h
0x1800875c8  cmp     eax, 70000h
0x1800875cd  jnz     short loc_1800875D2
0x1800875cf  movzx   ebx, bx
0x1800875d2  lea     r9, aFailedToExpand_7; "Failed to expand drv patch extract path"...
0x1800875d9  mov     r8d, 757h
0x1800875df  mov     [rsp+680h+var_660], ebx
0x1800875e3  mov     ecx, 1
0x1800875e8  lea     rdx, aPatchdbInstall_1; "PatchDb_InstallDrvPatch"
0x1800875ef  call    AslLogCallPrintf
0x1800875f4  jmp     loc_18008779E
0x1800875f9  lea     rcx, [rbp+580h+FileName]; FileName
0x180087600  call    cs:__imp_RtlDoesFileExists_U
0x180087606  test    al, al
0x180087608  jz      loc_18008779C
0x18008760e  call    cs:__imp_RtlGetNtSystemRoot
0x180087614  lea     r8, aSApppatchDrvpa_0; "%s\\apppatch\\drvpatch.sdb"
0x18008761b  mov     rdx, r14; unsigned __int64
0x18008761e  mov     r9, rax
0x180087621  lea     rcx, [rsp+680h+ExistingFileName]; unsigned __int16 *
0x180087626  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008762b  mov     ebx, eax
0x18008762d  test    eax, eax
0x18008762f  jns     short loc_18008764F
0x180087631  and     eax, 1FFF0000h
0x180087636  cmp     eax, 70000h
0x18008763b  jnz     short loc_180087640
0x18008763d  movzx   ebx, bx
0x180087640  lea     r9, aFailedToExpand_12; "Failed to expand drv patch path %d"
0x180087647  mov     r8d, 76Fh
0x18008764d  jmp     short loc_1800875DF
0x18008764f  lea     rcx, [rsp+680h+ExistingFileName]; FileName
0x180087654  xor     esi, esi
0x180087656  call    cs:__imp_RtlDoesFileExists_U
0x18008765c  lea     edi, [rsi+1]
0x18008765f  test    al, al
0x180087661  jz      loc_1800876E9
0x180087667  call    cs:__imp_RtlGetNtSystemRoot
0x18008766d  lea     r8, aSApppatchDrvpa; "%s\\apppatch\\drvpatch.sdb.bak"
0x180087674  mov     rdx, r14; unsigned __int64
0x180087677  mov     r9, rax
0x18008767a  lea     rcx, [rbp+580h+NewFileName]; unsigned __int16 *
0x180087681  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180087686  mov     ebx, eax
0x180087688  test    eax, eax
0x18008768a  jns     short loc_1800876B3
0x18008768c  and     eax, 1FFF0000h
0x180087691  cmp     eax, 70000h
0x180087696  jnz     short loc_18008769B
0x180087698  movzx   ebx, bx
0x18008769b  mov     [rsp+680h+var_660], ebx
0x18008769f  lea     r9, aFailedToExpand_2; "Failed to expand drv patch temp path st"...
0x1800876a6  mov     r8d, 77Ch
0x1800876ac  mov     ecx, edi
0x1800876ae  jmp     loc_1800875E8
0x1800876b3  mov     r8d, edi; dwFlags
0x1800876b6  lea     rdx, [rbp+580h+NewFileName]; lpNewFileName
0x1800876bd  lea     rcx, [rsp+680h+ExistingFileName]; lpExistingFileName
0x1800876c2  call    cs:__imp_MoveFileExW
0x1800876c8  test    eax, eax
0x1800876ca  jnz     short loc_1800876E7
0x1800876cc  call    cs:__imp_GetLastError
0x1800876d2  mov     [rsp+680h+var_660], eax
0x1800876d6  lea     r9, aFailedToMoveTh; "Failed to move the old drvpatch.sdb to "...
0x1800876dd  mov     ebx, eax
0x1800876df  mov     r8d, 782h
0x1800876e5  jmp     short loc_1800876AC
0x1800876e7  mov     esi, edi
0x1800876e9  xor     r8d, r8d; bFailIfExists
0x1800876ec  lea     rdx, [rsp+680h+ExistingFileName]; lpNewFileName
0x1800876f1  lea     rcx, [rbp+580h+FileName]; lpExistingFileName
0x1800876f8  call    cs:__imp_CopyFileW
0x1800876fe  test    eax, eax
0x180087700  jnz     short loc_180087762
0x180087702  call    cs:__imp_GetLastError
0x180087708  lea     r9, aFailedToCopyEx_2; "Failed to copy extracted drvpatch.sdb t"...
0x18008770f  mov     r8d, 78Dh
0x180087715  lea     rdx, aPatchdbInstall_1; "PatchDb_InstallDrvPatch"
0x18008771c  mov     [rsp+680h+var_660], eax
0x180087720  mov     ecx, edi
0x180087722  mov     ebx, eax
0x180087724  call    AslLogCallPrintf
0x180087729  test    esi, esi
0x18008772b  jz      short loc_18008779E
0x18008772d  xor     r8d, r8d; dwFlags
0x180087730  lea     rdx, [rsp+680h+ExistingFileName]; lpNewFileName
0x180087735  lea     rcx, [rbp+580h+NewFileName]; lpExistingFileName
0x18008773c  call    cs:__imp_MoveFileExW
0x180087742  test    eax, eax
0x180087744  jnz     short loc_18008779E
0x180087746  call    cs:__imp_GetLastError
0x18008774c  mov     [rsp+680h+var_660], eax
0x180087750  lea     r9, aFailedToMoveBa; "Failed to move backup drvpatch.sdb to d"...
0x180087757  mov     r8d, 792h
0x18008775d  jmp     loc_1800876AC
0x180087762  test    esi, esi
0x180087764  jz      short loc_18008779C
0x180087766  lea     rcx, [rbp+580h+NewFileName]; lpFileName
0x18008776d  call    cs:__imp_DeleteFileW
0x180087773  test    eax, eax
0x180087775  jnz     short loc_18008779C
0x180087777  call    cs:__imp_GetLastError
0x18008777d  lea     r9, aFailedToDelete_3; "Failed to delete temp drvpatch.sdb %d"
0x180087784  mov     r8d, 799h
0x18008778a  lea     rdx, aPatchdbInstall_1; "PatchDb_InstallDrvPatch"
0x180087791  mov     [rsp+680h+var_660], eax
0x180087795  mov     ecx, edi
0x180087797  call    AslLogCallPrintf
0x18008779c  xor     ebx, ebx
0x18008779e  mov     eax, ebx
0x1800877a0  mov     rcx, [rbp+580h+var_20]
0x1800877a7  xor     rcx, rsp; StackCookie
0x1800877aa  call    __security_check_cookie
0x1800877af  lea     r11, [rsp+680h+var_10]
0x1800877b7  mov     rbx, [r11+28h]
0x1800877bb  mov     rsi, [r11+30h]
0x1800877bf  mov     rsp, r11
0x1800877c2  pop     r14
0x1800877c4  pop     rdi
0x1800877c5  pop     rbp
0x1800877c6  retn
```
