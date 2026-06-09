# RasStatIpv6CreatePrefixList

- ea: `0x180059ac8`
- end: `0x18005a0f1`
- name: `RasStatIpv6CreatePrefixList`
- size: `1577`
- prototype: `__int64 __fastcall(void *Buf1)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180050870`
- `0x180055114`

## callees

- `0x180002bbe`
- `0x18001945c`
- `0x180025c98`
- `0x180059ac8`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180059bc0`
- `KERNEL32!LocalAlloc` at `0x180059f45`
- `KERNEL32!LocalAlloc` at `0x180059bc0`
- `KERNEL32!LocalAlloc` at `0x180059f45`
- `ADVAPI32!RegCloseKey` at `0x18005a09e`
- `ADVAPI32!RegCloseKey` at `0x18005a0c1`
- `ADVAPI32!RegCloseKey` at `0x18005a09e`
- `ADVAPI32!RegCloseKey` at `0x18005a0c1`
- `ADVAPI32!RegOpenKeyExA` at `0x180059d6c`
- `ADVAPI32!RegOpenKeyExA` at `0x180059dec`
- `ADVAPI32!RegOpenKeyExA` at `0x180059d6c`
- `ADVAPI32!RegOpenKeyExA` at `0x180059dec`
- `ADVAPI32!RegQueryValueExA` at `0x180059e77`
- `ADVAPI32!RegQueryValueExA` at `0x180059ef3`
- `ADVAPI32!RegQueryValueExA` at `0x180059e77`
- `ADVAPI32!RegQueryValueExA` at `0x180059ef3`
- `ntdll!RtlIpv6AddressToStringA` at `0x180059c89`
- `ntdll!RtlIpv6AddressToStringA` at `0x180059cd8`
- `ntdll!RtlIpv6AddressToStringA` at `0x180059f99`
- `ntdll!RtlIpv6AddressToStringA` at `0x180059fe8`
- `ntdll!RtlIpv6AddressToStringA` at `0x180059c89`
- `ntdll!RtlIpv6AddressToStringA` at `0x180059cd8`
- `ntdll!RtlIpv6AddressToStringA` at `0x180059f99`
- `ntdll!RtlIpv6AddressToStringA` at `0x180059fe8`

## string_xrefs

- `0x180059b58`: `RasStatIpv6CreatePrefixList`
- `0x180059d5e`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6\StaticPrefixPool`
- `0x180059dff`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6\StaticPrefixPool`
- `0x180059e13`: `Couldn't open key %hs in %hs error:%ld`
- `0x18005a061`: `Couldn't read value %hs in key %hs: %d`

## pseudocode

```c
unsigned int __fastcall RasStatIpv6CreatePrefixList(void *Buf1, _QWORD *a2)
{
  char *v4; // rbx
  int v5; // esi
  unsigned int result; // eax
  char *v7; // rax
  __int64 *v8; // r12
  int v9; // r15d
  int v10; // edi
  LSTATUS v11; // eax
  __int64 v12; // rdx
  const wchar_t *v13; // r8
  LSTATUS v14; // eax
  char *v15; // rax
  __int64 *v16; // rbx
  struct in6_addr v17; // xmm0
  const CHAR *v18; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY v23; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  struct in6_addr Addr; // [rsp+50h] [rbp-B0h] BYREF
  struct in6_addr v27; // [rsp+68h] [rbp-98h] BYREF
  struct in6_addr v28; // [rsp+78h] [rbp-88h] BYREF
  char pszDest[24]; // [rsp+88h] [rbp-78h] BYREF
  struct in6_addr S[8]; // [rsp+A0h] [rbp-60h] BYREF
  int v31; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v32[2044]; // [rsp+124h] [rbp+24h] BYREF

  hKey = 0;
  v23 = 0;
  Type = 0;
  v4 = 0;
  cbData = 0;
  v25 = 0;
  memset(&Addr, 0, 20);
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
      L"RasStatIpv6CreatePrefixList");
  if ( !dword_1800C8650 || !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
  {
    result = RegOpenKeyExA(
               HKEY_LOCAL_MACHINE,
               "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ipv6\\StaticPrefixPool",
               0,
               0x20019u,
               &hKey);
    if ( result )
      goto LABEL_46;
    v8 = &v25;
    v9 = 0;
    v10 = 0;
    while ( 1 )
    {
      v27.u.Byte[0] = 0;
      *(_QWORD *)&v27.u.Byte[1] = 0;
      *(_DWORD *)((char *)&v27.u.Word[4] + 1) = 0;
      *(USHORT *)((char *)&v27.u.Word[6] + 1) = 0;
      v27.u.Byte[15] = 0;
      v28.u.Byte[0] = 0;
      *(_QWORD *)&v28.u.Byte[1] = 0;
      *(_DWORD *)((char *)&v28.u.Word[4] + 1) = 0;
      *(USHORT *)((char *)&v28.u.Word[6] + 1) = 0;
      v28.u.Byte[15] = 0;
      v23 = 0;
      StringCbPrintfA(pszDest, 0xAu, "%d", v9);
      v11 = RegOpenKeyExA(hKey, pszDest, 0, 0x20019u, &v23);
      if ( v11 )
        break;
      cbData = 128;
      v14 = RegQueryValueExA(v23, "From", 0, &Type, S[0].u.Byte, &cbData);
      if ( !v14 && Type == 3 && cbData == 16 )
      {
        v27 = S[0];
        cbData = 128;
        v14 = RegQueryValueExA(v23, "To", 0, &Type, S[0].u.Byte, &cbData);
        if ( !v14 && Type == 3 && cbData == 16 )
        {
          v28 = S[0];
          v15 = (char *)LocalAlloc(0x40u, 0x38u);
          v16 = (__int64 *)v15;
          if ( v15 )
          {
            *(struct in6_addr *)(v15 + 8) = v27;
            *(struct in6_addr *)(v15 + 40) = v27;
            v17 = v28;
            *(_QWORD *)v15 = 0;
            *(struct in6_addr *)(v15 + 24) = v17;
            RtlIpv6AddressToStringA(&v27, (PSTR)S);
            if ( (_QWORD)xmmword_1800C9740 )
            {
              LOWORD(v31) = 0;
              FormatRRASErrorString(&v31, L"Static Pool From Addr: %hs", S);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
                gRasIpAddrMgmtEtwContext,
                xmmword_1800C9740,
                &v31);
            }
            RtlIpv6AddressToStringA(&v28, (PSTR)S);
            if ( (_QWORD)xmmword_1800C9740 )
            {
              LOWORD(v31) = 0;
              FormatRRASErrorString(&v31, L"Static Pool To   Addr: %hs", S);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
                gRasIpAddrMgmtEtwContext,
                xmmword_1800C9740,
                &v31);
            }
            *v8 = (__int64)v16;
            v8 = v16;
            goto LABEL_42;
          }
          v12 = *((_QWORD *)&xmmword_1800C9740 + 1);
          if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
          {
            v13 = L"Out of memory";
LABEL_21:
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              v12,
              v13);
          }
LABEL_22:
          v10 = 1;
          goto LABEL_42;
        }
        if ( (_QWORD)xmmword_1800C9740 )
        {
          v18 = "To";
LABEL_41:
          LODWORD(phkResulta) = v14;
          LOWORD(v31) = 0;
          FormatRRASErrorString(&v31, L"Couldn't read value %hs in key %hs: %d", v18, pszDest, phkResulta);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v31);
        }
      }
      else if ( (_QWORD)xmmword_1800C9740 )
      {
        v18 = "From";
        goto LABEL_41;
      }
LABEL_42:
      if ( v23 )
        RegCloseKey(v23);
      ++v9;
      if ( v10 )
      {
        result = v25;
        *a2 = v25;
        goto LABEL_46;
      }
    }
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v31) = 0;
      LODWORD(phkResult) = v11;
      FormatRRASErrorString(
        &v31,
        L"Couldn't open key %hs in %hs error:%ld",
        pszDest,
        "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ipv6\\StaticPrefixPool",
        phkResult);
      v12 = xmmword_1800C9740;
      v13 = (const wchar_t *)&v31;
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  v5 = 0;
  result = GetRoutingDomainConfigData(Buf1, 2, 20, &Addr);
  if ( result )
    goto LABEL_13;
  v7 = (char *)LocalAlloc(0x40u, 0x38u);
  v4 = v7;
  if ( v7 )
  {
    v7[8] = Addr.u.Byte[0];
    v5 = 1;
    *(_QWORD *)(v7 + 9) = *(_QWORD *)&Addr.u.Byte[1];
    *(_DWORD *)(v7 + 17) = *(_DWORD *)((char *)&Addr.u.Word[4] + 1);
    *(_WORD *)(v7 + 21) = *(USHORT *)((char *)&Addr.u.Word[6] + 1);
    v7[23] = Addr.u.Byte[15];
    v7[40] = Addr.u.Byte[0];
    *(_QWORD *)(v7 + 41) = *(_QWORD *)&Addr.u.Byte[1];
    *(_DWORD *)(v7 + 49) = *(_DWORD *)((char *)&Addr.u.Word[4] + 1);
    *(_WORD *)(v7 + 53) = *(USHORT *)((char *)&Addr.u.Word[6] + 1);
    v7[55] = Addr.u.Byte[15];
    v7[24] = Addr.u.Byte[0];
    *(_QWORD *)(v7 + 25) = *(_QWORD *)&Addr.u.Byte[1];
    *(_DWORD *)(v7 + 33) = *(_DWORD *)((char *)&Addr.u.Word[4] + 1);
    *(_WORD *)(v7 + 37) = *(USHORT *)((char *)&Addr.u.Word[6] + 1);
    v7[39] = Addr.u.Byte[15];
    *(_QWORD *)v7 = 0;
    RtlIpv6AddressToStringA(&Addr, (PSTR)S);
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v31) = 0;
      FormatRRASErrorString(&v31, L"Static Pool From Addr: %hs", S);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v31);
    }
    result = (unsigned int)RtlIpv6AddressToStringA(&Addr, (PSTR)S);
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v31) = 0;
      FormatRRASErrorString(&v31, L"Static Pool To   Addr: %hs", S);
      result = ((__int64 (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
                 gRasIpAddrMgmtEtwContext,
                 xmmword_1800C9740,
                 &v31);
    }
LABEL_13:
    *a2 = v4;
    if ( !v5 )
      goto LABEL_46;
    goto LABEL_14;
  }
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
      L"Out of memory");
LABEL_14:
  result = (unsigned int)qword_1800C8690;
  if ( qword_1800C8690 )
    result = qword_1800C8690(2, &Addr);
LABEL_46:
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x180059ac8  mov     [rsp-8+arg_10], rbx
0x180059acd  push    rbp
0x180059ace  push    rsi
0x180059acf  push    rdi
0x180059ad0  push    r12
0x180059ad2  push    r13
0x180059ad4  push    r14
0x180059ad6  push    r15
0x180059ad8  lea     rbp, [rsp-830h]
0x180059ae0  sub     rsp, 930h
0x180059ae7  mov     rax, cs:__security_cookie
0x180059aee  xor     rax, rsp
0x180059af1  mov     [rbp+860h+var_40], rax
0x180059af8  xor     r13d, r13d
0x180059afb  xorps   xmm0, xmm0
0x180059afe  mov     r14, rdx
0x180059b01  mov     [rsp+960h+hKey], r13
0x180059b06  mov     rdi, rcx
0x180059b09  mov     [rsp+960h+var_928], r13
0x180059b0e  xor     eax, eax
0x180059b10  mov     [rsp+960h+Type], r13d
0x180059b15  movups  xmmword ptr [rsp+960h+Addr.u+1], xmm0
0x180059b1a  mov     ebx, r13d
0x180059b1d  mov     [rsp+960h+cbData], r13d
0x180059b22  xor     edx, edx; Val
0x180059b24  mov     [rsp+960h+var_918], rbx
0x180059b29  mov     r8d, 7FCh; Size
0x180059b2f  mov     byte ptr [rsp+960h+Addr.u], r13b
0x180059b34  lea     rcx, [rbp+860h+var_83C]; void *
0x180059b38  mov     [rsp+60h], eax
0x180059b3c  mov     [rbp+860h+var_840], r13d
0x180059b40  call    memset_0
0x180059b45  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x180059b4c  test    rdx, rdx
0x180059b4f  jz      short loc_180059B6B
0x180059b51  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180059b58  lea     r8, aRasstatipv6cre; "RasStatIpv6CreatePrefixList"
0x180059b5f  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180059b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b6b  cmp     cs:dword_1800C8650, r13d
0x180059b72  jz      loc_180059D4B
0x180059b78  mov     r8d, 10h; Size
0x180059b7e  lea     rdx, GUID_NULL; Buf2
0x180059b85  mov     rcx, rdi; Buf1
0x180059b88  call    memcmp_0
0x180059b8d  test    eax, eax
0x180059b8f  jz      loc_180059D4B
0x180059b95  mov     r8d, 14h
0x180059b9b  lea     r9, [rsp+960h+Addr]
0x180059ba0  mov     rcx, rdi
0x180059ba3  mov     esi, r13d
0x180059ba6  lea     r15d, [r8-12h]
0x180059baa  mov     edx, r15d
0x180059bad  call    GetRoutingDomainConfigData
0x180059bb2  test    eax, eax
0x180059bb4  jnz     loc_180059D1E
0x180059bba  lea     edx, [rax+38h]; uBytes
0x180059bbd  lea     ecx, [rax+40h]; uFlags
0x180059bc0  call    cs:__imp_LocalAlloc
0x180059bc6  mov     rbx, rax
0x180059bc9  test    rax, rax
0x180059bcc  jnz     short loc_180059BFD
0x180059bce  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x180059bd5  test    rdx, rdx
0x180059bd8  jz      loc_180059D29
0x180059bde  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180059be5  lea     r8, aOutOfMemory; "Out of memory"
0x180059bec  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180059bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059bf8  jmp     loc_180059D29
0x180059bfd  mov     al, byte ptr [rsp+960h+Addr.u]
0x180059c01  lea     rdx, [rbp+860h+S]; S
0x180059c05  mov     [rbx+8], al
0x180059c08  lea     rcx, [rsp+960h+Addr]; Addr
0x180059c0d  movsd   xmm0, qword ptr [rsp+960h+Addr.u+1]
0x180059c13  mov     esi, 1
0x180059c18  movsd   qword ptr [rbx+9], xmm0
0x180059c1d  mov     eax, dword ptr [rsp+960h+Addr.u+9]
0x180059c21  mov     [rbx+11h], eax
0x180059c24  movzx   eax, word ptr [rsp+960h+Addr.u+0Dh]
0x180059c29  mov     [rbx+15h], ax
0x180059c2d  mov     al, byte ptr [rsp+960h+Addr.u+0Fh]
0x180059c31  mov     [rbx+17h], al
0x180059c34  mov     al, byte ptr [rsp+960h+Addr.u]
0x180059c38  mov     [rbx+28h], al
0x180059c3b  movsd   xmm0, qword ptr [rsp+960h+Addr.u+1]
0x180059c41  movsd   qword ptr [rbx+29h], xmm0
0x180059c46  mov     eax, dword ptr [rsp+960h+Addr.u+9]
0x180059c4a  mov     [rbx+31h], eax
0x180059c4d  movzx   eax, word ptr [rsp+960h+Addr.u+0Dh]
0x180059c52  mov     [rbx+35h], ax
0x180059c56  mov     al, byte ptr [rsp+960h+Addr.u+0Fh]
0x180059c5a  mov     [rbx+37h], al
0x180059c5d  mov     al, byte ptr [rsp+960h+Addr.u]
0x180059c61  mov     [rbx+18h], al
0x180059c64  movsd   xmm0, qword ptr [rsp+960h+Addr.u+1]
0x180059c6a  movsd   qword ptr [rbx+19h], xmm0
0x180059c6f  mov     eax, dword ptr [rsp+960h+Addr.u+9]
0x180059c73  mov     [rbx+21h], eax
0x180059c76  movzx   eax, word ptr [rsp+960h+Addr.u+0Dh]
0x180059c7b  mov     [rbx+25h], ax
0x180059c7f  mov     al, byte ptr [rsp+960h+Addr.u+0Fh]
0x180059c83  mov     [rbx+27h], al
0x180059c86  mov     [rbx], r13
0x180059c89  call    cs:__imp_RtlIpv6AddressToStringA
0x180059c8f  cmp     qword ptr cs:xmmword_1800C9740, r13
0x180059c96  jz      short loc_180059CCF
0x180059c98  lea     r8, [rbp+860h+S]
0x180059c9c  mov     word ptr [rbp+860h+var_840], r13w
0x180059ca1  lea     rdx, aStaticPoolFrom; "Static Pool From Addr: %hs"
0x180059ca8  lea     rcx, [rbp+860h+var_840]
0x180059cac  call    FormatRRASErrorString
0x180059cb1  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180059cb8  lea     r8, [rbp+860h+var_840]
0x180059cbc  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180059cc3  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180059cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ccf  lea     rdx, [rbp+860h+S]; S
0x180059cd3  lea     rcx, [rsp+960h+Addr]; Addr
0x180059cd8  call    cs:__imp_RtlIpv6AddressToStringA
0x180059cde  cmp     qword ptr cs:xmmword_1800C9740, r13
0x180059ce5  jz      short loc_180059D1E
0x180059ce7  lea     r8, [rbp+860h+S]
0x180059ceb  mov     word ptr [rbp+860h+var_840], r13w
0x180059cf0  lea     rdx, aStaticPoolToAd; "Static Pool To   Addr: %hs"
0x180059cf7  lea     rcx, [rbp+860h+var_840]
0x180059cfb  call    FormatRRASErrorString
0x180059d00  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180059d07  lea     r8, [rbp+860h+var_840]
0x180059d0b  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180059d12  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180059d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d1e  mov     [r14], rbx
0x180059d21  test    esi, esi
0x180059d23  jz      loc_18005A0B7
0x180059d29  mov     rax, cs:qword_1800C8690
0x180059d30  test    rax, rax
0x180059d33  jz      loc_18005A0B7
0x180059d39  lea     rdx, [rsp+960h+Addr]
0x180059d3e  mov     ecx, r15d
0x180059d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d46  jmp     loc_18005A0B7
0x180059d4b  lea     rax, [rsp+960h+hKey]
0x180059d50  mov     r9d, 20019h; samDesired
0x180059d56  xor     r8d, r8d; ulOptions
0x180059d59  mov     [rsp+960h+phkResult], rax; phkResult
0x180059d5e  lea     rdx, aSystemCurrentc_18; "System\\CurrentControlSet\\Services\\Re"...
0x180059d65  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180059d6c  call    cs:__imp_RegOpenKeyExA
0x180059d72  test    eax, eax
0x180059d74  jnz     loc_18005A0B7
0x180059d7a  lea     r12, [rsp+960h+var_918]
0x180059d7f  mov     r15d, r13d
0x180059d82  mov     edi, r13d
0x180059d85  lea     esi, [rax+1]
0x180059d88  xor     eax, eax
0x180059d8a  mov     byte ptr [rsp+960h+var_8F8.u], r13b
0x180059d8f  mov     r9d, r15d
0x180059d92  mov     qword ptr [rsp+960h+var_8F8.u+1], rax
0x180059d97  lea     r8, aD; "%d"
0x180059d9e  mov     dword ptr [rsp+960h+var_8F8.u+9], eax
0x180059da2  lea     rcx, [rbp+860h+pszDest]; pszDest
0x180059da6  mov     word ptr [rsp+960h+var_8F8.u+0Dh], ax
0x180059dab  lea     edx, [rax+0Ah]; cbDest
0x180059dae  mov     byte ptr [rsp+960h+var_8F8.u+0Fh], al
0x180059db2  mov     byte ptr [rsp+960h+var_8E8.u], r13b
0x180059db7  mov     qword ptr [rsp+960h+var_8E8.u+1], rax
0x180059dbc  mov     dword ptr [rbp+860h+var_8E8.u+9], eax
0x180059dbf  mov     word ptr [rbp+860h+var_8E8.u+0Dh], ax
0x180059dc3  mov     byte ptr [rbp+860h+var_8E8.u+0Fh], al
0x180059dc6  mov     [rsp+960h+var_928], r13
0x180059dcb  call    StringCbPrintfA
0x180059dd0  mov     rcx, [rsp+960h+hKey]; hKey
0x180059dd5  lea     rax, [rsp+960h+var_928]
0x180059dda  mov     r9d, 20019h; samDesired
0x180059de0  mov     [rsp+960h+phkResult], rax; phkResult
0x180059de5  xor     r8d, r8d; ulOptions
0x180059de8  lea     rdx, [rbp+860h+pszDest]; lpSubKey
0x180059dec  call    cs:__imp_RegOpenKeyExA
0x180059df2  test    eax, eax
0x180059df4  jz      short loc_180059E48
0x180059df6  cmp     qword ptr cs:xmmword_1800C9740, r13
0x180059dfd  jz      short loc_180059E41
0x180059dff  lea     r9, aSystemCurrentc_18; "System\\CurrentControlSet\\Services\\Re"...
0x180059e06  mov     word ptr [rbp+860h+var_840], r13w
0x180059e0b  lea     r8, [rbp+860h+pszDest]
0x180059e0f  mov     dword ptr [rsp+960h+phkResult], eax
0x180059e13  lea     rdx, aCouldnTOpenKey_0; "Couldn't open key %hs in %hs error:%ld"
0x180059e1a  lea     rcx, [rbp+860h+var_840]
0x180059e1e  call    FormatRRASErrorString
0x180059e23  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180059e2a  lea     r8, [rbp+860h+var_840]
0x180059e2e  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180059e35  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180059e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e41  mov     edi, esi
0x180059e43  jmp     loc_18005A094
0x180059e48  mov     rcx, [rsp+960h+var_928]; hKey
0x180059e4d  lea     rax, [rsp+960h+cbData]
0x180059e52  mov     [rsp+960h+lpcbData], rax; lpcbData
0x180059e57  lea     r9, [rsp+960h+Type]; lpType
0x180059e5c  lea     rax, [rbp+860h+S]
0x180059e60  mov     [rsp+960h+cbData], 80h
0x180059e68  xor     r8d, r8d; lpReserved
0x180059e6b  mov     [rsp+960h+phkResult], rax; lpData
0x180059e70  lea     rdx, aFrom; "From"
0x180059e77  call    cs:__imp_RegQueryValueExA
0x180059e7d  test    eax, eax
0x180059e7f  jnz     loc_18005A049
0x180059e85  cmp     [rsp+960h+Type], 3
0x180059e8a  jnz     loc_18005A049
0x180059e90  cmp     [rsp+960h+cbData], 10h
0x180059e95  jnz     loc_18005A049
0x180059e9b  mov     al, [rbp+860h+S]
0x180059e9e  lea     r9, [rsp+960h+Type]; lpType
0x180059ea3  movsd   xmm0, [rbp+860h+var_8BF]
0x180059ea8  lea     rdx, aTo; "To"
0x180059eaf  mov     rcx, [rsp+960h+var_928]; hKey
0x180059eb4  xor     r8d, r8d; lpReserved
0x180059eb7  mov     byte ptr [rsp+960h+var_8F8.u], al
0x180059ebb  mov     eax, [rbp+860h+var_8B7]
0x180059ebe  mov     dword ptr [rsp+960h+var_8F8.u+9], eax
0x180059ec2  movzx   eax, [rbp+860h+var_8B3]
0x180059ec6  mov     word ptr [rsp+960h+var_8F8.u+0Dh], ax
0x180059ecb  mov     al, [rbp+860h+var_8B1]
0x180059ece  mov     byte ptr [rsp+960h+var_8F8.u+0Fh], al
0x180059ed2  lea     rax, [rsp+960h+cbData]
0x180059ed7  mov     [rsp+960h+lpcbData], rax; lpcbData
0x180059edc  lea     rax, [rbp+860h+S]
0x180059ee0  mov     [rsp+960h+phkResult], rax; lpData
0x180059ee5  movsd   qword ptr [rsp+960h+var_8F8.u+1], xmm0
0x180059eeb  mov     [rsp+960h+cbData], 80h
0x180059ef3  call    cs:__imp_RegQueryValueExA
0x180059ef9  test    eax, eax
0x180059efb  jnz     loc_18005A037
0x180059f01  cmp     [rsp+960h+Type], 3
0x180059f06  jnz     loc_18005A037
0x180059f0c  cmp     [rsp+960h+cbData], 10h
0x180059f11  jnz     loc_18005A037
0x180059f17  mov     al, [rbp+860h+S]
0x180059f1a  mov     edx, 38h ; '8'; uBytes
0x180059f1f  movsd   xmm0, [rbp+860h+var_8BF]
0x180059f24  mov     byte ptr [rsp+960h+var_8E8.u], al
0x180059f28  mov     eax, [rbp+860h+var_8B7]
0x180059f2b  mov     dword ptr [rbp+860h+var_8E8.u+9], eax
0x180059f2e  lea     ecx, [rdx+8]; uFlags
0x180059f31  movzx   eax, [rbp+860h+var_8B3]
0x180059f35  mov     word ptr [rbp+860h+var_8E8.u+0Dh], ax
0x180059f39  mov     al, [rbp+860h+var_8B1]
0x180059f3c  mov     byte ptr [rbp+860h+var_8E8.u+0Fh], al
0x180059f3f  movsd   qword ptr [rsp+960h+var_8E8.u+1], xmm0
0x180059f45  call    cs:__imp_LocalAlloc
0x180059f4b  mov     rbx, rax
0x180059f4e  test    rax, rax
0x180059f51  jnz     short loc_180059F6F
0x180059f53  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x180059f5a  test    rdx, rdx
0x180059f5d  jz      loc_180059E41
0x180059f63  lea     r8, aOutOfMemory; "Out of memory"
0x180059f6a  jmp     loc_180059E2E
0x180059f6f  movups  xmm0, xmmword ptr [rsp+960h+var_8F8.u]
0x180059f74  lea     rdx, [rbp+860h+S]; S
0x180059f78  lea     rcx, [rsp+960h+var_8F8]; Addr
0x180059f7d  movdqu  xmmword ptr [rax+8], xmm0
0x180059f82  movups  xmm1, xmmword ptr [rsp+960h+var_8F8.u]
0x180059f87  movdqu  xmmword ptr [rax+28h], xmm1
0x180059f8c  movups  xmm0, xmmword ptr [rsp+960h+var_8E8.u]
0x180059f91  mov     [rax], r13
0x180059f94  movdqu  xmmword ptr [rax+18h], xmm0
0x180059f99  call    cs:__imp_RtlIpv6AddressToStringA
0x180059f9f  cmp     qword ptr cs:xmmword_1800C9740, r13
0x180059fa6  jz      short loc_180059FDF
0x180059fa8  lea     r8, [rbp+860h+S]
0x180059fac  mov     word ptr [rbp+860h+var_840], r13w
0x180059fb1  lea     rdx, aStaticPoolFrom; "Static Pool From Addr: %hs"
0x180059fb8  lea     rcx, [rbp+860h+var_840]
0x180059fbc  call    FormatRRASErrorString
0x180059fc1  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180059fc8  lea     r8, [rbp+860h+var_840]
0x180059fcc  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180059fd3  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180059fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fdf  lea     rdx, [rbp+860h+S]; S
0x180059fe3  lea     rcx, [rsp+960h+var_8E8]; Addr
0x180059fe8  call    cs:__imp_RtlIpv6AddressToStringA
0x180059fee  cmp     qword ptr cs:xmmword_1800C9740, r13
0x180059ff5  jz      short loc_18005A02E
0x180059ff7  lea     r8, [rbp+860h+S]
0x180059ffb  mov     word ptr [rbp+860h+var_840], r13w
0x18005a000  lea     rdx, aStaticPoolToAd; "Static Pool To   Addr: %hs"
0x18005a007  lea     rcx, [rbp+860h+var_840]
0x18005a00b  call    FormatRRASErrorString
0x18005a010  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005a017  lea     r8, [rbp+860h+var_840]
0x18005a01b  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005a022  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005a029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a02e  mov     [r12], rbx
0x18005a032  mov     r12, rbx
0x18005a035  jmp     short loc_18005A094
  ... truncated ...
```
