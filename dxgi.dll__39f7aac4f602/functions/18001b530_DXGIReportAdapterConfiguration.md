# DXGIReportAdapterConfiguration

- ea: `0x18001b530`
- end: `0x18001c084`
- name: `DXGIReportAdapterConfiguration`
- size: `2900`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18001b22c`
- `0x18001b530`
- `0x18001c574`
- `0x180037c50`
- `0x180050bd4`
- `0x180050c10`
- `0x180050d70`
- `0x180075fa0`
- `0x180076f08`
- `0x180076f20`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b5d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b5e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b5fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b60d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b622`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b635`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b648`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b65d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b672`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b5d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b5e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b5fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b60d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b622`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b635`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b648`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b65d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b672`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b578`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b592`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b578`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b592`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001bed1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001bee7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001bed1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001bee7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bb91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bb91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bb83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bb83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b76e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b76e`

## string_xrefs

- `0x18001b564`: `setupapi.dll`
- `0x18001b581`: `gdi32.dll`
- `0x18001b613`: `D3DKMTOpenAdapterFromDeviceName`

## pseudocode

```c
__int64 __fastcall DXGIReportAdapterConfiguration(unsigned int *a1)
{
  HMODULE v2; // r14
  HMODULE v3; // rax
  HMODULE v4; // r12
  FARPROC ProcAddress; // r15
  FARPROC v6; // rsi
  FARPROC v7; // rbx
  FARPROC v8; // r14
  FARPROC v9; // r13
  FARPROC v10; // r12
  FARPROC v11; // rax
  __int64 v12; // rax
  __int64 v13; // r9
  __int64 v14; // rsi
  void *v15; // rax
  _DWORD *v16; // r15
  unsigned int v17; // eax
  unsigned int v18; // esi
  unsigned int v19; // r14d
  _DWORD *v20; // r13
  int (*v21)(struct _D3DKMT_QUERYVIDEOMEMORYINFO *); // rax
  int (*v22)(struct _D3DKMT_QUERYVIDEOMEMORYINFO *); // rbx
  int v23; // edx
  unsigned int v24; // r10d
  __m128 si128; // xmm5
  __m128i v26; // xmm4
  __m128i v27; // xmm8
  __int64 v28; // rdx
  __m128i v29; // xmm2
  __int64 v30; // rcx
  __m128i v31; // xmm3
  __m128i v32; // xmm4
  __m128i v33; // xmm4
  unsigned int v34; // ecx
  int v35; // r12d
  unsigned int v36; // r15d
  __int64 v37; // rdi
  __int64 v38; // rsi
  _DWORD *v39; // r14
  HANDLE ProcessHeap; // rax
  _DWORD *v41; // rbx
  _DWORD *v42; // rbx
  unsigned int *v43; // rbx
  _DWORD *v44; // rbx
  char v45; // al
  _QWORD *v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rbx
  int v49; // eax
  void *v50; // rbx
  int v52; // eax
  __int64 v53; // rcx
  int v54; // eax
  unsigned int v55; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v56; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v57; // [rsp+50h] [rbp-B8h] BYREF
  HMODULE hModule; // [rsp+58h] [rbp-B0h]
  int (*v59)(struct _D3DKMT_QUERYVIDEOMEMORYINFO *); // [rsp+60h] [rbp-A8h]
  HMODULE Library; // [rsp+68h] [rbp-A0h]
  __int64 v61; // [rsp+70h] [rbp-98h]
  FARPROC v62; // [rsp+78h] [rbp-90h]
  void (__fastcall *v63)(__int64 *); // [rsp+80h] [rbp-88h]
  _DWORD *v64; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v65[4]; // [rsp+90h] [rbp-78h]
  __int128 v66; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v67; // [rsp+B0h] [rbp-58h]
  LPVOID lpMem[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v69; // [rsp+C8h] [rbp-40h]
  __int128 v70; // [rsp+D8h] [rbp-30h]
  _OWORD v71[2]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE Src[2080]; // [rsp+108h] [rbp+0h] BYREF

  if ( !a1 )
    return 2147942487LL;
  Library = LoadLibraryExW(L"setupapi.dll", 0, 0);
  v2 = Library;
  v3 = LoadLibraryExW(L"gdi32.dll", 0, 0);
  hModule = v3;
  v4 = v3;
  if ( !Library || !v3 )
  {
    v18 = -2147467259;
    if ( v3 )
      goto LABEL_87;
    goto LABEL_88;
  }
  ProcAddress = GetProcAddress(Library, "SetupDiGetClassDevsW");
  v6 = GetProcAddress(Library, "SetupDiEnumDeviceInterfaces");
  v7 = GetProcAddress(Library, "SetupDiGetDeviceInterfaceDetailW");
  v62 = GetProcAddress(Library, "SetupDiDestroyDeviceInfoList");
  v8 = GetProcAddress(v4, "D3DKMTOpenAdapterFromDeviceName");
  v9 = GetProcAddress(v4, "D3DKMTQueryAdapterInfo");
  v59 = (int (*)(struct _D3DKMT_QUERYVIDEOMEMORYINFO *))GetProcAddress(v4, "D3DKMTQueryVideoMemoryInfo");
  v10 = GetProcAddress(v4, "D3DKMTGetDisplayModeList");
  v11 = GetProcAddress(hModule, "D3DKMTCloseAdapter");
  v63 = (void (__fastcall *)(__int64 *))v11;
  if ( !ProcAddress || !v6 || !v7 || !v62 || !v8 || !v9 || !v59 || !v10 || !v11 )
  {
    v18 = -2147467259;
    goto LABEL_58;
  }
  v12 = ((__int64 (__fastcall *)(GUID *, _QWORD, _QWORD, __int64))ProcAddress)(&GUID_DISPLAY_DEVICE_ARRIVAL, 0, 0, 18);
  v61 = v12;
  if ( v12 == -1 )
  {
    v18 = -2005270526;
    goto LABEL_58;
  }
  v13 = *a1;
  memset(v71, 0, sizeof(v71));
  LODWORD(v71[0]) = 32;
  if ( !((unsigned int (__fastcall *)(__int64, _QWORD, GUID *, __int64, _OWORD *))v6)(
          v12,
          0,
          &GUID_DISPLAY_DEVICE_ARRIVAL,
          v13,
          v71) )
  {
    v18 = -2005270526;
    goto LABEL_57;
  }
  v14 = v61;
  v56 = 0;
  if ( ((unsigned int (__fastcall *)(__int64, _OWORD *, _QWORD, _QWORD, unsigned int *, _QWORD))v7)(
         v61,
         v71,
         0,
         0,
         &v56,
         0)
    || GetLastError() != 122 )
  {
    v18 = -2147467259;
    goto LABEL_57;
  }
  v15 = operator new(v56);
  lpMem[0] = v15;
  v16 = v15;
  if ( !v15 )
  {
    v18 = -2147024882;
    goto LABEL_57;
  }
  memset_0(v15, 0, v56);
  *v16 = 8;
  if ( !((unsigned int (__fastcall *)(__int64, _OWORD *, _DWORD *, _QWORD, _QWORD, _QWORD))v7)(v14, v71, v16, v56, 0, 0) )
  {
    v18 = -2147467259;
    goto LABEL_56;
  }
  v64 = v16 + 1;
  *(_OWORD *)v65 = 0;
  if ( ((int (__fastcall *)(_DWORD **))v8)(&v64) < 0 )
  {
    v18 = -2147467259;
    goto LABEL_56;
  }
  v17 = a1[1];
  v18 = 0;
  v19 = v65[0];
  v55 = 0;
  LODWORD(v57) = v65[0];
  if ( v17 != 4 )
  {
    switch ( v17 )
    {
      case 0u:
        if ( a1[4] == 16 )
        {
          v46 = (_QWORD *)*((_QWORD *)a1 + 1);
          *(_QWORD *)&v69 = 24;
          v67 = 0;
          lpMem[0] = (LPVOID)(v65[0] | 0x300000000LL);
          lpMem[1] = &v66;
          v66 = 0;
          if ( ((int (__fastcall *)(LPVOID *))v9)(lpMem) < 0 )
            goto LABEL_98;
          ProcessVideoMemoryReporting(v59, v19, (struct _D3DKMT_SEGMENTSIZEINFO *)&v66);
          v47 = v67;
          *v46 = v66 + *((_QWORD *)&v66 + 1);
          v46[1] = v47;
        }
        else
        {
          v18 = -2147024809;
        }
        break;
      case 1u:
        if ( a1[4] == 12 )
        {
          v48 = *((_QWORD *)a1 + 1);
          v67 = 12;
          lpMem[0] = 0;
          LODWORD(lpMem[1]) = 0;
          *((_QWORD *)&v66 + 1) = lpMem;
          *(_QWORD *)&v66 = v65[0] | 0x600000000LL;
          if ( ((int (__fastcall *)(__int128 *))v9)(&v66) < 0 )
          {
            v18 = -2147467259;
          }
          else
          {
            v49 = (int)lpMem[1];
            *(LPVOID *)v48 = lpMem[0];
            *(_DWORD *)(v48 + 8) = v49;
          }
        }
        else
        {
          v18 = -2147024809;
        }
        break;
      case 2u:
        if ( a1[4] == 2080 )
        {
          v50 = (void *)*((_QWORD *)a1 + 1);
          v67 = 2080;
          memset_0(Src, 0, sizeof(Src));
          *(_QWORD *)&v66 = v19 | 0x800000000LL;
          *((_QWORD *)&v66 + 1) = Src;
          if ( ((int (__fastcall *)(__int128 *))v9)(&v66) < 0 )
            v18 = -2147467259;
          else
            memcpy_0(v50, Src, 0x820u);
        }
        else
        {
          v18 = -2147024809;
        }
        break;
      case 3u:
        if ( a1[4] == 224 )
        {
          v41 = (_DWORD *)*((_QWORD *)a1 + 1);
          *((_QWORD *)&v66 + 1) = lpMem;
          *(_OWORD *)lpMem = 0;
          v67 = 48;
          LODWORD(lpMem[0]) = *v41;
          v69 = 0;
          *(_QWORD *)&v66 = v65[0] | 0x900000000LL;
          v70 = 0;
          if ( ((int (__fastcall *)(__int128 *))v9)(&v66) >= 0 )
            DXGIInitializeDevMode((char *)lpMem + 4, v41 + 1);
          else
            v18 = -2147467259;
        }
        else
        {
          v18 = -2147024809;
        }
        break;
      case 5u:
        if ( a1[4] == 4 )
        {
          v43 = (unsigned int *)*((_QWORD *)a1 + 1);
          *((_QWORD *)&v66 + 1) = &v55;
          v67 = 4;
          v55 = 0;
          *(_QWORD *)&v66 = v65[0] | 0xD00000000LL;
          if ( ((int (__fastcall *)(__int128 *))v9)(&v66) < 0 )
            v18 = -2147467259;
          else
            *v43 = v55;
        }
        else
        {
          v18 = -2147024809;
        }
        break;
      case 6u:
        if ( a1[4] == 12 )
        {
          v42 = (_DWORD *)*((_QWORD *)a1 + 1);
          v67 = 12;
          lpMem[0] = 0;
          LODWORD(lpMem[1]) = 0;
          *((_QWORD *)&v66 + 1) = lpMem;
          *(_QWORD *)&v66 = v65[0] | 0x1100000000LL;
          if ( ((int (__fastcall *)(__int128 *))v9)(&v66) >= 0 )
          {
            v52 = ConvertGraphicsPreemptionEnum(LODWORD(lpMem[0]));
            v53 = HIDWORD(lpMem[0]);
            *v42 = v52;
            v54 = ConvertComputePreemptionEnum(v53);
            v42[2] &= 0xFFFFFFC0;
            v42[1] = v54;
            v42[2] |= (__int64)lpMem[1] & 0x3F;
          }
          else
          {
            v18 = -2147467259;
          }
        }
        else
        {
          v18 = -2147024809;
        }
        break;
      case 7u:
        if ( a1[4] == 4 )
        {
          v44 = (_DWORD *)*((_QWORD *)a1 + 1);
          *((_QWORD *)&v66 + 1) = &v55;
          v67 = 4;
          v55 = 0;
          *(_QWORD *)&v66 = v65[0] | 0x1600000000LL;
          if ( ((int (__fastcall *)(__int128 *))v9)(&v66) < 0 )
          {
            v18 = -2147467259;
          }
          else
          {
            v45 = v55;
            *v44 &= 0xFFFFFFF0;
            *v44 |= v45 & 0xF;
          }
        }
        else
        {
          v18 = -2147024809;
        }
        break;
      default:
LABEL_98:
        v18 = -2147467259;
        break;
    }
    goto LABEL_54;
  }
  if ( a1[4] < 0xE4 )
  {
    v18 = -2147024809;
    goto LABEL_54;
  }
  v20 = (_DWORD *)*((_QWORD *)a1 + 1);
  v66 = 0;
  v67 = 0;
  LODWORD(v66) = v65[0];
  DWORD1(v66) = *v20;
  if ( ((int (__fastcall *)(__int128 *))v10)(&v66) < 0 )
  {
    v18 = -2147467259;
    goto LABEL_54;
  }
  v21 = (int (*)(struct _D3DKMT_QUERYVIDEOMEMORYINFO *))operator new(saturated_mul((unsigned int)v67, 0x2Cu));
  v59 = v21;
  v22 = v21;
  if ( !v21 )
  {
    v18 = -2147024882;
    operator delete(0);
    goto LABEL_54;
  }
  memset_0(v21, 0, 44LL * (unsigned int)v67);
  *((_QWORD *)&v66 + 1) = v22;
  if ( ((int (__fastcall *)(__int128 *))v10)(&v66) < 0 )
    goto LABEL_109;
  v23 = 0;
  v24 = 0;
  if ( (unsigned int)v67 >= 8 )
  {
    si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
    v26 = 0;
    v27 = 0;
    do
    {
      v26 = _mm_add_epi32(
              v26,
              (__m128i)_mm_andnot_ps(
                         (__m128)_mm_cmpeq_epi32(
                                   (__m128i)_mm_and_ps(
                                              (__m128)_mm_unpacklo_epi64(
                                                        _mm_unpacklo_epi32(
                                                          _mm_cvtsi32_si128(*(_DWORD *)(44LL * v24
                                                                                      + *((_QWORD *)&v66 + 1)
                                                                                      + 36)),
                                                          _mm_cvtsi32_si128(*(_DWORD *)(44LL * (v24 + 1)
                                                                                      + *((_QWORD *)&v66 + 1)
                                                                                      + 36))),
                                                        _mm_unpacklo_epi32(
                                                          _mm_cvtsi32_si128(*(_DWORD *)(44LL * (v24 + 2)
                                                                                      + *((_QWORD *)&v66 + 1)
                                                                                      + 36)),
                                                          _mm_cvtsi32_si128(*(_DWORD *)(44LL * (v24 + 3)
                                                                                      + *((_QWORD *)&v66 + 1)
                                                                                      + 36)))),
                                              si128),
                                   (__m128i)0LL),
                         si128));
      v28 = 44LL * (v24 + 5);
      v29 = _mm_unpacklo_epi32(
              _mm_cvtsi32_si128(*(_DWORD *)(44LL * (v24 + 6) + *((_QWORD *)&v66 + 1) + 36)),
              _mm_cvtsi32_si128(*(_DWORD *)(44LL * (v24 + 7) + *((_QWORD *)&v66 + 1) + 36)));
      v30 = v24 + 4;
      v24 += 8;
      v31 = _mm_add_epi32(
              (__m128i)_mm_andnot_ps(
                         (__m128)_mm_cmpeq_epi32(
                                   (__m128i)_mm_and_ps(
                                              (__m128)_mm_unpacklo_epi64(
                                                        _mm_unpacklo_epi32(
                                                          _mm_cvtsi32_si128(*(_DWORD *)(44 * v30
                                                                                      + *((_QWORD *)&v66 + 1)
                                                                                      + 36)),
                                                          _mm_cvtsi32_si128(*(_DWORD *)(v28 + *((_QWORD *)&v66 + 1) + 36))),
                                                        v29),
                                              si128),
                                   (__m128i)0LL),
                         si128),
              v27);
      v27 = v31;
    }
    while ( v24 < ((unsigned int)v67 & 0xFFFFFFF8) );
    v32 = _mm_add_epi32(v26, v31);
    v33 = _mm_add_epi32(v32, _mm_srli_si128(v32, 8));
    v23 = _mm_cvtsi128_si32(_mm_add_epi32(v33, _mm_srli_si128(v33, 4)));
  }
  for ( ; v24 < (unsigned int)v67; ++v24 )
  {
    if ( (*(_BYTE *)(44LL * v24 + *((_QWORD *)&v66 + 1) + 36) & 1) != 0 )
      ++v23;
  }
  if ( !v23 )
  {
LABEL_109:
    v18 = -2147467259;
    operator delete(v22);
    goto LABEL_54;
  }
  v20[1] = v23;
  if ( a1[4] < 220 * (unsigned __int64)(unsigned int)(v23 - 1) + 228 )
  {
    v18 = -2147024774;
    operator delete(v22);
    goto LABEL_54;
  }
  v34 = v67;
  v35 = 0;
  v36 = 0;
  if ( !(_DWORD)v67 )
    goto LABEL_53;
  do
  {
    v37 = *((_QWORD *)&v66 + 1);
    v38 = 44LL * v36;
    if ( (*(_BYTE *)(v38 + *((_QWORD *)&v66 + 1) + 36) & 1) == 0 )
      goto LABEL_51;
    v39 = &v20[55 * v35];
    memset_0(v39 + 2, 0, 0xDCu);
    v39[18] = 67175425;
    *((_WORD *)v39 + 38) = 220;
    v39[20] = 544997504;
    if ( *(_DWORD *)(v38 + v37 + 28) != 1 )
    {
      switch ( *(_DWORD *)(v38 + v37 + 28) )
      {
        case 2:
          v39[23] = 1;
          break;
        case 3:
          v39[23] = 2;
          break;
        case 4:
          v39[23] = 3;
          break;
      }
    }
    switch ( *(_DWORD *)(v38 + v37 + 8) )
    {
      case 0x14:
        v39[44] = 24;
        break;
      case 0x15:
        goto LABEL_47;
      case 0x17:
        v39[44] = 16;
        break;
      case 0x29:
        v39[44] = 8;
        break;
      default:
LABEL_47:
        v39[44] = 32;
        break;
    }
    v39[24] = *(_DWORD *)(v38 + v37 + 32);
    v39[45] = *(_DWORD *)(v38 + v37);
    v39[46] = *(_DWORD *)(v38 + v37 + 4);
    v39[48] = *(_DWORD *)(v38 + v37 + 16) / *(_DWORD *)(v38 + v37 + 20);
    if ( (unsigned int)(*(_DWORD *)(v38 + v37 + 24) - 2) <= 1 )
      v39[47] |= 2u;
    v34 = v67;
    ++v35;
LABEL_51:
    ++v36;
  }
  while ( v36 < v34 );
  v22 = v59;
LABEL_53:
  operator delete(v22);
  v18 = v55;
  v16 = lpMem[0];
LABEL_54:
  if ( (_DWORD)v57 )
    v63(&v57);
LABEL_56:
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v16);
LABEL_57:
  ((void (__fastcall *)(__int64))v62)(v61);
LABEL_58:
  v2 = Library;
  v4 = hModule;
LABEL_87:
  FreeLibrary(v4);
LABEL_88:
  if ( v2 )
    FreeLibrary(v2);
  return v18;
}

```

## disassembly

```asm
0x18001b530  mov     r11, rsp
0x18001b533  push    rbp
0x18001b534  push    rdi
0x18001b535  lea     rbp, [r11-888h]
0x18001b53c  sub     rsp, 978h
0x18001b543  mov     rax, cs:__security_cookie
0x18001b54a  xor     rax, rsp
0x18001b54d  mov     [rbp+880h+var_60], rax
0x18001b554  mov     rdi, rcx
0x18001b557  test    rcx, rcx
0x18001b55a  jz      loc_18001BF67
0x18001b560  mov     [r11+18h], rsi
0x18001b564  lea     rcx, aSetupapiDll; "setupapi.dll"
0x18001b56b  mov     [r11+20h], r12
0x18001b56f  xor     r8d, r8d; dwFlags
0x18001b572  xor     edx, edx; hFile
0x18001b574  mov     [r11-20h], r14
0x18001b578  call    cs:__imp_LoadLibraryExW
0x18001b57e  xor     r8d, r8d; dwFlags
0x18001b581  lea     rcx, LibFileName; "gdi32.dll"
0x18001b588  xor     edx, edx; hFile
0x18001b58a  mov     [rsp+980h+var_920], rax
0x18001b58f  mov     r14, rax
0x18001b592  call    cs:__imp_LoadLibraryExW
0x18001b598  mov     [rsp+980h+hModule], rax
0x18001b59d  mov     r12, rax
0x18001b5a0  test    r14, r14
0x18001b5a3  jz      loc_18001BEC4
0x18001b5a9  test    rax, rax
0x18001b5ac  jz      loc_18001BEC4
0x18001b5b2  mov     [rsp+980h+arg_8], rbx
0x18001b5ba  lea     rdx, aSetupdigetclas; "SetupDiGetClassDevsW"
0x18001b5c1  mov     [rsp+970h], r13
0x18001b5c9  mov     rcx, r14; hModule
0x18001b5cc  mov     [rsp+980h+var_20], r15
0x18001b5d4  call    cs:__imp_GetProcAddress
0x18001b5da  lea     rdx, aSetupdienumdev; "SetupDiEnumDeviceInterfaces"
0x18001b5e1  mov     rcx, r14; hModule
0x18001b5e4  mov     r15, rax
0x18001b5e7  call    cs:__imp_GetProcAddress
0x18001b5ed  lea     rdx, aSetupdigetdevi; "SetupDiGetDeviceInterfaceDetailW"
0x18001b5f4  mov     rcx, r14; hModule
0x18001b5f7  mov     rsi, rax
0x18001b5fa  call    cs:__imp_GetProcAddress
0x18001b600  lea     rdx, aSetupdidestroy; "SetupDiDestroyDeviceInfoList"
0x18001b607  mov     rcx, r14; hModule
0x18001b60a  mov     rbx, rax
0x18001b60d  call    cs:__imp_GetProcAddress
0x18001b613  lea     rdx, aD3dkmtopenadap_2; "D3DKMTOpenAdapterFromDeviceName"
0x18001b61a  mov     rcx, r12; hModule
0x18001b61d  mov     [rsp+980h+var_910], rax
0x18001b622  call    cs:__imp_GetProcAddress
0x18001b628  lea     rdx, aD3dkmtqueryada_0; "D3DKMTQueryAdapterInfo"
0x18001b62f  mov     rcx, r12; hModule
0x18001b632  mov     r14, rax
0x18001b635  call    cs:__imp_GetProcAddress
0x18001b63b  lea     rdx, aD3dkmtqueryvid_1; "D3DKMTQueryVideoMemoryInfo"
0x18001b642  mov     rcx, r12; hModule
0x18001b645  mov     r13, rax
0x18001b648  call    cs:__imp_GetProcAddress
0x18001b64e  lea     rdx, aD3dkmtgetdispl; "D3DKMTGetDisplayModeList"
0x18001b655  mov     rcx, r12; hModule
0x18001b658  mov     [rsp+980h+var_928], rax
0x18001b65d  call    cs:__imp_GetProcAddress
0x18001b663  mov     rcx, [rsp+980h+hModule]; hModule
0x18001b668  lea     rdx, aD3dkmtcloseada; "D3DKMTCloseAdapter"
0x18001b66f  mov     r12, rax
0x18001b672  call    cs:__imp_GetProcAddress
0x18001b678  mov     [rsp+980h+var_908], rax
0x18001b67d  test    r15, r15
0x18001b680  jz      loc_18001BC61
0x18001b686  test    rsi, rsi
0x18001b689  jz      loc_18001BC61
0x18001b68f  test    rbx, rbx
0x18001b692  jz      loc_18001BC61
0x18001b698  cmp     [rsp+980h+var_910], 0
0x18001b69e  jz      loc_18001BC61
0x18001b6a4  test    r14, r14
0x18001b6a7  jz      loc_18001BC61
0x18001b6ad  test    r13, r13
0x18001b6b0  jz      loc_18001BC61
0x18001b6b6  cmp     [rsp+980h+var_928], 0
0x18001b6bc  jz      loc_18001BC61
0x18001b6c2  test    r12, r12
0x18001b6c5  jz      loc_18001BC61
0x18001b6cb  test    rax, rax
0x18001b6ce  jz      loc_18001BC61
0x18001b6d4  mov     r9d, 12h
0x18001b6da  lea     rcx, GUID_DISPLAY_DEVICE_ARRIVAL
0x18001b6e1  xor     r8d, r8d
0x18001b6e4  xor     edx, edx
0x18001b6e6  mov     rax, r15
0x18001b6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6ee  mov     [rsp+980h+var_918], rax
0x18001b6f3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b6f7  jz      loc_18001BFD9
0x18001b6fd  mov     r9d, [rdi]
0x18001b700  lea     rcx, [rbp+880h+var_8A0]
0x18001b704  xorps   xmm0, xmm0
0x18001b707  mov     [rsp+980h+var_960], rcx
0x18001b70c  mov     rcx, rax
0x18001b70f  lea     r8, GUID_DISPLAY_DEVICE_ARRIVAL
0x18001b716  movups  [rbp+880h+var_8A0], xmm0
0x18001b71a  mov     rax, rsi
0x18001b71d  mov     dword ptr [rbp+880h+var_8A0], 20h ; ' '
0x18001b724  xor     edx, edx
0x18001b726  movups  [rbp+880h+var_890], xmm0
0x18001b72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b72f  test    eax, eax
0x18001b731  jz      loc_18001C009
0x18001b737  mov     rsi, [rsp+980h+var_918]
0x18001b73c  lea     rdx, [rbp+880h+var_8A0]
0x18001b740  xor     eax, eax
0x18001b742  xor     r9d, r9d
0x18001b745  mov     [rsp+28h], rax
0x18001b74a  xor     r8d, r8d
0x18001b74d  mov     [rsp+980h+var_93C], eax
0x18001b751  mov     rcx, rsi
0x18001b754  lea     rax, [rsp+980h+var_93C]
0x18001b759  mov     [rsp+980h+var_960], rax
0x18001b75e  mov     rax, rbx
0x18001b761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b766  test    eax, eax
0x18001b768  jnz     loc_18001BFFF
0x18001b76e  call    cs:__imp_GetLastError
0x18001b774  cmp     eax, 7Ah ; 'z'
0x18001b777  jnz     loc_18001BFFF
0x18001b77d  mov     ecx, [rsp+980h+var_93C]; dwBytes
0x18001b781  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b786  mov     [rbp+880h+lpMem], rax
0x18001b78a  mov     r15, rax
0x18001b78d  test    rax, rax
0x18001b790  jz      loc_18001C013
0x18001b796  mov     r8d, [rsp+980h+var_93C]; Size
0x18001b79b  xor     edx, edx; Val
0x18001b79d  mov     rcx, rax; void *
0x18001b7a0  call    memset_0
0x18001b7a5  xor     eax, eax
0x18001b7a7  mov     dword ptr [r15], 8
0x18001b7ae  mov     r9d, [rsp+980h+var_93C]
0x18001b7b3  lea     rdx, [rbp+880h+var_8A0]
0x18001b7b7  mov     [rsp+28h], rax
0x18001b7bc  mov     r8, r15
0x18001b7bf  mov     [rsp+980h+var_960], rax
0x18001b7c4  mov     rcx, rsi
0x18001b7c7  mov     rax, rbx
0x18001b7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7cf  test    eax, eax
0x18001b7d1  jz      loc_18001C01D
0x18001b7d7  lea     rcx, [r15+4]
0x18001b7db  xorps   xmm0, xmm0
0x18001b7de  mov     [rbp+880h+var_900], rcx
0x18001b7e2  mov     rax, r14
0x18001b7e5  lea     rcx, [rbp+880h+var_900]
0x18001b7e9  movdqu  xmmword ptr [rbp+880h+var_8F8], xmm0
0x18001b7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7f3  test    eax, eax
0x18001b7f5  js      loc_18001C027
0x18001b7fb  movsxd  rax, dword ptr [rdi+4]
0x18001b7ff  xor     esi, esi
0x18001b801  mov     r14d, [rbp+880h+var_8F8]
0x18001b805  mov     [rsp+980h+var_940], esi
0x18001b809  mov     dword ptr [rsp+980h+var_938], r14d
0x18001b80e  cmp     eax, 4
0x18001b811  jnz     loc_18001BBE7
0x18001b817  cmp     dword ptr [rdi+10h], 0E4h
0x18001b81e  jb      loc_18001BF3F
0x18001b824  mov     r13, [rdi+8]
0x18001b828  lea     rcx, [rbp+880h+var_8E8]
0x18001b82c  xor     eax, eax
0x18001b82e  xorps   xmm0, xmm0
0x18001b831  movups  [rbp+880h+var_8E8], xmm0
0x18001b835  mov     [rbp+880h+var_8D8], rax
0x18001b839  mov     dword ptr [rbp+880h+var_8E8], r14d
0x18001b83d  mov     eax, [r13+0]
0x18001b841  mov     dword ptr [rbp+880h+var_8E8+4], eax
0x18001b844  mov     rax, r12
0x18001b847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b84c  test    eax, eax
0x18001b84e  js      loc_18001BFE3
0x18001b854  mov     ecx, dword ptr [rbp+880h+var_8D8]
0x18001b857  mov     eax, 2Ch ; ','
0x18001b85c  mul     rcx
0x18001b85f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001b866  cmovb   rax, rcx
0x18001b86a  mov     rcx, rax; dwBytes
0x18001b86d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b872  mov     [rsp+980h+var_928], rax
0x18001b877  mov     rbx, rax
0x18001b87a  test    rax, rax
0x18001b87d  jz      loc_18001BFC8
0x18001b883  mov     ecx, dword ptr [rbp+880h+var_8D8]
0x18001b886  xor     edx, edx; Val
0x18001b888  imul    r8, rcx, 2Ch ; ','; Size
0x18001b88c  mov     rcx, rax; void *
0x18001b88f  call    memset_0
0x18001b894  lea     rcx, [rbp+880h+var_8E8]
0x18001b898  mov     qword ptr [rbp+880h+var_8E8+8], rbx
0x18001b89c  mov     rax, r12
0x18001b89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8a4  test    eax, eax
0x18001b8a6  js      loc_18001BFED
0x18001b8ac  mov     r14d, dword ptr [rbp+880h+var_8D8]
0x18001b8b0  xor     edx, edx
0x18001b8b2  mov     r11, qword ptr [rbp+880h+var_8E8+8]
0x18001b8b6  xor     r10d, r10d
0x18001b8b9  cmp     r14d, 8
0x18001b8bd  jb      loc_18001B9F9
0x18001b8c3  movdqa  xmm5, cs:__xmm@00000001000000010000000100000001
0x18001b8cb  mov     esi, r14d
0x18001b8ce  movaps  [rsp+980h+var_38+8], xmm6
0x18001b8d6  and     esi, 0FFFFFFF8h
0x18001b8d9  movaps  [rsp+980h+var_48+8], xmm7
0x18001b8e1  xorps   xmm4, xmm4
0x18001b8e4  movaps  [rsp+980h+var_58+8], xmm8
0x18001b8ed  xorps   xmm6, xmm6
0x18001b8f0  xorps   xmm8, xmm8
0x18001b8f4  nop     dword ptr [rax+00h]
0x18001b8f8  nop     dword ptr [rax+rax+00000000h]
0x18001b900  lea     ecx, [r10+3]
0x18001b904  mov     eax, r10d
0x18001b907  imul    r9, rcx, 2Ch ; ','
0x18001b90b  lea     ecx, [r10+2]
0x18001b90f  imul    r8, rcx, 2Ch ; ','
0x18001b913  movd    xmm1, dword ptr [r9+r11+24h]
0x18001b91a  lea     ecx, [r10+1]
0x18001b91e  imul    rdx, rcx, 2Ch ; ','
0x18001b922  movd    xmm2, dword ptr [r8+r11+24h]
0x18001b929  imul    rcx, rax, 2Ch ; ','
0x18001b92d  movd    xmm0, dword ptr [rdx+r11+24h]
0x18001b934  punpckldq xmm2, xmm1
0x18001b938  movd    xmm3, dword ptr [rcx+r11+24h]
0x18001b93f  lea     ecx, [r10+7]
0x18001b943  punpckldq xmm3, xmm0
0x18001b947  punpcklqdq xmm3, xmm2
0x18001b94b  andps   xmm3, xmm5
0x18001b94e  pcmpeqd xmm3, xmm6
0x18001b952  andnps  xmm3, xmm5
0x18001b955  paddd   xmm4, xmm3
0x18001b959  imul    r9, rcx, 2Ch ; ','
0x18001b95d  lea     ecx, [r10+6]
0x18001b961  imul    r8, rcx, 2Ch ; ','
0x18001b965  movd    xmm1, dword ptr [r9+r11+24h]
0x18001b96c  lea     ecx, [r10+5]
0x18001b970  imul    rdx, rcx, 2Ch ; ','
0x18001b974  movd    xmm2, dword ptr [r8+r11+24h]
0x18001b97b  punpckldq xmm2, xmm1
0x18001b97f  lea     ecx, [r10+4]
0x18001b983  add     r10d, 8
0x18001b987  imul    rax, rcx, 2Ch ; ','
0x18001b98b  movd    xmm0, dword ptr [rdx+r11+24h]
0x18001b992  movd    xmm3, dword ptr [rax+r11+24h]
0x18001b999  punpckldq xmm3, xmm0
0x18001b99d  punpcklqdq xmm3, xmm2
0x18001b9a1  andps   xmm3, xmm5
0x18001b9a4  pcmpeqd xmm3, xmm6
0x18001b9a8  andnps  xmm3, xmm5
0x18001b9ab  paddd   xmm3, xmm8
0x18001b9b0  movdqa  xmm8, xmm3
0x18001b9b5  cmp     r10d, esi
0x18001b9b8  jb      loc_18001B900
0x18001b9be  movaps  xmm7, [rsp+980h+var_48+8]
0x18001b9c6  paddd   xmm4, xmm3
0x18001b9ca  movaps  xmm6, [rsp+980h+var_38+8]
0x18001b9d2  movdqa  xmm0, xmm4
0x18001b9d6  movaps  xmm8, [rsp+980h+var_58+8]
0x18001b9df  psrldq  xmm0, 8
0x18001b9e4  paddd   xmm4, xmm0
0x18001b9e8  movdqa  xmm0, xmm4
0x18001b9ec  psrldq  xmm0, 4
0x18001b9f1  paddd   xmm4, xmm0
0x18001b9f5  movd    edx, xmm4
0x18001b9f9  cmp     r10d, r14d
0x18001b9fc  jnb     short loc_18001BA19
0x18001b9fe  xchg    ax, ax
0x18001ba00  mov     eax, r10d
0x18001ba03  imul    rcx, rax, 2Ch ; ','
0x18001ba07  test    byte ptr [rcx+r11+24h], 1
0x18001ba0d  jz      short loc_18001BA11
0x18001ba0f  inc     edx
0x18001ba11  inc     r10d
0x18001ba14  cmp     r10d, r14d
0x18001ba17  jb      short loc_18001BA00
0x18001ba19  test    edx, edx
0x18001ba1b  jz      loc_18001C031
0x18001ba21  mov     [r13+4], edx
0x18001ba25  lea     ecx, [rdx-1]
0x18001ba28  mov     eax, [rdi+10h]
0x18001ba2b  imul    rdx, rcx, 0DCh
0x18001ba32  add     rdx, 0E4h
0x18001ba39  cmp     rax, rdx
0x18001ba3c  jb      loc_18001BEA0
0x18001ba42  mov     ecx, dword ptr [rbp+880h+var_8D8]
0x18001ba45  xor     r12d, r12d
0x18001ba48  xor     r15d, r15d
0x18001ba4b  test    ecx, ecx
0x18001ba4d  jz      loc_18001BB58
0x18001ba53  mov     ebx, 0DCh
0x18001ba58  nop     dword ptr [rax+rax+00000000h]
0x18001ba60  mov     rdi, qword ptr [rbp+880h+var_8E8+8]
  ... truncated ...
```
