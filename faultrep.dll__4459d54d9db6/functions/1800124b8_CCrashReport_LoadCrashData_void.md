# CCrashReport::LoadCrashData(void)

- ea: `0x1800124b8`
- end: `0x180012ee7`
- name: `?LoadCrashData@CCrashReport@@AEAAJXZ`
- size: `2607`
- prototype: `__int64 __fastcall(CCrashReport *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180014c34`

## callees

- `0x180003474`
- `0x180009ed8`
- `0x180009f00`
- `0x180009f40`
- `0x1800124b8`
- `0x180016b18`
- `0x180016b78`
- `0x18003be40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180012993`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180012993`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012dcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012dcd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180012910`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180012910`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800129e1`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800129e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001293b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001293b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012703`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012723`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012742`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001275b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001285f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012928`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012703`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012723`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012742`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001275b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001285f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012928`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x180012b72`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x180012d82`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x180012b72`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x180012d82`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180012847`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180012847`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180012540`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180012540`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180012a2e`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180012a2e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180012e3b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180012e8f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180012e3b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180012e8f`
- `api-ms-win-core-processsnapshot-l1-1-0!PssDuplicateSnapshot` at `0x180012df2`
- `api-ms-win-core-processsnapshot-l1-1-0!PssDuplicateSnapshot` at `0x180012df2`

## pseudocode

```c
__int64 __fastcall CCrashReport::LoadCrashData(CCrashReport *this)
{
  __m128i *v2; // rax
  __m128i *v3; // r15
  signed int LastError; // eax
  signed int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __m128i v8; // xmm1
  __m128i v9; // xmm10
  __m128i v10; // xmm11
  __m128i v11; // xmm12
  __m128i v12; // xmm13
  __m128i v13; // xmm14
  __m128i v14; // xmm15
  __m128i v15; // xmm9
  __m128i v16; // xmm6
  __m128i v17; // xmm7
  __m128i v18; // xmm8
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  int v21; // eax
  int v22; // ecx
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  _QWORD *v27; // rcx
  HANDLE v28; // rax
  void *v29; // rcx
  signed int v30; // eax
  signed int i; // ebx
  HANDLE v32; // rax
  void *v33; // rcx
  signed int v34; // eax
  __int64 v35; // r8
  bool v36; // sf
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  void *v39; // rcx
  void *v40; // xmm0_8
  signed int v41; // eax
  _OWORD *v42; // rcx
  __int64 v43; // rax
  __m128i *v44; // rcx
  DWORD v45; // eax
  __m128i *v46; // rax
  __int64 v47; // rdx
  int ExceptionInformationFromExceptionPointer; // eax
  void *v49; // rcx
  DWORD v50; // eax
  HANDLE CurrentProcess; // rax
  unsigned int v52; // eax
  const void *v53; // rcx
  __m128i v55; // [rsp+30h] [rbp-238h]
  __m128i v56; // [rsp+40h] [rbp-228h]
  __m128i v57; // [rsp+50h] [rbp-218h]
  __m128i v58; // [rsp+60h] [rbp-208h]
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+70h] [rbp-1F8h] BYREF
  __int64 v60; // [rsp+190h] [rbp-D8h]
  int v61; // [rsp+270h] [rbp+8h]
  int v62; // [rsp+278h] [rbp+10h]

  memset(&Buffer, 0, sizeof(Buffer));
  v2 = (__m128i *)MapViewOfFile(*((HANDLE *)this + 94), 6u, 0, 0, 0);
  v3 = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 91;
LABEL_7:
      WPP_SF_d(v6[2], v7, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, (unsigned int)v5);
      goto LABEL_126;
    }
    goto LABEL_126;
  }
  v8 = *v2;
  v9 = v2[1];
  v10 = v2[2];
  v11 = v2[3];
  v12 = v2[4];
  v13 = v2[5];
  v14 = v2[6];
  v55 = v2[7];
  v56 = v2[8];
  v57 = v2[9];
  v15 = v2[10];
  v16 = v2[11];
  v17 = v2[12];
  v18 = v2[13];
  v58 = v2[14];
  v60 = v2[15].m128i_i64[0];
  if ( _mm_cvtsi128_si32(v8) != 248 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v20 = 93;
LABEL_12:
    WPP_SF_(v19[2], v20, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
LABEL_13:
    v5 = -2147024883;
    goto LABEL_126;
  }
  v21 = _mm_cvtsi128_si32(_mm_srli_si128(v8, 4));
  v61 = v21;
  if ( !v21 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v20 = 94;
    goto LABEL_12;
  }
  v22 = _mm_cvtsi128_si32(_mm_srli_si128(v8, 8));
  v62 = v22;
  if ( !v22 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v20 = 95;
    goto LABEL_12;
  }
  *((_DWORD *)this + 184) = v21;
  *((_DWORD *)this + 185) = v22;
  v23 = (void *)*((_QWORD *)this + 95);
  *((_QWORD *)this + 95) = _mm_srli_si128(v17, 8).m128i_u64[0];
  if ( (unsigned __int64)v23 + 1 > 1 )
    CloseHandle(v23);
  v24 = (void *)*((_QWORD *)this + 96);
  *((_QWORD *)this + 96) = v18.m128i_i64[0];
  if ( (unsigned __int64)v24 + 1 > 1 )
    CloseHandle(v24);
  v25 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = _mm_srli_si128(v16, 8).m128i_u64[0];
  if ( (unsigned __int64)v25 + 1 > 1 )
    CloseHandle(v25);
  v26 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = v17.m128i_i64[0];
  if ( (unsigned __int64)v26 + 1 > 1 )
    CloseHandle(v26);
  v27 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        96,
        WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
        *((unsigned int *)this + 184),
        *((_DWORD *)this + 184));
      v27 = WPP_GLOBAL_Control;
    }
    if ( v27 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v27 + 28) & 8) != 0 )
      {
        WPP_SF_Dd(
          v27[2],
          97,
          WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
          *((unsigned int *)this + 185),
          *((_DWORD *)this + 185));
        v27 = WPP_GLOBAL_Control;
      }
      if ( v27 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v27 + 28) & 8) != 0 )
        {
          WPP_SF_q(v27[2], 98, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, *((_QWORD *)this + 6));
          v27 = WPP_GLOBAL_Control;
        }
        if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 8) != 0 )
          WPP_SF_q(v27[2], 99, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, *((_QWORD *)this + 7));
      }
    }
  }
  if ( *((_QWORD *)this + 6) == -1 || *((_QWORD *)this + 6) == 0 )
  {
    v28 = OpenProcess(0x1FFFFFu, 0, *((_DWORD *)this + 184));
    v29 = (void *)*((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = v28;
    if ( (unsigned __int64)v29 + 1 > 1 )
      CloseHandle(v29);
    if ( *((_QWORD *)this + 6) == -1 || *((_QWORD *)this + 6) == 0 )
    {
      v30 = GetLastError();
      v5 = v30;
      if ( v30 > 0 )
        v5 = (unsigned __int16)v30 | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          100,
          WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
          *((unsigned int *)this + 184),
          v5);
      goto LABEL_126;
    }
  }
  for ( i = 0; (*((_QWORD *)this + 7) == -1 || *((_QWORD *)this + 7) == 0) && (unsigned int)i < 4; ++i )
  {
    v32 = OpenThread(*((_DWORD *)qword_180051A20 + i), 0, *((_DWORD *)this + 185));
    v33 = (void *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = v32;
    if ( (unsigned __int64)v33 + 1 > 1 )
      CloseHandle(v33);
    if ( *((_QWORD *)this + 7) == -1 || *((_QWORD *)this + 7) == 0 )
    {
      v34 = GetLastError();
      v36 = v34 < 0;
      if ( v34 > 0 )
      {
        v34 = (unsigned __int16)v34 | 0x80070000;
        v36 = v34 < 0;
      }
      if ( !v36 )
        v34 = -2147467259;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dDd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          qword_180051A20,
          v35,
          *((unsigned int *)this + 185),
          *((_DWORD *)qword_180051A20 + i),
          v34);
    }
  }
  if ( v61 != GetProcessId(*((HANDLE *)this + 6)) )
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v38 = 102;
LABEL_71:
    WPP_SF_(v37[2], v38, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
LABEL_72:
    v5 = -2147418113;
    goto LABEL_126;
  }
  v39 = (void *)*((_QWORD *)this + 7);
  if ( (unsigned __int64)v39 + 1 > 1 && v62 != GetThreadId(v39) )
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v38 = 103;
    goto LABEL_71;
  }
  v40 = (void *)_mm_srli_si128(v15, 8).m128i_u64[0];
  if ( v40 != (void *)1 )
  {
    if ( v40 )
    {
      ExceptionInformationFromExceptionPointer = UtilReadExceptionInformationFromExceptionPointer(
                                                   *((HANDLE *)this + 93),
                                                   v40,
                                                   (struct _EXCEPTION_RECORD *)((char *)this + 824),
                                                   (struct _CONTEXT *)((char *)this + 976));
      if ( ExceptionInformationFromExceptionPointer < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            108,
            WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids,
            (unsigned int)ExceptionInformationFromExceptionPointer);
        memset_0((char *)this + 824, 0, 0x98u);
        memset_0((char *)this + 976, 0, 0x4D0u);
      }
    }
    else
    {
      *(__m128i *)((char *)this + 824) = v9;
      *(__m128i *)((char *)this + 840) = v10;
      *(__m128i *)((char *)this + 856) = v11;
      *(__m128i *)((char *)this + 872) = v12;
      *(__m128i *)((char *)this + 888) = v13;
      *(__m128i *)((char *)this + 904) = v14;
      *(__m128i *)((char *)this + 920) = v55;
      *(__m128i *)((char *)this + 936) = v56;
      *(__m128i *)((char *)this + 952) = v57;
      *((_QWORD *)this + 121) = v15.m128i_i64[0];
      v49 = (void *)*((_QWORD *)this + 7);
      if ( (unsigned __int64)v49 + 1 > 1 )
      {
        *((_DWORD *)this + 256) = 1048607;
        if ( !GetThreadContext(v49, (LPCONTEXT)((char *)this + 976))
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v50 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, v50);
        }
      }
    }
LABEL_117:
    if ( v58.m128i_i64[0] )
    {
      CurrentProcess = GetCurrentProcess();
      v52 = PssDuplicateSnapshot(*((_QWORD *)this + 93), v58.m128i_i64[0], CurrentProcess, (char *)this + 4936, 1);
      if ( v52 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, v52);
        *((_QWORD *)this + 617) = 0;
      }
    }
    v53 = (const void *)*((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = v3;
    if ( v53 )
      UnmapViewOfFile(v53);
    v3 = 0;
    v5 = 0;
    goto LABEL_126;
  }
  if ( VirtualQuery(v3, &Buffer, 0x30u) )
  {
    if ( Buffer.RegionSize < 0x670 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
      v5 = -2147483637;
      goto LABEL_126;
    }
    v42 = (_OWORD *)((char *)this + 824);
    if ( v3[15].m128i_i64[1] == 1 )
    {
      *v42 = *(__m128i *)((char *)&v3[16] + 8);
      *(__m128i *)((char *)this + 840) = *(__m128i *)((char *)v3 + 280);
      *(__m128i *)((char *)this + 856) = *(__m128i *)((char *)v3 + 296);
      *(__m128i *)((char *)this + 872) = *(__m128i *)((char *)v3 + 312);
      *(__m128i *)((char *)this + 888) = *(__m128i *)((char *)v3 + 328);
      *(__m128i *)((char *)this + 904) = *(__m128i *)((char *)v3 + 344);
      *(__m128i *)((char *)this + 920) = *(__m128i *)((char *)v3 + 360);
      *(__m128i *)((char *)this + 936) = *(__m128i *)((char *)v3 + 376);
      *(__m128i *)((char *)this + 952) = *(__m128i *)((char *)v3 + 392);
      *((_QWORD *)this + 121) = v3[25].m128i_i64[1];
    }
    else
    {
      memset_0(v42, 0, 0x98u);
    }
    v43 = v3[16].m128i_i64[0];
    v44 = (__m128i *)((char *)this + 976);
    if ( v43 == 2 )
    {
      *((_DWORD *)this + 256) = 1048607;
      if ( !GetThreadContext(*((HANDLE *)this + 7), (LPCONTEXT)((char *)this + 976))
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v45 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, v45);
      }
    }
    else if ( v43 == 1 )
    {
      v46 = v3 + 26;
      v47 = 9;
      do
      {
        *v44 = *v46;
        v44[1] = v46[1];
        v44[2] = v46[2];
        v44[3] = v46[3];
        v44[4] = v46[4];
        v44[5] = v46[5];
        v44[6] = v46[6];
        v44[7] = v46[7];
        v44 += 8;
        v46 += 8;
        --v47;
      }
      while ( v47 );
      *v44 = *v46;
      v44[1] = v46[1];
      v44[2] = v46[2];
      v44[3] = v46[3];
      v44[4] = v46[4];
    }
    else
    {
      memset_0(v44, 0, 0x4D0u);
    }
    goto LABEL_117;
  }
  v41 = GetLastError();
  v5 = v41;
  if ( v41 > 0 )
    v5 = (unsigned __int16)v41 | 0x80070000;
  if ( v5 >= 0 )
    v5 = -2147467259;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 104;
    goto LABEL_7;
  }
LABEL_126:
  if ( v3 )
    UnmapViewOfFile(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800124b8  mov     rax, rsp
0x1800124bb  mov     [rax+20h], rbx
0x1800124bf  push    rsi
0x1800124c0  push    rdi
0x1800124c1  push    r12
0x1800124c3  push    r13
0x1800124c5  push    r15
0x1800124c7  sub     rsp, 240h
0x1800124ce  movaps  xmmword ptr [rax-38h], xmm6
0x1800124d2  movaps  xmmword ptr [rax-48h], xmm7
0x1800124d6  movaps  xmmword ptr [rax-58h], xmm8
0x1800124db  movaps  xmmword ptr [rax-68h], xmm9
0x1800124e0  movaps  xmmword ptr [rax-78h], xmm10
0x1800124e5  movaps  xmmword ptr [rax-88h], xmm11
0x1800124ed  movaps  xmmword ptr [rax-98h], xmm12
0x1800124f5  movaps  xmmword ptr [rax-0A8h], xmm13
0x1800124fd  movaps  xmmword ptr [rax-0B8h], xmm14
0x180012505  movaps  xmmword ptr [rax-0C8h], xmm15
0x18001250d  mov     rdi, rcx
0x180012510  xorps   xmm0, xmm0
0x180012513  movups  xmmword ptr [rsp+268h+Buffer.BaseAddress], xmm0
0x180012518  movups  xmmword ptr [rax-1E8h], xmm0
0x18001251f  movups  xmmword ptr [rax-1D8h], xmm0
0x180012526  mov     [rsp+268h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x18001252f  xor     r9d, r9d; dwFileOffsetLow
0x180012532  xor     r8d, r8d; dwFileOffsetHigh
0x180012535  lea     edx, [r9+6]; dwDesiredAccess
0x180012539  mov     rcx, [rcx+2F0h]; hFileMappingObject
0x180012540  call    cs:__imp_MapViewOfFile
0x180012546  mov     r15, rax
0x180012549  mov     [rsp+268h+arg_10], rax
0x180012551  test    rax, rax
0x180012554  jnz     short loc_1800125A9
0x180012556  call    cs:__imp_GetLastError
0x18001255c  mov     ebx, eax
0x18001255e  test    eax, eax
0x180012560  jle     short loc_18001256B
0x180012562  movzx   ebx, ax
0x180012565  or      ebx, 80070000h
0x18001256b  lea     rsi, WPP_GLOBAL_Control
0x180012572  mov     rcx, cs:WPP_GLOBAL_Control
0x180012579  cmp     rcx, rsi
0x18001257c  jz      loc_180012E87
0x180012582  test    byte ptr [rcx+1Ch], 1
0x180012586  jz      loc_180012E87
0x18001258c  mov     edx, 5Bh ; '['
0x180012591  mov     r9d, ebx
0x180012594  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x18001259b  mov     rcx, [rcx+10h]
0x18001259f  call    WPP_SF_d
0x1800125a4  jmp     loc_180012E87
0x1800125a9  movups  xmm1, xmmword ptr [rax]
0x1800125ac  movups  xmm10, xmmword ptr [rax+10h]
0x1800125b1  movups  xmm11, xmmword ptr [rax+20h]
0x1800125b6  movups  xmm12, xmmword ptr [rax+30h]
0x1800125bb  movups  xmm13, xmmword ptr [rax+40h]
0x1800125c0  movups  xmm14, xmmword ptr [rax+50h]
0x1800125c5  movups  xmm15, xmmword ptr [rax+60h]
0x1800125ca  movups  xmm0, xmmword ptr [rax+70h]
0x1800125ce  movups  [rsp+268h+var_238], xmm0
0x1800125d3  movups  xmm0, xmmword ptr [rax+80h]
0x1800125da  movups  [rsp+268h+var_228], xmm0
0x1800125df  movups  xmm0, xmmword ptr [rax+90h]
0x1800125e6  movups  [rsp+268h+var_218], xmm0
0x1800125eb  movups  xmm9, xmmword ptr [rax+0A0h]
0x1800125f3  movups  xmm6, xmmword ptr [rax+0B0h]
0x1800125fa  movups  xmm7, xmmword ptr [rax+0C0h]
0x180012601  movups  xmm8, xmmword ptr [rax+0D0h]
0x180012609  movups  xmm0, xmmword ptr [rax+0E0h]
0x180012610  movups  [rsp+268h+var_208], xmm0
0x180012615  mov     rax, [rax+0F0h]
0x18001261c  mov     [rsp+268h+var_D8], rax
0x180012624  movd    eax, xmm1
0x180012628  cmp     eax, 0F8h
0x18001262d  jz      short loc_180012667
0x18001262f  lea     rsi, WPP_GLOBAL_Control
0x180012636  mov     rcx, cs:WPP_GLOBAL_Control
0x18001263d  cmp     rcx, rsi
0x180012640  jz      short loc_18001265D
0x180012642  test    byte ptr [rcx+1Ch], 1
0x180012646  jz      short loc_18001265D
0x180012648  mov     edx, 5Dh ; ']'
0x18001264d  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x180012654  mov     rcx, [rcx+10h]
0x180012658  call    WPP_SF_
0x18001265d  mov     ebx, 8007000Dh
0x180012662  jmp     loc_180012E87
0x180012667  movdqa  xmm0, xmm1
0x18001266b  psrldq  xmm0, 4
0x180012670  movd    eax, xmm0
0x180012674  mov     [rsp+268h+arg_0], eax
0x18001267b  test    eax, eax
0x18001267d  jnz     short loc_18001269D
0x18001267f  lea     rsi, WPP_GLOBAL_Control
0x180012686  mov     rcx, cs:WPP_GLOBAL_Control
0x18001268d  cmp     rcx, rsi
0x180012690  jz      short loc_18001265D
0x180012692  test    byte ptr [rcx+1Ch], 1
0x180012696  jz      short loc_18001265D
0x180012698  lea     edx, [rax+5Eh]
0x18001269b  jmp     short loc_18001264D
0x18001269d  psrldq  xmm1, 8
0x1800126a2  movd    ecx, xmm1
0x1800126a6  mov     [rsp+268h+arg_8], ecx
0x1800126ad  test    ecx, ecx
0x1800126af  jnz     short loc_1800126D4
0x1800126b1  lea     rsi, WPP_GLOBAL_Control
0x1800126b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126bf  cmp     rcx, rsi
0x1800126c2  jz      short loc_18001265D
0x1800126c4  test    byte ptr [rcx+1Ch], 1
0x1800126c8  jz      short loc_18001265D
0x1800126ca  mov     edx, 5Fh ; '_'
0x1800126cf  jmp     loc_18001264D
0x1800126d4  mov     [rdi+2E0h], eax
0x1800126da  mov     [rdi+2E4h], ecx
0x1800126e0  mov     rcx, [rdi+2F8h]; hObject
0x1800126e7  movdqa  xmm0, xmm7
0x1800126eb  psrldq  xmm0, 8
0x1800126f0  movq    qword ptr [rdi+2F8h], xmm0
0x1800126f9  lea     rax, [rcx+1]
0x1800126fd  cmp     rax, 1
0x180012701  jbe     short loc_180012709
0x180012703  call    cs:__imp_CloseHandle
0x180012709  mov     rcx, [rdi+300h]; hObject
0x180012710  movsd   qword ptr [rdi+300h], xmm8
0x180012719  lea     rax, [rcx+1]
0x18001271d  cmp     rax, 1
0x180012721  jbe     short loc_180012729
0x180012723  call    cs:__imp_CloseHandle
0x180012729  mov     rcx, [rdi+30h]; hObject
0x18001272d  psrldq  xmm6, 8
0x180012732  movq    qword ptr [rdi+30h], xmm6
0x180012738  lea     rax, [rcx+1]
0x18001273c  cmp     rax, 1
0x180012740  jbe     short loc_180012748
0x180012742  call    cs:__imp_CloseHandle
0x180012748  mov     rcx, [rdi+38h]; hObject
0x18001274c  movsd   qword ptr [rdi+38h], xmm7
0x180012751  lea     rax, [rcx+1]
0x180012755  cmp     rax, 1
0x180012759  jbe     short loc_180012761
0x18001275b  call    cs:__imp_CloseHandle
0x180012761  lea     rsi, WPP_GLOBAL_Control
0x180012768  mov     rcx, cs:WPP_GLOBAL_Control
0x18001276f  cmp     rcx, rsi
0x180012772  jz      loc_180012828
0x180012778  test    byte ptr [rcx+1Ch], 8
0x18001277c  jz      short loc_1800127A6
0x18001277e  mov     r9d, [rdi+2E0h]
0x180012785  mov     edx, 60h ; '`'
0x18001278a  mov     dword ptr [rsp+268h+dwNumberOfBytesToMap], r9d
0x18001278f  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x180012796  mov     rcx, [rcx+10h]
0x18001279a  call    WPP_SF_Dd
0x18001279f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127a6  cmp     rcx, rsi
0x1800127a9  jz      short loc_180012828
0x1800127ab  test    byte ptr [rcx+1Ch], 8
0x1800127af  jz      short loc_1800127D9
0x1800127b1  mov     r9d, [rdi+2E4h]
0x1800127b8  mov     edx, 61h ; 'a'
0x1800127bd  mov     dword ptr [rsp+268h+dwNumberOfBytesToMap], r9d
0x1800127c2  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x1800127c9  mov     rcx, [rcx+10h]
0x1800127cd  call    WPP_SF_Dd
0x1800127d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127d9  cmp     rcx, rsi
0x1800127dc  jz      short loc_180012828
0x1800127de  test    byte ptr [rcx+1Ch], 8
0x1800127e2  jz      short loc_180012804
0x1800127e4  mov     edx, 62h ; 'b'
0x1800127e9  mov     r9, [rdi+30h]
0x1800127ed  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x1800127f4  mov     rcx, [rcx+10h]
0x1800127f8  call    WPP_SF_q
0x1800127fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180012804  cmp     rcx, rsi
0x180012807  jz      short loc_180012828
0x180012809  test    byte ptr [rcx+1Ch], 8
0x18001280d  jz      short loc_180012828
0x18001280f  mov     edx, 63h ; 'c'
0x180012814  mov     r9, [rdi+38h]
0x180012818  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x18001281f  mov     rcx, [rcx+10h]
0x180012823  call    WPP_SF_q
0x180012828  mov     rax, [rdi+30h]
0x18001282c  inc     rax
0x18001282f  cmp     rax, 1
0x180012833  ja      loc_1800128D2
0x180012839  mov     r8d, [rdi+2E0h]; dwProcessId
0x180012840  xor     edx, edx; bInheritHandle
0x180012842  mov     ecx, 1FFFFFh; dwDesiredAccess
0x180012847  call    cs:__imp_OpenProcess
0x18001284d  mov     rcx, [rdi+30h]; hObject
0x180012851  mov     [rdi+30h], rax
0x180012855  lea     rax, [rcx+1]
0x180012859  cmp     rax, 1
0x18001285d  jbe     short loc_180012865
0x18001285f  call    cs:__imp_CloseHandle
0x180012865  mov     rax, [rdi+30h]
0x180012869  inc     rax
0x18001286c  cmp     rax, 1
0x180012870  ja      short loc_1800128D2
0x180012872  call    cs:__imp_GetLastError
0x180012878  mov     ebx, eax
0x18001287a  test    eax, eax
0x18001287c  jle     short loc_180012887
0x18001287e  movzx   ebx, ax
0x180012881  or      ebx, 80070000h
0x180012887  mov     r13d, 80004005h
0x18001288d  test    ebx, ebx
0x18001288f  cmovns  ebx, r13d
0x180012893  mov     rcx, cs:WPP_GLOBAL_Control
0x18001289a  cmp     rcx, rsi
0x18001289d  jz      loc_180012E87
0x1800128a3  test    byte ptr [rcx+1Ch], 1
0x1800128a7  jz      loc_180012E87
0x1800128ad  mov     edx, 64h ; 'd'
0x1800128b2  mov     dword ptr [rsp+268h+dwNumberOfBytesToMap], ebx
0x1800128b6  mov     r9d, [rdi+2E0h]
0x1800128bd  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x1800128c4  mov     rcx, [rcx+10h]
0x1800128c8  call    WPP_SF_Dd
0x1800128cd  jmp     loc_180012E87
0x1800128d2  xor     ebx, ebx
0x1800128d4  mov     r12d, 80070000h
0x1800128da  mov     r13d, 80004005h
0x1800128e0  mov     rax, [rdi+38h]
0x1800128e4  inc     rax
0x1800128e7  cmp     rax, 1
0x1800128eb  ja      loc_18001298F
0x1800128f1  cmp     ebx, 4
0x1800128f4  jnb     loc_18001298F
0x1800128fa  movsxd  rax, ebx
0x1800128fd  lea     rcx, qword_180051A20
0x180012904  mov     r8d, [rdi+2E4h]; dwThreadId
0x18001290b  xor     edx, edx; bInheritHandle
0x18001290d  mov     ecx, [rcx+rax*4]; dwDesiredAccess
0x180012910  call    cs:__imp_OpenThread
0x180012916  mov     rcx, [rdi+38h]; hObject
0x18001291a  mov     [rdi+38h], rax
0x18001291e  lea     rax, [rcx+1]
0x180012922  cmp     rax, 1
0x180012926  jbe     short loc_18001292E
0x180012928  call    cs:__imp_CloseHandle
0x18001292e  mov     rax, [rdi+38h]
0x180012932  inc     rax
0x180012935  cmp     rax, 1
0x180012939  ja      short loc_180012988
0x18001293b  call    cs:__imp_GetLastError
0x180012941  test    eax, eax
0x180012943  jle     short loc_18001294D
0x180012945  movzx   eax, ax
0x180012948  or      eax, r12d
0x18001294b  test    eax, eax
0x18001294d  cmovns  eax, r13d
0x180012951  mov     rcx, cs:WPP_GLOBAL_Control
0x180012958  cmp     rcx, rsi
0x18001295b  jz      short loc_180012988
0x18001295d  test    byte ptr [rcx+1Ch], 2
0x180012961  jz      short loc_180012988
0x180012963  mov     [rsp+268h+var_240], eax
0x180012967  movsxd  rax, ebx
0x18001296a  lea     rdx, qword_180051A20
0x180012971  mov     eax, [rdx+rax*4]
0x180012974  mov     dword ptr [rsp+268h+dwNumberOfBytesToMap], eax
0x180012978  mov     r9d, [rdi+2E4h]
0x18001297f  mov     rcx, [rcx+10h]
0x180012983  call    WPP_SF_dDd
0x180012988  inc     ebx
0x18001298a  jmp     loc_1800128E0
0x18001298f  mov     rcx, [rdi+30h]; Process
0x180012993  call    cs:__imp_GetProcessId
0x180012999  cmp     [rsp+268h+arg_0], eax
0x1800129a0  jz      short loc_1800129D3
0x1800129a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129a9  cmp     rcx, rsi
0x1800129ac  jz      short loc_1800129C9
0x1800129ae  test    byte ptr [rcx+1Ch], 1
0x1800129b2  jz      short loc_1800129C9
0x1800129b4  mov     edx, 66h ; 'f'
0x1800129b9  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x1800129c0  mov     rcx, [rcx+10h]
0x1800129c4  call    WPP_SF_
0x1800129c9  mov     ebx, 8000FFFFh
0x1800129ce  jmp     loc_180012E87
0x1800129d3  mov     rcx, [rdi+38h]; Thread
0x1800129d7  lea     rax, [rcx+1]
0x1800129db  cmp     rax, 1
0x1800129df  jbe     short loc_180012A09
0x1800129e1  call    cs:__imp_GetThreadId
0x1800129e7  cmp     [rsp+268h+arg_8], eax
0x1800129ee  jz      short loc_180012A09
0x1800129f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129f7  cmp     rcx, rsi
0x1800129fa  jz      short loc_1800129C9
0x1800129fc  test    byte ptr [rcx+1Ch], 1
0x180012a00  jz      short loc_1800129C9
0x180012a02  mov     edx, 67h ; 'g'
  ... truncated ...
```
