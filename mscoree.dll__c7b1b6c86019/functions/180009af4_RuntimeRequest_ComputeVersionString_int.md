# RuntimeRequest::ComputeVersionString(int)

- ea: `0x180009af4`
- end: `0x18000a595`
- name: `?ComputeVersionString@RuntimeRequest@@QEAAJH@Z`
- size: `2721`
- prototype: `__int64 __fastcall(unsigned __int16 **this, int)`
- caller_count: `7`
- callee_count: `29`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180008484`
- `0x18000a6a4`
- `0x1800297ac`
- `0x18002cdbc`
- `0x18002dfb4`
- `0x18002e23c`
- `0x18002e4f0`

## callees

- `0x180001f20`
- `0x180001ff0`
- `0x180003840`
- `0x180003ed0`
- `0x180007300`
- `0x180008bcc`
- `0x180008f00`
- `0x180009af4`
- `0x18000a59c`
- `0x18000ac2c`
- `0x18000b324`
- `0x18000b3c4`
- `0x18000b5e8`
- `0x18000c1a8`
- `0x18000d614`
- `0x180029528`
- `0x18002a43c`
- `0x18002adf4`
- `0x18002b1cc`
- `0x18002c01c`
- `0x180030758`
- `0x180030798`
- `0x180031008`
- `0x1800313bc`
- `0x18003145c`
- `0x18003fff4`
- `0x180040128`
- `0x180041ac0`
- `0x180041b20`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180009bf9`
- `KERNEL32!GetModuleFileNameW` at `0x180009bf9`
- `KERNEL32!GetModuleHandleW` at `0x18000a269`
- `KERNEL32!GetModuleHandleW` at `0x18000a269`
- `KERNEL32!CloseHandle` at `0x18000a521`
- `KERNEL32!CloseHandle` at `0x18000a521`
- `SHLWAPI!PathIsRelativeW` at `0x180009da5`
- `SHLWAPI!PathIsRelativeW` at `0x180009da5`
- `SHLWAPI!PathCombineW` at `0x180009e3c`
- `SHLWAPI!PathCombineW` at `0x180009e3c`

## string_xrefs

- `0x180009e9b`: `.config`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __fastcall RuntimeRequest::ComputeVersionString(const unsigned __int16 **this, int a2)
{
  ShimLog *v3; // rsi
  unsigned __int16 **v4; // rdx
  RuntimeRequest *v5; // rcx
  const unsigned __int16 *v6; // r8
  RuntimeRequest *v7; // rcx
  int result; // eax
  int LatestVersionWithCallback; // edi
  WCHAR *v10; // rdx
  RuntimeRequest *v11; // rcx
  const unsigned __int16 *v12; // r8
  const wchar_t *v13; // r15
  int ConfigFileFromWin32Manifest; // eax
  wchar_t *v15; // rcx
  wchar_t *v16; // rcx
  int ApplicationPathFromWin32Manifest; // eax
  RuntimeRequest *v18; // rcx
  wchar_t *v19; // rcx
  const WCHAR *v20; // rcx
  const WCHAR *v21; // r8
  const WCHAR *v22; // rdx
  WCHAR *v23; // rcx
  const wchar_t *v24; // r15
  __int64 v25; // rdx
  wchar_t *v26; // rcx
  __int64 v27; // rdx
  wchar_t *v28; // rcx
  wchar_t *v29; // rcx
  const unsigned __int16 *v30; // r8
  RuntimeRequest *v31; // r15
  unsigned __int16 *v32; // rdi
  unsigned int v33; // edx
  RuntimeRequest *v34; // rcx
  unsigned __int16 *v35; // r12
  unsigned __int16 *v36; // r12
  unsigned __int16 *ConfigString; // rdi
  unsigned __int16 *v38; // rcx
  const unsigned __int16 *v39; // r8
  const unsigned __int16 *v40; // r8
  unsigned __int16 *v41; // r12
  unsigned __int64 v42; // rax
  __int64 v43; // rcx
  unsigned __int64 v44; // rcx
  void *v45; // rsp
  void *v46; // rsp
  unsigned __int8 *ModuleHandleW; // rax
  unsigned __int16 *PERuntimeVersion; // r12
  unsigned __int16 *v49; // r12
  unsigned __int16 *v50; // r12
  const unsigned __int16 *v51; // r8
  void **v52; // r12
  __int64 v53; // r13
  void *v54; // rcx
  const unsigned __int16 *v55; // r8
  unsigned __int16 *v56; // r14
  unsigned __int16 *v57; // rdi
  unsigned __int16 *v58; // rcx
  unsigned __int16 v59[2]; // [rsp+40h] [rbp+0h] BYREF
  LPCWSTR pszPath; // [rsp+50h] [rbp+10h] BYREF
  unsigned __int64 v61; // [rsp+58h] [rbp+18h]
  unsigned __int64 v62; // [rsp+60h] [rbp+20h]
  wchar_t Destination[260]; // [rsp+68h] [rbp+28h] BYREF
  LPWSTR lpFilename; // [rsp+270h] [rbp+230h] BYREF
  unsigned __int64 v65; // [rsp+278h] [rbp+238h]
  unsigned __int64 v66; // [rsp+280h] [rbp+240h]
  _BYTE v67[520]; // [rsp+288h] [rbp+248h] BYREF
  LPWSTR pszDest[3]; // [rsp+490h] [rbp+450h] BYREF
  char v69; // [rsp+4A8h] [rbp+468h] BYREF
  wchar_t Source[8]; // [rsp+6B0h] [rbp+670h] BYREF

  *(_DWORD *)v59 = a2;
  v3 = (ShimLog *)(this + 14);
  ShimLog::StartLog((ShimLog *)(this + 14));
  RuntimeRequest::LogStartValues((RuntimeRequest *)this);
  if ( (unsigned int)UseLocalRuntime() )
  {
    ShimLog::Log(v3, 0x32u);
    result = RuntimeRequest::CopyString(v7, this, &word_180050144, 1);
    if ( result >= 0 )
    {
      *((_DWORD *)this + 12) = 1;
      *((_DWORD *)this + 13) = 1;
      return 1;
    }
    return result;
  }
  LatestVersionWithCallback = 0;
  if ( !this[2] )
  {
    lpFilename = 0;
    v65 = 0;
    v66 = 512;
    LatestVersionWithCallback = CQuickArrayBase<unsigned short>::ReSizeNoThrow(&lpFilename, 269);
    if ( LatestVersionWithCallback < 0 )
    {
LABEL_6:
      CQuickArray<unsigned short>::~CQuickArray<unsigned short>(&lpFilename);
      return LatestVersionWithCallback;
    }
    v10 = (WCHAR *)v67;
    if ( lpFilename )
      v10 = lpFilename;
    GetModuleFileNameW(0, v10, v66 >> 1);
    v12 = (const unsigned __int16 *)v67;
    if ( lpFilename )
      v12 = lpFilename;
    RuntimeRequest::CopyString(v11, this + 2, v12, 1);
    CQuickArray<unsigned short>::~CQuickArray<unsigned short>(&lpFilename);
  }
  if ( !this[3] && !this[4] )
  {
    *(_QWORD *)Source = 0;
    v13 = this[2];
    lpFilename = 0;
    v65 = 0;
    v66 = 512;
    pszPath = 0;
    v61 = 0;
    v62 = 512;
    ConfigFileFromWin32Manifest = GetConfigFileFromWin32Manifest(Destination, 0x100u, (unsigned __int64 *)Source);
    if ( ConfigFileFromWin32Manifest < 0 )
    {
      if ( ConfigFileFromWin32Manifest != -2147024774 )
        goto LABEL_51;
      LatestVersionWithCallback = CQuickArrayBase<unsigned short>::ReSizeNoThrow(&pszPath, *(_QWORD *)Source);
      if ( LatestVersionWithCallback < 0 )
      {
LABEL_18:
        CQuickArray<unsigned short>::~CQuickArray<unsigned short>(&pszPath);
        goto LABEL_6;
      }
      v15 = Destination;
      if ( pszPath )
        v15 = (wchar_t *)pszPath;
      if ( (int)GetConfigFileFromWin32Manifest(v15, v62 >> 1, (unsigned __int64 *)Source) < 0 )
        goto LABEL_51;
    }
    v16 = (wchar_t *)v67;
    if ( lpFilename )
      v16 = lpFilename;
    ApplicationPathFromWin32Manifest = GetApplicationPathFromWin32Manifest(v16, v66 >> 1, (unsigned __int64 *)Source);
    LatestVersionWithCallback = ApplicationPathFromWin32Manifest;
    if ( ApplicationPathFromWin32Manifest < 0 )
    {
      if ( ApplicationPathFromWin32Manifest != -2147024774 )
        goto LABEL_51;
      LatestVersionWithCallback = CQuickArrayBase<unsigned short>::ReSizeNoThrow(&lpFilename, *(_QWORD *)Source);
      if ( LatestVersionWithCallback < 0 )
        goto LABEL_18;
      v19 = (wchar_t *)v67;
      if ( lpFilename )
        v19 = lpFilename;
      LatestVersionWithCallback = GetApplicationPathFromWin32Manifest(v19, v66 >> 1, (unsigned __int64 *)Source);
      if ( LatestVersionWithCallback < 0 )
        goto LABEL_51;
    }
    if ( v61 >= 2 )
    {
      if ( v65 >= 2 )
      {
        v20 = Destination;
        if ( pszPath )
          v20 = pszPath;
        if ( PathIsRelativeW(v20) )
        {
          pszDest[0] = 0;
          pszDest[1] = 0;
          pszDest[2] = (LPWSTR)512;
          LatestVersionWithCallback = CQuickArrayBase<unsigned short>::ReSizeNoThrow(pszDest, (v65 >> 1) + (v61 >> 1));
          if ( LatestVersionWithCallback < 0 )
          {
LABEL_36:
            CQuickArray<unsigned short>::~CQuickArray<unsigned short>(pszDest);
            goto LABEL_18;
          }
          v21 = Destination;
          if ( pszPath )
            v21 = pszPath;
          v22 = (const WCHAR *)v67;
          if ( lpFilename )
            v22 = lpFilename;
          v23 = (WCHAR *)&v69;
          if ( pszDest[0] )
            v23 = pszDest[0];
          v24 = PathCombineW(v23, v22, v21);
          if ( v24 )
          {
            v25 = -1;
            do
              ++v25;
            while ( v24[v25] );
            LatestVersionWithCallback = CQuickArrayBase<unsigned short>::ReSizeNoThrow(&pszPath, v25 + 1);
            if ( LatestVersionWithCallback < 0 )
              goto LABEL_36;
            v26 = Destination;
            if ( pszPath )
              v26 = (wchar_t *)pszPath;
            wcscpy_s(v26, v62 >> 1, v24);
          }
          CQuickArray<unsigned short>::~CQuickArray<unsigned short>(pszDest);
        }
      }
    }
    else
    {
LABEL_51:
      wcscpy(Source, L".config");
      v27 = -1;
      do
        ++v27;
      while ( v13[v27] );
      LatestVersionWithCallback = CQuickArrayBase<unsigned short>::ReSizeNoThrow(&pszPath, v27 + 8);
      if ( LatestVersionWithCallback < 0 )
        goto LABEL_18;
      v28 = Destination;
      if ( pszPath )
        v28 = (wchar_t *)pszPath;
      wcscpy_s(v28, v62 >> 1, v13);
      v29 = Destination;
      if ( pszPath )
        v29 = (wchar_t *)pszPath;
      wcscat_s(v29, v62 >> 1, Source);
    }
    if ( v61 >= 2 )
    {
      v30 = Destination;
      if ( pszPath )
        v30 = pszPath;
      LatestVersionWithCallback = RuntimeRequest::CopyString(v18, this + 4, v30, 1);
      if ( LatestVersionWithCallback < 0 )
        goto LABEL_18;
    }
    CQuickArray<unsigned short>::~CQuickArray<unsigned short>(&pszPath);
    CQuickArray<unsigned short>::~CQuickArray<unsigned short>(&lpFilename);
  }
  v31 = 0;
  if ( *((_DWORD *)this + 16) )
  {
    v31 = g_PreferredVersion;
    if ( g_PreferredVersion )
    {
      if ( !this[3] )
      {
        v4 = (unsigned __int16 **)(this + 4);
        if ( !this[4] )
        {
          v6 = (const unsigned __int16 *)*((_QWORD *)g_PreferredVersion + 3);
          if ( v6 )
          {
            v4 = (unsigned __int16 **)(this + 3);
          }
          else
          {
            v6 = (const unsigned __int16 *)*((_QWORD *)g_PreferredVersion + 4);
            if ( !v6 )
              goto LABEL_73;
          }
          result = RuntimeRequest::CopyString(v5, (const unsigned __int16 **)v4, v6, 1);
          LatestVersionWithCallback = result;
          if ( result < 0 )
            return result;
        }
      }
    }
  }
LABEL_73:
  if ( (unsigned int)GetConfigDWORD(v5, v4, v6, *((unsigned int *)this + 27)) )
  {
    *(_QWORD *)Source = 0;
    LatestVersionWithCallback = FindLatestVersionWithCallback(Source, *((unsigned int *)this + 27), 0, 0, 0, 1, v3);
    if ( LatestVersionWithCallback >= 0 )
    {
      v32 = *(unsigned __int16 **)Source;
      if ( *this )
        operator delete((void *)*this);
      *this = v32;
      LatestVersionWithCallback = 0;
    }
    v33 = 64;
LABEL_79:
    ShimLog::Log(v3, v33, *this);
    goto LABEL_125;
  }
  RuntimeRequest::GetRuntimeVersion((RuntimeRequest *)this);
  if ( *((_DWORD *)this + 26) )
  {
    ShimLog::Log(v3, 0x33u);
    *((_DWORD *)this + 14) = 0;
    *(_QWORD *)Source = 0;
    if ( (unsigned int)RuntimeRequest::FindSupportedInstalledRuntime(
                         (RuntimeRequest *)this,
                         (unsigned __int16 **)Source) )
    {
      v35 = *(unsigned __int16 **)Source;
      if ( *this )
        operator delete((void *)*this);
      *this = v35;
      LatestVersionWithCallback = 0;
      ShimLog::Log(v3, 0x34u, v35);
    }
    else
    {
      ShimLog::Log(v3, 0x35u);
    }
  }
  else if ( *this )
  {
    ShimLog::Log(v3, 0x36u);
    result = RuntimeRequest::VerifyRuntimeVersionToLoad((unsigned __int16 **)this);
    LatestVersionWithCallback = result;
    if ( result < 0 )
      return result;
    *(_QWORD *)Source = 0;
    if ( (int)FindStandardVersion(*this, *((unsigned int *)this + 27), Source) >= 0 )
    {
      v36 = *(unsigned __int16 **)Source;
      if ( *(_QWORD *)Source )
      {
        if ( *this )
          operator delete((void *)*this);
        *this = v36;
        LatestVersionWithCallback = 0;
        ShimLog::Log(v3, 0x37u, v36);
      }
    }
  }
  else
  {
    ConfigString = (unsigned __int16 *)GetConfigString(L"Version", 0, *((unsigned int *)this + 27));
    v38 = (unsigned __int16 *)*this;
    if ( *this )
      operator delete(v38);
    *this = ConfigString;
    if ( ConfigString )
    {
      result = RuntimeRequest::VerifyRuntimeVersionToLoad((unsigned __int16 **)this);
      LatestVersionWithCallback = result;
      if ( result < 0 )
        return result;
      v33 = 56;
      goto LABEL_79;
    }
    v39 = this[1];
    if ( v39 )
    {
      result = RuntimeRequest::CopyString((RuntimeRequest *)v38, this, v39, 1);
      if ( result < 0 )
        return result;
      result = RuntimeRequest::VerifyRuntimeVersionToLoad((unsigned __int16 **)this);
      LatestVersionWithCallback = result;
      if ( result < 0 )
        return result;
      v33 = 57;
      goto LABEL_79;
    }
    if ( v31 )
    {
      v40 = (const unsigned __int16 *)*((_QWORD *)v31 + 1);
      if ( v40 )
      {
        result = RuntimeRequest::CopyString((RuntimeRequest *)v38, this, v40, 1);
        if ( result < 0 )
          return result;
        result = RuntimeRequest::VerifyRuntimeVersionToLoad((unsigned __int16 **)this);
        LatestVersionWithCallback = result;
        if ( result < 0 )
          return result;
        v33 = 58;
        goto LABEL_79;
      }
    }
    LatestVersionWithCallback = 0;
    v41 = (unsigned __int16 *)this[2];
    if ( v41 )
    {
      *(_DWORD *)Source = 0;
      if ( (unsigned int)GetFileVersion_0(v41, 0, 0, Source) == -2147024774 )
      {
        v42 = 2LL * *(unsigned int *)Source;
        v43 = v42 + 15;
        if ( v42 + 15 < v42 )
          v43 = 0xFFFFFFFFFFFFFF0LL;
        v44 = v43 & 0xFFFFFFFFFFFFFFF0uLL;
        v45 = alloca(v44);
        v46 = alloca(v44);
        if ( (int)GetFileVersion_0(v41, v59, *(unsigned int *)Source, Source) >= 0 )
        {
          result = RuntimeRequest::CopyString(v34, this, v59, 1);
          LatestVersionWithCallback = result;
          if ( result < 0 )
            return result;
          ShimLog::Log(v3, 0x3Bu, v41, *this);
        }
      }
    }
    else
    {
      ModuleHandleW = (unsigned __int8 *)GetModuleHandleW(0);
      PERuntimeVersion = GetPERuntimeVersion(ModuleHandleW, 0, 1);
      if ( PERuntimeVersion )
      {
        if ( *this )
          operator delete((void *)*this);
        *this = PERuntimeVersion;
        ShimLog::Log(v3, 0x3Cu, PERuntimeVersion);
      }
    }
    if ( *this )
    {
      result = RuntimeRequest::VerifyRuntimeVersionToLoad((unsigned __int16 **)this);
      LatestVersionWithCallback = result;
      if ( result < 0 )
        return result;
      *(_QWORD *)Source = 0;
      if ( (int)FindStandardVersion(*this, *((unsigned int *)this + 27), Source) >= 0 )
      {
        v49 = *(unsigned __int16 **)Source;
        if ( *this )
          operator delete((void *)*this);
        *this = v49;
        LatestVersionWithCallback = 0;
        ShimLog::Log(v3, 0x3Du, v49);
      }
      *((_DWORD *)this + 17) = 1;
    }
  }
LABEL_125:
  if ( *((_DWORD *)this + 17) )
  {
    if ( (unsigned int)IsRuntimeVersionInstalled(*this, *((unsigned int *)this + 27), *((unsigned int *)this + 18)) )
    {
      *(_QWORD *)Source = 0;
      if ( (int)FindVersionUsingUpgradePolicy(*this, *((unsigned int *)this + 27), Source, v3) >= 0 )
      {
        v50 = *(unsigned __int16 **)Source;
        if ( *(_QWORD *)Source )
        {
          ShimLog::Log(v3, 0x3Eu, *this, *(_QWORD *)Source);
          v34 = (RuntimeRequest *)*this;
          if ( *this )
            operator delete(v34);
          *this = v50;
          LatestVersionWithCallback = 0;
        }
      }
    }
  }
  if ( this[5]
    || !v31
    || (v51 = (const unsigned __int16 *)*((_QWORD *)v31 + 5)) == 0
    || (result = RuntimeRequest::CopyString(v34, this + 5, v51, 1), LatestVersionWithCallback = result, result >= 0) )
  {
    v52 = (void **)(this + 10);
    if ( this[10] )
      goto LABEL_145;
    v53 = GetConfigString(L"BuildFlavor", 0, *((unsigned int *)this + 27));
    v54 = *v52;
    if ( *v52 )
      operator delete(v54);
    *v52 = (void *)v53;
    LatestVersionWithCallback = 0;
    if ( v53
      || !v31
      || (v55 = (const unsigned __int16 *)*((_QWORD *)v31 + 10)) == 0
      || (result = RuntimeRequest::CopyString((RuntimeRequest *)v54, this + 10, v55, 1),
          LatestVersionWithCallback = result,
          result >= 0) )
    {
      if ( *v52 )
        ShimLog::Log(v3, 0x3Fu);
LABEL_145:
      if ( !*this && *((_DWORD *)this + 14) )
      {
        *(_QWORD *)Source = 0;
        if ( !(unsigned int)CheckAppDatabase(this[2], *((unsigned int *)this + 27), Source) )
        {
          v56 = *(unsigned __int16 **)Source;
          if ( *this )
            operator delete((void *)*this);
          *this = v56;
          LatestVersionWithCallback = 0;
          ShimLog::Log(v3, 0x40u, v56);
          goto LABEL_157;
        }
        *(_QWORD *)Source = 0;
        LatestVersionWithCallback = FindLatestVersionWithCallback(
                                      Source,
                                      *((unsigned int *)this + 27),
                                      *((_DWORD *)this + 15) == 0,
                                      0,
                                      0,
                                      1,
                                      v3);
        if ( LatestVersionWithCallback >= 0 )
        {
          v57 = *(unsigned __int16 **)Source;
          if ( *this )
            operator delete((void *)*this);
          *this = v57;
          LatestVersionWithCallback = 0;
        }
        ShimLog::Log(v3, 0x40u, *this);
      }
      if ( LatestVersionWithCallback < 0 )
      {
LABEL_162:
        ShimLog::LogNewline(v3);
        ShimLog::LogNewline(v3);
        if ( *this )
          ShimLog::Log(v3, 0x42u);
        else
          ShimLog::Log(v3, 0x41u);
        return RuntimeRequest::NoSupportedVersion((RuntimeRequest *)this, *(int *)v59);
      }
LABEL_157:
      if ( *this
        && !(unsigned int)IsRuntimeVersionInstalled(*this, *((unsigned int *)this + 27), *((unsigned int *)this + 18)) )
      {
        ShimLog::LogNewline(v3);
        ShimLog::LogNewline(v3);
        ShimLog::Log(v3, 0x43u, *this);
        v58 = (unsigned __int16 *)this[16];
        if ( v58 != (unsigned __int16 *)-1LL )
          CloseHandle(v58);
        this[16] = (const unsigned __int16 *)-1LL;
        return LatestVersionWithCallback;
      }
      goto LABEL_162;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009af4  push    rbp
0x180009af6  push    rbx
0x180009af7  push    rsi
0x180009af8  push    rdi
0x180009af9  push    r12
0x180009afb  push    r13
0x180009afd  push    r14
0x180009aff  push    r15
0x180009b01  sub     rsp, 6D8h
0x180009b08  lea     rbp, [rsp+40h]
0x180009b0d  mov     rax, cs:__security_cookie
0x180009b14  xor     rax, rbp
0x180009b17  mov     [rbp+6D0h+var_50], rax
0x180009b1e  mov     dword ptr [rbp+6D0h+var_6D0], edx
0x180009b21  mov     rbx, rcx
0x180009b24  lea     rsi, [rcx+70h]
0x180009b28  mov     rcx, rsi; this
0x180009b2b  call    ?StartLog@ShimLog@@QEAAXXZ; ShimLog::StartLog(void)
0x180009b30  mov     rcx, rbx; this
0x180009b33  call    ?LogStartValues@RuntimeRequest@@QEAAXXZ; RuntimeRequest::LogStartValues(void)
0x180009b38  call    UseLocalRuntime
0x180009b3d  xor     r13d, r13d
0x180009b40  test    eax, eax
0x180009b42  jz      short loc_180009B7E
0x180009b44  lea     edx, [r13+32h]; unsigned int
0x180009b48  mov     rcx, rsi; this
0x180009b4b  call    ?Log@ShimLog@@QEAAXIZZ; ShimLog::Log(uint,...)
0x180009b50  lea     r14d, [r13+1]
0x180009b54  mov     r9d, r14d; int
0x180009b57  lea     r8, word_180050144; unsigned __int16 *
0x180009b5e  mov     rdx, rbx; unsigned __int16 **
0x180009b61  call    ?CopyString@RuntimeRequest@@AEAAJPEAPEBGPEBGH@Z; RuntimeRequest::CopyString(ushort const * *,ushort const *,int)
0x180009b66  test    eax, eax
0x180009b68  js      loc_18000A572
0x180009b6e  mov     [rbx+30h], r14d
0x180009b72  mov     [rbx+34h], r14d
0x180009b76  mov     eax, r14d
0x180009b79  jmp     loc_18000A572
0x180009b7e  mov     edi, r13d
0x180009b81  lea     r15, [rbx+10h]
0x180009b85  mov     eax, 200h
0x180009b8a  mov     r14d, 1
0x180009b90  cmp     [r15], r13
0x180009b93  jnz     loc_180009C31
0x180009b99  mov     [rbp+6D0h+lpFilename], r13
0x180009ba0  mov     [rbp+6D0h+var_498], r13
0x180009ba7  mov     [rbp+6D0h+var_490], rax
0x180009bae  mov     edx, 10Dh
0x180009bb3  lea     rcx, [rbp+6D0h+lpFilename]
0x180009bba  call    ?ReSizeNoThrow@?$CQuickArrayBase@G@@QEAAJ_K@Z; CQuickArrayBase<ushort>::ReSizeNoThrow(unsigned __int64)
0x180009bbf  mov     edi, eax
0x180009bc1  test    eax, eax
0x180009bc3  jns     short loc_180009BD8
0x180009bc5  lea     rcx, [rbp+6D0h+lpFilename]
0x180009bcc  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x180009bd1  mov     eax, edi
0x180009bd3  jmp     loc_18000A572
0x180009bd8  mov     r8, [rbp+6D0h+var_490]
0x180009bdf  shr     r8, 1; nSize
0x180009be2  lea     rdx, [rbp+6D0h+var_488]
0x180009be9  mov     rax, [rbp+6D0h+lpFilename]
0x180009bf0  test    rax, rax
0x180009bf3  cmovnz  rdx, rax; lpFilename
0x180009bf7  xor     ecx, ecx; hModule
0x180009bf9  call    cs:__imp_GetModuleFileNameW
0x180009bff  lea     r8, [rbp+6D0h+var_488]
0x180009c06  mov     rax, [rbp+6D0h+lpFilename]
0x180009c0d  test    rax, rax
0x180009c10  cmovnz  r8, rax; unsigned __int16 *
0x180009c14  mov     r9d, r14d; int
0x180009c17  mov     rdx, r15; unsigned __int16 **
0x180009c1a  call    ?CopyString@RuntimeRequest@@AEAAJPEAPEBGPEBGH@Z; RuntimeRequest::CopyString(ushort const * *,ushort const *,int)
0x180009c1f  nop
0x180009c20  lea     rcx, [rbp+6D0h+lpFilename]
0x180009c27  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x180009c2c  mov     eax, 200h
0x180009c31  lea     r12, [rbx+18h]
0x180009c35  cmp     [r12], r13
0x180009c39  jnz     loc_180009F5D
0x180009c3f  cmp     qword ptr [rbx+20h], 0
0x180009c44  jnz     loc_180009F5A
0x180009c4a  xor     edi, edi
0x180009c4c  mov     qword ptr [rbp+6D0h+Source], rdi
0x180009c53  mov     r15, [r15]
0x180009c56  mov     [rbp+6D0h+lpFilename], rdi
0x180009c5d  mov     [rbp+6D0h+var_498], rdi
0x180009c64  mov     [rbp+6D0h+var_490], rax
0x180009c6b  mov     [rbp+6D0h+pszPath], rdi
0x180009c6f  mov     [rbp+6D0h+var_6B8], rdi
0x180009c73  mov     [rbp+6D0h+var_6B0], rax
0x180009c77  lea     r8, [rbp+6D0h+Source]; unsigned __int64 *
0x180009c7e  mov     edx, 100h; unsigned __int64
0x180009c83  lea     rcx, [rbp+6D0h+Destination]; Destination
0x180009c87  call    ?GetConfigFileFromWin32Manifest@@YAJPEAG_KPEA_K@Z; GetConfigFileFromWin32Manifest(ushort *,unsigned __int64,unsigned __int64 *)
0x180009c8c  test    eax, eax
0x180009c8e  jns     short loc_180009CEC
0x180009c90  cmp     eax, 8007007Ah
0x180009c95  jnz     loc_180009E9B
0x180009c9b  mov     rdx, qword ptr [rbp+6D0h+Source]
0x180009ca2  lea     rcx, [rbp+6D0h+pszPath]
0x180009ca6  call    ?ReSizeNoThrow@?$CQuickArrayBase@G@@QEAAJ_K@Z; CQuickArrayBase<ushort>::ReSizeNoThrow(unsigned __int64)
0x180009cab  mov     edi, eax
0x180009cad  test    eax, eax
0x180009caf  jns     short loc_180009CC0
0x180009cb1  lea     rcx, [rbp+6D0h+pszPath]
0x180009cb5  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x180009cba  nop
0x180009cbb  jmp     loc_180009BC5
0x180009cc0  mov     rdx, [rbp+6D0h+var_6B0]
0x180009cc4  shr     rdx, 1; unsigned __int64
0x180009cc7  lea     rcx, [rbp+6D0h+Destination]
0x180009ccb  mov     rax, [rbp+6D0h+pszPath]
0x180009ccf  xor     edi, edi
0x180009cd1  test    rax, rax
0x180009cd4  cmovnz  rcx, rax; Destination
0x180009cd8  lea     r8, [rbp+6D0h+Source]; unsigned __int64 *
0x180009cdf  call    ?GetConfigFileFromWin32Manifest@@YAJPEAG_KPEA_K@Z; GetConfigFileFromWin32Manifest(ushort *,unsigned __int64,unsigned __int64 *)
0x180009ce4  test    eax, eax
0x180009ce6  js      loc_180009E9B
0x180009cec  mov     rdx, [rbp+6D0h+var_490]
0x180009cf3  shr     rdx, 1; SizeInWords
0x180009cf6  lea     rcx, [rbp+6D0h+var_488]
0x180009cfd  mov     rax, [rbp+6D0h+lpFilename]
0x180009d04  test    rax, rax
0x180009d07  cmovnz  rcx, rax; Destination
0x180009d0b  lea     r8, [rbp+6D0h+Source]; unsigned __int64 *
0x180009d12  call    ?GetApplicationPathFromWin32Manifest@@YAJPEAG_KPEA_K@Z; GetApplicationPathFromWin32Manifest(ushort *,unsigned __int64,unsigned __int64 *)
0x180009d17  mov     edi, eax
0x180009d19  test    eax, eax
0x180009d1b  jns     short loc_180009D7A
0x180009d1d  cmp     eax, 8007007Ah
0x180009d22  jnz     loc_180009E99
0x180009d28  mov     rdx, qword ptr [rbp+6D0h+Source]
0x180009d2f  lea     rcx, [rbp+6D0h+lpFilename]
0x180009d36  call    ?ReSizeNoThrow@?$CQuickArrayBase@G@@QEAAJ_K@Z; CQuickArrayBase<ushort>::ReSizeNoThrow(unsigned __int64)
0x180009d3b  mov     edi, eax
0x180009d3d  test    eax, eax
0x180009d3f  js      loc_180009CB1
0x180009d45  mov     rdx, [rbp+6D0h+var_490]
0x180009d4c  shr     rdx, 1; SizeInWords
0x180009d4f  lea     rcx, [rbp+6D0h+var_488]
0x180009d56  mov     rax, [rbp+6D0h+lpFilename]
0x180009d5d  test    rax, rax
0x180009d60  cmovnz  rcx, rax; Destination
0x180009d64  lea     r8, [rbp+6D0h+Source]; unsigned __int64 *
0x180009d6b  call    ?GetApplicationPathFromWin32Manifest@@YAJPEAG_KPEA_K@Z; GetApplicationPathFromWin32Manifest(ushort *,unsigned __int64,unsigned __int64 *)
0x180009d70  mov     edi, eax
0x180009d72  test    eax, eax
0x180009d74  js      loc_180009E99
0x180009d7a  cmp     [rbp+6D0h+var_6B8], 2
0x180009d7f  jb      loc_180009E99
0x180009d85  cmp     [rbp+6D0h+var_498], 2
0x180009d8d  jb      loc_180009F0F
0x180009d93  lea     rcx, [rbp+6D0h+Destination]
0x180009d97  mov     rax, [rbp+6D0h+pszPath]
0x180009d9b  xor     r15d, r15d
0x180009d9e  test    rax, rax
0x180009da1  cmovnz  rcx, rax; pszPath
0x180009da5  call    cs:__imp_PathIsRelativeW
0x180009dab  test    eax, eax
0x180009dad  jz      loc_180009F0F
0x180009db3  mov     [rbp+6D0h+pszDest], r15
0x180009dba  mov     [rbp+6D0h+var_278], r15
0x180009dc1  mov     [rbp+6D0h+var_270], 200h
0x180009dcc  mov     rdx, [rbp+6D0h+var_6B8]
0x180009dd0  shr     rdx, 1
0x180009dd3  mov     rax, [rbp+6D0h+var_498]
0x180009dda  shr     rax, 1
0x180009ddd  add     rdx, rax
0x180009de0  lea     rcx, [rbp+6D0h+pszDest]
0x180009de7  call    ?ReSizeNoThrow@?$CQuickArrayBase@G@@QEAAJ_K@Z; CQuickArrayBase<ushort>::ReSizeNoThrow(unsigned __int64)
0x180009dec  mov     edi, eax
0x180009dee  test    eax, eax
0x180009df0  jns     short loc_180009E03
0x180009df2  lea     rcx, [rbp+6D0h+pszDest]
0x180009df9  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x180009dfe  jmp     loc_180009CB1
0x180009e03  lea     r8, [rbp+6D0h+Destination]
0x180009e07  mov     rax, [rbp+6D0h+pszPath]
0x180009e0b  test    rax, rax
0x180009e0e  cmovnz  r8, rax; pszFile
0x180009e12  lea     rdx, [rbp+6D0h+var_488]
0x180009e19  mov     rax, [rbp+6D0h+lpFilename]
0x180009e20  test    rax, rax
0x180009e23  cmovnz  rdx, rax; pszDir
0x180009e27  lea     rcx, [rbp+6D0h+var_268]
0x180009e2e  mov     rax, [rbp+6D0h+pszDest]
0x180009e35  test    rax, rax
0x180009e38  cmovnz  rcx, rax; pszDest
0x180009e3c  call    cs:__imp_PathCombineW
0x180009e42  mov     r15, rax
0x180009e45  xor     eax, eax
0x180009e47  test    r15, r15
0x180009e4a  jz      short loc_180009E8B
0x180009e4c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009e50  inc     rdx
0x180009e53  cmp     [r15+rdx*2], ax
0x180009e58  jnz     short loc_180009E50
0x180009e5a  inc     rdx
0x180009e5d  lea     rcx, [rbp+6D0h+pszPath]
0x180009e61  call    ?ReSizeNoThrow@?$CQuickArrayBase@G@@QEAAJ_K@Z; CQuickArrayBase<ushort>::ReSizeNoThrow(unsigned __int64)
0x180009e66  mov     edi, eax
0x180009e68  test    eax, eax
0x180009e6a  js      short loc_180009DF2
0x180009e6c  mov     rdx, [rbp+6D0h+var_6B0]
0x180009e70  shr     rdx, 1; SizeInWords
0x180009e73  lea     rcx, [rbp+6D0h+Destination]
0x180009e77  mov     rax, [rbp+6D0h+pszPath]
0x180009e7b  test    rax, rax
0x180009e7e  cmovnz  rcx, rax; Destination
0x180009e82  mov     r8, r15; Source
0x180009e85  call    wcscpy_s
0x180009e8a  nop
0x180009e8b  lea     rcx, [rbp+6D0h+pszDest]
0x180009e92  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x180009e97  jmp     short loc_180009F0F
0x180009e99  xor     edi, edi
0x180009e9b  movups  xmm0, xmmword ptr cs:aConfig; ".config"
0x180009ea2  movdqu  xmmword ptr [rbp+6D0h+Source], xmm0
0x180009eaa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009eae  inc     rdx
0x180009eb1  cmp     [r15+rdx*2], di
0x180009eb6  jnz     short loc_180009EAE
0x180009eb8  add     rdx, 8
0x180009ebc  lea     rcx, [rbp+6D0h+pszPath]
0x180009ec0  call    ?ReSizeNoThrow@?$CQuickArrayBase@G@@QEAAJ_K@Z; CQuickArrayBase<ushort>::ReSizeNoThrow(unsigned __int64)
0x180009ec5  mov     edi, eax
0x180009ec7  test    eax, eax
0x180009ec9  js      loc_180009CB1
0x180009ecf  mov     rdx, [rbp+6D0h+var_6B0]
0x180009ed3  shr     rdx, 1; SizeInWords
0x180009ed6  lea     rcx, [rbp+6D0h+Destination]
0x180009eda  mov     rax, [rbp+6D0h+pszPath]
0x180009ede  test    rax, rax
0x180009ee1  cmovnz  rcx, rax; Destination
0x180009ee5  mov     r8, r15; Source
0x180009ee8  call    wcscpy_s
0x180009eed  mov     rdx, [rbp+6D0h+var_6B0]
0x180009ef1  shr     rdx, 1; SizeInWords
0x180009ef4  lea     rcx, [rbp+6D0h+Destination]
0x180009ef8  mov     rax, [rbp+6D0h+pszPath]
0x180009efc  test    rax, rax
0x180009eff  cmovnz  rcx, rax; Destination
0x180009f03  lea     r8, [rbp+6D0h+Source]; Source
0x180009f0a  call    wcscat_s
0x180009f0f  cmp     [rbp+6D0h+var_6B8], 2
0x180009f14  jb      short loc_180009F3F
0x180009f16  lea     r8, [rbp+6D0h+Destination]
0x180009f1a  mov     rax, [rbp+6D0h+pszPath]
0x180009f1e  test    rax, rax
0x180009f21  cmovnz  r8, rax; unsigned __int16 *
0x180009f25  mov     r9d, r14d; int
0x180009f28  lea     rdx, [rbx+20h]; unsigned __int16 **
0x180009f2c  call    ?CopyString@RuntimeRequest@@AEAAJPEAPEBGPEBGH@Z; RuntimeRequest::CopyString(ushort const * *,ushort const *,int)
0x180009f31  mov     edi, eax
0x180009f33  xor     r13d, r13d
0x180009f36  test    eax, eax
0x180009f38  jns     short loc_180009F42
0x180009f3a  jmp     loc_180009CB1
0x180009f3f  xor     r13d, r13d
0x180009f42  lea     rcx, [rbp+6D0h+pszPath]
0x180009f46  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x180009f4b  nop
0x180009f4c  lea     rcx, [rbp+6D0h+lpFilename]
0x180009f53  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x180009f58  jmp     short loc_180009F5D
0x180009f5a  xor     r13d, r13d
0x180009f5d  mov     r15, r13
0x180009f60  cmp     [rbx+40h], r13d
0x180009f64  jz      short loc_180009FA9
0x180009f66  mov     r15, cs:?g_PreferredVersion@@3PEAVRuntimeRequest@@EA; RuntimeRequest * g_PreferredVersion
0x180009f6d  test    r15, r15
0x180009f70  jz      short loc_180009FA9
0x180009f72  cmp     [r12], r13
0x180009f76  jnz     short loc_180009FA9
0x180009f78  lea     rdx, [rbx+20h]
0x180009f7c  cmp     [rdx], r13
0x180009f7f  jnz     short loc_180009FA9
0x180009f81  mov     r8, [r15+18h]; unsigned __int16 *
0x180009f85  test    r8, r8
0x180009f88  jz      short loc_180009FA0
0x180009f8a  mov     rdx, r12; unsigned __int16 **
0x180009f8d  mov     r9d, r14d; int
0x180009f90  call    ?CopyString@RuntimeRequest@@AEAAJPEAPEBGPEBGH@Z; RuntimeRequest::CopyString(ushort const * *,ushort const *,int)
0x180009f95  test    eax, eax
0x180009f97  mov     edi, eax
0x180009f99  jns     short loc_180009FA9
0x180009f9b  jmp     loc_18000A572
0x180009fa0  mov     r8, [r15+20h]
0x180009fa4  test    r8, r8
0x180009fa7  jnz     short loc_180009F8D
0x180009fa9  mov     r9d, [rbx+6Ch]
0x180009fad  call    ?GetConfigDWORD@@YAKPEBGKHW4VERSION_ARCHITECTURE@@@Z; GetConfigDWORD(ushort const *,ulong,int,VERSION_ARCHITECTURE)
0x180009fb2  test    eax, eax
0x180009fb4  jz      short loc_18000A016
0x180009fb6  mov     qword ptr [rbp+6D0h+Source], r13
0x180009fbd  mov     [rsp+710h+var_6E0], rsi
0x180009fc2  mov     [rsp+710h+var_6E8], r14d
0x180009fc7  mov     [rsp+710h+var_6F0], r13
0x180009fcc  xor     r9d, r9d
  ... truncated ...
```
