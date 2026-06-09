# RRasRoutingDomainConfig::ReadDialInConfig(void)

- ea: `0x18004bf80`
- end: `0x18004c2ed`
- name: `?ReadDialInConfig@RRasRoutingDomainConfig@@AEAAKXZ`
- size: `877`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180047ff4`
- `0x18004b3ac`

## callees

- `0x180030498`
- `0x18004bf80`
- `0x180050004`
- `0x1800503d8`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c2a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c2a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c06e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c06e`

## string_xrefs

- `0x18004c089`: `%s: RegOpenKeyEx (%s) failed: %d.`
- `0x18004c016`: `RRasRoutingDomainConfig::ReadDialInConfig`
- `0x18004c15a`: `%s: ReadAddressFromRegistry (%s) failed: %d.`
- `0x18004c1bf`: `%s: ReadAddressFromRegistry (%s) failed: %d.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::ReadDialInConfig(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int AddressFromRegistry; // eax
  const wchar_t *v4; // rdx
  GUID *v5; // r9
  unsigned int MultiSzFromRegistry; // eax
  const unsigned __int16 *v7; // rdx
  unsigned int v8; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int v11; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v14; // [rsp+58h] [rbp-A8h]
  __int128 v15; // [rsp+68h] [rbp-98h]
  __int64 v16; // [rsp+78h] [rbp-88h]
  int v17; // [rsp+80h] [rbp-80h]
  int v18; // [rsp+84h] [rbp-7Ch]
  GUID v19; // [rsp+88h] [rbp-78h] BYREF
  int v20; // [rsp+98h] [rbp-68h] BYREF
  __int128 v21; // [rsp+9Ch] [rbp-64h]
  __int128 v22; // [rsp+ACh] [rbp-54h]
  int v23; // [rsp+BCh] [rbp-44h]
  int v24; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v25[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v11 = 0;
  hKey = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v17 = -1;
  v18 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v13,
      L"RRasRoutingDomainConfig::ReadDialInConfig",
      &v11,
      v2,
      (struct _GUID *)((char *)this + 516));
  if ( (*((_BYTE *)this + 536) & 9) == 0 )
    goto LABEL_34;
  AddressFromRegistry = RegOpenKeyExW(*((HKEY *)this + 103), L"DialIn", 0, 0x20019u, &hKey);
  v11 = AddressFromRegistry;
  if ( AddressFromRegistry )
  {
    if ( !(_QWORD)xmmword_180078C60 )
      goto LABEL_34;
    v4 = L"%s: RegOpenKeyEx (%s) failed: %d.";
    goto LABEL_7;
  }
  RegGetDword(hKey, L"MaxVpnConnections", 1, 0xFFFFFFFFLL, 100, (char *)this + 624);
  AddressFromRegistry = ReadAddressFromRegistry(hKey, L"IPv4DnsServer", 1, (unsigned __int8 *)this + 632);
  v11 = AddressFromRegistry;
  if ( !AddressFromRegistry )
  {
LABEL_15:
    MultiSzFromRegistry = ReadAddressFromRegistry(hKey, L"IPv4DhcpServer", 1, (unsigned __int8 *)this + 648);
    v11 = MultiSzFromRegistry;
    if ( MultiSzFromRegistry )
    {
      if ( MultiSzFromRegistry != 2 )
        goto LABEL_17;
      v11 = 0;
    }
    MultiSzFromRegistry = ReadAddressFromRegistry(hKey, L"IPv4NetBiosServer", 1, (unsigned __int8 *)this + 664);
    v11 = MultiSzFromRegistry;
    if ( MultiSzFromRegistry )
    {
      if ( MultiSzFromRegistry != 2 )
        goto LABEL_17;
      v11 = 0;
    }
    MultiSzFromRegistry = ReadAddressFromRegistry(hKey, L"IPv6DnsServer", 0, (unsigned __int8 *)this + 680);
    v11 = MultiSzFromRegistry;
    if ( MultiSzFromRegistry )
    {
      if ( MultiSzFromRegistry != 2 )
        goto LABEL_17;
      v11 = 0;
    }
    MultiSzFromRegistry = ReadAddressFromRegistry(hKey, L"IPv6DhcpServer", 0, (unsigned __int8 *)this + 696);
    v11 = MultiSzFromRegistry;
    if ( !MultiSzFromRegistry )
      goto LABEL_31;
    if ( MultiSzFromRegistry == 2 )
    {
      v11 = 0;
LABEL_31:
      MultiSzFromRegistry = ReadMultiSzFromRegistry(hKey, v7, (RRasRoutingDomainConfig *)((char *)this + 712));
      v11 = MultiSzFromRegistry;
      if ( !MultiSzFromRegistry )
        goto LABEL_34;
      if ( MultiSzFromRegistry == 2 )
      {
        v11 = 0;
        goto LABEL_34;
      }
    }
LABEL_17:
    if ( (_QWORD)xmmword_180078C60 )
    {
      LOWORD(v24) = 0;
      v19 = GUID_NULL;
      LOWORD(v20) = 0;
      LODWORD(phkResult) = MultiSzFromRegistry;
      FormatRRASErrorString(
        &v24,
        L"%s: ReadAddressFromRegistry (%s) failed: %d.",
        L"RRasRoutingDomainConfig::ReadDialInConfig",
        L"DialIn",
        phkResult);
      v5 = &v19;
      if ( this != (RRasRoutingDomainConfig *)-516LL )
        v5 = (GUID *)((char *)this + 516);
      goto LABEL_9;
    }
    goto LABEL_34;
  }
  if ( AddressFromRegistry == 2 )
  {
    v11 = 0;
    goto LABEL_15;
  }
  if ( (_QWORD)xmmword_180078C60 )
  {
    v4 = L"%s: ReadAddressFromRegistry (%s) failed: %d.";
LABEL_7:
    LODWORD(phkResult) = AddressFromRegistry;
    LOWORD(v20) = 0;
    v19 = GUID_NULL;
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, v4, L"RRasRoutingDomainConfig::ReadDialInConfig", L"DialIn", phkResult);
    v5 = &v19;
    if ( this != (RRasRoutingDomainConfig *)-516LL )
      v5 = (GUID *)((char *)this + 516);
LABEL_9:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C60,
      &v24,
      v5,
      0,
      &v20);
  }
LABEL_34:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v8 = v11;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v13);
  return v8;
}

```

## disassembly

```asm
0x18004bf80  mov     [rsp-8+arg_8], rbx
0x18004bf85  mov     [rsp-8+arg_10], rsi
0x18004bf8a  push    rbp
0x18004bf8b  push    rdi
0x18004bf8c  push    r12
0x18004bf8e  push    r14
0x18004bf90  push    r15
0x18004bf92  lea     rbp, [rsp-7D0h]
0x18004bf9a  sub     rsp, 8D0h
0x18004bfa1  mov     rax, cs:__security_cookie
0x18004bfa8  xor     rax, rsp
0x18004bfab  mov     [rbp+7F0h+var_30], rax
0x18004bfb2  mov     rdi, rcx
0x18004bfb5  xor     r14d, r14d
0x18004bfb8  mov     [rsp+8F0h+var_8B0], r14d
0x18004bfbd  mov     [rsp+8F0h+hKey], r14
0x18004bfc2  mov     [rbp+7F0h+var_830], r14d
0x18004bfc6  xor     edx, edx; Val
0x18004bfc8  mov     r8d, 7FCh; Size
0x18004bfce  lea     rcx, [rbp+7F0h+var_82C]; void *
0x18004bfd2  call    memset_0
0x18004bfd7  mov     [rbp+7F0h+var_858], r14d
0x18004bfdb  xorps   xmm0, xmm0
0x18004bfde  xor     eax, eax
0x18004bfe0  movups  [rbp+7F0h+var_854], xmm0
0x18004bfe4  movups  [rbp+7F0h+var_844], xmm0
0x18004bfe8  mov     [rbp+7F0h+var_834], eax
0x18004bfeb  movdqu  [rsp+8F0h+var_898], xmm0
0x18004bff1  mov     [rsp+8F0h+var_8A0], r14
0x18004bff6  xorps   xmm1, xmm1
0x18004bff9  movdqu  [rsp+8F0h+var_888], xmm1
0x18004bfff  mov     [rsp+8F0h+var_878], r14
0x18004c004  mov     [rbp+7F0h+var_870], 0FFFFFFFFh
0x18004c00b  mov     [rbp+7F0h+var_86C], r14d
0x18004c00f  lea     rsi, [rdi+204h]
0x18004c016  lea     r12, aRrasroutingdom_37; "RRasRoutingDomainConfig::ReadDialInConf"...
0x18004c01d  cmp     qword ptr cs:xmmword_180078C60+8, r14
0x18004c024  jz      short loc_18004C03D
0x18004c026  mov     [rsp+8F0h+phkResult], rsi; struct _GUID *
0x18004c02b  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x18004c030  mov     rdx, r12; unsigned __int16 *
0x18004c033  lea     rcx, [rsp+8F0h+var_8A0]; this
0x18004c038  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004c03d  test    byte ptr [rdi+218h], 9
0x18004c044  jz      loc_18004C29D
0x18004c04a  lea     rax, [rsp+8F0h+hKey]
0x18004c04f  mov     [rsp+8F0h+phkResult], rax; phkResult
0x18004c054  mov     r9d, 20019h; samDesired
0x18004c05a  xor     r8d, r8d; ulOptions
0x18004c05d  lea     r15, aDialin; "DialIn"
0x18004c064  mov     rdx, r15; lpSubKey
0x18004c067  mov     rcx, [rdi+338h]; hKey
0x18004c06e  call    cs:__imp_RegOpenKeyExW
0x18004c074  mov     [rsp+8F0h+var_8B0], eax
0x18004c078  test    eax, eax
0x18004c07a  jz      short loc_18004C0F5
0x18004c07c  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004c083  jz      loc_18004C29D
0x18004c089  lea     rdx, aSRegopenkeyexS_0; "%s: RegOpenKeyEx (%s) failed: %d."
0x18004c090  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004c097  mov     r8, r12
0x18004c09a  mov     r9, r15
0x18004c09d  mov     dword ptr [rsp+8F0h+phkResult], eax
0x18004c0a1  mov     word ptr [rbp+7F0h+var_858], r14w
0x18004c0a6  movdqu  [rbp+7F0h+var_868], xmm0
0x18004c0ab  mov     word ptr [rbp+7F0h+var_830], r14w
0x18004c0b0  lea     rcx, [rbp+7F0h+var_830]
0x18004c0b4  call    FormatRRASErrorString
0x18004c0b9  lea     r9, [rbp+7F0h+var_868]
0x18004c0bd  test    rsi, rsi
0x18004c0c0  cmovnz  r9, rsi
0x18004c0c4  lea     rax, [rbp+7F0h+var_858]
0x18004c0c8  mov     [rsp+8F0h+var_8C8], rax
0x18004c0cd  mov     [rsp+8F0h+phkResult], r14
0x18004c0d2  lea     r8, [rbp+7F0h+var_830]
0x18004c0d6  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004c0dd  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004c0e4  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004c0eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0f0  jmp     loc_18004C29D
0x18004c0f5  lea     rbx, [rdi+270h]
0x18004c0fc  mov     [rsp+8F0h+var_8C8], rbx
0x18004c101  mov     dword ptr [rsp+8F0h+phkResult], 64h ; 'd'
0x18004c109  or      r9d, 0FFFFFFFFh
0x18004c10d  mov     r8d, 1
0x18004c113  lea     rdx, aMaxvpnconnecti; "MaxVpnConnections"
0x18004c11a  mov     rcx, [rsp+8F0h+hKey]
0x18004c11f  call    RegGetDword
0x18004c124  lea     r9, [rbx+8]; unsigned __int8 *
0x18004c128  mov     r8b, 1; bool
0x18004c12b  lea     rdx, aIpv4dnsserver; "IPv4DnsServer"
0x18004c132  mov     rcx, [rsp+8F0h+hKey]; hkey
0x18004c137  call    ?ReadAddressFromRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; ReadAddressFromRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18004c13c  mov     [rsp+8F0h+var_8B0], eax
0x18004c140  mov     ebx, 2
0x18004c145  test    eax, eax
0x18004c147  jz      short loc_18004C16B
0x18004c149  cmp     eax, ebx
0x18004c14b  jz      short loc_18004C166
0x18004c14d  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004c154  jz      loc_18004C29D
0x18004c15a  lea     rdx, aSReadaddressfr; "%s: ReadAddressFromRegistry (%s) failed"...
0x18004c161  jmp     loc_18004C090
0x18004c166  mov     [rsp+8F0h+var_8B0], r14d
0x18004c16b  lea     r9, [rdi+288h]; unsigned __int8 *
0x18004c172  mov     r8b, 1; bool
0x18004c175  lea     rdx, aIpv4dhcpserver; "IPv4DhcpServer"
0x18004c17c  mov     rcx, [rsp+8F0h+hKey]; hkey
0x18004c181  call    ?ReadAddressFromRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; ReadAddressFromRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18004c186  mov     [rsp+8F0h+var_8B0], eax
0x18004c18a  test    eax, eax
0x18004c18c  jz      short loc_18004C1EB
0x18004c18e  cmp     eax, ebx
0x18004c190  jz      short loc_18004C1E6
0x18004c192  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004c199  jz      loc_18004C29D
0x18004c19f  mov     word ptr [rbp+7F0h+var_830], r14w
0x18004c1a4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004c1ab  movdqu  [rbp+7F0h+var_868], xmm0
0x18004c1b0  mov     word ptr [rbp+7F0h+var_858], r14w
0x18004c1b5  mov     dword ptr [rsp+8F0h+phkResult], eax
0x18004c1b9  mov     r9, r15
0x18004c1bc  mov     r8, r12
0x18004c1bf  lea     rdx, aSReadaddressfr; "%s: ReadAddressFromRegistry (%s) failed"...
0x18004c1c6  lea     rcx, [rbp+7F0h+var_830]
0x18004c1ca  call    FormatRRASErrorString
0x18004c1cf  lea     rcx, [rdi+204h]
0x18004c1d6  lea     r9, [rbp+7F0h+var_868]
0x18004c1da  test    rcx, rcx
0x18004c1dd  cmovnz  r9, rcx
0x18004c1e1  jmp     loc_18004C0C4
0x18004c1e6  mov     [rsp+8F0h+var_8B0], r14d
0x18004c1eb  lea     r9, [rdi+298h]; unsigned __int8 *
0x18004c1f2  mov     r8b, 1; bool
0x18004c1f5  lea     rdx, aIpv4netbiosser; "IPv4NetBiosServer"
0x18004c1fc  mov     rcx, [rsp+8F0h+hKey]; hkey
0x18004c201  call    ?ReadAddressFromRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; ReadAddressFromRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18004c206  mov     [rsp+8F0h+var_8B0], eax
0x18004c20a  test    eax, eax
0x18004c20c  jz      short loc_18004C217
0x18004c20e  cmp     eax, ebx
0x18004c210  jnz     short loc_18004C192
0x18004c212  mov     [rsp+8F0h+var_8B0], r14d
0x18004c217  lea     r9, [rdi+2A8h]; unsigned __int8 *
0x18004c21e  xor     r8d, r8d; bool
0x18004c221  lea     rdx, aIpv6dnsserver; "IPv6DnsServer"
0x18004c228  mov     rcx, [rsp+8F0h+hKey]; hkey
0x18004c22d  call    ?ReadAddressFromRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; ReadAddressFromRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18004c232  mov     [rsp+8F0h+var_8B0], eax
0x18004c236  test    eax, eax
0x18004c238  jz      short loc_18004C247
0x18004c23a  cmp     eax, ebx
0x18004c23c  jnz     loc_18004C192
0x18004c242  mov     [rsp+8F0h+var_8B0], r14d
0x18004c247  lea     r9, [rdi+2B8h]; unsigned __int8 *
0x18004c24e  xor     r8d, r8d; bool
0x18004c251  lea     rdx, aIpv6dhcpserver; "IPv6DhcpServer"
0x18004c258  mov     rcx, [rsp+8F0h+hKey]; hkey
0x18004c25d  call    ?ReadAddressFromRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; ReadAddressFromRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x18004c262  mov     [rsp+8F0h+var_8B0], eax
0x18004c266  test    eax, eax
0x18004c268  jz      short loc_18004C277
0x18004c26a  cmp     eax, ebx
0x18004c26c  jnz     loc_18004C192
0x18004c272  mov     [rsp+8F0h+var_8B0], r14d
0x18004c277  lea     r8, [rdi+2C8h]; struct _MPRI_STRING_LIST *
0x18004c27e  mov     rcx, [rsp+8F0h+hKey]; hkey
0x18004c283  call    ?ReadMultiSzFromRegistry@@YAKPEAUHKEY__@@PEBGPEAU_MPRI_STRING_LIST@@@Z; ReadMultiSzFromRegistry(HKEY__ *,ushort const *,_MPRI_STRING_LIST *)
0x18004c288  mov     [rsp+8F0h+var_8B0], eax
0x18004c28c  test    eax, eax
0x18004c28e  jz      short loc_18004C29D
0x18004c290  cmp     eax, ebx
0x18004c292  jnz     loc_18004C192
0x18004c298  mov     [rsp+8F0h+var_8B0], r14d
0x18004c29d  mov     rcx, [rsp+8F0h+hKey]; hKey
0x18004c2a2  test    rcx, rcx
0x18004c2a5  jz      short loc_18004C2B2
0x18004c2a7  call    cs:__imp_RegCloseKey
0x18004c2ad  mov     [rsp+8F0h+hKey], r14
0x18004c2b2  mov     ebx, [rsp+8F0h+var_8B0]
0x18004c2b6  lea     rcx, [rsp+8F0h+var_8A0]; this
0x18004c2bb  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004c2c0  mov     eax, ebx
0x18004c2c2  mov     rcx, [rbp+7F0h+var_30]
0x18004c2c9  xor     rcx, rsp; StackCookie
0x18004c2cc  call    __security_check_cookie
0x18004c2d1  lea     r11, [rsp+8F0h+var_20]
0x18004c2d9  mov     rbx, [r11+38h]
0x18004c2dd  mov     rsi, [r11+40h]
0x18004c2e1  mov     rsp, r11
0x18004c2e4  pop     r15
0x18004c2e6  pop     r14
0x18004c2e8  pop     r12
0x18004c2ea  pop     rdi
0x18004c2eb  pop     rbp
0x18004c2ec  retn
```
