# RasStatCreatePoolList

- ea: `0x18005bd78`
- end: `0x18005c3e5`
- name: `RasStatCreatePoolList`
- size: `1645`
- prototype: `__int64 __fastcall(void *Buf1)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180050110`
- `0x180055114`

## callees

- `0x180002bbe`
- `0x18001945c`
- `0x180025c98`
- `0x18005bc4c`
- `0x18005bd78`
- `0x18005c9bc`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18005bfb2`
- `KERNEL32!LocalAlloc` at `0x18005c220`
- `KERNEL32!LocalAlloc` at `0x18005bfb2`
- `KERNEL32!LocalAlloc` at `0x18005c220`
- `ADVAPI32!RegCloseKey` at `0x18005c364`
- `ADVAPI32!RegCloseKey` at `0x18005c3b5`
- `ADVAPI32!RegCloseKey` at `0x18005c364`
- `ADVAPI32!RegCloseKey` at `0x18005c3b5`
- `ADVAPI32!RegOpenKeyExA` at `0x18005be53`
- `ADVAPI32!RegOpenKeyExA` at `0x18005c0fb`
- `ADVAPI32!RegOpenKeyExA` at `0x18005be53`
- `ADVAPI32!RegOpenKeyExA` at `0x18005c0fb`
- `ADVAPI32!RegQueryValueExA` at `0x18005c183`
- `ADVAPI32!RegQueryValueExA` at `0x18005c1d0`
- `ADVAPI32!RegQueryValueExA` at `0x18005c183`
- `ADVAPI32!RegQueryValueExA` at `0x18005c1d0`

## string_xrefs

- `0x18005c327`: `Couldn't read value %hs in key %hs: %d`
- `0x18005be19`: `RasStatCreatePoolList`
- `0x18005be45`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip\StaticAddressPool`
- `0x18005bee0`: `No Pool information found in ConfigStore... Using APIPA address`
- `0x18005bf29`: `Acquired IP pool details from the Global configuration object.. Creating IP Pool from the same`
- `0x18005c11a`: `Couldn't open key %hs in key :%ld`

## pseudocode

```c
LSTATUS __fastcall RasStatCreatePoolList(GUID *Buf1, _QWORD *a2, __int64 *a3)
{
  int v5; // ebx
  LSTATUS result; // eax
  unsigned int v7; // r12d
  int RoutingDomainConfigData; // eax
  __int64 v9; // rdx
  unsigned int v10; // r13d
  unsigned int v11; // r14d
  unsigned int v12; // esi
  unsigned int v13; // ecx
  unsigned int j; // r8d
  __int64 *v15; // rax
  __int64 v16; // r9
  __int64 *v17; // rdi
  __int64 v18; // r15
  bool v19; // zf
  __int64 *v20; // rax
  int v21; // edi
  unsigned int v22; // eax
  __int64 v23; // rdx
  const wchar_t *v24; // r8
  LSTATUS v25; // eax
  unsigned int v26; // esi
  unsigned int v27; // r15d
  unsigned int v28; // r13d
  unsigned int v29; // ecx
  unsigned int i; // r8d
  __int64 *v31; // rax
  __int64 v32; // r9
  __int64 *v33; // rdi
  __int64 v34; // r14
  __int64 *v35; // rax
  const CHAR *v36; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  GUID *v42; // [rsp+40h] [rbp-C0h]
  int v43; // [rsp+48h] [rbp-B8h]
  HKEY v44; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h]
  __int64 *v46; // [rsp+60h] [rbp-A0h]
  __int128 v47; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v49[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v50; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v51; // [rsp+90h] [rbp-70h]
  _QWORD *v52; // [rsp+98h] [rbp-68h]
  GUID v53; // [rsp+A0h] [rbp-60h] BYREF
  char pszDest[16]; // [rsp+B0h] [rbp-50h] BYREF
  int v55; // [rsp+C0h] [rbp-40h] BYREF
  char v56[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v51 = a3;
  v52 = a2;
  v42 = Buf1;
  hKey = 0;
  v44 = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  v50 = 0;
  v47 = 0;
  v55 = 0;
  v49[0] = -1442971391;
  v49[1] = -1442970368;
  memset_0(v56, 0, sizeof(v56));
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
      L"RasStatCreatePoolList");
  v5 = dword_1800C8650;
  if ( RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip\\StaticAddressPool",
         0,
         0x20019u,
         &hKey)
    && !v5 )
  {
    result = rasStatCreatePoolListFromOldValues(a2, v51);
    goto LABEL_59;
  }
  v43 = 0;
  v46 = &v50;
  v7 = 0;
  v45 = 0;
  if ( !v5 || !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
  {
    v21 = 0;
    LODWORD(v42) = 0;
    while ( 1 )
    {
      v44 = 0;
      StringCbPrintfA(pszDest, 0xAu, "%d", v7);
      v22 = RegOpenKeyExA(hKey, pszDest, 0, 0x20019u, &v44);
      if ( v22 )
        break;
      cbData = 4;
      v25 = RegQueryValueExA(v44, "From", 0, &Type, Data, &cbData);
      if ( v25 || Type != 4 )
      {
        if ( (_QWORD)xmmword_1800C9740 )
        {
          v36 = "From";
          goto LABEL_52;
        }
      }
      else
      {
        v26 = *(_DWORD *)Data;
        cbData = 4;
        v25 = RegQueryValueExA(v44, "To", 0, &Type, Data, &cbData);
        if ( !v25 && Type == 4 )
        {
          v27 = *(_DWORD *)Data;
          v28 = 0;
          v29 = 0;
          for ( i = 0; i < 0x20; ++i )
          {
            v29 = (v29 >> 1) | 0x80000000;
            if ( (~(v26 ^ *(_DWORD *)Data) & v29) != v29 )
              break;
            v28 = v29;
          }
          v31 = (__int64 *)LocalAlloc(0x40u, 0x18u);
          v33 = v31;
          if ( v31 )
          {
            *((_DWORD *)v31 + 2) = v26;
            *((_DWORD *)v31 + 3) = v27;
            *((_DWORD *)v31 + 5) = v26;
            *((_DWORD *)v31 + 4) = v28;
            v34 = v45 & -(__int64)(v7 != 0);
            v19 = (_QWORD)xmmword_1800C9740 == 0;
            *v31 = 0;
            if ( !v19 )
            {
              LODWORD(phkResulta) = v28;
              LOWORD(v55) = 0;
              FormatRRASErrorString(&v55, L"0x%x...0x%x/0x%x", v26, v27, phkResulta);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
                gRasIpAddrMgmtEtwContext,
                xmmword_1800C9740,
                &v55);
            }
            v45 = v34 + v27 - v26 + 1;
            v53 = GUID_NULL;
            LOBYTE(v32) = v7 == 0;
            RasStatComputeAcquiredAddressesCountForPool(&v53, v26, v27, v32);
            v35 = v46;
            v46 = v33;
            *v35 = (__int64)v33;
            v21 = (int)v42;
            goto LABEL_53;
          }
          v23 = *((_QWORD *)&xmmword_1800C9740 + 1);
          if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
          {
            v24 = L"Out of memory";
LABEL_33:
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              v23,
              v24);
          }
LABEL_34:
          v21 = 1;
          LODWORD(v42) = 1;
          goto LABEL_53;
        }
        if ( (_QWORD)xmmword_1800C9740 )
        {
          v36 = "To";
LABEL_52:
          LODWORD(phkResulta) = v25;
          LOWORD(v55) = 0;
          FormatRRASErrorString(&v55, L"Couldn't read value %hs in key %hs: %d", v36, pszDest, phkResulta);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v55);
        }
      }
LABEL_53:
      if ( v44 )
        RegCloseKey(v44);
      ++v7;
      if ( v21 )
        goto LABEL_56;
    }
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v55) = 0;
      FormatRRASErrorString(&v55, L"Couldn't open key %hs in key :%ld", pszDest, v22);
      v23 = xmmword_1800C9740;
      v24 = (const wchar_t *)&v55;
      goto LABEL_33;
    }
    goto LABEL_34;
  }
  RoutingDomainConfigData = GetRoutingDomainConfigData(Buf1, 1, 16, &v47);
  if ( RoutingDomainConfigData == 1168 )
  {
    v9 = *((_QWORD *)&xmmword_1800C9740 + 1);
    if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    {
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        *((_QWORD *)&xmmword_1800C9740 + 1),
        L"No Pool information found in ConfigStore... Using APIPA address");
      v9 = *((_QWORD *)&xmmword_1800C9740 + 1);
    }
    *((_QWORD *)&v47 + 1) = v49;
    *(_QWORD *)&v47 = 0x100000000LL;
    goto LABEL_16;
  }
  if ( !RoutingDomainConfigData )
  {
    v9 = *((_QWORD *)&xmmword_1800C9740 + 1);
    if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    {
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        *((_QWORD *)&xmmword_1800C9740 + 1),
        L"Acquired IP pool details from the Global configuration object.. Creating IP Pool from the same");
      v9 = *((_QWORD *)&xmmword_1800C9740 + 1);
    }
    v43 = 1;
LABEL_16:
    if ( v9 )
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        v9,
        L"Pool information available");
    if ( DWORD1(v47) )
    {
      while ( 1 )
      {
        v10 = 0;
        v11 = *(_DWORD *)(*((_QWORD *)&v47 + 1) + 8LL * v7 + 4);
        v12 = *(_DWORD *)(*((_QWORD *)&v47 + 1) + 8LL * v7);
        v13 = 0;
        for ( j = 0; j < 0x20; ++j )
        {
          v13 = (v13 >> 1) | 0x80000000;
          if ( (~(v12 ^ *(_DWORD *)(*((_QWORD *)&v47 + 1) + 8LL * v7 + 4)) & v13) != v13 )
            break;
          v10 = v13;
        }
        v15 = (__int64 *)LocalAlloc(0x40u, 0x18u);
        v17 = v15;
        if ( !v15 )
          break;
        *((_DWORD *)v15 + 2) = v12;
        *((_DWORD *)v15 + 3) = v11;
        *((_DWORD *)v15 + 5) = v12;
        *((_DWORD *)v15 + 4) = v10;
        v18 = v45 & -(__int64)(v7 != 0);
        v19 = (_QWORD)xmmword_1800C9740 == 0;
        *v15 = 0;
        if ( !v19 )
        {
          LODWORD(phkResult) = v10;
          LOWORD(v55) = 0;
          FormatRRASErrorString(&v55, L"0x%x...0x%x/0x%x", v12, v11, phkResult);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v55);
        }
        v45 = v18 + v11 - v12 + 1;
        LOBYTE(v16) = v7 == 0;
        v53 = *v42;
        RasStatComputeAcquiredAddressesCountForPool(&v53, v12, v11, v16);
        v20 = v46;
        ++v7;
        v46 = v17;
        *v20 = (__int64)v17;
        if ( v7 >= DWORD1(v47) )
          goto LABEL_56;
      }
      if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          *((_QWORD *)&xmmword_1800C9740 + 1),
          L"Out of memory");
    }
  }
LABEL_56:
  *v52 = v50;
  result = v45;
  *v51 = v45;
  if ( v43 )
  {
    result = (int)qword_1800C8690;
    if ( qword_1800C8690 )
      result = qword_1800C8690(1, &v47);
  }
LABEL_59:
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x18005bd78  mov     [rsp-8+arg_18], rbx
0x18005bd7d  push    rbp
0x18005bd7e  push    rsi
0x18005bd7f  push    rdi
0x18005bd80  push    r12
0x18005bd82  push    r13
0x18005bd84  push    r14
0x18005bd86  push    r15
0x18005bd88  lea     rbp, [rsp-7D0h]
0x18005bd90  sub     rsp, 8D0h
0x18005bd97  mov     rax, cs:__security_cookie
0x18005bd9e  xor     rax, rsp
0x18005bda1  mov     [rbp+800h+var_40], rax
0x18005bda8  xor     r14d, r14d
0x18005bdab  mov     [rbp+800h+var_870], r8
0x18005bdaf  mov     r12, rdx
0x18005bdb2  mov     [rbp+800h+var_868], rdx
0x18005bdb6  mov     rdi, rcx
0x18005bdb9  mov     [rsp+900h+var_8C0], rcx
0x18005bdbe  xorps   xmm0, xmm0
0x18005bdc1  mov     [rsp+900h+hKey], r14
0x18005bdc6  xor     edx, edx; Val
0x18005bdc8  mov     [rsp+900h+var_8B0], r14
0x18005bdcd  mov     r8d, 7FCh; Size
0x18005bdd3  mov     [rsp+900h+Type], r14d
0x18005bdd8  lea     rcx, [rbp+800h+var_83C]; void *
0x18005bddc  mov     dword ptr [rsp+900h+Data], r14d
0x18005bde1  mov     [rsp+900h+cbData], r14d
0x18005bde6  mov     [rbp+800h+var_878], r14
0x18005bdea  movups  [rsp+900h+var_898], xmm0
0x18005bdef  mov     [rbp+800h+var_840], r14d
0x18005bdf3  mov     [rbp+800h+var_880], 0A9FE0101h
0x18005bdfa  mov     [rbp+800h+var_87C], 0A9FE0500h
0x18005be01  call    memset_0
0x18005be06  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005be0d  test    rdx, rdx
0x18005be10  jz      short loc_18005BE2C
0x18005be12  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005be19  lea     r8, aRasstatcreatep_0; "RasStatCreatePoolList"
0x18005be20  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005be27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be2c  mov     ebx, cs:dword_1800C8650
0x18005be32  lea     rax, [rsp+900h+hKey]
0x18005be37  mov     r9d, 20019h; samDesired
0x18005be3d  mov     [rsp+900h+phkResult], rax; phkResult
0x18005be42  xor     r8d, r8d; ulOptions
0x18005be45  lea     rdx, aSystemCurrentc_23; "System\\CurrentControlSet\\Services\\Re"...
0x18005be4c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005be53  call    cs:__imp_RegOpenKeyExA
0x18005be59  test    eax, eax
0x18005be5b  jz      short loc_18005BE72
0x18005be5d  test    ebx, ebx
0x18005be5f  jnz     short loc_18005BE72
0x18005be61  mov     rdx, [rbp+800h+var_870]
0x18005be65  mov     rcx, r12
0x18005be68  call    rasStatCreatePoolListFromOldValues
0x18005be6d  jmp     loc_18005C3AB
0x18005be72  mov     [rsp+900h+var_8B8], r14d
0x18005be77  lea     r15, [rbp+800h+var_878]
0x18005be7b  mov     [rsp+900h+var_8A0], r15
0x18005be80  mov     r12d, r14d
0x18005be83  mov     [rsp+900h+var_8A8], r14
0x18005be88  test    ebx, ebx
0x18005be8a  jz      loc_18005C0B5
0x18005be90  mov     ebx, 10h
0x18005be95  lea     rdx, GUID_NULL; Buf2
0x18005be9c  mov     r8d, ebx; Size
0x18005be9f  mov     rcx, rdi; Buf1
0x18005bea2  call    memcmp_0
0x18005bea7  test    eax, eax
0x18005bea9  jz      loc_18005C0B5
0x18005beaf  mov     r8d, ebx
0x18005beb2  lea     r9, [rsp+900h+var_898]
0x18005beb7  mov     ebx, 1
0x18005bebc  mov     rcx, rdi
0x18005bebf  mov     edx, ebx
0x18005bec1  call    GetRoutingDomainConfigData
0x18005bec6  cmp     eax, 490h
0x18005becb  jnz     short loc_18005BF0E
0x18005becd  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005bed4  test    rdx, rdx
0x18005bed7  jz      short loc_18005BEFA
0x18005bed9  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005bee0  lea     r8, aNoPoolInformat; "No Pool information found in ConfigStor"...
0x18005bee7  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005beee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bef3  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005befa  lea     rax, [rbp+800h+var_880]
0x18005befe  mov     dword ptr [rsp+900h+var_898+4], ebx
0x18005bf02  mov     qword ptr [rsp+900h+var_898+8], rax
0x18005bf07  mov     dword ptr [rsp+900h+var_898], r14d
0x18005bf0c  jmp     short loc_18005BF47
0x18005bf0e  test    eax, eax
0x18005bf10  jnz     loc_18005C375
0x18005bf16  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005bf1d  test    rdx, rdx
0x18005bf20  jz      short loc_18005BF43
0x18005bf22  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005bf29  lea     r8, aAcquiredIpPool; "Acquired IP pool details from the Globa"...
0x18005bf30  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005bf37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf3c  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005bf43  mov     [rsp+900h+var_8B8], ebx
0x18005bf47  test    rdx, rdx
0x18005bf4a  jz      short loc_18005BF66
0x18005bf4c  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005bf53  lea     r8, aPoolInformatio; "Pool information available"
0x18005bf5a  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005bf61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf66  cmp     dword ptr [rsp+900h+var_898+4], r14d
0x18005bf6b  jbe     loc_18005C375
0x18005bf71  mov     rax, qword ptr [rsp+900h+var_898+8]
0x18005bf76  xor     r13d, r13d
0x18005bf79  mov     ecx, r12d
0x18005bf7c  mov     r14d, [rax+rcx*8+4]
0x18005bf81  mov     edx, r14d
0x18005bf84  mov     esi, [rax+rcx*8]
0x18005bf87  xor     edx, esi
0x18005bf89  xor     ecx, ecx
0x18005bf8b  not     edx
0x18005bf8d  xor     r8d, r8d
0x18005bf90  shr     ecx, 1
0x18005bf92  bts     ecx, 1Fh
0x18005bf96  mov     eax, ecx
0x18005bf98  and     eax, edx
0x18005bf9a  cmp     eax, ecx
0x18005bf9c  jnz     short loc_18005BFAA
0x18005bf9e  add     r8d, ebx
0x18005bfa1  mov     r13d, ecx
0x18005bfa4  cmp     r8d, 20h ; ' '
0x18005bfa8  jb      short loc_18005BF90
0x18005bfaa  mov     edx, 18h; uBytes
0x18005bfaf  lea     ecx, [rdx+28h]; uFlags
0x18005bfb2  call    cs:__imp_LocalAlloc
0x18005bfb8  mov     rdi, rax
0x18005bfbb  test    rax, rax
0x18005bfbe  jz      loc_18005C083
0x18005bfc4  mov     ecx, r12d
0x18005bfc7  mov     [rax+8], esi
0x18005bfca  neg     ecx
0x18005bfcc  mov     [rax+0Ch], r14d
0x18005bfd0  mov     [rax+14h], esi
0x18005bfd3  sbb     r15, r15
0x18005bfd6  mov     [rax+10h], r13d
0x18005bfda  and     r15, [rsp+900h+var_8A8]
0x18005bfdf  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005bfe7  mov     qword ptr [rax], 0
0x18005bfee  jz      short loc_18005C02F
0x18005bff0  xor     eax, eax
0x18005bff2  mov     dword ptr [rsp+900h+phkResult], r13d
0x18005bff7  mov     r9d, r14d
0x18005bffa  mov     word ptr [rbp+800h+var_840], ax
0x18005bffe  mov     r8d, esi
0x18005c001  lea     rdx, a0xX0xX0xX; "0x%x...0x%x/0x%x"
0x18005c008  lea     rcx, [rbp+800h+var_840]
0x18005c00c  call    FormatRRASErrorString
0x18005c011  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005c018  lea     r8, [rbp+800h+var_840]
0x18005c01c  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005c023  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005c02a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c02f  mov     eax, r14d
0x18005c032  lea     rcx, [rbp+800h+var_860]
0x18005c036  sub     eax, esi
0x18005c038  mov     r8d, r14d
0x18005c03b  add     eax, ebx
0x18005c03d  mov     edx, esi
0x18005c03f  add     rax, r15
0x18005c042  mov     [rsp+900h+var_8A8], rax
0x18005c047  test    r12d, r12d
0x18005c04a  mov     rax, [rsp+900h+var_8C0]
0x18005c04f  setz    r9b
0x18005c053  movaps  xmm0, xmmword ptr [rax]
0x18005c056  movdqa  [rbp+800h+var_860], xmm0
0x18005c05b  call    RasStatComputeAcquiredAddressesCountForPool
0x18005c060  mov     rax, [rsp+900h+var_8A0]
0x18005c065  add     r12d, ebx
0x18005c068  mov     [rsp+900h+var_8A0], rdi
0x18005c06d  mov     [rax], rdi
0x18005c070  cmp     r12d, dword ptr [rsp+900h+var_898+4]
0x18005c075  jb      loc_18005BF71
0x18005c07b  xor     r14d, r14d
0x18005c07e  jmp     loc_18005C375
0x18005c083  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005c08a  xor     r14d, r14d
0x18005c08d  test    rdx, rdx
0x18005c090  jz      loc_18005C375
0x18005c096  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005c09d  lea     r8, aOutOfMemory; "Out of memory"
0x18005c0a4  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005c0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c0b0  jmp     loc_18005C375
0x18005c0b5  mov     edi, r14d
0x18005c0b8  mov     dword ptr [rsp+900h+var_8C0], r14d
0x18005c0bd  mov     ebx, 1
0x18005c0c2  mov     r9d, r12d
0x18005c0c5  mov     [rsp+900h+var_8B0], r14
0x18005c0ca  lea     r8, aD; "%d"
0x18005c0d1  mov     edx, 0Ah; cbDest
0x18005c0d6  lea     rcx, [rbp+800h+pszDest]; pszDest
0x18005c0da  call    StringCbPrintfA
0x18005c0df  mov     rcx, [rsp+900h+hKey]; hKey
0x18005c0e4  lea     rax, [rsp+900h+var_8B0]
0x18005c0e9  mov     r9d, 20019h; samDesired
0x18005c0ef  mov     [rsp+900h+phkResult], rax; phkResult
0x18005c0f4  xor     r8d, r8d; ulOptions
0x18005c0f7  lea     rdx, [rbp+800h+pszDest]; lpSubKey
0x18005c0fb  call    cs:__imp_RegOpenKeyExA
0x18005c101  test    eax, eax
0x18005c103  jz      short loc_18005C153
0x18005c105  cmp     qword ptr cs:xmmword_1800C9740, r14
0x18005c10c  jz      short loc_18005C148
0x18005c10e  mov     r9d, eax
0x18005c111  mov     word ptr [rbp+800h+var_840], r14w
0x18005c116  lea     r8, [rbp+800h+pszDest]
0x18005c11a  lea     rdx, aCouldnTOpenKey_1; "Couldn't open key %hs in key :%ld"
0x18005c121  lea     rcx, [rbp+800h+var_840]
0x18005c125  call    FormatRRASErrorString
0x18005c12a  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005c131  lea     r8, [rbp+800h+var_840]
0x18005c135  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005c13c  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005c143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c148  mov     edi, ebx
0x18005c14a  mov     dword ptr [rsp+900h+var_8C0], ebx
0x18005c14e  jmp     loc_18005C35A
0x18005c153  mov     rcx, [rsp+900h+var_8B0]; hKey
0x18005c158  lea     rax, [rsp+900h+cbData]
0x18005c15d  mov     [rsp+900h+lpcbData], rax; lpcbData
0x18005c162  lea     r9, [rsp+900h+Type]; lpType
0x18005c167  lea     rax, [rsp+900h+Data]
0x18005c16c  mov     [rsp+900h+cbData], 4
0x18005c174  xor     r8d, r8d; lpReserved
0x18005c177  mov     [rsp+900h+phkResult], rax; lpData
0x18005c17c  lea     rdx, aFrom; "From"
0x18005c183  call    cs:__imp_RegQueryValueExA
0x18005c189  test    eax, eax
0x18005c18b  jnz     loc_18005C30F
0x18005c191  cmp     [rsp+900h+Type], 4
0x18005c196  jnz     loc_18005C30F
0x18005c19c  mov     rcx, [rsp+900h+var_8B0]; hKey
0x18005c1a1  lea     rax, [rsp+900h+cbData]
0x18005c1a6  mov     esi, dword ptr [rsp+900h+Data]
0x18005c1aa  lea     r9, [rsp+900h+Type]; lpType
0x18005c1af  mov     [rsp+900h+lpcbData], rax; lpcbData
0x18005c1b4  lea     rdx, aTo; "To"
0x18005c1bb  lea     rax, [rsp+900h+Data]
0x18005c1c0  mov     [rsp+900h+cbData], 4
0x18005c1c8  xor     r8d, r8d; lpReserved
0x18005c1cb  mov     [rsp+900h+phkResult], rax; lpData
0x18005c1d0  call    cs:__imp_RegQueryValueExA
0x18005c1d6  test    eax, eax
0x18005c1d8  jnz     loc_18005C2FD
0x18005c1de  cmp     [rsp+900h+Type], 4
0x18005c1e3  jnz     loc_18005C2FD
0x18005c1e9  mov     r15d, dword ptr [rsp+900h+Data]
0x18005c1ee  mov     r13d, r14d
0x18005c1f1  mov     edx, r15d
0x18005c1f4  mov     ecx, r14d
0x18005c1f7  xor     edx, esi
0x18005c1f9  mov     r8d, r14d
0x18005c1fc  not     edx
0x18005c1fe  shr     ecx, 1
0x18005c200  bts     ecx, 1Fh
0x18005c204  mov     eax, ecx
0x18005c206  and     eax, edx
0x18005c208  cmp     eax, ecx
0x18005c20a  jnz     short loc_18005C218
0x18005c20c  add     r8d, ebx
0x18005c20f  mov     r13d, ecx
0x18005c212  cmp     r8d, 20h ; ' '
0x18005c216  jb      short loc_18005C1FE
0x18005c218  mov     edx, 18h; uBytes
0x18005c21d  lea     ecx, [rdx+28h]; uFlags
0x18005c220  call    cs:__imp_LocalAlloc
0x18005c226  mov     rdi, rax
0x18005c229  test    rax, rax
0x18005c22c  jnz     short loc_18005C24A
0x18005c22e  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18005c235  test    rdx, rdx
0x18005c238  jz      loc_18005C148
0x18005c23e  lea     r8, aOutOfMemory; "Out of memory"
0x18005c245  jmp     loc_18005C135
0x18005c24a  mov     eax, r12d
0x18005c24d  mov     [rdi+8], esi
0x18005c250  neg     eax
0x18005c252  mov     [rdi+0Ch], r15d
0x18005c256  mov     [rdi+14h], esi
0x18005c259  sbb     r14, r14
0x18005c25c  mov     [rdi+10h], r13d
0x18005c260  and     r14, [rsp+900h+var_8A8]
0x18005c265  cmp     qword ptr cs:xmmword_1800C9740, 0
0x18005c26d  mov     qword ptr [rdi], 0
0x18005c274  jz      short loc_18005C2B5
0x18005c276  xor     eax, eax
0x18005c278  mov     dword ptr [rsp+900h+phkResult], r13d
0x18005c27d  mov     r9d, r15d
0x18005c280  mov     word ptr [rbp+800h+var_840], ax
0x18005c284  mov     r8d, esi
0x18005c287  lea     rdx, a0xX0xX0xX; "0x%x...0x%x/0x%x"
  ... truncated ...
```
