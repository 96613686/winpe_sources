# LDAP_CONN_CACHE_ENTRY::Initialize(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180026040`
- end: `0x180026489`
- name: `?Initialize@LDAP_CONN_CACHE_ENTRY@@QEAAJPEBG000@Z`
- size: `1097`
- prototype: `__int64 __fastcall(LDAP_CONN_CACHE_ENTRY *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180025db4`

## callees

- `0x180026040`

## import_xrefs

- `msvcrt!wcschr` at `0x180026155`
- `msvcrt!wcschr` at `0x180026155`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180026176`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180026176`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026075`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002608f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800260a9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800260c4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180026075`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002608f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800260a9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800260c4`
- `iisutil!PuDbgPrint` at `0x1800262a9`
- `iisutil!PuDbgPrint` at `0x1800262a9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002618e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800261aa`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180026231`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18002618e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800261aa`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180026231`
- `iisutil!PuDbgPrintError` at `0x1800261ea`
- `iisutil!PuDbgPrintError` at `0x1800261ea`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800262c9`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18002630d`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180026353`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180026391`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800263ce`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800262c9`
- `WLDAP32!__imp_ldap_set_optionW` at `0x18002630d`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180026353`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180026391`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800263ce`
- `WLDAP32!__imp_LdapGetLastError` at `0x180026259`
- `WLDAP32!__imp_LdapGetLastError` at `0x180026259`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18002620d`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18002620d`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180026453`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180026453`
- `WLDAP32!__imp_ldap_initW` at `0x180026247`
- `WLDAP32!__imp_ldap_initW` at `0x180026247`
- `NETAPI32!DsGetDcNameW` at `0x1800260f1`
- `NETAPI32!DsGetDcNameW` at `0x1800260f1`
- `NETAPI32!NetApiBufferFree` at `0x1800261f9`
- `NETAPI32!NetApiBufferFree` at `0x1800261f9`

## string_xrefs

- `0x1800261dc`: `LDAP_CONN_CACHE_ENTRY::Initialize`
- `0x180026296`: `LDAP_CONN_CACHE_ENTRY::Initialize`
- `0x1800261e3`: `inetsrv\iis\iisrearc\ftp\server\ftp_ad_isolation\ldap_conn_cache.cxx`
- `0x18002629d`: `inetsrv\iis\iisrearc\ftp\server\ftp_ad_isolation\ldap_conn_cache.cxx`

## pseudocode

```c
__int64 __fastcall LDAP_CONN_CACHE_ENTRY::Initialize(
        LDAP_CONN_CACHE_ENTRY *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  ULONG LastError; // edi
  signed int v9; // ebx
  signed int DcNameW; // eax
  const wchar_t *DomainName; // r14
  wchar_t *v12; // rax
  STRU *v13; // rcx
  wchar_t *v14; // r15
  int v15; // eax
  signed int v16; // eax
  LDAP *v18; // rax
  ULONG v19; // eax
  LDAP *v20; // rcx
  ULONG v21; // eax
  LDAP *v22; // rcx
  ULONG v23; // eax
  ULONG v24; // eax
  ULONG v25; // eax
  LDAP *v26; // rcx
  ULONG v27; // eax
  PDOMAIN_CONTROLLER_INFOW *DomainControllerInfo; // [rsp+28h] [rbp-50h]
  PDOMAIN_CONTROLLER_INFOW v29; // [rsp+30h] [rbp-48h] BYREF
  WCHAR cred[8]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v31; // [rsp+48h] [rbp-30h]
  __int128 v32; // [rsp+58h] [rbp-20h]
  int invalue; // [rsp+B0h] [rbp+38h] BYREF

  LastError = 0;
  invalue = 0;
  *(_OWORD *)cred = 0;
  v29 = 0;
  v31 = 0;
  v32 = 0;
  v9 = STRU::Copy((LDAP_CONN_CACHE_ENTRY *)((char *)this + 24), a2);
  if ( v9 < 0 )
    goto LABEL_19;
  v9 = STRU::Copy((LDAP_CONN_CACHE_ENTRY *)((char *)this + 144), a3);
  if ( v9 < 0 )
    goto LABEL_19;
  v9 = STRU::Copy((LDAP_CONN_CACHE_ENTRY *)((char *)this + 264), a4);
  if ( v9 < 0 )
    goto LABEL_19;
  v9 = STRU::Copy((LDAP_CONN_CACHE_ENTRY *)((char *)this + 384), a5);
  if ( v9 < 0 )
    goto LABEL_19;
  DcNameW = DsGetDcNameW(0, *((LPCWSTR *)this + 7), 0, 0, 0x40000010u, &v29);
  v9 = DcNameW;
  if ( DcNameW )
  {
    if ( DcNameW > 0 )
      v9 = (unsigned __int16)DcNameW | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ad_isolation\\ldap_conn_cache.cxx",
        148,
        "LDAP_CONN_CACHE_ENTRY::Initialize",
        v9,
        "DsGetDcName() failed");
    goto LABEL_19;
  }
  DomainName = v29->DomainName;
  **((_WORD **)this + 67) = 0;
  *((_DWORD *)this + 138) = 0;
  while ( 1 )
  {
    v15 = STRU::Append((LDAP_CONN_CACHE_ENTRY *)((char *)this + 504), L"DC=");
    if ( v15 < 0 )
    {
      v9 = v15;
      goto LABEL_17;
    }
    v12 = wcschr(DomainName, 0x2Eu);
    v13 = (LDAP_CONN_CACHE_ENTRY *)((char *)this + 504);
    v14 = v12;
    if ( !v12 )
      break;
    v15 = STRU::Append(v13, DomainName, v12 - DomainName);
    if ( v15 < 0 )
      goto LABEL_26;
    v15 = STRU::Append((LDAP_CONN_CACHE_ENTRY *)((char *)this + 504), L",");
    if ( v15 < 0 )
      goto LABEL_26;
    DomainName = v14 + 1;
  }
  v15 = STRU::Append(v13, DomainName);
LABEL_26:
  v9 = v15;
  if ( v15 < 0 )
  {
LABEL_17:
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ad_isolation\\ldap_conn_cache.cxx",
        163,
        "LDAP_CONN_CACHE_ENTRY::Initialize",
        v15,
        "StoreForestNameAsDN() failed");
    goto LABEL_19;
  }
  v18 = ldap_initW(*((const PWSTR *)this + 7), 0);
  *((_QWORD *)this + 102) = v18;
  if ( v18 )
  {
    invalue = 3;
    v19 = ldap_set_optionW(v18, 17, &invalue);
    LastError = v19;
    if ( v19 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(DomainControllerInfo) = v19;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ad_isolation\\ldap_conn_cache.cxx",
          202,
          "LDAP_CONN_CACHE_ENTRY::Initialize",
          "ldap_set_option(LDAP_OPT_VERSION) failed (0x%X)\n",
          DomainControllerInfo);
      }
    }
    else
    {
      v20 = (LDAP *)*((_QWORD *)this + 102);
      invalue = 1;
      v21 = ldap_set_optionW(v20, 3, &invalue);
      LastError = v21;
      if ( v21 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LODWORD(DomainControllerInfo) = v21;
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ad_isolation\\ldap_conn_cache.cxx",
            214,
            "LDAP_CONN_CACHE_ENTRY::Initialize",
            "ldap_set_option(LDAP_OPT_SIZELIMIT) failed (0x%X)\n",
            DomainControllerInfo);
        }
      }
      else
      {
        v22 = (LDAP *)*((_QWORD *)this + 102);
        invalue = 60;
        v23 = ldap_set_optionW(v22, 4, &invalue);
        LastError = v23;
        if ( v23 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            LODWORD(DomainControllerInfo) = v23;
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ad_isolation\\ldap_conn_cache.cxx",
              229,
              "LDAP_CONN_CACHE_ENTRY::Initialize",
              "ldap_set_option(LDAP_OPT_TIMELIMIT) failed (0x%X)\n",
              DomainControllerInfo);
          }
        }
        else
        {
          v24 = ldap_set_optionW(*((LDAP **)this + 102), 145, (const void *)1);
          LastError = v24;
          if ( v24 )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              LODWORD(DomainControllerInfo) = v24;
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ad_isolation\\ldap_conn_cache.cxx",
                240,
                "LDAP_CONN_CACHE_ENTRY::Initialize",
                "ldap_set_option(LDAP_OPT_AUTO_RECONNECT) failed (0x%X)\n",
                DomainControllerInfo);
            }
          }
          else
          {
            v25 = ldap_set_optionW(*((LDAP **)this + 102), 8, 0);
            LastError = v25;
            if ( v25 )
            {
              if ( (g_dwDebugFlags & 3) != 0 )
              {
                LODWORD(DomainControllerInfo) = v25;
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ad_isolation\\ldap_conn_cache.cxx",
                  249,
                  "LDAP_CONN_CACHE_ENTRY::Initialize",
                  "ldap_set_option(LDAP_OPT_REFERRALS) failed (0x%X)\n",
                  DomainControllerInfo);
              }
            }
            else
            {
              v26 = (LDAP *)*((_QWORD *)this + 102);
              *(_QWORD *)cred = *((_QWORD *)this + 22);
              *(_DWORD *)&cred[4] = *((_DWORD *)this + 48);
              *(_QWORD *)&v31 = *((_QWORD *)this + 37);
              DWORD2(v31) = *((_DWORD *)this + 78);
              *(_QWORD *)&v32 = *((_QWORD *)this + 52);
              DWORD2(v32) = *((_DWORD *)this + 108);
              HIDWORD(v32) = 2;
              v27 = ldap_bind_sW(v26, 0, cred, 0x486u);
              LastError = v27;
              if ( v27 )
              {
                if ( (g_dwDebugFlags & 3) != 0 )
                {
                  LODWORD(DomainControllerInfo) = v27;
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ad_isolation\\ldap_conn_cache.cxx",
                    279,
                    "LDAP_CONN_CACHE_ENTRY::Initialize",
                    "ldap_bind_s() failed (0x%X)\n",
                    DomainControllerInfo);
                }
              }
              else
              {
                v9 = 0;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    LastError = LdapGetLastError();
    if ( !LastError )
      LastError = 1;
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(DomainControllerInfo) = LastError;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_ad_isolation\\ldap_conn_cache.cxx",
        186,
        "LDAP_CONN_CACHE_ENTRY::Initialize",
        "ldap_init() failed (0x%X)",
        DomainControllerInfo);
    }
  }
LABEL_19:
  if ( v29 )
  {
    NetApiBufferFree(v29);
    v29 = 0;
  }
  if ( LastError )
  {
    v16 = LdapMapErrorToWin32(LastError);
    v9 = v16;
    if ( v16 > 0 )
      return (unsigned __int16)v16 | 0x80070000;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180026040  push    rbp
0x180026042  push    rbx
0x180026043  push    rsi
0x180026044  push    rdi
0x180026045  push    r14
0x180026047  push    r15
0x180026049  mov     rbp, rsp
0x18002604c  sub     rsp, 78h
0x180026050  xorps   xmm0, xmm0
0x180026053  mov     rsi, rcx
0x180026056  xor     edi, edi
0x180026058  add     rcx, 18h
0x18002605c  mov     [rbp+invalue], edi
0x18002605f  mov     r15, r9
0x180026062  movups  xmmword ptr [rbp+cred], xmm0
0x180026066  mov     [rbp+var_48], rdi
0x18002606a  mov     r14, r8
0x18002606d  movups  [rbp+var_30], xmm0
0x180026071  movups  [rbp+var_20], xmm0
0x180026075  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002607b  mov     ebx, eax
0x18002607d  test    eax, eax
0x18002607f  js      loc_1800261F0
0x180026085  lea     rcx, [rsi+90h]
0x18002608c  mov     rdx, r14
0x18002608f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180026095  mov     ebx, eax
0x180026097  test    eax, eax
0x180026099  js      loc_1800261F0
0x18002609f  lea     rcx, [rsi+108h]
0x1800260a6  mov     rdx, r15
0x1800260a9  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800260af  mov     ebx, eax
0x1800260b1  test    eax, eax
0x1800260b3  js      loc_1800261F0
0x1800260b9  mov     rdx, [rbp+arg_20]
0x1800260bd  lea     rcx, [rsi+180h]
0x1800260c4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800260ca  mov     ebx, eax
0x1800260cc  test    eax, eax
0x1800260ce  js      loc_1800261F0
0x1800260d4  mov     rdx, [rsi+38h]; DomainName
0x1800260d8  lea     rax, [rbp+var_48]
0x1800260dc  mov     [rsp+78h+DomainControllerInfo], rax; DomainControllerInfo
0x1800260e1  xor     r9d, r9d; SiteName
0x1800260e4  xor     r8d, r8d; DomainGuid
0x1800260e7  mov     [rsp+78h+Flags], 40000010h; Flags
0x1800260ef  xor     ecx, ecx; ComputerName
0x1800260f1  call    cs:__imp_DsGetDcNameW
0x1800260f7  mov     ebx, eax
0x1800260f9  test    eax, eax
0x1800260fb  jz      short loc_180026130
0x1800260fd  jle     short loc_180026108
0x1800260ff  movzx   ebx, ax
0x180026102  or      ebx, 80070000h
0x180026108  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002610f  jz      loc_1800261F0
0x180026115  lea     rax, aDsgetdcnameFai; "DsGetDcName() failed"
0x18002611c  mov     r8d, 94h
0x180026122  mov     [rsp+78h+DomainControllerInfo], rax
0x180026127  mov     [rsp+78h+Flags], ebx
0x18002612b  jmp     loc_1800261D5
0x180026130  mov     rax, [rbp+var_48]
0x180026134  lea     rbx, [rsi+1F8h]
0x18002613b  mov     rcx, [rbx+20h]
0x18002613f  mov     r14, [rax+28h]
0x180026143  xor     eax, eax
0x180026145  mov     [rcx], ax
0x180026148  mov     [rbx+30h], eax
0x18002614b  jmp     short loc_1800261A0
0x18002614d  mov     edx, 2Eh ; '.'; Ch
0x180026152  mov     rcx, r14; Str
0x180026155  call    cs:__imp_wcschr
0x18002615b  mov     rdx, r14
0x18002615e  mov     rcx, rbx
0x180026161  mov     r15, rax
0x180026164  test    rax, rax
0x180026167  jz      loc_180026231
0x18002616d  mov     r8, rax
0x180026170  sub     r8, r14
0x180026173  sar     r8, 1
0x180026176  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x18002617c  test    eax, eax
0x18002617e  js      loc_180026237
0x180026184  lea     rdx, asc_18004EC70; ","
0x18002618b  mov     rcx, rbx
0x18002618e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180026194  test    eax, eax
0x180026196  js      loc_180026237
0x18002619c  lea     r14, [r15+2]
0x1800261a0  lea     rdx, aDc; "DC="
0x1800261a7  mov     rcx, rbx
0x1800261aa  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800261b0  test    eax, eax
0x1800261b2  jns     short loc_18002614D
0x1800261b4  mov     ebx, eax
0x1800261b6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800261bd  jz      short loc_1800261F0
0x1800261bf  lea     rcx, aStoreforestnam; "StoreForestNameAsDN() failed"
0x1800261c6  mov     r8d, 0A3h
0x1800261cc  mov     [rsp+78h+DomainControllerInfo], rcx
0x1800261d1  mov     [rsp+78h+Flags], eax
0x1800261d5  mov     rcx, cs:g_pDebug
0x1800261dc  lea     r9, aLdapConnCacheE; "LDAP_CONN_CACHE_ENTRY::Initialize"
0x1800261e3  lea     rdx, aInetsrvIisIisr_5; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x1800261ea  call    cs:__imp_PuDbgPrintError
0x1800261f0  mov     rcx, [rbp+var_48]; Buffer
0x1800261f4  test    rcx, rcx
0x1800261f7  jz      short loc_180026207
0x1800261f9  call    cs:__imp_NetApiBufferFree
0x1800261ff  mov     [rbp+var_48], 0
0x180026207  test    edi, edi
0x180026209  jz      short loc_180026222
0x18002620b  mov     ecx, edi; LdapError
0x18002620d  call    cs:__imp_LdapMapErrorToWin32
0x180026213  mov     ebx, eax
0x180026215  test    eax, eax
0x180026217  jle     short loc_180026222
0x180026219  movzx   ebx, ax
0x18002621c  or      ebx, 80070000h
0x180026222  mov     eax, ebx
0x180026224  add     rsp, 78h
0x180026228  pop     r15
0x18002622a  pop     r14
0x18002622c  pop     rdi
0x18002622d  pop     rsi
0x18002622e  pop     rbx
0x18002622f  pop     rbp
0x180026230  retn
0x180026231  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180026237  mov     ebx, eax
0x180026239  test    eax, eax
0x18002623b  js      loc_1800261B6
0x180026241  mov     rcx, [rsi+38h]; HostName
0x180026245  xor     edx, edx; PortNumber
0x180026247  call    cs:__imp_ldap_initW
0x18002624d  mov     [rsi+330h], rax
0x180026254  test    rax, rax
0x180026257  jnz     short loc_1800262B4
0x180026259  call    cs:__imp_LdapGetLastError
0x18002625f  mov     r15d, 1
0x180026265  test    eax, eax
0x180026267  mov     edi, eax
0x180026269  cmovz   edi, r15d
0x18002626d  lea     r14d, [r15+2]
0x180026271  test    byte ptr cs:g_dwDebugFlags, r14b
0x180026278  jz      loc_1800261F0
0x18002627e  mov     dword ptr [rsp+78h+DomainControllerInfo], edi
0x180026282  lea     rax, aLdapInitFailed; "ldap_init() failed (0x%X)"
0x180026289  mov     r8d, 0BAh
0x18002628f  mov     rcx, cs:g_pDebug
0x180026296  lea     r9, aLdapConnCacheE; "LDAP_CONN_CACHE_ENTRY::Initialize"
0x18002629d  lea     rdx, aInetsrvIisIisr_5; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x1800262a4  mov     qword ptr [rsp+78h+Flags], rax
0x1800262a9  call    cs:__imp_PuDbgPrint
0x1800262af  jmp     loc_1800261F0
0x1800262b4  mov     r14d, 3
0x1800262ba  lea     r8, [rbp+invalue]; invalue
0x1800262be  mov     rcx, rax; ld
0x1800262c1  mov     [rbp+invalue], r14d
0x1800262c5  lea     edx, [r14+0Eh]; option
0x1800262c9  call    cs:__imp_ldap_set_optionW
0x1800262cf  mov     edi, eax
0x1800262d1  test    eax, eax
0x1800262d3  jz      short loc_1800262F5
0x1800262d5  test    byte ptr cs:g_dwDebugFlags, r14b
0x1800262dc  jz      loc_1800261F0
0x1800262e2  mov     dword ptr [rsp+78h+DomainControllerInfo], eax
0x1800262e6  mov     r8d, 0CAh
0x1800262ec  lea     rax, aLdapSetOptionL_2; "ldap_set_option(LDAP_OPT_VERSION) faile"...
0x1800262f3  jmp     short loc_18002628F
0x1800262f5  mov     rcx, [rsi+330h]; ld
0x1800262fc  lea     r8, [rbp+invalue]; invalue
0x180026300  mov     r15d, 1
0x180026306  mov     edx, r14d; option
0x180026309  mov     [rbp+invalue], r15d
0x18002630d  call    cs:__imp_ldap_set_optionW
0x180026313  mov     edi, eax
0x180026315  test    eax, eax
0x180026317  jz      short loc_18002633C
0x180026319  test    byte ptr cs:g_dwDebugFlags, r14b
0x180026320  jz      loc_1800261F0
0x180026326  mov     dword ptr [rsp+78h+DomainControllerInfo], eax
0x18002632a  mov     r8d, 0D6h
0x180026330  lea     rax, aLdapSetOptionL_1; "ldap_set_option(LDAP_OPT_SIZELIMIT) fai"...
0x180026337  jmp     loc_18002628F
0x18002633c  mov     rcx, [rsi+330h]; ld
0x180026343  lea     r8, [rbp+invalue]; invalue
0x180026347  mov     edx, 4; option
0x18002634c  mov     [rbp+invalue], 3Ch ; '<'
0x180026353  call    cs:__imp_ldap_set_optionW
0x180026359  mov     edi, eax
0x18002635b  test    eax, eax
0x18002635d  jz      short loc_180026382
0x18002635f  test    byte ptr cs:g_dwDebugFlags, r14b
0x180026366  jz      loc_1800261F0
0x18002636c  mov     dword ptr [rsp+78h+DomainControllerInfo], eax
0x180026370  mov     r8d, 0E5h
0x180026376  lea     rax, aLdapSetOptionL_3; "ldap_set_option(LDAP_OPT_TIMELIMIT) fai"...
0x18002637d  jmp     loc_18002628F
0x180026382  mov     rcx, [rsi+330h]; ld
0x180026389  mov     r8, r15; invalue
0x18002638c  mov     edx, 91h; option
0x180026391  call    cs:__imp_ldap_set_optionW
0x180026397  mov     edi, eax
0x180026399  test    eax, eax
0x18002639b  jz      short loc_1800263C0
0x18002639d  test    byte ptr cs:g_dwDebugFlags, r14b
0x1800263a4  jz      loc_1800261F0
0x1800263aa  mov     dword ptr [rsp+78h+DomainControllerInfo], eax
0x1800263ae  mov     r8d, 0F0h
0x1800263b4  lea     rax, aLdapSetOptionL_0; "ldap_set_option(LDAP_OPT_AUTO_RECONNECT"...
0x1800263bb  jmp     loc_18002628F
0x1800263c0  mov     rcx, [rsi+330h]; ld
0x1800263c7  xor     r8d, r8d; invalue
0x1800263ca  lea     edx, [r8+8]; option
0x1800263ce  call    cs:__imp_ldap_set_optionW
0x1800263d4  mov     edi, eax
0x1800263d6  test    eax, eax
0x1800263d8  jz      short loc_1800263FD
0x1800263da  test    byte ptr cs:g_dwDebugFlags, r14b
0x1800263e1  jz      loc_1800261F0
0x1800263e7  mov     dword ptr [rsp+78h+DomainControllerInfo], eax
0x1800263eb  mov     r8d, 0F9h
0x1800263f1  lea     rax, aLdapSetOptionL; "ldap_set_option(LDAP_OPT_REFERRALS) fai"...
0x1800263f8  jmp     loc_18002628F
0x1800263fd  mov     rax, [rsi+0B0h]
0x180026404  lea     r8, [rbp+cred]; cred
0x180026408  mov     rcx, [rsi+330h]; ld
0x18002640f  mov     r9d, 486h; method
0x180026415  mov     qword ptr [rbp+cred], rax
0x180026419  xor     edx, edx; dn
0x18002641b  mov     eax, [rsi+0C0h]
0x180026421  mov     dword ptr [rbp+cred+8], eax
0x180026424  mov     rax, [rsi+128h]
0x18002642b  mov     qword ptr [rbp+var_30], rax
0x18002642f  mov     eax, [rsi+138h]
0x180026435  mov     dword ptr [rbp+var_30+8], eax
0x180026438  mov     rax, [rsi+1A0h]
0x18002643f  mov     qword ptr [rbp+var_20], rax
0x180026443  mov     eax, [rsi+1B0h]
0x180026449  mov     dword ptr [rbp+var_20+8], eax
0x18002644c  mov     dword ptr [rbp+var_20+0Ch], 2
0x180026453  call    cs:__imp_ldap_bind_sW
0x180026459  mov     edi, eax
0x18002645b  test    eax, eax
0x18002645d  jz      short loc_180026482
0x18002645f  test    byte ptr cs:g_dwDebugFlags, r14b
0x180026466  jz      loc_1800261F0
0x18002646c  mov     dword ptr [rsp+78h+DomainControllerInfo], eax
0x180026470  mov     r8d, 117h
0x180026476  lea     rax, aLdapBindSFaile; "ldap_bind_s() failed (0x%X)\n"
0x18002647d  jmp     loc_18002628F
0x180026482  xor     ebx, ebx
0x180026484  jmp     loc_1800261F0
```
