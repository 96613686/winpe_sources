# NetpDcInitializeContext(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,void *,_GUID *,ushort const *,ushort const *,_SOCKET_ADDRESS *,ulong,ulong,ulong,ulong,_NL_GETDC_CONTEXT * *)

- ea: `0x18000a564`
- end: `0x18000af70`
- name: `?NetpDcInitializeContext@@YAKPEAXPEBG11K1110PEAU_GUID@@11PEAU_SOCKET_ADDRESS@@KKKKPEAPEAU_NL_GETDC_CONTEXT@@@Z`
- size: `2572`
- prototype: `unsigned int __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, void *, struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, struct _SOCKET_ADDRESS *, unsigned int, unsigned int, unsigned int, char, struct _NL_GETDC_CONTEXT **)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005b9cc`
- `0x18006b750`
- `0x18007ea48`

## callees

- `0x180002cc0`
- `0x180007518`
- `0x18000a564`
- `0x18000af78`
- `0x18000e910`
- `0x180018f38`
- `0x18001906c`
- `0x18007a940`
- `0x18007d970`
- `0x18007db70`
- `0x18007dd80`
- `0x180082a84`
- `0x180084098`
- `0x180084eac`
- `0x180089dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac9f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a5ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ac12`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a5ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ac12`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetMailslotInfo` at `0x18000ac8f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetMailslotInfo` at `0x18000ac8f`

## string_xrefs

- `0x18000a8a5`: `NetpDcInitializeContext: %ws: invalid flag, DS_DIRECTORY_SERVICE_{[6|8|9|10|12|13|14]_}REQUIRED flags are mutually exclusive %lx\n`
- `0x18000aa1c`: `NetpDcInitializeContext: Using flag DS_TRY_NEXTCLOSEST_SITE due to registry/policy TryNextClosestSite\n`
- `0x18000aa73`: `NetpDcInitializeContext: %ws: flags not compatible with 'Good Time' %lx\n`
- `0x18000ac51`: `NetpDcInitializeContext: %ws: cannot create temp mailslot %ld\n`
- `0x18000acaf`: `NetpDcInitializeContext: %ws: cannot change temp mailslot timeout %ld\n`

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
        unsigned __int8 *Sid,
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
          &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
          (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
            &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
        if ( (v43 & v39) == 0 && dword_1800F8284 == 1 )
        {
          *((_DWORD *)v23 + 3) = v39 | v43;
          NlPrintRoutine(
            2u,
            L"NetpDcInitializeContext: Using flag DS_TRY_NEXTCLOSEST_SITE due to registry/policy TryNextClosestSite\n");
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids);
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
        LODWORD(LastError) = NetpGetComputerNameEx2((LPVOID *)&v59, ComputerNamePhysicalNetBIOS);
        if ( (_DWORD)LastError )
          goto LABEL_33;
        a2 = v59;
        *((_BYTE *)v23 + 230) = 1;
      }
      *((_QWORD *)v23 + 10) = a2;
      if ( !a3 )
      {
        LODWORD(LastError) = NetpGetComputerNameEx2((LPVOID *)&v60, ComputerNameDnsFullyQualified);
        if ( (_DWORD)LastError )
          goto LABEL_33;
        a3 = v60;
        *((_BYTE *)v23 + 231) = 1;
      }
      v45 = (const unsigned __int16 *)*((_QWORD *)v23 + 7);
      v46 = (const unsigned __int16 *)*((_QWORD *)v23 + 6);
      *((_QWORD *)v23 + 11) = a3;
      *((_BYTE *)v23 + 232) = dword_1800F81B4 == 2;
      DomainEntry = NetpDcCreateDomainEntry(*((struct _GUID **)v23 + 13), v46, v45);
      *((_QWORD *)v23 + 14) = DomainEntry;
      if ( !DomainEntry )
      {
        NlPrintRoutine(0x100u, L"NetpDcInitializeContext: not enough memory for DomainEntry.\n");
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids);
        goto LABEL_91;
      }
      *(_DWORD *)v23 |= 1u;
      *((_DWORD *)v23 + 68) = dword_1800F8298;
      *((_DWORD *)v23 + 69) = dword_1800F829C;
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
              (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
            (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
              *((_DWORD *)v23 + 8),
              Sid,
              *((LPCWCH *)v23 + 7),
              *((unsigned __int8 **)v23 + 13),
              *((_DWORD *)v23 + 4),
              v49 | 0x16u,
              (_QWORD *)v23 + 20);
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
0x18000a564  push    rbp
0x18000a566  push    rbx
0x18000a567  push    rsi
0x18000a568  push    rdi
0x18000a569  push    r12
0x18000a56b  push    r13
0x18000a56d  push    r14
0x18000a56f  push    r15
0x18000a571  lea     rbp, [rsp-0B8h]
0x18000a579  sub     rsp, 1B8h
0x18000a580  mov     rax, cs:__security_cookie
0x18000a587  xor     rax, rsp
0x18000a58a  mov     [rbp+0F0h+var_50], rax
0x18000a591  mov     rax, [rbp+0F0h+arg_40]
0x18000a598  mov     rsi, r9
0x18000a59b  mov     r11, [rbp+0F0h+arg_58]
0x18000a5a2  mov     r13, r8
0x18000a5a5  mov     [rsp+1F0h+var_198], rax
0x18000a5aa  mov     r12, rdx
0x18000a5ad  mov     rax, [rbp+0F0h+arg_60]
0x18000a5b4  mov     r14, rcx
0x18000a5b7  mov     [rsp+1F0h+var_178], rax
0x18000a5bc  mov     rax, [rbp+0F0h+arg_88]
0x18000a5c3  mov     [rsp+1F0h+var_190], r11
0x18000a5c8  mov     [rbp+0F0h+var_170], rax
0x18000a5cc  mov     [rsp+1F0h+var_188], 0
0x18000a5d5  mov     rbx, [rax]
0x18000a5d8  mov     [rsp+1F0h+var_180], 0
0x18000a5e1  test    rbx, rbx
0x18000a5e4  jnz     short loc_18000A619
0x18000a5e6  mov     edx, 118h; uBytes
0x18000a5eb  lea     ecx, [rbx+40h]; uFlags
0x18000a5ee  call    cs:__imp_LocalAlloc
0x18000a5f5  nop     dword ptr [rax+rax+00h]
0x18000a5fa  mov     [rsp+1F0h+hMem], rax
0x18000a5ff  test    rax, rax
0x18000a602  jnz     short loc_18000A60F
0x18000a604  lea     edi, [rbx+8]
0x18000a607  mov     rcx, rax
0x18000a60a  jmp     loc_18000A7E5
0x18000a60f  mov     r11, [rsp+1F0h+var_190]
0x18000a614  mov     rbx, rax
0x18000a617  jmp     short loc_18000A622
0x18000a619  mov     [rsp+1F0h+hMem], 0
0x18000a622  xor     edi, edi
0x18000a624  lea     r15d, [rdi+1]
0x18000a628  test    [rbp+0F0h+arg_80], r15b
0x18000a62f  jz      loc_18000ABBC
0x18000a635  mov     r8, [rbp+0F0h+arg_30]
0x18000a63c  test    r8, r8
0x18000a63f  jz      short loc_18000A64E
0x18000a641  movzx   eax, word ptr [r8]
0x18000a645  neg     ax
0x18000a648  sbb     rcx, rcx
0x18000a64b  and     r8, rcx
0x18000a64e  mov     r10, [rbp+0F0h+arg_38]
0x18000a655  test    r10, r10
0x18000a658  jz      short loc_18000A667
0x18000a65a  movzx   eax, word ptr [r10]
0x18000a65e  neg     ax
0x18000a661  sbb     rcx, rcx
0x18000a664  and     r10, rcx
0x18000a667  mov     rdx, [rbp+0F0h+arg_28]
0x18000a66e  test    rdx, rdx
0x18000a671  jz      short loc_18000A67F
0x18000a673  movzx   eax, word ptr [rdx]
0x18000a676  neg     ax
0x18000a679  sbb     rcx, rcx
0x18000a67c  and     rdx, rcx
0x18000a67f  mov     r9, [rbp+0F0h+arg_50]
0x18000a686  test    r9, r9
0x18000a689  jz      short loc_18000A698
0x18000a68b  movzx   eax, word ptr [r9]
0x18000a68f  neg     ax
0x18000a692  sbb     rcx, rcx
0x18000a695  and     r9, rcx
0x18000a698  test    r11, r11
0x18000a69b  jz      short loc_18000A6AF
0x18000a69d  movzx   eax, word ptr [r11]
0x18000a6a1  neg     ax
0x18000a6a4  sbb     rcx, rcx
0x18000a6a7  and     r11, rcx
0x18000a6aa  mov     [rsp+1F0h+var_190], r11
0x18000a6af  mov     eax, [rbp+0F0h+arg_20]
0x18000a6b5  test    r8, r8
0x18000a6b8  mov     [rbx+20h], eax
0x18000a6bb  mov     rax, [rbp+0F0h+arg_48]
0x18000a6c2  mov     [rbx+30h], rdx
0x18000a6c6  cmovnz  rdx, r8
0x18000a6ca  mov     [rbx+18h], rsi
0x18000a6ce  mov     esi, [rbp+0F0h+arg_70]
0x18000a6d4  mov     [rbx+0E6h], di
0x18000a6db  mov     [rbx+38h], r8
0x18000a6df  mov     [rbx+40h], r10
0x18000a6e3  mov     [rbx+60h], r11
0x18000a6e7  mov     [rbx+48h], rdx
0x18000a6eb  mov     [rbx+68h], rax
0x18000a6ef  mov     eax, [rbp+0F0h+arg_78]
0x18000a6f5  mov     [rbx+78h], r14
0x18000a6f9  xor     r14d, r14d
0x18000a6fc  mov     [rbx+10h], eax
0x18000a6ff  lea     rax, [rbx+0A8h]
0x18000a706  mov     [rbx+0Ch], esi
0x18000a709  mov     [rbx+0D8h], r14
0x18000a710  mov     [rax+8], rax
0x18000a714  mov     [rax], rax
0x18000a717  mov     [rbx+0BCh], r14d
0x18000a71e  mov     [rbx+28h], r9
0x18000a722  test    r9, r9
0x18000a725  jz      short loc_18000A730
0x18000a727  test    byte ptr [rbx+10h], 4
0x18000a72b  mov     al, r15b
0x18000a72e  jz      short loc_18000A733
0x18000a730  mov     al, r14b
0x18000a733  mov     [rbx+0E3h], al
0x18000a739  cmp     [rbx+18h], r14
0x18000a73d  jnz     short loc_18000A743
0x18000a73f  mov     [rbx+20h], r14d
0x18000a743  mov     edi, 2
0x18000a748  lea     rdx, aNetpdcinitiali_1; "NetpDcInitializeContext: DSGETDC_VALID_"...
0x18000a74f  mov     ecx, edi; unsigned int
0x18000a751  mov     r8d, 0CFFFFFF1h
0x18000a757  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a75c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a763  test    byte ptr [rcx+1Ch], 4
0x18000a767  jz      short loc_18000A788
0x18000a769  cmp     byte ptr [rcx+19h], 4
0x18000a76d  jb      short loc_18000A788
0x18000a76f  mov     rcx, [rcx+10h]
0x18000a773  lea     edx, [rdi+3Ah]
0x18000a776  mov     r9d, 0CFFFFFF1h
0x18000a77c  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x18000a783  call    WPP_SF_l
0x18000a788  mov     ecx, [rbx+0Ch]
0x18000a78b  test    ecx, 3000000Eh
0x18000a791  jz      short loc_18000A810
0x18000a793  mov     r8, [rbx+48h]
0x18000a797  lea     rdx, aNetpdcinitiali_0; "NetpDcInitializeContext: %ws: invalid f"...
0x18000a79e  mov     r9d, esi
0x18000a7a1  mov     ecx, 100h; unsigned int
0x18000a7a6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a7ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7b2  test    byte ptr [rcx+1Ch], 4
0x18000a7b6  jz      short loc_18000A7DB
0x18000a7b8  cmp     [rcx+19h], dil
0x18000a7bc  jb      short loc_18000A7DB
0x18000a7be  mov     edx, 3Dh ; '='
0x18000a7c3  mov     r9, [rbx+48h]
0x18000a7c7  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x18000a7ce  mov     rcx, [rcx+10h]
0x18000a7d2  mov     dword ptr [rsp+1F0h+Sid], esi
0x18000a7d6  call    WPP_SF_SL
0x18000a7db  mov     edi, 3ECh
0x18000a7e0  mov     rcx, [rsp+1F0h+hMem]; hMem
0x18000a7e5  call    ?NetpDcUninitializeContext@@YAXPEAU_NL_GETDC_CONTEXT@@@Z; NetpDcUninitializeContext(_NL_GETDC_CONTEXT *)
0x18000a7ea  mov     eax, edi
0x18000a7ec  mov     rcx, [rbp+0F0h+var_50]
0x18000a7f3  xor     rcx, rsp; StackCookie
0x18000a7f6  call    __security_check_cookie
0x18000a7fb  add     rsp, 1B8h
0x18000a802  pop     r15
0x18000a804  pop     r14
0x18000a806  pop     r13
0x18000a808  pop     r12
0x18000a80a  pop     rdi
0x18000a80b  pop     rsi
0x18000a80c  pop     rbx
0x18000a80d  pop     rbp
0x18000a80e  retn
0x18000a810  test    cl, 40h
0x18000a813  jz      short loc_18000A873
0x18000a815  cmp     [rbx+18h], r14
0x18000a819  jnz     short loc_18000A828
0x18000a81b  cmp     [rbx+20h], r14d
0x18000a81f  jnz     short loc_18000A828
0x18000a821  cmp     [rsp+1F0h+var_198], r14
0x18000a826  jz      short loc_18000A873
0x18000a828  mov     r8, [rbx+48h]
0x18000a82c  lea     rdx, aNetpdcinitiali_7; "NetpDcInitializeContext: %ws: GC querie"...
0x18000a833  mov     ecx, 100h; unsigned int
0x18000a838  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a83d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a844  test    byte ptr [rcx+1Ch], 4
0x18000a848  jz      short loc_18000A869
0x18000a84a  cmp     [rcx+19h], dil
0x18000a84e  jb      short loc_18000A869
0x18000a850  mov     r9, [rbx+48h]
0x18000a854  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x18000a85b  mov     rcx, [rcx+10h]
0x18000a85f  mov     edx, 3Eh ; '>'
0x18000a864  call    WPP_SF_S
0x18000a869  mov     edi, 57h ; 'W'
0x18000a86e  jmp     loc_18000A7E0
0x18000a873  bt      ecx, 0Fh
0x18000a877  jnb     short loc_18000A882
0x18000a879  and     ecx, 0F007D34Fh; unsigned int
0x18000a87f  mov     [rbx+0Ch], ecx
0x18000a882  mov     edx, ecx
0x18000a884  mov     r8d, 0EE80010h
0x18000a88a  and     edx, r8d
0x18000a88d  jz      short loc_18000A8DE
0x18000a88f  mov     eax, ecx
0x18000a891  and     eax, 0FEE80010h
0x18000a896  neg     eax
0x18000a898  and     eax, ecx
0x18000a89a  and     eax, r8d
0x18000a89d  cmp     eax, edx
0x18000a89f  jz      short loc_18000A8DE
0x18000a8a1  mov     r8, [rbx+48h]
0x18000a8a5  lea     rdx, aNetpdcinitiali_14; "NetpDcInitializeContext: %ws: invalid f"...
0x18000a8ac  mov     r9d, esi
0x18000a8af  mov     ecx, 100h; unsigned int
0x18000a8b4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a8b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8c0  test    byte ptr [rcx+1Ch], 4
0x18000a8c4  jz      loc_18000A7DB
0x18000a8ca  cmp     [rcx+19h], dil
0x18000a8ce  jb      loc_18000A7DB
0x18000a8d4  mov     edx, 3Fh ; '?'
0x18000a8d9  jmp     loc_18000A7C3
0x18000a8de  bt      ecx, 18h
0x18000a8e2  jnb     short loc_18000A927
0x18000a8e4  bt      ecx, 0Ah
0x18000a8e8  jb      short loc_18000A927
0x18000a8ea  mov     r8, [rbx+48h]
0x18000a8ee  lea     rdx, aNetpdcinitiali_2; "NetpDcInitializeContext: %ws: invalid f"...
0x18000a8f5  mov     r9d, esi
0x18000a8f8  mov     ecx, 100h; unsigned int
0x18000a8fd  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a902  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a909  test    byte ptr [rcx+1Ch], 4
0x18000a90d  jz      loc_18000A7DB
0x18000a913  cmp     [rcx+19h], dil
0x18000a917  jb      loc_18000A7DB
0x18000a91d  mov     edx, 40h ; '@'
0x18000a922  jmp     loc_18000A7C3
0x18000a927  mov     r9d, 40000h
0x18000a92d  cmp     [rbx+0E3h], r14b
0x18000a934  jz      short loc_18000A978
0x18000a936  test    r9d, ecx
0x18000a939  jz      short loc_18000A978
0x18000a93b  mov     r8, [rbx+48h]
0x18000a93f  lea     rdx, aNetpdcinitiali_4; "NetpDcInitializeContext: %ws: invalid f"...
0x18000a946  mov     r9d, esi
0x18000a949  mov     ecx, 100h; unsigned int
0x18000a94e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a953  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a95a  test    byte ptr [rcx+1Ch], 4
0x18000a95e  jz      loc_18000A7DB
0x18000a964  cmp     [rcx+19h], dil
0x18000a968  jb      loc_18000A7DB
0x18000a96e  mov     edx, 41h ; 'A'
0x18000a973  jmp     loc_18000A7C3
0x18000a978  lea     rdx, [rbx+8]; enum _NL_DNS_NAME_TYPE *
0x18000a97c  call    ?NetpDcFlagsToNameType@@YAKKPEAW4_NL_DNS_NAME_TYPE@@@Z; NetpDcFlagsToNameType(ulong,_NL_DNS_NAME_TYPE *)
0x18000a981  mov     edi, eax
0x18000a983  test    eax, eax
0x18000a985  jz      short loc_18000A9DC
0x18000a987  mov     r8, [rbx+48h]
0x18000a98b  lea     rdx, aNetpdcinitiali; "NetpDcInitializeContext: %ws: cannot co"...
0x18000a992  mov     r9d, eax
0x18000a995  mov     ecx, 100h; unsigned int
0x18000a99a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000a99f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9a6  test    byte ptr [rcx+1Ch], 4
0x18000a9aa  jz      loc_18000A7E0
0x18000a9b0  cmp     byte ptr [rcx+19h], 2
0x18000a9b4  jb      loc_18000A7E0
0x18000a9ba  mov     edx, 42h ; 'B'
0x18000a9bf  mov     r9, [rbx+48h]
0x18000a9c3  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x18000a9ca  mov     rcx, [rcx+10h]
0x18000a9ce  mov     dword ptr [rsp+1F0h+Sid], edi
0x18000a9d2  call    WPP_SF_SL
0x18000a9d7  jmp     loc_18000A7E0
0x18000a9dc  movsxd  rcx, dword ptr [rdx]
0x18000a9df  lea     rdx, ?NlDcDnsNameTypeDesc@@3PAU_NL_DNS_NAME_TYPE_DESC@@A; _NL_DNS_NAME_TYPE_DESC near * NlDcDnsNameTypeDesc
0x18000a9e6  shl     rcx, 5
0x18000a9ea  mov     eax, [rcx+rdx+8]
0x18000a9ee  mov     [rbx+4], eax
0x18000a9f1  cmp     dword ptr [rcx+rdx+0Ch], 28h ; '('
0x18000a9f6  jnz     short loc_18000A9FF
0x18000a9f8  btr     dword ptr [rbx+0Ch], 12h
0x18000a9fd  jmp     short loc_18000AA58
0x18000a9ff  cmp     [rbx+0E3h], r14b
0x18000aa06  jnz     short loc_18000AA58
0x18000aa08  mov     eax, [rbx+0Ch]
0x18000aa0b  test    r9d, eax
0x18000aa0e  jnz     short loc_18000AA58
0x18000aa10  cmp     cs:dword_1800F8284, r15d
0x18000aa17  jnz     short loc_18000AA58
0x18000aa19  or      eax, r9d
0x18000aa1c  lea     rdx, aNetpdcinitiali_5; "NetpDcInitializeContext: Using flag DS_"...
0x18000aa23  mov     ecx, 2; unsigned int
0x18000aa28  mov     [rbx+0Ch], eax
0x18000aa2b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18000aa30  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa37  test    byte ptr [rcx+1Ch], 4
0x18000aa3b  jz      short loc_18000AA58
0x18000aa3d  cmp     byte ptr [rcx+19h], 4
  ... truncated ...
```
