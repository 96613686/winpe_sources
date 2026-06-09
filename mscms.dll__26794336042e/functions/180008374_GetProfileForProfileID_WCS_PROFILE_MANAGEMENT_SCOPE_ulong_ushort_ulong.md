# GetProfileForProfileID(WCS_PROFILE_MANAGEMENT_SCOPE,ulong,ushort *,ulong *)

- ea: `0x180008374`
- end: `0x1800087d1`
- name: `?GetProfileForProfileID@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@KPEAGPEAK@Z`
- size: `1117`
- prototype: `unsigned int(enum WCS_PROFILE_MANAGEMENT_SCOPE, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180007b70`
- `0x18000e184`
- `0x18002195c`
- `0x1800461b0`

## callees

- `0x180008374`
- `0x1800089d8`
- `0x180008bf0`
- `0x180008cc0`
- `0x1800097bc`
- `0x180009810`
- `0x180029f14`
- `0x18002e5f0`
- `0x18002f2f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000848b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800084da`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000848b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800084da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000845a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000845a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800086ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800086ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000877a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000879b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000877a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008791`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000879b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008598`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008598`

## pseudocode

```c
__int64 __fastcall GetProfileForProfileID(
        enum WCS_PROFILE_MANAGEMENT_SCOPE a1,
        DWORD a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  int v8; // eax
  DWORD LastError; // ebx
  signed int i; // r8d
  __int64 v11; // rdx
  char *v12; // rax
  LSTATUS v13; // eax
  DWORD v14; // edx
  const unsigned __int16 *FilenameFromPath; // rbx
  int v16; // r15d
  __int64 v17; // rcx
  int v18; // ecx
  unsigned int v19; // edx
  unsigned int v20; // r9d
  __int64 v21; // r8
  __int64 v22; // rax
  BYTE *v23; // rcx
  unsigned __int16 *v24; // rcx
  unsigned int v25; // edx
  unsigned __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rdx
  unsigned int v29; // ecx
  DWORD pdwSize; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ValueName[12]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Data[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR SubKey[264]; // [rsp+480h] [rbp+380h] BYREF

  memset_0(Data, 0, 0x208u);
  cbData = 0;
  hKey = 0;
  Type = 0;
  v8 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", gszICMRegPath, gszRegisteredProfiles);
  LastError = v8;
  if ( v8 < 0 )
    goto LABEL_49;
  pdwSize = a2;
  for ( i = 0; (unsigned int)i < 4; ++i )
  {
    v11 = i;
    v12 = (char *)&pdwSize - i + 3;
    ValueName[v11] = *v12;
  }
  ValueName[4] = 0;
  LastError = RegOpenKeyExW(
                (HKEY)(-(__int64)(a1 != WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE) - 2147483646),
                SubKey,
                0,
                0x20119u,
                &hKey);
  if ( LastError )
    goto LABEL_46;
  v13 = RegQueryValueExW(hKey, ValueName, 0, &Type, 0, &cbData);
  LastError = v13;
  if ( v13 )
  {
    if ( v13 != 2 || a1 || a2 != 1466527264 && a2 != 1934772034 )
      goto LABEL_46;
    v26 = *a4;
    pdwSize = 520;
    if ( !GetColorDirectoryW(0, FileName, &pdwSize) )
    {
      LastError = GetLastError();
      goto LABEL_46;
    }
    v27 = -1;
    v28 = -1;
    do
      ++v28;
    while ( gszBackslash[v28] );
    do
      ++v27;
    while ( gszsRGBProfile[v27] );
    v29 = v28 + (pdwSize >> 1) + v27;
    *a4 = v29;
    if ( !a3 )
      goto LABEL_55;
    if ( v29 > (unsigned int)v26 )
    {
LABEL_45:
      LastError = 122;
      goto LABEL_46;
    }
    v8 = StringCchPrintfW(a3, v26, L"%s%s%s", FileName, gszBackslash, gszsRGBProfile);
    LastError = v8;
    if ( v8 >= 0 )
    {
LABEL_55:
      LastError = 0;
      goto LABEL_46;
    }
LABEL_49:
    if ( (v8 & 0x1FFF0000) == 0x70000 )
      LastError = (unsigned __int16)LastError;
    goto LABEL_46;
  }
  if ( cbData > 0x208 || Type != 1 )
    goto LABEL_51;
  LastError = RegQueryValueExW(hKey, ValueName, 0, 0, (LPBYTE)Data, &cbData);
  if ( LastError )
    goto LABEL_46;
  if ( (cbData & 1) != 0 || FileName[((unsigned __int64)cbData >> 1) + 263] )
    goto LABEL_51;
  if ( (unsigned int)IsCustomWorkingSpaceProfile(a2) )
    goto LABEL_25;
  pdwSize = 520;
  FilenameFromPath = GetFilenameFromPath(Data);
  if ( !FilenameFromPath )
  {
    LastError = 87;
    goto LABEL_46;
  }
  v16 = 0;
  if ( !InternalGetColorDirectory(0, FileName, &pdwSize) )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      goto LABEL_22;
    }
LABEL_51:
    LastError = -2147467259;
    goto LABEL_46;
  }
  v17 = -1;
  do
    ++v17;
  while ( FileName[v17] );
  if ( ValueName[v17 + 11] != 92 && (v18 = StringCchCatW(FileName, 0x104u, gszBackslash), v18 < 0)
    || (v18 = StringCchCatW(FileName, 0x104u, FilenameFromPath), v18 < 0) )
  {
    LastError = (unsigned __int16)v18;
    if ( (v18 & 0x1FFF0000) != 0x70000 )
      LastError = v18;
LABEL_22:
    if ( LastError )
      goto LABEL_46;
    goto LABEL_23;
  }
  LastError = 0;
  LOBYTE(v16) = GetFileAttributesW(FileName) != -1;
LABEL_23:
  if ( !v16 )
  {
    LastError = 2;
    goto LABEL_46;
  }
  v14 = cbData;
LABEL_25:
  v19 = v14 >> 1;
  v20 = v19;
  if ( !a3 )
  {
LABEL_35:
    *a4 = v20;
    goto LABEL_46;
  }
  if ( *a4 < v19 )
    goto LABEL_45;
  v21 = v19;
  if ( v19 )
  {
    v22 = 2147483646;
    v23 = (BYTE *)Data;
    do
    {
      if ( !v22 )
        break;
      if ( !*(_WORD *)v23 )
        break;
      *a3 = *(_WORD *)v23;
      v23 += 2;
      ++a3;
      --v22;
      --v21;
    }
    while ( v21 );
    v24 = a3 - 1;
    v25 = v21 == 0 ? 0x8007007A : 0;
    if ( v21 )
      v24 = a3;
    *v24 = 0;
    if ( v21 )
      goto LABEL_35;
  }
  else
  {
    v25 = -2147024809;
  }
  LastError = (unsigned __int16)v25;
  if ( (v25 & 0x1FFF0000) != 0x70000 )
    LastError = v25;
LABEL_46:
  if ( hKey )
    RegCloseKey(hKey);
  return LastError;
}

```

## disassembly

```asm
0x180008374  mov     [rsp-8+arg_0], rbx
0x180008379  push    rbp
0x18000837a  push    rsi
0x18000837b  push    rdi
0x18000837c  push    r12
0x18000837e  push    r13
0x180008380  push    r14
0x180008382  push    r15
0x180008384  lea     rbp, [rsp-5A0h]
0x18000838c  sub     rsp, 6A0h
0x180008393  mov     rax, cs:__security_cookie
0x18000839a  xor     rax, rsp
0x18000839d  mov     [rbp+5D0h+var_40], rax
0x1800083a4  mov     r14, r8
0x1800083a7  mov     edi, edx
0x1800083a9  mov     esi, ecx
0x1800083ab  xor     edx, edx; Val
0x1800083ad  mov     r8d, 208h; Size
0x1800083b3  lea     rcx, [rbp+5D0h+Data]; void *
0x1800083ba  mov     r12, r9
0x1800083bd  call    memset_0
0x1800083c2  xor     r13d, r13d
0x1800083c5  lea     r9, gszICMRegPath; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800083cc  mov     eax, esi
0x1800083ce  mov     [rsp+6D0h+cbData], r13d
0x1800083d3  neg     eax
0x1800083d5  mov     [rsp+6D0h+hKey], r13
0x1800083da  lea     rax, gszRegisteredProfiles; "RegisteredProfiles"
0x1800083e1  mov     [rsp+6D0h+Type], r13d
0x1800083e6  lea     r8, aSS; "%s\\%s"
0x1800083ed  mov     [rsp+6D0h+phkResult], rax
0x1800083f2  mov     edx, 104h; unsigned __int64
0x1800083f7  lea     rcx, [rbp+5D0h+SubKey]; unsigned __int16 *
0x1800083fe  sbb     r15, r15
0x180008401  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008406  mov     ebx, eax
0x180008408  test    eax, eax
0x18000840a  js      loc_180008721
0x180008410  mov     [rsp+6D0h+pdwSize], edi
0x180008414  mov     r8d, r13d
0x180008417  movsxd  rdx, r8d
0x18000841a  lea     rax, [rsp+6D0h+pdwSize+3]
0x18000841f  sub     rax, rdx
0x180008422  inc     r8d
0x180008425  movsx   eax, byte ptr [rax]
0x180008428  mov     [rsp+rdx*2+6D0h+ValueName], ax
0x18000842d  cmp     r8d, 4
0x180008431  jb      short loc_180008417
0x180008433  lea     rax, [rsp+6D0h+hKey]
0x180008438  mov     [rsp+6D0h+var_680], r13w
0x18000843e  mov     r9d, 20119h; samDesired
0x180008444  mov     [rsp+6D0h+phkResult], rax; phkResult
0x180008449  xor     r8d, r8d; ulOptions
0x18000844c  lea     rdx, [rbp+5D0h+SubKey]; lpSubKey
0x180008453  lea     rcx, [r15-7FFFFFFEh]; hKey
0x18000845a  call    cs:__imp_RegOpenKeyExW
0x180008460  mov     ebx, eax
0x180008462  test    eax, eax
0x180008464  jnz     loc_1800086E5
0x18000846a  mov     rcx, [rsp+6D0h+hKey]; hKey
0x18000846f  lea     rax, [rsp+6D0h+cbData]
0x180008474  mov     [rsp+6D0h+lpcbData], rax; lpcbData
0x180008479  lea     r9, [rsp+6D0h+Type]; lpType
0x18000847e  xor     r8d, r8d; lpReserved
0x180008481  mov     [rsp+6D0h+phkResult], r13; lpData
0x180008486  lea     rdx, [rsp+6D0h+ValueName]; lpValueName
0x18000848b  call    cs:__imp_RegQueryValueExW
0x180008491  mov     ebx, eax
0x180008493  test    eax, eax
0x180008495  jnz     loc_180008662
0x18000849b  cmp     [rsp+6D0h+cbData], 208h
0x1800084a3  ja      loc_180008736
0x1800084a9  cmp     [rsp+6D0h+Type], 1
0x1800084ae  jnz     loc_180008736
0x1800084b4  mov     rcx, [rsp+6D0h+hKey]; hKey
0x1800084b9  lea     rax, [rsp+6D0h+cbData]
0x1800084be  mov     [rsp+6D0h+lpcbData], rax; lpcbData
0x1800084c3  lea     rdx, [rsp+6D0h+ValueName]; lpValueName
0x1800084c8  lea     rax, [rbp+5D0h+Data]
0x1800084cf  xor     r9d, r9d; lpType
0x1800084d2  xor     r8d, r8d; lpReserved
0x1800084d5  mov     [rsp+6D0h+phkResult], rax; lpData
0x1800084da  call    cs:__imp_RegQueryValueExW
0x1800084e0  mov     ebx, eax
0x1800084e2  test    eax, eax
0x1800084e4  jnz     loc_1800086E5
0x1800084ea  mov     edx, [rsp+6D0h+cbData]
0x1800084ee  test    dl, 1
0x1800084f1  jnz     loc_180008736
0x1800084f7  mov     eax, edx
0x1800084f9  shr     rax, 1
0x1800084fc  cmp     [rbp+rax*2+5D0h+var_462], r13w
0x180008505  jnz     loc_180008736
0x18000850b  mov     ecx, edi; unsigned int
0x18000850d  call    ?IsCustomWorkingSpaceProfile@@YAHK@Z; IsCustomWorkingSpaceProfile(ulong)
0x180008512  mov     edi, 1FFF0000h
0x180008517  mov     esi, 70000h
0x18000851c  test    eax, eax
0x18000851e  jnz     loc_1800085E7
0x180008524  lea     rcx, [rbp+5D0h+Data]; lpStringSource
0x18000852b  mov     [rsp+6D0h+pdwSize], 208h
0x180008533  call    GetFilenameFromPath
0x180008538  mov     rbx, rax
0x18000853b  test    rax, rax
0x18000853e  jz      loc_180008787
0x180008544  lea     r8, [rsp+6D0h+pdwSize]; pcbNeeded
0x180008549  xor     ecx, ecx; pName
0x18000854b  lea     rdx, [rsp+6D0h+FileName]; unsigned __int16 *
0x180008550  mov     r15d, r13d
0x180008553  call    ?InternalGetColorDirectory@@YAHPEBGPEAGPEAK@Z; InternalGetColorDirectory(ushort const *,ushort *,ulong *)
0x180008558  test    eax, eax
0x18000855a  jz      loc_180008791
0x180008560  lea     rax, [rsp+6D0h+FileName]
0x180008565  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008569  inc     rcx
0x18000856c  cmp     [rax+rcx*2], r13w
0x180008571  jnz     short loc_180008569
0x180008573  cmp     [rsp+rcx*2+6D0h+var_672], 5Ch ; '\'
0x180008579  jnz     short loc_1800085AA
0x18000857b  mov     r8, rbx; unsigned __int16 *
0x18000857e  lea     rcx, [rsp+6D0h+FileName]; unsigned __int16 *
0x180008583  mov     edx, 104h; unsigned __int64
0x180008588  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000858d  mov     ecx, eax
0x18000858f  test    eax, eax
0x180008591  js      short loc_1800085C6
0x180008593  lea     rcx, [rsp+6D0h+FileName]; lpFileName
0x180008598  call    cs:__imp_GetFileAttributesW
0x18000859e  cmp     eax, 0FFFFFFFFh
0x1800085a1  mov     ebx, r13d
0x1800085a4  setnz   r15b
0x1800085a8  jmp     short loc_1800085DA
0x1800085aa  lea     r8, gszBackslash; "\\"
0x1800085b1  mov     edx, 104h; unsigned __int64
0x1800085b6  lea     rcx, [rsp+6D0h+FileName]; unsigned __int16 *
0x1800085bb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800085c0  mov     ecx, eax
0x1800085c2  test    eax, eax
0x1800085c4  jns     short loc_18000857B
0x1800085c6  mov     eax, ecx
0x1800085c8  movzx   ebx, cx
0x1800085cb  and     eax, edi
0x1800085cd  cmp     eax, esi
0x1800085cf  cmovnz  ebx, ecx
0x1800085d2  test    ebx, ebx
0x1800085d4  jnz     loc_1800086E5
0x1800085da  test    r15d, r15d
0x1800085dd  jz      loc_1800087A8
0x1800085e3  mov     edx, [rsp+6D0h+cbData]
0x1800085e7  shr     edx, 1
0x1800085e9  mov     r9d, edx
0x1800085ec  test    r14, r14
0x1800085ef  jz      short loc_180008659
0x1800085f1  cmp     [r12], r9d
0x1800085f5  jb      loc_1800086E0
0x1800085fb  mov     r8d, r9d
0x1800085fe  test    edx, edx
0x180008600  jz      loc_1800087B2
0x180008606  mov     eax, 7FFFFFFEh
0x18000860b  lea     rcx, [rbp+5D0h+Data]
0x180008612  test    rax, rax
0x180008615  jz      short loc_180008634
0x180008617  movzx   edx, word ptr [rcx]
0x18000861a  test    dx, dx
0x18000861d  jz      short loc_180008634
0x18000861f  mov     [r14], dx
0x180008623  add     rcx, 2
0x180008627  add     r14, 2
0x18000862b  dec     rax
0x18000862e  sub     r8, 1
0x180008632  jnz     short loc_180008612
0x180008634  mov     rax, r8
0x180008637  lea     rcx, [r14-2]
0x18000863b  neg     rax
0x18000863e  sbb     edx, edx
0x180008640  not     edx
0x180008642  and     edx, 8007007Ah
0x180008648  test    r8, r8
0x18000864b  cmovnz  rcx, r14
0x18000864f  mov     [rcx], r13w
0x180008653  jz      loc_1800087C0
0x180008659  mov     [r12], r9d
0x18000865d  jmp     loc_1800086E5
0x180008662  cmp     eax, 2
0x180008665  jnz     short loc_1800086E5
0x180008667  test    esi, esi
0x180008669  jnz     short loc_1800086E5
0x18000866b  cmp     edi, 57696E20h
0x180008671  jnz     loc_18000873D
0x180008677  mov     ebx, [r12]
0x18000867b  lea     r8, [rsp+6D0h+pdwSize]; pdwSize
0x180008680  lea     rdx, [rsp+6D0h+FileName]; pBuffer
0x180008685  mov     [rsp+6D0h+pdwSize], 208h
0x18000868d  xor     ecx, ecx; pMachineName
0x18000868f  call    GetColorDirectoryW
0x180008694  test    eax, eax
0x180008696  jz      loc_18000877A
0x18000869c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800086a0  lea     r8, gszBackslash; "\\"
0x1800086a7  mov     rdx, rcx
0x1800086aa  inc     rdx
0x1800086ad  cmp     [r8+rdx*2], r13w
0x1800086b2  jnz     short loc_1800086AA
0x1800086b4  lea     r9, gszsRGBProfile; "sRGB Color Space Profile.icm"
0x1800086bb  inc     rcx
0x1800086be  cmp     [r9+rcx*2], r13w
0x1800086c3  jnz     short loc_1800086BB
0x1800086c5  mov     eax, [rsp+6D0h+pdwSize]
0x1800086c9  shr     eax, 1
0x1800086cb  add     ecx, eax
0x1800086cd  add     ecx, edx
0x1800086cf  mov     [r12], ecx
0x1800086d3  test    r14, r14
0x1800086d6  jz      loc_180008772
0x1800086dc  cmp     ecx, ebx
0x1800086de  jbe     short loc_18000874B
0x1800086e0  mov     ebx, 7Ah ; 'z'
0x1800086e5  mov     rcx, [rsp+6D0h+hKey]; hKey
0x1800086ea  test    rcx, rcx
0x1800086ed  jz      short loc_1800086F5
0x1800086ef  call    cs:__imp_RegCloseKey
0x1800086f5  mov     eax, ebx
0x1800086f7  mov     rcx, [rbp+5D0h+var_40]
0x1800086fe  xor     rcx, rsp; StackCookie
0x180008701  call    __security_check_cookie
0x180008706  mov     rbx, [rsp+6D0h+arg_0]
0x18000870e  add     rsp, 6A0h
0x180008715  pop     r15
0x180008717  pop     r14
0x180008719  pop     r13
0x18000871b  pop     r12
0x18000871d  pop     rdi
0x18000871e  pop     rsi
0x18000871f  pop     rbp
0x180008720  retn
0x180008721  mov     edi, 1FFF0000h
0x180008726  mov     esi, 70000h
0x18000872b  and     eax, edi
0x18000872d  cmp     eax, esi
0x18000872f  jnz     short loc_1800086E5
0x180008731  movzx   ebx, bx
0x180008734  jmp     short loc_1800086E5
0x180008736  mov     ebx, 80004005h
0x18000873b  jmp     short loc_1800086E5
0x18000873d  cmp     edi, 73524742h
0x180008743  jz      loc_180008677
0x180008749  jmp     short loc_1800086E5
0x18000874b  mov     [rsp+6D0h+lpcbData], r9
0x180008750  mov     rdx, rbx; unsigned __int64
0x180008753  mov     [rsp+6D0h+phkResult], r8
0x180008758  lea     r9, [rsp+6D0h+FileName]
0x18000875d  lea     r8, aSSS_0; "%s%s%s"
0x180008764  mov     rcx, r14; unsigned __int16 *
0x180008767  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000876c  mov     ebx, eax
0x18000876e  test    eax, eax
0x180008770  js      short loc_180008721
0x180008772  mov     ebx, r13d
0x180008775  jmp     loc_1800086E5
0x18000877a  call    cs:__imp_GetLastError
0x180008780  mov     ebx, eax
0x180008782  jmp     loc_1800086E5
0x180008787  mov     ebx, 57h ; 'W'
0x18000878c  jmp     loc_1800086E5
0x180008791  call    cs:__imp_GetLastError
0x180008797  test    eax, eax
0x180008799  jz      short loc_180008736
0x18000879b  call    cs:__imp_GetLastError
0x1800087a1  mov     ebx, eax
0x1800087a3  jmp     loc_1800085D2
0x1800087a8  mov     ebx, 2
0x1800087ad  jmp     loc_1800086E5
0x1800087b2  mov     edx, 80070057h
0x1800087b7  test    r9d, r9d
0x1800087ba  jz      short loc_1800087C0
0x1800087bc  mov     [r14], r13w
0x1800087c0  mov     eax, edx
0x1800087c2  movzx   ebx, dx
0x1800087c5  and     eax, edi
0x1800087c7  cmp     eax, esi
0x1800087c9  cmovnz  ebx, edx
0x1800087cc  jmp     loc_1800086E5
```
