# HelperV4ChangeNotification

- ea: `0x180051a00`
- end: `0x1800521a7`
- name: `HelperV4ChangeNotification`
- size: `1959`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001b520`
- `0x180056f10`

## callees

- `0x18005033c`
- `0x180051a00`
- `0x180056024`
- `0x180058bd4`
- `0x180058dac`
- `0x18005a844`
- `0x18005ad18`
- `0x18005adcc`
- `0x18005b124`
- `0x18005c090`
- `0x18005db74`
- `0x18005df7c`
- `0x1800755b8`
- `0x1800771b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180051d5d`
- `KERNEL32!LeaveCriticalSection` at `0x180051f79`
- `KERNEL32!LeaveCriticalSection` at `0x1800520fa`
- `KERNEL32!LeaveCriticalSection` at `0x180051d5d`
- `KERNEL32!LeaveCriticalSection` at `0x180051f79`
- `KERNEL32!LeaveCriticalSection` at `0x1800520fa`
- `KERNEL32!EnterCriticalSection` at `0x180051c4c`
- `KERNEL32!EnterCriticalSection` at `0x180051d88`
- `KERNEL32!EnterCriticalSection` at `0x180051fa5`
- `KERNEL32!EnterCriticalSection` at `0x180051c4c`
- `KERNEL32!EnterCriticalSection` at `0x180051d88`
- `KERNEL32!EnterCriticalSection` at `0x180051fa5`
- `ADVAPI32!RegCloseKey` at `0x180051bf8`
- `ADVAPI32!RegCloseKey` at `0x180051bf8`
- `ADVAPI32!RegOpenKeyExA` at `0x180051b98`
- `ADVAPI32!RegOpenKeyExA` at `0x180051b98`
- `ADVAPI32!RegQueryValueExA` at `0x180051bd6`
- `ADVAPI32!RegQueryValueExA` at `0x180051bd6`

## string_xrefs

- `0x180051b69`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`

## pseudocode

```c
void __fastcall HelperV4ChangeNotification(GUID *a1)
{
  int v1; // esi
  int v3; // r13d
  struct _ADDR_POOL *v4; // rdi
  __int64 v5; // r15
  int v6; // r12d
  __m128i v7; // xmm6
  __int64 v8; // rdx
  int v9; // r14d
  int v10; // eax
  int v11; // r10d
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  const wchar_t *v15; // rdx
  int RoutingDomainAddressPool; // r10d
  BOOL v17; // r14d
  BOOL v18; // esi
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  BYTE Data[8]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v24[3]; // [rsp+40h] [rbp-C8h] BYREF
  DWORD cbData[2]; // [rsp+58h] [rbp-B0h] BYREF
  struct _ADDR_POOL *v26; // [rsp+60h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+70h] [rbp-98h] BYREF
  __int64 v29; // [rsp+78h] [rbp-90h] BYREF
  _OWORD v30[4]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v31; // [rsp+C8h] [rbp-40h]
  int v32; // [rsp+D0h] [rbp-38h]
  wchar_t v33; // [rsp+D4h] [rbp-34h]
  __int16 v34; // [rsp+D6h] [rbp-32h]
  int v35; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v36[2044]; // [rsp+DCh] [rbp-2Ch] BYREF

  v1 = 0;
  v30[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v32 = *(_DWORD *)L"0}";
  v3 = 0;
  v4 = 0;
  v30[2] = *(_OWORD *)L"000-0000-000000000000}";
  v5 = 0;
  v6 = 0;
  v30[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v7 = 0;
  v33 = a00000000000000[38];
  v31 = *(_QWORD *)L"00000}";
  v26 = 0;
  cbData[1] = 0;
  hKey = 0;
  v29 = 0;
  v28 = 0;
  v30[3] = *(_OWORD *)L"-000000000000}";
  v34 = 0;
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  v9 = dword_1800CF650;
  if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)a1->Data4 == *(_QWORD *)GUID_NULL.Data4 )
    v1 = 1;
  else
    MprConvertGuidToString(a1, v8, v30);
  v10 = 0;
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v35) = 0;
    FormatRRASErrorString(&v35, L"HelperV4ChangeNotification for RDID-%ws", v30);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v35);
    v10 = 0;
  }
  if ( v9 && !v1 )
    goto LABEL_15;
  v3 = dword_1800D08DC;
  v6 = HIDWORD(qword_1800D08F0);
  v7 = (__m128i)pclsid;
  *(_DWORD *)Data = 1;
  *a1 = GUID_NULL;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip",
          0,
          0x20019u,
          &hKey) )
  {
    cbData[1] = 4;
    if ( RegQueryValueExA(hKey, "UseDhcpAddressing", 0, 0, Data, &cbData[1]) )
      *(_DWORD *)Data = 1;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  helperReadRegistry();
  v10 = 0;
  if ( v9 )
LABEL_15:
    *(_DWORD *)Data = 0;
  else
    v10 = *(_DWORD *)Data;
  if ( !v10 )
  {
    *(GUID *)&v24[1] = *a1;
    RasStatCreatePoolList(&v24[1], &v26, &v29);
    v4 = v26;
  }
  EnterCriticalSection(&RasSrvrCriticalSection);
  LODWORD(v26) = 0;
  cbData[0] = 4;
  RasRoutingDomainGetConfigParam(a1, 2, cbData, &v26);
  *(GUID *)&v24[1] = *a1;
  if ( !(_DWORD)v26 )
  {
    dword_1800D08DC = *(_DWORD *)Data;
    v14 = RasStatAddRoutingDomainv4AddressPool(v4);
    if ( v14 )
    {
      if ( !(_QWORD)xmmword_1800D0740 )
        goto LABEL_72;
      v15 = L"RasStatAddRoutingDomainv4AddressPool failed and returned %d";
      goto LABEL_78;
    }
LABEL_71:
    v4 = 0;
    goto LABEL_72;
  }
  RasSrvrEnableRouter(&v24[1], (unsigned int)qword_1800D08F0);
  if ( !v9 || v1 )
  {
    *(GUID *)&v24[1] = *a1;
    RoutingDomainAddressPool = RasGetRoutingDomainAddressPool(&v24[1], 1, &v28);
    v17 = RoutingDomainAddressPool == 0;
    if ( !RoutingDomainAddressPool && v28 )
      v5 = *(_QWORD *)(v28 + 48);
    if ( v3 != *(_DWORD *)Data
      || !*(_DWORD *)Data && (unsigned int)RasStatAddrPoolsDiffer(v5, v4)
      || (v18 = v17, *(_DWORD *)Data)
      && (v6 != HIDWORD(qword_1800D08F0)
       || v6
       && (v7.m128i_i64[0] != *(_QWORD *)&pclsid.Data1 || _mm_srli_si128(v7, 8).m128i_u64[0] != *(_QWORD *)pclsid.Data4)) )
    {
      v18 = v17;
      if ( !RoutingDomainAddressPool )
      {
        *(GUID *)&v24[1] = *a1;
        v19 = RasReleaseRoutingDomainAddressPool(&v24[1]);
        if ( v19 )
        {
          if ( (_QWORD)xmmword_1800D0740 )
          {
            LOWORD(v35) = 0;
            FormatRRASErrorString(
              &v35,
              L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
              v19);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800D0740,
              &v35);
          }
        }
        else
        {
          v18 = 0;
        }
      }
      LeaveCriticalSection(&RasSrvrCriticalSection);
      *(GUID *)&v24[1] = *a1;
      RasSrvrStop(&v24[1], 0, 1);
      EnterCriticalSection(&RasSrvrCriticalSection);
      *(GUID *)&v24[1] = *a1;
      dword_1800D08DC = *(_DWORD *)Data;
      v20 = RasStatAddRoutingDomainv4AddressPool(v4);
      if ( v20 )
      {
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v35) = 0;
          FormatRRASErrorString(&v35, L"RasStatAddRoutingDomainv4AddressPool failed and returned %d", v20);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v35);
        }
      }
      else
      {
        v4 = 0;
      }
      *(GUID *)&v24[1] = *a1;
      v21 = RasSrvrStart(&v24[1]);
      if ( v21 && (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v35, L"RasSrvrStart failed and returned %d", v21);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v35);
      }
    }
    if ( v18 )
    {
      *(GUID *)&v24[1] = *a1;
      v22 = RasReleaseRoutingDomainAddressPool(&v24[1]);
      if ( v22 )
      {
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v35) = 0;
          FormatRRASErrorString(&v35, L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d", v22);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v35);
        }
      }
    }
    if ( *(_DWORD *)Data )
      goto LABEL_72;
    if ( !v4 )
      goto LABEL_74;
    RasStatFreeAddrPool(v4);
    goto LABEL_71;
  }
  *(GUID *)&v24[1] = *a1;
  if ( !(unsigned int)RasGetRoutingDomainAddressPool(&v24[1], 1, &v28) && v28 )
    v5 = *(_QWORD *)(v28 + 48);
  if ( (unsigned int)RasStatAddrPoolsDiffer(v5, v4) )
  {
    if ( !v11 )
    {
      *(GUID *)&v24[1] = *a1;
      v12 = RasReleaseRoutingDomainAddressPool(&v24[1]);
      if ( v12 )
      {
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v35) = 0;
          FormatRRASErrorString(&v35, L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d", v12);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v35);
        }
      }
    }
    LeaveCriticalSection(&RasSrvrCriticalSection);
    *(GUID *)&v24[1] = *a1;
    RasSrvrStop(&v24[1], 0, 1);
    EnterCriticalSection(&RasSrvrCriticalSection);
    *(GUID *)&v24[1] = *a1;
    v13 = RasStatAddRoutingDomainv4AddressPool(v4);
    if ( v13 )
    {
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v35, L"RasStatAddRoutingDomainv4AddressPool failed and returned %d", v13);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v35);
      }
    }
    else
    {
      v4 = 0;
    }
    *(GUID *)&v24[1] = *a1;
    v14 = RasSrvrStart(&v24[1]);
    if ( !v14 || !(_QWORD)xmmword_1800D0740 )
      goto LABEL_72;
    v15 = L"RasSrvrStart failed and returned %d";
    goto LABEL_78;
  }
  if ( !v11 )
  {
    *(GUID *)&v24[1] = *a1;
    v14 = RasReleaseRoutingDomainAddressPool(&v24[1]);
    if ( v14 )
    {
      if ( (_QWORD)xmmword_1800D0740 )
      {
        v15 = L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d";
LABEL_78:
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v35, v15, v14);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v35);
      }
    }
  }
LABEL_72:
  if ( v4 )
    RasStatFreeAddrPool(v4);
LABEL_74:
  LeaveCriticalSection(&RasSrvrCriticalSection);
}

```

## disassembly

```asm
0x180051a00  mov     rax, rsp
0x180051a03  mov     [rax+10h], rbx
0x180051a07  mov     [rax+18h], rsi
0x180051a0b  mov     [rax+20h], rdi
0x180051a0f  push    rbp
0x180051a10  push    r12
0x180051a12  push    r13
0x180051a14  push    r14
0x180051a16  push    r15
0x180051a18  lea     rbp, [rax-818h]
0x180051a1f  sub     rsp, 8F0h
0x180051a26  movaps  xmmword ptr [rax-38h], xmm6
0x180051a2a  mov     rax, cs:__security_cookie
0x180051a31  xor     rax, rsp
0x180051a34  mov     [rbp+810h+var_40], rax
0x180051a3b  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180051a42  xor     esi, esi
0x180051a44  mov     eax, dword ptr cs:a00000000000000+48h; "0}"
0x180051a4a  mov     rbx, rcx
0x180051a4d  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x180051a54  lea     rcx, [rbp+810h+var_83C]; void *
0x180051a58  movaps  [rbp+810h+var_890], xmm0
0x180051a5c  xor     edx, edx; Val
0x180051a5e  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180051a65  mov     r8d, 7FCh; Size
0x180051a6b  mov     [rbp+810h+var_848], eax
0x180051a6e  mov     r13d, esi
0x180051a71  movzx   eax, word ptr cs:a00000000000000+4Ch; ""
0x180051a78  mov     edi, esi
0x180051a7a  movaps  [rbp+810h+var_870], xmm0
0x180051a7e  mov     r15d, esi
0x180051a81  movsd   xmm0, qword ptr cs:a00000000000000+40h; "00000}"
0x180051a89  mov     r12d, esi
0x180051a8c  movaps  [rbp+810h+var_880], xmm1
0x180051a90  xorps   xmm6, xmm6
0x180051a93  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180051a9a  mov     [rbp+810h+var_844], ax
0x180051a9e  xor     eax, eax
0x180051aa0  movsd   [rbp+810h+var_850], xmm0
0x180051aa5  mov     [rsp+910h+var_8B8], rsi
0x180051aaa  mov     [rsp+910h+cbData+4], esi
0x180051aae  mov     [rsp+910h+hKey], rsi
0x180051ab3  mov     [rsp+910h+var_8A0], rsi
0x180051ab8  mov     [rsp+910h+var_8A8], rsi
0x180051abd  movaps  [rbp+810h+var_860], xmm1
0x180051ac1  mov     [rbp+810h+var_842], ax
0x180051ac5  mov     [rbp+810h+var_840], esi
0x180051ac8  call    memset_0
0x180051acd  mov     rax, [rbx]
0x180051ad0  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180051ad7  mov     r14d, cs:dword_1800CF650
0x180051ade  jnz     short loc_180051AF3
0x180051ae0  mov     rax, [rbx+8]
0x180051ae4  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180051aeb  jnz     short loc_180051AF3
0x180051aed  lea     esi, [r15+1]
0x180051af1  jmp     short loc_180051AFF
0x180051af3  lea     r8, [rbp+810h+var_890]
0x180051af7  mov     rcx, rbx
0x180051afa  call    MprConvertGuidToString
0x180051aff  xor     eax, eax
0x180051b01  cmp     qword ptr cs:xmmword_1800D0740, rax
0x180051b08  jz      short loc_180051B42
0x180051b0a  lea     r8, [rbp+810h+var_890]
0x180051b0e  mov     word ptr [rbp+810h+var_840], ax
0x180051b12  lea     rdx, aHelperv4change; "HelperV4ChangeNotification for RDID-%ws"
0x180051b19  lea     rcx, [rbp+810h+var_840]
0x180051b1d  call    FormatRRASErrorString
0x180051b22  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180051b29  lea     r8, [rbp+810h+var_840]
0x180051b2d  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180051b34  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180051b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b40  xor     eax, eax
0x180051b42  test    r14d, r14d
0x180051b45  jz      short loc_180051B4F
0x180051b47  test    esi, esi
0x180051b49  jz      loc_180051C15
0x180051b4f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180051b56  mov     r13d, cs:dword_1800D08DC
0x180051b5d  lea     rax, [rsp+910h+hKey]
0x180051b62  mov     r12d, dword ptr cs:qword_1800D08F0+4
0x180051b69  lea     rdx, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Re"...
0x180051b70  movups  xmm6, xmmword ptr cs:pclsid.Data1
0x180051b77  mov     r9d, 20019h; samDesired
0x180051b7d  mov     dword ptr [rsp+910h+Data], 1
0x180051b85  xor     r8d, r8d; ulOptions
0x180051b88  mov     [rsp+910h+phkResult], rax; phkResult
0x180051b8d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180051b94  movdqu  xmmword ptr [rbx], xmm0
0x180051b98  call    cs:__imp_RegOpenKeyExA
0x180051b9f  nop     dword ptr [rax+rax+00h]
0x180051ba4  test    eax, eax
0x180051ba6  jnz     short loc_180051BEE
0x180051ba8  mov     rcx, [rsp+910h+hKey]; hKey
0x180051bad  lea     rax, [rsp+910h+cbData+4]
0x180051bb2  mov     [rsp+910h+lpcbData], rax; lpcbData
0x180051bb7  lea     rdx, aUsedhcpaddress; "UseDhcpAddressing"
0x180051bbe  lea     rax, [rsp+910h+Data]
0x180051bc3  mov     [rsp+910h+cbData+4], 4
0x180051bcb  xor     r9d, r9d; lpType
0x180051bce  mov     [rsp+910h+phkResult], rax; lpData
0x180051bd3  xor     r8d, r8d; lpReserved
0x180051bd6  call    cs:__imp_RegQueryValueExA
0x180051bdd  nop     dword ptr [rax+rax+00h]
0x180051be2  test    eax, eax
0x180051be4  jz      short loc_180051BEE
0x180051be6  mov     dword ptr [rsp+910h+Data], 1
0x180051bee  mov     rcx, [rsp+910h+hKey]; hKey
0x180051bf3  test    rcx, rcx
0x180051bf6  jz      short loc_180051C09
0x180051bf8  call    cs:__imp_RegCloseKey
0x180051bff  nop     dword ptr [rax+rax+00h]
0x180051c04  and     [rsp+910h+hKey], rdi
0x180051c09  call    ?helperReadRegistry@@YAXXZ; helperReadRegistry(void)
0x180051c0e  xor     eax, eax
0x180051c10  test    r14d, r14d
0x180051c13  jz      short loc_180051C1B
0x180051c15  mov     dword ptr [rsp+910h+Data], eax
0x180051c19  jmp     short loc_180051C1F
0x180051c1b  mov     eax, dword ptr [rsp+910h+Data]
0x180051c1f  test    eax, eax
0x180051c21  jnz     short loc_180051C45
0x180051c23  movups  xmm0, xmmword ptr [rbx]
0x180051c26  lea     r8, [rsp+910h+var_8A0]
0x180051c2b  lea     rdx, [rsp+910h+var_8B8]
0x180051c30  lea     rcx, [rsp+910h+var_8D8+8]
0x180051c35  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x180051c3b  call    RasStatCreatePoolList
0x180051c40  mov     rdi, [rsp+910h+var_8B8]
0x180051c45  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180051c4c  call    cs:__imp_EnterCriticalSection
0x180051c53  nop     dword ptr [rax+rax+00h]
0x180051c58  and     dword ptr [rsp+910h+var_8B8], r15d
0x180051c5d  lea     r9, [rsp+910h+var_8B8]
0x180051c62  lea     r8, [rsp+910h+cbData]
0x180051c67  mov     [rsp+910h+cbData], 4
0x180051c6f  mov     edx, 2
0x180051c74  mov     rcx, rbx
0x180051c77  call    RasRoutingDomainGetConfigParam
0x180051c7c  movups  xmm0, xmmword ptr [rbx]
0x180051c7f  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x180051c85  cmp     dword ptr [rsp+910h+var_8B8], r15d
0x180051c8a  jz      loc_18005213C
0x180051c90  mov     edx, dword ptr cs:qword_1800D08F0
0x180051c96  lea     rcx, [rsp+910h+var_8D8+8]
0x180051c9b  call    RasSrvrEnableRouter
0x180051ca0  test    r14d, r14d
0x180051ca3  jz      loc_180051E68
0x180051ca9  test    esi, esi
0x180051cab  jnz     loc_180051E68
0x180051cb1  movups  xmm0, xmmword ptr [rbx]
0x180051cb4  mov     esi, 1
0x180051cb9  lea     r8, [rsp+910h+var_8A8]
0x180051cbe  mov     edx, esi
0x180051cc0  lea     rcx, [rsp+910h+var_8D8+8]
0x180051cc5  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x180051ccb  call    RasGetRoutingDomainAddressPool
0x180051cd0  xor     r13d, r13d
0x180051cd3  mov     r10d, eax
0x180051cd6  test    eax, eax
0x180051cd8  jnz     short loc_180051CE8
0x180051cda  mov     rax, [rsp+910h+var_8A8]
0x180051cdf  test    rax, rax
0x180051ce2  jz      short loc_180051CE8
0x180051ce4  mov     r15, [rax+30h]
0x180051ce8  mov     rdx, rdi
0x180051ceb  mov     rcx, r15
0x180051cee  call    RasStatAddrPoolsDiffer
0x180051cf3  test    eax, eax
0x180051cf5  jz      loc_180051E2B
0x180051cfb  test    r10d, r10d
0x180051cfe  jnz     short loc_180051D56
0x180051d00  movups  xmm0, xmmword ptr [rbx]
0x180051d03  lea     rcx, [rsp+910h+var_8D8+8]
0x180051d08  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x180051d0e  call    RasReleaseRoutingDomainAddressPool
0x180051d13  test    eax, eax
0x180051d15  jz      short loc_180051D56
0x180051d17  cmp     qword ptr cs:xmmword_1800D0740, r13
0x180051d1e  jz      short loc_180051D56
0x180051d20  mov     r8d, eax
0x180051d23  mov     word ptr [rbp+810h+var_840], r13w
0x180051d28  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x180051d2f  lea     rcx, [rbp+810h+var_840]
0x180051d33  call    FormatRRASErrorString
0x180051d38  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180051d3f  lea     r8, [rbp+810h+var_840]
0x180051d43  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180051d4a  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180051d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d56  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180051d5d  call    cs:__imp_LeaveCriticalSection
0x180051d64  nop     dword ptr [rax+rax+00h]
0x180051d69  movups  xmm0, xmmword ptr [rbx]
0x180051d6c  mov     r8d, esi
0x180051d6f  lea     rcx, [rsp+910h+var_8D8+8]
0x180051d74  xor     edx, edx
0x180051d76  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x180051d7c  call    RasSrvrStop
0x180051d81  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180051d88  call    cs:__imp_EnterCriticalSection
0x180051d8f  nop     dword ptr [rax+rax+00h]
0x180051d94  movups  xmm0, xmmword ptr [rbx]
0x180051d97  mov     r8, [rsp+910h+var_8A0]
0x180051d9c  lea     rdx, [rsp+910h+var_8D8+8]
0x180051da1  mov     rcx, rdi; struct _ADDR_POOL *
0x180051da4  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x180051daa  call    RasStatAddRoutingDomainv4AddressPool
0x180051daf  test    eax, eax
0x180051db1  jz      short loc_180051DF4
0x180051db3  cmp     qword ptr cs:xmmword_1800D0740, r13
0x180051dba  jz      short loc_180051DF7
0x180051dbc  mov     r8d, eax
0x180051dbf  mov     word ptr [rbp+810h+var_840], r13w
0x180051dc4  lea     rdx, aRasstataddrout; "RasStatAddRoutingDomainv4AddressPool fa"...
0x180051dcb  lea     rcx, [rbp+810h+var_840]
0x180051dcf  call    FormatRRASErrorString
0x180051dd4  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180051ddb  lea     r8, [rbp+810h+var_840]
0x180051ddf  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180051de6  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180051ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051df2  jmp     short loc_180051DF7
0x180051df4  mov     rdi, r13
0x180051df7  movups  xmm0, xmmword ptr [rbx]
0x180051dfa  lea     rcx, [rsp+910h+var_8D8+8]
0x180051dff  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x180051e05  call    RasSrvrStart
0x180051e0a  test    eax, eax
0x180051e0c  jz      loc_1800520E6
0x180051e12  cmp     qword ptr cs:xmmword_1800D0740, r13
0x180051e19  jz      loc_1800520E6
0x180051e1f  lea     rdx, aRassrvrstartFa; "RasSrvrStart failed and returned %d"
0x180051e26  jmp     loc_180052173
0x180051e2b  test    r10d, r10d
0x180051e2e  jnz     loc_1800520E6
0x180051e34  movups  xmm0, xmmword ptr [rbx]
0x180051e37  lea     rcx, [rsp+910h+var_8D8+8]
0x180051e3c  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x180051e42  call    RasReleaseRoutingDomainAddressPool
0x180051e47  test    eax, eax
0x180051e49  jz      loc_1800520E6
0x180051e4f  cmp     qword ptr cs:xmmword_1800D0740, r13
0x180051e56  jz      loc_1800520E6
0x180051e5c  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x180051e63  jmp     loc_180052173
0x180051e68  movups  xmm0, xmmword ptr [rbx]
0x180051e6b  lea     r8, [rsp+910h+var_8A8]
0x180051e70  mov     edx, 1
0x180051e75  lea     rcx, [rsp+910h+var_8D8+8]
0x180051e7a  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x180051e80  call    RasGetRoutingDomainAddressPool
0x180051e85  mov     r10d, eax
0x180051e88  xor     eax, eax
0x180051e8a  test    r10d, r10d
0x180051e8d  mov     r14d, eax
0x180051e90  setz    r14b
0x180051e94  test    r10d, r10d
0x180051e97  jnz     short loc_180051EA7
0x180051e99  mov     rcx, [rsp+910h+var_8A8]
0x180051e9e  test    rcx, rcx
0x180051ea1  jz      short loc_180051EA7
0x180051ea3  mov     r15, [rcx+30h]
0x180051ea7  mov     eax, dword ptr [rsp+910h+Data]
0x180051eab  cmp     r13d, eax
0x180051eae  jnz     short loc_180051F0C
0x180051eb0  xor     r13d, r13d
0x180051eb3  test    eax, eax
0x180051eb5  jnz     short loc_180051EC6
0x180051eb7  mov     rdx, rdi
0x180051eba  mov     rcx, r15
0x180051ebd  call    RasStatAddrPoolsDiffer
0x180051ec2  test    eax, eax
0x180051ec4  jnz     short loc_180051F0F
0x180051ec6  mov     esi, r14d
0x180051ec9  cmp     dword ptr [rsp+910h+Data], r13d
0x180051ece  jz      loc_180052074
0x180051ed4  cmp     r12d, dword ptr cs:qword_1800D08F0+4
0x180051edb  jnz     short loc_180051F0F
0x180051edd  test    r12d, r12d
0x180051ee0  jz      loc_180052074
0x180051ee6  movq    rax, xmm6
0x180051eeb  cmp     rax, qword ptr cs:pclsid.Data1
0x180051ef2  jnz     short loc_180051F0F
0x180051ef4  psrldq  xmm6, 8
0x180051ef9  movq    rax, xmm6
0x180051efe  cmp     rax, qword ptr cs:pclsid.Data4
0x180051f05  jnz     short loc_180051F0F
0x180051f07  jmp     loc_180052074
0x180051f0c  xor     r13d, r13d
0x180051f0f  mov     esi, r14d
0x180051f12  test    r10d, r10d
0x180051f15  jnz     short loc_180051F72
0x180051f17  movups  xmm0, xmmword ptr [rbx]
0x180051f1a  lea     rcx, [rsp+910h+var_8D8+8]
0x180051f1f  movdqu  xmmword ptr [rsp+910h+var_8D8+8], xmm0
0x180051f25  call    RasReleaseRoutingDomainAddressPool
0x180051f2a  test    eax, eax
0x180051f2c  jz      short loc_180051F6F
  ... truncated ...
```
