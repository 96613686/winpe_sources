# RegScanUtil::ScanFiles(RegScanUtil::FILE_SCAN_ENUM)

- ea: `0x18002fbb8`
- end: `0x18002ffb9`
- name: `?ScanFiles@RegScanUtil@@CAXW4FILE_SCAN_ENUM@1@@Z`
- size: `1025`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002ffc0`
- `0x18003c380`

## callees

- `0x18000a01c`
- `0x18001ec1c`
- `0x18002f9a0`
- `0x18002fbb8`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ff70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fd5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fd5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ff90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ff90`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002fdcd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002fdcd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ff49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ff49`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002ff80`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002ff80`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002fcdc`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002fcdc`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002fcc5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002fcc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002fe01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002fe5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002fe01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002fe5f`

## string_xrefs

- `0x18002fd4d`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SharedDlls`

## pseudocode

```c
int __fastcall RegScanUtil::ScanFiles(int a1)
{
  __int64 v2; // r11
  __int64 v3; // rsi
  unsigned __int16 *FirstFileW; // rax
  __int64 v5; // rdi
  unsigned int i; // r12d
  int v7; // ecx
  int v8; // ecx
  int v9; // ebx
  HKEY v10; // rax
  HKEY v11; // rbx
  __int64 v12; // rax
  unsigned int v13; // r14d
  unsigned __int16 *v14; // rax
  const unsigned __int16 **j; // r11
  __int64 v16; // r11
  int v17; // ecx
  int v18; // edx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  BYTE v21[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  HKEY hKey[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR FileName[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned __int16 v28[264]; // [rsp+6C0h] [rbp+5C0h] BYREF

  hKey[0] = 0;
  StringCchCopyW(ValueName, 0x104u, RegScanUtil::sm_wszDir);
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)(v2 + 2 * v3) );
  if ( ValueName[(unsigned int)(v3 - 1)] != 92 )
  {
    StringCchCatW(ValueName, 0x104u, L"\\");
    LODWORD(v3) = v3 + 1;
  }
  StringCchCopyW(v28, 0x104u, ValueName);
  StringCchCopyW(FileName, 0x104u, ValueName);
  StringCchCatW(FileName, 0x104u, L"*");
  LODWORD(FirstFileW) = (unsigned int)memset_0(&FindFileData, 0, sizeof(FindFileData));
  v5 = -1;
  for ( i = 0; i < 0x64; ++i )
  {
    if ( v5 == -1 )
    {
      FirstFileW = (unsigned __int16 *)FindFirstFileW(FileName, &FindFileData);
      v5 = (__int64)FirstFileW;
      if ( FirstFileW == (unsigned __int16 *)-1LL )
        goto LABEL_48;
    }
    else if ( !FindNextFileW((HANDLE)v5, &FindFileData) )
    {
      GetLastError();
      goto LABEL_47;
    }
    LODWORD(FirstFileW) = FindFileData.cFileName[0];
    v7 = 46 - FindFileData.cFileName[0];
    if ( FindFileData.cFileName[0] == 46 )
    {
      LODWORD(FirstFileW) = FindFileData.cFileName[1];
      v7 = -FindFileData.cFileName[1];
    }
    if ( v7 )
    {
      LODWORD(FirstFileW) = FindFileData.cFileName[0];
      v8 = 46 - FindFileData.cFileName[0];
      if ( FindFileData.cFileName[0] == 46 )
      {
        LODWORD(FirstFileW) = FindFileData.cFileName[1];
        v8 = 46 - FindFileData.cFileName[1];
        if ( FindFileData.cFileName[1] == 46 )
        {
          LODWORD(FirstFileW) = FindFileData.cFileName[2];
          v8 = -FindFileData.cFileName[2];
        }
      }
      if ( v8 )
      {
        if ( !hKey[0]
          && RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedDlls", 0, 0, hKey) )
        {
          goto LABEL_47;
        }
        StringCchCopyW(&ValueName[(unsigned int)v3], 260LL - (unsigned int)v3, FindFileData.cFileName);
        *(_DWORD *)Data = 0;
        Type = 0;
        cbData = 4;
        LODWORD(FirstFileW) = RegQueryValueExW(hKey[0], ValueName, 0, &Type, Data, &cbData);
        if ( (_DWORD)FirstFileW || Type != 4 || (v9 = 1, cbData != 4) )
        {
          v9 = 0;
          *(_DWORD *)Data = 1;
        }
        if ( a1 )
        {
          if ( a1 == 1 )
          {
            for ( j = (const unsigned __int16 **)RegScanUtil::sm_pFileRefCountHead;
                  j;
                  j = *(const unsigned __int16 ***)(v16 + 16) )
            {
              StringCchCopyW(&v28[(unsigned int)v3], 260LL - (unsigned int)v3, *j);
              FirstFileW = v28;
              do
              {
                v17 = *(FirstFileW - 528);
                v18 = *FirstFileW - v17;
                if ( v18 )
                  break;
                ++FirstFileW;
              }
              while ( v17 );
              if ( !v18 )
              {
                *(_DWORD *)v21 = 0;
                LODWORD(FirstFileW) = *(_DWORD *)(v16 + 8) + 1;
                *(_DWORD *)v21 = (_DWORD)FirstFileW;
                if ( *(_DWORD *)Data <= (unsigned int)FirstFileW )
                  goto LABEL_43;
                goto LABEL_41;
              }
            }
            *(_DWORD *)v21 = 1;
            if ( *(_DWORD *)Data == 1 )
              continue;
LABEL_41:
            if ( v9 )
              LODWORD(FirstFileW) = RegSetValueExW(hKey[0], ValueName, 0, Type, v21, cbData);
          }
        }
        else
        {
          v10 = (HKEY)CoTaskMemAlloc(0x18u);
          hKey[1] = v10;
          v11 = v10;
          if ( !v10 )
            goto LABEL_47;
          *(_QWORD *)v10 = 0;
          *((_DWORD *)v10 + 2) = 0;
          *((_QWORD *)v10 + 2) = 0;
          *(_DWORD *)(v10 + 2) = *(_DWORD *)(HKEY)Data;
          v12 = -1;
          do
            ++v12;
          while ( FindFileData.cFileName[v12] );
          v13 = v12 + 1;
          v14 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul((unsigned int)(v12 + 1), 2u));
          *(_QWORD *)v11 = v14;
          if ( !v14 )
          {
            FILE_REF_COUNT::`scalar deleting destructor'((void **)v11);
            goto LABEL_47;
          }
          LODWORD(FirstFileW) = StringCchCopyW(v14, v13, FindFileData.cFileName);
          *((_QWORD *)v11 + 2) = RegScanUtil::sm_pFileRefCountHead;
          RegScanUtil::sm_pFileRefCountHead = (FILE_REF_COUNT *)v11;
        }
      }
    }
LABEL_43:
    ;
  }
  if ( v5 == -1 )
    goto LABEL_48;
LABEL_47:
  LODWORD(FirstFileW) = FindClose((HANDLE)v5);
LABEL_48:
  if ( hKey[0] )
    LODWORD(FirstFileW) = RegCloseKey(hKey[0]);
  return (int)FirstFileW;
}

```

## disassembly

```asm
0x18002fbb8  push    rbp
0x18002fbba  push    rbx
0x18002fbbb  push    rsi
0x18002fbbc  push    rdi
0x18002fbbd  push    r12
0x18002fbbf  push    r13
0x18002fbc1  push    r14
0x18002fbc3  push    r15
0x18002fbc5  lea     rbp, [rsp-7E8h]
0x18002fbcd  sub     rsp, 8E8h
0x18002fbd4  mov     rax, cs:__security_cookie
0x18002fbdb  xor     rax, rsp
0x18002fbde  mov     [rbp+820h+var_50], rax
0x18002fbe5  mov     r11, cs:?sm_wszDir@RegScanUtil@@0PEAGEA; ushort * RegScanUtil::sm_wszDir
0x18002fbec  mov     r13d, ecx
0x18002fbef  xor     r15d, r15d
0x18002fbf2  lea     rcx, [rbp+820h+ValueName]; unsigned __int16 *
0x18002fbf9  mov     r8, r11; unsigned __int16 *
0x18002fbfc  mov     [rsp+920h+hKey], r15
0x18002fc01  mov     edx, 104h; unsigned __int64
0x18002fc06  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fc0b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002fc0f  mov     rsi, rbx
0x18002fc12  inc     rsi
0x18002fc15  cmp     [r11+rsi*2], r15w
0x18002fc1a  jnz     short loc_18002FC12
0x18002fc1c  lea     eax, [rsi-1]
0x18002fc1f  cmp     [rbp+rax*2+820h+ValueName], 5Ch ; '\'
0x18002fc28  jz      short loc_18002FC44
0x18002fc2a  lea     r8, asc_18005D30C; "\\"
0x18002fc31  mov     edx, 104h; unsigned __int64
0x18002fc36  lea     rcx, [rbp+820h+ValueName]; unsigned __int16 *
0x18002fc3d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fc42  inc     esi
0x18002fc44  lea     r8, [rbp+820h+ValueName]; unsigned __int16 *
0x18002fc4b  mov     edx, 104h; unsigned __int64
0x18002fc50  lea     rcx, [rbp+820h+var_260]; unsigned __int16 *
0x18002fc57  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fc5c  lea     r8, [rbp+820h+ValueName]; unsigned __int16 *
0x18002fc63  mov     edx, 104h; unsigned __int64
0x18002fc68  lea     rcx, [rbp+820h+FileName]; unsigned __int16 *
0x18002fc6f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fc74  lea     r8, asc_180063430; "*"
0x18002fc7b  mov     edx, 104h; unsigned __int64
0x18002fc80  lea     rcx, [rbp+820h+FileName]; unsigned __int16 *
0x18002fc87  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fc8c  xor     edx, edx; Val
0x18002fc8e  lea     rcx, [rsp+920h+FindFileData]; void *
0x18002fc93  mov     r8d, 250h; Size
0x18002fc99  call    memset_0
0x18002fc9e  mov     rdi, rbx
0x18002fca1  mov     r12d, r15d
0x18002fca4  mov     r14d, 2Eh ; '.'
0x18002fcaa  cmp     r12d, 64h ; 'd'
0x18002fcae  jnb     loc_18002FF78
0x18002fcb4  lea     rdx, [rsp+920h+FindFileData]; lpFindFileData
0x18002fcb9  cmp     rdi, rbx
0x18002fcbc  jnz     short loc_18002FCD9
0x18002fcbe  lea     rcx, [rbp+820h+FileName]; lpFileName
0x18002fcc5  call    cs:__imp_FindFirstFileW
0x18002fccb  mov     rdi, rax
0x18002fcce  cmp     rax, rbx
0x18002fcd1  jz      loc_18002FF86
0x18002fcd7  jmp     short loc_18002FCEA
0x18002fcd9  mov     rcx, rdi; hFindFile
0x18002fcdc  call    cs:__imp_FindNextFileW
0x18002fce2  test    eax, eax
0x18002fce4  jz      loc_18002FF70
0x18002fcea  movzx   eax, [rsp+920h+FindFileData.cFileName]
0x18002fcef  movzx   ecx, r14w
0x18002fcf3  sub     ecx, eax
0x18002fcf5  jnz     short loc_18002FD02
0x18002fcf7  movzx   eax, [rsp+920h+FindFileData.cFileName+2]
0x18002fcfc  movzx   ecx, r15w
0x18002fd00  sub     ecx, eax
0x18002fd02  test    ecx, ecx
0x18002fd04  jz      loc_18002FF5E
0x18002fd0a  movzx   eax, [rsp+920h+FindFileData.cFileName]
0x18002fd0f  movzx   ecx, r14w
0x18002fd13  sub     ecx, eax
0x18002fd15  jnz     short loc_18002FD2E
0x18002fd17  movzx   eax, [rsp+920h+FindFileData.cFileName+2]
0x18002fd1c  movzx   ecx, r14w
0x18002fd20  sub     ecx, eax
0x18002fd22  jnz     short loc_18002FD2E
0x18002fd24  movzx   eax, [rbp+820h+FindFileData.cFileName+4]
0x18002fd28  movzx   ecx, r15w
0x18002fd2c  sub     ecx, eax
0x18002fd2e  test    ecx, ecx
0x18002fd30  jz      loc_18002FF5E
0x18002fd36  cmp     [rsp+920h+hKey], r15
0x18002fd3b  jnz     short loc_18002FD69
0x18002fd3d  lea     rax, [rsp+920h+hKey]
0x18002fd42  xor     r9d, r9d; samDesired
0x18002fd45  xor     r8d, r8d; ulOptions
0x18002fd48  mov     [rsp+920h+phkResult], rax; phkResult
0x18002fd4d  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002fd54  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002fd5b  call    cs:__imp_RegOpenKeyExW
0x18002fd61  test    eax, eax
0x18002fd63  jnz     loc_18002FF7D
0x18002fd69  mov     r15d, esi
0x18002fd6c  lea     rcx, [rbp+820h+ValueName]
0x18002fd73  mov     r14d, 104h
0x18002fd79  lea     r8, [rsp+920h+FindFileData.cFileName]; unsigned __int16 *
0x18002fd7e  sub     r14, r15
0x18002fd81  mov     rdx, r14; unsigned __int64
0x18002fd84  lea     rcx, [rcx+r15*2]; unsigned __int16 *
0x18002fd88  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fd8d  mov     rcx, [rsp+920h+hKey]; hKey
0x18002fd92  lea     rax, [rsp+920h+cbData]
0x18002fd97  mov     [rsp+920h+lpcbData], rax; lpcbData
0x18002fd9c  lea     r9, [rsp+920h+Type]; lpType
0x18002fda1  lea     rax, [rsp+920h+Data]
0x18002fda6  mov     dword ptr [rsp+920h+Data], 0
0x18002fdae  xor     r8d, r8d; lpReserved
0x18002fdb1  mov     [rsp+920h+phkResult], rax; lpData
0x18002fdb6  lea     rdx, [rbp+820h+ValueName]; lpValueName
0x18002fdbd  mov     [rsp+920h+Type], 0
0x18002fdc5  mov     [rsp+920h+cbData], 4
0x18002fdcd  call    cs:__imp_RegQueryValueExW
0x18002fdd3  xor     ecx, ecx
0x18002fdd5  test    eax, eax
0x18002fdd7  jnz     short loc_18002FDEA
0x18002fdd9  cmp     [rsp+920h+Type], 4
0x18002fdde  jnz     short loc_18002FDEA
0x18002fde0  cmp     [rsp+920h+cbData], 4
0x18002fde5  lea     ebx, [rcx+1]
0x18002fde8  jz      short loc_18002FDF4
0x18002fdea  mov     ebx, ecx
0x18002fdec  mov     dword ptr [rsp+920h+Data], 1
0x18002fdf4  test    r13d, r13d
0x18002fdf7  jnz     loc_18002FE98
0x18002fdfd  lea     ecx, [r13+18h]; cb
0x18002fe01  call    cs:__imp_CoTaskMemAlloc
0x18002fe07  xor     r15d, r15d
0x18002fe0a  mov     [rsp+920h+var_8D8], rax
0x18002fe0f  mov     rbx, rax
0x18002fe12  test    rax, rax
0x18002fe15  jz      loc_18002FF7D
0x18002fe1b  mov     [rax], r15
0x18002fe1e  mov     [rax+8], r15d
0x18002fe22  mov     [rax+10h], r15
0x18002fe26  test    rax, rax
0x18002fe29  jz      loc_18002FF7D
0x18002fe2f  mov     eax, dword ptr [rsp+920h+Data]
0x18002fe33  lea     rdx, [rsp+920h+FindFileData.cFileName]
0x18002fe38  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002fe3c  mov     [rbx+8], eax
0x18002fe3f  mov     rax, rcx
0x18002fe42  inc     rax
0x18002fe45  cmp     [rdx+rax*2], r15w
0x18002fe4a  jnz     short loc_18002FE42
0x18002fe4c  lea     r14d, [rax+1]
0x18002fe50  mov     eax, 2
0x18002fe55  mul     r14
0x18002fe58  cmovb   rax, rcx
0x18002fe5c  mov     rcx, rax; cb
0x18002fe5f  call    cs:__imp_CoTaskMemAlloc
0x18002fe65  mov     [rbx], rax
0x18002fe68  test    rax, rax
0x18002fe6b  jz      loc_18002FF66
0x18002fe71  lea     r8, [rsp+920h+FindFileData.cFileName]; unsigned __int16 *
0x18002fe76  mov     edx, r14d; unsigned __int64
0x18002fe79  mov     rcx, rax; unsigned __int16 *
0x18002fe7c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fe81  mov     r11, cs:?sm_pFileRefCountHead@RegScanUtil@@0PEAUFILE_REF_COUNT@@EA; FILE_REF_COUNT * RegScanUtil::sm_pFileRefCountHead
0x18002fe88  mov     [rbx+10h], r11
0x18002fe8c  mov     cs:?sm_pFileRefCountHead@RegScanUtil@@0PEAUFILE_REF_COUNT@@EA, rbx; FILE_REF_COUNT * RegScanUtil::sm_pFileRefCountHead
0x18002fe93  jmp     loc_18002FF54
0x18002fe98  cmp     r13d, 1
0x18002fe9c  jnz     loc_18002FF51
0x18002fea2  mov     r11, cs:?sm_pFileRefCountHead@RegScanUtil@@0PEAUFILE_REF_COUNT@@EA; FILE_REF_COUNT * RegScanUtil::sm_pFileRefCountHead
0x18002fea9  test    r11, r11
0x18002feac  jz      short loc_18002FF0D
0x18002feae  mov     r8, [r11]; unsigned __int16 *
0x18002feb1  lea     rcx, [rbp+820h+var_260]
0x18002feb8  lea     rcx, [rcx+r15*2]; unsigned __int16 *
0x18002febc  mov     rdx, r14; unsigned __int64
0x18002febf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002fec4  lea     rax, [rbp+820h+var_260]
0x18002fecb  lea     r8, [rbp+820h+ValueName]
0x18002fed2  sub     r8, rax
0x18002fed5  movzx   edx, word ptr [rax]
0x18002fed8  movzx   ecx, word ptr [rax+r8]
0x18002fedd  sub     edx, ecx
0x18002fedf  jnz     short loc_18002FEE9
0x18002fee1  add     rax, 2
0x18002fee5  test    ecx, ecx
0x18002fee7  jnz     short loc_18002FED5
0x18002fee9  test    edx, edx
0x18002feeb  jz      short loc_18002FEF3
0x18002feed  mov     r11, [r11+10h]
0x18002fef1  jmp     short loc_18002FEA9
0x18002fef3  xor     r15d, r15d
0x18002fef6  mov     dword ptr [rsp+920h+var_8EC], r15d
0x18002fefb  mov     eax, [r11+8]
0x18002feff  inc     eax
0x18002ff01  mov     dword ptr [rsp+920h+var_8EC], eax
0x18002ff05  cmp     dword ptr [rsp+920h+Data], eax
0x18002ff09  jbe     short loc_18002FF54
0x18002ff0b  jmp     short loc_18002FF1F
0x18002ff0d  xor     r15d, r15d
0x18002ff10  mov     dword ptr [rsp+920h+var_8EC], 1
0x18002ff18  cmp     dword ptr [rsp+920h+Data], 1
0x18002ff1d  jz      short loc_18002FF54
0x18002ff1f  test    ebx, ebx
0x18002ff21  jz      short loc_18002FF54
0x18002ff23  mov     eax, [rsp+920h+cbData]
0x18002ff27  lea     rdx, [rbp+820h+ValueName]; lpValueName
0x18002ff2e  mov     r9d, [rsp+920h+Type]; dwType
0x18002ff33  xor     r8d, r8d; Reserved
0x18002ff36  mov     rcx, [rsp+920h+hKey]; hKey
0x18002ff3b  mov     dword ptr [rsp+920h+lpcbData], eax; cbData
0x18002ff3f  lea     rax, [rsp+920h+var_8EC]
0x18002ff44  mov     [rsp+920h+phkResult], rax; lpData
0x18002ff49  call    cs:__imp_RegSetValueExW
0x18002ff4f  jmp     short loc_18002FF54
0x18002ff51  xor     r15d, r15d
0x18002ff54  mov     r14d, 2Eh ; '.'
0x18002ff5a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002ff5e  inc     r12d
0x18002ff61  jmp     loc_18002FCAA
0x18002ff66  mov     rcx, rbx; this
0x18002ff69  call    ??_GFILE_REF_COUNT@@QEAAPEAXI@Z; FILE_REF_COUNT::`scalar deleting destructor'(uint)
0x18002ff6e  jmp     short loc_18002FF7D
0x18002ff70  call    cs:__imp_GetLastError
0x18002ff76  jmp     short loc_18002FF7D
0x18002ff78  cmp     rdi, rbx
0x18002ff7b  jz      short loc_18002FF86
0x18002ff7d  mov     rcx, rdi; hFindFile
0x18002ff80  call    cs:__imp_FindClose
0x18002ff86  mov     rcx, [rsp+920h+hKey]; hKey
0x18002ff8b  test    rcx, rcx
0x18002ff8e  jz      short loc_18002FF96
0x18002ff90  call    cs:__imp_RegCloseKey
0x18002ff96  mov     rcx, [rbp+820h+var_50]
0x18002ff9d  xor     rcx, rsp; StackCookie
0x18002ffa0  call    __security_check_cookie
0x18002ffa5  add     rsp, 8E8h
0x18002ffac  pop     r15
0x18002ffae  pop     r14
0x18002ffb0  pop     r13
0x18002ffb2  pop     r12
0x18002ffb4  pop     rdi
0x18002ffb5  pop     rsi
0x18002ffb6  pop     rbx
0x18002ffb7  pop     rbp
0x18002ffb8  retn
```
