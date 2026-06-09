# CWSDPublisher::BeginPublication(void)

- ea: `0x1800022b4`
- end: `0x1800027a8`
- name: `?BeginPublication@CWSDPublisher@@QEAAJXZ`
- size: `1268`
- prototype: `__int64 __fastcall(CWSDPublisher *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001b20`

## callees

- `0x180001014`
- `0x180001020`
- `0x180001f24`
- `0x180001f70`
- `0x1800022b4`
- `0x180002930`
- `0x180002bc0`
- `0x180003404`
- `0x18000399c`
- `0x180004220`
- `0x180005246`
- `0x180005270`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000272c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000272c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000233a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000233a`
- `wsdapi!WSDFreeLinkedMemory` at `0x180002622`
- `wsdapi!WSDFreeLinkedMemory` at `0x180002637`
- `wsdapi!WSDFreeLinkedMemory` at `0x180002622`
- `wsdapi!WSDFreeLinkedMemory` at `0x180002637`
- `wsdapi!WSDXMLCleanupElement` at `0x1800025f8`
- `wsdapi!WSDXMLCleanupElement` at `0x18000260d`
- `wsdapi!WSDXMLCleanupElement` at `0x1800025f8`
- `wsdapi!WSDXMLCleanupElement` at `0x18000260d`
- `wsdapi!WSDXMLBuildAnyForSingleElement` at `0x1800024dd`
- `wsdapi!WSDXMLBuildAnyForSingleElement` at `0x180002564`
- `wsdapi!WSDXMLBuildAnyForSingleElement` at `0x1800024dd`
- `wsdapi!WSDXMLBuildAnyForSingleElement` at `0x180002564`
- `wsdapi!WSDCreateDeviceHost2` at `0x1800023a2`
- `wsdapi!WSDCreateDeviceHost2` at `0x1800023a2`
- `wsdapi!WSDAddFirewallCheck` at `0x180002353`
- `wsdapi!WSDAddFirewallCheck` at `0x180002353`

## string_xrefs

- `0x1800023fe`: `http://schemas.microsoft.com/windows/pub/2005/07`
- `0x18000234c`: `@FirewallAPI.dll,-32752`
- `0x1800023f7`: `Computer`
- `0x18000241d`: `IWSDXMLContext::AddNameToNamespace`
- `0x180002537`: `IWSDXMLContext::AddNameToNamespace`
- `0x1800024ef`: `WSDXMLBuildAnyForSingleElement`
- `0x180002576`: `WSDXMLBuildAnyForSingleElement`
- `0x180002518`: `http://schemas.microsoft.com/windows/pnpx/2005/10`
- `0x18000255d`: `Computers`

## pseudocode

```c
__int64 __fastcall CWSDPublisher::BeginPublication(CWSDPublisher *this)
{
  unsigned int ComputerInfo; // ebx
  IWSDXMLContext *v3; // rdx
  const WCHAR *v4; // rcx
  int v5; // eax
  const struct _EVENT_DESCRIPTOR *v6; // rcx
  unsigned __int16 *v7; // rsi
  int v8; // ecx
  __int64 v9; // rax
  unsigned int v10; // ebx
  unsigned __int16 *v11; // rax
  HRESULT v12; // eax
  const struct _EVENT_DESCRIPTOR *v13; // rcx
  int v14; // eax
  const struct _EVENT_DESCRIPTOR *v15; // rcx
  HRESULT v16; // eax
  const struct _EVENT_DESCRIPTOR *v17; // rcx
  int v18; // eax
  const struct _EVENT_DESCRIPTOR *v19; // rcx
  __int64 v20; // rcx
  struct IFunctionInstanceCollection *v21; // rdx
  unsigned int v22; // eax
  int v23; // eax
  bool v24; // cf
  IWSDDeviceHost **ppDeviceHost; // [rsp+20h] [rbp-E0h]
  WSDXML_ELEMENT *pAny; // [rsp+40h] [rbp-C0h] BYREF
  WSDXML_NAME *v28; // [rsp+48h] [rbp-B8h] BYREF
  WSDXML_ELEMENT *ppAny; // [rsp+50h] [rbp-B0h] BYREF
  WSDXML_NAME *pElementName; // [rsp+58h] [rbp-A8h] BYREF
  struct IFunctionInstanceCollection *v31; // [rsp+60h] [rbp-A0h] BYREF
  WSD_CONFIG_PARAM pConfigParams; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v33; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v34; // [rsp+88h] [rbp-78h]
  unsigned __int64 v35; // [rsp+90h] [rbp-70h]
  WSDXML_ELEMENT *v36; // [rsp+98h] [rbp-68h]
  _QWORD v37[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v38[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v39; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v40[3]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v41[1024]; // [rsp+100h] [rbp+0h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    ppDeviceHost = (IWSDDeviceHost **)this;
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
  }
  v31 = 0;
  ComputerInfo = 0;
  memset(&pConfigParams, 0, sizeof(pConfigParams));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  if ( !*((_QWORD *)this + 24) )
    ComputerInfo = WSDAddFirewallCheck(L"@FirewallAPI.dll,-32752", (void **)this + 24);
  if ( !*((_QWORD *)this + 9) )
  {
    if ( !ComputerInfo )
    {
      v3 = (IWSDXMLContext *)*((_QWORD *)this + 1);
      v4 = (const WCHAR *)*((_QWORD *)this + 8);
      pConfigParams.pConfigData = (char *)this + 88;
      *(_QWORD *)&pConfigParams.configParamType = 2;
      *(_QWORD *)&pConfigParams.dwConfigDataSize = 4;
      ComputerInfo = WSDCreateDeviceHost2(v4, v3, &pConfigParams, 1u, (IWSDDeviceHost **)this + 9);
    }
    v34 = 0;
    v36 = 0;
    v37[1] = v40;
    v35 = *((_QWORD *)this + 8);
    v37[0] = 0;
    v33 = v37;
    pElementName = 0;
    v40[0] = v35;
    v39 = 0;
    memset(&v40[1], 0, 32);
    if ( !ComputerInfo )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, WSDXML_NAME **))(**((_QWORD **)this + 1)
                                                                                               + 32LL))(
             *((_QWORD *)this + 1),
             L"http://schemas.microsoft.com/windows/pub/2005/07",
             L"Computer",
             &pElementName);
      ComputerInfo = v5;
      if ( v5 )
        LogError(v6, v5, L"IWSDXMLContext::AddNameToNamespace", 0x271u, (const char *)ppDeviceHost);
    }
    v7 = 0;
    v38[1] = pElementName;
    v38[0] = 0;
    if ( !ComputerInfo )
    {
      memset_0(v41, 0, sizeof(v41));
      ComputerInfo = GetComputerInfo(v8, v41);
      if ( !ComputerInfo )
      {
        v9 = -1;
        do
          ++v9;
        while ( v41[v9] );
        v10 = 2 * v9 + 1;
        v11 = (unsigned __int16 *)operator new[](saturated_mul(v10, 2u));
        v7 = v11;
        if ( !v11 )
        {
          ComputerInfo = -2147024882;
          ppAny = 0;
          goto LABEL_18;
        }
        ComputerInfo = EscapeString(v41, v11, v10);
      }
    }
    ppAny = 0;
    if ( ComputerInfo || (v12 = WSDXMLBuildAnyForSingleElement(pElementName, v7, &ppAny), (ComputerInfo = v12) == 0) )
    {
      v28 = 0;
      if ( ComputerInfo
        || (v14 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, WSDXML_NAME **))(**((_QWORD **)this + 1) + 32LL))(
                    *((_QWORD *)this + 1),
                    L"http://schemas.microsoft.com/windows/pnpx/2005/10",
                    L"DeviceCategory",
                    &v28),
            (ComputerInfo = v14) == 0) )
      {
        pAny = 0;
        if ( !ComputerInfo )
        {
          v16 = WSDXMLBuildAnyForSingleElement(v28, L"Computers", &pAny);
          ComputerInfo = v16;
          if ( v16 )
            LogError(v17, v16, L"WSDXMLBuildAnyForSingleElement", 0x2A4u, (const char *)ppDeviceHost);
        }
        goto LABEL_30;
      }
      LogError(v15, v14, L"IWSDXMLContext::AddNameToNamespace", 0x29Bu, (const char *)ppDeviceHost);
LABEL_19:
      pAny = 0;
LABEL_30:
      v36 = ppAny;
      v34 = v38;
      *(_QWORD *)&v39 = &v33;
      qword_18000A098 = (__int64)pAny;
      if ( !ComputerInfo )
      {
        v18 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64 *, __int128 *))(**((_QWORD **)this + 9) + 64LL))(
                *((_QWORD *)this + 9),
                &off_18000A068,
                &off_180007060,
                &v39);
        ComputerInfo = v18;
        if ( v18 )
          LogError(v19, v18, L"IWSDDeviceHost::SetMetadata", 0x2B0u, 0);
      }
      if ( pAny )
      {
        WSDXMLCleanupElement(pAny);
        pAny = 0;
      }
      if ( ppAny )
      {
        WSDXMLCleanupElement(ppAny);
        ppAny = 0;
      }
      if ( pElementName )
      {
        WSDFreeLinkedMemory(pElementName);
        pElementName = 0;
      }
      if ( v28 )
      {
        WSDFreeLinkedMemory(v28);
        v28 = 0;
      }
      if ( v7 )
        operator delete[](v7);
      goto LABEL_43;
    }
    LogError(v13, v12, L"WSDXMLBuildAnyForSingleElement", 0x292u, (const char *)ppDeviceHost);
LABEL_18:
    v28 = 0;
    goto LABEL_19;
  }
LABEL_43:
  if ( *((_DWORD *)this + 5) )
  {
    if ( *((_DWORD *)this + 6) && !ComputerInfo )
      ComputerInfo = CWSDPublisher::StartHost(this);
  }
  else
  {
    if ( ComputerInfo
      || (ComputerInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, CWSDPublisher *, _QWORD, char *))(**((_QWORD **)this + 4) + 40LL))(
                           *((_QWORD *)this + 4),
                           *((_QWORD *)this + 6),
                           *((_QWORD *)this + 7),
                           1,
                           this,
                           0,
                           (char *)this + 40)) != 0
      || (ComputerInfo = (*(__int64 (__fastcall **)(_QWORD, struct IFunctionInstanceCollection **))(**((_QWORD **)this + 5)
                                                                                                  + 40LL))(
                           *((_QWORD *)this + 5),
                           &v31)) != 0 )
    {
      v20 = *((_QWORD *)this + 5);
      if ( v20 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        *((_QWORD *)this + 5) = 0;
      }
    }
    else
    {
      *((_DWORD *)this + 5) = 1;
      *((_DWORD *)this + 6) = 1;
      v21 = v31;
      *((_DWORD *)this + 7) = 1;
      v22 = CWSDPublisher::PublishInitialCollection(this, v21);
      *((_DWORD *)this + 7) = 0;
      ComputerInfo = v22;
      if ( !v22 )
        ComputerInfo = CWSDPublisher::StartHost(this);
    }
    if ( v31 )
    {
      ((void (__fastcall *)(struct IFunctionInstanceCollection *))v31->lpVtbl->Release)(v31);
      v31 = 0;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v23 = 0;
  if ( ComputerInfo )
    v24 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v24 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v23) = !v24;
    if ( v23 )
      WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
  }
  return ComputerInfo;
}

```

## disassembly

```asm
0x1800022b4  mov     [rsp-8+arg_8], rbx
0x1800022b9  mov     [rsp-8+arg_10], rsi
0x1800022be  push    rbp
0x1800022bf  push    rdi
0x1800022c0  push    r12
0x1800022c2  push    r14
0x1800022c4  push    r15
0x1800022c6  lea     rbp, [rsp-810h]
0x1800022ce  sub     rsp, 910h
0x1800022d5  mov     rax, cs:__security_cookie
0x1800022dc  xor     rax, rsp
0x1800022df  mov     [rbp+830h+var_30], rax
0x1800022e6  mov     rdi, rcx
0x1800022e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022f0  lea     rax, WPP_GLOBAL_Control
0x1800022f7  cmp     rcx, rax
0x1800022fa  jz      short loc_18000231C
0x1800022fc  cmp     byte ptr [rcx+19h], 4
0x180002300  jb      short loc_18000231C
0x180002302  mov     rcx, [rcx+10h]
0x180002306  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x18000230d  mov     edx, 13h
0x180002312  mov     [rsp+930h+ppDeviceHost], rdi
0x180002317  call    WPP_SF_sq
0x18000231c  xor     r15d, r15d
0x18000231f  lea     rcx, [rdi+60h]; lpCriticalSection
0x180002323  xorps   xmm0, xmm0
0x180002326  mov     [rsp+930h+var_8D0], r15
0x18000232b  xor     eax, eax
0x18000232d  mov     ebx, r15d
0x180002330  movups  xmmword ptr [rsp+930h+pConfigParams.configParamType], xmm0
0x180002335  mov     qword ptr [rsp+930h+pConfigParams.dwConfigDataSize], rax
0x18000233a  call    cs:__imp_EnterCriticalSection
0x180002340  lea     rdx, [rdi+0C0h]
0x180002347  cmp     [rdx], r15
0x18000234a  jnz     short loc_18000235B
0x18000234c  lea     rcx, aFirewallapiDll; "@FirewallAPI.dll,-32752"
0x180002353  call    cs:__imp_?WSDAddFirewallCheck@@YAJPEBGPEAPEAX@Z; WSDAddFirewallCheck(ushort const *,void * *)
0x180002359  mov     ebx, eax
0x18000235b  lea     rcx, [rdi+48h]
0x18000235f  mov     r12d, 1
0x180002365  cmp     [rcx], r15
0x180002368  jnz     loc_18000264F
0x18000236e  test    ebx, ebx
0x180002370  jnz     short loc_1800023AA
0x180002372  mov     rdx, [rdi+8]; pContext
0x180002376  lea     rax, [rdi+58h]
0x18000237a  mov     [rsp+930h+ppDeviceHost], rcx; char *
0x18000237f  lea     r8, [rsp+930h+pConfigParams]; pConfigParams
0x180002384  mov     rcx, [rdi+40h]; pszLocalId
0x180002388  mov     r9d, r12d; dwConfigParamCount
0x18000238b  mov     [rsp+930h+pConfigParams.pConfigData], rax
0x180002390  mov     qword ptr [rsp+930h+pConfigParams.configParamType], 2
0x180002399  mov     qword ptr [rsp+930h+pConfigParams.dwConfigDataSize], 4
0x1800023a2  call    cs:__imp_WSDCreateDeviceHost2
0x1800023a8  mov     ebx, eax
0x1800023aa  mov     [rbp+830h+var_8A8], r15
0x1800023ae  xorps   xmm0, xmm0
0x1800023b1  mov     [rbp+830h+var_898], r15
0x1800023b5  lea     rax, [rbp+830h+var_860]
0x1800023b9  mov     [rbp+830h+var_888], rax
0x1800023bd  lea     rcx, [rbp+830h+var_890]
0x1800023c1  mov     rax, [rdi+40h]
0x1800023c5  mov     [rbp+830h+var_8A0], rax
0x1800023c9  mov     [rbp+830h+var_890], r15
0x1800023cd  mov     [rbp+830h+var_8B0], rcx
0x1800023d1  mov     [rsp+930h+pElementName], r15
0x1800023d6  movups  [rbp+830h+var_860], xmm0
0x1800023da  mov     qword ptr [rbp+830h+var_860], rax
0x1800023de  movups  [rbp+830h+var_870], xmm0
0x1800023e2  movups  [rbp+830h+var_850], xmm0
0x1800023e6  movups  [rbp+830h+var_840], xmm0
0x1800023ea  test    ebx, ebx
0x1800023ec  jnz     short loc_18000242B
0x1800023ee  mov     rcx, [rdi+8]
0x1800023f2  lea     r9, [rsp+930h+pElementName]
0x1800023f7  lea     r8, aComputer; "Computer"
0x1800023fe  lea     rdx, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/pu"...
0x180002405  mov     rax, [rcx]
0x180002408  mov     rax, [rax+20h]
0x18000240c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002411  mov     ebx, eax
0x180002413  test    eax, eax
0x180002415  jz      short loc_18000242B
0x180002417  mov     r9d, 271h; unsigned int
0x18000241d  lea     r8, aIwsdxmlcontext_1; "IWSDXMLContext::AddNameToNamespace"
0x180002424  mov     edx, eax; int
0x180002426  call    ?LogError@@YAJPEBU_EVENT_DESCRIPTOR@@JPEBGKPEBD@Z; LogError(_EVENT_DESCRIPTOR const *,long,ushort const *,ulong,char const *)
0x18000242b  mov     rax, [rsp+930h+pElementName]
0x180002430  mov     rsi, r15
0x180002433  mov     [rbp+830h+var_878], rax
0x180002437  mov     [rbp+830h+var_880], r15
0x18000243b  test    ebx, ebx
0x18000243d  jnz     loc_1800024C7
0x180002443  xor     edx, edx; Val
0x180002445  lea     rcx, [rbp+830h+var_830]; void *
0x180002449  mov     r8d, 800h; Size
0x18000244f  call    memset_0
0x180002454  lea     rdx, [rbp+830h+var_830]; unsigned __int16 *
0x180002458  call    ?GetComputerInfo@@YAJHPEAG@Z; GetComputerInfo(int,ushort *)
0x18000245d  mov     ebx, eax
0x18000245f  test    eax, eax
0x180002461  jnz     short loc_1800024C7
0x180002463  or      r8, 0FFFFFFFFFFFFFFFFh
0x180002467  lea     rcx, [rbp+830h+var_830]
0x18000246b  mov     rax, r8
0x18000246e  inc     rax
0x180002471  cmp     [rcx+rax*2], r15w
0x180002476  jnz     short loc_18000246E
0x180002478  lea     ebx, ds:1[rax*2]
0x18000247f  mov     eax, 2
0x180002484  mov     ecx, ebx
0x180002486  mul     rcx
0x180002489  cmovb   rax, r8
0x18000248d  mov     rcx, rax; unsigned __int64
0x180002490  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002495  mov     rsi, rax
0x180002498  test    rax, rax
0x18000249b  jnz     short loc_1800024B6
0x18000249d  mov     ebx, 8007000Eh
0x1800024a2  mov     [rsp+930h+ppAny], r15
0x1800024a7  mov     [rsp+930h+var_8E8], r15
0x1800024ac  mov     [rsp+930h+pAny], r15
0x1800024b1  jmp     loc_180002584
0x1800024b6  mov     r8d, ebx; unsigned int
0x1800024b9  lea     rcx, [rbp+830h+var_830]; unsigned __int16 *
0x1800024bd  mov     rdx, rax; unsigned __int16 *
0x1800024c0  call    ?EscapeString@@YAJPEBGPEAGK@Z; EscapeString(ushort const *,ushort *,ulong)
0x1800024c5  mov     ebx, eax
0x1800024c7  mov     [rsp+930h+ppAny], r15
0x1800024cc  test    ebx, ebx
0x1800024ce  jnz     short loc_1800024FF
0x1800024d0  mov     rcx, [rsp+930h+pElementName]; pElementName
0x1800024d5  lea     r8, [rsp+930h+ppAny]; ppAny
0x1800024da  mov     rdx, rsi; pszText
0x1800024dd  call    cs:__imp_WSDXMLBuildAnyForSingleElement
0x1800024e3  mov     ebx, eax
0x1800024e5  test    eax, eax
0x1800024e7  jz      short loc_1800024FF
0x1800024e9  mov     r9d, 292h; unsigned int
0x1800024ef  lea     r8, aWsdxmlbuildany; "WSDXMLBuildAnyForSingleElement"
0x1800024f6  mov     edx, eax; int
0x1800024f8  call    ?LogError@@YAJPEBU_EVENT_DESCRIPTOR@@JPEBGKPEBD@Z; LogError(_EVENT_DESCRIPTOR const *,long,ushort const *,ulong,char const *)
0x1800024fd  jmp     short loc_1800024A7
0x1800024ff  mov     [rsp+930h+var_8E8], r15
0x180002504  test    ebx, ebx
0x180002506  jnz     short loc_18000254A
0x180002508  mov     rcx, [rdi+8]
0x18000250c  lea     r9, [rsp+930h+var_8E8]
0x180002511  lea     r8, aDevicecategory; "DeviceCategory"
0x180002518  lea     rdx, aHttpSchemasMic; "http://schemas.microsoft.com/windows/pn"...
0x18000251f  mov     rax, [rcx]
0x180002522  mov     rax, [rax+20h]
0x180002526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000252b  mov     ebx, eax
0x18000252d  test    eax, eax
0x18000252f  jz      short loc_18000254A
0x180002531  mov     r9d, 29Bh; unsigned int
0x180002537  lea     r8, aIwsdxmlcontext_1; "IWSDXMLContext::AddNameToNamespace"
0x18000253e  mov     edx, eax; int
0x180002540  call    ?LogError@@YAJPEBU_EVENT_DESCRIPTOR@@JPEBGKPEBD@Z; LogError(_EVENT_DESCRIPTOR const *,long,ushort const *,ulong,char const *)
0x180002545  jmp     loc_1800024AC
0x18000254a  mov     [rsp+930h+pAny], r15
0x18000254f  test    ebx, ebx
0x180002551  jnz     short loc_180002584
0x180002553  mov     rcx, [rsp+930h+var_8E8]; pElementName
0x180002558  lea     r8, [rsp+930h+pAny]; ppAny
0x18000255d  lea     rdx, pszText; "Computers"
0x180002564  call    cs:__imp_WSDXMLBuildAnyForSingleElement
0x18000256a  mov     ebx, eax
0x18000256c  test    eax, eax
0x18000256e  jz      short loc_180002584
0x180002570  mov     r9d, 2A4h; unsigned int
0x180002576  lea     r8, aWsdxmlbuildany; "WSDXMLBuildAnyForSingleElement"
0x18000257d  mov     edx, eax; int
0x18000257f  call    ?LogError@@YAJPEBU_EVENT_DESCRIPTOR@@JPEBGKPEBD@Z; LogError(_EVENT_DESCRIPTOR const *,long,ushort const *,ulong,char const *)
0x180002584  mov     rax, [rsp+930h+ppAny]
0x180002589  mov     [rbp+830h+var_898], rax
0x18000258d  lea     rax, [rbp+830h+var_880]
0x180002591  mov     [rbp+830h+var_8A8], rax
0x180002595  lea     rax, [rbp+830h+var_8B0]
0x180002599  mov     qword ptr [rbp+830h+var_870], rax
0x18000259d  mov     rax, [rsp+930h+pAny]
0x1800025a2  mov     cs:qword_18000A098, rax
0x1800025a9  test    ebx, ebx
0x1800025ab  jnz     short loc_1800025EE
0x1800025ad  mov     rcx, [rdi+48h]
0x1800025b1  lea     r9, [rbp+830h+var_870]
0x1800025b5  lea     r8, off_180007060
0x1800025bc  mov     [rsp+930h+ppDeviceHost], r15; char *
0x1800025c1  lea     rdx, off_18000A068
0x1800025c8  mov     rax, [rcx]
0x1800025cb  mov     rax, [rax+40h]
0x1800025cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025d4  mov     ebx, eax
0x1800025d6  test    eax, eax
0x1800025d8  jz      short loc_1800025EE
0x1800025da  mov     r9d, 2B0h; unsigned int
0x1800025e0  lea     r8, aIwsddevicehost; "IWSDDeviceHost::SetMetadata"
0x1800025e7  mov     edx, eax; int
0x1800025e9  call    ?LogError@@YAJPEBU_EVENT_DESCRIPTOR@@JPEBGKPEBD@Z; LogError(_EVENT_DESCRIPTOR const *,long,ushort const *,ulong,char const *)
0x1800025ee  mov     rcx, [rsp+930h+pAny]; pAny
0x1800025f3  test    rcx, rcx
0x1800025f6  jz      short loc_180002603
0x1800025f8  call    cs:__imp_WSDXMLCleanupElement
0x1800025fe  mov     [rsp+930h+pAny], r15
0x180002603  mov     rcx, [rsp+930h+ppAny]; pAny
0x180002608  test    rcx, rcx
0x18000260b  jz      short loc_180002618
0x18000260d  call    cs:__imp_WSDXMLCleanupElement
0x180002613  mov     [rsp+930h+ppAny], r15
0x180002618  mov     rcx, [rsp+930h+pElementName]; pVoid
0x18000261d  test    rcx, rcx
0x180002620  jz      short loc_18000262D
0x180002622  call    cs:__imp_WSDFreeLinkedMemory
0x180002628  mov     [rsp+930h+pElementName], r15
0x18000262d  mov     rcx, [rsp+930h+var_8E8]; pVoid
0x180002632  test    rcx, rcx
0x180002635  jz      short loc_180002642
0x180002637  call    cs:__imp_WSDFreeLinkedMemory
0x18000263d  mov     [rsp+930h+var_8E8], r15
0x180002642  test    rsi, rsi
0x180002645  jz      short loc_18000264F
0x180002647  mov     rcx, rsi; Block
0x18000264a  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000264f  cmp     [rdi+14h], r15d
0x180002653  jnz     loc_180002714
0x180002659  test    ebx, ebx
0x18000265b  jnz     short loc_1800026B5
0x18000265d  mov     rcx, [rdi+20h]
0x180002661  lea     rsi, [rdi+28h]
0x180002665  mov     r8, [rdi+38h]
0x180002669  mov     r9d, r12d
0x18000266c  mov     rdx, [rdi+30h]
0x180002670  mov     [rsp+930h+var_900], rsi
0x180002675  mov     rax, [rcx]
0x180002678  mov     [rsp+930h+var_908], r15
0x18000267d  mov     [rsp+930h+ppDeviceHost], rdi
0x180002682  mov     rax, [rax+28h]
0x180002686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000268b  mov     ebx, eax
0x18000268d  test    eax, eax
0x18000268f  jnz     short loc_1800026B5
0x180002691  mov     rcx, [rsi]
0x180002694  lea     rdx, [rsp+930h+var_8D0]
0x180002699  mov     rax, [rcx]
0x18000269c  mov     rax, [rax+28h]
0x1800026a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026a5  mov     ebx, eax
0x1800026a7  test    eax, eax
0x1800026a9  jnz     short loc_1800026B5
0x1800026ab  mov     [rdi+14h], r12d
0x1800026af  mov     [rdi+18h], r12d
0x1800026b3  jmp     short loc_1800026D2
0x1800026b5  mov     rcx, [rdi+28h]
0x1800026b9  test    rcx, rcx
0x1800026bc  jz      short loc_1800026CE
0x1800026be  mov     rax, [rcx]
0x1800026c1  mov     rax, [rax+10h]
0x1800026c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026ca  mov     [rdi+28h], r15
0x1800026ce  test    ebx, ebx
0x1800026d0  jnz     short loc_1800026F7
0x1800026d2  mov     rdx, [rsp+930h+var_8D0]; struct IFunctionInstanceCollection *
0x1800026d7  mov     rcx, rdi; this
0x1800026da  mov     [rdi+1Ch], r12d
0x1800026de  call    ?PublishInitialCollection@CWSDPublisher@@IEAAJPEAUIFunctionInstanceCollection@@@Z; CWSDPublisher::PublishInitialCollection(IFunctionInstanceCollection *)
0x1800026e3  mov     [rdi+1Ch], r15d
0x1800026e7  mov     ebx, eax
0x1800026e9  test    eax, eax
0x1800026eb  jnz     short loc_1800026F7
0x1800026ed  mov     rcx, rdi; this
0x1800026f0  call    ?StartHost@CWSDPublisher@@IEAAJXZ; CWSDPublisher::StartHost(void)
0x1800026f5  mov     ebx, eax
0x1800026f7  mov     rcx, [rsp+930h+var_8D0]
0x1800026fc  test    rcx, rcx
0x1800026ff  jz      short loc_180002728
0x180002701  mov     rax, [rcx]
0x180002704  mov     rax, [rax+10h]
0x180002708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000270d  mov     [rsp+930h+var_8D0], r15
0x180002712  jmp     short loc_180002728
0x180002714  cmp     [rdi+18h], r15d
0x180002718  jz      short loc_180002728
0x18000271a  test    ebx, ebx
0x18000271c  jnz     short loc_180002728
0x18000271e  mov     rcx, rdi; this
0x180002721  call    ?StartHost@CWSDPublisher@@IEAAJXZ; CWSDPublisher::StartHost(void)
0x180002726  mov     ebx, eax
0x180002728  lea     rcx, [rdi+60h]; lpCriticalSection
0x18000272c  call    cs:__imp_LeaveCriticalSection
0x180002732  mov     rcx, cs:WPP_GLOBAL_Control
0x180002739  mov     eax, r15d
0x18000273c  test    ebx, ebx
0x18000273e  jnz     short loc_180002746
0x180002740  cmp     byte ptr [rcx+19h], 4
0x180002744  jmp     short loc_18000274A
0x180002746  cmp     byte ptr [rcx+19h], 2
0x18000274a  setnb   al
0x18000274d  lea     rdx, WPP_GLOBAL_Control
  ... truncated ...
```
