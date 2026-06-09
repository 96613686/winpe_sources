# RRasRoutingDomainConfig::PersistConfig(void)

- ea: `0x18003f104`
- end: `0x18003f417`
- name: `?PersistConfig@RRasRoutingDomainConfig@@QEAAKXZ`
- size: `787`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18003bd5c`

## callees

- `0x1800383ac`
- `0x18003eefc`
- `0x18003f104`
- `0x18003f420`
- `0x18003f824`
- `0x18003fc38`
- `0x18004583c`
- `0x1800459e8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18003f1d9`
- `ADVAPI32!RegSetValueExW` at `0x18003f317`
- `ADVAPI32!RegSetValueExW` at `0x18003f1d9`
- `ADVAPI32!RegSetValueExW` at `0x18003f317`

## string_xrefs

- `0x18003f214`: `%s: Couldn't write value %s: %d`
- `0x18003f358`: `%s: Couldn't write value %s: %d`
- `0x18003f18e`: `RRasRoutingDomainConfig::PersistConfig`
- `0x18003f285`: `%s: WriteQoSPoliciesToRegsitry failed: %d.`
- `0x18003f385`: `%s:PersistDialInConfig failed: %d.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::PersistConfig(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  LSTATUS v3; // eax
  GUID *v4; // r9
  unsigned int v5; // eax
  unsigned int v6; // ebx
  const wchar_t *v7; // rdx
  LSTATUS v8; // eax
  GUID *v9; // r9
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  BYTE *lpDataa; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *cbData; // [rsp+28h] [rbp-D8h]
  unsigned int v14; // [rsp+30h] [rbp-D0h]
  unsigned int v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v17; // [rsp+50h] [rbp-B0h]
  __int128 v18; // [rsp+60h] [rbp-A0h]
  __int64 v19; // [rsp+70h] [rbp-90h]
  int v20; // [rsp+78h] [rbp-88h]
  int v21; // [rsp+7Ch] [rbp-84h]
  GUID v22; // [rsp+80h] [rbp-80h] BYREF
  int v23; // [rsp+90h] [rbp-70h] BYREF
  __int128 v24; // [rsp+94h] [rbp-6Ch]
  __int128 v25; // [rsp+A4h] [rbp-5Ch]
  int v26; // [rsp+B4h] [rbp-4Ch]
  int v27; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v28[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v15 = 0;
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
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v16,
      L"RRasRoutingDomainConfig::PersistConfig",
      &v15,
      v2,
      (struct _GUID *)((char *)this + 516),
      cbData,
      v14);
  v3 = RegSetValueExW(*((HKEY *)this + 103), L"RoutingDomainName", 0, 1u, (const BYTE *)this, 0x202u);
  v15 = v3;
  if ( v3 && (_QWORD)xmmword_1800710A0 )
  {
    LOWORD(v27) = 0;
    v22 = GUID_NULL;
    LOWORD(v23) = 0;
    LODWORD(lpData) = v3;
    FormatRRASErrorString(
      &v27,
      L"%s: Couldn't write value %s: %d",
      L"RRasRoutingDomainConfig::PersistConfig",
      L"RoutingDomainName",
      lpData);
    v4 = &v22;
    if ( this != (RRasRoutingDomainConfig *)-516LL )
      v4 = (GUID *)((char *)this + 516);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_1800710A0,
      &v27,
      v4,
      0,
      &v23);
  }
  v5 = WriteQoSPoliciesToRegsitry(*((HKEY *)this + 103));
  v6 = v5;
  v15 = v5;
  if ( v5 )
  {
    if ( !(_QWORD)xmmword_1800710A0 )
      goto LABEL_27;
    v7 = L"%s: WriteQoSPoliciesToRegsitry failed: %d.";
  }
  else
  {
    RRasRoutingDomainConfig::PersistAccountingConfig(this);
    v5 = RRasRoutingDomainConfig::PersistIpv4AddrPool(this);
    v6 = v5;
    v15 = v5;
    if ( v5 )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
        goto LABEL_27;
      v7 = L"%s: PersistIpv4AddrPool failed: %d.";
    }
    else
    {
      v5 = RRasRoutingDomainConfig::PersistIpv6AddrPool(this);
      v6 = v5;
      v15 = v5;
      if ( v5 )
      {
        if ( !(_QWORD)xmmword_1800710A0 )
          goto LABEL_27;
        v7 = L"%s:PersistIpv6AddrPool failed: %d.";
      }
      else
      {
        v8 = RegSetValueExW(*((HKEY *)this + 103), L"RouterType", 0, 4u, (const BYTE *)this + 536, 4u);
        v6 = v8;
        v15 = v8;
        if ( v8 )
        {
          if ( !(_QWORD)xmmword_1800710A0 )
            goto LABEL_27;
          LOWORD(v27) = 0;
          v22 = GUID_NULL;
          LOWORD(v23) = 0;
          LODWORD(lpDataa) = v8;
          FormatRRASErrorString(
            &v27,
            L"%s: Couldn't write value %s: %d",
            L"RRasRoutingDomainConfig::PersistConfig",
            L"RouterType",
            lpDataa);
          goto LABEL_24;
        }
        v5 = RRasRoutingDomainConfig::PersistDialInConfig(this);
        v6 = v5;
        v15 = v5;
        if ( !v5 || !(_QWORD)xmmword_1800710A0 )
          goto LABEL_27;
        v7 = L"%s:PersistDialInConfig failed: %d.";
      }
    }
  }
  LOWORD(v27) = 0;
  v22 = GUID_NULL;
  LOWORD(v23) = 0;
  FormatRRASErrorString(&v27, v7, L"RRasRoutingDomainConfig::PersistConfig", v5);
LABEL_24:
  v9 = &v22;
  if ( this != (RRasRoutingDomainConfig *)-516LL )
    v9 = (GUID *)((char *)this + 516);
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
    gCfgStoreEtwContext,
    xmmword_1800710A0,
    &v27,
    v9,
    0,
    &v23);
  v6 = v15;
LABEL_27:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v16);
  return v6;
}

```

## disassembly

```asm
0x18003f104  push    rbp
0x18003f106  push    rbx
0x18003f107  push    rsi
0x18003f108  push    rdi
0x18003f109  push    r14
0x18003f10b  push    r15
0x18003f10d  lea     rbp, [rsp-7D8h]
0x18003f115  sub     rsp, 8D8h
0x18003f11c  mov     rax, cs:__security_cookie
0x18003f123  xor     rax, rsp
0x18003f126  mov     [rbp+800h+var_40], rax
0x18003f12d  mov     rdi, rcx
0x18003f130  xor     r14d, r14d
0x18003f133  mov     [rsp+900h+var_8C0], r14d
0x18003f138  mov     [rbp+800h+var_840], r14d
0x18003f13c  xor     edx, edx; Val
0x18003f13e  mov     r8d, 7FCh; Size
0x18003f144  lea     rcx, [rbp+800h+var_83C]; void *
0x18003f148  call    memset_0
0x18003f14d  mov     [rbp+800h+var_870], r14d
0x18003f151  xorps   xmm0, xmm0
0x18003f154  xor     eax, eax
0x18003f156  movups  [rbp+800h+var_86C], xmm0
0x18003f15a  movups  [rbp+800h+var_85C], xmm0
0x18003f15e  mov     [rbp+800h+var_84C], eax
0x18003f161  movdqu  [rsp+900h+var_8B0], xmm0
0x18003f167  mov     [rsp+900h+var_8B8], r14
0x18003f16c  xorps   xmm1, xmm1
0x18003f16f  movdqu  [rsp+900h+var_8A0], xmm1
0x18003f175  mov     [rsp+900h+var_890], r14
0x18003f17a  mov     [rsp+900h+var_888], 0FFFFFFFFh
0x18003f182  mov     [rsp+900h+var_884], r14d
0x18003f187  lea     rsi, [rdi+204h]
0x18003f18e  lea     r15, aRrasroutingdom_47; "RRasRoutingDomainConfig::PersistConfig"
0x18003f195  cmp     qword ptr cs:xmmword_1800710A0+8, r14
0x18003f19c  jz      short loc_18003F1B5
0x18003f19e  mov     [rsp+900h+lpData], rsi; struct _GUID *
0x18003f1a3  lea     r8, [rsp+900h+var_8C0]; unsigned int *
0x18003f1a8  mov     rdx, r15; unsigned __int16 *
0x18003f1ab  lea     rcx, [rsp+900h+var_8B8]; this
0x18003f1b0  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18003f1b5  mov     [rsp+900h+cbData], 202h; cbData
0x18003f1bd  mov     [rsp+900h+lpData], rdi; lpData
0x18003f1c2  mov     r9d, 1; dwType
0x18003f1c8  xor     r8d, r8d; Reserved
0x18003f1cb  lea     rdx, aRoutingdomainn; "RoutingDomainName"
0x18003f1d2  mov     rcx, [rdi+338h]; hKey
0x18003f1d9  call    cs:__imp_RegSetValueExW
0x18003f1df  mov     [rsp+900h+var_8C0], eax
0x18003f1e3  test    eax, eax
0x18003f1e5  jz      short loc_18003F25B
0x18003f1e7  cmp     qword ptr cs:xmmword_1800710A0, r14
0x18003f1ee  jz      short loc_18003F25B
0x18003f1f0  mov     word ptr [rbp+800h+var_840], r14w
0x18003f1f5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003f1fc  movdqu  [rbp+800h+var_880], xmm0
0x18003f201  mov     word ptr [rbp+800h+var_870], r14w
0x18003f206  mov     dword ptr [rsp+900h+lpData], eax
0x18003f20a  lea     r9, aRoutingdomainn; "RoutingDomainName"
0x18003f211  mov     r8, r15
0x18003f214  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x18003f21b  lea     rcx, [rbp+800h+var_840]
0x18003f21f  call    FormatRRASErrorString
0x18003f224  lea     r9, [rbp+800h+var_880]
0x18003f228  test    rsi, rsi
0x18003f22b  cmovnz  r9, rsi
0x18003f22f  lea     rax, [rbp+800h+var_870]
0x18003f233  mov     qword ptr [rsp+900h+cbData], rax
0x18003f238  mov     [rsp+900h+lpData], r14
0x18003f23d  lea     r8, [rbp+800h+var_840]
0x18003f241  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003f248  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003f24f  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003f256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f25b  lea     rdx, [rdi+220h]
0x18003f262  mov     rcx, [rdi+338h]; hKey
0x18003f269  call    WriteQoSPoliciesToRegsitry
0x18003f26e  mov     ebx, eax
0x18003f270  mov     [rsp+900h+var_8C0], eax
0x18003f274  test    eax, eax
0x18003f276  jz      short loc_18003F291
0x18003f278  cmp     qword ptr cs:xmmword_1800710A0, r14
0x18003f27f  jz      loc_18003F3EC
0x18003f285  lea     rdx, aSWriteqospolic; "%s: WriteQoSPoliciesToRegsitry failed: "...
0x18003f28c  jmp     loc_18003F38C
0x18003f291  mov     rcx, rdi; this
0x18003f294  call    ?PersistAccountingConfig@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistAccountingConfig(void)
0x18003f299  mov     rcx, rdi; this
0x18003f29c  call    ?PersistIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistIpv4AddrPool(void)
0x18003f2a1  mov     ebx, eax
0x18003f2a3  mov     [rsp+900h+var_8C0], eax
0x18003f2a7  test    eax, eax
0x18003f2a9  jz      short loc_18003F2C4
0x18003f2ab  cmp     qword ptr cs:xmmword_1800710A0, r14
0x18003f2b2  jz      loc_18003F3EC
0x18003f2b8  lea     rdx, aSPersistipv4ad; "%s: PersistIpv4AddrPool failed: %d."
0x18003f2bf  jmp     loc_18003F38C
0x18003f2c4  mov     rcx, rdi; this
0x18003f2c7  call    ?PersistIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistIpv6AddrPool(void)
0x18003f2cc  mov     ebx, eax
0x18003f2ce  mov     [rsp+900h+var_8C0], eax
0x18003f2d2  test    eax, eax
0x18003f2d4  jz      short loc_18003F2EF
0x18003f2d6  cmp     qword ptr cs:xmmword_1800710A0, r14
0x18003f2dd  jz      loc_18003F3EC
0x18003f2e3  lea     rdx, aSPersistipv6ad; "%s:PersistIpv6AddrPool failed: %d."
0x18003f2ea  jmp     loc_18003F38C
0x18003f2ef  lea     rax, [rdi+218h]
0x18003f2f6  mov     r9d, 4; dwType
0x18003f2fc  mov     [rsp+900h+cbData], r9d; cbData
0x18003f301  mov     [rsp+900h+lpData], rax; lpData
0x18003f306  xor     r8d, r8d; Reserved
0x18003f309  lea     rdx, aRoutertype; "RouterType"
0x18003f310  mov     rcx, [rdi+338h]; hKey
0x18003f317  call    cs:__imp_RegSetValueExW
0x18003f31d  mov     ebx, eax
0x18003f31f  mov     [rsp+900h+var_8C0], eax
0x18003f323  test    eax, eax
0x18003f325  jz      short loc_18003F36A
0x18003f327  cmp     qword ptr cs:xmmword_1800710A0, r14
0x18003f32e  jz      loc_18003F3EC
0x18003f334  mov     word ptr [rbp+800h+var_840], r14w
0x18003f339  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003f340  movdqu  [rbp+800h+var_880], xmm0
0x18003f345  mov     word ptr [rbp+800h+var_870], r14w
0x18003f34a  mov     dword ptr [rsp+900h+lpData], eax
0x18003f34e  lea     r9, aRoutertype; "RouterType"
0x18003f355  mov     r8, r15
0x18003f358  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x18003f35f  lea     rcx, [rbp+800h+var_840]
0x18003f363  call    FormatRRASErrorString
0x18003f368  jmp     short loc_18003F3B1
0x18003f36a  mov     rcx, rdi; this
0x18003f36d  call    ?PersistDialInConfig@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistDialInConfig(void)
0x18003f372  mov     ebx, eax
0x18003f374  mov     [rsp+900h+var_8C0], eax
0x18003f378  test    eax, eax
0x18003f37a  jz      short loc_18003F3EC
0x18003f37c  cmp     qword ptr cs:xmmword_1800710A0, r14
0x18003f383  jz      short loc_18003F3EC
0x18003f385  lea     rdx, aSPersistdialin_0; "%s:PersistDialInConfig failed: %d."
0x18003f38c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003f393  mov     word ptr [rbp+800h+var_840], r14w
0x18003f398  movdqu  [rbp+800h+var_880], xmm0
0x18003f39d  mov     word ptr [rbp+800h+var_870], r14w
0x18003f3a2  mov     r9d, eax
0x18003f3a5  mov     r8, r15
0x18003f3a8  lea     rcx, [rbp+800h+var_840]
0x18003f3ac  call    FormatRRASErrorString
0x18003f3b1  lea     rax, [rbp+800h+var_870]
0x18003f3b5  mov     qword ptr [rsp+900h+cbData], rax
0x18003f3ba  lea     r9, [rbp+800h+var_880]
0x18003f3be  test    rsi, rsi
0x18003f3c1  mov     [rsp+900h+lpData], r14
0x18003f3c6  cmovnz  r9, rsi
0x18003f3ca  lea     r8, [rbp+800h+var_840]
0x18003f3ce  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003f3d5  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003f3dc  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18003f3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3e8  mov     ebx, [rsp+900h+var_8C0]
0x18003f3ec  lea     rcx, [rsp+900h+var_8B8]; this
0x18003f3f1  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003f3f6  mov     eax, ebx
0x18003f3f8  mov     rcx, [rbp+800h+var_40]
0x18003f3ff  xor     rcx, rsp; StackCookie
0x18003f402  call    __security_check_cookie
0x18003f407  add     rsp, 8D8h
0x18003f40e  pop     r15
0x18003f410  pop     r14
0x18003f412  pop     rdi
0x18003f413  pop     rsi
0x18003f414  pop     rbx
0x18003f415  pop     rbp
0x18003f416  retn
```
