# RRasRoutingDomainConfig::PersistIpv4AddrPool(void)

- ea: `0x18003f824`
- end: `0x18003fc30`
- name: `?PersistIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKXZ`
- size: `1036`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003f104`
- `0x1800416fc`

## callees

- `0x18003f824`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!_itow` at `0x18003fa23`
- `msvcrt!_itow` at `0x18003fa80`
- `msvcrt!_itow` at `0x18003fa23`
- `msvcrt!_itow` at `0x18003fa80`
- `KERNEL32!RegDeleteKeyExW` at `0x18003fa07`
- `KERNEL32!RegDeleteKeyExW` at `0x18003fa07`
- `ADVAPI32!RegOpenKeyExW` at `0x18003fa45`
- `ADVAPI32!RegOpenKeyExW` at `0x18003fa45`
- `ADVAPI32!RegSetValueExW` at `0x18003fb25`
- `ADVAPI32!RegSetValueExW` at `0x18003fb7a`
- `ADVAPI32!RegSetValueExW` at `0x18003fb25`
- `ADVAPI32!RegSetValueExW` at `0x18003fb7a`
- `ADVAPI32!RegCloseKey` at `0x18003f9a7`
- `ADVAPI32!RegCloseKey` at `0x18003f9ed`
- `ADVAPI32!RegCloseKey` at `0x18003fa90`
- `ADVAPI32!RegCloseKey` at `0x18003fc19`
- `ADVAPI32!RegCloseKey` at `0x18003f9a7`
- `ADVAPI32!RegCloseKey` at `0x18003f9ed`
- `ADVAPI32!RegCloseKey` at `0x18003fa90`
- `ADVAPI32!RegCloseKey` at `0x18003fc19`
- `ADVAPI32!RegCreateKeyExW` at `0x18003f90d`
- `ADVAPI32!RegCreateKeyExW` at `0x18003facb`
- `ADVAPI32!RegCreateKeyExW` at `0x18003f90d`
- `ADVAPI32!RegCreateKeyExW` at `0x18003facb`

## string_xrefs

- `0x18003fb9e`: `%s: Couldn't write value %s: %d`
- `0x18003f952`: `%s: RegCreateKeyEx (%s) failed: %d.`
- `0x18003f8c7`: `RRasRoutingDomainConfig::PersistIpv4AddrPool`
- `0x18003f94b`: `RRasRoutingDomainConfig::PersistIpv4AddrPool`
- `0x18003fbbf`: `RRasRoutingDomainConfig::PersistIpv4AddrPool`
- `0x18003faea`: `%s: RegCreateKeyEx (%ws) failed: %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasRoutingDomainConfig::PersistIpv4AddrPool(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  WCHAR *v5; // r9
  int v7; // ebx
  int i; // ecx
  unsigned int j; // edi
  LSTATUS v10; // eax
  wchar_t *v11; // r9
  const wchar_t *v12; // rdx
  WCHAR *v13; // r9
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *samDesired; // [rsp+28h] [rbp-D8h]
  unsigned int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  unsigned int v18; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  __int128 v22; // [rsp+70h] [rbp-90h]
  __int128 v23; // [rsp+80h] [rbp-80h]
  __int64 v24; // [rsp+90h] [rbp-70h]
  int v25; // [rsp+98h] [rbp-68h]
  int v26; // [rsp+9Ch] [rbp-64h]
  WCHAR SubKey[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v28; // [rsp+B0h] [rbp-50h]
  int v29; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v30; // [rsp+C4h] [rbp-3Ch]
  __int128 v31; // [rsp+D4h] [rbp-2Ch]
  int v32; // [rsp+E4h] [rbp-1Ch]
  wchar_t Buffer[8]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v34; // [rsp+F8h] [rbp-8h]
  int v35; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v36[2044]; // [rsp+114h] [rbp+14h] BYREF

  v18 = 0;
  hKey = 0;
  phkResult = 0;
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v22 = 0;
  v21 = 0;
  v23 = 0;
  v24 = 0;
  v25 = -1;
  v26 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v21,
      L"RRasRoutingDomainConfig::PersistIpv4AddrPool",
      &v18,
      v2,
      (struct _GUID *)((char *)this + 516),
      samDesired,
      lpSecurityAttributes);
  v3 = RegCreateKeyExW(*((HKEY *)this + 103), L"Ipv4AddrPool", 0, 0, 0, 0x20006u, 0, &hKey, 0);
  v4 = v3;
  v18 = v3;
  if ( !v3 )
  {
    v7 = 0;
    for ( i = 0; ; i = v7 )
    {
      *(_OWORD *)SubKey = 0;
      v28 = 0;
      _itow(i, SubKey, 10);
      v18 = RegOpenKeyExW(hKey, SubKey, 0, 0x20006u, &phkResult);
      if ( v18 )
        break;
      RegCloseKey(phkResult);
      phkResult = 0;
      RegDeleteKeyExW(hKey, SubKey, 0, 0);
      ++v7;
    }
    v4 = 0;
    v18 = 0;
    for ( j = 0; ; ++j )
    {
      if ( j >= *((_DWORD *)this + 147) )
        goto LABEL_8;
      *(_OWORD *)Buffer = 0;
      v34 = 0;
      _itow(j, Buffer, 10);
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      v10 = RegCreateKeyExW(hKey, Buffer, 0, 0, 0, 0x20006u, 0, &phkResult, 0);
      v18 = v10;
      if ( v10 )
        break;
      v10 = RegSetValueExW(phkResult, L"From", 0, 4u, (const BYTE *)(*((_QWORD *)this + 74) + 8LL * j), 4u);
      v18 = v10;
      if ( v10 )
      {
        if ( (_QWORD)xmmword_1800710A0 )
        {
          v11 = (wchar_t *)L"From";
          goto LABEL_27;
        }
        goto LABEL_31;
      }
      v10 = RegSetValueExW(phkResult, L"To", 0, 4u, (const BYTE *)(*((_QWORD *)this + 74) + 4LL + 8LL * j), 4u);
      v4 = v10;
      v18 = v10;
      if ( v10 )
      {
        if ( (_QWORD)xmmword_1800710A0 )
        {
          v11 = (wchar_t *)L"To";
LABEL_27:
          v12 = L"%s: Couldn't write value %s: %d";
LABEL_28:
          dwOptionsa[0] = v10;
          LOWORD(v35) = 0;
          *(GUID *)SubKey = GUID_NULL;
          LOWORD(v29) = 0;
          FormatRRASErrorString(&v35, v12, L"RRasRoutingDomainConfig::PersistIpv4AddrPool", v11, *(_QWORD *)dwOptionsa);
          v13 = SubKey;
          if ( this != (RRasRoutingDomainConfig *)-516LL )
            v13 = (WCHAR *)((char *)this + 516);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, WCHAR *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_1800710A0,
            &v35,
            v13,
            0,
            &v29);
        }
LABEL_31:
        v4 = 0;
        v18 = 0;
        continue;
      }
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
        v4 = v18;
      }
    }
    if ( (_QWORD)xmmword_1800710A0 )
    {
      v11 = Buffer;
      v12 = L"%s: RegCreateKeyEx (%ws) failed: %d.";
      goto LABEL_28;
    }
    goto LABEL_31;
  }
  if ( (_QWORD)xmmword_1800710A0 )
  {
    LOWORD(v35) = 0;
    *(GUID *)SubKey = GUID_NULL;
    LOWORD(v29) = 0;
    dwOptions[0] = v3;
    FormatRRASErrorString(
      &v35,
      L"%s: RegCreateKeyEx (%s) failed: %d.",
      L"RRasRoutingDomainConfig::PersistIpv4AddrPool",
      L"Ipv4",
      *(_QWORD *)dwOptions);
    v5 = SubKey;
    if ( this != (RRasRoutingDomainConfig *)-516LL )
      v5 = (WCHAR *)((char *)this + 516);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, WCHAR *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_1800710A0,
      &v35,
      v5,
      0,
      &v29);
    v4 = v18;
  }
LABEL_8:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v4 = v18;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v21);
  return v4;
}

```

## disassembly

```asm
0x18003f824  push    rbp
0x18003f826  push    rbx
0x18003f827  push    rsi
0x18003f828  push    rdi
0x18003f829  push    r14
0x18003f82b  push    r15
0x18003f82d  lea     rbp, [rsp-828h]
0x18003f835  sub     rsp, 928h
0x18003f83c  mov     rax, cs:__security_cookie
0x18003f843  xor     rax, rsp
0x18003f846  mov     [rbp+850h+var_40], rax
0x18003f84d  mov     rsi, rcx
0x18003f850  xor     r15d, r15d
0x18003f853  mov     [rsp+950h+var_900], r15d
0x18003f858  mov     [rsp+950h+hKey], r15
0x18003f85d  mov     [rsp+950h+var_8F8], r15
0x18003f862  mov     [rbp+850h+var_840], r15d
0x18003f866  xor     edx, edx; Val
0x18003f868  mov     r8d, 7FCh; Size
0x18003f86e  lea     rcx, [rbp+850h+var_83C]; void *
0x18003f872  call    memset_0
0x18003f877  mov     [rbp+850h+var_890], r15d
0x18003f87b  xorps   xmm0, xmm0
0x18003f87e  xor     eax, eax
0x18003f880  movups  [rbp+850h+var_88C], xmm0
0x18003f884  movups  [rbp+850h+var_87C], xmm0
0x18003f888  mov     [rbp+850h+var_86C], eax
0x18003f88b  movdqu  [rsp+950h+var_8E0], xmm0
0x18003f891  mov     [rsp+950h+var_8E8], r15
0x18003f896  xorps   xmm1, xmm1
0x18003f899  movdqu  [rbp+850h+var_8D0], xmm1
0x18003f89e  mov     [rbp+850h+var_8C0], r15
0x18003f8a2  mov     [rbp+850h+var_8B8], 0FFFFFFFFh
0x18003f8a9  mov     [rbp+850h+var_8B4], r15d
0x18003f8ad  lea     r14, [rsi+204h]
0x18003f8b4  cmp     qword ptr cs:xmmword_1800710A0+8, r15
0x18003f8bb  jz      short loc_18003F8D8
0x18003f8bd  mov     qword ptr [rsp+950h+dwOptions], r14; struct _GUID *
0x18003f8c2  lea     r8, [rsp+950h+var_900]; unsigned int *
0x18003f8c7  lea     rdx, aRrasroutingdom_13; "RRasRoutingDomainConfig::PersistIpv4Add"...
0x18003f8ce  lea     rcx, [rsp+950h+var_8E8]; this
0x18003f8d3  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003f8d8  mov     [rsp+950h+lpdwDisposition], r15; lpdwDisposition
0x18003f8dd  lea     rax, [rsp+950h+hKey]
0x18003f8e2  mov     [rsp+950h+phkResult], rax; phkResult
0x18003f8e7  mov     [rsp+950h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18003f8ec  mov     [rsp+950h+samDesired], 20006h; samDesired
0x18003f8f4  mov     [rsp+950h+dwOptions], r15d; dwOptions
0x18003f8f9  xor     r9d, r9d; lpClass
0x18003f8fc  xor     r8d, r8d; Reserved
0x18003f8ff  lea     rdx, aIpv4addrpool; "Ipv4AddrPool"
0x18003f906  mov     rcx, [rsi+338h]; hKey
0x18003f90d  call    cs:__imp_RegCreateKeyExW
0x18003f913  mov     ebx, eax
0x18003f915  mov     [rsp+950h+var_900], eax
0x18003f919  test    eax, eax
0x18003f91b  jz      loc_18003F9DC
0x18003f921  cmp     qword ptr cs:xmmword_1800710A0, r15
0x18003f928  jz      short loc_18003F99D
0x18003f92a  mov     word ptr [rbp+850h+var_840], r15w
0x18003f92f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003f936  movdqu  xmmword ptr [rbp+850h+SubKey], xmm0
0x18003f93b  mov     word ptr [rbp+850h+var_890], r15w
0x18003f940  mov     [rsp+950h+dwOptions], eax
0x18003f944  lea     r9, aIpv4; "Ipv4"
0x18003f94b  lea     r8, aRrasroutingdom_13; "RRasRoutingDomainConfig::PersistIpv4Add"...
0x18003f952  lea     rdx, aSRegcreatekeye_1; "%s: RegCreateKeyEx (%s) failed: %d."
0x18003f959  lea     rcx, [rbp+850h+var_840]
0x18003f95d  call    FormatRRASErrorString
0x18003f962  lea     r9, [rbp+850h+SubKey]
0x18003f966  test    r14, r14
0x18003f969  cmovnz  r9, r14
0x18003f96d  lea     rax, [rbp+850h+var_890]
0x18003f971  mov     qword ptr [rsp+950h+samDesired], rax
0x18003f976  mov     qword ptr [rsp+950h+dwOptions], r15
0x18003f97b  lea     r8, [rbp+850h+var_840]
0x18003f97f  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003f986  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003f98d  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003f994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f999  mov     ebx, [rsp+950h+var_900]
0x18003f99d  mov     rcx, [rsp+950h+hKey]; hKey
0x18003f9a2  test    rcx, rcx
0x18003f9a5  jz      short loc_18003F9B1
0x18003f9a7  call    cs:__imp_RegCloseKey
0x18003f9ad  mov     ebx, [rsp+950h+var_900]
0x18003f9b1  lea     rcx, [rsp+950h+var_8E8]; this
0x18003f9b6  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003f9bb  mov     eax, ebx
0x18003f9bd  mov     rcx, [rbp+850h+var_40]
0x18003f9c4  xor     rcx, rsp; StackCookie
0x18003f9c7  call    __security_check_cookie
0x18003f9cc  add     rsp, 928h
0x18003f9d3  pop     r15
0x18003f9d5  pop     r14
0x18003f9d7  pop     rdi
0x18003f9d8  pop     rsi
0x18003f9d9  pop     rbx
0x18003f9da  pop     rbp
0x18003f9db  retn
0x18003f9dc  mov     ebx, r15d
0x18003f9df  mov     edi, 0Ah
0x18003f9e4  xor     ecx, ecx
0x18003f9e6  jmp     short loc_18003FA11
0x18003f9e8  mov     rcx, [rsp+950h+var_8F8]; hKey
0x18003f9ed  call    cs:__imp_RegCloseKey
0x18003f9f3  mov     [rsp+950h+var_8F8], r15
0x18003f9f8  xor     r9d, r9d; Reserved
0x18003f9fb  xor     r8d, r8d; samDesired
0x18003f9fe  lea     rdx, [rbp+850h+SubKey]; lpSubKey
0x18003fa02  mov     rcx, [rsp+950h+hKey]; hKey
0x18003fa07  call    cs:__imp_RegDeleteKeyExW
0x18003fa0d  inc     ebx
0x18003fa0f  mov     ecx, ebx; Value
0x18003fa11  xorps   xmm0, xmm0
0x18003fa14  movups  xmmword ptr [rbp+850h+SubKey], xmm0
0x18003fa18  movups  [rbp+850h+var_8A0], xmm0
0x18003fa1c  mov     r8d, edi; Radix
0x18003fa1f  lea     rdx, [rbp+850h+SubKey]; Buffer
0x18003fa23  call    cs:__imp__itow
0x18003fa29  lea     rax, [rsp+950h+var_8F8]
0x18003fa2e  mov     qword ptr [rsp+950h+dwOptions], rax; phkResult
0x18003fa33  mov     r9d, 20006h; samDesired
0x18003fa39  xor     r8d, r8d; ulOptions
0x18003fa3c  lea     rdx, [rbp+850h+SubKey]; lpSubKey
0x18003fa40  mov     rcx, [rsp+950h+hKey]; hKey
0x18003fa45  call    cs:__imp_RegOpenKeyExW
0x18003fa4b  test    eax, eax
0x18003fa4d  mov     [rsp+950h+var_900], eax
0x18003fa51  jz      short loc_18003F9E8
0x18003fa53  mov     ebx, r15d
0x18003fa56  mov     [rsp+950h+var_900], ebx
0x18003fa5a  mov     edi, r15d
0x18003fa5d  cmp     edi, [rsi+24Ch]
0x18003fa63  jnb     loc_18003F99D
0x18003fa69  xorps   xmm0, xmm0
0x18003fa6c  movups  xmmword ptr [rbp+850h+Buffer], xmm0
0x18003fa70  movups  [rbp+850h+var_858], xmm0
0x18003fa74  mov     r8d, 0Ah; Radix
0x18003fa7a  lea     rdx, [rbp+850h+Buffer]; Buffer
0x18003fa7e  mov     ecx, edi; Value
0x18003fa80  call    cs:__imp__itow
0x18003fa86  mov     rcx, [rsp+950h+var_8F8]; hKey
0x18003fa8b  test    rcx, rcx
0x18003fa8e  jz      short loc_18003FA9B
0x18003fa90  call    cs:__imp_RegCloseKey
0x18003fa96  mov     [rsp+950h+var_8F8], r15
0x18003fa9b  mov     [rsp+950h+lpdwDisposition], r15; lpdwDisposition
0x18003faa0  lea     rax, [rsp+950h+var_8F8]
0x18003faa5  mov     [rsp+950h+phkResult], rax; phkResult
0x18003faaa  mov     [rsp+950h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18003faaf  mov     [rsp+950h+samDesired], 20006h; samDesired
0x18003fab7  mov     [rsp+950h+dwOptions], r15d; dwOptions
0x18003fabc  xor     r9d, r9d; lpClass
0x18003fabf  xor     r8d, r8d; Reserved
0x18003fac2  lea     rdx, [rbp+850h+Buffer]; lpSubKey
0x18003fac6  mov     rcx, [rsp+950h+hKey]; hKey
0x18003facb  call    cs:__imp_RegCreateKeyExW
0x18003fad1  mov     [rsp+950h+var_900], eax
0x18003fad5  test    eax, eax
0x18003fad7  jz      short loc_18003FAF6
0x18003fad9  cmp     qword ptr cs:xmmword_1800710A0, r15
0x18003fae0  jz      loc_18003FC06
0x18003fae6  lea     r9, [rbp+850h+Buffer]
0x18003faea  lea     rdx, aSRegcreatekeye_0; "%s: RegCreateKeyEx (%ws) failed: %d."
0x18003faf1  jmp     loc_18003FBA5
0x18003faf6  mov     ebx, edi
0x18003faf8  mov     rax, [rsi+250h]
0x18003faff  lea     rcx, [rax+rbx*8]
0x18003fb03  mov     [rsp+950h+samDesired], 4; cbData
0x18003fb0b  mov     qword ptr [rsp+950h+dwOptions], rcx; lpData
0x18003fb10  mov     r9d, 4; dwType
0x18003fb16  xor     r8d, r8d; Reserved
0x18003fb19  lea     rdx, aFrom; "From"
0x18003fb20  mov     rcx, [rsp+950h+var_8F8]; hKey
0x18003fb25  call    cs:__imp_RegSetValueExW
0x18003fb2b  mov     [rsp+950h+var_900], eax
0x18003fb2f  test    eax, eax
0x18003fb31  jz      short loc_18003FB49
0x18003fb33  cmp     qword ptr cs:xmmword_1800710A0, r15
0x18003fb3a  jz      loc_18003FC06
0x18003fb40  lea     r9, aFrom; "From"
0x18003fb47  jmp     short loc_18003FB9E
0x18003fb49  mov     rcx, [rsi+250h]
0x18003fb50  add     rcx, 4
0x18003fb54  lea     rcx, [rcx+rbx*8]
0x18003fb58  mov     [rsp+950h+samDesired], 4; cbData
0x18003fb60  mov     qword ptr [rsp+950h+dwOptions], rcx; lpData
0x18003fb65  mov     r9d, 4; dwType
0x18003fb6b  xor     r8d, r8d; Reserved
0x18003fb6e  lea     rdx, aTo; "To"
0x18003fb75  mov     rcx, [rsp+950h+var_8F8]; hKey
0x18003fb7a  call    cs:__imp_RegSetValueExW
0x18003fb80  mov     ebx, eax
0x18003fb82  mov     [rsp+950h+var_900], eax
0x18003fb86  test    eax, eax
0x18003fb88  jz      loc_18003FC0F
0x18003fb8e  cmp     qword ptr cs:xmmword_1800710A0, r15
0x18003fb95  jz      short loc_18003FC06
0x18003fb97  lea     r9, aTo; "To"
0x18003fb9e  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x18003fba5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003fbac  mov     [rsp+950h+dwOptions], eax
0x18003fbb0  mov     word ptr [rbp+850h+var_840], r15w
0x18003fbb5  movdqu  xmmword ptr [rbp+850h+SubKey], xmm0
0x18003fbba  mov     word ptr [rbp+850h+var_890], r15w
0x18003fbbf  lea     r8, aRrasroutingdom_13; "RRasRoutingDomainConfig::PersistIpv4Add"...
0x18003fbc6  lea     rcx, [rbp+850h+var_840]
0x18003fbca  call    FormatRRASErrorString
0x18003fbcf  lea     rax, [rbp+850h+var_890]
0x18003fbd3  mov     qword ptr [rsp+950h+samDesired], rax
0x18003fbd8  lea     r9, [rbp+850h+SubKey]
0x18003fbdc  test    r14, r14
0x18003fbdf  mov     qword ptr [rsp+950h+dwOptions], r15
0x18003fbe4  cmovnz  r9, r14
0x18003fbe8  lea     r8, [rbp+850h+var_840]
0x18003fbec  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003fbf3  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003fbfa  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003fc01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc06  mov     ebx, r15d
0x18003fc09  mov     [rsp+950h+var_900], ebx
0x18003fc0d  jmp     short loc_18003FC28
0x18003fc0f  mov     rcx, [rsp+950h+var_8F8]; hKey
0x18003fc14  test    rcx, rcx
0x18003fc17  jz      short loc_18003FC28
0x18003fc19  call    cs:__imp_RegCloseKey
0x18003fc1f  mov     [rsp+950h+var_8F8], r15
0x18003fc24  mov     ebx, [rsp+950h+var_900]
0x18003fc28  inc     edi
0x18003fc2a  jmp     loc_18003FA5D
```
