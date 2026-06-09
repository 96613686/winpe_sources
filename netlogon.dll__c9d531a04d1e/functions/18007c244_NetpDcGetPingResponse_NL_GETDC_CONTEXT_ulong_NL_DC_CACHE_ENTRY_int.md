# NetpDcGetPingResponse(_NL_GETDC_CONTEXT *,ulong,_NL_DC_CACHE_ENTRY * *,int *)

- ea: `0x18007c244`
- end: `0x18007ca26`
- name: `?NetpDcGetPingResponse@@YAKPEAU_NL_GETDC_CONTEXT@@KPEAPEAU_NL_DC_CACHE_ENTRY@@PEAH@Z`
- size: `2018`
- prototype: `__int64 __fastcall(struct _NL_GETDC_CONTEXT *, unsigned int, struct _NL_DC_CACHE_ENTRY **, int *)`
- caller_count: `7`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x18000b1c4`
- `0x180066108`
- `0x180078f00`
- `0x18007af44`
- `0x18007b398`
- `0x18007ba90`
- `0x18007ca2c`

## callees

- `0x180007278`
- `0x18000cbe0`
- `0x180018414`
- `0x18001843c`
- `0x1800184c8`
- `0x180074f80`
- `0x1800782b8`
- `0x1800787c4`
- `0x180078d9c`
- `0x18007c244`
- `0x18007e2f0`
- `0x18007e350`
- `0x18007e564`
- `0x18007e7dc`
- `0x180080670`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c817`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007c9d7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18007c9d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007c284`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007c284`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007c80d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18007c80d`
- `WLDAP32!__imp_LdapGetLastError` at `0x18007c40a`
- `WLDAP32!__imp_LdapGetLastError` at `0x18007c6aa`
- `WLDAP32!__imp_LdapGetLastError` at `0x18007c40a`
- `WLDAP32!__imp_LdapGetLastError` at `0x18007c6aa`
- `WLDAP32!__imp_ldap_first_entry` at `0x18007c607`
- `WLDAP32!__imp_ldap_first_entry` at `0x18007c607`
- `WLDAP32!__imp_ldap_count_entries` at `0x18007c5c7`
- `WLDAP32!__imp_ldap_count_entries` at `0x18007c5c7`
- `WLDAP32!__imp_ldap_result` at `0x18007c3b1`
- `WLDAP32!__imp_ldap_result` at `0x18007c3b1`
- `WLDAP32!__imp_ldap_msgfree` at `0x18007c2f0`
- `WLDAP32!__imp_ldap_msgfree` at `0x18007ca0d`
- `WLDAP32!__imp_ldap_msgfree` at `0x18007c2f0`
- `WLDAP32!__imp_ldap_msgfree` at `0x18007ca0d`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18007c2d7`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18007c9fe`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18007c2d7`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18007c9fe`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18007c427`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18007c45d`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18007c6bc`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18007c6ff`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18007c427`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18007c45d`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18007c6bc`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18007c6ff`
- `WLDAP32!__imp_ldap_get_values_lenA` at `0x18007c698`
- `WLDAP32!__imp_ldap_get_values_lenA` at `0x18007c698`

## string_xrefs

- `0x18007c620`: `NetpDcGetPingResponse: %ws: Netlogon service stopped on DC at %hs\n`
- `0x18007c82c`: `NetpDcGetPingResponse: %ws: cannot read temp mailslot timeout %ld\n`

## pseudocode

```c
__int64 __fastcall NetpDcGetPingResponse(
        struct _NL_GETDC_CONTEXT *a1,
        unsigned int a2,
        struct _NL_DC_CACHE_ENTRY **a3,
        int *a4)
{
  struct berval **v4; // r12
  DWORD TickCount; // eax
  __int64 **v8; // r14
  struct _NL_DC_ADDRESS *v9; // r13
  unsigned int v10; // eax
  __int64 v11; // r8
  __int64 *v12; // rbx
  ScannerInfoNameMappings *v13; // r10
  __int64 v14; // rsi
  int v15; // edx
  ULONG v16; // r9d
  ULONG LastError; // esi
  PCHAR v18; // rax
  PCHAR v19; // rax
  int v20; // eax
  unsigned int v21; // edx
  __int64 v22; // rcx
  LDAPMessage *entry; // rax
  int v24; // eax
  struct berval **values_lenA; // rax
  ULONG v26; // eax
  ULONG v27; // esi
  PCHAR v28; // rax
  PCHAR v29; // rax
  int v30; // eax
  struct berval *v31; // rax
  PCHAR bv_val; // rsi
  unsigned int v33; // r14d
  DWORD bv_len; // eax
  void *v35; // rcx
  DWORD v36; // eax
  unsigned int v37; // ebx
  unsigned int v38; // eax
  __int64 *v39; // r14
  int v40; // eax
  unsigned int v41; // esi
  unsigned int v42; // ebx
  DWORD v43; // ecx
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-48h]
  unsigned int v46; // [rsp+40h] [rbp-28h]
  LDAPMessage *res; // [rsp+48h] [rbp-20h] BYREF
  struct l_timeval timeout; // [rsp+50h] [rbp-18h] BYREF
  __int64 *v49; // [rsp+58h] [rbp-10h]
  unsigned int v50; // [rsp+B0h] [rbp+48h]
  DWORD NumberOfBytesRead; // [rsp+B8h] [rbp+50h] BYREF
  struct _NL_DC_CACHE_ENTRY **v52; // [rsp+C0h] [rbp+58h]
  int *v53; // [rsp+C8h] [rbp+60h]

  v53 = a4;
  v52 = a3;
  v4 = 0;
  NumberOfBytesRead = 0;
  *a3 = 0;
  timeout = 0;
  res = 0;
  TickCount = GetTickCount();
  v50 = TickCount;
  if ( a2 < 0x64 && (*((_DWORD *)a1 + 4) & 0x300) == 0 )
    a2 = 100;
  while ( 2 )
  {
    v8 = (__int64 **)((char *)a1 + 168);
    while ( 2 )
    {
      v9 = 0;
      v10 = NetpDcElapsedTime(TickCount);
      v12 = *v8;
      v46 = v10;
      v49 = 0;
      if ( v12 == (__int64 *)v8 )
        break;
      v13 = WPP_GLOBAL_Control;
      while ( 1 )
      {
        if ( v4 )
        {
          ldap_value_free_len(v4);
          v13 = WPP_GLOBAL_Control;
          v4 = 0;
        }
        if ( res )
        {
          ldap_msgfree(res);
          v13 = WPP_GLOBAL_Control;
          res = 0;
        }
        if ( !v12[30] )
          goto LABEL_72;
        if ( (*((_BYTE *)v13 + 28) & 4) != 0 && *((_BYTE *)v13 + 25) >= 5u )
        {
          WPP_SF_d(
            *((_QWORD *)v13 + 2),
            15,
            &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
            *((unsigned int *)v12 + 65));
          v13 = WPP_GLOBAL_Control;
        }
        v14 = 0;
        if ( *((_DWORD *)v12 + 65) )
        {
          while ( 1 )
          {
            timeout = 0;
            if ( (*((_BYTE *)v13 + 28) & 4) != 0 && *((_BYTE *)v13 + 25) >= 5u )
            {
              v15 = *(_DWORD *)(v12[31] + 4 * v14);
              WPP_SF_SsDd(*((_QWORD *)v13 + 2), v15, v11, *((_QWORD *)a1 + 9), (__int64)(v12 + 21), v15, v15);
            }
            v16 = ldap_result(*(LDAP **)v12[30], *(_DWORD *)(v12[31] + 4 * v14), 1u, &timeout, &res);
            if ( v16 )
              break;
            v13 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids);
              v13 = WPP_GLOBAL_Control;
            }
            v14 = (unsigned int)(v14 + 1);
            if ( (unsigned int)v14 >= *((_DWORD *)v12 + 65) )
              goto LABEL_45;
          }
          if ( v16 == -1 )
          {
            LastError = LdapGetLastError();
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v18 = ldap_err2stringA(LastError);
              WPP_SF_Ssls(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)(v12 + 21), LastError, (__int64)v18);
            }
            v19 = ldap_err2stringA(LastError);
            LODWORD(lpOverlapped) = LastError;
            NlPrintRoutine(
              0x100u,
              L"NetpDcGetPingResponse: %ws: Cannot ldap_result ip address %hs: %ld %hs\n",
              *((_QWORD *)a1 + 9),
              v12 + 21,
              lpOverlapped,
              v19);
            if ( LastError == 85 )
            {
              v20 = *((_DWORD *)v12 + 67);
              if ( (v20 & 1) == 0 )
              {
                *((_DWORD *)v12 + 67) = v20 | 1;
                --*((_DWORD *)a1 + 47);
              }
            }
            NetpCancelOutstandingRequests((struct _NL_DC_ADDRESS *)v12);
            NlReleaseLocatorLdapConnection((struct _CACHED_CONNECTION *)v12[30]);
            v12[30] = 0;
          }
          else
          {
            v13 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_DdDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids);
              v13 = WPP_GLOBAL_Control;
            }
            v21 = *((_DWORD *)v12 + 65);
            if ( !v21 )
              goto LABEL_45;
            v11 = v12[31];
            v22 = 0;
            while ( *(_DWORD *)(v11 + 4 * v22) != *(_DWORD *)(v11 + 4 * v14) )
            {
              v22 = (unsigned int)(v22 + 1);
              if ( (unsigned int)v22 >= v21 )
                goto LABEL_45;
            }
            if ( (unsigned int)v22 < v21 - 1 )
            {
              do
              {
                v11 = (unsigned int)(v22 + 1);
                *(_DWORD *)(v12[31] + 4 * v22) = *(_DWORD *)(v12[31] + 4 * v11);
                v22 = v11;
              }
              while ( (unsigned int)v11 < *((_DWORD *)v12 + 65) - 1 );
            }
            *(_DWORD *)(v12[31] + 4LL * (unsigned int)--*((_DWORD *)v12 + 65)) = 0;
          }
          v13 = WPP_GLOBAL_Control;
LABEL_45:
          v8 = (__int64 **)((char *)a1 + 168);
        }
        if ( res )
          break;
        if ( (*((_BYTE *)v13 + 28) & 4) == 0 || *((_BYTE *)v13 + 25) < 5u )
          goto LABEL_72;
        WPP_SF_(*((_QWORD *)v13 + 2), 20, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids);
LABEL_71:
        v13 = WPP_GLOBAL_Control;
LABEL_72:
        v12 = (__int64 *)*v12;
        if ( v12 == (__int64 *)v8 )
          goto LABEL_77;
      }
      ldap_count_entries(*(LDAP **)v12[30], res);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 2));
      entry = ldap_first_entry(*(LDAP **)v12[30], res);
      if ( !entry )
      {
        NlPrintRoutine(
          0x2000000u,
          L"NetpDcGetPingResponse: %ws: Netlogon service stopped on DC at %hs\n",
          *((_QWORD *)a1 + 9),
          v12 + 21);
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_Ss(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
            *((_QWORD *)a1 + 9),
            (__int64)(v12 + 21));
        v24 = *((_DWORD *)v12 + 67);
        if ( (v24 & 1) == 0 )
        {
          *((_DWORD *)v12 + 67) = v24 | 1;
          --*((_DWORD *)a1 + 47);
        }
LABEL_69:
        NetpCancelOutstandingRequests((struct _NL_DC_ADDRESS *)v12);
        NlReleaseLocatorLdapConnection((struct _CACHED_CONNECTION *)v12[30]);
LABEL_70:
        v12[30] = 0;
        goto LABEL_71;
      }
      values_lenA = ldap_get_values_lenA(*(LDAP **)v12[30], entry, (const PSTR)"Netlogon");
      v4 = values_lenA;
      if ( !values_lenA )
      {
        v26 = LdapGetLastError();
        v27 = v26;
        if ( v26 )
        {
          v28 = ldap_err2stringA(v26);
          LODWORD(lpOverlapped) = v27;
          NlPrintRoutine(
            0x100u,
            L"NetpDcGetPingResponse: %ws: Cannot ldap_get_values_len ip address %hs: %ld %hs\n",
            *((_QWORD *)a1 + 9),
            v12 + 21,
            lpOverlapped,
            v28);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v29 = ldap_err2stringA(v27);
            WPP_SF_Ssls(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)(v12 + 21), v27, (__int64)v29);
          }
          if ( v27 == 16 )
          {
            v30 = *((_DWORD *)v12 + 67);
            if ( (v30 & 1) == 0 )
            {
              *((_DWORD *)v12 + 67) = v30 | 1;
              --*((_DWORD *)a1 + 47);
            }
          }
        }
        NetpCancelOutstandingRequests((struct _NL_DC_ADDRESS *)v12);
        NlReleaseLocatorLdapConnection((struct _CACHED_CONNECTION *)v12[30]);
        v8 = (__int64 **)((char *)a1 + 168);
        goto LABEL_70;
      }
      v31 = *values_lenA;
      if ( !v31 )
        goto LABEL_69;
      bv_val = v31->bv_val;
      v33 = 2;
      bv_len = v31->bv_len;
      if ( *((_DWORD *)v12 + 8) )
        v9 = (struct _NL_DC_ADDRESS *)v12;
      NumberOfBytesRead = bv_len;
      v49 = v12;
      NetpCancelOutstandingRequests((struct _NL_DC_ADDRESS *)v12);
      NlReleaseLocatorLdapConnection((struct _CACHED_CONNECTION *)v12[30]);
      v12[30] = 0;
      if ( bv_val )
      {
LABEL_84:
        v38 = NetpDcHandlePingResponse(a1, bv_val, NumberOfBytesRead, v33, v9, v52, v53);
        v37 = v38;
        if ( (*((_DWORD *)a1 + 4) & 0x300) != 0 )
        {
          if ( v38 == 121 )
            v37 = 13;
        }
        else
        {
          if ( v38 == 13 )
            goto LABEL_94;
          if ( v38 == 121 || v38 == 1317 )
          {
            v39 = v49;
            if ( v49 )
            {
              NlPrintRoutine(
                0x2000000u,
                L"NetpDcGetPingResponse: %ws: marked DC as NeverTryAgain %ld\n",
                *((_QWORD *)a1 + 9),
                v38);
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                WPP_SF_SL(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  25,
                  (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
                  *((_QWORD *)a1 + 9),
                  v37);
              v40 = *((_DWORD *)v39 + 67);
              if ( (v40 & 1) == 0 )
              {
                *((_DWORD *)v39 + 67) = v40 | 1;
                --*((_DWORD *)a1 + 47);
              }
            }
LABEL_94:
            TickCount = v50;
            v8 = (__int64 **)((char *)a1 + 168);
            continue;
          }
        }
        goto LABEL_107;
      }
      break;
    }
LABEL_77:
    v35 = (void *)*((_QWORD *)a1 + 25);
    if ( !v35 )
      goto LABEL_95;
    if ( ReadFile(v35, *((LPVOID *)a1 + 30), *((_DWORD *)a1 + 62), &NumberOfBytesRead, 0) )
    {
      bv_val = (PCHAR)*((_QWORD *)a1 + 30);
      v33 = 1;
      if ( !bv_val )
        goto LABEL_95;
      goto LABEL_84;
    }
    v36 = GetLastError();
    v37 = v36;
    if ( v36 != 121 )
    {
      NlPrintRoutine(
        0x100u,
        L"NetpDcGetPingResponse: %ws: cannot read temp mailslot timeout %ld\n",
        *((_QWORD *)a1 + 9),
        v36);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_SL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
          *((_QWORD *)a1 + 9),
          v37);
      goto LABEL_107;
    }
LABEL_95:
    v41 = NetpDcElapsedTime(v50);
    if ( v41 != v46 )
    {
      v42 = v41 - v46;
      if ( v41 - v46 > 0x19 )
      {
        NlPrintRoutine(0x100u, L"NetpDcGetPingResponse: it took %ld msecs to poll\n", v42);
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids, v42);
      }
    }
    if ( v41 < a2 )
    {
      v43 = *((_BYTE *)a1 + 232) != 0 ? 50 : 100;
      if ( a2 - v41 < v43 )
        v43 = a2 - v41;
      Sleep(v43);
      TickCount = v50;
      continue;
    }
    break;
  }
  v37 = 121;
LABEL_107:
  if ( v4 )
    ldap_value_free_len(v4);
  if ( res )
    ldap_msgfree(res);
  return v37;
}

```

## disassembly

```asm
0x18007c244  mov     [rsp-40h+arg_18], r9
0x18007c249  mov     [rsp-40h+arg_10], r8
0x18007c24e  push    rbp
0x18007c24f  push    rbx
0x18007c250  push    rsi
0x18007c251  push    rdi
0x18007c252  push    r12
0x18007c254  push    r13
0x18007c256  push    r14
0x18007c258  push    r15
0x18007c25a  mov     rbp, rsp
0x18007c25d  sub     rsp, 68h
0x18007c261  xor     r12d, r12d
0x18007c264  mov     [rbp+NumberOfBytesRead], 0
0x18007c26b  mov     [r8], r12
0x18007c26e  mov     r15d, edx
0x18007c271  mov     rdi, rcx
0x18007c274  mov     qword ptr [rbp+timeout.tv_sec], 0
0x18007c27c  mov     [rbp+res], 0
0x18007c284  call    cs:__imp_GetTickCount
0x18007c28a  lea     ecx, [r12+64h]
0x18007c28f  mov     [rbp+arg_0], eax
0x18007c292  cmp     r15d, ecx
0x18007c295  jnb     short loc_18007C2A2
0x18007c297  test    dword ptr [rdi+10h], 300h
0x18007c29e  cmovz   r15d, ecx
0x18007c2a2  lea     r14, [rdi+0A8h]
0x18007c2a9  mov     ecx, eax; unsigned int
0x18007c2ab  xor     r13d, r13d
0x18007c2ae  call    ?NetpDcElapsedTime@@YAKK@Z; NetpDcElapsedTime(ulong)
0x18007c2b3  mov     rbx, [r14]
0x18007c2b6  xor     ecx, ecx
0x18007c2b8  mov     [rbp+var_28], eax
0x18007c2bb  mov     [rbp+var_10], rcx
0x18007c2bf  cmp     rbx, r14
0x18007c2c2  jz      loc_18007C7E2
0x18007c2c8  mov     r10, cs:WPP_GLOBAL_Control
0x18007c2cf  test    r12, r12
0x18007c2d2  jz      short loc_18007C2E7
0x18007c2d4  mov     rcx, r12; vals
0x18007c2d7  call    cs:__imp_ldap_value_free_len
0x18007c2dd  mov     r10, cs:WPP_GLOBAL_Control
0x18007c2e4  xor     r12d, r12d
0x18007c2e7  mov     rcx, [rbp+res]; res
0x18007c2eb  test    rcx, rcx
0x18007c2ee  jz      short loc_18007C301
0x18007c2f0  call    cs:__imp_ldap_msgfree
0x18007c2f6  mov     r10, cs:WPP_GLOBAL_Control
0x18007c2fd  mov     [rbp+res], r13
0x18007c301  cmp     [rbx+0F0h], r13
0x18007c308  jz      loc_18007C791
0x18007c30e  test    byte ptr [r10+1Ch], 4
0x18007c313  jz      short loc_18007C33F
0x18007c315  cmp     byte ptr [r10+19h], 5
0x18007c31a  jb      short loc_18007C33F
0x18007c31c  mov     r9d, [rbx+104h]
0x18007c323  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x18007c32a  mov     rcx, [r10+10h]
0x18007c32e  mov     edx, 0Fh
0x18007c333  call    WPP_SF_d
0x18007c338  mov     r10, cs:WPP_GLOBAL_Control
0x18007c33f  xor     esi, esi
0x18007c341  cmp     [rbx+104h], esi
0x18007c347  jbe     loc_18007C583
0x18007c34d  mov     qword ptr [rbp+timeout.tv_sec], r13
0x18007c351  test    byte ptr [r10+1Ch], 4
0x18007c356  jz      short loc_18007C38A
0x18007c358  cmp     byte ptr [r10+19h], 5
0x18007c35d  jb      short loc_18007C38A
0x18007c35f  mov     rax, [rbx+0F8h]
0x18007c366  mov     r9, [rdi+48h]
0x18007c36a  mov     rcx, [r10+10h]
0x18007c36e  mov     edx, [rax+rsi*4]
0x18007c371  lea     rax, [rbx+0A8h]
0x18007c378  mov     dword ptr [rsp+68h+var_38], edx
0x18007c37c  mov     dword ptr [rsp+68h+var_40], edx
0x18007c380  mov     [rsp+68h+lpOverlapped], rax
0x18007c385  call    WPP_SF_SsDd
0x18007c38a  mov     rdx, [rbx+0F8h]
0x18007c391  lea     rax, [rbp+res]
0x18007c395  mov     rcx, [rbx+0F0h]
0x18007c39c  lea     r9, [rbp+timeout]; timeout
0x18007c3a0  mov     r8d, 1; all
0x18007c3a6  mov     [rsp+68h+lpOverlapped], rax; res
0x18007c3ab  mov     edx, [rdx+rsi*4]; msgid
0x18007c3ae  mov     rcx, [rcx]; ld
0x18007c3b1  call    cs:__imp_ldap_result
0x18007c3b7  mov     r9d, eax
0x18007c3ba  test    eax, eax
0x18007c3bc  jnz     short loc_18007C400
0x18007c3be  mov     r10, cs:WPP_GLOBAL_Control
0x18007c3c5  test    byte ptr [r10+1Ch], 4
0x18007c3ca  jz      short loc_18007C3ED
0x18007c3cc  cmp     byte ptr [r10+19h], 5
0x18007c3d1  jb      short loc_18007C3ED
0x18007c3d3  mov     rcx, [r10+10h]
0x18007c3d7  lea     edx, [rax+11h]
0x18007c3da  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x18007c3e1  call    WPP_SF_
0x18007c3e6  mov     r10, cs:WPP_GLOBAL_Control
0x18007c3ed  inc     esi
0x18007c3ef  cmp     esi, [rbx+104h]
0x18007c3f5  jb      loc_18007C34D
0x18007c3fb  jmp     loc_18007C57C
0x18007c400  cmp     r9d, 0FFFFFFFFh
0x18007c404  jnz     loc_18007C4C6
0x18007c40a  call    cs:__imp_LdapGetLastError
0x18007c410  mov     esi, eax
0x18007c412  mov     rax, cs:WPP_GLOBAL_Control
0x18007c419  test    byte ptr [rax+1Ch], 4
0x18007c41d  jz      short loc_18007C45B
0x18007c41f  cmp     byte ptr [rax+19h], 2
0x18007c423  jb      short loc_18007C45B
0x18007c425  mov     ecx, esi; err
0x18007c427  call    cs:__imp_ldap_err2stringA
0x18007c42d  mov     r9, [rdi+48h]
0x18007c431  lea     rcx, [rbx+0A8h]
0x18007c438  mov     [rsp+68h+var_38], rax; __int64
0x18007c43d  mov     edx, 12h
0x18007c442  mov     dword ptr [rsp+68h+var_40], esi; char
0x18007c446  mov     [rsp+68h+lpOverlapped], rcx; __int64
0x18007c44b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c452  mov     rcx, [rcx+10h]; LoggerHandle
0x18007c456  call    WPP_SF_Ssls
0x18007c45b  mov     ecx, esi; err
0x18007c45d  call    cs:__imp_ldap_err2stringA
0x18007c463  mov     r8, [rdi+48h]
0x18007c467  lea     r9, [rbx+0A8h]
0x18007c46e  mov     [rsp+68h+var_40], rax
0x18007c473  lea     rdx, aNetpdcgetpingr; "NetpDcGetPingResponse: %ws: Cannot ldap"...
0x18007c47a  mov     ecx, 100h; unsigned int
0x18007c47f  mov     dword ptr [rsp+68h+lpOverlapped], esi
0x18007c483  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007c488  cmp     esi, 55h ; 'U'
0x18007c48b  jnz     short loc_18007C4A6
0x18007c48d  mov     eax, [rbx+10Ch]
0x18007c493  test    al, 1
0x18007c495  jnz     short loc_18007C4A6
0x18007c497  or      eax, 1
0x18007c49a  mov     [rbx+10Ch], eax
0x18007c4a0  dec     dword ptr [rdi+0BCh]
0x18007c4a6  mov     rcx, rbx; struct _NL_DC_ADDRESS *
0x18007c4a9  call    ?NetpCancelOutstandingRequests@@YAXPEAU_NL_DC_ADDRESS@@@Z; NetpCancelOutstandingRequests(_NL_DC_ADDRESS *)
0x18007c4ae  mov     rcx, [rbx+0F0h]; struct _CACHED_CONNECTION *
0x18007c4b5  call    ?NlReleaseLocatorLdapConnection@@YAXPEAU_CACHED_CONNECTION@@@Z; NlReleaseLocatorLdapConnection(_CACHED_CONNECTION *)
0x18007c4ba  mov     [rbx+0F0h], r13
0x18007c4c1  jmp     loc_18007C575
0x18007c4c6  mov     r10, cs:WPP_GLOBAL_Control
0x18007c4cd  test    byte ptr [r10+1Ch], 4
0x18007c4d2  jz      short loc_18007C50E
0x18007c4d4  cmp     byte ptr [r10+19h], 4
0x18007c4d9  jb      short loc_18007C50E
0x18007c4db  mov     rax, [rbx+0F8h]
0x18007c4e2  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x18007c4e9  mov     edx, 13h
0x18007c4ee  mov     ecx, [rax+rsi*4]
0x18007c4f1  mov     dword ptr [rsp+68h+var_38], ecx
0x18007c4f5  mov     dword ptr [rsp+68h+var_40], ecx
0x18007c4f9  mov     rcx, [r10+10h]
0x18007c4fd  mov     dword ptr [rsp+68h+lpOverlapped], r9d
0x18007c502  call    WPP_SF_DdDd
0x18007c507  mov     r10, cs:WPP_GLOBAL_Control
0x18007c50e  mov     edx, [rbx+104h]
0x18007c514  test    edx, edx
0x18007c516  jz      short loc_18007C57C
0x18007c518  mov     r8, [rbx+0F8h]
0x18007c51f  xor     ecx, ecx
0x18007c521  mov     r9d, [r8+rsi*4]
0x18007c525  cmp     [r8+rcx*4], r9d
0x18007c529  jz      short loc_18007C533
0x18007c52b  inc     ecx
0x18007c52d  cmp     ecx, edx
0x18007c52f  jb      short loc_18007C525
0x18007c531  jmp     short loc_18007C57C
0x18007c533  lea     eax, [rdx-1]
0x18007c536  cmp     ecx, eax
0x18007c538  jnb     short loc_18007C55C
0x18007c53a  mov     rdx, [rbx+0F8h]
0x18007c541  lea     r8d, [rcx+1]
0x18007c545  mov     eax, [rdx+r8*4]
0x18007c549  mov     [rdx+rcx*4], eax
0x18007c54c  mov     eax, [rbx+104h]
0x18007c552  dec     eax
0x18007c554  mov     ecx, r8d
0x18007c557  cmp     r8d, eax
0x18007c55a  jb      short loc_18007C53A
0x18007c55c  mov     ecx, [rbx+104h]
0x18007c562  mov     rax, [rbx+0F8h]
0x18007c569  dec     ecx
0x18007c56b  mov     [rax+rcx*4], r13d
0x18007c56f  dec     dword ptr [rbx+104h]
0x18007c575  mov     r10, cs:WPP_GLOBAL_Control
0x18007c57c  lea     r14, [rdi+0A8h]
0x18007c583  cmp     [rbp+res], r13
0x18007c587  jnz     short loc_18007C5B9
0x18007c589  test    byte ptr [r10+1Ch], 4
0x18007c58e  jz      loc_18007C791
0x18007c594  cmp     byte ptr [r10+19h], 5
0x18007c599  jb      loc_18007C791
0x18007c59f  mov     rcx, [r10+10h]
0x18007c5a3  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x18007c5aa  mov     edx, 14h
0x18007c5af  call    WPP_SF_
0x18007c5b4  jmp     loc_18007C78A
0x18007c5b9  mov     rcx, [rbx+0F0h]
0x18007c5c0  mov     rdx, [rbp+res]; res
0x18007c5c4  mov     rcx, [rcx]; ld
0x18007c5c7  call    cs:__imp_ldap_count_entries
0x18007c5cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c5d4  test    byte ptr [rcx+1Ch], 4
0x18007c5d8  jz      short loc_18007C5F9
0x18007c5da  cmp     byte ptr [rcx+19h], 4
0x18007c5de  jb      short loc_18007C5F9
0x18007c5e0  mov     rdx, [rbp+res]
0x18007c5e4  mov     rcx, [rcx+10h]
0x18007c5e8  mov     dword ptr [rsp+68h+var_40], eax
0x18007c5ec  mov     r9d, [rdx]
0x18007c5ef  mov     dword ptr [rsp+68h+lpOverlapped], r9d
0x18007c5f4  call    WPP_SF_Ddd
0x18007c5f9  mov     rcx, [rbx+0F0h]
0x18007c600  mov     rdx, [rbp+res]; res
0x18007c604  mov     rcx, [rcx]; ld
0x18007c607  call    cs:__imp_ldap_first_entry
0x18007c60d  test    rax, rax
0x18007c610  jnz     short loc_18007C684
0x18007c612  mov     r8, [rdi+48h]
0x18007c616  lea     rsi, [rbx+0A8h]
0x18007c61d  mov     r9, rsi
0x18007c620  lea     rdx, aNetpdcgetpingr_4; "NetpDcGetPingResponse: %ws: Netlogon se"...
0x18007c627  mov     ecx, 2000000h; unsigned int
0x18007c62c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007c631  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c638  test    byte ptr [rcx+1Ch], 4
0x18007c63c  jz      short loc_18007C662
0x18007c63e  cmp     byte ptr [rcx+19h], 4
0x18007c642  jb      short loc_18007C662
0x18007c644  mov     r9, [rdi+48h]
0x18007c648  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x18007c64f  mov     rcx, [rcx+10h]
0x18007c653  mov     edx, 16h
0x18007c658  mov     [rsp+68h+lpOverlapped], rsi
0x18007c65d  call    WPP_SF_Ss
0x18007c662  mov     eax, [rbx+10Ch]
0x18007c668  test    al, 1
0x18007c66a  jnz     loc_18007C76F
0x18007c670  or      eax, 1
0x18007c673  mov     [rbx+10Ch], eax
0x18007c679  dec     dword ptr [rdi+0BCh]
0x18007c67f  jmp     loc_18007C76F
0x18007c684  mov     rcx, [rbx+0F0h]
0x18007c68b  lea     r8, aNetlogon_3; "Netlogon"
0x18007c692  mov     rdx, rax; Message
0x18007c695  mov     rcx, [rcx]; ExternalHandle
0x18007c698  call    cs:__imp_ldap_get_values_lenA
0x18007c69e  mov     r12, rax
0x18007c6a1  test    rax, rax
0x18007c6a4  jnz     loc_18007C767
0x18007c6aa  call    cs:__imp_LdapGetLastError
0x18007c6b0  mov     esi, eax
0x18007c6b2  test    eax, eax
0x18007c6b4  jz      loc_18007C74A
0x18007c6ba  mov     ecx, eax; err
0x18007c6bc  call    cs:__imp_ldap_err2stringA
0x18007c6c2  mov     r8, [rdi+48h]
0x18007c6c6  lea     r14, [rbx+0A8h]
0x18007c6cd  mov     [rsp+68h+var_40], rax
0x18007c6d2  lea     rdx, aNetpdcgetpingr_1; "NetpDcGetPingResponse: %ws: Cannot ldap"...
0x18007c6d9  mov     r9, r14
0x18007c6dc  mov     dword ptr [rsp+68h+lpOverlapped], esi
0x18007c6e0  mov     ecx, 100h; unsigned int
0x18007c6e5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007c6ea  mov     rax, cs:WPP_GLOBAL_Control
0x18007c6f1  test    byte ptr [rax+1Ch], 4
0x18007c6f5  jz      short loc_18007C72C
0x18007c6f7  cmp     byte ptr [rax+19h], 2
0x18007c6fb  jb      short loc_18007C72C
0x18007c6fd  mov     ecx, esi; err
0x18007c6ff  call    cs:__imp_ldap_err2stringA
0x18007c705  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c70c  lea     edx, [r12+17h]
0x18007c711  mov     r9, [rdi+48h]
0x18007c715  mov     [rsp+68h+var_38], rax; __int64
0x18007c71a  mov     dword ptr [rsp+68h+var_40], esi; char
0x18007c71e  mov     rcx, [rcx+10h]; LoggerHandle
0x18007c722  mov     [rsp+68h+lpOverlapped], r14; __int64
0x18007c727  call    WPP_SF_Ssls
0x18007c72c  cmp     esi, 10h
0x18007c72f  jnz     short loc_18007C74A
0x18007c731  mov     eax, [rbx+10Ch]
0x18007c737  test    al, 1
0x18007c739  jnz     short loc_18007C74A
0x18007c73b  or      eax, 1
0x18007c73e  mov     [rbx+10Ch], eax
0x18007c744  dec     dword ptr [rdi+0BCh]
0x18007c74a  mov     rcx, rbx; struct _NL_DC_ADDRESS *
0x18007c74d  call    ?NetpCancelOutstandingRequests@@YAXPEAU_NL_DC_ADDRESS@@@Z; NetpCancelOutstandingRequests(_NL_DC_ADDRESS *)
0x18007c752  mov     rcx, [rbx+0F0h]; struct _CACHED_CONNECTION *
0x18007c759  call    ?NlReleaseLocatorLdapConnection@@YAXPEAU_CACHED_CONNECTION@@@Z; NlReleaseLocatorLdapConnection(_CACHED_CONNECTION *)
0x18007c75e  lea     r14, [rdi+0A8h]
0x18007c765  jmp     short loc_18007C783
  ... truncated ...
```
