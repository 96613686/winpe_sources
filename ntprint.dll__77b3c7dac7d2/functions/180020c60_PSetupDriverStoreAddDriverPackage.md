# PSetupDriverStoreAddDriverPackage

- ea: `0x180020c60`
- end: `0x180020f2c`
- name: `PSetupDriverStoreAddDriverPackage`
- size: `716`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002bcf0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x1800078f0`
- `0x18000b200`
- `0x180019818`
- `0x18001c914`
- `0x18001e07c`
- `0x180020c60`
- `0x1800274fc`
- `0x180027570`
- `0x1800356a8`
- `0x180035728`
- `0x1800359b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180020dff`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180020dff`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180020d8c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180020d8c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180020e12`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180020e12`
- `SETUPAPI!DriverStoreAddDriverPackageW` at `0x180020eda`
- `SETUPAPI!DriverStoreAddDriverPackageW` at `0x180020eda`
- `SETUPAPI!SetupGetInfDriverStoreLocationW` at `0x180020e82`
- `SETUPAPI!SetupGetInfDriverStoreLocationW` at `0x180020e82`

## pseudocode

```c
__int64 __fastcall PSetupDriverStoreAddDriverPackage(unsigned __int16 *a1, unsigned __int16 a2, WCHAR *a3, DWORD *a4)
{
  int v5; // r13d
  int v8; // r8d
  const int *v9; // rdx
  int v10; // esi
  int LastErrorAsFailHR; // ebx
  NCoreLibrary *v12; // rcx
  const unsigned __int16 *v13; // rax
  HANDLE FirstFileW; // r15
  NCoreLibrary *v15; // rcx
  unsigned int v16; // ebx
  DWORD ReturnBufferSize; // [rsp+20h] [rbp-E0h]
  bool v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  FILETIME FileTime2; // [rsp+48h] [rbp-B8h] BYREF
  FILETIME FileTime1; // [rsp+50h] [rbp-B0h] BYREF
  struct _SP_ALTPLATFORM_INFO_V2 AlternatePlatformInfo; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v25[64]; // [rsp+80h] [rbp-80h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR FileName[264]; // [rsp+310h] [rbp+210h] BYREF

  v5 = a2;
  memset_0(FileName, 0, 0x208u);
  if ( !a1 || !a3 || !a4 || *a4 < 0x104 )
    return (unsigned int)-2147024809;
  v9 = &PlatformArch;
  if ( *(&PlatformArch + 2 * MyPlatform + 1) != v5 )
  {
LABEL_24:
    v16 = 0;
    v19 = 0;
    NSecurityLibrary::TSidUserContext::TSidUserContext((NSecurityLibrary::TSidUserContext *)v25, (int)v9, v8);
    if ( (int)NSecurityLibrary::TSidUserContext::IsLocalSystem((NSecurityLibrary::TSidUserContext *)v25, &v19) >= 0
      && v19 )
    {
      v16 = 64;
    }
    LastErrorAsFailHR = DriverStoreAddDriverPackageW(a1, v16, 0, (unsigned __int16)v5, a3, a4);
    if ( (((unsigned __int16)LastErrorAsFailHR - 559) & 0xFFFFFFEF) == 0 )
      LastErrorAsFailHR = -2147023673;
    NSecurityLibrary::TSidUserContext::~TSidUserContext((NSecurityLibrary::TSidUserContext *)v25);
    return (unsigned int)LastErrorAsFailHR;
  }
  v10 = 0;
  v20[0] = 0;
  if ( !(unsigned int)IsNTPrintInf(a1, &PlatformArch) )
  {
    LastErrorAsFailHR = InfUsesInboxVersionRequired(a1, v20);
    if ( LastErrorAsFailHR < 0 )
      return (unsigned int)LastErrorAsFailHR;
    if ( !v20[0] )
    {
LABEL_20:
      if ( v10 )
      {
        HIWORD(AlternatePlatformInfo.FirstValidatedMinorVersion) = 0;
        *(_QWORD *)&AlternatePlatformInfo.MajorVersion = 0;
        AlternatePlatformInfo.Platform = *(&PlatformArch + 2 * MyPlatform);
        AlternatePlatformInfo.ProcessorArchitecture = *((_WORD *)&PlatformArch + 4 * MyPlatform + 2);
        ReturnBufferSize = *a4;
        *(_QWORD *)&AlternatePlatformInfo.Reserved = 0;
        AlternatePlatformInfo.cbSize = 28;
        if ( SetupGetInfDriverStoreLocationW(FileName, &AlternatePlatformInfo, 0, a3, ReturnBufferSize, a4) )
          return 0;
        else
          return (unsigned int)NCoreLibrary::GetLastErrorAsFailHR(v15);
      }
      goto LABEL_24;
    }
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !(unsigned int)GetWindowsInfDir(FileName) )
  {
    LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v12);
    if ( LastErrorAsFailHR < 0 )
      return (unsigned int)LastErrorAsFailHR;
  }
  v13 = (const unsigned __int16 *)FileNamePart(a1);
  if ( !v13 )
    return (unsigned int)-2147024809;
  LastErrorAsFailHR = StringCchCatW(FileName, 0x104u, v13);
  if ( LastErrorAsFailHR >= 0 )
  {
    FirstFileW = FindFirstFileW(FileName, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
      goto LABEL_20;
    FileTime1 = 0;
    v21 = 0;
    FileTime2 = 0;
    *(_QWORD *)v20 = 0;
    LastErrorAsFailHR = GetInfDriverVerInfo(FileName, &FileTime1, &v21);
    if ( LastErrorAsFailHR >= 0 )
    {
      LastErrorAsFailHR = GetInfDriverVerInfo(a1, &FileTime2, v20);
      if ( LastErrorAsFailHR >= 0 && v21 == *(_QWORD *)v20 && !CompareFileTime(&FileTime1, &FileTime2) )
        v10 = 1;
    }
    FindClose(FirstFileW);
    if ( LastErrorAsFailHR >= 0 )
      goto LABEL_20;
  }
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x180020c60  push    rbp
0x180020c62  push    rbx
0x180020c63  push    rsi
0x180020c64  push    rdi
0x180020c65  push    r12
0x180020c67  push    r13
0x180020c69  push    r14
0x180020c6b  push    r15
0x180020c6d  lea     rbp, [rsp-438h]
0x180020c75  sub     rsp, 538h
0x180020c7c  mov     rax, cs:__security_cookie
0x180020c83  xor     rax, rsp
0x180020c86  mov     [rbp+470h+var_50], rax
0x180020c8d  mov     r12, r8
0x180020c90  movzx   r13d, dx
0x180020c94  mov     rdi, rcx
0x180020c97  xor     edx, edx; Val
0x180020c99  mov     r8d, 208h; Size
0x180020c9f  lea     rcx, [rbp+470h+FileName]; void *
0x180020ca6  mov     r14, r9
0x180020ca9  call    memset_0
0x180020cae  test    rdi, rdi
0x180020cb1  jz      loc_180020F02
0x180020cb7  test    r12, r12
0x180020cba  jz      loc_180020F02
0x180020cc0  test    r14, r14
0x180020cc3  jz      loc_180020F02
0x180020cc9  mov     r15d, 104h
0x180020ccf  cmp     [r14], r15d
0x180020cd2  jb      loc_180020F02
0x180020cd8  movsxd  rcx, cs:MyPlatform
0x180020cdf  lea     rdx, PlatformArch; int
0x180020ce6  cmp     [rdx+rcx*8+4], r13d
0x180020ceb  jnz     loc_180020E99
0x180020cf1  xor     esi, esi
0x180020cf3  mov     rcx, rdi
0x180020cf6  mov     [rsp+570h+var_538], esi
0x180020cfa  call    IsNTPrintInf
0x180020cff  test    eax, eax
0x180020d01  jnz     short loc_180020D24
0x180020d03  lea     rdx, [rsp+570h+var_538]; int *
0x180020d08  mov     rcx, rdi; unsigned __int16 *
0x180020d0b  call    ?InfUsesInboxVersionRequired@@YAJPEBGPEAH@Z; InfUsesInboxVersionRequired(ushort const *,int *)
0x180020d10  mov     ebx, eax
0x180020d12  test    eax, eax
0x180020d14  js      loc_180020F07
0x180020d1a  cmp     [rsp+570h+var_538], esi
0x180020d1e  jz      loc_180020E20
0x180020d24  xor     edx, edx; Val
0x180020d26  lea     rcx, [rbp+470h+FindFileData]; void *
0x180020d2a  mov     r8d, 250h; Size
0x180020d30  call    memset_0
0x180020d35  lea     rcx, [rbp+470h+FileName]; unsigned __int16 *
0x180020d3c  call    GetWindowsInfDir
0x180020d41  test    eax, eax
0x180020d43  jnz     short loc_180020D54
0x180020d45  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180020d4a  mov     ebx, eax
0x180020d4c  test    eax, eax
0x180020d4e  js      loc_180020F07
0x180020d54  mov     rcx, rdi; Str
0x180020d57  call    FileNamePart
0x180020d5c  test    rax, rax
0x180020d5f  jz      loc_180020F02
0x180020d65  mov     r8, rax; unsigned __int16 *
0x180020d68  lea     rcx, [rbp+470h+FileName]; unsigned __int16 *
0x180020d6f  mov     rdx, r15; unsigned __int64
0x180020d72  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180020d77  mov     ebx, eax
0x180020d79  test    eax, eax
0x180020d7b  js      loc_180020F07
0x180020d81  lea     rdx, [rbp+470h+FindFileData]; lpFindFileData
0x180020d85  lea     rcx, [rbp+470h+FileName]; lpFileName
0x180020d8c  call    cs:__imp_FindFirstFileW
0x180020d92  mov     r15, rax
0x180020d95  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020d99  jz      loc_180020E20
0x180020d9f  xor     eax, eax
0x180020da1  lea     r8, [rsp+570h+var_530]
0x180020da6  lea     rdx, [rsp+570h+FileTime1]
0x180020dab  mov     qword ptr [rsp+570h+FileTime1.dwLowDateTime], rax
0x180020db0  lea     rcx, [rbp+470h+FileName]
0x180020db7  mov     [rsp+570h+var_530], rax
0x180020dbc  mov     qword ptr [rsp+570h+FileTime2.dwLowDateTime], rax
0x180020dc1  mov     qword ptr [rsp+570h+var_538], rax
0x180020dc6  call    GetInfDriverVerInfo
0x180020dcb  mov     ebx, eax
0x180020dcd  test    eax, eax
0x180020dcf  js      short loc_180020E0F
0x180020dd1  lea     r8, [rsp+570h+var_538]
0x180020dd6  mov     rcx, rdi
0x180020dd9  lea     rdx, [rsp+570h+FileTime2]
0x180020dde  call    GetInfDriverVerInfo
0x180020de3  mov     ebx, eax
0x180020de5  test    eax, eax
0x180020de7  js      short loc_180020E0F
0x180020de9  mov     rax, qword ptr [rsp+570h+var_538]
0x180020dee  cmp     [rsp+570h+var_530], rax
0x180020df3  jnz     short loc_180020E0F
0x180020df5  lea     rdx, [rsp+570h+FileTime2]; lpFileTime2
0x180020dfa  lea     rcx, [rsp+570h+FileTime1]; lpFileTime1
0x180020dff  call    cs:__imp_CompareFileTime
0x180020e05  test    eax, eax
0x180020e07  mov     ecx, 1
0x180020e0c  cmovz   esi, ecx
0x180020e0f  mov     rcx, r15; hFindFile
0x180020e12  call    cs:__imp_FindClose
0x180020e18  test    ebx, ebx
0x180020e1a  js      loc_180020F07
0x180020e20  test    esi, esi
0x180020e22  jz      short loc_180020E99
0x180020e24  movsxd  rcx, cs:MyPlatform
0x180020e2b  lea     rdx, PlatformArch
0x180020e32  xor     eax, eax
0x180020e34  mov     [rsp+570h+RequiredSize], r14; RequiredSize
0x180020e39  mov     word ptr [rsp+570h+AlternatePlatformInfo.FirstValidatedMinorVersion+2], ax
0x180020e3e  mov     r9, r12; ReturnBuffer
0x180020e41  xor     r8d, r8d; LocaleName
0x180020e44  mov     qword ptr [rsp+570h+AlternatePlatformInfo.MajorVersion], 0
0x180020e4d  mov     eax, [rdx+rcx*8]
0x180020e50  mov     [rsp+570h+AlternatePlatformInfo.Platform], eax
0x180020e54  movzx   eax, word ptr [rdx+rcx*8+4]
0x180020e59  lea     rdx, [rsp+570h+AlternatePlatformInfo]; AlternatePlatformInfo
0x180020e5e  mov     [rsp+570h+AlternatePlatformInfo.ProcessorArchitecture], ax
0x180020e63  lea     rcx, [rbp+470h+FileName]; FileName
0x180020e6a  mov     eax, [r14]
0x180020e6d  mov     [rsp+570h+ReturnBufferSize], eax; ReturnBufferSize
0x180020e71  mov     qword ptr [rsp+570h+AlternatePlatformInfo.12h], 0
0x180020e7a  mov     [rsp+570h+AlternatePlatformInfo.cbSize], 1Ch
0x180020e82  call    cs:__imp_SetupGetInfDriverStoreLocationW
0x180020e88  test    eax, eax
0x180020e8a  jz      short loc_180020E90
0x180020e8c  xor     ebx, ebx
0x180020e8e  jmp     short loc_180020F07
0x180020e90  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180020e95  mov     ebx, eax
0x180020e97  jmp     short loc_180020F07
0x180020e99  xor     ebx, ebx
0x180020e9b  lea     rcx, [rbp+470h+var_4F0]; this
0x180020e9f  mov     [rsp+570h+var_540], bl
0x180020ea3  call    ??0TSidUserContext@NSecurityLibrary@@QEAA@HH@Z; NSecurityLibrary::TSidUserContext::TSidUserContext(int,int)
0x180020ea8  lea     rdx, [rsp+570h+var_540]; bool *
0x180020ead  lea     rcx, [rbp+470h+var_4F0]; this
0x180020eb1  call    ?IsLocalSystem@TSidUserContext@NSecurityLibrary@@QEBAJPEA_N@Z; NSecurityLibrary::TSidUserContext::IsLocalSystem(bool *)
0x180020eb6  test    eax, eax
0x180020eb8  js      short loc_180020EC4
0x180020eba  cmp     [rsp+570h+var_540], bl
0x180020ebe  lea     eax, [rbx+40h]
0x180020ec1  cmovnz  ebx, eax
0x180020ec4  mov     [rsp+570h+RequiredSize], r14
0x180020ec9  movzx   r9d, r13w
0x180020ecd  xor     r8d, r8d
0x180020ed0  mov     qword ptr [rsp+570h+ReturnBufferSize], r12
0x180020ed5  mov     edx, ebx
0x180020ed7  mov     rcx, rdi
0x180020eda  call    cs:__imp_DriverStoreAddDriverPackageW
0x180020ee0  mov     ebx, eax
0x180020ee2  lea     rcx, [rbp+470h+var_4F0]; this
0x180020ee6  movzx   eax, ax
0x180020ee9  sub     eax, 22Fh
0x180020eee  test    eax, 0FFFFFFEFh
0x180020ef3  mov     eax, 800704C7h
0x180020ef8  cmovz   ebx, eax
0x180020efb  call    ??1TSidUserContext@NSecurityLibrary@@UEAA@XZ; NSecurityLibrary::TSidUserContext::~TSidUserContext(void)
0x180020f00  jmp     short loc_180020F07
0x180020f02  mov     ebx, 80070057h
0x180020f07  mov     eax, ebx
0x180020f09  mov     rcx, [rbp+470h+var_50]
0x180020f10  xor     rcx, rsp; StackCookie
0x180020f13  call    __security_check_cookie
0x180020f18  add     rsp, 538h
0x180020f1f  pop     r15
0x180020f21  pop     r14
0x180020f23  pop     r13
0x180020f25  pop     r12
0x180020f27  pop     rdi
0x180020f28  pop     rsi
0x180020f29  pop     rbx
0x180020f2a  pop     rbp
0x180020f2b  retn
```
