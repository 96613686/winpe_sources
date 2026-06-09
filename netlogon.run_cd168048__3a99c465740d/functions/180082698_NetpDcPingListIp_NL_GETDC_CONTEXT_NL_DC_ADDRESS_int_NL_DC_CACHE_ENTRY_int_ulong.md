# NetpDcPingListIp(_NL_GETDC_CONTEXT *,_NL_DC_ADDRESS *,int,_NL_DC_CACHE_ENTRY * *,int *,ulong *)

- ea: `0x180082698`
- end: `0x180082a7e`
- name: `?NetpDcPingListIp@@YAKPEAU_NL_GETDC_CONTEXT@@PEAU_NL_DC_ADDRESS@@HPEAPEAU_NL_DC_CACHE_ENTRY@@PEAHPEAK@Z`
- size: `998`
- prototype: `unsigned int __usercall@<eax>(struct _NL_GETDC_CONTEXT *@<rcx>, struct _NL_DC_ADDRESS *@<rdx>, int@<r8d>, struct _NL_DC_CACHE_ENTRY **@<r9>, int *, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18000b7bc`
- `0x18008166c`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x18007dd80`
- `0x18007e2b4`
- `0x180081e40`
- `0x180082698`
- `0x180083370`
- `0x18008439c`
- `0x18008448c`
- `0x180084554`
- `0x1800862d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082776`
- `WLDAP32!__imp_ldap_err2stringA` at `0x1800828bd`
- `WLDAP32!__imp_ldap_err2stringA` at `0x180082909`
- `WLDAP32!__imp_ldap_err2stringA` at `0x1800828bd`
- `WLDAP32!__imp_ldap_err2stringA` at `0x180082909`
- `WLDAP32!__imp_ldap_search_extA` at `0x1800828a4`
- `WLDAP32!__imp_ldap_search_extA` at `0x1800828a4`

## string_xrefs

- `0x1800826da`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\netpdc.cxx`
- `0x180082702`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\netpdc.cxx`
- `0x1800829cd`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\netpdc.cxx`
- `0x1800826e1`: `NlDcCacheEntry != NULL || (NlDcCacheEntry == NULL && !WaitForResponse)`
- `0x180082786`: `NetpDcPingListIp: %ws: Cannot LdapOpen ip address %hs: %ld\n`
- `0x1800828cd`: `NetpDcPingListIp: %ws: Cannot LdapOpen ip address %hs: %ld %hs\n`

## pseudocode

```c
__int64 __fastcall NetpDcPingListIp(
        struct _NL_GETDC_CONTEXT *a1,
        struct _NL_DC_ADDRESS *a2,
        unsigned int a3,
        struct _NL_DC_CACHE_ENTRY **a4,
        int *a5,
        unsigned int *a6)
{
  unsigned int *v9; // r12
  struct _NL_DC_ADDRESS *v10; // r15
  struct _CACHED_CONNECTION *LocatorLdapConnection; // rax
  char v12; // r14
  int v13; // edx
  unsigned int v14; // ebx
  CHAR *v15; // r9
  ULONG v16; // eax
  char *v17; // r9
  ULONG v18; // r14d
  PCHAR v19; // rax
  PCHAR v20; // rax
  __int64 v21; // rdx
  unsigned int PingResponse; // eax
  PZPSTR attrs; // [rsp+20h] [rbp-78h]
  __int128 v25; // [rsp+60h] [rbp-38h] BYREF
  ULONG MessageNumber; // [rsp+A0h] [rbp+8h] BYREF
  struct _NL_DC_CACHE_ENTRY **v27; // [rsp+B8h] [rbp+20h]

  v27 = a4;
  MessageNumber = 0;
  v25 = 0;
  if ( !a4 && a3 )
    NlAssertFailed(
      "NlDcCacheEntry != NULL || (NlDcCacheEntry == NULL && !WaitForResponse)",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\netpdc.cxx",
      0x559u,
      0);
  if ( !a5 && a3 )
    NlAssertFailed(
      "UsedNetbios != NULL || (UsedNetbios == NULL && !WaitForResponse)",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\netpdc.cxx",
      0x55Cu,
      (char *)a4);
  v9 = a6;
  v10 = (struct _NL_GETDC_CONTEXT *)((char *)a1 + 168);
  *a6 = 0;
  if ( !a2 )
    a2 = *(struct _NL_DC_ADDRESS **)v10;
  while ( 1 )
  {
    if ( a2 == v10 )
      return a3 != 0 ? 0x79 : 0;
    if ( (*((_BYTE *)a2 + 268) & 1) == 0 )
    {
      if ( !*((_QWORD *)a2 + 30) )
      {
        LocatorLdapConnection = NlGetLocatorLdapConnection(a1, (char *)a2 + 168, a3);
        *((_QWORD *)a2 + 30) = LocatorLdapConnection;
        if ( !LocatorLdapConnection )
        {
          LODWORD(attrs) = GetLastError();
          v12 = (char)attrs;
          NlPrintRoutine(
            0x100u,
            L"NetpDcPingListIp: %ws: Cannot LdapOpen ip address %hs: %ld\n",
            *((_QWORD *)a1 + 9),
            (char *)a2 + 168,
            attrs);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_Ssl(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, a3, *((_QWORD *)a1 + 9), (__int64)a2 + 168, v12);
          goto LABEL_31;
        }
      }
      v14 = NetpGrowLdapMsgIdArrayIfNecessary(a2);
      if ( v14 )
        return v14;
      NlPrintRoutine(0x10u, L"NetpDcPingListIp: %ws: Sending UDP ping to %hs\n", *((_QWORD *)a1 + 9), (char *)a2 + 168);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        WPP_SF_Ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
          *((_QWORD *)a1 + 9),
          (__int64)a2 + 168);
      v15 = (CHAR *)*((_QWORD *)a1 + 20);
      *(_QWORD *)&v25 = "Netlogon";
      *((_QWORD *)&v25 + 1) = 0;
      v16 = ldap_search_extA(**((LDAP ***)a2 + 30), 0, 0, v15, (PZPSTR)&v25, 0, 0, 0, 0, 0, &MessageNumber);
      v18 = v16;
      if ( v16 )
      {
        v19 = ldap_err2stringA(v16);
        LODWORD(attrs) = v18;
        NlPrintRoutine(
          0x100u,
          L"NetpDcPingListIp: %ws: Cannot LdapOpen ip address %hs: %ld %hs\n",
          *((_QWORD *)a1 + 9),
          (char *)a2 + 168,
          attrs,
          v19);
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v20 = ldap_err2stringA(v18);
          WPP_SF_Ssls(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2 + 168, v18, (__int64)v20);
        }
        goto LABEL_31;
      }
      _InterlockedIncrement64(&qword_1800F8DF8);
      _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(*((_QWORD *)a1 + 14) + 360LL) + 184LL));
      v21 = *((unsigned int *)a2 + 65);
      *(_DWORD *)(*((_QWORD *)a2 + 31) + 4 * v21) = MessageNumber;
      ++*((_DWORD *)a2 + 65);
      ++*v9;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_SsDdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v21,
          a3,
          *((_QWORD *)a1 + 9),
          (__int64)a2 + 168,
          MessageNumber,
          MessageNumber,
          *v9);
      if ( a3 )
      {
        if ( !*((_DWORD *)a2 + 66) )
          NlAssertFailed(
            "DcAddress->AddressPingWait != 0",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\coreloc\\netpdc.cxx",
            0x600u,
            v17);
        PingResponse = NetpDcGetPingResponse(a1, *((_DWORD *)a2 + 66), v27, a5);
        v14 = PingResponse;
        if ( PingResponse != 121 )
          break;
      }
    }
LABEL_31:
    a2 = *(struct _NL_DC_ADDRESS **)a2;
  }
  if ( PingResponse )
  {
    NlPrintRoutine(
      0x100u,
      L"NetpDcPingListIp: %ws: Cannot NetpDcGetPingResponse. %ld\n",
      *((_QWORD *)a1 + 9),
      PingResponse);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SL(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)&WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
        *((_QWORD *)a1 + 9),
        v14);
  }
  return v14;
}

```

## disassembly

```asm
0x180082698  mov     rax, rsp
0x18008269b  mov     [rax+10h], rbx
0x18008269f  mov     [rax+18h], rbp
0x1800826a3  mov     [rax+20h], r9
0x1800826a7  push    rsi
0x1800826a8  push    rdi
0x1800826a9  push    r12
0x1800826ab  push    r14
0x1800826ad  push    r15
0x1800826af  sub     rsp, 70h
0x1800826b3  mov     dword ptr [rax+8], 0
0x1800826ba  xorps   xmm0, xmm0
0x1800826bd  mov     ebp, r8d
0x1800826c0  mov     rdi, rdx
0x1800826c3  mov     rsi, rcx
0x1800826c6  movups  xmmword ptr [rax-38h], xmm0
0x1800826ca  test    r9, r9
0x1800826cd  jnz     short loc_1800826ED
0x1800826cf  test    r8d, r8d
0x1800826d2  jz      short loc_1800826ED
0x1800826d4  mov     r8d, 559h; unsigned int
0x1800826da  lea     rdx, aOnecoreDsNetap_7; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800826e1  lea     rcx, aNldccacheentry; "NlDcCacheEntry != NULL || (NlDcCacheEnt"...
0x1800826e8  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800826ed  cmp     [rsp+98h+arg_20], 0
0x1800826f6  jnz     short loc_180082715
0x1800826f8  test    ebp, ebp
0x1800826fa  jz      short loc_180082715
0x1800826fc  mov     r8d, 55Ch; unsigned int
0x180082702  lea     rdx, aOnecoreDsNetap_7; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180082709  lea     rcx, aUsednetbiosNul; "UsedNetbios != NULL || (UsedNetbios == "...
0x180082710  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180082715  mov     r12, [rsp+98h+arg_28]
0x18008271d  lea     r15, [rsi+0A8h]
0x180082724  mov     dword ptr [r12], 0
0x18008272c  test    rdi, rdi
0x18008272f  jnz     short loc_180082734
0x180082731  mov     rdi, [r15]
0x180082734  cmp     rdi, r15
0x180082737  jz      loc_180082A5B
0x18008273d  test    byte ptr [rdi+10Ch], 1
0x180082744  jnz     loc_180082A05
0x18008274a  cmp     qword ptr [rdi+0F0h], 0
0x180082752  jnz     loc_1800827D8
0x180082758  lea     rbx, [rdi+0A8h]
0x18008275f  mov     rcx, rsi; struct _NL_GETDC_CONTEXT *
0x180082762  mov     rdx, rbx; char *
0x180082765  call    ?NlGetLocatorLdapConnection@@YAPEAU_CACHED_CONNECTION@@PEAU_NL_GETDC_CONTEXT@@PEADK@Z; NlGetLocatorLdapConnection(_NL_GETDC_CONTEXT *,char *,ulong)
0x18008276a  mov     [rdi+0F0h], rax
0x180082771  test    rax, rax
0x180082774  jnz     short loc_1800827D8
0x180082776  call    cs:__imp_GetLastError
0x18008277d  nop     dword ptr [rax+rax+00h]
0x180082782  mov     r8, [rsi+48h]
0x180082786  lea     rdx, aNetpdcpinglist_2; "NetpDcPingListIp: %ws: Cannot LdapOpen "...
0x18008278d  mov     r9, rbx
0x180082790  mov     dword ptr [rsp+98h+attrs], eax
0x180082794  mov     ecx, 100h; unsigned int
0x180082799  mov     r14d, eax
0x18008279c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800827a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800827a8  test    byte ptr [rcx+1Ch], 4
0x1800827ac  jz      loc_180082A05
0x1800827b2  cmp     byte ptr [rcx+19h], 2
0x1800827b6  jb      loc_180082A05
0x1800827bc  mov     r9, [rsi+48h]
0x1800827c0  mov     rcx, [rcx+10h]
0x1800827c4  mov     [rsp+98h+attrsonly], r14d
0x1800827c9  mov     [rsp+98h+attrs], rbx
0x1800827ce  call    WPP_SF_Ssl
0x1800827d3  jmp     loc_180082A05
0x1800827d8  mov     rcx, rdi; struct _NL_DC_ADDRESS *
0x1800827db  call    ?NetpGrowLdapMsgIdArrayIfNecessary@@YAKPEAU_NL_DC_ADDRESS@@@Z; NetpGrowLdapMsgIdArrayIfNecessary(_NL_DC_ADDRESS *)
0x1800827e0  mov     ebx, eax
0x1800827e2  test    eax, eax
0x1800827e4  jnz     loc_180082A62
0x1800827ea  mov     r8, [rsi+48h]
0x1800827ee  lea     rbx, [rdi+0A8h]
0x1800827f5  mov     r9, rbx
0x1800827f8  lea     rdx, aNetpdcpinglist_0; "NetpDcPingListIp: %ws: Sending UDP ping"...
0x1800827ff  lea     ecx, [rax+10h]; unsigned int
0x180082802  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180082807  mov     rcx, cs:WPP_GLOBAL_Control
0x18008280e  test    byte ptr [rcx+1Ch], 4
0x180082812  jz      short loc_180082838
0x180082814  cmp     byte ptr [rcx+19h], 5
0x180082818  jb      short loc_180082838
0x18008281a  mov     r9, [rsi+48h]
0x18008281e  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x180082825  mov     rcx, [rcx+10h]
0x180082829  mov     edx, 1Dh
0x18008282e  mov     [rsp+98h+attrs], rbx
0x180082833  call    WPP_SF_Ss
0x180082838  mov     r9, [rsi+0A0h]; filter
0x18008283f  lea     rax, aNetlogon_3; "Netlogon"
0x180082846  mov     [rsp+98h+var_38], rax
0x18008284b  xor     r8d, r8d; scope
0x18008284e  mov     [rsp+98h+var_30], 0
0x180082857  lea     rax, [rsp+98h+arg_0]
0x18008285f  mov     rcx, [rdi+0F0h]
0x180082866  xor     edx, edx; base
0x180082868  mov     [rsp+98h+MessageNumber], rax; MessageNumber
0x18008286d  lea     rax, [rsp+98h+var_38]
0x180082872  mov     [rsp+98h+SizeLimit], 0; SizeLimit
0x18008287a  mov     [rsp+98h+TimeLimit], 0; TimeLimit
0x180082882  mov     rcx, [rcx]; ld
0x180082885  mov     [rsp+98h+ClientControls], 0; ClientControls
0x18008288e  mov     [rsp+98h+ServerControls], 0; ServerControls
0x180082897  mov     [rsp+98h+attrsonly], 0; attrsonly
0x18008289f  mov     [rsp+98h+attrs], rax; attrs
0x1800828a4  call    cs:__imp_ldap_search_extA
0x1800828ab  nop     dword ptr [rax+rax+00h]
0x1800828b0  mov     r14d, eax
0x1800828b3  test    eax, eax
0x1800828b5  jz      loc_180082942
0x1800828bb  mov     ecx, eax; err
0x1800828bd  call    cs:__imp_ldap_err2stringA
0x1800828c4  nop     dword ptr [rax+rax+00h]
0x1800828c9  mov     r8, [rsi+48h]
0x1800828cd  lea     rdx, aNetpdcpinglist; "NetpDcPingListIp: %ws: Cannot LdapOpen "...
0x1800828d4  mov     qword ptr [rsp+98h+attrsonly], rax
0x1800828d9  mov     r9, rbx
0x1800828dc  mov     ecx, 100h; unsigned int
0x1800828e1  mov     dword ptr [rsp+98h+attrs], r14d
0x1800828e6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800828eb  mov     rax, cs:WPP_GLOBAL_Control
0x1800828f2  test    byte ptr [rax+1Ch], 4
0x1800828f6  jz      loc_180082A05
0x1800828fc  cmp     byte ptr [rax+19h], 2
0x180082900  jb      loc_180082A05
0x180082906  mov     ecx, r14d; err
0x180082909  call    cs:__imp_ldap_err2stringA
0x180082910  nop     dword ptr [rax+rax+00h]
0x180082915  mov     rcx, cs:WPP_GLOBAL_Control
0x18008291c  mov     edx, 1Eh
0x180082921  mov     r9, [rsi+48h]
0x180082925  mov     [rsp+98h+ServerControls], rax; __int64
0x18008292a  mov     [rsp+98h+attrsonly], r14d; char
0x18008292f  mov     rcx, [rcx+10h]; LoggerHandle
0x180082933  mov     [rsp+98h+attrs], rbx; __int64
0x180082938  call    WPP_SF_Ssls
0x18008293d  jmp     loc_180082A05
0x180082942  lock inc cs:qword_1800F8DF8
0x18008294a  mov     rax, [rsi+70h]
0x18008294e  mov     rcx, [rax+168h]
0x180082955  lock inc qword ptr [rcx+0B8h]
0x18008295d  mov     eax, [rsp+98h+arg_0]
0x180082964  mov     edx, [rdi+104h]
0x18008296a  mov     rcx, [rdi+0F8h]
0x180082971  mov     [rcx+rdx*4], eax
0x180082974  inc     dword ptr [rdi+104h]
0x18008297a  inc     dword ptr [r12]
0x18008297e  mov     eax, [r12]
0x180082982  mov     rcx, cs:WPP_GLOBAL_Control
0x180082989  test    byte ptr [rcx+1Ch], 4
0x18008298d  jz      short loc_1800829BA
0x18008298f  cmp     byte ptr [rcx+19h], 4
0x180082993  jb      short loc_1800829BA
0x180082995  mov     r9, [rsi+48h]
0x180082999  mov     rcx, [rcx+10h]
0x18008299d  mov     dword ptr [rsp+98h+ClientControls], eax
0x1800829a1  mov     eax, [rsp+98h+arg_0]
0x1800829a8  mov     dword ptr [rsp+98h+ServerControls], eax
0x1800829ac  mov     [rsp+98h+attrsonly], eax
0x1800829b0  mov     [rsp+98h+attrs], rbx
0x1800829b5  call    WPP_SF_SsDdD
0x1800829ba  test    ebp, ebp
0x1800829bc  jz      short loc_180082A05
0x1800829be  cmp     dword ptr [rdi+108h], 0
0x1800829c5  jnz     short loc_1800829E0
0x1800829c7  mov     r8d, 600h; unsigned int
0x1800829cd  lea     rdx, aOnecoreDsNetap_7; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800829d4  lea     rcx, aDcaddressAddre; "DcAddress->AddressPingWait != 0"
0x1800829db  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800829e0  mov     r9, [rsp+98h+arg_20]; int *
0x1800829e8  mov     rcx, rsi; struct _NL_GETDC_CONTEXT *
0x1800829eb  mov     r8, [rsp+98h+arg_18]; struct _NL_DC_CACHE_ENTRY **
0x1800829f3  mov     edx, [rdi+108h]; unsigned int
0x1800829f9  call    ?NetpDcGetPingResponse@@YAKPEAU_NL_GETDC_CONTEXT@@KPEAPEAU_NL_DC_CACHE_ENTRY@@PEAH@Z; NetpDcGetPingResponse(_NL_GETDC_CONTEXT *,ulong,_NL_DC_CACHE_ENTRY * *,int *)
0x1800829fe  mov     ebx, eax
0x180082a00  cmp     eax, 79h ; 'y'
0x180082a03  jnz     short loc_180082A0D
0x180082a05  mov     rdi, [rdi]
0x180082a08  jmp     loc_180082734
0x180082a0d  test    ebx, ebx
0x180082a0f  jz      short loc_180082A62
0x180082a11  mov     r8, [rsi+48h]
0x180082a15  lea     rdx, aNetpdcpinglist_1; "NetpDcPingListIp: %ws: Cannot NetpDcGet"...
0x180082a1c  mov     r9d, ebx
0x180082a1f  mov     ecx, 100h; unsigned int
0x180082a24  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180082a29  mov     rcx, cs:WPP_GLOBAL_Control
0x180082a30  test    byte ptr [rcx+1Ch], 4
0x180082a34  jz      short loc_180082A62
0x180082a36  cmp     byte ptr [rcx+19h], 2
0x180082a3a  jb      short loc_180082A62
0x180082a3c  mov     r9, [rsi+48h]
0x180082a40  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x180082a47  mov     rcx, [rcx+10h]
0x180082a4b  mov     edx, 20h ; ' '
0x180082a50  mov     dword ptr [rsp+98h+attrs], ebx
0x180082a54  call    WPP_SF_SL
0x180082a59  jmp     short loc_180082A62
0x180082a5b  neg     ebp
0x180082a5d  sbb     ebx, ebx
0x180082a5f  and     ebx, 79h
0x180082a62  lea     r11, [rsp+98h+var_28]
0x180082a67  mov     eax, ebx
0x180082a69  mov     rbx, [r11+38h]
0x180082a6d  mov     rbp, [r11+40h]
0x180082a71  mov     rsp, r11
0x180082a74  pop     r15
0x180082a76  pop     r14
0x180082a78  pop     r12
0x180082a7a  pop     rdi
0x180082a7b  pop     rsi
0x180082a7c  retn
```
