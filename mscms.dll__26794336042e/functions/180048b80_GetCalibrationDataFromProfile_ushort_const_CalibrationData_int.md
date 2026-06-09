# GetCalibrationDataFromProfile(ushort const *,CalibrationData *,int)

- ea: `0x180048b80`
- end: `0x180048f31`
- name: `?GetCalibrationDataFromProfile@@YAJPEBGPEAUCalibrationData@@H@Z`
- size: `945`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct CalibrationData *, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180047f20`
- `0x18004aa0c`

## callees

- `0x180009810`
- `0x18000a30c`
- `0x18000a538`
- `0x18001ca84`
- `0x180029f14`
- `0x18002e5f0`
- `0x18002e614`
- `0x18002ea60`
- `0x180047d28`
- `0x180048b80`
- `0x180048f38`
- `0x180049220`
- `0x180049360`
- `0x18004a6d4`
- `0x18004aebc`
- `0x18004aef8`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180048ee8`
- `ntdll!EtwEventWrite` at `0x180048ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048cc3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180048cb4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180048cb4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180048d43`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180048d43`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180048cdd`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180048cdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048ef7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048ef7`

## pseudocode

```c
__int64 __fastcall GetCalibrationDataFromProfile(WCHAR *lpFileName, struct CalibrationData *a2)
{
  __int64 v2; // rbx
  const WCHAR *FilenameFromPath; // rax
  const unsigned __int16 *v6; // rsi
  int v7; // eax
  unsigned __int64 v8; // rdx
  signed int LastError; // eax
  bool v10; // cc
  unsigned __int64 v11; // rdx
  WCHAR *v12; // rcx
  HANDLE FileW; // rax
  void *v14; // rax
  bool *v15; // r9
  __int64 v16; // rdx
  int v17; // esi
  __int64 v18; // rdx
  _QWORD *v19; // rax
  __int64 v20; // rcx
  float v21; // xmm0_4
  __int64 v22; // rax
  unsigned int v23; // eax
  int IsIccProfile; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v26; // [rsp+44h] [rbp-BCh] BYREF
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  struct tagPROFILE v28; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwSize; // [rsp+68h] [rbp-98h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v31[2]; // [rsp+80h] [rbp-80h] BYREF
  int v32; // [rsp+A0h] [rbp-60h]
  __int128 v33; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v34; // [rsp+C0h] [rbp-40h]
  int v35; // [rsp+D0h] [rbp-30h]
  WCHAR pBuffer[264]; // [rsp+E0h] [rbp-20h] BYREF

  *(_QWORD *)&v28.dwType = 2;
  v2 = -1;
  IsIccProfile = 0;
  v28.pProfileData = 0;
  *(_QWORD *)&v28.cbDataSize = 0;
  if ( !lpFileName || !a2 )
  {
    LastError = -2147024809;
    goto LABEL_42;
  }
  *(_OWORD *)a2 = 0;
  *((_OWORD *)a2 + 1) = 0;
  *((_QWORD *)a2 + 4) = 0;
  FilenameFromPath = GetFilenameFromPath(lpFileName);
  v6 = FilenameFromPath;
  if ( !FilenameFromPath )
  {
    v7 = -2147024809;
LABEL_5:
    IsIccProfile = v7;
    goto LABEL_45;
  }
  if ( FilenameFromPath == lpFileName )
  {
    pdwSize = 520;
    if ( !GetColorDirectoryW(0, pBuffer, &pdwSize) )
    {
      LastError = GetLastError();
      v10 = LastError <= 0;
      if ( !LastError )
      {
        LastError = -2147467259;
        goto LABEL_42;
      }
LABEL_10:
      if ( !v10 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_42;
    }
    IsIccProfile = StringCbCatW(pBuffer, v8, L"\\");
    if ( IsIccProfile < 0 )
      goto LABEL_44;
    IsIccProfile = StringCbCatW(pBuffer, v11, v6);
    if ( IsIccProfile < 0 )
      goto LABEL_44;
    v12 = pBuffer;
  }
  else
  {
    v12 = lpFileName;
  }
  FileW = CreateFileW(v12, 0x80000000, 1u, 0, 3u, 0x10000080u, 0);
  v2 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_17;
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
    goto LABEL_17;
  if ( FileSize.HighPart )
  {
    IsIccProfile = -2147022885;
    goto LABEL_45;
  }
  v28.cbDataSize = FileSize.LowPart;
  v14 = operator new[](FileSize.LowPart, (const struct std::nothrow_t *)&std::nothrow);
  v28.pProfileData = v14;
  if ( !v14 )
  {
    IsIccProfile = -2147024882;
    goto LABEL_45;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile((HANDLE)v2, v14, v28.cbDataSize, &NumberOfBytesRead, 0) )
  {
LABEL_17:
    LastError = GetLastError();
    v10 = LastError <= 0;
    goto LABEL_10;
  }
  if ( NumberOfBytesRead != v28.cbDataSize )
  {
    v7 = -2147467259;
    goto LABEL_5;
  }
  LOBYTE(v26) = 0;
  IsIccProfile = ProfileProperties::IsIccProfile((HANDLE)v2, (void *)v28.cbDataSize, &v26, v15);
  if ( IsIccProfile >= 0 )
  {
    if ( (_BYTE)v26 )
    {
      IsIccProfile = GetCalibrationDataFromIccProfile(&v28, a2);
      if ( IsIccProfile < 0 )
        goto LABEL_44;
      LOBYTE(v16) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2>::GetImpl'::`2'::impl,
        v16);
      v17 = IsIccProfile;
      IsIccProfile = GetCharacterizationDataFromIccProfile(&v28, a2);
      if ( IsIccProfile < 0 )
        goto LABEL_44;
      IsIccProfile = v17;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles>::GetImpl'::`2'::impl)
        || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl'::`2'::impl) )
      {
        v19 = (_QWORD *)((char *)a2 + 16);
        v20 = *((_QWORD *)a2 + 2);
        if ( *(float *)(v20 + 56) == 0.0 )
        {
          v21 = *(float *)(v20 + 48);
          if ( v21 != 0.0 )
            *(float *)(v20 + 56) = v21;
        }
      }
      else
      {
        v19 = (_QWORD *)((char *)a2 + 16);
      }
      if ( *v19 )
      {
        v33 = 0;
        v35 = 0;
        v34 = 0;
        if ( (int)GetChromaticAdaptationMatrixFromIccProfile(&v28, &v33) >= 0 )
        {
          v32 = v35;
          v31[0] = v33;
          v31[1] = v34;
          ApplyChromaticAdaptationMatrixInverseToAdaptedPrimaries(a2, v31);
        }
      }
      LOBYTE(v18) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2>::GetImpl'::`2'::impl,
        v18);
      LastError = IsIccProfile;
      goto LABEL_43;
    }
    LastError = GetCalibrationDataFromWcsProfile(&v28, a2);
LABEL_42:
    IsIccProfile = LastError;
LABEL_43:
    if ( LastError >= 0 )
      goto LABEL_50;
  }
LABEL_44:
  if ( lpFileName )
  {
LABEL_45:
    v22 = -1;
    do
      ++v22;
    while ( lpFileName[v22] );
    v23 = 2 * v22 + 2;
    goto LABEL_49;
  }
  v23 = 0;
LABEL_49:
  *((_QWORD *)&v33 + 1) = v23;
  *(_QWORD *)&v33 = lpFileName;
  *(_QWORD *)&v34 = &IsIccProfile;
  *((_QWORD *)&v34 + 1) = 4;
  EtwEventWrite(g_etwHandle, CALIBRATION_LOADING_DATA_FAILED, 2, &v33);
LABEL_50:
  if ( v2 != -1 )
    CloseHandle((HANDLE)v2);
  operator delete(v28.pProfileData);
  return (unsigned int)IsIccProfile;
}

```

## disassembly

```asm
0x180048b80  mov     [rsp-8+arg_10], rbx
0x180048b85  push    rbp
0x180048b86  push    rsi
0x180048b87  push    rdi
0x180048b88  push    r14
0x180048b8a  push    r15
0x180048b8c  lea     rbp, [rsp-200h]
0x180048b94  sub     rsp, 300h
0x180048b9b  mov     rax, cs:__security_cookie
0x180048ba2  xor     rax, rsp
0x180048ba5  mov     [rbp+220h+var_30], rax
0x180048bac  xor     r15d, r15d
0x180048baf  mov     qword ptr [rsp+320h+var_2D0.dwType], 2
0x180048bb8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180048bbc  mov     [rsp+320h+var_2E0], r15d
0x180048bc1  mov     [rsp+320h+var_2D0.pProfileData], r15
0x180048bc6  mov     rdi, rdx
0x180048bc9  mov     qword ptr [rsp+320h+var_2D0.cbDataSize], r15
0x180048bce  mov     r14, rcx
0x180048bd1  test    rcx, rcx
0x180048bd4  jz      loc_180048E87
0x180048bda  test    rdx, rdx
0x180048bdd  jz      loc_180048E87
0x180048be3  xorps   xmm0, xmm0
0x180048be6  xor     eax, eax
0x180048be8  movups  xmmword ptr [rdx], xmm0
0x180048beb  movups  xmmword ptr [rdx+10h], xmm0
0x180048bef  mov     [rdx+20h], rax
0x180048bf3  call    GetFilenameFromPath
0x180048bf8  mov     rsi, rax
0x180048bfb  test    rax, rax
0x180048bfe  jnz     short loc_180048C0E
0x180048c00  mov     eax, 80070057h
0x180048c05  mov     [rsp+320h+var_2E0], eax
0x180048c09  jmp     loc_180048E99
0x180048c0e  cmp     rsi, r14
0x180048c11  jnz     short loc_180048C90
0x180048c13  lea     r8, [rsp+320h+pdwSize]; pdwSize
0x180048c18  mov     [rsp+320h+pdwSize], 208h
0x180048c20  lea     rdx, [rbp+220h+pBuffer]; pBuffer
0x180048c24  xor     ecx, ecx; pMachineName
0x180048c26  call    GetColorDirectoryW
0x180048c2b  test    eax, eax
0x180048c2d  jnz     short loc_180048C56
0x180048c2f  call    cs:__imp_GetLastError
0x180048c35  test    eax, eax
0x180048c37  jnz     short loc_180048C43
0x180048c39  mov     eax, 80004005h
0x180048c3e  jmp     loc_180048E8C
0x180048c43  jle     loc_180048E8C
0x180048c49  movzx   eax, ax
0x180048c4c  or      eax, 80070000h
0x180048c51  jmp     loc_180048E8C
0x180048c56  lea     r8, StringValue; "\\"
0x180048c5d  lea     rcx, [rbp+220h+pBuffer]; unsigned __int16 *
0x180048c61  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180048c66  mov     [rsp+320h+var_2E0], eax
0x180048c6a  test    eax, eax
0x180048c6c  js      loc_180048E94
0x180048c72  mov     r8, rsi; unsigned __int16 *
0x180048c75  lea     rcx, [rbp+220h+pBuffer]; unsigned __int16 *
0x180048c79  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180048c7e  mov     [rsp+320h+var_2E0], eax
0x180048c82  test    eax, eax
0x180048c84  js      loc_180048E94
0x180048c8a  lea     rcx, [rbp+220h+pBuffer]
0x180048c8e  jmp     short loc_180048C93
0x180048c90  mov     rcx, r14; lpFileName
0x180048c93  xor     r9d, r9d; lpSecurityAttributes
0x180048c96  mov     [rsp+320h+hTemplateFile], r15; hTemplateFile
0x180048c9b  mov     [rsp+320h+dwFlagsAndAttributes], 10000080h; dwFlagsAndAttributes
0x180048ca3  mov     edx, 80000000h; dwDesiredAccess
0x180048ca8  mov     [rsp+320h+dwCreationDisposition], 3; dwCreationDisposition
0x180048cb0  lea     r8d, [r9+1]; dwShareMode
0x180048cb4  call    cs:__imp_CreateFileW
0x180048cba  mov     rbx, rax
0x180048cbd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180048cc1  jnz     short loc_180048CD0
0x180048cc3  call    cs:__imp_GetLastError
0x180048cc9  test    eax, eax
0x180048ccb  jmp     loc_180048C43
0x180048cd0  lea     rdx, [rsp+320h+FileSize]; lpFileSize
0x180048cd5  mov     qword ptr [rsp+320h+FileSize], r15
0x180048cda  mov     rcx, rbx; hFile
0x180048cdd  call    cs:__imp_GetFileSizeEx
0x180048ce3  test    eax, eax
0x180048ce5  jz      short loc_180048CC3
0x180048ce7  cmp     dword ptr [rsp+320h+FileSize+4], r15d
0x180048cec  jz      short loc_180048CFB
0x180048cee  mov     [rsp+320h+var_2E0], 800707DBh
0x180048cf6  jmp     loc_180048E99
0x180048cfb  mov     rax, qword ptr [rsp+320h+FileSize]
0x180048d00  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180048d07  mov     ecx, eax; unsigned __int64
0x180048d09  mov     [rsp+320h+var_2D0.cbDataSize], eax
0x180048d0d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180048d12  mov     [rsp+320h+var_2D0.pProfileData], rax
0x180048d17  test    rax, rax
0x180048d1a  jnz     short loc_180048D29
0x180048d1c  mov     [rsp+320h+var_2E0], 8007000Eh
0x180048d24  jmp     loc_180048E99
0x180048d29  mov     r8d, [rsp+320h+var_2D0.cbDataSize]; nNumberOfBytesToRead
0x180048d2e  lea     r9, [rsp+320h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180048d33  mov     rdx, rax; lpBuffer
0x180048d36  mov     [rsp+320h+NumberOfBytesRead], r15d
0x180048d3b  mov     rcx, rbx; hFile
0x180048d3e  mov     qword ptr [rsp+320h+dwCreationDisposition], r15; lpOverlapped
0x180048d43  call    cs:__imp_ReadFile
0x180048d49  test    eax, eax
0x180048d4b  jz      loc_180048CC3
0x180048d51  mov     edx, [rsp+320h+var_2D0.cbDataSize]; void *
0x180048d55  cmp     [rsp+320h+NumberOfBytesRead], edx
0x180048d59  jz      short loc_180048D65
0x180048d5b  mov     eax, 80004005h
0x180048d60  jmp     loc_180048C05
0x180048d65  lea     r8, [rsp+320h+var_2DC]; unsigned int
0x180048d6a  mov     byte ptr [rsp+320h+var_2DC], r15b
0x180048d6f  mov     rcx, rbx; hFile
0x180048d72  call    ?IsIccProfile@ProfileProperties@@YAJPEAXKPEA_N@Z; ProfileProperties::IsIccProfile(void *,ulong,bool *)
0x180048d77  mov     [rsp+320h+var_2E0], eax
0x180048d7b  test    eax, eax
0x180048d7d  js      loc_180048E94
0x180048d83  lea     rcx, [rsp+320h+var_2D0]; struct tagPROFILE *
0x180048d88  mov     rdx, rdi; struct CalibrationData *
0x180048d8b  cmp     byte ptr [rsp+320h+var_2DC], r15b
0x180048d90  jz      loc_180048E80
0x180048d96  call    ?GetCalibrationDataFromIccProfile@@YAJPEAUtagPROFILE@@PEAUCalibrationData@@@Z; GetCalibrationDataFromIccProfile(tagPROFILE *,CalibrationData *)
0x180048d9b  mov     [rsp+320h+var_2E0], eax
0x180048d9f  test    eax, eax
0x180048da1  js      loc_180048E94
0x180048da7  mov     dl, 1
0x180048da9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2> `wil::Feature<__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2>::GetImpl(void)'::`2'::impl
0x180048db0  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180048db5  mov     esi, [rsp+320h+var_2E0]
0x180048db9  lea     rcx, [rsp+320h+var_2D0]; struct tagPROFILE *
0x180048dbe  mov     rdx, rdi; struct CalibrationData *
0x180048dc1  call    ?GetCharacterizationDataFromIccProfile@@YAJPEAUtagPROFILE@@PEAUCalibrationData@@@Z; GetCharacterizationDataFromIccProfile(tagPROFILE *,CalibrationData *)
0x180048dc6  mov     [rsp+320h+var_2E0], eax
0x180048dca  test    eax, eax
0x180048dcc  js      loc_180048E94
0x180048dd2  mov     [rsp+320h+var_2E0], esi
0x180048dd6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles> `wil::Feature<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles>::GetImpl(void)'::`2'::impl
0x180048ddd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles>::__private_IsEnabled(void)
0x180048de2  test    al, al
0x180048de4  jnz     short loc_180048DFC
0x180048de6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer> `wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl(void)'::`2'::impl
0x180048ded  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(void)
0x180048df2  test    al, al
0x180048df4  jnz     short loc_180048DFC
0x180048df6  lea     rax, [rdi+10h]
0x180048dfa  jmp     short loc_180048E23
0x180048dfc  lea     rax, [rdi+10h]
0x180048e00  xorps   xmm1, xmm1
0x180048e03  mov     rcx, [rax]
0x180048e06  movss   xmm0, dword ptr [rcx+38h]
0x180048e0b  ucomiss xmm0, xmm1
0x180048e0e  jp      short loc_180048E23
0x180048e10  jnz     short loc_180048E23
0x180048e12  movss   xmm0, dword ptr [rcx+30h]
0x180048e17  ucomiss xmm0, xmm1
0x180048e1a  jp      short loc_180048E1E
0x180048e1c  jz      short loc_180048E23
0x180048e1e  movss   dword ptr [rcx+38h], xmm0
0x180048e23  cmp     [rax], r15
0x180048e26  jz      short loc_180048E6C
0x180048e28  xorps   xmm0, xmm0
0x180048e2b  lea     rdx, [rbp+220h+var_270]
0x180048e2f  xor     eax, eax
0x180048e31  lea     rcx, [rsp+320h+var_2D0]
0x180048e36  movups  [rbp+220h+var_270], xmm0
0x180048e3a  mov     [rbp+220h+var_250], eax
0x180048e3d  movups  [rbp+220h+var_260], xmm0
0x180048e41  call    ?GetChromaticAdaptationMatrixFromIccProfile@@YAJPEAUtagPROFILE@@AEAV?$array@M$08@std@@@Z; GetChromaticAdaptationMatrixFromIccProfile(tagPROFILE *,std::array<float,9> &)
0x180048e46  test    eax, eax
0x180048e48  js      short loc_180048E6C
0x180048e4a  movups  xmm0, [rbp+220h+var_270]
0x180048e4e  mov     eax, [rbp+220h+var_250]
0x180048e51  lea     rdx, [rbp+220h+var_2A0]
0x180048e55  movups  xmm1, [rbp+220h+var_260]
0x180048e59  mov     rcx, rdi
0x180048e5c  mov     [rbp+220h+var_280], eax
0x180048e5f  movaps  [rbp+220h+var_2A0], xmm0
0x180048e63  movaps  [rbp+220h+var_290], xmm1
0x180048e67  call    ?ApplyChromaticAdaptationMatrixInverseToAdaptedPrimaries@@YAJPEAUCalibrationData@@V?$array@M$08@std@@@Z; ApplyChromaticAdaptationMatrixInverseToAdaptedPrimaries(CalibrationData *,std::array<float,9>)
0x180048e6c  mov     dl, 1
0x180048e6e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2> `wil::Feature<__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2>::GetImpl(void)'::`2'::impl
0x180048e75  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowColorimetryWithoutMHC2>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180048e7a  mov     eax, [rsp+320h+var_2E0]
0x180048e7e  jmp     short loc_180048E90
0x180048e80  call    ?GetCalibrationDataFromWcsProfile@@YAJPEAUtagPROFILE@@PEAUCalibrationData@@@Z; GetCalibrationDataFromWcsProfile(tagPROFILE *,CalibrationData *)
0x180048e85  jmp     short loc_180048E8C
0x180048e87  mov     eax, 80070057h
0x180048e8c  mov     [rsp+320h+var_2E0], eax
0x180048e90  test    eax, eax
0x180048e92  jns     short loc_180048EEE
0x180048e94  test    r14, r14
0x180048e97  jz      short loc_180048EB1
0x180048e99  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048e9d  inc     rax
0x180048ea0  cmp     [r14+rax*2], r15w
0x180048ea5  jnz     short loc_180048E9D
0x180048ea7  lea     rax, ds:2[rax*2]
0x180048eaf  jmp     short loc_180048EB4
0x180048eb1  mov     rax, r15
0x180048eb4  mov     rcx, cs:g_etwHandle
0x180048ebb  lea     r9, [rbp+220h+var_270]
0x180048ebf  mov     dword ptr [rbp+220h+var_270+8], eax
0x180048ec2  lea     rdx, CALIBRATION_LOADING_DATA_FAILED
0x180048ec9  lea     rax, [rsp+320h+var_2E0]
0x180048ece  mov     qword ptr [rbp+220h+var_270], r14
0x180048ed2  mov     r8d, 2
0x180048ed8  mov     qword ptr [rbp+220h+var_260], rax
0x180048edc  mov     dword ptr [rbp+220h+var_270+0Ch], r15d
0x180048ee0  mov     qword ptr [rbp+220h+var_260+8], 4
0x180048ee8  call    cs:__imp_EtwEventWrite
0x180048eee  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180048ef2  jz      short loc_180048EFD
0x180048ef4  mov     rcx, rbx; hObject
0x180048ef7  call    cs:__imp_CloseHandle
0x180048efd  mov     rcx, [rsp+320h+var_2D0.pProfileData]; void *
0x180048f02  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048f07  mov     eax, [rsp+320h+var_2E0]
0x180048f0b  mov     rcx, [rbp+220h+var_30]
0x180048f12  xor     rcx, rsp; StackCookie
0x180048f15  call    __security_check_cookie
0x180048f1a  mov     rbx, [rsp+320h+arg_10]
0x180048f22  add     rsp, 300h
0x180048f29  pop     r15
0x180048f2b  pop     r14
0x180048f2d  pop     rdi
0x180048f2e  pop     rsi
0x180048f2f  pop     rbp
0x180048f30  retn
```
