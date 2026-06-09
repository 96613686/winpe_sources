# CDeploymentSessionWrapper::PostDownload(ushort const *,ushort const *,ushort const *)

- ea: `0x18029994c`
- end: `0x180299ebb`
- name: `?PostDownload@CDeploymentSessionWrapper@@QEAAJPEBG00@Z`
- size: `1391`
- prototype: `__int64 __fastcall(CDeploymentSessionWrapper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `15`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180299ed0`
- `0x180299fb0`

## callees

- `0x18003f44c`
- `0x18003f950`
- `0x1800d986c`
- `0x1800eb920`
- `0x1800ec920`
- `0x1801f15e4`
- `0x1801f17f8`
- `0x180296168`
- `0x180297084`
- `0x180298470`
- `0x1802989d8`
- `0x180299100`
- `0x18029994c`
- `0x18029a67c`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180299c85`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180299c85`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180299c33`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180299c33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180299c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180299c99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180299c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180299c99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180299b02`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180299b02`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180299aaf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180299aaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180299b15`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180299b15`

## string_xrefs

- `0x180299b5e`: `UpdateAgent.dll`
- `0x180299c76`: `CreateOfflineDeploymentSession`
- `0x180299afb`: `AlternateServiceStackDLLPath`
- `0x180299aa1`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x180299d12`: `DeploymentSessionWrapper: Sandbox path [%s]`
- `0x180299c1a`: `DeploymentSessionWrapper: Loading Update Agent from [%s]`
- `0x180299de4`: `DeploymentSessionWrapper: This version of UpdateAgent doesn't support Recovery on UUP.`

## pseudocode

```c
__int64 __fastcall CDeploymentSessionWrapper::PostDownload(
        CDeploymentSessionWrapper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // ebx
  int v12; // eax
  LSTATUS v13; // ebx
  const WCHAR *v14; // rbx
  int FinalPath; // eax
  const WCHAR *v16; // rsi
  HMODULE Library; // rbx
  DWORD LastError; // eax
  FARPROC ProcAddress; // rbx
  DWORD v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  HMODULE v26; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v27[2]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v29; // [rsp+80h] [rbp-80h]
  __int128 v30; // [rsp+90h] [rbp-70h]
  __int128 v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+B0h] [rbp-50h]
  DWORD Type; // [rsp+B8h] [rbp-48h] BYREF
  LPCWSTR lpLibFileName; // [rsp+C0h] [rbp-40h] BYREF
  DWORD cbData[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v36; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v37; // [rsp+D8h] [rbp-28h]
  BYTE Data[1024]; // [rsp+E0h] [rbp-20h] BYREF

  v27[0] = 0;
  lpLibFileName = 0;
  v26 = 0;
  v37 = 0;
  v36 = 0;
  v32 = 0;
  Type = 0;
  v25 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  if ( !a2 )
  {
    v8 = 282;
LABEL_3:
    v9 = *(_QWORD *)this;
    v10 = 2147942487LL;
    v11 = -2147024809;
LABEL_62:
    CFCLogLiteT<CEmptyType>::LogError(v9, v10, L"CDeploymentSessionWrapper::PostDownload", v8);
    goto LABEL_63;
  }
  if ( !a4 )
  {
    v8 = 283;
    goto LABEL_3;
  }
  v12 = CMiscHelpersT<CEmptyType>::DirectoryExists(a4, &Type);
  v11 = v12;
  if ( v12 < 0 )
  {
    v8 = 287;
LABEL_60:
    v10 = (unsigned int)v12;
    goto LABEL_61;
  }
  if ( !Type )
  {
    v10 = 2147942403LL;
    v8 = 288;
    v11 = -2147024893;
LABEL_61:
    v9 = *(_QWORD *)this;
    goto LABEL_62;
  }
  v12 = CMiscHelpersT<CEmptyType>::CombinePath(a4, L"metadata", 0, v27);
  v11 = v12;
  if ( v12 < 0 )
  {
    v8 = 292;
    goto LABEL_60;
  }
  v12 = CMiscHelpersT<CEmptyType>::DirectoryExists(v27[0], &Type);
  v11 = v12;
  if ( v12 < 0 )
  {
    v8 = 293;
    goto LABEL_60;
  }
  if ( !Type )
  {
    v10 = 2147942403LL;
    v8 = 294;
    v11 = -2147024893;
    goto LABEL_61;
  }
  SH<unsigned short *,SH_SSTRING>::Reset(&lpLibFileName);
  if ( !a3 )
  {
    hKey[0] = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
            0,
            0x20019u,
            hKey) )
    {
      Type = 0;
      memset_0(Data, 0, sizeof(Data));
      cbData[0] = 1024;
      v13 = RegQueryValueExW(hKey[0], L"AlternateServiceStackDLLPath", 0, &Type, Data, cbData);
      RegCloseKey(hKey[0]);
      if ( !v13 && Type == 1 )
      {
        v12 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(Data);
        v11 = v12;
        if ( v12 < 0 )
        {
          v8 = 315;
          goto LABEL_60;
        }
      }
    }
  }
  v14 = lpLibFileName;
  if ( !lpLibFileName )
  {
    v12 = CMiscHelpersT<CEmptyType>::CombinePath(v27[0], L"UpdateAgent.dll", 0, &lpLibFileName);
    v11 = v12;
    if ( v12 < 0 )
    {
      v8 = 324;
      goto LABEL_60;
    }
    v14 = lpLibFileName;
  }
  lpLibFileName = 0;
  *(_QWORD *)cbData = 0;
  SH<unsigned short *,SH_SSTRING>::Reset(cbData);
  *(_QWORD *)cbData = v14;
  FinalPath = CMiscHelpersT<CEmptyType>::GetFinalPath(v14);
  v11 = FinalPath;
  if ( FinalPath < 0 )
  {
    CFCLogLiteT<CEmptyType>::LogError(
      *(_QWORD *)this,
      (unsigned int)FinalPath,
      L"CDeploymentSessionWrapper::PostDownload",
      331);
    SH<unsigned short *,SH_SSTRING>::Reset(cbData);
    goto LABEL_63;
  }
  SH<unsigned short *,SH_SSTRING>::Reset(cbData);
  v16 = lpLibFileName;
  v12 = CMiscHelpersT<CEmptyType>::FileExists(lpLibFileName, &v25);
  v11 = v12;
  if ( v12 < 0 )
  {
    v8 = 333;
    goto LABEL_60;
  }
  v9 = *(_QWORD *)this;
  if ( !v25 )
  {
    v11 = -2147024894;
    v8 = 334;
    v10 = 2147942402LL;
    goto LABEL_62;
  }
  if ( v9 )
    CFCLogLiteT<CEmptyType>::LogFormat(v9, 2, L"DeploymentSessionWrapper: Loading Update Agent from [%s]", v16);
  Library = LoadLibraryExW(v16, 0, 0);
  SH<HINSTANCE__ *,SH_HMODULE>::Reset(&v26);
  if ( !Library )
  {
    v26 = 0;
    LastError = GetLastError();
    v12 = SErrorConverter::C_LR2HR(LastError);
    v11 = v12;
    v8 = 338;
    goto LABEL_60;
  }
  v26 = Library;
  ProcAddress = GetProcAddress(Library, "CreateOfflineDeploymentSession");
  if ( !ProcAddress )
  {
    v20 = GetLastError();
    v12 = SErrorConverter::C_LR2HR(v20);
    v11 = v12;
    v8 = 341;
    goto LABEL_60;
  }
  v21 = *(_QWORD *)this;
  v32 = 0;
  v29 = (unsigned __int64)a2;
  v30 = 0;
  v31 = 0;
  if ( v21 )
    CFCLogLiteT<CEmptyType>::LogFormat(v21, 2, L"DeploymentSessionWrapper: Creating Deployment Session object");
  if ( *(_QWORD *)this )
    CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Session Version [%d]", 1);
  if ( *(_QWORD *)this )
    CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Sandbox path [%s]", a4);
  if ( *(_QWORD *)this )
    CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Offline windir [%s]", a3);
  if ( *(_QWORD *)this )
    CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Info2version [%d]", 2);
  if ( *(_QWORD *)this )
    CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Session data [%s]", (_QWORD)v29);
  *(GUID *)hKey = GUID_NULL;
  v12 = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, const unsigned __int16 *))ProcAddress)(1, a4, a3);
  v11 = v12;
  if ( v12 < 0 )
  {
    v8 = 362;
    goto LABEL_60;
  }
  v22 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v37)(
          v37,
          &GUID_36fb071a_6dc5_48bf_a6f3_d4f6751d39dc,
          &v36);
  v23 = *(_QWORD *)this;
  v11 = v22;
  if ( v22 < 0 )
  {
    if ( v23 )
      CFCLogLiteT<CEmptyType>::LogFormat(
        v23,
        4,
        L"DeploymentSessionWrapper: This version of UpdateAgent doesn't support Recovery on UUP.");
    v8 = 369;
    v10 = v11;
    goto LABEL_61;
  }
  if ( v23 )
    CFCLogLiteT<CEmptyType>::LogFormat(
      v23,
      2,
      L"DeploymentSessionWrapper: Calling PostDownload on Deployment Session object, to perform expand.");
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 88LL))(v36);
  v11 = v12;
  if ( v12 < 0 )
  {
    v8 = 372;
    goto LABEL_60;
  }
LABEL_63:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  SH<HINSTANCE__ *,SH_HMODULE>::Reset(&v26);
  SH<unsigned short *,SH_SSTRING>::Reset(&lpLibFileName);
  SH<unsigned short *,SH_SSTRING>::Reset(v27);
  return v11;
}

```

## disassembly

```asm
0x18029994c  push    rbp
0x18029994e  push    rbx
0x18029994f  push    rsi
0x180299950  push    rdi
0x180299951  push    r12
0x180299953  push    r13
0x180299955  push    r14
0x180299957  push    r15
0x180299959  lea     rbp, [rsp-3F8h]
0x180299961  sub     rsp, 4F8h
0x180299968  mov     rax, cs:__security_cookie
0x18029996f  xor     rax, rsp
0x180299972  mov     [rbp+430h+var_50], rax
0x180299979  xor     r13d, r13d
0x18029997c  xorps   xmm0, xmm0
0x18029997f  xor     eax, eax
0x180299981  mov     [rsp+530h+var_4D0], r13
0x180299986  mov     [rbp+430h+lpLibFileName], r13
0x18029998a  mov     r14, r9
0x18029998d  mov     [rsp+530h+var_4D8], r13
0x180299992  mov     r12, r8
0x180299995  mov     [rbp+430h+var_458], r13
0x180299999  mov     r15, rdx
0x18029999c  mov     [rbp+430h+var_460], r13
0x1802999a0  mov     rdi, rcx
0x1802999a3  mov     [rbp+430h+var_480], rax
0x1802999a7  mov     [rbp+430h+Type], r13d
0x1802999ab  mov     [rsp+530h+var_4E0], r13d
0x1802999b0  movups  [rbp+430h+var_4B0], xmm0
0x1802999b4  movups  [rbp+430h+var_4A0], xmm0
0x1802999b8  movups  [rbp+430h+var_490], xmm0
0x1802999bc  test    rdx, rdx
0x1802999bf  jnz     short loc_1802999D6
0x1802999c1  mov     r9d, 11Ah
0x1802999c7  mov     rcx, [rcx]
0x1802999ca  mov     edx, 80070057h
0x1802999cf  mov     ebx, edx
0x1802999d1  jmp     loc_180299E33
0x1802999d6  test    r14, r14
0x1802999d9  jnz     short loc_1802999E3
0x1802999db  mov     r9d, 11Bh
0x1802999e1  jmp     short loc_1802999C7
0x1802999e3  lea     rdx, [rbp+430h+Type]
0x1802999e7  mov     rcx, r14
0x1802999ea  call    ?DirectoryExists@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAH@Z; CMiscHelpersT<CEmptyType>::DirectoryExists(ushort const *,int *)
0x1802999ef  mov     ebx, eax
0x1802999f1  test    eax, eax
0x1802999f3  jns     short loc_180299A00
0x1802999f5  mov     r9d, 11Fh
0x1802999fb  jmp     loc_180299E2E
0x180299a00  cmp     [rbp+430h+Type], r13d
0x180299a04  jnz     short loc_180299A18
0x180299a06  mov     edx, 80070003h
0x180299a0b  mov     r9d, 120h
0x180299a11  mov     ebx, edx
0x180299a13  jmp     loc_180299E30
0x180299a18  lea     r9, [rsp+530h+var_4D0]
0x180299a1d  xor     r8d, r8d
0x180299a20  lea     rdx, aMetadata_2; "metadata"
0x180299a27  mov     rcx, r14
0x180299a2a  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180299a2f  mov     ebx, eax
0x180299a31  test    eax, eax
0x180299a33  jns     short loc_180299A40
0x180299a35  mov     r9d, 124h
0x180299a3b  jmp     loc_180299E2E
0x180299a40  mov     rcx, [rsp+530h+var_4D0]
0x180299a45  lea     rdx, [rbp+430h+Type]
0x180299a49  call    ?DirectoryExists@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAH@Z; CMiscHelpersT<CEmptyType>::DirectoryExists(ushort const *,int *)
0x180299a4e  mov     ebx, eax
0x180299a50  test    eax, eax
0x180299a52  jns     short loc_180299A5F
0x180299a54  mov     r9d, 125h
0x180299a5a  jmp     loc_180299E2E
0x180299a5f  cmp     [rbp+430h+Type], r13d
0x180299a63  jnz     short loc_180299A77
0x180299a65  mov     edx, 80070003h
0x180299a6a  mov     r9d, 126h
0x180299a70  mov     ebx, edx
0x180299a72  jmp     loc_180299E30
0x180299a77  lea     rcx, [rbp+430h+lpLibFileName]
0x180299a7b  call    ?Reset@?$SH@PEAGVSH_SSTRING@@@@QEAAXXZ; SH<ushort *,SH_SSTRING>::Reset(void)
0x180299a80  test    r12, r12
0x180299a83  jnz     loc_180299B49
0x180299a89  lea     rax, [rsp+530h+hKey]
0x180299a8e  mov     [rsp+530h+hKey], r13
0x180299a93  mov     r9d, 20019h; samDesired
0x180299a99  mov     [rsp+530h+phkResult], rax; phkResult
0x180299a9e  xor     r8d, r8d; ulOptions
0x180299aa1  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180299aa8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180299aaf  call    cs:__imp_RegOpenKeyExW
0x180299ab6  nop     dword ptr [rax+rax+00h]
0x180299abb  test    eax, eax
0x180299abd  jnz     loc_180299B49
0x180299ac3  mov     ebx, 400h
0x180299ac8  mov     [rbp+430h+Type], r13d
0x180299acc  mov     r8d, ebx; Size
0x180299acf  lea     rcx, [rbp+430h+Data]; void *
0x180299ad3  xor     edx, edx; Val
0x180299ad5  call    memset_0
0x180299ada  mov     rcx, [rsp+530h+hKey]; hKey
0x180299adf  lea     rax, [rbp+430h+cbData]
0x180299ae3  mov     [rsp+530h+lpcbData], rax; lpcbData
0x180299ae8  lea     r9, [rbp+430h+Type]; lpType
0x180299aec  lea     rax, [rbp+430h+Data]
0x180299af0  mov     [rbp+430h+cbData], ebx
0x180299af3  xor     r8d, r8d; lpReserved
0x180299af6  mov     [rsp+530h+phkResult], rax; lpData
0x180299afb  lea     rdx, aAlternateservi; "AlternateServiceStackDLLPath"
0x180299b02  call    cs:__imp_RegQueryValueExW
0x180299b09  nop     dword ptr [rax+rax+00h]
0x180299b0e  mov     rcx, [rsp+530h+hKey]; hKey
0x180299b13  mov     ebx, eax
0x180299b15  call    cs:__imp_RegCloseKey
0x180299b1c  nop     dword ptr [rax+rax+00h]
0x180299b21  test    ebx, ebx
0x180299b23  jnz     short loc_180299B49
0x180299b25  cmp     [rbp+430h+Type], 1
0x180299b29  jnz     short loc_180299B49
0x180299b2b  lea     rdx, [rbp+430h+lpLibFileName]
0x180299b2f  lea     rcx, [rbp+430h+Data]; Src
0x180299b33  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x180299b38  mov     ebx, eax
0x180299b3a  test    eax, eax
0x180299b3c  jns     short loc_180299B49
0x180299b3e  mov     r9d, 13Bh
0x180299b44  jmp     loc_180299E2E
0x180299b49  mov     rbx, [rbp+430h+lpLibFileName]
0x180299b4d  test    rbx, rbx
0x180299b50  jnz     short loc_180299B7F
0x180299b52  mov     rcx, [rsp+530h+var_4D0]
0x180299b57  lea     r9, [rbp+430h+lpLibFileName]
0x180299b5b  xor     r8d, r8d
0x180299b5e  lea     rdx, aUpdateagentDll_1; "UpdateAgent.dll"
0x180299b65  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180299b6a  mov     ebx, eax
0x180299b6c  test    eax, eax
0x180299b6e  jns     short loc_180299B7B
0x180299b70  mov     r9d, 144h
0x180299b76  jmp     loc_180299E2E
0x180299b7b  mov     rbx, [rbp+430h+lpLibFileName]
0x180299b7f  lea     rcx, [rbp+430h+cbData]
0x180299b83  mov     [rbp+430h+lpLibFileName], r13
0x180299b87  mov     qword ptr [rbp+430h+cbData], r13
0x180299b8b  call    ?Reset@?$SH@PEAGVSH_SSTRING@@@@QEAAXXZ; SH<ushort *,SH_SSTRING>::Reset(void)
0x180299b90  lea     r8, [rbp+430h+lpLibFileName]
0x180299b94  mov     qword ptr [rbp+430h+cbData], rbx
0x180299b98  mov     rcx, rbx; lpFileName
0x180299b9b  call    ?GetFinalPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGKPEAPEAG@Z; CMiscHelpersT<CEmptyType>::GetFinalPath(ushort const *,ulong,ushort * *)
0x180299ba0  mov     ebx, eax
0x180299ba2  test    eax, eax
0x180299ba4  jns     short loc_180299BCB
0x180299ba6  mov     rcx, [rdi]
0x180299ba9  lea     r8, aCdeploymentses_0; "CDeploymentSessionWrapper::PostDownload"
0x180299bb0  mov     r9d, 14Bh
0x180299bb6  mov     edx, eax
0x180299bb8  call    ?LogError@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@JPEBGK@Z; CFCLogLiteT<CEmptyType>::LogError(IFCDiagnosticsLite *,long,ushort const *,ulong)
0x180299bbd  lea     rcx, [rbp+430h+cbData]
0x180299bc1  call    ?Reset@?$SH@PEAGVSH_SSTRING@@@@QEAAXXZ; SH<ushort *,SH_SSTRING>::Reset(void)
0x180299bc6  jmp     loc_180299E3F
0x180299bcb  lea     rcx, [rbp+430h+cbData]
0x180299bcf  call    ?Reset@?$SH@PEAGVSH_SSTRING@@@@QEAAXXZ; SH<ushort *,SH_SSTRING>::Reset(void)
0x180299bd4  mov     rsi, [rbp+430h+lpLibFileName]
0x180299bd8  lea     rdx, [rsp+530h+var_4E0]
0x180299bdd  mov     rcx, rsi
0x180299be0  call    ?FileExists@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAH@Z; CMiscHelpersT<CEmptyType>::FileExists(ushort const *,int *)
0x180299be5  mov     ebx, eax
0x180299be7  test    eax, eax
0x180299be9  jns     short loc_180299BF6
0x180299beb  mov     r9d, 14Dh
0x180299bf1  jmp     loc_180299E2E
0x180299bf6  mov     rcx, [rdi]
0x180299bf9  cmp     [rsp+530h+var_4E0], r13d
0x180299bfe  jnz     short loc_180299C12
0x180299c00  mov     ebx, 80070002h
0x180299c05  mov     r9d, 14Eh
0x180299c0b  mov     edx, ebx
0x180299c0d  jmp     loc_180299E33
0x180299c12  test    rcx, rcx
0x180299c15  jz      short loc_180299C2B
0x180299c17  mov     r9, rsi
0x180299c1a  lea     r8, aDeploymentsess_17; "DeploymentSessionWrapper: Loading Updat"...
0x180299c21  mov     edx, 2
0x180299c26  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180299c2b  xor     r8d, r8d; dwFlags
0x180299c2e  xor     edx, edx; hFile
0x180299c30  mov     rcx, rsi; lpLibFileName
0x180299c33  call    cs:__imp_LoadLibraryExW
0x180299c3a  nop     dword ptr [rax+rax+00h]
0x180299c3f  lea     rcx, [rsp+530h+var_4D8]
0x180299c44  mov     rbx, rax
0x180299c47  call    ?Reset@?$SH@PEAUHINSTANCE__@@VSH_HMODULE@@@@QEAAXXZ; SH<HINSTANCE__ *,SH_HMODULE>::Reset(void)
0x180299c4c  test    rbx, rbx
0x180299c4f  jnz     short loc_180299C76
0x180299c51  mov     [rsp+530h+var_4D8], r13
0x180299c56  call    cs:__imp_GetLastError
0x180299c5d  nop     dword ptr [rax+rax+00h]
0x180299c62  mov     ecx, eax; unsigned int
0x180299c64  call    ?C_LR2HR@SErrorConverter@@SAJK@Z; SErrorConverter::C_LR2HR(ulong)
0x180299c69  mov     ebx, eax
0x180299c6b  mov     r9d, 152h
0x180299c71  jmp     loc_180299E2E
0x180299c76  lea     rdx, aCreateofflined; "CreateOfflineDeploymentSession"
0x180299c7d  mov     [rsp+530h+var_4D8], rbx
0x180299c82  mov     rcx, rbx; hModule
0x180299c85  call    cs:__imp_GetProcAddress
0x180299c8c  nop     dword ptr [rax+rax+00h]
0x180299c91  mov     rbx, rax
0x180299c94  test    rax, rax
0x180299c97  jnz     short loc_180299CB9
0x180299c99  call    cs:__imp_GetLastError
0x180299ca0  nop     dword ptr [rax+rax+00h]
0x180299ca5  mov     ecx, eax; unsigned int
0x180299ca7  call    ?C_LR2HR@SErrorConverter@@SAJK@Z; SErrorConverter::C_LR2HR(ulong)
0x180299cac  mov     ebx, eax
0x180299cae  mov     r9d, 155h
0x180299cb4  jmp     loc_180299E2E
0x180299cb9  mov     rcx, [rdi]
0x180299cbc  xor     eax, eax
0x180299cbe  mov     [rbp+430h+var_480], rax
0x180299cc2  xorps   xmm0, xmm0
0x180299cc5  movups  [rbp+430h+var_4B0], xmm0
0x180299cc9  mov     qword ptr [rbp+430h+var_4B0], r15
0x180299ccd  lea     esi, [rax+2]
0x180299cd0  movups  [rbp+430h+var_4A0], xmm0
0x180299cd4  movups  [rbp+430h+var_490], xmm0
0x180299cd8  test    rcx, rcx
0x180299cdb  jz      short loc_180299CEB
0x180299cdd  lea     r8, aDeploymentsess_7; "DeploymentSessionWrapper: Creating Depl"...
0x180299ce4  mov     edx, esi
0x180299ce6  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180299ceb  mov     rcx, [rdi]
0x180299cee  test    rcx, rcx
0x180299cf1  jz      short loc_180299D07
0x180299cf3  mov     r9d, 1
0x180299cf9  lea     r8, aDeploymentsess_19; "DeploymentSessionWrapper: Session Versi"...
0x180299d00  mov     edx, esi
0x180299d02  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180299d07  mov     rcx, [rdi]
0x180299d0a  test    rcx, rcx
0x180299d0d  jz      short loc_180299D20
0x180299d0f  mov     r9, r14
0x180299d12  lea     r8, aDeploymentsess_11; "DeploymentSessionWrapper: Sandbox path "...
0x180299d19  mov     edx, esi
0x180299d1b  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180299d20  mov     rcx, [rdi]
0x180299d23  test    rcx, rcx
0x180299d26  jz      short loc_180299D39
0x180299d28  mov     r9, r12
0x180299d2b  lea     r8, aDeploymentsess_5; "DeploymentSessionWrapper: Offline windi"...
0x180299d32  mov     edx, esi
0x180299d34  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180299d39  mov     rcx, [rdi]
0x180299d3c  test    rcx, rcx
0x180299d3f  jz      short loc_180299D52
0x180299d41  mov     r9d, esi
0x180299d44  lea     r8, aDeploymentsess_20; "DeploymentSessionWrapper: Info2version "...
0x180299d4b  mov     edx, esi
0x180299d4d  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180299d52  mov     rcx, [rdi]
0x180299d55  test    rcx, rcx
0x180299d58  jz      short loc_180299D6C
0x180299d5a  mov     r9, qword ptr [rbp+430h+var_4B0]
0x180299d5e  lea     r8, aDeploymentsess_12; "DeploymentSessionWrapper: Session data "...
0x180299d65  mov     edx, esi
0x180299d67  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180299d6c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180299d73  lea     rax, [rbp+430h+var_458]
0x180299d77  xor     r9d, r9d
0x180299d7a  mov     [rsp+530h+var_4F8], rax
0x180299d7f  mov     r8, r12
0x180299d82  lea     rax, [rbp+430h+var_4B0]
0x180299d86  mov     rdx, r14
0x180299d89  mov     [rsp+530h+var_500], rax
0x180299d8e  lea     rax, [rsp+530h+hKey]
0x180299d93  mov     dword ptr [rsp+530h+lpcbData], esi
0x180299d97  lea     ecx, [r9+1]
0x180299d9b  mov     [rsp+530h+phkResult], rax
0x180299da0  mov     rax, rbx
0x180299da3  movdqu  xmmword ptr [rsp+530h+hKey], xmm0
0x180299da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180299dae  mov     ebx, eax
0x180299db0  test    eax, eax
0x180299db2  jns     short loc_180299DBC
0x180299db4  mov     r9d, 16Ah
0x180299dba  jmp     short loc_180299E2E
0x180299dbc  mov     rcx, [rbp+430h+var_458]
0x180299dc0  lea     r8, [rbp+430h+var_460]
0x180299dc4  lea     rdx, _GUID_36fb071a_6dc5_48bf_a6f3_d4f6751d39dc
0x180299dcb  mov     rax, [rcx]
0x180299dce  mov     rax, [rax]
0x180299dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180299dd6  mov     rcx, [rdi]
0x180299dd9  mov     ebx, eax
0x180299ddb  test    eax, eax
0x180299ddd  jns     short loc_180299DFF
0x180299ddf  test    rcx, rcx
0x180299de2  jz      short loc_180299DF5
0x180299de4  lea     r8, aDeploymentsess_8; "DeploymentSessionWrapper: This version "...
  ... truncated ...
```
