# NetpDcPingListIp(_NL_GETDC_CONTEXT *,_NL_DC_ADDRESS *,int,_NL_DC_CACHE_ENTRY * *,int *,ulong *)

- ea: `0x18007ca2c`
- end: `0x18007cdf1`
- name: `?NetpDcPingListIp@@YAKPEAU_NL_GETDC_CONTEXT@@PEAU_NL_DC_ADDRESS@@HPEAPEAU_NL_DC_CACHE_ENTRY@@PEAHPEAK@Z`
- size: `965`
- prototype: `__int64 __fastcall(struct _NL_GETDC_CONTEXT *, struct _NL_DC_ADDRESS *, unsigned int, struct _NL_DC_CACHE_ENTRY **, int *, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18000b1c4`
- `0x18007ba90`

## callees

- `0x180007278`
- `0x18000d710`
- `0x1800782b8`
- `0x1800787c4`
- `0x18007c244`
- `0x18007ca2c`
- `0x18007d6cc`
- `0x18007e634`
- `0x18007e71c`
- `0x18007e7dc`
- `0x180080424`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cb06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cb06`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18007cc3d`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18007cc83`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18007cc3d`
- `WLDAP32!__imp_ldap_err2stringA` at `0x18007cc83`
- `WLDAP32!__imp_ldap_search_extA` at `0x18007cc2e`
- `WLDAP32!__imp_ldap_search_extA` at `0x18007cc2e`

## string_xrefs

- `0x18007ca6e`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\netpdc.cxx`
- `0x18007ca96`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\netpdc.cxx`
- `0x18007cd41`: `onecore\ds\netapi\svcdlls\logonsrv\coreloc\netpdc.cxx`
- `0x18007ca75`: `NlDcCacheEntry != NULL || (NlDcCacheEntry == NULL && !WaitForResponse)`
- `0x18007cb10`: `NetpDcPingListIp: %ws: Cannot LdapOpen ip address %hs: %ld\n`
- `0x18007cc47`: `NetpDcPingListIp: %ws: Cannot LdapOpen ip address %hs: %ld %hs\n`

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
          (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
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
      _InterlockedIncrement64(&qword_1800F1E38);
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
        (unsigned int)&WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
        *((_QWORD *)a1 + 9),
        v14);
  }
  return v14;
}

```

## disassembly

```asm
0x18007ca2c  mov     rax, rsp
0x18007ca2f  mov     [rax+10h], rbx
0x18007ca33  mov     [rax+18h], rbp
0x18007ca37  mov     [rax+20h], r9
0x18007ca3b  push    rsi
0x18007ca3c  push    rdi
0x18007ca3d  push    r12
0x18007ca3f  push    r14
0x18007ca41  push    r15
0x18007ca43  sub     rsp, 70h
0x18007ca47  mov     dword ptr [rax+8], 0
0x18007ca4e  xorps   xmm0, xmm0
0x18007ca51  mov     ebp, r8d
0x18007ca54  mov     rdi, rdx
0x18007ca57  mov     rsi, rcx
0x18007ca5a  movups  xmmword ptr [rax-38h], xmm0
0x18007ca5e  test    r9, r9
0x18007ca61  jnz     short loc_18007CA81
0x18007ca63  test    r8d, r8d
0x18007ca66  jz      short loc_18007CA81
0x18007ca68  mov     r8d, 559h; unsigned int
0x18007ca6e  lea     rdx, aOnecoreDsNetap_7; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18007ca75  lea     rcx, aNldccacheentry; "NlDcCacheEntry != NULL || (NlDcCacheEnt"...
0x18007ca7c  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18007ca81  cmp     [rsp+98h+arg_20], 0
0x18007ca8a  jnz     short loc_18007CAA9
0x18007ca8c  test    ebp, ebp
0x18007ca8e  jz      short loc_18007CAA9
0x18007ca90  mov     r8d, 55Ch; unsigned int
0x18007ca96  lea     rdx, aOnecoreDsNetap_7; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18007ca9d  lea     rcx, aUsednetbiosNul; "UsedNetbios != NULL || (UsedNetbios == "...
0x18007caa4  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18007caa9  mov     r12, [rsp+98h+arg_28]
0x18007cab1  lea     r15, [rsi+0A8h]
0x18007cab8  mov     dword ptr [r12], 0
0x18007cac0  test    rdi, rdi
0x18007cac3  jnz     short loc_18007CAC8
0x18007cac5  mov     rdi, [r15]
0x18007cac8  cmp     rdi, r15
0x18007cacb  jz      loc_18007CDCF
0x18007cad1  test    byte ptr [rdi+10Ch], 1
0x18007cad8  jnz     loc_18007CD79
0x18007cade  cmp     qword ptr [rdi+0F0h], 0
0x18007cae6  jnz     short loc_18007CB62
0x18007cae8  lea     rbx, [rdi+0A8h]
0x18007caef  mov     rcx, rsi; struct _NL_GETDC_CONTEXT *
0x18007caf2  mov     rdx, rbx; char *
0x18007caf5  call    ?NlGetLocatorLdapConnection@@YAPEAU_CACHED_CONNECTION@@PEAU_NL_GETDC_CONTEXT@@PEADK@Z; NlGetLocatorLdapConnection(_NL_GETDC_CONTEXT *,char *,ulong)
0x18007cafa  mov     [rdi+0F0h], rax
0x18007cb01  test    rax, rax
0x18007cb04  jnz     short loc_18007CB62
0x18007cb06  call    cs:__imp_GetLastError
0x18007cb0c  mov     r8, [rsi+48h]
0x18007cb10  lea     rdx, aNetpdcpinglist_2; "NetpDcPingListIp: %ws: Cannot LdapOpen "...
0x18007cb17  mov     r9, rbx
0x18007cb1a  mov     dword ptr [rsp+98h+attrs], eax
0x18007cb1e  mov     ecx, 100h; unsigned int
0x18007cb23  mov     r14d, eax
0x18007cb26  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007cb2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cb32  test    byte ptr [rcx+1Ch], 4
0x18007cb36  jz      loc_18007CD79
0x18007cb3c  cmp     byte ptr [rcx+19h], 2
0x18007cb40  jb      loc_18007CD79
0x18007cb46  mov     r9, [rsi+48h]
0x18007cb4a  mov     rcx, [rcx+10h]
0x18007cb4e  mov     [rsp+98h+attrsonly], r14d
0x18007cb53  mov     [rsp+98h+attrs], rbx
0x18007cb58  call    WPP_SF_Ssl
0x18007cb5d  jmp     loc_18007CD79
0x18007cb62  mov     rcx, rdi; struct _NL_DC_ADDRESS *
0x18007cb65  call    ?NetpGrowLdapMsgIdArrayIfNecessary@@YAKPEAU_NL_DC_ADDRESS@@@Z; NetpGrowLdapMsgIdArrayIfNecessary(_NL_DC_ADDRESS *)
0x18007cb6a  mov     ebx, eax
0x18007cb6c  test    eax, eax
0x18007cb6e  jnz     loc_18007CDD6
0x18007cb74  mov     r8, [rsi+48h]
0x18007cb78  lea     rbx, [rdi+0A8h]
0x18007cb7f  mov     r9, rbx
0x18007cb82  lea     rdx, aNetpdcpinglist_0; "NetpDcPingListIp: %ws: Sending UDP ping"...
0x18007cb89  lea     ecx, [rax+10h]; unsigned int
0x18007cb8c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007cb91  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cb98  test    byte ptr [rcx+1Ch], 4
0x18007cb9c  jz      short loc_18007CBC2
0x18007cb9e  cmp     byte ptr [rcx+19h], 5
0x18007cba2  jb      short loc_18007CBC2
0x18007cba4  mov     r9, [rsi+48h]
0x18007cba8  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x18007cbaf  mov     rcx, [rcx+10h]
0x18007cbb3  mov     edx, 1Dh
0x18007cbb8  mov     [rsp+98h+attrs], rbx
0x18007cbbd  call    WPP_SF_Ss
0x18007cbc2  mov     r9, [rsi+0A0h]; filter
0x18007cbc9  lea     rax, aNetlogon_3; "Netlogon"
0x18007cbd0  mov     [rsp+98h+var_38], rax
0x18007cbd5  xor     r8d, r8d; scope
0x18007cbd8  mov     [rsp+98h+var_30], 0
0x18007cbe1  lea     rax, [rsp+98h+arg_0]
0x18007cbe9  mov     rcx, [rdi+0F0h]
0x18007cbf0  xor     edx, edx; base
0x18007cbf2  mov     [rsp+98h+MessageNumber], rax; MessageNumber
0x18007cbf7  lea     rax, [rsp+98h+var_38]
0x18007cbfc  mov     [rsp+98h+SizeLimit], 0; SizeLimit
0x18007cc04  mov     [rsp+98h+TimeLimit], 0; TimeLimit
0x18007cc0c  mov     rcx, [rcx]; ld
0x18007cc0f  mov     [rsp+98h+ClientControls], 0; ClientControls
0x18007cc18  mov     [rsp+98h+ServerControls], 0; ServerControls
0x18007cc21  mov     [rsp+98h+attrsonly], 0; attrsonly
0x18007cc29  mov     [rsp+98h+attrs], rax; attrs
0x18007cc2e  call    cs:__imp_ldap_search_extA
0x18007cc34  mov     r14d, eax
0x18007cc37  test    eax, eax
0x18007cc39  jz      short loc_18007CCB6
0x18007cc3b  mov     ecx, eax; err
0x18007cc3d  call    cs:__imp_ldap_err2stringA
0x18007cc43  mov     r8, [rsi+48h]
0x18007cc47  lea     rdx, aNetpdcpinglist; "NetpDcPingListIp: %ws: Cannot LdapOpen "...
0x18007cc4e  mov     qword ptr [rsp+98h+attrsonly], rax
0x18007cc53  mov     r9, rbx
0x18007cc56  mov     ecx, 100h; unsigned int
0x18007cc5b  mov     dword ptr [rsp+98h+attrs], r14d
0x18007cc60  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007cc65  mov     rax, cs:WPP_GLOBAL_Control
0x18007cc6c  test    byte ptr [rax+1Ch], 4
0x18007cc70  jz      loc_18007CD79
0x18007cc76  cmp     byte ptr [rax+19h], 2
0x18007cc7a  jb      loc_18007CD79
0x18007cc80  mov     ecx, r14d; err
0x18007cc83  call    cs:__imp_ldap_err2stringA
0x18007cc89  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cc90  mov     edx, 1Eh
0x18007cc95  mov     r9, [rsi+48h]
0x18007cc99  mov     [rsp+98h+ServerControls], rax; __int64
0x18007cc9e  mov     [rsp+98h+attrsonly], r14d; char
0x18007cca3  mov     rcx, [rcx+10h]; LoggerHandle
0x18007cca7  mov     [rsp+98h+attrs], rbx; __int64
0x18007ccac  call    WPP_SF_Ssls
0x18007ccb1  jmp     loc_18007CD79
0x18007ccb6  lock inc cs:qword_1800F1E38
0x18007ccbe  mov     rax, [rsi+70h]
0x18007ccc2  mov     rcx, [rax+168h]
0x18007ccc9  lock inc qword ptr [rcx+0B8h]
0x18007ccd1  mov     eax, [rsp+98h+arg_0]
0x18007ccd8  mov     edx, [rdi+104h]
0x18007ccde  mov     rcx, [rdi+0F8h]
0x18007cce5  mov     [rcx+rdx*4], eax
0x18007cce8  inc     dword ptr [rdi+104h]
0x18007ccee  inc     dword ptr [r12]
0x18007ccf2  mov     eax, [r12]
0x18007ccf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ccfd  test    byte ptr [rcx+1Ch], 4
0x18007cd01  jz      short loc_18007CD2E
0x18007cd03  cmp     byte ptr [rcx+19h], 4
0x18007cd07  jb      short loc_18007CD2E
0x18007cd09  mov     r9, [rsi+48h]
0x18007cd0d  mov     rcx, [rcx+10h]
0x18007cd11  mov     dword ptr [rsp+98h+ClientControls], eax
0x18007cd15  mov     eax, [rsp+98h+arg_0]
0x18007cd1c  mov     dword ptr [rsp+98h+ServerControls], eax
0x18007cd20  mov     [rsp+98h+attrsonly], eax
0x18007cd24  mov     [rsp+98h+attrs], rbx
0x18007cd29  call    WPP_SF_SsDdD
0x18007cd2e  test    ebp, ebp
0x18007cd30  jz      short loc_18007CD79
0x18007cd32  cmp     dword ptr [rdi+108h], 0
0x18007cd39  jnz     short loc_18007CD54
0x18007cd3b  mov     r8d, 600h; unsigned int
0x18007cd41  lea     rdx, aOnecoreDsNetap_7; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18007cd48  lea     rcx, aDcaddressAddre; "DcAddress->AddressPingWait != 0"
0x18007cd4f  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18007cd54  mov     r9, [rsp+98h+arg_20]; int *
0x18007cd5c  mov     rcx, rsi; struct _NL_GETDC_CONTEXT *
0x18007cd5f  mov     r8, [rsp+98h+arg_18]; struct _NL_DC_CACHE_ENTRY **
0x18007cd67  mov     edx, [rdi+108h]; unsigned int
0x18007cd6d  call    ?NetpDcGetPingResponse@@YAKPEAU_NL_GETDC_CONTEXT@@KPEAPEAU_NL_DC_CACHE_ENTRY@@PEAH@Z; NetpDcGetPingResponse(_NL_GETDC_CONTEXT *,ulong,_NL_DC_CACHE_ENTRY * *,int *)
0x18007cd72  mov     ebx, eax
0x18007cd74  cmp     eax, 79h ; 'y'
0x18007cd77  jnz     short loc_18007CD81
0x18007cd79  mov     rdi, [rdi]
0x18007cd7c  jmp     loc_18007CAC8
0x18007cd81  test    ebx, ebx
0x18007cd83  jz      short loc_18007CDD6
0x18007cd85  mov     r8, [rsi+48h]
0x18007cd89  lea     rdx, aNetpdcpinglist_1; "NetpDcPingListIp: %ws: Cannot NetpDcGet"...
0x18007cd90  mov     r9d, ebx
0x18007cd93  mov     ecx, 100h; unsigned int
0x18007cd98  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007cd9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cda4  test    byte ptr [rcx+1Ch], 4
0x18007cda8  jz      short loc_18007CDD6
0x18007cdaa  cmp     byte ptr [rcx+19h], 2
0x18007cdae  jb      short loc_18007CDD6
0x18007cdb0  mov     r9, [rsi+48h]
0x18007cdb4  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x18007cdbb  mov     rcx, [rcx+10h]
0x18007cdbf  mov     edx, 20h ; ' '
0x18007cdc4  mov     dword ptr [rsp+98h+attrs], ebx
0x18007cdc8  call    WPP_SF_SL
0x18007cdcd  jmp     short loc_18007CDD6
0x18007cdcf  neg     ebp
0x18007cdd1  sbb     ebx, ebx
0x18007cdd3  and     ebx, 79h
0x18007cdd6  lea     r11, [rsp+98h+var_28]
0x18007cddb  mov     eax, ebx
0x18007cddd  mov     rbx, [r11+38h]
0x18007cde1  mov     rbp, [r11+40h]
0x18007cde5  mov     rsp, r11
0x18007cde8  pop     r15
0x18007cdea  pop     r14
0x18007cdec  pop     r12
0x18007cdee  pop     rdi
0x18007cdef  pop     rsi
0x18007cdf0  retn
```
