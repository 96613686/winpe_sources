# RasStatIpv6CreatePrefixList

- ea: `0x18005ba30`
- end: `0x18005c002`
- name: `RasStatIpv6CreatePrefixList`
- size: `1490`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800521b0`
- `0x180056f10`

## callees

- `0x180019d50`
- `0x180027ec0`
- `0x18005ba30`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18005bb31`
- `KERNEL32!LocalAlloc` at `0x18005be18`
- `KERNEL32!LocalAlloc` at `0x18005bb31`
- `KERNEL32!LocalAlloc` at `0x18005be18`
- `ADVAPI32!RegCloseKey` at `0x18005bf82`
- `ADVAPI32!RegCloseKey` at `0x18005bfcb`
- `ADVAPI32!RegCloseKey` at `0x18005bf82`
- `ADVAPI32!RegCloseKey` at `0x18005bfcb`
- `ADVAPI32!RegOpenKeyExA` at `0x18005bc69`
- `ADVAPI32!RegOpenKeyExA` at `0x18005bce7`
- `ADVAPI32!RegOpenKeyExA` at `0x18005bc69`
- `ADVAPI32!RegOpenKeyExA` at `0x18005bce7`
- `ADVAPI32!RegQueryValueExA` at `0x18005bd7b`
- `ADVAPI32!RegQueryValueExA` at `0x18005bdde`
- `ADVAPI32!RegQueryValueExA` at `0x18005bd7b`
- `ADVAPI32!RegQueryValueExA` at `0x18005bdde`
- `ntdll!RtlIpv6AddressToStringA` at `0x18005bb9e`
- `ntdll!RtlIpv6AddressToStringA` at `0x18005bbf3`
- `ntdll!RtlIpv6AddressToStringA` at `0x18005be72`
- `ntdll!RtlIpv6AddressToStringA` at `0x18005bec7`
- `ntdll!RtlIpv6AddressToStringA` at `0x18005bb9e`
- `ntdll!RtlIpv6AddressToStringA` at `0x18005bbf3`
- `ntdll!RtlIpv6AddressToStringA` at `0x18005be72`
- `ntdll!RtlIpv6AddressToStringA` at `0x18005bec7`

## string_xrefs

- `0x18005bac8`: `RasStatIpv6CreatePrefixList`
- `0x18005bc5b`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6\StaticPrefixPool`
- `0x18005bd00`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6\StaticPrefixPool`
- `0x18005bd14`: `Couldn't open key %hs in %hs error:%ld`
- `0x18005bf45`: `Couldn't read value %hs in key %hs: %d`

## pseudocode

```c
int __fastcall RasStatIpv6CreatePrefixList(_QWORD *a1, _QWORD *a2)
{
  char *v4; // rbx
  int v5; // esi
  char **v6; // r15
  char *v7; // rax
  char *v8; // rax
  __int128 v9; // xmm0
  int v10; // r14d
  int v11; // edi
  __int64 v12; // rdx
  const wchar_t *v13; // r8
  char *v14; // rbx
  struct in6_addr v15; // xmm0
  const CHAR *v16; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY v22; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  char *v24; // [rsp+48h] [rbp-B8h] BYREF
  struct in6_addr v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Addr[17]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v27; // [rsp+71h] [rbp-8Fh]
  char v28; // [rsp+73h] [rbp-8Dh]
  struct in6_addr v29; // [rsp+78h] [rbp-88h] BYREF
  char pszDest[24]; // [rsp+88h] [rbp-78h] BYREF
  CHAR S[128]; // [rsp+A0h] [rbp-60h] BYREF
  int v32; // [rsp+120h] [rbp+20h] BYREF
  char v33[2044]; // [rsp+124h] [rbp+24h] BYREF

  hKey = 0;
  v22 = 0;
  Type = 0;
  v4 = 0;
  cbData = 0;
  v24 = 0;
  memset(Addr, 0, sizeof(Addr));
  v27 = 0;
  v28 = 0;
  v5 = 0;
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"RasStatIpv6CreatePrefixList");
  v6 = &v24;
  if ( !dword_1800CF650 || *a1 == *(_QWORD *)&GUID_NULL.Data1 && a1[1] == *(_QWORD *)GUID_NULL.Data4 )
  {
    LODWORD(v7) = RegOpenKeyExA(
                    HKEY_LOCAL_MACHINE,
                    "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ipv6\\StaticPrefixPool",
                    0,
                    0x20019u,
                    &hKey);
    if ( (_DWORD)v7 )
      goto LABEL_47;
    v10 = 0;
    v11 = 0;
    while ( 1 )
    {
      v25.u.Byte[0] = 0;
      *(_QWORD *)&v25.u.Byte[1] = 0;
      *(_DWORD *)((char *)&v25.u.Word[4] + 1) = 0;
      *(USHORT *)((char *)&v25.u.Word[6] + 1) = 0;
      v25.u.Byte[15] = 0;
      v29.u.Byte[0] = 0;
      *(_QWORD *)&v29.u.Byte[1] = 0;
      *(_DWORD *)((char *)&v29.u.Word[4] + 1) = 0;
      *(USHORT *)((char *)&v29.u.Word[6] + 1) = 0;
      v29.u.Byte[15] = 0;
      v22 = 0;
      StringCbPrintfA(pszDest, 0xAu, "%d", v10);
      LODWORD(v7) = RegOpenKeyExA(hKey, pszDest, 0, 0x20019u, &v22);
      if ( (_DWORD)v7 )
        break;
      cbData = 128;
      LODWORD(v7) = RegQueryValueExA(v22, "From", 0, &Type, (LPBYTE)S, &cbData);
      if ( !(_DWORD)v7 && Type == 3 && cbData == 16 )
      {
        cbData = 128;
        v25 = *(struct in6_addr *)S;
        LODWORD(v7) = RegQueryValueExA(v22, "To", 0, &Type, (LPBYTE)S, &cbData);
        if ( !(_DWORD)v7 && Type == 3 && cbData == 16 )
        {
          v29 = *(struct in6_addr *)S;
          v7 = (char *)LocalAlloc(0x40u, 0x38u);
          v14 = v7;
          if ( v7 )
          {
            *(struct in6_addr *)(v7 + 8) = v25;
            *(struct in6_addr *)(v7 + 40) = v25;
            v15 = v29;
            *(_QWORD *)v7 = 0;
            *(struct in6_addr *)(v7 + 24) = v15;
            RtlIpv6AddressToStringA(&v25, S);
            if ( (_QWORD)xmmword_1800D0740 )
            {
              LOWORD(v32) = 0;
              FormatRRASErrorString(&v32, L"Static Pool From Addr: %hs", S);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
                gRasIpAddrMgmtEtwContext,
                xmmword_1800D0740,
                &v32);
            }
            LODWORD(v7) = (unsigned int)RtlIpv6AddressToStringA(&v29, S);
            if ( (_QWORD)xmmword_1800D0740 )
            {
              LOWORD(v32) = 0;
              FormatRRASErrorString(&v32, L"Static Pool To   Addr: %hs", S);
              LODWORD(v7) = ((__int64 (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
                              gRasIpAddrMgmtEtwContext,
                              xmmword_1800D0740,
                              &v32);
            }
            *v6 = v14;
            v6 = (char **)v14;
            goto LABEL_40;
          }
          v12 = *((_QWORD *)&xmmword_1800D0740 + 1);
          if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
          {
            v13 = L"Out of memory";
LABEL_19:
            LODWORD(v7) = ((__int64 (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
                            gRasIpAddrMgmtEtwContext,
                            v12,
                            v13);
          }
LABEL_20:
          v11 = 1;
          goto LABEL_40;
        }
        if ( (_QWORD)xmmword_1800D0740 )
        {
          v16 = "To";
LABEL_39:
          LODWORD(phkResulta) = (_DWORD)v7;
          LOWORD(v32) = 0;
          FormatRRASErrorString(&v32, L"Couldn't read value %hs in key %hs: %d", v16, pszDest, phkResulta);
          LODWORD(v7) = ((__int64 (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
                          gRasIpAddrMgmtEtwContext,
                          xmmword_1800D0740,
                          &v32);
        }
      }
      else if ( (_QWORD)xmmword_1800D0740 )
      {
        v16 = "From";
        goto LABEL_39;
      }
LABEL_40:
      if ( v22 )
        LODWORD(v7) = RegCloseKey(v22);
      ++v10;
      if ( v11 )
      {
        v4 = v24;
        goto LABEL_44;
      }
    }
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v32) = 0;
      LODWORD(phkResult) = (_DWORD)v7;
      FormatRRASErrorString(
        &v32,
        L"Couldn't open key %hs in %hs error:%ld",
        pszDest,
        "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ipv6\\StaticPrefixPool",
        phkResult);
      v12 = xmmword_1800D0740;
      v13 = (const wchar_t *)&v32;
      goto LABEL_19;
    }
    goto LABEL_20;
  }
  LODWORD(v7) = GetRoutingDomainConfigData(a1, 2, 20, Addr);
  if ( (_DWORD)v7 )
    goto LABEL_44;
  v5 = 1;
  v8 = (char *)LocalAlloc(0x40u, 0x38u);
  v4 = v8;
  if ( !v8 )
  {
    if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        *((_QWORD *)&xmmword_1800D0740 + 1),
        L"Out of memory");
LABEL_45:
    LODWORD(v7) = (_DWORD)qword_1800CF690;
    if ( qword_1800CF690 )
      LODWORD(v7) = qword_1800CF690(2, Addr);
    goto LABEL_47;
  }
  *(_OWORD *)(v8 + 8) = *(_OWORD *)Addr;
  *(_OWORD *)(v8 + 40) = *(_OWORD *)Addr;
  v9 = *(_OWORD *)Addr;
  *(_QWORD *)v8 = 0;
  *(_OWORD *)(v8 + 24) = v9;
  RtlIpv6AddressToStringA((const struct in6_addr *)Addr, S);
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v32) = 0;
    FormatRRASErrorString(&v32, L"Static Pool From Addr: %hs", S);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v32);
  }
  LODWORD(v7) = (unsigned int)RtlIpv6AddressToStringA((const struct in6_addr *)Addr, S);
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v32) = 0;
    FormatRRASErrorString(&v32, L"Static Pool To   Addr: %hs", S);
    LODWORD(v7) = ((__int64 (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
                    gRasIpAddrMgmtEtwContext,
                    xmmword_1800D0740,
                    &v32);
  }
LABEL_44:
  *a2 = v4;
  if ( v5 )
    goto LABEL_45;
LABEL_47:
  if ( hKey )
    LODWORD(v7) = RegCloseKey(hKey);
  return (int)v7;
}

```

## disassembly

```asm
0x18005ba30  mov     [rsp-8+arg_10], rbx
0x18005ba35  push    rbp
0x18005ba36  push    rsi
0x18005ba37  push    rdi
0x18005ba38  push    r12
0x18005ba3a  push    r13
0x18005ba3c  push    r14
0x18005ba3e  push    r15
0x18005ba40  lea     rbp, [rsp-830h]
0x18005ba48  sub     rsp, 930h
0x18005ba4f  mov     rax, cs:__security_cookie
0x18005ba56  xor     rax, rsp
0x18005ba59  mov     [rbp+860h+var_40], rax
0x18005ba60  xor     r13d, r13d
0x18005ba63  xor     eax, eax
0x18005ba65  mov     r12, rdx
0x18005ba68  mov     [rsp+960h+hKey], r13
0x18005ba6d  mov     rdi, rcx
0x18005ba70  mov     [rsp+960h+var_928], r13
0x18005ba75  xorps   xmm0, xmm0
0x18005ba78  mov     [rsp+960h+Type], r13d
0x18005ba7d  mov     ebx, r13d
0x18005ba80  mov     [rsp+960h+cbData], r13d
0x18005ba85  xor     edx, edx; Val
0x18005ba87  mov     [rsp+960h+var_918], rbx
0x18005ba8c  mov     r8d, 7FCh; Size
0x18005ba92  mov     [rsp+960h+Addr], r13b
0x18005ba97  lea     rcx, [rbp+860h+var_83C]; void *
0x18005ba9b  mov     [rsp+960h+var_8EF], ax
0x18005baa0  movups  xmmword ptr [rsp+960h+Addr+1], xmm0
0x18005baa5  mov     [rsp+960h+var_8ED], al
0x18005baa9  mov     esi, r13d
0x18005baac  mov     [rbp+860h+var_840], r13d
0x18005bab0  call    memset_0
0x18005bab5  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005babc  test    rdx, rdx
0x18005babf  jz      short loc_18005BADB
0x18005bac1  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005bac8  lea     r8, aRasstatipv6cre; "RasStatIpv6CreatePrefixList"
0x18005bacf  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005bad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005badb  cmp     cs:dword_1800CF650, r13d
0x18005bae2  lea     r15, [rsp+960h+var_918]
0x18005bae7  jz      loc_18005BC48
0x18005baed  mov     rax, [rdi]
0x18005baf0  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18005baf7  jnz     short loc_18005BB0A
0x18005baf9  mov     rax, [rdi+8]
0x18005bafd  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18005bb04  jz      loc_18005BC48
0x18005bb0a  mov     edx, 2
0x18005bb0f  lea     r9, [rsp+960h+Addr]
0x18005bb14  mov     rcx, rdi
0x18005bb17  lea     r8d, [rdx+12h]
0x18005bb1b  call    GetRoutingDomainConfigData
0x18005bb20  test    eax, eax
0x18005bb22  jnz     loc_18005BF9E
0x18005bb28  lea     edx, [rax+38h]; uBytes
0x18005bb2b  lea     ecx, [rax+40h]; uFlags
0x18005bb2e  lea     esi, [rax+1]
0x18005bb31  call    cs:__imp_LocalAlloc
0x18005bb38  nop     dword ptr [rax+rax+00h]
0x18005bb3d  mov     rbx, rax
0x18005bb40  test    rax, rax
0x18005bb43  jnz     short loc_18005BB74
0x18005bb45  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005bb4c  test    rdx, rdx
0x18005bb4f  jz      loc_18005BFA6
0x18005bb55  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005bb5c  lea     r8, aOutOfMemory; "Out of memory"
0x18005bb63  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005bb6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb6f  jmp     loc_18005BFA6
0x18005bb74  movups  xmm0, xmmword ptr [rsp+960h+Addr]
0x18005bb79  lea     rdx, [rbp+860h+S]; S
0x18005bb7d  lea     rcx, [rsp+960h+Addr]; Addr
0x18005bb82  movdqu  xmmword ptr [rax+8], xmm0
0x18005bb87  movups  xmm1, xmmword ptr [rsp+960h+Addr]
0x18005bb8c  movdqu  xmmword ptr [rax+28h], xmm1
0x18005bb91  movups  xmm0, xmmword ptr [rsp+960h+Addr]
0x18005bb96  mov     [rax], r13
0x18005bb99  movdqu  xmmword ptr [rax+18h], xmm0
0x18005bb9e  call    cs:__imp_RtlIpv6AddressToStringA
0x18005bba5  nop     dword ptr [rax+rax+00h]
0x18005bbaa  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18005bbb1  jz      short loc_18005BBEA
0x18005bbb3  lea     r8, [rbp+860h+S]
0x18005bbb7  mov     word ptr [rbp+860h+var_840], r13w
0x18005bbbc  lea     rdx, aStaticPoolFrom; "Static Pool From Addr: %hs"
0x18005bbc3  lea     rcx, [rbp+860h+var_840]
0x18005bbc7  call    FormatRRASErrorString
0x18005bbcc  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005bbd3  lea     r8, [rbp+860h+var_840]
0x18005bbd7  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005bbde  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005bbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bbea  lea     rdx, [rbp+860h+S]; S
0x18005bbee  lea     rcx, [rsp+960h+Addr]; Addr
0x18005bbf3  call    cs:__imp_RtlIpv6AddressToStringA
0x18005bbfa  nop     dword ptr [rax+rax+00h]
0x18005bbff  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18005bc06  jz      loc_18005BF9E
0x18005bc0c  lea     r8, [rbp+860h+S]
0x18005bc10  mov     word ptr [rbp+860h+var_840], r13w
0x18005bc15  lea     rdx, aStaticPoolToAd; "Static Pool To   Addr: %hs"
0x18005bc1c  lea     rcx, [rbp+860h+var_840]
0x18005bc20  call    FormatRRASErrorString
0x18005bc25  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005bc2c  lea     r8, [rbp+860h+var_840]
0x18005bc30  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005bc37  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005bc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc43  jmp     loc_18005BF9E
0x18005bc48  lea     rax, [rsp+960h+hKey]
0x18005bc4d  mov     r9d, 20019h; samDesired
0x18005bc53  xor     r8d, r8d; ulOptions
0x18005bc56  mov     [rsp+960h+phkResult], rax; phkResult
0x18005bc5b  lea     rdx, aSystemCurrentc_18; "System\\CurrentControlSet\\Services\\Re"...
0x18005bc62  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005bc69  call    cs:__imp_RegOpenKeyExA
0x18005bc70  nop     dword ptr [rax+rax+00h]
0x18005bc75  test    eax, eax
0x18005bc77  jnz     loc_18005BFC1
0x18005bc7d  mov     r14d, r13d
0x18005bc80  mov     edi, r13d
0x18005bc83  xor     eax, eax
0x18005bc85  mov     byte ptr [rsp+960h+var_910.u], r13b
0x18005bc8a  mov     r9d, r14d
0x18005bc8d  mov     qword ptr [rsp+960h+var_910.u+1], rax
0x18005bc92  lea     r8, aD; "%d"
0x18005bc99  mov     dword ptr [rsp+960h+var_910.u+9], eax
0x18005bc9d  lea     rcx, [rbp+860h+pszDest]; pszDest
0x18005bca1  mov     word ptr [rsp+960h+var_910.u+0Dh], ax
0x18005bca6  lea     edx, [rax+0Ah]; cbDest
0x18005bca9  mov     byte ptr [rsp+960h+var_910.u+0Fh], al
0x18005bcad  mov     byte ptr [rsp+960h+var_8E8.u], r13b
0x18005bcb2  mov     qword ptr [rsp+960h+var_8E8.u+1], rax
0x18005bcb7  mov     dword ptr [rbp+860h+var_8E8.u+9], eax
0x18005bcba  mov     word ptr [rbp+860h+var_8E8.u+0Dh], ax
0x18005bcbe  mov     byte ptr [rbp+860h+var_8E8.u+0Fh], al
0x18005bcc1  mov     [rsp+960h+var_928], r13
0x18005bcc6  call    StringCbPrintfA
0x18005bccb  mov     rcx, [rsp+960h+hKey]; hKey
0x18005bcd0  lea     rax, [rsp+960h+var_928]
0x18005bcd5  mov     r9d, 20019h; samDesired
0x18005bcdb  mov     [rsp+960h+phkResult], rax; phkResult
0x18005bce0  xor     r8d, r8d; ulOptions
0x18005bce3  lea     rdx, [rbp+860h+pszDest]; lpSubKey
0x18005bce7  call    cs:__imp_RegOpenKeyExA
0x18005bcee  nop     dword ptr [rax+rax+00h]
0x18005bcf3  test    eax, eax
0x18005bcf5  jz      short loc_18005BD4C
0x18005bcf7  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18005bcfe  jz      short loc_18005BD42
0x18005bd00  lea     r9, aSystemCurrentc_18; "System\\CurrentControlSet\\Services\\Re"...
0x18005bd07  mov     word ptr [rbp+860h+var_840], r13w
0x18005bd0c  lea     r8, [rbp+860h+pszDest]
0x18005bd10  mov     dword ptr [rsp+960h+phkResult], eax
0x18005bd14  lea     rdx, aCouldnTOpenKey_0; "Couldn't open key %hs in %hs error:%ld"
0x18005bd1b  lea     rcx, [rbp+860h+var_840]
0x18005bd1f  call    FormatRRASErrorString
0x18005bd24  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005bd2b  lea     r8, [rbp+860h+var_840]
0x18005bd2f  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005bd36  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005bd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd42  mov     edi, 1
0x18005bd47  jmp     loc_18005BF78
0x18005bd4c  mov     rcx, [rsp+960h+var_928]; hKey
0x18005bd51  lea     rax, [rsp+960h+cbData]
0x18005bd56  mov     [rsp+960h+lpcbData], rax; lpcbData
0x18005bd5b  lea     r9, [rsp+960h+Type]; lpType
0x18005bd60  lea     rax, [rbp+860h+S]
0x18005bd64  mov     [rsp+960h+cbData], 80h
0x18005bd6c  xor     r8d, r8d; lpReserved
0x18005bd6f  mov     [rsp+960h+phkResult], rax; lpData
0x18005bd74  lea     rdx, aFrom; "From"
0x18005bd7b  call    cs:__imp_RegQueryValueExA
0x18005bd82  nop     dword ptr [rax+rax+00h]
0x18005bd87  test    eax, eax
0x18005bd89  jnz     loc_18005BF2D
0x18005bd8f  cmp     [rsp+960h+Type], 3
0x18005bd94  jnz     loc_18005BF2D
0x18005bd9a  cmp     [rsp+960h+cbData], 10h
0x18005bd9f  jnz     loc_18005BF2D
0x18005bda5  movaps  xmm0, xmmword ptr [rbp+860h+S]
0x18005bda9  lea     rax, [rsp+960h+cbData]
0x18005bdae  mov     rcx, [rsp+960h+var_928]; hKey
0x18005bdb3  lea     r9, [rsp+960h+Type]; lpType
0x18005bdb8  mov     [rsp+960h+lpcbData], rax; lpcbData
0x18005bdbd  lea     rdx, aTo; "To"
0x18005bdc4  lea     rax, [rbp+860h+S]
0x18005bdc8  mov     [rsp+960h+cbData], 80h
0x18005bdd0  xor     r8d, r8d; lpReserved
0x18005bdd3  mov     [rsp+960h+phkResult], rax; lpData
0x18005bdd8  movdqu  xmmword ptr [rsp+960h+var_910.u], xmm0
0x18005bdde  call    cs:__imp_RegQueryValueExA
0x18005bde5  nop     dword ptr [rax+rax+00h]
0x18005bdea  test    eax, eax
0x18005bdec  jnz     loc_18005BF1B
0x18005bdf2  cmp     [rsp+960h+Type], 3
0x18005bdf7  jnz     loc_18005BF1B
0x18005bdfd  cmp     [rsp+960h+cbData], 10h
0x18005be02  jnz     loc_18005BF1B
0x18005be08  movaps  xmm0, xmmword ptr [rbp+860h+S]
0x18005be0c  lea     edx, [rax+38h]; uBytes
0x18005be0f  lea     ecx, [rax+40h]; uFlags
0x18005be12  movdqu  xmmword ptr [rsp+960h+var_8E8.u], xmm0
0x18005be18  call    cs:__imp_LocalAlloc
0x18005be1f  nop     dword ptr [rax+rax+00h]
0x18005be24  mov     rbx, rax
0x18005be27  test    rax, rax
0x18005be2a  jnz     short loc_18005BE48
0x18005be2c  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005be33  test    rdx, rdx
0x18005be36  jz      loc_18005BD42
0x18005be3c  lea     r8, aOutOfMemory; "Out of memory"
0x18005be43  jmp     loc_18005BD2F
0x18005be48  movups  xmm0, xmmword ptr [rsp+960h+var_910.u]
0x18005be4d  lea     rdx, [rbp+860h+S]; S
0x18005be51  lea     rcx, [rsp+960h+var_910]; Addr
0x18005be56  movdqu  xmmword ptr [rax+8], xmm0
0x18005be5b  movups  xmm1, xmmword ptr [rsp+960h+var_910.u]
0x18005be60  movdqu  xmmword ptr [rax+28h], xmm1
0x18005be65  movups  xmm0, xmmword ptr [rsp+960h+var_8E8.u]
0x18005be6a  mov     [rax], r13
0x18005be6d  movdqu  xmmword ptr [rax+18h], xmm0
0x18005be72  call    cs:__imp_RtlIpv6AddressToStringA
0x18005be79  nop     dword ptr [rax+rax+00h]
0x18005be7e  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18005be85  jz      short loc_18005BEBE
0x18005be87  lea     r8, [rbp+860h+S]
0x18005be8b  mov     word ptr [rbp+860h+var_840], r13w
0x18005be90  lea     rdx, aStaticPoolFrom; "Static Pool From Addr: %hs"
0x18005be97  lea     rcx, [rbp+860h+var_840]
0x18005be9b  call    FormatRRASErrorString
0x18005bea0  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005bea7  lea     r8, [rbp+860h+var_840]
0x18005beab  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005beb2  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005beb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bebe  lea     rdx, [rbp+860h+S]; S
0x18005bec2  lea     rcx, [rsp+960h+var_8E8]; Addr
0x18005bec7  call    cs:__imp_RtlIpv6AddressToStringA
0x18005bece  nop     dword ptr [rax+rax+00h]
0x18005bed3  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18005beda  jz      short loc_18005BF13
0x18005bedc  lea     r8, [rbp+860h+S]
0x18005bee0  mov     word ptr [rbp+860h+var_840], r13w
0x18005bee5  lea     rdx, aStaticPoolToAd; "Static Pool To   Addr: %hs"
0x18005beec  lea     rcx, [rbp+860h+var_840]
0x18005bef0  call    FormatRRASErrorString
0x18005bef5  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005befc  lea     r8, [rbp+860h+var_840]
0x18005bf00  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005bf07  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005bf0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf13  mov     [r15], rbx
0x18005bf16  mov     r15, rbx
0x18005bf19  jmp     short loc_18005BF78
0x18005bf1b  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18005bf22  jz      short loc_18005BF78
0x18005bf24  lea     r8, aTo; "To"
0x18005bf2b  jmp     short loc_18005BF3D
0x18005bf2d  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18005bf34  jz      short loc_18005BF78
0x18005bf36  lea     r8, aFrom; "From"
0x18005bf3d  lea     r9, [rbp+860h+pszDest]
0x18005bf41  mov     dword ptr [rsp+960h+phkResult], eax
0x18005bf45  lea     rdx, aCouldnTReadVal; "Couldn't read value %hs in key %hs: %d"
0x18005bf4c  mov     word ptr [rbp+860h+var_840], r13w
0x18005bf51  lea     rcx, [rbp+860h+var_840]
0x18005bf55  call    FormatRRASErrorString
0x18005bf5a  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005bf61  lea     r8, [rbp+860h+var_840]
0x18005bf65  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005bf6c  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005bf73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf78  mov     rcx, [rsp+960h+var_928]; hKey
0x18005bf7d  test    rcx, rcx
0x18005bf80  jz      short loc_18005BF8E
0x18005bf82  call    cs:__imp_RegCloseKey
0x18005bf89  nop     dword ptr [rax+rax+00h]
0x18005bf8e  inc     r14d
0x18005bf91  test    edi, edi
0x18005bf93  jz      loc_18005BC83
0x18005bf99  mov     rbx, [rsp+960h+var_918]
0x18005bf9e  mov     [r12], rbx
0x18005bfa2  test    esi, esi
0x18005bfa4  jz      short loc_18005BFC1
0x18005bfa6  mov     rax, cs:qword_1800CF690
0x18005bfad  test    rax, rax
0x18005bfb0  jz      short loc_18005BFC1
0x18005bfb2  lea     rdx, [rsp+960h+Addr]
0x18005bfb7  mov     ecx, 2
0x18005bfbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bfc1  mov     rcx, [rsp+960h+hKey]; hKey
0x18005bfc6  test    rcx, rcx
0x18005bfc9  jz      short loc_18005BFD7
0x18005bfcb  call    cs:__imp_RegCloseKey
  ... truncated ...
```
