# InternalSetDefaultColorProfile(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,COLORPROFILETYPE,COLORPROFILESUBTYPE,ulong,ushort const *)

- ea: `0x18002435c`
- end: `0x1800248fd`
- name: `?InternalSetDefaultColorProfile@@YAHW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGW4COLORPROFILETYPE@@W4COLORPROFILESUBTYPE@@K1@Z`
- size: `1441`
- prototype: `int(enum WCS_PROFILE_MANAGEMENT_SCOPE, const unsigned __int16 *, enum COLORPROFILETYPE, enum COLORPROFILESUBTYPE, unsigned int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x18002af30`
- `0x180044d90`
- `0x18004d700`

## callees

- `0x180001a08`
- `0x18000be44`
- `0x180023428`
- `0x180023a4c`
- `0x18002435c`
- `0x180029f14`
- `0x18002e5f0`
- `0x18003f554`
- `0x18003ff94`
- `0x180042bfc`
- `0x180042ccc`
- `0x180043094`
- `0x180043324`
- `0x180044ab0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800243d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800243d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024740`

## string_xrefs

- `0x18002442d`: `InstallColorProfileW failed: %d\n`

## pseudocode

```c
__int64 __fastcall InternalSetDefaultColorProfile(
        enum WCS_PROFILE_MANAGEMENT_SCOPE a1,
        unsigned __int16 *a2,
        enum COLORPROFILETYPE a3,
        int *a4,
        unsigned int a5,
        const unsigned __int16 *pProfileName)
{
  unsigned int v7; // edi
  unsigned __int16 *v8; // r8
  const unsigned __int16 *v10; // r12
  int v11; // r15d
  const OLECHAR *v12; // rbx
  DWORD v13; // ecx
  __int64 v14; // rax
  int v15; // eax
  const WCHAR *FilenameFromPath; // rax
  DWORD v17; // eax
  int AdvancedColorState; // eax
  __int64 v19; // r8
  int v20; // edx
  int v21; // ecx
  int v22; // eax
  int v23; // eax
  DWORD LastError; // eax
  unsigned int v25; // ebx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  int v30; // [rsp+100h] [rbp-80h] BYREF
  int v31; // [rsp+104h] [rbp-7Ch] BYREF
  int v32; // [rsp+108h] [rbp-78h]
  WORD wSecond; // [rsp+10Ch] [rbp-74h] BYREF
  WORD wMinute; // [rsp+10Eh] [rbp-72h] BYREF
  WORD wHour; // [rsp+110h] [rbp-70h] BYREF
  WORD wDay; // [rsp+112h] [rbp-6Eh] BYREF
  int v37; // [rsp+114h] [rbp-6Ch] BYREF
  unsigned int v38; // [rsp+118h] [rbp-68h] BYREF
  unsigned int v39; // [rsp+11Ch] [rbp-64h] BYREF
  unsigned __int16 *v40; // [rsp+120h] [rbp-60h] BYREF
  LPVOID lpMem; // [rsp+128h] [rbp-58h] BYREF
  unsigned __int16 *v42; // [rsp+130h] [rbp-50h] BYREF
  unsigned __int16 *v43; // [rsp+138h] [rbp-48h] BYREF
  unsigned __int16 *v44; // [rsp+140h] [rbp-40h] BYREF
  int v45; // [rsp+148h] [rbp-38h] BYREF
  unsigned int v46; // [rsp+14Ch] [rbp-34h] BYREF
  unsigned int v47; // [rsp+150h] [rbp-30h] BYREF
  enum COLORPROFILETYPE v48; // [rsp+154h] [rbp-2Ch] BYREF
  enum WCS_PROFILE_MANAGEMENT_SCOPE v49; // [rsp+158h] [rbp-28h] BYREF
  DWORD v50; // [rsp+15Ch] [rbp-24h] BYREF
  UINT32 id; // [rsp+160h] [rbp-20h] BYREF
  int v52; // [rsp+164h] [rbp-1Ch] BYREF
  int v53; // [rsp+168h] [rbp-18h] BYREF
  unsigned int v54; // [rsp+16Ch] [rbp-14h] BYREF
  unsigned int v55; // [rsp+170h] [rbp-10h] BYREF
  unsigned __int16 *v56; // [rsp+178h] [rbp-8h] BYREF
  LUID adapterId; // [rsp+180h] [rbp+0h] BYREF
  const OLECHAR *v58; // [rsp+188h] [rbp+8h] BYREF
  const OLECHAR *v59; // [rsp+190h] [rbp+10h] BYREF
  const OLECHAR *v60; // [rsp+198h] [rbp+18h] BYREF
  const OLECHAR *v61; // [rsp+1A0h] [rbp+20h] BYREF
  const OLECHAR *v62; // [rsp+1A8h] [rbp+28h] BYREF
  const OLECHAR *v63; // [rsp+1B0h] [rbp+30h] BYREF
  const OLECHAR *v64; // [rsp+1B8h] [rbp+38h] BYREF
  const OLECHAR *v65; // [rsp+1C0h] [rbp+40h] BYREF
  struct DISPLAYCONFIG_PATH_TARGET_INFO v66; // [rsp+1C8h] [rbp+48h] BYREF
  struct _SYSTEMTIME v67; // [rsp+1F8h] [rbp+78h] BYREF

  v40 = a2;
  v32 = 0;
  v30 = 0;
  v7 = (unsigned int)a4;
  v31 = 0;
  v8 = a2;
  memset(&v66, 0, sizeof(v66));
  v10 = 0;
  v11 = 0;
  if ( pProfileName )
  {
    v14 = -1;
    do
      ++v14;
    while ( pProfileName[v14] );
    if ( v14 )
    {
      if ( (_DWORD)a4 != 6 && !InstallColorProfileW(0, pProfileName) )
      {
        v12 = L"InstallColorProfileW failed: %d\n";
        goto LABEL_51;
      }
      v15 = DetermineProfileTypeFromFile(pProfileName, &v30);
      v11 = v30;
      if ( !v15 )
      {
        v12 = L"DetermineProfileTypeFromFile failed: %d\n";
        goto LABEL_51;
      }
      if ( v30 != a3 && (v30 || a3 != CPT_DMP) && (v30 != 1 || a3) )
      {
        v12 = L"Profile type from file %s (%d) does not match input cpt (%d)\n";
        goto LABEL_4;
      }
      FilenameFromPath = GetFilenameFromPath(pProfileName);
      v8 = v40;
      v10 = FilenameFromPath;
    }
    else
    {
      if ( (_DWORD)a4 != 6 )
      {
        v12 = L"Empty profile name is only allowed for custom working space.\n";
        goto LABEL_4;
      }
      v10 = pProfileName;
    }
  }
  else
  {
    if ( a1 == WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE )
    {
      v12 = L"System-wide default can't be reset.\n";
LABEL_4:
      v13 = 87;
LABEL_5:
      SetLastError(v13);
      goto LABEL_51;
    }
    if ( a2 )
    {
      v12 = L"Device-specific default can't be reset.\n";
      goto LABEL_4;
    }
  }
  v12 = &word_1800884E0;
  if ( v8 )
  {
    v30 = 0;
    AdvancedColorState = InternalGetAdvancedColorState(
                           v8,
                           (enum _DISPLAYCONFIG_ADVANCED_COLOR_MODE *)&v30,
                           (int *)v8,
                           a4,
                           &v66);
    v20 = v30;
    v21 = AdvancedColorState;
    v22 = 0;
    if ( v21 < 0 )
      v20 = 0;
    LOBYTE(v22) = v20 == 2;
    v31 = v22;
    if ( v7 == 8 )
    {
      v23 = 1;
    }
    else
    {
      v23 = 0;
      if ( v7 != 7 )
        LOBYTE(v23) = v20 == 2;
    }
    v17 = SetDefaultDeviceProfile(a1, v40, v19, a3, v10, v23);
    if ( v17 )
    {
      v12 = L"SetDefaultDeviceProfile failed: %d\n";
      goto LABEL_30;
    }
  }
  else if ( a3 == CPT_CAMP )
  {
    v17 = SetDefaultCAMProfile(a1, v10);
    if ( v17 )
    {
      v12 = L"SetDefaultCAMProfile failed: %d\n";
LABEL_30:
      v13 = v17;
      goto LABEL_5;
    }
  }
  else if ( (unsigned int)a3 <= CPT_DMP )
  {
    if ( v7 - 5 > 1 )
    {
      v12 = L"Invalid color profile sub-type\n";
      goto LABEL_4;
    }
    v17 = SetDefaultWorkingSpaceProfile(a1, (enum COLORPROFILETYPE)a2, a5, v10);
    if ( v17 )
    {
      v12 = L"SetDefaultWorkingSpaceProfile failed: %d\n";
      goto LABEL_30;
    }
  }
  else
  {
    if ( a3 != CPT_GMMP )
    {
      v12 = L"Invalid profile type.\n";
      goto LABEL_4;
    }
    if ( v7 >= 2 && v7 - 2 > 1 )
      goto LABEL_4;
    v17 = SetDefaultProfileForRenderingIntent(a1, v7, v10);
    if ( v17 )
    {
      v12 = L"SetDefaultProfileForRenderingIntent failed: %d\n";
      goto LABEL_30;
    }
  }
  v32 = 1;
LABEL_51:
  v39 = 0;
  lpMem = 0;
  v42 = 0;
  v38 = 0;
  v43 = 0;
  v44 = 0;
  v56 = 0;
  v37 = 0;
  v67 = 0;
  if ( pProfileName )
    CreatePropertiesFromProfile(
      pProfileName,
      &v39,
      &v67,
      0,
      (unsigned __int16 **)&lpMem,
      &v42,
      0,
      0,
      0,
      0,
      0,
      0,
      &v38,
      &v43,
      &v44,
      &v56,
      (enum DmpDeviceType *)&v37);
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x400000000000LL) )
  {
    adapterId = v66.adapterId;
    id = v66.id;
    v52 = v31;
    v53 = v37;
    v58 = v56;
    v59 = v44;
    v60 = v43;
    v54 = v38;
    v61 = v42;
    v62 = (const OLECHAR *)lpMem;
    wSecond = v67.wSecond;
    wMinute = v67.wMinute;
    wHour = v67.wHour;
    wDay = v67.wDay;
    LOWORD(v31) = v67.wMonth;
    LOWORD(v30) = v67.wYear;
    v55 = v39;
    v46 = a5;
    v64 = v40;
    v63 = v10;
    v45 = v11;
    v47 = v7;
    v48 = a3;
    v49 = a1;
    v65 = v12;
    LastError = GetLastError();
    v25 = v32;
    v50 = LastError;
    LODWORD(v40) = v32;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v26,
      (__int64)&dword_180090A94,
      v27,
      v28,
      (__int64)&v40,
      (__int64)&v50,
      &v65,
      (__int64)&v49,
      &v64,
      (__int64)&v48,
      (__int64)&v47,
      (__int64)&v46,
      (__int64)&v45,
      &v63,
      (__int64)&v55,
      (__int64)&v30,
      (__int64)&v31,
      (__int64)&wDay,
      (__int64)&wHour,
      (__int64)&wMinute,
      (__int64)&wSecond,
      &v62,
      &v61,
      (__int64)&v54,
      &v60,
      &v59,
      &v58,
      (__int64)&v53,
      (__int64)&v52,
      (__int64)&id,
      (__int64)&adapterId);
  }
  else
  {
    v25 = v32;
  }
  if ( lpMem )
  {
    MemFree(lpMem);
    lpMem = 0;
  }
  if ( v42 )
  {
    MemFree(v42);
    v42 = 0;
  }
  if ( v43 )
  {
    MemFree(v43);
    v43 = 0;
  }
  if ( v44 )
  {
    MemFree(v44);
    v44 = 0;
  }
  if ( v56 )
    MemFree(v56);
  return v25;
}

```

## disassembly

```asm
0x18002435c  push    rbp
0x18002435e  push    rbx
0x18002435f  push    rsi
0x180024360  push    rdi
0x180024361  push    r12
0x180024363  push    r13
0x180024365  push    r14
0x180024367  push    r15
0x180024369  lea     rbp, [rsp-98h]
0x180024371  sub     rsp, 218h
0x180024378  mov     rax, cs:__security_cookie
0x18002437f  xor     rax, rsp
0x180024382  mov     [rbp+0D0h+var_48], rax
0x180024389  mov     rsi, [rbp+0D0h+pProfileName]
0x180024390  xor     ebx, ebx
0x180024392  mov     [rbp+0D0h+var_130], rdx
0x180024396  xorps   xmm0, xmm0
0x180024399  mov     [rbp+0D0h+var_148], ebx
0x18002439c  mov     r14d, r8d
0x18002439f  mov     [rbp+0D0h+var_150], ebx
0x1800243a2  mov     edi, r9d
0x1800243a5  mov     [rbp+0D0h+var_14C], ebx
0x1800243a8  mov     r8, rdx
0x1800243ab  mov     [rbp+0D0h+var_88.adapterId.LowPart], ebx
0x1800243ae  mov     r13d, ecx
0x1800243b1  mov     r12d, ebx
0x1800243b4  mov     r15d, ebx
0x1800243b7  movups  xmmword ptr [rbp+0D0h+var_88.rotation], xmm0
0x1800243bb  movups  xmmword ptr [rbp+0D0h+var_88.refreshRate.Denominator], xmm0
0x1800243bf  movups  xmmword ptr [rbp+0D0h+var_88.adapterId.HighPart], xmm0
0x1800243c3  test    rsi, rsi
0x1800243c6  jnz     short loc_1800243F5
0x1800243c8  test    ecx, ecx
0x1800243ca  jnz     short loc_1800243E3
0x1800243cc  lea     rbx, aSystemWideDefa; "System-wide default can't be reset.\n"
0x1800243d3  mov     ecx, 57h ; 'W'; dwErrCode
0x1800243d8  call    cs:__imp_SetLastError
0x1800243de  jmp     loc_1800245C2
0x1800243e3  test    rdx, rdx
0x1800243e6  jz      loc_18002448F
0x1800243ec  lea     rbx, aDeviceSpecific; "Device-specific default can't be reset."...
0x1800243f3  jmp     short loc_1800243D3
0x1800243f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800243f9  inc     rax
0x1800243fc  cmp     [rsi+rax*2], bx
0x180024400  jnz     short loc_1800243F9
0x180024402  test    rax, rax
0x180024405  jnz     short loc_18002441A
0x180024407  cmp     edi, 6
0x18002440a  jz      short loc_180024415
0x18002440c  lea     rbx, aEmptyProfileNa; "Empty profile name is only allowed for "...
0x180024413  jmp     short loc_1800243D3
0x180024415  mov     r12, rsi
0x180024418  jmp     short loc_18002448F
0x18002441a  cmp     edi, 6
0x18002441d  jz      short loc_180024439
0x18002441f  mov     rdx, rsi; pProfileName
0x180024422  xor     ecx, ecx; pMachineName
0x180024424  call    InstallColorProfileW
0x180024429  test    eax, eax
0x18002442b  jnz     short loc_180024439
0x18002442d  lea     rbx, aInstallcolorpr_1; "InstallColorProfileW failed: %d\n"
0x180024434  jmp     loc_1800245C2
0x180024439  lea     rdx, [rbp+0D0h+var_150]
0x18002443d  mov     rcx, rsi
0x180024440  call    DetermineProfileTypeFromFile
0x180024445  mov     r15d, [rbp+0D0h+var_150]
0x180024449  test    eax, eax
0x18002444b  jnz     short loc_180024459
0x18002444d  lea     rbx, aDetermineprofi; "DetermineProfileTypeFromFile failed: %d"...
0x180024454  jmp     loc_1800245C2
0x180024459  cmp     r15d, r14d
0x18002445c  jz      short loc_180024480
0x18002445e  test    r15d, r15d
0x180024461  jnz     short loc_180024469
0x180024463  cmp     r14d, 1
0x180024467  jz      short loc_180024480
0x180024469  cmp     r15d, 1
0x18002446d  jnz     short loc_180024474
0x18002446f  test    r14d, r14d
0x180024472  jz      short loc_180024480
0x180024474  lea     rbx, aProfileTypeFro; "Profile type from file %s (%d) does not"...
0x18002447b  jmp     loc_1800243D3
0x180024480  mov     rcx, rsi; lpStringSource
0x180024483  call    GetFilenameFromPath
0x180024488  mov     r8, [rbp+0D0h+var_130]; int *
0x18002448c  mov     r12, rax
0x18002448f  lea     rbx, word_1800884E0
0x180024496  test    r8, r8
0x180024499  jnz     loc_18002454B
0x18002449f  cmp     r14d, 2
0x1800244a3  jnz     short loc_1800244C6
0x1800244a5  mov     rdx, r12; unsigned __int16 *
0x1800244a8  mov     ecx, r13d; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x1800244ab  call    ?SetDefaultCAMProfile@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBG@Z; SetDefaultCAMProfile(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *)
0x1800244b0  test    eax, eax
0x1800244b2  jz      loc_1800245BB
0x1800244b8  lea     rbx, aSetdefaultcamp; "SetDefaultCAMProfile failed: %d\n"
0x1800244bf  mov     ecx, eax
0x1800244c1  jmp     loc_1800243D8
0x1800244c6  cmp     r14d, 1
0x1800244ca  jbe     short loc_180024515
0x1800244cc  cmp     r14d, 3
0x1800244d0  jnz     short loc_180024509
0x1800244d2  mov     ecx, edi
0x1800244d4  test    edi, edi
0x1800244d6  jz      short loc_1800244EB
0x1800244d8  sub     ecx, 1
0x1800244db  jz      short loc_1800244EB
0x1800244dd  sub     ecx, 1
0x1800244e0  jz      short loc_1800244EB
0x1800244e2  cmp     ecx, 1
0x1800244e5  jnz     loc_1800243D3
0x1800244eb  mov     r8, r12; unsigned __int16 *
0x1800244ee  mov     edx, edi; unsigned int
0x1800244f0  mov     ecx, r13d; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x1800244f3  call    ?SetDefaultProfileForRenderingIntent@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@KPEBG@Z; SetDefaultProfileForRenderingIntent(WCS_PROFILE_MANAGEMENT_SCOPE,ulong,ushort const *)
0x1800244f8  test    eax, eax
0x1800244fa  jz      loc_1800245BB
0x180024500  lea     rbx, aSetdefaultprof; "SetDefaultProfileForRenderingIntent fai"...
0x180024507  jmp     short loc_1800244BF
0x180024509  lea     rbx, aInvalidProfile; "Invalid profile type.\n"
0x180024510  jmp     loc_1800243D3
0x180024515  lea     eax, [rdi-5]
0x180024518  cmp     eax, 1
0x18002451b  jbe     short loc_180024529
0x18002451d  lea     rbx, aInvalidColorPr_0; "Invalid color profile sub-type\n"
0x180024524  jmp     loc_1800243D3
0x180024529  mov     r8d, [rbp+0D0h+arg_20]; unsigned int
0x180024530  mov     r9, r12; unsigned __int16 *
0x180024533  mov     ecx, r13d; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180024536  call    ?SetDefaultWorkingSpaceProfile@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@W4COLORPROFILETYPE@@KPEBG@Z; SetDefaultWorkingSpaceProfile(WCS_PROFILE_MANAGEMENT_SCOPE,COLORPROFILETYPE,ulong,ushort const *)
0x18002453b  test    eax, eax
0x18002453d  jz      short loc_1800245BB
0x18002453f  lea     rbx, aSetdefaultwork; "SetDefaultWorkingSpaceProfile failed: %"...
0x180024546  jmp     loc_1800244BF
0x18002454b  lea     rax, [rbp+0D0h+var_88]
0x18002454f  mov     [rbp+0D0h+var_150], 0
0x180024556  lea     rdx, [rbp+0D0h+var_150]; enum _DISPLAYCONFIG_ADVANCED_COLOR_MODE *
0x18002455a  mov     [rsp+250h+var_230], rax; struct DISPLAYCONFIG_PATH_TARGET_INFO *
0x18002455f  mov     rcx, r8; unsigned __int16 *
0x180024562  call    ?InternalGetAdvancedColorState@@YAJPEBGPEAW4_DISPLAYCONFIG_ADVANCED_COLOR_MODE@@PEAH2PEAUDISPLAYCONFIG_PATH_TARGET_INFO@@@Z; InternalGetAdvancedColorState(ushort const *,_DISPLAYCONFIG_ADVANCED_COLOR_MODE *,int *,int *,DISPLAYCONFIG_PATH_TARGET_INFO *)
0x180024567  mov     edx, [rbp+0D0h+var_150]
0x18002456a  mov     ecx, eax
0x18002456c  xor     eax, eax
0x18002456e  test    ecx, ecx
0x180024570  cmovs   edx, eax
0x180024573  cmp     edx, 2
0x180024576  setz    al
0x180024579  mov     [rbp+0D0h+var_14C], eax
0x18002457c  cmp     edi, 8
0x18002457f  jnz     short loc_180024586
0x180024581  lea     eax, [rdi-7]
0x180024584  jmp     short loc_180024593
0x180024586  xor     eax, eax
0x180024588  cmp     edi, 7
0x18002458b  jz      short loc_180024593
0x18002458d  cmp     edx, 2
0x180024590  setz    al
0x180024593  mov     rdx, [rbp+0D0h+var_130]; unsigned __int16 *
0x180024597  mov     r9d, r14d; enum COLORPROFILETYPE
0x18002459a  mov     dword ptr [rsp+250h+var_228], eax; int
0x18002459e  mov     ecx, r13d; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x1800245a1  mov     [rsp+250h+var_230], r12; unsigned __int16 *
0x1800245a6  call    ?SetDefaultDeviceProfile@@YAKW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGKW4COLORPROFILETYPE@@1H@Z; SetDefaultDeviceProfile(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,COLORPROFILETYPE,ushort const *,int)
0x1800245ab  test    eax, eax
0x1800245ad  jz      short loc_1800245BB
0x1800245af  lea     rbx, aSetdefaultdevi; "SetDefaultDeviceProfile failed: %d\n"
0x1800245b6  jmp     loc_1800244BF
0x1800245bb  mov     [rbp+0D0h+var_148], 1
0x1800245c2  xor     r8d, r8d
0x1800245c5  xorps   xmm0, xmm0
0x1800245c8  mov     [rbp+0D0h+var_134], r8d
0x1800245cc  mov     [rbp+0D0h+lpMem], r8
0x1800245d0  mov     [rbp+0D0h+var_120], r8
0x1800245d4  mov     [rbp+0D0h+var_138], r8d
0x1800245d8  mov     [rbp+0D0h+var_118], r8
0x1800245dc  mov     [rbp+0D0h+var_110], r8
0x1800245e0  mov     [rbp+0D0h+var_D8], r8
0x1800245e4  mov     [rbp+0D0h+var_13C], r8d
0x1800245e8  movups  xmmword ptr [rbp+0D0h+var_58.wYear], xmm0
0x1800245ec  test    rsi, rsi
0x1800245ef  jz      short loc_180024664
0x1800245f1  lea     rax, [rbp+0D0h+var_13C]
0x1800245f5  xor     r9d, r9d; unsigned __int16 **
0x1800245f8  mov     [rsp+250h+var_1D0], rax; enum DmpDeviceType *
0x180024600  lea     rdx, [rbp+0D0h+var_134]; unsigned int *
0x180024604  lea     rax, [rbp+0D0h+var_D8]
0x180024608  mov     rcx, rsi; unsigned __int16 *
0x18002460b  mov     [rsp+250h+var_1D8], rax; unsigned __int16 **
0x180024610  lea     rax, [rbp+0D0h+var_110]
0x180024614  mov     [rsp+250h+var_1E0], rax; unsigned __int16 **
0x180024619  lea     rax, [rbp+0D0h+var_118]
0x18002461d  mov     [rsp+250h+var_1E8], rax; unsigned __int16 **
0x180024622  lea     rax, [rbp+0D0h+var_138]
0x180024626  mov     [rsp+250h+var_1F0], rax; unsigned int *
0x18002462b  lea     rax, [rbp+0D0h+var_120]
0x18002462f  mov     [rsp+250h+var_1F8], r8; enum COLORPROFILESUBTYPE *
0x180024634  mov     [rsp+250h+var_200], r8; enum COLORPROFILETYPE *
0x180024639  mov     [rsp+250h+var_208], r8; unsigned __int16 **
0x18002463e  mov     [rsp+250h+var_210], r8; unsigned __int16 **
0x180024643  mov     [rsp+250h+var_218], r8; unsigned __int16 **
0x180024648  mov     [rsp+250h+var_220], r8; unsigned __int16 **
0x18002464d  lea     r8, [rbp+0D0h+var_58]; struct _SYSTEMTIME *
0x180024651  mov     [rsp+250h+var_228], rax; unsigned __int16 **
0x180024656  lea     rax, [rbp+0D0h+lpMem]
0x18002465a  mov     [rsp+250h+var_230], rax; unsigned __int16 **
0x18002465f  call    ?CreatePropertiesFromProfile@@YAJPEBGPEAKPEAU_SYSTEMTIME@@PEAPEAG333333PEAW4COLORPROFILETYPE@@PEAW4COLORPROFILESUBTYPE@@1333PEAW4DmpDeviceType@@@Z; CreatePropertiesFromProfile(ushort const *,ulong *,_SYSTEMTIME *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,COLORPROFILETYPE *,COLORPROFILESUBTYPE *,ulong *,ushort * *,ushort * *,ushort * *,DmpDeviceType *)
0x180024664  mov     eax, cs:dword_18009E080
0x18002466a  cmp     eax, 5
0x18002466d  jbe     loc_18002487D
0x180024673  mov     rdx, 400000000000h
0x18002467d  lea     rcx, dword_18009E080
0x180024684  call    _tlgKeywordOn
0x180024689  test    al, al
0x18002468b  jz      loc_18002487D
0x180024691  mov     rax, qword ptr [rbp+0D0h+var_88.adapterId.LowPart]
0x180024695  mov     [rbp+0D0h+var_D0], rax
0x180024699  mov     eax, [rbp+0D0h+var_88.id]
0x18002469c  mov     [rbp+0D0h+var_F0], eax
0x18002469f  mov     eax, [rbp+0D0h+var_14C]
0x1800246a2  mov     [rbp+0D0h+var_EC], eax
0x1800246a5  mov     eax, [rbp+0D0h+var_13C]
0x1800246a8  mov     [rbp+0D0h+var_E8], eax
0x1800246ab  mov     rax, [rbp+0D0h+var_D8]
0x1800246af  mov     [rbp+0D0h+var_C8], rax
0x1800246b3  mov     rax, [rbp+0D0h+var_110]
0x1800246b7  mov     [rbp+0D0h+var_C0], rax
0x1800246bb  mov     rax, [rbp+0D0h+var_118]
0x1800246bf  mov     [rbp+0D0h+var_B8], rax
0x1800246c3  mov     eax, [rbp+0D0h+var_138]
0x1800246c6  mov     [rbp+0D0h+var_E4], eax
0x1800246c9  mov     rax, [rbp+0D0h+var_120]
0x1800246cd  mov     [rbp+0D0h+var_B0], rax
0x1800246d1  mov     rax, [rbp+0D0h+lpMem]
0x1800246d5  mov     [rbp+0D0h+var_A8], rax
0x1800246d9  movzx   eax, [rbp+0D0h+var_58.wSecond]
0x1800246e0  mov     [rbp+0D0h+var_144], ax
0x1800246e4  movzx   eax, [rbp+0D0h+var_58.wMinute]
0x1800246eb  mov     [rbp+0D0h+var_142], ax
0x1800246ef  movzx   eax, [rbp+0D0h+var_58.wHour]
0x1800246f6  mov     [rbp+0D0h+var_140], ax
0x1800246fa  movzx   eax, [rbp+0D0h+var_58.wDay]
0x1800246fe  mov     [rbp+0D0h+var_13E], ax
0x180024702  movzx   eax, [rbp+0D0h+var_58.wMonth]
0x180024706  mov     word ptr [rbp+0D0h+var_14C], ax
0x18002470a  movzx   eax, [rbp+0D0h+var_58.wYear]
0x18002470e  mov     word ptr [rbp+0D0h+var_150], ax
0x180024712  mov     eax, [rbp+0D0h+var_134]
0x180024715  mov     [rbp+0D0h+var_E0], eax
0x180024718  mov     eax, [rbp+0D0h+arg_20]
0x18002471e  mov     [rbp+0D0h+var_104], eax
0x180024721  mov     rax, [rbp+0D0h+var_130]
0x180024725  mov     [rbp+0D0h+var_98], rax
0x180024729  mov     [rbp+0D0h+var_A0], r12
0x18002472d  mov     [rbp+0D0h+var_108], r15d
0x180024731  mov     [rbp+0D0h+var_100], edi
0x180024734  mov     [rbp+0D0h+var_FC], r14d
0x180024738  mov     [rbp+0D0h+var_F8], r13d
0x18002473c  mov     [rbp+0D0h+var_90], rbx
0x180024740  call    cs:__imp_GetLastError
0x180024746  mov     ebx, [rbp+0D0h+var_148]
0x180024749  mov     [rbp+0D0h+var_F4], eax
0x18002474c  lea     rax, [rbp+0D0h+var_D0]
0x180024750  mov     [rsp+250h+var_160], rax
0x180024758  lea     rax, [rbp+0D0h+var_F0]
0x18002475c  mov     [rsp+250h+var_168], rax
0x180024764  lea     rax, [rbp+0D0h+var_EC]
0x180024768  mov     [rsp+250h+var_170], rax
0x180024770  lea     rax, [rbp+0D0h+var_E8]
0x180024774  mov     [rsp+250h+var_178], rax
0x18002477c  lea     rax, [rbp+0D0h+var_C8]
0x180024780  mov     [rsp+250h+var_180], rax
0x180024788  lea     rax, [rbp+0D0h+var_C0]
0x18002478c  mov     [rsp+250h+var_188], rax
0x180024794  lea     rax, [rbp+0D0h+var_B8]
0x180024798  mov     [rsp+250h+var_190], rax
0x1800247a0  lea     rax, [rbp+0D0h+var_E4]
0x1800247a4  mov     [rsp+250h+var_198], rax
0x1800247ac  lea     rax, [rbp+0D0h+var_B0]
0x1800247b0  mov     [rsp+250h+var_1A0], rax
0x1800247b8  lea     rax, [rbp+0D0h+var_A8]
0x1800247bc  mov     [rsp+250h+var_1A8], rax
0x1800247c4  lea     rax, [rbp+0D0h+var_144]
0x1800247c8  mov     [rsp+250h+var_1B0], rax
0x1800247d0  lea     rax, [rbp+0D0h+var_142]
0x1800247d4  mov     [rsp+250h+var_1B8], rax
0x1800247dc  lea     rax, [rbp+0D0h+var_140]
0x1800247e0  mov     [rsp+250h+var_1C0], rax
0x1800247e8  lea     rax, [rbp+0D0h+var_13E]
0x1800247ec  mov     [rsp+250h+var_1C8], rax
0x1800247f4  lea     rax, [rbp+0D0h+var_14C]
0x1800247f8  mov     [rsp+250h+var_1D0], rax
0x180024800  lea     rax, [rbp+0D0h+var_150]
0x180024804  mov     [rsp+250h+var_1D8], rax
0x180024809  lea     rax, [rbp+0D0h+var_E0]
0x18002480d  mov     dword ptr [rbp+0D0h+var_130], ebx
0x180024810  mov     [rsp+250h+var_1E0], rax
0x180024815  lea     rdx, dword_180090A94
0x18002481c  lea     rax, [rbp+0D0h+var_A0]
  ... truncated ...
```
