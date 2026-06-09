# NetpDcInitializeContext(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,void *,_GUID *,ushort const *,ushort const *,_SOCKET_ADDRESS *,ulong,ulong,ulong,ulong,_NL_GETDC_CONTEXT * *)

- ea: `0x180009fb0`
- end: `0x18000a9a3`
- name: `?NetpDcInitializeContext@@YAKPEAXPEBG11K1110PEAU_GUID@@11PEAU_SOCKET_ADDRESS@@KKKKPEAPEAU_NL_GETDC_CONTEXT@@@Z`
- size: `2547`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, void *Sid, struct _GUID *, const unsigned __int16 *, unsigned __int16 *, struct _SOCKET_ADDRESS *, unsigned int, unsigned int, unsigned int, char, struct _NL_GETDC_CONTEXT **)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180057aec`
- `0x180066a84`
- `0x180078f00`

## callees

- `0x180002c00`
- `0x180007278`
- `0x180009fb0`
- `0x18000a9ac`
- `0x18000e270`
- `0x180018414`
- `0x18001852c`
- `0x180074f1c`
- `0x180077ebc`
- `0x1800780b4`
- `0x1800782b8`
- `0x18007cdf8`
- `0x18007e350`
- `0x18007f110`
- `0x180083ca4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a03a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a657`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a03a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a657`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetMailslotInfo` at `0x18000a6ce`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetMailslotInfo` at `0x18000a6ce`

## string_xrefs

- `0x18000a2ea`: `NetpDcInitializeContext: %ws: invalid flag, DS_DIRECTORY_SERVICE_{[6|8|9|10|12|13|14]_}REQUIRED flags are mutually exclusive %lx\n`
- `0x18000a461`: `NetpDcInitializeContext: Using flag DS_TRY_NEXTCLOSEST_SITE due to registry/policy TryNextClosestSite\n`
- `0x18000a4b8`: `NetpDcInitializeContext: %ws: flags not compatible with 'Good Time' %lx\n`
- `0x18000a690`: `NetpDcInitializeContext: %ws: cannot create temp mailslot %ld\n`
- `0x18000a6e2`: `NetpDcInitializeContext: %ws: cannot change temp mailslot timeout %ld\n`

## pseudocode

```c
__int64 __fastcall NetpDcInitializeContext(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8,
        void *Sid,
        struct _GUID *a10,
        const unsigned __int16 *a11,
        unsigned __int16 *a12,
        struct _SOCKET_ADDRESS *a13,
        unsigned int a14,
        unsigned int a15,
        unsigned int a16,
        char a17,
        struct _NL_GETDC_CONTEXT **a18)
{
  unsigned __int64 v19; // r11
  struct _NL_GETDC_CONTEXT *v23; // rbx
  HLOCAL v24; // rax
  __int64 LastError; // rdi
  void *v26; // rcx
  unsigned int v27; // r15d
  const unsigned __int16 *v28; // r8
  const unsigned __int16 *v29; // r10
  const unsigned __int16 *v30; // rdx
  const unsigned __int16 *v31; // r9
  char v32; // al
  unsigned int v33; // ecx
  ScannerInfoNameMappings *v34; // rcx
  int v35; // edx
  unsigned int v37; // eax
  int *v38; // rdx
  int v39; // r9d
  ScannerInfoNameMappings *v40; // rcx
  int v41; // edx
  __int64 v42; // rcx
  int v43; // eax
  int v44; // edx
  const unsigned __int16 *v45; // r8
  const unsigned __int16 *v46; // rdx
  struct _NL_DC_DOMAIN_ENTRY *DomainEntry; // rax
  unsigned int v48; // edx
  int v49; // esi
  HLOCAL v50; // rax
  __int64 v51; // rcx
  unsigned int RandomMailslot; // eax
  unsigned int v53; // eax
  __int64 v54; // rdx
  unsigned int v55; // eax
  unsigned int v56; // eax
  HLOCAL hMem; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v58; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v59; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v60; // [rsp+70h] [rbp-90h] BYREF
  struct _SOCKET_ADDRESS *v61; // [rsp+78h] [rbp-88h]
  struct _NL_GETDC_CONTEXT **v62; // [rsp+80h] [rbp-80h]
  _BYTE v63[272]; // [rsp+90h] [rbp-70h] BYREF

  v19 = (unsigned __int64)a12;
  v61 = a13;
  v58 = a12;
  v62 = a18;
  v59 = 0;
  v23 = *a18;
  v60 = 0;
  if ( v23 )
  {
    hMem = 0;
LABEL_6:
    LODWORD(LastError) = 0;
    v27 = 1;
    if ( (a17 & 1) != 0 )
    {
      v28 = a7;
      if ( a7 )
        v28 = (const unsigned __int16 *)(-(__int64)(*a7 != 0) & (unsigned __int64)a7);
      v29 = a8;
      if ( a8 )
        v29 = (const unsigned __int16 *)(-(__int64)(*a8 != 0) & (unsigned __int64)a8);
      v30 = a6;
      if ( a6 )
        v30 = (const unsigned __int16 *)(-(__int64)(*a6 != 0) & (unsigned __int64)a6);
      v31 = a11;
      if ( a11 )
        v31 = (const unsigned __int16 *)(-(__int64)(*a11 != 0) & (unsigned __int64)a11);
      if ( v19 )
      {
        v19 &= -(__int64)(*(_WORD *)v19 != 0);
        v58 = (unsigned __int16 *)v19;
      }
      *((_DWORD *)v23 + 8) = a5;
      *((_QWORD *)v23 + 6) = v30;
      if ( v28 )
        v30 = v28;
      *((_QWORD *)v23 + 3) = a4;
      *((_WORD *)v23 + 115) = 0;
      *((_QWORD *)v23 + 7) = v28;
      *((_QWORD *)v23 + 8) = v29;
      *((_QWORD *)v23 + 12) = v19;
      *((_QWORD *)v23 + 9) = v30;
      *((_QWORD *)v23 + 13) = a10;
      *((_QWORD *)v23 + 15) = a1;
      *((_DWORD *)v23 + 4) = a16;
      *((_DWORD *)v23 + 3) = a15;
      *((_QWORD *)v23 + 27) = 0;
      *((_QWORD *)v23 + 22) = (char *)v23 + 168;
      *((_QWORD *)v23 + 21) = (char *)v23 + 168;
      *((_DWORD *)v23 + 47) = 0;
      *((_QWORD *)v23 + 5) = v31;
      if ( !v31 || (v32 = 1, (*((_BYTE *)v23 + 16) & 4) != 0) )
        v32 = 0;
      *((_BYTE *)v23 + 227) = v32;
      if ( !*((_QWORD *)v23 + 3) )
        *((_DWORD *)v23 + 8) = 0;
      NlPrintRoutine(2u, L"NetpDcInitializeContext: DSGETDC_VALID_FLAGS is %lx\n", 3489660913LL);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_l(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
          3489660913LL);
      v33 = *((_DWORD *)v23 + 3);
      if ( (v33 & 0x3000000E) != 0 )
      {
        NlPrintRoutine(0x100u, L"NetpDcInitializeContext: %ws: invalid flags %lx\n", *((_QWORD *)v23 + 9), a15);
        v34 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_32;
        v35 = 61;
LABEL_31:
        WPP_SF_SL(
          *((_QWORD *)v34 + 2),
          v35,
          (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
          *((_QWORD *)v23 + 9),
          a15);
LABEL_32:
        LODWORD(LastError) = 1004;
LABEL_33:
        v26 = hMem;
        goto LABEL_34;
      }
      if ( (v33 & 0x40) != 0 && (*((_QWORD *)v23 + 3) || *((_DWORD *)v23 + 8) || Sid) )
      {
        NlPrintRoutine(
          0x100u,
          L"NetpDcInitializeContext: %ws: GC queried and invalid parameters specified.\n",
          *((_QWORD *)v23 + 9));
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            62,
            &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
            *((_QWORD *)v23 + 9));
        LODWORD(LastError) = 87;
        goto LABEL_33;
      }
      if ( (v33 & 0x8000) != 0 )
      {
        v33 &= 0xF007D34F;
        *((_DWORD *)v23 + 3) = v33;
      }
      if ( (v33 & 0xEE80010) != 0 && (v33 & -(v33 & 0xFEE80010) & 0xEE80010) != (v33 & 0xEE80010) )
      {
        NlPrintRoutine(
          0x100u,
          L"NetpDcInitializeContext: %ws: invalid flag, DS_DIRECTORY_SERVICE_{[6|8|9|10|12|13|14]_}REQUIRED flags are mutu"
           "ally exclusive %lx\n",
          *((_QWORD *)v23 + 9),
          a15);
        v34 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_32;
        v35 = 63;
        goto LABEL_31;
      }
      if ( (v33 & 0x1000000) != 0 && (v33 & 0x400) == 0 )
      {
        NlPrintRoutine(
          0x100u,
          L"NetpDcInitializeContext: %ws: invalid flag, DS_KEY_LIST_SUPPORT_REQUIRED cannot be specified without DS_KDC_REQUIRED %lx\n",
          *((_QWORD *)v23 + 9),
          a15);
        v34 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_32;
        v35 = 64;
        goto LABEL_31;
      }
      if ( *((_BYTE *)v23 + 227) && (v33 & 0x40000) != 0 )
      {
        NlPrintRoutine(
          0x100u,
          L"NetpDcInitializeContext: %ws: invalid flag, DS_TRY_NEXTCLOSEST_SITE can not be specified when site name is exp"
           "licitly used %lx\n",
          *((_QWORD *)v23 + 9),
          a15);
        v34 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_32;
        v35 = 65;
        goto LABEL_31;
      }
      v37 = NetpDcFlagsToNameType(v33, (struct _NL_GETDC_CONTEXT *)((char *)v23 + 8));
      LODWORD(LastError) = v37;
      if ( v37 )
      {
        NlPrintRoutine(
          0x100u,
          L"NetpDcInitializeContext: %ws: cannot convert flags to nametype %ld\n",
          *((_QWORD *)v23 + 9),
          v37);
        v40 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_33;
        v41 = 66;
        goto LABEL_64;
      }
      v42 = 32LL * *v38;
      *((_DWORD *)v23 + 1) = *(_DWORD *)((char *)&NlDcDnsNameTypeDesc + v42 + 8);
      if ( *(_DWORD *)((char *)&NlDcDnsNameTypeDesc + v42 + 12) == 40 )
      {
        *((_DWORD *)v23 + 3) &= ~0x40000u;
      }
      else if ( !*((_BYTE *)v23 + 227) )
      {
        v43 = *((_DWORD *)v23 + 3);
        if ( (v43 & v39) == 0 && dword_1800F1284 == 1 )
        {
          *((_DWORD *)v23 + 3) = v39 | v43;
          NlPrintRoutine(
            2u,
            L"NetpDcInitializeContext: Using flag DS_TRY_NEXTCLOSEST_SITE due to registry/policy TryNextClosestSite\n");
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids);
        }
      }
      v44 = *((_DWORD *)v23 + 3);
      if ( (v44 & 0x4F0) != 0 && (v44 & 0x2000) != 0 )
      {
        NlPrintRoutine(
          0x100u,
          L"NetpDcInitializeContext: %ws: flags not compatible with 'Good Time' %lx\n",
          *((_QWORD *)v23 + 9),
          a15);
        v34 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_32;
        v35 = 69;
        goto LABEL_31;
      }
      if ( (v44 & 0x80u) != 0 )
      {
        v44 &= 0xFFFFEFDF;
        *((_DWORD *)v23 + 3) = v44;
      }
      if ( (v44 & 0x40020E50) != 0 && (v44 & 0x20) != 0 )
        *((_DWORD *)v23 + 3) = v44 & 0xFFFFFFDF;
      if ( !a2 )
      {
        LODWORD(LastError) = NetpGetComputerNameEx2(&v59, 4);
        if ( (_DWORD)LastError )
          goto LABEL_33;
        a2 = v59;
        *((_BYTE *)v23 + 230) = 1;
      }
      *((_QWORD *)v23 + 10) = a2;
      if ( !a3 )
      {
        LODWORD(LastError) = NetpGetComputerNameEx2(&v60, 3);
        if ( (_DWORD)LastError )
          goto LABEL_33;
        a3 = v60;
        *((_BYTE *)v23 + 231) = 1;
      }
      v45 = (const unsigned __int16 *)*((_QWORD *)v23 + 7);
      v46 = (const unsigned __int16 *)*((_QWORD *)v23 + 6);
      *((_QWORD *)v23 + 11) = a3;
      *((_BYTE *)v23 + 232) = dword_1800F11B4 == 2;
      DomainEntry = NetpDcCreateDomainEntry(*((struct _GUID **)v23 + 13), v46, v45);
      *((_QWORD *)v23 + 14) = DomainEntry;
      if ( !DomainEntry )
      {
        NlPrintRoutine(0x100u, L"NetpDcInitializeContext: not enough memory for DomainEntry.\n");
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids);
        goto LABEL_91;
      }
      *(_DWORD *)v23 |= 1u;
      *((_DWORD *)v23 + 68) = dword_1800F1298;
      *((_DWORD *)v23 + 69) = dword_1800F129C;
    }
    if ( (a17 & 2) != 0 )
    {
      v48 = ((*((_DWORD *)v23 + 3) & 0xFFFFFFC0) << 25) | 0x20000000;
      if ( (*((_DWORD *)v23 + 3) & 0x200) == 0 )
        v48 = (*((_DWORD *)v23 + 3) & 0xFFFFFFC0) << 25;
      v49 = v48 | 0x10000000;
      if ( *((char *)v23 + 12) >= 0 )
        v49 = v48;
      if ( *((_QWORD *)v23 + 6) && !*((_DWORD *)v23 + 69) )
      {
        v50 = LocalAlloc(0, 0x298u);
        *((_QWORD *)v23 + 30) = v50;
        if ( !v50 )
        {
LABEL_91:
          LODWORD(LastError) = 8;
          goto LABEL_33;
        }
        *((_DWORD *)v23 + 62) = 664;
        RandomMailslot = NetpLogonCreateRandomMailslot(v51, v63, (char *)v23 + 200);
        LODWORD(LastError) = RandomMailslot;
        if ( RandomMailslot )
        {
          NlPrintRoutine(
            0x100u,
            L"NetpDcInitializeContext: %ws: cannot create temp mailslot %ld\n",
            *((_QWORD *)v23 + 9),
            RandomMailslot);
          v40 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_33;
          v41 = 71;
          goto LABEL_64;
        }
        if ( !SetMailslotInfo(*((HANDLE *)v23 + 25), 0) )
        {
          LastError = GetLastError();
          NlPrintRoutine(
            0x100u,
            L"NetpDcInitializeContext: %ws: cannot change temp mailslot timeout %ld\n",
            *((_QWORD *)v23 + 9),
            LastError);
          v40 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_33;
          v41 = 72;
          goto LABEL_64;
        }
        if ( *((_DWORD *)v23 + 1) != 5 && (*((_DWORD *)v23 + 3) & 0x1000) == 0 )
          v27 = 0;
        v53 = NetpDcBuildPing(
                v27,
                (char *)v23 + 128,
                *((_QWORD *)v23 + 10),
                *((_QWORD *)v23 + 3),
                v63,
                *((_DWORD *)v23 + 8),
                Sid,
                v49 | 0xAu,
                (char *)v23 + 128,
                (char *)v23 + 136);
        LODWORD(LastError) = v53;
        if ( v53 == 1113 )
        {
          NlPrintRoutine(
            0x100u,
            L"NetpDcInitializeContext: translation error building ping message %ws (ignoring), NetStatus:%lu\n",
            *((_QWORD *)v23 + 9),
            1113);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_SL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              73,
              (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
              *((_QWORD *)v23 + 9),
              89);
        }
        else if ( v53 )
        {
          NlPrintRoutine(
            0x100u,
            L"NetpDcInitializeContext: %ws: cannot build ping message %ld\n",
            *((_QWORD *)v23 + 9),
            v53);
          v40 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_33;
          v41 = 74;
LABEL_64:
          WPP_SF_SL(
            *((_QWORD *)v40 + 2),
            v41,
            (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
            *((_QWORD *)v23 + 9),
            LastError);
          goto LABEL_33;
        }
        if ( *((char *)v23 + 16) < 0
          && ((*((_DWORD *)v23 + 3) & 0x1000) != 0 || *((_QWORD *)v23 + 3) && *((_DWORD *)v23 + 1) == 5) )
        {
          v55 = NetpDcBuildPing(
                  0,
                  v54,
                  *((_QWORD *)v23 + 10),
                  *((_QWORD *)v23 + 3),
                  v63,
                  *((_DWORD *)v23 + 8),
                  Sid,
                  v49 | 0xAu,
                  (char *)v23 + 144,
                  (char *)v23 + 152);
          LODWORD(LastError) = v55;
          if ( v55 )
          {
            NlPrintRoutine(
              0x100u,
              L"NetpDcInitializeContext: %ws: cannot build alternate ping message %ld\n",
              *((_QWORD *)v23 + 9),
              v55);
            v40 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_33;
            v41 = 75;
            goto LABEL_64;
          }
        }
      }
      v56 = NetpDcBuildLdapFilter(
              *((LPCWCH *)v23 + 10),
              *((LPCWCH *)v23 + 11),
              *((LPCWCH *)v23 + 3),
              Sid,
              *((LPCWCH *)v23 + 7),
              *((unsigned __int8 **)v23 + 13),
              *((_DWORD *)v23 + 4),
              v49 | 0x16u,
              (__int64)v23 + 160);
      LODWORD(LastError) = v56;
      if ( v56 )
      {
        NlPrintRoutine(
          0x100u,
          L"NetpDcInitializeContext: %ws: cannot build ldap filter %ld\n",
          *((_QWORD *)v23 + 9),
          v56);
        v40 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_33;
        v41 = 76;
        goto LABEL_64;
      }
      if ( a14 )
      {
        LODWORD(LastError) = NetpDcProcessAddressList(v23, v58, v61, a14, 0, 0);
        if ( (_DWORD)LastError )
          goto LABEL_33;
      }
      *(_DWORD *)v23 |= 2u;
    }
    v26 = 0;
    *v62 = v23;
    goto LABEL_34;
  }
  v24 = LocalAlloc(0x40u, 0x118u);
  hMem = v24;
  if ( v24 )
  {
    v19 = (unsigned __int64)a12;
    v23 = (struct _NL_GETDC_CONTEXT *)v24;
    goto LABEL_6;
  }
  LODWORD(LastError) = 8;
  v26 = 0;
LABEL_34:
  NetpDcUninitializeContext(v26);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180009fb0  push    rbp
0x180009fb2  push    rbx
0x180009fb3  push    rsi
0x180009fb4  push    rdi
0x180009fb5  push    r12
0x180009fb7  push    r13
0x180009fb9  push    r14
0x180009fbb  push    r15
0x180009fbd  lea     rbp, [rsp-0B8h]
0x180009fc5  sub     rsp, 1B8h
0x180009fcc  mov     rax, cs:__security_cookie
0x180009fd3  xor     rax, rsp
0x180009fd6  mov     [rbp+0F0h+var_50], rax
0x180009fdd  mov     rax, [rbp+0F0h+arg_40]
0x180009fe4  mov     rsi, r9
0x180009fe7  mov     r11, [rbp+0F0h+arg_58]
0x180009fee  mov     r13, r8
0x180009ff1  mov     [rsp+1F0h+var_198], rax
0x180009ff6  mov     r12, rdx
0x180009ff9  mov     rax, [rbp+0F0h+arg_60]
0x18000a000  mov     r14, rcx
0x18000a003  mov     [rsp+1F0h+var_178], rax
0x18000a008  mov     rax, [rbp+0F0h+arg_88]
0x18000a00f  mov     [rsp+1F0h+var_190], r11
0x18000a014  mov     [rbp+0F0h+var_170], rax
0x18000a018  mov     [rsp+1F0h+var_188], 0
0x18000a021  mov     rbx, [rax]
0x18000a024  mov     [rsp+1F0h+var_180], 0
0x18000a02d  test    rbx, rbx
0x18000a030  jnz     short loc_18000A05F
0x18000a032  mov     edx, 118h; uBytes
0x18000a037  lea     ecx, [rbx+40h]; uFlags
0x18000a03a  call    cs:__imp_LocalAlloc
0x18000a040  mov     [rsp+1F0h+hMem], rax
0x18000a045  test    rax, rax
0x18000a048  jnz     short loc_18000A055
0x18000a04a  lea     edi, [rbx+8]
0x18000a04d  mov     rcx, rax
0x18000a050  jmp     loc_18000A22B
0x18000a055  mov     r11, [rsp+1F0h+var_190]
0x18000a05a  mov     rbx, rax
0x18000a05d  jmp     short loc_18000A068
0x18000a05f  mov     [rsp+1F0h+hMem], 0
0x18000a068  xor     edi, edi
0x18000a06a  lea     r15d, [rdi+1]
0x18000a06e  test    [rbp+0F0h+arg_80], r15b
0x18000a075  jz      loc_18000A601
0x18000a07b  mov     r8, [rbp+0F0h+arg_30]
0x18000a082  test    r8, r8
0x18000a085  jz      short loc_18000A094
0x18000a087  movzx   eax, word ptr [r8]
0x18000a08b  neg     ax
0x18000a08e  sbb     rcx, rcx
0x18000a091  and     r8, rcx
0x18000a094  mov     r10, [rbp+0F0h+arg_38]
0x18000a09b  test    r10, r10
0x18000a09e  jz      short loc_18000A0AD
0x18000a0a0  movzx   eax, word ptr [r10]
0x18000a0a4  neg     ax
0x18000a0a7  sbb     rcx, rcx
0x18000a0aa  and     r10, rcx
0x18000a0ad  mov     rdx, [rbp+0F0h+arg_28]
0x18000a0b4  test    rdx, rdx
0x18000a0b7  jz      short loc_18000A0C5
0x18000a0b9  movzx   eax, word ptr [rdx]
0x18000a0bc  neg     ax
0x18000a0bf  sbb     rcx, rcx
0x18000a0c2  and     rdx, rcx
0x18000a0c5  mov     r9, [rbp+0F0h+arg_50]
0x18000a0cc  test    r9, r9
0x18000a0cf  jz      short loc_18000A0DE
0x18000a0d1  movzx   eax, word ptr [r9]
0x18000a0d5  neg     ax
0x18000a0d8  sbb     rcx, rcx
0x18000a0db  and     r9, rcx
0x18000a0de  test    r11, r11
0x18000a0e1  jz      short loc_18000A0F5
0x18000a0e3  movzx   eax, word ptr [r11]
0x18000a0e7  neg     ax
0x18000a0ea  sbb     rcx, rcx
0x18000a0ed  and     r11, rcx
0x18000a0f0  mov     [rsp+1F0h+var_190], r11
0x18000a0f5  mov     eax, [rbp+0F0h+arg_20]
0x18000a0fb  test    r8, r8
0x18000a0fe  mov     [rbx+20h], eax
0x18000a101  mov     rax, [rbp+0F0h+arg_48]
0x18000a108  mov     [rbx+30h], rdx
0x18000a10c  cmovnz  rdx, r8
0x18000a110  mov     [rbx+18h], rsi
0x18000a114  mov     esi, [rbp+0F0h+arg_70]
0x18000a11a  mov     [rbx+0E6h], di
0x18000a121  mov     [rbx+38h], r8
0x18000a125  mov     [rbx+40h], r10
0x18000a129  mov     [rbx+60h], r11
0x18000a12d  mov     [rbx+48h], rdx
0x18000a131  mov     [rbx+68h], rax
0x18000a135  mov     eax, [rbp+0F0h+arg_78]
0x18000a13b  mov     [rbx+78h], r14
0x18000a13f  xor     r14d, r14d
0x18000a142  mov     [rbx+10h], eax
0x18000a145  lea     rax, [rbx+0A8h]
0x18000a14c  mov     [rbx+0Ch], esi
0x18000a14f  mov     [rbx+0D8h], r14
0x18000a156  mov     [rax+8], rax
0x18000a15a  mov     [rax], rax
0x18000a15d  mov     [rbx+0BCh], r14d
0x18000a164  mov     [rbx+28h], r9
0x18000a168  test    r9, r9
0x18000a16b  jz      short loc_18000A176
0x18000a16d  test    byte ptr [rbx+10h], 4
0x18000a171  mov     al, r15b
0x18000a174  jz      short loc_18000A179
0x18000a176  mov     al, r14b
0x18000a179  mov     [rbx+0E3h], al
0x18000a17f  cmp     [rbx+18h], r14
0x18000a183  jnz     short loc_18000A189
0x18000a185  mov     [rbx+20h], r14d
0x18000a189  mov     edi, 2
0x18000a18e  lea     rdx, aNetpdcinitiali_1; "NetpDcInitializeContext: DSGETDC_VALID_"...
0x18000a195  mov     ecx, edi; unsigned int
0x18000a197  mov     r8d, 0CFFFFFF1h
0x18000a19d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a1a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1a9  test    byte ptr [rcx+1Ch], 4
0x18000a1ad  jz      short loc_18000A1CE
0x18000a1af  cmp     byte ptr [rcx+19h], 4
0x18000a1b3  jb      short loc_18000A1CE
0x18000a1b5  mov     rcx, [rcx+10h]
0x18000a1b9  lea     edx, [rdi+3Ah]
0x18000a1bc  mov     r9d, 0CFFFFFF1h
0x18000a1c2  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x18000a1c9  call    WPP_SF_l
0x18000a1ce  mov     ecx, [rbx+0Ch]
0x18000a1d1  test    ecx, 3000000Eh
0x18000a1d7  jz      short loc_18000A255
0x18000a1d9  mov     r8, [rbx+48h]
0x18000a1dd  lea     rdx, aNetpdcinitiali_0; "NetpDcInitializeContext: %ws: invalid f"...
0x18000a1e4  mov     r9d, esi
0x18000a1e7  mov     ecx, 100h; unsigned int
0x18000a1ec  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a1f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1f8  test    byte ptr [rcx+1Ch], 4
0x18000a1fc  jz      short loc_18000A221
0x18000a1fe  cmp     [rcx+19h], dil
0x18000a202  jb      short loc_18000A221
0x18000a204  mov     edx, 3Dh ; '='
0x18000a209  mov     r9, [rbx+48h]
0x18000a20d  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x18000a214  mov     rcx, [rcx+10h]
0x18000a218  mov     dword ptr [rsp+1F0h+Sid], esi
0x18000a21c  call    WPP_SF_SL
0x18000a221  mov     edi, 3ECh
0x18000a226  mov     rcx, [rsp+1F0h+hMem]; hMem
0x18000a22b  call    ?NetpDcUninitializeContext@@YAXPEAU_NL_GETDC_CONTEXT@@@Z; NetpDcUninitializeContext(_NL_GETDC_CONTEXT *)
0x18000a230  mov     eax, edi
0x18000a232  mov     rcx, [rbp+0F0h+var_50]
0x18000a239  xor     rcx, rsp; StackCookie
0x18000a23c  call    __security_check_cookie
0x18000a241  add     rsp, 1B8h
0x18000a248  pop     r15
0x18000a24a  pop     r14
0x18000a24c  pop     r13
0x18000a24e  pop     r12
0x18000a250  pop     rdi
0x18000a251  pop     rsi
0x18000a252  pop     rbx
0x18000a253  pop     rbp
0x18000a254  retn
0x18000a255  test    cl, 40h
0x18000a258  jz      short loc_18000A2B8
0x18000a25a  cmp     [rbx+18h], r14
0x18000a25e  jnz     short loc_18000A26D
0x18000a260  cmp     [rbx+20h], r14d
0x18000a264  jnz     short loc_18000A26D
0x18000a266  cmp     [rsp+1F0h+var_198], r14
0x18000a26b  jz      short loc_18000A2B8
0x18000a26d  mov     r8, [rbx+48h]
0x18000a271  lea     rdx, aNetpdcinitiali_7; "NetpDcInitializeContext: %ws: GC querie"...
0x18000a278  mov     ecx, 100h; unsigned int
0x18000a27d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a282  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a289  test    byte ptr [rcx+1Ch], 4
0x18000a28d  jz      short loc_18000A2AE
0x18000a28f  cmp     [rcx+19h], dil
0x18000a293  jb      short loc_18000A2AE
0x18000a295  mov     r9, [rbx+48h]
0x18000a299  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x18000a2a0  mov     rcx, [rcx+10h]
0x18000a2a4  mov     edx, 3Eh ; '>'
0x18000a2a9  call    WPP_SF_S
0x18000a2ae  mov     edi, 57h ; 'W'
0x18000a2b3  jmp     loc_18000A226
0x18000a2b8  bt      ecx, 0Fh
0x18000a2bc  jnb     short loc_18000A2C7
0x18000a2be  and     ecx, 0F007D34Fh; unsigned int
0x18000a2c4  mov     [rbx+0Ch], ecx
0x18000a2c7  mov     edx, ecx
0x18000a2c9  mov     r8d, 0EE80010h
0x18000a2cf  and     edx, r8d
0x18000a2d2  jz      short loc_18000A323
0x18000a2d4  mov     eax, ecx
0x18000a2d6  and     eax, 0FEE80010h
0x18000a2db  neg     eax
0x18000a2dd  and     eax, ecx
0x18000a2df  and     eax, r8d
0x18000a2e2  cmp     eax, edx
0x18000a2e4  jz      short loc_18000A323
0x18000a2e6  mov     r8, [rbx+48h]
0x18000a2ea  lea     rdx, aNetpdcinitiali_14; "NetpDcInitializeContext: %ws: invalid f"...
0x18000a2f1  mov     r9d, esi
0x18000a2f4  mov     ecx, 100h; unsigned int
0x18000a2f9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a2fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a305  test    byte ptr [rcx+1Ch], 4
0x18000a309  jz      loc_18000A221
0x18000a30f  cmp     [rcx+19h], dil
0x18000a313  jb      loc_18000A221
0x18000a319  mov     edx, 3Fh ; '?'
0x18000a31e  jmp     loc_18000A209
0x18000a323  bt      ecx, 18h
0x18000a327  jnb     short loc_18000A36C
0x18000a329  bt      ecx, 0Ah
0x18000a32d  jb      short loc_18000A36C
0x18000a32f  mov     r8, [rbx+48h]
0x18000a333  lea     rdx, aNetpdcinitiali_2; "NetpDcInitializeContext: %ws: invalid f"...
0x18000a33a  mov     r9d, esi
0x18000a33d  mov     ecx, 100h; unsigned int
0x18000a342  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a347  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a34e  test    byte ptr [rcx+1Ch], 4
0x18000a352  jz      loc_18000A221
0x18000a358  cmp     [rcx+19h], dil
0x18000a35c  jb      loc_18000A221
0x18000a362  mov     edx, 40h ; '@'
0x18000a367  jmp     loc_18000A209
0x18000a36c  mov     r9d, 40000h
0x18000a372  cmp     [rbx+0E3h], r14b
0x18000a379  jz      short loc_18000A3BD
0x18000a37b  test    r9d, ecx
0x18000a37e  jz      short loc_18000A3BD
0x18000a380  mov     r8, [rbx+48h]
0x18000a384  lea     rdx, aNetpdcinitiali_4; "NetpDcInitializeContext: %ws: invalid f"...
0x18000a38b  mov     r9d, esi
0x18000a38e  mov     ecx, 100h; unsigned int
0x18000a393  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a398  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a39f  test    byte ptr [rcx+1Ch], 4
0x18000a3a3  jz      loc_18000A221
0x18000a3a9  cmp     [rcx+19h], dil
0x18000a3ad  jb      loc_18000A221
0x18000a3b3  mov     edx, 41h ; 'A'
0x18000a3b8  jmp     loc_18000A209
0x18000a3bd  lea     rdx, [rbx+8]; enum _NL_DNS_NAME_TYPE *
0x18000a3c1  call    ?NetpDcFlagsToNameType@@YAKKPEAW4_NL_DNS_NAME_TYPE@@@Z; NetpDcFlagsToNameType(ulong,_NL_DNS_NAME_TYPE *)
0x18000a3c6  mov     edi, eax
0x18000a3c8  test    eax, eax
0x18000a3ca  jz      short loc_18000A421
0x18000a3cc  mov     r8, [rbx+48h]
0x18000a3d0  lea     rdx, aNetpdcinitiali; "NetpDcInitializeContext: %ws: cannot co"...
0x18000a3d7  mov     r9d, eax
0x18000a3da  mov     ecx, 100h; unsigned int
0x18000a3df  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a3e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3eb  test    byte ptr [rcx+1Ch], 4
0x18000a3ef  jz      loc_18000A226
0x18000a3f5  cmp     byte ptr [rcx+19h], 2
0x18000a3f9  jb      loc_18000A226
0x18000a3ff  mov     edx, 42h ; 'B'
0x18000a404  mov     r9, [rbx+48h]
0x18000a408  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x18000a40f  mov     rcx, [rcx+10h]
0x18000a413  mov     dword ptr [rsp+1F0h+Sid], edi
0x18000a417  call    WPP_SF_SL
0x18000a41c  jmp     loc_18000A226
0x18000a421  movsxd  rcx, dword ptr [rdx]
0x18000a424  lea     rdx, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A; _NL_DNS_NAME_TYPE_DESC near * NlDcDnsNameTypeDesc
0x18000a42b  shl     rcx, 5
0x18000a42f  mov     eax, [rcx+rdx+8]
0x18000a433  mov     [rbx+4], eax
0x18000a436  cmp     dword ptr [rcx+rdx+0Ch], 28h ; '('
0x18000a43b  jnz     short loc_18000A444
0x18000a43d  btr     dword ptr [rbx+0Ch], 12h
0x18000a442  jmp     short loc_18000A49D
0x18000a444  cmp     [rbx+0E3h], r14b
0x18000a44b  jnz     short loc_18000A49D
0x18000a44d  mov     eax, [rbx+0Ch]
0x18000a450  test    r9d, eax
0x18000a453  jnz     short loc_18000A49D
0x18000a455  cmp     cs:dword_1800F1284, r15d
0x18000a45c  jnz     short loc_18000A49D
0x18000a45e  or      eax, r9d
0x18000a461  lea     rdx, aNetpdcinitiali_5; "NetpDcInitializeContext: Using flag DS_"...
0x18000a468  mov     ecx, 2; unsigned int
0x18000a46d  mov     [rbx+0Ch], eax
0x18000a470  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a475  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a47c  test    byte ptr [rcx+1Ch], 4
0x18000a480  jz      short loc_18000A49D
0x18000a482  cmp     byte ptr [rcx+19h], 4
0x18000a486  jb      short loc_18000A49D
  ... truncated ...
```
