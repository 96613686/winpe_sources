# RasStatCreatePoolList

- ea: `0x18005df7c`
- end: `0x18005e61a`
- name: `RasStatCreatePoolList`
- size: `1694`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180051a00`
- `0x180056f10`

## callees

- `0x180019d50`
- `0x180027ec0`
- `0x18005c090`
- `0x18005de48`
- `0x18005df7c`
- `0x18005ec00`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18005e1ca`
- `KERNEL32!LocalAlloc` at `0x18005e441`
- `KERNEL32!LocalAlloc` at `0x18005e1ca`
- `KERNEL32!LocalAlloc` at `0x18005e441`
- `ADVAPI32!RegCloseKey` at `0x18005e580`
- `ADVAPI32!RegCloseKey` at `0x18005e5dc`
- `ADVAPI32!RegCloseKey` at `0x18005e580`
- `ADVAPI32!RegCloseKey` at `0x18005e5dc`
- `ADVAPI32!RegOpenKeyExA` at `0x18005e064`
- `ADVAPI32!RegOpenKeyExA` at `0x18005e30a`
- `ADVAPI32!RegOpenKeyExA` at `0x18005e064`
- `ADVAPI32!RegOpenKeyExA` at `0x18005e30a`
- `ADVAPI32!RegQueryValueExA` at `0x18005e398`
- `ADVAPI32!RegQueryValueExA` at `0x18005e3eb`
- `ADVAPI32!RegQueryValueExA` at `0x18005e398`
- `ADVAPI32!RegQueryValueExA` at `0x18005e3eb`

## string_xrefs

- `0x18005e543`: `Couldn't read value %hs in key %hs: %d`
- `0x18005e02a`: `RasStatCreatePoolList`
- `0x18005e056`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip\StaticAddressPool`
- `0x18005e0f3`: `No Pool information found in ConfigStore... Using APIPA address`
- `0x18005e13d`: `Acquired IP pool details from the Global configuration object.. Creating IP Pool from the same`
- `0x18005e32f`: `Couldn't open key %hs in key :%ld`

## pseudocode

```c
__int64 __fastcall RasStatCreatePoolList(_QWORD *a1, _QWORD *a2, __int64 *a3)
{
  __int64 v6; // r12
  int v7; // ebx
  unsigned int v8; // r13d
  int v9; // edi
  int RoutingDomainConfigData; // eax
  __int64 v11; // rdx
  unsigned int v12; // r14d
  unsigned int v13; // esi
  unsigned int v14; // r8d
  unsigned int v15; // ecx
  __int64 *v16; // rax
  __int64 v17; // r9
  __int64 *v18; // rdi
  __int64 v19; // r12
  bool v20; // zf
  __int64 *v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rdx
  const wchar_t *v24; // r8
  LSTATUS v25; // eax
  unsigned int v26; // esi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  unsigned int v29; // r15d
  unsigned int v30; // ecx
  __int64 *v31; // rax
  __int64 v32; // r9
  __int64 *v33; // rdi
  __int64 v34; // r12
  __int64 *v35; // rax
  const CHAR *v36; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+30h] [rbp-D0h]
  unsigned int v41; // [rsp+30h] [rbp-D0h]
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  int v45; // [rsp+40h] [rbp-C0h]
  HKEY v46; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v47; // [rsp+50h] [rbp-B0h]
  __int64 v48; // [rsp+58h] [rbp-A8h]
  __int128 v49; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v51[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v52; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v53; // [rsp+88h] [rbp-78h]
  __int64 *v54; // [rsp+90h] [rbp-70h]
  GUID v55; // [rsp+A0h] [rbp-60h] BYREF
  char pszDest[16]; // [rsp+B0h] [rbp-50h] BYREF
  int v57; // [rsp+C0h] [rbp-40h] BYREF
  char v58[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v54 = a3;
  v53 = a2;
  hKey = 0;
  v46 = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  v52 = 0;
  v49 = 0;
  v6 = 0;
  v48 = 0;
  v45 = 0;
  v57 = 0;
  v51[0] = -1442971391;
  v51[1] = -1442970368;
  memset_0(v58, 0, sizeof(v58));
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"RasStatCreatePoolList");
  v7 = dword_1800CF650;
  if ( RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip\\StaticAddressPool",
         0,
         0x20019u,
         &hKey)
    && !v7 )
  {
    rasStatCreatePoolListFromOldValues(a2, a3);
    goto LABEL_60;
  }
  v40 = 0;
  v47 = &v52;
  v8 = 0;
  v9 = 0;
  if ( !v7 || *a1 == *(_QWORD *)&GUID_NULL.Data1 && a1[1] == *(_QWORD *)GUID_NULL.Data4 )
  {
    while ( 1 )
    {
      v46 = 0;
      StringCbPrintfA(pszDest, 0xAu, "%d", v8);
      v22 = RegOpenKeyExA(hKey, pszDest, 0, 0x20019u, &v46);
      if ( v22 )
        break;
      cbData = 4;
      v25 = RegQueryValueExA(v46, "From", 0, &Type, Data, &cbData);
      if ( v25 || Type != 4 )
      {
        if ( (_QWORD)xmmword_1800D0740 )
        {
          v36 = "From";
          goto LABEL_52;
        }
      }
      else
      {
        v26 = *(_DWORD *)Data;
        cbData = 4;
        v25 = RegQueryValueExA(v46, "To", 0, &Type, Data, &cbData);
        if ( !v25 && Type == 4 )
        {
          v27 = *(_DWORD *)Data;
          v28 = 0;
          v29 = 0;
          v30 = 0;
          do
          {
            v30 = (v30 >> 1) | 0x80000000;
            if ( (~(*(_DWORD *)Data ^ v26) & v30) != v30 )
              break;
            ++v28;
            v29 = v30;
          }
          while ( v28 < 0x20 );
          v31 = (__int64 *)LocalAlloc(0x40u, 0x18u);
          v33 = v31;
          if ( v31 )
          {
            *((_DWORD *)v31 + 2) = v26;
            *((_DWORD *)v31 + 3) = v27;
            *((_DWORD *)v31 + 5) = v26;
            *((_DWORD *)v31 + 4) = v29;
            v34 = -(__int64)(v8 != 0) & v6;
            *v31 = 0;
            if ( (_QWORD)xmmword_1800D0740 )
            {
              LOWORD(v57) = 0;
              LODWORD(phkResulta) = v29;
              FormatRRASErrorString(&v57, L"0x%x...0x%x/0x%x", v26, v27, phkResulta);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
                gRasIpAddrMgmtEtwContext,
                xmmword_1800D0740,
                &v57);
            }
            v6 = v27 - v26 + 1 + v34;
            v55 = GUID_NULL;
            LOBYTE(v32) = v8 == 0;
            RasStatComputeAcquiredAddressesCountForPool(&v55, v26, v27, v32);
            v35 = v47;
            v47 = v33;
            *v35 = (__int64)v33;
            v9 = v40;
            goto LABEL_53;
          }
          v23 = *((_QWORD *)&xmmword_1800D0740 + 1);
          if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
          {
            v24 = L"Out of memory";
LABEL_33:
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              v23,
              v24);
          }
LABEL_34:
          v9 = 1;
          v40 = 1;
          goto LABEL_53;
        }
        if ( (_QWORD)xmmword_1800D0740 )
        {
          v36 = "To";
LABEL_52:
          LODWORD(phkResulta) = v25;
          LOWORD(v57) = 0;
          FormatRRASErrorString(&v57, L"Couldn't read value %hs in key %hs: %d", v36, pszDest, phkResulta);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v57);
        }
      }
LABEL_53:
      if ( v46 )
        RegCloseKey(v46);
      ++v8;
      if ( v9 )
      {
        v48 = v6;
        goto LABEL_57;
      }
    }
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v57) = 0;
      FormatRRASErrorString(&v57, L"Couldn't open key %hs in key :%ld", pszDest, v22);
      v23 = xmmword_1800D0740;
      v24 = (const wchar_t *)&v57;
      goto LABEL_33;
    }
    goto LABEL_34;
  }
  RoutingDomainConfigData = GetRoutingDomainConfigData(a1, 1, 16, &v49);
  if ( RoutingDomainConfigData == 1168 )
  {
    v11 = *((_QWORD *)&xmmword_1800D0740 + 1);
    if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    {
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        *((_QWORD *)&xmmword_1800D0740 + 1),
        L"No Pool information found in ConfigStore... Using APIPA address");
      v11 = *((_QWORD *)&xmmword_1800D0740 + 1);
    }
    *((_QWORD *)&v49 + 1) = v51;
    *(_QWORD *)&v49 = 0x100000000LL;
  }
  else
  {
    if ( RoutingDomainConfigData )
      goto LABEL_57;
    v11 = *((_QWORD *)&xmmword_1800D0740 + 1);
    if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    {
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        *((_QWORD *)&xmmword_1800D0740 + 1),
        L"Acquired IP pool details from the Global configuration object.. Creating IP Pool from the same");
      v11 = *((_QWORD *)&xmmword_1800D0740 + 1);
    }
    v45 = 1;
  }
  if ( v11 )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      v11,
      L"Pool information available");
  if ( DWORD1(v49) )
  {
    while ( 1 )
    {
      v12 = *(_DWORD *)(*((_QWORD *)&v49 + 1) + 8LL * v8 + 4);
      v13 = *(_DWORD *)(*((_QWORD *)&v49 + 1) + 8LL * v8);
      v14 = 0;
      v41 = 0;
      v15 = 0;
      do
      {
        v15 = (v15 >> 1) | 0x80000000;
        if ( (~(v13 ^ *(_DWORD *)(*((_QWORD *)&v49 + 1) + 8LL * v8 + 4)) & v15) != v15 )
          break;
        ++v14;
        v41 = v15;
      }
      while ( v14 < 0x20 );
      v16 = (__int64 *)LocalAlloc(0x40u, 0x18u);
      v18 = v16;
      if ( !v16 )
        break;
      *((_DWORD *)v16 + 2) = v13;
      *((_DWORD *)v16 + 3) = v12;
      *((_DWORD *)v16 + 5) = v13;
      v19 = v48 & -(__int64)(v8 != 0);
      v20 = (_QWORD)xmmword_1800D0740 == 0;
      *((_DWORD *)v16 + 4) = v41;
      *v16 = 0;
      if ( !v20 )
      {
        LOWORD(v57) = 0;
        LODWORD(phkResult) = v41;
        FormatRRASErrorString(&v57, L"0x%x...0x%x/0x%x", v13, v12, phkResult);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v57);
      }
      v55 = *(GUID *)a1;
      v48 = v19 + v12 - v13 + 1;
      LOBYTE(v17) = v8 == 0;
      RasStatComputeAcquiredAddressesCountForPool(&v55, v13, v12, v17);
      v21 = v47;
      ++v8;
      v47 = v18;
      *v21 = (__int64)v18;
      if ( v8 >= DWORD1(v49) )
        goto LABEL_57;
    }
    if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        *((_QWORD *)&xmmword_1800D0740 + 1),
        L"Out of memory");
  }
LABEL_57:
  *v53 = v52;
  *v54 = v48;
  if ( v45 && qword_1800CF690 )
    qword_1800CF690(1, &v49);
LABEL_60:
  if ( hKey )
    RegCloseKey(hKey);
  return RasStatFreeAddrPool(0);
}

```

## disassembly

```asm
0x18005df7c  mov     [rsp-8+arg_18], rbx
0x18005df81  push    rbp
0x18005df82  push    rsi
0x18005df83  push    rdi
0x18005df84  push    r12
0x18005df86  push    r13
0x18005df88  push    r14
0x18005df8a  push    r15
0x18005df8c  lea     rbp, [rsp-7D0h]
0x18005df94  sub     rsp, 8D0h
0x18005df9b  mov     rax, cs:__security_cookie
0x18005dfa2  xor     rax, rsp
0x18005dfa5  mov     [rbp+800h+var_40], rax
0x18005dfac  xor     r14d, r14d
0x18005dfaf  mov     [rbp+800h+var_870], r8
0x18005dfb3  mov     r13, r8
0x18005dfb6  mov     [rbp+800h+var_878], rdx
0x18005dfba  mov     rdi, rdx
0x18005dfbd  mov     [rsp+900h+hKey], r14
0x18005dfc2  mov     r15, rcx
0x18005dfc5  mov     [rsp+900h+var_8B8], r14
0x18005dfca  xorps   xmm0, xmm0
0x18005dfcd  mov     [rsp+900h+Type], r14d
0x18005dfd2  xor     edx, edx; Val
0x18005dfd4  mov     dword ptr [rsp+900h+Data], r14d
0x18005dfd9  mov     r8d, 7FCh; Size
0x18005dfdf  mov     [rsp+900h+cbData], r14d
0x18005dfe4  lea     rcx, [rbp+800h+var_83C]; void *
0x18005dfe8  mov     [rbp+800h+var_880], r14
0x18005dfec  movups  [rsp+900h+var_8A0], xmm0
0x18005dff1  mov     r12d, r14d
0x18005dff4  mov     [rsp+900h+var_8A8], r14
0x18005dff9  mov     [rsp+900h+var_8C0], r14d
0x18005dffe  mov     [rbp+800h+var_840], r14d
0x18005e002  mov     [rsp+900h+var_888], 0A9FE0101h
0x18005e00a  mov     [rsp+900h+var_884], 0A9FE0500h
0x18005e012  call    memset_0
0x18005e017  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005e01e  test    rdx, rdx
0x18005e021  jz      short loc_18005E03D
0x18005e023  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005e02a  lea     r8, aRasstatcreatep_0; "RasStatCreatePoolList"
0x18005e031  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e03d  mov     ebx, cs:dword_1800CF650
0x18005e043  lea     rax, [rsp+900h+hKey]
0x18005e048  mov     r9d, 20019h; samDesired
0x18005e04e  mov     [rsp+900h+phkResult], rax; phkResult
0x18005e053  xor     r8d, r8d; ulOptions
0x18005e056  lea     rdx, aSystemCurrentc_23; "System\\CurrentControlSet\\Services\\Re"...
0x18005e05d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005e064  call    cs:__imp_RegOpenKeyExA
0x18005e06b  nop     dword ptr [rax+rax+00h]
0x18005e070  test    eax, eax
0x18005e072  jz      short loc_18005E088
0x18005e074  test    ebx, ebx
0x18005e076  jnz     short loc_18005E088
0x18005e078  mov     rdx, r13
0x18005e07b  mov     rcx, rdi
0x18005e07e  call    rasStatCreatePoolListFromOldValues
0x18005e083  jmp     loc_18005E5D2
0x18005e088  mov     [rsp+900h+var_8D0], r14d
0x18005e08d  lea     rsi, [rbp+800h+var_880]
0x18005e091  mov     [rsp+900h+var_8B0], rsi
0x18005e096  mov     r13d, r14d
0x18005e099  mov     edi, r14d
0x18005e09c  test    ebx, ebx
0x18005e09e  jz      loc_18005E2CC
0x18005e0a4  mov     rax, [r15]
0x18005e0a7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18005e0ae  jnz     short loc_18005E0C1
0x18005e0b0  mov     rax, [r15+8]
0x18005e0b4  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18005e0bb  jz      loc_18005E2CC
0x18005e0c1  mov     ebx, 1
0x18005e0c6  lea     r9, [rsp+900h+var_8A0]
0x18005e0cb  mov     edx, ebx
0x18005e0cd  mov     rcx, r15
0x18005e0d0  lea     r8d, [rbx+0Fh]
0x18005e0d4  call    GetRoutingDomainConfigData
0x18005e0d9  cmp     eax, 490h
0x18005e0de  jnz     short loc_18005E122
0x18005e0e0  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005e0e7  test    rdx, rdx
0x18005e0ea  jz      short loc_18005E10D
0x18005e0ec  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005e0f3  lea     r8, aNoPoolInformat; "No Pool information found in ConfigStor"...
0x18005e0fa  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e106  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005e10d  lea     rax, [rsp+900h+var_888]
0x18005e112  mov     dword ptr [rsp+900h+var_8A0+4], ebx
0x18005e116  mov     qword ptr [rsp+900h+var_8A0+8], rax
0x18005e11b  mov     dword ptr [rsp+900h+var_8A0], r14d
0x18005e120  jmp     short loc_18005E15B
0x18005e122  test    eax, eax
0x18005e124  jnz     loc_18005E59C
0x18005e12a  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005e131  test    rdx, rdx
0x18005e134  jz      short loc_18005E157
0x18005e136  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005e13d  lea     r8, aAcquiredIpPool; "Acquired IP pool details from the Globa"...
0x18005e144  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e150  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005e157  mov     [rsp+900h+var_8C0], ebx
0x18005e15b  test    rdx, rdx
0x18005e15e  jz      short loc_18005E17A
0x18005e160  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005e167  lea     r8, aPoolInformatio; "Pool information available"
0x18005e16e  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e17a  cmp     dword ptr [rsp+900h+var_8A0+4], r14d
0x18005e17f  jbe     loc_18005E59C
0x18005e185  mov     rax, qword ptr [rsp+900h+var_8A0+8]
0x18005e18a  mov     ecx, r13d
0x18005e18d  mov     r14d, [rax+rcx*8+4]
0x18005e192  mov     edx, r14d
0x18005e195  mov     esi, [rax+rcx*8]
0x18005e198  xor     edx, esi
0x18005e19a  xor     r8d, r8d
0x18005e19d  not     edx
0x18005e19f  mov     [rsp+900h+var_8D0], r8d
0x18005e1a4  mov     ecx, r8d
0x18005e1a7  shr     ecx, 1
0x18005e1a9  bts     ecx, 1Fh
0x18005e1ad  mov     eax, ecx
0x18005e1af  and     eax, edx
0x18005e1b1  cmp     eax, ecx
0x18005e1b3  jnz     short loc_18005E1C2
0x18005e1b5  add     r8d, ebx
0x18005e1b8  mov     [rsp+900h+var_8D0], ecx
0x18005e1bc  cmp     r8d, 20h ; ' '
0x18005e1c0  jb      short loc_18005E1A7
0x18005e1c2  mov     edx, 18h; uBytes
0x18005e1c7  lea     ecx, [rdx+28h]; uFlags
0x18005e1ca  call    cs:__imp_LocalAlloc
0x18005e1d1  nop     dword ptr [rax+rax+00h]
0x18005e1d6  xor     edx, edx
0x18005e1d8  mov     rdi, rax
0x18005e1db  test    rax, rax
0x18005e1de  jz      loc_18005E29A
0x18005e1e4  mov     ecx, r13d
0x18005e1e7  mov     [rax+8], esi
0x18005e1ea  neg     ecx
0x18005e1ec  mov     [rax+0Ch], r14d
0x18005e1f0  mov     [rax+14h], esi
0x18005e1f3  mov     eax, [rsp+900h+var_8D0]
0x18005e1f7  sbb     r12, r12
0x18005e1fa  and     r12, [rsp+900h+var_8A8]
0x18005e1ff  cmp     qword ptr cs:xmmword_1800D0740, rdx
0x18005e206  mov     [rdi+10h], eax
0x18005e209  mov     [rdi], rdx
0x18005e20c  jz      short loc_18005E24A
0x18005e20e  mov     word ptr [rbp+800h+var_840], dx
0x18005e212  lea     rcx, [rbp+800h+var_840]
0x18005e216  lea     rdx, a0xX0xX0xX; "0x%x...0x%x/0x%x"
0x18005e21d  mov     dword ptr [rsp+900h+phkResult], eax
0x18005e221  mov     r9d, r14d
0x18005e224  mov     r8d, esi
0x18005e227  call    FormatRRASErrorString
0x18005e22c  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005e233  lea     r8, [rbp+800h+var_840]
0x18005e237  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005e23e  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e24a  movaps  xmm0, xmmword ptr [r15]
0x18005e24e  lea     rcx, [rbp+800h+var_860]
0x18005e252  mov     eax, r14d
0x18005e255  movdqa  [rbp+800h+var_860], xmm0
0x18005e25a  sub     eax, esi
0x18005e25c  mov     r8d, r14d
0x18005e25f  add     eax, ebx
0x18005e261  mov     edx, esi
0x18005e263  add     rax, r12
0x18005e266  test    r13d, r13d
0x18005e269  mov     [rsp+900h+var_8A8], rax
0x18005e26e  setz    r9b
0x18005e272  call    RasStatComputeAcquiredAddressesCountForPool
0x18005e277  mov     rax, [rsp+900h+var_8B0]
0x18005e27c  add     r13d, ebx
0x18005e27f  mov     [rsp+900h+var_8B0], rdi
0x18005e284  mov     [rax], rdi
0x18005e287  cmp     r13d, dword ptr [rsp+900h+var_8A0+4]
0x18005e28c  jb      loc_18005E185
0x18005e292  xor     r14d, r14d
0x18005e295  jmp     loc_18005E59C
0x18005e29a  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005e2a1  xor     r14d, r14d
0x18005e2a4  test    rdx, rdx
0x18005e2a7  jz      loc_18005E59C
0x18005e2ad  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005e2b4  lea     r8, aOutOfMemory; "Out of memory"
0x18005e2bb  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e2c7  jmp     loc_18005E59C
0x18005e2cc  mov     ebx, 1
0x18005e2d1  mov     r9d, r13d
0x18005e2d4  mov     [rsp+900h+var_8B8], r14
0x18005e2d9  lea     r8, aD; "%d"
0x18005e2e0  mov     edx, 0Ah; cbDest
0x18005e2e5  lea     rcx, [rbp+800h+pszDest]; pszDest
0x18005e2e9  call    StringCbPrintfA
0x18005e2ee  mov     rcx, [rsp+900h+hKey]; hKey
0x18005e2f3  lea     rax, [rsp+900h+var_8B8]
0x18005e2f8  mov     r9d, 20019h; samDesired
0x18005e2fe  mov     [rsp+900h+phkResult], rax; phkResult
0x18005e303  xor     r8d, r8d; ulOptions
0x18005e306  lea     rdx, [rbp+800h+pszDest]; lpSubKey
0x18005e30a  call    cs:__imp_RegOpenKeyExA
0x18005e311  nop     dword ptr [rax+rax+00h]
0x18005e316  test    eax, eax
0x18005e318  jz      short loc_18005E368
0x18005e31a  cmp     qword ptr cs:xmmword_1800D0740, r14
0x18005e321  jz      short loc_18005E35D
0x18005e323  mov     r9d, eax
0x18005e326  mov     word ptr [rbp+800h+var_840], r14w
0x18005e32b  lea     r8, [rbp+800h+pszDest]
0x18005e32f  lea     rdx, aCouldnTOpenKey_1; "Couldn't open key %hs in key :%ld"
0x18005e336  lea     rcx, [rbp+800h+var_840]
0x18005e33a  call    FormatRRASErrorString
0x18005e33f  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005e346  lea     r8, [rbp+800h+var_840]
0x18005e34a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005e351  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005e358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e35d  mov     edi, ebx
0x18005e35f  mov     [rsp+900h+var_8D0], ebx
0x18005e363  jmp     loc_18005E576
0x18005e368  mov     rcx, [rsp+900h+var_8B8]; hKey
0x18005e36d  lea     rax, [rsp+900h+cbData]
0x18005e372  mov     [rsp+900h+lpcbData], rax; lpcbData
0x18005e377  lea     r9, [rsp+900h+Type]; lpType
0x18005e37c  lea     rax, [rsp+900h+Data]
0x18005e381  mov     [rsp+900h+cbData], 4
0x18005e389  xor     r8d, r8d; lpReserved
0x18005e38c  mov     [rsp+900h+phkResult], rax; lpData
0x18005e391  lea     rdx, aFrom; "From"
0x18005e398  call    cs:__imp_RegQueryValueExA
0x18005e39f  nop     dword ptr [rax+rax+00h]
0x18005e3a4  test    eax, eax
0x18005e3a6  jnz     loc_18005E52B
0x18005e3ac  cmp     [rsp+900h+Type], 4
0x18005e3b1  jnz     loc_18005E52B
0x18005e3b7  mov     rcx, [rsp+900h+var_8B8]; hKey
0x18005e3bc  lea     rax, [rsp+900h+cbData]
0x18005e3c1  mov     esi, dword ptr [rsp+900h+Data]
0x18005e3c5  lea     r9, [rsp+900h+Type]; lpType
0x18005e3ca  mov     [rsp+900h+lpcbData], rax; lpcbData
0x18005e3cf  lea     rdx, aTo; "To"
0x18005e3d6  lea     rax, [rsp+900h+Data]
0x18005e3db  mov     [rsp+900h+cbData], 4
0x18005e3e3  xor     r8d, r8d; lpReserved
0x18005e3e6  mov     [rsp+900h+phkResult], rax; lpData
0x18005e3eb  call    cs:__imp_RegQueryValueExA
0x18005e3f2  nop     dword ptr [rax+rax+00h]
0x18005e3f7  test    eax, eax
0x18005e3f9  jnz     loc_18005E519
0x18005e3ff  cmp     [rsp+900h+Type], 4
0x18005e404  jnz     loc_18005E519
0x18005e40a  mov     r14d, dword ptr [rsp+900h+Data]
0x18005e40f  mov     edx, esi
0x18005e411  xor     edx, r14d
0x18005e414  xor     r8d, r8d
0x18005e417  not     edx
0x18005e419  mov     r15d, r8d
0x18005e41c  mov     ecx, r8d
0x18005e41f  shr     ecx, 1
0x18005e421  bts     ecx, 1Fh
0x18005e425  mov     eax, ecx
0x18005e427  and     eax, edx
0x18005e429  cmp     eax, ecx
0x18005e42b  jnz     short loc_18005E439
0x18005e42d  add     r8d, ebx
0x18005e430  mov     r15d, ecx
0x18005e433  cmp     r8d, 20h ; ' '
0x18005e437  jb      short loc_18005E41F
0x18005e439  mov     edx, 18h; uBytes
0x18005e43e  lea     ecx, [rdx+28h]; uFlags
0x18005e441  call    cs:__imp_LocalAlloc
0x18005e448  nop     dword ptr [rax+rax+00h]
0x18005e44d  xor     edx, edx
0x18005e44f  mov     rdi, rax
0x18005e452  test    rax, rax
0x18005e455  jnz     short loc_18005E476
0x18005e457  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18005e45e  xor     r14d, r14d
0x18005e461  test    rdx, rdx
0x18005e464  jz      loc_18005E35D
0x18005e46a  lea     r8, aOutOfMemory; "Out of memory"
0x18005e471  jmp     loc_18005E34A
0x18005e476  mov     eax, r13d
0x18005e479  mov     [rdi+8], esi
0x18005e47c  neg     eax
0x18005e47e  mov     [rdi+0Ch], r14d
0x18005e482  mov     [rdi+14h], esi
0x18005e485  sbb     rcx, rcx
0x18005e488  mov     [rdi+10h], r15d
0x18005e48c  and     r12, rcx
0x18005e48f  mov     [rdi], rdx
  ... truncated ...
```
