# InternalDisassociateColorProfileFromDevice(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ushort const *,int,int)

- ea: `0x1800412a4`
- end: `0x1800417cb`
- name: `?InternalDisassociateColorProfileFromDevice@@YAHW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBG1HH@Z`
- size: `1319`
- prototype: `int(enum WCS_PROFILE_MANAGEMENT_SCOPE, const unsigned __int16 *, const unsigned __int16 *, int, int)`
- caller_count: `5`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x180044370`
- `0x180044470`
- `0x180044cf0`
- `0x180045500`
- `0x18004d650`

## callees

- `0x1800022a0`
- `0x180008bf0`
- `0x180008cc0`
- `0x18001b3a8`
- `0x18001ffe0`
- `0x180023a4c`
- `0x180029f14`
- `0x18002af3c`
- `0x18002e5f0`
- `0x18002f2f4`
- `0x18003eb70`
- `0x18003ec6c`
- `0x18003f20c`
- `0x180040d94`
- `0x1800412a4`
- `0x180042334`
- `0x1800427b8`
- `0x18004344c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180041789`
- `ntdll!EtwEventWrite` at `0x180041789`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041373`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004145e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800414cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041676`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041705`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041799`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041373`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004145e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800414cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041676`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041705`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041531`

## string_xrefs

- `0x180041369`: `Could not parse file name from profile path %s\n`
- `0x180041395`: `Could not get color directory\n`
- `0x180041680`: `RemoveProfileFromAssociatedProfileList failed: 0x%08x\n`
- `0x1800416f4`: `AttemptRefreshCalibrationIfProfileChanged Failed: 0x%08x\n`

## pseudocode

```c
__int64 __fastcall InternalDisassociateColorProfileFromDevice(
        enum WCS_PROFILE_MANAGEMENT_SCOPE a1,
        const unsigned __int16 *a2,
        WCHAR *a3,
        int a4,
        int a5)
{
  int v8; // r14d
  unsigned int v9; // ebx
  const unsigned __int16 *v10; // r12
  const OLECHAR *v11; // rdi
  DWORD v12; // ecx
  __int64 v13; // r15
  __int64 v14; // rax
  int v15; // r8d
  DWORD phClass; // ebx
  unsigned int v17; // edx
  unsigned int v18; // r9d
  unsigned int v19; // r13d
  int DefaultDeviceProfileInDefaultScope; // eax
  DWORD v21; // ecx
  DWORD LastError; // eax
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  enum WCS_PROFILE_MANAGEMENT_SCOPE v27; // ecx
  unsigned int v28; // eax
  unsigned int v29; // r12d
  DWORD v30; // ecx
  bool v31; // zf
  int refreshed; // eax
  DWORD v33; // ecx
  __int64 v34; // rax
  WCHAR *v35; // [rsp+70h] [rbp-90h] BYREF
  enum WCS_PROFILE_MANAGEMENT_SCOPE v36; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v37; // [rsp+80h] [rbp-80h] BYREF
  const OLECHAR *v38; // [rsp+88h] [rbp-78h] BYREF
  int v39; // [rsp+90h] [rbp-70h] BYREF
  int v40; // [rsp+94h] [rbp-6Ch] BYREF
  int v41; // [rsp+98h] [rbp-68h] BYREF
  DWORD pcbNeeded; // [rsp+A0h] [rbp-60h] BYREF
  const OLECHAR *FilenameFromPath; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-50h] BYREF
  const OLECHAR *v45; // [rsp+B8h] [rbp-48h] BYREF
  struct tagPROFILEHEADER v46; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v47; // [rsp+140h] [rbp+40h] BYREF
  int v48; // [rsp+148h] [rbp+48h]
  int v49; // [rsp+14Ch] [rbp+4Ch]
  WCHAR *v50; // [rsp+150h] [rbp+50h]
  int v51; // [rsp+158h] [rbp+58h]
  int v52; // [rsp+15Ch] [rbp+5Ch]
  enum WCS_PROFILE_MANAGEMENT_SCOPE *v53; // [rsp+160h] [rbp+60h]
  __int64 v54; // [rsp+168h] [rbp+68h]
  unsigned __int16 v55[264]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v56[264]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int16 v57[264]; // [rsp+590h] [rbp+490h] BYREF

  v44 = (__int64)a2;
  v36 = a1;
  LODWORD(v35) = a4;
  v8 = a4;
  memset_0(&v46, 0, sizeof(v46));
  pcbNeeded = 0;
  v37 = 0;
  v40 = 0;
  memset_0(v56, 0, 0x208u);
  memset_0(v57, 0, 0x208u);
  if ( !a2 || !a3 || (unsigned int)a1 > WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER )
  {
    SetLastError(0x57u);
    return 0;
  }
  v9 = 0;
  LODWORD(v38) = 0;
  FilenameFromPath = GetFilenameFromPath(a2);
  v10 = FilenameFromPath;
  if ( FilenameFromPath )
  {
    pcbNeeded = 520;
    if ( !InternalGetColorDirectory(0, v55, &pcbNeeded) )
    {
      v11 = L"Could not get color directory\n";
      goto LABEL_32;
    }
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( v55[v14] );
    if ( v55[v14 - 1] != 92 && (v15 = StringCchCatW(v55, 0x104u, gszBackslash), v15 < 0)
      || (v15 = StringCchCatW(v55, 0x104u, v10), v15 < 0) )
    {
      v12 = (unsigned __int16)v15;
      v11 = L"Input buffer is not big enough\n";
      if ( (v15 & 0x1FFF0000) != 0x70000 )
        v12 = v15;
      goto LABEL_6;
    }
    if ( GetProfileInfo(v55, 0, &v37, &v46, 0) )
    {
      phClass = v46.phClass;
      if ( v46.phClass == 1835955314 )
        phClass = 1936744803;
    }
    else
    {
      phClass = 1936744803;
    }
    if ( (unsigned int)IsLegacyColorManagedShimAppliedOnDeviceClass(phClass) )
    {
      v11 = L"DisassociateColorProfileWithDevice is not supported as the legacy color managed shim is enabled\n";
      SetLastError(0x32u);
      v9 = 0;
LABEL_31:
      v8 = (int)v35;
      goto LABEL_32;
    }
    v19 = v37;
    if ( v37 != 1667329392 && v37 != 1735224688 && phClass == 1936744803 )
    {
      DefaultDeviceProfileInDefaultScope = GetDefaultDeviceProfileInDefaultScope(a3, v17, v56, v18, v57);
      v21 = DefaultDeviceProfileInDefaultScope;
      if ( DefaultDeviceProfileInDefaultScope < 0 )
      {
        v11 = L"GetDefaultDeviceProfile Failed: %d\n";
        if ( (DefaultDeviceProfileInDefaultScope & 0x1FFF0000) == 0x70000 )
          v21 = (unsigned __int16)DefaultDeviceProfileInDefaultScope;
        SetLastError(v21);
        goto LABEL_30;
      }
    }
    v27 = v36;
    v11 = &word_1800884E0;
    if ( v36 == WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER && (_DWORD)v35 )
    {
      v39 = 0;
      if ( !(unsigned int)InternalGetUsePerUserProfiles(a3, phClass, &v39)
        || !v39
        && (!(unsigned int)CloneSystemWideProfileList(a3, phClass)
         || !(unsigned int)SaveSystemWideProfileListSnapshot(a3, phClass)
         || (v41 = 1, !(unsigned int)SetDeviceData(WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, a3, &v41, 4u))) )
      {
LABEL_30:
        v9 = (unsigned int)v38;
        goto LABEL_31;
      }
      v27 = v36;
    }
    v28 = RemoveProfileFromAssociatedProfileList(v27, a3, phClass, v10, &v37, a5, &v40);
    v29 = v28;
    if ( !v28 )
    {
      if ( v40 )
        ChangeICMSetting(v36, a3, 1);
      if ( v19 == 1667329392
        || v19 == 1735224688
        || phClass != 1936744803
        || (refreshed = AttemptRefreshCalibrationIfProfileChanged(a3, v56, v57, 1u), v33 = refreshed, refreshed >= 0) )
      {
        v9 = 1;
        v34 = -1;
        do
          ++v34;
        while ( *(_WORD *)(v44 + 2 * v34) );
        v47 = v44;
        v48 = 2 * v34 + 2;
        v49 = 0;
        do
          ++v13;
        while ( a3[v13] );
        v51 = 2 * v13 + 2;
        v50 = a3;
        v53 = &v36;
        v52 = 0;
        v54 = 4;
        EtwEventWrite(g_etwHandle, DISASSOCIATE_PROFILE, 3, &v47);
      }
      else
      {
        v11 = L"AttemptRefreshCalibrationIfProfileChanged Failed: 0x%08x\n";
        if ( (refreshed & 0x1FFF0000) == 0x70000 )
          v33 = (unsigned __int16)refreshed;
        SetLastError(v33);
        v9 = 0;
      }
      v10 = FilenameFromPath;
      goto LABEL_31;
    }
    v30 = v28;
    if ( v28 == 2 )
      v30 = 2015;
    SetLastError(v30);
    v31 = v29 == 2;
    v10 = FilenameFromPath;
    v11 = L"Trying to disassociate a profile that is not associated %s\n";
    if ( !v31 )
      v11 = L"RemoveProfileFromAssociatedProfileList failed: 0x%08x\n";
    goto LABEL_30;
  }
  v11 = L"Could not parse file name from profile path %s\n";
  v12 = 87;
LABEL_6:
  SetLastError(v12);
LABEL_32:
  if ( (unsigned int)dword_18009E080 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x200000000000LL) )
    {
      v44 = 0x2000000;
      FilenameFromPath = v56;
      v40 = v36;
      v38 = v10;
      v41 = v8;
      v35 = a3;
      v45 = v11;
      LastError = GetLastError();
      v37 = v9;
      v39 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v23,
        (__int64)&byte_180090CC7,
        v24,
        v25,
        (__int64)&v37,
        (__int64)&v39,
        &v45,
        (__int64)&v40,
        (const OLECHAR **)&v35,
        (__int64)&v41,
        &v38,
        &FilenameFromPath,
        (__int64)&v44);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800412a4  mov     [rsp-8+arg_18], rbx
0x1800412a9  push    rbp
0x1800412aa  push    rsi
0x1800412ab  push    rdi
0x1800412ac  push    r12
0x1800412ae  push    r13
0x1800412b0  push    r14
0x1800412b2  push    r15
0x1800412b4  lea     rbp, [rsp-6B0h]
0x1800412bc  sub     rsp, 7B0h
0x1800412c3  mov     rax, cs:__security_cookie
0x1800412ca  xor     rax, rsp
0x1800412cd  mov     [rbp+6E0h+var_40], rax
0x1800412d4  mov     rsi, r8
0x1800412d7  mov     [rbp+6E0h+var_730], rdx
0x1800412db  mov     rdi, rdx
0x1800412de  mov     [rsp+7E0h+var_768], ecx
0x1800412e2  mov     ebx, ecx
0x1800412e4  mov     dword ptr [rsp+7E0h+var_770], r9d
0x1800412e9  xor     edx, edx; Val
0x1800412eb  lea     rcx, [rbp+6E0h+var_720]; void *
0x1800412ef  mov     r8d, 80h; Size
0x1800412f5  mov     r14d, r9d
0x1800412f8  call    memset_0
0x1800412fd  xor     r13d, r13d
0x180041300  lea     rcx, [rbp+6E0h+var_460]; void *
0x180041307  mov     r15d, 208h
0x18004130d  mov     [rbp+6E0h+pcbNeeded], r13d
0x180041311  mov     r8d, r15d; Size
0x180041314  mov     [rbp+6E0h+var_760], r13d
0x180041318  xor     edx, edx; Val
0x18004131a  mov     [rbp+6E0h+var_74C], r13d
0x18004131e  call    memset_0
0x180041323  mov     r8d, r15d; Size
0x180041326  lea     rcx, [rbp+6E0h+var_250]; void *
0x18004132d  xor     edx, edx; Val
0x18004132f  call    memset_0
0x180041334  test    rdi, rdi
0x180041337  jz      loc_180041794
0x18004133d  test    rsi, rsi
0x180041340  jz      loc_180041794
0x180041346  cmp     ebx, 1
0x180041349  ja      loc_180041794
0x18004134f  mov     ebx, r13d
0x180041352  mov     rcx, rdi; lpStringSource
0x180041355  mov     dword ptr [rbp+6E0h+var_758], ebx
0x180041358  call    GetFilenameFromPath
0x18004135d  mov     [rbp+6E0h+var_738], rax
0x180041361  mov     r12, rax
0x180041364  test    rax, rax
0x180041367  jnz     short loc_18004137E
0x180041369  lea     rdi, aCouldNotParseF; "Could not parse file name from profile "...
0x180041370  lea     ecx, [rax+57h]; dwErrCode
0x180041373  call    cs:__imp_SetLastError
0x180041379  jmp     loc_1800414D9
0x18004137e  lea     r8, [rbp+6E0h+pcbNeeded]; pcbNeeded
0x180041382  mov     [rbp+6E0h+pcbNeeded], r15d
0x180041386  lea     rdx, [rbp+6E0h+var_670]; unsigned __int16 *
0x18004138a  xor     ecx, ecx; pName
0x18004138c  call    ?InternalGetColorDirectory@@YAHPEBGPEAGPEAK@Z; InternalGetColorDirectory(ushort const *,ushort *,ulong *)
0x180041391  test    eax, eax
0x180041393  jnz     short loc_1800413A1
0x180041395  lea     rdi, aCouldNotGetCol; "Could not get color directory\n"
0x18004139c  jmp     loc_1800414D9
0x1800413a1  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800413a5  lea     rcx, [rbp+6E0h+var_670]
0x1800413a9  mov     rax, r15
0x1800413ac  inc     rax
0x1800413af  cmp     [rcx+rax*2], r13w
0x1800413b4  jnz     short loc_1800413AC
0x1800413b6  cmp     [rbp+rax*2+6E0h+var_672], 5Ch ; '\'
0x1800413bc  mov     edi, 104h
0x1800413c1  jz      short loc_1800413DC
0x1800413c3  lea     r8, gszBackslash; "\\"
0x1800413ca  mov     edx, edi; unsigned __int64
0x1800413cc  lea     rcx, [rbp+6E0h+var_670]; unsigned __int16 *
0x1800413d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800413d5  mov     r8d, eax
0x1800413d8  test    eax, eax
0x1800413da  js      short loc_1800413F2
0x1800413dc  mov     r8, r12; unsigned __int16 *
0x1800413df  lea     rcx, [rbp+6E0h+var_670]; unsigned __int16 *
0x1800413e3  mov     rdx, rdi; unsigned __int64
0x1800413e6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800413eb  mov     r8d, eax
0x1800413ee  test    eax, eax
0x1800413f0  jns     short loc_180041413
0x1800413f2  mov     eax, r8d
0x1800413f5  movzx   ecx, r8w
0x1800413f9  and     eax, 1FFF0000h
0x1800413fe  lea     rdi, aInputBufferIsN; "Input buffer is not big enough\n"
0x180041405  cmp     eax, 70000h
0x18004140a  cmovnz  ecx, r8d
0x18004140e  jmp     loc_180041373
0x180041413  lea     r9, [rbp+6E0h+var_720]; struct tagPROFILEHEADER *
0x180041417  mov     [rsp+7E0h+var_7C0], r13; void **
0x18004141c  lea     r8, [rbp+6E0h+var_760]; unsigned int *
0x180041420  xor     edx, edx; enum COLORPROFILETYPE *
0x180041422  lea     rcx, [rbp+6E0h+var_670]; unsigned __int16 *
0x180041426  call    ?GetProfileInfo@@YAHPEBGPEAW4COLORPROFILETYPE@@PEAKPEAUtagPROFILEHEADER@@PEAPEAX@Z; GetProfileInfo(ushort const *,COLORPROFILETYPE *,ulong *,tagPROFILEHEADER *,void * *)
0x18004142b  mov     r14d, 73706163h
0x180041431  test    eax, eax
0x180041433  jnz     short loc_18004143A
0x180041435  mov     ebx, r14d
0x180041438  jmp     short loc_180041447
0x18004143a  mov     ebx, [rbp+6E0h+var_720.phClass]
0x18004143d  cmp     ebx, 6D6E7472h
0x180041443  cmovz   ebx, r14d
0x180041447  mov     ecx, ebx
0x180041449  call    IsLegacyColorManagedShimAppliedOnDeviceClass
0x18004144e  test    eax, eax
0x180041450  jz      short loc_180041469
0x180041452  mov     ecx, 32h ; '2'; dwErrCode
0x180041457  lea     rdi, aDisassociateco_1; "DisassociateColorProfileWithDevice is n"...
0x18004145e  call    cs:__imp_SetLastError
0x180041464  mov     ebx, r13d
0x180041467  jmp     short loc_1800414D4
0x180041469  mov     r13d, [rbp+6E0h+var_760]
0x18004146d  cmp     r13d, 63616D70h
0x180041474  jz      loc_1800415A2
0x18004147a  cmp     r13d, 676D6D70h
0x180041481  jz      loc_1800415A2
0x180041487  cmp     ebx, r14d
0x18004148a  jnz     loc_1800415A2
0x180041490  lea     rax, [rbp+6E0h+var_250]
0x180041497  mov     rcx, rsi; pDeviceName
0x18004149a  lea     r8, [rbp+6E0h+var_460]; unsigned __int16 *
0x1800414a1  mov     [rsp+7E0h+var_7C0], rax; unsigned __int16 *
0x1800414a6  call    ?GetDefaultDeviceProfileInDefaultScope@@YAJPEBGIPEAGI1@Z; GetDefaultDeviceProfileInDefaultScope(ushort const *,uint,ushort *,uint,ushort *)
0x1800414ab  mov     ecx, eax
0x1800414ad  test    eax, eax
0x1800414af  jns     loc_1800415A2
0x1800414b5  and     eax, 1FFF0000h
0x1800414ba  lea     rdi, aGetdefaultdevi; "GetDefaultDeviceProfile Failed: %d\n"
0x1800414c1  cmp     eax, 70000h
0x1800414c6  jnz     short loc_1800414CB
0x1800414c8  movzx   ecx, cx; dwErrCode
0x1800414cb  call    cs:__imp_SetLastError
0x1800414d1  mov     ebx, dword ptr [rbp+6E0h+var_758]
0x1800414d4  mov     r14d, dword ptr [rsp+7E0h+var_770]
0x1800414d9  mov     eax, cs:dword_18009E080
0x1800414df  cmp     eax, 5
0x1800414e2  jbe     loc_18004159B
0x1800414e8  mov     rdx, 200000000000h
0x1800414f2  lea     rcx, dword_18009E080
0x1800414f9  call    _tlgKeywordOn
0x1800414fe  test    al, al
0x180041500  jz      loc_18004159B
0x180041506  lea     rax, [rbp+6E0h+var_460]
0x18004150d  mov     [rbp+6E0h+var_730], 2000000h
0x180041515  mov     [rbp+6E0h+var_738], rax
0x180041519  mov     eax, [rsp+7E0h+var_768]
0x18004151d  mov     [rbp+6E0h+var_74C], eax
0x180041520  mov     [rbp+6E0h+var_758], r12
0x180041524  mov     [rbp+6E0h+var_748], r14d
0x180041528  mov     [rsp+7E0h+var_770], rsi
0x18004152d  mov     [rbp+6E0h+var_728], rdi
0x180041531  call    cs:__imp_GetLastError
0x180041537  lea     rdx, byte_180090CC7
0x18004153e  mov     [rbp+6E0h+var_760], ebx
0x180041541  mov     [rbp+6E0h+var_750], eax
0x180041544  lea     rax, [rbp+6E0h+var_730]
0x180041548  mov     [rsp+7E0h+var_780], rax
0x18004154d  lea     rax, [rbp+6E0h+var_738]
0x180041551  mov     [rsp+7E0h+var_788], rax
0x180041556  lea     rax, [rbp+6E0h+var_758]
0x18004155a  mov     [rsp+7E0h+var_790], rax
0x18004155f  lea     rax, [rbp+6E0h+var_748]
0x180041563  mov     [rsp+7E0h+var_798], rax
0x180041568  lea     rax, [rsp+7E0h+var_770]
0x18004156d  mov     [rsp+7E0h+var_7A0], rax
0x180041572  lea     rax, [rbp+6E0h+var_74C]
0x180041576  mov     [rsp+7E0h+var_7A8], rax
0x18004157b  lea     rax, [rbp+6E0h+var_728]
0x18004157f  mov     [rsp+7E0h+var_7B0], rax
0x180041584  lea     rax, [rbp+6E0h+var_750]
0x180041588  mov     qword ptr [rsp+7E0h+var_7B8], rax
0x18004158d  lea     rax, [rbp+6E0h+var_760]
0x180041591  mov     [rsp+7E0h+var_7C0], rax
0x180041596  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U1@U2@U1@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@34344AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18004159b  mov     eax, ebx
0x18004159d  jmp     loc_1800417A1
0x1800415a2  mov     ecx, [rsp+7E0h+var_768]
0x1800415a6  lea     rdi, word_1800884E0
0x1800415ad  cmp     ecx, 1
0x1800415b0  jnz     loc_180041638
0x1800415b6  cmp     dword ptr [rsp+7E0h+var_770], 0
0x1800415bb  jz      short loc_180041638
0x1800415bd  lea     r8, [rbp+6E0h+var_750]; int *
0x1800415c1  mov     [rbp+6E0h+var_750], 0
0x1800415c8  mov     edx, ebx; unsigned int
0x1800415ca  mov     rcx, rsi; unsigned __int16 *
0x1800415cd  call    ?InternalGetUsePerUserProfiles@@YAHPEBGKPEAH@Z; InternalGetUsePerUserProfiles(ushort const *,ulong,int *)
0x1800415d2  test    eax, eax
0x1800415d4  jz      loc_1800414D1
0x1800415da  cmp     [rbp+6E0h+var_750], 0
0x1800415de  jnz     short loc_180041634
0x1800415e0  mov     edx, ebx; unsigned int
0x1800415e2  mov     rcx, rsi; unsigned __int16 *
0x1800415e5  call    ?CloneSystemWideProfileList@@YAHPEBGK@Z; CloneSystemWideProfileList(ushort const *,ulong)
0x1800415ea  test    eax, eax
0x1800415ec  jz      loc_1800414D1
0x1800415f2  mov     edx, ebx; unsigned int
0x1800415f4  mov     rcx, rsi; unsigned __int16 *
0x1800415f7  call    ?SaveSystemWideProfileListSnapshot@@YAHPEBGK@Z; SaveSystemWideProfileListSnapshot(ushort const *,ulong)
0x1800415fc  test    eax, eax
0x1800415fe  jz      loc_1800414D1
0x180041604  mov     ecx, 1; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180041609  mov     [rsp+7E0h+var_7B8], 4; unsigned int
0x180041611  lea     rax, [rbp+6E0h+var_748]
0x180041615  mov     [rbp+6E0h+var_748], ecx
0x180041618  mov     r8d, ebx
0x18004161b  mov     [rsp+7E0h+var_7C0], rax; void *
0x180041620  mov     rdx, rsi; unsigned __int16 *
0x180041623  lea     r9d, [rcx+2]
0x180041627  call    SetDeviceData
0x18004162c  test    eax, eax
0x18004162e  jz      loc_1800414D1
0x180041634  mov     ecx, [rsp+7E0h+var_768]; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180041638  lea     rax, [rbp+6E0h+var_74C]
0x18004163c  mov     r9, r12; unsigned __int16 *
0x18004163f  mov     [rsp+7E0h+var_7B0], rax; int *
0x180041644  mov     r8d, ebx; unsigned int
0x180041647  mov     eax, [rbp+6E0h+arg_20]
0x18004164d  mov     rdx, rsi; unsigned __int16 *
0x180041650  mov     [rsp+7E0h+var_7B8], eax; int
0x180041654  lea     rax, [rbp+6E0h+var_760]
0x180041658  mov     [rsp+7E0h+var_7C0], rax; unsigned int *
0x18004165d  call    ?RemoveProfileFromAssociatedProfileList@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGK1PEBKHPEAH@Z; RemoveProfileFromAssociatedProfileList(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,ushort const *,ulong const *,int,int *)
0x180041662  mov     r12d, eax
0x180041665  test    eax, eax
0x180041667  jz      short loc_18004169B
0x180041669  mov     ecx, eax
0x18004166b  mov     eax, 7DFh
0x180041670  cmp     ecx, 2
0x180041673  cmovz   ecx, eax; dwErrCode
0x180041676  call    cs:__imp_SetLastError
0x18004167c  cmp     r12d, 2
0x180041680  lea     rax, aRemoveprofilef; "RemoveProfileFromAssociatedProfileList "...
0x180041687  mov     r12, [rbp+6E0h+var_738]
0x18004168b  lea     rdi, aTryingToDisass; "Trying to disassociate a profile that i"...
0x180041692  cmovnz  rdi, rax
0x180041696  jmp     loc_1800414D1
0x18004169b  cmp     [rbp+6E0h+var_74C], 0
0x18004169f  jz      short loc_1800416B3
0x1800416a1  mov     ecx, [rsp+7E0h+var_768]; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x1800416a5  mov     r8d, 1; unsigned int
0x1800416ab  mov     rdx, rsi; unsigned __int16 *
0x1800416ae  call    ?ChangeICMSetting@@YAXW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGK@Z; ChangeICMSetting(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong)
0x1800416b3  cmp     r13d, 63616D70h
0x1800416ba  jz      short loc_180041717
0x1800416bc  cmp     r13d, 676D6D70h
0x1800416c3  jz      short loc_180041717
0x1800416c5  cmp     ebx, r14d
0x1800416c8  jnz     short loc_180041717
0x1800416ca  mov     r9d, 1; int
0x1800416d0  lea     r8, [rbp+6E0h+var_250]; unsigned __int16 *
0x1800416d7  lea     rdx, [rbp+6E0h+var_460]; unsigned __int16 *
0x1800416de  mov     rcx, rsi; lpString1
0x1800416e1  call    ?AttemptRefreshCalibrationIfProfileChanged@@YAJPEBG00H@Z; AttemptRefreshCalibrationIfProfileChanged(ushort const *,ushort const *,ushort const *,int)
0x1800416e6  xor     r13d, r13d
0x1800416e9  mov     ecx, eax
0x1800416eb  test    eax, eax
0x1800416ed  jns     short loc_18004171A
0x1800416ef  and     eax, 1FFF0000h
0x1800416f4  lea     rdi, aAttemptrefresh_0; "AttemptRefreshCalibrationIfProfileChang"...
0x1800416fb  cmp     eax, 70000h
0x180041700  jnz     short loc_180041705
0x180041702  movzx   ecx, cx; dwErrCode
0x180041705  call    cs:__imp_SetLastError
0x18004170b  mov     ebx, r13d
0x18004170e  mov     r12, [rbp+6E0h+var_738]
0x180041712  jmp     loc_1800414D4
0x180041717  xor     r13d, r13d
0x18004171a  mov     ebx, 1
0x18004171f  mov     rcx, [rbp+6E0h+var_730]
0x180041723  mov     rax, r15
0x180041726  inc     rax
0x180041729  cmp     [rcx+rax*2], r13w
0x18004172e  jnz     short loc_180041726
0x180041730  lea     rax, ds:2[rax*2]
0x180041738  mov     [rbp+6E0h+var_6A0], rcx
0x18004173c  mov     [rbp+6E0h+var_698], eax
0x18004173f  mov     [rbp+6E0h+var_694], r13d
0x180041743  inc     r15
0x180041746  cmp     [rsi+r15*2], r13w
0x18004174b  jnz     short loc_180041743
0x18004174d  mov     rcx, cs:g_etwHandle
0x180041754  lea     rax, ds:2[r15*2]
0x18004175c  mov     [rbp+6E0h+var_688], eax
0x18004175f  lea     r9, [rbp+6E0h+var_6A0]
0x180041763  lea     rax, [rsp+7E0h+var_768]
0x180041768  mov     [rbp+6E0h+var_690], rsi
0x18004176c  mov     r8d, 3
0x180041772  mov     [rbp+6E0h+var_680], rax
0x180041776  lea     rdx, DISASSOCIATE_PROFILE
0x18004177d  mov     [rbp+6E0h+var_684], r13d
0x180041781  mov     qword ptr [rbp+68h], 4
0x180041789  call    cs:__imp_EtwEventWrite
0x18004178f  jmp     loc_18004170E
  ... truncated ...
```
