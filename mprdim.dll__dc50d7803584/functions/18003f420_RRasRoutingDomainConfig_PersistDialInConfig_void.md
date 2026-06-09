# RRasRoutingDomainConfig::PersistDialInConfig(void)

- ea: `0x18003f420`
- end: `0x18003f81d`
- name: `?PersistDialInConfig@RRasRoutingDomainConfig@@AEAAKXZ`
- size: `1021`
- prototype: `unsigned int __fastcall(RRasRoutingDomainConfig *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003f104`
- `0x1800416fc`

## callees

- `0x18003f420`
- `0x180045018`
- `0x180045228`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `KERNEL32!RegDeleteValueW` at `0x18003f636`
- `KERNEL32!RegDeleteValueW` at `0x18003f6ba`
- `KERNEL32!RegDeleteValueW` at `0x18003f701`
- `KERNEL32!RegDeleteValueW` at `0x18003f748`
- `KERNEL32!RegDeleteValueW` at `0x18003f78b`
- `KERNEL32!RegDeleteValueW` at `0x18003f7cb`
- `KERNEL32!RegDeleteValueW` at `0x18003f636`
- `KERNEL32!RegDeleteValueW` at `0x18003f6ba`
- `KERNEL32!RegDeleteValueW` at `0x18003f701`
- `KERNEL32!RegDeleteValueW` at `0x18003f748`
- `KERNEL32!RegDeleteValueW` at `0x18003f78b`
- `KERNEL32!RegDeleteValueW` at `0x18003f7cb`
- `ADVAPI32!RegSetValueExW` at `0x18003f5ca`
- `ADVAPI32!RegSetValueExW` at `0x18003f5ca`
- `ADVAPI32!RegCloseKey` at `0x18003f7db`
- `ADVAPI32!RegCloseKey` at `0x18003f7db`
- `ADVAPI32!RegCreateKeyExW` at `0x18003f51b`
- `ADVAPI32!RegCreateKeyExW` at `0x18003f51b`
- `ADVAPI32!RegDeleteKeyW` at `0x18003f4ea`
- `ADVAPI32!RegDeleteKeyW` at `0x18003f4ea`

## string_xrefs

- `0x18003f5ec`: `%s: Couldn't write value %s: %d`
- `0x18003f693`: `%s: Couldn't write value %s: %d`
- `0x18003f53d`: `%s: RegCreateKeyEx (%s) failed: %d.`
- `0x18003f4ac`: `RRasRoutingDomainConfig::PersistDialInConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  unsigned __int16 *samDesired; // [rsp+28h] [rbp-D8h]
  unsigned int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  unsigned int v16; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v19; // [rsp+68h] [rbp-98h]
  __int128 v20; // [rsp+78h] [rbp-88h]
  __int64 v21; // [rsp+88h] [rbp-78h]
  int v22; // [rsp+90h] [rbp-70h]
  int v23; // [rsp+94h] [rbp-6Ch]
  GUID v24; // [rsp+98h] [rbp-68h] BYREF
  int v25; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v26; // [rsp+ACh] [rbp-54h]
  __int128 v27; // [rsp+BCh] [rbp-44h]
  int v28; // [rsp+CCh] [rbp-34h]
  int v29; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v30[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v16 = 0;
  hKey = 0;
  v29 = 0;
  memset_0(v30, 0, sizeof(v30));
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v19 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  v22 = -1;
  v23 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v18,
      L"RRasRoutingDomainConfig::PersistDialInConfig",
      &v16,
      v2,
      (struct _GUID *)((char *)this + 516),
      samDesired,
      lpSecurityAttributes);
  v3 = (HKEY)*((_QWORD *)this + 103);
  if ( (*((_BYTE *)this + 536) & 9) == 0 )
  {
    RegDeleteKeyW(v3, L"DialIn");
    goto LABEL_48;
  }
  v4 = RegCreateKeyExW(v3, L"DialIn", 0, 0, 0, 0x20006u, 0, &hKey, 0);
  v16 = v4;
  if ( v4 )
  {
    if ( !(_QWORD)xmmword_1800710A0 )
      goto LABEL_48;
    v5 = L"DialIn";
    v6 = L"%s: RegCreateKeyEx (%s) failed: %d.";
    goto LABEL_8;
  }
  v4 = RegSetValueExW(hKey, L"MaxVpnConnections", 0, 4u, (const BYTE *)this + 624, 4u);
  v16 = v4;
  if ( v4 )
  {
    if ( (_QWORD)xmmword_1800710A0 )
    {
      v5 = L"MaxVpnConnections";
LABEL_14:
      v6 = L"%s: Couldn't write value %s: %d";
LABEL_8:
      dwOptions[0] = v4;
      LOWORD(v25) = 0;
      v24 = GUID_NULL;
      LOWORD(v29) = 0;
      FormatRRASErrorString(&v29, v6, L"RRasRoutingDomainConfig::PersistDialInConfig", v5, *(_QWORD *)dwOptions);
      v7 = &v24;
      if ( this != (RRasRoutingDomainConfig *)-516LL )
        v7 = (GUID *)((char *)this + 516);
LABEL_10:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_1800710A0,
        &v29,
        v7,
        0,
        &v25);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  if ( *((_DWORD *)this + 158) )
  {
    v4 = WriteAddressToRegistry(hKey, L"IPv4DnsServer", 1, (unsigned __int8 *)this + 632);
    v16 = v4;
    if ( v4 )
    {
      if ( (_QWORD)xmmword_1800710A0 )
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
    v16 = v8;
    if ( v8 )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
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
    v16 = v8;
    if ( v8 )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
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
    v16 = v8;
    if ( v8 )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
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
    v16 = v8;
    if ( v8 )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
        goto LABEL_48;
      v9 = L"IPv6DhcpServer";
LABEL_24:
      LOWORD(v29) = 0;
      v24 = GUID_NULL;
      LOWORD(v25) = 0;
      dwOptions[0] = v8;
      FormatRRASErrorString(
        &v29,
        L"%s: Couldn't write value %s: %d",
        L"RRasRoutingDomainConfig::PersistDialInConfig",
        v9,
        *(_QWORD *)dwOptions);
      v7 = &v24;
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
  v16 = v8;
  if ( v8 && (_QWORD)xmmword_1800710A0 )
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
  v11 = v16;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
  return v11;
}

```

## disassembly

```asm
0x18003f420  mov     [rsp-8+arg_8], rbx
0x18003f425  mov     [rsp-8+arg_10], rsi
0x18003f42a  push    rbp
0x18003f42b  push    rdi
0x18003f42c  push    r14
0x18003f42e  lea     rbp, [rsp-7E0h]
0x18003f436  sub     rsp, 8E0h
0x18003f43d  mov     rax, cs:__security_cookie
0x18003f444  xor     rax, rsp
0x18003f447  mov     [rbp+7F0h+var_20], rax
0x18003f44e  mov     rbx, rcx
0x18003f451  xor     esi, esi
0x18003f453  mov     [rsp+8F0h+var_8A0], esi
0x18003f457  mov     [rsp+8F0h+hKey], rsi
0x18003f45c  mov     [rbp+7F0h+var_820], esi
0x18003f45f  xor     edx, edx; Val
0x18003f461  mov     r8d, 7FCh; Size
0x18003f467  lea     rcx, [rbp+7F0h+var_81C]; void *
0x18003f46b  call    memset_0
0x18003f470  mov     [rbp+7F0h+var_848], esi
0x18003f473  xorps   xmm0, xmm0
0x18003f476  xor     eax, eax
0x18003f478  movups  [rbp+7F0h+var_844], xmm0
0x18003f47c  movups  [rbp+7F0h+var_834], xmm0
0x18003f480  mov     [rbp+7F0h+var_824], eax
0x18003f483  movdqu  [rsp+8F0h+var_888], xmm0
0x18003f489  mov     [rsp+8F0h+var_890], rsi
0x18003f48e  xorps   xmm1, xmm1
0x18003f491  movdqu  [rsp+8F0h+var_878], xmm1
0x18003f497  mov     [rbp+7F0h+var_868], rsi
0x18003f49b  mov     [rbp+7F0h+var_860], 0FFFFFFFFh
0x18003f4a2  mov     [rbp+7F0h+var_85C], esi
0x18003f4a5  lea     rdi, [rbx+204h]
0x18003f4ac  lea     r14, aRrasroutingdom_53; "RRasRoutingDomainConfig::PersistDialInC"...
0x18003f4b3  cmp     qword ptr cs:xmmword_1800710A0+8, rsi
0x18003f4ba  jz      short loc_18003F4D3
0x18003f4bc  mov     qword ptr [rsp+8F0h+dwOptions], rdi; struct _GUID *
0x18003f4c1  lea     r8, [rsp+8F0h+var_8A0]; unsigned int *
0x18003f4c6  mov     rdx, r14; unsigned __int16 *
0x18003f4c9  lea     rcx, [rsp+8F0h+var_890]; this
0x18003f4ce  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003f4d3  mov     rcx, [rbx+338h]; hKey
0x18003f4da  lea     rdx, aDialin; "DialIn"
0x18003f4e1  test    byte ptr [rbx+218h], 9
0x18003f4e8  jnz     short loc_18003F4F5
0x18003f4ea  call    cs:__imp_RegDeleteKeyW
0x18003f4f0  jmp     loc_18003F7D1
0x18003f4f5  mov     [rsp+8F0h+lpdwDisposition], rsi; lpdwDisposition
0x18003f4fa  lea     rax, [rsp+8F0h+hKey]
0x18003f4ff  mov     [rsp+8F0h+phkResult], rax; phkResult
0x18003f504  mov     [rsp+8F0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18003f509  mov     [rsp+8F0h+samDesired], 20006h; samDesired
0x18003f511  mov     [rsp+8F0h+dwOptions], esi; dwOptions
0x18003f515  xor     r9d, r9d; lpClass
0x18003f518  xor     r8d, r8d; Reserved
0x18003f51b  call    cs:__imp_RegCreateKeyExW
0x18003f521  mov     [rsp+8F0h+var_8A0], eax
0x18003f525  test    eax, eax
0x18003f527  jz      short loc_18003F5A4
0x18003f529  cmp     qword ptr cs:xmmword_1800710A0, rsi
0x18003f530  jz      loc_18003F7D1
0x18003f536  lea     r9, aDialin; "DialIn"
0x18003f53d  lea     rdx, aSRegcreatekeye_1; "%s: RegCreateKeyEx (%s) failed: %d."
0x18003f544  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003f54b  mov     [rsp+8F0h+dwOptions], eax
0x18003f54f  mov     word ptr [rbp+7F0h+var_848], si
0x18003f553  movdqu  [rbp+7F0h+var_858], xmm0
0x18003f558  mov     word ptr [rbp+7F0h+var_820], si
0x18003f55c  mov     r8, r14
0x18003f55f  lea     rcx, [rbp+7F0h+var_820]
0x18003f563  call    FormatRRASErrorString
0x18003f568  lea     r9, [rbp+7F0h+var_858]
0x18003f56c  test    rdi, rdi
0x18003f56f  cmovnz  r9, rdi
0x18003f573  lea     rax, [rbp+7F0h+var_848]
0x18003f577  mov     qword ptr [rsp+8F0h+samDesired], rax
0x18003f57c  mov     qword ptr [rsp+8F0h+dwOptions], rsi
0x18003f581  lea     r8, [rbp+7F0h+var_820]
0x18003f585  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003f58c  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003f593  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003f59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f59f  jmp     loc_18003F7D1
0x18003f5a4  lea     rax, [rbx+270h]
0x18003f5ab  mov     r9d, 4; dwType
0x18003f5b1  mov     [rsp+8F0h+samDesired], r9d; cbData
0x18003f5b6  mov     qword ptr [rsp+8F0h+dwOptions], rax; lpData
0x18003f5bb  xor     r8d, r8d; Reserved
0x18003f5be  lea     rdx, aMaxvpnconnecti; "MaxVpnConnections"
0x18003f5c5  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18003f5ca  call    cs:__imp_RegSetValueExW
0x18003f5d0  mov     [rsp+8F0h+var_8A0], eax
0x18003f5d4  test    eax, eax
0x18003f5d6  jz      short loc_18003F5F8
0x18003f5d8  cmp     qword ptr cs:xmmword_1800710A0, rsi
0x18003f5df  jz      loc_18003F7D1
0x18003f5e5  lea     r9, aMaxvpnconnecti; "MaxVpnConnections"
0x18003f5ec  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x18003f5f3  jmp     loc_18003F544
0x18003f5f8  lea     r9, [rbx+278h]; unsigned __int8 *
0x18003f5ff  lea     rdx, aIpv4dnsserver; "IPv4DnsServer"
0x18003f606  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18003f60b  cmp     [r9], esi
0x18003f60e  jz      short loc_18003F636
0x18003f610  mov     r8b, 1; bool
0x18003f613  call    ?WriteAddressToRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; WriteAddressToRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18003f618  mov     [rsp+8F0h+var_8A0], eax
0x18003f61c  test    eax, eax
0x18003f61e  jz      short loc_18003F63C
0x18003f620  cmp     qword ptr cs:xmmword_1800710A0, rsi
0x18003f627  jz      loc_18003F7D1
0x18003f62d  lea     r9, aIpv4dnsserver; "IPv4DnsServer"
0x18003f634  jmp     short loc_18003F5EC
0x18003f636  call    cs:__imp_RegDeleteValueW
0x18003f63c  lea     r9, [rbx+288h]; unsigned __int8 *
0x18003f643  lea     rdx, aIpv4dhcpserver; "IPv4DhcpServer"
0x18003f64a  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18003f64f  cmp     [r9], esi
0x18003f652  jz      short loc_18003F6BA
0x18003f654  mov     r8b, 1; bool
0x18003f657  call    ?WriteAddressToRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; WriteAddressToRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18003f65c  mov     [rsp+8F0h+var_8A0], eax
0x18003f660  test    eax, eax
0x18003f662  jz      short loc_18003F6C0
0x18003f664  cmp     qword ptr cs:xmmword_1800710A0, rsi
0x18003f66b  jz      loc_18003F7D1
0x18003f671  lea     r9, aIpv4dhcpserver; "IPv4DhcpServer"
0x18003f678  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003f67f  mov     word ptr [rbp+7F0h+var_820], si
0x18003f683  movdqu  [rbp+7F0h+var_858], xmm0
0x18003f688  mov     word ptr [rbp+7F0h+var_848], si
0x18003f68c  mov     [rsp+8F0h+dwOptions], eax
0x18003f690  mov     r8, r14
0x18003f693  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x18003f69a  lea     rcx, [rbp+7F0h+var_820]
0x18003f69e  call    FormatRRASErrorString
0x18003f6a3  lea     rcx, [rbx+204h]
0x18003f6aa  lea     r9, [rbp+7F0h+var_858]
0x18003f6ae  test    rcx, rcx
0x18003f6b1  cmovnz  r9, rcx
0x18003f6b5  jmp     loc_18003F573
0x18003f6ba  call    cs:__imp_RegDeleteValueW
0x18003f6c0  lea     r9, [rbx+298h]; unsigned __int8 *
0x18003f6c7  lea     rdx, aIpv4netbiosser; "IPv4NetBiosServer"
0x18003f6ce  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18003f6d3  cmp     [r9], esi
0x18003f6d6  jz      short loc_18003F701
0x18003f6d8  mov     r8b, 1; bool
0x18003f6db  call    ?WriteAddressToRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; WriteAddressToRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18003f6e0  mov     [rsp+8F0h+var_8A0], eax
0x18003f6e4  test    eax, eax
0x18003f6e6  jz      short loc_18003F707
0x18003f6e8  cmp     qword ptr cs:xmmword_1800710A0, rsi
0x18003f6ef  jz      loc_18003F7D1
0x18003f6f5  lea     r9, aIpv4netbiosser; "IPv4NetBiosServer"
0x18003f6fc  jmp     loc_18003F678
0x18003f701  call    cs:__imp_RegDeleteValueW
0x18003f707  lea     r9, [rbx+2A8h]; unsigned __int8 *
0x18003f70e  lea     rdx, aIpv6dnsserver; "IPv6DnsServer"
0x18003f715  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18003f71a  cmp     [r9], esi
0x18003f71d  jz      short loc_18003F748
0x18003f71f  xor     r8d, r8d; bool
0x18003f722  call    ?WriteAddressToRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; WriteAddressToRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18003f727  mov     [rsp+8F0h+var_8A0], eax
0x18003f72b  test    eax, eax
0x18003f72d  jz      short loc_18003F74E
0x18003f72f  cmp     qword ptr cs:xmmword_1800710A0, rsi
0x18003f736  jz      loc_18003F7D1
0x18003f73c  lea     r9, aIpv6dnsserver; "IPv6DnsServer"
0x18003f743  jmp     loc_18003F678
0x18003f748  call    cs:__imp_RegDeleteValueW
0x18003f74e  lea     r9, [rbx+2B8h]; unsigned __int8 *
0x18003f755  lea     rdx, aIpv6dhcpserver; "IPv6DhcpServer"
0x18003f75c  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18003f761  cmp     [r9], esi
0x18003f764  jz      short loc_18003F78B
0x18003f766  xor     r8d, r8d; bool
0x18003f769  call    ?WriteAddressToRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; WriteAddressToRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18003f76e  mov     [rsp+8F0h+var_8A0], eax
0x18003f772  test    eax, eax
0x18003f774  jz      short loc_18003F791
0x18003f776  cmp     qword ptr cs:xmmword_1800710A0, rsi
0x18003f77d  jz      short loc_18003F7D1
0x18003f77f  lea     r9, aIpv6dhcpserver; "IPv6DhcpServer"
0x18003f786  jmp     loc_18003F678
0x18003f78b  call    cs:__imp_RegDeleteValueW
0x18003f791  lea     r8, [rbx+2C8h]; struct _MPRI_STRING_LIST *
0x18003f798  mov     rcx, [rsp+8F0h+hKey]; HKEY
0x18003f79d  cmp     [r8], esi
0x18003f7a0  jz      short loc_18003F7C4
0x18003f7a2  call    ?WriteMultiSzToRegistry@@YAKPEAUHKEY__@@PEBGPEAU_MPRI_STRING_LIST@@@Z; WriteMultiSzToRegistry(HKEY__ *,ushort const *,_MPRI_STRING_LIST *)
0x18003f7a7  mov     [rsp+8F0h+var_8A0], eax
0x18003f7ab  test    eax, eax
0x18003f7ad  jz      short loc_18003F7D1
0x18003f7af  cmp     qword ptr cs:xmmword_1800710A0, rsi
0x18003f7b6  jz      short loc_18003F7D1
0x18003f7b8  lea     r9, aTenantids; "TenantIDs"
0x18003f7bf  jmp     loc_18003F678
0x18003f7c4  lea     rdx, aTenantids; "TenantIDs"
0x18003f7cb  call    cs:__imp_RegDeleteValueW
0x18003f7d1  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18003f7d6  test    rcx, rcx
0x18003f7d9  jz      short loc_18003F7E6
0x18003f7db  call    cs:__imp_RegCloseKey
0x18003f7e1  mov     [rsp+8F0h+hKey], rsi
0x18003f7e6  mov     ebx, [rsp+8F0h+var_8A0]
0x18003f7ea  lea     rcx, [rsp+8F0h+var_890]; this
0x18003f7ef  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003f7f4  mov     eax, ebx
0x18003f7f6  mov     rcx, [rbp+7F0h+var_20]
0x18003f7fd  xor     rcx, rsp; StackCookie
0x18003f800  call    __security_check_cookie
0x18003f805  lea     r11, [rsp+8F0h+var_10]
0x18003f80d  mov     rbx, [r11+28h]
0x18003f811  mov     rsi, [r11+30h]
0x18003f815  mov     rsp, r11
0x18003f818  pop     r14
0x18003f81a  pop     rdi
0x18003f81b  pop     rbp
0x18003f81c  retn
```
