# HelperV4ChangeNotification

- ea: `0x180050110`
- end: `0x180050863`
- name: `HelperV4ChangeNotification`
- size: `1875`
- prototype: `__int64 __fastcall(void *Buf1)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task`

## callers

- `0x18001abb0`
- `0x180055114`

## callees

- `0x180002bbe`
- `0x18004eb94`
- `0x180050110`
- `0x180054408`
- `0x180056d88`
- `0x180056f10`
- `0x1800588f4`
- `0x180058dc4`
- `0x180058e78`
- `0x1800591e8`
- `0x18005b998`
- `0x18005bd78`
- `0x180071cec`
- `0x180073664`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800507b0`
- `KERNEL32!LocalFree` at `0x180050828`
- `KERNEL32!LocalFree` at `0x1800507b0`
- `KERNEL32!LocalFree` at `0x180050828`
- `KERNEL32!LeaveCriticalSection` at `0x18005044d`
- `KERNEL32!LeaveCriticalSection` at `0x18005064c`
- `KERNEL32!LeaveCriticalSection` at `0x18005083a`
- `KERNEL32!LeaveCriticalSection` at `0x18005044d`
- `KERNEL32!LeaveCriticalSection` at `0x18005064c`
- `KERNEL32!LeaveCriticalSection` at `0x18005083a`
- `KERNEL32!EnterCriticalSection` at `0x18005033d`
- `KERNEL32!EnterCriticalSection` at `0x180050472`
- `KERNEL32!EnterCriticalSection` at `0x180050672`
- `KERNEL32!EnterCriticalSection` at `0x18005033d`
- `KERNEL32!EnterCriticalSection` at `0x180050472`
- `KERNEL32!EnterCriticalSection` at `0x180050672`
- `ADVAPI32!RegCloseKey` at `0x1800502ea`
- `ADVAPI32!RegCloseKey` at `0x1800502ea`
- `ADVAPI32!RegOpenKeyExA` at `0x180050296`
- `ADVAPI32!RegOpenKeyExA` at `0x180050296`
- `ADVAPI32!RegQueryValueExA` at `0x1800502ce`
- `ADVAPI32!RegQueryValueExA` at `0x1800502ce`

## string_xrefs

- `0x180050262`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`

## pseudocode

```c
void __fastcall HelperV4ChangeNotification(GUID *Buf1)
{
  int v1; // r12d
  struct _ADDR_POOL *v3; // rbx
  int v4; // r15d
  __int64 v5; // rdx
  int v6; // esi
  int v7; // r13d
  int v8; // eax
  __int64 v9; // r14
  int v10; // r9d
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  const wchar_t *v14; // rdx
  int RoutingDomainAddressPool; // r15d
  BOOL v16; // esi
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  struct _ADDR_POOL *v21; // rcx
  struct _ADDR_POOL *v22; // rcx
  BYTE Data[16]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v24; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+54h] [rbp-ACh] BYREF
  struct _ADDR_POOL *v27; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  GUID Buf1a; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v32[3]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v33[30]; // [rsp+C0h] [rbp-40h]
  __int16 v34; // [rsp+DEh] [rbp-22h]
  int v35; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v36[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  v1 = 0;
  v32[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  Buf1a = 0;
  v3 = 0;
  v32[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v32[2] = *(_OWORD *)L"000-0000-000000000000}";
  *(_DWORD *)Data = 0;
  *(_OWORD *)v33 = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)&v33[14] = *(_OWORD *)L"000000}";
  v27 = 0;
  cbData = 0;
  hKey = 0;
  v30 = 0;
  v29 = 0;
  v34 = 0;
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  v4 = dword_1800C8650;
  if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
  {
    v6 = 1;
  }
  else
  {
    v6 = 0;
    MprConvertGuidToString(Buf1, v5, v32);
  }
  if ( (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v35) = 0;
    FormatRRASErrorString(&v35, L"HelperV4ChangeNotification for RDID-%ws", v32);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v35);
  }
  if ( v4 && !v6 )
  {
    v7 = 0;
LABEL_15:
    v8 = 0;
    *(_DWORD *)Data = 0;
    goto LABEL_17;
  }
  v1 = HIDWORD(qword_1800C98F0);
  *(_DWORD *)Data = 1;
  v7 = dword_1800C98DC;
  *Buf1 = GUID_NULL;
  Buf1a = Buf2;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( RegQueryValueExA(hKey, "UseDhcpAddressing", 0, 0, Data, &cbData) )
      *(_DWORD *)Data = 1;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  helperReadRegistry();
  if ( v4 )
    goto LABEL_15;
  v8 = *(_DWORD *)Data;
LABEL_17:
  if ( !v8 )
  {
    v24 = *Buf1;
    RasStatCreatePoolList(&v24, &v27, &v30);
    v3 = v27;
  }
  EnterCriticalSection(&RasSrvrCriticalSection);
  v26 = 0;
  LODWORD(v27) = 4;
  RasRoutingDomainGetConfigParam(Buf1, 2, &v27, &v26);
  v24 = *Buf1;
  if ( v26 )
  {
    v9 = 0;
    RasSrvrEnableRouter(&v24, (unsigned int)qword_1800C98F0);
    if ( v4 && !v6 )
    {
      v24 = *Buf1;
      if ( !(unsigned int)RasGetRoutingDomainAddressPool(&v24, 1, &v29) && v29 )
        v9 = *(_QWORD *)(v29 + 48);
      if ( (unsigned int)RasStatAddrPoolsDiffer(v9, v3) )
      {
        if ( !v10 )
        {
          v24 = *Buf1;
          v11 = RasReleaseRoutingDomainAddressPool(&v24);
          if ( v11 )
          {
            if ( (_QWORD)xmmword_1800C9740 )
            {
              LOWORD(v35) = 0;
              FormatRRASErrorString(
                &v35,
                L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
                v11);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
                gRasIpAddrMgmtEtwContext,
                xmmword_1800C9740,
                &v35);
            }
          }
        }
        LeaveCriticalSection(&RasSrvrCriticalSection);
        v24 = *Buf1;
        RasSrvrStop((__int128 *)&v24, 0, 1);
        EnterCriticalSection(&RasSrvrCriticalSection);
        v24 = *Buf1;
        v12 = RasStatAddRoutingDomainv4AddressPool(v3);
        if ( v12 )
        {
          if ( (_QWORD)xmmword_1800C9740 )
          {
            LOWORD(v35) = 0;
            FormatRRASErrorString(&v35, L"RasStatAddRoutingDomainv4AddressPool failed and returned %d", v12);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800C9740,
              &v35);
          }
        }
        else
        {
          v3 = 0;
        }
        v24 = *Buf1;
        v13 = RasSrvrStart(&v24);
        if ( !v13 || !(_QWORD)xmmword_1800C9740 )
          goto LABEL_76;
        v14 = L"RasSrvrStart failed and returned %d";
      }
      else
      {
        if ( v10 )
          goto LABEL_76;
        v24 = *Buf1;
        v13 = RasReleaseRoutingDomainAddressPool(&v24);
        if ( !v13 || !(_QWORD)xmmword_1800C9740 )
          goto LABEL_76;
        v14 = L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d";
      }
      goto LABEL_74;
    }
    v24 = *Buf1;
    RoutingDomainAddressPool = RasGetRoutingDomainAddressPool(&v24, 1, &v29);
    v16 = RoutingDomainAddressPool == 0;
    if ( !RoutingDomainAddressPool && v29 )
      v9 = *(_QWORD *)(v29 + 48);
    if ( v7 != *(_DWORD *)Data )
      goto LABEL_51;
    if ( *(_DWORD *)Data )
      goto LABEL_80;
    if ( (unsigned int)RasStatAddrPoolsDiffer(v9, v3) )
    {
LABEL_51:
      if ( !RoutingDomainAddressPool )
      {
        v24 = *Buf1;
        v17 = RasReleaseRoutingDomainAddressPool(&v24);
        if ( v17 )
        {
          if ( (_QWORD)xmmword_1800C9740 )
          {
            LOWORD(v35) = 0;
            FormatRRASErrorString(
              &v35,
              L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
              v17);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800C9740,
              &v35);
          }
        }
        else
        {
          v16 = 0;
        }
      }
      LeaveCriticalSection(&RasSrvrCriticalSection);
      v24 = *Buf1;
      RasSrvrStop((__int128 *)&v24, 0, 1);
      EnterCriticalSection(&RasSrvrCriticalSection);
      v24 = *Buf1;
      dword_1800C98DC = *(_DWORD *)Data;
      v18 = RasStatAddRoutingDomainv4AddressPool(v3);
      if ( v18 )
      {
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v35) = 0;
          FormatRRASErrorString(&v35, L"RasStatAddRoutingDomainv4AddressPool failed and returned %d", v18);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v35);
        }
      }
      else
      {
        v3 = 0;
      }
      v24 = *Buf1;
      v19 = RasSrvrStart(&v24);
      if ( v19 && (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v35, L"RasSrvrStart failed and returned %d", v19);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v35);
      }
      goto LABEL_63;
    }
    if ( *(_DWORD *)Data )
    {
LABEL_80:
      if ( v1 != HIDWORD(qword_1800C98F0) || v1 && memcmp_0(&Buf1a, &Buf2, 0x10u) )
        goto LABEL_51;
    }
LABEL_63:
    if ( v16 )
    {
      v24 = *Buf1;
      v20 = RasReleaseRoutingDomainAddressPool(&v24);
      if ( v20 )
      {
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v35) = 0;
          FormatRRASErrorString(&v35, L"RasReleaseRoutingDomainAddressPool failed to release lock and returned %d", v20);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v35);
        }
      }
    }
    if ( *(_DWORD *)Data )
      goto LABEL_76;
    if ( !v3 )
      goto LABEL_77;
    do
    {
      v21 = v3;
      v3 = *(struct _ADDR_POOL **)v3;
      LocalFree(v21);
    }
    while ( v3 );
    goto LABEL_70;
  }
  dword_1800C98DC = *(_DWORD *)Data;
  v13 = RasStatAddRoutingDomainv4AddressPool(v3);
  if ( !v13 )
  {
LABEL_70:
    v3 = 0;
    goto LABEL_76;
  }
  if ( !(_QWORD)xmmword_1800C9740 )
    goto LABEL_76;
  v14 = L"RasStatAddRoutingDomainv4AddressPool failed and returned %d";
LABEL_74:
  LOWORD(v35) = 0;
  FormatRRASErrorString(&v35, v14, v13);
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
    gRasIpAddrMgmtEtwContext,
    xmmword_1800C9740,
    &v35);
LABEL_76:
  while ( v3 )
  {
    v22 = v3;
    v3 = *(struct _ADDR_POOL **)v3;
    LocalFree(v22);
  }
LABEL_77:
  LeaveCriticalSection(&RasSrvrCriticalSection);
}

```

## disassembly

```asm
0x180050110  push    rbp
0x180050112  push    rbx
0x180050113  push    rsi
0x180050114  push    rdi
0x180050115  push    r12
0x180050117  push    r13
0x180050119  push    r14
0x18005011b  push    r15
0x18005011d  lea     rbp, [rsp-7F8h]
0x180050125  sub     rsp, 8F8h
0x18005012c  mov     rax, cs:__security_cookie
0x180050133  xor     rax, rsp
0x180050136  mov     [rbp+830h+var_50], rax
0x18005013d  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x180050144  xor     r12d, r12d
0x180050147  xorps   xmm0, xmm0
0x18005014a  movaps  [rbp+830h+var_890], xmm1
0x18005014e  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180050155  mov     rdi, rcx
0x180050158  movups  xmmword ptr [rsp+930h+Buf1.Data1], xmm0
0x18005015d  lea     rcx, [rbp+830h+var_84C]; void *
0x180050161  xor     eax, eax
0x180050163  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x18005016a  mov     ebx, r12d
0x18005016d  movaps  [rbp+830h+var_8A0], xmm0
0x180050171  xor     edx, edx; Val
0x180050173  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x18005017a  mov     r8d, 7FCh; Size
0x180050180  movaps  [rbp+830h+var_880], xmm0
0x180050184  mov     r14d, r12d
0x180050187  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x18005018e  mov     dword ptr [rsp+930h+Data], r12d
0x180050193  movaps  xmmword ptr [rbp+830h+var_870], xmm1
0x180050197  movups  xmmword ptr [rbp+830h+var_870+0Eh], xmm0
0x18005019b  mov     [rsp+930h+var_8D8], rbx
0x1800501a0  mov     [rsp+930h+cbData], r12d
0x1800501a5  mov     [rsp+930h+hKey], r12
0x1800501aa  mov     [rsp+930h+var_8C0], r12
0x1800501af  mov     [rsp+930h+var_8C8], r12
0x1800501b4  mov     [rbp+830h+var_852], ax
0x1800501b8  mov     [rbp+830h+var_850], r12d
0x1800501bc  call    memset_0
0x1800501c1  mov     r15d, cs:dword_1800C8650
0x1800501c8  lea     r8d, [r12+10h]; Size
0x1800501cd  lea     rdx, GUID_NULL; Buf2
0x1800501d4  mov     rcx, rdi; Buf1
0x1800501d7  call    memcmp_0
0x1800501dc  lea     r13d, [r12+1]
0x1800501e1  test    eax, eax
0x1800501e3  jnz     short loc_1800501EA
0x1800501e5  mov     esi, r13d
0x1800501e8  jmp     short loc_1800501F9
0x1800501ea  lea     r8, [rbp+830h+var_8A0]
0x1800501ee  mov     rcx, rdi
0x1800501f1  mov     esi, r12d
0x1800501f4  call    MprConvertGuidToString
0x1800501f9  cmp     qword ptr cs:xmmword_1800C9740, r12
0x180050200  jz      short loc_180050239
0x180050202  lea     r8, [rbp+830h+var_8A0]
0x180050206  mov     word ptr [rbp+830h+var_850], r12w
0x18005020b  lea     rdx, aHelperv4change; "HelperV4ChangeNotification for RDID-%ws"
0x180050212  lea     rcx, [rbp+830h+var_850]
0x180050216  call    FormatRRASErrorString
0x18005021b  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180050222  lea     r8, [rbp+830h+var_850]
0x180050226  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005022d  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050239  test    r15d, r15d
0x18005023c  jz      short loc_18005024A
0x18005023e  test    esi, esi
0x180050240  jnz     short loc_18005024A
0x180050242  mov     r13d, r12d
0x180050245  jmp     loc_1800502FF
0x18005024a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180050251  mov     r12d, dword ptr cs:qword_1800C98F0+4
0x180050258  lea     rax, [rsp+930h+hKey]
0x18005025d  mov     dword ptr [rsp+930h+Data], r13d
0x180050262  lea     rdx, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Re"...
0x180050269  mov     r13d, cs:dword_1800C98DC
0x180050270  mov     r9d, 20019h; samDesired
0x180050276  movdqu  xmmword ptr [rdi], xmm0
0x18005027a  xor     r8d, r8d; ulOptions
0x18005027d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180050284  movups  xmm0, xmmword ptr cs:Buf2.Data1
0x18005028b  mov     [rsp+930h+phkResult], rax; phkResult
0x180050290  movdqu  xmmword ptr [rsp+930h+Buf1.Data1], xmm0
0x180050296  call    cs:__imp_RegOpenKeyExA
0x18005029c  test    eax, eax
0x18005029e  jnz     short loc_1800502E0
0x1800502a0  mov     rcx, [rsp+930h+hKey]; hKey
0x1800502a5  lea     rax, [rsp+930h+cbData]
0x1800502aa  mov     [rsp+930h+lpcbData], rax; lpcbData
0x1800502af  lea     rdx, aUsedhcpaddress; "UseDhcpAddressing"
0x1800502b6  lea     rax, [rsp+930h+Data]
0x1800502bb  mov     [rsp+930h+cbData], 4
0x1800502c3  xor     r9d, r9d; lpType
0x1800502c6  mov     [rsp+930h+phkResult], rax; lpData
0x1800502cb  xor     r8d, r8d; lpReserved
0x1800502ce  call    cs:__imp_RegQueryValueExA
0x1800502d4  test    eax, eax
0x1800502d6  jz      short loc_1800502E0
0x1800502d8  mov     dword ptr [rsp+930h+Data], 1
0x1800502e0  mov     rcx, [rsp+930h+hKey]; hKey
0x1800502e5  test    rcx, rcx
0x1800502e8  jz      short loc_1800502F5
0x1800502ea  call    cs:__imp_RegCloseKey
0x1800502f0  mov     [rsp+930h+hKey], rbx
0x1800502f5  call    ?helperReadRegistry@@YAXXZ; helperReadRegistry(void)
0x1800502fa  test    r15d, r15d
0x1800502fd  jz      short loc_180050307
0x1800502ff  xor     eax, eax
0x180050301  mov     dword ptr [rsp+930h+Data], eax
0x180050305  jmp     short loc_18005030B
0x180050307  mov     eax, dword ptr [rsp+930h+Data]
0x18005030b  test    eax, eax
0x18005030d  jnz     short loc_180050336
0x18005030f  movups  xmm0, xmmword ptr [rdi]
0x180050312  lea     r8, [rsp+930h+var_8C0]
0x180050317  lea     rdx, [rsp+930h+var_8D8]
0x18005031c  lea     rcx, [rsp+930h+var_8F0]; Buf1
0x180050321  movdqu  [rsp+930h+var_8F0], xmm0
0x180050327  call    RasStatCreatePoolList
0x18005032c  mov     rbx, [rsp+930h+var_8D8]
0x180050331  mov     r14, [rsp+930h+var_8C0]
0x180050336  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005033d  call    cs:__imp_EnterCriticalSection
0x180050343  lea     r9, [rsp+930h+var_8DC]
0x180050348  mov     [rsp+930h+var_8DC], 0
0x180050350  lea     r8, [rsp+930h+var_8D8]
0x180050355  mov     dword ptr [rsp+930h+var_8D8], 4
0x18005035d  mov     edx, 2
0x180050362  mov     rcx, rdi
0x180050365  call    RasRoutingDomainGetConfigParam
0x18005036a  cmp     [rsp+930h+var_8DC], 0
0x18005036f  movups  xmm0, xmmword ptr [rdi]
0x180050372  movdqu  [rsp+930h+var_8F0], xmm0
0x180050378  jz      loc_1800507C0
0x18005037e  mov     edx, dword ptr cs:qword_1800C98F0
0x180050384  lea     rcx, [rsp+930h+var_8F0]
0x180050389  xor     r14d, r14d
0x18005038c  call    RasSrvrEnableRouter
0x180050391  test    r15d, r15d
0x180050394  jz      loc_18005054C
0x18005039a  test    esi, esi
0x18005039c  jnz     loc_18005054C
0x1800503a2  movups  xmm0, xmmword ptr [rdi]
0x1800503a5  lea     esi, [r14+1]
0x1800503a9  lea     r8, [rsp+930h+var_8C8]
0x1800503ae  mov     edx, esi
0x1800503b0  lea     rcx, [rsp+930h+var_8F0]
0x1800503b5  movdqu  [rsp+930h+var_8F0], xmm0
0x1800503bb  call    RasGetRoutingDomainAddressPool
0x1800503c0  xor     r13d, r13d
0x1800503c3  mov     r9d, eax
0x1800503c6  test    eax, eax
0x1800503c8  jnz     short loc_1800503D8
0x1800503ca  mov     rax, [rsp+930h+var_8C8]
0x1800503cf  test    rax, rax
0x1800503d2  jz      short loc_1800503D8
0x1800503d4  mov     r14, [rax+30h]
0x1800503d8  mov     rdx, rbx
0x1800503db  mov     rcx, r14
0x1800503de  call    RasStatAddrPoolsDiffer
0x1800503e3  test    eax, eax
0x1800503e5  jz      loc_18005050F
0x1800503eb  test    r9d, r9d
0x1800503ee  jnz     short loc_180050446
0x1800503f0  movups  xmm0, xmmword ptr [rdi]
0x1800503f3  lea     rcx, [rsp+930h+var_8F0]
0x1800503f8  movdqu  [rsp+930h+var_8F0], xmm0
0x1800503fe  call    RasReleaseRoutingDomainAddressPool
0x180050403  test    eax, eax
0x180050405  jz      short loc_180050446
0x180050407  cmp     qword ptr cs:xmmword_1800C9740, r13
0x18005040e  jz      short loc_180050446
0x180050410  mov     r8d, eax
0x180050413  mov     word ptr [rbp+830h+var_850], r13w
0x180050418  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x18005041f  lea     rcx, [rbp+830h+var_850]
0x180050423  call    FormatRRASErrorString
0x180050428  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005042f  lea     r8, [rbp+830h+var_850]
0x180050433  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005043a  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050446  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005044d  call    cs:__imp_LeaveCriticalSection
0x180050453  movups  xmm0, xmmword ptr [rdi]
0x180050456  mov     r8d, esi
0x180050459  lea     rcx, [rsp+930h+var_8F0]
0x18005045e  xor     edx, edx
0x180050460  movdqu  [rsp+930h+var_8F0], xmm0
0x180050466  call    RasSrvrStop
0x18005046b  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180050472  call    cs:__imp_EnterCriticalSection
0x180050478  movups  xmm0, xmmword ptr [rdi]
0x18005047b  mov     r8, [rsp+930h+var_8C0]
0x180050480  lea     rdx, [rsp+930h+var_8F0]
0x180050485  mov     rcx, rbx; struct _ADDR_POOL *
0x180050488  movdqu  [rsp+930h+var_8F0], xmm0
0x18005048e  call    RasStatAddRoutingDomainv4AddressPool
0x180050493  test    eax, eax
0x180050495  jz      short loc_1800504D8
0x180050497  cmp     qword ptr cs:xmmword_1800C9740, r13
0x18005049e  jz      short loc_1800504DB
0x1800504a0  mov     r8d, eax
0x1800504a3  mov     word ptr [rbp+830h+var_850], r13w
0x1800504a8  lea     rdx, aRasstataddrout; "RasStatAddRoutingDomainv4AddressPool fa"...
0x1800504af  lea     rcx, [rbp+830h+var_850]
0x1800504b3  call    FormatRRASErrorString
0x1800504b8  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800504bf  lea     r8, [rbp+830h+var_850]
0x1800504c3  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800504ca  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800504d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504d6  jmp     short loc_1800504DB
0x1800504d8  mov     rbx, r13
0x1800504db  movups  xmm0, xmmword ptr [rdi]
0x1800504de  lea     rcx, [rsp+930h+var_8F0]; Buf1
0x1800504e3  movdqu  [rsp+930h+var_8F0], xmm0
0x1800504e9  call    RasSrvrStart
0x1800504ee  test    eax, eax
0x1800504f0  jz      loc_18005082E
0x1800504f6  cmp     qword ptr cs:xmmword_1800C9740, r13
0x1800504fd  jz      loc_18005082E
0x180050503  lea     rdx, aRassrvrstartFa; "RasSrvrStart failed and returned %d"
0x18005050a  jmp     loc_1800507F1
0x18005050f  test    r9d, r9d
0x180050512  jnz     loc_18005082E
0x180050518  movups  xmm0, xmmword ptr [rdi]
0x18005051b  lea     rcx, [rsp+930h+var_8F0]
0x180050520  movdqu  [rsp+930h+var_8F0], xmm0
0x180050526  call    RasReleaseRoutingDomainAddressPool
0x18005052b  test    eax, eax
0x18005052d  jz      loc_18005082E
0x180050533  cmp     qword ptr cs:xmmword_1800C9740, r13
0x18005053a  jz      loc_18005082E
0x180050540  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x180050547  jmp     loc_1800507F1
0x18005054c  movups  xmm0, xmmword ptr [rdi]
0x18005054f  lea     r8, [rsp+930h+var_8C8]
0x180050554  mov     edx, 1
0x180050559  lea     rcx, [rsp+930h+var_8F0]
0x18005055e  movdqu  [rsp+930h+var_8F0], xmm0
0x180050564  call    RasGetRoutingDomainAddressPool
0x180050569  xor     esi, esi
0x18005056b  mov     r15d, eax
0x18005056e  test    eax, eax
0x180050570  setz    sil
0x180050574  test    eax, eax
0x180050576  jnz     short loc_180050586
0x180050578  mov     rcx, [rsp+930h+var_8C8]
0x18005057d  test    rcx, rcx
0x180050580  jz      short loc_180050586
0x180050582  mov     r14, [rcx+30h]
0x180050586  mov     eax, dword ptr [rsp+930h+Data]
0x18005058a  cmp     r13d, eax
0x18005058d  jnz     short loc_1800505E2
0x18005058f  xor     r13d, r13d
0x180050592  test    eax, eax
0x180050594  jnz     short loc_1800505B0
0x180050596  mov     rdx, rbx
0x180050599  mov     rcx, r14
0x18005059c  call    RasStatAddrPoolsDiffer
0x1800505a1  test    eax, eax
0x1800505a3  jnz     short loc_1800505E5
0x1800505a5  cmp     dword ptr [rsp+930h+Data], r13d
0x1800505aa  jz      loc_18005073B
0x1800505b0  cmp     r12d, dword ptr cs:qword_1800C98F0+4
0x1800505b7  jnz     short loc_1800505E5
0x1800505b9  test    r12d, r12d
0x1800505bc  jz      loc_18005073B
0x1800505c2  mov     r8d, 10h; Size
0x1800505c8  lea     rdx, Buf2; Buf2
0x1800505cf  lea     rcx, [rsp+930h+Buf1]; Buf1
0x1800505d4  call    memcmp_0
0x1800505d9  test    eax, eax
0x1800505db  jnz     short loc_1800505E5
0x1800505dd  jmp     loc_18005073B
0x1800505e2  xor     r13d, r13d
0x1800505e5  test    r15d, r15d
0x1800505e8  jnz     short loc_180050645
0x1800505ea  movups  xmm0, xmmword ptr [rdi]
0x1800505ed  lea     rcx, [rsp+930h+var_8F0]
0x1800505f2  movdqu  [rsp+930h+var_8F0], xmm0
0x1800505f8  call    RasReleaseRoutingDomainAddressPool
0x1800505fd  test    eax, eax
0x1800505ff  jz      short loc_180050642
0x180050601  cmp     qword ptr cs:xmmword_1800C9740, r13
0x180050608  jz      short loc_180050645
0x18005060a  mov     r8d, eax
0x18005060d  mov     word ptr [rbp+830h+var_850], r13w
0x180050612  lea     rdx, aRasreleaserout; "RasReleaseRoutingDomainAddressPool fail"...
0x180050619  lea     rcx, [rbp+830h+var_850]
0x18005061d  call    FormatRRASErrorString
0x180050622  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180050629  lea     r8, [rbp+830h+var_850]
0x18005062d  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180050634  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
  ... truncated ...
```
