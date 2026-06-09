# IsCallFromAuthorizedLicenseServer(void)

- ea: `0x18000a50c`
- end: `0x18000acee`
- name: `?IsCallFromAuthorizedLicenseServer@@YAHXZ`
- size: `2018`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x1800102e0`
- `0x180010500`
- `0x180010b60`
- `0x180013390`
- `0x180019360`

## callees

- `0x180005665`
- `0x18000644c`
- `0x180006d38`
- `0x18000a048`
- `0x18000a2b4`
- `0x18000a2d8`
- `0x18000a50c`
- `0x18001aea4`
- `0x18001afb4`
- `0x18001b028`
- `0x18001b128`
- `0x18001b1dc`
- `0x18001b2a4`
- `0x18001b374`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a8f3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ac92`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000aca7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a8f3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ac92`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000aca7`
- `mstlsapi!??0CLSDiscoveryPolicy@@QEAA@PEAW4LS_DISC_MECH_ENUM@@@Z` at `0x18000a964`
- `mstlsapi!??0CLSDiscoveryPolicy@@QEAA@PEAW4LS_DISC_MECH_ENUM@@@Z` at `0x18000a964`
- `mstlsapi!??0CLSDiscovery@@QEAA@PEBVCLSDiscoveryPolicy@@@Z` at `0x18000a98b`
- `mstlsapi!??0CLSDiscovery@@QEAA@PEBVCLSDiscoveryPolicy@@@Z` at `0x18000a98b`
- `mstlsapi!??1CLSDiscovery@@UEAA@XZ` at `0x18000ac4f`
- `mstlsapi!??1CLSDiscovery@@UEAA@XZ` at `0x18000ac4f`
- `mstlsapi!?Refresh@CLSDiscovery@@QEAAKXZ` at `0x18000a9a0`
- `mstlsapi!?Refresh@CLSDiscovery@@QEAAKXZ` at `0x18000a9a0`
- `mstlsapi!?Begin@CLSDiscovery@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVCDiscoveredLS@@@std@@@std@@@std@@XZ` at `0x18000aa16`
- `mstlsapi!?Begin@CLSDiscovery@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVCDiscoveredLS@@@std@@@std@@@std@@XZ` at `0x18000aa16`
- `mstlsapi!?End@CLSDiscovery@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVCDiscoveredLS@@@std@@@std@@@std@@XZ` at `0x18000aa4c`
- `mstlsapi!?End@CLSDiscovery@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVCDiscoveredLS@@@std@@@std@@@std@@XZ` at `0x18000aa4c`
- `mstlsapi!?Next@CLSDiscovery@@QEAAPEAVCDiscoveredLS@@AEAV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVCDiscoveredLS@@@std@@@std@@@std@@@Z` at `0x18000aa73`
- `mstlsapi!?Next@CLSDiscovery@@QEAAPEAVCDiscoveredLS@@AEAV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVCDiscoveredLS@@@std@@@std@@@std@@@Z` at `0x18000aa73`
- `mstlsapi!__imp_TLSInDomain` at `0x18000a7b5`
- `mstlsapi!__imp_TLSInDomain` at `0x18000a7b5`
- `mstlsapi!__imp_TLSGetInfoForDiscoveredLicenseServer` at `0x18000ab96`
- `mstlsapi!__imp_TLSGetInfoForDiscoveredLicenseServer` at `0x18000ab96`
- `mstlsapi!__imp_TLSGetLsNameFormat` at `0x18000aad9`
- `mstlsapi!__imp_TLSGetLsNameFormat` at `0x18000aad9`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18000a6a3`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18000a6a3`
- `RPCRT4!RpcServerInqBindingHandle` at `0x18000a54f`
- `RPCRT4!RpcServerInqBindingHandle` at `0x18000a54f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000a5c4`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000a5c4`
- `KERNEL32!LocalFree` at `0x18000a75d`
- `KERNEL32!LocalFree` at `0x18000a75d`

## pseudocode

```c
__int64 IsCallFromAuthorizedLicenseServer(void)
{
  signed int v0; // r14d
  unsigned int v1; // r15d
  RPC_STATUS v2; // eax
  RPC_STATUS v3; // eax
  signed int Error; // eax
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  PVOID *v8; // rcx
  int v9; // eax
  unsigned int v10; // eax
  char v11; // bl
  int v12; // eax
  int WorkgroupLicenseServerAccountsGroupSid; // eax
  int v14; // eax
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  PVOID *v18; // rcx
  void *v19; // rbx
  void *v20; // rdi
  unsigned __int64 i; // rax
  unsigned int v22; // eax
  _QWORD *v23; // rax
  unsigned int *v24; // r14
  int v25; // eax
  int v26; // r14d
  _DWORD *v27; // r14
  int v28; // edx
  int v29; // r8d
  int v30; // r9d
  int v31; // eax
  int v33; // [rsp+40h] [rbp-1B8h] BYREF
  int v34; // [rsp+44h] [rbp-1B4h]
  PSID Sid; // [rsp+48h] [rbp-1B0h] BYREF
  int v36; // [rsp+50h] [rbp-1A8h] BYREF
  unsigned int v37; // [rsp+54h] [rbp-1A4h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-1A0h] BYREF
  __int64 v39; // [rsp+60h] [rbp-198h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-190h] BYREF
  unsigned __int64 v41; // [rsp+70h] [rbp-188h]
  void *v42; // [rsp+78h] [rbp-180h]
  void *v43; // [rsp+80h] [rbp-178h]
  _BYTE v44[8]; // [rsp+88h] [rbp-170h] BYREF
  _BYTE v45[8]; // [rsp+90h] [rbp-168h] BYREF
  _BYTE v46[32]; // [rsp+98h] [rbp-160h] BYREF
  int v47; // [rsp+B8h] [rbp-140h]
  _DWORD RpcCallAttributes[22]; // [rsp+C0h] [rbp-138h] BYREF
  __int16 v49; // [rsp+118h] [rbp-E0h]
  _BYTE v50[160]; // [rsp+130h] [rbp-C8h] BYREF

  v0 = 0;
  v1 = 0;
  v33 = 0;
  Binding = 0;
  v2 = RpcServerInqBindingHandle(&Binding);
  if ( v2 == 1725 )
  {
    v1 = 1;
    v33 = 1;
  }
  else if ( v2 )
  {
    v0 = v2 | 0x80010000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
        (unsigned int)L"IsCallFromAuthorizedLicenseServer",
        v2);
  }
  memset_0(RpcCallAttributes, 0, 0x70u);
  if ( v0 >= 0 && !v1 )
  {
    RpcCallAttributes[0] = 2;
    RpcCallAttributes[1] = 32;
    v3 = RpcServerInqCallAttributesW(Binding, RpcCallAttributes);
    if ( v3 )
    {
      v0 = v3 | 0x80010000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
          (unsigned int)L"IsCallFromAuthorizedLicenseServer",
          v3);
      goto LABEL_31;
    }
    if ( RpcCallAttributes[15] != 1 )
      goto LABEL_31;
    Sid = 0;
    if ( !ConvertStringSidToSidW(L"S-1-5-80-3893474178-2562712516-324399186-2343250756-2176344804", &Sid) )
    {
      Error = HResultFromLastError();
      v0 = Error;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
          (unsigned int)L"IsCallFromAuthorizedLicenseServer",
          Error);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v0 < 0 )
        goto LABEL_25;
    }
    v9 = CheckRpcCallerTokenMembership(Binding, Sid, &v33);
    v0 = v9;
    if ( v9 < 0 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
        goto LABEL_24;
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        v6,
        (unsigned int)L"IsCallFromAuthorizedLicenseServer",
        (__int64)L"S-1-5-80-3893474178-2562712516-324399186-2343250756-2176344804",
        v9);
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_24:
    v1 = v33;
LABEL_25:
    if ( Sid )
    {
      LocalFree(Sid);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v1 && v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x1000) != 0 )
      WPP_SF_SHS((unsigned int)v8[2], v5, v6, v7, v49);
  }
LABEL_31:
  v36 = 0;
  if ( v0 >= 0 && !v1 )
  {
    v10 = TLSInDomain(&v36, 0);
    v11 = v10;
    if ( !v10 )
      goto LABEL_38;
    v0 = HResultFromWin32Error(v10);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
        (unsigned int)L"IsCallFromAuthorizedLicenseServer",
        v11);
    if ( v0 >= 0 )
    {
LABEL_38:
      v12 = v36;
      if ( v36 )
      {
LABEL_53:
        if ( !v1 && v12 )
        {
          v19 = 0;
          v43 = 0;
          v20 = 0;
          v42 = 0;
          for ( i = 0; ; i = v41 + 1 )
          {
            v41 = i;
            if ( v0 < 0 || v1 || i >= 2 )
              break;
            try
            {
              CLSDiscoveryPolicy::CLSDiscoveryPolicy(
                (CLSDiscoveryPolicy *)v46,
                (enum LS_DISC_MECH_ENUM *)((char *)qword_1800E6720 + 12 * i));
              v47 = 488;
              CLSDiscovery::CLSDiscovery((CLSDiscovery *)v50, (const struct CLSDiscoveryPolicy *)v46);
              v22 = CLSDiscovery::Refresh((CLSDiscovery *)v50);
              LODWORD(Sid) = v22;
              if ( v22 )
              {
                v0 = HResultFromWin32Error(v22);
                v34 = v0;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                  WPP_SF_SD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    36,
                    (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
                    (unsigned int)L"IsCallFromAuthorizedLicenseServer",
                    (char)Sid);
              }
              v39 = 0;
              if ( v0 >= 0 )
              {
                v39 = *(_QWORD *)CLSDiscovery::Begin(v50, v44);
                while ( !v1 )
                {
                  v23 = (_QWORD *)CLSDiscovery::End(v50, v45);
                  if ( *v23 == v39 )
                    break;
                  v24 = (unsigned int *)CLSDiscovery::Next(v50, &v39);
                  Sid = v24;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                    WPP_SF_SSd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      37,
                      &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
                      L"IsCallFromAuthorizedLicenseServer");
                  v37 = 0;
                  v25 = TLSGetLsNameFormat(v24, v24[130], &v37);
                  v26 = v25;
                  v34 = v25;
                  if ( v25 >= 0 )
                  {
                    if ( v37 - 2 > 1 )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                      {
                        WPP_SF_SS(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          39,
                          (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
                          (unsigned int)L"IsCallFromAuthorizedLicenseServer",
                          (__int64)Sid);
                      }
                      v26 = -2147418113;
                      v34 = -2147418113;
                    }
                  }
                  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                  {
                    WPP_SF_SD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      38,
                      (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
                      (unsigned int)L"IsCallFromAuthorizedLicenseServer",
                      v25);
                  }
                  SidToCheck = 0;
                  if ( v26 >= 0 )
                  {
                    v27 = Sid;
                    v28 = TLSGetInfoForDiscoveredLicenseServer(Sid, v37, &SidToCheck, 0);
                    v34 = v28;
                    if ( v28 >= 0 )
                    {
                      v31 = CheckRpcCallerTokenMembership(Binding, SidToCheck, &v33);
                      v34 = v31;
                      if ( v31 < 0
                        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                      {
                        WPP_SF_SD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          41,
                          (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
                          (unsigned int)L"IsCallFromAuthorizedLicenseServer",
                          v31);
                      }
                      v1 = v33;
                    }
                    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                    {
                      WPP_SF_SSdD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, v29, v30, (__int64)v27, v27[130], v28);
                    }
                  }
                  v0 = 0;
                  v34 = 0;
                  ATL::CHeapPtr<void,ATL::CLocalAllocator>::~CHeapPtr<void,ATL::CLocalAllocator>(&SidToCheck);
                }
              }
              CLSDiscovery::~CLSDiscovery((CLSDiscovery *)v50);
            }
            catch ( ... )
            {
              v34 = -2147418113;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  42,
                  &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
                  L"IsCallFromAuthorizedLicenseServer");
              v0 = v34;
              v1 = v33;
              v19 = v43;
              v20 = v42;
              continue;
            }
          }
          operator delete[](v20);
          v42 = 0;
          operator delete[](v19);
          v43 = 0;
        }
        return v1;
      }
      Sid = 0;
      WorkgroupLicenseServerAccountsGroupSid = GetWorkgroupLicenseServerAccountsGroupSid(&Sid);
      if ( WorkgroupLicenseServerAccountsGroupSid < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
            (unsigned int)L"IsCallFromAuthorizedLicenseServer",
            WorkgroupLicenseServerAccountsGroupSid);
LABEL_52:
        v0 = 0;
        operator delete[](Sid);
        Sid = 0;
        v12 = v36;
        goto LABEL_53;
      }
      v14 = CheckRpcCallerTokenMembership(Binding, Sid, &v33);
      if ( v14 < 0 )
      {
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
        {
LABEL_48:
          v1 = v33;
          if ( v33 && v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x1000) != 0 )
            WPP_SF_SH((unsigned int)v18[2], v15, v16, v17, v49);
          goto LABEL_52;
        }
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
          (unsigned int)L"IsCallFromAuthorizedLicenseServer",
          v14);
      }
      v18 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_48;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000a50c  mov     [rsp+arg_0], rbx
0x18000a511  mov     [rsp+arg_8], rdi
0x18000a516  mov     [rsp+arg_10], r12
0x18000a51b  push    r13
0x18000a51d  push    r14
0x18000a51f  push    r15
0x18000a521  sub     rsp, 1E0h
0x18000a528  mov     rax, cs:__security_cookie
0x18000a52f  xor     rax, rsp
0x18000a532  mov     [rsp+1F8h+var_28], rax
0x18000a53a  xor     r14d, r14d
0x18000a53d  xor     r15d, r15d
0x18000a540  mov     [rsp+1F8h+var_1B8], r15d
0x18000a545  and     [rsp+1F8h+Binding], r14
0x18000a54a  lea     rcx, [rsp+1F8h+Binding]; Binding
0x18000a54f  call    cs:__imp_RpcServerInqBindingHandle
0x18000a556  nop     dword ptr [rax+rax+00h]
0x18000a55b  cmp     eax, 6BDh
0x18000a560  jnz     loc_18000A621
0x18000a566  lea     r15d, [r14+1]
0x18000a56a  mov     [rsp+1F8h+var_1B8], r15d
0x18000a56f  mov     r12d, 1000h
0x18000a575  lea     r13, WPP_GLOBAL_Control
0x18000a57c  xor     edx, edx; Val
0x18000a57e  lea     r8d, [rdx+70h]; Size
0x18000a582  lea     rcx, [rsp+1F8h+RpcCallAttributes]; void *
0x18000a58a  call    memset_0
0x18000a58f  test    r14d, r14d
0x18000a592  js      loc_18000A796
0x18000a598  test    r15d, r15d
0x18000a59b  jnz     loc_18000A796
0x18000a5a1  mov     [rsp+1F8h+RpcCallAttributes], 2
0x18000a5ac  mov     [rsp+1F8h+var_134], 20h ; ' '
0x18000a5b7  lea     rdx, [rsp+1F8h+RpcCallAttributes]; RpcCallAttributes
0x18000a5bf  mov     rcx, [rsp+1F8h+Binding]; ClientBinding
0x18000a5c4  call    cs:__imp_RpcServerInqCallAttributesW
0x18000a5cb  nop     dword ptr [rax+rax+00h]
0x18000a5d0  test    eax, eax
0x18000a5d2  jz      loc_18000A680
0x18000a5d8  mov     ebx, eax
0x18000a5da  or      ebx, 80010000h
0x18000a5e0  mov     r14d, ebx
0x18000a5e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5ea  cmp     rcx, r13
0x18000a5ed  jz      loc_18000A796
0x18000a5f3  test    [rcx+1Ch], r12d
0x18000a5f7  jz      loc_18000A796
0x18000a5fd  lea     edx, [r15+1Ch]
0x18000a601  mov     dword ptr [rsp+1F8h+var_1D8], eax
0x18000a605  lea     r9, aIscallfromauth; "IsCallFromAuthorizedLicenseServer"
0x18000a60c  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000a613  mov     rcx, [rcx+10h]
0x18000a617  call    WPP_SF_SD
0x18000a61c  jmp     loc_18000A796
0x18000a621  test    eax, eax
0x18000a623  jz      loc_18000A56F
0x18000a629  mov     ebx, eax
0x18000a62b  or      ebx, 80010000h
0x18000a631  mov     r14d, ebx
0x18000a634  lea     r13, WPP_GLOBAL_Control
0x18000a63b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a642  mov     r12d, 1000h
0x18000a648  cmp     rcx, r13
0x18000a64b  jz      loc_18000A57C
0x18000a651  test    [rcx+1Ch], r12d
0x18000a655  jz      loc_18000A57C
0x18000a65b  mov     edx, 1Bh
0x18000a660  mov     dword ptr [rsp+1F8h+var_1D8], eax
0x18000a664  lea     r9, aIscallfromauth; "IsCallFromAuthorizedLicenseServer"
0x18000a66b  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000a672  mov     rcx, [rcx+10h]
0x18000a676  call    WPP_SF_SD
0x18000a67b  jmp     loc_18000A57C
0x18000a680  cmp     [rsp+1F8h+var_FC], 1
0x18000a688  jnz     loc_18000A796
0x18000a68e  and     [rsp+1F8h+Sid], 0
0x18000a694  lea     rdx, [rsp+1F8h+Sid]; Sid
0x18000a699  lea     rbx, StringSid; "S-1-5-80-3893474178-2562712516-32439918"...
0x18000a6a0  mov     rcx, rbx; StringSid
0x18000a6a3  call    cs:__imp_ConvertStringSidToSidW
0x18000a6aa  nop     dword ptr [rax+rax+00h]
0x18000a6af  test    eax, eax
0x18000a6b1  jnz     short loc_18000A6F9
0x18000a6b3  call    ?HResultFromLastError@@YAJXZ; HResultFromLastError(void)
0x18000a6b8  mov     r14d, eax
0x18000a6bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6c2  cmp     rcx, r13
0x18000a6c5  jz      short loc_18000A6F4
0x18000a6c7  test    [rcx+1Ch], r12d
0x18000a6cb  jz      short loc_18000A6F4
0x18000a6cd  mov     edx, 1Dh
0x18000a6d2  mov     dword ptr [rsp+1F8h+var_1D8], eax
0x18000a6d6  lea     r9, aIscallfromauth; "IsCallFromAuthorizedLicenseServer"
0x18000a6dd  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000a6e4  mov     rcx, [rcx+10h]
0x18000a6e8  call    WPP_SF_SD
0x18000a6ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6f4  test    r14d, r14d
0x18000a6f7  js      short loc_18000A750
0x18000a6f9  lea     r8, [rsp+1F8h+var_1B8]; int *
0x18000a6fe  mov     rdx, [rsp+1F8h+Sid]; SidToCheck
0x18000a703  mov     rcx, [rsp+1F8h+Binding]; BindingHandle
0x18000a708  call    ?CheckRpcCallerTokenMembership@@YAJPEAX0PEAH@Z; CheckRpcCallerTokenMembership(void *,void *,int *)
0x18000a70d  mov     r14d, eax
0x18000a710  test    eax, eax
0x18000a712  jns     short loc_18000A744
0x18000a714  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a71b  cmp     rcx, r13
0x18000a71e  jz      short loc_18000A74B
0x18000a720  test    [rcx+1Ch], r12d
0x18000a724  jz      short loc_18000A74B
0x18000a726  mov     edx, 1Eh
0x18000a72b  mov     [rsp+1F8h+var_1D0], eax
0x18000a72f  mov     [rsp+1F8h+var_1D8], rbx
0x18000a734  lea     r9, aIscallfromauth; "IsCallFromAuthorizedLicenseServer"
0x18000a73b  mov     rcx, [rcx+10h]
0x18000a73f  call    WPP_SF_SSD
0x18000a744  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a74b  mov     r15d, [rsp+1F8h+var_1B8]
0x18000a750  cmp     [rsp+1F8h+Sid], 0
0x18000a756  jz      short loc_18000A770
0x18000a758  mov     rcx, [rsp+1F8h+Sid]; hMem
0x18000a75d  call    cs:__imp_LocalFree
0x18000a764  nop     dword ptr [rax+rax+00h]
0x18000a769  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a770  test    r15d, r15d
0x18000a773  jz      short loc_18000A796
0x18000a775  cmp     rcx, r13
0x18000a778  jz      short loc_18000A796
0x18000a77a  test    [rcx+1Ch], r12d
0x18000a77e  jz      short loc_18000A796
0x18000a780  movzx   eax, [rsp+1F8h+var_E0]
0x18000a788  mov     word ptr [rsp+1F8h+var_1D8], ax
0x18000a78d  mov     rcx, [rcx+10h]
0x18000a791  call    WPP_SF_SHS
0x18000a796  xor     eax, eax
0x18000a798  mov     [rsp+1F8h+var_1A8], eax
0x18000a79c  test    r14d, r14d
0x18000a79f  js      loc_18000ACBC
0x18000a7a5  test    r15d, r15d
0x18000a7a8  jnz     loc_18000ACBC
0x18000a7ae  xor     edx, edx
0x18000a7b0  lea     rcx, [rsp+1F8h+var_1A8]
0x18000a7b5  call    cs:__imp_TLSInDomain
0x18000a7bc  nop     dword ptr [rax+rax+00h]
0x18000a7c1  mov     ebx, eax
0x18000a7c3  test    eax, eax
0x18000a7c5  jz      short loc_18000A80B
0x18000a7c7  mov     ecx, eax; unsigned int
0x18000a7c9  call    ?HResultFromWin32Error@@YAJK@Z; HResultFromWin32Error(ulong)
0x18000a7ce  mov     r14d, eax
0x18000a7d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7d8  cmp     rcx, r13
0x18000a7db  jz      short loc_18000A802
0x18000a7dd  test    [rcx+1Ch], r12d
0x18000a7e1  jz      short loc_18000A802
0x18000a7e3  lea     edx, [r15+20h]
0x18000a7e7  mov     dword ptr [rsp+1F8h+var_1D8], ebx
0x18000a7eb  lea     r9, aIscallfromauth; "IsCallFromAuthorizedLicenseServer"
0x18000a7f2  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000a7f9  mov     rcx, [rcx+10h]
0x18000a7fd  call    WPP_SF_SD
0x18000a802  test    r14d, r14d
0x18000a805  js      loc_18000ACBC
0x18000a80b  mov     eax, [rsp+1F8h+var_1A8]
0x18000a80f  test    r15d, r15d
0x18000a812  jnz     loc_18000ACBC
0x18000a818  test    eax, eax
0x18000a81a  jnz     loc_18000A908
0x18000a820  and     [rsp+1F8h+Sid], 0
0x18000a826  lea     rcx, [rsp+1F8h+Sid]; void **
0x18000a82b  call    ?GetWorkgroupLicenseServerAccountsGroupSid@@YAJPEAPEAX@Z; GetWorkgroupLicenseServerAccountsGroupSid(void * *)
0x18000a830  test    eax, eax
0x18000a832  jns     short loc_18000A86F
0x18000a834  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a83b  cmp     rcx, r13
0x18000a83e  jz      loc_18000A8EB
0x18000a844  test    [rcx+1Ch], r12d
0x18000a848  jz      loc_18000A8EB
0x18000a84e  lea     edx, [r15+21h]
0x18000a852  mov     dword ptr [rsp+1F8h+var_1D8], eax
0x18000a856  lea     r9, aIscallfromauth; "IsCallFromAuthorizedLicenseServer"
0x18000a85d  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000a864  mov     rcx, [rcx+10h]
0x18000a868  call    WPP_SF_SD
0x18000a86d  jmp     short loc_18000A8EB
0x18000a86f  lea     r8, [rsp+1F8h+var_1B8]; int *
0x18000a874  mov     rdx, [rsp+1F8h+Sid]; SidToCheck
0x18000a879  mov     rcx, [rsp+1F8h+Binding]; BindingHandle
0x18000a87e  call    ?CheckRpcCallerTokenMembership@@YAJPEAX0PEAH@Z; CheckRpcCallerTokenMembership(void *,void *,int *)
0x18000a883  test    eax, eax
0x18000a885  jns     short loc_18000A8B9
0x18000a887  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a88e  cmp     rcx, r13
0x18000a891  jz      short loc_18000A8C0
0x18000a893  test    [rcx+1Ch], r12d
0x18000a897  jz      short loc_18000A8C0
0x18000a899  mov     edx, 22h ; '"'
0x18000a89e  mov     dword ptr [rsp+1F8h+var_1D8], eax
0x18000a8a2  lea     r9, aIscallfromauth; "IsCallFromAuthorizedLicenseServer"
0x18000a8a9  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000a8b0  mov     rcx, [rcx+10h]
0x18000a8b4  call    WPP_SF_SD
0x18000a8b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8c0  mov     r15d, [rsp+1F8h+var_1B8]
0x18000a8c5  test    r15d, r15d
0x18000a8c8  jz      short loc_18000A8EB
0x18000a8ca  cmp     rcx, r13
0x18000a8cd  jz      short loc_18000A8EB
0x18000a8cf  test    [rcx+1Ch], r12d
0x18000a8d3  jz      short loc_18000A8EB
0x18000a8d5  movzx   eax, [rsp+1F8h+var_E0]
0x18000a8dd  mov     word ptr [rsp+1F8h+var_1D8], ax
0x18000a8e2  mov     rcx, [rcx+10h]
0x18000a8e6  call    WPP_SF_SH
0x18000a8eb  xor     r14d, r14d
0x18000a8ee  mov     rcx, [rsp+1F8h+Sid]
0x18000a8f3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000a8fa  nop     dword ptr [rax+rax+00h]
0x18000a8ff  and     [rsp+1F8h+Sid], r14
0x18000a904  mov     eax, [rsp+1F8h+var_1A8]
0x18000a908  test    r15d, r15d
0x18000a90b  jnz     loc_18000ACBC
0x18000a911  test    eax, eax
0x18000a913  jz      loc_18000ACBC
0x18000a919  xor     ebx, ebx
0x18000a91b  mov     [rsp+1F8h+var_178], rbx
0x18000a923  xor     edi, edi
0x18000a925  mov     [rsp+1F8h+var_180], rdi
0x18000a92a  xor     eax, eax
0x18000a92c  mov     [rsp+1F8h+var_188], rax
0x18000a931  test    r14d, r14d
0x18000a934  js      loc_18000AC8F
0x18000a93a  test    r15d, r15d
0x18000a93d  jnz     loc_18000AC8F
0x18000a943  cmp     rax, 2
0x18000a947  jnb     loc_18000AC8F
0x18000a94d  lea     rax, [rax+rax*2]
0x18000a951  lea     rcx, qword_1800E6720
0x18000a958  lea     rdx, [rcx+rax*4]
0x18000a95c  lea     rcx, [rsp+1F8h+var_160]
0x18000a964  call    cs:__imp_??0CLSDiscoveryPolicy@@QEAA@PEAW4LS_DISC_MECH_ENUM@@@Z; CLSDiscoveryPolicy::CLSDiscoveryPolicy(LS_DISC_MECH_ENUM *)
0x18000a96b  nop     dword ptr [rax+rax+00h]
0x18000a970  mov     [rsp+1F8h+var_140], 1E8h
0x18000a97b  lea     rdx, [rsp+1F8h+var_160]
0x18000a983  lea     rcx, [rsp+1F8h+var_C8]
0x18000a98b  call    cs:__imp_??0CLSDiscovery@@QEAA@PEBVCLSDiscoveryPolicy@@@Z; CLSDiscovery::CLSDiscovery(CLSDiscoveryPolicy const *)
0x18000a992  nop     dword ptr [rax+rax+00h]
0x18000a997  nop
0x18000a998  lea     rcx, [rsp+1F8h+var_C8]
0x18000a9a0  call    cs:__imp_?Refresh@CLSDiscovery@@QEAAKXZ; CLSDiscovery::Refresh(void)
0x18000a9a7  nop     dword ptr [rax+rax+00h]
0x18000a9ac  mov     dword ptr [rsp+1F8h+Sid], eax
0x18000a9b0  test    eax, eax
0x18000a9b2  jz      short loc_18000A9F7
0x18000a9b4  mov     ecx, eax; unsigned int
0x18000a9b6  call    ?HResultFromWin32Error@@YAJK@Z; HResultFromWin32Error(ulong)
0x18000a9bb  mov     r14d, eax
0x18000a9be  mov     [rsp+1F8h+var_1B4], eax
0x18000a9c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9c9  cmp     rcx, r13
0x18000a9cc  jz      short loc_18000A9F7
0x18000a9ce  test    [rcx+1Ch], r12d
0x18000a9d2  jz      short loc_18000A9F7
0x18000a9d4  lea     edx, [r15+24h]
0x18000a9d8  mov     eax, dword ptr [rsp+1F8h+Sid]
0x18000a9dc  mov     dword ptr [rsp+1F8h+var_1D8], eax
0x18000a9e0  lea     r9, aIscallfromauth; "IsCallFromAuthorizedLicenseServer"
0x18000a9e7  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000a9ee  mov     rcx, [rcx+10h]
0x18000a9f2  call    WPP_SF_SD
0x18000a9f7  and     [rsp+1F8h+var_198], 0
0x18000a9fd  test    r14d, r14d
0x18000aa00  js      loc_18000AC47
0x18000aa06  lea     rdx, [rsp+1F8h+var_170]
0x18000aa0e  lea     rcx, [rsp+1F8h+var_C8]
0x18000aa16  call    cs:__imp_?Begin@CLSDiscovery@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVCDiscoveredLS@@@std@@@std@@@std@@XZ; CLSDiscovery::Begin(void)
0x18000aa1d  nop     dword ptr [rax+rax+00h]
0x18000aa22  mov     rcx, [rax]
0x18000aa25  mov     [rsp+1F8h+var_198], rcx
0x18000aa2a  test    r14d, r14d
0x18000aa2d  js      loc_18000AC47
0x18000aa33  test    r15d, r15d
0x18000aa36  jnz     loc_18000AC47
0x18000aa3c  lea     rdx, [rsp+1F8h+var_168]
0x18000aa44  lea     rcx, [rsp+1F8h+var_C8]
0x18000aa4c  call    cs:__imp_?End@CLSDiscovery@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVCDiscoveredLS@@@std@@@std@@@std@@XZ; CLSDiscovery::End(void)
0x18000aa53  nop     dword ptr [rax+rax+00h]
0x18000aa58  mov     rcx, [rsp+1F8h+var_198]
0x18000aa5d  cmp     [rax], rcx
0x18000aa60  jz      loc_18000AC47
0x18000aa66  lea     rdx, [rsp+1F8h+var_198]
0x18000aa6b  lea     rcx, [rsp+1F8h+var_C8]
0x18000aa73  call    cs:__imp_?Next@CLSDiscovery@@QEAAPEAVCDiscoveredLS@@AEAV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVCDiscoveredLS@@@std@@@std@@@std@@@Z; CLSDiscovery::Next(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<CDiscoveredLS *>>> &)
0x18000aa7a  nop     dword ptr [rax+rax+00h]
0x18000aa7f  mov     r14, rax
0x18000aa82  mov     [rsp+1F8h+Sid], rax
0x18000aa87  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa8e  cmp     rcx, r13
0x18000aa91  jz      short loc_18000AAC5
  ... truncated ...
```
