# GetSrumData(_LARGE_INTEGER,_LARGE_INTEGER,std::map<SrumKey,EnergyEstimationInfo *,std::less<SrumKey>,std::allocator<std::pair<SrumKey const,EnergyEstimationInfo *>>> &,std::map<SrumKey,EnergyEstimationInfo *,std::less<SrumKey>,std::allocator<std::pair<SrumKey const,EnergyEstimationInfo *>>> &,uchar)

- ea: `0x180007920`
- end: `0x180008739`
- name: `?GetSrumData@@YAKT_LARGE_INTEGER@@0AEAV?$map@USrumKey@@PEAUEnergyEstimationInfo@@U?$less@USrumKey@@@std@@V?$allocator@U?$pair@$$CBUSrumKey@@PEAUEnergyEstimationInfo@@@std@@@4@@std@@1E@Z`
- size: `3609`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800395d8`
- `0x180057a3c`

## callees

- `0x180006350`
- `0x180007920`
- `0x180008740`
- `0x1800087e8`
- `0x180008a4c`
- `0x180008d2c`
- `0x180008d64`
- `0x180008da0`
- `0x180008f30`
- `0x180025224`
- `0x1800253e0`
- `0x18003ae80`
- `0x18003bb60`
- `0x18003bf74`
- `0x18003dfdc`
- `0x18004ca90`
- `0x18004ce78`
- `0x18004d12c`
- `0x18004d194`
- `0x18004dea8`
- `0x1800867c0`
- `0x180086890`
- `0x1800907f0`
- `0x180096010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180008664`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180008664`
- `ntdll!RtlCopySid` at `0x180007c56`
- `ntdll!RtlCopySid` at `0x180007c56`
- `ntdll!RtlLengthSid` at `0x180007c2b`
- `ntdll!RtlLengthSid` at `0x180007c2b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800079d8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800079f6`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800079d8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800079f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800080ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800080ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007c3a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007c3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GetSrumData(FILETIME a1, FILETIME a2, _QWORD *a3, _QWORD *a4, char a5)
{
  unsigned int v5; // edi
  struct _SYSTEMTIME v6; // xmm0
  unsigned int v7; // esi
  Srum *v8; // rbx
  unsigned int v9; // ecx
  __m128i si128; // xmm7
  unsigned __int64 v11; // rdi
  unsigned __int64 v12; // rbx
  __int64 v13; // rdx
  char *v14; // rcx
  int v15; // r10d
  __int64 *v16; // r8
  unsigned __int64 v17; // r11
  unsigned int v18; // r9d
  __int64 i; // rdx
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  char v22; // r12
  _QWORD *v23; // r14
  unsigned __int64 v24; // rdi
  __int128 v25; // xmm0
  void *v26; // rbx
  SIZE_T v27; // rsi
  HLOCAL v28; // rax
  __int64 *KeyData; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  volatile signed __int32 *v32; // rbx
  volatile signed __int32 *v33; // rbx
  int v34; // ecx
  __int64 v35; // rdx
  __int64 v36; // r8
  __int128 v37; // kr10_16
  volatile signed __int32 *v38; // rbx
  volatile signed __int32 *v39; // rbx
  _QWORD *v40; // rbx
  __int64 *v41; // rdi
  const wchar_t *v42; // rsi
  __int64 v43; // r14
  unsigned __int64 v44; // r12
  const wchar_t *v45; // rdx
  unsigned __int64 v46; // r15
  const wchar_t *v47; // rcx
  size_t v48; // r8
  int v49; // eax
  __int64 v50; // rax
  size_t v51; // r8
  const wchar_t *v52; // rcx
  size_t v53; // rsi
  const wchar_t *v54; // rdx
  size_t v55; // r14
  size_t v56; // r8
  int v57; // eax
  char v58; // cl
  __int64 *v59; // rax
  __int64 v60; // rsi
  const wchar_t *v61; // rdi
  unsigned __int64 v62; // r15
  const wchar_t *v63; // rdx
  unsigned __int64 v64; // r14
  const wchar_t *v65; // rcx
  size_t v66; // r8
  int v67; // eax
  __int64 v68; // rax
  size_t v69; // r8
  const wchar_t *v70; // rdx
  size_t v71; // rdi
  size_t v72; // rsi
  const wchar_t *v73; // rcx
  size_t v74; // r8
  int v75; // eax
  _WORD *v76; // rdi
  int v77; // eax
  HANDLE v78; // rcx
  _WORD *v79; // rax
  __int64 v80; // rax
  __int128 v81; // xmm6
  __int64 v82; // rbx
  char *v83; // rax
  __int64 v84; // rcx
  __int64 v85; // r9
  volatile signed __int32 *v86; // rbx
  Srum *v87; // rbx
  volatile signed __int32 *v88; // rbx
  Srum *v90; // rax
  __int64 v91; // rdx
  Srum *v92; // rax
  __int64 v93; // rdx
  unsigned int v94; // [rsp+30h] [rbp-248h]
  unsigned int v95; // [rsp+34h] [rbp-244h]
  __int64 v96; // [rsp+38h] [rbp-240h] BYREF
  PSID v97; // [rsp+40h] [rbp-238h] BYREF
  __int128 v98; // [rsp+50h] [rbp-228h] BYREF
  _QWORD *v99; // [rsp+60h] [rbp-218h]
  _QWORD *v100; // [rsp+68h] [rbp-210h]
  __int64 v101; // [rsp+70h] [rbp-208h]
  __int64 v102; // [rsp+78h] [rbp-200h]
  FILETIME FileTime; // [rsp+80h] [rbp-1F8h] BYREF
  FILETIME v104; // [rsp+88h] [rbp-1F0h] BYREF
  _QWORD *v105; // [rsp+90h] [rbp-1E8h]
  _QWORD *v106; // [rsp+98h] [rbp-1E0h]
  _QWORD *v107; // [rsp+A0h] [rbp-1D8h]
  __int64 v108; // [rsp+A8h] [rbp-1D0h]
  _QWORD v109[12]; // [rsp+B0h] [rbp-1C8h]
  __int64 v110; // [rsp+110h] [rbp-168h]
  unsigned __int16 v111; // [rsp+118h] [rbp-160h]
  char v112; // [rsp+11Ah] [rbp-15Eh]
  _QWORD pExceptionObject[3]; // [rsp+120h] [rbp-158h] BYREF
  _QWORD v114[3]; // [rsp+138h] [rbp-140h] BYREF
  __int64 v115; // [rsp+150h] [rbp-128h] BYREF
  volatile signed __int32 *v116; // [rsp+158h] [rbp-120h]
  wchar_t *S2[2]; // [rsp+160h] [rbp-118h] BYREF
  size_t N[2]; // [rsp+170h] [rbp-108h]
  __int128 v119; // [rsp+180h] [rbp-F8h]
  __int128 v120; // [rsp+190h] [rbp-E8h] BYREF
  __m128i v121; // [rsp+1A0h] [rbp-D8h]
  __int128 v122; // [rsp+1B0h] [rbp-C8h]
  struct _SYSTEMTIME v123; // [rsp+1C0h] [rbp-B8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+1D0h] [rbp-A8h] BYREF
  void *v125[3]; // [rsp+1E0h] [rbp-98h] BYREF
  unsigned __int64 v126; // [rsp+1F8h] [rbp-80h]
  __int128 v127; // [rsp+200h] [rbp-78h]
  _WORD *v128; // [rsp+210h] [rbp-68h]

  v100 = a4;
  v99 = a3;
  FileTime = a1;
  v104 = a2;
  v105 = a3;
  v106 = a4;
  v5 = 0;
  v94 = 0;
  v6 = 0;
  *(_OWORD *)S2 = 0;
  *(_OWORD *)N = 0;
  *(double *)&v6.wYear = std::wstring::_Construct_empty(S2);
  v119 = 0;
  v96 = 0;
  SystemTime = v6;
  v123 = 0;
  if ( FileTimeToSystemTime(&FileTime, &SystemTime) && FileTimeToSystemTime(&v104, &v123) )
  {
    v96 = 0;
    v102 = 4;
    v7 = tls_index;
    if ( dword_1800C8FA0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_1800C8FA0);
      if ( dword_1800C8FA0 == -1 )
      {
        atexit(Srum::Instance_::_2_::_dynamic_atexit_destructor_for__PSrum__);
        Init_thread_footer(&dword_1800C8FA0);
      }
    }
    v8 = (Srum *)qword_1800C8D60;
    if ( !qword_1800C8D60 )
    {
      v90 = (Srum *)operator new(0x18u);
      v8 = v90;
      v101 = (__int64)v90;
      if ( v90 )
      {
        if ( (int)Srum::LoadDll(v90) < 0 )
        {
          *(_QWORD *)v8 = std::_String_val<std::_Simple_types<char>>::_Bxty::_Switch_to_buf;
          *((_QWORD *)v8 + 1) = &SruQueryStatsDefault;
        }
      }
      else
      {
        v8 = 0;
      }
      v91 = qword_1800C8D60;
      qword_1800C8D60 = (__int64)v8;
      if ( v91 )
      {
        std::default_delete<Srum>::operator()();
        v8 = (Srum *)qword_1800C8D60;
      }
    }
    if ( !(*((unsigned int (__fastcall **)(__int64, struct _SYSTEMTIME *, struct _SYSTEMTIME *, __int64, __int64 *))v8
           + 1))(
            7,
            &SystemTime,
            &v123,
            2,
            &v96)
      && v96 )
    {
      v101 = 4;
      v9 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      while ( 1 )
      {
        v95 = v9;
        if ( v9 >= *(_DWORD *)v96 )
          break;
        try
        {
          v11 = (unsigned __int64)v9 << 6;
          v12 = v11 + *(_QWORD *)(v96 + 8);
          if ( *(_WORD *)(v12 + 48) != 1 )
            ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
          if ( **(_WORD **)(v12 + 56) )
            ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
          if ( *(_DWORD *)(*(_QWORD *)(v12 + 56) + 4LL) != 3 )
            ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
          if ( *(_QWORD *)(*(_QWORD *)(v12 + 56) + 8LL) < 0x10u )
            ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
          v13 = *(_QWORD *)(v12 + 56);
          v14 = *(char **)(v13 + 16);
          v112 = *v14;
          v111 = *((_WORD *)v14 + 7);
          v15 = *((unsigned __int16 *)v14 + 4);
          v16 = (__int64 *)&v14[v14[1] & 8 | 0x10LL];
          v17 = *(unsigned int *)(v13 + 8);
          v18 = 8;
          for ( i = 2; (__int16)i < 13; LOWORD(i) = i + 1 )
          {
            if ( _bittest(&v15, (unsigned __int8)i) )
            {
              v21 = v18 + 8LL;
              if ( v21 > v17 )
              {
                MicrosoftTelemetryAssertTriggeredNoArgs(v21, i, v16);
                break;
              }
              v20 = *v16++;
              v18 += 8;
            }
            else
            {
              v20 = 0;
            }
            v109[(__int16)i] = v20;
          }
          v109[0] = 0;
          v109[1] = 0;
          v109[11] = 0;
        }
        catch ( std::invalid_argument )
        {
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          v99 = v105;
          v100 = v106;
          goto LABEL_103;
        }
        v22 = v112;
        if ( (v112 & 8) != 0 || a5 )
        {
          v23 = v99;
          if ( v110 )
            v23 = v100;
          *(_QWORD *)&v98 = v23;
          v24 = *(_QWORD *)(v96 + 8) + v11;
          v25 = 0;
          v120 = 0;
          v121 = 0;
          *(double *)&v25 = std::wstring::_Construct_empty(&v120);
          v122 = v25;
          if ( dword_1800C8F30 > *(_DWORD *)(v101 + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v7)) )
          {
            Init_thread_header(&dword_1800C8F30);
            if ( dword_1800C8F30 == -1 )
            {
              anonymous_namespace_::SrumDataCache::SrumDataCache();
              atexit(``anonymous namespace'::SrumDataCache::GetInstance'::`2'::`dynamic atexit destructor for 'Instance'');
              Init_thread_footer(&dword_1800C8F30);
            }
          }
          v26 = *(void **)(v24 + 40);
          v97 = 0;
          v27 = RtlLengthSid(v26);
          v28 = LocalAlloc(0x40u, v27);
          v97 = v28;
          if ( !v28 )
          {
            pExceptionObject[2] = 0;
            pExceptionObject[1] = "bad allocation";
            pExceptionObject[0] = &std::bad_alloc::`vftable';
            throw (std::bad_alloc *)pExceptionObject;
          }
          RtlCopySid(v27, v28, v26);
          KeyData = anonymous_namespace_::SrumDataCache::GetKeyData((char *)&qword_1800C8F40, &v115, &v97);
          v30 = *KeyData;
          v31 = KeyData[1];
          *KeyData = 0;
          KeyData[1] = 0;
          *(_QWORD *)&v122 = v30;
          v32 = (volatile signed __int32 *)*((_QWORD *)&v122 + 1);
          *((_QWORD *)&v122 + 1) = v31;
          if ( v32 )
          {
            if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
              if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
            }
          }
          v33 = v116;
          if ( v116 )
          {
            if ( _InterlockedExchangeAdd(v116 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
              if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
            }
          }
          v34 = *(_DWORD *)(v24 + 16);
          if ( v34 )
          {
            if ( (unsigned int)(v34 - 1) < 2 )
              std::wstring::assign(&v120, *(_QWORD *)(v24 + 24));
            else
              std::wstring::assign(&v120, L"Unknown");
          }
          else
          {
            v35 = *(_QWORD *)(v24 + 24);
            v36 = -1;
            do
              ++v36;
            while ( *(_WORD *)(v35 + 2 * v36) );
            std::wstring::_Assign<unsigned short>(&v120, v35, v36);
          }
          if ( N[1] > 7 )
            std::_Deallocate<16>(S2[0], 2 * N[1] + 2);
          *(_OWORD *)S2 = v120;
          *(__m128i *)N = v121;
          v121 = si128;
          LOWORD(v120) = 0;
          v37 = v122;
          v122 = 0;
          v38 = (volatile signed __int32 *)*((_QWORD *)&v119 + 1);
          v119 = v37;
          if ( v38 )
          {
            if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
              if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
            }
          }
          v39 = (volatile signed __int32 *)*((_QWORD *)&v122 + 1);
          if ( *((_QWORD *)&v122 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v122 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
              if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
            }
          }
          if ( v121.m128i_i64[1] > 7uLL )
            std::_Deallocate<16>((void *)v120, 2 * v121.m128i_i64[1] + 2);
          v40 = (_QWORD *)*v23;
          v41 = *(__int64 **)(*v23 + 8LL);
          HIDWORD(v120) = 0;
          if ( !*((_BYTE *)v41 + 25) )
          {
            while ( 1 )
            {
              v42 = (const wchar_t *)(v119 + 32);
              v43 = v41[8] + 32;
              v44 = *(_QWORD *)(v119 + 48);
              v45 = (const wchar_t *)(v119 + 32);
              if ( *(_QWORD *)(v119 + 56) > 7u )
                v45 = *(const wchar_t **)v42;
              v46 = *(_QWORD *)(v41[8] + 48);
              v47 = (const wchar_t *)(v41[8] + 32);
              if ( *(_QWORD *)(v41[8] + 56) > 7u )
                v47 = *(const wchar_t **)v43;
              v48 = *(_QWORD *)(v119 + 48);
              if ( v44 >= v46 )
                v48 = *(_QWORD *)(v41[8] + 48);
              v49 = wmemcmp(v47, v45, v48);
              if ( v49 )
              {
                if ( v49 < 0 )
                  goto LABEL_119;
              }
              else if ( v46 < v44 )
              {
                goto LABEL_119;
              }
              v50 = *((_QWORD *)v42 + 2);
              if ( *((_QWORD *)v42 + 3) > 7u )
                v42 = *(const wchar_t **)v42;
              v51 = *(_QWORD *)(v43 + 16);
              if ( *(_QWORD *)(v43 + 24) > 7u )
                v43 = *(_QWORD *)v43;
              if ( v51 == v50 && (!v51 || !wmemcmp((const wchar_t *)v43, v42, v51)) )
              {
                v52 = (const wchar_t *)(v41 + 4);
                v53 = N[0];
                v54 = (const wchar_t *)S2;
                if ( N[1] > 7 )
                  v54 = S2[0];
                v55 = v41[6];
                if ( (unsigned __int64)v41[7] > 7 )
                  v52 = *(const wchar_t **)v52;
                v56 = N[0];
                if ( N[0] >= v55 )
                  v56 = v41[6];
                v57 = wmemcmp(v52, v54, v56);
                if ( v57 )
                {
                  if ( v57 < 0 )
                    goto LABEL_119;
                }
                else if ( v55 < v53 )
                {
LABEL_119:
                  v58 = 1;
                  goto LABEL_73;
                }
              }
              v58 = 0;
              v40 = v41;
LABEL_73:
              v59 = v41 + 2;
              if ( !v58 )
                v59 = v41;
              v41 = (__int64 *)*v59;
              if ( *(_BYTE *)(*v59 + 25) )
              {
                v23 = (_QWORD *)v98;
                v22 = v112;
                break;
              }
            }
          }
          if ( v40 == (_QWORD *)*v23 )
            goto LABEL_107;
          v60 = v40[8] + 32LL;
          v61 = (const wchar_t *)(v119 + 32);
          v62 = *(_QWORD *)(v40[8] + 48LL);
          v63 = (const wchar_t *)v60;
          if ( *(_QWORD *)(v40[8] + 56LL) > 7u )
            v63 = *(const wchar_t **)v60;
          v64 = *(_QWORD *)(v119 + 48);
          v65 = (const wchar_t *)(v119 + 32);
          if ( *(_QWORD *)(v119 + 56) > 7u )
            v65 = *(const wchar_t **)v61;
          v66 = *(_QWORD *)(v40[8] + 48LL);
          if ( v62 >= v64 )
            v66 = *(_QWORD *)(v119 + 48);
          v67 = wmemcmp(v65, v63, v66);
          if ( v67 )
          {
            if ( v67 >= 0 )
              goto LABEL_86;
LABEL_106:
            v23 = (_QWORD *)v98;
LABEL_107:
            v78 = NewOperatorMemoryArena;
            if ( !NewOperatorMemoryArena && (InitializeMemoryArena(), (v78 = NewOperatorMemoryArena) == 0)
              || (v79 = HeapAlloc(v78, 8u, 0x70u), (v76 = v79) == 0) )
            {
              v114[2] = 0;
              v114[1] = "bad allocation";
              v114[0] = &std::bad_alloc::`vftable';
              throw (std::bad_alloc *)v114;
            }
            v79[52] = 0;
            *((_BYTE *)v79 + 106) = 0;
            *(_OWORD *)v79 = 0;
            *((_OWORD *)v79 + 1) = 0;
            *((_OWORD *)v79 + 2) = 0;
            *((_OWORD *)v79 + 3) = 0;
            *((_OWORD *)v79 + 4) = 0;
            *((_OWORD *)v79 + 5) = 0;
            *((_QWORD *)v79 + 12) = 0;
            std::wstring::wstring((__int64)v125, (__int64)S2);
            v127 = v119;
            v119 = 0;
            v128 = v76;
            v80 = std::_Tree<std::_Tmap_traits<SrumKey,EnergyEstimationInfo *,std::less<SrumKey>,std::allocator<std::pair<SrumKey const,EnergyEstimationInfo *>>,0>>::_Find_hint<SrumKey>(
                    v23,
                    &v120,
                    v40,
                    v125);
            v81 = *(_OWORD *)v80;
            if ( !*(_BYTE *)(v80 + 16) )
            {
              if ( v23[1] == 0x2E8BA2E8BA2E8BALL )
                std::_Xlength_error("map/set too long");
              v107 = v23;
              v108 = 0;
              v82 = *v23;
              v83 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(0x58u);
              SrumKey::SrumKey(v83 + 32, v125);
              *(_QWORD *)(v84 + 48) = v128;
              *(_QWORD *)v85 = v82;
              *(_QWORD *)(v85 + 8) = v82;
              *(_QWORD *)(v85 + 16) = v82;
              *(_WORD *)(v85 + 24) = 0;
              v108 = 0;
              v98 = v81;
              std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,Domain>>>::_Insert_node(
                v23,
                &v98,
                v85);
            }
            v86 = (volatile signed __int32 *)*((_QWORD *)&v127 + 1);
            if ( *((_QWORD *)&v127 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v127 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v86)(v86);
                if ( _InterlockedExchangeAdd(v86 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v86 + 8LL))(v86);
              }
            }
            if ( v126 > 7 )
              std::_Deallocate<16>(v125[0], 2 * v126 + 2);
          }
          else
          {
            if ( v64 < v62 )
              goto LABEL_106;
LABEL_86:
            v68 = *(_QWORD *)(v60 + 16);
            if ( *(_QWORD *)(v60 + 24) > 7u )
              v60 = *(_QWORD *)v60;
            v69 = *((_QWORD *)v61 + 2);
            if ( *((_QWORD *)v61 + 3) > 7u )
              v61 = *(const wchar_t **)v61;
            if ( v69 == v68 && (!v69 || !wmemcmp(v61, (const wchar_t *)v60, v69)) )
            {
              v70 = (const wchar_t *)(v40 + 4);
              v71 = v40[6];
              if ( v40[7] > 7u )
                v70 = *(const wchar_t **)v70;
              v72 = N[0];
              v73 = (const wchar_t *)S2;
              if ( N[1] > 7 )
                v73 = S2[0];
              v74 = v40[6];
              if ( v71 >= N[0] )
                v74 = N[0];
              v75 = wmemcmp(v73, v70, v74);
              if ( v75 )
              {
                if ( v75 < 0 )
                  goto LABEL_106;
              }
              else if ( v72 < v71 )
              {
                goto LABEL_106;
              }
            }
            v76 = (_WORD *)v40[10];
          }
          *((_QWORD *)v76 + 2) += v109[2];
          *((_QWORD *)v76 + 3) += v109[3];
          *((_QWORD *)v76 + 4) += v109[4];
          *((_QWORD *)v76 + 5) += v109[5];
          *((_QWORD *)v76 + 6) += v109[6];
          *((_QWORD *)v76 + 7) += v109[7];
          *((_QWORD *)v76 + 8) += v109[8];
          *((_QWORD *)v76 + 9) += v109[9];
          *((_QWORD *)v76 + 10) += v109[10];
          *((_QWORD *)v76 + 12) += v110;
          *((_BYTE *)v76 + 106) |= v22;
          v77 = v111;
          v76[52] |= v111;
          v94 |= v77;
LABEL_103:
          v7 = tls_index;
        }
        v9 = v95 + 1;
      }
      if ( dword_1800C8FA0 > *(_DWORD *)(v102 + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v7)) )
      {
        Init_thread_header(&dword_1800C8FA0);
        if ( dword_1800C8FA0 == -1 )
        {
          atexit(Srum::Instance_::_2_::_dynamic_atexit_destructor_for__PSrum__);
          Init_thread_footer(&dword_1800C8FA0);
        }
      }
      v87 = (Srum *)qword_1800C8D60;
      if ( !qword_1800C8D60 )
      {
        v92 = (Srum *)operator new(0x18u);
        v87 = v92;
        v102 = (__int64)v92;
        if ( v92 )
        {
          if ( (int)Srum::LoadDll(v92) < 0 )
          {
            *(_QWORD *)v87 = std::_String_val<std::_Simple_types<char>>::_Bxty::_Switch_to_buf;
            *((_QWORD *)v87 + 1) = &SruQueryStatsDefault;
          }
        }
        else
        {
          v87 = 0;
        }
        v93 = qword_1800C8D60;
        qword_1800C8D60 = (__int64)v87;
        if ( v93 )
        {
          std::default_delete<Srum>::operator()();
          v87 = (Srum *)qword_1800C8D60;
        }
      }
      (*(void (__fastcall **)(__int64))v87)(v96);
      v5 = v94;
    }
  }
  v88 = (volatile signed __int32 *)*((_QWORD *)&v119 + 1);
  if ( *((_QWORD *)&v119 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v119 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v88)(v88);
      if ( _InterlockedExchangeAdd(v88 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v88 + 8LL))(v88);
    }
  }
  if ( N[1] > 7 )
    std::_Deallocate<16>(S2[0], 2 * N[1] + 2);
  return v5;
}

```

## disassembly

```asm
0x180007920  mov     r11, rsp
0x180007923  push    rbx
0x180007924  push    rsi
0x180007925  push    rdi
0x180007926  push    r12
0x180007928  push    r13
0x18000792a  push    r14
0x18000792c  push    r15
0x18000792e  sub     rsp, 240h
0x180007935  movaps  xmmword ptr [r11-48h], xmm6
0x18000793a  movaps  xmmword ptr [r11-58h], xmm7
0x18000793f  mov     rax, cs:__security_cookie
0x180007946  xor     rax, rsp
0x180007949  mov     [rsp+278h+var_60], rax
0x180007951  mov     [rsp+278h+var_210], r9
0x180007956  mov     rax, r8
0x180007959  mov     [rsp+278h+var_218], rax
0x18000795e  mov     [r11-1F8h], rcx
0x180007965  mov     [r11-1F0h], rdx
0x18000796c  mov     [rsp+278h+var_1E8], rax
0x180007974  mov     [rsp+278h+var_1E0], r9
0x18000797c  xor     r13d, r13d
0x18000797f  mov     edi, r13d
0x180007982  mov     [rsp+278h+var_248], r13d
0x180007987  xorps   xmm0, xmm0
0x18000798a  movups  xmmword ptr [rsp+278h+S2], xmm0
0x180007992  xorps   xmm1, xmm1
0x180007995  movdqu  xmmword ptr [rsp+278h+N], xmm1
0x18000799e  lea     rcx, [r11-118h]
0x1800079a5  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800079aa  movdqu  [rsp+278h+var_F8], xmm1
0x1800079b3  mov     [rsp+278h+var_240], r13
0x1800079b8  movups  xmmword ptr [rsp+278h+SystemTime.wYear], xmm0
0x1800079c0  movups  xmmword ptr [rsp+278h+var_B8.wYear], xmm1
0x1800079c8  lea     rdx, [rsp+278h+SystemTime]; lpSystemTime
0x1800079d0  lea     rcx, [rsp+278h+FileTime]; lpFileTime
0x1800079d8  call    cs:__imp_FileTimeToSystemTime
0x1800079de  test    eax, eax
0x1800079e0  jz      loc_1800086E1
0x1800079e6  lea     rdx, [rsp+278h+var_B8]; lpSystemTime
0x1800079ee  lea     rcx, [rsp+278h+var_1F0]; lpFileTime
0x1800079f6  call    cs:__imp_FileTimeToSystemTime
0x1800079fc  test    eax, eax
0x1800079fe  jz      loc_1800086E1
0x180007a04  mov     [rsp+278h+var_240], r13
0x180007a09  mov     r12d, 4
0x180007a0f  mov     [rsp+278h+var_200], r12
0x180007a14  mov     esi, cs:_tls_index
0x180007a1a  mov     rax, gs:58h
0x180007a23  mov     rcx, [rax+rsi*8]
0x180007a27  mov     eax, [r12+rcx]
0x180007a2b  cmp     cs:dword_1800C8FA0, eax
0x180007a31  jg      loc_180008317
0x180007a37  mov     rbx, cs:qword_1800C8D60
0x180007a3e  test    rbx, rbx
0x180007a41  jz      loc_180008383
0x180007a47  lea     rax, [rsp+278h+var_240]
0x180007a4c  mov     [rsp+278h+var_258], rax
0x180007a51  mov     r14d, 2
0x180007a57  mov     r9d, r14d
0x180007a5a  lea     r8, [rsp+278h+var_B8]
0x180007a62  lea     rdx, [rsp+278h+SystemTime]
0x180007a6a  mov     ecx, 7
0x180007a6f  mov     rax, [rbx+8]
0x180007a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a78  test    eax, eax
0x180007a7a  jnz     loc_1800086E1
0x180007a80  cmp     [rsp+278h+var_240], 0
0x180007a86  jz      loc_1800086E1
0x180007a8c  mov     [rsp+278h+var_208], r12
0x180007a91  mov     ecx, r13d
0x180007a94  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180007a9b  movdqa  xmm7, cs:__xmm@00000000000000070000000000000000
0x180007aa3  mov     [rsp+278h+var_244], ecx
0x180007aa7  mov     rax, [rsp+278h+var_240]
0x180007aac  cmp     ecx, [rax]
0x180007aae  jnb     loc_180008260
0x180007ab4  mov     edi, ecx
0x180007ab6  shl     rdi, 6
0x180007aba  mov     rbx, [rax+8]
0x180007abe  add     rbx, rdi
0x180007ac1  cmp     word ptr [rbx+30h], 1
0x180007ac6  jz      short loc_180007ACD
0x180007ac8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007acd  mov     rax, [rbx+38h]
0x180007ad1  cmp     word ptr [rax], 0
0x180007ad5  jz      short loc_180007ADC
0x180007ad7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007adc  mov     rax, [rbx+38h]
0x180007ae0  cmp     dword ptr [rax+4], 3
0x180007ae4  jz      short loc_180007AEB
0x180007ae6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007aeb  mov     rax, [rbx+38h]
0x180007aef  cmp     qword ptr [rax+8], 10h
0x180007af4  jnb     short loc_180007AFB
0x180007af6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007afb  mov     rdx, [rbx+38h]
0x180007aff  mov     rcx, [rdx+10h]
0x180007b03  movzx   eax, byte ptr [rcx]
0x180007b06  mov     [rsp+278h+var_15E], al
0x180007b0d  movzx   eax, word ptr [rcx+0Eh]
0x180007b11  mov     [rsp+278h+var_160], ax
0x180007b19  movzx   r10d, word ptr [rcx+8]
0x180007b1e  movzx   r8d, byte ptr [rcx+1]
0x180007b23  and     r8d, 8
0x180007b27  or      r8, 10h
0x180007b2b  add     r8, rcx
0x180007b2e  mov     r11d, [rdx+8]
0x180007b32  mov     r9d, 8
0x180007b38  movzx   edx, r14w
0x180007b3c  nop     dword ptr [rax+00h]
0x180007b40  cmp     dx, 0Dh
0x180007b44  jge     short loc_180007B81
0x180007b46  movzx   eax, dl
0x180007b49  bt      r10d, eax
0x180007b4d  jb      short loc_180007B63
0x180007b4f  mov     rcx, r13
0x180007b52  movsx   rax, dx
0x180007b56  mov     [rsp+rax*8+278h+var_1C8], rcx
0x180007b5e  inc     dx
0x180007b61  jmp     short loc_180007B40
0x180007b63  mov     ecx, r9d
0x180007b66  add     rcx, 8
0x180007b6a  cmp     rcx, r11
0x180007b6d  ja      short loc_180007B7C
0x180007b6f  mov     rcx, [r8]
0x180007b72  add     r8, 8
0x180007b76  add     r9d, 8
0x180007b7a  jmp     short loc_180007B52
0x180007b7c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007b81  mov     [rsp+278h+var_1C8], r13
0x180007b89  mov     [rsp+278h+var_1C0], r13
0x180007b91  mov     [rsp+278h+var_170], r13
0x180007b99  movzx   r12d, [rsp+278h+var_15E]
0x180007ba2  test    r12b, 8
0x180007ba6  jz      loc_18000822B
0x180007bac  mov     r14, [rsp+278h+var_218]
0x180007bb1  cmp     [rsp+278h+var_168], 0
0x180007bba  cmovnz  r14, [rsp+278h+var_210]
0x180007bc0  mov     qword ptr [rsp+278h+var_228], r14
0x180007bc5  mov     rax, [rsp+278h+var_240]
0x180007bca  add     rdi, [rax+8]
0x180007bce  xorps   xmm0, xmm0
0x180007bd1  movups  [rsp+278h+var_E8], xmm0
0x180007bd9  xorps   xmm1, xmm1
0x180007bdc  movdqu  [rsp+278h+var_D8], xmm1
0x180007be5  lea     rcx, [rsp+278h+var_E8]
0x180007bed  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180007bf2  nop
0x180007bf3  movdqu  [rsp+278h+var_C8], xmm0
0x180007bfc  mov     ecx, esi
0x180007bfe  mov     rax, gs:58h
0x180007c07  mov     rcx, [rax+rcx*8]
0x180007c0b  mov     rax, [rsp+278h+var_208]
0x180007c10  mov     eax, [rax+rcx]
0x180007c13  cmp     cs:dword_1800C8F30, eax
0x180007c19  jg      loc_1800084DA
0x180007c1f  mov     rbx, [rdi+28h]
0x180007c23  mov     [rsp+278h+var_238], r13
0x180007c28  mov     rcx, rbx; Sid
0x180007c2b  call    cs:__imp_RtlLengthSid
0x180007c31  mov     esi, eax
0x180007c33  mov     edx, eax; uBytes
0x180007c35  mov     ecx, 40h ; '@'; uFlags
0x180007c3a  call    cs:__imp_LocalAlloc
0x180007c40  mov     [rsp+278h+var_238], rax
0x180007c45  test    rax, rax
0x180007c48  jz      loc_18000842F
0x180007c4e  mov     r8, rbx; SourceSid
0x180007c51  mov     rdx, rax; DestinationSid
0x180007c54  mov     ecx, esi; DestinationSidLength
0x180007c56  call    cs:__imp_RtlCopySid
0x180007c5c  lea     r8, [rsp+278h+var_238]
0x180007c61  lea     rdx, [rsp+278h+var_128]
0x180007c69  lea     rcx, qword_1800C8F40; _Mtx_t
0x180007c70  call    _anonymous_namespace___SrumDataCache__GetKeyData
0x180007c75  mov     rcx, [rax]
0x180007c78  mov     rdx, [rax+8]
0x180007c7c  mov     [rax], r13
0x180007c7f  mov     [rax+8], r13
0x180007c83  mov     qword ptr [rsp+278h+var_C8], rcx
0x180007c8b  mov     rbx, qword ptr [rsp+278h+var_C8+8]
0x180007c93  mov     qword ptr [rsp+278h+var_C8+8], rdx
0x180007c9b  test    rbx, rbx
0x180007c9e  jz      short loc_180007CB1
0x180007ca0  mov     eax, r15d
0x180007ca3  lock xadd [rbx+8], eax
0x180007ca8  cmp     eax, 1
0x180007cab  jz      loc_180008516
0x180007cb1  mov     rbx, [rsp+278h+var_120]
0x180007cb9  test    rbx, rbx
0x180007cbc  jz      short loc_180007CCF
0x180007cbe  mov     eax, r15d
0x180007cc1  lock xadd [rbx+8], eax
0x180007cc6  cmp     eax, 1
0x180007cc9  jz      loc_180008549
0x180007ccf  mov     ecx, [rdi+10h]
0x180007cd2  test    ecx, ecx
0x180007cd4  jnz     loc_18000857C
0x180007cda  mov     rdx, [rdi+18h]
0x180007cde  mov     r8, r15
0x180007ce1  inc     r8
0x180007ce4  cmp     word ptr [rdx+r8*2], 0
0x180007cea  jnz     short loc_180007CE1
0x180007cec  lea     rcx, [rsp+278h+var_E8]
0x180007cf4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180007cf9  nop
0x180007cfa  mov     rdx, [rsp+278h+N+8]
0x180007d02  cmp     rdx, 7
0x180007d06  ja      loc_1800085C3
0x180007d0c  mov     rax, qword ptr [rsp+278h+var_E8]
0x180007d14  mov     [rsp+278h+S2], rax
0x180007d1c  mov     rax, qword ptr [rsp+278h+var_E8+8]
0x180007d24  mov     [rsp+278h+S2+8], rax
0x180007d2c  mov     rax, qword ptr [rsp+278h+var_D8]
0x180007d34  mov     [rsp+278h+N], rax
0x180007d3c  mov     rax, qword ptr [rsp+278h+var_D8+8]
0x180007d44  mov     [rsp+278h+N+8], rax
0x180007d4c  movdqu  [rsp+278h+var_D8], xmm7
0x180007d55  mov     word ptr [rsp+278h+var_E8], r13w
0x180007d5e  mov     rax, qword ptr [rsp+278h+var_C8]
0x180007d66  mov     rcx, qword ptr [rsp+278h+var_C8+8]
0x180007d6e  xorps   xmm0, xmm0
0x180007d71  movdqu  [rsp+278h+var_C8], xmm0
0x180007d7a  mov     qword ptr [rsp+278h+var_F8], rax
0x180007d82  mov     rbx, qword ptr [rsp+278h+var_F8+8]
0x180007d8a  mov     qword ptr [rsp+278h+var_F8+8], rcx
0x180007d92  test    rbx, rbx
0x180007d95  jz      short loc_180007DA8
0x180007d97  mov     eax, r15d
0x180007d9a  lock xadd [rbx+8], eax
0x180007d9f  cmp     eax, 1
0x180007da2  jz      loc_1800085DD
0x180007da8  mov     rbx, qword ptr [rsp+278h+var_C8+8]
0x180007db0  test    rbx, rbx
0x180007db3  jz      short loc_180007DC6
0x180007db5  mov     eax, r15d
0x180007db8  lock xadd [rbx+8], eax
0x180007dbd  cmp     eax, 1
0x180007dc0  jz      loc_180008610
0x180007dc6  mov     rdx, qword ptr [rsp+278h+var_D8+8]
0x180007dce  cmp     rdx, 7
0x180007dd2  ja      loc_180008643
0x180007dd8  mov     rbx, [r14]
0x180007ddb  mov     rdi, [rbx+8]
0x180007ddf  xor     eax, eax
0x180007de1  mov     dword ptr [rsp+278h+var_E8+0Ch], eax
0x180007de8  cmp     [rdi+19h], al
0x180007deb  jnz     loc_180007EF4
0x180007df1  mov     rsi, qword ptr [rsp+278h+var_F8]
0x180007df9  add     rsi, 20h ; ' '
0x180007dfd  mov     r14, [rdi+40h]
0x180007e01  add     r14, 20h ; ' '
0x180007e05  mov     r12, [rsi+10h]
0x180007e09  mov     rdx, rsi
0x180007e0c  cmp     qword ptr [rsi+18h], 7
0x180007e11  jbe     short loc_180007E16
0x180007e13  mov     rdx, [rsi]; S2
0x180007e16  mov     r15, [r14+10h]
0x180007e1a  mov     rcx, r14
0x180007e1d  cmp     qword ptr [r14+18h], 7
0x180007e22  jbe     short loc_180007E27
0x180007e24  mov     rcx, [r14]; S1
0x180007e27  mov     r8, r12
0x180007e2a  cmp     r12, r15
0x180007e2d  cmovnb  r8, r15; N
0x180007e31  call    wmemcmp
0x180007e36  test    eax, eax
0x180007e38  jz      loc_180008246
0x180007e3e  js      loc_18000824F
0x180007e44  mov     rax, [rsi+10h]
0x180007e48  cmp     qword ptr [rsi+18h], 7
0x180007e4d  jbe     short loc_180007E52
0x180007e4f  mov     rsi, [rsi]
0x180007e52  mov     r8, [r14+10h]; N
0x180007e56  cmp     qword ptr [r14+18h], 7
0x180007e5b  jbe     short loc_180007E60
0x180007e5d  mov     r14, [r14]
0x180007e60  cmp     r8, rax
0x180007e63  jnz     short loc_180007ECA
0x180007e65  test    r8, r8
0x180007e68  jz      short loc_180007E79
0x180007e6a  mov     rdx, rsi; S2
0x180007e6d  mov     rcx, r14; S1
0x180007e70  call    wmemcmp
0x180007e75  test    eax, eax
0x180007e77  jnz     short loc_180007ECA
0x180007e79  lea     rcx, [rdi+20h]
0x180007e7d  mov     rsi, [rsp+278h+N]
0x180007e85  lea     rdx, [rsp+278h+S2]
0x180007e8d  cmp     [rsp+278h+N+8], 7
0x180007e96  cmova   rdx, [rsp+278h+S2]; S2
0x180007e9f  mov     r14, [rcx+10h]
0x180007ea3  cmp     qword ptr [rcx+18h], 7
0x180007ea8  jbe     short loc_180007EAD
0x180007eaa  mov     rcx, [rcx]; S1
0x180007ead  mov     r8, rsi
0x180007eb0  cmp     rsi, r14
0x180007eb3  cmovnb  r8, r14; N
0x180007eb7  call    wmemcmp
  ... truncated ...
```
