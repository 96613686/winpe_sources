# KerbCreateAuthenticator

- ea: `0x180003890`
- end: `0x18000464f`
- name: `KerbCreateAuthenticator`
- size: `3519`
- prototype: `__int64 __fastcall(struct _KERB_ENCRYPTION_KEY *, unsigned int, union _LARGE_INTEGER *, __int16 *, unsigned __int16 *, __int64, __int64, __int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting`

## callers

- `0x180003630`

## callees

- `0x180002ba4`
- `0x180002ff4`
- `0x180003890`
- `0x180004760`
- `0x1800049e0`
- `0x180006350`
- `0x1800069a0`
- `0x1800093f0`
- `0x18006c048`
- `0x18006ccec`
- `0x18006fe20`
- `0x180070680`
- `0x18007108c`
- `0x1800744c3`
- `0x1800744cf`
- `0x180075008`
- `0x180077804`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004218`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004225`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004218`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004225`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180003fd8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000404c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800040ef`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180004168`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180003fd8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000404c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800040ef`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180004168`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003eb8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003eb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003ef1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800042a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800042b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800042db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003ef1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800042a0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800042b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800042db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ec8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ed3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ede`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003f1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004303`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000430e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ec8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ed3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ede`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003f1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004303`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000430e`
- `ntdll!RtlTimeToTimeFields` at `0x1800039a5`
- `ntdll!RtlTimeToTimeFields` at `0x1800039a5`
- `ntdll!RtlTimeFieldsToTime` at `0x180003ac2`
- `ntdll!RtlTimeFieldsToTime` at `0x180003ac2`
- `Kerb3961!__imp_Kerb3961Free` at `0x180004411`
- `Kerb3961!__imp_Kerb3961Free` at `0x180004455`
- `Kerb3961!__imp_Kerb3961Free` at `0x180004411`
- `Kerb3961!__imp_Kerb3961Free` at `0x180004455`
- `MSASN1!ASN1_CreateModule` at `0x180003c6a`
- `MSASN1!ASN1_CreateModule` at `0x180003c6a`
- `MSASN1!ASN1intx_free` at `0x180003ddc`
- `MSASN1!ASN1intx_free` at `0x180003ddc`
- `MSASN1!ASN1intx_setuint32` at `0x180003ae8`
- `MSASN1!ASN1intx_setuint32` at `0x180003ae8`
- `MSASN1!ASN1_CreateEncoder` at `0x180003c8a`
- `MSASN1!ASN1_CreateEncoder` at `0x180003c8a`
- `MSASN1!ASN1_FreeEncoded` at `0x180003d2c`
- `MSASN1!ASN1_FreeEncoded` at `0x180003d2c`
- `MSASN1!ASN1_Encode` at `0x180003cbe`
- `MSASN1!ASN1_Encode` at `0x180003cbe`
- `MSASN1!ASN1_CloseEncoder` at `0x180003e0c`
- `MSASN1!ASN1_CloseEncoder` at `0x180003e0c`

## pseudocode

```c
__int64 __fastcall KerbCreateAuthenticator(
        struct _KERB_ENCRYPTION_KEY *a1,
        unsigned int a2,
        union _LARGE_INTEGER *a3,
        __int16 *a4,
        unsigned __int16 *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        unsigned int a10,
        __int64 a11)
{
  __int16 *v11; // r14
  KerberosCryptoPolicy *v14; // r15
  union _LARGE_INTEGER v16; // rax
  unsigned __int32 v17; // ebx
  HLOCAL v18; // r15
  unsigned int v19; // edi
  _QWORD *v20; // rbx
  void *v21; // rcx
  _QWORD *v22; // rsi
  unsigned int v23; // r14d
  __int16 v24; // r8
  __int64 Module; // rax
  unsigned int v26; // eax
  int v27; // eax
  void *v28; // rbx
  unsigned int v29; // esi
  KerberosCryptoPolicy *v30; // rcx
  PVOID *v31; // r10
  KerberosCryptoPolicy *v32; // r13
  __int64 v33; // rax
  __int64 v34; // rsi
  unsigned int v35; // ecx
  __int64 v36; // rdx
  SIZE_T v37; // rsi
  HLOCAL v38; // rax
  unsigned int v39; // eax
  unsigned int v40; // eax
  int cbMultiByte; // edi
  CHAR *lpMultiByteStr; // rbx
  int v43; // eax
  __int64 v44; // rax
  KerberosCryptoPolicy *v45; // rdi
  __int64 v46; // r13
  __int16 *v47; // rsi
  unsigned int v48; // eax
  unsigned int v49; // eax
  int v50; // edi
  SIZE_T v51; // rdx
  CHAR *v52; // rbx
  int v53; // eax
  __int64 v54; // rax
  KerberosCryptoPolicy *v55; // rax
  DWORD v56; // ecx
  DWORD v57; // ecx
  unsigned int v58; // r14d
  CHAR *v59; // rax
  unsigned int v60; // r14d
  CHAR *v61; // rax
  __int64 v62; // r9
  CHAR *v63; // rax
  CHAR *v64; // rax
  unsigned int v65; // ebx
  unsigned int v66; // eax
  __int64 Key; // rax
  int v68; // ebx
  __int64 v69; // rdi
  void *v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rax
  KerberosCryptoPolicy *v73; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v74; // [rsp+58h] [rbp-A8h]
  unsigned int v75; // [rsp+60h] [rbp-A0h] BYREF
  union _LARGE_INTEGER Time; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v77[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _TIME_FIELDS v78; // [rsp+80h] [rbp-80h] BYREF
  __int128 v79; // [rsp+90h] [rbp-70h] BYREF
  __int64 v80; // [rsp+A0h] [rbp-60h]
  __int16 *v81; // [rsp+A8h] [rbp-58h]
  __int64 v82; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v83; // [rsp+B8h] [rbp-48h]
  int v84; // [rsp+C0h] [rbp-40h]
  __int64 v85; // [rsp+C8h] [rbp-38h]
  __int64 v86; // [rsp+D0h] [rbp-30h]
  KerberosCryptoPolicy *v87; // [rsp+D8h] [rbp-28h]
  __int64 v88; // [rsp+E0h] [rbp-20h]
  HLOCAL v89[2]; // [rsp+F0h] [rbp-10h] BYREF
  HLOCAL hMem[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v91; // [rsp+110h] [rbp+10h]
  __int128 Buf2; // [rsp+120h] [rbp+20h] BYREF
  __int128 v93; // [rsp+130h] [rbp+30h]
  __int128 v94; // [rsp+140h] [rbp+40h]
  __int128 v95; // [rsp+150h] [rbp+50h] BYREF
  __int128 v96; // [rsp+160h] [rbp+60h]
  struct _TIME_FIELDS Buf1; // [rsp+170h] [rbp+70h] BYREF
  int v98; // [rsp+180h] [rbp+80h]
  struct _TIME_FIELDS TimeFields; // [rsp+190h] [rbp+90h] BYREF

  v11 = a4;
  v81 = a4;
  v75 = a2;
  *(_QWORD *)&Buf1.Year = a6;
  v85 = a8;
  v86 = a9;
  v88 = a11;
  *(_OWORD *)v89 = 0;
  *(_OWORD *)hMem = 0;
  v91 = 0;
  Buf2 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  Time.QuadPart = 0;
  if ( !a1 )
    goto LABEL_4;
  KerberosCryptoPolicy::Create((__int64 **)&v73);
  v14 = v73;
  v87 = v73;
  if ( !v73 )
  {
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v73);
LABEL_4:
    v77[0] = 0;
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(v77);
    return 60;
  }
  KerberosCryptoPolicy::SetKey(v73, a1, 0);
  *((_BYTE *)v14 + 8) = 1;
  v73 = 0;
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v73);
  v77[0] = v14;
  v18 = 0;
  v74 = 0;
  *(_QWORD *)(a11 + 24) = 0;
  v89[0] = (HLOCAL)0x500000000LL;
  *(_OWORD *)hMem = 0;
  v91 = 0;
  Buf2 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v89[1] = 0;
  v39 = *a5;
  if ( (_WORD)v39 )
  {
    v40 = WideCharToMultiByte(0xFDE9u, 0, *((LPCWCH *)a5 + 1), v39 >> 1, 0, 0, 0, 0);
    cbMultiByte = v40;
    if ( !v40 )
      goto LABEL_18;
    if ( v40 > 0xFFFC )
    {
      v57 = 87;
    }
    else
    {
      if ( v40 + 1 >= v40 )
      {
        if ( KerbGlobalPackageState == 1 )
        {
          lpMultiByteStr = (CHAR *)((__int64 (*)(void))LsaFunctions->AllocateLsaHeap)();
          if ( !lpMultiByteStr )
            goto LABEL_18;
        }
        else
        {
          v60 = v40 + 1;
          v61 = (CHAR *)LocalAlloc(0, v40 + 1);
          lpMultiByteStr = v61;
          if ( !v61 )
            goto LABEL_18;
          memset_0(v61, 0, v60);
          v11 = v81;
        }
        v43 = WideCharToMultiByte(0xFDE9u, 0, *((LPCWCH *)a5 + 1), *a5 >> 1, lpMultiByteStr, cbMultiByte, 0, 0);
        if ( !v43 )
        {
          if ( KerbGlobalPackageState == 1 )
            ((void (__fastcall *)(CHAR *))LsaFunctions->FreeLsaHeap)(lpMultiByteStr);
          else
            LocalFree(lpMultiByteStr);
          goto LABEL_18;
        }
        lpMultiByteStr[v43] = 0;
        goto LABEL_82;
      }
      v57 = 534;
    }
    SetLastError(v57);
    goto LABEL_18;
  }
  v63 = (CHAR *)MIDL_user_allocate(1u);
  lpMultiByteStr = v63;
  if ( !v63 )
    goto LABEL_18;
  *v63 = 0;
LABEL_82:
  v44 = -1;
  do
    ++v44;
  while ( lpMultiByteStr[v44] );
  if ( (unsigned int)v44 <= 0xFFFD )
  {
    v89[1] = lpMultiByteStr;
    v78 = 0;
    LODWORD(hMem[0]) = *v11;
    hMem[1] = 0;
    v45 = (KerberosCryptoPolicy *)&hMem[1];
    v73 = (KerberosCryptoPolicy *)&hMem[1];
    v46 = 0;
    while ( (unsigned int)v18 < (unsigned __int16)v11[1] )
    {
      *(_DWORD *)&TimeFields.Day = 0;
      v47 = &v11[8 * (unsigned int)v18];
      v48 = (unsigned __int16)v47[4];
      if ( (_WORD)v48 )
      {
        v49 = WideCharToMultiByte(0xFDE9u, 0, *((LPCWCH *)v47 + 2), v48 >> 1, 0, 0, 0, 0);
        v50 = v49;
        if ( !v49 )
          goto LABEL_108;
        if ( v49 > 0xFFFC )
        {
          v56 = 87;
          goto LABEL_103;
        }
        v51 = v49 + 1;
        if ( (unsigned int)v51 < v49 )
        {
          v56 = 534;
LABEL_103:
          SetLastError(v56);
LABEL_108:
          v19 = 60;
          KerbFreePrincipalName(hMem);
          if ( v46 )
            KerbFree(v46);
          v18 = v74;
          goto LABEL_19;
        }
        if ( KerbGlobalPackageState == 1 )
        {
          v52 = (CHAR *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocateLsaHeap)((unsigned int)v51);
          if ( !v52 )
            goto LABEL_108;
        }
        else
        {
          v58 = v49 + 1;
          v59 = (CHAR *)LocalAlloc(0, v51);
          v52 = v59;
          if ( !v59 )
            goto LABEL_108;
          memset_0(v59, 0, v58);
          v11 = v81;
        }
        v53 = WideCharToMultiByte(0xFDE9u, 0, *((LPCWCH *)v47 + 2), (unsigned __int16)v47[4] >> 1, v52, v50, 0, 0);
        if ( !v53 )
        {
          if ( KerbGlobalPackageState == 1 )
            ((void (__fastcall *)(CHAR *))LsaFunctions->FreeLsaHeap)(v52);
          else
            LocalFree(v52);
          goto LABEL_108;
        }
        v52[v53] = 0;
        *(_QWORD *)&TimeFields.Minute = v52;
        v45 = v73;
      }
      else
      {
        v64 = (CHAR *)MIDL_user_allocate(1u);
        v52 = v64;
        if ( !v64 )
          goto LABEL_108;
        *v64 = 0;
        *(_QWORD *)&TimeFields.Minute = v64;
      }
      *(_QWORD *)&TimeFields.Minute = v52;
      v54 = -1;
      do
        ++v54;
      while ( v52[v54] );
      if ( (unsigned int)v54 > 0xFFFD )
        goto LABEL_108;
      TimeFields.Year = v54;
      TimeFields.Month = v54 + 1;
      v78 = TimeFields;
      if ( KerbGlobalPackageState == 1 )
        v55 = (KerberosCryptoPolicy *)((__int64 (__fastcall *)(__int64))LsaFunctions->AllocateLsaHeap)(16);
      else
        v55 = (KerberosCryptoPolicy *)LocalAlloc(0, 0x10u);
      if ( !v55 )
      {
        v46 = *(_QWORD *)&v78.Minute;
        goto LABEL_108;
      }
      *((_QWORD *)v55 + 1) = v52;
      *(_QWORD *)v55 = 0;
      *(_QWORD *)v45 = v55;
      v45 = v55;
      v73 = v55;
      v46 = 0;
      LODWORD(v18) = (_DWORD)v18 + 1;
    }
    if ( *(_QWORD *)&Buf1.Year )
    {
      v16 = *(union _LARGE_INTEGER *)(*(_QWORD *)&Buf1.Year + 8LL);
      Time = v16;
    }
    else
    {
      GetSystemTimeAsFileTime((LPFILETIME)&Time);
      v16 = Time;
    }
    TimeFields = 0;
    if ( v16.QuadPart )
    {
      RtlTimeToTimeFields(&Time, &TimeFields);
      if ( TimeFields.Year > 2100 )
        WORD6(Buf2) = 2100;
      else
        WORD6(Buf2) = TimeFields.Year;
      BYTE14(Buf2) = TimeFields.Month;
      HIBYTE(Buf2) = TimeFields.Day;
      LOBYTE(v93) = TimeFields.Hour;
      BYTE1(v93) = TimeFields.Minute;
      BYTE2(v93) = TimeFields.Second;
      WORD2(v93) = 0;
      WORD4(v93) = 0;
    }
    else
    {
      *(_QWORD *)&v93 = 0;
      WORD4(v93) = 0;
      HIDWORD(Buf2) = 16844722;
    }
    BYTE6(v93) = 1;
    v17 = _InterlockedIncrement(&LastuSec) % 0xF4240u;
    DWORD2(Buf2) = v17;
    if ( a3 )
    {
      a3->QuadPart = 0;
      *(_QWORD *)&Buf1.Year = 0;
      *(_DWORD *)&Buf1.Minute = 0x10000;
      Buf1.Milliseconds = 0;
      if ( memcmp_0(&Buf1, (char *)&Buf2 + 12, 0xEu) )
      {
        *(_DWORD *)&Buf1.Year = 16844722;
        if ( memcmp_0(&Buf1, (char *)&Buf2 + 12, 0xEu) )
        {
          Buf1.Year = WORD6(Buf2);
          Buf1.Month = BYTE14(Buf2);
          Buf1.Day = HIBYTE(Buf2);
          Buf1.Hour = (unsigned __int8)v93;
          Buf1.Minute = BYTE1(v93);
          Buf1.Second = BYTE2(v93);
          *(_DWORD *)&Buf1.Milliseconds = WORD2(v93);
          if ( RtlTimeFieldsToTime(&Buf1, a3) )
            a3->QuadPart += (int)(10 * v17);
          else
            a3->QuadPart = 0;
        }
      }
    }
    LOWORD(v89[0]) |= 0x20u;
    ASN1intx_setuint32((char *)&v95 + 8, v75);
    if ( !(_QWORD)v96 )
    {
      v18 = v74;
      goto LABEL_18;
    }
    v23 = 0;
    v24 = (__int16)v89[0];
    if ( a7 )
    {
      v24 = LOWORD(v89[0]) | 0x40;
      LOWORD(v89[0]) |= 0x40u;
      v79 = 0;
      v80 = 0;
      v35 = *(_DWORD *)(a7 + 16);
      v36 = *(_QWORD *)(a7 + 24);
      *(_QWORD *)&v94 = *(unsigned int *)(a7 + 12);
      *((_QWORD *)&v94 + 1) = v35;
      *(_QWORD *)&v95 = v36;
    }
    if ( v85 )
    {
      v24 |= 0x10u;
      LOWORD(v89[0]) = v24;
      *((_QWORD *)&v96 + 1) = v85;
    }
    if ( v86 )
    {
      v91 = *(_OWORD *)v86;
      *(_QWORD *)&Buf2 = *(_QWORD *)(v86 + 16);
      LOWORD(v89[0]) = v24 | 0x80;
    }
    v73 = 0;
    if ( fKRB5ModuleStarted )
    {
      Module = KRB5_Module;
    }
    else
    {
      fKRB5ModuleStarted = 1;
      Module = ASN1_CreateModule(
                 0x10000,
                 1024,
                 4096,
                 81,
                 off_1800F62D0,
                 off_1800F6040,
                 off_1800F6560,
                 qword_1800FE8B0,
                 895644267);
      KRB5_Module = Module;
    }
    v26 = ASN1_CreateEncoder(Module, &v73, 0, 0, 0);
    if ( v26 )
    {
      v31 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v26);
        v19 = 60;
        v29 = 60;
        goto LABEL_49;
      }
    }
    else
    {
      v27 = ASN1_Encode(v73, v89, 52, 16, 0, 0);
      if ( v27 >= 0 )
      {
        v19 = 60;
        if ( KerbGlobalPackageState == 1 )
        {
          v28 = (void *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocateLsaHeap)(*((unsigned int *)v73 + 7));
        }
        else
        {
          v37 = *((unsigned int *)v73 + 7);
          v38 = LocalAlloc(0, v37);
          v28 = v38;
          if ( v38 )
          {
            memset_0(v38, 0, v37);
            v74 = v28;
            goto LABEL_47;
          }
        }
        v74 = v28;
        if ( !v28 )
        {
          v29 = 60;
          v30 = v73;
          goto LABEL_48;
        }
LABEL_47:
        v29 = 0;
        memcpy_0(v28, *((const void **)v73 + 2), *((unsigned int *)v73 + 7));
        v30 = v73;
        v23 = *((_DWORD *)v73 + 7);
LABEL_48:
        ASN1_FreeEncoded(v30, *((_QWORD *)v30 + 2));
LABEL_49:
        v31 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_50;
      }
      v31 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          &WPP_c655c859b2e13de8f31f421519d58447_Traceguids,
          (unsigned int)v27);
        v31 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    v19 = 60;
    v29 = 60;
LABEL_50:
    if ( v73 )
    {
      ASN1_CloseEncoder();
      v31 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v29 )
    {
      v19 = v29;
      if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 1) != 0 )
        WPP_SF_D(v31[2], 30, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v29);
      v18 = v74;
      goto LABEL_19;
    }
    v32 = v87;
    v33 = KerberosCryptoPolicy::SelectEncryptionAlgorithm(v87, a10);
    v34 = v33;
    if ( v33 )
    {
      v65 = *((_DWORD *)v32 + 14);
      v66 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 216LL))(v33);
      v75 = 0;
      Key = KerberosCryptoPolicy::GetKey(v32, v66, a10, v65);
      if ( Key )
      {
        *(_QWORD *)&v78.Year = *(unsigned int *)(Key + 16);
        *(_QWORD *)&v78.Minute = *(_QWORD *)(Key + 24);
        (*(void (__fastcall **)(__int64, __int128 *, struct _TIME_FIELDS *, _QWORD, int, unsigned int *))(*(_QWORD *)v34 + 168LL))(
          v34,
          &v79,
          &v78,
          a10,
          1,
          &v75);
        if ( (int)v80 >= 0 )
        {
          LOBYTE(v62) = 1;
          (*(void (__fastcall **)(__int64, __int64 *, __int128 *, __int64))(*(_QWORD *)v34 + 184LL))(
            v34,
            &v82,
            &v79,
            v62);
          if ( v84 >= 0 )
          {
            v78 = (struct _TIME_FIELDS)0LL;
            *(_QWORD *)&TimeFields.Year = v23;
            v18 = v74;
            *(_QWORD *)&TimeFields.Minute = v74;
            (*(void (__fastcall **)(__int64, struct _TIME_FIELDS *, __int128 *, __int64 *, struct _TIME_FIELDS *, struct _TIME_FIELDS *))(*(_QWORD *)v34 + 200LL))(
              v34,
              &Buf1,
              &v79,
              &v82,
              &TimeFields,
              &v78);
            if ( v98 >= 0 )
            {
              v68 = *(_DWORD *)&Buf1.Year;
              v69 = v88;
              if ( *(_DWORD *)(v88 + 16) >= *(_DWORD *)&Buf1.Year && (v70 = *(void **)(v88 + 24)) != 0 )
              {
                memcpy_0(v70, *(const void **)&Buf1.Minute, *(unsigned int *)&Buf1.Year);
              }
              else
              {
                v71 = *(_QWORD *)(v88 + 24);
                if ( v71 )
                  KerbFree(v71);
                v72 = *(_QWORD *)&Buf1.Minute;
                *(_QWORD *)&Buf1.Minute = 0;
                *(_QWORD *)&Buf1.Year = 0;
                v98 = -1073741823;
                *(_QWORD *)(v69 + 24) = v72;
              }
              *(_DWORD *)(v69 + 16) = v68;
              *(_DWORD *)(v69 + 4) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v79 + 216LL))(v79);
              if ( *(_QWORD *)&Buf1.Minute )
                Kerb3961Free();
              if ( v83 )
                 Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}(v82);
              Kerb3961::SpecificKeyReturn::~SpecificKeyReturn((Kerb3961::SpecificKeyReturn *)&v79);
              v19 = 0;
              goto LABEL_19;
            }
            if ( *(_QWORD *)&Buf1.Minute )
              Kerb3961Free();
            if ( v83 )
               Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}(v82);
            Kerb3961::SpecificKeyReturn::~SpecificKeyReturn((Kerb3961::SpecificKeyReturn *)&v79);
            goto LABEL_55;
          }
          if ( v83 )
             Kerb3961::EncryptionAlgorithm::`vcall'{176,{flat}}(v82);
        }
        Kerb3961::SpecificKeyReturn::~SpecificKeyReturn((Kerb3961::SpecificKeyReturn *)&v79);
        v18 = v74;
      }
      else
      {
        v19 = 14;
        v18 = v74;
      }
    }
    else
    {
      v19 = 14;
      v18 = v74;
    }
LABEL_55:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v19);
    goto LABEL_19;
  }
LABEL_18:
  v19 = 60;
LABEL_19:
  v20 = hMem[1];
  if ( hMem[1] )
  {
    do
    {
      v21 = (void *)v20[1];
      if ( v21 )
      {
        if ( KerbGlobalPackageState == 1 )
          ((void (*)(void))LsaFunctions->FreeLsaHeap)();
        else
          LocalFree(v21);
      }
      v22 = (_QWORD *)*v20;
      if ( KerbGlobalPackageState == 1 )
        ((void (__fastcall *)(_QWORD *))LsaFunctions->FreeLsaHeap)(v20);
      else
        LocalFree(v20);
      v20 = v22;
    }
    while ( v22 );
  }
  hMem[1] = 0;
  if ( v89[1] )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
    else
      LocalFree(v89[1]);
    v89[1] = 0;
  }
  if ( (_QWORD)v96 )
    ASN1intx_free((char *)&v95 + 8);
  if ( v18 )
  {
    if ( KerbGlobalPackageState == 1 )
      ((void (__fastcall *)(HLOCAL))LsaFunctions->FreeLsaHeap)(v18);
    else
      LocalFree(v18);
  }
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(v77);
  return v19;
}

```

## disassembly

```asm
0x180003890  push    rbp
0x180003892  push    rbx
0x180003893  push    rsi
0x180003894  push    rdi
0x180003895  push    r12
0x180003897  push    r13
0x180003899  push    r14
0x18000389b  push    r15
0x18000389d  lea     rbp, [rsp-0B8h]
0x1800038a5  sub     rsp, 1B8h
0x1800038ac  mov     rax, cs:__security_cookie
0x1800038b3  xor     rax, rsp
0x1800038b6  mov     [rbp+0F0h+var_50], rax
0x1800038bd  mov     r14, r9
0x1800038c0  mov     [rbp+0F0h+var_148], r9
0x1800038c4  mov     r12, r8
0x1800038c7  mov     [rsp+1F0h+var_190], edx
0x1800038cb  mov     rbx, rcx
0x1800038ce  mov     rsi, [rbp+0F0h+arg_20]
0x1800038d5  mov     rax, [rbp+0F0h+arg_28]
0x1800038dc  mov     [rbp+0F0h+Buf1], rax
0x1800038e0  mov     rax, [rbp+0F0h+arg_38]
0x1800038e7  mov     [rbp+0F0h+var_128], rax
0x1800038eb  mov     rax, [rbp+0F0h+arg_40]
0x1800038f2  mov     [rbp+0F0h+var_120], rax
0x1800038f6  mov     rdi, [rbp+0F0h+arg_50]
0x1800038fd  mov     [rbp+0F0h+var_110], rdi
0x180003901  xorps   xmm0, xmm0
0x180003904  movups  xmmword ptr [rbp+0F0h+var_100], xmm0
0x180003908  movups  xmmword ptr [rbp+0F0h+hMem], xmm0
0x18000390c  movups  [rbp+0F0h+var_E0], xmm0
0x180003910  movups  [rbp+0F0h+Buf2], xmm0
0x180003914  movups  [rbp+0F0h+var_C0], xmm0
0x180003918  movups  [rbp+0F0h+var_B0], xmm0
0x18000391c  movups  [rbp+0F0h+var_A0], xmm0
0x180003920  movups  [rbp+0F0h+var_90], xmm0
0x180003924  xor     r13d, r13d
0x180003927  mov     qword ptr [rsp+1F0h+Time], r13
0x18000392c  test    rcx, rcx
0x18000392f  jz      short loc_180003957
0x180003931  lea     rcx, [rsp+1F0h+var_1A0]
0x180003936  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x18000393b  mov     r15, [rsp+1F0h+var_1A0]
0x180003940  mov     [rbp+0F0h+var_118], r15
0x180003944  test    r15, r15
0x180003947  jnz     loc_180003F3D
0x18000394d  lea     rcx, [rsp+1F0h+var_1A0]
0x180003952  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180003957  mov     [rsp+1F0h+var_180], r13
0x18000395c  lea     rcx, [rsp+1F0h+var_180]
0x180003961  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180003966  mov     eax, 3Ch ; '<'
0x18000396b  jmp     loc_180003BAB
0x180003970  mov     rax, [rbp+0F0h+Buf1]
0x180003974  test    rax, rax
0x180003977  jz      loc_180003EB3
0x18000397d  mov     rax, [rax+8]
0x180003981  mov     qword ptr [rsp+1F0h+Time], rax
0x180003986  xorps   xmm0, xmm0
0x180003989  movups  xmmword ptr [rbp+0F0h+TimeFields.Year], xmm0
0x180003990  test    rax, rax
0x180003993  jz      loc_180003DBE
0x180003999  lea     rdx, [rbp+0F0h+TimeFields]; TimeFields
0x1800039a0  lea     rcx, [rsp+1F0h+Time]; Time
0x1800039a5  call    cs:__imp_RtlTimeToTimeFields
0x1800039ab  mov     ecx, 834h
0x1800039b0  movzx   eax, [rbp+0F0h+TimeFields.Year]
0x1800039b7  cmp     ax, cx
0x1800039ba  jg      loc_180003DB5
0x1800039c0  mov     word ptr [rbp+0F0h+Buf2+0Ch], ax
0x1800039c4  movzx   eax, byte ptr [rbp+0F0h+TimeFields.Month]
0x1800039cb  mov     byte ptr [rbp+0F0h+Buf2+0Eh], al
0x1800039ce  movzx   eax, byte ptr [rbp+0F0h+TimeFields.Day]
0x1800039d5  mov     byte ptr [rbp+0F0h+Buf2+0Fh], al
0x1800039d8  movzx   eax, byte ptr [rbp+0F0h+TimeFields.Hour]
0x1800039df  mov     byte ptr [rbp+0F0h+var_C0], al
0x1800039e2  movzx   eax, byte ptr [rbp+0F0h+TimeFields.Minute]
0x1800039e9  mov     byte ptr [rbp+0F0h+var_C0+1], al
0x1800039ec  movzx   eax, byte ptr [rbp+0F0h+TimeFields.Second]
0x1800039f3  mov     byte ptr [rbp+0F0h+var_C0+2], al
0x1800039f6  xor     r13d, r13d
0x1800039f9  mov     word ptr [rbp+0F0h+var_C0+4], r13w
0x1800039fe  mov     word ptr [rbp+0F0h+var_C0+8], r13w
0x180003a03  mov     byte ptr [rbp+0F0h+var_C0+6], 1
0x180003a07  mov     ebx, 1
0x180003a0c  lock xadd cs:?LastuSec@@3JC, ebx; long volatile LastuSec
0x180003a14  inc     ebx
0x180003a16  mov     eax, 431BDE83h
0x180003a1b  mul     ebx
0x180003a1d  shr     edx, 12h
0x180003a20  imul    eax, edx, 0F4240h
0x180003a26  sub     ebx, eax
0x180003a28  mov     dword ptr [rbp+0F0h+Buf2+8], ebx
0x180003a2b  test    r12, r12
0x180003a2e  jz      loc_180003ADB
0x180003a34  mov     [r12], r13
0x180003a38  xor     eax, eax
0x180003a3a  mov     [rbp+0F0h+Buf1], rax
0x180003a3e  mov     dword ptr [rbp+0F0h+Src], eax
0x180003a41  mov     word ptr [rbp+0F0h+Src+4], ax
0x180003a45  mov     byte ptr [rbp+0F0h+Src+2], 1
0x180003a49  mov     r8d, 0Eh; Size
0x180003a4f  lea     rdx, [rbp+0F0h+Buf2+0Ch]; Buf2
0x180003a53  lea     rcx, [rbp+0F0h+Buf1]; Buf1
0x180003a57  call    memcmp_0
0x180003a5c  test    eax, eax
0x180003a5e  jz      short loc_180003ADB
0x180003a60  mov     dword ptr [rbp+0F0h+Buf1], 10107B2h
0x180003a67  mov     r8d, 0Eh; Size
0x180003a6d  lea     rdx, [rbp+0F0h+Buf2+0Ch]; Buf2
0x180003a71  lea     rcx, [rbp+0F0h+Buf1]; Buf1
0x180003a75  call    memcmp_0
0x180003a7a  test    eax, eax
0x180003a7c  jz      short loc_180003ADB
0x180003a7e  movzx   eax, word ptr [rbp+0F0h+Buf2+0Ch]
0x180003a82  mov     word ptr [rbp+0F0h+Buf1], ax
0x180003a86  movzx   eax, byte ptr [rbp+0F0h+Buf2+0Eh]
0x180003a8a  mov     word ptr [rbp+0F0h+Buf1+2], ax
0x180003a8e  movzx   eax, byte ptr [rbp+0F0h+Buf2+0Fh]
0x180003a92  mov     word ptr [rbp+0F0h+Buf1+4], ax
0x180003a96  movzx   eax, byte ptr [rbp+0F0h+var_C0]
0x180003a9a  mov     word ptr [rbp+0F0h+Buf1+6], ax
0x180003a9e  movzx   eax, byte ptr [rbp+0F0h+var_C0+1]
0x180003aa2  mov     word ptr [rbp+0F0h+Src], ax
0x180003aa6  movzx   eax, byte ptr [rbp+0F0h+var_C0+2]
0x180003aaa  mov     word ptr [rbp+0F0h+Src+2], ax
0x180003aae  movzx   eax, word ptr [rbp+0F0h+var_C0+4]
0x180003ab2  mov     word ptr [rbp+0F0h+Src+4], ax
0x180003ab6  mov     word ptr [rbp+0F0h+Src+6], r13w
0x180003abb  mov     rdx, r12; Time
0x180003abe  lea     rcx, [rbp+0F0h+Buf1]; TimeFields
0x180003ac2  call    cs:__imp_RtlTimeFieldsToTime
0x180003ac8  test    al, al
0x180003aca  jz      loc_180003EAA
0x180003ad0  lea     eax, [rbx+rbx*4]
0x180003ad3  add     eax, eax
0x180003ad5  cdqe
0x180003ad7  add     [r12], rax
0x180003adb  or      word ptr [rbp+0F0h+var_100], 20h
0x180003ae0  mov     edx, [rsp+1F0h+var_190]
0x180003ae4  lea     rcx, [rbp+0F0h+var_A0+8]
0x180003ae8  call    cs:__imp_ASN1intx_setuint32
0x180003aee  cmp     qword ptr [rbp+0F0h+var_90], 0
0x180003af3  jnz     loc_180003BCE
0x180003af9  mov     r15, [rsp+1F0h+var_198]
0x180003afe  mov     edi, 3Ch ; '<'
0x180003b03  mov     rbx, [rbp+0F0h+hMem+8]
0x180003b07  test    rbx, rbx
0x180003b0a  jz      short loc_180003B5D
0x180003b0c  mov     rcx, [rbx+8]; hMem
0x180003b10  test    rcx, rcx
0x180003b13  jz      short loc_180003B32
0x180003b15  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180003b1c  jnz     loc_180003EC8
0x180003b22  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180003b29  mov     rax, [rax+30h]
0x180003b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b32  mov     rsi, [rbx]
0x180003b35  mov     rcx, rbx; hMem
0x180003b38  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180003b3f  jnz     loc_180003ED3
0x180003b45  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180003b4c  mov     rax, [rax+30h]
0x180003b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b55  mov     rbx, rsi
0x180003b58  test    rsi, rsi
0x180003b5b  jnz     short loc_180003B0C
0x180003b5d  mov     [rbp+0F0h+hMem+8], r13
0x180003b61  mov     rcx, [rbp+0F0h+var_100+8]; hMem
0x180003b65  test    rcx, rcx
0x180003b68  jz      short loc_180003B8B
0x180003b6a  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180003b71  jnz     loc_180003EDE
0x180003b77  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180003b7e  mov     rax, [rax+30h]
0x180003b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b87  mov     [rbp+0F0h+var_100+8], r13
0x180003b8b  cmp     qword ptr [rbp+0F0h+var_90], 0
0x180003b90  jnz     loc_180003DD8
0x180003b96  test    r15, r15
0x180003b99  jnz     loc_180003DE7
0x180003b9f  lea     rcx, [rsp+1F0h+var_180]
0x180003ba4  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180003ba9  mov     eax, edi
0x180003bab  mov     rcx, [rbp+0F0h+var_50]
0x180003bb2  xor     rcx, rsp; StackCookie
0x180003bb5  call    __security_check_cookie
0x180003bba  add     rsp, 1B8h
0x180003bc1  pop     r15
0x180003bc3  pop     r14
0x180003bc5  pop     r13
0x180003bc7  pop     r12
0x180003bc9  pop     rdi
0x180003bca  pop     rsi
0x180003bcb  pop     rbx
0x180003bcc  pop     rbp
0x180003bcd  retn
0x180003bce  mov     r14d, r13d
0x180003bd1  mov     rdx, [rbp+0F0h+arg_30]
0x180003bd8  movzx   r8d, word ptr [rbp+0F0h+var_100]
0x180003bdd  test    rdx, rdx
0x180003be0  jnz     loc_180003E3A
0x180003be6  mov     rax, [rbp+0F0h+var_128]
0x180003bea  test    rax, rax
0x180003bed  jnz     loc_180003E76
0x180003bf3  mov     rax, [rbp+0F0h+var_120]
0x180003bf7  test    rax, rax
0x180003bfa  jnz     loc_180003E89
0x180003c00  mov     [rsp+1F0h+var_1A0], r13
0x180003c05  cmp     cs:?fKRB5ModuleStarted@@3HA, 0; int fKRB5ModuleStarted
0x180003c0c  jnz     loc_180003F31
0x180003c12  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x180003c1c  mov     [rsp+1F0h+var_1B0], 3562726Bh
0x180003c24  lea     rax, qword_1800FE8B0
0x180003c2b  mov     [rsp+1F0h+lpUsedDefaultChar], rax
0x180003c30  lea     rax, off_1800F6560
0x180003c37  mov     [rsp+1F0h+lpDefaultChar], rax
0x180003c3c  lea     rax, off_1800F6040
0x180003c43  mov     qword ptr [rsp+1F0h+cbMultiByte], rax
0x180003c48  lea     rax, off_1800F62D0
0x180003c4f  mov     [rsp+1F0h+lpMultiByteStr], rax
0x180003c54  mov     edx, 400h
0x180003c59  mov     ecx, 10000h
0x180003c5e  mov     r9d, 51h ; 'Q'
0x180003c64  mov     r8d, 1000h
0x180003c6a  call    cs:__imp_ASN1_CreateModule
0x180003c70  mov     cs:KRB5_Module, rax
0x180003c77  mov     [rsp+1F0h+lpMultiByteStr], r13
0x180003c7c  xor     r9d, r9d
0x180003c7f  xor     r8d, r8d
0x180003c82  lea     rdx, [rsp+1F0h+var_1A0]
0x180003c87  mov     rcx, rax
0x180003c8a  call    cs:__imp_ASN1_CreateEncoder
0x180003c90  lea     r12, WPP_GLOBAL_Control
0x180003c97  test    eax, eax
0x180003c99  jnz     loc_1800044DE
0x180003c9f  mov     [rsp+1F0h+cbMultiByte], r13d
0x180003ca4  mov     [rsp+1F0h+lpMultiByteStr], r13
0x180003ca9  mov     r9d, 10h
0x180003caf  mov     r8d, 34h ; '4'
0x180003cb5  lea     rdx, [rbp+0F0h+var_100]
0x180003cb9  mov     rcx, [rsp+1F0h+var_1A0]
0x180003cbe  call    cs:__imp_ASN1_Encode
0x180003cc4  test    eax, eax
0x180003cc6  js      loc_180003E1E
0x180003ccc  mov     rax, [rsp+1F0h+var_1A0]
0x180003cd1  mov     ecx, [rax+1Ch]
0x180003cd4  mov     edi, 3Ch ; '<'
0x180003cd9  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x180003ce0  jnz     loc_180003EE9
0x180003ce6  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180003ced  mov     rax, [rax+28h]
0x180003cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cf6  mov     rbx, rax
0x180003cf9  mov     [rsp+1F0h+var_198], rbx
0x180003cfe  test    rbx, rbx
0x180003d01  jz      loc_180003F25
0x180003d07  mov     esi, r13d
0x180003d0a  mov     rdx, [rsp+1F0h+var_1A0]
0x180003d0f  mov     r8d, [rdx+1Ch]; Size
0x180003d13  mov     rdx, [rdx+10h]; Src
0x180003d17  mov     rcx, rbx; void *
0x180003d1a  call    memcpy_0
0x180003d1f  mov     rcx, [rsp+1F0h+var_1A0]
0x180003d24  mov     r14d, [rcx+1Ch]
0x180003d28  mov     rdx, [rcx+10h]
0x180003d2c  call    cs:__imp_ASN1_FreeEncoded
0x180003d32  mov     r10, cs:WPP_GLOBAL_Control
0x180003d39  mov     rcx, [rsp+1F0h+var_1A0]
0x180003d3e  test    rcx, rcx
0x180003d41  jnz     loc_180003E0C
0x180003d47  test    esi, esi
0x180003d49  jnz     loc_18000454C
0x180003d4f  mov     r15d, [rbp+0F0h+arg_48]
0x180003d56  mov     edx, r15d
0x180003d59  mov     r13, [rbp+0F0h+var_118]
0x180003d5d  mov     rcx, r13
0x180003d60  call    ?SelectEncryptionAlgorithm@KerberosCryptoPolicy@@QEAAPEAUEncryptionAlgorithm@Kerb3961@@W4KeyUsage@3@W4KdcPrincipalKeyState@@@Z; KerberosCryptoPolicy::SelectEncryptionAlgorithm(Kerb3961::KeyUsage,KdcPrincipalKeyState)
0x180003d65  mov     rsi, rax
0x180003d68  test    rax, rax
0x180003d6b  jnz     loc_18000457C
0x180003d71  mov     edi, 0Eh
0x180003d76  mov     r15, [rsp+1F0h+var_198]
0x180003d7b  xor     r13d, r13d
0x180003d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d85  cmp     rcx, r12
0x180003d88  jz      loc_180003B03
0x180003d8e  test    byte ptr [rcx+1Ch], 1
0x180003d92  jz      loc_180003B03
0x180003d98  mov     edx, 1Fh
0x180003d9d  mov     r9d, edi
0x180003da0  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180003da7  mov     rcx, [rcx+10h]
0x180003dab  call    WPP_SF_D
0x180003db0  jmp     loc_180003B03
0x180003db5  mov     word ptr [rbp+0F0h+Buf2+0Ch], cx
0x180003db9  jmp     loc_1800039C4
0x180003dbe  mov     qword ptr [rbp+0F0h+Buf2+0Ch], rax
0x180003dc2  mov     dword ptr [rbp+0F0h+var_C0+4], eax
0x180003dc5  mov     word ptr [rbp+0F0h+var_C0+8], ax
  ... truncated ...
```
