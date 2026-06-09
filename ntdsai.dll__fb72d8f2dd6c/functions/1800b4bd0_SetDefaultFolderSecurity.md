# SetDefaultFolderSecurity

- ea: `0x1800b4bd0`
- end: `0x1800b514c`
- name: `SetDefaultFolderSecurity`
- size: `1404`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800a37a0`

## callees

- `0x18001e090`
- `0x18002a060`
- `0x1800b4b2c`
- `0x1800b4bd0`
- `0x1800b5154`
- `0x1801703f0`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800b4ff7`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800b4ff7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b4f8a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b4fa3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b4f8a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b4fa3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800b4dd6`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800b4dd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4df7`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800b4ded`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800b4ded`
- `SCECLI!SceCloseProfile` at `0x1800b5121`
- `SCECLI!SceCloseProfile` at `0x1800b5121`
- `SCECLI!SceFreeProfileMemory` at `0x1800b510f`
- `SCECLI!SceFreeProfileMemory` at `0x1800b510f`
- `SCECLI!SceOpenProfile` at `0x1800b4e57`
- `SCECLI!SceOpenProfile` at `0x1800b4e57`
- `SCECLI!SceGetSecurityProfileInfo` at `0x1800b4e89`
- `SCECLI!SceGetSecurityProfileInfo` at `0x1800b4e89`

## string_xrefs

- `0x1800b4cf2`: `Database log files path`

## pseudocode

```c
__int64 SetDefaultFolderSecurity()
{
  DWORD ConfigParamLocal; // ebx
  __int64 v1; // rdi
  char *v2; // rax
  DWORD LastError; // eax
  __int64 v4; // rax
  unsigned int v5; // eax
  unsigned int SecurityProfileInfo; // eax
  LPOVERLAPPED v7; // rdi
  __int64 *v8; // rcx
  _QWORD *v9; // rdi
  _QWORD *v10; // rbx
  unsigned int v11; // esi
  _QWORD *v12; // r15
  DWORD v13; // ecx
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+48h] [rbp-B8h]
  DWORD Offset; // [rsp+4Ch] [rbp-B4h]
  __int64 v20; // [rsp+50h] [rbp-B0h]
  int v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+5Ch] [rbp-A4h]
  __int64 v23; // [rsp+60h] [rbp-A0h]
  __int64 v24; // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  __int64 v27; // [rsp+80h] [rbp-80h]
  int v28; // [rsp+88h] [rbp-78h]
  __int64 v29; // [rsp+8Ch] [rbp-74h]
  int v30; // [rsp+94h] [rbp-6Ch]
  int *v31; // [rsp+98h] [rbp-68h]
  int v32; // [rsp+A0h] [rbp-60h]
  int v33; // [rsp+A4h] [rbp-5Ch]
  __int64 v34; // [rsp+B0h] [rbp-50h] BYREF
  int v35; // [rsp+B8h] [rbp-48h]
  DWORD v36; // [rsp+BCh] [rbp-44h]
  __int64 v37; // [rsp+C0h] [rbp-40h]
  int v38; // [rsp+C8h] [rbp-38h]
  int v39; // [rsp+CCh] [rbp-34h]
  __int64 v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  __int64 v44; // [rsp+F0h] [rbp-10h]
  int v45; // [rsp+F8h] [rbp-8h]
  __int64 v46; // [rsp+FCh] [rbp-4h]
  int v47; // [rsp+104h] [rbp+4h]
  int *v48; // [rsp+108h] [rbp+8h]
  int v49; // [rsp+110h] [rbp+10h] BYREF
  const char *v50; // [rsp+118h] [rbp+18h]
  __int64 v51; // [rsp+128h] [rbp+28h] BYREF
  int v52; // [rsp+130h] [rbp+30h]
  __int64 *v53; // [rsp+138h] [rbp+38h]
  __int64 v54; // [rsp+148h] [rbp+48h] BYREF
  int v55; // [rsp+150h] [rbp+50h]
  __int64 *v56; // [rsp+158h] [rbp+58h]
  __int64 v57; // [rsp+168h] [rbp+68h] BYREF
  char Str[272]; // [rsp+330h] [rbp+230h] BYREF
  CHAR pObjectName[272]; // [rsp+440h] [rbp+340h] BYREF
  WCHAR Buffer[264]; // [rsp+550h] [rbp+450h] BYREF

  v15 = 0;
  v16 = 0;
  v32 = 0;
  ConfigParamLocal = GetConfigParamLocalEx((__int64)"DSA Database file", (LPBYTE)Str);
  if ( ConfigParamLocal )
  {
    if ( gpDsEventConfig
      && ((int)gpDsEventConfig[3].OffsetHigh >= 2
       || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(768, 2)
       || (unsigned int)DoLogMsgOverride(1073742911)) )
    {
      v20 = 2;
      v26 = 0;
      v29 = 0;
      v30 = 0;
      v18 = 1073742911;
      v21 = 0;
      v22 = 1;
      Offset = gpDsEventConfig[3].Offset;
      v31 = &v49;
      v49 = 0;
      v50 = "DSA Database file";
      v17 = 1;
      v25 = 0;
      v24 = 768;
      v23 = 1;
      v27 = 0;
      v28 = 0;
      DoLogEventAndTrace(&v17);
    }
    v1 = 50339867;
    goto LABEL_51;
  }
  v33 = 0;
  ConfigParamLocal = GetConfigParamLocalEx((__int64)"Database log files path", (LPBYTE)pObjectName);
  if ( !ConfigParamLocal )
  {
    v2 = strrchr(Str, 92);
    if ( v2 )
      *v2 = 0;
    if ( GetWindowsDirectoryW(Buffer, 0x105u) )
    {
      v4 = -1;
      do
        ++v4;
      while ( Buffer[v4] );
      if ( (unsigned __int64)(v4 + 17) >= 0x105 )
      {
        ConfigParamLocal = 111;
        v1 = 0;
        goto LABEL_51;
      }
      StringCchCatW(Buffer, 0x105u, L"\\inf\\defltdc.inf");
      v5 = SceOpenProfile(Buffer, 1, &v16);
      if ( v5 )
      {
        LastError = SceStatusToDosError(v5);
        v1 = 50339917;
      }
      else
      {
        SecurityProfileInfo = SceGetSecurityProfileInfo(v16, 302, 64, &v15, 0);
        if ( !SecurityProfileInfo )
        {
          v9 = 0;
          v10 = 0;
          v11 = 0;
          if ( !**(_DWORD **)(v15 + 120) )
            goto LABEL_50;
          do
          {
            v12 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)(v15 + 120) + 8LL) + 8LL * v11);
            if ( (unsigned int)_o__wcsicmp(*v12, L"%DSDIT%") )
            {
              if ( !(unsigned int)_o__wcsicmp(*v12, L"%DSLOG%") )
                v10 = v12;
            }
            else
            {
              v9 = v12;
            }
            ++v11;
          }
          while ( v11 < **(_DWORD **)(v15 + 120) );
          if ( !v9 || !v10 )
          {
LABEL_50:
            ConfigParamLocal = 13;
            v1 = 50339942;
            goto LABEL_51;
          }
          ConfigParamLocal = SetFolderSecurity(pObjectName, *((_DWORD *)v10 + 6), (void *)v10[2]);
          if ( ConfigParamLocal )
          {
            v1 = 50339949;
            goto LABEL_51;
          }
          if ( (unsigned int)_o__stricmp(pObjectName, Str) )
          {
            ConfigParamLocal = SetFolderSecurity(Str, *((_DWORD *)v9 + 6), (void *)v9[2]);
            if ( ConfigParamLocal )
            {
              v1 = 50339956;
              goto LABEL_51;
            }
          }
          goto LABEL_30;
        }
        LastError = SceStatusToDosError(SecurityProfileInfo);
        v1 = 50339924;
      }
    }
    else
    {
      LastError = GetLastError();
      v1 = 50339903;
    }
    ConfigParamLocal = LastError;
    if ( LastError )
      goto LABEL_51;
LABEL_30:
    v7 = gpDsEventConfig;
    if ( !gpDsEventConfig )
      goto LABEL_58;
    if ( (gpDsEventConfig[4].OffsetHigh & 0x80000000) != 0
      && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(768, 0)) )
    {
      if ( !(unsigned int)DoLogMsgOverride(1073743824) )
        goto LABEL_58;
      v7 = gpDsEventConfig;
    }
    v17 = 0;
    v8 = &v17;
    v26 = 0;
    v29 = 0;
    v30 = 0;
    Offset = v7[4].Offset;
    v31 = &v49;
    v20 = 0;
    v18 = 1073743824;
    v21 = 0;
    v22 = 1;
    v25 = 0;
    v24 = 768;
    v23 = 1;
    v27 = 0;
    v28 = 0;
    goto LABEL_57;
  }
  if ( gpDsEventConfig
    && ((int)gpDsEventConfig[3].OffsetHigh >= 2
     || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(768, 2)
     || (unsigned int)DoLogMsgOverride(1073742911)) )
  {
    v20 = 2;
    v26 = 0;
    v29 = 0;
    v30 = 0;
    v18 = 1073742911;
    v21 = 0;
    v22 = 1;
    Offset = gpDsEventConfig[3].Offset;
    v31 = &v49;
    v49 = 0;
    v50 = "Database log files path";
    v17 = 1;
    v25 = 0;
    v24 = 768;
    v23 = 1;
    v27 = 0;
    v28 = 0;
    DoLogEventAndTrace(&v17);
  }
  v1 = 50339881;
LABEL_51:
  if ( gpDsEventConfig
    && ((gpDsEventConfig[4].OffsetHigh & 0x80000000) == 0
     || HIDWORD(gpDsEventConfig->Internal) && (unsigned int)DoLogOverride(768, 0)
     || (unsigned int)DoLogMsgOverride(3221227473LL)) )
  {
    v35 = -1073739823;
    v37 = 0;
    v43 = 0;
    v46 = 0;
    v47 = 0;
    v38 = 0;
    v39 = 1;
    v34 = 3;
    v13 = gpDsEventConfig[4].Offset;
    v48 = &v49;
    v51 = ConfigParamLocal;
    v54 = ConfigParamLocal;
    v36 = v13;
    v53 = &v54;
    v50 = (const char *)&v51;
    v8 = &v34;
    v56 = &v57;
    v49 = 3;
    v52 = 10;
    v55 = 4;
    v57 = v1;
    v42 = 0;
    v41 = 768;
    v40 = 1;
    v44 = 0;
    v45 = 0;
LABEL_57:
    DoLogEventAndTrace(v8);
  }
LABEL_58:
  if ( v15 )
    SceFreeProfileMemory();
  if ( v16 )
    SceCloseProfile(&v16);
  return ConfigParamLocal;
}

```

## disassembly

```asm
0x1800b4bd0  push    rbp
0x1800b4bd2  push    rbx
0x1800b4bd3  push    rsi
0x1800b4bd4  push    rdi
0x1800b4bd5  push    r12
0x1800b4bd7  push    r13
0x1800b4bd9  push    r14
0x1800b4bdb  push    r15
0x1800b4bdd  lea     rbp, [rsp-678h]
0x1800b4be5  sub     rsp, 778h
0x1800b4bec  mov     rax, cs:__security_cookie
0x1800b4bf3  xor     rax, rsp
0x1800b4bf6  mov     [rbp+6B0h+var_50], rax
0x1800b4bfd  xor     r12d, r12d
0x1800b4c00  lea     r15, aDsaDatabaseFil; "DSA Database file"
0x1800b4c07  mov     edi, 105h
0x1800b4c0c  mov     [rsp+7B0h+var_780], r12
0x1800b4c11  mov     r8d, edi
0x1800b4c14  mov     [rsp+7B0h+var_778], r12
0x1800b4c19  mov     rcx, r15; __int64
0x1800b4c1c  mov     [rbp+6B0h+var_710], r12d
0x1800b4c20  lea     r9, [rbp+6B0h+var_710]
0x1800b4c24  lea     rdx, [rbp+6B0h+Str]; lpData
0x1800b4c2b  call    GetConfigParamLocalEx
0x1800b4c30  lea     r13d, [r12+1]
0x1800b4c35  mov     ebx, eax
0x1800b4c37  mov     r14d, 300h
0x1800b4c3d  test    eax, eax
0x1800b4c3f  jz      loc_1800B4CF2
0x1800b4c45  mov     rax, cs:gpDsEventConfig
0x1800b4c4c  test    rax, rax
0x1800b4c4f  jz      loc_1800B4CE8
0x1800b4c55  lea     edi, [r12+2]
0x1800b4c5a  mov     esi, 4000043Fh
0x1800b4c5f  cmp     [rax+74h], edi
0x1800b4c62  jge     short loc_1800B4C83
0x1800b4c64  cmp     [rax+4], r12d
0x1800b4c68  jz      short loc_1800B4C78
0x1800b4c6a  mov     edx, edi
0x1800b4c6c  mov     ecx, r14d
0x1800b4c6f  call    DoLogOverride
0x1800b4c74  test    eax, eax
0x1800b4c76  jnz     short loc_1800B4C83
0x1800b4c78  mov     ecx, esi
0x1800b4c7a  call    DoLogMsgOverride
0x1800b4c7f  test    eax, eax
0x1800b4c81  jz      short loc_1800B4CE8
0x1800b4c83  xor     eax, eax
0x1800b4c85  mov     [rsp+7B0h+var_760], rdi
0x1800b4c8a  mov     [rsp+7B0h+var_738], rax
0x1800b4c8f  mov     [rbp+6B0h+var_724], rax
0x1800b4c93  mov     [rbp+6B0h+var_71C], eax
0x1800b4c96  mov     rax, cs:gpDsEventConfig
0x1800b4c9d  mov     [rsp+7B0h+var_768], esi
0x1800b4ca1  mov     [rsp+7B0h+var_758], r12d
0x1800b4ca6  mov     [rsp+7B0h+var_754], r13d
0x1800b4cab  mov     ecx, [rax+70h]
0x1800b4cae  lea     rax, [rbp+6B0h+var_6A0]
0x1800b4cb2  mov     [rsp+7B0h+var_764], ecx
0x1800b4cb6  lea     rcx, [rsp+7B0h+var_770]
0x1800b4cbb  mov     [rbp+6B0h+var_718], rax
0x1800b4cbf  mov     [rbp+6B0h+var_6A0], r12d
0x1800b4cc3  mov     [rbp+6B0h+var_698], r15
0x1800b4cc7  mov     [rsp+7B0h+var_770], r13
0x1800b4ccc  mov     [rsp+7B0h+var_740], r12
0x1800b4cd1  mov     [rsp+7B0h+var_748], r14
0x1800b4cd6  mov     [rsp+7B0h+var_750], r13
0x1800b4cdb  mov     [rbp+6B0h+var_730], r12
0x1800b4cdf  mov     [rbp+6B0h+var_728], r12d
0x1800b4ce3  call    DoLogEventAndTrace
0x1800b4ce8  mov     edi, 300201Bh
0x1800b4ced  jmp     loc_1800B5033
0x1800b4cf2  lea     r15, aDatabaseLogFil; "Database log files path"
0x1800b4cf9  mov     [rbp+6B0h+var_70C], r12d
0x1800b4cfd  mov     rcx, r15; __int64
0x1800b4d00  lea     r9, [rbp+6B0h+var_70C]
0x1800b4d04  mov     r8d, edi
0x1800b4d07  lea     rdx, [rbp+6B0h+pObjectName]; lpData
0x1800b4d0e  call    GetConfigParamLocalEx
0x1800b4d13  mov     ebx, eax
0x1800b4d15  test    eax, eax
0x1800b4d17  jz      loc_1800B4DCA
0x1800b4d1d  mov     rax, cs:gpDsEventConfig
0x1800b4d24  test    rax, rax
0x1800b4d27  jz      loc_1800B4DC0
0x1800b4d2d  mov     edi, 2
0x1800b4d32  mov     esi, 4000043Fh
0x1800b4d37  cmp     [rax+74h], edi
0x1800b4d3a  jge     short loc_1800B4D5B
0x1800b4d3c  cmp     [rax+4], r12d
0x1800b4d40  jz      short loc_1800B4D50
0x1800b4d42  mov     edx, edi
0x1800b4d44  mov     ecx, r14d
0x1800b4d47  call    DoLogOverride
0x1800b4d4c  test    eax, eax
0x1800b4d4e  jnz     short loc_1800B4D5B
0x1800b4d50  mov     ecx, esi
0x1800b4d52  call    DoLogMsgOverride
0x1800b4d57  test    eax, eax
0x1800b4d59  jz      short loc_1800B4DC0
0x1800b4d5b  xor     eax, eax
0x1800b4d5d  mov     [rsp+7B0h+var_760], rdi
0x1800b4d62  mov     [rsp+7B0h+var_738], rax
0x1800b4d67  mov     [rbp+6B0h+var_724], rax
0x1800b4d6b  mov     [rbp+6B0h+var_71C], eax
0x1800b4d6e  mov     rax, cs:gpDsEventConfig
0x1800b4d75  mov     [rsp+7B0h+var_768], esi
0x1800b4d79  mov     [rsp+7B0h+var_758], r12d
0x1800b4d7e  mov     [rsp+7B0h+var_754], r13d
0x1800b4d83  mov     ecx, [rax+70h]
0x1800b4d86  lea     rax, [rbp+6B0h+var_6A0]
0x1800b4d8a  mov     [rsp+7B0h+var_764], ecx
0x1800b4d8e  lea     rcx, [rsp+7B0h+var_770]
0x1800b4d93  mov     [rbp+6B0h+var_718], rax
0x1800b4d97  mov     [rbp+6B0h+var_6A0], r12d
0x1800b4d9b  mov     [rbp+6B0h+var_698], r15
0x1800b4d9f  mov     [rsp+7B0h+var_770], r13
0x1800b4da4  mov     [rsp+7B0h+var_740], r12
0x1800b4da9  mov     [rsp+7B0h+var_748], r14
0x1800b4dae  mov     [rsp+7B0h+var_750], r13
0x1800b4db3  mov     [rbp+6B0h+var_730], r12
0x1800b4db7  mov     [rbp+6B0h+var_728], r12d
0x1800b4dbb  call    DoLogEventAndTrace
0x1800b4dc0  mov     edi, 3002029h
0x1800b4dc5  jmp     loc_1800B5033
0x1800b4dca  mov     edx, 5Ch ; '\'; Ch
0x1800b4dcf  lea     rcx, [rbp+6B0h+Str]; Str
0x1800b4dd6  call    cs:__imp_strrchr
0x1800b4ddc  test    rax, rax
0x1800b4ddf  jz      short loc_1800B4DE4
0x1800b4de1  mov     [rax], r12b
0x1800b4de4  mov     edx, edi; uSize
0x1800b4de6  lea     rcx, [rbp+6B0h+Buffer]; lpBuffer
0x1800b4ded  call    cs:__imp_GetWindowsDirectoryW
0x1800b4df3  test    eax, eax
0x1800b4df5  jnz     short loc_1800B4E07
0x1800b4df7  call    cs:__imp_GetLastError
0x1800b4dfd  mov     edi, 300203Fh
0x1800b4e02  jmp     loc_1800B4EA3
0x1800b4e07  lea     rcx, [rbp+6B0h+Buffer]
0x1800b4e0e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b4e12  inc     rax
0x1800b4e15  cmp     [rcx+rax*2], r12w
0x1800b4e1a  jnz     short loc_1800B4E12
0x1800b4e1c  add     rax, 11h
0x1800b4e20  cmp     rax, rdi
0x1800b4e23  jb      short loc_1800B4E32
0x1800b4e25  mov     ebx, 6Fh ; 'o'
0x1800b4e2a  mov     rdi, r12
0x1800b4e2d  jmp     loc_1800B5033
0x1800b4e32  lea     r8, aInfDefltdcInf; "\\inf\\defltdc.inf"
0x1800b4e39  mov     rdx, rdi; cchDest
0x1800b4e3c  lea     rcx, [rbp+6B0h+Buffer]; pszDest
0x1800b4e43  call    StringCchCatW
0x1800b4e48  lea     r8, [rsp+7B0h+var_778]
0x1800b4e4d  mov     edx, r13d
0x1800b4e50  lea     rcx, [rbp+6B0h+Buffer]
0x1800b4e57  call    cs:__imp_SceOpenProfile
0x1800b4e5d  test    eax, eax
0x1800b4e5f  jz      short loc_1800B4E6F
0x1800b4e61  mov     ecx, eax
0x1800b4e63  call    SceStatusToDosError
0x1800b4e68  mov     edi, 300204Dh
0x1800b4e6d  jmp     short loc_1800B4EA3
0x1800b4e6f  mov     rcx, [rsp+7B0h+var_778]
0x1800b4e74  lea     r9, [rsp+7B0h+var_780]
0x1800b4e79  mov     edx, 12Eh
0x1800b4e7e  mov     [rsp+7B0h+var_790], r12
0x1800b4e83  mov     r8d, 40h ; '@'
0x1800b4e89  call    cs:__imp_SceGetSecurityProfileInfo
0x1800b4e8f  test    eax, eax
0x1800b4e91  jz      loc_1800B4F52
0x1800b4e97  mov     ecx, eax
0x1800b4e99  call    SceStatusToDosError
0x1800b4e9e  mov     edi, 3002054h
0x1800b4ea3  mov     ebx, eax
0x1800b4ea5  test    eax, eax
0x1800b4ea7  jnz     loc_1800B5033
0x1800b4ead  mov     rdi, cs:gpDsEventConfig
0x1800b4eb4  test    rdi, rdi
0x1800b4eb7  jz      loc_1800B5105
0x1800b4ebd  mov     esi, 400007D0h
0x1800b4ec2  cmp     [rdi+94h], r12d
0x1800b4ec9  jge     short loc_1800B4EF5
0x1800b4ecb  cmp     [rdi+4], r12d
0x1800b4ecf  jz      short loc_1800B4EDF
0x1800b4ed1  xor     edx, edx
0x1800b4ed3  mov     ecx, r14d
0x1800b4ed6  call    DoLogOverride
0x1800b4edb  test    eax, eax
0x1800b4edd  jnz     short loc_1800B4EF5
0x1800b4edf  mov     ecx, esi
0x1800b4ee1  call    DoLogMsgOverride
0x1800b4ee6  test    eax, eax
0x1800b4ee8  jz      loc_1800B5105
0x1800b4eee  mov     rdi, cs:gpDsEventConfig
0x1800b4ef5  xor     eax, eax
0x1800b4ef7  mov     [rsp+7B0h+var_770], r12
0x1800b4efc  mov     dword ptr [rsp+7B0h+var_760+4], eax
0x1800b4f00  lea     rcx, [rsp+7B0h+var_770]
0x1800b4f05  mov     [rsp+7B0h+var_738], rax
0x1800b4f0a  mov     [rbp+6B0h+var_724], rax
0x1800b4f0e  mov     [rbp+6B0h+var_71C], eax
0x1800b4f11  mov     eax, [rdi+90h]
0x1800b4f17  mov     [rsp+7B0h+var_764], eax
0x1800b4f1b  lea     rax, [rbp+6B0h+var_6A0]
0x1800b4f1f  mov     [rbp+6B0h+var_718], rax
0x1800b4f23  mov     dword ptr [rsp+7B0h+var_760], r12d
0x1800b4f28  mov     [rsp+7B0h+var_768], esi
0x1800b4f2c  mov     [rsp+7B0h+var_758], r12d
0x1800b4f31  mov     [rsp+7B0h+var_754], r13d
0x1800b4f36  mov     [rsp+7B0h+var_740], r12
0x1800b4f3b  mov     [rsp+7B0h+var_748], r14
0x1800b4f40  mov     [rsp+7B0h+var_750], r13
0x1800b4f45  mov     [rbp+6B0h+var_730], r12
0x1800b4f49  mov     [rbp+6B0h+var_728], r12d
0x1800b4f4d  jmp     loc_1800B5100
0x1800b4f52  mov     rax, [rsp+7B0h+var_780]
0x1800b4f57  mov     rdi, r12
0x1800b4f5a  mov     rbx, r12
0x1800b4f5d  mov     esi, r12d
0x1800b4f60  mov     rcx, [rax+78h]
0x1800b4f64  cmp     [rcx], r12d
0x1800b4f67  jbe     loc_1800B5029
0x1800b4f6d  mov     rax, [rsp+7B0h+var_780]
0x1800b4f72  lea     rdx, aDsdit; "%DSDIT%"
0x1800b4f79  mov     ecx, esi
0x1800b4f7b  mov     rax, [rax+78h]
0x1800b4f7f  mov     rax, [rax+8]
0x1800b4f83  mov     r15, [rax+rcx*8]
0x1800b4f87  mov     rcx, [r15]
0x1800b4f8a  call    cs:__imp__o__wcsicmp
0x1800b4f90  test    eax, eax
0x1800b4f92  jnz     short loc_1800B4F99
0x1800b4f94  mov     rdi, r15
0x1800b4f97  jmp     short loc_1800B4FAF
0x1800b4f99  mov     rcx, [r15]
0x1800b4f9c  lea     rdx, aDslog; "%DSLOG%"
0x1800b4fa3  call    cs:__imp__o__wcsicmp
0x1800b4fa9  test    eax, eax
0x1800b4fab  cmovz   rbx, r15
0x1800b4faf  mov     rax, [rsp+7B0h+var_780]
0x1800b4fb4  add     esi, r13d
0x1800b4fb7  mov     rcx, [rax+78h]
0x1800b4fbb  cmp     esi, [rcx]
0x1800b4fbd  jb      short loc_1800B4F6D
0x1800b4fbf  test    rdi, rdi
0x1800b4fc2  jz      short loc_1800B5029
0x1800b4fc4  test    rbx, rbx
0x1800b4fc7  jz      short loc_1800B5029
0x1800b4fc9  mov     r8, [rbx+10h]
0x1800b4fcd  lea     rcx, [rbp+6B0h+pObjectName]; pObjectName
0x1800b4fd4  mov     edx, [rbx+18h]
0x1800b4fd7  call    SetFolderSecurity
0x1800b4fdc  mov     ebx, eax
0x1800b4fde  test    eax, eax
0x1800b4fe0  jz      short loc_1800B4FE9
0x1800b4fe2  mov     edi, 300206Dh
0x1800b4fe7  jmp     short loc_1800B5033
0x1800b4fe9  lea     rdx, [rbp+6B0h+Str]
0x1800b4ff0  lea     rcx, [rbp+6B0h+pObjectName]
0x1800b4ff7  call    cs:__imp__o__stricmp
0x1800b4ffd  test    eax, eax
0x1800b4fff  jz      loc_1800B4EAD
0x1800b5005  mov     r8, [rdi+10h]
0x1800b5009  lea     rcx, [rbp+6B0h+Str]; pObjectName
0x1800b5010  mov     edx, [rdi+18h]
0x1800b5013  call    SetFolderSecurity
0x1800b5018  mov     ebx, eax
0x1800b501a  test    eax, eax
0x1800b501c  jz      loc_1800B4EAD
0x1800b5022  mov     edi, 3002074h
0x1800b5027  jmp     short loc_1800B5033
0x1800b5029  mov     ebx, 0Dh
0x1800b502e  mov     edi, 3002066h
0x1800b5033  mov     rax, cs:gpDsEventConfig
0x1800b503a  test    rax, rax
0x1800b503d  jz      loc_1800B5105
0x1800b5043  mov     esi, 0C00007D1h
0x1800b5048  cmp     [rax+94h], r12d
0x1800b504f  jge     short loc_1800B5074
0x1800b5051  cmp     [rax+4], r12d
0x1800b5055  jz      short loc_1800B5065
0x1800b5057  xor     edx, edx
0x1800b5059  mov     ecx, r14d
0x1800b505c  call    DoLogOverride
0x1800b5061  test    eax, eax
0x1800b5063  jnz     short loc_1800B5074
0x1800b5065  mov     ecx, esi
0x1800b5067  call    DoLogMsgOverride
0x1800b506c  test    eax, eax
0x1800b506e  jz      loc_1800B5105
0x1800b5074  xor     eax, eax
0x1800b5076  mov     [rbp+6B0h+var_6F8], esi
0x1800b5079  mov     [rbp+6B0h+var_6F0], rax
0x1800b507d  mov     edx, 3
0x1800b5082  mov     [rbp+6B0h+var_6C8], rax
0x1800b5086  mov     [rbp+6B0h+var_6B4], rax
0x1800b508a  mov     [rbp+6B0h+var_6AC], eax
0x1800b508d  mov     rax, cs:gpDsEventConfig
  ... truncated ...
```
