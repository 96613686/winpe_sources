# WcsSetUsePerUserProfiles

- ea: `0x180045690`
- end: `0x180045a1d`
- name: `WcsSetUsePerUserProfiles`
- size: `909`
- prototype: `BOOL __stdcall(LPCWSTR pDeviceName, DWORD dwDeviceClass, BOOL usePerUserProfiles)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting`

## callees

- `0x180001750`
- `0x180002500`
- `0x18001b3a8`
- `0x180023a4c`
- `0x18002af3c`
- `0x18002e5f0`
- `0x18002f2f4`
- `0x18003eb70`
- `0x18003f20c`
- `0x180040d94`
- `0x1800427b8`
- `0x18004344c`
- `0x180045690`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180045936`
- `ntdll!EtwEventWrite` at `0x180045936`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045765`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800458e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045765`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800458e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004598f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004598f`

## string_xrefs

- `0x1800458c8`: `AttemptRefreshCalibrationIfProfileChanged Failed: 0x%08x\n`

## pseudocode

```c
BOOL __stdcall WcsSetUsePerUserProfiles(LPCWSTR pDeviceName, DWORD dwDeviceClass, BOOL usePerUserProfiles)
{
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  const OLECHAR *v8; // r14
  DWORD v9; // ecx
  int v10; // edi
  unsigned int v11; // r9d
  BOOL v12; // eax
  _BOOL8 v13; // rdx
  signed int DefaultDeviceProfileInDefaultScope; // eax
  int v15; // eax
  __int64 v16; // rax
  DWORD LastError; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  DWORD v22; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v23; // [rsp+68h] [rbp-98h] BYREF
  int v24; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD v25; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR v26; // [rsp+78h] [rbp-88h] BYREF
  __int64 v27; // [rsp+80h] [rbp-80h] BYREF
  const OLECHAR *v28; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR v29; // [rsp+90h] [rbp-70h] BYREF
  const OLECHAR *v30; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR v31; // [rsp+A0h] [rbp-60h] BYREF
  int v32; // [rsp+A8h] [rbp-58h]
  int v33; // [rsp+ACh] [rbp-54h]
  BOOL *v34; // [rsp+B0h] [rbp-50h]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v36[264]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v37[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  BOOL v38; // [rsp+530h] [rbp+430h] BYREF

  v38 = usePerUserProfiles;
  v24 = 0;
  memset_0(v36, 0, 0x208u);
  memset_0(v37, 0, 0x208u);
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x200000000000LL) )
  {
    v23 = v38;
    v22 = dwDeviceClass;
    v26 = pDeviceName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v5,
      (__int64)word_180090F72,
      v6,
      v7,
      &v26,
      (__int64)&v22,
      (__int64)&v23);
  }
  if ( !pDeviceName )
  {
    v8 = L"Invalid pDeviceName parameter to WcsSetUsePerUserProfiles\n";
LABEL_6:
    v9 = 87;
LABEL_7:
    SetLastError(v9);
    v10 = 0;
    goto LABEL_35;
  }
  if ( dwDeviceClass != 1935896178 && dwDeviceClass != 1835955314 && dwDeviceClass != 1886549106 )
  {
    v8 = L"Invalid dwDeviceClass parameter to WcsSetUsePerUserProfiles\n";
    goto LABEL_6;
  }
  if ( (unsigned int)IsLegacyColorManagedShimAppliedOnDeviceClass(dwDeviceClass) )
  {
    v8 = L"SetUsePerUserProfiles is not supported as the legacy color managed shim is enabled\n";
    v9 = 50;
    goto LABEL_7;
  }
  v8 = &word_1800884E0;
  v10 = InternalGetUsePerUserProfiles(pDeviceName, dwDeviceClass, &v24);
  if ( !v10 )
    goto LABEL_35;
  v12 = v38;
  v13 = !v38;
  if ( v13 == (v24 == 0) )
    goto LABEL_32;
  if ( dwDeviceClass == 1835955314 )
  {
    DefaultDeviceProfileInDefaultScope = GetDefaultDeviceProfileInDefaultScope(pDeviceName, v13, v36, v11, v37);
    if ( DefaultDeviceProfileInDefaultScope < 0 )
    {
      v8 = L"GetDefaultDeviceProfile Failed: 0x%08x\n";
      goto LABEL_29;
    }
    v12 = v38;
  }
  if ( !v12 )
    goto LABEL_23;
  v10 = CloneSystemWideProfileList(pDeviceName, dwDeviceClass);
  if ( !v10 )
    goto LABEL_35;
  v15 = 1;
  if ( !v38 )
LABEL_23:
    v15 = 0;
  v22 = v15;
  v10 = SetDeviceData(WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER, (unsigned __int16 *)pDeviceName, &v22, 4u);
  if ( v10 )
  {
    v10 = SaveSystemWideProfileListSnapshot(pDeviceName, dwDeviceClass);
    if ( v10 )
    {
      if ( dwDeviceClass != 1835955314
        || (DefaultDeviceProfileInDefaultScope = AttemptRefreshCalibrationIfProfileChanged(pDeviceName, v36, v37, 0),
            DefaultDeviceProfileInDefaultScope >= 0) )
      {
LABEL_32:
        v16 = -1;
        do
          ++v16;
        while ( pDeviceName[v16] );
        v32 = 2 * v16 + 2;
        v31 = pDeviceName;
        v34 = &v38;
        v33 = 0;
        v35 = 4;
        EtwEventWrite(g_etwHandle, SET_USE_PER_USER_PROFILES, 2, &v31);
        goto LABEL_35;
      }
      v8 = L"AttemptRefreshCalibrationIfProfileChanged Failed: 0x%08x\n";
LABEL_29:
      if ( (DefaultDeviceProfileInDefaultScope & 0x1FFF0000) == 0x70000 )
        DefaultDeviceProfileInDefaultScope = (unsigned __int16)DefaultDeviceProfileInDefaultScope;
      SetLastError(DefaultDeviceProfileInDefaultScope);
      goto LABEL_32;
    }
  }
LABEL_35:
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x200000000000LL) )
  {
    v27 = 0x2000000;
    v28 = v36;
    v22 = v38;
    v23 = dwDeviceClass;
    v29 = pDeviceName;
    v30 = v8;
    LastError = GetLastError();
    LODWORD(v26) = v10;
    v25 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v18,
      (__int64)word_1800913FA,
      v19,
      v20,
      (__int64)&v26,
      (__int64)&v25,
      &v30,
      &v29,
      (__int64)&v23,
      (__int64)&v22,
      &v28,
      (__int64)&v27);
  }
  return v10;
}

```

## disassembly

```asm
0x180045690  mov     [rsp-8+arg_18], rbx
0x180045695  mov     [rsp-8+arg_10], r8d
0x18004569a  push    rbp
0x18004569b  push    rsi
0x18004569c  push    rdi
0x18004569d  push    r14
0x18004569f  push    r15
0x1800456a1  lea     rbp, [rsp-3F0h]
0x1800456a9  sub     rsp, 4F0h
0x1800456b0  mov     rax, cs:__security_cookie
0x1800456b7  xor     rax, rsp
0x1800456ba  mov     [rbp+410h+var_30], rax
0x1800456c1  mov     ebx, edx
0x1800456c3  mov     rsi, rcx
0x1800456c6  mov     edi, 208h
0x1800456cb  lea     rcx, [rbp+410h+var_450]; void *
0x1800456cf  xor     r15d, r15d
0x1800456d2  mov     r8d, edi; Size
0x1800456d5  xor     edx, edx; Val
0x1800456d7  mov     [rsp+510h+var_4A4], r15d
0x1800456dc  call    memset_0
0x1800456e1  mov     r8d, edi; Size
0x1800456e4  lea     rcx, [rbp+410h+var_240]; void *
0x1800456eb  xor     edx, edx; Val
0x1800456ed  call    memset_0
0x1800456f2  mov     eax, cs:dword_18009E080
0x1800456f8  cmp     eax, 5
0x1800456fb  jbe     short loc_180045754
0x1800456fd  mov     rdx, 200000000000h
0x180045707  lea     rcx, dword_18009E080
0x18004570e  call    _tlgKeywordOn
0x180045713  test    al, al
0x180045715  jz      short loc_180045754
0x180045717  mov     eax, [rbp+410h+arg_10]
0x18004571d  lea     rdx, word_180090F72
0x180045724  mov     [rsp+510h+var_4A8], eax
0x180045728  lea     rax, [rsp+510h+var_4A8]
0x18004572d  mov     [rsp+510h+var_4E0], rax
0x180045732  lea     rax, [rsp+510h+var_4B0]
0x180045737  mov     qword ptr [rsp+510h+var_4E8], rax
0x18004573c  lea     rax, [rsp+510h+var_498]
0x180045741  mov     [rsp+510h+var_4F0], rax
0x180045746  mov     [rsp+510h+var_4B0], ebx
0x18004574a  mov     [rsp+510h+var_498], rsi
0x18004574f  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180045754  test    rsi, rsi
0x180045757  jnz     short loc_180045773
0x180045759  lea     r14, aInvalidPdevice; "Invalid pDeviceName parameter to WcsSet"...
0x180045760  mov     ecx, 57h ; 'W'; dwErrCode
0x180045765  call    cs:__imp_SetLastError
0x18004576b  mov     edi, r15d
0x18004576e  jmp     loc_18004593C
0x180045773  cmp     ebx, 73636E72h
0x180045779  jz      short loc_180045794
0x18004577b  cmp     ebx, 6D6E7472h
0x180045781  jz      short loc_180045794
0x180045783  cmp     ebx, 70727472h
0x180045789  jz      short loc_180045794
0x18004578b  lea     r14, aInvalidDwdevic; "Invalid dwDeviceClass parameter to WcsS"...
0x180045792  jmp     short loc_180045760
0x180045794  mov     ecx, ebx
0x180045796  call    IsLegacyColorManagedShimAppliedOnDeviceClass
0x18004579b  test    eax, eax
0x18004579d  jz      short loc_1800457AD
0x18004579f  lea     r14, aSetuseperuserp; "SetUsePerUserProfiles is not supported "...
0x1800457a6  mov     ecx, 32h ; '2'
0x1800457ab  jmp     short loc_180045765
0x1800457ad  lea     r8, [rsp+510h+var_4A4]; int *
0x1800457b2  mov     edx, ebx; unsigned int
0x1800457b4  mov     rcx, rsi; unsigned __int16 *
0x1800457b7  lea     r14, word_1800884E0
0x1800457be  call    ?InternalGetUsePerUserProfiles@@YAHPEBGKPEAH@Z; InternalGetUsePerUserProfiles(ushort const *,ulong,int *)
0x1800457c3  mov     edi, eax
0x1800457c5  test    eax, eax
0x1800457c7  jz      loc_18004593C
0x1800457cd  mov     eax, [rbp+410h+arg_10]
0x1800457d3  mov     edx, r15d
0x1800457d6  test    eax, eax
0x1800457d8  mov     ecx, r15d
0x1800457db  setz    dl; unsigned int
0x1800457de  cmp     [rsp+510h+var_4A4], r15d
0x1800457e3  setz    cl
0x1800457e6  cmp     edx, ecx
0x1800457e8  jz      loc_1800458EA
0x1800457ee  cmp     ebx, 6D6E7472h
0x1800457f4  jz      short loc_1800457FE
0x1800457f6  cmp     ebx, 73706163h
0x1800457fc  jnz     short loc_18004582C
0x1800457fe  lea     rax, [rbp+410h+var_240]
0x180045805  mov     rcx, rsi; pDeviceName
0x180045808  lea     r8, [rbp+410h+var_450]; unsigned __int16 *
0x18004580c  mov     [rsp+510h+var_4F0], rax; unsigned __int16 *
0x180045811  call    ?GetDefaultDeviceProfileInDefaultScope@@YAJPEBGIPEAGI1@Z; GetDefaultDeviceProfileInDefaultScope(ushort const *,uint,ushort *,uint,ushort *)
0x180045816  test    eax, eax
0x180045818  jns     short loc_180045826
0x18004581a  lea     r14, aGetdefaultdevi_0; "GetDefaultDeviceProfile Failed: 0x%08x"...
0x180045821  jmp     loc_1800458CF
0x180045826  mov     eax, [rbp+410h+arg_10]
0x18004582c  test    eax, eax
0x18004582e  jz      short loc_180045852
0x180045830  mov     edx, ebx; unsigned int
0x180045832  mov     rcx, rsi; unsigned __int16 *
0x180045835  call    ?CloneSystemWideProfileList@@YAHPEBGK@Z; CloneSystemWideProfileList(ushort const *,ulong)
0x18004583a  mov     edi, eax
0x18004583c  test    eax, eax
0x18004583e  jz      loc_18004593C
0x180045844  mov     eax, 1
0x180045849  cmp     [rbp+410h+arg_10], r15d
0x180045850  jnz     short loc_180045855
0x180045852  mov     eax, r15d
0x180045855  mov     r9d, 3
0x18004585b  mov     [rsp+510h+var_4B0], eax
0x18004585f  lea     rax, [rsp+510h+var_4B0]
0x180045864  mov     [rsp+510h+var_4E8], 4; unsigned int
0x18004586c  mov     r8d, ebx
0x18004586f  mov     [rsp+510h+var_4F0], rax; void *
0x180045874  mov     rdx, rsi; unsigned __int16 *
0x180045877  lea     ecx, [r9-2]; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18004587b  call    SetDeviceData
0x180045880  mov     edi, eax
0x180045882  test    eax, eax
0x180045884  jz      loc_18004593C
0x18004588a  mov     edx, ebx; unsigned int
0x18004588c  mov     rcx, rsi; unsigned __int16 *
0x18004588f  call    ?SaveSystemWideProfileListSnapshot@@YAHPEBGK@Z; SaveSystemWideProfileListSnapshot(ushort const *,ulong)
0x180045894  mov     edi, eax
0x180045896  test    eax, eax
0x180045898  jz      loc_18004593C
0x18004589e  cmp     ebx, 6D6E7472h
0x1800458a4  jz      short loc_1800458AE
0x1800458a6  cmp     ebx, 73706163h
0x1800458ac  jnz     short loc_1800458EA
0x1800458ae  xor     r9d, r9d; int
0x1800458b1  lea     r8, [rbp+410h+var_240]; unsigned __int16 *
0x1800458b8  lea     rdx, [rbp+410h+var_450]; unsigned __int16 *
0x1800458bc  mov     rcx, rsi; lpString1
0x1800458bf  call    ?AttemptRefreshCalibrationIfProfileChanged@@YAJPEBG00H@Z; AttemptRefreshCalibrationIfProfileChanged(ushort const *,ushort const *,ushort const *,int)
0x1800458c4  test    eax, eax
0x1800458c6  jns     short loc_1800458EA
0x1800458c8  lea     r14, aAttemptrefresh_0; "AttemptRefreshCalibrationIfProfileChang"...
0x1800458cf  mov     ecx, eax
0x1800458d1  and     ecx, 1FFF0000h
0x1800458d7  cmp     ecx, 70000h
0x1800458dd  jnz     short loc_1800458E2
0x1800458df  movzx   eax, ax
0x1800458e2  mov     ecx, eax; dwErrCode
0x1800458e4  call    cs:__imp_SetLastError
0x1800458ea  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800458ee  inc     rax
0x1800458f1  cmp     [rsi+rax*2], r15w
0x1800458f6  jnz     short loc_1800458EE
0x1800458f8  mov     rcx, cs:g_etwHandle
0x1800458ff  lea     rax, ds:2[rax*2]
0x180045907  mov     [rbp+410h+var_468], eax
0x18004590a  lea     r9, [rbp+410h+var_470]
0x18004590e  lea     rax, [rbp+410h+arg_10]
0x180045915  mov     [rbp+410h+var_470], rsi
0x180045919  mov     r8d, 2
0x18004591f  mov     [rbp+410h+var_460], rax
0x180045923  lea     rdx, SET_USE_PER_USER_PROFILES
0x18004592a  mov     [rbp+410h+var_464], r15d
0x18004592e  mov     [rbp+410h+var_458], 4
0x180045936  call    cs:__imp_EtwEventWrite
0x18004593c  mov     eax, cs:dword_18009E080
0x180045942  cmp     eax, 5
0x180045945  jbe     loc_1800459F5
0x18004594b  mov     rdx, 200000000000h
0x180045955  lea     rcx, dword_18009E080
0x18004595c  call    _tlgKeywordOn
0x180045961  test    al, al
0x180045963  jz      loc_1800459F5
0x180045969  lea     rax, [rbp+410h+var_450]
0x18004596d  mov     [rbp+410h+var_490], 2000000h
0x180045975  mov     [rbp+410h+var_488], rax
0x180045979  mov     eax, [rbp+410h+arg_10]
0x18004597f  mov     [rsp+510h+var_4B0], eax
0x180045983  mov     [rsp+510h+var_4A8], ebx
0x180045987  mov     [rbp+410h+var_480], rsi
0x18004598b  mov     [rbp+410h+var_478], r14
0x18004598f  call    cs:__imp_GetLastError
0x180045995  lea     rdx, word_1800913FA
0x18004599c  mov     dword ptr [rsp+510h+var_498], edi
0x1800459a0  mov     [rsp+510h+var_4A0], eax
0x1800459a4  lea     rax, [rbp+410h+var_490]
0x1800459a8  mov     [rsp+510h+var_4B8], rax
0x1800459ad  lea     rax, [rbp+410h+var_488]
0x1800459b1  mov     [rsp+510h+var_4C0], rax
0x1800459b6  lea     rax, [rsp+510h+var_4B0]
0x1800459bb  mov     [rsp+510h+var_4C8], rax
0x1800459c0  lea     rax, [rsp+510h+var_4A8]
0x1800459c5  mov     [rsp+510h+var_4D0], rax
0x1800459ca  lea     rax, [rbp+410h+var_480]
0x1800459ce  mov     [rsp+510h+var_4D8], rax
0x1800459d3  lea     rax, [rbp+410h+var_478]
0x1800459d7  mov     [rsp+510h+var_4E0], rax
0x1800459dc  lea     rax, [rsp+510h+var_4A0]
0x1800459e1  mov     qword ptr [rsp+510h+var_4E8], rax
0x1800459e6  lea     rax, [rsp+510h+var_498]
0x1800459eb  mov     [rsp+510h+var_4F0], rax
0x1800459f0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U2@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@4334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800459f5  mov     eax, edi
0x1800459f7  mov     rcx, [rbp+410h+var_30]
0x1800459fe  xor     rcx, rsp; StackCookie
0x180045a01  call    __security_check_cookie
0x180045a06  mov     rbx, [rsp+510h+arg_18]
0x180045a0e  add     rsp, 4F0h
0x180045a15  pop     r15
0x180045a17  pop     r14
0x180045a19  pop     rdi
0x180045a1a  pop     rsi
0x180045a1b  pop     rbp
0x180045a1c  retn
```
