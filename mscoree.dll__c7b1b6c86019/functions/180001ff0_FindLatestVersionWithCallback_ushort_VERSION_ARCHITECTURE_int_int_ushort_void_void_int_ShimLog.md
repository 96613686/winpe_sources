# FindLatestVersionWithCallback(ushort * *,VERSION_ARCHITECTURE,int,int (*)(ushort *,void *),void *,int,ShimLog *)

- ea: `0x180001ff0`
- end: `0x1800026fc`
- name: `?FindLatestVersionWithCallback@@YAJPEAPEAGW4VERSION_ARCHITECTURE@@HP6AHPEAGPEAX@Z3HPEAVShimLog@@@Z`
- size: `1804`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002f30`
- `0x180009af4`
- `0x180029528`

## callees

- `0x180001c60`
- `0x180001ff0`
- `0x1800037b0`
- `0x180003840`
- `0x180003e00`
- `0x180003ed0`
- `0x180004230`
- `0x180004d50`
- `0x180008b2c`
- `0x18000a59c`
- `0x18000c1a8`
- `0x18000d164`
- `0x18000d614`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002230`
- `KERNEL32!GetLastError` at `0x180002255`
- `KERNEL32!GetLastError` at `0x18000226e`
- `KERNEL32!GetLastError` at `0x18000228d`
- `KERNEL32!GetLastError` at `0x180002330`
- `KERNEL32!GetLastError` at `0x18000234b`
- `KERNEL32!GetLastError` at `0x180002483`
- `KERNEL32!GetLastError` at `0x18000249e`
- `KERNEL32!GetLastError` at `0x18000253a`
- `KERNEL32!GetLastError` at `0x180002555`
- `KERNEL32!GetLastError` at `0x180002635`
- `KERNEL32!GetLastError` at `0x180002650`
- `KERNEL32!GetLastError` at `0x180002230`
- `KERNEL32!GetLastError` at `0x180002255`
- `KERNEL32!GetLastError` at `0x18000226e`
- `KERNEL32!GetLastError` at `0x18000228d`
- `KERNEL32!GetLastError` at `0x180002330`
- `KERNEL32!GetLastError` at `0x18000234b`
- `KERNEL32!GetLastError` at `0x180002483`
- `KERNEL32!GetLastError` at `0x18000249e`
- `KERNEL32!GetLastError` at `0x18000253a`
- `KERNEL32!GetLastError` at `0x180002555`
- `KERNEL32!GetLastError` at `0x180002635`
- `KERNEL32!GetLastError` at `0x180002650`
- `KERNEL32!SetLastError` at `0x180002262`
- `KERNEL32!SetLastError` at `0x180002299`
- `KERNEL32!SetLastError` at `0x180002357`
- `KERNEL32!SetLastError` at `0x1800024aa`
- `KERNEL32!SetLastError` at `0x180002561`
- `KERNEL32!SetLastError` at `0x18000265c`
- `KERNEL32!SetLastError` at `0x180002262`
- `KERNEL32!SetLastError` at `0x180002299`
- `KERNEL32!SetLastError` at `0x180002357`
- `KERNEL32!SetLastError` at `0x1800024aa`
- `KERNEL32!SetLastError` at `0x180002561`
- `KERNEL32!SetLastError` at `0x18000265c`
- `ADVAPI32!RegOpenKeyExW` at `0x1800020a8`
- `ADVAPI32!RegOpenKeyExW` at `0x18000219e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800020a8`
- `ADVAPI32!RegOpenKeyExW` at `0x18000219e`
- `ADVAPI32!RegCloseKey` at `0x1800021e4`
- `ADVAPI32!RegCloseKey` at `0x180002590`
- `ADVAPI32!RegCloseKey` at `0x1800021e4`
- `ADVAPI32!RegCloseKey` at `0x180002590`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall FindLatestVersionWithCallback(
        _QWORD *a1,
        unsigned int a2,
        int a3,
        unsigned int (__fastcall *a4)(void *, __int64),
        __int64 a5,
        int a6,
        ShimLog *a7)
{
  unsigned int (__fastcall *v7)(void *, __int64); // r13
  unsigned int v8; // ebx
  VersionStackEntry *v9; // rdi
  unsigned int v11; // r12d
  int v12; // esi
  void *v13; // r14
  int v14; // r15d
  REGSAM v15; // r9d
  int v16; // r9d
  REGSAM v17; // eax
  int v18; // eax
  unsigned int v19; // edx
  BOOL v20; // r13d
  int v21; // r15d
  WCHAR *v22; // r12
  VersionStackEntry *v23; // rcx
  REGSAM v24; // r9d
  int v25; // r9d
  REGSAM v26; // eax
  unsigned int v27; // edx
  int LatestBuild; // esi
  int v29; // eax
  wchar_t *v30; // rbx
  __int64 v31; // rcx
  __int64 v32; // rax
  unsigned __int64 v33; // r15
  unsigned __int64 v34; // rbx
  DWORD v35; // r14d
  void *v36; // rsi
  DWORD v37; // ebx
  unsigned int v38; // eax
  DWORD v39; // esi
  VersionStackEntry *v40; // rcx
  const wchar_t *v41; // rsi
  VersionStackEntry *v42; // rbx
  unsigned int v43; // edx
  VersionStackEntry *v44; // rcx
  const wchar_t *v45; // rbx
  DWORD LastError; // ebx
  WCHAR *v47; // rbx
  bool v48; // zf
  DWORD v49; // esi
  void *ConfigString; // rbx
  BOOL v51; // esi
  void *v52; // r14
  DWORD v53; // esi
  void **v54; // r14
  _QWORD *v55; // rbx
  __int16 v56; // [rsp+30h] [rbp-71h] BYREF
  int v57; // [rsp+34h] [rbp-6Dh]
  VersionStackEntry *v58; // [rsp+38h] [rbp-69h] BYREF
  unsigned int v59; // [rsp+40h] [rbp-61h] BYREF
  wchar_t *Source; // [rsp+48h] [rbp-59h] BYREF
  int v61; // [rsp+50h] [rbp-51h]
  wchar_t **p_Source; // [rsp+58h] [rbp-49h]
  void *v63; // [rsp+60h] [rbp-41h]
  BOOL v64; // [rsp+68h] [rbp-39h]
  void *v65; // [rsp+70h] [rbp-31h]
  int v66; // [rsp+78h] [rbp-29h]
  int v67; // [rsp+80h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-19h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-11h] BYREF
  DWORD v70; // [rsp+98h] [rbp-9h]
  int v71; // [rsp+9Ch] [rbp-5h]

  v7 = a4;
  v8 = a2;
  hKey = 0;
  v9 = 0;
  v58 = 0;
  if ( !a1 )
    return 2147500035LL;
  v11 = 0;
  v12 = 0;
  v57 = 0;
  v13 = 0;
  v65 = 0;
  v14 = 0;
  v66 = 0;
  if ( g_OSVersionInfo.dwMajorVersion > 5
    || (v15 = 131097, g_OSVersionInfo.dwMajorVersion == 5) && g_OSVersionInfo.dwMinorVersion )
  {
    v16 = 131609;
    if ( a2 != 1 )
      v16 = 131097;
    v17 = v16;
    v15 = v16 | 0x100;
    if ( a2 - 2 > 1 )
      v15 = v17;
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\.NETFramework\\Policy\\", 0, v15, &hKey) )
    goto LABEL_106;
  v18 = BuildMajorMinorStack(hKey, (struct VersionStack *)&v58);
  LODWORD(p_Source) = v18;
  if ( v18 < 0 )
  {
    v9 = v58;
    v11 = v18;
    v12 = v57;
    goto LABEL_106;
  }
  v20 = 0;
  v64 = 0;
  v21 = a3;
  if ( a3 )
  {
    v22 = VersionStack::WhidbeyCappedPop((VersionStack *)&v58);
    v63 = v22;
    v9 = v58;
    if ( !v22 )
      goto LABEL_19;
    v20 = 1;
  }
  else
  {
    v9 = v58;
    v23 = v58;
    if ( !v58 )
    {
      v22 = 0;
      v63 = 0;
      goto LABEL_19;
    }
    v9 = (VersionStackEntry *)*((_QWORD *)v58 + 1);
    v58 = v9;
    v22 = *(WCHAR **)v23;
    *(_QWORD *)v23 = 0;
    VersionStackEntry::`scalar deleting destructor'(v23, v19);
    v63 = v22;
    v20 = v22 != 0;
  }
LABEL_18:
  v64 = v20;
  while ( 1 )
  {
LABEL_19:
    if ( !v22 )
      goto LABEL_102;
    phkResult = 0;
    if ( g_OSVersionInfo.dwMajorVersion > 5
      || (v24 = 131097, g_OSVersionInfo.dwMajorVersion == 5) && g_OSVersionInfo.dwMinorVersion )
    {
      v25 = 131609;
      if ( v8 != 1 )
        v25 = 131097;
      v26 = v25;
      v24 = v25 | 0x100;
      if ( v8 - 2 > 1 )
        v24 = v26;
    }
    if ( !RegOpenKeyExW(hKey, v22, 0, v24, &phkResult) )
      break;
LABEL_60:
    v40 = v9;
    if ( v21 )
    {
      if ( v9
        && (v9 = (VersionStackEntry *)*((_QWORD *)v9 + 1),
            v58 = v9,
            v41 = *(const wchar_t **)v40,
            *(_QWORD *)v40 = 0,
            VersionStackEntry::`scalar deleting destructor'(v40, v27),
            v41) )
      {
        v59 = 0;
        v67 = 0;
        v56 = 0;
        if ( swscanf(v41, L"%c%u.%u", &v56, &v59, &v67) == 3 && ((v56 - 86) & 0xFFDF) == 0 && v59 > 2 && v9 )
        {
          v42 = v9;
          while ( 1 )
          {
            v56 = 0;
            if ( swscanf(*(const wchar_t *const *)v42, L"%c%u.%u", &v56, &v59, &v67) == 3
              && ((v56 - 86) & 0xFFDF) == 0
              && v59 <= 2 )
            {
              break;
            }
            v42 = (VersionStackEntry *)*((_QWORD *)v42 + 1);
            if ( !v42 )
              goto LABEL_80;
          }
          v41 = *(const wchar_t **)v42;
          do
          {
            v44 = v9;
            if ( v9 )
            {
              v9 = (VersionStackEntry *)*((_QWORD *)v9 + 1);
              v58 = v9;
              v45 = *(const wchar_t **)v44;
              *(_QWORD *)v44 = 0;
              VersionStackEntry::`scalar deleting destructor'(v44, v43);
            }
            else
            {
              v45 = 0;
            }
          }
          while ( v45 != v41 );
        }
      }
      else
      {
        v41 = 0;
      }
LABEL_80:
      if ( v20 )
      {
        LastError = GetLastError();
        ClrFreeInProcessHeapBootstrap(0, v22);
        if ( LastError )
        {
          if ( !GetLastError() )
            SetLastError(LastError);
        }
        v20 = 0;
        v64 = 0;
      }
      v22 = (WCHAR *)v41;
      v63 = (void *)v41;
      v8 = a2;
      if ( v41 )
      {
        v20 = 1;
        goto LABEL_18;
      }
    }
    else
    {
      if ( v9 )
      {
        v9 = (VersionStackEntry *)*((_QWORD *)v9 + 1);
        v58 = v9;
        v47 = *(WCHAR **)v40;
        *(_QWORD *)v40 = 0;
        VersionStackEntry::`scalar deleting destructor'(v40, v27);
      }
      else
      {
        v47 = 0;
      }
      if ( v20 )
      {
        operator delete(v22);
        v20 = 0;
        v64 = 0;
      }
      v22 = v47;
      v63 = v47;
      v48 = v47 == 0;
      v8 = a2;
      if ( !v48 )
      {
        v20 = 1;
        goto LABEL_18;
      }
    }
  }
  Source = 0;
  v61 = 0;
  p_Source = &Source;
  LatestBuild = FindLatestBuild(phkResult, &Source);
  LODWORD(p_Source) = LatestBuild;
  v29 = v61;
  if ( Source )
    v29 = 1;
  v61 = v29;
  RegCloseKey(phkResult);
  v30 = Source;
  if ( Source )
  {
    v31 = -1;
    do
      ++v31;
    while ( v22[v31] );
    v32 = -1;
    do
      ++v32;
    while ( Source[v32] );
    v33 = v32 + v31 + 2;
    v34 = 2 * v33;
    if ( !is_mul_ok(v33, 2u) )
      v34 = -1;
    v35 = GetLastError();
    v70 = v35;
    v71 = 2;
    v36 = ClrAllocInProcessHeapBootstrap(0, v34);
    if ( v35 && !GetLastError() )
      SetLastError(v35);
    if ( v66 )
    {
      v37 = GetLastError();
      if ( v65 )
        ClrFreeInProcessHeapBootstrap(0, v65);
      if ( v37 && !GetLastError() )
        SetLastError(v37);
      v66 = 0;
    }
    v13 = v36;
    v65 = v36;
    if ( !v36 )
    {
      LODWORD(p_Source) = -2147024882;
      v30 = Source;
LABEL_95:
      if ( v61 )
      {
        v49 = GetLastError();
        if ( v30 )
          ClrFreeInProcessHeapBootstrap(0, v30);
        if ( v49 && !GetLastError() )
          SetLastError(v49);
      }
      goto LABEL_101;
    }
    v66 = 1;
    wcscpy_s((wchar_t *)v36, v33, v22);
    wcscat_s((wchar_t *)v36, v33, L".");
    wcscat_s((wchar_t *)v36, v33, Source);
    v30 = Source;
    LatestBuild = (int)p_Source;
    v21 = a3;
  }
  if ( LatestBuild < 0 )
    goto LABEL_95;
  if ( LatestBuild || a4 && (v38 = a4(v13, a5), v30 = Source, !v38) )
  {
    if ( v61 )
    {
      v39 = GetLastError();
      if ( v30 )
        ClrFreeInProcessHeapBootstrap(0, v30);
      if ( v39 && !GetLastError() )
        SetLastError(v39);
      v61 = 0;
    }
    goto LABEL_60;
  }
  v12 = 1;
  v57 = 1;
  if ( v61 )
  {
    v53 = GetLastError();
    if ( v30 )
      ClrFreeInProcessHeapBootstrap(0, v30);
    if ( v53 && !GetLastError() )
      SetLastError(v53);
LABEL_101:
    v8 = a2;
LABEL_102:
    v12 = v57;
    goto LABEL_103;
  }
  v8 = a2;
LABEL_103:
  if ( v20 )
    operator delete(v22);
  v7 = a4;
  v11 = (unsigned int)p_Source;
  v14 = v66;
LABEL_106:
  if ( hKey )
    RegCloseKey(hKey);
  if ( !a6 && v12 )
  {
    v52 = v65;
  }
  else
  {
    ConfigString = (void *)GetConfigString(L"DefaultVersion", 0, v8);
    v63 = ConfigString;
    v51 = ConfigString != 0;
    v64 = v51;
    if ( ConfigString && (a6 || !v7 || v7(ConfigString, a5)) )
    {
      if ( a7 )
        ShimLog::Log(a7, 0x44u, ConfigString);
      v51 = 0;
      if ( v14 )
        operator delete(v65);
      v52 = ConfigString;
      v11 = 0;
    }
    else
    {
      v52 = v65;
    }
    if ( v51 )
      operator delete(ConfigString);
  }
  *a1 = v52;
  while ( v9 )
  {
    v54 = (void **)v9;
    v55 = (_QWORD *)((char *)v9 + 8);
    v9 = (VersionStackEntry *)*((_QWORD *)v9 + 1);
    if ( *v54 )
    {
      operator delete(*v54);
      *v54 = 0;
    }
    *v55 = 0;
    operator delete(v54);
  }
  return v11;
}

```

## disassembly

```asm
0x180001ff0  mov     [rsp-8+arg_18], r9
0x180001ff5  mov     [rsp-8+arg_10], r8d
0x180001ffa  mov     [rsp-8+arg_8], edx
0x180001ffe  mov     [rsp-8+arg_0], rcx
0x180002003  push    rbp
0x180002004  push    rbx
0x180002005  push    rsi
0x180002006  push    rdi
0x180002007  push    r12
0x180002009  push    r13
0x18000200b  push    r14
0x18000200d  push    r15
0x18000200f  lea     rbp, [rsp-7]
0x180002014  sub     rsp, 0A8h
0x18000201b  mov     r13, r9
0x18000201e  mov     ebx, edx
0x180002020  mov     [rbp+3Fh+hKey], 0
0x180002028  xor     edi, edi
0x18000202a  mov     [rbp+3Fh+var_A8], rdi
0x18000202e  test    rcx, rcx
0x180002031  jnz     short loc_18000203D
0x180002033  mov     eax, 80004003h
0x180002038  jmp     loc_1800026E8
0x18000203d  xor     r12d, r12d
0x180002040  xor     esi, esi
0x180002042  mov     [rbp+3Fh+var_AC], esi
0x180002045  xor     r14d, r14d
0x180002048  mov     [rbp+3Fh+var_70], r14
0x18000204c  xor     r15d, r15d
0x18000204f  mov     [rbp+3Fh+var_68], r15d
0x180002053  mov     ecx, 20019h
0x180002058  cmp     cs:?g_OSVersionInfo@@3U_OSVERSIONINFOW@@A.dwMajorVersion, 5; _OSVERSIONINFOW g_OSVersionInfo ...
0x18000205f  ja      short loc_18000206F
0x180002061  mov     r9d, ecx
0x180002064  jnz     short loc_18000208E
0x180002066  cmp     cs:?g_OSVersionInfo@@3U_OSVERSIONINFOW@@A.dwMinorVersion, r15d; _OSVERSIONINFOW g_OSVersionInfo ...
0x18000206d  jbe     short loc_18000208E
0x18000206f  mov     r9d, 20219h
0x180002075  cmp     edx, 1
0x180002078  cmovnz  r9d, ecx
0x18000207c  lea     ecx, [rdx-2]
0x18000207f  mov     eax, r9d
0x180002082  bts     r9d, 8
0x180002087  cmp     ecx, 1
0x18000208a  cmova   r9d, eax; samDesired
0x18000208e  lea     rax, [rbp+3Fh+hKey]
0x180002092  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180002097  xor     r8d, r8d; ulOptions
0x18000209a  lea     rdx, SubKey; "Software\\Microsoft\\.NETFramework\\Pol"...
0x1800020a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800020a8  call    cs:__imp_RegOpenKeyExW
0x1800020ae  test    eax, eax
0x1800020b0  jnz     loc_180002587
0x1800020b6  lea     rdx, [rbp+3Fh+var_A8]; struct VersionStack *
0x1800020ba  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800020be  call    ?BuildMajorMinorStack@@YAJPEAUHKEY__@@PEAVVersionStack@@@Z; BuildMajorMinorStack(HKEY__ *,VersionStack *)
0x1800020c3  mov     dword ptr [rbp+3Fh+var_88], eax
0x1800020c6  test    eax, eax
0x1800020c8  js      loc_180002670
0x1800020ce  xor     esi, esi
0x1800020d0  mov     r13d, esi
0x1800020d3  mov     [rbp+3Fh+var_78], esi
0x1800020d6  mov     r15d, [rbp+3Fh+arg_10]
0x1800020da  test    r15d, r15d
0x1800020dd  jz      short loc_180002100
0x1800020df  lea     rcx, [rbp+3Fh+var_A8]; this
0x1800020e3  call    ?WhidbeyCappedPop@VersionStack@@QEAAPEAGXZ; VersionStack::WhidbeyCappedPop(void)
0x1800020e8  mov     r12, rax
0x1800020eb  mov     [rbp+3Fh+var_80], rax
0x1800020ef  mov     rdi, [rbp+3Fh+var_A8]
0x1800020f3  test    rax, rax
0x1800020f6  jz      short loc_180002140
0x1800020f8  mov     r13d, 1
0x1800020fe  jmp     short loc_180002138
0x180002100  mov     rdi, [rbp+3Fh+var_A8]
0x180002104  mov     rcx, rdi; this
0x180002107  test    rdi, rdi
0x18000210a  jnz     short loc_180002115
0x18000210c  mov     r12, rsi
0x18000210f  mov     [rbp+3Fh+var_80], rsi
0x180002113  jmp     short loc_180002140
0x180002115  mov     rdi, [rdi+8]
0x180002119  mov     [rbp+3Fh+var_A8], rdi
0x18000211d  mov     r12, [rcx]
0x180002120  mov     [rcx], rsi
0x180002123  call    ??_GVersionStackEntry@@AEAAPEAXI@Z; VersionStackEntry::`scalar deleting destructor'(uint)
0x180002128  mov     [rbp+3Fh+var_80], r12
0x18000212c  test    r12, r12
0x18000212f  mov     eax, 1
0x180002134  cmovnz  r13d, eax
0x180002138  mov     [rbp+3Fh+var_78], r13d
0x18000213c  nop     dword ptr [rax+00h]
0x180002140  test    r12, r12
0x180002143  jz      loc_18000256B
0x180002149  mov     [rbp+3Fh+var_50], rsi
0x18000214d  cmp     cs:?g_OSVersionInfo@@3U_OSVERSIONINFOW@@A.dwMajorVersion, 5; _OSVERSIONINFOW g_OSVersionInfo ...
0x180002154  ja      short loc_180002167
0x180002156  mov     r9d, 20019h
0x18000215c  jnz     short loc_18000218B
0x18000215e  cmp     cs:?g_OSVersionInfo@@3U_OSVERSIONINFOW@@A.dwMinorVersion, 0; _OSVERSIONINFOW g_OSVersionInfo ...
0x180002165  jbe     short loc_18000218B
0x180002167  mov     r9d, 20219h
0x18000216d  cmp     ebx, 1
0x180002170  mov     eax, 20019h
0x180002175  cmovnz  r9d, eax
0x180002179  lea     ecx, [rbx-2]
0x18000217c  mov     eax, r9d
0x18000217f  bts     r9d, 8
0x180002184  cmp     ecx, 1
0x180002187  cmova   r9d, eax; samDesired
0x18000218b  lea     rax, [rbp+3Fh+var_50]
0x18000218f  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180002194  xor     r8d, r8d; ulOptions
0x180002197  mov     rdx, r12; lpSubKey
0x18000219a  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18000219e  call    cs:__imp_RegOpenKeyExW
0x1800021a4  test    eax, eax
0x1800021a6  jnz     loc_180002367
0x1800021ac  mov     [rbp+3Fh+Source], rsi
0x1800021b0  mov     [rbp+3Fh+var_90], esi
0x1800021b3  lea     rax, [rbp+3Fh+Source]
0x1800021b7  mov     [rbp+3Fh+var_88], rax
0x1800021bb  lea     rdx, [rbp+3Fh+Source]; unsigned __int16 **
0x1800021bf  mov     rcx, [rbp+3Fh+var_50]; hKey
0x1800021c3  call    ?FindLatestBuild@@YAJPEAUHKEY__@@PEAPEAG@Z; FindLatestBuild(HKEY__ *,ushort * *)
0x1800021c8  mov     esi, eax
0x1800021ca  mov     dword ptr [rbp+3Fh+var_88], eax
0x1800021cd  mov     eax, [rbp+3Fh+var_90]
0x1800021d0  cmp     [rbp+3Fh+Source], 0
0x1800021d5  mov     ecx, 1
0x1800021da  cmovnz  eax, ecx
0x1800021dd  mov     [rbp+3Fh+var_90], eax
0x1800021e0  mov     rcx, [rbp+3Fh+var_50]; hKey
0x1800021e4  call    cs:__imp_RegCloseKey
0x1800021ea  mov     rbx, [rbp+3Fh+Source]
0x1800021ee  test    rbx, rbx
0x1800021f1  jz      loc_1800022F8
0x1800021f7  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800021fe  mov     rcx, r8
0x180002201  lea     rcx, [rcx+1]
0x180002205  cmp     word ptr [r12+rcx*2], 0
0x18000220b  jnz     short loc_180002201
0x18000220d  mov     rax, r8
0x180002210  inc     rax
0x180002213  cmp     word ptr [rbx+rax*2], 0
0x180002218  jnz     short loc_180002210
0x18000221a  lea     r15, [rcx+2]
0x18000221e  add     r15, rax
0x180002221  mov     eax, 2
0x180002226  mul     r15
0x180002229  mov     rbx, rax
0x18000222c  cmovb   rbx, r8
0x180002230  call    cs:__imp_GetLastError
0x180002236  mov     r14d, eax
0x180002239  mov     [rbp+3Fh+var_48], eax
0x18000223c  mov     [rbp+3Fh+var_44], 2
0x180002243  mov     rdx, rbx; unsigned __int64
0x180002246  xor     ecx, ecx; unsigned int
0x180002248  call    ?ClrAllocInProcessHeapBootstrap@@YAPEAXK_K@Z; ClrAllocInProcessHeapBootstrap(ulong,unsigned __int64)
0x18000224d  mov     rsi, rax
0x180002250  test    r14d, r14d
0x180002253  jz      short loc_180002268
0x180002255  call    cs:__imp_GetLastError
0x18000225b  test    eax, eax
0x18000225d  jnz     short loc_180002268
0x18000225f  mov     ecx, r14d; dwErrCode
0x180002262  call    cs:__imp_SetLastError
0x180002268  cmp     [rbp+3Fh+var_68], 0
0x18000226c  jz      short loc_1800022A7
0x18000226e  call    cs:__imp_GetLastError
0x180002274  mov     ebx, eax
0x180002276  mov     r14, [rbp+3Fh+var_70]
0x18000227a  test    r14, r14
0x18000227d  jz      short loc_180002289
0x18000227f  mov     rdx, r14; void *
0x180002282  xor     ecx, ecx; unsigned int
0x180002284  call    ?ClrFreeInProcessHeapBootstrap@@YAHKPEAX@Z; ClrFreeInProcessHeapBootstrap(ulong,void *)
0x180002289  test    ebx, ebx
0x18000228b  jz      short loc_1800022A0
0x18000228d  call    cs:__imp_GetLastError
0x180002293  test    eax, eax
0x180002295  jnz     short loc_1800022A0
0x180002297  mov     ecx, ebx; dwErrCode
0x180002299  call    cs:__imp_SetLastError
0x18000229f  nop
0x1800022a0  mov     [rbp+3Fh+var_68], 0
0x1800022a7  mov     r14, rsi
0x1800022aa  mov     [rbp+3Fh+var_70], rsi
0x1800022ae  test    rsi, rsi
0x1800022b1  jz      loc_180002529
0x1800022b7  mov     [rbp+3Fh+var_68], 1
0x1800022be  mov     r8, r12; Source
0x1800022c1  mov     rdx, r15; SizeInWords
0x1800022c4  mov     rcx, rsi; Destination
0x1800022c7  call    wcscpy_s
0x1800022cc  lea     r8, Delimiter; "."
0x1800022d3  mov     rdx, r15; SizeInWords
0x1800022d6  mov     rcx, rsi; Destination
0x1800022d9  call    wcscat_s
0x1800022de  mov     r8, [rbp+3Fh+Source]; Source
0x1800022e2  mov     rdx, r15; SizeInWords
0x1800022e5  mov     rcx, rsi; Destination
0x1800022e8  call    wcscat_s
0x1800022ed  mov     rbx, [rbp+3Fh+Source]
0x1800022f1  mov     esi, dword ptr [rbp+3Fh+var_88]
0x1800022f4  mov     r15d, [rbp+3Fh+arg_10]
0x1800022f8  test    esi, esi
0x1800022fa  js      loc_180002534
0x180002300  jnz     short loc_18000232A
0x180002302  mov     rsi, [rbp+3Fh+arg_18]
0x180002306  test    rsi, rsi
0x180002309  jz      loc_180002627
0x18000230f  mov     rdx, [rbp+3Fh+arg_20]
0x180002313  mov     rcx, r14
0x180002316  mov     rax, rsi
0x180002319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000231e  mov     rbx, [rbp+3Fh+Source]
0x180002322  test    eax, eax
0x180002324  jnz     loc_180002627
0x18000232a  cmp     [rbp+3Fh+var_90], 0
0x18000232e  jz      short loc_180002365
0x180002330  call    cs:__imp_GetLastError
0x180002336  mov     esi, eax
0x180002338  test    rbx, rbx
0x18000233b  jz      short loc_180002347
0x18000233d  mov     rdx, rbx; void *
0x180002340  xor     ecx, ecx; unsigned int
0x180002342  call    ?ClrFreeInProcessHeapBootstrap@@YAHKPEAX@Z; ClrFreeInProcessHeapBootstrap(ulong,void *)
0x180002347  test    esi, esi
0x180002349  jz      short loc_18000235E
0x18000234b  call    cs:__imp_GetLastError
0x180002351  test    eax, eax
0x180002353  jnz     short loc_18000235E
0x180002355  mov     ecx, esi; dwErrCode
0x180002357  call    cs:__imp_SetLastError
0x18000235d  nop
0x18000235e  xor     esi, esi
0x180002360  mov     [rbp+3Fh+var_90], esi
0x180002363  jmp     short loc_180002367
0x180002365  xor     esi, esi
0x180002367  mov     rcx, rdi; this
0x18000236a  test    r15d, r15d
0x18000236d  jz      loc_1800024DB
0x180002373  xor     ebx, ebx
0x180002375  test    rdi, rdi
0x180002378  jz      loc_18000247B
0x18000237e  mov     rdi, [rdi+8]
0x180002382  mov     [rbp+3Fh+var_A8], rdi
0x180002386  mov     rsi, [rcx]
0x180002389  mov     [rcx], rbx
0x18000238c  call    ??_GVersionStackEntry@@AEAAPEAXI@Z; VersionStackEntry::`scalar deleting destructor'(uint)
0x180002391  test    rsi, rsi
0x180002394  jz      loc_18000247B
0x18000239a  mov     [rbp+3Fh+var_A0], ebx
0x18000239d  mov     [rbp+3Fh+var_60], ebx
0x1800023a0  mov     [rbp+3Fh+var_B0], bx
0x1800023a4  lea     rax, [rbp+3Fh+var_60]
0x1800023a8  mov     [rsp+0E0h+phkResult], rax
0x1800023ad  lea     r9, [rbp+3Fh+var_A0]
0x1800023b1  lea     r8, [rbp+3Fh+var_B0]
0x1800023b5  lea     rdx, aCUU; "%c%u.%u"
0x1800023bc  mov     rcx, rsi; Buffer
0x1800023bf  call    swscanf
0x1800023c4  cmp     eax, 3
0x1800023c7  jnz     loc_18000247E
0x1800023cd  movzx   eax, [rbp+3Fh+var_B0]
0x1800023d1  sub     ax, 56h ; 'V'
0x1800023d5  mov     ecx, 0FFDFh
0x1800023da  test    cx, ax
0x1800023dd  jnz     loc_18000247E
0x1800023e3  cmp     [rbp+3Fh+var_A0], 2
0x1800023e7  jbe     loc_18000247E
0x1800023ed  test    rdi, rdi
0x1800023f0  jz      loc_18000247E
0x1800023f6  mov     rbx, rdi
0x1800023f9  nop     dword ptr [rax+00000000h]
0x180002400  xor     eax, eax
0x180002402  mov     [rbp+3Fh+var_B0], ax
0x180002406  lea     rax, [rbp+3Fh+var_60]
0x18000240a  mov     [rsp+0E0h+phkResult], rax
0x18000240f  lea     r9, [rbp+3Fh+var_A0]
0x180002413  lea     r8, [rbp+3Fh+var_B0]
0x180002417  lea     rdx, aCUU; "%c%u.%u"
0x18000241e  mov     rcx, [rbx]; Buffer
0x180002421  call    swscanf
0x180002426  cmp     eax, 3
0x180002429  jnz     short loc_180002443
0x18000242b  movzx   eax, [rbp+3Fh+var_B0]
0x18000242f  sub     ax, 56h ; 'V'
0x180002433  mov     ecx, 0FFDFh
0x180002438  test    cx, ax
0x18000243b  jnz     short loc_180002443
0x18000243d  cmp     [rbp+3Fh+var_A0], 2
0x180002441  jbe     short loc_18000244E
0x180002443  mov     rbx, [rbx+8]
0x180002447  test    rbx, rbx
0x18000244a  jnz     short loc_180002400
0x18000244c  jmp     short loc_18000247E
0x18000244e  mov     rsi, [rbx]
0x180002451  mov     rcx, rdi; this
  ... truncated ...
```
