# NlpBuildCacheEntry

- ea: `0x180011370`
- end: `0x180011cff`
- name: `NlpBuildCacheEntry`
- size: `2447`
- prototype: `__int64 __usercall@<rax>(struct _UNICODE_STRING *@<rcx>, void *, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001a470`
- `0x18004339c`

## callees

- `0x180011370`
- `0x18002e9fc`
- `0x18002ee7c`
- `0x18002f014`
- `0x180030844`
- `0x180042040`
- `0x180042dac`
- `0x1800450b4`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x18001183e`
- `ntdll!NtQuerySystemTime` at `0x18001183e`
- `ntdll!RtlLengthSid` at `0x1800116f5`
- `ntdll!RtlLengthSid` at `0x1800117e8`
- `ntdll!RtlLengthSid` at `0x180011afc`
- `ntdll!RtlLengthSid` at `0x180011b53`
- `ntdll!RtlLengthSid` at `0x1800116f5`
- `ntdll!RtlLengthSid` at `0x1800117e8`
- `ntdll!RtlLengthSid` at `0x180011afc`
- `ntdll!RtlLengthSid` at `0x180011b53`
- `ntdll!RtlCopySid` at `0x180011b14`
- `ntdll!RtlCopySid` at `0x180011b6c`
- `ntdll!RtlCopySid` at `0x180011b14`
- `ntdll!RtlCopySid` at `0x180011b6c`
- `ntdll!RtlEqualUnicodeString` at `0x180011419`
- `ntdll!RtlEqualUnicodeString` at `0x180011419`
- `CRYPTBASE!SystemFunction036` at `0x180011c05`
- `CRYPTBASE!SystemFunction036` at `0x180011c05`

## pseudocode

```c
__int64 __fastcall NlpBuildCacheEntry(
        struct _UNICODE_STRING *a1,
        __int64 a2,
        LONG a3,
        unsigned int a4,
        __m128i *a5,
        _LARGE_INTEGER **a6,
        unsigned int *a7)
{
  __int128 v7; // xmm6
  unsigned __int16 *v9; // r15
  unsigned int v10; // r13d
  char v11; // al
  struct _UNICODE_STRING v13; // xmm0
  __int128 v14; // xmm0
  int v15; // ebx
  unsigned int i; // edx
  __int16 v17; // cx
  __m128i *v18; // rbx
  int v19; // eax
  int v20; // r8d
  NTSTATUS v21; // r15d
  __m128i *v22; // rcx
  unsigned int v23; // eax
  unsigned int j; // edx
  __int32 *v25; // rax
  __int64 v26; // rcx
  __m128i v27; // xmm0
  int v28; // edx
  __m128i v29; // xmm0
  char *v30; // rax
  char *v31; // rbx
  bool v32; // sf
  int v33; // ebx
  ULONG v34; // eax
  unsigned int v35; // ebx
  bool v36; // zf
  int v37; // eax
  unsigned int v38; // edi
  ULONG v39; // eax
  size_t v40; // rdi
  _LARGE_INTEGER *v41; // rax
  _LARGE_INTEGER *v42; // rbx
  _LARGE_INTEGER v44; // rcx
  _LARGE_INTEGER v45; // rax
  bool v46; // cc
  __int64 Length; // rdi
  char *v48; // r12
  void *v49; // rcx
  __int64 v50; // rdi
  __int64 v51; // rdi
  __int64 v52; // rdi
  unsigned int v53; // eax
  __int64 v54; // rdi
  unsigned int v55; // eax
  __int64 v56; // rdi
  unsigned int v57; // eax
  __int64 v58; // rdi
  unsigned int v59; // eax
  __int64 v60; // rdi
  unsigned int v61; // eax
  __int64 v62; // rdi
  unsigned int v63; // eax
  __int64 v64; // rdi
  DWORD v65; // eax
  unsigned int v66; // eax
  __int64 v67; // rdi
  unsigned int v68; // eax
  __int64 v69; // rdi
  LONG v70; // eax
  __int64 v71; // rax
  char *v72; // rcx
  __int64 v73; // r15
  char *v74; // r13
  ULONG v75; // eax
  __int64 v76; // rdi
  int v77; // eax
  unsigned __int16 v78; // di
  DWORD v79; // eax
  void *v80; // rsi
  void *v81; // rcx
  __int64 v82; // rdi
  __m128i *v83; // rdi
  unsigned int v84; // ecx
  void *v85; // rbx
  struct _UNICODE_STRING v86; // [rsp+58h] [rbp-B0h] BYREF
  struct _LOGON_CACHE_ENTRY *v87; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v88[3]; // [rsp+70h] [rbp-98h] BYREF
  void *v89[2]; // [rsp+88h] [rbp-80h] BYREF
  void *v90; // [rsp+98h] [rbp-70h]
  _LARGE_INTEGER SystemTime; // [rsp+A0h] [rbp-68h] BYREF
  void *v92[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v93; // [rsp+B8h] [rbp-50h]
  char *v94; // [rsp+C8h] [rbp-40h]
  struct _UNICODE_STRING v95; // [rsp+D8h] [rbp-30h] BYREF
  struct _UNICODE_STRING v96; // [rsp+E8h] [rbp-20h] BYREF
  unsigned int v97; // [rsp+158h] [rbp+50h] BYREF
  size_t Size; // [rsp+160h] [rbp+58h] BYREF
  LONG v99; // [rsp+168h] [rbp+60h]
  unsigned int v100; // [rsp+170h] [rbp+68h]

  v100 = a4;
  v99 = a3;
  v7 = *(_OWORD *)(a2 + 208);
  v90 = 0;
  v87 = 0;
  v86 = 0;
  v9 = (unsigned __int16 *)(a2 + 48);
  *a6 = 0;
  v10 = a4;
  v11 = a3;
  LODWORD(Size) = 0;
  SystemTime.QuadPart = 0;
  v93 = 0;
  *a7 = 0;
  v13 = *(struct _UNICODE_STRING *)(a2 + 48);
  *(_OWORD *)&v88[1] = 0;
  v96 = v13;
  v14 = *(_OWORD *)(a2 + 288);
  v95 = 0;
  *(_OWORD *)v92 = v14;
  *(_OWORD *)v89 = 0;
  v15 = a3 & 8;
  if ( (a3 & 8) == 0 && !a1->Length )
  {
    if ( !RtlEqualUnicodeString(a1 + 2, (PCUNICODE_STRING)(a2 + 48), 1u) )
    {
      for ( i = 0; i < a1[2].Length >> 1; ++i )
      {
        if ( a1[2].Buffer[i] == 64 )
        {
          *(struct _UNICODE_STRING *)v89 = a1[2];
          break;
        }
      }
    }
    v11 = v99;
  }
  v17 = (__int16)v89[0];
  if ( !LOWORD(v89[0]) )
  {
    *(_OWORD *)v89 = *(_OWORD *)(a2 + 304);
    v17 = _mm_cvtsi128_si32(*(__m128i *)v89);
  }
  if ( (v11 & 1) == 0 )
  {
    v20 = (int)a1;
    v28 = 32;
    if ( v15 )
    {
      v86 = a1[2];
    }
    else
    {
      v86 = v96;
      *(_OWORD *)&v88[1] = v7;
    }
    if ( *(_DWORD *)&a1[1].Length == 16 && !v17 )
    {
      v97 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_905305d962583d6f838b30057de84013_Traceguids);
      if ( (int)NlpReadCacheEntry(a1, a1 + 2, 0, &v97, &v87, (unsigned int *)&Size) < 0 )
      {
        v90 = v87;
LABEL_40:
        v11 = v99;
        goto LABEL_41;
      }
      v90 = v87;
      v32 = (int)NlpGetAccountNamesInCacheEntry(v87, 0, 0, 0, &v95) < 0;
      v11 = v99;
      if ( !v32 )
        *(struct _UNICODE_STRING *)v89 = v95;
    }
LABEL_41:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
      WPP_SF_ZZZZZD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v28,
        v20,
        (unsigned int)&v88[1],
        (__int64)&v86,
        (__int64)v92,
        (__int64)&v96,
        (__int64)v89,
        v11);
    v33 = 8 * *(_DWORD *)(a2 + 156);
    v34 = RtlLengthSid(*(PSID *)(a2 + 224));
    v35 = ((*(unsigned __int16 *)(a2 + 96) + 3) & 0xFFFFFFFC)
        + ((LOWORD(v89[0]) + 3) & 0xFFFFFFFC)
        + ((v86.Length + 3) & 0xFFFFFFFC)
        + ((LOWORD(v88[1]) + 3) & 0xFFFFFFFC)
        + ((LOWORD(v92[0]) + 3) & 0xFFFFFFFC)
        + ((*(unsigned __int16 *)(a2 + 112) + 3) & 0xFFFFFFFC)
        + ((*(unsigned __int16 *)(a2 + 64) + 3) & 0xFFFFFFFC)
        + ((*(unsigned __int16 *)(a2 + 128) + 3) & 0xFFFFFFFC)
        + ((*(unsigned __int16 *)(a2 + 80) + 3) & 0xFFFFFFFC)
        + ((*(unsigned __int16 *)(a2 + 192) + 3) & 0xFFFFFFFC)
        + ((*(unsigned __int16 *)(a2 + 208) + 3) & 0xFFFFFFFC)
        + ((v34 + 3) & 0xFFFFFFFC)
        + ((*v9 + 3) & 0xFFFFFFFC)
        + ((v10 + 3) & 0xFFFFFFFC)
        + v33
        + 168;
    v36 = (*(_BYTE *)(a2 + 168) & 0x20) == 0;
    v97 = v35;
    if ( !v36 )
    {
      v37 = *(_DWORD *)(a2 + 272);
      if ( v37 )
      {
        v35 += 4 * v37;
        v38 = 0;
        v97 = v35;
        do
        {
          v39 = RtlLengthSid(*(PSID *)(*(_QWORD *)(a2 + 280) + 16LL * v38++));
          v35 += (v39 + 3) & 0xFFFFFFFC;
        }
        while ( v38 < *(_DWORD *)(a2 + 272) );
        v97 = v35;
      }
    }
    v40 = v35;
    v41 = (_LARGE_INTEGER *)((__int64 (__fastcall *)(_QWORD))qword_180088390)(v35);
    v42 = v41;
    if ( !v41 )
      return 3221225495LL;
    memset_0(v41, 0, v40);
    v42[5].LowPart = 65540;
    NtQuerySystemTime(&SystemTime);
    v44 = *(_LARGE_INTEGER *)(a2 + 24);
    v45 = SystemTime;
    v46 = v44.QuadPart <= SystemTime.QuadPart;
    LOBYTE(v42[6].LowPart) = 1;
    if ( !v46 )
      v45 = v44;
    v42[4] = v45;
    v42[7].LowPart = *(_DWORD *)&a1[1].Length;
    LOWORD(v42->LowPart) = v86.Length;
    Length = v86.Length;
    memcpy_0(&v42[21], v86.Buffer, v86.Length);
    HIWORD(v42->u.LowPart) = v88[1];
    v48 = (char *)(((unsigned __int64)&v42[21].QuadPart + Length + 3) & 0xFFFFFFFFFFFFFFFCuLL);
    if ( LOWORD(v88[1]) )
    {
      v49 = (void *)(((unsigned __int64)&v42[21].QuadPart + Length + 3) & 0xFFFFFFFFFFFFFFFCuLL);
      v50 = LOWORD(v88[1]);
      memcpy_0(v49, (const void *)v88[2], LOWORD(v88[1]));
      v48 = (char *)((unsigned __int64)&v48[v50 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
    }
    WORD2(v42[7].QuadPart) = v92[0];
    if ( LOWORD(v92[0]) )
    {
      v51 = LOWORD(v92[0]);
      memcpy_0(v48, v92[1], LOWORD(v92[0]));
      v48 = (char *)((unsigned __int64)&v48[v51 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
    }
    HIWORD(v42[7].QuadPart) = v89[0];
    if ( LOWORD(v89[0]) )
    {
      v52 = LOWORD(v89[0]);
      memcpy_0(v48, v89[1], LOWORD(v89[0]));
      v48 = (char *)((unsigned __int64)&v48[v52 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
    }
    v53 = *v9;
    WORD2(v42->QuadPart) = v53;
    if ( (_WORD)v53 )
    {
      v54 = v53;
      memcpy_0(v48, *(const void **)(a2 + 56), v53);
      v48 = (char *)((unsigned __int64)&v48[v54 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
    }
    v55 = *(unsigned __int16 *)(a2 + 64);
    HIWORD(v42->QuadPart) = v55;
    if ( (_WORD)v55 )
    {
      v56 = v55;
      memcpy_0(v48, *(const void **)(a2 + 72), v55);
      v48 = (char *)((unsigned __int64)&v48[v56 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
    }
    v57 = *(unsigned __int16 *)(a2 + 80);
    LOWORD(v42[1].LowPart) = v57;
    if ( (_WORD)v57 )
    {
      v58 = v57;
      memcpy_0(v48, *(const void **)(a2 + 88), v57);
      v48 = (char *)((unsigned __int64)&v48[v58 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
    }
    v59 = *(unsigned __int16 *)(a2 + 96);
    HIWORD(v42[1].u.LowPart) = v59;
    if ( (_WORD)v59 )
    {
      v60 = v59;
      memcpy_0(v48, *(const void **)(a2 + 104), v59);
      v48 = (char *)((unsigned __int64)&v48[v60 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
    }
    v61 = *(unsigned __int16 *)(a2 + 112);
    WORD2(v42[1].QuadPart) = v61;
    if ( (_WORD)v61 )
    {
      v62 = v61;
      memcpy_0(v48, *(const void **)(a2 + 120), v61);
      v48 = (char *)((unsigned __int64)&v48[v62 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
    }
    v63 = *(unsigned __int16 *)(a2 + 128);
    HIWORD(v42[1].QuadPart) = v63;
    if ( (_WORD)v63 )
    {
      v64 = v63;
      memcpy_0(v48, *(const void **)(a2 + 136), v63);
      v48 = (char *)((unsigned __int64)&v48[v64 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
    }
    v42[2].LowPart = *(_DWORD *)(a2 + 148);
    v42[2].HighPart = *(_DWORD *)(a2 + 152);
    v65 = *(_DWORD *)(a2 + 156);
    v42[3].LowPart = v65;
    v66 = 8 * v65;
    if ( v66 )
    {
      v67 = v66;
      memcpy_0(v48, *(const void **)(a2 + 160), v66);
      v48 = (char *)((unsigned __int64)&v48[v67 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
    }
    v68 = *(unsigned __int16 *)(a2 + 208);
    WORD2(v42[3].QuadPart) = v68;
    if ( (_WORD)v68 )
    {
      v69 = v68;
      memcpy_0(v48, *(const void **)(a2 + 216), v68);
      v48 = (char *)((unsigned __int64)&v48[v69 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
    }
    if ( (*(_BYTE *)(a2 + 168) & 0x20) != 0 )
    {
      v70 = *(_DWORD *)(a2 + 272);
      v42[5].HighPart = v70;
      v71 = (unsigned int)(4 * v70);
      if ( (_DWORD)v71 )
      {
        v72 = v48;
        v73 = 0;
        v48 += v71;
        v94 = v72;
        if ( *(_DWORD *)(a2 + 272) )
        {
          v74 = v72;
          do
          {
            *(_DWORD *)&v74[4 * v73] = *(_DWORD *)(*(_QWORD *)(a2 + 280) + 16LL * (unsigned int)v73 + 8);
            v75 = RtlLengthSid(*(PSID *)(*(_QWORD *)(a2 + 280) + 16LL * (unsigned int)v73));
            v76 = v75;
            RtlCopySid(v75, v48, *(PSID *)(*(_QWORD *)(a2 + 280) + 16LL * (unsigned int)v73));
            v73 = (unsigned int)(v73 + 1);
            v48 = (char *)((unsigned __int64)&v48[v76 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
          }
          while ( (unsigned int)v73 < *(_DWORD *)(a2 + 272) );
          v10 = v100;
          LODWORD(v72) = (_DWORD)v94;
        }
        v77 = (_DWORD)v48 - (_DWORD)v72;
LABEL_84:
        v42[6].HighPart = v77;
        v78 = RtlLengthSid(*(PSID *)(a2 + 224));
        HIWORD(v42[3].QuadPart) = v78;
        v21 = RtlCopySid(v78, v48, *(PSID *)(a2 + 224));
        if ( v21 >= 0 )
        {
          v79 = *(unsigned __int16 *)(a2 + 192);
          v42[18].LowPart = v79;
          v80 = (void *)((unsigned __int64)&v48[v78 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
          if ( v79 )
          {
            v81 = (void *)((unsigned __int64)&v48[v78 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
            v82 = v79;
            memcpy_0(v81, *(const void **)(a2 + 200), v79);
            v80 = (void *)(((unsigned __int64)v80 + v82 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
          }
          v42[16].HighPart = v10;
          v42[17].LowPart = (_DWORD)v80 - (_DWORD)v42;
          if ( !v10 )
            goto LABEL_91;
          v83 = a5;
          v21 = NlpValidateSupplementalData(v10, a5);
          if ( v21 == -1073741275 )
          {
            v21 = 0;
LABEL_90:
            memcpy_0(v80, v83, v10);
LABEL_91:
            SystemFunction036(&v42[8], 0x10u);
            v84 = v97;
            v42[17].HighPart = v99;
            v42[18].HighPart = *(_DWORD *)(a2 + 40);
            v42[19].LowPart = *(_DWORD *)(a2 + 44);
            *a6 = v42;
            *a7 = v84;
            goto LABEL_97;
          }
          if ( v21 >= 0 )
            goto LABEL_90;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              44,
              WPP_905305d962583d6f838b30057de84013_Traceguids,
              (unsigned int)v21);
        }
        ((void (__fastcall *)(_LARGE_INTEGER *))qword_180088398)(v42);
LABEL_97:
        v85 = v90;
        if ( v90 )
        {
          memset_0(v90, 0, (unsigned int)Size);
          ((void (__fastcall *)(void *))qword_180088398)(v85);
        }
        goto LABEL_99;
      }
    }
    else
    {
      v42[5].HighPart = 0;
    }
    v77 = 0;
    goto LABEL_84;
  }
  v18 = a5;
  v19 = NlpValidateSupplementalData(v10, a5);
  v21 = v19;
  if ( v19 == -1073741275 )
  {
    v22 = v18;
    v23 = v10;
LABEL_21:
    if ( v23 >= 0x20 )
    {
      v27 = *v22;
      *(_QWORD *)&v86.Length = v22->m128i_i64[0];
      v28 = v86.Length;
      v86.Buffer = (unsigned __int16 *)((char *)v22->m128i_u16 + _mm_srli_si128(v27, 8).m128i_u64[0]);
      v29 = *(__m128i *)((char *)&v22[1] + ((v86.Length + 3LL) & 0xFFFFFFFFFFFFFFFCuLL));
      v88[1] = *(__int64 *)((char *)v22[1].m128i_i64 + ((v86.Length + 3LL) & 0xFFFFFFFFFFFFFFFCuLL));
      v88[2] = (char *)v22 + _mm_srli_si128(v29, 8).m128i_u64[0];
      if ( !LOWORD(v89[0]) )
      {
        LOWORD(v93) = v86.Length + LOWORD(v88[1]) + 2;
        WORD1(v93) = v86.Length + LOWORD(v88[1]) + 4;
        v30 = (char *)((__int64 (*)(void))LsaFunctions->AllocatePrivateHeap)();
        *((_QWORD *)&v93 + 1) = v30;
        v31 = v30;
        if ( !v30 )
        {
          v21 = -1073741801;
          goto LABEL_99;
        }
        memcpy_0(v30, v86.Buffer, v86.Length);
        *(_WORD *)&v31[v86.Length] = 64;
        memcpy_0(&v31[v86.Length + 2], (const void *)v88[2], LOWORD(v88[1]));
        *(_OWORD *)v89 = v93;
      }
      v9 = (unsigned __int16 *)(a2 + 48);
      goto LABEL_40;
    }
LABEL_27:
    v21 = -1073741811;
    goto LABEL_99;
  }
  if ( v19 >= 0 )
  {
    for ( j = 0; j < v18->m128i_i32[2]; ++j )
    {
      v25 = &v18->m128i_i32[3 * j];
      if ( !v25[3] )
      {
        _mm_lfence();
        v26 = (unsigned int)v25[4];
        v23 = v25[5];
        v22 = (__m128i *)((char *)v18 + v26);
        goto LABEL_21;
      }
    }
    goto LABEL_27;
  }
LABEL_99:
  if ( v95.Buffer )
    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
  if ( *((_QWORD *)&v93 + 1) )
    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180011370  mov     rax, rsp
0x180011373  mov     [rax+20h], r9d
0x180011377  mov     [rax+18h], r8d
0x18001137b  push    rbp
0x18001137c  push    rbx
0x18001137d  push    rsi
0x18001137e  push    rdi
0x18001137f  push    r12
0x180011381  push    r13
0x180011383  push    r14
0x180011385  push    r15
0x180011387  lea     rbp, [rax-48h]
0x18001138b  sub     rsp, 108h
0x180011392  xor     r12d, r12d
0x180011395  movaps  xmmword ptr [rax-58h], xmm6
0x180011399  movups  xmm6, xmmword ptr [rdx+0D0h]
0x1800113a0  mov     [rbp+40h+var_B0], r12
0x1800113a4  mov     rsi, rcx
0x1800113a7  mov     rcx, [rbp+40h+arg_28]
0x1800113ab  xorps   xmm0, xmm0
0x1800113ae  xorps   xmm1, xmm1
0x1800113b1  mov     [rsp+140h+var_E0], r12
0x1800113b6  movups  [rsp+140h+var_F8+8], xmm0
0x1800113bb  lea     r15, [rdx+30h]
0x1800113bf  mov     ebx, r8d
0x1800113c2  mov     [rcx], r12
0x1800113c5  mov     r13d, r9d
0x1800113c8  mov     rcx, [rbp+40h+arg_30]
0x1800113cf  mov     eax, r8d
0x1800113d2  mov     dword ptr [rbp+40h+Size], r12d
0x1800113d6  mov     r14, rdx
0x1800113d9  mov     qword ptr [rbp+40h+SystemTime], r12
0x1800113dd  movups  [rbp+40h+var_90], xmm0
0x1800113e1  mov     [rcx], r12d
0x1800113e4  movups  xmm0, xmmword ptr [r15]
0x1800113e8  movups  xmmword ptr [rsp+140h+var_D8+8], xmm1
0x1800113ed  movaps  xmmword ptr [rbp-20h], xmm0
0x1800113f1  movups  xmm0, xmmword ptr [rdx+120h]
0x1800113f8  movups  xmmword ptr [rbp+40h+var_70.Length], xmm1
0x1800113fc  movups  xmmword ptr [rbp+40h+var_A0], xmm0
0x180011400  movups  xmmword ptr [rbp+40h+var_C0], xmm1
0x180011404  and     ebx, 8
0x180011407  jnz     short loc_18001144F
0x180011409  cmp     [rsi], r12w
0x18001140d  jnz     short loc_18001144F
0x18001140f  mov     r8b, 1; CaseInsensitive
0x180011412  lea     rcx, [rsi+20h]; String1
0x180011416  mov     rdx, r15; String2
0x180011419  call    cs:__imp_RtlEqualUnicodeString
0x18001141f  test    al, al
0x180011421  jnz     short loc_18001144C
0x180011423  movzx   r8d, word ptr [rsi+20h]
0x180011428  mov     edx, r12d
0x18001142b  shr     r8d, 1
0x18001142e  cmp     edx, r8d
0x180011431  jnb     short loc_18001144C
0x180011433  mov     rax, [rsi+28h]
0x180011437  mov     ecx, edx
0x180011439  cmp     word ptr [rax+rcx*2], 40h ; '@'
0x18001143e  jz      short loc_180011444
0x180011440  inc     edx
0x180011442  jmp     short loc_18001142E
0x180011444  movups  xmm0, xmmword ptr [rsi+20h]
0x180011448  movaps  xmmword ptr [rbp+40h+var_C0], xmm0
0x18001144c  mov     eax, [rbp+40h+arg_10]
0x18001144f  movzx   ecx, word ptr [rbp+40h+var_C0]
0x180011453  test    cx, cx
0x180011456  jnz     short loc_180011468
0x180011458  movups  xmm0, xmmword ptr [r14+130h]
0x180011460  movaps  xmmword ptr [rbp+40h+var_C0], xmm0
0x180011464  movd    ecx, xmm0
0x180011468  lea     rdi, WPP_GLOBAL_Control
0x18001146f  test    al, 1
0x180011471  jz      loc_1800115BF
0x180011477  mov     rbx, [rbp+40h+arg_20]
0x18001147b  mov     ecx, r13d
0x18001147e  mov     rdx, rbx
0x180011481  call    NlpValidateSupplementalData
0x180011486  mov     r15d, eax
0x180011489  cmp     eax, 0C0000225h
0x18001148e  jnz     short loc_180011498
0x180011490  mov     rcx, rbx
0x180011493  mov     eax, r13d
0x180011496  jmp     short loc_1800114CD
0x180011498  test    eax, eax
0x18001149a  js      loc_180011CA8
0x1800114a0  mov     edx, r12d
0x1800114a3  cmp     edx, [rbx+8]
0x1800114a6  jnb     loc_1800115B4
0x1800114ac  mov     eax, edx
0x1800114ae  lea     rcx, [rax+rax*2]
0x1800114b2  cmp     [rbx+rcx*4+0Ch], r12d
0x1800114b7  lea     rax, [rbx+rcx*4]
0x1800114bb  jz      short loc_1800114C1
0x1800114bd  inc     edx
0x1800114bf  jmp     short loc_1800114A3
0x1800114c1  lfence
0x1800114c4  mov     ecx, [rax+10h]
0x1800114c7  mov     eax, [rax+14h]
0x1800114ca  add     rcx, rbx
0x1800114cd  cmp     eax, 20h ; ' '
0x1800114d0  jb      loc_1800115B4
0x1800114d6  movups  xmm0, xmmword ptr [rcx]
0x1800114d9  movaps  [rsp+140h+var_F8+8], xmm0
0x1800114de  movzx   edx, word ptr [rsp+140h+var_F8+8]
0x1800114e3  psrldq  xmm0, 8
0x1800114e8  movq    rax, xmm0
0x1800114ed  add     rax, rcx
0x1800114f0  mov     [rsp+140h+Src], rax
0x1800114f5  lea     rax, [rdx+3]
0x1800114f9  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800114fd  movups  xmm0, xmmword ptr [rax+rcx+10h]
0x180011502  movaps  xmmword ptr [rsp+140h+var_D8+8], xmm0
0x180011507  psrldq  xmm0, 8
0x18001150c  movq    rax, xmm0
0x180011511  add     rax, rcx
0x180011514  mov     qword ptr [rsp+140h+var_D8+10h], rax
0x180011519  cmp     word ptr [rbp+40h+var_C0], r12w
0x18001151e  jnz     loc_1800115AB
0x180011524  movzx   ecx, word ptr [rsp+140h+var_D8+8]
0x180011529  add     cx, dx
0x18001152c  lea     eax, [rcx+2]
0x18001152f  add     cx, 4
0x180011533  mov     word ptr [rbp+40h+var_90], ax
0x180011537  mov     rax, cs:LsaFunctions
0x18001153e  movzx   ecx, cx
0x180011541  mov     word ptr [rbp+40h+var_90+2], cx
0x180011545  mov     rax, [rax+180h]
0x18001154c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011551  mov     qword ptr [rbp+40h+var_90+8], rax
0x180011555  mov     rbx, rax
0x180011558  test    rax, rax
0x18001155b  jnz     short loc_180011568
0x18001155d  mov     r15d, 0C0000017h
0x180011563  jmp     loc_180011CA8
0x180011568  movzx   r8d, word ptr [rsp+140h+var_F8+8]; Size
0x18001156e  mov     rcx, rbx; void *
0x180011571  mov     rdx, [rsp+140h+Src]; Src
0x180011576  call    memcpy_0
0x18001157b  movzx   eax, word ptr [rsp+140h+var_F8+8]
0x180011580  mov     word ptr [rax+rbx], 40h ; '@'
0x180011586  movzx   ecx, word ptr [rsp+140h+var_F8+8]
0x18001158b  movzx   r8d, word ptr [rsp+140h+var_D8+8]; Size
0x180011591  add     rcx, 2
0x180011595  mov     rdx, qword ptr [rsp+140h+var_D8+10h]; Src
0x18001159a  add     rcx, rbx; void *
0x18001159d  call    memcpy_0
0x1800115a2  movaps  xmm0, [rbp+40h+var_90]
0x1800115a6  movdqa  xmmword ptr [rbp+40h+var_C0], xmm0
0x1800115ab  lea     r15, [r14+30h]
0x1800115af  jmp     loc_180011691
0x1800115b4  mov     r15d, 0C000000Dh
0x1800115ba  jmp     loc_180011CA8
0x1800115bf  mov     r8, rsi
0x1800115c2  mov     edx, 20h ; ' '
0x1800115c7  test    ebx, ebx
0x1800115c9  jz      short loc_1800115D6
0x1800115cb  movups  xmm0, xmmword ptr [rsi+20h]
0x1800115cf  movaps  [rsp+140h+var_F8+8], xmm0
0x1800115d4  jmp     short loc_1800115E6
0x1800115d6  movaps  xmm0, xmmword ptr [rbp-20h]
0x1800115da  movdqa  [rsp+140h+var_F8+8], xmm0
0x1800115e0  movdqa  xmmword ptr [rsp+140h+var_D8+8], xmm6
0x1800115e6  cmp     dword ptr [rsi+10h], 10h
0x1800115ea  jnz     loc_180011694
0x1800115f0  test    cx, cx
0x1800115f3  jnz     loc_180011694
0x1800115f9  lea     rbx, [rdx+r8]
0x1800115fd  mov     [rbp+40h+arg_0], r12d
0x180011601  mov     rcx, cs:WPP_GLOBAL_Control
0x180011608  cmp     rcx, rdi
0x18001160b  jz      short loc_18001162B
0x18001160d  test    dword ptr [rcx+1Ch], 4000h
0x180011614  jz      short loc_18001162B
0x180011616  mov     rcx, [rcx+10h]
0x18001161a  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x180011621  mov     edx, 2Ah ; '*'
0x180011626  call    WPP_SF_
0x18001162b  lea     rax, [rbp+40h+Size]
0x18001162f  xor     r8d, r8d; unsigned int
0x180011632  mov     [rsp+140h+var_118], rax; unsigned int *
0x180011637  lea     r9, [rbp+40h+arg_0]; unsigned int *
0x18001163b  lea     rax, [rsp+140h+var_E0]
0x180011640  mov     rdx, rbx; struct _UNICODE_STRING *
0x180011643  mov     rcx, rsi; struct _UNICODE_STRING *
0x180011646  mov     [rsp+140h+var_120], rax; struct _LOGON_CACHE_ENTRY **
0x18001164b  call    ?NlpReadCacheEntry@@YAJPEAU_UNICODE_STRING@@0KPEAKPEAPEAU_LOGON_CACHE_ENTRY@@1@Z; NlpReadCacheEntry(_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong *,_LOGON_CACHE_ENTRY * *,ulong *)
0x180011650  test    eax, eax
0x180011652  js      short loc_180011688
0x180011654  mov     rbx, [rsp+140h+var_E0]
0x180011659  lea     rax, [rbp+40h+var_70]
0x18001165d  mov     rcx, rbx; struct _LOGON_CACHE_ENTRY *
0x180011660  mov     [rsp+140h+var_120], rax; struct _UNICODE_STRING *
0x180011665  xor     r9d, r9d; struct _UNICODE_STRING *
0x180011668  mov     [rbp+40h+var_B0], rbx
0x18001166c  xor     r8d, r8d; struct _UNICODE_STRING *
0x18001166f  xor     edx, edx; struct _UNICODE_STRING *
0x180011671  call    ?NlpGetAccountNamesInCacheEntry@@YAJPEAU_LOGON_CACHE_ENTRY@@PEAU_UNICODE_STRING@@111@Z; NlpGetAccountNamesInCacheEntry(_LOGON_CACHE_ENTRY *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x180011676  test    eax, eax
0x180011678  mov     eax, [rbp+40h+arg_10]
0x18001167b  js      short loc_180011694
0x18001167d  movaps  xmm0, xmmword ptr [rbp+40h+var_70.Length]
0x180011681  movdqa  xmmword ptr [rbp+40h+var_C0], xmm0
0x180011686  jmp     short loc_180011694
0x180011688  mov     rax, [rsp+140h+var_E0]
0x18001168d  mov     [rbp+40h+var_B0], rax
0x180011691  mov     eax, [rbp+40h+arg_10]
0x180011694  mov     rcx, cs:WPP_GLOBAL_Control
0x18001169b  cmp     rcx, rdi
0x18001169e  jz      short loc_1800116E0
0x1800116a0  test    dword ptr [rcx+1Ch], 4000h
0x1800116a7  jz      short loc_1800116E0
0x1800116a9  mov     rcx, [rcx+10h]
0x1800116ad  lea     r9, [rsp+140h+var_D8+8]
0x1800116b2  mov     [rsp+40h], eax
0x1800116b6  lea     rax, [rbp+40h+var_C0]
0x1800116ba  mov     qword ptr [rsp+140h+var_108], rax
0x1800116bf  lea     rax, [rbp+40h+var_60]
0x1800116c3  mov     [rsp+140h+var_110], rax
0x1800116c8  lea     rax, [rbp+40h+var_A0]
0x1800116cc  mov     [rsp+140h+var_118], rax
0x1800116d1  lea     rax, [rsp+140h+var_F8+8]
0x1800116d6  mov     [rsp+140h+var_120], rax
0x1800116db  call    WPP_SF_ZZZZZD
0x1800116e0  mov     eax, [r14+9Ch]
0x1800116e7  mov     rcx, [r14+0E0h]; Sid
0x1800116ee  lea     ebx, ds:0[rax*8]
0x1800116f5  call    cs:__imp_RtlLengthSid
0x1800116fb  movzx   edx, word ptr [r14+0D0h]
0x180011703  add     ebx, 0A8h
0x180011709  movzx   ecx, word ptr [r15]
0x18001170d  add     edx, 3
0x180011710  and     edx, 0FFFFFFFCh
0x180011713  add     ecx, 3
0x180011716  lea     r8d, [rax+3]
0x18001171a  and     ecx, 0FFFFFFFCh
0x18001171d  movzx   eax, word ptr [r14+0C0h]
0x180011725  and     r8d, 0FFFFFFFCh
0x180011729  add     eax, 3
0x18001172c  add     ecx, r8d
0x18001172f  and     eax, 0FFFFFFFCh
0x180011732  add     edx, eax
0x180011734  movzx   eax, word ptr [r14+50h]
0x180011739  add     eax, 3
0x18001173c  and     eax, 0FFFFFFFCh
0x18001173f  add     edx, eax
0x180011741  movzx   eax, word ptr [r14+80h]
0x180011749  add     eax, 3
0x18001174c  and     eax, 0FFFFFFFCh
0x18001174f  add     edx, eax
0x180011751  movzx   eax, word ptr [r14+40h]
0x180011756  add     eax, 3
0x180011759  and     eax, 0FFFFFFFCh
0x18001175c  add     edx, eax
0x18001175e  movzx   eax, word ptr [r14+70h]
0x180011763  add     eax, 3
0x180011766  and     eax, 0FFFFFFFCh
0x180011769  add     edx, eax
0x18001176b  movzx   eax, word ptr [rbp+40h+var_A0]
0x18001176f  add     eax, 3
0x180011772  and     eax, 0FFFFFFFCh
0x180011775  add     edx, eax
0x180011777  movzx   eax, word ptr [rsp+140h+var_D8+8]
0x18001177c  add     eax, 3
0x18001177f  and     eax, 0FFFFFFFCh
0x180011782  add     edx, eax
0x180011784  movzx   eax, word ptr [rsp+140h+var_F8+8]
0x180011789  add     eax, 3
0x18001178c  and     eax, 0FFFFFFFCh
0x18001178f  add     edx, eax
0x180011791  movzx   eax, word ptr [rbp+40h+var_C0]
0x180011795  add     eax, 3
0x180011798  and     eax, 0FFFFFFFCh
0x18001179b  add     edx, eax
0x18001179d  movzx   eax, word ptr [r14+60h]
0x1800117a2  add     eax, 3
0x1800117a5  and     eax, 0FFFFFFFCh
0x1800117a8  add     edx, eax
0x1800117aa  lea     eax, [r13+3]
0x1800117ae  and     eax, 0FFFFFFFCh
0x1800117b1  add     ecx, edx
0x1800117b3  add     eax, ecx
0x1800117b5  add     ebx, eax
0x1800117b7  test    byte ptr [r14+0A8h], 20h
0x1800117bf  mov     [rbp+40h+arg_0], ebx
0x1800117c2  jz      short loc_180011804
0x1800117c4  mov     eax, [r14+110h]
0x1800117cb  test    eax, eax
0x1800117cd  jz      short loc_180011804
0x1800117cf  lea     ebx, [rbx+rax*4]
0x1800117d2  mov     edi, r12d
0x1800117d5  mov     [rbp+40h+arg_0], ebx
0x1800117d8  mov     rcx, [r14+118h]
0x1800117df  mov     eax, edi
0x1800117e1  add     rax, rax
0x1800117e4  mov     rcx, [rcx+rax*8]; Sid
0x1800117e8  call    cs:__imp_RtlLengthSid
0x1800117ee  add     eax, 3
0x1800117f1  inc     edi
0x1800117f3  and     eax, 0FFFFFFFCh
  ... truncated ...
```
