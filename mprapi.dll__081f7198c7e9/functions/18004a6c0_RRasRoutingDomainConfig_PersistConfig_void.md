# RRasRoutingDomainConfig::PersistConfig(void)

- ea: `0x18004a6c0`
- end: `0x18004a9d3`
- name: `?PersistConfig@RRasRoutingDomainConfig@@QEAAKXZ`
- size: `787`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180047508`
- `0x18004ceec`

## callees

- `0x180043aa0`
- `0x18004a4b8`
- `0x18004a6c0`
- `0x18004a9dc`
- `0x18004ade0`
- `0x18004b204`
- `0x180050b2c`
- `0x180050be8`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a795`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a8d3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a795`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004a8d3`

## string_xrefs

- `0x18004a7d0`: `%s: Couldn't write value %s: %d`
- `0x18004a914`: `%s: Couldn't write value %s: %d`
- `0x18004a74a`: `RRasRoutingDomainConfig::PersistConfig`
- `0x18004a841`: `%s: WriteQoSPoliciesToRegsitry failed: %d.`
- `0x18004a941`: `%s:PersistDialInConfig failed: %d.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::PersistConfig(RRasRoutingDomainConfig *this)
{
  void (*v2)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  LSTATUS v3; // eax
  GUID *v4; // r9
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  void (*v8)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v9; // ebx
  const wchar_t *v10; // rdx
  LSTATUS v11; // eax
  GUID *v12; // r9
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  BYTE *lpDataa; // [rsp+20h] [rbp-E0h]
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v18; // [rsp+50h] [rbp-B0h]
  __int128 v19; // [rsp+60h] [rbp-A0h]
  __int64 v20; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+78h] [rbp-88h]
  int v22; // [rsp+7Ch] [rbp-84h]
  GUID v23; // [rsp+80h] [rbp-80h] BYREF
  int v24; // [rsp+90h] [rbp-70h] BYREF
  __int128 v25; // [rsp+94h] [rbp-6Ch]
  __int128 v26; // [rsp+A4h] [rbp-5Ch]
  int v27; // [rsp+B4h] [rbp-4Ch]
  int v28; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v29[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v16 = 0;
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v18 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v21 = -1;
  v22 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v17,
      L"RRasRoutingDomainConfig::PersistConfig",
      &v16,
      v2,
      (struct _GUID *)((char *)this + 516));
  v3 = RegSetValueExW(*((HKEY *)this + 103), L"RoutingDomainName", 0, 1u, (const BYTE *)this, 0x202u);
  v16 = v3;
  if ( v3 && (_QWORD)xmmword_180078C60 )
  {
    LOWORD(v28) = 0;
    v23 = GUID_NULL;
    LOWORD(v24) = 0;
    LODWORD(lpData) = v3;
    FormatRRASErrorString(
      &v28,
      L"%s: Couldn't write value %s: %d",
      L"RRasRoutingDomainConfig::PersistConfig",
      L"RoutingDomainName",
      lpData);
    v4 = &v23;
    if ( this != (RRasRoutingDomainConfig *)-516LL )
      v4 = (GUID *)((char *)this + 516);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C60,
      &v28,
      v4,
      0,
      &v24);
  }
  v5 = WriteQoSPoliciesToRegsitry(*((HKEY *)this + 103));
  v9 = v5;
  v16 = v5;
  if ( v5 )
  {
    if ( !(_QWORD)xmmword_180078C60 )
      goto LABEL_27;
    v10 = L"%s: WriteQoSPoliciesToRegsitry failed: %d.";
  }
  else
  {
    RRasRoutingDomainConfig::PersistAccountingConfig(this, v6, v7, v8);
    v5 = RRasRoutingDomainConfig::PersistIpv4AddrPool(this);
    v9 = v5;
    v16 = v5;
    if ( v5 )
    {
      if ( !(_QWORD)xmmword_180078C60 )
        goto LABEL_27;
      v10 = L"%s: PersistIpv4AddrPool failed: %d.";
    }
    else
    {
      v5 = RRasRoutingDomainConfig::PersistIpv6AddrPool(this);
      v9 = v5;
      v16 = v5;
      if ( v5 )
      {
        if ( !(_QWORD)xmmword_180078C60 )
          goto LABEL_27;
        v10 = L"%s:PersistIpv6AddrPool failed: %d.";
      }
      else
      {
        v11 = RegSetValueExW(*((HKEY *)this + 103), L"RouterType", 0, 4u, (const BYTE *)this + 536, 4u);
        v9 = v11;
        v16 = v11;
        if ( v11 )
        {
          if ( !(_QWORD)xmmword_180078C60 )
            goto LABEL_27;
          LOWORD(v28) = 0;
          v23 = GUID_NULL;
          LOWORD(v24) = 0;
          LODWORD(lpDataa) = v11;
          FormatRRASErrorString(
            &v28,
            L"%s: Couldn't write value %s: %d",
            L"RRasRoutingDomainConfig::PersistConfig",
            L"RouterType",
            lpDataa);
          goto LABEL_24;
        }
        v5 = RRasRoutingDomainConfig::PersistDialInConfig(this);
        v9 = v5;
        v16 = v5;
        if ( !v5 || !(_QWORD)xmmword_180078C60 )
          goto LABEL_27;
        v10 = L"%s:PersistDialInConfig failed: %d.";
      }
    }
  }
  LOWORD(v28) = 0;
  v23 = GUID_NULL;
  LOWORD(v24) = 0;
  FormatRRASErrorString(&v28, v10, L"RRasRoutingDomainConfig::PersistConfig", v5);
LABEL_24:
  v12 = &v23;
  if ( this != (RRasRoutingDomainConfig *)-516LL )
    v12 = (GUID *)((char *)this + 516);
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
    gCfgStoreEtwContext,
    xmmword_180078C60,
    &v28,
    v12,
    0,
    &v24);
  v9 = v16;
LABEL_27:
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v17);
  return v9;
}

```

## disassembly

```asm
0x18004a6c0  push    rbp
0x18004a6c2  push    rbx
0x18004a6c3  push    rsi
0x18004a6c4  push    rdi
0x18004a6c5  push    r14
0x18004a6c7  push    r15
0x18004a6c9  lea     rbp, [rsp-7D8h]
0x18004a6d1  sub     rsp, 8D8h
0x18004a6d8  mov     rax, cs:__security_cookie
0x18004a6df  xor     rax, rsp
0x18004a6e2  mov     [rbp+800h+var_40], rax
0x18004a6e9  mov     rdi, rcx
0x18004a6ec  xor     r14d, r14d
0x18004a6ef  mov     [rsp+900h+var_8C0], r14d
0x18004a6f4  mov     [rbp+800h+var_840], r14d
0x18004a6f8  xor     edx, edx; Val
0x18004a6fa  mov     r8d, 7FCh; Size
0x18004a700  lea     rcx, [rbp+800h+var_83C]; void *
0x18004a704  call    memset_0
0x18004a709  mov     [rbp+800h+var_870], r14d
0x18004a70d  xorps   xmm0, xmm0
0x18004a710  xor     eax, eax
0x18004a712  movups  [rbp+800h+var_86C], xmm0
0x18004a716  movups  [rbp+800h+var_85C], xmm0
0x18004a71a  mov     [rbp+800h+var_84C], eax
0x18004a71d  movdqu  [rsp+900h+var_8B0], xmm0
0x18004a723  mov     [rsp+900h+var_8B8], r14
0x18004a728  xorps   xmm1, xmm1
0x18004a72b  movdqu  [rsp+900h+var_8A0], xmm1
0x18004a731  mov     [rsp+900h+var_890], r14
0x18004a736  mov     [rsp+900h+var_888], 0FFFFFFFFh
0x18004a73e  mov     [rsp+900h+var_884], r14d
0x18004a743  lea     rsi, [rdi+204h]
0x18004a74a  lea     r15, aRrasroutingdom_46; "RRasRoutingDomainConfig::PersistConfig"
0x18004a751  cmp     qword ptr cs:xmmword_180078C60+8, r14
0x18004a758  jz      short loc_18004A771
0x18004a75a  mov     [rsp+900h+lpData], rsi; struct _GUID *
0x18004a75f  lea     r8, [rsp+900h+var_8C0]; unsigned int *
0x18004a764  mov     rdx, r15; unsigned __int16 *
0x18004a767  lea     rcx, [rsp+900h+var_8B8]; this
0x18004a76c  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004a771  mov     [rsp+900h+cbData], 202h; cbData
0x18004a779  mov     [rsp+900h+lpData], rdi; lpData
0x18004a77e  mov     r9d, 1; dwType
0x18004a784  xor     r8d, r8d; Reserved
0x18004a787  lea     rdx, aRoutingdomainn; "RoutingDomainName"
0x18004a78e  mov     rcx, [rdi+338h]; hKey
0x18004a795  call    cs:__imp_RegSetValueExW
0x18004a79b  mov     [rsp+900h+var_8C0], eax
0x18004a79f  test    eax, eax
0x18004a7a1  jz      short loc_18004A817
0x18004a7a3  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004a7aa  jz      short loc_18004A817
0x18004a7ac  mov     word ptr [rbp+800h+var_840], r14w
0x18004a7b1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004a7b8  movdqu  [rbp+800h+var_880], xmm0
0x18004a7bd  mov     word ptr [rbp+800h+var_870], r14w
0x18004a7c2  mov     dword ptr [rsp+900h+lpData], eax
0x18004a7c6  lea     r9, aRoutingdomainn; "RoutingDomainName"
0x18004a7cd  mov     r8, r15
0x18004a7d0  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x18004a7d7  lea     rcx, [rbp+800h+var_840]
0x18004a7db  call    FormatRRASErrorString
0x18004a7e0  lea     r9, [rbp+800h+var_880]
0x18004a7e4  test    rsi, rsi
0x18004a7e7  cmovnz  r9, rsi
0x18004a7eb  lea     rax, [rbp+800h+var_870]
0x18004a7ef  mov     qword ptr [rsp+900h+cbData], rax
0x18004a7f4  mov     [rsp+900h+lpData], r14
0x18004a7f9  lea     r8, [rbp+800h+var_840]
0x18004a7fd  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004a804  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004a80b  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004a812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a817  lea     rdx, [rdi+220h]
0x18004a81e  mov     rcx, [rdi+338h]; hKey
0x18004a825  call    WriteQoSPoliciesToRegsitry
0x18004a82a  mov     ebx, eax
0x18004a82c  mov     [rsp+900h+var_8C0], eax
0x18004a830  test    eax, eax
0x18004a832  jz      short loc_18004A84D
0x18004a834  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004a83b  jz      loc_18004A9A8
0x18004a841  lea     rdx, aSWriteqospolic; "%s: WriteQoSPoliciesToRegsitry failed: "...
0x18004a848  jmp     loc_18004A948
0x18004a84d  mov     rcx, rdi; this
0x18004a850  call    ?PersistAccountingConfig@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistAccountingConfig(void)
0x18004a855  mov     rcx, rdi; this
0x18004a858  call    ?PersistIpv4AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistIpv4AddrPool(void)
0x18004a85d  mov     ebx, eax
0x18004a85f  mov     [rsp+900h+var_8C0], eax
0x18004a863  test    eax, eax
0x18004a865  jz      short loc_18004A880
0x18004a867  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004a86e  jz      loc_18004A9A8
0x18004a874  lea     rdx, aSPersistipv4ad; "%s: PersistIpv4AddrPool failed: %d."
0x18004a87b  jmp     loc_18004A948
0x18004a880  mov     rcx, rdi; this
0x18004a883  call    ?PersistIpv6AddrPool@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistIpv6AddrPool(void)
0x18004a888  mov     ebx, eax
0x18004a88a  mov     [rsp+900h+var_8C0], eax
0x18004a88e  test    eax, eax
0x18004a890  jz      short loc_18004A8AB
0x18004a892  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004a899  jz      loc_18004A9A8
0x18004a89f  lea     rdx, aSPersistipv6ad; "%s:PersistIpv6AddrPool failed: %d."
0x18004a8a6  jmp     loc_18004A948
0x18004a8ab  lea     rax, [rdi+218h]
0x18004a8b2  mov     r9d, 4; dwType
0x18004a8b8  mov     [rsp+900h+cbData], r9d; cbData
0x18004a8bd  mov     [rsp+900h+lpData], rax; lpData
0x18004a8c2  xor     r8d, r8d; Reserved
0x18004a8c5  lea     rdx, aRoutertype; "RouterType"
0x18004a8cc  mov     rcx, [rdi+338h]; hKey
0x18004a8d3  call    cs:__imp_RegSetValueExW
0x18004a8d9  mov     ebx, eax
0x18004a8db  mov     [rsp+900h+var_8C0], eax
0x18004a8df  test    eax, eax
0x18004a8e1  jz      short loc_18004A926
0x18004a8e3  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004a8ea  jz      loc_18004A9A8
0x18004a8f0  mov     word ptr [rbp+800h+var_840], r14w
0x18004a8f5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004a8fc  movdqu  [rbp+800h+var_880], xmm0
0x18004a901  mov     word ptr [rbp+800h+var_870], r14w
0x18004a906  mov     dword ptr [rsp+900h+lpData], eax
0x18004a90a  lea     r9, aRoutertype; "RouterType"
0x18004a911  mov     r8, r15
0x18004a914  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x18004a91b  lea     rcx, [rbp+800h+var_840]
0x18004a91f  call    FormatRRASErrorString
0x18004a924  jmp     short loc_18004A96D
0x18004a926  mov     rcx, rdi; this
0x18004a929  call    ?PersistDialInConfig@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::PersistDialInConfig(void)
0x18004a92e  mov     ebx, eax
0x18004a930  mov     [rsp+900h+var_8C0], eax
0x18004a934  test    eax, eax
0x18004a936  jz      short loc_18004A9A8
0x18004a938  cmp     qword ptr cs:xmmword_180078C60, r14
0x18004a93f  jz      short loc_18004A9A8
0x18004a941  lea     rdx, aSPersistdialin_0; "%s:PersistDialInConfig failed: %d."
0x18004a948  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004a94f  mov     word ptr [rbp+800h+var_840], r14w
0x18004a954  movdqu  [rbp+800h+var_880], xmm0
0x18004a959  mov     word ptr [rbp+800h+var_870], r14w
0x18004a95e  mov     r9d, eax
0x18004a961  mov     r8, r15
0x18004a964  lea     rcx, [rbp+800h+var_840]
0x18004a968  call    FormatRRASErrorString
0x18004a96d  lea     rax, [rbp+800h+var_870]
0x18004a971  mov     qword ptr [rsp+900h+cbData], rax
0x18004a976  lea     r9, [rbp+800h+var_880]
0x18004a97a  test    rsi, rsi
0x18004a97d  mov     [rsp+900h+lpData], r14
0x18004a982  cmovnz  r9, rsi
0x18004a986  lea     r8, [rbp+800h+var_840]
0x18004a98a  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004a991  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004a998  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004a99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9a4  mov     ebx, [rsp+900h+var_8C0]
0x18004a9a8  lea     rcx, [rsp+900h+var_8B8]; this
0x18004a9ad  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18004a9b2  mov     eax, ebx
0x18004a9b4  mov     rcx, [rbp+800h+var_40]
0x18004a9bb  xor     rcx, rsp; StackCookie
0x18004a9be  call    __security_check_cookie
0x18004a9c3  add     rsp, 8D8h
0x18004a9ca  pop     r15
0x18004a9cc  pop     r14
0x18004a9ce  pop     rdi
0x18004a9cf  pop     rsi
0x18004a9d0  pop     rbx
0x18004a9d1  pop     rbp
0x18004a9d2  retn
```
