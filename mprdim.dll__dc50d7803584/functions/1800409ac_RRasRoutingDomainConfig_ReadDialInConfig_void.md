# RRasRoutingDomainConfig::ReadDialInConfig(void)

- ea: `0x1800409ac`
- end: `0x180040d19`
- name: `?ReadDialInConfig@RRasRoutingDomainConfig@@AEAAKXZ`
- size: `877`
- prototype: `unsigned int __fastcall(RRasRoutingDomainConfig *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18003c810`
- `0x18003fde0`

## callees

- `0x180034094`
- `0x1800409ac`
- `0x180044964`
- `0x180044d0c`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180040a9a`
- `ADVAPI32!RegOpenKeyExW` at `0x180040a9a`
- `ADVAPI32!RegCloseKey` at `0x180040cd3`
- `ADVAPI32!RegCloseKey` at `0x180040cd3`

## string_xrefs

- `0x180040ab5`: `%s: RegOpenKeyEx (%s) failed: %d.`
- `0x180040a42`: `RRasRoutingDomainConfig::ReadDialInConfig`
- `0x180040b86`: `%s: ReadAddressFromRegistry (%s) failed: %d.`
- `0x180040beb`: `%s: ReadAddressFromRegistry (%s) failed: %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasRoutingDomainConfig::ReadDialInConfig(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  LSTATUS AddressFromRegistry; // eax
  const wchar_t *v4; // rdx
  GUID *v5; // r9
  unsigned int MultiSzFromRegistry; // eax
  const unsigned __int16 *v7; // rdx
  unsigned int v8; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v11; // [rsp+28h] [rbp-D8h]
  unsigned int v12; // [rsp+30h] [rbp-D0h]
  unsigned int v13; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v15; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v16; // [rsp+58h] [rbp-A8h]
  __int128 v17; // [rsp+68h] [rbp-98h]
  __int64 v18; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+80h] [rbp-80h]
  int v20; // [rsp+84h] [rbp-7Ch]
  GUID v21; // [rsp+88h] [rbp-78h] BYREF
  int v22; // [rsp+98h] [rbp-68h] BYREF
  __int128 v23; // [rsp+9Ch] [rbp-64h]
  __int128 v24; // [rsp+ACh] [rbp-54h]
  int v25; // [rsp+BCh] [rbp-44h]
  int v26; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v27[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v13 = 0;
  hKey = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  v19 = -1;
  v20 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v15,
      L"RRasRoutingDomainConfig::ReadDialInConfig",
      &v13,
      v2,
      (struct _GUID *)((char *)this + 516),
      v11,
      v12);
  if ( (*((_BYTE *)this + 536) & 9) == 0 )
    goto LABEL_34;
  AddressFromRegistry = RegOpenKeyExW(*((HKEY *)this + 103), L"DialIn", 0, 0x20019u, &hKey);
  v13 = AddressFromRegistry;
  if ( AddressFromRegistry )
  {
    if ( !(_QWORD)xmmword_1800710A0 )
      goto LABEL_34;
    v4 = L"%s: RegOpenKeyEx (%s) failed: %d.";
    goto LABEL_7;
  }
  RegGetDword(hKey, L"MaxVpnConnections", 1, 0xFFFFFFFFLL, 100, (char *)this + 624);
  AddressFromRegistry = ReadAddressFromRegistry(hKey, L"IPv4DnsServer", 1, (unsigned __int8 *)this + 632);
  v13 = AddressFromRegistry;
  if ( !AddressFromRegistry )
  {
LABEL_15:
    MultiSzFromRegistry = ReadAddressFromRegistry(hKey, L"IPv4DhcpServer", 1, (unsigned __int8 *)this + 648);
    v13 = MultiSzFromRegistry;
    if ( MultiSzFromRegistry )
    {
      if ( MultiSzFromRegistry != 2 )
        goto LABEL_17;
      v13 = 0;
    }
    MultiSzFromRegistry = ReadAddressFromRegistry(hKey, L"IPv4NetBiosServer", 1, (unsigned __int8 *)this + 664);
    v13 = MultiSzFromRegistry;
    if ( MultiSzFromRegistry )
    {
      if ( MultiSzFromRegistry != 2 )
        goto LABEL_17;
      v13 = 0;
    }
    MultiSzFromRegistry = ReadAddressFromRegistry(hKey, L"IPv6DnsServer", 0, (unsigned __int8 *)this + 680);
    v13 = MultiSzFromRegistry;
    if ( MultiSzFromRegistry )
    {
      if ( MultiSzFromRegistry != 2 )
        goto LABEL_17;
      v13 = 0;
    }
    MultiSzFromRegistry = ReadAddressFromRegistry(hKey, L"IPv6DhcpServer", 0, (unsigned __int8 *)this + 696);
    v13 = MultiSzFromRegistry;
    if ( !MultiSzFromRegistry )
      goto LABEL_31;
    if ( MultiSzFromRegistry == 2 )
    {
      v13 = 0;
LABEL_31:
      MultiSzFromRegistry = ReadMultiSzFromRegistry(hKey, v7, (RRasRoutingDomainConfig *)((char *)this + 712));
      v13 = MultiSzFromRegistry;
      if ( !MultiSzFromRegistry )
        goto LABEL_34;
      if ( MultiSzFromRegistry == 2 )
      {
        v13 = 0;
        goto LABEL_34;
      }
    }
LABEL_17:
    if ( (_QWORD)xmmword_1800710A0 )
    {
      LOWORD(v26) = 0;
      v21 = GUID_NULL;
      LOWORD(v22) = 0;
      LODWORD(phkResult) = MultiSzFromRegistry;
      FormatRRASErrorString(
        &v26,
        L"%s: ReadAddressFromRegistry (%s) failed: %d.",
        L"RRasRoutingDomainConfig::ReadDialInConfig",
        L"DialIn",
        phkResult);
      v5 = &v21;
      if ( this != (RRasRoutingDomainConfig *)-516LL )
        v5 = (GUID *)((char *)this + 516);
      goto LABEL_9;
    }
    goto LABEL_34;
  }
  if ( AddressFromRegistry == 2 )
  {
    v13 = 0;
    goto LABEL_15;
  }
  if ( (_QWORD)xmmword_1800710A0 )
  {
    v4 = L"%s: ReadAddressFromRegistry (%s) failed: %d.";
LABEL_7:
    LODWORD(phkResult) = AddressFromRegistry;
    LOWORD(v22) = 0;
    v21 = GUID_NULL;
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, v4, L"RRasRoutingDomainConfig::ReadDialInConfig", L"DialIn", phkResult);
    v5 = &v21;
    if ( this != (RRasRoutingDomainConfig *)-516LL )
      v5 = (GUID *)((char *)this + 516);
LABEL_9:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_1800710A0,
      &v26,
      v5,
      0,
      &v22);
  }
LABEL_34:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v8 = v13;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v15);
  return v8;
}

```

## disassembly

```asm
0x1800409ac  mov     [rsp-8+arg_8], rbx
0x1800409b1  mov     [rsp-8+arg_10], rsi
0x1800409b6  push    rbp
0x1800409b7  push    rdi
0x1800409b8  push    r12
0x1800409ba  push    r14
0x1800409bc  push    r15
0x1800409be  lea     rbp, [rsp-7D0h]
0x1800409c6  sub     rsp, 8D0h
0x1800409cd  mov     rax, cs:__security_cookie
0x1800409d4  xor     rax, rsp
0x1800409d7  mov     [rbp+7F0h+var_30], rax
0x1800409de  mov     rdi, rcx
0x1800409e1  xor     r14d, r14d
0x1800409e4  mov     [rsp+8F0h+var_8B0], r14d
0x1800409e9  mov     [rsp+8F0h+hKey], r14
0x1800409ee  mov     [rbp+7F0h+var_830], r14d
0x1800409f2  xor     edx, edx; Val
0x1800409f4  mov     r8d, 7FCh; Size
0x1800409fa  lea     rcx, [rbp+7F0h+var_82C]; void *
0x1800409fe  call    memset_0
0x180040a03  mov     [rbp+7F0h+var_858], r14d
0x180040a07  xorps   xmm0, xmm0
0x180040a0a  xor     eax, eax
0x180040a0c  movups  [rbp+7F0h+var_854], xmm0
0x180040a10  movups  [rbp+7F0h+var_844], xmm0
0x180040a14  mov     [rbp+7F0h+var_834], eax
0x180040a17  movdqu  [rsp+8F0h+var_898], xmm0
0x180040a1d  mov     [rsp+8F0h+var_8A0], r14
0x180040a22  xorps   xmm1, xmm1
0x180040a25  movdqu  [rsp+8F0h+var_888], xmm1
0x180040a2b  mov     [rsp+8F0h+var_878], r14
0x180040a30  mov     [rbp+7F0h+var_870], 0FFFFFFFFh
0x180040a37  mov     [rbp+7F0h+var_86C], r14d
0x180040a3b  lea     rsi, [rdi+204h]
0x180040a42  lea     r12, aRrasroutingdom_38; "RRasRoutingDomainConfig::ReadDialInConf"...
0x180040a49  cmp     qword ptr cs:xmmword_1800710A0+8, r14
0x180040a50  jz      short loc_180040A69
0x180040a52  mov     [rsp+8F0h+phkResult], rsi; struct _GUID *
0x180040a57  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x180040a5c  mov     rdx, r12; unsigned __int16 *
0x180040a5f  lea     rcx, [rsp+8F0h+var_8A0]; this
0x180040a64  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180040a69  test    byte ptr [rdi+218h], 9
0x180040a70  jz      loc_180040CC9
0x180040a76  lea     rax, [rsp+8F0h+hKey]
0x180040a7b  mov     [rsp+8F0h+phkResult], rax; phkResult
0x180040a80  mov     r9d, 20019h; samDesired
0x180040a86  xor     r8d, r8d; ulOptions
0x180040a89  lea     r15, aDialin; "DialIn"
0x180040a90  mov     rdx, r15; lpSubKey
0x180040a93  mov     rcx, [rdi+338h]; hKey
0x180040a9a  call    cs:__imp_RegOpenKeyExW
0x180040aa0  mov     [rsp+8F0h+var_8B0], eax
0x180040aa4  test    eax, eax
0x180040aa6  jz      short loc_180040B21
0x180040aa8  cmp     qword ptr cs:xmmword_1800710A0, r14
0x180040aaf  jz      loc_180040CC9
0x180040ab5  lea     rdx, aSRegopenkeyexS_0; "%s: RegOpenKeyEx (%s) failed: %d."
0x180040abc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180040ac3  mov     r8, r12
0x180040ac6  mov     r9, r15
0x180040ac9  mov     dword ptr [rsp+8F0h+phkResult], eax
0x180040acd  mov     word ptr [rbp+7F0h+var_858], r14w
0x180040ad2  movdqu  [rbp+7F0h+var_868], xmm0
0x180040ad7  mov     word ptr [rbp+7F0h+var_830], r14w
0x180040adc  lea     rcx, [rbp+7F0h+var_830]
0x180040ae0  call    FormatRRASErrorString
0x180040ae5  lea     r9, [rbp+7F0h+var_868]
0x180040ae9  test    rsi, rsi
0x180040aec  cmovnz  r9, rsi
0x180040af0  lea     rax, [rbp+7F0h+var_858]
0x180040af4  mov     [rsp+8F0h+var_8C8], rax
0x180040af9  mov     [rsp+8F0h+phkResult], r14
0x180040afe  lea     r8, [rbp+7F0h+var_830]
0x180040b02  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180040b09  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180040b10  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180040b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b1c  jmp     loc_180040CC9
0x180040b21  lea     rbx, [rdi+270h]
0x180040b28  mov     [rsp+8F0h+var_8C8], rbx
0x180040b2d  mov     dword ptr [rsp+8F0h+phkResult], 64h ; 'd'
0x180040b35  or      r9d, 0FFFFFFFFh
0x180040b39  mov     r8d, 1
0x180040b3f  lea     rdx, aMaxvpnconnecti; "MaxVpnConnections"
0x180040b46  mov     rcx, [rsp+8F0h+hKey]
0x180040b4b  call    RegGetDword
0x180040b50  lea     r9, [rbx+8]; unsigned __int8 *
0x180040b54  mov     r8b, 1; bool
0x180040b57  lea     rdx, aIpv4dnsserver; "IPv4DnsServer"
0x180040b5e  mov     rcx, [rsp+8F0h+hKey]; hkey
0x180040b63  call    ?ReadAddressFromRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; ReadAddressFromRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x180040b68  mov     [rsp+8F0h+var_8B0], eax
0x180040b6c  mov     ebx, 2
0x180040b71  test    eax, eax
0x180040b73  jz      short loc_180040B97
0x180040b75  cmp     eax, ebx
0x180040b77  jz      short loc_180040B92
0x180040b79  cmp     qword ptr cs:xmmword_1800710A0, r14
0x180040b80  jz      loc_180040CC9
0x180040b86  lea     rdx, aSReadaddressfr; "%s: ReadAddressFromRegistry (%s) failed"...
0x180040b8d  jmp     loc_180040ABC
0x180040b92  mov     [rsp+8F0h+var_8B0], r14d
0x180040b97  lea     r9, [rdi+288h]; unsigned __int8 *
0x180040b9e  mov     r8b, 1; bool
0x180040ba1  lea     rdx, aIpv4dhcpserver; "IPv4DhcpServer"
0x180040ba8  mov     rcx, [rsp+8F0h+hKey]; hkey
0x180040bad  call    ?ReadAddressFromRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; ReadAddressFromRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x180040bb2  mov     [rsp+8F0h+var_8B0], eax
0x180040bb6  test    eax, eax
0x180040bb8  jz      short loc_180040C17
0x180040bba  cmp     eax, ebx
0x180040bbc  jz      short loc_180040C12
0x180040bbe  cmp     qword ptr cs:xmmword_1800710A0, r14
0x180040bc5  jz      loc_180040CC9
0x180040bcb  mov     word ptr [rbp+7F0h+var_830], r14w
0x180040bd0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180040bd7  movdqu  [rbp+7F0h+var_868], xmm0
0x180040bdc  mov     word ptr [rbp+7F0h+var_858], r14w
0x180040be1  mov     dword ptr [rsp+8F0h+phkResult], eax
0x180040be5  mov     r9, r15
0x180040be8  mov     r8, r12
0x180040beb  lea     rdx, aSReadaddressfr; "%s: ReadAddressFromRegistry (%s) failed"...
0x180040bf2  lea     rcx, [rbp+7F0h+var_830]
0x180040bf6  call    FormatRRASErrorString
0x180040bfb  lea     rcx, [rdi+204h]
0x180040c02  lea     r9, [rbp+7F0h+var_868]
0x180040c06  test    rcx, rcx
0x180040c09  cmovnz  r9, rcx
0x180040c0d  jmp     loc_180040AF0
0x180040c12  mov     [rsp+8F0h+var_8B0], r14d
0x180040c17  lea     r9, [rdi+298h]; unsigned __int8 *
0x180040c1e  mov     r8b, 1; bool
0x180040c21  lea     rdx, aIpv4netbiosser; "IPv4NetBiosServer"
0x180040c28  mov     rcx, [rsp+8F0h+hKey]; hkey
0x180040c2d  call    ?ReadAddressFromRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; ReadAddressFromRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x180040c32  mov     [rsp+8F0h+var_8B0], eax
0x180040c36  test    eax, eax
0x180040c38  jz      short loc_180040C43
0x180040c3a  cmp     eax, ebx
0x180040c3c  jnz     short loc_180040BBE
0x180040c3e  mov     [rsp+8F0h+var_8B0], r14d
0x180040c43  lea     r9, [rdi+2A8h]; unsigned __int8 *
0x180040c4a  xor     r8d, r8d; bool
0x180040c4d  lea     rdx, aIpv6dnsserver; "IPv6DnsServer"
0x180040c54  mov     rcx, [rsp+8F0h+hKey]; hkey
0x180040c59  call    ?ReadAddressFromRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; ReadAddressFromRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x180040c5e  mov     [rsp+8F0h+var_8B0], eax
0x180040c62  test    eax, eax
0x180040c64  jz      short loc_180040C73
0x180040c66  cmp     eax, ebx
0x180040c68  jnz     loc_180040BBE
0x180040c6e  mov     [rsp+8F0h+var_8B0], r14d
0x180040c73  lea     r9, [rdi+2B8h]; unsigned __int8 *
0x180040c7a  xor     r8d, r8d; bool
0x180040c7d  lea     rdx, aIpv6dhcpserver; "IPv6DhcpServer"
0x180040c84  mov     rcx, [rsp+8F0h+hKey]; hkey
0x180040c89  call    ?ReadAddressFromRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z; ReadAddressFromRegistry(HKEY__ *,ushort const *,bool,uchar *)
0x180040c8e  mov     [rsp+8F0h+var_8B0], eax
0x180040c92  test    eax, eax
0x180040c94  jz      short loc_180040CA3
0x180040c96  cmp     eax, ebx
0x180040c98  jnz     loc_180040BBE
0x180040c9e  mov     [rsp+8F0h+var_8B0], r14d
0x180040ca3  lea     r8, [rdi+2C8h]; struct _MPRI_STRING_LIST *
0x180040caa  mov     rcx, [rsp+8F0h+hKey]; hkey
0x180040caf  call    ?ReadMultiSzFromRegistry@@YAKPEAUHKEY__@@PEBGPEAU_MPRI_STRING_LIST@@@Z; ReadMultiSzFromRegistry(HKEY__ *,ushort const *,_MPRI_STRING_LIST *)
0x180040cb4  mov     [rsp+8F0h+var_8B0], eax
0x180040cb8  test    eax, eax
0x180040cba  jz      short loc_180040CC9
0x180040cbc  cmp     eax, ebx
0x180040cbe  jnz     loc_180040BBE
0x180040cc4  mov     [rsp+8F0h+var_8B0], r14d
0x180040cc9  mov     rcx, [rsp+8F0h+hKey]; hKey
0x180040cce  test    rcx, rcx
0x180040cd1  jz      short loc_180040CDE
0x180040cd3  call    cs:__imp_RegCloseKey
0x180040cd9  mov     [rsp+8F0h+hKey], r14
0x180040cde  mov     ebx, [rsp+8F0h+var_8B0]
0x180040ce2  lea     rcx, [rsp+8F0h+var_8A0]; this
0x180040ce7  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180040cec  mov     eax, ebx
0x180040cee  mov     rcx, [rbp+7F0h+var_30]
0x180040cf5  xor     rcx, rsp; StackCookie
0x180040cf8  call    __security_check_cookie
0x180040cfd  lea     r11, [rsp+8F0h+var_20]
0x180040d05  mov     rbx, [r11+38h]
0x180040d09  mov     rsi, [r11+40h]
0x180040d0d  mov     rsp, r11
0x180040d10  pop     r15
0x180040d12  pop     r14
0x180040d14  pop     r12
0x180040d16  pop     rdi
0x180040d17  pop     rbp
0x180040d18  retn
```
