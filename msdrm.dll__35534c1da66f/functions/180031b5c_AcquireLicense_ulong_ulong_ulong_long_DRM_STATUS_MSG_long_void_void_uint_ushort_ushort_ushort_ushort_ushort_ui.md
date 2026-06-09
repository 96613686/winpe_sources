# AcquireLicense(ulong,ulong,ulong,long (*)(_DRM_STATUS_MSG,long,void *,void *),uint,ushort *,ushort *,ushort *,ushort *,ushort *,uint,ushort *,ushort *,ushort *,ushort *,void *)

- ea: `0x180031b5c`
- end: `0x18003259e`
- name: `?AcquireLicense@@YAJKKKP6AJW4_DRM_STATUS_MSG@@JPEAX1@ZIPEAG3333I33331@Z`
- size: `2626`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int, int (*)(enum _DRM_STATUS_MSG, int, void *, void *), unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001a680`

## callees

- `0x180001244`
- `0x180001284`
- `0x18000420c`
- `0x180004654`
- `0x1800046c8`
- `0x180015438`
- `0x180017358`
- `0x180019e28`
- `0x18001a1fc`
- `0x180031b5c`
- `0x1800385a0`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x180032487`
- `msvcrt!_beginthreadex` at `0x180032487`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031c8b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031c8b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180031c96`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180031c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032492`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031ff7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031ff7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032505`

## string_xrefs

- `0x180031c1f`: `UDRMReaderLicAcq_%lu`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=7
__int64 __fastcall AcquireLicense(
        unsigned int a1,
        int a2,
        int a3,
        int (*a4)(enum _DRM_STATUS_MSG, int, void *, void *),
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        unsigned __int16 *a10,
        unsigned int a11,
        unsigned __int16 *a12,
        unsigned __int16 *a13,
        unsigned __int16 *a14,
        unsigned __int16 *a15,
        void *a16)
{
  void *v18; // r15
  void *v19; // rax
  signed int ThreadTermEvent; // ebx
  int v21; // esi
  DRMOS *v22; // rcx
  const unsigned __int16 *v23; // r9
  void *v24; // rax
  signed int LastError; // eax
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // r8
  __int64 v33; // r9
  void **v34; // rax
  __int64 v35; // r9
  void **v36; // rsi
  __int64 v37; // rdx
  unsigned __int16 *v38; // rax
  unsigned __int64 v39; // r8
  signed __int64 v40; // rbx
  unsigned __int64 v41; // rax
  unsigned __int64 v42; // rcx
  unsigned __int16 *v43; // rax
  unsigned __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rdx
  unsigned __int16 *v47; // rax
  signed __int64 v48; // rbx
  unsigned __int64 v49; // rax
  unsigned __int64 v50; // rcx
  unsigned __int16 *v51; // rax
  __int64 v52; // rdx
  unsigned __int16 *v53; // rax
  unsigned __int64 v54; // r8
  signed __int64 v55; // rbx
  void *v56; // rcx
  unsigned __int64 v57; // rax
  unsigned __int64 v58; // rcx
  unsigned __int16 *v59; // rax
  __int64 v60; // rdx
  unsigned __int16 *v61; // rax
  unsigned __int64 v62; // r8
  signed __int64 v63; // rbx
  unsigned __int64 v64; // rax
  unsigned __int64 v65; // rcx
  unsigned __int16 *v66; // rax
  unsigned __int16 *v67; // rax
  __int64 v68; // rdx
  unsigned __int64 v69; // r8
  signed __int64 v70; // rbx
  unsigned __int64 v71; // rax
  unsigned __int64 v72; // rcx
  unsigned __int16 *v73; // rax
  __int64 v74; // rdx
  unsigned __int16 *v75; // rax
  unsigned __int64 v76; // r8
  signed __int64 v77; // rbx
  unsigned __int64 v78; // rax
  unsigned __int64 v79; // rcx
  unsigned __int16 *v80; // rax
  unsigned __int16 *v81; // rax
  __int64 v82; // rcx
  unsigned __int64 v83; // rdx
  signed __int64 v84; // rbx
  unsigned __int64 v85; // rax
  unsigned __int64 v86; // rcx
  unsigned __int16 *v87; // rax
  void *v88; // rax
  signed int v89; // eax
  unsigned int ThrdAddr; // [rsp+50h] [rbp-68h] BYREF
  void **v92; // [rsp+58h] [rbp-60h]
  void *v93; // [rsp+60h] [rbp-58h]
  void *Block; // [rsp+68h] [rbp-50h]
  __int64 v95; // [rsp+70h] [rbp-48h]

  v95 = -2;
  _RTLTRACE("[msdrm]:+AcquireLicense");
  ThrdAddr = 0;
  v18 = 0;
  _RTLTRACE(
    "[msdrm]: AcquireLicense : wszDPURL = %S, wszLAURL = %S , wszExtLAURL = %S, wszContentID = %S , uFlags = %d , wszRequ"
    "estedRights = %S ,wszDPURLFriendlyName = %S , wszUserCert = %S  ",
    a6,
    a7,
    a8,
    a9,
    a11,
    a12,
    a13,
    a14);
  v19 = operator new(0x3Eu);
  Block = v19;
  if ( !v19 )
    goto LABEL_2;
  v21 = (int)v19;
  ThreadTermEvent = StringCchPrintfW((unsigned __int16 *)v19, 0x1Fu, L"UDRMReaderLicAcq_%lu", a1);
  if ( ThreadTermEvent >= 0 )
  {
    v24 = DRMOS::OpenEventA(v22, 1u, v21, v23);
    v18 = v24;
    v93 = v24;
    if ( !v24 )
    {
      LastError = GetLastError();
      ThreadTermEvent = LastError;
      if ( LastError > 0 )
        ThreadTermEvent = (unsigned __int16)LastError | 0x80070000;
      if ( ThreadTermEvent >= 0 )
        ThreadTermEvent = -2147467259;
      goto LABEL_123;
    }
    if ( (a11 & 4) != 0 )
    {
      SetEvent(v24);
      goto LABEL_123;
    }
    ResetEvent(v24);
    if ( !a4
      || !(unsigned __int8)DRMIsValidStringT<unsigned short>(a9, 0, v26, v27)
      || !(unsigned __int8)DRMIsValidStringT<unsigned short>(a10, 0, v28, v29)
      || a15 && !(unsigned __int8)DRMIsValidStringT<unsigned short>(a15, 0, v30, v31)
      || a12 && !(unsigned __int8)DRMIsValidStringT<unsigned short>(a12, 0, v30, v31)
      || !(unsigned __int8)DRMIsValidStringT<unsigned short>(a7, 0, v30, v31)
      && !(unsigned __int8)DRMIsValidStringT<unsigned short>(a8, 0, v32, v33)
      || !(unsigned __int8)DRMIsValidStringT<unsigned short>(a14, 0, v32, v33) )
    {
      ThreadTermEvent = -2147024809;
      goto LABEL_123;
    }
    v34 = (void **)operator new(0x70u);
    v36 = v34;
    v92 = v34;
    if ( !v34 )
    {
LABEL_2:
      ThreadTermEvent = -2147024882;
      goto LABEL_123;
    }
    *v34 = 0;
    v34[1] = 0;
    v34[2] = 0;
    v34[4] = 0;
    v34[5] = 0;
    v34[6] = 0;
    v34[7] = 0;
    v34[8] = 0;
    v34[9] = 0;
    v34[12] = 0;
    v34[13] = 0;
    v34[10] = a4;
    v34[11] = a16;
    v92 = v34;
    if ( !a9 )
    {
      ThreadTermEvent = -2147024809;
      goto LABEL_56;
    }
    v37 = 0x7FFFFFFF;
    v38 = a9;
    do
    {
      if ( !*v38 )
        break;
      ++v38;
      --v37;
    }
    while ( v37 );
    ThreadTermEvent = v37 == 0 ? 0x80070057 : 0;
    v39 = (0x7FFFFFFF - v37) & -(__int64)(v37 != 0);
    if ( !v37 )
      goto LABEL_56;
    v40 = v39 + 1;
    if ( v39 + 1 < v39 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    if ( v40 < 0 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    v41 = 2LL * (unsigned int)v40;
    v42 = HIDWORD(v40) << 33;
    if ( v42 + v41 < v41 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    if ( v42 + v41 )
    {
      v43 = (unsigned __int16 *)operator new(saturated_mul(v40, 2u));
      *v36 = v43;
      if ( !v43 )
      {
        ThreadTermEvent = -2147024882;
LABEL_56:
        v56 = v36[12];
        if ( v56 )
          CloseHandle(v56);
        operator delete(*v36);
        operator delete(v36[1]);
        operator delete(v36[2]);
        operator delete(v36[4]);
        operator delete(v36[5]);
        operator delete(v36[7]);
        operator delete(v36[6]);
        operator delete(v36);
        goto LABEL_123;
      }
      ThreadTermEvent = StringCchCopyW(v43, v40, a9);
      if ( ThreadTermEvent < 0 )
        goto LABEL_56;
    }
    if ( (unsigned __int8)DRMIsValidStringT<unsigned short>(a7, 0, v39, v35) )
    {
      if ( !a7 )
      {
        ThreadTermEvent = -2147024809;
        goto LABEL_56;
      }
      v46 = 0x7FFFFFFF;
      v47 = a7;
      do
      {
        if ( !*v47 )
          break;
        ++v47;
        --v46;
      }
      while ( v46 );
      ThreadTermEvent = v46 == 0 ? 0x80070057 : 0;
      v44 = (0x7FFFFFFF - v46) & -(__int64)(v46 != 0);
      if ( !v46 )
        goto LABEL_56;
      v48 = v44 + 1;
      if ( v44 + 1 < v44 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      if ( v48 < 0 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      v49 = 2LL * (unsigned int)v48;
      v50 = HIDWORD(v48) << 33;
      if ( v50 + v49 < v49 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      if ( v50 + v49 )
      {
        v51 = (unsigned __int16 *)operator new(saturated_mul(v48, 2u));
        v36[1] = v51;
        if ( !v51 )
        {
          ThreadTermEvent = -2147024882;
          goto LABEL_56;
        }
        ThreadTermEvent = StringCchCopyW(v51, v48, a7);
        if ( ThreadTermEvent < 0 )
          goto LABEL_56;
      }
    }
    if ( (unsigned __int8)DRMIsValidStringT<unsigned short>(a8, 0, v44, v45) )
    {
      if ( !a8 )
      {
        ThreadTermEvent = -2147024809;
        goto LABEL_56;
      }
      v52 = 0x7FFFFFFF;
      v53 = a8;
      do
      {
        if ( !*v53 )
          break;
        ++v53;
        --v52;
      }
      while ( v52 );
      ThreadTermEvent = v52 == 0 ? 0x80070057 : 0;
      v54 = (0x7FFFFFFF - v52) & -(__int64)(v52 != 0);
      if ( !v52 )
        goto LABEL_56;
      v55 = v54 + 1;
      if ( v54 + 1 < v54 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      if ( v55 < 0 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      v57 = 2LL * (unsigned int)v55;
      v58 = HIDWORD(v55) << 33;
      if ( v58 + v57 < v57 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      if ( v58 + v57 )
      {
        v59 = (unsigned __int16 *)operator new(saturated_mul(v55, 2u));
        v36[2] = v59;
        if ( !v59 )
        {
          ThreadTermEvent = -2147024882;
          goto LABEL_56;
        }
        ThreadTermEvent = StringCchCopyW(v59, v55, a8);
        if ( ThreadTermEvent < 0 )
          goto LABEL_56;
      }
    }
    if ( !a10 )
    {
      ThreadTermEvent = -2147024809;
      goto LABEL_56;
    }
    v60 = 0x7FFFFFFF;
    v61 = a10;
    do
    {
      if ( !*v61 )
        break;
      ++v61;
      --v60;
    }
    while ( v60 );
    ThreadTermEvent = v60 == 0 ? 0x80070057 : 0;
    v62 = (0x7FFFFFFF - v60) & -(__int64)(v60 != 0);
    if ( !v60 )
      goto LABEL_56;
    v63 = v62 + 1;
    if ( v62 + 1 < v62 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    if ( v63 < 0 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    v64 = 2LL * (unsigned int)v63;
    v65 = HIDWORD(v63) << 33;
    if ( v65 + v64 < v64 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    if ( v65 + v64 )
    {
      v66 = (unsigned __int16 *)operator new(saturated_mul(v63, 2u));
      v36[4] = v66;
      if ( !v66 )
      {
        ThreadTermEvent = -2147024882;
        goto LABEL_56;
      }
      ThreadTermEvent = StringCchCopyW(v66, v63, a10);
      if ( ThreadTermEvent < 0 )
        goto LABEL_56;
    }
    v67 = a14;
    if ( !a14 )
    {
      ThreadTermEvent = -2147024809;
      goto LABEL_56;
    }
    v68 = 0x7FFFFFFF;
    do
    {
      if ( !*v67 )
        break;
      ++v67;
      --v68;
    }
    while ( v68 );
    ThreadTermEvent = v68 == 0 ? 0x80070057 : 0;
    v69 = (0x7FFFFFFF - v68) & -(__int64)(v68 != 0);
    if ( !v68 )
      goto LABEL_56;
    v70 = v69 + 1;
    if ( v69 + 1 < v69 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    if ( v70 < 0 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    v71 = 2LL * (unsigned int)v70;
    v72 = HIDWORD(v70) << 33;
    if ( v72 + v71 < v71 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    if ( v72 + v71 )
    {
      v73 = (unsigned __int16 *)operator new(saturated_mul(v70, 2u));
      v36[5] = v73;
      if ( !v73 )
      {
        ThreadTermEvent = -2147024882;
        goto LABEL_56;
      }
      ThreadTermEvent = StringCchCopyW(v73, v70, a14);
      if ( ThreadTermEvent < 0 )
        goto LABEL_56;
    }
    if ( a15 )
    {
      v74 = 0x7FFFFFFF;
      v75 = a15;
      do
      {
        if ( !*v75 )
          break;
        ++v75;
        --v74;
      }
      while ( v74 );
      ThreadTermEvent = v74 == 0 ? 0x80070057 : 0;
      v76 = (0x7FFFFFFF - v74) & -(__int64)(v74 != 0);
      if ( !v74 )
        goto LABEL_56;
      v77 = v76 + 1;
      if ( v76 + 1 < v76 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      if ( v77 < 0 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      v78 = 2LL * (unsigned int)v77;
      v79 = HIDWORD(v77) << 33;
      if ( v79 + v78 < v78 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      if ( v79 + v78 )
      {
        v80 = (unsigned __int16 *)operator new(saturated_mul(v77, 2u));
        v36[6] = v80;
        if ( !v80 )
        {
          ThreadTermEvent = -2147024882;
          goto LABEL_56;
        }
        ThreadTermEvent = StringCchCopyW(v80, v77, a15);
        if ( ThreadTermEvent < 0 )
          goto LABEL_56;
      }
    }
    v81 = a12;
    if ( a12 )
    {
      v82 = 0x7FFFFFFF;
      do
      {
        if ( !*v81 )
          break;
        ++v81;
        --v82;
      }
      while ( v82 );
      ThreadTermEvent = v82 == 0 ? 0x80070057 : 0;
      v83 = (0x7FFFFFFF - v82) & ((unsigned __int128)-(__int128)(unsigned __int64)v82 >> 64);
      if ( !v82 )
        goto LABEL_56;
      v84 = v83 + 1;
      if ( v83 + 1 < v83 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      if ( v84 < 0 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      v85 = 2LL * (unsigned int)v84;
      v86 = HIDWORD(v84) << 33;
      if ( v86 + v85 < v85 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      if ( v86 + v85 )
      {
        v87 = (unsigned __int16 *)operator new(saturated_mul(v84, 2u));
        v36[7] = v87;
        if ( !v87 )
        {
          ThreadTermEvent = -2147024882;
          goto LABEL_56;
        }
        ThreadTermEvent = StringCchCopyW(v87, v84, a12);
        if ( ThreadTermEvent < 0 )
          goto LABEL_56;
      }
    }
    *((_DWORD *)v36 + 19) = a11;
    *((_DWORD *)v36 + 17) = a2;
    *((_DWORD *)v36 + 18) = a3;
    *((_DWORD *)v36 + 16) = a1;
    v36[12] = v18;
    v18 = 0;
    ThreadTermEvent = GetThreadTermEvent(a1, 0, v36 + 13);
    if ( ThreadTermEvent >= 0 )
    {
      v88 = (void *)_beginthreadex(0, 0, AcquisitionProc, v36, 0, &ThrdAddr);
      if ( v88 )
      {
        SetThreadInfo(a1, 0, v88);
        goto LABEL_123;
      }
      v89 = GetLastError();
      ThreadTermEvent = v89;
      if ( v89 > 0 )
        ThreadTermEvent = (unsigned __int16)v89 | 0x80070000;
      if ( ThreadTermEvent >= 0 )
        ThreadTermEvent = -2147467259;
    }
    goto LABEL_56;
  }
LABEL_123:
  operator delete(Block);
  if ( v18 )
    CloseHandle(v18);
  _RTLTRACE("[msdrm]:-AcquireLicense");
  return (unsigned int)ThreadTermEvent;
}

```

## disassembly

```asm
0x180031b5c  mov     rax, rsp
0x180031b5f  mov     [rax+18h], r8d
0x180031b63  mov     [rax+10h], edx
0x180031b66  mov     [rax+8], ecx
0x180031b69  push    rbx
0x180031b6a  push    rsi
0x180031b6b  push    rdi
0x180031b6c  push    r12
0x180031b6e  push    r13
0x180031b70  push    r14
0x180031b72  push    r15
0x180031b74  sub     rsp, 80h
0x180031b7b  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180031b83  mov     r14, r9
0x180031b86  mov     ebx, ecx
0x180031b88  lea     rcx, aMsdrmAcquireli; "[msdrm]:+AcquireLicense"
0x180031b8f  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180031b94  xor     edi, edi
0x180031b96  mov     [rsp+0B8h+var_68], edi
0x180031b9a  mov     r15d, edi
0x180031b9d  mov     r12, [rsp+0B8h+arg_68]
0x180031ba5  mov     [rsp+0B8h+var_78], r12
0x180031baa  mov     rax, [rsp+0B8h+arg_60]
0x180031bb2  mov     [rsp+0B8h+var_80], rax
0x180031bb7  mov     r8, [rsp+0B8h+arg_58]
0x180031bbf  mov     [rsp+0B8h+var_88], r8
0x180031bc4  mov     eax, [rsp+0B8h+arg_50]
0x180031bcb  mov     dword ptr [rsp+0B8h+ThrdAddr], eax
0x180031bcf  mov     r13, [rsp+0B8h+arg_40]
0x180031bd7  mov     qword ptr [rsp+0B8h+InitFlag], r13
0x180031bdc  mov     r9, [rsp+0B8h+arg_38]
0x180031be4  mov     r8, [rsp+0B8h+arg_30]
0x180031bec  mov     rdx, [rsp+0B8h+arg_28]
0x180031bf4  lea     rcx, aMsdrmAcquireli_1; "[msdrm]: AcquireLicense : wszDPURL = %S"...
0x180031bfb  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180031c00  lea     ecx, [rdi+3Eh]; Size
0x180031c03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031c08  mov     [rsp+0B8h+Block], rax
0x180031c0d  test    rax, rax
0x180031c10  jnz     short loc_180031C1C
0x180031c12  mov     ebx, 8007000Eh
0x180031c17  jmp     loc_1800324F3
0x180031c1c  mov     r9d, ebx
0x180031c1f  lea     r8, ?g_wszLA_ReaderCancelEventName@@3QBGB; "UDRMReaderLicAcq_%lu"
0x180031c26  mov     edx, 1Fh; unsigned __int64
0x180031c2b  mov     rsi, rax
0x180031c2e  mov     rcx, rax; unsigned __int16 *
0x180031c31  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180031c36  mov     ebx, eax
0x180031c38  test    eax, eax
0x180031c3a  js      loc_1800324F3
0x180031c40  mov     r8, rsi; int
0x180031c43  mov     edx, 1; unsigned int
0x180031c48  call    ?OpenEventA@DRMOS@@YAPEAXKHPEBG@Z; DRMOS::OpenEventA(ulong,int,ushort const *)
0x180031c4d  mov     r15, rax
0x180031c50  mov     [rsp+0B8h+var_58], rax
0x180031c55  test    rax, rax
0x180031c58  jnz     short loc_180031C7E
0x180031c5a  call    cs:__imp_GetLastError
0x180031c60  mov     ebx, eax
0x180031c62  test    eax, eax
0x180031c64  jle     short loc_180031C6F
0x180031c66  movzx   ebx, ax
0x180031c69  or      ebx, 80070000h
0x180031c6f  mov     eax, 80004005h
0x180031c74  test    ebx, ebx
0x180031c76  cmovns  ebx, eax
0x180031c79  jmp     loc_1800324F3
0x180031c7e  mov     rcx, r15; hEvent
0x180031c81  test    byte ptr [rsp+0B8h+arg_50], 4
0x180031c89  jz      short loc_180031C96
0x180031c8b  call    cs:__imp_SetEvent
0x180031c91  jmp     loc_1800324F3
0x180031c96  call    cs:__imp_ResetEvent
0x180031c9c  test    r14, r14
0x180031c9f  jz      loc_1800324EE
0x180031ca5  xor     edx, edx
0x180031ca7  mov     rcx, r13
0x180031caa  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180031caf  test    al, al
0x180031cb1  jz      loc_1800324EE
0x180031cb7  xor     edx, edx
0x180031cb9  mov     rcx, [rsp+0B8h+arg_48]
0x180031cc1  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180031cc6  test    al, al
0x180031cc8  jz      loc_1800324EE
0x180031cce  cmp     [rsp+0B8h+arg_70], rdi
0x180031cd6  jz      short loc_180031CEF
0x180031cd8  xor     edx, edx
0x180031cda  mov     rcx, [rsp+0B8h+arg_70]
0x180031ce2  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180031ce7  test    al, al
0x180031ce9  jz      loc_1800324EE
0x180031cef  mov     rax, [rsp+0B8h+arg_58]
0x180031cf7  test    rax, rax
0x180031cfa  jz      short loc_180031D0E
0x180031cfc  xor     edx, edx
0x180031cfe  mov     rcx, rax
0x180031d01  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180031d06  test    al, al
0x180031d08  jz      loc_1800324EE
0x180031d0e  xor     edx, edx
0x180031d10  mov     rcx, [rsp+0B8h+arg_30]
0x180031d18  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180031d1d  test    al, al
0x180031d1f  jnz     short loc_180031D38
0x180031d21  xor     edx, edx
0x180031d23  mov     rcx, [rsp+0B8h+arg_38]
0x180031d2b  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180031d30  test    al, al
0x180031d32  jz      loc_1800324EE
0x180031d38  xor     edx, edx
0x180031d3a  mov     rcx, r12
0x180031d3d  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180031d42  test    al, al
0x180031d44  jz      loc_1800324EE
0x180031d4a  mov     ecx, 70h ; 'p'; Size
0x180031d4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031d54  mov     rsi, rax
0x180031d57  mov     [rsp+0B8h+var_60], rax
0x180031d5c  test    rax, rax
0x180031d5f  jz      loc_180031C12
0x180031d65  mov     [rax], rdi
0x180031d68  mov     [rax+8], rdi
0x180031d6c  mov     [rax+10h], rdi
0x180031d70  mov     [rax+20h], rdi
0x180031d74  mov     [rax+28h], rdi
0x180031d78  mov     [rax+30h], rdi
0x180031d7c  mov     [rax+38h], rdi
0x180031d80  mov     [rax+40h], rdi
0x180031d84  mov     [rax+48h], rdi
0x180031d88  mov     [rax+60h], rdi
0x180031d8c  mov     [rax+68h], rdi
0x180031d90  test    rax, rax
0x180031d93  jz      loc_180031C12
0x180031d99  mov     [rax+50h], r14
0x180031d9d  mov     rax, [rsp+0B8h+arg_78]
0x180031da5  mov     [rsi+58h], rax
0x180031da9  mov     [rsp+0B8h+var_60], rsi
0x180031dae  test    r13, r13
0x180031db1  jz      loc_1800324E4
0x180031db7  mov     r12d, 7FFFFFFFh
0x180031dbd  mov     edx, r12d
0x180031dc0  mov     rax, r13
0x180031dc3  cmp     [rax], di
0x180031dc6  jz      short loc_180031DD2
0x180031dc8  add     rax, 2
0x180031dcc  sub     rdx, 1
0x180031dd0  jnz     short loc_180031DC3
0x180031dd2  mov     rax, rdx
0x180031dd5  neg     rax
0x180031dd8  sbb     ebx, ebx
0x180031dda  not     ebx
0x180031ddc  mov     r14d, 80070057h
0x180031de2  and     ebx, r14d
0x180031de5  mov     rax, rdx
0x180031de8  mov     rcx, r12
0x180031deb  sub     rcx, rdx
0x180031dee  neg     rax
0x180031df1  sbb     r8, r8
0x180031df4  and     r8, rcx
0x180031df7  test    rdx, rdx
0x180031dfa  jz      loc_1800324E9
0x180031e00  lea     rbx, [r8+1]
0x180031e04  cmp     rbx, r8
0x180031e07  jb      loc_18003252C
0x180031e0d  mov     rcx, rbx
0x180031e10  shr     rcx, 20h
0x180031e14  mov     rax, rcx
0x180031e17  shr     rax, 1Fh
0x180031e1b  test    eax, eax
0x180031e1d  jnz     loc_180032532
0x180031e23  mov     eax, ebx
0x180031e25  add     rax, rax
0x180031e28  shl     rcx, 21h
0x180031e2c  lea     rdx, [rcx+rax]
0x180031e30  cmp     rdx, rax
0x180031e33  jb      loc_180032537
0x180031e39  test    rdx, rdx
0x180031e3c  jz      short loc_180031E84
0x180031e3e  mov     eax, 2
0x180031e43  mul     rbx
0x180031e46  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180031e4d  cmovb   rax, rcx
0x180031e51  mov     rcx, rax; Size
0x180031e54  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031e59  mov     [rsi], rax
0x180031e5c  test    rax, rax
0x180031e5f  jnz     short loc_180031E6B
0x180031e61  mov     ebx, 8007000Eh
0x180031e66  jmp     loc_180031FEE
0x180031e6b  mov     r8, r13; unsigned __int16 *
0x180031e6e  mov     rdx, rbx; unsigned __int64
0x180031e71  mov     rcx, rax; unsigned __int16 *
0x180031e74  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031e79  mov     ebx, eax
0x180031e7b  test    eax, eax
0x180031e7d  jns     short loc_180031E84
0x180031e7f  jmp     loc_180031FEE
0x180031e84  xor     edx, edx
0x180031e86  mov     r13, [rsp+0B8h+arg_30]
0x180031e8e  mov     rcx, r13
0x180031e91  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180031e96  test    al, al
0x180031e98  jz      loc_180031F69
0x180031e9e  test    r13, r13
0x180031ea1  jz      loc_180031FD8
0x180031ea7  mov     rdx, r12
0x180031eaa  mov     rax, r13
0x180031ead  cmp     [rax], di
0x180031eb0  jz      short loc_180031EBC
0x180031eb2  add     rax, 2
0x180031eb6  sub     rdx, 1
0x180031eba  jnz     short loc_180031EAD
0x180031ebc  mov     rax, rdx
0x180031ebf  neg     rax
0x180031ec2  sbb     ebx, ebx
0x180031ec4  not     ebx
0x180031ec6  and     ebx, r14d
0x180031ec9  mov     rax, rdx
0x180031ecc  mov     rcx, r12
0x180031ecf  sub     rcx, rdx
0x180031ed2  neg     rax
0x180031ed5  sbb     r8, r8
0x180031ed8  and     r8, rcx
0x180031edb  test    rdx, rdx
0x180031ede  jz      loc_180031FDB
0x180031ee4  lea     rbx, [r8+1]
0x180031ee8  cmp     rbx, r8
0x180031eeb  jb      loc_18003253D
0x180031ef1  mov     rcx, rbx
0x180031ef4  shr     rcx, 20h
0x180031ef8  mov     rax, rcx
0x180031efb  shr     rax, 1Fh
0x180031eff  test    eax, eax
0x180031f01  jnz     loc_180032542
0x180031f07  mov     eax, ebx
0x180031f09  add     rax, rax
0x180031f0c  shl     rcx, 21h
0x180031f10  lea     rdx, [rcx+rax]
0x180031f14  cmp     rdx, rax
0x180031f17  jb      loc_180032547
0x180031f1d  test    rdx, rdx
0x180031f20  jz      short loc_180031F69
0x180031f22  mov     eax, 2
0x180031f27  mul     rbx
0x180031f2a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180031f31  cmovb   rax, rcx
0x180031f35  mov     rcx, rax; Size
0x180031f38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031f3d  mov     [rsi+8], rax
0x180031f41  test    rax, rax
0x180031f44  jnz     short loc_180031F50
0x180031f46  mov     ebx, 8007000Eh
0x180031f4b  jmp     loc_180031FEE
0x180031f50  mov     r8, r13; unsigned __int16 *
0x180031f53  mov     rdx, rbx; unsigned __int64
0x180031f56  mov     rcx, rax; unsigned __int16 *
0x180031f59  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031f5e  mov     ebx, eax
0x180031f60  test    eax, eax
0x180031f62  jns     short loc_180031F69
0x180031f64  jmp     loc_180031FEE
0x180031f69  xor     edx, edx
0x180031f6b  mov     r13, [rsp+0B8h+arg_38]
0x180031f73  mov     rcx, r13
0x180031f76  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180031f7b  test    al, al
0x180031f7d  jz      loc_1800320C0
0x180031f83  test    r13, r13
0x180031f86  jz      loc_18003211D
0x180031f8c  mov     rdx, r12
0x180031f8f  mov     rax, r13
0x180031f92  cmp     [rax], di
0x180031f95  jz      short loc_180031FA1
0x180031f97  add     rax, 2
0x180031f9b  sub     rdx, 1
0x180031f9f  jnz     short loc_180031F92
0x180031fa1  mov     rax, rdx
0x180031fa4  neg     rax
0x180031fa7  sbb     ebx, ebx
0x180031fa9  not     ebx
0x180031fab  and     ebx, r14d
0x180031fae  mov     rax, rdx
0x180031fb1  mov     rcx, r12
0x180031fb4  sub     rcx, rdx
0x180031fb7  neg     rax
0x180031fba  sbb     r8, r8
0x180031fbd  and     r8, rcx
0x180031fc0  test    rdx, rdx
0x180031fc3  jz      loc_180032120
0x180031fc9  lea     rbx, [r8+1]
0x180031fcd  cmp     rbx, r8
0x180031fd0  jb      loc_18003254D
0x180031fd6  jmp     short loc_180032048
0x180031fd8  mov     ebx, r14d
0x180031fdb  jmp     short loc_180031FEE
0x180031fdd  mov     ebx, [rsp+0B8h+arg_20]
0x180031fe4  mov     r15, [rsp+0B8h+var_58]
0x180031fe9  mov     rsi, [rsp+0B8h+var_60]
  ... truncated ...
```
