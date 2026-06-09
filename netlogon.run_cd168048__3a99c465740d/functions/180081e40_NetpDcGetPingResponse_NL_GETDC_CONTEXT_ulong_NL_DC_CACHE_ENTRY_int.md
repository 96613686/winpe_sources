# NetpDcGetPingResponse(_NL_GETDC_CONTEXT *,ulong,_NL_DC_CACHE_ENTRY * *,int *)

- ea: `0x180081e40`
- end: `0x18008268f`
- name: `?NetpDcGetPingResponse@@YAKPEAU_NL_GETDC_CONTEXT@@KPEAPEAU_NL_DC_CACHE_ENTRY@@PEAH@Z`
- size: `2127`
- prototype: `unsigned int __fastcall(struct _NL_GETDC_CONTEXT *, unsigned int, struct _NL_DC_CACHE_ENTRY **, int *)`
- caller_count: `7`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x18000b7bc`
- `0x18006ad64`
- `0x18007ea48`
- `0x180080b08`
- `0x180080f74`
- `0x18008166c`
- `0x180082698`

## callees

- `0x180007518`
- `0x18000d324`
- `0x180018f38`
- `0x180018f68`
- `0x180019000`
- `0x18007a9a4`
- `0x18007dd80`
- `0x18007e2b4`
- `0x18007e8bc`
- `0x180081e40`
- `0x180084034`
- `0x180084098`
- `0x1800842c4`
- `0x180084554`
- `0x18008654c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082467`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008262d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008262d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180081e80`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180081e80`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180082457`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180082457`
- `WLDAP32!__imp_LdapGetLastError` at `0x18008201e`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800822e2`
- `WLDAP32!__imp_LdapGetLastError` at `0x18008201e`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800822e2`
- `WLDAP32!__imp_ldap_first_entry` at `0x180082233`
- `WLDAP32!__imp_ldap_first_entry` at `0x180082233`
- `WLDAP32!__imp_ldap_count_entries` at `0x1800821ed`
- `WLDAP32!__imp_ldap_count_entries` at `0x1800821ed`
- `WLDAP32!__imp_ldap_result` at `0x180081fbf`
- `WLDAP32!__imp_ldap_result` at `0x180081fbf`
- `WLDAP32!__imp_ldap_msgfree` at `0x180081ef8`
- `WLDAP32!__imp_ldap_msgfree` at `0x18008266f`
- `WLDAP32!__imp_ldap_msgfree` at `0x180081ef8`
- `WLDAP32!__imp_ldap_msgfree` at `0x18008266f`
- `WLDAP32!__imp_ldap_value_free_len` at `0x180081ed9`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18008265a`
- `WLDAP32!__imp_ldap_value_free_len` at `0x180081ed9`
- `WLDAP32!__imp_ldap_value_free_len` at `0x18008265a`
- `WLDAP32!__imp_ldap_err2stringA` at `0x180082041`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18008207d`
- `WLDAP32!__imp_ldap_err2stringA` at `0x1800822fa`
- `WLDAP32!__imp_ldap_err2stringA` at `0x180082343`
- `WLDAP32!__imp_ldap_err2stringA` at `0x180082041`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18008207d`
- `WLDAP32!__imp_ldap_err2stringA` at `0x1800822fa`
- `WLDAP32!__imp_ldap_err2stringA` at `0x180082343`
- `WLDAP32!__imp_ldap_get_values_lenA` at `0x1800822ca`
- `WLDAP32!__imp_ldap_get_values_lenA` at `0x1800822ca`

## string_xrefs

- `0x180082252`: `NetpDcGetPingResponse: %ws: Netlogon service stopped on DC at %hs\n`
- `0x180082482`: `NetpDcGetPingResponse: %ws: cannot read temp mailslot timeout %ld\n`

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
            &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids);
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
              WPP_SF_DdDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids);
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
        WPP_SF_(*((_QWORD *)v13 + 2), 20, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids);
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
            (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
                  (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
          (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
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
          WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids, v42);
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
0x180081e40  mov     [rsp-40h+arg_18], r9
0x180081e45  mov     [rsp-40h+arg_10], r8
0x180081e4a  push    rbp
0x180081e4b  push    rbx
0x180081e4c  push    rsi
0x180081e4d  push    rdi
0x180081e4e  push    r12
0x180081e50  push    r13
0x180081e52  push    r14
0x180081e54  push    r15
0x180081e56  mov     rbp, rsp
0x180081e59  sub     rsp, 68h
0x180081e5d  xor     r12d, r12d
0x180081e60  mov     [rbp+NumberOfBytesRead], 0
0x180081e67  mov     [r8], r12
0x180081e6a  mov     r15d, edx
0x180081e6d  mov     rdi, rcx
0x180081e70  mov     qword ptr [rbp+timeout.tv_sec], 0
0x180081e78  mov     [rbp+res], 0
0x180081e80  call    cs:__imp_GetTickCount
0x180081e87  nop     dword ptr [rax+rax+00h]
0x180081e8c  lea     ecx, [r12+64h]
0x180081e91  mov     [rbp+arg_0], eax
0x180081e94  cmp     r15d, ecx
0x180081e97  jnb     short loc_180081EA4
0x180081e99  test    dword ptr [rdi+10h], 300h
0x180081ea0  cmovz   r15d, ecx
0x180081ea4  lea     r14, [rdi+0A8h]
0x180081eab  mov     ecx, eax; unsigned int
0x180081ead  xor     r13d, r13d
0x180081eb0  call    ?NetpDcElapsedTime@@YAKK@Z; NetpDcElapsedTime(ulong)
0x180081eb5  mov     rbx, [r14]
0x180081eb8  xor     ecx, ecx
0x180081eba  mov     [rbp+var_28], eax
0x180081ebd  mov     [rbp+var_10], rcx
0x180081ec1  cmp     rbx, r14
0x180081ec4  jz      loc_18008242C
0x180081eca  mov     r10, cs:WPP_GLOBAL_Control
0x180081ed1  test    r12, r12
0x180081ed4  jz      short loc_180081EEF
0x180081ed6  mov     rcx, r12; vals
0x180081ed9  call    cs:__imp_ldap_value_free_len
0x180081ee0  nop     dword ptr [rax+rax+00h]
0x180081ee5  mov     r10, cs:WPP_GLOBAL_Control
0x180081eec  xor     r12d, r12d
0x180081eef  mov     rcx, [rbp+res]; res
0x180081ef3  test    rcx, rcx
0x180081ef6  jz      short loc_180081F0F
0x180081ef8  call    cs:__imp_ldap_msgfree
0x180081eff  nop     dword ptr [rax+rax+00h]
0x180081f04  mov     r10, cs:WPP_GLOBAL_Control
0x180081f0b  mov     [rbp+res], r13
0x180081f0f  cmp     [rbx+0F0h], r13
0x180081f16  jz      loc_1800823DB
0x180081f1c  test    byte ptr [r10+1Ch], 4
0x180081f21  jz      short loc_180081F4D
0x180081f23  cmp     byte ptr [r10+19h], 5
0x180081f28  jb      short loc_180081F4D
0x180081f2a  mov     r9d, [rbx+104h]
0x180081f31  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x180081f38  mov     rcx, [r10+10h]
0x180081f3c  mov     edx, 0Fh
0x180081f41  call    WPP_SF_d
0x180081f46  mov     r10, cs:WPP_GLOBAL_Control
0x180081f4d  xor     esi, esi
0x180081f4f  cmp     [rbx+104h], esi
0x180081f55  jbe     loc_1800821A9
0x180081f5b  mov     qword ptr [rbp+timeout.tv_sec], r13
0x180081f5f  test    byte ptr [r10+1Ch], 4
0x180081f64  jz      short loc_180081F98
0x180081f66  cmp     byte ptr [r10+19h], 5
0x180081f6b  jb      short loc_180081F98
0x180081f6d  mov     rax, [rbx+0F8h]
0x180081f74  mov     r9, [rdi+48h]
0x180081f78  mov     rcx, [r10+10h]
0x180081f7c  mov     edx, [rax+rsi*4]
0x180081f7f  lea     rax, [rbx+0A8h]
0x180081f86  mov     dword ptr [rsp+68h+var_38], edx
0x180081f8a  mov     dword ptr [rsp+68h+var_40], edx
0x180081f8e  mov     [rsp+68h+lpOverlapped], rax
0x180081f93  call    WPP_SF_SsDd
0x180081f98  mov     rdx, [rbx+0F8h]
0x180081f9f  lea     rax, [rbp+res]
0x180081fa3  mov     rcx, [rbx+0F0h]
0x180081faa  lea     r9, [rbp+timeout]; timeout
0x180081fae  mov     r8d, 1; all
0x180081fb4  mov     [rsp+68h+lpOverlapped], rax; res
0x180081fb9  mov     edx, [rdx+rsi*4]; msgid
0x180081fbc  mov     rcx, [rcx]; ld
0x180081fbf  call    cs:__imp_ldap_result
0x180081fc6  nop     dword ptr [rax+rax+00h]
0x180081fcb  mov     r9d, eax
0x180081fce  test    eax, eax
0x180081fd0  jnz     short loc_180082014
0x180081fd2  mov     r10, cs:WPP_GLOBAL_Control
0x180081fd9  test    byte ptr [r10+1Ch], 4
0x180081fde  jz      short loc_180082001
0x180081fe0  cmp     byte ptr [r10+19h], 5
0x180081fe5  jb      short loc_180082001
0x180081fe7  mov     rcx, [r10+10h]
0x180081feb  lea     edx, [rax+11h]
0x180081fee  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x180081ff5  call    WPP_SF_
0x180081ffa  mov     r10, cs:WPP_GLOBAL_Control
0x180082001  inc     esi
0x180082003  cmp     esi, [rbx+104h]
0x180082009  jb      loc_180081F5B
0x18008200f  jmp     loc_1800821A2
0x180082014  cmp     r9d, 0FFFFFFFFh
0x180082018  jnz     loc_1800820EC
0x18008201e  call    cs:__imp_LdapGetLastError
0x180082025  nop     dword ptr [rax+rax+00h]
0x18008202a  mov     esi, eax
0x18008202c  mov     rax, cs:WPP_GLOBAL_Control
0x180082033  test    byte ptr [rax+1Ch], 4
0x180082037  jz      short loc_18008207B
0x180082039  cmp     byte ptr [rax+19h], 2
0x18008203d  jb      short loc_18008207B
0x18008203f  mov     ecx, esi; err
0x180082041  call    cs:__imp_ldap_err2stringA
0x180082048  nop     dword ptr [rax+rax+00h]
0x18008204d  mov     r9, [rdi+48h]
0x180082051  lea     rcx, [rbx+0A8h]
0x180082058  mov     [rsp+68h+var_38], rax; __int64
0x18008205d  mov     edx, 12h
0x180082062  mov     dword ptr [rsp+68h+var_40], esi; char
0x180082066  mov     [rsp+68h+lpOverlapped], rcx; __int64
0x18008206b  mov     rcx, cs:WPP_GLOBAL_Control
0x180082072  mov     rcx, [rcx+10h]; LoggerHandle
0x180082076  call    WPP_SF_Ssls
0x18008207b  mov     ecx, esi; err
0x18008207d  call    cs:__imp_ldap_err2stringA
0x180082084  nop     dword ptr [rax+rax+00h]
0x180082089  mov     r8, [rdi+48h]
0x18008208d  lea     r9, [rbx+0A8h]
0x180082094  mov     [rsp+68h+var_40], rax
0x180082099  lea     rdx, aNetpdcgetpingr; "NetpDcGetPingResponse: %ws: Cannot ldap"...
0x1800820a0  mov     ecx, 100h; unsigned int
0x1800820a5  mov     dword ptr [rsp+68h+lpOverlapped], esi
0x1800820a9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800820ae  cmp     esi, 55h ; 'U'
0x1800820b1  jnz     short loc_1800820CC
0x1800820b3  mov     eax, [rbx+10Ch]
0x1800820b9  test    al, 1
0x1800820bb  jnz     short loc_1800820CC
0x1800820bd  or      eax, 1
0x1800820c0  mov     [rbx+10Ch], eax
0x1800820c6  dec     dword ptr [rdi+0BCh]
0x1800820cc  mov     rcx, rbx; struct _NL_DC_ADDRESS *
0x1800820cf  call    ?NetpCancelOutstandingRequests@@YAXPEAU_NL_DC_ADDRESS@@@Z; NetpCancelOutstandingRequests(_NL_DC_ADDRESS *)
0x1800820d4  mov     rcx, [rbx+0F0h]; struct _CACHED_CONNECTION *
0x1800820db  call    ?NlReleaseLocatorLdapConnection@@YAXPEAU_CACHED_CONNECTION@@@Z; NlReleaseLocatorLdapConnection(_CACHED_CONNECTION *)
0x1800820e0  mov     [rbx+0F0h], r13
0x1800820e7  jmp     loc_18008219B
0x1800820ec  mov     r10, cs:WPP_GLOBAL_Control
0x1800820f3  test    byte ptr [r10+1Ch], 4
0x1800820f8  jz      short loc_180082134
0x1800820fa  cmp     byte ptr [r10+19h], 4
0x1800820ff  jb      short loc_180082134
0x180082101  mov     rax, [rbx+0F8h]
0x180082108  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x18008210f  mov     edx, 13h
0x180082114  mov     ecx, [rax+rsi*4]
0x180082117  mov     dword ptr [rsp+68h+var_38], ecx
0x18008211b  mov     dword ptr [rsp+68h+var_40], ecx
0x18008211f  mov     rcx, [r10+10h]
0x180082123  mov     dword ptr [rsp+68h+lpOverlapped], r9d
0x180082128  call    WPP_SF_DdDd
0x18008212d  mov     r10, cs:WPP_GLOBAL_Control
0x180082134  mov     edx, [rbx+104h]
0x18008213a  test    edx, edx
0x18008213c  jz      short loc_1800821A2
0x18008213e  mov     r8, [rbx+0F8h]
0x180082145  xor     ecx, ecx
0x180082147  mov     r9d, [r8+rsi*4]
0x18008214b  cmp     [r8+rcx*4], r9d
0x18008214f  jz      short loc_180082159
0x180082151  inc     ecx
0x180082153  cmp     ecx, edx
0x180082155  jb      short loc_18008214B
0x180082157  jmp     short loc_1800821A2
0x180082159  lea     eax, [rdx-1]
0x18008215c  cmp     ecx, eax
0x18008215e  jnb     short loc_180082182
0x180082160  mov     rdx, [rbx+0F8h]
0x180082167  lea     r8d, [rcx+1]
0x18008216b  mov     eax, [rdx+r8*4]
0x18008216f  mov     [rdx+rcx*4], eax
0x180082172  mov     eax, [rbx+104h]
0x180082178  dec     eax
0x18008217a  mov     ecx, r8d
0x18008217d  cmp     r8d, eax
0x180082180  jb      short loc_180082160
0x180082182  mov     ecx, [rbx+104h]
0x180082188  mov     rax, [rbx+0F8h]
0x18008218f  dec     ecx
0x180082191  mov     [rax+rcx*4], r13d
0x180082195  dec     dword ptr [rbx+104h]
0x18008219b  mov     r10, cs:WPP_GLOBAL_Control
0x1800821a2  lea     r14, [rdi+0A8h]
0x1800821a9  cmp     [rbp+res], r13
0x1800821ad  jnz     short loc_1800821DF
0x1800821af  test    byte ptr [r10+1Ch], 4
0x1800821b4  jz      loc_1800823DB
0x1800821ba  cmp     byte ptr [r10+19h], 5
0x1800821bf  jb      loc_1800823DB
0x1800821c5  mov     rcx, [r10+10h]
0x1800821c9  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x1800821d0  mov     edx, 14h
0x1800821d5  call    WPP_SF_
0x1800821da  jmp     loc_1800823D4
0x1800821df  mov     rcx, [rbx+0F0h]
0x1800821e6  mov     rdx, [rbp+res]; res
0x1800821ea  mov     rcx, [rcx]; ld
0x1800821ed  call    cs:__imp_ldap_count_entries
0x1800821f4  nop     dword ptr [rax+rax+00h]
0x1800821f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180082200  test    byte ptr [rcx+1Ch], 4
0x180082204  jz      short loc_180082225
0x180082206  cmp     byte ptr [rcx+19h], 4
0x18008220a  jb      short loc_180082225
0x18008220c  mov     rdx, [rbp+res]
0x180082210  mov     rcx, [rcx+10h]
0x180082214  mov     dword ptr [rsp+68h+var_40], eax
0x180082218  mov     r9d, [rdx]
0x18008221b  mov     dword ptr [rsp+68h+lpOverlapped], r9d
0x180082220  call    WPP_SF_Ddd
0x180082225  mov     rcx, [rbx+0F0h]
0x18008222c  mov     rdx, [rbp+res]; res
0x180082230  mov     rcx, [rcx]; ld
0x180082233  call    cs:__imp_ldap_first_entry
0x18008223a  nop     dword ptr [rax+rax+00h]
0x18008223f  test    rax, rax
0x180082242  jnz     short loc_1800822B6
0x180082244  mov     r8, [rdi+48h]
0x180082248  lea     rsi, [rbx+0A8h]
0x18008224f  mov     r9, rsi
0x180082252  lea     rdx, aNetpdcgetpingr_4; "NetpDcGetPingResponse: %ws: Netlogon se"...
0x180082259  mov     ecx, 2000000h; unsigned int
0x18008225e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180082263  mov     rcx, cs:WPP_GLOBAL_Control
0x18008226a  test    byte ptr [rcx+1Ch], 4
0x18008226e  jz      short loc_180082294
0x180082270  cmp     byte ptr [rcx+19h], 4
0x180082274  jb      short loc_180082294
0x180082276  mov     r9, [rdi+48h]
0x18008227a  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x180082281  mov     rcx, [rcx+10h]
0x180082285  mov     edx, 16h
0x18008228a  mov     [rsp+68h+lpOverlapped], rsi
0x18008228f  call    WPP_SF_Ss
0x180082294  mov     eax, [rbx+10Ch]
0x18008229a  test    al, 1
0x18008229c  jnz     loc_1800823B9
0x1800822a2  or      eax, 1
0x1800822a5  mov     [rbx+10Ch], eax
0x1800822ab  dec     dword ptr [rdi+0BCh]
0x1800822b1  jmp     loc_1800823B9
0x1800822b6  mov     rcx, [rbx+0F0h]
0x1800822bd  lea     r8, aNetlogon_3; "Netlogon"
0x1800822c4  mov     rdx, rax; Message
0x1800822c7  mov     rcx, [rcx]; ExternalHandle
0x1800822ca  call    cs:__imp_ldap_get_values_lenA
0x1800822d1  nop     dword ptr [rax+rax+00h]
0x1800822d6  mov     r12, rax
0x1800822d9  test    rax, rax
0x1800822dc  jnz     loc_1800823B1
0x1800822e2  call    cs:__imp_LdapGetLastError
0x1800822e9  nop     dword ptr [rax+rax+00h]
0x1800822ee  mov     esi, eax
0x1800822f0  test    eax, eax
0x1800822f2  jz      loc_180082394
0x1800822f8  mov     ecx, eax; err
0x1800822fa  call    cs:__imp_ldap_err2stringA
0x180082301  nop     dword ptr [rax+rax+00h]
0x180082306  mov     r8, [rdi+48h]
0x18008230a  lea     r14, [rbx+0A8h]
0x180082311  mov     [rsp+68h+var_40], rax
0x180082316  lea     rdx, aNetpdcgetpingr_1; "NetpDcGetPingResponse: %ws: Cannot ldap"...
0x18008231d  mov     r9, r14
0x180082320  mov     dword ptr [rsp+68h+lpOverlapped], esi
0x180082324  mov     ecx, 100h; unsigned int
0x180082329  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18008232e  mov     rax, cs:WPP_GLOBAL_Control
0x180082335  test    byte ptr [rax+1Ch], 4
0x180082339  jz      short loc_180082376
0x18008233b  cmp     byte ptr [rax+19h], 2
0x18008233f  jb      short loc_180082376
0x180082341  mov     ecx, esi; err
0x180082343  call    cs:__imp_ldap_err2stringA
0x18008234a  nop     dword ptr [rax+rax+00h]
0x18008234f  mov     rcx, cs:WPP_GLOBAL_Control
0x180082356  lea     edx, [r12+17h]
0x18008235b  mov     r9, [rdi+48h]
0x18008235f  mov     [rsp+68h+var_38], rax; __int64
0x180082364  mov     dword ptr [rsp+68h+var_40], esi; char
0x180082368  mov     rcx, [rcx+10h]; LoggerHandle
0x18008236c  mov     [rsp+68h+lpOverlapped], r14; __int64
0x180082371  call    WPP_SF_Ssls
0x180082376  cmp     esi, 10h
  ... truncated ...
```
