# UtcEvents_InstallerComplete(_PCA_EVENT_TYPE,void *)

- ea: `0x1800473a0`
- end: `0x18004801b`
- name: `?UtcEvents_InstallerComplete@@YAKW4_PCA_EVENT_TYPE@@PEAX@Z`
- size: `3195`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001d30`
- `0x180002028`
- `0x180007b3c`
- `0x18000c08c`
- `0x18000cb44`
- `0x180012920`
- `0x180013fac`
- `0x180019c84`
- `0x18001b320`
- `0x1800212b0`
- `0x18004290c`
- `0x1800473a0`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180047661`
- `msvcrt!_wcsicmp` at `0x180047661`
- `ntdll!RtlFreeHeap` at `0x180047f61`
- `ntdll!RtlFreeHeap` at `0x180047f77`
- `ntdll!RtlFreeHeap` at `0x180047f93`
- `ntdll!RtlFreeHeap` at `0x180047fac`
- `ntdll!RtlFreeHeap` at `0x180047f61`
- `ntdll!RtlFreeHeap` at `0x180047f77`
- `ntdll!RtlFreeHeap` at `0x180047f93`
- `ntdll!RtlFreeHeap` at `0x180047fac`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800478a0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180047aea`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180047b8e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180047e8f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800478a0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180047aea`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180047b8e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180047e8f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004749f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004749f`

## string_xrefs

- `0x18004754b`: `InstallShield`
- `0x18004753f`: `InstallAware`
- `0x1800474b1`: `Failed to create Installer instance guid [%d]`
- `0x1800474c1`: `UtcEvents_InstallerComplete`
- `0x180047713`: `UtcEvents_InstallerComplete`
- `0x18004751b`: `AdvancedInstaller`
- `0x180047f36`: `Installer event sent`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall UtcEvents_InstallerComplete(__int64 a1, __int64 a2)
{
  int v3; // r13d
  unsigned int v4; // ebx
  const char *v5; // r9
  int v6; // r8d
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  const char *v14; // rsi
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  __int64 v22; // r9
  unsigned int v23; // r12d
  unsigned __int64 v24; // rcx
  const unsigned __int16 *v25; // r13
  const wchar_t **v26; // rax
  __int64 v27; // r9
  __int64 v28; // r9
  const unsigned __int16 **v29; // rdx
  __int64 v30; // r9
  const unsigned __int16 *Value; // rax
  __int64 v32; // r9
  unsigned int v33; // r12d
  unsigned __int64 v34; // rcx
  const unsigned __int16 *v35; // rbx
  const unsigned __int16 **v36; // rdx
  __int64 v37; // r9
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // r9
  unsigned int v41; // ecx
  ULONGLONG v42; // rsi
  __int64 v43; // r9
  __int64 v44; // r9
  unsigned int v45; // r12d
  ULONGLONG v46; // r10
  ULONGLONG v47; // rdx
  __int64 v48; // r9
  __int64 v49; // r9
  LPCWSTR *v50; // rax
  __int64 v51; // r9
  const unsigned __int16 *v52; // rax
  int v53; // r8d
  __int64 v54; // r9
  unsigned int v55; // r12d
  LPCWSTR *v56; // rax
  __int64 v57; // r9
  const unsigned __int16 *v58; // rax
  ULONGLONG v59; // r11
  __int64 v60; // r9
  unsigned int i; // r12d
  ULONGLONG v62; // r10
  ULONGLONG v63; // rdx
  __int64 v64; // r9
  __int64 v65; // r9
  const unsigned __int16 **v66; // rdx
  __int64 v67; // r9
  const unsigned __int16 **v68; // r11
  __int64 v69; // r9
  unsigned int j; // r12d
  const unsigned __int16 **v71; // rdx
  __int64 v72; // r9
  const unsigned __int16 **v73; // r11
  int v74; // ecx
  int v75; // r8d
  int v76; // r9d
  struct _PCA_CHAIN *v77; // rax
  ULONGLONG pullResult; // [rsp+E0h] [rbp-80h] BYREF
  ULONGLONG v80; // [rsp+E8h] [rbp-78h] BYREF
  int v81; // [rsp+F0h] [rbp-70h] BYREF
  unsigned int v82; // [rsp+F4h] [rbp-6Ch] BYREF
  int v83; // [rsp+F8h] [rbp-68h] BYREF
  int v84; // [rsp+FCh] [rbp-64h] BYREF
  int v85; // [rsp+100h] [rbp-60h] BYREF
  int v86; // [rsp+104h] [rbp-5Ch] BYREF
  int v87; // [rsp+108h] [rbp-58h] BYREF
  int v88; // [rsp+10Ch] [rbp-54h] BYREF
  int v89; // [rsp+110h] [rbp-50h] BYREF
  int v90; // [rsp+114h] [rbp-4Ch] BYREF
  int v91; // [rsp+118h] [rbp-48h] BYREF
  int v92; // [rsp+11Ch] [rbp-44h] BYREF
  int v93; // [rsp+120h] [rbp-40h] BYREF
  int v94; // [rsp+124h] [rbp-3Ch] BYREF
  int v95; // [rsp+128h] [rbp-38h] BYREF
  int v96; // [rsp+12Ch] [rbp-34h] BYREF
  __int64 FileNameW; // [rsp+130h] [rbp-30h] BYREF
  GUID *v98; // [rsp+138h] [rbp-28h] BYREF
  LPWSTR v99; // [rsp+140h] [rbp-20h] BYREF
  GUID *p_pguid; // [rsp+148h] [rbp-18h] BYREF
  __int64 v101; // [rsp+150h] [rbp-10h] BYREF
  HANDLE HeapHandle[2]; // [rsp+158h] [rbp-8h] BYREF
  __int128 v103; // [rsp+168h] [rbp+8h]
  PVOID P[2]; // [rsp+178h] [rbp+18h]
  HANDLE v105[2]; // [rsp+188h] [rbp+28h] BYREF
  __int128 v106; // [rsp+198h] [rbp+38h]
  PVOID v107[2]; // [rsp+1A8h] [rbp+48h]
  PVOID v108; // [rsp+1B8h] [rbp+58h] BYREF
  HANDLE v109[2]; // [rsp+1C0h] [rbp+60h] BYREF
  __int128 v110; // [rsp+1D0h] [rbp+70h]
  PVOID v111[2]; // [rsp+1E0h] [rbp+80h]
  HANDLE v112[2]; // [rsp+1F0h] [rbp+90h] BYREF
  __int128 v113; // [rsp+200h] [rbp+A0h]
  PVOID v114[2]; // [rsp+210h] [rbp+B0h]
  GUID pguid; // [rsp+220h] [rbp+C0h] BYREF

  pguid = 0;
  *(_OWORD *)v109 = 0;
  v110 = 0;
  *(_OWORD *)v111 = 0;
  v109[0] = NtCurrentPeb()->ProcessHeap;
  *((_QWORD *)&v110 + 1) = 4096;
  *(_OWORD *)v112 = 0;
  v113 = 0;
  *(_OWORD *)v114 = 0;
  v112[0] = NtCurrentPeb()->ProcessHeap;
  *((_QWORD *)&v113 + 1) = 4096;
  *(_OWORD *)v105 = 0;
  v106 = 0;
  *(_OWORD *)v107 = 0;
  v105[0] = NtCurrentPeb()->ProcessHeap;
  *((_QWORD *)&v106 + 1) = 4096;
  *(_OWORD *)HeapHandle = 0;
  v103 = 0;
  *(_OWORD *)P = 0;
  HeapHandle[0] = NtCurrentPeb()->ProcessHeap;
  *((_QWORD *)&v103 + 1) = 4096;
  PcapChainFromHandle(*(_QWORD *)(a2 + 8));
  v3 = 0;
  if ( *(_DWORD *)(a2 + 36) || *(_DWORD *)(a2 + 48) )
    goto LABEL_154;
  v4 = 8;
  if ( CoCreateGuid(&pguid) < 0 )
  {
    v5 = "Failed to create Installer instance guid [%d]";
    v6 = 642;
    goto LABEL_5;
  }
  v7 = *(_DWORD *)(a2 + 32);
  if ( v7 <= 8 )
  {
    if ( v7 == 8 )
    {
      v14 = "7-Zip";
      goto LABEL_42;
    }
    if ( !v7 )
    {
      v14 = "Other";
      goto LABEL_42;
    }
    v8 = v7 - 1;
    if ( !v8 )
    {
      v14 = "MSI";
      goto LABEL_42;
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
      v14 = "InstallShield";
      goto LABEL_42;
    }
    v10 = v9 - 1;
    if ( !v10 )
    {
      v14 = "InstallAware";
      goto LABEL_42;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v14 = "NullSoft";
      goto LABEL_42;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v14 = "Inno";
      goto LABEL_42;
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      v14 = "AdvancedInstaller";
      goto LABEL_42;
    }
    if ( v13 == 1 )
    {
      v14 = "DemoShield";
      goto LABEL_42;
    }
    goto LABEL_33;
  }
  v15 = v7 - 9;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            v20 = v19 - 1;
            if ( v20 )
            {
              v21 = v20 - 1;
              if ( v21 )
              {
                if ( v21 != 1 )
                {
LABEL_33:
                  v14 = "Unknown";
                  goto LABEL_42;
                }
                v14 = "Wise";
              }
              else
              {
                v14 = "Gentee";
              }
            }
            else
            {
              v14 = "Raphael";
            }
          }
          else
          {
            v14 = "Astrum";
          }
        }
        else
        {
          v14 = "WinRAR";
        }
      }
      else
      {
        v14 = "IllustrateSpoon";
      }
    }
    else
    {
      v14 = "Sonic";
    }
  }
  else
  {
    v14 = "WinZip";
  }
LABEL_42:
  v22 = *(_QWORD *)(a2 + 112);
  if ( !*(_QWORD *)(v22 + 16) )
  {
LABEL_60:
    v32 = *(_QWORD *)(a2 + 104);
    if ( *(_QWORD *)(v32 + 16) )
    {
      v33 = 0;
      do
      {
        pullResult = 0;
        v34 = *(_QWORD *)(v32 + 16);
        v35 = &dword_1800FF0F4;
        if ( v33 != v34 - 1 )
          v35 = L";";
        v36 = 0;
        if ( v33 < v34 )
        {
          v80 = 0;
          if ( ULongLongMult(*(_QWORD *)(v32 + 8), v33, &v80) < 0
            || (v36 = (const unsigned __int16 **)(*(_QWORD *)(v37 + 40) + v80),
                (unsigned __int64)v36 < *(_QWORD *)(v37 + 40)) )
          {
            v36 = 0;
          }
        }
        if ( UtcEventsp_EncodeProgramInfo((unsigned __int16 **)&pullResult, *v36) )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"UtcEvents_InstallerComplete",
            758,
            (unsigned int)"Unable to retrieve arp attributes [%d]");
        }
        else
        {
          v4 = RtlMemoryStream::WriteString((RtlMemoryStream *)v112, (const unsigned __int16 *)pullResult, v35);
          AslFree(NtCurrentPeb()->ProcessHeap, pullResult);
          if ( v4 )
          {
            v53 = 766;
            goto LABEL_99;
          }
        }
        ++v33;
        v32 = *(_QWORD *)(a2 + 104);
      }
      while ( (unsigned __int64)v33 < *(_QWORD *)(v32 + 16) );
    }
    if ( (unsigned int)dword_180155F98 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180155F98, 0x200000000000LL) )
    {
      v108 = v111[1];
      LOWORD(v81) = *(_WORD *)(a2 + 128);
      v82 = *(_DWORD *)(a2 + 36);
      v86 = *(_DWORD *)(a2 + 68);
      v87 = *(_DWORD *)(a2 + 64);
      v88 = *(_DWORD *)(a2 + 60);
      v89 = *(_DWORD *)(a2 + 52);
      v90 = *(_DWORD *)(a2 + 56);
      v91 = *(_DWORD *)(a2 + 28);
      v92 = *(_DWORD *)(a2 + 48);
      v93 = *(_DWORD *)(a2 + 44);
      v94 = *(_DWORD *)(a2 + 24);
      v95 = *(_DWORD *)(a2 + 40);
      FileNameW = (__int64)PathFindFileNameW(*(LPCWSTR *)(a2 + 136));
      v98 = (GUID *)v114[1];
      v96 = *(_DWORD *)(*(_QWORD *)(a2 + 104) + 16LL);
      v83 = *(_DWORD *)(*(_QWORD *)(a2 + 96) + 16LL);
      v84 = *(_DWORD *)(*(_QWORD *)(a2 + 88) + 16LL);
      v85 = *(_DWORD *)(*(_QWORD *)(a2 + 80) + 16LL);
      LODWORD(v80) = *(_DWORD *)(*(_QWORD *)(a2 + 120) + 16LL);
      LODWORD(pullResult) = *(_DWORD *)(a2 + 16);
      v99 = (LPWSTR)v14;
      p_pguid = &pguid;
      v101 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapSz<unsigned short>>(
        v80,
        (unsigned int)&unk_18013AFB0,
        v38,
        v39,
        (__int64)&v101,
        (__int64)&p_pguid,
        (__int64)&v99,
        (__int64)&pullResult,
        (__int64)&v80,
        (__int64)&v85,
        (__int64)&v84,
        (__int64)&v83,
        (__int64)&v96,
        (__int64)&v98,
        (__int64)&FileNameW,
        (__int64)&v95,
        (__int64)&v94,
        (__int64)&v93,
        (__int64)&v92,
        (__int64)&v91,
        (__int64)&v90,
        (__int64)&v89,
        (__int64)&v88,
        (__int64)&v87,
        (__int64)&v86,
        (__int64)&v82,
        (__int64)&v81,
        (__int64)&v108);
    }
    v40 = *(_QWORD *)(a2 + 120);
    if ( *(_QWORD *)(v40 + 16) )
    {
      v41 = 0;
      v82 = 0;
      while ( 1 )
      {
        v42 = 0;
        if ( (unsigned __int64)v41 < *(_QWORD *)(v40 + 16) )
        {
          pullResult = 0;
          if ( ULongLongMult(*(_QWORD *)(v40 + 8), v41, &pullResult) < 0
            || (v42 = *(_QWORD *)(v43 + 40) + pullResult, v42 < *(_QWORD *)(v43 + 40)) )
          {
            v42 = 0;
          }
        }
        v81 = 0;
        v105[1] = 0;
        v107[0] = 0;
        v44 = *(_QWORD *)(a2 + 80);
        if ( *(_QWORD *)(v44 + 16) )
        {
          v45 = 0;
          while ( 1 )
          {
            v46 = v45;
            v47 = 0;
            if ( (unsigned __int64)v45 < *(_QWORD *)(v44 + 16) )
            {
              pullResult = 0;
              if ( ULongLongMult(*(_QWORD *)(v44 + 8), v45, &pullResult) < 0
                || (v47 = *(_QWORD *)(v48 + 40) + pullResult, v47 < *(_QWORD *)(v48 + 40)) )
              {
                v47 = 0;
              }
            }
            if ( *(_QWORD *)(v47 + 8) == *(_QWORD *)(v42 + 520) )
            {
              v49 = *(_QWORD *)(a2 + 80);
              v50 = 0;
              if ( v46 < *(_QWORD *)(v49 + 16) )
              {
                pullResult = 0;
                if ( ULongLongMult(*(_QWORD *)(v49 + 8), v46, &pullResult) < 0
                  || (v50 = (LPCWSTR *)(*(_QWORD *)(v51 + 40) + pullResult),
                      (unsigned __int64)v50 < *(_QWORD *)(v51 + 40)) )
                {
                  v50 = 0;
                }
              }
              v52 = PathFindFileNameW(*v50);
              v4 = RtlMemoryStream::WriteString((RtlMemoryStream *)v105, v52, L";");
              if ( v4 )
              {
                v53 = 846;
                goto LABEL_99;
              }
              if ( v105[1] > (HANDLE)0x4000 )
                break;
            }
            ++v45;
            v44 = *(_QWORD *)(a2 + 80);
            if ( (unsigned __int64)v45 >= *(_QWORD *)(v44 + 16) )
              goto LABEL_101;
          }
          v81 = 1;
        }
LABEL_101:
        v54 = *(_QWORD *)(a2 + 96);
        if ( *(_QWORD *)(v54 + 16) )
        {
          v55 = 0;
          while ( 1 )
          {
            v56 = 0;
            if ( (unsigned __int64)v55 < *(_QWORD *)(v54 + 16) )
            {
              pullResult = 0;
              if ( ULongLongMult(*(_QWORD *)(v54 + 8), v55, &pullResult) < 0
                || (v56 = (LPCWSTR *)(*(_QWORD *)(v57 + 40) + pullResult), (unsigned __int64)v56 < *(_QWORD *)(v57 + 40)) )
              {
                v56 = 0;
              }
            }
            v58 = PathFindFileNameW(*v56);
            v4 = RtlMemoryStream::WriteString((RtlMemoryStream *)v105, v58, L";");
            if ( v4 )
            {
              v53 = 860;
              goto LABEL_99;
            }
            if ( v105[1] > (HANDLE)0x4000 )
              break;
            ++v55;
            v54 = *(_QWORD *)(a2 + 96);
            if ( (unsigned __int64)v55 >= *(_QWORD *)(v54 + 16) )
              goto LABEL_112;
          }
          v81 = 1;
        }
LABEL_112:
        v4 = RtlMemoryStream::WriteString((RtlMemoryStream *)v105, 0, &dword_1800FF0F4);
        if ( v4 )
          break;
        v59 = 0;
        HeapHandle[1] = 0;
        P[0] = 0;
        v60 = *(_QWORD *)(a2 + 88);
        if ( *(_QWORD *)(v60 + 16) )
        {
          for ( i = 0; (unsigned __int64)i < *(_QWORD *)(v60 + 16); ++i )
          {
            pullResult = v59;
            v62 = i;
            v63 = v59;
            if ( (unsigned __int64)i < *(_QWORD *)(v60 + 16) )
            {
              v80 = v59;
              if ( ULongLongMult(*(_QWORD *)(v60 + 8), i, &v80) < 0
                || (v63 = *(_QWORD *)(v64 + 40) + v80, v63 < *(_QWORD *)(v64 + 40)) )
              {
                v63 = v59;
              }
            }
            if ( *(_QWORD *)(v63 + 8) == *(_QWORD *)(v42 + 520) )
            {
              v65 = *(_QWORD *)(a2 + 88);
              v66 = (const unsigned __int16 **)v59;
              if ( v62 < *(_QWORD *)(v65 + 16) )
              {
                v80 = v59;
                if ( ULongLongMult(*(_QWORD *)(v65 + 8), v62, &v80) < 0
                  || (v66 = (const unsigned __int16 **)(*(_QWORD *)(v67 + 40) + v80),
                      (unsigned __int64)v66 < *(_QWORD *)(v67 + 40)) )
                {
                  v66 = v68;
                }
              }
              if ( UtcEventsp_EncodeProgramInfo((unsigned __int16 **)&pullResult, *v66) )
              {
                AslLogCallPrintf(
                  1,
                  (unsigned int)"UtcEvents_InstallerComplete",
                  892,
                  (unsigned int)"Unable to retrieve arp attributes [%d]");
                v59 = 0;
              }
              else
              {
                v4 = RtlMemoryStream::WriteString(
                       (RtlMemoryStream *)HeapHandle,
                       (const unsigned __int16 *)pullResult,
                       L";");
                AslFree(NtCurrentPeb()->ProcessHeap, pullResult);
                v59 = 0;
                if ( v4 )
                {
                  v53 = 978;
                  goto LABEL_99;
                }
                if ( HeapHandle[1] > (HANDLE)0x4000 )
                {
                  v3 = 1;
                  break;
                }
              }
            }
            v60 = *(_QWORD *)(a2 + 88);
          }
        }
        if ( *(_QWORD *)(*(_QWORD *)(a2 + 88) + 16LL) == v59 )
        {
          v69 = *(_QWORD *)(a2 + 104);
          if ( *(_QWORD *)(v69 + 16) > v59 )
          {
            for ( j = v59; (unsigned __int64)j < *(_QWORD *)(v69 + 16); ++j )
            {
              pullResult = v59;
              v71 = (const unsigned __int16 **)v59;
              if ( (unsigned __int64)j < *(_QWORD *)(v69 + 16) )
              {
                v80 = v59;
                if ( ULongLongMult(*(_QWORD *)(v69 + 8), j, &v80) < 0
                  || (v71 = (const unsigned __int16 **)(*(_QWORD *)(v72 + 40) + v80),
                      (unsigned __int64)v71 < *(_QWORD *)(v72 + 40)) )
                {
                  v71 = v73;
                }
              }
              if ( UtcEventsp_EncodeProgramInfo((unsigned __int16 **)&pullResult, *v71) )
              {
                AslLogCallPrintf(
                  1,
                  (unsigned int)"UtcEvents_InstallerComplete",
                  997,
                  (unsigned int)"Unable to retrieve arp attributes [%d]");
                v59 = 0;
              }
              else
              {
                v4 = RtlMemoryStream::WriteString(
                       (RtlMemoryStream *)HeapHandle,
                       (const unsigned __int16 *)pullResult,
                       L";");
                AslFree(NtCurrentPeb()->ProcessHeap, pullResult);
                v59 = 0;
                if ( v4 )
                {
                  v53 = 1084;
                  goto LABEL_99;
                }
                if ( HeapHandle[1] > (HANDLE)0x4000 )
                {
                  v3 = 1;
                  break;
                }
              }
              v69 = *(_QWORD *)(a2 + 104);
            }
          }
        }
        v4 = RtlMemoryStream::WriteString((RtlMemoryStream *)HeapHandle, 0, &dword_1800FF0F4);
        if ( v4 )
        {
          v53 = 1097;
          goto LABEL_99;
        }
        if ( (*(_WORD *)v42 || v105[1] > HANDLE_FLAG_PROTECT_FROM_CLOSE
                            || HeapHandle[1] > HANDLE_FLAG_PROTECT_FROM_CLOSE)
          && (unsigned int)dword_180155F98 > 5
          && (unsigned __int8)tlgKeywordOn(&dword_180155F98, 0x200000000000LL) )
        {
          v101 = (__int64)P[1];
          p_pguid = (GUID *)v107[1];
          LODWORD(pullResult) = v3;
          LODWORD(v80) = v81;
          v85 = *(_DWORD *)(v42 + 536);
          v84 = *(_DWORD *)(v42 + 532);
          v83 = *(_DWORD *)(v42 + 528);
          v99 = PathFindFileNameW((LPCWSTR)v42);
          v98 = &pguid;
          FileNameW = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v74,
            (unsigned int)&byte_18013AF17,
            v75,
            v76,
            (__int64)&FileNameW,
            (__int64)&v98,
            (__int64)&v99,
            (__int64)&v83,
            (__int64)&v84,
            (__int64)&v85,
            (__int64)&v80,
            (__int64)&pullResult,
            (__int64)&p_pguid,
            (__int64)&v101);
        }
        v41 = v82 + 1;
        v82 = v41;
        v40 = *(_QWORD *)(a2 + 120);
        v3 = 0;
        if ( (unsigned __int64)v41 >= *(_QWORD *)(v40 + 16) )
          goto LABEL_153;
      }
      v53 = 872;
LABEL_99:
      AslLogCallPrintf(1, (unsigned int)"UtcEvents_InstallerComplete", v53, (unsigned int)"Out of memory");
      goto LABEL_155;
    }
LABEL_153:
    v77 = PcapChainFromHandle(*(_QWORD *)(a2 + 8));
    PcaTracePrintf("UtcEvents", *((_DWORD *)v77 + 4), 0, "Installer event sent");
LABEL_154:
    v4 = 0;
    goto LABEL_155;
  }
  v23 = 0;
  while ( 1 )
  {
    v24 = *(_QWORD *)(v22 + 16);
    v25 = &dword_1800FF0F4;
    if ( v23 != v24 - 1 )
      v25 = L";";
    v26 = 0;
    if ( v23 < v24 )
    {
      pullResult = 0;
      if ( ULongLongMult(*(_QWORD *)(v22 + 8), v23, &pullResult) < 0
        || (v26 = (const wchar_t **)(*(_QWORD *)(v27 + 40) + pullResult), (unsigned __int64)v26 < *(_QWORD *)(v27 + 40)) )
      {
        v26 = 0;
      }
    }
    if ( !_wcsicmp(*v26, L"Path") )
    {
      v3 = 0;
      goto LABEL_59;
    }
    v28 = *(_QWORD *)(a2 + 112);
    v29 = 0;
    if ( (unsigned __int64)v23 < *(_QWORD *)(v28 + 16) )
    {
      pullResult = 0;
      if ( ULongLongMult(*(_QWORD *)(v28 + 8), v23, &pullResult) < 0
        || (v29 = (const unsigned __int16 **)(*(_QWORD *)(v30 + 40) + pullResult),
            (unsigned __int64)v29 < *(_QWORD *)(v30 + 40)) )
      {
        v29 = 0;
      }
    }
    v4 = RtlMemoryStream::WriteString((RtlMemoryStream *)v109, *v29, L"=");
    if ( v4 )
      break;
    Value = RtlNameValueArray::GetValue(*(RtlNameValueArray **)(a2 + 112), v23);
    v4 = RtlMemoryStream::WriteString((RtlMemoryStream *)v109, Value, v25);
    v3 = 0;
    if ( v4 )
    {
      v6 = 743;
      goto LABEL_71;
    }
LABEL_59:
    ++v23;
    v22 = *(_QWORD *)(a2 + 112);
    if ( (unsigned __int64)v23 >= *(_QWORD *)(v22 + 16) )
      goto LABEL_60;
  }
  v6 = 737;
LABEL_71:
  v5 = "Bad attribute [%d]";
LABEL_5:
  AslLogCallPrintf(1, (unsigned int)"UtcEvents_InstallerComplete", v6, (_DWORD)v5);
LABEL_155:
  if ( P[1] )
    RtlFreeHeap(HeapHandle[0], 0, P[1]);
  if ( v107[1] )
    RtlFreeHeap(v105[0], 0, v107[1]);
  if ( v114[1] )
    RtlFreeHeap(v112[0], 0, v114[1]);
  if ( v111[1] )
    RtlFreeHeap(v109[0], 0, v111[1]);
  return v4;
}

```

## disassembly

```asm
0x1800473a0  push    rbp
0x1800473a2  push    rbx
0x1800473a3  push    rsi
0x1800473a4  push    rdi
0x1800473a5  push    r12
0x1800473a7  push    r13
0x1800473a9  push    r14
0x1800473ab  push    r15
0x1800473ad  lea     rbp, [rsp-0E8h]
0x1800473b5  sub     rsp, 248h
0x1800473bc  mov     rax, cs:__security_cookie
0x1800473c3  xor     rax, rsp
0x1800473c6  mov     [rbp+120h+var_50], rax
0x1800473cd  mov     r14, rdx
0x1800473d0  xorps   xmm0, xmm0
0x1800473d3  movups  xmmword ptr [rbp+120h+pguid.Data1], xmm0
0x1800473da  xorps   xmm1, xmm1
0x1800473dd  movups  xmmword ptr [rbp+120h+var_C0], xmm1
0x1800473e1  movups  [rbp+120h+var_B0], xmm1
0x1800473e5  movups  xmmword ptr [rbp+120h+var_A0], xmm1
0x1800473ec  mov     rax, gs:60h
0x1800473f5  mov     rcx, [rax+30h]
0x1800473f9  mov     [rbp+120h+var_C0], rcx
0x1800473fd  mov     edx, 1000h
0x180047402  mov     qword ptr [rbp+120h+var_B0+8], rdx
0x180047406  movups  xmmword ptr [rbp+120h+var_90], xmm0
0x18004740d  movups  [rbp+120h+var_80], xmm0
0x180047414  movups  xmmword ptr [rbp+120h+var_70], xmm0
0x18004741b  mov     rax, gs:60h
0x180047424  mov     rcx, [rax+30h]
0x180047428  mov     [rbp+120h+var_90], rcx
0x18004742f  mov     qword ptr [rbp+120h+var_80+8], rdx
0x180047436  movups  xmmword ptr [rbp+120h+var_F8], xmm0
0x18004743a  movups  [rbp+120h+var_E8], xmm0
0x18004743e  movups  xmmword ptr [rbp+120h+var_D8], xmm0
0x180047442  mov     rax, gs:60h
0x18004744b  mov     rcx, [rax+30h]
0x18004744f  mov     [rbp+120h+var_F8], rcx
0x180047453  mov     qword ptr [rbp+120h+var_E8+8], rdx
0x180047457  movups  xmmword ptr [rbp+120h+HeapHandle], xmm0
0x18004745b  movups  [rbp+120h+var_118], xmm0
0x18004745f  movups  xmmword ptr [rbp+120h+P], xmm0
0x180047463  mov     rax, gs:60h
0x18004746c  mov     rcx, [rax+30h]
0x180047470  mov     [rbp+120h+HeapHandle], rcx
0x180047474  mov     qword ptr [rbp+120h+var_118+8], rdx
0x180047478  mov     rcx, [r14+8]; unsigned __int64
0x18004747c  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x180047481  xor     r13d, r13d
0x180047484  cmp     [r14+24h], r13d
0x180047488  jnz     loc_180047F4F
0x18004748e  cmp     [r14+30h], r13d
0x180047492  jnz     loc_180047F4F
0x180047498  lea     rcx, [rbp+120h+pguid]; pguid
0x18004749f  call    cs:__imp_CoCreateGuid
0x1800474a5  lea     ebx, [r13+8]
0x1800474a9  test    eax, eax
0x1800474ab  jns     short loc_1800474D2
0x1800474ad  mov     dword ptr [rsp+280h+var_260], ebx
0x1800474b1  lea     r9, aFailedToCreate_23; "Failed to create Installer instance gui"...
0x1800474b8  mov     r8d, 282h
0x1800474be  lea     ecx, [rbx-7]
0x1800474c1  lea     rdx, aUtceventsInsta; "UtcEvents_InstallerComplete"
0x1800474c8  call    AslLogCallPrintf
0x1800474cd  jmp     loc_180047F52
0x1800474d2  mov     ecx, [r14+20h]
0x1800474d6  cmp     ecx, ebx
0x1800474d8  jg      loc_180047578
0x1800474de  jz      loc_18004756F
0x1800474e4  test    ecx, ecx
0x1800474e6  jz      short loc_180047563
0x1800474e8  sub     ecx, 1
0x1800474eb  jz      short loc_180047557
0x1800474ed  sub     ecx, 1
0x1800474f0  jz      short loc_18004754B
0x1800474f2  sub     ecx, 1
0x1800474f5  jz      short loc_18004753F
0x1800474f7  sub     ecx, 1
0x1800474fa  jz      short loc_180047533
0x1800474fc  sub     ecx, 1
0x1800474ff  jz      short loc_180047527
0x180047501  sub     ecx, 1
0x180047504  jz      short loc_18004751B
0x180047506  cmp     ecx, 1
0x180047509  jnz     loc_1800475A0
0x18004750f  lea     rsi, aDemoshield; "DemoShield"
0x180047516  jmp     loc_1800475EF
0x18004751b  lea     rsi, aAdvancedinstal; "AdvancedInstaller"
0x180047522  jmp     loc_1800475EF
0x180047527  lea     rsi, aInno_0; "Inno"
0x18004752e  jmp     loc_1800475EF
0x180047533  lea     rsi, aNullsoft_2; "NullSoft"
0x18004753a  jmp     loc_1800475EF
0x18004753f  lea     rsi, aInstallaware_0; "InstallAware"
0x180047546  jmp     loc_1800475EF
0x18004754b  lea     rsi, aInstallshield_1; "InstallShield"
0x180047552  jmp     loc_1800475EF
0x180047557  lea     rsi, aMsi_0; "MSI"
0x18004755e  jmp     loc_1800475EF
0x180047563  lea     rsi, aOther; "Other"
0x18004756a  jmp     loc_1800475EF
0x18004756f  lea     rsi, a7Zip_0; "7-Zip"
0x180047576  jmp     short loc_1800475EF
0x180047578  sub     ecx, 9
0x18004757b  jz      short loc_1800475E8
0x18004757d  sub     ecx, 1
0x180047580  jz      short loc_1800475DF
0x180047582  sub     ecx, 1
0x180047585  jz      short loc_1800475D6
0x180047587  sub     ecx, 1
0x18004758a  jz      short loc_1800475CD
0x18004758c  sub     ecx, 1
0x18004758f  jz      short loc_1800475C4
0x180047591  sub     ecx, 1
0x180047594  jz      short loc_1800475BB
0x180047596  sub     ecx, 1
0x180047599  jz      short loc_1800475B2
0x18004759b  cmp     ecx, 1
0x18004759e  jz      short loc_1800475A9
0x1800475a0  lea     rsi, aUnknown; "Unknown"
0x1800475a7  jmp     short loc_1800475EF
0x1800475a9  lea     rsi, aWise; "Wise"
0x1800475b0  jmp     short loc_1800475EF
0x1800475b2  lea     rsi, aGentee; "Gentee"
0x1800475b9  jmp     short loc_1800475EF
0x1800475bb  lea     rsi, aRaphael_0; "Raphael"
0x1800475c2  jmp     short loc_1800475EF
0x1800475c4  lea     rsi, aAstrum_0; "Astrum"
0x1800475cb  jmp     short loc_1800475EF
0x1800475cd  lea     rsi, aWinrar; "WinRAR"
0x1800475d4  jmp     short loc_1800475EF
0x1800475d6  lea     rsi, aIllustratespoo; "IllustrateSpoon"
0x1800475dd  jmp     short loc_1800475EF
0x1800475df  lea     rsi, aSonic_0; "Sonic"
0x1800475e6  jmp     short loc_1800475EF
0x1800475e8  lea     rsi, aWinzip; "WinZip"
0x1800475ef  mov     r9, [r14+70h]
0x1800475f3  mov     edi, 1
0x1800475f8  lea     rdx, asc_18011A0E8; ";"
0x1800475ff  cmp     [r9+10h], r13
0x180047603  jbe     loc_18004770F
0x180047609  mov     r12d, r13d
0x18004760c  mov     rcx, [r9+10h]
0x180047610  mov     r15d, r12d
0x180047613  lea     rax, [rcx-1]
0x180047617  lea     r13, dword_1800FF0F4
0x18004761e  cmp     r15, rax
0x180047621  cmovnz  r13, rdx
0x180047625  xor     ebx, ebx
0x180047627  mov     eax, ebx
0x180047629  cmp     r15, rcx
0x18004762c  jnb     short loc_180047657
0x18004762e  mov     [rbp+120h+pullResult], rbx
0x180047632  lea     r8, [rbp+120h+pullResult]; pullResult
0x180047636  mov     edx, r15d; ullMultiplier
0x180047639  mov     rcx, [r9+8]; ullMultiplicand
0x18004763d  call    ULongLongMult
0x180047642  test    eax, eax
0x180047644  js      short loc_180047654
0x180047646  mov     rax, [rbp+120h+pullResult]
0x18004764a  add     rax, [r9+28h]
0x18004764e  cmp     rax, [r9+28h]
0x180047652  jnb     short loc_180047657
0x180047654  mov     rax, rbx
0x180047657  lea     rdx, aPath_0; "Path"
0x18004765e  mov     rcx, [rax]; String1
0x180047661  call    cs:__imp__wcsicmp
0x180047667  test    eax, eax
0x180047669  jz      loc_1800476F1
0x18004766f  mov     r9, [r14+70h]
0x180047673  mov     rdx, rbx
0x180047676  cmp     r15, [r9+10h]
0x18004767a  jnb     short loc_1800476A5
0x18004767c  mov     [rbp+120h+pullResult], rbx
0x180047680  lea     r8, [rbp+120h+pullResult]; pullResult
0x180047684  mov     rdx, r15; ullMultiplier
0x180047687  mov     rcx, [r9+8]; ullMultiplicand
0x18004768b  call    ULongLongMult
0x180047690  test    eax, eax
0x180047692  js      short loc_1800476A2
0x180047694  mov     rdx, [rbp+120h+pullResult]
0x180047698  add     rdx, [r9+28h]
0x18004769c  cmp     rdx, [r9+28h]
0x1800476a0  jnb     short loc_1800476A5
0x1800476a2  mov     rdx, rbx
0x1800476a5  lea     r8, asc_18010C8A8; "="
0x1800476ac  mov     rdx, [rdx]; unsigned __int16 *
0x1800476af  lea     rcx, [rbp+120h+var_C0]; this
0x1800476b3  call    ?WriteString@RtlMemoryStream@@QEAAKPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x1800476b8  mov     ebx, eax
0x1800476ba  test    eax, eax
0x1800476bc  jnz     loc_1800477A2
0x1800476c2  mov     rdx, r15; unsigned __int64
0x1800476c5  mov     rcx, [r14+70h]; this
0x1800476c9  call    ?GetValue@RtlNameValueArray@@QEBAPEBG_K@Z; RtlNameValueArray::GetValue(unsigned __int64)
0x1800476ce  mov     rdx, rax; unsigned __int16 *
0x1800476d1  mov     r8, r13; unsigned __int16 *
0x1800476d4  lea     rcx, [rbp+120h+var_C0]; this
0x1800476d8  call    ?WriteString@RtlMemoryStream@@QEAAKPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x1800476dd  mov     ebx, eax
0x1800476df  xor     r13d, r13d
0x1800476e2  test    eax, eax
0x1800476e4  jz      short loc_1800476F4
0x1800476e6  mov     r8d, 2E7h
0x1800476ec  jmp     loc_1800477A8
0x1800476f1  xor     r13d, r13d
0x1800476f4  add     r12d, edi
0x1800476f7  mov     r9, [r14+70h]
0x1800476fb  mov     eax, r12d
0x1800476fe  lea     rdx, asc_18011A0E8; ";"
0x180047705  cmp     rax, [r9+10h]
0x180047709  jb      loc_18004760C
0x18004770f  mov     r9, [r14+68h]
0x180047713  lea     r15, aUtceventsInsta; "UtcEvents_InstallerComplete"
0x18004771a  cmp     [r9+10h], r13
0x18004771e  jbe     loc_180047808
0x180047724  mov     r12d, r13d
0x180047727  mov     [rbp+120h+pullResult], r13
0x18004772b  mov     rcx, [r9+10h]
0x18004772f  mov     r10d, r12d
0x180047732  lea     rax, [rcx-1]
0x180047736  lea     rbx, dword_1800FF0F4
0x18004773d  cmp     r10, rax
0x180047740  cmovnz  rbx, rdx
0x180047744  mov     rdx, r13
0x180047747  cmp     r10, rcx
0x18004774a  jnb     short loc_180047775
0x18004774c  mov     [rbp+120h+var_198], r13
0x180047750  lea     r8, [rbp+120h+var_198]; pullResult
0x180047754  mov     edx, r10d; ullMultiplier
0x180047757  mov     rcx, [r9+8]; ullMultiplicand
0x18004775b  call    ULongLongMult
0x180047760  test    eax, eax
0x180047762  js      short loc_180047772
0x180047764  mov     rdx, [rbp+120h+var_198]
0x180047768  add     rdx, [r9+28h]
0x18004776c  cmp     rdx, [r9+28h]
0x180047770  jnb     short loc_180047775
0x180047772  mov     rdx, r13
0x180047775  mov     rdx, [rdx]; unsigned __int16 *
0x180047778  lea     rcx, [rbp+120h+pullResult]; unsigned __int16 **
0x18004777c  call    ?UtcEventsp_EncodeProgramInfo@@YAKPEAPEAGPEBG@Z; UtcEventsp_EncodeProgramInfo(ushort * *,ushort const *)
0x180047781  test    eax, eax
0x180047783  jz      short loc_1800477BA
0x180047785  mov     dword ptr [rsp+280h+var_260], eax
0x180047789  lea     r9, aUnableToRetrie; "Unable to retrieve arp attributes [%d]"
0x180047790  mov     r8d, 2F6h
0x180047796  mov     rdx, r15
0x180047799  mov     ecx, edi
0x18004779b  call    AslLogCallPrintf
0x1800477a0  jmp     short loc_1800477ED
0x1800477a2  mov     r8d, 2E1h
0x1800477a8  lea     r9, aBadAttributeD; "Bad attribute [%d]"
0x1800477af  mov     dword ptr [rsp+280h+var_260], eax
0x1800477b3  mov     ecx, edi
0x1800477b5  jmp     loc_1800474C1
0x1800477ba  mov     r8, rbx; unsigned __int16 *
0x1800477bd  mov     rdx, [rbp+120h+pullResult]; unsigned __int16 *
0x1800477c1  lea     rcx, [rbp+120h+var_90]; this
0x1800477c8  call    ?WriteString@RtlMemoryStream@@QEAAKPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x1800477cd  mov     ebx, eax
0x1800477cf  mov     rcx, gs:60h
0x1800477d8  mov     rdx, [rbp+120h+pullResult]
0x1800477dc  mov     rcx, [rcx+30h]
0x1800477e0  call    AslFree
0x1800477e5  test    ebx, ebx
0x1800477e7  jnz     loc_180047B2D
0x1800477ed  add     r12d, edi
0x1800477f0  mov     r9, [r14+68h]
0x1800477f4  mov     eax, r12d
0x1800477f7  cmp     rax, [r9+10h]
0x1800477fb  lea     rdx, asc_18011A0E8; ";"
0x180047802  jb      loc_180047727
0x180047808  mov     eax, cs:dword_180155F98
0x18004780e  cmp     eax, 5
0x180047811  jbe     loc_180047A0D
0x180047817  mov     rdx, 200000000000h
0x180047821  lea     rcx, dword_180155F98
0x180047828  call    _tlgKeywordOn
0x18004782d  test    al, al
0x18004782f  jz      loc_180047A0D
0x180047835  mov     rax, [rbp+120h+var_A0+8]
0x18004783c  mov     [rbp+120h+var_C8], rax
0x180047840  movzx   eax, word ptr [r14+80h]
0x180047848  mov     word ptr [rbp+120h+var_190], ax
0x18004784c  mov     eax, [r14+24h]
0x180047850  mov     [rbp+120h+var_18C], eax
0x180047853  mov     eax, [r14+44h]
0x180047857  mov     [rbp+120h+var_17C], eax
0x18004785a  mov     eax, [r14+40h]
0x18004785e  mov     [rbp+120h+var_178], eax
0x180047861  mov     eax, [r14+3Ch]
0x180047865  mov     [rbp+120h+var_174], eax
0x180047868  mov     eax, [r14+34h]
0x18004786c  mov     [rbp+120h+var_170], eax
0x18004786f  mov     eax, [r14+38h]
0x180047873  mov     [rbp+120h+var_16C], eax
0x180047876  mov     eax, [r14+1Ch]
0x18004787a  mov     [rbp+120h+var_168], eax
0x18004787d  mov     eax, [r14+30h]
  ... truncated ...
```
