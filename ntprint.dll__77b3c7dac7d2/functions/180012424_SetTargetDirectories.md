# SetTargetDirectories

- ea: `0x180012424`
- end: `0x180012b1f`
- name: `SetTargetDirectories`
- size: `1787`
- prototype: `__int64 __usercall@<rax>(struct _PSETUP_LOCAL_DATA *@<rcx>, char)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, installer_update`

## callers

- `0x180019908`
- `0x18001f958`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000797c`
- `0x18000b314`
- `0x18000d57c`
- `0x18000d624`
- `0x180012424`
- `0x18001b3f8`
- `0x18001bc44`
- `0x180020624`
- `0x180023900`
- `0x180036248`
- `0x1800367b0`
- `0x180036c28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001297e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001297e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001278e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001278e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012b14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125cd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800127fa`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800127fa`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180012b04`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180012b04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012734`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012912`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012734`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012912`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800128ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800128ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001267b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001267b`
- `SETUPAPI!SetupGetFieldCount` at `0x18001253b`
- `SETUPAPI!SetupGetFieldCount` at `0x18001253b`
- `SETUPAPI!SetupSetDirectoryIdW` at `0x180012ab8`
- `SETUPAPI!SetupSetDirectoryIdW` at `0x180012ab8`
- `SETUPAPI!SetupGetIntField` at `0x180012568`
- `SETUPAPI!SetupGetIntField` at `0x180012568`
- `SETUPAPI!SetupGetLineCountW` at `0x1800124e3`
- `SETUPAPI!SetupGetLineCountW` at `0x1800124e3`
- `SETUPAPI!SetupGetLineByIndexW` at `0x180012528`
- `SETUPAPI!SetupGetLineByIndexW` at `0x180012528`
- `WINSPOOL!GetPrintProcessorDirectoryW` at `0x1800126da`
- `WINSPOOL!GetPrintProcessorDirectoryW` at `0x1800126da`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180012a66`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180012a66`
- `mscms!GetColorDirectoryW` at `0x180012630`
- `mscms!GetColorDirectoryW` at `0x180012630`

## string_xrefs

- `0x180012a97`: `Setting directory ID to %ws`

## pseudocode

```c
__int64 __fastcall SetTargetDirectories(struct _PSETUP_LOCAL_DATA *a1, int a2, WCHAR *a3, void *a4, char a5)
{
  int v6; // esi
  HINF v8; // r15
  __int64 v9; // r8
  DWORD v10; // r12d
  unsigned int v11; // r14d
  DWORD v12; // ebx
  DWORD v13; // r15d
  UINT SystemDirectoryW; // eax
  DWORD LastError; // eax
  const unsigned __int16 *v17; // r8
  WCHAR *v18; // r8
  int v19; // eax
  __int16 v20; // r11
  void *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // ebx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rax
  unsigned int v30; // esi
  unsigned __int16 *v31; // rax
  unsigned __int16 *v32; // rbx
  __int64 v33; // r11
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rax
  wchar_t *v37; // rax
  const unsigned __int16 *v38; // r8
  __int64 v39; // rax
  DWORD pdwSize; // [rsp+30h] [rbp-D0h] BYREF
  int IntegerValue; // [rsp+34h] [rbp-CCh] BYREF
  DWORD FieldCount; // [rsp+38h] [rbp-C8h]
  int v43; // [rsp+3Ch] [rbp-C4h]
  unsigned int LineCountW; // [rsp+40h] [rbp-C0h]
  HINF InfHandle; // [rsp+48h] [rbp-B8h]
  struct _INFCONTEXT Context; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v47; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR PathName[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR pBuffer[264]; // [rsp+490h] [rbp+390h] BYREF
  BYTE pPrintProcessorInfo[2]; // [rsp+6A0h] [rbp+5A0h] BYREF
  BYTE pDriverDirectory[528]; // [rsp+8B0h] [rbp+7B0h] BYREF
  unsigned __int16 v53[264]; // [rsp+AC0h] [rbp+9C0h] BYREF

  v43 = a2;
  v6 = a2;
  InfHandle = a4;
  IntegerValue = 0;
  v8 = a4;
  memset_0(Buffer, 0, 0x208u);
  memset_0(pDriverDirectory, 0, 0x208u);
  memset_0(pPrintProcessorInfo, 0, 0x208u);
  memset_0(pBuffer, 0, 0x208u);
  v9 = *(_QWORD *)a1;
  memset(&Context, 0, sizeof(Context));
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "SetTargetDirectories",
    L"Setting the target directories for the files listed in %ws",
    v9);
  LineCountW = SetupGetLineCountW(v8, L"DestinationDirs");
  if ( LineCountW == -1 || !(unsigned int)SetupSkipDir() )
    goto LABEL_16;
  v10 = 0;
  v11 = 1;
  if ( !LineCountW )
  {
LABEL_83:
    ClassInstallerTelemetry::WriteDbgTraceInfo("SetTargetDirectories", L"Successfully set target directories.");
    return v11;
  }
  while ( 1 )
  {
    if ( !SetupGetLineByIndexW(v8, L"DestinationDirs", v10, &Context) )
      goto LABEL_16;
    FieldCount = SetupGetFieldCount(&Context);
    v12 = FieldCount;
    if ( FieldCount )
      break;
LABEL_82:
    if ( ++v10 >= LineCountW )
      goto LABEL_83;
  }
  v13 = 1;
  while ( !SetupGetIntField(&Context, v13, &IntegerValue) || IntegerValue < 0x8000 )
  {
LABEL_80:
    if ( ++v13 > v12 )
    {
      v8 = InfHandle;
      goto LABEL_82;
    }
  }
  if ( IntegerValue == 66000 )
  {
    if ( a5 < 0 )
    {
      v38 = (const unsigned __int16 *)*((_QWORD *)a1 + 29);
      if ( v38 )
      {
        if ( (int)StringCchCopyW(Buffer, 0x104u, v38) < 0 )
          goto LABEL_16;
      }
      else
      {
        if ( (int)GetUniqueTempDirInPrintShare(a3, PlatformEnv[v6], Buffer) < 0 )
          goto LABEL_16;
        v39 = AllocStr(Buffer);
        *((_QWORD *)a1 + 29) = v39;
        if ( !v39 )
          goto LABEL_16;
      }
      AddDirToDriverInfo(Buffer);
      goto LABEL_79;
    }
    if ( !*(_WORD *)pDriverDirectory )
    {
      pdwSize = 260;
      if ( !GetPrinterDriverDirectoryW(a3, (LPWSTR)PlatformEnv[v6], 1u, pDriverDirectory, 0x208u, &pdwSize) )
        goto LABEL_16;
    }
    v17 = (const unsigned __int16 *)pDriverDirectory;
    goto LABEL_78;
  }
  if ( IntegerValue != 66001 )
  {
    if ( IntegerValue == 66002 )
    {
      if ( (a5 & 0x24) == 0
        && v6 == MyPlatform
        && (a1 && (*((_BYTE *)a1 + 164) & 8) != 0 || (unsigned int)IsLocalMachine(a3)) )
      {
        SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
LABEL_15:
        if ( !SystemDirectoryW )
          goto LABEL_16;
        goto LABEL_79;
      }
      goto LABEL_27;
    }
    if ( IntegerValue != 66003 )
    {
      if ( IntegerValue == 66004 )
      {
        SystemDirectoryW = GetWebPageDir(a1, Buffer);
        goto LABEL_15;
      }
      goto LABEL_27;
    }
    if ( !pBuffer[0] )
    {
      pdwSize = 520;
      if ( !GetColorDirectoryW(a3, pBuffer, &pdwSize) )
        goto LABEL_16;
    }
    v17 = pBuffer;
LABEL_78:
    if ( (int)StringCchCopyW(Buffer, 0x104u, v17) < 0 )
      goto LABEL_16;
LABEL_79:
    ClassInstallerTelemetry::WriteDbgTraceInfo("SetTargetDirectories", L"Setting directory ID to %ws", Buffer);
    if ( !SetupSetDirectoryIdW(InfHandle, IntegerValue, Buffer) )
      goto LABEL_16;
    goto LABEL_80;
  }
  if ( (a5 & 4) != 0 )
  {
LABEL_27:
    v18 = (WCHAR *)gpszSkipDir;
LABEL_67:
    StringCchCopyW(Buffer, 0x104u, v18);
    goto LABEL_79;
  }
  if ( !*(_WORD *)pPrintProcessorInfo )
  {
    pdwSize = 260;
    if ( !GetPrintProcessorDirectoryW(a3, (LPWSTR)PlatformEnv[v6], 1u, pPrintProcessorInfo, 0x208u, &pdwSize) )
      goto LABEL_16;
  }
  if ( (int)StringCchCopyW(Buffer, 0x104u, (const unsigned __int16 *)pPrintProcessorInfo) < 0 )
    goto LABEL_16;
  v19 = IsLocalMachine(a3);
  v20 = 0;
  if ( !v19 && !(unsigned int)IsUNCPath(Buffer) )
  {
    if ( a1 )
    {
      v21 = (void *)*((_QWORD *)a1 + 25);
      if ( v21 )
      {
        LocalFree(v21);
        *((_QWORD *)a1 + 25) = 0;
      }
    }
    StringCchCopyW(Buffer, 0x104u, gpszSkipDir);
  }
  if ( !a1 )
    goto LABEL_79;
  v22 = *((_QWORD *)a1 + 25);
  if ( !v22 )
    goto LABEL_79;
  v23 = -1;
  do
    ++v23;
  while ( *(_WORD *)(v22 + 2 * v23) != v20 );
  if ( wcschr((const wchar_t *)(v22 + 2 * v23 + 2), 0x5Cu) )
  {
LABEL_61:
    v35 = *((_QWORD *)a1 + 25);
    v36 = -1;
    do
      ++v36;
    while ( *(_WORD *)(v35 + 2 * v36) );
    if ( (unsigned int)StrNCatBuff(PathName, 260, Buffer, L"\\", v35 + 2 + 2 * v36, 0) )
      goto LABEL_16;
    v37 = wcsrchr(PathName, 0x5Cu);
    if ( v37 )
      *v37 = 0;
    v18 = PathName;
    goto LABEL_67;
  }
  v24 = 1;
  while ( 1 )
  {
    StringCchPrintfW(&v47, 4u, L"%d", v24);
    if ( (unsigned int)StrNCatBuff(PathName, 260, Buffer, L"\\", &v47, 0) )
      break;
    if ( CreateDirectoryW(PathName, 0) )
    {
      v25 = AllocStr(PathName);
      *((_QWORD *)a1 + 26) = v25;
      if ( !v25 )
        break;
LABEL_49:
      if ( v24 == 500 )
      {
        SetLastError(2u);
        break;
      }
      v26 = *((_QWORD *)a1 + 25);
      v27 = -1;
      do
        ++v27;
      while ( *(_WORD *)(v26 + 2 * v27) );
      if ( (unsigned int)StrNCatBuff(v53, 260, &v47, L"\\", v26 + 2 + 2 * v27, 0) )
        goto LABEL_84;
      v28 = -1;
      do
        ++v28;
      while ( v53[v28] );
      v29 = -1;
      do
        ++v29;
      while ( *(_WORD *)(*((_QWORD *)a1 + 25) + 2 * v29) );
      v30 = v28 + v29 + 2;
      v31 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v30);
      v32 = v31;
      if ( !v31 )
      {
LABEL_84:
        RemoveDirectoryW(PathName);
        break;
      }
      StringCchCopyW(v31, v30, *((const unsigned __int16 **)a1 + 25));
      v34 = -1;
      do
        ++v34;
      while ( v32[v34] );
      StringCchCopyW(&v32[v34 + 1], v33 - v34 - 1, v53);
      LocalFree(*((HLOCAL *)a1 + 25));
      v6 = v43;
      *((_QWORD *)a1 + 25) = v32;
      v12 = FieldCount;
      goto LABEL_61;
    }
    if ( (int)++v24 >= 500 )
      goto LABEL_49;
  }
LABEL_16:
  v11 = 0;
  LastError = GetLastError();
  ClassInstallerTelemetry::WriteDbgTraceError("SetTargetDirectories", L"Error setting directories: %d", LastError);
  return v11;
}

```

## disassembly

```asm
0x180012424  push    rbp
0x180012426  push    rbx
0x180012427  push    rsi
0x180012428  push    rdi
0x180012429  push    r12
0x18001242b  push    r13
0x18001242d  push    r14
0x18001242f  push    r15
0x180012431  lea     rbp, [rsp-0BE8h]
0x180012439  sub     rsp, 0CE8h
0x180012440  mov     rax, cs:__security_cookie
0x180012447  xor     rax, rsp
0x18001244a  mov     [rbp+0C20h+var_50], rax
0x180012451  mov     r13, r8
0x180012454  mov     [rsp+0D20h+var_CE4], edx
0x180012458  mov     esi, edx
0x18001245a  mov     [rsp+0D20h+InfHandle], r9
0x18001245f  mov     rdi, rcx
0x180012462  mov     [rsp+0D20h+IntegerValue], 0
0x18001246a  mov     ebx, 208h
0x18001246f  lea     rcx, [rsp+0D20h+Buffer]; void *
0x180012474  mov     r8d, ebx; Size
0x180012477  xor     edx, edx; Val
0x180012479  mov     r15, r9
0x18001247c  call    memset_0
0x180012481  mov     r8d, ebx; Size
0x180012484  lea     rcx, [rbp+0C20h+pDriverDirectory]; void *
0x18001248b  xor     edx, edx; Val
0x18001248d  call    memset_0
0x180012492  mov     r8d, ebx; Size
0x180012495  lea     rcx, [rbp+0C20h+pPrintProcessorInfo]; void *
0x18001249c  xor     edx, edx; Val
0x18001249e  call    memset_0
0x1800124a3  mov     r8d, ebx; Size
0x1800124a6  lea     rcx, [rbp+0C20h+pBuffer]; void *
0x1800124ad  xor     edx, edx; Val
0x1800124af  call    memset_0
0x1800124b4  mov     r8, [rdi]
0x1800124b7  lea     rdx, aSettingTheTarg; "Setting the target directories for the "...
0x1800124be  xorps   xmm0, xmm0
0x1800124c1  lea     rcx, aSettargetdirec_1; "SetTargetDirectories"
0x1800124c8  xor     eax, eax
0x1800124ca  movups  xmmword ptr [rsp+0D20h+Context.Inf], xmm0
0x1800124cf  mov     qword ptr [rsp+0D20h+Context.Section], rax
0x1800124d4  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800124d9  lea     rdx, cszDestinationDirs; "DestinationDirs"
0x1800124e0  mov     rcx, r15; InfHandle
0x1800124e3  call    cs:__imp_SetupGetLineCountW
0x1800124e9  mov     [rsp+0D20h+var_CE0], eax
0x1800124ed  mov     ebx, eax
0x1800124ef  cmp     eax, 0FFFFFFFFh
0x1800124f2  jz      loc_1800125CA
0x1800124f8  call    SetupSkipDir
0x1800124fd  test    eax, eax
0x1800124ff  jz      loc_1800125CA
0x180012505  xor     eax, eax
0x180012507  mov     r12d, eax
0x18001250a  lea     r14d, [rax+1]
0x18001250e  test    ebx, ebx
0x180012510  jz      loc_180012AE5
0x180012516  lea     r9, [rsp+0D20h+Context]; Context
0x18001251b  mov     r8d, r12d; Index
0x18001251e  lea     rdx, cszDestinationDirs; "DestinationDirs"
0x180012525  mov     rcx, r15; InfHandle
0x180012528  call    cs:__imp_SetupGetLineByIndexW
0x18001252e  test    eax, eax
0x180012530  jz      loc_1800125CA
0x180012536  lea     rcx, [rsp+0D20h+Context]; Context
0x18001253b  call    cs:__imp_SetupGetFieldCount
0x180012541  mov     [rsp+0D20h+var_CE8], eax
0x180012545  mov     ebx, eax
0x180012547  test    eax, eax
0x180012549  jz      loc_180012AD7
0x18001254f  mov     r15d, r14d
0x180012552  cmp     eax, r14d
0x180012555  jb      loc_180012AD2
0x18001255b  lea     r8, [rsp+0D20h+IntegerValue]; IntegerValue
0x180012560  mov     edx, r15d; FieldIndex
0x180012563  lea     rcx, [rsp+0D20h+Context]; Context
0x180012568  call    cs:__imp_SetupGetIntField
0x18001256e  xor     r11d, r11d
0x180012571  test    eax, eax
0x180012573  jz      loc_180012AC6
0x180012579  mov     ecx, [rsp+0D20h+IntegerValue]
0x18001257d  cmp     ecx, 8000h
0x180012583  jl      loc_180012AC6
0x180012589  sub     ecx, 101D0h
0x18001258f  jz      loc_1800129A9
0x180012595  sub     ecx, r14d
0x180012598  jz      loc_180012692
0x18001259e  sub     ecx, r14d
0x1800125a1  jz      loc_180012646
0x1800125a7  sub     ecx, r14d
0x1800125aa  jz      short loc_18001260F
0x1800125ac  cmp     ecx, r14d
0x1800125af  jnz     loc_180012686
0x1800125b5  lea     rdx, [rsp+0D20h+Buffer]; unsigned __int16 *
0x1800125ba  mov     rcx, rdi; struct _PSETUP_LOCAL_DATA *
0x1800125bd  call    ?GetWebPageDir@@YAHPEAU_PSETUP_LOCAL_DATA@@QEAG@Z; GetWebPageDir(_PSETUP_LOCAL_DATA *,ushort * const)
0x1800125c2  test    eax, eax
0x1800125c4  jnz     loc_180012A92
0x1800125ca  xor     r14d, r14d
0x1800125cd  call    cs:__imp_GetLastError
0x1800125d3  mov     r8d, eax
0x1800125d6  lea     rdx, aErrorSettingDi; "Error setting directories: %d"
0x1800125dd  lea     rcx, aSettargetdirec_1; "SetTargetDirectories"
0x1800125e4  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800125e9  mov     eax, r14d
0x1800125ec  mov     rcx, [rbp+0C20h+var_50]
0x1800125f3  xor     rcx, rsp; StackCookie
0x1800125f6  call    __security_check_cookie
0x1800125fb  add     rsp, 0CE8h
0x180012602  pop     r15
0x180012604  pop     r14
0x180012606  pop     r13
0x180012608  pop     r12
0x18001260a  pop     rdi
0x18001260b  pop     rsi
0x18001260c  pop     rbx
0x18001260d  pop     rbp
0x18001260e  retn
0x18001260f  cmp     [rbp+0C20h+pBuffer], r11w
0x180012617  jnz     short loc_18001263A
0x180012619  lea     r8, [rsp+0D20h+pdwSize]; pdwSize
0x18001261e  mov     [rsp+0D20h+pdwSize], 208h
0x180012626  lea     rdx, [rbp+0C20h+pBuffer]; pBuffer
0x18001262d  mov     rcx, r13; pMachineName
0x180012630  call    cs:__imp_GetColorDirectoryW
0x180012636  test    eax, eax
0x180012638  jz      short loc_1800125CA
0x18001263a  lea     r8, [rbp+0C20h+pBuffer]
0x180012641  jmp     loc_180012A7B
0x180012646  test    [rbp+0C20h+arg_20], 24h
0x18001264d  jnz     short loc_180012686
0x18001264f  cmp     esi, cs:MyPlatform
0x180012655  jnz     short loc_180012686
0x180012657  test    rdi, rdi
0x18001265a  jz      short loc_180012665
0x18001265c  test    byte ptr [rdi+0A4h], 8
0x180012663  jnz     short loc_180012671
0x180012665  mov     rcx, r13; lpString1
0x180012668  call    IsLocalMachine
0x18001266d  test    eax, eax
0x18001266f  jz      short loc_180012686
0x180012671  mov     edx, 104h; uSize
0x180012676  lea     rcx, [rsp+0D20h+Buffer]; lpBuffer
0x18001267b  call    cs:__imp_GetSystemDirectoryW
0x180012681  jmp     loc_1800125C2
0x180012686  mov     r8, cs:gpszSkipDir
0x18001268d  jmp     loc_180012995
0x180012692  test    [rbp+0C20h+arg_20], 4
0x180012699  jnz     short loc_180012686
0x18001269b  cmp     word ptr [rbp+0C20h+pPrintProcessorInfo], r11w
0x1800126a3  jnz     short loc_1800126E8
0x1800126a5  lea     rax, [rsp+0D20h+pdwSize]
0x1800126aa  movsxd  rdx, esi
0x1800126ad  mov     [rsp+0D20h+pcbNeeded], rax; pcbNeeded
0x1800126b2  lea     r9, [rbp+0C20h+pPrintProcessorInfo]; pPrintProcessorInfo
0x1800126b9  lea     rax, PlatformEnv
0x1800126c0  mov     [rsp+0D20h+pdwSize], 104h
0x1800126c8  mov     r8d, r14d; Level
0x1800126cb  mov     [rsp+0D20h+cbBuf], 208h; cbBuf
0x1800126d3  mov     rdx, [rax+rdx*8]; pEnvironment
0x1800126d7  mov     rcx, r13; pName
0x1800126da  call    cs:__imp_GetPrintProcessorDirectoryW
0x1800126e0  test    eax, eax
0x1800126e2  jz      loc_1800125CA
0x1800126e8  lea     r8, [rbp+0C20h+pPrintProcessorInfo]; unsigned __int16 *
0x1800126ef  mov     edx, 104h; unsigned __int64
0x1800126f4  lea     rcx, [rsp+0D20h+Buffer]; unsigned __int16 *
0x1800126f9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800126fe  test    eax, eax
0x180012700  js      loc_1800125CA
0x180012706  mov     rcx, r13; lpString1
0x180012709  call    IsLocalMachine
0x18001270e  xor     r11d, r11d
0x180012711  test    eax, eax
0x180012713  jnz     short loc_18001275A
0x180012715  lea     rcx, [rsp+0D20h+Buffer]
0x18001271a  call    IsUNCPath
0x18001271f  test    eax, eax
0x180012721  jnz     short loc_18001275A
0x180012723  test    rdi, rdi
0x180012726  jz      short loc_180012744
0x180012728  mov     rcx, [rdi+0C8h]; hMem
0x18001272f  test    rcx, rcx
0x180012732  jz      short loc_180012744
0x180012734  call    cs:__imp_LocalFree
0x18001273a  xor     r11d, r11d
0x18001273d  mov     [rdi+0C8h], r11
0x180012744  mov     r8, cs:gpszSkipDir; unsigned __int16 *
0x18001274b  lea     rcx, [rsp+0D20h+Buffer]; unsigned __int16 *
0x180012750  mov     edx, 104h; unsigned __int64
0x180012755  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001275a  test    rdi, rdi
0x18001275d  jz      loc_180012A92
0x180012763  mov     rcx, [rdi+0C8h]
0x18001276a  test    rcx, rcx
0x18001276d  jz      loc_180012A92
0x180012773  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012777  inc     rax
0x18001277a  cmp     [rcx+rax*2], r11w
0x18001277f  jnz     short loc_180012777
0x180012781  lea     rcx, [rcx+rax*2]
0x180012785  mov     edx, 5Ch ; '\'; Ch
0x18001278a  add     rcx, 2; Str
0x18001278e  call    cs:__imp_wcschr
0x180012794  xor     edx, edx
0x180012796  test    rax, rax
0x180012799  jnz     loc_180012929
0x18001279f  mov     ebx, r14d
0x1800127a2  xor     esi, esi
0x1800127a4  mov     r9d, ebx
0x1800127a7  lea     r8, aD; "%d"
0x1800127ae  mov     edx, 4; unsigned __int64
0x1800127b3  lea     rcx, [rsp+0D20h+var_CB8]; unsigned __int16 *
0x1800127b8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800127bd  lea     rax, [rsp+0D20h+var_CB8]
0x1800127c2  mov     [rsp+0D20h+pcbNeeded], rsi
0x1800127c7  lea     r9, SubBlock; "\\"
0x1800127ce  mov     qword ptr [rsp+0D20h+cbBuf], rax
0x1800127d3  lea     r8, [rsp+0D20h+Buffer]
0x1800127d8  mov     edx, 104h
0x1800127dd  lea     rcx, [rbp+0C20h+PathName]
0x1800127e4  call    StrNCatBuff
0x1800127e9  test    eax, eax
0x1800127eb  jnz     loc_1800125CA
0x1800127f1  xor     edx, edx; lpSecurityAttributes
0x1800127f3  lea     rcx, [rbp+0C20h+PathName]; lpPathName
0x1800127fa  call    cs:__imp_CreateDirectoryW
0x180012800  test    eax, eax
0x180012802  jnz     short loc_180012811
0x180012804  add     ebx, r14d
0x180012807  cmp     ebx, 1F4h
0x18001280d  jl      short loc_1800127A4
0x18001280f  jmp     short loc_18001282D
0x180012811  lea     rcx, [rbp+0C20h+PathName]; unsigned __int16 *
0x180012818  call    AllocStr
0x18001281d  mov     [rdi+0D0h], rax
0x180012824  test    rax, rax
0x180012827  jz      loc_1800125CA
0x18001282d  cmp     ebx, 1F4h
0x180012833  jz      loc_180012B0F
0x180012839  mov     rcx, [rdi+0C8h]
0x180012840  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012844  mov     rax, rbx
0x180012847  inc     rax
0x18001284a  cmp     [rcx+rax*2], si
0x18001284e  jnz     short loc_180012847
0x180012850  add     rcx, 2
0x180012854  mov     [rsp+0D20h+pcbNeeded], rsi
0x180012859  lea     r9, SubBlock; "\\"
0x180012860  mov     edx, 104h
0x180012865  lea     r8, [rsp+0D20h+var_CB8]
0x18001286a  lea     rax, [rcx+rax*2]
0x18001286e  lea     rcx, [rbp+0C20h+var_260]
0x180012875  mov     qword ptr [rsp+0D20h+cbBuf], rax
0x18001287a  call    StrNCatBuff
0x18001287f  test    eax, eax
0x180012881  jnz     loc_180012AFD
0x180012887  lea     rax, [rbp+0C20h+var_260]
0x18001288e  mov     rcx, rbx
0x180012891  inc     rcx
0x180012894  cmp     [rax+rcx*2], si
0x180012898  jnz     short loc_180012891
0x18001289a  mov     rdx, [rdi+0C8h]
0x1800128a1  mov     rax, rbx
0x1800128a4  inc     rax
0x1800128a7  cmp     [rdx+rax*2], si
0x1800128ab  jnz     short loc_1800128A4
0x1800128ad  lea     esi, [rax+2]
0x1800128b0  add     esi, ecx
0x1800128b2  mov     ecx, 40h ; '@'; uFlags
0x1800128b7  lea     edx, [rsi+rsi]; uBytes
0x1800128ba  call    cs:__imp_LocalAlloc
0x1800128c0  mov     rbx, rax
0x1800128c3  test    rax, rax
0x1800128c6  jz      loc_180012AFD
0x1800128cc  mov     r8, [rdi+0C8h]; unsigned __int16 *
0x1800128d3  mov     rcx, rax; unsigned __int16 *
0x1800128d6  mov     edx, esi; unsigned __int64
0x1800128d8  mov     r11d, esi
0x1800128db  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800128e0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800128e4  xor     eax, eax
0x1800128e6  inc     rcx
0x1800128e9  cmp     [rbx+rcx*2], ax
0x1800128ed  jnz     short loc_1800128E6
0x1800128ef  sub     r11, rcx
0x1800128f2  lea     r8, [rbp+0C20h+var_260]; unsigned __int16 *
0x1800128f9  inc     rcx
0x1800128fc  sub     r11, r14
0x1800128ff  mov     rdx, r11; unsigned __int64
0x180012902  lea     rcx, [rbx+rcx*2]; unsigned __int16 *
0x180012906  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001290b  mov     rcx, [rdi+0C8h]; hMem
0x180012912  call    cs:__imp_LocalFree
0x180012918  mov     esi, [rsp+0D20h+var_CE4]
0x18001291c  xor     edx, edx
0x18001291e  mov     [rdi+0C8h], rbx
  ... truncated ...
```
