# CopyCredManCredentials

- ea: `0x18000ffb0`
- end: `0x180010b0c`
- name: `CopyCredManCredentials`
- size: `2908`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18000fb80`
- `0x18004e67c`

## callees

- `0x18000cba0`
- `0x18000ffb0`
- `0x180010b14`
- `0x1800131fc`
- `0x18002ee7c`
- `0x18002f014`
- `0x18002fb50`
- `0x18002fb90`
- `0x180040bac`
- `0x18004f264`
- `0x18004f35c`
- `0x18005c19c`
- `0x18006bcf0`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800103a7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800103a7`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x180010453`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x180010988`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x180010453`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x180010988`

## pseudocode

```c
__int64 __fastcall CopyCredManCredentials(
        __int64 *a1,
        const void **a2,
        int **a3,
        __int64 a4,
        char a5,
        char a6,
        bool *a7)
{
  __int64 *v10; // r14
  int *v12; // rbx
  int *v13; // r15
  __int64 *v14; // rcx
  unsigned __int64 v15; // r12
  unsigned __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  int *v21; // rax
  int v22; // esi
  struct _LSA_SECPKG_FUNCTION_TABLE *v23; // rax
  int v24; // eax
  struct _LSA_SECPKG_FUNCTION_TABLE *v25; // rax
  int v26; // eax
  _DWORD *v27; // rcx
  _BYTE *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // r11
  unsigned int v31; // esi
  _QWORD *v32; // rcx
  int *v33; // r8
  __int64 v34; // r10
  int v35; // r9d
  int v36; // edx
  __int64 v37; // rax
  wchar_t *v38; // rax
  __int64 v39; // rax
  _WORD *v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rcx
  unsigned __int64 v43; // rsi
  const WCHAR *v44; // r14
  __int64 v45; // rax
  const WCHAR *v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // r8
  bool *v50; // r12
  __int64 v51; // r8
  _DWORD *v52; // r10
  int v53; // r9d
  int v54; // eax
  int *v55; // rsi
  int v56; // eax
  __int64 v57; // r9
  _WORD *v58; // rdx
  __int64 v59; // rax
  __int64 v60; // rcx
  unsigned __int64 v61; // rsi
  _DWORD *v62; // r12
  __int64 v63; // rcx
  bool v64; // zf
  __int64 v65; // [rsp+0h] [rbp-40h] BYREF
  unsigned int *v66; // [rsp+20h] [rbp-20h]
  __int64 *v67; // [rsp+28h] [rbp-18h]
  int v68; // [rsp+40h] [rbp+0h] BYREF
  int v69; // [rsp+44h] [rbp+4h] BYREF
  unsigned int v70; // [rsp+48h] [rbp+8h] BYREF
  __int64 v71; // [rsp+50h] [rbp+10h] BYREF
  int *v72; // [rsp+58h] [rbp+18h]
  unsigned int v73; // [rsp+60h] [rbp+20h] BYREF
  __int64 v74; // [rsp+68h] [rbp+28h] BYREF
  __int128 v75; // [rsp+70h] [rbp+30h] BYREF
  _QWORD v76[2]; // [rsp+80h] [rbp+40h] BYREF
  __int64 v77; // [rsp+90h] [rbp+50h]
  int *v78; // [rsp+98h] [rbp+58h] BYREF
  __int128 v79; // [rsp+A0h] [rbp+60h]
  _DWORD *v80; // [rsp+B0h] [rbp+70h] BYREF
  __int64 v81; // [rsp+B8h] [rbp+78h] BYREF
  bool *v82; // [rsp+C0h] [rbp+80h]
  __int128 v83; // [rsp+C8h] [rbp+88h] BYREF
  __int128 v84; // [rsp+D8h] [rbp+98h] BYREF
  __int128 v85; // [rsp+E8h] [rbp+A8h]
  __int128 v86; // [rsp+F8h] [rbp+B8h]
  _WORD v87[520]; // [rsp+110h] [rbp+D0h] BYREF

  v82 = a7;
  v74 = 0;
  v70 = 0;
  v80 = 0;
  v78 = 0;
  v73 = 0;
  v10 = a1;
  v69 = 0;
  v81 = 999;
  v75 = 0;
  v83 = 0;
  v79 = 0;
  if ( !a4 )
    return 3221226021LL;
  v12 = 0;
  v13 = *a3;
  if ( *(_DWORD *)a1 == NtLmGlobalLuidMachineLogon.LowPart )
  {
    v14 = &v81;
    if ( *((_DWORD *)v10 + 1) != NtLmGlobalLuidMachineLogon.HighPart )
      v14 = v10;
    v10 = v14;
  }
  if ( a2 )
  {
    v15 = *(unsigned __int16 *)a2 + 2LL;
    if ( v15 > g_ulMaxStackAllocSize )
      goto LABEL_152;
    v16 = v15 + g_ulAdditionalProbeSize + 8;
    if ( v16 < v15 || !(unsigned int)VerifyStackAvailable(v16, a2, a3) )
      goto LABEL_152;
    v17 = v15 + 23;
    if ( v15 + 23 <= v15 + 8 )
      v17 = 0xFFFFFFFFFFFFFF0LL;
    v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
    v19 = alloca(v18);
    v20 = alloca(v18);
    v12 = &v68;
    if ( &v65 == (__int64 *)-64LL || (v68 = 1801679955, (v12 = (int *)&v70) == 0) )
    {
LABEL_152:
      if ( v15 + 8 >= v15 )
      {
        v21 = (int *)((__int64 (*)(void))g_pfnAllocate)();
        v12 = v21;
        if ( v21 )
        {
          *v21 = 1885431112;
          v12 = v21 + 2;
        }
      }
    }
    if ( !v12 )
    {
      v22 = -1073741670;
      goto LABEL_29;
    }
    memcpy_0(v12, a2[1], *(unsigned __int16 *)a2);
    v23 = LsaFunctions;
    *((_WORD *)v12 + ((unsigned __int64)*(unsigned __int16 *)a2 >> 1)) = 0;
    v67 = &v74;
    v66 = &v70;
    *a3 = v12;
    v24 = ((__int64 (__fastcall *)(__int64 *, __int64, int **, _QWORD, unsigned int *, __int64 *))v23->DummyFunction2)(
            v10,
            1,
            a3,
            0,
            v66,
            v67);
    if ( v24 >= 0 )
      goto LABEL_41;
    if ( v24 != -1073741275 && v24 != -1073741729 && v24 != -1073741811 )
      goto LABEL_28;
  }
  v25 = LsaFunctions;
  v67 = &v74;
  *a3 = v13;
  v26 = ((__int64 (__fastcall *)(__int64 *, __int64, int **, _QWORD, unsigned int *, __int64 *))v25->DummyFunction2)(
          v10,
          1,
          a3,
          0,
          &v70,
          v67);
  if ( v26 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_DDd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        155,
        WPP_9d14a29214673930ad919c44725bb8be_Traceguids,
        (unsigned int)v26,
        *((_DWORD *)v10 + 1),
        *(_DWORD *)v10);
    goto LABEL_28;
  }
LABEL_41:
  v30 = v74;
  v31 = 0;
  v32 = WPP_GLOBAL_Control;
  v77 = 0;
  v72 = 0;
  v87[515] = 0;
  v71 = v74;
  while ( v31 < v70 )
  {
    v33 = *(int **)(v30 + 8LL * v31);
    v34 = 8LL * v31;
    v76[0] = v34;
    v35 = *v33;
    if ( (*v33 & 0x40) == 0 || (dword_180087A84 & 0x20) != 0 )
    {
      v36 = v33[1];
      LOBYTE(v68) = 0;
      if ( v36 == 3 )
      {
        v72 = v33;
      }
      else if ( v36 == 6 )
      {
        LOBYTE(v68) = 1;
      }
      else if ( v36 != 2 || !a6 && (v35 & 8) != 0 )
      {
        goto LABEL_64;
      }
      if ( v32 != &WPP_GLOBAL_Control && (*((_DWORD *)v32 + 7) & 0x4000) != 0 )
      {
        WPP_SF_DDDSS(v32[2], v36, (_DWORD)v33, v31, v36, v35, *((_QWORD *)v33 + 1), *((_QWORD *)v33 + 9));
        v32 = WPP_GLOBAL_Control;
        v34 = v76[0];
        v30 = v71;
      }
      if ( a5 )
      {
        v37 = *(_QWORD *)(v30 + v34);
        if ( *(_QWORD *)(v37 + 8) )
        {
          v38 = wcschr(*(const wchar_t **)(v37 + 8), 0x2Au);
          v32 = WPP_GLOBAL_Control;
          v30 = v71;
          if ( v38 )
            goto LABEL_64;
          v34 = v76[0];
        }
      }
      v39 = *(_QWORD *)(v30 + v34);
      if ( (*(_DWORD *)v39 & 1) != 0 )
      {
        v77 = *(_QWORD *)(v30 + v34);
      }
      else
      {
        if ( (*(_DWORD *)v39 & 2) != 0 )
          goto LABEL_123;
        v40 = *(_WORD **)(v39 + 72);
        if ( !v40 )
          goto LABEL_28;
        if ( *(_DWORD *)(v39 + 4) != 3 )
        {
          v41 = -1;
          do
            ++v41;
          while ( v40[v41] );
          v42 = 515;
          if ( (unsigned __int16)v41 < 0x203u )
            v42 = (unsigned __int16)v41;
          v43 = v42;
          memcpy_0(v87, v40, 2 * v42);
          if ( v43 >= 516 )
            _report_rangecheckfailure();
          v87[v43] = 0;
          v22 = CredParseUserNameWithType(v87, &v83, &v75, &v69);
          if ( v22 >= 0 )
          {
            v44 = &Src;
            if ( !(_BYTE)v68 && v69 == 1 )
            {
              *((_QWORD *)&v75 + 1) = &Src;
              LODWORD(v75) = 0x20000;
            }
            if ( *(_QWORD *)(a4 + 128) )
            {
              ((void (*)(void))LsaFunctions->FreePrivateHeap)();
              *(_QWORD *)(a4 + 128) = 0;
              *(_WORD *)(a4 + 120) = 0;
            }
            v22 = NtLmDuplicateUnicodeString(a4 + 120, &v75);
            if ( v22 >= 0 )
            {
              if ( *(_QWORD *)(a4 + 144) )
              {
                ((void (*)(void))LsaFunctions->FreePrivateHeap)();
                *(_QWORD *)(a4 + 144) = 0;
              }
              v22 = NtLmDuplicateUnicodeString(a4 + 136, &v83);
              if ( v22 >= 0 )
              {
                _mm_lfence();
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, WPP_9d14a29214673930ad919c44725bb8be_Traceguids);
                }
                v45 = *(_QWORD *)(v71 + v76[0]);
                v46 = *(const WCHAR **)(v45 + 40);
                WORD1(v79) = *(_WORD *)(v45 + 32);
                v47 = *(_QWORD *)(a4 + 160);
                LOWORD(v79) = *(_WORD *)(*(_QWORD *)(v76[0] + v74) + 80LL);
                if ( (_WORD)v79 )
                  v44 = v46;
                *((_QWORD *)&v79 + 1) = v44;
                if ( v47 )
                {
                  ((void (*)(void))LsaFunctions->FreePrivateHeap)();
                  *(_QWORD *)(a4 + 160) = 0;
                }
                v22 = NtLmDuplicatePassword(a4 + 152);
                if ( v22 >= 0 )
                {
                  _mm_lfence();
                  v48 = v76[0];
                  v49 = v71;
                  v50 = v82;
                  *v82 = (**(_DWORD **)(v71 + v76[0]) & 8) != 0;
                  if ( a6 || (_mm_lfence(), (**(_BYTE **)(v49 + v48) & 0x40) == 0) )
                  {
                    _mm_lfence();
                    if ( (**(_BYTE **)(v49 + v48) & 0x40) != 0 )
                    {
                      if ( (dword_180087A84 & 0x20) == 0 )
                        MicrosoftTelemetryAssertTriggeredNoArgs();
                      v22 = (*(__int64 (__fastcall **)(struct NtlmCredIsoApi *, __int64, PLSA_ALLOCATE_PRIVATE_HEAP, PLSA_FREE_PRIVATE_HEAP))(*(_QWORD *)LocalhostNtLmCredIsoObj::IsoObj + 152LL))(
                              LocalhostNtLmCredIsoObj::IsoObj,
                              a4 + 152,
                              LsaFunctions->AllocatePrivateHeap,
                              LsaFunctions->FreePrivateHeap);
                      if ( v22 >= 0 )
                      {
                        *(_DWORD *)(a4 + 248) = 1;
                        *v50 = 1;
                      }
                    }
                  }
                  else
                  {
                    if ( (dword_180087A84 & 0x20) == 0 )
                      MicrosoftTelemetryAssertTriggeredNoArgs();
                    v22 = (*(__int64 (__fastcall **)(struct NtlmCredIsoApi *, __int64, PLSA_ALLOCATE_PRIVATE_HEAP, PLSA_FREE_PRIVATE_HEAP))(*(_QWORD *)LocalhostNtLmCredIsoObj::IsoObj + 160LL))(
                            LocalhostNtLmCredIsoObj::IsoObj,
                            a4 + 152,
                            LsaFunctions->AllocatePrivateHeap,
                            LsaFunctions->FreePrivateHeap);
                    *(_DWORD *)(a4 + 248) = 1;
                  }
                }
              }
            }
          }
          goto LABEL_29;
        }
      }
    }
LABEL_64:
    ++v31;
  }
  v51 = v77;
  v52 = v72;
  if ( !v77 && !v72 )
  {
    if ( v32 != &WPP_GLOBAL_Control && (*((_DWORD *)v32 + 7) & 0x4000) != 0 )
      WPP_SF_(v32[2], 162, WPP_9d14a29214673930ad919c44725bb8be_Traceguids);
    goto LABEL_28;
  }
  v76[0] = 1179664;
  v53 = 0;
  LODWORD(v71) = -1073741823;
  v72 = 0;
  v76[1] = L"Kerberos";
  v84 = 0;
  v85 = 0;
  v86 = 0;
  if ( v77 )
  {
    if ( v32 != &WPP_GLOBAL_Control && (*((_DWORD *)v32 + 7) & 0x4000) != 0 )
    {
      WPP_SF_S(v32[2], 158, WPP_9d14a29214673930ad919c44725bb8be_Traceguids, *(_QWORD *)(v77 + 8));
      v51 = v77;
    }
    v22 = ((__int64 (__fastcall *)(__int64 *, __int64, _QWORD, __int64, _DWORD, _DWORD **))LsaFunctions->DummyFunction1)(
            v10,
            1,
            *(_QWORD *)(v51 + 8),
            3,
            0,
            &v80);
    if ( v22 >= 0 )
    {
      v52 = v80;
      v53 = (int)v72;
      goto LABEL_110;
    }
  }
  else
  {
LABEL_110:
    *((_QWORD *)&v86 + 1) = 0;
    *(_QWORD *)&v85 = L"NTLM";
    *(_QWORD *)&v86 = *v10;
    HIDWORD(v84) = v53;
    v67 = &v71;
    *(_QWORD *)&v84 = 18;
    DWORD2(v84) = 655368;
    *((_QWORD *)&v85 + 1) = v52;
    *((_QWORD *)&v86 + 1) = (*v52 & 0x80 | 0x20u) >> 3;
    v54 = ((__int64 (__fastcall *)(_QWORD *, __int128 *, __int64, int **, unsigned int *, __int64 *))LsaFunctions->CallPackage)(
            v76,
            &v84,
            48,
            &v78,
            &v73,
            &v71);
    v22 = v54;
    if ( v54 >= 0 )
    {
      v22 = v71;
      if ( (int)v71 >= 0 )
      {
        v55 = v78;
        v72 = v78;
        if ( v78[1] != 2 )
          goto LABEL_28;
        v56 = *v78;
        if ( (*v78 & 1) != 0 || !a6 && (v56 & 8) != 0 )
          goto LABEL_28;
        if ( (v56 & 2) != 0 )
        {
LABEL_123:
          v22 = -2146893044;
          goto LABEL_29;
        }
        v57 = *((_QWORD *)v78 + 9);
        if ( v57 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, WPP_9d14a29214673930ad919c44725bb8be_Traceguids, v57);
          }
          v58 = (_WORD *)*((_QWORD *)v55 + 9);
          v59 = -1;
          do
            ++v59;
          while ( v58[v59] );
          v60 = 515;
          if ( (unsigned int)v59 < 0x203 )
            v60 = (unsigned int)v59;
          v61 = v60;
          memcpy_0(v87, v58, 2 * v60);
          if ( v61 >= 516 )
            _report_rangecheckfailure();
          v87[v61] = 0;
          v22 = CredParseUserNameWithType(v87, &v83, &v75, &v69);
          if ( v22 >= 0 )
          {
            if ( v69 == 3 )
            {
              v22 = -1073741637;
            }
            else
            {
              if ( v69 == 1 )
              {
                LODWORD(v75) = 0x20000;
                *((_QWORD *)&v75 + 1) = &Src;
              }
              if ( *(_QWORD *)(a4 + 128) )
              {
                ((void (*)(void))LsaFunctions->FreePrivateHeap)();
                *(_QWORD *)(a4 + 128) = 0;
                *(_WORD *)(a4 + 120) = 0;
              }
              v22 = NtLmDuplicateUnicodeString(a4 + 120, &v75);
              if ( v22 >= 0 )
              {
                if ( *(_QWORD *)(a4 + 144) )
                {
                  ((void (*)(void))LsaFunctions->FreePrivateHeap)();
                  *(_QWORD *)(a4 + 144) = 0;
                }
                v22 = NtLmDuplicateUnicodeString(a4 + 136, &v83);
                if ( v22 >= 0 )
                {
                  v62 = v72;
                  v63 = *(_QWORD *)(a4 + 160);
                  *((_QWORD *)&v79 + 1) = *((_QWORD *)v72 + 5);
                  WORD1(v79) = *((_WORD *)v72 + 16);
                  LOWORD(v79) = *((_WORD *)v72 + 40);
                  if ( v63 )
                  {
                    ((void (*)(void))LsaFunctions->FreePrivateHeap)();
                    *(_QWORD *)(a4 + 160) = 0;
                    *(_DWORD *)(a4 + 248) = 0;
                  }
                  v22 = NtLmDuplicatePassword(a4 + 152);
                  if ( v22 >= 0 )
                  {
                    v64 = v77 == 0;
                    *v82 = (*v62 & 8) != 0;
                    if ( !v64 )
                      ((void (__fastcall *)(__int64 *, __int64, int *, _QWORD))LsaFunctions->DummyFunction4)(
                        v10,
                        1,
                        v72,
                        0);
                  }
                }
              }
            }
          }
        }
        else
        {
LABEL_28:
          v22 = -1073741275;
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          160,
          WPP_9d14a29214673930ad919c44725bb8be_Traceguids,
          (unsigned int)v71);
        v22 = v71;
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        159,
        WPP_9d14a29214673930ad919c44725bb8be_Traceguids,
        (unsigned int)v54);
    }
  }
LABEL_29:
  v27 = v80;
  *a3 = v13;
  if ( v27 )
    ((void (*)(void))LsaFunctions->FreeLsaHeap)();
  if ( v74 )
    ((void (__fastcall *)(_QWORD))LsaFunctions->DummyFunction3)(v70);
  v28 = v78;
  if ( v78 )
  {
    v29 = v73;
    if ( v73 )
    {
      do
      {
        *v28++ = 0;
        --v29;
      }
      while ( v29 );
    }
    ((void (__fastcall *)(int *))LsaFunctions->FreePrivateHeap)(v78);
  }
  if ( v12 )
  {
    if ( *(v12 - 2) == 1885431112 )
      ((void (__fastcall *)(int *))g_pfnFree)(v12 - 2);
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18000ffb0  push    rbp
0x18000ffb2  push    rbx
0x18000ffb3  push    rsi
0x18000ffb4  push    rdi
0x18000ffb5  push    r12
0x18000ffb7  push    r13
0x18000ffb9  push    r14
0x18000ffbb  push    r15
0x18000ffbd  sub     rsp, 538h
0x18000ffc4  lea     rbp, [rsp+40h]
0x18000ffc9  mov     rax, cs:__security_cookie
0x18000ffd0  xor     rax, rbp
0x18000ffd3  mov     [rbp+530h+var_50], rax
0x18000ffda  mov     rax, [rbp+530h+arg_30]
0x18000ffe1  xor     r12d, r12d
0x18000ffe4  mov     [rbp+530h+var_4B0], rax
0x18000ffeb  xorps   xmm0, xmm0
0x18000ffee  mov     [rbp+530h+var_508], r12
0x18000fff2  xorps   xmm1, xmm1
0x18000fff5  mov     [rbp+530h+var_528], r12d
0x18000fff9  mov     r13, r9
0x18000fffc  mov     [rbp+530h+var_4C0], r12
0x180010000  mov     rdi, r8
0x180010003  mov     [rbp+530h+var_4D8], r12
0x180010007  mov     rsi, rdx
0x18001000a  mov     [rbp+530h+var_510], r12d
0x18001000e  mov     r14, rcx
0x180010011  mov     [rbp+530h+var_52C], r12d
0x180010015  mov     [rbp+530h+var_4B8], 3E7h
0x18001001d  movups  [rbp+530h+var_500], xmm0
0x180010021  movups  [rbp+530h+var_4A8], xmm1
0x180010028  movups  [rbp+530h+var_4D0], xmm0
0x18001002c  test    r9, r9
0x18001002f  jnz     short loc_18001003B
0x180010031  mov     eax, 0C0000225h
0x180010036  jmp     loc_18001028E
0x18001003b  mov     eax, cs:NtLmGlobalLuidMachineLogon.LowPart
0x180010041  mov     rbx, r12
0x180010044  mov     r15, [r8]
0x180010047  cmp     [rcx], eax
0x180010049  jnz     short loc_180010060
0x18001004b  mov     eax, cs:NtLmGlobalLuidMachineLogon.HighPart
0x180010051  lea     rcx, [rbp+530h+var_4B8]
0x180010055  cmp     [r14+4], eax
0x180010059  cmovnz  rcx, r14
0x18001005d  mov     r14, rcx
0x180010060  test    rsi, rsi
0x180010063  jz      loc_18001017B
0x180010069  movzx   r12d, word ptr [rdx]
0x18001006d  add     r12, 2
0x180010071  cmp     r12, cs:g_ulMaxStackAllocSize
0x180010078  ja      short loc_1800100D3
0x18001007a  mov     rcx, cs:g_ulAdditionalProbeSize
0x180010081  add     rcx, 8
0x180010085  add     rcx, r12
0x180010088  cmp     rcx, r12
0x18001008b  jb      short loc_1800100D3
0x18001008d  call    VerifyStackAvailable
0x180010092  test    eax, eax
0x180010094  jz      short loc_1800100D3
0x180010096  lea     rax, [r12+8]
0x18001009b  lea     rcx, [rax+0Fh]
0x18001009f  cmp     rcx, rax
0x1800100a2  ja      short loc_1800100AE
0x1800100a4  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800100ae  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800100b2  mov     rax, rcx
0x1800100b5  call    _alloca_probe
0x1800100ba  sub     rsp, rcx
0x1800100bd  lea     rbx, [rsp+570h+var_530]
0x1800100c2  test    rbx, rbx
0x1800100c5  jz      short loc_1800100D3
0x1800100c7  mov     dword ptr [rbx], 6B637453h
0x1800100cd  add     rbx, 8
0x1800100d1  jnz     short loc_1800100FB
0x1800100d3  lea     rcx, [r12+8]
0x1800100d8  cmp     rcx, r12
0x1800100db  jb      short loc_1800100FB
0x1800100dd  mov     rax, cs:g_pfnAllocate
0x1800100e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100e9  mov     rbx, rax
0x1800100ec  test    rax, rax
0x1800100ef  jz      short loc_1800100FB
0x1800100f1  mov     dword ptr [rax], 70616548h
0x1800100f7  add     rbx, 8
0x1800100fb  test    rbx, rbx
0x1800100fe  jnz     short loc_18001010A
0x180010100  mov     esi, 0C000009Ah
0x180010105  jmp     loc_1800101FE
0x18001010a  movzx   r8d, word ptr [rsi]; Size
0x18001010e  mov     rcx, rbx; void *
0x180010111  mov     rdx, [rsi+8]; Src
0x180010115  call    memcpy_0
0x18001011a  movzx   ecx, word ptr [rsi]
0x18001011d  xor     r12d, r12d
0x180010120  mov     rax, cs:LsaFunctions
0x180010127  xor     r9d, r9d
0x18001012a  shr     rcx, 1
0x18001012d  mov     r8, rdi
0x180010130  mov     edx, 1
0x180010135  mov     [rbx+rcx*2], r12w
0x18001013a  lea     rcx, [rbp+530h+var_508]
0x18001013e  mov     [rsp+570h+var_548], rcx
0x180010143  lea     rcx, [rbp+530h+var_528]
0x180010147  mov     [rsp+570h+var_550], rcx
0x18001014c  mov     rcx, r14
0x18001014f  mov     [rdi], rbx
0x180010152  mov     rax, [rax+150h]
0x180010159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001015e  test    eax, eax
0x180010160  jns     loc_1800102B1
0x180010166  cmp     eax, 0C0000225h
0x18001016b  jz      short loc_18001017B
0x18001016d  cmp     eax, 0C000005Fh
0x180010172  jz      short loc_18001017B
0x180010174  cmp     eax, 0C000000Dh
0x180010179  jnz     short loc_1800101F9
0x18001017b  mov     rax, cs:LsaFunctions
0x180010182  lea     rcx, [rbp+530h+var_508]
0x180010186  mov     [rsp+570h+var_548], rcx
0x18001018b  xor     r9d, r9d
0x18001018e  lea     rcx, [rbp+530h+var_528]
0x180010192  mov     [rdi], r15
0x180010195  mov     [rsp+570h+var_550], rcx
0x18001019a  mov     r8, rdi
0x18001019d  mov     rax, [rax+150h]
0x1800101a4  mov     rcx, r14
0x1800101a7  mov     edx, 1
0x1800101ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101b1  mov     r9d, eax
0x1800101b4  test    eax, eax
0x1800101b6  jns     loc_1800102B1
0x1800101bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101c3  lea     r12, WPP_GLOBAL_Control
0x1800101ca  cmp     rcx, r12
0x1800101cd  jz      short loc_1800101F9
0x1800101cf  test    byte ptr [rcx+1Ch], 8
0x1800101d3  jz      short loc_1800101F9
0x1800101d5  mov     eax, [r14]
0x1800101d8  lea     r8, WPP_9d14a29214673930ad919c44725bb8be_Traceguids
0x1800101df  mov     rcx, [rcx+10h]
0x1800101e3  mov     edx, 9Bh
0x1800101e8  mov     dword ptr [rsp+570h+var_548], eax
0x1800101ec  mov     eax, [r14+4]
0x1800101f0  mov     dword ptr [rsp+570h+var_550], eax
0x1800101f4  call    WPP_SF_DDd
0x1800101f9  mov     esi, 0C0000225h
0x1800101fe  mov     rcx, [rbp+530h+var_4C0]
0x180010202  mov     [rdi], r15
0x180010205  test    rcx, rcx
0x180010208  jz      short loc_18001021A
0x18001020a  mov     rax, cs:LsaFunctions
0x180010211  mov     rax, [rax+30h]
0x180010215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001021a  mov     rdx, [rbp+530h+var_508]
0x18001021e  test    rdx, rdx
0x180010221  jz      short loc_180010239
0x180010223  mov     rax, cs:LsaFunctions
0x18001022a  mov     ecx, [rbp+530h+var_528]
0x18001022d  mov     rax, [rax+158h]
0x180010234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010239  mov     rax, [rbp+530h+var_4D8]
0x18001023d  test    rax, rax
0x180010240  jz      short loc_18001026E
0x180010242  mov     ecx, [rbp+530h+var_510]
0x180010245  test    rcx, rcx
0x180010248  jz      short loc_180010257
0x18001024a  mov     byte ptr [rax], 0
0x18001024d  lea     rax, [rax+1]
0x180010251  sub     rcx, 1
0x180010255  jnz     short loc_18001024A
0x180010257  mov     rax, cs:LsaFunctions
0x18001025e  mov     rcx, [rbp+530h+var_4D8]
0x180010262  mov     rax, [rax+188h]
0x180010269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001026e  test    rbx, rbx
0x180010271  jz      short loc_18001028C
0x180010273  cmp     dword ptr [rbx-8], 70616548h
0x18001027a  lea     rcx, [rbx-8]
0x18001027e  jnz     short loc_18001028C
0x180010280  mov     rax, cs:g_pfnFree
0x180010287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001028c  mov     eax, esi
0x18001028e  mov     rcx, [rbp+530h+var_50]
0x180010295  xor     rcx, rbp; StackCookie
0x180010298  call    __security_check_cookie
0x18001029d  lea     rsp, [rbp+4F8h]
0x1800102a4  pop     r15
0x1800102a6  pop     r14
0x1800102a8  pop     r13
0x1800102aa  pop     r12
0x1800102ac  pop     rdi
0x1800102ad  pop     rsi
0x1800102ae  pop     rbx
0x1800102af  pop     rbp
0x1800102b0  retn
0x1800102b1  mov     r11, [rbp+530h+var_508]
0x1800102b5  mov     esi, r12d
0x1800102b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102bf  mov     [rbp+530h+var_4E0], r12
0x1800102c3  mov     [rbp+530h+var_518], r12
0x1800102c7  mov     [rbp+530h+var_5A], r12w
0x1800102cf  lea     r12, WPP_GLOBAL_Control
0x1800102d6  mov     [rbp+530h+var_520], r11
0x1800102da  cmp     esi, [rbp+530h+var_528]
0x1800102dd  jnb     loc_1800106B2
0x1800102e3  mov     eax, esi
0x1800102e5  mov     r8, [r11+rax*8]
0x1800102e9  lea     r10, ds:0[rax*8]
0x1800102f1  mov     [rbp+530h+var_4F0], r10
0x1800102f5  mov     r9d, [r8]
0x1800102f8  test    r9b, 40h
0x1800102fc  jz      short loc_18001030B
0x1800102fe  test    byte ptr cs:dword_180087A84, 20h
0x180010305  jz      loc_1800103EE
0x18001030b  mov     edx, [r8+4]
0x18001030f  mov     byte ptr [rbp+530h+var_530], 0
0x180010313  cmp     edx, 3
0x180010316  jnz     short loc_18001031E
0x180010318  mov     [rbp+530h+var_518], r8
0x18001031c  jmp     short loc_180010345
0x18001031e  cmp     edx, 6
0x180010321  jnz     short loc_180010329
0x180010323  mov     byte ptr [rbp+530h+var_530], 1
0x180010327  jmp     short loc_180010345
0x180010329  cmp     edx, 2
0x18001032c  jnz     loc_1800103EE
0x180010332  cmp     [rbp+530h+arg_28], 0
0x180010339  jnz     short loc_180010345
0x18001033b  test    r9b, 8
0x18001033f  jnz     loc_1800103EE
0x180010345  cmp     rcx, r12
0x180010348  jz      short loc_180010389
0x18001034a  test    dword ptr [rcx+1Ch], 4000h
0x180010351  jz      short loc_180010389
0x180010353  mov     rax, [r8+48h]
0x180010357  mov     rcx, [rcx+10h]
0x18001035b  mov     [rsp+570h+var_538], rax
0x180010360  mov     rax, [r8+8]
0x180010364  mov     [rsp+570h+var_540], rax
0x180010369  mov     dword ptr [rsp+570h+var_548], r9d
0x18001036e  mov     r9d, esi
0x180010371  mov     dword ptr [rsp+570h+var_550], edx
0x180010375  call    WPP_SF_DDDSS
0x18001037a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010381  mov     r10, [rbp+530h+var_4F0]
0x180010385  mov     r11, [rbp+530h+var_520]
0x180010389  cmp     [rbp+530h+arg_20], 0
0x180010390  jz      short loc_1800103C1
0x180010392  mov     rax, [r11+r10]
0x180010396  mov     r8, [rax+8]
0x18001039a  test    r8, r8
0x18001039d  jz      short loc_1800103C1
0x18001039f  mov     edx, 2Ah ; '*'; Ch
0x1800103a4  mov     rcx, r8; Str
0x1800103a7  call    cs:__imp_wcschr
0x1800103ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800103b4  mov     r11, [rbp+530h+var_520]
0x1800103b8  test    rax, rax
0x1800103bb  jnz     short loc_1800103EE
0x1800103bd  mov     r10, [rbp+530h+var_4F0]
0x1800103c1  mov     rax, [r11+r10]
0x1800103c5  mov     edx, [rax]
0x1800103c7  test    dl, 1
0x1800103ca  jz      short loc_1800103D2
0x1800103cc  mov     [rbp+530h+var_4E0], rax
0x1800103d0  jmp     short loc_1800103EE
0x1800103d2  test    dl, 2
0x1800103d5  jnz     loc_1800108E8
0x1800103db  mov     rdx, [rax+48h]; Src
0x1800103df  test    rdx, rdx
0x1800103e2  jz      loc_1800101F9
0x1800103e8  cmp     dword ptr [rax+4], 3
0x1800103ec  jnz     short loc_1800103F5
0x1800103ee  inc     esi
0x1800103f0  jmp     loc_1800102DA
0x1800103f5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800103fc  inc     rax
0x1800103ff  cmp     word ptr [rdx+rax*2], 0
0x180010404  jnz     short loc_1800103FC
0x180010406  mov     ecx, 203h
0x18001040b  cmp     ax, cx
0x18001040e  jnb     short loc_180010413
0x180010410  movzx   ecx, ax
0x180010413  lea     rsi, [rcx+rcx]
0x180010417  mov     r8, rsi; Size
0x18001041a  lea     rcx, [rbp+530h+var_460]; void *
0x180010421  call    memcpy_0
0x180010426  cmp     rsi, 408h
0x18001042d  jnb     loc_1800106AC
0x180010433  xor     eax, eax
0x180010435  lea     r9, [rbp+530h+var_52C]
0x180010439  lea     r8, [rbp+530h+var_500]
0x18001043d  mov     [rbp+rsi+530h+var_460], ax
0x180010445  lea     rdx, [rbp+530h+var_4A8]
0x18001044c  lea     rcx, [rbp+530h+var_460]
0x180010453  call    cs:__imp_CredParseUserNameWithType
0x180010459  mov     esi, eax
0x18001045b  test    eax, eax
0x18001045d  js      loc_1800101FE
  ... truncated ...
```
