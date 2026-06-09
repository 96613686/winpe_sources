# RRasRoutingDomainConfig::PopulateFromRegistry(void)

- ea: `0x18003fde0`
- end: `0x1800400bc`
- name: `?PopulateFromRegistry@RRasRoutingDomainConfig@@QEAAKXZ`
- size: `732`
- prototype: `unsigned int __fastcall(RRasRoutingDomainConfig *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18003de9c`

## callees

- `0x180037308`
- `0x18003fde0`
- `0x1800400c4`
- `0x1800406cc`
- `0x1800408a8`
- `0x1800409ac`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18003fed7`
- `ADVAPI32!RegQueryValueExW` at `0x18004003d`
- `ADVAPI32!RegQueryValueExW` at `0x18003fed7`
- `ADVAPI32!RegQueryValueExW` at `0x18004003d`

## string_xrefs

- `0x18003fe7b`: `RRasRoutingDomainConfig::PopulateFromRegistry`
- `0x18003fef4`: `%s:  Failed to read the routing domain name: %d.`
- `0x18003ff86`: `%s:  ReadQoSPoliciesFromRegistry failed: %d.`
- `0x1800400af`: `%s:  Failed to read the router type: %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RRasRoutingDomainConfig::PopulateFromRegistry(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int QoSPoliciesFromRegistry; // eax
  unsigned int v4; // ebx
  const wchar_t *v5; // rdx
  GUID *v6; // r9
  _DWORD *v7; // rsi
  unsigned __int16 *lpcbData; // [rsp+28h] [rbp-D8h]
  unsigned int v10; // [rsp+30h] [rbp-D0h]
  unsigned int v11; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+58h] [rbp-A8h]
  __int128 v16; // [rsp+68h] [rbp-98h]
  __int64 v17; // [rsp+78h] [rbp-88h]
  int v18; // [rsp+80h] [rbp-80h]
  int v19; // [rsp+84h] [rbp-7Ch]
  GUID v20; // [rsp+88h] [rbp-78h] BYREF
  int v21; // [rsp+98h] [rbp-68h] BYREF
  __int128 v22; // [rsp+9Ch] [rbp-64h]
  __int128 v23; // [rsp+ACh] [rbp-54h]
  int v24; // [rsp+BCh] [rbp-44h]
  int v25; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v26[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v11 = 0;
  cbData = 0;
  Type = 0;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v15 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v18 = -1;
  v19 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v14,
      L"RRasRoutingDomainConfig::PopulateFromRegistry",
      &v11,
      v2,
      (struct _GUID *)((char *)this + 516),
      lpcbData,
      v10);
  cbData = 514;
  Type = 1;
  QoSPoliciesFromRegistry = RegQueryValueExW(
                              *((HKEY *)this + 103),
                              L"RoutingDomainName",
                              0,
                              &Type,
                              (LPBYTE)this,
                              &cbData);
  v4 = QoSPoliciesFromRegistry;
  v11 = QoSPoliciesFromRegistry;
  if ( QoSPoliciesFromRegistry )
  {
    if ( (_QWORD)xmmword_1800710A0 )
    {
      v5 = L"%s:  Failed to read the routing domain name: %d.";
LABEL_6:
      LOWORD(v25) = 0;
      v20 = GUID_NULL;
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v25, v5, L"RRasRoutingDomainConfig::PopulateFromRegistry", QoSPoliciesFromRegistry);
      v6 = &v20;
      if ( this != (RRasRoutingDomainConfig *)-516LL )
        v6 = (GUID *)((char *)this + 516);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_1800710A0,
        &v25,
        v6,
        0,
        &v21);
      goto LABEL_25;
    }
  }
  else
  {
    QoSPoliciesFromRegistry = ReadQoSPoliciesFromRegistry(*((HKEY *)this + 103));
    v4 = QoSPoliciesFromRegistry;
    v11 = QoSPoliciesFromRegistry;
    if ( QoSPoliciesFromRegistry )
    {
      if ( (_QWORD)xmmword_1800710A0 )
      {
        v5 = L"%s:  ReadQoSPoliciesFromRegistry failed: %d.";
        goto LABEL_6;
      }
    }
    else
    {
      RRasRoutingDomainConfig::ReadAccountingConfig(this);
      QoSPoliciesFromRegistry = RRasRoutingDomainConfig::PopulateIpv4AddrPool(this);
      v4 = QoSPoliciesFromRegistry;
      v11 = QoSPoliciesFromRegistry;
      if ( !QoSPoliciesFromRegistry || QoSPoliciesFromRegistry == 1168 )
      {
        v11 = 0;
        QoSPoliciesFromRegistry = RRasRoutingDomainConfig::PopulateIpv6AddrPool(this);
        v4 = QoSPoliciesFromRegistry;
        v11 = QoSPoliciesFromRegistry;
        if ( !QoSPoliciesFromRegistry || QoSPoliciesFromRegistry == 1168 )
        {
          v11 = 0;
          cbData = 4;
          Type = 4;
          v7 = (_DWORD *)((char *)this + 536);
          QoSPoliciesFromRegistry = RegQueryValueExW(
                                      *((HKEY *)this + 103),
                                      L"RouterType",
                                      0,
                                      &Type,
                                      (LPBYTE)this + 536,
                                      &cbData);
          v4 = QoSPoliciesFromRegistry;
          v11 = QoSPoliciesFromRegistry;
          if ( QoSPoliciesFromRegistry )
          {
            *v7 = 0;
            if ( QoSPoliciesFromRegistry != 1168 )
            {
              if ( !(_QWORD)xmmword_1800710A0 )
                goto LABEL_26;
              v5 = L"%s:  Failed to read the router type: %d.";
              goto LABEL_6;
            }
            v4 = 0;
            v11 = 0;
          }
          if ( (*(_BYTE *)v7 & 9) != 0 )
          {
            RRasRoutingDomainConfig::ReadDialInConfig(this);
LABEL_25:
            v4 = v11;
          }
        }
        else if ( (_QWORD)xmmword_1800710A0 )
        {
          v5 = L"%s:  PopulateIpv6AddrPool failed: %d.";
          goto LABEL_6;
        }
      }
      else if ( (_QWORD)xmmword_1800710A0 )
      {
        v5 = L"%s:  PopulateIpv4AddrPool failed: %d.";
        goto LABEL_6;
      }
    }
  }
LABEL_26:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v14);
  return v4;
}

```

## disassembly

```asm
0x18003fde0  mov     [rsp-8+arg_8], rbx
0x18003fde5  mov     [rsp-8+arg_10], rsi
0x18003fdea  push    rbp
0x18003fdeb  push    rdi
0x18003fdec  push    r13
0x18003fdee  push    r14
0x18003fdf0  push    r15
0x18003fdf2  lea     rbp, [rsp-7D0h]
0x18003fdfa  sub     rsp, 8D0h
0x18003fe01  mov     rax, cs:__security_cookie
0x18003fe08  xor     rax, rsp
0x18003fe0b  mov     [rbp+7F0h+var_30], rax
0x18003fe12  mov     rdi, rcx
0x18003fe15  xor     r15d, r15d
0x18003fe18  mov     [rsp+8F0h+var_8B0], r15d
0x18003fe1d  mov     [rsp+8F0h+cbData], r15d
0x18003fe22  mov     [rsp+8F0h+Type], r15d
0x18003fe27  mov     [rbp+7F0h+var_830], r15d
0x18003fe2b  xor     edx, edx; Val
0x18003fe2d  mov     r8d, 7FCh; Size
0x18003fe33  lea     rcx, [rbp+7F0h+var_82C]; void *
0x18003fe37  call    memset_0
0x18003fe3c  mov     [rbp+7F0h+var_858], r15d
0x18003fe40  xorps   xmm0, xmm0
0x18003fe43  xor     eax, eax
0x18003fe45  movups  [rbp+7F0h+var_854], xmm0
0x18003fe49  movups  [rbp+7F0h+var_844], xmm0
0x18003fe4d  mov     [rbp+7F0h+var_834], eax
0x18003fe50  movdqu  [rsp+8F0h+var_898], xmm0
0x18003fe56  mov     [rsp+8F0h+var_8A0], r15
0x18003fe5b  xorps   xmm1, xmm1
0x18003fe5e  movdqu  [rsp+8F0h+var_888], xmm1
0x18003fe64  mov     [rsp+8F0h+var_878], r15
0x18003fe69  mov     [rbp+7F0h+var_870], 0FFFFFFFFh
0x18003fe70  mov     [rbp+7F0h+var_86C], r15d
0x18003fe74  lea     r14, [rdi+204h]
0x18003fe7b  lea     r13, aRrasroutingdom_52; "RRasRoutingDomainConfig::PopulateFromRe"...
0x18003fe82  cmp     qword ptr cs:xmmword_1800710A0+8, r15
0x18003fe89  jz      short loc_18003FEA2
0x18003fe8b  mov     [rsp+8F0h+lpData], r14; struct _GUID *
0x18003fe90  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x18003fe95  mov     rdx, r13; unsigned __int16 *
0x18003fe98  lea     rcx, [rsp+8F0h+var_8A0]; this
0x18003fe9d  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003fea2  mov     [rsp+8F0h+cbData], 202h
0x18003feaa  mov     [rsp+8F0h+Type], 1
0x18003feb2  lea     rax, [rsp+8F0h+cbData]
0x18003feb7  mov     [rsp+8F0h+lpcbData], rax; lpcbData
0x18003febc  mov     [rsp+8F0h+lpData], rdi; lpData
0x18003fec1  lea     r9, [rsp+8F0h+Type]; lpType
0x18003fec6  xor     r8d, r8d; lpReserved
0x18003fec9  lea     rdx, aRoutingdomainn; "RoutingDomainName"
0x18003fed0  mov     rcx, [rdi+338h]; hKey
0x18003fed7  call    cs:__imp_RegQueryValueExW
0x18003fedd  mov     ebx, eax
0x18003fedf  mov     [rsp+8F0h+var_8B0], eax
0x18003fee3  test    eax, eax
0x18003fee5  jz      short loc_18003FF5C
0x18003fee7  cmp     qword ptr cs:xmmword_1800710A0, r15
0x18003feee  jz      loc_18004006F
0x18003fef4  lea     rdx, aSFailedToReadT; "%s:  Failed to read the routing domain "...
0x18003fefb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003ff02  mov     word ptr [rbp+7F0h+var_830], r15w
0x18003ff07  movdqu  [rbp+7F0h+var_868], xmm0
0x18003ff0c  mov     word ptr [rbp+7F0h+var_858], r15w
0x18003ff11  mov     r9d, eax
0x18003ff14  mov     r8, r13
0x18003ff17  lea     rcx, [rbp+7F0h+var_830]
0x18003ff1b  call    FormatRRASErrorString
0x18003ff20  lea     r9, [rbp+7F0h+var_868]
0x18003ff24  test    r14, r14
0x18003ff27  cmovnz  r9, r14
0x18003ff2b  lea     rax, [rbp+7F0h+var_858]
0x18003ff2f  mov     [rsp+8F0h+lpcbData], rax
0x18003ff34  mov     [rsp+8F0h+lpData], r15
0x18003ff39  lea     r8, [rbp+7F0h+var_830]
0x18003ff3d  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003ff44  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003ff4b  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003ff52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff57  jmp     loc_18004006B
0x18003ff5c  lea     rdx, [rdi+220h]
0x18003ff63  mov     rcx, [rdi+338h]; hKey
0x18003ff6a  call    ReadQoSPoliciesFromRegistry
0x18003ff6f  mov     ebx, eax
0x18003ff71  mov     [rsp+8F0h+var_8B0], eax
0x18003ff75  test    eax, eax
0x18003ff77  jz      short loc_18003FF92
0x18003ff79  cmp     qword ptr cs:xmmword_1800710A0, r15
0x18003ff80  jz      loc_18004006F
0x18003ff86  lea     rdx, aSReadqospolici; "%s:  ReadQoSPoliciesFromRegistry failed"...
0x18003ff8d  jmp     loc_18003FEFB
0x18003ff92  mov     rcx, rdi; this
0x18003ff95  call    ?ReadAccountingConfig@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::ReadAccountingConfig(void)
0x18003ff9a  mov     rcx, rdi; this
0x18003ff9d  call    ?PopulateIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PopulateIpv4AddrPool(void)
0x18003ffa2  mov     ebx, eax
0x18003ffa4  mov     [rsp+8F0h+var_8B0], eax
0x18003ffa8  test    eax, eax
0x18003ffaa  jz      short loc_18003FFCC
0x18003ffac  cmp     eax, 490h
0x18003ffb1  jz      short loc_18003FFCC
0x18003ffb3  cmp     qword ptr cs:xmmword_1800710A0, r15
0x18003ffba  jz      loc_18004006F
0x18003ffc0  lea     rdx, aSPopulateipv4a; "%s:  PopulateIpv4AddrPool failed: %d."
0x18003ffc7  jmp     loc_18003FEFB
0x18003ffcc  mov     [rsp+8F0h+var_8B0], r15d
0x18003ffd1  mov     rcx, rdi; this
0x18003ffd4  call    ?PopulateIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PopulateIpv6AddrPool(void)
0x18003ffd9  mov     ebx, eax
0x18003ffdb  mov     [rsp+8F0h+var_8B0], eax
0x18003ffdf  test    eax, eax
0x18003ffe1  jz      short loc_18003FFFF
0x18003ffe3  cmp     eax, 490h
0x18003ffe8  jz      short loc_18003FFFF
0x18003ffea  cmp     qword ptr cs:xmmword_1800710A0, r15
0x18003fff1  jz      short loc_18004006F
0x18003fff3  lea     rdx, aSPopulateipv6a; "%s:  PopulateIpv6AddrPool failed: %d."
0x18003fffa  jmp     loc_18003FEFB
0x18003ffff  mov     [rsp+8F0h+var_8B0], r15d
0x180040004  mov     eax, 4
0x180040009  mov     [rsp+8F0h+cbData], eax
0x18004000d  mov     [rsp+8F0h+Type], eax
0x180040011  lea     rsi, [rdi+218h]
0x180040018  lea     rax, [rsp+8F0h+cbData]
0x18004001d  mov     [rsp+8F0h+lpcbData], rax; lpcbData
0x180040022  mov     [rsp+8F0h+lpData], rsi; lpData
0x180040027  lea     r9, [rsp+8F0h+Type]; lpType
0x18004002c  xor     r8d, r8d; lpReserved
0x18004002f  lea     rdx, aRoutertype; "RouterType"
0x180040036  mov     rcx, [rdi+338h]; hKey
0x18004003d  call    cs:__imp_RegQueryValueExW
0x180040043  mov     ebx, eax
0x180040045  mov     [rsp+8F0h+var_8B0], eax
0x180040049  test    eax, eax
0x18004004b  jz      short loc_18004005E
0x18004004d  mov     [rsi], r15d
0x180040050  cmp     eax, 490h
0x180040055  jnz     short loc_1800400A6
0x180040057  mov     ebx, r15d
0x18004005a  mov     [rsp+8F0h+var_8B0], ebx
0x18004005e  test    byte ptr [rsi], 9
0x180040061  jz      short loc_18004006F
0x180040063  mov     rcx, rdi; this
0x180040066  call    ?ReadDialInConfig@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::ReadDialInConfig(void)
0x18004006b  mov     ebx, [rsp+8F0h+var_8B0]
0x18004006f  lea     rcx, [rsp+8F0h+var_8A0]; this
0x180040074  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180040079  mov     eax, ebx
0x18004007b  mov     rcx, [rbp+7F0h+var_30]
0x180040082  xor     rcx, rsp; StackCookie
0x180040085  call    __security_check_cookie
0x18004008a  lea     r11, [rsp+8F0h+var_20]
0x180040092  mov     rbx, [r11+38h]
0x180040096  mov     rsi, [r11+40h]
0x18004009a  mov     rsp, r11
0x18004009d  pop     r15
0x18004009f  pop     r14
0x1800400a1  pop     r13
0x1800400a3  pop     rdi
0x1800400a4  pop     rbp
0x1800400a5  retn
0x1800400a6  cmp     qword ptr cs:xmmword_1800710A0, r15
0x1800400ad  jz      short loc_18004006F
0x1800400af  lea     rdx, aSFailedToReadT_0; "%s:  Failed to read the router type: %d"...
0x1800400b6  jmp     loc_18003FEFB
```
