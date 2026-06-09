# DimStopRoutingDomain(_GUID *,int)

- ea: `0x180014fcc`
- end: `0x18001547e`
- name: `?DimStopRoutingDomain@@YAKPEAU_GUID@@H@Z`
- size: `1202`
- prototype: `__int64 __fastcall(struct _GUID *, int)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000e270`
- `0x180014b44`
- `0x180016b80`

## callees

- `0x180002598`
- `0x180008250`
- `0x18000ad04`
- `0x18000da10`
- `0x18000df70`
- `0x180014fcc`
- `0x1800161b8`
- `0x180016884`
- `0x180027454`
- `0x18002f5d4`
- `0x180036730`
- `0x18003748c`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800150c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800150c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001503d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001503d`

## string_xrefs

- `0x18001517e`: `DimStopRoutingDomain: PlumbRDIkev2Policy failed to remove IKEv2 policies: %d.`
- `0x1800151f9`: `DimStopRoutingDomain: IfObjectPlumbIkev2PskPolicy failed to remove IKEv2 PSK policies: %d.`
- `0x18001528d`: `DimStopRoutingDomain: NotifyDDMForRoutingDomainChange (RD delete) failed: %d.`
- `0x18001530c`: `DimStopRoutingDomain: RouterManager:RemoveRoutingDomain (ipv4) failed: %d.`
- `0x18001537e`: `DimStopRoutingDomain: RouterManager:RemoveRoutingDomain (ipv6) failed: %d.`

## pseudocode

```c
__int64 __fastcall DimStopRoutingDomain(struct _GUID *a1, int a2)
{
  unsigned int v4; // eax
  __int128 *v5; // r9
  unsigned int v6; // eax
  CDimInterfaceTable *v7; // rcx
  unsigned int v8; // edi
  __int128 *v9; // r9
  unsigned int v10; // eax
  __int128 *v11; // r9
  unsigned int v12; // eax
  __int128 *v13; // r9
  unsigned int v14; // eax
  __int128 *v15; // r9
  unsigned int v16; // eax
  CDimRouterManager *v17; // rcx
  __int128 *v18; // r9
  unsigned int v19; // eax
  __int128 *v20; // r9
  __int128 *v21; // r9
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v24; // [rsp+38h] [rbp-C8h] BYREF
  int v25; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v26; // [rsp+4Ch] [rbp-B4h]
  __int128 v27; // [rsp+5Ch] [rbp-A4h]
  int v28; // [rsp+6Ch] [rbp-94h]
  int v29; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v23 = 1;
  v29 = 0;
  memset_0(v30, 0, sizeof(v30));
  v25 = 0;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  v24 = 0;
  LeaveCriticalSection(&CriticalSection);
  v4 = RegisterInterfaceChangeNotifications(a1, 0);
  if ( v4 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v29) = 0;
      LOWORD(v25) = 0;
      FormatRRASErrorString(
        &v29,
        L"DimStopRoutingDomain: RegisterInterfaceChangeNotifications failed with error %d",
        v4);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        v5 = &v24;
        if ( a1 )
          LODWORD(v5) = (_DWORD)a1;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceError,
          (unsigned int)&v29,
          (_DWORD)v5,
          0,
          (__int64)&v25);
      }
    }
  }
  EnterCriticalSection(&CriticalSection);
  v6 = IsRoutingDomainAvailable(a1, &v23);
  v8 = v6;
  if ( v6 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v29) = 0;
      LOWORD(v25) = 0;
      FormatRRASErrorString(
        &v29,
        L"DimStopRoutingDomain: RegisterInterfaceChangeNotifications failed with error %d",
        v6);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        v9 = &v24;
        if ( a1 )
          LODWORD(v9) = (_DWORD)a1;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceError,
          (unsigned int)&v29,
          (_DWORD)v9,
          0,
          (__int64)&v25);
      }
    }
  }
  if ( v23 )
  {
    if ( (gbldwDIMComponentsLoaded & 4) != 0 )
    {
      v10 = CDimInterfaceTable::PlumbRDIkev2Policy(g_pCDimInterfaceTable, a1, 1);
      if ( v10 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          LOWORD(v29) = 0;
          LOWORD(v25) = 0;
          FormatRRASErrorString(
            &v29,
            L"DimStopRoutingDomain: PlumbRDIkev2Policy failed to remove IKEv2 policies: %d.",
            v10);
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            v11 = &v24;
            if ( a1 )
              LODWORD(v11) = (_DWORD)a1;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceError,
              (unsigned int)&v29,
              (_DWORD)v11,
              0,
              (__int64)&v25);
          }
        }
      }
      v12 = CDimInterfaceTable::PlumbIkev2PskPolicy(g_pCDimInterfaceTable, a1, 1);
      if ( v12 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          LOWORD(v29) = 0;
          LOWORD(v25) = 0;
          FormatRRASErrorString(
            &v29,
            L"DimStopRoutingDomain: IfObjectPlumbIkev2PskPolicy failed to remove IKEv2 PSK policies: %d.",
            v12);
          if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          {
            v13 = &v24;
            if ( a1 )
              LODWORD(v13) = (_DWORD)a1;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceError,
              (unsigned int)&v29,
              (_DWORD)v13,
              0,
              (__int64)&v25);
          }
        }
      }
    }
    if ( a2 )
      CDimInterfaceTable::DisableDisconnectS2SInterfacesInRd(v7, a1);
    if ( (gbldwDIMComponentsLoaded & 4) != 0 )
    {
      v14 = NotifyDDMForRoutingDomainChange(a1, 2u, 0);
      if ( v14 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
        {
          LOWORD(v29) = 0;
          LOWORD(v25) = 0;
          FormatRRASErrorString(
            &v29,
            L"DimStopRoutingDomain: NotifyDDMForRoutingDomainChange (RD delete) failed: %d.",
            v14);
          if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
          {
            v15 = &v24;
            if ( a1 )
              LODWORD(v15) = (_DWORD)a1;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceAdminError,
              (unsigned int)&v29,
              (_DWORD)v15,
              0,
              (__int64)&v25);
          }
        }
      }
    }
    if ( (gbldwDIMComponentsLoaded & 2) != 0 )
    {
      v16 = CDimRouterManager::RemoveRoutingDomain(v7, 0x21u, a1);
      if ( v16 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
        {
          LOWORD(v29) = 0;
          LOWORD(v25) = 0;
          FormatRRASErrorString(
            &v29,
            L"DimStopRoutingDomain: RouterManager:RemoveRoutingDomain (ipv4) failed: %d.",
            v16);
          if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
          {
            v18 = &v24;
            if ( a1 )
              LODWORD(v18) = (_DWORD)a1;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceAdminError,
              (unsigned int)&v29,
              (_DWORD)v18,
              0,
              (__int64)&v25);
          }
        }
      }
      v19 = CDimRouterManager::RemoveRoutingDomain(v17, 0x57u, a1);
      if ( v19 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
        {
          LOWORD(v29) = 0;
          LOWORD(v25) = 0;
          FormatRRASErrorString(
            &v29,
            L"DimStopRoutingDomain: RouterManager:RemoveRoutingDomain (ipv6) failed: %d.",
            v19);
          if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
          {
            v20 = &v24;
            if ( a1 )
              LODWORD(v20) = (_DWORD)a1;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceAdminError,
              (unsigned int)&v29,
              (_DWORD)v20,
              0,
              (__int64)&v25);
          }
        }
      }
    }
    if ( a2 )
      CDimInterfaceTable::RemoveInterfaces(v7, a1);
    v8 = ReferenceOrDereferenceRoutingDomain(a1, 0);
    if ( v8 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v29) = 0;
        LOWORD(v25) = 0;
        FormatRRASErrorString(
          &v29,
          L"DimStopRoutingDomain: ReferenceOrDereferenceRoutingDomain failed with error %d.",
          v8);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        {
          v21 = &v24;
          if ( a1 )
            LODWORD(v21) = (_DWORD)a1;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceError,
            (unsigned int)&v29,
            (_DWORD)v21,
            0,
            (__int64)&v25);
        }
      }
    }
    MarkRoutingDomainAsUnAvailable(a1);
  }
  return v8;
}

```

## disassembly

```asm
0x180014fcc  push    rbp
0x180014fce  push    rbx
0x180014fcf  push    rsi
0x180014fd0  push    rdi
0x180014fd1  push    r13
0x180014fd3  push    r15
0x180014fd5  lea     rbp, [rsp-788h]
0x180014fdd  sub     rsp, 888h
0x180014fe4  mov     rax, cs:__security_cookie
0x180014feb  xor     rax, rsp
0x180014fee  mov     [rbp+7B0h+var_40], rax
0x180014ff5  mov     esi, edx
0x180014ff7  mov     [rsp+8B0h+var_880], 1
0x180014fff  mov     rbx, rcx
0x180015002  xor     eax, eax
0x180015004  xor     edx, edx; Val
0x180015006  mov     [rsp+8B0h+var_840], eax
0x18001500a  lea     rcx, [rsp+8B0h+var_83C]; void *
0x18001500f  mov     r8d, 7FCh; Size
0x180015015  call    memset_0
0x18001501a  xorps   xmm0, xmm0
0x18001501d  lea     rcx, CriticalSection; lpCriticalSection
0x180015024  xor     eax, eax
0x180015026  mov     [rsp+8B0h+var_868], eax
0x18001502a  movups  [rsp+8B0h+var_864], xmm0
0x18001502f  mov     [rsp+8B0h+var_844], eax
0x180015033  movups  [rsp+8B0h+var_854], xmm0
0x180015038  movups  [rsp+8B0h+var_878], xmm0
0x18001503d  call    cs:__imp_LeaveCriticalSection
0x180015043  xor     edx, edx; int
0x180015045  mov     rcx, rbx; struct _GUID *
0x180015048  call    ?RegisterInterfaceChangeNotifications@@YAKPEAU_GUID@@H@Z; RegisterInterfaceChangeNotifications(_GUID *,int)
0x18001504d  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015054  mov     r15b, 4
0x180015057  test    eax, eax
0x180015059  jz      short loc_1800150C0
0x18001505b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180015062  jz      short loc_1800150C0
0x180015064  xor     ecx, ecx
0x180015066  lea     rdx, aDimstoprouting_1; "DimStopRoutingDomain: RegisterInterface"...
0x18001506d  mov     word ptr [rsp+8B0h+var_840], cx
0x180015072  mov     r8d, eax
0x180015075  mov     word ptr [rsp+8B0h+var_868], cx
0x18001507a  lea     rcx, [rsp+8B0h+var_840]
0x18001507f  call    FormatRRASErrorString
0x180015084  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001508b  jz      short loc_1800150C0
0x18001508d  test    rbx, rbx
0x180015090  lea     rax, [rsp+8B0h+var_868]
0x180015095  mov     [rsp+8B0h+var_888], rax
0x18001509a  lea     r9, [rsp+8B0h+var_878]
0x18001509f  cmovnz  r9, rbx
0x1800150a3  mov     [rsp+8B0h+var_890], 0
0x1800150ac  lea     r8, [rsp+8B0h+var_840]
0x1800150b1  mov     rcx, r13
0x1800150b4  lea     rdx, RasDimParamTraceError
0x1800150bb  call    McTemplateU0zjzz_EventWriteTransfer
0x1800150c0  lea     rcx, CriticalSection; lpCriticalSection
0x1800150c7  call    cs:__imp_EnterCriticalSection
0x1800150cd  lea     rdx, [rsp+8B0h+var_880]; int *
0x1800150d2  mov     rcx, rbx; struct _GUID *
0x1800150d5  call    ?IsRoutingDomainAvailable@@YAKPEAU_GUID@@PEAH@Z; IsRoutingDomainAvailable(_GUID *,int *)
0x1800150da  mov     edi, eax
0x1800150dc  test    eax, eax
0x1800150de  jz      short loc_180015145
0x1800150e0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800150e7  jz      short loc_180015145
0x1800150e9  xor     ecx, ecx
0x1800150eb  lea     rdx, aDimstoprouting_1; "DimStopRoutingDomain: RegisterInterface"...
0x1800150f2  mov     word ptr [rsp+8B0h+var_840], cx
0x1800150f7  mov     r8d, eax
0x1800150fa  mov     word ptr [rsp+8B0h+var_868], cx
0x1800150ff  lea     rcx, [rsp+8B0h+var_840]
0x180015104  call    FormatRRASErrorString
0x180015109  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180015110  jz      short loc_180015145
0x180015112  test    rbx, rbx
0x180015115  lea     rax, [rsp+8B0h+var_868]
0x18001511a  mov     [rsp+8B0h+var_888], rax
0x18001511f  lea     r9, [rsp+8B0h+var_878]
0x180015124  cmovnz  r9, rbx
0x180015128  mov     [rsp+8B0h+var_890], 0
0x180015131  lea     r8, [rsp+8B0h+var_840]
0x180015136  mov     rcx, r13
0x180015139  lea     rdx, RasDimParamTraceError
0x180015140  call    McTemplateU0zjzz_EventWriteTransfer
0x180015145  cmp     [rsp+8B0h+var_880], 0
0x18001514a  jz      loc_18001545D
0x180015150  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, r15b; ulong gbldwDIMComponentsLoaded
0x180015157  jz      loc_180015253
0x18001515d  mov     rcx, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; this
0x180015164  mov     r8b, 1; bool
0x180015167  mov     rdx, rbx; struct _GUID *
0x18001516a  call    ?PlumbRDIkev2Policy@CDimInterfaceTable@@QEAAKPEAU_GUID@@_N@Z; CDimInterfaceTable::PlumbRDIkev2Policy(_GUID *,bool)
0x18001516f  test    eax, eax
0x180015171  jz      short loc_1800151D8
0x180015173  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001517a  jz      short loc_1800151D8
0x18001517c  xor     ecx, ecx
0x18001517e  lea     rdx, aDimstoprouting_5; "DimStopRoutingDomain: PlumbRDIkev2Polic"...
0x180015185  mov     word ptr [rsp+8B0h+var_840], cx
0x18001518a  mov     r8d, eax
0x18001518d  mov     word ptr [rsp+8B0h+var_868], cx
0x180015192  lea     rcx, [rsp+8B0h+var_840]
0x180015197  call    FormatRRASErrorString
0x18001519c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800151a3  jz      short loc_1800151D8
0x1800151a5  test    rbx, rbx
0x1800151a8  lea     rax, [rsp+8B0h+var_868]
0x1800151ad  mov     [rsp+8B0h+var_888], rax
0x1800151b2  lea     r9, [rsp+8B0h+var_878]
0x1800151b7  cmovnz  r9, rbx
0x1800151bb  mov     [rsp+8B0h+var_890], 0
0x1800151c4  lea     r8, [rsp+8B0h+var_840]
0x1800151c9  mov     rcx, r13
0x1800151cc  lea     rdx, RasDimParamTraceError
0x1800151d3  call    McTemplateU0zjzz_EventWriteTransfer
0x1800151d8  mov     rcx, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; this
0x1800151df  mov     r8b, 1; bool
0x1800151e2  mov     rdx, rbx; struct _GUID *
0x1800151e5  call    ?PlumbIkev2PskPolicy@CDimInterfaceTable@@QEAAKAEBU_GUID@@_N@Z; CDimInterfaceTable::PlumbIkev2PskPolicy(_GUID const &,bool)
0x1800151ea  test    eax, eax
0x1800151ec  jz      short loc_180015253
0x1800151ee  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800151f5  jz      short loc_180015253
0x1800151f7  xor     ecx, ecx
0x1800151f9  lea     rdx, aDimstoprouting_0; "DimStopRoutingDomain: IfObjectPlumbIkev"...
0x180015200  mov     word ptr [rsp+8B0h+var_840], cx
0x180015205  mov     r8d, eax
0x180015208  mov     word ptr [rsp+8B0h+var_868], cx
0x18001520d  lea     rcx, [rsp+8B0h+var_840]
0x180015212  call    FormatRRASErrorString
0x180015217  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001521e  jz      short loc_180015253
0x180015220  test    rbx, rbx
0x180015223  lea     rax, [rsp+8B0h+var_868]
0x180015228  mov     [rsp+8B0h+var_888], rax
0x18001522d  lea     r9, [rsp+8B0h+var_878]
0x180015232  cmovnz  r9, rbx
0x180015236  mov     [rsp+8B0h+var_890], 0
0x18001523f  lea     r8, [rsp+8B0h+var_840]
0x180015244  mov     rcx, r13
0x180015247  lea     rdx, RasDimParamTraceError
0x18001524e  call    McTemplateU0zjzz_EventWriteTransfer
0x180015253  test    esi, esi
0x180015255  jz      short loc_18001525F
0x180015257  mov     rdx, rbx; struct _GUID *
0x18001525a  call    ?DisableDisconnectS2SInterfacesInRd@CDimInterfaceTable@@QEAAXPEAU_GUID@@@Z; CDimInterfaceTable::DisableDisconnectS2SInterfacesInRd(_GUID *)
0x18001525f  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, r15b; ulong gbldwDIMComponentsLoaded
0x180015266  lea     rdi, RasDimParamTraceAdminError
0x18001526d  jz      short loc_1800152E3
0x18001526f  xor     r8d, r8d; void *
0x180015272  mov     rcx, rbx; struct _GUID *
0x180015275  lea     edx, [r8+2]; unsigned int
0x180015279  call    ?NotifyDDMForRoutingDomainChange@@YAKPEAU_GUID@@KPEAX@Z; NotifyDDMForRoutingDomainChange(_GUID *,ulong,void *)
0x18001527e  test    eax, eax
0x180015280  jz      short loc_1800152E3
0x180015282  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x180015289  jz      short loc_1800152E3
0x18001528b  xor     ecx, ecx
0x18001528d  lea     rdx, aDimstoprouting_3; "DimStopRoutingDomain: NotifyDDMForRouti"...
0x180015294  mov     word ptr [rsp+8B0h+var_840], cx
0x180015299  mov     r8d, eax
0x18001529c  mov     word ptr [rsp+8B0h+var_868], cx
0x1800152a1  lea     rcx, [rsp+8B0h+var_840]
0x1800152a6  call    FormatRRASErrorString
0x1800152ab  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x1800152b2  jz      short loc_1800152E3
0x1800152b4  test    rbx, rbx
0x1800152b7  lea     rax, [rsp+8B0h+var_868]
0x1800152bc  mov     [rsp+8B0h+var_888], rax
0x1800152c1  lea     r9, [rsp+8B0h+var_878]
0x1800152c6  cmovnz  r9, rbx
0x1800152ca  mov     [rsp+8B0h+var_890], 0
0x1800152d3  lea     r8, [rsp+8B0h+var_840]
0x1800152d8  mov     rdx, rdi
0x1800152db  mov     rcx, r13
0x1800152de  call    McTemplateU0zjzz_EventWriteTransfer
0x1800152e3  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 2; ulong gbldwDIMComponentsLoaded
0x1800152ea  jz      loc_1800153D4
0x1800152f0  mov     r8, rbx; struct _GUID *
0x1800152f3  mov     edx, 21h ; '!'; unsigned int
0x1800152f8  call    ?RemoveRoutingDomain@CDimRouterManager@@QEAAKKPEAU_GUID@@@Z; CDimRouterManager::RemoveRoutingDomain(ulong,_GUID *)
0x1800152fd  test    eax, eax
0x1800152ff  jz      short loc_180015362
0x180015301  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x180015308  jz      short loc_180015362
0x18001530a  xor     ecx, ecx
0x18001530c  lea     rdx, aDimstoprouting; "DimStopRoutingDomain: RouterManager:Rem"...
0x180015313  mov     word ptr [rsp+8B0h+var_840], cx
0x180015318  mov     r8d, eax
0x18001531b  mov     word ptr [rsp+8B0h+var_868], cx
0x180015320  lea     rcx, [rsp+8B0h+var_840]
0x180015325  call    FormatRRASErrorString
0x18001532a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x180015331  jz      short loc_180015362
0x180015333  test    rbx, rbx
0x180015336  lea     rax, [rsp+8B0h+var_868]
0x18001533b  mov     [rsp+8B0h+var_888], rax
0x180015340  lea     r9, [rsp+8B0h+var_878]
0x180015345  cmovnz  r9, rbx
0x180015349  mov     [rsp+8B0h+var_890], 0
0x180015352  lea     r8, [rsp+8B0h+var_840]
0x180015357  mov     rdx, rdi
0x18001535a  mov     rcx, r13
0x18001535d  call    McTemplateU0zjzz_EventWriteTransfer
0x180015362  mov     r8, rbx; struct _GUID *
0x180015365  mov     edx, 57h ; 'W'; unsigned int
0x18001536a  call    ?RemoveRoutingDomain@CDimRouterManager@@QEAAKKPEAU_GUID@@@Z; CDimRouterManager::RemoveRoutingDomain(ulong,_GUID *)
0x18001536f  test    eax, eax
0x180015371  jz      short loc_1800153D4
0x180015373  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x18001537a  jz      short loc_1800153D4
0x18001537c  xor     ecx, ecx
0x18001537e  lea     rdx, aDimstoprouting_2; "DimStopRoutingDomain: RouterManager:Rem"...
0x180015385  mov     word ptr [rsp+8B0h+var_840], cx
0x18001538a  mov     r8d, eax
0x18001538d  mov     word ptr [rsp+8B0h+var_868], cx
0x180015392  lea     rcx, [rsp+8B0h+var_840]
0x180015397  call    FormatRRASErrorString
0x18001539c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x1800153a3  jz      short loc_1800153D4
0x1800153a5  test    rbx, rbx
0x1800153a8  lea     rax, [rsp+8B0h+var_868]
0x1800153ad  mov     [rsp+8B0h+var_888], rax
0x1800153b2  lea     r9, [rsp+8B0h+var_878]
0x1800153b7  cmovnz  r9, rbx
0x1800153bb  mov     [rsp+8B0h+var_890], 0
0x1800153c4  lea     r8, [rsp+8B0h+var_840]
0x1800153c9  mov     rdx, rdi
0x1800153cc  mov     rcx, r13
0x1800153cf  call    McTemplateU0zjzz_EventWriteTransfer
0x1800153d4  test    esi, esi
0x1800153d6  jz      short loc_1800153E0
0x1800153d8  mov     rdx, rbx; struct _GUID *
0x1800153db  call    ?RemoveInterfaces@CDimInterfaceTable@@QEAAXPEAU_GUID@@@Z; CDimInterfaceTable::RemoveInterfaces(_GUID *)
0x1800153e0  xor     edx, edx; int
0x1800153e2  mov     rcx, rbx; struct _GUID *
0x1800153e5  call    ReferenceOrDereferenceRoutingDomain
0x1800153ea  mov     edi, eax
0x1800153ec  test    eax, eax
0x1800153ee  jz      short loc_180015455
0x1800153f0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800153f7  jz      short loc_180015455
0x1800153f9  xor     eax, eax
0x1800153fb  lea     rdx, aDimstoprouting_4; "DimStopRoutingDomain: ReferenceOrDerefe"...
0x180015402  mov     r8d, edi
0x180015405  mov     word ptr [rsp+8B0h+var_840], ax
0x18001540a  lea     rcx, [rsp+8B0h+var_840]
0x18001540f  mov     word ptr [rsp+8B0h+var_868], ax
0x180015414  call    FormatRRASErrorString
0x180015419  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180015420  jz      short loc_180015455
0x180015422  test    rbx, rbx
0x180015425  lea     rax, [rsp+8B0h+var_868]
0x18001542a  mov     [rsp+8B0h+var_888], rax
0x18001542f  lea     r9, [rsp+8B0h+var_878]
0x180015434  cmovnz  r9, rbx
0x180015438  mov     [rsp+8B0h+var_890], 0
0x180015441  lea     r8, [rsp+8B0h+var_840]
0x180015446  mov     rcx, r13
0x180015449  lea     rdx, RasDimParamTraceError
0x180015450  call    McTemplateU0zjzz_EventWriteTransfer
0x180015455  mov     rcx, rbx; struct _GUID *
0x180015458  call    MarkRoutingDomainAsUnAvailable
0x18001545d  mov     eax, edi
0x18001545f  mov     rcx, [rbp+7B0h+var_40]
0x180015466  xor     rcx, rsp; StackCookie
0x180015469  call    __security_check_cookie
0x18001546e  add     rsp, 888h
0x180015475  pop     r15
0x180015477  pop     r13
0x180015479  pop     rdi
0x18001547a  pop     rsi
0x18001547b  pop     rbx
0x18001547c  pop     rbp
0x18001547d  retn
```
