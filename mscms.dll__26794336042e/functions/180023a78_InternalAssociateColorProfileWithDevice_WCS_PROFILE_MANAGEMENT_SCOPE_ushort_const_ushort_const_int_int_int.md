# InternalAssociateColorProfileWithDevice(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ushort const *,int,int,int)

- ea: `0x180023a78`
- end: `0x180024355`
- name: `?InternalAssociateColorProfileWithDevice@@YAHW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBG1HHH@Z`
- size: `2269`
- prototype: `int(enum WCS_PROFILE_MANAGEMENT_SCOPE, const unsigned __int16 *, const unsigned __int16 *, int, int, int)`
- caller_count: `6`
- callee_count: `21`
- tags: `loader_planting`

## callers

- `0x18002ba60`
- `0x1800441d0`
- `0x1800442e0`
- `0x180045470`
- `0x180046450`
- `0x18004cea0`

## callees

- `0x180001dc4`
- `0x1800027b0`
- `0x180008bf0`
- `0x180008cc0`
- `0x18000be44`
- `0x18001b3a8`
- `0x18001ffe0`
- `0x180023a4c`
- `0x180023a78`
- `0x180029f14`
- `0x18002af3c`
- `0x18002e5f0`
- `0x18002f2f4`
- `0x18003e944`
- `0x18003eb70`
- `0x18003ec6c`
- `0x18003f20c`
- `0x18003f554`
- `0x180040d94`
- `0x1800427b8`
- `0x18004344c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18002431a`
- `ntdll!EtwEventWrite` at `0x18002431a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023ba7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023c50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023cb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023d26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002432a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023ba7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023c50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023cb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023d26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002432a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f24`

## string_xrefs

- `0x180023ba0`: `Could not parse file name from profile path %s\n`
- `0x180023bcb`: `Could not get color directory\n`
- `0x180024273`: `AttemptRefreshCalibrationIfProfileChanged Failed: %d\n`

## pseudocode

```c
__int64 __fastcall InternalAssociateColorProfileWithDevice(
        enum WCS_PROFILE_MANAGEMENT_SCOPE a1,
        const unsigned __int16 *a2,
        OLECHAR *a3,
        int a4,
        int a5,
        int a6)
{
  int v8; // r14d
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int v12; // ebx
  const unsigned __int16 *FilenameFromPath; // r13
  const OLECHAR *v14; // rsi
  __int64 v15; // r14
  __int64 v16; // rax
  int v17; // r8d
  DWORD v18; // ecx
  DWORD phClass; // ebx
  unsigned int v20; // edx
  int v21; // r8d
  unsigned int v22; // r9d
  DWORD v23; // ecx
  unsigned int v24; // r15d
  signed int DefaultDeviceProfileInDefaultScope; // eax
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  enum WCS_PROFILE_MANAGEMENT_SCOPE v30; // ecx
  int refreshed; // eax
  __int64 v32; // rax
  int v33; // [rsp+110h] [rbp-80h] BYREF
  int v34; // [rsp+114h] [rbp-7Ch] BYREF
  WCS_PROFILE_MANAGEMENT_SCOPE v35; // [rsp+118h] [rbp-78h] BYREF
  int v36; // [rsp+120h] [rbp-70h] BYREF
  unsigned int v37; // [rsp+124h] [rbp-6Ch] BYREF
  WCS_PROFILE_MANAGEMENT_SCOPE v38; // [rsp+128h] [rbp-68h] BYREF
  int v39; // [rsp+130h] [rbp-60h] BYREF
  DWORD pcbNeeded; // [rsp+134h] [rbp-5Ch] BYREF
  int v41; // [rsp+138h] [rbp-58h] BYREF
  unsigned int v42; // [rsp+13Ch] [rbp-54h] BYREF
  COLORPROFILESUBTYPE v43; // [rsp+140h] [rbp-50h] BYREF
  enum COLORPROFILETYPE v44; // [rsp+144h] [rbp-4Ch] BYREF
  unsigned int v45; // [rsp+148h] [rbp-48h] BYREF
  unsigned __int16 *v46; // [rsp+150h] [rbp-40h] BYREF
  unsigned __int16 *v47; // [rsp+158h] [rbp-38h] BYREF
  LPVOID lpMem; // [rsp+160h] [rbp-30h] BYREF
  unsigned __int16 *v49; // [rsp+168h] [rbp-28h] BYREF
  unsigned __int16 *v50; // [rsp+170h] [rbp-20h] BYREF
  unsigned __int16 *v51; // [rsp+178h] [rbp-18h] BYREF
  unsigned __int16 *v52; // [rsp+180h] [rbp-10h] BYREF
  unsigned __int16 *v53; // [rsp+188h] [rbp-8h] BYREF
  unsigned __int16 *v54; // [rsp+190h] [rbp+0h] BYREF
  int v55; // [rsp+198h] [rbp+8h] BYREF
  int v56; // [rsp+19Ch] [rbp+Ch] BYREF
  DWORD LastError; // [rsp+1A0h] [rbp+10h] BYREF
  OLECHAR *v58; // [rsp+1A8h] [rbp+18h] BYREF
  WCS_PROFILE_MANAGEMENT_SCOPE v59; // [rsp+1B0h] [rbp+20h] BYREF
  int v60; // [rsp+1B4h] [rbp+24h] BYREF
  unsigned int v61; // [rsp+1B8h] [rbp+28h] BYREF
  COLORPROFILESUBTYPE v62; // [rsp+1BCh] [rbp+2Ch] BYREF
  enum COLORPROFILETYPE v63; // [rsp+1C0h] [rbp+30h] BYREF
  unsigned int v64; // [rsp+1C4h] [rbp+34h] BYREF
  unsigned __int16 *v65; // [rsp+1C8h] [rbp+38h] BYREF
  const OLECHAR *v66; // [rsp+1D0h] [rbp+40h] BYREF
  const OLECHAR *v67; // [rsp+1D8h] [rbp+48h] BYREF
  const OLECHAR *v68; // [rsp+1E0h] [rbp+50h] BYREF
  const OLECHAR *v69; // [rsp+1E8h] [rbp+58h] BYREF
  const OLECHAR *v70; // [rsp+1F0h] [rbp+60h] BYREF
  const OLECHAR *v71; // [rsp+1F8h] [rbp+68h] BYREF
  const OLECHAR *v72; // [rsp+200h] [rbp+70h] BYREF
  const OLECHAR *v73; // [rsp+208h] [rbp+78h] BYREF
  const OLECHAR *v74; // [rsp+210h] [rbp+80h] BYREF
  const OLECHAR *v75; // [rsp+218h] [rbp+88h] BYREF
  const OLECHAR *v76; // [rsp+220h] [rbp+90h] BYREF
  const OLECHAR *v77; // [rsp+228h] [rbp+98h] BYREF
  OLECHAR *v78; // [rsp+230h] [rbp+A0h] BYREF
  const OLECHAR *v79; // [rsp+238h] [rbp+A8h] BYREF
  struct _SYSTEMTIME v80; // [rsp+240h] [rbp+B0h] BYREF
  struct tagPROFILEHEADER v81; // [rsp+250h] [rbp+C0h] BYREF
  const unsigned __int16 *v82; // [rsp+2D0h] [rbp+140h] BYREF
  int v83; // [rsp+2D8h] [rbp+148h]
  int v84; // [rsp+2DCh] [rbp+14Ch]
  OLECHAR *v85; // [rsp+2E0h] [rbp+150h]
  int v86; // [rsp+2E8h] [rbp+158h]
  int v87; // [rsp+2ECh] [rbp+15Ch]
  WCS_PROFILE_MANAGEMENT_SCOPE *v88; // [rsp+2F0h] [rbp+160h]
  __int64 v89; // [rsp+2F8h] [rbp+168h]
  unsigned __int16 v90[264]; // [rsp+300h] [rbp+170h] BYREF
  unsigned __int16 v91[264]; // [rsp+510h] [rbp+380h] BYREF
  unsigned __int16 v92[264]; // [rsp+720h] [rbp+590h] BYREF

  v35 = a1;
  v33 = a4;
  v8 = a4;
  memset_0(&v81, 0, sizeof(v81));
  pcbNeeded = 0;
  v37 = 0;
  v39 = 0;
  memset_0(v91, 0, 0x208u);
  memset_0(v92, 0, 0x208u);
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x200000000000LL) )
  {
    v34 = a5;
    v38 = v35;
    v36 = v8;
    v58 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v9,
      (__int64)&byte_180090E9F,
      v10,
      v11,
      (__int64)&v38,
      (const OLECHAR **)&v58,
      (__int64)&v36,
      (__int64)&v34);
  }
  if ( !a2 || !a3 || (unsigned int)v35 > WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER )
  {
    SetLastError(0x57u);
    return 0;
  }
  v12 = 0;
  v34 = 0;
  FilenameFromPath = GetFilenameFromPath(a2);
  if ( !FilenameFromPath )
  {
    v14 = L"Could not parse file name from profile path %s\n";
    SetLastError(0x57u);
    goto LABEL_34;
  }
  pcbNeeded = 520;
  if ( !InternalGetColorDirectory(0, v90, &pcbNeeded) )
  {
    v14 = L"Could not get color directory\n";
    goto LABEL_34;
  }
  v15 = -1;
  v16 = -1;
  do
    ++v16;
  while ( v90[v16] );
  if ( v90[v16 - 1] != 92 && (v17 = StringCchCatW(v90, 0x104u, gszBackslash), v17 < 0)
    || (v17 = StringCchCatW(v90, 0x104u, FilenameFromPath), v17 < 0) )
  {
    v18 = (unsigned __int16)v17;
    v14 = L"Input buffer is not big enough\n";
    if ( (v17 & 0x1FFF0000) != 0x70000 )
      v18 = v17;
    SetLastError(v18);
    goto LABEL_33;
  }
  v14 = &word_1800884E0;
  if ( GetProfileInfo(v90, 0, &v37, &v81, 0) )
  {
    phClass = v81.phClass;
    if ( v81.phClass == 1835955314 )
      phClass = 1936744803;
    if ( (unsigned int)IsLegacyColorManagedShimAppliedOnDeviceClass(phClass) )
    {
      v14 = L"AssociateColorProfileWithDevice is not supported as the legacy color managed shim is enabled\n";
      v23 = 50;
LABEL_24:
      SetLastError(v23);
      v12 = 0;
      goto LABEL_33;
    }
    v24 = v37;
    if ( v37 == 1667329392
      || v37 == 1735224688
      || phClass != v21
      || (DefaultDeviceProfileInDefaultScope = GetDefaultDeviceProfileInDefaultScope(a3, v20, v91, v22, v92),
          DefaultDeviceProfileInDefaultScope >= 0) )
    {
      v30 = v35;
      if ( v35 == WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER && a5 )
      {
        v36 = 0;
        if ( !(unsigned int)InternalGetUsePerUserProfiles(a3, phClass, &v36) )
          goto LABEL_32;
        if ( !v36 )
        {
          if ( !(unsigned int)CloneSystemWideProfileList(a3, phClass) )
            goto LABEL_32;
          if ( !(unsigned int)SaveSystemWideProfileListSnapshot(a3, phClass) )
            goto LABEL_32;
          v38 = WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER;
          if ( !(unsigned int)SetDeviceData(WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, a3, &v38, 4u) )
            goto LABEL_32;
        }
        v30 = v35;
      }
      DefaultDeviceProfileInDefaultScope = AddProfileToAssociatedProfileList(
                                             v30,
                                             a3,
                                             phClass,
                                             FilenameFromPath,
                                             &v37,
                                             v33,
                                             a6,
                                             &v39);
      if ( !DefaultDeviceProfileInDefaultScope || DefaultDeviceProfileInDefaultScope == 183 )
      {
        if ( v39 )
          ChangeICMSetting(v35, a3, 2);
        if ( v24 == 1667329392
          || v24 == 1735224688
          || phClass != 1936744803
          || (refreshed = AttemptRefreshCalibrationIfProfileChanged(a3, v91, v92, 0), refreshed >= 0) )
        {
          v12 = 1;
          v32 = -1;
          do
            ++v32;
          while ( a2[v32] );
          v82 = a2;
          v83 = 2 * v32 + 2;
          v84 = 0;
          do
            ++v15;
          while ( a3[v15] );
          v86 = 2 * v15 + 2;
          v85 = a3;
          v88 = &v35;
          v87 = 0;
          v89 = 4;
          EtwEventWrite(g_etwHandle, ASSOCIATE_PROFILE, 3, &v82);
          goto LABEL_33;
        }
        v14 = L"AttemptRefreshCalibrationIfProfileChanged Failed: %d\n";
        if ( (refreshed & 0x1FFF0000) == 0x70000 )
          refreshed = (unsigned __int16)refreshed;
        v23 = refreshed;
        goto LABEL_24;
      }
      v14 = L"AddProfileToAssociatedProfileList failed: %d\n";
    }
    else
    {
      v14 = L"GetDefaultDeviceProfile Failed: 0x%08x\n";
      if ( (DefaultDeviceProfileInDefaultScope & 0x1FFF0000) == 0x70000 )
        DefaultDeviceProfileInDefaultScope = (unsigned __int16)DefaultDeviceProfileInDefaultScope;
    }
    SetLastError(DefaultDeviceProfileInDefaultScope);
LABEL_32:
    v12 = v34;
  }
LABEL_33:
  v8 = v33;
LABEL_34:
  v45 = 0;
  lpMem = 0;
  v46 = 0;
  v47 = 0;
  v49 = 0;
  v50 = 0;
  v80 = 0;
  v51 = 0;
  v52 = 0;
  v44 = CPT_ICC;
  v43 = CPST_PERCEPTUAL;
  v42 = 0;
  v53 = 0;
  v54 = 0;
  v65 = 0;
  v41 = 0;
  CreatePropertiesFromProfile(
    a2,
    &v45,
    &v80,
    (unsigned __int16 **)&lpMem,
    &v46,
    &v47,
    &v49,
    &v50,
    &v51,
    &v52,
    &v44,
    &v43,
    &v42,
    &v53,
    &v54,
    &v65,
    (enum DmpDeviceType *)&v41);
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x400000000000LL) )
  {
    v60 = v41;
    v66 = v65;
    v67 = v54;
    v68 = v53;
    v61 = v42;
    v62 = v43;
    v63 = v44;
    v69 = v52;
    v70 = v51;
    v71 = v50;
    v72 = v49;
    v73 = v47;
    v74 = v46;
    v75 = (const OLECHAR *)lpMem;
    LOWORD(v38) = v80.wSecond;
    LOWORD(v39) = v80.wMinute;
    LOWORD(v36) = v80.wHour;
    LOWORD(v37) = v80.wDay;
    LOWORD(v34) = v80.wMonth;
    LOWORD(v33) = v80.wYear;
    v64 = v45;
    v76 = v91;
    v55 = a5;
    v59 = v35;
    v77 = FilenameFromPath;
    v56 = v8;
    v78 = a3;
    v79 = v14;
    LastError = GetLastError();
    LODWORD(v58) = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v26,
      (__int64)byte_1800910B3,
      v27,
      v28,
      (__int64)&v58,
      (__int64)&LastError,
      &v79,
      (__int64)&v59,
      (const OLECHAR **)&v78,
      (__int64)&v56,
      (__int64)&v55,
      &v77,
      &v76,
      (__int64)&v64,
      (__int64)&v33,
      (__int64)&v34,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v39,
      (__int64)&v38,
      &v75,
      &v74,
      &v73,
      &v72,
      &v71,
      &v70,
      &v69,
      (__int64)&v63,
      (__int64)&v62,
      (__int64)&v61,
      &v68,
      &v67,
      &v66,
      (__int64)&v60);
  }
  if ( lpMem )
  {
    MemFree(lpMem);
    lpMem = 0;
  }
  if ( v46 )
  {
    MemFree(v46);
    v46 = 0;
  }
  if ( v47 )
  {
    MemFree(v47);
    v47 = 0;
  }
  if ( v49 )
  {
    MemFree(v49);
    v49 = 0;
  }
  if ( v50 )
  {
    MemFree(v50);
    v50 = 0;
  }
  if ( v51 )
  {
    MemFree(v51);
    v51 = 0;
  }
  if ( v52 )
  {
    MemFree(v52);
    v52 = 0;
  }
  if ( v53 )
  {
    MemFree(v53);
    v53 = 0;
  }
  if ( v54 )
  {
    MemFree(v54);
    v54 = 0;
  }
  if ( v65 )
    MemFree(v65);
  return v12;
}

```

## disassembly

```asm
0x180023a78  push    rbp
0x180023a7a  push    rbx
0x180023a7b  push    rsi
0x180023a7c  push    rdi
0x180023a7d  push    r12
0x180023a7f  push    r13
0x180023a81  push    r14
0x180023a83  push    r15
0x180023a85  lea     rbp, [rsp-7B8h]
0x180023a8d  sub     rsp, 948h
0x180023a94  mov     rax, cs:__security_cookie
0x180023a9b  xor     rax, rsp
0x180023a9e  mov     [rbp+7F0h+var_50], rax
0x180023aa5  mov     rdi, r8
0x180023aa8  mov     [rbp+7F0h+var_868], ecx
0x180023aab  mov     r12, rdx
0x180023aae  mov     [rbp+7F0h+var_870], r9d
0x180023ab2  xor     edx, edx; Val
0x180023ab4  lea     rcx, [rbp+7F0h+var_730]; void *
0x180023abb  mov     r8d, 80h; Size
0x180023ac1  mov     r14d, r9d
0x180023ac4  call    memset_0
0x180023ac9  xor     r15d, r15d
0x180023acc  lea     rcx, [rbp+7F0h+var_470]; void *
0x180023ad3  mov     esi, 208h
0x180023ad8  mov     [rbp+7F0h+pcbNeeded], r15d
0x180023adc  mov     r8d, esi; Size
0x180023adf  mov     [rbp+7F0h+var_85C], r15d
0x180023ae3  xor     edx, edx; Val
0x180023ae5  mov     [rbp+7F0h+var_850], r15d
0x180023ae9  call    memset_0
0x180023aee  mov     r8d, esi; Size
0x180023af1  lea     rcx, [rbp+7F0h+var_260]; void *
0x180023af8  xor     edx, edx; Val
0x180023afa  call    memset_0
0x180023aff  mov     eax, cs:dword_18009E080
0x180023b05  cmp     eax, 5
0x180023b08  jbe     short loc_180023B6B
0x180023b0a  mov     rdx, 200000000000h
0x180023b14  lea     rcx, dword_18009E080
0x180023b1b  call    _tlgKeywordOn
0x180023b20  test    al, al
0x180023b22  jz      short loc_180023B6B
0x180023b24  mov     eax, [rbp+7F0h+arg_20]
0x180023b2a  lea     rdx, byte_180090E9F
0x180023b31  mov     [rbp+7F0h+var_86C], eax
0x180023b34  mov     eax, [rbp+7F0h+var_868]
0x180023b37  mov     [rbp+7F0h+var_858], eax
0x180023b3a  lea     rax, [rbp+7F0h+var_86C]
0x180023b3e  mov     [rsp+980h+var_948], rax
0x180023b43  lea     rax, [rbp+7F0h+var_860]
0x180023b47  mov     [rsp+980h+var_950], rax
0x180023b4c  lea     rax, [rbp+7F0h+var_7D8]
0x180023b50  mov     [rsp+980h+var_958], rax
0x180023b55  lea     rax, [rbp+7F0h+var_858]
0x180023b59  mov     [rsp+980h+var_960], rax
0x180023b5e  mov     [rbp+7F0h+var_860], r14d
0x180023b62  mov     [rbp+7F0h+var_7D8], rdi
0x180023b66  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180023b6b  test    r12, r12
0x180023b6e  jz      loc_180024325
0x180023b74  test    rdi, rdi
0x180023b77  jz      loc_180024325
0x180023b7d  cmp     [rbp+7F0h+var_868], 1
0x180023b81  ja      loc_180024325
0x180023b87  mov     ebx, r15d
0x180023b8a  mov     rcx, r12; lpStringSource
0x180023b8d  mov     [rbp+7F0h+var_86C], ebx
0x180023b90  call    GetFilenameFromPath
0x180023b95  mov     r13, rax
0x180023b98  test    rax, rax
0x180023b9b  jnz     short loc_180023BB2
0x180023b9d  lea     ecx, [rax+57h]; dwErrCode
0x180023ba0  lea     rsi, aCouldNotParseF; "Could not parse file name from profile "...
0x180023ba7  call    cs:__imp_SetLastError
0x180023bad  jmp     loc_180023D36
0x180023bb2  lea     r8, [rbp+7F0h+pcbNeeded]; pcbNeeded
0x180023bb6  mov     [rbp+7F0h+pcbNeeded], esi
0x180023bb9  lea     rdx, [rbp+7F0h+var_680]; unsigned __int16 *
0x180023bc0  xor     ecx, ecx; pName
0x180023bc2  call    ?InternalGetColorDirectory@@YAHPEBGPEAGPEAK@Z; InternalGetColorDirectory(ushort const *,ushort *,ulong *)
0x180023bc7  test    eax, eax
0x180023bc9  jnz     short loc_180023BD7
0x180023bcb  lea     rsi, aCouldNotGetCol; "Could not get color directory\n"
0x180023bd2  jmp     loc_180023D36
0x180023bd7  or      r14, 0FFFFFFFFFFFFFFFFh
0x180023bdb  lea     rcx, [rbp+7F0h+var_680]
0x180023be2  mov     rax, r14
0x180023be5  inc     rax
0x180023be8  cmp     [rcx+rax*2], r15w
0x180023bed  jnz     short loc_180023BE5
0x180023bef  cmp     [rbp+rax*2+7F0h+var_682], 5Ch ; '\'
0x180023bf8  mov     esi, 104h
0x180023bfd  jz      short loc_180023C1B
0x180023bff  lea     r8, gszBackslash; "\\"
0x180023c06  mov     edx, esi; unsigned __int64
0x180023c08  lea     rcx, [rbp+7F0h+var_680]; unsigned __int16 *
0x180023c0f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023c14  mov     r8d, eax
0x180023c17  test    eax, eax
0x180023c19  js      short loc_180023C34
0x180023c1b  mov     r8, r13; unsigned __int16 *
0x180023c1e  lea     rcx, [rbp+7F0h+var_680]; unsigned __int16 *
0x180023c25  mov     rdx, rsi; unsigned __int64
0x180023c28  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023c2d  mov     r8d, eax
0x180023c30  test    eax, eax
0x180023c32  jns     short loc_180023C5B
0x180023c34  mov     eax, r8d
0x180023c37  movzx   ecx, r8w
0x180023c3b  and     eax, 1FFF0000h
0x180023c40  lea     rsi, aInputBufferIsN; "Input buffer is not big enough\n"
0x180023c47  cmp     eax, 70000h
0x180023c4c  cmovnz  ecx, r8d; dwErrCode
0x180023c50  call    cs:__imp_SetLastError
0x180023c56  jmp     loc_180023D32
0x180023c5b  lea     r9, [rbp+7F0h+var_730]; struct tagPROFILEHEADER *
0x180023c62  mov     [rsp+980h+var_960], r15; void **
0x180023c67  lea     r8, [rbp+7F0h+var_85C]; unsigned int *
0x180023c6b  xor     edx, edx; enum COLORPROFILETYPE *
0x180023c6d  lea     rcx, [rbp+7F0h+var_680]; unsigned __int16 *
0x180023c74  lea     rsi, word_1800884E0
0x180023c7b  call    ?GetProfileInfo@@YAHPEBGPEAW4COLORPROFILETYPE@@PEAKPEAUtagPROFILEHEADER@@PEAPEAX@Z; GetProfileInfo(ushort const *,COLORPROFILETYPE *,ulong *,tagPROFILEHEADER *,void * *)
0x180023c80  test    eax, eax
0x180023c82  jz      loc_180023D32
0x180023c88  mov     ebx, [rbp+7F0h+var_730.phClass]
0x180023c8e  mov     r8d, 73706163h
0x180023c94  cmp     ebx, 6D6E7472h
0x180023c9a  cmovz   ebx, r8d
0x180023c9e  mov     ecx, ebx
0x180023ca0  call    IsLegacyColorManagedShimAppliedOnDeviceClass
0x180023ca5  test    eax, eax
0x180023ca7  jz      short loc_180023CC0
0x180023ca9  lea     rsi, aAssociatecolor_1; "AssociateColorProfileWithDevice is not "...
0x180023cb0  mov     ecx, 32h ; '2'; dwErrCode
0x180023cb5  call    cs:__imp_SetLastError
0x180023cbb  mov     ebx, r15d
0x180023cbe  jmp     short loc_180023D32
0x180023cc0  mov     r15d, [rbp+7F0h+var_85C]
0x180023cc4  cmp     r15d, 63616D70h
0x180023ccb  jz      loc_180024149
0x180023cd1  cmp     r15d, 676D6D70h
0x180023cd8  jz      loc_180024149
0x180023cde  cmp     ebx, r8d
0x180023ce1  jnz     loc_180024149
0x180023ce7  lea     rax, [rbp+7F0h+var_260]
0x180023cee  mov     rcx, rdi; pDeviceName
0x180023cf1  lea     r8, [rbp+7F0h+var_470]; unsigned __int16 *
0x180023cf8  mov     [rsp+980h+var_960], rax; unsigned __int16 *
0x180023cfd  call    ?GetDefaultDeviceProfileInDefaultScope@@YAJPEBGIPEAGI1@Z; GetDefaultDeviceProfileInDefaultScope(ushort const *,uint,ushort *,uint,ushort *)
0x180023d02  test    eax, eax
0x180023d04  jns     loc_180024149
0x180023d0a  mov     ecx, eax
0x180023d0c  lea     rsi, aGetdefaultdevi_0; "GetDefaultDeviceProfile Failed: 0x%08x"...
0x180023d13  and     ecx, 1FFF0000h
0x180023d19  cmp     ecx, 70000h
0x180023d1f  jnz     short loc_180023D24
0x180023d21  movzx   eax, ax
0x180023d24  mov     ecx, eax; dwErrCode
0x180023d26  call    cs:__imp_SetLastError
0x180023d2c  mov     ebx, [rbp+7F0h+var_86C]
0x180023d2f  xor     r15d, r15d
0x180023d32  mov     r14d, [rbp+7F0h+var_870]
0x180023d36  lea     rax, [rbp+7F0h+var_848]
0x180023d3a  mov     [rbp+7F0h+var_838], r15d
0x180023d3e  mov     [rsp+980h+var_900], rax; enum DmpDeviceType *
0x180023d46  lea     r9, [rbp+7F0h+lpMem]; unsigned __int16 **
0x180023d4a  lea     rax, [rbp+7F0h+var_7B8]
0x180023d4e  mov     [rbp+7F0h+lpMem], r15
0x180023d52  mov     [rsp+980h+var_908], rax; unsigned __int16 **
0x180023d57  lea     r8, [rbp+7F0h+var_740]; struct _SYSTEMTIME *
0x180023d5e  lea     rax, [rbp+7F0h+var_7F0]
0x180023d62  mov     [rbp+7F0h+var_830], r15
0x180023d66  mov     [rsp+980h+var_910], rax; unsigned __int16 **
0x180023d6b  lea     rdx, [rbp+7F0h+var_838]; unsigned int *
0x180023d6f  lea     rax, [rbp+7F0h+var_7F8]
0x180023d73  mov     [rbp+7F0h+var_828], r15
0x180023d77  mov     [rsp+980h+var_918], rax; unsigned __int16 **
0x180023d7c  xorps   xmm0, xmm0
0x180023d7f  lea     rax, [rbp+7F0h+var_844]
0x180023d83  mov     [rbp+7F0h+var_818], r15
0x180023d87  mov     [rsp+980h+var_920], rax; unsigned int *
0x180023d8c  mov     rcx, r12; unsigned __int16 *
0x180023d8f  lea     rax, [rbp+7F0h+var_840]
0x180023d93  mov     [rbp+7F0h+var_810], r15
0x180023d97  mov     [rsp+980h+var_928], rax; enum COLORPROFILESUBTYPE *
0x180023d9c  lea     rax, [rbp+7F0h+var_83C]
0x180023da0  mov     [rsp+980h+var_930], rax; enum COLORPROFILETYPE *
0x180023da5  lea     rax, [rbp+7F0h+var_800]
0x180023da9  mov     [rsp+980h+var_938], rax; unsigned __int16 **
0x180023dae  lea     rax, [rbp+7F0h+var_808]
0x180023db2  mov     [rsp+980h+var_940], rax; unsigned __int16 **
0x180023db7  lea     rax, [rbp+7F0h+var_810]
0x180023dbb  mov     [rsp+980h+var_948], rax; unsigned __int16 **
0x180023dc0  lea     rax, [rbp+7F0h+var_818]
0x180023dc4  mov     [rsp+980h+var_950], rax; unsigned __int16 **
0x180023dc9  lea     rax, [rbp+7F0h+var_828]
0x180023dcd  mov     [rsp+980h+var_958], rax; unsigned __int16 **
0x180023dd2  lea     rax, [rbp+7F0h+var_830]
0x180023dd6  mov     [rsp+980h+var_960], rax; unsigned __int16 **
0x180023ddb  movups  xmmword ptr [rbp+7F0h+var_740.wYear], xmm0
0x180023de2  mov     [rbp+7F0h+var_808], r15
0x180023de6  mov     [rbp+7F0h+var_800], r15
0x180023dea  mov     [rbp+7F0h+var_83C], r15d
0x180023dee  mov     [rbp+7F0h+var_840], r15d
0x180023df2  mov     [rbp+7F0h+var_844], r15d
0x180023df6  mov     [rbp+7F0h+var_7F8], r15
0x180023dfa  mov     [rbp+7F0h+var_7F0], r15
0x180023dfe  mov     [rbp+7F0h+var_7B8], r15
0x180023e02  mov     [rbp+7F0h+var_848], r15d
0x180023e06  call    ?CreatePropertiesFromProfile@@YAJPEBGPEAKPEAU_SYSTEMTIME@@PEAPEAG333333PEAW4COLORPROFILETYPE@@PEAW4COLORPROFILESUBTYPE@@1333PEAW4DmpDeviceType@@@Z; CreatePropertiesFromProfile(ushort const *,ulong *,_SYSTEMTIME *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,COLORPROFILETYPE *,COLORPROFILESUBTYPE *,ulong *,ushort * *,ushort * *,ushort * *,DmpDeviceType *)
0x180023e0b  mov     eax, cs:dword_18009E080
0x180023e11  cmp     eax, 5
0x180023e14  jbe     loc_180024092
0x180023e1a  mov     rdx, 400000000000h
0x180023e24  lea     rcx, dword_18009E080
0x180023e2b  call    _tlgKeywordOn
0x180023e30  test    al, al
0x180023e32  jz      loc_180024092
0x180023e38  mov     eax, [rbp+7F0h+var_848]
0x180023e3b  mov     [rbp+7F0h+var_7CC], eax
0x180023e3e  mov     rax, [rbp+7F0h+var_7B8]
0x180023e42  mov     [rbp+7F0h+var_7B0], rax
0x180023e46  mov     rax, [rbp+7F0h+var_7F0]
0x180023e4a  mov     [rbp+7F0h+var_7A8], rax
0x180023e4e  mov     rax, [rbp+7F0h+var_7F8]
0x180023e52  mov     [rbp+7F0h+var_7A0], rax
0x180023e56  mov     eax, [rbp+7F0h+var_844]
0x180023e59  mov     [rbp+7F0h+var_7C8], eax
0x180023e5c  mov     eax, [rbp+7F0h+var_840]
0x180023e5f  mov     [rbp+7F0h+var_7C4], eax
0x180023e62  mov     eax, [rbp+7F0h+var_83C]
0x180023e65  mov     [rbp+7F0h+var_7C0], eax
0x180023e68  mov     rax, [rbp+7F0h+var_800]
0x180023e6c  mov     [rbp+7F0h+var_798], rax
0x180023e70  mov     rax, [rbp+7F0h+var_808]
0x180023e74  mov     [rbp+7F0h+var_790], rax
0x180023e78  mov     rax, [rbp+7F0h+var_810]
0x180023e7c  mov     [rbp+7F0h+var_788], rax
0x180023e80  mov     rax, [rbp+7F0h+var_818]
0x180023e84  mov     [rbp+7F0h+var_780], rax
0x180023e88  mov     rax, [rbp+7F0h+var_828]
0x180023e8c  mov     [rbp+7F0h+var_778], rax
0x180023e90  mov     rax, [rbp+7F0h+var_830]
0x180023e94  mov     [rbp+7F0h+var_770], rax
0x180023e9b  mov     rax, [rbp+7F0h+lpMem]
0x180023e9f  mov     [rbp+7F0h+var_768], rax
0x180023ea6  movzx   eax, [rbp+7F0h+var_740.wSecond]
0x180023ead  mov     word ptr [rbp+7F0h+var_858], ax
0x180023eb1  movzx   eax, [rbp+7F0h+var_740.wMinute]
0x180023eb8  mov     word ptr [rbp+7F0h+var_850], ax
0x180023ebc  movzx   eax, [rbp+7F0h+var_740.wHour]
0x180023ec3  mov     word ptr [rbp+7F0h+var_860], ax
0x180023ec7  movzx   eax, [rbp+7F0h+var_740.wDay]
0x180023ece  mov     word ptr [rbp+7F0h+var_85C], ax
0x180023ed2  movzx   eax, [rbp+7F0h+var_740.wMonth]
0x180023ed9  mov     word ptr [rbp+7F0h+var_86C], ax
0x180023edd  movzx   eax, [rbp+7F0h+var_740.wYear]
0x180023ee4  mov     word ptr [rbp+7F0h+var_870], ax
0x180023ee8  mov     eax, [rbp+7F0h+var_838]
0x180023eeb  mov     [rbp+7F0h+var_7BC], eax
0x180023eee  lea     rax, [rbp+7F0h+var_470]
0x180023ef5  mov     [rbp+7F0h+var_760], rax
0x180023efc  mov     eax, [rbp+7F0h+arg_20]
0x180023f02  mov     [rbp+7F0h+var_7E8], eax
0x180023f05  mov     eax, [rbp+7F0h+var_868]
0x180023f08  mov     [rbp+7F0h+var_7D0], eax
0x180023f0b  mov     [rbp+7F0h+var_758], r13
0x180023f12  mov     [rbp+7F0h+var_7E4], r14d
0x180023f16  mov     [rbp+7F0h+var_750], rdi
0x180023f1d  mov     [rbp+7F0h+var_748], rsi
0x180023f24  call    cs:__imp_GetLastError
0x180023f2a  mov     [rbp+7F0h+var_7E0], eax
0x180023f2d  lea     rax, [rbp+7F0h+var_7CC]
0x180023f31  mov     [rsp+980h+var_878], rax
0x180023f39  lea     rax, [rbp+7F0h+var_7B0]
0x180023f3d  mov     [rsp+980h+var_880], rax
0x180023f45  lea     rax, [rbp+7F0h+var_7A8]
0x180023f49  mov     [rsp+980h+var_888], rax
0x180023f51  lea     rax, [rbp+7F0h+var_7A0]
0x180023f55  mov     [rsp+980h+var_890], rax
0x180023f5d  lea     rax, [rbp+7F0h+var_7C8]
0x180023f61  mov     [rsp+980h+var_898], rax
0x180023f69  lea     rax, [rbp+7F0h+var_7C4]
0x180023f6d  mov     [rsp+980h+var_8A0], rax
0x180023f75  lea     rax, [rbp+7F0h+var_7C0]
0x180023f79  mov     [rsp+980h+var_8A8], rax
0x180023f81  lea     rax, [rbp+7F0h+var_798]
0x180023f85  mov     [rsp+980h+var_8B0], rax
0x180023f8d  lea     rax, [rbp+7F0h+var_790]
0x180023f91  mov     [rsp+980h+var_8B8], rax
0x180023f99  lea     rax, [rbp+7F0h+var_788]
0x180023f9d  mov     [rsp+980h+var_8C0], rax
0x180023fa5  lea     rax, [rbp+7F0h+var_780]
0x180023fa9  mov     [rsp+980h+var_8C8], rax
0x180023fb1  lea     rax, [rbp+7F0h+var_778]
0x180023fb5  mov     [rsp+980h+var_8D0], rax
0x180023fbd  lea     rax, [rbp+7F0h+var_770]
0x180023fc4  mov     [rsp+980h+var_8D8], rax
0x180023fcc  mov     dword ptr [rbp+7F0h+var_7D8], ebx
  ... truncated ...
```
