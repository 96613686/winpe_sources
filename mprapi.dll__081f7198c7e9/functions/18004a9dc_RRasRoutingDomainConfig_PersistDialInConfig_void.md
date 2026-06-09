# RRasRoutingDomainConfig::PersistDialInConfig(void)

- ea: `0x18004a9dc`
- end: `0x18004add9`
- name: `?PersistDialInConfig@RRasRoutingDomainConfig@@AEAAKXZ`
- size: `1021`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18004a6c0`
- `0x18004c944`

## callees

- `0x18004a9dc`
- `0x180050714`
- `0x180050924`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ad97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ad97`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ab86`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ab86`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004aad7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004aad7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004abf2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004ac76`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004acbd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004ad04`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004ad47`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004ad87`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004abf2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004ac76`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004acbd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004ad04`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004ad47`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004ad87`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18004aaa6`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18004aaa6`

## string_xrefs

- `0x18004aba8`: `%s: Couldn't write value %s: %d`
- `0x18004ac4f`: `%s: Couldn't write value %s: %d`
- `0x18004aaf9`: `%s: RegCreateKeyEx (%s) failed: %d.`
- `0x18004aa68`: `RRasRoutingDomainConfig::PersistDialInConfig`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::PersistDialInConfig(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  HKEY v3; // rcx
  LSTATUS v4; // eax
  const WCHAR *v5; // r9
  const wchar_t *v6; // rdx
  GUID *v7; // r9
  unsigned int v8; // eax
  const WCHAR *v9; // r9
  const unsigned __int16 *v10; // rdx
  unsigned int v11; // ebx
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  unsigned int v14; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v17; // [rsp+68h] [rbp-98h]
  __int128 v18; // [rsp+78h] [rbp-88h]
  __int64 v19; // [rsp+88h] [rbp-78h]
  int v20; // [rsp+90h] [rbp-70h]
  int v21; // [rsp+94h] [rbp-6Ch]
  GUID v22; // [rsp+98h] [rbp-68h] BYREF
  int v23; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v24; // [rsp+ACh] [rbp-54h]
  __int128 v25; // [rsp+BCh] [rbp-44h]
  int v26; // [rsp+CCh] [rbp-34h]
  int v27; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v28[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v14 = 0;
  hKey = 0;
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v17 = 0;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  v20 = -1;
  v21 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v16,
      L"RRasRoutingDomainConfig::PersistDialInConfig",
      &v14,
      v2,
      (struct _GUID *)((char *)this + 516));
  v3 = (HKEY)*((_QWORD *)this + 103);
  if ( (*((_BYTE *)this + 536) & 9) == 0 )
  {
    RegDeleteKeyW(v3, L"DialIn");
    goto LABEL_48;
  }
  v4 = RegCreateKeyExW(v3, L"DialIn", 0, 0, 0, 0x20006u, 0, &hKey, 0);
  v14 = v4;
  if ( v4 )
  {
    if ( !(_QWORD)xmmword_180078C60 )
      goto LABEL_48;
    v5 = L"DialIn";
    v6 = L"%s: RegCreateKeyEx (%s) failed: %d.";
    goto LABEL_8;
  }
  v4 = RegSetValueExW(hKey, L"MaxVpnConnections", 0, 4u, (const BYTE *)this + 624, 4u);
  v14 = v4;
  if ( v4 )
  {
    if ( (_QWORD)xmmword_180078C60 )
    {
      v5 = L"MaxVpnConnections";
LABEL_14:
      v6 = L"%s: Couldn't write value %s: %d";
LABEL_8:
      dwOptions[0] = v4;
      LOWORD(v23) = 0;
      v22 = GUID_NULL;
      LOWORD(v27) = 0;
      FormatRRASErrorString(&v27, v6, L"RRasRoutingDomainConfig::PersistDialInConfig", v5, *(_QWORD *)dwOptions);
      v7 = &v22;
      if ( this != (RRasRoutingDomainConfig *)-516LL )
        v7 = (GUID *)((char *)this + 516);
LABEL_10:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C60,
        &v27,
        v7,
        0,
        &v23);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  if ( *((_DWORD *)this + 158) )
  {
    v4 = WriteAddressToRegistry(hKey, L"IPv4DnsServer", 1, (unsigned __int8 *)this + 632);
    v14 = v4;
    if ( v4 )
    {
      if ( (_QWORD)xmmword_180078C60 )
      {
        v5 = L"IPv4DnsServer";
        goto LABEL_14;
      }
      goto LABEL_48;
    }
  }
  else
  {
    RegDeleteValueW(hKey, L"IPv4DnsServer");
  }
  if ( *((_DWORD *)this + 162) )
  {
    v8 = WriteAddressToRegistry(hKey, L"IPv4DhcpServer", 1, (unsigned __int8 *)this + 648);
    v14 = v8;
    if ( v8 )
    {
      if ( !(_QWORD)xmmword_180078C60 )
        goto LABEL_48;
      v9 = L"IPv4DhcpServer";
      goto LABEL_24;
    }
  }
  else
  {
    RegDeleteValueW(hKey, L"IPv4DhcpServer");
  }
  if ( *((_DWORD *)this + 166) )
  {
    v8 = WriteAddressToRegistry(hKey, L"IPv4NetBiosServer", 1, (unsigned __int8 *)this + 664);
    v14 = v8;
    if ( v8 )
    {
      if ( !(_QWORD)xmmword_180078C60 )
        goto LABEL_48;
      v9 = L"IPv4NetBiosServer";
      goto LABEL_24;
    }
  }
  else
  {
    RegDeleteValueW(hKey, L"IPv4NetBiosServer");
  }
  if ( *((_DWORD *)this + 170) )
  {
    v8 = WriteAddressToRegistry(hKey, L"IPv6DnsServer", 0, (unsigned __int8 *)this + 680);
    v14 = v8;
    if ( v8 )
    {
      if ( !(_QWORD)xmmword_180078C60 )
        goto LABEL_48;
      v9 = L"IPv6DnsServer";
      goto LABEL_24;
    }
  }
  else
  {
    RegDeleteValueW(hKey, L"IPv6DnsServer");
  }
  if ( *((_DWORD *)this + 174) )
  {
    v8 = WriteAddressToRegistry(hKey, L"IPv6DhcpServer", 0, (unsigned __int8 *)this + 696);
    v14 = v8;
    if ( v8 )
    {
      if ( !(_QWORD)xmmword_180078C60 )
        goto LABEL_48;
      v9 = L"IPv6DhcpServer";
LABEL_24:
      LOWORD(v27) = 0;
      v22 = GUID_NULL;
      LOWORD(v23) = 0;
      dwOptions[0] = v8;
      FormatRRASErrorString(
        &v27,
        L"%s: Couldn't write value %s: %d",
        L"RRasRoutingDomainConfig::PersistDialInConfig",
        v9,
        *(_QWORD *)dwOptions);
      v7 = &v22;
      if ( this != (RRasRoutingDomainConfig *)-516LL )
        v7 = (GUID *)((char *)this + 516);
      goto LABEL_10;
    }
  }
  else
  {
    RegDeleteValueW(hKey, L"IPv6DhcpServer");
  }
  if ( !*((_DWORD *)this + 178) )
  {
    RegDeleteValueW(hKey, L"TenantIDs");
    goto LABEL_48;
  }
  v8 = WriteMultiSzToRegistry(hKey, v10, (RRasRoutingDomainConfig *)((char *)this + 712));
  v14 = v8;
  if ( v8 && (_QWORD)xmmword_180078C60 )
  {
    v9 = L"TenantIDs";
    goto LABEL_24;
  }
LABEL_48:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v11 = v14;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v16);
  return v11;
}

```

## disassembly

```asm
0x18004a9dc  mov     [rsp-8+arg_8], rbx
0x18004a9e1  mov     [rsp-8+arg_10], rsi
0x18004a9e6  push    rbp
0x18004a9e7  push    rdi
0x18004a9e8  push    r14
0x18004a9ea  lea     rbp, [rsp-7E0h]
0x18004a9f2  sub     rsp, 8E0h
0x18004a9f9  mov     rax, cs:__security_cookie
0x18004aa00  xor     rax, rsp
0x18004aa03  mov     [rbp+7F0h+var_20], rax
0x18004aa0a  mov     rbx, rcx
0x18004aa0d  xor     esi, esi
0x18004aa0f  mov     [rsp+8F0h+var_8A0], esi
0x18004aa13  mov     [rsp+8F0h+hKey], rsi
0x18004aa18  mov     [rbp+7F0h+var_820], esi
0x18004aa1b  xor     edx, edx; Val
0x18004aa1d  mov     r8d, 7FCh; Size
0x18004aa23  lea     rcx, [rbp+7F0h+var_81C]; void *
0x18004aa27  call    memset_0
0x18004aa2c  mov     [rbp+7F0h+var_848], esi
0x18004aa2f  xorps   xmm0, xmm0
0x18004aa32  xor     eax, eax
0x18004aa34  movups  [rbp+7F0h+var_844], xmm0
0x18004aa38  movups  [rbp+7F0h+var_834], xmm0
0x18004aa3c  mov     [rbp+7F0h+var_824], eax
0x18004aa3f  movdqu  [rsp+8F0h+var_888], xmm0
0x18004aa45  mov     [rsp+8F0h+var_890], rsi
0x18004aa4a  xorps   xmm1, xmm1
0x18004aa4d  movdqu  [rsp+8F0h+var_878], xmm1
0x18004aa53  mov     [rbp+7F0h+var_868], rsi
0x18004aa57  mov     [rbp+7F0h+var_860], 0FFFFFFFFh
0x18004aa5e  mov     [rbp+7F0h+var_85C], esi
0x18004aa61  lea     rdi, [rbx+204h]
0x18004aa68  lea     r14, aRrasroutingdom_52; "RRasRoutingDomainConfig::PersistDialInC"...
0x18004aa6f  cmp     qword ptr cs:xmmword_180078C60+8, rsi
0x18004aa76  jz      short loc_18004AA8F
0x18004aa78  mov     qword ptr [rsp+8F0h+dwOptions], rdi; struct _GUID *
0x18004aa7d  lea     r8, [rsp+8F0h+var_8A0]; unsigned int *
0x18004aa82  mov     rdx, r14; unsigned __int16 *
0x18004aa85  lea     rcx, [rsp+8F0h+var_890]; this
0x18004aa8a  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004aa8f  mov     rcx, [rbx+338h]; hKey
0x18004aa96  lea     rdx, aDialin; "DialIn"
0x18004aa9d  test    byte ptr [rbx+218h], 9
0x18004aaa4  jnz     short loc_18004AAB1
0x18004aaa6  call    cs:__imp_RegDeleteKeyW
0x18004aaac  jmp     loc_18004AD8D
0x18004aab1  mov     [rsp+8F0h+lpdwDisposition], rsi; lpdwDisposition
0x18004aab6  lea     rax, [rsp+8F0h+hKey]
0x18004aabb  mov     [rsp+8F0h+phkResult], rax; phkResult
0x18004aac0  mov     [rsp+8F0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18004aac5  mov     [rsp+8F0h+samDesired], 20006h; samDesired
0x18004aacd  mov     [rsp+8F0h+dwOptions], esi; dwOptions
0x18004aad1  xor     r9d, r9d; lpClass
0x18004aad4  xor     r8d, r8d; Reserved
0x18004aad7  call    cs:__imp_RegCreateKeyExW
0x18004aadd  mov     [rsp+8F0h+var_8A0], eax
0x18004aae1  test    eax, eax
0x18004aae3  jz      short loc_18004AB60
0x18004aae5  cmp     qword ptr cs:xmmword_180078C60, rsi
0x18004aaec  jz      loc_18004AD8D
0x18004aaf2  lea     r9, aDialin; "DialIn"
0x18004aaf9  lea     rdx, aSRegcreatekeye_1; "%s: RegCreateKeyEx (%s) failed: %d."
0x18004ab00  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004ab07  mov     [rsp+8F0h+dwOptions], eax
0x18004ab0b  mov     word ptr [rbp+7F0h+var_848], si
0x18004ab0f  movdqu  [rbp+7F0h+var_858], xmm0
0x18004ab14  mov     word ptr [rbp+7F0h+var_820], si
0x18004ab18  mov     r8, r14
0x18004ab1b  lea     rcx, [rbp+7F0h+var_820]
0x18004ab1f  call    FormatRRASErrorString
0x18004ab24  lea     r9, [rbp+7F0h+var_858]
0x18004ab28  test    rdi, rdi
0x18004ab2b  cmovnz  r9, rdi
0x18004ab2f  lea     rax, [rbp+7F0h+var_848]
0x18004ab33  mov     qword ptr [rsp+8F0h+samDesired], rax
0x18004ab38  mov     qword ptr [rsp+8F0h+dwOptions], rsi
0x18004ab3d  lea     r8, [rbp+7F0h+var_820]
0x18004ab41  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004ab48  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004ab4f  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004ab56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab5b  jmp     loc_18004AD8D
0x18004ab60  lea     rax, [rbx+270h]
0x18004ab67  mov     r9d, 4; dwType
0x18004ab6d  mov     [rsp+8F0h+samDesired], r9d; cbData
0x18004ab72  mov     qword ptr [rsp+8F0h+dwOptions], rax; lpData
0x18004ab77  xor     r8d, r8d; Reserved
0x18004ab7a  lea     rdx, aMaxvpnconnecti; "MaxVpnConnections"
0x18004ab81  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18004ab86  call    cs:__imp_RegSetValueExW
0x18004ab8c  mov     [rsp+8F0h+var_8A0], eax
0x18004ab90  test    eax, eax
0x18004ab92  jz      short loc_18004ABB4
0x18004ab94  cmp     qword ptr cs:xmmword_180078C60, rsi
0x18004ab9b  jz      loc_18004AD8D
0x18004aba1  lea     r9, aMaxvpnconnecti; "MaxVpnConnections"
0x18004aba8  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x18004abaf  jmp     loc_18004AB00
0x18004abb4  lea     r9, [rbx+278h]; unsigned __int8 *
0x18004abbb  lea     rdx, aIpv4dnsserver; "IPv4DnsServer"
0x18004abc2  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18004abc7  cmp     [r9], esi
0x18004abca  jz      short loc_18004ABF2
0x18004abcc  mov     r8b, 1; bool
0x18004abcf  call    ?WriteAddressToRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; WriteAddressToRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18004abd4  mov     [rsp+8F0h+var_8A0], eax
0x18004abd8  test    eax, eax
0x18004abda  jz      short loc_18004ABF8
0x18004abdc  cmp     qword ptr cs:xmmword_180078C60, rsi
0x18004abe3  jz      loc_18004AD8D
0x18004abe9  lea     r9, aIpv4dnsserver; "IPv4DnsServer"
0x18004abf0  jmp     short loc_18004ABA8
0x18004abf2  call    cs:__imp_RegDeleteValueW
0x18004abf8  lea     r9, [rbx+288h]; unsigned __int8 *
0x18004abff  lea     rdx, aIpv4dhcpserver; "IPv4DhcpServer"
0x18004ac06  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18004ac0b  cmp     [r9], esi
0x18004ac0e  jz      short loc_18004AC76
0x18004ac10  mov     r8b, 1; bool
0x18004ac13  call    ?WriteAddressToRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; WriteAddressToRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18004ac18  mov     [rsp+8F0h+var_8A0], eax
0x18004ac1c  test    eax, eax
0x18004ac1e  jz      short loc_18004AC7C
0x18004ac20  cmp     qword ptr cs:xmmword_180078C60, rsi
0x18004ac27  jz      loc_18004AD8D
0x18004ac2d  lea     r9, aIpv4dhcpserver; "IPv4DhcpServer"
0x18004ac34  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004ac3b  mov     word ptr [rbp+7F0h+var_820], si
0x18004ac3f  movdqu  [rbp+7F0h+var_858], xmm0
0x18004ac44  mov     word ptr [rbp+7F0h+var_848], si
0x18004ac48  mov     [rsp+8F0h+dwOptions], eax
0x18004ac4c  mov     r8, r14
0x18004ac4f  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x18004ac56  lea     rcx, [rbp+7F0h+var_820]
0x18004ac5a  call    FormatRRASErrorString
0x18004ac5f  lea     rcx, [rbx+204h]
0x18004ac66  lea     r9, [rbp+7F0h+var_858]
0x18004ac6a  test    rcx, rcx
0x18004ac6d  cmovnz  r9, rcx
0x18004ac71  jmp     loc_18004AB2F
0x18004ac76  call    cs:__imp_RegDeleteValueW
0x18004ac7c  lea     r9, [rbx+298h]; unsigned __int8 *
0x18004ac83  lea     rdx, aIpv4netbiosser; "IPv4NetBiosServer"
0x18004ac8a  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18004ac8f  cmp     [r9], esi
0x18004ac92  jz      short loc_18004ACBD
0x18004ac94  mov     r8b, 1; bool
0x18004ac97  call    ?WriteAddressToRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; WriteAddressToRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18004ac9c  mov     [rsp+8F0h+var_8A0], eax
0x18004aca0  test    eax, eax
0x18004aca2  jz      short loc_18004ACC3
0x18004aca4  cmp     qword ptr cs:xmmword_180078C60, rsi
0x18004acab  jz      loc_18004AD8D
0x18004acb1  lea     r9, aIpv4netbiosser; "IPv4NetBiosServer"
0x18004acb8  jmp     loc_18004AC34
0x18004acbd  call    cs:__imp_RegDeleteValueW
0x18004acc3  lea     r9, [rbx+2A8h]; unsigned __int8 *
0x18004acca  lea     rdx, aIpv6dnsserver; "IPv6DnsServer"
0x18004acd1  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18004acd6  cmp     [r9], esi
0x18004acd9  jz      short loc_18004AD04
0x18004acdb  xor     r8d, r8d; bool
0x18004acde  call    ?WriteAddressToRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; WriteAddressToRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18004ace3  mov     [rsp+8F0h+var_8A0], eax
0x18004ace7  test    eax, eax
0x18004ace9  jz      short loc_18004AD0A
0x18004aceb  cmp     qword ptr cs:xmmword_180078C60, rsi
0x18004acf2  jz      loc_18004AD8D
0x18004acf8  lea     r9, aIpv6dnsserver; "IPv6DnsServer"
0x18004acff  jmp     loc_18004AC34
0x18004ad04  call    cs:__imp_RegDeleteValueW
0x18004ad0a  lea     r9, [rbx+2B8h]; unsigned __int8 *
0x18004ad11  lea     rdx, aIpv6dhcpserver; "IPv6DhcpServer"
0x18004ad18  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18004ad1d  cmp     [r9], esi
0x18004ad20  jz      short loc_18004AD47
0x18004ad22  xor     r8d, r8d; bool
0x18004ad25  call    ?WriteAddressToRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; WriteAddressToRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18004ad2a  mov     [rsp+8F0h+var_8A0], eax
0x18004ad2e  test    eax, eax
0x18004ad30  jz      short loc_18004AD4D
0x18004ad32  cmp     qword ptr cs:xmmword_180078C60, rsi
0x18004ad39  jz      short loc_18004AD8D
0x18004ad3b  lea     r9, aIpv6dhcpserver; "IPv6DhcpServer"
0x18004ad42  jmp     loc_18004AC34
0x18004ad47  call    cs:__imp_RegDeleteValueW
0x18004ad4d  lea     r8, [rbx+2C8h]; struct _MPRI_STRING_LIST *
0x18004ad54  mov     rcx, [rsp+8F0h+hKey]; HKEY
0x18004ad59  cmp     [r8], esi
0x18004ad5c  jz      short loc_18004AD80
0x18004ad5e  call    ?WriteMultiSzToRegistry@@YAKPEAUHKEY__@@PEBGPEAU_MPRI_STRING_LIST@@@Z; WriteMultiSzToRegistry(HKEY__ *,ushort const *,_MPRI_STRING_LIST *)
0x18004ad63  mov     [rsp+8F0h+var_8A0], eax
0x18004ad67  test    eax, eax
0x18004ad69  jz      short loc_18004AD8D
0x18004ad6b  cmp     qword ptr cs:xmmword_180078C60, rsi
0x18004ad72  jz      short loc_18004AD8D
0x18004ad74  lea     r9, aTenantids; "TenantIDs"
0x18004ad7b  jmp     loc_18004AC34
0x18004ad80  lea     rdx, aTenantids; "TenantIDs"
0x18004ad87  call    cs:__imp_RegDeleteValueW
0x18004ad8d  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18004ad92  test    rcx, rcx
0x18004ad95  jz      short loc_18004ADA2
0x18004ad97  call    cs:__imp_RegCloseKey
0x18004ad9d  mov     [rsp+8F0h+hKey], rsi
0x18004ada2  mov     ebx, [rsp+8F0h+var_8A0]
0x18004ada6  lea     rcx, [rsp+8F0h+var_890]; this
0x18004adab  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004adb0  mov     eax, ebx
0x18004adb2  mov     rcx, [rbp+7F0h+var_20]
0x18004adb9  xor     rcx, rsp; StackCookie
0x18004adbc  call    __security_check_cookie
0x18004adc1  lea     r11, [rsp+8F0h+var_10]
0x18004adc9  mov     rbx, [r11+28h]
0x18004adcd  mov     rsi, [r11+30h]
0x18004add1  mov     rsp, r11
0x18004add4  pop     r14
0x18004add6  pop     rdi
0x18004add7  pop     rbp
0x18004add8  retn
```
