# LocalSpoolerTelemetry::LogJobStarted(INIJOB *,int,ushort const *,ushort const *,unsigned __int64,ushort const *)

- ea: `0x18004dbcc`
- end: `0x18004e38f`
- name: `?LogJobStarted@LocalSpoolerTelemetry@@SAXPEAVINIJOB@@HPEBG1_K1@Z`
- size: `1987`
- prototype: `void __fastcall(struct INIJOB *, int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting`

## callers

- `0x18005fe20`
- `0x1800602a8`

## callees

- `0x180002f2c`
- `0x18001366c`
- `0x180014130`
- `0x180025f34`
- `0x180026fe4`
- `0x18003303c`
- `0x180035e2c`
- `0x1800419cc`
- `0x180042644`
- `0x180046650`
- `0x180047330`
- `0x18004c9a0`
- `0x18004d01c`
- `0x18004d06c`
- `0x18004d208`
- `0x18004dbcc`
- `0x18004ef4c`
- `0x180053404`

## import_xrefs

- `ntdll!NtSetInformationProcess` at `0x18004dd6a`
- `ntdll!NtSetInformationProcess` at `0x18004dd6a`
- `ntdll!EtwCheckCoverage` at `0x18004dca7`
- `ntdll!EtwCheckCoverage` at `0x18004dd4b`
- `ntdll!EtwCheckCoverage` at `0x18004dca7`
- `ntdll!EtwCheckCoverage` at `0x18004dd4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dc21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dc21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e35f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e35f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18004dee4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18004dee4`
- `SPOOLSS!DllFreeSplStr` at `0x18004e349`
- `SPOOLSS!DllFreeSplStr` at `0x18004e349`
- `SPOOLSS!DllFreeSplMem` at `0x18004dd24`
- `SPOOLSS!DllFreeSplMem` at `0x18004e33b`
- `SPOOLSS!DllFreeSplMem` at `0x18004dd24`
- `SPOOLSS!DllFreeSplMem` at `0x18004e33b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall LocalSpoolerTelemetry::LogJobStarted(
        struct INIJOB *a1,
        int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int64 a5,
        const unsigned __int16 *a6)
{
  DWORD LastError; // ebx
  int v9; // r15d
  int v10; // r12d
  __int64 v11; // rcx
  int v12; // r13d
  __int64 v13; // r14
  int v14; // r14d
  char **v15; // r8
  __int64 v16; // rax
  unsigned __int16 *v17; // rcx
  __int64 v18; // r8
  int v19; // eax
  int v20; // edx
  __int64 WppConfigInfo; // rax
  __int64 v22; // rax
  const struct _tlgProvider_t *v23; // rax
  __int128 *v24; // rcx
  const unsigned __int16 *v25; // rsi
  const unsigned __int16 *v26; // rax
  const unsigned __int16 *v27; // rax
  const unsigned __int16 *v28; // rax
  const WCHAR *v29; // rcx
  LPWSTR ExtensionW; // rax
  __int64 v31; // rax
  BOOL v32; // eax
  wchar_t *v33; // rax
  int v34; // ecx
  int v35; // ecx
  int v36; // r9d
  __int64 v37; // rcx
  const unsigned __int16 *v38; // rax
  __int64 v39; // rdx
  int v40; // r8d
  __int64 *v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rax
  const unsigned __int16 *v44; // rax
  const unsigned __int16 *v45; // rax
  __int64 v46; // r13
  __int64 v47; // r12
  int v48; // ecx
  const unsigned __int16 *v49; // rcx
  const unsigned __int16 *v50; // [rsp+20h] [rbp-1B0h]
  int v51; // [rsp+150h] [rbp-80h] BYREF
  _DWORD v52[3]; // [rsp+154h] [rbp-7Ch] BYREF
  int v53; // [rsp+160h] [rbp-70h] BYREF
  int PrintingProcessName; // [rsp+164h] [rbp-6Ch] BYREF
  int v55; // [rsp+168h] [rbp-68h] BYREF
  __int64 v56; // [rsp+170h] [rbp-60h] BYREF
  int v57[2]; // [rsp+178h] [rbp-58h] BYREF
  const unsigned __int16 *v58; // [rsp+180h] [rbp-50h] BYREF
  const unsigned __int16 *v59; // [rsp+188h] [rbp-48h] BYREF
  BOOL v60; // [rsp+190h] [rbp-40h] BYREF
  int v61; // [rsp+194h] [rbp-3Ch] BYREF
  int v62; // [rsp+198h] [rbp-38h] BYREF
  int v63; // [rsp+19Ch] [rbp-34h] BYREF
  int v64; // [rsp+1A0h] [rbp-30h] BYREF
  int v65; // [rsp+1A4h] [rbp-2Ch] BYREF
  int IsFaxDevice; // [rsp+1A8h] [rbp-28h] BYREF
  int v67; // [rsp+1ACh] [rbp-24h] BYREF
  int v68; // [rsp+1B0h] [rbp-20h] BYREF
  int v69; // [rsp+1B4h] [rbp-1Ch] BYREF
  __int64 v70; // [rsp+1B8h] [rbp-18h] BYREF
  const unsigned __int16 *v71; // [rsp+1C0h] [rbp-10h] BYREF
  unsigned __int64 v72; // [rsp+1C8h] [rbp-8h] BYREF
  int v73; // [rsp+1D0h] [rbp+0h] BYREF
  const unsigned __int16 *v74; // [rsp+1D8h] [rbp+8h] BYREF
  const unsigned __int16 *v75; // [rsp+1E0h] [rbp+10h] BYREF
  UINT32 packageFullNameLength; // [rsp+1E8h] [rbp+18h] BYREF
  __int128 *v77; // [rsp+1F0h] [rbp+20h] BYREF
  const unsigned __int16 *v78; // [rsp+1F8h] [rbp+28h] BYREF
  const unsigned __int16 *v79; // [rsp+200h] [rbp+30h] BYREF
  const unsigned __int16 *v80; // [rsp+208h] [rbp+38h] BYREF
  __int64 v81; // [rsp+210h] [rbp+40h] BYREF
  __int64 v82; // [rsp+218h] [rbp+48h] BYREF
  LPWSTR v83; // [rsp+220h] [rbp+50h] BYREF
  unsigned __int16 *IDList; // [rsp+228h] [rbp+58h] BYREF
  wchar_t *v85; // [rsp+230h] [rbp+60h] BYREF
  __int64 v86; // [rsp+238h] [rbp+68h] BYREF
  const unsigned __int16 *v87; // [rsp+240h] [rbp+70h] BYREF
  __int64 v88; // [rsp+248h] [rbp+78h] BYREF
  const unsigned __int16 *v89; // [rsp+250h] [rbp+80h] BYREF
  __int64 v90; // [rsp+258h] [rbp+88h] BYREF
  const unsigned __int16 *v91; // [rsp+260h] [rbp+90h] BYREF
  const unsigned __int16 *v92; // [rsp+268h] [rbp+98h] BYREF
  __int64 v93; // [rsp+270h] [rbp+A0h] BYREF
  _OWORD *v94; // [rsp+278h] [rbp+A8h] BYREF
  __int64 v95; // [rsp+280h] [rbp+B0h] BYREF
  const struct _tlgProvider_t *v96; // [rsp+288h] [rbp+B8h]
  int v97[2]; // [rsp+290h] [rbp+C0h] BYREF
  __int128 v98; // [rsp+298h] [rbp+C8h] BYREF
  __int64 v99; // [rsp+2A8h] [rbp+D8h]
  unsigned __int64 v100; // [rsp+2B0h] [rbp+E0h]
  _OWORD v101[2]; // [rsp+2B8h] [rbp+E8h] BYREF
  wchar_t Filename[264]; // [rsp+2E0h] [rbp+110h] BYREF

  v71 = a4;
  v75 = a3;
  LODWORD(v59) = a2;
  *(_QWORD *)v97 = a1;
  v73 = a2;
  v72 = a5;
  LastError = GetLastError();
  LODWORD(v74) = LastError;
  v9 = 0;
  v51 = 0;
  v10 = 1;
  LODWORD(v58) = 1;
  memset_0(Filename, 0, 0x208u);
  packageFullNameLength = 260;
  v12 = 0;
  v53 = 0;
  memset(v52, 0, sizeof(v52));
  v56 = 0;
  *(_QWORD *)v57 = 0;
  v13 = *((_QWORD *)a1 + 12);
  if ( v13 )
  {
    v9 = 1;
    v55 = 1;
    v14 = *(_DWORD *)(v13 + 200) & 0x1000;
    if ( v14 )
    {
      if ( (unsigned int)dword_18013D24C < MEMORY[0x7FFE037C] && !(unsigned __int8)EtwCheckCoverage(&off_18013D240) )
      {
        v15 = &off_18013D240;
LABEL_22:
        NtSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessAffinityMask|0x40, v15, 0x18u);
        goto LABEL_23;
      }
      goto LABEL_23;
    }
  }
  else
  {
    v55 = 0;
    v14 = 0;
  }
  if ( (unsigned int)InternalGetDefaultPrinter(v11, 0, 0, 0, v50, (unsigned __int16 **)&v52[1]) )
  {
    v16 = *((_QWORD *)a1 + 11);
    if ( a2 )
      v17 = *(unsigned __int16 **)(v16 + 80);
    else
      v17 = *(unsigned __int16 **)(v16 + 24);
    v18 = *(_QWORD *)&v52[1] - (_QWORD)v17;
    do
    {
      v19 = *(unsigned __int16 *)((char *)v17 + v18);
      v20 = *v17 - v19;
      if ( v20 )
        break;
      ++v17;
    }
    while ( v19 );
    if ( !v20 )
      v12 = 1;
    v53 = v12;
  }
  if ( *(_QWORD *)&v52[1] )
    DllFreeSplMem(*(_QWORD *)&v52[1]);
  GetLegacyDefaultMode(0);
  if ( (unsigned int)dword_18013D1CC < MEMORY[0x7FFE037C] && !(unsigned __int8)EtwCheckCoverage(&off_18013D1C0) )
  {
    v15 = &off_18013D1C0;
    goto LABEL_22;
  }
LABEL_23:
  PrintingProcessName = GetPrintingProcessName(Filename, &packageFullNameLength);
  if ( v9 )
  {
    v52[0] = ConvertDriverDateToLPWSTR(*(_QWORD *)(*((_QWORD *)a1 + 12) + 112LL), &v56, &v51);
    ConvertDriverVersionToLPWSTR(*(_QWORD *)(*((_QWORD *)a1 + 12) + 120LL), v57, &v51);
  }
  WppConfigInfo = LocalSpoolerTelemetry::GetWppConfigInfo(v101);
  v51 = *(_DWORD *)WppConfigInfo;
  v70 = *(_QWORD *)(WppConfigInfo + 8);
  *(_QWORD *)&v52[1] = *(_QWORD *)(WppConfigInfo + 16);
  v98 = 0;
  v99 = 0;
  v100 = 7;
  LOWORD(v98) = 0;
  if ( v72 )
  {
    v22 = LocalSpoolerTelemetry::ConvertPackageVersion(v101, v72);
    std::wstring::operator=(&v98, v22);
    std::wstring::_Tidy_deallocate(v101);
  }
  else
  {
    v99 = 0;
    LOWORD(v98) = 0;
  }
  v23 = LocalSpoolerLogging::Provider();
  v96 = v23;
  if ( *(_DWORD *)v23 <= 5u || !(unsigned __int8)tlgKeywordOn(v23, 0x400000000000LL) )
  {
    v46 = v56;
    v47 = *(_QWORD *)v57;
    goto LABEL_78;
  }
  v24 = &v98;
  if ( v100 > 7 )
    v24 = (__int128 *)v98;
  v77 = v24;
  v25 = &qword_1800EBF90;
  v26 = v71;
  if ( !v71 )
    v26 = &qword_1800EBF90;
  v78 = v26;
  v27 = v75;
  if ( !v75 )
    v27 = &qword_1800EBF90;
  v79 = v27;
  v28 = a6;
  if ( !a6 )
    v28 = &qword_1800EBF90;
  v80 = v28;
  v81 = *(_QWORD *)&v52[1];
  v82 = v70;
  v29 = (const WCHAR *)*((_QWORD *)a1 + 10);
  if ( v29 )
    ExtensionW = PathFindExtensionW(v29);
  else
    ExtensionW = 0;
  v83 = ExtensionW;
  v31 = *((_QWORD *)a1 + 11);
  v32 = (*(_BYTE *)(v31 + 136) & 4) == 0 && *(char *)(v31 + 320) >= 0 && (*(_DWORD *)(v31 + 152) & 0x400) == 0;
  v60 = v32;
  IDList = _INIPRINTER::GetIDList(
             *((_INIPRINTER **)a1 + 11),
             &DEVPKEY_Device_HardwareIds,
             (unsigned __int16 **)(*((_QWORD *)a1 + 11) + 560LL));
  v33 = Filename;
  if ( !PrintingProcessName )
    v33 = (wchar_t *)&qword_1800EBF90;
  v85 = v33;
  v61 = (int)v58;
  v62 = v12;
  v63 = *(_DWORD *)(*((_QWORD *)a1 + 11) + 152LL);
  if ( v9 )
    v34 = *(_DWORD *)(*((_QWORD *)a1 + 12) + 200LL) & 8;
  else
    v34 = 0;
  v64 = v34;
  if ( v9 )
    v35 = (*(_DWORD *)(*((_QWORD *)a1 + 12) + 200LL) >> 1) & 1;
  else
    v35 = 0;
  v65 = v35;
  if ( !v9 || (*(_BYTE *)(*((_QWORD *)a1 + 12) + 200LL) & 0x40) == 0 )
    v10 = 0;
  IsFaxDevice = _INIPRINTER::IsFaxDevice(*((_INIPRINTER **)a1 + 11), v10);
  v67 = v9 != 0 ? v14 : 0;
  if ( v9 && (v37 = *(_QWORD *)(*((_QWORD *)a1 + 12) + 248LL)) != 0 )
    v38 = *(const unsigned __int16 **)(v37 + 24);
  else
    v38 = &qword_1800EBF90;
  v58 = v38;
  v39 = *((_QWORD *)a1 + 11);
  v86 = *(_QWORD *)(*(_QWORD *)(v39 + 56) + 24LL);
  v68 = *(_DWORD *)(v39 + 528);
  v69 = *((_DWORD *)a1 + 8);
  LODWORD(v70) = *(_DWORD *)(*((_QWORD *)a1 + 11) + 308LL);
  v40 = (int)v59;
  LODWORD(v75) = (_DWORD)v59;
  v41 = *(__int64 **)(*((_QWORD *)a1 + 11) + 312LL);
  if ( !v41 )
  {
    v74 = &qword_1800EBF90;
    goto LABEL_65;
  }
  v42 = *v41;
  v74 = *(const unsigned __int16 **)(*v41 + 24);
  v43 = *(_QWORD *)(v42 + 96);
  if ( !v43 )
  {
LABEL_65:
    v44 = &qword_1800EBF90;
    goto LABEL_66;
  }
  v44 = *(const unsigned __int16 **)(v43 + 24);
LABEL_66:
  v59 = v44;
  v87 = &qword_1800EBF90;
  v88 = *((_QWORD *)a1 + 16);
  v45 = &qword_1800EBF90;
  v46 = v56;
  if ( v52[0] )
    v45 = (const unsigned __int16 *)v56;
  v89 = v45;
  v47 = *(_QWORD *)v57;
  v90 = *(_QWORD *)v57;
  if ( v9 )
    v48 = *(_DWORD *)(*((_QWORD *)a1 + 12) + 236LL);
  else
    v48 = 0;
  LODWORD(v71) = v48;
  if ( v9 )
    v49 = *(const unsigned __int16 **)(*((_QWORD *)a1 + 12) + 24LL);
  else
    v49 = &qword_1800EBF90;
  v91 = v49;
  LODWORD(v72) = *(_DWORD *)(*((_QWORD *)a1 + 11) + 136LL);
  if ( v40 )
    v25 = *(const unsigned __int16 **)(*((_QWORD *)a1 + 11) + 80LL);
  v92 = v25;
  v93 = *(_QWORD *)(*((_QWORD *)a1 + 11) + 24LL);
  v52[1] = *((_DWORD *)a1 + 10);
  v101[0] = *(_OWORD *)((char *)a1 + 600);
  v94 = v101;
  v95 = 0x1000000;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
    (_DWORD)v96,
    (unsigned int)&word_18012A0C6,
    v40,
    v36,
    (__int64)&v95,
    (__int64)&v94,
    (__int64)&v52[1],
    (__int64)&v93,
    (__int64)&v92,
    (__int64)&v72,
    (__int64)&v91,
    (__int64)&v71,
    (__int64)&v90,
    (__int64)&v89,
    (__int64)&v88,
    (__int64)&v87,
    (__int64)&v59,
    (__int64)&v74,
    (__int64)&v75,
    (__int64)&v70,
    (__int64)&v69,
    (__int64)&v68,
    (__int64)&v86,
    (__int64)&v58,
    (__int64)&v67,
    (__int64)&IsFaxDevice,
    (__int64)&v65,
    (__int64)&v64,
    (__int64)&v63,
    (__int64)&v62,
    (__int64)&v61,
    (__int64)&v85,
    (__int64)&IDList,
    (__int64)&v60,
    (__int64)&v83,
    (__int64)&v51,
    (__int64)&v82,
    (__int64)&v81,
    (__int64)&v80,
    (__int64)&v79,
    (__int64)&v78,
    (__int64)&v77);
LABEL_78:
  if ( v14 )
    MS3DLocalSpoolerTelemetry::JobStarted<INIJOB * &,int &,int &,unsigned short * &,int &,unsigned short * &,int &,unsigned short (&)[260],int &>(
      (int)v97,
      (int)&v73,
      (int)&v55,
      (int)v57,
      (__int64)v52,
      (__int64)&v56,
      (__int64)&PrintingProcessName,
      Filename,
      (__int64)&v53);
  if ( v46 )
    DllFreeSplMem(v46);
  if ( v47 )
    DllFreeSplStr(v47);
  std::wstring::_Tidy_deallocate(&v98);
  SetLastError(LastError);
}

```

## disassembly

```asm
0x18004dbcc  mov     [rsp-8+arg_10], rbx
0x18004dbd1  push    rbp
0x18004dbd2  push    rsi
0x18004dbd3  push    rdi
0x18004dbd4  push    r12
0x18004dbd6  push    r13
0x18004dbd8  push    r14
0x18004dbda  push    r15
0x18004dbdc  lea     rbp, [rsp-330h]
0x18004dbe4  sub     rsp, 500h
0x18004dbeb  mov     rax, cs:__security_cookie
0x18004dbf2  xor     rax, rsp
0x18004dbf5  mov     [rbp+360h+var_40], rax
0x18004dbfc  mov     [rbp+360h+var_370], r9
0x18004dc00  mov     [rbp+360h+var_350], r8
0x18004dc04  mov     esi, edx
0x18004dc06  mov     dword ptr [rbp+360h+var_3A8], edx
0x18004dc09  mov     rdi, rcx
0x18004dc0c  mov     qword ptr [rbp+360h+var_2A0], rcx
0x18004dc13  mov     [rbp+360h+var_360], edx
0x18004dc16  mov     rax, [rbp+360h+arg_20]
0x18004dc1d  mov     [rbp+360h+var_368], rax
0x18004dc21  call    cs:__imp_GetLastError
0x18004dc27  mov     ebx, eax
0x18004dc29  mov     dword ptr [rbp+360h+var_358], eax
0x18004dc2c  xor     r15d, r15d
0x18004dc2f  mov     [rbp+360h+var_3E0], r15d
0x18004dc33  mov     qword ptr [rbp+360h+var_3DC+4], r15
0x18004dc37  lea     r12d, [r15+1]
0x18004dc3b  mov     dword ptr [rbp+360h+var_3B0], r12d
0x18004dc3f  xor     edx, edx; Val
0x18004dc41  mov     r8d, 208h; Size
0x18004dc47  lea     rcx, [rbp+360h+Filename]; void *
0x18004dc4e  call    memset_0
0x18004dc53  mov     [rbp+360h+packageFullNameLength], 104h
0x18004dc5a  mov     r13d, r15d
0x18004dc5d  mov     dword ptr [rbp+360h+var_3D0], r15d
0x18004dc61  mov     dword ptr [rbp+360h+var_3DC], r15d
0x18004dc65  mov     [rbp+360h+var_3C0], r15
0x18004dc69  mov     qword ptr [rbp+360h+var_3B8], r15
0x18004dc6d  mov     r14, [rdi+60h]
0x18004dc71  test    r14, r14
0x18004dc74  jz      short loc_18004DCC1
0x18004dc76  mov     r15d, r12d
0x18004dc79  mov     [rbp+360h+var_3C8], r12d
0x18004dc7d  mov     r14d, [r14+0C8h]
0x18004dc84  and     r14d, 1000h
0x18004dc8b  jz      short loc_18004DCC8
0x18004dc8d  mov     eax, ds:7FFE037Ch; __annotation("Debug", "TelemetryCoverage", "Printing_Job_Start_3D")
0x18004dc94  cmp     cs:dword_18013D24C, eax
0x18004dc9a  jnb     loc_18004DD70
0x18004dca0  lea     rcx, off_18013D240; "Printing_Job_Start_3D"
0x18004dca7  call    cs:__imp_EtwCheckCoverage
0x18004dcad  test    al, al
0x18004dcaf  jnz     loc_18004DD70
0x18004dcb5  lea     r8, off_18013D240; "Printing_Job_Start_3D"
0x18004dcbc  jmp     loc_18004DD5C
0x18004dcc1  mov     [rbp+360h+var_3C8], r15d
0x18004dcc5  xor     r14d, r14d
0x18004dcc8  lea     rax, [rbp+360h+var_3DC+4]
0x18004dccc  mov     [rsp+530h+var_508], rax; unsigned __int16 **
0x18004dcd1  xor     r9d, r9d; unsigned __int16 *
0x18004dcd4  xor     r8d, r8d; unsigned __int16 *
0x18004dcd7  xor     edx, edx; int
0x18004dcd9  call    ?InternalGetDefaultPrinter@@YAHHHPEBG00PEAPEAG@Z; InternalGetDefaultPrinter(int,int,ushort const *,ushort const *,ushort const *,ushort * *)
0x18004dcde  mov     r9, qword ptr [rbp+360h+var_3DC+4]
0x18004dce2  test    eax, eax
0x18004dce4  jz      short loc_18004DD1C
0x18004dce6  mov     rax, [rdi+58h]
0x18004dcea  test    esi, esi
0x18004dcec  jz      short loc_18004DCF4
0x18004dcee  mov     rcx, [rax+50h]
0x18004dcf2  jmp     short loc_18004DCF8
0x18004dcf4  mov     rcx, [rax+18h]
0x18004dcf8  mov     r8, r9
0x18004dcfb  sub     r8, rcx
0x18004dcfe  movzx   edx, word ptr [rcx]
0x18004dd01  movzx   eax, word ptr [rcx+r8]
0x18004dd06  sub     edx, eax
0x18004dd08  jnz     short loc_18004DD12
0x18004dd0a  add     rcx, 2
0x18004dd0e  test    eax, eax
0x18004dd10  jnz     short loc_18004DCFE
0x18004dd12  test    edx, edx
0x18004dd14  cmovz   r13d, r12d
0x18004dd18  mov     dword ptr [rbp+360h+var_3D0], r13d
0x18004dd1c  test    r9, r9
0x18004dd1f  jz      short loc_18004DD2A
0x18004dd21  mov     rcx, r9
0x18004dd24  call    cs:__imp_DllFreeSplMem
0x18004dd2a  lea     rdx, [rbp+360h+var_3B0]
0x18004dd2e  xor     ecx, ecx; lpSubKey
0x18004dd30  call    GetLegacyDefaultMode
0x18004dd35  mov     eax, ds:7FFE037Ch; __annotation("Debug", "TelemetryCoverage", "Printing_Job_Start")
0x18004dd3c  cmp     cs:dword_18013D1CC, eax
0x18004dd42  jnb     short loc_18004DD70
0x18004dd44  lea     rcx, off_18013D1C0; "Printing_Job_Start"
0x18004dd4b  call    cs:__imp_EtwCheckCoverage
0x18004dd51  test    al, al
0x18004dd53  jnz     short loc_18004DD70
0x18004dd55  lea     r8, off_18013D1C0; ProcessInformation
0x18004dd5c  mov     r9d, 18h; ProcessInformationLength
0x18004dd62  lea     edx, [r9+3Dh]; ProcessInformationClass
0x18004dd66  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18004dd6a  call    cs:__imp_NtSetInformationProcess
0x18004dd70  lea     rdx, [rbp+360h+packageFullNameLength]; packageFullNameLength
0x18004dd74  lea     rcx, [rbp+360h+Filename]; Filename
0x18004dd7b  call    GetPrintingProcessName
0x18004dd80  mov     dword ptr [rbp+360h+var_3D0+4], eax
0x18004dd83  test    r15d, r15d
0x18004dd86  jz      short loc_18004DDB5
0x18004dd88  mov     rcx, [rdi+60h]
0x18004dd8c  lea     r8, [rbp+360h+var_3E0]
0x18004dd90  lea     rdx, [rbp+360h+var_3C0]
0x18004dd94  mov     rcx, [rcx+70h]
0x18004dd98  call    ConvertDriverDateToLPWSTR
0x18004dd9d  mov     dword ptr [rbp+360h+var_3DC], eax
0x18004dda0  mov     rcx, [rdi+60h]
0x18004dda4  lea     r8, [rbp+360h+var_3E0]
0x18004dda8  lea     rdx, [rbp+360h+var_3B8]
0x18004ddac  mov     rcx, [rcx+78h]
0x18004ddb0  call    ConvertDriverVersionToLPWSTR
0x18004ddb5  lea     rcx, [rbp+360h+var_278]
0x18004ddbc  call    ?GetWppConfigInfo@LocalSpoolerTelemetry@@CA?AU_TELEMETRY_WPP_CONFIG_INFO@@XZ; LocalSpoolerTelemetry::GetWppConfigInfo(void)
0x18004ddc1  mov     ecx, [rax]
0x18004ddc3  mov     [rbp+360h+var_3E0], ecx
0x18004ddc6  mov     rcx, [rax+8]
0x18004ddca  mov     [rbp+360h+var_378], rcx
0x18004ddce  mov     rax, [rax+10h]
0x18004ddd2  mov     qword ptr [rbp+360h+var_3DC+4], rax
0x18004ddd6  xorps   xmm0, xmm0
0x18004ddd9  movups  [rbp+360h+var_298], xmm0
0x18004dde0  mov     [rbp+360h+var_288], 0
0x18004ddeb  mov     [rbp+360h+var_280], 7
0x18004ddf6  xor     eax, eax
0x18004ddf8  mov     word ptr [rbp+360h+var_298], ax
0x18004ddff  mov     rax, [rbp+360h+var_368]
0x18004de03  test    rax, rax
0x18004de06  jnz     short loc_18004DE18
0x18004de08  mov     [rbp+360h+var_288], rax
0x18004de0f  mov     word ptr [rbp+360h+var_298], ax
0x18004de16  jmp     short loc_18004DE42
0x18004de18  mov     rdx, rax
0x18004de1b  lea     rcx, [rbp+360h+var_278]
0x18004de22  call    ?ConvertPackageVersion@LocalSpoolerTelemetry@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z; LocalSpoolerTelemetry::ConvertPackageVersion(unsigned __int64)
0x18004de27  mov     rdx, rax
0x18004de2a  lea     rcx, [rbp+360h+var_298]
0x18004de31  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004de36  lea     rcx, [rbp+360h+var_278]
0x18004de3d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004de42  call    ?Provider@LocalSpoolerLogging@@SAPEBU_tlgProvider_t@@XZ; LocalSpoolerLogging::Provider(void)
0x18004de47  mov     [rbp+360h+var_2A8], rax
0x18004de4e  mov     ecx, [rax]
0x18004de50  cmp     ecx, 5
0x18004de53  jbe     loc_18004E2DE
0x18004de59  mov     rdx, 400000000000h
0x18004de63  mov     rcx, rax
0x18004de66  call    _tlgKeywordOn
0x18004de6b  test    al, al
0x18004de6d  jz      loc_18004E2DE
0x18004de73  lea     rcx, [rbp+360h+var_298]
0x18004de7a  cmp     [rbp+360h+var_280], 7
0x18004de82  cmova   rcx, qword ptr [rbp+360h+var_298]
0x18004de8a  mov     [rbp+360h+var_340], rcx
0x18004de8e  lea     rsi, qword_1800EBF90
0x18004de95  mov     rax, [rbp+360h+var_370]
0x18004de99  test    rax, rax
0x18004de9c  cmovz   rax, rsi
0x18004dea0  mov     [rbp+360h+var_338], rax
0x18004dea4  mov     rax, [rbp+360h+var_350]
0x18004dea8  test    rax, rax
0x18004deab  cmovz   rax, rsi
0x18004deaf  mov     [rbp+360h+var_330], rax
0x18004deb3  mov     rax, [rbp+360h+arg_28]
0x18004deba  test    rax, rax
0x18004debd  cmovz   rax, rsi
0x18004dec1  mov     [rbp+360h+var_328], rax
0x18004dec5  mov     rax, qword ptr [rbp+360h+var_3DC+4]
0x18004dec9  mov     [rbp+360h+var_320], rax
0x18004decd  mov     rax, [rbp+360h+var_378]
0x18004ded1  mov     [rbp+360h+var_318], rax
0x18004ded5  mov     eax, [rbp+360h+var_3E0]
0x18004ded8  mov     [rbp+360h+var_3E0], eax
0x18004dedb  mov     rcx, [rdi+50h]; pszPath
0x18004dedf  test    rcx, rcx
0x18004dee2  jz      short loc_18004DEEC
0x18004dee4  call    cs:__imp_PathFindExtensionW
0x18004deea  jmp     short loc_18004DEEE
0x18004deec  xor     eax, eax
0x18004deee  mov     [rbp+360h+var_310], rax
0x18004def2  mov     rax, [rdi+58h]
0x18004def6  test    byte ptr [rax+88h], 4
0x18004defd  jnz     short loc_18004DF19
0x18004deff  test    byte ptr [rax+140h], 80h
0x18004df06  jnz     short loc_18004DF19
0x18004df08  test    dword ptr [rax+98h], 400h
0x18004df12  jnz     short loc_18004DF19
0x18004df14  mov     eax, r12d
0x18004df17  jmp     short loc_18004DF1B
0x18004df19  xor     eax, eax
0x18004df1b  mov     [rbp+360h+var_3A0], eax
0x18004df1e  mov     rcx, [rdi+58h]; this
0x18004df22  lea     r8, [rcx+230h]; unsigned __int16 **
0x18004df29  lea     rdx, DEVPKEY_Device_HardwareIds; struct _DEVPROPKEY *
0x18004df30  call    ?GetIDList@_INIPRINTER@@AEAAPEAGPEBU_DEVPROPKEY@@PEAPEAG@Z; _INIPRINTER::GetIDList(_DEVPROPKEY const *,ushort * *)
0x18004df35  mov     [rbp+360h+var_308], rax
0x18004df39  lea     rax, [rbp+360h+Filename]
0x18004df40  cmp     dword ptr [rbp+360h+var_3D0+4], 0
0x18004df44  cmovz   rax, rsi
0x18004df48  mov     [rbp+360h+var_300], rax
0x18004df4c  mov     eax, dword ptr [rbp+360h+var_3B0]
0x18004df4f  mov     [rbp+360h+var_39C], eax
0x18004df52  mov     [rbp+360h+var_398], r13d
0x18004df56  mov     rax, [rdi+58h]
0x18004df5a  mov     ecx, [rax+98h]
0x18004df60  mov     [rbp+360h+var_394], ecx
0x18004df63  test    r15d, r15d
0x18004df66  jz      short loc_18004DF77
0x18004df68  mov     rax, [rdi+60h]
0x18004df6c  mov     ecx, [rax+0C8h]
0x18004df72  and     ecx, 8
0x18004df75  jmp     short loc_18004DF79
0x18004df77  xor     ecx, ecx
0x18004df79  mov     [rbp+360h+var_390], ecx
0x18004df7c  test    r15d, r15d
0x18004df7f  jz      short loc_18004DF92
0x18004df81  mov     rax, [rdi+60h]
0x18004df85  mov     ecx, [rax+0C8h]
0x18004df8b  shr     ecx, 1
0x18004df8d  and     ecx, r12d
0x18004df90  jmp     short loc_18004DF94
0x18004df92  xor     ecx, ecx
0x18004df94  mov     [rbp+360h+var_38C], ecx
0x18004df97  test    r15d, r15d
0x18004df9a  jz      short loc_18004DFA9
0x18004df9c  mov     rax, [rdi+60h]
0x18004dfa0  test    byte ptr [rax+0C8h], 40h
0x18004dfa7  jnz     short loc_18004DFAC
0x18004dfa9  xor     r12d, r12d
0x18004dfac  mov     edx, r12d; int
0x18004dfaf  mov     rcx, [rdi+58h]; this
0x18004dfb3  call    ?IsFaxDevice@_INIPRINTER@@QEAAHH@Z; _INIPRINTER::IsFaxDevice(int)
0x18004dfb8  mov     [rbp+360h+var_388], eax
0x18004dfbb  mov     eax, r15d
0x18004dfbe  neg     eax
0x18004dfc0  sbb     ecx, ecx
0x18004dfc2  and     ecx, r14d
0x18004dfc5  mov     [rbp+360h+var_384], ecx
0x18004dfc8  test    r15d, r15d
0x18004dfcb  jz      short loc_18004DFE3
0x18004dfcd  mov     rax, [rdi+60h]
0x18004dfd1  mov     rcx, [rax+0F8h]
0x18004dfd8  test    rcx, rcx
0x18004dfdb  jz      short loc_18004DFE3
0x18004dfdd  mov     rax, [rcx+18h]
0x18004dfe1  jmp     short loc_18004DFE6
0x18004dfe3  mov     rax, rsi
0x18004dfe6  mov     [rbp+360h+var_3B0], rax
0x18004dfea  mov     rdx, [rdi+58h]
0x18004dfee  mov     rax, [rdx+38h]
0x18004dff2  mov     rcx, [rax+18h]
0x18004dff6  mov     [rbp+360h+var_2F8], rcx
0x18004dffa  mov     eax, [rdx+210h]
0x18004e000  mov     [rbp+360h+var_380], eax
0x18004e003  mov     eax, [rdi+20h]
0x18004e006  mov     [rbp+360h+var_37C], eax
0x18004e009  mov     rax, [rdi+58h]
0x18004e00d  mov     ecx, [rax+134h]
0x18004e013  mov     dword ptr [rbp+360h+var_378], ecx
0x18004e016  mov     r8d, dword ptr [rbp+360h+var_3A8]
0x18004e01a  mov     dword ptr [rbp+360h+var_350], r8d
0x18004e01e  mov     rax, [rdi+58h]
0x18004e022  mov     rdx, [rax+138h]
0x18004e029  test    rdx, rdx
0x18004e02c  jz      short loc_18004E048
0x18004e02e  mov     rax, [rdx]
0x18004e031  mov     rcx, [rax+18h]
0x18004e035  mov     [rbp+360h+var_358], rcx
0x18004e039  mov     rax, [rax+60h]
0x18004e03d  test    rax, rax
0x18004e040  jz      short loc_18004E04C
0x18004e042  mov     rax, [rax+18h]
0x18004e046  jmp     short loc_18004E04F
0x18004e048  mov     [rbp+360h+var_358], rsi
0x18004e04c  mov     rax, rsi
0x18004e04f  mov     [rbp+360h+var_3A8], rax
0x18004e053  mov     [rbp+360h+var_2F0], rsi
0x18004e057  mov     rax, [rdi+80h]
0x18004e05e  mov     [rbp+360h+var_2E8], rax
0x18004e062  mov     rax, rsi
0x18004e065  cmp     dword ptr [rbp+360h+var_3DC], 0
0x18004e069  mov     r13, [rbp+360h+var_3C0]
0x18004e06d  cmovnz  rax, r13
0x18004e071  mov     [rbp+360h+var_2E0], rax
0x18004e078  mov     r12, qword ptr [rbp+360h+var_3B8]
0x18004e07c  mov     [rbp+360h+var_2D8], r12
0x18004e083  test    r15d, r15d
0x18004e086  jz      short loc_18004E094
0x18004e088  mov     rax, [rdi+60h]
0x18004e08c  mov     ecx, [rax+0ECh]
  ... truncated ...
```
