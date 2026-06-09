# CalibrationMonitorEnumCallback(HMONITOR__ *,HDC__ *,tagRECT *,__int64)

- ea: `0x180047f20`
- end: `0x180048595`
- name: `?CalibrationMonitorEnumCallback@@YAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z`
- size: `1653`
- prototype: `_BOOL8 __fastcall(HMONITOR, HDC, LPRECT, __int64)`
- caller_count: `0`
- callee_count: `26`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001008`
- `0x18000271c`
- `0x18001582c`
- `0x180015e7c`
- `0x180019a3c`
- `0x18001b360`
- `0x18001f614`
- `0x180022234`
- `0x180023428`
- `0x180023a4c`
- `0x180024a0c`
- `0x1800258c0`
- `0x18002e5f0`
- `0x18002e614`
- `0x18002ea60`
- `0x18002f2f4`
- `0x180040358`
- `0x180047f20`
- `0x180048b80`
- `0x18004a294`
- `0x18004aa0c`
- `0x18004ae7c`
- `0x18004aebc`
- `0x18004aef8`
- `0x18007f1dc`
- `0x180084010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180048085`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180048085`
- `ntdll!EtwEventWrite` at `0x180048008`
- `ntdll!EtwEventWrite` at `0x180048361`
- `ntdll!EtwEventWrite` at `0x180048008`
- `ntdll!EtwEventWrite` at `0x180048361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047fd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047fd0`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180048549`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180048549`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180047fa7`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180047fa7`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigSetDeviceInfo` at `0x180048280`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigSetDeviceInfo` at `0x180048280`

## pseudocode

```c
_BOOL8 __fastcall CalibrationMonitorEnumCallback(HMONITOR a1, HDC a2, LPRECT a3, __int64 a4)
{
  WCHAR *v6; // r12
  unsigned __int16 *v7; // r14
  int v8; // ebx
  signed int LastError; // eax
  signed int AdvancedColorState; // edi
  int *v11; // r8
  int *v12; // r9
  enum WCS_PROFILE_MANAGEMENT_SCOPE v13; // r15d
  const char *v14; // r9
  unsigned int v15; // r13d
  enum COLORPROFILESUBTYPE v16; // r12d
  int v17; // r15d
  LONG v18; // eax
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rax
  HMONITOR v23; // r15
  int v24; // eax
  BOOL v25; // r15d
  __int64 v26; // rcx
  const OLECHAR *v27; // r8
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  unsigned int v33; // [rsp+70h] [rbp-90h] BYREF
  BOOL v34; // [rsp+74h] [rbp-8Ch] BYREF
  int v35; // [rsp+78h] [rbp-88h]
  int v36; // [rsp+7Ch] [rbp-84h] BYREF
  LPCWSTR lpFileName; // [rsp+80h] [rbp-80h] BYREF
  int v38; // [rsp+88h] [rbp-78h] BYREF
  BOOL pUsePerUserProfiles; // [rsp+8Ch] [rbp-74h] BYREF
  HMONITOR hMonitor; // [rsp+90h] [rbp-70h] BYREF
  int v41; // [rsp+98h] [rbp-68h] BYREF
  __int128 v42; // [rsp+A0h] [rbp-60h] BYREF
  struct AdvancedColorCalibrationData *v43[2]; // [rsp+B0h] [rbp-50h]
  __int64 v44; // [rsp+C0h] [rbp-40h]
  int v45; // [rsp+C8h] [rbp-38h]
  __int64 v46; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v47; // [rsp+D8h] [rbp-28h] BYREF
  const OLECHAR *v48; // [rsp+E0h] [rbp-20h] BYREF
  const OLECHAR *v49; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v50; // [rsp+F0h] [rbp-10h] BYREF
  struct AdvancedColorCalibrationData *v51[2]; // [rsp+100h] [rbp+0h]
  __int64 v52; // [rsp+110h] [rbp+10h]
  struct DISPLAYCONFIG_PATH_INFO v53; // [rsp+120h] [rbp+20h] BYREF
  _BYTE setPacket[24]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v55; // [rsp+188h] [rbp+88h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  hMonitor = a1;
  v6 = 0;
  lpFileName = 0;
  v36 = 0;
  v35 = 0;
  v42 = 0;
  *(_OWORD *)v43 = 0;
  v44 = 0;
  v50 = 0;
  *(_OWORD *)v51 = 0;
  v52 = 0;
  v7 = 0;
  memset_0(&v53, 0, sizeof(v53));
  v8 = RoInitialize(1);
  v45 = v8;
  v38 = 0;
  if ( !(***(unsigned int (__fastcall ****)(_QWORD, HMONITOR, int *))(a4 + 24))(*(_QWORD *)(a4 + 24), a1, &v38) )
  {
LABEL_2:
    LastError = GetLastError();
    AdvancedColorState = LastError;
    if ( LastError > 0 )
      AdvancedColorState = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_60;
  }
  if ( v38 != 1 )
  {
    EtwEventWrite(g_etwHandle, CALIBRATION_MANAGEMENT_MULTIPLE_DEVICES, 0, 0);
    AdvancedColorState = -2147467259;
    goto LABEL_61;
  }
  v7 = (unsigned __int16 *)operator new[](0x208u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v7 )
  {
    AdvancedColorState = -2147024882;
    goto LABEL_61;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl'::`2'::impl) )
    *v7 = 0;
  AdvancedColorState = InternalTranslateHMonitorToICMName(a1, v7);
  if ( AdvancedColorState < 0 )
    goto LABEL_61;
  AdvancedColorState = InternalTranslateICMNameToPath(v7, &v53);
  if ( AdvancedColorState < 0 )
    goto LABEL_61;
  if ( *(_QWORD *)a4 )
  {
    if ( (unsigned int)_o__wcsicmp(*(_QWORD *)a4, v7) )
    {
      AdvancedColorState = -2147024809;
      goto LABEL_61;
    }
    v36 = 1;
  }
  pUsePerUserProfiles = 0;
  if ( !WcsGetUsePerUserProfiles(v7, 0x6D6E7472u, &pUsePerUserProfiles) )
    goto LABEL_2;
  v13 = pUsePerUserProfiles;
  v33 = 0;
  AdvancedColorState = InternalGetAdvancedColorState(v7, (enum _DISPLAYCONFIG_ADVANCED_COLOR_MODE *)&v33, v11, v12, 0);
  if ( AdvancedColorState >= 0 )
  {
    AdvancedColorState = GetDefaultCalibrationData((struct CalibrationData *)&v50);
    if ( AdvancedColorState >= 0 )
    {
      v15 = v33;
      if ( v33 < 2 )
      {
        v16 = CPST_STANDARD_DISPLAY_COLOR_MODE;
      }
      else
      {
        if ( v33 != 2 )
          wil::details::in1diag3::FailFast_Unexpected(
            retaddr,
            (void *)0xB1C,
            (unsigned int)"onecoreuap\\windows\\core\\color\\mscms\\calibration.cxx",
            v14);
        v16 = CPST_EXTENDED_DISPLAY_COLOR_MODE;
      }
      if ( ((v33 = v16,
             (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::GetImpl'::`2'::impl))
         || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl'::`2'::impl))
        && *(_DWORD *)(a4 + 36) )
      {
        v17 = 1;
        if ( (int)InternalModernColorGetProfile(v7, (unsigned __int16 **)&lpFileName) < 0 )
          AdvancedColorState = 1;
      }
      else
      {
        AdvancedColorState = GetDefaultProfileForSubType(v7, v13, v16, (unsigned __int16 **)&lpFileName);
        v17 = 1;
      }
      v6 = (WCHAR *)lpFileName;
      if ( AdvancedColorState
        || (AdvancedColorState = GetCalibrationDataFromProfile(lpFileName, (struct CalibrationData *)&v42, v15 == 1),
            AdvancedColorState >= 0) )
      {
        if ( AdvancedColorState == 1 )
        {
          DeleteCalibrationData((struct CalibrationData *)&v42, 1, 1, 1);
          v42 = v50;
          *(_OWORD *)v43 = *(_OWORD *)v51;
          v44 = v52;
          v35 = 1;
        }
        else
        {
          v17 = 0;
          v35 = 0;
          if ( !AdvancedColorState )
          {
            v35 = 0;
            if ( v43[0] )
              goto LABEL_38;
          }
        }
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl'::`2'::impl)
          || !v6
          || !v17 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles>::GetImpl'::`2'::impl)
            || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl'::`2'::impl) )
          {
            if ( *(_DWORD *)(a4 + 36) )
            {
              *(_QWORD *)setPacket = 0x18FFFFFFD7LL;
              *(LUID *)&setPacket[8] = v53.targetInfo.adapterId;
              *(_QWORD *)&setPacket[16] = v53.targetInfo.id | 0x100000000LL;
              v18 = DisplayConfigSetDeviceInfo((DISPLAYCONFIG_DEVICE_INFO_HEADER *)setPacket);
              if ( v18 < 0 )
                MicrosoftTelemetryAssertTriggeredArgs(v19, (unsigned int)v18);
            }
          }
          goto LABEL_44;
        }
LABEL_38:
        AdvancedColorState = SetMHC2DataToDisplay(v7, v6);
LABEL_44:
        if ( (unsigned int)dword_18009E048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E048, 0x200000000001LL) )
        {
          lpFileName = (LPCWSTR)0x2000000;
          v34 = v15 != 0;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (__int64)&dword_18009E048,
            (__int64)byte_1800917DB,
            v20,
            v21,
            (__int64)&v34,
            (__int64)&v33,
            (__int64)&lpFileName);
        }
        v22 = -1;
        do
          ++v22;
        while ( v7[v22] );
        *(_QWORD *)setPacket = v7;
        *(_QWORD *)&setPacket[8] = (unsigned int)(2 * v22 + 2);
        v34 = AdvancedColorState == 0;
        *(_QWORD *)&setPacket[16] = &v34;
        v55 = 4;
        EtwEventWrite(g_etwHandle, REFRESHING_CALIBRATION, 2, setPacket);
        if ( ((unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::GetImpl'::`2'::impl)
           || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl'::`2'::impl))
          && *(_DWORD *)(a4 + 36) )
        {
          v23 = hMonitor;
        }
        else
        {
          v23 = hMonitor;
          SetDisplayStateFromCalibrationData(
            *(struct IDxva2Wrapper **)(a4 + 24),
            hMonitor,
            (struct CalibrationData *)&v50);
        }
        if ( v43[1] )
        {
          if ( (int)ApplyAdvancedColorCalibration(v23, v43[1]) >= 0 )
            goto LABEL_60;
        }
        else
        {
          ApplyAdvancedColorCalibration(v23, v51[1]);
        }
        if ( *(_DWORD *)(a4 + 32) )
          AdvancedColorState = SetDisplayStateFromCalibrationData(
                                 *(struct IDxva2Wrapper **)(a4 + 24),
                                 v23,
                                 (struct CalibrationData *)&v42);
LABEL_60:
        if ( AdvancedColorState >= 0 )
          goto LABEL_63;
      }
    }
  }
LABEL_61:
  *(_DWORD *)(a4 + 12) = 1;
  if ( *(int *)(a4 + 16) >= 0 )
    *(_DWORD *)(a4 + 16) = AdvancedColorState;
LABEL_63:
  v24 = v36;
  if ( v36 )
  {
    *(_DWORD *)(a4 + 8) = 1;
    *(_DWORD *)(a4 + 20) = AdvancedColorState;
  }
  v25 = v24 == 0;
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x200000000000LL) )
  {
    v46 = 0x2000000;
    v34 = AdvancedColorState;
    v47 = *(_QWORD *)(a4 + 24);
    v36 = *(_DWORD *)(a4 + 20);
    v33 = *(_DWORD *)(a4 + 16);
    v41 = *(_DWORD *)(a4 + 12);
    LODWORD(hMonitor) = *(_DWORD *)(a4 + 8);
    v48 = *(const OLECHAR **)a4;
    v49 = v27;
    LODWORD(lpFileName) = v25;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v26,
      (__int64)&dword_180091B6C,
      (__int64)v27,
      v28,
      (__int64)&lpFileName,
      &v49,
      &v48,
      (__int64)&hMonitor,
      (__int64)&v41,
      (__int64)&v33,
      (__int64)&v36,
      (__int64)&v47,
      (__int64)&v34,
      (__int64)&v46);
  }
  if ( v7 )
    operator delete(v7);
  if ( v6 )
    operator delete(v6);
  DeleteCalibrationData((struct CalibrationData *)&v42, 1, 1, 1);
  if ( !v35 )
    DeleteCalibrationData((struct CalibrationData *)&v50, 1, 1, 1);
  if ( v8 >= 0 )
    RoUninitialize(v30, v29, v31);
  return v25;
}

```

## disassembly

```asm
0x180047f20  mov     [rsp-8+arg_8], rbx
0x180047f25  push    rbp
0x180047f26  push    rsi
0x180047f27  push    rdi
0x180047f28  push    r12
0x180047f2a  push    r13
0x180047f2c  push    r14
0x180047f2e  push    r15
0x180047f30  lea     rbp, [rsp-0A0h]
0x180047f38  sub     rsp, 1A0h
0x180047f3f  mov     rax, cs:__security_cookie
0x180047f46  xor     rax, rsp
0x180047f49  mov     [rbp+0D0h+var_40], rax
0x180047f50  mov     rsi, r9
0x180047f53  mov     rdi, rcx
0x180047f56  mov     [rbp+0D0h+hMonitor], rcx
0x180047f5a  xor     r13d, r13d
0x180047f5d  mov     r12d, r13d
0x180047f60  mov     [rbp+0D0h+lpFileName], r13
0x180047f64  mov     [rsp+1D0h+var_154], r13d
0x180047f69  mov     [rsp+1D0h+var_158], r13d
0x180047f6e  xorps   xmm0, xmm0
0x180047f71  xor     eax, eax
0x180047f73  movups  [rbp+0D0h+var_130], xmm0
0x180047f77  movups  xmmword ptr [rbp+0D0h+var_120], xmm0
0x180047f7b  mov     [rbp+0D0h+var_110], rax
0x180047f7f  xorps   xmm1, xmm1
0x180047f82  movups  [rbp+0D0h+var_E0], xmm1
0x180047f86  movups  xmmword ptr [rbp+0D0h+var_D0], xmm1
0x180047f8a  mov     [rbp+0D0h+var_C0], rax
0x180047f8e  mov     r14d, r13d
0x180047f91  xor     edx, edx; Val
0x180047f93  lea     r8d, [r13+48h]; Size
0x180047f97  lea     rcx, [rbp+0D0h+var_B0]; void *
0x180047f9b  call    memset_0
0x180047fa0  lea     r15d, [r13+1]
0x180047fa4  mov     ecx, r15d
0x180047fa7  call    cs:__imp_RoInitialize
0x180047fad  mov     ebx, eax
0x180047faf  mov     [rbp+0D0h+var_108], eax
0x180047fb2  mov     [rbp+0D0h+var_148], r13d
0x180047fb6  mov     rcx, [rsi+18h]
0x180047fba  mov     rax, [rcx]
0x180047fbd  lea     r8, [rbp+0D0h+var_148]
0x180047fc1  mov     rdx, rdi
0x180047fc4  mov     rax, [rax]
0x180047fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fcc  test    eax, eax
0x180047fce  jnz     short loc_180047FEE
0x180047fd0  call    cs:__imp_GetLastError
0x180047fd6  mov     edi, eax
0x180047fd8  test    eax, eax
0x180047fda  jle     loc_1800483E5
0x180047fe0  movzx   edi, ax
0x180047fe3  or      edi, 80070000h
0x180047fe9  jmp     loc_1800483E5
0x180047fee  cmp     [rbp+0D0h+var_148], r15d
0x180047ff2  jz      short loc_180048018
0x180047ff4  xor     r9d, r9d
0x180047ff7  xor     r8d, r8d
0x180047ffa  lea     rdx, CALIBRATION_MANAGEMENT_MULTIPLE_DEVICES
0x180048001  mov     rcx, cs:g_etwHandle
0x180048008  call    cs:__imp_EtwEventWrite
0x18004800e  mov     edi, 80004005h
0x180048013  jmp     loc_1800483F6
0x180048018  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004801f  mov     ecx, 208h; unsigned __int64
0x180048024  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180048029  mov     r14, rax
0x18004802c  test    rax, rax
0x18004802f  jnz     short loc_18004803B
0x180048031  mov     edi, 8007000Eh
0x180048036  jmp     loc_1800483F6
0x18004803b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer> `wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl(void)'::`2'::impl
0x180048042  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(void)
0x180048047  test    al, al
0x180048049  jz      short loc_18004804F
0x18004804b  mov     [r14], r13w
0x18004804f  mov     rdx, r14; unsigned __int16 *
0x180048052  mov     rcx, rdi; hMonitor
0x180048055  call    ?InternalTranslateHMonitorToICMName@@YAJPEAUHMONITOR__@@PEAG@Z; InternalTranslateHMonitorToICMName(HMONITOR__ *,ushort *)
0x18004805a  mov     edi, eax
0x18004805c  test    eax, eax
0x18004805e  js      loc_1800483F6
0x180048064  lea     rdx, [rbp+0D0h+var_B0]; struct DISPLAYCONFIG_PATH_INFO *
0x180048068  mov     rcx, r14; unsigned __int16 *
0x18004806b  call    ?InternalTranslateICMNameToPath@@YAJPEBGPEAUDISPLAYCONFIG_PATH_INFO@@@Z; InternalTranslateICMNameToPath(ushort const *,DISPLAYCONFIG_PATH_INFO *)
0x180048070  mov     edi, eax
0x180048072  test    eax, eax
0x180048074  js      loc_1800483F6
0x18004807a  mov     rcx, [rsi]
0x18004807d  test    rcx, rcx
0x180048080  jz      short loc_180048098
0x180048082  mov     rdx, r14
0x180048085  call    cs:__imp__o__wcsicmp
0x18004808b  test    eax, eax
0x18004808d  jnz     loc_18004811C
0x180048093  mov     [rsp+1D0h+var_154], r15d
0x180048098  mov     [rbp+0D0h+pUsePerUserProfiles], r13d
0x18004809c  lea     r8, [rbp+0D0h+pUsePerUserProfiles]; pUsePerUserProfiles
0x1800480a0  mov     edx, 6D6E7472h; dwDeviceClass
0x1800480a5  mov     rcx, r14; pDeviceName
0x1800480a8  call    WcsGetUsePerUserProfiles
0x1800480ad  test    eax, eax
0x1800480af  jz      loc_180047FD0
0x1800480b5  mov     r15d, r13d
0x1800480b8  cmp     [rbp+0D0h+pUsePerUserProfiles], r13d
0x1800480bc  mov     eax, 1
0x1800480c1  cmovnz  r15d, eax
0x1800480c5  mov     [rsp+1D0h+var_160], r13d
0x1800480ca  mov     [rsp+1D0h+var_1B0], r13; struct DISPLAYCONFIG_PATH_TARGET_INFO *
0x1800480cf  lea     rdx, [rsp+1D0h+var_160]; enum _DISPLAYCONFIG_ADVANCED_COLOR_MODE *
0x1800480d4  mov     rcx, r14; unsigned __int16 *
0x1800480d7  call    ?InternalGetAdvancedColorState@@YAJPEBGPEAW4_DISPLAYCONFIG_ADVANCED_COLOR_MODE@@PEAH2PEAUDISPLAYCONFIG_PATH_TARGET_INFO@@@Z; InternalGetAdvancedColorState(ushort const *,_DISPLAYCONFIG_ADVANCED_COLOR_MODE *,int *,int *,DISPLAYCONFIG_PATH_TARGET_INFO *)
0x1800480dc  mov     edi, eax
0x1800480de  test    eax, eax
0x1800480e0  js      loc_1800483F0
0x1800480e6  lea     rcx, [rbp+0D0h+var_E0]; struct CalibrationData *
0x1800480ea  call    ?GetDefaultCalibrationData@@YAJPEAUCalibrationData@@@Z; GetDefaultCalibrationData(CalibrationData *)
0x1800480ef  mov     edi, eax
0x1800480f1  test    eax, eax
0x1800480f3  js      loc_1800483F0
0x1800480f9  mov     r13d, [rsp+1D0h+var_160]
0x1800480fe  mov     ecx, r13d
0x180048101  test    r13d, r13d
0x180048104  jz      short loc_180048126
0x180048106  sub     ecx, 1
0x180048109  jz      short loc_180048126
0x18004810b  cmp     ecx, 1
0x18004810e  jnz     loc_18004857C
0x180048114  mov     r12d, 8
0x18004811a  jmp     short loc_18004812C
0x18004811c  mov     edi, 80070057h
0x180048121  jmp     loc_1800483F6
0x180048126  mov     r12d, 7
0x18004812c  mov     [rsp+1D0h+var_160], r12d
0x180048131  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ColorProfileAfterHibernate@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ColorProfileAfterHibernate@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ColorProfileAfterHibernate> `wil::Feature<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::GetImpl(void)'::`2'::impl
0x180048138  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ColorProfileAfterHibernate@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::__private_IsEnabled(void)
0x18004813d  test    al, al
0x18004813f  jnz     short loc_180048151
0x180048141  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer> `wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl(void)'::`2'::impl
0x180048148  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(void)
0x18004814d  test    al, al
0x18004814f  jz      short loc_180048172
0x180048151  cmp     dword ptr [rsi+24h], 0
0x180048155  jz      short loc_180048172
0x180048157  lea     rdx, [rbp+0D0h+lpFileName]; unsigned __int16 **
0x18004815b  mov     rcx, r14; unsigned __int16 *
0x18004815e  call    ?InternalModernColorGetProfile@@YAJPEBGPEAPEAG@Z; InternalModernColorGetProfile(ushort const *,ushort * *)
0x180048163  mov     r15d, 1
0x180048169  test    eax, eax
0x18004816b  jns     short loc_18004818C
0x18004816d  mov     edi, r15d
0x180048170  jmp     short loc_18004818C
0x180048172  lea     r9, [rbp+0D0h+lpFileName]; unsigned __int16 **
0x180048176  mov     r8d, r12d; enum COLORPROFILESUBTYPE
0x180048179  mov     edx, r15d; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18004817c  mov     rcx, r14; unsigned __int16 *
0x18004817f  call    ?GetDefaultProfileForSubType@@YAJPEAGW4WCS_PROFILE_MANAGEMENT_SCOPE@@W4COLORPROFILESUBTYPE@@PEAPEAG@Z; GetDefaultProfileForSubType(ushort *,WCS_PROFILE_MANAGEMENT_SCOPE,COLORPROFILESUBTYPE,ushort * *)
0x180048184  mov     edi, eax
0x180048186  mov     r15d, 1
0x18004818c  mov     r12, [rbp+0D0h+lpFileName]
0x180048190  test    edi, edi
0x180048192  jnz     short loc_1800481B4
0x180048194  xor     r8d, r8d
0x180048197  cmp     r13d, r15d
0x18004819a  setz    r8b; int
0x18004819e  lea     rdx, [rbp+0D0h+var_130]; struct CalibrationData *
0x1800481a2  mov     rcx, r12; lpFileName
0x1800481a5  call    ?GetCalibrationDataFromProfile@@YAJPEBGPEAUCalibrationData@@H@Z; GetCalibrationDataFromProfile(ushort const *,CalibrationData *,int)
0x1800481aa  mov     edi, eax
0x1800481ac  test    eax, eax
0x1800481ae  js      loc_1800483EB
0x1800481b4  cmp     edi, r15d
0x1800481b7  jnz     short loc_1800481EC
0x1800481b9  mov     r9d, r15d; int
0x1800481bc  mov     r8d, r15d; int
0x1800481bf  mov     edx, r15d; int
0x1800481c2  lea     rcx, [rbp+0D0h+var_130]; struct CalibrationData *
0x1800481c6  call    ?DeleteCalibrationData@@YAXPEAUCalibrationData@@HHH@Z; DeleteCalibrationData(CalibrationData *,int,int,int)
0x1800481cb  movups  xmm0, [rbp+0D0h+var_E0]
0x1800481cf  movups  [rbp+0D0h+var_130], xmm0
0x1800481d3  movups  xmm1, xmmword ptr [rbp+0D0h+var_D0]
0x1800481d7  movups  xmmword ptr [rbp+0D0h+var_120], xmm1
0x1800481db  movsd   xmm0, [rbp+0D0h+var_C0]
0x1800481e0  movsd   [rbp+0D0h+var_110], xmm0
0x1800481e5  mov     [rsp+1D0h+var_158], r15d
0x1800481ea  jmp     short loc_180048203
0x1800481ec  xor     r15d, r15d
0x1800481ef  mov     [rsp+1D0h+var_158], r15d
0x1800481f4  test    edi, edi
0x1800481f6  jnz     short loc_180048203
0x1800481f8  mov     [rsp+1D0h+var_158], r15d
0x1800481fd  cmp     [rbp+0D0h+var_120], r15
0x180048201  jnz     short loc_18004821D
0x180048203  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer> `wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl(void)'::`2'::impl
0x18004820a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(void)
0x18004820f  test    al, al
0x180048211  jz      short loc_18004822C
0x180048213  test    r12, r12
0x180048216  jz      short loc_18004822C
0x180048218  test    r15d, r15d
0x18004821b  jz      short loc_18004822C
0x18004821d  mov     rdx, r12; lpFileName
0x180048220  mov     rcx, r14; unsigned __int16 *
0x180048223  call    ?SetMHC2DataToDisplay@@YAJPEBG0@Z; SetMHC2DataToDisplay(ushort const *,ushort const *)
0x180048228  mov     edi, eax
0x18004822a  jmp     short loc_180048291
0x18004822c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles> `wil::Feature<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles>::GetImpl(void)'::`2'::impl
0x180048233  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepKernelColorimetryUpToDateWithProfiles>::__private_IsEnabled(void)
0x180048238  test    al, al
0x18004823a  jnz     short loc_18004824C
0x18004823c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer> `wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl(void)'::`2'::impl
0x180048243  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(void)
0x180048248  test    al, al
0x18004824a  jz      short loc_180048291
0x18004824c  cmp     dword ptr [rsi+24h], 0
0x180048250  jz      short loc_180048291
0x180048252  mov     dword ptr [rbp+0D0h+setPacket], 0FFFFFFD7h
0x180048259  mov     dword ptr [rbp+0D0h+setPacket+4], 18h
0x180048260  mov     rax, qword ptr [rbp+0D0h+var_B0.targetInfo.adapterId.LowPart]
0x180048264  mov     qword ptr [rbp+0D0h+setPacket+8], rax
0x180048268  mov     eax, [rbp+0D0h+var_B0.targetInfo.id]
0x18004826b  mov     dword ptr [rbp+0D0h+setPacket+10h], eax
0x180048271  mov     eax, 1
0x180048276  mov     dword ptr [rbp+0D0h+setPacket+14h], eax
0x18004827c  lea     rcx, [rbp+0D0h+setPacket]; setPacket
0x180048280  call    cs:__imp_DisplayConfigSetDeviceInfo
0x180048286  test    eax, eax
0x180048288  jns     short loc_180048291
0x18004828a  mov     edx, eax
0x18004828c  call    MicrosoftTelemetryAssertTriggeredArgs
0x180048291  mov     eax, cs:dword_18009E048
0x180048297  cmp     eax, 5
0x18004829a  jbe     short loc_180048302
0x18004829c  mov     rdx, 200000000001h
0x1800482a6  lea     rcx, dword_18009E048
0x1800482ad  call    _tlgKeywordOn
0x1800482b2  test    al, al
0x1800482b4  jz      short loc_180048302
0x1800482b6  mov     [rbp+0D0h+lpFileName], 2000000h
0x1800482be  mov     eax, [rsp+1D0h+var_160]
0x1800482c2  mov     [rsp+1D0h+var_160], eax
0x1800482c6  xor     eax, eax
0x1800482c8  test    r13d, r13d
0x1800482cb  setnz   al
0x1800482ce  mov     [rsp+1D0h+var_15C], eax
0x1800482d2  lea     rax, [rbp+0D0h+lpFileName]
0x1800482d6  mov     [rsp+1D0h+var_1A0], rax
0x1800482db  lea     rax, [rsp+1D0h+var_160]
0x1800482e0  mov     [rsp+1D0h+var_1A8], rax
0x1800482e5  lea     rax, [rsp+1D0h+var_15C]
0x1800482ea  mov     [rsp+1D0h+var_1B0], rax
0x1800482ef  lea     rdx, byte_1800917DB
0x1800482f6  lea     rcx, dword_18009E048
0x1800482fd  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180048302  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048306  xor     r13d, r13d
0x180048309  inc     rax
0x18004830c  cmp     [r14+rax*2], r13w
0x180048311  jnz     short loc_180048309
0x180048313  lea     rax, ds:2[rax*2]
0x18004831b  mov     qword ptr [rbp+0D0h+setPacket], r14
0x18004831f  mov     dword ptr [rbp+0D0h+setPacket+8], eax
0x180048322  mov     dword ptr [rbp+0D0h+setPacket+0Ch], r13d
0x180048326  mov     eax, r13d
0x180048329  test    edi, edi
0x18004832b  setz    al
0x18004832e  mov     [rsp+1D0h+var_15C], eax
0x180048332  lea     rax, [rsp+1D0h+var_15C]
0x180048337  mov     qword ptr [rbp+0D0h+setPacket+10h], rax
0x18004833e  mov     [rbp+0D0h+var_48], 4
0x180048349  lea     r9, [rbp+0D0h+setPacket]
0x18004834d  mov     r8d, 2
0x180048353  lea     rdx, REFRESHING_CALIBRATION
0x18004835a  mov     rcx, cs:g_etwHandle
0x180048361  call    cs:__imp_EtwEventWrite
0x180048367  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ColorProfileAfterHibernate@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ColorProfileAfterHibernate@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ColorProfileAfterHibernate> `wil::Feature<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::GetImpl(void)'::`2'::impl
0x18004836e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ColorProfileAfterHibernate@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ColorProfileAfterHibernate>::__private_IsEnabled(void)
0x180048373  test    al, al
0x180048375  jnz     short loc_180048387
0x180048377  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer> `wil::Feature<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::GetImpl(void)'::`2'::impl
0x18004837e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UseIntermediaryColorServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseIntermediaryColorServer>::__private_IsEnabled(void)
0x180048383  test    al, al
0x180048385  jz      short loc_18004838D
0x180048387  cmp     [rsi+24h], r13d
0x18004838b  jnz     short loc_1800483A3
0x18004838d  lea     r8, [rbp+0D0h+var_E0]; struct CalibrationData *
0x180048391  mov     r15, [rbp+0D0h+hMonitor]
0x180048395  mov     rdx, r15; HMONITOR
0x180048398  mov     rcx, [rsi+18h]; struct IDxva2Wrapper *
0x18004839c  call    ?SetDisplayStateFromCalibrationData@@YAJPEAVIDxva2Wrapper@@PEAUHMONITOR__@@PEAUCalibrationData@@@Z; SetDisplayStateFromCalibrationData(IDxva2Wrapper *,HMONITOR__ *,CalibrationData *)
0x1800483a1  jmp     short loc_1800483A7
0x1800483a3  mov     r15, [rbp+0D0h+hMonitor]
0x1800483a7  mov     rdx, [rbp+0D0h+var_120+8]; struct AdvancedColorCalibrationData *
0x1800483ab  mov     rcx, r15; hMonitor
0x1800483ae  test    rdx, rdx
0x1800483b1  jz      short loc_1800483BE
0x1800483b3  call    ?ApplyAdvancedColorCalibration@@YAJPEAUHMONITOR__@@PEAUAdvancedColorCalibrationData@@@Z; ApplyAdvancedColorCalibration(HMONITOR__ *,AdvancedColorCalibrationData *)
0x1800483b8  test    eax, eax
  ... truncated ...
```
