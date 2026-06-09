# RRasRoutingDomainConfig::PopulateFromRegistry(void)

- ea: `0x18004b3ac`
- end: `0x18004b688`
- name: `?PopulateFromRegistry@RRasRoutingDomainConfig@@QEAAKXZ`
- size: `732`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180048d84`
- `0x180049728`

## callees

- `0x180042bc4`
- `0x18004b3ac`
- `0x18004b690`
- `0x18004bca0`
- `0x18004be7c`
- `0x18004bf80`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b4a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b609`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b4a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004b609`

## string_xrefs

- `0x18004b447`: `RRasRoutingDomainConfig::PopulateFromRegistry`
- `0x18004b4c0`: `%s:  Failed to read the routing domain name: %d.`
- `0x18004b552`: `%s:  ReadQoSPoliciesFromRegistry failed: %d.`
- `0x18004b67b`: `%s:  Failed to read the router type: %d.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::PopulateFromRegistry(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int QoSPoliciesFromRegistry; // eax
  unsigned int v4; // ebx
  const wchar_t *v5; // rdx
  GUID *v6; // r9
  _DWORD *v7; // rsi
  unsigned int v9; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v12; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v13; // [rsp+58h] [rbp-A8h]
  __int128 v14; // [rsp+68h] [rbp-98h]
  __int64 v15; // [rsp+78h] [rbp-88h]
  int v16; // [rsp+80h] [rbp-80h]
  int v17; // [rsp+84h] [rbp-7Ch]
  GUID v18; // [rsp+88h] [rbp-78h] BYREF
  int v19; // [rsp+98h] [rbp-68h] BYREF
  __int128 v20; // [rsp+9Ch] [rbp-64h]
  __int128 v21; // [rsp+ACh] [rbp-54h]
  int v22; // [rsp+BCh] [rbp-44h]
  int v23; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v24[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v9 = 0;
  cbData = 0;
  Type = 0;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v13 = 0;
  v12 = 0;
  v14 = 0;
  v15 = 0;
  v16 = -1;
  v17 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v12,
      L"RRasRoutingDomainConfig::PopulateFromRegistry",
      &v9,
      v2,
      (struct _GUID *)((char *)this + 516));
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
  v9 = QoSPoliciesFromRegistry;
  if ( QoSPoliciesFromRegistry )
  {
    if ( (_QWORD)xmmword_180078C60 )
    {
      v5 = L"%s:  Failed to read the routing domain name: %d.";
LABEL_6:
      LOWORD(v23) = 0;
      v18 = GUID_NULL;
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v23, v5, L"RRasRoutingDomainConfig::PopulateFromRegistry", QoSPoliciesFromRegistry);
      v6 = &v18;
      if ( this != (RRasRoutingDomainConfig *)-516LL )
        v6 = (GUID *)((char *)this + 516);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C60,
        &v23,
        v6,
        0,
        &v19);
      goto LABEL_25;
    }
  }
  else
  {
    QoSPoliciesFromRegistry = ReadQoSPoliciesFromRegistry(*((HKEY *)this + 103));
    v4 = QoSPoliciesFromRegistry;
    v9 = QoSPoliciesFromRegistry;
    if ( QoSPoliciesFromRegistry )
    {
      if ( (_QWORD)xmmword_180078C60 )
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
      v9 = QoSPoliciesFromRegistry;
      if ( !QoSPoliciesFromRegistry || QoSPoliciesFromRegistry == 1168 )
      {
        v9 = 0;
        QoSPoliciesFromRegistry = RRasRoutingDomainConfig::PopulateIpv6AddrPool(this);
        v4 = QoSPoliciesFromRegistry;
        v9 = QoSPoliciesFromRegistry;
        if ( !QoSPoliciesFromRegistry || QoSPoliciesFromRegistry == 1168 )
        {
          v9 = 0;
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
          v9 = QoSPoliciesFromRegistry;
          if ( QoSPoliciesFromRegistry )
          {
            *v7 = 0;
            if ( QoSPoliciesFromRegistry != 1168 )
            {
              if ( !(_QWORD)xmmword_180078C60 )
                goto LABEL_26;
              v5 = L"%s:  Failed to read the router type: %d.";
              goto LABEL_6;
            }
            v4 = 0;
            v9 = 0;
          }
          if ( (*(_BYTE *)v7 & 9) != 0 )
          {
            RRasRoutingDomainConfig::ReadDialInConfig(this);
LABEL_25:
            v4 = v9;
          }
        }
        else if ( (_QWORD)xmmword_180078C60 )
        {
          v5 = L"%s:  PopulateIpv6AddrPool failed: %d.";
          goto LABEL_6;
        }
      }
      else if ( (_QWORD)xmmword_180078C60 )
      {
        v5 = L"%s:  PopulateIpv4AddrPool failed: %d.";
        goto LABEL_6;
      }
    }
  }
LABEL_26:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v12);
  return v4;
}

```

## disassembly

```asm
0x18004b3ac  mov     [rsp-8+arg_8], rbx
0x18004b3b1  mov     [rsp-8+arg_10], rsi
0x18004b3b6  push    rbp
0x18004b3b7  push    rdi
0x18004b3b8  push    r13
0x18004b3ba  push    r14
0x18004b3bc  push    r15
0x18004b3be  lea     rbp, [rsp-7D0h]
0x18004b3c6  sub     rsp, 8D0h
0x18004b3cd  mov     rax, cs:__security_cookie
0x18004b3d4  xor     rax, rsp
0x18004b3d7  mov     [rbp+7F0h+var_30], rax
0x18004b3de  mov     rdi, rcx
0x18004b3e1  xor     r15d, r15d
0x18004b3e4  mov     [rsp+8F0h+var_8B0], r15d
0x18004b3e9  mov     [rsp+8F0h+cbData], r15d
0x18004b3ee  mov     [rsp+8F0h+Type], r15d
0x18004b3f3  mov     [rbp+7F0h+var_830], r15d
0x18004b3f7  xor     edx, edx; Val
0x18004b3f9  mov     r8d, 7FCh; Size
0x18004b3ff  lea     rcx, [rbp+7F0h+var_82C]; void *
0x18004b403  call    memset_0
0x18004b408  mov     [rbp+7F0h+var_858], r15d
0x18004b40c  xorps   xmm0, xmm0
0x18004b40f  xor     eax, eax
0x18004b411  movups  [rbp+7F0h+var_854], xmm0
0x18004b415  movups  [rbp+7F0h+var_844], xmm0
0x18004b419  mov     [rbp+7F0h+var_834], eax
0x18004b41c  movdqu  [rsp+8F0h+var_898], xmm0
0x18004b422  mov     [rsp+8F0h+var_8A0], r15
0x18004b427  xorps   xmm1, xmm1
0x18004b42a  movdqu  [rsp+8F0h+var_888], xmm1
0x18004b430  mov     [rsp+8F0h+var_878], r15
0x18004b435  mov     [rbp+7F0h+var_870], 0FFFFFFFFh
0x18004b43c  mov     [rbp+7F0h+var_86C], r15d
0x18004b440  lea     r14, [rdi+204h]
0x18004b447  lea     r13, aRrasroutingdom_51; "RRasRoutingDomainConfig::PopulateFromRe"...
0x18004b44e  cmp     qword ptr cs:xmmword_180078C60+8, r15
0x18004b455  jz      short loc_18004B46E
0x18004b457  mov     [rsp+8F0h+lpData], r14; struct _GUID *
0x18004b45c  lea     r8, [rsp+8F0h+var_8B0]; unsigned int *
0x18004b461  mov     rdx, r13; unsigned __int16 *
0x18004b464  lea     rcx, [rsp+8F0h+var_8A0]; this
0x18004b469  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004b46e  mov     [rsp+8F0h+cbData], 202h
0x18004b476  mov     [rsp+8F0h+Type], 1
0x18004b47e  lea     rax, [rsp+8F0h+cbData]
0x18004b483  mov     [rsp+8F0h+lpcbData], rax; lpcbData
0x18004b488  mov     [rsp+8F0h+lpData], rdi; lpData
0x18004b48d  lea     r9, [rsp+8F0h+Type]; lpType
0x18004b492  xor     r8d, r8d; lpReserved
0x18004b495  lea     rdx, aRoutingdomainn; "RoutingDomainName"
0x18004b49c  mov     rcx, [rdi+338h]; hKey
0x18004b4a3  call    cs:__imp_RegQueryValueExW
0x18004b4a9  mov     ebx, eax
0x18004b4ab  mov     [rsp+8F0h+var_8B0], eax
0x18004b4af  test    eax, eax
0x18004b4b1  jz      short loc_18004B528
0x18004b4b3  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004b4ba  jz      loc_18004B63B
0x18004b4c0  lea     rdx, aSFailedToReadT; "%s:  Failed to read the routing domain "...
0x18004b4c7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004b4ce  mov     word ptr [rbp+7F0h+var_830], r15w
0x18004b4d3  movdqu  [rbp+7F0h+var_868], xmm0
0x18004b4d8  mov     word ptr [rbp+7F0h+var_858], r15w
0x18004b4dd  mov     r9d, eax
0x18004b4e0  mov     r8, r13
0x18004b4e3  lea     rcx, [rbp+7F0h+var_830]
0x18004b4e7  call    FormatRRASErrorString
0x18004b4ec  lea     r9, [rbp+7F0h+var_868]
0x18004b4f0  test    r14, r14
0x18004b4f3  cmovnz  r9, r14
0x18004b4f7  lea     rax, [rbp+7F0h+var_858]
0x18004b4fb  mov     [rsp+8F0h+lpcbData], rax
0x18004b500  mov     [rsp+8F0h+lpData], r15
0x18004b505  lea     r8, [rbp+7F0h+var_830]
0x18004b509  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004b510  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004b517  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004b51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b523  jmp     loc_18004B637
0x18004b528  lea     rdx, [rdi+220h]
0x18004b52f  mov     rcx, [rdi+338h]; hKey
0x18004b536  call    ReadQoSPoliciesFromRegistry
0x18004b53b  mov     ebx, eax
0x18004b53d  mov     [rsp+8F0h+var_8B0], eax
0x18004b541  test    eax, eax
0x18004b543  jz      short loc_18004B55E
0x18004b545  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004b54c  jz      loc_18004B63B
0x18004b552  lea     rdx, aSReadqospolici; "%s:  ReadQoSPoliciesFromRegistry failed"...
0x18004b559  jmp     loc_18004B4C7
0x18004b55e  mov     rcx, rdi; this
0x18004b561  call    ?ReadAccountingConfig@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::ReadAccountingConfig(void)
0x18004b566  mov     rcx, rdi; this
0x18004b569  call    ?PopulateIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PopulateIpv4AddrPool(void)
0x18004b56e  mov     ebx, eax
0x18004b570  mov     [rsp+8F0h+var_8B0], eax
0x18004b574  test    eax, eax
0x18004b576  jz      short loc_18004B598
0x18004b578  cmp     eax, 490h
0x18004b57d  jz      short loc_18004B598
0x18004b57f  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004b586  jz      loc_18004B63B
0x18004b58c  lea     rdx, aSPopulateipv4a; "%s:  PopulateIpv4AddrPool failed: %d."
0x18004b593  jmp     loc_18004B4C7
0x18004b598  mov     [rsp+8F0h+var_8B0], r15d
0x18004b59d  mov     rcx, rdi; this
0x18004b5a0  call    ?PopulateIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PopulateIpv6AddrPool(void)
0x18004b5a5  mov     ebx, eax
0x18004b5a7  mov     [rsp+8F0h+var_8B0], eax
0x18004b5ab  test    eax, eax
0x18004b5ad  jz      short loc_18004B5CB
0x18004b5af  cmp     eax, 490h
0x18004b5b4  jz      short loc_18004B5CB
0x18004b5b6  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004b5bd  jz      short loc_18004B63B
0x18004b5bf  lea     rdx, aSPopulateipv6a; "%s:  PopulateIpv6AddrPool failed: %d."
0x18004b5c6  jmp     loc_18004B4C7
0x18004b5cb  mov     [rsp+8F0h+var_8B0], r15d
0x18004b5d0  mov     eax, 4
0x18004b5d5  mov     [rsp+8F0h+cbData], eax
0x18004b5d9  mov     [rsp+8F0h+Type], eax
0x18004b5dd  lea     rsi, [rdi+218h]
0x18004b5e4  lea     rax, [rsp+8F0h+cbData]
0x18004b5e9  mov     [rsp+8F0h+lpcbData], rax; lpcbData
0x18004b5ee  mov     [rsp+8F0h+lpData], rsi; lpData
0x18004b5f3  lea     r9, [rsp+8F0h+Type]; lpType
0x18004b5f8  xor     r8d, r8d; lpReserved
0x18004b5fb  lea     rdx, aRoutertype; "RouterType"
0x18004b602  mov     rcx, [rdi+338h]; hKey
0x18004b609  call    cs:__imp_RegQueryValueExW
0x18004b60f  mov     ebx, eax
0x18004b611  mov     [rsp+8F0h+var_8B0], eax
0x18004b615  test    eax, eax
0x18004b617  jz      short loc_18004B62A
0x18004b619  mov     [rsi], r15d
0x18004b61c  cmp     eax, 490h
0x18004b621  jnz     short loc_18004B672
0x18004b623  mov     ebx, r15d
0x18004b626  mov     [rsp+8F0h+var_8B0], ebx
0x18004b62a  test    byte ptr [rsi], 9
0x18004b62d  jz      short loc_18004B63B
0x18004b62f  mov     rcx, rdi; this
0x18004b632  call    ?ReadDialInConfig@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::ReadDialInConfig(void)
0x18004b637  mov     ebx, [rsp+8F0h+var_8B0]
0x18004b63b  lea     rcx, [rsp+8F0h+var_8A0]; this
0x18004b640  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004b645  mov     eax, ebx
0x18004b647  mov     rcx, [rbp+7F0h+var_30]
0x18004b64e  xor     rcx, rsp; StackCookie
0x18004b651  call    __security_check_cookie
0x18004b656  lea     r11, [rsp+8F0h+var_20]
0x18004b65e  mov     rbx, [r11+38h]
0x18004b662  mov     rsi, [r11+40h]
0x18004b666  mov     rsp, r11
0x18004b669  pop     r15
0x18004b66b  pop     r14
0x18004b66d  pop     r13
0x18004b66f  pop     rdi
0x18004b670  pop     rbp
0x18004b671  retn
0x18004b672  cmp     qword ptr cs:xmmword_180078C60, r15
0x18004b679  jz      short loc_18004B63B
0x18004b67b  lea     rdx, aSFailedToReadT_0; "%s:  Failed to read the router type: %d"...
0x18004b682  jmp     loc_18004B4C7
```
